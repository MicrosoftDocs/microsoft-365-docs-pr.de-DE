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
ms.openlocfilehash: daafcf003ded35868413d99c11ec1bf3941dca9f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634157"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="d3b0f-103">Importieren von nicht-Microsoft 365-Inhalten für die erweiterte eDiscovery-Analyse (klassisch)</span><span class="sxs-lookup"><span data-stu-id="d3b0f-103">Import non-Microsoft 365 content for Advanced eDiscovery (classic) analysis</span></span>

<span data-ttu-id="d3b0f-104">Nicht alle Dokumente, die Sie möglicherweise mit Advanced eDiscovery analysieren müssen, werden in Microsoft 365 Live verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-104">Not all documents that you may need to analyze with Advanced eDiscovery will live in Microsoft 365.</span></span> <span data-ttu-id="d3b0f-105">Mit der nicht-Microsoft 365-Inhalts Importfunktion in Advanced eDiscovery können Sie Dokumente, die nicht in Microsoft 365 (außer PST-Dateien) Leben, in einen verknüpften Fall mit Azure Storage BLOB hochladen und mit Advanced eDiscovery analysieren.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-105">With the Non-Microsoft 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Microsoft 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="d3b0f-106">In diesem Verfahren erfahren Sie, wie Sie Ihre nicht-Microsoft 365-Dokumente zur Analyse in Advanced eDiscovery integrieren.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-106">This procedure shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3b0f-p102">Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="d3b0f-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d3b0f-109">Sie können ein erweitertes eDiscovery Data Storage-Add-on-Abonnement für Ihre nicht von Microsoft 365 Inhalte erwerben.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-109">You can purchase an Advanced eDiscovery data storage add-on subscription for your non-Microsoft 365 content.</span></span> <span data-ttu-id="d3b0f-110">Dies steht ausschließlich für Inhalte zur Verfügung, die mit Advanced eDiscovery analysiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="d3b0f-111">Befolgen Sie die Schritte unter [kaufen oder Bearbeiten eines Add-ons für Microsoft 365 for Business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) , und erwerben Sie das erweiterte eDiscovery-Speicher-Add-on.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-111">Follow the steps in [Buy or edit an add-on for Microsoft 365 for business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) and purchase the Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="d3b0f-112">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="d3b0f-112">Before you begin</span></span>

<span data-ttu-id="d3b0f-113">Wenn Sie das Feature nicht Office 365 hochladen wie in diesem Verfahren beschrieben verwenden, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d3b0f-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="d3b0f-114">Ein Office 365 E3 mit Advanced Compliance-Add-on oder E5-Abonnement</span><span class="sxs-lookup"><span data-stu-id="d3b0f-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
    
- <span data-ttu-id="d3b0f-115">Alle Verwalter, deren nicht Office 365 Inhalt hochgeladen wird, müssen über E3 mit Advanced Compliance Add-on oder E5-Lizenzen verfügen.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
    
- <span data-ttu-id="d3b0f-116">Ein vorhandener eDiscovery-Fall</span><span class="sxs-lookup"><span data-stu-id="d3b0f-116">An existing eDiscovery case</span></span>
    
- <span data-ttu-id="d3b0f-117">Alle Dateien für das Hochladen wurden in Ordner gesammelt, in denen pro Depot ein Ordner vorhanden ist und der Name des Ordners in diesem Format *Alias@Domainname* .</span><span class="sxs-lookup"><span data-stu-id="d3b0f-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="d3b0f-118">Die *Alias@Domainname* müssen Benutzer Office 365 Alias und Domäne sein.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="d3b0f-119">Sie können alle *Alias@Domainname* Ordner in einem Stammordner sammeln.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="d3b0f-120">Der Stammordner kann nur die *Alias@Domainname* Ordner enthalten, es dürfen keine losen Dateien im Stammordner vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder</span></span> 
    
- <span data-ttu-id="d3b0f-121">Ein Konto, das entweder eDiscovery-Manager oder eDiscovery-Administrator ist</span><span class="sxs-lookup"><span data-stu-id="d3b0f-121">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>
    
- <span data-ttu-id="d3b0f-122">[Microsoft Azure Speicher Tools](https://aka.ms/downloadazcopy) , die auf einem Computer installiert sind, der Zugriff auf die Struktur nicht Office 365 Inhaltsordner hat.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="d3b0f-123">Hochladen nicht Office 365er Inhalte in die erweiterte eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d3b0f-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="d3b0f-124">Öffnen Sie als eDiscovery-Manager oder eDiscovery-Administrator **eDiscovery**, und öffnen Sie den Fall, dass die nicht Office 365 Daten hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="d3b0f-125">Wenn Sie einen Fall erstellen müssen, finden Sie weitere Informationen unter [Verwalten von eDiscovery &amp; -Fällen im Security Compliance Center](ediscovery-cases.md) .</span><span class="sxs-lookup"><span data-stu-id="d3b0f-125">If you need to create a case, see [Manage eDiscovery cases in the Security &amp; Compliance Center](ediscovery-cases.md)</span></span>
    
2. <span data-ttu-id="d3b0f-126">Klicken Sie auf **zu Advanced eDiscovery wechseln** .</span><span class="sxs-lookup"><span data-stu-id="d3b0f-126">Click **Switch to Advanced eDiscovery**</span></span>
    
3. <span data-ttu-id="d3b0f-127">Wählen **Source type** Sie unter Quelltext **nicht Office 365 Daten**aus.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-127">Under **Source type** select **Non-Office 365 data**.</span></span>
    
4. <span data-ttu-id="d3b0f-128">Klicken Sie auf **Container hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-128">Click **Add container**.</span></span> <span data-ttu-id="d3b0f-129">Nennen Sie den Container, und fügen Sie eine Beschreibung hinzu.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-129">Name the container and add a description.</span></span>
    
5. <span data-ttu-id="d3b0f-130">Wählen Sie den neu hinzugefügten Container aus der Container Liste aus, und kopieren Sie die URL, die im Container Detailbereich angezeigt wird, und schließen Sie dann den Bereich.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-130">Select the newly added container from the container list and copy the URL that appears in the container details pane and then close the pane</span></span>
    
6. <span data-ttu-id="d3b0f-131">Öffnen Sie eine Eingabeaufforderung als Administrator, und ändern Sie das Verzeichnis in Ordner, in dem Sie AzCopy installiert haben..</span><span class="sxs-lookup"><span data-stu-id="d3b0f-131">Open a command prompt as an administrator and change directory to folder where you have AzCopy installed..</span></span>
    
7. <span data-ttu-id="d3b0f-132">Erstellen Sie die AzCopy-Befehlszeile, um die Dateien wie folgt hochzuladen:</span><span class="sxs-lookup"><span data-stu-id="d3b0f-132">Construct the AzCopy command line to upload the files like this:</span></span>
    
    <span data-ttu-id="d3b0f-133">AzCopy/Source: " *Vollständiger Pfad zum Stammordner auf dem lokalen Computer* "/dest: " *Container-URL bis einschließlich der?*</span><span class="sxs-lookup"><span data-stu-id="d3b0f-133">AzCopy /Source:" *full path to root folder on local machine*  " /Dest:"  *container URL up to but not including the ?*</span></span>  <span data-ttu-id="d3b0f-134">"/DestSAS:" *Rest der Container-URL aus dem? bis zum Ende* "/s</span><span class="sxs-lookup"><span data-stu-id="d3b0f-134">" /DestSAS:"  *remainder of the container url from the ? to the end*  " /S.</span></span> 
    
    <span data-ttu-id="d3b0f-135">Verwenden Sie beispielsweise die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="d3b0f-135">For example, using these values:</span></span> 
    
  - <span data-ttu-id="d3b0f-136">Stammordner – C:\Collected-Daten</span><span class="sxs-lookup"><span data-stu-id="d3b0f-136">root folder - C:\Collected Data</span></span> 
    
  - <span data-ttu-id="d3b0f-137">Container-URL https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp-; SR =&amp;c Si = NonOfficeData15%&amp;7C0 SIG = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3D</span><span class="sxs-lookup"><span data-stu-id="d3b0f-137">container url - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D</span></span>
    
    <span data-ttu-id="d3b0f-138">die AzCopy-Befehlszeilensyntax lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d3b0f-138">the AzCopy command line syntax would be:</span></span>
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    <span data-ttu-id="d3b0f-139">Weitere Informationen zur Azcopy-Syntax finden Sie unter [übertragen von Daten mit dem Azcopy unter Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span><span class="sxs-lookup"><span data-stu-id="d3b0f-139">For more information on Azcopy syntax see, [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="d3b0f-140">Pro Benutzer muss ein Stammordner vorhanden sein, und der Ordnername muss das *Alias@Domainname* Format aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-140">There must be one root folder per user and the folder name must be in the  *alias@domainname*  format.</span></span> 
  
8. <span data-ttu-id="d3b0f-141">Nachdem die Ordner fertig hochgeladen wurden, wechseln Sie zurück zu Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-141">Once the folders have finished uploading, switch back to Advanced eDiscovery.</span></span> <span data-ttu-id="d3b0f-142">Der Inhalt in den Ordnern, die Sie hochgeladen haben, ist nun für die Verarbeitung in Advanced eDiscovery verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-142">The content in the folders you uploaded is now ready to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="d3b0f-143">Wählen Sie den Container aus, und klicken Sie auf die Schaltfläche Prozess.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-143">Select the container and click the Process button.</span></span> <span data-ttu-id="d3b0f-144">Weitere Informationen zur erweiterten eDiscovery-Verarbeitung finden Sie unter [Ausführen des Prozess Moduls und Laden von Daten in Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md) .</span><span class="sxs-lookup"><span data-stu-id="d3b0f-144">For more details on Advanced eDiscovery Processing see, [Run the Process module and load data in Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d3b0f-145">Nachdem der Container in Advanced eDiscovery erfolgreich verarbeitet wurde, können Sie dem SAS-Speicher in Azure keine neuen Inhalte mehr hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-145">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="d3b0f-146">Wenn Sie zusätzliche Inhalte erfassen und Sie dem Fall für die erweiterte eDiscovery-Analyse hinzufügen möchten, müssen Sie einen neuen **nicht-Office 365-Daten** Container erstellen und dieses Verfahren wiederholen.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-146">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="d3b0f-147">Wenn der Container *aufgrund von Ordner Benennungs Problemen nicht erfolgreich verarbeitet* wird und Sie dann die Probleme beheben, müssen Sie weiterhin einen neuen Container erstellen und die wiederherstellen und erneut mit den Verfahren in diesem Artikel hochladen.</span><span class="sxs-lookup"><span data-stu-id="d3b0f-147">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
