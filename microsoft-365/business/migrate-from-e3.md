---
title: Migrieren zu Microsoft 365 Business von Office 365 E3
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Erfahren Sie, wie Sie Ihr Unternehmen von Microsoft 365 Business Premium E3 Office 365 verschieben.
ms.openlocfilehash: f08b054473fdd63ec2372e81c776a1b64f89fe9d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244834"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="6eba6-103">Migrieren von Office 365 E3 zu Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="6eba6-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="6eba6-104">Microsoft 365 Business Premium bietet alles, was Sie für Ihr kleines Unternehmen benötigen, und kombiniert die erstklassigen cloudbasierten Produktivitäts-Apps mit einfacher Geräteverwaltung und Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="6eba6-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="6eba6-105">Wenn Sie derzeit über ein Office 365 E3-Abonnement verfügen, aber nicht mehr als 300 Mitarbeiter haben, sollten Sie für zusätzliche Sicherheitsfeatures zu Microsoft 365 Business Premium wechseln.</span><span class="sxs-lookup"><span data-stu-id="6eba6-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="6eba6-106">Die Migration ist einfach: Zuerst wechseln Sie die Lizenzen, und alle Ihre Daten und Benutzerinformationen in Ihrem aktuellen Abonnement werden verwaltet.</span><span class="sxs-lookup"><span data-stu-id="6eba6-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="6eba6-107">Nach der Migration müssen Sie die Features einrichten, die in der Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="6eba6-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="6eba6-108">Unterschiede zwischen Office 365 E3 und Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="6eba6-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="6eba6-109">Diese Tabelle zeigt die Unterschiede zwischen Microsoft 365 Business Premium und Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="6eba6-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="6eba6-110">Feature</span><span class="sxs-lookup"><span data-stu-id="6eba6-110">Feature</span></span>    | <span data-ttu-id="6eba6-111">Support in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="6eba6-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="6eba6-112">Support in Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="6eba6-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="6eba6-113">**Lokal**</span><span class="sxs-lookup"><span data-stu-id="6eba6-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="6eba6-114">Office Apps<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="6eba6-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="6eba6-115">Microsoft 365 Apps for Business</span><span class="sxs-lookup"><span data-stu-id="6eba6-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="6eba6-116">Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="6eba6-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="6eba6-117">**Cloud-Produktivitäts-Apps**</span><span class="sxs-lookup"><span data-stu-id="6eba6-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="6eba6-118">Exchange Online und Outlook</span><span class="sxs-lookup"><span data-stu-id="6eba6-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="6eba6-119">50 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online-Archivierung</span><span class="sxs-lookup"><span data-stu-id="6eba6-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="6eba6-120">100 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online-Archivierung</span><span class="sxs-lookup"><span data-stu-id="6eba6-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="6eba6-121">Teams</span><span class="sxs-lookup"><span data-stu-id="6eba6-121">Teams</span></span>    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="6eba6-124">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="6eba6-124">OneDrive for Business</span></span>    | <span data-ttu-id="6eba6-125">Speichergrenzwert von 1 TB pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="6eba6-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="6eba6-126">Unbegrenzt</span><span class="sxs-lookup"><span data-stu-id="6eba6-126">Unlimited</span></span> | 
| <span data-ttu-id="6eba6-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="6eba6-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="6eba6-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="6eba6-130">StaffHub</span></span>    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="6eba6-133">MileIQ</span><span class="sxs-lookup"><span data-stu-id="6eba6-133">MileIQ</span></span>    | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| <span data-ttu-id="6eba6-135">**Bedrohungsschutz**</span><span class="sxs-lookup"><span data-stu-id="6eba6-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="6eba6-136">Microsoft Defender für Office 365 Plan 1</span><span class="sxs-lookup"><span data-stu-id="6eba6-136">Defender for Office 365 Plan 1</span></span> | ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="6eba6-138">Nicht enthalten, kann aber hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="6eba6-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="6eba6-139">**Identitätsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="6eba6-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="6eba6-140">Self-Service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span><span class="sxs-lookup"><span data-stu-id="6eba6-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| <span data-ttu-id="6eba6-142">**Verwaltung von Geräten und Apps**</span><span class="sxs-lookup"><span data-stu-id="6eba6-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="6eba6-143">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="6eba6-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="6eba6-145">Aktivierung gemeinsam genutzter Computer</span><span class="sxs-lookup"><span data-stu-id="6eba6-145">Shared computer activation</span></span>|     ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    | ![Enthalten in Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="6eba6-148">Upgraderechte auf Windows 10 Pro von Win 7/8.1-Pro</span><span class="sxs-lookup"><span data-stu-id="6eba6-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)    || 
| <span data-ttu-id="6eba6-150">**Schutz von Daten**</span><span class="sxs-lookup"><span data-stu-id="6eba6-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="6eba6-151">Verhinderung von Datenverlust in Office 365</span><span class="sxs-lookup"><span data-stu-id="6eba6-151">Office 365 Data Loss Prevention</span></span>|    ![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)|![Enthalten in Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="6eba6-154">Azure Information Protection Plan 1, BitLocker Erzwingung</span><span class="sxs-lookup"><span data-stu-id="6eba6-154">Azure Information Protection Plan 1, BitLocker enforcement</span></span>|![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="6eba6-156">Azure Information Protection Plan 1, Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="6eba6-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Im Lieferumfang Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="6eba6-158">**Clientzugriffslizenz (CAL-Rechte)**</span><span class="sxs-lookup"><span data-stu-id="6eba6-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="6eba6-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="6eba6-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Enthalten in Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="6eba6-161"><sup>1</sup> Die Microsoft 365 Business Premium der Office-Apps umfasst keine Volumenaktivierung über Gruppenrichtlinien, App-Telemetrie, Updatesteuerelemente, Tabellenvergleich und -abfragen oder Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="6eba6-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="6eba6-162">Migration</span><span class="sxs-lookup"><span data-stu-id="6eba6-162">Migration</span></span>

<span data-ttu-id="6eba6-163">Anweisungen zum Migrieren [](../commerce/subscriptions/change-plans-manually.md) Ihres Abonnements finden Sie unter Manuelles Ändern von Plänen für Anweisungen, wenn Sie nur wenige Personen in die Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="6eba6-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="6eba6-164">Sie können auch [alle Benutzer automatisch aktualisieren](../commerce/subscriptions/upgrade-to-different-plan.md)oder mit einem Partner zusammenarbeiten, um Ihr E3-Abonnement und Ihre Lizenzen in ein Microsoft 365 Business Premium verschieben.</span><span class="sxs-lookup"><span data-stu-id="6eba6-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="6eba6-165">In den folgenden Abschnitten werden die Änderungen beschrieben, die Sie gegebenenfalls vornehmen müssen, und was Sie nach der Migration tun können.</span><span class="sxs-lookup"><span data-stu-id="6eba6-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="6eba6-166">Office 365 Konfiguration und Daten des E3-Abonnements</span><span class="sxs-lookup"><span data-stu-id="6eba6-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="6eba6-167">Sie müssen vor der Migration keine Änderungen an Ihrem aktuellen Abonnement oder Ihren Daten vornehmen. Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="6eba6-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="6eba6-168">Abonnementkonfiguration, z. B. DNS-Einträge und Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="6eba6-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="6eba6-169">Benutzer- und Gruppenkonten und Authentifizierungseinstellungen, z. B. mehrstufige Authentifizierung oder Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="6eba6-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="6eba6-170">Produktivitätsdienstkonfigurationen und ihre Daten, z. B. Teams, Exchange Online Postfächer, SharePoint Onlinewebsites, OneDrive for Business Ordner und OneNote Notizbücher.</span><span class="sxs-lookup"><span data-stu-id="6eba6-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="6eba6-171">Office Anwendungen werden automatisch skaliert.</span><span class="sxs-lookup"><span data-stu-id="6eba6-171">Office applications will scale automatically.</span></span> <span data-ttu-id="6eba6-172">Office 365 moderne Lizenzierung überprüft alle 72 Stunden die Lizenzzuweisung des Benutzers und konvertiert Office-Anwendungen in die Version, die dem Benutzerabonnement entspricht.</span><span class="sxs-lookup"><span data-stu-id="6eba6-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="6eba6-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="6eba6-173">Windows 10</span></span>

<span data-ttu-id="6eba6-174">Wenn Ihre Windows noch nicht auf Windows Pro Creator-Update installiert sind, aktualisieren Sie sie auf [Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="6eba6-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="6eba6-175">Einrichten von Richtlinien zum Schutz von Benutzergeräten und -dateien</span><span class="sxs-lookup"><span data-stu-id="6eba6-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="6eba6-176">Wenn Sie die Office 365 und Geräte einrichten, werden diese Geräte  auf der Seite Geräte im Microsoft 365 admin center aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6eba6-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6eba6-177">Alle von Ihnen eingerichteten Richtlinien werden in der Liste der klassischen Richtlinien im [Intune-Portal angezeigt.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)</span><span class="sxs-lookup"><span data-stu-id="6eba6-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="6eba6-178">Nachdem Sie Lizenzen für Microsoft 365 Business Premium zugewiesen haben, können Sie mit dem Schutz der Geräte und Dateien der Benutzer beginnen.</span><span class="sxs-lookup"><span data-stu-id="6eba6-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="6eba6-179">Wenn Sie alle Benutzer in Ihrer Organisation auf Microsoft 365 Business Premium aktualisiert haben, wird der Setup-Assistent auf der Startseite angezeigt, und Sie können die Schritte [einrichten Microsoft 365 Business Premium in](set-up.md) den Schritten des Setup-Assistenten zum Schutz von Dateien und mobilen Geräten ausführen.</span><span class="sxs-lookup"><span data-stu-id="6eba6-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="6eba6-180">Sie können die folgenden Schritte auch auf der Seite Geräte ausführen:</span><span class="sxs-lookup"><span data-stu-id="6eba6-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="6eba6-181">Wechseln Sie im Admin Center im  linken Navigations navi zu \> **Geräterichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="6eba6-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="6eba6-182">Wählen Sie **auf der Seite** Geräterichtlinien die Option Hinzufügen **aus.**</span><span class="sxs-lookup"><span data-stu-id="6eba6-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="6eba6-183">Geben Sie **der Richtlinie im** Bereich Richtlinie hinzufügen  einen Namen zu, und wählen Sie dann in der Dropdownliste einen Richtlinientyp aus.</span><span class="sxs-lookup"><span data-stu-id="6eba6-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="6eba6-184">Sie können Anwendungsrichtlinien für den Schutz von Dateien auf Android- und iPhone-Geräten sowie Windows 10 einrichten und Gerätekonfigurationsrichtlinien für Unternehmenseigene Windows 10 einrichten.</span><span class="sxs-lookup"><span data-stu-id="6eba6-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="6eba6-185">Weitere Informationen finden Sie unter den folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="6eba6-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="6eba6-186">Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="6eba6-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="6eba6-187">Festlegen von Anwendungsschutzeinstellungen für Windows 10 Geräte</span><span class="sxs-lookup"><span data-stu-id="6eba6-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="6eba6-188">Festlegen von Geräteschutzeinstellungen für Windows 10 PCs</span><span class="sxs-lookup"><span data-stu-id="6eba6-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="6eba6-189">Nachdem Sie Richtlinien eingerichtet haben, können Sie und Ihre Mitarbeiter Geräte einrichten:</span><span class="sxs-lookup"><span data-stu-id="6eba6-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="6eba6-190">Unter [Einrichten von Windows für Microsoft 365 Business Premium finden](set-up-windows-devices.md) Sie Schritte für Windows Geräte.</span><span class="sxs-lookup"><span data-stu-id="6eba6-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="6eba6-191">Unter [Einrichten mobiler Geräte für Microsoft 365 Business Premium finden Sie](set-up-mobile-devices.md) Schritte für Android-Smartphones und iPhones.</span><span class="sxs-lookup"><span data-stu-id="6eba6-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="6eba6-192">Postfachgröße</span><span class="sxs-lookup"><span data-stu-id="6eba6-192">Mailbox Size</span></span>

<span data-ttu-id="6eba6-193">Microsoft 365 Business Premium hat einen Speichergrenzwert von 50 GB, während er Exchange Online Plan 1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="6eba6-193">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="6eba6-194">Bei der Migration zu Microsoft 365 Business Premium wird empfohlen, diesem Benutzer einen Exchange Online Plan 2 zuzuordnen und den Exchange Online Plan 1 zu entfernen, da beides nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="6eba6-194">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>


### <a name="threat-protection"></a><span data-ttu-id="6eba6-195">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="6eba6-195">Threat protection</span></span>

<span data-ttu-id="6eba6-196">Nach der Migration zu Microsoft 365 Business Premium haben Sie Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="6eba6-196">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="6eba6-197">Eine Übersicht finden Sie Office 365 Microsoft [Defender.](../security/office-365-security/defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="6eba6-197">See [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="6eba6-198">Informationen zum Einrichten finden Sie [](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)unter [Einrichten sicherer Links,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)Einrichten sicherer Anlagen und Einrichten von [Antiphishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="6eba6-198">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="6eba6-199">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="6eba6-199">Sensitivity labels</span></span>

<span data-ttu-id="6eba6-200">Informationen zur Verwendung von Vertraulichkeitsbezeichnungen finden Sie unter Übersicht über [Vertraulichkeitsbezeichnungen](../compliance/sensitivity-labels.md) und [Erstellen und Verwalten von Vertraulichkeitsbezeichnungen.](../business-video/create-sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="6eba6-200">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>
