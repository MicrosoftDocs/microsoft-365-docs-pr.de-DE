---
title: Einrichten einer Archivierungs- und Löschrichtlinie für Postfächer in Ihrer Organisation
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
ms.custom: seo-marvel-apr2020
description: Erfahren Sie, wie Sie eine Archivierungs- und Löschrichtlinie in Microsoft 365 erstellen, die Elemente automatisch in das Archivpostfach eines Benutzers verschiebt.
ms.openlocfilehash: 45d6428f5b0a856538d500b1d1f0447447b9dfe9
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341640"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-organization"></a>Einrichten einer Archivierungs- und Löschrichtlinie für Postfächer in Ihrer Organisation

In Microsoft 365 können Administratoren eine Archivierungs- und Löschrichtlinie erstellen, die Elemente automatisch in das Archivpostfach eines Benutzers verschiebt und Elemente automatisch aus dem Postfach löscht. Der Administrator erstellt dazu eine Aufbewahrungsrichtlinie, die Postfächern zugewiesen ist, und verschiebt Elemente nach einem bestimmten Zeitraum in das Archivpostfach eines Benutzers und löscht auch Elemente aus dem Postfach, nachdem sie ein bestimmtes Alter erreicht haben. Die tatsächlichen Regeln, die bestimmen, welche Elemente verschoben oder gelöscht werden und wann dies geschieht, werden als Aufbewahrungstags bezeichnet. Aufbewahrungstags sind mit einer Aufbewahrungsrichtlinie verknüpft, die wiederum dem Postfach eines Benutzers zugewiesen wird. Ein Aufbewahrungstag wendet Aufbewahrungseinstellungen auf einzelne Nachrichten und Ordner im Postfach eines Benutzers an. Es definiert, wie lange eine Nachricht im Postfach verbleibt und welche Aktion ausgeführt wird, wenn die Nachricht das angegebene Aufbewahrungsalter erreicht. Wenn eine Nachricht das Aufbewahrungsalter erreicht, wird sie entweder in das Archivpostfach des Benutzers verschoben oder gelöscht.
  
Mit den Schritten in diesem Artikel wird eine Archivierungs- und Aufbewahrungsrichtlinie für eine fiktive Organisation namens "The House" eingerichtet. Das Einrichten dieser Richtlinie umfasst die folgenden Aufgaben:
  
- Aktivieren eines Archivpostfachs für jeden Benutzer in der Organisation. Dadurch erhalten Benutzer zusätzlichen Postfachspeicher und ist erforderlich, damit eine Aufbewahrungsrichtlinie Elemente in das Archivpostfach verschieben kann. Darüber hinaus können Benutzer Archivinformationen speichern, indem Elemente in ihr Archivpostfach verschoben werden.

- Erstellen von drei benutzerdefinierten Aufbewahrungstags mit folgenden Aktionen:

  - Verschiebt Elemente, die 3 Jahre alt sind, automatisch in das Archivpostfach des Benutzers. Durch verschieben von Elementen in das Archivpostfach wird Speicherplatz im primären Postfach eines Benutzers freigegeben.

  - Löscht automatisch Elemente, die 5 Jahre alt sind, aus dem Ordner "Gelöschte Elemente". Dadurch wird auch Speicherplatz im primären Postfach des Benutzers freigegeben. Benutzer haben die Möglichkeit, diese Elemente bei Bedarf wiederherzustellen. Weitere Informationen finden Sie in der Fußnote im Abschnitt ["Weitere Informationen".](#more-information) 

  - Löscht Elemente, die 7 Jahre alt sind, automatisch (und dauerhaft) aus dem primären Postfach und dem Archivpostfach. Aufgrund von Compliance-Bestimmungen müssen einige Organisationen E-Mails für einen bestimmten Zeitraum aufbewahren. Nach Ablauf dieses Zeitraums möchte eine Organisation diese Benutzerpostfächer möglicherweise dauerhaft entfernen.

- Erstellen einer neuen Aufbewahrungsrichtlinie und Hinzufügen der neuen benutzerdefinierten Aufbewahrungstags. Darüber hinaus fügen Sie der neuen Aufbewahrungsrichtlinie auch integrierte Aufbewahrungstags hinzu. Dazu gehören persönliche Tags, die Benutzer Elementen in ihrem Postfach zuweisen können. Darüber hinaus fügen Sie ein Aufbewahrungstag hinzu, das Elemente aus dem Ordner "Wiederherstellbare Elemente" im primären Postfach des Benutzers in den Ordner "Wiederherstellbare Elemente" im Archivpostfach verschiebt. Dadurch wird Speicherplatz im Ordner "Wiederherstellbare Elemente" eines Benutzers freigegeben, wenn sein Postfach in den Haltebereich versetzt wird.

Sie können einige oder alle Schritte in diesem Artikel ausführen, um eine Archiv- und Löschrichtlinie für Postfächer in Ihrer eigenen Organisation einzurichten. Es wird empfohlen, diesen Prozess mit einigen Postfächern zu testen, bevor Sie ihn für alle Postfächer in Ihrer Organisation implementieren.
  
## <a name="before-you-set-up-an-archive-and-deletion-policy"></a>Vor dem Einrichten einer Archivierungs- und Löschrichtlinie

- Sie müssen ein globaler Administrator in Ihrer Organisation sein, um die Schritte in diesem Thema ausführen zu können. 

- Wenn Sie ein neues Benutzerkonto erstellen und dem Benutzer eine Exchange Online Lizenz zuweisen, wird automatisch ein Postfach für den Benutzer erstellt. Wenn das Postfach erstellt wird, wird ihm automatisch eine Standardaufbewahrungsrichtlinie mit dem Namen "Standard-MRM-Richtlinie" zugewiesen. In diesem Artikel erstellen Sie eine neue Aufbewahrungsrichtlinie und weisen sie dann Benutzerpostfächern zu, indem Sie die Standard-MRM-Richtlinie ersetzen. Einem Postfach kann jeweils nur eine Aufbewahrungsrichtlinie zugewiesen werden.

- Weitere Informationen zu Aufbewahrungstags und Aufbewahrungsrichtlinien in Exchange Online finden Sie unter [Aufbewahrungstags und Aufbewahrungsrichtlinien.](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

## <a name="step-1-enable-archive-mailboxes-for-users"></a>Schritt 1: Aktivieren von Archivpostfächern für Benutzer

Der erste Schritt besteht darin, das Archivpostfach für jeden Benutzer in Ihrer Organisation zu aktivieren. Das Archivpostfach eines Benutzers muss aktiviert sein, damit ein Aufbewahrungstag mit der Aufbewahrungsaktion "In Archiv verschieben" das Element nach Ablauf des Aufbewahrungsalters verschieben kann.
  
> [!NOTE]
> Sie können Archivpostfächer während dieses Prozesses jederzeit aktivieren, solange sie zu einem bestimmten Zeitpunkt aktiviert sind, bevor Sie den Prozess abschließen. Wenn ein Archivpostfach nicht aktiviert ist, wird keine Aktion für Elemente ausgeführt, denen eine Archiv- oder Löschrichtlinie zugewiesen ist.
  
1. Wechseln Sie zu <https://compliance.microsoft.com>.

2. Melden Sie sich mit Ihrem globalen Administratorkonto an.
    
3. Klicken Sie im Microsoft 365 Compliance Center auf **"Informationsgovernance"** und dann auf die Registerkarte **"Archiv".**

    Es wird eine Liste der Postfächer in Ihrer Organisation angezeigt und ob das entsprechende Archivpostfach aktiviert oder deaktiviert ist.

4. Wählen Sie alle Postfächer aus, indem Sie auf das erste In der Liste klicken, die **UMSCHALTTASTE** gedrückt halten und dann auf das letzte Postfach in der Liste klicken.

    > [!TIP]
    > Bei diesem Schritt wird davon ausgegangen, dass keine Archivpostfächer aktiviert sind. Wenn Sie Postfächer mit aktivierter Archivierung haben, halten Sie die **STRG-TASTE** gedrückt, und klicken Sie auf jedes Postfach, das über ein deaktiviertes Archivpostfach verfügt. Sie können auch auf die Spaltenüberschrift des **Archivpostfachs** klicken, um die Zeilen basierend darauf zu sortieren, ob das Archivpostfach aktiviert oder deaktiviert ist, um die Auswahl von Postfächern zu vereinfachen.
  
5. Klicken Sie im Detailbereich unter **"Massenbearbeitung"** auf **"Aktivieren".**

    Es wird eine Warnung angezeigt, die besagt, dass Elemente, die älter als zwei Jahre sind, in das neue Archivpostfach verschoben werden. Dies liegt daran, dass die Standardaufbewahrungsrichtlinie, die einem neuen Benutzerpostfach zugewiesen wird, wenn es erstellt wird, ein Standardmäßiges Archivrichtlinientag mit einem Aufbewahrungsalter von 2 Jahren aufweist. Das benutzerdefinierte Standardrichtlinientag, das Sie in Schritt 2 erstellen, hat ein Aufbewahrungsalter von 3 Jahren. Das bedeutet, dass Elemente, die 3 Jahre oder älter sind, in das Archivpostfach verschoben werden.

6. Klicken Sie auf **"Ja",** um die Warnmeldung zu schließen und den Vorgang zum Aktivieren des Archivpostfachs für jedes ausgewählte Postfach zu starten.

7. Klicken Sie nach Abschluss  des Vorgangs auf ![ "Aktualisieren", ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) um die Liste auf der Seite **"Archiv"** zu aktualisieren.

    Das Archivpostfach ist für alle Benutzer in Ihrer Organisation aktiviert.

    ![Die Liste der Postfächer, für die das Archivpostfach aktiviert ist](../media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)

## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a>Schritt 2: Erstellen neuer Aufbewahrungstags für die Archiv- und Löschrichtlinien

In diesem Schritt erstellen Sie die drei benutzerdefinierten Aufbewahrungstags, die zuvor beschrieben wurden.
  
- Almen house 3 Year Move to Archive (custom archive policy)

- Dauerhaftes Löschen des 7-Jahres-Hauses (benutzerdefinierte Löschrichtlinie)

- Datensätze gelöschte Elemente 5 Jahre Löschen und Wiederherstellen zulassen (benutzerdefiniertes Tag für den Ordner "Gelöschte Elemente")

Um neue Aufbewahrungstags zu erstellen, verwenden Sie das Exchange Admin Center (EAC) in Ihrer Exchange Online Organisation. Achten Sie darauf, die klassische Version des EAC zu verwenden.
  
1. Wechseln Sie zu [https://admin.protection.outlook.com/ecp/](https://admin.protection.outlook.com/ecp/) und melden Sie sich mit Ihren Anmeldeinformationen an.
  
2. Wechseln Sie im EAC zu   >  **Aufbewahrungstags** für die Complianceverwaltung

    Eine Liste der Aufbewahrungstags für Ihre Organisation wird angezeigt.

### <a name="create-a-custom-archive-default-policy-tag"></a>Erstellen eines benutzerdefinierten Standardrichtlinientags für das Archiv
  
Zuerst erstellen Sie ein benutzerdefiniertes Standardrichtlinientag (Archive Default Policy Tag, DPT), mit dem Elemente nach 3 Jahren in das Archivpostfach verschoben werden.
  
1. Klicken Sie auf der Seite **"Aufbewahrungstags"** auf das Symbol **"Neues Tag"** ![ und wählen Sie dann automatisch auf das gesamte Postfach angewendet aus ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **(Standard).**

2. Füllen Sie auf der Seite "Neues Tag", das **automatisch auf das gesamte Postfach angewendet wird (Standardseite),** die folgenden Felder aus: 

    ![Einstellungen zum Erstellen eines neuen Standardmäßigen Archivierungsrichtlinientags](../media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
   1. **Name** Geben Sie einen Namen für das neue Aufbewahrungstag ein. 

   2. **Aufbewahrungsaktion** Wählen Sie **"In Archiv verschieben"** aus, um Elemente in das Archivpostfach zu verschieben, wenn der Aufbewahrungszeitraum abläuft.

   3. **Aufbewahrungszeitraum** Wählen Sie **aus, wann das Element das folgende Alter (in Tagen) erreicht,** und geben Sie dann die Dauer des Aufbewahrungszeitraums ein. In diesem Szenario werden Elemente nach 1095 Tagen (3 Jahren) in das Archivpostfach verschoben.

   4. **Comment** (Optional) Geben Sie einen Kommentar ein, der den Zweck des benutzerdefinierten Aufbewahrungstags erläutert.

3. Klicken Sie auf **"Speichern",** um das benutzerdefinierte Archiv-DPT zu erstellen.

    Das neue Archiv-DPT wird in der Liste der Aufbewahrungstags angezeigt.

### <a name="create-a-custom-deletion-default-policy-tag"></a>Erstellen eines benutzerdefinierten Standardrichtlinientags für Löschvorgänge
  
Als Nächstes erstellen Sie ein weiteres benutzerdefiniertes DPT, bei dem es sich jedoch um eine Löschrichtlinie handelt, die Elemente nach 7 Jahren endgültig löscht.
  
1. Klicken Sie auf der Seite **"Aufbewahrungstags"** auf das Symbol **"Neues Tag"** ![ und wählen Sie dann automatisch auf das gesamte Postfach angewendet aus ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **(Standard).**

2. Füllen Sie auf der Seite "Neues Tag", das **automatisch auf das gesamte Postfach angewendet wird (Standardseite),** die folgenden Felder aus: 

    ![Einstellungen zum Erstellen eines neuen Standardmäßigen Richtlinientags für Löschvorgänge](../media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
   1. **Name** Geben Sie einen Namen für das neue Aufbewahrungstag ein. 

   2. **Aufbewahrungsaktion** Wählen Sie **"Endgültig löschen"** aus, um Elemente aus dem Postfach zu löschen, wenn der Aufbewahrungszeitraum abläuft.

   3. **Aufbewahrungszeitraum** Wählen Sie **aus, wann das Element das folgende Alter (in Tagen) erreicht,** und geben Sie dann die Dauer des Aufbewahrungszeitraums ein. In diesem Szenario werden Elemente nach 2555 Tagen (7 Jahren) gelöscht.

   4. **Comment** (Optional) Geben Sie einen Kommentar ein, der den Zweck des benutzerdefinierten Aufbewahrungstags erläutert. 

3. Klicken Sie auf **"Speichern",** um das benutzerdefinierte Lösch-DPT zu erstellen. 

    Das neue Lösch-DPT wird in der Liste der Aufbewahrungstags angezeigt.

### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a>Erstellen eines benutzerdefinierten Aufbewahrungsrichtlinientags für den Ordner "Gelöschte Elemente"
  
Das letzte Aufbewahrungstag, das Sie erstellen werden, ist ein benutzerdefiniertes Aufbewahrungsrichtlinientag (RPT) für den Ordner "Gelöschte Elemente". Dieses Tag löscht Elemente im Ordner "Gelöschte Elemente" nach 5 Jahren und bietet einen Wiederherstellungszeitraum, in dem Benutzer das Tool "Gelöschte Elemente wiederherstellen" verwenden können, um ein Element wiederherzustellen.
  
1. Klicken Sie auf der Seite **"Aufbewahrungstags"** auf das Symbol **"Neues Tag"** ![ und wählen Sie dann ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **"Automatisch auf einen Standardordner angewendet"** aus.

2. Füllen Sie auf dem neuen Tag, das **automatisch auf eine Standardordnerseite angewendet wird,** die folgenden Felder aus:

    ![Einstellungen zum Erstellen eines neuen Aufbewahrungsrichtlinientags für den Ordner "Gelöschte Elemente"](../media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
   1. **Name** Geben Sie einen Namen für das neue Aufbewahrungstag ein. 

   2. **Anwenden dieses Tags auf den folgenden Standardordner** Wählen Sie in der Dropdownliste **gelöschte Elemente aus.**

   3. **Aufbewahrungsaktion** Wählen Sie **"Löschen" und "Wiederherstellung zulassen"** aus, um Elemente zu löschen, wenn der Aufbewahrungszeitraum abgelaufen ist, aber zulassen, dass Benutzer ein gelöschtes Element innerhalb des Aufbewahrungszeitraums für gelöschte Elemente wiederherstellen (standardmäßig 14 Tage).

   4. **Aufbewahrungszeitraum** Wählen Sie **aus, wann das Element das folgende Alter (in Tagen) erreicht,** und geben Sie dann die Dauer des Aufbewahrungszeitraums ein. In diesem Szenario werden Elemente nach 1825 Tagen (5 Jahren) gelöscht.

   5. **Comment** (Optional) Geben Sie einen Kommentar ein, der den Zweck des benutzerdefinierten Aufbewahrungstags erläutert. 

3. Klicken Sie auf **"Speichern",** um das benutzerdefinierte RPT für den Ordner "Gelöschte Elemente" zu erstellen.

    Das neue RPT wird in der Liste der Aufbewahrungstags angezeigt.

## <a name="step-3-create-a-new-retention-policy"></a>Schritt 3: Erstellen einer neuen Aufbewahrungsrichtlinie

Nachdem Sie die benutzerdefinierten Aufbewahrungstags erstellt haben, besteht der nächste Schritt darin, eine neue Aufbewahrungsrichtlinie zu erstellen und die Aufbewahrungstags hinzuzufügen. Sie fügen die drei benutzerdefinierten Aufbewahrungstags, die Sie in Schritt 2 erstellt haben, und die integrierten Tags hinzu, die im ersten Abschnitt erwähnt wurden. In Schritt 4 weisen Sie diese neue Aufbewahrungsrichtlinie Benutzerpostfächern zu.
  
1. Wechseln Sie im EAC zu Aufbewahrungsrichtlinien für die **Complianceverwaltung.**  >  

2. Klicken Sie auf der Seite **"Aufbewahrungsrichtlinien"** auf das Symbol **"Neu"** ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) .

3. Geben Sie im **Feld "Name"** einen Namen für die neue Aufbewahrungsrichtlinie ein. Beispielsweise die Richtlinie zum **Archivieren und Löschen des Hauses**.

4. Klicken Sie unter **"Aufbewahrungstags"** auf das Symbol "Neu  ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) hinzufügen".

    Eine Liste der Aufbewahrungstags in Ihrer Organisation wird angezeigt. Beachten Sie, dass die benutzerdefinierten Tags, die Sie in Schritt 2 erstellt haben, angezeigt werden.

5. Fügen Sie die 9 Aufbewahrungstags hinzu, die im folgenden Screenshot hervorgehoben sind (diese Tags werden im Abschnitt ["Weitere Informationen"](#more-information) ausführlicher beschrieben). Um ein Aufbewahrungstag hinzuzufügen, wählen Sie es aus, und klicken Sie dann auf **Hinzufügen**.

    ![Hinzufügen von Aufbewahrungstags zur neuen Aufbewahrungsrichtlinie](../media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > Sie können mehrere Aufbewahrungstags auswählen, indem Sie die **STRG-TASTE** gedrückt halten und dann auf jedes Tag klicken. 
  
6. Nachdem Sie die Aufbewahrungstags hinzugefügt haben, klicken Sie auf **OK**.

7. Klicken Sie auf der Seite **"Neue Aufbewahrungsrichtlinie"** auf **"Speichern",** um die neue Richtlinie zu erstellen.

    Die neue Aufbewahrungsrichtlinie wird in der Liste angezeigt. Wählen Sie ihn aus, um die mit ihm verknüpften Aufbewahrungstags im Detailbereich anzuzeigen.

    ![Die neue Aufbewahrungsrichtlinie und die Liste der verknüpften Aufbewahrungstags](../media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a>Schritt 4: Zuweisen der neuen Aufbewahrungsrichtlinie zu Benutzerpostfächern

Wenn ein neues Postfach erstellt wird, wird ihm standardmäßig eine Aufbewahrungsrichtlinie mit dem Namen "MrM-Standardrichtlinie" zugewiesen. In diesem Schritt ersetzen Sie diese Aufbewahrungsrichtlinie (da einem Postfach nur eine Aufbewahrungsrichtlinie zugewiesen werden kann), indem Sie die neue Aufbewahrungsrichtlinie, die Sie in Schritt 3 erstellt haben, den Benutzerpostfächern in Ihrer Organisation zuweisen. Bei diesem Schritt wird davon ausgegangen, dass Sie die neue Richtlinie allen Postfächern in Ihrer Organisation zuweisen.
  
1. Wechseln Sie im EAC zu   >  **"Empfängerpostfächer".**

    Eine Liste aller Benutzerpostfächer in Ihrer Organisation wird angezeigt.

2. Wählen Sie alle Postfächer aus, indem Sie auf das erste In der Liste klicken, die **UMSCHALTTASTE** gedrückt halten und dann auf das letzte Postfach in der Liste klicken. 

3. Klicken Sie im Detailbereich auf der rechten Seite des EAC unter **"Massenbearbeitung"** auf **weitere Optionen.**

4. Klicken Sie unter **Aufbewahrungsrichtlinie** auf **Aktualisieren**.

5. Wählen Sie auf der Seite **"Massenzuweisung von Aufbewahrungsrichtlinien"** in der Dropdownliste **"Aufbewahrungsrichtlinie auswählen"** die Aufbewahrungsrichtlinie aus, die Sie in Schritt 3 erstellt haben. Beispiel: **Archiv- und Aufbewahrungsrichtlinie** für Das Archiv und die Aufbewahrungsrichtlinie .

6. Klicken Sie auf **"Speichern",** um die neue Aufbewahrungsrichtlinienzuweisung zu speichern.

7. Um zu überprüfen, ob die neue Aufbewahrungsrichtlinie Postfächern zugewiesen wurde, können Sie folgendermaßen vorgehen:

   1. Wählen Sie auf der Seite **"Postfächer"** ein Postfach aus, und klicken Sie dann auf  ![ ](../media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png) Bearbeiten.

   2. Klicken Sie auf der Seite "Postfacheigenschaften" für den ausgewählten Benutzer auf **"Postfachfeatures".**

   Der Name der neuen Richtlinie, die dem Postfach zugewiesen ist, wird in der Dropdownliste für **Aufbewahrungsrichtlinien** angezeigt.

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a>(Optional) Schritt 5: Ausführen des Assistenten für verwaltete Ordner zum Anwenden der neuen Einstellungen

Nachdem Sie die neue Aufbewahrungsrichtlinie in Schritt 4 auf Postfächer angewendet haben, kann es bis zu 7 Tage in Exchange Online dauern, bis die neuen Aufbewahrungseinstellungen auf die Postfächer angewendet werden. Der Grund dafür ist, dass ein Prozess, der als Assistent für verwaltete Ordner bezeichnet *wird,* Postfächer mindestens einmal alle 7 Tage verarbeitet. Anstatt auf die Ausführung des Assistenten für verwaltete Ordner zu warten, können Sie dies erzwingen, indem Sie das Cmdlet **"Start-ManagedFolderAssistant"** in Exchange Online PowerShell ausführen.

 **Was geschieht, wenn Sie den Assistenten für verwaltete Ordner ausführen?** Es wendet die Einstellungen in der Aufbewahrungsrichtlinie an, indem Elemente im Postfach überprüft und ermittelt wird, ob sie der Aufbewahrung unterliegen. Anschließend stempelt es Elemente, die der Aufbewahrung unterliegen, mit dem entsprechenden Aufbewahrungstag und führt dann die angegebene Aufbewahrungsaktion für Elemente aus, die über das Aufbewahrungsalter hinausgeht.
  
Führen Sie die folgenden Schritte aus, um eine Verbindung mit Exchange Online PowerShell herzustellen und dann den Assistenten für verwaltete Ordner für jedes Postfach in Ihrer Organisation auszuführen.

1. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](/powershell/exchange/connect-to-exchange-online-powershell).
  
2. Führen Sie die folgenden beiden Befehle aus, um den Assistenten für verwaltete Ordner für alle Benutzerpostfächer in Ihrer Organisation zu starten.

    ```powershell
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```powershell
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

Das ist alles. Sie haben eine Archivierungs- und Löschrichtlinie für die Organisation "Dataset House" eingerichtet.

> [!NOTE]
> Wie bereits erwähnt, verarbeitet der Assistent für verwaltete Ordner Postfächer mindestens einmal alle 7 Tage. Es ist also möglich, dass ein Postfach häufiger vom Assistenten für verwaltete Ordner verarbeitet werden kann. Außerdem können Administratoren nicht prognostizieren, wenn ein Postfach das nächste Mal vom Assistenten für verwaltete Ordner verarbeitet wird. Dies ist ein Grund, warum Sie es möglicherweise manuell ausführen möchten. Wenn Sie jedoch vorübergehend verhindern möchten, dass der Assistent für verwaltete Ordner die neuen Aufbewahrungseinstellungen auf ein Postfach anwendet, können Sie den Befehl ausführen, `Set-Mailbox -ElcProcessingDisabled $true` um den Assistenten für verwaltete Ordner vorübergehend von der Verarbeitung eines Postfachs zu deaktivieren. Führen Sie den Befehl aus, um den Assistenten für verwaltete Ordner für ein Postfach erneut zu `Set-Mailbox -ElcProcessingDisabled $false` aktivieren. Wenn ein Postfachbenutzer über ein deaktiviertes Konto verfügt, verarbeiten wir die Verschiebungselemente nicht, um die Archivaktion für dieses Postfach zu archivieren.
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a>(Optional) Schritt 6: Festlegen der neuen Aufbewahrungsrichtlinie als Standard für Ihre Organisation

In Schritt 4 müssen Sie die neue Aufbewahrungsrichtlinie vorhandenen Postfächern zuweisen. Sie können jedoch Exchange Online so konfigurieren, dass die neue Aufbewahrungsrichtlinie neuen Postfächern zugewiesen wird, die in Zukunft erstellt werden. Verwenden Sie dazu Exchange Online PowerShell, um den Standardpostfachplan Ihrer Organisation zu aktualisieren. Ein *Postfachplan* ist eine Vorlage, die Eigenschaften für neue Postfächer automatisch konfiguriert.  In diesem optionalen Schritt können Sie die aktuelle Aufbewahrungsrichtlinie, die dem Postfachplan zugewiesen ist (standardmäßig die Standard-MRM-Richtlinie), durch die Aufbewahrungsrichtlinie ersetzen, die Sie in Schritt 3 erstellt haben. Nachdem Sie den Postfachplan aktualisiert haben, wird die neue Aufbewahrungsrichtlinie neuen Postfächern zugewiesen.

1. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie den folgenden Befehl aus, um Informationen zu den Postfachplänen in Ihrer Organisation anzuzeigen.

    ```powershell
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```

    Beachten Sie den Postfachplan, der als Standard festgelegt ist.

3. Führen Sie den folgenden Befehl aus, um die neue Aufbewahrungsrichtlinie, die Sie in Schritt 3 erstellt haben (z. **B. Archiv- und Aufbewahrungsrichtlinie),** dem Standardpostfachplan zuzuweisen. In diesem Beispiel wird davon ausgegangen, dass der Name des Standardpostfachplans **ExchangeOnlineEnterprise** lautet.

    ```powershell
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```

4. Sie können den Befehl in Schritt 2 erneut ausführen, um zu überprüfen, ob die dem Standardpostfachplan zugewiesene Aufbewahrungsrichtlinie geändert wurde.

## <a name="more-information"></a>Weitere Informationen

- Wie wird das Aufbewahrungsalter berechnet? Das Aufbewahrungsalter von Postfachelementen wird ab dem Datum der Zustellung oder dem Erstellungsdatum für Elemente wie Entwurfsnachrichten berechnet, die nicht gesendet, aber vom Benutzer erstellt werden. Wenn der Assistent für verwaltete Ordner Elemente in einem Postfach verarbeitet, werden alle Elemente, die Aufbewahrungstags mit der Aufbewahrungsaktion Löschen und Wiederherstellung zulassen oder Endgültig löschen aufweisen, mit einem Start- und einem Ablaufdatum gestempelt. Elemente mit einem Archivtag werden mit einem Verschiebungsdatum gestempelt. 

- Die folgende Tabelle enthält weitere Informationen zu jedem Aufbewahrungstag, das der benutzerdefinierten Aufbewahrungsrichtlinie hinzugefügt wird, die durch Ausführen der Schritte in diesem Thema erstellt wurde.

    | Aufbewahrungstag | Funktion dieses Tags | Integriert oder benutzerdefiniert? | Typ |
    |:-----|:-----|:-----|:-----|
    |Alpine House 3 Year Move to Archive  <br/> |Verschiebt Elemente, die 1095 Tage (3 Jahre) alt sind, in das Archivpostfach.  <br/> |Benutzerdefiniert (siehe [Schritt 2: Erstellen neuer Aufbewahrungstags für die Archiv- und Löschrichtlinien)](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)  <br/> |Standardrichtlinientag (Archiv); Dieses Tag wird automatisch auf das gesamte Postfach angewendet.  <br/> |
    |7.000Er-Haus endgültig löschen  <br/> |Löscht Elemente im primären Postfach oder im Archivpostfach dauerhaft, wenn sie 7 Jahre alt sind.  <br/> |Benutzerdefiniert (siehe [Schritt 2: Erstellen neuer Aufbewahrungstags für die Archiv- und Löschrichtlinien)](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)  <br/> |Standardrichtlinientag (Löschung); Dieses Tag wird automatisch auf das gesamte Postfach angewendet.  <br/> |
    |Gelöschte Elemente 5 Jahre Löschen und Wiederherstellung zulassen  <br/> |Löscht Elemente aus dem Ordner "Gelöschte Elemente", die 5 Jahre alt sind. Benutzer können diese Elemente bis zu 14 Tage lang wiederherstellen, nachdem sie gelöscht wurden.<sup>\*</sup> <br/> |Benutzerdefiniert (siehe [Schritt 2: Erstellen neuer Aufbewahrungstags für die Archiv- und Löschrichtlinien)](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)  <br/> |Aufbewahrungsrichtlinientag (gelöschte Elemente); Dieses Tag wird automatisch auf Elemente im Ordner "Gelöschte Elemente" angewendet.  <br/> |
    |Wiederherstellbare Elemente 14 Tage Nach Archiv verschieben  <br/> |Verschiebt Elemente, die sich seit 14 Tagen im Ordner "Wiederherstellbare Elemente" befinden, in den Ordner "Wiederherstellbare Elemente" im Archivpostfach.  <br/> |Integriert  <br/> |Aufbewahrungsrichtlinientag (wiederherstellbare Elemente); Dieses Tag wird automatisch auf Elemente im Ordner "Wiederherstellbare Elemente" angewendet.  <br/> |
    |Junk-E-Mail  <br/> |Löscht Elemente, die sich 30 Tage lang im Junk-E-Mail-Ordner befinden, dauerhaft. Benutzer können diese Elemente bis zu 14 Tage lang wiederherstellen, nachdem sie gelöscht wurden.<sup>\*</sup> <br/> |Integriert  <br/> |Aufbewahrungsrichtlinientag (Junk-E-Mail); Dieses Tag wird automatisch auf Elemente im Junk-E-Mail-Ordner angewendet.  <br/> |
    |1 Monat, löschen  <br/> |Löscht Elemente, die 30 Tage alt sind, dauerhaft. Benutzer können diese Elemente bis zu 14 Tage lang wiederherstellen, nachdem sie gelöscht wurden.<sup>\*</sup> <br/> |Integriert  <br/> |Persönlich; Dieses Tag kann von Benutzern angewendet werden.  <br/> |
    |1 Jahr, löschen  <br/> |Löscht Elemente, die 365 Tage alt sind, dauerhaft. Benutzer können diese Elemente bis zu 14 Tage lang wiederherstellen, nachdem sie gelöscht wurden.<sup>\*</sup> <br/> |Integriert  <br/> |Persönlich; Dieses Tag kann von Benutzern angewendet werden.  <br/> |
    |Nie löschen  <br/> |Dieses Tag verhindert, dass Elemente durch eine Aufbewahrungsrichtlinie gelöscht werden.  <br/> |Integriert  <br/> |Persönlich; Dieses Tag kann von Benutzern angewendet werden.  <br/> |
    |Persönlich, 1 Jahre, in Archiv verschieben  <br/> |Verschiebt Elemente nach 1 Jahr in das Archivpostfach.  <br/> |Integriert  <br/> |Persönlich; Dieses Tag kann von Benutzern angewendet werden.  <br/> |

    > <sup>\*</sup>Benutzer können das Tool "Gelöschte Elemente wiederherstellen" in Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) verwenden, um ein gelöschtes Element innerhalb des Aufbewahrungszeitraums für gelöschte Elemente wiederherzustellen, der standardmäßig 14 Tage in Exchange Online beträgt. Ein Administrator kann Windows PowerShell verwenden, um den Aufbewahrungszeitraum für gelöschte Elemente auf maximal 30 Tage zu erhöhen. Weitere Informationen finden Sie unter: [Wiederherstellen gelöschter Elemente in Outlook für Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) und Ändern des [Aufbewahrungszeitraums für gelöschte Elemente für ein Postfach in Exchange Online](/exchange/recipients-in-exchange-online/manage-user-mailboxes/change-deleted-item-retention)
  
- Mithilfe des Aufbewahrungstags **"Wiederherstellbare Elemente 14 Tage Verschieben in Archiv"** können Sie Speicherplatz im Ordner "Wiederherstellbare Elemente" im primären Postfach des Benutzers freigeben. Dies ist nützlich, wenn das Postfach eines Benutzers in die Warteschleife versetzt wird, was bedeutet, dass das Postfach des Benutzers nie endgültig gelöscht wird. Ohne Verschieben von Elementen in das Archivpostfach ist es möglich, dass das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" im primären Postfach erreicht wird. Weitere Informationen hierzu und wie Sie dies vermeiden können, finden Sie unter [Erhöhen des Kontingents für wiederherstellbare Elemente für postfächer, die in der Warteschleife sind.](./increase-the-recoverable-quota-for-mailboxes-on-hold.md)
