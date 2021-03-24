---
title: Onboarding von Windows-Servern in den Microsoft Defender for Endpoint-Dienst
description: Onboarding von Windows-Servern, damit sie Sensordaten an den Microsoft Defender for Endpoint-Sensor senden können.
keywords: onboard server, server, 2012r2, 2016, 2019, server onboarding, device management, configure Windows ATP servers, onboard Microsoft Defender for Endpoint servers, onboard Microsoft Defender for Endpoint servers
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: bd92b44892b49a007316acb97296a44514db0578
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061703"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="04e0c-104">Onboarding von Windows-Servern in den Microsoft Defender for Endpoint-Dienst</span><span class="sxs-lookup"><span data-stu-id="04e0c-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="04e0c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="04e0c-105">**Applies to:**</span></span>

- <span data-ttu-id="04e0c-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="04e0c-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="04e0c-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="04e0c-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="04e0c-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="04e0c-108">Windows Server 2016</span></span>
- <span data-ttu-id="04e0c-109">Windows Server (SAC) Version 1803 und höher</span><span class="sxs-lookup"><span data-stu-id="04e0c-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="04e0c-110">Windows Server 2019 und höher</span><span class="sxs-lookup"><span data-stu-id="04e0c-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="04e0c-111">Windows Server 2019 Core Edition</span><span class="sxs-lookup"><span data-stu-id="04e0c-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="04e0c-112">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="04e0c-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="04e0c-113">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="04e0c-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)


<span data-ttu-id="04e0c-114">Defender for Endpoint erweitert die Unterstützung auch auf das Windows Server-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="04e0c-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="04e0c-115">Diese Unterstützung bietet erweiterte Angriffserkennungs- und Untersuchungsfunktionen nahtlos über die Microsoft Defender Security Center-Konsole.</span><span class="sxs-lookup"><span data-stu-id="04e0c-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="04e0c-116">Eine praktische Anleitung dazu, was für Lizenzierung und Infrastruktur erforderlich ist, finden Sie unter [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span><span class="sxs-lookup"><span data-stu-id="04e0c-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="04e0c-117">Anleitungen zum Herunterladen und Verwenden von Windows Security Baselines für Windows-Server finden Sie unter [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span><span class="sxs-lookup"><span data-stu-id="04e0c-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span></span>

<br>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="04e0c-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2 und Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="04e0c-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="04e0c-119">Sie können Windows Server 2008 R2 SP1, Windows Server 2012 R2 und Windows Server 2016 in Defender for Endpoint integrieren, indem Sie eine der folgenden Optionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="04e0c-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="04e0c-120">**Option 1**: [Onboarding durch Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span><span class="sxs-lookup"><span data-stu-id="04e0c-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="04e0c-121">**Option 2**: [Onboarding über Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="04e0c-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="04e0c-122">**Option 3**: [Onboarding über Microsoft Endpoint Manager, Version 2002 und höher](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="04e0c-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>


<span data-ttu-id="04e0c-123">Nachdem Sie die Onboardingschritte mit einer der bereitgestellten Optionen abgeschlossen haben, müssen Sie System Center Endpoint Protection-Clients konfigurieren und [aktualisieren.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="04e0c-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>


> [!NOTE]
> <span data-ttu-id="04e0c-124">Die eigenständige Defender for Endpoint-Serverlizenz ist pro Knoten erforderlich, um einen Windows-Server über den Microsoft Monitoring Agent (Option 1) oder den Microsoft Endpoint Manager (Option 3) zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="04e0c-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="04e0c-125">Alternativ ist eine Azure Defender for Servers-Lizenz pro Knoten erforderlich, um einen Windows-Server über Azure Security Center (Option 2) zu integrieren. Weitere Informationen finden Sie unter Unterstützte Features, die [in Azure Security Center verfügbar sind.](https://docs.microsoft.com/azure/security-center/security-center-services)</span><span class="sxs-lookup"><span data-stu-id="04e0c-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-services).</span></span>


### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="04e0c-126">Option 1: Onboarding durch Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA)</span><span class="sxs-lookup"><span data-stu-id="04e0c-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>
<span data-ttu-id="04e0c-127">Sie müssen MMA für Windows-Server installieren und konfigurieren, um Sensordaten an Defender for Endpoint zu melden.</span><span class="sxs-lookup"><span data-stu-id="04e0c-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="04e0c-128">Weitere Informationen finden Sie unter [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span><span class="sxs-lookup"><span data-stu-id="04e0c-128">For more information, see [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="04e0c-129">Wenn Sie bereits System Center Operations Manager (SCOM) oder Azure Monitor (ehemals Operations Management Suite (OMS) verwenden, fügen Sie den Microsoft Monitoring Agent (MMA) an, um ihren Defender for Endpoint-Arbeitsbereich über die Multihomingunterstützung zu melden.</span><span class="sxs-lookup"><span data-stu-id="04e0c-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="04e0c-130">Im Allgemeinen müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="04e0c-130">In general, you'll need to take the following steps:</span></span>
1. <span data-ttu-id="04e0c-131">Erfüllen Sie die im Abschnitt Before you begin beschriebenen **Onboardinganforderungen.**</span><span class="sxs-lookup"><span data-stu-id="04e0c-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="04e0c-132">Aktivieren Sie die Serverüberwachung vom Microsoft Defender Security Center aus.</span><span class="sxs-lookup"><span data-stu-id="04e0c-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="04e0c-133">Installieren und konfigurieren Sie MMA für den Server, um Sensordaten an Defender for Endpoint zu melden.</span><span class="sxs-lookup"><span data-stu-id="04e0c-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="04e0c-134">Konfigurieren und Aktualisieren von System Center Endpoint Protection-Clients.</span><span class="sxs-lookup"><span data-stu-id="04e0c-134">Configure and update System Center Endpoint Protection clients.</span></span>


> [!TIP]
> <span data-ttu-id="04e0c-135">Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob es ordnungsgemäß in den Dienst integrierte ist.</span><span class="sxs-lookup"><span data-stu-id="04e0c-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="04e0c-136">Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Defender for Endpoint-Endpunkt](run-detection-test.md).</span><span class="sxs-lookup"><span data-stu-id="04e0c-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>


#### <a name="before-you-begin"></a><span data-ttu-id="04e0c-137">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="04e0c-137">Before you begin</span></span> 
<span data-ttu-id="04e0c-138">Führen Sie die folgenden Schritte aus, um die Onboardinganforderungen zu erfüllen:</span><span class="sxs-lookup"><span data-stu-id="04e0c-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

 - <span data-ttu-id="04e0c-139">Stellen Windows Server 2008 R2 SP1 oder Windows Server 2012 R2 sicher, dass Sie den folgenden Hotfix installieren:</span><span class="sxs-lookup"><span data-stu-id="04e0c-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>
    - [<span data-ttu-id="04e0c-140">Update für Kundenerfahrung und Diagnosetelemetrie</span><span class="sxs-lookup"><span data-stu-id="04e0c-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

 - <span data-ttu-id="04e0c-141">Stellen Sie außerdem für Windows Server 2008 R2 SP1 sicher, dass Sie die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="04e0c-141">In addition, for Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>
    - <span data-ttu-id="04e0c-142">Installieren des monatlichen [Updaterollups vom Februar](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="04e0c-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
    - <span data-ttu-id="04e0c-143">Installieren von [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (oder höher) oder [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="04e0c-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

 - <span data-ttu-id="04e0c-144">Für Windows Server 2008 R2 SP1 und Windows Server 2012 R2: Konfigurieren und Aktualisieren [von System Center Endpoint Protection-Clients](#configure-and-update-system-center-endpoint-protection-clients).</span><span class="sxs-lookup"><span data-stu-id="04e0c-144">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

    > [!NOTE]
    > <span data-ttu-id="04e0c-145">Dieser Schritt ist nur erforderlich, wenn Ihre Organisation System Center Endpoint Protection (SCEP) verwendet und Sie Windows Server 2008 R2 SP1 und Windows Server 2012 R2 integrieren.</span><span class="sxs-lookup"><span data-stu-id="04e0c-145">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>


<span id="server-mma"/>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="04e0c-146">Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA) zum Melden von Sensordaten an Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="04e0c-146">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="04e0c-147">Laden Sie die Agent-Setupdatei herunter: [Windows 64-Bit-Agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span><span class="sxs-lookup"><span data-stu-id="04e0c-147">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="04e0c-148">Wählen Sie mithilfe der im vorherigen Verfahren ermittelten Arbeitsbereichs-ID und des Workspace-Schlüssels eine der folgenden Installationsmethoden aus, um den Agent auf dem Windows-Server zu installieren:</span><span class="sxs-lookup"><span data-stu-id="04e0c-148">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="04e0c-149">[Installieren Sie den Agent manuell mithilfe von Setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="04e0c-149">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
    <span data-ttu-id="04e0c-150">Wählen Sie auf der Seite **Agent-Setupoptionen** die Option **Agent mit Azure Log Analytics (OMS) verbinden aus.**</span><span class="sxs-lookup"><span data-stu-id="04e0c-150">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="04e0c-151">[Installieren Sie den Agent über die Befehlszeile](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="04e0c-151">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="04e0c-152">[Konfigurieren Sie den Agent mithilfe eines Skripts.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)</span><span class="sxs-lookup"><span data-stu-id="04e0c-152">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="04e0c-153">Wenn Sie ein [Us Government-Kunde](gov.md)sind, müssen Sie unter "Azure Cloud" "Azure US Government" auswählen, wenn Sie den Setup-Assistenten verwenden oder wenn Sie eine Befehlszeile oder ein Skript verwenden – legen Sie den Parameter "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" auf 1.</span><span class="sxs-lookup"><span data-stu-id="04e0c-153">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>


<span id="server-proxy"/>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="04e0c-154">Konfigurieren von Einstellungen für Windows-Serverproxy und Internetkonnektivität bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="04e0c-154">Configure Windows server proxy and Internet connectivity settings if needed</span></span>
<span data-ttu-id="04e0c-155">Wenn Ihre Server einen Proxy für die Kommunikation mit Defender for Endpoint verwenden müssen, verwenden Sie eine der folgenden Methoden, um das MMA für die Verwendung des Proxyservers zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="04e0c-155">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>


- [<span data-ttu-id="04e0c-156">Konfigurieren der MMA für die Verwendung eines Proxyservers</span><span class="sxs-lookup"><span data-stu-id="04e0c-156">Configure the MMA to use a proxy server</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="04e0c-157">Konfigurieren von Windows für die Verwendung eines Proxyservers für alle Verbindungen</span><span class="sxs-lookup"><span data-stu-id="04e0c-157">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="04e0c-158">Wenn ein Proxy oder eine Firewall verwendet wird, stellen Sie sicher, dass Server direkt und ohne SSL-Abfangen auf alle URLs des Microsoft Defender for Endpoint-Diensts zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="04e0c-158">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="04e0c-159">Weitere Informationen finden Sie unter [Aktivieren des Zugriffs auf Defender for Endpoint-Dienst-URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="04e0c-159">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="04e0c-160">Die Verwendung des SSL-Abfangs verhindert, dass das System mit dem Defender for Endpoint-Dienst kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="04e0c-160">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span> 

<span data-ttu-id="04e0c-161">Sobald sie abgeschlossen sind, sollten integrierte Windows-Server innerhalb einer Stunde im Portal angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="04e0c-161">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="04e0c-162">Option 2: Onboarding von Windows-Servern über Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="04e0c-162">Option 2: Onboard Windows servers through Azure Security Center</span></span>
1. <span data-ttu-id="04e0c-163">Wählen Sie im Navigationsbereich des Microsoft Defender Security Center die Option **Einstellungen**  >  **Geräteverwaltung**  >  **Onboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="04e0c-163">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="04e0c-164">Wählen **Windows Server 2008 R2 SP1, 2012 R2 und 2016** als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="04e0c-164">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="04e0c-165">Klicken **Sie im Azure Security Center auf Onboard-Server**.</span><span class="sxs-lookup"><span data-stu-id="04e0c-165">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="04e0c-166">Befolgen Sie die Anweisungen zum Onboarding in [Microsoft Defender for Endpoint mit Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span><span class="sxs-lookup"><span data-stu-id="04e0c-166">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span></span>

<span data-ttu-id="04e0c-167">Nach Abschluss der Onboardingschritte müssen Sie System Center Endpoint Protection-Clients konfigurieren und [aktualisieren.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="04e0c-167">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> - <span data-ttu-id="04e0c-168">Damit das Onboarding über Azure Defender for Servers (zuvor Azure Security Center Standard Edition) wie erwartet funktioniert, muss der Server über einen geeigneten Arbeitsbereich und Schlüssel verfügen, der in den Einstellungen des Microsoft Monitoring Agent (MMA) konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="04e0c-168">For onboarding via Azure Defender for Servers (previously Azure Security Center Standard Edition) to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="04e0c-169">Nach der Konfiguration wird das entsprechende Cloud Management Pack auf dem Computer bereitgestellt, und der Sensorprozess (MsSenseS.exe) wird bereitgestellt und gestartet.</span><span class="sxs-lookup"><span data-stu-id="04e0c-169">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span> 
> - <span data-ttu-id="04e0c-170">Dies ist auch erforderlich, wenn der Server für die Verwendung eines OMS-Gatewayservers als Proxy konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="04e0c-170">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="04e0c-171">Option 3: Onboarding von Windows-Servern über Microsoft Endpoint Manager, Version 2002 und höher</span><span class="sxs-lookup"><span data-stu-id="04e0c-171">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>
<span data-ttu-id="04e0c-172">Sie können Windows Server 2012 R2 und Windows Server 2016 mithilfe von Microsoft Endpoint Manager, Version 2002 und höher, integrieren.</span><span class="sxs-lookup"><span data-stu-id="04e0c-172">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="04e0c-173">Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="04e0c-173">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="04e0c-174">Nach Abschluss der Onboardingschritte müssen Sie System Center Endpoint Protection-Clients konfigurieren und [aktualisieren.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="04e0c-174">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

<br>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="04e0c-175">Windows Server (SAC) Version 1803, Windows Server 2019 und Windows Server 2019 Core Edition</span><span class="sxs-lookup"><span data-stu-id="04e0c-175">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>
<span data-ttu-id="04e0c-176">Sie können Windows Server (SAC) Version 1803, Windows Server 2019 oder Windows Server 2019 Core edition mithilfe der folgenden Bereitstellungsmethoden integrieren:</span><span class="sxs-lookup"><span data-stu-id="04e0c-176">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="04e0c-177">Lokales Skript</span><span class="sxs-lookup"><span data-stu-id="04e0c-177">Local script</span></span>](configure-endpoints-script.md) 
- [<span data-ttu-id="04e0c-178">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="04e0c-178">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="04e0c-179">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="04e0c-179">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="04e0c-180">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="04e0c-180">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="04e0c-181">VDI-Onboardingskripts für nicht persistente Geräte</span><span class="sxs-lookup"><span data-stu-id="04e0c-181">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
> - <span data-ttu-id="04e0c-182">Das Onboardingpaket für Windows Server 2019 über Microsoft Endpoint Manager enthält derzeit ein Skript.</span><span class="sxs-lookup"><span data-stu-id="04e0c-182">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="04e0c-183">Weitere Informationen zum Bereitstellen von [Skripts](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)in Configuration Manager finden Sie unter Pakete und Programme in Configuration Manager .</span><span class="sxs-lookup"><span data-stu-id="04e0c-183">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="04e0c-184">Ein lokales Skript eignet sich für einen Nachweis des Konzepts, sollte jedoch nicht für die Produktionsbereitstellung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="04e0c-184">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="04e0c-185">Für eine Produktionsbereitstellung wird die Verwendung von Gruppenrichtlinien oder Microsoft Endpoint Configuration Manager empfohlen.</span><span class="sxs-lookup"><span data-stu-id="04e0c-185">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="04e0c-186">Die Unterstützung für Windows Server bietet tiefere Einblicke in Serveraktivitäten, die Abdeckung der Kernel- und Speicherangriffserkennung und ermöglicht Reaktionsaktionen.</span><span class="sxs-lookup"><span data-stu-id="04e0c-186">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="04e0c-187">Konfigurieren Sie die Einstellungen für das Defender for Endpoint-Onboarding auf dem Windows-Server mit den gleichen Tools und Methoden für Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="04e0c-187">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="04e0c-188">Weitere Informationen finden Sie unter [Onboarding von Windows 10-Geräten](configure-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="04e0c-188">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="04e0c-189">Wenn Sie eine Antischalwarelösung eines Drittanbieters ausführen, müssen Sie die folgenden Einstellungen für den passiven Microsoft Defender AV-Modus anwenden.</span><span class="sxs-lookup"><span data-stu-id="04e0c-189">If you're running a third-party antimalware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="04e0c-190">Stellen Sie sicher, dass sie ordnungsgemäß konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="04e0c-190">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="04e0c-191">Legen Sie den folgenden Registrierungseintrag ein:</span><span class="sxs-lookup"><span data-stu-id="04e0c-191">Set the following registry entry:</span></span>
       - <span data-ttu-id="04e0c-192">Pfad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="04e0c-192">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="04e0c-193">Name: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="04e0c-193">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="04e0c-194">Typ: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="04e0c-194">Type: REG_DWORD</span></span>
       - <span data-ttu-id="04e0c-195">Value: 1</span><span class="sxs-lookup"><span data-stu-id="04e0c-195">Value: 1</span></span>

    1. <span data-ttu-id="04e0c-196">Führen Sie den folgenden PowerShell-Befehl aus, um zu überprüfen, ob der passive Modus konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="04e0c-196">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="04e0c-197">Vergewissern Sie sich, dass ein aktuelles Ereignis gefunden wurde, das das Passive Mode-Ereignis enthält:</span><span class="sxs-lookup"><span data-stu-id="04e0c-197">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![Abbildung des Überprüfungsergebniss für den passiven Modus](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="04e0c-199">Führen Sie den folgenden Befehl aus, um zu überprüfen, ob Microsoft Defender AV installiert ist:</span><span class="sxs-lookup"><span data-stu-id="04e0c-199">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="04e0c-200">Wenn das Ergebnis "Der angegebene Dienst ist nicht als installierter Dienst vorhanden" ist, müssen Sie Microsoft Defender AV installieren.</span><span class="sxs-lookup"><span data-stu-id="04e0c-200">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="04e0c-201">Weitere Informationen finden Sie unter [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span><span class="sxs-lookup"><span data-stu-id="04e0c-201">For more information, see [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>
    
    <span data-ttu-id="04e0c-202">Informationen zur Verwendung von Gruppenrichtlinien zum Konfigurieren und Verwalten von Microsoft Defender Antivirus auf Ihren Windows-Servern finden Sie unter Verwenden von Gruppenrichtlinieneinstellungen zum Konfigurieren und Verwalten [von Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="04e0c-202">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

<br>

## <a name="integration-with-azure-security-center"></a><span data-ttu-id="04e0c-203">Integration in Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="04e0c-203">Integration with Azure Security Center</span></span>
<span data-ttu-id="04e0c-204">Defender for Endpoint kann in Azure Security Center integriert werden, um eine umfassende Windows-Serverschutzlösung zu bieten.</span><span class="sxs-lookup"><span data-stu-id="04e0c-204">Defender for Endpoint can integrate with Azure Security Center to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="04e0c-205">Mit dieser Integration kann Azure Security Center die Leistung von Defender for Endpoint nutzen, um eine verbesserte Bedrohungserkennung für Windows-Server zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="04e0c-205">With this integration, Azure Security Center can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="04e0c-206">Die folgenden Funktionen sind in dieser Integration enthalten:</span><span class="sxs-lookup"><span data-stu-id="04e0c-206">The following capabilities are included in this integration:</span></span>
- <span data-ttu-id="04e0c-207">Automatisiertes Onboarding – Der Defender for Endpoint-Sensor wird automatisch auf Windows-Servern aktiviert, die in Azure Security Center onboarded sind.</span><span class="sxs-lookup"><span data-stu-id="04e0c-207">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Security Center.</span></span> <span data-ttu-id="04e0c-208">Weitere Informationen zum Azure Security Center-Onboarding finden Sie [unter Onboarding to Azure Security Center Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).</span><span class="sxs-lookup"><span data-stu-id="04e0c-208">For more information on Azure Security Center onboarding, see [Onboarding to Azure Security Center Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).</span></span>

    > [!NOTE]
    > <span data-ttu-id="04e0c-209">Automatisiertes Onboarding gilt nur für Windows Server 2008 R2 SP1, Windows Server 2012 R2 und Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="04e0c-209">Automated onboarding is only applicable for Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016.</span></span>

- <span data-ttu-id="04e0c-210">Windows-Server, die vom Azure Security Center überwacht werden, stehen auch in Defender for Endpoint zur Verfügung – Azure Security Center stellt nahtlos eine Verbindung mit dem Defender for Endpoint-Mandanten her und bietet eine einheitliche Ansicht über Clients und Server hinweg.</span><span class="sxs-lookup"><span data-stu-id="04e0c-210">Windows servers monitored by Azure Security Center will also be available in Defender for Endpoint - Azure Security Center seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="04e0c-211">Darüber hinaus stehen Defender for Endpoint-Warnungen in der Azure Security Center-Konsole zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="04e0c-211">In addition, Defender for Endpoint alerts will be available in the Azure Security Center console.</span></span>
- <span data-ttu-id="04e0c-212">Serveruntersuchung – Azure Security Center-Kunden können auf Microsoft Defender Security Center zugreifen, um eine detaillierte Untersuchung durchzuführen, um den Umfang einer potenziellen Verletzung aufzudecken.</span><span class="sxs-lookup"><span data-stu-id="04e0c-212">Server investigation -  Azure Security Center customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="04e0c-213">Wenn Sie Azure Security Center zum Überwachen von Servern verwenden, wird automatisch ein Defender for Endpoint-Mandant erstellt (in den USA für US-Benutzer, in der EU für europäische und britische Benutzer).</span><span class="sxs-lookup"><span data-stu-id="04e0c-213">When you use Azure Security Center to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="04e0c-214">Von Defender for Endpoint erfasste Daten werden am geografischen Standort des Mandanten gespeichert, der während der Bereitstellung identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="04e0c-214">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="04e0c-215">Wenn Sie Defender for Endpoint vor der Verwendung von Azure Security Center verwenden, werden Ihre Daten an dem Ort gespeichert, den Sie beim Erstellen Ihres Mandanten angegeben haben, auch wenn Sie zu einem späteren Zeitpunkt in Azure Security Center integriert werden.</span><span class="sxs-lookup"><span data-stu-id="04e0c-215">If you use Defender for Endpoint before using Azure Security Center, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Security Center at a later time.</span></span>
> - <span data-ttu-id="04e0c-216">Nach der Konfiguration können Sie den Speicherort ihrer Daten nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="04e0c-216">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="04e0c-217">Wenn Sie Ihre Daten an einen anderen Speicherort verschieben müssen, müssen Sie den Microsoft Support kontaktieren, um den Mandanten zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="04e0c-217">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="04e0c-218">Die Serverendpunktüberwachung, die diese Integration nutzt, wurde für Office 365 GCC-Kunden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="04e0c-218">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

<br>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="04e0c-219">Konfigurieren und Aktualisieren von System Center Endpoint Protection-Clients</span><span class="sxs-lookup"><span data-stu-id="04e0c-219">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="04e0c-220">Defender for Endpoint ist in System Center Endpoint Protection integriert.</span><span class="sxs-lookup"><span data-stu-id="04e0c-220">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="04e0c-221">Die Integration bietet Sichtbarkeit für Schadsoftwareerkennungen und zum Beenden der Verbreitung eines Angriffs in Ihrer Organisation, indem potenziell schädliche Dateien oder mutmaßliche Schadsoftware verboten werden.</span><span class="sxs-lookup"><span data-stu-id="04e0c-221">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="04e0c-222">Die folgenden Schritte sind erforderlich, um diese Integration zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="04e0c-222">The following steps are required to enable this integration:</span></span>
- <span data-ttu-id="04e0c-223">Installieren Sie [das Anti-Malware-Plattformupdate vom Januar 2017 für Endpoint Protection-Clients.](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="04e0c-223">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="04e0c-224">[Konfigurieren Sie die ScEP-Client-Cloud Protection Service-Mitgliedschaft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) auf die **Einstellung Erweitert.**</span><span class="sxs-lookup"><span data-stu-id="04e0c-224">[Configure the SCEP client Cloud Protection Service membership](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

<br>

## <a name="offboard-windows-servers"></a><span data-ttu-id="04e0c-225">Offboard-Windows-Server</span><span class="sxs-lookup"><span data-stu-id="04e0c-225">Offboard Windows servers</span></span>
<span data-ttu-id="04e0c-226">Sie können Windows Server (SAC), Windows Server 2019 und Windows Server 2019 Core Edition mit derselben Methode ausschalten, die für Windows 10-Clientgeräte verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="04e0c-226">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="04e0c-227">Für andere Windows-Serverversionen stehen Ihnen zwei Optionen zur Offboardung von Windows-Servern vom Dienst zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="04e0c-227">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>
- <span data-ttu-id="04e0c-228">Deinstallieren des MMA-Agents</span><span class="sxs-lookup"><span data-stu-id="04e0c-228">Uninstall the MMA agent</span></span>
- <span data-ttu-id="04e0c-229">Entfernen der Konfiguration des Defender for Endpoint-Arbeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="04e0c-229">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="04e0c-230">Offboarding bewirkt, dass der Windows-Server das Senden von Sensordaten an das Portal beendet, aber Daten vom Windows-Server, einschließlich Verweis auf alle Warnungen, die er erhalten hat, werden für bis zu 6 Monate aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="04e0c-230">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="04e0c-231">Deinstallieren von Windows-Servern durch Deinstallieren des MMA-Agents</span><span class="sxs-lookup"><span data-stu-id="04e0c-231">Uninstall Windows servers by uninstalling the MMA agent</span></span>
<span data-ttu-id="04e0c-232">Zum Offboarden des Windows-Servers können Sie den MMA-Agent vom Windows-Server deinstallieren oder von der Berichterstellung an Ihren Defender for Endpoint-Arbeitsbereich trennen.</span><span class="sxs-lookup"><span data-stu-id="04e0c-232">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="04e0c-233">Nach dem Offboarding des Agents sendet der Windows-Server keine Sensordaten mehr an Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="04e0c-233">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="04e0c-234">Weitere Informationen finden Sie unter [So deaktivieren Sie einen Agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span><span class="sxs-lookup"><span data-stu-id="04e0c-234">For more information, see [To disable an agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="04e0c-235">Entfernen der Konfiguration des Defender for Endpoint-Arbeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="04e0c-235">Remove the Defender for Endpoint workspace configuration</span></span>
<span data-ttu-id="04e0c-236">Zum Offboarden des Windows-Servers können Sie eine der folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="04e0c-236">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="04e0c-237">Entfernen der Defender for Endpoint-Arbeitsbereichskonfiguration aus dem MMA-Agent</span><span class="sxs-lookup"><span data-stu-id="04e0c-237">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="04e0c-238">Ausführen eines PowerShell-Befehls zum Entfernen der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="04e0c-238">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="04e0c-239">Entfernen der Defender for Endpoint-Arbeitsbereichskonfiguration aus dem MMA-Agent</span><span class="sxs-lookup"><span data-stu-id="04e0c-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="04e0c-240">Wählen Sie **auf der Registerkarte Microsoft Monitoring Agent Properties** die Registerkarte Azure Log Analytics **(OMS)** aus.</span><span class="sxs-lookup"><span data-stu-id="04e0c-240">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="04e0c-241">Wählen Sie den Arbeitsbereich Defender für Endpunkt aus, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="04e0c-241">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Abbildung der Microsoft Monitoring Agent-Eigenschaften](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="04e0c-243">Ausführen eines PowerShell-Befehls zum Entfernen der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="04e0c-243">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="04e0c-244">Ihre Arbeitsbereichs-ID erhalten:</span><span class="sxs-lookup"><span data-stu-id="04e0c-244">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="04e0c-245">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="04e0c-245">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="04e0c-246">Wählen **Windows Server 2008 R2 SP1, 2012 R2 und 2016** als Betriebssystem aus, und erhalten Sie Ihre Arbeitsbereichs-ID:</span><span class="sxs-lookup"><span data-stu-id="04e0c-246">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Abbildung des Onboardings von Windows-Servern](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="04e0c-248">Öffnen Sie eine PowerShell mit erhöhten Rechten, und führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="04e0c-248">Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id="04e0c-249">Verwenden Sie die arbeitsbereichs-ID, die Sie erhalten haben, und ersetzen `WorkspaceID` Sie:</span><span class="sxs-lookup"><span data-stu-id="04e0c-249">Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = "SilentlyContinue"
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

<br>

## <a name="related-topics"></a><span data-ttu-id="04e0c-250">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="04e0c-250">Related topics</span></span>
- [<span data-ttu-id="04e0c-251">Onboarding von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="04e0c-251">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="04e0c-252">Onboarding von Nicht-Windows-Geräten</span><span class="sxs-lookup"><span data-stu-id="04e0c-252">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="04e0c-253">Konfigurieren von Proxy- und Internetverbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="04e0c-253">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="04e0c-254">Ausführen eines Erkennungstests auf einem neu integrierten Defender for Endpoint-Gerät</span><span class="sxs-lookup"><span data-stu-id="04e0c-254">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="04e0c-255">Beheben von Problemen beim Onboarding von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="04e0c-255">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
