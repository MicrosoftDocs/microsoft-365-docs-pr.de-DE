---
title: Erstellen einer Suche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informationen zum Erstellen, Definieren und Auswählen von Verwahrern und Verwahrstellen für eine Suche in einem Advanced eDiscovery Fall.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035767"
---
# <a name="create-a-search"></a><span data-ttu-id="663d2-103">Erstellen einer Suche</span><span class="sxs-lookup"><span data-stu-id="663d2-103">Create a search</span></span>

<span data-ttu-id="663d2-104">Auf der **Registerkarte Suchen** in Ihrem Fall können Sie eine neue Suche erstellen, indem Sie auf **Neue** Suche klicken und dem Assistenten folgen.</span><span class="sxs-lookup"><span data-stu-id="663d2-104">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

![Der Suchassistent in einem Advanced eDiscovery Fall](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a><span data-ttu-id="663d2-106">Benennen Sie die Suche, und geben Sie ihr eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="663d2-106">Name the search and give it a description</span></span>

<span data-ttu-id="663d2-107">Jede Suche mit einem Fall sollte einen eindeutigen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="663d2-107">Each search with a case should have a unique name.</span></span> <span data-ttu-id="663d2-108">Sie können optional eine Beschreibung für Ihre Suche bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="663d2-108">You can optionally provide a description for your search.</span></span> 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a><span data-ttu-id="663d2-109">Wählen Sie die zu durchsuchenden Verwahrer und Verwahrer aus.</span><span class="sxs-lookup"><span data-stu-id="663d2-109">Choose the custodians and custodial locations to search</span></span>

<span data-ttu-id="663d2-110">Wählen Sie Speicherorte für verwahrerische Inhalte aus, um zu suchen, indem Sie angeben, welche Verwahrer Sie dem Fall hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="663d2-110">Choose custodian content locations to search by specifying that custodians you have added to the case.</span></span> <span data-ttu-id="663d2-111">Wenn Sie einen Verwahrer auswählen, führen Sie die Suche nach allen Datenquellen aus, die dem Custodian zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="663d2-111">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="663d2-112">Sie haben auch die Möglichkeit, die Suche für jeden Custodian auf ausgewählte Datenquellen zu verenten.</span><span class="sxs-lookup"><span data-stu-id="663d2-112">You also have the option to narrow the search to selected data sources for each custodian.</span></span> <span data-ttu-id="663d2-113">Weitere Informationen zum Hinzufügen von Custodians und zum Verwalten ihrer Datenquellen finden Sie unter [Arbeiten mit Verwahrern](managing-custodians.md).</span><span class="sxs-lookup"><span data-stu-id="663d2-113">For more information about how to add custodians and manage their data sources, see [Work with custodians](managing-custodians.md).</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="663d2-114">Wählen Sie nicht verwahrungsfreie Speicherorte aus</span><span class="sxs-lookup"><span data-stu-id="663d2-114">Choose non-custodial locations</span></span>

<span data-ttu-id="663d2-115">In einigen Fällen können Sie Datenquellen durchsuchen, die keinem Verwahrer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="663d2-115">In some cases, you may want to search data sources that are not associated with a custodian.</span></span> <span data-ttu-id="663d2-116">In diesem Fall können Sie die Speicherorte angeben, die Sie durchsuchen möchten, oder alle Inhaltsspeicherorte nach einem bestimmten Microsoft-Dienst durchsuchen (z. B. alle Exchange-Postfächer oder alle SharePoint-Websites und OneDrive-Konten).</span><span class="sxs-lookup"><span data-stu-id="663d2-116">In this case, you can specify the locations you want to search, or choose to search all content locations for a specific Microsoft service (such as searching all Exchange mailboxes or all SharePoint sites and OneDrive accounts).</span></span>

## <a name="define-the-search-query-and-conditions"></a><span data-ttu-id="663d2-117">Definieren der Suchabfrage und -bedingungen</span><span class="sxs-lookup"><span data-stu-id="663d2-117">Define the search query and conditions</span></span>

<span data-ttu-id="663d2-118">Sie können die Schlüsselwörterabfrage und alle Bedingungen für die Suche mithilfe der vordefinierten Bedingungskarten oder mithilfe von Keyword Query Language (KQL) definieren.</span><span class="sxs-lookup"><span data-stu-id="663d2-118">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="663d2-119">Weitere Informationen finden Sie unter [Erstellen von Suchabfragen](building-search-queries.md).</span><span class="sxs-lookup"><span data-stu-id="663d2-119">For more information, see [Build search queries](building-search-queries.md).</span></span>
