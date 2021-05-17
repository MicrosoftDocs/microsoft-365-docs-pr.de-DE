---
title: Abrufen von Warnungen vom KUNDEN-Mandanten von MSSP
description: Informationen zum Abrufen von Warnungen von einem Kunden-Mandanten
keywords: Managed Security Service Provider, mssp, configure, integration
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
ms.openlocfilehash: ee2a5e1815dd552753ac7f3dee30df11ac4332e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068568"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a>Abrufen von Warnungen vom KUNDEN-Mandanten von MSSP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
>Diese Aktion wird vom MSSP ergriffen.


Es gibt zwei Möglichkeiten zum Abrufen von Warnungen:
- Verwenden der SIEM-Methode
- Verwenden von APIs

## <a name="fetch-alerts-into-your-siem"></a>Abrufen von Warnungen in Ihr SIEM

Zum Abrufen von Warnungen in Ihr SIEM-System müssen Sie die folgenden Schritte ausführen:

Schritt 1: Erstellen einer Drittanbieteranwendung

Schritt 2: Erhalten von Zugriffs- und Aktualisierungstoken vom Mandanten Ihres Kunden
 
Schritt 3: Zulassen der Anwendung auf Microsoft Defender Security Center
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>Schritt 1: Erstellen einer Anwendung in Azure Active Directory (Azure AD)
 
Sie müssen eine Anwendung erstellen und ihr Berechtigungen zum Abrufen von Warnungen vom Microsoft Defender for Endpoint-Mandanten Ihres Kunden erteilen.

1. Melden Sie sich beim [Azure AD-Portal an.](https://aad.portal.azure.com/)

2. Wählen **Azure Active Directory**  >  **App-Registrierungen aus.**
 
3. Klicken Sie **auf Neue Registrierung**.

4. Geben Sie die folgenden Werte an:

    - Name: \<Tenant_name\> SIEM MSSP Connector (ersetzen Tenant_name durch den Mandantenanzeigenamen)
 
    - Unterstützte Kontotypen: Nur Konto in diesem Organisationsverzeichnis 
    - Umleitungs-URI: Wählen Sie Web und Typ `https://<domain_name>/SiemMsspConnector` aus (ersetzen <domain_name> durch den Mandantennamen)

5. Klicken Sie auf **Registrieren**. Die Anwendung wird in der Liste der Anwendungen angezeigt, die Sie besitzen.

6. Wählen Sie die Anwendung aus, und klicken Sie dann auf **Übersicht**.

7. Kopieren Sie den Wert aus dem **Feld Anwendungs-ID (Client-ID)** an einen sicheren Ort, den Sie im nächsten Schritt benötigen.

8. Wählen **Sie zertifikats & im** neuen Anwendungsbereich aus.

9. Klicken Sie **auf Neuer Geheimer Clientgeheimnis**.

    - Beschreibung: Geben Sie eine Beschreibung für den Schlüssel ein.
    - Expires: Select **In 1 year**

 
10. Klicken **Sie auf Hinzufügen,** kopieren Sie den Wert des geheimen Clientgeheimnis an einen sicheren Ort, den Sie im nächsten Schritt benötigen.
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>Schritt 2: Erhalten von Zugriffs- und Aktualisierungstoken vom Mandanten Ihres Kunden
In diesem Abschnitt erfahren Sie, wie Sie ein PowerShell-Skript verwenden, um die Token vom Mandanten Ihres Kunden abzurufen. Dieses Skript verwendet die Anwendung aus dem vorherigen Schritt, um die Zugriffs- und Aktualisierungstoken mithilfe der OAuth-Autorisierungscode-Flow.

Nachdem Sie Ihre Anmeldeinformationen angegeben haben, müssen Sie der Anwendung zustimmen, damit die Anwendung im Mandanten des Kunden bereitgestellt wird.


1. Erstellen Sie einen neuen Ordner, und nennen Sie ihn: `MsspTokensAcquisition` .

2. Laden Sie [das Modul LoginBrowser.psm1 herunter,](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) und speichern Sie es im `MsspTokensAcquisition` Ordner.

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
 
    - Ersetzen \<client_id\> Sie durch die **Anwendungs-ID (Client-ID),** die Sie aus dem vorherigen Schritt erhalten haben.
    - Ersetzen \<app_key\> Sie durch den **geheimen Clientgeheimnis,** den Sie im vorherigen Schritt erstellt haben.
    - Ersetzen \<customer_tenant_id\> Sie durch die Mandanten-ID Ihres **Kunden.** 
 

7. Sie werden aufgefordert, Ihre Anmeldeinformationen und Ihre Zustimmung zur Verfügung zu stellen. Ignorieren Sie die Seitenumleitung.

8. Im PowerShell-Fenster erhalten Sie ein Zugriffstoken und ein Aktualisierungstoken. Speichern Sie das Aktualisierungstoken, um Ihren SIEM-Connector zu konfigurieren. 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a>Schritt 3: Zulassen der Anwendung Microsoft Defender Security Center
Sie müssen die Anwendung zulassen, die Sie in diesem Microsoft Defender Security Center.
 
Sie benötigen die Berechtigung **Portalsystemeinstellungen verwalten,** um die Anwendung zu erlauben. Andernfalls müssen Sie Ihren Kunden bitten, die Anwendung für Sie zu erlauben.

1. Wechseln Sie `https://securitycenter.windows.com?tid=<customer_tenant_id>` zu \<customer_tenant_id\> (ersetzen Sie durch die Mandanten-ID des Kunden.

2. Klicken **Sie Einstellungen**  >  **SIEM**. 

3. Wählen Sie die **Registerkarte MSSP** aus.

4. Geben Sie **die Anwendungs-ID** aus dem ersten Schritt und Ihre **Mandanten-ID ein.**

5. Klicken **Sie auf Anwendung autorisieren**. 

 
Sie können nun die relevante Konfigurationsdatei für Ihr SIEM herunterladen und eine Verbindung mit der Defender for Endpoint-API herstellen. Weitere Informationen finden Sie unter [Pull alerts to your SIEM tools](configure-siem.md).
 

- Schreiben Sie in der Datei ArcSight-Konfigurationsdatei/Splunk-Authentifizierungseigenschaften den Anwendungsschlüssel manuell, indem Sie den geheimen Wert festlegen.
- Anstatt ein Aktualisierungstoken im Portal zu erwerben, verwenden Sie das Skript aus dem vorherigen Schritt, um ein Aktualisierungstoken zu erwerben (oder es auf andere Art zu erwerben).

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>Abrufen von Warnungen vom Mandanten des MSSP-Kunden mithilfe von APIs
 
Informationen zum Abrufen von Warnungen mithilfe der REST-API finden Sie unter [Pull alerts using REST API](pull-alerts-using-rest-api.md).


## <a name="see-also"></a>Siehe auch
- [Gewähren von MSSP-Zugriff auf das Portal](grant-mssp-access.md)
- [Zugreifen auf das MSSP-Kundenportal](access-mssp-portal.md)
- [Warnungsbenachrichtigungen konfigurieren](configure-mssp-notifications.md)
