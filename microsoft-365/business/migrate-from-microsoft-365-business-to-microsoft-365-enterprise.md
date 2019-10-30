---
title: Migrieren von Microsoft 365 Business zu Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Erfahren Sie, wie Sie Ihr Unternehmen von Microsoft 365 Business auf Microsoft 365 Enterprise E3 migrieren.
ms.openlocfilehash: efdf4030a2a638a3fd56d1c415fcc6e6ac261c1a
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772716"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-enterprise-e3"></a><span data-ttu-id="2cb70-103">Migrieren von Microsoft 365 Business zu Microsoft 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="2cb70-103">Migrate from Microsoft 365 Business to Microsoft 365 Enterprise E3</span></span>

<span data-ttu-id="2cb70-104">Microsoft 365 Business bietet alles, was Sie für Ihr kleines Unternehmen benötigen, und kombiniert die branchenbesten Cloud-basierten Produktivitäts-apps mit einfacher Geräteverwaltung und Sicherheit, mit denen Ihre Mitarbeiter ihre besten Aufgaben erledigen können.</span><span class="sxs-lookup"><span data-stu-id="2cb70-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="2cb70-105">In einigen Fällen müssen Sie jedoch möglicherweise Ihr Microsoft 365 Business-Abonnement zu Microsoft 365 Enterprise migrieren.</span><span class="sxs-lookup"><span data-stu-id="2cb70-105">In some cases, however, you may need to migrate your Microsoft 365 Business subscription to Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="2cb70-106">Beispielsweise ist Ihr Unternehmen gewachsen und benötigt mehr als 300 Lizenzen (Herzlichen Glückwunsch).</span><span class="sxs-lookup"><span data-stu-id="2cb70-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="2cb70-107">Oder Ihr Unternehmen benötigt Enterprise-Features wie Office 365 ProPlus, Windows 10 Enterprise E3 oder Enterprise-Client Zugriffs Lizenzen (CALs).</span><span class="sxs-lookup"><span data-stu-id="2cb70-107">Or, your business needs enterprise features, such as Office 365 ProPlus, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="2cb70-108">Die Migration ist ganz einfach: Wechseln Sie einfach Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="2cb70-108">Migrating is easy: Just switch licenses.</span></span> <span data-ttu-id="2cb70-109">Alle Ihre Daten und Konfigurationen in Ihrem aktuellen Abonnement werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2cb70-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="2cb70-110">Es gibt nichts, was Sie tun müssen, um die Migration vorzubereiten und danach nichts zu tun, außer nutzen Sie die neuen Features.</span><span class="sxs-lookup"><span data-stu-id="2cb70-110">There is nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span> 

>[!Note]
><span data-ttu-id="2cb70-111">Sie können auch ein Microsoft 365 Business-Abonnement für bis zu 300-Sitze verwenden und ein Microsoft 365 Enterprise E3-Abonnement für mehr als 300 Sitze erhalten.</span><span class="sxs-lookup"><span data-stu-id="2cb70-111">You can also use a Microsoft 365 Business subscription for up to 300 seats and get a Microsoft 365 Enterprise E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="2cb70-112">Office 365 ATP ist jedoch nicht in Microsoft 365 Enterprise E3 enthalten.</span><span class="sxs-lookup"><span data-stu-id="2cb70-112">However, Office 365 ATP is not included with Microsoft 365 Enterprise E3.</span></span> <span data-ttu-id="2cb70-113">Sie sollten weitere Office 365 ATP-Lizenzen für die Benutzer in Ihrem Microsoft 365 Enterprise E3-Abonnement hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2cb70-113">You should add additional Office 365 ATP licenses for the users in your Microsoft 365 Enterprise E3 subscription.</span></span>
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a><span data-ttu-id="2cb70-114">Unterschiede zwischen Microsoft 365 Business und Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2cb70-114">Differences between Microsoft 365 Business and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2cb70-115">In dieser Tabelle sind die Unterschiede zwischen Microsoft 365 Business und Microsoft 365 Enterprise E3 aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="2cb70-115">This table shows the differences between Microsoft 365 Business and Microsoft 365 Enterprise E3.</span></span>

| <span data-ttu-id="2cb70-116">Feature</span><span class="sxs-lookup"><span data-stu-id="2cb70-116">Feature</span></span>   | <span data-ttu-id="2cb70-117">Unterstützung in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="2cb70-117">Support in Microsoft 365 Business</span></span> | <span data-ttu-id="2cb70-118">Unterstützung in Microsoft 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="2cb70-118">Support in Microsoft 365 Enterprise E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="2cb70-119">**Lokal**</span><span class="sxs-lookup"><span data-stu-id="2cb70-119">**On-premises**</span></span>       | | | 
| <span data-ttu-id="2cb70-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2cb70-120">Windows 10</span></span>    | <span data-ttu-id="2cb70-121">Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="2cb70-121">Windows 10 Business</span></span>  |    <span data-ttu-id="2cb70-122">Windows 10 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="2cb70-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="2cb70-123">Office-Apps \*</span><span class="sxs-lookup"><span data-stu-id="2cb70-123">Office apps\*</span></span>  | [<span data-ttu-id="2cb70-124">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="2cb70-124">Office 365 Business</span></span>](#office-365-business)   | <span data-ttu-id="2cb70-125">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="2cb70-125">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="2cb70-126">**Apps für die Cloud-Produktivität**</span><span class="sxs-lookup"><span data-stu-id="2cb70-126">**Cloud productivity apps**</span></span>       | | | 
| <span data-ttu-id="2cb70-127">Exchange Online und Outlook</span><span class="sxs-lookup"><span data-stu-id="2cb70-127">Exchange Online and Outlook</span></span>   | <span data-ttu-id="2cb70-128">50 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online Archivierung</span><span class="sxs-lookup"><span data-stu-id="2cb70-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>   | <span data-ttu-id="2cb70-129">100 GB Speichergrenzwert pro Postfach und unbegrenzte Exchange Online Archivierung</span><span class="sxs-lookup"><span data-stu-id="2cb70-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="2cb70-130">Teams</span><span class="sxs-lookup"><span data-stu-id="2cb70-130">Teams</span></span> | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-133">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="2cb70-133">OneDrive for Business</span></span> | <span data-ttu-id="2cb70-134">1 TB Speichergrenzwert pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="2cb70-134">1 TB storage limit per user</span></span>   | <span data-ttu-id="2cb70-135">Unbegrenzt</span><span class="sxs-lookup"><span data-stu-id="2cb70-135">Unlimited</span></span> | 
| <span data-ttu-id="2cb70-136">Jammern, SharePoint Online, Planer, Stream</span><span class="sxs-lookup"><span data-stu-id="2cb70-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-139">StaffHub</span><span class="sxs-lookup"><span data-stu-id="2cb70-139">StaffHub</span></span>  | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-142">Outlook-Kunden Manager, MileIQ</span><span class="sxs-lookup"><span data-stu-id="2cb70-142">Outlook Customer Manager, MileIQ</span></span>  | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | | 
| <span data-ttu-id="2cb70-144">**Bedrohungsschutz**</span><span class="sxs-lookup"><span data-stu-id="2cb70-144">**Threat Protection**</span></span>     | | | 
| <span data-ttu-id="2cb70-145">Funktionen zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="2cb70-145">Attack surface reduction capabilities</span></span> | [<span data-ttu-id="2cb70-146">Siehe diese Liste</span><span class="sxs-lookup"><span data-stu-id="2cb70-146">See this list</span></span>](#threat-protection) | <span data-ttu-id="2cb70-147">Unternehmensverwaltung der hardwarebasierten Isolierung für Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2cb70-147">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="2cb70-148">Office 365 Advanced Threat Protection (ATP) Plan 1</span><span class="sxs-lookup"><span data-stu-id="2cb70-148">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)  | <span data-ttu-id="2cb70-150">Nicht enthalten, kann aber hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="2cb70-150">Not included, but can be added on</span></span> | 
| <span data-ttu-id="2cb70-151">**Identitätsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="2cb70-151">**Identity management**</span></span>       | | | 
| <span data-ttu-id="2cb70-152">Self-Service Password Reset für hybride Azure Active Directory (Azure AD)-Konten, Azure Multi-Factor Authentication (MFA), bedingter Zugriff, Kenn Wort Rückschreiben für lokale Identitäten</span><span class="sxs-lookup"><span data-stu-id="2cb70-152">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|    ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png) | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-155">Cloud-App-Ermittlung, Azure AD Connect-Integrität</span><span class="sxs-lookup"><span data-stu-id="2cb70-155">Cloud App Discovery, Azure AD Connect Health</span></span>  |   | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-157">Einmaliges Anmelden für Azure AD Office 365 Apps (SSO): 10 apps pro Benutzer (Galerie Saas-apps wie Salesforce) \*</span><span class="sxs-lookup"><span data-stu-id="2cb70-157">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png) | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-160">Azure AD Premium 1 SSO: No Limit (lokale Apps über Azure AD Anwendungs Proxy und nicht-Gallery-Apps mithilfe von Self-Service-APP-Integrations Vorlagen)</span><span class="sxs-lookup"><span data-stu-id="2cb70-160">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>  |   | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-162">**Geräte-und App-Verwaltung**</span><span class="sxs-lookup"><span data-stu-id="2cb70-162">**Device and app management**</span></span>     | | | 
| <span data-ttu-id="2cb70-163">Microsoft InTune, Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="2cb70-163">Microsoft Intune, Windows Autopilot</span></span>|  ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png) | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
|<span data-ttu-id="2cb70-166">Virtueller Desktop Zugriff (VDA)</span><span class="sxs-lookup"><span data-stu-id="2cb70-166">Virtual Desktop Access (VDA)</span></span>   |  |    ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
|<span data-ttu-id="2cb70-168">Virtueller Windows-Desktop (Oktober)</span><span class="sxs-lookup"><span data-stu-id="2cb70-168">Windows Virtual Desktop (WVD)</span></span>  | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png) |     ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
|<span data-ttu-id="2cb70-171">Freigegebene Computer Aktivierung (SCA)</span><span class="sxs-lookup"><span data-stu-id="2cb70-171">Shared Computer Activation (SCA)</span></span>   | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png) |     ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-174">Microsoft-Desktop Optimierungspaket</span><span class="sxs-lookup"><span data-stu-id="2cb70-174">Microsoft Desktop Optimization Package</span></span>    | |     ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-176">**Schutz von Daten**</span><span class="sxs-lookup"><span data-stu-id="2cb70-176">**Information protection**</span></span>        | | | 
| <span data-ttu-id="2cb70-177">Office 365 Verhinderung von Datenverlust, Azure Information Protection-Plan 1</span><span class="sxs-lookup"><span data-stu-id="2cb70-177">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>  | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-180">Schutz von Fenster Informationen für Endpunkt-DLP</span><span class="sxs-lookup"><span data-stu-id="2cb70-180">Window Information Protection for endpoint DLP</span></span>    | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-183">**Client Zugriffslizenz (CAL-Rechte)**</span><span class="sxs-lookup"><span data-stu-id="2cb70-183">**Client Access License (CAL rights)**</span></span>    | | |   
| <span data-ttu-id="2cb70-184">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, System Center Configuration Manager, Windows Rights Management)</span><span class="sxs-lookup"><span data-stu-id="2cb70-184">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, System Center Configuration Manager, Windows Rights Management)</span></span>| |        ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-186">**Compliance**</span><span class="sxs-lookup"><span data-stu-id="2cb70-186">**Compliance**</span></span>        | | | 
| <span data-ttu-id="2cb70-187">Unbegrenzte e-Mail-Archivierung</span><span class="sxs-lookup"><span data-stu-id="2cb70-187">Unlimited email archiving</span></span> | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-190">Compliance-Manager</span><span class="sxs-lookup"><span data-stu-id="2cb70-190">Compliance Manager</span></span>    | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-193">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2cb70-193">eDiscovery</span></span>    | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-196">Compliance-Aufbewahrungs-und Beweissicherungsverfahren</span><span class="sxs-lookup"><span data-stu-id="2cb70-196">In-place hold and litigation hold</span></span> | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
| <span data-ttu-id="2cb70-199">Aufbewahrungstags und Aufbewahrungsrichtlinien für die Messaging-Datensatzverwaltung</span><span class="sxs-lookup"><span data-stu-id="2cb70-199">Messaging Records Management (MRM) retention tags and retention policies</span></span>  | ![Im Lieferumfang von Microsoft 365 Business enthalten](./media/check-mark.png)   | ![Im Lieferumfang von Microsoft 365 Enterprise E3 enthalten](./media/check-mark.png) | 
||||

<span data-ttu-id="2cb70-202">\*Benutzer, denen Zugriff auf Saas-apps zugewiesen wurde, können SSO-Zugriff auf bis zu 10 apps erhalten.</span><span class="sxs-lookup"><span data-stu-id="2cb70-202">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="2cb70-203">Administratoren können SSO konfigurieren und den Benutzer Zugriff auf verschiedene Saas-apps ändern, aber SSO-Zugriff ist nur für 10 apps pro Benutzer gleichzeitig zulässig.</span><span class="sxs-lookup"><span data-stu-id="2cb70-203">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="2cb70-204">Alle Office 365 apps werden als einzelne APP gezählt.</span><span class="sxs-lookup"><span data-stu-id="2cb70-204">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="2cb70-205">Migration</span><span class="sxs-lookup"><span data-stu-id="2cb70-205">Migration</span></span>

<span data-ttu-id="2cb70-206">Um zu migrieren, arbeiten Sie mit Ihrem Partner zusammen, um Ihr Microsoft 365 Business-Abonnement und ihre Lizenzen auf ein geeignetes Microsoft 365 Enterprise E3-Abonnement mit seinen Lizenzen zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="2cb70-206">To migrate, work with your partner to move your Microsoft 365 Business subscription and licenses to suitable a Microsoft 365 Enterprise E3 subscription with its licenses.</span></span>

<span data-ttu-id="2cb70-207">In den folgenden Abschnitten wird beschrieben, welche Änderungen Sie vornehmen müssen, falls vorhanden, und was Sie nach der Migration tun können.</span><span class="sxs-lookup"><span data-stu-id="2cb70-207">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="2cb70-208">Microsoft 365-Abonnementkonfiguration und-Daten</span><span class="sxs-lookup"><span data-stu-id="2cb70-208">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="2cb70-209">Sie müssen vor der Migration keine Änderungen am aktuellen Abonnement oder an den Daten vornehmen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="2cb70-209">You don’t need to do any changes to your current subscription or data prior to migrating, which includes:</span></span>

- <span data-ttu-id="2cb70-210">Abonnementkonfiguration, wie DNS-Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="2cb70-210">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="2cb70-211">Benutzer-und Gruppenkonten und Authentifizierungseinstellungen, beispielsweise mehrstufige Authentifizierung oder Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="2cb70-211">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="2cb70-212">Produktivitäts Dienstkonfigurationen und deren Daten wie Teams, Exchange Online Postfächern, SharePoint Online Websites, OneDrive für Unternehmen Ordnern und OneNote-Notizbüchern.</span><span class="sxs-lookup"><span data-stu-id="2cb70-212">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="2cb70-213">Ihre Benutzer können jetzt unbegrenzten Speicherplatz in den Exchange Online Postfächern und OneDrive für Unternehmen Ordnern genießen.</span><span class="sxs-lookup"><span data-stu-id="2cb70-213">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="2cb70-214">Sie können mit der Verwendung der Cloud-App-Ermittlung, Azure AD Connect-Integrität und SSO für mehr als 10 apps beginnen.</span><span class="sxs-lookup"><span data-stu-id="2cb70-214">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

>[!Note]
><span data-ttu-id="2cb70-215">Nach der Migration zu Microsoft 365 Enterprise E3 sind Sie nicht mehr Outlook-Kunden Manager und MileIQ.</span><span class="sxs-lookup"><span data-stu-id="2cb70-215">After migrating to Microsoft 365 Enterprise E3, you no longer Outlook Customer Manager and MileIQ.</span></span>
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="2cb70-216">Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="2cb70-216">Threat protection</span></span>

<span data-ttu-id="2cb70-217">Windows 10 Business umfasst diese Schutzfunktionen:</span><span class="sxs-lookup"><span data-stu-id="2cb70-217">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="2cb70-218">Integritäts Erzwingung des Betriebssystem-Startvorgangs</span><span class="sxs-lookup"><span data-stu-id="2cb70-218">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="2cb70-219">Integritäts Erzwingung von vertraulichen Betriebskomponenten</span><span class="sxs-lookup"><span data-stu-id="2cb70-219">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="2cb70-220">Erweiterte Sicherheitsanfälligkeit und Zero-Day-Exploits zur Schadensminimierung</span><span class="sxs-lookup"><span data-stu-id="2cb70-220">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="2cb70-221">Reputations basierter Netzwerkschutz für Microsoft Edge, Internet Explorer und Chrome</span><span class="sxs-lookup"><span data-stu-id="2cb70-221">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="2cb70-222">Host basierte Firewall</span><span class="sxs-lookup"><span data-stu-id="2cb70-222">Host-based firewall</span></span>
- <span data-ttu-id="2cb70-223">Ransomware-Abhilfemaßnahmen</span><span class="sxs-lookup"><span data-stu-id="2cb70-223">Ransomware mitigations</span></span>
- <span data-ttu-id="2cb70-224">Hardware basierte Isolierung für Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2cb70-224">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="2cb70-225">Mit dem intelligenten Sicherheits Diagramm unterstützte Anwendungssteuerung</span><span class="sxs-lookup"><span data-stu-id="2cb70-225">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="2cb70-226">Gerätesteuerung (USB)</span><span class="sxs-lookup"><span data-stu-id="2cb70-226">Device control (USB)</span></span>
- <span data-ttu-id="2cb70-227">Netzwerkschutz für webbasierte Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="2cb70-227">Network protection for web-based threats</span></span>
- <span data-ttu-id="2cb70-228">Host Intrusion Prevention-Regeln</span><span class="sxs-lookup"><span data-stu-id="2cb70-228">Host intrusion prevention rules</span></span>

<span data-ttu-id="2cb70-229">Windows 10 Enterprise E3 umfasst auch die Unternehmensverwaltung der hardwarebasierten Isolierung für Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="2cb70-229">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="2cb70-230">Nach der Migration zu Microsoft 365 Enterprise E3 haben Sie Office 365 ATP nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="2cb70-230">After migrating to Microsoft 365 Enterprise E3, you no longer have Office 365 ATP.</span></span> <span data-ttu-id="2cb70-231">Sie können zusätzliche Office 365 ATP-Lizenzen für Ihr Microsoft 365 Enterprise E3-Abonnement erwerben und Sie Ihren Benutzerkonten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2cb70-231">You can purchase additional Office 365 ATP licenses for your Microsoft 365 Enterprise E3 subscription and assign them to your user accounts.</span></span>
>

### <a name="device-management-with-intune"></a><span data-ttu-id="2cb70-232">Geräteverwaltung mit InTune</span><span class="sxs-lookup"><span data-stu-id="2cb70-232">Device management with Intune</span></span>

<span data-ttu-id="2cb70-233">Vor der Migration müssen Sie keine Änderungen an Ihrer aktuellen InTune-Konfiguration vornehmen, einschließlich der registrierten Geräte und Geräte-und App-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="2cb70-233">You don’t need to do any changes to your current Intune configuration prior to migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="2cb70-234">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2cb70-234">Windows 10</span></span>

<span data-ttu-id="2cb70-235">Microsoft 365 Business umfasst Windows 10 Business, das Sie mit Windows Autopilot installieren können.</span><span class="sxs-lookup"><span data-stu-id="2cb70-235">Microsoft 365 Business includes Windows 10 Business, which you can install with Windows Autopilot.</span></span> <span data-ttu-id="2cb70-236">Wenn Sie zu Microsoft 365 Enterprise E3 migrieren, enthält jede Benutzerlizenz Windows 10 Enterprise E3, das Sie auch mit Windows Autopilot installieren können.</span><span class="sxs-lookup"><span data-stu-id="2cb70-236">When you migrate to Microsoft 365 Enterprise E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
### <a name="office-365-business"></a><span data-ttu-id="2cb70-237">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="2cb70-237">Office 365 Business</span></span>

<span data-ttu-id="2cb70-238">Der auf Ihren Geräten installierte Office 365 Business-Client beginnt automatisch mit der Verwendung der Features von Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="2cb70-238">Your Office 365 Business client installed on your devices will automatically begin to use the features of Office 365 ProPlus.</span></span> <span data-ttu-id="2cb70-239">Nach der Migration können Sie nun Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="2cb70-239">After migration, you can now use:</span></span>

 - <span data-ttu-id="2cb70-240">Volumenaktivierung über Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2cb70-240">Volume activation through Group Policy</span></span>
 - <span data-ttu-id="2cb70-241">App-Telemetrie</span><span class="sxs-lookup"><span data-stu-id="2cb70-241">App telemetry</span></span>
 - <span data-ttu-id="2cb70-242">Aktualisieren von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="2cb70-242">Update controls</span></span>
 - <span data-ttu-id="2cb70-243">Kalkulationstabelle vergleichen und Abfragen</span><span class="sxs-lookup"><span data-stu-id="2cb70-243">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="2cb70-244">Business intelligence</span><span class="sxs-lookup"><span data-stu-id="2cb70-244">Business intelligence</span></span>

