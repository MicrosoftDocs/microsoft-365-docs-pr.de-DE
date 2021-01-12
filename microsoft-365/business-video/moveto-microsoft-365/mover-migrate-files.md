---
title: 'Migrieren von Google-Dateien zu Microsoft 365 Business '
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie Mithilfe von Mover Google-Dateien zu Microsoft 365 Business migrieren.
ms.openlocfilehash: a6f9dbf7803cb552c23b6c6abb13d13d6f3eda5d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794639"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="8056b-103">Migrieren von Google-Dateien zu Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="8056b-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="8056b-104">Wenn Sie zu Microsoft 365 Business wechseln, sollten Sie Ihre Dateien von Google Drive migrieren.</span><span class="sxs-lookup"><span data-stu-id="8056b-104">When you move to Microsoft 365 for business, you’ll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="8056b-105">Sie können die Mover-App verwenden, um Dateien von persönlichen und freigegebenen Laufwerken zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="8056b-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="8056b-106">Weitere Informationen finden Sie unter [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span><span class="sxs-lookup"><span data-stu-id="8056b-106">For more information, see [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span></span>

> [!NOTE]
> <span data-ttu-id="8056b-107">Mover erstellt eine Kopie der Dateien und verschiebt die Kopien nach Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="8056b-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="8056b-108">Die Originaldateien bleiben auch in Google Drives.</span><span class="sxs-lookup"><span data-stu-id="8056b-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="8056b-109">Vor der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="8056b-109">Before you start</span></span>

<span data-ttu-id="8056b-110">Alle Benutzer sollten sich bei Microsoft 365 Business angemeldet und OneDrive for Business eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="8056b-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="8056b-111">Wechseln Sie dazu zu [office.com](https://office.com), melden Sie sich mit Ihren Microsft 365 #A0 an, und wählen Sie dann OneDrive aus.</span><span class="sxs-lookup"><span data-stu-id="8056b-111">To do this, go to [office.com](https://office.com), sign in with you Microsft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="8056b-112">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="8056b-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="8056b-113">Installieren von Mover</span><span class="sxs-lookup"><span data-stu-id="8056b-113">Install Mover</span></span>

1. <span data-ttu-id="8056b-114">Melden Sie sich bei Ihrer Google Workspace-Verwaltungskonsole [unter admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="8056b-114">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="8056b-115">Choose **Apps**, **Google Workspace Marketplace apps**, then Add app to Domain Install **list**.</span><span class="sxs-lookup"><span data-stu-id="8056b-115">Choose **Apps**, **Google Workspace Marketplace apps**, Then **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="8056b-116">Suchen Sie nach Mover, und wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="8056b-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="8056b-117">Choose **Domain Install**, then **Continue**.</span><span class="sxs-lookup"><span data-stu-id="8056b-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="8056b-118">Überprüfen Sie die Berechtigungen, aktivieren Sie das Kontrollkästchen, um den Bedingungen zu zustimmen, und wählen Sie dann **"Zulassen",**"Weiter" und dann "Fertig" **aus.**</span><span class="sxs-lookup"><span data-stu-id="8056b-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="8056b-119">Erstellen von Connectors und Ausführen der Migration</span><span class="sxs-lookup"><span data-stu-id="8056b-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="8056b-120">Zurück zu **Google Workspace Marketplace-Apps.**</span><span class="sxs-lookup"><span data-stu-id="8056b-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="8056b-121">Aktualisieren Sie Ihren Browser, und wählen Sie die **Mover-App** aus.</span><span class="sxs-lookup"><span data-stu-id="8056b-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="8056b-122">Scrollen Sie nach unten, und wählen Sie den universellen Navigationslink aus.</span><span class="sxs-lookup"><span data-stu-id="8056b-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="8056b-123">Wählen **Sie "Neuen Connector autorisieren"** aus, **suchen Sie nach G Suite (Administrator)** und wählen Sie **"Autorisieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="8056b-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="8056b-124">Ändern Sie **den Anzeigenamen,** wenn Sie möchten, und wählen Sie **"Autorisieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="8056b-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="8056b-125">Wählen Sie ein Google-Administratorkonto aus, überprüfen Sie die Berechtigungen, und wählen Sie dann **"Zulassen" aus.**</span><span class="sxs-lookup"><span data-stu-id="8056b-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="8056b-126">Mover zeigt die Anzahl der ermittelten Teamlaufwerke und Benutzerlaufwerke an.</span><span class="sxs-lookup"><span data-stu-id="8056b-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="8056b-127">Wählen **Sie unter Ziel auswählen** die Option **"Neuen Connector autorisieren"** aus, suchen Sie nach Office **365,** und wählen Sie **"Autorisieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="8056b-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="8056b-128">Um der Mover-App in Ihrem Azure Active Directory Berechtigungen zu erteilen, navigieren Sie zu [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span><span class="sxs-lookup"><span data-stu-id="8056b-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="8056b-129">Wählen **Sie Office 365 Mover**, **Berechtigungen,** **Administratorzuwilligung für Ihr Unternehmen.**</span><span class="sxs-lookup"><span data-stu-id="8056b-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="8056b-130">Wählen Sie Ihr Konto aus, überprüfen Sie die Berechtigungen, und wählen Sie **"Annehmen" aus.**</span><span class="sxs-lookup"><span data-stu-id="8056b-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="8056b-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span><span class="sxs-lookup"><span data-stu-id="8056b-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="8056b-132">Kehren Sie zur Mover-App zurück, ändern Sie den **Anzeigenamen,** wählen Sie bei Auswahl von "Autorisieren" **und** dann ein Microsoft-Administratorkonto aus.</span><span class="sxs-lookup"><span data-stu-id="8056b-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="8056b-133">Mover informiert Sie über die Anzahl von SharePoint Online-Websites (oder SPO)-Websites und Benutzern, die es ermittelt hat.</span><span class="sxs-lookup"><span data-stu-id="8056b-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="8056b-134">Choose **Continue Migration Setup**, select Add **Users**, then Automatically Discover and **Add Users**.</span><span class="sxs-lookup"><span data-stu-id="8056b-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="8056b-135">Die Mover-App versucht, Laufwerke aus dem Quellpfad in Google dem Zielpfad in Microsoft 365 zu zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="8056b-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="8056b-136">Wenn ein Laufwerk nicht automatisch zuordnungiert wird, fügen Sie den Zielpfad zu einer CSV-Datei hinzu, die wir später zum Migrieren des freigegebenen Laufwerks zu einer SharePoint-Dokumentbibliothek verwenden.</span><span class="sxs-lookup"><span data-stu-id="8056b-136">If a drive doesn’t map automatically, add its destination path to a CSV file, which we’ll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="8056b-137">In diesem Fall haben wir eine SharePoint-Website namens "Migrierte Dateien" hinzugefügt und die URL für die Dokumentseite notiert.</span><span class="sxs-lookup"><span data-stu-id="8056b-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="8056b-138">Anschließend haben wir eine CSV-Datei mit dem Format "Quellpfad", "Zielpfad" und "Tags" erstellt.</span><span class="sxs-lookup"><span data-stu-id="8056b-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="8056b-139">Weitere Informationen finden Sie [unter aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span><span class="sxs-lookup"><span data-stu-id="8056b-139">For details see [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="8056b-140">Entfernen Sie beim Hinzufügen der Zielpfad-URL z. B. alles nach freigegebenen Dokumenten. Diese vollständige URL funktioniert beispielsweise nicht: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="8056b-140">When adding the Destination Path URL, remove everything after Shared Documents for example For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="8056b-141">Ändern Sie sie zu `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="8056b-141">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="8056b-142">Sobald Ihre CSV-Datei bereit ist, wählen **Sie "Migrationsaktionen",** **"Zur Migration** hinzufügen" und **"Datei zum Hochladen" aus.**</span><span class="sxs-lookup"><span data-stu-id="8056b-142">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="8056b-143">Navigieren Sie zu Ihrer CSV-Datei, wählen Sie sie aus, und wählen Sie dann **Öffnen aus.**</span><span class="sxs-lookup"><span data-stu-id="8056b-143">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="8056b-144">Wählen Sie die Benutzerlaufwerke aus, deren Dateien Sie migrieren möchten, und wählen Sie dann **"Migration von Benutzern starten" aus.**</span><span class="sxs-lookup"><span data-stu-id="8056b-144">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="8056b-145">Überprüfen Sie die Migrationsinformationen, wählen Sie aus, wann die Migration gestartet werden soll, stimmen Sie den Allgemeinen Geschäftsbedingungen **zu,** und wählen Sie dann **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="8056b-145">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="8056b-146">Die Mover-App informiert Sie, wenn der Migrationsprozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8056b-146">The Mover app will inform you when the migration process is complete.</span></span>