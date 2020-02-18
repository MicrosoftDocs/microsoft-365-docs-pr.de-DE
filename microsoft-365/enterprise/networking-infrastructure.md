---
title: 'Phase 1: Netzwerkinfrastruktur für Microsoft 365 Enterprise'
f1.keywords:
- NOCSH
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
description: Die Schritte zur Bereitstellung der Netzwerkinfrastruktur für Microsoft 365 Enterprise.
ms.openlocfilehash: 9a805ffbdbdc19ef5943a0c0ba0ff8f010d3e19b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066582"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="9cb9f-103">Phase 1: Netzwerkinfrastruktur für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9cb9f-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![Phase 1: Vernetzung](../media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="9cb9f-105">Microsoft 365 Enterprise umfasst Office 365, Microsoft Intune und viele Identitäts- und Sicherheitsdienste von Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="9cb9f-105">Microsoft 365 Enterprise includes Office 365, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="9cb9f-106">Alle cloudbasierten Dienste basieren auf der Sicherheit, Leistung und Zuverlässigkeit der Verbindungen von Clientgeräten über das Internet oder dedizierte Leitungen.</span><span class="sxs-lookup"><span data-stu-id="9cb9f-106">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="9cb9f-107">Um diese Dienste zu hosten und sie für Kunden auf der ganzen Welt verfügbar zu machen, hat Microsoft eine Netzwerkinfrastruktur entwickelt, deren Fokus auf Leistung und Integration liegt.</span><span class="sxs-lookup"><span data-stu-id="9cb9f-107">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="9cb9f-p102">In dieser Phase durchlaufen Sie die wichtigsten Aspekte zum Erstellen einer leistungsfähigen Verbindung zu den Clouddiensten von Microsoft 365 Enterprise. Eine Übersicht finden Sie unter [Office 365-Netzwerkkenntnisse](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span><span class="sxs-lookup"><span data-stu-id="9cb9f-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="9cb9f-110">Wenn Sie bereits eine Netzwerkinfrastruktur bereitgestellt haben, lesen Sie bitte den Abschnitt zu den [Beendigungskriterien](networking-exit-criteria.md) für diese Phase, um sicherzustellen, dass sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9cb9f-110">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="9cb9f-111">Planen und Bereitstellen Ihrer Microsoft 365 Enterprise-Netzwerkinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="9cb9f-111">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="9cb9f-112">Gehen Sie folgendermaßen zur Erstellung Ihrer Netzwerkinfrastruktur für die Anforderungen und Funktionen von Microsoft 365 Enterprise vor.</span><span class="sxs-lookup"><span data-stu-id="9cb9f-112">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![Schritt 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="9cb9f-114">Vorbereiten Ihres Netzwerks für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9cb9f-114">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![Schritt 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="9cb9f-116">Konfigurieren von lokalen Internetverbindungen für jedes Büro</span><span class="sxs-lookup"><span data-stu-id="9cb9f-116">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![Schritt 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="9cb9f-118">Vermeiden von Spitzkehren für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="9cb9f-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![Schritt 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="9cb9f-120">Konfigurieren von Datenverkehrumgehungen</span><span class="sxs-lookup"><span data-stu-id="9cb9f-120">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![Schritt 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="9cb9f-122">Optimieren der Leistung des Clients und des Office 365-Diensts</span><span class="sxs-lookup"><span data-stu-id="9cb9f-122">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="9cb9f-123">Wenn Sie diese Schritte abgeschlossen haben, wechseln Sie zu [Beendigungskriterien](networking-exit-criteria.md) für diese Phase, um sicherzustellen, dass Sie die erforderlichen und optionalen Kriterien für Microsoft 365 Enterprise erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9cb9f-123">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="9cb9f-124">Funktionsweise von Microsoft 365 Enterprise bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="9cb9f-124">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="9cb9f-125">Werfen Sie einen Blick hinter die Kulissen von Microsoft, und erfahren Sie, wie das Unternehmen [das Microsoft-Netzwerk für Clouddienste optimiert hat](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span><span class="sxs-lookup"><span data-stu-id="9cb9f-125">Peek inside Microsoft and learn how the company [optimized the Microsoft network for cloud services](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="9cb9f-126">Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird</span><span class="sxs-lookup"><span data-stu-id="9cb9f-126">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="9cb9f-127">Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber repräsentatives multinationales Unternehmen, [seine Netzwerkgeräte und Internetverbindungen für Microsoft 365-Clouddienste optimiert hat](contoso-networking.md).</span><span class="sxs-lookup"><span data-stu-id="9cb9f-127">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Die Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="9cb9f-129">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="9cb9f-129">Next step</span></span>

|||
|:-------|:-----|
|![Schritt 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="9cb9f-131">Vorbereiten Ihres Netzwerks für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9cb9f-131">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

