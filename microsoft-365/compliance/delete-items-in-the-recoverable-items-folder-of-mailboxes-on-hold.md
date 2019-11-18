---
title: Löschen von Elementen im Ordner "Wiederherstellbare Elemente" von cloudbasierten Postfächern in der Warteschleife – Administratorhilfe
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
description: 'Für Administratoren: Elemente im Ordner "Wiederherstellbare Elemente" eines Benutzers für ein Exchange Online Postfach löschen, auch wenn das Postfach legal aufbewahrt wird. Dies ist eine effektive Möglichkeit zum Löschen von Daten, die versehentlich in Office 365 verschüttet wurden.'
ms.openlocfilehash: 1954ac4db8b978b0b1c3cdc8cee080cc0f0e6c22
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686260"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>Löschen von Elementen im Ordner "Wiederherstellbare Elemente" von cloudbasierten Postfächern in der Warteschleife – Administratorhilfe

Der Ordner "refundable Items" für ein Exchange Online Postfach ist vorhanden, um vor versehentlichen oder böswilligen Löschungen zu schützen. Es wird auch zum Speichern von Elementen verwendet, die beibehalten werden und von Office 365-Kompatibilitätsfeatures wie Holds und eDiscovery-suchen abgerufen werden. In einigen Situationen können Organisationen jedoch Daten haben, die versehentlich im Ordner "Wiederherstellbare Elemente" aufbewahrt werden, den Sie löschen müssen. Beispielsweise kann ein Benutzer unwissentlich eine e-Mail-Nachricht senden oder weiterleiten, die vertrauliche Informationen oder Informationen enthält, die möglicherweise schwerwiegende geschäftliche Konsequenzen haben. Selbst wenn die Nachricht dauerhaft gelöscht wird, kann Sie auf unbestimmte Zeit aufbewahrt werden, da im Postfach ein rechtlicher Aufbewahrungsplatz gespeichert wurde. Dieses Szenario wird als Datenüberlauf bezeichnet, da Daten versehentlich in Office 365 verschüttet wurden. In diesen Situationen können Sie Elemente im Ordner "Wiederherstellbare Elemente" eines Benutzers für ein Exchange Online Postfach löschen, auch wenn das Postfach mit einem der unterschiedlichen Hold-Features in Office 365 in den Haltestatus versetzt wird. Zu diesen Aufbewahrungsarten zählen Beweissicherungsverfahren, Compliance-Archiv, eDiscovery-Haltestatus und Office 365 im Security and Compliance Center in Office 365 oder Microsoft 365 erstellte Aufbewahrungsrichtlinien.
  
 In diesem Artikel wird erläutert, wie Sie Elemente aus dem Ordner "Wiederherstellbare Elemente" für in der Warteschleife verhaltene Cloud-basierte Postfächer löschen. Dieses Verfahren umfasst das Deaktivieren des Zugriffs auf das Postfach und das Deaktivieren der Wiederherstellung einzelner Elemente, das Deaktivieren des Assistenten für verwaltete Ordner für die Verarbeitung des Postfachs, das vorübergehende Entfernen des haltebereichs, das Löschen von Elementen aus dem Ordner "Wiederherstellbare Elemente" und das anschließende zurücksetzen das Postfach in seiner vorherigen Konfiguration. Hier ist der Prozess: 
  
[Schritt 1: Erfassen von Informationen zum Postfach](#step-1-collect-information-about-the-mailbox)

[Schritt 2: Vorbereiten des Postfachs](#step-2-prepare-the-mailbox)

[Schritt 3: Entfernen aller Haltestatus aus dem Postfach](#step-3-remove-all-holds-from-the-mailbox)

[Schritt 4: Entfernen der Verzögerungs Sperre aus dem Postfach](#step-4-remove-the-delay-hold-from-the-mailbox)

[Schritt 5: Löschen von Elementen im Ordner "Wiederherstellbare Elemente"](#step-5-delete-items-in-the-recoverable-items-folder)

[Schritt 6: Zurücksetzen des Postfachs in den vorherigen Zustand](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Die in diesem Artikel beschriebenen Verfahren führen dazu, dass Daten endgültig aus einem Exchange Online Postfach gelöscht (bereinigt) werden. Das bedeutet, dass Nachrichten, die Sie aus dem Ordner "Wiederherstellbare Elemente" löschen, nicht wiederhergestellt werden können und nicht für rechtliche Ermittlungen oder andere Compliance-Zwecke zur Verfügung stehen. Wenn Sie Nachrichten aus einem Postfach löschen möchten, das im Rahmen eines beweissicherungsverfahrens, eines Compliance-Archivs, eines eDiscovery Holds oder Office 365 im Security and Compliance Center erstellten Aufbewahrungsrichtlinie aufbewahrt wird, erkundigen Sie sich bei ihrer Datensatzverwaltung oder Ihren Rechtsabteilungen. vor dem Entfernen des haltebereichs. Ihre Organisation verfügt möglicherweise über eine Richtlinie, die definiert, ob ein aufbewahrtes Postfach oder ein Vorfall mit Datenüberlauf Vorrang hat. 
  
## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Sie müssen in Exchange Online beide der folgenden Verwaltungsrollen zugewiesen sein, um nach Nachrichten aus dem Ordner "Wiederherstellbare Elemente" in Schritt 5 zu suchen und zu löschen.
    
  - **Postfachsuche** – mit dieser Rolle können Sie Postfächer in Ihrer Organisation durchsuchen. Exchange-Administratoren wird diese Rolle nicht standardmäßig zugewiesen. Um diese Rolle selbst zuzuweisen, fügen Sie sich selbst als Mitglied der Rollengruppe "Discoveryverwaltung" in Exchange Online hinzu. 
    
  - **Post Fach Import Export** – mit dieser Rolle können Sie Nachrichten aus dem Postfach eines Benutzers löschen. Diese Rolle ist standardmäßig keiner Rollengruppe zugewiesen. Um Nachrichten aus den Postfächern von Benutzern zu löschen, können Sie die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. 
    
- Das in diesem Artikel beschriebene Verfahren wird nicht für inaktive Postfächer unterstützt. Das liegt daran, dass Sie nach dem Entfernen eines Haltestatus (oder Office 365 einer Aufbewahrungsrichtlinie) nicht auf ein inaktives Postfach erneut anwenden können. Wenn Sie einen Haltebereich aus einem inaktiven Postfach entfernen, wird er in ein normales, vorläufig gelöschtes Postfach geändert und dauerhaft aus Ihrer Organisation gelöscht, nachdem es vom Assistenten für verwaltete Ordner verarbeitet wurde.
    
- Sie können dieses Verfahren nicht für ein Postfach ausführen, das einer Office 365 Aufbewahrungsrichtlinie zugewiesen wurde, die mit einer Aufbewahrungs Sperre gesperrt wurde. Das liegt daran, dass Sie durch eine Aufbewahrungs Sperre verhindert werden, dass Sie das Postfach aus der Office 365 Aufbewahrungsrichtlinie entfernen oder ausschließen und den Assistenten für verwaltete Ordner für das Postfach deaktivieren. Weitere Informationen zum Sperren von Aufbewahrungsrichtlinien finden Sie unter [Sperren einer Aufbewahrungsrichtlinie](retention-policies.md#locking-a-retention-policy).
    
- Wenn ein Postfach nicht in der Warteschleife abgelegt wird (oder wenn die Wiederherstellung einzelner Elemente nicht aktiviert ist), können Sie die Elemente einfach aus dem Ordner "Wiederherstellbare Elemente" löschen. Weitere Informationen zur Vorgehensweise finden Sie unter [Suchen nach und Löschen von Nachrichten ](https://go.microsoft.com/fwlink/?linkid=852453).
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Schritt 1: Erfassen von Informationen zum Postfach

In diesem ersten Schritt werden ausgewählte Eigenschaften aus dem Zielpostfach gesammelt, die sich auf diese Prozedur auswirken. Achten Sie darauf, diese Einstellungen zu notieren oder in einer Textdatei zu speichern, da Sie einige dieser Eigenschaften ändern und dann wieder zu den ursprünglichen Werten in Schritt 6 zurückkehren, nachdem Sie Elemente aus dem Ordner "Wiederherstellbare Elemente" gelöscht haben. Im folgenden finden Sie eine Liste der Postfacheigenschaften, die Sie erfassen müssen.
  
-  *SingleItemRecoveryEnabled* und *Parameter RetainDeletedItemsFor* ; bei Bedarf können Sie die einzelne Wiederherstellung deaktivieren und den Aufbewahrungszeitraum für gelöschte Elemente in Schritt 3 verbessern. 
    
-  *LitigationHoldEnabled* und *InPlaceHolds* ; Sie müssen alle auf dem Postfach angeordneten haltebereiche identifizieren, damit Sie Sie in Schritt 3 vorübergehend entfernen können. Im Abschnitt [Weitere Informationen](#more-information) finden Sie Tipps zum Identifizieren des Typs Hold, der möglicherweise in einem Postfach gespeichert wird. 
    
Darüber hinaus müssen Sie die Einstellungen für den Post Fach Clientzugriff abrufen, sodass Sie Sie vorübergehend deaktivieren können, sodass der Besitzer (oder andere Benutzer) während dieses Verfahrens nicht auf das Postfach zugreifen kann. Schließlich können Sie die aktuelle Größe und Anzahl der Elemente im Ordner "Wiederherstellbare Elemente" abrufen. Nachdem Sie Elemente im Ordner "Wiederherstellbare Elemente" in Schritt 5 gelöscht haben, verwenden Sie diese Informationen, um zu überprüfen, ob die Elemente tatsächlich entfernt wurden.
  
1. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://go.microsoft.com/fwlink/?linkid=396554). Achten Sie darauf, einen Benutzernamen und ein Kennwort für ein Administratorkonto zu verwenden, dem in Exchange Online die entsprechenden Verwaltungsrollen zugewiesen wurden. 
    
2. Führen Sie den folgenden Befehl aus, um Informationen zur Wiederherstellung einzelner Elemente und zum Aufbewahrungszeitraum für gelöschte Elemente abzurufen.

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Wenn die Wiederherstellung einzelner Elemente aktiviert ist, müssen Sie Sie in Schritt 2 deaktivieren. Wenn der Aufbewahrungszeitraum für gelöschte Elemente für 30 Tage (der Höchstwert in Exchange Online) nicht festgelegt ist, können Sie ihn in Schritt 2 vergrössern. 
    
3. Führen Sie den folgenden Befehl aus, um die Postfachzugriffs Einstellungen für das Postfach abzurufen. 
    
    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   In Schritt 2 deaktivieren Sie alle diese Zugriffsmethoden.
    
4. Führen Sie den folgenden Befehl aus, um Informationen zu den Haltebereichen und Office 365 auf das Postfach angewendeten Aufbewahrungsrichtlinien abzurufen.
    
    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > Wenn die *InPlaceHolds* -Eigenschaft zu viele Werte enthält und nicht alle angezeigt werden, können Sie den `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` Befehl ausführen, um jeden Wert in einer separaten Zeile anzuzeigen. 
  
5. Führen Sie den folgenden Befehl aus, um Informationen zu organisationsweiten Office 365-Aufbewahrungsrichtlinien zu erhalten. 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   
   Wenn Ihre Organisation über organisationsweite Office 365 Aufbewahrungsrichtlinien verfügt, müssen Sie das Postfach in Schritt 3 von diesen Richtlinien ausschließen.

   > [!TIP]
    > Wenn die *InPlaceHolds* -Eigenschaft zu viele Werte enthält und nicht alle angezeigt werden, können Sie den `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` Befehl ausführen, um jeden Wert in einer separaten Zeile anzuzeigen. 
  
6. Führen Sie den folgenden Befehl aus, um die aktuelle Größe und Gesamtzahl der Elemente in Ordnern und Unterordnern im Ordner "Wiederherstellbare Elemente" im primären Postfach des Benutzers abzurufen. 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Wenn das Archivpostfach des Benutzers aktiviert ist, führen Sie den folgenden Befehl aus, um die Größe und die Gesamtzahl der Elemente in Ordnern und Unterordnern im Ordner "Wiederherstellbare Elemente" in Ihrem Archivpostfach abzurufen. 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Wenn Sie Elemente in Schritt 5 löschen, können Sie auswählen, ob Elemente im Ordner "Wiederherstellbare Elemente" im primären Archivpostfach des Benutzers gelöscht oder nicht gelöscht werden sollen. Beachten Sie Folgendes: Wenn die automatisch expandierende Archivierung für das Postfach aktiviert ist, werden Elemente in einem zusätzlichen Archivpostfach nicht gelöscht.
  
## <a name="step-2-prepare-the-mailbox"></a>Schritt 2: Vorbereiten des Postfachs

Nach dem sammeln und Speichern von Informationen über das Postfach besteht der nächste Schritt darin, das Postfach durch Ausführen der folgenden Aufgaben vorzubereiten: 
  
- **Deaktivieren Sie den Clientzugriff auf das Postfach** , sodass der Postfachbesitzer während dieses Verfahrens nicht auf sein Postfach zugreifen und Änderungen an den Postfachdaten vornehmen kann. 
    
- **Erweitern Sie den Aufbewahrungszeitraum für gelöschte Elemente** auf 30 Tage (der Höchstwert in Exchange Online), sodass Elemente nicht aus dem Ordner "Wiederherstellbare Elemente" gelöscht werden, bevor Sie Sie in Schritt 5 löschen können. 
    
- **Deaktivieren Sie die Wiederherstellung einzelner** Elemente, sodass Elemente (während der Dauer des Aufbewahrungszeitraums für gelöschte Elemente) nicht aufbewahrt werden, nachdem Sie Sie aus dem Ordner "Wiederherstellbare Elemente" in Schritt 5 gelöscht haben. 
    
- **Deaktivieren Sie den Assistenten für verwaltete Ordner** , sodass das Postfach nicht verarbeitet wird und die in Schritt 5 gelöschten Elemente beibehalten werden. 
    
Führen Sie die folgenden Schritte in Exchange Online PowerShell aus.
  
1. Führen Sie den folgenden Befehl aus, um den gesamten Clientzugriff auf das Postfach zu deaktivieren. Bei der Befehlssyntax wird davon ausgegangen, dass alle Clientzugriffsmethoden für das Postfach aktiviert wurden.

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > Es kann bis zu 60 Minuten dauern, bis alle Clientzugriffsmethoden für das Postfach deaktiviert sind. Beachten Sie, dass das Deaktivieren dieser Zugriffsmethoden nicht den Postfachbesitzer trennt, in dem Sie sich gerade angemeldet haben. Wenn der Besitzer nicht angemeldet ist, kann er nicht auf sein Postfach zugreifen, nachdem diese Zugriffsmethoden deaktiviert wurden. 
  
2. Führen Sie den folgenden Befehl aus, um den Aufbewahrungszeitraum für gelöschte Elemente um maximal 30 Tage zu verlängern. Dabei wird davon ausgegangen, dass die aktuelle Einstellung weniger als 30 Tage beträgt. 

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Führen Sie den folgenden Befehl aus, um die Wiederherstellung einzelner Elemente zu deaktivieren.
    
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > Es kann bis zu 60 Minuten dauern, bis die Wiederherstellung einzelner Elemente deaktiviert ist. Löschen Sie keine Elemente im Ordner "Wiederherstellbare Elemente", bis dieser Zeitraum abgelaufen ist. 
  
4. Führen Sie den folgenden Befehl aus, um zu verhindern, dass der Assistent für verwaltete Ordner das Postfach verarbeitet. Wie bereits erläutert, können Sie den Assistenten für verwaltete Ordner nur deaktivieren, wenn keine Office 365 Aufbewahrungsrichtlinie mit einer Aufbewahrungs Sperre auf das Postfach angewendet wird. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Schritt 3: Entfernen aller Haltestatus aus dem Postfach

Der letzte Schritt, bevor Sie Elemente aus dem Ordner "Wiederherstellbare Elemente" löschen können, ist das Entfernen aller haltebereiche (die Sie in Schritt 1 identifiziert haben), die in das Postfach aufgenommen wurden. Alle Haltestatus müssen entfernt werden, sodass Elemente nicht beibehalten werden, nachdem Sie Sie aus dem Ordner "Wiederherstellbare Elemente" gelöscht haben. Die folgenden Abschnitte enthalten Informationen zum Entfernen verschiedener Aufbewahrungs Typen für ein Postfach. Im Abschnitt [Weitere Informationen](#more-information) finden Sie Tipps zum Identifizieren des Typs Hold, der möglicherweise in einem Postfach gespeichert wird. Weitere Informationen finden Sie unter [Vorgehensweise zum Identifizieren des Aufbewahrungs Typs, der in einem Exchange Online Postfach gespeichert](identify-a-hold-on-an-exchange-online-mailbox.md)ist.
  
> [!CAUTION]
> Erkundigen Sie sich wie bereits erwähnt mit ihrer Datensatzverwaltung oder den Rechtsabteilungen, bevor Sie einen Haltebereich aus einem Postfach entfernen. 
  
 ### <a name="litigation-hold"></a>Aufbewahrung für eventuelle Rechtsstreitigkeiten
  
Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um ein Beweissicherungsverfahren aus dem Postfach zu entfernen.

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> Ähnlich wie beim Deaktivieren der Clientzugriffsmethoden und der Wiederherstellung einzelner Elemente kann es bis zu 60 Minuten dauern, bis das Beweissicherungsverfahren entfernt wurde. Löschen Sie keine Elemente aus dem Ordner "Wiederherstellbare Elemente", bis dieser Zeitraum abgelaufen ist. 
  
 ### <a name="in-place-hold"></a>Compliance-Archiv
  
Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um den in-situ-Speicher zu identifizieren, der auf dem Postfach platziert wird. Verwenden Sie die GUID für den in-situ-Speicher, den Sie in Schritt 1 identifiziert haben. 

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

Nachdem Sie den in-situ-Speicher identifiziert haben, können Sie die Exchange-Verwaltungskonsole (EAC) oder Exchange Online PowerShell verwenden, um das Postfach aus dem Archiv zu entfernen. Weitere Informationen finden Sie unter [Erstellen oder Entfernen eines Compliance-Archivs](https://go.microsoft.com/fwlink/?linkid=852668).
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a>Office 365 auf bestimmte Postfächer angewendete Aufbewahrungsrichtlinien
  
Führen Sie den folgenden Befehl in [Security #a0 Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) aus, um die Office 365-Aufbewahrungsrichtlinie zu ermitteln, die auf das Postfach angewendet wird. Verwenden Sie die GUID (ohne das `mbx` Präfix `skp` oder) für die Aufbewahrungsrichtlinie, die Sie in Schritt 1 identifiziert haben. 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Nachdem Sie **die Aufbewahrungs** Richtlinie identifiziert haben, wechseln Sie im Security #a0 Compliance Center zur Seite zur **Verwaltung der Datumssteuerung** \> , bearbeiten Sie die im vorherigen Schritt identifizierte Aufbewahrungsrichtlinie, und entfernen Sie das Postfach aus der Liste der Empfänger, die in der Aufbewahrungsrichtlinie enthalten sind. 
  
 ### <a name="organization-wide-office-365-retention-policies"></a>Organisationsweite Office 365 Aufbewahrungsrichtlinien
  
Organisationsweite und Exchange-weite Office 365 Aufbewahrungsrichtlinien werden auf jedes Postfach in der Organisation angewendet. Sie werden auf Organisationsebene (nicht auf Postfachebene) angewendet und werden zurückgegeben, wenn Sie das Cmdlet **Get-OrganizationConfig** in Schritt 1 ausführen. Führen Sie den folgenden Befehl in [Security #a0 Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) aus, um die organisationsweiten Office 365-Aufbewahrungsrichtlinien zu identifizieren. Verwenden Sie die GUID (ohne das `mbx` Präfix eingeschlossen) für die organisationsweiten Aufbewahrungsrichtlinien, die Sie in Schritt 1 identifiziert haben. 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Nachdem Sie die organisationsweiten Office 365 **-Aufbewahrungs** Richtlinien identifiziert haben, wechseln Sie im Security #a0 Compliance Center auf die Seite zur **Verwaltung der Datumssteuerung** \> , und bearbeiten Sie jede organisationsweite Aufbewahrungsrichtlinie, die Sie im vorherigen Schritt identifiziert haben, und fügen Sie das Postfach der Liste der ausgeschlossenen Empfänger hinzu. Dadurch wird das Postfach des Benutzers aus der Aufbewahrungsrichtlinie entfernt. 

### <a name="office-365-retention-labels"></a>Office 365-Aufbewahrungsbezeichnungen

Wenn ein Benutzer eine Bezeichnung anwendet, die für die Aufbewahrung von Inhalten konfiguriert ist, oder die Inhalte in einem beliebigen Ordner oder Element in seinem Postfach aufbewahren und dann löschen, wird die *ComplianceTagHoldApplied* -Postfacheigenschaft auf **true**festgelegt. In diesem Fall gilt das Postfach als in der Warteschleife, als ob es in einem Beweissicherungsverfahren gespeichert oder einer Office 365 Aufbewahrungsrichtlinie zugewiesen wurde.

Um den Wert der *ComplianceTagHoldApplied* -Eigenschaft anzuzeigen, führen Sie den folgenden Befehl in Exchange Online PowerShell aus:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Nachdem Sie festgestellt haben, dass ein Postfach in der Warteschleife ist, da eine Aufbewahrungs Bezeichnung auf einen Ordner oder ein Element angewendet wird, können Sie das Inhalts Such Tool im Security and Compliance Center verwenden, um nach beschrifteten Elementen mithilfe der ComplianceTag-Suchbedingung zu suchen. Weitere Informationen finden Sie im Abschnitt "Suchbedingungen" unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md#conditions-for-common-properties).

Weitere Informationen zu Bezeichnungen finden Sie unter [Overview of Office 365 Labels](labels.md).

 ### <a name="ediscovery-case-holds"></a>eDiscovery-Fall Behältern
  
Führen Sie die folgenden Befehle in [Security #a0 Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) aus, um den Haltebereich zu identifizieren, der einem eDiscovery-Fall zugeordnet ist, der auf das Postfach angewendet wird. Verwenden Sie die GUID (ohne das `UniH` Präfix eingeschlossen) für den eDiscovery-Haltebereich, den Sie in Schritt 1 identifiziert haben. Beachten Sie, dass der zweite Befehl den Namen des eDiscovery-Falls anzeigt, dem der Haltebereich zugeordnet ist. der dritte Befehl zeigt den Namen des Haltestatus an. 
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

Nachdem Sie den Namen des eDiscovery-Falls und des Haltestatus identifiziert haben, wechseln Sie zur **eDiscovery** \> **-eDiscovery-Seite im** Compliance Center, öffnen Sie den Fall, und entfernen Sie das Postfach aus dem Archiv. Weitere Informationen finden Sie unter [eDiscovery Cases](ediscovery-cases.md).
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Schritt 4: Entfernen der Verzögerungs Sperre aus dem Postfach

Nach dem Entfernen eines beliebigen haltebereichs aus einem Postfach wird der Wert der *DelayHoldApplied* -Postfacheigenschaft auf **true**festgelegt. Dies tritt auf, wenn der Assistent für verwaltete Ordner das nächste Mal das Postfach verarbeitet und erkennt, dass ein Haltebereich entfernt wurde. Dies wird als *Verzögerungs* Speicher bezeichnet und bedeutet, dass das tatsächliche Entfernen des Haltestatus für 30 Tage verzögert wird, um zu verhindern, dass Daten endgültig aus dem Postfach gelöscht werden. (Der Zweck einer Verzögerungs Sperre besteht darin, Administratoren die Möglichkeit zu geben, nach Postfachelementen zu suchen oder diese wiederherzustellen, die nach dem Entfernen eines Haltestatus gelöscht werden.)  Wenn ein Verzögerungs Speicher auf das Postfach gesetzt wird, wird das Postfach weiterhin für unbegrenzte Dauer aufbewahrt, als ob das Postfach ein Beweissicherungsverfahren aufweist. Nach 30 Tagen läuft die Verzögerungsdauer ab, und Office 365 versucht automatisch, die Verzögerungszeit zu entfernen (indem die *DelayHoldApplied* -Eigenschaft auf **false**festgelegt wird), sodass der Haltestatus tatsächlich entfernt wird. 

Bevor Sie Elemente in Schritt 5 löschen können, müssen Sie die Verzögerungszeit aus dem Postfach entfernen. Ermitteln Sie zunächst, ob die Verzögerungszeit auf das Postfach angewendet wird, indem Sie den folgenden Befehl in Exchange Online PowerShell ausführen:

```powershell
Get-Mailbox <username> | FL DelayHoldApplied
```

Wenn der Wert der *DelayHoldApplied* -Eigenschaft auf **false**festgelegt ist, wurde ein Verzögerungs Speicher nicht auf das Postfach gesetzt. Sie können zu Schritt 5 wechseln und Elemente im Ordner "Wiederherstellbare Elemente" löschen.

Wenn der Wert der *DelayHoldApplied* -Eigenschaft auf **true**festgelegt ist, führen Sie den folgenden Befehl aus, um die Verzögerung zu entfernen:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Beachten Sie, dass der Rolle "Legal Hold" in Exchange Online zugewiesen werden muss, um den *RemoveDelayHoldApplied* -Parameter verwenden zu können.

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Schritt 5: Löschen von Elementen im Ordner "Wiederherstellbare Elemente"

Jetzt können Sie Elemente im Ordner "Wiederherstellbare Elemente" mithilfe des Cmdlets [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) in Exchange Online PowerShell tatsächlich löschen. Sie haben drei Optionen, wenn Sie das Cmdlet **Search-Mailbox** ausführen. 
  
- Kopieren Sie Elemente vor dem Löschen in ein Zielpostfach, damit Sie die Elemente vor dem Löschen ggf. überprüfen können.
    
- Kopieren Sie Elemente in ein Zielpostfach, und löschen Sie Sie in demselben Befehl.
    
- Elemente löschen, ohne Sie in ein Zielpostfach zu kopieren. 
    
Beachten Sie, dass Elemente im Ordner "Wiederherstellbare Elemente" im primären Archivpostfach des Benutzers ebenfalls gelöscht werden, wenn Sie das Cmdlet **Search-Mailbox** ausführen. Um dies zu verhindern, können Sie die Option  *DoNotIncludeArchive*  einschließen. Wenn die automatisch expandierende Archivierung für das Postfach aktiviert ist, werden von dem * *-Cmdlet "Search-Mailbox * *" keine Elemente in einem zusätzlichen Archivpostfach gelöscht, wie bereits erwähnt. Weitere Informationen zum automatisch wachsenden Archiv finden Sie unter [Overview of Unlimited Archiving in Office 365](unlimited-archiving.md).
  
> [!NOTE]
> Wenn Sie eine Suchabfrage (durch Verwendung des Parameters  *SearchQuery*  ) einschließen, gibt das Cmdlet **Search-Mailbox** maximal 10.000 Elemente in den Suchergebnissen zurück. Wenn Sie also eine Suchabfrage einschließen, müssen Sie den Befehl **Search-Mailbox** möglicherweise mehrere Male ausführen, um mehr als 10.000 Elemente zu löschen. 
  
Die folgenden Beispiele zeigen die Befehlssyntax für jede dieser Optionen. In diesen Beispielen wird `-SearchQuery size>0` der Parameterwert verwendet, mit dem alle Elemente aus allen Unterordnern im Ordner "refundable Items" gelöscht werden. Wenn Sie nur Elemente löschen müssen, die bestimmten Bedingungen entsprechen, können Sie auch den *SearchQuery* -Parameter verwenden, um andere Bedingungen anzugeben, beispielsweise den Betreff einer Nachricht oder einen Datumsbereich. Weitere Beispiele finden Sie unter [Verwenden des SearchQuery-Parameters](#other-examples-of-using-the-searchquery-parameter) . 
  
### <a name="example-1"></a>Beispiel 1

In diesem Beispiel werden alle Elemente im Ordner "refundable Items" des Benutzers in einen Ordner im Discovery-Such Postfach Ihrer Organisation kopiert. Auf diese Weise können Sie die Elemente überprüfen, bevor Sie sie endgültig löschen.

```powershell
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

Im vorherigen Beispiel ist es nicht erforderlich, Elemente in das Ermittlungs Such Postfach zu kopieren. Sie können Nachrichten in ein beliebiges Zielpostfach kopieren. Um jedoch den Zugriff auf potenziell vertrauliche Postfachdaten zu verhindern, wird empfohlen, Nachrichten in ein Postfach zu kopieren, das auf autorisiertes Personal beschränkt ist. Standardmäßig ist der Zugriff auf das standardmäßige Ermittlungs Such Postfach auf Mitglieder der Rollengruppe Ermittlungsverwaltung in Exchange Online beschränkt. 
  
### <a name="example-2"></a>Beispiel 2

In diesem Beispiel werden alle Elemente im Ordner "Wiederherstellbare Elemente" des Benutzers in einen Ordner im Discovery-Such Postfach Ihrer Organisation kopiert, und anschließend werden die Elemente aus dem Ordner "Wiederherstellbare Elemente" des Benutzers gelöscht.

```powershell
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```

### <a name="example-3"></a>Beispiel 3

In diesem Beispiel werden alle Elemente im Ordner "refundable Items" des Benutzers gelöscht, ohne Sie in ein Zielpostfach zu kopieren. 

```powershell
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a>Weitere Beispiele für die Verwendung des SearchQuery-Parameters

Im folgenden finden Sie einige Beispiele für die Verwendung des *SearchQuery* -Parameters zum Suchen nach bestimmten Nachrichten. Wenn Sie den *SearchQuery* -Parameter verwenden, um nach bestimmten Elementen zu suchen, sollten Sie die Suchergebnisse in ein Zielpostfach kopieren, sodass Sie die Suchergebnisse überprüfen und die Abfrage gegebenenfalls überarbeiten können, bevor Sie die Ergebnisse einer Suche löschen. 
  
In diesem Beispiel werden Nachrichten zurückgegeben, die einen bestimmten Ausdruck im Subject-Feld enthalten.
  
```powershell
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

In diesem Beispiel werden Nachrichten zurückgegeben, die innerhalb des angegebenen Datumsbereichs gesendet wurden.
  
```powershell
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```

In diesem Beispiel werden Nachrichten zurückgegeben, die an die angegebene Person gesendet wurden.

```powershell
SearchQuery 'to:garthf@alpinehouse.com'
```

### <a name="verify-that-items-were-deleted"></a>Überprüfen, ob Elemente gelöscht wurden

Um zu überprüfen, ob Sie Elemente erfolgreich aus dem Ordner "Wiederherstellbare Elemente" eines Postfachs gelöscht haben, verwenden Sie das Cmdlet **Get-MailboxFolderStatistics** in Exchange Online PowerShell, um die Größe und Anzahl der Elemente im Ordner "Wiederherstellbare Elemente" zu überprüfen. Sie können diese Statistiken mit denen vergleichen, die Sie in Schritt 1 gesammelt haben. 
  
Führen Sie den folgenden Befehl in aus, um die aktuelle Größe und Gesamtzahl der Elemente in Ordnern und Unterordnern im Ordner "Wiederherstellbare Elemente" im primären Postfach des Benutzers abzurufen. 
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

Führen Sie den folgenden Befehl aus, um die Größe und die Gesamtzahl der Elemente in Ordnern und Unterordnern im Ordner "Wiederherstellbare Elemente" im Archivpostfach des Benutzers abzurufen. 

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Schritt 6: Zurücksetzen des Postfachs in den vorherigen Zustand

Im letzten Schritt wird das Postfach wieder auf seine frühere Konfiguration zurückgesetzt. Dies bedeutet, dass Sie die Eigenschaften, die Sie in Schritt 2 geändert haben, erneut festlegen und die in Schritt 3 entfernten Haltestatus erneut anwenden. Dies umfasst Folgendes:
  
- Ändern der Aufbewahrungsdauer für gelöschte Elemente zurück in den vorherigen Wert. Alternativ können Sie diese Einstellung auf 30 Tage festlegen, wobei der Höchstwert in Exchange Online liegt.
    
- Erneutes Aktivieren der Wiederherstellung einzelner Elemente
    
- Erneutes Aktivieren der Clientzugriffsmethoden, damit der Besitzer auf sein Postfach zugreifen kann.
    
- Erneutes Anwenden der haltebereiche und Office 365 von Ihnen entfernten Aufbewahrungsrichtlinien
    
- Erneutes Aktivieren des Assistenten für verwaltete Ordner zum Verarbeiten des Postfachs.
    
> [!IMPORTANT]
> Es wird empfohlen, dass Sie 24 Stunden nach der erneuten Anwendung eines Haltestatus oder Office 365 Aufbewahrungsrichtlinie warten (und sicherstellen, dass Sie vorhanden ist), bevor Sie den Assistenten für verwaltete Ordner erneut aktivieren, um das Postfach zu verarbeiten. 
  
Führen Sie die folgenden Schritte (in der angegebenen Reihenfolge) in Exchange Online PowerShell aus.
  
1. Führen Sie den folgenden Befehl aus, um die Aufbewahrungsdauer für gelöschte Elemente in den ursprünglichen Wert zurück zu ändern. Dabei wird davon ausgegangen, dass die vorherige Einstellung weniger als 30 Tage beträgt; Beispiel: 14 Tage. 
    
    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. Führen Sie den folgenden Befehl aus, um die Wiederherstellung einzelner Elemente wieder zu aktivieren.
   
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. Führen Sie den folgenden Befehl aus, um alle Clientzugriffsmethoden für das Postfach erneut zu aktivieren.
    
    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. Wenden Sie die in Schritt 3 entfernten Haltestatus erneut an. Je nach Typ des haltebereichs verwenden Sie eines der folgenden Verfahren.
    
    **Aufbewahrung für eventuelle Rechtsstreitigkeiten**
    
    Führen Sie den folgenden Befehl aus, um ein Beweissicherungsverfahren für das Postfach erneut zu aktivieren.
    
    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**
    
    Verwenden Sie die Exchange-Verwaltungskonsole (oder Exchange Online PowerShell), um das Postfach wieder dem in-situ-Speicher hinzuzufügen. 
    
    **Office 365 auf bestimmte Postfächer angewendete Aufbewahrungsrichtlinien**
    
    Verwenden Sie das Security #a0 Compliance Center, um das Postfach wieder zur Aufbewahrungsrichtlinie hinzuzufügen. Wechseln Sie zur Seite " **Date Governance** \> **Retention** " im Security #a0 Compliance Center, bearbeiten Sie die Aufbewahrungsrichtlinie, und fügen Sie das Postfach wieder der Liste der Empfänger hinzu, auf die die Aufbewahrungsrichtlinie angewendet wird. 
    
    **Organisationsweite Office 365 Aufbewahrungsrichtlinien**
    
    Wenn Sie eine organisationsweite oder Exchange-weite Aufbewahrungsrichtlinie durch Ausschließen aus der Richtlinie entfernt haben, verwenden Sie das Sicherheits #a0 Compliance Center, um das Postfach aus der Liste der ausgeschlossenen Benutzer zu entfernen. Wechseln Sie zur Seite " **Date Governance** \> **Retention** " im Security #a0 Compliance Center, bearbeiten Sie die organisationsweite Aufbewahrungsrichtlinie, und entfernen Sie das Postfach aus der Liste der ausgeschlossenen Empfänger. Dadurch wird die Aufbewahrungsrichtlinie erneut auf das Postfach des Benutzers angewendet. 
    
    **eDiscovery-Fall Behältern**
    
    Verwenden Sie das Security #a0 Compliance Center, um das Postfach wieder dem Aufbewahrungsplatz hinzuzufügen, der einem eDiscovery-Fall zugeordnet ist. Wechseln Sie zur **eDiscovery** \> - **eDiscovery** -Seite, öffnen Sie die Anfrage, und fügen Sie das Postfach wieder in das Archiv ein. 
    
5. Führen Sie den folgenden Befehl aus, um dem Assistenten für verwaltete Ordner das erneute verarbeiten des Postfachs zu gestatten. Wie bereits erwähnt, wird empfohlen, dass Sie 24 Stunden warten, nachdem Sie den Assistenten für verwaltete Ordner erneut aktiviert haben oder Office 365-Aufbewahrungsrichtlinie (und sicherstellen, dass Sie vorhanden ist) erneut anwenden. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. Um zu überprüfen, ob das Postfach wieder auf seine frühere Konfiguration zurückgesetzt wurde, können Sie die folgenden Befehle ausführen und dann die Einstellungen mit denen vergleichen, die Sie in Schritt 1 gesammelt haben.

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>Weitere Informationen

Im folgenden finden Sie eine Tabelle, in der beschrieben wird, wie verschiedene Aufbewahrungs Typen basierend auf den Werten in der *InPlaceHolds* -Eigenschaft identifiziert werden, wenn Sie die Cmdlets **Get-Mailbox** oder **Get-OrganizationConfig** ausführen. Ausführlichere Informationen finden Sie unter [Identifizieren des Aufbewahrungs Typs, der in einem Exchange Online Postfach gespeichert](identify-a-hold-on-an-exchange-online-mailbox.md)ist.

Wie bereits erläutert, müssen Sie alle haltebereiche und Office 365 Aufbewahrungsrichtlinien aus einem Postfach entfernen, bevor Sie Elemente im Ordner "Wiederherstellbare Elemente" erfolgreich löschen können. 
  
|**Haltebereichstyp**|**Beispielwert**|**Vorgehensweise zum Identifizieren des Haltestatus**|
|:-----|:-----|:-----|
|Beweissicherungsverfahren  <br/> | `True` <br/> |Die  *LitigationHoldEnabled*  -Eigenschaft wird festgelegt auf  `True`.  <br/> |
|Compliance-Archiv  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |Die *InPlaceHolds* -Eigenschaft enthält die GUID des in-situ-Speichers, der im Postfach platziert wird. Sie können feststellen, dass es sich um einen in-situ-Speicher handelt, da die GUID nicht mit einem Präfix beginnt.  <br/> Sie können den `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` Befehl in Exchange Online PowerShell verwenden, um Informationen zum in-situ-Speicher für das Postfach abzurufen.  <br/> |
| Office 365 von Aufbewahrungsrichtlinien im Security #a0 Compliance Center, die auf bestimmte Postfächer angewendet werden  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> oder  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Wenn Sie das Cmdlet **Get-Mailbox** ausführen, enthält die *InPlaceHolds* -Eigenschaft auch GUIDs Office 365 auf das Postfach angewendeten Aufbewahrungsrichtlinien. Sie können Aufbewahrungsrichtlinien identifizieren, da die GUID mit `mbx` dem Präfix beginnt. Beachten Sie, dass, wenn die GUID der Aufbewahrungsrichtlinie `skp` mit dem Präfix beginnt, dies darauf hinweist, dass die Aufbewahrungsrichtlinie auf Skype for Business Unterhaltungen angewendet wird.  <br/> Führen Sie den folgenden Befehl in Security #a0 Compliance Center PowerShell aus, um die Office 365-Aufbewahrungsrichtlinie zu identifizieren, die auf das Postfach angewendet wird: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Entfernen Sie die Präfix  `mbx` oder  `skp`, wenn Sie diesen Befehl ausführen.  <br/> |
|Organisationsweite Office 365 von Aufbewahrungsrichtlinien im Security #a0 Compliance Center  <br/> |Kein Wert  <br/> oder  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`(gibt an, dass das Postfach von einer organisationsweiten Richtlinie ausgeschlossen wird)  <br/> |Auch wenn die *InPlaceHolds* -Eigenschaft leer ist, wenn Sie das Cmdlet **Get-Mailbox** ausführen, kann es dennoch eine oder mehrere organisationsweite Office 365 auf das Postfach angewendete Aufbewahrungsrichtlinien geben.  <br/> Um dies zu überprüfen, können Sie `Get-OrganizationConfig | FL InPlaceHolds` den Befehl in Exchange Online PowerShell ausführen, um eine Liste der GUIDs für organisationsweite Office 365-Aufbewahrungsrichtlinien zu erhalten. Die GUID für organisationsweite Aufbewahrungsrichtlinien, die auf Exchange-Postfächer `mbx` angewendet werden, beginnt mit dem Präfix; zum Beispiel `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> Führen Sie den folgenden Befehl in Security #a0 Compliance Center PowerShell aus, um die organisationsweite Office 365-Aufbewahrungsrichtlinie zu identifizieren, die auf das Postfach angewendet wird: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Beachten Sie Folgendes: Wenn ein Postfach aus einer organisationsweiten Office 365 Aufbewahrungsrichtlinie ausgeschlossen wird, wird die GUID für die Aufbewahrungsrichtlinie in der *InPlaceHolds* -Eigenschaft des Postfachs des Benutzers angezeigt, wenn Sie das Cmdlet **Get-Mailbox** ausführen. Sie wird durch das Präfix `-mbx`identifiziert; Zum Beispiel`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|eDiscovery-Aufbewahrungs Fall im Security #a0 Compliance Center  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |Die *InPlaceHolds* -Eigenschaft enthält auch die GUID aller Halterungen, die einem eDiscovery-Fall im Security #a0 Compliance Center zugeordnet sind, das möglicherweise in das Postfach eingefügt wird. Sie können erkennen, dass es sich hierbei um einen eDiscovery-Fall handelt, da die GUID mit dem Präfix  `UniH` beginnt.  <br/> Sie können das `Get-CaseHoldPolicy` Cmdlet in Security #a0 Compliance Center PowerShell verwenden, um Informationen zu dem eDiscovery-Fall abzurufen, dem der Aufbewahrungs Status für das Postfach zugeordnet ist. Beispielsweise können Sie den Befehl `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` ausführen, um den Namen des Aufbewahrungs Falls im Postfach anzuzeigen. Be sure to remove the  `UniH`, wenn Sie diesen Befehl ausführen.  <br/><br/> Führen Sie die folgenden Befehle aus, um den eDiscovery-Fall zu identifizieren, dem der Haltebereich für das Postfach zugeordnet ist:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


