---
title: Erstellen von Indikatoren für IPs und URLs/Domänen
ms.reviewer: ''
description: Erstellen Von Indikatoren für IP-Adressen und URLs/Domänen, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.
keywords: IP, URL, Domäne, verwalten, zulässig, blockiert, blockieren, sauber, bösartig, Dateihash, IP-Adresse, URLs, Domäne
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
ms.openlocfilehash: e7dc11fe709a6d04b6309706df90f0ebbc177e25
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841066"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="702bf-104">Erstellen von Indikatoren für IPs und URLs/Domänen</span><span class="sxs-lookup"><span data-stu-id="702bf-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="702bf-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="702bf-105">**Applies to:**</span></span>
- [<span data-ttu-id="702bf-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="702bf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="702bf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="702bf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> <span data-ttu-id="702bf-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="702bf-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="702bf-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="702bf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="702bf-110">Defender für Endpunkt kann blockieren, was Microsoft als bösartige IPs/URLs angibt, über Windows Defender SmartScreen für Microsoft-Browser und über Netzwerkschutz für Nicht-Microsoft-Browser oder Anrufe außerhalb eines Browsers.</span><span class="sxs-lookup"><span data-stu-id="702bf-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="702bf-111">Der dafür festgelegte Datensatz für die Bedrohungserkennung wurde von Microsoft verwaltet.</span><span class="sxs-lookup"><span data-stu-id="702bf-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="702bf-112">Durch das Erstellen von Indikatoren für IPs und URLs oder Domänen können Sie jetzt IPs, URLs oder Domänen basierend auf Ihrer eigenen Bedrohungserkennung zulassen oder blockieren.</span><span class="sxs-lookup"><span data-stu-id="702bf-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="702bf-113">Sie können dies über die Einstellungsseite oder nach Computergruppen tun, wenn Sie bestimmte Gruppen als mehr oder weniger gefährdet betrachten als andere.</span><span class="sxs-lookup"><span data-stu-id="702bf-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="702bf-114">Die CiDR-Notation (Classless Inter-Domain Routing) für IP-Adressen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="702bf-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="702bf-115">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="702bf-115">Before you begin</span></span>
<span data-ttu-id="702bf-116">Es ist wichtig, die folgenden Voraussetzungen zu verstehen, bevor Sie Indikatoren für IPS, URLs oder Domänen erstellen:</span><span class="sxs-lookup"><span data-stu-id="702bf-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="702bf-117">Die URL/IP-Zulassung und -Blockierung basiert darauf, dass der Netzwerkschutz der Defender für Endpunktkomponente im Blockierungsmodus aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="702bf-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="702bf-118">Weitere Informationen zu Netzwerkschutz und Konfigurationsanweisungen finden Sie unter Aktivieren des [Netzwerkschutzes.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="702bf-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="702bf-119">Die Antischadsoftware-Clientversion muss 4.18.1906.x oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="702bf-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="702bf-120">Unterstützt auf Computern mit Windows 10, Version 1709 oder höher.</span><span class="sxs-lookup"><span data-stu-id="702bf-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="702bf-121">Stellen Sie sicher, dass **benutzerdefinierte Netzwerkindikatoren** in **Microsoft Defender Security Center > Einstellungen > Erweiterten Features** aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="702bf-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="702bf-122">Weitere Informationen finden Sie unter ["Erweiterte Features".](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="702bf-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="702bf-123">Informationen zur Unterstützung von Indikatoren unter iOS finden Sie unter [Konfigurieren benutzerdefinierter Indikatoren.](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)</span><span class="sxs-lookup"><span data-stu-id="702bf-123">For support of indicators on iOS, see [Configure custom indicators](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="702bf-124">Der Indikatorliste können nur externe IPs hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="702bf-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="702bf-125">Indikatoren können nicht für interne IPs erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="702bf-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="702bf-126">Für Webschutzszenarien empfehlen wir die Verwendung der integrierten Funktionen in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="702bf-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="702bf-127">Microsoft Edge verwendet Network [Protection,](network-protection.md) um Netzwerkdatenverkehr zu überprüfen, und lässt Blöcke für TCP, HTTP und HTTPS (TLS) zu.</span><span class="sxs-lookup"><span data-stu-id="702bf-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="702bf-128">Wenn es widersprüchliche URL-Indikatorrichtlinien gibt, wird der längere Pfad angewendet.</span><span class="sxs-lookup"><span data-stu-id="702bf-128">If there are conflicting URL indicator policies, the longer path is applied.</span></span> <span data-ttu-id="702bf-129">Beispielsweise hat die URL-Indikatorrichtlinie `https:\\support.microsoft.com/en-us/office` Vorrang vor der URL-Indikatorrichtlinie. `https:\\support.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="702bf-129">For example, the URL indicator policy `https:\\support.microsoft.com/en-us/office` takes precedence over the URL indicator policy `https:\\support.microsoft.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="702bf-130">Für alle anderen Prozesse nutzen Webschutzszenarien Den Netzwerkschutz zur Überprüfung und Durchsetzung:</span><span class="sxs-lookup"><span data-stu-id="702bf-130">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> 
> - <span data-ttu-id="702bf-131">IP wird für alle drei Protokolle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="702bf-131">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="702bf-132">Es werden nur einzelne IP-Adressen unterstützt (keine CIDR-Blöcke oder IP-Bereiche)</span><span class="sxs-lookup"><span data-stu-id="702bf-132">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="702bf-133">Verschlüsselte URLs (vollständiger Pfad) können nur in Erstanbieterbrowsern (Internet Explorer, Edge) blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="702bf-133">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="702bf-134">Verschlüsselte URLS (nur FQDN) können außerhalb von Erstanbieterbrowsern (Internet Explorer, Edge) blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="702bf-134">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="702bf-135">Vollständige URL-Pfadblöcke können auf Domänenebene und alle unverschlüsselten URLs angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="702bf-135">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="702bf-136">Es kann bis zu 2 Stunden Wartezeit (in der Regel weniger) zwischen dem Zeitpunkt, zu dem die Aktion ausgeführt wird, und der URL und der IP-Adresse, die blockiert wird, geben.</span><span class="sxs-lookup"><span data-stu-id="702bf-136">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="702bf-137">Erstellen eines Indikators für IPs, URLs oder Domänen auf der Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="702bf-137">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="702bf-138">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Indikatoren** aus.</span><span class="sxs-lookup"><span data-stu-id="702bf-138">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="702bf-139">Wählen Sie die Registerkarte **"IP-Adressen" oder "URLs/Domänen"** aus.</span><span class="sxs-lookup"><span data-stu-id="702bf-139">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="702bf-140">Wählen Sie **"Element hinzufügen"** aus.</span><span class="sxs-lookup"><span data-stu-id="702bf-140">Select **Add item**.</span></span>

4. <span data-ttu-id="702bf-141">Geben Sie die folgenden Details an:</span><span class="sxs-lookup"><span data-stu-id="702bf-141">Specify the following details:</span></span>
   - <span data-ttu-id="702bf-142">Indikator – Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators.</span><span class="sxs-lookup"><span data-stu-id="702bf-142">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="702bf-143">Aktion – Geben Sie die auszuführende Aktion an, und geben Sie eine Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="702bf-143">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="702bf-144">Bereich: Definieren Sie den Bereich der Computergruppe.</span><span class="sxs-lookup"><span data-stu-id="702bf-144">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="702bf-145">Überprüfen Sie die Details auf der Registerkarte "Zusammenfassung", und klicken Sie dann auf **"Speichern".**</span><span class="sxs-lookup"><span data-stu-id="702bf-145">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="702bf-146">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="702bf-146">Related topics</span></span>
- [<span data-ttu-id="702bf-147">Indikatoren erstellen</span><span class="sxs-lookup"><span data-stu-id="702bf-147">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="702bf-148">Erstellen von Indikatoren für Dateien</span><span class="sxs-lookup"><span data-stu-id="702bf-148">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="702bf-149">Erstellen von Indikatoren basierend auf Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="702bf-149">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="702bf-150">Indikatoren verwalten</span><span class="sxs-lookup"><span data-stu-id="702bf-150">Manage indicators</span></span>](indicator-manage.md)
