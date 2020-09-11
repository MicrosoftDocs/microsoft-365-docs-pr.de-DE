---
title: Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 26b9ff81-93b0-4251-beaf-3c9f1d7c80c8
description: Informationen zum Verwalten von Microsoft 365-Benutzerkonten,-Lizenzen und-Gruppen mit PowerShell.
ms.openlocfilehash: 0c6ca6a4165b616097405a9de178c254aa489a3c
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429986"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="711ea-103">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="711ea-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="711ea-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="711ea-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="711ea-105">Microsoft 365-Administratoren müssen Benutzerkonten, Lizenzen und Gruppen verwalten.</span><span class="sxs-lookup"><span data-stu-id="711ea-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="711ea-106">Obwohl Sie die meisten dieser Aufgaben im Microsoft 365 Admin Center erledigen können, sind einige einfacher in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="711ea-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="711ea-107">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="711ea-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="711ea-108">Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="711ea-108">User accounts</span></span>

- [<span data-ttu-id="711ea-109">Erstellen von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="711ea-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="711ea-110">Anzeigen von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="711ea-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="711ea-111">Konfigurieren der Eigenschaften von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="711ea-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="711ea-112">Zuweisen von Rollen für Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="711ea-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="711ea-113">Löschen und Wiederherstellen von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="711ea-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="711ea-114">Blockieren von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="711ea-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="711ea-115">Lizenzen und Dienste</span><span class="sxs-lookup"><span data-stu-id="711ea-115">Licenses and services</span></span>
- [<span data-ttu-id="711ea-116">Anzeigen der Lizenzen und Diensten</span><span class="sxs-lookup"><span data-stu-id="711ea-116">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="711ea-117">Anzeigen von lizenzierte und nicht lizenzierten Benutzern</span><span class="sxs-lookup"><span data-stu-id="711ea-117">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="711ea-118">Zuweisen von Lizenzen für Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="711ea-118">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="711ea-119">Anzeigen von Lizenz- und Dienstdetails für Konten</span><span class="sxs-lookup"><span data-stu-id="711ea-119">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="711ea-120">Deaktivieren des Zugriffs auf Dienste</span><span class="sxs-lookup"><span data-stu-id="711ea-120">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="711ea-121">Deaktivieren des Zugriffs auf Sway</span><span class="sxs-lookup"><span data-stu-id="711ea-121">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="711ea-122">Deaktivieren des Zugriffs auf Dienste während des Zuweisens von Benutzerlizenzen</span><span class="sxs-lookup"><span data-stu-id="711ea-122">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="711ea-123">Entfernen von Benutzerlizenzen aus Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="711ea-123">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="711ea-124">Gruppen</span><span class="sxs-lookup"><span data-stu-id="711ea-124">Groups</span></span>
- [<span data-ttu-id="711ea-125">Verwalten von Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="711ea-125">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="711ea-126">Verwalten von Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="711ea-126">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
