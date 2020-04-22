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
ms.openlocfilehash: 4b740b07b59b7500b8f57584767796b7f31ae87d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635975"
---
# <a name="create-a-search"></a><span data-ttu-id="0b3a3-102">Erstellen einer Suche</span><span class="sxs-lookup"><span data-stu-id="0b3a3-102">Create a search</span></span>

<span data-ttu-id="0b3a3-103">Auf der Registerkarte **Suchen** in Ihrem Fall können Sie eine neue Suche erstellen, indem Sie auf **neue Suche** klicken und dem Assistenten folgen.</span><span class="sxs-lookup"><span data-stu-id="0b3a3-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

![Der Such-Assistent in einem erweiterten eDiscovery-Fall](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a><span data-ttu-id="0b3a3-105">Benennen Sie die Suche, und geben Sie Ihr eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="0b3a3-105">Name the search and give it a description</span></span>

<span data-ttu-id="0b3a3-106">Jede Suche mit einem Fall sollte einen eindeutigen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="0b3a3-106">Each search with a case should have a unique name.</span></span> <span data-ttu-id="0b3a3-107">Optional können Sie eine Beschreibung für Ihre Suche angeben.</span><span class="sxs-lookup"><span data-stu-id="0b3a3-107">You can optionally provide a description for your search.</span></span> 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a><span data-ttu-id="0b3a3-108">Auswählen der zu durchsuchenden Depotstellen und Freiheits Orte</span><span class="sxs-lookup"><span data-stu-id="0b3a3-108">Choose the custodians and custodial locations to search</span></span>

<span data-ttu-id="0b3a3-109">Wählen Sie Depot inhaltsspeicherorte für die Suche aus, indem Sie die depotverwalter angeben, die Sie dem Fall hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="0b3a3-109">Choose custodian content locations to search by specifying that custodians you have added to the case.</span></span> <span data-ttu-id="0b3a3-110">Wenn Sie eine Depotbank auswählen, führen Sie die Suche anhand aller Datenquellen aus, die der Depotbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0b3a3-110">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="0b3a3-111">Sie haben auch die Möglichkeit, die Suche für jede Depotbank auf ausgewählte Datenquellen einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="0b3a3-111">You also have the option to narrow the search to selected data sources for each custodian.</span></span> <span data-ttu-id="0b3a3-112">Weitere Informationen zum Hinzufügen von Depotstellen und Verwalten Ihrer Datenquellen finden Sie unter [Arbeiten mit](managing-custodians.md)Betreuern.</span><span class="sxs-lookup"><span data-stu-id="0b3a3-112">For more information about how to add custodians and manage their data sources, see [Work with custodians](managing-custodians.md).</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="0b3a3-113">Auswählen von Speicherorten ohne Freiheitsentzug</span><span class="sxs-lookup"><span data-stu-id="0b3a3-113">Choose non-custodial locations</span></span>

<span data-ttu-id="0b3a3-114">In einigen Fällen möchten Sie möglicherweise Datenquellen durchsuchen, die keiner Depotbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0b3a3-114">In some cases, you may want to search data sources that are not associated with a custodian.</span></span> <span data-ttu-id="0b3a3-115">In diesem Fall können Sie die Speicherorte angeben, die Sie durchsuchen möchten, oder Sie möchten alle inhaltsspeicherorte für einen bestimmten Microsoft-Dienst durchsuchen (beispielsweisedurch Suchen aller Exchange-Postfächer oder aller SharePoint-Websites und OneDrive-Konten).</span><span class="sxs-lookup"><span data-stu-id="0b3a3-115">In this case, you can specify the locations you want to search, or choose to search all content locations for a specific Microsoft service (such as searching all Exchange mailboxes or all SharePoint sites and OneDrive accounts).</span></span>

## <a name="define-the-search-query-and-conditions"></a><span data-ttu-id="0b3a3-116">Definieren der Suchabfrage und Bedingungen</span><span class="sxs-lookup"><span data-stu-id="0b3a3-116">Define the search query and conditions</span></span>

<span data-ttu-id="0b3a3-117">Sie können die Stichwörter-Abfrage und alle Bedingungen für die Suche definieren, indem Sie die vordefinierten Bedingungs Karten verwenden oder KQL (Keyword Query Language) verwenden.</span><span class="sxs-lookup"><span data-stu-id="0b3a3-117">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="0b3a3-118">Weitere Informationen finden Sie unter [Erstellen von Suchabfragen](building-search-queries.md).</span><span class="sxs-lookup"><span data-stu-id="0b3a3-118">For more information, see [Build search queries](building-search-queries.md).</span></span>
