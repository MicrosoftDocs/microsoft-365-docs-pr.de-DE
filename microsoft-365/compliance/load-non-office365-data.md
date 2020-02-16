---
title: Laden nicht Office 365er Daten in Beweise
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
description: ''
ms.openlocfilehash: 4db0b40d485c4c1107bdcb0d49616cadb15b1915
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072163"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="18f7e-102">Laden nicht Office 365er Daten in Beweise</span><span class="sxs-lookup"><span data-stu-id="18f7e-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="18f7e-103">Nicht alle Dokumente, die Sie möglicherweise in einer Datenuntersuchung analysieren müssen, befinden sich in Office 365.</span><span class="sxs-lookup"><span data-stu-id="18f7e-103">Not all documents that you may need to analyze in a data investigation will be located in Office 365.</span></span> <span data-ttu-id="18f7e-104">Mit der nicht Office 365en Funktion zum Importieren von Inhalten können Sie Dokumente, die nicht in Office 365 Leben, in Beweise hochladen, damit Sie in einer Datenuntersuchung analysiert werden können.</span><span class="sxs-lookup"><span data-stu-id="18f7e-104">With the Non-Office 365 content import feature you can upload documents that don't live in Office 365 into evidence so they can be analyzed in a data investigation.</span></span>

>[!Note]
><span data-ttu-id="18f7e-105">Für die Untersuchung von Daten ist ein Office 365 E3 mit dem Advanced Compliance-Add-on oder einem E5-Abonnement für Ihre Organisation erforderlich.</span><span class="sxs-lookup"><span data-stu-id="18f7e-105">Data investigation requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="18f7e-106">Wenn Sie diesen Plan nicht haben und Advanced eDiscovery testen möchten, können Sie sich für eine Testversion von Office 365 Enterprise E5 anmelden.</span><span class="sxs-lookup"><span data-stu-id="18f7e-106">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="18f7e-107">Vorabinformationen</span><span class="sxs-lookup"><span data-stu-id="18f7e-107">Before you begin</span></span>

<span data-ttu-id="18f7e-108">Wenn Sie das Feature nicht Office 365 hochladen wie in diesem Verfahren beschrieben verwenden, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="18f7e-108">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="18f7e-109">Ein Office 365 E3 mit Advanced Compliance-Add-on oder E5-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="18f7e-109">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="18f7e-110">Alle Verwalter, deren nicht Office 365 Inhalt hochgeladen wird, müssen über E3 mit Advanced Compliance Add-on oder E5-Lizenzen verfügen.</span><span class="sxs-lookup"><span data-stu-id="18f7e-110">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="18f7e-111">Ein vorhandener eDiscovery-Fall.</span><span class="sxs-lookup"><span data-stu-id="18f7e-111">An existing eDiscovery case.</span></span>

- <span data-ttu-id="18f7e-112">Alle Dateien für das Hochladen wurden in Ordner gesammelt, in denen pro Depot ein Ordner vorhanden ist und der Name des Ordners in diesem Format *Alias@Domainname*.</span><span class="sxs-lookup"><span data-stu-id="18f7e-112">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="18f7e-113">Die *Alias@Domainname* müssen Benutzer Office 365 Alias und Domäne sein.</span><span class="sxs-lookup"><span data-stu-id="18f7e-113">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="18f7e-114">Sie können alle *Alias@Domainname* Ordner in einem Stammordner sammeln.</span><span class="sxs-lookup"><span data-stu-id="18f7e-114">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="18f7e-115">Der Stammordner kann nur die *Alias@Domainname* Ordner enthalten, es dürfen keine losen Dateien im Stammordner vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="18f7e-115">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="18f7e-116">Ein Konto, bei dem es sich um einen eDiscovery-Manager oder eDiscovery-Administrator handelt Microsoft Azure Speicher Tools, die auf einem Computer installiert sind, der Zugriff auf die nicht Office 365 Inhaltsordner Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="18f7e-116">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="18f7e-117">Installieren Sie AzCopy, was Sie von hier aus tun können:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="18f7e-117">Install AzCopy, which you can do from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-in-to-a-data-investigation"></a><span data-ttu-id="18f7e-118">Hochladen nicht Office 365er Inhalte in eine Datenuntersuchung</span><span class="sxs-lookup"><span data-stu-id="18f7e-118">Upload non-Office 365 content in to a data investigation</span></span>

1. <span data-ttu-id="18f7e-119">Open \* \* \* \* Data Investigations \* \*, dann die Untersuchung, in die die nicht Office 365 Daten hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="18f7e-119">Open \*\*\*\*Data Investigations\*\*, then the investigation that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="18f7e-120">Klicken Sie auf die Registerkarte **Beweise** , und wählen Sie dann den Beweissatz aus, in den Sie die nicht Office 365 Daten laden möchten.</span><span class="sxs-lookup"><span data-stu-id="18f7e-120">Click the **Evidence** tab, then select the evidence set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="18f7e-121">Wenn Sie noch keinen Beweis Sätze erstellt haben, können Sie dies jetzt tun.</span><span class="sxs-lookup"><span data-stu-id="18f7e-121">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="18f7e-122">Klicken Sie schließlich auf **Beweise verwalten** , und zeigen Sie dann **Uploads** im Abschnitt nicht Office 365 Daten an.</span><span class="sxs-lookup"><span data-stu-id="18f7e-122">Finally, click **Manage evidence** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="18f7e-123">Klicken Sie auf die Schaltfläche **Dateien hochladen** , um den nicht Office 365 Datenimport-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="18f7e-123">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![Dateien hochladen](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="18f7e-125">Im ersten Schritt des Assistenten wird einfach ein sicheres Azure-BLOB für die zu hochzuladenden Dateien vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="18f7e-125">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="18f7e-126">Klicken Sie nach Abschluss der Vorbereitung auf die Schaltfläche **Weiter: Dateien hochladen** .</span><span class="sxs-lookup"><span data-stu-id="18f7e-126">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![Vorbereiten des Datenimports ohne Office 365](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="18f7e-128">Geben Sie im Schritt **Upload Files** den **Pfad zum Speicherort der Dateien**an, hier befinden sich die nicht Office 365 Daten, die Sie beim Import planen.</span><span class="sxs-lookup"><span data-stu-id="18f7e-128">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="18f7e-129">Durch Festlegen des richtigen Speicherorts wird sichergestellt, dass der AzCopy-Befehl ordnungsgemäß aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="18f7e-129">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="18f7e-130">Wenn Sie AzCopy nicht bereits installiert haben, können Sie dies hier tun:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="18f7e-130">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="18f7e-131">Kopieren Sie den vordefinierten Befehl, indem Sie auf den Link **in Zwischenablage kopieren** klicken.</span><span class="sxs-lookup"><span data-stu-id="18f7e-131">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="18f7e-132">Starten Sie eine Windows-Eingabeaufforderung, fügen Sie den Befehl ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="18f7e-132">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="18f7e-133">Die Dateien werden in den sicheren Azure-BLOB-Speicher für den nächsten Schritt hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="18f7e-133">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Hochladen von Dateien für nicht Office 365 Datenimport](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Verwenden von AzCopy zum Importieren nicht Office 365er Daten](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="18f7e-136">Kehren Sie schließlich zur Sicherheits & Compliance zurück, und klicken Sie auf die Schaltfläche **Weiter: Prozessdateien** .</span><span class="sxs-lookup"><span data-stu-id="18f7e-136">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="18f7e-137">Dadurch werden Verarbeitung, Textextraktion und Indizierung der hochgeladenen Dateien initiiert.</span><span class="sxs-lookup"><span data-stu-id="18f7e-137">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="18f7e-138">Sie können den Fortschritt der Verarbeitung hier oder auf der Registerkarte **Aufträge** nachverfolgen.  Sobald der Vorgang abgeschlossen ist, sind die neuen Dateien im Evidence-Paket verfügbar.</span><span class="sxs-lookup"><span data-stu-id="18f7e-138">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="18f7e-139">Nachdem die Verarbeitung abgeschlossen ist, können Sie den Assistenten schließen.</span><span class="sxs-lookup"><span data-stu-id="18f7e-139">After processing is complete, you can dismiss the wizard.</span></span>

![Nicht Office 365 Import Prozessdateien](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

