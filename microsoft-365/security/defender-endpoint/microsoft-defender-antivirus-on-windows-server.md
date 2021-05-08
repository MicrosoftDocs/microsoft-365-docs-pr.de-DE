---
title: Microsoft Defender Antivirus auf Windows Server
description: Erfahren Sie, wie Sie Microsoft Defender Antivirus unter Windows Server 2016 und Windows Server 2019 aktivieren und konfigurieren.
keywords: Windows Defender, Server, Scep, System Center Endpoint Protection, Server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/23/2021
ms.openlocfilehash: 175b06738b8c1508dab68c1e19648aa5385a7137
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269492"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="c5619-104">Microsoft Defender Antivirus auf Windows Server</span><span class="sxs-lookup"><span data-stu-id="c5619-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c5619-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c5619-105">**Applies to:**</span></span>

- [<span data-ttu-id="c5619-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c5619-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c5619-107">Microsoft Defender Antivirus ist in den folgenden Editionen/Versionen von Windows Server verfügbar:</span><span class="sxs-lookup"><span data-stu-id="c5619-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="c5619-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c5619-108">Windows Server 2019</span></span>
- <span data-ttu-id="c5619-109">Windows Server, Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="c5619-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="c5619-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="c5619-110">Windows Server 2016.</span></span> 

<span data-ttu-id="c5619-111">In einigen Fällen wird Microsoft Defender Antivirus als Endpoint *Protection bezeichnet.* Das Schutzmodul ist jedoch identisch.</span><span class="sxs-lookup"><span data-stu-id="c5619-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="c5619-112">Obwohl Funktionalität, Konfiguration und Verwaltung für Microsoft Defender Antivirus unter [Windows 10](microsoft-defender-antivirus-in-windows-10.md)weitgehend identisch sind, gibt es einige wichtige Unterschiede in Windows Server:</span><span class="sxs-lookup"><span data-stu-id="c5619-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="c5619-113">Unter Windows Server [werden automatische Ausschlüsse](configure-server-exclusions-microsoft-defender-antivirus.md) basierend auf Ihrer definierten Serverrolle angewendet.</span><span class="sxs-lookup"><span data-stu-id="c5619-113">On Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
 
- <span data-ttu-id="c5619-114">Wenn Sie unter Windows Server eine Nicht-Microsoft-Antiviren-/Antischalwarelösung ausführen, wechselt Microsoft Defender Antivirus nicht automatisch in den passiven oder deaktivierten Modus.</span><span class="sxs-lookup"><span data-stu-id="c5619-114">On Windows Server, if you are running a non-Microsoft antivirus/antimalware solution, Microsoft Defender Antivirus does not go into either passive mode or disabled mode automatically.</span></span> <span data-ttu-id="c5619-115">Sie können Microsoft Defender Antivirus jedoch manuell auf den passiven oder deaktivierten Modus festlegen.</span><span class="sxs-lookup"><span data-stu-id="c5619-115">However, you can set Microsoft Defender Antivirus to passive or disabled mode manually.</span></span>

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="c5619-116">Einrichten von Microsoft Defender Antivirus auf Windows Server</span><span class="sxs-lookup"><span data-stu-id="c5619-116">Setting up Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="c5619-117">Das Einrichten und Ausführen von Microsoft Defender Antivirus auf einer Serverplattform umfasst mehrere Schritte:</span><span class="sxs-lookup"><span data-stu-id="c5619-117">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="c5619-118">[Aktivieren Sie die Schnittstelle](#enable-the-user-interface-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="c5619-118">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="c5619-119">[Installieren Sie Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="c5619-119">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="c5619-120">[Überprüfen Sie, ob Microsoft Defender Antivirus ausgeführt wird.](#verify-microsoft-defender-antivirus-is-running)</span><span class="sxs-lookup"><span data-stu-id="c5619-120">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="c5619-121">[Aktualisieren Sie Ihre Antischalware Security Intelligence](#update-antimalware-security-intelligence).</span><span class="sxs-lookup"><span data-stu-id="c5619-121">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="c5619-122">(Nach Bedarf) [Senden Von Beispielen](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="c5619-122">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="c5619-123">(Nach Bedarf) [Konfigurieren von automatischen Ausschlüssen](#configure-automatic-exclusions).</span><span class="sxs-lookup"><span data-stu-id="c5619-123">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="c5619-124">(Nur bei Bedarf) [Legen Sie Microsoft Defender Antivirus auf den passiven Modus .](#need-to-set-microsoft-defender-antivirus-to-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="c5619-124">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="c5619-125">Aktivieren der Benutzeroberfläche unter Windows Server</span><span class="sxs-lookup"><span data-stu-id="c5619-125">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="c5619-126">Standardmäßig ist Microsoft Defender Antivirus unter Windows Server installiert und funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="c5619-126">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="c5619-127">Manchmal ist die Benutzeroberfläche (GUI) standardmäßig installiert, die GUI ist jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c5619-127">Sometimes, the user interface (GUI) is installed by default, but the GUI is not required.</span></span> <span data-ttu-id="c5619-128">Sie können PowerShell, Gruppenrichtlinien oder andere Methoden zum Verwalten von Microsoft Defender Antivirus verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5619-128">You can use PowerShell, Group Policy, or other methods to manage Microsoft Defender Antivirus.</span></span> 

<span data-ttu-id="c5619-129">Wenn die GUI nicht auf Ihrem Server installiert ist und Sie sie installieren möchten, verwenden Sie entweder den Assistenten Zum Hinzufügen von Rollen und **Features** oder PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c5619-129">If the GUI is not installed on your server, and you want to install it, either the **Add Roles and Features** wizard or PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="c5619-130">Aktivieren der GUI mithilfe des Assistenten zum Hinzufügen von Rollen und Features</span><span class="sxs-lookup"><span data-stu-id="c5619-130">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="c5619-131">Weitere Informationen finden Sie unter Installieren von [Rollen, Rollendiensten](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)und Features mithilfe des Assistenten zum Hinzufügen von Rollen und Features und verwenden Sie den Assistenten zum Hinzufügen von **Rollen und Features.**</span><span class="sxs-lookup"><span data-stu-id="c5619-131">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="c5619-132">Wenn Sie zum Schritt **Features** des Assistenten kommen, wählen Sie **unter Windows Defender Features** die Option GUI für **Windows Defender** aus.</span><span class="sxs-lookup"><span data-stu-id="c5619-132">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="c5619-133">In Windows Server 2016 sieht der Assistent zum Hinzufügen von **Rollen und Features** wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="c5619-133">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![Hinzufügen von Rollen und Feature-Assistenten, der die GUI für Windows Defender zeigt](images/server-add-gui.png)

   <span data-ttu-id="c5619-135">In Windows Server 2019 ist der Assistent zum Hinzufügen von **Rollen und Features** ähnlich.</span><span class="sxs-lookup"><span data-stu-id="c5619-135">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="c5619-136">Aktivieren der GUI mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5619-136">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="c5619-137">Das folgende PowerShell-Cmdlet aktiviert die Schnittstelle:</span><span class="sxs-lookup"><span data-stu-id="c5619-137">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="c5619-138">Installieren von Microsoft Defender Antivirus auf Windows Server</span><span class="sxs-lookup"><span data-stu-id="c5619-138">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="c5619-139">Wenn Sie Microsoft Defender Antivirus auf Windows Server installieren oder neu installieren müssen, können Sie dies entweder mit dem Assistenten zum Hinzufügen von Rollen und **Features** oder powerShell tun.</span><span class="sxs-lookup"><span data-stu-id="c5619-139">If you need to install or reinstall Microsoft Defender Antivirus on Windows Server, you can do that using either the **Add Roles and Features Wizard** or PowerShell.</span></span>

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="c5619-140">Verwenden des Assistenten zum Hinzufügen von Rollen und Features zum Installieren von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="c5619-140">Use the Add Roles and Features Wizard to install Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="c5619-141">Lesen Sie [diesen Artikel,](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)und verwenden Sie den Assistenten zum Hinzufügen **von Rollen und Features.**</span><span class="sxs-lookup"><span data-stu-id="c5619-141">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="c5619-142">Wenn Sie zum Schritt **Features** des Assistenten kommen, wählen Sie die Option Microsoft Defender Antivirus aus.</span><span class="sxs-lookup"><span data-stu-id="c5619-142">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="c5619-143">Wählen Sie auch die **GUI für Windows Defender** aus.</span><span class="sxs-lookup"><span data-stu-id="c5619-143">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="c5619-144">Installieren von Microsoft Defender Antivirus mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5619-144">Use PowerShell to install Microsoft Defender Antivirus</span></span>

<span data-ttu-id="c5619-145">Führen Sie das folgende Cmdlet aus, um Microsoft Defender Antivirus mithilfe von PowerShell zu installieren:</span><span class="sxs-lookup"><span data-stu-id="c5619-145">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="c5619-146">Ereignismeldungen für das in Microsoft Defender Antivirus enthaltene Antischalsoftwaremodul finden Sie unter [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="c5619-146">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="c5619-147">Überprüfen, ob Microsoft Defender Antivirus ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="c5619-147">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="c5619-148">Sobald Microsoft Defender Antivirus installiert ist, müssen Sie im nächsten Schritt überprüfen, ob es ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c5619-148">Once Microsoft Defender Antivirus is installed, your next step is to verify that it's running.</span></span> <span data-ttu-id="c5619-149">Führen Sie auf Dem Windows Server-Endpunkt das folgende PowerShell-Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="c5619-149">On your Windows Server endpoint, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="c5619-150">Führen Sie das folgende PowerShell-Cmdlet aus, um zu überprüfen, ob der Firewallschutz aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="c5619-150">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="c5619-151">Als Alternative zu PowerShell können Sie mithilfe der Eingabeaufforderung überprüfen, ob Microsoft Defender Antivirus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c5619-151">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="c5619-152">Führen Sie dazu den folgenden Befehl an einer Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="c5619-152">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="c5619-153">Der `sc query` Befehl gibt Informationen zum Microsoft Defender Antivirus-Dienst zurück.</span><span class="sxs-lookup"><span data-stu-id="c5619-153">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="c5619-154">Wenn Microsoft Defender Antivirus ausgeführt wird, wird `STATE` der Wert `RUNNING` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c5619-154">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="c5619-155">Aktualisieren von Antischalware Security Intelligence</span><span class="sxs-lookup"><span data-stu-id="c5619-155">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="c5619-156">Um aktualisierte Antischalware-Sicherheitsintelligenz zu erhalten, muss der Windows Update-Dienst ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c5619-156">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="c5619-157">Wenn Sie einen Updateverwaltungsdienst wie Windows Server Update Services (WSUS) verwenden, stellen Sie sicher, dass Updates für Microsoft Defender Antivirus Security Intelligence für die von Ihnen verwalteten Computer genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="c5619-157">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="c5619-158">Standardmäßig werden Updates von Windows Update nicht automatisch unter Windows Server 2019 oder Windows Server 2016 heruntergeladen und installiert.</span><span class="sxs-lookup"><span data-stu-id="c5619-158">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="c5619-159">Sie können diese Konfiguration mithilfe einer der folgenden Methoden ändern:</span><span class="sxs-lookup"><span data-stu-id="c5619-159">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="c5619-160">Methode</span><span class="sxs-lookup"><span data-stu-id="c5619-160">Method</span></span>  |<span data-ttu-id="c5619-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5619-161">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="c5619-162">**Windows Update** in der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="c5619-162">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="c5619-163">- **Die automatische Installation von** Updates führt dazu, dass alle Updates automatisch installiert werden, einschließlich Windows Defender Security Intelligence-Updates.</span><span class="sxs-lookup"><span data-stu-id="c5619-163">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="c5619-164">- **Laden Sie Updates** herunter, aber lassen Sie mich auswählen, ob sie installiert werden sollen Windows Defender sicherheitsintelligente Updates automatisch herunterladen und installieren können, andere Updates werden jedoch nicht automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="c5619-164">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="c5619-165">**Gruppenrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="c5619-165">**Group Policy**</span></span>     | <span data-ttu-id="c5619-166">Sie können Windows Update mithilfe der in der Gruppenrichtlinie verfügbaren Einstellungen im folgenden Pfad einrichten und **verwalten: Administrative Vorlagen\Windows-Komponenten\Windows Update\Automatische Updates konfigurieren**</span><span class="sxs-lookup"><span data-stu-id="c5619-166">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="c5619-167">Der **AUOptions-Registrierungsschlüssel**</span><span class="sxs-lookup"><span data-stu-id="c5619-167">The **AUOptions** registry key</span></span>     |<span data-ttu-id="c5619-168">Die folgenden beiden Werte ermöglichen Windows Update das automatische Herunterladen und Installieren von Security Intelligence-Updates:</span><span class="sxs-lookup"><span data-stu-id="c5619-168">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="c5619-169">- **4**  -  **Installieren Sie Updates automatisch**.</span><span class="sxs-lookup"><span data-stu-id="c5619-169">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="c5619-170">Dieser Wert führt dazu, dass alle Updates automatisch installiert werden, einschließlich Windows Defender Security Intelligence-Updates.</span><span class="sxs-lookup"><span data-stu-id="c5619-170">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="c5619-171">- **3**  -  **Laden Sie Updates herunter, aber lassen Sie mich auswählen, ob sie installiert werden sollen.**</span><span class="sxs-lookup"><span data-stu-id="c5619-171">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="c5619-172">Dieser Wert ermöglicht Windows Defender, Sicherheitsintelligenzupdates automatisch herunterzuladen und zu installieren, andere Updates werden jedoch nicht automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="c5619-172">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="c5619-173">Um sicherzustellen, dass der Schutz vor Schadsoftware erhalten bleibt, wird empfohlen, die folgenden Dienste zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="c5619-173">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="c5619-174">Windows-Fehlerberichtsdienst</span><span class="sxs-lookup"><span data-stu-id="c5619-174">Windows Error Reporting service</span></span>

- <span data-ttu-id="c5619-175">Windows Update-Dienst</span><span class="sxs-lookup"><span data-stu-id="c5619-175">Windows Update service</span></span>

<span data-ttu-id="c5619-176">In der folgenden Tabelle sind die Dienste für Microsoft Defender Antivirus und die abhängigen Dienste aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c5619-176">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="c5619-177">Dienstname</span><span class="sxs-lookup"><span data-stu-id="c5619-177">Service Name</span></span>|<span data-ttu-id="c5619-178">Dateispeicherort</span><span class="sxs-lookup"><span data-stu-id="c5619-178">File Location</span></span>|<span data-ttu-id="c5619-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5619-179">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="c5619-180">Windows Defender Service (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="c5619-180">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="c5619-181">Dies ist der wichtigste Microsoft Defender Antivirus-Dienst, der jederzeit ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="c5619-181">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="c5619-182">Windows Error Reporting Service (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="c5619-182">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="c5619-183">Dieser Dienst sendet Fehlerberichte zurück an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5619-183">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="c5619-184">Windows Defender Firewall (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="c5619-184">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="c5619-185">Es wird empfohlen, Windows Defender Firewalldienst aktiviert zu lassen.</span><span class="sxs-lookup"><span data-stu-id="c5619-185">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="c5619-186">Windows Update (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="c5619-186">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="c5619-187">Windows Update ist erforderlich, um Sicherheitsintelligenzupdates und Antischalwaremodulupdates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c5619-187">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="c5619-188">Übermitteln von Beispielen</span><span class="sxs-lookup"><span data-stu-id="c5619-188">Submit samples</span></span>

<span data-ttu-id="c5619-189">Die Beispielübermittlung ermöglicht Microsoft das Sammeln von Beispielen potenziell schädlicher Software.</span><span class="sxs-lookup"><span data-stu-id="c5619-189">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="c5619-190">Um weiterhin und auf dem neuesten Stand zu sein, verwenden Microsoft-Forscher diese Beispiele, um verdächtige Aktivitäten zu analysieren und aktualisierte Sicherheitsintelligenz für Antischalware zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c5619-190">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="c5619-191">Wir sammeln ausführbare Dateien des Programms, z. B. .exe dateien und .dll Dateien.</span><span class="sxs-lookup"><span data-stu-id="c5619-191">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="c5619-192">Wir sammeln keine Dateien, die personenbezogene Daten enthalten, z. B. Microsoft Word-Dokumente und PDF-Dateien.</span><span class="sxs-lookup"><span data-stu-id="c5619-192">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="c5619-193">Senden einer Datei</span><span class="sxs-lookup"><span data-stu-id="c5619-193">Submit a file</span></span>

1. <span data-ttu-id="c5619-194">Lesen Sie das [Übermittlungshandbuch](/windows/security/threat-protection/intelligence/submission-guide).</span><span class="sxs-lookup"><span data-stu-id="c5619-194">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="c5619-195">Besuchen Sie [das Beispielübermittlungsportal,](https://www.microsoft.com/wdsi/filesubmission)und übermitteln Sie Ihre Datei.</span><span class="sxs-lookup"><span data-stu-id="c5619-195">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="c5619-196">Aktivieren der automatischen Beispielübermittlung</span><span class="sxs-lookup"><span data-stu-id="c5619-196">Enable automatic sample submission</span></span>

<span data-ttu-id="c5619-197">Um die automatische Beispielübermittlung zu aktivieren, starten Sie eine Windows PowerShell-Konsole als Administrator, und legen Sie die **SubmitSamplesConsent-Wertdaten** gemäß einer der folgenden Einstellungen ein:</span><span class="sxs-lookup"><span data-stu-id="c5619-197">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="c5619-198">Einstellung</span><span class="sxs-lookup"><span data-stu-id="c5619-198">Setting</span></span>  |<span data-ttu-id="c5619-199">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5619-199">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="c5619-200">**0**  -  **Always-Eingabeaufforderung**</span><span class="sxs-lookup"><span data-stu-id="c5619-200">**0** - **Always prompt**</span></span>     |<span data-ttu-id="c5619-201">Der Microsoft Defender Antivirus-Dienst fordert Sie auf, die Übermittlung aller erforderlichen Dateien zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="c5619-201">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="c5619-202">Dies ist die Standardeinstellung für Microsoft Defender Antivirus, wird jedoch nicht für Installationen unter Windows Server 2016 oder 2019 ohne GUI empfohlen.</span><span class="sxs-lookup"><span data-stu-id="c5619-202">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="c5619-203">**1**   -  **Automatisches Senden sicherer Beispiele**</span><span class="sxs-lookup"><span data-stu-id="c5619-203">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="c5619-204">Der Microsoft Defender Antivirus-Dienst sendet alle Dateien, die als "sicher" gekennzeichnet sind, und fordert die restlichen Dateien auf.</span><span class="sxs-lookup"><span data-stu-id="c5619-204">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="c5619-205">**2**  -  **Nie senden**</span><span class="sxs-lookup"><span data-stu-id="c5619-205">**2** - **Never send**</span></span>      |<span data-ttu-id="c5619-206">Der Microsoft Defender Antivirus-Dienst fordert keine Eingabeaufforderungen auf und sendet keine Dateien.</span><span class="sxs-lookup"><span data-stu-id="c5619-206">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="c5619-207">**3**  -  **Alle Beispiele automatisch senden**</span><span class="sxs-lookup"><span data-stu-id="c5619-207">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="c5619-208">Der Microsoft Defender Antivirus-Dienst sendet alle Dateien ohne Bestätigungsaufforderung.</span><span class="sxs-lookup"><span data-stu-id="c5619-208">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="c5619-209">Konfigurieren automatischer Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="c5619-209">Configure automatic exclusions</span></span>

<span data-ttu-id="c5619-210">Um Sicherheit und Leistung sicherzustellen, werden bestimmte Ausschlüsse automatisch basierend auf den Rollen und Features hinzugefügt, die Sie bei Verwendung von Microsoft Defender Antivirus unter Windows Server 2016 oder 2019 installieren.</span><span class="sxs-lookup"><span data-stu-id="c5619-210">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="c5619-211">Weitere [Informationen finden Sie unter Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="c5619-211">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="c5619-212">Müssen Sie Microsoft Defender Antivirus auf den passiven Modus festlegen?</span><span class="sxs-lookup"><span data-stu-id="c5619-212">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="c5619-213">Wenn Sie ein Nicht-Microsoft-Antivirenprodukt als primäre Antivirenlösung unter Windows Server verwenden, müssen Sie Microsoft Defender Antivirus auf den passiven oder deaktivierten Modus festlegen.</span><span class="sxs-lookup"><span data-stu-id="c5619-213">If you are using a non-Microsoft antivirus product as your primary antivirus solution on Windows Server, you must set Microsoft Defender Antivirus to passive mode or disabled mode.</span></span>

- <span data-ttu-id="c5619-214">Unter Windows Server, Version 1803 oder neuer, oder Windows Server 2019, können Sie Microsoft Defender Antivirus auf den passiven Modus festlegen.</span><span class="sxs-lookup"><span data-stu-id="c5619-214">On Windows Server, version 1803 or newer, or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode.</span></span>  

- <span data-ttu-id="c5619-215">Unter Windows Server 2016 wird Microsoft Defender Antivirus nicht zusammen mit einem Nicht-Microsoft-Antiviren-/Antischalwareprodukt unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c5619-215">On Windows Server 2016, Microsoft Defender Antivirus is not supported alongside a non-Microsoft antivirus/antimalware product.</span></span> <span data-ttu-id="c5619-216">In diesen Fällen müssen Sie Microsoft Defender Antivirus auf den deaktivierten Modus festlegen.</span><span class="sxs-lookup"><span data-stu-id="c5619-216">In these cases, you must set Microsoft Defender Antivirus to disabled mode.</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a><span data-ttu-id="c5619-217">Festlegen des passiven Modus von Microsoft Defender Antivirus mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5619-217">Set Microsoft Defender Antivirus to passive mode using PowerShell</span></span>

<span data-ttu-id="c5619-218">Wenn Sie Windows Server, Version 1803 oder Windows Server 2019 verwenden, können Sie Microsoft Defender Antivirus mithilfe des folgenden PowerShell-Cmdlets auf den passiven Modus festlegen:</span><span class="sxs-lookup"><span data-stu-id="c5619-218">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by using the following PowerShell cmdlet:</span></span>

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a><span data-ttu-id="c5619-219">Festlegen des passiven Modus von Microsoft Defender Antivirus mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c5619-219">Set Microsoft Defender Antivirus to passive mode using Group Policy</span></span>

<span data-ttu-id="c5619-220">VERFAHREN ERFORDERLICH</span><span class="sxs-lookup"><span data-stu-id="c5619-220">PROCEDURE NEEDED</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="c5619-221">Festlegen des passiven Modus von Microsoft Defender Antivirus mithilfe eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="c5619-221">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="c5619-222">Wenn Sie Windows Server, Version 1803 oder Windows Server 2019 verwenden, können Sie Microsoft Defender Antivirus auf den passiven Modus festlegen, indem Sie den folgenden Registrierungsschlüssel festlegen:</span><span class="sxs-lookup"><span data-stu-id="c5619-222">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="c5619-223">Pfad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="c5619-223">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="c5619-224">Name: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="c5619-224">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="c5619-225">Typ: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="c5619-225">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="c5619-226">Wert: `1`</span><span class="sxs-lookup"><span data-stu-id="c5619-226">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="c5619-227">Deaktivieren von Microsoft Defender Antivirus mithilfe des Assistenten zum Entfernen von Rollen und Features</span><span class="sxs-lookup"><span data-stu-id="c5619-227">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="c5619-228">Weitere Informationen finden Sie unter Installieren oder Deinstallieren von [Rollen, Rollendiensten](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)oder Features, und verwenden Sie den Assistenten zum Entfernen **von Rollen und Features.**</span><span class="sxs-lookup"><span data-stu-id="c5619-228">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="c5619-229">Wenn Sie zum Schritt **Features** des Assistenten kommen, deaktivieren Sie **die Option Windows Defender Features.**</span><span class="sxs-lookup"><span data-stu-id="c5619-229">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="c5619-230">Wenn Sie **Windows Defender** im Abschnitt **Windows Defender Features** selbst löschen, werden Sie aufgefordert, die GUI für die Benutzeroberflächenoption für Windows Defender **.**</span><span class="sxs-lookup"><span data-stu-id="c5619-230">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="c5619-231">Microsoft Defender Antivirus wird weiterhin normal ohne die Benutzeroberfläche ausgeführt, aber die Benutzeroberfläche kann nicht aktiviert werden, wenn Sie das **Hauptfeature** Windows Defender deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c5619-231">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="c5619-232">Deaktivieren der Microsoft Defender Antivirus-Benutzeroberfläche mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5619-232">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="c5619-233">Verwenden Sie das folgende PowerShell-Cmdlet, um die Microsoft Defender Antivirus-GUI zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="c5619-233">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="c5619-234">Verwenden Sie Windows Server 2016?</span><span class="sxs-lookup"><span data-stu-id="c5619-234">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="c5619-235">Wenn Sie Windows Server 2016 und ein Antivirenprodukt eines Drittanbieters verwenden, das nicht von Microsoft angeboten oder entwickelt wird, müssen Sie Microsoft Defender Antivirus deaktivieren/deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="c5619-235">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="c5619-236">Sie können die Windows Security-App nicht deinstallieren, aber Sie können die Benutzeroberfläche mit diesen Anweisungen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c5619-236">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="c5619-237">Das folgende PowerShell-Cmdlet deinstalliert Microsoft Defender Antivirus unter Windows Server 2016:</span><span class="sxs-lookup"><span data-stu-id="c5619-237">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="c5619-238">Verwenden Sie das folgende PowerShell-Cmdlet, um Microsoft Defender Antivirus unter Windows Server 2016 zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="c5619-238">To disable Microsoft Defender Antivirus on Windows Server 2016, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a><span data-ttu-id="c5619-239">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5619-239">See also</span></span>

- [<span data-ttu-id="c5619-240">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="c5619-240">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="c5619-241">Microsoft Defender Antivirus-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="c5619-241">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
