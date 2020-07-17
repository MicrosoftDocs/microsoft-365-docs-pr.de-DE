---
title: Laden von nicht von Microsoft 365 Daten in Beweise
f1.keywords:
- NOCSH
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
description: In diesem Artikel erfahren Sie, wie Sie das nicht Office 365 Inhalts Importfeature verwenden können, um nicht Office 365 Dokumente in einer Datenermittlung in Beweise hochzuladen.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 9bfebc6aad9bc37d7d78ec4a0d50e6de967ac7d1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815482"
---
# <a name="load-non-microsoft-365-data-into-evidence"></a><span data-ttu-id="3f432-103">Laden von nicht von Microsoft 365 Daten in Beweise</span><span class="sxs-lookup"><span data-stu-id="3f432-103">Load non-Microsoft 365 data into evidence</span></span>

<span data-ttu-id="3f432-104">Nicht alle Dokumente, die Sie möglicherweise in einer Datenuntersuchung analysieren müssen, befinden sich in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f432-104">Not all documents that you may need to analyze in a data investigation will be located in Microsoft 365.</span></span> <span data-ttu-id="3f432-105">Mit der nicht-Microsoft 365-Funktion zum Importieren von Inhalten können Sie Dokumente, die nicht in Microsoft 365 Leben, in Beweise hochladen, damit Sie in einer Datenuntersuchung analysiert werden können.</span><span class="sxs-lookup"><span data-stu-id="3f432-105">With the Non-Microsoft 365 content import feature you can upload documents that don't live in Microsoft 365 into evidence so they can be analyzed in a data investigation.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="3f432-106">Anforderungen zum Hochladen nicht Office 365der Inhalte</span><span class="sxs-lookup"><span data-stu-id="3f432-106">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="3f432-107">Wenn Sie das Feature "nicht-Microsoft 365 hochladen" wie in diesem Verfahren beschrieben verwenden, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3f432-107">Using the upload Non-Microsoft 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="3f432-108">Ein Microsoft 365-oder Office 365 E5-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="3f432-108">A Microsoft 365 or Office 365 E5 subscription.</span></span>

- <span data-ttu-id="3f432-109">Alle Personen, deren Inhalt nicht von Microsoft 365 hochgeladen wird, müssen über die entsprechende E5-oder E5-Add-on-Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="3f432-109">All people of interest whose non-Microsoft 365 content will be uploaded must have the appropriate E5 or E5 add-on license.</span></span>

- <span data-ttu-id="3f432-110">Ein vorhandener eDiscovery-Fall.</span><span class="sxs-lookup"><span data-stu-id="3f432-110">An existing eDiscovery case.</span></span>

- <span data-ttu-id="3f432-111">Alle Dateien für das Hochladen wurden in Ordner gesammelt, in denen pro Depot ein Ordner vorhanden ist und der Name des Ordners in diesem Format *Alias@Domainname*.</span><span class="sxs-lookup"><span data-stu-id="3f432-111">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="3f432-112">Das *Alias@Domainname* muss der Alias und die Domäne des Benutzers sein.</span><span class="sxs-lookup"><span data-stu-id="3f432-112">The *alias@domainname* must be user's alias and domain.</span></span> <span data-ttu-id="3f432-113">Sie können alle *Alias@Domainname* Ordner in einem Stammordner sammeln.</span><span class="sxs-lookup"><span data-stu-id="3f432-113">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="3f432-114">Der Stammordner kann nur die *Alias@Domainname* Ordner enthalten, es dürfen keine losen Dateien im Stammordner vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="3f432-114">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="3f432-115">Ein Konto, bei dem es sich entweder um einen eDiscovery-Manager oder eDiscovery-Administrator handelt Microsoft Azure Speicher Tools, die auf einem Computer installiert sind, der Zugriff auf die Struktur eines nicht von Microsoft 365 Inhaltsordner hat.</span><span class="sxs-lookup"><span data-stu-id="3f432-115">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span>

- <span data-ttu-id="3f432-116">Installieren Sie AzCopy, was Sie [unter Erste Schritte mit AzCopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)tun können.</span><span class="sxs-lookup"><span data-stu-id="3f432-116">Install AzCopy, which you can do from [Get started with AzCopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span>

## <a name="upload-non-microsoft-365-content-in-to-a-data-investigation"></a><span data-ttu-id="3f432-117">Hochladen von nicht-Microsoft 365-Inhalten in eine Datenuntersuchung</span><span class="sxs-lookup"><span data-stu-id="3f432-117">Upload non-Microsoft 365 content in to a data investigation</span></span>

1. <span data-ttu-id="3f432-118">Öffnen Sie **Daten Untersuchungen** , und gehen Sie zu der Untersuchung, in die die Daten von nicht-Microsoft 365 hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="3f432-118">Open **Data Investigations** and go to the investigation that the non-Microsoft 365 data will be uploaded to.</span></span>  <span data-ttu-id="3f432-119">Klicken Sie auf die Registerkarte **Beweise** , und wählen Sie dann den Beweissatz aus, in den Sie die Daten laden möchten.</span><span class="sxs-lookup"><span data-stu-id="3f432-119">Click the **Evidence** tab, then select the evidence set you wish to load the data to.</span></span>  <span data-ttu-id="3f432-120">Wenn Sie noch keinen Beweis Sätze erstellt haben, können Sie dies jetzt tun.</span><span class="sxs-lookup"><span data-stu-id="3f432-120">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="3f432-121">Klicken Sie schließlich auf **Beweise verwalten** , und zeigen Sie dann **Uploads** im Abschnitt Data an.</span><span class="sxs-lookup"><span data-stu-id="3f432-121">Finally, click **Manage evidence** then **View uploads** in the data section</span></span>

2. <span data-ttu-id="3f432-122">Klicken Sie auf die Schaltfläche **Dateien hochladen** , um den Datenimport-Assistenten von nicht Microsoft 365 zu starten.</span><span class="sxs-lookup"><span data-stu-id="3f432-122">Click the **Upload files** button to start the Non-Microsoft 365 data import wizard.</span></span>

![Dateien hochladen](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="3f432-124">Im ersten Schritt des Assistenten wird einfach ein sicheres Azure-BLOB für die zu hochzuladenden Dateien vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="3f432-124">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="3f432-125">Klicken Sie nach Abschluss der Vorbereitung auf die Schaltfläche **Weiter: Dateien hochladen** .</span><span class="sxs-lookup"><span data-stu-id="3f432-125">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![Vorbereiten des Datenimports von nicht-Microsoft 365](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="3f432-127">Geben Sie im Schritt **Upload Files** den **Pfad zum Speicherort der Dateien**an, wo sich die nicht von Microsoft 365 Daten befinden, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3f432-127">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Microsoft 365 data you plan on importing is located.</span></span>  <span data-ttu-id="3f432-128">Durch Festlegen des richtigen Speicherorts wird sichergestellt, dass der AzCopy-Befehl ordnungsgemäß aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="3f432-128">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="3f432-129">Wenn Sie AzCopy nicht bereits installiert haben, können Sie dies hier tun:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="3f432-129">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="3f432-130">Kopieren Sie den vordefinierten Befehl, indem Sie auf den Link **in Zwischenablage kopieren** klicken.</span><span class="sxs-lookup"><span data-stu-id="3f432-130">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="3f432-131">Starten Sie eine Windows-Eingabeaufforderung, fügen Sie den Befehl ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="3f432-131">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="3f432-132">Die Dateien werden in den sicheren Azure-BLOB-Speicher für den nächsten Schritt hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="3f432-132">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Hochladen von Dateien für den Datenimport von nicht-Microsoft 365](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Verwenden von AzCopy zum Importieren von nicht von Microsoft 365 Daten](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="3f432-135">Kehren Sie schließlich zur Sicherheits & Compliance zurück, und klicken Sie auf die Schaltfläche **Weiter: Prozessdateien** .</span><span class="sxs-lookup"><span data-stu-id="3f432-135">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="3f432-136">Dadurch werden Verarbeitung, Textextraktion und Indizierung der hochgeladenen Dateien initiiert.</span><span class="sxs-lookup"><span data-stu-id="3f432-136">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="3f432-137">Sie können den Fortschritt der Verarbeitung hier oder auf der Registerkarte **Aufträge** nachverfolgen.  Sobald der Vorgang abgeschlossen ist, sind die neuen Dateien im Evidence-Paket verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3f432-137">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="3f432-138">Nachdem die Verarbeitung abgeschlossen ist, können Sie den Assistenten schließen.</span><span class="sxs-lookup"><span data-stu-id="3f432-138">After processing is complete, you can dismiss the wizard.</span></span>

![Nicht von Microsoft 365 Import Prozessdateien](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

