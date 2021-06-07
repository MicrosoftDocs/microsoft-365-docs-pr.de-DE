---
title: Abrufen von Warnungen vom MSSP-Kundenmandanten
description: Erfahren Sie, wie Sie Warnungen von einem Kundenmandanten abrufen
keywords: managed security service provider, mssp, configure, integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: api
ms.openlocfilehash: 456507533265bc085adc1008f3264e123569a6ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770769"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a><span data-ttu-id="45cc8-104">Abrufen von Warnungen vom MSSP-Kundenmandanten</span><span class="sxs-lookup"><span data-stu-id="45cc8-104">Fetch alerts from MSSP customer tenant</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="45cc8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="45cc8-105">**Applies to:**</span></span>
- [<span data-ttu-id="45cc8-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="45cc8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="45cc8-107">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="45cc8-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="45cc8-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="45cc8-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
><span data-ttu-id="45cc8-109">Diese Aktion wird vom MSSP ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="45cc8-109">This action is taken by the MSSP.</span></span>


<span data-ttu-id="45cc8-110">Es gibt zwei Möglichkeiten, Warnungen abzurufen:</span><span class="sxs-lookup"><span data-stu-id="45cc8-110">There are two ways you can fetch alerts:</span></span>
- <span data-ttu-id="45cc8-111">Verwenden der SIEM-Methode</span><span class="sxs-lookup"><span data-stu-id="45cc8-111">Using the SIEM method</span></span>
- <span data-ttu-id="45cc8-112">Verwenden von APIs</span><span class="sxs-lookup"><span data-stu-id="45cc8-112">Using APIs</span></span>

## <a name="fetch-alerts-into-your-siem"></a><span data-ttu-id="45cc8-113">Abrufen von Warnungen in Ihr SIEM</span><span class="sxs-lookup"><span data-stu-id="45cc8-113">Fetch alerts into your SIEM</span></span>

<span data-ttu-id="45cc8-114">Um Warnungen in Ihr SIEM-System abzurufen, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="45cc8-114">To fetch alerts into your SIEM system, you'll need to take the following steps:</span></span>

<span data-ttu-id="45cc8-115">Schritt 1: Erstellen einer Drittanbieteranwendung</span><span class="sxs-lookup"><span data-stu-id="45cc8-115">Step 1: Create a third-party application</span></span>

<span data-ttu-id="45cc8-116">Schritt 2: Abrufen von Zugriffs- und Aktualisierungstoken vom Mandanten Ihres Kunden</span><span class="sxs-lookup"><span data-stu-id="45cc8-116">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
 
<span data-ttu-id="45cc8-117">Schritt 3: Zulassen der Anwendung auf Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="45cc8-117">Step 3: allow your application on Microsoft Defender Security Center</span></span>
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a><span data-ttu-id="45cc8-118">Schritt 1: Erstellen einer Anwendung in Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="45cc8-118">Step 1: Create an application in Azure Active Directory (Azure AD)</span></span>
 
<span data-ttu-id="45cc8-119">Sie müssen eine Anwendung erstellen und ihr Berechtigungen erteilen, um Warnungen vom Microsoft Defender für Endpunkt-Mandanten Ihres Kunden abzurufen.</span><span class="sxs-lookup"><span data-stu-id="45cc8-119">You'll need to create an application and grant it permissions to fetch alerts from your customer's Microsoft Defender for Endpoint tenant.</span></span>

1. <span data-ttu-id="45cc8-120">Melden Sie sich beim [Azure AD-Portal](https://aad.portal.azure.com/)an.</span><span class="sxs-lookup"><span data-stu-id="45cc8-120">Sign in to the [Azure AD portal](https://aad.portal.azure.com/).</span></span>

2. <span data-ttu-id="45cc8-121">Wählen Sie **Azure Active Directory**  >  **App-Registrierungen aus.**</span><span class="sxs-lookup"><span data-stu-id="45cc8-121">Select **Azure Active Directory** > **App registrations**.</span></span>
 
3. <span data-ttu-id="45cc8-122">Klicken Sie auf **"Neue Registrierung".**</span><span class="sxs-lookup"><span data-stu-id="45cc8-122">Click **New registration**.</span></span>

4. <span data-ttu-id="45cc8-123">Geben Sie die folgenden Werte an:</span><span class="sxs-lookup"><span data-stu-id="45cc8-123">Specify the following values:</span></span>

    - <span data-ttu-id="45cc8-124">Name: \<Tenant_name\> SIEM MSSP Connector (ersetzen Sie Tenant_name durch den Anzeigenamen des Mandanten)</span><span class="sxs-lookup"><span data-stu-id="45cc8-124">Name: \<Tenant_name\> SIEM MSSP Connector (replace Tenant_name with the tenant display name)</span></span>
 
    - <span data-ttu-id="45cc8-125">Unterstützte Kontotypen: Nur Konto in diesem Organisationsverzeichnis</span><span class="sxs-lookup"><span data-stu-id="45cc8-125">Supported account types: Account in this organizational directory only</span></span> 
    - <span data-ttu-id="45cc8-126">Umleitungs-URI: Web und Typ auswählen `https://<domain_name>/SiemMsspConnector` (<domain_name> durch den Mandantennamen ersetzen)</span><span class="sxs-lookup"><span data-stu-id="45cc8-126">Redirect URI: Select Web and type `https://<domain_name>/SiemMsspConnector`(replace <domain_name> with the tenant name)</span></span>

5. <span data-ttu-id="45cc8-127">Klicken Sie auf **Registrieren**.</span><span class="sxs-lookup"><span data-stu-id="45cc8-127">Click **Register**.</span></span> <span data-ttu-id="45cc8-128">Die Anwendung wird in der Liste der Anwendungen angezeigt, die Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="45cc8-128">The application is displayed in the list of applications you own.</span></span>

6. <span data-ttu-id="45cc8-129">Wählen Sie die Anwendung aus, und klicken Sie dann auf **"Übersicht".**</span><span class="sxs-lookup"><span data-stu-id="45cc8-129">Select the application, then click **Overview**.</span></span>

7. <span data-ttu-id="45cc8-130">Kopieren Sie den Wert aus dem **Anwendungs-ID-Feld (Client)** an einen sicheren Ort, den Sie im nächsten Schritt benötigen.</span><span class="sxs-lookup"><span data-stu-id="45cc8-130">Copy the value from the **Application (client) ID** field to a safe place, you will need this in the next step.</span></span>

8. <span data-ttu-id="45cc8-131">Wählen Sie im neuen Anwendungsbereich **"Zertifikat & geheime Schlüssel"** aus.</span><span class="sxs-lookup"><span data-stu-id="45cc8-131">Select **Certificate & secrets** in the new application panel.</span></span>

9. <span data-ttu-id="45cc8-132">Klicken Sie auf **"Neuer geheimer Clientschlüssel".**</span><span class="sxs-lookup"><span data-stu-id="45cc8-132">Click **New client secret**.</span></span>

    - <span data-ttu-id="45cc8-133">Beschreibung: Geben Sie eine Beschreibung für den Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="45cc8-133">Description: Enter a description for the key.</span></span>
    - <span data-ttu-id="45cc8-134">Läuft ab: **In 1 Jahr** auswählen</span><span class="sxs-lookup"><span data-stu-id="45cc8-134">Expires: Select **In 1 year**</span></span>

 
10. <span data-ttu-id="45cc8-135">Klicken Sie auf **"Hinzufügen",** kopieren Sie den Wert des geheimen Clientschlüssels an einen sicheren Ort, den Sie im nächsten Schritt benötigen.</span><span class="sxs-lookup"><span data-stu-id="45cc8-135">Click **Add**, copy the value of the client secret to a safe place, you will need this in the next step.</span></span>
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a><span data-ttu-id="45cc8-136">Schritt 2: Abrufen von Zugriffs- und Aktualisierungstoken vom Mandanten Ihres Kunden</span><span class="sxs-lookup"><span data-stu-id="45cc8-136">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
<span data-ttu-id="45cc8-137">In diesem Abschnitt erfahren Sie, wie Sie ein PowerShell-Skript verwenden, um die Token vom Mandanten Ihres Kunden abzurufen.</span><span class="sxs-lookup"><span data-stu-id="45cc8-137">This section guides you on how to use a PowerShell script to get the tokens from your customer's tenant.</span></span> <span data-ttu-id="45cc8-138">Dieses Skript verwendet die Anwendung aus dem vorherigen Schritt, um die Zugriffs- und Aktualisierungstoken mithilfe des OAuth-Autorisierungscodes Flow abzurufen.</span><span class="sxs-lookup"><span data-stu-id="45cc8-138">This script uses the application from the previous step to get the access and refresh tokens using the OAuth Authorization Code Flow.</span></span>

<span data-ttu-id="45cc8-139">Nachdem Sie Ihre Anmeldeinformationen angegeben haben, müssen Sie der Anwendung zustimmen, damit die Anwendung im Mandanten des Kunden bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="45cc8-139">After providing your credentials, you'll need to grant consent to the application so that the application is provisioned in the customer's tenant.</span></span>


1. <span data-ttu-id="45cc8-140">Erstellen Sie einen neuen Ordner, und nennen Sie ihn: `MsspTokensAcquisition` .</span><span class="sxs-lookup"><span data-stu-id="45cc8-140">Create a new folder and name it: `MsspTokensAcquisition`.</span></span>

2. <span data-ttu-id="45cc8-141">Laden Sie das [Modul "LoginBrowser.psm1"](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) herunter, und speichern Sie es im `MsspTokensAcquisition` Ordner.</span><span class="sxs-lookup"><span data-stu-id="45cc8-141">Download the [LoginBrowser.psm1 module](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) and save it in the `MsspTokensAcquisition` folder.</span></span>

    >[!NOTE]
    ><span data-ttu-id="45cc8-142">Ersetzen Sie in Zeile 30 `authorzationUrl` durch `authorizationUrl` .</span><span class="sxs-lookup"><span data-stu-id="45cc8-142">In line 30, replace `authorzationUrl` with `authorizationUrl`.</span></span>

3. <span data-ttu-id="45cc8-143">Erstellen Sie eine Datei mit dem folgenden Inhalt, und speichern Sie sie mit dem Namen `MsspTokensAcquisition.ps1` im Ordner:</span><span class="sxs-lookup"><span data-stu-id="45cc8-143">Create a file with the following content and save it with the name `MsspTokensAcquisition.ps1` in the folder:</span></span>
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. <span data-ttu-id="45cc8-144">Öffnen Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten im `MsspTokensAcquisition` Ordner.</span><span class="sxs-lookup"><span data-stu-id="45cc8-144">Open an elevated PowerShell command prompt in the `MsspTokensAcquisition` folder.</span></span>

5. <span data-ttu-id="45cc8-145">Führen Sie den folgenden Befehl aus:`Set-ExecutionPolicy -ExecutionPolicy Bypass`</span><span class="sxs-lookup"><span data-stu-id="45cc8-145">Run the following command: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span></span>

6. <span data-ttu-id="45cc8-146">Geben Sie die folgenden Befehle ein: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span><span class="sxs-lookup"><span data-stu-id="45cc8-146">Enter the following commands: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span></span>
 
    - <span data-ttu-id="45cc8-147">Ersetzen Sie \<client_id\> dies durch die **Anwendungs-ID (Client-ID),** die Sie aus dem vorherigen Schritt erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="45cc8-147">Replace \<client_id\> with the **Application (client) ID** you got from the previous step.</span></span>
    - <span data-ttu-id="45cc8-148">Ersetzen Sie \<app_key\> dies durch den **geheimen Clientschlüssel,** den Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="45cc8-148">Replace \<app_key\> with the **Client Secret** you created from the previous step.</span></span>
    - <span data-ttu-id="45cc8-149">Ersetzen Sie \<customer_tenant_id\> dies durch die **Mandanten-ID** Ihres Kunden.</span><span class="sxs-lookup"><span data-stu-id="45cc8-149">Replace \<customer_tenant_id\> with your customer's **Tenant ID**.</span></span> 
 

7. <span data-ttu-id="45cc8-150">Sie werden aufgefordert, Ihre Anmeldeinformationen und Ihre Zustimmung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="45cc8-150">You'll be asked to provide your credentials and consent.</span></span> <span data-ttu-id="45cc8-151">Ignorieren Sie die Seitenumleitung.</span><span class="sxs-lookup"><span data-stu-id="45cc8-151">Ignore the page redirect.</span></span>

8. <span data-ttu-id="45cc8-152">Im PowerShell-Fenster erhalten Sie ein Zugriffstoken und ein Aktualisierungstoken.</span><span class="sxs-lookup"><span data-stu-id="45cc8-152">In the PowerShell window, you'll receive an access token and a refresh token.</span></span> <span data-ttu-id="45cc8-153">Speichern Sie das Aktualisierungstoken, um Ihren SIEM-Connector zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="45cc8-153">Save the refresh token to configure your SIEM connector.</span></span> 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a><span data-ttu-id="45cc8-154">Schritt 3: Zulassen der Anwendung auf Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="45cc8-154">Step 3: Allow your application on Microsoft Defender Security Center</span></span>
<span data-ttu-id="45cc8-155">Sie müssen die Anwendung zulassen, die Sie in Microsoft Defender Security Center erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="45cc8-155">You'll need to allow the application you created in Microsoft Defender Security Center.</span></span>
 
<span data-ttu-id="45cc8-156">Sie benötigen die Berechtigung **"Portalsystemeinstellungen verwalten",** um die Anwendung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="45cc8-156">You'll need to have **Manage portal system settings** permission to allow the application.</span></span> <span data-ttu-id="45cc8-157">Andernfalls müssen Sie Ihren Kunden auffordern, die Anwendung für Sie zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="45cc8-157">Otherwise, you'll need to request your customer to allow the application for you.</span></span>

1. <span data-ttu-id="45cc8-158">Wechseln Sie zu `https://securitycenter.windows.com?tid=<customer_tenant_id>` (ersetzen Sie \<customer_tenant_id\> diese durch die Mandanten-ID des Kunden.</span><span class="sxs-lookup"><span data-stu-id="45cc8-158">Go to `https://securitycenter.windows.com?tid=<customer_tenant_id>` (replace \<customer_tenant_id\> with the customer's tenant ID.</span></span>

2. <span data-ttu-id="45cc8-159">Klicken Sie **auf Einstellungen**  >  **SIEM**.</span><span class="sxs-lookup"><span data-stu-id="45cc8-159">Click **Settings** > **SIEM**.</span></span> 

3. <span data-ttu-id="45cc8-160">Wählen Sie die **Registerkarte "MSSP"** aus.</span><span class="sxs-lookup"><span data-stu-id="45cc8-160">Select the **MSSP** tab.</span></span>

4. <span data-ttu-id="45cc8-161">Geben Sie die **Anwendungs-ID** aus dem ersten Schritt und Ihre **Mandanten-ID** ein.</span><span class="sxs-lookup"><span data-stu-id="45cc8-161">Enter the **Application ID** from the first step and your **Tenant ID**.</span></span>

5. <span data-ttu-id="45cc8-162">Klicken Sie auf **"Anwendung autorisieren".**</span><span class="sxs-lookup"><span data-stu-id="45cc8-162">Click **Authorize application**.</span></span> 

 
<span data-ttu-id="45cc8-163">Sie können jetzt die relevante Konfigurationsdatei für Ihr SIEM herunterladen und eine Verbindung mit der Defender für Endpunkt-API herstellen.</span><span class="sxs-lookup"><span data-stu-id="45cc8-163">You can now download the relevant configuration file for your SIEM and connect to the Defender for Endpoint API.</span></span> <span data-ttu-id="45cc8-164">Weitere Informationen finden Sie unter [Pull-Warnungen an Ihre SIEM-Tools.](configure-siem.md)</span><span class="sxs-lookup"><span data-stu-id="45cc8-164">For more information, see, [Pull alerts to your SIEM tools](configure-siem.md).</span></span>
 

- <span data-ttu-id="45cc8-165">Schreiben Sie in der ArcSight-Konfigurationsdatei/Splunk-Authentifizierungseigenschaftendatei Den Anwendungsschlüssel manuell, indem Sie den geheimen Wert festlegen.</span><span class="sxs-lookup"><span data-stu-id="45cc8-165">In the ArcSight configuration file / Splunk Authentication Properties file, write your application key manually by setting the secret value.</span></span>
- <span data-ttu-id="45cc8-166">Anstatt ein Aktualisierungstoken im Portal abzurufen, verwenden Sie das Skript aus dem vorherigen Schritt, um ein Aktualisierungstoken abzurufen (oder es auf andere Weise zu erwerben).</span><span class="sxs-lookup"><span data-stu-id="45cc8-166">Instead of acquiring a refresh token in the portal, use the script from the previous step to acquire a refresh token (or acquire it by other means).</span></span>

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a><span data-ttu-id="45cc8-167">Abrufen von Warnungen vom Mandanten des MSSP-Kunden mithilfe von APIs</span><span class="sxs-lookup"><span data-stu-id="45cc8-167">Fetch alerts from MSSP customer's tenant using APIs</span></span>
 
<span data-ttu-id="45cc8-168">Informationen zum Abrufen von Warnungen mithilfe der REST-API finden Sie unter [Pull-Warnungen mithilfe der REST-API.](pull-alerts-using-rest-api.md)</span><span class="sxs-lookup"><span data-stu-id="45cc8-168">For information on how to fetch alerts using REST API, see [Pull alerts using REST API](pull-alerts-using-rest-api.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="45cc8-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45cc8-169">See also</span></span>
- [<span data-ttu-id="45cc8-170">Gewähren von MSSP-Zugriff auf das Portal</span><span class="sxs-lookup"><span data-stu-id="45cc8-170">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="45cc8-171">Zugreifen auf das MSSP-Kundenportal</span><span class="sxs-lookup"><span data-stu-id="45cc8-171">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="45cc8-172">Warnungsbenachrichtigungen konfigurieren</span><span class="sxs-lookup"><span data-stu-id="45cc8-172">Configure alert notifications</span></span>](configure-mssp-notifications.md)
