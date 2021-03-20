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
ms.openlocfilehash: d6639032b379a2cd632b6ab6ee7e4082b1e7be0b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913622"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="bd2c9-103">Migrieren von Geschäftlichen E-Mails und Kalendern aus Google Workspace</span><span class="sxs-lookup"><span data-stu-id="bd2c9-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="bd2c9-104">Sie können eine vom Administrator verwaltete Migration von Google Workspace zu Exchange Online verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="bd2c9-105">Sie können die E-Mails entweder alle gleichzeitig oder phasenweise migrieren.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="bd2c9-106">Die folgenden Schritte zeigen, wie Sie die E-Mail-Daten gleichzeitig migrieren.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="bd2c9-107">Weitere Informationen finden Sie unter [Perform a G Suite migration](/exchange/mailbox-migration/perform-g-suite-migration).</span><span class="sxs-lookup"><span data-stu-id="bd2c9-107">For more information, see [Perform a G Suite migration](/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="bd2c9-108">Der Migrationsprozess dauert mehrere Schritte und kann abhängig von der Datenmenge, die Sie migrieren, mehrere Stunden bis ein paar Tage dauern.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="bd2c9-109">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="bd2c9-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="bd2c9-110">Erstellen eines Google-Dienstkontos</span><span class="sxs-lookup"><span data-stu-id="bd2c9-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="bd2c9-111">Melden Sie sich mit einem Chrome-Browser bei Ihrer Google Workspace-Verwaltungskonsole unter [admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="bd2c9-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="bd2c9-112">Navigieren Sie in einer neuen Registerkarte oder einem neuen Fenster zur Seite [Dienstkonten.](https://console.developers.google.com/iam-admin/serviceaccounts)</span><span class="sxs-lookup"><span data-stu-id="bd2c9-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="bd2c9-113">Wählen **Sie Projekt erstellen** aus, benennen Sie das Projekt, und wählen Sie Erstellen **aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="bd2c9-114">Wählen **Sie Dienstkonto erstellen** aus, geben Sie einen Namen ein, wählen Sie **Erstellen** und dann **Fertig aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="bd2c9-115">Öffnen Sie das **Menü** Aktionen, wählen **Sie Bearbeiten** aus, und notieren Sie sich die eindeutige ID.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="bd2c9-116">Sie benötigen diese ID später im Prozess.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="bd2c9-117">Öffnen Sie den **Abschnitt Domänenweite Delegierung** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="bd2c9-118">Wählen **Sie G Suite Domänenweite Delegierung aktivieren** aus, geben Sie einen Produktnamen für den Zustimmungsbildschirm ein, und wählen Sie Speichern **aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="bd2c9-119">Der Produktname wird vom Migrationsprozess nicht verwendet, wird jedoch zum Speichern im Dialogfeld benötigt.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="bd2c9-120">Öffnen Sie das **Menü** Aktionen erneut, und wählen Sie **Schlüssel erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="bd2c9-121">Wählen **Sie JSON** und dann **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="bd2c9-122">Der private Schlüssel wird im Downloadordner auf Ihrem Gerät gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="bd2c9-123">Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="bd2c9-124">Aktivieren der API-Verwendung für das Projekt</span><span class="sxs-lookup"><span data-stu-id="bd2c9-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="bd2c9-125">Navigieren Sie zur [Seite APIs](https://console.developers.google.com/apis/library).</span><span class="sxs-lookup"><span data-stu-id="bd2c9-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="bd2c9-126">Geben Sie in der Suchleiste die **Gmail-API ein.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="bd2c9-127">Wählen Sie sie aus, und wählen Sie dann **Aktivieren aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="bd2c9-128">Wiederholen Sie diesen Vorgang für die Google Calendar API und die Contacts-API.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="bd2c9-129">Gewähren des Zugriffs auf das Dienstkonto</span><span class="sxs-lookup"><span data-stu-id="bd2c9-129">Grant access to the service account</span></span>

1. <span data-ttu-id="bd2c9-130">Kehren Sie zur Google Workspace-Verwaltungskonsole zurück.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="bd2c9-131">Wählen **Sie Sicherheit** aus, scrollen Sie nach unten, und öffnen Sie **API-Steuerelemente.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="bd2c9-132">Scrollen Sie nach unten, und wählen **Sie Domänenweite Delegierung verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="bd2c9-133">Wählen **Sie Neu hinzufügen** aus, und geben Sie die Client-ID ein, die Sie zuvor notieren haben.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="bd2c9-134">Geben Sie dann die OAuth-Bereiche für Google-APIs ein.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="bd2c9-135">Diese sind unter [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) Schritt 5 verfügbar und sind:</span><span class="sxs-lookup"><span data-stu-id="bd2c9-135">These are available at [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="bd2c9-136">Wählen Sie **Autorisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="bd2c9-137">Erstellen einer Unterdomäne für E-Mails, die zu Microsoft 365 gehen</span><span class="sxs-lookup"><span data-stu-id="bd2c9-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="bd2c9-138">Kehren Sie zur **Google Workspace-Verwaltungskonsole** zurück.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="bd2c9-139">Wählen **Sie Domänen**, Domänen **verwalten** und dann **Domänenalias hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="bd2c9-140">Geben Sie einen Domänenalias wie ein `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="bd2c9-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="bd2c9-141">Wählen Sie dann **Weiter aus, und überprüfen Sie den Domänenbesitz.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="bd2c9-142">Die Domänenüberprüfung dauert in der Regel nur wenige Minuten, kann jedoch bis zu 48 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="bd2c9-143">Wechseln Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="bd2c9-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="bd2c9-144">Wählen Sie **im Microsoft 365 Admin Center** im linken Navigations navi die Option **Alle** anzeigen , **Einstellungen**, **Domänen** und dann Domäne **hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="bd2c9-145">Geben Sie die zuvor erstellte Unterdomäne ein, und wählen Sie **Diese Domäne verwenden aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="bd2c9-146">Um eine Verbindung mit der Domäne herzustellen, wählen Sie **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="bd2c9-147">Scrollen Sie nach unten, und notieren Sie sich die MX-, CNAME- und TXT-Einträge.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="bd2c9-148">Kehren Sie zur **Google Admin Console zurück.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="bd2c9-149">Wählen **Sie Domänen** aus, wählen Sie Domänen **verwalten,** **Details überprüfen** und dann Domäne verwalten **aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="bd2c9-150">Wählen Sie im linken Navigationsgerät **DNS aus,** und scrollen Sie nach unten zu **Benutzerdefinierte Ressourceneinträge**.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="bd2c9-151">Öffnen Sie das Dropdownmenü datensatztyp, und wählen Sie **MX** aus, geben Sie die zuvor notierte MX-Eintragsinformationen ein, oder kopieren Sie sie, und fügen Sie dann **Hinzufügen ein.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="bd2c9-152">Wiederholen Sie den Vorgang für den CNAME-Eintrag und den TXT-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="bd2c9-153">Es kann einige Zeit dauern, bis diese Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="bd2c9-154">Kehren Sie zu dem Ort zurück, an dem Sie im **Microsoft 365 Admin Center** auf dem Weg waren, und wählen Sie Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="bd2c9-155">Ihre Domäne ist jetzt eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="bd2c9-156">Erstellen von E-Mail-Aliasen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd2c9-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="bd2c9-157">Bevor die Migration beginnen kann, müssen Sie E-Mail-Aliase für Ihre Benutzer mit der neuen Unterdomäne erstellen.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="bd2c9-158">Um den nächsten Schritt zu starten, wählen Sie im Assistenten Zum Hinzufügen von **Domänen** im Microsoft 365 Admin Center Die Option **Zu Aktive Benutzer wechseln aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="bd2c9-159">Wählen Sie einen Benutzer und dann Benutzernamen **und E-Mail verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="bd2c9-160">Wählen Sie **im Dropdownmenü** Domänen die zuvor erstellte Unterdomäne aus.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="bd2c9-161">Geben Sie einen Benutzernamen ein, wählen **Sie Hinzufügen**, **Speichern** von Änderungen aus, und schließen Sie das Fenster.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="bd2c9-162">Wiederholen Sie diesen Vorgang für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="bd2c9-163">Starten des Migrationsprozesses</span><span class="sxs-lookup"><span data-stu-id="bd2c9-163">Start the migration process</span></span>

<span data-ttu-id="bd2c9-164">Sobald Sie fertig sind, können Sie migrieren.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="bd2c9-165">Scrollen Sie im linken Navigations navi des **Microsoft 365 Admin Centers** nach unten zu Admin **Center,** und wählen Sie **Exchange aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="bd2c9-166">Wählen **Sie unter Empfänger** die Option **Migration** aus, wählen **Sie Neu**, Zu Exchange **Online** migrieren, **G Suite-Migration** und dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="bd2c9-167">Erstellen Sie eine CSV-Datei mit einer Liste der Postfächer, die Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="bd2c9-168">Stellen Sie sicher, dass die Datei diesem Format folgt:</span><span class="sxs-lookup"><span data-stu-id="bd2c9-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="bd2c9-169">Weitere Informationen finden Sie [unter aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span><span class="sxs-lookup"><span data-stu-id="bd2c9-169">For details see [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="bd2c9-170">Wählen **Sie Datei auswählen** aus, navigieren Sie zur CSV-Datei, wählen Sie sie aus, wählen Sie **Öffnen** und dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="bd2c9-171">Überprüfen Sie die Administrator-E-Mail-Adresse, die Sie zum Testen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="bd2c9-172">Wählen **Sie Datei auswählen** aus, navigieren Sie zu der zuvor erstellten JSON-Datei (in der Regel im Ordner Downloads auf Ihrem Computer), wählen Sie sie aus, wählen Sie **Öffnen** und dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="bd2c9-173">Geben Sie im Feld **Neuer Migrationsbatchname einen Namen ein.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="bd2c9-174">Geben Sie die von Ihnen erstellte Unterdomäne in das Feld **Zielzustellungsdomäne** ein, wählen Sie **Weiter** und dann **Neu aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="bd2c9-175">Nachdem die Informationen gespeichert wurden, wählen Sie **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="bd2c9-176">Sie können nun den Status Ihrer Migration anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="bd2c9-177">Wählen Sie nach einiger Zeit abhängig davon, wie viele Benutzer Sie migrieren, Aktualisieren **aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="bd2c9-178">Sobald der Status in **Synchronisiert geändert wurde,** wählen Sie **Diesen Migrationsbatch abschließen** und dann Ja **aus.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="bd2c9-179">Sobald der Prozess abgeschlossen ist, wird Ihr Status in **Abgeschlossen geändert.**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="bd2c9-180">Wenn Sie möchten, können Sie Details anzeigen **auswählen,** um weitere Informationen zur Migration zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="bd2c9-181">Wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-181">Select **Close**.</span></span> 
1. <span data-ttu-id="bd2c9-182">Öffnen Sie Outlook, um zu überprüfen, ob alle E-Mails von Google Workspace erfolgreich migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="bd2c9-183">Sie können dies auch für Kalenderelemente und Kontakte wiederholen.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-183">You can repeat this for calendar items and contacts as well.</span></span>