---
title: Migrieren von Office 365 E3 zu Microsoft 365 Business
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
description: Erfahren Sie, wie Sie Ihr Unternehmen von Office 365 E3 zu Microsoft 365 Business Premium verschieben.
ms.openlocfilehash: f2b7962918186f4a1063c5a66596135c2972ec71
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51749998"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="fff27-103">Migrieren von Office 365 E3 zu Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="fff27-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="fff27-104">Microsoft 365 Business Premium bietet alles, was Sie für Ihr kleines Unternehmen benötigen, und kombiniert die erstklassigen cloudbasierten Produktivitäts-Apps mit einfacher Geräteverwaltung und -sicherheit.</span><span class="sxs-lookup"><span data-stu-id="fff27-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="fff27-105">Wenn Sie derzeit über ein Office 365 E3-Abonnement verfügen, aber nicht mehr als 300 Mitarbeiter haben, sollten Sie für zusätzliche Sicherheitsfeatures zu Microsoft 365 Business Premium wechseln.</span><span class="sxs-lookup"><span data-stu-id="fff27-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="fff27-106">Die Migration ist einfach: Zuerst wechseln Sie die Lizenzen, und alle Ihre Daten und Benutzerinformationen in Ihrem aktuellen Abonnement werden verwaltet.</span><span class="sxs-lookup"><span data-stu-id="fff27-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="fff27-107">Nach der Migration müssen Sie die Features einrichten, die in Microsoft 365 Business Premium hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fff27-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="fff27-108">Unterschiede zwischen Office 365 E3 und Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="fff27-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="fff27-109">Diese Tabelle zeigt die Unterschiede zwischen Microsoft 365 Business Premium und Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="fff27-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="fff27-110">Feature</span><span class="sxs-lookup"><span data-stu-id="fff27-110">Feature</span></span>    | <span data-ttu-id="fff27-111">Support in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="fff27-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="fff27-112">Support in Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="fff27-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="fff27-113">**Lokal**</span><span class="sxs-lookup"><span data-stu-id="fff27-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="fff27-114">Office Apps<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fff27-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="fff27-115">Microsoft 365 Apps for Business</span><span class="sxs-lookup"><span data-stu-id="fff27-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="fff27-116">Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="fff27-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="fff27-117">**Cloud-Produktivitäts-Apps**</span><span class="sxs-lookup"><span data-stu-id="fff27-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="fff27-118">Exchange Online und Outlook</span><span class="sxs-lookup"><span data-stu-id="fff27-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="fff27-119">50 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online-Archivierung</span><span class="sxs-lookup"><span data-stu-id="fff27-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="fff27-120">100 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online-Archivierung</span><span class="sxs-lookup"><span data-stu-id="fff27-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="fff27-121">Teams</span><span class="sxs-lookup"><span data-stu-id="fff27-121">Teams</span></span>    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Office 365 E3 enthalten](../media/check-mark.png) | 
| <span data-ttu-id="fff27-124">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="fff27-124">OneDrive for Business</span></span>    | <span data-ttu-id="fff27-125">Speichergrenzwert von 1 TB pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="fff27-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="fff27-126">Unbegrenzt</span><span class="sxs-lookup"><span data-stu-id="fff27-126">Unlimited</span></span> | 
| <span data-ttu-id="fff27-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="fff27-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Office 365 E3 enthalten](../media/check-mark.png) | 
| <span data-ttu-id="fff27-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="fff27-130">StaffHub</span></span>    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Office 365 E3 enthalten](../media/check-mark.png) | 
| <span data-ttu-id="fff27-133">MileIQ</span><span class="sxs-lookup"><span data-stu-id="fff27-133">MileIQ</span></span>    | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | | 
| <span data-ttu-id="fff27-135">**Bedrohungsschutz**</span><span class="sxs-lookup"><span data-stu-id="fff27-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="fff27-136">Microsoft Defender für Office 365 Plan 1</span><span class="sxs-lookup"><span data-stu-id="fff27-136">Defender for Office 365 Plan 1</span></span> | ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | <span data-ttu-id="fff27-138">Nicht enthalten, kann aber hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="fff27-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="fff27-139">**Identitätsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="fff27-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="fff27-140">Self-Service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span><span class="sxs-lookup"><span data-stu-id="fff27-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    |  | 
| <span data-ttu-id="fff27-142">**Verwaltung von Geräten und Apps**</span><span class="sxs-lookup"><span data-stu-id="fff27-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="fff27-143">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="fff27-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    |  |
| <span data-ttu-id="fff27-145">Aktivierung gemeinsam genutzter Computer</span><span class="sxs-lookup"><span data-stu-id="fff27-145">Shared computer activation</span></span>|     ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    | ![In Office 365 E3 enthalten](../media/check-mark.png)| 
| <span data-ttu-id="fff27-148">Upgraderechte auf Windows 10 Pro von Win 7/8.1 Pro-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="fff27-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)    || 
| <span data-ttu-id="fff27-150">**Schutz von Daten**</span><span class="sxs-lookup"><span data-stu-id="fff27-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="fff27-151">Verhinderung von Datenverlust in Office 365</span><span class="sxs-lookup"><span data-stu-id="fff27-151">Office 365 Data Loss Prevention</span></span>|    ![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)|![In Office 365 E3 enthalten](../media/check-mark.png)|
|<span data-ttu-id="fff27-154">Azure Information Protection Plan 1, BitLocker-Erzwingung</span><span class="sxs-lookup"><span data-stu-id="fff27-154">Azure Information Protection Plan 1, BitLocker enforcement</span></span>|![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)||
|<span data-ttu-id="fff27-156">Azure Information Protection Plan 1, Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="fff27-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![In Microsoft 365 Business Premium enthalten](../media/check-mark.png)||
|<span data-ttu-id="fff27-158">**Clientzugriffslizenz (CAL-Rechte)**</span><span class="sxs-lookup"><span data-stu-id="fff27-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="fff27-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="fff27-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![In Office 365 E3 enthalten](../media/check-mark.png)|

<span data-ttu-id="fff27-161"><sup>1</sup> Die Microsoft 365 Business Premium-Version der Office-Apps umfasst keine Volumenaktivierung über Gruppenrichtlinien, App-Telemetrie, Updatesteuerelemente, Tabellenkalkulationsvergleiche und -abfragen oder Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="fff27-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="fff27-162">Migration</span><span class="sxs-lookup"><span data-stu-id="fff27-162">Migration</span></span>

<span data-ttu-id="fff27-163">Anweisungen zum Migrieren [](../commerce/subscriptions/change-plans-manually.md) Ihres Abonnements finden Sie unter Manuelles Ändern von Plänen, wenn Sie nur wenige Personen zu Microsoft 365 Business Premium verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="fff27-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="fff27-164">Sie können auch [alle Benutzer automatisch aktualisieren](../commerce/subscriptions/upgrade-to-different-plan.md)oder mit einem Partner zusammenarbeiten, um Ihr E3-Abonnement und Ihre Lizenzen in ein Microsoft 365 Business Premium-Abonnement zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="fff27-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="fff27-165">In den folgenden Abschnitten werden die Änderungen beschrieben, die Sie gegebenenfalls vornehmen müssen, und was Sie nach der Migration tun können.</span><span class="sxs-lookup"><span data-stu-id="fff27-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="fff27-166">Office 365 E3-Abonnementkonfiguration und -daten</span><span class="sxs-lookup"><span data-stu-id="fff27-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="fff27-167">Sie müssen vor der Migration keine Änderungen an Ihrem aktuellen Abonnement oder Ihren Daten vornehmen. Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="fff27-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="fff27-168">Abonnementkonfiguration, z. B. DNS-Einträge und Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="fff27-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="fff27-169">Benutzer- und Gruppenkonten und Authentifizierungseinstellungen, z. B. mehrstufige Authentifizierung oder Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="fff27-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="fff27-170">Produktivitätsdienstkonfigurationen und deren Daten, z. B. Teams, Exchange Online-Postfächer, SharePoint #A0, OneDrive for #A1 und OneNote-Notizbücher.</span><span class="sxs-lookup"><span data-stu-id="fff27-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="fff27-171">Office-Anwendungen werden automatisch skaliert.</span><span class="sxs-lookup"><span data-stu-id="fff27-171">Office applications will scale automatically.</span></span> <span data-ttu-id="fff27-172">Moderne Office 365-Lizenzierung überprüft alle 72 Stunden die Lizenzzuweisung des Benutzers und konvertiert Office-Anwendungen in die Version, die dem Benutzerabonnement entspricht.</span><span class="sxs-lookup"><span data-stu-id="fff27-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="fff27-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="fff27-173">Windows 10</span></span>

<span data-ttu-id="fff27-174">Wenn Ihre Windows noch nicht unter Windows Pro Creator Update sind, aktualisieren Sie sie [auf Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="fff27-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="fff27-175">Einrichten von Richtlinien zum Schutz von Benutzergeräten und -dateien</span><span class="sxs-lookup"><span data-stu-id="fff27-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="fff27-176">Wenn Sie Office 365-MDM-Richtlinien und -Geräte einrichten, werden diese Geräte auf der Seite Geräte im Microsoft 365 Admin Center aufgeführt. </span><span class="sxs-lookup"><span data-stu-id="fff27-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="fff27-177">Alle von Ihnen eingerichteten Richtlinien werden in der Liste der klassischen Richtlinien im [Intune-Portal angezeigt.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)</span><span class="sxs-lookup"><span data-stu-id="fff27-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="fff27-178">Nachdem Sie Microsoft 365 Business Premium Lizenzen zugewiesen haben, können Sie mit dem Schutz der Geräte und Dateien der Benutzer beginnen.</span><span class="sxs-lookup"><span data-stu-id="fff27-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="fff27-179">Wenn Sie alle Benutzer in Ihrer Organisation auf Microsoft 365 Business Premium aktualisiert haben, wird der Setup-Assistent auf der Startseite angezeigt, und Sie können die Schritte zum Einrichten von [Microsoft 365 Business Premium in](set-up.md) den Schritten des Setup-Assistenten befolgen, um Dateien und mobile Geräte zu schützen.</span><span class="sxs-lookup"><span data-stu-id="fff27-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="fff27-180">Sie können die folgenden Schritte auch auf der Seite Geräte ausführen:</span><span class="sxs-lookup"><span data-stu-id="fff27-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="fff27-181">Wechseln Sie im Admin Center im  linken Navigations navi zu \> **Geräterichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="fff27-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="fff27-182">Wählen Sie **auf der Seite** Geräterichtlinien die Option Hinzufügen **aus.**</span><span class="sxs-lookup"><span data-stu-id="fff27-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="fff27-183">Geben Sie **der Richtlinie im** Bereich Richtlinie hinzufügen  einen Namen zu, und wählen Sie dann in der Dropdownliste einen Richtlinientyp aus.</span><span class="sxs-lookup"><span data-stu-id="fff27-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="fff27-184">Sie können Anwendungsrichtlinien zum Schutz von Dateien auf Android- und iPhone-Geräten sowie Windows 10 einrichten und Gerätekonfigurationsrichtlinien für Windows 10-Geräte im Besitz des Unternehmens einrichten.</span><span class="sxs-lookup"><span data-stu-id="fff27-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="fff27-185">Weitere Informationen finden Sie unter den folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="fff27-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="fff27-186">Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="fff27-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="fff27-187">Festlegen von Anwendungsschutzeinstellungen für Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="fff27-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="fff27-188">Festlegen von Geräteschutzeinstellungen für Windows 10-PCs</span><span class="sxs-lookup"><span data-stu-id="fff27-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="fff27-189">Nachdem Sie Richtlinien eingerichtet haben, können Sie und Ihre Mitarbeiter Geräte einrichten:</span><span class="sxs-lookup"><span data-stu-id="fff27-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="fff27-190">Schritte für Windows-Geräte finden Sie unter Einrichten von Windows-Geräten für [Microsoft 365 Business](set-up-windows-devices.md) Premium-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="fff27-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="fff27-191">Unter [Einrichten mobiler Geräte für Microsoft 365 Business Premium-Benutzer](set-up-mobile-devices.md) finden Sie Schritte für Android-Smartphones und iPhones.</span><span class="sxs-lookup"><span data-stu-id="fff27-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="fff27-192">Postfachgröße</span><span class="sxs-lookup"><span data-stu-id="fff27-192">Mailbox Size</span></span>

<span data-ttu-id="fff27-193">Microsoft 365 Business Premium verfügt bei Verwendung von Exchange Online Plan 1 über einen Speichergrenzwert von 50 GB.</span><span class="sxs-lookup"><span data-stu-id="fff27-193">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="fff27-194">Bei der Migration zu Microsoft 365 Business Premium wird empfohlen, diesem Benutzer einen Exchange Online Plan 2 zuzuordnen und den Exchange Online Plan 1 zu entfernen, da beides nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="fff27-194">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>


### <a name="threat-protection"></a><span data-ttu-id="fff27-195">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="fff27-195">Threat protection</span></span>

<span data-ttu-id="fff27-196">Nach der Migration zu Microsoft 365 Business Premium haben Sie Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="fff27-196">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="fff27-197">Eine [Übersicht finden Sie unter Microsoft Defender for Office 365.](../security/office-365-security/defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="fff27-197">See [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="fff27-198">Informationen zum Einrichten finden Sie [](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)unter [Einrichten sicherer Links,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)Einrichten sicherer Anlagen und Einrichten [von Antiphishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="fff27-198">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="fff27-199">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="fff27-199">Sensitivity labels</span></span>

<span data-ttu-id="fff27-200">Informationen zur Verwendung von Vertraulichkeitsbezeichnungen finden Sie unter Übersicht über [Vertraulichkeitsbezeichnungen](../compliance/sensitivity-labels.md) und [Erstellen und Verwalten von Vertraulichkeitsbezeichnungen.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)</span><span class="sxs-lookup"><span data-stu-id="fff27-200">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
