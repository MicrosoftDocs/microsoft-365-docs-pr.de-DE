---
title: Erstellen einer APP für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers
description: Erfahren Sie, wie Sie im Namen eines Benutzers auf Microsoft 365 Defender-APIs zugreifen.
keywords: Zugriff im Namen des Benutzers, der API, der Anwendung, des Benutzers, des Zugriffstokens, des Tokens,
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
ms.openlocfilehash: f1c0caea9ff7810f79026c789241a4f250ec5303
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719416"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="91f47-104">Erstellen einer APP für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="91f47-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="91f47-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="91f47-105">**Applies to:**</span></span>

- <span data-ttu-id="91f47-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91f47-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91f47-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="91f47-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="91f47-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="91f47-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="91f47-109">Auf dieser Seite wird beschrieben, wie Sie eine Anwendung erstellen, um den programmgesteuerten Zugriff auf Microsoft 365 Defender im Auftrag eines einzelnen Benutzers zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="91f47-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="91f47-110">Wenn Sie den programmgesteuerten Zugriff auf Microsoft 365 Defender ohne definierten Benutzer benötigen (beispielsweise wenn Sie eine Hintergrund-APP oder einen-Daemon schreiben), finden Sie weitere Informationen unter [Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="91f47-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="91f47-111">Wenn Sie Zugriff für mehrere Mandanten bereitstellen müssen, beispielsweise wenn Sie eine große Organisation oder eine Gruppe von Kunden bedienen, finden Sie weitere Informationen unter [Erstellen einer APP mit Partner Zugriff auf Microsoft 365 Defender-APIs](api-partner-access.md). Wenn Sie nicht sicher sind, welche Art von Zugriff Sie benötigen, finden Sie weitere Informationen unter [Erste Schritte](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="91f47-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="91f47-112">Microsoft 365 Defender macht einen Großteil seiner Daten und Aktionen über eine Reihe von programmgesteuerten APIs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="91f47-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="91f47-113">Diese APIs unterstützen Sie beim Automatisieren von Workflows und bei der Verwendung der Funktionen von Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="91f47-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="91f47-114">Für diesen API-Zugriff ist die OAuth 2.0-Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="91f47-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="91f47-115">Weitere Informationen finden Sie unter [OAuth 2,0-Autorisierungs Code Fluss](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="91f47-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="91f47-116">Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um diese APIs zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="91f47-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="91f47-117">Erstellen Sie eine Azure Active Directory (Azure AD)-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="91f47-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="91f47-118">Abrufen eines Zugriffstokens mithilfe dieser Anwendung.</span><span class="sxs-lookup"><span data-stu-id="91f47-118">Get an access token using this application.</span></span>
- <span data-ttu-id="91f47-119">Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="91f47-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="91f47-120">In diesem Artikel wird erklärt, wie Sie:</span><span class="sxs-lookup"><span data-stu-id="91f47-120">This article explains how to:</span></span>

- <span data-ttu-id="91f47-121">Erstellen einer Azure AD-Anwendung</span><span class="sxs-lookup"><span data-stu-id="91f47-121">Create an Azure AD application</span></span>
- <span data-ttu-id="91f47-122">Abrufen eines Zugriffstokens für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91f47-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="91f47-123">Überprüfen des Tokens</span><span class="sxs-lookup"><span data-stu-id="91f47-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="91f47-124">Wenn Sie im Namen eines Benutzers auf die Microsoft 365 Defender-API zugreifen, benötigen Sie die richtigen Anwendungsberechtigungen und Benutzerberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="91f47-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="91f47-125">Wenn Sie über die Berechtigung zum Ausführen einer Aktion im Portal verfügen, haben Sie die Berechtigung, die Aktion in der API auszuführen.</span><span class="sxs-lookup"><span data-stu-id="91f47-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="91f47-126">App erstellen</span><span class="sxs-lookup"><span data-stu-id="91f47-126">Create an app</span></span>

1. <span data-ttu-id="91f47-127">Melden Sie sich als Benutzer mit **globaler Administrator** Rolle bei [Azure](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="91f47-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="91f47-128">Navigieren Sie zu **Azure Active Directory**  >  **App Registrations**  >  **New Registration**.</span><span class="sxs-lookup"><span data-stu-id="91f47-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="91f47-130">Wählen Sie im Formular einen Namen für Ihre Anwendung aus, und geben Sie die folgenden Informationen für den Umleitungs-URI ein, und wählen Sie dann **registrieren** aus.</span><span class="sxs-lookup"><span data-stu-id="91f47-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![Bild des Fensters "Anwendungs erstellen"](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="91f47-132">**Anwendungstyp:** Öffentlicher Client</span><span class="sxs-lookup"><span data-stu-id="91f47-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="91f47-133">**Umleitungs-URI:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="91f47-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="91f47-134">Wählen Sie auf Ihrer Anwendungsseite **API-Berechtigungen**  >  **Add permission**  >  **APIs meine Organisation verwendet** >, geben Sie **Microsoft Threat Protection** ein, und wählen Sie **Microsoft Threat Protection** aus.</span><span class="sxs-lookup"><span data-stu-id="91f47-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="91f47-135">Ihre APP kann nun auf Microsoft 365 Defender zugreifen.</span><span class="sxs-lookup"><span data-stu-id="91f47-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="91f47-136">*Microsoft Threat Protection* ist ein ehemaliger Name für Microsoft 365 Defender und wird nicht in der ursprünglichen Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91f47-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="91f47-137">Sie müssen mit dem Schreiben des Namens in das Textfeld beginnen, damit dieser angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="91f47-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![Abbildung der API-Berechtigungs Auswahl](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="91f47-139">Wählen Sie **Delegierte Berechtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="91f47-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="91f47-140">Wählen Sie die relevanten Berechtigungen für Ihr Szenario (beispielsweise **Incident. Read**) aus, und wählen Sie dann **Berechtigungen hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="91f47-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="91f47-142">Sie müssen die relevanten Berechtigungen für Ihr Szenario auswählen.</span><span class="sxs-lookup"><span data-stu-id="91f47-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="91f47-143">*Lesen Sie alle Vorfälle* ist nur ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="91f47-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="91f47-144">Um zu ermitteln, welche Berechtigungen Sie benötigen, sehen Sie sich den Abschnitt **Berechtigungen** in der API an, die Sie aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="91f47-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="91f47-145">Um beispielsweise [erweiterte Abfragen auszuführen](api-advanced-hunting.md), wählen Sie die Berechtigung ' erweiterte Abfragen ausführen ' aus; um [ein Gerät zu isolieren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), wählen Sie die Berechtigung "Computer isolieren" aus.</span><span class="sxs-lookup"><span data-stu-id="91f47-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="91f47-146">Wählen Sie **Administrator Zustimmung erteilen** aus.</span><span class="sxs-lookup"><span data-stu-id="91f47-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="91f47-147">Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie die Option **Administrator Zustimmung erteilen** auswählen, damit Sie wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="91f47-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![Image von Grant-Berechtigungen](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="91f47-149">Notieren Sie Ihre Anwendungs-ID und ihre Mandanten-ID an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="91f47-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="91f47-150">Sie werden unter **Übersicht** auf Ihrer Anwendungsseite aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="91f47-150">They're listed under **Overview** on your application page.</span></span>

   ![Bild der erstellten APP-ID](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="91f47-152">Abrufen eines Zugriffstokens</span><span class="sxs-lookup"><span data-stu-id="91f47-152">Get an access token</span></span>

<span data-ttu-id="91f47-153">Weitere Informationen zu Azure Active Directory Token finden Sie im [Azure AD-Lernprogramm](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="91f47-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="91f47-154">Abrufen eines Zugriffstokens mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="91f47-154">Get an access token using PowerShell</span></span>

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a><span data-ttu-id="91f47-155">Überprüfen des Tokens</span><span class="sxs-lookup"><span data-stu-id="91f47-155">Validate the token</span></span>

1. <span data-ttu-id="91f47-156">Kopieren Sie das Token, und fügen Sie es in [JWT](https://jwt.ms) ein, um es zu decodieren.</span><span class="sxs-lookup"><span data-stu-id="91f47-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="91f47-157">Stellen Sie sicher, dass die *Rollen* Forderung innerhalb des decodierten Tokens die gewünschten Berechtigungen enthält.</span><span class="sxs-lookup"><span data-stu-id="91f47-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="91f47-158">In der folgenden Abbildung sehen Sie ein decodiertes Token, das aus einer APP, mit ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` und Berechtigungen erworben wurde ```AdvancedHunting.Read.All``` :</span><span class="sxs-lookup"><span data-stu-id="91f47-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Bild der Token-Validierung](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="91f47-160">Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API</span><span class="sxs-lookup"><span data-stu-id="91f47-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="91f47-161">Wählen Sie die API aus, die Sie verwenden möchten (Incidents oder Advanced Hunting).</span><span class="sxs-lookup"><span data-stu-id="91f47-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="91f47-162">Weitere Informationen finden Sie unter [Supported Microsoft 365 Defender APIs](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="91f47-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="91f47-163">Legen Sie in der HTTP-Anforderung, die Sie senden möchten, den Autorisierungs Kopf auf `"Bearer" <token>` , *Bearer* ist das Autorisierungsschema, und *Token* ist Ihr validiertes Token.</span><span class="sxs-lookup"><span data-stu-id="91f47-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="91f47-164">Das Token wird innerhalb einer Stunde ablaufen.</span><span class="sxs-lookup"><span data-stu-id="91f47-164">The token will expire within one hour.</span></span> <span data-ttu-id="91f47-165">Sie können während dieser Zeit mehr als eine Anforderung mit demselben Token senden.</span><span class="sxs-lookup"><span data-stu-id="91f47-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="91f47-166">Das folgende Beispiel zeigt, wie Sie eine Anforderung zum Abrufen einer Liste von Vorfällen **mithilfe von C#** senden.</span><span class="sxs-lookup"><span data-stu-id="91f47-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="91f47-167">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="91f47-167">Related articles</span></span>

- [<span data-ttu-id="91f47-168">Microsoft 365 Defender-APIs (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="91f47-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="91f47-169">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="91f47-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="91f47-170">Erstellen einer "Hello World"-App</span><span class="sxs-lookup"><span data-stu-id="91f47-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="91f47-171">Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer</span><span class="sxs-lookup"><span data-stu-id="91f47-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="91f47-172">Erstellen einer APP mit mehr Mandanten fähigem Partner Zugriff auf Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="91f47-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="91f47-173">Informationen zu API-Grenzwerten und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="91f47-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="91f47-174">Grundlegendes zu Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="91f47-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="91f47-175">OAuth 2,0 Autorisierung für Benutzeranmeldung und API-Zugriff</span><span class="sxs-lookup"><span data-stu-id="91f47-175">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
