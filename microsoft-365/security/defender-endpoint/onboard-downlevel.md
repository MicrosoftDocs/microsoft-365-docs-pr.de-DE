---
title: Onboarding früherer Versionen von Windows auf Microsoft Defender ATP
description: Onboarding unterstützter früherer Versionen von Windows-Geräten, damit sie Sensordaten an den Microsoft Defender ATP-Sensor senden können
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
ms.openlocfilehash: b180e7555bb3339324d3b99956d8f8ad73dc13c3
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186389"
---
# <a name="onboard-previous-versions-of-windows"></a><span data-ttu-id="51a28-104">Onboarding früherer Versionen von Windows</span><span class="sxs-lookup"><span data-stu-id="51a28-104">Onboard previous versions of Windows</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="51a28-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="51a28-105">**Applies to:**</span></span>
- [<span data-ttu-id="51a28-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="51a28-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="51a28-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51a28-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="51a28-108">**Plattformen**</span><span class="sxs-lookup"><span data-stu-id="51a28-108">**Platforms**</span></span>
- <span data-ttu-id="51a28-109">Windows 7 SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="51a28-109">Windows 7 SP1 Enterprise</span></span>
- <span data-ttu-id="51a28-110">Windows 7 SP1 Pro</span><span class="sxs-lookup"><span data-stu-id="51a28-110">Windows 7 SP1 Pro</span></span>
- <span data-ttu-id="51a28-111">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="51a28-111">Windows 8.1 Pro</span></span>
- <span data-ttu-id="51a28-112">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="51a28-112">Windows 8.1 Enterprise</span></span>


><span data-ttu-id="51a28-113">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="51a28-113">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="51a28-114">[Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="51a28-114">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span></span>

<span data-ttu-id="51a28-115">Defender for Endpoint erweitert die Unterstützung um Betriebssysteme auf unterer Ebene und bietet erweiterte Angriffserkennungs- und Untersuchungsfunktionen für unterstützte Windows-Versionen.</span><span class="sxs-lookup"><span data-stu-id="51a28-115">Defender for Endpoint extends support to include down-level operating systems, providing advanced attack detection and investigation capabilities on supported Windows versions.</span></span>

<span data-ttu-id="51a28-116">Um Windows-Clientendpunkte auf ebener Ebene in Defender for Endpoint zu integrieren, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="51a28-116">To onboard down-level Windows client endpoints to Defender for Endpoint, you'll need to:</span></span>
- <span data-ttu-id="51a28-117">Konfigurieren und Aktualisieren von System Center Endpoint Protection-Clients.</span><span class="sxs-lookup"><span data-stu-id="51a28-117">Configure and update System Center Endpoint Protection clients.</span></span>
- <span data-ttu-id="51a28-118">Installieren und konfigurieren Sie Microsoft Monitoring Agent (MMA), um Sensordaten wie unten beschrieben an Defender for Endpoint zu melden.</span><span class="sxs-lookup"><span data-stu-id="51a28-118">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Defender for Endpoint as instructed below.</span></span>

> [!TIP]
> <span data-ttu-id="51a28-119">Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob es ordnungsgemäß in den Dienst integrierte ist.</span><span class="sxs-lookup"><span data-stu-id="51a28-119">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="51a28-120">Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Defender for Endpoint-Endpunkt](run-detection-test.md).</span><span class="sxs-lookup"><span data-stu-id="51a28-120">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="51a28-121">Konfigurieren und Aktualisieren von System Center Endpoint Protection-Clients</span><span class="sxs-lookup"><span data-stu-id="51a28-121">Configure and update System Center Endpoint Protection clients</span></span>
> [!IMPORTANT]
> <span data-ttu-id="51a28-122">Dieser Schritt ist nur erforderlich, wenn Ihre Organisation System Center Endpoint Protection (SCEP) verwendet.</span><span class="sxs-lookup"><span data-stu-id="51a28-122">This step is required only if your organization uses System Center Endpoint Protection (SCEP).</span></span>

<span data-ttu-id="51a28-123">Defender for Endpoint ist in System Center Endpoint Protection integriert, um Sichtbarkeit für Schadsoftwareerkennungen zu bieten und die Verbreitung eines Angriffs in Ihrer Organisation zu beenden, indem potenziell schädliche Dateien oder mutmaßliche Schadsoftware verboten werden.</span><span class="sxs-lookup"><span data-stu-id="51a28-123">Defender for Endpoint integrates with System Center Endpoint Protection to provide visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 

<span data-ttu-id="51a28-124">Die folgenden Schritte sind erforderlich, um diese Integration zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="51a28-124">The following steps are required to enable this integration:</span></span> 
- <span data-ttu-id="51a28-125">Installieren des [Anti-Malware-Plattformupdates vom Januar 2017 für Endpoint Protection-Clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="51a28-125">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span></span> 
- <span data-ttu-id="51a28-126">Konfigurieren der Cloud Protection Service-Mitgliedschaft des SCEP-Clients auf die **Erweiterte** Einstellung</span><span class="sxs-lookup"><span data-stu-id="51a28-126">Configure the SCEP client Cloud Protection Service membership to the **Advanced** setting</span></span>
- <span data-ttu-id="51a28-127">Konfigurieren Sie Ihr Netzwerk so, dass Verbindungen mit der Microsoft Defender Antivirus-Cloud zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="51a28-127">Configure your network to allow connections to the Microsoft Defender Antivirus cloud.</span></span> <span data-ttu-id="51a28-128">Weitere Informationen finden Sie unter [Zulassen von Verbindungen mit der Microsoft Defender Antivirus-Cloud.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span><span class="sxs-lookup"><span data-stu-id="51a28-128">For more information, see [Allow connections to the Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span></span>

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="51a28-129">Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA) zum Melden von Sensordaten an Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="51a28-129">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="51a28-130">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="51a28-130">Before you begin</span></span>
<span data-ttu-id="51a28-131">Überprüfen Sie die folgenden Details, um die Mindestsystemanforderungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="51a28-131">Review the following details to verify minimum system requirements:</span></span>
- <span data-ttu-id="51a28-132">Installieren des monatlichen Updaterollups vom Februar [2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="51a28-132">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="51a28-133">Gilt nur für Windows 7 SP1 Enterprise und Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="51a28-133">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span> 

- <span data-ttu-id="51a28-134">Installieren des [Updates für Kundenerfahrung und Diagnosetelemetrie](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span><span class="sxs-lookup"><span data-stu-id="51a28-134">Install the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span></span>

- <span data-ttu-id="51a28-135">Installieren von [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (oder höher) oder [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="51a28-135">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="51a28-136">Gilt nur für Windows 7 SP1 Enterprise und Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="51a28-136">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span>
    > <span data-ttu-id="51a28-137">Installieren Sie nicht .NET Framework 4.0.x, da die oben aufgeführte Installation negiert wird.</span><span class="sxs-lookup"><span data-stu-id="51a28-137">Don't install .NET Framework 4.0.x, since it will negate the above installation.</span></span>

- <span data-ttu-id="51a28-138">Erfüllen Sie die Mindestsystemanforderungen des Azure Log Analytics-Agents.</span><span class="sxs-lookup"><span data-stu-id="51a28-138">Meet the Azure Log Analytics agent minimum system requirements.</span></span> <span data-ttu-id="51a28-139">Weitere Informationen finden Sie unter [Sammeln von Daten von Computern in Ihrer Umgebung mit Log Analytics.](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="51a28-139">For more information, see [Collect data from computers in you environment with Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span></span>



1. <span data-ttu-id="51a28-140">Laden Sie die Agent-Setupdatei herunter: [Windows 64-Bit-Agent](https://go.microsoft.com/fwlink/?LinkId=828603) oder [Windows 32-Bit-Agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span><span class="sxs-lookup"><span data-stu-id="51a28-140">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603) or [Windows 32-bit agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span></span>

2. <span data-ttu-id="51a28-141">Rufen Sie die Arbeitsbereichs-ID ab:</span><span class="sxs-lookup"><span data-stu-id="51a28-141">Obtain the workspace ID:</span></span>
   - <span data-ttu-id="51a28-142">Wählen Sie im Navigationsbereich Defender for Endpoint die Option Einstellungen **> Geräteverwaltung > Onboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="51a28-142">In the Defender for Endpoint navigation pane, select **Settings > Device management > Onboarding**</span></span>
   - <span data-ttu-id="51a28-143">Wählen **Sie Windows 7 SP1 und 8.1** als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="51a28-143">Select **Windows 7 SP1 and 8.1** as the operating system</span></span>
   - <span data-ttu-id="51a28-144">Kopieren der Arbeitsbereichs-ID und des Arbeitsbereichsschlüssels</span><span class="sxs-lookup"><span data-stu-id="51a28-144">Copy the workspace ID and workspace key</span></span>

3. <span data-ttu-id="51a28-145">Wählen Sie unter Verwendung der Arbeitsbereichs-ID und des Arbeitsbereichsschlüssels eine der folgenden Installationsmethoden aus, um den Agent zu installieren:</span><span class="sxs-lookup"><span data-stu-id="51a28-145">Using the Workspace ID and Workspace key choose any of the following installation methods to install the agent:</span></span>
    - <span data-ttu-id="51a28-146">[Installieren Sie den Agent manuell mithilfe von Setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="51a28-146">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
      <span data-ttu-id="51a28-147">Wählen Sie auf der Seite **Agent-Setupoptionen** die Option **Agent mit Azure Log Analytics (OMS) verbinden aus.**</span><span class="sxs-lookup"><span data-stu-id="51a28-147">On the **Agent Setup Options** page, select **Connect the agent to Azure Log Analytics (OMS)**</span></span>
    - <span data-ttu-id="51a28-148">[Installieren Sie den Agent über die Befehlszeile](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="51a28-148">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="51a28-149">[Konfigurieren Sie den Agent mithilfe eines Skripts.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)</span><span class="sxs-lookup"><span data-stu-id="51a28-149">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

   > [!NOTE]
   > <span data-ttu-id="51a28-150">Wenn Sie ein [Us Government-Kunde](gov.md)sind, müssen Sie unter "Azure Cloud" "Azure US Government" auswählen, wenn Sie den Setup-Assistenten verwenden oder wenn Sie eine Befehlszeile oder ein Skript verwenden – legen Sie den Parameter "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" auf 1.</span><span class="sxs-lookup"><span data-stu-id="51a28-150">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

4. <span data-ttu-id="51a28-151">Wenn Sie einen Proxy zum Herstellen einer Verbindung mit dem Internet verwenden, lesen Sie den Abschnitt Konfigurieren von Proxyeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="51a28-151">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="51a28-152">Sobald sie abgeschlossen sind, sollten integrierte Endpunkte innerhalb einer Stunde im Portal angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="51a28-152">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="configure-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="51a28-153">Konfigurieren von Proxy- und Internetverbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="51a28-153">Configure proxy and Internet connectivity settings</span></span>
 
- <span data-ttu-id="51a28-154">Jeder Windows-Endpunkt muss über HTTPS eine Verbindung mit dem Internet herstellen können.</span><span class="sxs-lookup"><span data-stu-id="51a28-154">Each Windows endpoint must be able to connect to the Internet using HTTPS.</span></span> <span data-ttu-id="51a28-155">Diese Verbindung kann direkt über einen Proxy oder über das [OMS-Gateway hergestellt werden.](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)</span><span class="sxs-lookup"><span data-stu-id="51a28-155">This connection can be direct, using a proxy, or through the [OMS Gateway](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway).</span></span>
- <span data-ttu-id="51a28-156">Wenn ein Proxy oder eine Firewall standardmäßig den ganzen Datenverkehr blockiert und nur bestimmte Domänen über oder die HTTPS-Überprüfung (SSL-Überprüfung) aktiviert ist, stellen Sie sicher, dass Sie den Zugriff auf [DIE URLs](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)des Defender for Endpoint-Diensts aktivieren.</span><span class="sxs-lookup"><span data-stu-id="51a28-156">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through or HTTPS scanning (SSL inspection) is enabled, make sure that you [enable access to Defender for Endpoint service URLs](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

## <a name="offboard-client-endpoints"></a><span data-ttu-id="51a28-157">Offboard-Clientendpunkte</span><span class="sxs-lookup"><span data-stu-id="51a28-157">Offboard client endpoints</span></span>
<span data-ttu-id="51a28-158">In offboard können Sie den MMA-Agent vom Endpunkt deinstallieren oder von der Berichterstellung an Ihren Defender for Endpoint-Arbeitsbereich trennen.</span><span class="sxs-lookup"><span data-stu-id="51a28-158">To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="51a28-159">Nach dem Offboarding des Agents sendet der Endpunkt keine Sensordaten mehr an Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="51a28-159">After offboarding the agent, the endpoint will no longer send sensor data to Defender for Endpoint.</span></span> 

> <span data-ttu-id="51a28-160">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="51a28-160">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="51a28-161">[Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span><span class="sxs-lookup"><span data-stu-id="51a28-161">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span></span>

