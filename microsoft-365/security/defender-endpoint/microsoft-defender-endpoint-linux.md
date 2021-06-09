---
title: Microsoft Defender für Endpunkt unter Linux
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter Linux installiert und verwendet wird.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Linux, Installation, bereitstellen, Deinstallation, entinstallation, ansible, linux, redhat, ubuntu, git, sles, suse, centos
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
ms.openlocfilehash: bd9d42ed85e9a489107a72ccbe841537a7e524d4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843518"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="731e5-104">Microsoft Defender für Endpunkt unter Linux</span><span class="sxs-lookup"><span data-stu-id="731e5-104">Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="731e5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="731e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="731e5-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="731e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="731e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="731e5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="731e5-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="731e5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="731e5-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="731e5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="731e5-110">In diesem Thema wird beschrieben, wie Sie Microsoft Defender für Endpunkt unter Linux installieren, konfigurieren, aktualisieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="731e5-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="731e5-111">Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Microsoft Defender für Endpunkt unter Linux führt wahrscheinlich zu Leistungsproblemen und unvorhersehbaren Nebeneffekten.</span><span class="sxs-lookup"><span data-stu-id="731e5-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="731e5-112">Wenn der Nicht-Microsoft-Endpunktschutz eine absolute Anforderung in Ihrer Umgebung ist, können Sie nach der Konfiguration der Antivirenfunktionen für die Ausführung im [passiven Modus](linux-preferences.md#enable--disable-passive-mode)weiterhin die Funktionen von Defender für Endpunkt unter Linux EDR nutzen.</span><span class="sxs-lookup"><span data-stu-id="731e5-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="731e5-113">So installieren Sie Microsoft Defender für Endpunkt unter Linux</span><span class="sxs-lookup"><span data-stu-id="731e5-113">How to install Microsoft Defender for Endpoint on Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="731e5-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="731e5-114">Prerequisites</span></span>

- <span data-ttu-id="731e5-115">Zugriff auf das Microsoft Defender Security Center-Portal</span><span class="sxs-lookup"><span data-stu-id="731e5-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="731e5-116">Linux-Verteilung mithilfe des [systemierten](https://systemd.io/) System-Managers</span><span class="sxs-lookup"><span data-stu-id="731e5-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="731e5-117">Anfängererfahrung in Linux- und BASH-Skripting</span><span class="sxs-lookup"><span data-stu-id="731e5-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="731e5-118">Administratorrechte auf dem Gerät (bei manueller Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="731e5-118">Administrative privileges on the device (in case of manual deployment)</span></span>

> [!NOTE]
>  <span data-ttu-id="731e5-119">Microsoft Defender für Endpunkt unter Linux-Agent ist unabhängig vom [OMS-Agent.](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="731e5-119">Microsoft Defender for Endpoint on Linux agent is independent from [OMS agent](/azure/azure-monitor/agents/agents-overview#log-analytics-agent).</span></span> <span data-ttu-id="731e5-120">Microsoft Defender für Endpunkt basiert auf einer eigenen unabhängigen Telemetriepipeline.</span><span class="sxs-lookup"><span data-stu-id="731e5-120">Microsoft Defender for Endpoint relies on its own independent telemetry pipeline.</span></span>
> 
> <span data-ttu-id="731e5-121">Microsoft Defender für Endpunkt unter Linux ist noch nicht in Azure Security Center integriert.</span><span class="sxs-lookup"><span data-stu-id="731e5-121">Microsoft Defender for Endpoint on Linux is not yet integrated into Azure Security Center.</span></span>



### <a name="installation-instructions"></a><span data-ttu-id="731e5-122">Installationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="731e5-122">Installation instructions</span></span>

<span data-ttu-id="731e5-123">Es gibt mehrere Methoden und Bereitstellungstools, mit denen Sie Microsoft Defender für Endpunkt unter Linux installieren und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="731e5-123">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="731e5-124">Im Allgemeinen müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="731e5-124">In general you need to take the following steps:</span></span>

- <span data-ttu-id="731e5-125">Stellen Sie sicher, dass Sie über ein Microsoft Defender für Endpunkt-Abonnement verfügen und Zugriff auf das [Microsoft Defender für Endpunkt-Portal](microsoft-defender-security-center.md)haben.</span><span class="sxs-lookup"><span data-stu-id="731e5-125">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="731e5-126">Stellen Sie Microsoft Defender für Endpunkt unter Linux mithilfe einer der folgenden Bereitstellungsmethoden bereit:</span><span class="sxs-lookup"><span data-stu-id="731e5-126">Deploy Microsoft Defender for Endpoint on Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="731e5-127">Das Befehlszeilentool:</span><span class="sxs-lookup"><span data-stu-id="731e5-127">The command-line tool:</span></span>
    - [<span data-ttu-id="731e5-128">Manuelle Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="731e5-128">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="731e5-129">Verwaltungstools von Drittanbietern:</span><span class="sxs-lookup"><span data-stu-id="731e5-129">Third-party management tools:</span></span>
    - [<span data-ttu-id="731e5-130">Bereitstellen mithilfe des Konfigurationsverwaltungstools für die Konfiguration von "Durchbauen"</span><span class="sxs-lookup"><span data-stu-id="731e5-130">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="731e5-131">Bereitstellen mithilfe des Ansible-Konfigurationsverwaltungstools</span><span class="sxs-lookup"><span data-stu-id="731e5-131">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="731e5-132">Wenn Installationsfehler auftreten, finden Sie informationen zur [Problembehandlung von Installationsfehlern in Microsoft Defender für Endpunkt unter Linux.](linux-support-install.md)</span><span class="sxs-lookup"><span data-stu-id="731e5-132">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span></span>



### <a name="system-requirements"></a><span data-ttu-id="731e5-133">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="731e5-133">System requirements</span></span>

- <span data-ttu-id="731e5-134">Unterstützte Linux-Serververteilungen und x64-Versionen (AMD64/EM64T):</span><span class="sxs-lookup"><span data-stu-id="731e5-134">Supported Linux server distributions and x64 (AMD64/EM64T) versions:</span></span>

  - <span data-ttu-id="731e5-135">Red Hat Enterprise Linux 7.2 oder höher</span><span class="sxs-lookup"><span data-stu-id="731e5-135">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="731e5-136">CentOS 7.2 oder höher</span><span class="sxs-lookup"><span data-stu-id="731e5-136">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="731e5-137">Ubuntu 16.04 LTS oder höher LTS</span><span class="sxs-lookup"><span data-stu-id="731e5-137">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="731e5-138">Ubuntu 9 oder höher</span><span class="sxs-lookup"><span data-stu-id="731e5-138">Debian 9 or higher</span></span>
  - <span data-ttu-id="731e5-139">SUSE Linux Enterprise Server 12 oder höher</span><span class="sxs-lookup"><span data-stu-id="731e5-139">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="731e5-140">Oracle Linux 7.2 oder höher</span><span class="sxs-lookup"><span data-stu-id="731e5-140">Oracle Linux 7.2 or higher</span></span>

    > [!NOTE]
    > <span data-ttu-id="731e5-141">Verteilungen und Versionen, die nicht explizit aufgeführt sind, werden nicht unterstützt (auch wenn sie von den offiziell unterstützten Distributionen abgeleitet sind).</span><span class="sxs-lookup"><span data-stu-id="731e5-141">Distributions and version that are not explicitly listed are unsupported (even if they are derived from the officially supported distributions).</span></span>


- <span data-ttu-id="731e5-142">Minimale Kernelversion 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="731e5-142">Minimum kernel version 3.10.0-327</span></span>

- <span data-ttu-id="731e5-143">Die `fanotify` Kerneloption muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="731e5-143">The `fanotify` kernel option must be enabled</span></span>

  > [!CAUTION]
  > <span data-ttu-id="731e5-144">Das parallele Ausführen von Defender für Endpunkt unter Linux mit anderen `fanotify` -basierten Sicherheitslösungen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="731e5-144">Running Defender for Endpoint on Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="731e5-145">Dies kann zu unvorhersehbaren Ergebnissen führen, z. B. zum Hängen des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="731e5-145">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="731e5-146">Speicherplatz: 1 GB</span><span class="sxs-lookup"><span data-stu-id="731e5-146">Disk space: 1 GB</span></span>

- <span data-ttu-id="731e5-147">/opt/microsoft/mdatp/sbin/wdavdaemon erfordert eine ausführbare Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="731e5-147">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="731e5-148">Weitere Informationen finden Sie unter "Sicherstellen, dass der Daemon über ausführbare Berechtigungen verfügt" in [der Problembehandlung von Installationsproblemen für Microsoft Defender für Endpunkt unter Linux.](/microsoft-365/security/defender-endpoint/linux-support-install)</span><span class="sxs-lookup"><span data-stu-id="731e5-148">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>

- <span data-ttu-id="731e5-149">Arbeitsspeicher: 1 GB</span><span class="sxs-lookup"><span data-stu-id="731e5-149">Memory: 1 GB</span></span>

    > [!NOTE]
    > <span data-ttu-id="731e5-150">Stellen Sie sicher, dass Sie über freien Speicherplatz in /var verfügen.</span><span class="sxs-lookup"><span data-stu-id="731e5-150">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="731e5-151">Die Lösung bietet derzeit Echtzeitschutz für die folgenden Dateisystemtypen:</span><span class="sxs-lookup"><span data-stu-id="731e5-151">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="731e5-152">Nachdem Sie den Dienst aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder Ihre Firewall konfigurieren, um ausgehende Verbindungen zwischen ihm und Ihren Endpunkten zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="731e5-152">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="731e5-153">Überwachungsframework ( `auditd` ) muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="731e5-153">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="731e5-154">Systemereignisse, die von Regeln erfasst werden, die hinzugefügt `/etc/audit/rules.d/` werden, werden `audit.log` (n) hinzugefügt und können sich auf die Hostüberwachung und die Upstreamsammlung auswirken.</span><span class="sxs-lookup"><span data-stu-id="731e5-154">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="731e5-155">Ereignisse, die von Microsoft Defender für Endpunkt unter Linux hinzugefügt wurden, werden mit `mdatp` Schlüssel gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="731e5-155">Events added by Microsoft Defender for Endpoint on Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="731e5-156">Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="731e5-156">Network connections</span></span>

<span data-ttu-id="731e5-157">In der folgenden herunterladbaren Tabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit denen ihr Netzwerk eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="731e5-157">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="731e5-158">Sie sollten sicherstellen, dass keine Firewall- oder Netzwerkfilterregeln vorhanden sind, die den Zugriff auf diese URLs verweigern würden.</span><span class="sxs-lookup"><span data-stu-id="731e5-158">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="731e5-159">Falls vorhanden, müssen Sie möglicherweise eine *Zulassungsregel* speziell für sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="731e5-159">If there are, you may need to create an *allow* rule specifically for them.</span></span>

| <span data-ttu-id="731e5-160">Kalkulationstabelle der Domänenliste</span><span class="sxs-lookup"><span data-stu-id="731e5-160">Spreadsheet of domains list</span></span> | <span data-ttu-id="731e5-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="731e5-161">Description</span></span> |
|:-----|:-----|
|![Miniaturbild für Microsoft Defender für Endpunkt-URLs-Tabellenkalkulation](images/mdatp-urls.png)<br/>  | <span data-ttu-id="731e5-163">Kalkulationstabelle für bestimmte DNS-Einträge für Dienststandorte, geografische Standorte und Das Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="731e5-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="731e5-164">Laden Sie das Arbeitsblatt hier herunter.</span><span class="sxs-lookup"><span data-stu-id="731e5-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="731e5-165">Eine spezifischere URL-Liste finden Sie unter [Konfigurieren von Proxy- und Internetverbindungseinstellungen.](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="731e5-165">For a more specific URL list, see [Configure proxy and internet connectivity settings](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="731e5-166">Defender für Endpunkt kann einen Proxyserver mithilfe der folgenden Ermittlungsmethoden ermitteln:</span><span class="sxs-lookup"><span data-stu-id="731e5-166">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="731e5-167">Transparenter Proxy</span><span class="sxs-lookup"><span data-stu-id="731e5-167">Transparent proxy</span></span>
- <span data-ttu-id="731e5-168">Manuelle Konfiguration statischer Proxys</span><span class="sxs-lookup"><span data-stu-id="731e5-168">Manual static proxy configuration</span></span>

<span data-ttu-id="731e5-169">Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="731e5-169">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="731e5-170">Für transparente Proxys ist keine zusätzliche Konfiguration für Defender für Endpunkt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="731e5-170">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="731e5-171">Führen Sie für statischen Proxy die Schritte in [manual Static Proxy Configuration](linux-static-proxy-configuration.md)aus.</span><span class="sxs-lookup"><span data-stu-id="731e5-171">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="731e5-172">PAC-, WPAD- und authentifizierte Proxys werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="731e5-172">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="731e5-173">Stellen Sie sicher, dass nur ein statischer oder ein transparenter Proxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="731e5-173">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="731e5-174">SSL-Überprüfungs- und -Abfangproxys werden aus Sicherheitsgründen ebenfalls nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="731e5-174">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="731e5-175">Konfigurieren Sie eine Ausnahme für die SSL-Überprüfung und Ihren Proxyserver, um Daten von Defender für Endpunkt unter Linux direkt an die relevanten URLs ohne Interception zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="731e5-175">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="731e5-176">Das Hinzufügen des Interception-Zertifikats zum globalen Speicher lässt keine Interception zu.</span><span class="sxs-lookup"><span data-stu-id="731e5-176">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="731e5-177">Informationen zur Problembehandlung finden Sie unter [Behandeln von Problemen mit der Cloudkonnektivität für Microsoft Defender für Endpunkt unter Linux.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="731e5-177">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="731e5-178">Aktualisieren von Microsoft Defender für Endpunkt unter Linux</span><span class="sxs-lookup"><span data-stu-id="731e5-178">How to update Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="731e5-179">Microsoft veröffentlicht regelmäßig Softwareupdates, um Leistung, Sicherheit und neue Features zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="731e5-179">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="731e5-180">Informationen zum Aktualisieren von Microsoft Defender für Endpunkt unter Linux finden Sie unter [Bereitstellen von Updates für Microsoft Defender für Endpunkt unter Linux.](linux-updates.md)</span><span class="sxs-lookup"><span data-stu-id="731e5-180">To update Microsoft Defender for Endpoint on Linux, refer to [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="731e5-181">So konfigurieren Sie Microsoft Defender für Endpunkt unter Linux</span><span class="sxs-lookup"><span data-stu-id="731e5-181">How to configure Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="731e5-182">Anleitungen zum Konfigurieren des Produkts in Unternehmensumgebungen finden Sie unter Festlegen von [Einstellungen für Microsoft Defender für Endpunkt unter Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="731e5-182">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="731e5-183">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="731e5-183">Resources</span></span>

- <span data-ttu-id="731e5-184">Weitere Informationen zur Protokollierung, Deinstallation oder anderen Themen finden Sie unter [Ressourcen.](linux-resources.md)</span><span class="sxs-lookup"><span data-stu-id="731e5-184">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
