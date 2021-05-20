---
title: Liste der Vorfällen-API in Microsoft 365 Defender
description: Erfahren Sie, wie Sie die Vorfall-API in Microsoft 365 Defender auflisten
keywords: Liste, Vorfall, Vorfälle, api
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
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572153"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Liste der Vorfällen-API in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.


## <a name="api-description"></a>API-Beschreibung

Die Api für Listenvorfälle ermöglicht es Ihnen, Vorfälle zu sortieren, um eine informierte Cybersicherheitsreaktion zu erstellen. Es macht eine Sammlung von Vorfällen verfügbar, die in Ihrem Netzwerk innerhalb des in der Umgebungsbindungsrichtlinie angegebenen Zeitraums gekennzeichnet wurden. Die neuesten Vorfälle werden oben in der Liste angezeigt. Jeder Vorfall enthält ein Array verwandter Warnungen und der zugehörigen Entitäten.

Die API unterstützt  die folgenden OData-Operatoren:

- `$filter` auf den `lastUpdateTime` , `createdTime` , und `status` `assignedTo` Eigenschaften
- `$top`, mit einem Maximalwert von **100**
- `$skip`

## <a name="limitations"></a>Einschränkungen

1. Die maximale Seitengröße beträgt **100 Vorfälle**.
2. Die maximale Rate der Anfragen beträgt **50 Anrufe pro Minute** und **1500 Anrufe pro Stunde**.

## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access Microsoft 365 Defender-APIs](api-access.md)

Berechtigungstyp | Berechtigung | Name der Berechtigungsanzeige
-|-|-
Anwendung | Incident.Read.All | Lesen Sie alle Vorfälle
Anwendung | Incident.ReadWrite.All | Lesen und Schreiben aller Vorfälle
Delegiert (Geschäfts-, Schul- oder Unikonto) | Incident.Read | Vorfälle lesen
Delegiert (Geschäfts-, Schul- oder Unikonto) | Incident.ReadWrite | Vorkommnisse lesen und schreiben

> [!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>
> - Der Benutzer muss über die Ansichtsberechtigung für Vorfälle im Portal verfügen.
> - Die Antwort enthält nur Vorfälle, denen der Benutzer ausgesetzt ist.

## <a name="http-request"></a>HTTP-Anforderung

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
-|-|-
Authorization | String | Träger 'Token'. **Required**


## <a name="request-body"></a>Anforderungstext

Keine

## <a name="response"></a>Antwort

Bei Erfolg gibt diese Methode `200 OK` zurück , und eine Liste der [Vorfälle](api-incident.md) im Antworttext.

## <a name="schema-mapping"></a>Schemazuordnung

### <a name="incident-metadata"></a>Vorfallmetadaten

Feldname | Beschreibung | Beispielwert
-|-|-
incidentId | Eindeutiger Bezeichner zur Darstellung des Vorfalls | 924565
redirectIncidentId | Nur für den Fall, dass ein Vorfall zusammen mit einem anderen Vorfall als Teil der Ereignisverarbeitungslogik gruppiert wird. | 924569
incidentName | Zeichenfolgenwert für jeden Vorfall verfügbar. | Ransomware-Aktivität
createdZeit | Zeitpunkt, zu dem der Vorfall zum ersten Mal erstellt wurde. | 2020-09-06T14:46:57.0733333Z
lastUpdateTime | Uhrzeit, zu der der Vorfall zuletzt auf dem Backend aktualisiert wurde.<br /><br /> Dieses Feld kann verwendet werden, wenn Sie den Anforderungsparameter für den Zeitbereich festlegen, in dem Vorfälle abgerufen werden. | 2020-09-06T14:46:57.29Z
assignedTo | Besitzer des Vorfalls oder *null,* wenn kein Besitzer zugewiesen ist. | secop2@contoso.com
classification | Die Spezifikation für den Vorfall. Die Eigenschaftswerte sind: *Unknown*, *FalsePositive*, *TruePositive* | Unbekannt
Bestimmung | Gibt die Bestimmung des Vorfalls an. Die Eigenschaftswerte sind: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Andere* | Nicht verfügbar
status | Kategorisieren von Vorfällen (als *Aktiv* oder *Aufgelöst*). Es kann Ihnen helfen, Ihre Reaktion auf Vorfälle zu organisieren und zu verwalten. | Aktiv
Schweregrad | Gibt die möglichen Auswirkungen auf Anlagen an. Je höher der Schweregrad, desto größer die Auswirkungen. In der Regel erfordern Elemente mit höherem Schweregrad die unmittelbarste Aufmerksamkeit.<br /><br />Einer der folgenden Werte: *Informational*, *Low*, *Medium und *High*. | Mittel
tags | Array von benutzerdefinierten Tags, die einem Vorfall zugeordnet sind, z. B. zum Kennzeichnen einer Gruppe von Vorfällen mit einem gemeinsamen Merkmal. | \[\]
Kommentare | Array von Kommentaren, die von Secops bei der Verwaltung des Vorfalls erstellt wurden, z. B. zusätzliche Informationen zur Klassifizierungsauswahl. | \[\]
Warnungen | Array, das alle Warnungen im Zusammenhang mit dem Vorfall enthält, sowie andere Informationen, z. B. Schweregrad, Entitäten, die an der Warnung beteiligt waren, und die Quelle der Warnungen. | \[\] (siehe Details zu den Warnungsfeldern unten)

### <a name="alerts-metadata"></a>Warnungsmetadaten

Feldname | Beschreibung | Beispielwert
-|-|-
alertId | Eindeutiger Bezeichner zur Darstellung der Warnung | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId | Eindeutiger Bezeichner zur Darstellung des Vorfalls, dem diese Warnung zugeordnet ist | 924565
serviceSource | Der Dienst, von dem die Warnung stammt, z. B. Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity oder Microsoft Defender für Office 365. | MicrosoftCloudAppSecurity
Creationtime | Uhrzeit, zu dem die Warnung zum ersten Mal erstellt wurde. | 2020-09-06T14:46:55.7182276Z
lastUpdatedTime | Uhrzeit, zu der die Warnung zuletzt am Back-End aktualisiert wurde. | 2020-09-06T14:46:57.243333Z
resolvedZeit | Uhrzeit, zu der die Warnung aufgelöst wurde. | 2020-09-10T05:22:59Z
firstAktivität | Zeitpunkt, zu dem die Warnung zum ersten Mal gemeldet hat, dass die Aktivität am Back-End aktualisiert wurde.| 2020-09-04T05:22:59Z
title | Kurzes Identifizieren des Zeichenfolgenwerts, der für jede Warnung verfügbar ist. | Ransomware-Aktivität
Beschreibung | Zeichenfolgenwert, der jede Warnung beschreibt. | Der User Test User2 (testUser2@contoso.com) hat 99 Dateien mit mehreren Erweiterungen manipuliert, die mit der ungewöhnlichen *Erweiterung* enden. Dies ist eine ungewöhnliche Anzahl von Dateimanipulationen und ist ein Hinweis auf einen möglichen Ransomware-Angriff.
category | Visuelle und numerische Ansicht, wie weit der Angriff entlang der Kill-Kette fortgeschritten ist. Ausgerichtet an das [MITRE ATT&CK™ Framework](https://attack.mitre.org/). | Auswirkung
status | Kategorisieren von Warnungen (als *Neu*, *Aktiv* oder *Aufgelöst*). Es kann Ihnen helfen, Ihre Reaktion auf Warnungen zu organisieren und zu verwalten. | Neu
Schweregrad | Gibt die möglichen Auswirkungen auf Anlagen an. Je höher der Schweregrad, desto größer die Auswirkungen. In der Regel erfordern Elemente mit höherem Schweregrad die unmittelbarste Aufmerksamkeit.<br>Einer der folgenden Werte: *Informational*, *Low*, *Medium und *High*. | Mittel
investigationId | Die automatisierte Untersuchungs-ID, die durch diese Warnung ausgelöst wird. | 1234
UntersuchungStaat | Informationen über den aktuellen Stand der Untersuchung. Einer der folgenden Werte: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*. | Nicht unterstütztAlertType
classification | Die Spezifikation für den Vorfall. Die Eigenschaftswerte lauten: *Unknown*, *FalsePositive*, *TruePositive* oder *null* | Unbekannt
Bestimmung | Gibt die Bestimmung des Vorfalls an. Die Eigenschaftswerte lauten: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* oder  *NULL* | Apt
assignedTo | Besitzer des Vorfalls oder *null,* wenn kein Besitzer zugewiesen ist. | secop2@contoso.com
actorName | Die Aktivitätsgruppe, falls vorhanden, die dieser Warnung zugeordnet ist. | Bor
threatFamilyName | Bedrohungsfamilie, die mit dieser Warnung verknüpft ist. | null
mitreTechniques | Die Angriffstechniken, die auf das [MITRE ATT&CK](https://attack.mitre.org/)™ Framework ausgerichtet sind. | \[\]
Geräte | Alle Geräte, auf denen Warnungen im Zusammenhang mit dem Vorfall gesendet wurden. | \[\] (siehe Details zu Entitätsfeldern unten)

### <a name="device-format"></a>Geräteformat

Feldname | Beschreibung | Beispielwert
-|-|-
Deviceid | Die Geräte-ID, wie in Microsoft Defender für Endpoint festgelegt. | 24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId |  Die Geräte-ID, wie in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis)angegeben. Nur für Domänengeräte verfügbar. | null
deviceDnsName | Der vollqualifizierte Domänenname für das Gerät. | user5cx.middleeast.corp.contoso.com
osPlatform | Die Betriebssystemplattform, auf der das Gerät ausgeführt wird.| WindowsServer2016
osBuild | Die Buildversion für das Betriebssystem, auf dem das Gerät ausgeführt wird. | 14393
rbacGroupName | Die dem Gerät zugeordnete [rollenbasierte Zugriffssteuerungsgruppe](/azure/role-based-access-control/overview) (RBAC). | WDATP-Ring0
firstSeen | Uhrzeit, zu der das Gerät zum ersten Mal gesehen wurde. | 2020-02-06T14:16:01.9330135Z
healthStatus | Der Integritätszustand des Geräts. | Aktiv
riskScore | Der Risiko-Score für das Gerät. | Hoch
Entitäten | Alle Entitäten, die als Teil einer bestimmten Warnung identifiziert wurden oder mit ihr verknüpft sind. | \[\] (siehe Details zu Entitätsfeldern unten)

### <a name="entity-format"></a>Entitätsformat

Feldname | Beschreibung | Beispielwert
-|-|-
Entitytype | Entitäten, die als Teil einer bestimmten Warnung identifiziert wurden oder mit ihr verbunden sind.<br>Die Eigenschaftenwerte sind: *Benutzer*, *Ip*, *Url*, *Datei*, *Prozess*, *MailBox*, *MailMessage*, *MailCluster*, *Registry* | Benutzer
sha1 | Verfügbar, wenn entityType *Datei* ist.<br>Der Dateihash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind. | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256 | Verfügbar, wenn entityType *Datei* ist.<br>Der Dateihash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind. | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
fileName | Verfügbar, wenn entityType *Datei* ist.<br>Der Dateiname für Warnungen, die einer Datei oder einem Prozess zugeordnet sind | Detector.UnitTests.dll
Filepath | Verfügbar, wenn entityType *Datei* ist.<br>Der Dateipfad für Warnungen, die einer Datei oder einem Prozess zugeordnet sind | C: \\ agent_work_temp-Bereitstellungssystem, 2020-09-06 12_14_54, Out
Processid | Verfügbar, wenn entityType *Prozess* ist. | 24348
processCommandLine | Verfügbar, wenn entityType *Prozess* ist. | "Ihre Datei ist bereit, \_1911150169.exe herunterzuladen"
processCreationTime | Verfügbar, wenn entityType *Prozess* ist. | 2020-07-18T03:25:38.5269993Z
parentProcessId | Verfügbar, wenn entityType *Prozess* ist. | 16840
parentProcessCreationTime | Verfügbar, wenn entityType *Prozess* ist. | 18.07.2010 02:12:32.8616797Z
ipAddress | Verfügbar, wenn entityType *Ip* ist. <br>IP-Adresse für Warnungen im Zusammenhang mit Netzwerkereignissen, z. B. *Kommunikation mit einem böswilligen Netzwerkziel*. | 62.216.203.204
url | Verfügbar, wenn entityType *Url* ist. <br>URL für Warnungen im Zusammenhang mit Netzwerkereignissen, z. B. *Kommunikation mit einem böswilligen Netzwerkziel*. | down.esales360.cn
accountName | Verfügbar, wenn entityType *Benutzer* ist. | testUser2
Domänname | Verfügbar, wenn entityType *Benutzer* ist. | europe.corp.contoso
userSid | Verfügbar, wenn entityType *Benutzer* ist. | S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId | Verfügbar, wenn entityType *Benutzer* ist. | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | Verfügbar, wenn entityType *Benutzer* / *MailBox* / *MailMessage* ist. | testUser2@contoso.com
mailboxDisplayName | Verfügbar, wenn entityType *MailBox* ist. | Test Benutzer2
mailboxAddress | Verfügbar, wenn entityType *Benutzer* / *MailBox* / *MailMessage* ist. | testUser2@contoso.com
clusterBy | Verfügbar, wenn entityType  *MailCluster* ist. | Thema; P2SenderDomain; Contenttype
sender | Verfügbar, wenn entityType *Benutzer* / *MailBox* / *MailMessage* ist. | user.abc@mail.contoso.co.in
recipient | Verfügbar, wenn entityType *MailMessage* ist. | testUser2@contoso.com
subject | Verfügbar, wenn entityType *MailMessage* ist. | \[EXTERNAL \] Aufmerksamkeit
deliveryAction | Verfügbar, wenn entityType *MailMessage* ist. | Geliefert
securityGroupId | Verfügbar, wenn entityType  *SecurityGroup* ist. | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName | Verfügbar, wenn entityType  *SecurityGroup* ist. | Netzwerkkonfigurationsoperatoren
registryHive | Verfügbar, wenn entityType  *Registrierung* ist. | HKEY \_ LOCAL \_ MASCHINE |
Registrykey | Verfügbar, wenn entityType  *Registrierung* ist. | SOFTWARE-Windows NT-Version-Winlogon-Windows-NT-Version-Winlogon
registryValueType | Verfügbar, wenn entityType  *Registrierung* ist. | String
RegistryValue | Verfügbar, wenn entityType  *Registrierung* ist. | 31-00-00-00
deviceId | Die ID(en) des Geräts, das sich auf die Entität bezieht. | 986e5df8b73dacd43c8917d17e523e76b13c75cd

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
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
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
            "comments": [],
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
            "comments": [],
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

- [Zugriff auf die Microsoft 365 Defender-APIs](api-access.md)
- [Informationen zu API-Limits und Lizenzierung](api-terms.md)
- [Verstehen von Fehlercodes](api-error-codes.md)
- [Übersicht über Vorfälle](incidents-overview.md)
- [Vorfall-APIs](api-incident.md)
- [Aktualisieren der Vorfall-API](api-update-incidents.md)
