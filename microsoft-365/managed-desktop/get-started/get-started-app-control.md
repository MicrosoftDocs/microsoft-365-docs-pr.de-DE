---
title: Erste Schritte mit dem App-Steuerelement
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430459"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="de896-103">Erste Schritte mit dem App-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="de896-103">Get started with app control</span></span>

<span data-ttu-id="de896-104">Bevor Sie die App-Steuerung in Ihrer Umgebung aktivieren, sollten Sie überprüfen und verstehen, [wie](../service-description/app-control.md) Microsoft Managed Desktop und Ihre Rollen und Verantwortlichkeiten implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="de896-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="de896-105">Microsoft Managed Desktop vereinfacht die App-Steuerung, indem die anspruchsvolleren Aspekte einer sicheren Basisrichtlinie berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="de896-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="de896-106">Ihre IT-Administratoren müssen Ihre Apps weiterhin im Testring testen und die Protokolle auf Warnungen oder Fehler überprüfen.</span><span class="sxs-lookup"><span data-stu-id="de896-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="de896-107">Wenn eine App eine Ausnahme benötigt, können Sie eine Anforderung oder eine Microsoft Managed Desktop Operation, je nachdem, wer sie zuerst erkennt.</span><span class="sxs-lookup"><span data-stu-id="de896-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="de896-108">Erstbereitstellung von Apps</span><span class="sxs-lookup"><span data-stu-id="de896-108">Initial deployment of apps</span></span>

<span data-ttu-id="de896-109">Bei der ersten Bereitstellung von Apps müssen Microsoft Managed Desktop das aktuelle Verhalten bewerten.</span><span class="sxs-lookup"><span data-stu-id="de896-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="de896-110">Die genauen Schritte zum Aktivieren der App-Steuerung hängen davon ab, ob geräte bereits in Ihrer Umgebung bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="de896-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="de896-111">Noch nicht verwendete Geräte</span><span class="sxs-lookup"><span data-stu-id="de896-111">Devices not yet in use</span></span>

<span data-ttu-id="de896-112">Wenn Sie noch keine Geräte verwenden, öffnen Sie ein Dienstticket mit Microsoft Managed Desktop Vorgängen, die das Aktivieren der App-Steuerung anfordern.</span><span class="sxs-lookup"><span data-stu-id="de896-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="de896-113">Im Anschluss an diesen Zeitplan werden schrittweise Richtlinien für Bereitstellungsgruppen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="de896-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="de896-114">Bereitstellungsgruppe</span><span class="sxs-lookup"><span data-stu-id="de896-114">Deployment group</span></span>  |<span data-ttu-id="de896-115">Richtlinientyp</span><span class="sxs-lookup"><span data-stu-id="de896-115">Policy type</span></span>  |<span data-ttu-id="de896-116">Timing</span><span class="sxs-lookup"><span data-stu-id="de896-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="de896-117">Testen</span><span class="sxs-lookup"><span data-stu-id="de896-117">Test</span></span>     |  <span data-ttu-id="de896-118">Überwachung</span><span class="sxs-lookup"><span data-stu-id="de896-118">Audit</span></span>       |  <span data-ttu-id="de896-119">Tag 0</span><span class="sxs-lookup"><span data-stu-id="de896-119">Day 0</span></span>       |
|<span data-ttu-id="de896-120">Erster</span><span class="sxs-lookup"><span data-stu-id="de896-120">First</span></span>     | <span data-ttu-id="de896-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="de896-121">Enforced</span></span>        | <span data-ttu-id="de896-122">Tag 1</span><span class="sxs-lookup"><span data-stu-id="de896-122">Day 1</span></span>        |
|<span data-ttu-id="de896-123">Schnell</span><span class="sxs-lookup"><span data-stu-id="de896-123">Fast</span></span>     | <span data-ttu-id="de896-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="de896-124">Enforced</span></span>        |  <span data-ttu-id="de896-125">Tag 2</span><span class="sxs-lookup"><span data-stu-id="de896-125">Day 2</span></span>       |
|<span data-ttu-id="de896-126">Allgemein</span><span class="sxs-lookup"><span data-stu-id="de896-126">Broad</span></span>     | <span data-ttu-id="de896-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="de896-127">Enforced</span></span>        |  <span data-ttu-id="de896-128">Tag 3</span><span class="sxs-lookup"><span data-stu-id="de896-128">Day 3</span></span>       |

<span data-ttu-id="de896-129">Sie können während des Rollouts immer eine andere Dienstanforderung öffnen, um einen Teil dieser Bereitstellung anzuhalten oder ein Rollback zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="de896-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="de896-130">Geräte, die bereits verwendet werden</span><span class="sxs-lookup"><span data-stu-id="de896-130">Devices already in use</span></span>

<span data-ttu-id="de896-131">Wenn bereits mindestens ein Microsoft Managed Desktop verwendet wird, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="de896-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="de896-132">Öffnen Sie ein Dienstticket mit Microsoft Managed Desktop Vorgänge, die das Aktivieren der App-Steuerung anfordern.</span><span class="sxs-lookup"><span data-stu-id="de896-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="de896-133">Vorgänge stellen eine [Überwachungsrichtlinie auf](../service-description/app-control.md#audit-policy) allen Geräten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="de896-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="de896-134">[Testen Sie Ihre Anwendungen,](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) um zu sehen, ob eine blockiert werden würde.</span><span class="sxs-lookup"><span data-stu-id="de896-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="de896-135">Wenn eine Anwendung blockiert würde, öffnen Sie eine [Signieranforderung](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span><span class="sxs-lookup"><span data-stu-id="de896-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="de896-136">Nachdem Sie die Tests abgeschlossen haben (unabhängig von den Ergebnissen), benachrichtigen Sie Operations, und notieren Sie sich alle ausstehenden Signieranforderungen.</span><span class="sxs-lookup"><span data-stu-id="de896-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="de896-137">Im Anschluss an diesen Zeitplan werden schrittweise Richtlinien für Bereitstellungsgruppen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="de896-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="de896-138">Bereitstellungsgruppe</span><span class="sxs-lookup"><span data-stu-id="de896-138">Deployment group</span></span>  |<span data-ttu-id="de896-139">Richtlinientyp</span><span class="sxs-lookup"><span data-stu-id="de896-139">Policy type</span></span>  |<span data-ttu-id="de896-140">Timing</span><span class="sxs-lookup"><span data-stu-id="de896-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="de896-141">Testen</span><span class="sxs-lookup"><span data-stu-id="de896-141">Test</span></span>     |  <span data-ttu-id="de896-142">Überwachung</span><span class="sxs-lookup"><span data-stu-id="de896-142">Audit</span></span>       |  <span data-ttu-id="de896-143">Tag 0</span><span class="sxs-lookup"><span data-stu-id="de896-143">Day 0</span></span>       |
|<span data-ttu-id="de896-144">Erster</span><span class="sxs-lookup"><span data-stu-id="de896-144">First</span></span>     | <span data-ttu-id="de896-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="de896-145">Enforced</span></span>        | <span data-ttu-id="de896-146">Tag 1</span><span class="sxs-lookup"><span data-stu-id="de896-146">Day 1</span></span>        |
|<span data-ttu-id="de896-147">Schnell</span><span class="sxs-lookup"><span data-stu-id="de896-147">Fast</span></span>     | <span data-ttu-id="de896-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="de896-148">Enforced</span></span>        |  <span data-ttu-id="de896-149">Angehalten, Rollout auf Anfrage</span><span class="sxs-lookup"><span data-stu-id="de896-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="de896-150">Allgemein</span><span class="sxs-lookup"><span data-stu-id="de896-150">Broad</span></span>     | <span data-ttu-id="de896-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="de896-151">Enforced</span></span>        |  <span data-ttu-id="de896-152">Angehalten, Rollout auf Anfrage</span><span class="sxs-lookup"><span data-stu-id="de896-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="de896-153">Sie können während des Rollouts immer eine andere Dienstanforderung öffnen, um einen Teil dieser Bereitstellung anzuhalten oder ein Rollback zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="de896-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



