---
title: Hinzufügen von benutzerdefinierten Kacheln zum App-Startfeld
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Erstellen Sie schnell Links zu Ihren e-Mails, Dokumenten, apps, SharePoint-Websites, externen Websites und anderen Ressourcen durch Hinzufügen von benutzerdefinierten Kacheln zum App-Startfeld. '
ms.openlocfilehash: fff65c7263e40bf376f53e5f150daea7a24ff55d
ms.sourcegitcommit: 256184cf731c1851b04a07dd7d59ecf020d02635
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43131531"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Hinzufügen von benutzerdefinierten Kacheln zum App-Startfeld

[] In Office 365 können Sie mithilfe des Office 365-App-Startfelds schnell und einfach zu Ihren E-Mails, Kalendern, Dokumenten und Apps gelangen ([weitere Informationen](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). Dabei handelt es sich um Apps, die in Office 365 enthalten sind, sowie benutzerdefinierte Apps, die Sie aus dem [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) oder [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher) hinzufügen.
  
Sie können dem App-Startfeld auch eigene benutzerdefinierte Kacheln hinzufügen, die auf SharePoint-Websites, externe Websites, Legacy-Apps usw. verweisen. Die benutzerdefinierte Kachel wird unter den Apps **Alle** des App-Startfelds angezeigt. Sie können sie aber an die **Start**-Apps anheften und Ihre Benutzer anweisen, ebenso zu verfahren. Auf diese Weise sind die relevanten Websites, Apps und Ressourcen für Ihre Arbeit leicht zu finden. Im folgenden Beispiel wird eine benutzerdefinierte Kachel mit dem Namen "Contoso-Portal" verwendet, um auf die SharePoint-Intranetwebsite einer Organisation zuzugreifen. 
  
![App-Startfeld für Office 365](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Hinzufügen einer benutzerdefinierten Kachel zum App-Startfeld

1. Wechseln Sie im Admin Center zu den **Einstellungs** > **Einstellungen** , und wählen Sie Registerkarte **Organisationsprofil** aus.
    
2. Klicken Sie auf der Registerkarte **Organisationsprofil** auf **benutzerdefinierte Kacheln für App-Startfelder**.
  
3. Wählen Sie **benutzerdefinierte Kachel hinzufügen**aus. 
  
4. Geben Sie einen **Kachelnamen** für die neue Kachel ein. Der Name wird in der Kachel angezeigt. 
    
5. Geben Sie eine **URL der Website** für die Kachel ein. Dies ist der Ort, an dem Ihre Benutzer wechseln sollen, wenn Sie die Kachel auf dem App-Startfeld auswählen. Verwenden Sie https in der URL.<br/>Tipp: Wenn Sie eine Kachel für eine SharePoint-Website erstellen, navigieren Sie zu dieser Website, kopieren Sie die URL, und fügen Sie Sie hier ein. Die URL der Standard-Teamwebsite sieht wie folgt aus:`https://<company_name>.sharepoint.com` 
  
6. Geben Sie eine **URL des Bilds** für die Kachel ein. Das Bild wird auf der Seite "Meine Apps" und im App-Startfeld angezeigt.<br/>Tipp: das Bild sollte 60x60 Pixel sein und für alle Benutzer in Ihrer Organisation verfügbar sein, ohne dass eine Authentifizierung erforderlich ist.

7. Geben Sie eine **Beschreibung** für die Kachel ein. Dies wird angezeigt, wenn Sie die Kachel auf der Seite "meine apps" auswählen und **App-Details**auswählen. 
  
8. Wählen Sie **Änderungen speichern** aus, um die benutzerdefinierte Kachel zu erstellen. 
    
Ihre benutzerdefinierte Kachel wird jetzt im App-Startfeld auf der Registerkarte **Alle** für Sie und Ihre Benutzer angezeigt. 
  
## <a name="promote-the-tile-to-app-launcher"></a>Heraufstufen der Kachel auf den App-startstart

1. Wählen Sie das App-Startprogramm Symbol aus, und wählen Sie **alle apps**aus. 
    
2. Suchen Sie die neue Kachel für Ihre APP, wählen Sie die Auslassungspunkte aus, und wählen Sie **Pin to Launcher**aus.
  
    > [!NOTE]
    > Wenn die in den vorstehenden Schritten erstellte benutzerdefinierte Kachel nicht angezeigt wird, vergewissern Sie sich, dass Ihnen ein Exchange Online-Postfach zugewiesen wurde und Sie sich bei Ihrem Postfach mindestens einmal angemeldet haben. Diese Schritte sind für benutzerdefinierte Kacheln in Office 365 erforderlich. 
  
> [!IMPORTANT]
> Sowohl Sie als auch Ihre Benutzer müssen diese Schritte ausführen, um benutzerdefinierte Kacheln von der Seite "Meine Apps" in das App-Startfeld heraufzustufen. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. Wechseln Sie im Admin Center zur Registerkarte<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organisationsprofil</a> für **Einstellungs** > **Settings** > Einstellungen.
    
2. Klicken Sie auf der Seite **Organisationsprofil** neben **benutzerdefinierte Kacheln für Ihre Organisation hinzufügen**auf **Bearbeiten**.

3. Aktualisieren Sie die Felder **Kachelname**, **URL**, **Beschreibung** oder **Bild-URL** für die benutzerdefinierte Kachel (siehe [Hinzufügen einer benutzerdefinierten Kachel zum App-Startfeld](#add-a-custom-tile-to-the-app-launcher)).
    
4. Wählen Sie **Close** **Aktualisieren** \> aus. 
    
Wenn Sie eine benutzerdefinierte Kachel aus dem Fenster **benutzerdefinierte** Kacheln löschen möchten, wählen Sie die Kachel aus, und wählen Sie **Kachel** > **Löschung**entfernen aus. 
  
## <a name="whats-next"></a>Nächste Schritte

Sie können nicht nur Kacheln zum App-Startfeld hinzufügen, sondern auch Kacheln im App-Startfeld zur Office 365-Navigationsleiste hinzufügen ([weitere Informationen](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). Informationen zum Anpassen des Aussehens und Verhaltens von Office 365 entsprechend dem Branding Ihrer Organisation finden Sie unter [Anpassen des Office 365-Designs](../setup/customize-your-organization-theme.md).
  

