---
title: Herunterladbare Überprüfung der Bereitschaftsbewertung
description: Überprüft Geräte- und Netzwerkeinstellungen, einschließlich der erforderlichen Endpunkte
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921971"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="c598b-104">Herunterladbare Überprüfung der Bereitschaftsbewertung</span><span class="sxs-lookup"><span data-stu-id="c598b-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="c598b-105">Für eine gute Zusammenarbeit mit Microsoft Managed Desktop müssen Geräte bestimmte Hardware- und Einstellungsanforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c598b-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="c598b-106">Außerdem muss jedes Gerät in der Lage sein, wichtige Endpunkte zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="c598b-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="c598b-107">Laden Sie dieses Tool herunter, und führen Sie es aus, um einen HTML-Bericht zu erhalten, Ergebnisse anzeigen und dann Maßnahmen zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="c598b-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="c598b-108">Sie müssen das Tool und die unterstützenden Dateien herunterladen und es dann manuell auf jedem Gerät ausführen, das Sie bei Microsoft Managed Desktop registrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c598b-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="c598b-109">Für jede Prüfung gibt das Tool eines von drei möglichen Ergebnissen aus:</span><span class="sxs-lookup"><span data-stu-id="c598b-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="c598b-110">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="c598b-110">Result</span></span>  |<span data-ttu-id="c598b-111">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="c598b-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="c598b-112">Bereit</span><span class="sxs-lookup"><span data-stu-id="c598b-112">Ready</span></span>     | <span data-ttu-id="c598b-113">Es ist keine Aktion erforderlich, bevor Sie die Registrierung abschließen.</span><span class="sxs-lookup"><span data-stu-id="c598b-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="c598b-114">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="c598b-114">Advisory</span></span>    | <span data-ttu-id="c598b-115">Führen Sie die Schritte im Tool aus, um die beste Erfahrung mit der Registrierung und für Benutzer zu bieten.</span><span class="sxs-lookup"><span data-stu-id="c598b-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="c598b-116">Sie *können* die Registrierung abschließen, aber Sie müssen diese Probleme beheben, bevor Sie Ihr erstes Gerät bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c598b-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="c598b-117">Nicht bereit</span><span class="sxs-lookup"><span data-stu-id="c598b-117">Not ready</span></span> | <span data-ttu-id="c598b-118">*Die Registrierung wird fehlschlagen,* wenn Sie diese Probleme nicht beheben.</span><span class="sxs-lookup"><span data-stu-id="c598b-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="c598b-119">Führen Sie die Schritte im Tool aus, um sie zu beheben.</span><span class="sxs-lookup"><span data-stu-id="c598b-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="c598b-120">Abrufen der Prüfung</span><span class="sxs-lookup"><span data-stu-id="c598b-120">Obtain the checker</span></span>

<span data-ttu-id="c598b-121">Laden Sie die ZIP-Datei von https://aka.ms/mmddratoolv0 herunter.</span><span class="sxs-lookup"><span data-stu-id="c598b-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="c598b-122">Der Benutzer, der das Tool ausgeführt, muss über lokale Administratorrechte auf dem Gerät verfügen, auf dem es ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c598b-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="c598b-123">Führen Sie dann das Tool aus, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c598b-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="c598b-124">Kopieren Sie die heruntergeladene ZIP-Datei auf jedes Gerät, das Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="c598b-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="c598b-125">Extrahieren Sie alle Dateien im komprimierten Download.</span><span class="sxs-lookup"><span data-stu-id="c598b-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="c598b-126">Führen Sie **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** aus.</span><span class="sxs-lookup"><span data-stu-id="c598b-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="c598b-127">Wenn die Eingabeaufforderung für die Benutzerzugriffssteuerung angezeigt wird, wählen Sie **"Ja" aus.**</span><span class="sxs-lookup"><span data-stu-id="c598b-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="c598b-128">Das Tool wird ausgeführt und öffnet einen Bericht im Standardbrowser.</span><span class="sxs-lookup"><span data-stu-id="c598b-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="c598b-129">Sie können das ZIP-Archiv auch herunterladen und  an einen freigegebenen Speicherort extrahieren, aufMicrosoft.MMD.DeviceReadinessAssessmentTool.exeGeräte zugreifen und es dann lokal ausführen.</span><span class="sxs-lookup"><span data-stu-id="c598b-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="c598b-130">Prüfungen</span><span class="sxs-lookup"><span data-stu-id="c598b-130">Checks</span></span>

<span data-ttu-id="c598b-131">Das herunterladbare Tool überprüft diese geräte- und netzwerkbezogenen Elemente:</span><span class="sxs-lookup"><span data-stu-id="c598b-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="c598b-132">Hardware</span><span class="sxs-lookup"><span data-stu-id="c598b-132">Hardware</span></span>

<span data-ttu-id="c598b-133">Geräte müssen bestimmte Hardwareanforderungen erfüllen, um mit Microsoft Managed Desktop arbeiten zu können.</span><span class="sxs-lookup"><span data-stu-id="c598b-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="c598b-134">Derzeit dürfen nur bestimmte [genehmigte](../service-description/device-list.md) Geräte registriert werden.</span><span class="sxs-lookup"><span data-stu-id="c598b-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="c598b-135">Wenn auf Ihrem Gerät eine der Überprüfungen fehlschlägt, ist es nicht mit Microsoft Managed Desktop kompatibel.</span><span class="sxs-lookup"><span data-stu-id="c598b-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="c598b-136">Netzwerkendpunkte</span><span class="sxs-lookup"><span data-stu-id="c598b-136">Network endpoints</span></span>

<span data-ttu-id="c598b-137">Geräte können viele wichtige Endpunkte [erreichen,](network.md) um mit Microsoft Managed Desktop zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="c598b-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="c598b-138">Wenn das Tool ein Ergebnis meldet, das **nicht** bereit ist, sehen Sie sich den detaillierten Bericht an, um herauszufinden, welche Endpunkte nicht erreichbar waren.</span><span class="sxs-lookup"><span data-stu-id="c598b-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="c598b-139">Passen Sie dann Ihre Firewall oder andere Netzwerkeinstellungen an, um sicherzustellen, dass diese Endpunkte erreicht werden können.</span><span class="sxs-lookup"><span data-stu-id="c598b-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="c598b-140">Weitere Einstellungen</span><span class="sxs-lookup"><span data-stu-id="c598b-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="c598b-141">Unternehmens-WLAN-Profile</span><span class="sxs-lookup"><span data-stu-id="c598b-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="c598b-142">Ein **Empfehlungsergebnis** bedeutet, dass Sie einige WLAN-Profile verwenden, die Zertifikate und Profile benötigen, damit sie ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="c598b-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="c598b-143">Weitere Informationen finden Sie unter [Bereitstellen von Zertifikaten und WLAN/VPN-Profil.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)</span><span class="sxs-lookup"><span data-stu-id="c598b-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="c598b-144">LAN-Profile</span><span class="sxs-lookup"><span data-stu-id="c598b-144">LAN profiles</span></span>

<span data-ttu-id="c598b-145">Ein **Empfehlungsergebnis** bedeutet, dass Sie ÜBER LANs verfügen, die Zertifikate und Profile benötigen, um ordnungsgemäß zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="c598b-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="c598b-146">Weitere Informationen finden Sie unter [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="c598b-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="c598b-147">VPN-Profile</span><span class="sxs-lookup"><span data-stu-id="c598b-147">VPN profiles</span></span>

<span data-ttu-id="c598b-148">Ein **Empfehlungsergebnis** bedeutet, dass Sie ein virtuelles privates Netzwerk (VPN) verwenden.</span><span class="sxs-lookup"><span data-stu-id="c598b-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="c598b-149">Erstellen Sie ein VPN-Profil, das in Microsoft Intune integrierte Zertifikate bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c598b-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="c598b-150">Weitere Informationen finden Sie unter [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="c598b-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="c598b-151">Zugeordnete Laufwerke</span><span class="sxs-lookup"><span data-stu-id="c598b-151">Mapped drives</span></span>

<span data-ttu-id="c598b-152">Ein **Empfehlungsergebnis** bedeutet, dass Sie über einige zugeordnete Laufwerke verfügen, die nicht empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="c598b-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="c598b-153">Weitere Informationen finden Sie unter [Vorbereiten zugeordneter Laufwerke für Microsoft Managed Desktop](mapped-drives.md).</span><span class="sxs-lookup"><span data-stu-id="c598b-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="c598b-154">Druckwarteschlangen</span><span class="sxs-lookup"><span data-stu-id="c598b-154">Print queues</span></span>

<span data-ttu-id="c598b-155">Ein **Empfehlungsergebnis** bedeutet, dass sie über einige ausstehende Druckwarteschlangen verfügen, die nicht empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="c598b-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="c598b-156">Eine Lösung besteht in der Verwendung des Clouddrucks.</span><span class="sxs-lookup"><span data-stu-id="c598b-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="c598b-157">Weitere Informationen finden Sie unter [Vorbereiten der Druckressourcen für Microsoft Managed Desktop](printing.md).</span><span class="sxs-lookup"><span data-stu-id="c598b-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="c598b-158">Proxys</span><span class="sxs-lookup"><span data-stu-id="c598b-158">Proxies</span></span>

<span data-ttu-id="c598b-159">Ein **Empfehlungsergebnis** bedeutet, dass Sie einen Proxyserver verwenden.</span><span class="sxs-lookup"><span data-stu-id="c598b-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="c598b-160">Weitere Informationen finden Sie unter [Netzwerkkonfiguration für Microsoft Managed Desktop](network.md).</span><span class="sxs-lookup"><span data-stu-id="c598b-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

