---
title: Migrieren von Geschäftlichen E-Mails und Kalendern aus Google Workspace
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie E-Mails, Kontakte und Kalender von Google Workspace zu Microsoft 365 Business migrieren.
ms.openlocfilehash: ab70a43fb7c26c23ebc9024b1cd2803c164a0aa4
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794647"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="3d6d4-103">Migrieren von Geschäftlichen E-Mails und Kalendern aus Google Workspace</span><span class="sxs-lookup"><span data-stu-id="3d6d4-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="3d6d4-104">Sie können eine vom Administrator verwaltete Migration zu Exchange Online aus Google Workspace verwenden.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="3d6d4-105">Sie können die E-Mails entweder alle gleichzeitig oder phasenweise migrieren.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="3d6d4-106">Die folgenden Schritte zeigen, wie Sie die E-Mail-Daten gleichzeitig migrieren.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="3d6d4-107">Weitere Informationen finden Sie unter [Ausführen einer G Suite-Migration.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)</span><span class="sxs-lookup"><span data-stu-id="3d6d4-107">For more information, see [Perform a G Suite migration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="3d6d4-108">Der Migrationsprozess dauert mehrere Schritte und kann abhängig von der Datenmenge, die Sie migrieren, mehrere Stunden bis zu ein paar Tage dauern.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="3d6d4-109">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="3d6d4-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="3d6d4-110">Erstellen eines Google -Dienstkontos</span><span class="sxs-lookup"><span data-stu-id="3d6d4-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="3d6d4-111">Melden Sie sich mit einem Browser Chrome bei Ihrer Google Workspace-Verwaltungskonsole [unter admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="3d6d4-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="3d6d4-112">Navigieren Sie in einer neuen Registerkarte oder einem neuen Fenster zur Seite ["Dienstkonten".](https://console.developers.google.com/iam-admin/serviceaccounts)</span><span class="sxs-lookup"><span data-stu-id="3d6d4-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="3d6d4-113">Select **Create project,** name the project and choose **Create**.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="3d6d4-114">Wählen **Sie "Dienstkonto erstellen"** aus, geben Sie einen Namen ein, wählen **Sie "Erstellen"** und dann "Fertig" **aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="3d6d4-115">Öffnen Sie das **Menü "Aktionen",** wählen Sie **"Bearbeiten"** aus, und notieren Sie sich die eindeutige ID.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="3d6d4-116">Sie benötigen diese ID später im Prozess.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="3d6d4-117">Öffnen Sie den **Abschnitt "Domänenweite Delegierung anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="3d6d4-118">Wählen **Sie "Domänenweite Delegierung für G Suite aktivieren",** geben Sie einen Produktnamen für den Zustimmungsbildschirm ein, und wählen Sie **"Speichern" aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="3d6d4-119">Der Produktname wird nicht vom Migrationsprozess verwendet, sondern zum Speichern im Dialogfeld benötigt.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="3d6d4-120">Öffnen Sie das **Menü "Aktionen"** erneut, und wählen Sie **"Schlüssel erstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="3d6d4-121">Choose **JSON**, then **Create**.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="3d6d4-122">Der private Schlüssel wird im Downloadordner auf Ihrem Gerät gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="3d6d4-123">Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="3d6d4-124">Aktivieren der API-Verwendung für das Projekt</span><span class="sxs-lookup"><span data-stu-id="3d6d4-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="3d6d4-125">Navigieren Sie zur [APIs-Seite.](https://console.developers.google.com/apis/library)</span><span class="sxs-lookup"><span data-stu-id="3d6d4-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="3d6d4-126">Geben Sie in der Suchleiste die **Gmail-API ein.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="3d6d4-127">Wählen Sie es aus, und wählen Sie dann **"Aktivieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="3d6d4-128">Wiederholen Sie diesen Vorgang für die Google Kalender-API und die Kontakte-API.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="3d6d4-129">Gewähren des Zugriffs auf das Dienstkonto</span><span class="sxs-lookup"><span data-stu-id="3d6d4-129">Grant access to the service account</span></span>

1. <span data-ttu-id="3d6d4-130">Kehren Sie zur Google Workspace-Verwaltungskonsole zurück.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="3d6d4-131">Wählen Sie **Sicherheit** aus, scrollen Sie nach unten, und öffnen Sie **API-Steuerelemente.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="3d6d4-132">Scrollen Sie nach unten, und wählen **Sie "Domänenweite Delegierung verwalten" aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="3d6d4-133">Wählen **Sie "Neu hinzufügen"** aus, und geben Sie die Client-ID ein, die Sie sich zuvor notieren.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="3d6d4-134">Geben Sie dann die OAuth-Bereiche für die Google-APIs ein.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="3d6d4-135">Diese sind unter [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) Schritt 5 verfügbar und sind:</span><span class="sxs-lookup"><span data-stu-id="3d6d4-135">These are available at [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="3d6d4-136">Choose **Authorize**.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="3d6d4-137">Erstellen einer Unterdomäne für E-Mails an Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d6d4-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="3d6d4-138">Kehren Sie zur **Google Workspace-Verwaltungskonsole** zurück.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="3d6d4-139">Select **Domains**, **Manage domains**, then, Add a domain **alias**.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="3d6d4-140">Geben Sie einen Domänenalias wie `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="3d6d4-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="3d6d4-141">Wählen Sie dann **"Weiter" aus, und überprüfen Sie den Domänenbesitz.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="3d6d4-142">Die Domänenüberprüfung dauert in der Regel nur einige Minuten, kann aber bis zu 48 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="3d6d4-143">Wechseln Sie zum [Microsoft 365 Admin Center.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="3d6d4-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="3d6d4-144">Wählen Sie **im Microsoft 365 Admin Center** im linken Navigationsbereich **"Alle** anzeigen", **"Einstellungen",** **"Domänen"** und dann **"Domäne hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="3d6d4-145">Geben Sie die zuvor erstellte Unterdomäne ein, und wählen Sie **dann "Diese Domäne verwenden" aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="3d6d4-146">Um die Domäne zu verbinden, wählen Sie **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="3d6d4-147">Scrollen Sie nach unten, und notieren Sie sich die MX-, CNAME- und TXT-Einträge.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="3d6d4-148">Kehren Sie zur **Google Admin Konsole zurück.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="3d6d4-149">Select **Domains**, select **Manage domains**, Verify **Details** and then, Manage **domain**.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="3d6d4-150">Wählen Sie in der linken Navigationsleiste **DNS** aus, und scrollen Sie nach unten zu **benutzerdefinierten Ressourceneinträgen.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="3d6d4-151">Öffnen Sie das Eintragstypdropdown, und wählen Sie **MX** aus, geben Sie die zuvor notierte MX-Eintragsinformationen ein, oder kopieren Sie sie, und fügen Sie sie ein, und wählen Sie dann **"Hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="3d6d4-152">Wiederholen Sie den Vorgang für den #A0 und den TXT-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="3d6d4-153">Es kann einige Zeit dauern, bis diese Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="3d6d4-154">Kehren Sie zu dem Ort zurück, an dem Sie im **Microsoft 365 Admin Center** auf dem Weg waren, und wählen Sie **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="3d6d4-155">Ihre Domäne ist jetzt eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="3d6d4-156">Erstellen von E-Mail-Aliasen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d6d4-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="3d6d4-157">Bevor die Migration beginnen kann, müssen Sie E-Mail-Aliase für Ihre Benutzer mit der neuen Unterdomäne erstellen.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="3d6d4-158">Um den nächsten Schritt  zu starten, wählen Sie im Assistenten zum Hinzufügen von Domänen im Microsoft 365 Admin Center **"Zu aktive Benutzer wechseln" aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="3d6d4-159">Wählen Sie einen Benutzer aus, und verwalten **Sie dann Benutzernamen und E-Mails.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="3d6d4-160">Wählen Sie **in der Dropdownliste** "Domänen" die Zuvor erstellte Unterdomäne aus.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="3d6d4-161">Geben Sie einen Benutzernamen ein, wählen **Sie "Hinzufügen",** **"Änderungen speichern"** aus, und schließen Sie das Fenster.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="3d6d4-162">Wiederholen Sie diesen Vorgang für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="3d6d4-163">Starten des Migrationsprozesses</span><span class="sxs-lookup"><span data-stu-id="3d6d4-163">Start the migration process</span></span>

<span data-ttu-id="3d6d4-164">Sobald Sie fertig sind, können Sie migrieren.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="3d6d4-165">Scrollen Sie in der linken Navigationsleiste des **Microsoft 365 Admin Centers** nach unten zu Admin **Center,** und wählen Sie **Exchange aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="3d6d4-166">Wählen **Sie unter "Empfänger"** **die Option "Migration",** **"Neu",** **"Zu Exchange Online** migrieren", **"G Suite-Migration"** und dann **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="3d6d4-167">Erstellen Sie eine CSV-Datei mit einer Liste der Postfächer, die Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="3d6d4-168">Stellen Sie sicher, dass die Datei dieses Format verwendet:</span><span class="sxs-lookup"><span data-stu-id="3d6d4-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="3d6d4-169">Weitere Informationen finden Sie [unter aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span><span class="sxs-lookup"><span data-stu-id="3d6d4-169">For details see [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="3d6d4-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="3d6d4-171">Überprüfen Sie die Administrator-E-Mail-Adresse, die Sie zu Testzwecken verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="3d6d4-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="3d6d4-173">Geben Sie einen Namen in das Feld **"Neuer Migrationsbatchname" ein.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="3d6d4-174">Geben Sie die Von Ihnen erstellte Unterdomäne im Feld **Zielzustellungsdomäne** ein, wählen Sie **"Weiter"** und dann **"Neu" aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="3d6d4-175">Nachdem die Informationen gespeichert wurden, wählen Sie **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="3d6d4-176">Sie können jetzt den Status Ihrer Migration anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="3d6d4-177">Wählen Sie nach einiger Zeit abhängig von der Anzahl der Benutzer, die Sie migrieren, die Option **"Aktualisieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="3d6d4-178">Nachdem der Status in **"Synchronisiert" geändert** wurde, wählen **Sie "Diesen Migrationsbatch abschließen"** und dann **"Ja" aus.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="3d6d4-179">Sobald der Prozess abgeschlossen ist, wird Ihr Status in Abgeschlossen **geändert.**</span><span class="sxs-lookup"><span data-stu-id="3d6d4-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="3d6d4-180">Wenn Sie möchten, können Sie Details **anzeigen auswählen,** um weitere Informationen zur Migration zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="3d6d4-181">Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-181">Select **Close**.</span></span> 
1. <span data-ttu-id="3d6d4-182">Öffnen Sie Outlook, um zu überprüfen, ob alle E-Mails von Google Workspace erfolgreich migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="3d6d4-183">Sie können dies auch für Kalenderelemente und Kontakte wiederholen.</span><span class="sxs-lookup"><span data-stu-id="3d6d4-183">You can repeat this for calendar items and contacts as well.</span></span>