---
title: Zuteilungsgrunddaten
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
description: Erfahren Sie mehr über das neue Zuteilungsfeature.
ms.openlocfilehash: 62df346def3fd2577568916d2d668ca50542bdbd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911614"
---
# <a name="allotment-basics"></a><span data-ttu-id="cddf9-103">Zuteilungsgrunddaten</span><span class="sxs-lookup"><span data-stu-id="cddf9-103">Allotment basics</span></span>

<span data-ttu-id="cddf9-104">Mit Lizenzzuweisungen können Sie Lizenzbeschränkungen festlegen und die Verwaltung der Lizenzzuweisung nur auf die von Ihnen ausgewählten Produkte und Lizenzbeschränkungen delegieren.</span><span class="sxs-lookup"><span data-stu-id="cddf9-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="cddf9-105">Zuteilungen verwenden die gruppenbasierte Lizenzierung, um Ihren Benutzern Lizenzen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="cddf9-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="cddf9-106">Lizenzbeschränkungen bieten zusätzliche Kontrolle darüber, wie viele Lizenzen den Benutzern in Ihren Gruppen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="cddf9-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="cddf9-107">Selbst wenn also die Anzahl der Benutzer in Ihren Gruppen zunimmt, können Sie sicherstellen, dass Sie innerhalb des Lizenzlimits bleiben, den Sie für Ihre Zuteilung festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="cddf9-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="cddf9-108">Sie können auch die Verwaltung Ihrer Zuteilungen delegieren.</span><span class="sxs-lookup"><span data-stu-id="cddf9-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="cddf9-109">Delegierte Zuteilungsbesitzer erhalten Zugriff auf das Admin Center, können die Lizenzen jedoch nur in den ihnen eigenen Zuteilungen sehen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="cddf9-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="cddf9-110">Dies ermöglicht eine differenziertere Delegierung der Lizenzverwaltung innerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="cddf9-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cddf9-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cddf9-111">Prerequisites</span></span>

<span data-ttu-id="cddf9-112">Sie müssen die Lizenzierungsanforderungen für die [gruppenbasierte Lizenzierung erfüllen.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="cddf9-112">You must meet the licensing requirements for [group-based licensing](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="cddf9-113">Sie können Zuteilungen mit einem beliebigen Produkt verwenden, das Benutzern zur Verfügung steht:</span><span class="sxs-lookup"><span data-stu-id="cddf9-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="cddf9-114">Office-Suites und eigenständige Produkte</span><span class="sxs-lookup"><span data-stu-id="cddf9-114">Office suites and standalone products</span></span>
- <span data-ttu-id="cddf9-115">Enterprise- und Mobility-Produkte</span><span class="sxs-lookup"><span data-stu-id="cddf9-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="cddf9-116">Dynamics 365-Produkte</span><span class="sxs-lookup"><span data-stu-id="cddf9-116">Dynamics 365 products</span></span>

<span data-ttu-id="cddf9-117">Die folgenden Produkte können nicht mit Zuteilungen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="cddf9-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="cddf9-118">Microsoft Store-Apps</span><span class="sxs-lookup"><span data-stu-id="cddf9-118">Microsoft Store apps</span></span>
- <span data-ttu-id="cddf9-119">Unbefristete Software oder Software, die einem Benutzer direkt zugewiesen ist, wenn keine Lizenz beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="cddf9-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="cddf9-120">Azure-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="cddf9-120">Azure resources</span></span>

<span data-ttu-id="cddf9-121">Sie müssen ein globaler Administrator oder Lizenzadministrator sein, um mit einer Zuteilung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="cddf9-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="cddf9-122">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="cddf9-122">Getting started</span></span>

<span data-ttu-id="cddf9-123">Das Zuteilungsfeature steht nur einer kleinen Anzahl von Kunden in einer privaten Vorschau zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cddf9-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="cddf9-124">Wenn Sie an der Teilnahme interessiert sind, füllen Sie dieses Formular aus: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) .</span><span class="sxs-lookup"><span data-stu-id="cddf9-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>