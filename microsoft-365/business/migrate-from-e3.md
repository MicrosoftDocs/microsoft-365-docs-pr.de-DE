---
title: Migrieren zu Microsoft 365 Business von Office 365 E3
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
ms.openlocfilehash: 5142038110cada6e1da77d405c82f119e0f9e4d3
ms.sourcegitcommit: 0fa897d06b664c0ed005817752da1426d4ee17cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "38002428"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a><span data-ttu-id="a4974-103">Migrieren von Office 365 E3 zu Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="a4974-103">Migrating from Office 365 E3 to Microsoft 365 Business</span></span> 

<span data-ttu-id="a4974-104">Microsoft 365 Business verfügt über alles, was Sie für Ihr kleines Unternehmen benötigen, und kombiniert die branchenbesten Cloud-basierten Produktivitäts-apps mit einfacher Geräteverwaltung und Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="a4974-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span>  <span data-ttu-id="a4974-105">Wenn Sie derzeit über ein Office 365 E3-Abonnement verfügen, aber nicht über mehr als 300 Mitarbeiter verfügen, sollten Sie zum Hinzufügen von Sicherheitsfeatures zu Microsoft 365 Business wechseln.</span><span class="sxs-lookup"><span data-stu-id="a4974-105">If you currently have an Office 365 E3 subscription, but don’t have more than 300 employees, consider switching to Microsoft 365 Business for added security features.</span></span>

<span data-ttu-id="a4974-106">Die Migration ist einfach: zuerst wechseln Sie die Lizenzen, und alle Ihre Daten und Benutzerinformationen in Ihrem aktuellen Abonnement werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a4974-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="a4974-107">Nach der Migration müssen Sie die Features einrichten, die in Microsoft 365 Business hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a4974-107">After the migration you will need to set up the features that are added in Microsoft 365 Business.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a><span data-ttu-id="a4974-108">Unterschiede zwischen Office 365 E3 und Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="a4974-108">Differences between Office 365 E3 and Microsoft 365 Business</span></span>

<span data-ttu-id="a4974-109">In dieser Tabelle sind die Unterschiede zwischen Microsoft 365 Business und Office 365 E3 aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a4974-109">This table shows the differences between Microsoft 365 Business and Office 365 E3.</span></span>

| <span data-ttu-id="a4974-110">Feature</span><span class="sxs-lookup"><span data-stu-id="a4974-110">Feature</span></span>   | <span data-ttu-id="a4974-111">Unterstützung in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="a4974-111">Support in Microsoft 365 Business</span></span> | <span data-ttu-id="a4974-112">Unterstützung in Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="a4974-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="a4974-113">**Lokal**</span><span class="sxs-lookup"><span data-stu-id="a4974-113">**On-premises**</span></span>       | | | 
| <span data-ttu-id="a4974-114">Office-Apps<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a4974-114">Office apps<sup>1</sup></span></span>   | <span data-ttu-id="a4974-115">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="a4974-115">Office 365 Business</span></span>   | <span data-ttu-id="a4974-116">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="a4974-116">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="a4974-117">**Apps für die Cloud-Produktivität**</span><span class="sxs-lookup"><span data-stu-id="a4974-117">**Cloud productivity apps**</span></span>       | | | 
| <span data-ttu-id="a4974-118">Exchange Online und Outlook</span><span class="sxs-lookup"><span data-stu-id="a4974-118">Exchange Online and Outlook</span></span>   | <span data-ttu-id="a4974-119">50 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online Archivierung</span><span class="sxs-lookup"><span data-stu-id="a4974-119">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>   | <span data-ttu-id="a4974-120">100 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online Archivierung</span><span class="sxs-lookup"><span data-stu-id="a4974-120">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="a4974-121">Teams</span><span class="sxs-lookup"><span data-stu-id="a4974-121">Teams</span></span> | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Office 365 E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="a4974-124">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="a4974-124">OneDrive for Business</span></span> | <span data-ttu-id="a4974-125">1 TB Speichergrenzwert pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="a4974-125">1 TB storage limit per user</span></span>   | <span data-ttu-id="a4974-126">Unbegrenzt</span><span class="sxs-lookup"><span data-stu-id="a4974-126">Unlimited</span></span> | 
| <span data-ttu-id="a4974-127">Jammern, SharePoint Online, Planer, Stream</span><span class="sxs-lookup"><span data-stu-id="a4974-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Office 365 E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="a4974-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="a4974-130">StaffHub</span></span>  | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Office 365 E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="a4974-133">Outlook-Kunden Manager, MileIQ</span><span class="sxs-lookup"><span data-stu-id="a4974-133">Outlook Customer Manager, MileIQ</span></span>  | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | | 
| <span data-ttu-id="a4974-135">**Bedrohungsschutz**</span><span class="sxs-lookup"><span data-stu-id="a4974-135">**Threat Protection**</span></span>     | | | 
| <span data-ttu-id="a4974-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span><span class="sxs-lookup"><span data-stu-id="a4974-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)  | <span data-ttu-id="a4974-138">Nicht enthalten, kann aber hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="a4974-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="a4974-139">**Identitätsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="a4974-139">**Identity management**</span></span>       | | | 
| <span data-ttu-id="a4974-140">Self-Service Password Reset für hybride Azure Active Directory (Azure AD)-Konten, Azure Multi-Factor Authentication (MFA), bedingter Zugriff, Kenn Wort Rückschreiben für lokale Identitäten</span><span class="sxs-lookup"><span data-stu-id="a4974-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|    ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png) |  | 
| <span data-ttu-id="a4974-142">**Geräte-und App-Verwaltung**</span><span class="sxs-lookup"><span data-stu-id="a4974-142">**Device and app management**</span></span>     | | |
| <span data-ttu-id="a4974-143">Microsoft InTune, Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="a4974-143">Microsoft Intune, Windows AutoPilot</span></span>|  ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png) |  |
| <span data-ttu-id="a4974-145">Aktivierung gemeinsam genutzter Computer</span><span class="sxs-lookup"><span data-stu-id="a4974-145">Shared computer activation</span></span>|   ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png) | ![Im Lieferumfang von Office 365 E3 enthalten](./media/check-mark.png)| 
| <span data-ttu-id="a4974-148">Aktualisieren von Rechten auf Windows 10 pro von Win 7/8.1 pro-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="a4974-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png) || 
| <span data-ttu-id="a4974-150">**Schutz von Daten**</span><span class="sxs-lookup"><span data-stu-id="a4974-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="a4974-151">Office 365 Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="a4974-151">Office 365 Data Loss Prevention</span></span>|   ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)|![Im Lieferumfang von Office 365 E3 enthalten](./media/check-mark.png)|
|<span data-ttu-id="a4974-154">Azure Information Protection Plan 1, BitLocker-Erzwingung</span><span class="sxs-lookup"><span data-stu-id="a4974-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)||
|<span data-ttu-id="a4974-156">Azure Information Protection-Plan 1, Sensitivitäts Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="a4974-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)||
|<span data-ttu-id="a4974-158">**Client Zugriffslizenz (CAL-Rechte)**</span><span class="sxs-lookup"><span data-stu-id="a4974-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="a4974-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="a4974-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Im Lieferumfang von Office 365 E3 enthalten](./media/check-mark.png)|

<span data-ttu-id="a4974-161"><sup>1</sup> die Microsoft 365 Business-Version der Office-Apps beinhalten keine Volumenaktivierung über Gruppenrichtlinien, App-Telemetrie, Update Steuerelemente, Kalkulationstabelle vergleichen und erkundigen sowie Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="a4974-161"><sup>1</sup> The Microsoft 365 Business version of the Office apps do not include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, and business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="a4974-162">Migration</span><span class="sxs-lookup"><span data-stu-id="a4974-162">Migration</span></span>

<span data-ttu-id="a4974-163">Informationen zum Migrieren Ihres Abonnements finden Sie unter [Wechseln zu einem anderen Plan manuell](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) für Anweisungen Wenn Sie nur einige wenige Personen in Microsoft 365 Business verschieben möchten, können Sie [jeden automatisch aktualisieren](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan)oder mit Partner zusammenarbeiten, um Ihre E3 zu verschieben. Abonnement und Lizenzen für ein Microsoft 365 Business-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="a4974-163">To migrate your subscription, see [switch to a different plan manually](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) for instructions if you want to move just a few people to Microsoft 365 Business, you can [upgrade everyone automatically](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan), or you can work with partner to move your E3 subscription and licenses to a Microsoft 365 Business subscription.</span></span>
<span data-ttu-id="a4974-164">In den folgenden Abschnitten wird beschrieben, welche Änderungen Sie vornehmen müssen, falls vorhanden, und was Sie nach der Migration tun können.</span><span class="sxs-lookup"><span data-stu-id="a4974-164">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="a4974-165">Office 365 E3-Abonnementkonfiguration und-Daten</span><span class="sxs-lookup"><span data-stu-id="a4974-165">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="a4974-166">Sie müssen vor der Migration keine Änderungen am aktuellen Abonnement oder an den Daten vornehmen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="a4974-166">You don’t need to do any changes to your current subscription or data prior to migrating, which includes:</span></span>

- <span data-ttu-id="a4974-167">Abonnementkonfiguration, wie DNS-Einträge und Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="a4974-167">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="a4974-168">Benutzer-und Gruppenkonten und Authentifizierungseinstellungen, beispielsweise mehrstufige Authentifizierung oder Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="a4974-168">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="a4974-169">Produktivitäts Dienstkonfigurationen und deren Daten wie Teams, Exchange Online Postfächern, SharePoint Online Websites, OneDrive für Unternehmen Ordnern und OneNote-Notizbüchern.</span><span class="sxs-lookup"><span data-stu-id="a4974-169">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

### <a name="windows-10"></a><span data-ttu-id="a4974-170">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a4974-170">Windows 10</span></span>

<span data-ttu-id="a4974-171">Wenn Ihre Windows-Version nicht bereits auf dem Windows pro Creator-Update installiert ist, müssen Sie [diese auf Windows pro Creators Update](upgrade-to-windows-pro-creators-update.md)aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a4974-171">If your Windows aren't already on Windows Pro Creator update, you will need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="a4974-172">Einrichten von Richtlinien zum Schutz von Benutzergeräten und-Dateien</span><span class="sxs-lookup"><span data-stu-id="a4974-172">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="a4974-173">Wenn Sie Office 365 MDM-Richtlinien und-Geräte einrichten, werden diese Geräte auf der Seite **Geräte** im Microsoft 365 Admin Center aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a4974-173">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a4974-174">Alle Richtlinien, die Sie einrichten, werden in der Liste der klassischen Richtlinien im [InTune-Portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4974-174">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="a4974-175">Nachdem Sie Microsoft 365 Business Lizenzen zugewiesen haben, können Sie mit dem Schutz der Geräte und Dateien der Benutzer beginnen.</span><span class="sxs-lookup"><span data-stu-id="a4974-175">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="a4974-176">Wenn Sie alle Benutzer in Ihrer Organisation auf Microsoft 365 Business aktualisiert haben, wird der Setup-Assistent auf der Startseite angezeigt, und Sie können die Schritte zum [Einrichten von Microsoft 365 Business im Setup-Assistenten](set-up.md) ausführen, um Dateien und mobile Geräte zu schützen.</span><span class="sxs-lookup"><span data-stu-id="a4974-176">If you upgraded everyone in your organization to Microsoft 365 Business, you will see the set up wizard on teh home page, and can follow the [Set up Microsoft 365 Business in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="a4974-177">Sie können diese Schritte auch auf der Seite Geräte ausführen:</span><span class="sxs-lookup"><span data-stu-id="a4974-177">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="a4974-178">Wechseln Sie im Admin Center im linken Navigationsbereich zu **Geräte** \> **Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="a4974-178">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="a4974-179">Klicken Sie auf der Seite **Geräterichtlinien** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a4974-179">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="a4974-180">Geben Sie im Bereich **Richtlinie hinzufügen** der Richtlinie einen Namen, und wählen Sie dann einen **Richtlinientyp** aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="a4974-180">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="a4974-181">Sie können Anwendungsrichtlinien zum Schützen von Dateien auf Android-und iPhone-Geräten sowie Windows 10 einrichten, und Sie können Geräte Konfigurationsrichtlinien für Windows 10-Geräte im Unternehmen einrichten.</span><span class="sxs-lookup"><span data-stu-id="a4974-181">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="a4974-182">Weitere Informationen finden Sie unter den folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="a4974-182">See the following links for details:</span></span>
    
  - [<span data-ttu-id="a4974-183">Festlegen von App-Schutzeinstellungen für Android-oder IOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="a4974-183">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="a4974-184">Festlegen von Anwendungsschutz Einstellungen für Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="a4974-184">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="a4974-185">Festlegen von Geräteschutz Einstellungen für Windows 10-PCs</span><span class="sxs-lookup"><span data-stu-id="a4974-185">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="a4974-186">Nachdem Sie Richtlinien eingerichtet haben, können Sie und ihre mitarbeitergeräte einrichten:</span><span class="sxs-lookup"><span data-stu-id="a4974-186">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="a4974-187">Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für Microsoft 365 Business Users](set-up-windows-devices.md) für Schritte für Windows-Geräte.</span><span class="sxs-lookup"><span data-stu-id="a4974-187">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="a4974-188">Weitere Informationen finden Sie unter [Einrichten von mobilen Geräten für Microsoft 365 Business-Benutzer](set-up-mobile-devices.md) für Schritte für Android-Telefone und iPhones.</span><span class="sxs-lookup"><span data-stu-id="a4974-188">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 

### <a name="threat-protection"></a><span data-ttu-id="a4974-189">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="a4974-189">Threat protection</span></span>

<span data-ttu-id="a4974-190">Nach der Migration zu Microsoft 365 Business haben Sie Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="a4974-190">After migrating to Microsoft 365 Business, you have Office 365 ATP.</span></span> <span data-ttu-id="a4974-191">Weitere Informationen finden Sie unter [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) für eine Übersicht und einrichten siehe [Einrichten von ATP-Sicherheits Links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), einrichten [von ATP-Tresoranlagen](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5) und [Einrichten von ATP-AntiPhishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="a4974-191">See [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview and to set up see [set up ATP safe links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP safe attachments](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5) and [set up ATP anti-phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="a4974-192">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="a4974-192">Sensitivity labels</span></span>

<span data-ttu-id="a4974-193">Informationen zur Verwendung von Sensitivitäts Bezeichnungen finden Sie unter [Übersicht über Sensitivitäts Bezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) und [Erstellen und Verwalten von Sensitivitäts Beschriftungen](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) (Video).</span><span class="sxs-lookup"><span data-stu-id="a4974-193">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
