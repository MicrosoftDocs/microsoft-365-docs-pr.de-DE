---
title: Hello World für Microsoft 365 Defender-Rest-API
description: Informationen zum Erstellen einer APP und Verwenden eines Tokens für den Zugriff auf die Microsoft 365 Defender-APIs
keywords: APP, Token, Access, AAD, APP, Anwendungsregistrierung, PowerShell, Skript, globaler Administrator, Berechtigung, Microsoft 365 Defender
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
ms.openlocfilehash: b36a6acca5880a455a66b03b5355cdf1fb85b29b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719310"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hello World für Microsoft 365 Defender-Rest-API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

## <a name="get-incidents-using-a-simple-powershell-script"></a>Abrufen von Vorfällen mithilfe eines einfachen PowerShell-Skripts

Es sollte 5 bis 10 Minuten dauern, bis Sie dieses Projekt abgeschlossen haben. Diese Zeitschätzung umfasst das Registrieren der Anwendung und das Anwenden des Codes aus dem PowerShell-Beispielskript.

### <a name="register-an-app-in-azure-active-directory"></a>Registrieren einer APP in Azure Active Directory

1. Melden Sie sich als Benutzer mit **globaler Administrator** Rolle bei [Azure](https://portal.azure.com) an.

2. Navigieren Sie zu **Azure Active Directory**  >  **App Registrations**  >  **New Registration**.

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. Wählen Sie im Registrierungsformular einen Namen für Ihre Anwendung aus, und wählen Sie dann **registrieren** aus. Das Auswählen eines Umleitungs-URI ist optional. Sie benötigen keins, um dieses Beispiel abzuschließen.

4. Wählen Sie auf Ihrer Anwendungsseite **API-Berechtigungen**  >  **Add permission**  >  **APIs meine Organisation verwendet** >, geben Sie **Microsoft Threat Protection** ein, und wählen Sie **Microsoft Threat Protection** aus. Ihre APP kann nun auf Microsoft 365 Defender zugreifen.

   > [!TIP]
   > *Microsoft Threat Protection* ist ein ehemaliger Name für Microsoft 365 Defender und wird nicht in der ursprünglichen Liste angezeigt. Sie müssen mit dem Schreiben des Namens in das Textfeld beginnen, damit dieser angezeigt wird.
   ![Abbildung der API-Berechtigungs Auswahl](../../media/apis-in-my-org-tab.PNG)

   - Wählen Sie **Anwendungsberechtigungen**  >  **Vorfall. Read. all** und dann **Berechtigungen hinzufügen** aus.

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions.PNG)

5. Wählen Sie **Administrator Zustimmung erteilen** aus. Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie die Option **Administrator Zustimmung erteilen** auswählen, damit Sie wirksam wird.

    ![Image von Grant-Berechtigungen](../../media/grant-consent.PNG)

6. Fügen Sie der Anwendung ein Kennwort hinzu. Wählen Sie **Zertifikate & Geheimnisse** aus, fügen Sie eine Beschreibung zum geheimen Schlüssel hinzu, und wählen Sie dann **Hinzufügen** aus.

    > [!TIP]
    > Nachdem Sie **Hinzufügen** ausgewählt haben, wählen Sie **den generierten geheimen Wert kopieren** aus. Sie können den geheimen Wert nach dem verlassen nicht mehr abrufen.

    ![Bild der APP-Schlüssel erstellen](../../media/webapp-create-key2.png)

7. Notieren Sie Ihre Anwendungs-ID und ihre Mandanten-ID an einem sicheren Ort. Sie werden unter **Übersicht** auf Ihrer Anwendungsseite aufgeführt.

   ![Bild der erstellten APP-ID](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>Abrufen eines Tokens mithilfe der APP und Verwenden des Tokens für den Zugriff auf die API

Weitere Informationen zu Azure Active Directory Token finden Sie im [Azure AD-Lernprogramm](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Das Beispiel in dieser Demo-App ermutigt Sie zwar, den geheimen Wert zu Testzwecken einzufügen, aber Sie sollten **Secrets niemals** in einer Anwendung hartcodieren, die in Production läuft. Ein Drittanbieter kann ihren geheimen Schlüssel für den Zugriff auf Ressourcen verwenden. Mithilfe von [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)können Sie die Sicherheit Ihrer APP-Geheimnisse schützen. Ein praktisches Beispiel dafür, wie Sie Ihre APP schützen können, finden Sie unter [Manage Secrets in Your Server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).

1. Kopieren Sie das Skript unten, und fügen Sie es in Ihren bevorzugten Text-Editor ein. Speichern unter **Get-Token.ps1**. Sie können den Code auch wie in PowerShell ISE ausführen, aber Sie sollten ihn speichern, da wir ihn erneut ausführen müssen, wenn wir das Ereignis-Fetching-Skript im nächsten Abschnitt verwenden.

    Dieses Skript generiert ein Token und speichert es im Arbeitsordner unter dem Namen *Latest-token.txt*.

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

#### <a name="validate-the-token"></a>Überprüfen des Tokens

1. Kopieren Sie das empfangene Token in [JWT](https://jwt.ms) , und fügen Sie es ein, um es zu decodieren.
1. *JWT* steht für *JSON-webtoken*. Das decodierte Token enthält eine Reihe von JSON-formatierten Elementen oder Ansprüchen. Stellen Sie sicher, dass die *Rollen* Forderung innerhalb des decodierten Tokens die gewünschten Berechtigungen enthält.

    In der folgenden Abbildung sehen Sie ein decodiertes Token, das aus einer APP, mit ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` und Berechtigungen erworben wurde ```AdvancedHunting.Read.All``` :

    ![Bild JWT.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>Abrufen einer Liste der letzten Vorfälle

Im folgenden Skript wird **Get-Token.ps1** verwendet, um auf die API zuzugreifen. Anschließend wird eine Liste der Vorfälle abgerufen, die zuletzt in den letzten 48 Stunden aktualisiert wurden, und die Liste wird als JSON-Datei gespeichert.

> [!IMPORTANT]
> Speichern Sie dieses Skript im gleichen Ordner, den Sie **Get-Token.ps1** gespeichert haben.

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

Sie sind fertig! Sie haben erfolgreich:

- Erstellt und registriert eine Anwendung.
- Gewährte Berechtigung für diese Anwendung zum Lesen von Warnungen.
- Mit der API verbunden.
- Ein PowerShell-Skript zum Zurückgeben von Vorfällen verwendet, die in den letzten 48 Stunden aktualisiert wurden.

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft 365 Defender-APIs (Übersicht)](api-overview.md)
- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
- [Erstellen einer APP für den Zugriff auf Microsoft 365 Defender ohne Benutzer](api-create-app-web.md)
- [Erstellen einer APP für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers](api-create-app-user-context.md)
- [Erstellen einer APP mit mehr Mandanten fähigem Partner Zugriff auf Microsoft 365 Defender-APIs](api-partner-access.md)
- [Verwalten von geheimen Schlüsseln in Ihren Server-apps mit Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2,0 Autorisierung für Benutzeranmeldung und API-Zugriff](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
