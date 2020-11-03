---
title: ATP für SharePoint, OneDrive und Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Erfahren Sie mehr über Microsoft Defender für Office 365 für Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams.
ms.openlocfilehash: 7b007671a7fecb3ae074fd07ce38d17fb025f6b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844332"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="a5226-103">ATP für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a5226-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a5226-104">ATP für SharePoint, OneDrive und Microsoft Teams in [Microsoft Defender für Office 365](office-365-atp.md) bietet eine zusätzliche Schutzschicht für Dateien, die bereits zum Zeitpunkt des Uploads durch das [Allgemeine Viruserkennungsmodul in Microsoft 365](virus-detection-in-spo.md)überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="a5226-104">ATP for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="a5226-105">ATP für SharePoint, OneDrive und Microsoft Teams unterstützt das erkennen und blockieren vorhandener Dateien, die als bösartig identifiziert werden, in Teamwebsites und Dokumentbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="a5226-105">ATP for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="a5226-106">ATP für SharePoint, OneDrive und Microsoft Teams ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a5226-106">ATP for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="a5226-107">Weitere Informationen zum Aktivieren finden Sie unter [Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a5226-107">To turn it on, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="a5226-108">Funktionsweise von ATP für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a5226-108">How ATP for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="a5226-109">Wenn ATP für SharePoint, OneDrive und Microsoft Teams aktiviert ist und eine Datei als bösartig identifiziert, wird die Datei mithilfe der direkten Integration mit den Datei speichern gesperrt.</span><span class="sxs-lookup"><span data-stu-id="a5226-109">When ATP for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="a5226-110">In der folgenden Abbildung ist ein Beispiel für eine in einer Bibliothek erkannte schädliche Datei dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a5226-110">The following image shows an example of a malicious file detected in a library.</span></span>

![Dateien in OneDrive für Unternehmen mit einem als bösartig erkannt](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="a5226-112">Obwohl die blockierte Datei weiterhin in der Dokumentbibliothek und in den Webanwendungen, mobilen oder Desktopanwendungen aufgeführt ist, können die Benutzer die Datei nicht öffnen, kopieren, weiterleiten oder freigeben.</span><span class="sxs-lookup"><span data-stu-id="a5226-112">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="a5226-113">Die blockierte Datei kann jedoch gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="a5226-113">But they can delete the blocked file.</span></span>

<span data-ttu-id="a5226-114">Hier sehen Sie ein Beispiel dafür, wie eine blockierte Datei auf einem mobilen Gerät aussieht:</span><span class="sxs-lookup"><span data-stu-id="a5226-114">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Löschen einer gesperrten Datei aus OneDrive für Unternehmen aus dem OneDrive-Mobile App](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="a5226-116">Standardmäßig können Benutzer eine blockierte Datei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="a5226-116">By default, people can download a blocked file.</span></span> <span data-ttu-id="a5226-117">Hier sehen Sie, was das Herunterladen einer gesperrten Datei auf einem mobilen Gerät aussieht:</span><span class="sxs-lookup"><span data-stu-id="a5226-117">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Herunterladen einer gesperrten Datei in OneDrive für Unternehmen](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="a5226-119">SharePoint Online Administratoren können verhindern, dass Benutzer schädliche Dateien herunterladen.</span><span class="sxs-lookup"><span data-stu-id="a5226-119">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="a5226-120">Anweisungen finden Sie unter [use SharePoint Online PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="a5226-120">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="a5226-121">Weitere Informationen zur Benutzerfreundlichkeit, wenn eine Datei als bösartig erkannt wurde, finden Sie unter [Vorgehensweise, wenn eine schädliche Datei in SharePoint Online, OneDrive oder Microsoft Teams gefunden wird](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="a5226-121">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="a5226-122">Anzeigen von Informationen zu bösartigen Dateien, die von ATP für SharePoint, OneDrive und Microsoft Teams erkannt wurden</span><span class="sxs-lookup"><span data-stu-id="a5226-122">View information about malicious files detected by ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="a5226-123">Dateien, die von Microsoft Defender für Office 365 als bösartig identifiziert werden, werden in [Berichten für Microsoft Defender für Office 365](view-reports-for-atp.md) und in [Explorer (und Echtzeiterkennung)](threat-explorer.md)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5226-123">Files that are identified as malicious by Microsoft Defender for Office 365 will show up in [reports for Microsoft Defender for Office 365](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="a5226-124">Ab dem 2018. Mai wird die Datei auch in der Quarantäne zur Verfügung gestellt, wenn eine Datei von Microsoft Defender für Office 365 als bösartig gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="a5226-124">As of May 2018, when a file is identified as malicious by Microsoft Defender for Office 365, the file is also available in quarantine.</span></span> <span data-ttu-id="a5226-125">Weitere Informationen finden Sie unter [Verwenden des Security & Compliance Center zum Verwalten von isolierten Dateien](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="a5226-125">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="a5226-126">Beachten Sie diese Punkte</span><span class="sxs-lookup"><span data-stu-id="a5226-126">Keep these points in mind</span></span>

- <span data-ttu-id="a5226-127">Defender für Office 365 überprüft nicht jede einzelne Datei in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5226-127">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="a5226-128">Es handelt sich hierbei um ein beabsichtigtes Verhalten.</span><span class="sxs-lookup"><span data-stu-id="a5226-128">This is by design.</span></span> <span data-ttu-id="a5226-129">Dateien werden asynchron gescannt.</span><span class="sxs-lookup"><span data-stu-id="a5226-129">Files are scanned asynchronously.</span></span> <span data-ttu-id="a5226-130">Der Prozess verwendet Freigabe-und Gast Aktivitätsereignisse zusammen mit intelligenten Heuristiken und Bedrohungs Signalen, um bösartige Dateien zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a5226-130">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="a5226-131">Stellen Sie sicher, dass Ihre SharePoint-Websites so konfiguriert sind, dass Sie die [moderne Benutzeroberfläche](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5226-131">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="a5226-132">Defender für Office 365 Schutz gilt, ob die moderne Erfahrung oder die klassische Ansicht verwendet wird; visuelle Indikatoren, die eine Datei blockiert, sind jedoch nur in der modernen Benutzeroberfläche verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a5226-132">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="a5226-133">ATP für SharePoint, OneDrive und Microsoft Teams ist Teil der allgemeinen Bedrohungsschutz Strategie Ihrer Organisation, die den Schutz vor Spam und Antischadsoftware in Exchange Online Protection (EoP) sowie sichere Links und sichere Anlagen in Microsoft Defender für Office 365 enthält.</span><span class="sxs-lookup"><span data-stu-id="a5226-133">ATP for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="a5226-134">Weitere Informationen finden Sie unter [Protect Against Threats in Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="a5226-134">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
