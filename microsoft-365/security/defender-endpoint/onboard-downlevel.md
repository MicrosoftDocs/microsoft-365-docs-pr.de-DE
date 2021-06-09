---
title: Onboarding früherer Versionen von Windows in Microsoft Defender für Endpunkt
description: Onboarding unterstützter früherer Versionen von Windows Geräten, sodass sie Sensordaten an den Microsoft Defender für Endpunkt-Sensor senden können
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, down level
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d0cb4a3d01c1380f4fd06999c8f81a4054e2fd00
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844430"
---
# <a name="onboard-previous-versions-of-windows"></a><span data-ttu-id="24ccd-104">Onboarding von früheren Windows-Versionen</span><span class="sxs-lookup"><span data-stu-id="24ccd-104">Onboard previous versions of Windows</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="24ccd-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="24ccd-105">**Applies to:**</span></span>
- [<span data-ttu-id="24ccd-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="24ccd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="24ccd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24ccd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="24ccd-108">**Plattformen**</span><span class="sxs-lookup"><span data-stu-id="24ccd-108">**Platforms**</span></span>
- <span data-ttu-id="24ccd-109">Windows 7 SP1-Enterprise</span><span class="sxs-lookup"><span data-stu-id="24ccd-109">Windows 7 SP1 Enterprise</span></span>
- <span data-ttu-id="24ccd-110">Windows 7 SP1-Pro</span><span class="sxs-lookup"><span data-stu-id="24ccd-110">Windows 7 SP1 Pro</span></span>
- <span data-ttu-id="24ccd-111">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="24ccd-111">Windows 8.1 Pro</span></span>
- <span data-ttu-id="24ccd-112">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="24ccd-112">Windows 8.1 Enterprise</span></span>


><span data-ttu-id="24ccd-113">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="24ccd-113">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="24ccd-114">[Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="24ccd-114">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span></span>

<span data-ttu-id="24ccd-115">Defender für Endpunkt erweitert die Unterstützung um Vorgängerbetriebssysteme und bietet erweiterte Angriffserkennungs- und Untersuchungsfunktionen auf unterstützten Windows Versionen.</span><span class="sxs-lookup"><span data-stu-id="24ccd-115">Defender for Endpoint extends support to include down-level operating systems, providing advanced attack detection and investigation capabilities on supported Windows versions.</span></span>

<span data-ttu-id="24ccd-116">Zum Onboarding von untergeordneten Windows Clientendpunkten in Defender für Endpunkt müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="24ccd-116">To onboard down-level Windows client endpoints to Defender for Endpoint, you'll need to:</span></span>
- <span data-ttu-id="24ccd-117">Konfigurieren und Aktualisieren System Center Endpoint Protection Clients.</span><span class="sxs-lookup"><span data-stu-id="24ccd-117">Configure and update System Center Endpoint Protection clients.</span></span>
- <span data-ttu-id="24ccd-118">Installieren und konfigurieren Sie Microsoft Monitoring Agent (MMA), um Sensordaten wie unten beschrieben an Defender für Endpunkt zu melden.</span><span class="sxs-lookup"><span data-stu-id="24ccd-118">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Defender for Endpoint as instructed below.</span></span>

> [!TIP]
> <span data-ttu-id="24ccd-119">Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob es ordnungsgemäß in den Dienst integriert ist.</span><span class="sxs-lookup"><span data-stu-id="24ccd-119">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="24ccd-120">Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Defender für Endpunkt-Endpunkt.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="24ccd-120">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="24ccd-121">Konfigurieren und Aktualisieren System Center Endpoint Protection Clients</span><span class="sxs-lookup"><span data-stu-id="24ccd-121">Configure and update System Center Endpoint Protection clients</span></span>
> [!IMPORTANT]
> <span data-ttu-id="24ccd-122">Dieser Schritt ist nur erforderlich, wenn Ihre Organisation System Center Endpoint Protection (SCEP) verwendet.</span><span class="sxs-lookup"><span data-stu-id="24ccd-122">This step is required only if your organization uses System Center Endpoint Protection (SCEP).</span></span>

<span data-ttu-id="24ccd-123">Defender für Endpunkt lässt sich in System Center Endpoint Protection integrieren, um die Erkennung von Schadsoftware sichtbar zu machen und die Verbreitung eines Angriffs in Ihrer Organisation zu beenden, indem potenziell schädliche Dateien oder verdächtige Schadsoftware verboten werden.</span><span class="sxs-lookup"><span data-stu-id="24ccd-123">Defender for Endpoint integrates with System Center Endpoint Protection to provide visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 

<span data-ttu-id="24ccd-124">Die folgenden Schritte sind erforderlich, um diese Integration zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="24ccd-124">The following steps are required to enable this integration:</span></span> 
- <span data-ttu-id="24ccd-125">Installieren des [Plattformupdates für die Antischadsoftware-Plattform vom Januar 2017 für Endpoint Protection Clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="24ccd-125">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span></span> 
- <span data-ttu-id="24ccd-126">Konfigurieren der SCEP-Client-Cloud Protection Service-Mitgliedschaft mit der **Erweiterten** Einstellung</span><span class="sxs-lookup"><span data-stu-id="24ccd-126">Configure the SCEP client Cloud Protection Service membership to the **Advanced** setting</span></span>
- <span data-ttu-id="24ccd-127">Konfigurieren Sie Ihr Netzwerk so, dass Verbindungen mit der Microsoft Defender Antivirus Cloud zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="24ccd-127">Configure your network to allow connections to the Microsoft Defender Antivirus cloud.</span></span> <span data-ttu-id="24ccd-128">Weitere Informationen finden Sie unter [Zulassen von Verbindungen mit der Microsoft Defender Antivirus Cloud](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span><span class="sxs-lookup"><span data-stu-id="24ccd-128">For more information, see [Allow connections to the Microsoft Defender Antivirus cloud](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span></span>

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="24ccd-129">Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA) zum Melden von Sensordaten an Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="24ccd-129">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="24ccd-130">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="24ccd-130">Before you begin</span></span>
<span data-ttu-id="24ccd-131">Überprüfen Sie die Mindestsystemanforderungen anhand der folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="24ccd-131">Review the following details to verify minimum system requirements:</span></span>
- <span data-ttu-id="24ccd-132">Installieren des [monatlichen Updaterollups vom Februar 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="24ccd-132">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="24ccd-133">Gilt nur für Windows 7 SP1-Enterprise und Windows 7 SP1-Pro.</span><span class="sxs-lookup"><span data-stu-id="24ccd-133">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span> 

- <span data-ttu-id="24ccd-134">Installieren des [Updates für Kundenerfahrung und Diagnosetelemetrie](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span><span class="sxs-lookup"><span data-stu-id="24ccd-134">Install the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span></span>

- <span data-ttu-id="24ccd-135">Installieren Von [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (oder höher) oder [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="24ccd-135">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="24ccd-136">Gilt nur für Windows 7 SP1-Enterprise und Windows 7 SP1-Pro.</span><span class="sxs-lookup"><span data-stu-id="24ccd-136">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span>
    > <span data-ttu-id="24ccd-137">Installieren Sie .NET Framework 4.0.x nicht, da die oben genannte Installation nicht mehr ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="24ccd-137">Don't install .NET Framework 4.0.x, since it will negate the above installation.</span></span>

- <span data-ttu-id="24ccd-138">Erfüllen sie die Mindestsystemanforderungen des Azure Log Analytics-Agents.</span><span class="sxs-lookup"><span data-stu-id="24ccd-138">Meet the Azure Log Analytics agent minimum system requirements.</span></span> <span data-ttu-id="24ccd-139">Weitere Informationen finden Sie unter [Sammeln von Daten von Computern in Ihrer Umgebung mit Log Analytics.](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="24ccd-139">For more information, see [Collect data from computers in your environment with Log Analytics](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites).</span></span>



1. <span data-ttu-id="24ccd-140">Laden Sie die Agent-Setupdatei herunter: [Windows 64-Bit-Agent](https://go.microsoft.com/fwlink/?LinkId=828603) oder [Windows 32-Bit-Agent.](https://go.microsoft.com/fwlink/?LinkId=828604)</span><span class="sxs-lookup"><span data-stu-id="24ccd-140">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603) or [Windows 32-bit agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span></span>

2. <span data-ttu-id="24ccd-141">Abrufen der Arbeitsbereichs-ID:</span><span class="sxs-lookup"><span data-stu-id="24ccd-141">Obtain the workspace ID:</span></span>
   - <span data-ttu-id="24ccd-142">Wählen Sie im Navigationsbereich von Defender für Endpunkt **Einstellungen > Geräteverwaltung > Onboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="24ccd-142">In the Defender for Endpoint navigation pane, select **Settings > Device management > Onboarding**</span></span>
   - <span data-ttu-id="24ccd-143">Wählen Sie **Windows 7 SP1 und 8.1** als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="24ccd-143">Select **Windows 7 SP1 and 8.1** as the operating system</span></span>
   - <span data-ttu-id="24ccd-144">Kopieren der Arbeitsbereichs-ID und des Arbeitsbereichsschlüssels</span><span class="sxs-lookup"><span data-stu-id="24ccd-144">Copy the workspace ID and workspace key</span></span>

3. <span data-ttu-id="24ccd-145">Wählen Sie unter Verwendung der Arbeitsbereichs-ID und des Arbeitsbereichsschlüssels eine der folgenden Installationsmethoden aus, um den Agent zu installieren:</span><span class="sxs-lookup"><span data-stu-id="24ccd-145">Using the Workspace ID and Workspace key choose any of the following installation methods to install the agent:</span></span>
    - <span data-ttu-id="24ccd-146">[Installieren Sie den Agent manuell mithilfe des Setups.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)</span><span class="sxs-lookup"><span data-stu-id="24ccd-146">[Manually install the agent using setup](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
      <span data-ttu-id="24ccd-147">Wählen Sie auf der Seite **"Agent-Setupoptionen"** **Verbinden agent zu Azure Log Analytics (OMS)** aus.</span><span class="sxs-lookup"><span data-stu-id="24ccd-147">On the **Agent Setup Options** page, select **Connect the agent to Azure Log Analytics (OMS)**</span></span>
    - <span data-ttu-id="24ccd-148">[Installieren Sie den Agent über die Befehlszeile.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)</span><span class="sxs-lookup"><span data-stu-id="24ccd-148">[Install the agent using the command line](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="24ccd-149">[Konfigurieren Sie den Agent mithilfe eines Skripts.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)</span><span class="sxs-lookup"><span data-stu-id="24ccd-149">[Configure the agent using a script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

   > [!NOTE]
   > <span data-ttu-id="24ccd-150">Wenn Sie [US Government-Kunde](gov.md)sind, müssen Sie unter "Azure Cloud" "Azure US Government" auswählen, wenn Sie den Setup-Assistenten verwenden oder eine Befehlszeile oder ein Skript verwenden . Legen Sie den Parameter "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" auf 1 fest.</span><span class="sxs-lookup"><span data-stu-id="24ccd-150">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

4. <span data-ttu-id="24ccd-151">Wenn Sie einen Proxy zum Herstellen einer Verbindung mit dem Internet verwenden, lesen Sie den Abschnitt "Proxyeinstellungen konfigurieren".</span><span class="sxs-lookup"><span data-stu-id="24ccd-151">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="24ccd-152">Nach Abschluss des Vorgangs sollten innerhalb einer Stunde integrierte Endpunkte im Portal angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="24ccd-152">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="configure-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="24ccd-153">Konfigurieren der Einstellungen für Endpunktproxy und Internetkonnektivität für Ihren Azure ATP-Sensor</span><span class="sxs-lookup"><span data-stu-id="24ccd-153">Configure proxy and Internet connectivity settings</span></span>
 
- <span data-ttu-id="24ccd-154">Jeder Windows Endpunkt muss in der Lage sein, eine Verbindung mit dem Internet über HTTPS herzustellen.</span><span class="sxs-lookup"><span data-stu-id="24ccd-154">Each Windows endpoint must be able to connect to the Internet using HTTPS.</span></span> <span data-ttu-id="24ccd-155">Diese Verbindung kann direkt, mithilfe eines Proxys oder über das [OMS-Gateway](/azure/log-analytics/log-analytics-oms-gateway)erfolgen.</span><span class="sxs-lookup"><span data-stu-id="24ccd-155">This connection can be direct, using a proxy, or through the [OMS Gateway](/azure/log-analytics/log-analytics-oms-gateway).</span></span>
- <span data-ttu-id="24ccd-156">Wenn ein Proxy oder eine Firewall standardmäßig den gesamten Datenverkehr blockiert und nur bestimmte Domänen durchlässt oder HTTPS-Überprüfung (SSL-Überprüfung) aktiviert ist, stellen Sie sicher, dass Sie [den Zugriff auf Defender für Endpunkt-Dienst-URLs aktivieren.](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="24ccd-156">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through or HTTPS scanning (SSL inspection) is enabled, make sure that you [enable access to Defender for Endpoint service URLs](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

## <a name="offboard-client-endpoints"></a><span data-ttu-id="24ccd-157">Offboard-Clientendpunkte</span><span class="sxs-lookup"><span data-stu-id="24ccd-157">Offboard client endpoints</span></span>
<span data-ttu-id="24ccd-158">Um das Offboarding auszuführen, können Sie den MMA-Agent vom Endpunkt deinstallieren oder ihn von der Berichterstellung an Ihren Defender für Endpunkt-Arbeitsbereich trennen.</span><span class="sxs-lookup"><span data-stu-id="24ccd-158">To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="24ccd-159">Nach dem Offboarding des Agents sendet der Endpunkt keine Sensordaten mehr an Defender für Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="24ccd-159">After offboarding the agent, the endpoint will no longer send sensor data to Defender for Endpoint.</span></span> 

> <span data-ttu-id="24ccd-160">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="24ccd-160">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="24ccd-161">[Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)</span><span class="sxs-lookup"><span data-stu-id="24ccd-161">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span></span>
