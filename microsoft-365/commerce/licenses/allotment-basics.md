---
title: Grundlegendes zur Zuteilung
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 22f7c35b1a5baf97fb72f541d57da28adeeffbe4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594686"
---
# <a name="allotment-basics"></a><span data-ttu-id="71e70-103">Grundlegendes zur Zuteilung</span><span class="sxs-lookup"><span data-stu-id="71e70-103">Allotment basics</span></span>

<span data-ttu-id="71e70-104">Durch Lizenz Kontingente können Sie Lizenz Grenzwerte festlegen und die Verwaltung der Lizenzzuweisung nur auf die von Ihnen ausgewählten Produkte und Lizenz Grenzwerte delegieren.</span><span class="sxs-lookup"><span data-stu-id="71e70-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="71e70-105">Kontingente verwenden Gruppenbasierte Lizenzierungen, um Ihren Benutzern Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="71e70-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="71e70-106">Lizenz Grenzwerte bieten zusätzliche Kontrolle darüber, wie viele Lizenzen den Benutzern in ihren Gruppen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="71e70-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="71e70-107">Auch wenn sich die Anzahl der Benutzer in ihren Gruppen erhöht, können Sie sicherstellen, dass Sie innerhalb des Lizenzlimits bleiben, das Sie für Ihre Zuteilung festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="71e70-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="71e70-108">Sie können auch die Verwaltung ihrer Kontingente delegieren.</span><span class="sxs-lookup"><span data-stu-id="71e70-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="71e70-109">Delegierte Zuteilungs Besitzer erhalten Zugriff auf das Admin Center, können die Lizenzen jedoch nur in ihren eigenen Kontingenten anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="71e70-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="71e70-110">Dies bietet eine präzisere Delegierung der Lizenzverwaltung in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="71e70-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="71e70-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="71e70-111">Prerequisites</span></span>

<span data-ttu-id="71e70-112">Sie müssen die Lizenzierungsanforderungen für die [Gruppenbasierte Lizenzierung](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)erfüllen.</span><span class="sxs-lookup"><span data-stu-id="71e70-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="71e70-113">Sie können Kontingente mit allen Office 365 Produkten verwenden, die Benutzern zur Verfügung stehen:</span><span class="sxs-lookup"><span data-stu-id="71e70-113">You can use allotments with any Office 365 product available to users:</span></span>

- <span data-ttu-id="71e70-114">Office-Suiten und eigenständige Produkte</span><span class="sxs-lookup"><span data-stu-id="71e70-114">Office suites and standalone products</span></span>
- <span data-ttu-id="71e70-115">Enterprise-und Mobility-Produkte</span><span class="sxs-lookup"><span data-stu-id="71e70-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="71e70-116">Dynamics 365 Produkte</span><span class="sxs-lookup"><span data-stu-id="71e70-116">Dynamics 365 products</span></span>

<span data-ttu-id="71e70-117">Die folgenden Produkte können nicht mit Kontingenten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="71e70-117">The following products can’t be used with allotments:</span></span>

- <span data-ttu-id="71e70-118">Microsoft Store-Apps</span><span class="sxs-lookup"><span data-stu-id="71e70-118">Microsoft Store apps</span></span>
- <span data-ttu-id="71e70-119">Unbefristete Software oder Software, die einem Benutzer direkt zugewiesen wird, wenn keine Lizenz beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="71e70-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="71e70-120">Azure-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="71e70-120">Azure resources</span></span>

<span data-ttu-id="71e70-121">Sie müssen ein globaler oder Lizenzadministrator sein, um mit einer Zuteilung beginnen zu können.</span><span class="sxs-lookup"><span data-stu-id="71e70-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="71e70-122">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="71e70-122">Getting started</span></span>

<span data-ttu-id="71e70-123">Das Feature Kontingente steht in einer privaten Vorschau nur für eine kleine Anzahl von Kunden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="71e70-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="71e70-124">Wenn Sie an einer Teilnahme interessiert sind, füllen Sie dieses Formular [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup)aus:.</span><span class="sxs-lookup"><span data-stu-id="71e70-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
