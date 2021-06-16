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
description: Erfahren Sie, wie SharePoint Online Viren in Dateien erkennt, die Benutzer hochladen, und wie Benutzer die Dateien nicht herunterladen oder synchronisieren können.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ab11d4c1e2a064ad0717e6619f72a38b0cbc831
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2021
ms.locfileid: "52932830"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="eefdd-103">Integrierter Virenschutz in SharePoint Online, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eefdd-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eefdd-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="eefdd-104">**Applies to**</span></span>
- [<span data-ttu-id="eefdd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="eefdd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="eefdd-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="eefdd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="eefdd-107">Microsoft 365 verwendet ein gängiges Virenerkennungsmodul zum Scannen von Dateien, die Benutzer in SharePoint Online, OneDrive und Microsoft Teams hochladen.</span><span class="sxs-lookup"><span data-stu-id="eefdd-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="eefdd-108">Dieser Schutz ist in allen Abonnements enthalten, die SharePoint Online, OneDrive und Microsoft Teams enthalten.</span><span class="sxs-lookup"><span data-stu-id="eefdd-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eefdd-109">Die integrierten Antivirenfunktionen stellen eine Möglichkeit dar, Viren einzudämmen.</span><span class="sxs-lookup"><span data-stu-id="eefdd-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="eefdd-110">Sie sind nicht als einzelner Schutz gegen Schadsoftware für Ihre Umgebung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="eefdd-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="eefdd-111">Wir ermutigen alle Kunden, den Schutz vor Schadsoftware auf verschiedenen Ebenen zu untersuchen und zu implementieren und bewährte Methoden zum Sichern ihrer Unternehmensinfrastruktur anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="eefdd-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="eefdd-112">Weitere Informationen zu Strategien und bewährten Methoden finden Sie in der [Sicherheits-Roadmap.](security-roadmap.md)</span><span class="sxs-lookup"><span data-stu-id="eefdd-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="eefdd-113">Was geschieht, wenn eine infizierte Datei in SharePoint Online hochgeladen wird?</span><span class="sxs-lookup"><span data-stu-id="eefdd-113">What happens if an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="eefdd-114">Das Microsoft 365 Virenerkennungsmodul wird asynchron (unabhängig von Dateiuploads) in SharePoint Online ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="eefdd-114">The Microsoft 365 virus detection engine runs asynchronously (independent from file uploads) within SharePoint Online.</span></span> <span data-ttu-id="eefdd-115">**Alle Dateien werden nicht automatisch gescannt.**</span><span class="sxs-lookup"><span data-stu-id="eefdd-115">**All files are not automatically scanned**.</span></span> <span data-ttu-id="eefdd-116">Heuristiken bestimmen die zu scannenden Dateien.</span><span class="sxs-lookup"><span data-stu-id="eefdd-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="eefdd-117">Wenn eine Datei gefunden wird, die einen Virus enthält, wird die Datei gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="eefdd-117">When a file is found to contain a virus, the file is flagged.</span></span> <span data-ttu-id="eefdd-118">Im April 2018 wurde der Grenzwert von 25 MB für gescannte Dateien entfernt.</span><span class="sxs-lookup"><span data-stu-id="eefdd-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="eefdd-119">Dies geschieht:</span><span class="sxs-lookup"><span data-stu-id="eefdd-119">Here's what happens:</span></span>

1. <span data-ttu-id="eefdd-120">Ein Benutzer lädt eine Datei in SharePoint Online hoch.</span><span class="sxs-lookup"><span data-stu-id="eefdd-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="eefdd-121">SharePoint Online ermittelt im Rahmen der Virenüberprüfung später, ob die Datei die Kriterien für eine Überprüfung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="eefdd-121">SharePoint Online, as part of its virus scanning processes, later determines if the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="eefdd-122">Wenn die Datei die Kriterien für eine Überprüfung erfüllt, scannt das Virenerkennungsmodul die Datei.</span><span class="sxs-lookup"><span data-stu-id="eefdd-122">If the file meets the criteria for a scan, the virus detection engine scans the file.</span></span>
4. <span data-ttu-id="eefdd-123">Wenn in der gescannten Datei ein Virus gefunden wird, legt das Virenmodul eine Eigenschaft für die Datei fest, die angibt, dass sie infiziert ist.</span><span class="sxs-lookup"><span data-stu-id="eefdd-123">If a virus is found within the scanned file, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="eefdd-124">Was geschieht, wenn ein Benutzer versucht, eine infizierte Datei mithilfe des Browsers herunterzuladen?</span><span class="sxs-lookup"><span data-stu-id="eefdd-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="eefdd-125">Wenn eine Datei infiziert ist, können Benutzer die Datei nicht über SharePoint Online mithilfe eines Browsers herunterladen.</span><span class="sxs-lookup"><span data-stu-id="eefdd-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="eefdd-126">Dies geschieht:</span><span class="sxs-lookup"><span data-stu-id="eefdd-126">Here's what happens:</span></span>

1. <span data-ttu-id="eefdd-127">Ein Benutzer öffnet einen Webbrowser und versucht, eine infizierte Datei aus SharePoint Online herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="eefdd-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="eefdd-128">Der Benutzer erhält eine Warnung, dass ein Virus erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="eefdd-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="eefdd-129">Standardmäßig erhält der Benutzer die Möglichkeit, die Datei herunterzuladen und zu versuchen, sie mithilfe der Antivirensoftware auf ihrem eigenen Gerät zu bereinigen.</span><span class="sxs-lookup"><span data-stu-id="eefdd-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="eefdd-130">Administratoren können den *Parameter DisallowInfectedFileDownload* im [Cmdlet "Set-SPOTenant"](/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online-PowerShell verwenden, um zu verhindern, dass Benutzer infizierte Dateien herunterladen, auch im Fenster mit Virenwarnungen.</span><span class="sxs-lookup"><span data-stu-id="eefdd-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="eefdd-131">Anweisungen finden Sie unter [Verwenden von SharePoint Online-PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)</span><span class="sxs-lookup"><span data-stu-id="eefdd-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="eefdd-132">Sobald Sie den *Parameter DisallowInfectedFileDownload* aktivieren, wird der Zugriff auf die erkannten/blockierten Dateien für Benutzer und Administratoren vollständig blockiert.</span><span class="sxs-lookup"><span data-stu-id="eefdd-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="eefdd-133">Was geschieht, wenn der OneDrive-Synchronisierungsclient versucht, eine infizierte Datei zu synchronisieren?</span><span class="sxs-lookup"><span data-stu-id="eefdd-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="eefdd-134">Wenn eine schädliche Datei in OneDrive hochgeladen wird, wird sie mit dem lokalen Computer synchronisiert, bevor sie als Schadsoftware gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="eefdd-134">When a malicious file is uploaded to OneDrive, it will be synced to the local machine before it's marked as malware.</span></span> <span data-ttu-id="eefdd-135">Nachdem sie als Schadsoftware gekennzeichnet wurde, kann der Benutzer die synchronisierte Datei nicht mehr auf dem lokalen Computer öffnen.</span><span class="sxs-lookup"><span data-stu-id="eefdd-135">After it's marked as malware, the user can't open the synced file anymore from their local machine.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="eefdd-136">Erweiterte Funktionen mit Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="eefdd-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="eefdd-137">Microsoft 365 Organisationen, die [Microsoft Defender für Office 365](defender-for-office-365.md) in ihrem Abonnement enthalten oder als Add-On erworben haben, können sichere Anlagen für SharePoint, OneDrive und Microsoft Teams für erweiterte Berichterstellung und Schutz aktivieren.</span><span class="sxs-lookup"><span data-stu-id="eefdd-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](defender-for-office-365.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="eefdd-138">Weitere Informationen finden Sie unter ["Sichere Anlagen" für SharePoint, OneDrive und Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="eefdd-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="eefdd-139">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="eefdd-139">Related Articles</span></span>

[<span data-ttu-id="eefdd-140">Schutz vor Schadsoftware und Ransomware in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eefdd-140">Malware and ransomware protection in Microsoft 365</span></span>](/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="eefdd-141">Weitere Informationen zu Virenschutz in SharePoint Online- OneDrive und Microsoft Teams finden Sie unter ["Schutz vor Bedrohungen"](protect-against-threats.md) und [Aktivieren von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="eefdd-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>
