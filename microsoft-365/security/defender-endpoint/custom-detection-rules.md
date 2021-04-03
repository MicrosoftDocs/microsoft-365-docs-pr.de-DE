---
title: Erstellen von benutzerdefinierten Erkennungsregeln in Microsoft Defender ATP
ms.reviewer: ''
description: Erfahren Sie, wie Sie benutzerdefinierte Erkennungsregeln basierend auf erweiterten Suchabfragen erstellen.
keywords: Benutzerdefinierte Erkennungen, erstellen, verwalten, Warnungen, bearbeiten, bei Bedarf ausführen, Häufigkeit, Intervall, Erkennungsregeln, erweiterte Suche, Suche, Abfrage, Reaktionsaktionen, Mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 15dec5396a5ba95fe3ec7af5f9a72bbf15e07140
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500494"
---
# <a name="create-custom-detection-rules"></a>Erstellen von benutzerdefinierten Erkennungsregeln

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Mit benutzerdefinierten [](advanced-hunting-overview.md) Erkennungsregeln, die aus erweiterten Suchabfragen erstellt wurden, können Sie verschiedene Ereignisse und Systemzustände proaktiv überwachen, einschließlich mutmaßlicher Verletzungsaktivitäten und falsch konfigurierter Geräte. Sie können festlegen, dass sie in regelmäßigen Intervallen ausgeführt werden, Warnungen generieren und Reaktionsaktionen ausführen, wenn Übereinstimmungen angezeigt werden.

In diesem Artikel erfahren Sie, wie Sie neue benutzerdefinierte Erkennungsregeln erstellen. Weitere [Informationen finden Sie unter Anzeigen und Verwalten vorhandener Regeln.](custom-detections-manage.md)

> [!NOTE]
> Zum Erstellen oder Verwalten von benutzerdefinierten Erkennungen muss [Ihre Rolle](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) über die Berechtigung zum Verwalten **von Sicherheitseinstellungen** verfügen.

## <a name="1-prepare-the-query"></a>1. Bereiten Sie die Abfrage vor.

Wechseln Sie im Microsoft Defender Security Center zu **Erweiterte Suche,** und wählen Sie eine vorhandene Abfrage aus, oder erstellen Sie eine neue Abfrage. Wenn Sie eine neue Abfrage verwenden, führen Sie die Abfrage aus, um Fehler zu identifizieren und mögliche Ergebnisse zu verstehen.

>[!IMPORTANT]
>Damit der Dienst nicht zu viele Warnungen zurücksent, ist jede Regel auf die Generierung von nur 100 Warnungen beschränkt, wenn sie ausgeführt wird. Bevor Sie eine Regel erstellen, optimieren Sie Ihre Abfrage, um Warnungen für normale, täglich ausgeführte Aktivitäten zu vermeiden.

### <a name="required-columns-in-the-query-results"></a>Erforderliche Spalten in den Abfrageergebnissen

Um eine Abfrage für eine benutzerdefinierte Erkennungsregel zu verwenden, muss die Abfrage die folgenden Spalten zurückgeben:

- `Timestamp`
- `DeviceId`
- `ReportId`

Einfache Abfragen, z. B. solche, die den Operator or nicht zum Anpassen oder Aggregieren von Ergebnissen verwenden, geben in der Regel `project` `summarize` diese allgemeinen Spalten zurück.

Es gibt verschiedene Möglichkeiten, um sicherzustellen, dass komplexere Abfragen diese Spalten zurückgeben. Wenn Sie es z. B. vorziehen, nach zu aggregieren und zu zählen, können Sie sie trotzdem zurückgeben und aus dem neuesten Ereignis mit den `DeviceId` `Timestamp` einzelnen Geräten `ReportId` abrufen.

Die folgende Beispielabfrage zählt die Anzahl eindeutiger Geräte ( ) mit Antivirenerkennungen und verwendet diese, um nur die Geräte mit mehr als fünf Erkennungen `DeviceId` zu finden. Zum Zurückgeben der neuesten `Timestamp` und der entsprechenden wird der Operator mit der Funktion `ReportId` `summarize` `arg_max` verwendet.

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Legen Sie für eine bessere Abfrageleistung einen Zeitfilter fest, der der vorgesehenen Ausführungshäufigkeit für die Regel entspricht. Da die am wenigsten häufige Ausführung alle 24 Stunden ist, werden alle neuen Daten durch die Filterung für den letzten Tag verdeckt.

## <a name="2-create-a-new-rule-and-provide-alert-details"></a>2. Erstellen Sie eine neue Regel, und geben Sie Warnungsdetails an.

Wählen Sie mit der Abfrage  im Abfrage-Editor Erkennungsregel erstellen aus, und geben Sie die folgenden Warnungsdetails an:

- **Erkennungsname**– Name der Erkennungsregel
- **Häufigkeit**– Intervall zum Ausführen der Abfrage und Ausführen von Aktionen. [Weitere Anleitungen finden Sie weiter unten.](#rule-frequency)
- **Warnungstitel**– Titel, der mit von der Regel ausgelösten Warnungen angezeigt wird
- **Schweregrad**– potenzielles Risiko der durch die Regel identifizierten Komponente oder Aktivität. [Informationen zu Warnungsschweregraden](alerts-queue.md#severity)
- **Kategorie**– Typ der Bedrohungskomponente oder -aktivität, falls welche. [Informationen zu Warnungskategorien](alerts-queue.md#understanding-alert-categories)
- **MITRE ATT&CK-Techniken**– eine oder mehrere Angriffstechniken, die von der Regel identifiziert werden, wie im MITRE ATT&CK-Framework dokumentiert. Dieser Abschnitt ist nicht mit bestimmten Warnungskategorien wie Schadsoftware, Ransomware, verdächtigen Aktivitäten und unerwünschter Software verfügbar.
- **Beschreibung**– weitere Informationen zu der durch die Regel identifizierten Komponente oder Aktivität 
- **Empfohlene Aktionen**– zusätzliche Aktionen, die Reaktionshelfer als Reaktion auf eine Warnung ausführen können

Weitere Informationen zur Anzeige von Warnungsdetails finden Sie [in der Warnungswarteschlange](alerts-queue.md).

### <a name="rule-frequency"></a>Regelhäufigkeit

Beim Speichern wird sofort eine neue benutzerdefinierte Erkennungsregel ausgeführt und auf Übereinstimmungen aus den letzten 30 Tagen der Daten überprüft. Die Regel wird dann in festen Intervallen und Nachschlagedauern basierend auf der von Ihnen festgelegten Häufigkeit erneut ausgeführt:

- **Alle 24 Stunden**– wird alle 24 Stunden ausgeführt und überprüft Daten aus den letzten 30 Tagen
- **Alle 12 Stunden**– wird alle 12 Stunden ausgeführt und überprüft Daten aus den letzten 24 Stunden
- **Alle 3 Stunden**– wird alle 3 Stunden ausgeführt und überprüft Daten aus den letzten 6 Stunden
- **Jede Stunde**– wird stündlich ausgeführt und überprüft Daten aus den letzten 2 Stunden

Wenn Sie eine Regel bearbeiten, wird sie mit den angewendeten Änderungen in der nächsten Laufzeit ausgeführt, die entsprechend der von Ihnen festgelegten Häufigkeit geplant ist.


> [!TIP]
> Match the time filters in your query with the lookback duration. Ergebnisse außerhalb der Lookbackdauer werden ignoriert.

Wählen Sie die Häufigkeit aus, die mit der Überwachungshäufigkeit der Erkennungen zusammen passt, und berücksichtigen Sie die Kapazität Ihrer Organisation, auf die Warnungen zu reagieren.

## <a name="3-choose-the-impacted-entities"></a>3. Wählen Sie die betroffenen Entitäten aus.

Identifizieren Sie die Spalten in den Abfrageergebnissen, in denen Sie erwarten, dass sie die haupt betroffene oder betroffene Entität finden. Eine Abfrage kann z. B. Geräte- und Benutzer-IDs zurückgeben. Die Identifizierung, welche dieser Spalten die hauptsprallte Entität darstellen, hilft dem Dienst, relevante Warnungen zu aggregieren, Vorfälle zu korrelieren und Zielreaktionsaktionen zu ergreifen.

Sie können für jeden Entitätstyp nur eine Spalte auswählen. Spalten, die von Ihrer Abfrage nicht zurückgegeben werden, können nicht ausgewählt werden.

## <a name="4-specify-actions"></a>4. Geben Sie Aktionen an.

Ihre benutzerdefinierte Erkennungsregel kann automatisch Aktionen für Dateien oder Geräte ausführen, die von der Abfrage zurückgegeben werden.

### <a name="actions-on-devices"></a>Aktionen auf Geräten

Diese Aktionen werden auf Geräte in der `DeviceId` Spalte der Abfrageergebnisse angewendet:

- **Gerät isolieren**– wendet die vollständige Netzwerkisolation an und verhindert, dass das Gerät eine Verbindung mit einer Anwendung oder einem Dienst herstellen kann, mit Ausnahme des Defender for Endpoint-Diensts. [Weitere Informationen zur Geräteisolation](respond-machine-alerts.md#isolate-devices-from-the-network)
- **Untersuchungspaket sammeln**– Sammelt Geräteinformationen in einer ZIP-Datei. [Weitere Informationen zum Untersuchungspaket](respond-machine-alerts.md#collect-investigation-package-from-devices)
- **Ausführen eines Antivirenscans**– führt eine vollständige Microsoft Defender Antivirus-Überprüfung auf dem Gerät aus.
- **Initiieren der** Untersuchung – startet [eine automatisierte Untersuchung](automated-investigations.md) auf dem Gerät
- **Einschränken der App-Ausführung**– legt Einschränkungen auf dem Gerät fest, damit nur Dateien ausgeführt werden können, die mit einem von Microsoft ausgestellten Zertifikat signiert sind. [Weitere Informationen zum Einschränken der App-Ausführung](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a>Aktionen für Dateien

Diese Aktionen werden auf Dateien in der Spalte oder in `SHA1` `InitiatingProcessSHA1` den Abfrageergebnissen angewendet:

- **Zulassen/Blockieren**– fügt die [](manage-indicators.md) Datei automatisch zu Ihrer benutzerdefinierten Indikatorliste hinzu, sodass sie immer ausgeführt oder blockiert werden kann. Sie können den Umfang dieser Aktion so festlegen, dass sie nur für ausgewählte Gerätegruppen verwendet wird. Dieser Bereich ist unabhängig vom Bereich der Regel.
- **Quarantänedatei**– löscht die Datei vom aktuellen Speicherort und platziert eine Kopie in Quarantäne.

### <a name="actions-on-users"></a>Aktionen für Benutzer

- **Benutzer als gefährdet kennzeichnen**– legt die Risikostufe des Benutzers in Azure Active Directory auf "hoch" fest und löst die entsprechenden Identitätsschutzrichtlinien [aus.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)

## <a name="5-set-the-rule-scope"></a>5. Festlegen des Regelbereichs.

Legen Sie den Bereich fest, um anzugeben, welche Geräte von der Regel abgedeckt werden:

- Alle Geräte
- Bestimmte Gerätegruppen

Nur Daten von Geräten im Bereich werden abgefragt. Außerdem werden Aktionen nur auf diesen Geräten ergriffen.

## <a name="6-review-and-turn-on-the-rule"></a>6. Überprüfen und aktivieren Sie die Regel.

Nachdem Sie die Regel überprüft haben, wählen **Sie Erstellen aus,** um sie zu speichern. Die benutzerdefinierte Erkennungsregel wird sofort ausgeführt. Es wird basierend auf der konfigurierten Häufigkeit erneut ausgeführt, um nach Übereinstimmungen zu suchen, Warnungen zu generieren und Reaktionsaktionen zu ergreifen.

Sie können [benutzerdefinierte Erkennungsregeln](custom-detections-manage.md)anzeigen und verwalten, ihre vorherigen Läufe überprüfen und die ausgelösten Warnungen überprüfen. Sie können auch eine Regel bei Bedarf ausführen und ändern.

## <a name="related-topics"></a>Verwandte Themen

- [Anzeigen und Verwalten von benutzerdefinierten Erkennungsregeln](custom-detections-manage.md)
- [Benutzerdefinierte Erkennungen – Übersicht](overview-custom-detections.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Erlernen der Abfragesprache für die erweiterte Suche](advanced-hunting-query-language.md)
- [Anzeigen und Organisieren von Warnungen](alerts-queue.md)
