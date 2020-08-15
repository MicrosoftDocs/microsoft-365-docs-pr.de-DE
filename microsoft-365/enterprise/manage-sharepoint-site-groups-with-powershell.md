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
description: In diesem Artikel finden Sie Verfahren für die Verwendung von PowerShell für Microsoft 365 zum Verwalten von SharePoint Online Websitegruppen.
ms.openlocfilehash: fa9aff769ff84f8567c45b20c7b6c8a078b4a70c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690744"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a><span data-ttu-id="fe5ae-103">Verwalten von SharePoint Online-Websitegruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe5ae-103">Manage SharePoint Online site groups with PowerShell</span></span>

<span data-ttu-id="fe5ae-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fe5ae-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fe5ae-105">Obwohl Sie das Microsoft 365 Admin Center verwenden können, können Sie auch PowerShell für Microsoft 365 verwenden, um Ihre SharePoint Online Websitegruppen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-105">Although you can use the Microsoft 365 admin center, you can also use PowerShell for Microsoft 365 to manage your SharePoint Online site groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fe5ae-106">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="fe5ae-106">Before you begin</span></span>

<span data-ttu-id="fe5ae-107">Für die Verfahren in diesem Artikel müssen Sie eine Verbindung mit SharePoint Online herstellen.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-107">The procedures in this article require you to connect to SharePoint Online.</span></span> <span data-ttu-id="fe5ae-108">Weitere Anweisungen finden Sie unter [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="fe5ae-108">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a><span data-ttu-id="fe5ae-109">Anzeigen SharePoint Online mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe5ae-109">View SharePoint Online with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="fe5ae-110">Das SharePoint Online Admin Center verfügt über einige einfach zu verwendende Methoden zum Verwalten von Websitegruppen.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-110">The SharePoint Online admin center has some easy-to-use methods for managing site groups.</span></span> <span data-ttu-id="fe5ae-111">Nehmen wir beispielsweise an, Sie möchten die Gruppen und die Gruppenmitglieder für die `https://litwareinc.sharepoint.com/sites/finance` Website betrachten.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-111">For example, suppose you want to look at the groups, and the group members, for the `https://litwareinc.sharepoint.com/sites/finance` site.</span></span> <span data-ttu-id="fe5ae-112">Hier erfahren Sie, wie Sie vorgehen müssen:</span><span class="sxs-lookup"><span data-stu-id="fe5ae-112">Here's what you have to do to:</span></span>

1. <span data-ttu-id="fe5ae-113">Klicken Sie im SharePoint Admin Center auf **aktive Websites**, und klicken Sie dann auf die URL der Website.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-113">From the SharePoint admin center, click **Active sites**, and then click the URL of the site.</span></span>
2. <span data-ttu-id="fe5ae-114">Klicken Sie auf der Seite Website auf das Symbol **Einstellungen** (befindet sich in der rechten oberen Ecke der Seite), und klicken Sie dann auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-114">On the site page, click the **Settings** icon (located in the upper right-hand corner of the page), and then click **Site permissions**.</span></span>

<span data-ttu-id="fe5ae-115">Wiederholen Sie dieses Verfahren für die nächste gewünschte Website.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-115">And then repeat the process for the next site you want to look at.</span></span>

<span data-ttu-id="fe5ae-116">Um eine Liste der Gruppen mit PowerShell für Microsoft 365 zu erhalten, können Sie die folgenden Befehle verwenden:</span><span class="sxs-lookup"><span data-stu-id="fe5ae-116">To get a list of the groups with PowerShell for Microsoft 365, you can use the following commands:</span></span>

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

<span data-ttu-id="fe5ae-117">Es gibt zwei Möglichkeiten zum Ausführen dieses Befehlssatzes in der Eingabeaufforderung der SharePoint Online Verwaltungsshell:</span><span class="sxs-lookup"><span data-stu-id="fe5ae-117">There are two ways to run this command set in the SharePoint Online Management Shell command prompt:</span></span>

- <span data-ttu-id="fe5ae-118">Kopieren Sie die Befehle in Notepad (oder einen anderen Text-Editor), ändern Sie den Wert der **$SiteUrl** -Variablen, wählen Sie die Befehle aus, und fügen Sie Sie dann in die Eingabeaufforderung der SharePoint Online Verwaltungsshell ein.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-118">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, select the commands, and then paste them into the SharePoint Online Management Shell command prompt.</span></span> <span data-ttu-id="fe5ae-119">Wenn Sie dies tun, wird PowerShell an einer **>>** Eingabeaufforderung angehalten.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-119">When you do, PowerShell will stop at a **>>** prompt.</span></span> <span data-ttu-id="fe5ae-120">Drücken Sie die EINGABETASTE, um den `foreach` Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-120">Press Enter to execute the `foreach` command.</span></span><br/>
- <span data-ttu-id="fe5ae-121">Kopieren Sie die Befehle in Editor (oder einen anderen Text-Editor), ändern Sie den Wert der **$siteURL**Variable, und speichern Sie dann diese Textdatei mit einem Namen und der Erweiterung „.ps1“ in einem geeigneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-121">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, and then save this text file with a name and the .ps1 extension in a suitable folder.</span></span> <span data-ttu-id="fe5ae-122">Führen Sie als nächstes das Skript über die Eingabeaufforderung der SharePoint Online Management Shell aus, indem Sie den Pfad und den Dateinamen angeben.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-122">Next, run the script from the SharePoint Online Management Shell command prompt by specifying its path and file name.</span></span> <span data-ttu-id="fe5ae-123">Nachfolgend sehen Sie einen Beispielbefehl:</span><span class="sxs-lookup"><span data-stu-id="fe5ae-123">Here is an example command:</span></span>

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

<span data-ttu-id="fe5ae-124">In beiden Fällen wird Folgendes angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-124">In both cases, you should see something similar to this:</span></span>

![SharePoint Online Websitegruppen](../media/SPO-site-groups.png)

<span data-ttu-id="fe5ae-126">Dies sind alle Gruppen, die für die Website erstellt wurden `https://litwareinc.sharepoint.com/sites/finance` , sowie alle Benutzer, die diesen Gruppen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-126">These are all the groups that have been created for the site `https://litwareinc.sharepoint.com/sites/finance`, and all the users assigned to those groups.</span></span> <span data-ttu-id="fe5ae-127">Die Gruppennamen werden in gelb dargestellt, damit Sie die Gruppennamen von den Mitgliedern leicht unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-127">The group names are in yellow to help you separate group names from their members.</span></span>

<span data-ttu-id="fe5ae-128">Ein weiteres Beispiel ist ein Befehlssatz, der die Gruppen und alle Gruppenmitgliedschaften für alle Ihre SharePoint Online Websites auflistet.</span><span class="sxs-lookup"><span data-stu-id="fe5ae-128">As another example, here is a command set that lists the groups, and all the group memberships, for all of your SharePoint Online sites.</span></span>

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
    
## <a name="see-also"></a><span data-ttu-id="fe5ae-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe5ae-129">See also</span></span>

[<span data-ttu-id="fe5ae-130">Herstellen einer Verbindung mit SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe5ae-130">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="fe5ae-131">Erstellen von SharePoint Online-Websites und Hinzufügen von Benutzern mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe5ae-131">Create SharePoint Online sites and add users with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="fe5ae-132">Verwalten von SharePoint Online-Benutzern und-Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe5ae-132">Manage SharePoint Online users and groups with PowerShell</span></span>](manage-sharepoint-users-and-groups-with-powershell.md)

[<span data-ttu-id="fe5ae-133">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe5ae-133">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fe5ae-134">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe5ae-134">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

