<a name="crit-windows10-step1"></a>
### <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="39634-101">Erforderlich: Ihrer Microsoft 365-Domänen wurden hinzugefügt und überprüft</span><span class="sxs-lookup"><span data-stu-id="39634-101">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="39634-102">Der Azure AD-Mandant für Ihre Office 365- und Intune-Abonnements wurde mit Ihren Internetdomänennamen (z. B. „contoso.com“) konfiguriert, statt nur mit einem Domänennamen, der „onmicrosoft.com“ enthält.</span><span class="sxs-lookup"><span data-stu-id="39634-102">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="39634-p101">Wenn dies nicht der Fall ist, werden die Authentifizierungsmethoden eingeschränkt, die Sie konfigurieren können. Pass-Through und Verbundauthentifizierung können zum Beispiel den Domänennamen „onmicrosoft.com“ nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="39634-p101">If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="39634-105">Gegebenenfalls hilft Ihnen [Schritt 1](../windows10-prepare-your-org.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="39634-105">If needed, [Step 1](../windows10-prepare-your-org.md) can help you with this requirement.</span></span>

### <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="39634-106">Optional: Benutzer sind hinzugefügt und lizenziert</span><span class="sxs-lookup"><span data-stu-id="39634-106">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="39634-107">Die entsprechenden Konten für Ihre Benutzer wurden hinzugefügt, entweder direkt zu Ihrem Azure AD-Mandanten für Ihre Office 365- und Intune-Abonnements oder über die Verzeichnissynchronisierung von Ihren lokalen Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="39634-107">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Windows Server AD.</span></span>

<span data-ttu-id="39634-108">Nachdem Sie die Benutzer hinzugefügt haben, können Sie diesen Microsoft 365 Enterprise-Lizenzen zuweisen, entweder direkt als globaler Administrator oder Benutzeradministrator oder automatisch über die Gruppenmitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="39634-108">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="39634-109">Gegebenenfalls hilft Ihnen [Schritt 1](../windows10-prepare-your-org.md) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="39634-109">If needed, [Step 1](../windows10-prepare-your-org.md) can help you with this option.</span></span>

### <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="39634-110">Optional: Diagnosen sind aktiviert</span><span class="sxs-lookup"><span data-stu-id="39634-110">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="39634-111">Sie haben Diagnosedateneinstellungen mithilfe einer Gruppenrichtlinie, Microsoft Intune, des Registrierungs-Editors oder der Eingabeaufforderung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="39634-111">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="39634-112">Gegebenenfalls hilft Ihnen [Schritt 1](../windows10-prepare-your-org.md) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="39634-112">If needed, [Step 1](../windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
### <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="39634-113">Für direktes Upgrade erforderlich: Eine Tasksequenz des Konfigurations-Managers wurde für eine Bereitstellung des Betriebssystems erstellt</span><span class="sxs-lookup"><span data-stu-id="39634-113">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="39634-114">Zum Starten einer Tasksequenz des Konfigurations-Managers für ein direktes Upgrade auf einem Gerät unter Windows 7 oder Windows 8.1 müssen Sie die folgenden Schritte durchführen:</span><span class="sxs-lookup"><span data-stu-id="39634-114">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="39634-115">Festlegen der entsprechenden Windows-Diagnosedatenebene</span><span class="sxs-lookup"><span data-stu-id="39634-115">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="39634-116">Sie haben die Bereitschaft für ein Upgrade von Windows überprüft.</span><span class="sxs-lookup"><span data-stu-id="39634-116">Verify the readiness to upgrade Windows</span></span>
- <span data-ttu-id="39634-117">Sie haben eine Configuration Manager-Tasksequenz erstellt, die eine Gerätesammlung und eine Bereitstellung des Betriebssystems mit einem Windows 10-Betriebssystemimage enthält.</span><span class="sxs-lookup"><span data-stu-id="39634-117">Create a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="39634-p102">Nach Abschluss dieser Schritte können Sie direkte Upgrades auf Geräten durchführen, die für das Upgrade von Windows bereit sind. Um den maximalen Nutzen aus Microsoft 365 Enterprise zu ziehen, führen Sie das Upgrade für so viele Geräte unter Windows 7 und Windows 8.1 wie möglich durch.</span><span class="sxs-lookup"><span data-stu-id="39634-p102">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="39634-p103">Jedes Gerät unter Windows 10 Enterprise kann von den Vorteilen der integrierten Lösung von Microsoft 365 Enterprise profitieren. Die verbleibenden Geräte unter Windows 7 oder Windows 8.1 können die Cloudtechnologien und erweiterten Sicherheitsfunktionen von Windows 10 Enterprise nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="39634-p103">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="39634-122">Gegebenenfalls hilft Ihnen [Schritt 2](../windows10-deploy-inplaceupgrade.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="39634-122">If needed, [Step 2](../windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
### <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="39634-123">Erforderlich für neue Geräte: Windows Autopilot wurde konfiguriert</span><span class="sxs-lookup"><span data-stu-id="39634-123">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="39634-124">Um Windows Autopilot zum Bereitstellen und Anpassen von Windows 10 Enterprise auf einem neuen Gerät zu verwenden, müssen Sie die folgenden Schritte durchführen:</span><span class="sxs-lookup"><span data-stu-id="39634-124">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="39634-125">Sie haben die entsprechende Windows-Diagnosedatenebene festgelegt.</span><span class="sxs-lookup"><span data-stu-id="39634-125">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="39634-126">Sie haben die für Windows Autopilot erforderlichen Schritte abgeschlossen, die Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="39634-126">Completed the prerequisites for Windows Autopilot, which include:</span></span>
   - <span data-ttu-id="39634-127">Geräteregistrierung und Anpassung der Windows-Willkommensseite</span><span class="sxs-lookup"><span data-stu-id="39634-127">Device registration and OOBE customization</span></span>
   - <span data-ttu-id="39634-128">Unternehmensbranding für Windows-Willkommensseite</span><span class="sxs-lookup"><span data-stu-id="39634-128">Company branding for OOBE</span></span>
   - <span data-ttu-id="39634-129">Automatische Registrierung bei MDM in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="39634-129">MDM auto-enrollment in Microsoft Intune</span></span>
   - <span data-ttu-id="39634-130">Netzwerkkonnektivität mit von Windows Autopilot verwendeten Clouddiensten</span><span class="sxs-lookup"><span data-stu-id="39634-130">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="39634-131">Geräte, auf denen Windows 10, Version 1703 oder höher vorinstalliert ist</span><span class="sxs-lookup"><span data-stu-id="39634-131">Devices must be pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="39634-132">Auswählen des Windows Autopilot Deployment-Programms für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="39634-132">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="39634-133">Nach Abschluss der Konfiguration von Windows Autopilot können Sie diese zum Konfigurieren und Anpassen von Windows 10 Enterprise für die Windows-Willkommensseite für Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="39634-133">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="39634-134">Neue Geräte</span><span class="sxs-lookup"><span data-stu-id="39634-134">New devices</span></span>
- <span data-ttu-id="39634-135">Geräte, die in Ihrer Organisation bereits eingerichtet wurden</span><span class="sxs-lookup"><span data-stu-id="39634-135">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="39634-136">Windows Autopilot konfiguriert das Gerät und verbindet es mit Azure AD.</span><span class="sxs-lookup"><span data-stu-id="39634-136">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="39634-137">Ohne Windows Autopilot müssen neue Geräte manuell konfiguriert werden und mit Azure AD verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="39634-137">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="39634-138">Gegebenenfalls hilft Ihnen [Schritt 3](../windows10-deploy-autopilot.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="39634-138">If needed, [Step 3](../windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
### <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="39634-139">Optional: Bei Verwendung von Windows Analytics Device Health für Geräte für die Überwachung von Windows 10 Enterprise-basierten Geräten</span><span class="sxs-lookup"><span data-stu-id="39634-139">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="39634-p104">Sie haben die Informationen unter „Integrität von Geräten mit Device Health überwachen“ zum Erkennen und Beheben von Problemen mit Auswirkungen auf die Endbenutzer verwendet. Eine schnelle Behebung dieser Art von Problemen kann Ihre Supportkosten reduzieren und Benutzern das IT-Engagement für Windows 10 Enterprise demonstrieren, was eine schnelle Benutzerakzeptanz in Ihrer Organisation fördern kann.</span><span class="sxs-lookup"><span data-stu-id="39634-p104">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="39634-142">Gegebenenfalls hilft Ihnen [Schritt 4](../windows10-enable-windows-analytics.md) bei dieser Option.</span><span class="sxs-lookup"><span data-stu-id="39634-142">If needed, [Step 4](../windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
### <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="39634-143">Erforderlich: Bei Verwendung von Windows Defender Antivirus oder einer eigenen Antischadsoftwarelösung</span><span class="sxs-lookup"><span data-stu-id="39634-143">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="39634-p105">Sie haben Windows Defender Antivirus oder eine eigene Antischadsoftwarelösung bereitgestellt, um Ihre Geräte unter Windows 10 Enterprise vor Schadsoftware zu schützen. Wenn Sie Windows Defender Antivirus bereitgestellt haben, haben Sie eine Berichterstellungsmethode wie System Center Configuration Manager oder Microsoft Intune implementiert, um Antivirusereignisse und -aktivitäten zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="39634-p105">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="39634-146">Gegebenenfalls hilft Ihnen [Schritt 5](../windows10-enable-security-features.md#windows10-sec-av), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="39634-146">If needed, [Step 5](../windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
### <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="39634-147">Erforderlich: Verwendung von Windows Defender Exploit Guard</span><span class="sxs-lookup"><span data-stu-id="39634-147">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="39634-148">Sie haben Windows Defender Exploit Guard bereitgestellt, um Ihre Geräte unter Windows 10 Enterprise vor Angriffen zu schützen, und haben eine Berichterstellungsmethode wie System Center Configuration Manager oder Microsoft Intune implementiert, um Angriffsschutzereignisse und -aktivitäten zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="39634-148">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="39634-149">Gegebenenfalls hilft Ihnen [Schritt 5](../windows10-enable-security-features.md#windows10-sec-eg), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="39634-149">If needed, [Step 5](../windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
### <a name="required-you-are-using-windows-defender-advanced-threat-protection-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="39634-150">Erforderlich: Verwendung von Windows Defender Advanced Threat Protection (nur Microsoft 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="39634-150">Required: You are using Windows Defender Advanced Threat Protection (Microsoft 365 Enterprise E5 only)</span></span>

<span data-ttu-id="39634-151">Sie haben Windows Defender Advanced Threat Protection (ATP) bereitgestellt, um erweiterte Bedrohungen für Ihr Netzwerk und die Geräte unter Windows 10 Enterprise zu ermitteln, zu analysieren und auf diese zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="39634-151">You deployed Windows Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="39634-152">Optional haben Sie Windows Defender ATP in anderen Tools integriert, um seine Funktionen zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="39634-152">Optionally, you have integrated Windows Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="39634-153">Gegebenenfalls hilft Ihnen [Schritt 5](../windows10-enable-security-features.md#windows10-sec-atp), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="39634-153">If needed, [Step 5](../windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>
