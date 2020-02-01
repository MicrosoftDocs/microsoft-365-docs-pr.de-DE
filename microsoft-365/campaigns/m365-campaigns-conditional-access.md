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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie MFA erfordern und Richtlinien für bedingten Zugriff für Microsoft 365 Business einrichten.
ms.openlocfilehash: b65cccf9931da4701157f26ffece7a7c90689094
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594860"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="58365-103">Erzwingen der mehrstufigen Authentifizierung und Einrichten von Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="58365-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="58365-104">Sie schützen den Zugriff auf Ihre Daten mit mehrstufiger Authentifizierung und Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="58365-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="58365-105">Dadurch wird eine erhebliche zusätzliche Sicherheit hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="58365-105">These add substantial additional security.</span></span> <span data-ttu-id="58365-106">Microsoft stellt eine Reihe von Baseline-bedingten Zugriffsrichtlinien bereit, die für alle Kunden empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="58365-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="58365-107">Baseline-Richtlinien sind eine Reihe von vordefinierten Richtlinien, die Organisationen vor zahlreichen häufigen Angriffen schützen sollen.</span><span class="sxs-lookup"><span data-stu-id="58365-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="58365-108">Diese häufigen Angriffe können Kenn Wort Spray, Wiedergabe und Phishing umfassen.</span><span class="sxs-lookup"><span data-stu-id="58365-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="58365-109">Für diese Richtlinien müssen Administratoren und Benutzer eine zweite Authentifizierungsform (mehrstufige Authentifizierung oder MFA genannt) eingeben, wenn bestimmte Bedingungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="58365-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="58365-110">Wenn beispielsweise ein Benutzer in Ihrer Organisation versucht, sich bei Microsoft 365 aus einem anderen Land oder einem unbekannten Gerät anzumelden, wird die Anmeldung möglicherweise als riskant eingestuft.</span><span class="sxs-lookup"><span data-stu-id="58365-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="58365-111">Der Benutzer muss eine zusätzliche Form der Authentifizierung (beispielsweise Fingerabdruck oder Code) bereitstellen, um seine Identität nachzuweisen.</span><span class="sxs-lookup"><span data-stu-id="58365-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="58365-112">Derzeit umfassen Baseline-Richtlinien Folgendes:</span><span class="sxs-lookup"><span data-stu-id="58365-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="58365-113">Einrichten im Microsoft 365 Admin Center:</span><span class="sxs-lookup"><span data-stu-id="58365-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="58365-114">**MFA für Administratoren erforderlich** – erfordert mehrstufige Authentifizierung für die privilegierten Administratorrollen, einschließlich des globalen Administrators.</span><span class="sxs-lookup"><span data-stu-id="58365-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="58365-115">**Endbenutzer Schutz** – erfordert mehrstufige Authentifizierung für Benutzer nur, wenn eine Anmeldung riskant ist.</span><span class="sxs-lookup"><span data-stu-id="58365-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="58365-116">Einrichten in Azure Active Directory Portal:</span><span class="sxs-lookup"><span data-stu-id="58365-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="58365-117">**Legacy Authentifizierung blockieren** – ältere Client-apps und einige neue Apps verwenden keine neueren, sichereren Authentifizierungsprotokolle.</span><span class="sxs-lookup"><span data-stu-id="58365-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="58365-118">Diese älteren Apps können Richtlinien für bedingten Zugriff umgehen und nicht autorisierten Zugriff auf Ihre Umgebung erlangen.</span><span class="sxs-lookup"><span data-stu-id="58365-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="58365-119">Diese Richtlinie blockiert den Zugriff von Clients, die keinen bedingten Zugriff unterstützen.</span><span class="sxs-lookup"><span data-stu-id="58365-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="58365-120">**MFA für die Dienstverwaltung erforderlich** – erfordert mehrstufige Authentifizierung für den Zugriff auf Verwaltungstools, einschließlich Azure-Portal (in dem Sie Basisrichtlinien konfigurieren).</span><span class="sxs-lookup"><span data-stu-id="58365-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="58365-121">Microsoft empfiehlt, alle diese Basisrichtlinien zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="58365-121">Microsoft recommends that you enable all of these baseline policies.</span></span> <span data-ttu-id="58365-122">Nachdem diese Richtlinien aktiviert wurden, werden Administratoren und Benutzer aufgefordert, sich für die Azure-mehrstufige Authentifizierung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="58365-122">After these policies are enabled, admins and users will be prompted to register for Azure Multi-Factor authentication.</span></span>

<span data-ttu-id="58365-123">Weitere Informationen zu diesen Richtlinien finden Sie unter [Was sind Basisrichtlinien](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="58365-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="58365-124">MFA erforderlich</span><span class="sxs-lookup"><span data-stu-id="58365-124">Require MFA</span></span>

<span data-ttu-id="58365-125">So legen Sie fest, dass sich alle Benutzer mit einem zweiten ID-Formular anmelden müssen:</span><span class="sxs-lookup"><span data-stu-id="58365-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="58365-126">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> , und wählen Sie **Setup**aus.</span><span class="sxs-lookup"><span data-stu-id="58365-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="58365-127">Wählen Sie auf der Seite Setup die Option **Ansicht** in **sicherer Karte anmelden** .</span><span class="sxs-lookup"><span data-stu-id="58365-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![Anmelden sicherer Karten.](media/setupmfa.png)
3. <span data-ttu-id="58365-129">Wählen Sie auf der Seite Anmeldung sicherer gestalten die Option **Erste Schritte**aus.</span><span class="sxs-lookup"><span data-stu-id="58365-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="58365-130">Aktivieren Sie im Bereich Anmeldesicherheit verstärken die Kontrollkästchen neben mehrstufiger **Authentifizierung für Administratoren erforderlich** , und fordern Sie die **Benutzer auf, die mehrstufige Authentifizierung zu registrieren und den Zugriff zu blockieren, wenn das Risiko erkannt wird**.</span><span class="sxs-lookup"><span data-stu-id="58365-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="58365-131">Achten Sie darauf, das [Notfall](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) -oder "Break-Glass"-Administratorkonto aus der MFA-Anforderung im Feld **Benutzer suchen** auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="58365-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![Stärkung der Sing-in-Sicherheitsseite.](media/requiremfa.png)

5. <span data-ttu-id="58365-133">Klicken Sie unten auf der Seite auf **Richtlinie erstellen** .</span><span class="sxs-lookup"><span data-stu-id="58365-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="58365-134">Einrichten von Baseline-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="58365-134">Set up baseline policies</span></span>

1. <span data-ttu-id="58365-135">Wechseln Sie [zu Azure-Portal](https://portal.azure.com), und navigieren Sie dann zu **Azure Active Directory** \> **bedingten Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="58365-135">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="58365-136">Die grundlegenden Richtlinien werden auf der Seite aufgeführt, und Sie können sehen, dass **MFA für Administratoren** und **Endbenutzer Schutz** erforderlich ist, nachdem Sie die Schritte in " [MFA erfordern](#require-mfa)" abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="58365-136">The baseline policies are listed on the page, and you can see that **Require MFA for admins** and **End user protection** are already enabled after you completed the steps in [require MFA](#require-mfa).</span></span>

    ![Seite, auf der Basisrichtlinien für bedingten Zugriff aufgelistet werden.](media/casettings.png)
2. <span data-ttu-id="58365-138">Lesen Sie die folgenden spezifischen Anweisungen für jede Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="58365-138">See the following specific instructions for each policy:</span></span>

    - [<span data-ttu-id="58365-139">MFA für Administratoren erforderlich</span><span class="sxs-lookup"><span data-stu-id="58365-139">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
    - [<span data-ttu-id="58365-140">MFA für Benutzer erforderlich</span><span class="sxs-lookup"><span data-stu-id="58365-140">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [<span data-ttu-id="58365-141">Legacy Authentifizierung blockieren</span><span class="sxs-lookup"><span data-stu-id="58365-141">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [<span data-ttu-id="58365-142">MFA für Service Management erforderlich</span><span class="sxs-lookup"><span data-stu-id="58365-142">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="58365-143">Sie können zusätzliche Richtlinien einrichten, beispielsweise das Anfordern von genehmigten Client-apps.</span><span class="sxs-lookup"><span data-stu-id="58365-143">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="58365-144">Weitere Informationen finden Sie in der [Dokumentation zum bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="58365-144">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
