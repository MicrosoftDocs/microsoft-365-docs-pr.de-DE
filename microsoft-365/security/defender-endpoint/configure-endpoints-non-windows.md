---
title: Onboarding nicht Windows Geräte in den Microsoft Defender for Endpoint-Dienst
description: Konfigurieren Sie nicht Windows Geräte, damit sie Sensordaten an den Microsoft Defender for Endpoint-Dienst senden können.
keywords: onboard non-Windows devices, macos, linux, device management, configure Microsoft Defender for Endpoint devices
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1c10576b72793ab3833f2e9027e3814a449334ee
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933925"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="43c79-104">Onboarding von Nicht-Windows-Geräten</span><span class="sxs-lookup"><span data-stu-id="43c79-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="43c79-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="43c79-105">**Applies to:**</span></span>
- [<span data-ttu-id="43c79-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="43c79-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="43c79-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43c79-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="43c79-108">**Plattformen**</span><span class="sxs-lookup"><span data-stu-id="43c79-108">**Platforms**</span></span>
- <span data-ttu-id="43c79-109">macOS</span><span class="sxs-lookup"><span data-stu-id="43c79-109">macOS</span></span>
- <span data-ttu-id="43c79-110">Linux</span><span class="sxs-lookup"><span data-stu-id="43c79-110">Linux</span></span>

><span data-ttu-id="43c79-111">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="43c79-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="43c79-112">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="43c79-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="43c79-113">Defender for Endpoint bietet eine zentrale Sicherheitsbetriebserfahrung für Windows und nicht Windows Plattformen.</span><span class="sxs-lookup"><span data-stu-id="43c79-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="43c79-114">Sie können Warnungen von verschiedenen unterstützten Betriebssystemen in Microsoft Defender Security Center und das Netzwerk Ihrer Organisation besser schützen.</span><span class="sxs-lookup"><span data-stu-id="43c79-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> 

<span data-ttu-id="43c79-115">Sie müssen die genauen Linux-Distros- und macOS-Versionen kennen, die mit Defender for Endpoint kompatibel sind, damit die Integration funktioniert.</span><span class="sxs-lookup"><span data-stu-id="43c79-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="43c79-116">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="43c79-116">For more information, see:</span></span>
- [<span data-ttu-id="43c79-117">Systemanforderungen für Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="43c79-117">Microsoft Defender for Endpoint on Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="43c79-118">[Microsoft Defender for Endpoint für macOS-Systemanforderungen](microsoft-defender-endpoint-mac.md#system-requirements).</span><span class="sxs-lookup"><span data-stu-id="43c79-118">[Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="43c79-119">Onboarding nicht Windows Geräten</span><span class="sxs-lookup"><span data-stu-id="43c79-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="43c79-120">Sie müssen die folgenden Schritte zum Onboarding nicht Windows ausführen:</span><span class="sxs-lookup"><span data-stu-id="43c79-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="43c79-121">Wählen Sie Ihre bevorzugte Methode für das Onboarding aus:</span><span class="sxs-lookup"><span data-stu-id="43c79-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="43c79-122">Für macOS-Geräte können Sie das Onboarding über Microsoft Defender for Endpoint oder über eine Drittanbieterlösung auswählen.</span><span class="sxs-lookup"><span data-stu-id="43c79-122">For macOS devices, you can choose to onboard through Microsoft Defender for Endpoint or through a third-party solution.</span></span> <span data-ttu-id="43c79-123">Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint auf Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span><span class="sxs-lookup"><span data-stu-id="43c79-123">For more information, see [Microsoft Defender for Endpoint on Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span></span>

   - <span data-ttu-id="43c79-124">Für andere Nicht-Windows wählen Sie **Onboard non-Windows devices through third-party integration aus.**</span><span class="sxs-lookup"><span data-stu-id="43c79-124">For other non-Windows devices choose **Onboard non-Windows devices through third-party integration**.</span></span>   
    1. <span data-ttu-id="43c79-125">Wählen Sie im Navigationsbereich  >  **Interoperabilitätspartner aus.**</span><span class="sxs-lookup"><span data-stu-id="43c79-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="43c79-126">Stellen Sie sicher, dass die Drittanbieterlösung aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="43c79-126">Make sure the third-party solution is listed.</span></span>
    2. <span data-ttu-id="43c79-127">Wählen Sie **auf der Registerkarte** Partneranwendungen den Partner aus, der Ihre Nicht-Windows unterstützt.</span><span class="sxs-lookup"><span data-stu-id="43c79-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>
    3. <span data-ttu-id="43c79-128">Wählen **Sie Partnerseite öffnen aus,** um die Seite des Partners zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="43c79-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="43c79-129">Befolgen Sie die Anweisungen auf der Seite.</span><span class="sxs-lookup"><span data-stu-id="43c79-129">Follow the instructions provided on the page.</span></span>
    4. <span data-ttu-id="43c79-130">Nach dem Erstellen eines Kontos oder dem Abonnieren der Partnerlösung sollten Sie zu einer Phase kommen, in der ein globaler Mandantenadministrator in Ihrer Organisation aufgefordert wird, eine Berechtigungsanforderung von der Partneranwendung zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="43c79-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="43c79-131">Lesen Sie die Berechtigungsanforderung sorgfältig durch, um sicherzustellen, dass sie mit dem von Ihnen benötigten Dienst abgestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="43c79-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="43c79-132">Führen Sie einen Erkennungstest aus, indem Sie die Anweisungen der Drittanbieterlösung befolgen.</span><span class="sxs-lookup"><span data-stu-id="43c79-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="43c79-133">Offboard-Windows Geräte</span><span class="sxs-lookup"><span data-stu-id="43c79-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="43c79-134">Befolgen Sie die Dokumentation des Drittanbieters, um die Drittanbieterlösung von Microsoft Defender for Endpoint zu trennen.</span><span class="sxs-lookup"><span data-stu-id="43c79-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="43c79-135">Entfernen Von Berechtigungen für die Drittanbieterlösung in Ihrem Azure AD-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="43c79-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="43c79-136">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="43c79-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="43c79-137">Wählen **Azure Active Directory > Enterprise Anwendungen aus.**</span><span class="sxs-lookup"><span data-stu-id="43c79-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="43c79-138">Wählen Sie die Anwendung aus, die Sie offboarden möchten.</span><span class="sxs-lookup"><span data-stu-id="43c79-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="43c79-139">Wählen Sie die **Schaltfläche Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="43c79-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="43c79-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="43c79-140">Related topics</span></span>
- [<span data-ttu-id="43c79-141">Onboarding von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="43c79-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="43c79-142">Onboarding von Servern</span><span class="sxs-lookup"><span data-stu-id="43c79-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="43c79-143">Konfigurieren der Einstellungen für Endpunktproxy und Internetkonnektivität für Ihren Azure ATP-Sensor</span><span class="sxs-lookup"><span data-stu-id="43c79-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="43c79-144">Beheben von Problemen beim Onboarding von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="43c79-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
