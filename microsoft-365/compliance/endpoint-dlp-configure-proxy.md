---
title: Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen für die Verhinderung von Datenverlust am Endpunkt
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Erfahren Sie Näheres über das Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen für die Verhinderung von Datenverlust am Endpunkt (Data Loss Prevention, DLP).
ms.openlocfilehash: 4d1aa3b75ec0a0720f3d92c847bf7c6cde6d966f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199274"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a><span data-ttu-id="0e843-103">Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen für die Verhinderung von Datenverlust am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0e843-103">Configure device proxy and internet connection settings for Endpoint DLP</span></span>

<span data-ttu-id="0e843-104">Microsoft Endpunkt-DLP stützt sich auf Microsoft Windows-HTTP (WinHTTP) für die Datenmeldung und um mit dem Microsoft Endpunkt-Clouddienst zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="0e843-104">Microsoft Endpoint DLP uses Microsoft Windows HTTP (WinHTTP) to report data and communicate with the Microsoft endpoint cloud service.</span></span> <span data-ttu-id="0e843-105">Das eingebettete Endpunkt-DLP-Feature wird im Systemkontext unter Verwendung des LocalSystem-Kontos ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e843-105">The embedded Endpoint DLP runs in system context using the LocalSystem account.</span></span>

> [!TIP]
> <span data-ttu-id="0e843-106">Organisationen, die Weiterleitungsproxys als Gateway zum Internet verwenden, können mithilfe des Netzwerkschutzes Untersuchungen hinter einem Proxy durchführen.</span><span class="sxs-lookup"><span data-stu-id="0e843-106">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="0e843-107">Weitere Informationen finden Sie unter [Untersuchen von Verbindungsereignissen hinter Weiterleitungsproxys](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span><span class="sxs-lookup"><span data-stu-id="0e843-107">For more information, see [Investigate connection events that occur behind forward proxies](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span></span>

<span data-ttu-id="0e843-108">Die WinHTTP-Konfigurationseinstellung ist unabhängig von den Proxyeinstellungen von Windows Internet (WinINet) für das Browsen im Internet und kann einen Proxyserver nur mithilfe der folgenden Methoden der automatischen Ermittlung erkennen:</span><span class="sxs-lookup"><span data-stu-id="0e843-108">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following auto discovery methods:</span></span>

- <span data-ttu-id="0e843-109">Transparenter Proxy</span><span class="sxs-lookup"><span data-stu-id="0e843-109">Transparent proxy</span></span>
- <span data-ttu-id="0e843-110">Web Proxy Auto-Discovery Protocol (WPAD)</span><span class="sxs-lookup"><span data-stu-id="0e843-110">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

> [!NOTE]
> <span data-ttu-id="0e843-111">Wenn Sie in Ihrer Netzwerktopologie einen transparenten Proxy oder WPAD verwenden, sind keine speziellen Konfigurationseinstellungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0e843-111">If you’re using Transparent proxy or WPAD in your network topology, you don’t need special configuration settings.</span></span> <span data-ttu-id="0e843-112">Weitere Informationen zu Defender für Endpunkt-URL-Ausschlüssen im Proxy finden Sie unter [Aktivieren des Zugriffs auf Endpunkt-DLP-Clouddienst-URLs im Proxy Server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="0e843-112">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="0e843-113">Manuelle Konfiguration von statischen Proxys:</span><span class="sxs-lookup"><span data-stu-id="0e843-113">Manual static proxy configuration:</span></span>
    - <span data-ttu-id="0e843-114">Registrierungsbasierte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0e843-114">Registry-based configuration</span></span>
    - <span data-ttu-id="0e843-115">WinHTTP-Konfiguration mithilfe des netsh-Befehls: nur für Desktops in einer stabilen Topologie geeignet (beispielsweise ein Desktop in einem Unternehmensnetzwerk hinter demselben Proxy)</span><span class="sxs-lookup"><span data-stu-id="0e843-115">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="0e843-116">Manuelles Konfigurieren des Proxyservers mithilfe eines registrierungsbasierten statischen Proxys</span><span class="sxs-lookup"><span data-stu-id="0e843-116">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="0e843-117">Bei Endpunktgeräten, für die keine Verbindung mit dem Internet zulässig ist, müssen Sie einen registrierungsbasierten statischen Proxy konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0e843-117">For endpoint devices that aren't permitted to connect to the Internet, you need to configure a registry-based static proxy.</span></span> <span data-ttu-id="0e843-118">Sie müssen diesen so konfigurieren, dass nur Microsoft Endpunkt-DLP Diagnosedaten melden und mit dem Microsoft Endpunkt-Clouddienst kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="0e843-118">You need to configure this to allow only Microsoft Endpoint DLP to report diagnostic data and communicate with Microsoft endpoint cloud service.</span></span>

<span data-ttu-id="0e843-119">Der statische Proxy kann mithilfe von Gruppenrichtlinien konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="0e843-119">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="0e843-120">Die Gruppenrichtlinien finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="0e843-120">The group policy can be found under:</span></span>

1. <span data-ttu-id="0e843-121">Öffnen Sie **Administrative Vorlagen > Windows-Komponenten > Datensammlung und Vorabversionen > Verwendung authentifizierter Proxys für den Dienst "Benutzererfahrung und Telemetrie im verbundenen Modus" konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="0e843-121">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

2. <span data-ttu-id="0e843-122">Legen Sie dies auf **Aktiviert** fest, und wählen Sie **Verwendung von authentifiziertem Proxy deaktivieren**:</span><span class="sxs-lookup"><span data-stu-id="0e843-122">Set it to **Enabled** and select **Disable Authenticated Proxy usage**:</span></span> 

![Abbildung der Gruppenrichtlinieneinstellungen 1](../media/atp-gpo-proxy1.png)
 
3. <span data-ttu-id="0e843-124">Öffnen Sie **Administrative Vorlagen > Windows-Komponenten > Datensammlung und Vorabversionen > Benutzererfahrung und Telemetrie im verbundenen Modus konfigurieren**:</span><span class="sxs-lookup"><span data-stu-id="0e843-124">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

 <span data-ttu-id="0e843-125">Konfigurieren des Proxys</span><span class="sxs-lookup"><span data-stu-id="0e843-125">Configure the proxy</span></span>

![Abbildung der Gruppenrichtlinieneinstellungen 2](../media/atp-gpo-proxy2.png)

<span data-ttu-id="0e843-127">Die Richtlinie setzt zwei Registrierungswerte (`TelemetryProxyServer` als "REG_SZ" und `DisableEnterpriseAuthProxy` als "REG_DWORD") unter dem Registrierungsschlüssel `HKLM\Software\Policies\Microsoft\Windows\DataCollection` fest.</span><span class="sxs-lookup"><span data-stu-id="0e843-127">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="0e843-128">Der TelemetryProxyServer-Registrierungswert weist dieses Format auf: \<server name or ip\>:\<port\>.</span><span class="sxs-lookup"><span data-stu-id="0e843-128">The registry value TelemetryProxyServer is in this format \<server name or ip\>:\<port\>.</span></span> <span data-ttu-id="0e843-129">Beispiel: **10.0.0.6:8080**.</span><span class="sxs-lookup"><span data-stu-id="0e843-129">For example: **10.0.0.6:8080**</span></span>

<span data-ttu-id="0e843-130">Der Registrierungswert `DisableEnterpriseAuthProxy` sollte auf 1 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0e843-130">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="0e843-131">Manuelles Konfigurieren des Proxyservers mithilfe des netsh-Befehls</span><span class="sxs-lookup"><span data-stu-id="0e843-131">Configure the proxy server manually using "netsh" command</span></span>

<span data-ttu-id="0e843-132">Verwenden Sie den netsh-Befehl, um einen systemweiten statischen Proxy zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0e843-132">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> <span data-ttu-id="0e843-133">Dies wirkt sich auf alle Anwendungen aus, einschließlich Windows-Diensten, die WinHTTP mit Standardproxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e843-133">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span> <span data-ttu-id="0e843-134">- Laptops, die Topologie wechseln (z. B. vom Büro nach Hause), funktionieren mit netsh nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="0e843-134">- Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="0e843-135">Verwenden Sie die registrierungsbasierte Konfiguration für statische Proxys.</span><span class="sxs-lookup"><span data-stu-id="0e843-135">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="0e843-136">Öffnen Sie eine Befehlszeile mit erhöhten Rechten:</span><span class="sxs-lookup"><span data-stu-id="0e843-136">Open an elevated command line:</span></span>
    1. <span data-ttu-id="0e843-137">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="0e843-137">Go to **Start** and type **cmd**</span></span>
    1. <span data-ttu-id="0e843-138">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="0e843-138">Right-click **Command prompt** and select **Run as administrator**.</span></span>
2.  <span data-ttu-id="0e843-139">Geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:</span><span class="sxs-lookup"><span data-stu-id="0e843-139">Enter the following command and press **Enter**:</span></span>

    `netsh winhttp set proxy <proxy>:<port>`

    <span data-ttu-id="0e843-140">Beispiel: **netsh winhttp set proxy 10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="0e843-140">For example: **netsh winhttp set proxy 10.0.0.6:8080**</span></span>

3. <span data-ttu-id="0e843-141">Wenn Sie den WinHTTP-Proxy zurücksetzen möchten, geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:</span><span class="sxs-lookup"><span data-stu-id="0e843-141">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

     `netsh winhttp reset proxy`

<span data-ttu-id="0e843-142">Weitere Informationen hierzu finden Sie unter [netsh-Befehl: Syntax, Kontexte und Formatierung](/windows-server/networking/technologies/netsh/netsh-contexts).</span><span class="sxs-lookup"><span data-stu-id="0e843-142">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>


## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a><span data-ttu-id="0e843-143">Aktivieren des Zugriffs auf Endpunkt-DLP-Clouddienst-URLs im Proxy Server</span><span class="sxs-lookup"><span data-stu-id="0e843-143">Enable access to Endpoint DLP cloud service URLs in the proxy server</span></span>

<span data-ttu-id="0e843-144">Wenn ein Proxy oder eine Firewall den gesamten Datenverkehr standardmäßig blockiert und nur bestimmte Domänen durchlässt, fügen Sie die im herunterladbaren Blatt aufgeführten Domänen der Liste der zulässigen Domänen hinzu.</span><span class="sxs-lookup"><span data-stu-id="0e843-144">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="0e843-145">Diese [herunterladbare Kalkulationstabelle](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) enthält die Dienste und die zugehörigen URLs, mit denen Ihr Netzwerk sich verbinden können muss.</span><span class="sxs-lookup"><span data-stu-id="0e843-145">This [downloadable spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="0e843-146">Sie sollten sicherstellen, dass keine Firewall- oder Netzwerkfilterregeln den Zugriff auf diese URLs verhindern. Andernfalls müssen Sie eine eigene Zulassungsregel dafür erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e843-146">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an allow rule specifically for them.</span></span>

<span data-ttu-id="0e843-147">Wenn bei einem Proxy oder einer Firewall die HTTPS-Überprüfung aktiviert ist (SSL-Inspektion), schließen Sie die in der obigen Tabelle aufgeführten Domänen von der HTTPS-Überprüfung aus.</span><span class="sxs-lookup"><span data-stu-id="0e843-147">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>
<span data-ttu-id="0e843-148">Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, stellen Sie sicher, dass für die zuvor aufgeführten URLs anonymer Datenverkehr zulässig ist (Endpunkt-DLP stellt eine Verbindung vom Systemkontext aus her).</span><span class="sxs-lookup"><span data-stu-id="0e843-148">If a proxy or firewall is blocking anonymous traffic, as Endpoint DLP is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a><span data-ttu-id="0e843-149">Überprüfen der Clientkonnektivität mit Microsoft-Clouddienst-URLs</span><span class="sxs-lookup"><span data-stu-id="0e843-149">Verify client connectivity to Microsoft cloud service URLs</span></span>

<span data-ttu-id="0e843-150">Vergewissern Sie sich, dass die Proxykonfiguration erfolgreich abgeschlossen wurde, dass WinHTTP ermitteln und über den Proxyserver in Ihrer Umgebung kommunizieren kann und dass der Proxyserver Datenverkehr zu Defender für Endpunkt-Dienst-URLs zulässt.</span><span class="sxs-lookup"><span data-stu-id="0e843-150">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="0e843-151">Laden Sie das Tool [MDATP Client Analyzer](https://aka.ms/mdatpanalyzer) auf den PC herunter, auf dem Endpunkt-DLP ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0e843-151">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Endpoint DLP is running on.</span></span>
2. <span data-ttu-id="0e843-152">Extrahieren Sie den Inhalt von MDATPClientAnalyzer.zip auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="0e843-152">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>
3. <span data-ttu-id="0e843-153">Öffnen Sie eine Befehlszeile mit erhöhten Rechten:</span><span class="sxs-lookup"><span data-stu-id="0e843-153">Open an elevated command line:</span></span>
    1. <span data-ttu-id="0e843-154">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="0e843-154">Go to **Start** and type **cmd**.</span></span>
    1. <span data-ttu-id="0e843-155">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="0e843-155">Right-click **Command prompt** and select **Run as administrator**.</span></span>
4.  <span data-ttu-id="0e843-156">Geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:</span><span class="sxs-lookup"><span data-stu-id="0e843-156">Enter the following command and press **Enter**:</span></span>
    
`HardDrivePath\MDATPClientAnalyzer.cmd`

<span data-ttu-id="0e843-157">Ersetzen Sie *HardDrivePath* durch den Pfad, in den das MDATPClientAnalyzer-Tool heruntergeladen wurde (z. B.</span><span class="sxs-lookup"><span data-stu-id="0e843-157">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>
    
<span data-ttu-id="0e843-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**).</span><span class="sxs-lookup"><span data-stu-id="0e843-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span></span>


5.  <span data-ttu-id="0e843-159">Extrahieren Sie die Datei **MDATPClientAnalyzerResult.zip** _, die von dem Tool in dem Ordner erstellt wurde, der in _HardDrivePath\* verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e843-159">Extract the **MDATPClientAnalyzerResult.zip** _ file created by tool in the folder used in the _HardDrivePath\*.</span></span>

6.  <span data-ttu-id="0e843-160">Öffnen Sie **MDATPClientAnalyzerResult.txt**, und vergewissern Sie sich, dass Sie die Schritte zur Proxykonfiguration durchgeführt haben, um die Serverermittlung und den Zugriff auf die Dienst-URLs zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0e843-160">Open **MDATPClientAnalyzerResult.txt** and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>  <span data-ttu-id="0e843-161">Das Tool überprüft die Konnektivität von Defender für Endpunkt-Dienst-URLs, mit denen der Defender für Endpunkt-Client laut Konfiguration interagieren kann.</span><span class="sxs-lookup"><span data-stu-id="0e843-161">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="0e843-162">Anschließend werden die Ergebnisse für jede URL, die potentiell für die Kommunikation mit den Defender für Endpunkt-Diensten verwendet werden kann, in die Datei **MDATPClientAnalyzerResult.txt** gedruckt.</span><span class="sxs-lookup"><span data-stu-id="0e843-162">It then prints the results into the **MDATPClientAnalyzerResult.txt** file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="0e843-163">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0e843-163">For example:</span></span>

    <span data-ttu-id="0e843-164">**Getestete URL: https://xxx.microsoft.com/xxx </br> 1 - Standardproxy: Succeeded (200) </br> 2 - Proxy auto-discovery (WPAD): Succeeded (200)</br> 3 - Proxy deaktiviert: Succeeded (200)</br> 4 - Named proxy: Existiert nicht</br> 5 - Befehlszeilenproxy: Existiert nicht**</span><span class="sxs-lookup"><span data-stu-id="0e843-164">**Testing URL: https://xxx.microsoft.com/xxx </br> 1 - Default proxy: Succeeded (200) </br> 2 - Proxy auto discovery (WPAD): Succeeded (200)</br> 3 - Proxy disabled: Succeeded (200)</br> 4 - Named proxy: Doesn't exist</br> 5 - Command-line proxy: Doesn't exist**</span></span></br>


<span data-ttu-id="0e843-165">Wenn mindestens eine der Verbindungsoptionen einen (200)-Status zurückgibt, kann der Defender für Endpunkt-Client über diese Verbindungsmethode ordnungsgemäß mit der getesteten URL kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="0e843-165">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> 

<span data-ttu-id="0e843-166">Wenn die Ergebnisse der Verbindungsüberprüfung hingegen auf einen Fehler hindeuten, wird ein HTTP-Fehler angezeigt (siehe HTTP-Status-Codes).</span><span class="sxs-lookup"><span data-stu-id="0e843-166">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="0e843-167">Sie können dann die URLs in der Tabelle unter [Aktivieren des Zugriffs auf Endpunkt-DLP-Clouddienst-URLs im Proxy Server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server) verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e843-167">You can then use the URLs in the table shown in [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="0e843-168">Welche URLs Sie verwenden werden, ist von der Region abhängig, die während des Onboarding-Vorgangs ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="0e843-168">The URLs you’ll use will depend on the region selected during the onboarding procedure.</span></span>
[!NOTE]<span data-ttu-id="0e843-169"> Das Tool für die Verbindungsanalyse ist nicht kompatibel mit der ASR-Regel [Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="0e843-169"> The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="0e843-170">Sie müssen diese Regel vorübergehend deaktivieren, um das Verbindungstool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0e843-170">You will need to temporarily disable this rule to run the connectivity tool.</span></span>

[!NOTE] <span data-ttu-id="0e843-171">Wenn der TelemetryProxyServer in der Registrierung oder über eine Gruppenrichtlinie festgelegt ist, wird Defender für Endpunkt auf "Direct" zurückgreifen, wenn der Zugriff auf den definierten Proxy nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="0e843-171">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can’t access the defined proxy.</span></span>
<span data-ttu-id="0e843-172">Verwandte Themen • Onboarding von Windows 10-Geräten • Microsoft Endpunkt-DLP: Onboarding-Probleme behandeln</span><span class="sxs-lookup"><span data-stu-id="0e843-172">Related topics •   Onboard Windows 10 devices •   Troubleshoot Microsoft Endpoint DLP onboarding issues</span></span>





## <a name="see-also"></a><span data-ttu-id="0e843-173">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e843-173">See also</span></span>

- [<span data-ttu-id="0e843-174">Informationen zur Verhinderung von Datenverlust am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0e843-174">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="0e843-175">Verwenden der Verhinderung von Datenverlust am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0e843-175">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="0e843-176">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="0e843-176">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="0e843-177">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="0e843-177">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="0e843-178">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="0e843-178">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="0e843-179">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0e843-179">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="0e843-180">Onboarding-Tools und -Methoden für Windows 10-Computer</span><span class="sxs-lookup"><span data-stu-id="0e843-180">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="0e843-181">Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="0e843-181">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="0e843-182">Azure AD-verbundene Geräte</span><span class="sxs-lookup"><span data-stu-id="0e843-182">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="0e843-183">Herunterladen des auf Chromium basierenden neuen Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0e843-183">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)