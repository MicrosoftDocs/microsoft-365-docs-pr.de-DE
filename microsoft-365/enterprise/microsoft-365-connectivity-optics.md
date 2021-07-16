---
title: Microsoft 365 Connectivity-Optik
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: Dieser Artikel enthält Informationen zu Microsoft 365 Connectivity Optics.
ms.openlocfilehash: 952990a63d4ad064b2027c6f2364e8082342fa34
ms.sourcegitcommit: 2abc6bf9939b14a427647e88f319dbb70de49ca6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53455977"
---
# <a name="microsoft-365-connectivity-optics"></a>Microsoft 365 Connectivity-Optik

Dieses Dokument beschreibt einige der Konnektivitäts-Optiken, die Microsoft in der Regel von Kundengeräten erfasst, und beschreibt einige Möglichkeiten, wie Microsoft solche Daten verwendet, um die Dienstbereitstellung zu analysieren und zu optimieren und die bestmögliche Endbenutzererfahrung zu bewerten und sicherzustellen.

Konnektivitäts-Optiken werden in der Regel von Microsoft-Anwendungen erfasst, die auf Endbenutzergeräten installiert werden oder über Browser aufgerufen werden können. Im Gegensatz zur optionalen Datenerfassung in Microsoft 365 Diensten sind viele der hier beschriebenen Konnektivitäts-Optiken integraler Bestandteil, um sicherzustellen, dass Microsoft unserem Engagement für Verfügbarkeit und Leistung gegenüber Kunden entspricht. Diese Optik ermöglicht Es Microsoft, Probleme im Verbindungspfad zwischen Endbenutzern und Microsoft-Dienstendpunkten schnell zu erkennen und darauf zu reagieren. Einige dieser Optiken werden auch verwendet, um Features wie [netzwerkkonnektivität im Microsoft 365 Admin Center](office-365-network-mac-perf-overview.md)zu aktivieren.

## <a name="optics-collected-from-microsoft-365-applications"></a>Von Microsoft 365 Anwendungen gesammelte Optik

Optiken werden derzeit mit seltenen Samplings auf allen Geräten gesammelt. Allgemein gilt, dass die spezifische Gruppe von Optiken und Zielen (Dienstendpunkte), die in einer bestimmten Iteration gemessen werden sollen, von Microsoft basierend auf den Dienstanforderungen konfiguriert und für Samplingzwecke randomisiert wird.
In jedem Intervall der Optiksammlung kann eine oder mehrere der folgenden Messungen mithilfe des Endbenutzergeräts als Messquelle und eines Microsoft 365 Dienstendpunkts als Messziel erfasst werden:

| Messung | Beschreibung |
| --- | --- |
| Wartezeit | Zeitaufwand für das Abrufen einer kleinen Datei über HTTP |
| Durchsatz | Zeitaufwand für das Abrufen einer größeren Datei über HTTP, gemessen selten, um übermäßigen Bandbreitenverbrauch zu vermeiden |
| Roundtripzeit (RTT) | ICMP-Ping |
| Traceroute | ICMP-Ablaufverfolgungsroute |

Jede Maßeinheit ist in der Regel zusätzlichen Informationen zugeordnet, die die folgenden Elemente enthalten können:

| Element | Beschreibung |
| --- | --- |
| Mandanten-ID | Eindeutiger Bezeichner für den Azure Active Directory Mandanten des Kunden, der dem Endbenutzergerät zugeordnet ist. |
| Monitor-ID | Bezeichner für die Anwendung, die die Anforderung generiert (z. B. Outlook, OneDrive usw.), die von der Clientanwendung bereitgestellt wird, die die Messung durchführt. |
| Anforderungs-ID | Bezeichner für die Messanforderung, angegeben in der von Microsoft bereitgestellten Messkonfiguration. |
| Remote-IP | Maskierte Quell-IP, die der Anforderung vom Client-zu-Dienst-Endpunkt zugeordnet ist, bereitgestellt vom Server, der die Messanforderung erhalten hat und basierend auf der Clientquell-IP-Adresse berechnet wurde, die für Microsoft sichtbar ist. IP-Adressen werden in ein /24-Subnetz für IPv4-Adressen oder ein /48-Subnetz für IPv6-Adressen maskiert, um sicherzustellen, dass Microsoft keine einzelnen Geräte oder Benutzer identifizieren kann. |
| Front-End | Microsoft 365 Front-End-Bezeichner des Diensts, der vom Server bereitgestellt wird, der die Messanforderung erhalten hat. |
| Endpunkt | Microsoft 365 Standort des Dienstendpunkts, der vom Server bereitgestellt wird, der die Messanforderung erhalten hat. |
| Ausgestelltes Zertifikat von | Die Eigenschaft "Zertifikat ausgestellt von" des SSL-Zertifikats, das beim Herstellen einer Verbindung mit dem Dienstendpunkt angezeigt wird. Dies gibt die Zertifizierungsstelle an, die das Zertifikat für den Dienstendpunkt ausgestellt hat. |
| Zertifikatfingerabdruck | Die "Zertifikatfingerabdruck"-Eigenschaft des SSL-Zertifikats, das beim Herstellen einer Verbindung mit dem Dienstendpunkt angezeigt wird. Dabei handelt es sich um einen öffentlich zugänglichen eindeutigen Bezeichner des Zertifikats. |
| Breiten-/Längengrad | Der abstrahierte Breiten- und Längengrad des Endbenutzergeräts. Dies wird nur für Mandanten gesammelt, die Windows Standortdienst auf Endbenutzergeräten aktiviert haben und auch [die Sammlung dieser Informationen im Microsoft 365 Verwaltungsportal aktiviert](office-365-network-mac-perf-overview.md#1-enable-windows-location-services)haben. |

## <a name="measurement-process"></a>Messvorgang

Jedes Endbenutzergerät führt in der Regel eine Messung entweder auf einer geplanten Basis (für installierte Anwendungen) oder basierend auf der Aktion des Ladens von Browserseiten (für webbasierte Anwendungen) durch. Messaktivitäten werden als Hintergrundvorgänge ausgeführt und wirken sich nicht auf die Anwendungserfahrung für Benutzer aus. Da die Messtypen und Ziele, die für eine bestimmte Iteration dieses Prozesses verwendet werden, zufällig sind, werden Kunden möglicherweise Anforderungen an Microsoft-Dienstendpunkte in ihrer Region bemerken, die den typischen Anforderungen von Endbenutzergeräten für normale Anwendungskonnektivität ähneln. Darüber hinaus können Kunden Anforderungen an Microsoft-Dienstendpunkte bemerken, die sich weit außerhalb ihrer lokalen Region befinden. Diese Messungen werden häufig verwendet, um eine optimale Weiterleitung von Kundenanfragen an den besten Dienstendpunkt sicherzustellen, da Änderungen an der Kunden- und ISP-Infrastruktur microsoft möglicherweise erfordern, unsere Richtlinien für das Anforderungsrouting fortlaufend zu ändern. Weitere Informationen dazu, wie Microsoft Datenverkehr an den besten Dienstendpunkt weiterleiten und wie Sie die Konnektivität zu Microsoft 365 Diensten optimieren, finden Sie in der [Übersicht über Microsoft 365 Netzwerkkonnektivität.](microsoft-365-networking-overview.md)

## <a name="service-endpoints"></a>Dienstendpunkte

Die Microsoft-Dienstendpunkte, die als Ziele für diese Messungen verwendet werden, sind in den veröffentlichten [Office 365 URLs und IP-Adressbereichen](urls-and-ip-address-ranges.md)enthalten. Der Zugriff auf zusätzliche Dienstendpunkte ist für die Sammlung dieser Konnektivitäts-Optiken nicht erforderlich.
