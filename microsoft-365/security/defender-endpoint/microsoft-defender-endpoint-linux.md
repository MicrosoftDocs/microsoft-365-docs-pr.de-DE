---
title: Microsoft Defender for Endpoint unter Linux
ms.reviewer: ''
description: Beschreibt die Installation und Verwendung von Microsoft Defender ATP für Linux.
keywords: microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 0fea9d4dd46be2a77ea27728787a43b5273f92f5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687757"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="cacf5-104">Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="cacf5-104">Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cacf5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cacf5-105">**Applies to:**</span></span>
- [<span data-ttu-id="cacf5-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cacf5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cacf5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cacf5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cacf5-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="cacf5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cacf5-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cacf5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="cacf5-110">In diesem Thema wird beschrieben, wie Sie Microsoft Defender for Endpoint unter Linux installieren, konfigurieren, aktualisieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="cacf5-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="cacf5-111">Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern neben Microsoft Defender for Endpoint unter Linux führt wahrscheinlich zu Leistungsproblemen und unvorhersehbaren Nebenwirkungen.</span><span class="sxs-lookup"><span data-stu-id="cacf5-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="cacf5-112">Wenn der Schutz von Nicht-Microsoft-Endpunkten eine absolute Anforderung in Ihrer Umgebung ist, können Sie die Funktionen von Defender for Endpoint für Linux EDR weiterhin sicher nutzen, nachdem Sie die Antivirenfunktionen so konfiguriert haben, dass sie im passiven Modus [ausgeführt werden.](linux-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="cacf5-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint for Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="cacf5-113">Installieren von Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="cacf5-113">How to install Microsoft Defender for Endpoint on Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="cacf5-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cacf5-114">Prerequisites</span></span>

- <span data-ttu-id="cacf5-115">Zugriff auf das Microsoft Defender Security Center-Portal</span><span class="sxs-lookup"><span data-stu-id="cacf5-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="cacf5-116">Linux-Verteilung mithilfe des [systemd System](https://systemd.io/) Managers</span><span class="sxs-lookup"><span data-stu-id="cacf5-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="cacf5-117">Anfängererfahrung in Linux- und BASH-Skripting</span><span class="sxs-lookup"><span data-stu-id="cacf5-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="cacf5-118">Administratorrechte auf dem Gerät (bei manueller Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="cacf5-118">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="cacf5-119">Installationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="cacf5-119">Installation instructions</span></span>

<span data-ttu-id="cacf5-120">Es gibt mehrere Methoden und Bereitstellungstools, die Sie zum Installieren und Konfigurieren von Microsoft Defender for Endpoint unter Linux verwenden können.</span><span class="sxs-lookup"><span data-stu-id="cacf5-120">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="cacf5-121">Im Allgemeinen müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="cacf5-121">In general you need to take the following steps:</span></span>

- <span data-ttu-id="cacf5-122">Stellen Sie sicher, dass Sie über ein Microsoft Defender for Endpoint-Abonnement verfügen und auf das [Microsoft Defender for Endpoint-Portal zugreifen können.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="cacf5-122">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="cacf5-123">Stellen Sie Microsoft Defender for Endpoint unter Linux mithilfe einer der folgenden Bereitstellungsmethoden zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="cacf5-123">Deploy Microsoft Defender for Endpoint on Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="cacf5-124">Das Befehlszeilentool:</span><span class="sxs-lookup"><span data-stu-id="cacf5-124">The command-line tool:</span></span>
    - [<span data-ttu-id="cacf5-125">Manuelle Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="cacf5-125">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="cacf5-126">Verwaltungstools von Drittanbietern:</span><span class="sxs-lookup"><span data-stu-id="cacf5-126">Third-party management tools:</span></span>
    - [<span data-ttu-id="cacf5-127">Bereitstellen mit dem Tool für die Konfiguration von "Puppet"</span><span class="sxs-lookup"><span data-stu-id="cacf5-127">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="cacf5-128">Bereitstellen mithilfe des Ansible Configuration Management Tools</span><span class="sxs-lookup"><span data-stu-id="cacf5-128">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="cacf5-129">Wenn Installationsfehler auft werden, finden Sie informationen unter [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span><span class="sxs-lookup"><span data-stu-id="cacf5-129">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="cacf5-130">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="cacf5-130">System requirements</span></span>

- <span data-ttu-id="cacf5-131">Unterstützte Linux-Serververteilungen und -versionen:</span><span class="sxs-lookup"><span data-stu-id="cacf5-131">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="cacf5-132">Red Hat Enterprise Linux 7.2 oder höher</span><span class="sxs-lookup"><span data-stu-id="cacf5-132">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="cacf5-133">CentOS 7.2 oder höher</span><span class="sxs-lookup"><span data-stu-id="cacf5-133">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="cacf5-134">Ubuntu 16.04 LTS oder höher LTS</span><span class="sxs-lookup"><span data-stu-id="cacf5-134">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="cacf5-135">Debian 9 oder höher</span><span class="sxs-lookup"><span data-stu-id="cacf5-135">Debian 9 or higher</span></span>
  - <span data-ttu-id="cacf5-136">SUSE Linux Enterprise Server 12 oder höher</span><span class="sxs-lookup"><span data-stu-id="cacf5-136">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="cacf5-137">Oracle Linux 7.2 oder höher</span><span class="sxs-lookup"><span data-stu-id="cacf5-137">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="cacf5-138">Minimale Kernelversion 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="cacf5-138">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="cacf5-139">Die `fanotify` Kerneloption muss aktiviert sein</span><span class="sxs-lookup"><span data-stu-id="cacf5-139">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="cacf5-140">Das Ausführen von Defender for Endpoint für Linux neben anderen -basierten Sicherheitslösungen `fanotify` wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cacf5-140">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="cacf5-141">Dies kann zu unvorhersehbaren Ergebnissen führen, einschließlich des Aufhängens des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="cacf5-141">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="cacf5-142">Speicherplatz: 1 GB</span><span class="sxs-lookup"><span data-stu-id="cacf5-142">Disk space: 1GB</span></span>
- <span data-ttu-id="cacf5-143">/opt/microsoft/mdatp/sbin/wdavdaemon erfordert ausführbare Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="cacf5-143">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="cacf5-144">Weitere Informationen finden Sie unter "Sicherstellen, dass der Daemon über ausführbare Berechtigungen verfügt" unter Problembehandlung von Installationsproblemen [für Microsoft Defender ATP für Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span><span class="sxs-lookup"><span data-stu-id="cacf5-144">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender ATP for Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>
- <span data-ttu-id="cacf5-145">Arbeitsspeicher: 1 GB</span><span class="sxs-lookup"><span data-stu-id="cacf5-145">Memory: 1GB</span></span>
    > [!NOTE]
    > <span data-ttu-id="cacf5-146">Stellen Sie sicher, dass Sie freien Speicherplatz in /var haben.</span><span class="sxs-lookup"><span data-stu-id="cacf5-146">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="cacf5-147">Die Lösung bietet derzeit Echtzeitschutz für die folgenden Dateisystemtypen:</span><span class="sxs-lookup"><span data-stu-id="cacf5-147">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="cacf5-148">Nachdem Sie den Dienst aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder ihre Firewall so konfigurieren, dass ausgehende Verbindungen zwischen dem Dienst und Ihren Endpunkten zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="cacf5-148">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="cacf5-149">Das Überwachungsframework ( `auditd` ) muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="cacf5-149">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="cacf5-150">Systemereignisse, die von Regeln erfasst werden, die hinzugefügt werden, werden zu (n) hinzugefügt und können sich auf die `/etc/audit/rules.d/` `audit.log` Hostüberwachung und die Upstreamsammlung auswirken.</span><span class="sxs-lookup"><span data-stu-id="cacf5-150">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="cacf5-151">Ereignisse, die von Microsoft Defender for Endpoint unter Linux hinzugefügt werden, werden mit dem Schlüssel `mdatp` markiert.</span><span class="sxs-lookup"><span data-stu-id="cacf5-151">Events added by Microsoft Defender for Endpoint on Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="cacf5-152">Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="cacf5-152">Network connections</span></span>

<span data-ttu-id="cacf5-153">In der folgenden herunterladbaren Kalkulationstabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit deren Netzwerk eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="cacf5-153">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="cacf5-154">Sie sollten sicherstellen, dass es keine Firewall- oder Netzwerkfilterregeln gibt, die den Zugriff auf diese URLs verweigern würden.</span><span class="sxs-lookup"><span data-stu-id="cacf5-154">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="cacf5-155">Falls dies derFall ist, müssen Sie möglicherweise eine *speziell* für sie zulässige Regel erstellen.</span><span class="sxs-lookup"><span data-stu-id="cacf5-155">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="cacf5-156">**Tabellenkalkulation der Domänenliste**</span><span class="sxs-lookup"><span data-stu-id="cacf5-156">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="cacf5-157">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="cacf5-157">**Description**</span></span>|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="cacf5-159">Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme.</span><span class="sxs-lookup"><span data-stu-id="cacf5-159">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="cacf5-160">Laden Sie die Tabelle hier herunter.</span><span class="sxs-lookup"><span data-stu-id="cacf5-160">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="cacf5-161">Eine spezifischere URL-Liste finden Sie unter [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="cacf5-161">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="cacf5-162">Defender for Endpoint kann einen Proxyserver mithilfe der folgenden Ermittlungsmethoden ermitteln:</span><span class="sxs-lookup"><span data-stu-id="cacf5-162">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="cacf5-163">Transparenter Proxy</span><span class="sxs-lookup"><span data-stu-id="cacf5-163">Transparent proxy</span></span>
- <span data-ttu-id="cacf5-164">Manuelle Konfiguration statischer Proxys</span><span class="sxs-lookup"><span data-stu-id="cacf5-164">Manual static proxy configuration</span></span>

<span data-ttu-id="cacf5-165">Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="cacf5-165">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="cacf5-166">Für transparente Proxys ist keine zusätzliche Konfiguration für Defender for Endpoint erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cacf5-166">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="cacf5-167">Führen Sie für statischen Proxy die Schritte unter [Manuelle statische Proxykonfiguration aus.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="cacf5-167">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="cacf5-168">PAC-, WPAD- und authentifizierte Proxys werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cacf5-168">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="cacf5-169">Stellen Sie sicher, dass nur ein statischer oder transparenter Proxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cacf5-169">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="cacf5-170">Ssl-Überprüfung und Abfangen von Proxys werden aus Sicherheitsgründen ebenfalls nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cacf5-170">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="cacf5-171">Konfigurieren Sie eine Ausnahme für die SSL-Überprüfung und Ihren Proxyserver, um Daten von Defender for Endpoint unter Linux direkt an die relevanten URLs ohne Abfangen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="cacf5-171">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="cacf5-172">Wenn Sie Ihr Abfangzertifikat zum globalen Speicher hinzufügen, ist das Abfangen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="cacf5-172">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="cacf5-173">Informationen zur Problembehandlung finden Sie unter [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="cacf5-173">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="cacf5-174">Aktualisieren von Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="cacf5-174">How to update Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="cacf5-175">Microsoft veröffentlicht regelmäßig Softwareupdates, um leistung, Sicherheit und neue Features zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="cacf5-175">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="cacf5-176">Informationen zum Aktualisieren von Microsoft Defender for Endpoint unter Linux finden Sie unter [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span><span class="sxs-lookup"><span data-stu-id="cacf5-176">To update Microsoft Defender for Endpoint on Linux, refer to [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="cacf5-177">Konfigurieren von Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="cacf5-177">How to configure Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="cacf5-178">Anleitungen zum Konfigurieren des Produkts in Unternehmensumgebungen finden Sie unter [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="cacf5-178">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="cacf5-179">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="cacf5-179">Resources</span></span>

- <span data-ttu-id="cacf5-180">Weitere Informationen zum Protokollieren, Deinstallieren oder anderen Themen finden Sie unter [Ressourcen](linux-resources.md).</span><span class="sxs-lookup"><span data-stu-id="cacf5-180">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
