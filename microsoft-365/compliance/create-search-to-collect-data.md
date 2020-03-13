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
description: ''
ms.openlocfilehash: 47d30cb2da91eff1260ffcf07838bd066917b4a1
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "42610642"
---
# <a name="create-a-search"></a><span data-ttu-id="6f4e0-102">Erstellen einer Suche</span><span class="sxs-lookup"><span data-stu-id="6f4e0-102">Create a search</span></span>

<span data-ttu-id="6f4e0-103">Auf der Registerkarte **Suchen** in Ihrem Fall können Sie eine neue Suche erstellen, indem Sie auf **neue Suche** klicken und dem Assistenten folgen.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

![Der Such-Assistent in einem erweiterten eDiscovery-Fall](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a><span data-ttu-id="6f4e0-105">Benennen Sie die Suche, und geben Sie Ihr eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-105">Name the search and give it a description</span></span>

<span data-ttu-id="6f4e0-106">Jede Suche mit einem Fall sollte einen eindeutigen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-106">Each search with a case should have a unique name.</span></span> <span data-ttu-id="6f4e0-107">Optional können Sie eine Beschreibung für Ihre Suche angeben.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-107">You can optionally provide a description for your search.</span></span> 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a><span data-ttu-id="6f4e0-108">Auswählen der zu durchsuchenden Depotstellen und Freiheits Orte</span><span class="sxs-lookup"><span data-stu-id="6f4e0-108">Choose the custodians and custodial locations to search</span></span>

<span data-ttu-id="6f4e0-109">Wählen Sie Depot inhaltsspeicherorte für die Suche aus, indem Sie die depotverwalter angeben, die Sie dem Fall hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-109">Choose custodian content locations to search by specifying that custodians you have added to the case.</span></span> <span data-ttu-id="6f4e0-110">Wenn Sie eine Depotbank auswählen, führen Sie die Suche anhand aller Datenquellen aus, die der Depotbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-110">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="6f4e0-111">Sie haben auch die Möglichkeit, die Suche für jede Depotbank auf ausgewählte Datenquellen einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-111">You also have the option to narrow the search to selected data sources for each custodian.</span></span> <span data-ttu-id="6f4e0-112">Weitere Informationen zum Hinzufügen von Depotstellen und Verwalten Ihrer Datenquellen finden Sie unter [Arbeiten mit](managing-custodians.md)Betreuern.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-112">For more information about how to add custodians and manage their data sources, see [Work with custodians](managing-custodians.md).</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="6f4e0-113">Auswählen von Speicherorten ohne Freiheitsentzug</span><span class="sxs-lookup"><span data-stu-id="6f4e0-113">Choose non-custodial locations</span></span>

<span data-ttu-id="6f4e0-114">In einigen Fällen möchten Sie möglicherweise Datenquellen durchsuchen, die keiner Depotbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-114">In some cases, you may want to search data sources that are not associated with a custodian.</span></span> <span data-ttu-id="6f4e0-115">In diesem Fall können Sie die Speicherorte angeben, die Sie durchsuchen möchten, oder alle inhaltsspeicherorte nach einem bestimmten Office 365 Dienst durchsuchen (beispielsweisedurch Suchen aller Exchange-Postfächer oder aller SharePoint-Websites und OneDrive-Konten).</span><span class="sxs-lookup"><span data-stu-id="6f4e0-115">In this case, you can specify the locations you want to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint sites and OneDrive accounts).</span></span>

## <a name="define-the-search-query-and-conditions"></a><span data-ttu-id="6f4e0-116">Definieren der Suchabfrage und Bedingungen</span><span class="sxs-lookup"><span data-stu-id="6f4e0-116">Define the search query and conditions</span></span>

<span data-ttu-id="6f4e0-117">Sie können die Stichwörter-Abfrage und alle Bedingungen für die Suche definieren, indem Sie die vordefinierten Bedingungs Karten verwenden oder KQL (Keyword Query Language) verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f4e0-117">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="6f4e0-118">Weitere Informationen finden Sie unter [Erstellen von Suchabfragen](building-search-queries.md).</span><span class="sxs-lookup"><span data-stu-id="6f4e0-118">For more information, see [Build search queries](building-search-queries.md).</span></span>
