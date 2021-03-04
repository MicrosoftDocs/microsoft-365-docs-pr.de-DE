---
title: Erstellen und Verwalten von benutzerdefinierten Erkennungsregeln in Microsoft 365 Defender
description: Informationen zum Erstellen und Verwalten von benutzerdefinierten Erkennungsregeln basierend auf erweiterten Suchabfragen
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, rules, schema, kusto, microsoft 365, Microsoft Threat Protection, RBAC, permissions, Microsoft Defender ATP
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
ms.openlocfilehash: 51a6bc33778248a69e533d9e2077365a63b97e30
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50424131"
---
# <a name="create-and-manage-custom-detections-rules"></a>Erstellen und Verwalten von benutzerdefinierten Erkennungsregeln

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Benutzerdefinierte Erkennungsregeln sind Regeln, die Sie mit erweiterten Suchabfragen entwerfen [und](advanced-hunting-overview.md) optimieren können. Mit diesen Regeln können Sie verschiedene Ereignisse und Systemzustände proaktiv überwachen, einschließlich mutmaßlicher Verletzungsaktivitäten und falsch konfigurierter Endpunkte. Sie können festlegen, dass sie in regelmäßigen Intervallen ausgeführt werden, Warnungen generieren und Reaktionsaktionen ausführen, wenn Übereinstimmungen angezeigt werden.

## <a name="required-permissions-for-managing-custom-detections"></a>Erforderliche Berechtigungen zum Verwalten von benutzerdefinierten Erkennungen

Zum Verwalten von benutzerdefinierten Erkennungen muss Ihnen eine der folgenden Rollen zugewiesen werden:

- **Sicherheitsadministrator**– Benutzer mit dieser [Azure Active Directory-Rolle](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) können Sicherheitseinstellungen in Microsoft 365 Security Center und anderen Portalen und Diensten verwalten.

- **Sicherheitsoperator**– Benutzer mit dieser [Azure Active Directory-Rolle](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) können Warnungen verwalten und über globalen schreibgeschützten Zugriff auf sicherheitsrelevante Features verfügen, einschließlich aller Informationen im Microsoft 365 Security Center. Diese Rolle ist nur ausreichend, um benutzerdefinierte Erkennungen zu verwalten, wenn die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) in Microsoft Defender for Endpoint deaktiviert ist. Wenn Sie rbAC konfiguriert haben, benötigen Sie auch die **Berechtigung** Sicherheitseinstellungen verwalten für Defender for Endpoint.

Zum Verwalten der erforderlichen Berechtigungen kann **ein globaler Administrator:**

- Weisen Sie **die Rolle des Sicherheitsadministrators** oder **Sicherheitsoperators** im [Microsoft 365 Admin Center](https://admin.microsoft.com/) unter **Roles** Security  >  **admin zu.**
- Überprüfen Sie die RBAC-Einstellungen für Microsoft Defender for Endpoint im [Microsoft Defender Security Center](https://securitycenter.windows.com/) unter **Einstellungen**  >  **Berechtigungsrollen**  >  . Wählen Sie die entsprechende Rolle aus, um die **Berechtigung Sicherheitseinstellungen verwalten zu** erteilen.

> [!NOTE]
> Zum Verwalten benutzerdefinierter Erkennungen  benötigen Sicherheitsoperatoren  die Berechtigung Sicherheitseinstellungen verwalten in Microsoft Defender for Endpoint, wenn rbAC aktiviert ist.

## <a name="create-a-custom-detection-rule"></a>Erstellen einer benutzerdefinierten Erkennungsregel
### <a name="1-prepare-the-query"></a>1. Bereiten Sie die Abfrage vor.

Wechseln Sie im Microsoft 365 Security Center zu **Erweiterte** Suche, und wählen Sie eine vorhandene Abfrage aus, oder erstellen Sie eine neue Abfrage. Wenn Sie eine neue Abfrage verwenden, führen Sie die Abfrage aus, um Fehler zu identifizieren und mögliche Ergebnisse zu verstehen.

>[!IMPORTANT]
>Damit der Dienst nicht zu viele Warnungen zurücksent, ist jede Regel auf die Generierung von nur 100 Warnungen beschränkt, wenn sie ausgeführt wird. Bevor Sie eine Regel erstellen, optimieren Sie Ihre Abfrage, um Warnungen für normale, täglich ausgeführte Aktivitäten zu vermeiden.


#### <a name="required-columns-in-the-query-results"></a>Erforderliche Spalten in den Abfrageergebnissen
Zum Erstellen einer benutzerdefinierten Erkennungsregel muss die Abfrage die folgenden Spalten zurückgeben:

- `Timestamp`–Wird zum Festlegen des Zeitstempels für generierte Warnungen verwendet
- `ReportId`–aktiviert Nachschlagearbeiten für die ursprünglichen Datensätze
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
>Unterstützung für zusätzliche Entitäten wird hinzugefügt, wenn dem schema für die erweiterte Suche neue [Tabellen hinzugefügt werden.](advanced-hunting-schema-tables.md)

Einfache Abfragen, z. B. solche, die den Operator or nicht zum Anpassen oder Aggregieren von Ergebnissen verwenden, geben in der Regel `project` `summarize` diese allgemeinen Spalten zurück.

Es gibt verschiedene Möglichkeiten, um sicherzustellen, dass komplexere Abfragen diese Spalten zurückgeben. Wenn Sie z. B. das Aggregieren und Zählen nach Entitäten unter einer Spalte wie bevorzugen, können Sie es trotzdem zurückgeben und aus dem neuesten Ereignis abrufen, das jedes eindeutige `DeviceId` `Timestamp` Ereignis `ReportId` `DeviceId` enthält.

Die folgende Beispielabfrage zählt die Anzahl eindeutiger Geräte ( ) mit Antivirenerkennungen und verwendet diese Anzahl, um nur die Geräte mit mehr als fünf Erkennungen `DeviceId` zu finden. Zum Zurückgeben der neuesten `Timestamp` und der entsprechenden wird der Operator mit der Funktion `ReportId` `summarize` `arg_max` verwendet.

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Legen Sie für eine bessere Abfrageleistung einen Zeitfilter fest, der der vorgesehenen Ausführungshäufigkeit für die Regel entspricht. Da die am wenigsten häufige Ausführung _alle 24 Stunden ist,_ wird die Filterung für den letzten Tag alle neuen Daten abdecken.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Erstellen Sie eine neue Regel, und geben Sie Benachrichtigungsdetails an.

Wählen Sie mit der Abfrage  im Abfrage-Editor Erkennungsregel erstellen aus, und geben Sie die folgenden Warnungsdetails an:

- **Erkennungsname**– Name der Erkennungsregel
- **Häufigkeit**– Intervall zum Ausführen der Abfrage und Ausführen von Aktionen. [Weitere Anleitungen finden Sie weiter unten.](#rule-frequency)
- **Warnungstitel**– Titel, der mit von der Regel ausgelösten Warnungen angezeigt wird
- **Schweregrad**– potenzielles Risiko der durch die Regel identifizierten Komponente oder Aktivität
- **Kategorie**– Bedrohungskomponente oder Aktivität, die von der Regel identifiziert wird
- **MITRE ATT&CK-Techniken**– eine oder mehrere Angriffstechniken, die von der Regel identifiziert werden, wie im [MITRE ATT&CK-Framework dokumentiert.](https://attack.mitre.org/) Dieser Abschnitt ist für bestimmte Warnungskategorien ausgeblendet, z. B. Schadsoftware, Ransomware, verdächtige Aktivitäten und unerwünschte Software.
- **Beschreibung**– weitere Informationen zu der durch die Regel identifizierten Komponente oder Aktivität 
- **Empfohlene Aktionen**– zusätzliche Aktionen, die Reaktionshelfer als Reaktion auf eine Warnung ausführen können

#### <a name="rule-frequency"></a>Regelhäufigkeit
Wenn Sie eine neue Regel speichern oder bearbeiten, wird sie ausgeführt und auf Übereinstimmungen aus den letzten 30 Tagen der Daten überprüft. Die Regel wird dann erneut in festen Intervallen ausgeführt, und es wird eine Lookbackdauer basierend auf der von Ihnen festgelegten Häufigkeit angewendet:

- **Alle 24 Stunden**– wird alle 24 Stunden ausgeführt und überprüft Daten aus den letzten 30 Tagen
- **Alle 12 Stunden**– wird alle 12 Stunden ausgeführt und überprüft Daten aus den letzten 24 Stunden
- **Alle 3 Stunden**– wird alle 3 Stunden ausgeführt und überprüft Daten aus den letzten 6 Stunden
- **Jede Stunde**– wird stündlich ausgeführt und überprüft Daten aus den letzten 2 Stunden

>[!TIP]
> Match the time filters in your query with the lookback duration. Ergebnisse außerhalb der Lookbackdauer werden ignoriert.  

Wählen Sie die Häufigkeit aus, die mit der Überwachungshäufigkeit der Erkennungen entspricht. Berücksichtigen Sie die Fähigkeit Ihrer Organisation, auf die Warnungen zu reagieren.

### <a name="3-choose-the-impacted-entities"></a>3. Wählen Sie die betroffenen Entitäten aus.
Identifizieren Sie die Spalten in den Abfrageergebnissen, in denen Sie erwarten, dass sie die haupt betroffene oder betroffene Entität finden. Eine Abfrage kann z. B. Absenderadressen ( `SenderFromAddress` oder `SenderMailFromAddress` ) und Empfängeradressen ( `RecipientEmailAddress` ) zurückgeben. Die Identifizierung, welche dieser Spalten die hauptsprallte Entität darstellen, hilft dem Dienst, relevante Warnungen zu aggregieren, Vorfälle zu korrelieren und Zielreaktionsaktionen zu ergreifen.

Sie können für jeden Entitätstyp (Postfach, Benutzer oder Gerät) nur eine Spalte auswählen. Spalten, die von Ihrer Abfrage nicht zurückgegeben werden, können nicht ausgewählt werden.

### <a name="4-specify-actions"></a>4. Geben Sie Aktionen an.
Ihre benutzerdefinierte Erkennungsregel kann automatisch Aktionen auf Geräten, Dateien oder Benutzern ausführen, die von der Abfrage zurückgegeben werden.

#### <a name="actions-on-devices"></a>Aktionen auf Geräten
Diese Aktionen werden auf Geräte in der `DeviceId` Spalte der Abfrageergebnisse angewendet:
- **Gerät isolieren**– verwendet Microsoft Defender for Endpoint, um eine vollständige Netzwerkisolation anzuwenden, um zu verhindern, dass das Gerät eine Verbindung mit einer Anwendung oder einem Dienst herstellen kann. [Weitere Informationen zur Microsoft Defender for Endpoint-Computerisolation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Untersuchungspaket sammeln**– Sammelt Geräteinformationen in einer ZIP-Datei. [Weitere Informationen zum Microsoft Defender for Endpoint-Untersuchungspaket](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Antivirusscan ausführen**– führt eine vollständige Überprüfung Windows Defender Antivirusscan auf dem Gerät aus.
- **Initiieren der** Untersuchung – initiiert eine [automatisierte Untersuchung](mtp-autoir.md) auf dem Gerät
- **Einschränken der App-Ausführung**– legt Einschränkungen auf dem Gerät fest, damit nur Dateien ausgeführt werden können, die mit einem von Microsoft ausgestellten Zertifikat signiert sind. [Weitere Informationen zu App-Einschränkungen mit Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Aktionen für Dateien
Wenn diese Option ausgewählt ist, können Sie die Quarantänedateiaktion auf Dateien in der , , oder -Spalte der  `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` Abfrageergebnisse anwenden. Mit dieser Aktion wird die Datei vom aktuellen Speicherort gelöscht und eine Kopie in Quarantäne gestellt.

#### <a name="actions-on-users"></a>Aktionen für Benutzer
Wenn diese Option **ausgewählt** ist, wird die Aktion Benutzer als gefährdet markieren für Benutzer in der Spalte , oder in den `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` Abfrageergebnissen ausgeführt. Diese Aktion legt die Risikostufe für Benutzer in Azure Active Directory auf "hoch" fest und löst entsprechende [Identitätsschutzrichtlinien aus.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)

> [!NOTE]
> Die Aktion "Zulassen" oder "Blockieren" für benutzerdefinierte Erkennungsregeln wird derzeit in Microsoft 365 Defender nicht unterstützt.

### <a name="5-set-the-rule-scope"></a>5. Festlegen des Regelbereichs.
Legen Sie den Bereich fest, um anzugeben, welche Geräte von der Regel abgedeckt werden. Der Bereich wirkt sich auf Regeln aus, die Geräte überprüfen, und wirkt sich nicht auf Regeln aus, die nur Postfächer und Benutzerkonten oder Identitäten überprüfen.

Wenn Sie den Bereich festlegen, können Sie wählen:

- Alle Geräte
- Bestimmte Gerätegruppen

Nur Daten von Geräten im Bereich werden abgefragt. Außerdem werden Aktionen nur auf diesen Geräten ergriffen.

### <a name="6-review-and-turn-on-the-rule"></a>6. Überprüfen und aktivieren Sie die Regel.
Nachdem Sie die Regel überprüft haben, wählen **Sie Erstellen aus,** um sie zu speichern. Die benutzerdefinierte Erkennungsregel wird sofort ausgeführt. Es wird basierend auf der konfigurierten Häufigkeit erneut ausgeführt, um nach Übereinstimmungen zu suchen, Warnungen zu generieren und Reaktionsaktionen zu ergreifen.


>[!Important] 
>Benutzerdefinierte Erkennungen sollten regelmäßig auf Effizienz und Effektivität überprüft werden. Um sicherzustellen, dass Sie Erkennungen erstellen, die echte Warnungen auslösen, nehmen Sie sich Zeit, ihre vorhandenen benutzerdefinierten Erkennungen zu überprüfen, indem Sie die Schritte unter Verwalten vorhandener benutzerdefinierter [Erkennungsregeln ausführen.](#manage-existing-custom-detection-rules) <br>  
Sie behalten die Kontrolle über die Breite oder Spezifizität Ihrer benutzerdefinierten Erkennungen, sodass alle von benutzerdefinierten Erkennungen generierten falsch generierten Warnungen darauf hinweisen können, dass bestimmte Parameter der Regeln geändert werden müssen.


## <a name="manage-existing-custom-detection-rules"></a>Verwalten vorhandener benutzerdefinierter Erkennungsregeln
Sie können die Liste der vorhandenen benutzerdefinierten Erkennungsregeln anzeigen, die vorherigen Läufe überprüfen und die ausgelösten Warnungen überprüfen. Sie können auch eine Regel bei Bedarf ausführen und ändern.

### <a name="view-existing-rules"></a>Anzeigen vorhandener Regeln

Navigieren Sie zum Anzeigen aller vorhandenen benutzerdefinierten Erkennungsregeln zu **Hunting**  >  **Custom detections**. Auf der Seite sind alle Regeln mit den folgenden Ausführungsinformationen aufgeführt:

- **Letzte Ausführung**– bei der letzten Ausführung einer Regel zum Überprüfen von Abfrage übereinstimmungen und Generieren von Warnungen
- **Status der letzten Ausführung**– gibt an, ob eine Regel erfolgreich ausgeführt wurde
- **Nächste Ausführung**– die nächste geplante Ausführung
- **Status –** gibt an, ob eine Regel aktiviert oder deaktiviert wurde

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Anzeigen von Regeldetails, Ändern der Regel und Ausführen der Regel

Wenn Sie umfassende Informationen zu einer benutzerdefinierten Erkennungsregel anzeigen, wechseln Sie zu **Benutzerdefinierte**  >  **Erkennungen** nachjagen, und wählen Sie dann den Namen der Regel aus. Anschließend können Sie allgemeine Informationen zur Regel anzeigen, einschließlich Der Ausführungsstatus und -bereich. Die Seite enthält auch die Liste der ausgelösten Warnungen und Aktionen.

![Detailseite für benutzerdefinierte Erkennungsregel](../../media/custom-detection-details.png)<br>
*Details zu benutzerdefinierten Erkennungsregel*

Sie können auf dieser Seite auch die folgenden Aktionen für die Regel ausführen:

- **Ausführen**– Führen Sie die Regel sofort aus. Dadurch wird auch das Intervall für die nächste Ausführung zurückgesetzt.
- **Bearbeiten**– Ändern der Regel, ohne die Abfrage zu ändern
- **Abfrage ändern**– Bearbeiten der Abfrage bei der erweiterten Suche
- **Aktivieren**  /  **Deaktivieren –** Aktivieren der Regel oder Beenden der Ausführung
- **Löschen**– Deaktivieren der Regel und Entfernen der Regel

### <a name="view-and-manage-triggered-alerts"></a>Anzeigen und Verwalten ausgelöster Warnungen

Wechseln Sie im Regeldetailsescreen (**Suche** nach benutzerdefinierten Erkennungen  >    >  **[Regelname] )** zu **Ausgelöste** Warnungen , die die durch Übereinstimmungen mit der Regel generierten Warnungen auflisten. Wählen Sie eine Warnung aus, um detaillierte Informationen dazu ein- und die folgenden Aktionen zu ergreifen:

- Verwalten der Warnung durch Festlegen des Status und der Klassifizierung (true oder false alert)
- Verknüpfen der Warnung mit einem Vorfall
- Ausführen der Abfrage, die die Warnung bei der erweiterten Suche ausgelöst hat

### <a name="review-actions"></a>Überprüfen von Aktionen
Wechseln Sie im Regeldetailsescreen (**Suche** nach benutzerdefinierten Erkennungen  >    >  **[Regelname] )** zu **Ausgelöste** Aktionen , in der die auf Übereinstimmungen mit der Regel basierenden Aktionen aufgeführt sind.

>[!TIP]
>Verwenden Sie die Auswahlspalte [&#10003;] links neben der Tabelle, um Informationen schnell anzeigen und Aktionen für ein Element in einer Tabelle ergreifen zu können.

## <a name="see-also"></a>Siehe auch
- [Benutzerdefinierte Erkennungen – Übersicht](custom-detections-overview.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Erlernen der Abfragesprache für die erweiterte Suche](advanced-hunting-query-language.md)
- [Migrieren erweiterter Suchabfragen von Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mdatp.md)
