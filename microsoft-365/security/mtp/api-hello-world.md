---
title: Hello World für Microsoft 365 Defender-Rest-API
description: Informationen zum Erstellen einer APP und Verwenden eines Tokens für den Zugriff auf die Microsoft 365 Defender-APIs
keywords: APP, Token, Access, AAD, APP, Anwendungsregistrierung, PowerShell, Skript, globaler Administrator, Berechtigung, Microsoft 365 Defender
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
ms.openlocfilehash: b36a6acca5880a455a66b03b5355cdf1fb85b29b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719310"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="0be50-104">Hello World für Microsoft 365 Defender-Rest-API</span><span class="sxs-lookup"><span data-stu-id="0be50-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0be50-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0be50-105">**Applies to:**</span></span>

- <span data-ttu-id="0be50-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0be50-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0be50-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="0be50-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0be50-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="0be50-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="0be50-109">Abrufen von Vorfällen mithilfe eines einfachen PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="0be50-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="0be50-110">Es sollte 5 bis 10 Minuten dauern, bis Sie dieses Projekt abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="0be50-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="0be50-111">Diese Zeitschätzung umfasst das Registrieren der Anwendung und das Anwenden des Codes aus dem PowerShell-Beispielskript.</span><span class="sxs-lookup"><span data-stu-id="0be50-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="0be50-112">Registrieren einer APP in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0be50-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="0be50-113">Melden Sie sich als Benutzer mit **globaler Administrator** Rolle bei [Azure](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="0be50-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="0be50-114">Navigieren Sie zu **Azure Active Directory**  >  **App Registrations**  >  **New Registration**.</span><span class="sxs-lookup"><span data-stu-id="0be50-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="0be50-116">Wählen Sie im Registrierungsformular einen Namen für Ihre Anwendung aus, und wählen Sie dann **registrieren** aus.</span><span class="sxs-lookup"><span data-stu-id="0be50-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="0be50-117">Das Auswählen eines Umleitungs-URI ist optional.</span><span class="sxs-lookup"><span data-stu-id="0be50-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="0be50-118">Sie benötigen keins, um dieses Beispiel abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0be50-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="0be50-119">Wählen Sie auf Ihrer Anwendungsseite **API-Berechtigungen**  >  **Add permission**  >  **APIs meine Organisation verwendet** >, geben Sie **Microsoft Threat Protection** ein, und wählen Sie **Microsoft Threat Protection** aus.</span><span class="sxs-lookup"><span data-stu-id="0be50-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="0be50-120">Ihre APP kann nun auf Microsoft 365 Defender zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0be50-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="0be50-121">*Microsoft Threat Protection* ist ein ehemaliger Name für Microsoft 365 Defender und wird nicht in der ursprünglichen Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0be50-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="0be50-122">Sie müssen mit dem Schreiben des Namens in das Textfeld beginnen, damit dieser angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0be50-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="0be50-123">![Abbildung der API-Berechtigungs Auswahl](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="0be50-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="0be50-124">Wählen Sie **Anwendungsberechtigungen**  >  **Vorfall. Read. all** und dann **Berechtigungen hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="0be50-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="0be50-126">Wählen Sie **Administrator Zustimmung erteilen** aus.</span><span class="sxs-lookup"><span data-stu-id="0be50-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="0be50-127">Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie die Option **Administrator Zustimmung erteilen** auswählen, damit Sie wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="0be50-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Image von Grant-Berechtigungen](../../media/grant-consent.PNG)

6. <span data-ttu-id="0be50-129">Fügen Sie der Anwendung ein Kennwort hinzu.</span><span class="sxs-lookup"><span data-stu-id="0be50-129">Add a secret to the application.</span></span> <span data-ttu-id="0be50-130">Wählen Sie **Zertifikate & Geheimnisse** aus, fügen Sie eine Beschreibung zum geheimen Schlüssel hinzu, und wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="0be50-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="0be50-131">Nachdem Sie **Hinzufügen** ausgewählt haben, wählen Sie **den generierten geheimen Wert kopieren** aus.</span><span class="sxs-lookup"><span data-stu-id="0be50-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="0be50-132">Sie können den geheimen Wert nach dem verlassen nicht mehr abrufen.</span><span class="sxs-lookup"><span data-stu-id="0be50-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Bild der APP-Schlüssel erstellen](../../media/webapp-create-key2.png)

7. <span data-ttu-id="0be50-134">Notieren Sie Ihre Anwendungs-ID und ihre Mandanten-ID an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="0be50-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="0be50-135">Sie werden unter **Übersicht** auf Ihrer Anwendungsseite aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0be50-135">They're listed under **Overview** on your application page.</span></span>

   ![Bild der erstellten APP-ID](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="0be50-137">Abrufen eines Tokens mithilfe der APP und Verwenden des Tokens für den Zugriff auf die API</span><span class="sxs-lookup"><span data-stu-id="0be50-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="0be50-138">Weitere Informationen zu Azure Active Directory Token finden Sie im [Azure AD-Lernprogramm](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="0be50-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0be50-139">Das Beispiel in dieser Demo-App ermutigt Sie zwar, den geheimen Wert zu Testzwecken einzufügen, aber Sie sollten **Secrets niemals** in einer Anwendung hartcodieren, die in Production läuft.</span><span class="sxs-lookup"><span data-stu-id="0be50-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="0be50-140">Ein Drittanbieter kann ihren geheimen Schlüssel für den Zugriff auf Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0be50-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="0be50-141">Mithilfe von [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)können Sie die Sicherheit Ihrer APP-Geheimnisse schützen.</span><span class="sxs-lookup"><span data-stu-id="0be50-141">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="0be50-142">Ein praktisches Beispiel dafür, wie Sie Ihre APP schützen können, finden Sie unter [Manage Secrets in Your Server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span><span class="sxs-lookup"><span data-stu-id="0be50-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="0be50-143">Kopieren Sie das Skript unten, und fügen Sie es in Ihren bevorzugten Text-Editor ein.</span><span class="sxs-lookup"><span data-stu-id="0be50-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="0be50-144">Speichern unter **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="0be50-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="0be50-145">Sie können den Code auch wie in PowerShell ISE ausführen, aber Sie sollten ihn speichern, da wir ihn erneut ausführen müssen, wenn wir das Ereignis-Fetching-Skript im nächsten Abschnitt verwenden.</span><span class="sxs-lookup"><span data-stu-id="0be50-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="0be50-146">Dieses Skript generiert ein Token und speichert es im Arbeitsordner unter dem Namen *Latest-token.txt*.</span><span class="sxs-lookup"><span data-stu-id="0be50-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

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

#### <a name="validate-the-token"></a><span data-ttu-id="0be50-147">Überprüfen des Tokens</span><span class="sxs-lookup"><span data-stu-id="0be50-147">Validate the token</span></span>

1. <span data-ttu-id="0be50-148">Kopieren Sie das empfangene Token in [JWT](https://jwt.ms) , und fügen Sie es ein, um es zu decodieren.</span><span class="sxs-lookup"><span data-stu-id="0be50-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="0be50-149">*JWT* steht für *JSON-webtoken*.</span><span class="sxs-lookup"><span data-stu-id="0be50-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="0be50-150">Das decodierte Token enthält eine Reihe von JSON-formatierten Elementen oder Ansprüchen.</span><span class="sxs-lookup"><span data-stu-id="0be50-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="0be50-151">Stellen Sie sicher, dass die *Rollen* Forderung innerhalb des decodierten Tokens die gewünschten Berechtigungen enthält.</span><span class="sxs-lookup"><span data-stu-id="0be50-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="0be50-152">In der folgenden Abbildung sehen Sie ein decodiertes Token, das aus einer APP, mit ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` und Berechtigungen erworben wurde ```AdvancedHunting.Read.All``` :</span><span class="sxs-lookup"><span data-stu-id="0be50-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![Bild JWT.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="0be50-154">Abrufen einer Liste der letzten Vorfälle</span><span class="sxs-lookup"><span data-stu-id="0be50-154">Get a list of recent incidents</span></span>

<span data-ttu-id="0be50-155">Im folgenden Skript wird **Get-Token.ps1** verwendet, um auf die API zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="0be50-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="0be50-156">Anschließend wird eine Liste der Vorfälle abgerufen, die zuletzt in den letzten 48 Stunden aktualisiert wurden, und die Liste wird als JSON-Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0be50-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0be50-157">Speichern Sie dieses Skript im gleichen Ordner, den Sie **Get-Token.ps1** gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="0be50-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

<span data-ttu-id="0be50-158">Sie sind fertig!</span><span class="sxs-lookup"><span data-stu-id="0be50-158">You're all done!</span></span> <span data-ttu-id="0be50-159">Sie haben erfolgreich:</span><span class="sxs-lookup"><span data-stu-id="0be50-159">You've successfully:</span></span>

- <span data-ttu-id="0be50-160">Erstellt und registriert eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0be50-160">Created and registered an application.</span></span>
- <span data-ttu-id="0be50-161">Gewährte Berechtigung für diese Anwendung zum Lesen von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="0be50-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="0be50-162">Mit der API verbunden.</span><span class="sxs-lookup"><span data-stu-id="0be50-162">Connected to the API.</span></span>
- <span data-ttu-id="0be50-163">Ein PowerShell-Skript zum Zurückgeben von Vorfällen verwendet, die in den letzten 48 Stunden aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0be50-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0be50-164">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="0be50-164">Related articles</span></span>

- [<span data-ttu-id="0be50-165">Microsoft 365 Defender-APIs (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="0be50-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="0be50-166">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="0be50-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="0be50-167">Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer</span><span class="sxs-lookup"><span data-stu-id="0be50-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="0be50-168">Erstellen einer APP für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="0be50-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="0be50-169">Erstellen einer APP mit mehr Mandanten fähigem Partner Zugriff auf Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="0be50-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="0be50-170">Verwalten von geheimen Schlüsseln in Ihren Server-apps mit Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="0be50-170">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="0be50-171">OAuth 2,0 Autorisierung für Benutzeranmeldung und API-Zugriff</span><span class="sxs-lookup"><span data-stu-id="0be50-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
