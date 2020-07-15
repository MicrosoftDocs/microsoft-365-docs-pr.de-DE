---
title: Rückspeichern eines inaktiven Postfachs
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
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: Hier erfahren Sie, wie Sie den Inhalt eines inaktiven Postfachs in einem vorhandenen Postfach in Office 365 wiederherstellen (oder zusammenführen).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34965832c32bfd4139f4b9a54d3999313aace476
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127452"
---
# <a name="restore-an-inactive-mailbox"></a>Rückspeichern eines inaktiven Postfachs

An inactive mailbox (which is a type of soft-deleted mailbox) is used to retain a former employee's email after he or she leaves your organization. If another employee takes on the job responsibilities of the departed employee or if that employee returns to your organization, there are two ways that you can make the contents of the inactive mailbox available to a user:
  
- **Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox. This topic describes the procedures for restoring an inactive mailbox.

- **Wiederherstellen eines inaktiven Postfachs** Wenn der ehemalige Mitarbeiter in Ihre Organisation zurückkehrt oder ein neuer Mitarbeiter eingestellt wird, der die Zuständigkeiten des ehemaligen Mitarbeiters übernimmt, können Sie den Inhalt des inaktiven Postfachs wiederherstellen. Bei dieser Methode wird das inaktive Postfach in ein neues Postfach mit dem Inhalt des inaktiven Postfachs umgewandelt. Nach der Wiederherstellung ist das inaktive Postfach nicht mehr vorhanden. Schrittweise Anleitungen finden Sie unter [Wiederherstellen eines inaktiven Postfachs in Office 365](recover-an-inactive-mailbox.md).

Weitere Informationen zu den Unterschieden zwischen dem Wiederherstellen und der Wiederherstellung eines inaktiven Postfachs finden Sie im Abschnitt **Weitere Informationen** in diesem Artikel.
  
## <a name="requirements-to-restore-an-inactive-mailbox"></a>Anforderungen zum Wiederherstellen eines inaktiven Postfachs

- Zum Rückspeichern eines inaktiven Postfachs müssen Sie Exchange Online PowerShell verwenden. Das Exchange Admin Center (EAC) kann hierfür nicht verwendet werden. Eine Schritt-für-Schritt-Anleitung finden Sie unter [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).

- Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um Identitätsinformationen für die inaktiven Postfächer in Ihrer Organisation abzurufen.

    ```powershell
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     Verwenden Sie die von diesem Befehl zurückgegebenen Informationen zum Rückspeichern eines bestimmten inaktiven Postfachs.

- Weitere Informationen zu inaktiven Postfächern finden Sie unter [inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).

## <a name="restore-an-inactive-mailbox"></a>Rückspeichern eines inaktiven Postfachs

Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox. For more information about using this cmdlet, see [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).
  
1. Erstellen Sie eine Variable, die die Eigenschaften des inaktiven Postfachs enthält.

    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.
  
2. Restore the contents of the inactive mailbox to an existing mailbox. The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).

    ```powershell
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```

   Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox. If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process. 

    Im folgenden Beispiel werden Postfachelemente und Unterordner aus einem inaktiven Postfach in die übergeordnete Ordnerstruktur des Zielpostfachs in einen Ordner namens "Inactive Mailbox" kopiert.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>Rückspeichern des Archivs aus einem inaktiven Postfach

If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox. To restore the archive from an inactive mailbox, you have to add the  _SourceIsArchive_ and  _TargetIsAchive_ switches to the command used to restore an inactive mailbox.
  
1. Erstellen Sie eine Variable, die die Eigenschaften des inaktiven Postfachs enthält.

    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!NOTE]
    > In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address. 
  
2. Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive). In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.

    ```powershell
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

## <a name="more-information"></a>Weitere Informationen

- **Worin besteht der Hauptunterschied zwischen dem Wiederherstellen und der Wiederherstellung eines inaktiven Postfachs?** Wenn Sie ein inaktives Postfach wiederherstellen, wird das Postfach im Wesentlichen in ein neues Postfach konvertiert, die Inhalte und die Ordnerstruktur des inaktiven Postfachs werden beibehalten, und das Postfach ist mit einem neuen Benutzerkonto verknüpft. Nachdem er wiederhergestellt wurde, ist das inaktive Postfach nicht mehr vorhanden, und alle Änderungen, die an den Inhalten im neuen Postfach vorgenommen wurden, wirken sich auf den Inhalt aus, der im inaktiven Postfach ursprünglich gespeichert wurde. Wenn Sie umgekehrt ein inaktives Postfach wiederherstellen, wird der Inhalt lediglich in ein anderes Postfach kopiert. Das inaktive Postfach wird beibehalten und bleibt ein inaktives Postfach. Alle Änderungen, die an den Inhalten im Zielpostfach vorgenommen werden, wirken sich nicht auf den ursprünglichen Inhalt des inaktiven Postfachs aus. Das inaktive Postfach kann weiterhin mithilfe des [Inhalts Such Tools](content-search.md)durchsucht werden, dessen Inhalt kann in einem anderen Postfach wiederhergestellt werden, oder es kann zu einem späteren Zeitpunkt wiederhergestellt oder gelöscht werden.

- **How do you find inactive mailboxes?** To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **Verwenden Sie ein Beweissicherungsverfahren oder eine Microsoft 365-Aufbewahrungsrichtlinie, um inaktive Postfachinhalte beizubehalten.** Wenn Sie den Status eines inaktiven Postfachs nach der Wiederherstellung beibehalten möchten, können Sie das Zielpostfach in einem [Beweissicherungsverfahren](https://go.microsoft.com/fwlink/?linkid=856286) platzieren oder eine [Microsoft 365-Aufbewahrungsrichtlinie](retention.md) anwenden, bevor Sie das inaktive Postfach wiederherstellen. Dies verhindert das dauerhafte Löschen von Elementen aus dem inaktiven Postfach, nachdem sie in das Zielpostfach rückgespeichert wurden.

- **Aktivieren Sie das Anhalten der Aufbewahrungszeit für das Zielpostfach, ehe Sie ein inaktives Postfach rückspeichern.** Das Postfachelemente in einem inaktiven Postfach alt sein können, sollten Sie das Aktivieren des Anhaltens der Aufbewahrungszeit für das Zielpostfach erwägen, bevor Sie ein inaktives Postfach rückspeichern. Wenn Sie für ein Postfach das Anhalten der Aufbewahrungszeit aktivieren, wird die zugewiesene Aufbewahrungsrichtlinie so lange nicht verarbeitet, bis das Anhalten der Aufbewahrungszeit aufgehoben wird oder der entsprechende Zeitraum abgelaufen ist. Dadurch erhält der Besitzer der Zielpostfachs Zeit zum Verwalten alter Nachrichten aus dem inaktiven Postfach. Andernfalls löscht die Aufbewahrungsrichtlinie möglicherweise alte Elemente (oder verschiebt Elemente in das Archivpostfach, sofern aktiviert), die basierend auf den für das Zielpostfach konfigurierten Aufbewahrungseinstellungen abgelaufen sind. Weitere Informationen finden Sie unter [platzieren eines Postfachs in der Aufbewahrungszeit in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).

- **What does the AllowLegacyDNMismatch switch do?** In the previous examples to restore an inactive mailbox, the **AllowLegacyDNMismatch** switch is used to allow restoring the inactive mailbox to a different target mailbox. In a typical restore scenario, the goal is to restore content where the source and target mailboxes are the same mailbox. So by default, the **New-MailboxRestoreRequest** cmdlet checks to make sure that the value of the **LegacyExchangeDN** property on the source and target mailboxes is the same. This helps prevents you from accidentally restoring a source mailbox into the wrong target mailbox. If you try to restore an inactive mailbox without using the **AllowLegacyDNMismatch** switch, the command might fail if the source and target mailboxes have different values for the **LegacyExchangeDN** property.

- **You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.** For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox. 

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  Mit dem folgenden Befehl können auch das inaktive primäre Postfach im Archiv des Zielpostfachs rückspeichern.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **What does the TargetRootFolder parameter do?** As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox. If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox. The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.

    **Ordnerhierarchie im Zielpostfach, wenn der Parameter "TargetRootFolder" nicht verwendet wird**

    ![Screenshot: Der Parameter „TargetRootFolder' wird nicht verwendet.](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    **Ordnerhierarchie im Zielpostfach, wenn der Parameter "TargetRootFolder" verwendet wird**

    ![Screenshot: Der Parameter „TargetRootFolder' wird verwendet.](../media/300da592-7323-48db-b8a4-07012259d113.png)
