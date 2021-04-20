---
title: Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen
description: Konfigurieren Sie den Microsoft Defender for Endpoint-Proxy und die Interneteinstellungen, um die Kommunikation mit dem Clouddienst zu ermöglichen.
keywords: configure, proxy, internet, internet connectivity, settings, proxy settings, netsh, winhttp, proxy server
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
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ebfff7721bc61012811a66146079ac9758889594
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893601"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="66cd6-104">Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="66cd6-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="66cd6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="66cd6-105">**Applies to:**</span></span>
- [<span data-ttu-id="66cd6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="66cd6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="66cd6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66cd6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="66cd6-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="66cd6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="66cd6-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="66cd6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="66cd6-110">Für den Defender for Endpoint-Sensor muss Microsoft Windows HTTP (WinHTTP) Sensordaten melden und mit dem Defender for Endpoint-Dienst kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="66cd6-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="66cd6-111">Der eingebettete Defender for Endpoint-Sensor wird im Systemkontext mithilfe des LocalSystem-Kontos ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="66cd6-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="66cd6-112">Der Sensor verwendet Microsoft Windows HTTP Services (WinHTTP), um die Kommunikation mit dem Defender for Endpoint-Clouddienst zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="66cd6-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

>[!TIP]
><span data-ttu-id="66cd6-113">Organisationen, die Weiterleitungsproxys als Gateway zum Internet verwenden, können mithilfe des Netzwerkschutzes Untersuchungen hinter einem Proxy durchführen.</span><span class="sxs-lookup"><span data-stu-id="66cd6-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="66cd6-114">Weitere Informationen finden Sie unter [Untersuchen von Verbindungsereignissen hinter Weiterleitungsproxys](investigate-behind-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="66cd6-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="66cd6-115">Die WinHTTP-Konfigurationseinstellung ist unabhängig von den Windows Internet (WinINet)-Internet-Browserproxyeinstellungen und kann nur mithilfe der folgenden Ermittlungsmethoden einen Proxyserver ermitteln:</span><span class="sxs-lookup"><span data-stu-id="66cd6-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="66cd6-116">Methoden für die automatische Ermittlung:</span><span class="sxs-lookup"><span data-stu-id="66cd6-116">Auto-discovery methods:</span></span>
  - <span data-ttu-id="66cd6-117">Transparenter Proxy</span><span class="sxs-lookup"><span data-stu-id="66cd6-117">Transparent proxy</span></span>
  - <span data-ttu-id="66cd6-118">Web Proxy Auto-Discovery Protocol (WPAD)</span><span class="sxs-lookup"><span data-stu-id="66cd6-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="66cd6-119">Wenn Sie transparenten Proxy oder WPAD in Ihrer Netzwerktopologie verwenden, benötigen Sie keine speziellen Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="66cd6-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="66cd6-120">Weitere Informationen zu Defender for Endpoint-URL-Ausschlüssen im Proxy finden Sie unter [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="66cd6-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="66cd6-121">Manuelle Konfiguration von statischen Proxys:</span><span class="sxs-lookup"><span data-stu-id="66cd6-121">Manual static proxy configuration:</span></span>
  - <span data-ttu-id="66cd6-122">Registrierungsbasierte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="66cd6-122">Registry based configuration</span></span>
  - <span data-ttu-id="66cd6-123">WinHTTP-Konfiguration mithilfe des netsh-Befehls: nur für Desktops in einer stabilen Topologie geeignet (beispielsweise ein Desktop in einem Unternehmensnetzwerk hinter demselben Proxy)</span><span class="sxs-lookup"><span data-stu-id="66cd6-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="66cd6-124">Manuelles Konfigurieren des Proxyservers mithilfe eines registrierungsbasierten statischen Proxys</span><span class="sxs-lookup"><span data-stu-id="66cd6-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="66cd6-125">Konfigurieren Sie einen registrierungsbasierten statischen Proxy, damit nur defender for Endpoint-Sensor Diagnosedaten melden und mit Defender for Endpoint-Diensten kommunizieren kann, wenn ein Computer keine Verbindung mit dem Internet herstellen darf.</span><span class="sxs-lookup"><span data-stu-id="66cd6-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not be permitted to connect to the Internet.</span></span>

> [!NOTE]
> - <span data-ttu-id="66cd6-126">Wenn Sie diese Option unter Windows 10 oder Windows Server 2019 verwenden, wird empfohlen, das folgende (oder höher) Build- und kumulative Updaterollup zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="66cd6-126">When using this option on Windows 10 or Windows Server 2019, it is recommended to have the following (or later) build and cumulative update rollup:</span></span></br>
> <span data-ttu-id="66cd6-127">Windows 10, Version 1909 – https://support.microsoft.com/kb/4601380</span><span class="sxs-lookup"><span data-stu-id="66cd6-127">Windows 10, version 1909 - https://support.microsoft.com/kb/4601380</span></span></br>
> <span data-ttu-id="66cd6-128">Windows 10, Version 2004 – https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="66cd6-128">Windows 10, version 2004 - https://support.microsoft.com/kb/4601382</span></span></br>
> <span data-ttu-id="66cd6-129">Windows 10, Version 20H2 – https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="66cd6-129">Windows 10, version 20H2 - https://support.microsoft.com/kb/4601382</span></span></br>
> <span data-ttu-id="66cd6-130">Diese Updates verbessern die Konnektivität und Zuverlässigkeit des CnC(Command and Control)-Kanals.</span><span class="sxs-lookup"><span data-stu-id="66cd6-130">These updates improve the connectivity and reliability of the CnC (Command and Control) channel.</span></span></br>

<span data-ttu-id="66cd6-131">Der statische Proxy kann mithilfe von Gruppenrichtlinien konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="66cd6-131">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="66cd6-132">Die Gruppenrichtlinien finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="66cd6-132">The group policy can be found under:</span></span>

- <span data-ttu-id="66cd6-133">Administrative Vorlagen > Windows-Komponenten > Datensammlungs- und Vorschaubuilds > Konfigurieren der authentifizierten Proxyverwendung für den verbundenen Benutzererfahrungs- und Telemetriedienst</span><span class="sxs-lookup"><span data-stu-id="66cd6-133">Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
  - <span data-ttu-id="66cd6-134">Legen Sie es **auf Aktiviert,** und wählen **Sie Authentifizierte Proxyverwendung deaktivieren** aus: Abbildung der ![ Gruppenrichtlinieneinstellung1](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="66cd6-134">Set it to **Enabled** and select **Disable Authenticated Proxy usage**: ![Image of Group Policy setting1](images/atp-gpo-proxy1.png)</span></span>
- <span data-ttu-id="66cd6-135">**Administrative Vorlagen > Windows-Komponenten > Datensammlungs- und Vorschaubuilds**> Konfigurieren von verbundenen Benutzererfahrungen und Telemetrie :</span><span class="sxs-lookup"><span data-stu-id="66cd6-135">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>
  - <span data-ttu-id="66cd6-136">Konfigurieren des Proxys:</span><span class="sxs-lookup"><span data-stu-id="66cd6-136">Configure the proxy:</span></span><br>
    <span data-ttu-id="66cd6-137">![Abbildung der Gruppenrichtlinieneinstellung2](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="66cd6-137">![Image of Group Policy setting2](images/atp-gpo-proxy2.png)</span></span>

    <span data-ttu-id="66cd6-138&quot;>Die Richtlinie setzt zwei Registrierungswerte (`TelemetryProxyServer` als &quot;REG_SZ&quot; und `DisableEnterpriseAuthProxy` als &quot;REG_DWORD") unter dem Registrierungsschlüssel `HKLM\Software\Policies\Microsoft\Windows\DataCollection` fest.</span><span class="sxs-lookup"><span data-stu-id="66cd6-138">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

    <span data-ttu-id="66cd6-139">Der Registrierungswert `TelemetryProxyServer` hat das folgende Zeichenfolgenformat:</span><span class="sxs-lookup"><span data-stu-id="66cd6-139">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

    ```text
    <server name or ip>:<port>
    ```

    <span data-ttu-id="66cd6-140">Beispiel: 10.0.0.6:8080.</span><span class="sxs-lookup"><span data-stu-id="66cd6-140">For example: 10.0.0.6:8080</span></span>

    <span data-ttu-id="66cd6-141">Der Registrierungswert `DisableEnterpriseAuthProxy` sollte auf 1 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="66cd6-141">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="66cd6-142">Konfigurieren des Proxyservers manuell mithilfe des Befehls netsh</span><span class="sxs-lookup"><span data-stu-id="66cd6-142">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="66cd6-143">Verwenden Sie den netsh-Befehl, um einen systemweiten statischen Proxy zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="66cd6-143">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="66cd6-144">Dies wirkt sich auf alle Anwendungen aus, einschließlich Windows-Diensten, die WinHTTP mit Standardproxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="66cd6-144">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="66cd6-145">Laptops, die die Topologie ändern (z. B. von Büro zu Haus) können mit netsh nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="66cd6-145">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="66cd6-146">Verwenden Sie die registrierungsbasierte Konfiguration für statische Proxys.</span><span class="sxs-lookup"><span data-stu-id="66cd6-146">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="66cd6-147">Öffnen Sie eine Befehlszeile mit erhöhten Rechten:</span><span class="sxs-lookup"><span data-stu-id="66cd6-147">Open an elevated command-line:</span></span>

    <span data-ttu-id="66cd6-148">a.</span><span class="sxs-lookup"><span data-stu-id="66cd6-148">a.</span></span> <span data-ttu-id="66cd6-149">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="66cd6-149">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="66cd6-150">b.</span><span class="sxs-lookup"><span data-stu-id="66cd6-150">b.</span></span> <span data-ttu-id="66cd6-151">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="66cd6-151">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="66cd6-152">Geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:</span><span class="sxs-lookup"><span data-stu-id="66cd6-152">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="66cd6-153">Beispiel: netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="66cd6-153">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>

<span data-ttu-id="66cd6-154">Geben Sie zum Zurücksetzen des winhttp-Proxys den folgenden Befehl ein, und drücken Sie die **EINGABETASTE.**</span><span class="sxs-lookup"><span data-stu-id="66cd6-154">To reset the winhttp proxy, enter the following command and press **Enter**</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="66cd6-155">Weitere Informationen hierzu finden Sie unter [netsh-Befehl: Syntax, Kontexte und Formatierung](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts).</span><span class="sxs-lookup"><span data-stu-id="66cd6-155">See [Netsh Command Syntax, Contexts, and Formatting](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="66cd6-156">Aktivieren des Zugriffs auf Microsoft Defender for Endpoint-Dienst-URLs auf dem Proxyserver</span><span class="sxs-lookup"><span data-stu-id="66cd6-156">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="66cd6-157">Wenn ein Proxy oder eine Firewall den gesamten Datenverkehr standardmäßig blockiert und nur bestimmte Domänen durchlässt, fügen Sie die im herunterladbaren Blatt aufgeführten Domänen der Liste der zulässigen Domänen hinzu.</span><span class="sxs-lookup"><span data-stu-id="66cd6-157">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="66cd6-158">In der folgenden herunterladbaren Kalkulationstabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit deren Netzwerk eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="66cd6-158">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="66cd6-159">Sie sollten sicherstellen, dass es keine Firewall- oder Netzwerkfilterregeln gibt, die den  Zugriff auf diese URLs verweigern würden, oder Sie müssen möglicherweise eine speziell für sie zulässige Regel erstellen.</span><span class="sxs-lookup"><span data-stu-id="66cd6-159">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>


|<span data-ttu-id="66cd6-160">**Tabellenkalkulation der Domänenliste**</span><span class="sxs-lookup"><span data-stu-id="66cd6-160">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="66cd6-161">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="66cd6-161">**Description**</span></span>|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="66cd6-163">Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme.</span><span class="sxs-lookup"><span data-stu-id="66cd6-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="66cd6-164">Laden Sie die Tabelle hier herunter.</span><span class="sxs-lookup"><span data-stu-id="66cd6-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


<span data-ttu-id="66cd6-165">Wenn bei einem Proxy oder einer Firewall die HTTPS-Überprüfung aktiviert ist (SSL-Inspektion), schließen Sie die in der obigen Tabelle aufgeführten Domänen von der HTTPS-Überprüfung aus.</span><span class="sxs-lookup"><span data-stu-id="66cd6-165">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="66cd6-166">settings-win.data.microsoft.com ist nur erforderlich, wenn Windows 10-Geräte mit Version 1803 oder früher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="66cd6-166">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>


> [!NOTE]
> <span data-ttu-id="66cd6-167">URLs, die v20 enthalten, werden nur benötigt, wenn Windows 10-Geräte mit Version 1803 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="66cd6-167">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="66cd6-168">Ist beispielsweise für ein Windows 10-Gerät mit Version 1803 oder höher erforderlich und in die ```us-v20.events.data.microsoft.com``` Region "US Data Storage" onboarded.</span><span class="sxs-lookup"><span data-stu-id="66cd6-168">For example, ```us-v20.events.data.microsoft.com``` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>


> [!NOTE]
> <span data-ttu-id="66cd6-169">Wenn Sie Microsoft Defender Antivirus in Ihrer Umgebung verwenden, lesen Sie Konfigurieren von Netzwerkverbindungen [mit dem Microsoft Defender Antivirus-Clouddienst](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="66cd6-169">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="66cd6-170">Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, da der Defender for Endpoint-Sensor eine Verbindung aus dem Systemkontext verbindet, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="66cd6-170">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="66cd6-171">Microsoft Monitoring Agent (MMA) – Proxy- und Firewallanforderungen für ältere Versionen von Windows Client oder Windows Server</span><span class="sxs-lookup"><span data-stu-id="66cd6-171">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="66cd6-172">In den folgenden Informationen sind die Proxy- und Firewallkonfigurationsinformationen aufgeführt, die für die Kommunikation mit dem Log Analytics-Agent (häufig als Microsoft Monitoring Agent bezeichnet) für die vorherigen Versionen von Windows wie Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 und Windows Server 2016 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="66cd6-172">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="66cd6-173">Agent-Ressource</span><span class="sxs-lookup"><span data-stu-id="66cd6-173">Agent Resource</span></span>|<span data-ttu-id="66cd6-174">Ports</span><span class="sxs-lookup"><span data-stu-id="66cd6-174">Ports</span></span> |<span data-ttu-id="66cd6-175">Direction</span><span class="sxs-lookup"><span data-stu-id="66cd6-175">Direction</span></span> |<span data-ttu-id="66cd6-176">Umgehen der HTTPS-Überprüfung</span><span class="sxs-lookup"><span data-stu-id="66cd6-176">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|   
|<span data-ttu-id="66cd6-177">\*.ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="66cd6-177">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="66cd6-178">Port 443</span><span class="sxs-lookup"><span data-stu-id="66cd6-178">Port 443</span></span> |<span data-ttu-id="66cd6-179">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="66cd6-179">Outbound</span></span>|<span data-ttu-id="66cd6-180">Ja</span><span class="sxs-lookup"><span data-stu-id="66cd6-180">Yes</span></span> |  
|<span data-ttu-id="66cd6-181">\*.oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="66cd6-181">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="66cd6-182">Port 443</span><span class="sxs-lookup"><span data-stu-id="66cd6-182">Port 443</span></span> |<span data-ttu-id="66cd6-183">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="66cd6-183">Outbound</span></span>|<span data-ttu-id="66cd6-184">Ja</span><span class="sxs-lookup"><span data-stu-id="66cd6-184">Yes</span></span> |  
|<span data-ttu-id="66cd6-185">\*.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="66cd6-185">\*.blob.core.windows.net</span></span> |<span data-ttu-id="66cd6-186">Port 443</span><span class="sxs-lookup"><span data-stu-id="66cd6-186">Port 443</span></span> |<span data-ttu-id="66cd6-187">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="66cd6-187">Outbound</span></span>|<span data-ttu-id="66cd6-188">Ja</span><span class="sxs-lookup"><span data-stu-id="66cd6-188">Yes</span></span> |
|<span data-ttu-id="66cd6-189">\*.azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="66cd6-189">\*.azure-automation.net</span></span> |<span data-ttu-id="66cd6-190">Port 443</span><span class="sxs-lookup"><span data-stu-id="66cd6-190">Port 443</span></span> |<span data-ttu-id="66cd6-191">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="66cd6-191">Outbound</span></span>|<span data-ttu-id="66cd6-192">Ja</span><span class="sxs-lookup"><span data-stu-id="66cd6-192">Yes</span></span> |  


> [!NOTE]
> <span data-ttu-id="66cd6-193">Als cloudbasierte Lösung kann sich der IP-Bereich ändern.</span><span class="sxs-lookup"><span data-stu-id="66cd6-193">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="66cd6-194">Es wird empfohlen, zur Einstellung für die DNS-Auflösung zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="66cd6-194">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="66cd6-195">Bestätigen der Microsoft Monitoring Agent (MMA)-Dienst-URL-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66cd6-195">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="66cd6-196">Lesen Sie die folgenden Anleitungen, um die Platzhalter (\*)-Anforderung für Ihre spezifische Umgebung zu beseitigen, wenn Sie den Microsoft Monitoring Agent (MMA) für frühere Versionen von Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="66cd6-196">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1.  <span data-ttu-id="66cd6-197">Onboarding a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, [see Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and Onboard Windows [servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="66cd6-197">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2.  <span data-ttu-id="66cd6-198">Stellen Sie sicher, dass der Computer erfolgreich über das Microsoft Defender Security Center-Portal berichtet.</span><span class="sxs-lookup"><span data-stu-id="66cd6-198">Ensure the machine is successfully reporting into the Microsoft Defender Security Center portal.</span></span>

3.  <span data-ttu-id="66cd6-199">Führen Sie TestCloudConnection.exe "C:\Program Files\Microsoft Monitoring Agent\Agent" aus, um die Konnektivität zu überprüfen und die erforderlichen URLs für Ihren bestimmten Arbeitsbereich zu sehen.</span><span class="sxs-lookup"><span data-stu-id="66cd6-199">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4.  <span data-ttu-id="66cd6-200">In der Liste der Microsoft Defender for Endpoint-URLs finden Sie die vollständige Liste der Anforderungen für Ihre Region (weitere Informationen finden Sie unter Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span><span class="sxs-lookup"><span data-stu-id="66cd6-200">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

![Abbildung des Administrators in Windows PowerShell](images/admin-powershell.png)

<span data-ttu-id="66cd6-202">Die Platzhalter (\*) in \*.ods.opinsights.azure.com-, \*.oms.opinsights.azure.com- und \*.agentsvc.azure-automation.net-URL-Endpunkten können durch Ihre spezifische Arbeitsbereich-ID ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="66cd6-202">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="66cd6-203">Die Workspace-ID ist spezifisch für Ihre Umgebung und Ihren Arbeitsbereich und ist im Abschnitt Onboarding Ihres Mandanten im Microsoft Defender Security Center-Portal zu finden.</span><span class="sxs-lookup"><span data-stu-id="66cd6-203">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="66cd6-204">Der \*.blob.core.windows.net-URL-Endpunkt kann durch die URLs ersetzt werden, die im Abschnitt "Firewallregel: \*.blob.core.windows.net" der Testergebnisse angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="66cd6-204">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the “Firewall Rule: \*.blob.core.windows.net” section of the test results.</span></span> 

> [!NOTE]
> <span data-ttu-id="66cd6-205">Im Falle des Onboardings über das Azure Security Center (ASC) werden möglicherweise mehrere Arbeitsbereiche verwendet.</span><span class="sxs-lookup"><span data-stu-id="66cd6-205">In the case of onboarding via Azure Security Center (ASC), multiple workspaces maybe used.</span></span> <span data-ttu-id="66cd6-206">Sie müssen das oben beschriebene TestCloudConnection.exe auf einem integrierten Computer aus jedem Arbeitsbereich ausführen (um zu ermitteln, ob änderungen an den URLs \*.blob.core.windows.net zwischen den Arbeitsbereichen vorhanden sind).</span><span class="sxs-lookup"><span data-stu-id="66cd6-206">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a><span data-ttu-id="66cd6-207">Überprüfen der Clientkonnektivität mit Microsoft Defender for Endpoint-Dienst-URLs</span><span class="sxs-lookup"><span data-stu-id="66cd6-207">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>

<span data-ttu-id="66cd6-208">Vergewissern Sie sich, dass die Proxykonfiguration erfolgreich abgeschlossen wurde, dass WinHTTP ermitteln und über den Proxyserver in Ihrer Umgebung kommunizieren kann und dass der Proxyserver Datenverkehr zu Defender für Endpunkt-Dienst-URLs zulässt.</span><span class="sxs-lookup"><span data-stu-id="66cd6-208">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="66cd6-209">Laden Sie [das MDATP Client Analyzer-Tool](https://aka.ms/mdatpanalyzer) auf den PC herunter, auf dem der Defender for Endpoint-Sensor ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="66cd6-209">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="66cd6-210">Extrahieren Sie den Inhalt von MDATPClientAnalyzer.zip auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="66cd6-210">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="66cd6-211">Öffnen Sie eine Befehlszeile mit erhöhten Rechten:</span><span class="sxs-lookup"><span data-stu-id="66cd6-211">Open an elevated command-line:</span></span>

    <span data-ttu-id="66cd6-212">a.</span><span class="sxs-lookup"><span data-stu-id="66cd6-212">a.</span></span> <span data-ttu-id="66cd6-213">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="66cd6-213">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="66cd6-214">b.</span><span class="sxs-lookup"><span data-stu-id="66cd6-214">b.</span></span>  <span data-ttu-id="66cd6-215">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="66cd6-215">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="66cd6-216">Geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:</span><span class="sxs-lookup"><span data-stu-id="66cd6-216">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="66cd6-217">Ersetzen Sie *HardDrivePath* durch den Pfad, in den das MDATPClientAnalyzer-Tool heruntergeladen wurde (z. B.</span><span class="sxs-lookup"><span data-stu-id="66cd6-217">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="66cd6-218">Extrahieren Sie *dieMDATPClientAnalyzerResult.zip,* die vom Tool im Ordner erstellt wurde, der in *HardDrivePath verwendet wird.*</span><span class="sxs-lookup"><span data-stu-id="66cd6-218">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="66cd6-219">Öffnen Sie *MDATPClientAnalyzerResult.txt*, und vergewissern Sie sich, dass Sie die Schritte zur Proxykonfiguration durchgeführt haben, um die Serverermittlung und den Zugriff auf die Dienst-URLs zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="66cd6-219">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span> <br><br>
   <span data-ttu-id="66cd6-220">Das Tool überprüft die Konnektivität von Defender für Endpunkt-Dienst-URLs, mit denen der Defender für Endpunkt-Client laut Konfiguration interagieren kann.</span><span class="sxs-lookup"><span data-stu-id="66cd6-220">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="66cd6-221">Anschließend werden die Ergebnisse für jede URL, die potentiell für die Kommunikation mit den Defender für Endpunkt-Diensten verwendet werden kann, in die Datei *MDATPClientAnalyzerResult.txt* gedruckt.</span><span class="sxs-lookup"><span data-stu-id="66cd6-221">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="66cd6-222">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="66cd6-222">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="66cd6-223">Wenn mindestens eine der Verbindungsoptionen einen (200)-Status zurückgibt, kann der Defender für Endpunkt-Client über diese Verbindungsmethode ordnungsgemäß mit der getesteten URL kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="66cd6-223">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> <br><br>

<span data-ttu-id="66cd6-224">Wenn die Ergebnisse der Verbindungsüberprüfung hingegen auf einen Fehler hindeuten, wird ein HTTP-Fehler angezeigt (siehe HTTP-Status-Codes).</span><span class="sxs-lookup"><span data-stu-id="66cd6-224">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="66cd6-225">Anschließend können Sie die URLs in der Tabelle unter Zugriff auf [Defender for Endpoint-Dienst-URLs auf dem Proxyserver aktivieren verwenden.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="66cd6-225">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="66cd6-226">Die verwendeten URLs hängen von der Region ab, die während des Onboardings ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="66cd6-226">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="66cd6-227"> Das Tool für die Verbindungsanalyse ist nicht kompatibel mit der ASR-Regel [Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="66cd6-227">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="66cd6-228">Sie müssen diese Regel vorübergehend deaktivieren, um das Verbindungstool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="66cd6-228">You will need to temporarily disable this rule to run the connectivity tool.</span></span>


> [!NOTE]
> <span data-ttu-id="66cd6-229">Wenn TelemetryProxyServer festgelegt ist, wird Defender for Endpoint in der Registrierung oder über Eine Gruppenrichtlinie auf "Direct" zurückfallen, wenn er nicht auf den definierten Proxy zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="66cd6-229">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="66cd6-230">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="66cd6-230">Related topics</span></span>

- [<span data-ttu-id="66cd6-231">Onboarding von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="66cd6-231">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="66cd6-232">Behandeln von Problemen beim Onboarding von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="66cd6-232">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
