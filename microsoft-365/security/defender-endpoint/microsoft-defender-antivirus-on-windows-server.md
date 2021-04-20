---
title: Microsoft Defender Antivirus auf Windows Server
description: Erfahren Sie, wie Sie Microsoft Defender Antivirus unter Windows Server 2016 und Windows Server 2019 aktivieren und konfigurieren.
keywords: Windows Defender, Server, Scep, System Center Endpoint Protection, Server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 50e6f9b16dbc633e75e86acdc54ac43580107ae3
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893377"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="0daf7-104">Microsoft Defender Antivirus auf Windows Server</span><span class="sxs-lookup"><span data-stu-id="0daf7-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0daf7-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0daf7-105">**Applies to:**</span></span>

- [<span data-ttu-id="0daf7-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0daf7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0daf7-107">Microsoft Defender Antivirus ist in den folgenden Editionen/Versionen von Windows Server verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0daf7-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="0daf7-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="0daf7-108">Windows Server 2019</span></span>
- <span data-ttu-id="0daf7-109">Windows Server, Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="0daf7-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="0daf7-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="0daf7-110">Windows Server 2016.</span></span> 

<span data-ttu-id="0daf7-111">In einigen Fällen wird Microsoft Defender Antivirus als Endpoint *Protection bezeichnet.* Das Schutzmodul ist jedoch identisch.</span><span class="sxs-lookup"><span data-stu-id="0daf7-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="0daf7-112">Obwohl Funktionalität, Konfiguration und Verwaltung für Microsoft Defender Antivirus unter [Windows 10](microsoft-defender-antivirus-in-windows-10.md)weitgehend identisch sind, gibt es einige wichtige Unterschiede in Windows Server:</span><span class="sxs-lookup"><span data-stu-id="0daf7-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="0daf7-113">In Windows Server werden [automatische Ausschlüsse](configure-server-exclusions-microsoft-defender-antivirus.md) basierend auf Ihrer definierten Serverrolle angewendet.</span><span class="sxs-lookup"><span data-stu-id="0daf7-113">In Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
- <span data-ttu-id="0daf7-114">In Windows Server deaktiviert sich Microsoft Defender Antivirus nicht automatisch, wenn Sie ein anderes Antivirenprodukt ausführen.</span><span class="sxs-lookup"><span data-stu-id="0daf7-114">In Windows Server, Microsoft Defender Antivirus does not automatically disable itself if you are running another antivirus product.</span></span>

## <a name="the-process-at-a-glance"></a><span data-ttu-id="0daf7-115">Der Prozess auf einen Blick</span><span class="sxs-lookup"><span data-stu-id="0daf7-115">The process at a glance</span></span>

<span data-ttu-id="0daf7-116">Das Einrichten und Ausführen von Microsoft Defender Antivirus auf einer Serverplattform umfasst mehrere Schritte:</span><span class="sxs-lookup"><span data-stu-id="0daf7-116">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="0daf7-117">[Aktivieren Sie die Schnittstelle](#enable-the-user-interface-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="0daf7-117">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="0daf7-118">[Installieren Sie Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="0daf7-118">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="0daf7-119">[Überprüfen Sie, ob Microsoft Defender Antivirus ausgeführt wird.](#verify-microsoft-defender-antivirus-is-running)</span><span class="sxs-lookup"><span data-stu-id="0daf7-119">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="0daf7-120">[Aktualisieren Sie Ihre Antischalware Security Intelligence](#update-antimalware-security-intelligence).</span><span class="sxs-lookup"><span data-stu-id="0daf7-120">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="0daf7-121">(Nach Bedarf) [Senden Von Beispielen](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="0daf7-121">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="0daf7-122">(Nach Bedarf) [Konfigurieren von automatischen Ausschlüssen](#configure-automatic-exclusions).</span><span class="sxs-lookup"><span data-stu-id="0daf7-122">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="0daf7-123">(Nur bei Bedarf) [Legen Sie Microsoft Defender Antivirus auf den passiven Modus .](#need-to-set-microsoft-defender-antivirus-to-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="0daf7-123">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="0daf7-124">Aktivieren der Benutzeroberfläche unter Windows Server</span><span class="sxs-lookup"><span data-stu-id="0daf7-124">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="0daf7-125">Standardmäßig ist Microsoft Defender Antivirus unter Windows Server installiert und funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="0daf7-125">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="0daf7-126">Die Benutzeroberfläche (GUI) ist standardmäßig auf einigen SKUs installiert, ist jedoch nicht erforderlich, da Sie PowerShell oder andere Methoden zum Verwalten von Microsoft Defender Antivirus verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0daf7-126">The user interface (GUI) is installed by default on some SKUs, but is not required because you can use PowerShell or other methods to manage Microsoft Defender Antivirus.</span></span> <span data-ttu-id="0daf7-127">Wenn die GUI nicht auf Ihrem Server installiert ist, können Sie sie mithilfe des Assistenten zum Hinzufügen von Rollen und **Features** oder mithilfe von PowerShell-Cmdlets hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0daf7-127">If the GUI is not installed on your server, you can add it by using the **Add Roles and Features** wizard, or by using PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="0daf7-128">Aktivieren der GUI mithilfe des Assistenten zum Hinzufügen von Rollen und Features</span><span class="sxs-lookup"><span data-stu-id="0daf7-128">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="0daf7-129">Weitere Informationen finden Sie unter Installieren von [Rollen, Rollendiensten](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)und Features mithilfe des Assistenten zum Hinzufügen von Rollen und Features und verwenden Sie den Assistenten zum Hinzufügen von **Rollen und Features.**</span><span class="sxs-lookup"><span data-stu-id="0daf7-129">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="0daf7-130">Wenn Sie zum Schritt **Features** des Assistenten kommen, wählen Sie **unter Windows Defender Features** die Option GUI für **Windows Defender** aus.</span><span class="sxs-lookup"><span data-stu-id="0daf7-130">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="0daf7-131">In Windows Server 2016 sieht der Assistent zum Hinzufügen von **Rollen und Features** wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="0daf7-131">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![Hinzufügen von Rollen und Feature-Assistenten, der die GUI für Windows Defender zeigt](images/server-add-gui.png)

   <span data-ttu-id="0daf7-133">In Windows Server 2019 ist der Assistent zum Hinzufügen von **Rollen und Features** ähnlich.</span><span class="sxs-lookup"><span data-stu-id="0daf7-133">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="0daf7-134">Aktivieren der GUI mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="0daf7-134">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="0daf7-135">Das folgende PowerShell-Cmdlet aktiviert die Schnittstelle:</span><span class="sxs-lookup"><span data-stu-id="0daf7-135">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="0daf7-136">Installieren von Microsoft Defender Antivirus auf Windows Server</span><span class="sxs-lookup"><span data-stu-id="0daf7-136">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="0daf7-137">Sie können entweder den Assistenten zum Hinzufügen von **Rollen und Features** oder PowerShell verwenden, um Microsoft Defender Antivirus zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0daf7-137">You can use either the **Add Roles and Features Wizard** or PowerShell to install Microsoft Defender Antivirus.</span></span>

### <a name="use-the-add-roles-and-features-wizard"></a><span data-ttu-id="0daf7-138">Verwenden des Assistenten zum Hinzufügen von Rollen und Features</span><span class="sxs-lookup"><span data-stu-id="0daf7-138">Use the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="0daf7-139">Lesen Sie [diesen Artikel,](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)und verwenden Sie den Assistenten zum Hinzufügen **von Rollen und Features.**</span><span class="sxs-lookup"><span data-stu-id="0daf7-139">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="0daf7-140">Wenn Sie zum Schritt **Features** des Assistenten kommen, wählen Sie die Option Microsoft Defender Antivirus aus.</span><span class="sxs-lookup"><span data-stu-id="0daf7-140">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="0daf7-141">Wählen Sie auch die **GUI für Windows Defender** aus.</span><span class="sxs-lookup"><span data-stu-id="0daf7-141">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="0daf7-142">PowerShell verwenden</span><span class="sxs-lookup"><span data-stu-id="0daf7-142">Use PowerShell</span></span>

<span data-ttu-id="0daf7-143">Führen Sie das folgende Cmdlet aus, um Microsoft Defender Antivirus mithilfe von PowerShell zu installieren:</span><span class="sxs-lookup"><span data-stu-id="0daf7-143">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="0daf7-144">Ereignismeldungen für das in Microsoft Defender Antivirus enthaltene Antischalsoftwaremodul finden Sie unter [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="0daf7-144">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="0daf7-145">Überprüfen, ob Microsoft Defender Antivirus ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0daf7-145">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="0daf7-146">Führen Sie das folgende PowerShell-Cmdlet aus, um zu überprüfen, ob Microsoft Defender Antivirus auf Ihrem Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="0daf7-146">To verify that Microsoft Defender Antivirus is running on your server, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="0daf7-147">Führen Sie das folgende PowerShell-Cmdlet aus, um zu überprüfen, ob der Firewallschutz aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="0daf7-147">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="0daf7-148">Als Alternative zu PowerShell können Sie mithilfe der Eingabeaufforderung überprüfen, ob Microsoft Defender Antivirus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0daf7-148">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="0daf7-149">Führen Sie dazu den folgenden Befehl an einer Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="0daf7-149">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="0daf7-150">Der `sc query` Befehl gibt Informationen zum Microsoft Defender Antivirus-Dienst zurück.</span><span class="sxs-lookup"><span data-stu-id="0daf7-150">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="0daf7-151">Wenn Microsoft Defender Antivirus ausgeführt wird, wird `STATE` der Wert `RUNNING` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0daf7-151">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="0daf7-152">Aktualisieren von Antischalware Security Intelligence</span><span class="sxs-lookup"><span data-stu-id="0daf7-152">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="0daf7-153">Um aktualisierte Antischalware-Sicherheitsintelligenz zu erhalten, muss der Windows Update-Dienst ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0daf7-153">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="0daf7-154">Wenn Sie einen Updateverwaltungsdienst wie Windows Server Update Services (WSUS) verwenden, stellen Sie sicher, dass Updates für Microsoft Defender Antivirus Security Intelligence für die von Ihnen verwalteten Computer genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="0daf7-154">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="0daf7-155">Standardmäßig werden Updates von Windows Update nicht automatisch unter Windows Server 2019 oder Windows Server 2016 heruntergeladen und installiert.</span><span class="sxs-lookup"><span data-stu-id="0daf7-155">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="0daf7-156">Sie können diese Konfiguration mithilfe einer der folgenden Methoden ändern:</span><span class="sxs-lookup"><span data-stu-id="0daf7-156">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="0daf7-157">Methode</span><span class="sxs-lookup"><span data-stu-id="0daf7-157">Method</span></span>  |<span data-ttu-id="0daf7-158">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0daf7-158">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="0daf7-159">**Windows Update** in der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="0daf7-159">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="0daf7-160">- **Die automatische Installation von** Updates führt dazu, dass alle Updates automatisch installiert werden, einschließlich Windows Defender Security Intelligence-Updates.</span><span class="sxs-lookup"><span data-stu-id="0daf7-160">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="0daf7-161">- **Laden Sie Updates** herunter, aber lassen Sie mich auswählen, ob sie installiert werden sollen Windows Defender sicherheitsintelligente Updates automatisch herunterladen und installieren können, andere Updates werden jedoch nicht automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="0daf7-161">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="0daf7-162">**Gruppenrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="0daf7-162">**Group Policy**</span></span>     | <span data-ttu-id="0daf7-163">Sie können Windows Update mithilfe der in der Gruppenrichtlinie verfügbaren Einstellungen im folgenden Pfad einrichten und **verwalten: Administrative Vorlagen\Windows-Komponenten\Windows Update\Automatische Updates konfigurieren**</span><span class="sxs-lookup"><span data-stu-id="0daf7-163">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="0daf7-164">Der **AUOptions-Registrierungsschlüssel**</span><span class="sxs-lookup"><span data-stu-id="0daf7-164">The **AUOptions** registry key</span></span>     |<span data-ttu-id="0daf7-165">Die folgenden beiden Werte ermöglichen Windows Update das automatische Herunterladen und Installieren von Security Intelligence-Updates:</span><span class="sxs-lookup"><span data-stu-id="0daf7-165">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="0daf7-166">- **4**  -  **Installieren Sie Updates automatisch**.</span><span class="sxs-lookup"><span data-stu-id="0daf7-166">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="0daf7-167">Dieser Wert führt dazu, dass alle Updates automatisch installiert werden, einschließlich Windows Defender Security Intelligence-Updates.</span><span class="sxs-lookup"><span data-stu-id="0daf7-167">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="0daf7-168">- **3**  -  **Laden Sie Updates herunter, aber lassen Sie mich auswählen, ob sie installiert werden sollen.**</span><span class="sxs-lookup"><span data-stu-id="0daf7-168">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="0daf7-169">Dieser Wert ermöglicht Windows Defender, Sicherheitsintelligenzupdates automatisch herunterzuladen und zu installieren, andere Updates werden jedoch nicht automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="0daf7-169">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="0daf7-170">Um sicherzustellen, dass der Schutz vor Schadsoftware erhalten bleibt, wird empfohlen, die folgenden Dienste zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="0daf7-170">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="0daf7-171">Windows-Fehlerberichtsdienst</span><span class="sxs-lookup"><span data-stu-id="0daf7-171">Windows Error Reporting service</span></span>

- <span data-ttu-id="0daf7-172">Windows Update-Dienst</span><span class="sxs-lookup"><span data-stu-id="0daf7-172">Windows Update service</span></span>

<span data-ttu-id="0daf7-173">In der folgenden Tabelle sind die Dienste für Microsoft Defender Antivirus und die abhängigen Dienste aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0daf7-173">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="0daf7-174">Dienstname</span><span class="sxs-lookup"><span data-stu-id="0daf7-174">Service Name</span></span>|<span data-ttu-id="0daf7-175">Dateispeicherort</span><span class="sxs-lookup"><span data-stu-id="0daf7-175">File Location</span></span>|<span data-ttu-id="0daf7-176">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0daf7-176">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="0daf7-177">Windows Defender Service (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="0daf7-177">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="0daf7-178">Dies ist der wichtigste Microsoft Defender Antivirus-Dienst, der jederzeit ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="0daf7-178">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="0daf7-179">Windows Error Reporting Service (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="0daf7-179">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="0daf7-180">Dieser Dienst sendet Fehlerberichte zurück an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0daf7-180">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="0daf7-181">Windows Defender Firewall (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="0daf7-181">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="0daf7-182">Es wird empfohlen, Windows Defender Firewalldienst aktiviert zu lassen.</span><span class="sxs-lookup"><span data-stu-id="0daf7-182">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="0daf7-183">Windows Update (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="0daf7-183">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="0daf7-184">Windows Update ist erforderlich, um Sicherheitsintelligenzupdates und Antischalwaremodulupdates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0daf7-184">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="0daf7-185">Übermitteln von Beispielen</span><span class="sxs-lookup"><span data-stu-id="0daf7-185">Submit samples</span></span>

<span data-ttu-id="0daf7-186">Die Beispielübermittlung ermöglicht Microsoft das Sammeln von Beispielen potenziell schädlicher Software.</span><span class="sxs-lookup"><span data-stu-id="0daf7-186">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="0daf7-187">Um weiterhin und auf dem neuesten Stand zu sein, verwenden Microsoft-Forscher diese Beispiele, um verdächtige Aktivitäten zu analysieren und aktualisierte Sicherheitsintelligenz für Antischalware zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0daf7-187">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="0daf7-188">Wir sammeln ausführbare Dateien des Programms, z. B. EXE-Dateien und DLL-Dateien.</span><span class="sxs-lookup"><span data-stu-id="0daf7-188">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="0daf7-189">Wir sammeln keine Dateien, die personenbezogene Daten enthalten, z. B. Microsoft Word-Dokumente und PDF-Dateien.</span><span class="sxs-lookup"><span data-stu-id="0daf7-189">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="0daf7-190">Senden einer Datei</span><span class="sxs-lookup"><span data-stu-id="0daf7-190">Submit a file</span></span>

1. <span data-ttu-id="0daf7-191">Lesen Sie das [Übermittlungshandbuch](/windows/security/threat-protection/intelligence/submission-guide).</span><span class="sxs-lookup"><span data-stu-id="0daf7-191">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="0daf7-192">Besuchen Sie [das Beispielübermittlungsportal,](https://www.microsoft.com/wdsi/filesubmission)und übermitteln Sie Ihre Datei.</span><span class="sxs-lookup"><span data-stu-id="0daf7-192">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="0daf7-193">Aktivieren der automatischen Beispielübermittlung</span><span class="sxs-lookup"><span data-stu-id="0daf7-193">Enable automatic sample submission</span></span>

<span data-ttu-id="0daf7-194">Um die automatische Beispielübermittlung zu aktivieren, starten Sie eine Windows PowerShell-Konsole als Administrator, und legen Sie die **SubmitSamplesConsent-Wertdaten** gemäß einer der folgenden Einstellungen ein:</span><span class="sxs-lookup"><span data-stu-id="0daf7-194">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="0daf7-195">Einstellung</span><span class="sxs-lookup"><span data-stu-id="0daf7-195">Setting</span></span>  |<span data-ttu-id="0daf7-196">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0daf7-196">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="0daf7-197">**0**  -  **Always-Eingabeaufforderung**</span><span class="sxs-lookup"><span data-stu-id="0daf7-197">**0** - **Always prompt**</span></span>     |<span data-ttu-id="0daf7-198">Der Microsoft Defender Antivirus-Dienst fordert Sie auf, die Übermittlung aller erforderlichen Dateien zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="0daf7-198">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="0daf7-199">Dies ist die Standardeinstellung für Microsoft Defender Antivirus, wird jedoch nicht für Installationen unter Windows Server 2016 oder 2019 ohne GUI empfohlen.</span><span class="sxs-lookup"><span data-stu-id="0daf7-199">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="0daf7-200">**1**   -  **Automatisches Senden sicherer Beispiele**</span><span class="sxs-lookup"><span data-stu-id="0daf7-200">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="0daf7-201">Der Microsoft Defender Antivirus-Dienst sendet alle Dateien, die als "sicher" gekennzeichnet sind, und fordert die restlichen Dateien auf.</span><span class="sxs-lookup"><span data-stu-id="0daf7-201">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="0daf7-202">**2**  -  **Nie senden**</span><span class="sxs-lookup"><span data-stu-id="0daf7-202">**2** - **Never send**</span></span>      |<span data-ttu-id="0daf7-203">Der Microsoft Defender Antivirus-Dienst fordert keine Eingabeaufforderungen auf und sendet keine Dateien.</span><span class="sxs-lookup"><span data-stu-id="0daf7-203">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="0daf7-204">**3**  -  **Alle Beispiele automatisch senden**</span><span class="sxs-lookup"><span data-stu-id="0daf7-204">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="0daf7-205">Der Microsoft Defender Antivirus-Dienst sendet alle Dateien ohne Bestätigungsaufforderung.</span><span class="sxs-lookup"><span data-stu-id="0daf7-205">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="0daf7-206">Konfigurieren automatischer Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="0daf7-206">Configure automatic exclusions</span></span>

<span data-ttu-id="0daf7-207">Um Sicherheit und Leistung sicherzustellen, werden bestimmte Ausschlüsse automatisch basierend auf den Rollen und Features hinzugefügt, die Sie bei Verwendung von Microsoft Defender Antivirus unter Windows Server 2016 oder 2019 installieren.</span><span class="sxs-lookup"><span data-stu-id="0daf7-207">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="0daf7-208">Weitere [Informationen finden Sie unter Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="0daf7-208">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="0daf7-209">Müssen Sie Microsoft Defender Antivirus auf den passiven Modus festlegen?</span><span class="sxs-lookup"><span data-stu-id="0daf7-209">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="0daf7-210">Wenn Sie ein Nicht-Microsoft-Antivirenprodukt als primäre Antivirenlösung verwenden, legen Sie Microsoft Defender Antivirus auf den passiven Modus.</span><span class="sxs-lookup"><span data-stu-id="0daf7-210">If you are using a non-Microsoft antivirus product as your primary antivirus solution, set Microsoft Defender Antivirus to passive mode.</span></span>  

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="0daf7-211">Festlegen des passiven Modus von Microsoft Defender Antivirus mithilfe eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="0daf7-211">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="0daf7-212">Wenn Sie Windows Server, Version 1803 oder Windows Server 2019 verwenden, können Sie Microsoft Defender Antivirus auf den passiven Modus festlegen, indem Sie den folgenden Registrierungsschlüssel festlegen:</span><span class="sxs-lookup"><span data-stu-id="0daf7-212">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="0daf7-213">Pfad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="0daf7-213">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="0daf7-214">Name: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="0daf7-214">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="0daf7-215">Typ: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="0daf7-215">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="0daf7-216">Wert: `1`</span><span class="sxs-lookup"><span data-stu-id="0daf7-216">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="0daf7-217">Deaktivieren von Microsoft Defender Antivirus mithilfe des Assistenten zum Entfernen von Rollen und Features</span><span class="sxs-lookup"><span data-stu-id="0daf7-217">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="0daf7-218">Weitere Informationen finden Sie unter Installieren oder Deinstallieren von [Rollen, Rollendiensten](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)oder Features, und verwenden Sie den Assistenten zum Entfernen **von Rollen und Features.**</span><span class="sxs-lookup"><span data-stu-id="0daf7-218">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="0daf7-219">Wenn Sie zum Schritt **Features** des Assistenten kommen, deaktivieren Sie **die Option Windows Defender Features.**</span><span class="sxs-lookup"><span data-stu-id="0daf7-219">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="0daf7-220">Wenn Sie **Windows Defender** im Abschnitt **Windows Defender Features** selbst löschen, werden Sie aufgefordert, die GUI für die Benutzeroberflächenoption für Windows Defender **.**</span><span class="sxs-lookup"><span data-stu-id="0daf7-220">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="0daf7-221">Microsoft Defender Antivirus wird weiterhin normal ohne die Benutzeroberfläche ausgeführt, aber die Benutzeroberfläche kann nicht aktiviert werden, wenn Sie das **Hauptfeature** Windows Defender deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0daf7-221">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="0daf7-222">Deaktivieren der Microsoft Defender Antivirus-Benutzeroberfläche mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="0daf7-222">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="0daf7-223">Verwenden Sie das folgende PowerShell-Cmdlet, um die Microsoft Defender Antivirus-GUI zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="0daf7-223">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="0daf7-224">Verwenden Sie Windows Server 2016?</span><span class="sxs-lookup"><span data-stu-id="0daf7-224">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="0daf7-225">Wenn Sie Windows Server 2016 und ein Antivirenprodukt eines Drittanbieters verwenden, das nicht von Microsoft angeboten oder entwickelt wird, müssen Sie Microsoft Defender Antivirus deaktivieren/deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="0daf7-225">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="0daf7-226">Sie können die Windows Security-App nicht deinstallieren, aber Sie können die Benutzeroberfläche mit diesen Anweisungen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0daf7-226">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="0daf7-227">Das folgende PowerShell-Cmdlet deinstalliert Microsoft Defender Antivirus unter Windows Server 2016:</span><span class="sxs-lookup"><span data-stu-id="0daf7-227">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

## <a name="see-also"></a><span data-ttu-id="0daf7-228">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0daf7-228">See also</span></span>

- [<span data-ttu-id="0daf7-229">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="0daf7-229">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="0daf7-230">Microsoft Defender Antivirus-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="0daf7-230">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
