---
title: Verwalten von automatischen Ordnerausschlüssen
description: Fügen Sie Automatisierungsordnerausschlüsse hinzu, um die Dateien zu steuern, die von einer automatisierten Untersuchung ausgeschlossen sind.
keywords: Verwalten, Automatisierung, Ausschluss, blockieren, sauber, bösartig
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
ms.openlocfilehash: 05c103cba051c7d5e7f45e5dd3feb288013ee367
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454817"
---
# <a name="manage-automation-folder-exclusions"></a><span data-ttu-id="17683-104">Verwalten von automatischen Ordnerausschlüssen</span><span class="sxs-lookup"><span data-stu-id="17683-104">Manage automation folder exclusions</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="17683-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="17683-105">**Applies to:**</span></span>
- [<span data-ttu-id="17683-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="17683-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="17683-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17683-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="17683-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="17683-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="17683-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="17683-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

<span data-ttu-id="17683-110">Mit Automatisierungsordnerausschlüssen können Sie Ordner angeben, die von der automatischen Untersuchung übersprungen werden.</span><span class="sxs-lookup"><span data-stu-id="17683-110">Automation folder exclusions allow you to specify folders that the Automated investigation will skip.</span></span> 

<span data-ttu-id="17683-111">Sie können die folgenden Attribute zu dem Ordner steuern, der übersprungen werden soll:</span><span class="sxs-lookup"><span data-stu-id="17683-111">You can control the following attributes about the folder that you'd like to be skipped:</span></span>
- <span data-ttu-id="17683-112">Ordner</span><span class="sxs-lookup"><span data-stu-id="17683-112">Folders</span></span> 
- <span data-ttu-id="17683-113">Erweiterungen der Dateien</span><span class="sxs-lookup"><span data-stu-id="17683-113">Extensions of the files</span></span>
- <span data-ttu-id="17683-114">Dateinamen</span><span class="sxs-lookup"><span data-stu-id="17683-114">File names</span></span>


<span data-ttu-id="17683-115">**Ordner**</span><span class="sxs-lookup"><span data-stu-id="17683-115">**Folders**</span></span><br>
<span data-ttu-id="17683-116">Sie können einen Ordner und seine Unterordner angeben, die übersprungen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="17683-116">You can specify a folder and its subfolders to be skipped.</span></span> 


>[!NOTE]
><span data-ttu-id="17683-117">Derzeit wird die Verwendung von Platzhaltern als Möglichkeit zum Ausschließen von Dateien in einem Verzeichnis noch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="17683-117">At this time, use of wild cards as a way to exclude files under a directory is not yet supported.</span></span> 


<span data-ttu-id="17683-118">**Erweiterungen**</span><span class="sxs-lookup"><span data-stu-id="17683-118">**Extensions**</span></span><br>
<span data-ttu-id="17683-119">Sie können die auszuschließenden Erweiterungen in einem bestimmten Verzeichnis angeben.</span><span class="sxs-lookup"><span data-stu-id="17683-119">You can specify the extensions to exclude in a specific directory.</span></span> <span data-ttu-id="17683-120">Die Erweiterungen sind eine Möglichkeit, um zu verhindern, dass ein Angreifer einen ausgeschlossenen Ordner verwendet, um einen Exploit auszublenden.</span><span class="sxs-lookup"><span data-stu-id="17683-120">The extensions are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="17683-121">Die Erweiterungen definieren explizit, welche Dateien ignoriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="17683-121">The extensions explicitly define which files to ignore.</span></span> 

<span data-ttu-id="17683-122">**Dateinamen**</span><span class="sxs-lookup"><span data-stu-id="17683-122">**File names**</span></span><br>
<span data-ttu-id="17683-123">Sie können die Dateinamen angeben, die in einem bestimmten Verzeichnis ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="17683-123">You can specify the file names that you want to be excluded in a specific directory.</span></span> <span data-ttu-id="17683-124">Die Namen sind eine Möglichkeit, um zu verhindern, dass ein Angreifer einen ausgeschlossenen Ordner verwendet, um einen Exploit auszublenden.</span><span class="sxs-lookup"><span data-stu-id="17683-124">The names are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="17683-125">Die Namen definieren explizit, welche Dateien ignoriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="17683-125">The names explicitly define which files to ignore.</span></span> 



## <a name="add-an-automation-folder-exclusion"></a><span data-ttu-id="17683-126">Hinzufügen eines Automatisierungsordnerausschlusses</span><span class="sxs-lookup"><span data-stu-id="17683-126">Add an automation folder exclusion</span></span>
1. <span data-ttu-id="17683-127">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Ordnerausschlüsse** für die Automatisierung von  >  **Endpunktregeln**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="17683-127">In the navigation pane, select **Settings** > **Endpoints** > **Rules** > **Automation folder exclusions**.</span></span>  

2. <span data-ttu-id="17683-128">Klicken Sie auf **"Neuer Ordnerausschluss".**</span><span class="sxs-lookup"><span data-stu-id="17683-128">Click **New folder exclusion**.</span></span>  

3. <span data-ttu-id="17683-129">Geben Sie die Ordnerdetails ein:</span><span class="sxs-lookup"><span data-stu-id="17683-129">Enter the folder details:</span></span>

    - <span data-ttu-id="17683-130">Ordner</span><span class="sxs-lookup"><span data-stu-id="17683-130">Folder</span></span>
    - <span data-ttu-id="17683-131">Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="17683-131">Extensions</span></span>
    - <span data-ttu-id="17683-132">Dateinamen</span><span class="sxs-lookup"><span data-stu-id="17683-132">File names</span></span>
    - <span data-ttu-id="17683-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17683-133">Description</span></span>

4. <span data-ttu-id="17683-134">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="17683-134">Click **Save**.</span></span>

>[!NOTE]
> <span data-ttu-id="17683-135">Live Response-Befehle zum Sammeln oder Untersuchen ausgeschlossener Dateien schlagen mit der Fehlermeldung fehl: "Datei wird ausgeschlossen".</span><span class="sxs-lookup"><span data-stu-id="17683-135">Live Response commands to collect or examine excluded files will fail with error: "File is excluded".</span></span> <span data-ttu-id="17683-136">Darüber hinaus ignorieren automatisierte Untersuchungen die ausgeschlossenen Elemente.</span><span class="sxs-lookup"><span data-stu-id="17683-136">In addition, automated investigations will ignore the excluded items.</span></span>

## <a name="edit-an-automation-folder-exclusion"></a><span data-ttu-id="17683-137">Bearbeiten eines Automatisierungsordnerausschlusses</span><span class="sxs-lookup"><span data-stu-id="17683-137">Edit an automation folder exclusion</span></span> 
1. <span data-ttu-id="17683-138">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Ordnerausschlüsse** für die Automatisierung von  >  **Endpunktregeln**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="17683-138">In the navigation pane, select **Settings** > **Endpoints** > **Rules** > **Automation folder exclusions**.</span></span> 

2. <span data-ttu-id="17683-139">Klicken Sie auf **"Bearbeiten"** für den Ordnerausschluss.</span><span class="sxs-lookup"><span data-stu-id="17683-139">Click **Edit** on the folder exclusion.</span></span>  

3. <span data-ttu-id="17683-140">Aktualisieren Sie die Details der Regel, und klicken Sie auf **"Speichern".**</span><span class="sxs-lookup"><span data-stu-id="17683-140">Update the details of the rule and click **Save**.</span></span>

## <a name="remove-an-automation-folder-exclusion"></a><span data-ttu-id="17683-141">Entfernen eines Automatisierungsordnerausschlusses</span><span class="sxs-lookup"><span data-stu-id="17683-141">Remove an automation folder exclusion</span></span> 
1. <span data-ttu-id="17683-142">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Ordnerausschlüsse** für die Automatisierung von  >  **Endpunktregeln**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="17683-142">In the navigation pane, select **Settings** > **Endpoints** > **Rules** > **Automation folder exclusions**.</span></span>  
2. <span data-ttu-id="17683-143">Klicken Sie auf **"Ausschluss entfernen".**</span><span class="sxs-lookup"><span data-stu-id="17683-143">Click **Remove exclusion**.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="17683-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="17683-144">Related topics</span></span>
- [<span data-ttu-id="17683-145">Verwalten von zugelassenen/blockierten Automatisierungslisten</span><span class="sxs-lookup"><span data-stu-id="17683-145">Manage automation allowed/blocked lists</span></span>](manage-indicators.md)
- [<span data-ttu-id="17683-146">Verwalten von automatischen Dateiuploads</span><span class="sxs-lookup"><span data-stu-id="17683-146">Manage automation file uploads</span></span>](manage-automation-file-uploads.md)
