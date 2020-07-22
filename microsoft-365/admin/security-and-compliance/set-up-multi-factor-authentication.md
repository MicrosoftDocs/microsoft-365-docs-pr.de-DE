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
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Hier erfahren Sie, wie Sie die Multi-Faktor-Authentifizierung für Ihre Organisation einrichten.
monikerRange: o365-worldwide
ms.openlocfilehash: 34133f4204c1ee305b0a249a0ff8e0e9edaf5599
ms.sourcegitcommit: e891c7c25f351f10f250af3f483f68594976ddc9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "45153677"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="a6fac-103">Einrichten der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a6fac-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="a6fac-104">Ihre Kenntnis der [Multi-Faktor-Authentifizierung (MFA) und deren Unterstützung in Microsoft 365](multi-factor-authentication-microsoft-365.md) vorausgesetzt, ist es an der Zeit, diese einzurichten und für Ihre Organisation bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a6fac-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6fac-105">Wenn Sie Ihr Abonnement oder Ihre Testversion nach dem 21. Oktober 2019 erworben haben und beim Anmelden eine MFA-Aufforderung erhalten, wurden automatisch die [Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) für Ihr Abonnement aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a6fac-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="a6fac-106">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="a6fac-106">Before you begin</span></span>

- <span data-ttu-id="a6fac-107">Sie müssen globaler Administrator sein, um MFA zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="a6fac-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="a6fac-108">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a6fac-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="a6fac-109">Wenn Sie das veraltete MFA auf Benutzerbasis aktiviert haben, [Legacy-MFA auf Benutzerbasis](#turn-off-legacy-per-person-mfa).</span><span class="sxs-lookup"><span data-stu-id="a6fac-109">If you have legacy per person MFA turned on, [Turn off legacy per person MFA](#turn-off-legacy-per-person-mfa).</span></span>
- <span data-ttu-id="a6fac-110">Wenn Office 2013-Clients auf Windows-Geräten installiert sind, [aktivieren Sie die moderne Authentifizierung für Office 2013-Clients](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="a6fac-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>
- <span data-ttu-id="a6fac-111">Erweitert: Wenn Verzeichnisdienste von Drittanbietern mit Active Directory Federation Services (AD FS) genutzt werden, richten Sie den Azure MFA-Server ein.</span><span class="sxs-lookup"><span data-stu-id="a6fac-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="a6fac-112">Weitere Informationen finden Sie unter [Erweiterte Szenarien mit Azure Multi-Faktor-Authentifizierung und VPN-Lösungen von Drittanbietern](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn).</span><span class="sxs-lookup"><span data-stu-id="a6fac-112">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="a6fac-113">Aktivieren oder Deaktivieren von Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="a6fac-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="a6fac-114">In den meisten Organisationen bieten Sicherheitsstandards ein gutes Maß an zusätzlicher Anmeldesicherheit.</span><span class="sxs-lookup"><span data-stu-id="a6fac-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="a6fac-115">Weitere Informationen hierzu finden Sie unter [Was sind Sicherheitsstandards?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="a6fac-115">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="a6fac-116">Wenn Ihr Abonnement neu ist, sind die Sicherheitsstandards möglicherweise bereits automatisch für Sie aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a6fac-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="a6fac-117">Die Standardsicherheitseinstellungen können Sie im Azure-Portal im Bereich **Einstellungen** für Active Directory (Azure AD) aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a6fac-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="a6fac-118">Melden Sie sich mit den Anmeldeinformationen des globalen Administrators beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="a6fac-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="a6fac-119">Wählen Sie im linken Navigationsbereich **Alle anzeigen** und dann unter **Admin Center** die Option **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="a6fac-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="a6fac-120">Im **Azure Active Directory Admin Center** wählen Sie dann **Azure Active Directory** > **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="a6fac-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** > **Properties**.</span></span>
3.  <span data-ttu-id="a6fac-121">Wählen Sie unten auf der Seite **Sicherheitsstandards verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="a6fac-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="a6fac-122">Wählen Sie **Ja** aus, um die zu aktivieren oder **Nein**, um die Sicherheitsstandards zu deaktivieren. Klicken Sie anschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a6fac-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="a6fac-123">Wenn Sie bisher [Basisrichtlinien für den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection) verwendet haben, werden Sie aufgefordert, diese zu deaktivieren, bevor Sie Sicherheitsstandards nutzen.</span><span class="sxs-lookup"><span data-stu-id="a6fac-123">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1.  <span data-ttu-id="a6fac-124">Wechseln Sie zur Seite [Zugangsberechtigung – Richtlinien](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="a6fac-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="a6fac-125">Wählen Sie jede grundlegende Richtlinie aus, die auf **Ein** gesetzt ist und setzen Sie **Richtlinie aktivieren** auf **Aus**.</span><span class="sxs-lookup"><span data-stu-id="a6fac-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="a6fac-126">Wechseln Sie zur Seite [Azure Active Directory – Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="a6fac-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="a6fac-127">Wählen Sie unten auf der Seite **Standardsicherheitseinstellungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="a6fac-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="a6fac-128">Wählen Sie **Ja** aus, um die Standardsicherheitseinstellungen zu aktivieren und **Nein**, um die Standardsicherheitseinstellungen zu deaktivieren. Klicken Sie anschließend auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a6fac-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="a6fac-129">Verwenden von Richtlinien für den bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="a6fac-129">Use Conditional Access policies</span></span>

<span data-ttu-id="a6fac-130">Wenn Ihre Organisation detailliertere Anforderungen an die Anmeldesicherheit hat, können Richtlinien für den bedingten Zugriff Ihnen mehr Kontrolle bieten.</span><span class="sxs-lookup"><span data-stu-id="a6fac-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="a6fac-131">Mit bedingtem Zugriff können Sie Richtlinien erstellen und definieren, die auf Anmeldeereignisse reagieren und zusätzliche Aktionen anfordern, bevor einem Benutzer der Zugriff auf eine Anwendung oder einen Dienst gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="a6fac-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6fac-132">Deaktivieren Sie sowohl "MFA auf Benutzerbasis"als auch "Sicherheitsstandards, bevor Sie die Richtlinien für den bedingten Zugriff aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a6fac-132">Turn off both per person MFA and Security defaults before you enable Conditional Access policies.</span></span> 

<span data-ttu-id="a6fac-133">Bedingter Zugriff ist für Kunden verfügbar, die Azure AD Premium P1 oder Lizenzen erworben haben, die dies beinhalten, wie z. B. Microsoft 365 Business Premium und Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="a6fac-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="a6fac-134">Weitere Informationen finden Sie unter [Erstellen einer Richtlinie für den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span><span class="sxs-lookup"><span data-stu-id="a6fac-134">For more information, see [create a Conditional Access policy](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="a6fac-135">Risikobasierter bedingter Zugriff ist in der Azure AD Premium P2-Lizenz oder Lizenzen, die diese umfassen, verfügbar, z. B. Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a6fac-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licences that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="a6fac-136">Weitere Informationen finden Sie unter [Risikoabhängiger bedingter Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span><span class="sxs-lookup"><span data-stu-id="a6fac-136">For more information, see [risk-based Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

<span data-ttu-id="a6fac-137">Weitere Informationen zu Azure AD P1 und P2 finden Sie unter [Azure Active Directory – Preise](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="a6fac-137">For more information about the Azure AD P1 and P2, see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="a6fac-138">Aktivieren von moderner Authentifizierung für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="a6fac-138">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="a6fac-139">Bei den meisten Abonnements ist die moderne Authentifizierung automatisch aktiviert, aber wenn Sie Ihr Abonnement vor langer Zeit erworben haben, ist dies möglicherweise nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="a6fac-139">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription a long time ago, it might not be.</span></span> <span data-ttu-id="a6fac-140">Die moderne Authentifizierung muss aktiviert werden, bevor MFA mit Office-Apps angemessen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a6fac-140">This has to be turned on before MFA works appropriately with Office apps.</span></span>

1. <span data-ttu-id="a6fac-141">Wählen Sie im Microsoft 365 Admin Center im linken Navigationsbereich **Einstellungen** > **Organisationseinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="a6fac-141">In the Microsoft 365 admin center, in the left nav choose **Settings** > **Org settings**.</span></span>
1. <span data-ttu-id="a6fac-142">Wählen Sie auf der Registerkarte **Dienste** die **moderne Authentifizierung** aus, und vergewissern Sie sich, dass im Bereich **Moderne Authentifizierung** die Option **Moderne Authentifizierung aktivieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a6fac-142">Under **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="a6fac-143">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="a6fac-143">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-person-mfa"></a><span data-ttu-id="a6fac-144">Deaktivieren der Legacy-MFA auf Benutzerbasis</span><span class="sxs-lookup"><span data-stu-id="a6fac-144">Turn off legacy per person MFA</span></span>

<span data-ttu-id="a6fac-145">Wenn bisher die veraltete MFA auf Benutzerbasis aktiviert ist, müssen Sie diese deaktivieren, bevor Sie "Sicherheitsstandards" aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a6fac-145">If you have previously turned on per person MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="a6fac-146">Wählen Sie im Microsoft 365 Admin Center im linken Navigationsbereich **Benutzer** > **Aktive Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="a6fac-146">In the Microsoft 365 admin center, in the left nav choose **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="a6fac-147">Wählen Sie auf der Seite **Aktive Benutzer** die Option **Mehrstufige Authentifizierung** aus.</span><span class="sxs-lookup"><span data-stu-id="a6fac-147">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="a6fac-148">Wählen Sie auf der Seite "Mehrstufige Authentifizierung" jeden Benutzer aus, und setzen Sie Status für die mehrstufige Authentifizierung auf **Deaktiviert**.</span><span class="sxs-lookup"><span data-stu-id="a6fac-148">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a6fac-149">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a6fac-149">Next steps</span></span>

- [<span data-ttu-id="a6fac-150">Wie sie sich für die zusätzliche Überprüfungsmethode registrieren</span><span class="sxs-lookup"><span data-stu-id="a6fac-150">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="a6fac-151">Wie sie sich nach der Registrierung anmelden</span><span class="sxs-lookup"><span data-stu-id="a6fac-151">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="a6fac-152">Wie sie die zusätzliche Überprüfungsmethode ändern können</span><span class="sxs-lookup"><span data-stu-id="a6fac-152">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="a6fac-153">Wie z. B. bei einem Wechsel des Smartphones vorgegangen werden muss</span><span class="sxs-lookup"><span data-stu-id="a6fac-153">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)
- [<span data-ttu-id="a6fac-154">Problembehandlung bei MFA-Anmeldungen</span><span class="sxs-lookup"><span data-stu-id="a6fac-154">Troubleshoot MFA sign-ins</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)




