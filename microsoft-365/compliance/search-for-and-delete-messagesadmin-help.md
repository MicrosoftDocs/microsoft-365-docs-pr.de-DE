---
title: Suchen nach und Löschen von Nachrichten – Administratorhilfe
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: Mithilfe des Cmdlets Search-Mailbox können Administratoren Benutzerpostfächer durchsuchen und anschließend Nachrichten aus Postfächern löschen.
ms.openlocfilehash: b3505026034fabcc6d509e7a187fafc5691ef9e7
ms.sourcegitcommit: ca06ee52dec472d3827983d67b049847ec2fdfc1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2020
ms.locfileid: "41256675"
---
# <a name="search-for-and-delete-messages---admin-help"></a>Suchen nach und Löschen von Nachrichten – Administratorhilfe
  
Mithilfe des Cmdlets **Search-Mailbox** können Administratoren Benutzerpostfächer durchsuchen und anschließend Nachrichten aus Postfächern löschen. 
  
Um Nachrichten in einem Schritt zu suchen und zu löschen, führen Sie das Cmdlet **Search-Mailbox** mit der Option  _DeleteContent_ aus. Dabei können Sie jedoch keine Suchergebnisse in einer Vorschau anzeigen und kein Protokoll der von der Suche zurückgegebenen Nachrichten generieren. Außerdem löschen Sie ggf. versehentlich Nachrichten, die Sie gar nicht löschen wollten. Um ein Protokoll der von der Suche gefundenen Nachrichten in der Vorschau anzuzeigen, bevor sie gelöscht werden, führen Sie das Cmdlet **Search-Mailbox** mit der Option  _LogOnly_ aus. 
  
Als zusätzliche Schutzmaßnahme können Sie die Nachrichten zuerst in ein anderes Postfach kopieren; dazu verwenden Sie die Parameter  _TargetMailbox_ und  _TargetFolder_. So behalten Sie eine Kopie der gelöschten Nachrichten für den Fall, dass Sie wieder auf sie zugreifen müssen. 
  
## <a name="before-you-begin"></a>Bevor Sie beginnen

- Geschätzte Zeit bis zum Abschließen des Vorgangs: 10 Minuten. Die tatsächliche Zeit kann von der Größe des Postfachs und der Suchabfrage abhängen.
    
- Diese Verfahren können nicht in der Exchange-Verwaltungskonsole ausgeführt werden. Sie müssen die Shell verwenden.
    
- Ihnen müssen die beiden folgenden Verwaltungsrollen zugewiesen sein, damit Sie in den Benutzerpostfächern nach Nachrichten suchen und Nachrichten löschen können:
    
  - **Postfachsuche**– mit dieser Rolle können Sie Nachrichten in mehreren Postfächern in Ihrer Organisation suchen. Administratoren wird diese Rolle nicht standardmäßig zugewiesen. Wenn Sie sich diese Rolle selbst zuweisen möchten, damit Sie Postfächer durchsuchen können, fügen Sie sich als Mitglied der Rollengruppe "Discoveryverwaltung" hinzu. Weitere Informationen finden Sie unter [Add a User to the Discovery Management Role Group](https://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).
    
  - **Post Fach Import Export** – mit dieser Rolle können Sie Nachrichten aus dem Postfach eines Benutzers löschen. Diese Rolle ist standardmäßig keiner Rollengruppe zugewiesen. Um Nachrichten aus Benutzerpostfächern zu löschen, können Sie der Rollengruppe "Organisationsverwaltung" die Rolle "Postfachimport/-export" hinzufügen. Weitere Informationen finden Sie im Abschnitt "Hinzufügen einer Rolle zu einer Rollengruppe" unter [Manage Role](https://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) Groups. 
    
- Wenn für das Postfach, aus dem Sie Nachrichten löschen möchten, die Wiederherstellung einzelner Elemente aktiviert ist, müssen Sie diese Funktion zuerst deaktivieren. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der Wiederherstellung einzelner Elemente für ein Postfach](https://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).
    
- Wenn für das Postfach, aus dem Sie Nachrichten löschen möchten, die Aufbewahrung für eventuelle Rechtsstreitigkeiten festgelegt wurde, sollten Sie bei der Datensatzverwaltungs- oder Rechtsabteilung nachfragen, bevor Sie die entsprechende Sperre aufheben und den Postfachinhalt löschen. Nachdem Sie die Genehmigung erhalten haben, führen Sie die im Thema [Bereinigen des Ordners "Wiederherstellbare Elemente"](https://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx)aufgeführten Schritte aus.
    
- Mithilfe des Cmdlets **Search-Mailbox** können maximal 10.000 Postfächer durchsucht werden. Wenn Sie eine Exchange Online-Organisation mit mehr als 10.000 Postfächern haben, können Sie die Funktion „Compliancesuche" (oder das entsprechende Cmdlet **New-ComplianceSearch** ) verwenden, um eine unbegrenzte Anzahl von Postfächern zu durchsuchen. Anschließend können Sie mit dem Cmdlet **New-ComplianceSearchAction** die Nachrichten löschen, die von der Compliancesuche zurückgegeben wurden. Weitere Informationen finden Sie unter [Suchen und Löschen von E-Mail-Nachrichten in Ihrer Office 365-Organisation - Administratorhilfe](https://go.microsoft.com/fwlink/p/?LinkId=786856).
    
- Wenn Sie eine Suchabfrage (durch Verwendung des Parameters  *SearchQuery*  ) einschließen, gibt das Cmdlet **Search-Mailbox** maximal 10.000 Elemente in den Suchergebnissen zurück. Wenn Sie also eine Suchabfrage einschließen, müssen Sie den Befehl **Search-Mailbox** möglicherweise mehrere Male ausführen, um mehr als 10.000 Elemente zu löschen. 
    
- Wenn Sie das Cmdlet **Search-Mailbox** ausführen, wird auch das Archivpostfach des Benutzers durchsucht. In ähnlicher Weise werden Elemente im primären Archivpostfach gelöscht, wenn Sie das Cmdlet **Search-Mailbox** mit der Option  _DeleteContent_ verwenden. Um dies zu verhindern, können Sie die Option  *DoNotIncludeArchive*  einschließen.
    
## <a name="search-messages-and-log-the-search-results"></a>Suchen von Nachrichten und Protokollieren der Suchergebnisse

In diesem Beispiel wird das Postfach von April Stewart nach Nachrichten mit dem Satz "Your bank statement" im Betrefffeld durchsucht. Die Suchergebnisse werden im Postfach des Administrators im Ordner "SearchAndDeleteLog" protokolliert. Nachrichten werden nicht in das Zielpostfach kopiert und nicht aus diesem gelöscht.
  
```powershell
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

In diesem Beispiel werden alle Postfächer in der Organisation nach Nachrichten durchsucht, an die ein beliebiger Typ von Datei mit dem Namen "Trojan" angefügt ist. Anschließend wird eine Protokollnachricht an das Administratorpostfach gesendet.
  
```powershell
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Search-Mailbox](https://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).
  
 
## <a name="search-and-delete-messages"></a>Suchen und Löschen von Nachrichten

In diesem Beispiel wird das Postfach von April Stewart nach Nachrichten mit dem Satz "Your bank statement" im Betrefffeld durchsucht. Die Nachrichten werden aus dem Quellpostfach gelöscht, ohne dass die Suchergebnisse in einen anderen Ordner kopiert werden. Wie bereits erklärt muss Ihnen die Verwaltungsrolle "Postfachimport/-export" zugewiesen sein, damit Sie Nachrichten aus einem Benutzerpostfach löschen können.
  
> [!IMPORTANT]
> Wenn Sie das Cmdlet **Search-Mailbox** mit der Option  _DeleteContent_ verwenden, werden Nachrichten dauerhaft aus dem Quellpostfach gelöscht. Bevor Sie Nachrichten dauerhaft löschen, sollten Sie mit der Option  _LogOnly_ ein Protokoll der von der Suche gefundenen Nachrichten generieren, bevor sie gelöscht werden, oder die Nachrichten in ein anderes Postfach kopieren, bevor Sie sie aus dem Quellpostfach löschen. 
  
```powershell
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

In diesem Beispiel wird das Postfach von April Stewart nach Nachrichten mit dem Satz "Your bank statement" im Betrefffeld durchsucht. Die Suchergebnisse werden in den Ordner "AprilStewart-DeletedMessages" im Postfach "BackupMailbox" kopiert und aus dem Postfach von April Stewart gelöscht.
  
```powershell
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

In diesem Beispiel werden alle Postfächer in der Organisation nach Nachrichten mit der Betreffzeile "Laden Sie diese Datei herunter" durchsucht und dauerhaft gelöscht. 
  
```powershell
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Search-Mailbox](https://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).

## <a name="using-the--loglevel-full-parameter"></a>Verwenden des Parameters -LogLevel Full

In einigen der Beispiele oben wurde der Parameter  _LogLevel_ mit dem Wert  `Full` verwendet, um detaillierte Informationen zu den vom Cmdlet **Search-Mailbox** zurückgegebenen Ergebnissen zu protokollieren. Wenn Sie diesen Parameter verwendet haben, wird eine E-Mail-Nachricht erstellt und an das im Parameter  _TargetMailbox_ angegebene Postfach gesendet. Die Protokolldatei (eine CSV-formatierte Datei mit dem Namen „Results.csv") ist dieser E-Mail-Nachricht angefügt und wird in dem Ordner abgelegt, der im Parameter  _TargetFolder_ angegeben ist. Die Protokolldatei enthält eine Zeile für jede Nachricht, die in den vom Cmdlet **Search-Mailbox** zurückgegebenen Suchergebnissen aufgeführt ist. 
