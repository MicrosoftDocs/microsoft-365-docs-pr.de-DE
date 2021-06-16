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
ms.openlocfilehash: 7aa375020ce05ca1d484bb7ed18b8cf7a6e7d04e
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2021
ms.locfileid: "52932842"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="f1c0c-103">Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1c0c-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f1c0c-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="f1c0c-104">**Applies to**</span></span>
- [<span data-ttu-id="f1c0c-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="f1c0c-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f1c0c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1c0c-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f1c0c-107">Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams in Microsoft [Defender für Office 365](whats-new-in-defender-for-office-365.md) bieten eine zusätzliche Schutzebene für Dateien, die bereits zum Uploadzeitpunkt vom [allgemeinen Virenerkennungsmodul in Microsoft 365](virus-detection-in-spo.md)gescannt wurden.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="f1c0c-108">Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams helfen dabei, vorhandene Dateien zu erkennen und zu blockieren, die in Teamwebsites und Dokumentbibliotheken als bösartig erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="f1c0c-109">Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams sind nicht standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="f1c0c-110">Informationen zum Aktivieren finden Sie unter ["Sichere Anlagen aktivieren" für SharePoint, OneDrive und Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f1c0c-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="f1c0c-111">Funktionsweise sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1c0c-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="f1c0c-112">Wenn sichere Anlagen für SharePoint, OneDrive und Microsoft Teams aktiviert sind und eine Datei als bösartig identifiziert wird, wird die Datei durch direkte Integration in die Dateispeicher gesperrt.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="f1c0c-113">Die folgende Abbildung zeigt ein Beispiel für eine in einer Bibliothek erkannten böswilligen Datei.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-113">The following image shows an example of a malicious file detected in a library.</span></span>

![Dateien in OneDrive for Business mit einer als bösartig erkannten Datei](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="f1c0c-115">Obwohl die blockierte Datei weiterhin in der Dokumentbibliothek und in Web-, Mobil- oder Desktopanwendungen aufgeführt ist, können Benutzer die Datei nicht öffnen, kopieren, verschieben oder freigeben.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="f1c0c-116">Sie können die blockierte Datei jedoch löschen.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="f1c0c-117">Hier ist ein Beispiel, wie eine blockierte Datei auf einem mobilen Gerät aussieht:</span><span class="sxs-lookup"><span data-stu-id="f1c0c-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Löschen einer blockierten Datei aus OneDrive for Business aus der OneDrive mobilen App](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="f1c0c-119">Standardmäßig können Benutzer eine blockierte Datei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="f1c0c-120">Das Herunterladen einer blockierten Datei sieht auf einem mobilen Gerät wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f1c0c-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Herunterladen einer blockierten Datei in OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="f1c0c-122">SharePoint Onlineadministratoren können verhindern, dass Benutzer schädliche Dateien herunterladen.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="f1c0c-123">Anweisungen finden Sie unter [Verwenden von SharePoint Online PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)</span><span class="sxs-lookup"><span data-stu-id="f1c0c-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="f1c0c-124">Weitere Informationen zur Benutzererfahrung, wenn eine Datei als bösartig erkannt wurde, finden Sie unter ["Was tun, wenn eine schädliche Datei in SharePoint Online, OneDrive oder Microsoft Teams gefunden wird."](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="f1c0c-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="f1c0c-125">Anzeigen von Informationen zu schädlichen Dateien, die von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams erkannt wurden</span><span class="sxs-lookup"><span data-stu-id="f1c0c-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="f1c0c-126">Dateien, die von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams als bösartig erkannt werden, werden in [Berichten für Microsoft Defender für Office 365](view-reports-for-mdo.md) und im Explorer [(und Echtzeiterkennungen)](threat-explorer.md)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-126">Files that are identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams will show up in [reports for Microsoft Defender for Office 365](view-reports-for-mdo.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="f1c0c-127">Ab Mai 2018 ist eine Datei, die von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams als bösartig erkannt wird, auch in Quarantäne verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-127">As of May 2018, when a file is identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, the file is also available in quarantine.</span></span> <span data-ttu-id="f1c0c-128">Weitere Informationen finden Sie unter [Verwalten von isolierten Dateien in Defender für Office 365.](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="f1c0c-128">For more information, see [Manage quarantined files in Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="f1c0c-129">Beachten Sie diese Punkte</span><span class="sxs-lookup"><span data-stu-id="f1c0c-129">Keep these points in mind</span></span>

- <span data-ttu-id="f1c0c-130">Defender für Office 365 überprüft nicht jede einzelne Datei in SharePoint Online, OneDrive for Business oder Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="f1c0c-131">Es handelt sich hierbei um ein beabsichtigtes Verhalten.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-131">This is by design.</span></span> <span data-ttu-id="f1c0c-132">Dateien werden asynchron gescannt.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="f1c0c-133">Der Prozess verwendet Freigabe- und Gastaktivitätsereignisse zusammen mit intelligenten Heuristiken und Bedrohungssignalen, um schädliche Dateien zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="f1c0c-134">Stellen Sie sicher, dass Ihre SharePoint Websites für die Verwendung der [modernen Benutzeroberfläche](/sharepoint/guide-to-sharepoint-modern-experience)konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-134">Make sure your SharePoint sites are configured to use the [Modern experience](/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="f1c0c-135">Defender für Office 365 Schutz gilt unabhängig davon, ob die moderne oder die klassische Ansicht verwendet wird. Visuelle Indikatoren, die eine Datei blockiert, sind jedoch nur in der modernen Benutzeroberfläche verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="f1c0c-136">Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams sind Teil der allgemeinen Bedrohungsschutzstrategie Ihrer Organisation, die den Schutz vor Spam und Antischadsoftware in Exchange Online Protection (EOP) sowie sichere Links und sichere Anlagen in Microsoft Defender für Office 365 umfasst.</span><span class="sxs-lookup"><span data-stu-id="f1c0c-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f1c0c-137">Weitere Informationen finden Sie unter ["Schutz vor Bedrohungen in Office 365."](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="f1c0c-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
