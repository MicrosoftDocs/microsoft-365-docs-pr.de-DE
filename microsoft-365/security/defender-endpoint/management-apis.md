---
title: Übersicht über die Verwaltung und APIs
ms.reviewer: ''
description: Erfahren Sie mehr über die Verwaltungstools und API-Kategorien in Microsoft Defender für Endpunkt
keywords: Onboarding, API, Siem, rbac, Zugriff, Portal, Integration, Untersuchung, Antwort, Entitäten, Entität, Benutzerkontext, Anwendungskontext, Streaming
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 34fb58c2e32f69cda064bb6db4b180c78ba5d451
ms.sourcegitcommit: f0118e61e490496cb23189cc5c73b23e2ba939be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52780153"
---
# <a name="overview-of-management-and-apis"></a>Übersicht über die Verwaltung und APIs 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


Defender für Endpunkt unterstützt eine Vielzahl von Optionen, um sicherzustellen, dass Kunden die Plattform problemlos übernehmen können. 

Um zu bestätigen, dass Kundenumgebungen und -strukturen variieren können, wurde Defender für Endpunkt mit Flexibilität und präziser Kontrolle erstellt, um unterschiedliche Kundenanforderungen zu erfüllen. 

## <a name="endpoint-onboarding-and-portal-access"></a>Endpunkt-Onboarding und Portalzugriff 

Das Geräte-Onboarding ist vollständig in Microsoft Endpoint Manager und Microsoft Intune für Clientgeräte und Azure Defender für Servergeräte integriert und bietet eine vollständige End-to-End-Erfahrung bei Konfiguration, Bereitstellung und Überwachung. Darüber hinaus unterstützt Microsoft Defender für Endpunkt Gruppenrichtlinien und andere Tools von Drittanbietern, die für die Geräteverwaltung verwendet werden.

Defender für Endpunkt bietet eine differenzierte Kontrolle darüber, was Benutzer mit Zugriff auf das Portal durch die Flexibilität der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC) sehen und tun können. Das RBAC-Modell unterstützt alle Arten von Sicherheitsteams:
- Global verteilte Organisationen und Sicherheitsteams
- Teams für mehrstufige Modellsicherheitsvorgänge
- Vollständig getrennte Abteilungen mit einzelnen zentralen globalen Sicherheitsteams 

## <a name="available-apis"></a>Verfügbare APIs
Die Microsoft Defender für Endpunkt-Lösung basiert auf einer integrationsfähigen Plattform.

Defender für Endpunkt macht einen Großteil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar. Diese APIs ermöglichen es Ihnen, Workflows zu automatisieren und Innovationen basierend auf den Defender für Endpunkt-Funktionen zu entwickeln.

![Abbildung der verfügbaren API und Integration in Microsoft Defender für Endpunkt](images/mdatp-apis.png)  

Die Defender für Endpunkt-APIs können in drei Gruppen unterteilt werden:
- Microsoft Defender für Endpunkt-APIs 
- API für das Streaming von Rohdaten
- SIEM-Integration

## <a name="microsoft-defender-for-endpoint-apis"></a>Microsoft Defender für Endpunkt-APIs

Defender für Endpunkt bietet ein mehrstufiges API-Modell, das Daten und Funktionen in einem strukturierten, klaren und einfach zu verwendenden Modell verfügbar macht, das über ein standardmäßiges Azure AD-basiertes Authentifizierungs- und Autorisierungsmodell verfügbar gemacht wird, das den Zugriff im Kontext von Benutzern oder SaaS-Anwendungen ermöglicht. Das API-Modell wurde entwickelt, um Entitäten und Funktionen in einer konsistenten Form verfügbar zu machen. 

Sehen Sie sich dieses Video an, um einen schnellen Überblick über die APIs von Defender für Endpunkt zu erhalten. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

Die **Untersuchungs-API** macht den Nutzen von Defender für Endpunkt verfügbar – berechnete oder "profilierte" Entitäten (z. B. Gerät, Benutzer und Datei) und diskrete Ereignisse (z. B. Prozesserstellung und Dateierstellung), die in der Regel ein Verhalten im Zusammenhang mit einer Entität beschreiben und den Zugriff auf Daten über Untersuchungsschnittstellen ermöglichen, die einen abfragebasierten Zugriff auf Daten ermöglichen. Weitere Informationen finden Sie unter [Unterstützte APIs.](exposed-apis-list.md)

Die **Antwort-API** bietet die Möglichkeit, Aktionen im Dienst und auf Geräten auszuführen, sodass Kunden Indikatoren erfassen, Einstellungen, Warnungsstatus verwalten sowie Reaktionsaktionen auf Geräten programmgesteuert ausführen können, z. B. das Isolieren von Geräten aus dem Netzwerk, das Isolieren von Dateien und anderen. 

## <a name="raw-data-streaming-api"></a>API für das Streaming von Rohdaten 
Die Defender für Endpunkt-Streaming-API für Rohdaten bietet Kunden die Möglichkeit, Echtzeitereignisse und Warnungen aus ihren Instanzen zu versenden, sobald sie innerhalb eines einzelnen Datenstroms auftreten, und bietet einen Übermittlungsmechanismus mit geringer Latenz und hohem Durchsatz.

Die Defender für Endpunkt-Ereignisinformationen werden zur langfristigen Datenaufbewahrung direkt an den Azure-Speicher oder an Azure Event Hubs zur Nutzung durch Visualisierungsdienste oder zusätzliche Datenverarbeitungsmodule übertragen. 

Weitere Informationen finden Sie unter ["Streaming-API für Rohdaten".](raw-data-export.md)

Die neue Microsoft 365 Defender Streaming-API umfasst neben Geräteereignissen E-Mail- und Benachrichtigungsereignisse. Weitere Informationen finden Sie unter [Microsoft 365 Defender Streaming-API.](../defender/streaming-api.md)


## <a name="siem-api"></a>SIEM-API
Wenn Sie die Integration von Sicherheitsinformationen und Ereignisverwaltung (Security Information and Event Management, SIEM) aktivieren, können Sie Erkennungen aus Microsoft Defender Security Center mit Ihrer SIEM-Lösung abrufen oder eine direkte Verbindung mit der REST-API für Erkennungen herstellen. Dadurch wird der Abschnitt "SIEM-Connectorzugriffsdetails" mit vordefinierten Werten aktiviert, und eine Anwendung wird unter Ihrem Azure Active Directory (Azure AD)-Mandanten erstellt. Weitere Informationen finden Sie unter [SIEM-Integration.](enable-siem-integration.md)

## <a name="related-topics"></a>Verwandte Themen
- [Zugreifen auf die Microsoft Defender für Endpunkt-APIs ](apis-intro.md)
- [Unterstützte APIs](exposed-apis-list.md)
- [Chancen für technische Partner](partner-integration.md)

