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
ms.openlocfilehash: 8c65db566f165939d72429bcd61b7d0a880814e0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196511"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="52165-103">Virenerkennung in SharePoint Online-, OneDrive-und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52165-103">Virus detection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="52165-104">Microsoft 365 kann zum Schutz Ihrer Umgebung vor Schadsoftware beitragen, indem Viren in Dateien erkannt werden, die Benutzer in SharePoint Online, OneDrive und Microsoft Teams hochladen.</span><span class="sxs-lookup"><span data-stu-id="52165-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="52165-105">Dateien werden nach dem Hochladen möglicherweise auf Viren überprüft.</span><span class="sxs-lookup"><span data-stu-id="52165-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="52165-106">Wenn eine Datei als infiziert erkannt wird, wird eine Eigenschaft festgelegt, damit Benutzer die Datei nicht herunterladen oder synchronisieren können.</span><span class="sxs-lookup"><span data-stu-id="52165-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52165-107">Diese Antivirus-Funktionen in SharePoint Online sind eine Möglichkeit, Viren einzudämmen.</span><span class="sxs-lookup"><span data-stu-id="52165-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="52165-108">Sie sind nicht als einzelne Verteidigungspunkte gegen Schadsoftware für Ihre Umgebung gedacht.</span><span class="sxs-lookup"><span data-stu-id="52165-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="52165-109">Wir ermutigen alle Kunden, den Schutz vor Schadsoftware auf verschiedenen Ebenen zu bewerten und zu implementieren und bewährte Methoden für die Sicherung Ihrer Unternehmensinfrastruktur anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="52165-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="52165-110">Weitere Informationen zu Strategien und bewährten Methoden finden Sie unter [Security Roadmap](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="52165-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="52165-111">Was geschieht, wenn eine infizierte Datei in SharePoint Online hochgeladen wird?</span><span class="sxs-lookup"><span data-stu-id="52165-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="52165-112">Microsoft 365 verwendet ein allgemeines Viruserkennungsmodul.</span><span class="sxs-lookup"><span data-stu-id="52165-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="52165-113">Das Modul wird in SharePoint Online asynchron ausgeführt, und einige Dateien werden nach dem Hochladen überprüft.</span><span class="sxs-lookup"><span data-stu-id="52165-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="52165-114">Heuristiken werden verwendet, um zu bestimmen, welche Dateien gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="52165-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="52165-115">Wenn eine Datei gefunden wird, die einen Virus enthält, wird Sie gekennzeichnet, damit Sie nicht erneut heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="52165-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="52165-116">Im April 2018 haben wir den Grenzwert von 25 MB für gescannte Dateien entfernt.</span><span class="sxs-lookup"><span data-stu-id="52165-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="52165-117">Folgendes geschieht:</span><span class="sxs-lookup"><span data-stu-id="52165-117">Here's what happens:</span></span>

1. <span data-ttu-id="52165-118">Ein Benutzer lädt eine Datei in SharePoint Online hoch.</span><span class="sxs-lookup"><span data-stu-id="52165-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="52165-119">SharePoint Online bestimmt, ob die Datei die Kriterien für einen Scan erfüllt.</span><span class="sxs-lookup"><span data-stu-id="52165-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="52165-120">Das Viruserkennungsmodul scannt die Datei.</span><span class="sxs-lookup"><span data-stu-id="52165-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="52165-121">Wenn ein Virus gefunden wird, legt das Virusmodul eine Eigenschaft für die Datei fest, die angibt, dass es infiziert ist.</span><span class="sxs-lookup"><span data-stu-id="52165-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="52165-122">Was geschieht, wenn ein Benutzer versucht, eine infizierte Datei mithilfe des Browsers herunterzuladen?</span><span class="sxs-lookup"><span data-stu-id="52165-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="52165-123">Wenn eine Datei infiziert ist, können Benutzer die Datei nicht über den Browser aus SharePoint Online herunterladen.</span><span class="sxs-lookup"><span data-stu-id="52165-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="52165-124">Folgendes geschieht:</span><span class="sxs-lookup"><span data-stu-id="52165-124">Here's what happens:</span></span>

1. <span data-ttu-id="52165-125">Ein Benutzer öffnet einen Webbrowser und versucht, eine infizierte Datei aus SharePoint Online herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="52165-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="52165-126">Der Benutzer erhält eine Warnung, dass ein Virus erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="52165-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="52165-127">Der Benutzer hat die Möglichkeit, die Datei herunterzuladen und zu versuchen, Sie mit ihrer eigenen Antivirus-Software zu säubern.</span><span class="sxs-lookup"><span data-stu-id="52165-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
>
> <span data-ttu-id="52165-128">Sie können den Parameter *DisallowInfectedFileDownload* im Cmdlet [SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell verwenden, um zu verhindern, dass Benutzer eine infizierte Datei herunterladen, selbst im Fenster Antivirus-Warnung.</span><span class="sxs-lookup"><span data-stu-id="52165-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>
>
> <span data-ttu-id="52165-129">Beachten Sie auch, dass der Zugriff auf die erkannten/blockierten Dateien, sobald Sie den *DisallowInfectedFileDownload* -Parameter aktiviert haben, für Benutzer und Administratoren vollständig blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="52165-129">Also keep in mind, that as soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completly blocked for users and administrators.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="52165-130">Was geschieht, wenn der OneDrive-synchronisierungsclient versucht, eine infizierte Datei zu synchronisieren?</span><span class="sxs-lookup"><span data-stu-id="52165-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="52165-131">Unabhängig davon, ob Benutzer Dateien mit dem neuen OneDrive-synchronisierungsclient (OneDrive.exe) oder dem vorherigen OneDrive für Unternehmen-synchronisierungsclient (Groove.exe) synchronisieren, wenn eine Datei einen Virus enthält, wird Sie vom synchronisierungsclient nicht heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="52165-131">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="52165-132">Auf dem synchronisierungsclient wird eine Benachrichtigung angezeigt, dass die Datei nicht synchronisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="52165-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-office-365-atp"></a><span data-ttu-id="52165-133">Erweiterte Funktionen mit Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="52165-133">Extended capabilities with Office 365 ATP</span></span>

<span data-ttu-id="52165-134">Kunden, die Office 365 ATP für SharePoint, OneDrive und Microsoft Teams aktiviert haben, [aktivieren ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) können das Security & Compliance Center verwenden, um isolierte Dateien für AV-und ATP-Erkennungen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="52165-134">Customers who enabled Office 365 ATP for Sharepoint, OneDrive, and Microsoft Teams [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) are able to use the Security & Compliance Center to manage quarantined files for AV and ATP detections.</span></span> <span data-ttu-id="52165-135">[Nur ATP: Verwenden Sie das Security & Compliance Center, um isolierte Dateien zu verwalten](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="52165-135">[ATP Only: Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="more-information"></a><span data-ttu-id="52165-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52165-136">More information</span></span>

<span data-ttu-id="52165-137">Weitere Informationen zum Konfigurieren von SharePoint Online Antivirus finden Sie unter [Protect Against Threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) und [Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) .</span><span class="sxs-lookup"><span data-stu-id="52165-137">See [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) for more information on how to configure SharePoint Online antivirus.</span></span>


