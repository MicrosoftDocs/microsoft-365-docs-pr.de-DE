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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Erstellen Sie schnell Links zu Ihren e-Mails, Dokumenten, apps, SharePoint-Websites, externen Websites und anderen Ressourcen durch Hinzufügen von benutzerdefinierten Kacheln zum App-Startfeld. '
ms.openlocfilehash: 65c8da7aa0cdb68f4bf32a52b21140413a38a69a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361980"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="6f6ad-103">Hinzufügen von benutzerdefinierten Kacheln zum App-Startfeld</span><span class="sxs-lookup"><span data-stu-id="6f6ad-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="6f6ad-p101">[] In Office 365 können Sie mithilfe des Office 365-App-Startfelds schnell und einfach zu Ihren E-Mails, Kalendern, Dokumenten und Apps gelangen ([weitere Informationen](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). Dabei handelt es sich um Apps, die in Office 365 enthalten sind, sowie benutzerdefinierte Apps, die Sie aus dem [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) oder [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-p101">In Office 365, you can quickly and easily get to your email, calendars, documents, and apps using the Office 365 app launcher ([learn more](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). These are apps you get with Office 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="6f6ad-p102">Sie können dem App-Startfeld auch eigene benutzerdefinierte Kacheln hinzufügen, die auf SharePoint-Websites, externe Websites, Legacy-Apps usw. verweisen. Die benutzerdefinierte Kachel wird unter den Apps **Alle** des App-Startfelds angezeigt. Sie können sie aber an die **Start**-Apps anheften und Ihre Benutzer anweisen, ebenso zu verfahren. Auf diese Weise sind die relevanten Websites, Apps und Ressourcen für Ihre Arbeit leicht zu finden. Im folgenden Beispiel wird eine benutzerdefinierte Kachel mit dem Namen "Contoso-Portal" verwendet, um auf die SharePoint-Intranetwebsite einer Organisation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![App-Startfeld für Office 365](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="6f6ad-111">Hinzufügen einer benutzerdefinierten Kachel zum App-Startfeld</span><span class="sxs-lookup"><span data-stu-id="6f6ad-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="6f6ad-112">Wechseln Sie im Admin Center zu den **Einstellungs** > **Einstellungen** , und wählen Sie Registerkarte **Organisationsprofil** aus.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-112">In the admin center, go to the **Settings** > **Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="6f6ad-113">Klicken Sie auf der Registerkarte **Organisationsprofil** auf **benutzerdefinierte Kacheln für App-Startfelder**.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="6f6ad-114">Wählen Sie **benutzerdefinierte Kachel hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="6f6ad-115">Geben Sie einen **Kachelnamen** für die neue Kachel ein.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="6f6ad-116">Der Name wird in der Kachel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="6f6ad-117">Geben Sie eine **URL der Website** für die Kachel ein.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="6f6ad-118">Dies ist der Ort, an dem Ihre Benutzer wechseln sollen, wenn Sie die Kachel auf dem App-Startfeld auswählen.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="6f6ad-119">Verwenden Sie https in der URL.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="6f6ad-120">Tipp: Wenn Sie eine Kachel für eine SharePoint-Website erstellen, navigieren Sie zu dieser Website, kopieren Sie die URL, und fügen Sie Sie hier ein.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="6f6ad-121">Die URL der Standard-Teamwebsite sieht wie folgt aus:`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="6f6ad-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="6f6ad-122">Geben Sie eine **URL des Bilds** für die Kachel ein.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="6f6ad-123">Das Bild wird auf der Seite "Meine Apps" und im App-Startfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="6f6ad-124">Tipp: das Bild sollte 60x60 Pixel sein und für alle Benutzer in Ihrer Organisation verfügbar sein, ohne dass eine Authentifizierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="6f6ad-125">Geben Sie eine **Beschreibung** für die Kachel ein.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="6f6ad-126">Dies wird angezeigt, wenn Sie die Kachel auf der Seite "meine apps" auswählen und **App-Details**auswählen.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="6f6ad-127">Wählen Sie **Änderungen speichern** aus, um die benutzerdefinierte Kachel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="6f6ad-128">Ihre benutzerdefinierte Kachel wird jetzt im App-Startfeld auf der Registerkarte **Alle** für Sie und Ihre Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="6f6ad-129">Heraufstufen der Kachel auf den App-startstart</span><span class="sxs-lookup"><span data-stu-id="6f6ad-129">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="6f6ad-130">Wählen Sie das App-Startprogramm Symbol aus, und wählen Sie **alle apps**aus.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-130">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="6f6ad-131">Suchen Sie die neue Kachel für Ihre APP, wählen Sie die Auslassungspunkte aus, und wählen Sie **Pin to Launcher**aus.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-131">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="6f6ad-p108">Wenn die in den vorstehenden Schritten erstellte benutzerdefinierte Kachel nicht angezeigt wird, vergewissern Sie sich, dass Ihnen ein Exchange Online-Postfach zugewiesen wurde und Sie sich bei Ihrem Postfach mindestens einmal angemeldet haben. Diese Schritte sind für benutzerdefinierte Kacheln in Office 365 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-p108">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once. These steps are required for custom tiles in Office 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6f6ad-134">Sowohl Sie als auch Ihre Benutzer müssen diese Schritte ausführen, um benutzerdefinierte Kacheln von der Seite "Meine Apps" in das App-Startfeld heraufzustufen.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-134">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="6f6ad-135">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="6f6ad-135">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="6f6ad-136">Wechseln Sie im Admin Center zur Seite<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organisationsprofil</a> für **Einstellungen** > .</span><span class="sxs-lookup"><span data-stu-id="6f6ad-136">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organization profile</a> page.</span></span>
    
2. <span data-ttu-id="6f6ad-137">Klicken Sie auf der Seite **Organisationsprofil** neben **benutzerdefinierte Kacheln für Ihre Organisation hinzufügen**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-137">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="6f6ad-138">Aktualisieren Sie die Felder **Kachelname**, **URL**, **Beschreibung** oder **Bild-URL** für die benutzerdefinierte Kachel (siehe [Hinzufügen einer benutzerdefinierten Kachel zum App-Startfeld](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="6f6ad-138">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="6f6ad-139">Wählen Sie **Close** **Aktualisieren** \> aus.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-139">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="6f6ad-140">Wenn Sie eine benutzerdefinierte Kachel aus dem Fenster **benutzerdefinierte** Kacheln löschen möchten, wählen Sie die Kachel aus, und wählen Sie **Kachel** > **Löschung**entfernen aus.</span><span class="sxs-lookup"><span data-stu-id="6f6ad-140">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="6f6ad-141">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6f6ad-141">What's next?</span></span>

<span data-ttu-id="6f6ad-p109">Sie können nicht nur Kacheln zum App-Startfeld hinzufügen, sondern auch Kacheln im App-Startfeld zur Office 365-Navigationsleiste hinzufügen ([weitere Informationen](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). Informationen zum Anpassen des Aussehens und Verhaltens von Office 365 entsprechend dem Branding Ihrer Organisation finden Sie unter [Anpassen des Office 365-Designs](../setup/customize-your-organization-theme.md).</span><span class="sxs-lookup"><span data-stu-id="6f6ad-p109">In addition to adding tiles to the app launcher, you can add app launcher tiles to the Office 365 navigation bar ([learn more](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). To customize the look and feel of Office 365 to match your organization's brand, see [Customize the Office 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

