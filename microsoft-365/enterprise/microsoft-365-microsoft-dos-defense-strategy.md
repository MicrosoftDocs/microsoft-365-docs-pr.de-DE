---
title: Denial-of-Service-Verteidigungsstrategie von Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In diesem Artikel finden Sie eine Übersicht über die Microsoft-Verteidigungsstrategie für DOS-Angriffe (Denial-of-Service).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f28f7bcb9c6241404c8101bffe7268c5a1917ffa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690760"
---
# <a name="microsoft-365-denial-of-service-defense-strategy"></a>Denial-of-Service-Verteidigungsstrategie von Microsoft 365

Die Strategie von Microsoft zur Abwehr von netzwerkbasierten DOS-Angriffen (Denial of Service) ist aufgrund unserer Skalierung und Ihres globalen Fußabdrucks eindeutig. Diese Skalierung ermöglicht Microsoft, Strategien und Techniken zu nutzen, die nur wenige Organisationen, Anbieter oder Kundenorganisationen verwenden können. Der Eckpfeiler der DOS-Strategie ist unsere globale Präsenz. Microsoft engagiert sich mit Internet Anbietern, Peering-Anbietern (öffentlich und privat) und privaten Unternehmen in aller Welt. Dadurch erhält Microsoft eine erhebliche Internet Präsenz und ermöglicht es Microsoft, Angriffe über eine große Oberfläche hinweg zu absorbieren.

Aufgrund dieser einzigartigen Natur verwendet Microsoft Erkennungs-und Minderungs Prozesse, die sich von denen unterscheiden, die von großen Unternehmen verwendet werden. Die Strategie basiert auf einer Trennung von Erkennung und globaler verteilter Abschwächung über viele Netzwerkränder. Viele Unternehmen verwenden Lösungen von Drittanbietern, um Angriffe am Rande zu erkennen und zu mindern. Als die Edge-Kapazität für Microsoft wuchs, wurde deutlich, dass die Bedeutung eines Angriffs auf einzelne oder bestimmte Ränder gering war. Aufgrund dieser eindeutigen Konfiguration trennte Microsoft die Komponenten für Erkennung und Minderung. Microsoft stellt mehrstufige Erkennungssysteme bereit, um Angriffe näher an Ihren Sättigungs Punkten zu erkennen und gleichzeitig die globale Abschwächung am Rand beizubehalten. Diese Strategie gewährleistet, dass mehrere gleichzeitige Angriffe verarbeitet werden können.

Einer der effektivsten und kostengünstigsten Schutzmaßnahmen, die von Microsoft gegen DoS-Angriffe eingesetzt werden, ist das Reduzieren von Dienst Angriffs Oberflächen. Unerwünschter Datenverkehr wird am Netzwerkrand verworfen, anstatt die Daten Inline zu analysieren, zu verarbeiten und zu schrubben.

An der Schnittstelle mit dem öffentlichen Netzwerk verwendet Microsoft spezielle Sicherheitsgeräte für die Firewall, die Netzwerkadressübersetzung und IP-Filterfunktionen. Microsoft verwendet außerdem ein globales ECMP-Routing (Multi-Path, gleich Kosten). Das globale ECMP-Routing ist ein Netzwerk Framework, um sicherzustellen, dass mehrere globale Pfade vorhanden sind, um einen Dienst zu erreichen. Bei diesen mehreren Pfaden sind Angriffe auf Dienste auf die Region, aus der der Angriff stammt, limitiert. Andere Regionen sollten von diesem Angriff nicht betroffen sein, da Endbenutzer andere Pfade verwenden würden, um den Dienst in diesen Regionen zu erreichen. Microsoft hat auch interne DOS-Korrelations-und-Erkennungssysteme entwickelt, die Fluss Daten, Leistungs Metriken und andere Informationen verwenden. Dies ist ein hochwertiger clouddienst in Microsoft Azure, der Daten analysiert, die von verschiedenen Punkten in Microsoft-Netzwerken und-Diensten gesammelt wurden. Ein Aufgaben übergreifendes DOS-Vorfall Antwort Team identifiziert die Rollen und Verantwortlichkeiten in Teams, die Kriterien für Eskalationen und die Protokolle für die Einbindung verschiedener Teams und für die Vorfallbehandlung. Diese Lösungen bieten netzwerkbasierten Schutz vor DoS-Angriffen.

Schließlich werden Cloud-basierte Arbeitslasten mit optimierten Schwellenwerten basierend auf Ihren Protokoll-und Bandbreiten Nutzungsanforderungen konfiguriert, um diese Arbeitsauslastung eindeutig zu schützen.
