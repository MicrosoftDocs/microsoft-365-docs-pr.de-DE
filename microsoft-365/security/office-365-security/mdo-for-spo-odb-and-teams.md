---
title: Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
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
description: Erfahren Sie mehr über Microsoft Defender für Office 365 für Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80e30a52ef77dad32450bdfecc5010752b199b37
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205534"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e9385-103">Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e9385-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e9385-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="e9385-104">**Applies to**</span></span>
- [<span data-ttu-id="e9385-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="e9385-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e9385-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9385-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e9385-107">Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams in [Microsoft Defender für Office 365](whats-new-in-defender-for-office-365.md) bietet eine zusätzliche Schutzebene für Dateien, die bereits beim Hochladen vom allgemeinen Virenerkennungsmodul in Microsoft [365](virus-detection-in-spo.md)überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="e9385-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="e9385-108">Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams helfen beim Erkennen und Blockieren vorhandener Dateien, die in Teamwebsites und Dokumentbibliotheken als schädlich identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="e9385-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="e9385-109">Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams sind standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e9385-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="e9385-110">Informationen zum Aktivieren finden Sie [unter Aktivieren sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e9385-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="e9385-111">Funktionsweise sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e9385-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="e9385-112">Wenn sichere Anlagen für SharePoint, OneDrive und Microsoft Teams aktiviert sind und eine Datei als bösartig identifiziert wird, wird die Datei mithilfe der direkten Integration in die Dateispeicher gesperrt.</span><span class="sxs-lookup"><span data-stu-id="e9385-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="e9385-113">Die folgende Abbildung zeigt ein Beispiel für eine in einer Bibliothek erkannten böswilligen Datei.</span><span class="sxs-lookup"><span data-stu-id="e9385-113">The following image shows an example of a malicious file detected in a library.</span></span>

![Dateien in OneDrive for Business, bei der eine als schädlich erkannt wurde](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="e9385-115">Obwohl die blockierte Datei weiterhin in der Dokumentbibliothek und in Web-, Mobile- oder Desktopanwendungen aufgeführt ist, können Benutzer die Datei nicht öffnen, kopieren, verschieben oder freigeben.</span><span class="sxs-lookup"><span data-stu-id="e9385-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="e9385-116">Sie können die blockierte Datei jedoch löschen.</span><span class="sxs-lookup"><span data-stu-id="e9385-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="e9385-117">Im Folgenden finden Sie ein Beispiel dafür, wie eine blockierte Datei auf einem mobilen Gerät aussieht:</span><span class="sxs-lookup"><span data-stu-id="e9385-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Löschen einer blockierten Datei aus OneDrive for Business aus der mobilen OneDrive-App](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="e9385-119">Standardmäßig können Benutzer eine blockierte Datei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="e9385-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="e9385-120">So sieht das Herunterladen einer blockierten Datei auf einem mobilen Gerät aus:</span><span class="sxs-lookup"><span data-stu-id="e9385-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Herunterladen einer blockierten Datei in OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="e9385-122">SharePoint Online-Administratoren können verhindern, dass Benutzer schädliche Dateien herunterladen.</span><span class="sxs-lookup"><span data-stu-id="e9385-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="e9385-123">Anweisungen finden Sie unter [Use SharePoint Online PowerShell to prevent users from download malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="e9385-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="e9385-124">Weitere Informationen zur Benutzeroberfläche, wenn eine Datei als schädlich erkannt wurde, finden Sie unter Was tun, wenn eine schädliche Datei [in SharePoint Online, OneDrive](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)oder Microsoft Teams gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="e9385-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e9385-125">Anzeigen von Informationen zu schädlichen Dateien, die von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams erkannt wurden</span><span class="sxs-lookup"><span data-stu-id="e9385-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="e9385-126">Dateien, die von Microsoft Defender für Office 365 als bösartig identifiziert werden, werden in Berichten für [Microsoft Defender für Office 365](view-reports-for-mdo.md) und im Explorer (und Echtzeiterkennungen) [angezeigt.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="e9385-126">Files that are identified as malicious by Microsoft Defender for Office 365 will show up in [reports for Microsoft Defender for Office 365](view-reports-for-mdo.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="e9385-127">Ab Mai 2018, wenn eine Datei von Microsoft Defender für Office 365 als schädlich identifiziert wird, ist die Datei auch in Quarantäne verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e9385-127">As of May 2018, when a file is identified as malicious by Microsoft Defender for Office 365, the file is also available in quarantine.</span></span> <span data-ttu-id="e9385-128">Weitere Informationen finden Sie unter [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="e9385-128">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="e9385-129">Beachten Sie diese Punkte</span><span class="sxs-lookup"><span data-stu-id="e9385-129">Keep these points in mind</span></span>

- <span data-ttu-id="e9385-130">Defender for Office 365 scannt nicht jede einzelne Datei in SharePoint Online, OneDrive for Business oder Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e9385-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="e9385-131">Es handelt sich hierbei um ein beabsichtigtes Verhalten.</span><span class="sxs-lookup"><span data-stu-id="e9385-131">This is by design.</span></span> <span data-ttu-id="e9385-132">Dateien werden asynchron überprüft.</span><span class="sxs-lookup"><span data-stu-id="e9385-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="e9385-133">Der Prozess verwendet Freigabe- und Gastaktivitätsereignisse zusammen mit intelligenten Heuristiken und Bedrohungssignalen, um schädliche Dateien zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e9385-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="e9385-134">Stellen Sie sicher, dass Ihre SharePoint-Websites für die Verwendung der modernen [Benutzung konfiguriert sind.](/sharepoint/guide-to-sharepoint-modern-experience)</span><span class="sxs-lookup"><span data-stu-id="e9385-134">Make sure your SharePoint sites are configured to use the [Modern experience](/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="e9385-135">Defender for Office 365-Schutz gilt unabhängig davon, ob die moderne Oder die klassische Ansicht verwendet wird. Visuelle Indikatoren, dass eine Datei blockiert wird, sind jedoch nur in der modernen Benutzererfahrung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e9385-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="e9385-136">Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams ist Teil der gesamten Strategie zum Schutz vor Bedrohungen In Ihrer Organisation, die Antispam- und Anschmungsschutz in Exchange Online Protection (EOP) sowie sichere Links und sichere Anlagen in Microsoft Defender für Office 365 umfasst.</span><span class="sxs-lookup"><span data-stu-id="e9385-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="e9385-137">Weitere Informationen finden Sie unter [Protect against threats in Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="e9385-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>