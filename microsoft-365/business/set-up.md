---
title: Einrichten von Microsoft 365 Business
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Hier erfahren Sie, wie Sie Microsoft 365 Business einrichten.
ms.openlocfilehash: dbd2e740c85f52d3f43e6cd3d6ce45c478a9b1a9
ms.sourcegitcommit: 7690c8bfdea6e6d245cfa7c5b09b913b092cde0a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "37121316"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a><span data-ttu-id="76767-103">Einrichten von Microsoft 365 Business im Setup-Assistenten</span><span class="sxs-lookup"><span data-stu-id="76767-103">Set up Microsoft 365 Business in the setup wizard</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="76767-104">Hinzufügen von Richtlinien für Domäne, Benutzer und einrichten</span><span class="sxs-lookup"><span data-stu-id="76767-104">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="76767-105">[![Bezeichnungsfeld, damit Sie wissen, dass sich das Admin Center ändert, und weitere Informationen finden Sie unter aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="76767-105">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="76767-106">Wenn Sie Microsoft 365 Business erwerben, haben Sie die Möglichkeit, eine Domäne zu verwenden, die Sie besitzen, oder einen Kauf während der [Anmeldung](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="76767-106">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="76767-107">Wenn Sie bei der Registrierung eine neue Domäne erworben haben, ist Ihre Domäne eingerichtet, und Sie können zum [Hinzufügen von Benutzern und Zuweisen von Lizenzen](#add-users-and-assign-licenses)umsteigen.</span><span class="sxs-lookup"><span data-stu-id="76767-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="76767-108">Hinzufügen Ihrer Domäne zur Personalisierung der Anmeldung</span><span class="sxs-lookup"><span data-stu-id="76767-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="76767-109">Melden Sie sich mit ihren globalen Administratoranmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="76767-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="76767-110">Wählen Sie **Hinzufügen einer Domäne** oder **Hinzufügen von Benutzern** aus, um den Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="76767-110">Choose **Add a domain** or **Add users** to start the wizard.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="76767-111">Wenn Sie während der Registrierung eine Domäne erworben haben, wird hier kein Domänen Schritt **Hinzufügen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76767-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="76767-112">Wechseln Sie stattdessen zu [Benutzer hinzufügen](#add-users-and-assign-licenses) .</span><span class="sxs-lookup"><span data-stu-id="76767-112">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![Wählen Sie Domäne hinzufügen aus.](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="76767-114">Geben Sie im Assistenten den Domänennamen ein, den Sie verwenden möchten (wie contoso.com).</span><span class="sxs-lookup"><span data-stu-id="76767-114">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Screenshot der Personalisierung Ihrer Anmeldeseite.](media/personalizesignin.png)

    
4. <span data-ttu-id="76767-116">Befolgen Sie die Schritte im Assistenten zum [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) , die ihre eigene Domäne verifizieren.</span><span class="sxs-lookup"><span data-stu-id="76767-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="76767-117">Wenn Sie Ihren Domänenhost kennen, lesen Sie auch die [hostspezifischen Anweisungen](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="76767-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="76767-118">Wenn es sich bei Ihrem Hostinganbieter um einen GoDaddy oder einen anderen Host handelt, der mit der [Domäne Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)aktiviert ist, ist der Prozess einfach, und Sie werden automatisch aufgefordert, sich anzumelden und die Authentifizierung von Microsoft in Ihrem Namen zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="76767-118">If your hosting provider is GoDaddy, or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect),the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![Wählen Sie auf der Seite GoDaddy-Zugriff bestätigen die Option autorisieren aus.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="76767-120">Hinzufügen von Benutzern und Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="76767-120">Add users and assign licenses</span></span>

<span data-ttu-id="76767-121">Sie können Benutzer im Assistenten hinzufügen, Sie können aber auch später im Admin Center [Hinzufügen](add-users-m365b.md) .</span><span class="sxs-lookup"><span data-stu-id="76767-121">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="76767-122">Wenn Sie über einen lokalen Domänencontroller verfügen, können Sie außerdem Benutzer mit [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="76767-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="76767-123">Hinzufügen von Benutzern im Assistenten</span><span class="sxs-lookup"><span data-stu-id="76767-123">Add users in the wizard</span></span>

<span data-ttu-id="76767-124">Alle Benutzer, die Sie dem Assistenten hinzufügen, erhalten automatisch eine Microsoft 365 Business-Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="76767-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>

![Screenshot der Seite "neue Benutzer hinzufügen" im Assistenten](media/addnewuserspage.png)

1. <span data-ttu-id="76767-126">Wenn Ihr Microsoft 365 Business-Abonnement über vorhandene Benutzer verfügt (beispielsweise, wenn Sie Azure AD Connect verwendet haben), erhalten Sie eine Option, um Ihnen jetzt Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="76767-126">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you get an option to assign licenses to them now.</span></span> <span data-ttu-id="76767-127">Fügen Sie die Lizenzen ebenfalls hinzu.</span><span class="sxs-lookup"><span data-stu-id="76767-127">Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="76767-128">Nachdem Sie die Benutzer hinzugefügt haben, erhalten Sie auch eine Option zum Freigeben von Anmeldeinformationen für die neuen Benutzer, die Sie hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="76767-128">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="76767-129">Sie können auswählen, ob Sie Sie ausdrucken, per e-Mail versenden oder herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="76767-129">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="76767-130">Überspringen Sie die Migration von e-Mail-Nachrichten, und wählen Sie **weiter** auf Seite **e-Mails migrieren** .</span><span class="sxs-lookup"><span data-stu-id="76767-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="76767-131">Wenn Sie von einem anderen e-Mail-Anbieter wechseln und Ihre Daten später kopieren möchten, können Sie [e-Mails und Kontakte in Office 365 migrieren](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="76767-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>


### <a name="connect-your-domain"></a><span data-ttu-id="76767-132">Verbinden Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="76767-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="76767-133">Wenn Sie sich für die Verwendung der. onmicrosoft-Domäne entschieden oder Azure AD Connect zum Einrichten von Benutzern verwendet haben, wird dieser Schritt nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76767-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="76767-134">Zum Einrichten von Diensten müssen Sie einige Datensätze bei Ihrem DNS-Host oder Ihrer Domänenregistrierungsstelle aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="76767-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="76767-135">Der Setup-Assistent erkennt normalerweise Ihre Registrierungsstelle und stellt einen Link zu Schritt-für-Schritt-Anweisungen zum Aktualisieren der NS-Einträge auf der Registrierungsstellen Website bereit.</span><span class="sxs-lookup"><span data-stu-id="76767-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="76767-136">Wenn dies nicht der Fall ist, ändern Sie Namen [Server, um Office 365 bei einer beliebigen Domänenregistrierungsstelle einzurichten](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="76767-136">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="76767-137">Wenn Sie über vorhandene DNS-Einträge verfügen, beispielsweise eine vorhandene Website, Ihr DNS-Host jedoch für die [Domäne Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)aktiviert ist, wählen Sie **für mich Datensätze hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="76767-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> 
    - <span data-ttu-id="76767-138">Wenn Sie über vorhandene DNS-Einträge mit anderen DNS-Hosts verfügen (nicht für Domäne Connect aktiviert), sollten Sie Ihre eigenen DNS-Einträge verwalten, um sicherzustellen, dass die vorhandenen Dienste verbunden bleiben.</span><span class="sxs-lookup"><span data-stu-id="76767-138">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="76767-139">Weitere Informationen finden Sie unter [Domain Basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .</span><span class="sxs-lookup"><span data-stu-id="76767-139">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Verbinden Sie Ihre Domänen Seite mit ich werde meine eigenen DNS-Einträge verwalten.](media/connectyourdomainpage.png)

2. <span data-ttu-id="76767-141">Führen Sie die Schritte im Assistenten aus, und e-Mail und andere Dienste werden für Sie eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="76767-141">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="76767-142">Einrichten von Sicherheitsrichtlinien und Gerätekonfigurationen</span><span class="sxs-lookup"><span data-stu-id="76767-142">Set up security policies and device configurations</span></span> 

<span data-ttu-id="76767-143">Die Richtlinien, die Sie im Assistenten eingerichtet haben, werden automatisch auf eine [Sicherheitsgruppe](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) mit dem Namen " *alle Benutzer*" angewendet.</span><span class="sxs-lookup"><span data-stu-id="76767-143">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="76767-144">Sie können auch weitere Gruppen zum Zuweisen von Richtlinien im Admin Center erstellen.</span><span class="sxs-lookup"><span data-stu-id="76767-144">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="76767-145">Wählen Sie auf der Seite zum **Schützen Ihrer Arbeitsdateien auf mobilen Geräten** standardmäßig die Option **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden** .</span><span class="sxs-lookup"><span data-stu-id="76767-145">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="76767-146">Sie haben die Möglichkeit, die **Verwaltung der Benutzerzugriffe auf Office-Dateien auf mobilen Geräten**zu aktivieren, und dies wird empfohlen.</span><span class="sxs-lookup"><span data-stu-id="76767-146">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Screenshot der Seite Arbeitsdateien auf mobilen Geräten schützen.](media/protectworkfilesondevices.png)

     - <span data-ttu-id="76767-148">Erweitern Sie **Protect work Files, wenn Geräte verloren gehen oder gestohlen werden** , um die [Standardwerte](protect-work-files-on-lost-or-stolen-device.md)anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="76767-148">Expand **Protect work files when devices are lost or stolen** to display the [default values](protect-work-files-on-lost-or-stolen-device.md):</span></span>

        ![Screenshot der Standardwerte zum Schützen von Dateien auf verlorenen Geräten.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="76767-150">Wählen Sie **verwalten, wie Benutzer auf Office-Dateien auf mobilen Geräten zugreifen** , und erweitern Sie diese, um die [Standardwerte](manage-user-access-on-mobile-devices.md)anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="76767-150">Select **Manage how users access Office files on mobile devices** and expand it to display the [default values](manage-user-access-on-mobile-devices.md).</span></span> <span data-ttu-id="76767-151">Es wird empfohlen, während des Setups die Standardwerte zu übernehmen, um Anwendungsrichtlinien für Android, IOS und Windows 10 zu erstellen, die für alle Benutzer gelten.</span><span class="sxs-lookup"><span data-stu-id="76767-151">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="76767-152">Nach Abschluss des Setups können Sie weitere Richtlinien erstellen.</span><span class="sxs-lookup"><span data-stu-id="76767-152">You can create more policies after setup completes.</span></span>

        ![Screenshot der Schutzeinstellungen für Office-Dateien auf mobilen Geräten](media/useraccessonmobile.png)

2. <span data-ttu-id="76767-154">Der letzte Schritt zum Schutz von Daten und Geräten ermöglicht Ihnen das Einrichten von Richtlinien für die Sicherung von Windows 10-Geräten.</span><span class="sxs-lookup"><span data-stu-id="76767-154">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="76767-155">Diese Einstellungen werden automatisch angewendet, wenn Windows 10 eines Benutzers eine Verbindung mit Ihrer Organisation herstellt.</span><span class="sxs-lookup"><span data-stu-id="76767-155">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="76767-156">Sie können **sichere Windows 10-Geräte** erweitern, um die [Standardwerte](secure-windows-10-devices.md)anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="76767-156">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="76767-157">Sie können auch festlegen, dass Office auf Windows 10-Geräten [automatisch installiert](install-office-on-windows-10-during-setup.md) wird.</span><span class="sxs-lookup"><span data-stu-id="76767-157">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Screenshot der Seite "Windows 10-Gerätekonfiguration festlegen".](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="76767-159">Bereitstellen von Office 365-Client-apps</span><span class="sxs-lookup"><span data-stu-id="76767-159">Deploy Office 365 client apps</span></span>

<span data-ttu-id="76767-160">Wenn Sie Office-Apps während der Einrichtung automatisch in installieren, werden die apps auf den Windows 10-Geräten installiert, sobald sich die Benutzer bei Azure AD von Ihren Windows-Geräten mit ihren Arbeits Anmeldeinformationen angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="76767-160">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="76767-161">Informationen zum Installieren von Office auf mobilen IOS-oder Android-Geräten finden Sie unter [Einrichten von mobilen Geräten für Microsoft 365 Business-Benutzer](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="76767-161">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="76767-162">Sie können Office auch einzeln installieren.</span><span class="sxs-lookup"><span data-stu-id="76767-162">You can also install Office individually.</span></span> <span data-ttu-id="76767-163">Anweisungen finden Sie unter [Installieren von Office auf einem PC oder Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) .</span><span class="sxs-lookup"><span data-stu-id="76767-163">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>
