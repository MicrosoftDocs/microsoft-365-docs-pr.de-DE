---
title: Multi-Geo-Funktionen in Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Erfahren Sie, wie Teams mit Microsoft 365 Multi-Geo funktioniert.
ms.openlocfilehash: 9fe9b289b0ffbef12327c4232b9deb6727b6d718
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362653"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a><span data-ttu-id="c35d8-103">Multi-Geo-Funktionen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c35d8-103">Multi-Geo capabilities in Microsoft Teams</span></span>

<span data-ttu-id="c35d8-104">Multi-Geo-Funktionen in Teams ermöglichen das Speichern Teams Ruhezustands von Chatdaten an einem angegebenen geografischen Standort.</span><span class="sxs-lookup"><span data-stu-id="c35d8-104">Multi-Geo capabilities in Teams enables Teams chat data to be stored at rest in a specified geo location.</span></span> <span data-ttu-id="c35d8-105">Chatdaten bestehen aus Chatnachrichten, einschließlich privater Nachrichten, Kanalnachrichten und Bildern, die in Chats verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c35d8-105">Chat data consists of chat messages, including private messages, channel messages, and images used in chats.</span></span>

<span data-ttu-id="c35d8-106">Teams verwendet den bevorzugten Datenspeicherort (Preferred Data Location, PDL) für Benutzer und Gruppen, um zu bestimmen, wo Daten gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c35d8-106">Teams uses the Preferred Data Location (PDL) for users and groups to determine where to store data.</span></span> <span data-ttu-id="c35d8-107">Wenn der PDL nicht festgelegt ist oder ungültig ist, werden die Daten am zentralen Standort des Mandanten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c35d8-107">If the PDL is not set or is invalid, data is stored in the tenant's central location.</span></span>

## <a name="user-chat"></a><span data-ttu-id="c35d8-108">Benutzerchat</span><span class="sxs-lookup"><span data-stu-id="c35d8-108">User chat</span></span>

<span data-ttu-id="c35d8-109">Der Benutzerchat umfasst 1:1-, 1:n- und private Besprechungsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="c35d8-109">User chat includes one-to-one, one-to-many, and private meeting messages.</span></span>

<span data-ttu-id="c35d8-110">Wenn ein neuer Benutzer erstellt wird, liest Teams den PDL des Benutzers und speichert alle Chatdaten an diesem geografischen Standort.</span><span class="sxs-lookup"><span data-stu-id="c35d8-110">When a new user is created, Teams reads the user's PDL and stores all their chat data in that geo location.</span></span>

<span data-ttu-id="c35d8-111">Wenn ein Administrator für vorhandene Benutzer den PDL für einen Benutzer hinzufügt oder ändert, werden die Chatdaten dieses Benutzers einer Migrationswarteschlange hinzugefügt, um an den angegebenen geografischen Standort verschoben zu werden.</span><span class="sxs-lookup"><span data-stu-id="c35d8-111">For existing users, if an administrator adds or modifies the PDL for a user, that user's chat data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="c35d8-112">Der Speicherort für einen 1:1- oder 1:n-Chat basiert auf dem PDL der Person, die den Chat erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="c35d8-112">The storage location for a one-to-one or one-to-many chat is based on the PDL of the person who created the chat.</span></span> <span data-ttu-id="c35d8-113">Wenn der PDL dieses Benutzers geändert wird, wird der Chat an den neuen geografischen Standort migriert.</span><span class="sxs-lookup"><span data-stu-id="c35d8-113">If that user's PDL is changed, the chat will be migrated to the new geo location.</span></span> <span data-ttu-id="c35d8-114">Der Speicherort für einen Besprechungschat basiert auf dem PDL des Besprechungsorganisators.</span><span class="sxs-lookup"><span data-stu-id="c35d8-114">The storage location for a meeting chat is based on the PDL of the meeting organizer.</span></span>

<span data-ttu-id="c35d8-115">Um den aktuellen Speicherort der Teams Daten eines Benutzers zu finden, [stellen Sie eine Verbindung mit Teams PowerShell her,](/powershell/module/teams/connect-microsoftteams) und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c35d8-115">To find the current location of a user's Teams data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a><span data-ttu-id="c35d8-116">Kanalnachrichten</span><span class="sxs-lookup"><span data-stu-id="c35d8-116">Channel messages</span></span>

<span data-ttu-id="c35d8-117">Jede Microsoft 365 Gruppe verfügt über einen bevorzugten Datenspeicherort (Preferred Data Location, PDL), der den geografischen Standort angibt, an dem verwandte Daten gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c35d8-117">Each Microsoft 365 group has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="c35d8-118">Teams verwendet den PDL für die Gruppe, die jedem Team zugeordnet ist, um zu bestimmen, wo Kanalnachrichtendaten für dieses Team gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c35d8-118">Teams uses the PDL for the group associated with each team to determine where to store channel messaging data for that team.</span></span> <span data-ttu-id="c35d8-119">Dies schließt Chats ein, die innerhalb einer Kanalbesprechung stattfinden.</span><span class="sxs-lookup"><span data-stu-id="c35d8-119">This includes chat that occurs within a channel meeting.</span></span>

<span data-ttu-id="c35d8-120">Wenn ein Benutzer ein neues Team erstellt, bestimmt der PDL dieses Benutzers, welcher PDL der Microsoft 365 Gruppe zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c35d8-120">When a user creates a new team, that user's PDL determines what PDL is assigned to the Microsoft 365 group.</span></span> <span data-ttu-id="c35d8-121">Der Gruppen-PDL bestimmt, wo die Daten dieses Teams gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c35d8-121">The group PDL determines where that team's data is stored.</span></span> <span data-ttu-id="c35d8-122">Wenn sich der PDL dieses Benutzers später ändert, wird der PDL der Gruppe nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="c35d8-122">If that user's PDL later changes, the group's PDL is not changed.</span></span>

<span data-ttu-id="c35d8-123">Wenn ein Administrator für vorhandene Teams den PDL für die Microsoft 365 Gruppe hinzufügt oder ändert, die ein Team unterstützt, werden die Kanalnachrichtendaten dieses Teams einer Migrationswarteschlange hinzugefügt, um an den angegebenen geografischen Standort verschoben zu werden.</span><span class="sxs-lookup"><span data-stu-id="c35d8-123">For existing teams, if an administrator adds or modifies the PDL for the Microsoft 365 group that backs a team, that team's channel messaging data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="c35d8-124">Wenn Sie den PDL der Microsoft 365-Gruppe ändern, werden die Teams Daten in die Warteschlange für die Migration an den ausgewählten Speicherort gestellt.</span><span class="sxs-lookup"><span data-stu-id="c35d8-124">Changing the PDL of the Microsoft 365 group queues the Teams data to migrate to the chosen location.</span></span> <span data-ttu-id="c35d8-125">Dadurch wird jedoch nicht automatisch die SharePoint Website oder dateien migriert, die der Gruppe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c35d8-125">However, this does not migrate the SharePoint site or files associated with the Group automatically.</span></span> <span data-ttu-id="c35d8-126">Sie müssen die Website separat verschieben, indem Sie die Verfahren unter [Verschieben eines SharePoint-Standorts an einen anderen geografischen Standort](/microsoft-365/enterprise/move-sharepoint-between-geo-locations)ausführen.</span><span class="sxs-lookup"><span data-stu-id="c35d8-126">You must move the site separately by following the procedures in [Move a SharePoint site to a different geo location](/microsoft-365/enterprise/move-sharepoint-between-geo-locations).</span></span> <span data-ttu-id="c35d8-127">Führen Sie beide Schritte aus, um zu vermeiden, dass Daten Teams und Daten für eine Gruppe an unterschiedlichen Speicherorten SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c35d8-127">Be sure to do both steps to avoid Teams data and SharePoint data for one group in different locations.</span></span>

<span data-ttu-id="c35d8-128">Um den aktuellen Speicherort der Daten eines Teams zu finden, [stellen Sie eine Verbindung mit Teams PowerShell](/powershell/module/teams/connect-microsoftteams) her, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c35d8-128">To find the current location of a team's data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a><span data-ttu-id="c35d8-129">Benutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="c35d8-129">User Experience</span></span>

<span data-ttu-id="c35d8-130">Teams Multi-Geo ist nahtlos für den Endbenutzer.</span><span class="sxs-lookup"><span data-stu-id="c35d8-130">Teams Multi-Geo is seamless to the end user.</span></span> <span data-ttu-id="c35d8-131">Sobald Sie den PDL eines Benutzers oder einer Gruppe geändert haben, werden die entsprechenden Daten für die Migration in die Warteschlange warteschlangen, und die Migration erfolgt automatisch ohne Auswirkung auf den Benutzer oder den Teams Client, auch wenn sie während der Migration aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="c35d8-131">Once you change the PDL of a user or a group, the respective data will queue for migration and the migration will occur automatically with no impact to the user or their Teams client even if they are active while the migration occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="c35d8-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c35d8-132">See also</span></span>

[<span data-ttu-id="c35d8-133">Microsoft 365 Multi-Geo-Mandantenkonfiguration</span><span class="sxs-lookup"><span data-stu-id="c35d8-133">Microsoft 365 Multi-Geo tenant configuration</span></span>](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[<span data-ttu-id="c35d8-134">Verwalten einer Multi-Geo-Umgebung</span><span class="sxs-lookup"><span data-stu-id="c35d8-134">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="c35d8-135">Verwalten von Exchange Online-Postfächern in einer Multi-Geo-Umgebung</span><span class="sxs-lookup"><span data-stu-id="c35d8-135">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
