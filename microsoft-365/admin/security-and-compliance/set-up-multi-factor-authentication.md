---
title: Einrichten der mehrstufigen Authentifizierung für Benutzer
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
description: Hier erfahren Sie, wie Sie die mehrstufige Authentifizierung für Ihre Organisation einrichten.
monikerRange: o365-worldwide
ms.openlocfilehash: c84c66cc051363fbc582abfb5521f922440b6801
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432379"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="fe4bb-103">Einrichten der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fe4bb-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="fe4bb-104">Basierend auf Ihrem Verständnis der [mehrstufigen Authentifizierung (MFA) und seiner Unterstützung in Microsoft 365](multi-factor-authentication-microsoft-365.md)ist es an der Zeit, es einzurichten und für Ihre Organisation bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="fe4bb-105">Bevor Sie beginnen, sollten Sie feststellen, ob diese speziellen Bedingungen auf Sie zutreffen, und die entsprechende Aktion durchführen:</span><span class="sxs-lookup"><span data-stu-id="fe4bb-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="fe4bb-106">Wenn Sie Office 2013 Clients auf Windows-Geräten haben, aktivieren Sie die [moderne Authentifizierung](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="fe4bb-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="fe4bb-107">Wenn Sie über Drittanbieter-Verzeichnisdienste mit Active Directory Verbunddienste (AD FS) verfügen, richten Sie den Azure MFA-Server ein.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="fe4bb-108">Weitere Informationen finden Sie unter [Erweiterte Szenarien mit mehrstufiger Azure-Authentifizierung und VPN-Lösungen von Drittanbietern](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) .</span><span class="sxs-lookup"><span data-stu-id="fe4bb-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="fe4bb-109">Schritt 1: entscheiden Sie sich für die Methode, dass Ihre Benutzer MFA verwenden</span><span class="sxs-lookup"><span data-stu-id="fe4bb-109">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="fe4bb-110">Sie müssen ein globaler Administrator sein, um MFA einzurichten oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-110">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="fe4bb-111">Es gibt drei Möglichkeiten, Ihre Benutzer zur Verwendung von MFA für die Anmeldung zu zwingen. Details finden Sie unter [MFA Support in Microsoft 365](multi-factor-authentication-microsoft-365.md) .</span><span class="sxs-lookup"><span data-stu-id="fe4bb-111">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="fe4bb-112">Sicherheitsstandards (empfohlen für kleine Unternehmen)</span><span class="sxs-lookup"><span data-stu-id="fe4bb-112">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="fe4bb-113">Wenn Sie Ihr Abonnement oder eine Testversion nach dem 21. Oktober 2019 gekauft haben und Sie unerwarteterweise zur MFA aufgefordert werden, wurden [Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) für Ihr Abonnement automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-113">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="fe4bb-114">Für jedes neue Microsoft 365-Abonnement werden automatisch Sicherheitsstandards aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-114">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="fe4bb-115">Dies bedeutet, dass jeder Benutzer MFA einrichten und die Microsoft Authenticator-App auf seinem mobilen Gerät installieren muss.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-115">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="fe4bb-116">Alle Benutzer müssen die Microsoft Authenticator-App verwenden, da ihre zusätzliche Überprüfungsmethode und die Legacy Authentifizierung blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-116">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="fe4bb-117">Richtlinien für bedingten Zugriff (empfohlen für Unternehmen)</span><span class="sxs-lookup"><span data-stu-id="fe4bb-117">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="fe4bb-118">Benutzer wählen die zusätzliche Überprüfungsmethode während der MFA-Registrierung aus.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-118">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="fe4bb-119">Konto pro Benutzer (nicht empfohlen)</span><span class="sxs-lookup"><span data-stu-id="fe4bb-119">Per-user account (not recommended)</span></span>

  <span data-ttu-id="fe4bb-120">Benutzer wählen die zusätzliche Überprüfungsmethode während der MFA-Registrierung aus.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-120">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="fe4bb-121">Schritt 2:</span><span class="sxs-lookup"><span data-stu-id="fe4bb-121">Step 2.</span></span> <span data-ttu-id="fe4bb-122">Testen Sie MFA auf Ihren Pilotbenutzern.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-122">Test MFA on your pilot users</span></span>

<span data-ttu-id="fe4bb-123">Wenn Sie Richtlinien für bedingten Zugriff oder MFA auf Benutzerbasis (nicht empfohlen) verwenden, wählen Sie Pilotbenutzer in Ihrem Unternehmen oder Ihrer Organisation aus, um die MFA-Registrierung und-Anmeldung zu testen. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fe4bb-123">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="fe4bb-124">Erstellen Sie für Richtlinien für bedingten Zugriff eine Pilotbenutzergruppe und eine Richtlinie, die MFA für die Mitglieder der Gruppe und für alle apps erfordert.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-124">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="fe4bb-125">Fügen Sie dann die Konten Ihres Pilot Benutzers zur Gruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-125">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="fe4bb-126">Aktivieren Sie für den MFA pro Benutzer die Option MFA für die Benutzerkonten ihrer Pilotbenutzer jeweils.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-126">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="fe4bb-127">Arbeiten Sie mit ihren Pilotbenutzern zusammen, um Fragen und Probleme zur Vorbereitung auf ein reibungsloses Rollout in Ihrer Organisation zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-127">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="fe4bb-128">SCHRITT 3:</span><span class="sxs-lookup"><span data-stu-id="fe4bb-128">Step 3.</span></span> <span data-ttu-id="fe4bb-129">Informieren Sie Ihre Organisation, dass MFA kommt</span><span class="sxs-lookup"><span data-stu-id="fe4bb-129">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="fe4bb-130">Verwenden Sie e-Mail-Benachrichtigungen, Flur Poster, Teambesprechungen oder formelle Schulungen, um sicherzustellen, dass Ihre Mitarbeiter Folgendes verstehen:</span><span class="sxs-lookup"><span data-stu-id="fe4bb-130">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="fe4bb-131">Warum MFA für Anmeldungen erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="fe4bb-131">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="fe4bb-132">Registrieren für die zusätzliche Überprüfungsmethode</span><span class="sxs-lookup"><span data-stu-id="fe4bb-132">How to register for their additional verification method</span></span>](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [<span data-ttu-id="fe4bb-133">Vorgehensweise anmelden nach der Registrierung</span><span class="sxs-lookup"><span data-stu-id="fe4bb-133">How to sign-in after registration</span></span>](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="fe4bb-134">Vorgehensweise ändern ihrer zusätzlichen Überprüfungsmethode</span><span class="sxs-lookup"><span data-stu-id="fe4bb-134">How to change their additional verification method</span></span>](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="fe4bb-135">Umgang mit Situationen wie ein neues Smartphone</span><span class="sxs-lookup"><span data-stu-id="fe4bb-135">How to deal with situations like a new smart phone</span></span>](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="fe4bb-136">Stellen Sie sicher, dass Ihre Mitarbeiter verstehen, ***wann die MFA-Anforderung auferlegt*** wird, damit Sie nicht überrascht.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-136">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="fe4bb-137">Schritt 4:</span><span class="sxs-lookup"><span data-stu-id="fe4bb-137">Step 4.</span></span> <span data-ttu-id="fe4bb-138">Rollout der MFA-Anforderung für Ihre Organisation oder Benutzer</span><span class="sxs-lookup"><span data-stu-id="fe4bb-138">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="fe4bb-139">Stellen Sie basierend auf der ausgewählten MFA-Anforderungsmethode die MFA-Authentifizierung für die Mitarbeiter außerhalb ihrer Pilottester bereit.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-139">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="fe4bb-140">Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="fe4bb-140">Security defaults</span></span>

<span data-ttu-id="fe4bb-141">Sie aktivieren oder deaktivieren Sicherheitseinstellungen im **Eigenschaften** Bereich für Azure Active Directory (Azure AD) im Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-141">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="fe4bb-142">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit globalen Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-142">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="fe4bb-143">Wechseln Sie zur [Seite Azure Active Directory-Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="fe4bb-143">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="fe4bb-144">Wählen Sie am unteren Rand der Seite **Sicherheitsstandards verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-144">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="fe4bb-145">Wählen Sie **Ja** aus, um Sicherheitsstandards zu aktivieren, und **Nein** , um Sicherheitsstandards zu deaktivieren, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-145">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="fe4bb-146">Wenn Sie [grundlegende Richtlinien für bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)verwendet haben, erfahren Sie hier, wie Sie mit Sicherheitsstandards fortfahren.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-146">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="fe4bb-147">Wechseln Sie zur [Seite bedingte Zugriffs-Richtlinien](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="fe4bb-147">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="fe4bb-148">Wählen Sie die einzelnen Basisrichtlinien **aus, und legen** Sie die **Option Richtlinie aktivieren** auf **aus**fest.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-148">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="fe4bb-149">Wechseln Sie zur [Seite Azure Active Directory-Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="fe4bb-149">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="fe4bb-150">Wählen Sie am unteren Rand der Seite **Sicherheitsstandards verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-150">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="fe4bb-151">Wählen Sie **Ja** aus, um Sicherheitsstandards zu aktivieren, und **Nein** , um Sicherheitsstandards zu deaktivieren, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-151">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="fe4bb-152">Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="fe4bb-152">Conditional Access policies</span></span>

<span data-ttu-id="fe4bb-153">Erstellen, konfigurieren und aktivieren Sie die entsprechenden Richtlinien, die die Gruppe von Benutzern enthalten, die MFA für die Anmeldung benötigen.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-153">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="fe4bb-154">MFA pro Benutzer (nicht empfohlen)</span><span class="sxs-lookup"><span data-stu-id="fe4bb-154">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="fe4bb-155">Aktivieren Sie Benutzerkonten für den MFA, der Ihrem Rollout entspricht.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-155">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="fe4bb-156">Unterstützung ihrer Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="fe4bb-156">Supporting your employees</span></span>

<span data-ttu-id="fe4bb-157">Wenn sich Ihre Mitarbeiter registrieren und mit der Anmeldung bei MFA beginnen, stellen Sie sicher, dass Ihre IT-Spezialisten, die IT-Abteilung oder der Helpdesk Fragen beantworten und Probleme schnell beheben können.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-157">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="fe4bb-158">In diesem Artikel finden Sie [Informationen zur Problembehandlung bei MFA-Anmeldungen](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="fe4bb-158">See this article for [information about troubleshooting MFA sign-ins](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


