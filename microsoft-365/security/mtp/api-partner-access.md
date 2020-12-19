---
title: Partner Zugriff über Microsoft 365 Defender-APIs
description: Erfahren Sie, wie Sie eine APP erstellen, um den programmgesteuerten Zugriff auf Microsoft 365 Defender im Namen Ihrer Benutzer zu erhalten.
keywords: Partner, Zugriff, API, mehr Mandanten, Zustimmung, Zugriffstoken, App
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
ms.openlocfilehash: 5de113c8f8419b3af2a287bd7ba7e41dc06b4121
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719440"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a>Erstellen einer APP mit Partner Zugriff auf Microsoft 365 Defender-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Auf dieser Seite wird beschrieben, wie Sie eine Azure Active Directory-app erstellen, die den programmgesteuerten Zugriff auf Microsoft 365 Defender im Namen von Benutzern in mehreren Mandanten bietet. Multi-Mandanten-apps sind nützlich, um große Gruppen von Benutzern zu bedienen.

Wenn Sie im Namen eines einzelnen Benutzers programmgesteuerten Zugriff auf Microsoft 365 Defender benötigen, finden Sie weitere Informationen unter [Erstellen einer APP für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers](api-create-app-user-context.md). Wenn Sie Zugriff benötigen, ohne dass ein Benutzer explizit definiert ist (beispielsweise wenn Sie eine Hintergrund-APP oder einen-Daemon schreiben), finden Sie weitere Informationen unter [Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer](api-create-app-web.md). Wenn Sie nicht sicher sind, welche Art von Zugriff Sie benötigen, finden Sie weitere Informationen unter [Erste Schritte](api-access.md).

Microsoft 365 Defender macht einen Großteil seiner Daten und Aktionen über eine Reihe von programmgesteuerten APIs verfügbar. Diese APIs unterstützen Sie beim Automatisieren von Workflows und bei der Verwendung der Funktionen von Microsoft 365 Defender. Für diesen API-Zugriff ist die OAuth 2.0-Authentifizierung erforderlich. Weitere Informationen finden Sie unter [OAuth 2,0-Autorisierungs Code Fluss](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um diese APIs zu verwenden:

- Erstellen Sie eine Azure Active Directory (Azure AD)-Anwendung.
- Abrufen eines Zugriffstokens mithilfe dieser Anwendung.
- Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zuzugreifen.

Da es sich bei dieser APP um mehrere Mandanten handelt, benötigen Sie auch die [Zustimmung des Administrators](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) von jedem Mandanten im Namen seiner Benutzer.

In diesem Artikel wird erklärt, wie Sie:

- Erstellen einer Azure AD Anwendung mit **mehreren Mandanten**
- Erhalten Sie eine autorisierte Zustimmung ihres Benutzeradministrators für Ihre Anwendung, um auf den Microsoft 365 Defender zuzugreifen, der Ressourcen benötigt.
- Abrufen eines Zugriffstokens für Microsoft 365 Defender
- Überprüfen des Tokens

Microsoft 365 Defender macht einen Großteil seiner Daten und Aktionen über eine Reihe von programmgesteuerten APIs verfügbar. Diese APIs unterstützen Sie bei der Automatisierung von Arbeitsabläufen und Innovationen basierend auf den Microsoft 365 Defender-Funktionen. Für den API-Zugriff ist die OAuth 2.0-Authentifizierung erforderlich. Weitere Informationen finden Sie unter [OAuth 2,0-Autorisierungs Code Fluss](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:

- Erstellen Sie eine **mehrmandantenfähige** Azure AD Anwendung.
- Lassen Sie sich von Ihrem Benutzer Administrator genehmigen (Zustimmung), damit Ihre Anwendung auf von Microsoft 365 Defender benötigte Ressourcen zugreifen kann.
- Abrufen eines Zugriffstokens mithilfe dieser Anwendung.
- Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zuzugreifen.

In den folgenden Schritten finden Sie Anleitungen zum Erstellen einer Azure AD Anwendung mit mehreren Mandanten, zum Abrufen eines Zugriffstokens für Microsoft 365 Defender und zum Überprüfen des Tokens.

## <a name="create-the-multi-tenant-app"></a>Erstellen der Multi-Mandanten-App

1. Melden Sie sich als Benutzer mit **globaler Administrator** Rolle bei [Azure](https://portal.azure.com) an.

2. Navigieren Sie zu **Azure Active Directory**  >  **App Registrations**  >  **New Registration**.

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. Im Registrierungsformular:

   - Wählen Sie einen Namen für Ihre Anwendung aus.
   - Wählen Sie **unter Unterstützte Kontotypen** **Konten in einem beliebigen Organisations Verzeichnis (beliebiges Azure AD Verzeichnis) aus – Multitenant**.
   - Füllen Sie den Abschnitt **Umleitungs-URI** aus. Wählen Sie Type Internet aus, und geben Sie den Umleitungs **-** URI als an **https://portal.azure.com** .

   Nachdem Sie das Formular ausgefüllt haben, wählen Sie **registrieren** aus.

   ![Bild des Registrierungsformulars für ein Antragsformular](../..//media/atp-api-new-app-partner.png)

4. Wählen Sie auf Ihrer Anwendungsseite **API-Berechtigungen**  >  **Add permission**  >  **APIs meine Organisation verwendet** >, geben Sie **Microsoft Threat Protection** ein, und wählen Sie **Microsoft Threat Protection** aus. Ihre APP kann nun auf Microsoft 365 Defender zugreifen.

   > [!TIP]
   > *Microsoft Threat Protection* ist ein ehemaliger Name für Microsoft 365 Defender und wird nicht in der ursprünglichen Liste angezeigt. Sie müssen mit dem Schreiben des Namens in das Textfeld beginnen, damit dieser angezeigt wird.

   ![Abbildung der API-Berechtigungs Auswahl](../../media/apis-in-my-org-tab.PNG)

5. Wählen Sie **Anwendungsberechtigungen** aus. Wählen Sie die relevanten Berechtigungen für Ihr Szenario (beispielsweise **Incident. Read. all**) aus, und wählen Sie dann **Berechtigungen hinzufügen** aus.

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > Sie müssen die relevanten Berechtigungen für Ihr Szenario auswählen. *Lesen Sie alle Vorfälle* ist nur ein Beispiel. Um zu ermitteln, welche Berechtigungen Sie benötigen, sehen Sie sich den Abschnitt **Berechtigungen** in der API an, die Sie aufrufen möchten.
    >
    > Um beispielsweise [erweiterte Abfragen auszuführen](api-advanced-hunting.md), wählen Sie die Berechtigung ' erweiterte Abfragen ausführen ' aus; um [ein Gerät zu isolieren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), wählen Sie die Berechtigung "Computer isolieren" aus.

6. Wählen Sie **Administrator Zustimmung erteilen** aus. Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie die Option **Administrator Zustimmung erteilen** auswählen, damit Sie wirksam wird.

    ![Image von Grant-Berechtigungen](../../media/grant-consent.PNG)

7. Um der Anwendung ein Geheimnis hinzuzufügen, wählen Sie **Zertifikate & Secrets** aus, fügen Sie eine Beschreibung zum geheimen Schlüssel hinzu, und wählen Sie dann **Hinzufügen** aus.

    > [!TIP]
    > Nachdem Sie **Hinzufügen** ausgewählt haben, wählen Sie **den generierten geheimen Wert kopieren** aus. Sie können den geheimen Wert nach dem verlassen nicht mehr abrufen.

    ![Bild der APP-Schlüssel erstellen](../../media/webapp-create-key2.png)

8. Notieren Sie Ihre Anwendungs-ID und ihre Mandanten-ID an einem sicheren Ort. Sie werden unter **Übersicht** auf Ihrer Anwendungsseite aufgeführt.

   ![Bild der erstellten APP-ID](../../media/app-and-tenant-ids.png)

9. Fügen Sie die Anwendung dem Mandanten des Benutzers hinzu.

   Da Ihre Anwendung im Namen Ihrer Benutzer mit Microsoft 365 Defender interagiert, muss Sie für jeden Mandanten genehmigt werden, für den Sie Sie verwenden möchten.

   Ein **globaler Administrator** des Mandanten Ihres Benutzers muss den Zustimmungs Link anzeigen und Ihre Anwendung genehmigen.

   Der Zustimmungs Link hat folgendes Format:

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   Die Ziffern `00000000-0000-0000-0000-000000000000` sollten durch Ihre Anwendungs-ID ersetzt werden.

   Melden Sie sich nach dem Klicken auf den Link Zustimmung mit dem globalen Administrator des Mandanten des Benutzers an, und stimmen Sie der Anwendung zu.

   ![Bild der Zustimmung](../../media/app-consent-partner.png)

   Außerdem müssen Sie Ihren Benutzer um die Mandanten-ID bitten. Die Mandanten-ID ist einer der Bezeichner, die zum Abrufen von Zugriffstoken verwendet werden.

- **Fertig!** Sie haben eine Anwendung erfolgreich registriert!
- In den folgenden Beispielen finden Sie Informationen zur Token-Erfassung und-Validierung.

## <a name="get-an-access-token"></a>Abrufen eines Zugriffstokens

Weitere Informationen zu Azure AD Token finden Sie im [Azure AD-Lernprogramm](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Obwohl die Beispiele in diesem Abschnitt Sie dazu ermutigen, in geheimen Werten zu Testzwecken einzufügen, sollten Sie **keine Geheimnisse** in einer Anwendung, die in der Produktion läuft, hartcodieren. Ein Drittanbieter kann ihren geheimen Schlüssel für den Zugriff auf Ressourcen verwenden. Mithilfe von [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)können Sie die Sicherheit Ihrer APP-Geheimnisse schützen. Ein praktisches Beispiel dafür, wie Sie Ihre APP schützen können, finden Sie unter [Manage Secrets in Your Server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).

> [!TIP]
> Verwenden Sie in den folgenden Beispielen die Mandanten-ID eines Benutzers, um zu testen, ob das Skript funktionsfähig ist.

### <a name="get-an-access-token-using-powershell"></a>Abrufen eines Zugriffstokens mithilfe von PowerShell

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

### <a name="get-an-access-token-using-c"></a>Abrufen eines Zugriffstokens mithilfe von C\#

> [!NOTE]
> Der folgende Code wurde mit Nuget Microsoft. IdentityModel. Clients. ActiveDirectory 3.19.8 getestet.

1. Erstellen Sie eine neue Konsolenanwendung.
1. Installieren Sie NuGet [Microsoft. IdentityModel. Clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Fügen Sie die folgende Reihe hinzu:

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Kopieren Sie den folgenden Code, und fügen Sie ihn in Ihre APP ein (vergessen Sie nicht, die drei Variablen zu aktualisieren: `tenantId` , `clientId` , `appSecret` ):

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

### <a name="get-an-access-token-using-python"></a>Abrufen eines Zugriffstokens mithilfe von python

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

### <a name="get-an-access-token-using-curl"></a>Abrufen eines Zugriffstokens mithilfe von curl

> [!NOTE]
> Curl ist auf Windows 10, Version 1803 und höher, vorinstalliert. Laden Sie für andere Versionen von Windows das Tool direkt von der [offiziellen curl-Website](https://curl.haxx.se/windows/)herunter, und installieren Sie es.

1. Öffnen Sie eine Eingabeaufforderung, und legen Sie CLIENT_ID auf Ihre Azure-Anwendungs-ID fest.
1. Legen Sie CLIENT_SECRET auf Ihren Azure-Anwendungsschlüssel fest.
1. Legen Sie TENANT_ID auf die Azure-Mandanten-ID des Benutzers fest, der Ihre APP für den Zugriff auf Microsoft 365 Defender verwenden möchte.
1. Führen Sie den folgenden Befehl aus:

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Eine erfolgreiche Antwort wird wie folgt aussehen:

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Überprüfen des Tokens

1. Kopieren Sie das Token, und fügen Sie es in die [JSON Web Token Validator-Website, JWT,](https://jwt.ms) ein, um es zu decodieren.
1. Stellen Sie sicher, dass die *Rollen* Forderung innerhalb des decodierten Tokens die gewünschten Berechtigungen enthält.

In der folgenden Abbildung sehen Sie ein decodiertes Token, das aus einer APP, mit ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` und Berechtigungen erworben wurde ```AdvancedHunting.Read.All``` :

![Bild der Token-Validierung](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Verwenden des Tokens für den Zugriff auf die Microsoft 365 Defender-API

1. Wählen Sie die API aus, die Sie verwenden möchten (Incidents oder Advanced Hunting). Weitere Informationen finden Sie unter [Supported Microsoft 365 Defender APIs](api-supported.md).
2. Legen Sie in der HTTP-Anforderung, die Sie senden möchten, den Autorisierungs Kopf auf `"Bearer" <token>` , *Bearer* ist das Autorisierungsschema, und *Token* ist Ihr validiertes Token.
3. Das Token wird innerhalb einer Stunde ablaufen. Sie können während dieser Zeit mehr als eine Anforderung mit demselben Token senden.

Das folgende Beispiel zeigt, wie Sie eine Anforderung zum Abrufen einer Liste von Vorfällen **mithilfe von C#** senden.

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft 365 Defender-APIs (Übersicht)](api-overview.md)
- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
- [Erstellen einer "Hello World"-Anwendung](api-hello-world.md)
- [Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer](api-create-app-web.md)
- [Erstellen einer APP für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers](api-create-app-user-context.md)
- [Informationen zu API-Grenzwerten und Lizenzierung](api-terms.md)
- [Grundlegendes zu Fehlercodes](api-error-codes.md)
- [Verwalten von geheimen Schlüsseln in Ihren Server-apps mit Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2,0 Autorisierung für Benutzeranmeldung und API-Zugriff](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
