---
title: Testen von Microsoft 365 aus Ihrer benutzerdefinierten Domäne
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie die E-Mail-Funktionalität aus Ihrer benutzerdefinierten Domäne an ein Microsoft 365-Postfach mit nur zwei Testkonten testen können.
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186043"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="ed7c3-103">Testen von Microsoft 365 aus Ihrer benutzerdefinierten Domäne</span><span class="sxs-lookup"><span data-stu-id="ed7c3-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="ed7c3-104">Sie können Microsoft 365 mit den folgenden Anforderungen und Einschränkungen testen:</span><span class="sxs-lookup"><span data-stu-id="ed7c3-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="ed7c3-105">Ihr aktueller E-Mail-Anbieter muss E-Mail-Weiterleitung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="ed7c3-106">Sie müssen Ihre Microsoft 365-DNS-Einträge bei Ihrem DNS-Hostinganbieter verwalten, statt diese Einträge von Microsoft 365 verwalten zu lassen.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="ed7c3-107">Weitere Informationen finden Sie unter [Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="ed7c3-107">To learn more, see [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

- <span data-ttu-id="ed7c3-108">Frei/Gebucht-Informationen für Benutzer auf dem anderen E-Mail-Server stehen nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="ed7c3-109">Administratoren können nicht alle Benutzerkonten von einem einzigen Standort aus verwalten.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="ed7c3-110">Möglicherweise sind die Benutzer nicht in der Lage, Microsoft 365-Spamfilter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="ed7c3-111">Einrichten eines Microsoft 365-Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="ed7c3-111">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="ed7c3-112">Führen Sie die folgenden Schritte aus, um ein Microsoft 365-Pilotprojekt einzurichten:</span><span class="sxs-lookup"><span data-stu-id="ed7c3-112">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="ed7c3-113">Schritt 1: Anmelden beim Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="ed7c3-113">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="ed7c3-114">Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-114">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="ed7c3-115">Wählen Sie im linken Navigationsbereich **Einstellungen** > **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-115">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="ed7c3-116">Schritt 2: Überprüfung, ob Sie die gewünschte Domäne besitzen</span><span class="sxs-lookup"><span data-stu-id="ed7c3-116">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="ed7c3-117">Klicken Sie auf der Seite **Domänen** auf **Domäne hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-117">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="ed7c3-118">Geben Sie den Domänennamen in das Feld ein, wählen Sie **Diese Domäne verwenden** aus, und wählen Sie dann **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-118">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="ed7c3-119">Wählen Sie die Dienste aus, die Sie mit Ihrer Domäne testen möchten, z. B. E-Mail und Chat.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-119">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="ed7c3-120">Befolgen Sie auf der Seite **Domäne überprüfen** die schrittweisen Anleitungen, und wählen Sie dann **Überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-120">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="ed7c3-121">Es kann zwischen einigen Minuten und 72 Stunden dauern, bis DNS-Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-121">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="ed7c3-122">Wenn die Überprüfung erfolgreich ist, werden Sie aufgefordert, Ihre DNS-Einträge zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-122">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="ed7c3-123">Schritt 3: Kennzeichnen der Domäne als freigegeben in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ed7c3-123">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="ed7c3-124">Wählen Sie im Exchange Admin Center im Abschnitt **Nachrichtenfluss** die Option **Akzeptierte Domänen** aus, und wählen Sie dann die Domäne aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-124">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="ed7c3-125">Doppelklicken Sie, um das Fenster zu öffnen, und wählen Sie dann **Internes Relay** aus.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-125">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="ed7c3-126">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-126">Select **Save**.</span></span>

    <span data-ttu-id="ed7c3-127">Diese Einstellung wird möglicherweise erst nach einigen Minuten wirksam.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-127">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="ed7c3-128">Schritt 4: Entsperren des vorhandenen Mailservers (optional)</span><span class="sxs-lookup"><span data-stu-id="ed7c3-128">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="ed7c3-129">Microsoft 365 verwendet Exchange Online Protection (EOP) zum Schutz vor Spam.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-129">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="ed7c3-130">EOP blockiert möglicherweise Ihren vorhandenen E-Mail-Server, wenn ein hohes Spamaufkommen erkannt wird, das von Ihrem aktuellen E-Mail-Server weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-130">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="ed7c3-131">Wenn Sie den Spamschutz für Ihren anderen E-Mail-Anbieter als vertrauenswürdig einstufen, können Sie die Blockierung des Servers in Microsoft 365 aufheben.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-131">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="ed7c3-132">Wenn Sie die Blockierung des vorhandenen E-Mail-Servers aufheben, können alle Spamnachrichten, die über den ursprünglichen Server eintreffen, an die Microsoft 365-Postfächer übermittelt werden, und Sie können den Spamschutz durch Microsoft 365 nicht auswerten.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-132">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="ed7c3-133">Wählen Sie im Navigationsbereich des Exchange Admin Centers **Schutz** aus, und wählen Sie dann **Verbindungsfilter** aus.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-133">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="ed7c3-134">Wählen Sie in der **IP-Zulassungsliste** den Eintrag **+** aus, und fügen Sie die IP-Adresse des Mailservers für Ihren aktuellen E-Mail-Anbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-134">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="ed7c3-135">Schritt 5: Erstellen von Benutzerkonten und Festlegen der primären Antwortadresse</span><span class="sxs-lookup"><span data-stu-id="ed7c3-135">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="ed7c3-136">Wählen Sie linken Navigationsbereich des Microsoft 365 Admin Centers **Benutzer** > **Aktive Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-136">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="ed7c3-137">Erstellen Sie zwei Testkonten, indem Sie zwei vorhandene Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-137">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="ed7c3-138">Wählen Sie für jedes Konto **+ Benutzer hinzufügen** aus, und geben Sie die erforderlichen Informationen ein, einschließlich der Kennwortmethode, die Sie testen möchten.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-138">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="ed7c3-139">Um sicherzustellen, dass die E-Mail eines Benutzers unverändert bleibt, muss das Feld **Benutzername** der aktuellen E-Mail-Adresse des Benutzers entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-139">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="ed7c3-140">Wählen Sie die entsprechende Lizenz aus, klicken Sie auf **Weiter**, und klicken Sie dann auf **Hinzufügen fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-140">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="ed7c3-141">Wählen Sie neben **Benutzername** Ihren benutzerdefinierten Domänennamen aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-141">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="ed7c3-142">Wählen Sie **Erstellen** > **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-142">Select **Create** > **Close**.</span></span>

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="ed7c3-143">Schritt 6: Aktualisieren der DNS-Einträge bei Ihrem DNS-Hostinganbieter</span><span class="sxs-lookup"><span data-stu-id="ed7c3-143">Step 6: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="ed7c3-144">Melden Sie sich bei der Website Ihres DNS-Hostinganbieters an, und folgen Sie den Anweisungen unter [Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="ed7c3-144">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="ed7c3-145">**Machen Sie die folgenden beiden Ausnahmen:**</span><span class="sxs-lookup"><span data-stu-id="ed7c3-145">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="ed7c3-146">Erstellen Sie keinen neuen MX-Eintrag bzw. ändern Sie Ihren bestehenden MX-Eintrag nicht.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-146">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="ed7c3-147">Wenn Sie bereits über einen SPF-Eintrag (Sender Policy Framework) für Ihren bisherigen E-Mail-Anbieter verfügen, erstellen Sie keinen neuen SPF (TXT)-Eintrag für Exchange Online, sondern fügen Sie dem vorhandenen TXT-Eintrag "include:spf.protection.outlook.com" hinzu.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-147">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="ed7c3-148">Beispiel: "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all"</span><span class="sxs-lookup"><span data-stu-id="ed7c3-148">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="ed7c3-149">Wenn Sie nicht über einen SPF-Eintrag verfügen, ändern Sie den von Microsoft 365 empfohlenen so, dass er die Domäne für Ihren aktuellen E-Mail-Anbieter einschließt, und fügen Sie "spf.protection.outlook.com" hinzu.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-149">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="ed7c3-150">Dadurch werden ausgehende Nachrichten von beiden E-Mail-Systemen autorisiert.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-150">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="ed7c3-151">Schritt 7: Einrichten von E-Mail-Weiterleitung bei Ihrem aktuellen Anbieter</span><span class="sxs-lookup"><span data-stu-id="ed7c3-151">Step 7: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="ed7c3-152">Richten Sie bei Ihrem aktuellen E-Mail-Anbieter Weiterleitung für die E-Mail-Konten Ihrer Benutzer an Ihre onmicrosoft.com-Domäne ein:</span><span class="sxs-lookup"><span data-stu-id="ed7c3-152">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="ed7c3-153">Leiten Sie das Postfach des Benutzers A an usera@yourcompany.onmicrosoft.com weiter.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-153">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="ed7c3-154">Leiten Sie das Postfach des Benutzers B an userb@yourcompany.onmicrosoft.com weiter.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-154">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="ed7c3-155">Nachdem Sie diesen Schritt ausgeführt haben, sind alle an usera@yourcompany.com und userb@yourcompany.com gesendeten E-Mails in Microsoft 365 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-155">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="ed7c3-156">Wenden Sie sich an Ihren derzeitigen E-Mail-Anbieter, um die genauen Schritte für das Einrichten der E-Mail-Weiterleitung zu erfragen.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-156">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="ed7c3-157">Sie brauchen keine Kopie von Nachrichten beim aktuellen E-Mail-Anbieter zu behalten.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-157">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="ed7c3-158">Die meisten Anbieter leiten E-Mail so weiter, dass die Antwortadresse des Absenders erhalten bleibt, sodass Antworten an den ursprünglichen Absender gehen.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-158">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-8-test-mail-flow"></a><span data-ttu-id="ed7c3-159">Schritt 8: Testen des Nachrichtenflusses</span><span class="sxs-lookup"><span data-stu-id="ed7c3-159">Step 8: Test mail flow</span></span>

1. <span data-ttu-id="ed7c3-160">Melden Sie sich mit den Anmeldeinformationen für Benutzer A bei Outlook Web App an.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-160">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="ed7c3-161">Führen Sie die folgenden Tests aus:</span><span class="sxs-lookup"><span data-stu-id="ed7c3-161">Perform these tests:</span></span>

    - <span data-ttu-id="ed7c3-162">Testen Sie lokale Microsoft-E-Mail, indem Sie eine E-Mail z. B. an Benutzer B senden. Die E-Mail wird sofort zugestellt.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-162">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="ed7c3-163">In diesem Szenario wird die Nachricht nicht an das Postfach für Benutzer B auf dem ursprünglichen Server weitergeleitet, da das Microsoft 365-Postfach lokal ist.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-163">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="ed7c3-164">Testen Sie E-Mail an einen Benutzer auf dem vorhandenen E-Mail-System, indem Sie eine E-Mail z. B. an Benutzer C senden. Die E-Mail wird an das Postfach für Benutzer C auf Ihrem ursprünglichen E-Mail-Server übermittelt.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-164">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="ed7c3-165">Überprüfen Sie, ob die Weiterleitung von einem externen Konto oder von einem E-Mail-Konto eines Mitarbeiters auf dem vorhandenen E-Mail-System ordnungsgemäß eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-165">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="ed7c3-166">Senden Sie beispielsweise vom ursprünglichen Serverkonto für Benutzer C oder einem Hotmail-Konto eine E-Mail an Benutzer A, und überprüfen Sie, ob sie im Microsoft 365-Postfach für Benutzer A eingetroffen ist.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-166">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-9-move-mailbox-contents"></a><span data-ttu-id="ed7c3-167">Schritt 9: Verschieben von Postfachinhalten</span><span class="sxs-lookup"><span data-stu-id="ed7c3-167">Step 9: Move mailbox contents</span></span>

<span data-ttu-id="ed7c3-168">Da Sie nur zwei Testbenutzer verschieben und Benutzer A und Benutzer B beide Outlook verwenden, können Sie die E-Mail verschieben, indem Sie die alte .PST-Datei im neuen Outlook-Profil öffnen und die Nachrichten, Kalenderelemente, Kontakte usw. kopieren.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-168">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="ed7c3-169">Weitere Informationen hierzu finden Sie unter [Importieren von E-Mails, Kontakten und Kalendern aus einer Outlook-PST-Datei](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span><span class="sxs-lookup"><span data-stu-id="ed7c3-169">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="ed7c3-170">Nachdem sie in die entsprechenden Speicherorte im Microsoft 365-Postfach importiert wurden, kann auf die Elemente von jedem beliebigen Gerät aus zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-170">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>

<span data-ttu-id="ed7c3-171">Wenn mehr Postfächer beteiligt sind oder wenn Mitarbeiter Outlook nicht verwenden, können Sie die Migrationstools verwenden, die im Exchange Admin Center zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="ed7c3-171">When more mailboxes are involved, or if employees are not using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="ed7c3-172">Um zu beginnen, wechseln Sie zum Exchange Admin Center, und folgen Sie den Anweisungen unter [Migrieren von E-Mails von einem IMAP-Server zu Exchange Online-Postfächern – wir benötigen eine neue Artikel-Ressource].</span><span class="sxs-lookup"><span data-stu-id="ed7c3-172">To get started, go to Exchange admin center, and follow the directions in [Migrate Email from an IMAP Server to Exchange Online Mailboxes – we need a new article resource].</span></span>