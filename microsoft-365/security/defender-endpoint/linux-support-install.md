---
title: Beheben von Installationsproblemen für Microsoft Defender ATP für Linux
ms.reviewer: ''
description: Beheben von Installationsproblemen für Microsoft Defender ATP für Linux
keywords: microsoft, defender, atp, linux, installation
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
ms.openlocfilehash: 4486b8e9d3fb84c272343ca344a47e49663bb80d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187745"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="bf623-104">Beheben von Installationsproblemen für Microsoft Defender for Endpoint für Linux</span><span class="sxs-lookup"><span data-stu-id="bf623-104">Troubleshoot installation issues for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bf623-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bf623-105">**Applies to:**</span></span>
- [<span data-ttu-id="bf623-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bf623-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bf623-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf623-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bf623-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="bf623-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bf623-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bf623-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a><span data-ttu-id="bf623-110">Überprüfen, ob die Installation erfolgreich war</span><span class="sxs-lookup"><span data-stu-id="bf623-110">Verify if installation succeeded</span></span>

<span data-ttu-id="bf623-111">Ein Fehler bei der Installation kann zu einer aussagekräftigen Fehlermeldung des Paket-Managers führen.</span><span class="sxs-lookup"><span data-stu-id="bf623-111">An error in installation may or may not result in a meaningful error message by the package manager.</span></span> <span data-ttu-id="bf623-112">Um zu überprüfen, ob die Installation erfolgreich war, rufen Sie die Installationsprotokolle ab, und überprüfen Sie sie mit:</span><span class="sxs-lookup"><span data-stu-id="bf623-112">To verify if the installation succeeded, obtain and check the installation logs using:</span></span>

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

<span data-ttu-id="bf623-113">Eine Ausgabe des vorherigen Befehls mit dem richtigen Datum und der richtigen Installationszeit zeigt den Erfolg an.</span><span class="sxs-lookup"><span data-stu-id="bf623-113">An output from the previous command with correct date and time of installation indicates success.</span></span>

<span data-ttu-id="bf623-114">Überprüfen Sie außerdem die [Clientkonfiguration,](linux-install-manually.md#client-configuration) um die Integrität des Produkts zu überprüfen und die EICAR-Textdatei zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="bf623-114">Also check the [Client configuration](linux-install-manually.md#client-configuration) to verify the health of the product and detect the EICAR text file.</span></span>

## <a name="make-sure-you-have-the-correct-package"></a><span data-ttu-id="bf623-115">Stellen Sie sicher, dass Sie über das richtige Paket verfügen</span><span class="sxs-lookup"><span data-stu-id="bf623-115">Make sure you have the correct package</span></span>

<span data-ttu-id="bf623-116">Beachten Sie, dass das paket, das Sie installieren, mit der Hostverteilung und -version übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="bf623-116">Please mind that the package you are installing is matching the host distribution and version.</span></span>

| <span data-ttu-id="bf623-117">package</span><span class="sxs-lookup"><span data-stu-id="bf623-117">package</span></span>                       | <span data-ttu-id="bf623-118">Verteilung</span><span class="sxs-lookup"><span data-stu-id="bf623-118">distribution</span></span>                             |
|-------------------------------|------------------------------------------|
| <span data-ttu-id="bf623-119">mdatp-rhel8. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="bf623-119">mdatp-rhel8.Linux.x86_64.rpm</span></span>  | <span data-ttu-id="bf623-120">Oracle, RHEL und CentOS 8.x</span><span class="sxs-lookup"><span data-stu-id="bf623-120">Oracle, RHEL and CentOS 8.x</span></span>              |
| <span data-ttu-id="bf623-121">mdatp-sles12. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="bf623-121">mdatp-sles12.Linux.x86_64.rpm</span></span> | <span data-ttu-id="bf623-122">SuSE Linux Enterprise Server 12.x</span><span class="sxs-lookup"><span data-stu-id="bf623-122">SuSE Linux Enterprise Server 12.x</span></span>        |
| <span data-ttu-id="bf623-123">mdatp-sles15. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="bf623-123">mdatp-sles15.Linux.x86_64.rpm</span></span> | <span data-ttu-id="bf623-124">SuSE Linux Enterprise Server 15.x</span><span class="sxs-lookup"><span data-stu-id="bf623-124">SuSE Linux Enterprise Server 15.x</span></span>        |
| <span data-ttu-id="bf623-125">mdatp. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="bf623-125">mdatp.Linux.x86_64.rpm</span></span>        | <span data-ttu-id="bf623-126">Oracle, RHEL und CentOS 7.x</span><span class="sxs-lookup"><span data-stu-id="bf623-126">Oracle, RHEL and CentOS 7.x</span></span>              |
| <span data-ttu-id="bf623-127">mdatp. Linux.x86_64.deb</span><span class="sxs-lookup"><span data-stu-id="bf623-127">mdatp.Linux.x86_64.deb</span></span>        | <span data-ttu-id="bf623-128">Debian und Ubuntu 16.04, 18.04 und 20.04</span><span class="sxs-lookup"><span data-stu-id="bf623-128">Debian and Ubuntu 16.04, 18.04 and 20.04</span></span> |

<span data-ttu-id="bf623-129">Stellen Sie bei der [manuellen](linux-install-manually.md)Bereitstellung sicher, dass die richtige Distro- und Version ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="bf623-129">For [manual deployment](linux-install-manually.md), make sure the correct distro and version had been chosen.</span></span>

## <a name="installation-failed"></a><span data-ttu-id="bf623-130">Installation fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="bf623-130">Installation failed</span></span>

<span data-ttu-id="bf623-131">Überprüfen Sie, ob der mdatp-Dienst ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="bf623-131">Check if the mdatp service is running:</span></span>

```bash
systemctl status mdatp
```
```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a><span data-ttu-id="bf623-132">Schritte zur Problembehandlung, wenn der mdatp-Dienst nicht ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="bf623-132">Steps to troubleshoot if mdatp service isn't running</span></span>

1. <span data-ttu-id="bf623-133">Überprüfen Sie, ob "mdatp"-Benutzer vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="bf623-133">Check if "mdatp" user exists:</span></span>

    ```bash
    id "mdatp"
    ```

    <span data-ttu-id="bf623-134">Wenn keine Ausgabe angezeigt wird, führen Sie</span><span class="sxs-lookup"><span data-stu-id="bf623-134">If there’s no output, run</span></span>

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. <span data-ttu-id="bf623-135">Versuchen Sie, den Dienst zu aktivieren und neu zu starten:</span><span class="sxs-lookup"><span data-stu-id="bf623-135">Try enabling and restarting the service using:</span></span>

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. <span data-ttu-id="bf623-136">Wenn mdatp.service beim Ausführen des vorherigen Befehls nicht gefunden wird, führen Sie aus:</span><span class="sxs-lookup"><span data-stu-id="bf623-136">If mdatp.service isn't found upon running the previous command, run:</span></span>

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    <span data-ttu-id="bf623-137">Dabei handelt es sich um Ubuntu- und ```<systemd_path>``` ```/lib/systemd/system``` Debian-Distributionen sowie für ```/usr/lib/systemd/system``` Rhel, CentOS, Oracle und SLES.</span><span class="sxs-lookup"><span data-stu-id="bf623-137">where ```<systemd_path>``` is ```/lib/systemd/system``` for Ubuntu and Debian distributions and ```/usr/lib/systemd/system``` for Rhel, CentOS, Oracle and SLES.</span></span>
   <span data-ttu-id="bf623-138">Führen Sie dann Schritt 2 erneut aus.</span><span class="sxs-lookup"><span data-stu-id="bf623-138">Then rerun step 2.</span></span>

4. <span data-ttu-id="bf623-139">Wenn die oben genannten Schritte nicht funktionieren, überprüfen Sie, ob SELinux installiert ist und ob der Erzwingungsmodus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bf623-139">If the above steps don’t work, check if SELinux is installed and in enforcing mode.</span></span> <span data-ttu-id="bf623-140">Wenn ja, versuchen Sie, ihn auf den zulässigen (vorzugsweise) oder deaktivierten Modus zu setzen.</span><span class="sxs-lookup"><span data-stu-id="bf623-140">If so, try setting it to permissive (preferably) or disabled mode.</span></span> <span data-ttu-id="bf623-141">Dies kann durch Festlegen des Parameters auf "zulässig" oder "deaktiviert" in der Datei, gefolgt von `SELINUX` `/etc/selinux/config` einem Neustart, geschehen.</span><span class="sxs-lookup"><span data-stu-id="bf623-141">It can be done by setting the parameter `SELINUX` to "permissive" or "disabled" in `/etc/selinux/config` file, followed by reboot.</span></span> <span data-ttu-id="bf623-142">Weitere Informationen finden Sie auf der Man-Seite von selinux.</span><span class="sxs-lookup"><span data-stu-id="bf623-142">Check the man-page of selinux for more details.</span></span>
<span data-ttu-id="bf623-143">Versuchen Sie nun, den mdatp-Dienst mithilfe von Schritt 2 neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="bf623-143">Now try restarting the mdatp service using step 2.</span></span> <span data-ttu-id="bf623-144">Stellen Sie die Konfigurationsänderung nach dem Versuch und dem Neustart aus Sicherheitsgründen sofort wieder ein.</span><span class="sxs-lookup"><span data-stu-id="bf623-144">Revert the configuration change immediately though for security reasons after trying it and reboot.</span></span>

5. <span data-ttu-id="bf623-145">Wenn `/opt` Directory ein symbolischer Link ist, erstellen Sie eine Bindungs mount für `/opt/microsoft` .</span><span class="sxs-lookup"><span data-stu-id="bf623-145">If `/opt` directory is a symbolic link, create a bind mount for `/opt/microsoft`.</span></span>

6. <span data-ttu-id="bf623-146">Stellen Sie sicher, dass der Daemon über ausführbare Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="bf623-146">Ensure that the daemon has executable permission.</span></span>

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="bf623-147">Wenn der Daemon nicht über ausführbare Berechtigungen verfügt, machen Sie ihn mithilfe von:</span><span class="sxs-lookup"><span data-stu-id="bf623-147">If the daemon doesn't have executable permissions, make it executable using:</span></span>

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="bf623-148">und wiederholen Sie die Ausführung von Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="bf623-148">and retry running step 2.</span></span>

7. <span data-ttu-id="bf623-149">Stellen Sie sicher, dass das Dateisystem, das wdavdaemon enthält, nicht mit "noexec" bereitgestellt ist.</span><span class="sxs-lookup"><span data-stu-id="bf623-149">Ensure that the file system containing wdavdaemon isn't mounted with "noexec".</span></span>

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a><span data-ttu-id="bf623-150">Wenn der mdatp-Dienst ausgeführt wird, die ERKENNUNG von EICAR-Textdateien jedoch nicht funktioniert</span><span class="sxs-lookup"><span data-stu-id="bf623-150">If mdatp service is running, but EICAR text file detection doesn't work</span></span>

1. <span data-ttu-id="bf623-151">Überprüfen Sie den Dateisystemtyp mithilfe von:</span><span class="sxs-lookup"><span data-stu-id="bf623-151">Check the file system type using:</span></span>

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    <span data-ttu-id="bf623-152">Derzeit unterstützte Dateisysteme für On-Access-Aktivitäten sind hier [aufgeführt.](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="bf623-152">Currently supported file systems for on-access activity are listed [here](microsoft-defender-endpoint-linux.md#system-requirements).</span></span> <span data-ttu-id="bf623-153">Alle Dateien außerhalb dieser Dateisysteme werden nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="bf623-153">Any files outside these file systems won't be scanned.</span></span>

## <a name="command-line-tool-mdatp-isnt-working"></a><span data-ttu-id="bf623-154">Befehlszeilentool "mdatp" funktioniert nicht</span><span class="sxs-lookup"><span data-stu-id="bf623-154">Command-line tool “mdatp” isn't working</span></span>

1. <span data-ttu-id="bf623-155">Wenn beim Ausführen des Befehlszeilentools `mdatp` ein Fehler `command not found` auftritt, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bf623-155">If running the command-line tool `mdatp` gives an error `command not found`, run the following command:</span></span>

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    <span data-ttu-id="bf623-156">und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="bf623-156">and try again.</span></span>

    <span data-ttu-id="bf623-157">Wenn keiner der obigen Schritte hilfreich ist, erfassen Sie die Diagnoseprotokolle:</span><span class="sxs-lookup"><span data-stu-id="bf623-157">If none of the above steps help, collect the diagnostic logs:</span></span>

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    <span data-ttu-id="bf623-158">Der Pfad zu einer ZIP-Datei, die die Protokolle enthält, wird als Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf623-158">Path to a zip file that contains the logs will be displayed as an output.</span></span> <span data-ttu-id="bf623-159">Mit diesen Protokollen erreichen Sie unseren Kundensupport.</span><span class="sxs-lookup"><span data-stu-id="bf623-159">Reach out to our customer support with these logs.</span></span>
