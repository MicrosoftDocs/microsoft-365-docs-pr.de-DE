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
ms.openlocfilehash: ab57bcd3cd21d691e8c2dc669a55588dbcaa886b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595552"
---
# <a name="create-a-search"></a><span data-ttu-id="4e03e-102">Erstellen einer Suche</span><span class="sxs-lookup"><span data-stu-id="4e03e-102">Create a search</span></span>

<span data-ttu-id="4e03e-103">Auf der Registerkarte **Suchen** in Ihrem Fall können Sie eine neue Suche erstellen, indem Sie auf **neue Suche** klicken und dem Assistenten folgen.</span><span class="sxs-lookup"><span data-stu-id="4e03e-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

## <a name="name-your-search-and-give-it-a-description"></a><span data-ttu-id="4e03e-104">Benennen Sie Ihre Suche und geben Sie Ihr eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="4e03e-104">Name your search and give it a description</span></span>

<span data-ttu-id="4e03e-105">Jede Suche mit einem Fall sollte einen eindeutigen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="4e03e-105">Each search with a case should have a unique name.</span></span> <span data-ttu-id="4e03e-106">Optional können Sie eine Beschreibung für Ihre Suche angeben.</span><span class="sxs-lookup"><span data-stu-id="4e03e-106">You can optionally provide a description for your search.</span></span> 

## <a name="define-your-search-query-and-conditions"></a><span data-ttu-id="4e03e-107">Definieren der Suchabfrage und Bedingungen</span><span class="sxs-lookup"><span data-stu-id="4e03e-107">Define your search query and conditions</span></span>

<span data-ttu-id="4e03e-108">Sie können die Stichwörter-Abfrage und alle Bedingungen für die Suche definieren, indem Sie die vordefinierten Bedingungs Karten verwenden oder KQL (Keyword Query Language) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e03e-108">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="4e03e-109">Weitere Informationen finden Sie unter [Erstellen von Suchabfragen](building-search-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4e03e-109">For more information, see [Build search queries](building-search-queries.md).</span></span>

## <a name="choose-the-custodians-to-search-from"></a><span data-ttu-id="4e03e-110">Wählen Sie die zu suchenden Verwalter aus.</span><span class="sxs-lookup"><span data-stu-id="4e03e-110">Choose the custodians to search from</span></span>

<span data-ttu-id="4e03e-111">Nachdem Sie Ihre Bedingungen definiert haben, müssen Sie auswählen, welche Standorte Sie durchsuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="4e03e-111">Once you have defined your conditions, you need to choose which locations you want to search.</span></span> <span data-ttu-id="4e03e-112">Eine Möglichkeit besteht darin, die Verwalter anzugeben, die Sie bereits zu dem Fall hinzugefügt haben, den Sie durchsuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="4e03e-112">One way to do it is by specifying which custodians you have already added to the case you want to search.</span></span> <span data-ttu-id="4e03e-113">Wenn Sie eine Depotbank auswählen, führen Sie die Suche anhand aller Datenquellen aus, die der Depotbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4e03e-113">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="4e03e-114">Weitere Informationen zum Hinzufügen von depotbanks zu Ihrem Fall und zur Verwaltung ihrer Datenquellen finden Sie unter [work with depotbanks](managing-custodians.md) .</span><span class="sxs-lookup"><span data-stu-id="4e03e-114">See [Work with custodians](managing-custodians.md) for more information on how to add custodians to your case and manage their data sources.</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="4e03e-115">Auswählen von Speicherorten ohne Freiheitsentzug</span><span class="sxs-lookup"><span data-stu-id="4e03e-115">Choose non-custodial locations</span></span>

<span data-ttu-id="4e03e-116">In einigen Fällen möchten Sie möglicherweise Datenquellen durchsuchen, die nicht einer Depotbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4e03e-116">In some cases, you may wish to search data sources that are not mapped to a custodian.</span></span> <span data-ttu-id="4e03e-117">In diesem Fall können Sie die Speicherorte angeben, die Sie durchsuchen möchten, oder alle inhaltsspeicherorte nach einem bestimmten Office 365 Dienst durchsuchen (beispielsweisedurch Suchen aller Exchange-Postfächer oder aller SharePoint-und OneDrive für Unternehmen-Websites).</span><span class="sxs-lookup"><span data-stu-id="4e03e-117">In this case, you can specify the locations you would like to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint and OneDrive for Business sites).</span></span>