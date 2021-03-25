---
title: Erstellen einer App für den Zugriff auf Microsoft Defender for Endpoint ohne Benutzer
ms.reviewer: ''
description: Erfahren Sie, wie Sie eine Web-App entwerfen, um programmgesteuerten Zugriff auf Microsoft Defender for Endpoint ohne Benutzer zu erhalten.
keywords: apis, graph api, supported apis, actor, alerts, device, user, domain, ip, file, advanced hunting, query
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8f480a148d72428c6346930a91358d1e8b674ee7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200005"
---
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a><span data-ttu-id="ce1af-104">Erstellen einer App für den Zugriff auf Microsoft Defender for Endpoint ohne Benutzer</span><span class="sxs-lookup"><span data-stu-id="ce1af-104">Create an app to access Microsoft Defender for Endpoint without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ce1af-105">**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ce1af-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ce1af-106">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="ce1af-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ce1af-107">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="ce1af-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="ce1af-108">Auf dieser Seite wird beschrieben, wie Sie eine Anwendung erstellen, um programmgesteuerten Zugriff auf Defender for Endpoint ohne Benutzer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ce1af-108">This page describes how to create an application to get programmatic access to Defender for Endpoint without a user.</span></span> <span data-ttu-id="ce1af-109">Wenn Sie programmgesteuerten Zugriff auf Defender for Endpoint im Namen eines Benutzers benötigen, lesen Sie [Zugriff mit Benutzerkontext erhalten.](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="ce1af-109">If you need programmatic access to Defender for Endpoint on behalf of a user, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span> <span data-ttu-id="ce1af-110">Wenn Sie nicht sicher sind, welchen Zugriff Sie benötigen, lesen [Sie Erste Schritte](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="ce1af-110">If you are not sure which access you need, see [Get started](apis-intro.md).</span></span>

<span data-ttu-id="ce1af-111">Microsoft Defender for Endpoint macht einen Großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ce1af-111">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="ce1af-112">Diese APIs helfen Ihnen bei der Automatisierung von Arbeitsabläufen und innovationen basierend auf den Defender for Endpoint-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="ce1af-112">Those APIs will help you automate work flows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="ce1af-113">Für den API-Zugriff ist die OAuth2.0-Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce1af-113">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="ce1af-114">Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="ce1af-114">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="ce1af-115">Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="ce1af-115">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="ce1af-116">Erstellen Sie eine Azure Active Directory (Azure AD)-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ce1af-116">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="ce1af-117">Mit dieser Anwendung können Sie ein Zugriffstoken erhalten.</span><span class="sxs-lookup"><span data-stu-id="ce1af-117">Get an access token using this application.</span></span>
- <span data-ttu-id="ce1af-118">Verwenden Sie das Token, um auf die Defender for Endpoint-API zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ce1af-118">Use the token to access Defender for Endpoint API.</span></span>

<span data-ttu-id="ce1af-119">In diesem Artikel wird erläutert, wie Sie eine Azure AD-Anwendung erstellen, ein Zugriffstoken für Microsoft Defender for Endpoint erhalten und das Token überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ce1af-119">This article explains how to create an Azure AD application, get an access token to Microsoft Defender for Endpoint, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="ce1af-120">App erstellen</span><span class="sxs-lookup"><span data-stu-id="ce1af-120">Create an app</span></span>

1. <span data-ttu-id="ce1af-121">Melden Sie sich [mit einem](https://portal.azure.com) Benutzer mit der Rolle **"Globaler Administrator"** bei Azure an.</span><span class="sxs-lookup"><span data-stu-id="ce1af-121">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="ce1af-122">Navigieren Sie zu **Azure Active Directory**  >  **App-Registrierungen** Neue  >  **Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="ce1af-122">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](images/atp-azure-new-app2.png)

3. <span data-ttu-id="ce1af-124">Wählen Sie im Registrierungsformular einen Namen für Ihre Anwendung aus, und wählen Sie dann **Registrieren aus.**</span><span class="sxs-lookup"><span data-stu-id="ce1af-124">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="ce1af-125">Um Ihrer App den Zugriff auf Defender for Endpoint und die Berechtigung "Alle Warnungen **lesen"** zu ermöglichen, wählen Sie auf der Anwendungsseite **API-Berechtigungen** Hinzufügen von Berechtigungs-APIs aus, die meine Organisation > verwendet, geben  >    >   **Sie WindowsDefenderATP** ein, und wählen Sie **dann WindowsDefenderATP** aus.</span><span class="sxs-lookup"><span data-stu-id="ce1af-125">To enable your app to access Defender for Endpoint and assign it **'Read all alerts'** permission, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **WindowsDefenderATP**, and then select **WindowsDefenderATP**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ce1af-126">*WindowsDefenderATP* wird nicht in der ursprünglichen Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce1af-126">*WindowsDefenderATP* does not appear in the original list.</span></span> <span data-ttu-id="ce1af-127">Beginnen Sie, den Namen in das Textfeld zu schreiben, damit er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ce1af-127">Start writing its name in the text box to see it appear.</span></span>

   ![Hinzufügen von Berechtigungen](images/add-permission.png)

   - <span data-ttu-id="ce1af-129">Wählen **Sie Anwendungsberechtigungen**  >  **Alert.Read.All** aus, und wählen Sie **dann Berechtigungen hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="ce1af-129">Select **Application permissions** > **Alert.Read.All**, and then select **Add permissions**.</span></span>

   ![App-Berechtigung](images/application-permissions.png)

     <span data-ttu-id="ce1af-131">Sie müssen die entsprechenden Berechtigungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="ce1af-131">You need to select the relevant permissions.</span></span> <span data-ttu-id="ce1af-132">"Alle Warnungen lesen" ist nur ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ce1af-132">'Read All Alerts' is only an example.</span></span> <span data-ttu-id="ce1af-133">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ce1af-133">For instance:</span></span>

     - <span data-ttu-id="ce1af-134">Wählen [Sie zum Ausführen erweiterter](run-advanced-query-api.md)Abfragen die Berechtigung "Erweiterte Abfragen ausführen" aus.</span><span class="sxs-lookup"><span data-stu-id="ce1af-134">To [run advanced queries](run-advanced-query-api.md), select the 'Run advanced queries' permission.</span></span>
     - <span data-ttu-id="ce1af-135">Wählen [Sie zum Isolieren](isolate-machine.md)eines Geräts die Berechtigung "Computer isolieren" aus.</span><span class="sxs-lookup"><span data-stu-id="ce1af-135">To [isolate a device](isolate-machine.md), select the 'Isolate machine' permission.</span></span>
     - <span data-ttu-id="ce1af-136">Um zu bestimmen, welche Berechtigung Sie benötigen, sehen Sie sich den Abschnitt **Berechtigungen** in der API an, die Sie aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="ce1af-136">To determine which permission you need, look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="ce1af-137">Wählen Sie **Zustimmung erteilen aus.**</span><span class="sxs-lookup"><span data-stu-id="ce1af-137">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="ce1af-138">Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie **Zustimmung** erteilen auswählen, damit die neue Berechtigung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="ce1af-138">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![Erteilen von Berechtigungen](images/grant-consent.png)

6. <span data-ttu-id="ce1af-140">Wenn Sie der Anwendung einen geheimen Schlüssel hinzufügen möchten, wählen & **Zertifikate** aus, fügen Sie dem Geheimen eine Beschreibung hinzu, und wählen Sie dann **Hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="ce1af-140">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce1af-141">Nachdem Sie Hinzufügen **ausgewählt haben,** wählen **Sie den generierten geheimen Wert kopieren aus.**</span><span class="sxs-lookup"><span data-stu-id="ce1af-141">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="ce1af-142">Sie können diesen Wert nach dem Verlassen nicht mehr abrufen.</span><span class="sxs-lookup"><span data-stu-id="ce1af-142">You won't be able to retrieve this value after you leave.</span></span>

    ![Abbildung des App-Schlüssels erstellen](images/webapp-create-key2.png)

7. <span data-ttu-id="ce1af-144">Notieren Sie sich Ihre Anwendungs-ID und Ihre Mandanten-ID.</span><span class="sxs-lookup"><span data-stu-id="ce1af-144">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="ce1af-145">Wechseln Sie auf der Anwendungsseite zu **Übersicht,** und kopieren Sie Folgendes.</span><span class="sxs-lookup"><span data-stu-id="ce1af-145">On your application page, go to **Overview** and copy the following.</span></span>

   ![Abbildung der erstellten App-ID](images/app-and-tenant-ids.png)

8. <span data-ttu-id="ce1af-147">**Nur für Microsoft Defender für Endpunktpartner**.</span><span class="sxs-lookup"><span data-stu-id="ce1af-147">**For Microsoft Defender for Endpoint Partners only**.</span></span> <span data-ttu-id="ce1af-148">Legen Sie ihre App auf multi-tenanted (verfügbar in allen Mandanten nach Zustimmung) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ce1af-148">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="ce1af-149">Dies **ist für** Drittanbieter-Apps erforderlich (z. B. wenn Sie eine App erstellen, die im Mandanten mehrerer Kunden ausgeführt werden soll).</span><span class="sxs-lookup"><span data-stu-id="ce1af-149">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="ce1af-150">Dies **ist nicht** erforderlich, wenn Sie einen Dienst erstellen, den Sie nur in Ihrem Mandanten ausführen möchten (z. B. wenn Sie eine Anwendung für Ihre eigene Nutzung erstellen, die nur mit Ihren eigenen Daten interagiert).</span><span class="sxs-lookup"><span data-stu-id="ce1af-150">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="ce1af-151">So legen Sie ihre App auf mehr mandantenverdant festgelegt:</span><span class="sxs-lookup"><span data-stu-id="ce1af-151">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="ce1af-152">Wechseln Sie zu **Authentifizierung,** und fügen `https://portal.azure.com` Sie als **Umleitungs-URI hinzu.**</span><span class="sxs-lookup"><span data-stu-id="ce1af-152">Go to **Authentication**, and add `https://portal.azure.com` as the **Redirect URI**.</span></span>

    - <span data-ttu-id="ce1af-153">Wählen Sie unten auf der Seite unter Unterstützte **Kontotypen** die Option **Konten in** einer beliebigen Organisationsverzeichnisanwendungs-Zustimmung für Ihre Mehr-Mandanten-App aus.</span><span class="sxs-lookup"><span data-stu-id="ce1af-153">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="ce1af-154">Ihre Anwendung muss in jedem Mandanten genehmigt werden, in dem Sie sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ce1af-154">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="ce1af-155">Dies liegt daran, dass Ihre Anwendung Defender for Endpoint im Auftrag Ihres Kunden interagiert.</span><span class="sxs-lookup"><span data-stu-id="ce1af-155">This is because your application interacts Defender for Endpoint on behalf of your customer.</span></span>

    <span data-ttu-id="ce1af-156">Sie (oder Ihr Kunde, wenn Sie eine Drittanbieter-App schreiben) müssen den Zustimmungslink auswählen und Ihre App genehmigen.</span><span class="sxs-lookup"><span data-stu-id="ce1af-156">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="ce1af-157">Die Zustimmung sollte mit einem Benutzer durchgeführt werden, der über Administratorrechte in Active Directory verfügt.</span><span class="sxs-lookup"><span data-stu-id="ce1af-157">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="ce1af-158">Der Zustimmungslink besteht wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ce1af-158">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="ce1af-159">Dabei wird 00000000-0000-0000-0000-0000000000000 durch Ihre Anwendungs-ID ersetzt.</span><span class="sxs-lookup"><span data-stu-id="ce1af-159">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="ce1af-160">**Fertig!**</span><span class="sxs-lookup"><span data-stu-id="ce1af-160">**Done!**</span></span> <span data-ttu-id="ce1af-161">Sie haben eine Anwendung erfolgreich registriert!</span><span class="sxs-lookup"><span data-stu-id="ce1af-161">You have successfully registered an application!</span></span> <span data-ttu-id="ce1af-162">Weitere Informationen zum Erwerb und zur Überprüfung von Token finden Sie in den folgenden Beispielen.</span><span class="sxs-lookup"><span data-stu-id="ce1af-162">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="ce1af-163">Abrufen eines Zugriffstokens</span><span class="sxs-lookup"><span data-stu-id="ce1af-163">Get an access token</span></span>

<span data-ttu-id="ce1af-164">Weitere Informationen zu Azure AD-Token finden Sie im [Azure AD-Lernprogramm](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="ce1af-164">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="ce1af-165">PowerShell verwenden</span><span class="sxs-lookup"><span data-stu-id="ce1af-165">Use PowerShell</span></span>

```powershell
# This script acquires the App Context Token and stores it in the variable $token for later use in the script.
# Paste your Tenant ID, App ID, and App Secret (App key) into the indicated quotes below.

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
```

### <a name="use-c"></a><span data-ttu-id="ce1af-166">Verwenden C#:</span><span class="sxs-lookup"><span data-stu-id="ce1af-166">Use C#:</span></span>

<span data-ttu-id="ce1af-167">Der folgende Code wurde mit NuGet Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 getestet.</span><span class="sxs-lookup"><span data-stu-id="ce1af-167">The following code was tested with NuGet Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="ce1af-168">Erstellen Sie eine neue Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="ce1af-168">Create a new console application.</span></span>
1. <span data-ttu-id="ce1af-169">Installieren Sie NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="ce1af-169">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="ce1af-170">Fügen Sie Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="ce1af-170">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="ce1af-171">Kopieren Sie den folgenden Code, und fügen Sie ihn in Ihre App ein (vergessen Sie nicht, die drei Variablen zu aktualisieren: ```tenantId, appId, appSecret``` ):</span><span class="sxs-lookup"><span data-stu-id="ce1af-171">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.microsoftonline.com";
    const string wdatpResourceId = "https://api.securitycenter.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a><span data-ttu-id="ce1af-172">Verwenden von Python</span><span class="sxs-lookup"><span data-stu-id="ce1af-172">Use Python</span></span>

<span data-ttu-id="ce1af-173">Weitere [Informationen finden Sie unter Get token using Python](run-advanced-query-sample-python.md#get-token).</span><span class="sxs-lookup"><span data-stu-id="ce1af-173">See [Get token using Python](run-advanced-query-sample-python.md#get-token).</span></span>

### <a name="use-curl"></a><span data-ttu-id="ce1af-174">Verwenden von Locken</span><span class="sxs-lookup"><span data-stu-id="ce1af-174">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="ce1af-175">Im folgenden Verfahren wird davon ausgegangen, dass "Locken für Windows" bereits auf Ihrem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ce1af-175">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="ce1af-176">Öffnen Sie eine Eingabeaufforderung, und legen CLIENT_ID Auf Ihre Azure-Anwendungs-ID.</span><span class="sxs-lookup"><span data-stu-id="ce1af-176">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="ce1af-177">Legen CLIENT_SECRET auf Ihren geheimen Azure-Anwendungsgeheimnis.</span><span class="sxs-lookup"><span data-stu-id="ce1af-177">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="ce1af-178">Legen TENANT_ID auf die Azure-Mandanten-ID des Kunden fest, der Ihre App für den Zugriff auf Defender for Endpoint verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="ce1af-178">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Defender for Endpoint.</span></span>
1. <span data-ttu-id="ce1af-179">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ce1af-179">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="ce1af-180">Sie erhalten eine Antwort in folgendem Format:</span><span class="sxs-lookup"><span data-stu-id="ce1af-180">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="ce1af-181">Überprüfen des Tokens</span><span class="sxs-lookup"><span data-stu-id="ce1af-181">Validate the token</span></span>

<span data-ttu-id="ce1af-182">Stellen Sie sicher, dass Sie das richtige Token erhalten haben:</span><span class="sxs-lookup"><span data-stu-id="ce1af-182">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="ce1af-183">Kopieren Sie das Token, das Sie im vorherigen Schritt erhalten haben, und fügen Sie es in [JWT](https://jwt.ms) ein, um es zu decodieren.</span><span class="sxs-lookup"><span data-stu-id="ce1af-183">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="ce1af-184">Überprüfen, ob Sie einen "Rollen"-Anspruch mit den gewünschten Berechtigungen erhalten</span><span class="sxs-lookup"><span data-stu-id="ce1af-184">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="ce1af-185">In der folgenden Abbildung sehen Sie ein decodiertes Token, das von einer App mit Berechtigungen für alle Rollen von Microsoft Defender for Endpoint erworben wurde:</span><span class="sxs-lookup"><span data-stu-id="ce1af-185">In the following image, you can see a decoded token acquired from an app with permissions to all of  Microsoft Defender for Endpoint's roles:</span></span>

![Abbildung der Tokenüberprüfung](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a><span data-ttu-id="ce1af-187">Verwenden des Tokens für den Zugriff auf Die Microsoft Defender for Endpoint-API</span><span class="sxs-lookup"><span data-stu-id="ce1af-187">Use the token to access Microsoft Defender for Endpoint API</span></span>

1. <span data-ttu-id="ce1af-188">Wählen Sie die API aus, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ce1af-188">Choose the API you want to use.</span></span> <span data-ttu-id="ce1af-189">Weitere Informationen finden Sie unter [Supported Defender for Endpoint APIs](exposed-apis-list.md).</span><span class="sxs-lookup"><span data-stu-id="ce1af-189">For more information, see [Supported Defender for Endpoint APIs](exposed-apis-list.md).</span></span>
1. <span data-ttu-id="ce1af-190">Legen Sie den Autorisierungsheader in der http-Anforderung, die Sie an "Bearer {token}" senden, (Bearer ist das Autorisierungsschema).</span><span class="sxs-lookup"><span data-stu-id="ce1af-190">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>
1. <span data-ttu-id="ce1af-191">Die Ablaufzeit des Tokens beträgt eine Stunde.</span><span class="sxs-lookup"><span data-stu-id="ce1af-191">The expiration time of the token is one hour.</span></span> <span data-ttu-id="ce1af-192">Sie können mehrere Anfragen mit demselben Token senden.</span><span class="sxs-lookup"><span data-stu-id="ce1af-192">You can send more than one request with the same token.</span></span>

<span data-ttu-id="ce1af-193">Im Folgenden sehen Sie ein Beispiel für das Senden einer Anforderung zum Anfordern einer Liste von **Warnungen mithilfe C#:**</span><span class="sxs-lookup"><span data-stu-id="ce1af-193">The following is an example of sending a request to get a list of alerts **using C#**:</span></span> 
```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="see-also"></a><span data-ttu-id="ce1af-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce1af-194">See also</span></span>
- [<span data-ttu-id="ce1af-195">Unterstützte Microsoft Defender for Endpoint-APIs</span><span class="sxs-lookup"><span data-stu-id="ce1af-195">Supported Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="ce1af-196">Zugreifen auf Microsoft Defender for Endpoint im Namen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="ce1af-196">Access Microsoft Defender for Endpoint on behalf of a user</span></span>](exposed-apis-create-app-nativeapp.md)
