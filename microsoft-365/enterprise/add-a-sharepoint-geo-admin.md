---
title: Hinzufügen oder Entfernen eines Geo-Administrators
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Müssen separate Administratoren für jeden geografischen Standort konfiguriert werden? So fügen Sie eine Geo-Administrator in Microsoft 365 Multi-Geo hinzu oder entfernen ihn.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9a3d916bfec2c53850f923fb5322298e9ff440ca
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690861"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a><span data-ttu-id="4c636-104">Hinzufügen oder Entfernen eines Geo-Administrators in Microsoft 365 Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="4c636-104">Add or remove a geo administrator in Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="4c636-105">Sie können für jeden geographischen Standort in Ihrem Mandanten einen eigenen Administrator festlegen.</span><span class="sxs-lookup"><span data-stu-id="4c636-105">You can configure separate administrators for each geo location that you have in your tenant.</span></span> <span data-ttu-id="4c636-106">Dieser Administrator hat Zugriff auf SharePoint Online- und OneDrive-Einstellungen, die für seinen geographischen Standort gelten.</span><span class="sxs-lookup"><span data-stu-id="4c636-106">These administrators will have access to the SharePoint Online and OneDrive settings that are specific to their geo location.</span></span>

<span data-ttu-id="4c636-107">Einige Dienste – wie Terminologiespeicher – werden an einem zentralen Standort verwaltet und an Satellitenstandorten repliziert.</span><span class="sxs-lookup"><span data-stu-id="4c636-107">Some services - such as the term store - are administered from the central location and replicated to satellite locations.</span></span> <span data-ttu-id="4c636-108">Der Geo-Administrator des zentralen Standorts hat Zugriff auf diese, was für Administratoren von Satellitenstandorten nicht gilt.</span><span class="sxs-lookup"><span data-stu-id="4c636-108">The geo admin for the central location has access to these, whereas geo admins for satellite locations don't.</span></span>

<span data-ttu-id="4c636-109">Globale Administratoren und SharePoint-Onlineadministratoren haben weiterhin Zugriff auf Einstellungen am zentralen Standort und allen Satellitenstandorten.</span><span class="sxs-lookup"><span data-stu-id="4c636-109">Global administrators and SharePoint Online administrators continue to have access to settings in the central location and all satellite locations.</span></span>

## <a name="configuring-geo-administrators"></a><span data-ttu-id="4c636-110">Konfigurieren von Geo-Administratoren</span><span class="sxs-lookup"><span data-stu-id="4c636-110">Configuring geo administrators</span></span>

<span data-ttu-id="4c636-111">Für das Konfigurieren von Geo-Administratoren ist das SharePoint Online-PowerShell-Modul erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4c636-111">Configuring geo admins requires SharePoint Online PowerShell module.</span></span>

<span data-ttu-id="4c636-112">Verwenden Sie [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService), um eine Verbindung zum Administrationscenter des geographischen Standorts herzustellen, an dem Sie den Geo-Administrator hinzufügen möchten (zum Beispiel Connect-SPOService https://ContosoEUR-admin.sharepoint.com.))</span><span class="sxs-lookup"><span data-stu-id="4c636-112">Use [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService) to connect to the admin center of the geo location where you want to add the geo admin. (For example, Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)</span></span>

<span data-ttu-id="4c636-113">Führen Sie `Get-SPOGeoAdministrator` aus, um die vorhandenen Geo-Administratoren eines Standorts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c636-113">To view the existing geo admins of a location, run `Get-SPOGeoAdministrator`</span></span>

### <a name="adding-a-user-as-a-geo-admin"></a><span data-ttu-id="4c636-114">Einen Benutzer als Geo-Administrator hinzufügen</span><span class="sxs-lookup"><span data-stu-id="4c636-114">Adding a user as a geo admin</span></span>

<span data-ttu-id="4c636-115">Führen Sie `Add-SPOGeoAdministrator -UserPrincipalName <UPN>` aus, um einen Benutzer als Geo-Administrator hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4c636-115">To add a user as a geo admin, run `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

<span data-ttu-id="4c636-116">Führen Sie `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>` aus, um einen Benutzer als Geo-Administrator zu entfernen</span><span class="sxs-lookup"><span data-stu-id="4c636-116">To remove a user as a Geo Admin of a location, run  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

### <a name="adding-a-group-as-a-geo-admin"></a><span data-ttu-id="4c636-117">Eine Gruppe als Geo-Administrator hinzufügen</span><span class="sxs-lookup"><span data-stu-id="4c636-117">Adding a group as a geo admin</span></span>

<span data-ttu-id="4c636-118">Sie können eine Sicherheitsgruppe oder eine E-Mail-aktivierte Sicherheitsgruppe als Geo-Administrator hinzufügen. (Verteilergruppen und Microsoft 365-Gruppen werden nicht unterstützt.)</span><span class="sxs-lookup"><span data-stu-id="4c636-118">You can add a security group or a mail-enabled security group as a geo admin. (Distribution groups and Microsoft 365 Groups are not supported.)</span></span>

<span data-ttu-id="4c636-119">Führen Sie `Add-SPOGeoAdministrator -GroupAlias <alias>` aus, um eine Gruppe als Geo-Administrator hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4c636-119">To add a group as a geo administrator, run `Add-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="4c636-120">Führen Sie `Remove-SPOGeoAdministrator -GroupAlias <alias>` aus, um eine Gruppe als Geo-Administrator zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="4c636-120">To remove a group as a geo administrator, run `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="4c636-121">Beachten Sie, dass nicht alle Sicherheitsgruppen einen Gruppenalias besitzen.</span><span class="sxs-lookup"><span data-stu-id="4c636-121">Note that not all security groups have a group alias.</span></span> <span data-ttu-id="4c636-122">Wenn Sie eine Sicherheitsgruppe hinzufügen möchten, die keinen Alias besitzt, führen Sie [Get-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) aus, um eine Liste der Gruppen anzurufen. Suchen Sie nach der ObjectID Ihrer Sicherheitsgruppe Sie dann Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4c636-122">If you want to add a security group that does not have an alias, run [Get-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) to retrieve a list of groups, find your security group's ObjectID, and then run:</span></span>

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

<span data-ttu-id="4c636-123">Führen Sie `Remove-SPOGeoAdministrator -ObjectID <ObjectID>` aus, um eine Gruppe anhand der ObjectID zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="4c636-123">To remove a group by using the ObjectID, run `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="4c636-124">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4c636-124">Related topics</span></span>

[<span data-ttu-id="4c636-125">Add-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="4c636-125">Add-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/add-spogeoadministrator)

[<span data-ttu-id="4c636-126">Get-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="4c636-126">Get-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spogeoadministrator)

[<span data-ttu-id="4c636-127">Remove-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="4c636-127">Remove-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spogeoadministrator)

[<span data-ttu-id="4c636-128">Legen Sie einen Alias ("MailNickName") für eine Sicherheitsgruppe fest</span><span class="sxs-lookup"><span data-stu-id="4c636-128">Set an alias (MailNickName) for a security group</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup)