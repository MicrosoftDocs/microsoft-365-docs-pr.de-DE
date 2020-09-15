---
title: Zugreifen auf Microsoft Threat Protection-APIs im Namen des Benutzers
description: Informationen zum Zugriff auf Microsoft Threat Protection-APIs im Namen des Benutzers
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
ms.openlocfilehash: c3e5b758336f1a6ac57fcfcb448de93b7473591d
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650338"
---
# <a name="access-microsoft-threat-protection-apis-on-behalf-of-user"></a>Zugriff auf Microsoft Threat Protection-APIs im Namen des Benutzers

**Gilt für:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.


Auf dieser Seite wird beschrieben, wie Sie eine Anwendung erstellen, um den programmgesteuerten Zugriff auf Microsoft Threat Protection im Namen eines Benutzers zu erhalten.

Wenn Sie den programmgesteuerten Zugriff auf Microsoft Threat Protection ohne Benutzer benötigen, finden Sie weitere Informationen unter [Erstellen einer APP für den Zugriff auf Microsoft Threat Protection ohne Benutzer](api-create-app-web.md).

Wenn Sie nicht sicher sind, welchen Zugriff Sie benötigen, lesen Sie den [Zugriff auf die Microsoft Threat Protection-APIs](api-access.md).

Microsoft Threat Protection macht einen Großteil seiner Daten und Aktionen über eine Reihe von programmgesteuerten APIs verfügbar. Mit diesen APIs können Sie Arbeitsabläufe und Innovationen basierend auf den Microsoft Threat Protection-Funktionen automatisieren. Für den API-Zugriff ist die OAuth 2.0-Authentifizierung erforderlich. Weitere Informationen finden Sie unter [OAuth 2,0-Autorisierungs Code Fluss](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:
- Erstellen einer Aad-Anwendung
- Abrufen eines Zugriffstokens mithilfe dieser Anwendung
- Verwenden des Tokens für den Zugriff auf die Microsoft Threat Protection-API

Auf dieser Seite wird erklärt, wie Sie eine Aad-Anwendung erstellen, ein Zugriffstoken für Microsoft Threat Protection abrufen und das Token überprüfen.

>[!NOTE]
> Wenn Sie im Namen eines Benutzers auf die Microsoft Threat Protection-API zugreifen, benötigen Sie die richtige Anwendungs-und Benutzerberechtigung.


>[!TIP]
> Wenn Sie über die Berechtigung zum Ausführen einer Aktion im Portal verfügen, haben Sie die Berechtigung, die Aktion in der API auszuführen.

## <a name="create-an-app"></a>Erstellen einer APP

1. Melden Sie sich bei [Azure](https://portal.azure.com) mit dem Benutzer an, der über eine **globale Administrator** Rolle verfügt.

2. Navigieren Sie zu **Azure Active Directory**  >  **App Registrations**  >  **New Registration**. 

   ![Abbildung von Microsoft Azure und Navigation zur Anwendungsregistrierung](../../media/atp-azure-new-app2.png)

3. Geben Sie im Feld Registrierung von die folgenden Informationen ein, und klicken Sie dann auf **registrieren**.

   ![Bild des Fensters "Anwendungs erstellen"](../../media/nativeapp-create2.PNG)

   - **Name:** Name Ihrer Anwendung
   - **Anwendungstyp:** Öffentlicher Client
   - **Umleitungs-URI:**https://portal.azure.com

4. Um Ihrer APP den Zugriff auf Microsoft Threat Protection und das Zuweisen von IT-Berechtigungen zu ermöglichen, wählen Sie auf Ihrer Anwendungsseite **API-Berechtigungen**  >  **Add permission**  >  **APIs meine Organisation verwendet** > aus, geben Sie **Microsoft Threat Protection**ein, und wählen Sie dann **Microsoft Threat Protection**aus.

    >[!NOTE]
    > Microsoft Threat Protection wird nicht in der ursprünglichen Liste angezeigt. Sie müssen mit dem Schreiben des Namens in das Textfeld beginnen, damit dieser angezeigt wird.

      ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/apis-in-my-org-tab.PNG)

    - Wählen Sie **Delegierte Berechtigungen** > wählen Sie die entsprechenden Berechtigungen für Ihr Szenario aus, beispielsweise **Incident. Read**, und wählen Sie dann **Berechtigungen hinzufügen**aus.

      ![Abbildung des API-Zugriffs und der API-Auswahl](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     >Sie müssen die entsprechenden Berechtigungen auswählen. 

    -  Um zu ermitteln, welche Berechtigungen Sie benötigen, sehen Sie sich den Abschnitt **Berechtigungen** in der API an, die Sie aufrufen möchten.

    - Klicken Sie auf **Zustimmung erteilen** .

      >[!NOTE]
      >Jedes Mal, wenn Sie die Berechtigung hinzufügen, müssen Sie auf **Zustimmung erteilen** klicken, damit die neue Berechtigung wirksam wird.

      ![Image von Grant-Berechtigungen](../../media/grant-consent-delegated.PNG)

6. Notieren Sie Ihre Anwendungs-ID und ihre Mandanten-ID:

   - Wechseln Sie auf der Seite der Anwendung zu **Übersicht** , und kopieren Sie Folgendes:

   ![Bild der erstellten APP-ID](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a>Abrufen eines Zugriffstokens mithilfe von PowerShell

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a>Verwandte Themen
- [Zugreifen auf die Microsoft Threat Protection-APIs](api-access.md)
- [Zugriff auf Microsoft Threat Protection mit Anwendungskontext](api-create-app-web.md)
