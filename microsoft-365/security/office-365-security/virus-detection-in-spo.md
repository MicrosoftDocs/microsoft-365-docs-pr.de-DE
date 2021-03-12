---
title: Integrierter Virenschutz in SharePoint Online, OneDrive und Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie SharePoint Online Viren in Dateien erkennt, die Benutzer hochladen, und verhindert, dass Benutzer die Dateien herunterladen oder synchronisieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ba3d19c6b04b93d9b1089540b7483d8b2e7246c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727499"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="ed971-103">Integrierter Virenschutz in SharePoint Online, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed971-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ed971-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="ed971-104">**Applies to**</span></span>
- [<span data-ttu-id="ed971-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ed971-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ed971-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="ed971-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="ed971-107">Microsoft 365 verwendet ein gängiges Virenerkennungsmodul zum Scannen von Dateien, die Benutzer in SharePoint Online, OneDrive und Microsoft Teams hochladen.</span><span class="sxs-lookup"><span data-stu-id="ed971-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="ed971-108">Dieser Schutz ist in allen Abonnements enthalten, die SharePoint Online, OneDrive und Microsoft Teams enthalten.</span><span class="sxs-lookup"><span data-stu-id="ed971-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed971-109">Die integrierten Antivirenfunktionen sind eine Möglichkeit, Viren zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="ed971-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="ed971-110">Sie sind nicht als einzelner Schutzpunkt gegen Schadsoftware für Ihre Umgebung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="ed971-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="ed971-111">Wir ermutigen alle Kunden, den Schutz vor Schadsoftware auf verschiedenen Ebenen zu untersuchen und zu implementieren und bewährte Methoden für die Sicherung ihrer Unternehmensinfrastruktur anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ed971-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="ed971-112">Weitere Informationen zu Strategien und bewährten Methoden finden Sie unter [Security roadmap](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="ed971-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="ed971-113">Was geschieht, wenn eine infizierte Datei in SharePoint Online hochgeladen wird?</span><span class="sxs-lookup"><span data-stu-id="ed971-113">What happens if an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="ed971-114">Das Microsoft 365-Virenerkennungsmodul wird asynchron (unabhängig von Dateiuploads) in SharePoint Online ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed971-114">The Microsoft 365 virus detection engine runs asynchronously (independent from file uploads) within SharePoint Online.</span></span> <span data-ttu-id="ed971-115">**Alle Dateien werden nicht automatisch gescannt.**</span><span class="sxs-lookup"><span data-stu-id="ed971-115">**All files are not automatically scanned**.</span></span> <span data-ttu-id="ed971-116">Heuristiken bestimmen die zu scannenden Dateien.</span><span class="sxs-lookup"><span data-stu-id="ed971-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="ed971-117">Wenn eine Datei gefunden wird, die einen Virus enthält, wird die Datei gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="ed971-117">When a file is found to contain a virus, the file is flagged.</span></span> <span data-ttu-id="ed971-118">Im April 2018 wurde der Grenzwert von 25 MB für gescannte Dateien aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="ed971-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="ed971-119">Dies geschieht:</span><span class="sxs-lookup"><span data-stu-id="ed971-119">Here's what happens:</span></span>

1. <span data-ttu-id="ed971-120">Ein Benutzer lädt eine Datei nach SharePoint Online hoch.</span><span class="sxs-lookup"><span data-stu-id="ed971-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="ed971-121">SharePoint Online bestimmt im Rahmen seiner Virenscanprozesse später, ob die Datei die Kriterien für eine Überprüfung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="ed971-121">SharePoint Online, as part of its virus scanning processes, later determines if the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="ed971-122">Wenn die Datei die Kriterien für eine Überprüfung erfüllt, überprüft das Virenerkennungsmodul die Datei.</span><span class="sxs-lookup"><span data-stu-id="ed971-122">If the file meets the criteria for a scan, the virus detection engine scans the file.</span></span>
4. <span data-ttu-id="ed971-123">Wenn ein Virus in der gescannten Datei gefunden wird, legt das Virenmodul eine Eigenschaft für die Datei fest, die angibt, dass er infiziert ist.</span><span class="sxs-lookup"><span data-stu-id="ed971-123">If a virus is found within the scanned file, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="ed971-124">Was geschieht, wenn ein Benutzer versucht, eine infizierte Datei mithilfe des Browsers herunterzuladen?</span><span class="sxs-lookup"><span data-stu-id="ed971-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="ed971-125">Wenn eine Datei infiziert ist, können Benutzer die Datei nicht über einen Browser von SharePoint Online herunterladen.</span><span class="sxs-lookup"><span data-stu-id="ed971-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="ed971-126">Dies geschieht:</span><span class="sxs-lookup"><span data-stu-id="ed971-126">Here's what happens:</span></span>

1. <span data-ttu-id="ed971-127">Ein Benutzer öffnet einen Webbrowser und versucht, eine infizierte Datei aus SharePoint Online herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ed971-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="ed971-128">Dem Benutzer wird eine Warnung angezeigt, dass ein Virus erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="ed971-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="ed971-129">Standardmäßig hat der Benutzer die Möglichkeit, die Datei herunterzuladen und mithilfe der Antivirensoftware auf seinem eigenen Gerät zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ed971-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="ed971-130">Administratoren können den *Parameter DisallowInfectedFileDownload* im [Cmdlet Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell verwenden, um zu verhindern, dass Benutzer infizierte Dateien herunterladen, auch im Warnungsfenster für Viren.</span><span class="sxs-lookup"><span data-stu-id="ed971-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="ed971-131">Anweisungen finden Sie unter [Use SharePoint Online PowerShell to prevent users from download malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="ed971-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="ed971-132">Sobald Sie den *Parameter DisallowInfectedFileDownload* aktivieren, wird der Zugriff auf die erkannten/blockierten Dateien für Benutzer und Administratoren vollständig blockiert.</span><span class="sxs-lookup"><span data-stu-id="ed971-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="ed971-133">Was geschieht, wenn der #A0 versucht, eine infizierte Datei zu synchronisieren?</span><span class="sxs-lookup"><span data-stu-id="ed971-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="ed971-134">#A0 laden keine Dateien herunter, die Viren enthalten.</span><span class="sxs-lookup"><span data-stu-id="ed971-134">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="ed971-135">Der Synchronisierungsclient zeigt eine Benachrichtigung an, dass die Datei nicht synchronisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ed971-135">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="ed971-136">Erweiterte Funktionen mit Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="ed971-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ed971-137">Microsoft 365-Organisationen, die [Microsoft Defender für Office 365](office-365-atp.md) in ihrem Abonnement enthalten oder als #A0 erworben haben, können sichere Anlagen für SharePoint, OneDrive und Microsoft Teams für erweiterte Berichte und Schutz aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ed971-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](office-365-atp.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="ed971-138">Weitere Informationen finden Sie unter [Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ed971-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="ed971-139">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="ed971-139">Related Articles</span></span>

[<span data-ttu-id="ed971-140">Schutz vor Schadsoftware und Ransomware in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ed971-140">Malware and ransomware protection in Microsoft 365</span></span>](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="ed971-141">Weitere Informationen zum Virenschutz in SharePoint Online, OneDrive und Microsoft Teams finden Sie unter [Schützen](protect-against-threats.md) vor Bedrohungen und Aktivieren sicherer Anlagen für [SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ed971-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
