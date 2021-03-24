---
title: Manuelles Bereitstellen von Microsoft Defender ATP für Linux
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender ATP für Linux manuell über die Befehlszeile bereitgestellt wird.
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
ms.openlocfilehash: 6726671a1e38d80a91787f495d3e09884bc879f4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064255"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-linux-manually"></a><span data-ttu-id="9e97c-104">Manuelles Bereitstellen von Microsoft Defender for Endpoint für Linux</span><span class="sxs-lookup"><span data-stu-id="9e97c-104">Deploy Microsoft Defender for Endpoint for Linux manually</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9e97c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9e97c-105">**Applies to:**</span></span>
- [<span data-ttu-id="9e97c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9e97c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="9e97c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e97c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9e97c-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9e97c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9e97c-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9e97c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="9e97c-110">In diesem Artikel wird beschrieben, wie Sie Microsoft Defender for Endpoint für Linux manuell bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9e97c-110">This article describes how to deploy Microsoft Defender for Endpoint for Linux manually.</span></span> <span data-ttu-id="9e97c-111">Eine erfolgreiche Bereitstellung erfordert den Abschluss aller folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="9e97c-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="9e97c-112">Manuelles Bereitstellen von Microsoft Defender for Endpoint für Linux</span><span class="sxs-lookup"><span data-stu-id="9e97c-112">Deploy Microsoft Defender for Endpoint for Linux manually</span></span>](#deploy-microsoft-defender-for-endpoint-for-linux-manually)
  - [<span data-ttu-id="9e97c-113">Voraussetzungen und Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="9e97c-113">Prerequisites and system requirements</span></span>](#prerequisites-and-system-requirements)
  - [<span data-ttu-id="9e97c-114">Konfigurieren des Linux-Softwarerepositorys</span><span class="sxs-lookup"><span data-stu-id="9e97c-114">Configure the Linux software repository</span></span>](#configure-the-linux-software-repository)
    - [<span data-ttu-id="9e97c-115">RHEL und Varianten (CentOS und Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="9e97c-115">RHEL and variants (CentOS and Oracle Linux)</span></span>](#rhel-and-variants-centos-and-oracle-linux)
    - [<span data-ttu-id="9e97c-116">SLES und Varianten</span><span class="sxs-lookup"><span data-stu-id="9e97c-116">SLES and variants</span></span>](#sles-and-variants)
    - [<span data-ttu-id="9e97c-117">Ubuntu- und Debian-Systeme</span><span class="sxs-lookup"><span data-stu-id="9e97c-117">Ubuntu and Debian systems</span></span>](#ubuntu-and-debian-systems)
  - [<span data-ttu-id="9e97c-118">Anwendungsinstallation</span><span class="sxs-lookup"><span data-stu-id="9e97c-118">Application installation</span></span>](#application-installation)
  - [<span data-ttu-id="9e97c-119">Herunterladen des Onboardingpakets</span><span class="sxs-lookup"><span data-stu-id="9e97c-119">Download the onboarding package</span></span>](#download-the-onboarding-package)
  - [<span data-ttu-id="9e97c-120">Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="9e97c-120">Client configuration</span></span>](#client-configuration)
  - [<span data-ttu-id="9e97c-121">Installerskript</span><span class="sxs-lookup"><span data-stu-id="9e97c-121">Installer script</span></span>](#installer-script)
  - [<span data-ttu-id="9e97c-122">Probleme bei der Protokollinstallation</span><span class="sxs-lookup"><span data-stu-id="9e97c-122">Log installation issues</span></span>](#log-installation-issues)
  - [<span data-ttu-id="9e97c-123">Betriebssystemupgrades</span><span class="sxs-lookup"><span data-stu-id="9e97c-123">Operating system upgrades</span></span>](#operating-system-upgrades)
  - [<span data-ttu-id="9e97c-124">Deinstallation</span><span class="sxs-lookup"><span data-stu-id="9e97c-124">Uninstallation</span></span>](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="9e97c-125">Voraussetzungen und Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="9e97c-125">Prerequisites and system requirements</span></span>

<span data-ttu-id="9e97c-126">Bevor Sie beginnen, finden Sie unter [Microsoft Defender for Endpoint for Linux](microsoft-defender-endpoint-linux.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.</span><span class="sxs-lookup"><span data-stu-id="9e97c-126">Before you get started, see [Microsoft Defender for Endpoint for Linux](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="configure-the-linux-software-repository"></a><span data-ttu-id="9e97c-127">Konfigurieren des Linux-Softwarerepositorys</span><span class="sxs-lookup"><span data-stu-id="9e97c-127">Configure the Linux software repository</span></span>

<span data-ttu-id="9e97c-128">Defender for Endpoint für Linux kann über einen der folgenden Kanäle bereitgestellt werden (unten als *[Channel]* bezeichnet): *insiders-fast*, *insiders-slow* oder *prod*. Jeder dieser Kanäle entspricht einem Linux-Softwarerepository.</span><span class="sxs-lookup"><span data-stu-id="9e97c-128">Defender for Endpoint for Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span> <span data-ttu-id="9e97c-129">Anweisungen zum Konfigurieren Ihres Geräts für die Verwendung eines dieser Repositorys finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="9e97c-129">Instructions for configuring your device to use one of these repositories are provided below.</span></span>

<span data-ttu-id="9e97c-130">Die Auswahl des Kanals bestimmt den Typ und die Häufigkeit der Updates, die auf Ihrem Gerät angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="9e97c-130">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="9e97c-131">Geräte in *insiders-fast* sind die ersten, die Updates und neue Features erhalten, gefolgt von *insiders-slow* und schließlich von *prod*.</span><span class="sxs-lookup"><span data-stu-id="9e97c-131">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="9e97c-132">Um eine Vorschau neuer Features anzuzeigen und frühzeitig Feedback zu geben, empfiehlt es sich, einige Geräte in Ihrem Unternehmen so zu konfigurieren, dass sie entweder *insider-schnell* oder *insider-slow verwenden.*</span><span class="sxs-lookup"><span data-stu-id="9e97c-132">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="9e97c-133">Wenn Sie den Kanal nach der Erstinstallation wechseln, muss das Produkt neu installiert werden.</span><span class="sxs-lookup"><span data-stu-id="9e97c-133">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="9e97c-134">Um den Produktkanal zu wechseln: Deinstallieren Sie das vorhandene Paket, konfigurieren Sie Ihr Gerät neu, um den neuen Kanal zu verwenden, und führen Sie die Schritte in diesem Dokument aus, um das Paket vom neuen Speicherort aus zu installieren.</span><span class="sxs-lookup"><span data-stu-id="9e97c-134">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

### <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="9e97c-135">RHEL und Varianten (CentOS und Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="9e97c-135">RHEL and variants (CentOS and Oracle Linux)</span></span>

- <span data-ttu-id="9e97c-136">Installieren, `yum-utils` wenn es noch nicht installiert ist:</span><span class="sxs-lookup"><span data-stu-id="9e97c-136">Install `yum-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo yum install yum-utils
    ```

- <span data-ttu-id="9e97c-137">Notieren Sie sich Ihre Verteilung und Version, und identifizieren Sie den nächstgelegenen Eintrag (nach Haupt, dann neben) unter `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="9e97c-137">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span> <span data-ttu-id="9e97c-138">Rhel 7.9 ist beispielsweise näher an 7,4 als 8.</span><span class="sxs-lookup"><span data-stu-id="9e97c-138">For instance, RHEL 7.9 is closer to 7.4 than to 8.</span></span>

    <span data-ttu-id="9e97c-139">Ersetzen Sie in den folgenden Befehlen *[distro]* und *[version]* durch die informationen, die Sie identifiziert haben:</span><span class="sxs-lookup"><span data-stu-id="9e97c-139">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    > [!NOTE]
    > <span data-ttu-id="9e97c-140">Ersetzen Sie bei Oracle Linux *[distro] durch* "rhel".</span><span class="sxs-lookup"><span data-stu-id="9e97c-140">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="9e97c-141">Beispiel: Wenn Sie CentOS 7 ausführen und MDE für Linux über den *prod-Kanal bereitstellen* möchten:</span><span class="sxs-lookup"><span data-stu-id="9e97c-141">For example, if you are running CentOS 7 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    <span data-ttu-id="9e97c-142">Oder wenn Sie neue Features auf ausgewählten Geräten erkunden möchten, sollten Sie MDE für Linux für *insiders-fast channel* bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="9e97c-142">Or if you wish to explore new features on selected devices, you might want to deploy MDE for Linux to *insiders-fast* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- <span data-ttu-id="9e97c-143">Installieren sie den öffentlichen Microsoft GPG-Schlüssel:</span><span class="sxs-lookup"><span data-stu-id="9e97c-143">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- <span data-ttu-id="9e97c-144">Laden Sie alle Metadaten für die derzeit aktivierten yum-Repositorys herunter, und verwenden Sie sie:</span><span class="sxs-lookup"><span data-stu-id="9e97c-144">Download and make usable all the metadata for the currently enabled yum repositories:</span></span>

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a><span data-ttu-id="9e97c-145">SLES und Varianten</span><span class="sxs-lookup"><span data-stu-id="9e97c-145">SLES and variants</span></span>

- <span data-ttu-id="9e97c-146">Notieren Sie sich Ihre Verteilung und Version, und identifizieren Sie den nächstgelegenen Eintrag (nach Haupt, dann neben) unter `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="9e97c-146">Note your distribution and version, and identify the closest entry(by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="9e97c-147">Ersetzen Sie in den folgenden Befehlen *[distro]* und *[version]* durch die von Ihnen identifizierten Informationen:</span><span class="sxs-lookup"><span data-stu-id="9e97c-147">In the following commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="9e97c-148">Beispiel: Wenn Sie SLES 12 ausführen und MDE für Linux über den *prod-Kanal bereitstellen* möchten:</span><span class="sxs-lookup"><span data-stu-id="9e97c-148">For example, if you are running SLES 12 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- <span data-ttu-id="9e97c-149">Installieren sie den öffentlichen Microsoft GPG-Schlüssel:</span><span class="sxs-lookup"><span data-stu-id="9e97c-149">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="9e97c-150">Ubuntu- und Debian-Systeme</span><span class="sxs-lookup"><span data-stu-id="9e97c-150">Ubuntu and Debian systems</span></span>

- <span data-ttu-id="9e97c-151">Installieren, `curl` wenn es noch nicht installiert ist:</span><span class="sxs-lookup"><span data-stu-id="9e97c-151">Install `curl` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install curl
    ```

- <span data-ttu-id="9e97c-152">Installieren, `libplist-utils` wenn es noch nicht installiert ist:</span><span class="sxs-lookup"><span data-stu-id="9e97c-152">Install `libplist-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install libplist-utils
    ```

- <span data-ttu-id="9e97c-153">Notieren Sie sich Ihre Verteilung und Version, und identifizieren Sie den nächstgelegenen Eintrag (nach Haupt, dann neben) unter `https://packages.microsoft.com/config` .</span><span class="sxs-lookup"><span data-stu-id="9e97c-153">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config`.</span></span>

    <span data-ttu-id="9e97c-154">Ersetzen Sie im folgenden Befehl *[distro]* und *[version]* durch die informationen, die Sie identifiziert haben:</span><span class="sxs-lookup"><span data-stu-id="9e97c-154">In the below command, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    <span data-ttu-id="9e97c-155">Wenn Sie beispielsweise Ubuntu 18.04 ausführen und MDE für Linux über den *prod-Kanal bereitstellen* möchten:</span><span class="sxs-lookup"><span data-stu-id="9e97c-155">For example, if you are running Ubuntu 18.04 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- <span data-ttu-id="9e97c-156">Installieren Sie die Repositorykonfiguration:</span><span class="sxs-lookup"><span data-stu-id="9e97c-156">Install the repository configuration:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```
    <span data-ttu-id="9e97c-157">Wenn Sie z. B. prod channel *ausgewählt* haben:</span><span class="sxs-lookup"><span data-stu-id="9e97c-157">For example, if you chose *prod* channel:</span></span>
    
    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```   

- <span data-ttu-id="9e97c-158">Installieren Sie `gpg` das Paket, wenn es noch nicht installiert ist:</span><span class="sxs-lookup"><span data-stu-id="9e97c-158">Install the `gpg` package if not already installed:</span></span>

    ```bash
    sudo apt-get install gpg
    ```

  <span data-ttu-id="9e97c-159">Wenn `gpg` nicht verfügbar, installieren Sie `gnupg` .</span><span class="sxs-lookup"><span data-stu-id="9e97c-159">If `gpg` is not available, then install `gnupg`.</span></span>

- <span data-ttu-id="9e97c-160">Installieren sie den öffentlichen Microsoft GPG-Schlüssel:</span><span class="sxs-lookup"><span data-stu-id="9e97c-160">Install the Microsoft GPG public key:</span></span>

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- <span data-ttu-id="9e97c-161">Installieren Sie den https-Treiber, wenn er noch nicht vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="9e97c-161">Install the https driver if it's not already present:</span></span>

    ```bash
    sudo apt-get install apt-transport-https
    ```

- <span data-ttu-id="9e97c-162">Aktualisieren der Repositorymetadaten:</span><span class="sxs-lookup"><span data-stu-id="9e97c-162">Update the repository metadata:</span></span>

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a><span data-ttu-id="9e97c-163">Anwendungsinstallation</span><span class="sxs-lookup"><span data-stu-id="9e97c-163">Application installation</span></span>

- <span data-ttu-id="9e97c-164">RHEL und Varianten (CentOS und Oracle Linux):</span><span class="sxs-lookup"><span data-stu-id="9e97c-164">RHEL and variants (CentOS and Oracle Linux):</span></span>

    ```bash
    sudo yum install mdatp
    ```

    <span data-ttu-id="9e97c-165">Wenn Sie mehrere Microsoft-Repositorys auf Ihrem Gerät konfiguriert haben, können Sie genau wissen, von welchem Repository das Paket installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9e97c-165">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="9e97c-166">Das folgende Beispiel zeigt, wie Sie das Paket über den Kanal installieren, wenn Sie auch den `production` `insiders-fast` Repositorykanal auf diesem Gerät konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="9e97c-166">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="9e97c-167">Diese Situation kann auftreten, wenn Sie mehrere Microsoft-Produkte auf Ihrem Gerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e97c-167">This situation can happen if you are using multiple Microsoft products on your device.</span></span> <span data-ttu-id="9e97c-168">Je nach Verteilung und Version des Servers kann sich der Repositoryalias von dem im folgenden Beispiel unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="9e97c-168">Depending on the distribution and the version of your server, the repository alias might be different than the one in the following example.</span></span>

    ```bash
    # list all repositories
    yum repolist
    ```
    ```Output
    ...
    packages-microsoft-com-prod               packages-microsoft-com-prod        316
    packages-microsoft-com-prod-insiders-fast packages-microsoft-com-prod-ins      2
    ...
    ```
    ```bash
    # install the package from the production repository
    sudo yum --enablerepo=packages-microsoft-com-prod install mdatp
    ```

- <span data-ttu-id="9e97c-169">SLES und Varianten:</span><span class="sxs-lookup"><span data-stu-id="9e97c-169">SLES and variants:</span></span>

    ```bash
    sudo zypper install mdatp
    ```

    <span data-ttu-id="9e97c-170">Wenn Sie mehrere Microsoft-Repositorys auf Ihrem Gerät konfiguriert haben, können Sie genau wissen, von welchem Repository das Paket installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9e97c-170">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="9e97c-171">Das folgende Beispiel zeigt, wie Sie das Paket über den Kanal installieren, wenn Sie auch den `production` `insiders-fast` Repositorykanal auf diesem Gerät konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="9e97c-171">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="9e97c-172">Diese Situation kann auftreten, wenn Sie mehrere Microsoft-Produkte auf Ihrem Gerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e97c-172">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

    ```bash
    zypper repos
    ```

    ```Output
    ...
    #  | Alias | Name | ...
    XX | packages-microsoft-com-insiders-fast | microsoft-insiders-fast | ...
    XX | packages-microsoft-com-prod | microsoft-prod | ...
    ...
    ```
    ```bash
    sudo zypper install packages-microsoft-com-prod:mdatp
    ```

- <span data-ttu-id="9e97c-173">Ubuntu- und Debian-System:</span><span class="sxs-lookup"><span data-stu-id="9e97c-173">Ubuntu and Debian system:</span></span>

    ```bash
    sudo apt-get install mdatp
    ```

    <span data-ttu-id="9e97c-174">Wenn Sie mehrere Microsoft-Repositorys auf Ihrem Gerät konfiguriert haben, können Sie genau wissen, von welchem Repository das Paket installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9e97c-174">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="9e97c-175">Das folgende Beispiel zeigt, wie Sie das Paket über den Kanal installieren, wenn Sie auch den `production` `insiders-fast` Repositorykanal auf diesem Gerät konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="9e97c-175">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="9e97c-176">Diese Situation kann auftreten, wenn Sie mehrere Microsoft-Produkte auf Ihrem Gerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e97c-176">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

    ```bash
    cat /etc/apt/sources.list.d/*
    ```
    ```Output
    deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/ubuntu/18.04/prod insiders-fast main
    deb [arch=amd64] https://packages.microsoft.com/ubuntu/18.04/prod bionic main
    ```
    ```bash
    sudo apt -t bionic install mdatp
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="9e97c-177">Herunterladen des Onboardingpakets</span><span class="sxs-lookup"><span data-stu-id="9e97c-177">Download the onboarding package</span></span>

<span data-ttu-id="9e97c-178">Laden Sie das Onboardingpaket aus dem Microsoft Defender Security Center herunter:</span><span class="sxs-lookup"><span data-stu-id="9e97c-178">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="9e97c-179">Wechseln Sie im Microsoft Defender Security Center zu **Einstellungen > Geräteverwaltung > Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="9e97c-179">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="9e97c-180">Wählen Sie im ersten Dropdownmenü **Linux Server** als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="9e97c-180">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="9e97c-181">Wählen Sie im zweiten Dropdownmenü lokales Skript (für bis zu **10 Geräte)** als Bereitstellungsmethode aus.</span><span class="sxs-lookup"><span data-stu-id="9e97c-181">In the second drop-down menu, select **Local Script (for up to 10 devices)** as the deployment method.</span></span>
3. <span data-ttu-id="9e97c-182">Wählen **Sie Onboardingpaket herunterladen aus.**</span><span class="sxs-lookup"><span data-stu-id="9e97c-182">Select **Download onboarding package**.</span></span> <span data-ttu-id="9e97c-183">Speichern Sie die Datei WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="9e97c-183">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Screenshot des Microsoft Defender Security Center](images/atp-portal-onboarding-linux.png)

4. <span data-ttu-id="9e97c-185">Überprüfen Sie an einer Eingabeaufforderung, ob Sie über die Datei verfügen.</span><span class="sxs-lookup"><span data-stu-id="9e97c-185">From a command prompt, verify that you have the file.</span></span>
    <span data-ttu-id="9e97c-186">Extrahieren sie den Inhalt des Archivs:</span><span class="sxs-lookup"><span data-stu-id="9e97c-186">Extract the contents of the archive:</span></span>

    ```bash
    ls -l
    ```

    ```Output
    total 8
    -rw-r--r-- 1 test  staff  5752 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: MicrosoftDefenderATPOnboardingLinuxServer.py
    ```


## <a name="client-configuration"></a><span data-ttu-id="9e97c-187">Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="9e97c-187">Client configuration</span></span>

1. <span data-ttu-id="9e97c-188">Kopieren MicrosoftDefenderATPOnboardingLinuxServer.py auf das Zielgerät.</span><span class="sxs-lookup"><span data-stu-id="9e97c-188">Copy MicrosoftDefenderATPOnboardingLinuxServer.py to the target device.</span></span>

    <span data-ttu-id="9e97c-189">Anfangs ist das Clientgerät nicht einer Organisation zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9e97c-189">Initially the client device is not associated with an organization.</span></span> <span data-ttu-id="9e97c-190">Beachten Sie, dass *das orgId-Attribut* leer ist:</span><span class="sxs-lookup"><span data-stu-id="9e97c-190">Note that the *orgId* attribute is blank:</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="9e97c-191">Führen MicrosoftDefenderATPOnboardingLinuxServer.py aus, und beachten Sie, dass Sie zum Ausführen dieses Befehls auf dem `python` Gerät installiert sein müssen:</span><span class="sxs-lookup"><span data-stu-id="9e97c-191">Run MicrosoftDefenderATPOnboardingLinuxServer.py, and note that, in order to run this command, you must have `python` installed on the device:</span></span>

    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. <span data-ttu-id="9e97c-192">Stellen Sie sicher, dass das Gerät jetzt Ihrer Organisation zugeordnet ist, und meldet eine gültige Organisations-ID:</span><span class="sxs-lookup"><span data-stu-id="9e97c-192">Verify that the device is now associated with your organization and reports a valid organization identifier:</span></span>

    ```bash
    mdatp health --field org_id
    ```

4. <span data-ttu-id="9e97c-193">Ein paar Minuten nach Abschluss der Installation können Sie den Status anzeigen, indem Sie den folgenden Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="9e97c-193">A few minutes after you complete the installation, you can see the status by running the following command.</span></span> <span data-ttu-id="9e97c-194">Ein Rückgabewert von `1` gibt an, dass das Produkt wie erwartet funktioniert:</span><span class="sxs-lookup"><span data-stu-id="9e97c-194">A return value of `1` denotes that the product is functioning as expected:</span></span>

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="9e97c-195">Wenn das Produkt zum ersten Mal gestartet wird, werden die neuesten Antischalwaredefinitionen heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="9e97c-195">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="9e97c-196">Je nach Internetverbindung kann dies bis zu ein paar Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="9e97c-196">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="9e97c-197">Während dieser Zeit gibt der obige Befehl den Wert `false` zurück.</span><span class="sxs-lookup"><span data-stu-id="9e97c-197">During this time the above command returns a value of `false`.</span></span> <span data-ttu-id="9e97c-198">Sie können den Status der Definitionsaktualisierung mithilfe des folgenden Befehls überprüfen:</span><span class="sxs-lookup"><span data-stu-id="9e97c-198">You can check the status of the definition update using the following command:</span></span>
    > ```bash
    > mdatp health --field definitions_status
    > ```
    > <span data-ttu-id="9e97c-199">Bitte beachten Sie, dass Sie nach Abschluss der Erstinstallation möglicherweise auch einen Proxy konfigurieren müssen.</span><span class="sxs-lookup"><span data-stu-id="9e97c-199">Please note that you may also need to configure a proxy after completing the initial installation.</span></span> <span data-ttu-id="9e97c-200">Weitere Informationen finden Sie unter [Configure Defender for Endpoint for Linux for static proxy discovery: Post-installation configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration).</span><span class="sxs-lookup"><span data-stu-id="9e97c-200">See [Configure Defender for Endpoint for Linux for static proxy discovery: Post-installation configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration).</span></span>

5. <span data-ttu-id="9e97c-201">Führen Sie einen Erkennungstest aus, um zu überprüfen, ob das Gerät ordnungsgemäß onboardiert ist, und melden Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="9e97c-201">Run a detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="9e97c-202">Führen Sie die folgenden Schritte auf dem neu integrierten Gerät aus:</span><span class="sxs-lookup"><span data-stu-id="9e97c-202">Perform the following steps on the newly onboarded device:</span></span>

    - <span data-ttu-id="9e97c-203">Stellen Sie sicher, dass der Echtzeitschutz aktiviert ist (wird durch das Ausführen des folgenden `1` Befehls bezeichnet):</span><span class="sxs-lookup"><span data-stu-id="9e97c-203">Ensure that real-time protection is enabled (denoted by a result of `1` from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - <span data-ttu-id="9e97c-204">Öffnen Sie ein Terminalfenster.</span><span class="sxs-lookup"><span data-stu-id="9e97c-204">Open a Terminal window.</span></span> <span data-ttu-id="9e97c-205">Kopieren Sie den folgenden Befehl, und führen Sie diesen aus:</span><span class="sxs-lookup"><span data-stu-id="9e97c-205">Copy and execute the following command:</span></span>

        ``` bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - <span data-ttu-id="9e97c-206">Die Datei sollte von Defender for Endpoint für Linux isoliert worden sein.</span><span class="sxs-lookup"><span data-stu-id="9e97c-206">The file should have been quarantined by Defender for Endpoint for Linux.</span></span> <span data-ttu-id="9e97c-207">Verwenden Sie den folgenden Befehl, um alle erkannten Bedrohungen auflisten:</span><span class="sxs-lookup"><span data-stu-id="9e97c-207">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

## <a name="installer-script"></a><span data-ttu-id="9e97c-208">Installerskript</span><span class="sxs-lookup"><span data-stu-id="9e97c-208">Installer script</span></span>

<span data-ttu-id="9e97c-209">Alternativ können Sie ein automatisiertes [Installer-Bash-Skript verwenden,](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) das in unserem [öffentlichen GitHub-Repository bereitgestellt wird.](https://github.com/microsoft/mdatp-xplat/)</span><span class="sxs-lookup"><span data-stu-id="9e97c-209">Alternatively, you can use an automated [installer bash script](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) provided in our [public GitHub repository](https://github.com/microsoft/mdatp-xplat/).</span></span>
<span data-ttu-id="9e97c-210">Das Skript identifiziert die Verteilung und Version und richtet das Gerät ein, um das neueste Paket zu ziehen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="9e97c-210">The script identifies the distribution and version, and sets up the device to pull the latest package and install it.</span></span>
<span data-ttu-id="9e97c-211">Sie können auch ein Onboarding mit einem bereitgestellten Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="9e97c-211">You can also onboard with a provided script.</span></span>

```bash
❯ ./mde_installer.sh --help
usage: basename ./mde_installer.sh [OPTIONS]
Options:
-c|--channel      specify the channel from which you want to install. Default: insiders-fast
-i|--install      install the product
-r|--remove       remove the product
-u|--upgrade      upgrade the existing product
-o|--onboard      onboard/offboard the product with <onboarding_script>
-p|--passive-mode set EPP to passive mode
-t|--tag          set a tag by declaring <name> and <value>. ex: -t GROUP Coders
-m|--min_req      enforce minimum requirements
-w|--clean        remove repo from package manager for a specific channel
-v|--version      print out script version
-h|--help         display help
```

<span data-ttu-id="9e97c-212">Weitere Informationen [finden Sie hier](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).</span><span class="sxs-lookup"><span data-stu-id="9e97c-212">Read more [here](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="9e97c-213">Probleme bei der Protokollinstallation</span><span class="sxs-lookup"><span data-stu-id="9e97c-213">Log installation issues</span></span>

<span data-ttu-id="9e97c-214">Weitere [Informationen zum](linux-resources.md#log-installation-issues) Suchen des automatisch generierten Protokolls, das beim Auftreten eines Fehlers vom Installationsprogramm erstellt wird, finden Sie unter Protokollinstallationsprobleme.</span><span class="sxs-lookup"><span data-stu-id="9e97c-214">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="9e97c-215">Betriebssystemupgrades</span><span class="sxs-lookup"><span data-stu-id="9e97c-215">Operating system upgrades</span></span>

<span data-ttu-id="9e97c-216">Wenn Sie Ihr Betriebssystem auf eine neue Hauptversion aktualisieren, müssen Sie zunächst Defender for Endpoint für Linux deinstallieren, das Upgrade installieren und schließlich Defender for Endpoint für Linux auf Ihrem Gerät neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9e97c-216">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint for Linux, install the upgrade, and finally reconfigure Defender for Endpoint for Linux on your device.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="9e97c-217">Deinstallation</span><span class="sxs-lookup"><span data-stu-id="9e97c-217">Uninstallation</span></span>

<span data-ttu-id="9e97c-218">Weitere Informationen zum Entfernen von Defender for Endpoint für Linux von Clientgeräten finden Sie unter [Deinstallieren.](linux-resources.md#uninstall)</span><span class="sxs-lookup"><span data-stu-id="9e97c-218">See [Uninstall](linux-resources.md#uninstall) for details on how to remove Defender for Endpoint for Linux from client devices.</span></span>
