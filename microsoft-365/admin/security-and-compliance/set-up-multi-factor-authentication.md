---
title: Einrichten der mehrstufigen Authentifizierung für Office 365-Benutzer
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
description: Informationen zur Verwendung der Sicherheitsstandardeinstellungen zum Einrichten der mehrstufigen Authentifizierung für Office 365-Benutzer.
monikerRange: o365-worldwide
ms.openlocfilehash: 7e48f72f2fd8cfc5042bd15f994cc98bfa5fca8c
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2020
ms.locfileid: "43503971"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="d7a5d-103">Einrichten der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d7a5d-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d7a5d-104">Wenn Sie Ihr Abonnement oder eine Testversion nach dem 21. Oktober 2019 gekauft haben und Sie unerwarteterweise zur Eingabe einer mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) aufgefordert werden, wurden [Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch für Ihr Abonnement aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="d7a5d-105">Bei jedem neuen Office 365 Business- oder Microsoft 365 Business-Abonnement sind die Sicherheitseinstellungen automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-105">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="d7a5d-106">Dies bedeutet, dass jeder Benutzer MFA einrichten und die Microsoft Authenticator-App auf seinem mobilen Gerät installieren muss.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-106">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="d7a5d-107">Weitere Informationen finden Sie unter [Einrichten der Prüfung in zwei Schritten für Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="d7a5d-107">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="d7a5d-108">Für die folgenden neun Administratorrollen ist bei jeder Anmeldung eine zusätzliche Authentifizierung erforderlich:</span><span class="sxs-lookup"><span data-stu-id="d7a5d-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="d7a5d-109">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="d7a5d-109">Global administrator</span></span>
- <span data-ttu-id="d7a5d-110">SharePoint-Administrator</span><span class="sxs-lookup"><span data-stu-id="d7a5d-110">SharePoint administrator</span></span>
- <span data-ttu-id="d7a5d-111">Exchange-Administrator</span><span class="sxs-lookup"><span data-stu-id="d7a5d-111">Exchange administrator</span></span>
- <span data-ttu-id="d7a5d-112">Administrator für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="d7a5d-112">Conditional Access administrator</span></span>
- <span data-ttu-id="d7a5d-113">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="d7a5d-113">Security administrator</span></span>
- <span data-ttu-id="d7a5d-114">Helpdesk- oder Kennwortadministrator</span><span class="sxs-lookup"><span data-stu-id="d7a5d-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="d7a5d-115">Abrechnungsadministrator</span><span class="sxs-lookup"><span data-stu-id="d7a5d-115">Billing administrator</span></span>
- <span data-ttu-id="d7a5d-116">Benutzeradministrator</span><span class="sxs-lookup"><span data-stu-id="d7a5d-116">User administrator</span></span>
- <span data-ttu-id="d7a5d-117">Authentifizierungsadministrator</span><span class="sxs-lookup"><span data-stu-id="d7a5d-117">Authentication administrator</span></span>

<span data-ttu-id="d7a5d-118">Alle anderen Benutzer werden bei Bedarf zu einer weiteren Authentifizierung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="d7a5d-119">Weitere Informationen finden Sie unter [Was sind Sicherheitsstandards?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="d7a5d-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

> [!NOTE]
> <span data-ttu-id="d7a5d-120">Sie müssen ein Office 365 globaler Administrator sein, um MFA einzurichten oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-120">You must be an Office 365 global admin to set up or modify MFA.</span></span> <br><br>
> <span data-ttu-id="d7a5d-121">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="d7a5d-122">Wenn Sie zuvor die mehrstufige Authentifizierung mit Basisrichtlinien eingerichtet haben, müssen Sie [diese deaktivieren und die Standardsicherheitseinstellungen aktivieren](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="d7a5d-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="d7a5d-123">Wenn Sie jedoch über Microsoft 365 Business verfügen oder Ihr Abonnement [Azure Active Directory Premium P1 oder Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)enthält, können Sie auch Richtlinien für [bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) einrichten.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="d7a5d-124">Um Richtlinien für bedingten Zugriff zu verwenden, müssen Sie sicherstellen, dass die [moderne Authentifizierung](#enable-modern-authentication-for-your-organization) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="d7a5d-125">Wenn Sie Ihren Benutzern erklären möchten, wie die Authenticator-App eingerichtet wird, lesen Sie [Verwenden von Microsoft Authenticator mit Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="d7a5d-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="d7a5d-126">Verwalten von Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="d7a5d-126">Manage security defaults</span></span>

1. <span data-ttu-id="d7a5d-127">Melden Sie sich mit Ihren globalen Administratoranmeldeinformationen beim [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822) an.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-127">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="d7a5d-128">Wechseln Sie zu [Azure Active Directory-Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="d7a5d-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="d7a5d-129">Wählen Sie am unteren Rand der Seite **Sicherheitsstandards verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="d7a5d-130">Wählen Sie **Ja** aus, um Sicherheitsstandards zu aktivieren, oder **Nein** , um Sicherheitseinstellungen zu deaktivieren, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-130">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="d7a5d-131">Von Basisrichtlinien zu Sicherheitsstandards wechseln</span><span class="sxs-lookup"><span data-stu-id="d7a5d-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="d7a5d-132">Wählen Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822)die Option **Alle anzeigen**und dann **Azure Active Directory** unter **Admin**Center aus.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Show all**, and then **Azure Active Directory** under **Admin centers**.</span></span>

2. <span data-ttu-id="d7a5d-133">Wählen Sie im **Azure Active Directory Admin Center** **Azure Active Directory** > **Security**aus.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-133">In the  **Azure Active Directory admin center** choose **Azure Active Directory** > **Security**.</span></span>

3. <span data-ttu-id="d7a5d-134">Im Thema \*\*Sicherheit | \*\*Klicken Sie auf der Seite Erste Schritte **auf bedingter Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-134">On the **Security | Getting started** page, choose **Conditional Access**.</span></span> 

4. <span data-ttu-id="d7a5d-135">Wählen Sie auf der Seite **bedingte Zugriffs-Richtlinien** jede Basisrichtlinie aus, die **auf**ist, und legen Sie Sie auf **Off**fest.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-135">On the **Conditional Access - Policies** page, choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="d7a5d-136">Wechseln Sie zur Seite [Azure Active Directory-Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="d7a5d-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="d7a5d-137">Klicken Sie unten auf der Seite auf **Sicherheitsstandards verwalten**, und wählen Sie im Bereich **Sicherheitsstandard Einstellungen aktivieren** die Option **Sicherheits Standardwerte aktivieren** auf **Ja**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="d7a5d-138">Aktivieren der modernen Authentifizierung für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="d7a5d-138">Enable modern authentication for your organization</span></span>

<span data-ttu-id="d7a5d-139">Alle Office 2016-Clientanwendungen unterstützen MFA durch die Nutzung der Active Directory-Authentifizierungsbibliothek (Active Directory Authentication Library, ADAL).</span><span class="sxs-lookup"><span data-stu-id="d7a5d-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="d7a5d-140">Dies bedeutet, dass App-Kennwörter für Office 2016-Clients nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="d7a5d-141">Sie müssen jedoch sicherstellen, dass Ihr Office 365-Abonnement für ADAL oder die moderne Authentifizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-141">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="d7a5d-142">Wenn Sie die moderne Authentifizierung aktivieren möchten, wählen Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822) die Option **Einstellungen** \> **Einstellungen**, und dann auf der Registerkarte **Dienste** die Option **Moderne Authentifizierung** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="d7a5d-143">Aktivieren Sie das Kontrollkästchen **moderne Authentifizierung aktivieren (empfohlen)** im Bereich **moderne Authentifizierung** , und wählen Sie dann **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-143">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![Bereich "Moderne Authentifizierung" mit aktiviertem Kontrollkästchen "Moderne Authentifizierung aktivieren".](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="d7a5d-145">Seit August 2017 ist die moderne Authentifizierung (MA) auf allen neuen Office 365-Mandanten, die Skype for Business Online und Exchange Online umfassen, standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-145">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="d7a5d-146">Um Ihren MA-Status für Skype for Business Online zu überprüfen, können Sie Skype for Business Online-PowerShell mit Anmeldeinformationen eines globalen Administrators verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="d7a5d-147">Führen Sie "Get-CsOAuthConfiguration" aus, um die Ausgabe von "-ClientADALAuthOverride" zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="d7a5d-148">Wenn "-ClientADALAuthOverride" den Wert "Allowed" aufweist, ist die moderne Authentifizierung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d7a5d-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>

<span data-ttu-id="d7a5d-149">Informationen zum Überprüfen Ihres MA-Status für Exchange Online finden Sie unter [Aktivieren der modernen Authentifizierung in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="d7a5d-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="d7a5d-150">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="d7a5d-150">Related articles</span></span>

[<span data-ttu-id="d7a5d-151">Top 10 Methoden zum Sichern von Office 365 und Microsoft 365 Business-Pläne</span><span class="sxs-lookup"><span data-stu-id="d7a5d-151">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="d7a5d-152">Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten</span><span class="sxs-lookup"><span data-stu-id="d7a5d-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
