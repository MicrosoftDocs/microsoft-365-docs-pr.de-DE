---
title: Microsoft 365 Business Premium einrichten
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Ermitteln Sie die Installationsschritte für Microsoft 365 Business Premium, einschließlich Hinzufügen einer Domäne und Benutzer, Einrichten von Sicherheitsrichtlinien und vieles mehr.
ms.openlocfilehash: cfc8523fe88ebca6b8c03db0ad0f6caeba662923
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048037"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="16fa6-103">Einrichten von Microsoft 365 Business Premium im Setup-Assistenten</span><span class="sxs-lookup"><span data-stu-id="16fa6-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="16fa6-104">In diesem Video sehen Sie eine Übersicht über das Microsoft 365 Business Premium-Setup.</span><span class="sxs-lookup"><span data-stu-id="16fa6-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="16fa6-105">Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816), an.</span><span class="sxs-lookup"><span data-stu-id="16fa6-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="16fa6-106">Hinzufügen von Richtlinien für Domäne, Benutzer und einrichten</span><span class="sxs-lookup"><span data-stu-id="16fa6-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="16fa6-107">[![Hinweis, der Sie darüber informiert, dass sich das Admin Center ändert und Sie unter "aka.ms/aboutM365preview" weitere Details finden.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="16fa6-107">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="16fa6-108">Wenn Sie Microsoft 365 Business Premium erwerben, haben Sie die Möglichkeit, eine Domäne zu verwenden, die Sie besitzen oder die Sie während der [Anmeldung](sign-up.md)kaufen.</span><span class="sxs-lookup"><span data-stu-id="16fa6-108">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="16fa6-109">Wenn Sie bei der Registrierung eine neue Domäne erworben haben, ist Ihre Domäne eingerichtet, und Sie können zum [Hinzufügen von Benutzern und Zuweisen von Lizenzen](#add-users-and-assign-licenses)umsteigen.</span><span class="sxs-lookup"><span data-stu-id="16fa6-109">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="16fa6-110">Hinzufügen Ihrer Domäne zur Personalisierung der Anmeldung</span><span class="sxs-lookup"><span data-stu-id="16fa6-110">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="16fa6-111">Melden Sie sich mit ihren globalen Administratoranmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="16fa6-111">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="16fa6-112">Wählen Sie **Gehe zu Setup** aus, um den Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="16fa6-112">Choose **Go to setup** to start the wizard.</span></span>

    ![Wählen Sie Gehe zu Setup aus.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="16fa6-114">Auf der Seite **Office-Apps installieren** können Sie optional die apps auf Ihrem eigenen Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="16fa6-114">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="16fa6-115">Geben Sie im Schritt **Domäne hinzufügen** den Domänennamen ein, den Sie verwenden möchten (wie contoso.com).</span><span class="sxs-lookup"><span data-stu-id="16fa6-115">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="16fa6-116">Wenn Sie während der Registrierung eine Domäne erworben haben, wird hier kein Domänen Schritt **Hinzufügen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="16fa6-116">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="16fa6-117">Wechseln Sie stattdessen zu [Benutzer hinzufügen](#add-users-and-assign-licenses) .</span><span class="sxs-lookup"><span data-stu-id="16fa6-117">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Screenshot der Personalisierung Ihrer Anmeldeseite.](../media/adddomain.png)

    
4. <span data-ttu-id="16fa6-119">Befolgen Sie die Schritte im Assistenten zum [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) , die ihre eigene Domäne verifizieren.</span><span class="sxs-lookup"><span data-stu-id="16fa6-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="16fa6-120">Wenn Sie Ihren Domänenhost kennen, lesen Sie auch die [hostspezifischen Anweisungen](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="16fa6-120">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="16fa6-121">Wenn Ihr Hosting-Anbieter GoDaddy oder ein anderer Host ist, der mit der [Domäne Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)aktiviert ist, ist der Prozess einfach, und Sie werden automatisch aufgefordert, sich anzumelden und Microsoft in Ihrem Namen authentifizieren zu lassen.</span><span class="sxs-lookup"><span data-stu-id="16fa6-121">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Wählen Sie auf der Seite GoDaddy-Zugriff bestätigen die Option autorisieren aus.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="16fa6-123">Hinzufügen von Benutzern und Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="16fa6-123">Add users and assign licenses</span></span>

<span data-ttu-id="16fa6-124">Sie können Benutzer im Assistenten hinzufügen, Sie können aber auch später im Admin Center [Hinzufügen](add-users-m365b.md) .</span><span class="sxs-lookup"><span data-stu-id="16fa6-124">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="16fa6-125">Wenn Sie über einen lokalen Domänencontroller verfügen, können Sie außerdem Benutzer mit [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="16fa6-125">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="16fa6-126">Hinzufügen von Benutzern im Assistenten</span><span class="sxs-lookup"><span data-stu-id="16fa6-126">Add users in the wizard</span></span>

<span data-ttu-id="16fa6-127">Alle Benutzer, die Sie dem Assistenten hinzufügen, erhalten automatisch eine Microsoft 365 Business Premium-Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="16fa6-127">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Screenshot der Seite "neue Benutzer hinzufügen" im Assistenten](../media/addnewuserspage.png)

1. <span data-ttu-id="16fa6-129">Wenn Ihr Microsoft 365 Business Premium-Abonnement über vorhandene Benutzer verfügt (beispielsweise wenn Sie Azure AD Connect verwendet haben), erhalten Sie eine Option, um Ihnen jetzt Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="16fa6-129">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="16fa6-130">Fügen Sie die Lizenzen ebenfalls hinzu.</span><span class="sxs-lookup"><span data-stu-id="16fa6-130">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="16fa6-131">Nachdem Sie die Benutzer hinzugefügt haben, erhalten Sie auch eine Option zum Freigeben von Anmeldeinformationen für die neuen Benutzer, die Sie hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="16fa6-131">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="16fa6-132">Sie können auswählen, ob Sie Sie ausdrucken, per e-Mail versenden oder herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="16fa6-132">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="16fa6-133">Verbinden Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="16fa6-133">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="16fa6-134">Wenn Sie sich für die Verwendung der. onmicrosoft-Domäne entschieden oder Azure AD Connect zum Einrichten von Benutzern verwendet haben, wird dieser Schritt nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="16fa6-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="16fa6-135">Zum Einrichten von Diensten müssen Sie einige Datensätze bei Ihrem DNS-Host oder Ihrer Domänenregistrierungsstelle aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="16fa6-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="16fa6-136">Der Setup-Assistent erkennt normalerweise Ihre Registrierungsstelle und stellt einen Link zu Schritt-für-Schritt-Anweisungen zum Aktualisieren der NS-Einträge auf der Registrierungsstellen Website bereit.</span><span class="sxs-lookup"><span data-stu-id="16fa6-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="16fa6-137">Wenn dies nicht der Fall ist, ändern Sie Namen [Server, um Office 365 bei einer beliebigen Domänenregistrierungsstelle einzurichten](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="16fa6-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="16fa6-138">Wenn Sie über vorhandene DNS-Einträge verfügen, beispielsweise eine vorhandene Website, Ihr DNS-Host jedoch für die [Domäne Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)aktiviert ist, wählen Sie **für mich Datensätze hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="16fa6-138">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="16fa6-139">Übernehmen Sie auf der Seite **Wählen Sie Ihre Onlinedienste aus** alle Standardeinstellungen, und wählen Sie **weiter**aus, und klicken Sie auf der Seite Ihres DNS-Hosts auf **autorisieren** .</span><span class="sxs-lookup"><span data-stu-id="16fa6-139">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="16fa6-140">Wenn Sie über vorhandene DNS-Einträge mit anderen DNS-Hosts verfügen (nicht für Domäne Connect aktiviert), sollten Sie Ihre eigenen DNS-Einträge verwalten, um sicherzustellen, dass die vorhandenen Dienste verbunden bleiben.</span><span class="sxs-lookup"><span data-stu-id="16fa6-140">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="16fa6-141">Weitere Informationen finden Sie unter [Domain Basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .</span><span class="sxs-lookup"><span data-stu-id="16fa6-141">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Seite Datensätze aktivieren.](../media/activaterecords.png)

2. <span data-ttu-id="16fa6-143">Führen Sie die Schritte im Assistenten aus, und e-Mail und andere Dienste werden für Sie eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="16fa6-143">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="16fa6-144">Schützen Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="16fa6-144">Protect your organization</span></span> 

<span data-ttu-id="16fa6-145">Die Richtlinien, die Sie im Assistenten eingerichtet haben, werden automatisch auf eine [Sicherheitsgruppe](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) mit dem Namen " *alle Benutzer*" angewendet.</span><span class="sxs-lookup"><span data-stu-id="16fa6-145">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="16fa6-146">Sie können auch weitere Gruppen zum Zuweisen von Richtlinien im Admin Center erstellen.</span><span class="sxs-lookup"><span data-stu-id="16fa6-146">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="16fa6-147">Um den **Schutz vor fortgeschrittenen Cyber-Bedrohungen zu verbessern**, wird empfohlen, dass Sie die Standardeinstellungen akzeptieren, damit [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) Scandateien und Links in Office-Apps.</span><span class="sxs-lookup"><span data-stu-id="16fa6-147">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![Screenshot der Seite zur Verstärkung des Schutzes.](../media/increasetreatprotection.png)


2. <span data-ttu-id="16fa6-149">Übernehmen Sie auf der Seite " **Lecks von vertraulichen Daten verhindern** " die Standardeinstellungen, um die Office 365 Verhinderung von Datenverlust (Data Loss Prevention, DLP) zum Nachverfolgen vertraulicher Daten in Office-Apps zu aktivieren und die unbeabsichtigte Freigabe dieser außerhalb Ihrer Organisation zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="16fa6-149">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="16fa6-150">Lassen Sie Mobile App Verwaltung auf der Seite **Daten in Office für Mobile schützen** auf, erweitern Sie die Einstellungen, und überprüfen Sie Sie, und wählen Sie dann **Mobile App Verwaltungsrichtlinie erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="16fa6-150">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Screenshot von Daten in Office für Mobile Seite schützen.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="16fa6-152">Sichere Windows 10-PCs</span><span class="sxs-lookup"><span data-stu-id="16fa6-152">Secure Windows 10 PCs</span></span>

<span data-ttu-id="16fa6-153">Wählen Sie im linken Navigationsbereich die Option **Setup** aus, und wählen Sie dann unter **Anmeldung und Sicherheit** **die Option Sichern Ihrer Windows 10-Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="16fa6-153">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="16fa6-154">Wählen Sie **Ansicht** für erste Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="16fa6-154">Choose **View** to get started.</span></span> <span data-ttu-id="16fa6-155">Ausführliche Anweisungen finden Sie unter [Sichern Ihrer Windows 10-Computer](secure-win-10-pcs.md) .</span><span class="sxs-lookup"><span data-stu-id="16fa6-155">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="16fa6-156">Bereitstellen von Office 365-Client-apps</span><span class="sxs-lookup"><span data-stu-id="16fa6-156">Deploy Office 365 client apps</span></span>

<span data-ttu-id="16fa6-157">Wenn Sie während des Setups die automatische Installation von Office-Apps ausgewählt haben, werden die apps auf den Windows 10-Geräten installiert, sobald sich die Benutzer bei Azure AD von Ihren Windows-Geräten unter Verwendung ihrer Arbeits Anmeldeinformationen angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="16fa6-157">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="16fa6-158">Informationen zum Installieren von Office auf mobilen IOS-oder Android-Geräten finden Sie unter [Einrichten von mobilen Geräten für Microsoft 365 Business Premium-Benutzer](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="16fa6-158">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="16fa6-159">Sie können Office auch einzeln installieren.</span><span class="sxs-lookup"><span data-stu-id="16fa6-159">You can also install Office individually.</span></span> <span data-ttu-id="16fa6-160">Anweisungen finden Sie unter [Installieren von Office auf einem PC oder Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) .</span><span class="sxs-lookup"><span data-stu-id="16fa6-160">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="16fa6-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16fa6-161">See also</span></span>

[<span data-ttu-id="16fa6-162">Microsoft 365 für Unternehmen-Schulungsvideos</span><span class="sxs-lookup"><span data-stu-id="16fa6-162">Microsoft 365 for business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
