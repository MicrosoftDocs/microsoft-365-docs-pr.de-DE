---
title: Anpassen des kontrollierten Ordnerzugriffs
description: Fügen Sie andere Ordner hinzu, die durch kontrollierten Ordnerzugriff geschützt werden sollen, oder erlauben Sie Apps, die Änderungen an wichtigen Dateien fälschlicherweise blockieren.
keywords: Kontrollierter Ordnerzugriff, Windows 10, Windows Defender, Ransomware, Protect, Dateien, Ordner, anpassen, Ordner hinzufügen, App hinzufügen, zulassen, ausführbare Datei hinzufügen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 01/06/2021
ms.technology: mde
ms.openlocfilehash: 64f96544361a672881c590716adea80f40777c6e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163339"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="fc2d8-104">Anpassen des kontrollierten Ordnerzugriffs</span><span class="sxs-lookup"><span data-stu-id="fc2d8-104">Customize controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fc2d8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-105">**Applies to:**</span></span>
- [<span data-ttu-id="fc2d8-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="fc2d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fc2d8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc2d8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="fc2d8-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="fc2d8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fc2d8-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


<span data-ttu-id="fc2d8-110">Der kontrollierte Ordnerzugriff hilft Ihnen, wertvolle Daten vor schädlichen Apps und Bedrohungen wie Ransomware zu schützen.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="fc2d8-111">Der kontrollierte Ordnerzugriff wird auf Windows Server 2019- und Windows 10-Clients unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="fc2d8-112">In diesem Artikel wird beschrieben, wie Sie die Funktionen für den kontrollierten Ordnerzugriff anpassen und die folgenden Abschnitte umfassen:</span><span class="sxs-lookup"><span data-stu-id="fc2d8-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="fc2d8-113">Schützen zusätzlicher Ordner</span><span class="sxs-lookup"><span data-stu-id="fc2d8-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="fc2d8-114">Hinzufügen von Apps, die auf geschützte Ordner zugreifen dürfen sollten</span><span class="sxs-lookup"><span data-stu-id="fc2d8-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="fc2d8-115">Zugriff auf geschützte Ordner durch signierte ausführbare Dateien zulassen</span><span class="sxs-lookup"><span data-stu-id="fc2d8-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="fc2d8-116">Anpassen der Benachrichtigung</span><span class="sxs-lookup"><span data-stu-id="fc2d8-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="fc2d8-117">Der kontrollierte Ordnerzugriff überwacht Apps auf Aktivitäten, die als schädlich erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="fc2d8-118">Manchmal werden legitime Apps am Vornehmen von Änderungen an Ihren Dateien blockiert.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="fc2d8-119">Wenn sich der kontrollierte Ordnerzugriff auf die Produktivität [](audit-windows-defender.md) Ihrer Organisation auswirken sollte, können Sie die Ausführung dieses Features im Überwachungsmodus in Betracht ziehen, um die Auswirkungen vollständig zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="fc2d8-120">Schützen zusätzlicher Ordner</span><span class="sxs-lookup"><span data-stu-id="fc2d8-120">Protect additional folders</span></span>

<span data-ttu-id="fc2d8-121">Der kontrollierte Ordnerzugriff gilt für viele Systemordner und Standardspeicherorte, einschließlich Ordner wie **Dokumente,** **Bilder** und **Filme.**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="fc2d8-122">Sie können zusätzliche ordner hinzufügen, die geschützt werden sollen, aber Sie können die Standardordner in der Standardliste nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-122">You can add additional folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="fc2d8-123">Das Hinzufügen anderer Ordner zum kontrollierten Ordnerzugriff kann für Fälle hilfreich sein, in denen Sie keine Dateien in den standardmäßigen Windows-Bibliotheken speichern oder den Standardspeicherort Ihrer Bibliotheken geändert haben.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="fc2d8-124">Sie können auch Netzwerkfreigaben und zugeordnete Laufwerke angeben.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="fc2d8-125">Umgebungsvariablen und Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="fc2d8-126">Informationen zur Verwendung von Platzhaltern finden Sie unter Verwenden von Platzhaltern in den Listen für Dateinamen und Ordnerpfad oder [Erweiterungsausschluss](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span><span class="sxs-lookup"><span data-stu-id="fc2d8-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="fc2d8-127">Sie können die Windows-Sicherheits-App, Gruppenrichtlinien, PowerShell-Cmdlets oder Konfigurationsdienstanbieter für die Mobile Geräteverwaltung verwenden, um zusätzliche geschützte Ordner hinzuzufügen und zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove additional protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="fc2d8-128">Verwenden der Windows Security-App zum Schutz zusätzlicher Ordner</span><span class="sxs-lookup"><span data-stu-id="fc2d8-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="fc2d8-129">Öffnen Sie die Windows Security-App, indem Sie das Schildsymbol in der Taskleiste auswählen oder im Startmenü nach **Sicherheit suchen.**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-129">Open the Windows Security app by selecting the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="fc2d8-130">Wählen **Sie Virenschutz & bedrohungsschutz** aus, und scrollen Sie dann zum **Abschnitt Ransomware-Schutz.**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="fc2d8-131">Wählen **Sie Ransomware-Schutz verwalten aus,** um den **Bereich Ransomware-Schutz zu** öffnen.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="fc2d8-132">Wählen Sie **im Abschnitt Kontrollierter Ordnerzugriff** die Option **Geschützte Ordner aus.**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="fc2d8-133">Wählen **Sie in** der **Eingabeaufforderung für die Benutzerzugriffssteuerung Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="fc2d8-134">Der **Bereich Geschützte Ordner** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-134">The **Protected folders** pane displays.</span></span>

4. <span data-ttu-id="fc2d8-135">Wählen **Sie Geschützten Ordner hinzufügen aus,** und folgen Sie den Aufforderungen zum Hinzufügen von Ordnern.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="fc2d8-136">Verwenden von Gruppenrichtlinien zum Schutz zusätzlicher Ordner</span><span class="sxs-lookup"><span data-stu-id="fc2d8-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="fc2d8-137">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann Bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-137">On your Group Policy management computer, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure, and then and select **Edit**.</span></span>

2. <span data-ttu-id="fc2d8-138">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-138">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="fc2d8-139">Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus** Windows Defender Exploit  >  **Guard**  >  **Kontrollierter Ordnerzugriff**.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-139">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="fc2d8-140">Doppelklicken Sie **auf Konfigurierte geschützte Ordner,** und legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-140">Double-click **Configured protected folders** and set the option to **Enabled**.</span></span> <span data-ttu-id="fc2d8-141">Wählen **Sie Anzeigen** aus, und geben Sie die einzelnen Ordner ein.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-141">Select **Show** and enter each folder.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="fc2d8-142">Verwenden von PowerShell zum Schutz zusätzlicher Ordner</span><span class="sxs-lookup"><span data-stu-id="fc2d8-142">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="fc2d8-143">Geben **Sie PowerShell** im Menü Start ein, klicken Sie mit der rechten Maustaste **auf Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-143">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="fc2d8-144">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="fc2d8-144">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="fc2d8-145">Wiederholen Sie Schritt 2, bis Sie alle Ordner hinzugefügt haben, die Sie schützen möchten.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-145">Repeat step 2 until you have added all the folders you want to protect.</span></span> <span data-ttu-id="fc2d8-146">Hinzugefügte Ordner sind in der Windows-Sicherheits-App sichtbar.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-146">Folders that are added are visible in the Windows Security app.</span></span>

   ![Screenshot eines PowerShell-Fensters mit dem oben eingegebenen Cmdlet](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> <span data-ttu-id="fc2d8-148">Verwenden `Add-MpPreference` Sie zum Anfügen oder Hinzufügen von Apps zur Liste.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-148">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="fc2d8-149">Wenn Sie `Set-MpPreference` das Cmdlet verwenden, wird die vorhandene Liste überschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-149">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="fc2d8-150">Verwenden von MDM-CSPs zum Schutz zusätzlicher Ordner</span><span class="sxs-lookup"><span data-stu-id="fc2d8-150">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="fc2d8-151">Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) Configuration Service Provider (CSP), um Apps das Vornehmen von Änderungen an geschützten Ordnern zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-151">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="fc2d8-152">Zulassen, dass bestimmte Apps Änderungen an kontrollierten Ordnern vornehmen</span><span class="sxs-lookup"><span data-stu-id="fc2d8-152">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="fc2d8-153">Sie können angeben, ob bestimmte Apps immer als sicher gelten und Schreibzugriff auf Dateien in geschützten Ordnern erhalten.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-153">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="fc2d8-154">Das Zulassen von Apps kann hilfreich sein, wenn eine bestimmte App, die Sie kennen und der Sie vertrauen, durch das Feature für den kontrollierten Ordnerzugriff blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-154">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc2d8-155">Standardmäßig fügt Windows Apps hinzu, die als benutzerfreundlich für die liste zulässig gelten.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-155">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="fc2d8-156">Solche Apps, die automatisch hinzugefügt werden, werden nicht in der Liste aufgezeichnet, die in der Windows Security-App oder mithilfe der zugeordneten PowerShell-Cmdlets angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-156">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="fc2d8-157">Sie sollten die meisten Apps nicht hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-157">You shouldn't need to add most apps.</span></span> <span data-ttu-id="fc2d8-158">Fügen Sie apps nur hinzu, wenn sie blockiert werden, und Sie können ihre Vertrauenswürdigkeit überprüfen.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-158">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="fc2d8-159">Wenn Sie eine App hinzufügen, müssen Sie den Speicherort der App angeben.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-159">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="fc2d8-160">Nur die App an diesem Speicherort darf auf die geschützten Ordner zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-160">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="fc2d8-161">Wenn sich die App (mit demselben Namen) an einem anderen Speicherort befindet, wird sie nicht zur Liste der zulässigen Apps hinzugefügt und kann durch kontrollierten Ordnerzugriff blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-161">If the app (with the same name) is in a different location, it will not be added to the allow list and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="fc2d8-162">Eine zulässige Anwendung oder ein zulässiger Dienst hat nur nach dem Start Schreibzugriff auf einen kontrollierten Ordner.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-162">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="fc2d8-163">Ein Updatedienst löst beispielsweise weiterhin Ereignisse aus, nachdem er zugelassen ist, bis er beendet und neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-163">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="fc2d8-164">Verwenden der Windows Defender-Sicherheits-App zum Zulassen bestimmter Apps</span><span class="sxs-lookup"><span data-stu-id="fc2d8-164">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="fc2d8-165">Öffnen Sie die Windows Security-App, indem Sie im Startmenü nach **Sicherheit suchen.**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-165">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="fc2d8-166">Wählen Sie die Kachel **& Bedrohungsschutz** (oder das Schildsymbol auf der linken Menüleiste) aus, und wählen Sie dann **Ransomware-Schutz verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-166">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="fc2d8-167">Wählen Sie **im Abschnitt Kontrollierter Ordnerzugriff** die Option App über kontrollierten **Ordnerzugriff zulassen aus.**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-167">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="fc2d8-168">Wählen **Sie Zugelassene App hinzufügen aus,** und folgen Sie den Aufforderungen zum Hinzufügen von Apps.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-168">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

    ![Screenshot des Hinzufügens einer zugelassenen App-Schaltfläche](/microsoft-365/security/defender-endpoint/images/cfa-allow-app)

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="fc2d8-170">Verwenden von Gruppenrichtlinien zum Zulassen bestimmter Apps</span><span class="sxs-lookup"><span data-stu-id="fc2d8-170">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="fc2d8-171">Öffnen Sie auf Ihrem Gruppenrichtlinienverwaltungsgerät die [Gruppenrichtlinienverwaltungskonsole,](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-171">On your Group Policy management device, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="fc2d8-172">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-172">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="fc2d8-173">Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus** Windows Defender Exploit  >  **Guard**  >  **Kontrollierter Ordnerzugriff**.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-173">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="fc2d8-174">Doppelklicken Sie auf die Einstellung **Zugelassene Anwendungen konfigurieren,** und legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-174">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="fc2d8-175">Wählen **Sie Anzeigen** aus, und geben Sie jede App ein.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-175">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="fc2d8-176">Verwenden von PowerShell zum Zulassen bestimmter Apps</span><span class="sxs-lookup"><span data-stu-id="fc2d8-176">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="fc2d8-177">Geben **Sie PowerShell** im Menü Start ein, klicken Sie mit der rechten Maustaste **auf Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**</span><span class="sxs-lookup"><span data-stu-id="fc2d8-177">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="fc2d8-178">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="fc2d8-178">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="fc2d8-179">Wenn Sie beispielsweise die  ausführbare Dateitest.exeim Ordner *C:\apps* hinzufügen möchten, würde das Cmdlet wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="fc2d8-179">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="fc2d8-180">Verwenden Sie `Add-MpPreference -ControlledFolderAccessAllowedApplications` weiterhin, um der Liste weitere Apps hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-180">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="fc2d8-181">Apps, die mit diesem Cmdlet hinzugefügt wurden, werden in der Windows Security-App angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-181">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

![Screenshot eines PowerShell-Fensters mit dem oben eingegebenen Cmdlet](/microsoft-365/security/defender-endpoint/images/cfa-allow-app-ps)

> [!IMPORTANT]
> <span data-ttu-id="fc2d8-183">Verwenden `Add-MpPreference` Sie zum Anfügen oder Hinzufügen von Apps zur Liste.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-183">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="fc2d8-184">Wenn Sie `Set-MpPreference` das Cmdlet verwenden, wird die vorhandene Liste überschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-184">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="fc2d8-185">Verwenden von MDM-CSPs zum Zulassen bestimmter Apps</span><span class="sxs-lookup"><span data-stu-id="fc2d8-185">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="fc2d8-186">Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) Configuration Service Provider (CSP), damit Apps Änderungen an geschützten Ordnern vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-186">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="fc2d8-187">Zugriff auf geschützte Ordner durch signierte ausführbare Dateien zulassen</span><span class="sxs-lookup"><span data-stu-id="fc2d8-187">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="fc2d8-188">Microsoft Defender for Endpoint-Zertifikat- und Dateiindikatoren können signierten ausführbaren Dateien den Zugriff auf geschützte Ordner ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-188">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="fc2d8-189">Implementierungsdetails finden Sie unter [Erstellen von Indikatoren basierend auf Zertifikaten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span><span class="sxs-lookup"><span data-stu-id="fc2d8-189">For implementation details, see [Create indicators based on certificates](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span>

> [!Note]
> <span data-ttu-id="fc2d8-190">Dies gilt nicht für Skriptmodule, einschließlich Powershell.</span><span class="sxs-lookup"><span data-stu-id="fc2d8-190">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="fc2d8-191">Anpassen der Benachrichtigung</span><span class="sxs-lookup"><span data-stu-id="fc2d8-191">Customize the notification</span></span>

<span data-ttu-id="fc2d8-192">Weitere Informationen zum Anpassen der Benachrichtigung, wenn eine Regel ausgelöst wird, und zum Sperren einer App oder Datei finden Sie unter [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).</span><span class="sxs-lookup"><span data-stu-id="fc2d8-192">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).</span></span>

## <a name="see-also"></a><span data-ttu-id="fc2d8-193">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc2d8-193">See also</span></span>

- [<span data-ttu-id="fc2d8-194">Schützen wichtiger Ordner mit kontrolliertem Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="fc2d8-194">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="fc2d8-195">Aktivieren des kontrollierten Ordnerzugriffs</span><span class="sxs-lookup"><span data-stu-id="fc2d8-195">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="fc2d8-196">Bewerten von Regeln zur Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="fc2d8-196">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
