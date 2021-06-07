---
title: Microsoft Defender für Endpunkt im Microsoft 365 Security Center
description: Erfahren Sie mehr über Änderungen vom Microsoft Defender Security Center zum Microsoft 365 Security Center
keywords: Erste Schritte mit dem Microsoft 365 Security Center, Microsoft Defender für Office 365, Microsoft Defender für Endpunkt, MDO, MDE, einzelner Bereich, zusammengeführtes Portal, Sicherheitsportal, Defender Security-Portal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 487fc87c613d7321e3ae608097d98d2c90f8874e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771909"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a>Microsoft Defender für Endpunkt im Microsoft 365 Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender für Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

## <a name="quick-reference"></a>Kurzübersicht

In der Abbildung und der tabelle unten sind die Änderungen in der Navigation zwischen dem Microsoft Defender Security Center und dem Microsoft 365 Security Center aufgeführt.

> [!div class="mx-imgBorder"]
> ![Abbildung, was wohin verschoben wurde](../../media/mde-m3d-security-center.png)

| Microsoft Defender Security Center | Microsoft 365 Security Center |
|---------|---------|
| Dashboards <ul><li>Sicherheitsvorgänge</li><li>Bedrohungsanalyse</li></ul>  |Start <ul><li>Bedrohungsanalyse</li></ul>   |
| Vorfälle | Vorfälle und Benachrichtigungen |
| Geräteübersicht | Geräteübersicht |
| Benachrichtigungswarteschlange | Vorfälle und Benachrichtigungen |
| Automatisierte Untersuchungen | Info-Center |
| Erweiterte Suche | Suche |
| Berichte | Berichte |
| Partner & APIs | Partner & APIs |
| Bedrohungs- &-Sicherheitsrisikoverwaltung | Bedrohungs- und Sicherheitsrisikomanagement |
| Evaluierung und Lernprogramme | Lernprogramme zu Evaluierungs- & |
| Konfigurationsverwaltung | Konfigurationsverwaltung |
| Einstellungen | Einstellungen | 

Das verbesserte [Microsoft 365 Security Center](overview-security-center.md) kombiniert [https://security.microsoft.com](https://security.microsoft.com) Sicherheitsfunktionen, die E-Mail-, Zusammenarbeits-, Identitäts- und Gerätebedrohungen schützen, erkennen, untersuchen und darauf reagieren. Dieses Security Center vereint Funktionen aus vorhandenen Microsoft-Sicherheitsportalen, einschließlich Microsoft Defender Security Center und dem Office 365 Security & Compliance Center.

Wenn Sie mit dem Microsoft Defender Security Center vertraut sind, beschreibt dieser Artikel einige der Änderungen und Verbesserungen im verbesserten Microsoft 365 Security Center. Es gibt jedoch einige neue und aktualisierte Elemente, die Sie beachten sollten.

In der Vergangenheit war die [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) die Startseite von Microsoft Defender für Endpunkt. Enterprise Sicherheitsteams haben es verwendet, um Warnungen über potenzielle fortgeschrittene dauerhafte Bedrohungsaktivitäten oder Datenschutzverletzungen zu überwachen und darauf zu reagieren. Um die Anzahl der Portale zu reduzieren, ist das Microsoft 365 Security Center die Zentrale für die Überwachung und Verwaltung der Sicherheit über Ihre Microsoft-Identitäten, Daten, Geräte, Apps und Infrastruktur hinweg.

Microsoft Defender für Endpunkt im Microsoft 365 Security Center unterstützt das Gewähren des [Zugriffs auf verwaltete Sicherheitsdienstanbieter (Managed Security Service Providers, MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) auf die gleiche Weise, wie [der Zugriff im Microsoft Defender Security Center gewährt wird.](mssp-access.md)


> [!IMPORTANT]
> Was im Microsoft 365 Security Center angezeigt wird, hängt von Ihren aktuellen Abonnements ab. Wenn Sie beispielsweise keine Lizenz für Microsoft Defender für Office 365 haben, wird der Abschnitt "E-Mail & Zusammenarbeit" nicht angezeigt.

>[!Note]
>Das neue einheitliche Portal ist nicht verfügbar für:
>- US Government Community Cloud (GCC)
>- US Government Community Cloud High (GCC High)
>- US-Verteidigungsministerium
>- Alle US-Regierungseinrichtungen mit kommerziellen Lizenzen

Werfen Sie einen Blick auf das verbesserte Microsoft 365 Security Center: [https://security.microsoft.com](https://security.microsoft.com) .

Weitere Informationen zu den Vorteilen: [Übersicht über das Microsoft 365 Security Center](overview-security-center.md)

## <a name="whats-changed"></a>Änderungen

Diese Tabelle ist eine Kurzübersicht der Änderungen zwischen dem Microsoft Defender Security Center und dem Microsoft 365 Security Center.

### <a name="alerts-and-actions"></a>Warnungen und Aktionen

| Bereich | Beschreibung der Änderung |
|---------|---------|
| [Vorfälle & Warnungen](incidents-overview.md)  | Im Microsoft 365 Security Center können Sie Vorfälle und Warnungen über alle Endpunkte, E-Mails und Identitäten hinweg verwalten. Wir haben die Erfahrung zusammengeführt, um Ihnen zu helfen, verwandte Ereignisse einfacher zu finden. Weitere Informationen finden Sie unter [Incidents Overview](incidents-overview.md).   |
| [Suche](advanced-hunting-overview.md)  |  Wenn Sie benutzerdefinierte Erkennungsregeln ändern, die in Microsoft Defender für Endpunkt erstellt wurden, um Identitäts- und E-Mail-Tabellen einzuschließen, werden sie automatisch zu Microsoft 365 Defender verschoben. Die entsprechenden Warnungen werden auch in Microsoft 365 Defender angezeigt. Weitere Informationen zu diesen Änderungen finden Sie unter [Migrieren benutzerdefinierter Erkennungsregeln.](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules) <br><br>Die `DeviceAlertEvents` Tabelle für die erweiterte Suche ist in Microsoft 365 Defender nicht verfügbar. Wenn Sie gerätespezifische Warnungsinformationen in Microsoft 365 Defender abfragen möchten, können Sie die Und-Tabellen verwenden, `AlertInfo` um noch mehr Informationen aus einer Vielzahl von Quellen `AlertEvidence` aufzunehmen. Erstellen Sie Ihre nächste gerätebezogene Abfrage, indem [Sie Write-Abfragen ohne DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)ausführen.|
|[Info-Center](m365d-action-center.md)    | Listet ausstehende und abgeschlossene Aktionen auf, die nach automatisierten Untersuchungen und Abhilfemaßnahmen ausgeführt wurden. Früher wurden im Info-Center im Microsoft Defender Security Center ausstehende und abgeschlossene Aktionen für Abhilfemaßnahmen aufgelistet, die nur auf Geräten durchgeführt wurden, während automatisierte Untersuchungen Warnungen und Status aufgelistet haben. Im verbesserten Microsoft 365 Security Center vereint das Info-Center Abhilfemaßnahmen und Untersuchungen für E-Mails, Geräte und Benutzer – alles an einem Ort.  |
| [Bedrohungsanalyse](threat-analytics.md) |  Zur einfacheren Ermittlung und Verwendung an den oberen Rand der Navigationsleiste verschoben. Enthält jetzt Bedrohungsinformationen sowohl für Endpunkte als auch für E-Mails und die Zusammenarbeit.    |

### <a name="endpoints"></a>Endpunkte

| Bereich | Beschreibung der Änderung |
|---------|---------|
|Suchen   |  Anstatt in der Überschrift zu sein, wird die Microsoft Defender für Endpunkt-Suchleiste unter den Endpunktabschnitt verschoben. Sie können weiterhin nach Geräten, Dateien, Benutzern, URLs, IPs, Sicherheitsrisiken, Software und Empfehlungen suchen.  |
|[Dashboard](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  Dies ist Ihr Dashboard für den Sicherheitsbetrieb. Eine Übersicht darüber, wie viele aktive Warnungen ausgelöst wurden, welche Geräte gefährdet sind, welche Benutzer gefährdet sind und schweregrade für Warnungen, Geräte und Benutzer. Sie können auch sehen, ob Geräte Sensorprobleme haben, wie der allgemeine Dienststatus und wie unaufgelöste Warnungen erkannt wurden. |
|Geräteübersicht | Keine Änderungen. |
|[Bedrohungs- und Sicherheitsrisikomanagement](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    Der Name wurde so gekürzt, dass er in den Navigationsbereich passt. Es ist identisch mit dem Bedrohungs- und Sicherheitsrisikomanagement Abschnitt mit allen Seiten darunter.     |
| Partner und APIs | Keine Änderungen. |
| Lernprogramme zu Evaluierungen &    |     Neue Test- und Lernfunktionen.     |
| Konfigurationsverwaltung   |  Keine Änderungen.  |

> [!NOTE]
> **Die automatische Untersuchung und Behebung** ist jetzt Teil von Vorfällen. Auf der Registerkarte **"Vorfall > Untersuchung"** werden automatisierte Untersuchungs- und Wartungsereignisse angezeigt.

> [!TIP]
> Die Gerätesuche erfolgt über Endpunkte > Suche.

### <a name="access-and-reporting"></a>Zugriff und Berichterstellung

| Bereich | Beschreibung der Änderung |
|---------|---------|
| Berichte  | Siehe Berichte zu Endpunkten und E-Mail-& Zusammenarbeit, einschließlich Bedrohungsschutz, Geräteintegrität und Compliance sowie anfällige Geräte. |
| Gesundheitswesen  |  Derzeit werden Links zur Seite "Dienststatus" im [Microsoft 365 Admin Center angezeigt.](https://admin.microsoft.com/) |
| Einstellungen |  Verwalten Sie Ihre Einstellungen für das Microsoft 365 Security Center, Microsoft 365 Defender, Endpunkte, E-Mail-& Zusammenarbeit, Identitäten und Geräteermittlung.   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Microsoft 365 Sicherheitsnavigation und -funktionen

Die linke Navigationsleiste oder Schnellstartleiste wird Ihnen vertraut vorkommen. Dieses Sicherheitscenter enthält jedoch einige neue und aktualisierte Elemente.

### <a name="incidents-and-alerts"></a>Vorfälle und Warnungen

Vereint die Verwaltung von Vorfällen und Warnungen über Ihre E-Mails, Geräte und Identitäten hinweg. Die Warnungsseite bietet den vollständigen Kontext der Warnung, indem Angriffssignale kombiniert werden, um eine detaillierte Story zu erstellen. Eine neue, zentralisierte Ansicht führt nun Warnungen über Workloads hinweg zusammen. Sie können die Daten schnell sichten, untersuchen und entsprechende effektive Maßnahmen ergreifen.

- Erfahren Sie mehr über [Vorfälle](incidents-overview.md)
- [Erfahren Sie mehr über das Verwalten von Warnungen.](investigate-alerts.md)

![Die Schnellstartleiste für Warnungen und Aktionen](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Suche

Suchen Sie proaktiv mithilfe von [erweiterten Suchabfragen](advanced-hunting-overview.md) über Ihre Endpunkte, Office 365-Postfächer und mehr hinweg nach Bedrohungen, Schadsoftware und schädlichen Aktivitäten. Diese leistungsstarken Abfragen können verwendet werden, um Bedrohungsindikatoren und Entitäten für bekannte und potenzielle Bedrohungen zu suchen und zu überprüfen.

[Benutzerdefinierte Erkennungsregeln](custom-detection-rules.md) können aus erweiterten Suchabfragen erstellt werden, um Proaktive Überwachung auf Ereignisse zu ermöglichen, die möglicherweise auf Aktivitäten bei Sicherheitsverletzungen und falsch konfigurierte Geräte hindeuten.


### <a name="action-center"></a>Info-Center

Im Info-Center zeigt werden die Untersuchungen angezeigt, die durch automatisierte Untersuchungs- und Reaktionsfunktionen erstellt wurden. Diese Möglichkeit der automatisierten Selbstreparatur in Microsoft 365 Defender unterstützt Sicherheitsteams durch automatische Reaktionen auf bestimmte Ereignisse.

[Erfahren Sie mehr über das Info-Center.](m365d-action-center.md)

### <a name="threat-analytics"></a>Bedrohungsanalyse

Nutzen Sie Informationen zu Bedrohungen von erfahrenen Microsoft-Sicherheitsexperten. Die Bedrohungsanalyse ermöglicht es Sicherheitsteams, aufkommenden Bedrohungen und Risiken effizienter zu begegnen. Die Bedrohungsanalyse umfasst:

- E-Mail-bezogene Erkennungen und Gegenmaßnahmen durch Microsoft Defender für Office 365 zusätzlich zu den Endpunktdaten, die bereits über Microsoft Defender für Endpunkt verfügbar sind.
- Anzeigen von Vorfällen im Zusammenhang mit den Bedrohungen.
- Verbesserte Benutzeroberfläche für die schnelle Identifizierung und Verwendung nützlicher Informationen in den Berichten.

Sie können auf die Bedrohungsanalyse entweder über die obere linke Navigationsleiste im Microsoft 365 Security Center oder über eine dedizierte Dashboardkarte zugreifen, die die wichtigsten Bedrohungen für Ihre Organisation anzeigt.

Erfahren Sie mehr darüber, wie Sie [neue Bedrohungen mithilfe von Bedrohungsanalysen nachverfolgen und darauf reagieren](./threat-analytics.md)können.

### <a name="endpoints-section"></a>Endpunktabschnitt

Anzeigen und Verwalten der Sicherheit von Endpunkten in Ihrer Organisation. Wenn Sie die Microsoft Defender Security Center verwendet haben, sieht sie vertraut aus.

![Die Schnellstartleiste für Endpunkte](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>Zugriff und Berichte

Zeigen Sie Berichte an, und nehmen Sie Änderungen an Einstellungen und Benutzerrollen vor.

![Die Schnellstartleiste für Zugriff und Berichterstellung](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>SIEM-API-Verbindungen

Wenn Sie die [Defender für Endpunkt-SIEM-API](../defender-endpoint/enable-siem-integration.md)verwenden, können Sie dies weiterhin tun. Wir haben neue Links zur API-Nutzlast hinzugefügt, die auf die Warnungsseite oder die Vorfallseite im Microsoft 365 Sicherheitsportal verweisen. Zu den neuen API-Feldern gehören LinkToMTP und IncidentLinkToMTP. Weitere Informationen finden Sie unter [Umleiten von Konten von Microsoft Defender für Endpunkt an das Microsoft 365 Security Center.](./microsoft-365-security-mde-redirection.md)

### <a name="email-alerts"></a>E-Mail-Warnungen

Sie können weiterhin E-Mail-Warnungen für Defender für Endpunkt verwenden. Wir haben neue Links in den E-Mails hinzugefügt, die auf die Warnungsseite oder die Vorfallseite im Microsoft 365 Security Center verweisen. Weitere Informationen finden Sie unter [Umleiten von Konten von Microsoft Defender für Endpunkt an das Microsoft 365 Security Center.](./microsoft-365-security-mde-redirection.md)

### <a name="managed-security-service-providers-mssp"></a>Managed Security Service Providers (MSSP)

Die Gleichzeitige Anmeldung bei mehreren Mandanten in derselben Browsersitzung wird im einheitlichen Portal derzeit nicht unterstützt. Sie können die automatische Umleitung deaktivieren, indem Sie [zum früheren Microsoft Defender für Endpunkt-Portal wechseln,](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal)um diese Funktionalität beizubehalten, bis das Problem behoben ist.

## <a name="related-information"></a>Verwandte Informationen

- [Microsoft 365 Security Center](overview-security-center.md)
- [Microsoft Defender für Endpunkt im Microsoft 365 Security Center](microsoft-365-security-center-mde.md)
- [Umleiten von Konten von Microsoft Defender für Endpunkt zum Microsoft 365 Security Center](microsoft-365-security-mde-redirection.md)
