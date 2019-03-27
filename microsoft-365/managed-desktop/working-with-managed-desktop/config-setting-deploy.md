---
title: Bereitstellen von konfigurierbaren Einstellungen in Microsoft Managed Desktop
description: Bereitstellen und Nachverfolgen von Änderungen an konfigurierbaren Einstellungen in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, Deploy, Staging-Bereitstellung, konfigurierbare Einstellungen
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4662373b926d07558ecedd05c9dfcf472ceb6357
ms.sourcegitcommit: d38c0ce846bac19e876a03a59ed4f268c7bae389
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30900284"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="b5f94-104">Bereitstellen und Nachverfolgen von konfigurierbaren Einstellungen – Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="b5f94-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="b5f94-105">Nachdem Sie Änderungen an den Einstellungskategorien vorgenommen und eine Bereitstellung inszeniert haben, können Sie mit der Seite Bereitstellungsstatus mit der Bereitstellung der Einstellungen für Gruppen beginnen.</span><span class="sxs-lookup"><span data-stu-id="b5f94-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="b5f94-106">Auf dieser Seite wird eine Zusammenfassung der einzelnen konfigurierbaren Einstellungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5f94-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="b5f94-107">Durch Öffnen einer Einstellungskategorie können Sie Einstellungen für Gruppen bereitstellen und den Fortschritt dieser Bereitstellungen nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="b5f94-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="b5f94-108">Bereitstellungsstatus</span><span class="sxs-lookup"><span data-stu-id="b5f94-108">Deployment statuses</span></span> 

<span data-ttu-id="b5f94-109">Dies sind die Statuen, die für jede Bereitstellung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b5f94-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="b5f94-110">Status</span><span class="sxs-lookup"><span data-stu-id="b5f94-110">Status</span></span>  | <span data-ttu-id="b5f94-111">Erklärung</span><span class="sxs-lookup"><span data-stu-id="b5f94-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="b5f94-112">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="b5f94-112">Deploy</span></span> | <span data-ttu-id="b5f94-113">Ihre Änderung wartet darauf, für diese Gruppe bereitgestellt zu werden.</span><span class="sxs-lookup"><span data-stu-id="b5f94-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="b5f94-114">In Arbeit</span><span class="sxs-lookup"><span data-stu-id="b5f94-114">In progress</span></span> | <span data-ttu-id="b5f94-115">Die Änderung wird auf aktive Geräte in dieser Gruppe angewendet.</span><span class="sxs-lookup"><span data-stu-id="b5f94-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="b5f94-116">Abschließen</span><span class="sxs-lookup"><span data-stu-id="b5f94-116">Complete</span></span> | <span data-ttu-id="b5f94-117">Die Änderung, die für alle aktiven Geräte in dieser Gruppe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b5f94-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="b5f94-118">Failed</span><span class="sxs-lookup"><span data-stu-id="b5f94-118">Failed</span></span> | <span data-ttu-id="b5f94-119">Die Änderung ist bei 10 Prozent der aktiven Geräte in der Gruppe fehlgeschlagen, sodass die Bereitstellung angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="b5f94-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="b5f94-120">Eine Supportanforderung wird automatisch mit Microsoft Managed Desktop-Vorgängen geöffnet, um die Bereitstellung zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="b5f94-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="b5f94-121">Zurückgesetzt</span><span class="sxs-lookup"><span data-stu-id="b5f94-121">Reverted</span></span> | <span data-ttu-id="b5f94-122">Die Änderung wurde auf die letzte Änderung zurückgesetzt, die erfolgreich für alle Bereitstellungsgruppen bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b5f94-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="b5f94-123">Bereitstellen von Änderungen</span><span class="sxs-lookup"><span data-stu-id="b5f94-123">Deploy changes</span></span>

<span data-ttu-id="b5f94-124">In diesen Anweisungen wird das Hintergrundbild des Desktops angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5f94-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="b5f94-125">Nach dem Bereitstelleneiner Bereitstellung führen Sie Änderungen auf der Seite Bereitstellungsstatus aus.</span><span class="sxs-lookup"><span data-stu-id="b5f94-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="b5f94-126">**So stellen Sie Änderungen bereit**</span><span class="sxs-lookup"><span data-stu-id="b5f94-126">**To deploy changes**</span></span>

1. <span data-ttu-id="b5f94-127">Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="b5f94-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="b5f94-128">Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.</span><span class="sxs-lookup"><span data-stu-id="b5f94-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="b5f94-129">Wählen Sie im **Bereitstellungsstatus** -Arbeitsbereich die Einstellung aus, die Sie bereitstellen möchten, und wählen Sie dann die bereitgestellte Bereitstellung mit Staging aus.</span><span class="sxs-lookup"><span data-stu-id="b5f94-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="b5f94-130">Wählen Sie **Bereitstellen** aus, um die Änderung an einer der Bereitstellungsgruppen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b5f94-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

![Bereitstellungsstatus für konfigurierbare Einstellungen (Übersicht)](images/deploy-cs-overview.png)

<span data-ttu-id="b5f94-132">Microsoft Managed Desktop empfiehlt die Bereitstellung in Bereitstellungsgruppen in dieser Reihenfolge: Test, First, fast und dann Broad.</span><span class="sxs-lookup"><span data-stu-id="b5f94-132">Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="b5f94-133">Wenn in jeder Gruppe Änderungen abgeschlossen sind, wird der Status in **abgeschlossen**geändert.</span><span class="sxs-lookup"><span data-stu-id="b5f94-133">When changes complete in each group, the status changes to **Complete**.</span></span>

![Vollständige Bereitstellung von konfigurierbaren Einstellungen](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="b5f94-135">Wiederherstellen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="b5f94-135">Revert deployment</span></span>

<span data-ttu-id="b5f94-136">Nachdem Sie eine Änderung bereitgestellt haben, können Sie den **Bereitstellungsstatus**wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="b5f94-136">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="b5f94-137">Wenn Sie eine Änderung zurücksetzen, die gerade **ausgeführt** wird oder **abgeschlossen**ist, wird die aktuelle Bereitstellung angehalten.</span><span class="sxs-lookup"><span data-stu-id="b5f94-137">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="b5f94-138">Die Einstellung wird auf die letzte Version zurückgesetzt, die für alle Gruppen bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b5f94-138">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="b5f94-139">Wir zeigen die Schritte zum Zurücksetzen einer Änderung mithilfe des Desktop Hintergrundbilds als Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b5f94-139">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="b5f94-140">**So stellen Sie eine Änderung wieder her**</span><span class="sxs-lookup"><span data-stu-id="b5f94-140">**To revert a change**</span></span>
1. <span data-ttu-id="b5f94-141">Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="b5f94-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="b5f94-142">Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.</span><span class="sxs-lookup"><span data-stu-id="b5f94-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="b5f94-143">Wählen Sie im **Bereitstellungsstatus** -Arbeitsbereich die Einstellung aus, die Sie wiederherstellen möchten, und wählen Sie dann die wiederherzustellende Staging-Bereitstellung aus.</span><span class="sxs-lookup"><span data-stu-id="b5f94-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="b5f94-144">Wenn Sie **diese Änderung rückgängig**machen möchten, wählen Sie **Bereitstellung zurück**setzen aus.</span><span class="sxs-lookup"><span data-stu-id="b5f94-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![Konfigurierbare Einstellungen werden wiederhergestellt](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="b5f94-146">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b5f94-146">Additional resources</span></span>
- [<span data-ttu-id="b5f94-147">Übersicht über konfigurierbare Einstellungen</span><span class="sxs-lookup"><span data-stu-id="b5f94-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="b5f94-148">Referenz zu konfigurierbaren Einstellungen</span><span class="sxs-lookup"><span data-stu-id="b5f94-148">Configurable settings reference</span></span>](config-setting-ref.md) 
