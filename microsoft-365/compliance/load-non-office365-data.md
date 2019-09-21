---
title: Laden nicht Office 365er Daten in Beweise
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: ee1e6f8a064567126d75b099cc3003e8a4d6a020
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081635"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="24deb-102">Laden nicht Office 365er Daten in Beweise</span><span class="sxs-lookup"><span data-stu-id="24deb-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="24deb-103">Nicht alle Dokumente, die Sie möglicherweise mit Office 365 Advanced eDiscovery analysieren müssen, werden in Office 365 Live verwendet.</span><span class="sxs-lookup"><span data-stu-id="24deb-103">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="24deb-104">Mit der nicht Office 365den Funktion zum Importieren von Inhalten in Advanced eDiscovery können Sie Dokumente, die nicht in Office 365 Leben, in einen Arbeitsumfang hochladen, sodass Sie mit Advanced eDiscovery analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="24deb-104">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="24deb-105">In diesem Verfahren erfahren Sie, wie Sie Ihre nicht-Office 365-Dokumente zur Analyse in Advanced eDiscovery integrieren.</span><span class="sxs-lookup"><span data-stu-id="24deb-105">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="24deb-106">Advanced eDiscovery erfordert eine Office 365 E3 mit dem Advanced Compliance-Add-on oder ein E5-Abonnement für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="24deb-106">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="24deb-107">Wenn Sie diesen Plan nicht haben und Advanced eDiscovery testen möchten, können Sie sich für eine Testversion von Office 365 Enterprise E5 anmelden.</span><span class="sxs-lookup"><span data-stu-id="24deb-107">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="24deb-108">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="24deb-108">Before you begin</span></span>
<span data-ttu-id="24deb-109">Wenn Sie das Feature nicht Office 365 hochladen wie in diesem Verfahren beschrieben verwenden, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="24deb-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="24deb-110">Ein Office 365 E3 mit Advanced Compliance-Add-on oder E5-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="24deb-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="24deb-111">Alle Verwalter, deren nicht Office 365 Inhalt hochgeladen wird, müssen über E3 mit Advanced Compliance Add-on oder E5-Lizenzen verfügen.</span><span class="sxs-lookup"><span data-stu-id="24deb-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="24deb-112">Ein vorhandener eDiscovery-Fall.</span><span class="sxs-lookup"><span data-stu-id="24deb-112">An existing eDiscovery case.</span></span>

- <span data-ttu-id="24deb-113">Alle Dateien für das Hochladen wurden in Ordner gesammelt, in denen ein Ordner pro Depotbank vorhanden ist, und der Name des Ordners ist in diesem Format *Alias @ Domain* Name.</span><span class="sxs-lookup"><span data-stu-id="24deb-113">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* .</span></span> <span data-ttu-id="24deb-114">*Bei dem Alias @ Domain Name* muss es sich um Benutzer Office 365 Alias und Domäne handeln.</span><span class="sxs-lookup"><span data-stu-id="24deb-114">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="24deb-115">Sie können alle Alias- *@ Domain Name* -Ordner in einem Stammordner sammeln.</span><span class="sxs-lookup"><span data-stu-id="24deb-115">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="24deb-116">Der Stammordner darf nur die Ordner *Alias @ Domain Name* enthalten, es dürfen keine losen Dateien im Stammordner vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="24deb-116">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="24deb-117">Ein Konto, bei dem es sich um einen eDiscovery-Manager oder eDiscovery-Administrator handelt Microsoft Azure Speicher Tools, die auf einem Computer installiert sind, der Zugriff auf die nicht Office 365 Inhaltsordner Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="24deb-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="24deb-118">Installieren Sie AzCopy, was Sie von hier aus tun können:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="24deb-118">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="24deb-119">Hochladen nicht Office 365er Inhalte in die erweiterte eDiscovery</span><span class="sxs-lookup"><span data-stu-id="24deb-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="24deb-120">Öffnen Sie als eDiscovery-Manager oder eDiscovery-Administrator Advanced eDiscovery, dann werden die nicht Office 365-Daten hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="24deb-120">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="24deb-121">Klicken Sie auf die Registerkarte **Arbeitsmappen** , und wählen Sie dann den Arbeitssatz aus, in den Sie die nicht Office 365 Daten laden möchten.</span><span class="sxs-lookup"><span data-stu-id="24deb-121">Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="24deb-122">Wenn Sie noch keine Arbeitsmappe erstellt haben, können Sie dies jetzt tun.</span><span class="sxs-lookup"><span data-stu-id="24deb-122">If you have not already created a working set, you can do so now.</span></span>  <span data-ttu-id="24deb-123">Klicken Sie schließlich auf " **Arbeitsaufgaben verwalten** " und dann auf " **Uploads** " im Abschnitt "nicht Office 365 Daten" anzeigen</span><span class="sxs-lookup"><span data-stu-id="24deb-123">Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="24deb-124">Klicken Sie auf die Schaltfläche **Dateien hochladen** , um den nicht Office 365 Datenimport-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="24deb-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![Hochladen von Dateien](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="24deb-126">Im ersten Schritt des Assistenten wird einfach ein sicheres Azure-BLOB für die zu hochzuladenden Dateien vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="24deb-126">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="24deb-127">Wenn die Vorbereitung compelted ist, klicken Sie auf die Schaltfläche **Weiter: Dateien hochladen** .</span><span class="sxs-lookup"><span data-stu-id="24deb-127">Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![Nicht Office 365 Import – Prepare](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="24deb-129">Geben Sie im Schritt **Upload Files** den **Pfad zum Speicherort der Dateien**an, hier befinden sich die nicht Office 365 Daten, die Sie beim Import planen.</span><span class="sxs-lookup"><span data-stu-id="24deb-129">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="24deb-130">Durch Festlegen des richtigen Speicherorts wird sichergestellt, dass der AzCopy-Befehl ordnungsgemäß aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="24deb-130">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="24deb-131">Wenn Sie AzCopy nicht bereits installiert haben, können Sie dies hier tun:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="24deb-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="24deb-132">Kopieren Sie den vordefinierten Befehl, indem Sie auf den Link **in Zwischenablage kopieren** klicken.</span><span class="sxs-lookup"><span data-stu-id="24deb-132">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="24deb-133">Starten Sie eine Windows-Eingabeaufforderung, fügen Sie den Befehl ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="24deb-133">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="24deb-134">Die Dateien werden in den sicheren Azure-BLOB-Speicher für den nächsten Schritt hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="24deb-134">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Nicht Office 365 Import-Upload-Dateien](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Nicht Office 365 Import – AzCopy](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="24deb-137">Kehren Sie schließlich zur Sicherheits #a0 Compliance zurück, und klicken Sie auf die Schaltfläche **Weiter: Prozessdateien** .</span><span class="sxs-lookup"><span data-stu-id="24deb-137">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="24deb-138">Dadurch wird die Verarbeitung, die Textextraktion und die Indizierung der hochgeladenen Dateien initiiert.</span><span class="sxs-lookup"><span data-stu-id="24deb-138">This will initiate processing, text extraction and indexing of the uploaded files.</span></span>  <span data-ttu-id="24deb-139">Sie können den Fortschritt der Verarbeitung hier oder auf der Registerkarte **Aufträge** nachverfolgen.  Sobald der Vorgang abgeschlossen ist, sind die neuen Dateien im Arbeitspaket verfügbar.</span><span class="sxs-lookup"><span data-stu-id="24deb-139">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.</span></span>  <span data-ttu-id="24deb-140">Nachdem die Verarbeitung abgeschlossen ist, können Sie den Assistenten schließen.</span><span class="sxs-lookup"><span data-stu-id="24deb-140">Once processing is complete, you can dismiss the wizard.</span></span>

![Nicht Office 365 Import Prozess-Dateien](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

