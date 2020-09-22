---
title: Microsoft 365 Network Connectivity Location Services (Vorschau)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Connectivity Location Services (Vorschau)
ms.openlocfilehash: f2ab872f67eca70ab2791d3ad6fe1396b009cc18
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200781"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a>Microsoft 365 Network Connectivity Location Services (Vorschau)

Das Microsoft 365 Admin Center zeigt nun **Netzwerk Einblicke und Leistungsempfehlungen**an, bei denen es sich um Live-Leistungs Metriken handelt, die von Ihrem Microsoft 365-Mandanten gesammelt und nur für administrative Benutzer in Ihrem Mandanten verfügbar sind. Die Netzwerkkonnektivität des Unternehmens wird pro Bürostandort über einen Netzwerk Ausstieg-Standort im Internet entwickelt. Die Microsoft 365-Clientkonnektivität verwendet diese Route und dann über das Internet an Microsoft-Dienst-Front-Door-Server. Das Identifizieren von Office-Standorten ist der Schlüssel, um diese Netzwerk Einblicke anzeigen zu können.

## <a name="location-in-network-measurements"></a>Speicherort in Netzwerk Messungen

Der Administrator einer Organisation kann sich dafür entscheiden, dass der Standort in die Netzwerk Messungen einbezogen wird, die von dieser Funktion verwendet werden. Dadurch wird die automatische Erkennung der Stadt ermöglicht, in der sich die einzelnen Büros befinden. Standortinformationen sind nicht präzise und werden bis zu 300m verborgen und nach Ort kategorisiert. Zu dem Zeitpunkt, an dem ein Standort auf einem Windows-Gerät erfasst wird, wird ein **Standort** Symbol in der Taskleiste angezeigt, und Administratoren möchten Benutzer möglicherweise darüber informieren. Bei dieser Verarbeitung wird der Standort als Organisationsbüro Standort und nicht als Standort einer Person oder eines Geräts behandelt. Netzwerk Einblicke können an diesen entdeckten Bürostandort Städten gezeigt werden. Wenn eine größere Genauigkeit von Empfehlungen gewünscht wird, kann ein Administrator bestimmte Office-Standortadressen eingeben, und die Einblicke in das Netzwerk werden auf diese statt aggregiert. Office-Standorte können nicht enger als 300 Meter aggregiert werden.

## <a name="location-in-the-microsoft-365-admin-center"></a>Speicherort im Microsoft 365 Admin Center

Im Microsoft 365 Admin Center werden Bing Map-Steuerelemente verwendet, um anzuzeigen, wo sich die Standort Organisation befinden, und um die Netzwerkumkreis Topologie für einen ausgewählten Office-Standort anzuzeigen. Wenn ein Administrator bestimmte Adressdetails für Office-Standorte hinzufügt, wird Bing Maps auch verwendet, um Adressen anzudeuten, um die Dateneingabe zu vereinfachen.

## <a name="terms-of-use"></a>Nutzungsbedingungen

Alle Inhalte, die über Bing Maps zur Verfügung gestellt werden, einschließlich Geocodes, können nur innerhalb des Produkts verwendet werden, über das der Inhalt bereitgestellt wird. Die Verwendung des Microsoft 365 Admin Center Location Services-Features, betrieben von Bing Maps, richtet sich nach den _Nutzungsbedingungen von Bing Maps Endbenutzer_ , <https://go.microsoft.com/?linkid=9710837> die unter und der _Microsoft-Datenschutzerklärung_ verfügbar sind unter <https://go.microsoft.com/fwlink/?LinkID=248686.>

Dieses Feature, das über Bing Maps bereitgestellt wird, wird auch von **here Technologies**unterstützt. Wie Bing Maps die von hier bereitgestellten Standortdienste nutzt Technologien unterliegen den _hier angebotenen Technologien-Dienstbedingungen_ <https://legal.here.com/en-gb/terms> .

## <a name="related-topics"></a>Verwandte Themen

[Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Performance Insights (Vorschau)](office-365-network-mac-perf-insights.md)

[Microsoft 365 Netzwerkbewertung (Vorschau)](office-365-network-mac-perf-score.md)

[Microsoft 365 Connectivity Test im M365 Admin Center (Vorschau)](office-365-network-mac-perf-onboarding-tool.md)
