---
title: Multi-Geo-Funktionen in OneDrive und SharePoint Online
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: Erweitern Sie Ihre Microsoft 365-Präsenz auf mehrere geografische Regionen mit Multi-Geo-Funktionen in OneDrive Online.
ms.openlocfilehash: 8f42b071abef0602304f1a468190c33700fe3e82
ms.sourcegitcommit: 321610fd312e5c54ae8a757a71ab0c9fd2f1ac03
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "48995909"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a><span data-ttu-id="c03f5-103">Multi-Geo-Funktionen in OneDrive und SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c03f5-103">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>

<span data-ttu-id="c03f5-104">Multi-Geo-Funktionen in OneDrive und SharePoint Online ermöglichen die Steuerung freigegebener Ressourcen wie SharePoint-Teamwebsites und Microsoft 365-Gruppenpostfächer, die in einem Land oder einer Region gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c03f5-104">Multi-Geo capabilities in OneDrive and SharePoint Online enables control of shared resources like SharePoint team sites and Microsoft 365 Group mailboxes stored at rest in a country or region.</span></span>

<span data-ttu-id="c03f5-105">Benutzer, Gruppenpostfächer und SharePoint-Sites haben Preferred Data Locations (PDLs), die den geografischen Ort für die verknüpften Daten angeben.</span><span class="sxs-lookup"><span data-stu-id="c03f5-105">Each user, Group mailbox, and SharePoint site has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="c03f5-106">Die personenbezogenen Daten von Benutzern (Exchange-Posteingang und OneDrive) können zusammen mit beliebigen Microsoft 365-Gruppen oder SharePoint-Sites, die sie erstellen, am angegebenen geografischen Ort gespeichert werden, um Datenaufbewahrungsanforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c03f5-106">Users' personal data (Exchange mailbox and OneDrive) along with any Microsoft 365 Groups or SharePoint sites that they create can be stored in the specified geo location to meet data residency requirements.</span></span> <span data-ttu-id="c03f5-107">Sie können [verschiedene Administratoren für jeden geografischen Ort angeben](add-a-sharepoint-geo-admin.md).</span><span class="sxs-lookup"><span data-stu-id="c03f5-107">You can [specify different administrators for each geo location](add-a-sharepoint-geo-admin.md).</span></span>

<span data-ttu-id="c03f5-108">Benutzer erhalten die vertraute Oberfläche bei Verwendung von Microsoft 365-Diensten, einschließlich Office-Anwendungen, OneDrive und Suche.</span><span class="sxs-lookup"><span data-stu-id="c03f5-108">Users get a seamless experience when using Microsoft 365 services, including Office applications, OneDrive, and Search.</span></span> <span data-ttu-id="c03f5-109">Details finden Sie unter [Benutzererfahrung in einer Multi-Geo-Umgebung](multi-geo-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="c03f5-109">See [User experience in a multi-geo environment](multi-geo-user-experience.md) for details.</span></span>

## <a name="onedrive"></a><span data-ttu-id="c03f5-110">OneDrive</span><span class="sxs-lookup"><span data-stu-id="c03f5-110">OneDrive</span></span>

<span data-ttu-id="c03f5-111">Das OneDrive jedes Benutzers kann in Einklang mit der PDL an einem Satellitenort bereitgestellt oder [von einem Administrator dorthin verschoben werden](move-onedrive-between-geo-locations.md).</span><span class="sxs-lookup"><span data-stu-id="c03f5-111">Each user's OneDrive can be provisioned in or [moved by an administrator](move-onedrive-between-geo-locations.md) to a satellite location in accordance with the user's PDL.</span></span> <span data-ttu-id="c03f5-112">Persönliche Dateien verbleiben an diesem geografischen Ort, obwohl sie mit Benutzern an anderen geografischen Orten geteilt werden können.</span><span class="sxs-lookup"><span data-stu-id="c03f5-112">Personal files are then kept in that geo location, though they can be shared with users in other geo locations.</span></span>

## <a name="sharepoint-sites-and-groups"></a><span data-ttu-id="c03f5-113">SharePoint-Websites und -Gruppen</span><span class="sxs-lookup"><span data-stu-id="c03f5-113">SharePoint Sites and Groups</span></span>

<span data-ttu-id="c03f5-114">Die Verwaltung des Features "Multi-Geo" steht über das SharePoint Admin Center zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c03f5-114">Management of the Multi-Geo feature is available through the SharePoint admin center.</span></span> <span data-ttu-id="c03f5-115">Ausführliche Informationen finden Sie im [entsprechenden Blogbeitrag](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span><span class="sxs-lookup"><span data-stu-id="c03f5-115">Detailed information can be found in the [corresponding blog post](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span></span>

<span data-ttu-id="c03f5-116">Wenn ein Benutzer eine mit einer SharePoint-Gruppe verbundene Site in einer Multi-Geo-Umgebung erstellt, wird ihre PDL verwendet, um den geografischen Ort zu bestimmen, an dem die Site und ihr zugehöriges Gruppenpostfach erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c03f5-116">When a user creates a SharePoint group-connected site in a multi-geo environment, their PDL is used to determine the geo location where the site and its associated Group mailbox is created.</span></span> <span data-ttu-id="c03f5-117">(Wenn der PDL-Wert des Benutzers nicht festgelegt oder auf den geografischen Ort festgelegt wurde, der nicht als Satellitenort konfiguriert wurde, werden Site und Postfach am zentralen Ort erstellt.)</span><span class="sxs-lookup"><span data-stu-id="c03f5-117">(If the user's PDL value hasn't been set, or has been set to geo location that hasn't been configured as a satellite location, then the site and mailbox are created in the central location.)</span></span>

<span data-ttu-id="c03f5-118">Andere Microsoft 365-Dienste als Exchange, OneDrive und SharePoint sind nicht Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="c03f5-118">Microsoft 365 services other than Exchange, OneDrive, and SharePoint are not Multi-Geo.</span></span> <span data-ttu-id="c03f5-119">Microsoft 365-Gruppen, die jedoch von diesen Diensten erstellt werden, erhalten die PDL des Erstellers. Exchange-Gruppenpostfach und SharePoint O365-Gruppenwebsite werden am entsprechenden geografischen Ort bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c03f5-119">However, Microsoft 365 Groups that are created by these services will be stamped with the PDL of the creator and their Exchange Group mailbox and SharePoint O365 Group Site provisioned in the corresponding geo.</span></span> 

## <a name="managing-the-multi-geo-environment"></a><span data-ttu-id="c03f5-120">Verwalten der Multi-Geo-Umgebung</span><span class="sxs-lookup"><span data-stu-id="c03f5-120">Managing the multi-geo environment</span></span>

<span data-ttu-id="c03f5-121">Das Einrichten und Verwalten Ihrer Multi-Geo-Umgebung erfolgt über das SharePoint-Admin Center.</span><span class="sxs-lookup"><span data-stu-id="c03f5-121">Setting up and managing your multi-geo environment is done through the SharePoint admin center.</span></span> 

![Screenshot der Seite mit geografischen Orten im SharePoint-Admin Center](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="c03f5-123">(Für einige Aktionen wie das Verschieben einer SharePoint- oder OneDrive-Site ist Microsoft PowerShell erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="c03f5-123">(Some actions, such as moving a SharePoint site or a OneDrive site require Microsoft PowerShell.)</span></span>

## <a name="see-also"></a><span data-ttu-id="c03f5-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c03f5-124">See also</span></span>

[<span data-ttu-id="c03f5-125">Multi-Geo in SharePoint- und Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="c03f5-125">Multi-Geo in SharePoint and Microsoft 365 Groups</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[<span data-ttu-id="c03f5-126">Verwalten einer Multi-Geo-Umgebung</span><span class="sxs-lookup"><span data-stu-id="c03f5-126">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="c03f5-127">SharePoint-Speicherkontingente in Multi-Geo-Umgebungen</span><span class="sxs-lookup"><span data-stu-id="c03f5-127">SharePoint storage quotas in multi-geo environments</span></span>](sharepoint-multi-geo-storage-quota.md)

[<span data-ttu-id="c03f5-128">Verwalten von Exchange Online-Postfächern in einer Multi-Geo-Umgebung</span><span class="sxs-lookup"><span data-stu-id="c03f5-128">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
