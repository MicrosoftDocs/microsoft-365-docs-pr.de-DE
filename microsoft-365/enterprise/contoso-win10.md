---
title: Bereitstellung von Windows 10 Enterprise für Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen dazu, wie Contoso Microsoft Endpoint Configuration Manager zur Bereitstellung von direkten Upgrades für Windows 10 Enterprise verwendete.
ms.openlocfilehash: 0543f24665048d0679bc1b099fdd0a2d431c1e54
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754247"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="4fac9-103">Bereitstellung von Windows 10 Enterprise für Contoso</span><span class="sxs-lookup"><span data-stu-id="4fac9-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="4fac9-p101">Vor dem breiten Rollout von Microsoft 365 for Enterprise hatte Contoso Windows-kompatible PCs und Geräte mit einer Kombination aus Windows 7 (10%), Windows 8.1 (65%) und Windows 10 (25%). Contoso wollte ein Upgrade seiner PCs für Windows 10 Enterprise nutzen Sie die erweiterte Sicherheit und senken Sie den IT-Overhead von automatisierten Bereitstellungen von Updates.</span><span class="sxs-lookup"><span data-stu-id="4fac9-p101">Prior to the wide rollout of Microsoft 365 for enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="4fac9-106">Nach der Bewertung der Infrastruktur und der Geschäftsanforderungen identifizierte Contoso die folgenden Hauptanforderungen für die Bereitstellung:</span><span class="sxs-lookup"><span data-stu-id="4fac9-106">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="4fac9-107">Windows 10 Enterprise soll auf so vielen Computern und Geräten wie möglich ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4fac9-107">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="4fac9-108">Die Einführung von direkten Upgrades nutzt die vorhandene Configuration Manager-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="4fac9-108">Rollout of the in-place upgrades leverages existing Configuration Manager infrastructure</span></span>
- <span data-ttu-id="4fac9-109">Die Steuerung, welche Versionen von Windows 10 Enterprise bereitgestellt und aktualisiert werden sollen, erfolgt über Ringe.</span><span class="sxs-lookup"><span data-stu-id="4fac9-109">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="4fac9-110">Computer und Geräte sollen mit minimalen IT-Verwaltungskosten und minimalen Auswirkungen auf die Endbenutzer auf dem aktuellen Stand gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="4fac9-110">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="4fac9-111">„Auf dem neuesten Stand“ wird definiert als die unterstützte Version von Windows 10 Enterprise, die den Geschäftsanforderungen von Contoso entspricht; dabei muss es nicht unbedingt darum gehen, dass auf allen Windows-kompatiblen Computern die neueste Version von Windows 10 Enterprise ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4fac9-111">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="4fac9-112">Bereitstellungstools</span><span class="sxs-lookup"><span data-stu-id="4fac9-112">Deployment tools</span></span>

<span data-ttu-id="4fac9-113">Vor und während direkter Upgrades von Windows 10 Enterprise verwendete Contoso die folgenden Lösungen von Windows Analytics:</span><span class="sxs-lookup"><span data-stu-id="4fac9-113">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="4fac9-114">Upgradebereitschaft</span><span class="sxs-lookup"><span data-stu-id="4fac9-114">Upgrade Readiness</span></span>  

  <span data-ttu-id="4fac9-115">Es werden System-, Anwedungs- und Treiberdaten für die Analyse erfasst und dann Kompatibilitätsprobleme identifiziert, durch die ein Upgrade und vorgeschlagene Korrekturen blockiert werden können, die Microsoft bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="4fac9-115">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="4fac9-116">Update-Compliance</span><span class="sxs-lookup"><span data-stu-id="4fac9-116">Update Compliance</span></span>  

  <span data-ttu-id="4fac9-117">Zeigt den Status Ihrer Geräte in Bezug auf die Windows-Updates an, so dass Sie sicherstellen können, dass diese gegebenenfalls auf den aktuellsten Updates sind.</span><span class="sxs-lookup"><span data-stu-id="4fac9-117">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="4fac9-118">Geräteintegrität</span><span class="sxs-lookup"><span data-stu-id="4fac9-118">Device Health</span></span>  

  <span data-ttu-id="4fac9-119">Identifiziert Geräte, die häufig abstürzen und daher möglicherweise neu aufgebaut oder ersetzt werden müssen, und Gerätetreiber, die Geräteabstürze verursachen, mit Vorschlägen für alternative Versionen dieser Treiber, welche die Anzahl der Abstürze reduzieren könnten.</span><span class="sxs-lookup"><span data-stu-id="4fac9-119">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="4fac9-120">Bietet eine Benachrichtigung über Fehlkonfigurationen des Windows Information Protection, die Eingabeaufforderungen an Endbenutzer senden.</span><span class="sxs-lookup"><span data-stu-id="4fac9-120">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="4fac9-p103">Contoso verfügt über eine vorhandene Infrastruktur von Configuration Manager (Current Branch). Configuration Manager kann an große Umgebungen angepasst werden und bietet eine umfassende Kontrolle über Installation, Updates und Einstellungen. Er verfügt außerdem über integrierte Features, um die Bereitstellung und Verwaltung von Windows 10 Enterprise zu vereinfachen und effizienter zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="4fac9-p103">Contoso has an existing Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="4fac9-124">Planungsprozess</span><span class="sxs-lookup"><span data-stu-id="4fac9-124">Planning process</span></span>

<span data-ttu-id="4fac9-125">Contoso hat die Upgrade-Bereitschaft in Windows Analytics verwendet, um die Gruppe der installierten apps und deren Kompatibilität mit Windows 10 Enterprise zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="4fac9-125">Contoso used the Upgrade Readiness in Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="4fac9-126">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="4fac9-126">Deployment process</span></span>

<span data-ttu-id="4fac9-127">Um die Bereitstellung des direkten Upgrades von Windows 10 Enterprise abzuschließen, hat Contoso den folgenden Prozess implementiert, der Empfehlungen zu bewährten Vorgehensweisen von Microsoft umfasst:</span><span class="sxs-lookup"><span data-stu-id="4fac9-127">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="4fac9-128">Der Peercache für Configuration Manager wurde aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4fac9-128">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="4fac9-129">Es wurden angepasste Windows-Pakete basierend auf Images aus dem Volume Licensing Service Center erstellt.</span><span class="sxs-lookup"><span data-stu-id="4fac9-129">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="4fac9-130">Verwenden Sie den Konfigurations-Manager, um die Windows-Pakete für Verteilungspunkte in Ihrem Netzwerk bereitzustellen und Builds für die drei Bereitstellungsgruppen für Validierung und Bereitstellung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4fac9-130">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging groups.</span></span>
4. <span data-ttu-id="4fac9-131">Mithilfe der Lösungen für Geräteintegrität und Updatebereitschaft von Windows Analytics wurden der Erfolg von Computern und Geräten in den drei Ringen für Überprüfung und Staging der Bereitstellung bewertet.</span><span class="sxs-lookup"><span data-stu-id="4fac9-131">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="4fac9-132">Basierend auf den Windows Analytics-Informationen hat Contoso die Version von Windows 10 Enterprise festgelegt, die in der breiten Bereitstellungsgruppe bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4fac9-132">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment group.</span></span>
6. <span data-ttu-id="4fac9-133">Die Configuration Manager-Bereitstellungstasksequenzen wurden ausgeführt, um das ausgewählte Windows-Paket für die Breite Bereitstellungsgruppe bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4fac9-133">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment group.</span></span>
7. <span data-ttu-id="4fac9-134">Überwachte PCs und Geräte in der breiten Bereitstellungsgruppe mithilfe der Geräte Integrität und Update Compliance-Lösungen, um Probleme zu beheben.</span><span class="sxs-lookup"><span data-stu-id="4fac9-134">Monitored PCs and devices in the broad deployment group using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="4fac9-135">Hier ist Contosos Bereitstellungsarchitektur für das direkte Upgrade und fortlaufende Updates.</span><span class="sxs-lookup"><span data-stu-id="4fac9-135">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Contosos Bereitstellungsinfrastruktur für Windows 10 Enterprise](../media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="4fac9-137">Diese Infrastruktur besteht aus:</span><span class="sxs-lookup"><span data-stu-id="4fac9-137">This infrastructure consists of:</span></span>

- <span data-ttu-id="4fac9-138">Configuration Manager, der:</span><span class="sxs-lookup"><span data-stu-id="4fac9-138">Configuration Manager, which:</span></span>
  - <span data-ttu-id="4fac9-139">Images für Windows 10 Enterprise-Pakete aus dem Microsoft Volume Licensing Center im Microsoft Network abruft.</span><span class="sxs-lookup"><span data-stu-id="4fac9-139">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="4fac9-140">Als zentraler Verwaltungspunkt für Bereitstellungspakete fungiert.</span><span class="sxs-lookup"><span data-stu-id="4fac9-140">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="4fac9-141">Regionale Verteilungspunkte befinden sich in der Regel in den regionalen Hub-Büros von Contoso.</span><span class="sxs-lookup"><span data-stu-id="4fac9-141">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="4fac9-142">Windows-PCs und-Geräte an verschiedenen Standorten, die die Bereitstellungspakete für das in-Place-Upgrade oder laufende Updates basierend auf der Gruppenmitgliedschaft empfangen und installieren.</span><span class="sxs-lookup"><span data-stu-id="4fac9-142">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on group membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="4fac9-143">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="4fac9-143">Next step</span></span>

<span data-ttu-id="4fac9-144">Erfahren Sie, wie Contoso seine Configuration Manager-Infrastruktur nutzt, um [aktuelle Microsoft 365-Apps für Unternehmen in Ihrer Organisation bereitzustellen und zu halten](contoso-o365pp.md) .</span><span class="sxs-lookup"><span data-stu-id="4fac9-144">Learn how Contoso is leveraging its Configuration Manager infrastructure to [deploy and keep current Microsoft 365 Apps for enterprise](contoso-o365pp.md) across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="4fac9-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fac9-145">See also</span></span>

[<span data-ttu-id="4fac9-146">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4fac9-146">Windows 10 Enterprise</span></span>](https://docs.microsoft.com/windows/deployment/)

[<span data-ttu-id="4fac9-147">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4fac9-147">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4fac9-148">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="4fac9-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
