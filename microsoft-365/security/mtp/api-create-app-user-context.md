---
title: Erstellen einer App für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers
description: Erfahren Sie, wie Sie im Namen eines Benutzers auf Microsoft 365 Defender-APIs zugreifen.
keywords: Zugriff im Auftrag von Benutzer, API, Anwendung, Benutzer, Zugriffstoken, Token,
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
ms.openlocfilehash: d443334a00b5247525a2cdba98a11cfe0f515193
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928462"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="126fe-104">Erstellen einer App für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="126fe-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="126fe-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="126fe-105">**Applies to:**</span></span>

- <span data-ttu-id="126fe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="126fe-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="126fe-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="126fe-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="126fe-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="126fe-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="126fe-109">Auf dieser Seite wird beschrieben, wie Sie eine Anwendung erstellen, um programmgesteuerten Zugriff auf Microsoft 365 Defender im Namen eines einzelnen Benutzers zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="126fe-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="126fe-110">Wenn Sie programmgesteuerten Zugriff auf Microsoft 365 Defender ohne einen definierten Benutzer benötigen (z. B. wenn Sie eine Hintergrund-App oder einen Daemon schreiben), lesen Sie "Erstellen einer App für den Zugriff auf [Microsoft 365 Defender](api-create-app-web.md)ohne Benutzer".</span><span class="sxs-lookup"><span data-stu-id="126fe-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="126fe-111">Wenn Sie Zugriff für mehrere Mandanten bereitstellen müssen , z. B. wenn Sie eine große Organisation oder eine Gruppe von Kunden bereitstellen, lesen Sie "Erstellen einer App mit Partnerzugriff auf [Microsoft 365 Defender-APIs".](api-partner-access.md) Wenn Sie nicht sicher sind, welche Art von Zugriff Sie benötigen, lesen Sie ["Erste Schritte".](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="126fe-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="126fe-112">Microsoft 365 Defender macht einen Großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="126fe-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="126fe-113">Mit diesen APIs können Sie Workflows automatisieren und die Funktionen von Microsoft 365 Defender nutzen.</span><span class="sxs-lookup"><span data-stu-id="126fe-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="126fe-114">Für diesen ZUGRIFF auf die API ist die OAuth2.0-Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="126fe-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="126fe-115">Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="126fe-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="126fe-116">Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um diese APIs zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="126fe-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="126fe-117">Erstellen Sie eine Azure Active Directory (Azure AD)-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="126fe-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="126fe-118">Mit dieser Anwendung können Sie ein Zugriffstoken erhalten.</span><span class="sxs-lookup"><span data-stu-id="126fe-118">Get an access token using this application.</span></span>
- <span data-ttu-id="126fe-119">Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="126fe-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="126fe-120">In diesem Artikel wird erläutert, wie Sie:</span><span class="sxs-lookup"><span data-stu-id="126fe-120">This article explains how to:</span></span>

- <span data-ttu-id="126fe-121">Erstellen einer Azure AD-Anwendung</span><span class="sxs-lookup"><span data-stu-id="126fe-121">Create an Azure AD application</span></span>
- <span data-ttu-id="126fe-122">Erhalten eines Zugriffstokens für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="126fe-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="126fe-123">Überprüfen des Tokens</span><span class="sxs-lookup"><span data-stu-id="126fe-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="126fe-124">Wenn Sie im Namen eines Benutzers auf die Microsoft 365 Defender-API zugreifen, benötigen Sie die richtigen Anwendungsberechtigungen und Benutzerberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="126fe-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="126fe-125">Wenn Sie über die Berechtigung zum Ausführen einer Aktion im Portal verfügen, haben Sie die Berechtigung, die Aktion in der API durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="126fe-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="126fe-126">App erstellen</span><span class="sxs-lookup"><span data-stu-id="126fe-126">Create an app</span></span>

1. <span data-ttu-id="126fe-127">Melden Sie sich [bei Azure](https://portal.azure.com) als Benutzer mit der rolle **"Globaler Administrator"** an.</span><span class="sxs-lookup"><span data-stu-id="126fe-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="126fe-128">Navigieren Sie zu **Azure Active**  >  **Directory-App-Registrierungen**  >  **Neue Registrierung.**</span><span class="sxs-lookup"><span data-stu-id="126fe-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="126fe-130">Wählen Sie im Formular einen Namen für Ihre Anwendung aus, geben Sie die folgenden Informationen für den Umleitungs-URI ein, und wählen Sie dann **"Registrieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="126fe-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![Abbildung des Fensters "Anwendung erstellen"](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="126fe-132">**Anwendungstyp:** Öffentlicher Client</span><span class="sxs-lookup"><span data-stu-id="126fe-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="126fe-133">**Umleitungs-URI:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="126fe-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="126fe-134">Wählen Sie auf der Anwendungsseite DIE **API-Berechtigungen** hinzufügen Berechtigungs-APIs aus, die meine Organisation >, geben Sie Microsoft Threat Protection ein, und wählen Sie Microsoft  >    >   Threat **Protection aus.** </span><span class="sxs-lookup"><span data-stu-id="126fe-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="126fe-135">Ihre App kann jetzt auf Microsoft 365 Defender zugreifen.</span><span class="sxs-lookup"><span data-stu-id="126fe-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="126fe-136">*Microsoft Threat Protection* ist ein früherer Name für Microsoft 365 Defender und wird nicht in der ursprünglichen Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="126fe-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="126fe-137">Sie müssen damit beginnen, den Namen in das Textfeld zu schreiben, damit er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="126fe-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![Abbildung der Auswahl von APIs](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="126fe-139">Choose **Delegated permissions**.</span><span class="sxs-lookup"><span data-stu-id="126fe-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="126fe-140">Wählen Sie die relevanten Berechtigungen für Ihr Szenario aus (z. B. **Incident.Read),** und wählen Sie dann "Berechtigungen **hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="126fe-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="126fe-142">Sie müssen die relevanten Berechtigungen für Ihr Szenario auswählen.</span><span class="sxs-lookup"><span data-stu-id="126fe-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="126fe-143">*Das Lesen aller Vorfälle* ist nur ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="126fe-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="126fe-144">Um zu bestimmen, welche Berechtigung Sie benötigen, sehen Sie sich den Abschnitt **"Berechtigungen"** in der API an, die Sie aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="126fe-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="126fe-145">Um beispielsweise [erweiterte](api-advanced-hunting.md)Abfragen ausführen zu können, wählen Sie die Berechtigung "Erweiterte Abfragen ausführen" aus. um [ein Gerät zu isolieren,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)wählen Sie die Berechtigung "Computer isolieren" aus.</span><span class="sxs-lookup"><span data-stu-id="126fe-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="126fe-146">Wählen Sie **Administratorzuserteilung aus.**</span><span class="sxs-lookup"><span data-stu-id="126fe-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="126fe-147">Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie die Administratorzuserteilung **auswählen,** damit sie wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="126fe-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![Abbildung der Berechtigungserteilung](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="126fe-149">Noten Sie Ihre Anwendungs-ID und Ihre Mandanten-ID an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="126fe-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="126fe-150">Sie werden auf der **Anwendungsseite unter "Übersicht"** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="126fe-150">They're listed under **Overview** on your application page.</span></span>

   ![Abbildung der erstellten App-ID](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="126fe-152">Abrufen eines Zugriffstokens</span><span class="sxs-lookup"><span data-stu-id="126fe-152">Get an access token</span></span>

<span data-ttu-id="126fe-153">Weitere Informationen zu Azure Active Directory-Token finden Sie im [Azure AD-Lernprogramm.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="126fe-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="126fe-154">Erhalten eines Zugriffstokens mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="126fe-154">Get an access token using PowerShell</span></span>

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

## <a name="validate-the-token"></a><span data-ttu-id="126fe-155">Überprüfen des Tokens</span><span class="sxs-lookup"><span data-stu-id="126fe-155">Validate the token</span></span>

1. <span data-ttu-id="126fe-156">Kopieren Sie das Token, und fügen Sie es in [JWT ein,](https://jwt.ms) um es zu decodieren.</span><span class="sxs-lookup"><span data-stu-id="126fe-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="126fe-157">Stellen Sie sicher, dass *der Rollenanspruch* innerhalb des decodierten Tokens die gewünschten Berechtigungen enthält.</span><span class="sxs-lookup"><span data-stu-id="126fe-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="126fe-158">In der folgenden Abbildung sehen Sie ein decodiertes Token, das von einer App mit ```Incidents.Read.All``` , und Berechtigungen erworben ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` wurde:</span><span class="sxs-lookup"><span data-stu-id="126fe-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Abbildung der Tokenüberprüfung](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="126fe-160">Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API</span><span class="sxs-lookup"><span data-stu-id="126fe-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="126fe-161">Wählen Sie die API aus, die Sie verwenden möchten (Vorfälle oder erweiterte Suche).</span><span class="sxs-lookup"><span data-stu-id="126fe-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="126fe-162">Weitere Informationen finden Sie unter [Unterstützte Microsoft 365 Defender-APIs.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="126fe-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="126fe-163">Legen Sie in der http-Anforderung, die Sie senden möchten, den Autorisierungsheader auf `"Bearer" <token>` " *Bearer"* als Autorisierungsschema und das Token als ihr überprüftes  Token.</span><span class="sxs-lookup"><span data-stu-id="126fe-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="126fe-164">Das Token läuft innerhalb einer Stunde ab.</span><span class="sxs-lookup"><span data-stu-id="126fe-164">The token will expire within one hour.</span></span> <span data-ttu-id="126fe-165">Sie können während dieser Zeit mehr als eine Anforderung mit demselben Token senden.</span><span class="sxs-lookup"><span data-stu-id="126fe-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="126fe-166">Das folgende Beispiel zeigt, wie Sie eine Anforderung senden, um eine Liste der Vorfälle mit **C# zu erhalten.**</span><span class="sxs-lookup"><span data-stu-id="126fe-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="126fe-167">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="126fe-167">Related articles</span></span>

- [<span data-ttu-id="126fe-168">Übersicht über Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="126fe-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="126fe-169">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="126fe-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="126fe-170">Erstellen einer "Hello world"-App</span><span class="sxs-lookup"><span data-stu-id="126fe-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="126fe-171">Erstellen einer App für den Zugriff auf Microsoft 365 Defender ohne Benutzer</span><span class="sxs-lookup"><span data-stu-id="126fe-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="126fe-172">Erstellen einer App mit Mehr-Mandanten-Partnerzugriff auf Microsoft 365 -Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="126fe-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="126fe-173">Informationen zu API-Beschränkungen und Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="126fe-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="126fe-174">Fehlercodes verstehen</span><span class="sxs-lookup"><span data-stu-id="126fe-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="126fe-175">OAuth 2.0-Autorisierung für die Benutzerauthentifizierung und den Zugriff auf die API</span><span class="sxs-lookup"><span data-stu-id="126fe-175">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
