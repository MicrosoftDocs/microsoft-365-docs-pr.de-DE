---
title: 'Phase 3: Beendigungskriterien für die Windows 10 Enterprise-Infrastruktur'
f1.keywords:
- NOCSH
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Stellen Sie sicher, dass Ihre Konfiguration die Kriterien von Microsoft 365 Enterprise für Windows 10 Enterprise erfüllt.
ms.openlocfilehash: cf4a813a6cf89029eebde8e5947caf7b3c2ea553
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636687"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a><span data-ttu-id="a4a0c-103">Phase 3: Beendigungskriterien für die Windows 10 Enterprise-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="a4a0c-103">Phase 3: Windows 10 Enterprise infrastructure exit criteria</span></span>

![Phase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="a4a0c-105">Stellen Sie sicher, dass Ihre Windows 10 Enterprise-Infrastruktur die folgenden erforderlichen Kriterien erfüllt, und dass Sie die optionalen Kriterien berücksichtigt haben.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-105">Make sure your Windows 10 Enterprise infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="a4a0c-106">Erforderlich: Ihrer Microsoft 365-Domänen wurden hinzugefügt und überprüft</span><span class="sxs-lookup"><span data-stu-id="a4a0c-106">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="a4a0c-107">Der Azure AD-Mandant für Ihre Office 365- und Intune-Abonnements wurde mit Ihren Internetdomänennamen (z. B. „contoso.com“) konfiguriert, statt nur mit einem Domänennamen, der „onmicrosoft.com“ enthält.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-107">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="a4a0c-p101">Wenn dies nicht der Fall ist, werden die Authentifizierungsmethoden eingeschränkt, die Sie konfigurieren können. Pass-Through und Verbundauthentifizierung können zum Beispiel den Domänennamen „onmicrosoft.com“ nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-p101">If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="a4a0c-110">Gegebenenfalls hilft Ihnen [Schritt 1](windows10-prepare-your-org.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-110">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this requirement.</span></span>

## <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="a4a0c-111">Optional: Benutzer sind hinzugefügt und lizenziert</span><span class="sxs-lookup"><span data-stu-id="a4a0c-111">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="a4a0c-112">Die entsprechenden Konten für Ihre Benutzer wurden hinzugefügt, entweder direkt zu Ihrem Azure AD-Mandanten für Ihre Office 365- und Intune-Abonnements oder über die Verzeichnissynchronisierung von Ihren lokalen Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="a4a0c-112">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Active Directory Domain Services (AD DS).</span></span>

<span data-ttu-id="a4a0c-113">Nachdem Sie die Benutzer hinzugefügt haben, können Sie diesen Microsoft 365 Enterprise-Lizenzen zuweisen, entweder direkt als globaler Administrator oder Benutzeradministrator oder automatisch über die Gruppenmitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-113">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="a4a0c-114">Gegebenenfalls hilft Ihnen [Schritt 1](windows10-prepare-your-org.md) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-114">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

## <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="a4a0c-115">Optional: Diagnosen sind aktiviert</span><span class="sxs-lookup"><span data-stu-id="a4a0c-115">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="a4a0c-116">Sie haben Diagnosedateneinstellungen mithilfe einer Gruppenrichtlinie, Microsoft Intune, des Registrierungs-Editors oder der Eingabeaufforderung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-116">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="a4a0c-117">Gegebenenfalls hilft Ihnen [Schritt 1](windows10-prepare-your-org.md) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-117">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="a4a0c-118">Für direktes Upgrade erforderlich: Eine Tasksequenz des Konfigurations-Managers wurde für eine Bereitstellung des Betriebssystems erstellt</span><span class="sxs-lookup"><span data-stu-id="a4a0c-118">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="a4a0c-119">Zum Starten einer Tasksequenz des Konfigurations-Managers für ein direktes Upgrade auf einem Gerät unter Windows 7 oder Windows 8.1 müssen Sie die folgenden Schritte durchführen:</span><span class="sxs-lookup"><span data-stu-id="a4a0c-119">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="a4a0c-120">Festlegen der entsprechenden Windows-Diagnosedatenebene</span><span class="sxs-lookup"><span data-stu-id="a4a0c-120">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="a4a0c-121">Sie haben die Bereitschaft für ein Upgrade von Windows überprüft.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-121">Verified the readiness to upgrade Windows</span></span>
- <span data-ttu-id="a4a0c-122">Sie haben eine Configuration Manager-Tasksequenz erstellt, die eine Gerätesammlung und eine Bereitstellung des Betriebssystems mit einem Windows 10-Betriebssystemimage enthält.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-122">Created a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="a4a0c-p102">Nach Abschluss dieser Schritte können Sie direkte Upgrades auf Geräten durchführen, die für das Upgrade von Windows bereit sind. Um den maximalen Nutzen aus Microsoft 365 Enterprise zu ziehen, führen Sie das Upgrade für so viele Geräte unter Windows 7 und Windows 8.1 wie möglich durch.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-p102">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="a4a0c-p103">Jedes Gerät unter Windows 10 Enterprise kann von den Vorteilen der integrierten Lösung von Microsoft 365 Enterprise profitieren. Die verbleibenden Geräte unter Windows 7 oder Windows 8.1 können die Cloudtechnologien und erweiterten Sicherheitsfunktionen von Windows 10 Enterprise nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-p103">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="a4a0c-127">Gegebenenfalls hilft Ihnen [Schritt 2](windows10-deploy-inplaceupgrade.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-127">If needed, [Step 2](windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="a4a0c-128">Erforderlich für neue Geräte: Windows Autopilot wurde konfiguriert</span><span class="sxs-lookup"><span data-stu-id="a4a0c-128">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="a4a0c-129">Um Windows Autopilot zum Bereitstellen und Anpassen von Windows 10 Enterprise auf einem neuen Gerät zu verwenden, müssen Sie die folgenden Schritte durchführen:</span><span class="sxs-lookup"><span data-stu-id="a4a0c-129">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="a4a0c-130">Sie haben die entsprechende Windows-Diagnosedatenebene festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-130">Configured the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="a4a0c-131">Sie haben die für Windows Autopilot erforderlichen Schritte abgeschlossen, die Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="a4a0c-131">Configured the prerequisites for Windows Autopilot, which include:</span></span>
   - <span data-ttu-id="a4a0c-132">Geräteregistrierung und Anpassung der Windows-Willkommensseite</span><span class="sxs-lookup"><span data-stu-id="a4a0c-132">Device registration and OOBE customization</span></span>
   - <span data-ttu-id="a4a0c-133">Unternehmensbranding für Windows-Willkommensseite</span><span class="sxs-lookup"><span data-stu-id="a4a0c-133">Company branding for OOBE</span></span>
   - <span data-ttu-id="a4a0c-134">Automatische Registrierung bei MDM in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a4a0c-134">MDM auto-enrollment in Microsoft Intune</span></span>
   - <span data-ttu-id="a4a0c-135">Netzwerkkonnektivität mit von Windows Autopilot verwendeten Clouddiensten</span><span class="sxs-lookup"><span data-stu-id="a4a0c-135">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="a4a0c-136">Geräte, auf denen Windows 10, Version 1703 oder höher vorinstalliert ist</span><span class="sxs-lookup"><span data-stu-id="a4a0c-136">Devices that are pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="a4a0c-137">Auswählen des Windows Autopilot Deployment-Programms für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="a4a0c-137">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="a4a0c-138">Nach Abschluss der Konfiguration von Windows Autopilot können Sie diese zum Konfigurieren und Anpassen von Windows 10 Enterprise für die Windows-Willkommensseite für Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="a4a0c-138">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="a4a0c-139">Neue Geräte</span><span class="sxs-lookup"><span data-stu-id="a4a0c-139">New devices</span></span>
- <span data-ttu-id="a4a0c-140">Geräte, die in Ihrer Organisation bereits eingerichtet wurden</span><span class="sxs-lookup"><span data-stu-id="a4a0c-140">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="a4a0c-141">Windows Autopilot konfiguriert das Gerät und verbindet es mit Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-141">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="a4a0c-142">Ohne Windows Autopilot müssen neue Geräte manuell konfiguriert werden und mit Azure AD verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-142">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="a4a0c-143">Gegebenenfalls hilft Ihnen [Schritt 3](windows10-deploy-autopilot.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-143">If needed, [Step 3](windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="a4a0c-144">Optional: Bei Verwendung von Windows Analytics Device Health für Geräte für die Überwachung von Windows 10 Enterprise-basierten Geräten</span><span class="sxs-lookup"><span data-stu-id="a4a0c-144">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="a4a0c-p104">Sie haben die Informationen unter „Integrität von Geräten mit Device Health überwachen“ zum Erkennen und Beheben von Problemen mit Auswirkungen auf die Endbenutzer verwendet. Eine schnelle Behebung dieser Art von Problemen kann Ihre Supportkosten reduzieren und Benutzern das IT-Engagement für Windows 10 Enterprise demonstrieren, was eine schnelle Benutzerakzeptanz in Ihrer Organisation fördern kann.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-p104">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="a4a0c-147">Gegebenenfalls hilft Ihnen [Schritt 4](windows10-enable-windows-analytics.md) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-147">If needed, [Step 4](windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="a4a0c-148">Erforderlich: Bei Verwendung von Windows Defender Antivirus oder einer eigenen Antischadsoftwarelösung</span><span class="sxs-lookup"><span data-stu-id="a4a0c-148">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="a4a0c-p105">Sie haben Windows Defender Antivirus oder eine eigene Antischadsoftwarelösung bereitgestellt, um Ihre Geräte unter Windows 10 Enterprise vor Schadsoftware zu schützen. Wenn Sie Windows Defender Antivirus bereitgestellt haben, haben Sie eine Berichterstellungsmethode wie Microsoft Endpoint Configuration Manager oder Microsoft Intune implementiert, um Antivirusereignisse und -aktivitäten zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-p105">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as Microsoft Endpoint Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="a4a0c-151">Gegebenenfalls hilft Ihnen [Schritt 5](windows10-enable-security-features.md#windows10-sec-av), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-151">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="a4a0c-152">Erforderlich: Verwendung von Windows Defender Exploit Guard</span><span class="sxs-lookup"><span data-stu-id="a4a0c-152">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="a4a0c-153">Sie haben Windows Defender Exploit Guard bereitgestellt, um Ihre Geräte unter Windows 10 Enterprise vor Angriffen zu schützen, und haben eine Berichterstellungsmethode wie Configuration Manager oder Microsoft Intune implementiert, um Angriffsschutzereignisse und -aktivitäten zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-153">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="a4a0c-154">Gegebenenfalls hilft Ihnen [Schritt 5](windows10-enable-security-features.md#windows10-sec-eg), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-154">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a><span data-ttu-id="a4a0c-155">Erforderlich: Verwendung von Microsoft Defender Advanced Threat Protection (nur Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="a4a0c-155">Required: You are using Microsoft Defender Advanced Threat Protection (Microsoft 365 E5 only)</span></span>

<span data-ttu-id="a4a0c-156">Sie haben Microsoft Defender Advanced Threat Protection (ATP) bereitgestellt, um erweiterte Bedrohungen für Ihr Netzwerk und die Geräte unter Windows 10 Enterprise zu ermitteln, zu analysieren und auf diese zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-156">You deployed Microsoft Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="a4a0c-157">Optional haben Sie Microsoft Defender ATP in anderen Tools integriert, um seine Funktionen zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-157">Optionally, you have integrated Microsoft Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="a4a0c-158">Gegebenenfalls hilft Ihnen [Schritt 5](windows10-enable-security-features.md#windows10-sec-atp), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-158">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="a4a0c-159">Ergebnisse und nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a4a0c-159">Results and next steps</span></span>

<span data-ttu-id="a4a0c-160">Ihre Windows 10 Enterprise-Infrastruktur ist für die Installation auf neuen Geräten und für direkte Upgrades auf Geräten mit früheren Versionen von Windows bereit, und Sie verwenden die wichtigsten Sicherheitsfeatures von Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a4a0c-160">Your Windows 10 Enterprise infrastructure is ready to begin installation on new devices and upgrades-in-place on devices running previous versions of Windows, and you are using the key security features of Windows 10 Enterprise.</span></span>

|||
|:-------|:-----|
|![Phase 4: Microsoft 365 Apps for Enterprise](../media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| <span data-ttu-id="a4a0c-162">Wenn Sie den Phasen für die Ende-zu-Ende-Bereitstellung von Microsoft 365 Enterprise folgen, ist die nächste Phase [Microsoft 365 Apps for Enterprise](office365proplus-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="a4a0c-162">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md).</span></span> |
