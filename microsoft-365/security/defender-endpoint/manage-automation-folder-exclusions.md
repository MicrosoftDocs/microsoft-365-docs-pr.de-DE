---
title: Verwalten von automatischen Ordnerausschlüssen
description: Fügen Sie Automatisierungsordnerausschlüsse hinzu, um die Dateien zu steuern, die von einer automatisierten Untersuchung ausgeschlossen sind.
keywords: verwalten, automatisieren, ausschließen, blockieren, sauber, bösartig
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
ms.openlocfilehash: 37a251acd3b7631cffffaf2eb76bf0f2b4954ee6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185837"
---
# <a name="manage-automation-folder-exclusions"></a><span data-ttu-id="50ca3-104">Verwalten von automatischen Ordnerausschlüssen</span><span class="sxs-lookup"><span data-stu-id="50ca3-104">Manage automation folder exclusions</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="50ca3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="50ca3-105">**Applies to:**</span></span>
- [<span data-ttu-id="50ca3-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="50ca3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="50ca3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50ca3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="50ca3-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="50ca3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="50ca3-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="50ca3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

<span data-ttu-id="50ca3-110">Mit Ausschlüssen für Automatisierungsordner können Sie Ordner angeben, die von der automatisierten Untersuchung übersprungen werden.</span><span class="sxs-lookup"><span data-stu-id="50ca3-110">Automation folder exclusions allow you to specify folders that the Automated investigation will skip.</span></span> 

<span data-ttu-id="50ca3-111">Sie können die folgenden Attribute für den Ordner steuern, den Sie überspringen möchten:</span><span class="sxs-lookup"><span data-stu-id="50ca3-111">You can control the following attributes about the folder that you'd like to be skipped:</span></span>
- <span data-ttu-id="50ca3-112">Ordner</span><span class="sxs-lookup"><span data-stu-id="50ca3-112">Folders</span></span> 
- <span data-ttu-id="50ca3-113">Erweiterungen der Dateien</span><span class="sxs-lookup"><span data-stu-id="50ca3-113">Extensions of the files</span></span>
- <span data-ttu-id="50ca3-114">Dateinamen</span><span class="sxs-lookup"><span data-stu-id="50ca3-114">File names</span></span>


<span data-ttu-id="50ca3-115">**Ordner**</span><span class="sxs-lookup"><span data-stu-id="50ca3-115">**Folders**</span></span><br>
<span data-ttu-id="50ca3-116">Sie können einen Ordner und dessen Unterordner angeben, die übersprungen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="50ca3-116">You can specify a folder and its subfolders to be skipped.</span></span> 


>[!NOTE]
><span data-ttu-id="50ca3-117">Derzeit wird die Verwendung von Platzhaltern zum Ausschließen von Dateien unter einem Verzeichnis noch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="50ca3-117">At this time, use of wild cards as a way to exclude files under a directory is not yet supported.</span></span> 


<span data-ttu-id="50ca3-118">**Erweiterungen**</span><span class="sxs-lookup"><span data-stu-id="50ca3-118">**Extensions**</span></span><br>
<span data-ttu-id="50ca3-119">Sie können die erweiterungen angeben, die in einem bestimmten Verzeichnis ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="50ca3-119">You can specify the extensions to exclude in a specific directory.</span></span> <span data-ttu-id="50ca3-120">Die Erweiterungen verhindern, dass ein Angreifer einen ausgeschlossenen Ordner verwendet, um einen Exploit auszublenden.</span><span class="sxs-lookup"><span data-stu-id="50ca3-120">The extensions are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="50ca3-121">Die Erweiterungen definieren explizit, welche Dateien ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="50ca3-121">The extensions explicitly define which files to ignore.</span></span> 

<span data-ttu-id="50ca3-122">**Dateinamen**</span><span class="sxs-lookup"><span data-stu-id="50ca3-122">**File names**</span></span><br>
<span data-ttu-id="50ca3-123">Sie können die Dateinamen angeben, die in einem bestimmten Verzeichnis ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="50ca3-123">You can specify the file names that you want to be excluded in a specific directory.</span></span> <span data-ttu-id="50ca3-124">Die Namen sind eine Möglichkeit, einen Angreifer daran zu hindern, einen ausgeschlossenen Ordner zum Ausblenden eines Exploits zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="50ca3-124">The names are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="50ca3-125">Die Namen definieren explizit, welche Dateien ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="50ca3-125">The names explicitly define which files to ignore.</span></span> 



## <a name="add-an-automation-folder-exclusion"></a><span data-ttu-id="50ca3-126">Hinzufügen eines Automatisierungsordnerausschlusses</span><span class="sxs-lookup"><span data-stu-id="50ca3-126">Add an automation folder exclusion</span></span>
1. <span data-ttu-id="50ca3-127">Wählen Sie im Navigationsbereich die **Option Einstellungen**  >  **Automatisierungsordnerausschlüsse aus.**</span><span class="sxs-lookup"><span data-stu-id="50ca3-127">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  

2. <span data-ttu-id="50ca3-128">Klicken Sie **auf Neuer Ordnerausschluss**.</span><span class="sxs-lookup"><span data-stu-id="50ca3-128">Click **New folder exclusion**.</span></span>  

3. <span data-ttu-id="50ca3-129">Geben Sie die Ordnerdetails ein:</span><span class="sxs-lookup"><span data-stu-id="50ca3-129">Enter the folder details:</span></span>

    - <span data-ttu-id="50ca3-130">Ordner</span><span class="sxs-lookup"><span data-stu-id="50ca3-130">Folder</span></span>
    - <span data-ttu-id="50ca3-131">Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="50ca3-131">Extensions</span></span>
    - <span data-ttu-id="50ca3-132">Dateinamen</span><span class="sxs-lookup"><span data-stu-id="50ca3-132">File names</span></span>
    - <span data-ttu-id="50ca3-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50ca3-133">Description</span></span>
    

4. <span data-ttu-id="50ca3-134">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="50ca3-134">Click **Save**.</span></span>

>[!NOTE]
> <span data-ttu-id="50ca3-135">Live Response-Befehle zum Sammeln oder Untersuchen ausgeschlossener Dateien führen zu einem Fehler: "Datei ist ausgeschlossen".</span><span class="sxs-lookup"><span data-stu-id="50ca3-135">Live Response commands to collect or examine excluded files will fail with error: "File is excluded".</span></span> <span data-ttu-id="50ca3-136">Darüber hinaus ignorieren automatisierte Untersuchungen die ausgeschlossenen Elemente.</span><span class="sxs-lookup"><span data-stu-id="50ca3-136">In addition, automated investigations will ignore the excluded items.</span></span>

## <a name="edit-an-automation-folder-exclusion"></a><span data-ttu-id="50ca3-137">Bearbeiten eines Automatisierungsordnerausschlusses</span><span class="sxs-lookup"><span data-stu-id="50ca3-137">Edit an automation folder exclusion</span></span> 
1. <span data-ttu-id="50ca3-138">Wählen Sie im Navigationsbereich die **Option Einstellungen**  >  **Automatisierungsordnerausschlüsse aus.**</span><span class="sxs-lookup"><span data-stu-id="50ca3-138">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span> 

2. <span data-ttu-id="50ca3-139">Klicken **Sie auf Bearbeiten** für den Ordnerausschluss.</span><span class="sxs-lookup"><span data-stu-id="50ca3-139">Click **Edit** on the folder exclusion.</span></span>  

3. <span data-ttu-id="50ca3-140">Aktualisieren Sie die Details der Regel, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="50ca3-140">Update the details of the rule and click **Save**.</span></span>

## <a name="remove-an-automation-folder-exclusion"></a><span data-ttu-id="50ca3-141">Entfernen eines Automatisierungsordnerausschlusses</span><span class="sxs-lookup"><span data-stu-id="50ca3-141">Remove an automation folder exclusion</span></span> 
1. <span data-ttu-id="50ca3-142">Wählen Sie im Navigationsbereich die **Option Einstellungen**  >  **Automatisierungsordnerausschlüsse aus.**</span><span class="sxs-lookup"><span data-stu-id="50ca3-142">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  
2. <span data-ttu-id="50ca3-143">Klicken **Sie auf Ausschluss entfernen**.</span><span class="sxs-lookup"><span data-stu-id="50ca3-143">Click **Remove exclusion**.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="50ca3-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="50ca3-144">Related topics</span></span>
- [<span data-ttu-id="50ca3-145">Verwalten von zulässigen/blockierten Automatisierungslisten</span><span class="sxs-lookup"><span data-stu-id="50ca3-145">Manage automation allowed/blocked lists</span></span>](manage-indicators.md)
- [<span data-ttu-id="50ca3-146">Verwalten von automatischen Dateiuploads</span><span class="sxs-lookup"><span data-stu-id="50ca3-146">Manage automation file uploads</span></span>](manage-automation-file-uploads.md)
