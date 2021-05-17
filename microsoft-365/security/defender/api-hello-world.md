---
title: Hello World for Microsoft 365 Defender REST API
description: Erfahren Sie, wie Sie eine App erstellen und ein Token für den Zugriff auf die Microsoft 365 Defender-APIs verwenden
keywords: app, token, access, aad, app, application registration, powershell, script, global administrator, permission, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ffdcf91da6b5def7d63e5fdb8ff51ddbdb1ec550
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064719"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="e8358-104">Hello World for Microsoft 365 Defender REST API</span><span class="sxs-lookup"><span data-stu-id="e8358-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e8358-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e8358-105">**Applies to:**</span></span>

- <span data-ttu-id="e8358-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8358-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8358-107">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="e8358-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e8358-108">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="e8358-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="e8358-109">Erhalten von Vorfällen mithilfe eines einfachen PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="e8358-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="e8358-110">Es sollte 5 bis 10 Minuten dauern, bis dieses Projekt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e8358-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="e8358-111">Diese Zeitschätzung umfasst das Registrieren der Anwendung und das Anwenden des Codes aus dem PowerShell-Beispielskript.</span><span class="sxs-lookup"><span data-stu-id="e8358-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="e8358-112">Registrieren einer App in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e8358-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="e8358-113">Melden Sie sich [bei Azure](https://portal.azure.com) als Benutzer mit der Rolle **"Globaler Administrator"** an.</span><span class="sxs-lookup"><span data-stu-id="e8358-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="e8358-114">Navigieren Sie zu **Azure Active Directory**  >  **App-Registrierungen**  >  **Neue Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="e8358-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="e8358-116">Wählen Sie im Registrierungsformular einen Namen für Ihre Anwendung aus, und wählen Sie dann **Registrieren aus.**</span><span class="sxs-lookup"><span data-stu-id="e8358-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="e8358-117">Das Auswählen eines Umleitungs-URI ist optional.</span><span class="sxs-lookup"><span data-stu-id="e8358-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="e8358-118">Sie benötigen keinen, um dieses Beispiel zu vervollständigen.</span><span class="sxs-lookup"><span data-stu-id="e8358-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="e8358-119">Wählen Sie auf der Anwendungsseite **API-Berechtigungen** Hinzufügen von Berechtigungs-APIs aus, die meine > verwendet, geben Sie  >    >   **Microsoft Threat Protection** ein, und wählen Sie **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="e8358-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="e8358-120">Ihre App kann jetzt auf Microsoft 365 zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e8358-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="e8358-121">*Microsoft Threat Protection* ist ein früherer Name für Microsoft 365 Defender und wird nicht in der ursprünglichen Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e8358-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="e8358-122">Sie müssen damit beginnen, den Namen in das Textfeld zu schreiben, damit er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e8358-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="e8358-123">![Abbildung der API-Berechtigungsauswahl](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="e8358-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="e8358-124">Wählen **Sie Anwendungsberechtigungen**  >  **Incident.Read.All aus,** und wählen Sie Berechtigungen hinzufügen **aus.**</span><span class="sxs-lookup"><span data-stu-id="e8358-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="e8358-126">Wählen Sie **Administratorzuwilligung erteilen aus.**</span><span class="sxs-lookup"><span data-stu-id="e8358-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="e8358-127">Jedes Mal, wenn Sie eine  Berechtigung hinzufügen, müssen Sie Administratorzuwilligung erteilen auswählen, damit sie wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="e8358-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Abbildung der Berechtigungserteilung](../../media/grant-consent.PNG)

6. <span data-ttu-id="e8358-129">Fügen Sie der Anwendung einen geheimen Schlüssel hinzu.</span><span class="sxs-lookup"><span data-stu-id="e8358-129">Add a secret to the application.</span></span> <span data-ttu-id="e8358-130">Wählen **Sie Zertifikate & Schlüssel** aus, fügen Sie dem Geheimen eine Beschreibung hinzu, und wählen Sie dann Hinzufügen **aus.**</span><span class="sxs-lookup"><span data-stu-id="e8358-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="e8358-131">Nachdem Sie Hinzufügen **ausgewählt haben,** wählen **Sie den generierten geheimen Wert kopieren aus.**</span><span class="sxs-lookup"><span data-stu-id="e8358-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="e8358-132">Sie können den geheimen Wert nach dem Verlassen nicht mehr abrufen.</span><span class="sxs-lookup"><span data-stu-id="e8358-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Abbildung des App-Schlüssels erstellen](../../media/webapp-create-key2.png)

7. <span data-ttu-id="e8358-134">Noten Sie Ihre Anwendungs-ID und Ihre Mandanten-ID an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="e8358-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="e8358-135">Sie werden unter **Übersicht auf** Ihrer Anwendungsseite aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="e8358-135">They're listed under **Overview** on your application page.</span></span>

   ![Abbildung der erstellten App-ID](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="e8358-137">Abrufen eines Tokens mithilfe der App und Verwenden des Tokens für den Zugriff auf die API</span><span class="sxs-lookup"><span data-stu-id="e8358-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="e8358-138">Weitere Informationen zu Azure Active Directory Token finden Sie im [Azure AD-Lernprogramm](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="e8358-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8358-139">Das Beispiel in dieser Demo-App ermutigt Sie zwar, ihren  geheimen Wert zu Testzwecken einzugeben, aber Sie sollten geheime Schlüssel niemals in eine Anwendung hartcodieren, die in der Produktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e8358-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="e8358-140">Ein Drittanbieter kann Ihr Geheimnis für den Zugriff auf Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8358-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="e8358-141">Mithilfe von Azure Key Vault können Sie die Geheimen Ihrer App [schützen.](/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="e8358-141">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="e8358-142">Ein praktisches Beispiel, wie Sie Ihre App schützen können, finden Sie unter [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span><span class="sxs-lookup"><span data-stu-id="e8358-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="e8358-143">Kopieren Sie das skript unten, und fügen Sie es in Ihren bevorzugten Texteditor ein.</span><span class="sxs-lookup"><span data-stu-id="e8358-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="e8358-144">Speichern unter **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="e8358-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="e8358-145">Sie können den Code auch wie in PowerShell ISE ausführen, aber Sie sollten ihn speichern, da wir ihn erneut ausführen müssen, wenn wir das Skript zum Abrufen von Vorfällen im nächsten Abschnitt verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8358-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="e8358-146">Dieses Skript generiert ein Token und speichern es im Arbeitsordner unter dem Namen *Latest-token.txt*.</span><span class="sxs-lookup"><span data-stu-id="e8358-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

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

#### <a name="validate-the-token"></a><span data-ttu-id="e8358-147">Überprüfen des Tokens</span><span class="sxs-lookup"><span data-stu-id="e8358-147">Validate the token</span></span>

1. <span data-ttu-id="e8358-148">Kopieren Sie das token, das Sie erhalten haben, und fügen Sie es in [JWT](https://jwt.ms) ein, um es zu decodieren.</span><span class="sxs-lookup"><span data-stu-id="e8358-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="e8358-149">*JWT* steht für *JSON Web Token*.</span><span class="sxs-lookup"><span data-stu-id="e8358-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="e8358-150">Das decodierte Token enthält eine Reihe von JSON-formatierten Elementen oder Ansprüchen.</span><span class="sxs-lookup"><span data-stu-id="e8358-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="e8358-151">Stellen Sie sicher, dass *der Rollenanspruch* innerhalb des decodierten Tokens die gewünschten Berechtigungen enthält.</span><span class="sxs-lookup"><span data-stu-id="e8358-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="e8358-152">In der folgenden Abbildung sehen Sie ein decodiertes Token, das von einer App erworben wurde, mit ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` und ```AdvancedHunting.Read.All``` Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="e8358-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![Bild jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="e8358-154">Eine Liste der letzten Vorfälle erhalten</span><span class="sxs-lookup"><span data-stu-id="e8358-154">Get a list of recent incidents</span></span>

<span data-ttu-id="e8358-155">Das folgende Skript verwendet **Get-Token.ps1** für den Zugriff auf die API.</span><span class="sxs-lookup"><span data-stu-id="e8358-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="e8358-156">Anschließend wird eine Liste der Vorfälle abgerufen, die zuletzt innerhalb der letzten 48 Stunden aktualisiert wurden, und speichert die Liste als JSON-Datei.</span><span class="sxs-lookup"><span data-stu-id="e8358-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8358-157">Speichern Sie dieses Skript in dem Ordner, den Sie **Get-Token.ps1.**</span><span class="sxs-lookup"><span data-stu-id="e8358-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

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

<span data-ttu-id="e8358-158">Sie sind alle fertig!</span><span class="sxs-lookup"><span data-stu-id="e8358-158">You're all done!</span></span> <span data-ttu-id="e8358-159">Sie haben erfolgreich:</span><span class="sxs-lookup"><span data-stu-id="e8358-159">You've successfully:</span></span>

- <span data-ttu-id="e8358-160">Eine Anwendung wurde erstellt und registriert.</span><span class="sxs-lookup"><span data-stu-id="e8358-160">Created and registered an application.</span></span>
- <span data-ttu-id="e8358-161">Erteilte Berechtigung für diese Anwendung zum Lesen von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="e8358-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="e8358-162">Mit der API verbunden.</span><span class="sxs-lookup"><span data-stu-id="e8358-162">Connected to the API.</span></span>
- <span data-ttu-id="e8358-163">Verwendet ein PowerShell-Skript, um Vorfälle zurückzukehren, die in den letzten 48 Stunden aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e8358-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e8358-164">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="e8358-164">Related articles</span></span>

- [<span data-ttu-id="e8358-165">Microsoft 365 Übersicht über Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="e8358-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="e8358-166">Zugreifen auf die Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="e8358-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="e8358-167">Erstellen einer App für den Zugriff Microsoft 365 Defender ohne Benutzer</span><span class="sxs-lookup"><span data-stu-id="e8358-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="e8358-168">Erstellen einer App für den Zugriff auf Microsoft 365 Defender-APIs im Namen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="e8358-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="e8358-169">Erstellen einer App mit Mehr-Mandanten-Partnerzugriff auf Microsoft 365 Defender-APIs</span><span class="sxs-lookup"><span data-stu-id="e8358-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="e8358-170">Verwalten von Geheimschlüsseln in Ihren Server-Apps mit Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="e8358-170">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="e8358-171">OAuth 2.0 Autorisierung für die Benutzer anmeldung und den API-Zugriff</span><span class="sxs-lookup"><span data-stu-id="e8358-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)