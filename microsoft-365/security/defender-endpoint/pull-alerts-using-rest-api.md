---
title: Abrufen von Microsoft Defender für Endpunkterkennungen mithilfe der REST-API
description: Erfahren Sie, wie Sie einen Microsoft Defender für Endpunkt-API-Endpunkt aufrufen, um Erkennungen mithilfe der SIEM-REST-API im JSON-Format abzurufen.
keywords: Erkennungen, Pullerkennungen, Rest-API, Anforderung, Antwort
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: api
ms.openlocfilehash: 6716b0eb029b49ec08cb52ebefc23e50b19036ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771669"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a>Abrufen von Microsoft Defender für Endpunkterkennungen mithilfe der SIEM-REST-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- [Microsoft Defender für Endpunkt-Warnung](alerts.md) besteht aus einer oder mehreren Erkennungen.
>- [Die Microsoft Defender für Endpunkterkennung](api-portal-mapping.md) besteht aus dem verdächtigen Ereignis, das auf dem Gerät aufgetreten ist, und den zugehörigen Warnungsdetails.
>-Die Microsoft Defender für Endpunkt-Warnungs-API ist die neueste API für die Benachrichtigungsnutzung und enthält eine detaillierte Liste der zugehörigen Nachweise für jede Warnung. Weitere Informationen finden Sie unter ["Warnungsmethoden und -eigenschaften"](alerts.md) und ["Warnungen auflisten".](get-alerts.md)

Microsoft Defender für Endpunkt unterstützt das OAuth 2.0-Protokoll, um Erkennungen aus der API abzurufen.

Im Allgemeinen unterstützt das OAuth 2.0-Protokoll vier Arten von Flüssen:
- Autorisierungserteilungsfluss
- Impliziter Fluss
- Clientanmeldeinformationsfluss
- Ressourcenbesitzerablauf

Weitere Informationen zu den OAuth-Spezifikationen finden Sie auf der [OAuth-Website.](http://www.oauth.net)

Microsoft Defender für Endpunkt unterstützt den _Autorisierungserteilungs-_ und _Clientanmeldeinformationsfluss,_ um Zugriff auf Pullerkennungen mit Azure Active Directory (AAD) als Autorisierungsserver zu erhalten.

Der _Autorisierungserteilungsfluss_ verwendet Benutzeranmeldeinformationen, um einen Autorisierungscode abzurufen, der dann zum Abrufen eines Zugriffstokens verwendet wird.

Der _Clientanmeldeinformationsfluss_ verwendet Clientanmeldeinformationen, um sich bei der Microsoft Defender für Endpunkt-Endpunkt-URL zu authentifizieren. Dieser Fluss eignet sich für Szenarien, in denen ein OAuth-Client Anforderungen an eine API erstellt, für die keine Benutzeranmeldeinformationen erforderlich sind.

Verwenden Sie die folgende Methode in der Microsoft Defender für Endpunkt-API, um Erkennungen im JSON-Format abzurufen.

>[!NOTE]
>Microsoft Defender Security Center führt ähnliche Warnungserkennungen in einer einzigen Warnung zusammen. Diese API ruft Warnungserkennungen in der rohen Form basierend auf den von Ihnen festgelegten Abfrageparametern ab, sodass Sie Ihre eigene Gruppierung und Filterung anwenden können. 

## <a name="before-you-begin"></a>Bevor Sie beginnen
- Bevor Sie den Microsoft Defender für Endpunkt-Endpunkt aufrufen, um Erkennungen abzurufen, müssen Sie die SIEM-Integrationsanwendung in Azure Active Directory (AAD) aktivieren. Weitere Informationen finden Sie unter [Aktivieren der SIEM-Integration in Microsoft Defender für Endpunkt.](enable-siem-integration.md)

- Notieren Sie sich die folgenden Werte bei der Registrierung Ihrer Azure-App. Sie benötigen diese Werte, um den OAuth-Fluss in Ihrem Dienst oder Ihrer Dämon-App zu konfigurieren:
  - App-ID (eindeutig für Ihre Anwendung)
  - App-Schlüssel oder Secret (eindeutig für Ihre App)
  - OAuth 2.0-Tokenendpunkt Ihrer App
    - Klicken Sie für diesen Wert auf **Endpunkte anzeigen** am unteren Rand des Azure-Verwaltungsportals auf der App-Seite. Der Endpunkt sieht wie `https://login.microsoftonline.com/{tenantId}/oauth2/token` aus.

## <a name="get-an-access-token"></a>Abrufen eines Zugriffstokens
Bevor Sie Aufrufe an den Endpunkt erstellen, müssen Sie ein Zugriffstoken abrufen.

Sie verwenden das Zugriffstoken, um auf die geschützte Ressource zuzugreifen, bei der es sich um Erkennungen in Microsoft Defender für Endpunkt handelt.

Um ein Zugriffstoken abzurufen, müssen Sie eine POST-Anforderung an den Token ausgebenden Endpunkt ausführen. Hier ist eine Beispielanforderung:

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
Als Antwort werden ein Zugriffstoken und Ablauf Access-Token und Gültigkeitsinformationen zurückgegeben.

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
Sie können nun den Wert im *feld access_token* in einer Anforderung an die Defender für Endpunkt-API verwenden.

## <a name="request"></a>Anforderung
Mit einem Zugriffstoken kann Ihre App authentifizierte Anforderungen an die Microsoft Defender für Endpunkt-API senden. Ihre App muss das Zugriffstoken an den Autorisierungs-Header jeder Anforderung anfügen.

### <a name="request-syntax"></a>Anforderungssyntax
Methode | Anforderungs-URI
:---|:---|
GET| Verwenden Sie den für Ihre Region geltenden URI. <br><br> **Für die EU:**`https://wdatp-alertexporter-eu.windows.com/api/alerts` </br> **Für die USA:**`https://wdatp-alertexporter-us.windows.com/api/alerts` <br> **Für Großbritannien:**`https://wdatp-alertexporter-uk.windows.com/api/alerts` 

### <a name="request-header"></a>Anforderungsheader
Kopfzeile | Typ | Beschreibung|
:--|:--|:--
Authorization | string | Erforderlich. Das Azure AD-Zugriffstoken im Formular **Bearertoken.** &lt;  &gt; |

### <a name="request-parameters"></a>Anforderungsparameter

Verwenden Sie optionale Abfrageparameter, um die in einer Antwort zurückgegebene Datenmenge anzugeben und zu steuern. Wenn Sie diese Methode ohne Parameter aufrufen, enthält die Antwort alle Warnungen in Ihrer Organisation in den letzten 2 Stunden.

Name | Wert| Beschreibung
:---|:---|:---
sinceTimeUtc | DateTime | Definiert die unteren zeitgebundenen Warnungen, aus denen basierend auf dem Feld abgerufen wird: <br> `LastProcessedTimeUtc` <br> Der Zeitraum ist: von sinceTimeUtc-Zeit bis zur aktuellen Zeit. <br><br> **HINWEIS:** Wenn nicht angegeben, werden alle Warnungen abgerufen, die in den letzten zwei Stunden generiert wurden.
untilTimeUtc | DateTime | Definiert, dass warnungen mit oberen Zeitgrenzen abgerufen werden. <br> Der Zeitraum ist: von `sinceTimeUtc` Zeit zu `untilTimeUtc` Zeit. <br><br> **HINWEIS:** Wenn nicht angegeben, ist der Standardwert die aktuelle Uhrzeit.
Vor | Zeichenfolge | Ruft Warnungen im folgenden Zeitraum ab: von `(current_time - ago)` Zeit zu `current_time` Zeit. <br><br> Der Wert sollte gemäß **dem ISO 8601-Dauerformat** festgelegt werden. <br> Beispiel: `ago=PT10M` Ruft Warnungen ab, die in den letzten 10 Minuten empfangen wurden.
Begrenzung | int | Definiert die Anzahl der abzurufenden Warnungen. Die neuesten Warnungen werden basierend auf der definierten Anzahl abgerufen.<br><br> **HINWEIS:** Wenn nicht angegeben, werden alle im Zeitraum verfügbaren Warnungen abgerufen.
Computergruppen | Zeichenfolge | Gibt Gerätegruppen an, aus denen Warnungen abgerufen werden sollen. <br><br> **HINWEIS:** Wenn nicht angegeben, werden Warnungen von allen Gerätegruppen abgerufen. <br><br> Beispiel: <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
DeviceCreatedMachineTags | Zeichenfolge | Einzelnes Gerätetag aus der Registrierung.
CloudCreatedMachineTags | Zeichenfolge | Gerätetags, die in Microsoft Defender Security Center erstellt wurden.

### <a name="request-example"></a>Anforderungsbeispiel
Im folgenden Beispiel wird veranschaulicht, wie Sie alle Erkennungen in Ihrer Organisation abrufen.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

Das folgende Beispiel zeigt eine Anforderung zum Abrufen der letzten 20 Erkennungen seit 2016-09-12 00:00:00.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a>Antwort
Der Rückgabewert ist ein Array von Warnungsobjekten im JSON-Format.

Hier ist ein Beispiel für einen Rückgabewert:

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a>Codebeispiele
### <a name="get-access-token"></a>Zugriffstoken abrufen
Die folgenden Codebeispiele veranschaulichen, wie Sie ein Zugriffstoken zum Aufrufen der Microsoft Defender für Endpunkt-SIEM-API abrufen.

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a>Verwenden des Tokens zum Herstellen einer Verbindung mit dem Erkennungsendpunkt
Die folgenden Codebeispiele veranschaulichen, wie Sie ein Zugriffstoken zum Aufrufen der Defender für Endpunkt-SIEM-API zum Abrufen von Warnungen verwenden.

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a>Fehlercodes
Die Rest-API von Microsoft Defender für Endpunkt gibt die folgenden Fehlercodes zurück, die durch eine ungültige Anforderung verursacht wurden.

HTTP-Fehlercode | Beschreibung
:---|:---
401 | Fehlerhafte Anforderung oder ungültiges Token.
403 | Nicht autorisierte Ausnahme : Eine der Domänen wird nicht vom Mandantenadministrator verwaltet, oder der Mandantenstatus wird gelöscht.
500 | Fehler im Dienst.

## <a name="related-topics"></a>Verwandte Themen
- [Aktivieren der SIEM-Integration in Microsoft Defender für Endpunkt](enable-siem-integration.md)
- [Konfigurieren von ArcSight zum Abrufen von Microsoft Defender für Endpunkterkennungen](configure-arcsight.md)
- [Abrufen von Erkennungen an Ihre SIEM-Tools](configure-siem.md)
- [Microsoft Defender für Endpunkterkennungsfelder](api-portal-mapping.md)
- [Behandeln von Problemen mit der Integration von SIEM-Tools](troubleshoot-siem.md)
