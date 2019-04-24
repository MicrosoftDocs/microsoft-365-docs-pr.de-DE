---
title: Einrichten von Microsoft 365 Business mithilfe des Setup-Assistenten
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
description: Erfahren Sie, wie Sie Microsoft 365 Business einrichten, indem Sie vier Schritte ausführen.
ms.openlocfilehash: a1c8a41c3e291983276280a063248bdd10a7f85a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283901"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="904d9-103">Einrichten von Microsoft 365 Business mithilfe des Setup-Assistenten</span><span class="sxs-lookup"><span data-stu-id="904d9-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="904d9-104">Führen Sie die Schritte 1-4 unten aus.</span><span class="sxs-lookup"><span data-stu-id="904d9-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="904d9-105">Einrichten von Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="904d9-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="904d9-106">Sehen Sie sich ein Video zum Einrichten von Microsoft 365 Business an, wenn Sie nicht über ein lokales Active Directory verfügen:</span><span class="sxs-lookup"><span data-stu-id="904d9-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="904d9-107">Die Schritte zum Einrichten von Setups beziehen sich auf die lokalen Active Directory-Installationen.</span><span class="sxs-lookup"><span data-stu-id="904d9-107">The set-up steps include information for setups that include local Active Directory.</span></span> <span data-ttu-id="904d9-108">Wenn Sie weiterhin auf Domänen verbundene Geräte zugreifen möchten, lesen Sie die folgenden Artikel, um dies zu ermöglichen, und führen Sie die Schritte aus, bevor Sie den Setup-Assistenten ausführen:</span><span class="sxs-lookup"><span data-stu-id="904d9-108">If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="904d9-109">Aktivieren von Domänenbeitritt zu Windows 10-Geräten, die von Microsoft 365 Business verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="904d9-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="904d9-110">-Dies ist die empfohlene Methode.</span><span class="sxs-lookup"><span data-stu-id="904d9-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="904d9-111">Zugreifen auf lokale Ressourcen über ein Azure AD-verbundenes Gerät in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="904d9-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="904d9-112">Schritt 1: Personalisieren der Anmeldung</span><span class="sxs-lookup"><span data-stu-id="904d9-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="904d9-113">Melden Sie sich bei [Microsoft 365 Business](https://portal.microsoft.com) mit ihren globalen Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="904d9-113">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials.</span></span> <span data-ttu-id="904d9-114">Klicken Sie auf die Kachel **Admin**, um zum Admin Center zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="904d9-114">Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="904d9-115">Wählen Sie **Setup starten** (abhängig von Ihrem Status wird möglicherweise stattdessen die Option **Setup weiter** angezeigt) im Admin Center, um den Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="904d9-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="904d9-116">Geben Sie den Domänennamen ein, den Sie verwenden möchten (wie contoso.com).</span><span class="sxs-lookup"><span data-stu-id="904d9-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="904d9-117">Gehen Sie vor, und geben Sie Ihre Domäne ein, auch wenn Sie dies bei der Verwendung von Azure AD Connect überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="904d9-117">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example.</span></span> <span data-ttu-id="904d9-118">Die folgenden beiden Schritte gelten nicht für Sie, wenn Sie Azure AD Connect zum Überprüfen Ihrer Domäne verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="904d9-118">The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="904d9-119">Führen Sie die Schritte im Assistenten aus, um [DNS-Einträge bei einem beliebigen DNS-Hostinganbieter für Office 365 zu erstellen](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) , der überprüft, ob Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="904d9-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="904d9-120">Sie können sich ein Beispiel Video von [Video ansehen: Einrichten von Office 365 im neuen Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8).</span><span class="sxs-lookup"><span data-stu-id="904d9-120">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8).</span></span> <span data-ttu-id="904d9-121">Beachten Sie, dass dieses Video nicht die Datenschutz Schritte von Microsoft 365 Business umfasst.</span><span class="sxs-lookup"><span data-stu-id="904d9-121">Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot des Setup-Assistenten für die Business Cloud Suite.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="904d9-123">Schritt 2: Hinzufügen von Benutzern und Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="904d9-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="904d9-124">Sie können Benutzer hinzufügen, oder Sie können später im Admin Center [Benutzer hinzufügen](add-users-m365b.md) .</span><span class="sxs-lookup"><span data-stu-id="904d9-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="904d9-125">Allen Benutzern, die Sie hinzufügen, wird automatisch eine Microsoft 365 Business-Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="904d9-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="904d9-126">Wenn Ihr Microsoft 365 Business-Abonnement über vorhandene Benutzer verfügt (beispielsweise, wenn Sie Azure AD Connect verwendet haben), erhalten Sie jetzt die Option, Ihnen Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="904d9-126">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now.</span></span> <span data-ttu-id="904d9-127">Gehen Sie vor, und fügen Sie Lizenzen hinzu.</span><span class="sxs-lookup"><span data-stu-id="904d9-127">Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="904d9-128">Außerdem erhalten Sie eine Option zum Freigeben von Anmeldeinformationen für die neuen Benutzer, die Sie hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="904d9-128">You will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="904d9-129">Sie können auswählen, ob Sie Sie ausdrucken, per e-Mail versenden oder herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="904d9-129">You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="904d9-130">Überspringen Sie die Migration von e-Mail-Nachrichten, und wählen Sie **weiter** auf Seite **e-Mails migrieren** .</span><span class="sxs-lookup"><span data-stu-id="904d9-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="904d9-131">Wenn Sie von einem anderen e-Mail-Anbieter wechseln und Ihre Daten später kopieren möchten, können Sie [e-Mails und Kontakte zu Office 365 migrieren](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="904d9-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot von zwei neuen Benutzern, die im Setup-Assistenten hinzugefügt wurden](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="904d9-133">Schritt 3: Verbinden Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="904d9-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="904d9-134">Wenn Sie die. onmicrosoft-Domäne oder Azure AD Connect verwendet haben, wird dieser Schritt nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="904d9-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="904d9-135">Um Dienste einzurichten, müssen Sie einige Datensätze bei Ihrem DNS-Host oder Ihrer Domänenregistrierungsstelle aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="904d9-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="904d9-136">Der Setup-Assistent erkennt in der Regel Ihre Registrierungsstelle und gibt Ihnen einen Link zu Schritt-für-Schritt-Anweisungen zum Aktualisieren Ihrer NS-Einträge auf der Registrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="904d9-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="904d9-137">Wenn dies nicht der Fall ist, [Ändern Sie die Namenserver, um Office 365 für eine beliebige Domänenregistrierungsstelle](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)einzurichten.</span><span class="sxs-lookup"><span data-stu-id="904d9-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="904d9-138">E-Mails und andere Dienste werden für Sie eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="904d9-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="904d9-139">Schritt 4: Verwalten von Geräten und Arbeitsdateien</span><span class="sxs-lookup"><span data-stu-id="904d9-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="904d9-140">Schützen Sie auf der Seite **Arbeitsdateien auf Ihren mobilen Geräten schützen** sowohl **Arbeitsdateien bei Verlust oder Diebstahl von Geräten** , und verwalten Sie, **wie Benutzer auf Office-Dateien auf mobilen Geräte** Einstellungen auf **on**zugreifen.</span><span class="sxs-lookup"><span data-stu-id="904d9-140">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**.</span></span> <span data-ttu-id="904d9-141">Sie können auch auf jede unter Einstellung zugreifen, indem Sie auf die Chevrons neben jeder Einstellung klicken.</span><span class="sxs-lookup"><span data-stu-id="904d9-141">You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="904d9-142">Alle Arbeitsdateien ihrer lizenzierten Benutzer sind jetzt auf iOS-und Android-Geräten geschützt, sobald Sie [Office-Apps installieren](set-up-mobile-devices.md) (und sich mit ihren Microsoft 365 Business-Anmeldeinformationen authentifizieren).</span><span class="sxs-lookup"><span data-stu-id="904d9-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot von Schutz von Arbeitsdateien auf der Seite "Mobile Geräte"](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="904d9-144">Legen Sie auf der Seite **Windows 10-Gerätekonfiguration festlegen** die Einstellung für **sichere Windows 10-Geräte** auf **ein**fest.</span><span class="sxs-lookup"><span data-stu-id="904d9-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="904d9-145">Sie können auch auf jede unter Einstellung zugreifen, indem Sie auf das Chevron daneben klicken.</span><span class="sxs-lookup"><span data-stu-id="904d9-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="904d9-146">Legen Sie die Einstellung **Office auf Windows 10-Geräten installieren** auf **Ja** fest, wenn alle Ihre Benutzer Windows 10-Computer und entweder keine vorhandenen Office-Installationen oder Klick-und-Los-Office-Installationen haben.</span><span class="sxs-lookup"><span data-stu-id="904d9-146">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs.</span></span> <span data-ttu-id="904d9-147">Wenn dies nicht der Fall ist, legen Sie diese Option auf **Nein**fest.</span><span class="sxs-lookup"><span data-stu-id="904d9-147">If this is not the case, set this option to **No**.</span></span> <span data-ttu-id="904d9-148">Sie können Office später im Admin Center [automatisch installieren](auto-install-or-uninstall-office.md) , nachdem Sie die Benutzer Computer vorbereitet haben.</span><span class="sxs-lookup"><span data-stu-id="904d9-148">You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers.</span></span> <span data-ttu-id="904d9-149">Anweisungen finden Sie unter [Prepare for Office Clientinstallation](prepare-for-office-client-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="904d9-149">For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="904d9-150">Die Arbeitsdateien der lizenzierten Benutzer auf Windows 10-Geräten werden projiziert, sobald Sie [Ihr Windows 10-Gerät](set-up-windows-devices.md) mit einer Microsoft 365 Business Azure AD-Domäne verbinden oder [Windows 10 auf einem neuen Computer installieren](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) und gleichzeitig dem Microsoft 365 beitreten. Business Azure AD-Domäne.</span><span class="sxs-lookup"><span data-stu-id="904d9-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="904d9-151">Klicken Sie auf **weiter** , und Sie sind mit Setup fertig.</span><span class="sxs-lookup"><span data-stu-id="904d9-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="904d9-152">Bitte geben Sie uns Feedback in diesem Schritt, um die Erfahrung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="904d9-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot der Seite "Vorbereiten von Windows 10-Geräten"](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="904d9-154">Zusätzliche Sicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="904d9-154">Additional security settings</span></span>

<span data-ttu-id="904d9-155">Zusätzlich zur Sicherheits-und Konformitäts Einstellung im Setup-Assistenten können Sie auch die folgenden zusätzlichen Einstellungen einrichten:</span><span class="sxs-lookup"><span data-stu-id="904d9-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="904d9-156">Einrichten des Schutzes vor unsicheren Anlagen.</span><span class="sxs-lookup"><span data-stu-id="904d9-156">Set up protection against unsafe attachments.</span></span> <span data-ttu-id="904d9-157">**Erweiterter Bedrohungsschutz** (ATP) identifiziert bösartige Inhalte und blockiert dann die Bereitstellung von unsicheren Anlagen und schützt Sie vor Phishing-Schemata und Ransomware-Infektionen.</span><span class="sxs-lookup"><span data-stu-id="904d9-157">**Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections.</span></span> <span data-ttu-id="904d9-158">Informationen zum Aktivieren des Anlagenschutzes finden Sie unter [Einrichten von Office 365 ATP Safe Attachments Policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span><span class="sxs-lookup"><span data-stu-id="904d9-158">To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="904d9-159">Schützen Sie Ihre Umgebung, wenn Benutzer auf böswillige Links klicken.</span><span class="sxs-lookup"><span data-stu-id="904d9-159">Protect your environment when users click malicious links.</span></span> <span data-ttu-id="904d9-160">ATP untersucht Links in e-Mails zu dem Zeitpunkt, zu dem ein Benutzer darauf klickt.</span><span class="sxs-lookup"><span data-stu-id="904d9-160">ATP examines links in email at the time a user clicks them.</span></span> <span data-ttu-id="904d9-161">Wenn ein Link unsicher ist, wird der Benutzer gewarnt, die Website nicht zu besuchen oder zu benachrichtigen, dass die Website blockiert wurde.</span><span class="sxs-lookup"><span data-stu-id="904d9-161">If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked.</span></span> <span data-ttu-id="904d9-162">Dies schützt vor Phishing-Schemata.</span><span class="sxs-lookup"><span data-stu-id="904d9-162">This helps protect against phishing schemes.</span></span> <span data-ttu-id="904d9-163">Einrichten [von office 365 ATP Safe Links](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) Policies oder [einrichten von Office 365 ATP Safe Links Policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span><span class="sxs-lookup"><span data-stu-id="904d9-163">[Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="904d9-164">Sie können alle Postfachinhalte, einschließlich gelöschter Elemente, beibehalten, indem Sie für ein vollständiges Postfach des Benutzers einen **Rechtsstreit halten**.</span><span class="sxs-lookup"><span data-stu-id="904d9-164">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**.</span></span> <span data-ttu-id="904d9-165">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="904d9-165">For instructions, see</span></span> 
- <span data-ttu-id="904d9-166">[Einrichten der e-Mail-Aufbewahrung mit der Exchange Online-Archivierung](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span><span class="sxs-lookup"><span data-stu-id="904d9-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="904d9-167">Richten Sie angepasste **Aufbewahrungsrichtlinien**ein, um beispielsweise eine bestimmte Zeitdauer beizubehalten oder Inhalte dauerhaft am Ende des Aufbewahrungszeitraums zu löschen.</span><span class="sxs-lookup"><span data-stu-id="904d9-167">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="904d9-168">Sie können angepasste Aufbewahrungsrichtlinien im Securities and Compliance Center aktivieren, zur **Aufbewahrung**von **Datenverwaltung** \> wechseln und dann die Schritte im Assistenten befolgen.</span><span class="sxs-lookup"><span data-stu-id="904d9-168">You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard.</span></span> <span data-ttu-id="904d9-169">Weitere Informationen finden Sie unter [Übersicht über Aufbewahrungsrichtlinien](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="904d9-169">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="904d9-170">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="904d9-170">Next steps</span></span>

<span data-ttu-id="904d9-171">Für die Benutzer, die über Ihre Lizenzen verfügen, besteht der nächste Schritt darin, Geräte einzurichten.</span><span class="sxs-lookup"><span data-stu-id="904d9-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="904d9-172">Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für microsoft 365-Geschäftsbenutzer](set-up-windows-devices.md) und [Einrichten von mobilen geräten für Microsoft 365 Business-Benutzer](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="904d9-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="904d9-173">Weitere Informationen finden Sie unter [Verwalten von Microsoft 365 Business](manage.md) für Links zu Themen zum Festlegen von Geräte-und App-Schutzrichtlinien und zum Entfernen von Daten von Benutzergeräten.</span><span class="sxs-lookup"><span data-stu-id="904d9-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


