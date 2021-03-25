---
title: Bereitstellen von Microsoft Defender ATP für Linux mit Ansible
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender ATP für Linux mithilfe von Ansible bereitgestellt wird.
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
ms.openlocfilehash: eca9727676fec9b716724719c182ca958b22ec85
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187805"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-linux-with-ansible"></a><span data-ttu-id="b8770-104">Bereitstellen von Microsoft Defender for Endpoint für Linux mit Ansible</span><span class="sxs-lookup"><span data-stu-id="b8770-104">Deploy Microsoft Defender for Endpoint for Linux with Ansible</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b8770-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b8770-105">**Applies to:**</span></span>
- [<span data-ttu-id="b8770-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b8770-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b8770-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8770-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b8770-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b8770-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b8770-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b8770-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="b8770-110">In diesem Artikel wird beschrieben, wie Sie Defender for Endpoint für Linux mithilfe von Ansible bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b8770-110">This article describes how to deploy Defender for Endpoint for Linux using Ansible.</span></span> <span data-ttu-id="b8770-111">Eine erfolgreiche Bereitstellung erfordert den Abschluss aller folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="b8770-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="b8770-112">Herunterladen des Onboardingpakets</span><span class="sxs-lookup"><span data-stu-id="b8770-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="b8770-113">Erstellen von ansiblen YAML-Dateien</span><span class="sxs-lookup"><span data-stu-id="b8770-113">Create Ansible YAML files</span></span>](#create-ansible-yaml-files)
- [<span data-ttu-id="b8770-114">Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="b8770-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="b8770-115">References</span><span class="sxs-lookup"><span data-stu-id="b8770-115">References</span></span>](#references)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="b8770-116">Voraussetzungen und Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="b8770-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="b8770-117">Bevor Sie beginnen, finden Sie auf der Hauptseite [von Defender for Endpoint für Linux](microsoft-defender-endpoint-linux.md) eine Beschreibung der Voraussetzungen und Systemanforderungen für die aktuelle Softwareversion.</span><span class="sxs-lookup"><span data-stu-id="b8770-117">Before you get started, see [the main Defender for Endpoint for Linux page](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

<span data-ttu-id="b8770-118">Darüber hinaus müssen Sie für die Ansible-Bereitstellung mit ansiblen Verwaltungsaufgaben vertraut sein, ansible konfigurieren und wissen, wie Sie Playbooks und Aufgaben bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b8770-118">In addition, for Ansible deployment, you need to be familiar with Ansible administration tasks, have Ansible configured, and know how to deploy playbooks and tasks.</span></span> <span data-ttu-id="b8770-119">Ansible hat viele Möglichkeiten, dieselbe Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b8770-119">Ansible has many ways to complete the same task.</span></span> <span data-ttu-id="b8770-120">Diese Anweisungen setzen voraus, dass unterstützte Ansible-Module verfügbar sind, z. B. *apt* und *unarchive,* um das Paket bereitstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="b8770-120">These instructions assume availability of supported Ansible modules, such as *apt* and *unarchive* to help deploy the package.</span></span> <span data-ttu-id="b8770-121">Ihre Organisation kann einen anderen Workflow verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8770-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="b8770-122">Ausführliche Informationen finden Sie in [der Ansible-Dokumentation.](https://docs.ansible.com/)</span><span class="sxs-lookup"><span data-stu-id="b8770-122">Refer to the [Ansible documentation](https://docs.ansible.com/) for details.</span></span>

- <span data-ttu-id="b8770-123">Ansible muss auf mindestens einem Computer installiert werden (wir nennen ihn den primären Computer).</span><span class="sxs-lookup"><span data-stu-id="b8770-123">Ansible needs to be installed on at least one computer (we will call it the primary computer).</span></span>
- <span data-ttu-id="b8770-124">SSH muss für ein Administratorkonto zwischen dem primären Computer und allen Clients konfiguriert sein, und es wird empfohlen, die Authentifizierung mit öffentlichen Schlüsseln zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8770-124">SSH must be configured for an administrator account between the primary computer and all clients, and it is recommended be configured with public key authentication.</span></span>
- <span data-ttu-id="b8770-125">Die folgende Software muss auf allen Clients installiert sein:</span><span class="sxs-lookup"><span data-stu-id="b8770-125">The following software must be installed on all clients:</span></span>
  - <span data-ttu-id="b8770-126">locken</span><span class="sxs-lookup"><span data-stu-id="b8770-126">curl</span></span>
  - <span data-ttu-id="b8770-127">python-apt</span><span class="sxs-lookup"><span data-stu-id="b8770-127">python-apt</span></span>

- <span data-ttu-id="b8770-128">Alle Hosts müssen in der oder den relevanten Dateien im folgenden `/etc/ansible/hosts` Format aufgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="b8770-128">All hosts must be listed in the following format in the `/etc/ansible/hosts` or relevant file:</span></span>

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- <span data-ttu-id="b8770-129">Pingtest:</span><span class="sxs-lookup"><span data-stu-id="b8770-129">Ping test:</span></span>

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="b8770-130">Herunterladen des Onboardingpakets</span><span class="sxs-lookup"><span data-stu-id="b8770-130">Download the onboarding package</span></span>

<span data-ttu-id="b8770-131">Laden Sie das Onboardingpaket aus dem Microsoft Defender Security Center herunter:</span><span class="sxs-lookup"><span data-stu-id="b8770-131">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="b8770-132">Wechseln Sie im Microsoft Defender Security Center zu **Einstellungen > Geräteverwaltung > Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="b8770-132">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="b8770-133">Wählen Sie im ersten Dropdownmenü **Linux Server** als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="b8770-133">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="b8770-134">Wählen Sie im zweiten Dropdownmenü **Ihr bevorzugtes Linux-Konfigurationsverwaltungstool** als Bereitstellungsmethode aus.</span><span class="sxs-lookup"><span data-stu-id="b8770-134">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="b8770-135">Wählen **Sie Onboardingpaket herunterladen aus.**</span><span class="sxs-lookup"><span data-stu-id="b8770-135">Select **Download onboarding package**.</span></span> <span data-ttu-id="b8770-136">Speichern Sie die Datei WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="b8770-136">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Screenshot des Microsoft Defender Security Center](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="b8770-138">Überprüfen Sie an einer Eingabeaufforderung, ob Sie über die Datei verfügen.</span><span class="sxs-lookup"><span data-stu-id="b8770-138">From a command prompt, verify that you have the file.</span></span> <span data-ttu-id="b8770-139">Extrahieren sie den Inhalt des Archivs:</span><span class="sxs-lookup"><span data-stu-id="b8770-139">Extract the contents of the archive:</span></span>

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a><span data-ttu-id="b8770-140">Erstellen von ansiblen YAML-Dateien</span><span class="sxs-lookup"><span data-stu-id="b8770-140">Create Ansible YAML files</span></span>

<span data-ttu-id="b8770-141">Erstellen Sie eine Unteraufgabe oder Rollendateien, die zu einem Playbook oder einer Aufgabe beitragen.</span><span class="sxs-lookup"><span data-stu-id="b8770-141">Create a subtask or role files that contribute to an playbook or task.</span></span>

- <span data-ttu-id="b8770-142">Erstellen Sie die `onboarding_setup.yml` Onboardingaufgabe:</span><span class="sxs-lookup"><span data-stu-id="b8770-142">Create the onboarding task, `onboarding_setup.yml`:</span></span>

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- <span data-ttu-id="b8770-143">Fügen Sie das Defender for Endpoint-Repository und den Schlüssel hinzu.</span><span class="sxs-lookup"><span data-stu-id="b8770-143">Add the Defender for Endpoint repository and key.</span></span>

    <span data-ttu-id="b8770-144">Defender for Endpoint für Linux kann über einen der folgenden Kanäle bereitgestellt werden (unten als *[Channel]* bezeichnet): *insiders-fast*, *insiders-slow* oder *prod*. Jeder dieser Kanäle entspricht einem Linux-Softwarerepository.</span><span class="sxs-lookup"><span data-stu-id="b8770-144">Defender for Endpoint for Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

    <span data-ttu-id="b8770-145">Die Auswahl des Kanals bestimmt den Typ und die Häufigkeit der Updates, die auf Ihrem Gerät angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="b8770-145">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="b8770-146">Geräte in *insiders-fast* sind die ersten, die Updates und neue Features erhalten, gefolgt von *insiders-slow* und schließlich von *prod*.</span><span class="sxs-lookup"><span data-stu-id="b8770-146">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

    <span data-ttu-id="b8770-147">Um eine Vorschau neuer Features anzuzeigen und frühzeitig Feedback zu geben, empfiehlt es sich, einige Geräte in Ihrem Unternehmen so zu konfigurieren, dass sie entweder *insider-schnell* oder *insider-slow verwenden.*</span><span class="sxs-lookup"><span data-stu-id="b8770-147">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

    > [!WARNING]
    > <span data-ttu-id="b8770-148">Wenn Sie den Kanal nach der Erstinstallation wechseln, muss das Produkt neu installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b8770-148">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="b8770-149">Um den Produktkanal zu wechseln: Deinstallieren Sie das vorhandene Paket, konfigurieren Sie Ihr Gerät neu, um den neuen Kanal zu verwenden, und führen Sie die Schritte in diesem Dokument aus, um das Paket vom neuen Speicherort aus zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b8770-149">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

    <span data-ttu-id="b8770-150">Notieren Sie sich Ihre Verteilung und Version, und identifizieren Sie den nächstgelegenen Eintrag unter `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="b8770-150">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="b8770-151">Ersetzen Sie in den folgenden Befehlen *[distro]* und *[version]* durch die von Ihnen identifizierten Informationen.</span><span class="sxs-lookup"><span data-stu-id="b8770-151">In the following commands, replace *[distro]* and *[version]* with the information you've identified.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8770-152">Ersetzen Sie bei Oracle Linux *[distro] durch* "rhel".</span><span class="sxs-lookup"><span data-stu-id="b8770-152">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      keyserver: https://packages.microsoft.com/
      id: BC528686B50D79E339D3721CEB3E94ADBE1229CF
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel].list
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-com-prod-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/
      gpgcheck: yes
      enabled: Yes
  when: ansible_os_family == "RedHat"
  ```

- <span data-ttu-id="b8770-153">Erstellen Sie die Ansible-Installation und deinstallieren Sie YAML-Dateien.</span><span class="sxs-lookup"><span data-stu-id="b8770-153">Create the Ansible install and uninstall YAML files.</span></span>

    - <span data-ttu-id="b8770-154">Verwenden Sie für apt-basierte Verteilungen die folgende YAML-Datei:</span><span class="sxs-lookup"><span data-stu-id="b8770-154">For apt-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
        tasks:
            - apt:
                name: mdatp
                state: absent
        ```

    - <span data-ttu-id="b8770-155">Verwenden Sie für yum-basierte Verteilungen die folgende YAML-Datei:</span><span class="sxs-lookup"><span data-stu-id="b8770-155">For yum-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp_yum.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - yum:
              name: mdatp
              state: latest
              enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_yum.yml
        ```
        ```Output
        - hosts: servers
        tasks:
            - yum:
               name: mdatp
                state: absent
        ```

## <a name="deployment"></a><span data-ttu-id="b8770-156">Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="b8770-156">Deployment</span></span>

<span data-ttu-id="b8770-157">Führen Sie nun die Aufgabendateien unter `/etc/ansible/playbooks/` oder relevantem Verzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="b8770-157">Now run the tasks files under `/etc/ansible/playbooks/` or relevant directory.</span></span>

- <span data-ttu-id="b8770-158">Installation:</span><span class="sxs-lookup"><span data-stu-id="b8770-158">Installation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> <span data-ttu-id="b8770-159">Wenn das Produkt zum ersten Mal gestartet wird, werden die neuesten Antischalwaredefinitionen heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="b8770-159">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="b8770-160">Je nach Internetverbindung kann dies bis zu ein paar Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="b8770-160">Depending on your Internet connection, this can take up to a few minutes.</span></span>

- <span data-ttu-id="b8770-161">Validierung/Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="b8770-161">Validation/configuration:</span></span>

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- <span data-ttu-id="b8770-162">Deinstallation:</span><span class="sxs-lookup"><span data-stu-id="b8770-162">Uninstallation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a><span data-ttu-id="b8770-163">Probleme bei der Protokollinstallation</span><span class="sxs-lookup"><span data-stu-id="b8770-163">Log installation issues</span></span>

<span data-ttu-id="b8770-164">Weitere [Informationen zum](linux-resources.md#log-installation-issues) Suchen des automatisch generierten Protokolls, das beim Auftreten eines Fehlers vom Installationsprogramm erstellt wird, finden Sie unter Protokollinstallationsprobleme.</span><span class="sxs-lookup"><span data-stu-id="b8770-164">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="b8770-165">Betriebssystemupgrades</span><span class="sxs-lookup"><span data-stu-id="b8770-165">Operating system upgrades</span></span>

<span data-ttu-id="b8770-166">Wenn Sie Ihr Betriebssystem auf eine neue Hauptversion aktualisieren, müssen Sie zunächst Defender for Endpoint für Linux deinstallieren, das Upgrade installieren und schließlich Defender for Endpoint für Linux auf Ihrem Gerät neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b8770-166">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint for Linux, install the upgrade, and finally reconfigure Defender for Endpoint for Linux on your device.</span></span>

## <a name="references"></a><span data-ttu-id="b8770-167">Informationsquellen</span><span class="sxs-lookup"><span data-stu-id="b8770-167">References</span></span>

- [<span data-ttu-id="b8770-168">Hinzufügen oder Entfernen von YUM-Repositorys</span><span class="sxs-lookup"><span data-stu-id="b8770-168">Add or remove YUM repositories</span></span>](https://docs.ansible.com/ansible/2.3/yum_repository_module.html)

- [<span data-ttu-id="b8770-169">Verwalten von Paketen mit dem yum-Paket-Manager</span><span class="sxs-lookup"><span data-stu-id="b8770-169">Manage packages with the yum package manager</span></span>](https://docs.ansible.com/ansible/latest/modules/yum_module.html)

- [<span data-ttu-id="b8770-170">Hinzufügen und Entfernen von APT-Repositorys</span><span class="sxs-lookup"><span data-stu-id="b8770-170">Add and remove APT repositories</span></span>](https://docs.ansible.com/ansible/latest/modules/apt_repository_module.html)

- [<span data-ttu-id="b8770-171">Verwalten von apt-packages</span><span class="sxs-lookup"><span data-stu-id="b8770-171">Manage apt-packages</span></span>](https://docs.ansible.com/ansible/latest/modules/apt_module.html)
