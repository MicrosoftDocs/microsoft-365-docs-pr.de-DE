---
title: Microsoft Defender für Endpunkt im Microsoft 365 Security Center
description: Informationen zu Änderungen vom Microsoft Defender Security Center zum Microsoft 365 Security Center
keywords: Erste Schritte mit dem Microsoft 365 Security Center, OATP, MDATP, MDO, MDE, einzelnem Fensterausschnitt, konvergenten Portal, Sicherheitsportal, Defender-Sicherheitsportal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: dbbe692b3339a316f924ae4858753bbb961dd70c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165621"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a>Microsoft Defender für Endpunkt im Microsoft 365 Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gilt für:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender für Office 365](/microsoft-365/security/defender-365-security/defender-for-office-365)

Das verbesserte [Microsoft 365 Security Center](overview-security-center.md) kombiniert Sicherheitsfunktionen, die E-Mails, Zusammenarbeit, Identität und Gerätebedrohungen schützen, erkennen, untersuchen und darauf [https://security.microsoft.com](https://security.microsoft.com) reagieren. Dieses Sicherheitscenter vereint Funktionen aus vorhandenen Microsoft-Sicherheitsportalen, einschließlich Microsoft Defender Security Center und dem Office 365 Security & Compliance Center.

Wenn Sie mit dem Microsoft Defender Security Center vertraut sind, hilft dieser Artikel, einige der Änderungen und Verbesserungen im verbesserten Microsoft 365 Security Center zu beschreiben. Es gibt jedoch einige neue und aktualisierte Elemente, die Sie beachten müssen.

In der Vergangenheit war [das Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) das Zuhause von Microsoft Defender for Endpoint. Unternehmenssicherheitsteams haben sie verwendet, um Warnungen über potenzielle fortgeschrittene beständige Bedrohungsaktivitäten oder Datenschutzverletzungen zu überwachen und zu unterstützen. Um die Anzahl der Portale zu reduzieren, ist das Microsoft 365 Security Center das Zuhause für die Überwachung und Verwaltung der Sicherheit in Ihren Microsoft-Identitäten, Daten, Geräten, Apps und Infrastruktur.

Microsoft Defender for Endpoint im Microsoft 365 Security Center unterstützt die Gewährung des Zugriffs auf anbieter für verwaltete Sicherheitsdienste [(Managed Security Service Provider, MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) auf die gleiche Weise, wie der Zugriff [im Microsoft Defender Security Center gewährt wird.](mssp-access.md)


> [!IMPORTANT]
> Was Sie im Microsoft 365 Security Center sehen, hängt von Ihren aktuellen Abonnements ab. Wenn Sie beispielsweise keine Lizenz für Microsoft Defender für Office 365 haben, wird der Abschnitt E-Mail & Zusammenarbeit nicht angezeigt.

>[!Note]
>Das neue einheitliche Portal ist nicht verfügbar für:
>- US Government Community Cloud (GCC)
>- US Government Community Cloud High (GCC High)
>- US Department of Defense
>- Alle US-Behörden mit kommerziellen Lizenzen

Sehen Sie sich das verbesserte Microsoft 365 Security Center an: [https://security.microsoft.com](https://security.microsoft.com) .

Weitere Informationen zu den Vorteilen: [Übersicht über das Microsoft 365 Security Center](overview-security-center.md)

## <a name="whats-changed"></a>Änderungen

Diese Tabelle ist eine Kurzübersicht über die Änderungen zwischen dem Microsoft Defender Security Center und dem Microsoft 365 Security Center.

### <a name="alerts-and-actions"></a>Warnungen und Aktionen

|**Bereich**  |**Beschreibung der Änderung** |
|---------|---------|
| [Vorfälle & Warnungen](incidents-overview.md)  | Im Microsoft 365 Security Center können Sie Vorfälle und Warnungen über alle Endpunkte, E-Mails und Identitäten hinweg verwalten. Wir haben die Erfahrung zusammengeführt, um ihnen zu helfen, verwandte Ereignisse einfacher zu finden. Weitere Informationen finden Sie unter [Incidents Overview](incidents-overview.md).   |
| [Suche](advanced-hunting-overview.md)  |  Wenn Sie benutzerdefinierte Erkennungsregeln ändern, die in Microsoft Defender for Endpoint erstellt wurden, um Identitäts- und E-Mail-Tabellen zu enthalten, werden sie automatisch zu Microsoft 365 Defender verlagert. Die entsprechenden Warnungen werden auch in Microsoft 365 Defender angezeigt. Weitere Informationen zu diesen Änderungen finden Sie unter [Migrate custom detection rules](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules). <br><br>Die `DeviceAlertEvents` Tabelle für die erweiterte Suche ist in Microsoft 365 Defender nicht verfügbar. Zum Abfragen gerätespezifischer Warnungsinformationen in Microsoft 365 Defender können Sie die Tabellen und verwenden, um noch mehr Informationen aus verschiedenen Quellen `AlertInfo` `AlertEvidence` zu speichern. Erstellen Sie Ihre nächste gerätebezogene Abfrage, indem Sie [Write-Abfragen ohne DeviceAlertEvents folgen.](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)|
|[Info-Center](m365d-action-center.md)    | Listet ausstehende und abgeschlossene Aktionen auf, die nach automatisierten Untersuchungen und Korrekturmaßnahmen durchgeführt wurden. Früher hat das Action Center im Microsoft Defender Security Center ausstehende und abgeschlossene Aktionen für Korrekturaktionen aufgelistet, die nur auf Geräten durchgeführt wurden, während automatisierte Untersuchungen Warnungen und den Status aufgelistet haben. Im verbesserten Microsoft 365 Security Center vereint das Action Center Korrekturaktionen und Untersuchungen über E-Mails, Geräte und Benutzer hinweg – alle an einem einzigen Ort.  |
| [Bedrohungsanalyse](threat-analytics.md) |  Zur einfacheren Erkennung und Verwendung an den oberen Rand der Navigationsleiste verschoben. Enthält jetzt Bedrohungsinformationen für Endpunkte sowie E-Mail und Zusammenarbeit.    |

### <a name="endpoints"></a>Endpunkte

|**Bereich**  |**Beschreibung der Änderung**  |
|---------|---------|
|Suche   |  Anstatt in der Überschrift zu sein, bewegt sich die Microsoft Defender for Endpoint-Suchleiste unter dem Abschnitt Endpunkte. Sie können weiterhin nach Geräten, Dateien, Benutzern, URLs, IPs, Sicherheitsrisiken, Software und Empfehlungen suchen.  |
|[Dashboard](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  Dies ist Ihr Sicherheitsbetriebsdashboard. Sehen Sie sich eine Übersicht darüber an, wie viele aktive Warnungen ausgelöst wurden, welche Geräte gefährdet sind, welche Benutzer gefährdet sind, und den Schweregrad für Warnungen, Geräte und Benutzer. Sie können auch sehen, ob auf geräten Sensorprobleme auftreten, ihr Gesamtdienstzustand und wie nicht aufgelöste Warnungen erkannt wurden. |
|Geräteübersicht | Keine Änderungen. |
|[Bedrohungs- und Sicherheitsrisikomanagement](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    Der Name wurde so verkürzt, dass er in den Navigationsbereich passt. Es ist identisch mit dem Abschnitt zur Verwaltung von Bedrohungen und Sicherheitslücken mit allen Seiten darunter.     |
| Partner und APIs | Keine Änderungen. |
| Evaluierungen & Lernprogramme    |     Neue Test- und Lernfunktionen.     |
| Konfigurationsverwaltung   |  Keine Änderungen.  |

> [!NOTE]
> **Die automatische Untersuchung und Behebung** ist jetzt Teil von Vorfällen. Auf der Registerkarte Incident > Investigation werden Ereignisse zur automatischen Untersuchung **und Behebung** angezeigt.

### <a name="access-and-reporting"></a>Zugriff und Berichterstellung

|**Bereich**  |**Beschreibung der Änderung**  |
|---------|---------|
| Berichte  | Siehe Berichte für Endpunkte und E-Mail& zusammenarbeiten, einschließlich Bedrohungsschutz, Geräteintehität und -compliance und anfällige Geräte. |
| Gesundheitswesen  |  Zurzeit werden Links zur Seite "Dienstinte health" im [Microsoft 365 Admin Center angezeigt.](https://admin.microsoft.com/) |
| Einstellungen |  Verwalten Sie Ihre Einstellungen für das Microsoft 365 Security Center, Microsoft 365 Defender, Endpoints, Email & Zusammenarbeit, Identitäten und Geräteerkennung.   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Microsoft 365-Sicherheitsnavigation und -funktionen

Die linke Navigationsleiste oder Schnellstartleiste wird Ihnen vertraut vorkommen. Dieses Sicherheitscenter enthält jedoch einige neue und aktualisierte Elemente.

### <a name="incidents-and-alerts"></a>Vorfälle und Warnungen

Vereint die Verwaltung von Vorfällen und Warnungen über Ihre E-Mails, Geräte und Identitäten hinweg. Die Warnungsseite bietet den vollständigen Kontext für die Warnung, indem Angriffssignale kombiniert werden, um eine detaillierte Story zu erstellen. Eine neue, zentralisierte Ansicht führt nun Warnungen über Workloads hinweg zusammen. Sie können die Daten schnell sichten, untersuchen und entsprechende effektive Maßnahmen ergreifen.

- Erfahren Sie mehr über [Vorfälle](incidents-overview.md)
- [Erfahren Sie mehr über das Verwalten von Warnungen.](investigate-alerts.md)

![Die Schnellstartleiste für Warnungen und Aktionen](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Suche

Suchen Sie proaktiv mithilfe von [erweiterten Suchabfragen](advanced-hunting-overview.md) über Ihre Endpunkte, Office 365-Postfächer und mehr hinweg nach Bedrohungen, Schadsoftware und schädlichen Aktivitäten. Diese leistungsstarken Abfragen können verwendet werden, um Bedrohungsindikatoren und -entitäten auf bekannte und potenzielle Bedrohungen zu finden und zu überprüfen.

[Benutzerdefinierte Erkennungsregeln](custom-detection-rules.md) können aus erweiterten Suchabfragen erstellt werden, damit Sie proaktiv auf Ereignisse achten können, die auf Verletzungsaktivitäten und falsch konfigurierte Geräte hinweisen können.


### <a name="action-center"></a>Info-Center

Im Info-Center zeigt werden die Untersuchungen angezeigt, die durch automatisierte Untersuchungs- und Reaktionsfunktionen erstellt wurden. Diese Möglichkeit der automatisierten Selbstreparatur in Microsoft 365 Defender unterstützt Sicherheitsteams durch automatische Reaktionen auf bestimmte Ereignisse.

[Erfahren Sie mehr über das Info-Center](m365d-action-center.md)

### <a name="threat-analytics"></a>Bedrohungsanalyse

Nutzen Sie Informationen zu Bedrohungen von erfahrenen Microsoft-Sicherheitsexperten. Die Bedrohungsanalyse ermöglicht es Sicherheitsteams, aufkommenden Bedrohungen und Risiken effizienter zu begegnen. Die Bedrohungsanalyse umfasst:

- E-Mail-bezogene Erkennungen und Gegenmaßnahmen durch Microsoft Defender für Office 365 zusätzlich zu den Endpunktdaten, die bereits über Microsoft Defender für Endpunkt verfügbar sind.
- Anzeigen von Vorfällen im Zusammenhang mit den Bedrohungen.
- Verbesserte Benutzeroberfläche für die schnelle Identifizierung und Verwendung nützlicher Informationen in den Berichten.

Sie können auf Die Bedrohungsanalyse entweder über die obere linke Navigationsleiste im Microsoft 365 Security Center oder über eine dedizierte Dashboardkarte zugreifen, auf der die obersten Bedrohungen für Ihre Organisation angezeigt werden.

Erfahren Sie mehr über das [Nachverfolgen und Reagieren auf neue Bedrohungen mit Bedrohungsanalysen](./threat-analytics.md).

### <a name="endpoints-section"></a>Abschnitt "Endpoints"

Anzeigen und Verwalten der Sicherheit von Endpunkten in Ihrer Organisation. Wenn Sie das Microsoft Defender Security Center verwendet haben, sieht es vertraut aus.

![Die Schnellstartleiste für Endpunkte](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>Zugriff und Berichte

Zeigen Sie Berichte an, und nehmen Sie Änderungen an Einstellungen und Benutzerrollen vor.

![Die Schnellstartleiste für Zugriff und Berichterstellung](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>SIEM-API-Verbindungen

Wenn Sie die [Defender for Endpoint SIEM-API verwenden,](../defender-endpoint/enable-siem-integration.md)können Sie dies weiterhin tun. Wir haben neue Links zur API-Nutzlast hinzugefügt, die auf die Warnungsseite oder die Vorfallseite im Microsoft 365-Sicherheitsportal verweisen. Neue API-Felder umfassen LinkToMTP und IncidentLinkToMTP. Weitere Informationen finden Sie unter [Umleiten von Konten von Microsoft Defender for Endpoint zum Microsoft 365 Security Center](./microsoft-365-security-mde-redirection.md).

### <a name="email-alerts"></a>E-Mail-Benachrichtigungen

Sie können weiterhin E-Mail-Warnungen für Defender for Endpoint verwenden. Wir haben neue Links in den E-Mails hinzugefügt, die auf die Warnungsseite oder die Vorfallseite im Microsoft 365 Security Center verweisen. Weitere Informationen finden Sie unter [Umleiten von Konten von Microsoft Defender for Endpoint zum Microsoft 365 Security Center](./microsoft-365-security-mde-redirection.md).

## <a name="related-information"></a>Verwandte Informationen

- [Microsoft 365 Security Center](overview-security-center.md)
- [Microsoft Defender für Endpunkt im Microsoft 365 Security Center](microsoft-365-security-center-mde.md)
- [Umleiten von Konten von Microsoft Defender für Endpunkt zum Microsoft 365 Security Center](microsoft-365-security-mde-redirection.md)