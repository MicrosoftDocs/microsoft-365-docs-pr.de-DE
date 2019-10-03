---
title: 'Phase 1: Beendigungskriterien für die Netzwerkinfrastruktur'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Stellen Sie sicher, dass Ihre Konfiguration die Kriterien von Microsoft 365 Enterprise für die Netzwerkinfrastruktur erfüllt.
ms.openlocfilehash: ad54284fdbd00fef486a13a957af6f06cb6a7450
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370152"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a><span data-ttu-id="27fd6-103">Phase 1: Beendigungskriterien für die Netzwerkinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="27fd6-103">Phase 1: Networking infrastructure exit criteria</span></span>

![Phase 1: Vernetzung](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="27fd6-105">Stellen Sie sicher, dass Ihre Netzwerkinfrastruktur die folgenden erforderlichen Kriterien erfüllt, und dass Sie die optionalen Kriterien berücksichtigt haben.</span><span class="sxs-lookup"><span data-stu-id="27fd6-105">Make sure your networking infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="27fd6-106">Erforderlich: Ihr Netzwerk ist bereit für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="27fd6-106">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="27fd6-107">Ihre Büros verfügen über ausreichende Internetbandbreite für Microsoft 365-Datenverkehr, einschließlich Office 365, Microsoft Intune sowie Windows 10 Enterprise (Installation und Updates).</span><span class="sxs-lookup"><span data-stu-id="27fd6-107">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, and Windows 10 Enterprise installation and updates</span></span>
- <span data-ttu-id="27fd6-108">Ihr Gesamtnetzwerk ist einer [Office 365-Referenzarchitektur](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2) zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="27fd6-108">Your overall network maps to an Office 365 reference architecture</span></span>
- <span data-ttu-id="27fd6-109">Ihre Netzwerkänderungen wurden eingeführt und getestet und erfüllen Ihre Anforderungen an die Datenverkehrslatenz.</span><span class="sxs-lookup"><span data-stu-id="27fd6-109">Your network changes have been piloted and tested and meet with your traffic latency requirements</span></span>

<span data-ttu-id="27fd6-110">Gegebenenfalls hilft Ihnen [Schritt 1](networking-provide-bandwidth-cloud-services.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="27fd6-110">If needed, [Step 1](networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="27fd6-111">Erforderlich: Ihre lokalen Büros verfügen über lokale Internet-Verbindungen und -Namensauflösung.</span><span class="sxs-lookup"><span data-stu-id="27fd6-111">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="27fd6-112">Sie haben jedes lokale Büro mit Internetzugang über einen lokalen ISP konfiguriert, dessen DNS-Server eine lokale öffentliche IP-Adresse verwenden, die ihren Standort im Internet identifiziert.</span><span class="sxs-lookup"><span data-stu-id="27fd6-112">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet. This ensures the best possible performance for users who access Office 365 and Intune.</span></span> <span data-ttu-id="27fd6-113">Dies gewährleistet die bestmögliche Leistung für Benutzer, die auf Microsoft 365-Clouddienste zugreifen.</span><span class="sxs-lookup"><span data-stu-id="27fd6-113">This ensures the best possible performance for users who access Microsoft 365 cloud services.</span></span>

<span data-ttu-id="27fd6-114">Wenn Sie nicht für jede Zweigstelle einen lokalen ISP verwenden, kann die Leistung beeinträchtigt werden, da der Netzwerkverkehr den Backbone einer Organisation passieren muss oder Datenanforderungen von entfernten Front-End-Servern bedient werden.</span><span class="sxs-lookup"><span data-stu-id="27fd6-114">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="27fd6-115">Testen</span><span class="sxs-lookup"><span data-stu-id="27fd6-115">How to test</span></span>
<span data-ttu-id="27fd6-p102">Verwenden Sie ein Tool oder eine Website von einem Gerät in diesem Büro, um die öffentliche IP-Adresse zu ermitteln, die der Proxy-Server verwendet. Verwenden Sie dazu beispielsweise die [Wie lautet meine IP-Adresse](https://www.whatismypublicip.com/)-Webseite. Diese von Ihrem ISP zugewiesene öffentliche IP-Adresse sollte geografisch lokal sein. Sie sollte nicht aus einem öffentlichen IP-Adressbereich für eine Zentrale oder von einem Anbieter von cloud-basierter Netzwerksicherheit stammen.</span><span class="sxs-lookup"><span data-stu-id="27fd6-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="27fd6-120">Gegebenenfalls hilft Ihnen [Schritt 2](networking-dns-resolution-same-location.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="27fd6-120">If needed, [Step 2](networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
## <a name="optional-unneccessary-network-hairpins-are-removed"></a><span data-ttu-id="27fd6-121">Optional: Nicht benötigte Spitzkehren für Netzwerke werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="27fd6-121">Optional: Unneeded network hairpins are removed</span></span>

<span data-ttu-id="27fd6-p103">Sie haben Ihre Spitzkehren für Netzwerke untersucht und ihre Auswirkung auf die Leistung für alle Ihre Büros bestimmt. Sie haben Spitzkehren für Netzwerke (wo möglich) entfernt oder mit Ihrem Netzwerk- oder Sicherheitsanbieter zusammengearbeitet, um optimales Microsoft 365-Peering für das Netzwerk zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="27fd6-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="27fd6-124">Gegebenenfalls hilft Ihnen [Schritt 3](networking-avoid-network-hairpins.md) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="27fd6-124">If needed, [Step 3](networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="27fd6-125">Optional: Sie haben Datenverkehrumgehungen auf Ihren Internetbrowsern und Edge-Geräten konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="27fd6-125">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="27fd6-126">Sie haben die neuesten PAC-Dateien auf Ihren lokalen Internetbrowsern bereitgestellt, damit der Datenverkehr zu Microsoft 365-DNS-Domänennamen Proxyserver umgeht.</span><span class="sxs-lookup"><span data-stu-id="27fd6-126">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="27fd6-127">Sie haben Ihre Netzwerkperimetergeräte, wie Firewalls, SSL Break and Inspect und Paketüberprüfungsgeräte, konfiguriert, um Datenverkehrumgehungen zu nutzen oder den Datenverkehr minimal zu den Kategorien „Optimieren“ und „Zulassen“ von Microsoft 365-Endpunkten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="27fd6-127">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="27fd6-128">Testen</span><span class="sxs-lookup"><span data-stu-id="27fd6-128">How to test</span></span>

<span data-ttu-id="27fd6-129">Verwenden Sie die Protokollierungstools auf Ihren Netzwerkgeräten, um sicherzustellen, dass der Datenverkehr zu Microsoft 365-Zielen nicht überprüft, entschlüsselt oder anderweitig behindert wird.</span><span class="sxs-lookup"><span data-stu-id="27fd6-129">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="27fd6-130">Gegebenenfalls hilft Ihnen [Schritt 4](networking-configure-proxies-firewalls.md) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="27fd6-130">If needed, [Step 4](networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="27fd6-131">Optional: Ihre Clients und Office 365-Anwendungen sind für eine optimale Performance konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="27fd6-131">Optional: Your clients and Office 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="27fd6-132">Sie haben die Einstellungen für das Transmission Control Protocol (TCP) auf Ihren Client-Geräten und für die Dienste Exchange Online, Skype for Business Online, SharePoint Online und Project Online optimiert.</span><span class="sxs-lookup"><span data-stu-id="27fd6-132">You have optimized the Transmssion Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="27fd6-133">Gegebenenfalls hilft Ihnen [Schritt 5](networking-optimize-tcp-performance.md) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="27fd6-133">If needed, [Step 5](networking-optimize-tcp-performance.md) can help you with this option.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="27fd6-134">Ergebnisse und nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="27fd6-134">Results and next steps</span></span>

<span data-ttu-id="27fd6-135">Ihre Intranetbenutzer sind nun bereit, Microsoft 365-Clouddienste über einen effizienten Netzwerkpfad zum und über das Internet zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="27fd6-135">Your intranet users are now ready to consume Microsoft 365 cloud services over an efficient networking path to and across the Internet.</span></span>

|||
|:-------|:-----|
|![Phase 2: Identität](./media/deploy-foundation-infrastructure/identity_icon-small.png)| <span data-ttu-id="27fd6-137">Wenn Sie den Phasen für die Ende-zu-Ende-Bereitstellung von Microsoft 365 Enterprise folgen, folgt als nächstes die Phase [Identität](identity-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="27fd6-137">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [identity](identity-infrastructure.md).</span></span> |
