---
title: Listen Vorfälle-API in Microsoft Threat Protection
description: Informationen zum Auflisten von Vorfälle-API in Microsoft Threat Protection
keywords: Liste, Vorfall, Vorfälle, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 54f5ba640ecc175e78c7087df8016e9b715f17f7
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775111"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a>Listen Vorfälle-API in Microsoft Threat Protection

**Gilt für:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.


## <a name="api-description"></a>API-Beschreibung

Die Vorfall-API ermöglicht das Sortieren von Vorfällen, um Prioritäten zu setzen und eine informierte Cyber-Antwort zu erstellen. Es macht eine Sammlung von Vorfällen verfügbar, die von Geräten, e-Mail-Konten und Benutzern in Ihrem Netzwerk gekennzeichnet wurden, innerhalb des Zeitbereichs, den Sie in der Aufbewahrungsrichtlinie für die Umgebung angegeben haben. Die jüngsten Vorfälle werden oben in der Liste angezeigt. Jeder Vorfall enthält ein Array zusammengehöriger Warnungen und zugehöriger Entitäten.

<br>Die API unterstützt die folgenden **OData** -Operatoren:
<br>```$filter``` on: ```lastUpdateTime``` , ```createdTime``` ```status``` und ```assignedTo``` Properties.
<br>```$top``` mit dem Höchstwert von **100**
<br>```$skip```

## <a name="limitations"></a>Einschränkungen

1. Die maximale Seitengröße beträgt **100 Vorfälle**.
2. Die maximale Anzahl von Anforderungen beträgt **50 Anrufe pro Minute** und **1500 Anrufe pro Stunde**.

## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Access Microsoft Threat Protection APIs](api-access.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   Vorfall. Read. all | "Alle Vorfälle lesen"
Anwendung |   Incident. ReadWrite. all | "Alle Vorfälle lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Vorfall. Read | "Vorfälle lesen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Incident. ReadWrite | ' Lesen und Schreiben von Vorfällen '

> [!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
> - Der Benutzer muss über die Berechtigung "anzeigen" für Vorfälle im Portal verfügen.
> - Die Antwort umfasst nur Vorfälle, denen der Benutzer ausgesetzt ist.

## <a name="http-request"></a>HTTP-Anforderung

```
GET /api/incidents
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | Zeichenfolge | Bearer {Token}. **Erforderlich**.


## <a name="request-body"></a>Anforderungstext
Keine

## <a name="response"></a>Antwort
Wenn die Methode erfolgreich verläuft, werden 200 OK und eine Liste von [Vorfällen](api-incident.md) im Antworttext zurückgegeben.

## <a name="schema-mapping"></a>Schema Zuordnung

| Feldname                                | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                | Beispielwert                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Vorfall Metadaten**                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| Vorfall-Nr                                | Eindeutiger Bezeichner, der den Vorfall darstellt.                                                                                                                                                                                                                                                                                                                                                | 924565                                                                                                                                                                                                                                            |
| redirectIncidentId                        | Nur aufgefüllt, wenn ein Vorfall als Teil der Vorfall Verarbeitungslogik mit einem anderen Vorfall zusammengefasst wird.                                                                                                                                                                                                                                                           | 924569                                                                                                                                                                                                                                            |
| Vorfallname                              | Zeichenfolgenwert, der für jeden Vorfall verfügbar ist.                                                                                                                                                                                                                                                                                                                                                  | Ransomware-Aktivität                                                                                                                                                                                                                               |
| createdTime                               | Zeitpunkt, zu dem der Vorfall erstmals erstellt wurde.                                                                                                                                                                                                                                                                                                                                                      | 2020-09-06T14:46:57.0733333 z                                                                                                                                                                                                                      |
| Last Update time                            | Zeitpunkt der letzten Aktualisierung des Vorfalls im Back-End.<br> Dieses Feld kann verwendet werden, wenn der Anforderungsparameter für den Zeitraum festgelegt wird, in dem Vorfälle abgerufen werden.                                                                                                                                                                                                                      | 2020-09-06T14:46:57.29 z                                                                                                                                                                                                                           |
| assignedTo                                | Der Besitzer des Vorfalls oder *null* , wenn kein Besitzer zugewiesen ist.                                                                                                                                                                                                                                                                                                                         | secop2@contoso.com                                                                                                                                                                                                |
| classification                            | Die Spezifikation für den Vorfall. Die Eigenschaftswerte lauten: *unbekannt*, *FalsePositive*, *TruePositive*                                                                                                                                                                                                                                                                           | Unbekannt                                                                                                                                                                                                                                           |
| Bestimmung                             | Gibt die Ermittlung des Vorfalls an. Die Eigenschaftswerte lauten: *nichtin*, *apt*, *Schadsoftware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other*                                                                                                                                                                                                                | Nichtin                                                                                                                                                                                                                                      |
| status                                    | Vorfälle kategorisieren (als *aktiv*oder *aufgelöst*). Auf diese Weise können Sie Ihre Antwort auf Vorfälle organisieren und verwalten.                                                                                                                                                                                                                                                                  | Aktiv                                                                                                                                                                                                                                            |
| Schweregrad                                  | Gibt die möglichen Auswirkungen auf Objekte an. Je höher der Schweregrad, desto größer die Auswirkung. Normalerweise erfordern höhere Severity-Elemente die unmittelbarste Aufmerksamkeit.<br>Einer der folgenden Werte: *Informational*, *Low*, * Mittel und *High*.                                                                                                                                | Mittel                                                                                                                                                                                                                                            |
| tags                                      | Array von benutzerdefinierten Tags, die einem Vorfall zugeordnet sind, beispielsweise zum Kennzeichnen einer Gruppe von Vorfällen mit einem gemeinsamen Merkmal.                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| Warnungen                                    | Array aller Warnungen im Zusammenhang mit dem Vorfall und anderen Informationen, wie Schweregrad, Entitäten, die an der Warnung beteiligt waren, die Quelle der Warnungen.                                                                                                                                                                                                                     | \[\] (Weitere Informationen zu den folgenden Warnfeldern finden Sie unter)                                                                                                                                                                                                          |
| **Warnungs Metadaten**                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| Warnungs-Nr                                   | Eindeutiger Bezeichner zur Darstellung der Warnung                                                                                                                                                                                                                                                                                                                                                   | caD70CFEE2-1F54-32dB-9988-3A868A1EBFAC                                                                                                                                                                                                            |
| Vorfall-Nr                                | Eindeutige ID, die den Vorfall darstellt, dem diese Warnung zugeordnet ist                                                                                                                                                                                                                                                                                                                  | 924565                                                                                                                                                                                                                                            |
| Metadata                             | Dienst, von dem die Warnung stammt, beispielsweise Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP oder Office 365 ATP.                                                                                                                                                                                                                                                                     | MicrosoftCloudAppSecurity                                                                                                                                                                                                                         |
| CreationTime                              | Zeitpunkt, zu dem die Warnung erstmalig erstellt wurde.                                                                                                                                                                                                                                                                                                                                                         | 2020-09-06T14:46:55.7182276 z                                                                                                                                                                                                                      |
| lastUpdatedTime                           | Zeitpunkt, zu dem die Benachrichtigung zuletzt im Back-End aktualisiert wurde.                                                                                                                                                                                                                                                                                                                                           | 2020-09-06T14:46:57.2433333 z                                                                                                                                                                                                                      |
| aufgelöst                              | Zeitpunkt, zu dem die Warnung aufgelöst wurde.                                                                                                                                                                                                                                                                                                                                                              | 2020-09-10T05:22:59Z                                                                                                                                                                                                                              |
| First-Angleichung                             | Zeitpunkt, zu dem von der Warnung zuerst berichtet wurde, dass die Aktivität im Back-End aktualisiert wurde.                                                                                                                                                                                                                                                                                                                             | 2020-09-04T05:22:59Z                                                                                                                                                                                                                              |
| title                                     | Der kurze identifizierende Zeichenfolgenwert, der für jede Warnung verfügbar ist.                                                                                                                                                                                                                                                                                                                                                     | Ransomware-Aktivität                                                                                                                                                                                                                               |
| description                               | Zeichenfolgenwert, der jede Warnung beschreibt.                                                                                                                                                                                                                                                                                                                                                        | Der Benutzer testet Benutzer2 (testUser2@contoso.com) manipulierte 99-Dateien mit mehreren Endungen, die mit der ungewöhnlich *herunterladen*-Erweiterung enden. Dies ist eine ungewöhnliche Anzahl von Datei Manipulationen und deutet auf einen potenziellen Ransomware-Angriff hin. |
| category                                  | Visuelle und numerische Ansicht, wie weit der Angriff in der killkette fortgeschritten ist. Am [Mitra ATT&ck™ Framework](https://attack.mitre.org/)ausgerichtet.                                                                                                                                                                                                                           | Auswirkung                                                                                                                                                                                                                                            |
| status                                    | Benachrichtigungen kategorisieren (als *neu*, *aktiv*oder *aufgelöst*). Auf diese Weise können Sie Ihre Antwort auf Warnungen organisieren und verwalten.                                                                                                                                                                                                                                                                   | Neu                                                                                                                                                                                                                                               |
| Schweregrad                                  | Gibt die möglichen Auswirkungen auf Objekte an. Je höher der Schweregrad, desto größer die Auswirkung. Normalerweise erfordern höhere Severity-Elemente die unmittelbarste Aufmerksamkeit.<br>Einer der folgenden Werte: *Informational*, *Low*, * Mittel und *High*.                                                                                                                                   | Mittel                                                                                                                                                                                                                                            |
| Ermittlungs-Nr                           | Die von dieser Warnung ausgelöste automatische Ermittlungs-ID.                                                                                                                                                                                                                                                                                                                                | 1234                                                                                                                                                                                                                                              |
| investigationState                        | Informationen zum aktuellen Status der Untersuchung. Einer der folgenden: *Unknown*, *terminated*, *SuccessfullyRemediated*, *benigne*, *failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *unsupporteds*, *UnsupportedAlertType*, *SuppressedAlert*. | UnsupportedAlertType                                                                                                                                                                                                                              |
| classification                            | Die Spezifikation für den Vorfall. Die Eigenschaftswerte sind: *Unknown*, *FalsePositive*, *TruePositive* oder *null*                                                                                                                                                                                                                                                                   | Unbekannt                                                                                                                                                                                                                                           |
| Bestimmung                             | Gibt die Ermittlung des Vorfalls an. Die Eigenschaftswerte sind: *nichtin*, *apt*, *Schadsoftware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other* oder  *null*                                                                                                                                                                                                     | Apt                                                                                                                                                                                                                                               |
| assignedTo                                | Der Besitzer des Vorfalls oder *null* , wenn kein Besitzer zugewiesen ist.                                                                                                                                                                                                                                                                                                                            | secop2@contoso.com                                                                                                                                                                                                 |
| darstellername                                 | Die Aktivitätsgruppe (sofern vorhanden), die dieser Warnung zugeordnet ist.                                                                                                                                                                                                                                                                                                                                        | Bor                                                                                                                                                                                                                                             |
| threatFamilyName                          | Bedrohungs Familie, die dieser Warnung zugeordnet ist.                                                                                                                                                                                                                                                                                                                                                   | null                                                                                                                                                                                                                                              |
| mitreTechniques                           | Die Angriffstechniken, die mit dem [Gehrungs&ck](https://attack.mitre.org/)™ Framework ausgerichtet sind.                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| Geräte                                   | Alle Geräte, auf denen Benachrichtigungen im Zusammenhang mit dem Vorfall gesendet wurden.                                                                                                                                                                                                                                                                                                     | \[\] (siehe Details zu Entitätsfeldern unten)                                                                                                                                                                                                         |
| **Geräteformat**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| DeviceID                                  | Die Geräte-ID, wie in Microsoft Defender ATP angegeben.                                                                                                                                                                                                                                                                                                                                                       | 24c222b0b60fe148eeece49ac83910cc6a7ef491                                                                                                                                                                                                          |
| aadDeviceId                               |  Die in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD) festgelegte Geräte-ID. Nur für Domänen verbundene Geräte verfügbar.                                                                                                                                                                                                                                                                                                                              | null                                                                                                                                                                                                                                              |
| deviceDnsName                             | Der vollqualifizierte Domänenname für das Gerät.                                                                                                                                                                                                                                                                                                                                                                        | user5cx.middleeast.corp.contoso.com                                                                                                                                                                                                    |
| osPlatform                                | Die Betriebssystemplattform, die das Gerät ausführt.                                                                                                                                                                                                                                                                                                                                                                     | WindowsServer2016                                                                                                                                                                                                                                 |
| osBuild                                   | Die Buildversion für das Betriebssystem, auf dem das Gerät läuft.                                                                                                                                                                                                                                                                                                                                                                | 14393                                                                                                                                                                                                                                             |
| rbacGroupName                             | Die dem Gerät zugeordnete [rollenbasierte Zugriffs Steuerungsgruppe (Role-Based Access Control](https://docs.microsoft.com/azure/role-based-access-control/overview) , RBAC).                                                                                                                                                                                                                                                                                                                             | WDATP-ring0                                                                                                                                                                                                                                       |
| firstSeen                                 | Zeitpunkt, zu dem das Gerät zum ersten Mal angezeigt wurde.                                                                                                                                                                                                                                                                                                                                                           | 2020-02-06T14:16:01.9330135 z                                                                                                                                                                                                                      |
| healthStatus                              | Der Integritätsstatus des Geräts.                                                                                                                                                                                                                                                                                                                                                                        | Aktiv                                                                                                                                                                                                                                            |
| riskScore                                 | Die Risikobewertung für das Gerät.                                                                                                                                                                                                                                                                                                                                                                       | Hoch                                                                                                                                                                                                                                              |
| Entitäten                                  | Alle Entitäten, die als Teil einer bestimmten Warnung oder mit dieser in Verbindung mit dieser identifiziert wurden.                                                                                                                                                                                                                                                                                | \[\] (siehe Details zu Entitätsfeldern unten)                                                                                                                                                                                                         |
| **Entitäts Format**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| EntityType                                | Entitäten, die als Teil oder mit einer bestimmten Warnung in Verbindung mit identifiziert wurden.<br>Die Eigenschaftenwerte lauten: *User*, *IP*, *URL*, *File*, *Process*, *Mailbox*, *MailMessage*, *mailcluster*, *Registry*                                                                                                                                                                                                     | User                                                                                                                                                                                                                                              |
| SHA1                                      | Verfügbar, wenn EntityType *Datei*ist.<br>Der Datei Hash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.                                                                                                                                                                                                                                                                                    | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd                                                                                                                                                                                                          |
| SHA256                                    | Verfügbar, wenn EntityType *Datei*ist.<br>Der Datei Hash für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.                                                                                                                                                                                                                                                                                    | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043                                                                                                                                                                                  |
| fileName                                  | Verfügbar, wenn EntityType *Datei*ist.<br>Den Dateinamen für Warnungen, die einer Datei oder einem Prozess zugeordnet sind.                                                                                                                                                                                                                                                                                    | Detector.UnitTests.dll                                                                                                                                                                                                                            |
| FilePath                                  | Verfügbar, wenn EntityType *Datei*ist.<br>Der Dateipfad für Warnungen, die einer Datei oder einem Prozess zugeordnet sind                                                                                                                                                                                                                                                                                    | C: \\ \\ Agent \\ \\ \_ work \\ \\ \_ Temp \\ \\ Deploy \_ System 2020-09-06 12 \_ 14 \_ 54 \\ \\ out                                                                                                                                                                    |
| ProcessID                                 | Verfügbar, wenn EntityType *Prozess*ist.                                                                                                                                                                                                                                                                                                                                                     | 24348                                                                                                                                                                                                                                             |
| processCommandLine                        | Verfügbar, wenn EntityType *Prozess*ist.                                                                                                                                                                                                                                                                                                                                                     | " \\ " Ihre Datei kann \_1911150169.exe\\ "" heruntergeladen werden.                                                                                                                                                                                           |
| processCreationTime                       | Verfügbar, wenn EntityType *Prozess*ist.                                                                                                                                                                                                                                                                                                                                                     | 2020-07-18T03:25:38.5269993 z                                                                                                                                                                                                                      |
| parentProcessId                           | Verfügbar, wenn EntityType *Prozess*ist.                                                                                                                                                                                                                                                                                                                                                   | 16840                                                                                                                                                                                                                                             |
| parentProcessCreationTime                 | Verfügbar, wenn EntityType *Prozess*ist.                                                                                                                                                                                                                                                                                                                                                     | 2020-07-18T02:12:32.8616797 z                                                                                                                                                                                                                      |
| ipAddress                                 | Verfügbar, wenn EntityType *IP*ist. <br>IP-Adresse für Warnungen, die Netzwerkereignissen zugeordnet sind, beispielsweise *die Kommunikation mit einem böswilligen Netzwerkziel*.                                                                                                                                                                                                                                   | 62.216.203.204                                                                                                                                                                                                                                    |
| url                                       | Verfügbar, wenn EntityType *URL*ist. <br>URL für Warnungen, die Netzwerkereignissen zugeordnet sind, beispielsweise *die Kommunikation mit einem böswilligen Netzwerkziel*.                                                                                                                                                                                                                                  | down.esales360.cn                                                                                                                                                                                                                                 |
| accountName                               | Verfügbar, wenn EntityType *Benutzer*ist.                                                                                                                                                                                                                                                                                                                                                         | testUser2                                                                                                                                                                                                                                         |
| Domänname                                | Verfügbar, wenn EntityType *Benutzer*ist.                                                                                                                                                                                                                                                                                                                                                        | Europe. Corp. contoso                                                                                                                                                                                                                              |
| userSid                                   | Verfügbar, wenn EntityType *Benutzer*ist.                                                                                                                                                                                                                                                                                                                                                        | S-1-5-21-1721254763-462695806-1538882281-4156657                                                                                                                                                                                                  |
| aadUserId                                 | Verfügbar, wenn EntityType *Benutzer*ist.                                                                                                                                                                                                                                                                                                                                                        | fc8f7484-f813-4db2-afab-bc1507913fb6                                                                                                                                                                                                              |
| userPrincipalName                         | Verfügbar, wenn EntityType *Benutzer* / *Postfach* / -e-*Mail*ist.                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| mailboxDisplayName                        | Verfügbar, wenn EntityType *Postfach*ist.                                                                                                                                                                                                                                                                                                                                                     | Benutzer2 testen                                                                                                                                                                                                                                        |
| mailboxAddress                            | Verfügbar, wenn EntityType *Benutzer* / *Postfach* / -e-*Mail*ist.                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| clusterBy                                 | Verfügbar, wenn EntityType  *mailcluster*ist.                                                                                                                                                                                                                                                                                                                                                 | Thema P2SenderDomain; ContentType                                                                                                                                                                                                                |
| sender                                    | Verfügbar, wenn EntityType *Benutzer* / *Postfach* / -e-*Mail*ist.                                                                                                                                                                                                                                                                                                                                  | user.abc@mail.contoso.co.in                                                                                                                                                                 |
| recipient                                 | Verfügbar, wenn EntityType *MailMessage*ist.                                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                       |
| subject                                   | Verfügbar, wenn EntityType *MailMessage*ist.                                                                                                                                                                                                                                                                                                                                                 | \[Externe \] Aufmerksamkeit                                                                                                                                                                                                                            |
| Zustellungs-Dienst                            | Verfügbar, wenn EntityType *MailMessage*ist.                                                                                                                                                                                                                                                                                                                                                 | Geliefert                                                                                                                                                                                                                                         |
| securityGroupId                           | Verfügbar, wenn EntityType  *SecurityGroup*ist.                                                                                                                                                                                                                                                                                                                                               | 301c47c8-e15f-4059-ab09-e2ba9ffd372b                                                                                                                                                                                                              |
| securityGroupName                         | Verfügbar, wenn EntityType  *SecurityGroup*ist.                                                                                                                                                                                                                                                                                                                                               | Netzwerk Konfigurations Operatoren                                                                                                                                                                                                                   |
| registryHive                              | Verfügbar, wenn EntityType in der  *Registrierung*ist.                                                                                                                                                                                                                                                                                                                                                    | HKEY \_ lokaler \_ Computer                                                                                                                                                                                                                              |
| registryKey                               | Verfügbar, wenn EntityType in der  *Registrierung*ist.                                                                                                                                                                                                                                                                                                                                                     | Software \\ \\ Microsoft \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon                                                                                                                                                                                 |
| registryValueType                         | Verfügbar, wenn EntityType in der  *Registrierung*ist.                                                                                                                                                                                                                                                                                                                                                    | Zeichenfolge                                                                                                                                                                                                                                            |
| REGISTRYVALUE                             | Verfügbar, wenn EntityType in der  *Registrierung*ist.                                                                                                                                                                                                                                                                                                                                                    | 31-00-00-00                                                                                                                                                                                                                                       |
| deviceId                                  | Die ID (falls vorhanden) des Geräts, das mit der Entität verbunden ist.                                                                                                                                                                                                                                                                                                                                           | 986e5df8b73dacd43c8917d17e523e76b13c75cd                                                                                                                                                                                                          |



## <a name="example"></a>Beispiel

**Anforderung**

```
GET https://api.security.microsoft.com/api/incidents
```

**Response**
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

## <a name="related-topic"></a>Verwandtes Thema
- [Vorfall-APIs](api-incident.md)
- [Vorfall aktualisieren](api-update-incidents.md)
