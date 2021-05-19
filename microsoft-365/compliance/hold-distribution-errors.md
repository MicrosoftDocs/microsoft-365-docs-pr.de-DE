---
title: Behandeln von eDiscovery-Archiv-Fehlern
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Behandeln von Fehlern im Zusammenhang mit rechtlichen Halterechten, die auf Verwahrer und nicht verwahrte Datenquellen in Core eDiscovery angewendet werden.
ms.openlocfilehash: b101bf92c6a304262b3886a4ce0280f427a4a847
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538471"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="f1ae6-103">Behandeln von eDiscovery-Archiv-Fehlern</span><span class="sxs-lookup"><span data-stu-id="f1ae6-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="f1ae6-104">In diesem Artikel werden häufige Probleme behandelt, die bei eDiscovery-Halte halte auftreten können, und wie sie behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="f1ae6-105">Der Artikel enthält außerdem empfohlene Methoden, mit deren Hilfe Sie diese Probleme beheben oder vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="f1ae6-106">Empfohlene Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="f1ae6-106">Recommended practices</span></span>

<span data-ttu-id="f1ae6-107">Um die Anzahl der Fehler im Zusammenhang mit eDiscovery-Halte halte zu reduzieren, empfehlen wir die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="f1ae6-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="f1ae6-108">Wenn eine Halteverteilung noch aussteht, mit dem Status entweder oder , warten Sie, bis die Halteverteilung abgeschlossen ist, bevor Sie `On (Pending)` `Off (Pending)` weitere Aktualisierungen machen.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="f1ae6-109">Überprüfen Sie, ob eine Halterichtlinie aussteht, bevor Sie weitere Updates an dieser Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-109">Check whether a hold policy is pending before you make any further updates to it.</span></span> <span data-ttu-id="f1ae6-110">Führen Sie die folgenden Befehle aus, oder speichern Sie sie in einem PowerShell-Skript.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-110">Run the following commands or save them to a PowerShell script.</span></span>

    ```powershell
    $status = Get-CaseHoldPolicy -Identity <policyname> 
    if($status.DistributionStatus -ne "Pending"){
        # policy no longer pending
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user1
    }else{
        # policy still pending
        Write-Host "Hold policy still pending."
    }
   ```

- <span data-ttu-id="f1ae6-111">Führen Sie Ihre Updates in einer einzelnen Massenanforderung zu einem eDiscovery-Haltevorgang zusammen, anstatt die Halterichtlinie für jede Transaktion wiederholt zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-111">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="f1ae6-112">Wenn Sie beispielsweise einer vorhandenen Halterichtlinie mithilfe des [Cmdlets Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) mehrere Benutzerpostfächer hinzufügen möchten, führen Sie den Befehl aus (oder fügen Sie einem Skript als Codeblock hinzu), sodass er nur einmal ausgeführt wird, um mehrere Benutzer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-112">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="f1ae6-113">**Richtig**</span><span class="sxs-lookup"><span data-stu-id="f1ae6-113">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="f1ae6-114">**Falsch**</span><span class="sxs-lookup"><span data-stu-id="f1ae6-114">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="f1ae6-115">Im vorherigen falschen Beispiel wird das Cmdlet fünf separate Male ausgeführt, um die Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-115">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="f1ae6-116">Weitere Informationen zu den empfohlenen Methoden zum Hinzufügen von Benutzern zu einer Halterichtlinie finden Sie im [Abschnitt Weitere](#more-information) Informationen.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-116">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="f1ae6-117">Führen Sie vor dem Kontaktieren des Microsoft-Support zu eDiscovery-Halteproblemen die Schritte im Abschnitt [Fehler/Problem:](#errorissue-holds-dont-sync) Haltebereich nicht synchronisieren aus, um die Halteverteilung erneut zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-117">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="f1ae6-118">Bei diesem Prozess werden häufig temporäre Probleme behoben, z. B. interne Serverfehler.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-118">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="f1ae6-119">Fehler/Problem: Halte halte nicht synchronisiert</span><span class="sxs-lookup"><span data-stu-id="f1ae6-119">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="f1ae6-120">Wenn beim Speichern von Custodians und Datenquellen eine der folgenden Fehlermeldungen angezeigt wird, führen Sie die Lösungsschritte aus, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-120">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="f1ae6-121">Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-121">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="f1ae6-122">Es kann weitere 2 Stunden dauern, um den endgültigen Bereitstellungsstatus zu aktualisieren. Überprüfen Sie daher in ein paar Stunden.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-122">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="f1ae6-123">Die Richtlinie kann aufgrund eines temporären Datencenterproblems nicht Office 365 Inhaltsquelle bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-123">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="f1ae6-124">Die aktuelle Richtlinie wird nicht auf Inhalte in der Quelle angewendet, sodass die blockierte Bereitstellung keine Auswirkungen hat.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-124">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="f1ae6-125">Um dieses Problem zu beheben, versuchen Sie, die Richtlinie erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-125">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="f1ae6-126">Leider konnten die angeforderten Änderungen an der Richtlinie aufgrund eines vorübergehenden internen Serverfehlers nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-126">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="f1ae6-127">Versuchen Sie es in 30 Minuten erneut.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-127">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="f1ae6-128">Lösung</span><span class="sxs-lookup"><span data-stu-id="f1ae6-128">Resolution</span></span>

1. <span data-ttu-id="f1ae6-129">Verbinden [security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) und führen Sie den folgenden Befehl für eine eDiscovery-Halteschleife aus:</span><span class="sxs-lookup"><span data-stu-id="f1ae6-129">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="f1ae6-130">Untersuchen Sie den Wert im *Parameter DistributionDetail.*</span><span class="sxs-lookup"><span data-stu-id="f1ae6-130">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="f1ae6-131">Suchen Sie nach Fehlern wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="f1ae6-131">Look for errors like the following:</span></span>

   > <span data-ttu-id="f1ae6-132">Fehler: Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-132">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="f1ae6-133">Es kann weitere 2 Stunden dauern, um den endgültigen Bereitstellungsstatus zu aktualisieren. Überprüfen Sie daher in ein paar Stunden.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-133">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="f1ae6-134">Versuchen Sie, **den Befehl Set-CaseHoldPolicy -RetryDistribution** für die in Frage gestellte Halterichtlinie auszuführen. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f1ae6-134">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="error-the-sharepoint-site-is-read-only-or-not-accessible"></a><span data-ttu-id="f1ae6-135">Fehler: Die SharePoint schreibgeschützt oder nicht zugänglich</span><span class="sxs-lookup"><span data-stu-id="f1ae6-135">Error: The SharePoint site is read-only or not accessible</span></span>

<span data-ttu-id="f1ae6-136">Wenn die folgende Fehlermeldung angezeigt wird, wenn Custodians und Datenquellen [](/sharepoint/sharepoint-admin-role) gesperrt werden, bedeutet dies, dass der globale Administrator oder SharePoint Ihrer Organisation die Website gesperrt hat.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-136">If you see the following error message when putting custodians and data sources on hold, it means that your organization's [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) has locked the site.</span></span> <span data-ttu-id="f1ae6-137">Eine gesperrte Website verhindert, dass eDiscovery einen Halteschutz auf der Website einrist.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-137">A locked site blocks eDiscovery from placing a hold on the site.</span></span>

> <span data-ttu-id="f1ae6-138">Die SharePoint website ist schreibgeschützt oder nicht zugänglich.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-138">The SharePoint site is read-only or not accessible.</span></span> <span data-ttu-id="f1ae6-139">Wenden Sie sich an den Websiteadministrator, um die Website schreibbar zu machen, und stellen Sie diese Richtlinie erneut zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-139">Please contact the site administrator to make the site writable, and then redeploy this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="f1ae6-140">Lösung</span><span class="sxs-lookup"><span data-stu-id="f1ae6-140">Resolution</span></span>

<span data-ttu-id="f1ae6-141">Entsperren Sie die Website (oder bitten Sie einen Administrator, sie zu entsperren), um dieses Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-141">Unlock the site (or ask an admin to unlock it) to resolve this issue.</span></span> <span data-ttu-id="f1ae6-142">Weitere Informationen zum Ändern des Sperrstatus für eine Website finden Sie unter Sperren und Entsperren [von Websites](/sharepoint/manage-lock-status).</span><span class="sxs-lookup"><span data-stu-id="f1ae6-142">To learn more about how to change the lock state for a site, see [Lock and unlock sites](/sharepoint/manage-lock-status).</span></span>

## <a name="error-the-mailbox-or-sharepoint-site-may-not-exist"></a><span data-ttu-id="f1ae6-143">Fehler: Das Postfach oder SharePoint website ist möglicherweise nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-143">Error: The mailbox or SharePoint site may not exist</span></span>

<span data-ttu-id="f1ae6-144">Wenn beim Speichern von Custodians und Datenquellen die folgende Fehlermeldung angezeigt wird, führen Sie die Lösungsschritte aus, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-144">If you see the following error message when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="f1ae6-145">Das Postfach oder SharePoint website ist möglicherweise nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-145">The mailbox or SharePoint site may not exist.</span></span>  <span data-ttu-id="f1ae6-146">Wenn dies falsch ist, wenden Sie sich bitte an den Microsoft-Support.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-146">If this is incorrect, please contact Microsoft support.</span></span>  <span data-ttu-id="f1ae6-147">Andernfalls entfernen Sie ihn aus dieser Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-147">Otherwise, please remove it from this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="f1ae6-148">Lösung</span><span class="sxs-lookup"><span data-stu-id="f1ae6-148">Resolution</span></span>

- <span data-ttu-id="f1ae6-149">Führen Sie [das Get-Mailbox](/powershell/module/exchange/get-mailbox) in Exchange Online PowerShell aus, um zu überprüfen, ob das Benutzerpostfach in Ihrer Organisation vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-149">Run the [Get-Mailbox](/powershell/module/exchange/get-mailbox) in Exchange Online PowerShell to check if the user mailbox exists in your organization.</span></span>

- <span data-ttu-id="f1ae6-150">Führen Sie [das Cmdlet Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) in SharePoint Online PowerShell aus, um zu überprüfen, ob die Website in Ihrer Organisation vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-150">Run the [Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) cmdlet in SharePoint Online PowerShell to check if the site exists in your organization.</span></span>

- <span data-ttu-id="f1ae6-151">Überprüfen Sie, ob sich die Website-URL geändert hat.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-151">Check to see if the site URL has changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="f1ae6-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1ae6-152">More information</span></span>

<span data-ttu-id="f1ae6-153">Die Anleitung zum Aktualisieren von Halterichtlinien für mehrere Benutzer im Abschnitt "Empfohlene Methoden" ergibt sich aus der Tatsache, dass das System gleichzeitige Aktualisierungen einer Halterichtlinie blockiert.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-153">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="f1ae6-154">Das bedeutet, wenn eine aktualisierte Halterichtlinie auf neue Inhaltsstandorte angewendet wird und sich die Halterichtlinie in einem ausstehenden Zustand befindet, können der Halterichtlinie keine weiteren Inhaltsstandorte hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-154">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="f1ae6-155">Hier sind einige Dinge, die Sie beachten sollten, um dieses Problem zu beheben:</span><span class="sxs-lookup"><span data-stu-id="f1ae6-155">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
- <span data-ttu-id="f1ae6-156">Jedes Mal, wenn ein aktualisierter Haltestatus aktualisiert wird, wird er sofort in einen ausstehenden Zustand übergeht.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-156">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="f1ae6-157">Der Status "Ausstehend" bedeutet, dass der Haltestatus auf Inhaltsstandorte angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-157">The pending state status means the hold is being applied to content locations.</span></span>
  
- <span data-ttu-id="f1ae6-158">Wenn Sie über ein Skript verfügen, mit dem eine Schleife ausgeführt wird, und der Richtlinie 1 nach der anderen Speicherorte (ähnlich dem falschen Beispiel im Abschnitt "Empfohlene Methoden") hinzufügt, initiiert der erste Inhaltsspeicherort (z. B. ein Benutzerpostfach) den Synchronisierungsprozess, der den ausstehenden Zustand auslöst.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-158">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="f1ae6-159">Das bedeutet, dass die anderen Benutzer, die der Richtlinie in nachfolgenden Schleifen hinzugefügt werden, zu einem Fehler führen.</span><span class="sxs-lookup"><span data-stu-id="f1ae6-159">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
- <span data-ttu-id="f1ae6-160">Wenn Ihre Organisation ein Skript verwendet, das eine Schleife zum Aktualisieren der Inhaltsstandorte für eine Halterichtlinie verwendet, müssen Sie das Skript so aktualisieren, dass es Speicherorte in einem einzelnen Massenvorgang aktualisiert (wie im richtigen Beispiel im Abschnitt "Empfohlene Methoden" gezeigt).</span><span class="sxs-lookup"><span data-stu-id="f1ae6-160">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
