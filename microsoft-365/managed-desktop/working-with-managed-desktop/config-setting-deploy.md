---
title: Bereitstellen konfigurierbarer Einstellungen in Microsoft Managed Desktop
description: Bereitstellen und Nachverfolgen konfigurierbarer Einstellungen in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, Bereitstellung, mehrstufige Bereitstellung, konfigurierbare Einstellungen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104534"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="b1b5b-104">Bereitstellen und Nachverfolgen konfigurierbarer Einstellungen – Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="b1b5b-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="b1b5b-105">Nachdem Sie Änderungen an den Einstellungskategorien vorgenommen und eine Bereitstellung bereitgestellt haben, können Sie auf der Seite Bereitstellungsstatus mit der Bereitstellung Ihrer Einstellungen für Gruppen beginnen.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="b1b5b-106">Diese Seite enthält eine Zusammenfassung der einzelnen konfigurierbaren Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="b1b5b-107">Durch Öffnen einer Einstellungskategorie können Sie Einstellungen für Gruppen bereitstellen und den Fortschritt dieser Bereitstellungen nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="b1b5b-108">Bereitstellungsstatus</span><span class="sxs-lookup"><span data-stu-id="b1b5b-108">Deployment statuses</span></span> 

<span data-ttu-id="b1b5b-109">Dies sind die Status, die Für jede Bereitstellung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="b1b5b-110">Status</span><span class="sxs-lookup"><span data-stu-id="b1b5b-110">Status</span></span>  | <span data-ttu-id="b1b5b-111">Erklärung</span><span class="sxs-lookup"><span data-stu-id="b1b5b-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="b1b5b-112">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="b1b5b-112">Deploy</span></span> | <span data-ttu-id="b1b5b-113">Ihre Änderung wartet darauf, für diese Gruppe bereitgestellt zu werden.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="b1b5b-114">In Arbeit</span><span class="sxs-lookup"><span data-stu-id="b1b5b-114">In progress</span></span> | <span data-ttu-id="b1b5b-115">Die Änderung wird auf aktive Geräte in dieser Gruppe angewendet.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="b1b5b-116">Abschließen</span><span class="sxs-lookup"><span data-stu-id="b1b5b-116">Complete</span></span> | <span data-ttu-id="b1b5b-117">Die Änderung wurde auf allen aktiven Geräten in dieser Gruppe abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="b1b5b-118">Fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="b1b5b-118">Failed</span></span> | <span data-ttu-id="b1b5b-119">Die Änderung ist auf 10 Prozent der aktiven Geräte in der Gruppe fehlgeschlagen, sodass die Bereitstellung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="b1b5b-120">Eine Supportanfrage wird automatisch mit Microsoft Managed Desktop-Vorgängen geöffnet, um die Bereitstellung zu beheben.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="b1b5b-121">Reverted</span><span class="sxs-lookup"><span data-stu-id="b1b5b-121">Reverted</span></span> | <span data-ttu-id="b1b5b-122">Die Änderung wurde auf die letzte Änderung zurückgesetzt, die erfolgreich für alle Bereitstellungsgruppen bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="b1b5b-123">Bereitstellen von Änderungen</span><span class="sxs-lookup"><span data-stu-id="b1b5b-123">Deploy changes</span></span>

<span data-ttu-id="b1b5b-124">In diesen Anweisungen wird das Desktophintergrundbild angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="b1b5b-125">Nachdem Sie eine Bereitstellung bereitgestellt haben, stellen Sie Änderungen auf der Seite Bereitstellungsstatus zur Bereitstellung zur Bereitstellungsstatusseite zur Bereitstellungsstatusseite.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="b1b5b-126">**So stellen Sie Änderungen zur Bereitstellung**</span><span class="sxs-lookup"><span data-stu-id="b1b5b-126">**To deploy changes**</span></span>

1. <span data-ttu-id="b1b5b-127">Melden Sie sich bei [Microsoft Endpoint Manager an,](https://endpoint.microsoft.com/) und navigieren Sie zum **Menü Geräte**</span><span class="sxs-lookup"><span data-stu-id="b1b5b-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="b1b5b-128">Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, wählen Sie **Einstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="b1b5b-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="b1b5b-129">Wählen **Sie im** Arbeitsbereich Bereitstellungsstatus die Einstellung aus, die Sie bereitstellen möchten, und wählen Sie dann die bereitstellungsstufige Bereitstellung aus.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="b1b5b-130">Wählen **Sie Bereitstellen** aus, um die Änderung in einer der Bereitstellungsgruppen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="b1b5b-131">Das orangefarbene Warnsymbol zeigt an, dass eine vorherige Gruppe für die Bereitstellung verfügbar ist, da es empfohlen wird, den Rollup in der Reihenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="b1b5b-132">Es wird empfohlen, bereitstellungsgruppen in der reihenfolge: Test, First, Fast, and then Broad.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="b1b5b-133">Wenn die Änderungen in jeder Gruppe abgeschlossen sind, wird der Status in **Abgeschlossen geändert.**</span><span class="sxs-lookup"><span data-stu-id="b1b5b-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="b1b5b-134">Bereitstellung wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="b1b5b-134">Revert deployment</span></span>

<span data-ttu-id="b1b5b-135">Nachdem Sie eine Änderung bereitgestellt haben, können Sie den Bereitstellungsstatus **wiederherstellen.**</span><span class="sxs-lookup"><span data-stu-id="b1b5b-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="b1b5b-136">Wenn Sie eine Änderung wiederherstellen, die **in Bearbeitung ist** oder abgeschlossen **ist,** wird die aktuelle Bereitstellung beendet.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="b1b5b-137">Die Einstellung kehrt zur letzten Version zurück, die für alle Gruppen bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="b1b5b-138">Wir zeigen die Schritte zum Wiederherstellen einer Änderung mithilfe des Desktophintergrundbilds als Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="b1b5b-139">**So wiederherstellen Sie eine Änderung**</span><span class="sxs-lookup"><span data-stu-id="b1b5b-139">**To revert a change**</span></span>
1. <span data-ttu-id="b1b5b-140">Melden Sie sich bei [Microsoft Endpoint Manager an,](https://endpoint.microsoft.com/) und navigieren Sie zum **Menü Geräte**</span><span class="sxs-lookup"><span data-stu-id="b1b5b-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="b1b5b-141">Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, wählen Sie **Einstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="b1b5b-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="b1b5b-142">Wählen **Sie im** Arbeitsbereich Bereitstellungsstatus die Einstellung aus, die Sie wiederherstellen möchten, und wählen Sie dann die mehrstufige Bereitstellung aus, die wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b1b5b-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="b1b5b-143">Wählen **Sie unter Diese Änderung wiederherstellen?** die Option Bereitstellung **wiederherstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="b1b5b-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="b1b5b-144">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b1b5b-144">Additional resources</span></span>
- [<span data-ttu-id="b1b5b-145">Übersicht über konfigurierbare Einstellungen</span><span class="sxs-lookup"><span data-stu-id="b1b5b-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="b1b5b-146">Referenz der konfigurierbaren Einstellungen</span><span class="sxs-lookup"><span data-stu-id="b1b5b-146">Configurable settings reference</span></span>](config-setting-ref.md) 
