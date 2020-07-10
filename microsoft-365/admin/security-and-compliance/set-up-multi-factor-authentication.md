---
title: Einrichten der Multi-Faktor-Authentifizierung für Benutzer
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Hier erfahren Sie, wie Sie die Multi-Faktor-Authentifizierung für Ihre Organisation einrichten.
monikerRange: o365-worldwide
ms.openlocfilehash: b0fd16fc74319c88a6f91bf56ac96346915c35ac
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049760"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="f0284-103">Einrichten der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="f0284-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="f0284-104">Ihre Kenntnis der [Multi-Faktor-Authentifizierung (MFA) und deren Unterstützung in Microsoft 365](multi-factor-authentication-microsoft-365.md) vorausgesetzt, ist es an der Zeit, diese einzurichten und für Ihre Organisation bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f0284-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="f0284-105">Prüfen Sie, bevor Sie beginnen, ob diese speziellen Bedingungen für Sie zutreffen, und führen Sie die entsprechenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f0284-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="f0284-106">Wenn Office 2013-Clients auf Windows-Geräten installiert sind, [aktivieren Sie die moderne Authentifizierung](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="f0284-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="f0284-107">Wenn Verzeichnisdienste von Drittanbietern mit Active Directory Federation Services (AD FS) genutzt werden, richten Sie den Azure MFA-Server ein.</span><span class="sxs-lookup"><span data-stu-id="f0284-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="f0284-108">Weitere Informationen finden Sie unter [Erweiterte Szenarien mit Azure Multi-Faktor-Authentifizierung und VPN-Lösungen von Drittanbietern](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn).</span><span class="sxs-lookup"><span data-stu-id="f0284-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

<span data-ttu-id="f0284-109">Alle anderen Benutzer werden bei Bedarf zu einer zusätzlichen Authentifizierung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f0284-109">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="f0284-110">Weitere Informationen finden Sie unter [Zwei-Faktor-Authentifizierung – Methode und Einstellungen](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span><span class="sxs-lookup"><span data-stu-id="f0284-110">For more information, please visit [Two-factor verification method and settings](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="f0284-111">Schritt 1: Entscheiden Sie sich für eine Methode, die Ihre Benutzer für die MFA verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="f0284-111">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="f0284-112">Sie müssen ein globaler Administrator sein, um die MFA einrichten oder ändern zu können.</span><span class="sxs-lookup"><span data-stu-id="f0284-112">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="f0284-113">Es gibt drei Möglichkeiten, die MFA für die Anmeldung Ihrer Benutzer einzubinden. Weitere Informationen finden Sie unter [MFA-Support in Microsoft 365](multi-factor-authentication-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="f0284-113">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="f0284-114">Standardsicherheitseinstellungen (empfohlen für kleine Unternehmen)</span><span class="sxs-lookup"><span data-stu-id="f0284-114">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="f0284-115">Wenn Sie Ihr Abonnement oder Ihre Testversion nach dem 21. Oktober 2019 erworben haben und unerwartet eine MFA-Aufforderung erhalten, wurden automatisch die [Standardsicherheitseinstellungen](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) für Ihr Abonnement aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f0284-115">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="f0284-116">Bei jedem neuen Microsoft 365-Abonnement sind automatisch die Standardsicherheitseinstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f0284-116">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="f0284-117">Dies bedeutet, dass jeder Benutzer die Multi-Faktor-Authentifizierung (MFA) einrichten und die Microsoft Authenticator-App auf dem Mobilgerät installieren muss.</span><span class="sxs-lookup"><span data-stu-id="f0284-117">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="f0284-118">Alle Benutzer müssen die Microsoft Authenticator-App als zusätzliche Überprüfungsmethode verwenden. Die Legacy-Authentifizierung wird blockiert.</span><span class="sxs-lookup"><span data-stu-id="f0284-118">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="f0284-119">Zugangsberechtigungsrichtlinien (empfohlen für Unternehmen)</span><span class="sxs-lookup"><span data-stu-id="f0284-119">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="f0284-120">Die Benutzer wählen die zusätzliche Überprüfungsmethode während der MFA-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="f0284-120">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="f0284-121">Nach Benutzerkonto (nicht empfohlen)</span><span class="sxs-lookup"><span data-stu-id="f0284-121">Per-user account (not recommended)</span></span>

  <span data-ttu-id="f0284-122">Die Benutzer wählen die zusätzliche Überprüfungsmethode während der MFA-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="f0284-122">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="f0284-123">Schritt 2:</span><span class="sxs-lookup"><span data-stu-id="f0284-123">Step 2.</span></span> <span data-ttu-id="f0284-124">Testen Sie die MFA mit Ihren Pilotbenutzern</span><span class="sxs-lookup"><span data-stu-id="f0284-124">Test MFA on your pilot users</span></span>

<span data-ttu-id="f0284-125">Wenn Sie die MFA anhand von Zugangsberechtigungsrichtlinien oder nach Benutzerkonto (nicht empfohlen) verwenden, sollten Sie Pilotbenutzer in Ihrem Unternehmen oder Ihrer Organisation auswählen, um die MFA-Registrierung und die Anmeldung zu testen. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f0284-125">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="f0284-126">Wenn Sie Zugangsberechtigungsrichtlinien verwenden, müssen Sie eine Pilotbenutzergruppe und eine entsprechende Richtlinie erstellen, die die MFA für die Mitglieder der Gruppe und alle Apps erforderlich macht.</span><span class="sxs-lookup"><span data-stu-id="f0284-126">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="f0284-127">Fügen Sie dann die Konten Ihrer Pilotbenutzer der Gruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="f0284-127">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="f0284-128">Wenn Sie die MFA nach Benutzerkonto verwenden, müssen Sie die MFA für die einzelnen Benutzerkonten Ihrer Pilotbenutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f0284-128">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="f0284-129">Arbeiten Sie mit Ihren Pilotbenutzern zusammen und klären Sie Fragen und Probleme, um auf eine reibungslose Bereitstellung für Ihre Organisation vorbereitet zu sein.</span><span class="sxs-lookup"><span data-stu-id="f0284-129">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="f0284-130">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="f0284-130">Step 3.</span></span> <span data-ttu-id="f0284-131">Informieren Sie Ihre Organisation, dass die MFA eingerichtet wird</span><span class="sxs-lookup"><span data-stu-id="f0284-131">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="f0284-132">Nutzen Sie E-Mail-Benachrichtigungen, Plakate, Teambesprechungen oder entsprechende Schulungen, um sicherzustellen, dass Ihre Mitarbeiter folgendes verstehen:</span><span class="sxs-lookup"><span data-stu-id="f0284-132">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="f0284-133">Warum die MFA für Anmeldungen erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="f0284-133">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="f0284-134">Wie sie sich für die zusätzliche Überprüfungsmethode registrieren</span><span class="sxs-lookup"><span data-stu-id="f0284-134">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="f0284-135">Wie sie sich nach der Registrierung anmelden</span><span class="sxs-lookup"><span data-stu-id="f0284-135">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="f0284-136">Wie sie die zusätzliche Überprüfungsmethode ändern können</span><span class="sxs-lookup"><span data-stu-id="f0284-136">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="f0284-137">Wie z. B. bei einem Wechsel des Smartphones vorgegangen werden muss</span><span class="sxs-lookup"><span data-stu-id="f0284-137">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="f0284-138">Stellen Sie vor allem sicher, dass Ihre Mitarbeiter verstehen ***ab wann die MFA Voraussetzung wird***, sodass es zu keinen Überraschungen kommt.</span><span class="sxs-lookup"><span data-stu-id="f0284-138">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="f0284-139">Schritt 4:</span><span class="sxs-lookup"><span data-stu-id="f0284-139">Step 4.</span></span> <span data-ttu-id="f0284-140">Bereitstellung der MFA für Ihre Organisation oder Benutzer</span><span class="sxs-lookup"><span data-stu-id="f0284-140">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="f0284-141">Stellen Sie die MFA, entsprechend der von Ihnen gewählten MFA-Methode, für alle Mitarbeiter bereit.</span><span class="sxs-lookup"><span data-stu-id="f0284-141">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="f0284-142">Standardsicherheitseinstellungen </span><span class="sxs-lookup"><span data-stu-id="f0284-142">Security defaults</span></span>

<span data-ttu-id="f0284-143">Die Standardsicherheitseinstellungen können Sie im Azure-Portal im Bereich **Einstellungen** für Active Directory (Azure AD) aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f0284-143">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="f0284-144">Melden Sie sich mit den Anmeldeinformationen des globalen Administrators beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="f0284-144">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="f0284-145">Wechseln Sie zur Seite [Azure Active Directory – Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="f0284-145">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="f0284-146">Wählen Sie unten auf der Seite **Standardsicherheitseinstellungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="f0284-146">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="f0284-147">Wählen Sie **Ja** aus, um die Standardsicherheitseinstellungen zu aktivieren und **Nein**, um die Standardsicherheitseinstellungen zu deaktivieren. Klicken Sie anschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f0284-147">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="f0284-148">Wenn Sie bisher [grundlegende Zugangsberechtigungsrichtlinien](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection) verwendet haben, gehen Sie folgendermaßen vor, um die Standardsicherheitseinstellungen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="f0284-148">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="f0284-149">Wechseln Sie zur Seite [Zugangsberechtigung – Richtlinien](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="f0284-149">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="f0284-150">Wählen Sie jede grundlegende Richtlinie aus, die auf **Ein** gesetzt ist und setzen Sie **Richtlinie aktivieren** auf **Aus**.</span><span class="sxs-lookup"><span data-stu-id="f0284-150">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="f0284-151">Wechseln Sie zur Seite [Azure Active Directory – Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="f0284-151">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="f0284-152">Wählen Sie unten auf der Seite **Standardsicherheitseinstellungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="f0284-152">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="f0284-153">Wählen Sie **Ja** aus, um die Standardsicherheitseinstellungen zu aktivieren und **Nein**, um die Standardsicherheitseinstellungen zu deaktivieren. Klicken Sie anschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f0284-153">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="f0284-154">Zugangsberechtigungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f0284-154">Conditional Access policies</span></span>

<span data-ttu-id="f0284-155">Erstellen, konfigurieren und aktivieren Sie die geeigneten Richtlinien für die Benutzergruppe, für die die MFA zur Anmeldung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f0284-155">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="f0284-156">MFA nach Benutzerkonto (nicht empfohlen)</span><span class="sxs-lookup"><span data-stu-id="f0284-156">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="f0284-157">Aktivieren Sie die Benutzerkonten entsprechend Ihrem Rollout für die MFA.</span><span class="sxs-lookup"><span data-stu-id="f0284-157">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="f0284-158">Unterstützung ihrer Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="f0284-158">Supporting your employees</span></span>

<span data-ttu-id="f0284-159">Wenn Ihre Mitarbeiter sich registrieren und die Anmeldung mittels MFA nutzen, sollten Sie sicherstellen, dass Ihre IT-Experten, Ihre IT-Abteilung oder Ihr Helpdesk Fragen beantworten und Probleme schnell beheben können.</span><span class="sxs-lookup"><span data-stu-id="f0284-159">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="f0284-160">In diesem Artikel finden Sie [Informationen zur Problembehandlung bei der Anmeldung mit MFA](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="f0284-160">See this article for [information about troubleshooting MFA sign-ins](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


