---
title: Microsoft Defender ATP für Linux
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
ms.openlocfilehash: ce7b15a727ddfa9b0d2bc68b7901f2e79aaf0721
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064960"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="a4d66-104">Microsoft Defender for Endpoint for Linux</span><span class="sxs-lookup"><span data-stu-id="a4d66-104">Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a4d66-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a4d66-105">**Applies to:**</span></span>
- [<span data-ttu-id="a4d66-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a4d66-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="a4d66-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4d66-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a4d66-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a4d66-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a4d66-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a4d66-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a4d66-110">In diesem Thema wird beschrieben, wie Sie Microsoft Defender for Endpoint für Linux installieren, konfigurieren, aktualisieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4d66-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint for Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="a4d66-111">Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern neben Microsoft Defender for Endpoint für Linux verursacht wahrscheinlich Leistungsprobleme und unvorhersehbare Systemfehler.</span><span class="sxs-lookup"><span data-stu-id="a4d66-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Linux is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="a4d66-112">Installieren von Microsoft Defender for Endpoint für Linux</span><span class="sxs-lookup"><span data-stu-id="a4d66-112">How to install Microsoft Defender for Endpoint for Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="a4d66-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a4d66-113">Prerequisites</span></span>

- <span data-ttu-id="a4d66-114">Zugriff auf das Microsoft Defender Security Center-Portal</span><span class="sxs-lookup"><span data-stu-id="a4d66-114">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="a4d66-115">Linux-Verteilung mithilfe des [systemd System](https://systemd.io/) Managers</span><span class="sxs-lookup"><span data-stu-id="a4d66-115">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="a4d66-116">Anfängererfahrung in Linux- und BASH-Skripting</span><span class="sxs-lookup"><span data-stu-id="a4d66-116">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="a4d66-117">Administratorrechte auf dem Gerät (bei manueller Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="a4d66-117">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="a4d66-118">Installationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="a4d66-118">Installation instructions</span></span>

<span data-ttu-id="a4d66-119">Es gibt verschiedene Methoden und Bereitstellungstools, die Sie zum Installieren und Konfigurieren von Microsoft Defender for Endpoint für Linux verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a4d66-119">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="a4d66-120">Im Allgemeinen müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="a4d66-120">In general you need to take the following steps:</span></span>

- <span data-ttu-id="a4d66-121">Stellen Sie sicher, dass Sie über ein Microsoft Defender for Endpoint-Abonnement verfügen und auf das [Microsoft Defender for Endpoint-Portal zugreifen können.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="a4d66-121">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="a4d66-122">Stellen Sie Microsoft Defender for Endpoint für Linux mithilfe einer der folgenden Bereitstellungsmethoden zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="a4d66-122">Deploy Microsoft Defender for Endpoint for Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="a4d66-123">Das Befehlszeilentool:</span><span class="sxs-lookup"><span data-stu-id="a4d66-123">The command-line tool:</span></span>
    - [<span data-ttu-id="a4d66-124">Manuelle Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="a4d66-124">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="a4d66-125">Verwaltungstools von Drittanbietern:</span><span class="sxs-lookup"><span data-stu-id="a4d66-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="a4d66-126">Bereitstellen mit dem Tool für die Konfiguration von "Puppet"</span><span class="sxs-lookup"><span data-stu-id="a4d66-126">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="a4d66-127">Bereitstellen mithilfe des Ansible Configuration Management Tools</span><span class="sxs-lookup"><span data-stu-id="a4d66-127">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="a4d66-128">Wenn Installationsfehler auft werden, finden Sie informationen unter [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span><span class="sxs-lookup"><span data-stu-id="a4d66-128">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="a4d66-129">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="a4d66-129">System requirements</span></span>

- <span data-ttu-id="a4d66-130">Unterstützte Linux-Serververteilungen und -versionen:</span><span class="sxs-lookup"><span data-stu-id="a4d66-130">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="a4d66-131">Red Hat Enterprise Linux 7.2 oder höher</span><span class="sxs-lookup"><span data-stu-id="a4d66-131">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="a4d66-132">CentOS 7.2 oder höher</span><span class="sxs-lookup"><span data-stu-id="a4d66-132">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="a4d66-133">Ubuntu 16.04 LTS oder höher LTS</span><span class="sxs-lookup"><span data-stu-id="a4d66-133">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="a4d66-134">Debian 9 oder höher</span><span class="sxs-lookup"><span data-stu-id="a4d66-134">Debian 9 or higher</span></span>
  - <span data-ttu-id="a4d66-135">SUSE Linux Enterprise Server 12 oder höher</span><span class="sxs-lookup"><span data-stu-id="a4d66-135">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="a4d66-136">Oracle Linux 7.2 oder höher</span><span class="sxs-lookup"><span data-stu-id="a4d66-136">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="a4d66-137">Minimale Kernelversion 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="a4d66-137">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="a4d66-138">Die `fanotify` Kerneloption muss aktiviert sein</span><span class="sxs-lookup"><span data-stu-id="a4d66-138">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="a4d66-139">Das Ausführen von Defender for Endpoint für Linux neben anderen -basierten Sicherheitslösungen `fanotify` wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a4d66-139">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="a4d66-140">Dies kann zu unvorhersehbaren Ergebnissen führen, einschließlich des Aufhängens des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="a4d66-140">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="a4d66-141">Speicherplatz: 1 GB</span><span class="sxs-lookup"><span data-stu-id="a4d66-141">Disk space: 1GB</span></span>
- <span data-ttu-id="a4d66-142">Die Lösung bietet derzeit Echtzeitschutz für die folgenden Dateisystemtypen:</span><span class="sxs-lookup"><span data-stu-id="a4d66-142">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="a4d66-143">Nachdem Sie den Dienst aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder ihre Firewall so konfigurieren, dass ausgehende Verbindungen zwischen dem Dienst und Ihren Endpunkten zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="a4d66-143">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="a4d66-144">Das Überwachungsframework ( `auditd` ) muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="a4d66-144">Audit framework (`auditd`) must be enabled.</span></span>
  >[!NOTE]
  > <span data-ttu-id="a4d66-145">Systemereignisse, die von Regeln erfasst werden, die den Überwachungsprotokollen hinzugefügt werden, können sich auf die Hostüberwachung und `audit.logs` die Upstreamsammlung auswirken.</span><span class="sxs-lookup"><span data-stu-id="a4d66-145">System events captured by rules added to `audit.logs` will add to audit logs and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="a4d66-146">Ereignisse, die von Microsoft Defender für Endopoint für Linux hinzugefügt werden, werden mit dem Schlüssel `mdatp` markiert.</span><span class="sxs-lookup"><span data-stu-id="a4d66-146">Events added by Microsoft Defender for Endopoint for Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="a4d66-147">Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="a4d66-147">Network connections</span></span>

<span data-ttu-id="a4d66-148">In der folgenden herunterladbaren Kalkulationstabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit deren Netzwerk eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="a4d66-148">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="a4d66-149">Sie sollten sicherstellen, dass es keine Firewall- oder Netzwerkfilterregeln gibt, die den Zugriff auf diese URLs verweigern würden.</span><span class="sxs-lookup"><span data-stu-id="a4d66-149">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="a4d66-150">Falls dies derFall ist, müssen Sie möglicherweise eine *speziell* für sie zulässige Regel erstellen.</span><span class="sxs-lookup"><span data-stu-id="a4d66-150">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="a4d66-151">**Tabellenkalkulation der Domänenliste**</span><span class="sxs-lookup"><span data-stu-id="a4d66-151">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="a4d66-152">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a4d66-152">**Description**</span></span>|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="a4d66-154">Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme.</span><span class="sxs-lookup"><span data-stu-id="a4d66-154">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="a4d66-155">Laden Sie die Tabelle hier herunter.</span><span class="sxs-lookup"><span data-stu-id="a4d66-155">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="a4d66-156">Eine spezifischere URL-Liste finden Sie unter [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="a4d66-156">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="a4d66-157">Defender for Endpoint kann einen Proxyserver mithilfe der folgenden Ermittlungsmethoden ermitteln:</span><span class="sxs-lookup"><span data-stu-id="a4d66-157">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="a4d66-158">Transparenter Proxy</span><span class="sxs-lookup"><span data-stu-id="a4d66-158">Transparent proxy</span></span>
- <span data-ttu-id="a4d66-159">Manuelle Konfiguration statischer Proxys</span><span class="sxs-lookup"><span data-stu-id="a4d66-159">Manual static proxy configuration</span></span>

<span data-ttu-id="a4d66-160">Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="a4d66-160">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="a4d66-161">Für transparente Proxys ist keine zusätzliche Konfiguration für Defender for Endpoint erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a4d66-161">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="a4d66-162">Führen Sie für statischen Proxy die Schritte unter [Manuelle statische Proxykonfiguration aus.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="a4d66-162">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="a4d66-163">PAC-, WPAD- und authentifizierte Proxys werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a4d66-163">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="a4d66-164">Stellen Sie sicher, dass nur ein statischer oder transparenter Proxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a4d66-164">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="a4d66-165">Ssl-Überprüfung und Abfangen von Proxys werden aus Sicherheitsgründen ebenfalls nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a4d66-165">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="a4d66-166">Konfigurieren Sie eine Ausnahme für die SSL-Überprüfung und Ihren Proxyserver, um Daten von Defender for Endpoint für Linux direkt an die relevanten URLs ohne Abfangen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="a4d66-166">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="a4d66-167">Wenn Sie Ihr Abfangzertifikat zum globalen Speicher hinzufügen, ist das Abfangen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a4d66-167">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="a4d66-168">Informationen zur Problembehandlung finden Sie unter [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="a4d66-168">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="a4d66-169">Aktualisieren von Microsoft Defender for Endpoint für Linux</span><span class="sxs-lookup"><span data-stu-id="a4d66-169">How to update Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="a4d66-170">Microsoft veröffentlicht regelmäßig Softwareupdates, um leistung, Sicherheit und neue Features zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="a4d66-170">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="a4d66-171">Informationen zum Aktualisieren von Microsoft Defender for Endpoint für Linux finden Sie unter [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span><span class="sxs-lookup"><span data-stu-id="a4d66-171">To update Microsoft Defender for Endpoint for Linux, refer to [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="a4d66-172">Konfigurieren von Microsoft Defender for Endpoint für Linux</span><span class="sxs-lookup"><span data-stu-id="a4d66-172">How to configure Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="a4d66-173">Anleitungen zum Konfigurieren des Produkts in Unternehmensumgebungen finden Sie unter [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="a4d66-173">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="a4d66-174">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="a4d66-174">Resources</span></span>

- <span data-ttu-id="a4d66-175">Weitere Informationen zum Protokollieren, Deinstallieren oder anderen Themen finden Sie unter [Ressourcen](linux-resources.md).</span><span class="sxs-lookup"><span data-stu-id="a4d66-175">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
