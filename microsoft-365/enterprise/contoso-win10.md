---
title: Bereitstellung von Windows 10 Enterprise für Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen dazu, wie Contoso System Center Configuration Manager zur Bereitstellung von direkten Upgrades für Windows 10 Enterprise verwendete.
ms.openlocfilehash: a63a973bed4bf62ebf7c2534d4c55a4e3b8ef60c
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370472"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="ca42d-103">Bereitstellung von Windows 10 Enterprise für Contoso</span><span class="sxs-lookup"><span data-stu-id="ca42d-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="ca42d-104">**Zusammenfassung:** Informationen dazu, wie Contoso System Center Configuration Manager zur Bereitstellung von direkten Upgrades für Windows 10 Enterprise verwendete.</span><span class="sxs-lookup"><span data-stu-id="ca42d-104">**Summary:** Understand how Contoso used System Center Configuration Manager to deploy in-place upgrades for Windows 10 Enterprise.</span></span>

<span data-ttu-id="ca42d-p101">Vor der unternehmensweiten Einführung von Microsoft 365 Enterprise verfügte Contoso über Windows-kompatible Computer und Geräte, auf denen eine Mischung aus Windows 7 (10 %), Windows 8.1 (65 %) und Windows 10 (25 %) ausgeführt wurde. Contoso wollte seine Computer auf Windows 10 Enterprise aktualisieren, um die erweiterte Sicherheit sowie den niedrigeren IT-Aufwand der automatisierten Bereitstellung von Updates nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="ca42d-p101">Prior to the wide rollout of Microsoft 365 Enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of improved security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="ca42d-107">Nach der Bewertung der Infrastruktur und der Geschäftsanforderungen identifizierte Contoso die folgenden Hauptanforderungen für die Bereitstellung:</span><span class="sxs-lookup"><span data-stu-id="ca42d-107">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="ca42d-108">Windows 10 Enterprise soll auf so vielen Computern und Geräten wie möglich ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ca42d-108">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="ca42d-109">Die Einführung von direkten Upgrades nutzt die vorhandene System Center Configuration Manager-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="ca42d-109">Rollout of the in-place upgrades leverages existing System Center Configuration Manager infrastructure</span></span>
- <span data-ttu-id="ca42d-110">Die Steuerung, welche Versionen von Windows 10 Enterprise bereitgestellt und aktualisiert werden sollen, erfolgt über Ringe.</span><span class="sxs-lookup"><span data-stu-id="ca42d-110">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="ca42d-111">Computer und Geräte sollen mit minimalen IT-Verwaltungskosten und minimalen Auswirkungen auf die Endbenutzer auf dem aktuellen Stand gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="ca42d-111">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="ca42d-112">„Auf dem neuesten Stand“ wird definiert als die unterstützte Version von Windows 10 Enterprise, die den Geschäftsanforderungen von Contoso entspricht; dabei muss es nicht unbedingt darum gehen, dass auf allen Windows-kompatiblen Computern die neueste Version von Windows 10 Enterprise ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ca42d-112">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="ca42d-113">Bereitstellungstools</span><span class="sxs-lookup"><span data-stu-id="ca42d-113">Deployment tools</span></span>

<span data-ttu-id="ca42d-114">Vor und während direkter Upgrades von Windows 10 Enterprise verwendete Contoso die folgenden Lösungen von Windows Analytics:</span><span class="sxs-lookup"><span data-stu-id="ca42d-114">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="ca42d-115">Upgradebereitschaft</span><span class="sxs-lookup"><span data-stu-id="ca42d-115">Upgrade Readiness</span></span>  

  <span data-ttu-id="ca42d-116">Es werden System-, Anwedungs- und Treiberdaten für die Analyse erfasst und dann Kompatibilitätsprobleme identifiziert, durch die ein Upgrade und vorgeschlagene Korrekturen blockiert werden können, die Microsoft bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="ca42d-116">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="ca42d-117">Update-Compliance</span><span class="sxs-lookup"><span data-stu-id="ca42d-117">Update Compliance</span></span>  

  <span data-ttu-id="ca42d-118">Zeigt den Status Ihrer Geräte in Bezug auf die Windows-Updates an, so dass Sie sicherstellen können, dass diese gegebenenfalls auf den aktuellsten Updates sind.</span><span class="sxs-lookup"><span data-stu-id="ca42d-118">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="ca42d-119">Geräteintegrität</span><span class="sxs-lookup"><span data-stu-id="ca42d-119">Device Health</span></span>  

  <span data-ttu-id="ca42d-120">Identifiziert Geräte, die häufig abstürzen und daher möglicherweise neu aufgebaut oder ersetzt werden müssen, und Gerätetreiber, die Geräteabstürze verursachen, mit Vorschlägen für alternative Versionen dieser Treiber, welche die Anzahl der Abstürze reduzieren könnten.</span><span class="sxs-lookup"><span data-stu-id="ca42d-120">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="ca42d-121">Bietet eine Benachrichtigung über Fehlkonfigurationen des Windows Information Protection, die Eingabeaufforderungen an Endbenutzer senden.</span><span class="sxs-lookup"><span data-stu-id="ca42d-121">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="ca42d-p103">Contoso verfügt über eine vorhandene Infrastruktur von System Center Configuration Manager (Current Branch). Configuration Manager kann an große Umgebungen angepasst werden und bietet eine umfassende Kontrolle über Installation, Updates und Einstellungen. Er verfügt außerdem über integrierte Features, um die Bereitstellung und Verwaltung von Windows 10 Enterprise zu vereinfachen und effizienter zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="ca42d-p103">Contoso has an existing System Center Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="ca42d-125">Planungsprozess</span><span class="sxs-lookup"><span data-stu-id="ca42d-125">Planning process</span></span>

<span data-ttu-id="ca42d-126">Vor der Bereitstellung hat Contoso die folgenden Ringe definiert:</span><span class="sxs-lookup"><span data-stu-id="ca42d-126">Prior to deployment, Contoso defined the following rings:</span></span>

- <span data-ttu-id="ca42d-127">Drei Ringe für die Überprüfung und das Staging der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="ca42d-127">Three rings for validation and deployment staging</span></span> 
  - <span data-ttu-id="ca42d-128">Ein Ring für Vorschau-Builds</span><span class="sxs-lookup"><span data-stu-id="ca42d-128">One for preview builds</span></span> 
  - <span data-ttu-id="ca42d-129">Ein Ring für die Builds von neuen Versionen</span><span class="sxs-lookup"><span data-stu-id="ca42d-129">One for new release builds</span></span>
  - <span data-ttu-id="ca42d-130">Ein Ring für einen früheren Build</span><span class="sxs-lookup"><span data-stu-id="ca42d-130">One for a previous build</span></span> 
- <span data-ttu-id="ca42d-131">Ein Ring für die allgemeine Bereitstellung von Windows 10 Enterprise basierend auf Daten aus den Überprüfungsringen</span><span class="sxs-lookup"><span data-stu-id="ca42d-131">One ring for broad deployment of Windows 10 Enterprise based on data from the validation rings</span></span>

<span data-ttu-id="ca42d-132">Contoso hat auch die Lösung für die Upgradebereitschaft von Windows Analytics verwendet, um installierte Apps und deren Kompatibilität mit Windows 10 Enterprise zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ca42d-132">Contoso also used the Upgrade Readiness solution of Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="ca42d-133">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="ca42d-133">Deployment process</span></span>

<span data-ttu-id="ca42d-134">Um die Bereitstellung des direkten Upgrades von Windows 10 Enterprise abzuschließen, hat Contoso den folgenden Prozess implementiert, der Empfehlungen zu bewährten Vorgehensweisen von Microsoft umfasst:</span><span class="sxs-lookup"><span data-stu-id="ca42d-134">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="ca42d-135">Der Peercache für Configuration Manager wurde aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ca42d-135">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="ca42d-136">Es wurden angepasste Windows-Pakete basierend auf Images aus dem Volume Licensing Service Center erstellt.</span><span class="sxs-lookup"><span data-stu-id="ca42d-136">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="ca42d-137">Configuration Manager wurde zur Bereitstellung der Windows-Pakete an Verteilungspunkten im Netzwerk verwendet, und es wurden Builds an den drei Ringen für Überprüfung und Staging der Bereitstellung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ca42d-137">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging rings.</span></span>
4. <span data-ttu-id="ca42d-138">Mithilfe der Lösungen für Geräteintegrität und Updatebereitschaft von Windows Analytics wurden der Erfolg von Computern und Geräten in den drei Ringen für Überprüfung und Staging der Bereitstellung bewertet.</span><span class="sxs-lookup"><span data-stu-id="ca42d-138">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="ca42d-139">Contoso ermittelte (basierend auf den Windows Analytics-Informationen) die Version von Windows 10 Enterprise, die im Ring der Bereitstellung auf breiter Basis bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ca42d-139">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment ring.</span></span>
6. <span data-ttu-id="ca42d-140">Es wurden die Bereitstellungsaufgabenfolgen von Configuration Manager ausgeführt, um das ausgewählte Windows-Paket im Ring der Bereitstellung auf breiter Basis bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ca42d-140">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment ring.</span></span>
7. <span data-ttu-id="ca42d-141">Die Computer und Geräte im Ring der Bereitstellung auf breiter Basis wurden mithilfe der Lösungen für Geräteintegrität und Updatebereitschaft überwacht, die zur Behebung von Problemen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ca42d-141">Monitored PCs and devices in the broad deployment ring using the Device Health and Update Compliance solutions provided by Windows Analytics to address issues.</span></span>

<span data-ttu-id="ca42d-142">Hier ist Contosos Bereitstellungsarchitektur für das direkte Upgrade und fortlaufende Updates.</span><span class="sxs-lookup"><span data-stu-id="ca42d-142">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Contosos Bereitstellungsinfrastruktur für Windows 10 Enterprise](./media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="ca42d-144">Diese Infrastruktur besteht aus:</span><span class="sxs-lookup"><span data-stu-id="ca42d-144">This infrastructure consists of:</span></span>

- <span data-ttu-id="ca42d-145">System Center Configuration Manager, der:</span><span class="sxs-lookup"><span data-stu-id="ca42d-145">System Center Configuration Manager, which:</span></span>
  - <span data-ttu-id="ca42d-146">Images für Windows 10 Enterprise-Pakete aus dem Microsoft Volume Licensing Center im Microsoft Network abruft.</span><span class="sxs-lookup"><span data-stu-id="ca42d-146">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="ca42d-147">Als zentraler Verwaltungspunkt für Bereitstellungspakete fungiert.</span><span class="sxs-lookup"><span data-stu-id="ca42d-147">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="ca42d-148">Regionale Verteilungspunkte befinden sich in der Regel in den regionalen Hub-Büros von Contoso.</span><span class="sxs-lookup"><span data-stu-id="ca42d-148">Regional distribution points that are typically located in Contoso’s satellite offices.</span></span>
- <span data-ttu-id="ca42d-149">Windows-PCs und Geräte an verschiedenen Standorten, die die Bereitstellungspakete für das direkte Upgrade oder für laufende Updates basierend auf der Ringmitgliedschaft empfangen und installieren.</span><span class="sxs-lookup"><span data-stu-id="ca42d-149">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on ring membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="ca42d-150">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="ca42d-150">Next step</span></span>

<span data-ttu-id="ca42d-151">[Erfahren Sie mehr](contoso-o365pp.md) darüber, wie Contoso seine System Center Configuration Manager-Infrastruktur verwendet, um Office 365 ProPlus in der gesamten Organisation bereitzustellen und auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="ca42d-151">[Learn](contoso-o365pp.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Office 365 ProPlus across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="ca42d-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca42d-152">See also</span></span>

[<span data-ttu-id="ca42d-153">Windows 10 Enterprise für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ca42d-153">Windows 10 Enterprise for Microsoft 365 Enterprise</span></span>](windows10-infrastructure.md)

[<span data-ttu-id="ca42d-154">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="ca42d-154">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ca42d-155">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="ca42d-155">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
