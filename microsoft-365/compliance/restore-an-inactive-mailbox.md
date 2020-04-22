---
title: Rückspeichern eines inaktiven Postfachs
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: Wenn ein neuer Mitarbeiter oder ein anderer Benutzer Zugriff auf die Inhalte eines inaktiven Postfachs in Office 365 benötigt, können Sie den Inhalt des inaktiven Postfachs in einem vorhandenen Postfach wiederherstellen (oder zusammenführen).
ms.openlocfilehash: 3352dfa582fb09a5f0a6c7ecbd807ed80593351f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621317"
---
# <a name="restore-an-inactive-mailbox"></a>Rückspeichern eines inaktiven Postfachs

Ein inaktives Postfach (eine Art vorläufig gelöschtes Postfach) wird verwendet, um die E-Mails eines ehemaligen Mitarbeiters aufzubewahren, nachdem dieser die Organisation verlassen hat. Wenn ein anderer Mitarbeiter die Zuständigkeiten des ehemaligen Mitarbeiters übernimmt oder dieser Mitarbeiter in Ihre Organisation zurückkehrt, gibt es zwei Möglichkeiten, den Inhalt des inaktiven Postfachs wieder für einen Benutzer verfügbar zu machen:
  
- **Rückspeichern eines inaktiven Postfachs** Wenn ein anderer Mitarbeiter die Zuständigkeiten des ehemaligen Mitarbeiters übernimmt oder ein anderer Benutzer Zugriff auf die Inhalte des inaktiven Postfachs benötigt, können Sie den Inhalt des inaktiven Postfachs in ein vorhandenes Postfach rückspeichern (oder ihn mit diesem zusammenführen). Sie können auch das Archiv aus einem inaktiven Postfach rückspeichern. Nach dem Rückspeichern bleibt das inaktive Postfach als ein solches erhalten. In diesem Thema werden die Verfahren zum Rückspeichern eines inaktiven Postfachs beschrieben.

- **Wiederherstellen eines inaktiven Postfachs** Wenn der ehemalige Mitarbeiter in Ihre Organisation zurückkehrt oder ein neuer Mitarbeiter eingestellt wird, der die Zuständigkeiten des ehemaligen Mitarbeiters übernimmt, können Sie den Inhalt des inaktiven Postfachs wiederherstellen. Bei dieser Methode wird das inaktive Postfach in ein neues Postfach mit dem Inhalt des inaktiven Postfachs umgewandelt. Nach der Wiederherstellung ist das inaktive Postfach nicht mehr vorhanden. Schrittweise Anleitungen finden Sie unter [Wiederherstellen eines inaktiven Postfachs in Office 365](recover-an-inactive-mailbox.md).

Weitere Informationen zu den Unterschieden zwischen dem Wiederherstellen und der Wiederherstellung eines inaktiven Postfachs finden Sie im Abschnitt **Weitere Informationen** in diesem Artikel.
  
## <a name="before-you-begin"></a>Bevor Sie beginnen

- Zum Rückspeichern eines inaktiven Postfachs müssen Sie Exchange Online PowerShell verwenden. Das Exchange Admin Center (EAC) kann hierfür nicht verwendet werden. Eine Schritt-für-Schritt-Anleitung finden Sie unter [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).

- Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um Identitätsinformationen für die inaktiven Postfächer in Ihrer Organisation abzurufen.

    ```powershell
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     Verwenden Sie die von diesem Befehl zurückgegebenen Informationen zum Rückspeichern eines bestimmten inaktiven Postfachs.

- Weitere Informationen zu inaktiven Postfächern finden Sie unter [inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).

## <a name="restore-an-inactive-mailbox"></a>Rückspeichern eines inaktiven Postfachs

Verwenden Sie das Cmdlet **New-MailboxRestoreRequest** mit den Parametern  _SourceMailbox_ und  _TargetMailbox_, um den Inhalt eines inaktiven Postfachs in ein vorhandenes Postfach rückzuspeichern. Weitere Informationen zu diesem Cmdlet finden Sie unter [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).
  
1. Erstellen Sie eine Variable, die die Eigenschaften des inaktiven Postfachs enthält.

    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > Verwenden Sie im vorherigen Befehl den Wert der Eigenschaft **DistinguishedName** oder **ExchangeGUID** zum Identifizieren des inaktiven Postfachs. Diese Eigenschaften sind für jedes Postfach in Ihrer Organisation eindeutig, wobei ein aktives und ein inaktives Postfach die gleiche primäre SMTP-Adresse haben können.
  
2. Speichern Sie den Inhalt des inaktiven Postfachs in ein vorhandenes Postfach zurück. Die Inhalte des inaktiven Postfachs (Quellpostfachs) werden in den entsprechenden Ordnern im vorhandenen Postfach (Zielpostfach) zusammengeführt.

    ```powershell
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```

   Alternativ können Sie einen übergeordneten Ordner im Zielpostfach angeben, in den die Inhalte aus dem inaktiven Postfach rückgespeichert werden sollen. Wenn der angegebene Zielordner oder die angegebene Zielordnerstruktur nicht bereits im Zielpostfach vorhanden ist, wird es bzw. sie während des Rückspeichervorgangs erstellt. 

    Im folgenden Beispiel werden Postfachelemente und Unterordner aus einem inaktiven Postfach in die übergeordnete Ordnerstruktur des Zielpostfachs in einen Ordner namens "Inactive Mailbox" kopiert.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>Rückspeichern des Archivs aus einem inaktiven Postfach

Wenn ein inaktives Postfach ein Archivpostfach enthält, können Sie es auch im Archivpostfach eines vorhandenen Postfachs rückspeichern. Zum Rückspeichern des Archivs aus einem inaktiven Postfach müssen Sie die Schalter  _SourceIsArchive_ und  _TargetIsAchive_ dem Befehl hinzufügen, der zum Rückspeichern eines inaktiven Postfachs verwendet wird.
  
1. Erstellen Sie eine Variable, die die Eigenschaften des inaktiven Postfachs enthält.

    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!NOTE]
    > Verwenden Sie im vorherigen Befehl den Wert der Eigenschaft **DistinguishedName** oder **ExchangeGUID** zum Identifizieren des inaktiven Postfachs. Diese Eigenschaften sind für jedes Postfach in Ihrer Organisation eindeutig, wobei ein aktives und ein inaktives Postfach die gleiche primäre SMTP-Adresse haben können. 
  
2. Speichern Sie den Inhalt des Archivs aus dem inaktiven Postfach (Quellarchiv) in das Archiv eines vorhandenen Postfachs (Zielarchiv) zurück. Im folgenden Beispiel wird der Inhalt aus dem Quellarchiv in einen Ordner namens "Inactive Mailbox" im Archiv des Zielpostfachs kopiert.

    ```powershell
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

## <a name="more-information"></a>Weitere Informationen

- **Worin besteht der Hauptunterschied zwischen dem Wiederherstellen und der Wiederherstellung eines inaktiven Postfachs?** Wenn Sie ein inaktives Postfach wiederherstellen, wird das Postfach im Wesentlichen in ein neues Postfach konvertiert, die Inhalte und die Ordnerstruktur des inaktiven Postfachs werden beibehalten, und das Postfach ist mit einem neuen Benutzerkonto verknüpft. Nachdem er wiederhergestellt wurde, ist das inaktive Postfach nicht mehr vorhanden, und alle Änderungen, die an den Inhalten im neuen Postfach vorgenommen wurden, wirken sich auf den Inhalt aus, der im inaktiven Postfach ursprünglich gespeichert wurde. Wenn Sie umgekehrt ein inaktives Postfach wiederherstellen, wird der Inhalt lediglich in ein anderes Postfach kopiert. Das inaktive Postfach wird beibehalten und bleibt ein inaktives Postfach. Alle Änderungen, die an den Inhalten im Zielpostfach vorgenommen werden, wirken sich nicht auf den ursprünglichen Inhalt des inaktiven Postfachs aus. Das inaktive Postfach kann weiterhin mithilfe des [Inhalts Such Tools](content-search.md)durchsucht werden, dessen Inhalt kann in einem anderen Postfach wiederhergestellt werden, oder es kann zu einem späteren Zeitpunkt wiederhergestellt oder gelöscht werden.

- **Wie suchen Sie nach inaktiven Postfächern?** Zum Abrufen einer Liste der inaktiven Postfächer in Ihrer Organisation und Anzeigen von Informationen, die für das Rückspeichern eines inaktiven Postfachs nützlich sind, können Sie den folgenden Befehl ausführen.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **Verwenden Sie ein Beweissicherungsverfahren oder eine Microsoft 365-Aufbewahrungsrichtlinie, um inaktive Postfachinhalte beizubehalten.** Wenn Sie den Status eines inaktiven Postfachs nach der Wiederherstellung beibehalten möchten, können Sie das Zielpostfach in einem [Beweissicherungsverfahren](https://go.microsoft.com/fwlink/?linkid=856286) platzieren oder eine [Microsoft 365-Aufbewahrungsrichtlinie](retention-policies.md) anwenden, bevor Sie das inaktive Postfach wiederherstellen. Dies verhindert das dauerhafte Löschen von Elementen aus dem inaktiven Postfach, nachdem sie in das Zielpostfach rückgespeichert wurden.

- **Aktivieren Sie das Anhalten der Aufbewahrungszeit für das Zielpostfach, ehe Sie ein inaktives Postfach rückspeichern.** Das Postfachelemente in einem inaktiven Postfach alt sein können, sollten Sie das Aktivieren des Anhaltens der Aufbewahrungszeit für das Zielpostfach erwägen, bevor Sie ein inaktives Postfach rückspeichern. Wenn Sie für ein Postfach das Anhalten der Aufbewahrungszeit aktivieren, wird die zugewiesene Aufbewahrungsrichtlinie so lange nicht verarbeitet, bis das Anhalten der Aufbewahrungszeit aufgehoben wird oder der entsprechende Zeitraum abgelaufen ist. Dadurch erhält der Besitzer der Zielpostfachs Zeit zum Verwalten alter Nachrichten aus dem inaktiven Postfach. Andernfalls löscht die Aufbewahrungsrichtlinie möglicherweise alte Elemente (oder verschiebt Elemente in das Archivpostfach, sofern aktiviert), die basierend auf den für das Zielpostfach konfigurierten Aufbewahrungseinstellungen abgelaufen sind. Weitere Informationen finden Sie unter [platzieren eines Postfachs in der Aufbewahrungszeit in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).

- **Welche Funktion hat die Option „AllowLegacyDNMismatch"?** In den vorherigen Beispielen zum Rückspeichern eines inaktiven Postfachs wird die Option **AllowLegacyDNMismatch** verwendet, um das Rückspeichern des inaktiven Postfachs in ein anderes Zielpostfach zu erlauben. Ziel eines typischen Rückspeicherszenarios ist das Rückspeichern von Inhalten, bei denen das Quell- und Zielpostfach identisch sind. Standardmäßig prüft das Cmdlet **New-MailboxRestoreRequest** daher, ob der Wert der Eigenschaft **LegacyExchangeDN** für das Quell- und Zielpostfach identisch ist. Durch diese Prüfung wird vermieden, dass Sie versehentlich ein Quellpostfach im falschen Zielpostfach rückspeichern. Wenn Sie versuchen, ein inaktives Postfach ohne die Option **AllowLegacyDNMismatch** rückzuspeichern, kann es zu einem Fehler kommen, wenn das Quell- und Zielpostfach unterschiedliche Werte für die Eigenschaft **LegacyExchangeDN** aufweisen.

- **Sie können andere Parameter mit dem Cmdlet "New-MailboxRestoreRequest" verwenden, um verschiedene Rückspeicherszenarien für inaktive Postfächer zu implementieren.** Sie können beispielsweise den folgenden Befehl ausführen, um das Archiv aus dem inaktiven Postfach im primären Postfach des Zielpostfachs rückzuspeichern. 

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  Mit dem folgenden Befehl können auch das inaktive primäre Postfach im Archiv des Zielpostfachs rückspeichern.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **Welche Funktion hat der Parameter "TargetRootFolder"?** Wie bereits erläutert, können Sie den Parameter **TargetRootFolder** verwenden, um einen Ordner in der oberen Ebene der Ordnerstruktur (den Stammordner) im Zielpostfach anzugeben, in den der Inhalt des inaktiven Postfachs rückgespeichert werden soll. Wenn Sie diesen Parameter nicht verwenden, werden Postfachelemente aus dem inaktiven Postfach in den entsprechenden Standardordnern des Zielpostfachs zusammengeführt, und benutzerdefinierte Ordner werden im Stammverzeichnis des Zielpostfachs neu erstellt. Die folgenden Abbildungen veranschaulichen die Unterschiede zwischen Verwendung oder Nichtverwendung des Parameters **TargetRootFolder**.

    **Ordnerhierarchie im Zielpostfach, wenn der Parameter "TargetRootFolder" nicht verwendet wird**

    ![Screenshot: Der Parameter „TargetRootFolder' wird nicht verwendet.](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    **Ordnerhierarchie im Zielpostfach, wenn der Parameter "TargetRootFolder" verwendet wird**

    ![Screenshot: Der Parameter „TargetRootFolder' wird verwendet.](../media/300da592-7323-48db-b8a4-07012259d113.png)
