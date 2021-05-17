---
title: Erhöhen des Kontingents für wiederherstellbare Elemente für aufzubewahrende Postfächer
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
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: Aktivieren Sie das Archivpostfach, und aktivieren Sie die automatisch erweiterte Archivierung, um die Größe des Ordners "Wiederherstellbare Elemente" für ein Postfach in Microsoft 365.
ms.openlocfilehash: 7b4ee808bc3004438c9eb7424a89c01567fc04d9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911273"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>Erhöhen des Kontingents für wiederherstellbare Elemente für aufzubewahrende Postfächer

Die standard Exchange Aufbewahrungsrichtlinie mit dem Namen *Standard-MRM-Richtlinie,* die automatisch auf neue Postfächer in Exchange Online angewendet wird, enthält ein Aufbewahrungstag mit dem Namen Wiederherstellbare Elemente, die 14 Tage in das Archiv verschoben werden. Mit diesem Aufbewahrungstag werden Elemente aus dem Ordner "Wiederherstellbare Elemente" im primären Postfach des Benutzers in den Ordner "Wiederherstellbare Elemente" im Archivpostfach des Benutzers verschoben, nachdem der 14-tägige Aufbewahrungszeitraum für ein Element abgelaufen ist. Damit dies geschieht, muss das Archivpostfach des Benutzers aktiviert sein. Wenn das Archivpostfach nicht aktiviert ist, wird keine Aktion ergriffen, was bedeutet, dass Elemente im Ordner "Wiederherstellbare Elemente" für ein archivierbares Postfach nach Ablauf des 14-tägigen Aufbewahrungszeitraums nicht in das Archivpostfach verschoben werden. Da aus einem Archivpostfach nichts gelöscht wird, ist es möglich, dass das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" überschritten wird, insbesondere wenn das Archivpostfach des Benutzers nicht aktiviert ist. 
  
Um die Wahrscheinlichkeit zu verringern, dass dieser Grenzwert überschritten wird, wird das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" automatisch von 30 GB auf 100 GB erhöht, wenn ein Speicher für ein Postfach in einem Postfach in Exchange Online. Wenn das Archivpostfach aktiviert ist, wird das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" im Archivpostfach ebenfalls von 30 GB auf 100 GB erhöht. Wenn das Archivierungsfeature für die automatische Erweiterung in Exchange Online aktiviert ist, ist das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" im Archiv des Benutzers unbegrenzt.
  
 In der folgenden Tabelle wird das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" zusammengefasst. 
  
|**Speicherort des Ordners "Wiederherstellbare Elemente"**|**Postfächer, die nicht in der Warteschleife sind**|**In der Warteschleife gespeicherte Postfächer**|
|:-----|:-----|:-----|
|Primäres Postfach  <br/> |30 GB  <br/> |100 GB  <br/> |
|Archivpostfach<sup>\*</sup> <br/> |Unbegrenzt  <br/> |Unbegrenzt  <br/> |
|**Gesamtspeicherkontingent für den Ordner "Wiederherstellbare Elemente"** <br/> |Unbegrenzt  <br/> |Unbegrenzt  <br/> |
   
> [!NOTE]
> <sup>\*</sup>Das anfängliche Speicherkontingent für das Archivpostfach beträgt 100 GB für Benutzer mit Exchange Online (Plan 2) Lizenz. Wenn die automatische Erweiterung der Archivierung für postfächer aktiviert ist, wird das Speicherkontingent sowohl für das Archivpostfach als auch für den Ordner "Wiederherstellbare Elemente" auf 110 GB erhöht. Bei Bedarf wird zusätzlicher Archivspeicherplatz bereitgestellt, was zu einer unbegrenzten Menge an Archivspeicher führt. Weitere Informationen zum automatischen Erweitern der Archivierung finden Sie [unter Overview of unlimited archiving in Office 365](unlimited-archiving.md). 
  
Wenn das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" im primären Postfach eines postfachaktiven Postfachs kurz vor dem Erreichen seines Grenzwerts liegt, können Sie die folgenden Schritte tun:
  
- **Aktivieren Sie das Archivpostfach, und aktivieren Sie die automatische Erweiterung der Archivierung.** Sie können eine unbegrenzte Speicherkapazität für den Ordner "Wiederherstellbare Elemente" aktivieren, indem Sie einfach das Archivpostfach aktivieren und dann das Archivierungsfeature für automatisches Erweitern in Exchange Online. Dies führt zu 110 GB für den Ordner "Wiederherstellbare Elemente" im primären Postfach und einer unbegrenzten Speicherkapazität für den Ordner "Wiederherstellbare Elemente" im Archiv des Benutzers. Erfahren Sie, wie: Aktivieren von [Archivpostfächern im Security & Compliance Center](enable-archive-mailboxes.md) und Aktivieren der [unbegrenzten Archivierung in Office 365](enable-unlimited-archiving.md).
    
    > [!NOTE]
    > Nachdem Sie das Archiv für ein Postfach aktiviert haben, das das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" fast überschreitet, können Sie den Assistenten für verwaltete Ordner ausführen, um den Assistenten manuell zum Verarbeiten des Postfachs auszulösen, sodass abgelaufene Elemente in den Ordner "Wiederherstellbare Elemente" im Archivpostfach verschoben werden. Anweisungen [finden Sie unter Schritt 4.](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) Beachten Sie, dass andere Elemente im Postfach des Benutzers möglicherweise in das neue Archivpostfach verschoben werden. Erwägen Sie, dem Benutzer mitzuteilen, dass dies nach dem Aktivieren des Archivpostfachs passieren kann. 
  
- **Erstellen Sie eine benutzerdefinierte Exchange Aufbewahrungsrichtlinie für Postfächer im Archiv.** Zusätzlich zum Aktivieren des Archivpostfachs und der automatischen Erweiterung der Archivierung für Postfächer im Prozesssicherungsverfahren oder im In-Place-Archiv sollten Sie auch eine benutzerdefinierte Exchange-Aufbewahrungsrichtlinie für Postfächer im Halteverfahren erstellen. Auf diese Weise können Sie eine Aufbewahrungsrichtlinie auf Postfächer anwenden, die sich von der Standardmäßigen MRM-Richtlinie unterscheiden, die auf Postfächer angewendet wird, die sich nicht im Halteraum befinden, und sie können Aufbewahrungstags anwenden, die für Postfächer im Archiv entwickelt wurden. Dazu gehört das Erstellen eines neuen Aufbewahrungstags für den Ordner "Wiederherstellbare Elemente". 
    
Im restlichen Teil dieses Themas werden die schrittweisen Verfahren zum Erstellen einer benutzerdefinierten Aufbewahrungsrichtlinie Exchange Aufbewahrungsrichtlinie für Postfächer im Archiv beschrieben.
  
[Schritt 1: Erstellen eines benutzerdefinierten Aufbewahrungstags für den Ordner "Wiederherstellbare Elemente"](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[Schritt 2: Erstellen einer neuen Aufbewahrungsrichtlinie Exchange aufbewahrungsaktiven Postfächern](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[Schritt 3: Anwenden der neuen Aufbewahrungsrichtlinie Exchange Aufbewahrungsrichtlinie auf Postfächer, die sich im Archiv begnaufen](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[(Optional) Schritt 4: Ausführen des Assistenten für verwaltete Ordner zum Anwenden der neuen Aufbewahrungseinstellungen](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>Schritt 1: Erstellen eines benutzerdefinierten Aufbewahrungstags für den Ordner "Wiederherstellbare Elemente"

Der erste Schritt besteht darin, ein benutzerdefiniertes Aufbewahrungstag (als Aufbewahrungsrichtlinientag oder RPT bezeichnet) für den Ordner "Wiederherstellbare Elemente" zu erstellen. Wie bereits erläutert, verschiebt dieses RPT Elemente aus dem Ordner "Wiederherstellbare Elemente" im primären Postfach des Benutzers in den Ordner "Wiederherstellbare Elemente" im Archivpostfach des Benutzers. Sie müssen PowerShell verwenden, um ein RPT für den Ordner "Wiederherstellbare Elemente" zu erstellen. Sie können nicht die Exchange-Verwaltungskonsole (EAC) verwenden. 
  
1. [Stellen Sie eine Verbindung mit Exchange Online mithilfe der Remote-PowerShell her](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. Führen Sie den folgenden Befehl aus, um ein neues RPT für den Ordner "Wiederherstellbare Elemente" zu erstellen: 
    
    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    Mit dem folgenden Befehl wird beispielsweise ein RPT für den Ordner "Wiederherstellbare Elemente" mit dem Namen "Wiederherstellbare Elemente 30 Tage für Postfächer im Archiv" mit einem Aufbewahrungszeitraum von 30 Tagen erstellt. Dies bedeutet, dass ein Element, nachdem es sich 30 Tage lang im Ordner "Wiederherstellbare Elemente" befindet, in den Ordner "Wiederherstellbare Elemente" im Archivpostfach des Benutzers verschoben wird.
    
    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > Es wird empfohlen, dass der Aufbewahrungszeitraum (definiert durch den  _Parameter AgeLimitForRetention)_ für das RpT für wiederherstellbare Elemente mit dem Aufbewahrungszeitraum für gelöschte Elemente für die Postfächer identisch ist, auf die das RPT angewendet wird. Dadurch kann ein Benutzer den gesamten Aufbewahrungszeitraum für gelöschte Elemente wiederherstellen, bevor er in das Archivpostfach verschoben wird. Im vorherigen Beispiel wurde der Aufbewahrungszeitraum auf 30 Tage festgelegt, basierend auf der Annahme, dass der Aufbewahrungszeitraum für gelöschte Elemente für Postfächer ebenfalls 30 Tage beträgt. Ein Exchange Online ist standardmäßig so konfiguriert, dass gelöschte Elemente für 14 Tage beibehalten werden. Sie können diese Einstellung jedoch auf maximal 30 Tage ändern. Weitere Informationen finden Sie [unter Change the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go). 
  
## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a>Schritt 2: Erstellen einer neuen Aufbewahrungsrichtlinie Exchange aufbewahrungsaktiven Postfächern

Der nächste Schritt besteht darin, eine neue Aufbewahrungsrichtlinie zu erstellen und aufbewahrungstags hinzuzufügen, einschließlich des RPT für wiederherstellbare Elemente, das Sie in Schritt 1 erstellt haben. Diese neue Richtlinie wird im nächsten Schritt auf Postfächer angewendet, die im Archiv gespeichert sind. 
  
Bestimmen Sie vor dem Erstellen der neuen Aufbewahrungsrichtlinie die zusätzlichen Aufbewahrungstags, die Sie hinzufügen möchten. Eine Liste der Aufbewahrungstags, die der Standard-MRM-Richtlinie hinzugefügt werden, sowie Informationen zum Erstellen neuer Aufbewahrungstags finden Sie im Folgenden:
  
- [Standardaufbewahrungsrichtlinie in Exchange Online ](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)
    
- [Standardordner, die Aufbewahrungsrichtlinientags unterstützen](/exchange/security-and-compliance/messaging-records-management/default-folders)
    
- Der Abschnitt "Erstellen eines Aufbewahrungstags" im [Thema Erstellen einer Aufbewahrungsrichtlinie.](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy)
    
Sie können die EAC oder Exchange Online PowerShell verwenden, um eine Aufbewahrungsrichtlinie zu erstellen.
  
### <a name="use-the-eac-to-create-a-retention-policy"></a>Erstellen einer Aufbewahrungsrichtlinie mithilfe der Exchange-Verwaltungskonsole
  
1. Wechseln Sie in der EAC zu Aufbewahrungsrichtlinien für **die** Complianceverwaltung, und klicken Sie \> dann **auf Hinzufügen** ![ -Symbol ](../media/ITPro-EAC-AddIcon.gif) .
    
2. Geben Sie **auf der Seite** Neue Aufbewahrungsrichtlinie unter **Name** einen Namen ein, der den Zweck der Aufbewahrungsrichtlinie beschreibt. Beispiel: **MRM Policy for Mailboxes on Hold**. 
    
3. Klicken **Sie unter Aufbewahrungstags** auf **Add** Add ![ Icon ](../media/ITPro-EAC-AddIcon.gif) .
    
4. Wählen Sie in der Liste der Aufbewahrungstags das RPT für wiederherstellbare Elemente aus, das Sie in Schritt 1 erstellt haben, und klicken Sie dann auf **Hinzufügen**.
    
    ![Auswählen des benutzerdefinierten Aufbewahrungstags für wiederherstellbare Elemente](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. Wählen Sie zusätzliche Aufbewahrungstags aus, die der Aufbewahrungsrichtlinie hinzugefügt werden. Sie können beispielsweise die gleichen Tags hinzufügen, die in der Standard-MRM-Richtlinie enthalten sind.
    
6. Wenn Sie mit dem Hinzufügen von Aufbewahrungstags fertig sind, klicken Sie auf **OK**.
    
7. Klicken **Sie auf Speichern,** um die neue Aufbewahrungsrichtlinie zu erstellen. 
    
    Beachten Sie, dass die mit der Aufbewahrungsrichtlinie verknüpften Aufbewahrungstags im Detailbereich angezeigt werden.
    
    ![Aufbewahrungstags, die mit der Aufbewahrungsrichtlinie verknüpft sind, werden im Detailbereich angezeigt.](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>Verwenden Exchange Online PowerShell zum Erstellen einer Aufbewahrungsrichtlinie
  
Führen Sie den folgenden Befehl aus, um eine neue Aufbewahrungsrichtlinie für Postfächer im Archiv zu erstellen. 
  
```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

Der folgende Befehl erstellt beispielsweise die Aufbewahrungsrichtlinie und verknüpfte Aufbewahrungstags, die in der vorherigen Abbildung angezeigt werden.
  
```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a>Schritt 3: Anwenden der neuen Aufbewahrungsrichtlinie Exchange Aufbewahrungsrichtlinie auf Postfächer, die sich im Archiv begnaufen

Der letzte Schritt besteht in der Anwendung der neuen Aufbewahrungsrichtlinie, die Sie in Schritt 2 erstellt haben, auf Postfächer, die in Ihrer Organisation gespeichert sind. Sie können die EAC oder Exchange Online PowerShell verwenden, um die Aufbewahrungsrichtlinie auf ein einzelnes Postfach oder auf mehrere Postfächer anzuwenden. 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>Anwenden der neuen Aufbewahrungsrichtlinie mithilfe der EAC
  
1. Wechseln Sie zu **Empfänger**  >  **Postfächer**.
    
2. Wählen Sie in der Listenansicht das Postfach aus, auf das Sie die Aufbewahrungsrichtlinie anwenden möchten, und klicken Sie dann auf **Bearbeiten** ![ (Symbol). ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)
    
3. Klicken Sie **auf der Seite Benutzerpostfach** auf **Postfachfeatures**.
    
4. Wählen **Sie unter** Aufbewahrungsrichtlinie die Aufbewahrungsrichtlinie aus, die Sie in Schritt 2 erstellt haben, und klicken Sie dann auf **Speichern**.
    
Sie können auch die EAC verwenden, um die Aufbewahrungsrichtlinie auf mehrere Postfächer anzuwenden.
  
1. Wechseln Sie zu **Empfänger**  >  **Postfächer**.
    
2. Verwenden Sie in der Listenansicht die UMSCHALT- oder die STRG-TASTE, um mehrere Postfächer auszuwählen.
    
3. Klicken Sie im Detailbereich auf **Weitere Optionen**.
    
4. Klicken Sie unter **Aufbewahrungsrichtlinie** auf **Aktualisieren**.
    
5. Wählen Sie auf der **Seite Aufbewahrungsrichtlinie** massen zuweisen die Aufbewahrungsrichtlinie aus, die Sie in Schritt 2 erstellt haben, und klicken Sie dann auf **Speichern**. 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>Verwenden Exchange Online PowerShell zum Anwenden der neuen Aufbewahrungsrichtlinie
  
Sie können powerShell Exchange Online verwenden, um eine neue Aufbewahrungsrichtlinie auf ein einzelnes Postfach anzuwenden. Die eigentliche Stärke von PowerShell besteht jedoch in der schnellen Identifizierung aller Postfächer in Ihrer Organisation, die sich entweder im Prozesssicherungsverfahren oder im In-Place-Archiv befinden, und dann die neue Aufbewahrungsrichtlinie auf alle Postfächer anwenden können, die in einem einzigen Befehl gespeichert sind. Hier sind einige Beispiele für die Verwendung Exchange PowerShell zum Anwenden einer Aufbewahrungsrichtlinie auf mindestens ein Postfach. In allen Beispielen wird die in Schritt 2 erstellte Aufbewahrungsrichtlinie angewendet.
  
In diesem Beispiel wird die neue Aufbewahrungsrichtlinie auf das Postfach von Pilar Pinilla angewendet.
  
```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

In diesem Beispiel wird die neue Aufbewahrungsrichtlinie auf alle Postfächer in der Organisation angewendet, die sich im Prozessaufbewahrungsverfahren befinden.
  
```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

In diesem Beispiel wird die neue Aufbewahrungsrichtlinie auf alle Postfächer in der Organisation angewendet, die sich In-Place befinden.
  
```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

Mit dem **Cmdlet Get-Mailbox** können Sie überprüfen, ob die neue Aufbewahrungsrichtlinie angewendet wurde. 
  
Im Folgenden finden Sie einige Beispiele, um zu überprüfen, ob die Befehle in den vorherigen Beispielen die Aufbewahrungsrichtlinie "MRM Policy for Mailboxes on Hold" auf Postfächer im Prozesssicherungsverfahren und Postfächer im In-Place angewendet haben.
  
```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a>(Optional) Schritt 4: Ausführen des Assistenten für verwaltete Ordner zum Anwenden der neuen Aufbewahrungseinstellungen

Nachdem Sie die neue aufbewahrungsrichtlinie Exchange auf postfächer angewendet haben, kann es bis zu 7 Tage in Exchange Online dauern, bis der Assistent für verwaltete Ordner diese Postfächer mithilfe der Einstellungen in der neuen Aufbewahrungsrichtlinie verarbeiten kann. Anstatt auf die Ausführung des Assistenten für verwaltete Ordner zu warten, können Sie das **Cmdlet Start-ManagedFolderAssistant** verwenden, um den Assistenten manuell auszulösen, um die Postfächer zu verarbeiten, auf die Sie die neue Aufbewahrungsrichtlinie angewendet haben. 
  
Führen Sie den folgenden Befehl aus, um den Assistenten für verwaltete Ordner für das Postfach von Pilar Pinilla zu starten.
  
```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

Führen Sie die folgenden Befehle aus, um den Assistenten für verwaltete Ordner für alle postfächer im Halteraum zu starten.
  
```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>Weitere Informationen

- Nachdem Sie das Archivpostfach eines Benutzers aktiviert haben, sollten Sie dem Benutzer sagen, dass andere Elemente in seinem Postfach (nicht nur Elemente im Ordner "Wiederherstellbare Elemente") möglicherweise in das Archivpostfach verschoben werden. Dies liegt daran, dass die standardmäßige MRM-Richtlinie, die Exchange Online Postfächern zugewiesen ist, ein Aufbewahrungstag enthält (mit dem Namen Standard 2 Jahre in Archiv verschieben), das Elemente zwei Jahre nach dem Datum, an dem das Element an das Postfach zugestellt oder vom Benutzer erstellt wurde, in das Archivpostfach verschiebt. Weitere Informationen finden Sie unter [Standardaufbewahrungsrichtlinie in Exchange Online](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)
    
- Nachdem Sie das Archivpostfach eines Benutzers aktiviert haben, können Sie dem Benutzer auch mitteilen, dass er gelöschte Elemente im Ordner "Wiederherstellbare Elemente" in seinem Archivpostfach wiederherstellen kann. Sie können dies in Outlook,  indem sie den Ordner "Gelöschte Elemente" im Archivpostfach auswählen und dann auf der Registerkarte **Start** auf **Gelöschte** Elemente von Server wiederherstellen klicken. Weitere Informationen zum Wiederherstellen gelöschter Elemente finden Sie unter [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).