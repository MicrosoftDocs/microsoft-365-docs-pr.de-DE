---
title: Bereitstellen von konfigurierbaren Einstellungen in Microsoft Managed Desktop
description: Bereitstellen und Nachverfolgen von Änderungen an konfigurierbaren Einstellungen in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, Deploy, Staging-Bereitstellung, konfigurierbare Einstellungen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5b6a2756514e94cb4f96141d6e7c9f6f2a6dd7ff
ms.sourcegitcommit: a4657a499967751d4c2dfc6cd1904258ab8be193
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "37040799"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="c46c5-104">Bereitstellen und Nachverfolgen von konfigurierbaren Einstellungen – Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="c46c5-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="c46c5-105">Nachdem Sie Änderungen an den Einstellungskategorien vorgenommen und eine Bereitstellung bereitgestellt haben, können Sie mit der Seite Bereitstellungsstatus die Bereitstellung Ihrer Einstellungen für Gruppen beginnen.</span><span class="sxs-lookup"><span data-stu-id="c46c5-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="c46c5-106">Auf dieser Seite wird eine Zusammenfassung der einzelnen konfigurierbaren Einstellungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c46c5-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="c46c5-107">Wenn Sie eine Einstellungskategorie öffnen, können Sie Einstellungen für Gruppen bereitstellen und den Status dieser Bereitstellungen nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="c46c5-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="c46c5-108">Bereitstellungsstatus</span><span class="sxs-lookup"><span data-stu-id="c46c5-108">Deployment statuses</span></span> 

<span data-ttu-id="c46c5-109">Dies sind die Status, die Sie für jede Bereitstellung sehen.</span><span class="sxs-lookup"><span data-stu-id="c46c5-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="c46c5-110">Status</span><span class="sxs-lookup"><span data-stu-id="c46c5-110">Status</span></span>  | <span data-ttu-id="c46c5-111">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c46c5-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="c46c5-112">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="c46c5-112">Deploy</span></span> | <span data-ttu-id="c46c5-113">Ihre Änderung wartet auf die Bereitstellung für diese Gruppe.</span><span class="sxs-lookup"><span data-stu-id="c46c5-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="c46c5-114">In Arbeit</span><span class="sxs-lookup"><span data-stu-id="c46c5-114">In progress</span></span> | <span data-ttu-id="c46c5-115">Die Änderung wird auf aktive Geräte in dieser Gruppe angewendet.</span><span class="sxs-lookup"><span data-stu-id="c46c5-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="c46c5-116">Abschließen</span><span class="sxs-lookup"><span data-stu-id="c46c5-116">Complete</span></span> | <span data-ttu-id="c46c5-117">Die Änderung, die für alle aktiven Geräte in dieser Gruppe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="c46c5-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="c46c5-118">Failed</span><span class="sxs-lookup"><span data-stu-id="c46c5-118">Failed</span></span> | <span data-ttu-id="c46c5-119">Die Änderung konnte auf 10 Prozent der aktiven Geräte in der Gruppe nicht ausgeführt werden, sodass die Bereitstellung angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="c46c5-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="c46c5-120">Eine Supportanfrage wird automatisch mit Microsoft Managed Desktop Operations geöffnet, um die Bereitstellung zu beheben.</span><span class="sxs-lookup"><span data-stu-id="c46c5-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="c46c5-121">Zurückgesetzt</span><span class="sxs-lookup"><span data-stu-id="c46c5-121">Reverted</span></span> | <span data-ttu-id="c46c5-122">Die Änderung wurde auf die letzte Änderung zurückgesetzt, die für alle Bereitstellungsgruppen erfolgreich bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c46c5-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="c46c5-123">Bereitstellen von Änderungen</span><span class="sxs-lookup"><span data-stu-id="c46c5-123">Deploy changes</span></span>

<span data-ttu-id="c46c5-124">In diesen Anweisungen wird ein Desktop Hintergrundbild angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c46c5-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="c46c5-125">Nachdem Sie eine Bereitstellung bereitgestellt haben, stellen Sie die Änderungen auf der Seite Bereitstellungsstatus bereit.</span><span class="sxs-lookup"><span data-stu-id="c46c5-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="c46c5-126">**So stellen Sie Änderungen bereit**</span><span class="sxs-lookup"><span data-stu-id="c46c5-126">**To deploy changes**</span></span>

1. <span data-ttu-id="c46c5-127">Anmelden beim [Microsoft Managed Desktop-Verwaltungsportal](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="c46c5-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="c46c5-128">Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.</span><span class="sxs-lookup"><span data-stu-id="c46c5-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="c46c5-129">Wählen Sie im Bereich **Bereitstellungsstatus** die Einstellung aus, die Sie bereitstellen möchten, und wählen Sie dann die bereitgestellte Bereitstellung aus.</span><span class="sxs-lookup"><span data-stu-id="c46c5-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="c46c5-130">Wählen Sie **Bereitstellen** aus, um die Änderung an einer der Bereitstellungsgruppen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c46c5-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

<span data-ttu-id="c46c5-131">![Konfigurierbare Einstellungen Bereitstellungs](images/1deployedit.png) Statusübersicht Microsoft Managed Desktop empfiehlt die Bereitstellung in Bereitstellungsgruppen in dieser Reihenfolge: Test, erste, schnell und dann breit.</span><span class="sxs-lookup"><span data-stu-id="c46c5-131">![Configurable settings deployment status overview](images/1deployedit.png) Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="c46c5-132">Wenn Änderungen in jeder Gruppe abgeschlossen werden, ändert sich der Status in **abgeschlossen**.</span><span class="sxs-lookup"><span data-stu-id="c46c5-132">When changes complete in each group, the status changes to **Complete**.</span></span>

![Bereitstellung der konfigurierbaren Einstellungen abgeschlossen](images/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="c46c5-134">Wiederherstellen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="c46c5-134">Revert deployment</span></span>

<span data-ttu-id="c46c5-135">Nachdem Sie eine Änderung bereitgestellt haben, können Sie den **Bereitstellungsstatus**wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="c46c5-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="c46c5-136">Wenn Sie eine gerade **ausgeführte** oder **abgeschlossene**Änderung wiederherstellen, wird die aktuelle Bereitstellung angehalten.</span><span class="sxs-lookup"><span data-stu-id="c46c5-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="c46c5-137">Die Einstellung wird auf die letzte Version zurückgesetzt, die für alle Gruppen bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c46c5-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="c46c5-138">Wir zeigen die Schritte zum Rückgängigmachen einer Änderung mithilfe des Desktop Hintergrundbilds als Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c46c5-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="c46c5-139">**So stellen Sie eine Änderung wieder her**</span><span class="sxs-lookup"><span data-stu-id="c46c5-139">**To revert a change**</span></span>
1. <span data-ttu-id="c46c5-140">Anmelden beim [Microsoft Managed Desktop-Verwaltungsportal](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="c46c5-140">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="c46c5-141">Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.</span><span class="sxs-lookup"><span data-stu-id="c46c5-141">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="c46c5-142">Wählen Sie im Arbeitsbereich **Bereitstellungsstatus** die Einstellung aus, die Sie wiederherstellen möchten, und wählen Sie dann die bereitgestellte Bereitstellung aus, die wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c46c5-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="c46c5-143">Wählen Sie unter **Notwendigkeit zum Rückgängigmachen dieser Änderung**die Option **Bereitstellung rückgängig**machen aus.</span><span class="sxs-lookup"><span data-stu-id="c46c5-143">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![Bereitstellung konfigurierbarer Einstellungen wiederherstellen](images/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="c46c5-145">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c46c5-145">Additional resources</span></span>
- [<span data-ttu-id="c46c5-146">Übersicht über konfigurierbare Einstellungen</span><span class="sxs-lookup"><span data-stu-id="c46c5-146">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="c46c5-147">Referenz zu konfigurierbaren Einstellungen</span><span class="sxs-lookup"><span data-stu-id="c46c5-147">Configurable settings reference</span></span>](config-setting-ref.md) 
