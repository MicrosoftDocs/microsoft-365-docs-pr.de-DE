---
title: Migrieren zu Microsoft 365 Business von Office 365 E3
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
description: Informationen zum Migrieren Ihres Unternehmens zu Microsoft 365 Business von Office 365 E3.
ms.openlocfilehash: 210f3ebf76da49349dfb6d61d0b8ce88d15d3734
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593704"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a><span data-ttu-id="7b523-103">Migrieren von Office 365 E3 zu Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="7b523-103">Migrating from Office 365 E3 to Microsoft 365 Business</span></span> 

<span data-ttu-id="7b523-104">Microsoft 365 Business verfügt über alles, was Sie für Ihr kleines Unternehmen benötigen, und kombiniert die branchenbesten Cloud-basierten Produktivitäts-apps mit einfacher Geräteverwaltung und Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="7b523-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="7b523-105">Wenn Sie derzeit über ein Office 365 E3-Abonnement verfügen, aber nicht über mehr als 300 Mitarbeiter verfügen, sollten Sie zum Hinzufügen von Sicherheitsfeatures zu Microsoft 365 Business wechseln.</span><span class="sxs-lookup"><span data-stu-id="7b523-105">If you currently have an Office 365 E3 subscription, but don’t have more than 300 employees, consider switching to Microsoft 365 Business for added security features.</span></span>

<span data-ttu-id="7b523-106">Die Migration ist einfach: zuerst wechseln Sie die Lizenzen, und alle Ihre Daten und Benutzerinformationen in Ihrem aktuellen Abonnement werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="7b523-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="7b523-107">Nach der Migration müssen Sie die Features einrichten, die in Microsoft 365 Business hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7b523-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a><span data-ttu-id="7b523-108">Unterschiede zwischen Office 365 E3 und Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="7b523-108">Differences between Office 365 E3 and Microsoft 365 Business</span></span>

<span data-ttu-id="7b523-109">In dieser Tabelle sind die Unterschiede zwischen Microsoft 365 Business und Office 365 E3 aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7b523-109">This table shows the differences between Microsoft 365 Business and Office 365 E3.</span></span>

| <span data-ttu-id="7b523-110">Feature</span><span class="sxs-lookup"><span data-stu-id="7b523-110">Feature</span></span>   | <span data-ttu-id="7b523-111">Unterstützung in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="7b523-111">Support in Microsoft 365 Business</span></span> | <span data-ttu-id="7b523-112">Unterstützung in Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="7b523-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="7b523-113">**Lokal**</span><span class="sxs-lookup"><span data-stu-id="7b523-113">**On-premises**</span></span>       | | | 
| <span data-ttu-id="7b523-114">Office-Apps<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7b523-114">Office apps<sup>1</sup></span></span>   | <span data-ttu-id="7b523-115">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="7b523-115">Office 365 Business</span></span>   | <span data-ttu-id="7b523-116">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="7b523-116">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="7b523-117">**Apps für die Cloud-Produktivität**</span><span class="sxs-lookup"><span data-stu-id="7b523-117">**Cloud productivity apps**</span></span>       | | | 
| <span data-ttu-id="7b523-118">Exchange Online und Outlook</span><span class="sxs-lookup"><span data-stu-id="7b523-118">Exchange Online and Outlook</span></span>   | <span data-ttu-id="7b523-119">50 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online Archivierung</span><span class="sxs-lookup"><span data-stu-id="7b523-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>   | <span data-ttu-id="7b523-120">100 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online Archivierung</span><span class="sxs-lookup"><span data-stu-id="7b523-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="7b523-121">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7b523-121">Teams</span></span> | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Office 365 E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="7b523-124">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="7b523-124">OneDrive for Business</span></span> | <span data-ttu-id="7b523-125">1 TB Speichergrenzwert pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="7b523-125">1 TB storage limit per user</span></span>   | <span data-ttu-id="7b523-126">Unbegrenzt</span><span class="sxs-lookup"><span data-stu-id="7b523-126">Unlimited</span></span> | 
| <span data-ttu-id="7b523-127">Jammern, SharePoint Online, Planer, Stream</span><span class="sxs-lookup"><span data-stu-id="7b523-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Office 365 E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="7b523-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="7b523-130">StaffHub</span></span>  | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Office 365 E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="7b523-133">Outlook-Kunden Manager, MileIQ</span><span class="sxs-lookup"><span data-stu-id="7b523-133">Outlook Customer Manager, MileIQ</span></span>  | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | | 
| <span data-ttu-id="7b523-135">**Bedrohungsschutz**</span><span class="sxs-lookup"><span data-stu-id="7b523-135">**Threat Protection**</span></span>     | | | 
| <span data-ttu-id="7b523-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span><span class="sxs-lookup"><span data-stu-id="7b523-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)  | <span data-ttu-id="7b523-138">Nicht enthalten, kann aber hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="7b523-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="7b523-139">**Identitätsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="7b523-139">**Identity management**</span></span>       | | | 
| <span data-ttu-id="7b523-140">Self-Service Password Reset für hybride Azure Active Directory (Azure AD)-Konten, Azure Multi-Factor Authentication (MFA), bedingter Zugriff, Kenn Wort Rückschreiben für lokale Identitäten</span><span class="sxs-lookup"><span data-stu-id="7b523-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|    ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png) |  | 
| <span data-ttu-id="7b523-142">**Geräte-und App-Verwaltung**</span><span class="sxs-lookup"><span data-stu-id="7b523-142">**Device and app management**</span></span>     | | |
| <span data-ttu-id="7b523-143">Microsoft InTune, Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="7b523-143">Microsoft Intune, Windows AutoPilot</span></span>|  ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png) |  |
| <span data-ttu-id="7b523-145">Aktivierung gemeinsam genutzter Computer</span><span class="sxs-lookup"><span data-stu-id="7b523-145">Shared computer activation</span></span>|   ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png) | ![Im Lieferumfang von Office 365 E3 enthalten](./media/check-mark.png)| 
| <span data-ttu-id="7b523-148">Aktualisieren von Rechten auf Windows 10 pro von Win 7/8.1 pro-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="7b523-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png) || 
| <span data-ttu-id="7b523-150">**Schutz von Daten**</span><span class="sxs-lookup"><span data-stu-id="7b523-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="7b523-151">Verhinderung von Datenverlust in Office 365</span><span class="sxs-lookup"><span data-stu-id="7b523-151">Office 365 Data Loss Prevention</span></span>|   ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)|![Im Lieferumfang von Office 365 E3 enthalten](./media/check-mark.png)|
|<span data-ttu-id="7b523-154">Azure Information Protection Plan 1, BitLocker-Erzwingung</span><span class="sxs-lookup"><span data-stu-id="7b523-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)||
|<span data-ttu-id="7b523-156">Azure Information Protection-Plan 1, Sensitivitäts Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="7b523-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)||
|<span data-ttu-id="7b523-158">**Client Zugriffslizenz (CAL-Rechte)**</span><span class="sxs-lookup"><span data-stu-id="7b523-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="7b523-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="7b523-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Im Lieferumfang von Office 365 E3 enthalten](./media/check-mark.png)|

<span data-ttu-id="7b523-161"><sup>1</sup> die Microsoft 365 Business-Version der Office-Apps umfasst keine Volumenaktivierung über Gruppenrichtlinien, App-Telemetrie, Update Steuerelemente, Arbeitsblatt Vergleich und erkundigen oder Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="7b523-161"><sup>1</sup> The Microsoft 365 Business version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="7b523-162">Migration</span><span class="sxs-lookup"><span data-stu-id="7b523-162">Migration</span></span>

<span data-ttu-id="7b523-163">Informationen zum Migrieren Ihres Abonnements finden Sie unter [Wechseln zu einem anderen Plan manuell](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) , um Anweisungen zu erhalten, wenn Sie nur einige wenige Personen zu Microsoft 365 Business verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="7b523-163">To migrate your subscription, see [switch to a different plan manually](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) for instructions if you want to move just a few people to Microsoft 365 Business.</span></span> <span data-ttu-id="7b523-164">Sie können auch [alle automatisch aktualisieren](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan)oder mit Partner zusammenarbeiten, um Ihr E3-Abonnement und ihre Lizenzen in ein Microsoft 365 Business-Abonnement zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="7b523-164">You can also [upgrade everyone automatically](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan), or work with partner to move your E3 subscription and licenses to a Microsoft 365 Business subscription.</span></span>
<span data-ttu-id="7b523-165">In den folgenden Abschnitten werden die Änderungen beschrieben, die Sie vornehmen müssen, falls vorhanden, und was Sie nach der Migration tun können.</span><span class="sxs-lookup"><span data-stu-id="7b523-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="7b523-166">Office 365 E3-Abonnementkonfiguration und-Daten</span><span class="sxs-lookup"><span data-stu-id="7b523-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="7b523-167">Sie müssen keine Änderungen am aktuellen Abonnement oder an den Daten vor der Migration vornehmen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="7b523-167">You don’t need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="7b523-168">Abonnementkonfiguration, wie DNS-Einträge und Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="7b523-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="7b523-169">Benutzer-und Gruppenkonten und Authentifizierungseinstellungen, beispielsweise mehrstufige Authentifizierung oder Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="7b523-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="7b523-170">Produktivitäts Dienstkonfigurationen und deren Daten wie Teams, Exchange Online Postfächern, SharePoint Online Websites, OneDrive für Unternehmen Ordnern und OneNote-Notizbüchern.</span><span class="sxs-lookup"><span data-stu-id="7b523-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

### <a name="windows-10"></a><span data-ttu-id="7b523-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7b523-171">Windows 10</span></span>

<span data-ttu-id="7b523-172">Wenn sich Ihre Windows-Version nicht bereits auf dem Windows pro Creator-Update befindet, führen [Sie ein Upgrade auf Windows pro Creators Update durch](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="7b523-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="7b523-173">Einrichten von Richtlinien zum Schutz von Benutzergeräten und-Dateien</span><span class="sxs-lookup"><span data-stu-id="7b523-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="7b523-174">Wenn Sie Office 365 MDM-Richtlinien und-Geräte einrichten, werden diese Geräte auf der Seite **Geräte** im Microsoft 365 Admin Center aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7b523-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7b523-175">Alle Richtlinien, die Sie einrichten, werden in der Liste der klassischen Richtlinien im [InTune-Portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7b523-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="7b523-176">Nachdem Sie Microsoft 365 Business Lizenzen zugewiesen haben, können Sie mit dem Schutz der Geräte und Dateien der Benutzer beginnen.</span><span class="sxs-lookup"><span data-stu-id="7b523-176">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="7b523-177">Wenn Sie alle in Ihrer Organisation auf Microsoft 365 Business aktualisiert haben, wird der Setup-Assistent auf der Startseite angezeigt, und Sie können die Schritte zum [Einrichten von Microsoft 365 Business im Setup-Assistenten](set-up.md) ausführen, um Dateien und mobile Geräte zu schützen.</span><span class="sxs-lookup"><span data-stu-id="7b523-177">If you upgraded everyone in your organization to Microsoft 365 Business, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="7b523-178">Sie können diese Schritte auch auf der Seite Geräte ausführen:</span><span class="sxs-lookup"><span data-stu-id="7b523-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="7b523-179">Wechseln Sie im Admin Center im linken Navigationsbereich zu **Geräte** \> **Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="7b523-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="7b523-180">Klicken Sie auf der Seite **Geräterichtlinien** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7b523-180">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="7b523-181">Geben Sie im Bereich **Richtlinie hinzufügen** der Richtlinie einen Namen, und wählen Sie dann einen **Richtlinientyp** aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="7b523-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="7b523-182">Sie können Anwendungsrichtlinien zum Schützen von Dateien auf Android-und iPhone-Geräten sowie Windows 10 einrichten, und Sie können Geräte Konfigurationsrichtlinien für Windows 10-Geräte im Unternehmen einrichten.</span><span class="sxs-lookup"><span data-stu-id="7b523-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="7b523-183">Weitere Informationen finden Sie unter den folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="7b523-183">See the following links for details:</span></span>
    
  - [<span data-ttu-id="7b523-184">Festlegen von App-Schutzeinstellungen für Android-oder IOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="7b523-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="7b523-185">Festlegen von Anwendungsschutz Einstellungen für Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="7b523-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="7b523-186">Festlegen von Geräteschutz Einstellungen für Windows 10-PCs</span><span class="sxs-lookup"><span data-stu-id="7b523-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="7b523-187">Nachdem Sie Richtlinien eingerichtet haben, können Sie und ihre mitarbeitergeräte einrichten:</span><span class="sxs-lookup"><span data-stu-id="7b523-187">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="7b523-188">Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für Microsoft 365 Business Users](set-up-windows-devices.md) für Schritte für Windows-Geräte.</span><span class="sxs-lookup"><span data-stu-id="7b523-188">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="7b523-189">Weitere Informationen finden Sie unter [Einrichten von mobilen Geräten für Microsoft 365 Business-Benutzer](set-up-mobile-devices.md) für Schritte für Android-Telefone und iPhones.</span><span class="sxs-lookup"><span data-stu-id="7b523-189">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 

### <a name="threat-protection"></a><span data-ttu-id="7b523-190">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="7b523-190">Threat protection</span></span>

<span data-ttu-id="7b523-191">Nach der Migration zu Microsoft 365 Business haben Sie Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="7b523-191">After migrating to Microsoft 365 Business, you have Office 365 ATP.</span></span> <span data-ttu-id="7b523-192">Eine Übersicht finden Sie unter [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) .</span><span class="sxs-lookup"><span data-stu-id="7b523-192">See [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview.</span></span> <span data-ttu-id="7b523-193">Informationen zum Einrichten finden Sie unter [Einrichten von ATP-Safe-Links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), einrichten [von ATP-Tresoranlagen](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)und [Einrichten von ATP-Anti-Phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="7b523-193">To set up, see [set up ATP safe links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP safe attachments](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up ATP anti-phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="7b523-194">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="7b523-194">Sensitivity labels</span></span>

<span data-ttu-id="7b523-195">Informationen zur Verwendung von Sensitivitäts Bezeichnungen finden Sie unter [Übersicht über Sensitivitäts Bezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) und [Erstellen und Verwalten von Sensitivitäts Beschriftungen](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) (Video).</span><span class="sxs-lookup"><span data-stu-id="7b523-195">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
