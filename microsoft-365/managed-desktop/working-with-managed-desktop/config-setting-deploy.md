---
title: Bereitstellen konfigurierbarer Einstellungen in Microsoft Managed Desktop
description: Bereitstellen und Nachverfolgen konfigurierbarer Einstellungsänderungen in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, bereitstellen, mehrstufige Bereitstellung, konfigurierbare Einstellungen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: aad4995f9c329b0fd8fcbcc8b1d13379453c2a76
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287795"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="a2cb8-104">Bereitstellen und Nachverfolgen konfigurierbarer Einstellungen – Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="a2cb8-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="a2cb8-105">Nachdem Sie Änderungen an den Einstellungskategorien vorgenommen und eine Bereitstellung bereitgestellt haben, können Sie auf der Seite "Bereitstellungsstatus" mit der Bereitstellung Ihrer Einstellungen für Gruppen beginnen.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="a2cb8-106">Auf dieser Seite wird eine Zusammenfassung der einzelnen konfigurierbaren Einstellungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="a2cb8-107">Durch Öffnen einer Einstellungskategorie können Sie Einstellungen für Gruppen bereitstellen und den Fortschritt dieser Bereitstellungen nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="a2cb8-108">Bereitstellungsstatus</span><span class="sxs-lookup"><span data-stu-id="a2cb8-108">Deployment statuses</span></span>

<span data-ttu-id="a2cb8-109">Dies sind die Status, die Für jede Bereitstellung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="a2cb8-110">Status</span><span class="sxs-lookup"><span data-stu-id="a2cb8-110">Status</span></span> | <span data-ttu-id="a2cb8-111">Erklärung</span><span class="sxs-lookup"><span data-stu-id="a2cb8-111">Explanation</span></span>
--- | ---
<span data-ttu-id="a2cb8-112">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="a2cb8-112">Deploy</span></span> | <span data-ttu-id="a2cb8-113">Ihre Änderung wartet darauf, für diese Gruppe bereitgestellt zu werden.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="a2cb8-114">In Arbeit</span><span class="sxs-lookup"><span data-stu-id="a2cb8-114">In progress</span></span> | <span data-ttu-id="a2cb8-115">Die Änderung wird auf aktive Geräte in dieser Gruppe angewendet.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-115">The change is being applied to active devices in this group.</span></span>
<span data-ttu-id="a2cb8-116">Abschließen</span><span class="sxs-lookup"><span data-stu-id="a2cb8-116">Complete</span></span> | <span data-ttu-id="a2cb8-117">Die Änderung wurde auf allen aktiven Geräten in dieser Gruppe abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-117">The change completed on all active devices in this group.</span></span>
<span data-ttu-id="a2cb8-118">Fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="a2cb8-118">Failed</span></span> | <span data-ttu-id="a2cb8-119">Die Änderung ist auf 10 Prozent der aktiven Geräte in der Gruppe fehlgeschlagen, sodass die Bereitstellung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="a2cb8-120">Eine Supportanfrage wird automatisch mit Microsoft Managed Desktop-Vorgängen geöffnet, um die Bereitstellung zu beheben.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span>
<span data-ttu-id="a2cb8-121">Wiederhergestellt</span><span class="sxs-lookup"><span data-stu-id="a2cb8-121">Reverted</span></span> | <span data-ttu-id="a2cb8-122">Die Änderung wurde auf die letzte Änderung zurückgesetzt, die erfolgreich für alle Bereitstellungsgruppen bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="a2cb8-123">Bereitstellen von Änderungen</span><span class="sxs-lookup"><span data-stu-id="a2cb8-123">Deploy changes</span></span>

<span data-ttu-id="a2cb8-124">In diesen Anweisungen wird das Hintergrundbild des Desktops angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="a2cb8-125">Nachdem Sie eine Bereitstellung bereitgestellt haben, stellen Sie Änderungen über die Seite "Bereitstellungsstatus" bereit.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span>

<span data-ttu-id="a2cb8-126">**So stellen Sie Änderungen bereit**</span><span class="sxs-lookup"><span data-stu-id="a2cb8-126">**To deploy changes**</span></span>

1. <span data-ttu-id="a2cb8-127">Melden Sie sich bei [Microsoft Endpoint Manager an,](https://endpoint.microsoft.com/) und navigieren Sie zum Menü **"Geräte".**</span><span class="sxs-lookup"><span data-stu-id="a2cb8-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="a2cb8-128">Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, wählen Sie **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="a2cb8-129">Wählen Sie im Arbeitsbereich **"Bereitstellungsstatus"** die Einstellung aus, die Sie bereitstellen möchten, und wählen Sie dann die bereitstellungsbezogene Bereitstellung aus.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="a2cb8-130">Wählen Sie **"Bereitstellen"** aus, um die Änderung in einer der Bereitstellungsgruppen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE]
> <span data-ttu-id="a2cb8-131">Das orangefarbene Warnsymbol zeigt an, dass eine vorherige Gruppe für die Bereitstellung verfügbar ist, da es empfohlen wird, das Rollout in der angegebenen Reihenfolge durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="a2cb8-132">Es wird empfohlen, die Bereitstellung für Bereitstellungsgruppen in der folgenden Reihenfolge durchzuführen: "Test", "First", "Fast" und "Broad".</span><span class="sxs-lookup"><span data-stu-id="a2cb8-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="a2cb8-133">Wenn die Änderungen in jeder Gruppe abgeschlossen sind, wird der Status in **"Abgeschlossen"** geändert.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="a2cb8-134">Bereitstellung kehren zurück</span><span class="sxs-lookup"><span data-stu-id="a2cb8-134">Revert deployment</span></span>

<span data-ttu-id="a2cb8-135">Nachdem Sie eine Änderung bereitgestellt haben, können Sie den **Bereitstellungsstatus** kehren.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="a2cb8-136">Wenn Sie eine Änderung kehren, die **in Bearbeitung** oder **abgeschlossen** ist, wird die aktuelle Bereitstellung beendet.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="a2cb8-137">Die Einstellung wird auf die letzte Version zurückgesetzt, die für alle Gruppen bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-137">The setting will revert to the last version that was deployed to all groups.</span></span>

<span data-ttu-id="a2cb8-138">Wir zeigen die Schritte zum Rückgängig machen einer Änderung mithilfe des Desktop-Hintergrundbilds als Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="a2cb8-139">**So kehren Sie eine Änderung zurück**</span><span class="sxs-lookup"><span data-stu-id="a2cb8-139">**To revert a change**</span></span>

1. <span data-ttu-id="a2cb8-140">Melden Sie sich bei [Microsoft Endpoint Manager an,](https://endpoint.microsoft.com/) und navigieren Sie zum Menü **"Geräte".**</span><span class="sxs-lookup"><span data-stu-id="a2cb8-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="a2cb8-141">Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, wählen Sie **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="a2cb8-142">Wählen Sie im Arbeitsbereich **"Bereitstellungsstatus"** die Einstellung aus, die Sie zurücksetzen möchten, und wählen Sie dann die mehrstufige Bereitstellung aus, die wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="a2cb8-143">Wählen Sie unter **"Notwendigkeit, diese Änderung rückgängig zu machen?"** die Option **"Bereitstellung kehren"** aus.</span><span class="sxs-lookup"><span data-stu-id="a2cb8-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="a2cb8-144">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="a2cb8-144">Additional resources</span></span>

- [<span data-ttu-id="a2cb8-145">Übersicht über konfigurierbare Einstellungen</span><span class="sxs-lookup"><span data-stu-id="a2cb8-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="a2cb8-146">Referenz der konfigurierbaren Einstellungen</span><span class="sxs-lookup"><span data-stu-id="a2cb8-146">Configurable settings reference</span></span>](config-setting-ref.md) 
