---
title: Hinzufügen von benutzerdefinierten Kacheln zum App-Startfeld
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Erstellen Sie schnell Links zu Ihren E-Mails, Dokumenten, Apps, SharePoint-Websites, externen Websites und anderen Ressourcen, indem Sie dem App-Startfeld benutzerdefinierte Kacheln hinzufügen. '
ms.openlocfilehash: 2bbcf64b807754aed199c441f6df028d5fe20a97
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926234"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Hinzufügen von benutzerdefinierten Kacheln zum App-Startfeld

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

In Microsoft 365 können Sie mithilfe des App-Startfelds schnell und einfach auf Ihre E-Mails, Kalender, Dokumente und Apps zugreifen[(weitere Informationen).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) Dies sind Apps, die Sie mit Microsoft 365 erhalten, sowie benutzerdefinierte Apps, die Sie aus dem [SharePoint Store oder](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) [Azure AD hinzufügen.](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)
  
Sie können dem App-Startfeld auch eigene benutzerdefinierte Kacheln hinzufügen, die auf SharePoint-Websites, externe Websites, Legacy-Apps usw. verweisen. Die benutzerdefinierte Kachel wird unter den Apps **Alle** des App-Startfelds angezeigt. Sie können sie aber an die **Start**-Apps anheften und Ihre Benutzer anweisen, ebenso zu verfahren. Auf diese Weise sind die relevanten Websites, Apps und Ressourcen für Ihre Arbeit leicht zu finden. Im folgenden Beispiel wird eine benutzerdefinierte Kachel mit dem Namen "Contoso-Portal" verwendet, um auf die SharePoint-Intranetwebsite einer Organisation zuzugreifen. 
  
![App-Startfeld](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Hinzufügen einer benutzerdefinierten Kachel zum App-Startfeld

1. Melden Sie sich beim Admin Center als globaler Administrator an, wechseln Sie zu "Organisationseinstellungen", und wählen Sie  >  die Registerkarte **"Organisationsprofil"** aus.
    
2. Wählen Sie **auf der Registerkarte "Organisationsprofil"** die **Kacheln des benutzerdefinierten App-Startfelds aus.**
  
3. Wählen **Sie "Benutzerdefinierte Kachel hinzufügen" aus.** 
  
4. Geben Sie einen **Kachelnamen** für die neue Kachel ein. Der Name wird in der Kachel angezeigt. 
    
5. Geben Sie **eine URL der Website für** die Kachel ein. Dies ist der Ort, an den Ihre Benutzer gehen sollen, wenn sie die Kachel im App-Startfeld auswählen. Verwenden Sie HTTPS in der URL.<br/>TIPP: Wenn Sie eine Kachel für eine SharePoint-Website erstellen, navigieren Sie zu dieser Website, kopieren Sie die URL, und fügen Sie sie hier ein. Die URL Ihrer standardmäßigen Teamwebsite sieht wie die folgende aus: `https://<company_name>.sharepoint.com` 
  
6. Geben Sie **eine URL des Bilds für** die Kachel ein. Das Bild wird auf der Seite "Meine Apps" und im App-Startfeld angezeigt.<br/>TIPP: Das Bild sollte 60 x 60 Pixel groß sein und für alle Benutzer in Ihrer Organisation verfügbar sein, ohne dass eine Authentifizierung erforderlich ist.

7. Geben Sie eine **Beschreibung** für die Kachel ein. Dies wird angezeigt, wenn Sie die Kachel auf der Seite "Meine Apps" und die **App-Details auswählen.** 
  
8. Wählen **Sie "Änderungen speichern"** aus, um die benutzerdefinierte Kachel zu erstellen. 
    
Ihre benutzerdefinierte Kachel wird jetzt im App-Startfeld auf der Registerkarte **Alle** für Sie und Ihre Benutzer angezeigt. 
  
## <a name="promote-the-tile-to-app-launcher"></a>Promote the tile to App Startprogramm

1. Wählen Sie das Symbol für das App-Startfeld und dann **alle Apps aus.** 
    
2. Suchen Sie die neue Kachel für Ihre App, wählen Sie die Auslassungspunkte aus, und wählen **Sie "An Startfeld anheften" aus.**
  
    > [!NOTE]
    > Wenn die in den vorstehenden Schritten erstellte benutzerdefinierte Kachel nicht angezeigt wird, vergewissern Sie sich, dass Ihnen ein Exchange Online-Postfach zugewiesen wurde und Sie sich bei Ihrem Postfach mindestens einmal angemeldet haben. Diese Schritte sind für benutzerdefinierte Kacheln in Microsoft 365 erforderlich. 
  
> [!IMPORTANT]
> Sowohl Sie als auch Ihre Benutzer müssen diese Schritte ausführen, um benutzerdefinierte Kacheln von der Seite "Meine Apps" in das App-Startfeld heraufzustufen. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. Wechseln Sie im Admin Center zur Profilregisterkarte  >  "Organisationseinstellungen".  >   </a>
    
2. Wählen Sie **auf der Profilseite "Organisation"** neben "Benutzerdefinierte **Kacheln für Ihre** Organisation hinzufügen" die Option **"Bearbeiten" aus.**

3. Aktualisieren Sie die Felder **Kachelname**, **URL**, **Beschreibung** oder **Bild-URL** für die benutzerdefinierte Kachel (siehe [Hinzufügen einer benutzerdefinierten Kachel zum App-Startfeld](#add-a-custom-tile-to-the-app-launcher)).
    
4. Wählen Sie **"Update** \> **schließen" aus.** 
    
Um eine benutzerdefinierte Kachel zu löschen, wählen Sie im **Fenster** "Benutzerdefinierte Kacheln" die Kachel aus, und wählen **Sie "Kachel löschen"**  >  **aus.** 
  
## <a name="whats-next"></a>Nächste Schritte

Zusätzlich zum Hinzufügen von Kacheln zum App-Startfeld können Sie der Navigationsleiste Kacheln für das App-Startfeld hinzufügen[(weitere Informationen).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985) Informationen zum Anpassen des Erscheinungsbilds von Microsoft 365 an die Marke Ihrer Organisation finden Sie unter "Anpassen [des Microsoft 365-Designs".](../setup/customize-your-organization-theme.md)
  
