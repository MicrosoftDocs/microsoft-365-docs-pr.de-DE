---
title: Erstellen von Indikatoren für IPs und URLs/Domänen
ms.reviewer: ''
description: Erstellen Sie Indikatoren für IPs und URLs/Domänen, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.
keywords: ip, url, domain, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: 3cfdc226ec5b476a37d15b67ca6158313e508adf
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067711"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="41d4d-104">Erstellen von Indikatoren für IPs und URLs/Domänen</span><span class="sxs-lookup"><span data-stu-id="41d4d-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="41d4d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="41d4d-105">**Applies to:**</span></span>
- [<span data-ttu-id="41d4d-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="41d4d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="41d4d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41d4d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="41d4d-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="41d4d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="41d4d-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="41d4d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="41d4d-110">Defender for Endpoint kann das blockieren, was Microsoft als bösartige IPs/URLs bezeichnet, über Windows Defender SmartScreen für Microsoft-Browser und über Netzwerkschutz für Nicht-Microsoft-Browser oder Anrufe außerhalb eines Browsers.</span><span class="sxs-lookup"><span data-stu-id="41d4d-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="41d4d-111">Der Datensatz für Die Bedrohungsintelligenz wurde von Microsoft verwaltet.</span><span class="sxs-lookup"><span data-stu-id="41d4d-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="41d4d-112">Durch das Erstellen von Indikatoren für IPs und URLs oder Domänen können Sie jetzt IPs, URLs oder Domänen basierend auf Ihrer eigenen Bedrohungsintelligenz zulassen oder blockieren.</span><span class="sxs-lookup"><span data-stu-id="41d4d-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="41d4d-113">Sie können dies über die Einstellungsseite oder durch Computergruppen tun, wenn Sie bestimmte Gruppen als mehr oder weniger gefährdet als andere personen sehen.</span><span class="sxs-lookup"><span data-stu-id="41d4d-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="41d4d-114">Klassenlose Inter-Domain (CIDR)-Notation für IP-Adressen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41d4d-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="41d4d-115">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="41d4d-115">Before you begin</span></span>
<span data-ttu-id="41d4d-116">Es ist wichtig, vor dem Erstellen von Indikatoren für IPS, URLs oder Domänen die folgenden Voraussetzungen zu kennen:</span><span class="sxs-lookup"><span data-stu-id="41d4d-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="41d4d-117">URL/IP allow and block basiert darauf, dass die Defender for Endpoint-Komponente Netzwerkschutz im Blockmodus aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="41d4d-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="41d4d-118">Weitere Informationen zu Netzwerkschutz und Konfigurationsanweisungen finden Sie unter [Enable network protection](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="41d4d-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="41d4d-119">Die Antischalware-Clientversion muss 4.18.1906.x oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="41d4d-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="41d4d-120">Unterstützt auf Computern unter Windows 10, Version 1709 oder höher.</span><span class="sxs-lookup"><span data-stu-id="41d4d-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="41d4d-121">Stellen Sie **sicher, dass** benutzerdefinierte Netzwerkindikatoren in **Microsoft Defender Security Center > Einstellungen > Erweiterten Features aktiviert sind.**</span><span class="sxs-lookup"><span data-stu-id="41d4d-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="41d4d-122">Weitere Informationen finden Sie unter [Erweiterte Features](advanced-features.md).</span><span class="sxs-lookup"><span data-stu-id="41d4d-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="41d4d-123">Informationen zur Unterstützung von Indikatoren unter iOS finden Sie unter [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span><span class="sxs-lookup"><span data-stu-id="41d4d-123">For support of indicators on iOS, see [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="41d4d-124">Der Indikatorliste können nur externe IPs hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="41d4d-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="41d4d-125">Indikatoren können nicht für interne IPs erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="41d4d-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="41d4d-126">Für Webschutzszenarien wird die Verwendung der integrierten Funktionen in Microsoft Edge empfohlen.</span><span class="sxs-lookup"><span data-stu-id="41d4d-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="41d4d-127">Microsoft Edge nutzt [Network Protection zum](network-protection.md) Überprüfen des Netzwerkdatenverkehrs und ermöglicht Blöcke für TCP, HTTP und HTTPS (TLS).</span><span class="sxs-lookup"><span data-stu-id="41d4d-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="41d4d-128">Für alle anderen Prozesse nutzen Webschutzszenarien Network Protection für die Überprüfung und Durchsetzung:</span><span class="sxs-lookup"><span data-stu-id="41d4d-128">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> <br>
> <span data-ttu-id="41d4d-129">HINWEIS:</span><span class="sxs-lookup"><span data-stu-id="41d4d-129">NOTE:</span></span>
> - <span data-ttu-id="41d4d-130">IP wird für alle drei Protokolle unterstützt</span><span class="sxs-lookup"><span data-stu-id="41d4d-130">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="41d4d-131">Es werden nur einzelne IP-Adressen unterstützt (keine CIDR-Blöcke oder IP-Bereiche)</span><span class="sxs-lookup"><span data-stu-id="41d4d-131">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="41d4d-132">Verschlüsselte URLs (vollständiger Pfad) können nur in Browsern erster Partei (Internet Explorer, Edge) blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="41d4d-132">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="41d4d-133">Verschlüsselte URLs (nur FQDN) können außerhalb von Browsern von Drittanbietern blockiert werden (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="41d4d-133">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="41d4d-134">Vollständige URL-Pfadblöcke können auf Domänenebene und alle unverschlüsselten URLs angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="41d4d-134">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="41d4d-135">Es kann bis zu 2 Stunden Wartezeit (in der Regel weniger) zwischen dem Zeitpunkt, zu dem die Aktion ergriffen wird, und der URL und der BLOCKIERTen IP liegen.</span><span class="sxs-lookup"><span data-stu-id="41d4d-135">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="41d4d-136">Erstellen eines Indikators für IPs, URLs oder Domänen auf der Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="41d4d-136">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="41d4d-137">Wählen Sie im Navigationsbereich **Einstellungsindikatoren**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="41d4d-137">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="41d4d-138">Wählen Sie die **Registerkarte IP-Adressen oder URLs/Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="41d4d-138">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="41d4d-139">Wählen **Sie Element hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="41d4d-139">Select **Add item**.</span></span>

4. <span data-ttu-id="41d4d-140">Geben Sie die folgenden Details an:</span><span class="sxs-lookup"><span data-stu-id="41d4d-140">Specify the following details:</span></span>
   - <span data-ttu-id="41d4d-141">Indikator – Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators.</span><span class="sxs-lookup"><span data-stu-id="41d4d-141">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="41d4d-142">Aktion – Geben Sie die zu ergreifende Aktion an, und geben Sie eine Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="41d4d-142">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="41d4d-143">Bereich : Definieren Sie den Bereich der Computergruppe.</span><span class="sxs-lookup"><span data-stu-id="41d4d-143">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="41d4d-144">Überprüfen Sie die Details auf der Registerkarte Zusammenfassung, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="41d4d-144">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="41d4d-145">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="41d4d-145">Related topics</span></span>
- [<span data-ttu-id="41d4d-146">Erstellen von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="41d4d-146">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="41d4d-147">Erstellen von Indikatoren für Dateien</span><span class="sxs-lookup"><span data-stu-id="41d4d-147">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="41d4d-148">Erstellen von Indikatoren basierend auf Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="41d4d-148">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="41d4d-149">Verwalten von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="41d4d-149">Manage indicators</span></span>](indicator-manage.md)
