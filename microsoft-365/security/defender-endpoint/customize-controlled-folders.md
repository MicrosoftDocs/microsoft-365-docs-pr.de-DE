---
title: Kontrollierte Ordnerzugriff anpassen
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
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e12368b6241a2c79eead66ed77b30b7864af3955
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326536"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="a843e-104">Kontrollierte Ordnerzugriff anpassen</span><span class="sxs-lookup"><span data-stu-id="a843e-104">Customize controlled folder access</span></span>

<span data-ttu-id="a843e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a843e-105">**Applies to:**</span></span>
- [<span data-ttu-id="a843e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a843e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a843e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a843e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="a843e-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a843e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a843e-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a843e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="a843e-110">Der kontrollierte Ordnerzugriff hilft Ihnen, wertvolle Daten vor schädlichen Apps und Bedrohungen wie Ransomware zu schützen.</span><span class="sxs-lookup"><span data-stu-id="a843e-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="a843e-111">Der kontrollierte Ordnerzugriff wird auf Windows Server 2019- und Windows 10-Clients unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a843e-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span> <span data-ttu-id="a843e-112">In diesem Artikel wird beschrieben, wie Sie die Funktionen für den kontrollierten Ordnerzugriff anpassen und die folgenden Abschnitte umfassen:</span><span class="sxs-lookup"><span data-stu-id="a843e-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="a843e-113">Schützen zusätzlicher Ordner</span><span class="sxs-lookup"><span data-stu-id="a843e-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="a843e-114">Hinzufügen von Apps, die auf geschützte Ordner zugreifen dürfen sollten</span><span class="sxs-lookup"><span data-stu-id="a843e-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="a843e-115">Zugriff auf geschützte Ordner durch signierte ausführbare Dateien zulassen</span><span class="sxs-lookup"><span data-stu-id="a843e-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="a843e-116">Anpassen der Benachrichtigung</span><span class="sxs-lookup"><span data-stu-id="a843e-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="a843e-117">Der kontrollierte Ordnerzugriff überwacht Apps auf Aktivitäten, die als schädlich erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="a843e-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="a843e-118">Manchmal werden legitime Apps am Vornehmen von Änderungen an Ihren Dateien blockiert.</span><span class="sxs-lookup"><span data-stu-id="a843e-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="a843e-119">Wenn sich der kontrollierte Ordnerzugriff auf die Produktivität [](audit-windows-defender.md) Ihrer Organisation auswirken sollte, können Sie die Ausführung dieses Features im Überwachungsmodus in Betracht ziehen, um die Auswirkungen vollständig zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="a843e-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="a843e-120">Schützen zusätzlicher Ordner</span><span class="sxs-lookup"><span data-stu-id="a843e-120">Protect additional folders</span></span>

<span data-ttu-id="a843e-121">Der kontrollierte Ordnerzugriff gilt für viele Systemordner und Standardspeicherorte, einschließlich Ordner wie **Dokumente,** **Bilder** und **Filme.**</span><span class="sxs-lookup"><span data-stu-id="a843e-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="a843e-122">Sie können andere zu schützende Ordner hinzufügen, die Standardordner in der Standardliste können jedoch nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="a843e-122">You can add other folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="a843e-123">Das Hinzufügen anderer Ordner zum kontrollierten Ordnerzugriff kann für Fälle hilfreich sein, in denen Sie keine Dateien in den standardmäßigen Windows-Bibliotheken speichern oder den Standardspeicherort Ihrer Bibliotheken geändert haben.</span><span class="sxs-lookup"><span data-stu-id="a843e-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="a843e-124">Sie können auch Netzwerkfreigaben und zugeordnete Laufwerke angeben.</span><span class="sxs-lookup"><span data-stu-id="a843e-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="a843e-125">Umgebungsvariablen und Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a843e-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="a843e-126">Informationen zur Verwendung von Platzhaltern finden Sie unter Verwenden von Platzhaltern in den Listen für Dateinamen und Ordnerpfad oder [Erweiterungsausschluss](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="a843e-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="a843e-127">Sie können die Windows-Sicherheits-App, Gruppenrichtlinien, PowerShell-Cmdlets oder Konfigurationsdienstanbieter für die Mobile Geräteverwaltung verwenden, um geschützte Ordner hinzuzufügen und zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a843e-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="a843e-128">Verwenden der Windows Security-App zum Schutz zusätzlicher Ordner</span><span class="sxs-lookup"><span data-stu-id="a843e-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="a843e-129">Öffnen Sie die Windows Security-App, indem Sie das Schildsymbol in der Taskleiste auswählen oder im Menü Start *nach* Sicherheit suchen.</span><span class="sxs-lookup"><span data-stu-id="a843e-129">Open the Windows Security app by selecting the shield icon in the task bar, or by searching for *security* in the Start menu.</span></span>

2. <span data-ttu-id="a843e-130">Wählen **Sie Virenschutz & bedrohungsschutz** aus, und scrollen Sie dann zum **Abschnitt Ransomware-Schutz.**</span><span class="sxs-lookup"><span data-stu-id="a843e-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="a843e-131">Wählen **Sie Ransomware-Schutz verwalten aus,** um den **Bereich Ransomware-Schutz zu** öffnen.</span><span class="sxs-lookup"><span data-stu-id="a843e-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="a843e-132">Wählen Sie **im Abschnitt Kontrollierter Ordnerzugriff** die Option **Geschützte Ordner aus.**</span><span class="sxs-lookup"><span data-stu-id="a843e-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="a843e-133">Wählen **Sie in** der **Eingabeaufforderung für die Benutzerzugriffssteuerung Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="a843e-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="a843e-134">Der **Bereich Geschützte Ordner** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a843e-134">The **Protected folders** pane displays.</span></span>

6. <span data-ttu-id="a843e-135">Wählen **Sie Geschützten Ordner hinzufügen aus,** und folgen Sie den Aufforderungen zum Hinzufügen von Ordnern.</span><span class="sxs-lookup"><span data-stu-id="a843e-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="a843e-136">Verwenden von Gruppenrichtlinien zum Schutz zusätzlicher Ordner</span><span class="sxs-lookup"><span data-stu-id="a843e-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="a843e-137">Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span><span class="sxs-lookup"><span data-stu-id="a843e-137">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span></span> 

2. <span data-ttu-id="a843e-138">Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="a843e-138">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="a843e-139">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfigurationsrichtlinien**  >    >  **Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="a843e-139">In your **Group Policy Management Editor**, go to **Computer configuration** > **Policies** > **Administrative templates**.</span></span>

4. <span data-ttu-id="a843e-140">Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus** Windows Defender Exploit  >  **Guard**  >  **Kontrollierter Ordnerzugriff**.</span><span class="sxs-lookup"><span data-stu-id="a843e-140">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span> <br/><span data-ttu-id="a843e-141">**HINWEIS**: In älteren Versionen von Windows wird möglicherweise Windows Defender **Antivirus** anstelle von **Microsoft Defender Antivirus angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="a843e-141">**NOTE**: On older versions of Windows, you might see **Windows Defender Antivirus** instead of **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="a843e-142">Doppelklicken **Sie auf Konfigurierte geschützte Ordner,** und legen Sie dann die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="a843e-142">Double-click **Configured protected folders**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="a843e-143">Wählen **Sie Anzeigen** aus, und geben Sie jeden Ordner an, den Sie schützen möchten.</span><span class="sxs-lookup"><span data-stu-id="a843e-143">Select **Show**, and specify each folder that you want to protect.</span></span>

6. <span data-ttu-id="a843e-144">Stellen Sie Ihr Gruppenrichtlinienobjekt wie gewöhnlich zur Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a843e-144">Deploy your Group Policy Object as you usually do.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="a843e-145">Verwenden von PowerShell zum Schutz zusätzlicher Ordner</span><span class="sxs-lookup"><span data-stu-id="a843e-145">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="a843e-146">Geben **Sie PowerShell** im Menü Start ein, klicken Sie mit der rechten Maustaste **auf Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**</span><span class="sxs-lookup"><span data-stu-id="a843e-146">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="a843e-147">Geben Sie das folgende PowerShell-Cmdlet ein, das durch den Pfad des `<the folder to be protected>` Ordners ersetzt wird (z. B. `"c:\apps\"` ):</span><span class="sxs-lookup"><span data-stu-id="a843e-147">Type the following PowerShell cmdlet, replacing `<the folder to be protected>` with the folder's path (such as `"c:\apps\"`):</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="a843e-148">Wiederholen Sie Schritt 2 für jeden Ordner, den Sie schützen möchten.</span><span class="sxs-lookup"><span data-stu-id="a843e-148">Repeat step 2 for each folder that you want to protect.</span></span> <span data-ttu-id="a843e-149">Geschützte Ordner sind in der Windows-Sicherheits-App sichtbar.</span><span class="sxs-lookup"><span data-stu-id="a843e-149">Folders that are protected are visible in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="PowerShell-Fenster mit angezeigten Cmdlet":::

> [!IMPORTANT]
> <span data-ttu-id="a843e-151">Verwenden `Add-MpPreference` Sie zum Anfügen oder Hinzufügen von Apps zur Liste und nicht `Set-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="a843e-151">Use `Add-MpPreference` to append or add apps to the list and not `Set-MpPreference`.</span></span> <span data-ttu-id="a843e-152">Wenn Sie `Set-MpPreference` das Cmdlet verwenden, wird die vorhandene Liste überschrieben.</span><span class="sxs-lookup"><span data-stu-id="a843e-152">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="a843e-153">Verwenden von MDM-CSPs zum Schutz zusätzlicher Ordner</span><span class="sxs-lookup"><span data-stu-id="a843e-153">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="a843e-154">Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) Configuration Service Provider (CSP), um Apps das Vornehmen von Änderungen an geschützten Ordnern zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a843e-154">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="a843e-155">Zulassen, dass bestimmte Apps Änderungen an kontrollierten Ordnern vornehmen</span><span class="sxs-lookup"><span data-stu-id="a843e-155">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="a843e-156">Sie können angeben, ob bestimmte Apps immer als sicher gelten und Schreibzugriff auf Dateien in geschützten Ordnern erhalten.</span><span class="sxs-lookup"><span data-stu-id="a843e-156">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="a843e-157">Das Zulassen von Apps kann hilfreich sein, wenn eine bestimmte App, die Sie kennen und der Sie vertrauen, durch das Feature für den kontrollierten Ordnerzugriff blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="a843e-157">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a843e-158">Standardmäßig fügt Windows Apps hinzu, die als benutzerfreundlich für die liste zulässig gelten.</span><span class="sxs-lookup"><span data-stu-id="a843e-158">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="a843e-159">Solche Apps, die automatisch hinzugefügt werden, werden nicht in der Liste aufgezeichnet, die in der Windows Security-App oder mithilfe der zugeordneten PowerShell-Cmdlets angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a843e-159">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="a843e-160">Sie sollten die meisten Apps nicht hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a843e-160">You shouldn't need to add most apps.</span></span> <span data-ttu-id="a843e-161">Fügen Sie apps nur hinzu, wenn sie blockiert werden, und Sie können ihre Vertrauenswürdigkeit überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a843e-161">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="a843e-162">Wenn Sie eine App hinzufügen, müssen Sie den Speicherort der App angeben.</span><span class="sxs-lookup"><span data-stu-id="a843e-162">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="a843e-163">Nur die App an diesem Speicherort darf auf die geschützten Ordner zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a843e-163">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="a843e-164">Wenn sich die App (mit demselben Namen) an einem anderen Speicherort befindet, wird sie der Allowlist nicht hinzugefügt und kann durch kontrollierten Ordnerzugriff blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="a843e-164">If the app (with the same name) is in a different location, it will not be added to the allowlist and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="a843e-165">Eine zulässige Anwendung oder ein zulässiger Dienst hat nur nach dem Start Schreibzugriff auf einen kontrollierten Ordner.</span><span class="sxs-lookup"><span data-stu-id="a843e-165">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="a843e-166">Ein Updatedienst löst beispielsweise weiterhin Ereignisse aus, nachdem er zugelassen ist, bis er beendet und neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="a843e-166">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="a843e-167">Verwenden der Windows Defender-Sicherheits-App zum Zulassen bestimmter Apps</span><span class="sxs-lookup"><span data-stu-id="a843e-167">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="a843e-168">Öffnen Sie die Windows Security-App, indem Sie im Startmenü nach **Sicherheit suchen.**</span><span class="sxs-lookup"><span data-stu-id="a843e-168">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="a843e-169">Wählen Sie die Kachel **& Bedrohungsschutz** (oder das Schildsymbol auf der linken Menüleiste) aus, und wählen Sie dann **Ransomware-Schutz verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="a843e-169">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="a843e-170">Wählen Sie **im Abschnitt Kontrollierter Ordnerzugriff** die Option App über kontrollierten **Ordnerzugriff zulassen aus.**</span><span class="sxs-lookup"><span data-stu-id="a843e-170">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="a843e-171">Wählen **Sie Zugelassene App hinzufügen aus,** und folgen Sie den Aufforderungen zum Hinzufügen von Apps.</span><span class="sxs-lookup"><span data-stu-id="a843e-171">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Hinzufügen einer zugelassenen App-Schaltfläche":::

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="a843e-173">Verwenden von Gruppenrichtlinien zum Zulassen bestimmter Apps</span><span class="sxs-lookup"><span data-stu-id="a843e-173">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="a843e-174">Öffnen Sie auf Ihrem Gruppenrichtlinienverwaltungsgerät die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="a843e-174">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="a843e-175">Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computerkonfiguration**, und wählen Sie **Administrative Vorlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="a843e-175">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="a843e-176">Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus** Windows Defender Exploit  >  **Guard**  >  **Kontrollierter Ordnerzugriff**.</span><span class="sxs-lookup"><span data-stu-id="a843e-176">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="a843e-177">Doppelklicken Sie auf die Einstellung **Zugelassene Anwendungen konfigurieren,** und legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="a843e-177">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="a843e-178">Wählen **Sie Anzeigen** aus, und geben Sie jede App ein.</span><span class="sxs-lookup"><span data-stu-id="a843e-178">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="a843e-179">Verwenden von PowerShell zum Zulassen bestimmter Apps</span><span class="sxs-lookup"><span data-stu-id="a843e-179">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="a843e-180">Geben **Sie PowerShell** im Menü Start ein, klicken Sie mit der rechten Maustaste **auf Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**</span><span class="sxs-lookup"><span data-stu-id="a843e-180">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="a843e-181">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="a843e-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="a843e-182">Wenn Sie beispielsweise die  ausführbare Dateitest.exeim Ordner *C:\apps* hinzufügen möchten, würde das Cmdlet wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="a843e-182">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="a843e-183">Verwenden Sie `Add-MpPreference -ControlledFolderAccessAllowedApplications` weiterhin, um der Liste weitere Apps hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a843e-183">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="a843e-184">Apps, die mit diesem Cmdlet hinzugefügt wurden, werden in der Windows Security-App angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a843e-184">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="PowerShell-Cmdlet zum Zulassen einer App":::

> [!IMPORTANT]
> <span data-ttu-id="a843e-186">Verwenden `Add-MpPreference` Sie zum Anfügen oder Hinzufügen von Apps zur Liste.</span><span class="sxs-lookup"><span data-stu-id="a843e-186">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="a843e-187">Wenn Sie `Set-MpPreference` das Cmdlet verwenden, wird die vorhandene Liste überschrieben.</span><span class="sxs-lookup"><span data-stu-id="a843e-187">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="a843e-188">Verwenden von MDM-CSPs zum Zulassen bestimmter Apps</span><span class="sxs-lookup"><span data-stu-id="a843e-188">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="a843e-189">Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) Configuration Service Provider (CSP), damit Apps Änderungen an geschützten Ordnern vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="a843e-189">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="a843e-190">Zugriff auf geschützte Ordner durch signierte ausführbare Dateien zulassen</span><span class="sxs-lookup"><span data-stu-id="a843e-190">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="a843e-191">Microsoft Defender for Endpoint-Zertifikat- und Dateiindikatoren können signierten ausführbaren Dateien den Zugriff auf geschützte Ordner ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a843e-191">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="a843e-192">Implementierungsdetails finden Sie unter [Erstellen von Indikatoren basierend auf Zertifikaten](indicator-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a843e-192">For implementation details, see [Create indicators based on certificates](indicator-certificates.md).</span></span>

> [!Note]
> <span data-ttu-id="a843e-193">Dies gilt nicht für Skriptmodule, einschließlich Powershell.</span><span class="sxs-lookup"><span data-stu-id="a843e-193">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="a843e-194">Anpassen der Benachrichtigung</span><span class="sxs-lookup"><span data-stu-id="a843e-194">Customize the notification</span></span>

<span data-ttu-id="a843e-195">Weitere Informationen zum Anpassen der Benachrichtigung, wenn eine Regel ausgelöst wird, und zum Sperren einer App oder Datei finden Sie unter [Configure alert notifications in Microsoft Defender for Endpoint](configure-email-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="a843e-195">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](configure-email-notifications.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a843e-196">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a843e-196">See also</span></span>

- [<span data-ttu-id="a843e-197">Schützen wichtiger Ordner mit kontrolliertem Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="a843e-197">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="a843e-198">Kontrollierte Ordnerzugriff aktivieren</span><span class="sxs-lookup"><span data-stu-id="a843e-198">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="a843e-199">Auswerten der Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="a843e-199">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
