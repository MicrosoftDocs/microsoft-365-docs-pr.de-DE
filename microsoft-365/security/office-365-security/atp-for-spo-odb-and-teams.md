---
title: ATP für SharePoint, OneDrive und Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Erfahren Sie mehr über Office 365 Advanced Threat Protection für Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams.
ms.openlocfilehash: 9831b61fafc7cb4696fbad3d569f061612f85fe1
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199039"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="3633a-103">ATP für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3633a-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="3633a-104">Übersicht über Office 365 ATP für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3633a-104">Overview of Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="3633a-105">Personen teilen regelmäßig Dateien und arbeiten mit SharePoint, OneDrive und Microsoft Teams zusammen.</span><span class="sxs-lookup"><span data-stu-id="3633a-105">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="3633a-106">Mit [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kann Ihre Organisation auf sichere Weise zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3633a-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner.</span></span> <span data-ttu-id="3633a-107">ATP unterstützt das erkennen und Blockieren von Dateien, die als bösartig identifiziert werden, in Teamwebsites und Dokumentbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="3633a-107">ATP helps detect and block files that are identified as malicious in team sites and document libraries.</span></span>

## <a name="how-office-365-atp-operates"></a><span data-ttu-id="3633a-108">So funktioniert Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="3633a-108">How Office 365 ATP operates</span></span>

<span data-ttu-id="3633a-109">Wenn eine Datei in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams als bösartig identifiziert wurde, wird ATP direkt in die Dateispeicher integriert, um diese Datei zu sperren.</span><span class="sxs-lookup"><span data-stu-id="3633a-109">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file.</span></span> <span data-ttu-id="3633a-110">In der folgenden Abbildung ist ein Beispiel für eine in einer Bibliothek erkannte schädliche Datei dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3633a-110">The following image shows an example of a malicious file detected in a library.</span></span>

![Dateien in OneDrive für Unternehmen mit einem als bösartig erkannt](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="3633a-112">Obwohl die blockierte Datei immer noch in der Dokumentbibliothek und den Webanwendungen, mobilen Anwendungen oder Desktopanwendungen aufgeführt ist, kann die blockierte Datei nicht geöffnet, kopiert, verschoben oder freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3633a-112">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared.</span></span> <span data-ttu-id="3633a-113">Personen können jedoch eine blockierte Datei löschen.</span><span class="sxs-lookup"><span data-stu-id="3633a-113">People can, however, delete a blocked file.</span></span> <span data-ttu-id="3633a-114">Hier ist ein Beispiel dafür, wie das auf dem mobilen Gerät eines Benutzers aussieht:</span><span class="sxs-lookup"><span data-stu-id="3633a-114">Here's an example of what that looks like on a user's mobile device:</span></span>

![Löschen einer gesperrten Datei aus OneDrive für Unternehmen aus dem OneDrive-Mobile App](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="3633a-116">Je nachdem, wie Microsoft 365 konfiguriert ist, haben die Benutzer möglicherweise die Möglichkeit, eine blockierte Datei herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="3633a-116">Depending on how Microsoft 365 is configured, people might or might not have the ability to download a blocked file.</span></span> <span data-ttu-id="3633a-117">Hier sehen Sie, wie das Herunterladen einer gesperrten Datei auf dem mobilen Gerät eines Benutzers aussieht:</span><span class="sxs-lookup"><span data-stu-id="3633a-117">Here's what downloading a blocked file looks like on a user's mobile device:</span></span>

![Herunterladen einer gesperrten Datei in OneDrive für Unternehmen](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="3633a-119">Weitere Informationen finden Sie unter [Office 365 ATP für SharePoint, OneDrive, und Microsoft Teams aktivieren](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="3633a-119">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="3633a-120">Beachten Sie diese Punkte</span><span class="sxs-lookup"><span data-stu-id="3633a-120">Keep these points in mind</span></span>

- <span data-ttu-id="3633a-121">ATP wird nicht jede einzelne Datei in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3633a-121">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="3633a-122">Es handelt sich hierbei um ein beabsichtigtes Verhalten.</span><span class="sxs-lookup"><span data-stu-id="3633a-122">This is by design.</span></span> <span data-ttu-id="3633a-123">Dateien werden asynchron durch einen Prozess überprüft, der Freigabe-und Gast Aktivitätsereignisse zusammen mit intelligenten Heuristiken und Bedrohungs Signalen verwendet, um bösartige Dateien zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="3633a-123">Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="3633a-124">Stellen Sie sicher, dass Ihre SharePoint-Websites so konfiguriert sind, dass Sie die [moderne Benutzeroberfläche](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)verwenden.</span><span class="sxs-lookup"><span data-stu-id="3633a-124">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="3633a-125">Wenn eine Datei als bösartig und blockiert identifiziert wird, können die Benutzer sehen, dass dies in der modernen Benutzeroberfläche aufgetreten ist, jedoch nicht in der klassischen Ansicht.</span><span class="sxs-lookup"><span data-stu-id="3633a-125">When a file is identified as malicious and blocked, people can see that this has occurred in the Modern experience, but not the Classic view.</span></span> <span data-ttu-id="3633a-126">ATP-Schutz wendet an, ob die moderne Erfahrung oder die klassische Ansicht verwendet wird; visuelle Indikatoren, die eine Datei blockiert, sind jedoch nur in der modernen Benutzeroberfläche vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3633a-126">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are present only in the Modern experience.</span></span>

- <span data-ttu-id="3633a-127">Dateien, die in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams als bösartig identifiziert werden, werden in [Berichten für Office 365 Advanced Threat Protection](view-reports-for-atp.md) und in [Explorer (und Echtzeiterkennung)](threat-explorer.md)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3633a-127">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

- <span data-ttu-id="3633a-128">ATP ist Teil der allgemeinen Bedrohungsschutz Strategie Ihrer Organisation, die den Schutz vor Spam und Schadsoftware sowie sichere Links und sichere Anlagen umfasst.</span><span class="sxs-lookup"><span data-stu-id="3633a-128">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments.</span></span> <span data-ttu-id="3633a-129">Weitere Informationen finden Sie unter [Protect Against Threats in Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="3633a-129">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>

- <span data-ttu-id="3633a-130">Ein SharePoint Online Administrator kann bestimmen, ob Personen das Herunterladen von Dateien aktivieren können, die als bösartig erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="3633a-130">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious.</span></span> <span data-ttu-id="3633a-131">Dies erfolgt durch Ausführen des PowerShell-Cmdlets "SPOTenant" mithilfe eines DisallowInfectedFileDownload-Parameters (siehe [aktivieren Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span><span class="sxs-lookup"><span data-stu-id="3633a-131">This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="3633a-132">Quarantäne in ATP für SharePoint Online, OneDrive für Unternehmen und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3633a-132">Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="3633a-133">Ab Ende Mai 2018 werden die [Quarantäne](quarantine-email-messages.md) Funktionen im Security &amp; Compliance Center auf ATP für SharePoint Online, OneDrive für Unternehmen und Microsoft Teams erweitert.</span><span class="sxs-lookup"><span data-stu-id="3633a-133">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="3633a-134">Wenn eine Datei in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams als bösartig erkannt wird, wird die Datei zusätzlich zu ATP blockiert, wenn die Datei geöffnet oder freigegeben wird, und diese Datei wird in eine Liste mit isolierten Elementen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3633a-134">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items.</span></span> <span data-ttu-id="3633a-135">(Im Security &amp; Compliance Center finden Sie unter **Threat Management** \> **Review** \> **Quarantine** und Filter for **Files**.)</span><span class="sxs-lookup"><span data-stu-id="3633a-135">(In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for **Files**.)</span></span>

<span data-ttu-id="3633a-136">Wenn Sie Teil des Microsoft 365 for Business-Sicherheitsteams in Ihrer Organisation sind und über die erforderlichen Berechtigungen verfügen, die [im Security &amp; Compliance Center zugewiesen](permissions-in-the-security-and-compliance-center.md)sind, können Sie Dateien herunterladen, freigeben, melden und löschen, die von ATP als schädlich erkannt werden, aus der Quarantäne heraus.</span><span class="sxs-lookup"><span data-stu-id="3633a-136">If you're part of your organization's Microsoft 365 for business security team and have the necessary [permissions assigned in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>

- <span data-ttu-id="3633a-137">Durch das **Freigeben und melden** einer Datei wird der ATP-Block für die Datei in der jeweiligen Teamwebsite oder Dokumentbibliothek für SharePoint, OneDrive oder Microsoft Teams entfernt.</span><span class="sxs-lookup"><span data-stu-id="3633a-137">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams.</span></span> <span data-ttu-id="3633a-138">Benutzer können die Datei dann öffnen, freigeben und herunterladen.</span><span class="sxs-lookup"><span data-stu-id="3633a-138">Users are then able to open, share, and download the file.</span></span> <span data-ttu-id="3633a-139">Wenn die Option **Bericht an Microsoft senden** ausgewählt ist, wird die Datei als falsch positiv für Microsoft gemeldet.</span><span class="sxs-lookup"><span data-stu-id="3633a-139">And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span>

- <span data-ttu-id="3633a-140">Durch das **Löschen einer Datei** wird die Datei aus der Quarantäne entfernt. die Datei wird jedoch weiterhin blockiert geöffnet oder freigegeben.</span><span class="sxs-lookup"><span data-stu-id="3633a-140">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared.</span></span> <span data-ttu-id="3633a-141">Die Datei muss auch in der entsprechenden Dokumentbibliothek oder Teamwebsite (SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams) gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3633a-141">The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span>

- <span data-ttu-id="3633a-142">Durch das **Herunterladen einer Datei** können Sie die Datei für alle falsch positiven Ergebnisse herunterladen und analysieren.</span><span class="sxs-lookup"><span data-stu-id="3633a-142">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3633a-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3633a-143">Next steps</span></span>

 - [<span data-ttu-id="3633a-144">Aktivieren von Office 365 ATP für SharePoint, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3633a-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)

 - [<span data-ttu-id="3633a-145">Anzeigen von Informationen zu bösartigen Dateien, die in SharePoint, OneDrive oder Microsoft Teams erkannt wurden</span><span class="sxs-lookup"><span data-stu-id="3633a-145">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

