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
description: In diesem Artikel erfahren Sie, wie Sie eine Archivierungs-und Löschrichtlinie in Microsoft 365 erstellen, mit der Elemente automatisch in das Archivpostfach eines Benutzers verschoben werden.
ms.openlocfilehash: 5e8675c1cc6e1df4c22e55648e1655798bae5e5b
ms.sourcegitcommit: 21b0ea5715e20b4ab13719eb18c97fadb49b563d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49624777"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-organization"></a>Einrichten einer Archivierungs- und Löschrichtlinie für Postfächer in Ihrer Organisation

In Microsoft 365 können Administratoren eine Archivierungs-und Löschrichtlinie erstellen, die Elemente automatisch in das Archivpostfach eines Benutzers verschiebt und Elemente automatisch aus dem Postfach löscht. Der Administrator erstellt eine Aufbewahrungsrichtlinie, die Postfächern zugewiesen ist, und verschiebt Elemente nach einem bestimmten Zeitraum in das Archivpostfach eines Benutzers und löscht außerdem Elemente aus dem Postfach, nachdem Sie eine bestimmte Verfallszeit erreicht haben. Die tatsächlichen Regeln, die bestimmen, welche Elemente verschoben oder gelöscht werden, und wenn dies geschieht, werden als Aufbewahrungstags bezeichnet. Aufbewahrungstags sind mit einer Aufbewahrungsrichtlinie verknüpft, die wiederum dem Postfach eines Benutzers zugewiesen ist. Ein Aufbewahrungs Tag wendet Aufbewahrungseinstellungen auf einzelne Nachrichten und Ordner im Postfach eines Benutzers an. Es definiert, wie lange eine Nachricht im Postfach verbleibt und welche Aktion ausgeführt wird, wenn die Nachricht das angegebene Beibehaltungsalter erreicht. Wenn eine Nachricht das Aufbewahrungs Alter erreicht, wird Sie entweder in das Archivpostfach des Benutzers verschoben oder gelöscht.
  
In den Schritten in diesem Artikel wird eine Archivierungs-und Aufbewahrungsrichtlinie für eine fiktive Organisation namens "Alpine House" eingerichtet. Das Einrichten dieser Richtlinie umfasst die folgenden Aufgaben:
  
- Aktivieren eines Archivpostfachs für jeden Benutzer in der Organisation. Dadurch erhalten die Benutzer zusätzlichen Postfachspeicher und sind erforderlich, damit eine Aufbewahrungsrichtlinie Elemente in das Archivpostfach umlagern kann. Außerdem können benutzerarchiv Informationen speichern, indem Sie Elemente in Ihr Archivpostfach verschieben.

- Erstellen von drei benutzerdefinierten Aufbewahrungstags, die die folgenden Aktionen ausführen:

  - Verschiebt Elemente, die älter als drei Jahre sind, automatisch in das Archivpostfach des Benutzers. Durch das Verschieben von Elementen in das Archivpostfach wird Speicherplatz im primären Postfach eines Benutzers freigegeben.

  - Elemente, die älter als fünf Jahre sind, werden automatisch aus dem Ordner "Gelöschte Elemente" gelöscht. Dadurch wird auch Speicherplatz im primären Postfach des Benutzers freigegeben. Benutzer haben die Möglichkeit, diese Elemente bei Bedarf wiederherzustellen. Weitere Informationen finden Sie in der Fußnote im Abschnitt [Weitere Informationen](#more-information) . 

  - Löscht automatisch (und dauerhaft) Elemente, die älter als 7 Jahre sind, sowohl aus dem primären als auch aus dem Archivpostfach. Aufgrund von Compliance-Vorschriften müssen einige Organisationen e-Mails für einen bestimmten Zeitraum aufbewahren. Nach Ablauf dieses Zeitraums möchte eine Organisation möglicherweise diese Elemente Benutzerpostfächer endgültig entfernen.

- Erstellen einer neuen Aufbewahrungsrichtlinie und Hinzufügen der neuen benutzerdefinierten Aufbewahrungstags. Darüber hinaus fügen Sie der neuen Aufbewahrungsrichtlinie auch integrierte Aufbewahrungstags hinzu. Dies umfasst persönliche Tags, die Benutzer Elementen in Ihrem Postfach zuweisen können. Sie fügen außerdem ein Aufbewahrungs hinzu, mit dem Elemente aus dem Ordner "Wiederherstellbare Elemente" im primären Postfach des Benutzers in den Ordner "Wiederherstellbare Elemente" im Archivpostfach verschoben werden. Auf diese Weise können Sie Speicherplatz im Ordner "Wiederherstellbare Elemente" eines Benutzers freigeben, wenn das Postfach in der Warteschleife abgelegt wird.

Sie können einige oder alle Schritte in diesem Artikel befolgen, um eine Archivierungs-und Löschrichtlinie für Postfächer in ihrer eigenen Organisation einzurichten. Es wird empfohlen, diesen Prozess auf einigen Postfächern zu testen, bevor er für alle Postfächer in Ihrer Organisation implementiert wird.
  
## <a name="before-you-set-up-an-archive-and-deletion-policy"></a>Bevor Sie eine Richtlinie zum Archivieren und löschen einrichten

- Sie müssen ein globaler Administrator in Ihrer Organisation sein, um die Schritte in diesem Thema ausführen zu können. 

- Wenn Sie ein neues Benutzerkonto erstellen und dem Benutzer eine Exchange Online Lizenz zuweisen, wird automatisch ein Postfach für den Benutzer erstellt. Wenn das Postfach erstellt wird, wird ihm automatisch eine standardmäßige Aufbewahrungsrichtlinie zugewiesen, die als Standard-MRM-Richtlinie bezeichnet wird. In diesem Artikel erstellen Sie eine neue Aufbewahrungsrichtlinie und weisen diese dann den Benutzerpostfächern zu, wobei die standardmäßige MRM-Richtlinie ersetzt wird. Einem Postfach kann jeweils nur eine Aufbewahrungsrichtlinie zugewiesen sein.

- Weitere Informationen zu Aufbewahrungstags und Aufbewahrungsrichtlinien in Exchange Online finden Sie unter [Aufbewahrungstags und Aufbewahrungsrichtlinien](https://go.microsoft.com/fwlink/p/?LinkId=404424).

## <a name="step-1-enable-archive-mailboxes-for-users"></a>Schritt 1: Aktivieren von archivpostfächern für Benutzer

Der erste Schritt besteht darin, das Archivpostfach für jeden Benutzer in Ihrer Organisation zu aktivieren. Das Archivpostfach eines Benutzers muss aktiviert sein, damit ein Aufbewahrungs mit der Aufbewahrungsaktion "in Archiv verlagern" das Element nach Ablauf des Aufbewahrungs Zeitalters verlegen kann.
  
> [!NOTE]
> Sie können Archivpostfächer jederzeit während dieses Prozesses aktivieren, solange Sie erst an einem bestimmten Zeitpunkt aktiviert sind, bevor Sie den Vorgang abschließen. Wenn ein Archivpostfach nicht aktiviert ist, wird keine Aktion für Elemente ausgeführt, denen eine Archivierungs-oder Löschrichtlinie zugewiesen ist.
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).

2. Melden Sie sich mit ihrem globalen Administratorkonto an.
    
3. Wechseln Sie im Security & Compliance Center zu **Information Governance** \> **Archive**.

    Eine Liste der Postfächer in Ihrer Organisation wird angezeigt und ob das entsprechende Archivpostfach aktiviert oder deaktiviert ist.

4. Wählen Sie alle Postfächer aus, indem Sie auf die erste in der Liste klicken, die **UMSCHALT** Taste gedrückt halten und dann auf die letzte in der Liste klicken.

    > [!TIP]
    > Bei diesem Schritt wird davon ausgegangen, dass keine Archivpostfächer aktiviert sind. Wenn Sie über Postfächer verfügen, bei denen das Archiv aktiviert ist, halten Sie die **STRG** -Taste gedrückt, und klicken Sie auf jedes Postfach, das über ein deaktiviertes Archivpostfach verfügt. Sie können auch auf die Spaltenüberschrift **archivieren** klicken, um die Zeilen zu sortieren, je nachdem, ob das Archivpostfach aktiviert oder deaktiviert ist, um die Auswahl von Postfächern zu vereinfachen.
  
5. Klicken Sie im Detailbereich unter **Massenbearbeitung** auf **aktivieren**.

    Es wird eine Warnung angezeigt, die besagt, dass Elemente, die älter als zwei Jahre sind, in das neue Archivpostfach verschoben werden. Dies liegt daran, dass die standardmäßige Aufbewahrungsrichtlinie, der ein neues Benutzerpostfach bei ihrer Erstellung zugewiesen wurde, ein Standardrichtlinientag Archiv mit einem Aufbewahrungs Alter von 2 Jahren aufweist. Das Standardrichtlinientag für das benutzerdefinierte Archiv, das Sie in Schritt 2 erstellen, hat ein Aufbewahrungs Alter von drei Jahren. Das bedeutet, dass Elemente, die 3 Jahre oder älter sind, in das Archivpostfach verschoben werden.

6. Klicken Sie auf **Ja** , um die Warnmeldung zu schließen, und starten Sie den Vorgang, um das Archivpostfach für jedes ausgewählte Postfach zu aktivieren.

7. Wenn der Prozess abgeschlossen ist, klicken **Sie auf Aktualisierung aktualisieren** ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) , um die Liste auf der **Archiv** Seite zu aktualisieren.

    Das Archivpostfach ist für alle Benutzer in Ihrer Organisation aktiviert.

    ![Die Liste der Postfächer, für die das Archivpostfach aktiviert ist.](../media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)

## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a>Schritt 2: Erstellen neuer Aufbewahrungstags für die Archiv-und Löschrichtlinien

In diesem Schritt erstellen Sie die drei benutzerdefinierten Aufbewahrungstags, die zuvor beschrieben wurden.
  
- Alpine House 3 Jahre Umstellung auf Archiv (benutzerdefinierte Archivrichtlinie)

- Alpine House 7 Jahre dauerhaft löschen (Richtlinie für benutzerdefinierte Löschung)

- Alpine House gelöschte Elemente 5 Jahre löschen und Wiederherstellen zulassen (benutzerdefiniertes Tag für den Ordner "Gelöschte Elemente")

Um neue Aufbewahrungstags zu erstellen, verwenden Sie das Exchange Admin Center (EAC) in Ihrer Exchange Online Organisation. Stellen Sie sicher, dass Sie die klassische Version der Exchange-Verwaltungskonsole verwenden.
  
1. Wechseln Sie zu, [https://admin.protection.outlook.com/ecp/](https://admin.protection.outlook.com/ecp/) und melden Sie sich mit Ihren Anmeldeinformationen an.
  
2. Wechseln Sie in der Exchange- **Verwaltungs** Konsole zu Compliance-Management-  >  **Aufbewahrungstags**

    Eine Liste der Aufbewahrungstags für Ihre Organisation wird angezeigt.

### <a name="create-a-custom-archive-default-policy-tag"></a>Erstellen eines Standardrichtlinientags für ein benutzerdefiniertes Archiv
  
Zunächst erstellen Sie ein Standardrichtlinientag für ein benutzerdefiniertes Archiv, mit dem Elemente nach drei Jahren in das Archivpostfach übertragen werden.
  
1. Klicken Sie auf der Seite **Aufbewahrungstags** auf neues Symbol für **neue Tags** ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) , und wählen Sie dann **automatisch auf gesamtes Postfach angewendet (Standard)** aus.

2. Füllen Sie auf der Seite **Neues Tag wird automatisch auf gesamtes Postfach angewendet (Standard)** die folgenden Felder aus: 

    ![Einstellungen zum Erstellen eines neuen Standardrichtlinientags für das Archiv](../media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
   1. **Name** Geben Sie einen Namen für das neue Aufbewahrungs Tag ein. 

   2. **Aufbewahrungsaktion** Wählen Sie **in Archiv umsteigen** aus, um Elemente nach Ablauf des Aufbewahrungszeitraums in das Archivpostfach zu übertragen.

   3. **Aufbewahrungszeitraum** Wählen Sie aus, **wann das Element das folgende Alter (in Tagen) erreicht**, und geben Sie dann die Dauer des Aufbewahrungszeitraums ein. In diesem Szenario werden Elemente nach 1095 Tagen (3 Jahren) in das Archivpostfach verschoben.

   4. **Comment** (optional) geben Sie einen Kommentar ein, der den Zweck des benutzerdefinierten Aufbewahrungstags erläutert.

3. Klicken Sie auf **Speichern** , um das benutzerdefinierte Archiv-richtlinientag zu erstellen.

    Das neue Archiv-Standardrichtlinientag wird in der Liste der Aufbewahrungstags angezeigt.

### <a name="create-a-custom-deletion-default-policy-tag"></a>Erstellen eines Standardrichtlinientags für ein benutzerdefiniertes löschen
  
Als Nächstes erstellen Sie ein weiteres benutzerdefiniertes Standardrichtlinientag, wobei es sich dabei um eine Löschrichtlinie handelt, die Elemente nach 7 Jahren endgültig löscht.
  
1. Klicken Sie auf der Seite **Aufbewahrungstags** auf neues Symbol für **neue Tags** ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) , und wählen Sie dann **automatisch auf gesamtes Postfach angewendet (Standard)** aus.

2. Füllen Sie auf der Seite **Neues Tag wird automatisch auf gesamtes Postfach angewendet (Standard)** die folgenden Felder aus: 

    ![Einstellungen zum Erstellen eines neuen Standardrichtlinientags für das Löschen](../media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
   1. **Name** Geben Sie einen Namen für das neue Aufbewahrungs Tag ein. 

   2. **Aufbewahrungsaktion** Wählen Sie **dauerhaft löschen** aus, um Elemente aus dem Postfach zu bereinigen, wenn der Aufbewahrungszeitraum abgelaufen ist.

   3. **Aufbewahrungszeitraum** Wählen Sie aus, **wann das Element das folgende Alter (in Tagen) erreicht**, und geben Sie dann die Dauer des Aufbewahrungszeitraums ein. In diesem Szenario werden Elemente nach 2555 Tagen (7 Jahre) gelöscht.

   4. **Comment** (optional) geben Sie einen Kommentar ein, der den Zweck des benutzerdefinierten Aufbewahrungstags erläutert. 

3. Klicken Sie auf **Speichern** , um den benutzerdefinierten Löschungs richtlinientag zu erstellen. 

    Das neue Lösch richtlinientag wird in der Liste der Aufbewahrungstags angezeigt.

### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a>Erstellen eines benutzerdefinierten Aufbewahrungsrichtlinientags für den Ordner "Gelöschte Elemente"
  
Das letzte Aufbewahrungs-Tag, das Sie erstellen, ist ein benutzerdefiniertes Aufbewahrungsrichtlinientag (rpt) für den Ordner "Gelöschte Elemente". Mit diesem Tag werden Elemente im Ordner "Gelöschte Elemente" nach 5 Jahren gelöscht, und es wird ein Wiederherstellungszeitraum bereitgestellt, wenn Benutzer das Tool zum Wiederherstellen von gelöschten Elementen zum Wiederherstellen eines Elements verwenden können.
  
1. Klicken Sie auf der Seite **Aufbewahrungstags** auf neues Symbol für **neue Tags** ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) , und wählen Sie dann **automatisch auf einen Standardordner angewendet** aus.

2. Füllen Sie auf der Seite **Neues, automatisch auf eine Standardordner angewendetes Tag** die folgenden Felder aus:

    ![Einstellungen zum Erstellen eines neuen Aufbewahrungsrichtlinientags für den Ordner "Gelöschte Elemente"](../media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
   1. **Name** Geben Sie einen Namen für das neue Aufbewahrungs Tag ein. 

   2. **Dieses Tag auf den folgenden Standardordner anwenden** Wählen Sie in der Dropdownliste **Gelöschte Elemente** aus.

   3. **Aufbewahrungsaktion** Wählen Sie DELETE aus, **und ermöglichen Sie die Wiederherstellung** zum Löschen von Elementen, wenn der Aufbewahrungszeitraum abgelaufen ist, aber Benutzern ermöglichen, ein gelöschtes Element innerhalb des Aufbewahrungszeitraums für gelöschte Elemente wiederherzustellen (standardmäßig 14 Tage).

   4. **Aufbewahrungszeitraum** Wählen Sie aus, **wann das Element das folgende Alter (in Tagen) erreicht**, und geben Sie dann die Dauer des Aufbewahrungszeitraums ein. In diesem Szenario werden Elemente nach 1825 Tagen (5 Jahre) gelöscht.

   5. **Comment** (optional) geben Sie einen Kommentar ein, der den Zweck des benutzerdefinierten Aufbewahrungstags erläutert. 

3. Klicken Sie auf **Speichern** , um die benutzerdefinierte RPT für den Ordner Gelöschte Elemente zu erstellen.

    Die neue RPT wird in der Liste der Aufbewahrungstags angezeigt.

## <a name="step-3-create-a-new-retention-policy"></a>Schritt 3: Erstellen einer neuen Aufbewahrungsrichtlinie

Nachdem Sie die benutzerdefinierten Aufbewahrungstags erstellt haben, besteht der nächste Schritt darin, eine neue Aufbewahrungsrichtlinie zu erstellen und die Aufbewahrungstags hinzuzufügen. Sie fügen die drei benutzerdefinierten Aufbewahrungstags hinzu, die Sie in Schritt 2 erstellt haben, sowie die integrierten Tags, die im ersten Abschnitt erwähnt wurden. In Schritt 4 weisen Sie diese neue Aufbewahrungsrichtlinie den Benutzerpostfächern zu.
  
1. Wechseln Sie in der Exchange- **Verwaltungskonsole zu Compliance Management**  >  **Retention Policies**.

2. Klicken Sie auf der Seite **Aufbewahrungsrichtlinien** auf **Neues** ![ Neues Symbol ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) .

3. Geben Sie im Feld **Name** einen Namen für die neue Aufbewahrungsrichtlinie ein. Beispiel: **Alpine House-Archiv-und Löschrichtlinie**.

4. Klicken Sie unter **Aufbewahrungstags** auf neues Symbol **Hinzufügen** ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) .

    Eine Liste der Aufbewahrungstags in Ihrer Organisation wird angezeigt. Hinweis die benutzerdefinierten Tags, die Sie in Schritt 2 erstellt haben, werden angezeigt.

5. Fügen Sie die 9 Aufbewahrungstags hinzu, die im folgenden Screenshot hervorgehoben sind (diese Tags werden im Abschnitt [Weitere Informationen](#more-information) ausführlicher beschrieben). Wählen Sie zum Hinzufügen eines Aufbewahrungstags die Option aus, und klicken Sie dann auf **Hinzufügen**.

    ![Hinzufügen von Aufbewahrungstags zur neuen Aufbewahrungsrichtlinie](../media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > Sie können mehrere Aufbewahrungstags auswählen, indem Sie die **STRG** -Taste gedrückt halten und dann auf die einzelnen Tags klicken. 
  
6. Nachdem Sie die Aufbewahrungstags hinzugefügt haben, klicken Sie auf **OK**.

7. Klicken Sie auf der Seite **neue Aufbewahrungsrichtlinie** auf **Speichern** , um die neue Richtlinie zu erstellen.

    Die neue Aufbewahrungsrichtlinie wird in der Liste angezeigt. Wählen Sie diese Option aus, um die im Detailbereich verknüpften Aufbewahrungstags anzuzeigen.

    ![Die neue Aufbewahrungsrichtlinie und die Liste der verknüpften Aufbewahrungstags](../media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a>Schritt 4: Zuweisen der neuen Aufbewahrungsrichtlinie zu Benutzerpostfächern

Wenn ein neues Postfach erstellt wird, wird es standardmäßig einer Aufbewahrungsrichtlinie mit dem Namen "MRM-Richtlinie" zugewiesen. In diesem Schritt ersetzen Sie diese Aufbewahrungsrichtlinie (da einem Postfach nur eine Aufbewahrungsrichtlinie zugewiesen werden kann), indem Sie die neue Aufbewahrungsrichtlinie, die Sie in Schritt 3 erstellt haben, den Benutzerpostfächern in Ihrer Organisation zuweisen. Bei diesem Schritt wird davon ausgegangen, dass Sie die neue Richtlinie allen Postfächern in Ihrer Organisation zuweisen.
  
1. Wechseln Sie in der Exchange-Verwaltungskonsole zu **Empfänger**  >  **Postfächer**.

    Es wird eine Liste aller Benutzerpostfächer in Ihrer Organisation angezeigt.

2. Wählen Sie alle Postfächer aus, indem Sie auf die erste in der Liste klicken, die **UMSCHALT** Taste gedrückt halten und dann auf die letzte in der Liste klicken. 

3. Klicken Sie im Detailbereich auf der rechten Seite der Exchange-Verwaltungskonsole unter **Massenbearbeitung** auf **Weitere Optionen**.

4. Klicken Sie unter **Aufbewahrungsrichtlinie** auf **Aktualisieren**.

5. Wählen Sie auf der Seite **Aufbewahrungsrichtlinie für Massen Zuweisungen** in der Dropdownliste **Wählen Sie die Aufbewahrungsrichtlinie** aus die Aufbewahrungsrichtlinie aus, die Sie in Schritt 3 erstellt haben. Beispiel: **Alpine House Archive und Aufbewahrungsrichtlinie**.

6. Klicken Sie auf **Speichern** , um die neue Aufbewahrungsrichtlinien Zuweisung zu speichern.

7. Gehen Sie wie folgt vor, um zu überprüfen, ob die neue Aufbewahrungsrichtlinie Postfächern zugewiesen wurde:

   1. Wählen Sie auf der Seite **Postfächer** ein Postfach aus, **und klicken Sie dann auf bearbeiten bearbeiten** ![ ](../media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png) .

   2. Klicken Sie auf der Seite Postfacheigenschaften für den ausgewählten Benutzer auf **Postfachfunktionen**.

   Der Name der neuen Richtlinie, die dem Postfach zugewiesen ist, wird in der Dropdownliste **Aufbewahrungsrichtlinie** angezeigt.

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a>Optional Schritt 5: Ausführen des Assistenten für verwaltete Ordner zum Anwenden der neuen Einstellungen

Nachdem Sie die neue Aufbewahrungsrichtlinie in Schritt 4 auf Postfächer angewendet haben, kann es bis zu sieben Tage dauern, bis Exchange Online die neuen Aufbewahrungseinstellungen auf die Postfächer angewendet werden. Der Grund ist, dass ein Prozess, der als *Assistent für verwaltete Ordner* bezeichnet wird, Postfächer mindestens einmal alle 7 Tage verarbeitet. Anstatt auf die Ausführung des Assistenten für verwaltete Ordner zu warten, können Sie dies erzwingen, indem Sie das Cmdlet **Start-ManagedFolderAssistant** in Exchange Online PowerShell ausführen.

 **Was geschieht, wenn Sie den Assistenten für verwaltete Ordner ausführen?** Sie wendet die Einstellungen in der Aufbewahrungsrichtlinie an, indem Sie Elemente im Postfach überprüft und ermittelt, ob Sie Aufbewahrungs pflichtig sind. Anschließend werden Elemente, die der Aufbewahrung unterliegen, mit dem entsprechenden Aufbewahrungs versehen, und dann wird die angegebene Aufbewahrungsaktion für Elemente über das Aufbewahrungs Alter zurückgegeben.
  
Hier finden Sie die Schritte zum Herstellen einer Verbindung mit Exchange Online PowerShell, und führen Sie dann den Assistenten für verwaltete Ordner für jedes Postfach in Ihrer Organisation aus.

1. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://go.microsoft.com/fwlink/p/?LinkId=517283).
  
2. Führen Sie die folgenden beiden Befehle aus, um den Assistenten für verwaltete Ordner für alle Benutzerpostfächer in Ihrer Organisation zu starten.

    ```powershell
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```powershell
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

Das ist alles. Sie haben eine Archiv-und Löschrichtlinie für die Alpine House-Organisation eingerichtet.

> [!NOTE]
> Wie bereits erwähnt, verarbeitet der Assistent für verwaltete Ordner Postfächer mindestens einmal alle 7 Tage. Daher ist es möglich, dass ein Postfach häufiger vom Assistenten für verwaltete Ordner verarbeitet werden kann. Administratoren können auch nicht vorhersagen, wann das nächste Mal ein Postfach vom Assistenten für verwaltete Ordner verarbeitet wird, was ein Grund dafür ist, dass Sie es möglicherweise manuell ausführen möchten. Wenn Sie jedoch vorübergehend verhindern möchten, dass der Assistent für verwaltete Ordner die neuen Aufbewahrungseinstellungen auf ein Postfach anwendet, können Sie den Befehl ausführen, `Set-Mailbox -ElcProcessingDisabled $true` um den Assistenten für verwaltete Ordner vorübergehend für die Verarbeitung eines Postfachs zu deaktivieren. Führen Sie den Befehl aus, um den Assistenten für verwaltete Ordner für ein Postfach erneut zu aktivieren `Set-Mailbox -ElcProcessingDisabled $false` . Wenn ein Postfachbenutzer über ein deaktiviertes Konto verfügt, wird die Aktion Elemente in Archiv verlegen für dieses Postfach nicht verarbeitet.
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a>Optional Schritt 6: Festlegen der Standardeinstellung für die neue Aufbewahrungsrichtlinie für Ihre Organisation

In Schritt 4 müssen Sie die neue Aufbewahrungsrichtlinie vorhandenen Postfächern zuweisen. Sie können Exchange Online jedoch so konfigurieren, dass die neue Aufbewahrungsrichtlinie neuen Postfächern zugewiesen wird, die in der Zukunft erstellt werden. Verwenden Sie dazu Exchange Online PowerShell, um den Standard Postfachplan Ihrer Organisation zu aktualisieren. Bei einem *Postfachplan* handelt es sich um eine Vorlage, die automatisch Eigenschaften für neue Postfächer konfiguriert.  In diesem optionalen Schritt können Sie die aktuelle Aufbewahrungsrichtlinie, die dem Postfachplan zugewiesen ist (standardmäßig die standardmäßige MRM-Richtlinie), mit der in Schritt 3 erstellten Aufbewahrungsrichtlinie ersetzen. Nachdem Sie den Postfachplan aktualisiert haben, wird die neue Aufbewahrungsrichtlinie neuen Postfächern zugewiesen.

1. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://go.microsoft.com/fwlink/p/?LinkId=517283).

2. Führen Sie den folgenden Befehl aus, um Informationen zu den Postfachplänen in Ihrer Organisation anzuzeigen.

    ```powershell
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```

    Notieren Sie sich den Postfachplan, der als Standard festgelegt ist.

3. Führen Sie den folgenden Befehl aus, um die neue Aufbewahrungsrichtlinie, die Sie in Schritt 3 (beispielsweise **Alpine House Archive und Aufbewahrungsrichtlinie**) erstellt haben, dem Standard Postfachplan zuzuweisen. In diesem Beispiel wird davon ausgegangen, dass der Name des Standard Postfachplans **exchangeonlineenterprise zurückgegeben** ist.

    ```powershell
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```

4. Sie können den Befehl in Schritt 2 erneut ausführen, um zu überprüfen, ob die der Standardpostfacheinstellungen zugewiesene Aufbewahrungsrichtlinie geändert wurde.

## <a name="more-information"></a>Weitere Informationen

- Wie wird das Aufbewahrungs Alter berechnet? Das Aufbewahrungs Alter von Postfachelementen wird ab dem Zeitpunkt der Zustellung oder dem Erstellungsdatum für Elemente wie Entwurfsnachrichten berechnet, die nicht gesendet, aber vom Benutzer erstellt werden. Wenn der Assistent für verwaltete Ordner Elemente in einem Postfach verarbeitet, werden alle Elemente, die Aufbewahrungstags mit der Aufbewahrungsaktion Löschen und Wiederherstellung zulassen oder Endgültig löschen aufweisen, mit einem Start- und einem Ablaufdatum gestempelt. Elemente mit einem Archiv-Tag werden mit einem Verschiebedatum versehen. 

- In der folgenden Tabelle finden Sie weitere Informationen zu den einzelnen Aufbewahrungstags, die der benutzerdefinierten Aufbewahrungsrichtlinie hinzugefügt werden, die durch Befolgen der Schritte in diesem Thema erstellt wurde.

    | Aufbewahrungstags | Funktionsweise dieses Tags | Integriert oder Benutzerdefiniert? | Typ |
    |:-----|:-----|:-----|:-----|
    |Alpine House 3 Jahre Umstellung auf Archiv  <br/> |Verschiebt Elemente, die 1095 Tage (3 Jahre) alt sind, in das Archivpostfach.  <br/> |Benutzerdefiniert (siehe [Schritt 2: Erstellen neuer Aufbewahrungstags für die Archivierungs-und Löschrichtlinien](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Standardrichtlinientag (Archiv); Dieses Tag wird automatisch auf das gesamte Postfach angewendet.  <br/> |
    |Alpines Haus 7 Jahre dauerhaft löschen  <br/> |Löscht Elemente im primären Postfach oder im Archivpostfach endgültig, wenn Sie 7 Jahre alt sind.  <br/> |Benutzerdefiniert (siehe [Schritt 2: Erstellen neuer Aufbewahrungstags für die Archivierungs-und Löschrichtlinien](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Standardrichtlinientag (Löschen); Dieses Tag wird automatisch auf das gesamte Postfach angewendet.  <br/> |
    |Alpine House gelöschte Elemente 5 Jahre löschen und Wiederherstellen zulassen  <br/> |Löscht Elemente aus dem Ordner "Gelöschte Elemente", die fünf Jahre alt sind. Benutzer können diese Elemente bis zu 14 Tage nach dem Löschen wiederherstellen.<sup>\*</sup> <br/> |Benutzerdefiniert (siehe [Schritt 2: Erstellen neuer Aufbewahrungstags für die Archivierungs-und Löschrichtlinien](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Aufbewahrungsrichtlinien-Tag (Gelöschte Elemente); Dieses Tag wird automatisch auf Elemente im Ordner "Gelöschte Elemente" angewendet.  <br/> |
    |Wiederherstellungs fähige Elemente 14 Tage in Archiv umsteigen  <br/> |Verschiebt Elemente, die sich im Ordner "Wiederherstellbare Elemente" für 14 Tage befinden, in den Ordner "Wiederherstellbare Elemente" im Archivpostfach.  <br/> |Integriert  <br/> |Aufbewahrungsrichtlinientag (herstellbare Elemente); Dieses Tag wird automatisch auf Elemente im Ordner "refundable Items" angewendet.  <br/> |
    |Junk-E-Mail  <br/> |Löscht Elemente, die sich seit 30 Tagen im Junk-e-Mail-Ordner befinden, endgültig. Benutzer können diese Elemente bis zu 14 Tage nach dem Löschen wiederherstellen.<sup>\*</sup> <br/> |Integriert  <br/> |Aufbewahrungsrichtlinien-Tag (Junk-e-Mail); Dieses Tag wird automatisch auf Elemente im Ordner Junk-e-Mail angewendet.  <br/> |
    |1 Monat, löschen  <br/> |Löscht Elemente, die 30 Tage alt sind, endgültig. Benutzer können diese Elemente bis zu 14 Tage nach dem Löschen wiederherstellen.<sup>\*</sup> <br/> |Integriert  <br/> |Persönlichen Dieses Tag kann von Benutzern angewendet werden.  <br/> |
    |1 Jahr, löschen  <br/> |Löscht Elemente, die 365 Tage alt sind, endgültig. Benutzer können diese Elemente bis zu 14 Tage nach dem Löschen wiederherstellen.<sup>\*</sup> <br/> |Integriert  <br/> |Persönlichen Dieses Tag kann von Benutzern angewendet werden.  <br/> |
    |Nie löschen  <br/> |Dieses Tag verhindert, dass Elemente durch eine Aufbewahrungsrichtlinie gelöscht werden.  <br/> |Integriert  <br/> |Persönlichen Dieses Tag kann von Benutzern angewendet werden.  <br/> |
    |Persönlich, 1 Jahre, in Archiv verschieben  <br/> |Verschiebt Elemente nach einem Jahr in das Archivpostfach.  <br/> |Integriert  <br/> |Persönlichen Dieses Tag kann von Benutzern angewendet werden.  <br/> |

    > <sup>\*</sup> Benutzer können das Tool zum Wiederherstellen von gelöschten Elementen in Outlook und Outlook im Internet (früher als Outlook Web App bezeichnet) verwenden, um ein gelöschtes Element innerhalb des Aufbewahrungszeitraums für gelöschte Elemente wiederherzustellen, der standardmäßig 14 Tage in Exchange Online ist. Ein Administrator kann Windows PowerShell verwenden, um den Aufbewahrungszeitraum für gelöschte Elemente auf maximal 30 Tage zu verbessern. Weitere Informationen finden Sie unter: [Wiederherstellen von gelöschten Elementen in Outlook für Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) und [Ändern des Aufbewahrungszeitraums für gelöschte Elemente für ein Postfach in Exchange Online](https://www.microsoft.com/?ref=go)
  
- Verwenden der **wiederherstellbaren Elemente 14 Tage verschieben in Archiv** Aufbewahrungs Tag hilft beim Freigeben von Speicherplatz im Ordner "Wiederherstellbare Elemente" im primären Postfach des Benutzers. Dies ist hilfreich, wenn das Postfach eines Benutzers in den Haltestatus versetzt wird, was bedeutet, dass das Postfach des Benutzers nicht immer endgültig gelöscht wird. Ohne das Verschieben von Elementen in das Archivpostfach ist es möglich, dass das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" im primären Postfach erreicht wird. Weitere Informationen zu diesem Thema und dazu, wie Sie dies vermeiden können, finden Sie unter [increase the refundable Items Quota for Mailboxes on Hold](https://go.microsoft.com/fwlink/p/?LinkId=786479).
