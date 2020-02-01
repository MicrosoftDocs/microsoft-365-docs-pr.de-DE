---
title: Virenerkennung in SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/14/2019
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Office 365 können zum Schutz Ihrer Umgebung vor Schadsoftware beitragen, indem Sie Viren in Dateien erkennen, die von Benutzern in SharePoint Online hochgeladen werden. Dateien werden nach dem Hochladen auf Viren überprüft. Wenn eine Datei als infiziert erkannt wird, wird eine Eigenschaft festgelegt, damit Benutzer die Datei nicht herunterladen oder synchronisieren können.
ms.openlocfilehash: 1a41c5bb00e7169878206be2db076af0b0745e30
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598002"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="adc4a-105">Virenerkennung in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="adc4a-105">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="adc4a-106">Office 365 können zum Schutz Ihrer Umgebung vor Schadsoftware beitragen, indem Sie Viren in Dateien erkennen, die von Benutzern in SharePoint Online hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="adc4a-106">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="adc4a-107">Dateien werden nach dem Hochladen möglicherweise auf Viren überprüft.</span><span class="sxs-lookup"><span data-stu-id="adc4a-107">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="adc4a-108">Wenn eine Datei als infiziert erkannt wird, wird eine Eigenschaft festgelegt, damit Benutzer die Datei nicht herunterladen oder synchronisieren können.</span><span class="sxs-lookup"><span data-stu-id="adc4a-108">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="adc4a-109">Diese Antivirus-Funktionen in SharePoint Online sind eine Möglichkeit, Viren einzudämmen.</span><span class="sxs-lookup"><span data-stu-id="adc4a-109">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="adc4a-110">Sie sind nicht als einzelne Verteidigungspunkte gegen Schadsoftware für Ihre Umgebung gedacht.</span><span class="sxs-lookup"><span data-stu-id="adc4a-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="adc4a-111">Wir ermutigen alle Kunden, den Schutz vor Schadsoftware auf verschiedenen Ebenen zu bewerten und zu implementieren und bewährte Methoden für die Sicherung Ihrer Unternehmensinfrastruktur anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="adc4a-111">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="adc4a-112">Weitere Informationen zu Strategien und bewährten Methoden finden Sie unter [Security Roadmap](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="adc4a-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="adc4a-113">Was geschieht, wenn eine infizierte Datei in SharePoint Online hochgeladen wird?</span><span class="sxs-lookup"><span data-stu-id="adc4a-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="adc4a-114">Office 365 verwendet ein allgemeines Viruserkennungsmodul.</span><span class="sxs-lookup"><span data-stu-id="adc4a-114">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="adc4a-115">Das Modul wird in SharePoint Online asynchron ausgeführt, und einige Dateien werden nach dem Hochladen überprüft.</span><span class="sxs-lookup"><span data-stu-id="adc4a-115">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="adc4a-116">Heuristiken werden verwendet, um zu bestimmen, welche Dateien gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="adc4a-116">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="adc4a-117">Wenn eine Datei gefunden wird, die einen Virus enthält, wird Sie gekennzeichnet, damit Sie nicht erneut heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="adc4a-117">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="adc4a-118">Im April 2018 haben wir den Grenzwert von 25 MB für gescannte Dateien entfernt.</span><span class="sxs-lookup"><span data-stu-id="adc4a-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="adc4a-119">Folgendes geschieht:</span><span class="sxs-lookup"><span data-stu-id="adc4a-119">Here's what happens:</span></span>
  
1. <span data-ttu-id="adc4a-120">Ein Benutzer lädt eine Datei in SharePoint Online hoch.</span><span class="sxs-lookup"><span data-stu-id="adc4a-120">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="adc4a-121">SharePoint Online bestimmt, ob die Datei die Kriterien für einen Scan erfüllt.</span><span class="sxs-lookup"><span data-stu-id="adc4a-121">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="adc4a-122">Das Viruserkennungsmodul scannt die Datei.</span><span class="sxs-lookup"><span data-stu-id="adc4a-122">The virus detection engine scans the file.</span></span>
    
4. <span data-ttu-id="adc4a-123">Wenn ein Virus gefunden wird, legt das Virusmodul eine Eigenschaft für die Datei fest, die angibt, dass es infiziert ist.</span><span class="sxs-lookup"><span data-stu-id="adc4a-123">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="adc4a-124">Was geschieht, wenn ein Benutzer versucht, eine infizierte Datei mithilfe des Browsers herunterzuladen?</span><span class="sxs-lookup"><span data-stu-id="adc4a-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="adc4a-125">Wenn eine Datei mit einem Virus infiziert ist, können Benutzer die Datei nicht über den Browser aus SharePoint Online herunterladen.</span><span class="sxs-lookup"><span data-stu-id="adc4a-125">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="adc4a-126">Folgendes geschieht:</span><span class="sxs-lookup"><span data-stu-id="adc4a-126">Here's what happens:</span></span>
  
1. <span data-ttu-id="adc4a-127">Ein Benutzer öffnet einen Webbrowser und versucht, eine infizierte Datei aus SharePoint Online herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="adc4a-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="adc4a-128">Der Benutzer erhält eine Warnung, dass ein Virus erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="adc4a-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="adc4a-129">Der Benutzer erhält die Möglichkeit, die Datei herunterzuladen und zu versuchen, Sie mit ihrer eigenen Viren Software zu säubern.</span><span class="sxs-lookup"><span data-stu-id="adc4a-129">The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="adc4a-130">Sie können das Cmdlet "SPOTenant" mit dem Parameter " **DisallowInfectedFileDownload** " verwenden, um Benutzern das Herunterladen einer erkannten Datei zu ermöglichen, selbst im Fenster "Antivirus-Warnung".</span><span class="sxs-lookup"><span data-stu-id="adc4a-130">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window.</span></span> <span data-ttu-id="adc4a-131">Siehe [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="adc4a-131">See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="adc4a-132">Was geschieht, wenn der OneDrive-synchronisierungsclient versucht, eine infizierte Datei zu synchronisieren?</span><span class="sxs-lookup"><span data-stu-id="adc4a-132">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="adc4a-133">Unabhängig davon, ob Benutzer Dateien mit dem neuen OneDrive-synchronisierungsclient (OneDrive. exe) oder dem vorherigen OneDrive für Unternehmen synchronisierungsclient (Groove. exe) synchronisieren, wenn eine Datei einen Virus enthält, wird Sie vom synchronisierungsclient nicht heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="adc4a-133">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="adc4a-134">Auf dem synchronisierungsclient wird eine Benachrichtigung angezeigt, dass die Datei nicht synchronisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="adc4a-134">The sync client will display a notification that the file can't be synced.</span></span>
  

