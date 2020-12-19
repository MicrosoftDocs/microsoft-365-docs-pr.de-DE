---
title: Erstellen einer APP für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers
description: Erfahren Sie, wie Sie im Namen eines Benutzers auf Microsoft 365 Defender-APIs zugreifen.
keywords: Zugriff im Namen des Benutzers, der API, der Anwendung, des Benutzers, des Zugriffstokens, des Tokens,
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
ms.openlocfilehash: f1c0caea9ff7810f79026c789241a4f250ec5303
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719416"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Erstellen einer APP für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Auf dieser Seite wird beschrieben, wie Sie eine Anwendung erstellen, um den programmgesteuerten Zugriff auf Microsoft 365 Defender im Auftrag eines einzelnen Benutzers zu erhalten.

Wenn Sie den programmgesteuerten Zugriff auf Microsoft 365 Defender ohne definierten Benutzer benötigen (beispielsweise wenn Sie eine Hintergrund-APP oder einen-Daemon schreiben), finden Sie weitere Informationen unter [Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer](api-create-app-web.md). Wenn Sie Zugriff für mehrere Mandanten bereitstellen müssen, beispielsweise wenn Sie eine große Organisation oder eine Gruppe von Kunden bedienen, finden Sie weitere Informationen unter [Erstellen einer APP mit Partner Zugriff auf Microsoft 365 Defender-APIs](api-partner-access.md). Wenn Sie nicht sicher sind, welche Art von Zugriff Sie benötigen, finden Sie weitere Informationen unter [Erste Schritte](api-access.md).

Microsoft 365 Defender macht einen Großteil seiner Daten und Aktionen über eine Reihe von programmgesteuerten APIs verfügbar. Diese APIs unterstützen Sie beim Automatisieren von Workflows und bei der Verwendung der Funktionen von Microsoft 365 Defender. Für diesen API-Zugriff ist die OAuth 2.0-Authentifizierung erforderlich. Weitere Informationen finden Sie unter [OAuth 2,0-Autorisierungs Code Fluss](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um diese APIs zu verwenden:

- Erstellen Sie eine Azure Active Directory (Azure AD)-Anwendung.
- Abrufen eines Zugriffstokens mithilfe dieser Anwendung.
- Verwenden Sie das Token, um auf die Microsoft 365 Defender-API zuzugreifen.

In diesem Artikel wird erklärt, wie Sie:

- Erstellen einer Azure AD-Anwendung
- Abrufen eines Zugriffstokens für Microsoft 365 Defender
- Überprüfen des Tokens

> [!NOTE]
> Wenn Sie im Namen eines Benutzers auf die Microsoft 365 Defender-API zugreifen, benötigen Sie die richtigen Anwendungsberechtigungen und Benutzerberechtigungen.

> [!TIP]
> Wenn Sie über die Berechtigung zum Ausführen einer Aktion im Portal verfügen, haben Sie die Berechtigung, die Aktion in der API auszuführen.

## <a name="create-an-app"></a>App erstellen

1. Melden Sie sich als Benutzer mit **globaler Administrator** Rolle bei [Azure](https://portal.azure.com) an.

2. Navigieren Sie zu **Azure Active Directory**  >  **App Registrations**  >  **New Registration**.

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. Wählen Sie im Formular einen Namen für Ihre Anwendung aus, und geben Sie die folgenden Informationen für den Umleitungs-URI ein, und wählen Sie dann **registrieren** aus.

   ![Bild des Fensters "Anwendungs erstellen"](../../media/nativeapp-create2.PNG)

   - **Anwendungstyp:** Öffentlicher Client
   - **Umleitungs-URI:**https://portal.azure.com

4. Wählen Sie auf Ihrer Anwendungsseite **API-Berechtigungen**  >  **Add permission**  >  **APIs meine Organisation verwendet** >, geben Sie **Microsoft Threat Protection** ein, und wählen Sie **Microsoft Threat Protection** aus. Ihre APP kann nun auf Microsoft 365 Defender zugreifen.

   > [!TIP]
   > *Microsoft Threat Protection* ist ein ehemaliger Name für Microsoft 365 Defender und wird nicht in der ursprünglichen Liste angezeigt. Sie müssen mit dem Schreiben des Namens in das Textfeld beginnen, damit dieser angezeigt wird.

   ![Abbildung der API-Berechtigungs Auswahl](../../media/apis-in-my-org-tab.PNG)

   - Wählen Sie **Delegierte Berechtigungen** aus. Wählen Sie die relevanten Berechtigungen für Ihr Szenario (beispielsweise **Incident. Read**) aus, und wählen Sie dann **Berechtigungen hinzufügen** aus.

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > Sie müssen die relevanten Berechtigungen für Ihr Szenario auswählen. *Lesen Sie alle Vorfälle* ist nur ein Beispiel. Um zu ermitteln, welche Berechtigungen Sie benötigen, sehen Sie sich den Abschnitt **Berechtigungen** in der API an, die Sie aufrufen möchten.
    >
    > Um beispielsweise [erweiterte Abfragen auszuführen](api-advanced-hunting.md), wählen Sie die Berechtigung ' erweiterte Abfragen ausführen ' aus; um [ein Gerät zu isolieren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), wählen Sie die Berechtigung "Computer isolieren" aus.

5. Wählen Sie **Administrator Zustimmung erteilen** aus. Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie die Option **Administrator Zustimmung erteilen** auswählen, damit Sie wirksam wird.

   ![Image von Grant-Berechtigungen](../../media/grant-consent-delegated.PNG)

6. Notieren Sie Ihre Anwendungs-ID und ihre Mandanten-ID an einem sicheren Ort. Sie werden unter **Übersicht** auf Ihrer Anwendungsseite aufgeführt.

   ![Bild der erstellten APP-ID](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>Abrufen eines Zugriffstokens

Weitere Informationen zu Azure Active Directory Token finden Sie im [Azure AD-Lernprogramm](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

### <a name="get-an-access-token-using-powershell"></a>Abrufen eines Zugriffstokens mithilfe von PowerShell

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

1. Kopieren Sie das Token, und fügen Sie es in [JWT](https://jwt.ms) ein, um es zu decodieren.
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
- [Erstellen einer "Hello World"-App](api-hello-world.md)
- [Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer](api-create-app-web.md)
- [Erstellen einer APP mit mehr Mandanten fähigem Partner Zugriff auf Microsoft 365 Defender-APIs](api-partner-access.md)
- [Informationen zu API-Grenzwerten und Lizenzierung](api-terms.md)
- [Grundlegendes zu Fehlercodes](api-error-codes.md)
- [OAuth 2,0 Autorisierung für Benutzeranmeldung und API-Zugriff](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
