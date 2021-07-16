---
title: Manuelles Bereitstellen von Microsoft Defender für Endpunkt unter Linux
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter Linux manuell über die Befehlszeile bereitgestellt wird.
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4c4ed845a31f044e17c97e0b43adfc86dd3f68ba
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454805"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a><span data-ttu-id="4c291-104">Manuelles Bereitstellen von Microsoft Defender für Endpunkt unter Linux</span><span class="sxs-lookup"><span data-stu-id="4c291-104">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4c291-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4c291-105">**Applies to:**</span></span>
- [<span data-ttu-id="4c291-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4c291-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4c291-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c291-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4c291-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="4c291-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4c291-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="4c291-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="4c291-110">In diesem Artikel wird beschrieben, wie Sie Microsoft Defender für Endpunkt manuell unter Linux bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4c291-110">This article describes how to deploy Microsoft Defender for Endpoint on Linux manually.</span></span> <span data-ttu-id="4c291-111">Eine erfolgreiche Bereitstellung erfordert den Abschluss aller folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="4c291-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="4c291-112">Manuelles Bereitstellen von Microsoft Defender für Endpunkt unter Linux</span><span class="sxs-lookup"><span data-stu-id="4c291-112">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>](#deploy-microsoft-defender-for-endpoint-on-linux-manually)
  - [<span data-ttu-id="4c291-113">Voraussetzungen und Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="4c291-113">Prerequisites and system requirements</span></span>](#prerequisites-and-system-requirements)
  - [<span data-ttu-id="4c291-114">Konfigurieren des Linux-Software-Repositorys</span><span class="sxs-lookup"><span data-stu-id="4c291-114">Configure the Linux software repository</span></span>](#configure-the-linux-software-repository)
    - [<span data-ttu-id="4c291-115">RHEL und Varianten (CentOS und Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="4c291-115">RHEL and variants (CentOS and Oracle Linux)</span></span>](#rhel-and-variants-centos-and-oracle-linux)
    - [<span data-ttu-id="4c291-116">SLES und Varianten</span><span class="sxs-lookup"><span data-stu-id="4c291-116">SLES and variants</span></span>](#sles-and-variants)
    - [<span data-ttu-id="4c291-117">Ubuntu- und Ubuntu-Systeme</span><span class="sxs-lookup"><span data-stu-id="4c291-117">Ubuntu and Debian systems</span></span>](#ubuntu-and-debian-systems)
  - [<span data-ttu-id="4c291-118">Anwendungsinstallation</span><span class="sxs-lookup"><span data-stu-id="4c291-118">Application installation</span></span>](#application-installation)
  - [<span data-ttu-id="4c291-119">Herunterladen des Onboardingpakets</span><span class="sxs-lookup"><span data-stu-id="4c291-119">Download the onboarding package</span></span>](#download-the-onboarding-package)
  - [<span data-ttu-id="4c291-120">Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="4c291-120">Client configuration</span></span>](#client-configuration)
  - [<span data-ttu-id="4c291-121">Installer-Skript</span><span class="sxs-lookup"><span data-stu-id="4c291-121">Installer script</span></span>](#installer-script)
  - [<span data-ttu-id="4c291-122">Protokollieren von Installationsproblemen</span><span class="sxs-lookup"><span data-stu-id="4c291-122">Log installation issues</span></span>](#log-installation-issues)
  - [<span data-ttu-id="4c291-123">Betriebssystemupgrades</span><span class="sxs-lookup"><span data-stu-id="4c291-123">Operating system upgrades</span></span>](#operating-system-upgrades)
  - [<span data-ttu-id="4c291-124">Deinstallation</span><span class="sxs-lookup"><span data-stu-id="4c291-124">Uninstallation</span></span>](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="4c291-125">Voraussetzungen und Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="4c291-125">Prerequisites and system requirements</span></span>

<span data-ttu-id="4c291-126">Bevor Sie beginnen, finden Sie unter [Microsoft Defender für Endpunkt unter Linux](microsoft-defender-endpoint-linux.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.</span><span class="sxs-lookup"><span data-stu-id="4c291-126">Before you get started, see [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="configure-the-linux-software-repository"></a><span data-ttu-id="4c291-127">Konfigurieren des Linux-Software-Repositorys</span><span class="sxs-lookup"><span data-stu-id="4c291-127">Configure the Linux software repository</span></span>

<span data-ttu-id="4c291-128">Defender für Endpunkt unter Linux kann von einem der folgenden Kanäle bereitgestellt werden (unten als *[Kanal]* bezeichnet): *insiders-fast*, *insiders-slow* oder *prod*. Jeder dieser Kanäle entspricht einem Linux-Software-Repository.</span><span class="sxs-lookup"><span data-stu-id="4c291-128">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span> <span data-ttu-id="4c291-129">Anweisungen zum Konfigurieren Ihres Geräts für die Verwendung eines dieser Repositorys finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="4c291-129">Instructions for configuring your device to use one of these repositories are provided below.</span></span>

<span data-ttu-id="4c291-130">Die Wahl des Kanals bestimmt den Typ und die Häufigkeit von Updates, die auf Ihrem Gerät angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="4c291-130">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="4c291-131">Geräte in *Insider-Fast* sind die ersten Geräte, die Updates und neue Features erhalten, gefolgt von *insider-slow* und schließlich von *prod*.</span><span class="sxs-lookup"><span data-stu-id="4c291-131">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="4c291-132">Um eine Vorschau der neuen Features anzuzeigen und frühzeitigEs Feedback zu geben, empfiehlt es sich, einige Geräte in Ihrem Unternehmen so zu konfigurieren, dass sie entweder *insiderschnell* oder langsam verwendet *werden.*</span><span class="sxs-lookup"><span data-stu-id="4c291-132">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="4c291-133">Um den Kanal nach der Erstinstallation zu wechseln, muss das Produkt neu installiert werden.</span><span class="sxs-lookup"><span data-stu-id="4c291-133">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="4c291-134">Um den Produktkanal zu wechseln: Deinstallieren Sie das vorhandene Paket, konfigurieren Sie Ihr Gerät erneut für die Verwendung des neuen Kanals, und führen Sie die Schritte in diesem Dokument aus, um das Paket vom neuen Speicherort zu installieren.</span><span class="sxs-lookup"><span data-stu-id="4c291-134">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

### <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="4c291-135">RHEL und Varianten (CentOS und Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="4c291-135">RHEL and variants (CentOS and Oracle Linux)</span></span>

- <span data-ttu-id="4c291-136">Installieren `yum-utils` Sie, wenn es noch nicht installiert ist:</span><span class="sxs-lookup"><span data-stu-id="4c291-136">Install `yum-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo yum install yum-utils
    ```

- <span data-ttu-id="4c291-137">Notieren Sie sich Ihre Verteilung und Version, und ermitteln Sie den nächstgelegenen Eintrag (nach Haupt- und nebenversion) unter `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="4c291-137">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span> <span data-ttu-id="4c291-138">Beispielsweise liegt RHEL 7.9 näher bei 7,4 als bei 8.</span><span class="sxs-lookup"><span data-stu-id="4c291-138">For instance, RHEL 7.9 is closer to 7.4 than to 8.</span></span>

    <span data-ttu-id="4c291-139">Ersetzen Sie in den folgenden Befehlen *[distro]* und *[version]* durch die von Ihnen identifizierten Informationen:</span><span class="sxs-lookup"><span data-stu-id="4c291-139">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c291-140">Ersetzen Sie *[distro]* bei Oracle Linux durch "rhel".</span><span class="sxs-lookup"><span data-stu-id="4c291-140">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="4c291-141">Wenn Sie z. B. CentOS 7 ausführen und Defender für Endpunkt unter Linux über den *Prod-Kanal* bereitstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="4c291-141">For example, if you are running CentOS 7 and want to deploy Defender for Endpoint on Linux from the *prod* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    <span data-ttu-id="4c291-142">Oder wenn Sie neue Features auf ausgewählten Geräten erkunden möchten, sollten Sie Microsoft Defender für Endpunkt unter Linux im *Insider-Fast-Kanal* bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="4c291-142">Or if you wish to explore new features on selected devices, you might want to deploy Microsoft Defender for Endpoint on Linux to *insiders-fast* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- <span data-ttu-id="4c291-143">Installieren Sie den öffentlichen Microsoft GPG-Schlüssel:</span><span class="sxs-lookup"><span data-stu-id="4c291-143">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- <span data-ttu-id="4c291-144">Laden Sie alle Metadaten für die derzeit aktivierten Yum-Repositorys herunter, und verwenden Sie sie:</span><span class="sxs-lookup"><span data-stu-id="4c291-144">Download and make usable all the metadata for the currently enabled yum repositories:</span></span>

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a><span data-ttu-id="4c291-145">SLES und Varianten</span><span class="sxs-lookup"><span data-stu-id="4c291-145">SLES and variants</span></span>

- <span data-ttu-id="4c291-146">Notieren Sie sich Ihre Verteilung und Version, und ermitteln Sie den nächstgelegenen Eintrag (nach Haupt- und nebenversion) unter `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="4c291-146">Note your distribution and version, and identify the closest entry(by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="4c291-147">Ersetzen Sie in den folgenden Befehlen *[distro]* und *[version]* durch die von Ihnen identifizierten Informationen:</span><span class="sxs-lookup"><span data-stu-id="4c291-147">In the following commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="4c291-148">Wenn Sie beispielsweise SLES 12 ausführen und Microsoft Defender für Endpunkt unter Linux über den *prod-Kanal* bereitstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="4c291-148">For example, if you are running SLES 12 and wish to deploy Microsoft Defender for Endpoint on Linux from the *prod* channel:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- <span data-ttu-id="4c291-149">Installieren Sie den öffentlichen Microsoft GPG-Schlüssel:</span><span class="sxs-lookup"><span data-stu-id="4c291-149">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="4c291-150">Ubuntu- und Ubuntu-Systeme</span><span class="sxs-lookup"><span data-stu-id="4c291-150">Ubuntu and Debian systems</span></span>

- <span data-ttu-id="4c291-151">Installieren `curl` Sie, wenn es noch nicht installiert ist:</span><span class="sxs-lookup"><span data-stu-id="4c291-151">Install `curl` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install curl
    ```

- <span data-ttu-id="4c291-152">Installieren `libplist-utils` Sie, wenn es noch nicht installiert ist:</span><span class="sxs-lookup"><span data-stu-id="4c291-152">Install `libplist-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install libplist-utils
    ```

- <span data-ttu-id="4c291-153">Notieren Sie sich Ihre Verteilung und Version, und ermitteln Sie den nächstgelegenen Eintrag (nach Haupt- und nebenversion) unter `https://packages.microsoft.com/config` .</span><span class="sxs-lookup"><span data-stu-id="4c291-153">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config`.</span></span>

    <span data-ttu-id="4c291-154">Ersetzen Sie im folgenden Befehl *[distro]* und *[version]* durch die von Ihnen identifizierten Informationen:</span><span class="sxs-lookup"><span data-stu-id="4c291-154">In the below command, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    <span data-ttu-id="4c291-155">Wenn Sie beispielsweise Ubuntu 18.04 ausführen und MDE für Linux über den *Prod-Kanal* bereitstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="4c291-155">For example, if you are running Ubuntu 18.04 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- <span data-ttu-id="4c291-156">Installieren Sie die Repositorykonfiguration:</span><span class="sxs-lookup"><span data-stu-id="4c291-156">Install the repository configuration:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```
    <span data-ttu-id="4c291-157">Wenn Sie *z. B. "Prod Channel"* ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="4c291-157">For example, if you chose *prod* channel:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```

- <span data-ttu-id="4c291-158">Installieren Sie das `gpg` Paket, wenn es nicht bereits installiert ist:</span><span class="sxs-lookup"><span data-stu-id="4c291-158">Install the `gpg` package if not already installed:</span></span>

    ```bash
    sudo apt-get install gpg
    ```

  <span data-ttu-id="4c291-159">Wenn `gpg` nicht verfügbar, installieren Sie `gnupg` .</span><span class="sxs-lookup"><span data-stu-id="4c291-159">If `gpg` is not available, then install `gnupg`.</span></span>

- <span data-ttu-id="4c291-160">Installieren Sie den öffentlichen Microsoft GPG-Schlüssel:</span><span class="sxs-lookup"><span data-stu-id="4c291-160">Install the Microsoft GPG public key:</span></span>

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- <span data-ttu-id="4c291-161">Installieren Sie den HTTPS-Treiber, wenn er noch nicht vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="4c291-161">Install the https driver if it's not already present:</span></span>

    ```bash
    sudo apt-get install apt-transport-https
    ```

- <span data-ttu-id="4c291-162">Aktualisieren Sie die Repositorymetadaten:</span><span class="sxs-lookup"><span data-stu-id="4c291-162">Update the repository metadata:</span></span>

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a><span data-ttu-id="4c291-163">Anwendungsinstallation</span><span class="sxs-lookup"><span data-stu-id="4c291-163">Application installation</span></span>

- <span data-ttu-id="4c291-164">RHEL und Varianten (CentOS und Oracle Linux):</span><span class="sxs-lookup"><span data-stu-id="4c291-164">RHEL and variants (CentOS and Oracle Linux):</span></span>

    ```bash
    sudo yum install mdatp
    ```

    <span data-ttu-id="4c291-165">Wenn Sie mehrere Microsoft-Repositorys auf Ihrem Gerät konfiguriert haben, können Sie genau angeben, aus welchem Repository das Paket installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c291-165">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="4c291-166">Das folgende Beispiel zeigt, wie Sie das Paket aus dem `production` Kanal installieren, wenn Sie auch den `insiders-fast` Repositorykanal auf diesem Gerät konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="4c291-166">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="4c291-167">Diese Situation kann auftreten, wenn Sie mehrere Microsoft-Produkte auf Ihrem Gerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c291-167">This situation can happen if you are using multiple Microsoft products on your device.</span></span> <span data-ttu-id="4c291-168">Je nach Verteilung und Version des Servers kann sich der Repositoryalias von dem im folgenden Beispiel unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4c291-168">Depending on the distribution and the version of your server, the repository alias might be different than the one in the following example.</span></span>

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

- <span data-ttu-id="4c291-169">SLES und Varianten:</span><span class="sxs-lookup"><span data-stu-id="4c291-169">SLES and variants:</span></span>

    ```bash
    sudo zypper install mdatp
    ```

    <span data-ttu-id="4c291-170">Wenn Sie mehrere Microsoft-Repositorys auf Ihrem Gerät konfiguriert haben, können Sie genau angeben, aus welchem Repository das Paket installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c291-170">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="4c291-171">Das folgende Beispiel zeigt, wie Sie das Paket aus dem `production` Kanal installieren, wenn Sie auch den `insiders-fast` Repositorykanal auf diesem Gerät konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="4c291-171">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="4c291-172">Diese Situation kann auftreten, wenn Sie mehrere Microsoft-Produkte auf Ihrem Gerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c291-172">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

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

- <span data-ttu-id="4c291-173">Ubuntu- und Ubuntu-System:</span><span class="sxs-lookup"><span data-stu-id="4c291-173">Ubuntu and Debian system:</span></span>

    ```bash
    sudo apt-get install mdatp
    ```

    <span data-ttu-id="4c291-174">Wenn Sie mehrere Microsoft-Repositorys auf Ihrem Gerät konfiguriert haben, können Sie genau angeben, aus welchem Repository das Paket installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c291-174">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="4c291-175">Das folgende Beispiel zeigt, wie Sie das Paket aus dem `production` Kanal installieren, wenn Sie auch den `insiders-fast` Repositorykanal auf diesem Gerät konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="4c291-175">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="4c291-176">Diese Situation kann auftreten, wenn Sie mehrere Microsoft-Produkte auf Ihrem Gerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c291-176">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

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

## <a name="download-the-onboarding-package"></a><span data-ttu-id="4c291-177">Herunterladen des Onboardingpakets</span><span class="sxs-lookup"><span data-stu-id="4c291-177">Download the onboarding package</span></span>

<span data-ttu-id="4c291-178">Laden Sie das Onboardingpaket aus Microsoft 365 Defender Portal herunter:</span><span class="sxs-lookup"><span data-stu-id="4c291-178">Download the onboarding package from Microsoft 365 Defender portal:</span></span>

1. <span data-ttu-id="4c291-179">Wechseln Sie im Microsoft 365 Defender Portal zu **Einstellungen > Endpunkte > Geräteverwaltung > Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="4c291-179">In the Microsoft 365 Defender portal, go to **Settings > Endpoints > Device management > Onboarding**.</span></span>
2. <span data-ttu-id="4c291-180">Wählen Sie im ersten Dropdownmenü **Linux Server** als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="4c291-180">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="4c291-181">Wählen Sie im zweiten Dropdownmenü **"Lokales Skript"** als Bereitstellungsmethode aus.</span><span class="sxs-lookup"><span data-stu-id="4c291-181">In the second drop-down menu, select **Local Script** as the deployment method.</span></span>
3. <span data-ttu-id="4c291-182">Wählen Sie **"Onboardingpaket herunterladen"** aus.</span><span class="sxs-lookup"><span data-stu-id="4c291-182">Select **Download onboarding package**.</span></span> <span data-ttu-id="4c291-183">Speichern Sie die Datei als WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="4c291-183">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Screenshot des Microsoft 365 Defender Portals](images/atp-portal-onboarding-linux.png)

4. <span data-ttu-id="4c291-185">Überprüfen Sie an einer Eingabeaufforderung, ob Die Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4c291-185">From a command prompt, verify that you have the file.</span></span>
    <span data-ttu-id="4c291-186">Extrahieren Sie den Inhalt des Archivs:</span><span class="sxs-lookup"><span data-stu-id="4c291-186">Extract the contents of the archive:</span></span>

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


## <a name="client-configuration"></a><span data-ttu-id="4c291-187">Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="4c291-187">Client configuration</span></span>

1. <span data-ttu-id="4c291-188">Kopieren Sie MicrosoftDefenderATPOnboardingLinuxServer.py auf das Zielgerät.</span><span class="sxs-lookup"><span data-stu-id="4c291-188">Copy MicrosoftDefenderATPOnboardingLinuxServer.py to the target device.</span></span>

    <span data-ttu-id="4c291-189">Anfangs ist das Clientgerät keiner Organisation zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4c291-189">Initially the client device is not associated with an organization.</span></span> <span data-ttu-id="4c291-190">Beachten Sie, dass das *orgId-Attribut* leer ist:</span><span class="sxs-lookup"><span data-stu-id="4c291-190">Note that the *orgId* attribute is blank:</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="4c291-191">Führen Sie MicrosoftDefenderATPOnboardingLinuxServer.py aus.</span><span class="sxs-lookup"><span data-stu-id="4c291-191">Run MicrosoftDefenderATPOnboardingLinuxServer.py.</span></span> 
   
    >[!NOTE]
    ><span data-ttu-id="4c291-192">Zum Ausführen dieses Befehls müssen Sie `python` auf dem Gerät installiert sein.</span><span class="sxs-lookup"><span data-stu-id="4c291-192">To run this command, you must have `python` installed on the device.</span></span> <span data-ttu-id="4c291-193">Wenn Sie RHEL 8.x oder Ubuntu 20.04 oder höher ausführen, müssen Sie Python 3 anstelle von Python verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c291-193">If you're running RHEL 8.x or Ubuntu 20.04 or higher, then you will need to use Python 3 instead of Python.</span></span>



    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. <span data-ttu-id="4c291-194">Stellen Sie sicher, dass das Gerät jetzt Ihrer Organisation zugeordnet ist, und melden Sie einen gültigen Organisationsbezeichner:</span><span class="sxs-lookup"><span data-stu-id="4c291-194">Verify that the device is now associated with your organization and reports a valid organization identifier:</span></span>

    ```bash
    mdatp health --field org_id
    ```

4. <span data-ttu-id="4c291-195">Einige Minuten nach Abschluss der Installation können Sie den Status anzeigen, indem Sie den folgenden Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="4c291-195">A few minutes after you complete the installation, you can see the status by running the following command.</span></span> <span data-ttu-id="4c291-196">Ein Rückgabewert, der `1` angibt, dass das Produkt erwartungsgemäß funktioniert:</span><span class="sxs-lookup"><span data-stu-id="4c291-196">A return value of `1` denotes that the product is functioning as expected:</span></span>

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="4c291-197">Wenn das Produkt zum ersten Mal gestartet wird, werden die neuesten Antischadsoftwaredefinitionen heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="4c291-197">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="4c291-198">Je nach Internetverbindung kann dies bis zu ein paar Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="4c291-198">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="4c291-199">Während dieser Zeit gibt der obige Befehl den Wert `false` .</span><span class="sxs-lookup"><span data-stu-id="4c291-199">During this time the above command returns a value of `false`.</span></span> <span data-ttu-id="4c291-200">Mit dem folgenden Befehl können Sie den Status der Definitionsaktualisierung überprüfen:</span><span class="sxs-lookup"><span data-stu-id="4c291-200">You can check the status of the definition update using the following command:</span></span>
    > ```bash
    > mdatp health --field definitions_status
    > ```
    > <span data-ttu-id="4c291-201">Bitte beachten Sie, dass Sie nach Abschluss der Erstinstallation möglicherweise auch einen Proxy konfigurieren müssen.</span><span class="sxs-lookup"><span data-stu-id="4c291-201">Please note that you may also need to configure a proxy after completing the initial installation.</span></span> <span data-ttu-id="4c291-202">Siehe [Konfigurieren von Defender für Endpunkt unter Linux für statische Proxyermittlung: Konfiguration nach der Installation.](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration)</span><span class="sxs-lookup"><span data-stu-id="4c291-202">See [Configure Defender for Endpoint on Linux for static proxy discovery: Post-installation configuration](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration).</span></span>

5. <span data-ttu-id="4c291-203">Führen Sie einen Erkennungstest aus, um sicherzustellen, dass das Gerät ordnungsgemäß integriert ist, und melden Sie sich an den Dienst.</span><span class="sxs-lookup"><span data-stu-id="4c291-203">Run a detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="4c291-204">Führen Sie die folgenden Schritte auf dem neu eingebundenen Gerät durch:</span><span class="sxs-lookup"><span data-stu-id="4c291-204">Perform the following steps on the newly onboarded device:</span></span>

    - <span data-ttu-id="4c291-205">Stellen Sie sicher, dass der Echtzeitschutz aktiviert ist (angegeben durch ein Ergebnis der `1` Ausführung des folgenden Befehls):</span><span class="sxs-lookup"><span data-stu-id="4c291-205">Ensure that real-time protection is enabled (denoted by a result of `1` from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - <span data-ttu-id="4c291-206">Öffnen Sie ein Terminal-Fenster.</span><span class="sxs-lookup"><span data-stu-id="4c291-206">Open a Terminal window.</span></span> <span data-ttu-id="4c291-207">Kopieren Sie den folgenden Befehl und führen Sie ihn aus:</span><span class="sxs-lookup"><span data-stu-id="4c291-207">Copy and execute the following command:</span></span>

        ``` bash
        curl -o /tmp/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - <span data-ttu-id="4c291-208">Die Datei sollte von Defender für Endpunkt unter Linux in Quarantäne gestellt worden sein.</span><span class="sxs-lookup"><span data-stu-id="4c291-208">The file should have been quarantined by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="4c291-209">Verwenden Sie den folgenden Befehl, um alle entdeckten Bedrohungen aufzulisten:</span><span class="sxs-lookup"><span data-stu-id="4c291-209">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

## <a name="experience-linux-endpoint-detection-and-response-edr-capabilities-with-simulated-attacks"></a><span data-ttu-id="4c291-210">Erfahrung der Funktionen von Linux EDR (EDR) mit simulierten Angriffen</span><span class="sxs-lookup"><span data-stu-id="4c291-210">Experience Linux endpoint detection and response (EDR) capabilities with simulated attacks</span></span>

<span data-ttu-id="4c291-211">Um die Funktionen von EDR für Linux zu testen, führen Sie die folgenden Schritte aus, um eine Erkennung auf Ihrem Linux-Server zu simulieren und den Fall zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="4c291-211">To test out the functionalities of EDR for Linux, follow the steps below to simulate a detection on your Linux server and investigate the case.</span></span> 

1.  <span data-ttu-id="4c291-212">Stellen Sie sicher, dass der integrierte Linux-Server in Microsoft 365 Defender angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4c291-212">Verify that the onboarded Linux server appears in Microsoft 365 Defender.</span></span> <span data-ttu-id="4c291-213">Wenn es sich um das erste Onboarding des Computers handelt, kann es bis zu 20 Minuten dauern, bis er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4c291-213">If this is the first onboarding of the machine, it can take up to 20 minutes until it appears.</span></span> 

2.  <span data-ttu-id="4c291-214">Laden Sie die [Skriptdatei](https://aka.ms/LinuxDIY) herunter, extrahieren Sie sie auf einen integrierten Linux-Server, und führen Sie den folgenden Befehl aus: `./mde_linux_edr_diy.sh`</span><span class="sxs-lookup"><span data-stu-id="4c291-214">Download and extract the [script file](https://aka.ms/LinuxDIY) to an onboarded Linux server and run the following command: `./mde_linux_edr_diy.sh`</span></span>

3.  <span data-ttu-id="4c291-215">Nach ein paar Minuten sollte eine Erkennung in Microsoft 365 Defender ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="4c291-215">After a few minutes, a detection should be raised in Microsoft 365 Defender.</span></span>

4.  <span data-ttu-id="4c291-216">Sehen Sie sich die Warnungsdetails, die Computerzeitachse und die typischen Untersuchungsschritte an.</span><span class="sxs-lookup"><span data-stu-id="4c291-216">Look at the alert details, machine timeline, and perform your typical investigation steps.</span></span>




## <a name="installer-script"></a><span data-ttu-id="4c291-217">Installer-Skript</span><span class="sxs-lookup"><span data-stu-id="4c291-217">Installer script</span></span>

<span data-ttu-id="4c291-218">Alternativ können Sie ein automatisiertes [Installer-Bash-Skript](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) verwenden, das in unserem [öffentlichen GitHub-Repository](https://github.com/microsoft/mdatp-xplat/)bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4c291-218">Alternatively, you can use an automated [installer bash script](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) provided in our [public GitHub repository](https://github.com/microsoft/mdatp-xplat/).</span></span>
<span data-ttu-id="4c291-219">Das Skript identifiziert die Verteilung und Version und richtet das Gerät so ein, dass das neueste Paket abgerufen und installiert wird.</span><span class="sxs-lookup"><span data-stu-id="4c291-219">The script identifies the distribution and version, and sets up the device to pull the latest package and install it.</span></span>
<span data-ttu-id="4c291-220">Sie können das Onboarding auch mit einem bereitgestellten Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="4c291-220">You can also onboard with a provided script.</span></span>

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

<span data-ttu-id="4c291-221">Weitere Informationen finden Sie [hier.](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation)</span><span class="sxs-lookup"><span data-stu-id="4c291-221">Read more [here](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="4c291-222">Protokollieren von Installationsproblemen</span><span class="sxs-lookup"><span data-stu-id="4c291-222">Log installation issues</span></span>

<span data-ttu-id="4c291-223">Weitere Informationen zum Auffinden des automatisch generierten Protokolls, das beim Auftreten eines Fehlers vom Installationsprogramm erstellt wird, finden Sie unter ["Protokollinstallationsprobleme".](linux-resources.md#log-installation-issues)</span><span class="sxs-lookup"><span data-stu-id="4c291-223">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="4c291-224">Betriebssystemupgrades</span><span class="sxs-lookup"><span data-stu-id="4c291-224">Operating system upgrades</span></span>

<span data-ttu-id="4c291-225">Wenn Sie Ihr Betriebssystem auf eine neue Hauptversion aktualisieren, müssen Sie zuerst Defender für Endpunkt unter Linux deinstallieren, das Upgrade installieren und schließlich Defender für Endpunkt unter Linux auf Ihrem Gerät neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4c291-225">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a><span data-ttu-id="4c291-226">Migrieren von Insiders-Fast zum Produktionskanal</span><span class="sxs-lookup"><span data-stu-id="4c291-226">How to migrate from Insiders-Fast to Production channel</span></span>

1. <span data-ttu-id="4c291-227">Deinstallieren Sie die Version "Insiders-Fast Channel" von Defender für Endpunkt unter Linux.</span><span class="sxs-lookup"><span data-stu-id="4c291-227">Uninstall the “Insiders-Fast channel” version of Defender for Endpoint on Linux.</span></span>

    ``
    sudo yum remove mdatp
    ``

1. <span data-ttu-id="4c291-228">Deaktivieren des Repositorys für Defender für Endpunkt unter Linux Insiders-Fast  ``
    sudo yum repolist
    ``</span><span class="sxs-lookup"><span data-stu-id="4c291-228">Disable the Defender for Endpoint on Linux Insiders-Fast repo  ``
    sudo yum repolist
 ``</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c291-229">Die Ausgabe sollte "packages-microsoft-com-fast-prod" anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c291-229">The output should show “packages-microsoft-com-fast-prod”.</span></span>

    ``
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ``
1. <span data-ttu-id="4c291-230">Stellen Sie MDE für Linux unter Verwendung des "Produktionskanals" erneut bereit.</span><span class="sxs-lookup"><span data-stu-id="4c291-230">Redeploy MDE for Linux using the “Production channel”.</span></span>


## <a name="uninstallation"></a><span data-ttu-id="4c291-231">Deinstallation</span><span class="sxs-lookup"><span data-stu-id="4c291-231">Uninstallation</span></span>

<span data-ttu-id="4c291-232">Weitere Informationen zum Entfernen von Defender für Endpunkt auf Linux von Clientgeräten finden Sie unter ["Deinstallieren".](linux-resources.md#uninstall)</span><span class="sxs-lookup"><span data-stu-id="4c291-232">See [Uninstall](linux-resources.md#uninstall) for details on how to remove Defender for Endpoint on Linux from client devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c291-233">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c291-233">See also</span></span>
- [<span data-ttu-id="4c291-234">Untersuchen von Problemen mit der Agent-Integrität</span><span class="sxs-lookup"><span data-stu-id="4c291-234">Investigate agent health issues</span></span>](health-status.md)
