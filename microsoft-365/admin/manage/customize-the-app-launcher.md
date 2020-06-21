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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Erstellen Sie schnell Links zu Ihren e-Mails, Dokumenten, apps, SharePoint-Websites, externen Websites und anderen Ressourcen durch Hinzufügen von benutzerdefinierten Kacheln zum App-Startfeld. '
ms.openlocfilehash: 7220f0be8ad6605b7ad6d30000fde6411948c996
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780133"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Hinzufügen von benutzerdefinierten Kacheln zum App-Startfeld

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

In Microsoft 365 können Sie schnell und einfach mit dem App-Startfeld zu Ihren e-Mails, Kalendern, Dokumenten und apps gelangen ([Weitere Informationen](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)). Dies sind apps, die Sie mit Microsoft 365 sowie benutzerdefinierte apps erhalten, die Sie aus dem [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) oder [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)hinzufügen.
  
You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site. 
  
![App-Startprogramm](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Hinzufügen einer benutzerdefinierten Kachel zum App-Startfeld

1. Wechseln Sie im Admin Center zu den **Einstellungen**  >  **org** -Einstellungen, und wählen Sie Registerkarte **Organisationsprofil** aus.
    
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
    > Wenn die in den vorstehenden Schritten erstellte benutzerdefinierte Kachel nicht angezeigt wird, vergewissern Sie sich, dass Ihnen ein Exchange Online-Postfach zugewiesen wurde und Sie sich bei Ihrem Postfach mindestens einmal angemeldet haben. Diese Schritte sind für benutzerdefinierte Kacheln in Microsoft 365 erforderlich. 
  
> [!IMPORTANT]
> Sowohl Sie als auch Ihre Benutzer müssen diese Schritte ausführen, um benutzerdefinierte Kacheln von der Seite "Meine Apps" in das App-Startfeld heraufzustufen. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. Wechseln Sie im Admin Center zur **Settings**  >  **Org Settings**  >  Registerkarte**Organisationsprofil** der Einstellungen org Settings </a> .
    
2. Klicken Sie auf der Seite **Organisationsprofil** neben **benutzerdefinierte Kacheln für Ihre Organisation hinzufügen**auf **Bearbeiten**.

3. Aktualisieren Sie die Felder **Kachelname**, **URL**, **Beschreibung** oder **Bild-URL** für die benutzerdefinierte Kachel (siehe [Hinzufügen einer benutzerdefinierten Kachel zum App-Startfeld](#add-a-custom-tile-to-the-app-launcher)).
    
4. Wählen **Update** Sie \> **Close**aktualisieren aus. 
    
Wenn Sie eine benutzerdefinierte Kachel aus dem Fenster **benutzerdefinierte** Kacheln löschen möchten, wählen Sie die Kachel aus, und wählen Sie **Kachel**  >  **Löschung**entfernen aus. 
  
## <a name="whats-next"></a>Nächste Schritte

Zusätzlich zum Hinzufügen von Kacheln zum App-Startfeld können Sie der Navigationsleiste App-Start Kacheln hinzufügen ([Weitere Informationen](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)). Informationen zum Anpassen des Erscheinungsbild von Microsoft 365 an die Marke Ihrer Organisation finden Sie unter [Anpassen des Microsoft 365-Designs](../setup/customize-your-organization-theme.md).
  

