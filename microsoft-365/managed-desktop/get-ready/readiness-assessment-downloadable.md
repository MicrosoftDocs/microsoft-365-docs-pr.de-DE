---
title: Herunterladbare Bereitschaftsbewertungsüberprüfung
description: Überprüft Geräte- und Netzwerkeinstellungen, einschließlich erforderlicher Endpunkte
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581034"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="9cd88-104">Herunterladbare Bereitschaftsbewertungsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="9cd88-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="9cd88-105">Um mit Microsoft Managed Desktop gut arbeiten zu können, müssen Geräte bestimmte Anforderungen an Hardware und Einstellungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9cd88-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="9cd88-106">Außerdem muss jedes Gerät in der Lage sein, wichtige Endpunkte zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="9cd88-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="9cd88-107">Laden Sie dieses Tool herunter, und führen Sie es aus, um einen HTML-Bericht zu erhalten, Ergebnisse anzeigen und dann Maßnahmen zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="9cd88-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="9cd88-108">Sie müssen das Tool und die unterstützenden Dateien herunterladen und dann manuell auf jedem Gerät ausführen, das Sie bei Microsoft Managed Desktop registrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9cd88-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="9cd88-109">Für jede Prüfung berichtet das Tool eines von drei möglichen Ergebnissen:</span><span class="sxs-lookup"><span data-stu-id="9cd88-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="9cd88-110">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="9cd88-110">Result</span></span>  |<span data-ttu-id="9cd88-111">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="9cd88-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="9cd88-112">Bereit</span><span class="sxs-lookup"><span data-stu-id="9cd88-112">Ready</span></span>     | <span data-ttu-id="9cd88-113">Es ist keine Aktion erforderlich, bevor Sie die Registrierung abschließen.</span><span class="sxs-lookup"><span data-stu-id="9cd88-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="9cd88-114">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="9cd88-114">Advisory</span></span>    | <span data-ttu-id="9cd88-115">Führen Sie die Schritte im Tool aus, um eine optimale Erfahrung mit der Registrierung und für Benutzer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9cd88-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="9cd88-116">Sie *können* die Registrierung abschließen, aber Sie müssen diese Probleme beheben, bevor Sie Ihr erstes Gerät bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9cd88-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="9cd88-117">Nicht bereit</span><span class="sxs-lookup"><span data-stu-id="9cd88-117">Not ready</span></span> | <span data-ttu-id="9cd88-118">*Wenn Sie diese Probleme* nicht beheben, wird bei der Registrierung ein Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="9cd88-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="9cd88-119">Führen Sie die Schritte im Tool aus, um sie zu beheben.</span><span class="sxs-lookup"><span data-stu-id="9cd88-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="9cd88-120">Abrufen der Überprüfung</span><span class="sxs-lookup"><span data-stu-id="9cd88-120">Obtain the checker</span></span>

<span data-ttu-id="9cd88-121">Laden Sie die .zip aus https://aka.ms/mmddratoolv0 herunter.</span><span class="sxs-lookup"><span data-stu-id="9cd88-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="9cd88-122">Der Benutzer, der das Tool ausgeführt hat, muss über lokale Administratorrechte auf dem Gerät verfügen, auf dem es ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9cd88-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="9cd88-123">Führen Sie dann das Tool aus, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="9cd88-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="9cd88-124">Kopieren Sie die heruntergeladene .zip auf jedes Gerät, das Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="9cd88-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="9cd88-125">Extrahieren Sie alle Dateien im komprimierten Download.</span><span class="sxs-lookup"><span data-stu-id="9cd88-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="9cd88-126">Führen Sie **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** aus.</span><span class="sxs-lookup"><span data-stu-id="9cd88-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="9cd88-127">Wenn die Eingabeaufforderung für die Benutzerzugriffssteuerung angezeigt wird, wählen Sie **Ja aus.**</span><span class="sxs-lookup"><span data-stu-id="9cd88-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="9cd88-128">Das Tool wird im Standardbrowser ausgeführt und geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9cd88-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="9cd88-129">Sie können auch das .zip an einen freigegebenen Speicherort  herunterladen und extrahieren, aufMicrosoft.MMD.DeviceReadinessAssessmentTool.exeGeräte zugreifen und es dann lokal ausführen.</span><span class="sxs-lookup"><span data-stu-id="9cd88-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="9cd88-130">Prüfungen</span><span class="sxs-lookup"><span data-stu-id="9cd88-130">Checks</span></span>

<span data-ttu-id="9cd88-131">Das herunterladbare Tool überprüft die folgenden geräte- und netzwerkbezogenen Elemente:</span><span class="sxs-lookup"><span data-stu-id="9cd88-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="9cd88-132">Hardware</span><span class="sxs-lookup"><span data-stu-id="9cd88-132">Hardware</span></span>

<span data-ttu-id="9cd88-133">Geräte müssen bestimmte Hardwareanforderungen erfüllen, um mit Microsoft Managed Desktop arbeiten zu können.</span><span class="sxs-lookup"><span data-stu-id="9cd88-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="9cd88-134">Derzeit dürfen nur bestimmte [genehmigte](../service-description/device-list.md) Geräte registriert werden.</span><span class="sxs-lookup"><span data-stu-id="9cd88-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="9cd88-135">Wenn auf Ihrem Gerät eine der Prüfungen fehlschlägt, ist es nicht mit Microsoft Managed Desktop kompatibel.</span><span class="sxs-lookup"><span data-stu-id="9cd88-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="9cd88-136">Netzwerkendpunkte</span><span class="sxs-lookup"><span data-stu-id="9cd88-136">Network endpoints</span></span>

<span data-ttu-id="9cd88-137">Geräte können viele wichtige Endpunkte erreichen, [um](network.md) mit Microsoft Managed Desktop zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="9cd88-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="9cd88-138">Wenn das Tool ein **Nicht bereites** Ergebnis meldet, finden Sie im ausführlichen Bericht informationen, welche Endpunkte nicht erreichbar waren.</span><span class="sxs-lookup"><span data-stu-id="9cd88-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="9cd88-139">Passen Sie dann Ihre Firewall oder andere Netzwerkeinstellungen an, um sicherzustellen, dass diese Endpunkte erreicht werden können.</span><span class="sxs-lookup"><span data-stu-id="9cd88-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="9cd88-140">Weitere Einstellungen</span><span class="sxs-lookup"><span data-stu-id="9cd88-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="9cd88-141">Enterprise-WLAN-Profile</span><span class="sxs-lookup"><span data-stu-id="9cd88-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="9cd88-142">Ein **Empfehlungsergebnis** bedeutet, dass Sie einige WLAN-Profile verwenden, für die Zertifikate und Profile ordnungsgemäß funktionieren müssen.</span><span class="sxs-lookup"><span data-stu-id="9cd88-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="9cd88-143">Weitere Informationen finden Sie unter [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span><span class="sxs-lookup"><span data-stu-id="9cd88-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="9cd88-144">LAN-Profile</span><span class="sxs-lookup"><span data-stu-id="9cd88-144">LAN profiles</span></span>

<span data-ttu-id="9cd88-145">Ein **Empfehlungsergebnis** bedeutet, dass Sie ÜBER LANs verfügen, für die Zertifikate und Profile ordnungsgemäß funktionieren müssen.</span><span class="sxs-lookup"><span data-stu-id="9cd88-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="9cd88-146">Weitere Informationen finden Sie unter [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="9cd88-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="9cd88-147">VPN-Profile</span><span class="sxs-lookup"><span data-stu-id="9cd88-147">VPN profiles</span></span>

<span data-ttu-id="9cd88-148">Ein **Empfehlungsergebnis** bedeutet, dass Sie ein virtuelles privates Netzwerk (VPN) verwenden.</span><span class="sxs-lookup"><span data-stu-id="9cd88-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="9cd88-149">Erstellen Sie ein VPN-Profil, das in Microsoft Intune integrierte Zertifikate bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9cd88-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="9cd88-150">Weitere Informationen finden Sie unter [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="9cd88-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="9cd88-151">Zugeordnete Laufwerke</span><span class="sxs-lookup"><span data-stu-id="9cd88-151">Mapped drives</span></span>

<span data-ttu-id="9cd88-152">Ein **Empfehlungsergebnis** bedeutet, dass Sie über einige zugeordnete Laufwerke verfügen, die nicht empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="9cd88-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="9cd88-153">Weitere Informationen finden Sie unter [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span><span class="sxs-lookup"><span data-stu-id="9cd88-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="9cd88-154">Drucken von Warteschlangen</span><span class="sxs-lookup"><span data-stu-id="9cd88-154">Print queues</span></span>

<span data-ttu-id="9cd88-155">Ein **Empfehlungsergebnis** bedeutet, dass sie über einige ausstehende Druckwarteschlangen verfügen, die nicht empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="9cd88-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="9cd88-156">Eine Lösung ist die Verwendung des Clouddrucks.</span><span class="sxs-lookup"><span data-stu-id="9cd88-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="9cd88-157">Weitere Informationen finden Sie unter [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span><span class="sxs-lookup"><span data-stu-id="9cd88-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="9cd88-158">Proxys</span><span class="sxs-lookup"><span data-stu-id="9cd88-158">Proxies</span></span>

<span data-ttu-id="9cd88-159">Ein **Empfehlungsergebnis** bedeutet, dass Ein Proxyserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9cd88-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="9cd88-160">Weitere Informationen finden Sie unter [Netzwerkkonfiguration für Microsoft Managed Desktop](network.md).</span><span class="sxs-lookup"><span data-stu-id="9cd88-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

