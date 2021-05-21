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
ms.openlocfilehash: 0de55eefe2f7dd8c9f891fbe126a68a49699ecd3
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594097"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="a0cf4-104">Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="a0cf4-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a0cf4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a0cf4-105">**Applies to:**</span></span>
- [<span data-ttu-id="a0cf4-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a0cf4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a0cf4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a0cf4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a0cf4-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a0cf4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a0cf4-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="a0cf4-110">Für den Defender for Endpoint-Sensor muss Microsoft Windows HTTP (WinHTTP) Sensordaten melden und mit dem Defender for Endpoint-Dienst kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="a0cf4-111">Der eingebettete Defender for Endpoint-Sensor wird im Systemkontext mithilfe des LocalSystem-Kontos ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="a0cf4-112">Der Sensor verwendet Microsoft Windows HTTP Services (WinHTTP), um die Kommunikation mit dem Defender for Endpoint-Clouddienst zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

>[!TIP]
><span data-ttu-id="a0cf4-113">Organisationen, die Weiterleitungsproxys als Gateway zum Internet verwenden, können mithilfe des Netzwerkschutzes Untersuchungen hinter einem Proxy durchführen.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="a0cf4-114">Weitere Informationen finden Sie unter [Untersuchen von Verbindungsereignissen hinter Weiterleitungsproxys](investigate-behind-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="a0cf4-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="a0cf4-115">Die WinHTTP-Konfigurationseinstellung ist unabhängig von den Windows Internet (WinINet) Internet-Browserproxyeinstellungen und kann nur mithilfe der folgenden Ermittlungsmethoden einen Proxyserver ermitteln:</span><span class="sxs-lookup"><span data-stu-id="a0cf4-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="a0cf4-116">Methoden für die automatische Ermittlung:</span><span class="sxs-lookup"><span data-stu-id="a0cf4-116">Auto-discovery methods:</span></span>

  - <span data-ttu-id="a0cf4-117">Transparenter Proxy</span><span class="sxs-lookup"><span data-stu-id="a0cf4-117">Transparent proxy</span></span>

  - <span data-ttu-id="a0cf4-118">Web Proxy Auto-Discovery Protocol (WPAD)</span><span class="sxs-lookup"><span data-stu-id="a0cf4-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0cf4-119">Wenn Sie transparenten Proxy oder WPAD in Ihrer Netzwerktopologie verwenden, benötigen Sie keine speziellen Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="a0cf4-120">Weitere Informationen zu Defender for Endpoint-URL-Ausschlüssen im Proxy finden Sie unter [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="a0cf4-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="a0cf4-121">Manuelle Konfiguration von statischen Proxys:</span><span class="sxs-lookup"><span data-stu-id="a0cf4-121">Manual static proxy configuration:</span></span>

  - <span data-ttu-id="a0cf4-122">Registrierungsbasierte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a0cf4-122">Registry based configuration</span></span>

  - <span data-ttu-id="a0cf4-123">WinHTTP-Konfiguration mithilfe des netsh-Befehls: nur für Desktops in einer stabilen Topologie geeignet (beispielsweise ein Desktop in einem Unternehmensnetzwerk hinter demselben Proxy)</span><span class="sxs-lookup"><span data-stu-id="a0cf4-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="a0cf4-124">Manuelles Konfigurieren des Proxyservers mithilfe eines registrierungsbasierten statischen Proxys</span><span class="sxs-lookup"><span data-stu-id="a0cf4-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="a0cf4-125">Konfigurieren Sie einen registrierungsbasierten statischen Proxy, damit nur der Defender for Endpoint-Sensor Diagnosedaten melden und mit Defender for Endpoint-Diensten kommunizieren kann, wenn ein Computer keine Verbindung mit dem Internet herstellen darf.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not permitted to connect to the Internet.</span></span>

> [!NOTE]
> <span data-ttu-id="a0cf4-126">Wenn Sie diese Option auf Windows 10 oder Windows Server 2019 verwenden, wird empfohlen, das folgende (oder höher) Build- und kumulative Updaterollup zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="a0cf4-126">When using this option on Windows 10 or Windows Server 2019, it is recommended to have the following (or later) build and cumulative update rollup:</span></span>
>
> - <span data-ttu-id="a0cf4-127">Windows 10, Version 1809 oder Windows Server 2019 –https://support.microsoft.com/kb/5001384</span><span class="sxs-lookup"><span data-stu-id="a0cf4-127">Windows 10, version 1809 or Windows Server 2019 - https://support.microsoft.com/kb/5001384</span></span>
> - <span data-ttu-id="a0cf4-128">Windows 10, Version 1909 -https://support.microsoft.com/kb/4601380</span><span class="sxs-lookup"><span data-stu-id="a0cf4-128">Windows 10, version 1909 - https://support.microsoft.com/kb/4601380</span></span>
> - <span data-ttu-id="a0cf4-129">Windows 10, Version 2004 –https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="a0cf4-129">Windows 10, version 2004 - https://support.microsoft.com/kb/4601382</span></span>
> - <span data-ttu-id="a0cf4-130">Windows 10, Version 20H2 -https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="a0cf4-130">Windows 10, version 20H2 - https://support.microsoft.com/kb/4601382</span></span>
>
> <span data-ttu-id="a0cf4-131">Diese Updates verbessern die Konnektivität und Zuverlässigkeit des CnC(Command and Control)-Kanals.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-131">These updates improve the connectivity and reliability of the CnC (Command and Control) channel.</span></span>

<span data-ttu-id="a0cf4-132">Der statische Proxy kann mithilfe von Gruppenrichtlinien konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-132">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="a0cf4-133">Die Gruppenrichtlinien finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="a0cf4-133">The group policy can be found under:</span></span>

- <span data-ttu-id="a0cf4-134">**Administrative Vorlagen > Windows Komponenten > Datensammlungs- und Vorschaubuilds > Konfigurieren der authentifizierten Proxyverwendung für den verbundenen Benutzererfahrungs- und Telemetriedienst**</span><span class="sxs-lookup"><span data-stu-id="a0cf4-134">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

  <span data-ttu-id="a0cf4-135">Legen Sie es auf **Aktiviert,** und wählen **Sie Authentifizierte Proxyverwendung deaktivieren aus.**</span><span class="sxs-lookup"><span data-stu-id="a0cf4-135">Set it to **Enabled** and select **Disable Authenticated Proxy usage**.</span></span>

  ![Abbildung der Gruppenrichtlinieneinstellung1](images/atp-gpo-proxy1.png)

- <span data-ttu-id="a0cf4-137">Administrative Vorlagen > Windows Komponenten > Datensammlung und Vorschaubuilds > Konfigurieren von verbundenen **Benutzererfahrungen und Telemetrie**:</span><span class="sxs-lookup"><span data-stu-id="a0cf4-137">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

  <span data-ttu-id="a0cf4-138">Konfigurieren des Proxys</span><span class="sxs-lookup"><span data-stu-id="a0cf4-138">Configure the proxy</span></span>

  ![Abbildung der Gruppenrichtlinieneinstellung2](images/atp-gpo-proxy2.png)

  <span data-ttu-id="a0cf4-140">Die Richtlinie legt zwei Registrierungswerte als `TelemetryProxyServer` REG_SZ und REG_DWORD unter dem `DisableEnterpriseAuthProxy` Registrierungsschlüssel `HKLM\Software\Policies\Microsoft\Windows\DataCollection` fest.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-140">The policy sets two registry values, `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD, under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

  <span data-ttu-id="a0cf4-141">Der Registrierungswert `TelemetryProxyServer` hat das folgende Zeichenfolgenformat:</span><span class="sxs-lookup"><span data-stu-id="a0cf4-141">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

  ```text
  <server name or ip>:<port>
  ```

  <span data-ttu-id="a0cf4-142">Beispiel: 10.0.0.6:8080.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-142">For example: 10.0.0.6:8080</span></span>

  <span data-ttu-id="a0cf4-143">Der Registrierungswert `DisableEnterpriseAuthProxy` sollte auf 1 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-143">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="a0cf4-144">Konfigurieren des Proxyservers manuell mithilfe des Befehls netsh</span><span class="sxs-lookup"><span data-stu-id="a0cf4-144">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="a0cf4-145">Verwenden Sie den netsh-Befehl, um einen systemweiten statischen Proxy zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-145">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="a0cf4-146">Dies wirkt sich auf alle Anwendungen aus, einschließlich Windows-Diensten, die WinHTTP mit Standardproxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-146">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="a0cf4-147">Laptops, die die Topologie ändern (z. B. von Büro zu Haus) können mit netsh nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-147">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="a0cf4-148">Verwenden Sie die registrierungsbasierte Konfiguration für statische Proxys.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-148">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="a0cf4-149">Öffnen Sie eine Befehlszeile mit erhöhten Rechten:</span><span class="sxs-lookup"><span data-stu-id="a0cf4-149">Open an elevated command-line:</span></span>

   1. <span data-ttu-id="a0cf4-150">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-150">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="a0cf4-151">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-151">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="a0cf4-152">Geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:</span><span class="sxs-lookup"><span data-stu-id="a0cf4-152">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="a0cf4-153">Beispiel: `netsh winhttp set proxy 10.0.0.6:8080`</span><span class="sxs-lookup"><span data-stu-id="a0cf4-153">For example: `netsh winhttp set proxy 10.0.0.6:8080`</span></span>

<span data-ttu-id="a0cf4-154">Wenn Sie den WinHTTP-Proxy zurücksetzen möchten, geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:</span><span class="sxs-lookup"><span data-stu-id="a0cf4-154">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="a0cf4-155">Weitere Informationen hierzu finden Sie unter [netsh-Befehl: Syntax, Kontexte und Formatierung](/windows-server/networking/technologies/netsh/netsh-contexts).</span><span class="sxs-lookup"><span data-stu-id="a0cf4-155">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="a0cf4-156">Aktivieren des Zugriffs auf Microsoft Defender for Endpoint-Dienst-URLs auf dem Proxyserver</span><span class="sxs-lookup"><span data-stu-id="a0cf4-156">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="a0cf4-157">Wenn ein Proxy oder eine Firewall den gesamten Datenverkehr standardmäßig blockiert und nur bestimmte Domänen durchlässt, fügen Sie die im herunterladbaren Blatt aufgeführten Domänen der Liste der zulässigen Domänen hinzu.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-157">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="a0cf4-158">In der folgenden herunterladbaren Kalkulationstabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit deren Netzwerk eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-158">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="a0cf4-159">Sie sollten sicherstellen, dass es keine Firewall- oder Netzwerkfilterregeln gibt, die den  Zugriff auf diese URLs verweigern würden, oder Sie müssen möglicherweise eine speziell für sie zulässige Regel erstellen.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-159">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>


| <span data-ttu-id="a0cf4-160">Tabellenkalkulation der Domänenliste</span><span class="sxs-lookup"><span data-stu-id="a0cf4-160">Spreadsheet of domains list</span></span> | <span data-ttu-id="a0cf4-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0cf4-161">Description</span></span> |
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="a0cf4-163">Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="a0cf4-164">Laden Sie die Tabelle hier herunter.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


<span data-ttu-id="a0cf4-165">Wenn bei einem Proxy oder einer Firewall die HTTPS-Überprüfung aktiviert ist (SSL-Inspektion), schließen Sie die in der obigen Tabelle aufgeführten Domänen von der HTTPS-Überprüfung aus.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-165">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="a0cf4-166">settings-win.data.microsoft.com ist nur erforderlich, wenn Windows 10 Version 1803 oder früher installiert sind.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-166">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>


> [!NOTE]
> <span data-ttu-id="a0cf4-167">URLs, die v20 enthalten, werden nur benötigt, wenn sie Windows 10 Version 1803 oder höher ausführen.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-167">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="a0cf4-168">Ist beispielsweise `us-v20.events.data.microsoft.com` für ein Gerät erforderlich, Windows 10 Version 1803 oder höher ausgeführt wird und in die STORAGE wird.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-168">For example, `us-v20.events.data.microsoft.com` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>


> [!NOTE]
> <span data-ttu-id="a0cf4-169">Wenn Sie Microsoft Defender Antivirus in Ihrer Umgebung verwenden, lesen Sie Konfigurieren von Netzwerkverbindungen [mit dem Microsoft Defender Antivirus Clouddienst](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="a0cf4-169">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="a0cf4-170">Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, da der Defender for Endpoint-Sensor eine Verbindung aus dem Systemkontext verbindet, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-170">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="a0cf4-171">Microsoft Monitoring Agent (MMA) – Proxy- und Firewallanforderungen für ältere Versionen von Windows client oder Windows Server</span><span class="sxs-lookup"><span data-stu-id="a0cf4-171">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="a0cf4-172">In den folgenden Informationen sind die Proxy- und Firewallkonfigurationsinformationen aufgeführt, die für die Kommunikation mit dem Log Analytics-Agent (häufig als Microsoft Monitoring Agent bezeichnet) für die vorherigen Versionen von Windows wie Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 und Windows Server 2016 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-172">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="a0cf4-173">Agent-Ressource</span><span class="sxs-lookup"><span data-stu-id="a0cf4-173">Agent Resource</span></span>|<span data-ttu-id="a0cf4-174">Ports</span><span class="sxs-lookup"><span data-stu-id="a0cf4-174">Ports</span></span> |<span data-ttu-id="a0cf4-175">Direction</span><span class="sxs-lookup"><span data-stu-id="a0cf4-175">Direction</span></span> |<span data-ttu-id="a0cf4-176">Umgehen der HTTPS-Überprüfung</span><span class="sxs-lookup"><span data-stu-id="a0cf4-176">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|   
|<span data-ttu-id="a0cf4-177">\*.ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="a0cf4-177">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="a0cf4-178">Port 443</span><span class="sxs-lookup"><span data-stu-id="a0cf4-178">Port 443</span></span> |<span data-ttu-id="a0cf4-179">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="a0cf4-179">Outbound</span></span>|<span data-ttu-id="a0cf4-180">Ja</span><span class="sxs-lookup"><span data-stu-id="a0cf4-180">Yes</span></span> |  
|<span data-ttu-id="a0cf4-181">\*.oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="a0cf4-181">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="a0cf4-182">Port 443</span><span class="sxs-lookup"><span data-stu-id="a0cf4-182">Port 443</span></span> |<span data-ttu-id="a0cf4-183">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="a0cf4-183">Outbound</span></span>|<span data-ttu-id="a0cf4-184">Ja</span><span class="sxs-lookup"><span data-stu-id="a0cf4-184">Yes</span></span> |  
|<span data-ttu-id="a0cf4-185">\*.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="a0cf4-185">\*.blob.core.windows.net</span></span> |<span data-ttu-id="a0cf4-186">Port 443</span><span class="sxs-lookup"><span data-stu-id="a0cf4-186">Port 443</span></span> |<span data-ttu-id="a0cf4-187">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="a0cf4-187">Outbound</span></span>|<span data-ttu-id="a0cf4-188">Ja</span><span class="sxs-lookup"><span data-stu-id="a0cf4-188">Yes</span></span> |
|<span data-ttu-id="a0cf4-189">\*.azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="a0cf4-189">\*.azure-automation.net</span></span> |<span data-ttu-id="a0cf4-190">Port 443</span><span class="sxs-lookup"><span data-stu-id="a0cf4-190">Port 443</span></span> |<span data-ttu-id="a0cf4-191">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="a0cf4-191">Outbound</span></span>|<span data-ttu-id="a0cf4-192">Ja</span><span class="sxs-lookup"><span data-stu-id="a0cf4-192">Yes</span></span> |  


> [!NOTE]
> <span data-ttu-id="a0cf4-193">Als cloudbasierte Lösung kann sich der IP-Bereich ändern.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-193">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="a0cf4-194">Es wird empfohlen, zur Einstellung für die DNS-Auflösung zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-194">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="a0cf4-195">Bestätigen Microsoft Monitoring Agent (MMA)-Dienst-URL-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0cf4-195">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="a0cf4-196">Lesen Sie die folgenden Anleitungen, um die Platzhalter (\*)-Anforderung für Ihre spezifische Umgebung zu beseitigen, wenn Sie das Microsoft Monitoring Agent (MMA) für frühere Versionen von Windows.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-196">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1.  <span data-ttu-id="a0cf4-197">Onboarding a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, [see Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and Onboard Windows [servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="a0cf4-197">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2.  <span data-ttu-id="a0cf4-198">Stellen Sie sicher, dass der Computer erfolgreich im Microsoft Defender Security Center meldet.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-198">Ensure the machine is successfully reporting into the Microsoft Defender Security Center portal.</span></span>

3.  <span data-ttu-id="a0cf4-199">Führen Sie TestCloudConnection.exe "C:\Program Files\Microsoft Monitoring Agent\Agent" aus, um die Verbindung zu überprüfen und die erforderlichen URLs für Ihren bestimmten Arbeitsbereich zu sehen.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-199">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4.  <span data-ttu-id="a0cf4-200">In der Liste der Microsoft Defender for Endpoint-URLs finden Sie die vollständige Liste der Anforderungen für Ihre Region (weitere Informationen finden Sie unter Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span><span class="sxs-lookup"><span data-stu-id="a0cf4-200">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

    ![Abbildung des Administrators in Windows PowerShell](images/admin-powershell.png)

<span data-ttu-id="a0cf4-202">Die Platzhalter (\*) in \*.ods.opinsights.azure.com-, \*.oms.opinsights.azure.com- und \*.agentsvc.azure-automation.net-URL-Endpunkten können durch Ihre spezifische Arbeitsbereich-ID ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-202">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="a0cf4-203">Die Arbeitsbereichs-ID ist für Ihre Umgebung und Ihren Arbeitsbereich spezifisch und befindet sich im Abschnitt Onboarding Ihres Mandanten im Microsoft Defender Security Center Portal.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-203">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="a0cf4-204">Der \*.blob.core.windows.net-URL-Endpunkt kann durch die URLs ersetzt werden, die im Abschnitt "Firewallregel: \*.blob.core.windows.net" der Testergebnisse angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-204">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the “Firewall Rule: \*.blob.core.windows.net” section of the test results.</span></span> 

> [!NOTE]
> <span data-ttu-id="a0cf4-205">Im Falle des Onboardings über Azure Defender werden möglicherweise mehrere Arbeitsbereiche verwendet.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-205">In the case of onboarding via Azure Defender, multiple workspaces maybe used.</span></span> <span data-ttu-id="a0cf4-206">Sie müssen das oben beschriebene TestCloudConnection.exe auf einem integrierten Computer aus jedem Arbeitsbereich ausführen (um zu ermitteln, ob änderungen an den URLs \*.blob.core.windows.net zwischen den Arbeitsbereichen vorhanden sind).</span><span class="sxs-lookup"><span data-stu-id="a0cf4-206">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a><span data-ttu-id="a0cf4-207">Überprüfen der Clientkonnektivität mit Microsoft Defender for Endpoint-Dienst-URLs</span><span class="sxs-lookup"><span data-stu-id="a0cf4-207">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>

<span data-ttu-id="a0cf4-208">Vergewissern Sie sich, dass die Proxykonfiguration erfolgreich abgeschlossen wurde, dass WinHTTP ermitteln und über den Proxyserver in Ihrer Umgebung kommunizieren kann und dass der Proxyserver Datenverkehr zu Defender für Endpunkt-Dienst-URLs zulässt.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-208">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="a0cf4-209">Laden Sie [MDATP Client Analyzer-Tool auf](https://aka.ms/mdatpanalyzer) den PC herunter, auf dem der Defender for Endpoint-Sensor ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-209">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="a0cf4-210">Extrahieren Sie den Inhalt von MDATPClientAnalyzer.zip auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-210">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="a0cf4-211">Öffnen Sie eine Befehlszeile mit erhöhten Rechten:</span><span class="sxs-lookup"><span data-stu-id="a0cf4-211">Open an elevated command-line:</span></span>

   1. <span data-ttu-id="a0cf4-212">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-212">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="a0cf4-213">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-213">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="a0cf4-214">Geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:</span><span class="sxs-lookup"><span data-stu-id="a0cf4-214">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="a0cf4-215">Ersetzen *Sie HardDrivePath* durch den Pfad, in den das MDATPClientAnalyzer-Tool heruntergeladen wurde, z. B.:</span><span class="sxs-lookup"><span data-stu-id="a0cf4-215">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example:</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="a0cf4-216">Extrahieren Sie *dieMDATPClientAnalyzerResult.zip,* die vom Tool im Ordner erstellt wurde, der in *HardDrivePath verwendet wird.*</span><span class="sxs-lookup"><span data-stu-id="a0cf4-216">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="a0cf4-217">Öffnen Sie *MDATPClientAnalyzerResult.txt*, und vergewissern Sie sich, dass Sie die Schritte zur Proxykonfiguration durchgeführt haben, um die Serverermittlung und den Zugriff auf die Dienst-URLs zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-217">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>

   <span data-ttu-id="a0cf4-218">Das Tool überprüft die Konnektivität von Defender für Endpunkt-Dienst-URLs, mit denen der Defender für Endpunkt-Client laut Konfiguration interagieren kann.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-218">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="a0cf4-219">Anschließend werden die Ergebnisse für jede URL, die potentiell für die Kommunikation mit den Defender für Endpunkt-Diensten verwendet werden kann, in die Datei *MDATPClientAnalyzerResult.txt* gedruckt.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-219">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="a0cf4-220">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a0cf4-220">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="a0cf4-221">Wenn mindestens eine der Verbindungsoptionen einen (200)-Status zurückgibt, kann der Defender für Endpunkt-Client über diese Verbindungsmethode ordnungsgemäß mit der getesteten URL kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-221">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span>

<span data-ttu-id="a0cf4-222">Wenn die Ergebnisse der Verbindungsüberprüfung hingegen auf einen Fehler hindeuten, wird ein HTTP-Fehler angezeigt (siehe HTTP-Status-Codes).</span><span class="sxs-lookup"><span data-stu-id="a0cf4-222">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="a0cf4-223">Anschließend können Sie die URLs in der Tabelle unter Zugriff auf [Defender for Endpoint-Dienst-URLs auf dem Proxyserver aktivieren verwenden.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="a0cf4-223">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="a0cf4-224">Die verwendeten URLs hängen von der Region ab, die während des Onboardings ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-224">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="a0cf4-225"> Das Tool für die Verbindungsanalyse ist nicht kompatibel mit der ASR-Regel [Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="a0cf4-225">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="a0cf4-226">Sie müssen diese Regel vorübergehend deaktivieren, um das Verbindungstool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-226">You will need to temporarily disable this rule to run the connectivity tool.</span></span>


> [!NOTE]
> <span data-ttu-id="a0cf4-227">Wenn TelemetryProxyServer festgelegt ist, wird Defender for Endpoint in der Registrierung oder über Eine Gruppenrichtlinie auf "Direct" zurückfallen, wenn er nicht auf den definierten Proxy zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="a0cf4-227">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a0cf4-228">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a0cf4-228">Related topics</span></span>

- [<span data-ttu-id="a0cf4-229">Onboarding von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="a0cf4-229">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="a0cf4-230">Behandeln von Problemen beim Onboarding von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a0cf4-230">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
