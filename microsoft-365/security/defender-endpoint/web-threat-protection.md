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
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7754fa586b24fdedaa9691b45f5da4654c882a5b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185981"
---
# <a name="protect-your-organization-against-web-threats"></a><span data-ttu-id="2049d-104">Schützen Ihrer Organisation vor Webbedrohungen</span><span class="sxs-lookup"><span data-stu-id="2049d-104">Protect your organization against web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2049d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2049d-105">**Applies to:**</span></span>
- [<span data-ttu-id="2049d-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2049d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2049d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2049d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2049d-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="2049d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2049d-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2049d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="2049d-110">Der Schutz von Webbedrohungen ist Teil [des Webschutzes](web-protection-overview.md) in Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2049d-110">Web threat protection is part of [Web protection](web-protection-overview.md) in Defender for Endpoint.</span></span> <span data-ttu-id="2049d-111">Es verwendet [Netzwerkschutz,](network-protection.md) um Ihre Geräte vor Webbedrohungen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="2049d-111">It uses [network protection](network-protection.md) to secure your devices against web threats.</span></span> <span data-ttu-id="2049d-112">Durch die Integration mit Microsoft Edge und beliebten Browsern von Drittanbietern wie Chrome und Firefox stoppt der Webbedrohungsschutz Webbedrohungen ohne Webproxy und kann Geräte schützen, während sie nicht oder lokal sind.</span><span class="sxs-lookup"><span data-stu-id="2049d-112">By integrating with Microsoft Edge and popular third-party browsers like Chrome and Firefox, web threat protection stops web threats without a web proxy and can protect devices while they are away or on premises.</span></span> <span data-ttu-id="2049d-113">Der Schutz von Webbedrohungen verhindert den Zugriff auf Phishingwebsites, Schadsoftwarevektoren, Exploitwebsites, nicht vertrauenswürdige websites oder Websites mit niedriger Reputation sowie Websites, die Sie in Ihrer benutzerdefinierten Indikatorliste [blockiert haben.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="2049d-113">Web threat protection stops access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked in your [custom indicator list](manage-indicators.md).</span></span>

>[!Note]
><span data-ttu-id="2049d-114">Es kann bis zu einer Stunde dauern, bis Geräte neue Kundenindikatoren erhalten.</span><span class="sxs-lookup"><span data-stu-id="2049d-114">It can take up to an hour for devices to receive new customer indicators.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2049d-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2049d-115">Prerequisites</span></span>
<span data-ttu-id="2049d-116">Der Webschutz verwendet Netzwerkschutz, um Sicherheit beim Browsen im Web in Microsoft Edge und Webbrowsern von Drittanbietern zu bieten.</span><span class="sxs-lookup"><span data-stu-id="2049d-116">Web protection uses network protection to provide web browsing security on Microsoft Edge and third-party web browsers.</span></span>

<span data-ttu-id="2049d-117">So aktivieren Sie den Netzwerkschutz auf Ihren Geräten:</span><span class="sxs-lookup"><span data-stu-id="2049d-117">To turn on network protection on your devices:</span></span>
- <span data-ttu-id="2049d-118">Bearbeiten Sie die Sicherheitsbasis für Defender for Endpoint unter **Web & Network Protection,** um den Netzwerkschutz zu aktivieren, bevor Sie ihn bereitstellen oder erneut bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2049d-118">Edit the Defender for Endpoint security baseline under **Web & Network Protection** to enable network protection before deploying or redeploying it.</span></span> [<span data-ttu-id="2049d-119">Informationen zum Überprüfen und Zuweisen der Sicherheitsbasis für Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2049d-119">Learn about reviewing and assigning the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- <span data-ttu-id="2049d-120">Aktivieren Sie den Netzwerkschutz mithilfe von Intune-Gerätekonfiguration, SCCM, Gruppenrichtlinie oder Ihrer MDM-Lösung.</span><span class="sxs-lookup"><span data-stu-id="2049d-120">Turn network protection on using Intune device configuration, SCCM, Group Policy, or your MDM solution.</span></span> [<span data-ttu-id="2049d-121">Weitere Informationen zum Aktivieren des Netzwerkschutzes</span><span class="sxs-lookup"><span data-stu-id="2049d-121">Read more about enabling network protection</span></span>](enable-network-protection.md)  

>[!Note]
><span data-ttu-id="2049d-122">Wenn Sie den Netzwerkschutz auf **Nur Überwachung festlegen,** ist die Blockierung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2049d-122">If you set network protection to **Audit only**, blocking will be unavailable.</span></span> <span data-ttu-id="2049d-123">Außerdem können Sie Versuche erkennen und protokollieren, um nur auf schädliche und unerwünschte Websites auf Microsoft Edge zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="2049d-123">Also, you will be able to detect and log attempts to access malicious and unwanted websites on Microsoft Edge only.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2049d-124">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2049d-124">Related topics</span></span>

- [<span data-ttu-id="2049d-125">Übersicht über den Webschutz</span><span class="sxs-lookup"><span data-stu-id="2049d-125">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="2049d-126">Schutz vor Webbedrohungen</span><span class="sxs-lookup"><span data-stu-id="2049d-126">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="2049d-127">Überwachen der Websicherheit</span><span class="sxs-lookup"><span data-stu-id="2049d-127">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="2049d-128">Reagieren auf Webbedrohungen</span><span class="sxs-lookup"><span data-stu-id="2049d-128">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="2049d-129">Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="2049d-129">Network protection</span></span>](network-protection.md)
