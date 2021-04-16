---
title: Microsoft Defender for Endpoint-Partnerchancen und -szenarien
ms.reviewer: ''
description: Erfahren Sie, wie Sie vorhandene Sicherheitsangebote über das offene Framework und einen reichhaltigen Satz von APIs zum Erstellen von Erweiterungen und Integrationen in Microsoft Defender for Endpoint erweitern können.
keywords: API, Partner, extend, open framework, apis, extensions, integrations, detection, management, response, vulnerabilities, intelligence
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
ms.openlocfilehash: be2f33514a568f290a3fc5cf0adc62db72243a6f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861109"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a>Microsoft Defender for Endpoint-Partnerchancen und -szenarien

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Partner können ihre vorhandenen Sicherheitsangebote auf einfache Weise über das offene Framework und einen reichhaltigen und vollständigen Satz von APIs erweitern, um Erweiterungen und Integrationen mit Defender for Endpoint zu erstellen. 

Die APIs umfassen Funktionsbereiche wie Erkennung, Verwaltung, Reaktion, Sicherheitsrisiken und intelligenceweite Anwendungsbereiche. Je nach Fall und Bedarf können Partner Daten von Defender for Endpoint streamen oder abfragen. 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a>Szenario 1: Korrelation externer Warnungen und automatisierte Untersuchung und Behebung
Defender for Endpoint bietet einzigartige automatisierte Untersuchungs- und Behebungsfunktionen, um die Reaktion auf Vorfälle in einem großen Umfang zu unterstützen. 

Die Integration der automatisierten Untersuchungs- und Reaktionsfunktionen in andere Lösungen wie Netzwerksicherheitsprodukte oder andere Endpunktsicherheitsprodukte hilft bei der Problembeantwortung. Durch die Integration werden auch die Komplexitäten der Netzwerk- und Gerätesignalkorrelation minimiert und die Untersuchungs- und Bedrohungsbehebungsmaßnahmen auf Geräten effektiv reduziert.

Defender for Endpoint bietet unterstützung für dieses Szenario in den folgenden Formen:

- Externe Warnungen können in Defender for Endpoint übertragen und neben zusätzlichen gerätebasierten Warnungen von Defender for Endpoint angezeigt werden. Diese Ansicht bietet den vollständigen Kontext der Warnung – mit dem tatsächlichen Prozess und der vollständigen Angriffsgeschichte.

- Sobald eine Warnung generiert wurde, wird das Signal für alle geschützten Defender for Endpoint-Endpunkte im Unternehmen freigegeben. Defender for Endpoint reagiert sofort automatisiert oder vom Operator unterstützt, um die Warnung zu adressieren.

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a>Szenario 2: Integration von Sicherheits orchestrierung und Automatisierungsantwort (SOAR)
Orchestrierungslösungen können beim Erstellen von Playbooks helfen und das umfassende Datenmodell und die Aktionen integrieren, die Defender for Endpoint-APIs für orchestrierte Antworten verfügbar machen, z. B. Abfrage nach Gerätedaten, Auslösen der Geräteisolation, Blockieren/Zulassen, Auflösen von Warnungen und andere.

## <a name="scenario-3-indicators-matching"></a>Szenario 3: Abgleich von Indikatoren 
Der Kompromissindikator (IoCs) ist ein wesentliches Feature in jeder Endpunktschutzlösung. Diese Funktion ist in Defender for Endpoint verfügbar und bietet die Möglichkeit, eine Liste von Indikatoren für die Verhinderung, Erkennung und den Ausschluss von Entitäten zu erstellen. Sie können die zu ergreifende Aktion sowie die Dauer für die Anwendung der Aktion definieren.

Die obigen Szenarien dienen als Beispiele für die Erweiterbarkeit der Plattform. Sie sind nicht auf die Beispiele beschränkt, und wir empfehlen Ihnen, das offene Framework zu nutzen, um andere Szenarien zu entdecken und zu erkunden.

Führen Sie die Schritte unter [Microsoft Defender for Endpoint-Partner](get-started-partner-integration.md) werden aus, um Ihre Lösung in Defender for Endpoint zu integrieren.

## <a name="related-topic"></a>Verwandtes Thema
- [Übersicht über die Verwaltung und APIs](management-apis.md)
