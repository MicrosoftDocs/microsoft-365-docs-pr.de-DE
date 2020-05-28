---
title: Festlegen der Kennwortablaufrichtlinie für Ihre Organisation
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Hier erfahren Sie, wie Sie im Microsoft 365 Admin Center eine Richtlinie für den Kennwortablauf für Ihre Organisation festlegen. '
ms.openlocfilehash: a4d5f5240a6d4cca686b4809d05970b5e18b897f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399578"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="6a2d0-103">Festlegen der Kennwortablaufrichtlinie für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="6a2d0-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6a2d0-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-104">The admin center is changing.</span></span> <span data-ttu-id="6a2d0-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="6a2d0-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="6a2d0-106">Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-106">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span>  

<span data-ttu-id="6a2d0-107">Wenn Sie ein Benutzer sind, haben Sie nicht die Berechtigungen, um Ihr Kennwort so festzulegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-107">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="6a2d0-108">Bitten Sie den technischen Support Ihres Unternehmens bzw. der Schule/Uni, die Schritte in diesem Artikel für Sie durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-108">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="6a2d0-109">Als Administrator können Sie festlegen, dass Benutzerkennwörter nach einer bestimmten Anzahl von Tagen oder nie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-109">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> 

> [!Tip]
> <span data-ttu-id="6a2d0-110">Standardmäßig ist für Kennwörter festgelegt, dass sie in 90 Tagen ablaufen.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-110">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="6a2d0-111">Aktuelle Untersuchungen weisen nachdrücklich darauf hin, dass erzwungene Kennwortänderungen mehr Schaden anrichten als sinnvoll sind.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-111">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="6a2d0-112">Sie treiben Benutzer dazu, schwächere Kennwörter zu wählen, Kennwörter wiederzuverwenden oder alte Kennwörter in einer Weise zu aktualisieren, die von Hackern leicht erraten werden kann.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-112">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="6a2d0-113">Wenn Sie festlegen, dass das Kennwort niemals abläuft, empfehlen wir die Aktivierung [mehrstufigen Authentifizierung](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="6a2d0-113">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="6a2d0-114">Führen Sie die folgenden Schritte aus, wenn Sie festlegen möchten, dass Benutzerkennwörter nach einer bestimmten Zeit ablaufen.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-114">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="6a2d0-115">Nur [globale Administratoren](../add-users/about-admin-roles.md) können diese Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-115">Only [global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="6a2d0-116">Wechseln Sie im Admin Center zu **Einstellungen** \> **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-116">In the admin center, go to the **Settings** \> **Settings**.</span></span>

2. <span data-ttu-id="6a2d0-117">Wechseln Sie zur Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Sicherheit & Datenschutz</a>.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-117">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="6a2d0-118">Wenn Sie kein globaler Administrator sind, wird die Option "Sicherheit und Datenschutz" nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-118">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="6a2d0-119">Wählen Sie **Kennwortablaufrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-119">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="6a2d0-120">Wenn Sie nicht möchten, dass die Benutzer ihre Kennwörter ändern müssen, aktivieren Sie das Kontrollkästchen neben **Festlegen, dass Benutzerkennwörter nach einer Anzahl von Tagen ablaufen**.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-120">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="6a2d0-121">Geben Sie ein, wie oft Kennwörter ablaufen sollen.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-121">Type how often passwords should expire.</span></span> <span data-ttu-id="6a2d0-122">Wählen Sie eine Anzahl von Tagen zwischen 14 und 730.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-122">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="6a2d0-123">Geben Sie im zweiten Feld ein, wann die Benutzer über den Ablauf ihres Kennworts informiert werden sollen, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-123">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="6a2d0-124">Wählen Sie eine Anzahl von Tagen zwischen 1 und 30 aus.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-124">Choose a number of days from 1 to 30.</span></span>
    
7. <span data-ttu-id="6a2d0-125">Wenn das Kennwort des Benutzers abläuft, erhält er eine Benachrichtigung, die in der unteren rechten Ecke des Bildschirms angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-125">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="6a2d0-126">Wichtige Informationen über das Feature zum Ablauf von Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="6a2d0-126">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="6a2d0-127">Hier finden Sie einige wichtige Informationen darüber, wie dieses Feature ab Januar 2018 funktioniert:</span><span class="sxs-lookup"><span data-stu-id="6a2d0-127">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="6a2d0-p107">Personen, die nur die Outlook-App verwenden, werden nicht gezwungen, ihr Microsoft 365-Kennwort zurückzusetzen, bis es im Cache abläuft. Dies kann mehrere Tage nach dem tatsächlichen Ablaufdatum sein. Es gibt keine Problemumgehung für dieses Problem auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-p107">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>
    
- <span data-ttu-id="6a2d0-p108">Benutzer erhalten keine E-Mail-Benachrichtigung, die sie darauf hinweist, dass ihr Kennwort in x Tagen abläuft. Möchten Sie dieses Feature verwenden? **[Stimmen Sie hier ab!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="6a2d0-p108">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>
    
## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="6a2d0-134">Verhindern, dass das letzte Kennwort erneut verwendet wird</span><span class="sxs-lookup"><span data-stu-id="6a2d0-134">Prevent last password from being used again</span></span>

<span data-ttu-id="6a2d0-135">Wenn Sie Ihre Benutzer daran hindern möchten, alte Kennwörter wiederzuverwenden, können Sie das in Azure AD erledigen.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-135">If you want to prevent your users from recycling old passwords, you can do so in Azure AD.</span></span> <span data-ttu-id="6a2d0-136">Siehe [Kennwortverlauf erzwingen](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history).</span><span class="sxs-lookup"><span data-stu-id="6a2d0-136">See [Enforce password history](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history).</span></span>

<span data-ttu-id="6a2d0-137">Wenn ein Mitarbeiter ein mobiles Gerät für den Zugriff auf Microsoft 365 verwendet hat, können Sie dieses auch zurücksetzen, um sicherzustellen, dass das Kennwort nicht mehr gespeichert und von dort wiederverwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-137">In addition, if an employee used a mobile device to access Microsoft 365, you can wipe it to ensure the password is no longer stored and recycled from there.</span></span> <span data-ttu-id="6a2d0-138">Weitere Informationen finden Sie unter [Zurücksetzen und Blockieren des mobilen Geräts eines ehemaligen Mitarbeiters](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span><span class="sxs-lookup"><span data-stu-id="6a2d0-138">To learn more, see [Wipe and block a former employee's mobile device](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span></span>


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="6a2d0-139">Synchronisieren der Benutzerkennworthashes zwischen einem lokalen Active Directory und Azure Active Directory (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="6a2d0-139">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="6a2d0-140">Dieser Artikel befasst sich mit dem Festlegen der Ablaufrichtlinie für Nur-Cloud-Benutzer (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="6a2d0-140">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="6a2d0-141">Er gilt nicht für Benutzer von Hybrididentitäten, die eine Kennworthashsynchronisierung, eine Passthrough-Authentifizierung oder einen lokalen Partnerverbund wie ADFS verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a2d0-141">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="6a2d0-142">Informationen, wie Benutzerkennworthashes über lokales AD mit Azure AD synchronisiert werden, finden Sie unter [Implementieren der Kennworthashsynchronisierung bei Azure AD Connect-Synchronisierung](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="6a2d0-142">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
