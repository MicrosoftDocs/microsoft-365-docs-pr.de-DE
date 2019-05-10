---
title: Einrichten von Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
description: Erfahren Sie, wie Sie Microsoft 365 Business einrichten.
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660787"
---
# <a name="set-up-microsoft-365-business"></a><span data-ttu-id="62085-103">Einrichten von Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="62085-103">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="62085-104">Weitere Informationen finden Sie unter [Get Microsoft 365 Business](get-microsoft-365-business.md) for Sign-up Details.</span><span class="sxs-lookup"><span data-stu-id="62085-104">Before you get started, see [Get Microsoft 365 Business](get-microsoft-365-business.md) for sign-up details.</span></span>

<span data-ttu-id="62085-105">Sehen Sie sich ein [kurzes Video über das Einrichten von Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) mithilfe des Assistenten zum Einrichten und wenn Sie nicht über ein lokales Active Directory verfügen.</span><span class="sxs-lookup"><span data-stu-id="62085-105">Watch a [short video on how to set up Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) by using the set up wizard, and when you don't have an on-premises Active Directory</span></span>
  

## <a name="overview"></a><span data-ttu-id="62085-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="62085-106">Overview</span></span>

<span data-ttu-id="62085-107">Die meisten der einrichten-Schritte können im Setup-Assistenten ausgeführt werden, die anderen Optionen werden ebenfalls aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="62085-107">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>

1. <span data-ttu-id="62085-108">[Hinzufügen Ihrer Domäne](#add-your-domain-to-personalize-sign-in) (wenn Sie Ihre Domäne während der [Registrierung](sign-up.md)erworben haben, ist dieser Schritt bereits erfolgt.)</span><span class="sxs-lookup"><span data-stu-id="62085-108">[Add your domain](#add-your-domain-to-personalize-sign-in) (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>
2. <span data-ttu-id="62085-109">Fügen Sie Benutzer hinzu.</span><span class="sxs-lookup"><span data-stu-id="62085-109">Add users.</span></span> <span data-ttu-id="62085-110">Sie haben die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="62085-110">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="62085-111">Im [Setup-Assistenten](#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="62085-111">In the [setup wizard](#add-users-in-the-wizard).</span></span>
    - <span data-ttu-id="62085-112">Verwenden Sie die Verzeichnissynchronisierung, um [Benutzer mithilfe von Azure AD Connect hinzuzufügen](#add-users-by-using-azure-ad-connect) , wenn Sie über ein lokales Active Directory verfügen.</span><span class="sxs-lookup"><span data-stu-id="62085-112">Use directory synchronization to [add users by using Azure AD Connect](#add-users-by-using-azure-ad-connect) if you have an on-premises Active directory.</span></span>
    - <span data-ttu-id="62085-113">Sie können auch später im Admin Center [Benutzer hinzufügen](add-users-m365b.md) .</span><span class="sxs-lookup"><span data-stu-id="62085-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
3. <span data-ttu-id="62085-114">Einrichten von Sicherheitsrichtlinien und Konfigurieren von Geräten</span><span class="sxs-lookup"><span data-stu-id="62085-114">Set up security policies and configure devices.</span></span> <span data-ttu-id="62085-115">Sie haben die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="62085-115">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="62085-116">Im [Setup-Assistenten](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="62085-116">In the [setup wizard](#set-up-policies-in-the-wizard).</span></span>  
    - <span data-ttu-id="62085-117">Im [Admin Center](#modify-or-add-policies-in-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="62085-117">In the [admin center](#modify-or-add-policies-in-the-admin-center).</span></span>
    - <span data-ttu-id="62085-118">Im [InTune Admin Center](https://docs.microsoft.com/intune/what-is-device-management).</span><span class="sxs-lookup"><span data-stu-id="62085-118">In the [Intune admin center](https://docs.microsoft.com/intune/what-is-device-management).</span></span>
4. <span data-ttu-id="62085-119">Einrichten und Verwalten von Windows 10-Geräten.</span><span class="sxs-lookup"><span data-stu-id="62085-119">Set up and manage Windows 10 devices.</span></span>

    <span data-ttu-id="62085-120">Wenn Sie einem Windows 10-Gerät zu Azure AD beitreten, werden alle Richtlinien angewendet.</span><span class="sxs-lookup"><span data-stu-id="62085-120">When you join a WIndows 10 device to Azure AD, all the policies get applied to it.</span></span>
    - <span data-ttu-id="62085-121">Richten Sie Windows 10-Gerätekonfigurationen im [Setup-Assistenten](#set-up-policies-in-the-wizard)ein.</span><span class="sxs-lookup"><span data-stu-id="62085-121">Set up Windows 10 device configurations in the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="62085-122">Verbinden Sie ein [neues Windows 10-Gerät](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) mit Azure AD.</span><span class="sxs-lookup"><span data-stu-id="62085-122">Join a [new Windows 10 device](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) to Azure AD.</span></span>
    - <span data-ttu-id="62085-123">Verbinden Sie ein [vorhandenes Windows 10-Gerät](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) mit Azure AD.</span><span class="sxs-lookup"><span data-stu-id="62085-123">Join an [existing Windows 10 device](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) to Azure AD.</span></span>
1. <span data-ttu-id="62085-124">Installieren Sie Office 365 Business.</span><span class="sxs-lookup"><span data-stu-id="62085-124">Install Office 365 Business.</span></span>
    - <span data-ttu-id="62085-125">Sie können Office auf den Windows-Geräten mithilfe des Setup- [Assistenten](#set-up-policies-in-the-wizard)automatisch installieren.</span><span class="sxs-lookup"><span data-stu-id="62085-125">You can automatically install Office in the Windows devices by using the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="62085-126">[Installieren Sie Office](auto-install-or-uninstall-office.md) automatisch über das Admin Center.</span><span class="sxs-lookup"><span data-stu-id="62085-126">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
    - <span data-ttu-id="62085-127">Benutzer können [Office-Apps](https://docs.microsoft.com/office365/admin/setup/install-applications) für Windows und Geräte installieren.</span><span class="sxs-lookup"><span data-stu-id="62085-127">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
1. <span data-ttu-id="62085-128">Richten Sie zusätzliche Sicherheit ein.</span><span class="sxs-lookup"><span data-stu-id="62085-128">Set up additional security.</span></span>
    - <span data-ttu-id="62085-129">Der Setup-Assistent fügt Richtlinien hinzu, um Ihre Geräte zu schützen, aber Sie können auch [zusätzliche Sicherheits](#additional-security-settings) Funktionen nutzen, um Ihre Daten, Konten und e-Mails zu schützen.</span><span class="sxs-lookup"><span data-stu-id="62085-129">The setup wizard adds policies to secure your devices, but you can also take advantage of [additional security](#additional-security-settings) capabilities to helps secure your data, accounts, and emails.</span></span> 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="62085-130">Hinzufügen Ihrer Domäne, der Benutzer und Einrichten von Richtlinien</span><span class="sxs-lookup"><span data-stu-id="62085-130">Add your domain, users and set up policies</span></span>

![Banner, das auf https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

<span data-ttu-id="62085-132">Wenn Sie Microsoft 365 Business erwerben, haben Sie die Möglichkeit, eine Domäne zu verwenden, die Sie besitzen, oder einen während der [Registrierung](sign-up.md)zu kaufen.</span><span class="sxs-lookup"><span data-stu-id="62085-132">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="62085-133">Wenn Sie bei der Registrierung eine neue Domäne erworben haben, ist Ihre Domäne vollständig eingerichtet, und Sie können zum [Hinzufügen von Benutzern und zum Zuweisen von Lizenzen](#add-users-and-assign-licenses)wechseln.</span><span class="sxs-lookup"><span data-stu-id="62085-133">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="62085-134">Hinzufügen Ihrer Domäne zur Personalisierung der Anmeldung</span><span class="sxs-lookup"><span data-stu-id="62085-134">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="62085-135">Melden Sie sich mit ihren globalen Administratoranmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="62085-135">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="62085-136">Wählen Sie **Domäne hinzufügen** aus, um den Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="62085-136">Choose **Add a domain** to start the wizard.</span></span>

    ![Wählen Sie Domäne hinzufügen aus.](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="62085-138">Geben Sie im Assistenten den Domänennamen ein, den Sie verwenden möchten (wie contoso.com).</span><span class="sxs-lookup"><span data-stu-id="62085-138">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Screenshot der personalisieren Sie Ihre Anmeldeseite.](media/personalizesignin.png)

    
4. <span data-ttu-id="62085-140">Führen Sie die Schritte im Assistenten aus, um [DNS-Einträge bei einem beliebigen DNS-Hostinganbieter für Office 365 zu erstellen](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) , der überprüft, ob Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="62085-140">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="62085-141">Wenn Sie Ihren Domänenhost kennen, lesen Sie auch die [hostspezifischen Anweisungen](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="62085-141">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="62085-142">Wenn Ihr Hostinganbieter GoDaddy ist, ist der Vorgang einfach und Sie werden automatisch aufgefordert, sich anzumelden und Microsoft in Ihrem Namen zu authentifizieren:</span><span class="sxs-lookup"><span data-stu-id="62085-142">If your hosting provider is GoDaddy, the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![Wählen Sie auf GoDaddy Zugriffsseite bestätigen aus.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="62085-144">Hinzufügen von Benutzern und Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="62085-144">Add users and assign licenses</span></span>

<span data-ttu-id="62085-145">Sie können Benutzer im Assistenten hinzufügen, Sie können aber auch später im Admin Center [Benutzer hinzufügen](add-users-m365b.md) .</span><span class="sxs-lookup"><span data-stu-id="62085-145">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="62085-146">Darüber hinaus können Sie Benutzer mit [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)hinzufügen, wenn Sie über einen lokalen Domänencontroller verfügen.</span><span class="sxs-lookup"><span data-stu-id="62085-146">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="62085-147">Hinzufügen von Benutzern im Assistenten</span><span class="sxs-lookup"><span data-stu-id="62085-147">Add users in the wizard</span></span>

<span data-ttu-id="62085-148">Alle Benutzer, die Sie im Assistenten hinzufügen, erhalten automatisch eine Microsoft 365 Business-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="62085-148">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>
<span data-ttu-id="62085-149">Wenn Sie über einen lokalen Domänencontroller verfügen und Active Directory verwenden, erfahren Sie, [wie Sie DDD-Benutzer mithilfe von Azure AD Connect verwenden](#add-users-by-using-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="62085-149">If you have a local domain controller, and are using Active Directory, see [how to ddd users by using Azure AD Connect](#add-users-by-using-azure-ad-connect).</span></span>

![Screenshot der Seite "neue Benutzer hinzufügen" im Assistenten](media/addnewuserspage.png)

1. <span data-ttu-id="62085-151">Wenn Ihr Microsoft 365 Business-Abonnement über vorhandene Benutzer verfügt (beispielsweise, wenn Sie Azure AD Connect verwendet haben), erhalten Sie jetzt die Option, Ihnen Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="62085-151">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now.</span></span> <span data-ttu-id="62085-152">Gehen Sie vor, und fügen Sie Lizenzen hinzu.</span><span class="sxs-lookup"><span data-stu-id="62085-152">Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="62085-153">Nachdem Sie die Benutzer hinzugefügt haben, erhalten Sie auch die Möglichkeit, die Anmeldeinformationen für die neuen Benutzer freizugeben, die Sie hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="62085-153">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="62085-154">Sie können auswählen, ob Sie Sie ausdrucken, per e-Mail versenden oder herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="62085-154">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="62085-155">Überspringen Sie die Migration von e-Mail-Nachrichten, und wählen Sie **weiter** auf Seite **e-Mails migrieren** .</span><span class="sxs-lookup"><span data-stu-id="62085-155">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="62085-156">Wenn Sie von einem anderen e-Mail-Anbieter wechseln und Ihre Daten später kopieren möchten, können Sie [e-Mails und Kontakte zu Office 365 migrieren](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="62085-156">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>

#### <a name="add-users-by-using-azure-ad-connect"></a><span data-ttu-id="62085-157">Hinzufügen von Benutzern mithilfe von Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="62085-157">Add users by using Azure AD Connect</span></span>

 <span data-ttu-id="62085-158">Wenn Sie über einen lokalen Domänencontroller mit Active Directory verfügen, synchronisieren Sie Ihre Benutzer mit Microsoft 365 Business mithilfe von [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="62085-158">If you have a local domain controller with Active Directory, you synchronize your users with Microsoft 365 Business by using [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span> <span data-ttu-id="62085-159">Führen Sie diese Schritte aus, bevor Sie den Setup-Assistenten starten.</span><span class="sxs-lookup"><span data-stu-id="62085-159">Complete this before you start the setup wizard.</span></span> <span data-ttu-id="62085-160">Sie können es im Admin Center herunterladen:</span><span class="sxs-lookup"><span data-stu-id="62085-160">You can download it in the admin center:</span></span>

- <span data-ttu-id="62085-161">Wechseln Sie zu **Users** \> **Active Users**, wählen Sie die Ellipsen oben auf der Seite aus, und wählen Sie dann **Verzeichnissynchronisierung** zum Herunterladen von Azure AD Connect aus.</span><span class="sxs-lookup"><span data-stu-id="62085-161">Go to **Users** \> **Active users**, select the ellipses on the top of the page and then select **Directory synchronization** to download Azure AD Connect.</span></span>

    ![Wählen Sie auf der Seite aktive Benutzer Auslassungszeichen > Verzeichnis snchronization.](media/setupdirsync.png)

    > [!IMPORTANT]
    > <span data-ttu-id="62085-163">Wenn Sie Benutzer auf diese Weise erstellen, müssen Sie Ihnen im Admin Center weiterhin Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="62085-163">If you create users this way, you will still have to assign licenses to them in the admin center.</span></span>

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a><span data-ttu-id="62085-164">Weiterhin Zugriff auf Domänen verbundene apps und Geräte</span><span class="sxs-lookup"><span data-stu-id="62085-164">Continue to access domain-joined apps and devices</span></span>

<span data-ttu-id="62085-165">Wenn Sie weiterhin auf Domänen-Joined-apps und-Geräte zugreifen möchten, lesen Sie die folgenden Artikel, um Folgendes zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="62085-165">If you want to continue to access domain-joined apps and devices, read the following articles for two different way of enabling that:</span></span>
  
- [<span data-ttu-id="62085-166">Aktivieren von Domänenbeitritt zu Windows 10-Geräten, die von Microsoft 365 Business verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="62085-166">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    - <span data-ttu-id="62085-167">Dies ist die empfohlene Methode.</span><span class="sxs-lookup"><span data-stu-id="62085-167">This is the recommended way.</span></span>

- [<span data-ttu-id="62085-168">Zugreifen auf lokale Ressourcen über ein Azure AD-verbundenes Gerät in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="62085-168">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)

### <a name="connect-your-domain"></a><span data-ttu-id="62085-169">Verbinden Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="62085-169">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="62085-170">Wenn Sie die. onmicrosoft-Domäne verwenden oder Azure AD Connect zum Einrichten von Benutzern verwendet haben, wird dieser Schritt nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="62085-170">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="62085-171">Um Dienste einzurichten, müssen Sie einige Datensätze bei Ihrem DNS-Host oder Ihrer Domänenregistrierungsstelle aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="62085-171">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="62085-172">Der Setup-Assistent erkennt in der Regel Ihre Registrierungsstelle und gibt Ihnen einen Link zu Schritt-für-Schritt-Anweisungen zum Aktualisieren Ihrer NS-Einträge auf der Registrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="62085-172">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="62085-173">Wenn dies nicht der Fall ist, [Ändern Sie die Namenserver, um Office 365 für eine beliebige Domänenregistrierungsstelle](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)einzurichten.</span><span class="sxs-lookup"><span data-stu-id="62085-173">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="62085-174">Wenn Sie über vorhandene DNS-Einträge verfügen (beispielsweise eine vorhandene Website), sollten Sie Ihre eigenen DNS-Einträge verwalten, um sicherzustellen, dass die vorhandenen Dienste verbunden bleiben.</span><span class="sxs-lookup"><span data-stu-id="62085-174">If you have existing DNS records, for example an existing web site, you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="62085-175">Weitere Informationen finden Sie unter [Grundlagen der Domäne](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .</span><span class="sxs-lookup"><span data-stu-id="62085-175">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Verbinden Sie Ihre Domänen Seite mit ich werde meine eigenen DNS-Einträge verwalten.](media/connectyourdomainpage.png)

2. <span data-ttu-id="62085-177">Führen Sie die Schritte im Assistenten aus, und e-Mails und andere Dienste werden für Sie eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="62085-177">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="62085-178">Einrichten von Sicherheitsrichtlinien und Gerätekonfigurationen</span><span class="sxs-lookup"><span data-stu-id="62085-178">Set up security policies and device configurations</span></span> 

<span data-ttu-id="62085-179">Diese Richtlinien gelten für jeden Benutzer, dem Sie eine Lizenz erteilen, oder für eine Gruppe von Benutzern, wenn Sie eine Reihe von Benutzern unterschiedliche Richtlinien zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="62085-179">These policies apply to every user you give a license to, or to a group of users if you decide to assign different policies to a set of users.</span></span>

#### <a name="set-up-policies-in-the-wizard"></a><span data-ttu-id="62085-180">Einrichten von Richtlinien im Assistenten</span><span class="sxs-lookup"><span data-stu-id="62085-180">Set up policies in the wizard</span></span>

<span data-ttu-id="62085-181">Die Richtlinien, die Sie im Assistenten einrichten, werden automatisch auf eine [Sicherheitsgruppe](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) namens " *alle Benutzer*" angewendet.</span><span class="sxs-lookup"><span data-stu-id="62085-181">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span>

1. <span data-ttu-id="62085-182">Aktivieren Sie auf der Seite **schützen Sie Ihre Arbeitsdateien auf mobilen Geräten** standardmäßig die Option **Arbeitsdateien bei verlorenen oder gestohlenen Geräten schützen** .</span><span class="sxs-lookup"><span data-stu-id="62085-182">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="62085-183">Sie haben die Möglichkeit, zu **Steuern, wie Benutzer auf Office-Dateien auf mobilen Geräten zugreifen**, und dies wird empfohlen.</span><span class="sxs-lookup"><span data-stu-id="62085-183">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Screenshot der Seite zum Schutz von Arbeitsdateien auf mobilen Geräten.](media/protectworkfilesondevices.png)

     - <span data-ttu-id="62085-185">Wenn Sie **Arbeitsdateien schützen erweitern, wenn Geräte verloren gehen oder gestohlen**werden, sind die [Standardwerte](protect-work-files-on-lost-or-stolen-device.md) vorab ausgewählt:</span><span class="sxs-lookup"><span data-stu-id="62085-185">If you expand **Protect work files when devices are lost or stolen**, the [default values](protect-work-files-on-lost-or-stolen-device.md) are pre-selected:</span></span>

        ![Screenshot der Standardwerte für den Schutz von Dateien auf verlorenen Geräten.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="62085-187">Wenn Sie verwalten auswählen, **wie Benutzer auf mobilen Geräten auf Office-Dateien zugreifen** und diese erweitern, werden die [Standardwerte](manage-user-access-on-mobile-devices.md) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="62085-187">If you select **Manage how users access Office files on mobile devices** and expand it, the [default values](manage-user-access-on-mobile-devices.md) are shown.</span></span> <span data-ttu-id="62085-188">Wir empfehlen, während des Setups die Standardwerte zu übernehmen, um Anwendungsrichtlinien für Android, iOS und Windows 10 zu erstellen, die für alle Benutzer gelten.</span><span class="sxs-lookup"><span data-stu-id="62085-188">We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="62085-189">Nach Abschluss des Setups können Sie weitere Richtlinien erstellen.</span><span class="sxs-lookup"><span data-stu-id="62085-189">You can create more policies after setup completes.</span></span>

        ![Screenshot der Schutzeinstellungen für Office-Dateien auf mobilen Geräten.](media/useraccessonmobile.png)

2. <span data-ttu-id="62085-191">Im letzten Schritt zum Schutz von Daten und Geräten können Sie Richtlinien einrichten, um Windows 10-Geräte zu sichern.</span><span class="sxs-lookup"><span data-stu-id="62085-191">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="62085-192">Diese Einstellungen werden automatisch angewendet, wenn Windows 10 eines Benutzers eine Verbindung mit Ihrer Organisation herstellt.</span><span class="sxs-lookup"><span data-stu-id="62085-192">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="62085-193">Sie können **Secure Windows 10-Geräte** erweitern, um die [Standardwerte](secure-windows-10-devices.md)anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="62085-193">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="62085-194">Sie können Office auf Windows 10-Geräten auch [automatisch installieren](install-office-on-windows-10-during-setup.md) .</span><span class="sxs-lookup"><span data-stu-id="62085-194">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Screenshot der Seite Set Windows 10 Device Configuration.](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a><span data-ttu-id="62085-196">Ändern oder Hinzufügen von Richtlinien im Admin Center</span><span class="sxs-lookup"><span data-stu-id="62085-196">Modify or add policies in the admin center</span></span>

<span data-ttu-id="62085-197">Weitere Informationen finden Sie unter [Verwalten von Microsoft 365 Business](manage.md) für Links zu Themen zum Anzeigen und Ändern von Geräte-und App-Schutzrichtlinien sowie zum Entfernen von Daten aus oder Zurücksetzen von Benutzergeräten.</span><span class="sxs-lookup"><span data-stu-id="62085-197">See [manage Microsoft 365 Business](manage.md) for links to topics on how to view and modify device and app protection polices, and how to remove data from, or reset user devices.</span></span>

## <a name="deploy-and-manage-windows-10"></a><span data-ttu-id="62085-198">Bereitstellen und Verwalten von Windows 10</span><span class="sxs-lookup"><span data-stu-id="62085-198">Deploy and manage Windows 10</span></span>
<span data-ttu-id="62085-199">Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für Microsoft 365 Business-Benutzer](set-up-windows-devices.md) zur manuellen Verbindung mit Azure AD, entweder beim Setup für neue Computer oder durch Ändern des Anmelde Profils für vorhandene Computer.</span><span class="sxs-lookup"><span data-stu-id="62085-199">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) to manually connect to Azure AD, either during setup for new computers, or by changing sign-in profile for existing computers.</span></span> 

### <a name="use-autopilot-to-set-up-new-devices"></a><span data-ttu-id="62085-200">Verwenden von Autopilot zum Einrichten neuer Geräte</span><span class="sxs-lookup"><span data-stu-id="62085-200">Use Autopilot to set up new devices</span></span>

<span data-ttu-id="62085-201">Sie können [Windows Autopilot](add-autopilot-devices-and-profile.md) verwenden, um **neue** Windows 10-Geräte für einen Benutzer automatisch vorkonfigurieren, aber es ist möglicherweise einfacher, einen [Partner](https://www.microsoft.com/solution-providers/search) zu erhalten, der dies für Sie tun kann.</span><span class="sxs-lookup"><span data-stu-id="62085-201">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="62085-202">Sie können auch zu [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) wechseln und einen Experten für die Cloud-Technologie bitten, neue Geräte einzurichten, die Sie für Sie erwerben.</span><span class="sxs-lookup"><span data-stu-id="62085-202">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

### <a name="access-on-premises-resources"></a><span data-ttu-id="62085-203">Zugriff auf lokale Ressourcen</span><span class="sxs-lookup"><span data-stu-id="62085-203">Access on-premises resources</span></span>

<span data-ttu-id="62085-204">Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business einrichten, um Ihre Windows 10-Geräte zu schützen, ohne dabei den Zugriff auf lokale Ressourcen zu gewährleisten, die lokal authentifiziert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="62085-204">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="62085-205">Führen Sie die Schritte unter [enable Domain-Joined Windows 10 Devices aus, die von Microsoft 365 Business verwaltet werden](manage-windows-devices.md) , um diese einzurichten.</span><span class="sxs-lookup"><span data-stu-id="62085-205">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="62085-206">Dies ist die bevorzugte Methode, und die Geräte in diesem Zustand werden als hybride Azure AD-verbundene Geräte bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="62085-206">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

<span data-ttu-id="62085-207">Wenn Ihr Unternehmen über ein lokales Active Directory verfügt, das einige lokale Ressourcen (wie Dateifreigaben und Drucker) enthält, können Sie Ihren Azure AD-verbundenen Geräten Zugriff auf diese Ressourcen gewähren, indem Sie die folgenden Schritte ausführen: [Zugriff auf lokale Ressourcen über eine Azure AD-verbundenes Gerät in Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="62085-207">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="62085-208">Bereitstellen von Office 365-Client-apps</span><span class="sxs-lookup"><span data-stu-id="62085-208">Deploy Office 365 client apps</span></span>

<span data-ttu-id="62085-209">Wenn Sie während des Einrichtens die automatische Installation von Office-Apps ausgewählt haben, werden die apps auf den Windows 10-Geräten installiert, sobald sich die Benutzer bei Azure AD von Ihren Windows-Geräten mit Ihren Anmeldeinformationen angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="62085-209">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="62085-210">Informationen zum Installieren von Office auf mobilen IOS-oder Android-Geräten finden Sie unter [Einrichten von mobilen Geräten für Microsoft 365 Business-Benutzer](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="62085-210">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="62085-211">Sie können Office auch einzeln installieren.</span><span class="sxs-lookup"><span data-stu-id="62085-211">You can also install Office individually.</span></span> <span data-ttu-id="62085-212">Anweisungen hierzu finden Sie unter [Installieren von Office auf einem PC oder Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) .</span><span class="sxs-lookup"><span data-stu-id="62085-212">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) for instructions.</span></span>

## <a name="additional-security-settings"></a><span data-ttu-id="62085-213">Zusätzliche Sicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="62085-213">Additional security settings</span></span>

<span data-ttu-id="62085-214">Zusätzlich zur Sicherheits-und Konformitäts Einstellung im Setup-Assistenten können Sie auch die folgenden zusätzlichen Einstellungen einrichten:</span><span class="sxs-lookup"><span data-stu-id="62085-214">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="62085-215">**Schutz von e-Mail-Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="62085-215">**Email malware protection**</span></span>
- <span data-ttu-id="62085-216">**Advanced Threat Protection (ATP) sichere Anlagen**</span><span class="sxs-lookup"><span data-stu-id="62085-216">**Advanced Threat Protection (ATP) Safe Attachments**</span></span>
- <span data-ttu-id="62085-217">**ATP-sichere Links**</span><span class="sxs-lookup"><span data-stu-id="62085-217">**ATP Safe Links**</span></span>
- <span data-ttu-id="62085-218">**APT-Phishing**</span><span class="sxs-lookup"><span data-stu-id="62085-218">**APT anti-phishing**</span></span>
- <span data-ttu-id="62085-219">**Exchange Online-Archivierung**</span><span class="sxs-lookup"><span data-stu-id="62085-219">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="62085-220">**Verhinderung von Datenverlusten (Data Loss Prevention, DLP)**</span><span class="sxs-lookup"><span data-stu-id="62085-220">**Data loss prevention (DLP)**</span></span>
- <span data-ttu-id="62085-221">**Azure Information Protection** (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="62085-221">**Azure Information Protection** (Plan 1)</span></span>
- <span data-ttu-id="62085-222">**InTune-Portal Verfügbarkeit**</span><span class="sxs-lookup"><span data-stu-id="62085-222">**Intune portal availability**</span></span>

<span data-ttu-id="62085-223">Weitere Informationen finden Sie unter [Einrichten von erweiterten Sicherheitsrichtlinien](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="62085-223">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

<span data-ttu-id="62085-224">Weitere Informationen finden Sie unter [Top 10 Ways to Secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a Roadmap of Best Security Practices.</span><span class="sxs-lookup"><span data-stu-id="62085-224">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>