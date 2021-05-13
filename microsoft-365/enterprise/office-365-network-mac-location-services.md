---
title: Microsoft 365 Netzwerkverbindungsspeicherortdienste
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
description: Microsoft 365 Netzwerkverbindungsspeicherortdienste
ms.openlocfilehash: ed78d7ba48cd9666ce1aae1af5478e3b7536e1e1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470448"
---
# <a name="microsoft-365-network-connectivity-location-services"></a>Microsoft 365 Netzwerkverbindungsspeicherortdienste

Das Microsoft 365 Admin Center zeigt jetzt **Netzwerkeinblicke** und Leistungsempfehlungen an, bei denen es sich um Liveleistungsmetriken handelt, die von Ihrem Microsoft 365 werden. Diese Metriken können nur von administrativen Benutzern in Ihrem Mandanten angezeigt werden. Die Konnektivität des Organisationsnetzwerks wird pro Bürostandort über einen Netzwerkverbindungsspeicherort in das Internet entworfen. Microsoft 365 client connectivity verwendet diese Route und dann über das Internet zu Microsoft-Dienst-Front-Door-Servern. Das Identifizieren von Bürostandorten ist entscheidend, um diese Netzwerkeinblicke anzeigen zu können.

## <a name="location-in-network-measurements"></a>Speicherort in Netzwerkmessungen

Der Administrator einer Organisation kann sich dafür entscheiden, dass der Standort in die von diesem Feature verwendeten Netzwerkmessungen einbezogen wird. Dies ermöglicht die automatische Ermittlung der Stadt, in der sich jedes Büro befindet. Standortinformationen sind nicht genau und werden auf 300 m verschleiert und nach Stadt kategorisiert. Zu dem Zeitpunkt, zu dem der Speicherort auf einem Windows  erfasst wird, zeigt das Gerät ein Symbol für die Verwendung des Standorts im Tooltablett an. Administratoren möchten Benutzer möglicherweise über die Darstellung dieses Symbols informieren. Bei dieser Verarbeitung wird der Standort als Standort des Organisationsbüros und nicht als Standort einer Person oder eines Geräts behandelt. Netzwerkeinblicke können an diesen erkannten Bürostandorten gezeigt werden. Wenn Sie eine höhere Genauigkeit in den Empfehlungen wünschen, können Sie bestimmte Bürostandortadressen eingeben. Die Netzwerkeinblicke werden stattdessen auf diese Standorte aggregiert. Office Standorte können nicht näher als 300 Meter aggregiert werden.

## <a name="location-in-the-microsoft-365-admin-center"></a>Speicherort im Microsoft 365 Admin Center

Im Microsoft 365 Admin Center werden Bing Kartensteuerelemente verwendet, um anzuzeigen, wo sich die Bürostandorte der Organisation befinden. Die Steuerelemente zeigen außerdem die Netzwerkperimetertopologie für einen ausgewählten Bürostandort an. Wenn ein Administrator bestimmte Adressdetails für Bürostandorte hinzufügt, wird Bing Karten auch zum Vorschlagen von Adressen verwendet, um die Dateneingabe zu vereinfachen.

## <a name="terms-of-use"></a>Nutzungsbedingungen

Alle inhalte, die über Bing Karten bereitgestellt werden, einschließlich Geocodes, können nur innerhalb des Produkts verwendet werden, über das der Inhalt bereitgestellt wird. Die Nutzung der Microsoft 365 Admin Center Location Services durch den Kunden, die von Bing Karten unterstützt wird, unterliegt den _Bing Karten End-User-Nutzungsbedingungen_ unter und der <https://go.microsoft.com/?linkid=9710837> [Microsoft-Datenschutzbestimmungen](https://go.microsoft.com/fwlink/?LinkID=248686).

Dieses Feature, das über Bing Karten bereitgestellt wird, wird auch von **TomTom unterstützt.** Weitere Informationen zu den Produkten und Diensten von TomTom finden Sie unter [https://www.tomtom.com/legal](https://www.tomtom.com/legal) .

## <a name="related-topics"></a>Verwandte Themen

[Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Einblicke in die Netzwerkleistung (Vorschau)](office-365-network-mac-perf-insights.md)

[Microsoft 365 Netzwerkbewertung (Vorschau)](office-365-network-mac-perf-score.md)

[Microsoft 365 Konnektivitätstest im Microsoft 365 Admin Center (Vorschau)](office-365-network-mac-perf-onboarding-tool.md)
