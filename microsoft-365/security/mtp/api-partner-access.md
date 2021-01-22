---
title: Partnerzugriff über Microsoft 365 Defender-APIs
description: Erfahren Sie, wie Sie eine App erstellen, um im Namen Ihrer Benutzer programmgesteuerten Zugriff auf Microsoft 365 Defender zu erhalten.
keywords: Partner, Zugriff, API, Mehr mandant, Zustimmung, Zugriffstoken, App
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
ms.openlocfilehash: 07afb0baf5c115f2029abfe03795b081a4f253a8
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929398"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a>Erstellen einer App mit Partnerzugriff auf Microsoft 365 Defender-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Auf dieser Seite wird beschrieben, wie Sie eine Azure Active Directory-App erstellen, die programmgesteuerten Zugriff auf Microsoft 365 Defender im Namen von Benutzern in mehreren Mandanten hat. Apps mit mehreren Mandanten n

Wenn Sie programmgesteuerten Zugriff auf Microsoft 365 Defender im Namen eines einzelnen Benutzers benötigen, lesen Sie "Erstellen einer App für den Zugriff auf [Microsoft 365 Defender-APIs](api-create-app-user-context.md)im Auftrag eines Benutzers". Wenn Sie Zugriff benötigen, ohne dass ein Benutzer explizit definiert ist (z. B. wenn Sie eine Hintergrund-App oder einen Daemon schreiben), lesen Sie "Erstellen einer App für den Zugriff auf [Microsoft 365 Defender ohne Benutzer".](api-create-app-web.md) Wenn Sie nicht sicher sind, welche Art von Zugriff Sie benötigen, lesen Sie ["Erste Schritte".](api-access.md)

Microsoft 365 Defender macht einen Großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar. Mit diesen APIs können Sie Workflows automatisieren und die Funktionen von Microsoft 365 Defender nutzen. Für diesen ZUGRIFF auf die API ist die OAuth2.0-Authentifizierung erforderlich. Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um diese APIs zu verwenden:

- Erstellen Sie eine Azure Active Directory (Azure AD)-Anwendung.
- Mit dieser Anwendung können Sie ein Zugriffstoken erhalten.
- Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zu zugreifen.

Da diese App mehrere Mandanten hat, [](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) benötigen Sie auch die Administratoreinwilligung von jedem Mandanten im Namen seiner Benutzer.

In diesem Artikel wird erläutert, wie Sie:

- Erstellen einer **mehrstufigen Azure AD-Anwendung**
- Holen Sie sich autorisierte Zustimmung von Ihrem Benutzeradministrator für Ihre Anwendung, um auf die benötigten Ressourcen von Microsoft 365 Defender zu zugreifen.
- Erhalten eines Zugriffstokens für Microsoft 365 Defender
- Überprüfen des Tokens

Microsoft 365 Defender macht einen Großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar. Diese APIs helfen Ihnen bei der Automatisierung von Arbeitsflüssen und Innovationen basierend auf microsoft 365 Defender-Funktionen. Der Zugriff auf die API erfordert die OAuth2.0-Authentifizierung. Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:

- Erstellen Sie **eine azure ad-Anwendung mit** mehreren Mandanten.
- Lassen Sie sich von Ihrem Benutzeradministrator autorisiert (zustimmung) für Ihre Anwendung, um auf die benötigten Microsoft 365 Defender-Ressourcen zu zugreifen.
- Mit dieser Anwendung können Sie ein Zugriffstoken erhalten.
- Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zu zugreifen.

Die folgenden Schritte mit Anleitungen zum Erstellen einer azure ad-Anwendung mit mehreren Mandanten, zum Erhalten eines Zugriffstokens für Microsoft 365 Defender und zum Überprüfen des Tokens.

## <a name="create-the-multi-tenant-app"></a>Erstellen der mehrstufigen App

1. Melden Sie sich [bei Azure](https://portal.azure.com) als Benutzer mit der rolle **"Globaler Administrator"** an.

2. Navigieren Sie zu **Azure Active**  >  **Directory-App-Registrierungen**  >  **Neue Registrierung.**

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. Im Registrierungsformular:

   - Wählen Sie einen Namen für Ihre Anwendung aus.
   - Wählen **Sie unter den unterstützten** Kontotypen Konten in einem **beliebigen Organisationsverzeichnis (Beliebiges Azure AD-Verzeichnis) – Mehrant aus.**
   - Füllen Sie den Abschnitt **"Umleitungs-URI"** aus. Wählen Sie **"Web"** aus, und geben Sie den Umleitungs-URI **https://portal.azure.com** als .

   Nachdem Sie das Ausfüllen des Formulars fertig haben, wählen Sie **"Registrieren" aus.**

   ![Abbildung des Formulars "Anwendung registrieren"](../..//media/atp-api-new-app-partner.png)

4. Wählen Sie auf der Anwendungsseite DIE **API-Berechtigungen** hinzufügen Berechtigungs-APIs aus, die meine Organisation >, geben Sie Microsoft Threat Protection ein, und wählen Sie Microsoft  >    >   Threat **Protection aus.**  Ihre App kann jetzt auf Microsoft 365 Defender zugreifen.

   > [!TIP]
   > *Microsoft Threat Protection* ist ein früherer Name für Microsoft 365 Defender und wird nicht in der ursprünglichen Liste angezeigt. Sie müssen damit beginnen, den Namen in das Textfeld zu schreiben, damit er angezeigt wird.

   ![Abbildung der Auswahl von APIs](../../media/apis-in-my-org-tab.PNG)

5. Wählen Sie **Anwendungsberechtigungen aus.** Wählen Sie die relevanten Berechtigungen für Ihr Szenario aus (z. B. **Incident.Read.All),** und wählen Sie dann "Berechtigungen **hinzufügen" aus.**

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > Sie müssen die relevanten Berechtigungen für Ihr Szenario auswählen. *Das Lesen aller Vorfälle* ist nur ein Beispiel. Um zu bestimmen, welche Berechtigung Sie benötigen, sehen Sie sich den Abschnitt **"Berechtigungen"** in der API an, die Sie aufrufen möchten.
    >
    > Um beispielsweise [erweiterte](api-advanced-hunting.md)Abfragen ausführen zu können, wählen Sie die Berechtigung "Erweiterte Abfragen ausführen" aus. um [ein Gerät zu isolieren,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)wählen Sie die Berechtigung "Computer isolieren" aus.

6. Wählen Sie **Administratorzuserteilung aus.** Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie die Administratorzuserteilung **auswählen,** damit sie wirksam wird.

    ![Abbildung der Berechtigungserteilung](../../media/grant-consent.PNG)

7. Um der Anwendung einen geheimen Schlüssel hinzuzufügen, wählen Sie **"&** Zertifikate" aus, fügen Sie dem Geheimen eine Beschreibung hinzu, und wählen Sie dann **"Hinzufügen" aus.**

    > [!TIP]
    > Nachdem Sie **"Hinzufügen"** ausgewählt haben, wählen **Sie "Den generierten geheimen Wert kopieren" aus.** Sie können den geheimen Wert nach dem Verlassen nicht mehr abrufen.

    ![Abbildung des Erstellens eines App-Schlüssels](../../media/webapp-create-key2.png)

8. Noten Sie Ihre Anwendungs-ID und Ihre Mandanten-ID an einem sicheren Ort auf. Sie werden auf der **Anwendungsseite unter "Übersicht"** aufgeführt.

   ![Abbildung der erstellten App-ID](../../media/app-and-tenant-ids.png)

9. Fügen Sie die Anwendung dem Mandanten Ihres Benutzers hinzu.

   Da Ihre Anwendung im Namen Ihrer Benutzer mit Microsoft 365 Defender interagiert, muss sie für jeden Mandanten genehmigt werden, für den Sie ihn verwenden möchten.

   Ein **globaler Administrator** aus dem Mandanten Ihres Benutzers muss den Zustimmungslink anzeigen und Ihre Anwendung genehmigen.

   Der Zustimmungslink hat das format:

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   Die Ziffern `00000000-0000-0000-0000-000000000000` sollten durch Ihre Anwendungs-ID ersetzt werden.

   Nachdem Sie auf den Zustimmungslink geklickt haben, melden Sie sich beim globalen Administrator des Mandanten des Benutzers an, und stimmen Sie der Anwendung zu.

   ![Abbildung der Zustimmung](../../media/app-consent-partner.png)

   Sie müssen ihren Benutzer auch nach seiner Mandanten-ID fragen. Die Mandanten-ID ist einer der Bezeichner, die zum Erwerben von Zugriffstoken verwendet werden.

- **Fertig!** Sie haben eine Anwendung erfolgreich registriert!
- Beispiele für den Erwerb und die Überprüfung von Token finden Sie weiter unten.

## <a name="get-an-access-token"></a>Abrufen eines Zugriffstokens

Weitere Informationen zu Azure AD-Token finden Sie im [Azure AD-Lernprogramm.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

> [!IMPORTANT]
> Obwohl die Beispiele in diesem Abschnitt sie zum Einfügen geheimer Werte zu Testzwecken ermutigen, sollten Sie geheime Schlüssel niemals in eine Anwendung hartcodieren, die in der Produktion ausgeführt wird.  Ein Drittanbieter kann Ihr Geheimnis für den Zugriff auf Ressourcen verwenden. Mithilfe von Azure Key Vault können Sie die Geheimnisse Ihrer App [schützen.](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates) Ein praktisches Beispiel dafür, wie Sie Ihre App schützen können, finden Sie unter "Verwalten geheimer Schlüssel [in Ihren Server-Apps mit Azure Key Vault".](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)

> [!TIP]
> Verwenden Sie in den folgenden Beispielen die Mandanten-ID eines Benutzers, um zu testen, ob das Skript funktioniert.

### <a name="get-an-access-token-using-powershell"></a>Erhalten eines Zugriffstokens mithilfe von PowerShell

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

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

### <a name="get-an-access-token-using-c"></a>Erhalten eines Zugriffstokens mithilfe von C\#

> [!NOTE]
> Der folgende Code wurde mit Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 getestet.

1. Erstellen Sie eine neue Konsolenanwendung.
1. Installieren Sie NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Fügen Sie die folgende Zeile hinzu:

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Kopieren Sie den folgenden Code, und fügen Sie ihn in Ihre App ein (vergessen Sie nicht, die drei Variablen zu aktualisieren: `tenantId` `clientId` , , `appSecret` ):

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

### <a name="get-an-access-token-using-python"></a>Erhalten eines Zugriffstokens mithilfe von Python

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

### <a name="get-an-access-token-using-curl"></a>Erhalten eines Zugriffstokens mithilfe von "token"

> [!NOTE]
> Er ist unter Windows 10, Version 1803 und höher, vorinstalliert. Laden Sie für andere Versionen von Windows das Tool direkt von der offiziellen [Website des Betriebssystems herunter, und installieren Sie es.](https://curl.haxx.se/windows/)

1. Öffnen Sie eine Eingabeaufforderung, und legen CLIENT_ID Azure-Anwendungs-ID.
1. Legen CLIENT_SECRET auf Ihren geheimen Azure-Anwendungsgeheimnis.
1. Legen TENANT_ID auf die Azure-Mandanten-ID des Benutzers fest, der Ihre App für den Zugriff auf Microsoft 365 Defender verwenden möchte.
1. Führen Sie den folgenden Befehl aus:

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Eine erfolgreiche Antwort sieht wie dies aus:

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Überprüfen des Tokens

1. Kopieren Sie das Token, und fügen Sie es in die [JSON-Webtoken-Validator-Website, JWT, ein,](https://jwt.ms) um es zu decodieren.
1. Stellen Sie sicher, dass *der Rollenanspruch* innerhalb des decodierten Tokens die gewünschten Berechtigungen enthält.

In der folgenden Abbildung sehen Sie ein decodiertes Token, das von einer App mit ```Incidents.Read.All``` , und Berechtigungen erworben ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` wurde:

![Abbildung der Tokenüberprüfung](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API

1. Wählen Sie die API aus, die Sie verwenden möchten (Vorfälle oder erweiterte Suche). Weitere Informationen finden Sie unter [Unterstützte Microsoft 365 Defender-APIs.](api-supported.md)
2. Legen Sie in der http-Anforderung, die Sie senden möchten, den Autorisierungsheader auf `"Bearer" <token>` " *Bearer"* als Autorisierungsschema und das Token als ihr überprüftes  Token.
3. Das Token läuft innerhalb einer Stunde ab. Sie können während dieser Zeit mehr als eine Anforderung mit demselben Token senden.

Das folgende Beispiel zeigt, wie Sie eine Anforderung senden, um eine Liste der Vorfälle mit **C# zu erhalten.**

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
- [Erstellen einer App für den Zugriff auf Microsoft 365 Defender ohne Benutzer](api-create-app-web.md)
- [Erstellen einer App für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers](api-create-app-user-context.md)
- [Informationen zu API-Beschränkungen und Lizenzierung](api-terms.md)
- [Fehlercodes verstehen](api-error-codes.md)
- [Verwalten von geheimen Schlüsseln in Ihren Server-Apps mit Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2.0-Autorisierung für die Benutzerauthentifizierung und den Zugriff auf die API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
