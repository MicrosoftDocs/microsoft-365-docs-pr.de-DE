---
title: Bereitstellen von konfigurierbaren Einstellungen in Microsoft Managed Desktop
description: Bereitstellen und Nachverfolgen von Änderungen an konfigurierbaren Einstellungen in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, Deploy, Staging-Bereitstellung, konfigurierbare Einstellungen
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 62a17c95f5dc6b11f446a27684c507d7aaa95b7b
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414168"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="cdc19-104">Bereitstellen und Nachverfolgen von konfigurierbaren Einstellungen – Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="cdc19-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="cdc19-105">Nachdem Sie Änderungen an den Einstellungskategorien vorgenommen und eine Bereitstellung ausgeführt haben, können Sie den Bereitstellungsstatus für die Bereitstellung bereitstellen und nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="cdc19-105">After you make changes to your setting categories and stage a deployment, you can deploy and track progress for the deployment on Deployment status.</span></span> <span data-ttu-id="cdc19-106">Auf dieser Seite wird eine Zusammenfassung der einzelnen konfigurierbaren Einstellungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cdc19-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="cdc19-107">Öffnen Sie eine Einstellungskategorie, um die einzelnen Bereitstellungen und Ihre Details anzuzeigen, um die Änderungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="cdc19-107">Open a setting category to see each deployment and their details, to deploy the changes.</span></span> 

## <a name="deployment-statuses"></a><span data-ttu-id="cdc19-108">Bereitstellungsstatus</span><span class="sxs-lookup"><span data-stu-id="cdc19-108">Deployment statuses</span></span> 

<span data-ttu-id="cdc19-109">Dies sind die Statuen, die für jede Bereitstellung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cdc19-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="cdc19-110">Status</span><span class="sxs-lookup"><span data-stu-id="cdc19-110">Status</span></span>  | <span data-ttu-id="cdc19-111">Erklärung</span><span class="sxs-lookup"><span data-stu-id="cdc19-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="cdc19-112">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="cdc19-112">Deploy</span></span> | <span data-ttu-id="cdc19-113">Ihre Änderung wartet auf die Bereitstellung für diesen Ring.</span><span class="sxs-lookup"><span data-stu-id="cdc19-113">Your change is waiting to be deployed to this ring.</span></span>
<span data-ttu-id="cdc19-114">In Arbeit</span><span class="sxs-lookup"><span data-stu-id="cdc19-114">In progress</span></span> | <span data-ttu-id="cdc19-115">Die Änderung wird auf aktive Geräte in diesem Ring angewendet.</span><span class="sxs-lookup"><span data-stu-id="cdc19-115">The change is being applied to active devices in this ring.</span></span> 
<span data-ttu-id="cdc19-116">Abschließen</span><span class="sxs-lookup"><span data-stu-id="cdc19-116">Complete</span></span> | <span data-ttu-id="cdc19-117">Die Änderung, die für alle aktiven Geräte in diesem Ring abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="cdc19-117">The change completed on all active devices in this ring.</span></span> 
<span data-ttu-id="cdc19-118">Failed</span><span class="sxs-lookup"><span data-stu-id="cdc19-118">Failed</span></span> | <span data-ttu-id="cdc19-119">Die Änderung ist bei 10 Prozent der aktiven Geräte im Ring fehlgeschlagen, sodass die Bereitstellung angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="cdc19-119">The change failed on a 10 percent of active devices in the ring, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="cdc19-120">Eine Supportanforderung wird automatisch mit Microsoft Managed Desktop-Vorgängen geöffnet, um die Bereitstellung zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="cdc19-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="cdc19-121">Zurückgesetzt</span><span class="sxs-lookup"><span data-stu-id="cdc19-121">Reverted</span></span> | <span data-ttu-id="cdc19-122">Die Änderung wurde auf die letzte Änderung zurückgesetzt, die erfolgreich für alle Bereitstellungs Ringe bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cdc19-122">The change was reverted to the last change that was successfully deployed to all deployment rings.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="cdc19-123">Bereitstellen von Änderungen</span><span class="sxs-lookup"><span data-stu-id="cdc19-123">Deploy changes</span></span>

<span data-ttu-id="cdc19-124">In diesen Anweisungen wird das Hintergrundbild des Desktops angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cdc19-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="cdc19-125">Nachdem Sie eine Bereitstellung inszeniert haben, stellen Sie Änderungen aus dem Bereitstellungsstatus bereit.</span><span class="sxs-lookup"><span data-stu-id="cdc19-125">After you’ve staged a deployment, you deploy changes from Deployment status.</span></span> 

<span data-ttu-id="cdc19-126">**So stellen Sie Änderungen bereit**</span><span class="sxs-lookup"><span data-stu-id="cdc19-126">**To deploy changes**</span></span>

1. <span data-ttu-id="cdc19-127">Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="cdc19-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="cdc19-128">Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.</span><span class="sxs-lookup"><span data-stu-id="cdc19-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="cdc19-129">Wählen Sie im **Bereitstellungsstatus** -Arbeitsbereich die Einstellung aus, die Sie bereitstellen möchten, und wählen Sie dann die bereitgestellte Bereitstellung mit Staging aus.</span><span class="sxs-lookup"><span data-stu-id="cdc19-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="cdc19-130">Wählen Sie **Bereitstellen** aus, um die Änderung an einem der Bereitstellungs Ringe bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="cdc19-130">Select **Deploy** to deploy the change to one of the deployment rings.</span></span>

![Bereitstellungsstatus für konfigurierbare Einstellungen (Übersicht)](images/deploy-cs-overview.png)

<span data-ttu-id="cdc19-132">Microsoft Managed Desktop empfiehlt die Bereitstellung in Bereitstellungs Ringen in dieser Reihenfolge: Test, First, fast und dann Broad.</span><span class="sxs-lookup"><span data-stu-id="cdc19-132">Microsoft Managed Desktop recommends deploying to deployment rings in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="cdc19-133">Wenn in jedem Ring Änderungen vorgenommen werden, wird der Status in **abgeschlossen**geändert.</span><span class="sxs-lookup"><span data-stu-id="cdc19-133">When changes complete in each ring, the status changes to **Complete**.</span></span>

![Vollständige Bereitstellung von konfigurierbaren Einstellungen](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="cdc19-135">Wiederherstellen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="cdc19-135">Revert deployment</span></span>

<span data-ttu-id="cdc19-136">In diesen Anweisungen wird das Hintergrundbild des Desktops angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cdc19-136">We’ll show Desktop background picture in these instructions.</span></span> 

<span data-ttu-id="cdc19-137">Nachdem Sie eine Änderung bereitgestellt haben, können Sie den **Bereitstellungsstatus**wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="cdc19-137">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="cdc19-138">Wenn Sie eine Änderung zurücksetzen, die gerade **ausgeführt** wird oder **abgeschlossen**ist, wird die aktuelle Bereitstellung angehalten.</span><span class="sxs-lookup"><span data-stu-id="cdc19-138">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="cdc19-139">Die Einstellung wird auf die letzte Version zurückgesetzt, die für alle Ringe bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cdc19-139">The setting will revert to the last version that was deployed to all rings.</span></span> 

<span data-ttu-id="cdc19-140">**So stellen Sie eine Änderung wieder her**</span><span class="sxs-lookup"><span data-stu-id="cdc19-140">**To revert a change**</span></span>
1. <span data-ttu-id="cdc19-141">Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="cdc19-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="cdc19-142">Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.</span><span class="sxs-lookup"><span data-stu-id="cdc19-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="cdc19-143">Wählen Sie im **Bereitstellungsstatus** -Arbeitsbereich die Einstellung aus, die Sie wiederherstellen möchten, und wählen Sie dann die wiederherzustellende Staging-Bereitstellung aus.</span><span class="sxs-lookup"><span data-stu-id="cdc19-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="cdc19-144">Wenn Sie **diese Änderung rückgängig**machen möchten, wählen Sie **Bereitstellung zurück**setzen aus.</span><span class="sxs-lookup"><span data-stu-id="cdc19-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![Konfigurierbare Einstellungen werden wiederhergestellt](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="cdc19-146">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="cdc19-146">Additional resources</span></span>
- [<span data-ttu-id="cdc19-147">Übersicht über konfigurierbare Einstellungen</span><span class="sxs-lookup"><span data-stu-id="cdc19-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="cdc19-148">Referenz zu konfigurierbaren Einstellungen</span><span class="sxs-lookup"><span data-stu-id="cdc19-148">Configurable settings reference</span></span>](config-setting-ref.md) 