---
title: Einrichten der Bereitstellung von Microsoft Defender for Endpoint
description: Informationen zum Einrichten der Bereitstellung für Microsoft Defender for Endpoint
keywords: Bereitstellen, Einrichten, Lizenzierungsüberprüfung, Mandantenkonfiguration, Netzwerkkonfiguration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7abf1c9e4115c928ae581da3789270fd8ed036d3
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476310"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="fc73e-104">Einrichten der Bereitstellung von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fc73e-104">Set up Microsoft Defender for Endpoint deployment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fc73e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fc73e-105">**Applies to:**</span></span>
- [<span data-ttu-id="fc73e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="fc73e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fc73e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc73e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fc73e-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="fc73e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fc73e-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="fc73e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="fc73e-110">Die Bereitstellung von Defender for Endpoint ist ein drei phasenweiser Prozess:</span><span class="sxs-lookup"><span data-stu-id="fc73e-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="fc73e-111">[![Bereitstellungsphase – Vorbereiten](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="fc73e-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="fc73e-112">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="fc73e-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | ![Bereitstellungsphase – Setup](images/phase-diagrams/setup.png)<br><span data-ttu-id="fc73e-114">Phase 2: Setup</span><span class="sxs-lookup"><span data-stu-id="fc73e-114">Phase 2: Setup</span></span> | <span data-ttu-id="fc73e-115">[![Bereitstellungsphase – onboard](images/phase-diagrams/onboard.png)](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="fc73e-115">[![deployment phase - onboard](images/phase-diagrams/onboard.png)](onboarding.md)</span></span><br>[<span data-ttu-id="fc73e-116">Phase 3: Onboarding</span><span class="sxs-lookup"><span data-stu-id="fc73e-116">Phase 3: Onboard</span></span>](onboarding.md) |
| ----- | ----- | ----- |
| | <span data-ttu-id="fc73e-117">*Sie sind hier!*</span><span class="sxs-lookup"><span data-stu-id="fc73e-117">*You are here!*</span></span>||

<span data-ttu-id="fc73e-118">Sie befinden sich derzeit in der Einrichtungsphase.</span><span class="sxs-lookup"><span data-stu-id="fc73e-118">You are currently in the set-up phase.</span></span>

<span data-ttu-id="fc73e-119">In diesem Bereitstellungsszenario werden Sie durch die folgenden Schritte geführt:</span><span class="sxs-lookup"><span data-stu-id="fc73e-119">In this deployment scenario, you'll be guided through the steps on:</span></span>
- <span data-ttu-id="fc73e-120">Lizenzierungsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="fc73e-120">Licensing validation</span></span>
- <span data-ttu-id="fc73e-121">Mandantenkonfiguration</span><span class="sxs-lookup"><span data-stu-id="fc73e-121">Tenant configuration</span></span>
- <span data-ttu-id="fc73e-122">Netzwerkkonfiguration</span><span class="sxs-lookup"><span data-stu-id="fc73e-122">Network configuration</span></span>


>[!NOTE]
><span data-ttu-id="fc73e-123">Um Sie durch eine typische Bereitstellung zu führen, wird in diesem Szenario nur die Verwendung von Microsoft Endpoint Configuration Manager beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc73e-123">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="fc73e-124">Defender for Endpoint unterstützt die Verwendung anderer Onboardingtools, diese Szenarien werden jedoch nicht im Bereitstellungshandbuch beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc73e-124">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="fc73e-125">Weitere Informationen finden Sie unter [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="fc73e-125">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="check-license-state"></a><span data-ttu-id="fc73e-126">Überprüfen des Lizenzstatus</span><span class="sxs-lookup"><span data-stu-id="fc73e-126">Check license state</span></span>

<span data-ttu-id="fc73e-127">Die Überprüfung auf den Lizenzstatus und ob er ordnungsgemäß bereitgestellt wurde, kann über das Admin Center oder über das **Microsoft Azure-Portal durchgeführt werden.**</span><span class="sxs-lookup"><span data-stu-id="fc73e-127">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="fc73e-128">Um Ihre Lizenzen anzeigen zu können, wechseln Sie zum **Microsoft Azure-Portal,** und navigieren Sie zum [Microsoft Azure-Portallizenzabschnitt](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span><span class="sxs-lookup"><span data-stu-id="fc73e-128">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Abbildung der Azure-Lizenzierungsseite](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="fc73e-130">Navigieren Sie im Admin Center alternativ zu **Abrechnungsabonnements**  >  .</span><span class="sxs-lookup"><span data-stu-id="fc73e-130">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="fc73e-131">Auf dem Bildschirm werden alle bereitgestellten Lizenzen und deren aktueller **Status angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="fc73e-131">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![Abbildung von Abrechnungslizenzen](images/atp-billing-subscriptions.png)


## <a name="cloud-service-provider-validation"></a><span data-ttu-id="fc73e-133">Überprüfung des Clouddienstanbieters</span><span class="sxs-lookup"><span data-stu-id="fc73e-133">Cloud Service Provider validation</span></span>

<span data-ttu-id="fc73e-134">Um Zugriff darauf zu erhalten, welche Lizenzen für Ihr Unternehmen bereitgestellt werden, und um den Status der Lizenzen zu überprüfen, wechseln Sie zum Admin Center.</span><span class="sxs-lookup"><span data-stu-id="fc73e-134">To gain access into which licenses are provisioned to your company, and to check the state of the licenses, go to the admin center.</span></span>

1. <span data-ttu-id="fc73e-135">Wählen Sie **im Partnerportal** Die Option **Dienste > Office 365 verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="fc73e-135">From the **Partner portal**, select **Administer services > Office 365**.</span></span>

2. <span data-ttu-id="fc73e-136">Wenn Sie auf den **Link Partnerportal** klicken, wird die Option **Admin im** Namen geöffnet, und Sie erhalten Zugriff auf das Customer Admin Center.</span><span class="sxs-lookup"><span data-stu-id="fc73e-136">Clicking on the **Partner portal** link will open the **Admin on behalf** option and will give you access to the customer admin center.</span></span>

   ![Abbildung des O365-Verwaltungsportals](images/atp-O365-admin-portal-customer.png)



## <a name="tenant-configuration"></a><span data-ttu-id="fc73e-138">Mandantenkonfiguration</span><span class="sxs-lookup"><span data-stu-id="fc73e-138">Tenant Configuration</span></span>

<span data-ttu-id="fc73e-139">Beim ersten Zugriff auf Microsoft Defender Security Center ein Assistent, der Sie durch einige erste Schritte führt.</span><span class="sxs-lookup"><span data-stu-id="fc73e-139">When accessing Microsoft Defender Security Center for the first time, a wizard that will guide you through some initial steps.</span></span> <span data-ttu-id="fc73e-140">Am Ende des Setup-Assistenten wird eine dedizierte Cloudinstanz von Defender for Endpoint erstellt.</span><span class="sxs-lookup"><span data-stu-id="fc73e-140">At the end of the setup wizard, there will be a dedicated cloud instance of Defender for Endpoint created.</span></span> <span data-ttu-id="fc73e-141">Die einfachste Methode besteht in der Ausführung dieser Schritte auf einem Windows 10-Clientgerät.</span><span class="sxs-lookup"><span data-stu-id="fc73e-141">The easiest method is to perform these steps from a Windows 10 client device.</span></span>

1. <span data-ttu-id="fc73e-142">Navigieren Sie in einem Webbrowser zu <https://securitycenter.windows.com> .</span><span class="sxs-lookup"><span data-stu-id="fc73e-142">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

    ![Abbildung von Einrichten Ihrer Berechtigungen für Microsoft Defender for Endpoint](images/atp-setup-permissions-wdatp-portal.png)

2. <span data-ttu-id="fc73e-144">Wenn Sie eine TRIAL-Lizenz durchgehen, wechseln Sie zu dem Link ( <https://signup.microsoft.com/Signup?OfferId=6033e4b5-c320-4008-a936-909c2825d83c&dl=WIN_DEF_ATP&pc=xxxxxxx-xxxxxx-xxx-x> )</span><span class="sxs-lookup"><span data-stu-id="fc73e-144">If going through a TRIAL license, go to the link (<https://signup.microsoft.com/Signup?OfferId=6033e4b5-c320-4008-a936-909c2825d83c&dl=WIN_DEF_ATP&pc=xxxxxxx-xxxxxx-xxx-x>)</span></span>

    <span data-ttu-id="fc73e-145">Sobald der Autorisierungsschritt abgeschlossen ist, wird der **Willkommensbildschirm** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc73e-145">Once the authorization step is completed, the **Welcome** screen will be displayed.</span></span>
3. <span data-ttu-id="fc73e-146">Gehen Sie durch die Autorisierungsschritte.</span><span class="sxs-lookup"><span data-stu-id="fc73e-146">Go through the authorization steps.</span></span>

    ![Abbildung des Willkommensbildschirms für die Einrichtung des Portals](images/welcome1.png)

4. <span data-ttu-id="fc73e-148">Richten Sie Einstellungen ein.</span><span class="sxs-lookup"><span data-stu-id="fc73e-148">Set up preferences.</span></span>

   <span data-ttu-id="fc73e-149">**Datenspeicherort:** Es ist wichtig, dass Sie dies ordnungsgemäß einrichten.</span><span class="sxs-lookup"><span data-stu-id="fc73e-149">**Data storage location** - It's important to set this up correctly.</span></span> <span data-ttu-id="fc73e-150">Bestimmen Sie, wo der Kunde hauptsächlich gehostet werden möchte: USA, EU oder Großbritannien.</span><span class="sxs-lookup"><span data-stu-id="fc73e-150">Determine where the customer wants to be primarily hosted: US, EU, or UK.</span></span> <span data-ttu-id="fc73e-151">Sie können den Speicherort nach dieser Einrichtung nicht mehr ändern, und Microsoft übertstrat die Daten nicht von der angegebenen Geolocation.</span><span class="sxs-lookup"><span data-stu-id="fc73e-151">You can't change the location after this set up and Microsoft won't transfer the data from the specified geolocation.</span></span> 

    <span data-ttu-id="fc73e-152">**Datenaufbewahrung** – Der Standardwert ist sechs Monate.</span><span class="sxs-lookup"><span data-stu-id="fc73e-152">**Data retention** - The default is six months.</span></span>

    <span data-ttu-id="fc73e-153">**Aktivieren von Vorschaufeatures** – Der Standardwert ist aktiviert, kann später geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fc73e-153">**Enable preview features** - The default is on, can be changed later.</span></span>

    ![Abbildung des geografischen Standorts in der Einrichtung](images/setup-preferences.png)

5. <span data-ttu-id="fc73e-155">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fc73e-155">Select **Next**.</span></span>

     ![Abbildung der endgültigen Einstellungseinstellung](images/setup-preferences2.png)

6. <span data-ttu-id="fc73e-157">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="fc73e-157">Select **Continue**.</span></span>


## <a name="network-configuration"></a><span data-ttu-id="fc73e-158">Netzwerkkonfiguration</span><span class="sxs-lookup"><span data-stu-id="fc73e-158">Network configuration</span></span>
<span data-ttu-id="fc73e-159">Wenn die Organisation nicht erfordert, dass die Endpunkte einen Proxy für den Zugriff auf das Internet verwenden, überspringen Sie diesen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="fc73e-159">If the organization doesn't require the endpoints to use a Proxy to access the Internet, skip this section.</span></span>

<span data-ttu-id="fc73e-160">Der Microsoft Defender für Endpunkt-Sensor setzt Microsoft Windows HTTP (WinHTTP) voraus, um Sensordaten zu melden und mit dem Microsoft Defender für Endpunkt-Dienst zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="fc73e-160">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="fc73e-161">Der eingebettete Microsoft Defender for Endpoint-Sensor wird im Systemkontext mithilfe des LocalSystem-Kontos ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fc73e-161">The embedded Microsoft Defender for Endpoint sensor runs in the system context using the LocalSystem account.</span></span> <span data-ttu-id="fc73e-162">Der Sensor verwendet Microsoft Windows-HTTP-Dienste (WinHTTP), um die Kommunikation mit dem Microsoft Defender für Endpunkt-Clouddienst zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="fc73e-162">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Microsoft Defender for Endpoint cloud service.</span></span> <span data-ttu-id="fc73e-163">Die WinHTTP-Konfigurationseinstellung ist unabhängig von den Windows Internet (WinINet)-Internet-Browserproxyeinstellungen und kann nur mithilfe der folgenden Ermittlungsmethoden einen Proxyserver ermitteln:</span><span class="sxs-lookup"><span data-stu-id="fc73e-163">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

<span data-ttu-id="fc73e-164">**AutoErmittlungsmethoden:**</span><span class="sxs-lookup"><span data-stu-id="fc73e-164">**Autodiscovery methods:**</span></span>

-   <span data-ttu-id="fc73e-165">Transparenter Proxy</span><span class="sxs-lookup"><span data-stu-id="fc73e-165">Transparent proxy</span></span>

-   <span data-ttu-id="fc73e-166">Webproxy-AutoErmittlungsprotokoll (WPAD)</span><span class="sxs-lookup"><span data-stu-id="fc73e-166">Web Proxy Autodiscovery Protocol (WPAD)</span></span>

<span data-ttu-id="fc73e-167">Wenn in der Netzwerktopologie ein transparenter Proxy oder ein WPAD implementiert wurde, sind keine speziellen Konfigurationseinstellungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fc73e-167">If a Transparent proxy or WPAD has been implemented in the network topology, there is no need for special configuration settings.</span></span> <span data-ttu-id="fc73e-168">Weitere Informationen zu Microsoft Defender for Endpoint-URL-Ausschlüssen im Proxy finden Sie im Abschnitt [Proxydienst-URLs](production-deployment.md#proxy-service-urls) in diesem Dokument für die Liste der URLs zulassen oder unter Konfigurieren von Geräteproxy- und [Internetkonnektivitätseinstellungen.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="fc73e-168">For more information on Microsoft Defender for Endpoint URL exclusions in the proxy, see the [Proxy Service URLs](production-deployment.md#proxy-service-urls) section in this document for the URLs allow list or on [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="fc73e-169">**Manuelle Konfiguration von statischen Proxys:**</span><span class="sxs-lookup"><span data-stu-id="fc73e-169">**Manual static proxy configuration:**</span></span>

-   <span data-ttu-id="fc73e-170">Registrierungsbasierte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="fc73e-170">Registry-based configuration</span></span>

-   <span data-ttu-id="fc73e-171">WinHTTP mit netsh-Befehl konfiguriert</span><span class="sxs-lookup"><span data-stu-id="fc73e-171">WinHTTP configured using netsh command</span></span> <br> <span data-ttu-id="fc73e-172">Nur für Desktops in einer stabilen Topologie geeignet (z. B. ein Desktop in einem Unternehmensnetzwerk hinter demselben Proxy)</span><span class="sxs-lookup"><span data-stu-id="fc73e-172">Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="fc73e-173">Manuelles Konfigurieren des Proxyservers mithilfe eines registrierungsbasierten statischen Proxys</span><span class="sxs-lookup"><span data-stu-id="fc73e-173">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="fc73e-174">Konfigurieren Sie einen registrierungsbasierten statischen Proxy, damit nur der Microsoft Defender for Endpoint-Sensor Diagnosedaten melden und mit Microsoft Defender for Endpoint-Diensten kommunizieren kann, wenn ein Computer keine Verbindung mit dem Internet herstellen darf.</span><span class="sxs-lookup"><span data-stu-id="fc73e-174">Configure a registry-based static proxy to allow only Microsoft Defender for Endpoint sensor to report diagnostic data and communicate with Microsoft Defender for Endpoint services if a computer isn't permitted to connect to the Internet.</span></span> <span data-ttu-id="fc73e-175">Der statische Proxy kann mithilfe von Gruppenrichtlinien konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="fc73e-175">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="fc73e-176">Die Gruppenrichtlinien finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="fc73e-176">The group policy can be found under:</span></span>

 - <span data-ttu-id="fc73e-177">Administrative Vorlagen \> Windows-Komponenten Datensammlungs- und Vorschaubuilds Konfigurieren der authentifizierten Proxyverwendung für den verbundenen \> \> Benutzererfahrungs- und Telemetriedienst</span><span class="sxs-lookup"><span data-stu-id="fc73e-177">Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
     - <span data-ttu-id="fc73e-178">Legen Sie sie auf **Aktiviert,** und wählen **Sie Authentifizierte Proxyverwendung deaktivieren aus.**</span><span class="sxs-lookup"><span data-stu-id="fc73e-178">Set it to **Enabled** and select **Disable Authenticated Proxy usage**</span></span>

1. <span data-ttu-id="fc73e-179">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="fc73e-179">Open the Group Policy Management Console.</span></span>
2. <span data-ttu-id="fc73e-180">Erstellen Sie eine Richtlinie, oder bearbeiten Sie eine vorhandene Richtlinie basierend auf den Organisationspraktiken.</span><span class="sxs-lookup"><span data-stu-id="fc73e-180">Create a policy or edit an existing policy based off the organizational practices.</span></span>
3. <span data-ttu-id="fc73e-181">Bearbeiten Sie die Gruppenrichtlinie, und navigieren Sie zu **Administrative Vorlagen Windows Components Data Collection and Preview Builds Configure \> \> \> Authenticated Proxy usage for the Connected User Experience and Telemetry Service**.</span><span class="sxs-lookup"><span data-stu-id="fc73e-181">Edit the Group Policy and navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**.</span></span> 
    <span data-ttu-id="fc73e-182">![Abbildung der Gruppenrichtlinienkonfiguration](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="fc73e-182">![Image of Group Policy configuration](images/atp-gpo-proxy1.png)</span></span>

4. <span data-ttu-id="fc73e-183">Wählen Sie **Aktiviert** aus.</span><span class="sxs-lookup"><span data-stu-id="fc73e-183">Select **Enabled**.</span></span>
5. <span data-ttu-id="fc73e-184">Wählen **Sie Authentifizierte Proxyverwendung deaktivieren aus.**</span><span class="sxs-lookup"><span data-stu-id="fc73e-184">Select **Disable Authenticated Proxy usage**.</span></span>
   
6. <span data-ttu-id="fc73e-185">Navigieren Sie **zu Administrative Vorlagen \> Windows-Komponenten \> Datensammlung und Vorschaubuilds Konfigurieren \> von verbundenen Benutzererfahrungen und Telemetrie**.</span><span class="sxs-lookup"><span data-stu-id="fc73e-185">Navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure connected user experiences and telemetry**.</span></span>
    <span data-ttu-id="fc73e-186">![Abbildung der Gruppenrichtlinienkonfigurationseinstellung](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="fc73e-186">![Image of Group Policy configuration setting](images/atp-gpo-proxy2.png)</span></span>
7. <span data-ttu-id="fc73e-187">Wählen Sie **Aktiviert** aus.</span><span class="sxs-lookup"><span data-stu-id="fc73e-187">Select **Enabled**.</span></span>
8. <span data-ttu-id="fc73e-188">Geben Sie den **Proxyservernamen ein.**</span><span class="sxs-lookup"><span data-stu-id="fc73e-188">Enter the **Proxy Server Name**.</span></span>

<span data-ttu-id="fc73e-189">Die Richtlinie setzt zwei Registrierungswerte (`TelemetryProxyServer` als "REG_SZ" und `DisableEnterpriseAuthProxy` als "REG_DWORD") unter dem Registrierungsschlüssel `HKLM\Software\Policies\Microsoft\Windows\DataCollection` fest.</span><span class="sxs-lookup"><span data-stu-id="fc73e-189">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="fc73e-190">Der Registrierungswert `TelemetryProxyServer` hat das folgende Zeichenfolgenformat:</span><span class="sxs-lookup"><span data-stu-id="fc73e-190">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

```text
<server name or ip>:<port>
```

<span data-ttu-id="fc73e-191">Beispiel: 10.0.0.6:8080.</span><span class="sxs-lookup"><span data-stu-id="fc73e-191">For example: 10.0.0.6:8080</span></span>

<span data-ttu-id="fc73e-192">Der Registrierungswert `DisableEnterpriseAuthProxy` sollte auf 1 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fc73e-192">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

###  <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="fc73e-193">Konfigurieren des Proxyservers manuell mithilfe des Befehls netsh</span><span class="sxs-lookup"><span data-stu-id="fc73e-193">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="fc73e-194">Verwenden Sie den netsh-Befehl, um einen systemweiten statischen Proxy zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fc73e-194">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="fc73e-195">Dies wirkt sich auf alle Anwendungen aus, einschließlich Windows-Diensten, die WinHTTP mit Standardproxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc73e-195">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="fc73e-196">Laptops, die die Topologie ändern (z. B. von Büro zu Haus) können mit netsh nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc73e-196">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="fc73e-197">Verwenden Sie die registrierungsbasierte Konfiguration für statische Proxys.</span><span class="sxs-lookup"><span data-stu-id="fc73e-197">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="fc73e-198">Öffnen Sie eine Befehlszeile mit erhöhten Rechten:</span><span class="sxs-lookup"><span data-stu-id="fc73e-198">Open an elevated command line:</span></span>

    1. <span data-ttu-id="fc73e-199">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="fc73e-199">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="fc73e-200">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="fc73e-200">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="fc73e-201">Geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:</span><span class="sxs-lookup"><span data-stu-id="fc73e-201">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="fc73e-202">Beispiel: netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="fc73e-202">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>


###  <a name="proxy-configuration-for-down-level-devices"></a><span data-ttu-id="fc73e-203">Proxykonfiguration für Geräte auf ebener ebener Ebene</span><span class="sxs-lookup"><span data-stu-id="fc73e-203">Proxy Configuration for down-level devices</span></span>

<span data-ttu-id="fc73e-204">Down-Level gehören Windows 7 SP1- und Windows 8.1-Arbeitsstationen sowie Windows Server 2008 R2,Windows Server 2012, Windows Server 2012 R2 und Versionen von Windows Server 2016 vor Windows Server CB 1803.</span><span class="sxs-lookup"><span data-stu-id="fc73e-204">Down-Level devices include Windows 7 SP1 and Windows 8.1 workstations as well as Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2, and versions of Windows Server 2016 prior to Windows Server CB 1803.</span></span> <span data-ttu-id="fc73e-205">Für diese Betriebssysteme wird der Proxy als Teil des Microsoft Management Agent konfiguriert, um die Kommunikation vom Endpunkt an Azure zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="fc73e-205">These operating systems will have the proxy configured as part of the Microsoft Management Agent to handle communication from the endpoint to Azure.</span></span> <span data-ttu-id="fc73e-206">Informationen zur Konfiguration eines Proxys auf diesen Geräten finden Sie im Microsoft Management Agent Fast Deployment Guide.</span><span class="sxs-lookup"><span data-stu-id="fc73e-206">Refer to the Microsoft Management Agent Fast Deployment Guide for information on how a proxy is configured on these devices.</span></span>

### <a name="proxy-service-urls"></a><span data-ttu-id="fc73e-207">Proxydienst-URLs</span><span class="sxs-lookup"><span data-stu-id="fc73e-207">Proxy Service URLs</span></span>
<span data-ttu-id="fc73e-208">URLs, die v20 enthalten, werden nur benötigt, wenn Sie Über Windows 10, Version 1803 oder höher, verfügen.</span><span class="sxs-lookup"><span data-stu-id="fc73e-208">URLs that include v20 in them are only needed if you have Windows 10, version 1803 or later devices.</span></span> <span data-ttu-id="fc73e-209">Ist beispielsweise nur erforderlich, wenn sich das ```us-v20.events.data.microsoft.com``` Gerät unter Windows 10, Version 1803 oder höher befindet.</span><span class="sxs-lookup"><span data-stu-id="fc73e-209">For example, ```us-v20.events.data.microsoft.com``` is only needed if the device is on Windows 10, version 1803 or later.</span></span>
 

<span data-ttu-id="fc73e-210">Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, da der Microsoft Defender for Endpoint-Sensor eine Verbindung aus dem Systemkontext verbindet, stellen Sie sicher, dass anonymer Datenverkehr in den aufgeführten URLs zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="fc73e-210">If a proxy or firewall is blocking anonymous traffic, as Microsoft Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the listed URLs.</span></span>

<span data-ttu-id="fc73e-211">In der folgenden herunterladbaren Kalkulationstabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit deren Netzwerk eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="fc73e-211">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="fc73e-212">Stellen Sie sicher, dass es keine Firewall- oder Netzwerkfilterregeln gibt, die  den Zugriff auf diese URLs verweigern würden, oder Sie müssen möglicherweise eine speziell für sie zulässige Regel erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc73e-212">Ensure there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="fc73e-213">**Tabellenkalkulation der Domänenliste**</span><span class="sxs-lookup"><span data-stu-id="fc73e-213">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="fc73e-214">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="fc73e-214">**Description**</span></span>|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="fc73e-216">Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme.</span><span class="sxs-lookup"><span data-stu-id="fc73e-216">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="fc73e-217">Laden Sie die Tabelle hier herunter.</span><span class="sxs-lookup"><span data-stu-id="fc73e-217">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


###  <a name="microsoft-defender-for-endpoint-service-backend-ip-ranges"></a><span data-ttu-id="fc73e-218">Microsoft Defender for Endpoint Service-Back-End-IP-Bereiche</span><span class="sxs-lookup"><span data-stu-id="fc73e-218">Microsoft Defender for Endpoint service backend IP ranges</span></span>

<span data-ttu-id="fc73e-219">Wenn Ihre Netzwerkgeräte KEINE DNS-basierten Regeln unterstützen, verwenden Sie stattdessen IP-Bereiche.</span><span class="sxs-lookup"><span data-stu-id="fc73e-219">If your network devices don't support DNS-based rules, use IP ranges instead.</span></span>

<span data-ttu-id="fc73e-220">Defender for Endpoint ist in der Azure-Cloud aufgebaut und wird in den folgenden Regionen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="fc73e-220">Defender for Endpoint is built in Azure cloud, deployed in the following regions:</span></span>

- <span data-ttu-id="fc73e-221">AzureCloud.eastus</span><span class="sxs-lookup"><span data-stu-id="fc73e-221">AzureCloud.eastus</span></span>
- <span data-ttu-id="fc73e-222">AzureCloud.eastus2</span><span class="sxs-lookup"><span data-stu-id="fc73e-222">AzureCloud.eastus2</span></span>
- <span data-ttu-id="fc73e-223">AzureCloud.westcentralus</span><span class="sxs-lookup"><span data-stu-id="fc73e-223">AzureCloud.westcentralus</span></span>
- <span data-ttu-id="fc73e-224">AzureCloud.northeurope</span><span class="sxs-lookup"><span data-stu-id="fc73e-224">AzureCloud.northeurope</span></span>
- <span data-ttu-id="fc73e-225">AzureCloud.westeurope</span><span class="sxs-lookup"><span data-stu-id="fc73e-225">AzureCloud.westeurope</span></span>
- <span data-ttu-id="fc73e-226">AzureCloud.uksouth</span><span class="sxs-lookup"><span data-stu-id="fc73e-226">AzureCloud.uksouth</span></span>
- <span data-ttu-id="fc73e-227">AzureCloud.ukwest</span><span class="sxs-lookup"><span data-stu-id="fc73e-227">AzureCloud.ukwest</span></span>

<span data-ttu-id="fc73e-228">Die Azure-IP-Bereiche finden Sie unter [Azure IP Ranges and Service Tags – Public Cloud](https://www.microsoft.com/download/details.aspx?id=56519).</span><span class="sxs-lookup"><span data-stu-id="fc73e-228">You can find the Azure IP ranges in [Azure IP Ranges and Service Tags – Public Cloud](https://www.microsoft.com/download/details.aspx?id=56519).</span></span>

> [!NOTE]
> <span data-ttu-id="fc73e-229">Als cloudbasierte Lösung können sich die IP-Adressbereiche ändern.</span><span class="sxs-lookup"><span data-stu-id="fc73e-229">As a cloud-based solution, the IP address ranges can change.</span></span> <span data-ttu-id="fc73e-230">Es wird empfohlen, zu DNS-basierten Regeln zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="fc73e-230">It's recommended you move to DNS-based rules.</span></span>

> [!NOTE]
> <span data-ttu-id="fc73e-231">Wenn Sie ein Us Government-Kunde sind, lesen Sie den entsprechenden Abschnitt auf der [Seite Defender for Endpoint für US Government.](gov.md#service-backend-ip-ranges)</span><span class="sxs-lookup"><span data-stu-id="fc73e-231">If you are a US Government customer, please see the corresponding section in the [Defender for Endpoint for US Government](gov.md#service-backend-ip-ranges) page.</span></span>

## <a name="next-step"></a><span data-ttu-id="fc73e-232">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="fc73e-232">Next step</span></span>

<span data-ttu-id="fc73e-233">![**Phase 3: Onboard**](images/onboard.png)</span><span class="sxs-lookup"><span data-stu-id="fc73e-233">![**Phase 3: Onboard**](images/onboard.png)</span></span> <br><span data-ttu-id="fc73e-234">[Phase 3: Onboarding:](onboarding.md)Onboarding devices to the service so that the Microsoft Defender for Endpoint service can get sensor data from them.</span><span class="sxs-lookup"><span data-stu-id="fc73e-234">[Phase 3: Onboard](onboarding.md): Onboard devices to the service so that the Microsoft Defender for Endpoint service can get sensor data from them.</span></span> 
