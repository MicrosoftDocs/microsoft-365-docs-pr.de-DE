---
title: Schützen Ihrer Organisation vor Webbedrohungen
description: Erfahren Sie mehr über den Webschutz in Microsoft Defender for Endpoint und darüber, wie Sie Ihre Organisation schützen können.
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
ms.openlocfilehash: 0c42c05e318390741b94b6d7d1b5394fca961714
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688945"
---
# <a name="protect-your-organization-against-web-threats"></a><span data-ttu-id="5d2f5-104">Schützen Ihrer Organisation vor Webbedrohungen</span><span class="sxs-lookup"><span data-stu-id="5d2f5-104">Protect your organization against web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5d2f5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5d2f5-105">**Applies to:**</span></span>
- [<span data-ttu-id="5d2f5-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5d2f5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5d2f5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d2f5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5d2f5-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="5d2f5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5d2f5-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="5d2f5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="5d2f5-110">Der Schutz von Webbedrohungen ist Teil [des Webschutzes](web-protection-overview.md) in Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5d2f5-110">Web threat protection is part of [Web protection](web-protection-overview.md) in Defender for Endpoint.</span></span> <span data-ttu-id="5d2f5-111">Es verwendet [Netzwerkschutz,](network-protection.md) um Ihre Geräte vor Webbedrohungen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="5d2f5-111">It uses [network protection](network-protection.md) to secure your devices against web threats.</span></span> <span data-ttu-id="5d2f5-112">Durch die Integration Microsoft Edge browsern und beliebten Browsern von Drittanbietern wie Chrome und Firefox stoppt der Webbedrohungsschutz Webbedrohungen ohne Webproxy und kann Geräte schützen, während sie sich nicht oder lokal befinden.</span><span class="sxs-lookup"><span data-stu-id="5d2f5-112">By integrating with Microsoft Edge and popular third-party browsers like Chrome and Firefox, web threat protection stops web threats without a web proxy and can protect devices while they are away or on premises.</span></span> <span data-ttu-id="5d2f5-113">Der Schutz von Webbedrohungen verhindert den Zugriff auf Phishingwebsites, Schadsoftwarevektoren, Exploitwebsites, nicht vertrauenswürdige websites oder Websites mit niedriger Reputation sowie Websites, die Sie in Ihrer benutzerdefinierten Indikatorliste [blockiert haben.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="5d2f5-113">Web threat protection stops access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked in your [custom indicator list](manage-indicators.md).</span></span>

>[!Note]
><span data-ttu-id="5d2f5-114">Es kann bis zu einer Stunde dauern, bis Geräte neue benutzerdefinierte Indikatoren erhalten.</span><span class="sxs-lookup"><span data-stu-id="5d2f5-114">It can take up to an hour for devices to receive new custom indicators.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5d2f5-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5d2f5-115">Prerequisites</span></span>
<span data-ttu-id="5d2f5-116">Der Webschutz verwendet Netzwerkschutz, um die Sicherheit des Webbrowsers Microsoft Edge Webbrowsern von Drittanbietern zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="5d2f5-116">Web protection uses network protection to provide web browsing security on Microsoft Edge and third-party web browsers.</span></span>

<span data-ttu-id="5d2f5-117">So aktivieren Sie den Netzwerkschutz auf Ihren Geräten:</span><span class="sxs-lookup"><span data-stu-id="5d2f5-117">To turn on network protection on your devices:</span></span>
- <span data-ttu-id="5d2f5-118">Bearbeiten Sie die Sicherheitsbasis für Defender for Endpoint unter **Web & Network Protection,** um den Netzwerkschutz zu aktivieren, bevor Sie ihn bereitstellen oder erneut bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5d2f5-118">Edit the Defender for Endpoint security baseline under **Web & Network Protection** to enable network protection before deploying or redeploying it.</span></span> [<span data-ttu-id="5d2f5-119">Informationen zum Überprüfen und Zuweisen der Sicherheitsbasis für Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5d2f5-119">Learn about reviewing and assigning the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- <span data-ttu-id="5d2f5-120">Aktivieren Sie den Netzwerkschutz mithilfe von Intune-Gerätekonfiguration, SCCM, Gruppenrichtlinie oder Ihrer MDM-Lösung.</span><span class="sxs-lookup"><span data-stu-id="5d2f5-120">Turn network protection on using Intune device configuration, SCCM, Group Policy, or your MDM solution.</span></span> [<span data-ttu-id="5d2f5-121">Weitere Informationen zum Aktivieren des Netzwerkschutzes</span><span class="sxs-lookup"><span data-stu-id="5d2f5-121">Read more about enabling network protection</span></span>](enable-network-protection.md)  

>[!Note]
><span data-ttu-id="5d2f5-122">Wenn Sie den Netzwerkschutz auf **Nur Überwachung festlegen,** ist die Blockierung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5d2f5-122">If you set network protection to **Audit only**, blocking will be unavailable.</span></span> <span data-ttu-id="5d2f5-123">Außerdem können Sie Versuche erkennen und protokollieren, um nur auf schädliche und unerwünschte Websites Microsoft Edge können.</span><span class="sxs-lookup"><span data-stu-id="5d2f5-123">Also, you will be able to detect and log attempts to access malicious and unwanted websites on Microsoft Edge only.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5d2f5-124">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="5d2f5-124">Related topics</span></span>

- [<span data-ttu-id="5d2f5-125">Übersicht über Internetschutz</span><span class="sxs-lookup"><span data-stu-id="5d2f5-125">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="5d2f5-126">Internet-Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="5d2f5-126">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="5d2f5-127">Überwachen der Websicherheit</span><span class="sxs-lookup"><span data-stu-id="5d2f5-127">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="5d2f5-128">Reagieren auf Internetbedrohungen</span><span class="sxs-lookup"><span data-stu-id="5d2f5-128">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="5d2f5-129">Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="5d2f5-129">Network protection</span></span>](network-protection.md)
