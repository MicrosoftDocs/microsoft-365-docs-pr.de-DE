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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Hier erfahren Sie, wie Sie im Microsoft 365 Admin Center eine Richtlinie für den Kennwortablauf für Ihre Organisation festlegen.
ms.openlocfilehash: 4a7b544b6eded6f0cd6441ad7f6b02de790e5e44
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50603984"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="a951f-103">Festlegen der Kennwortablaufrichtlinie für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="a951f-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a951f-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="a951f-104">The admin center is changing.</span></span> <span data-ttu-id="a951f-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="a951f-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-worldwide).</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="a951f-106">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="a951f-106">Before you begin</span></span>

<span data-ttu-id="a951f-107">Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen.</span><span class="sxs-lookup"><span data-stu-id="a951f-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="a951f-108">Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="a951f-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="a951f-109">[Was ist ein Administratorkonto?](../admin-overview/admin-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a951f-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span>

<span data-ttu-id="a951f-110">Sie müssen [globaler Administrator](../add-users/about-admin-roles.md) sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="a951f-110">You must be a [global admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="a951f-111">Wenn Sie ein Benutzer sind, haben Sie nicht die Berechtigungen, um Ihr Kennwort so festzulegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="a951f-111">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="a951f-112">Bitten Sie den technischen Support Ihres Unternehmens bzw. der Schule/Uni, die Schritte in diesem Artikel für Sie durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="a951f-112">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="a951f-113">Als Administrator können Sie festlegen, dass Benutzerkennwörter nach einer bestimmten Anzahl von Tagen oder nie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="a951f-113">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="a951f-114">Festlegen der Kennwortablaufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="a951f-114">Set password expiration policy</span></span>

> [!Tip]
> <span data-ttu-id="a951f-115">Standardmäßig ist für Kennwörter festgelegt, dass sie in 90 Tagen ablaufen.</span><span class="sxs-lookup"><span data-stu-id="a951f-115">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="a951f-116">Aktuelle Untersuchungen weisen nachdrücklich darauf hin, dass erzwungene Kennwortänderungen mehr Schaden anrichten als sinnvoll sind.</span><span class="sxs-lookup"><span data-stu-id="a951f-116">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="a951f-117">Sie treiben Benutzer dazu, schwächere Kennwörter zu wählen, Kennwörter wiederzuverwenden oder alte Kennwörter in einer Weise zu aktualisieren, die von Hackern leicht erraten werden kann.</span><span class="sxs-lookup"><span data-stu-id="a951f-117">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="a951f-118">Wenn Sie festlegen, dass das Kennwort niemals abläuft, empfehlen wir die Aktivierung [mehrstufigen Authentifizierung](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a951f-118">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="a951f-119">Führen Sie die folgenden Schritte aus, wenn Sie festlegen möchten, dass Benutzerkennwörter nach einer bestimmten Zeit ablaufen.</span><span class="sxs-lookup"><span data-stu-id="a951f-119">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>

1. <span data-ttu-id="a951f-120">Wechseln Sie im Admin Center zu **Einstellungen** \> **Org-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="a951f-120">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="a951f-121">Wechseln Sie zur Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Sicherheit & Datenschutz</a>.</span><span class="sxs-lookup"><span data-stu-id="a951f-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="a951f-122">Wenn Sie kein globaler Administrator sind, wird die Option "Sicherheit und Datenschutz" nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a951f-122">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="a951f-123">Wählen Sie **Kennwortablaufrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="a951f-123">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="a951f-124">Wenn Sie nicht möchten, dass die Benutzer ihre Kennwörter ändern müssen, deaktivieren Sie das Kästchen neben **Festlegen, dass Benutzerkennwörter nach einer Anzahl von Tagen ablaufen**.</span><span class="sxs-lookup"><span data-stu-id="a951f-124">If you don't want users to have to change passwords, uncheck the box next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="a951f-125">Geben Sie ein, wie oft Kennwörter ablaufen sollen.</span><span class="sxs-lookup"><span data-stu-id="a951f-125">Type how often passwords should expire.</span></span> <span data-ttu-id="a951f-126">Wählen Sie eine Anzahl von Tagen zwischen 14 und 730.</span><span class="sxs-lookup"><span data-stu-id="a951f-126">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="a951f-127">Geben Sie im zweiten Feld ein, wann die Benutzer über den Ablauf ihres Kennworts informiert werden sollen, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="a951f-127">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="a951f-128">Wählen Sie eine Anzahl von Tagen zwischen 1 und 30 aus.</span><span class="sxs-lookup"><span data-stu-id="a951f-128">Choose a number of days from 1 to 30.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="a951f-129">Wichtige Informationen über das Feature zum Ablauf von Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="a951f-129">Important things you need to know about the password expiration feature</span></span>
  
- <span data-ttu-id="a951f-p108">Personen, die nur die Outlook-App verwenden, werden nicht gezwungen, ihr Microsoft 365-Kennwort zurückzusetzen, bis es im Cache abläuft. Dies kann mehrere Tage nach dem tatsächlichen Ablaufdatum sein. Es gibt keine Problemumgehung für dieses Problem auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="a951f-p108">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="a951f-133">Verhindern, dass das letzte Kennwort erneut verwendet wird</span><span class="sxs-lookup"><span data-stu-id="a951f-133">Prevent last password from being used again</span></span>

<span data-ttu-id="a951f-134">Wenn Sie Ihre Benutzer daran hindern möchten, alte Kennwörter wiederzuverwenden, können Sie das durch Erzwingen des Kennwortverlaufs im lokalen Active Directory (AD) erledigen.</span><span class="sxs-lookup"><span data-stu-id="a951f-134">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="a951f-135">Informationen hierzu finden Sie unter [Erstellen einer benutzerdefinierten Kennwortrichtlinie](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span><span class="sxs-lookup"><span data-stu-id="a951f-135">See [Create a custom password policy](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="a951f-136">In Azure AD kann das letzte Kennwort nicht mehr verwendet werden, wenn der Benutzer ein Kennwort ändert.</span><span class="sxs-lookup"><span data-stu-id="a951f-136">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="a951f-137">Die Kennwortrichtlinie wird auf alle Benutzerkonten angewendet, die direkt in Azure AD erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="a951f-137">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="a951f-138">Die Kennwortrichtlinie kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a951f-138">This password policy can't be modified.</span></span> <span data-ttu-id="a951f-139">Informationen hierzu finden Sie unter [Azure AD-Kennwortrichtlinien](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="a951f-139">See [Azure AD password policies](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="a951f-140">Synchronisieren der Benutzerkennworthashes zwischen einem lokalen Active Directory und Azure Active Directory (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="a951f-140">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="a951f-141">Dieser Artikel befasst sich mit dem Festlegen der Ablaufrichtlinie für Nur-Cloud-Benutzer (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a951f-141">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="a951f-142">Er gilt nicht für Benutzer von Hybrididentitäten, die eine Kennworthashsynchronisierung, eine Passthrough-Authentifizierung oder einen lokalen Partnerverbund wie ADFS verwenden.</span><span class="sxs-lookup"><span data-stu-id="a951f-142">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="a951f-143">Informationen, wie Benutzerkennworthashes über lokales AD mit Azure AD synchronisiert werden, finden Sie unter [Implementieren der Kennworthashsynchronisierung bei Azure AD Connect-Synchronisierung](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="a951f-143">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="a951f-144">Kennwortrichtlinien und Kontoeinschränkungen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a951f-144">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="a951f-145">Sie können weitere Kennwortrichtlinien und Einschränkungen in Azure Active Directory festlegen.</span><span class="sxs-lookup"><span data-stu-id="a951f-145">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="a951f-146">Weitere Informationen finden Sie unter [Kennwortrichtlinien und Kontoeinschränkungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy).</span><span class="sxs-lookup"><span data-stu-id="a951f-146">Check out [Password policies and account restrictions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="a951f-147">Aktualisieren der Kennwortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="a951f-147">Update password Policy</span></span>

<span data-ttu-id="a951f-148">Das Cmdlet "Set-MsolPasswordPolicy" aktualisiert die Kennwortrichtlinie einer bestimmten Domäne oder eines bestimmten Mandanten.</span><span class="sxs-lookup"><span data-stu-id="a951f-148">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant.</span></span> <span data-ttu-id="a951f-149">Zwei Einstellungen sind erforderlich: Die erste legt die Zeitspanne fest, die ein Kennwort gültig bleibt, bevor es geändert werden muss, und die zweite legt fest, wie viele Tage vor dem Ablaufdatum des Kennworts die erste Benachrichtigung an den Benutzer auslöst wird, dass sein Kennwort bald abläuft.</span><span class="sxs-lookup"><span data-stu-id="a951f-149">Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="a951f-150">Wie Sie die Kennwortrichtlinie für eine bestimmte Domäne oder einen bestimmten Mandanten aktualisieren, erfahren Sie unter [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="a951f-150">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>

## <a name="related-content"></a><span data-ttu-id="a951f-151">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="a951f-151">Related content</span></span>

[<span data-ttu-id="a951f-152">Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten</span><span class="sxs-lookup"><span data-stu-id="a951f-152">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="a951f-153">Zurücksetzen von Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="a951f-153">Reset passwords</span></span>](../add-users/reset-passwords.md)
