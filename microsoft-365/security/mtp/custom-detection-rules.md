---
title: Erstellen und Verwalten von benutzerdefinierten Erkennungsregeln in Microsoft 365 Defender
description: Hier erfahren Sie, wie Sie benutzerdefinierte Erkennungsregeln basierend auf erweiterten Suchabfragen erstellen und verwalten.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Regeln, Schema, Kusto, Microsoft 365, Microsoft Threat Protection, RBAC, Berechtigungen, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d58292f658446259bfab5b1b55c8b462d081421c
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080623"
---
# <a name="create-and-manage-custom-detections-rules"></a>Erstellen und Verwalten von benutzerdefinierten Erkennungsregeln

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Benutzerdefinierte Erkennungsregeln sind Regeln, die Sie mithilfe erweiterter [Suchabfragen entwerfen und](advanced-hunting-overview.md) optimieren können. Mit diesen Regeln können Sie proaktiv verschiedene Ereignisse und Systemzustände überwachen, einschließlich mutmaßlicher Sicherheitsverletzungen und falsch konfigurierter Endpunkte. Sie können festlegen, dass sie in regelmäßigen Intervallen ausgeführt werden, Warnungen generieren und bei Übereinstimmungen Reaktionsaktionen ausführen.

## <a name="required-permissions-for-managing-custom-detections"></a>Erforderliche Berechtigungen für die Verwaltung von benutzerdefinierten Erkennungen

Zum Verwalten von benutzerdefinierten Erkennungen muss Ihnen eine der folgenden Rollen zugewiesen sein:

- **Sicherheitsadministrator**– Benutzer mit dieser [Azure Active](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) Directory-Rolle können Sicherheitseinstellungen im Microsoft 365 Security Center und anderen Portalen und Diensten verwalten.

- **Sicherheitsoperator**– Benutzer mit dieser [Azure Active](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) Directory-Rolle können Warnungen verwalten und haben globalen schreibgeschützten Zugriff auf sicherheitsbezogene Features, einschließlich aller Informationen im Microsoft 365 Security Center. Diese Rolle ist nur dann für die Verwaltung von benutzerdefinierten Erkennungen ausreichend, wenn die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) in Microsoft Defender for Endpoint deaktiviert ist. Wenn Sie rbAC konfiguriert haben,  benötigen Sie auch die Berechtigung zum Verwalten von Sicherheitseinstellungen für Defender for Endpoint.

Um die erforderlichen Berechtigungen zu verwalten, kann **ein globaler Administrator:**

- Weisen Sie **die Rolle des Sicherheitsadministrators** oder der Sicherheitsoperatorrolle im Microsoft [365 Admin Center](https://admin.microsoft.com/) unter  **"Rollensicherheitsadministrator"**  >  **zu.**
- Überprüfen Sie die Einstellungen für die rollen rechte Zugriffsberechtigung für Microsoft Defender for Endpoint im [Microsoft Defender Security Center](https://securitycenter.windows.com/) unter **"Einstellungsberechtigungsrollen".**  >    >   Wählen Sie die entsprechende Rolle aus, um die Berechtigung zum Verwalten **von Sicherheitseinstellungen zu** erteilen.

> [!NOTE]
> Zum Verwalten von benutzerdefinierten Erkennungen benötigen Sicherheitsoperatoren die Berechtigung zum Verwalten von Sicherheitseinstellungen in Microsoft Defender for Endpoint, wenn rbAC aktiviert ist.  

## <a name="create-a-custom-detection-rule"></a>Erstellen einer benutzerdefinierten Erkennungsregel
### <a name="1-prepare-the-query"></a>1. Bereiten Sie die Abfrage vor.

Wechseln Sie im Microsoft 365 Security Center zur erweiterten Suche, und wählen Sie eine vorhandene Abfrage aus, oder erstellen Sie eine neue Abfrage.  Wenn Sie eine neue Abfrage verwenden, führen Sie die Abfrage aus, um Fehler zu identifizieren und mögliche Ergebnisse zu verstehen.

>[!IMPORTANT]
>Um zu verhindern, dass der Dienst zu viele Warnungen zurück gibt, ist jede Regel auf die Generierung von nur 100 Warnungen beschränkt, wenn sie ausgeführt wird. Optimieren Sie vor dem Erstellen einer Regel Ihre Abfrage, um Warnungen für normale, täglich ausgeführte Aktivitäten zu vermeiden.


#### <a name="required-columns-in-the-query-results"></a>Erforderliche Spalten in den Abfrageergebnissen
Zum Erstellen einer benutzerdefinierten Erkennungsregel muss die Abfrage die folgenden Spalten zurückgeben:

- `Timestamp`– wird verwendet, um den Zeitstempel für generierte Warnungen festlegen
- `ReportId`– ermöglicht Nachschlagearbeiten für die ursprünglichen Datensätze
- Eine der folgenden Spalten, die bestimmte Geräte, Benutzer oder Postfächer identifizieren:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (Umschlagsender oder Return-Path Adresse)
    - `SenderMailFromAddress` (Vom E-Mail-Client angezeigte Absenderadresse)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>Unterstützung für zusätzliche Entitäten wird hinzugefügt, wenn dem Schema für die erweiterte Suche neue Tabellen [hinzugefügt werden.](advanced-hunting-schema-tables.md)

Einfache Abfragen, z. B. solche, die den Oder-Operator nicht zum Anpassen oder Aggregieren von Ergebnissen verwenden, geben in der Regel `project` `summarize` diese allgemeinen Spalten zurück.

Es gibt verschiedene Möglichkeiten, um sicherzustellen, dass komplexere Abfragen diese Spalten zurückgeben. Wenn Sie es z. B. vorziehen, nach Entitäten unter einer Spalte wie zu aggregieren und zu zählen, können Sie sie trotzdem zurückgeben und aus dem neuesten Ereignis abrufen, das jedes eindeutige `DeviceId` `Timestamp` Ereignis `ReportId` `DeviceId` enthält.

Die folgende Beispielabfrage zählt die Anzahl der eindeutigen Geräte ( ) mit Antivirenerkennungen und verwendet diese Anzahl, um nur die Geräte mit mehr als `DeviceId` fünf Erkennungen zu finden. Um den neuesten und den entsprechenden Wert zurück zu geben, wird `Timestamp` der Operator mit der Funktion `ReportId` `summarize` `arg_max` verwendet.

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Um eine bessere Abfrageleistung zu erzielen, legen Sie einen Zeitfilter fest, der der beabsichtigten Ausführungshäufigkeit für die Regel entspricht. Da die am wenigsten häufige Ausführung _alle 24 Stunden_ ausgeführt wird, werden alle neuen Daten nach dem letzten Tag gefiltert.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Erstellen Sie eine neue Regel, und geben Sie Warnungsdetails an.

Wählen Sie mit der Abfrage im Abfrage-Editor die Option "Erkennungsregel **erstellen"** aus, und geben Sie die folgenden Warnungsdetails an:

- **Erkennungsname**– Name der Erkennungsregel
- **Häufigkeit**– Intervall für die Ausführung der Abfrage und das Ausführen von Aktionen. [Weitere Anleitungen finden Sie weiter unten](#rule-frequency)
- **Warnungstitel**– Titel mit von der Regel ausgelösten Warnungen
- **Schweregrad**– potenzielles Risiko der durch die Regel identifizierten Komponente oder Aktivität
- **Kategorie**– Bedrohungskomponente oder Aktivität, die durch die Regel identifiziert wird
- **MITRE ATT&-CK-Techniken**– eine oder mehrere Angriffstechniken, die von der Regel identifiziert werden, wie im [MITRE ATT&CK Framework dokumentiert.](https://attack.mitre.org/) Dieser Abschnitt ist für bestimmte Warnungskategorien ausgeblendet, z. B. Schadsoftware, Ransomware, verdächtige Aktivitäten und unerwünschte Software.
- **Beschreibung**– weitere Informationen zur Komponente oder Aktivität, die von der Regel identifiziert wird 
- **Empfohlene Aktionen**– zusätzliche Aktionen, die Responder als Reaktion auf eine Warnung ausführen können

#### <a name="rule-frequency"></a>Regelhäufigkeit
Wenn Sie eine neue Regel speichern oder bearbeiten, wird sie ausgeführt und sucht nach Übereinstimmungen aus den daten der letzten 30 Tage. Die Regel wird dann in festen Intervallen erneut ausgeführt, und es wird eine Lookbackdauer basierend auf der von Ihnen festgelegten Häufigkeit angewendet:

- **Alle 24 Stunden**– wird alle 24 Stunden ausgeführt und überprüft Daten aus den letzten 30 Tagen
- **Alle 12 Stunden**– wird alle 12 Stunden ausgeführt und überprüft Dabei werden Daten aus den letzten 24 Stunden überprüft.
- **Alle 3 Stunden –** wird alle 3 Stunden ausgeführt und überprüft Dabei werden Daten aus den letzten 6 Stunden überprüft.
- **Jede Stunde**– wird stündlich ausgeführt und überprüft Daten aus den letzten 2 Stunden

>[!TIP]
> Match the time filters in your query with the lookback duration. Ergebnisse außerhalb der Lookbackdauer werden ignoriert.  

Wählen Sie die Häufigkeit aus, mit der die Erkennungen überwacht werden. Berücksichtigen Sie die Kapazität Ihrer Organisation, auf die Warnungen zu reagieren.

### <a name="3-choose-the-impacted-entities"></a>3. Wählen Sie die betroffenen Entitäten aus.
Identifizieren Sie die Spalten in den Abfrageergebnissen, in denen Sie erwarten, die am stärksten betroffene oder betroffene Entität zu finden. Beispielsweise kann eine Abfrage Absender- ( oder ) und `SenderFromAddress` `SenderMailFromAddress` Empfängeradressen ( `RecipientEmailAddress` ) zurückgeben. Die Identifizierung, welche dieser Spalten die am wichtigsten betroffenen Entitäten darstellen, hilft dem Dienst, relevante Warnungen zu aggregieren, Vorfälle zu korrelieren und Reaktionsaktionen zu erreichen.

Sie können für jeden Entitätstyp (Postfach, Benutzer oder Gerät) nur eine Spalte auswählen. Spalten, die nicht von der Abfrage zurückgegeben werden, können nicht ausgewählt werden.

### <a name="4-specify-actions"></a>4. Angeben von Aktionen.
Ihre benutzerdefinierte Erkennungsregel kann automatisch Aktionen auf Geräten, Dateien oder Benutzern ausführen, die von der Abfrage zurückgegeben werden.

#### <a name="actions-on-devices"></a>Aktionen auf Geräten
Diese Aktionen werden auf Geräte in der `DeviceId` Spalte der Abfrageergebnisse angewendet:
- **Gerät isolieren**– verwendet Microsoft Defender für Endpunkt, um eine vollständige Netzwerkisolation anzuwenden, was verhindert, dass das Gerät eine Verbindung mit einer Anwendung oder einem Dienst herstellen kann. [Weitere Informationen zur Computerisolation von Microsoft Defender für Endpunkte](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Untersuchungspaket sammeln**– Sammelt Geräteinformationen in einer ZIP-Datei. [Weitere Informationen zum Microsoft Defender for Endpoint-Untersuchungspaket](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Ausführen eines Antivirenscans**– führt einen vollständigen Windows Defender Antivirusscan auf dem Gerät aus.
- **Untersuchung initiieren**– initiiert eine [automatisierte Untersuchung](mtp-autoir.md) auf dem Gerät
- **Einschränken der Ausführung von** Apps – legt Einschränkungen auf dem Gerät fest, damit nur Dateien ausgeführt werden können, die mit einem von Microsoft ausgestellten Zertifikat signiert sind. [Weitere Informationen zu Einschränkungen für Apps mit Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Aktionen für Dateien
Wenn diese Option ausgewählt ist, können Sie die Aktion "Quarantänedatei" auf Dateien in der , oder Spalte der  `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` Abfrageergebnisse anwenden. Diese Aktion löscht die Datei vom aktuellen Speicherort und platziert eine Kopie in Quarantäne.

#### <a name="actions-on-users"></a>Aktionen für Benutzer
Wenn diese Option **ausgewählt** ist, wird der Benutzer als gefährdete Aktion für Benutzer in der , oder Spalte der `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` Abfrageergebnisse markiert. Diese Aktion legt die Risikostufe für Benutzer in Azure Active Directory auf "hoch" fest und löst entsprechende [Identitätsschutzrichtlinien aus.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)

> [!NOTE]
> Die Aktion "Zulassen" oder "Blockieren" für benutzerdefinierte Erkennungsregeln wird derzeit in Microsoft 365 Defender nicht unterstützt.

### <a name="5-set-the-rule-scope"></a>5. Festlegen des Regelbereichs.
Legen Sie den Bereich fest, um anzugeben, welche Geräte von der Regel abgedeckt werden. Der Bereich wirkt sich auf Regeln aus, die Geräte überprüfen, und wirkt sich nicht auf Regeln aus, die nur Postfächer und Benutzerkonten oder Identitäten überprüfen.

Beim Festlegen des Bereichs können Sie Dies auswählen:

- Alle Geräte
- Bestimmte Gerätegruppen

Nur Daten von Geräten im Gültigkeitsbereich werden abgefragt. Außerdem werden Aktionen nur auf diesen Geräten ergriffen.

### <a name="6-review-and-turn-on-the-rule"></a>6. Überprüfen und aktivieren Sie die Regel.
Nachdem Sie die Regel überprüft haben, wählen **Sie "Erstellen"** aus, um sie zu speichern. Die benutzerdefinierte Erkennungsregel wird sofort ausgeführt. Sie wird basierend auf der konfigurierten Häufigkeit erneut ausgeführt, um nach Übereinstimmungen zu suchen, Warnungen zu generieren und Gegenmaßnahmen zu ergreifen.

## <a name="manage-existing-custom-detection-rules"></a>Verwalten vorhandener benutzerdefinierter Erkennungsregeln
Sie können die Liste der vorhandenen benutzerdefinierten Erkennungsregeln anzeigen, ihre vorherigen Läufe überprüfen und die ausgelösten Warnungen überprüfen. Sie können eine Regel auch bei Bedarf ausführen und ändern.

### <a name="view-existing-rules"></a>Anzeigen vorhandener Regeln

Navigieren Sie zum Anzeigen aller vorhandenen benutzerdefinierten Erkennungsregeln zu **"Benutzerdefinierte**  >  **Erkennungen"**. Auf der Seite werden alle Regeln mit den folgenden Ausführungsinformationen aufgeführt:

- **Letzte Ausführung –** wann eine Regel zuletzt ausgeführt wurde, um nach Abfrage übereinstimmungen zu suchen und Warnungen zu generieren
- **Status der letzten Ausführung**– unabhängig davon, ob eine Regel erfolgreich ausgeführt wurde
- **Nächste Ausführung –** nächste geplante Ausführung
- **Status –** unabhängig davon, ob eine Regel aktiviert oder deaktiviert wurde

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Anzeigen von Regeldetails, Ändern der Regel und Ausführen der Regel

Wenn Sie umfassende Informationen zu einer   >  benutzerdefinierten **Erkennungsregel** anzeigen wollen, wechseln Sie zu "Benutzerdefinierte Erkennungen" und wählen dann den Namen der Regel aus. Anschließend können Sie allgemeine Informationen zur Regel anzeigen, einschließlich des Ausführungsstatus und des Gültigkeitsbereichs. Die Seite enthält auch die Liste der ausgelösten Warnungen und Aktionen.

![Detailseite für benutzerdefinierte Erkennungsregel](../../media/custom-detection-details.png)<br>
*Details zu benutzerdefinierten Erkennungsregel*

Auf dieser Seite können Sie auch die folgenden Aktionen für die Regel ausführen:

- **Ausführen**– Führen Sie die Regel sofort aus. Dadurch wird auch das Intervall für die nächste Ausführung zurückgesetzt.
- **Bearbeiten**– Ändern der Regel ohne Ändern der Abfrage
- **Abfrage ändern –** Bearbeiten der Abfrage bei der erweiterten Suche
- **Aktivieren**  /  **Deaktivieren –** Aktivieren der Regel oder Beenden der Ausführung
- **Löschen**– Deaktivieren der Regel und Entfernen

### <a name="view-and-manage-triggered-alerts"></a>Anzeigen und Verwalten ausgelöster Warnungen

Wechseln Sie auf dem Bildschirm mit den Regeldetails **(** Suche nach benutzerdefinierten Erkennungen  >    >  **[Regelname]**) zu "Ausgelöste Warnungen", in dem die durch Übereinstimmungen mit der Regel generierten Warnungen aufgeführt sind. Wählen Sie eine Warnung aus, um detaillierte Informationen zu dieser Warnung ein, und ergreifen Sie die folgenden Aktionen:

- Verwalten der Warnung durch Festlegen des Status und der Klassifizierung (wahr oder falsch)
- Verknüpfen der Warnung mit einem Vorfall
- Ausführen der Abfrage, die die Warnung bei der erweiterten Suche ausgelöst hat

### <a name="review-actions"></a>Überprüfen von Aktionen
Wechseln Sie auf dem Bildschirm mit den Regeldetails **(** Suche nach benutzerdefinierten Erkennungen  >    >  **[Regelname]**) zu "Ausgelöste Aktionen", in dem die auf Übereinstimmungen mit der Regel basierenden Aktionen aufgeführt sind.

>[!TIP]
>Verwenden Sie die Auswahlspalte [&#10003;] am linken Ende der Tabelle, um schnell Informationen anzeigen und Aktionen für ein Element in einer Tabelle zu ergreifen.

## <a name="see-also"></a>Siehe auch
- [Benutzerdefinierte Erkennungen – Übersicht](custom-detections-overview.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Erlernen der Abfragesprache für die erweiterte Suche](advanced-hunting-query-language.md)
- [Migrieren erweiterter Suchabfragen von Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mdatp.md)
