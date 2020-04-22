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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: In diesem Artikel erfahren Sie, wie Sie Sicherheitsstandards zum Einrichten der mehrstufigen Authentifizierung für Benutzer verwenden.
monikerRange: o365-worldwide
ms.openlocfilehash: 1000689794b8b5471efa898e731fd75a0e5a8cce
ms.sourcegitcommit: 7c0470fd7a98911d142bac060c228947c46a6be7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43665632"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="1091e-103">Einrichten der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="1091e-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1091e-104">Wenn Sie Ihr Abonnement oder eine Testversion nach dem 21. Oktober 2019 gekauft haben und Sie unerwarteterweise zur Eingabe einer mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) aufgefordert werden, wurden [Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch für Ihr Abonnement aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1091e-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="1091e-105">Für jedes neue Microsoft 365-Abonnement werden automatisch [Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1091e-105">Every new Microsoft 365 subscription will automatically have [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) turned on.</span></span> <span data-ttu-id="1091e-106">Dies bedeutet, dass jeder Benutzer die Multi-Factor Authentication (MFA) einrichten und die Microsoft Authenticator-App auf seinem mobilen Gerät installieren muss.</span><span class="sxs-lookup"><span data-stu-id="1091e-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="1091e-107">Weitere Informationen finden Sie unter [Einrichten von MFA für ein Microsoft 365-Konto](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="1091e-107">For more information, see [Set up MFA for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>

<span data-ttu-id="1091e-108">Für die folgenden neun Administratorrollen ist bei jeder Anmeldung eine zusätzliche Authentifizierung erforderlich:</span><span class="sxs-lookup"><span data-stu-id="1091e-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="1091e-109">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="1091e-109">Global administrator</span></span>
- <span data-ttu-id="1091e-110">SharePoint-Administrator</span><span class="sxs-lookup"><span data-stu-id="1091e-110">SharePoint administrator</span></span>
- <span data-ttu-id="1091e-111">Exchange-Administrator</span><span class="sxs-lookup"><span data-stu-id="1091e-111">Exchange administrator</span></span>
- <span data-ttu-id="1091e-112">Administrator für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="1091e-112">Conditional Access administrator</span></span>
- <span data-ttu-id="1091e-113">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="1091e-113">Security administrator</span></span>
- <span data-ttu-id="1091e-114">Helpdesk- oder Kennwortadministrator</span><span class="sxs-lookup"><span data-stu-id="1091e-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="1091e-115">Abrechnungsadministrator</span><span class="sxs-lookup"><span data-stu-id="1091e-115">Billing administrator</span></span>
- <span data-ttu-id="1091e-116">Benutzeradministrator</span><span class="sxs-lookup"><span data-stu-id="1091e-116">User administrator</span></span>
- <span data-ttu-id="1091e-117">Authentifizierungsadministrator</span><span class="sxs-lookup"><span data-stu-id="1091e-117">Authentication administrator</span></span>

<span data-ttu-id="1091e-118">Alle anderen Benutzer werden bei Bedarf zu einer weiteren Authentifizierung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="1091e-118">All other users will be asked to perform additional authentication when needed.</span></span>

> [!NOTE]
> <span data-ttu-id="1091e-119">Sie müssen ein globaler Administrator sein, um MFA einzurichten oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1091e-119">You must be a global admin to set up or modify MFA</span></span> <br><br>
> <span data-ttu-id="1091e-120">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="1091e-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="1091e-121">Wenn Sie zuvor MFA mit Basisrichtlinien eingerichtet haben, [müssen Sie diese deaktivieren, um Sicherheitsstandards zu aktivieren](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="1091e-121">If you have previously set up MFA with baseline policies, [you must turn them off to turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="1091e-122">Wenn Sie jedoch über Microsoft 365 Business verfügen oder Ihr Abonnement [Azure Active Directory Premium P1 oder Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)enthält, können Sie auch Richtlinien für [bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) einrichten.</span><span class="sxs-lookup"><span data-stu-id="1091e-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="1091e-123">Um Richtlinien für bedingten Zugriff zu verwenden, müssen Sie sicherstellen, dass die Sicherheitseinstellungen deaktiviert sind und die [moderne Authentifizierung](#enable-modern-authentication-for-your-organization) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1091e-123">To use Conditional Access policies, you need to make sure security defaults are disabled and [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="1091e-124">Um Ihren Benutzern zu erklären, wie Sie die Microsoft Authenticator-App einrichten, lesen Sie [Verwenden von Microsoft Authenticator mit Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span><span class="sxs-lookup"><span data-stu-id="1091e-124">To explain to your users how to set up the Microsoft Authenticator app, see [Use Microsoft Authenticator with Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="1091e-125">Verwalten von Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="1091e-125">Manage security defaults</span></span>

1. <span data-ttu-id="1091e-126">Melden Sie sich beim [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822) mit globalen Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="1091e-126">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with global admin credentials.</span></span>
2. <span data-ttu-id="1091e-127">Wechseln Sie zur [Seite Azure Active Directory-Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="1091e-127">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="1091e-128">Wählen Sie am unteren Rand der Seite **Sicherheitsstandards verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="1091e-128">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="1091e-129">Wählen Sie **Ja** aus, um Sicherheitsstandards zu aktivieren, und **Nein** , um Sicherheitsstandards zu deaktivieren, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="1091e-129">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="1091e-130">Von Basisrichtlinien zu Sicherheitsstandards wechseln</span><span class="sxs-lookup"><span data-stu-id="1091e-130">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="1091e-131">Wechseln Sie zur [Seite bedingte Zugriffs-Richtlinien](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="1091e-131">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="1091e-132">Wählen Sie die einzelnen Basisrichtlinien **aus, und legen** Sie die **Option Richtlinie aktivieren** auf **aus**fest.</span><span class="sxs-lookup"><span data-stu-id="1091e-132">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="1091e-133">Wechseln Sie zur [Seite Azure Active Directory-Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="1091e-133">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="1091e-134">Klicken Sie unten auf der Seite auf **Sicherheitsstandards verwalten**, und wählen Sie im Bereich **Sicherheitsstandard Einstellungen aktivieren** die Option **Sicherheits Standardwerte aktivieren** auf **Ja**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1091e-134">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="1091e-135">Aktivieren der modernen Authentifizierung für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="1091e-135">Enable modern authentication for your organization</span></span>

<span data-ttu-id="1091e-136">Alle Office 2016-Clientanwendungen unterstützen MFA durch die Nutzung der Active Directory-Authentifizierungsbibliothek (Active Directory Authentication Library, ADAL).</span><span class="sxs-lookup"><span data-stu-id="1091e-136">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="1091e-137">Dies bedeutet, dass App-Kennwörter für Office 2016-Clients nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1091e-137">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="1091e-138">Sie müssen jedoch sicherstellen, dass Ihr Microsoft 365-Abonnement für Adal oder moderne Authentifizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1091e-138">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="1091e-139">Wenn Sie die moderne Authentifizierung aktivieren möchten, wählen Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822) die Option **Einstellungen** \> **Einstellungen**, und dann auf der Registerkarte **Dienste** die Option **Moderne Authentifizierung** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="1091e-139">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="1091e-140">Aktivieren Sie das Kontrollkästchen **moderne Authentifizierung aktivieren (empfohlen)** im Bereich **moderne Authentifizierung** , und wählen Sie dann **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="1091e-140">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![Bereich "Moderne Authentifizierung" mit aktiviertem Kontrollkästchen "Moderne Authentifizierung aktivieren".](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="1091e-142">Ab August 2017 werden alle neuen Microsoft 365-Abonnements, die Skype for Business Online und Exchange Online einschließen, standardmäßig mit moderner Authentifizierung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1091e-142">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="1091e-143">Um Ihren MA-Status für Skype for Business Online zu überprüfen, können Sie Skype for Business Online-PowerShell mit Anmeldeinformationen eines globalen Administrators verwenden.</span><span class="sxs-lookup"><span data-stu-id="1091e-143">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="1091e-144">Führen Sie "Get-CsOAuthConfiguration" aus, um die Ausgabe von "-ClientADALAuthOverride" zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1091e-144">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="1091e-145">Wenn "-ClientADALAuthOverride" den Wert "Allowed" aufweist, ist die moderne Authentifizierung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1091e-145">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="1091e-146">Informationen zum Überprüfen Ihres MA-Status für Exchange Online finden Sie unter [Aktivieren der modernen Authentifizierung in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="1091e-146">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="1091e-147">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="1091e-147">Related articles</span></span>

[<span data-ttu-id="1091e-148">Die 10 wichtigsten Möglichkeiten zum Sichern von Microsoft 365 for Business-Plänen</span><span class="sxs-lookup"><span data-stu-id="1091e-148">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="1091e-149">Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten</span><span class="sxs-lookup"><span data-stu-id="1091e-149">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
