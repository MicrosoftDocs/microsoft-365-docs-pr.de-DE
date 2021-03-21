---
title: Hello World für Microsoft 365 Defender REST API
description: Informationen zum Erstellen einer App und Verwenden eines Tokens für den Zugriff auf die Microsoft 365 Defender-APIs
keywords: app, token, access, aad, app, application registration, powershell, script, global administrator, permission, microsoft 365 defender
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
ms.openlocfilehash: 65319d46871282c454287af225647f89e3535c78
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924338"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hello World für Microsoft 365 Defender REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

## <a name="get-incidents-using-a-simple-powershell-script"></a>Erhalten von Vorfällen mithilfe eines einfachen PowerShell-Skripts

Es sollte 5 bis 10 Minuten dauern, bis dieses Projekt abgeschlossen ist. Diese Zeitschätzung umfasst das Registrieren der Anwendung und das Anwenden des Codes aus dem PowerShell-Beispielskript.

### <a name="register-an-app-in-azure-active-directory"></a>Registrieren einer App in Azure Active Directory

1. Melden Sie sich [bei Azure](https://portal.azure.com) als Benutzer mit der Rolle **"Globaler Administrator"** an.

2. Navigieren Sie zu **Azure Active Directory**  >  **App-Registrierungen** Neue  >  **Registrierung**.

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. Wählen Sie im Registrierungsformular einen Namen für Ihre Anwendung aus, und wählen Sie dann **Registrieren aus.** Das Auswählen eines Umleitungs-URI ist optional. Sie benötigen keinen, um dieses Beispiel zu vervollständigen.

4. Wählen Sie auf der Anwendungsseite **API-Berechtigungen** Hinzufügen von Berechtigungs-APIs aus, die meine > verwendet, geben Sie  >    >   Microsoft **Threat Protection** ein, und wählen Sie **Microsoft Threat Protection aus.** Ihre App kann jetzt auf Microsoft 365 Defender zugreifen.

   > [!TIP]
   > *Microsoft Threat Protection* ist ein früherer Name für Microsoft 365 Defender und wird nicht in der ursprünglichen Liste angezeigt. Sie müssen damit beginnen, den Namen in das Textfeld zu schreiben, damit er angezeigt wird.
   ![Abbildung der API-Berechtigungsauswahl](../../media/apis-in-my-org-tab.PNG)

   - Wählen **Sie Anwendungsberechtigungen**  >  **Incident.Read.All aus,** und wählen Sie Berechtigungen hinzufügen **aus.**

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions.PNG)

5. Wählen Sie **Administratorzuwilligung erteilen aus.** Jedes Mal, wenn Sie eine  Berechtigung hinzufügen, müssen Sie Administratorzuwilligung erteilen auswählen, damit sie wirksam wird.

    ![Abbildung der Berechtigungserteilung](../../media/grant-consent.PNG)

6. Fügen Sie der Anwendung einen geheimen Schlüssel hinzu. Wählen **Sie Zertifikate & Schlüssel** aus, fügen Sie dem Geheimen eine Beschreibung hinzu, und wählen Sie dann Hinzufügen **aus.**

    > [!TIP]
    > Nachdem Sie Hinzufügen **ausgewählt haben,** wählen **Sie den generierten geheimen Wert kopieren aus.** Sie können den geheimen Wert nach dem Verlassen nicht mehr abrufen.

    ![Abbildung des App-Schlüssels erstellen](../../media/webapp-create-key2.png)

7. Noten Sie Ihre Anwendungs-ID und Ihre Mandanten-ID an einem sicheren Ort auf. Sie werden unter **Übersicht auf** Ihrer Anwendungsseite aufgelistet.

   ![Abbildung der erstellten App-ID](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>Abrufen eines Tokens mithilfe der App und Verwenden des Tokens für den Zugriff auf die API

Weitere Informationen zu Azure Active Directory-Token finden Sie im [Azure AD-Lernprogramm](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Das Beispiel in dieser Demo-App ermutigt Sie zwar, ihren  geheimen Wert zu Testzwecken einzugeben, aber Sie sollten geheime Schlüssel niemals in eine Anwendung hartcodieren, die in der Produktion ausgeführt wird. Ein Drittanbieter kann Ihr Geheimnis für den Zugriff auf Ressourcen verwenden. Mithilfe von Azure Key Vault können Sie die Geheimen Ihrer App [schützen.](/azure/key-vault/general/about-keys-secrets-certificates) Ein praktisches Beispiel, wie Sie Ihre App schützen können, finden Sie unter [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).

1. Kopieren Sie das skript unten, und fügen Sie es in Ihren bevorzugten Texteditor ein. Speichern unter **Get-Token.ps1**. Sie können den Code auch wie in PowerShell ISE ausführen, aber Sie sollten ihn speichern, da wir ihn erneut ausführen müssen, wenn wir das Skript zum Abrufen von Vorfällen im nächsten Abschnitt verwenden.

    Dieses Skript generiert ein Token und speichern es im Arbeitsordner unter dem Namen *Latest-token.txt*.

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

1. Kopieren Sie das token, das Sie erhalten haben, und fügen Sie es in [JWT](https://jwt.ms) ein, um es zu decodieren.
1. *JWT* steht für *JSON Web Token*. Das decodierte Token enthält eine Reihe von JSON-formatierten Elementen oder Ansprüchen. Stellen Sie sicher, dass *der Rollenanspruch* innerhalb des decodierten Tokens die gewünschten Berechtigungen enthält.

    In der folgenden Abbildung sehen Sie ein decodiertes Token, das von einer App erworben wurde, mit ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` und ```AdvancedHunting.Read.All``` Berechtigungen:

    ![Bild jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>Eine Liste der letzten Vorfälle erhalten

Das folgende Skript verwendet **Get-Token.ps1** für den Zugriff auf die API. Anschließend wird eine Liste der Vorfälle abgerufen, die zuletzt innerhalb der letzten 48 Stunden aktualisiert wurden, und speichert die Liste als JSON-Datei.

> [!IMPORTANT]
> Speichern Sie dieses Skript in dem Ordner, den Sie **Get-Token.ps1.**

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

Sie sind alle fertig! Sie haben erfolgreich:

- Eine Anwendung wurde erstellt und registriert.
- Erteilte Berechtigung für diese Anwendung zum Lesen von Warnungen.
- Mit der API verbunden.
- Verwendet ein PowerShell-Skript, um Vorfälle zurückzukehren, die in den letzten 48 Stunden aktualisiert wurden.

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über Microsoft 365 Defender-APIs](api-overview.md)
- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
- [Erstellen einer App für den Zugriff auf Microsoft 365 Defender ohne Benutzer](api-create-app-web.md)
- [Erstellen einer App für den Zugriff auf Microsoft 365 Defender-APIs im Auftrag eines Benutzers](api-create-app-user-context.md)
- [Erstellen einer App mit Mehr-Mandanten-Partnerzugriff auf Microsoft 365 Defender-APIs](api-partner-access.md)
- [Verwalten von Geheimschlüsseln in Ihren Server-Apps mit Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2.0 Autorisierung für die Benutzer anmeldung und den API-Zugriff](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)