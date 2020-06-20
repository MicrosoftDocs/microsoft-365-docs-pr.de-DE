---
title: Wiederherstellen eines inaktiven Postfachs
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
ms.custom: seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie den Inhalt eines inaktiven Postfachs in Office 365 wiederherstellen, indem Sie es in ein neues Postfach konvertieren, das den Inhalt des inaktiven Postfachs enthält.
ms.openlocfilehash: e5ac5a5e5e9e73d118ea1872bf36476ee1e1965a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818945"
---
# <a name="recover-an-inactive-mailbox"></a>Wiederherstellen eines inaktiven Postfachs

An inactive mailbox (which is a type of soft-deleted mailbox) is used to preserve a former employee's email after he or she leaves your organization. If that employee returns to your organization or if another employee takes on the job responsibilities of the former employee, there are two ways that you can make the contents of the inactive mailbox available to a user: 
  
- **Wiederherstellen eines inaktiven Postfachs.** Wenn der frühere Mitarbeiter in Ihrer Organisation zurückkehrt oder ein neuer Mitarbeiter für die Übernahme der Aufgaben des ehemaligen Mitarbeiters eingestellt ist, können Sie den Inhalt des inaktiven Postfachs wiederherstellen. Bei dieser Methode wird das inaktive Postfach in ein neues, aktives Postfach mit dem Inhalt des inaktiven Postfachs umgewandelt. Nach der Wiederherstellung ist das inaktive Postfach nicht mehr vorhanden. In diesem Thema werden die Verfahren dieser Methode beschrieben. 
    
- **Stellen Sie ein inaktives Postfach wieder her.** Wenn ein anderer Mitarbeiter die Aufgaben des ehemaligen Mitarbeiters übernimmt oder ein anderer Benutzer Zugriff auf die Inhalte des inaktiven Postfachs benötigt, können Sie den Inhalt des inaktiven Postfachs in einem vorhandenen Postfach wiederherstellen (oder zusammenführen). Sie können auch das Archiv aus einem inaktiven Postfach rückspeichern. Die Verfahren für diese Methode finden Sie unter [Wiederherstellen eines inaktiven Postfachs in Office 365](restore-an-inactive-mailbox.md).

Im Abschnitt [Weitere Informationen](#more-information) finden Sie weitere Details zu den Unterschieden zwischen dem Rückspeichern und Wiederherstellen eines inaktiven Postfachs und eine Beschreibung, was passiert, wenn ein inaktives Postfach wiederhergestellt wird.
  
## <a name="requirements-to-recover-an-inactive-mailbox"></a>Anforderungen zum Wiederherstellen eines inaktiven Postfachs

- Zum Wiederherstellen eines inaktiven Postfachs müssen Sie Exchange Online PowerShell verwenden. Das Exchange Admin Center (EAC) kann hierfür nicht verwendet werden. Eine Schritt-für-Schritt-Anleitung finden Sie unter [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
- Führen Sie den folgenden Befehl aus, um die Identitätsinformationen für die inaktiven Postfächer in Ihrer Organisation abzurufen. 

    ```powershell
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    Verwenden Sie die von diesem Befehl zurückgegebenen Informationen, um ein bestimmtes inaktives Postfach wiederherzustellen.

## <a name="recover-an-inactive-mailbox"></a>Wiederherstellen eines inaktiven Postfachs

Verwenden Sie das Cmdlet **New-Mailbox** mit dem Parameter *InactiveMailbox* , um ein inaktives Postfach wiederherzustellen. 
  
1. Erstellen Sie eine Variable, die die Eigenschaften des inaktiven Postfachs enthält. 
    
    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address. 
  
2. In diesem Beispiel werden die mit dem vorherigen Befehl abgerufenen Eigenschaften verwendet, und das inaktive Postfach wird in ein aktives Postfach für die Benutzerin Ann Beebe wiederhergestellt. Stellen Sie sicher, dass die für den Parameter " *Name* " und " *MicrosoftOnlineServicesID* " angegebenen Werte innerhalb Ihrer Organisation eindeutig sind. 

    ```powershell
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    Die primäre SMTP-Adresse für das wiederhergestellte inaktive Postfach hat denselben Wert wie der, der durch den *MicrosoftOnlineServicesID* -Parameter angegeben wird. 
    
Nachdem Sie ein inaktives Postfach wiederhergestellt haben, wird auch ein neues Benutzerkonto erstellt. Sie müssen dieses Benutzerkonto aktivieren, indem Sie eine Lizenz zuweisen. Informationen zum Zuweisen einer Lizenz im Microsoft 365 Admin Center finden Sie unter Zuweisen oder Aufheben der [Zuweisung von Lizenzen für Microsoft 365 for Business](https://go.microsoft.com/fwlink/p/?LinkId=276798).
  
## <a name="more-information"></a>Weitere Informationen

- **Worin besteht der Hauptunterschied zwischen dem Wiederherstellen und der Wiederherstellung eines inaktiven Postfachs?** Wenn Sie ein inaktives Postfach wiederherstellen, wird das Postfach in ein neues Postfach umgewandelt, wobei Inhalt und Ordnerstruktur des inaktiven Postfachs beibehalten werden und das Postfach mit einem neuen Benutzerkonto verknüpft wird. Nachdem er wiederhergestellt wurde, ist das inaktive Postfach nicht mehr vorhanden, und alle Änderungen, die an den Inhalten im neuen Postfach vorgenommen wurden, wirken sich auf den Inhalt aus, der im inaktiven Postfach ursprünglich gespeichert wurde. Wenn Sie umgekehrt ein inaktives Postfach wiederherstellen, wird der Inhalt lediglich in ein anderes Postfach kopiert. Das inaktive Postfach wird beibehalten und bleibt ein inaktives Postfach. Alle Änderungen, die an den Inhalten im Zielpostfach vorgenommen werden, wirken sich nicht auf den ursprünglichen Inhalt des inaktiven Postfachs aus. Das inaktive Postfach kann weiterhin mithilfe von in-Place-eDiscovery durchsucht werden, dessen Inhalt kann in einem anderen Postfach wiederhergestellt werden, oder es kann zu einem späteren Zeitpunkt wiederhergestellt oder gelöscht werden. 

- **Was geschieht, wenn Sie ein inaktives Postfach wiederherstellen?** Wenn Sie ein inaktives Postfach wiederherstellen, geschieht Folgendes: 

   - Der auf ein inaktives Postfach angewendete Haltestatus wird basierend auf dem Aufbewahrungs, der vor der Wiederherstellung auf das inaktive Postfach angewendet wurde, geändert oder entfernt.
  
     - **Beweissicherungsverfahren.** Wenn das Beweissicherungsverfahren für das inaktive Postfach aktiviert wurde, wird es aus dem wiederhergestellten Postfach entfernt.
  
     - **In-situ-** Speicher In-Place-Speicher werden aus dem wiederhergestellten Postfach entfernt. Dies bedeutet, dass das wiederhergestellte Postfach als Quellpostfach aus einem in-situ-Speicher oder einer Compliance-eDiscovery-Suche entfernt wurde.
     
     - **Microsoft 365-Aufbewahrungsrichtlinie mit Erhaltungs Sperre.** Wenn das inaktive Postfach einer Aufbewahrungsrichtlinie mit Erhaltungs Sperre zugewiesen wurde (als *Gesperrte Aufbewahrungsrichtlinie*bezeichnet), wird das wiederhergestellte Postfach derselben gesperrten Aufbewahrungsrichtlinie zugewiesen. Weitere Informationen zu gesperrten Aufbewahrungsrichtlinien finden Sie unter Informationen [zu Aufbewahrungsrichtlinien](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements).
  
     - **Microsoft 365-Aufbewahrungsrichtlinie ohne Aufbewahrungs Sperre.** Das inaktive Postfach wird aus einer entsperrten Microsoft 365-Aufbewahrungsrichtlinie entfernt, die auf ihn angewendet wurde. Das Beweissicherungsverfahren ist jedoch für das wiederhergestellte Postfach aktiviert, um das Löschen von Postfachinhalten basierend auf organisationsweiten Aufbewahrungsrichtlinien zu verhindern, die Inhalte löschen, die älter sind als ein bestimmtes Alter. Sie können das Beweissicherungsverfahren halten oder entfernen. Weitere Informationen finden Sie unter [Create a Litigation Hold](create-a-litigation-hold.md).

  - The single item recovery period (which is defined by the **RetainDeletedItemsFor** mailbox property) is set to 30 days. Typically, when a new mailbox is created in Exchange Online, this retention period is set to 14 days. Setting this to the maximum value of 30 days gives you more time to recover any data that's been permanently deleted (or purged) from the inactive mailbox. You can also disable single item recovery or set the single item recovery period back to the default of 14 days. For more information, see [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769).
  
  - Die Aufbewahrungszeit ist aktiviert, und die Aufbewahrungsdauer ist auf 30 Tage festgelegt. Dies bedeutet, dass die standardmäßige Exchange-Aufbewahrungsrichtlinie und alle organisationsweiten oder Exchange-weiten Microsoft 365-Aufbewahrungsrichtlinien, die dem neuen Postfach zugewiesen sind, 30 Tage lang nicht verarbeitet werden. Dadurch erhält der zurückgebende Mitarbeiter oder der neue Besitzer des wiederhergestellten inaktiven Postfachs Zeit, um die alten Nachrichten zu verwalten. Andernfalls löscht die Aufbewahrungsrichtlinie für Exchange oder Microsoft 365 möglicherweise alte Postfachelemente (oder verschiebt Elemente in das Archivpostfach, sofern Sie aktiviert ist), die basierend auf den für die Exchange-oder Microsoft 365-Aufbewahrungsrichtlinien konfigurierten Einstellungen abgelaufen sind. Nach 30 Tagen läuft die Aufbewahrungsdauer ab, die **RetentionHoldEnabled** -Postfacheigenschaft ist auf **false**festgelegt, und der Assistent für verwaltete Ordner beginnt mit der Verarbeitung der dem Postfach zugewiesenen Richtlinien. Wenn Sie diese zusätzliche Zeit nicht benötigen, können Sie den Aufbewahrungsspeicher einfach entfernen. Alternativ können Sie die Aufbewahrungsdauer mithilfe des Befehls " **Sets-Mailbox-EndDateForRetentionHold** " verlängern. Weitere Informationen finden Sie unter [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/?linkid=856300).

- **Halten Sie das wiederhergestellte Postfach ein, wenn Sie den ursprünglichen Status des inaktiven Postfachs beibehalten müssen.** Um zu verhindern, dass der neue Postfachbesitzer oder die Aufbewahrungsrichtlinie dauerhaft alle Nachrichten aus dem wiederhergestellten inaktiven Postfach löscht, können Sie das Postfach für das Beweissicherungsverfahren aufbewahren. Weitere Informationen finden Sie unter [platzieren eines Postfachs bei der Aufbewahrung von Beweissicherungsverfahren](https://go.microsoft.com/fwlink/?linkid=856286).
    
- **Welche Benutzer-ID kann für das Wiederherstellen eines inaktiven Postfachs verwendet werden?** Wenn Sie ein inaktives Postfach wiederherstellen, kann sich der Wert, den Sie für den *MicrosoftOnlineServicesID* -Parameter angeben, von dem Original, das dem inaktiven Postfach zugeordnet wurde, unterscheiden. Sie können auch die ursprüngliche Benutzer-ID verwenden. Aber wie bereits erwähnt, stellen Sie sicher, dass die für *Name* und *MicrosoftOnlineServicesID* verwendeten Werte innerhalb Ihrer Organisation eindeutig sind, wenn Sie das inaktive Postfach wiederherstellen. 
    
- **Was geschieht, wenn die Aufbewahrungszeit für das inaktive Postfach nicht abgelaufen ist?** Wenn ein inaktives Postfach vor weniger als 30 Tagen vorläufig gelöscht wurde, kann es nicht mit dem Befehl **New-Mailbox -InactiveMailbox** wiederhergestellt werden. Sie müssen es wiederherstellen, indem Sie das entsprechende Benutzerkonto wiederherstellen. Weitere Informationen finden Sie unter [Löschen oder Wiederherstellen von Benutzern](https://go.microsoft.com/fwlink/p/?LinkId=279162).
    
- **Woher weiß ich, ob der Aufbewahrungszeitraum für vorläufig gelöschte Postfächer für ein inaktives Postfach abgelaufen ist?** Führen Sie hierzu den folgenden Befehl aus. 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    Wenn die Eigenschaft **ExternalDirectoryObjectId** keinen Wert hat, ist die Aufbewahrungszeit abgelaufen, und Sie können das inaktive Postfach wiederherstellen, indem Sie den Befehl **New-Mailbox -InactiveMailbox** ausführen. Wenn ein Wert für die **ExternalDirectoryObjectId** -Eigenschaft vorhanden ist, ist der Aufbewahrungszeitraum für vorläufig gelöschte Postfächer nicht abgelaufen, und Sie müssen das Postfach wiederherstellen, indem Sie das Benutzerkonto wiederherstellen. Siehe [Löschen oder Wiederherstellen von Benutzern](https://go.microsoft.com/fwlink/p/?LinkId=279162)
    
- **Erwägen Sie das Aktivieren des Archivpostfachs, nachdem Sie ein inaktives Postfach wiederhergestellt haben.** Auf diese Weise kann der zurückkehrende Benutzer oder neue Mitarbeiter alte Nachrichten in das Archivpostfach verschieben. Wenn das Anhalten der Aufbewahrungszeit abgelaufen ist, verschiebt die Archivrichtlinie, die Teil der Exchange Online-Postfächern zugewiesenen standardmäßigen Exchange-Aufbewahrungsrichtlinie ist, Elemente, die zwei Jahre oder älter sind, in das Archivpostfach. Wenn Sie das Archivpostfach nicht aktivieren, verbleiben Elemente, die älter als zwei Jahre sind, im primären Postfach des Benutzers. Weitere Informationen finden Sie unter [Aktivieren von archivpostfächern](enable-archive-mailboxes.md).
 