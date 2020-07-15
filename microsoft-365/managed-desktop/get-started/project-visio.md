---
title: Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten
description: Informationen zum Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126827"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="d06a9-104">Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten</span><span class="sxs-lookup"><span data-stu-id="d06a9-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="d06a9-105">Microsoft Project und Microsoft Visio erfordern bestimmte Schritte, die auf Microsoft Managed Desktop-Geräten installiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d06a9-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d06a9-106">In diesem Thema werden die Voraussetzungen und der Installationsvorgang für diese Anwendungen dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="d06a9-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d06a9-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d06a9-107">Prerequisites</span></span>

<span data-ttu-id="d06a9-108">Administratoren sollten überprüfen, ob Sie diese Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="d06a9-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="d06a9-109">**Lizenzmengen** – die richtige Menge an Microsoft Project-und Microsoft Visio Lizenzen müssen für Ihre Benutzer verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="d06a9-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="d06a9-110">Microsoft Managed Desktop unterstützt derzeit nur 64-Bit-Versionen dieser Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="d06a9-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="d06a9-111">**Lizenznamen** – die entsprechenden Lizenznamen für diese Anwendungen sind:</span><span class="sxs-lookup"><span data-stu-id="d06a9-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="d06a9-112">**Microsoft Project** -Project Online Professional oder Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="d06a9-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="d06a9-113">**Microsoft Visio** -Visio Online-Plan 2</span><span class="sxs-lookup"><span data-stu-id="d06a9-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="d06a9-114">**Unternehmensportal** : das Unternehmensportal muss in Ihrem Mandanten verfügbar sein, damit Ihre Benutzer diese Anwendungen installieren können.</span><span class="sxs-lookup"><span data-stu-id="d06a9-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="d06a9-115">Wenn das Unternehmensportal nicht in Ihrem Mandanten bereitgestellt wird, finden Sie weitere Informationen unter [Unternehmensportal](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="d06a9-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="d06a9-116">Bereitstellen von Project und Visio für Microsoft Managed Desktop-Geräte</span><span class="sxs-lookup"><span data-stu-id="d06a9-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="d06a9-117">Microsoft Managed Desktop wird Microsoft Project und Microsoft Visio als zwei Win32-Anwendungen in Microsoft InTune hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d06a9-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="d06a9-118">Außerdem werden zwei Gruppen in Azure Active Directory erstellt, die der entsprechenden Anwendung mit der "available"-Absicht zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d06a9-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="d06a9-119">**So stellen Sie Project und Visio bereit** Fügen Sie den Benutzer der entsprechenden Gruppe hinzu, und die Anwendung wird im Unternehmens Portal verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="d06a9-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="d06a9-120">Es kann einige Minuten dauern, bis die Synchronisierung ausgeführt wird, aber dann können Ihre Benutzer die Apps aus dem Unternehmens Portal installieren.</span><span class="sxs-lookup"><span data-stu-id="d06a9-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="d06a9-121">Azure AD Gruppenname</span><span class="sxs-lookup"><span data-stu-id="d06a9-121">Azure AD Group name</span></span> | <span data-ttu-id="d06a9-122">Welche Benutzer sollen zugewiesen werden?</span><span class="sxs-lookup"><span data-stu-id="d06a9-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="d06a9-123">Moderner Arbeitsplatz-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="d06a9-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="d06a9-124">Benutzer, die Project benötigen</span><span class="sxs-lookup"><span data-stu-id="d06a9-124">Users needing Project</span></span>
<span data-ttu-id="d06a9-125">Moderner Arbeitsplatz-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="d06a9-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="d06a9-126">Benutzer, die Visio benötigen</span><span class="sxs-lookup"><span data-stu-id="d06a9-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="d06a9-127">Kommunizieren von Änderungen</span><span class="sxs-lookup"><span data-stu-id="d06a9-127">Communicate changes</span></span>
<span data-ttu-id="d06a9-128">Es ist wichtig, dass IT-Administratoren ihren Benutzern mitteilen können, wie Sie Project und Visio installieren.</span><span class="sxs-lookup"><span data-stu-id="d06a9-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="d06a9-129">Dies umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d06a9-129">This includes:</span></span> 
- <span data-ttu-id="d06a9-130">Benachrichtigen von Benutzern, wenn diese Anwendungen für Sie verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d06a9-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="d06a9-131">Anweisungen zum Installieren dieser Anwendungen aus dem Unternehmens Portal.</span><span class="sxs-lookup"><span data-stu-id="d06a9-131">Instructions on how to install these applications from the Company Portal.</span></span>
