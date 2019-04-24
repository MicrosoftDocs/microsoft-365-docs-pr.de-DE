---
title: Installieren von Microsoft Project oder Microsoft Visio auf verwalteten Desktop Geräten von Microsoft
description: Informationen zum Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5c820e36b7b397fe770216ee229e38a1da5b034d
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288996"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="cde99-104">Installieren von Microsoft Project oder Microsoft Visio auf verwalteten Desktop Geräten von Microsoft</span><span class="sxs-lookup"><span data-stu-id="cde99-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="cde99-105">Microsoft Project und Microsoft Visio erfordern bestimmte Schritte für die Installation auf Microsoft-Desktop Geräten.</span><span class="sxs-lookup"><span data-stu-id="cde99-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="cde99-106">In diesem Thema werden die Voraussetzungen und der Installationsvorgang für diese Anwendungen dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="cde99-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cde99-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cde99-107">Prerequisites</span></span>

<span data-ttu-id="cde99-108">Administratoren sollten überprüfen, ob Sie diese Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="cde99-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="cde99-109">**Lizenzmengen** – die richtige Menge an Microsoft Project-und Microsoft Visio-Lizenzen muss für Ihre Benutzer verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="cde99-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="cde99-110">Microsoft Managed Desktop unterstützt derzeit nur 64-Bit-Versionen dieser Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="cde99-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="cde99-111">**Lizenznamen** – die entsprechenden Lizenznamen für diese Anwendungen sind:</span><span class="sxs-lookup"><span data-stu-id="cde99-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="cde99-112">**Microsoft Project** -Project Online Professional oder Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="cde99-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="cde99-113">**Microsoft Visio** -Visio Online-Plan 2</span><span class="sxs-lookup"><span data-stu-id="cde99-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="cde99-114">**Unternehmensportal** – das Unternehmensportal muss in Ihrem Mandanten verfügbar sein, damit Ihre Benutzer diese Anwendungen installieren können.</span><span class="sxs-lookup"><span data-stu-id="cde99-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="cde99-115">Wenn das Unternehmensportal nicht in Ihrem Mandanten bereitgestellt wird, finden Sie weitere Informationen unter [Unternehmensportal](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="cde99-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="cde99-116">Bereitstellen von Project und Visio für Microsoft Managed Desktop-Geräte</span><span class="sxs-lookup"><span data-stu-id="cde99-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="cde99-117">Nachdem Sie Ihre Supportanfrage übermittelt haben, erstellt Microsoft Managed Desktop drei Azure AD-Gruppen und drei Anwendungsbereitstellungen über Microsoft InTune, um die apps für Ihren Mandanten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="cde99-117">After you submit your support request, Microsoft Managed Desktop will create three Azure AD groups and three application deployments through Microsoft Intune to deploy the apps to your tenant.</span></span>  

<span data-ttu-id="cde99-118">**So stellen Sie Project und Visio bereit**</span><span class="sxs-lookup"><span data-stu-id="cde99-118">**To deploy Project and Visio**</span></span>
1. <span data-ttu-id="cde99-119">**Datei eine Supportanfrage** IT-Administratoren müssen eine Supportanfrage einreichen, damit diese Anwendungen Ihren Benutzern zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="cde99-119">**File a support request** IT administrators need to file a support request to make these applications available their users.</span></span> <span data-ttu-id="cde99-120">Informationen zur Kontaktaufnahme mit Microsoft Managed Desktop finden Sie unter [Admin Support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span><span class="sxs-lookup"><span data-stu-id="cde99-120">For information on contacting Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>
2. <span data-ttu-id="cde99-121">**Zuweisen von Benutzern zu neuen Azure Ad-Gruppen** Microsoft Managed Desktop erstellt 3 Azure AD-Gruppen in Ihrem Mandanten und 3 entsprechende Anwendungsbereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="cde99-121">**Assign users to new Azure AD groups** Microsoft Managed Desktop will create 3 Azure AD groups in your tenant and 3 corresponding application deployments.</span></span> <span data-ttu-id="cde99-122">IT-Administratoren müssen die Benutzer den entsprechenden Gruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cde99-122">IT admins need to assign the users to the appropriate groups.</span></span>

>[!NOTE]
><span data-ttu-id="cde99-123">Weisen Sie Benutzer nur einer dieser Azure AD-Gruppen zu.</span><span class="sxs-lookup"><span data-stu-id="cde99-123">Assign users to only one of these Azure AD groups.</span></span> 

<span data-ttu-id="cde99-124">Name der Azure AD-Gruppe</span><span class="sxs-lookup"><span data-stu-id="cde99-124">Azure AD Group name</span></span> | <span data-ttu-id="cde99-125">Welche Benutzer sollen zugewiesen werden?</span><span class="sxs-lookup"><span data-stu-id="cde99-125">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="cde99-126">Microsoft-Office-Project-install</span><span class="sxs-lookup"><span data-stu-id="cde99-126">Microsoft-Office-Project-Install</span></span> | <span data-ttu-id="cde99-127">Benutzer, die nur Project benötigen</span><span class="sxs-lookup"><span data-stu-id="cde99-127">Users needing only Project</span></span>
<span data-ttu-id="cde99-128">Microsoft-Office-Visio-install</span><span class="sxs-lookup"><span data-stu-id="cde99-128">Microsoft-Office-Visio-Install</span></span> | <span data-ttu-id="cde99-129">Benutzer, die nur Visio benötigen</span><span class="sxs-lookup"><span data-stu-id="cde99-129">Users needing only Visio</span></span>
<span data-ttu-id="cde99-130">Microsoft-Office-Project und Visio-install</span><span class="sxs-lookup"><span data-stu-id="cde99-130">Microsoft-Office-Project and Visio-Install</span></span> | <span data-ttu-id="cde99-131">Benutzer, die sowohl Project als auch Visio benötigen</span><span class="sxs-lookup"><span data-stu-id="cde99-131">Users needing both Project and Visio</span></span>

<span data-ttu-id="cde99-132">Nach der Zuweisung zu diesen Gruppen stehen Anwendungen im Unternehmens Portal zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cde99-132">Once assigned to these groups, applications will be available in the Company Portal.</span></span> <span data-ttu-id="cde99-133">Es kann einige Minuten dauern, bis die Synchronisierung stattfindet, aber dann können Ihre Benutzer die apps über das Unternehmens Portal installieren.</span><span class="sxs-lookup"><span data-stu-id="cde99-133">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

## <a name="communicate-changes"></a><span data-ttu-id="cde99-134">Kommunizieren von Änderungen</span><span class="sxs-lookup"><span data-stu-id="cde99-134">Communicate changes</span></span>
<span data-ttu-id="cde99-135">Es ist wichtig, dass IT-Administratoren ihre Benutzer über die Installation von Project und Visio informieren können.</span><span class="sxs-lookup"><span data-stu-id="cde99-135">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="cde99-136">Dies umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cde99-136">This includes:</span></span> 
- <span data-ttu-id="cde99-137">Benachrichtigen von Benutzern, wenn diese Anwendungen für Sie verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cde99-137">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="cde99-138">Anweisungen zur Installation dieser Anwendungen über das Unternehmens Portal.</span><span class="sxs-lookup"><span data-stu-id="cde99-138">Instructions on how to install these applications from the Company Portal.</span></span>

>[!NOTE]
><span data-ttu-id="cde99-139">Benutzer müssen alle Office-Anwendungen schließen, bevor Sie Microsoft Project oder Microsoft Visio aus dem Unternehmens Portal installieren.</span><span class="sxs-lookup"><span data-stu-id="cde99-139">Users must close all Office applications before installing Microsoft Project or Microsoft Visio from Company Portal.</span></span> 
