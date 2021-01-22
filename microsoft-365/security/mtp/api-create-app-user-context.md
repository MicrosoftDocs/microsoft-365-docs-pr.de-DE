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
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Erstellen einer App für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Auf dieser Seite wird beschrieben, wie Sie eine Anwendung erstellen, um programmgesteuerten Zugriff auf Microsoft 365 Defender im Namen eines einzelnen Benutzers zu erhalten.

Wenn Sie programmgesteuerten Zugriff auf Microsoft 365 Defender ohne einen definierten Benutzer benötigen (z. B. wenn Sie eine Hintergrund-App oder einen Daemon schreiben), lesen Sie "Erstellen einer App für den Zugriff auf [Microsoft 365 Defender](api-create-app-web.md)ohne Benutzer". Wenn Sie Zugriff für mehrere Mandanten bereitstellen müssen , z. B. wenn Sie eine große Organisation oder eine Gruppe von Kunden bereitstellen, lesen Sie "Erstellen einer App mit Partnerzugriff auf [Microsoft 365 Defender-APIs".](api-partner-access.md) Wenn Sie nicht sicher sind, welche Art von Zugriff Sie benötigen, lesen Sie ["Erste Schritte".](api-access.md)

Microsoft 365 Defender macht einen Großen Teil seiner Daten und Aktionen über eine Reihe programmgesteuerter APIs verfügbar. Mit diesen APIs können Sie Workflows automatisieren und die Funktionen von Microsoft 365 Defender nutzen. Für diesen ZUGRIFF auf die API ist die OAuth2.0-Authentifizierung erforderlich. Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um diese APIs zu verwenden:

- Erstellen Sie eine Azure Active Directory (Azure AD)-Anwendung.
- Mit dieser Anwendung können Sie ein Zugriffstoken erhalten.
- Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zu zugreifen.

In diesem Artikel wird erläutert, wie Sie:

- Erstellen einer Azure AD-Anwendung
- Erhalten eines Zugriffstokens für Microsoft 365 Defender
- Überprüfen des Tokens

> [!NOTE]
> Wenn Sie im Namen eines Benutzers auf die Microsoft 365 Defender-API zugreifen, benötigen Sie die richtigen Anwendungsberechtigungen und Benutzerberechtigungen.

> [!TIP]
> Wenn Sie über die Berechtigung zum Ausführen einer Aktion im Portal verfügen, haben Sie die Berechtigung, die Aktion in der API durchzuführen.

## <a name="create-an-app"></a>App erstellen

1. Melden Sie sich [bei Azure](https://portal.azure.com) als Benutzer mit der rolle **"Globaler Administrator"** an.

2. Navigieren Sie zu **Azure Active**  >  **Directory-App-Registrierungen**  >  **Neue Registrierung.**

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. Wählen Sie im Formular einen Namen für Ihre Anwendung aus, geben Sie die folgenden Informationen für den Umleitungs-URI ein, und wählen Sie dann **"Registrieren" aus.**

   ![Abbildung des Fensters "Anwendung erstellen"](../../media/nativeapp-create2.PNG)

   - **Anwendungstyp:** Öffentlicher Client
   - **Umleitungs-URI:**https://portal.azure.com

4. Wählen Sie auf der Anwendungsseite DIE **API-Berechtigungen** hinzufügen Berechtigungs-APIs aus, die meine Organisation >, geben Sie Microsoft Threat Protection ein, und wählen Sie Microsoft  >    >   Threat **Protection aus.**  Ihre App kann jetzt auf Microsoft 365 Defender zugreifen.

   > [!TIP]
   > *Microsoft Threat Protection* ist ein früherer Name für Microsoft 365 Defender und wird nicht in der ursprünglichen Liste angezeigt. Sie müssen damit beginnen, den Namen in das Textfeld zu schreiben, damit er angezeigt wird.

   ![Abbildung der Auswahl von APIs](../../media/apis-in-my-org-tab.PNG)

   - Choose **Delegated permissions**. Wählen Sie die relevanten Berechtigungen für Ihr Szenario aus (z. B. **Incident.Read),** und wählen Sie dann "Berechtigungen **hinzufügen" aus.**

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > Sie müssen die relevanten Berechtigungen für Ihr Szenario auswählen. *Das Lesen aller Vorfälle* ist nur ein Beispiel. Um zu bestimmen, welche Berechtigung Sie benötigen, sehen Sie sich den Abschnitt **"Berechtigungen"** in der API an, die Sie aufrufen möchten.
    >
    > Um beispielsweise [erweiterte](api-advanced-hunting.md)Abfragen ausführen zu können, wählen Sie die Berechtigung "Erweiterte Abfragen ausführen" aus. um [ein Gerät zu isolieren,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)wählen Sie die Berechtigung "Computer isolieren" aus.

5. Wählen Sie **Administratorzuserteilung aus.** Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie die Administratorzuserteilung **auswählen,** damit sie wirksam wird.

   ![Abbildung der Berechtigungserteilung](../../media/grant-consent-delegated.PNG)

6. Noten Sie Ihre Anwendungs-ID und Ihre Mandanten-ID an einem sicheren Ort auf. Sie werden auf der **Anwendungsseite unter "Übersicht"** aufgeführt.

   ![Abbildung der erstellten App-ID](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>Abrufen eines Zugriffstokens

Weitere Informationen zu Azure Active Directory-Token finden Sie im [Azure AD-Lernprogramm.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="get-an-access-token-using-powershell"></a>Erhalten eines Zugriffstokens mithilfe von PowerShell

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

## <a name="validate-the-token"></a>Überprüfen des Tokens

1. Kopieren Sie das Token, und fügen Sie es in [JWT ein,](https://jwt.ms) um es zu decodieren.
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
- [Erstellen einer "Hello world"-App](api-hello-world.md)
- [Erstellen einer App für den Zugriff auf Microsoft 365 Defender ohne Benutzer](api-create-app-web.md)
- [Erstellen einer App mit Mehr-Mandanten-Partnerzugriff auf Microsoft 365 -Defender-APIs](api-partner-access.md)
- [Informationen zu API-Beschränkungen und Lizenzierung](api-terms.md)
- [Fehlercodes verstehen](api-error-codes.md)
- [OAuth 2.0-Autorisierung für die Benutzerauthentifizierung und den Zugriff auf die API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
