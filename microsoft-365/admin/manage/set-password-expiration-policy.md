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
description: Erfahren Sie, wie ein Administrator im Microsoft 365 Admin Center eine Richtlinie zum Ablauf von Passwörtern für Ihr Unternehmen, Ihre Schule oder Ihre gemeinnützige Organisation festlegen kann.
ms.openlocfilehash: fdd219e4fc99e2388acb5b19eacb2fc470041f79
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286729"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="76751-103">Festlegen der Kennwortablaufrichtlinie für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="76751-103">Set the password expiration policy for your organization</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="76751-104">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="76751-104">Before you begin</span></span>

<span data-ttu-id="76751-105">Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen.</span><span class="sxs-lookup"><span data-stu-id="76751-105">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="76751-106">Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="76751-106">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="76751-107">[Was ist ein Administratorkonto?](../../business-video/admin-center-overview.md)</span><span class="sxs-lookup"><span data-stu-id="76751-107">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span>

<span data-ttu-id="76751-p102">Als Administrator können Sie festlegen, dass Benutzerkennwörter nach einer bestimmten Anzahl von Tagen oder nie ablaufen. Standardmäßig sind Passwörter für Ihre Organisation so eingestellt, dass sie nie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="76751-p102">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire. By default, passwords are set to never expire for your organization.</span></span>

<span data-ttu-id="76751-110">Aktuelle Untersuchungen weisen nachdrücklich darauf hin, dass erzwungene Kennwortänderungen mehr Schaden anrichten als sinnvoll sind.</span><span class="sxs-lookup"><span data-stu-id="76751-110">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="76751-111">Sie treiben Benutzer dazu, schwächere Kennwörter zu wählen, Kennwörter wiederzuverwenden oder alte Kennwörter in einer Weise zu aktualisieren, die von Hackern leicht erraten werden kann.</span><span class="sxs-lookup"><span data-stu-id="76751-111">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="76751-112">Wir empfehlen, die [mehrstufige Authentifizierung zu aktivieren](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="76751-112">We recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span> <span data-ttu-id="76751-113">Um mehr über Passwortrichtlinien zu erfahren, lesen Sie die [Empfehlungen für Passwortrichtlinien](../misc/password-policy-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="76751-113">To learn more about password policy, check out [Password policy recommendations](../misc/password-policy-recommendations.md).</span></span>

<span data-ttu-id="76751-114">Sie müssen [globaler Administrator](../add-users/about-admin-roles.md) sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="76751-114">You must be a [global admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="76751-p104">Wenn Sie ein Benutzer sind, haben Sie nicht die Berechtigungen, um Ihr Kennwort so festzulegen, dass es nie abläuft. Bitten Sie den technischen Support Ihres Unternehmens bzw. der Schule/Uni, die Schritte in diesem Artikel für Sie durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="76751-p104">If you're a user, you don't have the permissions to set your password to never expire. Ask your work or school technical support to do the steps in this article for you.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="76751-117">Festlegen der Kennwortablaufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="76751-117">Set password expiration policy</span></span>

<span data-ttu-id="76751-118">Führen Sie die folgenden Schritte aus, wenn Sie festlegen möchten, dass Benutzerkennwörter nach einer bestimmten Zeit ablaufen.</span><span class="sxs-lookup"><span data-stu-id="76751-118">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>

1. <span data-ttu-id="76751-119">Wechseln Sie im Admin Center zu **Einstellungen** \> **Org-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="76751-119">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="76751-120">Wechseln Sie zur Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Sicherheit & Datenschutz</a>.</span><span class="sxs-lookup"><span data-stu-id="76751-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="76751-121">Wenn Sie kein globaler Administrator sind, wird die Option "Sicherheit und Datenschutz" nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76751-121">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="76751-122">Wählen Sie **Kennwortablaufrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="76751-122">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="76751-123">Wenn Sie nicht möchten, dass die Benutzer ihre Kennwörter ändern müssen, deaktivieren Sie das Kästchen neben **Festlegen, dass Benutzerkennwörter nach einer Anzahl von Tagen ablaufen**.</span><span class="sxs-lookup"><span data-stu-id="76751-123">If you don't want users to have to change passwords, uncheck the box next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="76751-p106">Geben Sie ein, wie oft Kennwörter ablaufen sollen. Wählen Sie eine Anzahl von Tagen zwischen 14 und 730.</span><span class="sxs-lookup"><span data-stu-id="76751-p106">Type how often passwords should expire. Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="76751-126">Geben Sie im zweiten Feld ein, wann die Benutzer über den Ablauf ihres Kennworts informiert werden sollen, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="76751-126">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="76751-127">Wählen Sie eine Anzahl von Tagen zwischen 1 und 30 aus.</span><span class="sxs-lookup"><span data-stu-id="76751-127">Choose a number of days from 1 to 30.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="76751-128">Wichtige Informationen über das Feature zum Ablauf von Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="76751-128">Important things you need to know about the password expiration feature</span></span>
  
<span data-ttu-id="76751-p108">Personen, die nur die Outlook-App verwenden, werden nicht gezwungen, ihr Microsoft 365-Kennwort zurückzusetzen, bis es im Cache abläuft. Dies kann mehrere Tage nach dem tatsächlichen Ablaufdatum sein. Es gibt keine Problemumgehung für dieses Problem auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="76751-p108">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="76751-132">Verhindern, dass das letzte Kennwort erneut verwendet wird</span><span class="sxs-lookup"><span data-stu-id="76751-132">Prevent last password from being used again</span></span>

<span data-ttu-id="76751-133">Wenn Sie Ihre Benutzer daran hindern möchten, alte Kennwörter wiederzuverwenden, können Sie das durch Erzwingen des Kennwortverlaufs im lokalen Active Directory (AD) erledigen.</span><span class="sxs-lookup"><span data-stu-id="76751-133">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="76751-134">Informationen hierzu finden Sie unter [Erstellen einer benutzerdefinierten Kennwortrichtlinie](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span><span class="sxs-lookup"><span data-stu-id="76751-134">See [Create a custom password policy](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="76751-135">In Azure AD kann das letzte Kennwort nicht mehr verwendet werden, wenn der Benutzer ein Kennwort ändert.</span><span class="sxs-lookup"><span data-stu-id="76751-135">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="76751-136">Die Kennwortrichtlinie wird auf alle Benutzerkonten angewendet, die direkt in Azure AD erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="76751-136">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="76751-137">Die Kennwortrichtlinie kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="76751-137">This password policy can't be modified.</span></span> <span data-ttu-id="76751-138">Informationen hierzu finden Sie unter [Azure AD-Kennwortrichtlinien](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="76751-138">See [Azure AD password policies](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="76751-139">Synchronisieren der Benutzerkennworthashes zwischen einem lokalen Active Directory und Azure Active Directory (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="76751-139">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="76751-140">Dieser Artikel befasst sich mit dem Festlegen der Ablaufrichtlinie für Nur-Cloud-Benutzer (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="76751-140">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="76751-141">Er gilt nicht für Benutzer von Hybrididentitäten, die eine Kennworthashsynchronisierung, eine Passthrough-Authentifizierung oder einen lokalen Partnerverbund wie ADFS verwenden.</span><span class="sxs-lookup"><span data-stu-id="76751-141">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="76751-142">Informationen, wie Benutzerkennworthashes über lokales AD mit Azure AD synchronisiert werden, finden Sie unter [Implementieren der Kennworthashsynchronisierung bei Azure AD Connect-Synchronisierung](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="76751-142">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="76751-143">Kennwortrichtlinien und Kontoeinschränkungen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="76751-143">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="76751-144">Sie können weitere Kennwortrichtlinien und Einschränkungen in Azure Active Directory festlegen.</span><span class="sxs-lookup"><span data-stu-id="76751-144">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="76751-145">Weitere Informationen finden Sie unter [Kennwortrichtlinien und Kontoeinschränkungen in Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy).</span><span class="sxs-lookup"><span data-stu-id="76751-145">Check out [Password policies and account restrictions in Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="76751-146">Aktualisieren der Kennwortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="76751-146">Update password Policy</span></span>

<span data-ttu-id="76751-p113">Das Cmdlet "Set-MsolPasswordPolicy" aktualisiert die Kennwortrichtlinie einer angegebenen Domäne oder eines Mandanten. Zwei Einstellungen sind erforderlich; die erste ist die Angabe der Zeitspanne, die ein Kennwort gültig bleibt, bevor es geändert werden muss, und die zweite ist die Angabe der Anzahl von Tagen vor dem Ablaufdatum des Kennworts, das ausgelöst wird, wenn Benutzer ihre erste Benachrichtigung erhalten, dass ihr Kennwort bald abläuft.</span><span class="sxs-lookup"><span data-stu-id="76751-p113">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant. Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="76751-149">Wie Sie die Kennwortrichtlinie für eine bestimmte Domäne oder einen bestimmten Mandanten aktualisieren, erfahren Sie unter [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy).</span><span class="sxs-lookup"><span data-stu-id="76751-149">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy).</span></span>

## <a name="related-content"></a><span data-ttu-id="76751-150">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="76751-150">Related content</span></span>

<span data-ttu-id="76751-151">[Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten](../add-users/let-users-reset-passwords.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="76751-151">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>\

<span data-ttu-id="76751-152">[Kennwörter zurücksetzen](../add-users/reset-passwords.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="76751-152">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>
