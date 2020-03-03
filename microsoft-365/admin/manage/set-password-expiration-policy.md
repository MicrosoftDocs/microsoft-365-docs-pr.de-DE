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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Hier erfahren Sie, wie Sie im Microsoft 365 Admin Center eine Richtlinie für den Kennwortablauf für Ihre Organisation festlegen. '
ms.openlocfilehash: 88953317bea2b96c04c291dd028a4e9131b9a83e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361660"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="20685-103">Festlegen der Kennwortablaufrichtlinie für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="20685-103">Set the password expiration policy for your organization</span></span>

<span data-ttu-id="20685-104">Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen.</span><span class="sxs-lookup"><span data-stu-id="20685-104">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span>  

<span data-ttu-id="20685-105">Wenn Sie ein Benutzer sind, haben Sie nicht die Berechtigungen, um Ihr Kennwort so festzulegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="20685-105">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="20685-106">Bitten Sie den technischen Support Ihres Unternehmens bzw. der Schule/Uni, die Schritte in diesem Artikel für Sie durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="20685-106">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="20685-107">Als Administrator können Sie festlegen, dass Benutzerkennwörter nach einer bestimmten Anzahl von Tagen oder nie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="20685-107">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> 

> [!Tip]
> <span data-ttu-id="20685-108">Standardmäßig ist für Kennwörter festgelegt, dass sie in 90 Tagen ablaufen.</span><span class="sxs-lookup"><span data-stu-id="20685-108">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="20685-109">Aktuelle Untersuchungen weisen nachdrücklich darauf hin, dass erzwungene Kennwortänderungen mehr Schaden anrichten als sinnvoll sind.</span><span class="sxs-lookup"><span data-stu-id="20685-109">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="20685-110">Sie treiben Benutzer dazu, schwächere Kennwörter zu wählen, Kennwörter wiederzuverwenden oder alte Kennwörter in einer Weise zu aktualisieren, die von Hackern leicht erraten werden kann.</span><span class="sxs-lookup"><span data-stu-id="20685-110">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="20685-111">Wenn Sie festlegen, dass das Kennwort niemals abläuft, empfehlen wir die Aktivierung [mehrstufigen Authentifizierung](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="20685-111">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="20685-112">Führen Sie die folgenden Schritte aus, wenn Sie festlegen möchten, dass Benutzerkennwörter nach einer bestimmten Zeit ablaufen.</span><span class="sxs-lookup"><span data-stu-id="20685-112">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="20685-113">Nur [globale Office 365-Administratoren](../add-users/about-admin-roles.md) können diese Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="20685-113">Only [Office 365 global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="20685-114">Wechseln Sie im Admin Center zu **Einstellungen** \> **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="20685-114">In the admin center, go to the **Settings** \> **Settings**.</span></span>

2. <span data-ttu-id="20685-115">Wechseln Sie zur Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Sicherheit & Datenschutz</a>.</span><span class="sxs-lookup"><span data-stu-id="20685-115">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="20685-116">Wenn Sie kein globaler Office 365-Administrator sind, wird die Option "Sicherheit und Datenschutz" nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20685-116">If you aren't an Office 365 global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="20685-117">Wählen Sie **Kennwortablaufrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="20685-117">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="20685-118">Wenn Sie nicht möchten, dass die Benutzer ihre Kennwörter ändern müssen, aktivieren Sie das Kontrollkästchen neben **Festlegen, dass Benutzerkennwörter nach einer Anzahl von Tagen ablaufen**.</span><span class="sxs-lookup"><span data-stu-id="20685-118">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="20685-119">Geben Sie ein, wie oft Kennwörter ablaufen sollen.</span><span class="sxs-lookup"><span data-stu-id="20685-119">Type how often passwords should expire.</span></span> <span data-ttu-id="20685-120">Wählen Sie eine Anzahl von Tagen zwischen 14 und 730.</span><span class="sxs-lookup"><span data-stu-id="20685-120">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="20685-121">Geben Sie im zweiten Feld ein, wann die Benutzer über den Ablauf ihres Kennworts informiert werden sollen, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="20685-121">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="20685-122">Wählen Sie eine Anzahl von Tagen zwischen 1 und 30 aus.</span><span class="sxs-lookup"><span data-stu-id="20685-122">Choose a number of days from 1 to 30.</span></span>
    
7. <span data-ttu-id="20685-123">Wenn das Kennwort des Benutzers abläuft, erhält er eine Benachrichtigung, die in der unteren rechten Ecke des Bildschirms angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="20685-123">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="20685-124">Wichtige Informationen über das Feature zum Ablauf von Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="20685-124">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="20685-125">Hier finden Sie einige wichtige Informationen darüber, wie dieses Feature ab Januar 2018 funktioniert:</span><span class="sxs-lookup"><span data-stu-id="20685-125">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="20685-p106">Personen, die nur die Outlook-App verwenden, werden nicht gezwungen, ihr Office 365-Kennwort zurückzusetzen, bis es im Cache abläuft. Dies kann mehrere Tage nach dem tatsächlichen Ablaufdatum sein. Es gibt keine Problemumgehung für dieses Problem auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="20685-p106">People who only use the Outlook app won't be forced to reset their Office 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>
    
- <span data-ttu-id="20685-p107">Benutzer erhalten keine E-Mail-Benachrichtigung, die sie darauf hinweist, dass ihr Kennwort in x Tagen abläuft. Möchten Sie dieses Feature verwenden? **[Stimmen Sie hier ab!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="20685-p107">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>
    
## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="20685-132">Verhindern, dass das letzte Kennwort erneut verwendet wird</span><span class="sxs-lookup"><span data-stu-id="20685-132">Prevent last password from being used again</span></span>

<span data-ttu-id="20685-133">Wenn Sie Ihre Benutzer daran hindern möchten, alte Kennwörter wiederzuverwenden, können Sie das in Azure AD erledigen.</span><span class="sxs-lookup"><span data-stu-id="20685-133">If you want to prevent your users from recycling old passwords, you can do so in Azure AD.</span></span> <span data-ttu-id="20685-134">Schauen Sie sich [Festlegen der Kennwortablaufrichtlinie für Ihre Organisation](https://docs.microsoft.com/office365/admin/manage/set-password-expiration-policy?view=o365-worldwide) an.</span><span class="sxs-lookup"><span data-stu-id="20685-134">See [Set the password expiration policy for your organization](https://docs.microsoft.com/office365/admin/manage/set-password-expiration-policy?view=o365-worldwide).</span></span>

<span data-ttu-id="20685-135">Wenn ein Mitarbeiter ein mobiles Gerät für den Zugriff auf Office 365 verwendet hat, können Sie dieses auch zurücksetzen, um sicherzustellen, dass das Kennwort nicht mehr gespeichert und von dort wiederverwendet wird.</span><span class="sxs-lookup"><span data-stu-id="20685-135">In addition, if an employee used a mobile device to access Office 365, you can wipe it to ensure the password is no longer stored and recycled from there.</span></span> <span data-ttu-id="20685-136">Weitere Informationen finden Sie unter [Zurücksetzen und Blockieren des mobilen Geräts eines ehemaligen Mitarbeiters](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span><span class="sxs-lookup"><span data-stu-id="20685-136">To learn more, see [Wipe and block a former employee's mobile device](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span></span>


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-office-365"></a><span data-ttu-id="20685-137">Synchronisieren der Benutzerkennworthashes zwischen einem lokalen Active Directory und Azure Active Directory (Office 365)</span><span class="sxs-lookup"><span data-stu-id="20685-137">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Office 365)</span></span>

<span data-ttu-id="20685-138">Dieser Artikel befasst sich mit dem Festlegen der Ablaufrichtlinie für Nur-Cloud-Benutzer (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="20685-138">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="20685-139">Er gilt nicht für Benutzer von Hybrididentitäten, die eine Kennworthashsynchronisierung, eine Passthrough-Authentifizierung oder einen lokalen Partnerverbund wie ADFS verwenden.</span><span class="sxs-lookup"><span data-stu-id="20685-139">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="20685-140">Informationen, wie Benutzerkennworthashes über lokales AD mit Azure AD synchronisiert werden, finden Sie unter [Implementieren der Kennworthashsynchronisierung bei Azure AD Connect-Synchronisierung](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="20685-140">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
