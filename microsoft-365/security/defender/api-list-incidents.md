---
title: Auflisten der Incidents-API in Microsoft 365 Defender
description: Informationen zum Auflisten der Incidents API in Microsoft 365 Defender
keywords: list, incident, incidents, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7fb0de4f8dc67331e7acca59e70d061fe7c19493
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935737"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Auflisten der Incidents-API in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.


## <a name="api-description"></a>API-Beschreibung

Mit der API für Listenvorfälle können Sie Vorfälle sortieren, um eine informierte Cybersicherheitsantwort zu erstellen. Es wird eine Sammlung von Vorfällen verfügbar gemacht, die in Ihrem Netzwerk innerhalb des von Ihnen in Ihrer Umgebungsaufbewahrungsrichtlinie angegebenen Zeitbereichs gekennzeichnet wurden. Die neuesten Vorfälle werden am Anfang der Liste angezeigt. Jeder Vorfall enthält ein Array verwandter Warnungen und deren zugehörige Entitäten.

Die API unterstützt die folgenden **OData-Operatoren:**

- `$filter`auf `lastUpdateTime` den `createdTime` Eigenschaften , , `status` und `assignedTo`
- `$top`, mit einem maximalen Wert von **100**
- `$skip`

## <a name="limitations"></a>Einschränkungen

1. Die maximale Seitengröße beträgt **100 Vorfälle.**
2. Die maximale Anzahl von Anforderungen beträgt **50 Anrufe pro Minute und** **1500 Anrufe pro Stunde.**

## <a name="permissions"></a>Berechtigungen

Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access Microsoft 365 Defender APIs](api-access.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
-|-|-
Anwendung | Incident.Read.All | Alle Vorfälle lesen
Anwendung | Incident.ReadWrite.All | Lesen und Schreiben aller Vorfälle
Delegiert (Geschäfts-, Schul- oder Unikonto) | Incident.Read | Lesen von Vorfällen
Delegiert (Geschäfts-, Schul- oder Unikonto) | Incident.ReadWrite | Lese- und Schreibvorfälle

> [!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>
> - Der Benutzer muss über die Berechtigung zum Anzeigen von Vorfällen im Portal verfügen.
> - Die Antwort umfasst nur Vorfälle, für die der Benutzer verfügbar ist.

## <a name="http-request"></a>HTTP-Anforderung

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
-|-|-
Authorization | Zeichenfolge | Bearer {token}. **Required**


## <a name="request-body"></a>Anforderungstext

Keine

## <a name="response"></a>Antwort

Wenn die Methode erfolgreich ist, wird eine Liste der `200 OK` [Vorfälle im](api-incident.md) Antworttext zurückgegeben.

## <a name="schema-mapping"></a>Schemazuordnung

### <a name="incident-metadata"></a>Metadaten zu Vorfällen

Feldname | Beschreibung | Beispielwert
-|-|-
incidentId | Eindeutige ID zur Darstellung des Vorfalls | 924565
redirectIncidentId | Nur aufgefüllt, wenn ein Vorfall zusammen mit einem anderen Vorfall im Rahmen der Vorfallverarbeitungslogik gruppieren wird. | 924569
incidentName | Zeichenfolgenwert, der für jeden Vorfall verfügbar ist. | Ransomware-Aktivität
createdTime | Zeitpunkt, zu dem der Vorfall zum ersten Mal erstellt wurde. | 2020-09-06T14:46:57.0733333Z
lastUpdateTime | Zeitpunkt, zu dem der Vorfall zuletzt im Back-End aktualisiert wurde.<br /><br /> Dieses Feld kann verwendet werden, wenn Sie den Anforderungsparameter für den Zeitraum festlegen, in dem Vorfälle abgerufen werden. | 2020-09-06T14:46:57.29Z
assignedTo | Besitzer des Vorfalls oder *null,* wenn kein Besitzer zugewiesen ist. | secop2@contoso.com
classification | Die Spezifikation für den Vorfall. Die Eigenschaftswerte sind: *Unknown*, *FalsePositive*, *TruePositive* | Unbekannt
Bestimmung | Gibt die Ermittlung des Vorfalls an. Die Eigenschaftswerte sind: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* | NotAvailable
status | Kategorisieren von *Vorfällen (als Aktiv* oder *Aufgelöst*). Es kann Ihnen helfen, Ihre Reaktion auf Vorfälle zu organisieren und zu verwalten. | Aktiv
Schweregrad | Gibt die möglichen Auswirkungen auf Ressourcen an. Je höher der Schweregrad, desto größer sind die Auswirkungen. In der Regel erfordern Elemente mit höherem Schweregrad die unmittelbarste Aufmerksamkeit.<br /><br />Einer der folgenden Werte: *Informational*, *Low*, *Medium und *High*. | Mittel
tags | Array von benutzerdefinierten Tags, die einem Vorfall zugeordnet sind, z. B. zum Kennzeichnen einer Gruppe von Vorfällen mit einem gemeinsamen Merkmal. | \[\]
Warnungen | Array, das alle Warnungen im Zusammenhang mit dem Vorfall sowie weitere Informationen enthält, z. B. schweregrad, Entitäten, die an der Warnung beteiligt waren, und die Quelle der Warnungen. | \[\] (Weitere Informationen zu Warnungsfeldern finden Sie weiter unten)

### <a name="alerts-metadata"></a>Benachrichtigungsmetadaten

Feldname | Beschreibung | Beispielwert
-|-|-
alertId | Eindeutiger Bezeichner zur Darstellung der Warnung | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId | Eindeutiger Bezeichner zum Darstellen des Vorfalls, dem diese Warnung zugeordnet ist | 924565
serviceSource | Dienst, von dem die Warnung stammt, z. B. Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity oder Microsoft Defender für Office 365. | MicrosoftCloudAppSecurity
creationTime | Zeitpunkt, zu dem die Warnung zum ersten Mal erstellt wurde. | 2020-09-06T14:46:55.7182276Z
lastUpdatedTime | Zeitpunkt, zu dem die Warnung zuletzt im Back-End aktualisiert wurde. | 2020-09-06T14:46:57.2433333Z
resolvedTime | Zeitpunkt, zu dem die Warnung aufgelöst wurde. | 2020-09-10T05:22:59Z
firstActivity | Zeitpunkt, zu dem die Benachrichtigung zum ersten Mal gemeldet hat, dass die Aktivität im Back-End aktualisiert wurde.| 2020-09-04T05:22:59Z
title | Kurzes Identifizieren des Zeichenfolgenwerts, der für jede Warnung verfügbar ist. | Ransomware-Aktivität
description | Zeichenfolgenwert, der jede Warnung beschreibt. | Der Benutzer Test User2 (testUser2@contoso.com) bearbeitete 99 Dateien mit mehreren Erweiterungen, die mit der ungewöhnlichen Erweiterung *herunterladen endeten.* Dies ist eine ungewöhnliche Anzahl von Dateimanipulationen und deutet auf einen potenziellen Ransomware-Angriff hin.
category | Visuelle und numerische Ansicht, wie weit der Angriff entlang der Kill Chain schreitet. Ausgerichtet am [MITRE ATT&CK™ Framework](https://attack.mitre.org/). | Auswirkung
status | Kategorisieren von Warnungen *(als Neu,* *Aktiv* oder *Aufgelöst*). Es kann Ihnen helfen, Ihre Antwort auf Warnungen zu organisieren und zu verwalten. | Neu
Schweregrad | Gibt die möglichen Auswirkungen auf Ressourcen an. Je höher der Schweregrad, desto größer sind die Auswirkungen. In der Regel erfordern Elemente mit höherem Schweregrad die unmittelbarste Aufmerksamkeit.<br>Einer der folgenden Werte: *Informational*, *Low*, *Medium und *High*. | Mittel
investigationId | Die durch diese Warnung ausgelöste automatische Untersuchungs-ID. | 1234
investigationState | Informationen zum aktuellen Status der Untersuchung. Einer der folgenden Werte: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*. | UnsupportedAlertType
classification | Die Spezifikation für den Vorfall. Die Eigenschaftswerte sind: *Unknown*, *FalsePositive*, *TruePositive* oder *Null* | Unbekannt
Bestimmung | Gibt die Ermittlung des Vorfalls an. Die Eigenschaftswerte sind: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* oder  *Null* | Apt
assignedTo | Besitzer des Vorfalls oder *null,* wenn kein Besitzer zugewiesen ist. | secop2@contoso.com
actorName | Die Aktivitätsgruppe, falls die dieser Warnung zugeordnet ist. | BORON
threatFamilyName | Dieser Warnung zugeordnete Bedrohungsfamilie. | null
mitreTechniques | Die Angriffstechniken, die mit [dem MITRE ATT-&CK](https://attack.mitre.org/)™ werden. | \[\]
Geräte | Alle Geräte, auf denen Warnungen im Zusammenhang mit dem Vorfall gesendet wurden. | \[\] (Weitere Informationen zu Entitätsfeldern finden Sie weiter unten)

### <a name="device-format"></a>Geräteformat

Feldname | Beschreibung | Beispielwert
-|-|-
DeviceId | Die Geräte-ID, die in Microsoft Defender for Endpoint festgelegt ist. | 24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId |  Die Geräte-ID, die in [Azure Active Directory festgelegt ist.](/azure/active-directory/fundamentals/active-directory-whatis) Nur für Geräte verfügbar, die der Domäne beigetreten sind. | null
deviceDnsName | Der vollqualifizierte Domänenname für das Gerät. | user5cx.middleeast.corp.contoso.com
osPlatform | Die Betriebssystemplattform, auf der das Gerät ausgeführt wird.| WindowsServer2016
osBuild | Die Buildversion für das Betriebssystem, auf dem das Gerät ausgeführt wird. | 14393
rbacGroupName | Die [dem Gerät](/azure/role-based-access-control/overview) zugeordnete rollenbasierte Zugriffssteuerungsgruppe (RBAC). | WDATP-Ring0
firstSeen | Zeitpunkt, zu dem das Gerät zum ersten Mal angezeigt wurde. | 2020-02-06T14:16:01.9330135Z
healthStatus | Der Integritätsstatus des Geräts. | Aktiv
riskScore | Die Risikosentwertung für das Gerät. | Hoch
Entitäten | Alle Entitäten, die als Teil oder verwandt mit einer bestimmten Warnung identifiziert wurden. | \[\] (Weitere Informationen zu Entitätsfeldern finden Sie weiter unten)

### <a name="entity-format"></a>Entitätsformat

Feldname | Beschreibung | Beispielwert
-|-|-
entityType | Entitäten, die als Teil oder verwandt mit einer bestimmten Warnung identifiziert wurden.<br>Die Eigenschaftenwerte sind: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry* | Benutzer
sha1 | Verfügbar, wenn entityType File *ist.*<br>Der Dateihash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind. | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256 | Verfügbar, wenn entityType File *ist.*<br>Der Dateihash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind. | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
fileName | Verfügbar, wenn entityType File *ist.*<br>Der Dateiname für Warnungen, die einer Datei oder einem Prozess zugeordnet sind | Detector.UnitTests.dll
filePath | Verfügbar, wenn entityType File *ist.*<br>Der Dateipfad für Warnungen, die einer Datei oder einem Prozess zugeordnet sind | C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
processId | Verfügbar, wenn entityType Process *ist.* | 24348
processCommandLine | Verfügbar, wenn entityType Process *ist.* | "Ihre Datei kann heruntergeladen \_1911150169.exe"
processCreationTime | Verfügbar, wenn entityType Process *ist.* | 2020-07-18T03:25:38.5269993Z
parentProcessId | Verfügbar, wenn entityType Process *ist.* | 16840
parentProcessCreationTime | Verfügbar, wenn entityType Process *ist.* | 2020-07-18T02:12:32.8616797Z
ipAddress | Verfügbar, wenn entityType ip *ist.* <br>IP-Adresse für Warnungen im Zusammenhang mit Netzwerkereignissen, z. *B. Kommunikation mit einem schädlichen Netzwerkziel.* | 62.216.203.204
url | Verfügbar, wenn entityType url *ist.* <br>URL für Warnungen im Zusammenhang mit Netzwerkereignissen, z. *B. Kommunikation mit einem zielschädlichen Netzwerk.* | down.esales360.cn
accountName | Verfügbar, wenn entityType User *ist.* | testUser2
Domänname | Verfügbar, wenn entityType User *ist.* | europe.corp.contoso
userSid | Verfügbar, wenn entityType User *ist.* | S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId | Verfügbar, wenn entityType User *ist.* | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | Verfügbar, wenn entityType *User* / *MailBox* / *MailMessage ist.* | testUser2@contoso.com
mailboxDisplayName | Verfügbar, wenn entityType *MailBox ist.* | Testen von User2
mailboxAddress | Verfügbar, wenn entityType *User* / *MailBox* / *MailMessage ist.* | testUser2@contoso.com
clusterBy | Verfügbar, wenn entityType *MailCluster ist.* | Betreff; P2SenderDomain; ContentType
sender | Verfügbar, wenn entityType *User* / *MailBox* / *MailMessage ist.* | user.abc@mail.contoso.co.in
recipient | Verfügbar, wenn entityType *MailMessage ist.* | testUser2@contoso.com
subject | Verfügbar, wenn entityType *MailMessage ist.* | \[EXTERNE \] Aufmerksamkeit
deliveryAction | Verfügbar, wenn entityType *MailMessage ist.* | Zugestellt
securityGroupId | Verfügbar, wenn entityType *SecurityGroup ist.* | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName | Verfügbar, wenn entityType *SecurityGroup ist.* | Netzwerkkonfigurationsoperatoren
registryHive | Verfügbar, wenn entityType die *Registrierung ist.* | LOKALER \_ \_ HKEY-COMPUTER |
registryKey | Verfügbar, wenn entityType die *Registrierung ist.* | SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registryValueType | Verfügbar, wenn entityType die *Registrierung ist.* | Zeichenfolge
registryValue | Verfügbar, wenn entityType die *Registrierung ist.* | 31-00-00-00
deviceId | Die ID des Geräts, das sich auf die Entität bezogen hat. | 986e5df8b73dacd43c8917d17e523e76b13c75cd

## <a name="example"></a>Beispiel

**Anforderung**

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

**Antwort**

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a>Verwandte Artikel

- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
- [Informationen zu API-Beschränkungen und -Lizenzierung](api-terms.md)
- [Verstehen von Fehlercodes](api-error-codes.md)
- [Übersicht über Vorfälle](incidents-overview.md)
- [Vorfall-APIs](api-incident.md)
- [Aktualisieren der Vorfall-API](api-update-incidents.md)