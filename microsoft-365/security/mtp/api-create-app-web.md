---
title: Erstellen einer App für den Zugriff auf Microsoft 365 Defender ohne Benutzer
description: Erfahren Sie, wie Sie eine App für den Zugriff auf Microsoft 365 Defender ohne Benutzer erstellen.
keywords: app, access, api, create
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
ms.openlocfilehash: b9cee02d921ee4d0b9b0b97a109ac9c7141e8aac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924398"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>Erstellen einer App für den Zugriff auf Microsoft 365 Defender ohne Benutzer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Auf dieser Seite wird beschrieben, wie Sie eine Anwendung erstellen, um programmgesteuerten Zugriff auf Microsoft 365 Defender ohne einen definierten Benutzer zu erhalten, z. B. wenn Sie einen Daemon oder Hintergrunddienst erstellen.

Wenn Sie programmgesteuerten Zugriff auf Microsoft 365 Defender im Namen eines oder mehrere Benutzer benötigen, lesen Sie Erstellen einer App für den Zugriff auf [Microsoft 365 Defender-APIs](api-create-app-user-context.md) im Namen eines Benutzers und Erstellen einer App mit Partnerzugriff auf [Microsoft 365 Defender-APIs](api-partner-access.md). Wenn Sie nicht sicher sind, welche Art von Zugriff Sie benötigen, lesen Sie [Erste Schritte](api-access.md).

Microsoft 365 Defender macht einen Großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar. Diese APIs helfen Ihnen, Workflows zu automatisieren und die Funktionen von Microsoft 365 Defender zu nutzen. Für diesen API-Zugriff ist die OAuth2.0-Authentifizierung erforderlich. Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um diese APIs zu verwenden:

- Erstellen Sie eine Azure Active Directory (Azure AD)-Anwendung.
- Mit dieser Anwendung können Sie ein Zugriffstoken erhalten.
- Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zu zugreifen.

In diesem Artikel wird erläutert, wie Sie:

- Erstellen einer Azure AD-Anwendung
- Erhalten eines Zugriffstokens für Microsoft 365 Defender
- Überprüfen Sie das Token.

## <a name="create-an-app"></a>App erstellen

1. Melden Sie sich [bei Azure](https://portal.azure.com) als Benutzer mit der **Rolle "Globaler Administrator"** an.

2. Navigieren Sie zu **Azure Active Directory**  >  **App-Registrierungen** Neue  >  **Registrierung**.

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. Wählen Sie im Formular einen Namen für Ihre Anwendung aus, und wählen Sie dann **Registrieren aus.**

4. Wählen Sie auf der Anwendungsseite **API-Berechtigungen** Hinzufügen von Berechtigungs-APIs aus, die meine > verwendet, geben Sie  >    >   Microsoft **Threat Protection** ein, und wählen Sie **Microsoft Threat Protection aus.** Ihre App kann jetzt auf Microsoft 365 Defender zugreifen.

   > [!TIP]
   > *Microsoft Threat Protection* ist ein früherer Name für Microsoft 365 Defender und wird nicht in der ursprünglichen Liste angezeigt. Sie müssen damit beginnen, den Namen in das Textfeld zu schreiben, damit er angezeigt wird.

   ![Abbildung der API-Berechtigungsauswahl](../../media/apis-in-my-org-tab.PNG)

5. Wählen Sie **Anwendungsberechtigungen aus.** Wählen Sie die relevanten Berechtigungen für Ihr Szenario aus (z. B. **Incident.Read.All**), und wählen Sie **dann Berechtigungen hinzufügen aus.**

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > Sie müssen die relevanten Berechtigungen für Ihr Szenario auswählen. *Das Lesen aller Vorfälle* ist nur ein Beispiel. Um zu bestimmen, welche Berechtigung Sie benötigen, schauen Sie sich den Abschnitt **Berechtigungen** in der API an, die Sie aufrufen möchten.
    >
    > Wählen Sie zum Ausführen [erweiterter Abfragen](api-advanced-hunting.md)beispielsweise die Berechtigung "Erweiterte Abfragen ausführen" aus. Um [ein Gerät zu isolieren,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)wählen Sie die Berechtigung "Computer isolieren" aus.

6. Wählen Sie **Administratorzuwilligung erteilen aus.** Jedes Mal, wenn Sie eine  Berechtigung hinzufügen, müssen Sie Administratorzuwilligung erteilen auswählen, damit sie wirksam wird.

    ![Abbildung der Berechtigungserteilung](../../media/grant-consent.PNG)

7. Wenn Sie der Anwendung einen geheimen Schlüssel hinzufügen möchten, wählen & **Zertifikate** aus, fügen Sie dem Geheimen eine Beschreibung hinzu, und wählen Sie **dann Hinzufügen aus.**

    > [!TIP]
    > Nachdem Sie Hinzufügen **ausgewählt haben,** wählen **Sie den generierten geheimen Wert kopieren aus.** Sie können den geheimen Wert nach dem Verlassen nicht mehr abrufen.

    ![Abbildung des App-Schlüssels erstellen](../../media/webapp-create-key2.png)

8. Noten Sie Ihre Anwendungs-ID und Ihre Mandanten-ID an einem sicheren Ort auf. Sie werden unter **Übersicht auf** Ihrer Anwendungsseite aufgelistet.

   ![Abbildung der erstellten App-ID](../../media/app-and-tenant-ids.png)

9. Nur für **Microsoft 365 Defender Partners:** Befolgen Sie diese Anweisungen für den Partnerzugriff über die Microsoft 365 Defender-APIs, legen Sie Ihre App auf mehr mandantenverdingend, damit sie in allen Mandanten verfügbar sein kann, sobald Sie die Administrator zustimmung erhalten haben. [](./api-partner-access.md) Partnerzugriff ist **für** Drittanbieter-Apps erforderlich, z. B. wenn Sie eine App erstellen, die in Mandanten mehrerer Kunden ausgeführt werden soll. Dies **ist nicht** erforderlich, wenn Sie einen Dienst erstellen, den Sie nur in Ihrem Mandanten ausführen möchten, z. B. eine Anwendung für Ihre eigene Nutzung, die nur mit Ihren eigenen Daten interagiert. So legen Sie ihre App auf mehr mandantenverdingend ein:

    - Wechseln Sie zu **Authentifizierung,** und fügen https://portal.azure.com Sie als **Umleitungs-URI hinzu.**

    - Wählen Sie unten auf der Seite unter Unterstützte **Kontotypen** die Option **Konten in** einer beliebigen Organisationsverzeichnisanwendungs-Zustimmung für Ihre Mehr-Mandanten-App aus.

    Da Ihre Anwendung im Auftrag Ihrer Benutzer mit Microsoft 365 Defender interagiert, muss sie für jeden Mandanten genehmigt werden, für den Sie sie verwenden möchten.

    Der globale Active Directory-Administrator für jeden Mandanten muss den Zustimmungslink auswählen und Ihre App genehmigen.

    Der Zustimmungslink hat die folgende Struktur:

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    Die Ziffern `00000000-0000-0000-0000-000000000000` sollten durch Ihre Anwendungs-ID ersetzt werden.  

**Fertig!** Sie haben eine Anwendung erfolgreich registriert! Weitere Informationen zum Erwerb und zur Überprüfung von Token finden Sie in den folgenden Beispielen.

## <a name="get-an-access-token"></a>Abrufen eines Zugriffstokens

Weitere Informationen zu Azure Active Directory-Token finden Sie im [Azure AD-Lernprogramm](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Obwohl die Beispiele in diesem Abschnitt sie ermutigen, geheime  Werte zu Testzwecken einzugeben, sollten Sie geheime Schlüssel niemals in eine Anwendung hartcodieren, die in der Produktion ausgeführt wird. Ein Drittanbieter kann Ihr Geheimnis für den Zugriff auf Ressourcen verwenden. Mithilfe von Azure Key Vault können Sie die Geheimen Ihrer App [schützen.](/azure/key-vault/general/about-keys-secrets-certificates) Ein praktisches Beispiel, wie Sie Ihre App schützen können, finden Sie unter [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).

### <a name="get-an-access-token-using-powershell"></a>Zugreifen auf ein Zugriffstoken mithilfe von PowerShell

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

### <a name="get-an-access-token-using-c"></a>Zugreifen auf ein Zugriffstoken mithilfe von C\#

> [!NOTE]
> Der folgende Code wurde mit Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 getestet.

1. Erstellen Sie eine neue Konsolenanwendung.

1. Installieren Sie NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).

1. Fügen Sie die folgende Zeile hinzu:

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Kopieren Sie den folgenden Code, und fügen Sie ihn in Ihre App ein (vergessen Sie nicht, die drei Variablen zu aktualisieren: `tenantId` , `clientId` , `appSecret` ):

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

### <a name="get-an-access-token-using-python"></a>Zugreifen auf ein Zugriffstoken mithilfe von Python

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.security.microsoft.com'

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

### <a name="get-an-access-token-using-curl"></a>Erhalten eines Zugriffstokens mithilfe von locken

> [!NOTE]
> Locken ist unter Windows 10, Version 1803 und höher, vorinstalliert. Für andere Versionen von Windows laden Sie das Tool direkt von der offiziellen [locken-Website herunter](https://curl.haxx.se/windows/)und installieren es.

1. Öffnen Sie eine Eingabeaufforderung, und legen CLIENT_ID Auf Ihre Azure-Anwendungs-ID.

1. Legen CLIENT_SECRET auf Ihren geheimen Azure-Anwendungsgeheimnis.

1. Legen TENANT_ID auf die Azure-Mandanten-ID des Kunden fest, der Ihre App für den Zugriff auf Microsoft 365 Defender verwenden möchte.

1. Führen Sie den folgenden Befehl aus:

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   Eine erfolgreiche Antwort sieht wie dies aus:

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a>Überprüfen des Tokens

1. Kopieren Sie das Token, und fügen Sie es in die [JSON-Webtoken-Validierungswebsite JWT ein,](https://jwt.ms) um es zu decodieren.

1. Stellen Sie sicher, dass *der Rollenanspruch* innerhalb des decodierten Tokens die gewünschten Berechtigungen enthält.

   In der folgenden Abbildung sehen Sie ein decodiertes Token, das von einer App erworben wurde, mit `Incidents.Read.All` , `Incidents.ReadWrite.All` und `AdvancedHunting.Read.All` Berechtigungen:

   ![Abbildung der Tokenüberprüfung](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API

1. Wählen Sie die API aus, die Sie verwenden möchten (Vorfälle oder erweiterte Suche). Weitere Informationen finden Sie unter [Supported Microsoft 365 Defender APIs](api-supported.md).

2. Legen Sie in der http-Anforderung, die Sie senden möchten, den Autorisierungsheader auf , Bearer als Autorisierungsschema und Token als ihr überprüftes `"Bearer" <token>` Token.  

3. Das Token läuft innerhalb einer Stunde ab. Sie können während dieser Zeit mehrere Anfragen mit demselben Token senden.

Das folgende Beispiel zeigt, wie Sie eine Anforderung senden, um eine Liste von Vorfällen mithilfe von **C#.**

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über Microsoft 365 Defender-APIs](api-overview.md)
- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
- [Erstellen einer "Hello world"-Anwendung](api-hello-world.md)
- [Erstellen einer App für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers](api-create-app-user-context.md)
- [Erstellen einer App mit Mehr-Mandanten-Partnerzugriff auf Microsoft 365 Defender-APIs](api-partner-access.md)
- [Informationen zu API-Beschränkungen und -Lizenzierung](api-terms.md)
- [Verstehen von Fehlercodes](api-error-codes.md)
- [Verwalten von Geheimschlüsseln in Ihren Server-Apps mit Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2.0-Autorisierung für die Benutzer-Anmeldung und den API-Zugriff](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)