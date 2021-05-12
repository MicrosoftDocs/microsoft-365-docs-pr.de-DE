---
title: Löschen von Elementen im Ordner "Wiederherstellbare Elemente" des Cloudpostfachs im Archiv
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
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: Erfahren Sie, wie Administratoren Elemente im Ordner "Wiederherstellbare Elemente" eines Benutzers für ein Exchange Online-Postfach löschen können, auch wenn dieses Postfach in einem rechtlichen Haltebereich gespeichert ist.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 776113bcd6141c4f01c2da61f0bd71f99cffd3e2
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326642"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a>Löschen von Elementen im Ordner „Wiederherstellbare Elemente“ für cloudbasierte aufzubewahrende Postfächer

Der Ordner "Wiederherstellbare Elemente" für ein Exchange Online-Postfach ist vorhanden, um vor versehentlichen oder böswilligen Löschungen zu schützen. Es wird auch zum Speichern von Elementen verwendet, die von Compliancefeatures wie Halte- und eDiscovery-Suchfunktionen aufbewahrt und darauf zugegriffen werden. In einigen Situationen können Organisationen jedoch Daten haben, die versehentlich im Ordner "Wiederherstellbare Elemente" aufbewahrt wurden, die sie löschen müssen. Beispielsweise kann ein Benutzer unwissentlich eine E-Mail-Nachricht senden oder weiterleiten, die vertrauliche Informationen oder Informationen enthält, die schwerwiegende geschäftliche Folgen haben können. Auch wenn die Nachricht dauerhaft gelöscht wird, kann sie auf unbestimmte Zeit aufbewahrt werden, da für das Postfach ein rechtlicher Haltezustand aktiviert wurde. Dieses Szenario wird als *Datenleck* bezeichnet, da  Daten unbeabsichtigt in Office 365 übergelaufen wurden. In diesen Situationen können Sie Elemente im Ordner "Wiederherstellbare Elemente" eines Benutzers für ein Exchange Online-Postfach löschen, auch wenn dieses Postfach mit einer der verschiedenen Haltefunktionen in Office 365 in der Warteschleife platziert wird. Zu diesen Arten von Halterechten gehören In-Place-, eDiscovery- und Aufbewahrungsrichtlinien, die im Security and Compliance Center in Office 365 oder Microsoft 365 erstellt wurden.

In diesem Artikel wird erläutert, wie Administratoren Elemente aus dem Ordner "Wiederherstellbare Elemente" für cloudbasierte Postfächer löschen können, die sich im Haltebereich befinden. Dieses Verfahren umfasst das Deaktivieren des Zugriffs auf das Postfach und das Deaktivieren der Wiederherstellung einzelner Elemente, das Deaktivieren des Assistenten für verwaltete Ordner an der Verarbeitung des Postfachs, das vorübergehende Entfernen des Archivs, das Löschen von Elementen aus dem Ordner "Wiederherstellbare Elemente" und anschließend das Zurücksetzen des Postfachs auf die vorherige Konfiguration. Hier sehen Sie den Prozess:
  
[Schritt 1: Sammeln von Informationen zum Postfach](#step-1-collect-information-about-the-mailbox)

[Schritt 2: Vorbereiten des Postfachs](#step-2-prepare-the-mailbox)

[Schritt 3: Entfernen aller Haltefächer aus dem Postfach](#step-3-remove-all-holds-from-the-mailbox)

[Schritt 4: Entfernen des Verzögerungsspeichers aus dem Postfach](#step-4-remove-the-delay-hold-from-the-mailbox)

[Schritt 5: Löschen von Elementen im Ordner "Wiederherstellbare Elemente"](#step-5-delete-items-in-the-recoverable-items-folder)

[Schritt 6: Zurücksetzen des Postfachs auf den vorherigen Status](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Die in diesem Artikel beschriebenen Verfahren führen dazu, dass Daten dauerhaft aus einem Exchange Online-Postfach gelöscht (gelöscht) werden. Das bedeutet, dass Nachrichten, die Sie aus dem Ordner "Wiederherstellbare Elemente" löschen, nicht wiederhergestellt werden können und nicht für rechtliche Ermittlungen oder andere Compliancezwecke verfügbar sind. Wenn Sie Nachrichten aus einem Postfach löschen möchten, das im Rahmen einer Aufbewahrungsaufbewahrung, eines In-Place-Archivs, einer eDiscovery-Aufbewahrungsrichtlinie oder einer Aufbewahrungsrichtlinie im Security and Compliance Center gespeichert ist, fragen Sie sich bei Ihrer Datensatzverwaltung oder ihren Rechtsabteilungen, bevor Sie die Aufbewahrung entfernen. Ihre Organisation kann über eine Richtlinie verfügen, die definiert, ob ein Postfach im Archiv oder ein Datenlecksvorfall Vorrang hat.
  
## <a name="before-you-delete-items"></a>Bevor Sie Elemente löschen

- Zum Erstellen und Ausführen einer Inhaltssuche müssen Sie Mitglied der Rollengruppe für eDiscovery-Manager sein, oder Ihnen muss die Compliancesuche-Verwaltungsrolle zugewiesen sein. Um Nachrichten löschen zu können, müssen Sie Mitglied der Rollengruppe „Organisationsverwaltung“ sein, oder Ihnen muss die Verwaltungsrolle zum Suchen und Löschen zugewiesen sein. Informationen zum Hinzufügen von Benutzern zu einer Rollengruppe finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center](./assign-ediscovery-permissions.md).

- Das in diesem Artikel beschriebene Verfahren wird für inaktive Postfächer nicht unterstützt. Der Grund dafür ist, dass Sie nach dem Entfernen keine Aufbewahrungsrichtlinie (oder Aufbewahrungsrichtlinie) auf ein inaktives Postfach erneut verwenden können. Wenn Sie ein Haltefach aus einem inaktiven Postfach entfernen, wird es in ein normales postfach mit soft-deleted geändert und nach der Verarbeitung durch den Assistenten für verwaltete Ordner endgültig aus Ihrer Organisation gelöscht.

- Sie können dieses Verfahren nicht für ein Postfach ausführen, dem Aufbewahrungseinstellungen mit einer Richtlinie zugewiesen wurden, die mithilfe der Erhaltungssperre gesperrt ist. Das liegt daran, dass diese Sperre verhindert, dass Sie das Postfach aus der Richtlinie entfernen oder ausschließen und den Assistenten für verwaltete Ordner für das Postfach deaktivieren. Weitere Informationen zum Sperren von Richtlinien für die Aufbewahrung finden Sie unter [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).

- Wenn ein Postfach nicht in der Warteschleife platziert wird (oder die Wiederherstellung einzelner Elemente nicht aktiviert ist), können Sie die Elemente aus dem Ordner "Wiederherstellbare Elemente" löschen. Weitere Informationen dazu finden Sie unter Suchen und Löschen von E-Mail-Nachrichten [in Ihrer Organisation.](./search-for-and-delete-messages-in-your-organization.md)
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Schritt 1: Sammeln von Informationen zum Postfach

In diesem ersten Schritt werden ausgewählte Eigenschaften aus dem Zielpostfach gesammelt, die sich auf dieses Verfahren auswirken. Notieren Sie sich diese Einstellungen, oder speichern Sie sie in einer Textdatei, da Sie einige dieser Eigenschaften ändern und dann wieder zu den ursprünglichen Werten in Schritt 6 zurückkehren, nachdem Sie Elemente aus dem Ordner "Wiederherstellbare Elemente" gelöscht haben. Hier finden Sie eine Liste der Postfacheigenschaften, die Sie erfassen müssen.
  
- *SingleItemRecoveryEnabled*  und  *RetainDeletedItemsFor*. Bei Bedarf deaktivieren Sie die einmalige Wiederherstellung und erhöhen den Aufbewahrungszeitraum für gelöschte Elemente in Schritt 3.

- *LitigationHoldEnabled*  und  *InPlaceHolds*. Sie müssen alle Haltefächer für das Postfach identifizieren, damit Sie sie in Schritt 3 vorübergehend entfernen können. Im Abschnitt [Weitere Informationen finden](#more-information) Sie Tipps zum Identifizieren des Typspeichers, der in einem Postfach platziert werden kann.

Darüber hinaus müssen Sie die Einstellungen für den Postfachclientzugriff erhalten, damit Sie diese vorübergehend deaktivieren können, damit der Besitzer (oder andere Benutzer) während dieses Verfahrens nicht auf das Postfach zugreifen kann. Schließlich können Sie die aktuelle Größe und Anzahl der Elemente im Ordner "Wiederherstellbare Elemente" erhalten. Nachdem Sie Elemente im Ordner "Wiederherstellbare Elemente" in Schritt 5 gelöscht haben, verwenden Sie diese Informationen, um zu überprüfen, ob Elemente entfernt wurden.
  
1. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](/powershell/exchange/connect-to-exchange-online-powershell). Verwenden Sie unbedingt einen Benutzernamen und ein Kennwort für ein Administratorkonto, dem die entsprechenden Verwaltungsrollen in Exchange Online zugewiesen wurden.

2. Führen Sie den folgenden Befehl aus, um Informationen zur Wiederherstellung einzelner Elemente und zum Aufbewahrungszeitraum für gelöschte Elemente zu erhalten.

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Wenn die Wiederherstellung einzelner Elemente aktiviert ist, müssen Sie sie in Schritt 2 deaktivieren. Wenn der Aufbewahrungszeitraum für gelöschte Elemente nicht für 30 Tage festgelegt ist (der Höchstwert in Exchange Online), können Sie ihn in Schritt 2 erhöhen.

3. Führen Sie den folgenden Befehl aus, um die Postfachzugriffseinstellungen für das Postfach zu erhalten.

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   Sie deaktivieren alle diese Zugriffsmethoden in Schritt 2.

4. Führen Sie den folgenden Befehl aus, um Informationen zu den Aufbewahrungs- und Aufbewahrungsrichtlinien zu erhalten, die auf das Postfach angewendet werden.

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

    > [!TIP]
    > Wenn die  *InPlaceHolds-Eigenschaft*  zu viele Werte enthält und nicht alle angezeigt werden, können Sie den Befehl ausführen, um jeden Wert in einer separaten  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` Zeile anzeigen zu können.
  
5. Führen Sie den folgenden Befehl aus, um Informationen zu allen organisationsweiten Aufbewahrungsrichtlinien zu erhalten. 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   Wenn Ihre Organisation über organisationsweite Aufbewahrungsrichtlinien verfügt, müssen Sie das Postfach in Schritt 3 von diesen Richtlinien ausschließen. Es kann bis zu 24 Stunden dauern, bis die Änderung repliziert wird.

    > [!TIP]
    > Wenn die  *InPlaceHolds-Eigenschaft*  zu viele Werte enthält und nicht alle angezeigt werden, können Sie den Befehl ausführen, um jeden Wert in einer separaten  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` Zeile anzeigen zu können. 
  
6. Führen Sie den folgenden Befehl aus, um zu ermitteln, ob ein Verzögerungsspeicher auf das Postfach angewendet wird.

   ```powershell
   Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
   ```

   Wenn der Wert der *Eigenschaft DelayHoldApplied* oder *DelayReleaseHoldApplied* auf **True** festgelegt ist, wird ein Verzögerungsspeicher auf das Postfach angewendet und muss entfernt werden. Weitere Informationen zu Verzögerungsspeichern finden Sie unter [Schritt 4: Entfernen des Verzögerungsspeichers aus dem Postfach.](#step-4-remove-the-delay-hold-from-the-mailbox)

   Wenn der Wert einer der Eigenschaften auf **False** festgelegt ist, wird kein Verzögerungsspeicher auf das Postfach angewendet, und Sie können Schritt 4 überspringen.

7. Führen Sie den folgenden Befehl aus, um die aktuelle Größe und Gesamtanzahl der Elemente in Ordnern und Unterordnern im Ordner "Wiederherstellbare Elemente" im primären Postfach des Benutzers zu erhalten.

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Wenn das Archivpostfach des Benutzers aktiviert ist, führen Sie den folgenden Befehl aus, um die Größe und Gesamtanzahl der Elemente in Ordnern und Unterordnern im Ordner "Wiederherstellbare Elemente" in ihrem Archivpostfach zu erhalten. 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Wenn Sie Elemente in Schritt 5 löschen, können Sie elemente im Ordner "Wiederherstellbare Elemente" im primären Archivpostfach des Benutzers löschen oder nicht löschen. Wenn die automatische Erweiterung der Archivierung für das Postfach aktiviert ist, werden Elemente in einem Zusätzlichen Archivpostfach nicht gelöscht.
  
## <a name="step-2-prepare-the-mailbox"></a>Schritt 2: Vorbereiten des Postfachs

Nach dem Sammeln und Speichern von Informationen zum Postfach besteht der nächste Schritt in der Vorbereitung des Postfachs durch Ausführen der folgenden Aufgaben:
  
- **Deaktivieren Sie den Clientzugriff auf** das Postfach, damit der Postfachbesitzer nicht auf sein Postfach zugreifen kann, und nehmen Sie während dieses Verfahrens Änderungen an den Postfachdaten vor.

- **Erhöhen** Sie den Aufbewahrungszeitraum für gelöschte Elemente auf 30 Tage (der Höchstwert in Exchange Online), damit Elemente nicht aus dem Ordner "Wiederherstellbare Elemente" gelöscht werden, bevor Sie sie in Schritt 5 löschen können.

- **Deaktivieren Sie** die Wiederherstellung einzelner Elemente, damit Elemente (für die Dauer des Aufbewahrungszeitraums für gelöschte Elemente) nicht aufbewahrt werden, nachdem Sie sie in Schritt 5 aus dem Ordner "Wiederherstellbare Elemente" gelöscht haben.

- **Deaktivieren Sie den Assistenten für verwaltete** Ordner, damit er das Postfach nicht verarbeiten kann, und behalten Sie die Elemente bei, die Sie in Schritt 5 löschen.

Führen Sie die folgenden Schritte in Exchange Online PowerShell aus.
  
1. Führen Sie den folgenden Befehl aus, um den Clientzugriff auf das Postfach zu deaktivieren. Bei der Befehlssyntax wird davon ausgegangen, dass alle Clientzugriffsmethoden für das Postfach aktiviert wurden.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

    > [!NOTE]
    > Es kann bis zu 60 Minuten dauern, bis alle Clientzugriffsmethoden auf das Postfach deaktiviert sind. Beachten Sie, dass das Deaktivieren dieser Zugriffsmethoden den Postfachbesitzer nicht trennt, wenn er derzeit angemeldet ist. Wenn der Besitzer nicht angemeldet ist, kann er nicht mehr auf sein Postfach zugreifen, nachdem diese Zugriffsmethoden deaktiviert wurden.
  
2. Führen Sie den folgenden Befehl aus, um den Aufbewahrungszeitraum für gelöschte Elemente auf maximal 30 Tage zu erhöhen. Dabei wird davon ausgegangen, dass die aktuelle Einstellung weniger als 30 Tage beträgt.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Führen Sie den folgenden Befehl aus, um die Wiederherstellung einzelner Elemente zu deaktivieren.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

    > [!NOTE]
    > Es kann bis zu 60 Minuten dauern, bis die Wiederherstellung einzelner Elemente deaktiviert ist. Löschen Sie Elemente im Ordner "Wiederherstellbare Elemente" erst, wenn dieser Zeitraum abgelaufen ist. 
  
4. Führen Sie den folgenden Befehl aus, um zu verhindern, dass der Assistent für verwaltete Ordner das Postfach verarbeitet. Wie bereits erläutert, können Sie den Assistenten für verwaltete Ordner nur deaktivieren, wenn keine Aufbewahrungsrichtlinie mit einer Erhaltungssperre auf das Postfach angewendet wird. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Schritt 3: Entfernen aller Haltefächer aus dem Postfach

Der letzte Schritt, bevor Sie Elemente aus dem Ordner "Wiederherstellbare Elemente" löschen können, besteht im Entfernen aller Haltepunkte (die Sie in Schritt 1 identifiziert haben), die für das Postfach platziert wurden. Alle Haltepunkte müssen entfernt werden, damit Elemente nicht beibehalten werden, nachdem Sie sie aus dem Ordner "Wiederherstellbare Elemente" gelöscht haben. Die folgenden Abschnitte enthalten Informationen zum Entfernen verschiedener Haltebereiche für ein Postfach. Im Abschnitt [Weitere Informationen finden](#more-information) Sie Tipps zum Identifizieren des Typspeichers, der in einem Postfach platziert werden kann. Weitere Informationen finden Sie unter [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).
  
> [!CAUTION]
> Wie bereits erwähnt, sollten Sie sich an Ihre Datensatzverwaltung oder die Rechtsabteilungen halten, bevor Sie einen Halteraum aus einem Postfach entfernen. 
  
### <a name="litigation-hold"></a>Aufbewahrung für eventuelle Rechtsstreitigkeiten
  
Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um ein Prozessaufforderungsverfahren aus dem Postfach zu entfernen.

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> Ähnlich wie beim Deaktivieren der Clientzugriffsmethoden und der Wiederherstellung einzelner Elemente kann es bis zu 60 Minuten dauern, bis das Verfahrensverfahren entfernt wird. Löschen Sie Elemente erst nach Ablauf dieses Zeitraums aus dem Ordner "Wiederherstellbare Elemente". 
  
### <a name="in-place-hold"></a>Compliance-Archiv
  
Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um die In-Place zu identifizieren, die für das Postfach platziert wird. Verwenden Sie die GUID für In-Place, die Sie in Schritt 1 identifiziert haben.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

Nachdem Sie das In-Place identifiziert haben, können Sie das Exchange Admin Center (EAC) oder Exchange Online PowerShell verwenden, um das Postfach aus dem Haltebereich zu entfernen. Weitere Informationen finden Sie unter [Erstellen oder Entfernen eines Compliance-Archivs](/exchange/security-and-compliance/create-or-remove-in-place-holds).
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a>Aufbewahrungsrichtlinien, die auf bestimmte Postfächer angewendet werden
  
Führen Sie den folgenden Befehl in [Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell) aus, um die Aufbewahrungsrichtlinie zu identifizieren, die auf das Postfach angewendet wird. Dieser Befehl gibt auch alle Aufbewahrungsrichtlinien für Teams-Unterhaltungen zurück, die auf ein Postfach angewendet werden. Verwenden Sie die GUID (ohne das Präfix oder) für die `mbx` `skp` Aufbewahrungsrichtlinie, die Sie in Schritt 1 identifiziert haben.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Nachdem Sie die Aufbewahrungsrichtlinie identifiziert haben, wechseln Sie zur Seite Aufbewahrung von Informationsverwaltung im Security & Compliance Center, bearbeiten Sie die Aufbewahrungsrichtlinie, die Sie im vorherigen Schritt identifiziert haben, und entfernen Sie das Postfach aus der Liste der Empfänger, die in der Aufbewahrungsrichtlinie enthalten  >   sind.
  
### <a name="organization-wide-retention-policies"></a>Organisationsweite Aufbewahrungsrichtlinien
  
Organisationsweite, exchange- und teamsweite Aufbewahrungsrichtlinien werden auf jedes Postfach in der Organisation angewendet. Sie werden auf Organisationsebene (nicht auf Postfachebene) angewendet und zurückgegeben, wenn Sie das **Cmdlet Get-OrganizationConfig** in Schritt 1 ausführen. Führen Sie den folgenden Befehl in [Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell) aus, um die organisationsweiten Aufbewahrungsrichtlinien zu identifizieren. Verwenden Sie die GUID (ohne Präfix) für die organisationsweiten Aufbewahrungsrichtlinien, die  `mbx` Sie in Schritt 1 identifiziert haben.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Nachdem Sie die organisationsweiten Aufbewahrungsrichtlinien identifiziert haben, wechseln Sie zur Seite Aufbewahrung von Information **Governance** im Security & Compliance Center, bearbeiten Sie jede organisationsweite Aufbewahrungsrichtlinie, die Sie im vorherigen Schritt identifiziert haben, und fügen Sie das Postfach der Liste der ausgeschlossenen Empfänger  >   hinzu. Dadurch wird das Postfach des Benutzers aus der Aufbewahrungsrichtlinie entfernt. Es kann bis zu 24 Stunden dauern, bis die Änderung repliziert wird.

### <a name="retention-labels"></a>Aufbewahrungsbezeichnungen

Wenn ein Benutzer eine Bezeichnung an wendet, die zum Beibehalten oder Beibehalten von Inhalten konfiguriert ist, und dann Inhalte in einem Beliebigen Ordner oder Element in ihrem Postfach löscht, wird die *ComplianceTagHoldApplied-Postfacheigenschaft* auf **True festgelegt.** In diesem Fall gilt das Postfach als in der Warteschleife, als ob es in das Verfahrensverfahren einbehalten oder einer Aufbewahrungsrichtlinie zugewiesen wurde.

Führen Sie zum Anzeigen des Werts der *ComplianceTagHoldApplied-Eigenschaft* den folgenden Befehl in Exchange Online PowerShell aus:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Nachdem Sie festgestellt haben, dass sich ein Postfach im Haltezustand befindet, da eine Aufbewahrungsbezeichnung auf einen Ordner oder ein Element angewendet wird, können Sie das Tool für die Inhaltssuche im Security and Compliance Center verwenden, um mithilfe der ComplianceTag-Suchbedingung nach gekennzeichneten Elementen zu suchen. Weitere Informationen finden Sie im Abschnitt "Suchbedingungen" unter [Schlüsselwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md#conditions-for-common-properties).

Weitere Informationen zu Bezeichnungen finden Sie [unter Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen.](retention.md)

### <a name="ediscovery-holds"></a>eDiscovery-Haltebereiche
  
Führen Sie die folgenden Befehle in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) aus, um den Archivspeicher zu identifizieren, der einem eDiscovery-Fall zugeordnet ist (eDiscovery *holds* genannt), der auf das Postfach angewendet wird. Verwenden Sie die GUID (ohne Präfix) für den eDiscovery-Halteraum, den Sie  `UniH` in Schritt 1 identifiziert haben. Der zweite Befehl zeigt den Namen des eDiscovery-Falls an, dem der Halteraum zugeordnet ist. Der dritte Befehl zeigt den Namen des Halteraums an.
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

Nachdem Sie den Namen des eDiscovery-Falls und das Archiv identifiziert haben, wechseln Sie zur **eDiscovery eDiscovery-Seite** im Compliance Center, öffnen Sie den Fall, und entfernen Sie das Postfach aus dem \>  Archiv. Weitere Informationen zum Identifizieren von eDiscovery-Archiven finden Sie im Abschnitt "eDiscovery-Haltefächer" unter [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Schritt 4: Entfernen des Verzögerungsspeichers aus dem Postfach

Nachdem ein beliebiger Haltetyp aus einem Postfach entfernt wurde, wird der Wert der *Eigenschaft DelayHoldApplied* oder *DelayReleaseHoldApplied* auf **True festgelegt.** Dies tritt auf, wenn der Assistent für verwaltete Ordner das Postfach das nächste Mal verarbeitet und erkennt, dass ein Halteraum entfernt wurde. Dies wird  als Verzögerungsspeicher bezeichnet und bedeutet, dass das tatsächliche Entfernen des Haltezustands um 30 Tage verzögert wird, um zu verhindern, dass Daten dauerhaft aus dem Postfach gelöscht werden. (Der Zweck eines Verzögerungsspeichers besteht in der Möglichkeit, Administratoren die Möglichkeit zu geben, nach Postfachelementen zu suchen oder diese wiederhergestellt zu werden, die gelöscht werden, nachdem ein Haltebereich entfernt wurde.)  Wenn ein Verzögerungsspeicher für das Postfach platziert wird, gilt das Postfach weiterhin als auf unbegrenzte Zeit in der Warteschleife, als ob das Postfach im Prozesssicherungsverfahren war. Nach 30 Tagen läuft die Verzögerungsverzögerung ab, und Microsoft 365 versucht automatisch, die Verzögerungsverzögerung zu entfernen (indem die *Eigenschaft DelayHoldApplied* oder *DelayReleaseHoldApplied* auf **False** gesetzt wird), sodass der Halteraum entfernt wird. Weitere Informationen zu einem Verzögerungsspeicher finden Sie im Abschnitt "Verwalten von Postfächern im Verzögerungsspeicher" unter [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

Wenn der Wert der *Eigenschaft DelayHoldApplied* oder *DelayReleaseHoldApplied* auf **True** festgelegt ist, führen Sie einen der folgenden Befehle aus, um die Verzögerungsverzögerung zu entfernen:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Oder

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Für die Verwendung des Parameters *RemoveDelayHoldApplied* oder *RemoveDelayReleaseHoldApplied* muss Ihnen die Rolle "Rechtliches Haltehalten" in Exchange Online zugewiesen sein.

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Schritt 5: Löschen von Elementen im Ordner "Wiederherstellbare Elemente"

Jetzt können Sie Elemente im Ordner "Wiederherstellbare Elemente" mithilfe der [Cmdlets New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) und [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) in Security & Compliance Center PowerShell löschen.

Um nach Elementen zu suchen, die sich im Ordner "Wiederherstellbare Elemente" befinden, empfehlen wir Ihnen, eine *gezielte Sammlung* durchzuführen. Dies bedeutet, dass Sie den Umfang Ihrer Suche nur auf Elemente beschränken, die sich im Ordner "Wiederherstellbare Elemente" befinden. Sie können dies tun, indem Sie das Skript im Artikel [Inhaltssuche für gezielte Sammlungen verwenden](use-content-search-for-targeted-collections.md) ausführen. Dieses Skript gibt den Wert der Ordner-ID-Eigenschaft für alle Unterordner im Zielordner für wiederherstellbare Elemente zurück. Anschließend verwenden Sie die Ordner-ID in einer Suchabfrage, um Elemente in diesem Ordner zurückzugeben.

Hier ist eine Übersicht über den Vorgang zum Suchen und Löschen von Elementen im Ordner "Wiederherstellbare Elemente" eines Benutzers:

1. Führen Sie das Zielsammlungsskript aus, das die Ordner-IDs für alle Ordner im Postfach des Zielbenutzers zurückgibt. Das Skript stellt in derselben PowerShell-Sitzung eine Verbindung zu Exchange Online PowerShell und Security & Compliance PowerShell her. Weitere Informationen finden Sie unter [Ausführen des Skripts, um eine Liste der Ordner für ein Postfach zu erhalten.](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)

2. Kopieren Sie die Ordner-IDs für alle Unterordner in den Ordner "Wiederherstellbare Elemente". Alternativ können Sie die Ausgabe des Skripts in eine Textdatei umleiten.

   Hier finden Sie eine Liste und Beschreibung der Unterordner im Ordner "Wiederherstellbare Elemente", aus der Sie Elemente durchsuchen und löschen können:

   - **Löschungen**: Enthält „weich“ gelöschte Elemente, deren Aufbewahrungsfrist für gelöschte Elemente nicht abgelaufen ist. Benutzer können gelöschte Elemente aus diesem Unterordner mithilfe des Tools "Gelöschte Elemente wiederherstellen" in Outlook wiederherstellen.

   - **Bereinigung**: Enthält „fest“ gelöschte Elemente, deren Aufbewahrungsfrist für gelöschte Elemente abgelaufen ist. Benutzer können Elemente auch „fest“ löschen, indem sie Elemente aus ihrem Ordner "Wiederherstellbare Elemente" löschen. Wenn das Postfach einem Aufbewahrungsverfahren unterliegt, bleiben „fest“ gelöschte Elemente erhalten. Dieser Unterordner ist für Endbenutzer nicht sichtbar.

   - **DiscoveryHolds**: Enthält „fest“ gelöschte Elemente, die durch eine eDiscovery-Sperrung oder eine Aufbewahrungsrichtlinie beibehalten wurden. Dieser Unterordner ist für Endbenutzer nicht sichtbar.

   - **SubstrateHolds**: Enthält „fest“ gelöschte Elemente aus Teams und anderen Cloud-basierten Apps, die durch eine Aufbewahrungsrichtlinie oder eine andere Art von Sperrung beibehalten wurden. Dieser Unterordner ist für Endbenutzer nicht sichtbar.

3. Verwenden Sie das **Cmdlet New-ComplianceSearch** (in Security & Compliance Center PowerShell) oder verwenden Sie das Inhaltssuchtool im Compliance Center, um eine Inhaltssuche zu erstellen, die Elemente aus dem Ordner "Wiederherstellbare Elemente" des Zielbenutzers zurückgibt. Sie können dies tun, indem Sie die Ordner-ID in die Suchabfrage für alle Unterordner aufnehmen, die Sie durchsuchen möchten. Die folgende Abfrage gibt beispielsweise alle Nachrichten in den Unterordnern Purges und eDiscoveryHolds zurück:

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   Weitere Informationen und Beispiele zum Ausführen von Inhaltssuchen, die die Ordner-ID-Eigenschaft verwenden, finden Sie unter Verwenden einer Ordner-ID oder zum Ausführen einer [gezielten Auflistung.](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)

   > [!NOTE]
   > Wenn Sie das **Cmdlet New-ComplianceSearch** zum Durchsuchen des Ordners "Wiederherstellbare Elemente" verwenden, müssen Sie das **Cmdlet Start-ComplianceSearch** verwenden, um die Suche ausführen zu können.

4. Nachdem Sie eine Inhaltssuche erstellt und überprüft haben, ob sie die Elemente zurückgibt, die Sie löschen möchten, verwenden Sie den Befehl `New-ComplianceSearchAction -Purge -PurgeType HardDelete` (in Security & Compliance Center PowerShell), um die von der Inhaltssuche zurückgegebenen Elemente dauerhaft zu löschen, die Sie im vorherigen Schritt erstellt haben. Sie können beispielsweise einen Befehl ausführen, der dem folgenden Befehl ähnelt:

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. Maximal 10 Elemente pro Postfach werden gelöscht, wenn Sie den vorherigen Befehl ausführen. Das bedeutet, dass Sie den `New-ComplianceSearchAction -Purge` Befehl möglicherweise mehrmals ausführen müssen, um alle Elemente zu löschen, die Sie im Ordner "Wiederherstellbare Elemente" löschen möchten. Um weitere Elemente zu löschen, müssen Sie zuerst die vorherige Bereinigungsaktion für die Compliance-Suche entfernen. Sie tun dies, indem Sie das `Remove-ComplianceSearchAction` Cmdlet ausführen. Führen Sie beispielsweise den folgenden Befehl aus, um die im vorherigen Schritt ausgeführte Bereinigungsaktion zu löschen:

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   Anschließend können Sie eine neue Bereinigungsaktion der Compliance-Suche erstellen, um weitere Elemente zu löschen. Sie müssen jede Bereinigungsaktion löschen, bevor Sie eine neue erstellen.

   Um eine Liste der Compliance-Suchaktionen abzurufen, können Sie das `Get-ComplianceSearchAction` Cmdlet ausführen. Bereinigungsaktionen werden durch `_Purge` identifiziert, die an den Suchnamen angehängt wird.

### <a name="verify-that-items-were-deleted"></a>Überprüfen, ob Elemente gelöscht wurden

Um sicherzustellen, dass Sie Elemente erfolgreich aus dem Ordner "Wiederherstellbare Elemente" eines Postfachs gelöscht haben, verwenden Sie das **Cmdlet Get-MailboxFolderStatistics** in Exchange Online PowerShell, um die Größe und Anzahl der Elemente im Ordner "Wiederherstellbare Elemente" zu überprüfen. Sie können diese Statistiken mit den in Schritt 1 gesammelten vergleichen.
  
Führen Sie den folgenden Befehl aus, um die aktuelle Größe und Gesamtzahl der Elemente in Ordnern und Unterordnern im Ordner "Wiederherstellbare Elemente" im primären Postfach des Benutzers zu erhalten.
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

Führen Sie den folgenden Befehl aus, um die Größe und die Gesamtzahl der Elemente in Ordnern und Unterordnern im Ordner "Wiederherstellbare Elemente" im Archivpostfach des Benutzers abzurufen.

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Schritt 6: Zurücksetzen des Postfachs auf den vorherigen Status

Der letzte Schritt besteht im Zurücksetzen des Postfachs auf die vorherige Konfiguration. Dies bedeutet, dass Sie die Eigenschaften, die Sie in Schritt 2 geändert haben, zurücksetzen und die in Schritt 3 entfernten Halteobjekte erneut verwenden. Dies umfasst Folgendes:
  
- Ändern des Aufbewahrungszeitraums für gelöschte Elemente zurück in den vorherigen Wert. Alternativ können Sie diesen Satz einfach auf 30 Tage festlegen, den Maximalwert in Exchange Online.

- Erneutes Aktivieren der Wiederherstellung einzelner Elemente.

- Erneutes Aktivieren der Clientzugriffsmethoden, damit der Besitzer auf sein Postfach zugreifen kann.

- Erneutes Ansenden der aufbewahrungs- und aufbewahrungsrichtlinien, die Sie entfernt haben.

- Erneutes Aktivieren des Assistenten für verwaltete Ordner zum Verarbeiten des Postfachs.

> [!IMPORTANT]
> Es wird empfohlen, 24 Stunden nach der erneuten Anwendung einer Aufbewahrungs- oder Aufbewahrungsrichtlinie zu warten (und zu überprüfen, ob sie aktiviert ist), bevor Sie den Assistenten für verwaltete Ordner zum Verarbeiten des Postfachs erneut aktivieren.
  
Führen Sie die folgenden Schritte (in der angegebenen Reihenfolge) in Exchange Online PowerShell aus.
  
1. Führen Sie den folgenden Befehl aus, um den Aufbewahrungszeitraum für gelöschte Elemente wieder in den ursprünglichen Wert zu ändern. Dabei wird davon ausgegangen, dass die vorherige Einstellung weniger als 30 Tage beträgt. z. B. 14 Tage.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. Führen Sie den folgenden Befehl aus, um die Wiederherstellung einzelner Elemente erneut zu aktivieren.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. Führen Sie den folgenden Befehl aus, um alle Clientzugriffsmethoden für das Postfach erneut zu aktivieren.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. Die in Schritt 3 entfernten Halte halte wieder an. Verwenden Sie je nach Art des Halteverfahrens eines der folgenden Verfahren.

    **Aufbewahrung für eventuelle Rechtsstreitigkeiten**

    Führen Sie den folgenden Befehl aus, um ein Prozessaufforderungsverfahren für das Postfach erneut zu aktivieren.

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Situ-Aufbewahrung**

    Verwenden Sie die EAC (oder Exchange Online PowerShell), um das Postfach wieder zum In-Place hinzuzufügen.

    **Aufbewahrungsrichtlinien, die auf bestimmte Postfächer angewendet werden**

    Verwenden Sie das Security & Compliance Center, um das Postfach wieder zur Aufbewahrungsrichtlinie hinzuzufügen. Wechseln Sie zur Seite Aufbewahrung von Information **Governance** im Security & Compliance Center, bearbeiten Sie die Aufbewahrungsrichtlinie, und fügen Sie das Postfach wieder der Liste der Empfänger hinzu, auf die die Aufbewahrungsrichtlinie  >   angewendet wird.

    **Organisationsweite Aufbewahrungsrichtlinien**

    Wenn Sie eine organisationsweite oder exchangeweite Aufbewahrungsrichtlinie entfernt haben, indem Sie sie aus der Richtlinie ausschließen, verwenden Sie das Security & Compliance Center, um das Postfach aus der Liste der ausgeschlossenen Benutzer zu entfernen. Wechseln Sie zur Seite Aufbewahrung von Information **Governance** im Security & Compliance Center, bearbeiten Sie die organisationsweite Aufbewahrungsrichtlinie, und entfernen Sie das Postfach aus der Liste der  >   ausgeschlossenen Empfänger. Dadurch wird die Aufbewahrungsrichtlinie erneut auf das Postfach des Benutzers verwendet.

    **eDiscovery-Fall enthält**

    Verwenden Sie das Security & Compliance Center, um das Postfach wieder dem Archiv hinzuzufügen, das einem eDiscovery-Fall zugeordnet ist. Wechseln Sie zur **eDiscovery**  >  **eDiscovery-Seite,** öffnen Sie den Fall, und fügen Sie das Postfach wieder zum Archiv hinzu. 

5. Führen Sie den folgenden Befehl aus, damit der Assistent für verwaltete Ordner das Postfach erneut verarbeiten kann. Wie bereits erwähnt, wird empfohlen, 24 Stunden nach der erneuten Verwendung einer Aufbewahrungs- oder Aufbewahrungsrichtlinie zu warten (und zu überprüfen, ob sie aktiviert ist), bevor Sie den Assistenten für verwaltete Ordner erneut aktivieren.

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. Um zu überprüfen, ob das Postfach wieder auf die vorherige Konfiguration zurückgesetzt wurde, können Sie die folgenden Befehle ausführen und dann die Einstellungen mit den Einstellungen vergleichen, die Sie in Schritt 1 gesammelt haben.

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>Weitere Informationen

Hier ist eine Tabelle, in der beschrieben wird, wie unterschiedliche Haltetypen basierend auf den Werten in der  *InPlaceHolds-Eigenschaft*  identifiziert werden, wenn Sie die **Cmdlets Get-Mailbox** oder **Get-OrganizationConfig** ausführen. Ausführlichere Informationen finden Sie unter Identifizieren des Typs des Halteraums für [ein Exchange Online-Postfach.](identify-a-hold-on-an-exchange-online-mailbox.md)

Wie bereits erläutert, müssen Sie alle Aufbewahrungs- und Aufbewahrungsrichtlinien aus einem Postfach entfernen, bevor Sie Elemente im Ordner "Wiederherstellbare Elemente" erfolgreich löschen können.
  
| Haltebereichstyp | Beispielwert | Identifizieren des Halteraums |
|:-----|:-----|:-----|
|Beweissicherungsverfahren  <br/> | `True` <br/> |Die  *LitigationHoldEnabled*  -Eigenschaft wird festgelegt auf  `True`.  <br/> |
|Compliance-Archiv  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |Die  *InPlaceHolds-Eigenschaft*  enthält die GUID der In-Place, die für das Postfach platziert wird. Sie können sehen, dass es sich um einen In-Place handelt, da die GUID nicht mit einem Präfix beginnt.  <br/> Sie können den Befehl in Exchange Online PowerShell verwenden, um Informationen zum In-Place  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` für das Postfach zu erhalten.  <br/> |
| Aufbewahrungsrichtlinien im Security & Compliance Center, die auf bestimmte Postfächer angewendet werden  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> oder  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Wenn Sie das **Cmdlet Get-Mailbox** ausführen, enthält die  *InPlaceHolds-Eigenschaft*  auch GUIDs von Aufbewahrungsrichtlinien, die auf das Postfach angewendet werden. Sie können Aufbewahrungsrichtlinien identifizieren, da die GUID mit dem Präfix  `mbx` beginnt. Wenn die GUID der Aufbewahrungsrichtlinie mit dem Präfix beginnt, bedeutet dies, dass die  `skp` Aufbewahrungsrichtlinie auf Skype for Business-Unterhaltungen angewendet wird.  <br/> Führen Sie den folgenden Befehl in Security & Compliance Center PowerShell aus, um die Aufbewahrungsrichtlinie zu identitäten, die auf das Postfach angewendet wird: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Entfernen Sie die Präfix  `mbx` oder  `skp`, wenn Sie diesen Befehl ausführen.  <br/> |
|Organisationsweite Aufbewahrungsrichtlinien im Security & Compliance Center  <br/> |Kein Wert  <br/> oder  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696` (gibt an, dass das Postfach von einer organisationsweiten Richtlinie ausgeschlossen ist)  <br/> |Auch wenn die  *InPlaceHolds-Eigenschaft*  leer ist, wenn Sie das **Cmdlet Get-Mailbox** ausführen, kann es dennoch eine oder mehrere organisationsweite Aufbewahrungsrichtlinien für das Postfach gibt.  <br/> Um dies zu überprüfen, können Sie den Befehl in Exchange Online PowerShell ausführen, um eine Liste der GUIDs für organisationsweite  `Get-OrganizationConfig | FL InPlaceHolds` Aufbewahrungsrichtlinien zu erhalten. Die GUID für organisationsweite Aufbewahrungsrichtlinien, die auf #A0 angewendet werden, beginnt mit dem  `mbx` Präfix, z. B.  `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> Führen Sie den folgenden Befehl in Security & Compliance Center PowerShell aus, um die organisationsweite Aufbewahrungsrichtlinie zu identitäten, die auf das Postfach angewendet wird: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Wenn ein Postfach aus einer organisationsweiten Aufbewahrungsrichtlinie ausgeschlossen wird, wird die GUID für die Aufbewahrungsrichtlinie in der  *InPlaceHolds-Eigenschaft*  des Postfachs des Benutzers angezeigt, wenn Sie das **Cmdlet Get-Mailbox** ausführen. es wird durch das Präfix  `-mbx` identifiziert; z. B.  `-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|eDiscovery-Fallsicherung im Security & Compliance Center  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |Die  *InPlaceHolds-Eigenschaft*  enthält auch die GUID eines beliebigen Archivs, das einem eDiscovery-Fall im Security & Compliance Center zugeordnet ist, das möglicherweise für das Postfach platziert wird. Sie können erkennen, dass es sich hierbei um einen eDiscovery-Fall handelt, da die GUID mit dem Präfix  `UniH` beginnt.  <br/> Sie können das Cmdlet in Security & Compliance Center PowerShell verwenden, um Informationen zum eDiscovery-Fall zu erhalten, dem das Archiv für das Postfach  `Get-CaseHoldPolicy` zugeordnet ist. Sie können z. B. den Befehl ausführen, um den Namen des Fallspeichers im  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` Postfach anzeigen zu lassen. Be sure to remove the  `UniH`, wenn Sie diesen Befehl ausführen.  <br/><br/> Führen Sie die folgenden Befehle aus, um den eDiscovery-Fall zu identitäten, dem das Archiv für das Postfach zugeordnet ist:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
