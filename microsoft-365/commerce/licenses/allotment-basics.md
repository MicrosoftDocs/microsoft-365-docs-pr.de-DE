---
title: Zuteilungsgrunddaten
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: ''
ms.custom:
- commerce_licensing
description: Erfahren Sie mehr über das neue Zuteilungsfeature.
ms.date: 03/17/2021
ms.openlocfilehash: 949e06d4bf54405e0045f8c7512a04b1b5cc22c0
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327130"
---
# <a name="allotment-basics"></a><span data-ttu-id="ddf9d-103">Zuteilungsgrunddaten</span><span class="sxs-lookup"><span data-stu-id="ddf9d-103">Allotment basics</span></span>

<span data-ttu-id="ddf9d-104">Mit Lizenzzuweisungen können Sie Lizenzbeschränkungen festlegen und die Verwaltung der Lizenzzuweisung nur auf die von Ihnen ausgewählten Produkte und Lizenzbeschränkungen delegieren.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="ddf9d-105">Zuteilungen verwenden die gruppenbasierte Lizenzierung, um Ihren Benutzern Lizenzen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="ddf9d-106">Lizenzbeschränkungen bieten zusätzliche Kontrolle darüber, wie viele Lizenzen den Benutzern in Ihren Gruppen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="ddf9d-107">Selbst wenn also die Anzahl der Benutzer in Ihren Gruppen zunimmt, können Sie sicherstellen, dass Sie innerhalb des Lizenzlimits bleiben, den Sie für Ihre Zuteilung festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="ddf9d-108">Sie können auch die Verwaltung Ihrer Zuteilungen delegieren.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="ddf9d-109">Delegierte Zuteilungsbesitzer erhalten Zugriff auf das Admin Center, können die Lizenzen jedoch nur in den ihnen eigenen Zuteilungen sehen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="ddf9d-110">Dies ermöglicht eine differenziertere Delegierung der Lizenzverwaltung innerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ddf9d-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ddf9d-111">Prerequisites</span></span>

<span data-ttu-id="ddf9d-112">Sie müssen die Lizenzierungsanforderungen für die [gruppenbasierte Lizenzierung erfüllen.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="ddf9d-112">You must meet the licensing requirements for [group-based licensing](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="ddf9d-113">Sie können Zuteilungen mit einem beliebigen Produkt verwenden, das Benutzern zur Verfügung steht:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="ddf9d-114">Office-Suites und eigenständige Produkte</span><span class="sxs-lookup"><span data-stu-id="ddf9d-114">Office suites and standalone products</span></span>
- <span data-ttu-id="ddf9d-115">Enterprise- und Mobility-Produkte</span><span class="sxs-lookup"><span data-stu-id="ddf9d-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="ddf9d-116">Dynamics 365-Produkte</span><span class="sxs-lookup"><span data-stu-id="ddf9d-116">Dynamics 365 products</span></span>

<span data-ttu-id="ddf9d-117">Die folgenden Produkte können nicht mit Zuteilungen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="ddf9d-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="ddf9d-118">Microsoft Store-Apps</span><span class="sxs-lookup"><span data-stu-id="ddf9d-118">Microsoft Store apps</span></span>
- <span data-ttu-id="ddf9d-119">Unbefristete Software oder Software, die einem Benutzer direkt zugewiesen ist, wenn keine Lizenz beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="ddf9d-120">Azure-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ddf9d-120">Azure resources</span></span>

<span data-ttu-id="ddf9d-121">Sie müssen ein globaler Administrator oder Lizenzadministrator sein, um mit einer Zuteilung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="ddf9d-122">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="ddf9d-122">Getting started</span></span>

<span data-ttu-id="ddf9d-123">Das Zuteilungsfeature steht nur einer kleinen Anzahl von Kunden in einer privaten Vorschau zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ddf9d-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="ddf9d-124">Wenn Sie an der Teilnahme interessiert sind, füllen Sie dieses Formular aus: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) .</span><span class="sxs-lookup"><span data-stu-id="ddf9d-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>