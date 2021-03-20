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
description: Erfahren Sie, wie Sie Google-Dateien mithilfe von Mover zu Microsoft 365 Business migrieren.
ms.openlocfilehash: 6feabff7e36e84f7dba56e74333648325cf43920
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913574"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="9431d-103">Migrieren von Google-Dateien zu Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="9431d-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="9431d-104">Wenn Sie zu Microsoft 365 Business wechseln, sollten Sie Ihre Dateien von Google Drive migrieren.</span><span class="sxs-lookup"><span data-stu-id="9431d-104">When you move to Microsoft 365 for business, you'll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="9431d-105">Sie können die Mover-App verwenden, um Dateien von persönlichen und freigegebenen Laufwerken zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="9431d-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="9431d-106">Weitere Informationen finden Sie unter [Mover Cloud Migration](/sharepointmigration/mover-plan-migration).</span><span class="sxs-lookup"><span data-stu-id="9431d-106">For more information, see [Mover Cloud Migration](/sharepointmigration/mover-plan-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="9431d-107">Mover erstellt eine Kopie der Dateien und verschiebt die Kopien nach Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="9431d-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="9431d-108">Die originalen Dateien bleiben auch in Google Drives erhalten.</span><span class="sxs-lookup"><span data-stu-id="9431d-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="9431d-109">Vor dem Start</span><span class="sxs-lookup"><span data-stu-id="9431d-109">Before you start</span></span>

<span data-ttu-id="9431d-110">Alle Benutzer sollten sich bei Microsoft 365 Business angemeldet und ihr OneDrive for Business eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="9431d-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="9431d-111">Wechseln Sie dazu zu [office.com](https://office.com), melden Sie sich mit Ihren Microsoft 365 #A0 an, und wählen Sie dann OneDrive aus.</span><span class="sxs-lookup"><span data-stu-id="9431d-111">To do this, go to [office.com](https://office.com), sign in with your Microsoft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="9431d-112">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="9431d-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="9431d-113">Installieren von Mover</span><span class="sxs-lookup"><span data-stu-id="9431d-113">Install Mover</span></span>

1. <span data-ttu-id="9431d-114">Melden Sie sich bei Ihrer Google Workspace Admin Console unter [admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="9431d-114">Sign in to your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="9431d-115">Wählen **Sie Apps** Google Workspace Marketplace  >  **apps** App zu  >  **Domäneninstallationsliste hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="9431d-115">Choose **Apps** > **Google Workspace Marketplace apps** > **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="9431d-116">Suchen Sie nach Mover, und wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="9431d-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="9431d-117">Wählen **Sie Domäneninstallation** aus, und fahren Sie **dann fort.**</span><span class="sxs-lookup"><span data-stu-id="9431d-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="9431d-118">Überprüfen Sie die Berechtigungen, aktivieren Sie das Kontrollkästchen, um den Bedingungen zu zustimmen, und wählen Sie **Dann Zulassen** aus, wählen Sie **Weiter** und dann **Fertig aus.**</span><span class="sxs-lookup"><span data-stu-id="9431d-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="9431d-119">Erstellen von Connectors und Ausführen der Migration</span><span class="sxs-lookup"><span data-stu-id="9431d-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="9431d-120">Kehren Sie zu **Google Workspace Marketplace-Apps zurück.**</span><span class="sxs-lookup"><span data-stu-id="9431d-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="9431d-121">Aktualisieren Sie Ihren Browser, und wählen Sie die **Mover-App** aus.</span><span class="sxs-lookup"><span data-stu-id="9431d-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="9431d-122">Scrollen Sie nach unten, und wählen Sie den universellen Navigationslink aus.</span><span class="sxs-lookup"><span data-stu-id="9431d-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="9431d-123">Wählen **Sie Neuen Connector autorisieren,** G Suite **(Admin)** suchen und **Autorisieren aus.**</span><span class="sxs-lookup"><span data-stu-id="9431d-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="9431d-124">Ändern Sie **den Anzeigenamen**, wenn Sie möchten, und wählen Sie **Dann Autorisieren aus.**</span><span class="sxs-lookup"><span data-stu-id="9431d-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="9431d-125">Wählen Sie ein Google-Administratorkonto aus, überprüfen Sie die Berechtigungen, und wählen Sie dann **Zulassen aus.**</span><span class="sxs-lookup"><span data-stu-id="9431d-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="9431d-126">Mover zeigt die Anzahl der gefundenen Teamlaufwerke und Benutzerlaufwerke an.</span><span class="sxs-lookup"><span data-stu-id="9431d-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="9431d-127">Wählen **Sie unter Ziel auswählen** die Option Neuen Connector **autorisieren** aus, suchen Sie nach Office **365,** und wählen Sie **Autorisieren aus.**</span><span class="sxs-lookup"><span data-stu-id="9431d-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="9431d-128">Um der Mover-App in Azure Active Directory Berechtigungen zu erteilen, navigieren Sie zu [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span><span class="sxs-lookup"><span data-stu-id="9431d-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="9431d-129">Wählen **Sie Office 365 Mover**, **Berechtigungen**, **Administratorzusend für Ihr Unternehmen erteilen aus.**</span><span class="sxs-lookup"><span data-stu-id="9431d-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="9431d-130">Wählen Sie Ihr Konto aus, überprüfen Sie die Berechtigungen, und wählen Sie **Akzeptieren aus.**</span><span class="sxs-lookup"><span data-stu-id="9431d-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="9431d-131">Wählen **Sie Eigenschaften** aus, und vergewissern Sie sich, dass die **Benutzerzuweisung erforderlich ist?** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9431d-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="9431d-132">Kehren Sie zur Mover-App zurück, ändern Sie den **Anzeigenamen**, wenn Sie möchten, wählen Sie **Autorisieren** aus, und wählen Sie dann ein Microsoft-Administratorkonto aus.</span><span class="sxs-lookup"><span data-stu-id="9431d-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="9431d-133">Mover informiert Sie über die Anzahl der gefundenen SharePoint Online-Websites (oder SPO-Websites) und -Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9431d-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="9431d-134">Wählen **Sie Setup für die Migration fortsetzen** aus, wählen Sie Benutzer **hinzufügen** und dann Benutzer automatisch ermitteln und **hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="9431d-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="9431d-135">Die Mover-App versucht, Laufwerke vom Quellpfad in Google dem Zielpfad in Microsoft 365 zu zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="9431d-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="9431d-136">Wenn ein Laufwerk nicht automatisch zuordnung wird, fügen Sie den Zielpfad zu einer CSV-Datei hinzu, die wir später zum Migrieren des freigegebenen Laufwerks zu einer SharePoint-Dokumentbibliothek verwenden.</span><span class="sxs-lookup"><span data-stu-id="9431d-136">If a drive doesn't map automatically, add its destination path to a CSV file, which we'll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="9431d-137">In diesem Fall haben wir eine SharePoint-Website namens Migrierte Dateien hinzugefügt und die URL für die Dokumentseite notiert.</span><span class="sxs-lookup"><span data-stu-id="9431d-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="9431d-138">Anschließend haben wir eine CSV-Datei mit dem Format Source Path, Destination Path und Tags erstellt.</span><span class="sxs-lookup"><span data-stu-id="9431d-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="9431d-139">Weitere Informationen finden Sie [unter aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).</span><span class="sxs-lookup"><span data-stu-id="9431d-139">For details see [aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="9431d-140">Entfernen Sie beim Hinzufügen der Zielpfad-URL alles nach freigegebenen Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="9431d-140">When adding the Destination Path URL, remove everything after Shared Documents.</span></span> <span data-ttu-id="9431d-141">Diese vollständige URL funktioniert beispielsweise nicht: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="9431d-141">For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="9431d-142">Ändern Sie sie zu `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="9431d-142">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="9431d-143">Sobald Ihre CSV-Datei bereit ist, wählen Sie **Migrationsaktionen**, **Migration hinzufügen**, Datei zum Hochladen **auswählen aus.**</span><span class="sxs-lookup"><span data-stu-id="9431d-143">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="9431d-144">Navigieren Sie zu Ihrer CSV-Datei, wählen Sie sie aus, und wählen Sie dann **Öffnen aus.**</span><span class="sxs-lookup"><span data-stu-id="9431d-144">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="9431d-145">Wählen Sie die Benutzerlaufwerke aus, deren Dateien Sie migrieren möchten, und wählen Sie **dann Migrieren von Benutzern starten aus.**</span><span class="sxs-lookup"><span data-stu-id="9431d-145">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="9431d-146">Überprüfen Sie die Migrationsinformationen, wählen Sie aus, wann die Migration gestartet werden soll, stimmen Sie den **Allgemeinen** Geschäftsbedingungen zu und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="9431d-146">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="9431d-147">Die Mover-App informiert Sie, wenn der Migrationsprozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9431d-147">The Mover app will inform you when the migration process is complete.</span></span>