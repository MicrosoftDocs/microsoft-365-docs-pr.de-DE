---
title: Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer
description: Informationen zum Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer
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
ms.openlocfilehash: 446db803cc47bfd519642928a4a0257c4b3d57c8
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846068"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Auf dieser Seite wird beschrieben, wie Sie eine Anwendung erstellen, um den programmgesteuerten Zugriff auf Microsoft 365 Defender ohne Benutzer zu erhalten. Wenn Sie im Namen eines Benutzers programmgesteuerten Zugriff auf Microsoft 365 Defender benötigen, finden Sie weitere Informationen unter [Get Access with User Context](api-create-app-user-context.md). Wenn Sie nicht sicher sind, welchen Zugriff Sie benötigen, finden Sie weitere Informationen unter [Erste Schritte](api-access.md).

Microsoft 365 Defender macht einen Großteil seiner Daten und Aktionen über eine Reihe von programmgesteuerten APIs verfügbar. Diese APIs unterstützen Sie bei der Automatisierung von Arbeitsabläufen und Innovationen basierend auf den Microsoft 365 Defender-Funktionen. Für den API-Zugriff ist die OAuth 2.0-Authentifizierung erforderlich. Weitere Informationen finden Sie unter [OAuth 2,0-Autorisierungs Code Fluss](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:
- Erstellen Sie eine Azure Active Directory (Azure AD)-Anwendung.
- Abrufen eines Zugriffstokens mithilfe dieser Anwendung.
- Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zuzugreifen.

In diesem Artikel wird erklärt, wie Sie eine Azure AD Anwendung erstellen, ein Zugriffstoken für Microsoft 365 Defender abrufen und das Token überprüfen.

## <a name="create-an-app"></a>Erstellen einer APP

1. Melden Sie sich bei [Azure](https://portal.azure.com) mit einem Benutzer an, der über die **globale Administrator** Rolle verfügt.

2. Navigieren Sie zu **Azure Active Directory**  >  **App Registrations**  >  **New Registration**. 

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. Wählen Sie im Registrierungsformular einen Namen für Ihre Anwendung aus, und wählen Sie dann **registrieren** aus.

4. Um Ihrer APP den Zugriff auf Microsoft 365 Defender zu ermöglichen und ihr Berechtigungen zuzuweisen, wählen Sie auf Ihrer Anwendungsseite **API-Berechtigungen**  >  **Add permission**  >  **APIs meine Organisation verwendet** > aus, geben Sie **Microsoft 365 Defender** ein, und wählen Sie dann **Microsoft 365 Defender** aus.

   > [!NOTE]
   > Microsoft 365 Defender wird nicht in der ursprünglichen Liste angezeigt. Sie müssen mit dem Schreiben des Namens in das Textfeld beginnen, damit dieser angezeigt wird.

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/apis-in-my-org-tab.PNG)

   - Wählen Sie **Anwendungsberechtigungen** > wählen Sie die relevanten Berechtigungen für Ihr Szenario aus, beispielsweise **Incident. Read. all** , und wählen Sie dann **Berechtigungen hinzufügen** aus.

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions.PNG)

    >[!NOTE]
    >Sie müssen die relevanten Berechtigungen für Ihr Szenario auswählen, **"alle Vorfälle lesen"** ist nur ein Beispiel. Um zu ermitteln, welche Berechtigungen Sie benötigen, sehen Sie sich den Abschnitt **Berechtigungen** in der API an, die Sie aufrufen möchten.

5. Wählen Sie **Zustimmung erteilen** aus.

     > [!NOTE]
     > Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie **Zustimmung erteilen** auswählen, damit die neue Berechtigung wirksam wird.

    ![Image von Grant-Berechtigungen](../../media/grant-consent.PNG)

6. Um der Anwendung ein Geheimnis hinzuzufügen, wählen Sie **Zertifikate & Secrets** aus, fügen Sie eine Beschreibung zum geheimen Schlüssel hinzu, und wählen Sie dann **Hinzufügen** aus.

    > [!NOTE]
    > Nachdem Sie **Hinzufügen** ausgewählt haben, wählen Sie **den generierten geheimen Wert kopieren** aus. Sie können diesen Wert nach dem verlassen nicht mehr abrufen.

    ![Bild der APP-Schlüssel erstellen](../../media/webapp-create-key2.png)

7. Notieren Sie Ihre Anwendungs-ID und ihre Mandanten-ID. Wechseln Sie auf Ihrer Anwendungsseite zur **Übersicht** , und kopieren Sie Folgendes.

   ![Bild der erstellten APP-ID](../../media/app-and-tenant-ids.png)

8. **Nur für Microsoft 365 Defender-Partner**. [Befolgen Sie die Anweisungen hier](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access). Legen Sie fest, dass Ihre APP mehrmandantenfähig ist (nach Zustimmung in allen Mandanten verfügbar). Dies ist für apps von Drittanbietern **erforderlich** (beispielsweise, wenn Sie eine APP erstellen, die in Mandanten mehrerer Kunden ausgeführt werden soll). Dies ist **nicht erforderlich** , wenn Sie einen Dienst erstellen, der nur in Ihrem Mandanten ausgeführt werden soll (beispielsweise, wenn Sie eine Anwendung für Ihre eigene Nutzung erstellen, die nur mit ihren eigenen Daten interagiert). So legen Sie eine mehrmandantenfähige App fest:

    - Wechseln Sie zu **Authentifizierung** , und fügen Sie https://portal.azure.com als **Umleitungs-URI** hinzu.

    - Wählen Sie unten auf der Seite unter **unterstützte Kontotypen** die **Konten in einer beliebigen Organisations Verzeichnis** -Anwendungs Zustimmung für Ihre mandantenfähige App aus.

    Sie müssen Ihre Anwendung in jedem Mandanten genehmigen, in dem Sie Sie verwenden möchten. Dies liegt daran, dass Ihre Anwendung Microsoft 365 Defender im Namen Ihres Kunden interagiert.

    Sie (oder Ihr Kunde, wenn Sie eine Drittanbieter-app schreiben) müssen den Zustimmungs Link auswählen und Ihre APP genehmigen. Die Zustimmung sollte mit einem Benutzer erfolgen, der über Administratorrechte in Active Directory verfügt.

    Der Zustimmungs Link wird wie folgt gebildet: 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Wobei 00000000-0000-0000-0000-000000000000 durch Ihre Anwendungs-ID ersetzt wird.


**Fertig!** Sie haben eine Anwendung erfolgreich registriert! In den folgenden Beispielen finden Sie Informationen zur Token-Erfassung und-Validierung.

## <a name="get-an-access-token"></a>Abrufen eines Zugriffstokens

Weitere Informationen zu Azure AD Token finden Sie im [Azure AD-Lernprogramm](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

### <a name="use-powershell"></a>PowerShell verwenden

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="use-c"></a>Verwenden von C#:

Der folgende Code wurde mit Nuget Microsoft. IdentityModel. Clients. ActiveDirectory 3.19.8 getestet.

1. Erstellen Sie eine neue Konsolenanwendung.
1. Installieren Sie Nuget [Microsoft. IdentityModel. Clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Fügen Sie Folgendes hinzu:

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Kopieren Sie den folgenden Code, und fügen Sie ihn in Ihre APP ein (vergessen Sie nicht, die drei Variablen zu aktualisieren: ```tenantId, appId, appSecret``` ):

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a>Verwenden von python 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```
### <a name="use-curl"></a>Verwenden von curl

> [!NOTE]
> Im folgenden Verfahren wird davon ausgegangen, dass curl für Windows bereits auf Ihrem Computer installiert ist.

1. Öffnen Sie eine Eingabeaufforderung, und legen Sie CLIENT_ID auf Ihre Azure-Anwendungs-ID fest.
1. Legen Sie CLIENT_SECRET auf Ihren Azure-Anwendungsschlüssel fest.
1. Legen Sie TENANT_ID auf die Azure-Mandanten-ID des Kunden fest, der Ihre APP für den Zugriff auf Microsoft 365 Defender verwenden möchte.
1. Führen Sie den folgenden Befehl aus:

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Sie erhalten eine Antwort in folgendem Format:

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Überprüfen des Tokens

Stellen Sie sicher, dass Sie das richtige Token erhalten haben:

1. Kopieren Sie das Token, das Sie im vorherigen Schritt erhalten haben, und fügen Sie es in [JWT](https://jwt.ms) ein, um es zu decodieren.
1. Überprüfen, ob ein "Roles"-Anspruch mit den gewünschten Berechtigungen erhalten wird
1. In der folgenden Abbildung sehen Sie ein decodiertes Token, das von einer APP mit ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` und Berechtigungen erworben wurde ```AdvancedHunting.Read.All``` :

![Bild der Token-Validierung](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-365-defender-api"></a>Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API

1. Wählen Sie die API aus, die Sie verwenden möchten. Weitere Informationen finden Sie unter [Supported Microsoft 365 Defender APIs](api-supported.md).

2. Legen Sie den Autorisierungsheader in der HTTP-Anforderung, die Sie an "Bearer {Token}" senden (Inhaber ist das Autorisierungsschema).

3. Die Ablaufzeit des Tokens beträgt eine Stunde. Sie können mehr als eine Anforderung mit demselben Token senden.

Im folgenden finden Sie ein Beispiel für das Senden einer Anforderung zum Abrufen einer Liste von Vorfällen **mithilfe von C#** : 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a>Verwandte Themen
- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
- [Zugriff auf Microsoft 365 Defender mit Anwendungskontext](api-create-app-web.md)
- [Zugriff auf Microsoft 365 Defender mit Benutzerkontext](api-create-app-user-context.md)
