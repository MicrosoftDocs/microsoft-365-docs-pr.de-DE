---
title: Verwalten von SharePoint Online-Websitegruppen mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/17/2019
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: In diesem Artikel finden Sie Verfahren für die Verwendung von PowerShell für Microsoft 365 zum Verwalten von SharePoint Online-Websitegruppen.
ms.openlocfilehash: bcc7a00a6114a6fa2ba8aa02520267bd03a0abf5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909538"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a><span data-ttu-id="ed605-103">Verwalten von SharePoint Online-Websitegruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed605-103">Manage SharePoint Online site groups with PowerShell</span></span>

<span data-ttu-id="ed605-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ed605-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ed605-105">Obwohl Sie das Microsoft 365 Admin Center verwenden können, können Sie auch PowerShell für Microsoft 365 verwenden, um Ihre SharePoint Online-Websitegruppen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="ed605-105">Although you can use the Microsoft 365 admin center, you can also use PowerShell for Microsoft 365 to manage your SharePoint Online site groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ed605-106">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="ed605-106">Before you begin</span></span>

<span data-ttu-id="ed605-107">Für die Verfahren in diesem Artikel müssen Sie eine Verbindung mit SharePoint Online herstellen.</span><span class="sxs-lookup"><span data-stu-id="ed605-107">The procedures in this article require you to connect to SharePoint Online.</span></span> <span data-ttu-id="ed605-108">Weitere Anweisungen finden Sie unter [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="ed605-108">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a><span data-ttu-id="ed605-109">Anzeigen von SharePoint Online mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ed605-109">View SharePoint Online with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="ed605-110">Das SharePoint Online Admin Center verfügt über einige einfach zu verwendende Methoden zum Verwalten von Websitegruppen.</span><span class="sxs-lookup"><span data-stu-id="ed605-110">The SharePoint Online admin center has some easy-to-use methods for managing site groups.</span></span> <span data-ttu-id="ed605-111">Angenommen, Sie möchten die Gruppen und die Gruppenmitglieder für die Website `https://litwareinc.sharepoint.com/sites/finance` betrachten.</span><span class="sxs-lookup"><span data-stu-id="ed605-111">For example, suppose you want to look at the groups, and the group members, for the `https://litwareinc.sharepoint.com/sites/finance` site.</span></span> <span data-ttu-id="ed605-112">Hier sehen Sie, was Sie tun müssen:</span><span class="sxs-lookup"><span data-stu-id="ed605-112">Here's what you have to do to:</span></span>

1. <span data-ttu-id="ed605-113">Klicken Sie im SharePoint Admin Center auf **Aktive Websites,** und klicken Sie dann auf die URL der Website.</span><span class="sxs-lookup"><span data-stu-id="ed605-113">From the SharePoint admin center, click **Active sites**, and then click the URL of the site.</span></span>
2. <span data-ttu-id="ed605-114">Klicken Sie auf der Websiteseite auf **das** Symbol Einstellungen (in der oberen rechten Ecke der Seite), und klicken Sie dann auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="ed605-114">On the site page, click the **Settings** icon (located in the upper right-hand corner of the page), and then click **Site permissions**.</span></span>

<span data-ttu-id="ed605-115">Wiederholen Sie dieses Verfahren für die nächste gewünschte Website.</span><span class="sxs-lookup"><span data-stu-id="ed605-115">And then repeat the process for the next site you want to look at.</span></span>

<span data-ttu-id="ed605-116">Um eine Liste der Gruppen mit PowerShell für Microsoft 365 zu erhalten, können Sie die folgenden Befehle verwenden:</span><span class="sxs-lookup"><span data-stu-id="ed605-116">To get a list of the groups with PowerShell for Microsoft 365, you can use the following commands:</span></span>

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

<span data-ttu-id="ed605-117">Es gibt zwei Möglichkeiten, diesen Befehlssatz in der SharePoint Online-Verwaltungsshell-Eingabeaufforderung auszuführen:</span><span class="sxs-lookup"><span data-stu-id="ed605-117">There are two ways to run this command set in the SharePoint Online Management Shell command prompt:</span></span>

- <span data-ttu-id="ed605-118">Kopieren Sie die Befehle in Editor (oder einen  anderen Text-Editor), ändern Sie den Wert der $siteURL-Variable, wählen Sie die Befehle aus, und fügen Sie sie dann in die Eingabeaufforderung der SharePoint Online-Verwaltungsshell ein.</span><span class="sxs-lookup"><span data-stu-id="ed605-118">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, select the commands, and then paste them into the SharePoint Online Management Shell command prompt.</span></span> <span data-ttu-id="ed605-119">Wenn Sie dies tun, wird PowerShell an einer Eingabeaufforderung **>>** beendet.</span><span class="sxs-lookup"><span data-stu-id="ed605-119">When you do, PowerShell will stop at a **>>** prompt.</span></span> <span data-ttu-id="ed605-120">Drücken Sie die EINGABETASTE, um den Befehl `foreach` auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ed605-120">Press Enter to execute the `foreach` command.</span></span><br/>
- <span data-ttu-id="ed605-121">Kopieren Sie die Befehle in Editor (oder einen anderen Text-Editor), ändern Sie den Wert der **$siteURL** Variable, und speichern Sie dann diese Textdatei mit einem Namen und der Erweiterung „.ps1“ in einem geeigneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="ed605-121">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, and then save this text file with a name and the .ps1 extension in a suitable folder.</span></span> <span data-ttu-id="ed605-122">Führen Sie als Nächstes das Skript über die Eingabeaufforderung der SharePoint Online-Verwaltungsshell aus, indem Sie den Pfad und den Dateinamen angeben.</span><span class="sxs-lookup"><span data-stu-id="ed605-122">Next, run the script from the SharePoint Online Management Shell command prompt by specifying its path and file name.</span></span> <span data-ttu-id="ed605-123">Nachfolgend sehen Sie einen Beispielbefehl:</span><span class="sxs-lookup"><span data-stu-id="ed605-123">Here is an example command:</span></span>

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

<span data-ttu-id="ed605-124">In beiden Fällen wird Folgendes angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ed605-124">In both cases, you should see something similar to this:</span></span>

![SharePoint Online-Websitegruppen](../media/SPO-site-groups.png)

<span data-ttu-id="ed605-126">Dies sind alle Gruppen, die für die Website erstellt wurden, und `https://litwareinc.sharepoint.com/sites/finance` alle Benutzer, die diesen Gruppen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="ed605-126">These are all the groups that have been created for the site `https://litwareinc.sharepoint.com/sites/finance`, and all the users assigned to those groups.</span></span> <span data-ttu-id="ed605-127">Die Gruppennamen werden in gelb dargestellt, damit Sie die Gruppennamen von den Mitgliedern leicht unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="ed605-127">The group names are in yellow to help you separate group names from their members.</span></span>

<span data-ttu-id="ed605-128">Als weiteres Beispiel ist hier ein Befehlssatz, der die Gruppen und alle Gruppenmitgliedschaften für alle SharePoint Online-Websites auflistet.</span><span class="sxs-lookup"><span data-stu-id="ed605-128">As another example, here is a command set that lists the groups, and all the group memberships, for all of your SharePoint Online sites.</span></span>

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title 
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```
    
## <a name="see-also"></a><span data-ttu-id="ed605-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed605-129">See also</span></span>

[<span data-ttu-id="ed605-130">Herstellen einer Verbindung mit SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed605-130">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="ed605-131">Erstellen von SharePoint Online-Websites und Hinzufügen von Benutzern mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed605-131">Create SharePoint Online sites and add users with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="ed605-132">Verwalten von SharePoint Online-Benutzern und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed605-132">Manage SharePoint Online users and groups with PowerShell</span></span>](manage-sharepoint-users-and-groups-with-powershell.md)

[<span data-ttu-id="ed605-133">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed605-133">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ed605-134">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ed605-134">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)