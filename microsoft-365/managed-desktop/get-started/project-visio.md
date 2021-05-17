---
title: Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten
description: Informationen zum Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950532"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="19565-104">Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten</span><span class="sxs-lookup"><span data-stu-id="19565-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="19565-105">Microsoft Project und Microsoft Visio erfordern bestimmte Schritte, die auf Microsoft Managed Desktop-Geräten installiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="19565-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="19565-106">In diesem Thema werden die Voraussetzungen und der Installationsprozess für diese Anwendungen dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="19565-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="19565-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="19565-107">Prerequisites</span></span>

<span data-ttu-id="19565-108">Administratoren sollten überprüfen, ob sie die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="19565-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="19565-109">**Lizenzmengen** – Die richtige Menge an Microsoft Project- und Microsoft Visio-Lizenzen muss für Ihre Benutzer verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="19565-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="19565-110">Microsoft Managed Desktop unterstützt derzeit nur 64-Bit-Versionen dieser Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="19565-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="19565-111">**Lizenznamen** – Die entsprechenden Lizenznamen für diese Anwendungen sind:</span><span class="sxs-lookup"><span data-stu-id="19565-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="19565-112">**Microsoft Project** – Project Online Professional oder Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="19565-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="19565-113">**Microsoft Visio** – Visio Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="19565-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="19565-114">**Unternehmensportal** – Das Unternehmensportal muss in Ihrem Mandanten verfügbar sein, damit Ihre Benutzer diese Anwendungen installieren können.</span><span class="sxs-lookup"><span data-stu-id="19565-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="19565-115">Wenn das Unternehmensportal nicht in Ihrem Mandanten bereitgestellt wird, finden Sie weitere Informationen unter [Unternehmensportal](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="19565-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="19565-116">Bereitstellen von Project und Visio für Microsoft Managed Desktop-Geräte</span><span class="sxs-lookup"><span data-stu-id="19565-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="19565-117">Microsoft Managed Desktop fügt Microsoft Project und Microsoft Visio als zwei Win32-Anwendungen in Microsoft Intune hinzu.</span><span class="sxs-lookup"><span data-stu-id="19565-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="19565-118">Außerdem erstellen wir zwei Gruppen in Azure Active Directory, die der entsprechenden Anwendung mit der Absicht "Verfügbar" zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="19565-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="19565-119">**So stellen Sie Project und Visio zur Bereitstellung** Fügen Sie den Benutzer der entsprechenden Gruppe hinzu, und die Anwendung wird im Unternehmensportal verfügbar.</span><span class="sxs-lookup"><span data-stu-id="19565-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="19565-120">Die Synchronisierung kann einige Minuten dauern, aber dann können Ihre Benutzer die Apps über das Unternehmensportal installieren.</span><span class="sxs-lookup"><span data-stu-id="19565-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="19565-121">Azure AD-Gruppenname</span><span class="sxs-lookup"><span data-stu-id="19565-121">Azure AD Group name</span></span> | <span data-ttu-id="19565-122">Welche Benutzer müssen zugewiesen werden?</span><span class="sxs-lookup"><span data-stu-id="19565-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="19565-123">Moderne Workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="19565-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="19565-124">Benutzer, die Project benötigen</span><span class="sxs-lookup"><span data-stu-id="19565-124">Users needing Project</span></span>
<span data-ttu-id="19565-125">Moderne Workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="19565-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="19565-126">Benutzer, die Visio benötigen</span><span class="sxs-lookup"><span data-stu-id="19565-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="19565-127">Kommunizieren von Änderungen</span><span class="sxs-lookup"><span data-stu-id="19565-127">Communicate changes</span></span>
<span data-ttu-id="19565-128">It's important for IT administrators to let their users know how to install Project and Visio.</span><span class="sxs-lookup"><span data-stu-id="19565-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="19565-129">Dies umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="19565-129">This includes:</span></span> 
- <span data-ttu-id="19565-130">Benachrichtigen von Benutzern, wenn diese Anwendungen für sie verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="19565-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="19565-131">Anweisungen zum Installieren dieser Anwendungen aus dem Unternehmensportal.</span><span class="sxs-lookup"><span data-stu-id="19565-131">Instructions on how to install these applications from the Company Portal.</span></span>
