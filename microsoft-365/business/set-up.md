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
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Erfahren Sie, wie Microsoft 365 Business einrichten, indem Sie vier Schritte ausführen.
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867565"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="7365d-103">Einrichten von Microsoft 365 Business mithilfe des Setup-Assistenten</span><span class="sxs-lookup"><span data-stu-id="7365d-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="7365d-104">Führen Sie die Schritte 1 bis 4 unten.</span><span class="sxs-lookup"><span data-stu-id="7365d-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="7365d-105">Einrichten von Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="7365d-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="7365d-106">Sehen Sie sich ein Video über das Microsoft 365 Business einrichten, wenn Sie nicht über einen lokalen Active Directory verfügen:</span><span class="sxs-lookup"><span data-stu-id="7365d-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="7365d-p101">Die Installationsschritte enthalten Informationen für Installationen, die lokale Active Directory enthalten. Wenn Sie weiterhin auf die Domäne eingebundener Geräte zugreifen möchten, lesen Sie die folgenden Artikel für zwei neue Art und Weise aktivieren, und führen Sie die Schritte aus, bevor Sie den Setup-Assistenten ausführen:</span><span class="sxs-lookup"><span data-stu-id="7365d-p101">The set-up steps include information for setups that include local Active Directory. If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="7365d-109">Aktivieren Sie in die Domäne eingebundener Windows 10 Geräte von Microsoft 365 Business verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="7365d-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="7365d-110">-Dies ist die empfohlene Option.</span><span class="sxs-lookup"><span data-stu-id="7365d-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="7365d-111">Zugriff auf lokale Ressourcen von einem Azure AD gehörenden Gerät in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="7365d-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="7365d-112">Schritt 1: Personalisieren Sie-Anmeldung</span><span class="sxs-lookup"><span data-stu-id="7365d-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="7365d-p102">Melden Sie sich mit Ihren Anmeldeinformationen globaler Administrator [Microsoft 365 Business](https://portal.microsoft.com) an. Wählen Sie die Kachel " **Admin** ", fahren Sie mit der Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="7365d-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="7365d-115">Wählen Sie **Setup starten** (je nach Ihrem Status mangelndes **Weiter Setup** stattdessen) in der Verwaltungskonsole, um den Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="7365d-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="7365d-116">Geben Sie den Domänennamen ein, den Sie (wie "contoso.com") verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7365d-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="7365d-p103">Fahren Sie fort, und geben Sie Ihre Domäne, auch wenn Sie es bei Verwendung von Azure Active Directory verbinden, beispielsweise überprüft haben. Die folgenden beiden Schritte gelten nicht für Sie, wenn Sie Azure AD-Verbindung verwendet, um Ihre Domäne zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7365d-p103">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example. The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="7365d-119">Führen Sie die Schritte im Assistenten zum [Erstellen von DNS-Datensätze an alle DNS-Hostinganbieter für Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) , die überprüft, ob Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="7365d-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="7365d-p104">Sehen Sie ein Beispiel Video des [Video: Setup Office 365 in der neuen Verwaltungskonsole](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Beachten Sie, dass in diesem Video die Schritte zum Data Protection Microsoft 365 Business nicht enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="7365d-p104">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot des Business Cloud Suite Setup-Assistenten.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="7365d-123">Schritt 2: Hinzufügen von Benutzern und Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="7365d-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="7365d-124">Sie können hier Benutzer hinzufügen, oder können Sie in der Verwaltungskonsole [Benutzer später hinzufügen](add-users-m365b.md) .</span><span class="sxs-lookup"><span data-stu-id="7365d-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="7365d-125">Alle Benutzer, die Sie hinzufügen möchten automatisch Microsoft 365 Business Lizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7365d-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="7365d-p105">Wenn das Microsoft 365 Business-Abonnement umfasst vorhandener Benutzer (beispielsweise, wenn Sie Azure AD-Connect verwendet), erhalten Sie eine Option zum Zuweisen von Lizenzen für diese jetzt. Fahren Sie fort, und fügen Sie Lizenzen für diese ebenfalls.</span><span class="sxs-lookup"><span data-stu-id="7365d-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="7365d-p106">Sie erhalten auch eine Option, um Anmeldeinformationen für die neue Benutzer freizugeben, die Sie hinzugefügt haben. Sie können auch auszudrucken, per e-Mail senden oder herunterladen.</span><span class="sxs-lookup"><span data-stu-id="7365d-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="7365d-130">Überspringen Sie migrieren von e-Mail-Nachrichten, und wählen Sie auf der Seite **Migration e-Mail-Nachrichten** **Weiter** .</span><span class="sxs-lookup"><span data-stu-id="7365d-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="7365d-131">Wenn Sie aus einer anderen e-Mail-Anbieter verschieben und Ihre Daten später kopieren möchten, können Sie [e-Mail-Migration und Kontakte zu Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="7365d-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot des zwei neue Benutzer im Setup-Assistenten hinzugefügt](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="7365d-133">Schritt 3: Verbinden Sie Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="7365d-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="7365d-134">Wenn Sie, verwenden Sie die Domäne .onmicrosoft möchten oder Azure AD-Verbindung verwendet, wird dieser Schritt nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7365d-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="7365d-135">Um-Dienste einrichten zu können, müssen Sie einige Datensätze an Ihrer DNS-Host oder Domäne Registrierungsstelle zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7365d-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="7365d-p107">Der Setup-Assistent wird in der Regel erkennt die zu Ihrer Registrierungsstelle und bietet Ihnen eine Verknüpfung, eine schrittweise Anleitung zum Aktualisieren von Ihrer NS-Datensätzen auf der Website der Registrierungsstelle. Wenn dies nicht der Fall, [Änderung Namens-Server zum Einrichten von Office 365 mit jeder domänenregistrierungsstelle](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="7365d-p107">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website. If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="7365d-138">E-Mail und andere Dienste werden für Sie eingerichtet werden</span><span class="sxs-lookup"><span data-stu-id="7365d-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="7365d-139">Schritt 4: Verwalten von Geräten und Arbeitsdateien</span><span class="sxs-lookup"><span data-stu-id="7365d-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="7365d-p108">Seite festlegen auf die **Protect Arbeitsdateien auf Ihren mobilen Geräten** **Protect Arbeitsdateien bei verlorenen oder gestohlenen Geräten sind** und Einstellungen für **den Zugriff von Benutzern auf Office-Dateien auf mobilen Geräten verwalten** auf **aktiviert**. Sie können auch die einzelnen untergeordneten festlegen durch Klicken auf die Richtungspfeile neben jede Einstellung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7365d-p108">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**. You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="7365d-142">Alle Ihre lizenzierten Benutzern Arbeitsdateien sind jetzt geschützt auf iOS und Android-Geräte, sobald sie [Installieren von Office-apps](set-up-mobile-devices.md) (und die Authentifizierung mit den Anmeldeinformationen ihres Microsoft 365 Business).</span><span class="sxs-lookup"><span data-stu-id="7365d-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot des schützen Arbeitsdateien auf der Seite für mobile Geräte](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="7365d-144">Setzen Sie **Secure Windows 10 Geräte** Einstellung auf **aktiviert**, auf der Seite **Gerätekonfiguration Windows 10 festgelegt** .</span><span class="sxs-lookup"><span data-stu-id="7365d-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="7365d-145">Sie können auch die einzelnen untergeordneten festlegen durch Klicken auf den Doppelpfeil daneben zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7365d-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="7365d-p109">Legen Sie die Einstellung für die **Installation von Office auf Windows 10 Geräte** auf **Ja** , wenn alle Benutzer verfügen über Windows 10 Computer und entweder keine vorhandenen Office installiert, oder Klick-und-Los-Office-Installationen. Wenn dies nicht der Fall ist, legen Sie diese Option auf **Nein**. Sie können später aus dem Administrationscenter [automatisch installieren von Office](auto-install-or-uninstall-office.md) , nachdem Sie auf dem Computer des Benutzers vorbereitet haben. Anweisungen finden Sie unter [Vorbereiten der Installation von Office-Client](prepare-for-office-client-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="7365d-p109">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs. If this is not the case, set this option to **No**. You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers. For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="7365d-150">Sobald sie die lizenzierte Benutzer Arbeitsdateien auf Geräten mit Windows 10 projiziert werden für eine Microsoft 365 Business Azure AD-Domäne oder [Windows 10 auf einem neuen Computer installieren](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) , während gleichzeitig teilnehmen an der Microsoft 365 [Teilnehmen an ihrem Windows-10-Gerät](set-up-windows-devices.md) Business Azure AD-Domäne.</span><span class="sxs-lookup"><span data-stu-id="7365d-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="7365d-151">Klicken Sie auf **Weiter** und Sie mit dem Setup fertig sind.</span><span class="sxs-lookup"><span data-stu-id="7365d-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="7365d-152">Lassen Sie uns Feedback an dieser Stelle zu helfen, der zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="7365d-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot von vorbereiten Windows 10 Geräte-Seite](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="7365d-154">Zusätzliche Sicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="7365d-154">Additional security settings</span></span>

<span data-ttu-id="7365d-155">Zusätzlich zu den Sicherheit und Compliance-Einstellung im Setup-Assistenten können Sie auch die folgenden zusätzlichen Einstellungen einrichten:</span><span class="sxs-lookup"><span data-stu-id="7365d-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="7365d-p110">Einrichten von Schutz gegen unsichere Anlagen. **Erweiterte Schutz** (ATP) identifiziert schädlichem Inhalt und klicken Sie dann blockiert die Übermittlung von unsicheren Anlagen Schutz gegen Phishing-Methoden und Ransomware Infektionen. Zum Schutz der Anlage zu aktivieren, finden Sie unter [Einrichten von Richtlinien für Office 365 ATP sichere Anlagen](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span><span class="sxs-lookup"><span data-stu-id="7365d-p110">Set up protection against unsafe attachments. **Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections. To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="7365d-p111">Schützen Sie Ihre Umgebung aus, wenn Benutzer auf böswillige Links klicken. ATP untersucht Links in e-Mails an die Zeit, die ein Benutzer darauf klickt. Wenn eine Verknüpfung nicht sicher ist, wird der Benutzer gewarnt, nicht auf die Website zugreifen oder darüber informiert, dass die Website blockiert wurde. Dies bietet Schutz vor Phishing-Methoden. [Einrichten von Richtlinien für sichere Links zu Office 365 ATP](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) oder [Richten Sie sichere Links zu Office 365 ATP-Richtlinien](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span><span class="sxs-lookup"><span data-stu-id="7365d-p111">Protect your environment when users click malicious links. ATP examines links in email at the time a user clicks them. If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked. This helps protect against phishing schemes. [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="7365d-p112">Sie können den gesamten Inhalt des Postfachs einschließlich gelöschte Elemente durch die Bereitstellung der gesamte Postfach eines Benutzers auf **Rechtsstreitigkeiten halten**beibehalten. Anweisungen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="7365d-p112">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**. For instructions, see</span></span> 
- <span data-ttu-id="7365d-166">[Einrichten von e-Mail-Archivierung mit Exchange Online-Archivierung](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span><span class="sxs-lookup"><span data-stu-id="7365d-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="7365d-p113">Einrichten von benutzerdefinierten **Aufbewahrungsrichtlinien**, beispielsweise für eine bestimmte Zeitspanne beibehalten oder Löschen von Inhalt dauerhaft am Ende des Aufbewahrungszeitraums. Sie können benutzerdefinierte Aufbewahrungsrichtlinien in die Sicherheit und Compliance Center, klicken Sie auf **Daten Governance** aktivieren \> **Aufbewahrung**, und folgen Sie den Schritten im Assistenten. Finden Sie weitere Informationen finden Sie unter [Overview of Aufbewahrungsrichtlinien](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="7365d-p113">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard. To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="7365d-170">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7365d-170">Next steps</span></span>

<span data-ttu-id="7365d-171">Für Benutzer, die ihre Lizenzen haben, ist im nächste Schritt richten Sie Geräte ein.</span><span class="sxs-lookup"><span data-stu-id="7365d-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="7365d-172">Finden Sie unter [Einrichten von Windows-Geräte für Microsoft 365 Geschäftsbenutzer](set-up-windows-devices.md) und [Einrichten von mobilen Geräten für Microsoft 365 Geschäftsbenutzer](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="7365d-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="7365d-173">Finden Sie unter [Verwalten von Microsoft 365 Business](manage.md) Richtlinien von Links zu Themen über das Gerät und app-Schutz festlegen und wie Sie Daten von Benutzer-Geräten zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="7365d-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


