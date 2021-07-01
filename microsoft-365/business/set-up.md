---
title: Einrichten von Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Entdecken Sie die Einrichtungsschritte für Microsoft 365 Business Premium, z. B. das Hinzufügen einer Domäne und von Benutzern, das Einrichten von Sicherheitsrichtlinien und vieles mehr.
ms.openlocfilehash: 74a98e915577cf86ec32a706bd3b8f558f49db95
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227637"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="34293-103">Einrichten Microsoft 365 Business Premium im Setup-Assistenten</span><span class="sxs-lookup"><span data-stu-id="34293-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

## <a name="watch-overview-of-microsoft-365-setup"></a><span data-ttu-id="34293-104">Überwachung: Übersicht über Microsoft 365 Setup</span><span class="sxs-lookup"><span data-stu-id="34293-104">Watch: Overview of Microsoft 365 setup</span></span>

<span data-ttu-id="34293-105">Sehen Sie sich dieses Video an, um einen Überblick über Microsoft 365 Business Premium Setup zu geben.</span><span class="sxs-lookup"><span data-stu-id="34293-105">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="34293-106">Hinzufügen Ihrer Domäne, Benutzer und Einrichten von Richtlinien</span><span class="sxs-lookup"><span data-stu-id="34293-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="34293-107">Wenn Sie Microsoft 365 Business Premium erwerben, haben Sie die Möglichkeit, eine Domäne zu verwenden, die Sie besitzen, oder während der [Registrierung](sign-up.md)eine zu kaufen.</span><span class="sxs-lookup"><span data-stu-id="34293-107">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="34293-108">Wenn Sie bei der Registrierung eine neue Domäne erworben haben, ist Ihre Domäne eingerichtet, und Sie können zu [Benutzer hinzufügen und Lizenzen zuweisen](#add-users-and-assign-licenses) wechseln.</span><span class="sxs-lookup"><span data-stu-id="34293-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="34293-109">Hinzufügen Ihrer Domäne zum Personalisieren der Anmeldung</span><span class="sxs-lookup"><span data-stu-id="34293-109">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="34293-110">Melden Sie sich mit den Anmeldeinformationen des globalen Administrators bei [Microsoft 365 Admin Center](https://admin.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="34293-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="34293-111">Wählen Sie **Zu Setup wechseln** aus, um den Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="34293-111">Choose **Go to setup** to start the wizard.</span></span>

    ![Wählen Sie "Zum Setup wechseln" aus.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="34293-113">Auf der Seite **Office-Anwendungen installieren** können Sie die Apps optional auf Ihrem eigenen Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="34293-113">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="34293-114">Geben Sie im Schritt **Domäne hinzufügen** den gewünschten Domänennamen ein (z. B. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="34293-114">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="34293-115">Wenn Sie während der Registrierung eine Domäne erworben haben, wird der Schritt **eine Domäne hinzufügen** nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="34293-115">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="34293-116">Wechseln Sie stattdessen zu [Benutzer hinzufügen](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="34293-116">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Screenshot der Anmeldeseite "Personalisieren".](../media/adddomain.png)

    
4. <span data-ttu-id="34293-118">Führen Sie die Schritte im Assistenten aus, um [DNS-Einträge bei einem beliebigen DNS-Hostinganbieter für Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) zu erstellen, die Ihre Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="34293-118">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="34293-119">Wenn Sie Ihren Domänenhost kennen, finden Sie unter ["Hinzufügen einer Domäne zu Microsoft 365"](/microsoft-365/admin/setup/add-domain)weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="34293-119">If you know your domain host, see also [Add a domain to Microsoft 365](/microsoft-365/admin/setup/add-domain).</span></span>

    <span data-ttu-id="34293-120">Wenn es sich bei Ihrem Hostinganbieter um GoDaddy oder einen anderen Host handelt, der mit [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) arbeitet, ist der Vorgang einfach, und Sie werden aufgefordert, sich anzumelden, um Microsoft in Ihrem Auftrag authentifizieren zu lassen.</span><span class="sxs-lookup"><span data-stu-id="34293-120">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Wählen Sie auf der GoDaddy-Seite „Zugriff bestätigen“ den Befehl Autorisieren aus.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="34293-122">Benutzer hinzufügen und Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="34293-122">Add users and assign licenses</span></span>

<span data-ttu-id="34293-123">Sie können Benutzer entweder hier hinzufügen oder Sie können [Benutzer später im Admin Center hinzufügen](../admin/add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="34293-123">You can add users in the wizard, but you can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="34293-124">Wenn Sie einen lokalen Domänencontroller besitzen, können Sie Benutzer zudem mit [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="34293-124">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="34293-125">Hinzufügen von Benutzern im Assistenten</span><span class="sxs-lookup"><span data-stu-id="34293-125">Add users in the wizard</span></span>

<span data-ttu-id="34293-126">Allen Benutzern, die Sie im Assistenten hinzufügen, wird automatisch eine Microsoft 365 Business Premium-Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="34293-126">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Screenshot der Seite "Neue Benutzer hinzufügen" im Assistenten](../media/addnewuserspage.png)

1. <span data-ttu-id="34293-128">Wenn Ihr Microsoft 365 Business Premium Abonnement über vorhandene Benutzer verfügt (z. B. wenn Sie Azure AD Verbinden verwendet haben), erhalten Sie die Möglichkeit, ihnen jetzt Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="34293-128">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="34293-129">Setzen Sie den Vorgang fort, und fügen Sie ihnen Lizenzen hinzu.</span><span class="sxs-lookup"><span data-stu-id="34293-129">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="34293-130">Nachdem Sie die Benutzer hinzugefügrt haben, erhalten Sie außerdem die Möglichkeit, Anmeldeinformationen für die hinzugefügten neuen Benutzer freizugeben.</span><span class="sxs-lookup"><span data-stu-id="34293-130">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="34293-131">Sie können auswählen, ob diese Informationen ausgedruckt, per E-Mail gesendet oder heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="34293-131">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="34293-132">Ihre Domäne verbinden</span><span class="sxs-lookup"><span data-stu-id="34293-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="34293-133">Wenn Sie sich für die Verwendung der .onmicrosoft-Domäne oder die Verwendung von Azure AD Connect zum Einrichten von Benutzern entschieden haben, wird dieser Schritt nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="34293-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="34293-134">Zum Einrichten von Diensten müssen Sie einige Einträge bei Ihrem DNS-Host oder Ihrer Domänenregistrierungsstelle aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="34293-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="34293-135">In der Regel erkennt der Setup-Assistent Ihre Registrierungsstelle und zeigt einen Link an, über den Sie schrittweise Anleitungen zum Aktualisieren Ihrer NS-Einträge auf der Website der Registrierungsstelle aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="34293-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="34293-136">Wenn dies nicht der Fall ist, [ändern Sie Namenserver so, dass sie Microsoft 365 mit einer beliebigen Domänenregistrierungsstelle einrichten.](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)</span><span class="sxs-lookup"><span data-stu-id="34293-136">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="34293-137">Wenn Sie über vorhandene DNS-Einträge verfügen, z. B. eine vorhandene Website, aber Ihr DNS-Host für [Domain Connect](/office365/admin/get-help-with-domains/domain-connect) aktiviert ist, wählen Sie **Einträge für mich hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="34293-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="34293-138">Übernehmen Sie auf der Seite **Wählen Sie Ihre Onlinedienste** die Standardeinstellungen, wählen Sie **Weiter** aus, und wählen Sie auf der Seite Ihres DNS-Hosts **autorisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="34293-138">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="34293-139">Wenn Sie über vorhandene DNS-Einträge für andere DNS-Hosts (die nicht mit Domain Connect arbeiten) verfügen, können Sie Ihre eigenen DNS-Einträge verwalten, um sicherzustellen, dass die vorhandenen Dienste verbunden bleiben.</span><span class="sxs-lookup"><span data-stu-id="34293-139">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="34293-140">Weitere Informationen finden Sie unter [Domain-Grundlagen](/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="34293-140">See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Datensatzseite aktivieren.](../media/activaterecords.png)

2. <span data-ttu-id="34293-142">Befolgen Sie die Schritte im Assistenten, damit E-Mail und andere Dienste für Sie eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="34293-142">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="34293-143">Schützen Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="34293-143">Protect your organization</span></span> 

<span data-ttu-id="34293-144">Die Richtlinien, die Sie im Assistenten eingerichtet haben, werden automatisch auf eine [Sicherheitsgruppe](/office365/admin/create-groups/compare-groups#security-groups) namens *"Alle Benutzer"* angewendet.</span><span class="sxs-lookup"><span data-stu-id="34293-144">The policies you set up in the wizard are applied automatically to a [Security group](/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="34293-145">Sie können auch zusätzliche Gruppen erstellen, um Richtlinien im Admin Center zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="34293-145">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="34293-146">Um den **Schutz vor erweiterten Cyberbedrohungen** zu erhöhen, wird empfohlen, dass Sie die Standardeinstellungen akzeptieren, damit [Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) Dateien und Links in Office-Apps scannen kann.</span><span class="sxs-lookup"><span data-stu-id="34293-146">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) scan files and links in Office apps.</span></span>

    ![Screenshot der Seite "Schutz erhöhen".](../media/increasetreatprotection.png)


2. <span data-ttu-id="34293-148">Akzeptieren Sie auf der Seite **"Lecks vertraulicher Daten verhindern"** die Standardeinstellungen, um Office 365 Verhinderung von Datenverlust (Data Loss Prevention, DLP) zu aktivieren, um vertrauliche Daten in Office Apps nachzuverfolgen und die versehentliche Freigabe dieser Daten außerhalb Ihrer Organisation zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="34293-148">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="34293-149">Lassen Sie auf der Seite **"Daten schützen" in Office für mobilgeräte die** Verwaltung mobiler Apps aktiviert, erweitern Sie die Einstellungen und überprüfen Sie sie, und wählen Sie dann **"Verwaltungsrichtlinie** für mobile Apps erstellen" aus.</span><span class="sxs-lookup"><span data-stu-id="34293-149">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Screenshot der Seite "Schützen von Daten in Office für mobile Geräte".](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="34293-151">Sichern von Windows 10-PCs</span><span class="sxs-lookup"><span data-stu-id="34293-151">Secure Windows 10 PCs</span></span>

<span data-ttu-id="34293-152">Wählen Sie im linken Navigationsbereich **Setup** aus, und wählen Sie dann unter **"Anmelden und Sicherheit"** die Option **"Sichern Ihrer Windows 10 Computer"** aus.</span><span class="sxs-lookup"><span data-stu-id="34293-152">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="34293-153">Wählen Sie **"Ansicht"** aus, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="34293-153">Choose **View** to get started.</span></span> <span data-ttu-id="34293-154">Vollständige Anweisungen finden Sie unter ["Sichern Ihrer Windows 10 Computer".](secure-win-10-pcs.md)</span><span class="sxs-lookup"><span data-stu-id="34293-154">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="34293-155">Bereitstellen Office 365 Client-Apps</span><span class="sxs-lookup"><span data-stu-id="34293-155">Deploy Office 365 client apps</span></span>

<span data-ttu-id="34293-156">Wenn Sie sich für die automatische Installation Office Apps während des Setups entschieden haben, werden die Apps auf den Windows 10 Geräten installiert, sobald sich die Benutzer über ihre Windows Geräte mit ihren Geschäftlichen Anmeldeinformationen bei Azure AD angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="34293-156">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="34293-157">Informationen zum Installieren von Office auf mobilen iOS- oder Android-Geräten finden Sie unter ["Einrichten mobiler Geräte für Microsoft 365 Business Premium Benutzer".](set-up-mobile-devices.md)</span><span class="sxs-lookup"><span data-stu-id="34293-157">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="34293-158">Sie können Office auch einzeln installieren.</span><span class="sxs-lookup"><span data-stu-id="34293-158">You can also install Office individually.</span></span> <span data-ttu-id="34293-159">Anweisungen finden Sie unter [installieren Office auf einem PC oder Mac.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="34293-159">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="related-content"></a><span data-ttu-id="34293-160">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="34293-160">Related content</span></span>

<span data-ttu-id="34293-161">[Microsoft 365 für Business-Schulungsvideos](../business-video/index.yml) (Linkseite)</span><span class="sxs-lookup"><span data-stu-id="34293-161">[Microsoft 365 for business training videos](../business-video/index.yml) (link page)</span></span>
