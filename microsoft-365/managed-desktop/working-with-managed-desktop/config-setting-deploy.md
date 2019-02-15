---
title: Bereitstellen von konfigurierbaren Einstellungen in Microsoft Managed Desktop
description: Bereitstellen und Nachverfolgen von Änderungen an konfigurierbaren Einstellungen in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, Deploy, Staging-Bereitstellung, konfigurierbare Einstellungen
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/12/2019
ms.openlocfilehash: fd0e0750332fa8f650cfc4756f8eb108be2a71df
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051126"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="5a912-104">Bereitstellen und Nachverfolgen von konfigurierbaren Einstellungen – Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5a912-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="5a912-p101">Nachdem Sie Änderungen an den Einstellungskategorien vorgenommen und eine Bereitstellung ausgeführt haben, können Sie den Bereitstellungsstatus für die Bereitstellung bereitstellen und nachverfolgen. Auf dieser Seite wird eine Zusammenfassung der einzelnen konfigurierbaren Einstellungen angezeigt. Öffnen Sie eine Einstellungskategorie, um die einzelnen Bereitstellungen und Ihre Details anzuzeigen, um die Änderungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5a912-p101">After you make changes to your setting categories and stage a deployment, you can deploy and track progress for the deployment on Deployment status. This page shows a summary of each configurable setting. Open a setting category to see each deployment and their details, to deploy the changes.</span></span> 

## <a name="deployment-statuses"></a><span data-ttu-id="5a912-108">Bereitstellungsstatus</span><span class="sxs-lookup"><span data-stu-id="5a912-108">Deployment statuses</span></span> 

<span data-ttu-id="5a912-109">Dies sind die Statuen, die für jede Bereitstellung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5a912-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="5a912-110">Status</span><span class="sxs-lookup"><span data-stu-id="5a912-110">Status</span></span>  | <span data-ttu-id="5a912-111">Erläuterung</span><span class="sxs-lookup"><span data-stu-id="5a912-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="5a912-112">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="5a912-112">Deploy</span></span> | <span data-ttu-id="5a912-113">Ihre Änderung wartet auf die Bereitstellung für diesen Ring.</span><span class="sxs-lookup"><span data-stu-id="5a912-113">Your change is waiting to be deployed to this ring.</span></span>
<span data-ttu-id="5a912-114">In Bearbeitung</span><span class="sxs-lookup"><span data-stu-id="5a912-114">In progress</span></span> | <span data-ttu-id="5a912-115">Die Änderung wird auf Geräte in diesem Ring angewendet.</span><span class="sxs-lookup"><span data-stu-id="5a912-115">The change is being applied to devices in this ring.</span></span> 
<span data-ttu-id="5a912-116">Vollständig</span><span class="sxs-lookup"><span data-stu-id="5a912-116">Complete</span></span> | <span data-ttu-id="5a912-117">Die Änderung wird auf Geräte in diesem Ring angewendet.</span><span class="sxs-lookup"><span data-stu-id="5a912-117">The change is being applied to devices in this ring.</span></span> 
<span data-ttu-id="5a912-118">Failed</span><span class="sxs-lookup"><span data-stu-id="5a912-118">Failed</span></span> | <span data-ttu-id="5a912-119">Die Änderung ist bei 10 Prozent der Geräte im Ring fehlgeschlagen, sodass die Bereitstellung angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="5a912-119">The change failed on a 10 percent of devices in the ring, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="5a912-120">Eine Supportanforderung wird automatisch mit Microsoft Managed Desktop-Vorgängen geöffnet, um die Bereitstellung zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="5a912-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="5a912-121">Zurückgesetzt</span><span class="sxs-lookup"><span data-stu-id="5a912-121">Reverted</span></span> | <span data-ttu-id="5a912-122">Die Änderung wurde auf die letzte Änderung zurückgesetzt, die erfolgreich für alle Bereitstellungs Ringe bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5a912-122">The change was reverted to the last change that was successfully deployed to all deployment rings.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="5a912-123">Bereitstellen von Änderungen</span><span class="sxs-lookup"><span data-stu-id="5a912-123">Deploy changes</span></span>

<span data-ttu-id="5a912-p102">In diesen Anweisungen wird das Hintergrundbild des Desktops angezeigt. Nachdem Sie eine Bereitstellung inszeniert haben, stellen Sie Änderungen aus dem Bereitstellungsstatus bereit.</span><span class="sxs-lookup"><span data-stu-id="5a912-p102">We’ll show Desktop background picture in these instructions. After you’ve staged a deployment, you deploy changes from Deployment status.</span></span> 

<span data-ttu-id="5a912-126">**So stellen Sie Änderungen bereit**</span><span class="sxs-lookup"><span data-stu-id="5a912-126">**To deploy changes**</span></span>

1. <span data-ttu-id="5a912-127">Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="5a912-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="5a912-128">Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.</span><span class="sxs-lookup"><span data-stu-id="5a912-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="5a912-129">Wählen Sie im **Bereitstellungsstatus** -Arbeitsbereich die Einstellung aus, die Sie bereitstellen möchten, und wählen Sie dann die bereitgestellte Bereitstellung mit Staging aus.</span><span class="sxs-lookup"><span data-stu-id="5a912-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="5a912-130">Wählen Sie **Bereitstellen** aus, um die Änderung an einem der Bereitstellungs Ringe bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5a912-130">Select **Deploy** to deploy the change to one of the deployment rings.</span></span>

![Bereitstellungsstatus für konfigurierbare Einstellungen (Übersicht)](images/deploy-cs-overview.png)

<span data-ttu-id="5a912-132">Microsoft Managed Desktop empfiehlt die Bereitstellung in Bereitstellungs Ringen in dieser Reihenfolge: Test, First, fast und dann Broad.</span><span class="sxs-lookup"><span data-stu-id="5a912-132">Microsoft Managed Desktop recommends deploying to deployment rings in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="5a912-133">Wenn in jedem Ring Änderungen vorgenommen werden, wird der Status in **abgeschlossen**geändert.</span><span class="sxs-lookup"><span data-stu-id="5a912-133">When changes complete in each ring, the status changes to **Complete**.</span></span>

![Vollständige Bereitstellung von konfigurierbaren Einstellungen](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="5a912-135">Wiederherstellen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="5a912-135">Revert deployment</span></span>

<span data-ttu-id="5a912-136">In diesen Anweisungen wird das Hintergrundbild des Desktops angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a912-136">We’ll show Desktop background picture in these instructions.</span></span> 

<span data-ttu-id="5a912-p103">Nachdem Sie eine Änderung bereitgestellt haben, können Sie den **Bereitstellungsstatus**wiederherstellen. Wenn Sie eine Änderung zurücksetzen, die gerade **ausgeführt** wird oder **abgeschlossen**ist, wird die aktuelle Bereitstellung angehalten. Die Einstellung wird auf die letzte Version zurückgesetzt, die für alle Ringe bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5a912-p103">After you’ve deployed a change, you can revert from **Deployment status**. When you revert a change that is **In progress** or **Complete**, the current deployment stops. The setting will revert to the last version that was deployed to all rings.</span></span> 

<span data-ttu-id="5a912-140">**So stellen Sie eine Änderung wieder her**</span><span class="sxs-lookup"><span data-stu-id="5a912-140">**To revert a change**</span></span>
1. <span data-ttu-id="5a912-141">Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="5a912-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="5a912-142">Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.</span><span class="sxs-lookup"><span data-stu-id="5a912-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="5a912-143">Wählen Sie im **Bereitstellungsstatus** -Arbeitsbereich die Einstellung aus, die Sie wiederherstellen möchten, und wählen Sie dann die wiederherzustellende Staging-Bereitstellung aus.</span><span class="sxs-lookup"><span data-stu-id="5a912-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="5a912-144">Wenn Sie **diese Änderung rückgängig**machen möchten, wählen Sie **Bereitstellung zurück**setzen aus.</span><span class="sxs-lookup"><span data-stu-id="5a912-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![Konfigurierbare Einstellungen werden wiederhergestellt](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="5a912-146">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5a912-146">Additional resources</span></span>
- [<span data-ttu-id="5a912-147">Übersicht über konfigurierbare Einstellungen</span><span class="sxs-lookup"><span data-stu-id="5a912-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="5a912-148">Referenz zu konfigurierbaren Einstellungen</span><span class="sxs-lookup"><span data-stu-id="5a912-148">Configurable settings reference</span></span>](config-setting-ref.md) 