---
title: Erste Schritte mit App-Steuerelement
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
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170709"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="d4846-103">Erste Schritte mit App-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d4846-103">Get started with app control</span></span>

<span data-ttu-id="d4846-104">Bevor Sie die APP-Steuerung in Ihrer Umgebung aktivieren, sollten Sie sich vergewissern, [wie Sie von Microsoft Managed Desktop implementiert](../service-description/app-control.md) wird und welche Rollen und Zuständigkeiten Sie haben.</span><span class="sxs-lookup"><span data-stu-id="d4846-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="d4846-105">Microsoft Managed Desktop vereinfacht die APP-Steuerung, indem es die anspruchsvolleren Aspekte beim Erhalt einer sicheren Basisrichtlinie berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="d4846-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="d4846-106">Ihre IT-Administratoren müssen Ihre apps weiterhin im testring testen und die Protokolle auf Warnungen oder Fehler überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d4846-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="d4846-107">Wenn eine APP eine Ausnahme benötigt, können Sie eine Anforderung oder eine von Microsoft verwaltete Desktop Operation möglicherweise in Abhängigkeit davon, wer Sie zuerst erkennt, einreichen.</span><span class="sxs-lookup"><span data-stu-id="d4846-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="d4846-108">Erstbereitstellung von apps</span><span class="sxs-lookup"><span data-stu-id="d4846-108">Initial deployment of apps</span></span>

<span data-ttu-id="d4846-109">Wenn Sie Apps zum ersten Mal bereitstellen, muss Microsoft Managed Desktop das aktuelle Verhalten bewerten.</span><span class="sxs-lookup"><span data-stu-id="d4846-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="d4846-110">Die genauen Schritte zum Aktivieren der APP-Steuerung hängen davon ab, ob in Ihrer Umgebung bereits Geräte bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="d4846-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="d4846-111">Bereits verwendete Geräte</span><span class="sxs-lookup"><span data-stu-id="d4846-111">Devices already in use</span></span>

<span data-ttu-id="d4846-112">Wenn bereits mindestens ein von Microsoft verwaltetes Desktop Gerät verwendet wird, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d4846-112">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="d4846-113">Öffnen Sie ein Service Ticket bei Microsoft Managed Desktop Operations, in dem Sie aufgefordert werden, das App-Steuerelement einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="d4846-113">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="d4846-114">Der Vorgang stellt eine [Überwachungsrichtlinie](../service-description/app-control.md#audit-policy) für alle Geräte bereit.</span><span class="sxs-lookup"><span data-stu-id="d4846-114">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="d4846-115">[Testen Sie Ihre Anwendungen](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) , um festzustellen, ob alle blockiert wären.</span><span class="sxs-lookup"><span data-stu-id="d4846-115">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="d4846-116">Wenn eine Anwendung blockiert werden würde, öffnen Sie eine [Signaturer-Anforderung](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span><span class="sxs-lookup"><span data-stu-id="d4846-116">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="d4846-117">Nachdem Sie Ihre Tests (unabhängig von den Ergebnissen) abgeschlossen haben, Benachrichtigen Sie die Vorgänge und notieren Sie alle ausstehenden Signaturanforderungen.</span><span class="sxs-lookup"><span data-stu-id="d4846-117">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="d4846-118">Durch Vorgänge werden schrittweise Richtlinien für Bereitstellungsgruppen bereitgestellt, die auf diesen Zeitplan folgen:</span><span class="sxs-lookup"><span data-stu-id="d4846-118">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="d4846-119">Bereitstellungsgruppe</span><span class="sxs-lookup"><span data-stu-id="d4846-119">Deployment group</span></span>  |<span data-ttu-id="d4846-120">Richtlinientyp</span><span class="sxs-lookup"><span data-stu-id="d4846-120">Policy type</span></span>  |<span data-ttu-id="d4846-121">Timing</span><span class="sxs-lookup"><span data-stu-id="d4846-121">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="d4846-122">Testen</span><span class="sxs-lookup"><span data-stu-id="d4846-122">Test</span></span>     |  <span data-ttu-id="d4846-123">Überwachung</span><span class="sxs-lookup"><span data-stu-id="d4846-123">Audit</span></span>       |  <span data-ttu-id="d4846-124">Tag 0</span><span class="sxs-lookup"><span data-stu-id="d4846-124">Day 0</span></span>       |
|<span data-ttu-id="d4846-125">Erster</span><span class="sxs-lookup"><span data-stu-id="d4846-125">First</span></span>     | <span data-ttu-id="d4846-126">Enforced</span><span class="sxs-lookup"><span data-stu-id="d4846-126">Enforced</span></span>        | <span data-ttu-id="d4846-127">Tag 1</span><span class="sxs-lookup"><span data-stu-id="d4846-127">Day 1</span></span>        |
|<span data-ttu-id="d4846-128">Schnell</span><span class="sxs-lookup"><span data-stu-id="d4846-128">Fast</span></span>     | <span data-ttu-id="d4846-129">Enforced</span><span class="sxs-lookup"><span data-stu-id="d4846-129">Enforced</span></span>        |  <span data-ttu-id="d4846-130">Tag 3</span><span class="sxs-lookup"><span data-stu-id="d4846-130">Day 3</span></span>       |
|<span data-ttu-id="d4846-131">Allgemein</span><span class="sxs-lookup"><span data-stu-id="d4846-131">Broad</span></span>     | <span data-ttu-id="d4846-132">Enforced</span><span class="sxs-lookup"><span data-stu-id="d4846-132">Enforced</span></span>        |  <span data-ttu-id="d4846-133">Tag 7</span><span class="sxs-lookup"><span data-stu-id="d4846-133">Day 7</span></span>       |

<span data-ttu-id="d4846-134">Sie können jederzeit während des Rollouts eine andere Dienstanforderung öffnen, um einen Teil dieser Bereitstellung anzuhalten oder zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="d4846-134">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="d4846-135">Noch nicht verwendete Geräte</span><span class="sxs-lookup"><span data-stu-id="d4846-135">Devices not yet in use</span></span>

<span data-ttu-id="d4846-136">Wenn Sie noch keine Geräte in Gebrauch haben, öffnen Sie ein Service Ticket bei Microsoft Managed Desktop Operations, in dem Sie aufgefordert werden, das App-Steuerelement einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="d4846-136">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="d4846-137">Durch Vorgänge werden schrittweise Richtlinien für Bereitstellungsgruppen bereitgestellt, die auf diesen Zeitplan folgen:</span><span class="sxs-lookup"><span data-stu-id="d4846-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="d4846-138">Bereitstellungsgruppe</span><span class="sxs-lookup"><span data-stu-id="d4846-138">Deployment group</span></span>  |<span data-ttu-id="d4846-139">Richtlinientyp</span><span class="sxs-lookup"><span data-stu-id="d4846-139">Policy type</span></span>  |<span data-ttu-id="d4846-140">Timing</span><span class="sxs-lookup"><span data-stu-id="d4846-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="d4846-141">Testen</span><span class="sxs-lookup"><span data-stu-id="d4846-141">Test</span></span>     |  <span data-ttu-id="d4846-142">Überwachung</span><span class="sxs-lookup"><span data-stu-id="d4846-142">Audit</span></span>       |  <span data-ttu-id="d4846-143">Tag 0</span><span class="sxs-lookup"><span data-stu-id="d4846-143">Day 0</span></span>       |
|<span data-ttu-id="d4846-144">Erster</span><span class="sxs-lookup"><span data-stu-id="d4846-144">First</span></span>     | <span data-ttu-id="d4846-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="d4846-145">Enforced</span></span>        | <span data-ttu-id="d4846-146">Tag 1</span><span class="sxs-lookup"><span data-stu-id="d4846-146">Day 1</span></span>        |
|<span data-ttu-id="d4846-147">Schnell</span><span class="sxs-lookup"><span data-stu-id="d4846-147">Fast</span></span>     | <span data-ttu-id="d4846-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="d4846-148">Enforced</span></span>        |  <span data-ttu-id="d4846-149">Tag 3</span><span class="sxs-lookup"><span data-stu-id="d4846-149">Day 3</span></span>       |
|<span data-ttu-id="d4846-150">Allgemein</span><span class="sxs-lookup"><span data-stu-id="d4846-150">Broad</span></span>     | <span data-ttu-id="d4846-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="d4846-151">Enforced</span></span>        |  <span data-ttu-id="d4846-152">Tag 7</span><span class="sxs-lookup"><span data-stu-id="d4846-152">Day 7</span></span>       |

<span data-ttu-id="d4846-153">Sie können jederzeit während des Rollouts eine andere Dienstanforderung öffnen, um einen Teil dieser Bereitstellung anzuhalten oder zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="d4846-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

