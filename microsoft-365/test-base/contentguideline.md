---
title: Richtlinien für Testpakete
description: Überprüfen der Richtlinien für das Testpaket
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322758"
---
# <a name="test-package-guidelines"></a><span data-ttu-id="9c049-103">Richtlinien für Testpakete</span><span class="sxs-lookup"><span data-stu-id="9c049-103">Test package guidelines</span></span>

## <a name="1---script-referencing"></a><span data-ttu-id="9c049-104">1. Skriptreferenzierung</span><span class="sxs-lookup"><span data-stu-id="9c049-104">1.   Script referencing</span></span>

<span data-ttu-id="9c049-105">Wenn Sie eine .zip-Datei in das Portal hochladen, entpacken wir den gesamten Inhalt dieser Datei in einen Stammordner.</span><span class="sxs-lookup"><span data-stu-id="9c049-105">When you upload a .zip file to the portal, we unzip all the content of that file into a root folder.</span></span> <span data-ttu-id="9c049-106">Sie müssen keinen Code schreiben, um diesen anfänglichen Entzippenvorgang durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="9c049-106">You do not need to write any code to do this initial unzip operation.</span></span> <span data-ttu-id="9c049-107">Sie können auch auf eine beliebige Datei innerhalb des .zip verweisen, indem Sie den Pfad relativ zur hochgeladenen ZIP-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="9c049-107">You also can reference any file within the .zip by using the path relative to the zip file uploaded.</span></span>

<span data-ttu-id="9c049-108">Im folgenden Beispiel wird gezeigt, wie Sie über das Eingabefeld auf der Registerkarte "Aufgaben" auf Ihre Binärdateien/Skripts verweisen können. Der Text in Blau sollte ohne **Anführungszeichen** in das **Feld "Skriptpfad"** eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9c049-108">In the example below, we show how you can reference your binaries/scripts from the input field in the Tasks tab. The text in blue should be entered into the **Script path** field **without the quotation marks.**</span></span>

<span data-ttu-id="9c049-109">Es ist wichtig, dass Sie die Inhalte in Ihrer ZIP-Datei kennen, bevor Sie sie hochladen.</span><span class="sxs-lookup"><span data-stu-id="9c049-109">It is important you are aware of the content within your zip file before uploading it.</span></span> <span data-ttu-id="9c049-110">Beim Zippen eines Ordners erstellt Ihr lokaler Computer häufig einen Hauptordner unter der ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="9c049-110">Often when zipping a folder, your local machine will create a main folder underneath the zip file.</span></span> <span data-ttu-id="9c049-111">In diesem Fall ist der Verweis wie unten **fett** dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9c049-111">In this case, the referencing will be as shown in **bold** below:</span></span>

 <span data-ttu-id="9c049-112">**Contoso_App_Folder.zip**</span><span class="sxs-lookup"><span data-stu-id="9c049-112">**Contoso_App_Folder.zip**</span></span>
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - <span data-ttu-id="9c049-113">ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="9c049-113">ScriptX.ps1 – **“Contoso_App_Folder/ScriptX.ps1”**</span></span>
  - <span data-ttu-id="9c049-114">Script.ps1 – **"Contoso_App_Folder/folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="9c049-114">Script.ps1 – **“Contoso_App_Folder/folder1/script.ps1”**</span></span>

<span data-ttu-id="9c049-115">In anderen Fällen enthält Ihre ZIP-Datei möglicherweise Ihre Dateien oder Inhalte direkt darunter, d. h. keinen Ordner auf 2. Ebene:</span><span class="sxs-lookup"><span data-stu-id="9c049-115">Other times, your zip file may have your files or content right underneath it i.e. no 2nd-level folder:</span></span>

 <span data-ttu-id="9c049-116">**Zip_file_uploaded.zip**</span><span class="sxs-lookup"><span data-stu-id="9c049-116">**Zip_file_uploaded.zip**</span></span>
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="9c049-117">ScriptX.ps1 – **"ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="9c049-117">ScriptX.ps1 – **“ScriptX.ps1”**</span></span>
  - <span data-ttu-id="9c049-118">Script.ps1 – **"folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="9c049-118">Script.ps1 – **“folder1/script.ps1”**</span></span>
  
## <a name="2---script-execution"></a><span data-ttu-id="9c049-119">2. Skriptausführung</span><span class="sxs-lookup"><span data-stu-id="9c049-119">2.   Script execution</span></span>

<span data-ttu-id="9c049-120">**Out-of-Box-Tests:** Das Anwendungspaket muss mindestens drei PowerShell-Skripts enthalten, die das unbeaufsichtigte Installieren, Starten und Schließen der Anwendung und ihrer Abhängigkeiten ausführen.</span><span class="sxs-lookup"><span data-stu-id="9c049-120">**Out-of-Box tests:** The application package needs to contain at least three PowerShell scripts that will execute unattended installing, launching, and closing of the application and its dependencies.</span></span> <span data-ttu-id="9c049-121">Jedes Skript sollte die Überprüfung der eigenen Voraussetzungen, das Überprüfen des Erfolgreichen sowie das Aufräumen nach sich selbst (falls erforderlich) durchführen.</span><span class="sxs-lookup"><span data-stu-id="9c049-121">Each script should handle checking its own prerequisites, validating it succeeded, as well as cleaning up after itself (if necessary).</span></span>

<span data-ttu-id="9c049-122">**Funktionstests:** Das Anwendungspaket muss mindestens ein PowerShell-Skript enthalten.</span><span class="sxs-lookup"><span data-stu-id="9c049-122">**Functional tests:** The application package needs to contain at least one PowerShell script.</span></span> <span data-ttu-id="9c049-123">Wenn mehrere Skripts bereitgestellt werden, werden die Skripts in der Uploadsequenz ausgeführt, und ein Fehler in einem bestimmten Skript beendet die Ausführung nachfolgender Skripts.</span><span class="sxs-lookup"><span data-stu-id="9c049-123">Where more than one script is provided, the scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>

### <a name="script-requirements"></a><span data-ttu-id="9c049-124">Skriptanforderungen</span><span class="sxs-lookup"><span data-stu-id="9c049-124">Script requirements</span></span>

<span data-ttu-id="9c049-125">• PowerShell Version 5.1+</span><span class="sxs-lookup"><span data-stu-id="9c049-125">•   PowerShell Version 5.1+</span></span>     

<span data-ttu-id="9c049-126">• Unbeaufsichtigte Ausführung</span><span class="sxs-lookup"><span data-stu-id="9c049-126">•   Unattended execution</span></span>    

<span data-ttu-id="9c049-127">• Fehlerrückgabecode</span><span class="sxs-lookup"><span data-stu-id="9c049-127">•   Error return code</span></span>               

<span data-ttu-id="9c049-128">• Überprüfen des Erfolgs</span><span class="sxs-lookup"><span data-stu-id="9c049-128">•   Validate success</span></span>            

<span data-ttu-id="9c049-129">• Protokollierung in skriptspezifischen Protokollordnern</span><span class="sxs-lookup"><span data-stu-id="9c049-129">•   Logging to script specific log folder</span></span>

<span data-ttu-id="9c049-130">Jedes Skript muss vollständig unbeaufsichtigt ausgeführt werden, um in der Testpipeline erfolgreich ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="9c049-130">Each script needs to run completely unattended to successfully execute in the test pipeline.</span></span>

> [!Note]
> <span data-ttu-id="9c049-131">Skripts sollten bei erfolgreichem Abschluss "0" und einen Fehlercode ungleich Null zurückgeben, wenn während der Ausführung ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="9c049-131">Scripts should return “0” on successful completion and a non-zero error code if any error occurs during execution.</span></span>

<span data-ttu-id="9c049-132">Jedes Skript sollte überprüfen, ob es erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="9c049-132">Each script should validate that it ran successfully.</span></span> <span data-ttu-id="9c049-133">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9c049-133">E.g.</span></span> <span data-ttu-id="9c049-134">Das Installationsskript sollte überprüfen, ob bestimmte Binärdateien und/oder Registrierungsschlüssel auf dem System vorhanden sind, nachdem die Ausführung der Binärdatei des Installationsprogramms abgeschlossen ist, um mit einem angemessenen Maß an Zuverlässigkeit sicherzustellen, dass die Installation erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="9c049-134">the install script should check for the existence of certain binaries and/or registry keys on the system, after the installer binary finishes executing to ensure with a reasonable degree of confidence that the installation was successful.</span></span> 

<span data-ttu-id="9c049-135">Dies ist erforderlich, um ordnungsgemäß zu diagnostizieren, wo während eines Testlaufs Fehler auftreten, z. B. dass die Anwendung nicht erfolgreich installiert werden kann oder nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9c049-135">This is necessary to properly diagnose where errors occur during a test run, e.g. unable to install the application successfully versus being unable to launch it.</span></span>

> [!Important]
> <span data-ttu-id="9c049-136">**Vermeiden Sie Folgendes:** Skripts sollten den Computer nicht neu starten, wenn ein Neustart erforderlich ist, geben Sie dies während des Uploads Ihrer Skripts an.</span><span class="sxs-lookup"><span data-stu-id="9c049-136">**Avoid the following:** Scripts should not reboot the machine, if a reboot is necessary please specify this during the upload of your scripts.</span></span>

## <a name="3---log-collection"></a><span data-ttu-id="9c049-137">3. Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="9c049-137">3.   Log collection</span></span>

<span data-ttu-id="9c049-138">Jedes Skript sollte alle generierten Protokolle in einem Ordner mit dem Namen ```logs``` ausgeben.</span><span class="sxs-lookup"><span data-stu-id="9c049-138">Each script should output any logs it generates into a folder named ```logs```.</span></span> <span data-ttu-id="9c049-139">Alle Ordner im benannten Verzeichnis ```logs``` werden kopiert und zum Download auf der Seite ```Test Results``` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9c049-139">All folders in the directory named ```logs``` will be copied and presented for download on the ```Test Results``` page.</span></span>

<span data-ttu-id="9c049-140">Beispielsweise kann das Installationsskript (das sich im Verzeichnis **"App/skripts/install"** befindet) seine Protokolle ausgeben an: **logs/install.log,** sodass sich das endgültige Protokoll unter: **Apps/scripts/install/logs/install.log befindet.**</span><span class="sxs-lookup"><span data-stu-id="9c049-140">For example, the installation script (which may be located in the **App/scripts/install** directory) can output its logs to: **logs/install.log**, such that the final log will be at: **Apps/scripts/install/logs/install.log**</span></span>

<span data-ttu-id="9c049-141">Das System übernimmt die ```install.log``` Datei zusammen mit anderen Dateien in anderen ```logs``` Ordnern und sortiert sie zum Download.</span><span class="sxs-lookup"><span data-stu-id="9c049-141">The system will pick up the ```install.log``` file along with other files within other ```logs``` folders and collate it for download.</span></span>


## <a name="4---application-binaries"></a><span data-ttu-id="9c049-142">4. Anwendungsbinärdateien</span><span class="sxs-lookup"><span data-stu-id="9c049-142">4.   Application binaries</span></span>

<span data-ttu-id="9c049-143">Alle Binärdateien und Abhängigkeiten sollten in der einzelnen ZIP-Datei enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="9c049-143">Any binaries and dependencies should be included in the single zip file.</span></span> 

<span data-ttu-id="9c049-144">Diese sollten alles enthalten, was für die Installation der Anwendung erforderlich ist (z. B. das Installationsprogramm der Anwendung); wenn die Anwendung von Frameworks wie .NET Core/Standard oder .NET Framework abhängig ist, sollten diese in der Datei enthalten sein und in den bereitgestellten Skripts korrekt referenziert werden.</span><span class="sxs-lookup"><span data-stu-id="9c049-144">These should include everything necessary for installation of the application (e.g. the application installer); if the application has a dependency on any frameworks, such as .NET Core/Standard or .NET Framework, these should be included in the file and referenced correctly in the provided scripts.</span></span>


> [!Note]
> <span data-ttu-id="9c049-145">Die hochgeladene ZIP-Datei darf keine Leerzeichen oder Sonderzeichen im Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9c049-145">The uploaded zip file cannot have any spaces or special characters in its name</span></span>

## <a name="next-steps"></a><span data-ttu-id="9c049-146">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9c049-146">Next steps</span></span>

<span data-ttu-id="9c049-147">Wechseln Sie zum nächsten Artikel, um einige **häufig gestellte Fragen (FAQ)** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9c049-147">Advance to the next article to view some **Frequently Asked Questions (FAQ)**</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="9c049-148">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="9c049-148">Next step</span></span>](faq.md)
