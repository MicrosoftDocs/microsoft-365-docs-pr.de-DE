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
ms.openlocfilehash: 3bd417f2eb6bfb8de8d4b5ccaeb48e6ae1c888eb
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860386"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="3f49b-103">Behandeln von eDiscovery-Archiv-Fehlern</span><span class="sxs-lookup"><span data-stu-id="3f49b-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="3f49b-104">In diesem Artikel werden häufige Probleme behandelt, die bei eDiscovery-Halte halte auftreten können, und wie sie behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="3f49b-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="3f49b-105">Der Artikel enthält außerdem empfohlene Methoden, mit deren Hilfe Sie diese Probleme beheben oder vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="3f49b-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="3f49b-106">Empfohlene Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="3f49b-106">Recommended practices</span></span>

<span data-ttu-id="3f49b-107">Um die Anzahl der Fehler im Zusammenhang mit eDiscovery-Halte halte zu reduzieren, empfehlen wir die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="3f49b-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="3f49b-108">Wenn eine Halteverteilung noch aussteht, mit dem Status entweder oder , warten Sie, bis die Halteverteilung abgeschlossen ist, bevor Sie `On (Pending)` `Off (Pending)` weitere Aktualisierungen machen.</span><span class="sxs-lookup"><span data-stu-id="3f49b-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="3f49b-109">Führen Sie Ihre Updates in einer einzelnen Massenanforderung zu einem eDiscovery-Haltevorgang zusammen, anstatt die Halterichtlinie für jede Transaktion wiederholt zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3f49b-109">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="3f49b-110">Wenn Sie beispielsweise einer vorhandenen Halterichtlinie mithilfe des [Cmdlets Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) mehrere Benutzerpostfächer hinzufügen möchten, führen Sie den Befehl aus (oder fügen Sie einem Skript als Codeblock hinzu), sodass er nur einmal ausgeführt wird, um mehrere Benutzer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3f49b-110">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="3f49b-111">**Richtig**</span><span class="sxs-lookup"><span data-stu-id="3f49b-111">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="3f49b-112">**Falsch**</span><span class="sxs-lookup"><span data-stu-id="3f49b-112">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="3f49b-113">Im vorherigen falschen Beispiel wird das Cmdlet fünf separate Male ausgeführt, um die Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3f49b-113">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="3f49b-114">Weitere Informationen zu den empfohlenen Methoden zum Hinzufügen von Benutzern zu einer Halterichtlinie finden Sie im [Abschnitt Weitere](#more-information) Informationen.</span><span class="sxs-lookup"><span data-stu-id="3f49b-114">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="3f49b-115">Führen Sie vor dem Kontaktieren des Microsoft-Support zu eDiscovery-Halteproblemen die Schritte im Abschnitt [Fehler/Problem:](#errorissue-holds-dont-sync) Haltebereich nicht synchronisieren aus, um die Halteverteilung erneut zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="3f49b-115">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="3f49b-116">Bei diesem Prozess werden häufig temporäre Probleme behoben, z. B. interne Serverfehler.</span><span class="sxs-lookup"><span data-stu-id="3f49b-116">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="3f49b-117">Fehler/Problem: Halte halte nicht synchronisiert</span><span class="sxs-lookup"><span data-stu-id="3f49b-117">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="3f49b-118">Wenn beim Speichern von Custodians und Datenquellen eine der folgenden Fehlermeldungen angezeigt wird, führen Sie die Lösungsschritte aus, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="3f49b-118">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="3f49b-119">Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="3f49b-119">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="3f49b-120">Es kann weitere 2 Stunden dauern, um den endgültigen Bereitstellungsstatus zu aktualisieren. Überprüfen Sie daher in ein paar Stunden.</span><span class="sxs-lookup"><span data-stu-id="3f49b-120">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="3f49b-121">Die Richtlinie kann aufgrund eines temporären Datencenterproblems nicht Office 365 Inhaltsquelle bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3f49b-121">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="3f49b-122">Die aktuelle Richtlinie wird nicht auf Inhalte in der Quelle angewendet, sodass die blockierte Bereitstellung keine Auswirkungen hat.</span><span class="sxs-lookup"><span data-stu-id="3f49b-122">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="3f49b-123">Um dieses Problem zu beheben, versuchen Sie, die Richtlinie erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3f49b-123">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="3f49b-124">Leider konnten die angeforderten Änderungen an der Richtlinie aufgrund eines vorübergehenden internen Serverfehlers nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3f49b-124">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="3f49b-125">Versuchen Sie es in 30 Minuten erneut.</span><span class="sxs-lookup"><span data-stu-id="3f49b-125">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="3f49b-126">Lösung</span><span class="sxs-lookup"><span data-stu-id="3f49b-126">Resolution</span></span>

1. <span data-ttu-id="3f49b-127">Verbinden [security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) und führen Sie den folgenden Befehl für eine eDiscovery-Halteschleife aus:</span><span class="sxs-lookup"><span data-stu-id="3f49b-127">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="3f49b-128">Untersuchen Sie den Wert im *Parameter DistributionDetail.*</span><span class="sxs-lookup"><span data-stu-id="3f49b-128">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="3f49b-129">Suchen Sie nach Fehlern wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="3f49b-129">Look for errors like the following:</span></span>

   > <span data-ttu-id="3f49b-130">Fehler: Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="3f49b-130">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="3f49b-131">Es kann weitere 2 Stunden dauern, um den endgültigen Bereitstellungsstatus zu aktualisieren. Überprüfen Sie daher in ein paar Stunden.</span><span class="sxs-lookup"><span data-stu-id="3f49b-131">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="3f49b-132">Versuchen Sie, **den Befehl Set-CaseHoldPolicy -RetryDistribution** für die in Frage gestellte Halterichtlinie auszuführen. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f49b-132">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="more-information"></a><span data-ttu-id="3f49b-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f49b-133">More information</span></span>

- <span data-ttu-id="3f49b-134">Die Anleitung zum Aktualisieren von Halterichtlinien für mehrere Benutzer im Abschnitt "Empfohlene Methoden" ergibt sich aus der Tatsache, dass das System gleichzeitige Aktualisierungen einer Halterichtlinie blockiert.</span><span class="sxs-lookup"><span data-stu-id="3f49b-134">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="3f49b-135">Das bedeutet, wenn eine aktualisierte Halterichtlinie auf neue Inhaltsstandorte angewendet wird und sich die Halterichtlinie in einem ausstehenden Zustand befindet, können der Halterichtlinie keine weiteren Inhaltsstandorte hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="3f49b-135">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="3f49b-136">Hier sind einige Dinge, die Sie beachten sollten, um dieses Problem zu beheben:</span><span class="sxs-lookup"><span data-stu-id="3f49b-136">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
  - <span data-ttu-id="3f49b-137">Jedes Mal, wenn ein aktualisierter Haltestatus aktualisiert wird, wird er sofort in einen ausstehenden Zustand übergeht.</span><span class="sxs-lookup"><span data-stu-id="3f49b-137">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="3f49b-138">Der Status "Ausstehend" bedeutet, dass der Haltestatus auf Inhaltsstandorte angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f49b-138">The pending state status means the hold is being applied to content locations.</span></span>
  
  - <span data-ttu-id="3f49b-139">Wenn Sie über ein Skript verfügen, mit dem eine Schleife ausgeführt wird, und der Richtlinie 1 nach der anderen Speicherorte (ähnlich dem falschen Beispiel im Abschnitt "Empfohlene Methoden") hinzufügt, initiiert der erste Inhaltsspeicherort (z. B. ein Benutzerpostfach) den Synchronisierungsprozess, der den ausstehenden Zustand auslöst.</span><span class="sxs-lookup"><span data-stu-id="3f49b-139">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="3f49b-140">Das bedeutet, dass die anderen Benutzer, die der Richtlinie in nachfolgenden Schleifen hinzugefügt werden, zu einem Fehler führen.</span><span class="sxs-lookup"><span data-stu-id="3f49b-140">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
  - <span data-ttu-id="3f49b-141">Wenn Ihre Organisation ein Skript verwendet, das eine Schleife zum Aktualisieren der Inhaltsstandorte für eine Halterichtlinie verwendet, müssen Sie das Skript so aktualisieren, dass es Speicherorte in einem einzelnen Massenvorgang aktualisiert (wie im richtigen Beispiel im Abschnitt "Empfohlene Methoden" gezeigt).</span><span class="sxs-lookup"><span data-stu-id="3f49b-141">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
