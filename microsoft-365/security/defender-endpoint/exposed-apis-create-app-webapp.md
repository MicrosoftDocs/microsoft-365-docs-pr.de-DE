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
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a>Erstellen einer App für den Zugriff auf Microsoft Defender for Endpoint ohne Benutzer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Auf dieser Seite wird beschrieben, wie Sie eine Anwendung erstellen, um programmgesteuerten Zugriff auf Defender for Endpoint ohne Benutzer zu erhalten. Wenn Sie programmgesteuerten Zugriff auf Defender for Endpoint im Namen eines Benutzers benötigen, lesen Sie [Zugriff mit Benutzerkontext erhalten.](exposed-apis-create-app-nativeapp.md) Wenn Sie nicht sicher sind, welchen Zugriff Sie benötigen, lesen [Sie Erste Schritte](apis-intro.md).

Microsoft Defender for Endpoint macht einen Großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar. Diese APIs helfen Ihnen bei der Automatisierung von Arbeitsabläufen und innovationen basierend auf den Defender for Endpoint-Funktionen. Für den API-Zugriff ist die OAuth2.0-Authentifizierung erforderlich. Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:
- Erstellen Sie Azure Active Directory (Azure AD)-Anwendung.
- Mit dieser Anwendung können Sie ein Zugriffstoken erhalten.
- Verwenden Sie das Token, um auf die Defender for Endpoint-API zu zugreifen.

In diesem Artikel wird erläutert, wie Sie eine Azure AD-Anwendung erstellen, ein Zugriffstoken für Microsoft Defender for Endpoint erhalten und das Token überprüfen.

## <a name="create-an-app"></a>App erstellen

1. Melden Sie sich [mit einem](https://portal.azure.com) Benutzer mit der Rolle **"Globaler Administrator"** bei Azure an.

2. Navigieren Sie zu **Azure Active Directory**  >  **App-Registrierungen**  >  **Neue Registrierung**. 

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](images/atp-azure-new-app2.png)

3. Wählen Sie im Registrierungsformular einen Namen für Ihre Anwendung aus, und wählen Sie dann **Registrieren aus.**

4. Um Ihrer App den Zugriff auf Defender for Endpoint und die Berechtigung "Alle Warnungen **lesen"** zu ermöglichen, wählen Sie auf der Anwendungsseite **API-Berechtigungen** Hinzufügen von Berechtigungs-APIs aus, die meine Organisation > verwendet, geben  >    >   **Sie WindowsDefenderATP** ein, und wählen Sie **dann WindowsDefenderATP** aus.

   > [!NOTE]
   > *WindowsDefenderATP* wird nicht in der ursprünglichen Liste angezeigt. Beginnen Sie, den Namen in das Textfeld zu schreiben, damit er angezeigt wird.

   ![Hinzufügen von Berechtigungen](images/add-permission.png)

   - Wählen **Sie Anwendungsberechtigungen**  >  **Alert.Read.All** aus, und wählen Sie **dann Berechtigungen hinzufügen aus.**

   ![App-Berechtigung](images/application-permissions.png)

     Sie müssen die entsprechenden Berechtigungen auswählen. "Alle Warnungen lesen" ist nur ein Beispiel. Zum Beispiel:

     - Wählen [Sie zum Ausführen erweiterter](run-advanced-query-api.md)Abfragen die Berechtigung "Erweiterte Abfragen ausführen" aus.
     - Wählen [Sie zum Isolieren](isolate-machine.md)eines Geräts die Berechtigung "Computer isolieren" aus.
     - Um zu bestimmen, welche Berechtigung Sie benötigen, sehen Sie sich den Abschnitt **Berechtigungen** in der API an, die Sie aufrufen möchten.

5. Wählen Sie **Zustimmung erteilen aus.**

     > [!NOTE]
     > Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie **Zustimmung** erteilen auswählen, damit die neue Berechtigung wirksam wird.

    ![Erteilen von Berechtigungen](images/grant-consent.png)

6. Wenn Sie der Anwendung einen geheimen Schlüssel hinzufügen möchten, wählen & **Zertifikate** aus, fügen Sie dem Geheimen eine Beschreibung hinzu, und wählen Sie dann **Hinzufügen aus.**

    > [!NOTE]
    > Nachdem Sie Hinzufügen **ausgewählt haben,** wählen **Sie den generierten geheimen Wert kopieren aus.** Sie können diesen Wert nach dem Verlassen nicht mehr abrufen.

    ![Abbildung des App-Schlüssels erstellen](images/webapp-create-key2.png)

7. Notieren Sie sich Ihre Anwendungs-ID und Ihre Mandanten-ID. Wechseln Sie auf der Anwendungsseite zu **Übersicht,** und kopieren Sie Folgendes.

   ![Abbildung der erstellten App-ID](images/app-and-tenant-ids.png)

8. **Nur für Microsoft Defender für Endpunktpartner**. Legen Sie ihre App auf multi-tenanted (verfügbar in allen Mandanten nach Zustimmung) festgelegt. Dies **ist für** Drittanbieter-Apps erforderlich (z. B. wenn Sie eine App erstellen, die im Mandanten mehrerer Kunden ausgeführt werden soll). Dies **ist nicht** erforderlich, wenn Sie einen Dienst erstellen, den Sie nur in Ihrem Mandanten ausführen möchten (z. B. wenn Sie eine Anwendung für Ihre eigene Nutzung erstellen, die nur mit Ihren eigenen Daten interagiert). So legen Sie ihre App auf mehr mandantenverdant festgelegt:

    - Wechseln Sie zu **Authentifizierung,** und fügen `https://portal.azure.com` Sie als **Umleitungs-URI hinzu.**

    - Wählen Sie unten auf der Seite unter Unterstützte **Kontotypen** die Option **Konten in** einer beliebigen Organisationsverzeichnisanwendungs-Zustimmung für Ihre Mehr-Mandanten-App aus.

    Ihre Anwendung muss in jedem Mandanten genehmigt werden, in dem Sie sie verwenden möchten. Dies liegt daran, dass Ihre Anwendung Defender for Endpoint im Auftrag Ihres Kunden interagiert.

    Sie (oder Ihr Kunde, wenn Sie eine Drittanbieter-App schreiben) müssen den Zustimmungslink auswählen und Ihre App genehmigen. Die Zustimmung sollte mit einem Benutzer durchgeführt werden, der über Administratorrechte in Active Directory verfügt.

    Der Zustimmungslink besteht wie folgt: 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Dabei wird 00000000-0000-0000-0000-0000000000000 durch Ihre Anwendungs-ID ersetzt.


**Fertig!** Sie haben eine Anwendung erfolgreich registriert! Weitere Informationen zum Erwerb und zur Überprüfung von Token finden Sie in den folgenden Beispielen.

## <a name="get-an-access-token"></a>Abrufen eines Zugriffstokens

Weitere Informationen zu Azure AD-Token finden Sie im [Azure AD-Lernprogramm](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

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

### <a name="use-c"></a>Verwenden C#:

Der folgende Code wurde mit NuGet Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 getestet.

1. Erstellen Sie eine neue Konsolenanwendung.
1. Installieren NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
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

Weitere [Informationen finden Sie unter Get token using Python](run-advanced-query-sample-python.md#get-token).

### <a name="use-curl"></a>Verwenden von Locken

> [!NOTE]
> Im folgenden Verfahren wird davon ausgegangen, dass "Locken für Windows" bereits auf Ihrem Computer installiert ist.

1. Öffnen Sie eine Eingabeaufforderung, und legen CLIENT_ID Auf Ihre Azure-Anwendungs-ID.
1. Legen CLIENT_SECRET auf Ihren geheimen Azure-Anwendungsgeheimnis.
1. Legen TENANT_ID auf die Azure-Mandanten-ID des Kunden fest, der Ihre App für den Zugriff auf Defender for Endpoint verwenden möchte.
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
1. Überprüfen, ob Sie einen "Rollen"-Anspruch mit den gewünschten Berechtigungen erhalten
1. In der folgenden Abbildung sehen Sie ein decodiertes Token, das von einer App mit Berechtigungen für alle Rollen von Microsoft Defender for Endpoint erworben wurde:

![Abbildung der Tokenüberprüfung](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>Verwenden des Tokens für den Zugriff auf Die Microsoft Defender for Endpoint-API

1. Wählen Sie die API aus, die Sie verwenden möchten. Weitere Informationen finden Sie unter [Supported Defender for Endpoint APIs](exposed-apis-list.md).
1. Legen Sie den Autorisierungsheader in der http-Anforderung, die Sie an "Bearer {token}" senden, (Bearer ist das Autorisierungsschema).
1. Die Ablaufzeit des Tokens beträgt eine Stunde. Sie können mehrere Anfragen mit demselben Token senden.

Im Folgenden sehen Sie ein Beispiel für das Senden einer Anforderung zum Anfordern einer Liste von **Warnungen mithilfe C#:** 
```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="see-also"></a>Siehe auch
- [Unterstütze Microsoft Defender für Endpoint-APIs](exposed-apis-list.md)
- [Zugreifen auf Microsoft Defender for Endpoint im Namen eines Benutzers](exposed-apis-create-app-nativeapp.md)
