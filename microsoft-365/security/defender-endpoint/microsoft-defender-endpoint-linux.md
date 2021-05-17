---
title: Microsoft Defender für Endpunkt unter Linux
ms.reviewer: ''
description: Beschreibt, wie Sie Microsoft Defender for Endpoint unter Linux installieren und verwenden.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0e09a313b512135785050abd5aa61bb9576ce1d8
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274940"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="74536-104">Microsoft Defender für Endpunkt unter Linux</span><span class="sxs-lookup"><span data-stu-id="74536-104">Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="74536-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="74536-105">**Applies to:**</span></span>
- [<span data-ttu-id="74536-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="74536-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="74536-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74536-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="74536-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="74536-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="74536-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="74536-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="74536-110">In diesem Thema wird beschrieben, wie Sie Microsoft Defender for Endpoint unter Linux installieren, konfigurieren, aktualisieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="74536-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="74536-111">Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern neben Microsoft Defender for Endpoint unter Linux führt wahrscheinlich zu Leistungsproblemen und unvorhersehbaren Nebenwirkungen.</span><span class="sxs-lookup"><span data-stu-id="74536-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="74536-112">Wenn der Nicht-Microsoft-Endpunktschutz in Ihrer Umgebung eine absolute Anforderung ist, können Sie die Funktionen von Defender for Endpoint unter Linux EDR weiterhin sicher nutzen, nachdem Sie die Antivirenfunktionen so konfiguriert haben, dass sie im passiven Modus [ausgeführt werden.](linux-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="74536-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="74536-113">Installieren von Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="74536-113">How to install Microsoft Defender for Endpoint on Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="74536-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="74536-114">Prerequisites</span></span>

- <span data-ttu-id="74536-115">Zugriff auf das Microsoft Defender Security Center Portal</span><span class="sxs-lookup"><span data-stu-id="74536-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="74536-116">Linux-Verteilung mithilfe des [systemd System](https://systemd.io/) Managers</span><span class="sxs-lookup"><span data-stu-id="74536-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="74536-117">Anfängererfahrung in Linux- und BASH-Skripting</span><span class="sxs-lookup"><span data-stu-id="74536-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="74536-118">Administratorrechte auf dem Gerät (bei manueller Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="74536-118">Administrative privileges on the device (in case of manual deployment)</span></span>

> [!NOTE]
>  <span data-ttu-id="74536-119">Microsoft Defender for Endpoint on Linux Agent ist unabhängig vom [OMS-Agent.](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="74536-119">Microsoft Defender for Endpoint on Linux agent is independent from [OMS agent](/azure/azure-monitor/agents/agents-overview#log-analytics-agent).</span></span> <span data-ttu-id="74536-120">Microsoft Defender for Endpoint basiert auf einer eigenen unabhängigen Telemetriepipeline.</span><span class="sxs-lookup"><span data-stu-id="74536-120">Microsoft Defender for Endpoint relies on its own independent telemetry pipeline.</span></span>
> 
> <span data-ttu-id="74536-121">Microsoft Defender for Endpoint unter Linux ist noch nicht in Azure Security Center integriert.</span><span class="sxs-lookup"><span data-stu-id="74536-121">Microsoft Defender for Endpoint on Linux is not yet integrated into Azure Security Center.</span></span>



### <a name="installation-instructions"></a><span data-ttu-id="74536-122">Installationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="74536-122">Installation instructions</span></span>

<span data-ttu-id="74536-123">Es gibt mehrere Methoden und Bereitstellungstools, die Sie zum Installieren und Konfigurieren von Microsoft Defender for Endpoint unter Linux verwenden können.</span><span class="sxs-lookup"><span data-stu-id="74536-123">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="74536-124">Im Allgemeinen müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="74536-124">In general you need to take the following steps:</span></span>

- <span data-ttu-id="74536-125">Stellen Sie sicher, dass Sie über ein Microsoft Defender for Endpoint-Abonnement verfügen und auf das [Microsoft Defender for Endpoint-Portal zugreifen können.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="74536-125">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="74536-126">Stellen Sie Microsoft Defender for Endpoint unter Linux mithilfe einer der folgenden Bereitstellungsmethoden zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="74536-126">Deploy Microsoft Defender for Endpoint on Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="74536-127">Das Befehlszeilentool:</span><span class="sxs-lookup"><span data-stu-id="74536-127">The command-line tool:</span></span>
    - [<span data-ttu-id="74536-128">Manuelle Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="74536-128">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="74536-129">Verwaltungstools von Drittanbietern:</span><span class="sxs-lookup"><span data-stu-id="74536-129">Third-party management tools:</span></span>
    - [<span data-ttu-id="74536-130">Bereitstellen mit dem Tool für die Konfiguration von "Puppet"</span><span class="sxs-lookup"><span data-stu-id="74536-130">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="74536-131">Bereitstellen mithilfe des Ansible Configuration Management Tools</span><span class="sxs-lookup"><span data-stu-id="74536-131">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="74536-132">Wenn Installationsfehler auft werden, finden Sie informationen unter [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span><span class="sxs-lookup"><span data-stu-id="74536-132">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span></span>



### <a name="system-requirements"></a><span data-ttu-id="74536-133">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="74536-133">System requirements</span></span>

- <span data-ttu-id="74536-134">Unterstützte Linux-Serververteilungen und -versionen:</span><span class="sxs-lookup"><span data-stu-id="74536-134">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="74536-135">Red Hat Enterprise Linux 7.2 oder höher</span><span class="sxs-lookup"><span data-stu-id="74536-135">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="74536-136">CentOS 7.2 oder höher</span><span class="sxs-lookup"><span data-stu-id="74536-136">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="74536-137">Ubuntu 16.04 LTS oder höher LTS</span><span class="sxs-lookup"><span data-stu-id="74536-137">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="74536-138">Debian 9 oder höher</span><span class="sxs-lookup"><span data-stu-id="74536-138">Debian 9 or higher</span></span>
  - <span data-ttu-id="74536-139">SUSE Linux Enterprise Server 12 oder höher</span><span class="sxs-lookup"><span data-stu-id="74536-139">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="74536-140">Oracle Linux 7.2 oder höher</span><span class="sxs-lookup"><span data-stu-id="74536-140">Oracle Linux 7.2 or higher</span></span>

    > [!NOTE]
    > <span data-ttu-id="74536-141">Nicht explizit aufgeführte Verteilungen und Versionen werden nicht unterstützt (auch wenn sie von den offiziell unterstützten Verteilungen abgeleitet sind).</span><span class="sxs-lookup"><span data-stu-id="74536-141">Distributions and version that are not explicitly listed are unsupported (even if they are derived from the officially supported distributions).</span></span>


- <span data-ttu-id="74536-142">Minimale Kernelversion 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="74536-142">Minimum kernel version 3.10.0-327</span></span>

- <span data-ttu-id="74536-143">Die `fanotify` Kerneloption muss aktiviert sein</span><span class="sxs-lookup"><span data-stu-id="74536-143">The `fanotify` kernel option must be enabled</span></span>

  > [!CAUTION]
  > <span data-ttu-id="74536-144">Das Ausführen von Defender for Endpoint auf Linux neben anderen -basierten Sicherheitslösungen `fanotify` wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="74536-144">Running Defender for Endpoint on Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="74536-145">Dies kann zu unvorhersehbaren Ergebnissen führen, einschließlich des Aufhängens des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="74536-145">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="74536-146">Speicherplatz: 1 GB</span><span class="sxs-lookup"><span data-stu-id="74536-146">Disk space: 1 GB</span></span>

- <span data-ttu-id="74536-147">/opt/microsoft/mdatp/sbin/wdavdaemon erfordert ausführbare Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="74536-147">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="74536-148">Weitere Informationen finden Sie unter "Sicherstellen, dass der Daemon über ausführbare Berechtigungen verfügt" unter [Problembehandlung](/microsoft-365/security/defender-endpoint/linux-support-install)von Installationsproblemen für Microsoft Defender for Endpoint unter Linux .</span><span class="sxs-lookup"><span data-stu-id="74536-148">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>

- <span data-ttu-id="74536-149">Arbeitsspeicher: 1 GB</span><span class="sxs-lookup"><span data-stu-id="74536-149">Memory: 1 GB</span></span>

    > [!NOTE]
    > <span data-ttu-id="74536-150">Stellen Sie sicher, dass Sie freien Speicherplatz in /var haben.</span><span class="sxs-lookup"><span data-stu-id="74536-150">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="74536-151">Die Lösung bietet derzeit Echtzeitschutz für die folgenden Dateisystemtypen:</span><span class="sxs-lookup"><span data-stu-id="74536-151">The solution currently provides real-time protection for the following file system types:</span></span>

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

<span data-ttu-id="74536-152">Nachdem Sie den Dienst aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder ihre Firewall so konfigurieren, dass ausgehende Verbindungen zwischen dem Dienst und Ihren Endpunkten zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="74536-152">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="74536-153">Das Überwachungsframework ( `auditd` ) muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="74536-153">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="74536-154">Systemereignisse, die von Regeln erfasst werden, die hinzugefügt werden, werden zu (n) hinzugefügt und können sich auf die `/etc/audit/rules.d/` `audit.log` Hostüberwachung und die Upstreamsammlung auswirken.</span><span class="sxs-lookup"><span data-stu-id="74536-154">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="74536-155">Ereignisse, die von Microsoft Defender for Endpoint unter Linux hinzugefügt werden, werden mit dem Schlüssel `mdatp` markiert.</span><span class="sxs-lookup"><span data-stu-id="74536-155">Events added by Microsoft Defender for Endpoint on Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="74536-156">Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="74536-156">Network connections</span></span>

<span data-ttu-id="74536-157">In der folgenden herunterladbaren Kalkulationstabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit deren Netzwerk eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="74536-157">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="74536-158">Sie sollten sicherstellen, dass es keine Firewall- oder Netzwerkfilterregeln gibt, die den Zugriff auf diese URLs verweigern würden.</span><span class="sxs-lookup"><span data-stu-id="74536-158">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="74536-159">Falls dies derFall ist, müssen Sie möglicherweise eine *speziell* für sie zulässige Regel erstellen.</span><span class="sxs-lookup"><span data-stu-id="74536-159">If there are, you may need to create an *allow* rule specifically for them.</span></span>

| <span data-ttu-id="74536-160">Tabellenkalkulation der Domänenliste</span><span class="sxs-lookup"><span data-stu-id="74536-160">Spreadsheet of domains list</span></span> | <span data-ttu-id="74536-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74536-161">Description</span></span> |
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="74536-163">Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme.</span><span class="sxs-lookup"><span data-stu-id="74536-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="74536-164">Laden Sie die Tabelle hier herunter.</span><span class="sxs-lookup"><span data-stu-id="74536-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="74536-165">Eine spezifischere URL-Liste finden Sie unter [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="74536-165">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="74536-166">Defender for Endpoint kann einen Proxyserver mithilfe der folgenden Ermittlungsmethoden ermitteln:</span><span class="sxs-lookup"><span data-stu-id="74536-166">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="74536-167">Transparenter Proxy</span><span class="sxs-lookup"><span data-stu-id="74536-167">Transparent proxy</span></span>
- <span data-ttu-id="74536-168">Manuelle Konfiguration statischer Proxys</span><span class="sxs-lookup"><span data-stu-id="74536-168">Manual static proxy configuration</span></span>

<span data-ttu-id="74536-169">Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="74536-169">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="74536-170">Für transparente Proxys ist keine zusätzliche Konfiguration für Defender for Endpoint erforderlich.</span><span class="sxs-lookup"><span data-stu-id="74536-170">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="74536-171">Führen Sie für statischen Proxy die Schritte unter [Manuelle statische Proxykonfiguration aus.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="74536-171">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="74536-172">PAC-, WPAD- und authentifizierte Proxys werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="74536-172">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="74536-173">Stellen Sie sicher, dass nur ein statischer oder transparenter Proxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="74536-173">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="74536-174">Ssl-Überprüfung und Abfangen von Proxys werden aus Sicherheitsgründen ebenfalls nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="74536-174">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="74536-175">Konfigurieren Sie eine Ausnahme für die SSL-Überprüfung und Ihren Proxyserver, um Daten von Defender for Endpoint unter Linux direkt an die relevanten URLs ohne Abfangen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="74536-175">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="74536-176">Wenn Sie Ihr Abfangzertifikat zum globalen Speicher hinzufügen, ist das Abfangen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="74536-176">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="74536-177">Informationen zur Problembehandlung finden Sie unter [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="74536-177">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="74536-178">Aktualisieren von Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="74536-178">How to update Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="74536-179">Microsoft veröffentlicht regelmäßig Softwareupdates, um leistung, Sicherheit und neue Features zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="74536-179">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="74536-180">Informationen zum Aktualisieren von Microsoft Defender for Endpoint unter Linux finden Sie unter [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span><span class="sxs-lookup"><span data-stu-id="74536-180">To update Microsoft Defender for Endpoint on Linux, refer to [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="74536-181">Konfigurieren von Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="74536-181">How to configure Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="74536-182">Anleitungen zum Konfigurieren des Produkts in Unternehmensumgebungen finden Sie unter [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="74536-182">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="74536-183">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="74536-183">Resources</span></span>

- <span data-ttu-id="74536-184">Weitere Informationen zum Protokollieren, Deinstallieren oder anderen Themen finden Sie unter [Ressourcen](linux-resources.md).</span><span class="sxs-lookup"><span data-stu-id="74536-184">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
