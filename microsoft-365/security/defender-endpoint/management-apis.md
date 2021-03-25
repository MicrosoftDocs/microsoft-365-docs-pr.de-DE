---
title: Übersicht über Verwaltung und APIs
ms.reviewer: ''
description: Erfahren Sie mehr über die Verwaltungstools und API-Kategorien in Microsoft Defender ATP
keywords: onboarding, api, siem, rbac, access, portal, integration, investigation, response, entities, entity, user context, application context, streaming
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
ms.openlocfilehash: 094a7c94c5c1efd01f744c877467c443a5183737
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066832"
---
# <a name="overview-of-management-and-apis"></a>Übersicht über Verwaltung und APIs 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


Defender for Endpoint unterstützt eine Vielzahl von Optionen, um sicherzustellen, dass Kunden die Plattform problemlos übernehmen können. 

In der Erkenntnis, dass Kundenumgebungen und -strukturen variieren können, wurde Defender for Endpoint mit Flexibilität und präziser Steuerung erstellt, um unterschiedliche Kundenanforderungen zu erfüllen. 

## <a name="endpoint-onboarding-and-portal-access"></a>Endpunkt-Onboarding und Portalzugriff 

Das Geräte onboarding ist vollständig in Microsoft Endpoint Manager und Microsoft Intune für Clientgeräte und Azure Security Center für Servergeräte integriert und bietet eine vollständige End-to-End-Erfahrung in Konfiguration, Bereitstellung und Überwachung. Darüber hinaus unterstützt Microsoft Defender for Endpoint Gruppenrichtlinien und andere Tools von Drittanbietern, die für die Geräteverwaltung verwendet werden.

Defender for Endpoint bietet eine feinkörnige Kontrolle darüber, was Benutzer mit Zugriff auf das Portal durch die Flexibilität der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC) sehen und tun können. Das RBAC-Modell unterstützt alle Varianten der Struktur von Sicherheitsteams:
- Global verteilte Organisationen und Sicherheitsteams
- Teams für mehrstufige Sicherheitsvorgänge
- Vollständig getrennte Abteilungen mit einzelnen zentralen teams für globale Sicherheitsvorgänge 

## <a name="available-apis"></a>Verfügbare APIs
Die Microsoft Defender for Endpoint-Lösung baut auf einer integrationsbereiten Plattform auf.

Defender for Endpoint macht einen großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar. Mit diesen APIs können Sie Workflows automatisieren und innovationen basierend auf defender for Endpoint-Funktionen entwickeln.

![Abbildung der verfügbaren API und Integration in Microsoft Defender for Endpoint](images/mdatp-apis.png)  

Die Defender for Endpoint-APIs können in drei gruppen:
- Microsoft Defender für Endpunkt-APIs 
- Unformatierte Datenstreaming-API
- SIEM-Integration

## <a name="microsoft-defender-for-endpoint-apis"></a>Microsoft Defender für Endpunkt-APIs

Defender for Endpoint bietet ein mehrschichtiges API-Modell, das Daten und Funktionen in einem strukturierten, übersichtlichen und einfach zu verwendenden Modell verfügbar macht, das über ein standardmäßiges Azure AD-basiertes Authentifizierungs- und Autorisierungsmodell verfügbar gemacht wird, das den Zugriff im Kontext von Benutzern oder SaaS-Anwendungen ermöglicht. Das API-Modell wurde entwickelt, um Entitäten und Funktionen in einer konsistenten Form verfügbar zu machen. 

Sehen Sie sich dieses Video an, um einen schnellen Überblick über die APIs von Defender for Endpoint zu erhalten. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

Die **Untersuchungs-API** macht den Reichhaltigen von Defender for Endpoint verfügbar – das Verfügbar machen berechnete oder "profilierte" Entitäten (z. B. Gerät, Benutzer und Datei) und diskrete Ereignisse (z. B. Prozesserstellung und Dateierstellung), die in der Regel ein Verhalten im Zusammenhang mit einer Entität beschreiben und den Zugriff auf Daten über Untersuchungsschnittstellen ermöglichen, die einen abfragebasierten Zugriff auf Daten ermöglichen. Weitere Informationen finden Sie unter [Supported APIs](exposed-apis-list.md).

Die **Reaktions-API** macht die Möglichkeit verfügbar, Aktionen im Dienst und auf Geräten zu ergreifen, sodass Kunden Indikatoren abrufen, Einstellungen verwalten, Warnungsstatus verwalten sowie Reaktionsaktionen auf Geräten programmgesteuert ausführen können, z. B. Geräte vom Netzwerk isolieren, Quarantänedateien und andere. 

## <a name="raw-data-streaming-api"></a>Unformatierte Datenstreaming-API 
Die Raw Data Streaming-API von Defender for Endpoint bietet Kunden die Möglichkeit, Echtzeitereignisse und Warnungen von ihren Instanzen innerhalb eines einzelnen Datenstroms zu senden, was einen Mechanismus für die Zustellung mit niedriger Latenz und hohem Durchsatz bietet.

Die Defender for Endpoint-Ereignisinformationen werden zur langfristigen Datenaufbewahrung direkt an den Azure-Speicher oder an Azure Event Hubs zur Nutzung durch Visualisierungsdienste oder zusätzliche Datenverarbeitungsmodule gesendet. 

Weitere Informationen finden Sie unter [Raw data streaming API](raw-data-export.md).


## <a name="siem-api"></a>SIEM-API
Wenn Sie die Integration von Sicherheitsinformationen und Ereignisverwaltung (SIEM) aktivieren, können Sie Erkennungen aus Microsoft Defender Security Center mithilfe Ihrer SIEM-Lösung abrufen oder eine direkte Verbindung mit der REST-API für Erkennungen herstellen. Dadurch wird der Abschnitt MITM-Connectorzugriffsdetails mit vordefinierten Werten aktiviert, und eine Anwendung wird unter Ihrem Azure Active Directory (Azure AD)-Mandanten erstellt. Weitere Informationen finden Sie unter [SIEM-Integration](enable-siem-integration.md).

## <a name="related-topics"></a>Verwandte Themen
- [Zugreifen auf die Microsoft Defender for Endpoint-APIs ](apis-intro.md)
- [Unterstützte APIs](exposed-apis-list.md)
- [Technische Partnerchancen](partner-integration.md)

