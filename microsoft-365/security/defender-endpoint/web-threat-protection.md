---
title: Schützen Ihrer Organisation vor Webbedrohungen
description: Erfahren Sie mehr über den Webschutz in Microsoft Defender ATP und darüber, wie Sie Ihre Organisation schützen können.
keywords: Webschutz, Schutz vor Webbedrohungen, Browsen im Web, Sicherheit, Phishing, Schadsoftware, Exploit, Websites, Netzwerkschutz, Edge, Internet Explorer, Chrome, Firefox, Webbrowser
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: aeeea02ca1ef2d37623e9ab434b162237c2f4946
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499894"
---
# <a name="protect-your-organization-against-web-threats"></a>Schützen Ihrer Organisation vor Webbedrohungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Der Schutz von Webbedrohungen ist Teil [des Webschutzes](web-protection-overview.md) in Defender for Endpoint. Es verwendet [Netzwerkschutz,](network-protection.md) um Ihre Geräte vor Webbedrohungen zu schützen. Durch die Integration mit Microsoft Edge und beliebten Browsern von Drittanbietern wie Chrome und Firefox stoppt der Webbedrohungsschutz Webbedrohungen ohne Webproxy und kann Geräte schützen, während sie nicht oder lokal sind. Der Schutz von Webbedrohungen verhindert den Zugriff auf Phishingwebsites, Schadsoftwarevektoren, Exploitwebsites, nicht vertrauenswürdige websites oder Websites mit niedriger Reputation sowie Websites, die Sie in Ihrer benutzerdefinierten Indikatorliste [blockiert haben.](manage-indicators.md)

>[!Note]
>Es kann bis zu einer Stunde dauern, bis Geräte neue benutzerdefinierte Indikatoren erhalten.

## <a name="prerequisites"></a>Voraussetzungen
Der Webschutz verwendet Netzwerkschutz, um Sicherheit beim Browsen im Web in Microsoft Edge und Webbrowsern von Drittanbietern zu bieten.

So aktivieren Sie den Netzwerkschutz auf Ihren Geräten:
- Bearbeiten Sie die Sicherheitsbasis für Defender for Endpoint unter **Web & Network Protection,** um den Netzwerkschutz zu aktivieren, bevor Sie ihn bereitstellen oder erneut bereitstellen. [Informationen zum Überprüfen und Zuweisen der Sicherheitsbasis für Defender for Endpoint](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Aktivieren Sie den Netzwerkschutz mithilfe von Intune-Gerätekonfiguration, SCCM, Gruppenrichtlinie oder Ihrer MDM-Lösung. [Weitere Informationen zum Aktivieren des Netzwerkschutzes](enable-network-protection.md)  

>[!Note]
>Wenn Sie den Netzwerkschutz auf **Nur Überwachung festlegen,** ist die Blockierung nicht verfügbar. Außerdem können Sie Versuche erkennen und protokollieren, um nur auf schädliche und unerwünschte Websites auf Microsoft Edge zu zugreifen.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Internetschutz](web-protection-overview.md)
- [Internet-Bedrohungsschutz](web-threat-protection.md)
- [Überwachen der Websicherheit](web-protection-monitoring.md)
- [Reagieren auf Internetbedrohungen](web-protection-response.md)
- [Netzwerkschutz](network-protection.md)
