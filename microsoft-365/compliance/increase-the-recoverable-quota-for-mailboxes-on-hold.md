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
description: Aktivieren Sie das Archivpostfach, und aktivieren Sie die automatisch erweiternde Archivierung, um die Größe des Ordners "Wiederherstellbare Elemente" für ein Postfach in Microsoft 365 zu erhöhen.
ms.openlocfilehash: 47227e066f922a9e4b8bccedaa9573c001194836
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226587"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>Erhöhen des Kontingents für wiederherstellbare Elemente für aufzubewahrende Postfächer

Die Standardmäßige Exchange Aufbewahrungsrichtlinie mit dem Namen *"Standard-MRM-Richtlinie",* die automatisch auf neue Postfächer in Exchange Online angewendet wird, enthält ein Aufbewahrungstag namens "Wiederherstellbare Elemente 14 Tage" verschieben in das Archiv. Dieses Aufbewahrungstag verschiebt Elemente aus dem Ordner "Wiederherstellbare Elemente" im primären Postfach des Benutzers in den Ordner "Wiederherstellbare Elemente" im Archivpostfach des Benutzers, nachdem der Aufbewahrungszeitraum von 14 Tagen für ein Element abgelaufen ist. Damit dies geschieht, muss das Archivpostfach des Benutzers aktiviert sein. Wenn das Archivpostfach nicht aktiviert ist, wird keine Aktion ausgeführt, was bedeutet, dass Elemente im Ordner "Wiederherstellbare Elemente" für ein Postfach, für das die Aufbewahrung aktiviert ist, nach Ablauf des Aufbewahrungszeitraums von 14 Tagen nicht in das Archivpostfach verschoben werden. Da aus einem Postfach, für das die Aufbewahrung aktiviert ist, nichts gelöscht wird, kann das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" überschritten werden, insbesondere wenn das Archivpostfach des Benutzers nicht aktiviert ist.

Um die Wahrscheinlichkeit zu verringern, dass dieser Grenzwert überschritten wird, wird das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" automatisch von 30 GB auf 100 GB erhöht, wenn ein Postfach in Exchange Online gehalten wird. Wenn das Archivpostfach aktiviert ist, wird das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" im Archivpostfach ebenfalls von 30 GB auf 100 GB erhöht. Wenn die Funktion zum automatischen Erweitern der Archivierung in Exchange Online aktiviert ist, ist das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" im Archiv des Benutzers unbegrenzt.

 In der folgenden Tabelle ist das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" zusammengefasst.

|**Speicherort des Ordners "Wiederherstellbare Elemente"**|**Postfächer, die nicht in der Warteschleife sind**|**Postfächer im Haltebereich**|
|:-----|:-----|:-----|
|Primäres Postfach  <br/> |30 GB  <br/> |100 GB  <br/> |
|Archivpostfach<sup>\*</sup> <br/> |Unbegrenzt  <br/> |Unbegrenzt  <br/> |
|**Gesamtspeicherkontingent für den Ordner "Wiederherstellbare Elemente"** <br/> |Unbegrenzt  <br/> |Unbegrenzt  <br/> |

> [!NOTE]
> <sup>\*</sup>Das anfängliche Speicherkontingent für das Archivpostfach beträgt 100 GB für Benutzer mit einer Exchange Online (Plan 2)-Lizenz. Wenn jedoch die automatische Erweiterung der Archivierung für Postfächer aktiviert ist, die die Aufbewahrung aktiviert haben, wird das Speicherkontingent für das Archivpostfach und den Ordner "Wiederherstellbare Elemente" auf 110 GB erhöht. Bei Bedarf wird zusätzlicher Archivspeicherplatz bereitgestellt, was zu einer unbegrenzten Menge an Archivspeicher führt. Weitere Informationen zur automatischen Erweiterung der Archivierung finden Sie unter [Übersicht über die unbegrenzte Archivierung in Office 365.](unlimited-archiving.md)

Wenn das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" im primären Postfach eines Postfachs, für das die Aufbewahrung aktiviert ist, kurz vor dem Erreichen seines Grenzwerts liegt, können Sie die folgenden Schritte ausführen:

- **Aktivieren Sie das Archivpostfach, und aktivieren Sie die automatisch erweiternde Archivierung.** Sie können eine unbegrenzte Speicherkapazität für den Ordner "Wiederherstellbare Elemente" aktivieren, indem Sie einfach das Archivpostfach aktivieren und dann das Feature für die automatisch erweiternde Archivierung in Exchange Online aktivieren. Dies führt zu 110 GB für den Ordner "Wiederherstellbare Elemente" im primären Postfach und zu einer unbegrenzten Speicherkapazität für den Ordner "Wiederherstellbare Elemente" im Archiv des Benutzers. Erfahren Sie, wie Sie [Archivpostfächer im Security & Compliance Center aktivieren](enable-archive-mailboxes.md) und die unbegrenzte Archivierung in Office 365 [aktivieren.](enable-unlimited-archiving.md)

    > [!NOTE]
    > Nachdem Sie das Archiv für ein Postfach aktiviert haben, das fast das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" überschreitet, sollten Sie den Assistenten für verwaltete Ordner ausführen, um manuell die Verarbeitung des Postfachs durch den Assistenten auszulösen, sodass abgelaufene Elemente in den Ordner "Wiederherstellbare Elemente" im Archivpostfach verschoben werden. Anweisungen finden Sie [in Schritt 4.](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) Beachten Sie, dass andere Elemente im Postfach des Benutzers möglicherweise in das neue Archivpostfach verschoben werden. Erwägen Sie, dem Benutzer mitzuteilen, dass dies nach dem Aktivieren des Archivpostfachs passieren kann.

- **Erstellen Sie eine benutzerdefinierte Exchange Aufbewahrungsrichtlinie für Postfächer, die in der Warteschleife sind.** Zusätzlich zum Aktivieren des Archivpostfachs und der automatischen Erweiterung der Archivierung für Postfächer mit Beweissicherung oder In-Place Haltebereich sollten Sie auch eine benutzerdefinierte Exchange Aufbewahrungsrichtlinie für Postfächer erstellen, für die die Aufbewahrung aktiviert ist. Auf diese Weise können Sie eine Aufbewahrungsrichtlinie auf Postfächer anwenden, die sich von der Standard-MRM-Richtlinie unterscheiden, die auf Postfächer angewendet wird, die nicht in der Warteschleife sind, und Sie können Aufbewahrungstags anwenden, die für Postfächer im Haltebereich vorgesehen sind. Dazu gehört das Erstellen eines neuen Aufbewahrungstags für den Ordner "Wiederherstellbare Elemente".

Im restlichen Teil dieses Themas werden die schrittweisen Verfahren zum Erstellen einer benutzerdefinierten Exchange Aufbewahrungsrichtlinie für Postfächer im Haltebereich beschrieben.

[Schritt 1: Erstellen eines benutzerdefinierten Aufbewahrungstags für den Ordner "Wiederherstellbare Elemente"](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[Schritt 2: Erstellen einer neuen Exchange Aufbewahrungsrichtlinie für Postfächer, die in der Warteschleife sind](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[Schritt 3: Anwenden der neuen Exchange Aufbewahrungsrichtlinie auf Postfächer, die in der Warteschleife sind](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[(Optional) Schritt 4: Ausführen des Assistenten für verwaltete Ordner zum Anwenden der neuen Aufbewahrungseinstellungen](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)

## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>Schritt 1: Erstellen eines benutzerdefinierten Aufbewahrungstags für den Ordner "Wiederherstellbare Elemente"

Der erste Schritt besteht darin, ein benutzerdefiniertes Aufbewahrungstag (auch als Aufbewahrungsrichtlinientag oder RPT bezeichnet) für den Ordner "Wiederherstellbare Elemente" zu erstellen. Wie zuvor erläutert, verschiebt dieses RPT Elemente aus dem Ordner "Wiederherstellbare Elemente" im primären Postfach des Benutzers in den Ordner "Wiederherstellbare Elemente" im Archivpostfach des Benutzers. Sie müssen PowerShell verwenden, um ein RPT für den Ordner "Wiederherstellbare Elemente" zu erstellen. Sie können nicht die Exchange-Verwaltungskonsole (EAC) verwenden.

1. [Stellen Sie eine Verbindung mit Exchange Online mithilfe der Remote-PowerShell her](/powershell/exchange/connect-to-exchange-online-powershell)

2. Führen Sie den folgenden Befehl aus, um ein neues RPT für den Ordner "Wiederherstellbare Elemente" zu erstellen:

    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    Der folgende Befehl erstellt z. B. ein RPT für den Ordner "Wiederherstellbare Elemente 30 Tage für Postfächer im Haltebereich" mit einem Aufbewahrungszeitraum von 30 Tagen. Dies bedeutet, dass ein Element, nachdem es sich 30 Tage lang im Ordner "Wiederherstellbare Elemente" befindet, in den Ordner "Wiederherstellbare Elemente" im Archivpostfach des Benutzers verschoben wird.

    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > Es wird empfohlen, dass der Aufbewahrungszeitraum (definiert durch den  _Parameter AgeLimitForRetention)_ für das RPT "Wiederherstellbare Elemente" dem Aufbewahrungszeitraum für gelöschte Elemente für die Postfächer entspricht, auf die das RPT angewendet wird. Dadurch kann ein Benutzer den gesamten Aufbewahrungszeitraum für gelöschte Elemente wiederherstellen, bevor er in das Archivpostfach verschoben wird. Im vorherigen Beispiel wurde der Aufbewahrungszeitraum auf 30 Tage festgelegt, basierend auf der Annahme, dass der Aufbewahrungszeitraum für gelöschte Elemente für Postfächer ebenfalls 30 Tage beträgt. Ein Exchange Online Postfach ist so konfiguriert, dass gelöschte Elemente standardmäßig 14 Tage lang aufbewahrt werden. Sie können diese Einstellung jedoch auf maximal 30 Tage ändern. Weitere Informationen finden Sie unter [Ändern des Aufbewahrungszeitraums für gelöschte Elemente für ein Postfach in Exchange Online](https://www.microsoft.com/?ref=go).

## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a>Schritt 2: Erstellen einer neuen Exchange Aufbewahrungsrichtlinie für Postfächer, die in der Warteschleife sind

Der nächste Schritt besteht darin, eine neue Aufbewahrungsrichtlinie zu erstellen und ihr Aufbewahrungstags hinzuzufügen, einschließlich der wiederherstellbaren Elemente-RPT, die Sie in Schritt 1 erstellt haben. Diese neue Richtlinie wird im nächsten Schritt auf Postfächer angewendet, die in der Warteschleife sind.

Bevor Sie die neue Aufbewahrungsrichtlinie erstellen, bestimmen Sie die zusätzlichen Aufbewahrungstags, die Sie hinzufügen möchten. Eine Liste der Aufbewahrungstags, die der Standard-MRM-Richtlinie hinzugefügt werden, sowie Informationen zum Erstellen neuer Aufbewahrungstags finden Sie unter:

- [Standardaufbewahrungsrichtlinie in Exchange Online ](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

- [Standardordner, die Aufbewahrungsrichtlinientags unterstützen](/exchange/security-and-compliance/messaging-records-management/default-folders)

- Der Abschnitt "Erstellen eines Aufbewahrungstags" im Thema ["Aufbewahrungsrichtlinie erstellen".](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy)

Sie können das EAC oder Exchange Online PowerShell verwenden, um eine Aufbewahrungsrichtlinie zu erstellen.

### <a name="use-the-eac-to-create-a-retention-policy"></a>Erstellen einer Aufbewahrungsrichtlinie mithilfe der Exchange-Verwaltungskonsole

1. Wechseln Sie im EAC zu Aufbewahrungsrichtlinien für die **Complianceverwaltung,** \> und klicken Sie dann auf "Symbol **hinzufügen".** ![ ](../media/ITPro-EAC-AddIcon.gif)

2. Geben Sie auf der Seite **"Neue Aufbewahrungsrichtlinie"** unter **"Name"** einen Namen ein, der den Zweck der Aufbewahrungsrichtlinie beschreibt. Beispielsweise **mrm-Richtlinie für Postfächer im Haltebereich**.

3. Klicken Sie unter **"Aufbewahrungstags"** auf "Symbol  ![ ](../media/ITPro-EAC-AddIcon.gif) hinzufügen".

4. Wählen Sie in der Liste der Aufbewahrungstags das RPT "Wiederherstellbare Elemente", das Sie in Schritt 1 erstellt haben, und klicken Sie dann auf **"Hinzufügen".**

    ![Auswählen des benutzerdefinierten Aufbewahrungstags für wiederherstellbare Elemente](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)

5. Wählen Sie zusätzliche Aufbewahrungstags aus, die der Aufbewahrungsrichtlinie hinzugefügt werden sollen. Sie können z. B. dieselben Tags hinzufügen, die in der Standard-MRM-Richtlinie enthalten sind.

6. Wenn Sie mit dem Hinzufügen von Aufbewahrungstags fertig sind, klicken Sie auf **OK.**

7. Klicken Sie auf **"Speichern",** um die neue Aufbewahrungsrichtlinie zu erstellen.

    Beachten Sie, dass die mit der Aufbewahrungsrichtlinie verknüpften Aufbewahrungstags im Detailbereich angezeigt werden.

    ![Aufbewahrungstags, die mit der Aufbewahrungsrichtlinie verknüpft sind, werden im Detailbereich angezeigt.](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)

### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>Verwenden von Exchange Online PowerShell zum Erstellen einer Aufbewahrungsrichtlinie

Führen Sie den folgenden Befehl aus, um eine neue Aufbewahrungsrichtlinie für Postfächer zu erstellen, für die die Aufbewahrung aktiviert ist.

```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

Mit dem folgenden Befehl werden beispielsweise die Aufbewahrungsrichtlinie und verknüpfte Aufbewahrungstags erstellt, die in der vorherigen Abbildung angezeigt werden.

```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a>Schritt 3: Anwenden der neuen Exchange-Aufbewahrungsrichtlinie auf Postfächer, die in der Warteschleife sind

Der letzte Schritt besteht darin, die neue Aufbewahrungsrichtlinie, die Sie in Schritt 2 erstellt haben, auf Postfächer anzuwenden, die in Ihrer Organisation aufbewahrt werden. Sie können die EAC oder Exchange Online PowerShell verwenden, um die Aufbewahrungsrichtlinie auf ein einzelnes Postfach oder mehrere Postfächer anzuwenden.

### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>Verwenden des EAC zum Anwenden der neuen Aufbewahrungsrichtlinie

1. Wechseln Sie zu **"Empfängerpostfächer".**  >  

2. Wählen Sie in der Listenansicht das Postfach aus, auf das  Sie die Aufbewahrungsrichtlinie anwenden möchten, und klicken Sie dann auf das Symbol ![ "Bearbeiten". ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)

3. Klicken Sie auf der Seite **"Benutzerpostfach"** auf **"Postfachfeatures".**

4. Wählen Sie unter **"Aufbewahrungsrichtlinie"** die Aufbewahrungsrichtlinie aus, die Sie in Schritt 2 erstellt haben, und klicken Sie dann auf **"Speichern".**

Sie können das EAC auch verwenden, um die Aufbewahrungsrichtlinie auf mehrere Postfächer anzuwenden.

1. Wechseln Sie zu **"Empfängerpostfächer".**  >  

2. Verwenden Sie in der Listenansicht die UMSCHALT- oder die STRG-TASTE, um mehrere Postfächer auszuwählen.

3. Klicken Sie im Detailbereich auf **Weitere Optionen**.

4. Klicken Sie unter **Aufbewahrungsrichtlinie** auf **Aktualisieren**.

5. Wählen Sie auf der Seite **"Massenzuweisung von Aufbewahrungsrichtlinien"** die Aufbewahrungsrichtlinie aus, die Sie in Schritt 2 erstellt haben, und klicken Sie dann auf **"Speichern".**

### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>Verwenden Exchange Online PowerShell zum Anwenden der neuen Aufbewahrungsrichtlinie

Sie können Exchange Online PowerShell verwenden, um eine neue Aufbewahrungsrichtlinie auf ein einzelnes Postfach anzuwenden. Die eigentliche Leistungsfähigkeit von PowerShell besteht jedoch darin, dass Sie damit schnell alle Postfächer in Ihrer Organisation identifizieren können, die sich entweder für das Beweissicherungsverfahren oder In-Place Halten befinden, und dann die neue Aufbewahrungsrichtlinie in einem einzigen Befehl auf alle Postfächer anwenden können, die in der Warteschleife sind. Hier sind einige Beispiele für die Verwendung von Exchange PowerShell, um eine Aufbewahrungsrichtlinie auf ein oder mehrere Postfächer anzuwenden. Alle Beispiele wenden die Aufbewahrungsrichtlinie an, die in Schritt 2 erstellt wurde.

In diesem Beispiel wird die neue Aufbewahrungsrichtlinie auf das Postfach von Pilar Pinilla angewendet.

```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

In diesem Beispiel wird die neue Aufbewahrungsrichtlinie auf alle Postfächer in der Organisation angewendet, für die die Aufbewahrung für juristische Zwecke aktiviert ist.

```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

In diesem Beispiel wird die neue Aufbewahrungsrichtlinie auf alle Postfächer in der Organisation angewendet, die sich in In-Place Haltebereich befinden.

```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

Mit dem Cmdlet **"Get-Mailbox"** können Sie überprüfen, ob die neue Aufbewahrungsrichtlinie angewendet wurde.

Hier sind einige Beispiele, um zu überprüfen, ob die Befehle in den vorherigen Beispielen die Aufbewahrungsrichtlinie "MRM Policy for Mailboxes on Hold" auf Postfächer mit Beweissicherungsverfahren und Postfächer mit In-Place Aufbewahrung angewendet haben.

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

Nachdem Sie die neue Exchange Aufbewahrungsrichtlinie auf Postfächer angewendet haben, kann es bis zu 7 Tage in Exchange Online dauern, bis der Assistent für verwaltete Ordner diese Postfächer mithilfe der Einstellungen in der neuen Aufbewahrungsrichtlinie verarbeitet. Anstatt auf die Ausführung des Assistenten für verwaltete Ordner zu warten, können Sie das Cmdlet **"Start-ManagedFolderAssistant"** verwenden, um den Assistenten manuell auszulösen, um die Postfächer zu verarbeiten, auf die Sie die neue Aufbewahrungsrichtlinie angewendet haben.

Führen Sie den folgenden Befehl aus, um den Assistenten für verwaltete Ordner für das Postfach von Pilar Pinilla zu starten.

```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

Führen Sie die folgenden Befehle aus, um den Assistenten für verwaltete Ordner für alle Postfächer zu starten, die in der Warteschleife sind.

```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>Weitere Informationen

- Nachdem Sie das Archivpostfach eines Benutzers aktiviert haben, sollten Sie dem Benutzer mitteilen, dass andere Elemente in ihrem Postfach (nicht nur Elemente im Ordner "Wiederherstellbare Elemente") möglicherweise in das Archivpostfach verschoben werden. Dies liegt daran, dass die Standard-MRM-Richtlinie, die Exchange Online Postfächern zugewiesen ist, ein Aufbewahrungstag (mit dem Namen "Standard 2 Jahre Verschieben in archivieren") enthält, das Elemente zwei Jahre nach dem Datum, an dem das Element an das Postfach übermittelt oder vom Benutzer erstellt wurde, in das Archivpostfach verschiebt. Weitere Informationen finden Sie unter [Standardaufbewahrungsrichtlinie in Exchange Online](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

- Nachdem Sie das Archivpostfach eines Benutzers aktiviert haben, können Sie dem Benutzer auch mitteilen, dass er gelöschte Elemente im Ordner "Wiederherstellbare Elemente" in dessen Archivpostfach wiederherstellen kann. Sie können dies in Outlook tun, indem sie den Ordner **"Gelöschte Elemente"** im Archivpostfach auswählen und dann auf der Registerkarte **"Start"** auf **"Gelöschte Elemente vom Server wiederherstellen"** klicken. Weitere Informationen zum Wiederherstellen gelöschter Elemente finden Sie unter [Wiederherstellen gelöschter Elemente in Outlook für Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).
