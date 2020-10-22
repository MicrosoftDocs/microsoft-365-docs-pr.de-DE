---
title: Importieren von nicht-Microsoft 365-Inhalten für erweiterte eDiscovery-Analysen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Vorgehensweise zum Importieren von Inhalten, die nicht in Microsoft 365 gespeichert sind, in ein Azure-BLOB, damit es mit AeD analysiert werden kann
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be30daa35770247a9dd342b88093872083075547
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636952"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="11c40-103">Importieren von nicht-Microsoft 365-Inhalten für die erweiterte eDiscovery-Analyse (klassisch)</span><span class="sxs-lookup"><span data-stu-id="11c40-103">Import non-Microsoft 365 content for Advanced eDiscovery (classic) analysis</span></span>

<span data-ttu-id="11c40-104">Nicht alle Dokumente, die Sie möglicherweise mit Advanced eDiscovery analysieren müssen, werden in Microsoft 365 Live verwendet.</span><span class="sxs-lookup"><span data-stu-id="11c40-104">Not all documents that you may need to analyze with Advanced eDiscovery will live in Microsoft 365.</span></span> <span data-ttu-id="11c40-105">Mit der nicht-Microsoft 365-Inhalts Importfunktion in Advanced eDiscovery können Sie Dokumente, die nicht in Microsoft 365 (außer PST-Dateien) Leben, in einen verknüpften Fall mit Azure Storage BLOB hochladen und mit Advanced eDiscovery analysieren.</span><span class="sxs-lookup"><span data-stu-id="11c40-105">With the Non-Microsoft 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Microsoft 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="11c40-106">In diesem Verfahren erfahren Sie, wie Sie Ihre nicht-Microsoft 365-Dokumente zur Analyse in Advanced eDiscovery integrieren.</span><span class="sxs-lookup"><span data-stu-id="11c40-106">This procedure shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="11c40-p102">Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="11c40-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="11c40-109">Sie können ein erweitertes eDiscovery Data Storage-Add-on-Abonnement für Ihre nicht von Microsoft 365 Inhalte erwerben.</span><span class="sxs-lookup"><span data-stu-id="11c40-109">You can purchase an Advanced eDiscovery data storage add-on subscription for your non-Microsoft 365 content.</span></span> <span data-ttu-id="11c40-110">Dies steht ausschließlich für Inhalte zur Verfügung, die mit Advanced eDiscovery analysiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="11c40-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="11c40-111">Befolgen Sie die Schritte unter [kaufen oder Bearbeiten eines Add-ons für Microsoft 365 for Business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) , und erwerben Sie das erweiterte eDiscovery-Speicher-Add-on.</span><span class="sxs-lookup"><span data-stu-id="11c40-111">Follow the steps in [Buy or edit an add-on for Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) and purchase the Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="11c40-112">Anforderungen zum Hochladen nicht Office 365der Inhalte</span><span class="sxs-lookup"><span data-stu-id="11c40-112">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="11c40-113">Wenn Sie das Feature nicht Office 365 hochladen wie in diesem Verfahren beschrieben verwenden, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="11c40-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="11c40-114">Ein Office 365 E3 mit Advanced Compliance-Add-on oder E5-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="11c40-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>
    
- <span data-ttu-id="11c40-115">Alle Verwalter, deren nicht Office 365 Inhalt hochgeladen wird, müssen über E3 mit Advanced Compliance Add-on oder E5-Lizenzen verfügen.</span><span class="sxs-lookup"><span data-stu-id="11c40-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>
    
- <span data-ttu-id="11c40-116">Ein vorhandener eDiscovery-Fall.</span><span class="sxs-lookup"><span data-stu-id="11c40-116">An existing eDiscovery case.</span></span>
    
- <span data-ttu-id="11c40-117">Alle Dateien für das Hochladen wurden in Ordner gesammelt, in denen pro Depot ein Ordner vorhanden ist und der Name des Ordners in diesem Format  *Alias@Domainname*  .</span><span class="sxs-lookup"><span data-stu-id="11c40-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="11c40-118">Die  *Alias@Domainname*  müssen Benutzer Office 365 Alias und Domäne sein.</span><span class="sxs-lookup"><span data-stu-id="11c40-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="11c40-119">Sie können alle  *Alias@Domainname*  Ordner in einem Stammordner sammeln.</span><span class="sxs-lookup"><span data-stu-id="11c40-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="11c40-120">Der Stammordner kann nur die  *Alias@Domainname*  Ordner enthalten, es dürfen keine losen Dateien im Stammordner vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="11c40-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder.</span></span>
    
- <span data-ttu-id="11c40-121">Ein Konto, das entweder eDiscovery-Manager oder eDiscovery-Administrator ist.</span><span class="sxs-lookup"><span data-stu-id="11c40-121">An account that is either an eDiscovery Manager or eDiscovery Administrator.</span></span>
    
- <span data-ttu-id="11c40-122">[Microsoft Azure Speicher Tools](https://aka.ms/downloadazcopy) , die auf einem Computer installiert sind, der Zugriff auf die Struktur nicht Office 365 Inhaltsordner hat.</span><span class="sxs-lookup"><span data-stu-id="11c40-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="11c40-123">Hochladen nicht Office 365er Inhalte in die erweiterte eDiscovery</span><span class="sxs-lookup"><span data-stu-id="11c40-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="11c40-124">Öffnen Sie als eDiscovery-Manager oder eDiscovery-Administrator **eDiscovery**, und öffnen Sie den Fall, dass die nicht Office 365 Daten hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="11c40-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="11c40-125">Wenn Sie einen Fall erstellen müssen, finden Sie weitere Informationen unter [Verwalten von eDiscovery-Fällen im Security &amp; Compliance Center](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="11c40-125">If you need to create a case, see [Manage eDiscovery cases in the Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
    
2. <span data-ttu-id="11c40-126">Klicken Sie auf **zu Advanced eDiscovery wechseln**.</span><span class="sxs-lookup"><span data-stu-id="11c40-126">Click **Switch to Advanced eDiscovery**.</span></span>

3. <span data-ttu-id="11c40-127">Wählen Sie im Menü **Überprüfungs Sätze** aus.</span><span class="sxs-lookup"><span data-stu-id="11c40-127">Select **Review Sets** from the menu.</span></span>

4. <span data-ttu-id="11c40-128">Wählen Sie einen vorhandenen Überprüfungs aus, oder wählen Sie **Add Review Sets**aus.</span><span class="sxs-lookup"><span data-stu-id="11c40-128">Select an existing Review Set or choose **Add Review Set**.</span></span>

5. <span data-ttu-id="11c40-129">Wählen Sie **Manage Review Sets**aus.</span><span class="sxs-lookup"><span data-stu-id="11c40-129">Select **Manage review set**.</span></span>

6. <span data-ttu-id="11c40-130">Wählen Sie auf der nicht Office 365-Datenkarte die Option **Uploads anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="11c40-130">In the Non-Office 365 data card, select **View Uploads**.</span></span>

7. <span data-ttu-id="11c40-131">Wählen Sie **Dateien hochladen** aus, um den Dateiupload-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="11c40-131">Choose **Upload files** to start the file upload wizard.</span></span>

8. <span data-ttu-id="11c40-132">Die erste Registerkarte ist **1. Vorbereiten des Schritts**.</span><span class="sxs-lookup"><span data-stu-id="11c40-132">The first tab is **1. Prepare step**.</span></span> <span data-ttu-id="11c40-133">Wählen Sie **Weiter: Upload Files**aus.</span><span class="sxs-lookup"><span data-stu-id="11c40-133">Select **Next: Upload files**.</span></span>

9. <span data-ttu-id="11c40-134">Auf der \*\*2. \*\* Registerkarte "Dateien hochladen" Sie werden aufgefordert, AzCopy.exe herunterzuladen, wenn Sie dies nicht bereits getan haben, und dann den Pfad zum Dateispeicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="11c40-134">On the **2. Upload files** tab you will be prompted to download AzCopy.exe if you have not done so already, and then to provide the path to the file location.</span></span> <span data-ttu-id="11c40-135">Beispielsweise `C:\Upload`  erhalten Sie den Befehl zum Ausführen AzCopy.exe.</span><span class="sxs-lookup"><span data-stu-id="11c40-135">For example, `C:\Upload`  will give you the command to execute AzCopy.exe.</span></span> <span data-ttu-id="11c40-136">Mit wird `C:\Upload` Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="11c40-136">Using `C:\Upload`, you will see:</span></span>

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. <span data-ttu-id="11c40-137">Öffnen Sie ein Eingabeaufforderungsfenster, und führen Sie den Befehl AzCopy.exe aus, um die Daten in Azure zu importieren.</span><span class="sxs-lookup"><span data-stu-id="11c40-137">Open a command prompt window and execute the AzCopy.exe command to import the data into Azure.</span></span> <span data-ttu-id="11c40-138">Nachdem alle Daten geladen wurden, wählen Sie **Weiter: Process files**.</span><span class="sxs-lookup"><span data-stu-id="11c40-138">Once it has loaded all of the data, select **Next: Process files**.</span></span>

11. <span data-ttu-id="11c40-139">Die nächste Registerkarte ist **3. Verarbeiten von Dateien** , in denen die depotverwalter angezeigt werden, denen Daten zugeordnet sind, und der Fortschritt der importierten Daten wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11c40-139">The next tab is **3. Process files** where you will see the custodians that have data associated with them and will also show you the progress of the data being imported.</span></span>
        
    <span data-ttu-id="11c40-140">Weitere Informationen zur Azcopy-Syntax finden Sie unter [übertragen von Daten mit dem Azcopy unter Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="11c40-140">For more information on Azcopy syntax, see [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span> 
    
    <span data-ttu-id="11c40-141">Weitere Informationen zur erweiterten eDiscovery-Verarbeitung finden Sie unter [Ausführen des Prozess Moduls und Laden von Daten in Advanced eDiscovery (Classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="11c40-141">For more details on Advanced eDiscovery Processing, see [Run the Process module and load data in Advanced eDiscovery (classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="11c40-142">Pro Benutzer muss ein Stammordner vorhanden sein, und der Ordnername muss das <b>Alias@Domainname</b>  Format aufweisen.</span><span class="sxs-lookup"><span data-stu-id="11c40-142">There must be one root folder per user and the folder name must be in the <b>alias@domainname</b>  format.</span></span> 
   
    > [!IMPORTANT]
    > <span data-ttu-id="11c40-143">Nachdem der Container in Advanced eDiscovery erfolgreich verarbeitet wurde, können Sie dem SAS-Speicher in Azure keine neuen Inhalte mehr hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="11c40-143">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="11c40-144">Wenn Sie zusätzliche Inhalte erfassen und Sie dem Fall für die erweiterte eDiscovery-Analyse hinzufügen möchten, müssen Sie einen neuen **nicht-Office 365-Daten** Container erstellen und dieses Verfahren wiederholen.</span><span class="sxs-lookup"><span data-stu-id="11c40-144">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="11c40-145">Wenn der Container  *aufgrund von Ordner Benennungs Problemen nicht erfolgreich verarbeitet*  wird und Sie dann die Probleme beheben, müssen Sie weiterhin einen neuen Container erstellen und die wiederherstellen und erneut mit den Verfahren in diesem Artikel hochladen.</span><span class="sxs-lookup"><span data-stu-id="11c40-145">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
