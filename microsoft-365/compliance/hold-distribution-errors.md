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
# <a name="troubleshoot-ediscovery-hold-errors"></a>Behandeln von eDiscovery-Archiv-Fehlern

In diesem Artikel werden häufige Probleme behandelt, die bei eDiscovery-Halte halte auftreten können, und wie sie behoben werden können. Der Artikel enthält außerdem empfohlene Methoden, mit deren Hilfe Sie diese Probleme beheben oder vermeiden können.

## <a name="recommended-practices"></a>Empfohlene Vorgehensweise

Um die Anzahl der Fehler im Zusammenhang mit eDiscovery-Halte halte zu reduzieren, empfehlen wir die folgenden Methoden:

- Wenn eine Halteverteilung noch aussteht, mit dem Status entweder oder , warten Sie, bis die Halteverteilung abgeschlossen ist, bevor Sie `On (Pending)` `Off (Pending)` weitere Aktualisierungen machen.

- Überprüfen Sie, ob eine Halterichtlinie aussteht, bevor Sie weitere Updates an dieser Richtlinie erstellen. Führen Sie die folgenden Befehle aus, oder speichern Sie sie in einem PowerShell-Skript.

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

- Führen Sie Ihre Updates in einer einzelnen Massenanforderung zu einem eDiscovery-Haltevorgang zusammen, anstatt die Halterichtlinie für jede Transaktion wiederholt zu aktualisieren. Wenn Sie beispielsweise einer vorhandenen Halterichtlinie mithilfe des [Cmdlets Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) mehrere Benutzerpostfächer hinzufügen möchten, führen Sie den Befehl aus (oder fügen Sie einem Skript als Codeblock hinzu), sodass er nur einmal ausgeführt wird, um mehrere Benutzer hinzuzufügen.

  **Richtig**

    ```powershell
    Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   **Falsch**

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user
    }
    ```

   Im vorherigen falschen Beispiel wird das Cmdlet fünf separate Male ausgeführt, um die Aufgabe auszuführen. Weitere Informationen zu den empfohlenen Methoden zum Hinzufügen von Benutzern zu einer Halterichtlinie finden Sie im [Abschnitt Weitere](#more-information) Informationen.

- Führen Sie vor dem Kontaktieren des Microsoft-Support zu eDiscovery-Halteproblemen die Schritte im Abschnitt [Fehler/Problem:](#errorissue-holds-dont-sync) Haltebereich nicht synchronisieren aus, um die Halteverteilung erneut zu wiederholen. Bei diesem Prozess werden häufig temporäre Probleme behoben, z. B. interne Serverfehler.

## <a name="errorissue-holds-dont-sync"></a>Fehler/Problem: Halte halte nicht synchronisiert

Wenn beim Speichern von Custodians und Datenquellen eine der folgenden Fehlermeldungen angezeigt wird, führen Sie die Lösungsschritte aus, um das Problem zu beheben.

> Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet. Es kann weitere 2 Stunden dauern, um den endgültigen Bereitstellungsstatus zu aktualisieren. Überprüfen Sie daher in ein paar Stunden.

> Die Richtlinie kann aufgrund eines temporären Datencenterproblems nicht Office 365 Inhaltsquelle bereitgestellt werden. Die aktuelle Richtlinie wird nicht auf Inhalte in der Quelle angewendet, sodass die blockierte Bereitstellung keine Auswirkungen hat. Um dieses Problem zu beheben, versuchen Sie, die Richtlinie erneut zu bereitstellen.

> Leider konnten die angeforderten Änderungen an der Richtlinie aufgrund eines vorübergehenden internen Serverfehlers nicht ausgeführt werden. Versuchen Sie es in 30 Minuten erneut.

### <a name="resolution"></a>Lösung

1. Verbinden [security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) und führen Sie den folgenden Befehl für eine eDiscovery-Halteschleife aus:

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. Untersuchen Sie den Wert im *Parameter DistributionDetail.* Suchen Sie nach Fehlern wie den folgenden:

   > Fehler: Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet. Es kann weitere 2 Stunden dauern, um den endgültigen Bereitstellungsstatus zu aktualisieren. Überprüfen Sie daher in ein paar Stunden.

3. Versuchen Sie, **den Befehl Set-CaseHoldPolicy -RetryDistribution** für die in Frage gestellte Halterichtlinie auszuführen. Zum Beispiel:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="error-the-sharepoint-site-is-read-only-or-not-accessible"></a>Fehler: Die SharePoint schreibgeschützt oder nicht zugänglich

Wenn die folgende Fehlermeldung angezeigt wird, wenn Custodians und Datenquellen [](/sharepoint/sharepoint-admin-role) gesperrt werden, bedeutet dies, dass der globale Administrator oder SharePoint Ihrer Organisation die Website gesperrt hat. Eine gesperrte Website verhindert, dass eDiscovery einen Halteschutz auf der Website einrist.

> Die SharePoint website ist schreibgeschützt oder nicht zugänglich. Wenden Sie sich an den Websiteadministrator, um die Website schreibbar zu machen, und stellen Sie diese Richtlinie erneut zur Verfügung.

### <a name="resolution"></a>Lösung

Entsperren Sie die Website (oder bitten Sie einen Administrator, sie zu entsperren), um dieses Problem zu beheben. Weitere Informationen zum Ändern des Sperrstatus für eine Website finden Sie unter Sperren und Entsperren [von Websites](/sharepoint/manage-lock-status).

## <a name="error-the-mailbox-or-sharepoint-site-may-not-exist"></a>Fehler: Das Postfach oder SharePoint website ist möglicherweise nicht vorhanden.

Wenn beim Speichern von Custodians und Datenquellen die folgende Fehlermeldung angezeigt wird, führen Sie die Lösungsschritte aus, um das Problem zu beheben.

> Das Postfach oder SharePoint website ist möglicherweise nicht vorhanden.  Wenn dies falsch ist, wenden Sie sich bitte an den Microsoft-Support.  Andernfalls entfernen Sie ihn aus dieser Richtlinie.

### <a name="resolution"></a>Lösung

- Führen Sie [das Get-Mailbox](/powershell/module/exchange/get-mailbox) in Exchange Online PowerShell aus, um zu überprüfen, ob das Benutzerpostfach in Ihrer Organisation vorhanden ist.

- Führen Sie [das Cmdlet Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) in SharePoint Online PowerShell aus, um zu überprüfen, ob die Website in Ihrer Organisation vorhanden ist.

- Überprüfen Sie, ob sich die Website-URL geändert hat.

## <a name="more-information"></a>Weitere Informationen

Die Anleitung zum Aktualisieren von Halterichtlinien für mehrere Benutzer im Abschnitt "Empfohlene Methoden" ergibt sich aus der Tatsache, dass das System gleichzeitige Aktualisierungen einer Halterichtlinie blockiert. Das bedeutet, wenn eine aktualisierte Halterichtlinie auf neue Inhaltsstandorte angewendet wird und sich die Halterichtlinie in einem ausstehenden Zustand befindet, können der Halterichtlinie keine weiteren Inhaltsstandorte hinzugefügt werden. Hier sind einige Dinge, die Sie beachten sollten, um dieses Problem zu beheben:
  
- Jedes Mal, wenn ein aktualisierter Haltestatus aktualisiert wird, wird er sofort in einen ausstehenden Zustand übergeht. Der Status "Ausstehend" bedeutet, dass der Haltestatus auf Inhaltsstandorte angewendet wird.
  
- Wenn Sie über ein Skript verfügen, mit dem eine Schleife ausgeführt wird, und der Richtlinie 1 nach der anderen Speicherorte (ähnlich dem falschen Beispiel im Abschnitt "Empfohlene Methoden") hinzufügt, initiiert der erste Inhaltsspeicherort (z. B. ein Benutzerpostfach) den Synchronisierungsprozess, der den ausstehenden Zustand auslöst. Das bedeutet, dass die anderen Benutzer, die der Richtlinie in nachfolgenden Schleifen hinzugefügt werden, zu einem Fehler führen.
  
- Wenn Ihre Organisation ein Skript verwendet, das eine Schleife zum Aktualisieren der Inhaltsstandorte für eine Halterichtlinie verwendet, müssen Sie das Skript so aktualisieren, dass es Speicherorte in einem einzelnen Massenvorgang aktualisiert (wie im richtigen Beispiel im Abschnitt "Empfohlene Methoden" gezeigt).
