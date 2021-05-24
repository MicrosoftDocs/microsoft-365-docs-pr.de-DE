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
description: Erstellen Sie Schnelllinks zu E-Mails, Dokumenten, Apps, SharePoint Websites, externen Websites und anderen Ressourcen, indem Sie dem App-Startfeld benutzerdefinierte Kacheln hinzufügen.
ms.openlocfilehash: 47f871d66f180225e877a521ef159fc745960507
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623773"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Hinzufügen von benutzerdefinierten Kacheln zum App-Startfeld

In Microsoft 365 können Sie mithilfe des App-Startfelds schnell und einfach zu Ihren E-Mails, Kalendern, Dokumenten und Apps wechseln ([weitere Informationen).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) Dies sind Apps, die Sie mit Microsoft 365 und benutzerdefinierten Apps erhalten, die Sie aus dem SharePoint Store [oder Azure AD hinzufügen.](/previous-versions/office/office-365-api/) [](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43)
  
Sie können dem App-Startfeld auch eigene benutzerdefinierte Kacheln hinzufügen, die auf SharePoint-Websites, externe Websites, Legacy-Apps usw. verweisen. Die benutzerdefinierte Kachel wird unter den Apps **Alle** des App-Startfelds angezeigt. Sie können sie aber an die **Start**-Apps anheften und Ihre Benutzer anweisen, ebenso zu verfahren. Auf diese Weise sind die relevanten Websites, Apps und Ressourcen für Ihre Arbeit leicht zu finden. Im folgenden Beispiel wird eine benutzerdefinierte Kachel mit dem Namen "Contoso-Portal" verwendet, um auf die SharePoint-Intranetwebsite einer Organisation zuzugreifen. 
  
![App-Startfeld](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Hinzufügen einer benutzerdefinierten Kachel zum App-Startfeld

1. Melden Sie sich beim Admin Center als globaler Administrator an, wechseln Sie zu **Einstellungen** Org Einstellungen , und wählen Sie die Registerkarte  >   **Organisationsprofil** aus.
    
2. Wählen Sie **auf der** Registerkarte Organisationsprofil die Option **Benutzerdefinierte App-Startfeldkacheln aus.**
  
3. Wählen **Sie Hinzufügen einer benutzerdefinierten Kachel aus.** 
  
4. Geben Sie einen **Kachelnamen** für die neue Kachel ein. Der Name wird in der Kachel angezeigt. 
    
5. Geben Sie eine **URL der Website** für die Kachel ein. Dies ist der Ort, an dem Ihre Benutzer wechseln sollen, wenn sie die Kachel im App-Startfeld auswählen. Verwenden Sie HTTPS in der URL.

    > [!TIP]
    > Wenn Sie eine Kachel für eine SharePoint-Website erstellen, navigieren Sie zu dieser Website, kopieren Sie die URL, und fügen Sie diese hier ein. Die URL Ihrer Standardteamwebsite sieht wie die folgende aus: `https://<company_name>.sharepoint.com` 
  
6. Geben Sie eine **URL des Bilds für** die Kachel ein. Das Bild wird auf der Seite "Meine Apps" und im App-Startfeld angezeigt.

    > [!TIP]
    > Das Bild sollte 60 x 60 Pixel groß sein und für alle Benutzer in Ihrer Organisation verfügbar sein, ohne dass eine Authentifizierung erforderlich ist.

7. Geben Sie eine **Beschreibung** für die Kachel ein. Dies wird angezeigt, wenn Sie die Kachel auf der Seite Meine Apps auswählen und **App-Details auswählen.** 
  
8. Wählen **Sie Änderungen speichern aus,** um die benutzerdefinierte Kachel zu erstellen. 
    
    Ihre benutzerdefinierte Kachel wird jetzt im App-Startfeld auf der Registerkarte **Alle** für Sie und Ihre Benutzer angezeigt. 

    > [!NOTE]
    > Wenn die in den vorstehenden Schritten erstellte benutzerdefinierte Kachel nicht angezeigt wird, vergewissern Sie sich, dass Ihnen ein Exchange Online-Postfach zugewiesen wurde und Sie sich bei Ihrem Postfach mindestens einmal angemeldet haben. Diese Schritte sind für benutzerdefinierte Kacheln in Microsoft 365. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. Wechseln Sie im Admin Center zur Registerkarte **Einstellungen**  >  **Organisation Einstellungen**  >  **Organisationsprofil.**
    
2. Wählen Sie **auf der** Seite Organisationsprofil neben **Benutzerdefinierte Kacheln für Ihre Organisation** hinzufügen die Option Bearbeiten **aus.**

3. Aktualisieren Sie die Felder **Kachelname**, **URL**, **Beschreibung** oder **Bild-URL** für die benutzerdefinierte Kachel (siehe [Hinzufügen einer benutzerdefinierten Kachel zum App-Startfeld](#add-a-custom-tile-to-the-app-launcher)).
    
4. Wählen **Sie Update** schließen \> **aus.** 
    
Wählen Sie zum Löschen  einer benutzerdefinierten Kachel im Fenster Benutzerdefinierte Kacheln die Kachel aus, wählen Sie **Kachel entfernen**  >  **Löschen aus.** 
  
## <a name="next-steps"></a>Nächste Schritte

Zusätzlich zum Hinzufügen von Kacheln zum App-Startfeld können Sie der Navigationsleiste App-Startfeldkacheln hinzufügen[(weitere Informationen).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985) Informationen zum Anpassen des Erscheinungsbilds Microsoft 365 der Marke Ihrer Organisation finden Sie unter [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).

## <a name="related-content"></a>Verwandte Inhalte

[Anheften von Apps an das App-Startfeld](pin-apps-to-app-launcher.md) Ihrer Benutzer (Artikel)\
[Aktualisieren Sie Microsoft 365 für Geschäftsbenutzer auf den](../setup/upgrade-users-to-latest-office-client.md) neuesten Office (Artikel)\
[Verwalten von Add-Ins im Admin Center](../manage/manage-addins-in-the-admin-center.md) (Artikel)
