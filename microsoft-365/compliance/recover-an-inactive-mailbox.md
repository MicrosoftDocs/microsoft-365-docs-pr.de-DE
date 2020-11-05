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
ms.openlocfilehash: ab5b3265cd9d3b1bab539d45e5daf0e6b4110f9a
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920051"
---
# <a name="recover-an-inactive-mailbox"></a>Wiederherstellen eines inaktiven Postfachs

Ein inaktives Postfach (eine Art vorläufig gelöschtes Postfach) wird verwendet, um die E-Mails eines ehemaligen Mitarbeiters aufzubewahren, nachdem dieser die Organisation verlassen hat. Wenn ein anderer Mitarbeiter die Zuständigkeiten des ehemaligen Mitarbeiters übernimmt oder dieser Mitarbeiter in Ihre Organisation zurückkehrt, gibt es zwei Möglichkeiten, den Inhalt des inaktiven Postfachs wieder verfügbar zu machen:

- **Wiederherstellen eines inaktiven Postfachs.** Wenn der frühere Mitarbeiter in Ihrer Organisation zurückkehrt oder ein neuer Mitarbeiter für die Übernahme der Aufgaben des ehemaligen Mitarbeiters eingestellt ist, können Sie den Inhalt des inaktiven Postfachs wiederherstellen. Bei dieser Methode wird das inaktive Postfach in ein neues, aktives Postfach mit dem Inhalt des inaktiven Postfachs umgewandelt. Nach der Wiederherstellung ist das inaktive Postfach nicht mehr vorhanden. In diesem Thema werden die Verfahren dieser Methode beschrieben.

- **Stellen Sie ein inaktives Postfach wieder her.** Wenn ein anderer Mitarbeiter die Aufgaben des ehemaligen Mitarbeiters übernimmt oder ein anderer Benutzer Zugriff auf die Inhalte des inaktiven Postfachs benötigt, können Sie den Inhalt des inaktiven Postfachs in einem vorhandenen Postfach wiederherstellen (oder zusammenführen). Sie können auch das Archiv aus einem inaktiven Postfach rückspeichern. Die Verfahren für diese Methode finden Sie unter [Wiederherstellen eines inaktiven Postfachs in Office 365](restore-an-inactive-mailbox.md).

Im Abschnitt [Weitere Informationen](#more-information) finden Sie weitere Details zu den Unterschieden zwischen dem Rückspeichern und Wiederherstellen eines inaktiven Postfachs und eine Beschreibung, was passiert, wenn ein inaktives Postfach wiederhergestellt wird.

> [!NOTE]
> Sie können ein inaktives Postfach, das mit einem automatisch expandierenden Archiv konfiguriert ist, nicht wiederherstellen oder wiederherstellen. Wenn Sie Daten aus einem inaktiven Postfach mit einem automatisch expandierenden Archiv wiederherstellen müssen, verwenden Sie die Inhaltssuche, um die Daten aus dem Postfach zu exportieren und dann in ein anderes Postfach zu importieren. Anweisungen finden Sie unter den folgenden Themen:
>
> - [Inhaltssuche](content-search.md)
> - [Exportieren von Inhalts Suchergebnissen](export-search-results.md)

## <a name="requirements-to-recover-an-inactive-mailbox"></a>Anforderungen zum Wiederherstellen eines inaktiven Postfachs

- Zum Wiederherstellen eines inaktiven Postfachs müssen Sie Exchange Online PowerShell verwenden. Das Exchange Admin Center (EAC) kann hierfür nicht verwendet werden. Eine Schritt-für-Schritt-Anleitung finden Sie unter [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Führen Sie den folgenden Befehl aus, um die Identitätsinformationen für die inaktiven Postfächer in Ihrer Organisation abzurufen.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  Verwenden Sie die von diesem Befehl zurückgegebenen Informationen, um ein bestimmtes inaktives Postfach wiederherzustellen.

## <a name="recover-inactive-mailboxes"></a>Wiederherstellen inaktiver Postfächer

Verwenden Sie das Cmdlet **New-Mailbox** mit dem Parameter  *InactiveMailbox*  , um ein inaktives Postfach wiederherzustellen.

1. Erstellen Sie eine Variable, die die Eigenschaften des inaktiven Postfachs enthält.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > Verwenden Sie im vorherigen Befehl den Wert der Eigenschaft **DistinguishedName** oder **ExchangeGUID** zum Identifizieren des inaktiven Postfachs. Diese Eigenschaften sind für jedes Postfach in Ihrer Organisation eindeutig, wobei ein aktives und ein inaktives Postfach die gleiche primäre SMTP-Adresse haben können.

2. In diesem Beispiel werden die mit dem vorherigen Befehl abgerufenen Eigenschaften verwendet, und das inaktive Postfach wird in ein aktives Postfach für die Benutzerin Ann Beebe wiederhergestellt. Stellen Sie sicher, dass die für den Parameter "  *Name*  " und "  *MicrosoftOnlineServicesID*  " angegebenen Werte innerhalb Ihrer Organisation eindeutig sind.

   ```powershell
   New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
   ```

   Die primäre SMTP-Adresse für das wiederhergestellte inaktive Postfach hat denselben Wert wie der, der durch den  *MicrosoftOnlineServicesID*  -Parameter angegeben wird.

Nachdem Sie ein inaktives Postfach wiederhergestellt haben, wird auch ein neues Benutzerkonto erstellt. Sie müssen dieses Benutzerkonto aktivieren, indem Sie eine Lizenz zuweisen. Informationen zum Zuweisen einer Lizenz im Microsoft 365 Admin Center finden Sie unter [Hinzufügen von Benutzern und Zuweisen von Lizenzen gleichzeitig](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users).

## <a name="more-information"></a>Weitere Informationen

- **Worin besteht der Hauptunterschied zwischen dem Wiederherstellen und der Wiederherstellung eines inaktiven Postfachs?** Wenn Sie ein inaktives Postfach wiederherstellen, wird das Postfach in ein neues Postfach umgewandelt, wobei Inhalt und Ordnerstruktur des inaktiven Postfachs beibehalten werden und das Postfach mit einem neuen Benutzerkonto verknüpft wird. Nachdem er wiederhergestellt wurde, ist das inaktive Postfach nicht mehr vorhanden, und alle Änderungen, die an den Inhalten im neuen Postfach vorgenommen wurden, wirken sich auf den Inhalt aus, der im inaktiven Postfach ursprünglich gespeichert wurde. Wenn Sie umgekehrt ein inaktives Postfach wiederherstellen, wird der Inhalt lediglich in ein anderes Postfach kopiert. Das inaktive Postfach wird beibehalten und bleibt ein inaktives Postfach. Alle Änderungen, die an den Inhalten im Zielpostfach vorgenommen werden, wirken sich nicht auf den ursprünglichen Inhalt des inaktiven Postfachs aus. Das inaktive Postfach kann weiterhin mithilfe von In-Place eDiscovery durchsucht werden, dessen Inhalt kann in einem anderen Postfach wiederhergestellt werden, oder es kann zu einem späteren Zeitpunkt wiederhergestellt oder gelöscht werden.

- **Was geschieht, wenn Sie ein inaktives Postfach wiederherstellen?** Wenn Sie ein inaktives Postfach wiederherstellen, geschieht Folgendes:

  - Der auf ein inaktives Postfach angewendete Haltestatus wird basierend auf dem Aufbewahrungs, der vor der Wiederherstellung auf das inaktive Postfach angewendet wurde, geändert oder entfernt.

    - **Beweissicherungsverfahren.** Wenn das Beweissicherungsverfahren für das inaktive Postfach aktiviert wurde, wird es aus dem wiederhergestellten Postfach entfernt.

    - **In-situ-** Speicher In-Place Haltestatus werden aus dem wiederhergestellten Postfach entfernt. Dies bedeutet, dass das wiederhergestellte Postfach als Quellpostfach aus einer beliebigen In-Place halten oder In-Place eDiscovery-Suche entfernt wurde.

    - **Microsoft 365-Aufbewahrungsrichtlinie mit Erhaltungs Sperre.** Wenn das inaktive Postfach einer Aufbewahrungsrichtlinie mit Erhaltungs Sperre zugewiesen wurde (als *Gesperrte Aufbewahrungsrichtlinie* bezeichnet), wird das wiederhergestellte Postfach derselben gesperrten Aufbewahrungsrichtlinie zugewiesen. Weitere Informationen zu gesperrten Aufbewahrungsrichtlinien finden Sie unter Verwenden der Aufbewahrungs[Sperre, um Änderungen an Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungsrichtlinien einzuschränken](retention-preservation-lock.md).

    - **Microsoft 365-Aufbewahrungsrichtlinie ohne Aufbewahrungs Sperre.** Das inaktive Postfach wird aus einer entsperrten Microsoft 365-Aufbewahrungsrichtlinie entfernt, die auf ihn angewendet wurde. Das Beweissicherungsverfahren ist jedoch für das wiederhergestellte Postfach aktiviert, um das Löschen von Postfachinhalten basierend auf organisationsweiten Aufbewahrungsrichtlinien zu verhindern, die Inhalte löschen, die älter sind als ein bestimmtes Alter. Sie können das Beweissicherungsverfahren halten oder entfernen. Weitere Informationen finden Sie unter [Create a Litigation Hold](create-a-litigation-hold.md).

  - Der Zeitraum für die Wiederherstellung einzelner Elemente (der von der Postfacheigenschaft **RetainDeletedItemsFor** bestimmt wird) wird auf 30 Tage festgelegt. Wenn in Exchange Online ein neues Postfach erstellt wird, ist dieser Aufbewahrungszeitraum auf 14 Tage festgelegt. Durch Festlegen dieser Eigenschaft auf den Höchstwert von 30 Tagen bleibt Ihnen mehr Zeit zum Wiederherstellen von Daten, die (endgültig) aus dem inaktiven Postfach gelöscht wurden. Sie können die Wiederherstellung einzelner Elemente auch deaktivieren oder den Wiederherstellungszeitraum für einzelne Elemente wieder auf den Standardwert von 14 Tagen zurücksetzen. Weitere Informationen finden Sie unter [Enable or disable single item recovery for a mailbox](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery).

  - Die Aufbewahrungszeit ist aktiviert, und die Aufbewahrungsdauer ist auf 30 Tage festgelegt. Dies bedeutet, dass die standardmäßige Exchange-Aufbewahrungsrichtlinie und alle organisationsweiten oder Exchange-weiten Microsoft 365-Aufbewahrungsrichtlinien, die dem neuen Postfach zugewiesen sind, 30 Tage lang nicht verarbeitet werden. Dadurch erhält der zurückgebende Mitarbeiter oder der neue Besitzer des wiederhergestellten inaktiven Postfachs Zeit, um die alten Nachrichten zu verwalten. Andernfalls löscht die Aufbewahrungsrichtlinie für Exchange oder Microsoft 365 möglicherweise alte Postfachelemente (oder verschiebt Elemente in das Archivpostfach, sofern Sie aktiviert ist), die basierend auf den für die Exchange-oder Microsoft 365-Aufbewahrungsrichtlinien konfigurierten Einstellungen abgelaufen sind. Nach 30 Tagen läuft die Aufbewahrungsdauer ab, die **RetentionHoldEnabled** -Postfacheigenschaft ist auf **false** festgelegt, und der Assistent für verwaltete Ordner beginnt mit der Verarbeitung der dem Postfach zugewiesenen Richtlinien. Wenn Sie diese zusätzliche Zeit nicht benötigen, können Sie den Aufbewahrungsspeicher einfach entfernen. Alternativ können Sie die Aufbewahrungsdauer mithilfe des Befehls " **Sets-Mailbox-EndDateForRetentionHold** " verlängern. Weitere Informationen finden Sie unter [Place a mailbox on retention hold](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).

- **Halten Sie das wiederhergestellte Postfach ein, wenn Sie den ursprünglichen Status des inaktiven Postfachs beibehalten müssen.** Um zu verhindern, dass der neue Postfachbesitzer oder die Aufbewahrungsrichtlinie dauerhaft alle Nachrichten aus dem wiederhergestellten inaktiven Postfach löscht, können Sie das Postfach für das Beweissicherungsverfahren aufbewahren. Weitere Informationen finden Sie unter [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).

- **Welche Benutzer-ID kann für das Wiederherstellen eines inaktiven Postfachs verwendet werden?** Wenn Sie ein inaktives Postfach wiederherstellen, kann sich der Wert, den Sie für den  *MicrosoftOnlineServicesID*  -Parameter angeben, von dem Original, das dem inaktiven Postfach zugeordnet wurde, unterscheiden. Sie können auch die ursprüngliche Benutzer-ID verwenden. Aber wie bereits erwähnt, stellen Sie sicher, dass die für  *Name*  und  *MicrosoftOnlineServicesID*  verwendeten Werte innerhalb Ihrer Organisation eindeutig sind, wenn Sie das inaktive Postfach wiederherstellen.

- **Was geschieht, wenn die Aufbewahrungszeit für das inaktive Postfach nicht abgelaufen ist?** Wenn ein inaktives Postfach vor weniger als 30 Tagen vorläufig gelöscht wurde, kann es nicht mit dem Befehl **New-Mailbox -InactiveMailbox** wiederhergestellt werden. Sie müssen es wiederherstellen, indem Sie das entsprechende Benutzerkonto wiederherstellen. Weitere Informationen finden Sie unter [Löschen eines Benutzers aus Ihrer Organisation](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).

- **Woher weiß ich, ob der Aufbewahrungszeitraum für vorläufig gelöschte Postfächer für ein inaktives Postfach abgelaufen ist?** Führen Sie hierzu den folgenden Befehl aus.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | Format-List ExternalDirectoryObjectId
  ```

  Wenn die Eigenschaft **ExternalDirectoryObjectId** keinen Wert hat, ist die Aufbewahrungszeit abgelaufen, und Sie können das inaktive Postfach wiederherstellen, indem Sie den Befehl **New-Mailbox -InactiveMailbox** ausführen. Wenn ein Wert für die **ExternalDirectoryObjectId** -Eigenschaft vorhanden ist, ist der Aufbewahrungszeitraum für vorläufig gelöschte Postfächer nicht abgelaufen, und Sie müssen das Postfach wiederherstellen, indem Sie das Benutzerkonto wiederherstellen. Siehe [Löschen eines Benutzers aus Ihrer Organisation](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).

- **Erwägen Sie das Aktivieren des Archivpostfachs, nachdem Sie ein inaktives Postfach wiederhergestellt haben.** Auf diese Weise kann der zurückkehrende Benutzer oder neue Mitarbeiter alte Nachrichten in das Archivpostfach verschieben. Wenn das Anhalten der Aufbewahrungszeit abgelaufen ist, verschiebt die Archivrichtlinie, die Teil der Exchange Online-Postfächern zugewiesenen standardmäßigen Exchange-Aufbewahrungsrichtlinie ist, Elemente, die zwei Jahre oder älter sind, in das Archivpostfach. Wenn Sie das Archivpostfach nicht aktivieren, verbleiben Elemente, die älter als zwei Jahre sind, im primären Postfach des Benutzers. Weitere Informationen finden Sie unter [Aktivieren von archivpostfächern](enable-archive-mailboxes.md).
