---
title: 'Phase 1: Netzwerkinfrastruktur für Microsoft 365 Enterprise'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Die Schritte zur Bereitstellung der Netzwerkinfrastruktur für Microsoft 365 Enterprise.
ms.openlocfilehash: 9b8c23d543eca97147801d70e42de7105266c52d
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33399959"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="b2c02-103">Phase 1: Netzwerkinfrastruktur für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b2c02-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="b2c02-104">Microsoft 365 Enterprise enthält Office 365 und Microsoft Intune als Teil von Enterprise Management + Security (EMS).</span><span class="sxs-lookup"><span data-stu-id="b2c02-104">Microsoft 365 Enterprise includes Office 365 and Microsoft Intune as part of Enterprise Management + Security (EMS).</span></span> <span data-ttu-id="b2c02-105">Beide cloudbasierten Dienste basieren auf der Sicherheit, Leistung und Zuverlässigkeit der Verbindungen von Clientgeräten über das Internet oder dedizierte Leitungen.</span><span class="sxs-lookup"><span data-stu-id="b2c02-105">Both of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="b2c02-106">Um diese Dienste zu hosten und sie für Kunden auf der ganzen Welt verfügbar zu machen, hat Microsoft eine Netzwerkinfrastruktur entwickelt, deren Fokus auf Leistung und Integration liegt.</span><span class="sxs-lookup"><span data-stu-id="b2c02-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="b2c02-p102">In dieser Phase durchlaufen Sie die wichtigsten Aspekte zum Erstellen einer leistungsfähigen Verbindung zu den Clouddiensten von Microsoft 365 Enterprise. Eine Übersicht finden Sie unter [Office 365-Netzwerkkenntnisse](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span><span class="sxs-lookup"><span data-stu-id="b2c02-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="b2c02-109">Wenn Sie bereits eine Netzwerkinfrastruktur bereitgestellt haben, lesen Sie bitte den Abschnitt zu den [Beendigungskriterien](networking-exit-criteria.md) für diese Phase, um sicherzustellen, dass sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b2c02-109">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="b2c02-110">Planen und Bereitstellen Ihrer Microsoft 365 Enterprise-Netzwerkinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="b2c02-110">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="b2c02-111">Gehen Sie folgendermaßen zur Erstellung Ihrer Netzwerkinfrastruktur für die Anforderungen und Funktionen von Microsoft 365 Enterprise vor.</span><span class="sxs-lookup"><span data-stu-id="b2c02-111">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="b2c02-112">Vorbereiten Ihres Netzwerks für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b2c02-112">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="b2c02-113">Konfigurieren von lokalen Internetverbindungen für jedes Büro</span><span class="sxs-lookup"><span data-stu-id="b2c02-113">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="b2c02-114">Vermeiden von Spitzkehren für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="b2c02-114">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="b2c02-115">Konfigurieren von Datenverkehrumgehungen</span><span class="sxs-lookup"><span data-stu-id="b2c02-115">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="b2c02-116">Optimieren der Leistung des Clients und des Office 365-Diensts</span><span class="sxs-lookup"><span data-stu-id="b2c02-116">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="b2c02-117">Wenn Sie diese Schritte abgeschlossen haben, wechseln Sie zu [Beendigungskriterien](networking-exit-criteria.md) für diese Phase, um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b2c02-117">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="b2c02-118">Funktionsweise von Microsoft 365 Enterprise bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="b2c02-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b2c02-119">Erhalten Sie einen Einblick in die Arbeit bei Microsoft, und erfahren Sie, wie sich das Unternehmen auf die Office 365-Clouddienste vorbereitete und das Microsoft-Netzwerk optimierte, indem Sie den Artikel [Optimieren der Netzwerkleistung für Microsoft Office 365](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).</span><span class="sxs-lookup"><span data-stu-id="b2c02-119">Peek inside Microsoft and learn how the company prepared for and optimized the Microsoft network for the Office 365 cloud services with [Optimizing network performance for Microsoft Office 365](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="b2c02-120">Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird</span><span class="sxs-lookup"><span data-stu-id="b2c02-120">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b2c02-121">Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber multinationales, repräsentatives Unternehmen [ihr Netzwerk optimiert hat](contoso-networking.md) (für Microsoft 365-Clouddienste).</span><span class="sxs-lookup"><span data-stu-id="b2c02-121">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="b2c02-122">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b2c02-122">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="b2c02-123">Vorbereiten Ihres Netzwerks für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b2c02-123">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

