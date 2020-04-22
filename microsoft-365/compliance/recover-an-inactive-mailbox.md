---
title: Wiederherstellen eines inaktiven Postfachs
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/21/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: 'Wenn ein ehemaliger Mitarbeiter in Ihrer Organisation zurückkehrt oder ein neuer Mitarbeiter für die Übernahme der Aufgaben eines abgemeldeten Mitarbeiters eingestellt ist, können Sie den Inhalt des inaktiven Postfachs in Office 365 wiederherstellen. Wenn Sie ein inaktives Postfach wiederherstellen, wird es in ein neues Postfach konvertiert, das den Inhalt des inaktiven Postfachs enthält. '
ms.openlocfilehash: d79bdf19e4e16d33f55caf10cd864b2627609db7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636273"
---
# <a name="recover-an-inactive-mailbox"></a>Wiederherstellen eines inaktiven Postfachs

Ein inaktives Postfach (eine Art vorläufig gelöschtes Postfach) wird verwendet, um die E-Mails eines ehemaligen Mitarbeiters aufzubewahren, nachdem dieser die Organisation verlassen hat. Wenn ein anderer Mitarbeiter die Zuständigkeiten des ehemaligen Mitarbeiters übernimmt oder dieser Mitarbeiter in Ihre Organisation zurückkehrt, gibt es zwei Möglichkeiten, den Inhalt des inaktiven Postfachs wieder verfügbar zu machen: 
  
- **Wiederherstellen eines inaktiven Postfachs** Wenn der ehemalige Mitarbeiter in Ihre Organisation zurückkehrt oder ein neuer Mitarbeiter eingestellt wird, der die Zuständigkeiten des ehemaligen Mitarbeiters übernimmt, können Sie den Inhalt des inaktiven Postfachs wiederherstellen. Bei dieser Methode wird das inaktive Postfach in ein neues, aktives Postfach mit dem Inhalt des inaktiven Postfachs umgewandelt. Nach der Wiederherstellung ist das inaktive Postfach nicht mehr vorhanden. In diesem Thema werden die Verfahren dieser Methode beschrieben. 
    
- **Wiederherstellen eines inaktiven Postfachs** Wenn ein anderer Mitarbeiter die Aufgaben des ehemaligen Mitarbeiters übernimmt oder ein anderer Benutzer Zugriff auf die Inhalte des inaktiven Postfachs benötigt, können Sie den Inhalt des inaktiven Postfachs in einem vorhandenen Postfach wiederherstellen (oder zusammenführen). Sie können auch das Archiv aus einem inaktiven Postfach rückspeichern. Die Verfahren für diese Methode finden Sie unter [Wiederherstellen eines inaktiven Postfachs in Office 365](restore-an-inactive-mailbox.md).
    
Im Abschnitt [Weitere Informationen](#more-information) finden Sie weitere Details zu den Unterschieden zwischen dem Rückspeichern und Wiederherstellen eines inaktiven Postfachs und eine Beschreibung, was passiert, wenn ein inaktives Postfach wiederhergestellt wird.
  
## <a name="before-you-begin"></a>Bevor Sie beginnen

- Zum Rückspeichern eines inaktiven Postfachs müssen Sie Exchange Online PowerShell verwenden. Das Exchange Admin Center (EAC) kann hierfür nicht verwendet werden. Eine Schritt-für-Schritt-Anleitung finden Sie unter [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
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
    > Verwenden Sie im vorherigen Befehl den Wert der Eigenschaft **DistinguishedName** oder **ExchangeGUID** zum Identifizieren des inaktiven Postfachs. Diese Eigenschaften sind für jedes Postfach in Ihrer Organisation eindeutig, wobei ein aktives und ein inaktives Postfach die gleiche primäre SMTP-Adresse haben können. 
  
2. In diesem Beispiel werden die mit dem vorherigen Befehl abgerufenen Eigenschaften verwendet, und das inaktive Postfach wird in ein aktives Postfach für die Benutzerin Ann Beebe wiederhergestellt. Stellen Sie sicher, dass die für den Parameter " *Name* " und " *MicrosoftOnlineServicesID* " angegebenen Werte innerhalb Ihrer Organisation eindeutig sind. 

    ```powershell
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    Die primäre SMTP-Adresse für das wiederhergestellte inaktive Postfach hat denselben Wert wie der, der durch den *MicrosoftOnlineServicesID* -Parameter angegeben wird. 
    
Nachdem Sie ein inaktives Postfach wiederhergestellt haben, wird auch ein neues Benutzerkonto erstellt. Sie müssen dieses Benutzerkonto aktivieren, indem Sie eine Lizenz zuweisen. Informationen zum Zuweisen einer Lizenz im Microsoft 365 Admin Center finden Sie unter Zuweisen oder Aufheben der [Zuweisung von Lizenzen für Microsoft 365 for Business](https://go.microsoft.com/fwlink/p/?LinkId=276798).
  
## <a name="more-information"></a>Weitere Informationen

- **Was ist der Hauptunterschied zwischen dem Wiederherstellen und dem Rückspeichern eines inaktiven Postfachs?** Wenn Sie ein inaktives Postfach wiederherstellen, wird das Postfach im Wesentlichen in ein neues Postfach umgewandelt, wobei Inhalt und Ordnerstruktur des inaktiven Postfachs beibehalten werden und das Postfach mit einem neuen Benutzerkonto verknüpft wird. Nach der Wiederherstellung ist das inaktive Postfach nicht mehr vorhanden. Alle Änderungen am Inhalt des neuen Postfachs wirken sich auf den Inhalt aus, der ursprünglich im inaktiven Postfach archiviert wurde. Wenn Sie hingegen ein inaktives Postfach rückspeichern, wird der Inhalt lediglich in ein anderes Postfach kopiert. Das inaktive Postfach bleibt als ein solches erhalten. Änderungen am Inhalt des Zielpostfachs wirken sich nicht auf die ursprünglichen Inhalte des inaktiven Postfachs aus. Das inaktive Postfach kann weiterhin mithilfe der Compliance-eDiscovery durchsucht werden. Sein Inhalt kann in ein anderes Postfach rückgespeichert werden, oder es kann zu einem späteren Zeitpunkt wiederhergestellt oder gelöscht werden. 
    
- **Was geschieht, wenn Sie ein inaktives Postfach wiederherstellen?** Wenn Sie ein inaktives Postfach wiederherstellen, geschieht Folgendes: 
    
  - Das Beweissicherungsverfahren (sofern für das inaktive Postfach aktiviert ) wird entfernt.
    
  - Compliance-Archive werden entfernt. Dies bedeutet, dass das inaktive Postfach als Quellpostfach aus dem Compliance-Archiv und der Compliance-eDiscovery-Suche entfernt wird. 
    
  - Das inaktive Postfach wird aus allen Microsoft 365-Aufbewahrungsrichtlinien entfernt, die darauf angewendet wurden.
    
  - Der Zeitraum für die Wiederherstellung einzelner Elemente (der von der Postfacheigenschaft **RetainDeletedItemsFor** bestimmt wird) wird auf 30 Tage festgelegt. Wenn in Exchange Online ein neues Postfach erstellt wird, ist dieser Aufbewahrungszeitraum auf 14 Tage festgelegt. Durch Festlegen dieser Eigenschaft auf den Höchstwert von 30 Tagen bleibt Ihnen mehr Zeit zum Wiederherstellen von Daten, die (endgültig) aus dem inaktiven Postfach gelöscht wurden. Sie können die Wiederherstellung einzelner Elemente auch deaktivieren oder den Wiederherstellungszeitraum für einzelne Elemente wieder auf den Standardwert von 14 Tagen zurücksetzen. Weitere Informationen finden Sie unter [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769).
    
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
 