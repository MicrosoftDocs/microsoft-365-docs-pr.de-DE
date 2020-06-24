---
title: Einrichten von Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Erfahren Sie, wie Sie Ihr Microsoft 365 Business Standard-Abonnement einrichten.
ms.openlocfilehash: b42dd0779c708410614ea2ab0d134aa3dcf0c7e9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44778925"
---
# <a name="set-up-microsoft-business-standard"></a><span data-ttu-id="62c74-103">Einrichten von Microsoft Business Standard</span><span class="sxs-lookup"><span data-stu-id="62c74-103">Set up Microsoft Business Standard</span></span>
  
 <span data-ttu-id="62c74-104">*Diese Schritte gelten für Unternehmen und [gemeinnützige Einrichtungen](https://go.microsoft.com/fwlink/p/?LinkId=627221), die über den **[Microsoft 365 Business Standard-Plan verfügen.](https://go.microsoft.com/fwlink/p/?LinkId=627220)***</span><span class="sxs-lookup"><span data-stu-id="62c74-104">*These steps are for businesses and [nonprofits](https://go.microsoft.com/fwlink/p/?LinkId=627221) that have the **[Microsoft 365 Business Standard plan.](https://go.microsoft.com/fwlink/p/?LinkId=627220)***</span></span>

<span data-ttu-id="62c74-105">Sehen Sie sich ein kurzes Video zum Einrichten von Microsoft 365 Business Standard (vormals Office 365 Business Premium) an.</span><span class="sxs-lookup"><span data-stu-id="62c74-105">Watch a short video about setting up Microsoft 365 Business Standard (formerly known as Office 365 Business Premium).</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/913be1ad-bae1-40c0-9ded-15bb477b828b]

<span data-ttu-id="62c74-106">Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816), an.</span><span class="sxs-lookup"><span data-stu-id="62c74-106">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="62c74-107">Hinzufügen Ihrer Domäne zum Personalisieren der Anmeldung</span><span class="sxs-lookup"><span data-stu-id="62c74-107">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="62c74-108">Wenn Sie Microsoft 365 Business Standard erwerben, haben Sie die Möglichkeit, eine Domäne zu verwenden, die Sie besitzen, oder während der Registrierung eine zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="62c74-108">When you purchase Microsoft 365 Business Standard, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="62c74-109">Wenn Sie bei der Registrierung eine neue Domäne erworben haben, ist Ihre Domäne eingerichtet, und Sie können zu [Benutzer hinzufügen und Lizenzen zuweisen](#add-users-and-assign-licenses) wechseln.</span><span class="sxs-lookup"><span data-stu-id="62c74-109">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

1. <span data-ttu-id="62c74-110">Melden Sie sich mit den Anmeldeinformationen des globalen Administrators bei [Microsoft 365 Admin Center](https://admin.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="62c74-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="62c74-111">Wählen Sie **Zu Setup wechseln** aus, um den Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="62c74-111">Choose **Go to setup** to start the wizard.</span></span>

3. <span data-ttu-id="62c74-112">Auf der Seite **Office-Anwendungen installieren** können Sie die Apps optional auf Ihrem eigenen Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="62c74-112">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="62c74-113">Geben Sie im Schritt **Domäne hinzufügen** den gewünschten Domänennamen ein (z. B. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="62c74-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="62c74-114">Wenn Sie während der Registrierung eine Domäne erworben haben, wird der Schritt **eine Domäne hinzufügen** nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="62c74-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="62c74-115">Wechseln Sie stattdessen zu [Benutzer hinzufügen](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="62c74-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="62c74-116">Führen Sie die Schritte im Assistenten aus, um [DNS-Einträge bei einem beliebigen DNS-Hostinganbieter für Office 365 zu erstellen](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), der verifiziert, dass Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="62c74-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="62c74-117">Wenn Sie Ihren Domänenhost kennen, lesen Sie auch die [hostspezifischen Anweisungen](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="62c74-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="62c74-118">Wenn es sich bei Ihrem Hostinganbieter um GoDaddy oder einen anderen Host handelt, der mit [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) arbeitet, ist der Vorgang einfach, und Sie werden aufgefordert, sich anzumelden, um Microsoft in Ihrem Auftrag authentifizieren zu lassen.</span><span class="sxs-lookup"><span data-stu-id="62c74-118">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Wählen Sie auf der GoDaddy-Seite „Zugriff bestätigen“ den Befehl Autorisieren aus.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="62c74-120">Benutzer hinzufügen und Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="62c74-120">Add users and assign licenses</span></span>

<span data-ttu-id="62c74-121">Sie können Benutzer entweder hier hinzufügen oder Sie können [Benutzer später im Admin Center hinzufügen](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="62c74-121">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="62c74-122">Wenn Sie einen lokalen Domänencontroller besitzen, können Sie Benutzer zudem mit [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="62c74-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="62c74-123">Hinzufügen von Benutzern im Assistenten</span><span class="sxs-lookup"><span data-stu-id="62c74-123">Add users in the wizard</span></span>

<span data-ttu-id="62c74-124">Allen Benutzern, die Sie im Assistenten hinzufügen, wird automatisch eine Microsoft 365 Business Standard-Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="62c74-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Standard license.</span></span>

1. <span data-ttu-id="62c74-125">Wenn Ihr Microsoft 365 Business Standard-Abonnement bereits Benutzer enthält (z. B. bei vorheriger Verwendung von Azure AD Connect), erhalten Sie die Möglichkeit, diesen Benutzern jetzt Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="62c74-125">If your Microsoft 365 Business Standard subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="62c74-126">Setzen Sie den Vorgang fort, und fügen Sie ihnen Lizenzen hinzu.</span><span class="sxs-lookup"><span data-stu-id="62c74-126">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="62c74-127">Nachdem Sie die Benutzer hinzugefügrt haben, erhalten Sie außerdem die Möglichkeit, Anmeldeinformationen für die hinzugefügten neuen Benutzer freizugeben.</span><span class="sxs-lookup"><span data-stu-id="62c74-127">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="62c74-128">Sie können auswählen, ob diese Informationen ausgedruckt, per E-Mail gesendet oder heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="62c74-128">You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="62c74-129">Ihre Domäne verbinden</span><span class="sxs-lookup"><span data-stu-id="62c74-129">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="62c74-130">Wenn Sie sich für die Verwendung der .onmicrosoft-Domäne oder die Verwendung von Azure AD Connect zum Einrichten von Benutzern entschieden haben, wird dieser Schritt nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="62c74-130">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="62c74-131">Zum Einrichten von Diensten müssen Sie einige Einträge bei Ihrem DNS-Host oder Ihrer Domänenregistrierungsstelle aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="62c74-131">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="62c74-132">In der Regel erkennt der Setup-Assistent Ihre Registrierungsstelle und zeigt einen Link an, über den Sie schrittweise Anleitungen zum Aktualisieren Ihrer NS-Einträge auf der Website der Registrierungsstelle aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="62c74-132">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="62c74-133">falls nicht, [Ändern Sie Nameserver zum Einrichten von Office 365 bei einer beliebigen Domänenregistrierungsstelle](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span><span class="sxs-lookup"><span data-stu-id="62c74-133">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="62c74-134">Wenn Sie über vorhandene DNS-Einträge verfügen, z. B. eine vorhandene Website, aber Ihr DNS-Host für [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) aktiviert ist, wählen Sie **Einträge für mich hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="62c74-134">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="62c74-135">Übernehmen Sie auf der Seite **Wählen Sie Ihre Onlinedienste** die Standardeinstellungen, wählen Sie **Weiter** aus, und wählen Sie auf der Seite Ihres DNS-Hosts **autorisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="62c74-135">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="62c74-136">Wenn Sie über vorhandene DNS-Einträge für andere DNS-Hosts (die nicht mit Domain Connect arbeiten) verfügen, können Sie Ihre eigenen DNS-Einträge verwalten, um sicherzustellen, dass die vorhandenen Dienste verbunden bleiben.</span><span class="sxs-lookup"><span data-stu-id="62c74-136">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="62c74-137">Weitere Informationen finden Sie unter [Domain-Grundlagen](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="62c74-137">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="62c74-138">Befolgen Sie die Schritte im Assistenten, damit E-Mail und andere Dienste für Sie eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="62c74-138">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="62c74-139">Wenn der Registrierungsvorgang abgeschlossen ist, werden Sie zum Admin Center weitergeleitet, wo Sie einem Assistenten folgen, um Office-Apps zu installieren, Ihre Domäne hinzuzufügen, Benutzer hinzuzufügen und Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="62c74-139">When the signup process is complete, you'll be directed to the admin center, where you'll follow a wizard to install Office apps, add your domain, add users, and assign licenses.</span></span> <span data-ttu-id="62c74-140">Nach Abschluss der Ersteinrichtung können Sie die Seite **Setup** im Admin Center verwenden, um mit der Einrichtung und Konfiguration der Dienste fortzufahren, die in Ihren Abonnements enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="62c74-140">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="62c74-141">Weitere Informationen über den Installationsassistenten und die Seite **Setup** im Admin Center finden Sie unter [Unterschied zwischen dem Installationsassistenten und der Seite "Setup"](o365-setup-wizard-and-setup-page.md).</span><span class="sxs-lookup"><span data-stu-id="62c74-141">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

## <a name="finish-setting-up"></a><span data-ttu-id="62c74-142">Abschließen der Einrichtung</span><span class="sxs-lookup"><span data-stu-id="62c74-142">Finish setting up</span></span>

### <a name="set-up-outlook-for-email"></a><span data-ttu-id="62c74-143">Einrichten von Outlook für E-Mail</span><span class="sxs-lookup"><span data-stu-id="62c74-143">Set up Outlook for email</span></span>

1. <span data-ttu-id="62c74-144">Suchen Sie im Windows-Startmenü nach Outlook, und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="62c74-144">On the Windows Start menu, search for Outlook, and select it.</span></span>

    <span data-ttu-id="62c74-145">(Wenn Sie einen Mac verwenden, öffnen Sie Outlook über die Symbolleiste, oder suchen Sie es mit dem Finder.)</span><span class="sxs-lookup"><span data-stu-id="62c74-145">(If you're using a Mac, open Outlook from the toolbar or locate it using the Finder.)</span></span>

    <span data-ttu-id="62c74-146">Wenn Sie nur Outlook installiert haben, wählen Sie auf der Willkommensseite **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="62c74-146">If you've just installed Outlook, on the Welcome page, select **Next**.</span></span>

2. <span data-ttu-id="62c74-147">Wählen Sie **Datei** \> **Info** \> **Konto hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="62c74-147">Choose **File** \> **Info** \> **Add Account**.</span></span>

3. <span data-ttu-id="62c74-148">Geben Sie Ihre Microsoft E-Mail-Adresse ein, und wählen Sie **Verbinden** aus.</span><span class="sxs-lookup"><span data-stu-id="62c74-148">Enter your Microsoft email address and select **Connect**.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
<span data-ttu-id="62c74-149">Mehr dazu unter [Einrichten von Outlook für E-Mail](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span><span class="sxs-lookup"><span data-stu-id="62c74-149">More at [Set up Outlook for email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span></span>
  
### <a name="import-email"></a><span data-ttu-id="62c74-150">Importieren von E-Mails</span><span class="sxs-lookup"><span data-stu-id="62c74-150">Import email</span></span>

<span data-ttu-id="62c74-151">Wenn Sie Outlook mit einem anderen E-Mail-Konto verwendet haben, können Sie Ihre früheren E-Mails, Kalender und Kontakte in Ihr neues Microsoft-Konto importieren.</span><span class="sxs-lookup"><span data-stu-id="62c74-151">If you were using Outlook with another email account, you can import your previous email, calendar, and contacts into your new Microsoft account.</span></span>
  
1. <span data-ttu-id="62c74-152">**Exportieren Ihrer alten E-Mails**</span><span class="sxs-lookup"><span data-stu-id="62c74-152">**Export your old email**</span></span>

    <span data-ttu-id="62c74-153">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span><span class="sxs-lookup"><span data-stu-id="62c74-153">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="62c74-154">Wählen Sie **Exportieren in eine Datei** und folgen Sie dann den Schritten zum Exportieren Ihrer Outlook-Datendatei (.pst) und aller Unterordner.</span><span class="sxs-lookup"><span data-stu-id="62c74-154">Select **Export to a File** and then follow the steps to export your Outlook Data File (.pst) and any subfolders.</span></span>

2. <span data-ttu-id="62c74-155">**Importieren Ihrer alten E-Mails**</span><span class="sxs-lookup"><span data-stu-id="62c74-155">**Import your old email**</span></span>

    <span data-ttu-id="62c74-156">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span><span class="sxs-lookup"><span data-stu-id="62c74-156">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span></span>

    <span data-ttu-id="62c74-157">Dieses Mal wählen Sie **Aus anderen Programmen oder Dateien importieren** aus, und befolgen die Schritte zum Importieren der Sicherungsdatei, die Sie erstellt haben, als Sie Ihre alten E-Mails exportiert haben.</span><span class="sxs-lookup"><span data-stu-id="62c74-157">This time, select **Import from another program or file** and follow the steps to import the backup file you created when you exported your old email.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
<span data-ttu-id="62c74-158">Mehr dazu unter [Importieren von E-Mails mit Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span><span class="sxs-lookup"><span data-stu-id="62c74-158">More at [Import email with Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span></span>

<span data-ttu-id="62c74-159">Sie können das Exchange Admin Center verwenden, um die E-Mails aller Benutzer zu importieren.</span><span class="sxs-lookup"><span data-stu-id="62c74-159">You can also use Exchange admin center to import everyone's email.</span></span> <span data-ttu-id="62c74-160">Weitere Informationen finden Sie unter [Migrieren mehrerer E-Mail-Konten](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="62c74-160">For more information, see [migrate multiple email accounts](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
### <a name="use-a-public-website"></a><span data-ttu-id="62c74-161">Verwenden einer öffentlichen Website</span><span class="sxs-lookup"><span data-stu-id="62c74-161">Use a public website</span></span>

<span data-ttu-id="62c74-162">Microsoft 365 doesn't include a public website for your business.</span><span class="sxs-lookup"><span data-stu-id="62c74-162">Microsoft 365 doesn't include a public website for your business.</span></span> <span data-ttu-id="62c74-163">If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span><span class="sxs-lookup"><span data-stu-id="62c74-163">If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span></span>
  
1. <span data-ttu-id="62c74-164">Wechseln Sie aus dem Admin Center zu **Ressourcen** und wählen Sie **Öffentliche Website** aus.</span><span class="sxs-lookup"><span data-stu-id="62c74-164">From the admin center, go to **Resources**, and then select **Public website**.</span></span>

2. <span data-ttu-id="62c74-165">Wählen Sie unter einer der Optionen **Weitere Informationen** aus. Registrieren Sie sich dann bei einem Websitepartner, und verwenden Sie dessen Tools zum Einrichten und Entwerfen Ihrer Website.</span><span class="sxs-lookup"><span data-stu-id="62c74-165">Select **Learn more** under one of the options, and then sign up with a website partner and use their tools to set up and design your site.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

<span data-ttu-id="62c74-166">Mehr dazu unter [Verwenden einer öffentlichen Website](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="62c74-166">More at [Use a public website](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>