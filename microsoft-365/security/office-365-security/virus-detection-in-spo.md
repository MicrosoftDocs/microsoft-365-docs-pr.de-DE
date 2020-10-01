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
ms.openlocfilehash: 38d6111fe665e0af79cbd93f534b1058881ff76c
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327987"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="cf544-103">Integrierter Virenschutz in SharePoint Online, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf544-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cf544-104">Microsoft 365 verwendet ein allgemeines Viruserkennungsmodul zum Überprüfen von Dateien, die von Benutzern in SharePoint Online, OneDrive und Microsoft Teams hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="cf544-104">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="cf544-105">Dieser Schutz ist in allen Abonnements enthalten, die SharePoint Online, OneDrive und Microsoft Teams umfassen.</span><span class="sxs-lookup"><span data-stu-id="cf544-105">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf544-106">Die integrierten Antiviren-Funktionen sind eine Möglichkeit, Viren zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cf544-106">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="cf544-107">Sie sind nicht als einzelne Verteidigungspunkte gegen Schadsoftware für Ihre Umgebung gedacht.</span><span class="sxs-lookup"><span data-stu-id="cf544-107">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="cf544-108">Wir ermutigen alle Kunden, den Schutz vor Schadsoftware auf verschiedenen Ebenen zu untersuchen und zu implementieren und bewährte Methoden für die Sicherung Ihrer Unternehmensinfrastruktur anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="cf544-108">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="cf544-109">Weitere Informationen zu Strategien und bewährten Methoden finden Sie unter [Security Roadmap](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="cf544-109">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="cf544-110">Was geschieht, wenn eine infizierte Datei in SharePoint Online hochgeladen wird?</span><span class="sxs-lookup"><span data-stu-id="cf544-110">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="cf544-111">Das Microsoft 365-Viruserkennungsmodul wird in SharePoint Online asynchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cf544-111">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="cf544-112">**Alle Dateien werden beim Hochladen nicht automatisch gescannt**.</span><span class="sxs-lookup"><span data-stu-id="cf544-112">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="cf544-113">Heuristik legt fest, welche Dateien gescannt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cf544-113">Heuristics determine the files to scan.</span></span> <span data-ttu-id="cf544-114">Wenn eine Datei gefunden wird, die einen Virus enthält, wird die Datei gekennzeichnet, sodass Sie nicht erneut heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="cf544-114">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="cf544-115">Im April 2018 haben wir den Grenzwert von 25 MB für gescannte Dateien entfernt.</span><span class="sxs-lookup"><span data-stu-id="cf544-115">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="cf544-116">Folgendes geschieht:</span><span class="sxs-lookup"><span data-stu-id="cf544-116">Here's what happens:</span></span>

1. <span data-ttu-id="cf544-117">Ein Benutzer lädt eine Datei in SharePoint Online hoch.</span><span class="sxs-lookup"><span data-stu-id="cf544-117">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="cf544-118">SharePoint Online bestimmt, ob die Datei die Kriterien für einen Scan erfüllt.</span><span class="sxs-lookup"><span data-stu-id="cf544-118">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="cf544-119">Das Viruserkennungsmodul scannt die Datei.</span><span class="sxs-lookup"><span data-stu-id="cf544-119">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="cf544-120">Wenn ein Virus gefunden wird, legt das Virusmodul eine Eigenschaft für die Datei fest, die angibt, dass es infiziert ist.</span><span class="sxs-lookup"><span data-stu-id="cf544-120">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="cf544-121">Was geschieht, wenn ein Benutzer versucht, eine infizierte Datei mithilfe des Browsers herunterzuladen?</span><span class="sxs-lookup"><span data-stu-id="cf544-121">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="cf544-122">Wenn eine Datei infiziert ist, können Benutzer die Datei nicht mithilfe eines Browsers aus SharePoint Online herunterladen.</span><span class="sxs-lookup"><span data-stu-id="cf544-122">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="cf544-123">Folgendes geschieht:</span><span class="sxs-lookup"><span data-stu-id="cf544-123">Here's what happens:</span></span>

1. <span data-ttu-id="cf544-124">Ein Benutzer öffnet einen Webbrowser und versucht, eine infizierte Datei aus SharePoint Online herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="cf544-124">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="cf544-125">Der Benutzer erhält eine Warnung, dass ein Virus erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="cf544-125">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="cf544-126">Standardmäßig hat der Benutzer die Möglichkeit, die Datei herunterzuladen und zu versuchen, Sie mit der Antivirensoftware auf seinem eigenen Gerät zu säubern.</span><span class="sxs-lookup"><span data-stu-id="cf544-126">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="cf544-127">Administratoren können den Parameter *DisallowInfectedFileDownload* im Cmdlet [SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell verwenden, um zu verhindern, dass Benutzer infizierte Dateien herunterladen, selbst im Fenster Antivirus-Warnung.</span><span class="sxs-lookup"><span data-stu-id="cf544-127">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="cf544-128">Anweisungen finden Sie unter [use SharePoint Online PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="cf544-128">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="cf544-129">Sobald Sie den *DisallowInfectedFileDownload* -Parameter aktiviert haben, wird der Zugriff auf die erkannten/blockierten Dateien für Benutzer und Administratoren vollständig blockiert.</span><span class="sxs-lookup"><span data-stu-id="cf544-129">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="cf544-130">Was geschieht, wenn der OneDrive-synchronisierungsclient versucht, eine infizierte Datei zu synchronisieren?</span><span class="sxs-lookup"><span data-stu-id="cf544-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="cf544-131">OneDrive-Synchronisierungs Clients können keine Dateien herunterladen, die Viren enthalten.</span><span class="sxs-lookup"><span data-stu-id="cf544-131">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="cf544-132">Auf dem synchronisierungsclient wird eine Benachrichtigung angezeigt, dass die Datei nicht synchronisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="cf544-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-office-365-advanced-threat-protection"></a><span data-ttu-id="cf544-133">Erweiterte Funktionen mit Office 365 erweitertem Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="cf544-133">Extended capabilities with Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="cf544-134">Microsoft 365 Organisationen mit [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) , die in Ihrem Abonnement enthalten sind oder als Add-on erworben wurden, können ATP für SharePoint, OneDrive und Microsoft Teams für erweiterte Berichte und Schutz aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cf544-134">Microsoft 365 organizations that have [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) included in their subscription or purchased as an add-on can enable ATP for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="cf544-135">Weitere Informationen finden Sie unter [ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cf544-135">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="more-information"></a><span data-ttu-id="cf544-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cf544-136">More information</span></span>

<span data-ttu-id="cf544-137">Weitere Informationen zum Virenschutz in SharePoint Online, OneDrive und Microsoft Teams finden Sie unter [Protect Against Threats](protect-against-threats.md) und [Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cf544-137">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
