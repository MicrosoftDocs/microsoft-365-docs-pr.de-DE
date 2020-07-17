---
title: Virenerkennung in SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
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
description: Erfahren Sie, wie SharePoint Online Viren in Dateien erkennt, die von Benutzern hochgeladen werden, und verhindert, dass Benutzer die Dateien herunterladen oder synchronisieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60d696769ea402e6e2d0e52a1f6633e7962b8329
ms.sourcegitcommit: f2275d2fbc17a8b5b5da723c7353d3f36c6fb2a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45029608"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="ec559-103">Virenerkennung in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ec559-103">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="ec559-104">Microsoft 365 kann zum Schutz Ihrer Umgebung vor Schadsoftware beitragen, indem Viren in Dateien erkannt werden, die Benutzer in SharePoint Online hochladen.</span><span class="sxs-lookup"><span data-stu-id="ec559-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="ec559-105">Dateien werden nach dem Hochladen möglicherweise auf Viren überprüft.</span><span class="sxs-lookup"><span data-stu-id="ec559-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="ec559-106">Wenn eine Datei als infiziert erkannt wird, wird eine Eigenschaft festgelegt, damit Benutzer die Datei nicht herunterladen oder synchronisieren können.</span><span class="sxs-lookup"><span data-stu-id="ec559-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec559-107">Diese Antivirus-Funktionen in SharePoint Online sind eine Möglichkeit, Viren einzudämmen.</span><span class="sxs-lookup"><span data-stu-id="ec559-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="ec559-108">Sie sind nicht als einzelne Verteidigungspunkte gegen Schadsoftware für Ihre Umgebung gedacht.</span><span class="sxs-lookup"><span data-stu-id="ec559-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="ec559-109">Wir ermutigen alle Kunden, den Schutz vor Schadsoftware auf verschiedenen Ebenen zu bewerten und zu implementieren und bewährte Methoden für die Sicherung Ihrer Unternehmensinfrastruktur anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ec559-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="ec559-110">Weitere Informationen zu Strategien und bewährten Methoden finden Sie unter [Security Roadmap](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="ec559-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="ec559-111">Was geschieht, wenn eine infizierte Datei in SharePoint Online hochgeladen wird?</span><span class="sxs-lookup"><span data-stu-id="ec559-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="ec559-112">Microsoft 365 verwendet ein allgemeines Viruserkennungsmodul.</span><span class="sxs-lookup"><span data-stu-id="ec559-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="ec559-113">Das Modul wird in SharePoint Online asynchron ausgeführt, und einige Dateien werden nach dem Hochladen überprüft.</span><span class="sxs-lookup"><span data-stu-id="ec559-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="ec559-114">Heuristiken werden verwendet, um zu bestimmen, welche Dateien gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="ec559-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="ec559-115">Wenn eine Datei gefunden wird, die einen Virus enthält, wird Sie gekennzeichnet, damit Sie nicht erneut heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ec559-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="ec559-116">Im April 2018 haben wir den Grenzwert von 25 MB für gescannte Dateien entfernt.</span><span class="sxs-lookup"><span data-stu-id="ec559-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="ec559-117">Folgendes geschieht:</span><span class="sxs-lookup"><span data-stu-id="ec559-117">Here's what happens:</span></span>

1. <span data-ttu-id="ec559-118">Ein Benutzer lädt eine Datei in SharePoint Online hoch.</span><span class="sxs-lookup"><span data-stu-id="ec559-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="ec559-119">SharePoint Online bestimmt, ob die Datei die Kriterien für einen Scan erfüllt.</span><span class="sxs-lookup"><span data-stu-id="ec559-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="ec559-120">Das Viruserkennungsmodul scannt die Datei.</span><span class="sxs-lookup"><span data-stu-id="ec559-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="ec559-121">Wenn ein Virus gefunden wird, legt das Virusmodul eine Eigenschaft für die Datei fest, die angibt, dass es infiziert ist.</span><span class="sxs-lookup"><span data-stu-id="ec559-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="ec559-122">Was geschieht, wenn ein Benutzer versucht, eine infizierte Datei mithilfe des Browsers herunterzuladen?</span><span class="sxs-lookup"><span data-stu-id="ec559-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="ec559-123">Wenn eine Datei infiziert ist, können Benutzer die Datei nicht über den Browser aus SharePoint Online herunterladen.</span><span class="sxs-lookup"><span data-stu-id="ec559-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="ec559-124">Folgendes geschieht:</span><span class="sxs-lookup"><span data-stu-id="ec559-124">Here's what happens:</span></span>

1. <span data-ttu-id="ec559-125">Ein Benutzer öffnet einen Webbrowser und versucht, eine infizierte Datei aus SharePoint Online herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ec559-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="ec559-126">Der Benutzer erhält eine Warnung, dass ein Virus erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="ec559-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="ec559-127">Der Benutzer hat die Möglichkeit, die Datei herunterzuladen und zu versuchen, Sie mit ihrer eigenen Antivirus-Software zu säubern.</span><span class="sxs-lookup"><span data-stu-id="ec559-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
> <span data-ttu-id="ec559-128">Sie können den Parameter *DisallowInfectedFileDownload* im Cmdlet [SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell verwenden, um zu verhindern, dass Benutzer eine infizierte Datei herunterladen, selbst im Fenster Antivirus-Warnung.</span><span class="sxs-lookup"><span data-stu-id="ec559-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="ec559-129">Was geschieht, wenn der OneDrive-synchronisierungsclient versucht, eine infizierte Datei zu synchronisieren?</span><span class="sxs-lookup"><span data-stu-id="ec559-129">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="ec559-130">Unabhängig davon, ob Benutzer Dateien mit dem neuen OneDrive-synchronisierungsclient (OneDrive.exe) oder dem vorherigen OneDrive für Unternehmen-synchronisierungsclient (Groove.exe) synchronisieren, wenn eine Datei einen Virus enthält, wird Sie vom synchronisierungsclient nicht heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="ec559-130">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="ec559-131">Auf dem synchronisierungsclient wird eine Benachrichtigung angezeigt, dass die Datei nicht synchronisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ec559-131">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="more-information"></a><span data-ttu-id="ec559-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec559-132">More information</span></span>

<span data-ttu-id="ec559-133">Weitere Informationen zum Konfigurieren von SharePoint Online Antivirus finden Sie unter [Protect Against Threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) und [Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) .</span><span class="sxs-lookup"><span data-stu-id="ec559-133">See [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) for more information on how to configure SharePoint Online antivirus.</span></span>


