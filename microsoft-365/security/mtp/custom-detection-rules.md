---
title: Erstellen und Verwalten von benutzerdefinierten Erkennungsregeln in Microsoft Threat Protection
description: Hier erfahren Sie, wie Sie benutzerdefinierte Erkennungsregeln basierend auf erweiterten Jagd Abfragen erstellen und verwalten können.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Regeln, Schema, Kusto, Microsoft 365, Microsoft Threat Protection, RBAC, Permissions, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: a0fb30915cac875e1e5278ecec2b3a1c65685f37
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412526"
---
# <a name="create-and-manage-custom-detections-rules"></a>Erstellen und Verwalten von benutzerdefinierten Erkennungsregeln

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Benutzerdefinierte Erkennungsregeln sind Regeln, die Sie mit [erweiterten Jagd](advanced-hunting-overview.md) Abfragen entwerfen und optimieren können. Mit diesen Regeln können Sie verschiedene Ereignisse und Systemzustände proaktiv überwachen, einschließlich mutmaßlicher Sicherheitsverletzungen und falsch konfigurierter Endpunkte. Sie können festlegen, dass Sie in regelmäßigen Intervallen ausgeführt werden, indem Sie Warnungen generieren und Reaktions Aktionen ausführen, wenn Übereinstimmungen vorliegen.

## <a name="required-permissions-for-managing-custom-detections"></a>Erforderliche Berechtigungen zum Verwalten benutzerdefinierter Erkennungen

Um benutzerdefinierte Erkennungen zu verwalten, müssen Sie eine der folgenden Rollen zugewiesen werden:

- **Sicherheitsadministrator**– Benutzer mit dieser [Azure Active Directory Rolle](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) können Sicherheitseinstellungen im Microsoft 365 Security Center und anderen Portalen und Diensten verwalten.

- **Sicherheits Operator**– Benutzer mit dieser [Azure Active Directory-Rolle](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) können Warnungen verwalten und über einen globalen schreibgeschützten Zugriff auf sicherheitsbezogene Features verfügen, einschließlich aller Informationen im Microsoft 365 Security Center. Diese Rolle reicht aus, um benutzerdefinierte Erkennungen nur dann zu verwalten, wenn die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) in Microsoft Defender ATP deaktiviert ist. Wenn Sie RBAC konfiguriert haben, benötigen Sie auch die Berechtigung **Sicherheitseinstellungen verwalten** für Microsoft Defender ATP.

Zum Verwalten der erforderlichen Berechtigungen kann ein **globaler Administrator** folgende Schritte durchführen:

- Weisen Sie die Rolle " **Sicherheitsadministrator** " oder " **Sicherheits Operator** " im [Microsoft 365 Admin Center](https://admin.microsoft.com/) unter **roles**  >  **Security Admin**zu.
- Überprüfen Sie die RBAC-Einstellungen für Microsoft Defender ATP im [Microsoft Defender Security Center](https://securitycenter.windows.com/) unter **Einstellungen**  >  **Berechtigungs**  >  **Rollen**. Wählen Sie die entsprechende Rolle aus, um die Berechtigung **Sicherheitseinstellungen verwalten** zuzuweisen.

> [!NOTE]
> Zum Verwalten von benutzerdefinierten Erkennungen benötigen **Sicherheits Operatoren** die Berechtigung **Sicherheitseinstellungen verwalten** in Microsoft Defender ATP, wenn RBAC aktiviert ist.

## <a name="create-a-custom-detection-rule"></a>Erstellen einer benutzerdefinierten Erkennungsregel
### <a name="1-prepare-the-query"></a>1. bereiten Sie die Abfrage vor.

Wechseln Sie im Microsoft 365 Security Center zu **Advanced Hunting** , und wählen Sie eine vorhandene Abfrage aus, oder erstellen Sie eine neue Abfrage. Wenn Sie eine neue Abfrage verwenden, führen Sie die Abfrage aus, um Fehler zu identifizieren und mögliche Ergebnisse zu verstehen.

>[!IMPORTANT]
>Um zu verhindern, dass der Dienst zu viele Warnungen zurückgibt, ist jede Regel darauf beschränkt, bei der Ausführung nur 100 Warnungen zu generieren. Vor dem Erstellen einer Regel sollten Sie die Abfrage optimieren, um Warnungen für normale tägliche Aktivitäten zu vermeiden.


#### <a name="required-columns-in-the-query-results"></a>Erforderliche Spalten in den Abfrageergebnissen
Um eine benutzerdefinierte Erkennungsregel zu erstellen, muss die Abfrage die folgenden Spalten zurückgeben:

- `Timestamp`– wird zum Festlegen des Zeitstempels für generierte Warnungen verwendet.
- `ReportId`– aktiviert Nachschlagevorgänge für die ursprünglichen Datensätze
- Eine der folgenden Spalten, die bestimmte Geräte, Benutzer oder Postfächer identifizieren:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (Umschlagabsender oder Return-Path Adresse)
    - `SenderMailFromAddress` (Absenderadresse wird vom e-Mail-Client angezeigt)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>Die Unterstützung zusätzlicher Entitäten wird hinzugefügt, wenn dem [erweiterten Jagd Schema](advanced-hunting-schema-tables.md)neue Tabellen hinzugefügt werden.

Einfache Abfragen, beispielsweise solche, die den `project` or `summarize` -Operator nicht zum Anpassen oder Aggregieren von Ergebnissen verwenden, geben normalerweise diese allgemeinen Spalten zurück.

Es gibt verschiedene Möglichkeiten, um sicherzustellen, dass komplexere Abfragen diese Spalten zurückgeben. Wenn Sie beispielsweise eine Aggregation und eine Zählung nach Entität in einer Spalte wie, möchten `DeviceId` , können Sie immer noch zurückkehren `Timestamp` und `ReportId` diese von dem letzten Ereignis abrufen, das die einzelnen Eindeutigkeiten beinhaltet `DeviceId` .

Die folgende Beispielabfrage zählt die Anzahl der eindeutigen Geräte ( `DeviceId` ) mit Antivirus-Erkennungen und verwendet diese Anzahl, um nur die Geräte mit mehr als fünf Erkennungen zu finden. Um den neuesten `Timestamp` und den entsprechenden zurückzugeben `ReportId` , wird der `summarize` Operator mit der- `arg_max` Funktion verwendet.

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Für eine bessere Abfrageleistung legen Sie einen Zeitfilter fest, der mit der beabsichtigten Ausführungshäufigkeit für die Regel übereinstimmt. Da die am wenigsten häufige Ausführung alle _24 Stunden_erfolgt, werden die Filter für den letzten Tag alle neuen Daten umfassen.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Erstellen Sie eine neue Regel, und geben Sie Warnungsdetails an.

Wählen Sie mit der Abfrage im Abfrage-Editor **Erkennungsregel erstellen** aus, und geben Sie die folgenden Warnungsdetails an:

- **Erkennungsname**– Name der Erkennungsregel
- **Häufigkeit**– Intervall zum Ausführen der Abfrage und ergreifen von Aktionen. [Weitere Anleitungen finden Sie weiter unten.](#rule-frequency)
- **Warnungs Titel**– Titel mit Warnungen, die von der Regel ausgelöst werden
- **Schweregrad**– potenzielles Risiko der von der Regel identifizierten Komponente oder Aktivität
- **Category**– Bedrohungs Komponente oder Aktivität, die von der Regel identifiziert wird
- **Mitra ATT&ck Techniques**– eine oder mehrere von der Regel identifizierte Angriffstechniken, wie im [Mitra ATT&ck-Framework](https://attack.mitre.org/)dokumentiert. Dieser Abschnitt ist für bestimmte Warnungs Kategorien verborgen, einschließlich Schadsoftware, Ransomware, verdächtiger Aktivitäten und unerwünschter Software.
- **Description**– Weitere Informationen zur von der Regel identifizierten Komponente oder Aktivität 
- **Empfohlene Aktionen**– zusätzliche Aktionen, die Responder als Reaktion auf eine Warnung ausführen können

#### <a name="rule-frequency"></a>Regel Häufigkeit
Wenn Sie eine neue Regel speichern oder bearbeiten, wird Sie ausgeführt und überprüft, ob die Daten in den letzten 30 Tagen übereinstimmen. Die Regel wird dann in festen Intervallen erneut ausgeführt, wobei eine Lookback Dauer basierend auf der von Ihnen gewählten Häufigkeit angewendet wird:

- **Alle 24 Stunden**: wird alle 24 Stunden ausgeführt, und die Daten der letzten 30 Tage werden überprüft.
- **Alle 12 Stunden**-wird alle 12 Stunden ausgeführt, und die Daten der letzten 24 Stunden werden überprüft.
- **Alle 3 Stunden**: wird alle 3 Stunden ausgeführt, und die Daten aus den letzten 6 Stunden werden überprüft.
- **Stündlich – stündlich**ausgeführt, Daten aus den letzten 2 Stunden werden überprüft

>[!TIP]
> Passen Sie die Zeitfilter in Ihrer Abfrage mit der Lookback-Dauer an. Ergebnisse außerhalb der Lookback-Dauer werden ignoriert.  

Wählen Sie die Häufigkeit aus, mit der die genaue Überwachung der Erkennungen übereinstimmen soll. Überprüfen Sie die Kapazität Ihrer Organisation, auf die Warnungen zu reagieren.

### <a name="3-choose-the-impacted-entities"></a>3. Wählen Sie die betroffenen Entitäten aus.
Identifizieren Sie die Spalten in den Abfrageergebnissen, bei denen Sie davon ausgehen, dass Sie die Hauptbetroffene oder betroffene Entität finden. Beispielsweise kann eine Abfrage Absender ( `SenderFromAddress` oder `SenderMailFromAddress` )-und Empfängeradressen ( `RecipientEmailAddress` ) zurückgeben. Das Identifizieren der Spalten, die die Hauptbetroffene Entität darstellen, hilft dem Dienst, relevante Warnungen zu aggregieren, Vorfälle und Ziel Antwort Aktionen zu korrelieren.

Sie können für jeden Entitätstyp (Postfach, Benutzer oder Gerät) nur eine Spalte auswählen. Spalten, die nicht von der Abfrage zurückgegeben werden, können nicht ausgewählt werden.

### <a name="4-specify-actions"></a>4. Geben Sie Aktionen an.
Ihre benutzerdefinierte Erkennungsregel kann automatisch Aktionen für Geräte, Dateien oder Benutzer durchführen, die von der Abfrage zurückgegeben werden.

#### <a name="actions-on-devices"></a>Aktionen auf Geräten
Diese Aktionen werden auf Geräte in der `DeviceId` Spalte der Abfrageergebnisse angewendet:
- **Isolier Gerät**– mit Microsoft Defender ATP wird die vollständige Netzwerkisolation angewendet, sodass das Gerät nicht mit einer Anwendung oder einem Dienst verbunden werden kann. [Weitere Informationen zur Isolierung von Microsoft Defender ATP-Computern](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Ermittlungs Paket sammeln**– sammelt Geräteinformationen in einer ZIP-Datei. [Weitere Informationen zum Microsoft Defender ATP-Ermittlungs Paket](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Ausführen eines Antivirus-Scans**– führt eine vollständige Windows Defender-Antivirus-Überprüfung auf dem Gerät aus.
- **Einleitung einer Untersuchung**– initiiert eine [automatisierte Untersuchung](mtp-autoir.md) auf dem Gerät
- **App-Ausführung einschränken**– legt Einschränkungen für das Gerät fest, damit nur Dateien ausgeführt werden können, die mit einem von Microsoft ausgestellten Zertifikat signiert sind. [Weitere Informationen zu app-Einschränkungen mit Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Aktionen für Dateien
Wenn diese Option ausgewählt ist, können Sie die Aktion " **Quarantänedatei** " auf Dateien in der `SHA1` , `InitiatingProcessSHA1` , `SHA256` oder `InitiatingProcessSHA256` Spalte der Abfrageergebnisse anwenden. Mit dieser Aktion wird die Datei von Ihrem aktuellen Speicherort gelöscht und eine Kopie in Quarantäne platziert.

#### <a name="actions-on-users"></a>Aktionen für Benutzer
Wenn diese Option ausgewählt ist, wird die Aktion **Benutzer als kompromittiert markieren** für Benutzer in `AccountObjectId` der `InitiatingProcessAccountObjectId` Spalte, oder der `RecipientObjectId` Abfrageergebnisse verwendet. Mit dieser Aktion wird die Benutzer Risikostufe in Azure Active Directory auf "hoch" festgelegt, sodass entsprechende [Identitätsschutz Richtlinien](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)ausgelöst werden.

> [!NOTE]
> Die Aktion zulassen oder blockieren für benutzerdefinierte Erkennungsregeln wird derzeit von Microsoft Threat Protection nicht unterstützt.

### <a name="5-set-the-rule-scope"></a>5. Legen Sie den Regelbereich fest.
Legen Sie den Bereich fest, um anzugeben, welche Geräte von der Regel abgedeckt werden. Der Bereich beeinflusst Regeln, die Geräte überprüfen, und wirkt sich nicht auf Regeln aus, die nur Postfächer und Benutzerkonten oder Identitäten überprüfen.

Beim Festlegen des Bereichs können Sie Folgendes auswählen:

- Alle Geräte
- Bestimmte Gerätegruppen

Es werden nur Daten von Geräten im Bereich abgefragt. Außerdem werden Aktionen nur auf diesen Geräten ausgeführt.

### <a name="6-review-and-turn-on-the-rule"></a>6. überprüfen und aktivieren Sie die Regel.
Wählen Sie nach der Überprüfung der Regel **Create** aus, um Sie zu speichern. Die benutzerdefinierte Erkennungsregel wird sofort ausgeführt. Er wird basierend auf der konfigurierten Häufigkeit erneut ausgeführt, um nach Übereinstimmungen zu suchen, Warnungen zu generieren und Reaktions Aktionen durchführen zu können.

## <a name="manage-existing-custom-detection-rules"></a>Verwalten vorhandener benutzerdefinierter Erkennungsregeln
Sie können die Liste der vorhandenen benutzerdefinierten Erkennungsregeln anzeigen, Ihre vorherigen Ausführungen überprüfen und die von Ihnen ausgelösten Warnungen überprüfen. Sie können auch eine Regel bei Bedarf ausführen und diese ändern.

### <a name="view-existing-rules"></a>Anzeigen vorhandener Regeln

Um alle vorhandenen benutzerdefinierten Erkennungsregeln anzuzeigen, navigieren **Hunting**Sie zu  >  **benutzerdefinierten**Erkennungen für die Suche. Auf der Seite werden alle Regeln mit den folgenden Ausführungsinformationen aufgelistet:

- **Letzte Ausführung**: beim letzten Ausführen einer Regel, um nach Abfrage Übereinstimmungen zu suchen und Warnungen zu generieren
- **Status der letzten Ausführung**– gibt an, ob eine Regel erfolgreich ausgeführt wurde
- **Nächster Durchlauf**– die nächste geplante Ausführung
- **Status**– gibt an, ob eine Regel aktiviert oder deaktiviert wurde

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Anzeigen von Regeldetails, Regel ändern und Ausführen einer Regel

Wenn Sie umfassende Informationen zu einer benutzerdefinierten Erkennungsregel **anzeigen möchten,** navigieren Sie zu benutzerdefinierten Erkennungs Erkennungen,  >  **Custom detections** und wählen Sie dann den Namen der Regel aus. Sie können dann allgemeine Informationen zur Regel anzeigen, einschließlich der Informationen über den Ausführungsstatus und den Bereich. Die Seite enthält auch die Liste der ausgelösten Warnungen und Aktionen.

![Seite "Details zur benutzerdefinierten Erkennungsregel"](../../media/custom-detection-details.png)<br>
*Details der benutzerdefinierten Erkennungsregel*

Auf dieser Seite können Sie auch die folgenden Aktionen für die Regel ausführen:

- **Ausführen**– die Regel wird sofort ausgeführt. Dadurch wird auch das Intervall für die nächste Ausführung zurückgesetzt.
- **Bearbeiten**– Ändern der Regel, ohne die Abfrage zu ändern
- **Abfrage ändern**– Bearbeiten der Abfrage in erweiterter Suche
- **Einschalten**  /  **Deaktivieren**– Aktivieren der Regel oder Beenden der Ausführung
- **Delete**– deaktivieren Sie die Regel, und entfernen Sie Sie.

### <a name="view-and-manage-triggered-alerts"></a>Anzeigen und Verwalten von ausgelösten Warnungen

Wechseln Sie auf dem Bildschirm Regel**Details (**  >  **benutzerdefinierte Erkennungs Erkennungen**  >  **[Regelname]**) zu **ausgelöste Warnungen**, die die Warnungen auflisten, die von Übereinstimmungen mit der Regel generiert werden. Wählen Sie eine Warnung aus, um detaillierte Informationen dazu anzuzeigen, und führen Sie die folgenden Aktionen aus:

- Verwalten der Warnung durch Festlegen des Status und der Klassifizierung (true oder false Alert)
- Verknüpfen der Warnung mit einem Vorfall
- Ausführen der Abfrage, die die Warnung bei Advanced Hunting ausgelöst hat

### <a name="review-actions"></a>Überprüfen von Aktionen
Wechseln Sie im Bildschirm Regeldetails (**Jagd**  >  **benutzerdefinierte Erkennungen**  >  **[Regelname]**) zu **ausgelöste Aktionen**, die die auf Übereinstimmungen mit der Regel ausgeführten Aktionen auflisten.

>[!TIP]
>Um Informationen schnell anzuzeigen und Aktionen für ein Element in einer Tabelle durchführen zu können, verwenden Sie die Auswahlspalte [&#10003;] Links in der Tabelle.

## <a name="related-topic"></a>Verwandtes Thema
- [Benutzerdefinierte Erkennungen – Übersicht](custom-detections-overview.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Erlernen der Abfragesprache für die erweiterte Suche](advanced-hunting-query-language.md)
