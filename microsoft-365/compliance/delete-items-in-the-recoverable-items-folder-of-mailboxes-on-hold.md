---
title: Löschen von Elementen im Ordner "Cloud Mailbox" in "Wiederherstellbare Elemente speichern" – Administratorhilfe
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
description: 'Für Administratoren: Elemente im Ordner "Wiederherstellbare Elemente" eines Benutzers für ein Exchange Online Postfach löschen, auch wenn das Postfach legal aufbewahrt wird. Dies ist eine effektive Möglichkeit zum Löschen von Daten, die versehentlich in Microsoft 365 verschüttet wurden.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 223c589d191eef14662b7e19aa5ed113db9ff3b2
ms.sourcegitcommit: 252b1d1d8ae735b99bf46e27c08353afc330aef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232059"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>Löschen von Elementen im Ordner "Wiederherstellbare Elemente" von cloudbasierten Postfächern in der Warteschleife – Administratorhilfe

Der Ordner "refundable Items" für ein Exchange Online Postfach ist vorhanden, um vor versehentlichen oder böswilligen Löschungen zu schützen. Es wird auch verwendet, um Elemente zu speichern, die von Compliance-Features wie Holds und eDiscovery-suchen aufbewahrt werden und auf die zugegriffen werden kann. In einigen Situationen können Organisationen jedoch Daten haben, die versehentlich im Ordner "Wiederherstellbare Elemente" aufbewahrt werden, den Sie löschen müssen. Beispielsweise kann ein Benutzer unwissentlich eine e-Mail-Nachricht senden oder weiterleiten, die vertrauliche Informationen oder Informationen enthält, die möglicherweise schwerwiegende geschäftliche Konsequenzen haben. Selbst wenn die Nachricht dauerhaft gelöscht wird, kann Sie auf unbestimmte Zeit aufbewahrt werden, da im Postfach ein rechtlicher Aufbewahrungsplatz gespeichert wurde. Dieses Szenario wird als Datenüberlauf bezeichnet, da Daten versehentlich in Office 365 verschüttet wurden. In diesen Situationen können Sie Elemente im Ordner "Wiederherstellbare Elemente" eines Benutzers für ein Exchange Online Postfach löschen, auch wenn das Postfach mit einem der unterschiedlichen Hold-Features in Office 365 in den Haltestatus versetzt wird. Zu diesen Aufbewahrungsarten zählen Beweissicherungsverfahren, in-Place-Speicher, eDiscovery-Haltestatus und im Security and Compliance Center in Office 365 oder Microsoft 365 erstellte Aufbewahrungsrichtlinien.
  
 In diesem Artikel wird erläutert, wie Sie Elemente aus dem Ordner "Wiederherstellbare Elemente" für in der Warteschleife verhaltene Cloud-basierte Postfächer löschen. Dieses Verfahren umfasst das Deaktivieren des Zugriffs auf das Postfach und das Deaktivieren der Wiederherstellung einzelner Elemente, das Deaktivieren des Assistenten für verwaltete Ordner für die Verarbeitung des Postfachs, das vorübergehende Entfernen des haltebereichs, das Löschen von Elementen aus dem Ordner "Wiederherstellbare Elemente" und das anschließende Zurücksetzen des Postfachs auf die vorherige Konfiguration. Hier ist der Prozess: 
  
[Schritt 1: Erfassen von Informationen zum Postfach](#step-1-collect-information-about-the-mailbox)

[Schritt 2: Vorbereiten des Postfachs](#step-2-prepare-the-mailbox)

[Schritt 3: Entfernen aller Haltestatus aus dem Postfach](#step-3-remove-all-holds-from-the-mailbox)

[Schritt 4: Entfernen der Verzögerungs Sperre aus dem Postfach](#step-4-remove-the-delay-hold-from-the-mailbox)

[Schritt 5: Löschen von Elementen im Ordner "Wiederherstellbare Elemente"](#step-5-delete-items-in-the-recoverable-items-folder)

[Schritt 6: Zurücksetzen des Postfachs in den vorherigen Zustand](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Die in diesem Artikel beschriebenen Verfahren führen dazu, dass Daten endgültig aus einem Exchange Online Postfach gelöscht (bereinigt) werden. Das bedeutet, dass Nachrichten, die Sie aus dem Ordner "Wiederherstellbare Elemente" löschen, nicht wiederhergestellt werden können und nicht für rechtliche Ermittlungen oder andere Compliance-Zwecke zur Verfügung stehen. Wenn Sie Nachrichten aus einem Postfach löschen möchten, das im Rahmen eines beweissicherungsverfahrens, eines Compliance-Archivs, eines eDiscovery-Speichers oder einer im Security and Compliance Center erstellten Aufbewahrungsrichtlinie aufbewahrt wird, erkundigen Sie sich vor dem Entfernen des Haltestatus mit ihrer Datensatzverwaltung oder den Rechtsabteilungen. Ihre Organisation verfügt möglicherweise über eine Richtlinie, die definiert, ob ein aufbewahrtes Postfach oder ein Vorfall mit Datenüberlauf Vorrang hat. 
  
## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Zum Erstellen und Ausführen einer Inhaltssuche müssen Sie Mitglied der Rollengruppe für eDiscovery-Manager sein, oder Ihnen muss die Compliancesuche-Verwaltungsrolle zugewiesen sein. Um Nachrichten löschen zu können, müssen Sie Mitglied der Rollengruppe „Organisationsverwaltung“ sein, oder Ihnen muss die Verwaltungsrolle zum Suchen und Löschen zugewiesen sein. Informationen zum Hinzufügen von Benutzern zu einer Rollengruppe finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).

- Das in diesem Artikel beschriebene Verfahren wird nicht für inaktive Postfächer unterstützt. Das liegt daran, dass Sie nach dem Entfernen nicht erneut einen Haltestatus (oder keine Aufbewahrungsrichtlinie) auf ein inaktives Postfach anwenden können. Wenn Sie einen Haltebereich aus einem inaktiven Postfach entfernen, wird er in ein normales, vorläufig gelöschtes Postfach geändert und dauerhaft aus Ihrer Organisation gelöscht, nachdem es vom Assistenten für verwaltete Ordner verarbeitet wurde.

- Sie können dieses Verfahren nicht für ein Postfach ausführen, das einer Aufbewahrungsrichtlinie zugewiesen wurde, die mit einer Aufbewahrungs Sperre gesperrt wurde. Das liegt daran, dass Sie durch eine Aufbewahrungs Sperre verhindert werden, dass Sie das Postfach aus der Aufbewahrungsrichtlinie entfernen oder ausschließen und den Assistenten für verwaltete Ordner für das Postfach deaktivieren. Weitere Informationen zum Sperren von Aufbewahrungsrichtlinien finden Sie unter [use Preservation Lock zur Einhaltung behördlicher Anforderungen](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements).

- Wenn ein Postfach nicht in der Warteschleife abgelegt wird (oder wenn die Wiederherstellung einzelner Elemente nicht aktiviert ist), können Sie die Elemente aus dem Ordner "Wiederherstellbare Elemente" löschen. Weitere Informationen zur Vorgehensweise finden Sie unter [Suchen nach und Löschen von e-Mail-Nachrichten in Ihrer Organisation](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Schritt 1: Erfassen von Informationen zum Postfach

In diesem ersten Schritt werden ausgewählte Eigenschaften aus dem Zielpostfach gesammelt, die sich auf diese Prozedur auswirken. Achten Sie darauf, diese Einstellungen zu notieren oder in einer Textdatei zu speichern, da Sie einige dieser Eigenschaften ändern und dann wieder zu den ursprünglichen Werten in Schritt 6 zurückkehren, nachdem Sie Elemente aus dem Ordner "Wiederherstellbare Elemente" gelöscht haben. Im folgenden finden Sie eine Liste der Postfacheigenschaften, die Sie erfassen müssen.
  
- *SingleItemRecoveryEnabled* und *Parameter RetainDeletedItemsFor*. Bei Bedarf können Sie die einzelne Wiederherstellung deaktivieren und den Aufbewahrungszeitraum für gelöschte Elemente in Schritt 3 verbessern. 

- *LitigationHoldEnabled* und *InPlaceHolds*. Sie müssen alle auf dem Postfach angeordneten haltebereiche identifizieren, damit Sie Sie in Schritt 3 vorübergehend entfernen können. Im Abschnitt [Weitere Informationen](#more-information) finden Sie Tipps zum Identifizieren des Typs Hold, der möglicherweise in einem Postfach gespeichert wird. 

Darüber hinaus müssen Sie die Einstellungen für den Post Fach Clientzugriff abrufen, sodass Sie Sie vorübergehend deaktivieren können, sodass der Besitzer (oder andere Benutzer) während dieses Verfahrens nicht auf das Postfach zugreifen kann. Schließlich können Sie die aktuelle Größe und Anzahl der Elemente im Ordner "Wiederherstellbare Elemente" abrufen. Nachdem Sie Elemente im Ordner "Wiederherstellbare Elemente" in Schritt 5 gelöscht haben, verwenden Sie diese Informationen, um zu überprüfen, ob Elemente entfernt wurden.
  
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
    
4. Führen Sie den folgenden Befehl aus, um Informationen zu den auf das Postfach angewendeten Haltestatus-und Aufbewahrungsrichtlinien abzurufen.
    
    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > Wenn die *InPlaceHolds* -Eigenschaft zu viele Werte enthält und nicht alle angezeigt werden, können Sie den `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` Befehl ausführen, um jeden Wert in einer separaten Zeile anzuzeigen. 
  
5. Führen Sie den folgenden Befehl aus, um Informationen zu organisationsweiten Aufbewahrungsrichtlinien zu erhalten. 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   
   Wenn Ihre Organisation über eine unternehmensweite Aufbewahrungsrichtlinie verfügt, müssen Sie das Postfach in Schritt 3 von diesen Richtlinien ausschließen.

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

   Wenn Sie Elemente in Schritt 5 löschen, können Sie auswählen, ob Elemente im Ordner "Wiederherstellbare Elemente" im primären Archivpostfach des Benutzers gelöscht oder nicht gelöscht werden sollen. Wenn die automatisch expandierende Archivierung für das Postfach aktiviert ist, werden Elemente in einem zusätzlichen Archivpostfach nicht gelöscht.
  
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
  
4. Führen Sie den folgenden Befehl aus, um zu verhindern, dass der Assistent für verwaltete Ordner das Postfach verarbeitet. Wie bereits erläutert, können Sie den Assistenten für verwaltete Ordner nur deaktivieren, wenn keine Aufbewahrungsrichtlinie mit einer Erhaltungs Sperre auf das Postfach angewendet wird. 

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
  
 ### <a name="retention-policies-applied-to-specific-mailboxes"></a>Auf bestimmte Postfächer angewendete Aufbewahrungsrichtlinien
  
Führen Sie den folgenden Befehl in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) aus, um die Aufbewahrungsrichtlinie zu identifizieren, die auf das Postfach angewendet wird. Verwenden Sie die GUID (ohne das `mbx` `skp` Präfix oder) für die Aufbewahrungsrichtlinie, die Sie in Schritt 1 identifiziert haben. 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Nachdem Sie die Aufbewahrungsrichtlinie identifiziert haben, wechseln **Information governance** Sie \> im Security & Compliance Center zur Seite **Retentions** Informationen für die Informationsverwaltung, bearbeiten Sie die im vorherigen Schritt identifizierte Aufbewahrungsrichtlinie, und entfernen Sie das Postfach aus der Liste der Empfänger, die in der Aufbewahrungsrichtlinie enthalten sind. 
  
 ### <a name="organization-wide-retention-policies"></a>Organisationsweite Aufbewahrungsrichtlinien
  
Organisationsweite und Exchange-weite Aufbewahrungsrichtlinien werden auf jedes Postfach in der Organisation angewendet. Sie werden auf Organisationsebene (nicht auf Postfachebene) angewendet und werden zurückgegeben, wenn Sie das Cmdlet **Get-OrganizationConfig** in Schritt 1 ausführen. Führen Sie den folgenden Befehl in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) aus, um die organisationsweiten Aufbewahrungsrichtlinien zu identifizieren. Verwenden Sie die GUID (ohne das `mbx` Präfix eingeschlossen) für die organisationsweiten Aufbewahrungsrichtlinien, die Sie in Schritt 1 identifiziert haben. 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Nachdem Sie die organisationsweiten Aufbewahrungsrichtlinien identifiziert haben, wechseln Sie **Information governance** \> im Security & Compliance Center zur Registerkarte Information Governance **-Aufbewahrung** , bearbeiten Sie jede organisationsweite Aufbewahrungsrichtlinie, die Sie im vorherigen Schritt identifiziert haben, und fügen Sie das Postfach der Liste der ausgeschlossenen Empfänger hinzu. Dadurch wird das Postfach des Benutzers aus der Aufbewahrungsrichtlinie entfernt. 

### <a name="retention-labels"></a>Aufbewahrungsbezeichnungen

Wenn ein Benutzer eine Bezeichnung anwendet, die für die Aufbewahrung von Inhalten konfiguriert ist, oder die Inhalte in einem beliebigen Ordner oder Element in seinem Postfach aufbewahren und dann löschen, wird die *ComplianceTagHoldApplied* -Postfacheigenschaft auf **true**festgelegt. In diesem Fall gilt das Postfach als in der Warteschleife, als ob es in einem Beweissicherungsverfahren gespeichert oder einer Aufbewahrungsrichtlinie zugewiesen wurde.

Um den Wert der *ComplianceTagHoldApplied* -Eigenschaft anzuzeigen, führen Sie den folgenden Befehl in Exchange Online PowerShell aus:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Nachdem Sie festgestellt haben, dass ein Postfach in der Warteschleife ist, da eine Aufbewahrungs Bezeichnung auf einen Ordner oder ein Element angewendet wird, können Sie das Inhalts Such Tool im Security and Compliance Center verwenden, um nach beschrifteten Elementen mithilfe der ComplianceTag-Suchbedingung zu suchen. Weitere Informationen finden Sie im Abschnitt "Suchbedingungen" unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md#conditions-for-common-properties).

Weitere Informationen über Bezeichnungen finden Sie unter [Übersicht über Bezeichnungen](labels.md).

 ### <a name="ediscovery-holds"></a>eDiscovery-Aufbewahrung
  
Führen Sie die folgenden Befehle in [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) aus, um den Haltebereich für einen eDiscovery-Fall (so genannte *eDiscovery Holds*) zu identifizieren, der auf das Postfach angewendet wird. Verwenden Sie die GUID (ohne das `UniH` Präfix eingeschlossen) für den eDiscovery-Haltebereich, den Sie in Schritt 1 identifiziert haben. Der zweite Befehl zeigt den Namen des eDiscovery-Falls an, dem der Haltebereich zugeordnet ist. der dritte Befehl zeigt den Namen des Haltestatus an. 
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

Nachdem Sie den Namen des eDiscovery-Falls und des Haltestatus identifiziert haben, wechseln Sie zur **eDiscovery** -eDiscovery- \> **eDiscovery** Seite im Compliance Center, öffnen Sie den Fall, und entfernen Sie das Postfach aus dem Archiv. Weitere Informationen zum Identifizieren von eDiscovery-Archiven finden Sie im Abschnitt "eDiscovery-Aufbewahrungen" in [How to identify the Art of Hold in an Exchange Online Mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Schritt 4: Entfernen der Verzögerungs Sperre aus dem Postfach

Nachdem ein Aufbewahrungs aus einem Postfach entfernt wurde, wird der Wert der *DelayHoldApplied* -oder *DelayReleaseHoldApplied* -Postfacheigenschaft auf **true**festgelegt. Dies tritt auf, wenn der Assistent für verwaltete Ordner das nächste Mal das Postfach verarbeitet und erkennt, dass ein Haltebereich entfernt wurde. Dies wird als *Verzögerungs* Speicher bezeichnet und bedeutet, dass das tatsächliche Entfernen des Haltestatus für 30 Tage verzögert wird, um zu verhindern, dass Daten endgültig aus dem Postfach gelöscht werden. (Der Zweck einer Verzögerungs Sperre besteht darin, Administratoren die Möglichkeit zu geben, nach Postfachelementen zu suchen oder diese wiederherzustellen, die nach dem Entfernen eines Haltestatus gelöscht werden.)  Wenn ein Verzögerungs Speicher auf das Postfach gesetzt wird, wird das Postfach weiterhin für unbegrenzte Dauer aufbewahrt, als ob das Postfach ein Beweissicherungsverfahren aufweist. Nach 30 Tagen läuft die Verzögerungsdauer ab, und Microsoft 365 versucht automatisch, die Verzögerungszeit zu entfernen (indem die *DelayHoldApplied* -oder *DelayReleaseHoldApplied* -Eigenschaft auf **false**festgelegt wird), sodass der Haltebereich entfernt wird. Weitere Informationen zu einem Verzögerungs Speicher finden Sie im Abschnitt "Verwalten von Postfächern in Verzögerungs speichern" in [How to identify the Art of Hold in a Exchange Online Mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

Bevor Sie Elemente in Schritt 5 löschen können, müssen Sie eine Verzögerung aus dem Postfach entfernen. Ermitteln Sie zunächst, ob die Verzögerungszeit auf das Postfach angewendet wird, indem Sie den folgenden Befehl in Exchange Online PowerShell ausführen:

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

Wenn der Wert der *DelayHoldApplied* -oder der *DelayReleaseHoldApplied* -Eigenschaft auf **false**festgelegt ist, wurde ein Verzögerungs Speicher nicht auf das Postfach gesetzt. Sie können zu Schritt 5 wechseln und Elemente im Ordner "Wiederherstellbare Elemente" löschen.

Wenn der Wert der *DelayHoldApplied* -oder *DelayReleaseHoldApplied* -Eigenschaft auf **true**festgelegt ist, führen Sie einen der folgenden Befehle aus, um die Verzögerung zu entfernen:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Oder:

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Sie müssen die Rolle "Legal Hold" in Exchange Online zugewiesen haben, um den Parameter *RemoveDelayHoldApplied* oder *RemoveDelayReleaseHoldApplied* verwenden zu können.

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Schritt 5: Löschen von Elementen im Ordner "Wiederherstellbare Elemente"

Jetzt können Sie Elemente im Ordner "Wiederherstellbare Elemente" mithilfe der Cmdlets [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch) und [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction) im Security & Compliance Center tatsächlich löschen. 

Informationen dazu finden Sie unter [Suchen nach und Löschen von e-Mail-Nachrichten](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).

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
    
- Erneutes Anwenden der Aufbewahrungs-und Aufbewahrungsrichtlinien, die Sie entfernt haben.
    
- Erneutes Aktivieren des Assistenten für verwaltete Ordner zum Verarbeiten des Postfachs.
    
> [!IMPORTANT]
> Es wird empfohlen, dass Sie 24 Stunden nach der erneuten Anwendung eines Haltestatus oder einer Aufbewahrungsrichtlinie (und überprüfen, ob Sie vorhanden ist) warten, bevor Sie den Assistenten für verwaltete Ordner erneut aktivieren, um das Postfach zu verarbeiten. 
  
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

    **In-Situ-Aufbewahrung**
    
    Verwenden Sie die Exchange-Verwaltungskonsole (oder Exchange Online PowerShell), um das Postfach wieder dem in-situ-Speicher hinzuzufügen. 
    
    **Auf bestimmte Postfächer angewendete Aufbewahrungsrichtlinien**
    
    Verwenden Sie das Security & Compliance Center, um das Postfach wieder zur Aufbewahrungsrichtlinie hinzuzufügen. Wechseln Sie zur Seite Aufbewahrung von Informationen für die **Verwaltung** \> **Retention** im Security & Compliance Center, bearbeiten Sie die Aufbewahrungsrichtlinie, und fügen Sie das Postfach wieder der Liste der Empfänger hinzu, auf die die Aufbewahrungsrichtlinie angewendet wird. 
    
    **Organisationsweite Aufbewahrungsrichtlinien**
    
    Wenn Sie eine organisationsweite oder Exchange-weite Aufbewahrungsrichtlinie durch Ausschließen aus der Richtlinie entfernt haben, verwenden Sie das Sicherheits & Compliance Center, um das Postfach aus der Liste der ausgeschlossenen Benutzer zu entfernen. Wechseln Sie **Information governance** \> im Security & Compliance Center zur Registerkarte Information Governance- **Aufbewahrung** , bearbeiten Sie die organisationsweite Aufbewahrungsrichtlinie, und entfernen Sie das Postfach aus der Liste der ausgeschlossenen Empfänger. Dadurch wird die Aufbewahrungsrichtlinie erneut auf das Postfach des Benutzers angewendet. 
    
    **eDiscovery-Fall Behältern**
    
    Verwenden Sie das Security & Compliance Center, um das Postfach wieder dem Aufbewahrungsplatz hinzuzufügen, der einem eDiscovery-Fall zugeordnet ist. Wechseln Sie zur **eDiscovery** - \> **eDiscovery** -Seite, öffnen Sie die Anfrage, und fügen Sie das Postfach wieder in das Archiv ein. 
    
5. Führen Sie den folgenden Befehl aus, um dem Assistenten für verwaltete Ordner das erneute verarbeiten des Postfachs zu gestatten. Wie bereits erwähnt, wird empfohlen, dass Sie 24 Stunden nach der erneuten Anwendung eines Haltestatus oder einer Aufbewahrungsrichtlinie warten (und sich vergewissern, dass Sie vorhanden ist), bevor Sie den Assistenten für verwaltete Ordner erneut aktivieren. 

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

Wie bereits erläutert, müssen Sie alle halte-und Aufbewahrungsrichtlinien aus einem Postfach entfernen, bevor Sie die Elemente im Ordner "Wiederherstellbare Elemente" erfolgreich löschen können. 
  
|**Haltebereichstyp**|**Beispielwert**|**Vorgehensweise zum Identifizieren des Haltestatus**|
|:-----|:-----|:-----|
|Beweissicherungsverfahren  <br/> | `True` <br/> |Die  *LitigationHoldEnabled*  -Eigenschaft wird festgelegt auf  `True`.  <br/> |
|Compliance-Archiv  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |Die *InPlaceHolds* -Eigenschaft enthält die GUID des in-situ-Speichers, der im Postfach platziert wird. Sie können feststellen, dass es sich um einen in-situ-Speicher handelt, da die GUID nicht mit einem Präfix beginnt.  <br/> Sie können den `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` Befehl in Exchange Online PowerShell verwenden, um Informationen zum in-situ-Speicher für das Postfach abzurufen.  <br/> |
| Aufbewahrungsrichtlinien im Security & Compliance Center, die auf bestimmte Postfächer angewendet werden  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> oder  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Wenn Sie das Cmdlet **Get-Mailbox** ausführen, enthält die *InPlaceHolds* -Eigenschaft auch GUIDs von Aufbewahrungsrichtlinien, die auf das Postfach angewendet werden. Sie können Aufbewahrungsrichtlinien identifizieren, da die GUID mit dem `mbx` Präfix beginnt. Wenn die GUID der Aufbewahrungsrichtlinie mit dem `skp` Präfix beginnt, bedeutet dies, dass die Aufbewahrungsrichtlinie auf Skype for Business Unterhaltungen angewendet wird.  <br/> Führen Sie den folgenden Befehl in Security & Compliance Center PowerShell aus, um die Identität der auf das Postfach angewendeten Aufbewahrungsrichtlinie zu ermitteln: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Entfernen Sie die Präfix  `mbx` oder  `skp`, wenn Sie diesen Befehl ausführen.  <br/> |
|Organisationsweite Aufbewahrungsrichtlinien im Security & Compliance Center  <br/> |Kein Wert  <br/> oder  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`(gibt an, dass das Postfach von einer organisationsweiten Richtlinie ausgeschlossen wird)  <br/> |Auch wenn die *InPlaceHolds* -Eigenschaft leer ist, wenn Sie das Cmdlet **Get-Mailbox** ausführen, kann es trotzdem eine oder mehrere organisationsweite Aufbewahrungsrichtlinien geben, die auf das Postfach angewendet werden.  <br/> Um dies zu überprüfen, können Sie den `Get-OrganizationConfig | FL InPlaceHolds` Befehl in Exchange Online PowerShell ausführen, um eine Liste der GUIDs für organisationsweite Aufbewahrungsrichtlinien zu erhalten. Die GUID für organisationsweite Aufbewahrungsrichtlinien, die auf Exchange-Postfächer angewendet werden, beginnt mit dem `mbx` Präfix, beispielsweise `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> Um die organisationsweite Aufbewahrungsrichtlinie zu identifizieren, die auf das Postfach angewendet wird, führen Sie den folgenden Befehl in Security & Compliance Center PowerShell aus: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Wenn ein Postfach aus einer unternehmensweiten Aufbewahrungsrichtlinie ausgeschlossen wird, wird die GUID für die Aufbewahrungsrichtlinie in der *InPlaceHolds* -Eigenschaft des Postfachs des Benutzers angezeigt, wenn Sie das Cmdlet **Get-Mailbox** ausführen. Sie wird durch das Präfix identifiziert `-mbx` , beispielsweise`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|eDiscovery-Aufbewahrungs Fall im Security & Compliance Center  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |Die *InPlaceHolds* -Eigenschaft enthält auch die GUID aller Halterungen, die einem eDiscovery-Fall im Security & Compliance Center zugeordnet sind, das möglicherweise in das Postfach eingefügt wird. Sie können erkennen, dass es sich hierbei um einen eDiscovery-Fall handelt, da die GUID mit dem Präfix  `UniH` beginnt.  <br/> Sie können das `Get-CaseHoldPolicy` Cmdlet in Security & Compliance Center PowerShell verwenden, um Informationen zu dem eDiscovery-Fall abzurufen, dem der Aufbewahrungs Status für das Postfach zugeordnet ist. Beispielsweise können Sie den Befehl ausführen, `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` um den Namen des Aufbewahrungs Falls im Postfach anzuzeigen. Be sure to remove the  `UniH`, wenn Sie diesen Befehl ausführen.  <br/><br/> Führen Sie die folgenden Befehle aus, um den eDiscovery-Fall zu identifizieren, dem der Haltebereich für das Postfach zugeordnet ist:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


