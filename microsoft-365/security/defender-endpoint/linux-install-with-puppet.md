---
title: Bereitstellen von Microsoft Defender ATP für Linux mit Puppet
ms.reviewer: ''
description: Beschreibt, wie Sie Microsoft Defender ATP für Linux mithilfe von Puppet bereitstellen.
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
ms.openlocfilehash: 06611c19994ba34c4b59eb1a32b9ab9fd91cc1aa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066911"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-linux-with-puppet"></a><span data-ttu-id="cf86c-104">Bereitstellen von Microsoft Defender for Endpoint für Linux mit "Puppet"</span><span class="sxs-lookup"><span data-stu-id="cf86c-104">Deploy Microsoft Defender for Endpoint for Linux with Puppet</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cf86c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cf86c-105">**Applies to:**</span></span>
- [<span data-ttu-id="cf86c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cf86c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="cf86c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf86c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cf86c-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="cf86c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cf86c-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cf86c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="cf86c-110">In diesem Artikel wird beschrieben, wie Sie Defender for Endpoint für Linux mithilfe von Puppet bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cf86c-110">This article describes how to deploy Defender for Endpoint for Linux using Puppet.</span></span> <span data-ttu-id="cf86c-111">Eine erfolgreiche Bereitstellung erfordert den Abschluss aller folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="cf86c-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="cf86c-112">Herunterladen des Onboardingpakets</span><span class="sxs-lookup"><span data-stu-id="cf86c-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="cf86c-113">Erstellen eines "Puppet"-Manifests</span><span class="sxs-lookup"><span data-stu-id="cf86c-113">Create Puppet manifest</span></span>](#create-a-puppet-manifest)
- [<span data-ttu-id="cf86c-114">Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="cf86c-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="cf86c-115">Überprüfen des Onboardingstatus</span><span class="sxs-lookup"><span data-stu-id="cf86c-115">Check onboarding status</span></span>](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="cf86c-116">Voraussetzungen und Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="cf86c-116">Prerequisites and system requirements</span></span>

 <span data-ttu-id="cf86c-117">Eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion finden Sie auf der [Hauptseite von Defender for Endpoint für Linux](microsoft-defender-endpoint-linux.md).</span><span class="sxs-lookup"><span data-stu-id="cf86c-117">For a description of prerequisites and system requirements for the current software version, see [the main Defender for Endpoint for Linux page](microsoft-defender-endpoint-linux.md).</span></span>

<span data-ttu-id="cf86c-118">Darüber hinaus müssen Sie für die Bereitstellung von "Puppet" mit den Verwaltungsaufgaben von "Puppet" vertraut sein, "Puppet" konfiguriert haben und wissen, wie Sie Pakete bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cf86c-118">In addition, for Puppet deployment, you need to be familiar with Puppet administration tasks, have Puppet configured, and know how to deploy packages.</span></span> <span data-ttu-id="cf86c-119">"Puppet" bietet viele Möglichkeiten, dieselbe Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cf86c-119">Puppet has many ways to complete the same task.</span></span> <span data-ttu-id="cf86c-120">Diese Anweisungen setzen die Verfügbarkeit von unterstützten Puppet-Modulen voraus, z. B. *apt,* um das Paket bereitstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="cf86c-120">These instructions assume availability of supported Puppet modules, such as *apt* to help deploy the package.</span></span> <span data-ttu-id="cf86c-121">Ihre Organisation kann einen anderen Workflow verwenden.</span><span class="sxs-lookup"><span data-stu-id="cf86c-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="cf86c-122">Ausführliche Informationen finden Sie in [der Dokumentation zu Denkfiguren.](https://puppet.com/docs)</span><span class="sxs-lookup"><span data-stu-id="cf86c-122">Refer to the [Puppet documentation](https://puppet.com/docs) for details.</span></span>

## <a name="download-the-onboarding-package"></a><span data-ttu-id="cf86c-123">Herunterladen des Onboardingpakets</span><span class="sxs-lookup"><span data-stu-id="cf86c-123">Download the onboarding package</span></span>

<span data-ttu-id="cf86c-124">Laden Sie das Onboardingpaket aus dem Microsoft Defender Security Center herunter:</span><span class="sxs-lookup"><span data-stu-id="cf86c-124">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="cf86c-125">Wechseln Sie im Microsoft Defender Security Center zu **Einstellungen > Geräteverwaltung > Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="cf86c-125">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="cf86c-126">Wählen Sie im ersten Dropdownmenü **Linux Server** als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="cf86c-126">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="cf86c-127">Wählen Sie im zweiten Dropdownmenü **Ihr bevorzugtes Linux-Konfigurationsverwaltungstool** als Bereitstellungsmethode aus.</span><span class="sxs-lookup"><span data-stu-id="cf86c-127">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="cf86c-128">Wählen **Sie Onboardingpaket herunterladen aus.**</span><span class="sxs-lookup"><span data-stu-id="cf86c-128">Select **Download onboarding package**.</span></span> <span data-ttu-id="cf86c-129">Speichern Sie die Datei WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="cf86c-129">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Screenshot des Microsoft Defender Security Center](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="cf86c-131">Überprüfen Sie an einer Eingabeaufforderung, ob Sie über die Datei verfügen.</span><span class="sxs-lookup"><span data-stu-id="cf86c-131">From a command prompt, verify that you have the file.</span></span> 

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
5. <span data-ttu-id="cf86c-132">Extrahieren Sie den Inhalt des Archivs.</span><span class="sxs-lookup"><span data-stu-id="cf86c-132">Extract the contents of the archive.</span></span>
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a><span data-ttu-id="cf86c-133">Erstellen eines Puppet-Manifests</span><span class="sxs-lookup"><span data-stu-id="cf86c-133">Create a Puppet manifest</span></span>

<span data-ttu-id="cf86c-134">Sie müssen ein Puppet-Manifest für die Bereitstellung von Defender for Endpoint für Linux auf Geräten erstellen, die von einem Puppet-Server verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="cf86c-134">You need to create a Puppet manifest for deploying Defender for Endpoint for Linux to devices managed by a Puppet server.</span></span> <span data-ttu-id="cf86c-135">In diesem Beispiel werden die *apt-* und *yumrepo-Module* verwendet, die in den Puppetlabs verfügbar sind, und es wird davon ausgegangen, dass die Module auf Dem Puppet-Server installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="cf86c-135">This example makes use of the *apt* and *yumrepo* modules available from puppetlabs, and assumes that the modules have been installed on your Puppet server.</span></span>

<span data-ttu-id="cf86c-136">Erstellen Sie die *Ordner install_mdatp/Dateien* *und install_mdatp/Manifeste* unter dem Modulordner Ihrer Puppet-Installation.</span><span class="sxs-lookup"><span data-stu-id="cf86c-136">Create the folders *install_mdatp/files* and *install_mdatp/manifests* under the modules folder of your Puppet installation.</span></span> <span data-ttu-id="cf86c-137">Dieser Ordner befindet sich in der Regel in */etc/puppetlabs/code/environments/production/modules* auf Ihrem Puppet-Server.</span><span class="sxs-lookup"><span data-stu-id="cf86c-137">This folder is typically located in */etc/puppetlabs/code/environments/production/modules* on your Puppet server.</span></span> <span data-ttu-id="cf86c-138">Kopieren Sie mdatp_onboard.json-Datei, die oben erstellt wurde, in den *ordner install_mdatp/files.*</span><span class="sxs-lookup"><span data-stu-id="cf86c-138">Copy the mdatp_onboard.json file created above to the *install_mdatp/files* folder.</span></span> <span data-ttu-id="cf86c-139">Erstellen eines *init.pp*</span><span class="sxs-lookup"><span data-stu-id="cf86c-139">Create an *init.pp*</span></span> <span data-ttu-id="cf86c-140">datei, die die Bereitstellungsanweisungen enthält:</span><span class="sxs-lookup"><span data-stu-id="cf86c-140">file that contains the deployment instructions:</span></span>

```bash
pwd
```
```Output
/etc/puppetlabs/code/environments/production/modules
```

```bash
tree install_mdatp
```
```Output
install_mdatp
├── files
│   └── mdatp_onboard.json
└── manifests
    └── init.pp
```

### <a name="contents-of-install_mdatpmanifestsinitpp"></a><span data-ttu-id="cf86c-141">Inhalt von `install_mdatp/manifests/init.pp`</span><span class="sxs-lookup"><span data-stu-id="cf86c-141">Contents of `install_mdatp/manifests/init.pp`</span></span>

<span data-ttu-id="cf86c-142">Defender for Endpoint für Linux kann über einen der folgenden Kanäle bereitgestellt werden (unten als *[Channel]* bezeichnet): *insiders-fast*, *insiders-slow* oder *prod*. Jeder dieser Kanäle entspricht einem Linux-Softwarerepository.</span><span class="sxs-lookup"><span data-stu-id="cf86c-142">Defender for Endpoint for Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

<span data-ttu-id="cf86c-143">Die Auswahl des Kanals bestimmt den Typ und die Häufigkeit der Updates, die auf Ihrem Gerät angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="cf86c-143">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="cf86c-144">Geräte in *insiders-fast* sind die ersten, die Updates und neue Features erhalten, gefolgt von *insiders-slow* und schließlich von *prod*.</span><span class="sxs-lookup"><span data-stu-id="cf86c-144">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="cf86c-145">Um eine Vorschau neuer Features anzuzeigen und frühzeitig Feedback zu geben, empfiehlt es sich, einige Geräte in Ihrem Unternehmen so zu konfigurieren, dass sie entweder *insider-schnell* oder *insider-slow verwenden.*</span><span class="sxs-lookup"><span data-stu-id="cf86c-145">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="cf86c-146">Wenn Sie den Kanal nach der Erstinstallation wechseln, muss das Produkt neu installiert werden.</span><span class="sxs-lookup"><span data-stu-id="cf86c-146">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="cf86c-147">Um den Produktkanal zu wechseln: Deinstallieren Sie das vorhandene Paket, konfigurieren Sie Ihr Gerät neu, um den neuen Kanal zu verwenden, und führen Sie die Schritte in diesem Dokument aus, um das Paket vom neuen Speicherort aus zu installieren.</span><span class="sxs-lookup"><span data-stu-id="cf86c-147">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

<span data-ttu-id="cf86c-148">Notieren Sie sich Ihre Verteilung und Version, und identifizieren Sie den nächstgelegenen Eintrag unter `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="cf86c-148">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

<span data-ttu-id="cf86c-149">Ersetzen Sie in den folgenden Befehlen *[distro]* und *[version]* durch die informationen, die Sie identifiziert haben:</span><span class="sxs-lookup"><span data-stu-id="cf86c-149">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

> [!NOTE]
> <span data-ttu-id="cf86c-150">Ersetzen Sie bei RedHat, Oracle EL und CentOS 8 *[distro]* durch "rhel".</span><span class="sxs-lookup"><span data-stu-id="cf86c-150">In case of RedHat, Oracle EL, and CentOS 8, replace *[distro]* with 'rhel'.</span></span>

```puppet
# Puppet manifest to install Microsoft Defender ATP.
# @param channel The release channel based on your environment, insider-fast or prod.
# @param distro The Linux distribution in lowercase. In case of RedHat, Oracle EL, and CentOS 8, the distro variable should be 'rhel'.
# @param version The Linux distribution release number, e.g. 7.4.

class install_mdatp (
$channel = 'insiders-fast',
$distro = undef,
$version = undef
){
    case $::osfamily {
        'Debian' : {
            apt::source { 'microsoftpackages' :
                location => "https://packages.microsoft.com/${distro}/${version}/prod",
                release  => $channel,
                repos    => 'main',
                key      => {
                    'id'     => 'BC528686B50D79E339D3721CEB3E94ADBE1229CF',
                    'server' => 'keyserver.ubuntu.com',
                },
            }
        }
        'RedHat' : {
            yumrepo { 'microsoftpackages' :
                baseurl  => "https://packages.microsoft.com/${distro}/${version}/${channel}",
                descr    => "packages-microsoft-com-prod-${channel}",
                enabled  => 1,
                gpgcheck => 1,
                gpgkey   => 'https://packages.microsoft.com/keys/microsoft.asc'
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }

    case $::osfamily {
        /(Debian|RedHat)/: {
            file { ['/etc/opt', '/etc/opt/microsoft', '/etc/opt/microsoft/mdatp']:
                ensure => directory,
                owner  => root,
                group  => root,
                mode   => '0755'
            }

            file { '/etc/opt/microsoft/mdatp/mdatp_onboard.json':
                source  => 'puppet:///modules/install_mdatp/mdatp_onboard.json',
                owner   => root,
                group   => root,
                mode    => '0600',
                require => File['/etc/opt/microsoft/mdatp']
            }

            package { 'mdatp':
                ensure  => 'installed',
                require => File['/etc/opt/microsoft/mdatp/mdatp_onboard.json']
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }
}
```

## <a name="deployment"></a><span data-ttu-id="cf86c-151">Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="cf86c-151">Deployment</span></span>

<span data-ttu-id="cf86c-152">Schließen Sie das oben beschriebene Manifest in Ihre website.pp ein.</span><span class="sxs-lookup"><span data-stu-id="cf86c-152">Include the above manifest in your site.pp</span></span> <span data-ttu-id="cf86c-153">Datei:</span><span class="sxs-lookup"><span data-stu-id="cf86c-153">file:</span></span>

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```
```Output
node "default" {
    include install_mdatp
}
```

<span data-ttu-id="cf86c-154">Registrierte Agentgeräte suchen regelmäßig den Puppet Server ab, und installieren neue Konfigurationsprofile und -richtlinien, sobald sie erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="cf86c-154">Enrolled agent devices periodically poll the Puppet Server and install new configuration profiles and policies as soon as they are detected.</span></span>

## <a name="monitor-puppet-deployment"></a><span data-ttu-id="cf86c-155">Überwachen der Bereitstellung von "Puppet"</span><span class="sxs-lookup"><span data-stu-id="cf86c-155">Monitor Puppet deployment</span></span>

<span data-ttu-id="cf86c-156">Auf dem Agentgerät können Sie auch den Onboardingstatus überprüfen, indem Sie:</span><span class="sxs-lookup"><span data-stu-id="cf86c-156">On the agent device, you can also check the onboarding status by running:</span></span>

```bash
mdatp health
```
```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- <span data-ttu-id="cf86c-157">**lizenziert**: Dadurch wird bestätigt, dass das Gerät an Ihre Organisation gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="cf86c-157">**licensed**: This confirms that the device is tied to your organization.</span></span>

- <span data-ttu-id="cf86c-158">**orgId**: Dies ist Ihr Defender for Endpoint-Organisationsbezeichner.</span><span class="sxs-lookup"><span data-stu-id="cf86c-158">**orgId**: This is your Defender for Endpoint organization identifier.</span></span>

## <a name="check-onboarding-status"></a><span data-ttu-id="cf86c-159">Überprüfen des Onboardingstatus</span><span class="sxs-lookup"><span data-stu-id="cf86c-159">Check onboarding status</span></span>

<span data-ttu-id="cf86c-160">Sie können überprüfen, ob Geräte ordnungsgemäß onboardiert wurden, indem Sie ein Skript erstellen.</span><span class="sxs-lookup"><span data-stu-id="cf86c-160">You can check that devices have been correctly onboarded by creating a script.</span></span> <span data-ttu-id="cf86c-161">Das folgende Skript überprüft beispielsweise registrierte Geräte auf den Onboardingstatus:</span><span class="sxs-lookup"><span data-stu-id="cf86c-161">For example, the following script checks enrolled devices for onboarding status:</span></span>

```bash
mdatp health --field healthy
```

<span data-ttu-id="cf86c-162">Der obige Befehl `1` druckt, wenn das Produkt wie erwartet onboarded ist und funktioniert.</span><span class="sxs-lookup"><span data-stu-id="cf86c-162">The above command prints `1` if the product is onboarded and functioning as expected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf86c-163">Wenn das Produkt zum ersten Mal gestartet wird, werden die neuesten Antischalwaredefinitionen heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="cf86c-163">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="cf86c-164">Je nach Internetverbindung kann dies bis zu ein paar Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="cf86c-164">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="cf86c-165">Während dieser Zeit gibt der obige Befehl den Wert `0` zurück.</span><span class="sxs-lookup"><span data-stu-id="cf86c-165">During this time the above command returns a value of `0`.</span></span>

<span data-ttu-id="cf86c-166">Wenn das Produkt nicht fehlerfrei ist, gibt der Exitcode (der durchcheckt werden `echo $?` kann) das Problem an:</span><span class="sxs-lookup"><span data-stu-id="cf86c-166">If the product is not healthy, the exit code (which can be checked through `echo $?`) indicates the problem:</span></span>

- <span data-ttu-id="cf86c-167">1, wenn das Gerät noch nicht onboarded ist.</span><span class="sxs-lookup"><span data-stu-id="cf86c-167">1 if the device isn't onboarded yet.</span></span>
- <span data-ttu-id="cf86c-168">3, wenn die Verbindung zum Daemon nicht hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="cf86c-168">3 if the connection to the daemon cannot be established.</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="cf86c-169">Probleme bei der Protokollinstallation</span><span class="sxs-lookup"><span data-stu-id="cf86c-169">Log installation issues</span></span>

 <span data-ttu-id="cf86c-170">Weitere Informationen zum Suchen des automatisch generierten Protokolls, das beim Auftreten eines Fehlers vom Installationsprogramm erstellt wird, finden Sie unter [Log installation issues](linux-resources.md#log-installation-issues).</span><span class="sxs-lookup"><span data-stu-id="cf86c-170">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Log installation issues](linux-resources.md#log-installation-issues).</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="cf86c-171">Betriebssystemupgrades</span><span class="sxs-lookup"><span data-stu-id="cf86c-171">Operating system upgrades</span></span>

<span data-ttu-id="cf86c-172">Wenn Sie Ihr Betriebssystem auf eine neue Hauptversion aktualisieren, müssen Sie zunächst Defender for Endpoint für Linux deinstallieren, das Upgrade installieren und schließlich Defender for Endpoint für Linux auf Ihrem Gerät neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cf86c-172">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint for Linux, install the upgrade, and finally reconfigure Defender for Endpoint for Linux on your device.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="cf86c-173">Deinstallation</span><span class="sxs-lookup"><span data-stu-id="cf86c-173">Uninstallation</span></span>

<span data-ttu-id="cf86c-174">Erstellen eines *Moduls remove_mdatp* ähnlich *install_mdatp* Inhalten in *init.pp*</span><span class="sxs-lookup"><span data-stu-id="cf86c-174">Create a module *remove_mdatp* similar to *install_mdatp* with the following contents in *init.pp*</span></span> <span data-ttu-id="cf86c-175">Datei:</span><span class="sxs-lookup"><span data-stu-id="cf86c-175">file:</span></span>

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
