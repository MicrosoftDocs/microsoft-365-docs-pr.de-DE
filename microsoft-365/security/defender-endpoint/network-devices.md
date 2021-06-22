---
title: Netzwerkgeräteermittlung und Sicherheitsrisikomanagement
description: Sicherheitsempfehlungen und die Erkennung von Sicherheitsrisiken sind jetzt für Betriebssysteme von Switches, Routern, WLAN-Controllern und Firewalls verfügbar.
keywords: Netzwerkgeräte, Sicherheitsrisikoerkennung für Netzwerkgeräte, Betriebssysteme von Switches, Routern, WLAN-Controllern und Firewalls
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
ms.openlocfilehash: 86b8a37fd6b2d6f9906321b5d74de0e21c45fca3
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062139"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="f7ce0-104">Netzwerkgeräteermittlung und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="f7ce0-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f7ce0-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f7ce0-105">**Applies to:**</span></span>

- [<span data-ttu-id="f7ce0-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f7ce0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f7ce0-107">Bedrohung und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="f7ce0-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f7ce0-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7ce0-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f7ce0-109">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="f7ce0-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f7ce0-110">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="f7ce0-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]  
> <span data-ttu-id="f7ce0-111">Der Am 13.04.2021 veröffentlichte Blog ["Ermittlung von Netzwerkgeräten und Sicherheitsrisikobewertungen"](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) bietet Einblicke in die neuen Funktionen zur \( Ermittlung von \) **Netzwerkgeräten** in Defender für Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-111">The [Network device discovery and vulnerability assessments](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) Blog \(published 04-13-2021\) provides insights into the new **Network device discovery** capabilities in Defender for Endpoint.</span></span> <span data-ttu-id="f7ce0-112">Dieser Artikel enthält eine Übersicht über die Herausforderung, die die Ermittlung von **Netzwerkgeräten** zu bewältigen hat, sowie detaillierte Informationen zu den ersten Schritten mit diesen neuen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-112">This article provides an overview of the challenge that **Network device discovery** is designed to address, and detailed information about how get started using these new capabilities.</span></span>

<span data-ttu-id="f7ce0-113">Netzwerkermittlungsfunktionen sind im Abschnitt **"Geräteinventur"** des Microsoft 365 Security Centers und Microsoft Defender Security Center Konsolen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-113">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="f7ce0-114">Ein bestimmtes Microsoft Defender für Endpunkt-Gerät wird in jedem Netzwerksegment verwendet, um regelmäßige authentifizierte Scans von vorkonfigurierten Netzwerkgeräten durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-114">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="f7ce0-115">Nach der Erkennung bieten die Bedrohungs- und Sicherheitsrisikomanagement-Funktionen von Defender für Endpunkt integrierte Workflows, um ermittelte Switches, Router, WLAN-Controller, Firewalls und VPN-Gateways zu sichern.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-115">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="f7ce0-116">Sobald die Netzwerkgeräte ermittelt und klassifiziert wurden, können Sicherheitsadministratoren die neuesten Sicherheitsempfehlungen erhalten und kürzlich erkannte Sicherheitsrisiken auf Netzwerkgeräten überprüfen, die in ihrer Organisation bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-116">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="f7ce0-117">Ansatz</span><span class="sxs-lookup"><span data-stu-id="f7ce0-117">Approach</span></span>

<span data-ttu-id="f7ce0-118">Netzwerkgeräte werden nicht als Standardendpunkte verwaltet, da Defender für Endpunkt keinen sensor in die Netzwerkgeräte selbst integriert hat.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-118">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="f7ce0-119">Diese Gerätetypen erfordern einen agentlosen Ansatz, bei dem ein Remotescan die erforderlichen Informationen von den Geräten abruft.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-119">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="f7ce0-120">Je nach Netzwerktopologie und -merkmalen führt ein einzelnes Gerät oder einige geräte, die in Microsoft Defender für Endpunkt integriert sind, authentifizierte Scans von Netzwerkgeräten mithilfe von SNMP durch (schreibgeschützt).</span><span class="sxs-lookup"><span data-stu-id="f7ce0-120">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="f7ce0-121">Es gibt zwei Arten von Geräten, die Sie berücksichtigen sollten:</span><span class="sxs-lookup"><span data-stu-id="f7ce0-121">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="f7ce0-122">**Bewertungsgerät:** Ein bereits integriertes Gerät, das Sie zum Scannen der Netzwerkgeräte verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-122">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="f7ce0-123">**Netzwerkgeräte:** Die Netzwerkgeräte, die Sie scannen und integrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-123">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="f7ce0-124">Sicherheitsrisikoverwaltung für Netzwerkgeräte</span><span class="sxs-lookup"><span data-stu-id="f7ce0-124">Vulnerability management for network devices</span></span> 

<span data-ttu-id="f7ce0-125">Sobald die Netzwerkgeräte ermittelt und klassifiziert wurden, können Sicherheitsadministratoren die neuesten Sicherheitsempfehlungen erhalten und kürzlich erkannte Sicherheitsrisiken auf Netzwerkgeräten überprüfen, die in ihrer Organisation bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-125">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="f7ce0-126">Unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="f7ce0-126">Operating systems that are supported</span></span>

<span data-ttu-id="f7ce0-127">Die folgenden Betriebssysteme werden derzeit unterstützt:</span><span class="sxs-lookup"><span data-stu-id="f7ce0-127">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="f7ce0-128">Cisco IOS, IOS-XE, NX-OS</span><span class="sxs-lookup"><span data-stu-id="f7ce0-128">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="f7ce0-129">Juniper JUNOS</span><span class="sxs-lookup"><span data-stu-id="f7ce0-129">Juniper JUNOS</span></span>
- <span data-ttu-id="f7ce0-130">HPE IntuneOS, Procurve Switch Software</span><span class="sxs-lookup"><span data-stu-id="f7ce0-130">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="f7ce0-131">Palo Alto Networks PAN-OS</span><span class="sxs-lookup"><span data-stu-id="f7ce0-131">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="f7ce0-132">Im Laufe der Zeit werden weitere Netzwerkanbieter und Das Betriebssystem hinzugefügt, basierend auf den von der Kundennutzung gesammelten Daten.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-132">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="f7ce0-133">Daher wird empfohlen, alle Ihre Netzwerkgeräte zu konfigurieren, auch wenn sie in dieser Liste nicht angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-133">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="f7ce0-134">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="f7ce0-134">How to get started</span></span>

<span data-ttu-id="f7ce0-135">Der erste Schritt besteht darin, ein Gerät auszuwählen, das die authentifizierten Netzwerküberprüfungen durchführt.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-135">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="f7ce0-136">Entscheiden Sie sich für ein integriertes Defender für Endpunkt-Gerät (Client oder Server), das über eine Netzwerkverbindung mit dem Verwaltungsport für die Netzwerkgeräte verfügt, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-136">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="f7ce0-137">SNMP-Datenverkehr zwischen dem Defender für Endpunkt-Bewertungsgerät und den Zielnetzwerkgeräten muss zulässig sein (z. B. durch die Firewall).</span><span class="sxs-lookup"><span data-stu-id="f7ce0-137">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="f7ce0-138">Entscheiden Sie, welche Netzwerkgeräte auf Sicherheitsrisiken überprüft werden (z. B. ein Cisco-Switch oder eine Firewall von Palo Alto Networks).</span><span class="sxs-lookup"><span data-stu-id="f7ce0-138">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="f7ce0-139">Stellen Sie sicher, dass SNMP schreibgeschützt auf allen konfigurierten Netzwerkgeräten aktiviert ist, damit das Defender für Endpunkt-Bewertungsgerät die konfigurierten Netzwerkgeräte abfragen kann.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-139">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="f7ce0-140">"SNMP-Schreibvorgang" ist für die ordnungsgemäße Funktionalität dieses Features nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-140">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="f7ce0-141">Rufen Sie die IP-Adressen der zu scannenden Netzwerkgeräte ab (oder die Subnetze, in denen diese Geräte bereitgestellt werden).</span><span class="sxs-lookup"><span data-stu-id="f7ce0-141">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="f7ce0-142">Rufen Sie die SNMP-Anmeldeinformationen der Netzwerkgeräte ab (z. B.: Community String, noAuthNoPriv, authNoPriv, authPriv).</span><span class="sxs-lookup"><span data-stu-id="f7ce0-142">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="f7ce0-143">Sie müssen die Anmeldeinformationen angeben, wenn Sie einen neuen Bewertungsauftrag konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-143">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="f7ce0-144">Proxyclientkonfiguration: Außer den Proxyanforderungen des Defender für Endpunkt-Geräts ist keine zusätzliche Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-144">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="f7ce0-145">Damit der Netzwerkscanner authentifiziert werden kann und ordnungsgemäß funktioniert, müssen Sie unbedingt die folgenden Domänen/URLs hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="f7ce0-145">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="f7ce0-146">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="f7ce0-146">login.windows.net</span></span>  
    - <span data-ttu-id="f7ce0-147">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="f7ce0-147">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="f7ce0-148">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f7ce0-148">login.microsoftonline.com</span></span>
    - <span data-ttu-id="f7ce0-149">\*.blob.core.windows.net/networkscannerstable/ \*</span><span class="sxs-lookup"><span data-stu-id="f7ce0-149">\*.blob.core.windows.net/networkscannerstable/ \*</span></span>

    > [!NOTE]
    > <span data-ttu-id="f7ce0-150">Nicht alle URLs werden in der dokumentierten Liste der zulässigen Datensammlungen von Defender für Endpunkt angegeben.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-150">Not all URLs are specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="f7ce0-151">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f7ce0-151">Permissions</span></span>

<span data-ttu-id="f7ce0-152">Zum Konfigurieren von Bewertungsaufträgen ist die folgende Benutzerberechtigungsoption erforderlich: **Verwalten von Sicherheitseinstellungen im Security Center.**</span><span class="sxs-lookup"><span data-stu-id="f7ce0-152">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="f7ce0-153">Sie finden die Berechtigung unter **Einstellungen**  >  **Rollen.**</span><span class="sxs-lookup"><span data-stu-id="f7ce0-153">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="f7ce0-154">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="f7ce0-154">For more information, see [Create and manage roles for role-based access control](user-roles.md).</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="f7ce0-155">Installieren des Netzwerkscanners</span><span class="sxs-lookup"><span data-stu-id="f7ce0-155">Install the network scanner</span></span>

1. <span data-ttu-id="f7ce0-156">Wechseln Sie zu **Microsoft 365**  >  **Sicherheits-Einstellungen**  >  **Endpunktbewertungsaufträgen**  >   (unter **Netzwerkbewertungen).**</span><span class="sxs-lookup"><span data-stu-id="f7ce0-156">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under **Network assessments**).</span></span>
    1. <span data-ttu-id="f7ce0-157">Wechseln Sie im Microsoft Defender Security Center zur Seite Einstellungen > Bewertungsaufträge.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-157">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="f7ce0-158">Laden Sie den Netzwerkscanner herunter, und installieren Sie ihn auf dem angegebenen Defender für Endpunkt-Bewertungsgerät.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-158">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f7ce0-159">![Schaltfläche "Scanner herunterladen"](images/assessment-jobs-download-scanner.png)</span><span class="sxs-lookup"><span data-stu-id="f7ce0-159">![Download scanner button](images/assessment-jobs-download-scanner.png)</span></span>

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="f7ce0-160">Netzwerkscanner-Installation & Registrierung</span><span class="sxs-lookup"><span data-stu-id="f7ce0-160">Network scanner installation & registration</span></span>

<span data-ttu-id="f7ce0-161">Der Anmeldevorgang kann auf dem angegebenen Bewertungsgerät selbst oder auf einem anderen Gerät (z. B. Ihrem persönlichen Clientgerät) abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-161">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="f7ce0-162">So schließen Sie den Registrierungsvorgang für den Netzwerkscanner ab:</span><span class="sxs-lookup"><span data-stu-id="f7ce0-162">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="f7ce0-163">Kopieren Und folgen Sie der URL, die in der Befehlszeile angezeigt wird, und verwenden Sie den bereitgestellten Installationscode, um den Registrierungsprozess abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-163">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f7ce0-164">Möglicherweise müssen Sie die Eingabeaufforderungseinstellungen ändern, um die URL kopieren zu können.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-164">You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="f7ce0-165">Geben Sie den Code ein, und melden Sie sich mit einem Microsoft-Konto an, das über die Defender für Endpunkt-Berechtigung "Verwalten von Sicherheitseinstellungen im Security Center" verfügt.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-165">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="f7ce0-166">Wenn Sie fertig sind, sollte eine Meldung angezeigt werden, die bestätigt, dass Sie sich angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-166">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="f7ce0-167">Konfigurieren eines neuen Bewertungsauftrags</span><span class="sxs-lookup"><span data-stu-id="f7ce0-167">Configure a new assessment job</span></span>  

<span data-ttu-id="f7ce0-168">Wählen Sie auf der Seite "Bewertungsaufträge" in **Einstellungen** die Option **"Netzwerkbewertungsauftrag hinzufügen"** aus.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-168">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="f7ce0-169">Folgen Sie dem Einrichtungsprozess, um Netzwerkgeräte auszuwählen, die regelmäßig überprüft und dem Gerätebestand hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-169">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="f7ce0-170">Um eine Geräteduplizierung im Netzwerkgerätebestand zu verhindern, stellen Sie sicher, dass jede IP-Adresse auf mehreren Bewertungsgeräten nur einmal konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-170">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f7ce0-171">![Schaltfläche "Netzwerkbewertungsauftrag hinzufügen"](images/assessment-jobs-add.png)</span><span class="sxs-lookup"><span data-stu-id="f7ce0-171">![Add network assessment job button](images/assessment-jobs-add.png)</span></span>

<span data-ttu-id="f7ce0-172">Hinzufügen von Netzwerkbewertungsauftragsschritten:</span><span class="sxs-lookup"><span data-stu-id="f7ce0-172">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="f7ce0-173">Wählen Sie den Namen "Bewertungsauftrag" und das "Bewertungsgerät" aus, auf dem der Netzwerkscanner installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-173">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="f7ce0-174">Dieses Gerät führt die regelmäßigen authentifizierten Scans durch.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-174">This device will perform the periodic authenticated scans.</span></span>

2. <span data-ttu-id="f7ce0-175">Fügen Sie IP-Adressen von Zielnetzwerkgeräten hinzu, die gescannt werden sollen (oder die Subnetze, in denen diese Geräte bereitgestellt werden).</span><span class="sxs-lookup"><span data-stu-id="f7ce0-175">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 

3. <span data-ttu-id="f7ce0-176">Fügen Sie die erforderlichen SNMP-Anmeldeinformationen der Zielnetzwerkgeräte hinzu.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-176">Add required SNMP credentials of the target network devices.</span></span> 

4. <span data-ttu-id="f7ce0-177">Speichern Sie den neu konfigurierten Netzwerkbewertungsauftrag, um die regelmäßige Netzwerküberprüfung zu starten.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-177">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="f7ce0-178">Scannen und Hinzufügen von Netzwerkgeräten</span><span class="sxs-lookup"><span data-stu-id="f7ce0-178">Scan and add network devices</span></span>

<span data-ttu-id="f7ce0-179">Während des Einrichtungsprozesses können Sie einen einmaligen Testscan durchführen, um Folgendes zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="f7ce0-179">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="f7ce0-180">Es besteht eine Verbindung zwischen dem Defender für Endpunkt-Bewertungsgerät und den konfigurierten Zielnetzwerkgeräten.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-180">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="f7ce0-181">Die konfigurierten SNMP-Anmeldeinformationen sind korrekt.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-181">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="f7ce0-182">Jedes Bewertungsgerät kann bis zu 1.500 erfolgreiche IP-Adressenüberprüfungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-182">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="f7ce0-183">Wenn Sie beispielsweise 10 verschiedene Subnetze scannen, in denen nur 100 IP-Adressen erfolgreiche Ergebnisse zurückgeben, können Sie 1.400 zusätzliche IP-Adressen aus anderen Subnetzen auf demselben Bewertungsgerät überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-183">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="f7ce0-184">Wenn mehrere IP-Adressbereiche/Subnetze überprüft werden müssen, dauert es mehrere Minuten, bis die Testscanergebnisse angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-184">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="f7ce0-185">Ein Testscan wird für bis zu 1.024 Adressen verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-185">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="f7ce0-186">Sobald die Ergebnisse angezeigt werden, können Sie auswählen, welche Geräte in den regelmäßigen Scan einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-186">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="f7ce0-187">Wenn Sie die Anzeige der Scanergebnisse überspringen, werden alle konfigurierten IP-Adressen dem Netzwerkbewertungsauftrag hinzugefügt (unabhängig von der Antwort des Geräts).</span><span class="sxs-lookup"><span data-stu-id="f7ce0-187">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="f7ce0-188">Die Scanergebnisse können auch exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-188">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="f7ce0-189">Geräteübersicht</span><span class="sxs-lookup"><span data-stu-id="f7ce0-189">Device inventory</span></span>

<span data-ttu-id="f7ce0-190">Neu ermittelte Geräte werden auf der Seite **"Gerätebestand"** auf der Registerkarte "Neue **Netzwerkgeräte"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-190">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="f7ce0-191">Es kann bis zu zwei Stunden nach dem Hinzufügen eines Bewertungsauftrags dauern, bis die Geräte aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-191">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f7ce0-192">![Abschnitt "Netzwerkgeräte" im Gerätebestand](images/assessment-jobs-device-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="f7ce0-192">![Network devices section in the Device inventory](images/assessment-jobs-device-inventory.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f7ce0-193">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="f7ce0-193">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="f7ce0-194">Installation des Netzwerkscanners fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="f7ce0-194">Network scanner installation has failed</span></span>

<span data-ttu-id="f7ce0-195">Stellen Sie sicher, dass die erforderlichen URLs den zulässigen Domänen in den Firewalleinstellungen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-195">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="f7ce0-196">Stellen Sie außerdem sicher, dass Proxyeinstellungen wie unter [Konfigurieren von Geräteproxy- und Internetkonnektivitätseinstellungen](configure-proxy-internet.md)beschrieben konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-196">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="f7ce0-197">Die Microsoft.com/devicelogin Webseite wurde nicht angezeigt</span><span class="sxs-lookup"><span data-stu-id="f7ce0-197">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="f7ce0-198">Stellen Sie sicher, dass die erforderlichen URLs den zulässigen Domänen in Ihrer Firewall hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-198">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="f7ce0-199">Stellen Sie außerdem sicher, dass Proxyeinstellungen wie unter [Konfigurieren von Geräteproxy- und Internetkonnektivitätseinstellungen](configure-proxy-internet.md)beschrieben konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-199">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="f7ce0-200">Netzwerkgeräte werden nach mehreren Stunden nicht im Gerätebestand angezeigt</span><span class="sxs-lookup"><span data-stu-id="f7ce0-200">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="f7ce0-201">Die Scanergebnisse sollten einige Stunden nach der ersten Überprüfung aktualisiert werden, die nach Abschluss der Konfiguration des Bewertungsauftrags durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-201">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="f7ce0-202">Wenn Geräte weiterhin nicht angezeigt werden, überprüfen Sie, ob der Dienst "MdatpNetworkScanService" auf Ihren Bewertungsgeräten ausgeführt wird, auf denen Sie den Netzwerkscanner installiert haben, und führen Sie in der entsprechenden Konfiguration des Bewertungsauftrags eine "Überprüfung ausführen" aus.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-202">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="f7ce0-203">Wenn Sie nach 5 Minuten immer noch keine Ergebnisse erhalten, starten Sie den Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-203">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="f7ce0-204">Geräte, die zuletzt gesehen wurden, sind länger als 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-204">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="f7ce0-205">Überprüfen Sie, ob der Scanner ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-205">Validate that the scanner is running properly.</span></span> <span data-ttu-id="f7ce0-206">Wechseln Sie dann zur Scandefinition, und wählen Sie "Test ausführen" aus.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-206">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="f7ce0-207">Überprüfen Sie, welche Fehlermeldungen von den entsprechenden IP-Adressen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-207">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="f7ce0-208">Erforderliche Bedrohungs- und Sicherheitsrisikomanagement Benutzerberechtigung</span><span class="sxs-lookup"><span data-stu-id="f7ce0-208">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="f7ce0-209">Die Registrierung wurde mit einem Fehler abgeschlossen: "Es sieht so aus, als ob Sie nicht über ausreichende Berechtigungen zum Hinzufügen eines neuen Agents verfügen.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-209">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="f7ce0-210">Die erforderliche Berechtigung lautet "Sicherheitseinstellungen im Security Center verwalten"."</span><span class="sxs-lookup"><span data-stu-id="f7ce0-210">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="f7ce0-211">Drücken Sie eine beliebige Taste, um zu beenden.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-211">Press any key to exit.</span></span>

<span data-ttu-id="f7ce0-212">Bitten Sie Ihren Systemadministrator, Ihnen die erforderlichen Berechtigungen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-212">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="f7ce0-213">Bitten Sie alternativ ein anderes relevantes Mitglied, Ihnen beim Anmeldevorgang zu helfen, indem Sie ihnen den Anmeldecode und den Link zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-213">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="f7ce0-214">Registrierungsvorgang schlägt bei Verwendung des bereitgestellten Links in der Befehlszeile im Registrierungsprozess fehl</span><span class="sxs-lookup"><span data-stu-id="f7ce0-214">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="f7ce0-215">Probieren Sie einen anderen Browser aus, oder kopieren Sie den Anmeldelink und den Code auf ein anderes Gerät.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-215">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="f7ce0-216">Text zu klein oder Text kann nicht aus der Befehlszeile kopiert werden</span><span class="sxs-lookup"><span data-stu-id="f7ce0-216">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="f7ce0-217">Ändern Sie die Befehlszeileneinstellungen auf Ihrem Gerät, um das Kopieren und Ändern der Textgröße zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="f7ce0-217">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f7ce0-218">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="f7ce0-218">Related articles</span></span>

- [<span data-ttu-id="f7ce0-219">Gerätebestand</span><span class="sxs-lookup"><span data-stu-id="f7ce0-219">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="f7ce0-220">Konfigurieren erweiterter Funktionen</span><span class="sxs-lookup"><span data-stu-id="f7ce0-220">Configure advanced features</span></span>](advanced-features.md)
