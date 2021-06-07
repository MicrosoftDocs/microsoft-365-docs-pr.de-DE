---
title: Erstellen einer App für den Zugriff auf Microsoft Defender für Endpunkt ohne Benutzer
ms.reviewer: ''
description: Erfahren Sie, wie Sie eine Web-App entwerfen, um programmgesteuerten Zugriff auf Microsoft Defender für Endpunkt ohne Benutzer zu erhalten.
keywords: APIs, Graph-API, unterstützte APIs, Actor, Warnungen, Gerät, Benutzer, Domäne, IP, Datei, erweiterte Suche, Abfrage
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4742a32fd899f41d4e7772c52415891cdd8895bf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769521"
---
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a>Erstellen einer App für den Zugriff auf Microsoft Defender für Endpunkt ohne Benutzer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Auf dieser Seite wird beschrieben, wie Sie eine Anwendung erstellen, um programmgesteuerten Zugriff auf Defender für Endpunkt ohne Einen Benutzer zu erhalten. Wenn Sie programmgesteuerten Zugriff auf Defender für Endpunkt im Namen eines Benutzers benötigen, lesen [Sie "Zugriff mit Benutzerkontext](exposed-apis-create-app-nativeapp.md)erhalten". Wenn Sie nicht sicher sind, welchen Zugriff Sie benötigen, lesen Sie ["Erste Schritte".](apis-intro.md)

Microsoft Defender für Endpunkt macht einen Großteil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar. Diese APIs helfen Ihnen bei der Automatisierung von Arbeitsabläufen und Innovationen basierend auf den Defender für Endpunkt-Funktionen. Der API-Zugriff erfordert die OAuth2.0-Authentifizierung. Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:
- Erstellen Sie eine Azure Active Directory (Azure AD)-Anwendung.
- Rufen Sie mit dieser Anwendung ein Zugriffstoken ab.
- Verwenden Sie das Token, um auf die Defender für Endpunkt-API zuzugreifen.

In diesem Artikel wird erläutert, wie Sie eine Azure AD-Anwendung erstellen, ein Zugriffstoken für Microsoft Defender für Endpunkt abrufen und das Token überprüfen.

## <a name="create-an-app"></a>App erstellen

1. Melden Sie sich bei [Azure](https://portal.azure.com) mit einem Benutzer mit der Rolle **"Globaler Administrator"** an.

2. Navigieren Sie zu **Azure Active Directory**  >  **App-Registrierungen**  >  **Neuregistrierung.** 

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](images/atp-azure-new-app2.png)

3. Wählen Sie im Registrierungsformular einen Namen für Ihre Anwendung aus, und wählen Sie dann **Registrieren** aus.

4. Um Ihrer App den Zugriff auf Defender für Endpunkt zu ermöglichen und ihr die Berechtigung **"Alle Warnungen lesen"** zuzuweisen, wählen Sie auf der Anwendungsseite **API-Berechtigungen**  >  **hinzufügen-APIs** aus, die meine Organisation >  >  **verwendet,** geben Sie **WindowsDefenderATP** ein, und wählen Sie dann **WindowsDefenderATP** aus.

   > [!NOTE]
   > *WindowsDefenderATP* wird nicht in der ursprünglichen Liste angezeigt. Beginnen Sie damit, den Namen in das Textfeld zu schreiben, damit er angezeigt wird.

   ![Berechtigung hinzufügen](images/add-permission.png)

   - Wählen Sie **Anwendungsberechtigungen**  >  **Alert.Read.All** aus, und wählen Sie dann **Berechtigungen hinzufügen** aus.

   ![App-Berechtigung](images/application-permissions.png)

     Sie müssen die entsprechenden Berechtigungen auswählen. "Alle Warnungen lesen" ist nur ein Beispiel. Zum Beispiel:

     - Um [erweiterte Abfragen auszuführen,](run-advanced-query-api.md)wählen Sie die Berechtigung "Erweiterte Abfragen ausführen" aus.
     - Um [ein Gerät zu isolieren,](isolate-machine.md)wählen Sie die Berechtigung "Computer isolieren" aus.
     - Um zu bestimmen, welche Berechtigung Sie benötigen, sehen Sie sich den Abschnitt **"Berechtigungen"** in der API an, die Sie aufrufen möchten.

5. Wählen Sie **"Zustimmung erteilen"** aus.

     > [!NOTE]
     > Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie die **Berechtigung erteilen** auswählen, damit die neue Berechtigung wirksam wird.

    ![Erteilen von Berechtigungen](images/grant-consent.png)

6. Um der Anwendung einen geheimen Schlüssel hinzuzufügen, wählen Sie **Zertifikate & geheimen Schlüssel** aus, fügen Sie eine Beschreibung zum geheimen Schlüssel hinzu, und wählen Sie dann **Hinzufügen** aus.

    > [!NOTE]
    > Nachdem Sie **"Hinzufügen"** ausgewählt haben, wählen Sie **"Generierten geheimen Wert kopieren"** aus. Sie können diesen Wert nach dem Verlassen nicht mehr abrufen.

    ![Abbildung des App-Schlüssels erstellen](images/webapp-create-key2.png)

7. Notieren Sie Ihre Anwendungs-ID und Ihre Mandanten-ID. Wechseln Sie auf der Anwendungsseite zu **"Übersicht",** und kopieren Sie Folgendes.

   ![Abbildung der erstellten App-ID](images/app-and-tenant-ids.png)

8. **Nur für Microsoft Defender für Endpunktpartner.** Legen Sie fest, dass Ihre App mehrinstanzenfähig ist (nach der Zustimmung in allen Mandanten verfügbar). Dies ist für Drittanbieter-Apps **erforderlich** (z. B. wenn Sie eine App erstellen, die für die Ausführung im Mandanten mehrerer Kunden vorgesehen ist). Dies ist **nicht erforderlich,** wenn Sie einen Dienst erstellen, den Sie nur in Ihrem Mandanten ausführen möchten (z. B. wenn Sie eine Anwendung für Ihre eigene Nutzung erstellen, die nur mit Ihren eigenen Daten interagiert). So legen Sie fest, dass Ihre App mehrinstanzenfähig ist:

    - Wechseln Sie zur **Authentifizierung,** und fügen Sie `https://portal.azure.com` sie als **Umleitungs-URI hinzu.**

    - Wählen Sie unten auf der Seite unter **Unterstützte Kontotypen** die **Konten in einer beliebigen Organisationsverzeichnisanwendungsgenehmigung** für Ihre mehrinstanzenfähige App aus.

    Ihre Anwendung muss in jedem Mandanten genehmigt werden, in dem Sie sie verwenden möchten. Dies liegt daran, dass Ihre Anwendung Defender für Endpunkt im Auftrag Ihres Kunden interagiert.

    Sie (oder Ihr Kunde, wenn Sie eine Drittanbieter-App schreiben) müssen den Zustimmungslink auswählen und Ihre App genehmigen. Die Zustimmung sollte mit einem Benutzer erfolgen, der über Administratorrechte in Active Directory verfügt.

    Der Zustimmungslink wird wie folgt gebildet: 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Dabei wird 00000000-0000-0000-0000-000000000000 durch Ihre Anwendungs-ID ersetzt.


**fertig!** Sie haben eine Anwendung erfolgreich registriert! Beispiele für den Erwerb und die Validierung von Token finden Sie weiter unten.

## <a name="get-an-access-token"></a>Abrufen eines Zugriffstokens

Weitere Informationen zu Azure AD-Token finden Sie im [Azure AD-Lernprogramm.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="use-powershell"></a>PowerShell verwenden

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

### <a name="use-c"></a>Verwenden Sie C#:

Der folgende Code wurde mit NuGet Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 getestet.

1. Erstellen Sie eine neue Konsolenanwendung.
1. Installieren Sie NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Fügen Sie Folgendes hinzu:

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Kopieren Sie den folgenden Code, und fügen Sie ihn in Ihre App ein (vergessen Sie nicht, die drei Variablen zu aktualisieren: ```tenantId, appId, appSecret``` ):

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


### <a name="use-python"></a>Verwenden von Python

Weitere Informationen finden Sie unter [Abrufen von Token mit Python.](run-advanced-query-sample-python.md#get-token)

### <a name="use-curl"></a>Verwenden von Curl

> [!NOTE]
> Im folgenden Verfahren wird davon ausgegangen, dass Curl for Windows bereits auf Ihrem Computer installiert ist.

1. Öffnen Sie eine Eingabeaufforderung, und legen Sie CLIENT_ID auf Ihre Azure-Anwendungs-ID fest.
1. Legen Sie CLIENT_SECRET auf Ihren geheimen Azure-Anwendungsschlüssel fest.
1. Legen Sie TENANT_ID auf die Azure-Mandanten-ID des Kunden fest, der Ihre App für den Zugriff auf Defender für Endpunkt verwenden möchte.
1. Führen Sie den folgenden Befehl aus:

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Sie erhalten eine Antwort in der folgenden Form:

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Überprüfen des Tokens

Stellen Sie sicher, dass Sie das richtige Token erhalten haben:

1. Kopieren Sie das Token, das Sie im vorherigen Schritt erhalten haben, und fügen Sie es in [JWT](https://jwt.ms) ein, um es zu decodieren.
1. Überprüfen, ob Sie einen "Rollen"-Anspruch mit den gewünschten Berechtigungen erhalten
1. In der folgenden Abbildung sehen Sie ein decodiertes Token, das von einer App mit Berechtigungen für alle Microsoft Defender für Endpunkt-Rollen erworben wurde:

![Abbildung der Tokenüberprüfung](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>Verwenden des Tokens für den Zugriff auf die Microsoft Defender für Endpunkt-API

1. Wählen Sie die API aus, die Sie verwenden möchten. Weitere Informationen finden Sie unter [Unterstützte Defender für Endpunkt-APIs.](exposed-apis-list.md)
1. Legen Sie den Autorisierungsheader in der http-Anforderung, die Sie senden, auf "Bearer {token}" fest (Bearer ist das Autorisierungsschema).
1. Die Ablaufzeit des Tokens beträgt eine Stunde. Sie können mehrere Anforderungen mit demselben Token senden.

Es folgt ein Beispiel für das Senden einer Anforderung zum Abrufen einer Liste von Warnungen **mit C#:** 
```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="see-also"></a>Siehe auch
- [Unterstütze Microsoft Defender für Endpoint-APIs](exposed-apis-list.md)
- [Zugreifen auf Microsoft Defender für Endpunkt im Namen eines Benutzers](exposed-apis-create-app-nativeapp.md)
