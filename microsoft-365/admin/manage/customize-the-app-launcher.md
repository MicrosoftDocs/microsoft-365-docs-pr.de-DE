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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: Erstellen Sie Schnelllinks zu Ihren E-Mails, Dokumenten, Apps, SharePoint Websites, externen Websites und anderen Ressourcen, indem Sie dem App-Startfeld benutzerdefinierte Kacheln hinzufügen.
ms.openlocfilehash: 0f4141d08811847e8e27cf35975cfa6c6b1b1192
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393679"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="0c89a-103">Hinzufügen von benutzerdefinierten Kacheln zum App-Startfeld</span><span class="sxs-lookup"><span data-stu-id="0c89a-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="0c89a-104">In Microsoft 365 können Sie schnell und einfach mithilfe des App-Startfelds zu Ihren E-Mails, Kalendern, Dokumenten und Apps gelangen ([weitere Informationen).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)</span><span class="sxs-lookup"><span data-stu-id="0c89a-104">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="0c89a-105">Hierbei handelt es sich um Apps, die Sie mit Microsoft 365 erhalten, sowie um benutzerdefinierte Apps, die Sie aus dem [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) oder [Azure AD](/previous-versions/office/office-365-api/)hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0c89a-105">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](/previous-versions/office/office-365-api/).</span></span>
  
<span data-ttu-id="0c89a-p102">Sie können dem App-Startfeld auch eigene benutzerdefinierte Kacheln hinzufügen, die auf SharePoint-Websites, externe Websites, Legacy-Apps usw. verweisen. Die benutzerdefinierte Kachel wird unter den Apps **Alle** des App-Startfelds angezeigt. Sie können sie aber an die **Start**-Apps anheften und Ihre Benutzer anweisen, ebenso zu verfahren. Auf diese Weise sind die relevanten Websites, Apps und Ressourcen für Ihre Arbeit leicht zu finden. Im folgenden Beispiel wird eine benutzerdefinierte Kachel mit dem Namen "Contoso-Portal" verwendet, um auf die SharePoint-Intranetwebsite einer Organisation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="0c89a-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![App-Startfeld](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="0c89a-111">Hinzufügen einer benutzerdefinierten Kachel zum App-Startfeld</span><span class="sxs-lookup"><span data-stu-id="0c89a-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="0c89a-112">Melden Sie sich beim Admin Center als globaler Administrator an, wechseln Sie zu **Einstellungen**  >  **Organisations-Einstellungen,** und wählen Sie die Registerkarte **"Organisationsprofil"** aus.</span><span class="sxs-lookup"><span data-stu-id="0c89a-112">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="0c89a-113">Wählen Sie auf der Registerkarte **"Organisationsprofil"** kacheln für **das benutzerdefinierte App-Startfeld aus.**</span><span class="sxs-lookup"><span data-stu-id="0c89a-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="0c89a-114">Wählen Sie **eine benutzerdefinierte Kachel hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="0c89a-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="0c89a-p103">Geben Sie einen **Kachelnamen** für die neue Kachel ein. Der Name wird in der Kachel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c89a-p103">Enter a **Tile name** for the new tile. The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="0c89a-117">Geben Sie eine **URL der Website** für die Kachel ein.</span><span class="sxs-lookup"><span data-stu-id="0c89a-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="0c89a-118">Dies ist der Speicherort, an den Ihre Benutzer gehen sollen, wenn sie die Kachel im App-Startfeld auswählen.</span><span class="sxs-lookup"><span data-stu-id="0c89a-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="0c89a-119">Verwenden Sie HTTPS in der URL.</span><span class="sxs-lookup"><span data-stu-id="0c89a-119">Use HTTPS in the URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="0c89a-120">Wenn Sie eine Kachel für eine SharePoint-Website erstellen, navigieren Sie zu dieser Website, kopieren Sie die URL, und fügen Sie diese hier ein.</span><span class="sxs-lookup"><span data-stu-id="0c89a-120">If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="0c89a-121">Die URL Ihrer Standardteamwebsite sieht wie folgt aus: `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="0c89a-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="0c89a-122">Geben Sie eine **URL des Bilds** für die Kachel ein.</span><span class="sxs-lookup"><span data-stu-id="0c89a-122">Enter a **URL of the image** for the tile.</span></span> <span data-ttu-id="0c89a-123">Das Bild wird auf der Seite "Meine Apps" und im App-Startfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c89a-123">The image appears on the My apps page and app launcher.</span></span>

    > [!TIP]
    > <span data-ttu-id="0c89a-124">Das Bild sollte 60 x 60 Pixel groß sein und für alle Benutzer in Ihrer Organisation verfügbar sein, ohne dass eine Authentifizierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0c89a-124">The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="0c89a-125">Geben Sie eine **Beschreibung** für die Kachel ein.</span><span class="sxs-lookup"><span data-stu-id="0c89a-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="0c89a-126">Dies wird angezeigt, wenn Sie die Kachel auf der Seite "Meine Apps" auswählen und **App-Details** auswählen.</span><span class="sxs-lookup"><span data-stu-id="0c89a-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="0c89a-127">Wählen Sie **"Änderungen speichern"** aus, um die benutzerdefinierte Kachel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c89a-127">Select **Save changes** to create the custom tile.</span></span> 
    
    <span data-ttu-id="0c89a-128">Ihre benutzerdefinierte Kachel wird jetzt im App-Startfeld auf der Registerkarte **Alle** für Sie und Ihre Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c89a-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="0c89a-129">Wenn die in den vorstehenden Schritten erstellte benutzerdefinierte Kachel nicht angezeigt wird, vergewissern Sie sich, dass Ihnen ein Exchange Online-Postfach zugewiesen wurde und Sie sich bei Ihrem Postfach mindestens einmal angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="0c89a-129">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="0c89a-130">Diese Schritte sind für benutzerdefinierte Kacheln in Microsoft 365 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c89a-130">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="0c89a-131">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="0c89a-131">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="0c89a-132">Wechseln Sie im Admin Center zur Registerkarte **Einstellungen**  >  **Organisationsprofil Einstellungen**  >  **Organisation.**</span><span class="sxs-lookup"><span data-stu-id="0c89a-132">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="0c89a-133">Wählen Sie auf der Profilseite **"Organisation"** neben   **"Benutzerdefinierte Kacheln für Ihre Organisation hinzufügen"** die Option **"Bearbeiten"** aus.</span><span class="sxs-lookup"><span data-stu-id="0c89a-133">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="0c89a-134">Aktualisieren Sie die Felder **Kachelname**, **URL**, **Beschreibung** oder **Bild-URL** für die benutzerdefinierte Kachel (siehe [Hinzufügen einer benutzerdefinierten Kachel zum App-Startfeld](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="0c89a-134">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="0c89a-135">Wählen Sie **"Update** \> **schließen" aus.**</span><span class="sxs-lookup"><span data-stu-id="0c89a-135">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="0c89a-136">Um eine benutzerdefinierte Kachel zu löschen, wählen Sie im Fenster **"Benutzerdefinierte Kacheln"** die Kachel aus, und wählen Sie **"Kachel**  >  **löschen"** aus.</span><span class="sxs-lookup"><span data-stu-id="0c89a-136">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="0c89a-137">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0c89a-137">Next steps</span></span>

<span data-ttu-id="0c89a-138">Zusätzlich zum Hinzufügen von Kacheln zum App-Startfeld können Sie der Navigationsleiste Kacheln für das App-Startprogramm hinzufügen ([weitere Informationen).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)</span><span class="sxs-lookup"><span data-stu-id="0c89a-138">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="0c89a-139">Informationen zum Anpassen des Erscheinungsbilds von Microsoft 365 an die Marke Ihrer Organisation finden Sie unter [Anpassen des Microsoft 365 Designs.](../setup/customize-your-organization-theme.md)</span><span class="sxs-lookup"><span data-stu-id="0c89a-139">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="0c89a-140">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="0c89a-140">Related content</span></span>

<span data-ttu-id="0c89a-141">[Anheften von Apps an das App-Startfeld Ihrer Benutzer](pin-apps-to-app-launcher.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="0c89a-141">[Pin apps to your users' app launcher](pin-apps-to-app-launcher.md) (article)</span></span>\
<span data-ttu-id="0c89a-142">[Aktualisieren Sie Ihre Microsoft 365 für Geschäftsbenutzer auf den neuesten Office-Client](../setup/upgrade-users-to-latest-office-client.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="0c89a-142">[Upgrade your Microsoft 365 for business users to the latest Office client](../setup/upgrade-users-to-latest-office-client.md) (article)</span></span>\
<span data-ttu-id="0c89a-143">[Verwalten von Add-Ins im Admin Center](../manage/manage-addins-in-the-admin-center.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="0c89a-143">[Manage add-ins in the admin center](../manage/manage-addins-in-the-admin-center.md) (article)</span></span>
