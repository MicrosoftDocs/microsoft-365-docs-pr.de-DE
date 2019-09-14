---
title: 'Phase 3: Beendigungskriterien für die Windows 10 Enterprise-Infrastruktur'
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
ms.openlocfilehash: 289d20b87d9cefcc63a060fb0dc526cf7a45b071
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982636"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a><span data-ttu-id="88ac2-103">Phase 3: Beendigungskriterien für die Windows 10 Enterprise-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="88ac2-103">Phase 3: Windows 10 Enterprise infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="88ac2-104">Stellen Sie sicher, dass Ihre Windows 10 Enterprise-Infrastruktur die folgenden erforderlichen Kriterien erfüllt, und dass Sie die optionalen Kriterien berücksichtigt haben.</span><span class="sxs-lookup"><span data-stu-id="88ac2-104">Make sure your Windows 10 Enterprise infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="88ac2-105">Erforderlich: Ihrer Microsoft 365-Domänen wurden hinzugefügt und überprüft</span><span class="sxs-lookup"><span data-stu-id="88ac2-105">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="88ac2-106">Der Azure AD-Mandant für Ihre Office 365- und Intune-Abonnements wurde mit Ihren Internetdomänennamen (z. B. „contoso.com“) konfiguriert, statt nur mit einem Domänennamen, der „onmicrosoft.com“ enthält.</span><span class="sxs-lookup"><span data-stu-id="88ac2-106">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="88ac2-p101">Wenn dies nicht der Fall ist, werden die Authentifizierungsmethoden eingeschränkt, die Sie konfigurieren können. Pass-Through und Verbundauthentifizierung können zum Beispiel den Domänennamen „onmicrosoft.com“ nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="88ac2-p101">If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="88ac2-109">Gegebenenfalls hilft Ihnen [Schritt 1](windows10-prepare-your-org.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="88ac2-109">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this requirement.</span></span>

## <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="88ac2-110">Optional: Benutzer sind hinzugefügt und lizenziert</span><span class="sxs-lookup"><span data-stu-id="88ac2-110">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="88ac2-111">Die entsprechenden Konten für Ihre Benutzer wurden hinzugefügt, entweder direkt zu Ihrem Azure AD-Mandanten für Ihre Office 365- und Intune-Abonnements oder über die Verzeichnissynchronisierung von Ihren lokalen Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="88ac2-111">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Active Directory Domain Services (AD DS).</span></span>

<span data-ttu-id="88ac2-112">Nachdem Sie die Benutzer hinzugefügt haben, können Sie diesen Microsoft 365 Enterprise-Lizenzen zuweisen, entweder direkt als globaler Administrator oder Benutzeradministrator oder automatisch über die Gruppenmitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="88ac2-112">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="88ac2-113">Gegebenenfalls hilft Ihnen [Schritt 1](windows10-prepare-your-org.md) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="88ac2-113">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

## <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="88ac2-114">Optional: Diagnosen sind aktiviert</span><span class="sxs-lookup"><span data-stu-id="88ac2-114">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="88ac2-115">Sie haben Diagnosedateneinstellungen mithilfe einer Gruppenrichtlinie, Microsoft Intune, des Registrierungs-Editors oder der Eingabeaufforderung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="88ac2-115">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="88ac2-116">Gegebenenfalls hilft Ihnen [Schritt 1](windows10-prepare-your-org.md) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="88ac2-116">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="88ac2-117">Für direktes Upgrade erforderlich: Eine Tasksequenz des Konfigurations-Managers wurde für eine Bereitstellung des Betriebssystems erstellt</span><span class="sxs-lookup"><span data-stu-id="88ac2-117">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="88ac2-118">Zum Starten einer Tasksequenz des Konfigurations-Managers für ein direktes Upgrade auf einem Gerät unter Windows 7 oder Windows 8.1 müssen Sie die folgenden Schritte durchführen:</span><span class="sxs-lookup"><span data-stu-id="88ac2-118">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="88ac2-119">Festlegen der entsprechenden Windows-Diagnosedatenebene</span><span class="sxs-lookup"><span data-stu-id="88ac2-119">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="88ac2-120">Sie haben die Bereitschaft für ein Upgrade von Windows überprüft.</span><span class="sxs-lookup"><span data-stu-id="88ac2-120">Verified the readiness to upgrade Windows</span></span>
- <span data-ttu-id="88ac2-121">Sie haben eine Configuration Manager-Tasksequenz erstellt, die eine Gerätesammlung und eine Bereitstellung des Betriebssystems mit einem Windows 10-Betriebssystemimage enthält.</span><span class="sxs-lookup"><span data-stu-id="88ac2-121">Created a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="88ac2-p102">Nach Abschluss dieser Schritte können Sie direkte Upgrades auf Geräten durchführen, die für das Upgrade von Windows bereit sind. Um den maximalen Nutzen aus Microsoft 365 Enterprise zu ziehen, führen Sie das Upgrade für so viele Geräte unter Windows 7 und Windows 8.1 wie möglich durch.</span><span class="sxs-lookup"><span data-stu-id="88ac2-p102">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="88ac2-p103">Jedes Gerät unter Windows 10 Enterprise kann von den Vorteilen der integrierten Lösung von Microsoft 365 Enterprise profitieren. Die verbleibenden Geräte unter Windows 7 oder Windows 8.1 können die Cloudtechnologien und erweiterten Sicherheitsfunktionen von Windows 10 Enterprise nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="88ac2-p103">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="88ac2-126">Gegebenenfalls hilft Ihnen [Schritt 2](windows10-deploy-inplaceupgrade.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="88ac2-126">If needed, [Step 2](windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="88ac2-127">Erforderlich für neue Geräte: Windows Autopilot wurde konfiguriert</span><span class="sxs-lookup"><span data-stu-id="88ac2-127">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="88ac2-128">Um Windows Autopilot zum Bereitstellen und Anpassen von Windows 10 Enterprise auf einem neuen Gerät zu verwenden, müssen Sie die folgenden Schritte durchführen:</span><span class="sxs-lookup"><span data-stu-id="88ac2-128">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="88ac2-129">Sie haben die entsprechende Windows-Diagnosedatenebene festgelegt.</span><span class="sxs-lookup"><span data-stu-id="88ac2-129">Configured the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="88ac2-130">Sie haben die für Windows Autopilot erforderlichen Schritte abgeschlossen, die Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="88ac2-130">Configured the prerequisites for Windows Autopilot, which include:</span></span>
   - <span data-ttu-id="88ac2-131">Geräteregistrierung und Anpassung der Windows-Willkommensseite</span><span class="sxs-lookup"><span data-stu-id="88ac2-131">Device registration and OOBE customization</span></span>
   - <span data-ttu-id="88ac2-132">Unternehmensbranding für Windows-Willkommensseite</span><span class="sxs-lookup"><span data-stu-id="88ac2-132">Company branding for OOBE</span></span>
   - <span data-ttu-id="88ac2-133">Automatische Registrierung bei MDM in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="88ac2-133">MDM auto-enrollment in Microsoft Intune</span></span>
   - <span data-ttu-id="88ac2-134">Netzwerkkonnektivität mit von Windows Autopilot verwendeten Clouddiensten</span><span class="sxs-lookup"><span data-stu-id="88ac2-134">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="88ac2-135">Geräte, auf denen Windows 10, Version 1703 oder höher vorinstalliert ist</span><span class="sxs-lookup"><span data-stu-id="88ac2-135">Devices that are pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="88ac2-136">Auswählen des Windows Autopilot Deployment-Programms für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="88ac2-136">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="88ac2-137">Nach Abschluss der Konfiguration von Windows Autopilot können Sie diese zum Konfigurieren und Anpassen von Windows 10 Enterprise für die Windows-Willkommensseite für Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="88ac2-137">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="88ac2-138">Neue Geräte</span><span class="sxs-lookup"><span data-stu-id="88ac2-138">New devices</span></span>
- <span data-ttu-id="88ac2-139">Geräte, die in Ihrer Organisation bereits eingerichtet wurden</span><span class="sxs-lookup"><span data-stu-id="88ac2-139">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="88ac2-140">Windows Autopilot konfiguriert das Gerät und verbindet es mit Azure AD.</span><span class="sxs-lookup"><span data-stu-id="88ac2-140">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="88ac2-141">Ohne Windows Autopilot müssen neue Geräte manuell konfiguriert werden und mit Azure AD verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="88ac2-141">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="88ac2-142">Gegebenenfalls hilft Ihnen [Schritt 3](windows10-deploy-autopilot.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="88ac2-142">If needed, [Step 3](windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="88ac2-143">Optional: Bei Verwendung von Windows Analytics Device Health für Geräte für die Überwachung von Windows 10 Enterprise-basierten Geräten</span><span class="sxs-lookup"><span data-stu-id="88ac2-143">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="88ac2-p104">Sie haben die Informationen unter „Integrität von Geräten mit Device Health überwachen“ zum Erkennen und Beheben von Problemen mit Auswirkungen auf die Endbenutzer verwendet. Eine schnelle Behebung dieser Art von Problemen kann Ihre Supportkosten reduzieren und Benutzern das IT-Engagement für Windows 10 Enterprise demonstrieren, was eine schnelle Benutzerakzeptanz in Ihrer Organisation fördern kann.</span><span class="sxs-lookup"><span data-stu-id="88ac2-p104">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="88ac2-146">Gegebenenfalls hilft Ihnen [Schritt 4](windows10-enable-windows-analytics.md) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="88ac2-146">If needed, [Step 4](windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="88ac2-147">Erforderlich: Bei Verwendung von Windows Defender Antivirus oder einer eigenen Antischadsoftwarelösung</span><span class="sxs-lookup"><span data-stu-id="88ac2-147">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="88ac2-p105">Sie haben Windows Defender Antivirus oder eine eigene Antischadsoftwarelösung bereitgestellt, um Ihre Geräte unter Windows 10 Enterprise vor Schadsoftware zu schützen. Wenn Sie Windows Defender Antivirus bereitgestellt haben, haben Sie eine Berichterstellungsmethode wie System Center Configuration Manager oder Microsoft Intune implementiert, um Antivirusereignisse und -aktivitäten zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="88ac2-p105">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="88ac2-150">Gegebenenfalls hilft Ihnen [Schritt 5](windows10-enable-security-features.md#windows10-sec-av), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="88ac2-150">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="88ac2-151">Erforderlich: Verwendung von Windows Defender Exploit Guard</span><span class="sxs-lookup"><span data-stu-id="88ac2-151">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="88ac2-152">Sie haben Windows Defender Exploit Guard bereitgestellt, um Ihre Geräte unter Windows 10 Enterprise vor Angriffen zu schützen, und haben eine Berichterstellungsmethode wie System Center Configuration Manager oder Microsoft Intune implementiert, um Angriffsschutzereignisse und -aktivitäten zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="88ac2-152">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="88ac2-153">Gegebenenfalls hilft Ihnen [Schritt 5](windows10-enable-security-features.md#windows10-sec-eg), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="88ac2-153">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="88ac2-154">Erforderlich: Verwendung von Microsoft Defender Advanced Threat Protection (nur Microsoft 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="88ac2-154">Required: You are using Windows Defender Advanced Threat Protection (Microsoft 365 Enterprise E5 only)</span></span>

<span data-ttu-id="88ac2-155">Sie haben Microsoft Defender Advanced Threat Protection (ATP) bereitgestellt, um erweiterte Bedrohungen für Ihr Netzwerk und die Geräte unter Windows 10 Enterprise zu ermitteln, zu analysieren und auf diese zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="88ac2-155">You deployed Windows Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="88ac2-156">Optional haben Sie Microsoft Defender ATP in anderen Tools integriert, um seine Funktionen zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="88ac2-156">Optionally, you have integrated Windows Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="88ac2-157">Gegebenenfalls hilft Ihnen [Schritt 5](windows10-enable-security-features.md#windows10-sec-atp), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="88ac2-157">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="88ac2-158">Ergebnisse und nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="88ac2-158">Results and next steps</span></span>

<span data-ttu-id="88ac2-159">Ihre Windows 10 Enterprise-Infrastruktur ist für die Installation auf neuen Geräten und für direkte Upgrades auf Geräten mit früheren Versionen von Windows bereit, und Sie verwenden die wichtigsten Sicherheitsfeatures von Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="88ac2-159">Your Windows 10 Enterprise infrastructure is ready to begin installation on new devices and upgrades-in-place on devices running previous versions of Windows, and you are using the key security features of Windows 10 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| <span data-ttu-id="88ac2-160">Wenn Sie den Phasen für die Ende-zu-Ende-Bereitstellung von Microsoft 365 Enterprise folgen, folgt als nächstes die Phase [Office 365 ProPlus](office365proplus-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="88ac2-160">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Office 365 ProPlus](office365proplus-infrastructure.md).</span></span> |
