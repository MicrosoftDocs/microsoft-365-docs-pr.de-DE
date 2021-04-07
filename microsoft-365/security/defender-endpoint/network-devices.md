---
title: Netzwerkgeräteerkennung und Sicherheitsrisikoverwaltung
description: Sicherheitsempfehlungen und Die Erkennung von Sicherheitsrisiken sind jetzt für Betriebssysteme von Switches, Routern, WLAN-Controllern und Firewalls verfügbar.
keywords: Netzwerkgeräte, Erkennung von Sicherheitslücken bei Netzwerkgeräten, Betriebssysteme von Switches, Routern, WLAN-Controllern und Firewalls
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 06b52e937dd0260a50883c45c36389a6a955ad0e
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604507"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="cc0eb-104">Netzwerkgeräteerkennung und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="cc0eb-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cc0eb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cc0eb-105">**Applies to:**</span></span>

- [<span data-ttu-id="cc0eb-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cc0eb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="cc0eb-107">Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="cc0eb-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="cc0eb-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc0eb-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="cc0eb-109">**Das Scannen und Verwalten von Netzwerkgeräten befindet sich derzeit in der öffentlichen Vorschau.**</span><span class="sxs-lookup"><span data-stu-id="cc0eb-109">**Scanning and managing network devices is currently in public preview**</span></span><br>
> <span data-ttu-id="cc0eb-110">Diese Vorschauversion wird ohne Vereinbarung zum Servicelevel bereitgestellt und wird für Produktionsworkloads nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-110">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="cc0eb-111">Bestimmte Features werden möglicherweise nicht unterstützt oder verfügen möglicherweise über eingeschränkte Funktionen.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-111">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="cc0eb-112">Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint Preview Features](preview.md).</span><span class="sxs-lookup"><span data-stu-id="cc0eb-112">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="cc0eb-113">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="cc0eb-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cc0eb-114">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="cc0eb-115">Netzwerkerkennungsfunktionen sind im  Abschnitt Gerätebestand des Microsoft 365 Security Center und der Microsoft Defender Security Center-Konsolen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-115">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="cc0eb-116">Für jedes Netzwerksegment wird ein bestimmtes Microsoft Defender for Endpoint-Gerät verwendet, um regelmäßig authentifizierte Scans vorkonfigurierter Netzwerkgeräte durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-116">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="cc0eb-117">Nach dem Entdecken bieten die Bedrohungs- und Sicherheitsmanagementfunktionen von Defender for Endpoint integrierte Workflows, um ermittelte Switches, Router, WLAN-Controller, Firewalls und VPN-Gateways zu sichern.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-117">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="cc0eb-118">Sobald die Netzwerkgeräte erkannt und klassifiziert wurden, können Sicherheitsadministratoren die neuesten Sicherheitsempfehlungen erhalten und die kürzlich entdeckten Sicherheitsrisiken für in ihren Organisationen bereitgestellte Netzwerkgeräte überprüfen.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-118">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities foron network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="cc0eb-119">Ansatz</span><span class="sxs-lookup"><span data-stu-id="cc0eb-119">Approach</span></span>

<span data-ttu-id="cc0eb-120">Netzwerkgeräte werden nicht als Standardendpunkte verwaltet, da Defender for Endpoint keinen Sensor in die Netzwerkgeräte selbst integrierte.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-120">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="cc0eb-121">Diese Gerätetypen erfordern einen agentlosen Ansatz, bei dem eine Remotescan die erforderlichen Informationen von den Geräten erhält.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-121">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="cc0eb-122">Je nach Netzwerktopologie und -merkmalen führt ein einzelnes Gerät oder einige wenige In Microsoft Defender for Endpoint integrierte Geräte authentifizierte Scans von Netzwerkgeräten mithilfe von SNMP durch (schreibgeschützt).</span><span class="sxs-lookup"><span data-stu-id="cc0eb-122">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="cc0eb-123">Es gibt zwei Arten von Geräten, die Sie beachten sollten:</span><span class="sxs-lookup"><span data-stu-id="cc0eb-123">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="cc0eb-124">**Bewertungsgerät:** Ein Gerät, das bereits onboarded ist, mit dem Sie die Netzwerkgeräte überprüfen.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-124">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="cc0eb-125">**Netzwerkgeräte:** Die Netzwerkgeräte, die Sie überprüfen und onboarden möchten.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-125">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="cc0eb-126">Sicherheitsrisikoverwaltung für Netzwerkgeräte</span><span class="sxs-lookup"><span data-stu-id="cc0eb-126">Vulnerability management for network devices</span></span> 

<span data-ttu-id="cc0eb-127">Sobald die Netzwerkgeräte erkannt und klassifiziert wurden, können Sicherheitsadministratoren die neuesten Sicherheitsempfehlungen erhalten und kürzlich festgestellte Sicherheitsrisiken auf Netzwerkgeräten überprüfen, die in ihren Organisationen bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-127">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="cc0eb-128">Unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="cc0eb-128">Operating systems that are supported</span></span>

<span data-ttu-id="cc0eb-129">Die folgenden Betriebssysteme werden derzeit unterstützt:</span><span class="sxs-lookup"><span data-stu-id="cc0eb-129">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="cc0eb-130">Cisco IOS, IOS-XE, NX-OS</span><span class="sxs-lookup"><span data-stu-id="cc0eb-130">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="cc0eb-131">Juniper JUNOS</span><span class="sxs-lookup"><span data-stu-id="cc0eb-131">Juniper JUNOS</span></span>
- <span data-ttu-id="cc0eb-132">HPE ArubaOS, Procurve Switch Software</span><span class="sxs-lookup"><span data-stu-id="cc0eb-132">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="cc0eb-133">Palo Alto Networks PAN-OS</span><span class="sxs-lookup"><span data-stu-id="cc0eb-133">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="cc0eb-134">Weitere Netzwerkanbieter und Betriebssysteme werden im Laufe der Zeit hinzugefügt, basierend auf daten, die aus der Kundennutzung gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-134">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="cc0eb-135">Daher wird empfohlen, alle Netzwerkgeräte zu konfigurieren, auch wenn sie nicht in dieser Liste angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-135">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="cc0eb-136">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="cc0eb-136">How to get started</span></span>

<span data-ttu-id="cc0eb-137">Im ersten Schritt wählen Sie ein Gerät aus, auf dem die authentifizierten Netzwerkscans ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-137">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="cc0eb-138">Entscheiden Sie sich für ein integriertes Defender for Endpoint-Gerät (Client oder Server), das über eine Netzwerkverbindung zum Verwaltungsport für die Netzwerkgeräte verfügt, die Sie scannen möchten.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-138">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="cc0eb-139">Der SNMP-Datenverkehr zwischen dem Defender for Endpoint-Bewertungsgerät und den zielgerichteten Netzwerkgeräten muss zulässig sein (z. B. durch die Firewall).</span><span class="sxs-lookup"><span data-stu-id="cc0eb-139">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="cc0eb-140">Entscheiden Sie, welche Netzwerkgeräte auf Sicherheitsrisiken geprüft werden (z. B. ein Cisco Switch oder eine Palo Alto Networks-Firewall).</span><span class="sxs-lookup"><span data-stu-id="cc0eb-140">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="cc0eb-141">Stellen Sie sicher, dass SNMP schreibgeschützt auf allen konfigurierten Netzwerkgeräten aktiviert ist, damit das Defender for Endpoint-Bewertungsgerät die konfigurierten Netzwerkgeräte abfragen kann.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-141">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="cc0eb-142">"SNMP write" ist für die ordnungsgemäße Funktionalität dieses Features nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-142">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="cc0eb-143">Rufen Sie die IP-Adressen der zu scannenden Netzwerkgeräte ab (oder die Subnetze, in denen diese Geräte bereitgestellt werden).</span><span class="sxs-lookup"><span data-stu-id="cc0eb-143">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="cc0eb-144">Rufen Sie die SNMP-Anmeldeinformationen der Netzwerkgeräte ab (z. B. Community String, noAuthNoPriv, authNoPriv, authPriv).</span><span class="sxs-lookup"><span data-stu-id="cc0eb-144">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="cc0eb-145">Sie müssen die Anmeldeinformationen beim Konfigurieren eines neuen Bewertungsauftrags angeben.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-145">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="cc0eb-146">Proxyclientkonfiguration: Außer den Anforderungen des Defender for Endpoint-Geräteproxys ist keine zusätzliche Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-146">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="cc0eb-147">Damit der Netzwerkscanner authentifiziert werden kann und ordnungsgemäß funktioniert, müssen Sie unbedingt die folgenden Domänen/URLs hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="cc0eb-147">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="cc0eb-148">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="cc0eb-148">login.windows.net</span></span>  
    - <span data-ttu-id="cc0eb-149">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="cc0eb-149">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="cc0eb-150">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="cc0eb-150">login.microsoftonline.com</span></span>
    - <span data-ttu-id="cc0eb-151">*.blob.core.windows.net/networkscannerstable/*</span><span class="sxs-lookup"><span data-stu-id="cc0eb-151">*.blob.core.windows.net/networkscannerstable/*</span></span>

    <span data-ttu-id="cc0eb-152">Hinweis: Diese URLs sind nicht in der dokumentierten Liste der zulässigen Datensammlungen von Defender for Endpoint angegeben.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-152">Note: These URLs are not specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="cc0eb-153">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="cc0eb-153">Permissions</span></span>

<span data-ttu-id="cc0eb-154">Zum Konfigurieren von Bewertungsaufträgen ist die folgende Benutzerberechtigungsoption erforderlich: **Verwalten von Sicherheitseinstellungen in Security Center**.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-154">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="cc0eb-155">Sie können die Berechtigung finden, indem Sie zu **Einstellungen**  >  **Rollen .**</span><span class="sxs-lookup"><span data-stu-id="cc0eb-155">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="cc0eb-156">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="cc0eb-156">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="cc0eb-157">Installieren des Netzwerkscanners</span><span class="sxs-lookup"><span data-stu-id="cc0eb-157">Install the network scanner</span></span>

1. <span data-ttu-id="cc0eb-158">Wechseln Sie **zu Microsoft 365 Security**  >  **Settings**  >  **Endpoints**  >  **Assessment jobs** (under 'Network assessments').</span><span class="sxs-lookup"><span data-stu-id="cc0eb-158">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under 'Network assessments').</span></span>
    1. <span data-ttu-id="cc0eb-159">Wechseln Sie im Microsoft Defender Security Center zur Seite Einstellungen > Bewertungsaufträge.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-159">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="cc0eb-160">Laden Sie den Netzwerkscanner herunter, und installieren Sie ihn auf dem dafür vorgesehenen Defender for Endpoint-Bewertungsgerät.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-160">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

![Schaltfläche "Scanner herunterladen"](images/assessment-jobs-download-scanner.png)

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="cc0eb-162">Netzwerkscannerinstallation & Registrierung</span><span class="sxs-lookup"><span data-stu-id="cc0eb-162">Network scanner installation & registration</span></span>

<span data-ttu-id="cc0eb-163">Der Anmeldungsprozess kann auf dem festgelegten Bewertungsgerät selbst oder auf einem anderen Gerät (z. B. Ihrem persönlichen Clientgerät) abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-163">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="cc0eb-164">So führen Sie den Registrierungsprozess für Netzwerkscanner aus:</span><span class="sxs-lookup"><span data-stu-id="cc0eb-164">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="cc0eb-165">Kopieren Und folgen Sie der URL, die in der Befehlszeile angezeigt wird, und verwenden Sie den bereitgestellten Installationscode, um den Registrierungsprozess abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-165">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>
    - <span data-ttu-id="cc0eb-166">Hinweis: Möglicherweise müssen Sie die Eingabeaufforderungseinstellungen ändern, um die URL kopieren zu können.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-166">Note: You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="cc0eb-167">Geben Sie den Code ein, und melden Sie sich mit einem Microsoft-Konto an, das die Defender for Endpoint-Berechtigung "Sicherheitseinstellungen in Security Center verwalten" besitzt.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-167">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="cc0eb-168">Wenn Sie fertig sind, sollte eine Meldung angezeigt werden, in der Sie bestätigen, dass Sie sich angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-168">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="cc0eb-169">Konfigurieren eines neuen Bewertungsauftrags</span><span class="sxs-lookup"><span data-stu-id="cc0eb-169">Configure a new assessment job</span></span>  

<span data-ttu-id="cc0eb-170">Wählen Sie auf der Seite Bewertungsaufträge unter **Einstellungen** die Option **Netzwerkbewertungsauftrag hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="cc0eb-170">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="cc0eb-171">Führen Sie den Einrichtungsvorgang aus, um Netzwerkgeräte zu wählen, die regelmäßig überprüft und dem Gerätebestand hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-171">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="cc0eb-172">Stellen Sie sicher, dass jede IP-Adresse nur einmal auf mehreren Bewertungsgeräten konfiguriert ist, um eine Geräteduplizierung im Netzwerkgerätebestand zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-172">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

![Hinzufügen einer Netzwerkbewertungsauftragsschaltfläche](images/assessment-jobs-add.png)

<span data-ttu-id="cc0eb-174">Hinzufügen eines Auftrags zur Netzwerkbewertung:</span><span class="sxs-lookup"><span data-stu-id="cc0eb-174">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="cc0eb-175">Wählen Sie den Namen "Bewertungsauftrag" und das "Bewertungsgerät", auf dem der Netzwerkscanner installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-175">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="cc0eb-176">Dieses Gerät führt die regelmäßig authentifizierten Scans aus.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-176">This device will perform the periodic authenticated scans.</span></span> 
2. <span data-ttu-id="cc0eb-177">Fügen Sie IP-Adressen der zu scannenden Zielnetzwerkgeräte (oder der Subnetze, in denen diese Geräte bereitgestellt werden) hinzu.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-177">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 
3. <span data-ttu-id="cc0eb-178">Fügen Sie erforderliche SNMP-Anmeldeinformationen der Zielnetzwerkgeräte hinzu.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-178">Add required SNMP credentials of the target network devices.</span></span> 
4. <span data-ttu-id="cc0eb-179">Speichern Sie den neu konfigurierten Netzwerkbewertungsauftrag, um die regelmäßige Netzwerkprüfung zu starten.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-179">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="cc0eb-180">Überprüfen und Hinzufügen von Netzwerkgeräten</span><span class="sxs-lookup"><span data-stu-id="cc0eb-180">Scan and add network devices</span></span>

<span data-ttu-id="cc0eb-181">Während des Einrichtungsprozesses können Sie eine einmal durchgeführte Testprüfung durchführen, um zu überprüfen, dass:</span><span class="sxs-lookup"><span data-stu-id="cc0eb-181">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="cc0eb-182">Es besteht eine Verbindung zwischen dem Defender for Endpoint-Bewertungsgerät und den konfigurierten Zielnetzwerkgeräten.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-182">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="cc0eb-183">Die konfigurierten SNMP-Anmeldeinformationen sind richtig.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-183">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="cc0eb-184">Jedes Bewertungsgerät kann bis zu 1.500 erfolgreiche ÜBERPRÜFUNGen von IP-Adressen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-184">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="cc0eb-185">Wenn Sie beispielsweise 10 verschiedene Subnetze überprüfen, in denen nur 100 IP-Adressen erfolgreiche Ergebnisse zurückgeben, können Sie 1.400 ZUSÄTZLICHE IP-Adressen aus anderen Subnetzen auf demselben Bewertungsgerät überprüfen.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-185">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="cc0eb-186">Wenn mehrere IP-Adressbereiche/Subnetze zu überprüfen sind, dauert es einige Minuten, bis die Testscanergebnisse angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-186">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="cc0eb-187">Ein Testscan ist für bis zu 1.024 Adressen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-187">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="cc0eb-188">Sobald die Ergebnisse angezeigt werden, können Sie auswählen, welche Geräte in die regelmäßige Überprüfung einbezogen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-188">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="cc0eb-189">Wenn Sie die Anzeige der Scanergebnisse überspringen, werden alle konfigurierten IP-Adressen dem Netzwerkbewertungsauftrag hinzugefügt (unabhängig von der Antwort des Geräts).</span><span class="sxs-lookup"><span data-stu-id="cc0eb-189">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="cc0eb-190">Die Scanergebnisse können auch exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-190">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="cc0eb-191">Geräteübersicht</span><span class="sxs-lookup"><span data-stu-id="cc0eb-191">Device inventory</span></span>

<span data-ttu-id="cc0eb-192">Neu ermittelte Geräte werden  auf der Seite Geräteinventar unter der Registerkarte Neue **Netzwerkgeräte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-192">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="cc0eb-193">Es kann bis zu zwei Stunden nach dem Hinzufügen eines Bewertungsauftrags dauern, bis die Geräte aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-193">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

![Abschnitt "Netzwerkgeräte" im Geräteinventar](images/assessment-jobs-device-inventory.png)

## <a name="troubleshooting"></a><span data-ttu-id="cc0eb-195">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="cc0eb-195">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="cc0eb-196">Fehler bei der Installation von Netzwerkscannern</span><span class="sxs-lookup"><span data-stu-id="cc0eb-196">Network scanner installation has failed</span></span>

<span data-ttu-id="cc0eb-197">Stellen Sie sicher, dass die erforderlichen URLs den zulässigen Domänen in den Firewalleinstellungen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-197">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="cc0eb-198">Stellen Sie außerdem sicher, dass Proxyeinstellungen wie unter Konfigurieren von Geräteproxy- und [Internetkonnektivitätseinstellungen beschrieben konfiguriert sind.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="cc0eb-198">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md)</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="cc0eb-199">Die Microsoft.com/devicelogin webseite wurde nicht angezeigt</span><span class="sxs-lookup"><span data-stu-id="cc0eb-199">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="cc0eb-200">Stellen Sie sicher, dass die erforderlichen URLs den zulässigen Domänen in Ihrer Firewall hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-200">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="cc0eb-201">Stellen Sie außerdem sicher, dass Proxyeinstellungen wie unter Konfigurieren von Geräteproxy- und [Internetkonnektivitätseinstellungen beschrieben konfiguriert sind.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="cc0eb-201">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="cc0eb-202">Netzwerkgeräte werden nach mehreren Stunden nicht im Gerätebestand angezeigt</span><span class="sxs-lookup"><span data-stu-id="cc0eb-202">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="cc0eb-203">Die Scanergebnisse sollten einige Stunden nach der ersten Überprüfung aktualisiert werden, die nach Abschluss der Konfiguration des Bewertungsauftrags stattgefunden hat.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-203">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="cc0eb-204">Wenn geräte weiterhin nicht angezeigt werden, überprüfen Sie, ob der Dienst "MdatpNetworkScanService" auf Ihren Bewertungsgeräten ausgeführt wird, auf denen Sie den Netzwerkscanner installiert haben, und führen Sie in der entsprechenden Bewertungsauftragskonfiguration einen "Scan ausführen" aus.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-204">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="cc0eb-205">Wenn Sie nach 5 Minuten immer noch keine Ergebnisse erhalten, starten Sie den Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-205">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="cc0eb-206">Geräte, die zuletzt gesehen wurden, sind länger als 24 Stunden</span><span class="sxs-lookup"><span data-stu-id="cc0eb-206">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="cc0eb-207">Überprüfen Sie, ob der Scanner ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-207">Validate that the scanner is running properly.</span></span> <span data-ttu-id="cc0eb-208">Wechseln Sie dann zur Scandefinition, und wählen Sie "Test ausführen" aus.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-208">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="cc0eb-209">Überprüfen Sie, welche Fehlermeldungen von den relevanten IP-Adressen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-209">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="cc0eb-210">Erforderliche Benutzerberechtigung für die Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="cc0eb-210">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="cc0eb-211">Die Registrierung wurde mit einem Fehler abgeschlossen: "Es sieht so aus, als ob Sie nicht über ausreichende Berechtigungen zum Hinzufügen eines neuen Agents verfügen.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-211">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="cc0eb-212">Die erforderliche Berechtigung ist 'Sicherheitseinstellungen in Security Center verwalten'."</span><span class="sxs-lookup"><span data-stu-id="cc0eb-212">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="cc0eb-213">Drücken Sie eine beliebige Taste, um zu beenden.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-213">Press any key to exit.</span></span>

<span data-ttu-id="cc0eb-214">Bitten Sie Ihren Systemadministrator, Ihnen die erforderlichen Berechtigungen zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-214">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="cc0eb-215">Bitten Sie ein anderes relevantes Mitglied, Ihnen beim Anmeldevorgang zu helfen, indem Sie ihnen den Anmeldecode und den Link bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-215">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="cc0eb-216">Registrierungsprozess schlägt fehl, wenn der bereitgestellte Link in der Befehlszeile beim Registrierungsprozess verwendet wird</span><span class="sxs-lookup"><span data-stu-id="cc0eb-216">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="cc0eb-217">Probieren Sie einen anderen Browser aus, oder kopieren Sie den Anmeldelink und den Code auf ein anderes Gerät.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-217">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="cc0eb-218">Text zu klein oder kann keinen Text aus der Befehlszeile kopieren</span><span class="sxs-lookup"><span data-stu-id="cc0eb-218">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="cc0eb-219">Ändern Sie die Befehlszeileneinstellungen auf Ihrem Gerät, um das Kopieren und Ändern der Textgröße zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="cc0eb-219">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cc0eb-220">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="cc0eb-220">Related articles</span></span>

- [<span data-ttu-id="cc0eb-221">Geräteinventar</span><span class="sxs-lookup"><span data-stu-id="cc0eb-221">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="cc0eb-222">Konfigurieren erweiterter Funktionen</span><span class="sxs-lookup"><span data-stu-id="cc0eb-222">Configure advanced features</span></span>](advanced-features.md)
