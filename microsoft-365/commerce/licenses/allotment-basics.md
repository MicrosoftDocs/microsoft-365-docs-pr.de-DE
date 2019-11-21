---
title: Grundlegendes zur Zuteilung
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: ''
description: Erfahren Sie mehr über das Feature neue Kontingente.
ms.openlocfilehash: fff63b3c61ad95696e7f7677a34154ad65e82259
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "38753574"
---
# <a name="allotment-basics"></a><span data-ttu-id="057e4-103">Grundlegendes zur Zuteilung</span><span class="sxs-lookup"><span data-stu-id="057e4-103">Allotment basics</span></span>

<span data-ttu-id="057e4-104">Durch Lizenz Kontingente können Sie Lizenz Grenzwerte festlegen und die Verwaltung der Lizenzzuweisung nur auf die von Ihnen ausgewählten Produkte und Lizenz Grenzwerte delegieren.</span><span class="sxs-lookup"><span data-stu-id="057e4-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="057e4-105">Kontingente verwenden Gruppenbasierte Lizenzierungen, um Ihren Benutzern Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="057e4-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="057e4-106">Lizenz Grenzwerte bieten zusätzliche Kontrolle darüber, wie viele Lizenzen den Benutzern in ihren Gruppen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="057e4-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="057e4-107">Auch wenn sich die Anzahl der Benutzer in ihren Gruppen erhöht, können Sie sicherstellen, dass Sie innerhalb des Lizenzlimits bleiben, das Sie für Ihre Zuteilung festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="057e4-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="057e4-108">Sie können auch die Verwaltung ihrer Kontingente delegieren.</span><span class="sxs-lookup"><span data-stu-id="057e4-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="057e4-109">Delegierte Zuteilungs Besitzer erhalten Zugriff auf das Admin Center, können die Lizenzen jedoch nur in ihren eigenen Kontingenten anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="057e4-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="057e4-110">Dies bietet eine präzisere Delegierung der Lizenzverwaltung in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="057e4-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="057e4-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="057e4-111">Prerequisites</span></span>

<span data-ttu-id="057e4-112">Sie müssen die Lizenzierungsanforderungen für die [Gruppenbasierte Lizenzierung](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)erfüllen.</span><span class="sxs-lookup"><span data-stu-id="057e4-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="057e4-113">Sie können Kontingente mit allen Office 365 Produkten verwenden, die Benutzern zur Verfügung stehen:</span><span class="sxs-lookup"><span data-stu-id="057e4-113">You can use allotments with any Office 365 product available to users:</span></span>

- <span data-ttu-id="057e4-114">Office-Suiten und eigenständige Produkte</span><span class="sxs-lookup"><span data-stu-id="057e4-114">Office suites and standalone products</span></span>
- <span data-ttu-id="057e4-115">Enterprise-und Mobility-Produkte</span><span class="sxs-lookup"><span data-stu-id="057e4-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="057e4-116">Dynamics 365 Produkte</span><span class="sxs-lookup"><span data-stu-id="057e4-116">Dynamics 365 products</span></span>

<span data-ttu-id="057e4-117">Die folgenden Produkte können nicht mit Kontingenten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="057e4-117">The following products can’t be used with allotments:</span></span>

- <span data-ttu-id="057e4-118">Microsoft Store-Apps</span><span class="sxs-lookup"><span data-stu-id="057e4-118">Microsoft Store apps</span></span>
- <span data-ttu-id="057e4-119">Unbefristete Software oder Software, die einem Benutzer direkt zugewiesen wird, wenn keine Lizenz beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="057e4-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="057e4-120">Azure-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="057e4-120">Azure resources</span></span>

<span data-ttu-id="057e4-121">Sie müssen ein globaler oder Lizenzadministrator sein, um mit einer Zuteilung beginnen zu können.</span><span class="sxs-lookup"><span data-stu-id="057e4-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="057e4-122">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="057e4-122">Getting started</span></span>

<span data-ttu-id="057e4-123">Das Feature Kontingente steht in einer privaten Vorschau nur für eine kleine Anzahl von Kunden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="057e4-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="057e4-124">Wenn Sie an einer Teilnahme interessiert sind, füllen Sie dieses Formular [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup)aus:.</span><span class="sxs-lookup"><span data-stu-id="057e4-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
