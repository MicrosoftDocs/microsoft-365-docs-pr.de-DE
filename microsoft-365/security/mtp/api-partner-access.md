---
title: Partnerzugriff über Microsoft 365 Defender-APIs
description: Erfahren Sie, wie Sie eine App erstellen, um im Namen Ihrer Benutzer programmgesteuerten Zugriff auf Microsoft 365 Defender zu erhalten.
keywords: Partner, Zugriff, API, Mehr mandant, Zustimmung, Zugriffstoken, App
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 07afb0baf5c115f2029abfe03795b081a4f253a8
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929398"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a><span data-ttu-id="f61f0-104">Erstellen einer App mit Partnerzugriff auf Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="f61f0-104">Create an app with partner access to Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f61f0-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f61f0-105">**Applies to:**</span></span>

- <span data-ttu-id="f61f0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f61f0-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f61f0-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="f61f0-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f61f0-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="f61f0-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="f61f0-109">Auf dieser Seite wird beschrieben, wie Sie eine Azure Active Directory-App erstellen, die programmgesteuerten Zugriff auf Microsoft 365 Defender im Namen von Benutzern in mehreren Mandanten hat.</span><span class="sxs-lookup"><span data-stu-id="f61f0-109">This page describes how to create an Azure Active Directory app that has programmatic access to Microsoft 365 Defender, on behalf of users across multiple tenants.</span></span> <span data-ttu-id="f61f0-110">Apps mit mehreren Mandanten n</span><span class="sxs-lookup"><span data-stu-id="f61f0-110">Multi-tenant apps are useful for serving large groups of users.</span></span>

<span data-ttu-id="f61f0-111">Wenn Sie programmgesteuerten Zugriff auf Microsoft 365 Defender im Namen eines einzelnen Benutzers benötigen, lesen Sie "Erstellen einer App für den Zugriff auf [Microsoft 365 Defender-APIs](api-create-app-user-context.md)im Auftrag eines Benutzers".</span><span class="sxs-lookup"><span data-stu-id="f61f0-111">If you need programmatic access to Microsoft 365 Defender on behalf of a single user, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md).</span></span> <span data-ttu-id="f61f0-112">Wenn Sie Zugriff benötigen, ohne dass ein Benutzer explizit definiert ist (z. B. wenn Sie eine Hintergrund-App oder einen Daemon schreiben), lesen Sie "Erstellen einer App für den Zugriff auf [Microsoft 365 Defender ohne Benutzer".](api-create-app-web.md)</span><span class="sxs-lookup"><span data-stu-id="f61f0-112">If you need access without a user explicitly defined (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="f61f0-113">Wenn Sie nicht sicher sind, welche Art von Zugriff Sie benötigen, lesen Sie ["Erste Schritte".](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="f61f0-113">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="f61f0-114">Microsoft 365 Defender macht einen Großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f61f0-114">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="f61f0-115">Mit diesen APIs können Sie Workflows automatisieren und die Funktionen von Microsoft 365 Defender nutzen.</span><span class="sxs-lookup"><span data-stu-id="f61f0-115">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="f61f0-116">Für diesen ZUGRIFF auf die API ist die OAuth2.0-Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f61f0-116">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="f61f0-117">Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="f61f0-117">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="f61f0-118">Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um diese APIs zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="f61f0-118">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="f61f0-119">Erstellen Sie eine Azure Active Directory (Azure AD)-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f61f0-119">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="f61f0-120">Mit dieser Anwendung können Sie ein Zugriffstoken erhalten.</span><span class="sxs-lookup"><span data-stu-id="f61f0-120">Get an access token using this application.</span></span>
- <span data-ttu-id="f61f0-121">Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f61f0-121">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="f61f0-122">Da diese App mehrere Mandanten hat, [](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) benötigen Sie auch die Administratoreinwilligung von jedem Mandanten im Namen seiner Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f61f0-122">Since this app is multi-tenant, you'll also need [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) from each tenant on behalf of its users.</span></span>

<span data-ttu-id="f61f0-123">In diesem Artikel wird erläutert, wie Sie:</span><span class="sxs-lookup"><span data-stu-id="f61f0-123">This article explains how to:</span></span>

- <span data-ttu-id="f61f0-124">Erstellen einer **mehrstufigen Azure AD-Anwendung**</span><span class="sxs-lookup"><span data-stu-id="f61f0-124">Create a **multi-tenant** Azure AD application</span></span>
- <span data-ttu-id="f61f0-125">Holen Sie sich autorisierte Zustimmung von Ihrem Benutzeradministrator für Ihre Anwendung, um auf die benötigten Ressourcen von Microsoft 365 Defender zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f61f0-125">Get authorized consent from your user administrator for your application to access the Microsoft 365 Defender that resources it needs.</span></span>
- <span data-ttu-id="f61f0-126">Erhalten eines Zugriffstokens für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f61f0-126">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="f61f0-127">Überprüfen des Tokens</span><span class="sxs-lookup"><span data-stu-id="f61f0-127">Validate the token</span></span>

<span data-ttu-id="f61f0-128">Microsoft 365 Defender macht einen Großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f61f0-128">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="f61f0-129">Diese APIs helfen Ihnen bei der Automatisierung von Arbeitsflüssen und Innovationen basierend auf microsoft 365 Defender-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="f61f0-129">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="f61f0-130">Der Zugriff auf die API erfordert die OAuth2.0-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f61f0-130">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="f61f0-131">Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="f61f0-131">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="f61f0-132">Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="f61f0-132">In general, you’ll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="f61f0-133">Erstellen Sie **eine azure ad-Anwendung mit** mehreren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="f61f0-133">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="f61f0-134">Lassen Sie sich von Ihrem Benutzeradministrator autorisiert (zustimmung) für Ihre Anwendung, um auf die benötigten Microsoft 365 Defender-Ressourcen zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f61f0-134">Get authorized (consent) by your user administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="f61f0-135">Mit dieser Anwendung können Sie ein Zugriffstoken erhalten.</span><span class="sxs-lookup"><span data-stu-id="f61f0-135">Get an access token using this application.</span></span>
- <span data-ttu-id="f61f0-136">Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f61f0-136">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="f61f0-137">Die folgenden Schritte mit Anleitungen zum Erstellen einer azure ad-Anwendung mit mehreren Mandanten, zum Erhalten eines Zugriffstokens für Microsoft 365 Defender und zum Überprüfen des Tokens.</span><span class="sxs-lookup"><span data-stu-id="f61f0-137">The following steps with guide you how to create a multi-tenant Azure AD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="f61f0-138">Erstellen der mehrstufigen App</span><span class="sxs-lookup"><span data-stu-id="f61f0-138">Create the multi-tenant app</span></span>

1. <span data-ttu-id="f61f0-139">Melden Sie sich [bei Azure](https://portal.azure.com) als Benutzer mit der rolle **"Globaler Administrator"** an.</span><span class="sxs-lookup"><span data-stu-id="f61f0-139">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="f61f0-140">Navigieren Sie zu **Azure Active**  >  **Directory-App-Registrierungen**  >  **Neue Registrierung.**</span><span class="sxs-lookup"><span data-stu-id="f61f0-140">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="f61f0-142">Im Registrierungsformular:</span><span class="sxs-lookup"><span data-stu-id="f61f0-142">In the registration form:</span></span>

   - <span data-ttu-id="f61f0-143">Wählen Sie einen Namen für Ihre Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="f61f0-143">Choose a name for your application.</span></span>
   - <span data-ttu-id="f61f0-144">Wählen **Sie unter den unterstützten** Kontotypen Konten in einem **beliebigen Organisationsverzeichnis (Beliebiges Azure AD-Verzeichnis) – Mehrant aus.**</span><span class="sxs-lookup"><span data-stu-id="f61f0-144">From **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory) - Multitenant**.</span></span>
   - <span data-ttu-id="f61f0-145">Füllen Sie den Abschnitt **"Umleitungs-URI"** aus.</span><span class="sxs-lookup"><span data-stu-id="f61f0-145">Fill out the **Redirect URI** section.</span></span> <span data-ttu-id="f61f0-146">Wählen Sie **"Web"** aus, und geben Sie den Umleitungs-URI **https://portal.azure.com** als .</span><span class="sxs-lookup"><span data-stu-id="f61f0-146">Select type **Web** and give the redirect URI as **https://portal.azure.com**.</span></span>

   <span data-ttu-id="f61f0-147">Nachdem Sie das Ausfüllen des Formulars fertig haben, wählen Sie **"Registrieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="f61f0-147">After you're done filling out the form, select **Register**.</span></span>

   ![Abbildung des Formulars "Anwendung registrieren"](../..//media/atp-api-new-app-partner.png)

4. <span data-ttu-id="f61f0-149">Wählen Sie auf der Anwendungsseite DIE **API-Berechtigungen** hinzufügen Berechtigungs-APIs aus, die meine Organisation >, geben Sie Microsoft Threat Protection ein, und wählen Sie Microsoft  >    >   Threat **Protection aus.** </span><span class="sxs-lookup"><span data-stu-id="f61f0-149">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="f61f0-150">Ihre App kann jetzt auf Microsoft 365 Defender zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f61f0-150">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="f61f0-151">*Microsoft Threat Protection* ist ein früherer Name für Microsoft 365 Defender und wird nicht in der ursprünglichen Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f61f0-151">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="f61f0-152">Sie müssen damit beginnen, den Namen in das Textfeld zu schreiben, damit er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f61f0-152">You need to start writing its name in the text box to see it appear.</span></span>

   ![Abbildung der Auswahl von APIs](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="f61f0-154">Wählen Sie **Anwendungsberechtigungen aus.**</span><span class="sxs-lookup"><span data-stu-id="f61f0-154">Select **Application permissions**.</span></span> <span data-ttu-id="f61f0-155">Wählen Sie die relevanten Berechtigungen für Ihr Szenario aus (z. B. **Incident.Read.All),** und wählen Sie dann "Berechtigungen **hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="f61f0-155">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="f61f0-157">Sie müssen die relevanten Berechtigungen für Ihr Szenario auswählen.</span><span class="sxs-lookup"><span data-stu-id="f61f0-157">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="f61f0-158">*Das Lesen aller Vorfälle* ist nur ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f61f0-158">*Read all incidents* is just an example.</span></span> <span data-ttu-id="f61f0-159">Um zu bestimmen, welche Berechtigung Sie benötigen, sehen Sie sich den Abschnitt **"Berechtigungen"** in der API an, die Sie aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="f61f0-159">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="f61f0-160">Um beispielsweise [erweiterte](api-advanced-hunting.md)Abfragen ausführen zu können, wählen Sie die Berechtigung "Erweiterte Abfragen ausführen" aus. um [ein Gerät zu isolieren,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)wählen Sie die Berechtigung "Computer isolieren" aus.</span><span class="sxs-lookup"><span data-stu-id="f61f0-160">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="f61f0-161">Wählen Sie **Administratorzuserteilung aus.**</span><span class="sxs-lookup"><span data-stu-id="f61f0-161">Select **Grant admin consent**.</span></span> <span data-ttu-id="f61f0-162">Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie die Administratorzuserteilung **auswählen,** damit sie wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="f61f0-162">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Abbildung der Berechtigungserteilung](../../media/grant-consent.PNG)

7. <span data-ttu-id="f61f0-164">Um der Anwendung einen geheimen Schlüssel hinzuzufügen, wählen Sie **"&** Zertifikate" aus, fügen Sie dem Geheimen eine Beschreibung hinzu, und wählen Sie dann **"Hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="f61f0-164">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f61f0-165">Nachdem Sie **"Hinzufügen"** ausgewählt haben, wählen **Sie "Den generierten geheimen Wert kopieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="f61f0-165">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="f61f0-166">Sie können den geheimen Wert nach dem Verlassen nicht mehr abrufen.</span><span class="sxs-lookup"><span data-stu-id="f61f0-166">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Abbildung des Erstellens eines App-Schlüssels](../../media/webapp-create-key2.png)

8. <span data-ttu-id="f61f0-168">Noten Sie Ihre Anwendungs-ID und Ihre Mandanten-ID an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="f61f0-168">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="f61f0-169">Sie werden auf der **Anwendungsseite unter "Übersicht"** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f61f0-169">They're listed under **Overview** on your application page.</span></span>

   ![Abbildung der erstellten App-ID](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="f61f0-171">Fügen Sie die Anwendung dem Mandanten Ihres Benutzers hinzu.</span><span class="sxs-lookup"><span data-stu-id="f61f0-171">Add the application to your user's tenant.</span></span>

   <span data-ttu-id="f61f0-172">Da Ihre Anwendung im Namen Ihrer Benutzer mit Microsoft 365 Defender interagiert, muss sie für jeden Mandanten genehmigt werden, für den Sie ihn verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f61f0-172">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

   <span data-ttu-id="f61f0-173">Ein **globaler Administrator** aus dem Mandanten Ihres Benutzers muss den Zustimmungslink anzeigen und Ihre Anwendung genehmigen.</span><span class="sxs-lookup"><span data-stu-id="f61f0-173">A **Global Administrator** from your user's tenant needs to view the consent link and approve your application.</span></span>

   <span data-ttu-id="f61f0-174">Der Zustimmungslink hat das format:</span><span class="sxs-lookup"><span data-stu-id="f61f0-174">Consent link is of the form:</span></span>

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   <span data-ttu-id="f61f0-175">Die Ziffern `00000000-0000-0000-0000-000000000000` sollten durch Ihre Anwendungs-ID ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="f61f0-175">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>

   <span data-ttu-id="f61f0-176">Nachdem Sie auf den Zustimmungslink geklickt haben, melden Sie sich beim globalen Administrator des Mandanten des Benutzers an, und stimmen Sie der Anwendung zu.</span><span class="sxs-lookup"><span data-stu-id="f61f0-176">After clicking on the consent link, sign in with the Global Administrator of the user's tenant and consent the application.</span></span>

   ![Abbildung der Zustimmung](../../media/app-consent-partner.png)

   <span data-ttu-id="f61f0-178">Sie müssen ihren Benutzer auch nach seiner Mandanten-ID fragen.</span><span class="sxs-lookup"><span data-stu-id="f61f0-178">You'll also need to ask your user for their tenant ID.</span></span> <span data-ttu-id="f61f0-179">Die Mandanten-ID ist einer der Bezeichner, die zum Erwerben von Zugriffstoken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f61f0-179">The tenant ID is one of the identifiers used to acquire access tokens.</span></span>

- <span data-ttu-id="f61f0-180">**Fertig!**</span><span class="sxs-lookup"><span data-stu-id="f61f0-180">**Done!**</span></span> <span data-ttu-id="f61f0-181">Sie haben eine Anwendung erfolgreich registriert!</span><span class="sxs-lookup"><span data-stu-id="f61f0-181">You've successfully registered an application!</span></span>
- <span data-ttu-id="f61f0-182">Beispiele für den Erwerb und die Überprüfung von Token finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="f61f0-182">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="f61f0-183">Abrufen eines Zugriffstokens</span><span class="sxs-lookup"><span data-stu-id="f61f0-183">Get an access token</span></span>

<span data-ttu-id="f61f0-184">Weitere Informationen zu Azure AD-Token finden Sie im [Azure AD-Lernprogramm.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="f61f0-184">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f61f0-185">Obwohl die Beispiele in diesem Abschnitt sie zum Einfügen geheimer Werte zu Testzwecken ermutigen, sollten Sie geheime Schlüssel niemals in eine Anwendung hartcodieren, die in der Produktion ausgeführt wird. </span><span class="sxs-lookup"><span data-stu-id="f61f0-185">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="f61f0-186">Ein Drittanbieter kann Ihr Geheimnis für den Zugriff auf Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f61f0-186">A third party could use your secret to access resources.</span></span> <span data-ttu-id="f61f0-187">Mithilfe von Azure Key Vault können Sie die Geheimnisse Ihrer App [schützen.](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="f61f0-187">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="f61f0-188">Ein praktisches Beispiel dafür, wie Sie Ihre App schützen können, finden Sie unter "Verwalten geheimer Schlüssel [in Ihren Server-Apps mit Azure Key Vault".](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="f61f0-188">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

> [!TIP]
> <span data-ttu-id="f61f0-189">Verwenden Sie in den folgenden Beispielen die Mandanten-ID eines Benutzers, um zu testen, ob das Skript funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f61f0-189">In the following examples, use a user's tenant ID to test that the script is working.</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="f61f0-190">Erhalten eines Zugriffstokens mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="f61f0-190">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"

$authBody = [Ordered] @{
    resource = $resourceAppIdUri
    client_id = $clientId
    client_secret = $appSecret
    grant_type = 'client_credentials'
}

$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token

Out-File -FilePath "./Latest-token.txt" -InputObject $token

return $token
```

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="f61f0-191">Erhalten eines Zugriffstokens mithilfe von C\#</span><span class="sxs-lookup"><span data-stu-id="f61f0-191">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="f61f0-192">Der folgende Code wurde mit Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 getestet.</span><span class="sxs-lookup"><span data-stu-id="f61f0-192">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="f61f0-193">Erstellen Sie eine neue Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="f61f0-193">Create a new console application.</span></span>
1. <span data-ttu-id="f61f0-194">Installieren Sie NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="f61f0-194">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="f61f0-195">Fügen Sie die folgende Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="f61f0-195">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="f61f0-196">Kopieren Sie den folgenden Code, und fügen Sie ihn in Ihre App ein (vergessen Sie nicht, die drei Variablen zu aktualisieren: `tenantId` `clientId` , , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="f61f0-196">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="f61f0-197">Erhalten eines Zugriffstokens mithilfe von Python</span><span class="sxs-lookup"><span data-stu-id="f61f0-197">Get an access token using Python</span></span>

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="f61f0-198">Erhalten eines Zugriffstokens mithilfe von "token"</span><span class="sxs-lookup"><span data-stu-id="f61f0-198">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="f61f0-199">Er ist unter Windows 10, Version 1803 und höher, vorinstalliert.</span><span class="sxs-lookup"><span data-stu-id="f61f0-199">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="f61f0-200">Laden Sie für andere Versionen von Windows das Tool direkt von der offiziellen [Website des Betriebssystems herunter, und installieren Sie es.](https://curl.haxx.se/windows/)</span><span class="sxs-lookup"><span data-stu-id="f61f0-200">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="f61f0-201">Öffnen Sie eine Eingabeaufforderung, und legen CLIENT_ID Azure-Anwendungs-ID.</span><span class="sxs-lookup"><span data-stu-id="f61f0-201">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="f61f0-202">Legen CLIENT_SECRET auf Ihren geheimen Azure-Anwendungsgeheimnis.</span><span class="sxs-lookup"><span data-stu-id="f61f0-202">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="f61f0-203">Legen TENANT_ID auf die Azure-Mandanten-ID des Benutzers fest, der Ihre App für den Zugriff auf Microsoft 365 Defender verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="f61f0-203">Set TENANT_ID to the Azure tenant ID of the user that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="f61f0-204">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f61f0-204">Run the following command:</span></span>

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="f61f0-205">Eine erfolgreiche Antwort sieht wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="f61f0-205">A successful response will look like this:</span></span>

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="f61f0-206">Überprüfen des Tokens</span><span class="sxs-lookup"><span data-stu-id="f61f0-206">Validate the token</span></span>

1. <span data-ttu-id="f61f0-207">Kopieren Sie das Token, und fügen Sie es in die [JSON-Webtoken-Validator-Website, JWT, ein,](https://jwt.ms) um es zu decodieren.</span><span class="sxs-lookup"><span data-stu-id="f61f0-207">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="f61f0-208">Stellen Sie sicher, dass *der Rollenanspruch* innerhalb des decodierten Tokens die gewünschten Berechtigungen enthält.</span><span class="sxs-lookup"><span data-stu-id="f61f0-208">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="f61f0-209">In der folgenden Abbildung sehen Sie ein decodiertes Token, das von einer App mit ```Incidents.Read.All``` , und Berechtigungen erworben ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` wurde:</span><span class="sxs-lookup"><span data-stu-id="f61f0-209">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Abbildung der Tokenüberprüfung](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="f61f0-211">Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API</span><span class="sxs-lookup"><span data-stu-id="f61f0-211">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="f61f0-212">Wählen Sie die API aus, die Sie verwenden möchten (Vorfälle oder erweiterte Suche).</span><span class="sxs-lookup"><span data-stu-id="f61f0-212">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="f61f0-213">Weitere Informationen finden Sie unter [Unterstützte Microsoft 365 Defender-APIs.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="f61f0-213">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="f61f0-214">Legen Sie in der http-Anforderung, die Sie senden möchten, den Autorisierungsheader auf `"Bearer" <token>` " *Bearer"* als Autorisierungsschema und das Token als ihr überprüftes  Token.</span><span class="sxs-lookup"><span data-stu-id="f61f0-214">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="f61f0-215">Das Token läuft innerhalb einer Stunde ab.</span><span class="sxs-lookup"><span data-stu-id="f61f0-215">The token will expire within one hour.</span></span> <span data-ttu-id="f61f0-216">Sie können während dieser Zeit mehr als eine Anforderung mit demselben Token senden.</span><span class="sxs-lookup"><span data-stu-id="f61f0-216">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="f61f0-217">Das folgende Beispiel zeigt, wie Sie eine Anforderung senden, um eine Liste der Vorfälle mit **C# zu erhalten.**</span><span class="sxs-lookup"><span data-stu-id="f61f0-217">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="f61f0-218">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="f61f0-218">Related articles</span></span>

- [<span data-ttu-id="f61f0-219">Übersicht über Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="f61f0-219">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="f61f0-220">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="f61f0-220">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="f61f0-221">Erstellen einer "Hello world"-Anwendung</span><span class="sxs-lookup"><span data-stu-id="f61f0-221">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="f61f0-222">Erstellen einer App für den Zugriff auf Microsoft 365 Defender ohne Benutzer</span><span class="sxs-lookup"><span data-stu-id="f61f0-222">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="f61f0-223">Erstellen einer App für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="f61f0-223">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="f61f0-224">Informationen zu API-Beschränkungen und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="f61f0-224">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="f61f0-225">Fehlercodes verstehen</span><span class="sxs-lookup"><span data-stu-id="f61f0-225">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="f61f0-226">Verwalten von geheimen Schlüsseln in Ihren Server-Apps mit Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="f61f0-226">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="f61f0-227">OAuth 2.0-Autorisierung für die Benutzerauthentifizierung und den Zugriff auf die API</span><span class="sxs-lookup"><span data-stu-id="f61f0-227">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
