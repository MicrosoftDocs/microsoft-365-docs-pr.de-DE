---
title: Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer
description: Hier erfahren Sie, wie Sie eine APP für den Zugriff auf Microsoft 365 Defender ohne einen Benutzer erstellen.
keywords: APP, Access, API, CREATE
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: de925fa52056a051592fe5024c0abd40b51ad57b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719356"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="a98f5-104">Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer</span><span class="sxs-lookup"><span data-stu-id="a98f5-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a98f5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a98f5-105">**Applies to:**</span></span>

- <span data-ttu-id="a98f5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a98f5-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a98f5-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="a98f5-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a98f5-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="a98f5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a98f5-109">Auf dieser Seite wird beschrieben, wie Sie eine Anwendung erstellen, um den programmgesteuerten Zugriff auf Microsoft 365 Defender ohne definierten Benutzer zu erhalten (beispielsweise, wenn Sie einen Daemon oder einen Hintergrunddienst erstellen).</span><span class="sxs-lookup"><span data-stu-id="a98f5-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a defined user—for example, if you're creating a daemon or background service.</span></span>

<span data-ttu-id="a98f5-110">Wenn Sie den programmgesteuerten Zugriff auf Microsoft 365 Defender im Namen eines oder mehrerer Benutzer benötigen, finden Sie weitere Informationen unter [Erstellen einer APP für den Zugriff auf Microsoft 365 Defender-APIs im Namen eines Benutzers](api-create-app-user-context.md) und [Erstellen einer APP mit Partner Zugriff auf Microsoft 365 Defender-APIs](api-partner-access.md).</span><span class="sxs-lookup"><span data-stu-id="a98f5-110">If you need programmatic access to Microsoft 365 Defender on behalf of one or more users, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md) and [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).</span></span> <span data-ttu-id="a98f5-111">Wenn Sie nicht sicher sind, welche Art von Zugriff Sie benötigen, finden Sie weitere Informationen unter [Erste Schritte](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="a98f5-111">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="a98f5-112">Microsoft 365 Defender macht einen Großteil seiner Daten und Aktionen über eine Reihe von programmgesteuerten APIs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a98f5-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="a98f5-113">Diese APIs unterstützen Sie beim Automatisieren von Workflows und bei der Verwendung der Funktionen von Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a98f5-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="a98f5-114">Für diesen API-Zugriff ist die OAuth 2.0-Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a98f5-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="a98f5-115">Weitere Informationen finden Sie unter [OAuth 2,0-Autorisierungs Code Fluss](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="a98f5-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="a98f5-116">Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um diese APIs zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="a98f5-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="a98f5-117">Erstellen Sie eine Azure Active Directory (Azure AD)-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a98f5-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="a98f5-118">Abrufen eines Zugriffstokens mithilfe dieser Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a98f5-118">Get an access token using this application.</span></span>
- <span data-ttu-id="a98f5-119">Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a98f5-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="a98f5-120">In diesem Artikel wird erklärt, wie Sie:</span><span class="sxs-lookup"><span data-stu-id="a98f5-120">This article explains how to:</span></span>

- <span data-ttu-id="a98f5-121">Erstellen einer Azure AD-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a98f5-121">Create an Azure AD application</span></span>
- <span data-ttu-id="a98f5-122">Abrufen eines Zugriffstokens für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a98f5-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="a98f5-123">Überprüfen Sie das Token.</span><span class="sxs-lookup"><span data-stu-id="a98f5-123">Validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="a98f5-124">App erstellen</span><span class="sxs-lookup"><span data-stu-id="a98f5-124">Create an app</span></span>

1. <span data-ttu-id="a98f5-125">Melden Sie sich als Benutzer mit **globaler Administrator** Rolle bei [Azure](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="a98f5-125">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="a98f5-126">Navigieren Sie zu **Azure Active Directory**  >  **App Registrations**  >  **New Registration**.</span><span class="sxs-lookup"><span data-stu-id="a98f5-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="a98f5-128">Wählen Sie im Formular einen Namen für Ihre Anwendung aus, und wählen Sie dann **registrieren** aus.</span><span class="sxs-lookup"><span data-stu-id="a98f5-128">In the form, choose a name for your application, then select **Register**.</span></span>

4. <span data-ttu-id="a98f5-129">Wählen Sie auf Ihrer Anwendungsseite **API-Berechtigungen**  >  **Add permission**  >  **APIs meine Organisation verwendet** >, geben Sie **Microsoft Threat Protection** ein, und wählen Sie **Microsoft Threat Protection** aus.</span><span class="sxs-lookup"><span data-stu-id="a98f5-129">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="a98f5-130">Ihre APP kann nun auf Microsoft 365 Defender zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a98f5-130">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="a98f5-131">*Microsoft Threat Protection* ist ein ehemaliger Name für Microsoft 365 Defender und wird nicht in der ursprünglichen Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a98f5-131">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="a98f5-132">Sie müssen mit dem Schreiben des Namens in das Textfeld beginnen, damit dieser angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a98f5-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![Abbildung der API-Berechtigungs Auswahl](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="a98f5-134">Wählen Sie **Anwendungsberechtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="a98f5-134">Select **Application permissions**.</span></span> <span data-ttu-id="a98f5-135">Wählen Sie die relevanten Berechtigungen für Ihr Szenario (beispielsweise **Incident. Read. all**) aus, und wählen Sie dann **Berechtigungen hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="a98f5-135">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="a98f5-137">Sie müssen die relevanten Berechtigungen für Ihr Szenario auswählen.</span><span class="sxs-lookup"><span data-stu-id="a98f5-137">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="a98f5-138">*Lesen Sie alle Vorfälle* ist nur ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a98f5-138">*Read all incidents* is just an example.</span></span> <span data-ttu-id="a98f5-139">Um zu ermitteln, welche Berechtigungen Sie benötigen, sehen Sie sich den Abschnitt **Berechtigungen** in der API an, die Sie aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="a98f5-139">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="a98f5-140">Um beispielsweise [erweiterte Abfragen auszuführen](api-advanced-hunting.md), wählen Sie die Berechtigung ' erweiterte Abfragen ausführen ' aus; um [ein Gerät zu isolieren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), wählen Sie die Berechtigung "Computer isolieren" aus.</span><span class="sxs-lookup"><span data-stu-id="a98f5-140">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="a98f5-141">Wählen Sie **Administrator Zustimmung erteilen** aus.</span><span class="sxs-lookup"><span data-stu-id="a98f5-141">Select **Grant admin consent**.</span></span> <span data-ttu-id="a98f5-142">Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie die Option **Administrator Zustimmung erteilen** auswählen, damit Sie wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="a98f5-142">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Image von Grant-Berechtigungen](../../media/grant-consent.PNG)

7. <span data-ttu-id="a98f5-144">Um der Anwendung ein Geheimnis hinzuzufügen, wählen Sie **Zertifikate & Secrets** aus, fügen Sie eine Beschreibung zum geheimen Schlüssel hinzu, und wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="a98f5-144">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="a98f5-145">Nachdem Sie **Hinzufügen** ausgewählt haben, wählen Sie **den generierten geheimen Wert kopieren** aus.</span><span class="sxs-lookup"><span data-stu-id="a98f5-145">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="a98f5-146">Sie können den geheimen Wert nach dem verlassen nicht mehr abrufen.</span><span class="sxs-lookup"><span data-stu-id="a98f5-146">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Bild der APP-Schlüssel erstellen](../../media/webapp-create-key2.png)

8. <span data-ttu-id="a98f5-148">Notieren Sie Ihre Anwendungs-ID und ihre Mandanten-ID an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="a98f5-148">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="a98f5-149">Sie werden unter **Übersicht** auf Ihrer Anwendungsseite aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a98f5-149">They're listed under **Overview** on your application page.</span></span>

   ![Bild der erstellten APP-ID](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="a98f5-151">**Nur für Microsoft 365 Defender-Partner**: [befolgen Sie diese Anweisungen](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) für den Partner Zugriff über die Microsoft 365 Defender-APIs, und legen Sie Ihre APP auf mehrere Mandanten fest, sodass Sie in allen Mandanten verfügbar sein kann, sobald Sie die Zustimmung des Administrators erhalten.</span><span class="sxs-lookup"><span data-stu-id="a98f5-151">**For Microsoft 365 Defender Partners only**: [Follow these instructions](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) for partner access through the Microsoft 365 Defender APIs, set your app to be multi-tenant, so it can be available in all tenants once you receive admin consent.</span></span> <span data-ttu-id="a98f5-152">Partner Zugriff ist für Drittanbieter-apps **erforderlich** , beispielsweise, wenn Sie eine APP erstellen, die in Mandanten mehrerer Kunden ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a98f5-152">Partner access is **required** for third-party apps—for example, if you create an app that is intended to run in multiple customers' tenants.</span></span> <span data-ttu-id="a98f5-153">Es ist **nicht erforderlich** , wenn Sie einen Dienst erstellen, der nur in Ihrem Mandanten ausgeführt werden soll, beispielsweise eine Anwendung für Ihre eigene Verwendung, die nur mit ihren eigenen Daten interagiert.</span><span class="sxs-lookup"><span data-stu-id="a98f5-153">It is **not required** if you create a service that you want to run in your tenant only, such as an application for your own usage that will only interact with your own data.</span></span> <span data-ttu-id="a98f5-154">So legen Sie die APP als Multi-Mandanten fest:</span><span class="sxs-lookup"><span data-stu-id="a98f5-154">To set your app to be multi-tenant:</span></span>

    - <span data-ttu-id="a98f5-155">Wechseln Sie zu **Authentifizierung**, und fügen Sie https://portal.azure.com als **Umleitungs-URI** hinzu.</span><span class="sxs-lookup"><span data-stu-id="a98f5-155">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="a98f5-156">Wählen Sie unten auf der Seite unter **unterstützte Kontotypen** die **Konten in einer beliebigen Organisations Verzeichnis** -Anwendungs Zustimmung für Ihre mandantenfähige App aus.</span><span class="sxs-lookup"><span data-stu-id="a98f5-156">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="a98f5-157">Da Ihre Anwendung im Namen Ihrer Benutzer mit Microsoft 365 Defender interagiert, muss Sie für jeden Mandanten genehmigt werden, für den Sie Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a98f5-157">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

    <span data-ttu-id="a98f5-158">Der Active Directory globale Administrator für jeden Mandanten muss den Zustimmungs Link auswählen und Ihre APP genehmigen.</span><span class="sxs-lookup"><span data-stu-id="a98f5-158">The Active Directory global admin for each tenant needs to select the consent link and approve your app.</span></span>

    <span data-ttu-id="a98f5-159">Der Zustimmungs Link hat die folgende Struktur:</span><span class="sxs-lookup"><span data-stu-id="a98f5-159">The consent link has the following structure:</span></span>

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="a98f5-160">Die Ziffern `00000000-0000-0000-0000-000000000000` sollten durch Ihre Anwendungs-ID ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a98f5-160">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>  

<span data-ttu-id="a98f5-161">**Fertig!**</span><span class="sxs-lookup"><span data-stu-id="a98f5-161">**Done!**</span></span> <span data-ttu-id="a98f5-162">Sie haben eine Anwendung erfolgreich registriert!</span><span class="sxs-lookup"><span data-stu-id="a98f5-162">You've successfully registered an application!</span></span> <span data-ttu-id="a98f5-163">In den folgenden Beispielen finden Sie Informationen zur Token-Erfassung und-Validierung.</span><span class="sxs-lookup"><span data-stu-id="a98f5-163">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="a98f5-164">Abrufen eines Zugriffstokens</span><span class="sxs-lookup"><span data-stu-id="a98f5-164">Get an access token</span></span>

<span data-ttu-id="a98f5-165">Weitere Informationen zu Azure Active Directory Token finden Sie im [Azure AD-Lernprogramm](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="a98f5-165">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a98f5-166">Obwohl die Beispiele in diesem Abschnitt Sie dazu ermutigen, in geheimen Werten zu Testzwecken einzufügen, sollten Sie **keine Geheimnisse** in einer Anwendung, die in der Produktion läuft, hartcodieren.</span><span class="sxs-lookup"><span data-stu-id="a98f5-166">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="a98f5-167">Ein Drittanbieter kann ihren geheimen Schlüssel für den Zugriff auf Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a98f5-167">A third party could use your secret to access resources.</span></span> <span data-ttu-id="a98f5-168">Mithilfe von [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)können Sie die Sicherheit Ihrer APP-Geheimnisse schützen.</span><span class="sxs-lookup"><span data-stu-id="a98f5-168">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="a98f5-169">Ein praktisches Beispiel dafür, wie Sie Ihre APP schützen können, finden Sie unter [Manage Secrets in Your Server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span><span class="sxs-lookup"><span data-stu-id="a98f5-169">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="a98f5-170">Abrufen eines Zugriffstokens mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="a98f5-170">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="a98f5-171">Abrufen eines Zugriffstokens mithilfe von C\#</span><span class="sxs-lookup"><span data-stu-id="a98f5-171">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="a98f5-172">Der folgende Code wurde mit Nuget Microsoft. IdentityModel. Clients. ActiveDirectory 3.19.8 getestet.</span><span class="sxs-lookup"><span data-stu-id="a98f5-172">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="a98f5-173">Erstellen Sie eine neue Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="a98f5-173">Create a new console application.</span></span>

1. <span data-ttu-id="a98f5-174">Installieren Sie NuGet [Microsoft. IdentityModel. Clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="a98f5-174">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>

1. <span data-ttu-id="a98f5-175">Fügen Sie die folgende Reihe hinzu:</span><span class="sxs-lookup"><span data-stu-id="a98f5-175">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="a98f5-176">Kopieren Sie den folgenden Code, und fügen Sie ihn in Ihre APP ein (vergessen Sie nicht, die drei Variablen zu aktualisieren: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="a98f5-176">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="a98f5-177">Abrufen eines Zugriffstokens mithilfe von python</span><span class="sxs-lookup"><span data-stu-id="a98f5-177">Get an access token using Python</span></span>

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="a98f5-178">Abrufen eines Zugriffstokens mithilfe von curl</span><span class="sxs-lookup"><span data-stu-id="a98f5-178">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="a98f5-179">Curl ist auf Windows 10, Version 1803 und höher, vorinstalliert.</span><span class="sxs-lookup"><span data-stu-id="a98f5-179">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="a98f5-180">Laden Sie für andere Versionen von Windows das Tool direkt von der [offiziellen curl-Website](https://curl.haxx.se/windows/)herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="a98f5-180">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="a98f5-181">Öffnen Sie eine Eingabeaufforderung, und legen Sie CLIENT_ID auf Ihre Azure-Anwendungs-ID fest.</span><span class="sxs-lookup"><span data-stu-id="a98f5-181">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>

1. <span data-ttu-id="a98f5-182">Legen Sie CLIENT_SECRET auf Ihren Azure-Anwendungsschlüssel fest.</span><span class="sxs-lookup"><span data-stu-id="a98f5-182">Set CLIENT_SECRET to your Azure application secret.</span></span>

1. <span data-ttu-id="a98f5-183">Legen Sie TENANT_ID auf die Azure-Mandanten-ID des Kunden fest, der Ihre APP für den Zugriff auf Microsoft 365 Defender verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="a98f5-183">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>

1. <span data-ttu-id="a98f5-184">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a98f5-184">Run the following command:</span></span>

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   <span data-ttu-id="a98f5-185">Eine erfolgreiche Antwort wird wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="a98f5-185">A successful response will look like this:</span></span>

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a><span data-ttu-id="a98f5-186">Überprüfen des Tokens</span><span class="sxs-lookup"><span data-stu-id="a98f5-186">Validate the token</span></span>

1. <span data-ttu-id="a98f5-187">Kopieren Sie das Token, und fügen Sie es in die [JSON Web Token Validator-Website, JWT,](https://jwt.ms) ein, um es zu decodieren.</span><span class="sxs-lookup"><span data-stu-id="a98f5-187">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>

1. <span data-ttu-id="a98f5-188">Stellen Sie sicher, dass die *Rollen* Forderung innerhalb des decodierten Tokens die gewünschten Berechtigungen enthält.</span><span class="sxs-lookup"><span data-stu-id="a98f5-188">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

   <span data-ttu-id="a98f5-189">In der folgenden Abbildung sehen Sie ein decodiertes Token, das aus einer APP, mit `Incidents.Read.All` , `Incidents.ReadWrite.All` und Berechtigungen erworben wurde `AdvancedHunting.Read.All` :</span><span class="sxs-lookup"><span data-stu-id="a98f5-189">In the following image, you can see a decoded token acquired from an app, with `Incidents.Read.All`, `Incidents.ReadWrite.All`, and `AdvancedHunting.Read.All` permissions:</span></span>

   ![Bild der Token-Validierung](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="a98f5-191">Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API</span><span class="sxs-lookup"><span data-stu-id="a98f5-191">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="a98f5-192">Wählen Sie die API aus, die Sie verwenden möchten (Incidents oder Advanced Hunting).</span><span class="sxs-lookup"><span data-stu-id="a98f5-192">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="a98f5-193">Weitere Informationen finden Sie unter [Supported Microsoft 365 Defender APIs](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="a98f5-193">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="a98f5-194">Legen Sie in der HTTP-Anforderung, die Sie senden möchten, den Autorisierungs Kopf auf `"Bearer" <token>` , *Bearer* ist das Autorisierungsschema, und *Token* ist Ihr validiertes Token.</span><span class="sxs-lookup"><span data-stu-id="a98f5-194">In the http request you are about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>

3. <span data-ttu-id="a98f5-195">Das Token wird innerhalb einer Stunde ablaufen.</span><span class="sxs-lookup"><span data-stu-id="a98f5-195">The token will expire within one hour.</span></span> <span data-ttu-id="a98f5-196">Sie können während dieser Zeit mehr als eine Anforderung mit demselben Token senden.</span><span class="sxs-lookup"><span data-stu-id="a98f5-196">You can send more than one request during this time with the same token.</span></span>

<span data-ttu-id="a98f5-197">Das folgende Beispiel zeigt, wie Sie eine Anforderung zum Abrufen einer Liste von Vorfällen **mithilfe von C#** senden.</span><span class="sxs-lookup"><span data-stu-id="a98f5-197">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="a98f5-198">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="a98f5-198">Related articles</span></span>

- [<span data-ttu-id="a98f5-199">Microsoft 365 Defender-APIs (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="a98f5-199">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="a98f5-200">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="a98f5-200">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="a98f5-201">Erstellen einer "Hello World"-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a98f5-201">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="a98f5-202">Erstellen einer APP für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="a98f5-202">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="a98f5-203">Erstellen einer APP mit mehr Mandanten fähigem Partner Zugriff auf Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="a98f5-203">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="a98f5-204">Informationen zu API-Grenzwerten und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="a98f5-204">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="a98f5-205">Grundlegendes zu Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="a98f5-205">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="a98f5-206">Verwalten von geheimen Schlüsseln in Ihren Server-apps mit Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="a98f5-206">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="a98f5-207">OAuth 2,0 Autorisierung für Benutzeranmeldung und API-Zugriff</span><span class="sxs-lookup"><span data-stu-id="a98f5-207">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
