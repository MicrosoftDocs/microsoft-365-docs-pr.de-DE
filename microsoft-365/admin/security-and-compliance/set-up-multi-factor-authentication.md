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
ms.openlocfilehash: bc906299e42929dd4dd09b94502a6d463a5971b4
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254204"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="6f9b2-103">Einrichten der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="6f9b2-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="6f9b2-104">Bei jedem neuen Office 365 Business- oder Microsoft 365 Business-Abonnement sind die Sicherheitseinstellungen automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-104">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="6f9b2-105">Dies bedeutet, dass jeder Benutzer die mehrstufige Authentifizierung (MFA) einrichten und die Authenticator-App auf seinem mobilen Gerät installieren muss.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-105">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="6f9b2-106">Weitere Informationen finden Sie unter [Einrichten der Prüfung in zwei Schritten für Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="6f9b2-106">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="6f9b2-107">Für die folgenden neun Administratorrollen ist bei jeder Anmeldung eine zusätzliche Authentifizierung erforderlich:</span><span class="sxs-lookup"><span data-stu-id="6f9b2-107">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>
- <span data-ttu-id="6f9b2-108">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="6f9b2-108">Global administrator</span></span>
- <span data-ttu-id="6f9b2-109">SharePoint-Administrator</span><span class="sxs-lookup"><span data-stu-id="6f9b2-109">SharePoint administrator</span></span>
- <span data-ttu-id="6f9b2-110">Exchange-Administrator</span><span class="sxs-lookup"><span data-stu-id="6f9b2-110">Exchange administrator</span></span>
- <span data-ttu-id="6f9b2-111">Administrator für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="6f9b2-111">Conditional Access administrator</span></span>
- <span data-ttu-id="6f9b2-112">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="6f9b2-112">Security administrator</span></span>
- <span data-ttu-id="6f9b2-113">Helpdesk- oder Kennwortadministrator</span><span class="sxs-lookup"><span data-stu-id="6f9b2-113">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="6f9b2-114">Abrechnungsadministrator</span><span class="sxs-lookup"><span data-stu-id="6f9b2-114">Billing administrator</span></span>
- <span data-ttu-id="6f9b2-115">Benutzeradministrator</span><span class="sxs-lookup"><span data-stu-id="6f9b2-115">User administrator</span></span>
- <span data-ttu-id="6f9b2-116">Authentifizierungsadministrator</span><span class="sxs-lookup"><span data-stu-id="6f9b2-116">Authentication administrator</span></span>

<span data-ttu-id="6f9b2-117">Alle anderen Benutzer werden bei Bedarf zu einer weiteren Authentifizierung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-117">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="6f9b2-118">Weitere Informationen hierzu finden Sie unter [Was sind Standardsicherheitseinstellungen?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="6f9b2-118">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

> [!NOTE]
> <span data-ttu-id="6f9b2-p103">Sie müssen ein globaler Office 365-Administrator sein, um die mehrstufige Authentifizierung einzurichten oder zu ändern. </span><span class="sxs-lookup"><span data-stu-id="6f9b2-p103">You must be an Office 365 global admin to set up or modify multi-factor authentication. </span></span><br><br>
> <span data-ttu-id="6f9b2-120">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="6f9b2-121">Wenn Sie zuvor die mehrstufige Authentifizierung mit Basisrichtlinien eingerichtet haben, müssen Sie [diese deaktivieren und die Standardsicherheitseinstellungen aktivieren](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="6f9b2-121">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="6f9b2-122">Wenn Sie hingegen über Microsoft 365 Business verfügen oder Ihr Abonnement [Azure Active Directory Premium 1 oder Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/) enthält, können Sie auch Richtlinien für den [bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) einrichten.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="6f9b2-123">Um Richtlinien für den bedingten Zugriff verwenden zu können, müssen Sie sicherstellen, dass die Option für die [moderne Authentifizierung](#enable-multi-factor-authentication-for-your-organization) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-123">To use conditional access policies, you need to make sure [modern authentication is enabled](#enable-multi-factor-authentication-for-your-organization).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="6f9b2-124">Verwalten von Sicherheitsstandards</span><span class="sxs-lookup"><span data-stu-id="6f9b2-124">Manage security defaults</span></span>

1. <span data-ttu-id="6f9b2-125">Melden Sie sich beim [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822) mit Ihren globalen Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-125">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="6f9b2-126">Wechseln Sie zu [Azure Active Directory-Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="6f9b2-126">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>

3. <span data-ttu-id="6f9b2-127">Wählen Sie am unteren Rand der Seite **Sicherheitsstandards verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="6f9b2-128">Wählen Sie **Ja** aus, um Sicherheitsstandards zu aktivieren, und **Nein**, um Sicherheitsstandards zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-128">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="6f9b2-129">Von Basisrichtlinien zu Sicherheitsstandards wechseln</span><span class="sxs-lookup"><span data-stu-id="6f9b2-129">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="6f9b2-130">Wählen Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822) die Option **Setup** aus.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-130">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="6f9b2-131">Wählen Sie neben **Anmeldung und Sicherheit** unter **Anmeldung sicherer machen** die Option **Anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-131">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="6f9b2-132">Wählen Sie unter **Anmeldung sicherer machen** die Option **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-132">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="6f9b2-133">Wählen Sie auf der Seite **Bedingter Zugriff auf das Azure-Portal – Richtlinien** jede Basisrichtlinie aus, die **aktiviert** ist, und **deaktivieren** Sie sie.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-133">On the **Azure portal Conditional Access - Policies** page,  choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="6f9b2-134">Wechseln Sie zur Seite [Azure Active Directory-Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="6f9b2-134">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="6f9b2-135">Wählen Sie am unteren Rand der Seite **Sicherheitsstandards verwalten** aus, und legen Sie im Bereich **Sicherheitsstandards aktivieren** für die Option **Sicherheitsstandards aktivieren** **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-135">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="6f9b2-136">Aktivieren der modernen Authentifizierung für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="6f9b2-136">Enable Modern authentication for your organization</span></span>

<span data-ttu-id="6f9b2-137">Alle Office 2016-Clientanwendungen unterstützen MFA durch die Nutzung der Active Directory-Authentifizierungsbibliothek (Active Directory Authentication Library, ADAL).</span><span class="sxs-lookup"><span data-stu-id="6f9b2-137">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="6f9b2-138">Dies bedeutet, dass App-Kennwörter für Office 2016-Clients nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-138">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="6f9b2-139">Sie müssen jedoch sicherstellen, dass Ihr Office 365-Abonnement für ADAL oder die moderne Authentifizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-139">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="6f9b2-140">Wenn Sie die moderne Authentifizierung aktivieren möchten, wählen Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822) die Option **Einstellungen** \> **Einstellungen**, und dann auf der Registerkarte **Dienste** die Option **Moderne Authentifizierung** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="6f9b2-141">Aktivieren Sie das Kontrollkästchen **Moderne Authentifizierung aktivieren** im Bereich **Moderne Authentifizierung**.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-141">Check the **Enable modern authentication** box in the **Modern authentication** panel.</span></span> 

    ![Bereich "Moderne Authentifizierung" mit aktiviertem Kontrollkästchen "Moderne Authentifizierung aktivieren".](../media/enablemodernauth.png)
    
## <a name="enable-multi-factor-authentication-for-your-organization"></a><span data-ttu-id="6f9b2-143">Aktivieren der mehrstufigen Authentifizierung für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="6f9b2-143">Enable multi-factor authentication for your organization</span></span>
    
1. <span data-ttu-id="6f9b2-144">Wählen Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822)die Option **Users** und **Active Users**aus.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-144">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Users** and **Active Users**.</span></span>

2. <span data-ttu-id="6f9b2-145">Klicken Sie im Abschnitt **aktive Benutzer** auf mehrstufige **Authentifizierung**.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-145">In the **Active Users** section, Click on  **multi-factor authentication**.</span></span>

3. <span data-ttu-id="6f9b2-146">Wählen Sie auf der Seite mehrstufige **Authentifizierung** die Option **Benutzer** aus, wenn Sie dies für einen Benutzer aktivieren, oder Sie können eine **Massenaktualisierung**führen.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-146">On the **Multi-factor authentication** page, select **user** if you are enabling this for one user Or you can peform a **Bulk Update**.</span></span>

4. <span data-ttu-id="6f9b2-147">Klicken Sie unter **Quick Steps**auf **aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="6f9b2-147">CLick on **Enable** under **Quick Steps**.</span></span>

5. <span data-ttu-id="6f9b2-148">Klicken Sie im Popupfenster auf CLickc, um die mehrstufige **Authentifizierung zu aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-148">In the Pop-up window, CLickc on **Enable Multi-Factor Authentication**.</span></span>

<span data-ttu-id="6f9b2-149">Nachdem Sie die mehrstufige Authentifizierung für Ihre Organisation eingerichtet haben, müssen die Benutzer auf ihren Geräten die Prüfung in zwei Schritten einrichten.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-149">After you set up multi-factor authentication for your organization, your users will be required to set up two-step verification on their devices.</span></span> <span data-ttu-id="6f9b2-150">Weitere Informationen finden Sie unter [Einrichten der Prüfung in zwei Schritten für Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="6f9b2-150">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>
    
> [!TIP]
> <span data-ttu-id="6f9b2-151">Wenn Sie Ihren Benutzern erklären möchten, wie die Authenticator-App eingerichtet wird, lesen Sie [Verwenden von Microsoft Authenticator mit Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="6f9b2-151">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="6f9b2-152">Seit August 2017 ist die moderne Authentifizierung (MA) auf allen neuen Office 365-Mandanten, die Skype for Business Online und Exchange Online umfassen, standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-152">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="6f9b2-153">Um Ihren MA-Status für Skype for Business Online zu überprüfen, können Sie Skype for Business Online-PowerShell mit Anmeldeinformationen eines globalen Administrators verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-153">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="6f9b2-154">Führen Sie "Get-CsOAuthConfiguration" aus, um die Ausgabe von "-ClientADALAuthOverride" zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-154">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="6f9b2-155">Wenn "-ClientADALAuthOverride" den Wert "Allowed" aufweist, ist die moderne Authentifizierung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6f9b2-155">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="6f9b2-156">Informationen zum Überprüfen Ihres MA-Status für Exchange Online finden Sie unter [Aktivieren der modernen Authentifizierung in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="6f9b2-156">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="6f9b2-157">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="6f9b2-157">Related articles</span></span>

[<span data-ttu-id="6f9b2-158">Top 10 Methoden zum Sichern von Office 365 und Microsoft 365 Business-Pläne</span><span class="sxs-lookup"><span data-stu-id="6f9b2-158">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="6f9b2-159">Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten</span><span class="sxs-lookup"><span data-stu-id="6f9b2-159">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
