---
title: Bereitstellung von Windows 10 Enterprise für Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Informationen dazu, wie Contoso System Center Configuration Manager zur Bereitstellung von direkten Upgrades für Windows 10 Enterprise verwendete.
ms.openlocfilehash: 03ee4d9efcedf42eb976e001411299d2080abf83
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073855"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="09d4b-103">Bereitstellung von Windows 10 Enterprise für Contoso</span><span class="sxs-lookup"><span data-stu-id="09d4b-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="09d4b-104">**Zusammenfassung:** Informationen dazu, wie Contoso System Center Configuration Manager zur Bereitstellung von direkten Upgrades für Windows 10 Enterprise verwendete.</span><span class="sxs-lookup"><span data-stu-id="09d4b-104">**Summary:** Understand how Contoso used System Center Configuration Manager to deploy in-place upgrades for Windows 10 Enterprise.</span></span>

<span data-ttu-id="09d4b-p101">Vor der unternehmensweiten Einführung von Microsoft 365 Enterprise verfügte Contoso über Windows-kompatible Computer und Geräte, auf denen eine Mischung aus Windows 7 (10 %), Windows 8.1 (65 %) und Windows 10 (25 %) ausgeführt wurde. Contoso wollte seine Computer auf Windows 10 Enterprise aktualisieren, um die höhere Sicherheit sowie den niedrigeren IT-Aufwand der automatisierten Bereitstellung von Updates nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="09d4b-p101">Prior to the wide rollout of Microsoft 365 Enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of improved security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="09d4b-107">Nach der Bewertung der Infrastruktur und der Geschäftsanforderungen identifizierte Contoso die folgenden Hauptanforderungen für die Bereitstellung:</span><span class="sxs-lookup"><span data-stu-id="09d4b-107">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="09d4b-108">Windows 10 Enterprise soll auf so vielen Computern und Geräten wie möglich ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="09d4b-108">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="09d4b-109">Die Einführung von direkten Upgrades nutzt die vorhandene System Center Configuration Manager-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="09d4b-109">Rollout of the in-place upgrades leverages existing System Center Configuration Manager infrastructure</span></span>
- <span data-ttu-id="09d4b-110">Die Steuerung, welche Versionen von Windows 10 Enterprise bereitgestellt und aktualisiert werden sollen, erfolgt über Ringe.</span><span class="sxs-lookup"><span data-stu-id="09d4b-110">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="09d4b-111">Computer und Geräte sollen mit minimalen IT-Verwaltungskosten und minimalen Auswirkungen auf die Endbenutzer auf dem aktuellen Stand gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="09d4b-111">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="09d4b-112">„Auf dem neuesten Stand“ wird definiert als die unterstützte Version von Windows 10 Enterprise, die den Geschäftsanforderungen von Contoso entspricht; dabei muss es nicht unbedingt darum gehen, dass auf allen Windows-kompatiblen Computern die neueste Version von Windows 10 Enterprise ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="09d4b-112">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="09d4b-113">Bereitstellungstools</span><span class="sxs-lookup"><span data-stu-id="09d4b-113">Deployment tools</span></span>

<span data-ttu-id="09d4b-114">Vor und während direkter Upgrades von Windows 10 Enterprise verwendete Contoso die folgenden Lösungen von Windows Analytics:</span><span class="sxs-lookup"><span data-stu-id="09d4b-114">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="09d4b-115">Upgradebereitschaft</span><span class="sxs-lookup"><span data-stu-id="09d4b-115">Upgrade Readiness</span></span>  

  <span data-ttu-id="09d4b-116">Es werden System-, Anwedungs- und Treiberdaten für die Analyse erfasst und dann Kompatibilitätsprobleme identifiziert, durch die ein Upgrade und vorgeschlagene Korrekturen blockiert werden können, die Microsoft bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="09d4b-116">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="09d4b-117">Update-Compliance</span><span class="sxs-lookup"><span data-stu-id="09d4b-117">Update Compliance</span></span>  

  <span data-ttu-id="09d4b-118">Es werden System- und Diagnosedaten, einschließlich des Updateinstallationsstatus, WUfB-Konfigurationsdaten (Windows Update for Business), Windows Defender Antivirus-Daten und anderer updatespezifischer Informationen erfasst; diese Daten werden dann in der Cloudanalyse und -verwendung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="09d4b-118">Collects system and diagnostics data including update installation progress, Windows Update for Business (WUfB) configuration data, Windows Defender Antivirus data, and other update-specific information, and then stores this data in the cloud analysis and usage.</span></span>

- <span data-ttu-id="09d4b-119">Geräteintegrität</span><span class="sxs-lookup"><span data-stu-id="09d4b-119">Device Health</span></span>  

  <span data-ttu-id="09d4b-120">Es werden System- und Diagnosedaten für Windows 10, einschließlich des Updateinstallationsstatus, WUfB-Konfigurationsdaten (Windows Update for Business), Windows Defender Antivirus-Daten und anderer updatespezifischer Informationen erfasst; diese Daten werden dann in der Cloudanalyse und -verwendung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="09d4b-120">Collects Windows 10 system and diagnostic data including update installation progress, Windows Update for Business (WUfB) configuration data, Windows Defender Antivirus data, and other update-specific information, and then stores this data in the cloud analysis and usage.</span></span>
 
<span data-ttu-id="09d4b-p102">Contoso verfügt über eine vorhandene Infrastruktur von System Center Configuration Manager (Current Branch). Configuration Manager kann an große Umgebungen angepasst werden und bietet eine umfassende Kontrolle über Installation, Updates und Einstellungen. Er verfügt außerdem über integrierte Features, um die Bereitstellung und Verwaltung von Windows 10 Enterprise zu vereinfachen und effizienter zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="09d4b-p102">Contoso has an existing System Center Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="09d4b-124">Planungsprozess</span><span class="sxs-lookup"><span data-stu-id="09d4b-124">Planning process</span></span>

<span data-ttu-id="09d4b-125">Vor der Bereitstellung hat Contoso die folgenden Ringe definiert:</span><span class="sxs-lookup"><span data-stu-id="09d4b-125">Prior to deployment, Contoso defined the following rings:</span></span>

- <span data-ttu-id="09d4b-126">Drei Ringe für die Überprüfung und das Staging der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="09d4b-126">Three rings for validation and deployment staging</span></span> 
  - <span data-ttu-id="09d4b-127">Ein Ring für Vorschau-Builds</span><span class="sxs-lookup"><span data-stu-id="09d4b-127">One for preview builds</span></span> 
  - <span data-ttu-id="09d4b-128">Ein Ring für die Builds von neuen Versionen</span><span class="sxs-lookup"><span data-stu-id="09d4b-128">One for new release builds</span></span>
  - <span data-ttu-id="09d4b-129">Ein Ring für einen früheren Build</span><span class="sxs-lookup"><span data-stu-id="09d4b-129">One for a previous build</span></span> 
- <span data-ttu-id="09d4b-130">Ein Ring für die allgemeine Bereitstellung von Windows 10 Enterprise basierend auf Daten aus den Überprüfungsringen</span><span class="sxs-lookup"><span data-stu-id="09d4b-130">One ring for broad deployment of Windows 10 Enterprise based on data from the validation rings</span></span>

<span data-ttu-id="09d4b-131">Contoso hat auch die Lösung für die Upgradebereitschaft von Windows Analytics verwendet, um installierte Apps und deren Kompatibilität mit Windows 10 Enterprise zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="09d4b-131">Contoso also used the Upgrade Readiness solution of Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="09d4b-132">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="09d4b-132">Deployment process</span></span>

<span data-ttu-id="09d4b-133">Um die Bereitstellung des direkten Upgrades von Windows 10 Enterprise abzuschließen, hat Contoso den folgenden Prozess implementiert, der Empfehlungen zu bewährten Vorgehensweisen von Microsoft umfasst:</span><span class="sxs-lookup"><span data-stu-id="09d4b-133">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="09d4b-134">Der Peercache für Configuration Manager wurde aktiviert.</span><span class="sxs-lookup"><span data-stu-id="09d4b-134">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="09d4b-135">Es wurden angepasste Windows-Pakete basierend auf Images aus dem Volume Licensing Service Center erstellt.</span><span class="sxs-lookup"><span data-stu-id="09d4b-135">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="09d4b-136">Configuration Manager wurde zur Bereitstellung der Windows-Pakete an Verteilungspunkten im Netzwerk verwendet, und es wurden Builds an den drei Ringen für Überprüfung und Staging der Bereitstellung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="09d4b-136">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging rings.</span></span>
4. <span data-ttu-id="09d4b-137">Mithilfe der Lösungen für Geräteintegrität und Updatebereitschaft von Windows Analytics wurden der Erfolg von Computern und Geräten in den drei Ringen für Überprüfung und Staging der Bereitstellung bewertet.</span><span class="sxs-lookup"><span data-stu-id="09d4b-137">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="09d4b-138">Contoso ermittelte (basierend auf den Windows Analytics-Informationen) die Version von Windows 10 Enterprise, die im Ring der Bereitstellung auf breiter Basis bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="09d4b-138">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment ring.</span></span>
6. <span data-ttu-id="09d4b-139">Es wurden die Bereitstellungsaufgabenfolgen von Configuration Manager ausgeführt, um das ausgewählte Windows-Paket im Ring der Bereitstellung auf breiter Basis bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="09d4b-139">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment ring.</span></span>
7. <span data-ttu-id="09d4b-140">Die Computer und Geräte im Ring der Bereitstellung auf breiter Basis wurden mithilfe der Lösungen für Geräteintegrität und Updatebereitschaft überwacht, die von Windows Analytics zur Behebung von Problemen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="09d4b-140">Monitored PCs and devices in the broad deployment ring using the Device Health and Update Compliance solutions provided by Windows Analytics to address issues.</span></span>

<span data-ttu-id="09d4b-141">Abbildung 1 zeigt die Bereitstellungsarchitektur für das direkte Upgrade und fortlaufende Updates.</span><span class="sxs-lookup"><span data-stu-id="09d4b-141">Figure 1 shows the in-place upgrade and ongoing updates deployment architecture.</span></span>

![](./media/contoso-win10/contoso-win10-fig1.png)
 
<span data-ttu-id="09d4b-142">**Abbildung 1: Bereitstellungsinfrastruktur für Windows 10 Enterprise von Contoso**</span><span class="sxs-lookup"><span data-stu-id="09d4b-142">**Figure 1: Contoso’s Windows 10 Enterprise deployment infrastructure**</span></span>

<span data-ttu-id="09d4b-143">Diese Infrastruktur besteht aus:</span><span class="sxs-lookup"><span data-stu-id="09d4b-143">This infrastructure consists of:</span></span>

- <span data-ttu-id="09d4b-144">System Center Configuration Manager, der:</span><span class="sxs-lookup"><span data-stu-id="09d4b-144">System Center Configuration Manager, which:</span></span>
  - <span data-ttu-id="09d4b-145">Images für Windows 10 Enterprise-Pakete aus dem Microsoft Volume Licensing Center im Microsoft Network abruft.</span><span class="sxs-lookup"><span data-stu-id="09d4b-145">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="09d4b-146">Als zentraler Verwaltungspunkt für Bereitstellungspakete fungiert.</span><span class="sxs-lookup"><span data-stu-id="09d4b-146">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="09d4b-147">Regionale Verteilungspunkte befinden sich in der Regel in den Zweigstellen von Contoso.</span><span class="sxs-lookup"><span data-stu-id="09d4b-147">Regional distribution points that are typically located in Contoso’s satellite offices.</span></span>
- <span data-ttu-id="09d4b-148">Windows-PCs und Geräte an verschiedenen Standorten, die die Bereitstellungspakete für das direkte Upgrade oder für laufende Updates basierend auf der Ringmitgliedschaft empfangen und installieren.</span><span class="sxs-lookup"><span data-stu-id="09d4b-148">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on ring membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="09d4b-149">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="09d4b-149">Next step</span></span>

<span data-ttu-id="09d4b-150">[Erfahren Sie mehr](contoso-o365pp.md) darüber, wie Contoso seine System Center Configuration Manager-Infrastruktur verwendet, um Office 365 ProPlus in der gesamten Organisation bereitzustellen und auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="09d4b-150">[Learn](contoso-o365pp.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Office 365 ProPlus across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="09d4b-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09d4b-151">See also</span></span>

[<span data-ttu-id="09d4b-152">Windows 10 Enterprise für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="09d4b-152">Windows 10 Enterprise for Microsoft 365 Enterprise</span></span>](windows10-infrastructure.md)

[<span data-ttu-id="09d4b-153">Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="09d4b-153">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="09d4b-154">Testumgebungsanleitungen</span><span class="sxs-lookup"><span data-stu-id="09d4b-154">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
