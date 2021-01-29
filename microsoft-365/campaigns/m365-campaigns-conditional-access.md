---
title: Einrichten von Richtlinien für bedingten Zugriff
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie MFA erfordern und Richtlinien für bedingten Zugriff für Microsoft 365 Business einrichten.
ms.openlocfilehash: b13ba9f8c948d9a1209655c44871ca62cb5354dd
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044500"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="8acb2-103">Mehrstufige Authentifizierung erforderlich und Einrichten von Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="8acb2-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="8acb2-104">Sie schützen den Zugriff auf Ihre Daten mit mehrstufiger Authentifizierung und Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="8acb2-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="8acb2-105">Diese erhöhen die Sicherheit erheblich.</span><span class="sxs-lookup"><span data-stu-id="8acb2-105">These add substantial additional security.</span></span> <span data-ttu-id="8acb2-106">Microsoft stellt eine Reihe von grundlegenden Richtlinien für bedingten Zugriff zur Verfügung, die für alle Kunden empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="8acb2-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="8acb2-107">Basisrichtlinien sind eine Reihe vordefinierter Richtlinien, die Organisationen vor vielen häufigen Angriffen schützen.</span><span class="sxs-lookup"><span data-stu-id="8acb2-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="8acb2-108">Zu diesen häufigen Angriffen gehören Kennwort-Spray, Wiedergabe und Phishing.</span><span class="sxs-lookup"><span data-stu-id="8acb2-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="8acb2-109">Diese Richtlinien erfordern, dass Administratoren und Benutzer unter bestimmten Bedingungen eine zweite Authentifizierungsform (mehrstufige Authentifizierung oder MFA) eingeben.</span><span class="sxs-lookup"><span data-stu-id="8acb2-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) under certain conditions.</span></span> <span data-ttu-id="8acb2-110">Wenn beispielsweise ein Benutzer in Ihrer Organisation versucht, sich von einem anderen Land oder von einem unbekannten Gerät bei Microsoft 365 zu anmelden, kann die Anmeldung als riskant betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="8acb2-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="8acb2-111">Der Benutzer muss eine zusätzliche Form der Authentifizierung bereitstellen (z. B. einen Fingerabdruck oder einen Code), um seine Identität nachzuweisen.</span><span class="sxs-lookup"><span data-stu-id="8acb2-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span>

<span data-ttu-id="8acb2-112">Derzeit umfassen die Basisrichtlinien die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="8acb2-112">Currently, the baseline policies include the following policies:</span></span>

- <span data-ttu-id="8acb2-113">Einrichten im Microsoft 365 Admin Center:</span><span class="sxs-lookup"><span data-stu-id="8acb2-113">Set up in Microsoft 365 admin center:</span></span>
  - <span data-ttu-id="8acb2-114">**MFA für Administratoren** erforderlich: Erfordert die mehrstufige Authentifizierung für die privilegiertesten Administratorrollen, einschließlich des globalen Administrators.</span><span class="sxs-lookup"><span data-stu-id="8acb2-114">**Require MFA for admins**: Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
  - <span data-ttu-id="8acb2-115">**Endbenutzerschutz:** Erfordert eine mehrstufige Authentifizierung für Benutzer nur, wenn eine Anmeldung riskant ist.</span><span class="sxs-lookup"><span data-stu-id="8acb2-115">**End-user protection**: Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="8acb2-116">Einrichten im Azure Active Directory-Portal:</span><span class="sxs-lookup"><span data-stu-id="8acb2-116">Set up in Azure Active Directory portal:</span></span>
  - <span data-ttu-id="8acb2-117">**Blockieren der Legacyauthentifizierung:** Ältere Client-Apps und einige neue Apps verwenden keine neueren, sichereren Authentifizierungsprotokolle.</span><span class="sxs-lookup"><span data-stu-id="8acb2-117">**Block legacy authentication**: Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="8acb2-118">Diese älteren Apps können Richtlinien für bedingten Zugriff umgehen und nicht autorisierten Zugriff auf Ihre Umgebung erhalten.</span><span class="sxs-lookup"><span data-stu-id="8acb2-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="8acb2-119">Diese Richtlinie blockiert den Zugriff von Clients, die bedingten Zugriff nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8acb2-119">This policy blocks access from clients that don't support conditional access.</span></span> 
  - <span data-ttu-id="8acb2-120">**MFA für Dienstverwaltung** erforderlich: Erfordert eine mehrstufige Authentifizierung für den Zugriff auf Verwaltungstools, einschließlich des Azure-Portals (in dem Sie Basisrichtlinien konfigurieren).</span><span class="sxs-lookup"><span data-stu-id="8acb2-120">**Require MFA for Service Management**: Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span>

<span data-ttu-id="8acb2-121">Es wird empfohlen, alle diese Basisrichtlinien zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8acb2-121">We recommend that you enable all of these baseline policies.</span></span> <span data-ttu-id="8acb2-122">Nachdem diese Richtlinien aktiviert wurden, werden Administratoren und Benutzer aufgefordert, sich für die mehrstufige Azure AD-Authentifizierung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="8acb2-122">After these policies are enabled, admins and users will be prompted to register for Azure AD Multifactor Authentication.</span></span>

<span data-ttu-id="8acb2-123">Weitere Informationen zu diesen Richtlinien finden Sie unter [Was sind Basisrichtlinien?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)</span><span class="sxs-lookup"><span data-stu-id="8acb2-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>

## <a name="require-mfa"></a><span data-ttu-id="8acb2-124">MFA erforderlich</span><span class="sxs-lookup"><span data-stu-id="8acb2-124">Require MFA</span></span>

<span data-ttu-id="8acb2-125">So fordern Sie an, dass sich alle Benutzer mit einer zweiten Form der ID anmelden:</span><span class="sxs-lookup"><span data-stu-id="8acb2-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="8acb2-126">Wechseln Sie zum Admin Center, <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> und wählen Sie Setup **aus.**</span><span class="sxs-lookup"><span data-stu-id="8acb2-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="8acb2-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span><span class="sxs-lookup"><span data-stu-id="8acb2-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>

    ![Sorgen Sie dafür, dass die Anmeldung sicherer ist.](../media/setupmfa.png)
3. <span data-ttu-id="8acb2-129">Wählen Sie auf der Seite "Anmeldung sicherer machen" die Option **"Erste Schritte" aus.**</span><span class="sxs-lookup"><span data-stu-id="8acb2-129">On the Make sign-in more secure page, choose **Get started**.</span></span>

4. <span data-ttu-id="8acb2-130">Aktivieren Sie im Sicherheitsbereich "Anmeldung stärken"  die Kontrollkästchen neben "Mehrstufige Authentifizierung für Administratoren erforderlich" und "Benutzer müssen sich für die mehrstufige Authentifizierung registrieren und den Zugriff blockieren, wenn ein Risiko erkannt **wird".**</span><span class="sxs-lookup"><span data-stu-id="8acb2-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="8acb2-131">Stellen Sie sicher, dass Sie das Administratorkonto für Notfälle oder "Break-Glass" von der MFA-Anforderung im Feld "Benutzer **suchen"** ausschließen. [](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account)</span><span class="sxs-lookup"><span data-stu-id="8acb2-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>

    ![Stärken Sie die Sicherheitsseite für die Einsingung.](../media/requiremfa.png)

5. <span data-ttu-id="8acb2-133">Klicken **Sie unten auf** der Seite auf "Richtlinie erstellen".</span><span class="sxs-lookup"><span data-stu-id="8acb2-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="8acb2-134">Einrichten von Basisrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8acb2-134">Set up baseline policies</span></span>

1. <span data-ttu-id="8acb2-135">Wechseln Sie zum [Azure-Portal,](https://portal.azure.com)und navigieren Sie dann zu **Azure Active Directory** Conditional \> **Access,** um eine neue Richtlinie zu **erstellen.**</span><span class="sxs-lookup"><span data-stu-id="8acb2-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="8acb2-136">Weitere Informationen finden Sie in den folgenden spezifischen Anweisungen für jede Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="8acb2-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="8acb2-137">MFA für Administratoren erforderlich</span><span class="sxs-lookup"><span data-stu-id="8acb2-137">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="8acb2-138">MFA für Benutzer erforderlich</span><span class="sxs-lookup"><span data-stu-id="8acb2-138">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="8acb2-139">Blockieren von Legacy-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="8acb2-139">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="8acb2-140">MFA für Die Dienstverwaltung erforderlich</span><span class="sxs-lookup"><span data-stu-id="8acb2-140">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> <span data-ttu-id="8acb2-141">Vorschaurichtlinien sind nicht mehr vorhanden, und Benutzer müssen eigene Richtlinien erstellen.</span><span class="sxs-lookup"><span data-stu-id="8acb2-141">Preview policies no longer exist and users will need to create their own policies.</span></span>

<span data-ttu-id="8acb2-142">Sie können zusätzliche Richtlinien einrichten, z. B. die Anforderung genehmigter Client-Apps.</span><span class="sxs-lookup"><span data-stu-id="8acb2-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="8acb2-143">Weitere Informationen finden Sie in der [Dokumentation zum bedingten Zugriff.](https://docs.microsoft.com/azure/active-directory/conditional-access/)</span><span class="sxs-lookup"><span data-stu-id="8acb2-143">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
