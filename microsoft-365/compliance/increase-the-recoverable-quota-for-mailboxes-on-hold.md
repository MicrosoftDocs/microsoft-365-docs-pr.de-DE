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
description: Aktivieren Sie das Archivpostfach, und aktivieren Sie die automatische Erweiterung der Archivierung, um die Größe des Ordners "Wiederherstellbare Elemente" für ein Postfach in Microsoft 365 zu erhöhen.
ms.openlocfilehash: c674d3df4ad14dabce13effd0dd6729edaeab715
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804644"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>Erhöhen des Kontingents für wiederherstellbare Elemente für aufzubewahrende Postfächer

Die standardmäßige Exchange-Aufbewahrungsrichtlinie – benannte *Standard-MRM-Richtlinie* –, die automatisch auf neue Postfächer in Exchange Online angewendet wird, enthält ein Aufbewahrungs-Tag mit dem Namen "refundable Items 14 Tage" in Archiv verschieben. Mit diesem Aufbewahrungs werden Elemente aus dem Ordner "refundable Items" im primären Postfach des Benutzers in den Ordner "refundable Items" im Archivpostfach des Benutzers verschoben, nachdem der Aufbewahrungszeitraum von 14 Tagen für ein Element abgelaufen ist. Damit dies geschieht, muss das Archivpostfach des Benutzers aktiviert sein. Wenn das Archivpostfach nicht aktiviert ist, wird keine Aktion ausgeführt, was bedeutet, dass Elemente im Ordner "refundable Items" für ein aufbewahrtes Postfach nicht nach Ablauf der 14-tägigen Aufbewahrungsdauer in das Archivpostfach verschoben werden. Da nichts aus einem aufbewahrten Postfach gelöscht wird, kann es sein, dass das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" möglicherweise überschritten wird, insbesondere, wenn das Archivpostfach des Benutzers nicht aktiviert ist. 
  
Um die Wahrscheinlichkeit zu verringern, diesen Grenzwert zu überschreiten, wird das Speicherkontingent für den Ordner "refundable Items" automatisch von 30 GB auf 100 GB erhöht, wenn ein Haltebereich in einem Postfach in Exchange Online abgelegt wird. Wenn das Archivpostfach aktiviert ist, wird das Speicherkontingent für den Ordner "refundable Items" im Archivpostfach ebenfalls von 30 GB auf 100 GB erhöht. Wenn das Feature für die automatische Erweiterung der Archivierung in Exchange Online aktiviert ist, ist das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" im Archiv des Benutzers unbeschränkt.
  
 In der folgenden Tabelle ist das Speicherkontingent für den Ordner "refundable Items" zusammengefasst. 
  
|**Speicherort des Ordners "refundable Items"**|**Nicht in der Warteschleife gehaltene Postfächer**|**Aufbewahrung von Postfächern**|
|:-----|:-----|:-----|
|Primäres Postfach  <br/> |30 GB  <br/> |100 GB  <br/> |
|Archivpostfach<sup>\*</sup> <br/> |Unbegrenzt  <br/> |Unbegrenzt  <br/> |
|**Gesamtes Speicherkontingent für den Ordner "refundable Items"** <br/> |Unbegrenzt  <br/> |Unbegrenzt  <br/> |
   
> [!NOTE]
> <sup>\*</sup> Das anfängliche Speicherkontingent für das Archivpostfach beträgt 100 GB für Benutzer mit einer Lizenz für Exchange Online (Plan 2). Wenn die automatisch expandierende Archivierung für Postfächer aktiviert ist, wird das Speicherkontingent für das Archivpostfach und den Ordner "Wiederherstellbare Elemente" jedoch auf 110 GB erhöht. Wenn erforderlich, wird zusätzlicher Archivspeicherplatz zur Verfügung gestellt, was zu einer unbegrenzten Menge Archivspeicher führt. Weitere Informationen zur automatischen Erweiterung der Archivierung finden Sie unter [Overview of Unlimited Archiving in Office 365](unlimited-archiving.md). 
  
Wenn das Speicherkontingent für den Ordner "refundable Items" im primären Postfach eines aufbewahrten Postfachs nahe am Erreichen des Grenzwerts liegt, können Sie die folgenden Schritte ausführen:
  
- **Aktivieren Sie das Archivpostfach, und aktivieren Sie die automatisch expandierende Archivierung.** Sie können eine unbegrenzte Speicherkapazität für den Ordner "Wiederherstellbare Elemente" einfach aktivieren, indem Sie das Archivpostfach aktivieren und dann das Feature für die automatische Erweiterung der Archivierung in Exchange Online einschalten. Dies führt zu 110 GB für den Ordner "refundable Items" im primären Postfach und eine unbegrenzte Menge an Speicherkapazität für den Ordner "refundable Items" im Archiv des Benutzers. Weitere Informationen finden Sie unter Vorgehensweise: [Aktivieren von archivpostfächern im Security & Compliance Center](enable-archive-mailboxes.md) und [Aktivieren der unbegrenzten Archivierung in Office 365](enable-unlimited-archiving.md).
    
    > [!NOTE]
    > Nachdem Sie das Archiv für ein Postfach aktiviert haben, das das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" überschreitet, müssen Sie möglicherweise den Assistenten für verwaltete Ordner ausführen, um den Assistenten manuell zum Verarbeiten des Postfachs auszulösen, sodass abgelaufene Elemente in den Ordner "Wiederherstellbare Elemente" im Archivpostfach verschoben werden. Anweisungen finden Sie in [Schritt 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) . Beachten Sie, dass andere Elemente im Postfach des Benutzers möglicherweise in das neue Archivpostfach verschoben werden. Sie sollten dem Benutzer mitteilen, dass dies möglicherweise geschieht, nachdem Sie das Archivpostfach aktiviert haben. 
  
- **Erstellen Sie eine benutzerdefinierte Exchange-Aufbewahrungsrichtlinie für Postfächer in der Warteschleife.** Zusätzlich zum Aktivieren des Archivpostfachs und der automatisch wachsenden Archivierung für Postfächer im Aufbewahrungsverfahren oder in In-Place halten möchten Sie möglicherweise auch eine benutzerdefinierte Exchange-Aufbewahrungsrichtlinie für Postfächer in der Warteschleife erstellen. Auf diese Weise können Sie eine Aufbewahrungsrichtlinie auf Postfächer anwenden, die sich von der standardmäßigen MRM-Richtlinie unterscheiden, die auf nicht gesperrte Postfächer angewendet wird, und Sie können Aufbewahrungstags anwenden, die für Postfächer in der Warteschleife ausgelegt sind. Dies umfasst das Erstellen eines neuen Aufbewahrungstags für den Ordner "Wiederherstellbare Elemente". 
    
Im weiteren Verlauf dieses Themas werden die schrittweisen Verfahren zum Erstellen einer benutzerdefinierten Exchange-Aufbewahrungsrichtlinie für Postfächer in der Warteschleife beschrieben.
  
[Schritt 1: Erstellen eines benutzerdefinierten Aufbewahrungstags für den Ordner "Wiederherstellbare Elemente"](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[Schritt 2: Erstellen einer neuen Exchange-Aufbewahrungsrichtlinie für Postfächer in der Warteschleife](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[Schritt 3: Anwenden der neuen Exchange-Aufbewahrungsrichtlinie auf Postfächer in der Warteschleife](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[Optional Schritt 4: Ausführen des Assistenten für verwaltete Ordner zum Anwenden der neuen Aufbewahrungseinstellungen](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>Schritt 1: Erstellen eines benutzerdefinierten Aufbewahrungstags für den Ordner "Wiederherstellbare Elemente"

Der erste Schritt besteht darin, für den Ordner "Wiederherstellbare Elemente" ein benutzerdefiniertes Aufbewahrungstags (als Aufbewahrungsrichtlinientag oder RPT bezeichnet) zu erstellen. Wie bereits erläutert, verschiebt dieser RPT Elemente aus dem Ordner "refundable Items" im primären Postfach des Benutzers in den Ordner "refundable Items" im Archivpostfach des Benutzers. Sie müssen PowerShell verwenden, um eine RPT für den Ordner "Wiederherstellbare Elemente" zu erstellen. Sie können nicht die Exchange-Verwaltungskonsole (EAC) verwenden. 
  
1. [Stellen Sie eine Verbindung mit Exchange Online mithilfe der Remote-PowerShell her](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. Führen Sie den folgenden Befehl aus, um eine neue RPT für den Ordner "Wiederherstellbare Elemente" zu erstellen: 
    
    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    Mit dem folgenden Befehl wird beispielsweise eine RPT für den Ordner "refundable Items" mit dem Namen "refundable Items 30 Days for Mailboxes on Hold" mit einer Aufbewahrungsdauer von 30 Tagen erstellt. Dies bedeutet, dass ein Element im Ordner "Wiederherstellbare Elemente" 30 Tage lang in den Ordner "Wiederherstellbare Elemente" im Archivpostfach des Benutzers verschoben wird.
    
    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > Es wird empfohlen, dass der Aufbewahrungszeitraum (definiert durch den Parameter  _AgeLimitForRetention_ ) für die wiederherstellbaren Elemente RPT mit dem Beibehaltungszeitraum für gelöschte Elemente für die Postfächer identisch ist, auf die die RPT angewendet wird. Dadurch kann ein Benutzer den gesamten Aufbewahrungszeitraum für gelöschte Elemente wiederherstellen, bevor er in das Archivpostfach verschoben wird. Im vorherigen Beispiel wurde der Aufbewahrungszeitraum auf 30 Tage festgelegt, basierend auf der Annahme, dass der Aufbewahrungszeitraum für gelöschte Elemente für Postfächer ebenfalls 30 Tage beträgt. Ein Exchange Online Postfach wird standardmäßig so konfiguriert, dass gelöschte Elemente für 14 Tage aufbewahrt werden. Sie können diese Einstellung jedoch auf maximal 30 Tage ändern. Weitere Informationen finden Sie unter [Ändern des Aufbewahrungszeitraums für gelöschte Elemente für ein Postfach in Exchange Online](https://www.microsoft.com/?ref=go). 
  
## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a>Schritt 2: Erstellen einer neuen Exchange-Aufbewahrungsrichtlinie für Postfächer in der Warteschleife

Im nächsten Schritt erstellen Sie eine neue Aufbewahrungsrichtlinie und fügen ihr Aufbewahrungstags hinzu, einschließlich der wiederherstellbaren Elemente rpt, die Sie in Schritt 1 erstellt haben. Diese neue Richtlinie wird im nächsten Schritt auf die zu speichernden Postfächer angewendet. 
  
Bevor Sie die neue Aufbewahrungsrichtlinie erstellen, müssen Sie die zusätzlichen Aufbewahrungstags bestimmen, die Sie hinzufügen möchten. Eine Liste der Aufbewahrungstags, die der Standard-MRM-Richtlinie hinzugefügt werden, sowie Informationen zum Erstellen neuer Aufbewahrungstags finden Sie in den folgenden Themen:
  
- [Standardaufbewahrungsrichtlinie in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [Standardordner, die Aufbewahrungsrichtlinientags unterstützen](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- Im Abschnitt "Erstellen eines Aufbewahrungstags" im Thema " [Erstellen einer Aufbewahrungsrichtlinie](https://go.microsoft.com/fwlink/p/?LinkId=404422) ".
    
Sie können die Exchange-Verwaltungskonsole oder Exchange Online PowerShell verwenden, um eine Aufbewahrungsrichtlinie zu erstellen.
  
### <a name="use-the-eac-to-create-a-retention-policy"></a>Erstellen einer Aufbewahrungsrichtlinie mithilfe der Exchange-Verwaltungskonsole
  
1. Wechseln Sie in der Exchange- **Verwaltungskonsole zu Compliance Management** \> **Retention Policies** , und klicken Sie dann auf Add Icon **Hinzufügen** ![ ](../media/ITPro-EAC-AddIcon.gif) .
    
2. Geben Sie auf der Seite **neue Aufbewahrungsrichtlinie** unter **Name** einen Namen ein, der den Zweck der Aufbewahrungsrichtlinie beschreibt. beispielsweise **MRM-Richtlinie für Postfächer** , die aufbewahrt werden. 
    
3. Klicken Sie unter **Aufbewahrungstags** auf Add-Symbol **Hinzufügen** ![ ](../media/ITPro-EAC-AddIcon.gif) .
    
4. Wählen Sie in der Liste der Aufbewahrungstags die wiederherstellbaren Elemente RPT aus, die Sie in Schritt 1 erstellt haben, und klicken Sie dann auf **Hinzufügen** .
    
    ![Auswählen des Aufbewahrungstags für benutzerdefinierte Wiederherstellungselemente](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. Wählen Sie zusätzliche Aufbewahrungstags aus, die der Aufbewahrungsrichtlinie hinzugefügt werden sollen. Beispielsweise können Sie die gleichen Tags hinzufügen, die in der standardmäßigen MRM-Richtlinie enthalten sind.
    
6. Wenn Sie das Hinzufügen von Aufbewahrungstags abgeschlossen haben, klicken Sie auf **OK** .
    
7. Klicken Sie auf **Speichern** , um die neue Aufbewahrungsrichtlinie zu erstellen. 
    
    Beachten Sie, dass die Aufbewahrungstags, die mit der Aufbewahrungsrichtlinie verknüpft sind, im Detailbereich angezeigt werden.
    
    ![Im Detailbereich werden Aufbewahrungstags angezeigt, die mit der Aufbewahrungsrichtlinie verknüpft sind.](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>Verwenden Exchange Online PowerShell zum Erstellen einer Aufbewahrungsrichtlinie
  
Führen Sie den folgenden Befehl aus, um eine neue Aufbewahrungsrichtlinie für Postfächer in der Warteschleife zu erstellen. 
  
```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

Mit dem folgenden Befehl werden beispielsweise die Aufbewahrungsrichtlinie und verknüpfte Aufbewahrungstags erstellt, die in der vorherigen Abbildung angezeigt werden.
  
```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a>Schritt 3: Anwenden der neuen Exchange-Aufbewahrungsrichtlinie auf Postfächer in der Warteschleife

Der letzte Schritt besteht darin, die neue Aufbewahrungsrichtlinie, die Sie in Schritt 2 erstellt haben, auf in Ihrer Organisation aufbewahrte Postfächer anzuwenden. Sie können die Exchange-Verwaltungskonsole oder Exchange Online PowerShell verwenden, um die Aufbewahrungsrichtlinie auf ein einzelnes Postfach oder auf mehrere Postfächer anzuwenden. 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>Anwenden der neuen Aufbewahrungsrichtlinie mithilfe der Exchange-Verwaltungskonsole
  
1. Wechseln Sie zu **Empfänger**  >  **Postfächer** .
    
2. Wählen Sie in der Listenansicht das Postfach aus, auf das die Aufbewahrungsrichtlinie angewendet werden soll, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
3. Klicken Sie auf der Seite **Benutzerpostfach** auf **Postfachfunktionen** .
    
4. Wählen Sie unter **Aufbewahrungsrichtlinie** die Aufbewahrungsrichtlinie aus, die Sie in Schritt 2 erstellt haben, und klicken Sie dann auf **Speichern** .
    
Sie können auch die Exchange-Verwaltungskonsole verwenden, um die Aufbewahrungsrichtlinie auf mehrere Postfächer anzuwenden.
  
1. Wechseln Sie zu **Empfänger**  >  **Postfächer** .
    
2. Verwenden Sie in der Listenansicht die UMSCHALT- oder die STRG-TASTE, um mehrere Postfächer auszuwählen.
    
3. Klicken Sie im Detailbereich auf **Weitere Optionen** .
    
4. Klicken Sie unter **Aufbewahrungsrichtlinie** auf **Aktualisieren** .
    
5. Wählen Sie auf der Seite **Aufbewahrungsrichtlinie für Massen Zuweisungen** die Aufbewahrungsrichtlinie aus, die Sie in Schritt 2 erstellt haben, und klicken Sie dann auf **Speichern** . 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>Anwenden der neuen Aufbewahrungsrichtlinie mithilfe Exchange Online PowerShell
  
Sie können Exchange Online PowerShell verwenden, um eine neue Aufbewahrungsrichtlinie auf ein einzelnes Postfach anzuwenden. Die eigentliche Leistungsfähigkeit von PowerShell besteht darin, dass Sie Sie verwenden können, um schnell alle Postfächer in Ihrer Organisation zu identifizieren, die sich entweder in einem Beweissicherungsverfahren befinden oder In-Place halten, und dann die neue Aufbewahrungsrichtlinie auf alle Postfächer in der Warteschleife in einem einzigen Befehl anwenden. Im folgenden finden Sie einige Beispiele für die Verwendung von Exchange PowerShell zum Anwenden einer Aufbewahrungsrichtlinie auf ein oder mehrere Postfächer. In allen Beispielen wird die in Schritt 2 erstellte Aufbewahrungsrichtlinie angewendet.
  
In diesem Beispiel wird die neue Aufbewahrungsrichtlinie auf das Postfach von Pilar Pinilla angewendet.
  
```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

In diesem Beispiel wird die neue Aufbewahrungsrichtlinie auf alle Postfächer in der Organisation angewendet, die das Beweissicherungsverfahren besitzen.
  
```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

In diesem Beispiel wird die neue Aufbewahrungsrichtlinie auf alle Postfächer in der Organisation angewendet, die sich in In-Place halten.
  
```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

Sie können das Cmdlet **Get-Mailbox** verwenden, um zu überprüfen, ob die neue Aufbewahrungsrichtlinie angewendet wurde. 
  
Im folgenden finden Sie einige Beispiele, um zu überprüfen, ob in den Befehlen in den vorherigen Beispielen die Aufbewahrungsrichtlinie für MRM-Richtlinien für Postfächer auf Postfächer für das Beweissicherungsverfahren und die Postfächer in In-Place Archiv angewendet wurde.
  
```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a>Optional Schritt 4: Ausführen des Assistenten für verwaltete Ordner zum Anwenden der neuen Aufbewahrungseinstellungen

Nachdem Sie die neue Exchange-Aufbewahrungsrichtlinie auf aufbewahrte Postfächer angewendet haben, kann es bis zu sieben Tage dauern, bis Exchange Online vom Assistenten für verwaltete Ordner mit den Einstellungen in der neuen Aufbewahrungsrichtlinie diese Postfächer verarbeitet. Anstatt auf die Ausführung des Assistenten für verwaltete Ordner zu warten, können Sie das Cmdlet **Start-ManagedFolderAssistant** verwenden, um den Assistenten manuell auszulösen, um die Postfächer zu verarbeiten, auf die Sie die neue Aufbewahrungsrichtlinie angewendet haben. 
  
Führen Sie den folgenden Befehl aus, um den Assistenten für verwaltete Ordner für das Postfach von Pilar Pinilla zu starten.
  
```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

Führen Sie die folgenden Befehle aus, um den Assistenten für verwaltete Ordner für alle in der Warteschleife stehenden Postfächer zu starten.
  
```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>Weitere Informationen

- Nachdem Sie das Archivpostfach eines Benutzers aktiviert haben, sollten Sie dem Benutzer mitteilen, dass andere Elemente in seinem Postfach (nicht nur Elemente im Ordner "Wiederherstellbare Elemente") möglicherweise in das Archivpostfach verschoben werden. Dies liegt daran, dass die standardmäßige MRM-Richtlinie, die Exchange Online Postfächern zugewiesen ist, ein Aufbewahrungs-Tag enthält (standardmäßig 2 Jahre in Archiv verschieben), das Elemente in das Archivpostfach zwei Jahre nach dem Datum verschiebt, an dem das Element an das Postfach zugestellt oder vom Benutzer erstellt wurde. Weitere Informationen finden Sie unter [default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- Nachdem Sie das Archivpostfach eines Benutzers aktiviert haben, können Sie dem Benutzer auch mitteilen, dass er gelöschte Elemente im Ordner "Wiederherstellbare Elemente" im Archivpostfach wiederherstellen kann. Sie können dies in Outlook tun, indem Sie den Ordner **Gelöschte Elemente** im Archivpostfach auswählen und dann auf der Registerkarte **Start** auf **Gelöschte Elemente aus dem Server wiederherstellen** klicken. Weitere Informationen zum Wiederherstellen gelöschter Elemente finden Sie unter [Wiederherstellen gelöschter Elemente in Outlook für Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829). 
