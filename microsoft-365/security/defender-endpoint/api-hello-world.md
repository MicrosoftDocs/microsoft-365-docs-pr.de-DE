---
title: Hello World für die Microsoft Defender für Endpunkt-API
ms.reviewer: ''
description: Erstellen Sie einen API-Aufruf im Stil "Hello world" für die Microsoft Defender für Endpunkt-API.
keywords: APIs, unterstützte APIs, erweiterte Suche, Abfrage, Microsoft Defender ATP, Microsoft Defender für Endpunkt
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
ms.openlocfilehash: 385227dc67039fb3666d3b9518af5be8eb01dc7a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769761"
---
# <a name="microsoft-defender-for-endpoint-api---hello-world"></a>Microsoft Defender für Endpunkt-API – Hello World 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** 
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)


- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="get-alerts-using-a-simple-powershell-script"></a>Abrufen von Warnungen mithilfe eines einfachen PowerShell-Skripts

### <a name="how-long-it-takes-to-go-through-this-example"></a>Wie lange dauert es, bis dieses Beispiel durchgeht?
Es dauert nur 5 Minuten, wenn Sie in zwei Schritten fertig sind:
- Anwendungsregistrierung
- Verwenden von Beispielen: Erfordert nur das Kopieren/Einfügen eines kurzen PowerShell-Skripts.

### <a name="do-i-need-a-permission-to-connect"></a>Benöte ich eine Berechtigung zum Herstellen einer Verbindung?
Für die Phase der Anwendungsregistrierung benötigen Sie eine **globale Administratorrolle** in Ihrem Azure Active Directory (Azure AD)-Mandanten.

### <a name="step-1---create-an-app-in-azure-active-directory"></a>Schritt 1: Erstellen einer App in Azure Active Directory

1. Melden Sie sich mit Ihrem **globalen Administratorbenutzer** bei [Azure](https://portal.azure.com) an.

2. Navigieren Sie zu **Azure Active Directory**  >  **App-Registrierungen**  >  **Neuregistrierung.** 

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](images/atp-azure-new-app2.png)

3. Wählen Sie im Registrierungsformular einen Namen für Ihre Anwendung aus, und klicken Sie dann auf **"Registrieren".**

4. Zulassen, dass Ihre Anwendung auf Defender für Endpunkt zugreift und ihr die Berechtigung **"Alle Warnungen lesen"** zuweist:

   - Klicken Sie auf der Anwendungsseite auf **API-Berechtigungen**  >  **Hinzufügen von** Berechtigungs-APIs, die  >  meine Organisation > Typ **WindowsDefenderATP** **verwendet,** und klicken Sie auf **WindowsDefenderATP.**

   - **Hinweis:** WindowsDefenderATP wird nicht in der ursprünglichen Liste angezeigt. Sie müssen mit dem Schreiben des Namens in das Textfeld beginnen, damit es angezeigt wird.

   ![Abbildung des API-Zugriffs und der API-Auswahl1](images/add-permission.png)

   - Auswählen von **Anwendungsberechtigungen**  >  **Alert.Read.All** > Klicken Sie auf **"Berechtigungen hinzufügen".**

   ![Abbildung des API-Zugriffs und der API-Auswahl2](images/application-permissions.png)

   **Wichtiger Hinweis:** Sie müssen die entsprechenden Berechtigungen auswählen. "Alle Warnungen lesen" ist nur ein Beispiel!

     Zum Beispiel

     - Wählen Sie zum [Ausführen erweiterter Abfragen](run-advanced-query-api.md)die Berechtigung "Erweiterte Abfragen ausführen" aus.
     - Um [einen Computer zu isolieren,](isolate-machine.md)wählen Sie die Berechtigung "Computer isolieren" aus.
     - Um zu bestimmen, welche Berechtigung Sie benötigen, sehen Sie sich den Abschnitt **"Berechtigungen"** in der API an, die Sie aufrufen möchten.

5. Klicken Sie auf **"Zustimmung erteilen".**

    - **Hinweis:** Jedes Mal, wenn Sie eine Berechtigung hinzufügen, müssen Sie auf **"Zustimmung erteilen"** klicken, damit die neue Berechtigung wirksam wird.

    ![Abbildung der Berechtigungserteilung](images/grant-consent.png)

6. Fügen Sie der Anwendung einen geheimen Schlüssel hinzu.

    - Klicken Sie auf **"Zertifikate & geheime Schlüssel",** fügen Sie eine Beschreibung zum geheimen Schlüssel hinzu, und klicken Sie auf **"Hinzufügen".**

    **Wichtig:** Kopieren Sie nach dem Klicken auf "Hinzufügen" **den generierten geheimen Wert.** Sie können nach dem Verlassen nicht mehr abrufen!

    ![Abbildung des App-Schlüssels erstellen](images/webapp-create-key2.png)

7. Notieren Sie Ihre Anwendungs-ID und Ihre Mandanten-ID:

   - Wechseln Sie auf der Anwendungsseite zu **"Übersicht",** und kopieren Sie Folgendes:

   ![Abbildung der erstellten App-ID](images/app-and-tenant-ids.png)


fertig! Sie haben eine Anwendung erfolgreich registriert!

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>Schritt 2: Abrufen eines Tokens mithilfe der App und Verwenden dieses Tokens für den Zugriff auf die API.

-   Kopieren Sie das folgende Skript in PowerShell ISE oder in einen Text-Editor, und speichern Sie es als "**Get-Token.ps1**"
-   Durch Ausführen dieses Skripts wird ein Token generiert und im Arbeitsordner unter dem Namen **"Latest-token.txt"** gespeichert.

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

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
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

-   Sanity Check:<br>
Führen Sie das Skript aus.<br>
Wechseln Sie in Ihrem Browser zu: https://jwt.ms/ <br>
Kopieren Sie das Token (den Inhalt der Latest-token.txt-Datei).<br>
In das obere Feld einfügen.<br>
Suchen Sie nach dem Abschnitt "Rollen". Suchen Sie die Rolle "Alert.Read.All".

![Image jwt.ms](images/api-jwt-ms.png)

### <a name="lets-get-the-alerts"></a>Hiermit erhalten Sie die Warnungen!

-   Das folgende Skript verwendet **Get-Token.ps1** für den Zugriff auf die API und erhält die warnungen der letzten 48 Stunden.
-   Speichern Sie dieses Skript in dem Ordner, in dem Sie das vorherige Skript **Get-Token.ps1** gespeichert haben. 
-   Das Skript erstellt zwei Dateien (JSON und CSV) mit den Daten im selben Ordner wie die Skripts.

```
# Returns Alerts created in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Alert from the last 48 hours. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")       

# The URL contains the type of query and the time filter we create above
# Read more about other query options and filters at   Https://TBD- add the documentation link
$url = "https://api.securitycenter.microsoft.com/api/alerts?`$filter=alertCreationTime ge $dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the alerts from the results. 
$alerts =  ($response | ConvertFrom-Json).value | ConvertTo-Json

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json and as csv
$outputJsonPath = "./Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "./Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
($alerts | ConvertFrom-Json) | Export-CSV $outputCsvPath -NoTypeInformation 
```

Sie sind fertig! Sie haben gerade folgendes erfolgreich:
-   Erstellt und registriert und Anwendung
-   Dieser Anwendung wurde die Berechtigung zum Lesen von Warnungen erteilt.
-   Die API wurde verbunden
-   Verwenden eines PowerShell-Skripts zum Zurückgeben von Warnungen, die in den letzten 48 Stunden erstellt wurden



## <a name="related-topic"></a>Verwandtes Thema
- [Microsoft Defender für Endpunkt-APIs](exposed-apis-list.md)
- [Zugreifen auf Microsoft Defender für Endpunkt mit Anwendungskontext](exposed-apis-create-app-webapp.md)
- [Zugreifen auf Microsoft Defender für Endpunkt mit Benutzerkontext](exposed-apis-create-app-nativeapp.md)
