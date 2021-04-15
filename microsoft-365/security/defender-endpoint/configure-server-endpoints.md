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
ms.openlocfilehash: f2660f19d4b6b0d5f8e2dbf48843002a2bfb7f1d
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2021
ms.locfileid: "51769056"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="7d65a-104">Onboarding von Windows-Servern in den Microsoft Defender for Endpoint-Dienst</span><span class="sxs-lookup"><span data-stu-id="7d65a-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7d65a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7d65a-105">**Applies to:**</span></span>

- <span data-ttu-id="7d65a-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="7d65a-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="7d65a-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="7d65a-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="7d65a-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="7d65a-108">Windows Server 2016</span></span>
- <span data-ttu-id="7d65a-109">Windows Server (SAC) Version 1803 und höher</span><span class="sxs-lookup"><span data-stu-id="7d65a-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="7d65a-110">Windows Server 2019 und höher</span><span class="sxs-lookup"><span data-stu-id="7d65a-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="7d65a-111">Windows Server 2019 Core Edition</span><span class="sxs-lookup"><span data-stu-id="7d65a-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="7d65a-112">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="7d65a-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7d65a-113">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="7d65a-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)

<span data-ttu-id="7d65a-114">Defender for Endpoint erweitert die Unterstützung auch auf das Windows Server-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="7d65a-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="7d65a-115">Diese Unterstützung bietet erweiterte Angriffserkennungs- und Untersuchungsfunktionen nahtlos über die Microsoft Defender Security Center-Konsole.</span><span class="sxs-lookup"><span data-stu-id="7d65a-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="7d65a-116">Eine praktische Anleitung dazu, was für Lizenzierung und Infrastruktur erforderlich ist, finden Sie unter [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span><span class="sxs-lookup"><span data-stu-id="7d65a-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="7d65a-117">Anleitungen zum Herunterladen und Verwenden von Windows Security Baselines für Windows-Server finden Sie unter [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span><span class="sxs-lookup"><span data-stu-id="7d65a-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span></span>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="7d65a-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2 und Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="7d65a-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="7d65a-119">Sie können Windows Server 2008 R2 SP1, Windows Server 2012 R2 und Windows Server 2016 in Defender for Endpoint integrieren, indem Sie eine der folgenden Optionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="7d65a-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="7d65a-120">**Option 1**: [Onboarding durch Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span><span class="sxs-lookup"><span data-stu-id="7d65a-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="7d65a-121">**Option 2**: [Onboarding über Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="7d65a-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="7d65a-122">**Option 3**: [Onboarding über Microsoft Endpoint Manager, Version 2002 und höher](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="7d65a-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>

<span data-ttu-id="7d65a-123">Nachdem Sie die Onboardingschritte mit einer der bereitgestellten Optionen abgeschlossen haben, müssen Sie System Center Endpoint Protection-Clients konfigurieren und [aktualisieren.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="7d65a-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="7d65a-124">Die eigenständige Defender for Endpoint-Serverlizenz ist pro Knoten erforderlich, um einen Windows-Server über den Microsoft Monitoring Agent (Option 1) oder den Microsoft Endpoint Manager (Option 3) zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="7d65a-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="7d65a-125">Alternativ ist eine Azure Defender for Servers-Lizenz pro Knoten erforderlich, um einen Windows-Server über Azure Security Center (Option 2) zu integrieren. Weitere Informationen finden Sie unter Unterstützte Features, die [in Azure Security Center verfügbar sind.](https://docs.microsoft.com/azure/security-center/security-center-services)</span><span class="sxs-lookup"><span data-stu-id="7d65a-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-services).</span></span>

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="7d65a-126">Option 1: Onboarding durch Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA)</span><span class="sxs-lookup"><span data-stu-id="7d65a-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>

<span data-ttu-id="7d65a-127">Sie müssen MMA für Windows-Server installieren und konfigurieren, um Sensordaten an Defender for Endpoint zu melden.</span><span class="sxs-lookup"><span data-stu-id="7d65a-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="7d65a-128">Weitere Informationen finden Sie unter [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span><span class="sxs-lookup"><span data-stu-id="7d65a-128">For more information, see [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="7d65a-129">Wenn Sie bereits System Center Operations Manager (SCOM) oder Azure Monitor (ehemals Operations Management Suite (OMS) verwenden, fügen Sie den Microsoft Monitoring Agent (MMA) an, um ihren Defender for Endpoint-Arbeitsbereich über die Multihomingunterstützung zu melden.</span><span class="sxs-lookup"><span data-stu-id="7d65a-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="7d65a-130">Im Allgemeinen müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="7d65a-130">In general, you'll need to take the following steps:</span></span>

1. <span data-ttu-id="7d65a-131">Erfüllen Sie die im Abschnitt Before you begin beschriebenen **Onboardinganforderungen.**</span><span class="sxs-lookup"><span data-stu-id="7d65a-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="7d65a-132">Aktivieren Sie die Serverüberwachung vom Microsoft Defender Security Center aus.</span><span class="sxs-lookup"><span data-stu-id="7d65a-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="7d65a-133">Installieren und konfigurieren Sie MMA für den Server, um Sensordaten an Defender for Endpoint zu melden.</span><span class="sxs-lookup"><span data-stu-id="7d65a-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="7d65a-134">Konfigurieren und Aktualisieren von System Center Endpoint Protection-Clients.</span><span class="sxs-lookup"><span data-stu-id="7d65a-134">Configure and update System Center Endpoint Protection clients.</span></span>

> [!TIP]
> <span data-ttu-id="7d65a-135">Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob es ordnungsgemäß in den Dienst integrierte ist.</span><span class="sxs-lookup"><span data-stu-id="7d65a-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="7d65a-136">Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Defender for Endpoint-Endpunkt](run-detection-test.md).</span><span class="sxs-lookup"><span data-stu-id="7d65a-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="7d65a-137">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="7d65a-137">Before you begin</span></span>

<span data-ttu-id="7d65a-138">Führen Sie die folgenden Schritte aus, um die Onboardinganforderungen zu erfüllen:</span><span class="sxs-lookup"><span data-stu-id="7d65a-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

<span data-ttu-id="7d65a-139">Stellen Windows Server 2008 R2 SP1 oder Windows Server 2012 R2 sicher, dass Sie den folgenden Hotfix installieren:</span><span class="sxs-lookup"><span data-stu-id="7d65a-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>

- [<span data-ttu-id="7d65a-140">Update für Kundenerfahrung und Diagnosetelemetrie</span><span class="sxs-lookup"><span data-stu-id="7d65a-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

<span data-ttu-id="7d65a-141">Stellen Windows Server 2008 R2 SP1 sicher, dass Sie die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="7d65a-141">For Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="7d65a-142">Installieren des monatlichen [Updaterollups vom Februar](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="7d65a-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
- <span data-ttu-id="7d65a-143">Installieren von [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (oder höher) oder [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="7d65a-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d65a-144">Wenn Sie Ihre Windows Server 2008 R2 SP1 mit SCCM verwalten, installiert der SCCM-Client-Agent .Net Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="7d65a-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="7d65a-145">Sie müssen also nicht das .NET Framework 4.5 (oder höher) installieren.</span><span class="sxs-lookup"><span data-stu-id="7d65a-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>

<span data-ttu-id="7d65a-146">Für Windows Server 2008 R2 SP1 und Windows Server 2012 R2: Konfigurieren und Aktualisieren [von System Center Endpoint Protection-Clients](#configure-and-update-system-center-endpoint-protection-clients).</span><span class="sxs-lookup"><span data-stu-id="7d65a-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="7d65a-147">Dieser Schritt ist nur erforderlich, wenn Ihre Organisation System Center Endpoint Protection (SCEP) verwendet und Sie Windows Server 2008 R2 SP1 und Windows Server 2012 R2 integrieren.</span><span class="sxs-lookup"><span data-stu-id="7d65a-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="7d65a-148">Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA) zum Melden von Sensordaten an Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7d65a-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="7d65a-149">Laden Sie die Agent-Setupdatei herunter: [Windows 64-Bit-Agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span><span class="sxs-lookup"><span data-stu-id="7d65a-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="7d65a-150">Wählen Sie mithilfe der im vorherigen Verfahren ermittelten Arbeitsbereichs-ID und des Workspace-Schlüssels eine der folgenden Installationsmethoden aus, um den Agent auf dem Windows-Server zu installieren:</span><span class="sxs-lookup"><span data-stu-id="7d65a-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="7d65a-151">[Installieren Sie den Agent manuell mithilfe von Setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="7d65a-151">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> 
    <span data-ttu-id="7d65a-152">Wählen Sie auf der Seite **Agent-Setupoptionen** die Option **Agent mit Azure Log Analytics (OMS) verbinden aus.**</span><span class="sxs-lookup"><span data-stu-id="7d65a-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="7d65a-153">[Installieren Sie den Agent über die Befehlszeile](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="7d65a-153">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="7d65a-154">[Konfigurieren Sie den Agent mithilfe eines Skripts.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)</span><span class="sxs-lookup"><span data-stu-id="7d65a-154">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="7d65a-155">Wenn Sie ein [Us Government-Kunde](gov.md)sind, müssen Sie unter "Azure Cloud" "Azure US Government" auswählen, wenn Sie den Setup-Assistenten verwenden oder wenn Sie eine Befehlszeile oder ein Skript verwenden – legen Sie den Parameter "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" auf 1.</span><span class="sxs-lookup"><span data-stu-id="7d65a-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="7d65a-156">Konfigurieren von Einstellungen für Windows-Serverproxy und Internetkonnektivität bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="7d65a-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>

<span data-ttu-id="7d65a-157">Wenn Ihre Server einen Proxy für die Kommunikation mit Defender for Endpoint verwenden müssen, verwenden Sie eine der folgenden Methoden, um das MMA für die Verwendung des Proxyservers zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="7d65a-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>

- [<span data-ttu-id="7d65a-158">Konfigurieren der MMA für die Verwendung eines Proxyservers</span><span class="sxs-lookup"><span data-stu-id="7d65a-158">Configure the MMA to use a proxy server</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="7d65a-159">Konfigurieren von Windows für die Verwendung eines Proxyservers für alle Verbindungen</span><span class="sxs-lookup"><span data-stu-id="7d65a-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="7d65a-160">Wenn ein Proxy oder eine Firewall verwendet wird, stellen Sie sicher, dass Server direkt und ohne SSL-Abfangen auf alle URLs des Microsoft Defender for Endpoint-Diensts zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="7d65a-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="7d65a-161">Weitere Informationen finden Sie unter [Aktivieren des Zugriffs auf Defender for Endpoint-Dienst-URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="7d65a-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="7d65a-162">Die Verwendung des SSL-Abfangs verhindert, dass das System mit dem Defender for Endpoint-Dienst kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="7d65a-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span>

<span data-ttu-id="7d65a-163">Sobald sie abgeschlossen sind, sollten integrierte Windows-Server innerhalb einer Stunde im Portal angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7d65a-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="7d65a-164">Option 2: Onboarding von Windows-Servern über Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="7d65a-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>

1. <span data-ttu-id="7d65a-165">Wählen Sie im Navigationsbereich des Microsoft Defender Security Center die Option **Einstellungen**  >  **Geräteverwaltung**  >  **Onboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="7d65a-165">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="7d65a-166">Wählen **Windows Server 2008 R2 SP1, 2012 R2 und 2016** als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="7d65a-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="7d65a-167">Klicken **Sie im Azure Security Center auf Onboard-Server**.</span><span class="sxs-lookup"><span data-stu-id="7d65a-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="7d65a-168">Befolgen Sie die Onboardinganweisungen in [Microsoft Defender for Endpoint mit Azure Security Center,](https://docs.microsoft.com/azure/security-center/security-center-wdatp) und wenn Sie Azure ARC verwenden, befolgen Sie die Anweisungen zum Onboarding unter Aktivieren der Microsoft Defender for [Endpoint-Integration.](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)</span><span class="sxs-lookup"><span data-stu-id="7d65a-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and If you are using Azure ARC, Follow the onboarding instructions in [Enabling the Microsoft Defender for Endpoint integration](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).</span></span>

<span data-ttu-id="7d65a-169">Nach Abschluss der Onboardingschritte müssen Sie System Center Endpoint Protection-Clients konfigurieren und [aktualisieren.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="7d65a-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7d65a-170">Damit das Onboarding über Azure Defender for Servers (zuvor Azure Security Center Standard Edition) wie erwartet funktioniert, muss der Server über einen geeigneten Arbeitsbereich und Schlüssel verfügen, der in den Einstellungen des Microsoft Monitoring Agent (MMA) konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="7d65a-170">For onboarding via Azure Defender for Servers (previously Azure Security Center Standard Edition) to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="7d65a-171">Nach der Konfiguration wird das entsprechende Cloud Management Pack auf dem Computer bereitgestellt, und der Sensorprozess (MsSenseS.exe) wird bereitgestellt und gestartet.</span><span class="sxs-lookup"><span data-stu-id="7d65a-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span>
> - <span data-ttu-id="7d65a-172">Dies ist auch erforderlich, wenn der Server für die Verwendung eines OMS-Gatewayservers als Proxy konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="7d65a-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="7d65a-173">Option 3: Onboarding von Windows-Servern über Microsoft Endpoint Manager, Version 2002 und höher</span><span class="sxs-lookup"><span data-stu-id="7d65a-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>

<span data-ttu-id="7d65a-174">Sie können Windows Server 2012 R2 und Windows Server 2016 mithilfe von Microsoft Endpoint Manager, Version 2002 und höher, integrieren.</span><span class="sxs-lookup"><span data-stu-id="7d65a-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="7d65a-175">Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="7d65a-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="7d65a-176">Nach Abschluss der Onboardingschritte müssen Sie System Center Endpoint Protection-Clients konfigurieren und [aktualisieren.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="7d65a-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="7d65a-177">Windows Server (SAC) Version 1803, Windows Server 2019 und Windows Server 2019 Core Edition</span><span class="sxs-lookup"><span data-stu-id="7d65a-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>

<span data-ttu-id="7d65a-178">Sie können Windows Server (SAC) Version 1803, Windows Server 2019 oder Windows Server 2019 Core edition mithilfe der folgenden Bereitstellungsmethoden integrieren:</span><span class="sxs-lookup"><span data-stu-id="7d65a-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="7d65a-179">Lokales Skript</span><span class="sxs-lookup"><span data-stu-id="7d65a-179">Local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="7d65a-180">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="7d65a-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="7d65a-181">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7d65a-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="7d65a-182">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="7d65a-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="7d65a-183">VDI-Onboardingskripts für nicht persistente Geräte</span><span class="sxs-lookup"><span data-stu-id="7d65a-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
>
> - <span data-ttu-id="7d65a-184">Das Onboardingpaket für Windows Server 2019 über Microsoft Endpoint Manager enthält derzeit ein Skript.</span><span class="sxs-lookup"><span data-stu-id="7d65a-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="7d65a-185">Weitere Informationen zum Bereitstellen von [Skripts](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)in Configuration Manager finden Sie unter Pakete und Programme in Configuration Manager .</span><span class="sxs-lookup"><span data-stu-id="7d65a-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="7d65a-186">Ein lokales Skript eignet sich für einen Nachweis des Konzepts, sollte jedoch nicht für die Produktionsbereitstellung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7d65a-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="7d65a-187">Für eine Produktionsbereitstellung wird die Verwendung von Gruppenrichtlinien oder Microsoft Endpoint Configuration Manager empfohlen.</span><span class="sxs-lookup"><span data-stu-id="7d65a-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="7d65a-188">Die Unterstützung für Windows Server bietet tiefere Einblicke in Serveraktivitäten, die Abdeckung der Kernel- und Speicherangriffserkennung und ermöglicht Reaktionsaktionen.</span><span class="sxs-lookup"><span data-stu-id="7d65a-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="7d65a-189">Konfigurieren Sie die Einstellungen für das Defender for Endpoint-Onboarding auf dem Windows-Server mit den gleichen Tools und Methoden für Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="7d65a-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="7d65a-190">Weitere Informationen finden Sie unter [Onboarding von Windows 10-Geräten](configure-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="7d65a-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="7d65a-191">Wenn Sie eine Anti-Malware-Lösung eines Drittanbieters ausführen, müssen Sie die folgenden Einstellungen für den passiven Microsoft Defender AV-Modus anwenden.</span><span class="sxs-lookup"><span data-stu-id="7d65a-191">If you're running a third-party anti-malware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="7d65a-192">Stellen Sie sicher, dass sie ordnungsgemäß konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="7d65a-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="7d65a-193">Legen Sie den folgenden Registrierungseintrag ein:</span><span class="sxs-lookup"><span data-stu-id="7d65a-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="7d65a-194">Pfad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="7d65a-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="7d65a-195">Name: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="7d65a-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="7d65a-196">Typ: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7d65a-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="7d65a-197">Value: 1</span><span class="sxs-lookup"><span data-stu-id="7d65a-197">Value: 1</span></span>

    1. <span data-ttu-id="7d65a-198">Führen Sie den folgenden PowerShell-Befehl aus, um zu überprüfen, ob der passive Modus konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="7d65a-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="7d65a-199">Vergewissern Sie sich, dass ein aktuelles Ereignis gefunden wurde, das das Passive Mode-Ereignis enthält:</span><span class="sxs-lookup"><span data-stu-id="7d65a-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![Abbildung des Überprüfungsergebniss für den passiven Modus](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="7d65a-201">Führen Sie den folgenden Befehl aus, um zu überprüfen, ob Microsoft Defender AV installiert ist:</span><span class="sxs-lookup"><span data-stu-id="7d65a-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="7d65a-202">Wenn das Ergebnis "Der angegebene Dienst ist nicht als installierter Dienst vorhanden" ist, müssen Sie Microsoft Defender AV installieren.</span><span class="sxs-lookup"><span data-stu-id="7d65a-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="7d65a-203">Weitere Informationen finden Sie unter [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span><span class="sxs-lookup"><span data-stu-id="7d65a-203">For more information, see [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>

    <span data-ttu-id="7d65a-204">Informationen zur Verwendung von Gruppenrichtlinien zum Konfigurieren und Verwalten von Microsoft Defender Antivirus auf Ihren Windows-Servern finden Sie unter Verwenden von Gruppenrichtlinieneinstellungen zum Konfigurieren und Verwalten [von Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="7d65a-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

## <a name="integration-with-azure-security-center"></a><span data-ttu-id="7d65a-205">Integration in Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="7d65a-205">Integration with Azure Security Center</span></span>

<span data-ttu-id="7d65a-206">Defender for Endpoint kann in Azure Security Center integriert werden, um eine umfassende Windows-Serverschutzlösung zu bieten.</span><span class="sxs-lookup"><span data-stu-id="7d65a-206">Defender for Endpoint can integrate with Azure Security Center to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="7d65a-207">Mit dieser Integration kann Azure Security Center die Leistung von Defender for Endpoint nutzen, um eine verbesserte Bedrohungserkennung für Windows-Server zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7d65a-207">With this integration, Azure Security Center can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="7d65a-208">Die folgenden Funktionen sind in dieser Integration enthalten:</span><span class="sxs-lookup"><span data-stu-id="7d65a-208">The following capabilities are included in this integration:</span></span>

- <span data-ttu-id="7d65a-209">Automatisiertes Onboarding – Der Defender for Endpoint-Sensor wird automatisch auf Windows-Servern aktiviert, die in Azure Security Center onboarded sind.</span><span class="sxs-lookup"><span data-stu-id="7d65a-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Security Center.</span></span> <span data-ttu-id="7d65a-210">Weitere Informationen zum Azure Security Center-Onboarding finden Sie [unter Onboarding to Azure Security Center Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).</span><span class="sxs-lookup"><span data-stu-id="7d65a-210">For more information on Azure Security Center onboarding, see [Onboarding to Azure Security Center Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d65a-211">Die Integration zwischen Azure Defender for Servers und Microsoft Defender for Endpoint wurde erweitert, um [Windows Server 2019 und Windows Virtual Desktop (WVD) zu unterstützen.](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)</span><span class="sxs-lookup"><span data-stu-id="7d65a-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="7d65a-212">Windows-Server, die vom Azure Security Center überwacht werden, stehen auch in Defender for Endpoint zur Verfügung – Azure Security Center stellt nahtlos eine Verbindung mit dem Defender for Endpoint-Mandanten her und bietet eine einheitliche Ansicht über Clients und Server hinweg.</span><span class="sxs-lookup"><span data-stu-id="7d65a-212">Windows servers monitored by Azure Security Center will also be available in Defender for Endpoint - Azure Security Center seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="7d65a-213">Darüber hinaus stehen Defender for Endpoint-Warnungen in der Azure Security Center-Konsole zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7d65a-213">In addition, Defender for Endpoint alerts will be available in the Azure Security Center console.</span></span>
- <span data-ttu-id="7d65a-214">Serveruntersuchung – Azure Security Center-Kunden können auf Microsoft Defender Security Center zugreifen, um eine detaillierte Untersuchung durchzuführen, um den Umfang einer potenziellen Verletzung aufzudecken.</span><span class="sxs-lookup"><span data-stu-id="7d65a-214">Server investigation -  Azure Security Center customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="7d65a-215">Wenn Sie Azure Security Center zum Überwachen von Servern verwenden, wird automatisch ein Defender for Endpoint-Mandant erstellt (in den USA für US-Benutzer, in der EU für europäische und britische Benutzer).</span><span class="sxs-lookup"><span data-stu-id="7d65a-215">When you use Azure Security Center to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span>
<span data-ttu-id="7d65a-216">Von Defender for Endpoint erfasste Daten werden am geografischen Standort des Mandanten gespeichert, der während der Bereitstellung identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="7d65a-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="7d65a-217">Wenn Sie Defender for Endpoint vor der Verwendung von Azure Security Center verwenden, werden Ihre Daten an dem Ort gespeichert, den Sie beim Erstellen Ihres Mandanten angegeben haben, auch wenn Sie zu einem späteren Zeitpunkt in Azure Security Center integriert werden.</span><span class="sxs-lookup"><span data-stu-id="7d65a-217">If you use Defender for Endpoint before using Azure Security Center, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Security Center at a later time.</span></span>
> - <span data-ttu-id="7d65a-218">Nach der Konfiguration können Sie den Speicherort ihrer Daten nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="7d65a-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="7d65a-219">Wenn Sie Ihre Daten an einen anderen Speicherort verschieben müssen, müssen Sie den Microsoft Support kontaktieren, um den Mandanten zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="7d65a-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span>
<span data-ttu-id="7d65a-220">Die Serverendpunktüberwachung, die diese Integration nutzt, wurde für Office 365 GCC-Kunden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7d65a-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="7d65a-221">Konfigurieren und Aktualisieren von System Center Endpoint Protection-Clients</span><span class="sxs-lookup"><span data-stu-id="7d65a-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="7d65a-222">Defender for Endpoint ist in System Center Endpoint Protection integriert.</span><span class="sxs-lookup"><span data-stu-id="7d65a-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="7d65a-223">Die Integration bietet Sichtbarkeit für Schadsoftwareerkennungen und zum Beenden der Verbreitung eines Angriffs in Ihrer Organisation, indem potenziell schädliche Dateien oder mutmaßliche Schadsoftware verboten werden.</span><span class="sxs-lookup"><span data-stu-id="7d65a-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="7d65a-224">Die folgenden Schritte sind erforderlich, um diese Integration zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="7d65a-224">The following steps are required to enable this integration:</span></span>

- <span data-ttu-id="7d65a-225">Installieren Sie [das Anti-Malware-Plattformupdate vom Januar 2017 für Endpoint Protection-Clients.](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="7d65a-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="7d65a-226">[Konfigurieren Sie die ScEP-Client-Cloud Protection Service-Mitgliedschaft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) auf die **Einstellung Erweitert.**</span><span class="sxs-lookup"><span data-stu-id="7d65a-226">[Configure the SCEP client Cloud Protection Service membership](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

## <a name="offboard-windows-servers"></a><span data-ttu-id="7d65a-227">Offboard-Windows-Server</span><span class="sxs-lookup"><span data-stu-id="7d65a-227">Offboard Windows servers</span></span>

<span data-ttu-id="7d65a-228">Sie können Windows Server (SAC), Windows Server 2019 und Windows Server 2019 Core Edition mit derselben Methode ausschalten, die für Windows 10-Clientgeräte verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7d65a-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="7d65a-229">Für andere Windows-Serverversionen stehen Ihnen zwei Optionen zur Offboardung von Windows-Servern vom Dienst zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="7d65a-229">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>

- <span data-ttu-id="7d65a-230">Deinstallieren des MMA-Agents</span><span class="sxs-lookup"><span data-stu-id="7d65a-230">Uninstall the MMA agent</span></span>
- <span data-ttu-id="7d65a-231">Entfernen der Konfiguration des Defender for Endpoint-Arbeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="7d65a-231">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="7d65a-232">Offboarding bewirkt, dass der Windows-Server das Senden von Sensordaten an das Portal beendet, aber Daten vom Windows-Server, einschließlich Verweis auf alle Warnungen, die er erhalten hat, werden für bis zu 6 Monate aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="7d65a-232">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="7d65a-233">Deinstallieren von Windows-Servern durch Deinstallieren des MMA-Agents</span><span class="sxs-lookup"><span data-stu-id="7d65a-233">Uninstall Windows servers by uninstalling the MMA agent</span></span>

<span data-ttu-id="7d65a-234">Zum Offboarden des Windows-Servers können Sie den MMA-Agent vom Windows-Server deinstallieren oder von der Berichterstellung an Ihren Defender for Endpoint-Arbeitsbereich trennen.</span><span class="sxs-lookup"><span data-stu-id="7d65a-234">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="7d65a-235">Nach dem Offboarding des Agents sendet der Windows-Server keine Sensordaten mehr an Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7d65a-235">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="7d65a-236">Weitere Informationen finden Sie unter [So deaktivieren Sie einen Agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span><span class="sxs-lookup"><span data-stu-id="7d65a-236">For more information, see [To disable an agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="7d65a-237">Entfernen der Konfiguration des Defender for Endpoint-Arbeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="7d65a-237">Remove the Defender for Endpoint workspace configuration</span></span>

<span data-ttu-id="7d65a-238">Zum Offboarden des Windows-Servers können Sie eine der folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="7d65a-238">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="7d65a-239">Entfernen der Defender for Endpoint-Arbeitsbereichskonfiguration aus dem MMA-Agent</span><span class="sxs-lookup"><span data-stu-id="7d65a-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="7d65a-240">Ausführen eines PowerShell-Befehls zum Entfernen der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7d65a-240">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="7d65a-241">Entfernen der Defender for Endpoint-Arbeitsbereichskonfiguration aus dem MMA-Agent</span><span class="sxs-lookup"><span data-stu-id="7d65a-241">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="7d65a-242">Wählen Sie **auf der Registerkarte Microsoft Monitoring Agent Properties** die Registerkarte Azure Log Analytics **(OMS)** aus.</span><span class="sxs-lookup"><span data-stu-id="7d65a-242">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="7d65a-243">Wählen Sie den Arbeitsbereich Defender für Endpunkt aus, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="7d65a-243">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Abbildung der Microsoft Monitoring Agent-Eigenschaften](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="7d65a-245">Ausführen eines PowerShell-Befehls zum Entfernen der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7d65a-245">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="7d65a-246">Ihre Arbeitsbereichs-ID erhalten:</span><span class="sxs-lookup"><span data-stu-id="7d65a-246">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="7d65a-247">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="7d65a-247">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="7d65a-248">Wählen **Windows Server 2008 R2 SP1, 2012 R2 und 2016** als Betriebssystem aus, und erhalten Sie Ihre Arbeitsbereichs-ID:</span><span class="sxs-lookup"><span data-stu-id="7d65a-248">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Abbildung des Onboardings von Windows-Servern](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="7d65a-250&quot;>Öffnen Sie eine PowerShell mit erhöhten Rechten, und führen Sie den folgenden Befehl aus.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;7d65a-250&quot;>Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id=&quot;7d65a-251&quot;>Verwenden Sie die arbeitsbereichs-ID, die Sie erhalten haben, und ersetzen `WorkspaceID` Sie:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;7d65a-251&quot;>Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = &quot;SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

## <a name="onboarding-servers-with-no-management-solution"></a><span data-ttu-id="7d65a-252">Onboarding von Servern ohne Verwaltungslösung</span><span class="sxs-lookup"><span data-stu-id="7d65a-252">Onboarding Servers with no management solution</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="7d65a-253">Verwenden von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7d65a-253">Using Group Policy</span></span>

<span data-ttu-id="7d65a-254">**Schritt 1: Erstellen Sie die erforderlichen Dateien zum Kopieren auf die Server.**</span><span class="sxs-lookup"><span data-stu-id="7d65a-254">**Step-1: Create the necessary files to copy down to the servers.**</span></span>

1. <span data-ttu-id="7d65a-255">Navigieren Sie zu c:\windows\sysvol\domain\scripts (Die Änderungssteuerung kann auf einem der Domänencontroller erforderlich sein.)</span><span class="sxs-lookup"><span data-stu-id="7d65a-255">Navigate to c:\windows\sysvol\domain\scripts (Change control could be needed on one of the domain controllers.)</span></span>
1. <span data-ttu-id="7d65a-256">Erstellen Sie einen Ordner mit dem Namen MMA.</span><span class="sxs-lookup"><span data-stu-id="7d65a-256">Create a folder named MMA.</span></span>
1. <span data-ttu-id="7d65a-257">Laden Sie Folgendes herunter und platzieren Sie sich im Ordner MMA:</span><span class="sxs-lookup"><span data-stu-id="7d65a-257">Download the following and place in the MMA folder:</span></span>

    <span data-ttu-id="7d65a-258">**Update für Kundenerfahrung und Diagnosetelemetrie (Windows Server 2008 R2 und Windows Server 2012 R2)**</span><span class="sxs-lookup"><span data-stu-id="7d65a-258">**Update for customer experience and diagnostic telemetry (Windows Server 2008 R2 and Windows Server 2012 R2)**</span></span>

    [<span data-ttu-id="7d65a-259">Für Windows 2008 R2 x64</span><span class="sxs-lookup"><span data-stu-id="7d65a-259">For Windows 2008 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [<span data-ttu-id="7d65a-260">Für Windows 2012 R2 x64</span><span class="sxs-lookup"><span data-stu-id="7d65a-260">For Windows 2012 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > <span data-ttu-id="7d65a-261">In diesem Artikel wird davon ausgegangen, dass Sie x64-basierte Server verwenden (MMA Agent .exe x64 [Neue SHA-2-kompatible Version](https://go.microsoft.com/fwlink/?LinkId=828603))</span><span class="sxs-lookup"><span data-stu-id="7d65a-261">This article assumes you are using x64-based servers (MMA Agent .exe x64 [New SHA-2 compliant version](https://go.microsoft.com/fwlink/?LinkId=828603))</span></span>

<span data-ttu-id="7d65a-262">**Schritt 2: Erstellen eines Dateinamens DeployMMA.cmd (mithilfe des Editors)** Fügen Sie der Cmd-Datei die folgenden Zeilen hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d65a-262">**Step-2: Create a file name DeployMMA.cmd (using notepad)** Add the following lines to the cmd file.</span></span> <span data-ttu-id="7d65a-263">Beachten Sie, dass Sie Ihre ARBEITSBEREICHs-ID und den SCHLÜSSEL benötigen.</span><span class="sxs-lookup"><span data-stu-id="7d65a-263">Note that you will need your WORKSPACE ID and KEY.</span></span>

```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (
wusa.exe c:\Windows\MMA\Windows6.1-KB123456-x86.msu /quiet /norestart
wusa.exe c:\Windows\MMA\Windows8.1-KB123456-x86.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /C:"setup.exe /qn ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID=<your workspace ID>
OPINSIGHTS_WORKSPACE_KEY=<your workspace key>== AcceptEndUserLicenseAgreement=1"
)
```

## <a name="group-policy-configuration"></a><span data-ttu-id="7d65a-264">Gruppenrichtlinienkonfiguration</span><span class="sxs-lookup"><span data-stu-id="7d65a-264">Group Policy Configuration</span></span>

<span data-ttu-id="7d65a-265">Erstellen Sie eine neue Gruppenrichtlinie speziell für Onboardinggeräte wie "Microsoft Defender for Endpoint Onboarding".</span><span class="sxs-lookup"><span data-stu-id="7d65a-265">Create a new group policy specifically for onboarding devices such as “Microsoft Defender for Endpoint Onboarding”.</span></span>

- <span data-ttu-id="7d65a-266">Erstellen eines Gruppenrichtlinienordners mit dem Namen "c:\windows\MMA"</span><span class="sxs-lookup"><span data-stu-id="7d65a-266">Create a Group Policy Folder named “c:\windows\MMA”</span></span>

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="Folders":::

    <span data-ttu-id="7d65a-268">**Dadurch wird auf jedem Server, auf dem das Gruppenrichtlinienobjekt angewendet wird, ein neuer Ordner mit dem Namen MMA hinzugefügt und in c:\windows gespeichert. Dies enthält die Installationsdateien für das MMA, die Voraussetzungen und das Installationsskript.**</span><span class="sxs-lookup"><span data-stu-id="7d65a-268">**This will add a new folder on every server that gets the GPO applied, called MMA, and will be stored in c:\windows. This will contain the installation files for the MMA, prerequisites, and install script.**</span></span>

- <span data-ttu-id="7d65a-269">Erstellen Sie eine Gruppenrichtliniendateien-Einstellung für jede der dateien, die in der Net-Anmeldung gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="7d65a-269">Create a Group Policy Files preference for each of the files stored in Net logon.</span></span>

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="Gruppenrichtlinienbild1":::

<span data-ttu-id="7d65a-271">Es kopiert die Dateien aus DOMAIN\NETLOGON\MMA\filename in C:\windows\MMA\filename – die Installationsdateien sind also auf dem Server **lokal:**</span><span class="sxs-lookup"><span data-stu-id="7d65a-271">It copies the files from DOMAIN\NETLOGON\MMA\filename to C:\windows\MMA\filename – **so the installation files are local to the server**:</span></span>

:::image type="content" source="images/deploymma.png" alt-text="Bereitstellen von mma cmd":::

<span data-ttu-id="7d65a-273">Für die beiden KBs (einer für Windows Server 2008R2/Windows 7 und der andere für Windows Server 2012 R2) wiederholen Sie den Vorgang, erstellen jedoch auf der Registerkarte COMMON die Zielrichtung auf Elementebene, sodass die Datei im Bereich nur in die entsprechende Plattform-/Betriebssystemversion kopiert wird:</span><span class="sxs-lookup"><span data-stu-id="7d65a-273">For the two KBs (one for Windows Server 2008R2/Windows 7 and the other for Windows Server 2012 R2) repeat the process but create item level targeting on the COMMON tab, so the file only gets copied to the appropriate platform/Operating system version in scope:</span></span>

:::image type="content" source="images/targeteditor.png" alt-text="Ziel-Editor":::

- <span data-ttu-id="7d65a-275">For Windows Server 2008 R2 you need (and it will only copy down) Windows6.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="7d65a-275">For Windows Server 2008 R2 you need (and it will only copy down) Windows6.1-BJ3080149-x64.msu</span></span>
- <span data-ttu-id="7d65a-276">For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="7d65a-276">For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu</span></span>

<span data-ttu-id="7d65a-277">Sobald dies geschehen ist, müssen Sie eine Startskriptrichtlinie erstellen:</span><span class="sxs-lookup"><span data-stu-id="7d65a-277">Once this is done, you'll need to create a start-up script policy:</span></span>

:::image type="content" source="images/startupprops.png" alt-text="Starteigenschaften":::

<span data-ttu-id="7d65a-279">Der Name der Datei, die hier ausgeführt werden soll, ist c:\windows\MMA\DeployMMA.cmd Sobald der Server im Rahmen des Startvorgangs neu gestartet wird, wird das Update für die Benutzererfahrung und die Diagnosetelemetrie KB installiert, und dann der MMAAgent installiert, während die Arbeitsbereich-ID und der Schlüssel festgelegt werden, und der Server wird onboarded.</span><span class="sxs-lookup"><span data-stu-id="7d65a-279">The name of the file to run here is c:\windows\MMA\DeployMMA.cmd Once the server is restarted as part of the start-up process it will install the Update for customer experience and diagnostic telemetry KB, and then install the MMAAgent, while setting the workspace id and key, and the server will be onboarded.</span></span>

<span data-ttu-id="7d65a-280">Sie können auch eine sofortige **Aufgabe zum** Ausführen von deployMMA.cmd verwenden, wenn Sie nicht alle Server neu starten möchten.</span><span class="sxs-lookup"><span data-stu-id="7d65a-280">You could also use an **immediate task** to run the deployMMA.cmd if you do not want to reboot all the servers.</span></span>
<span data-ttu-id="7d65a-281">Dies kann in zwei Phasen geschehen.</span><span class="sxs-lookup"><span data-stu-id="7d65a-281">This could be done in two phases.</span></span> <span data-ttu-id="7d65a-282">Erstellen Sie **zuerst die Dateien und** den Ordner im GPO – Geben Sie dem System Zeit, um sicherzustellen, dass das Gruppenrichtlinienobjekt angewendet wurde, und alle Server verfügen über die Installationsdateien.</span><span class="sxs-lookup"><span data-stu-id="7d65a-282">First create **the files and the folder in** GPO – Give the system time to ensure the GPO has been applied, and all the servers have the install files.</span></span> <span data-ttu-id="7d65a-283">Fügen Sie dann die sofortige Aufgabe hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d65a-283">Then, add the immediate task.</span></span> <span data-ttu-id="7d65a-284">Dadurch wird dasselbe Ergebnis erzielt, ohne dass ein Neustart erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7d65a-284">This will achieve the same result without requiring a reboot.</span></span>

<span data-ttu-id="7d65a-285">Da das Skript über eine Exit-Methode verfügt und nicht erneut ausgeführt wird, wenn das MMA installiert ist, können Sie auch eine tägliche geplante Aufgabe verwenden, um dasselbe Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="7d65a-285">As the Script has an exit method and wont re-run if the MMA is installed, you could also use a daily scheduled task to achieve the same result.</span></span> <span data-ttu-id="7d65a-286">Ähnlich wie bei einer Configuration Manager-Konformitätsrichtlinie wird täglich überprüft, ob die MMA vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7d65a-286">Similar to an Configuration Manager compliance policy it will check daily to ensure the MMA is present.</span></span>

:::image type="content" source="images/schtask.png" alt-text="Zeitplanaufgabe":::

:::image type="content" source="images/newtaskprops.png" alt-text="neue Aufgabeneigenschaften":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="Bereitstellen von mma-Download-Requisiten":::

:::image type="content" source="images/tasksch.png" alt-text="Aufgabenplaner":::

<span data-ttu-id="7d65a-291">Wie in der Onboardingdokumentation für Server speziell für Server 2008 R2 erwähnt, lesen Sie bitte unten:</span><span class="sxs-lookup"><span data-stu-id="7d65a-291">As mentioned in the onboarding documentation for Server specifically around Server 2008 R2 please see below:</span></span>

<span data-ttu-id="7d65a-292">Stellen Windows Server 2008 R2 PS1 sicher, dass Sie die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="7d65a-292">For Windows Server 2008 R2 PS1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="7d65a-293">Installieren des monatlichen Updaterollups vom Februar [2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="7d65a-293">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
- <span data-ttu-id="7d65a-294">Installieren von [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (oder höher) oder [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="7d65a-294">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

<span data-ttu-id="7d65a-295">Überprüfen Sie, ob die KBs vorhanden sind, bevor Sie Windows Server 2008 R2 Dieser Prozess ermöglicht ihnen das Onboarding aller Server, wenn Configuration Manager keine Server verwaltet.</span><span class="sxs-lookup"><span data-stu-id="7d65a-295">Please check the KBs are present before onboarding Windows Server 2008 R2 This process allows you to onboard all the servers if you don’t have Configuration Manager managing Servers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7d65a-296">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7d65a-296">Related topics</span></span>

- [<span data-ttu-id="7d65a-297">Onboarding von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="7d65a-297">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="7d65a-298">Onboarding von Nicht-Windows-Geräten</span><span class="sxs-lookup"><span data-stu-id="7d65a-298">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="7d65a-299">Konfigurieren der Einstellungen für Endpunktproxy und Internetkonnektivität für Ihren Azure ATP-Sensor</span><span class="sxs-lookup"><span data-stu-id="7d65a-299">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="7d65a-300">Ausführen eines Erkennungstests auf einem neu integrierten Defender for Endpoint-Gerät</span><span class="sxs-lookup"><span data-stu-id="7d65a-300">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="7d65a-301">Beheben von Problemen beim Onboarding von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7d65a-301">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
