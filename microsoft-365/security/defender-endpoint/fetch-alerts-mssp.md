---
title: Abrufen von Warnungen vom MSSP-Kundenmandanten
description: Erfahren Sie, wie Sie Warnungen von einem Kundenmandanten abrufen
keywords: managed security service provider, mssp, configure, integration
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
ms.openlocfilehash: 456507533265bc085adc1008f3264e123569a6ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770769"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a>Abrufen von Warnungen vom MSSP-Kundenmandanten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
>Diese Aktion wird vom MSSP ausgeführt.


Es gibt zwei Möglichkeiten, Warnungen abzurufen:
- Verwenden der SIEM-Methode
- Verwenden von APIs

## <a name="fetch-alerts-into-your-siem"></a>Abrufen von Warnungen in Ihr SIEM

Um Warnungen in Ihr SIEM-System abzurufen, müssen Sie die folgenden Schritte ausführen:

Schritt 1: Erstellen einer Drittanbieteranwendung

Schritt 2: Abrufen von Zugriffs- und Aktualisierungstoken vom Mandanten Ihres Kunden
 
Schritt 3: Zulassen der Anwendung auf Microsoft Defender Security Center
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>Schritt 1: Erstellen einer Anwendung in Azure Active Directory (Azure AD)
 
Sie müssen eine Anwendung erstellen und ihr Berechtigungen erteilen, um Warnungen vom Microsoft Defender für Endpunkt-Mandanten Ihres Kunden abzurufen.

1. Melden Sie sich beim [Azure AD-Portal](https://aad.portal.azure.com/)an.

2. Wählen Sie **Azure Active Directory**  >  **App-Registrierungen aus.**
 
3. Klicken Sie auf **"Neue Registrierung".**

4. Geben Sie die folgenden Werte an:

    - Name: \<Tenant_name\> SIEM MSSP Connector (ersetzen Sie Tenant_name durch den Anzeigenamen des Mandanten)
 
    - Unterstützte Kontotypen: Nur Konto in diesem Organisationsverzeichnis 
    - Umleitungs-URI: Web und Typ auswählen `https://<domain_name>/SiemMsspConnector` (<domain_name> durch den Mandantennamen ersetzen)

5. Klicken Sie auf **Registrieren**. Die Anwendung wird in der Liste der Anwendungen angezeigt, die Sie besitzen.

6. Wählen Sie die Anwendung aus, und klicken Sie dann auf **"Übersicht".**

7. Kopieren Sie den Wert aus dem **Anwendungs-ID-Feld (Client)** an einen sicheren Ort, den Sie im nächsten Schritt benötigen.

8. Wählen Sie im neuen Anwendungsbereich **"Zertifikat & geheime Schlüssel"** aus.

9. Klicken Sie auf **"Neuer geheimer Clientschlüssel".**

    - Beschreibung: Geben Sie eine Beschreibung für den Schlüssel ein.
    - Läuft ab: **In 1 Jahr** auswählen

 
10. Klicken Sie auf **"Hinzufügen",** kopieren Sie den Wert des geheimen Clientschlüssels an einen sicheren Ort, den Sie im nächsten Schritt benötigen.
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>Schritt 2: Abrufen von Zugriffs- und Aktualisierungstoken vom Mandanten Ihres Kunden
In diesem Abschnitt erfahren Sie, wie Sie ein PowerShell-Skript verwenden, um die Token vom Mandanten Ihres Kunden abzurufen. Dieses Skript verwendet die Anwendung aus dem vorherigen Schritt, um die Zugriffs- und Aktualisierungstoken mithilfe des OAuth-Autorisierungscodes Flow abzurufen.

Nachdem Sie Ihre Anmeldeinformationen angegeben haben, müssen Sie der Anwendung zustimmen, damit die Anwendung im Mandanten des Kunden bereitgestellt wird.


1. Erstellen Sie einen neuen Ordner, und nennen Sie ihn: `MsspTokensAcquisition` .

2. Laden Sie das [Modul "LoginBrowser.psm1"](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) herunter, und speichern Sie es im `MsspTokensAcquisition` Ordner.

    >[!NOTE]
    >Ersetzen Sie in Zeile 30 `authorzationUrl` durch `authorizationUrl` .

3. Erstellen Sie eine Datei mit dem folgenden Inhalt, und speichern Sie sie mit dem Namen `MsspTokensAcquisition.ps1` im Ordner:
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. Öffnen Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten im `MsspTokensAcquisition` Ordner.

5. Führen Sie den folgenden Befehl aus:`Set-ExecutionPolicy -ExecutionPolicy Bypass`

6. Geben Sie die folgenden Befehle ein: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`
 
    - Ersetzen Sie \<client_id\> dies durch die **Anwendungs-ID (Client-ID),** die Sie aus dem vorherigen Schritt erhalten haben.
    - Ersetzen Sie \<app_key\> dies durch den **geheimen Clientschlüssel,** den Sie im vorherigen Schritt erstellt haben.
    - Ersetzen Sie \<customer_tenant_id\> dies durch die **Mandanten-ID** Ihres Kunden. 
 

7. Sie werden aufgefordert, Ihre Anmeldeinformationen und Ihre Zustimmung anzugeben. Ignorieren Sie die Seitenumleitung.

8. Im PowerShell-Fenster erhalten Sie ein Zugriffstoken und ein Aktualisierungstoken. Speichern Sie das Aktualisierungstoken, um Ihren SIEM-Connector zu konfigurieren. 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a>Schritt 3: Zulassen der Anwendung auf Microsoft Defender Security Center
Sie müssen die Anwendung zulassen, die Sie in Microsoft Defender Security Center erstellt haben.
 
Sie benötigen die Berechtigung **"Portalsystemeinstellungen verwalten",** um die Anwendung zuzulassen. Andernfalls müssen Sie Ihren Kunden auffordern, die Anwendung für Sie zuzulassen.

1. Wechseln Sie zu `https://securitycenter.windows.com?tid=<customer_tenant_id>` (ersetzen Sie \<customer_tenant_id\> diese durch die Mandanten-ID des Kunden.

2. Klicken Sie **auf Einstellungen**  >  **SIEM**. 

3. Wählen Sie die **Registerkarte "MSSP"** aus.

4. Geben Sie die **Anwendungs-ID** aus dem ersten Schritt und Ihre **Mandanten-ID** ein.

5. Klicken Sie auf **"Anwendung autorisieren".** 

 
Sie können jetzt die relevante Konfigurationsdatei für Ihr SIEM herunterladen und eine Verbindung mit der Defender für Endpunkt-API herstellen. Weitere Informationen finden Sie unter [Pull-Warnungen an Ihre SIEM-Tools.](configure-siem.md)
 

- Schreiben Sie in der ArcSight-Konfigurationsdatei/Splunk-Authentifizierungseigenschaftendatei Den Anwendungsschlüssel manuell, indem Sie den geheimen Wert festlegen.
- Anstatt ein Aktualisierungstoken im Portal abzurufen, verwenden Sie das Skript aus dem vorherigen Schritt, um ein Aktualisierungstoken abzurufen (oder es auf andere Weise zu erwerben).

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>Abrufen von Warnungen vom Mandanten des MSSP-Kunden mithilfe von APIs
 
Informationen zum Abrufen von Warnungen mithilfe der REST-API finden Sie unter [Pull-Warnungen mithilfe der REST-API.](pull-alerts-using-rest-api.md)


## <a name="see-also"></a>Siehe auch
- [Gewähren von MSSP-Zugriff auf das Portal](grant-mssp-access.md)
- [Zugreifen auf das MSSP-Kundenportal](access-mssp-portal.md)
- [Warnungsbenachrichtigungen konfigurieren](configure-mssp-notifications.md)
