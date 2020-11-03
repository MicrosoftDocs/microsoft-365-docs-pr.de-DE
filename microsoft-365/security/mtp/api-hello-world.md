---
title: Hello World für Microsoft 365 Defender-Rest-API
description: Informationen zum Erstellen einer APP und Verwenden eines Tokens für den Zugriff auf die Microsoft 365 Defender-APIs
keywords: APP, Token, Access, AAD, APP, Anwendungsregistrierung, PowerShell, Skript, globaler Administrator, Berechtigung
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
ms.openlocfilehash: bd4f7e5485d67cf74477900ae2cc5c77f1a6ee41
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844044"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hello World für Microsoft 365 Defender-Rest-API 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.


## <a name="get-incidents-using-a-simple-powershell-script"></a>Abrufen von Vorfällen mithilfe eines einfachen PowerShell-Skripts

### <a name="how-long-it-takes-to-go-through-this-example"></a>Wie lange dauert das durchlaufen dieses Beispiels?
Es dauert nur 5 Minuten in zwei Schritten:
- Anwendungsregistrierung
- Verwendungsbeispiele: benötigt nur Kopie/Paste eines kurzen PowerShell-Skripts

### <a name="do-i-need-a-permission-to-connect"></a>Benötige ich eine Berechtigung für eine Verbindung?
Für die Anwendungs Registrierungsphase benötigen Sie eine **globale Administrator** Rolle in Ihrem Azure Active Directory (Azure AD)-Mandanten.

### <a name="step-1---create-an-app-in-azure-active-directory"></a>Schritt 1: Erstellen einer APP in Azure Active Directory

1. Melden Sie sich bei [Azure](https://portal.azure.com) mit Ihrem **globalen Administrator** Benutzer an.

2. Navigieren Sie zu **Azure Active Directory**  >  **App Registrations**  >  **New Registration**. 

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. Wählen Sie im Registrierungsformular einen Namen für Ihre Anwendung aus, und wählen Sie dann **registrieren** aus.

4. Erlauben Sie Ihrer Anwendung den Zugriff auf Microsoft Defender for Endpoint, und weisen Sie Ihr die Berechtigung " **alle Vorfälle lesen** " zu:

   - Wählen Sie auf Ihrer Anwendungsseite **API-Berechtigungen**  >  **Add permission**  >  **APIs meine Organisation verwendet** > geben Sie **Microsoft 365 Defender** ein, und wählen Sie unter **Microsoft 365 Defender** aus.

   >[!NOTE]
   >Microsoft 365 Defender wird nicht in der ursprünglichen Liste angezeigt. Sie müssen mit dem Schreiben des Namens in das Textfeld beginnen, damit dieser angezeigt wird.

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/apis-in-my-org-tab.PNG)

   - Wählen Sie **Anwendungsberechtigungen**  >  **Incident. Read. all** > Select on **Add Permissions** aus.

   ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   >Sie müssen die entsprechenden Berechtigungen auswählen. 

     Zum Beispiel

     - Um zu ermitteln, welche Berechtigungen Sie benötigen, sehen Sie sich den Abschnitt **Berechtigungen** in der API an, die Sie aufrufen möchten.

5. Wählen Sie **Administrator Zustimmung erteilen** aus.

    - >[!NOTE]
      > Jedes Mal, wenn Sie die Berechtigung hinzufügen, müssen Sie die Option " **Zustimmung erteilen** " auswählen, damit die neue Berechtigung wirksam wird.

    ![Image von Grant-Berechtigungen](../../media/grant-consent.PNG)

6. Fügen Sie der Anwendung ein Kennwort hinzu.

    - Wählen Sie **Zertifikate & Geheimnisse** aus, fügen Sie der geheimen Verschlüsselung eine Beschreibung hinzu, und wählen Sie **Hinzufügen**

    >[!IMPORTANT]
    > Nachdem **Sie hinzufügen** ausgewählt haben, **Kopieren Sie den generierten geheimen Wert**. Sie können nach dem verlassen nicht mehr abrufen.

    ![Bild der APP-Schlüssel erstellen](../../media/webapp-create-key2.png)

7. Notieren Sie Ihre Anwendungs-ID und ihre Mandanten-ID:

   - Wechseln Sie auf der Seite der Anwendung zu **Übersicht** , und kopieren Sie Folgendes:

   ![Bild der erstellten APP-ID](../../media/app-and-tenant-ids.png)


Fertig! Sie haben eine Anwendung erfolgreich registriert.

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>Schritt 2: Abrufen eines Tokens mithilfe der APP und verwenden dieses Tokens für den Zugriff auf die API.

-   Kopieren Sie das Skript unten in PowerShell ISE oder in einen Text-Editor, und speichern Sie es als " **Get-Token.ps1** ".
-   Durch das Ausführen dieses Skripts wird ein Token generiert, das im Arbeitsordner unter dem Namen " **Latest-token.txt** " gespeichert wird.

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

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

-   Sanity Check:<br>
Führen Sie das Skript aus.<br>
Wechseln Sie in Ihrem Browser zu: https://jwt.ms/ <br>
Kopieren Sie das Token (den Inhalt der Latest-token.txt Datei).<br>
Fügen Sie in das obere Feld ein.<br>
Suchen Sie nach dem Abschnitt "Roles". Suchen Sie nach der ```Incidents.Read.All``` Rolle.<br>
Das folgende Beispiel stammt aus einer APP, die ```Incidents.Read.All``` über ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` Berechtigungen verfügt.

![Bild JWT.ms](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a>Lets get the Incidents!

-   Im folgenden Skript wird **Get-Token.ps1** verwendet, um auf die API zuzugreifen, und die letzten Ereignisse werden in den letzten 48 Stunden aktualisiert.
-   Speichern Sie dieses Skript im gleichen Ordner, in dem Sie das vorherige Skript **Get-Token.ps1** gespeichert haben. 
-   Das Skript eine JSON-Datei mit den Daten im gleichen Ordner wie die Skripts.

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

Sie sind fertig! Sie haben soeben erfolgreich Folgendes ausgeführt:
-   Erstellt und registriert und Anwendung
-   Gewährte Berechtigung für diese Anwendung zum Lesen von Warnungen
-   Verbindung mit der API hergestellt
-   Verwenden eines PowerShell-Skripts zum Zurückgeben von Vorfällen, die in den letzten 48 Stunden erstellt wurden



## <a name="related-topic"></a>Verwandtes Thema
- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
- [Zugriff auf Microsoft 365 Defender mit Anwendungskontext](api-create-app-web.md)
- [Zugriff auf Microsoft 365 Defender mit Benutzerkontext](api-create-app-user-context.md)
