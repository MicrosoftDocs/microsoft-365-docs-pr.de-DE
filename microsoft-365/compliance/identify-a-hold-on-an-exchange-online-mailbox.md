---
title: Identifizieren des Haltebereichs für ein Exchange Online-Postfach
f1.keywords:
- NOCSH
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
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: Hier erfahren Sie, wie Sie die verschiedenen Aufbewahrungs Typen identifizieren können, die in einem Microsoft 365-Postfach gespeichert werden können. Zu diesen Aufbewahrungsarten zählen Beweissicherungsverfahren, eDiscovery-Haltestatus und Microsoft 365-Aufbewahrungsrichtlinien. Sie können auch ermitteln, ob ein Benutzer von einer unternehmensweiten Aufbewahrungsrichtlinie ausgeschlossen wurde.
ms.openlocfilehash: 331fd37f48e42666ceb33a2a751b7d7a7a945e4b
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352314"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Identifizieren des Haltebereichs für ein Exchange Online-Postfach

In diesem Artikel wird erläutert, wie Sie in Exchange Online Postfächern in Microsoft 365 aufbewahrte haltebereiche identifizieren können.

Microsoft 365 bietet verschiedene Möglichkeiten, mit denen Ihre Organisation verhindern kann, dass Postfachinhalte endgültig gelöscht werden. Auf diese Weise kann Ihre Organisation Inhalte beibehalten, um Compliance-Vorschriften oder rechtliche und andere Arten von Untersuchungen einzuhalten. Im folgenden finden Sie eine Liste der Aufbewahrungs Features (auch " *Holds*" genannt) in Office 365:

- ** [Beweissicherungsverfahren](create-a-litigation-hold.md):** Haltestatus, die auf Benutzerpostfächer in Exchange Online angewendet werden.

- ** [eDiscovery-Aufbewahrung](create-ediscovery-holds.md):** Hält, die einem zentralen eDiscovery-Fall im Security and Compliance Center zugeordnet sind. eDiscovery-Haltestatus können auf Benutzerpostfächer und auf das entsprechende Postfach für Microsoft 365-Gruppen und Microsoft Teams angewendet werden.

- ** [In-situ-](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds)Speicher:** Gilt für Benutzerpostfächer, die mithilfe des in-situ-eDiscovery-&-halte Tools im Exchange Admin Center in Exchange Online angewendet werden.

- ** [Microsoft 365-Aufbewahrungsrichtlinien](retention-policies.md):** Kann so konfiguriert werden, dass Inhalte in Benutzerpostfächern in Exchange Online und im entsprechenden Postfach für Microsoft 365-Gruppen und Microsoft Teams beibehalten (oder beibehalten und anschließend gelöscht werden). Sie können auch eine Aufbewahrungsrichtlinie erstellen, um Skype for Business Unterhaltungen beizubehalten, die in Benutzerpostfächern gespeichert sind.

  Es gibt zwei Arten von Microsoft 365-Aufbewahrungsrichtlinien, die Postfächern zugewiesen werden können.

    - **Spezifische Aufbewahrungsrichtlinien für Standorte:** Hierbei handelt es sich um Richtlinien, die den Inhaltsspeicherorten bestimmter Benutzer zugewiesen sind. Verwenden Sie das Cmdlet **Get-Mailbox** in Exchange Online PowerShell, um Informationen zu Aufbewahrungsrichtlinien abzurufen, die bestimmten Postfächern zugewiesen sind.

    - **Organisationsweite Aufbewahrungsrichtlinien:** Dabei handelt es sich um Richtlinien, die allen Inhaltsspeicherorten in Ihrer Organisation zugewiesen sind. Verwenden Sie das Cmdlet **Get-OrganizationConfig** in Exchange Online PowerShell, um Informationen zu organisationsweiten Aufbewahrungsrichtlinien zu erhalten.
    
  Weitere Informationen finden Sie unter [Anwenden einer Aufbewahrungsrichtlinie auf eine gesamte Organisation oder einen bestimmten Speicherort](create-retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations) Abschnitt.

- **[Microsoft 365-Aufbewahrungs Bezeichnungen](labels.md):** wenn ein Benutzer eine Microsoft 365-Aufbewahrungs Bezeichnung anwendet (eine, die für das Aufbewahren von Inhalten oder das aufbewahren und Löschen von Inhalten konfiguriert ist *), wird* ein Aufbewahrungsplatz im Postfach abgelegt, als ob das Postfach in einem Beweissicherungsverfahren abgelegt oder einer Microsoft 365-Aufbewahrungsrichtlinie zugewiesen wurde. Weitere Informationen finden Sie unter [Identifizieren von Postfächern in der Warteschleife, da eine Aufbewahrungs Bezeichnung auf einen Ordner oder ein Element](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) Abschnitt in diesem Artikel angewendet wurde.

Zum Verwalten von Postfächern müssen Sie möglicherweise den Aufbewahrungs für ein Postfach identifizieren, sodass Sie Aufgaben wie das Ändern der Aufbewahrungsdauer, vorübergehendes oder dauerhaftes Entfernen des haltebereichs oder Ausschließen eines Postfachs aus einer Microsoft 365-Aufbewahrungsrichtlinie ausführen können. In diesen Fällen besteht der erste Schritt darin, den Typ des für das Postfach gelegten Haltestatus zu identifizieren. Da mehrere haltebereiche (und unterschiedliche Aufbewahrungs Typen) in einem einzelnen Postfach gespeichert werden können, müssen Sie alle in einem Postfach gelegenen Aufbewahrungsfristen identifizieren, wenn Sie das Archiv entfernen oder ändern möchten.

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>Schritt 1: Abrufen der GUID für in einem Postfach gelegte Haltestatus

Sie können die folgenden zwei Cmdlets in Exchange Online PowerShell ausführen, um die GUID der Haltestatus abzurufen, die in einem Postfach gespeichert werden. Nachdem Sie eine GUID abgerufen haben, verwenden Sie Sie, um den bestimmten Haltebereich in Schritt 2 zu identifizieren. Ein Beweissicherungsverfahren wird nicht durch eine GUID identifiziert. Beweissicherungsverfahren sind für ein Postfach entweder aktiviert oder deaktiviert.

- **Get-Mailbox:** Verwenden Sie dieses Cmdlet, um zu ermitteln, ob das Beweissicherungsverfahren für ein Postfach aktiviert ist, und um die GUIDs für eDiscovery Holds, in-situ-Speicher und Microsoft 365-Aufbewahrungsrichtlinien abzurufen, die speziell einem Postfach zugewiesen sind. Die Ausgabe dieses Cmdlets gibt außerdem an, ob ein Postfach explizit von einer Aufbewahrungsrichtlinie für die Organisation ausgeschlossen wurde.

- **Get-OrganizationConfig:** Verwenden Sie dieses Cmdlet, um die GUIDs für organisationsweite Aufbewahrungsrichtlinien abzurufen.

Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

### <a name="get-mailbox"></a>Get-Mailbox

Führen Sie den folgenden Befehl aus, um Informationen zu den Haltebereichen und den Microsoft 365-Aufbewahrungsrichtlinien zu erhalten, die auf ein Postfach angewendet werden.

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Wenn die InPlaceHolds-Eigenschaft zu viele Werte enthält und nicht alle angezeigt werden, können Sie den `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` Befehl ausführen, um die einzelnen GUIDs in einer separaten Zeile anzuzeigen.

In der folgenden Tabelle wird beschrieben, wie Sie unterschiedliche Aufbewahrungs Typen basierend auf den Werten in der *InPlaceHolds* -Eigenschaft identifizieren, wenn Sie das Cmdlet **Get-Mailbox** ausführen.


|Haltebereichstyp  |Beispielwert  |Vorgehensweise zum Identifizieren des Haltestatus  |
|---------|---------|---------|
|Aufbewahrung für eventuelle Rechtsstreitigkeiten     |    `True`     |     Das Beweissicherungsverfahren ist für ein Postfach aktiviert, wenn die *LitigationHoldEnabled* -Eigenschaft auf festgelegt ist `True` .    |
|eDiscovery-Aufbewahrung     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   Die *InPlaceHolds-Eigenschaft* enthält die GUID aller Halterungen, die einem eDiscovery-Fall im Security and Compliance Center zugeordnet sind. Sie können feststellen, dass es sich um einen eDiscovery-Speicher handelt, da die GUID mit dem `UniH` Präfix beginnt (das einen einheitlichen Haltestatus bezeichnet).      |
|Compliance-Archiv     |     `c0ba3ce811b6432a8751430937152491` <br/> oder <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     Die *InPlaceHolds* -Eigenschaft enthält die GUID des in-situ-Speichers, der im Postfach platziert wird. Sie können feststellen, dass es sich um einen in-situ-Speicher handelt, da die GUID entweder nicht mit einem Präfix beginnt oder mit dem `cld` Präfix beginnt.     |
|Microsoft 365-Aufbewahrungsrichtlinie, die speziell auf das Postfach angewendet wird     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> oder <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     Die InPlaceHolds-Eigenschaft enthält GUIDs einer bestimmten Aufbewahrungsrichtlinie für Standorte, die auf das Postfach angewendet wird. Sie können Aufbewahrungsrichtlinien identifizieren, da die GUID mit dem `mbx` oder dem `skp` Präfix beginnt. Das `skp` Präfix gibt an, dass die Aufbewahrungsrichtlinie auf Skype for Business Unterhaltungen im Postfach des Benutzers angewendet wird.    |
|Von einer organisationsweiten Microsoft 365-Aufbewahrungsrichtlinie ausgeschlossen     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Wenn ein Postfach aus einer organisationsweiten Microsoft 365-Aufbewahrungsrichtlinie ausgeschlossen wird, wird die GUID für die Aufbewahrungsrichtlinie, von der das Postfach ausgeschlossen wird, in der InPlaceHolds-Eigenschaft angezeigt und durch das `-mbx` Präfix identifiziert.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Wenn die *InPlaceHolds* -Eigenschaft leer ist, wenn Sie das Cmdlet **Get-Mailbox** ausführen, kann es immer noch eine oder mehrere organisationsweite Microsoft 365-Aufbewahrungsrichtlinien auf das Postfach angewendet werden. Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Liste von GUIDs für organisationsweite Microsoft 365-Aufbewahrungsrichtlinien zu erhalten.

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Wenn die InPlaceHolds-Eigenschaft zu viele Werte enthält und nicht alle angezeigt werden, können Sie den `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` Befehl ausführen, um die einzelnen GUIDs in einer separaten Zeile anzuzeigen.

In der folgenden Tabelle werden die unterschiedlichen Typen von organisationsweiten Haltebereichen beschrieben, und Sie können jeden Typ basierend auf den in der *InPlaceHolds* -Eigenschaft enthaltenen GUIDs identifizieren, wenn Sie das Cmdlet **Get-OrganizationConfig** ausführen.


|Haltebereichstyp  |Beispielwert  |Beschreibung  |
|---------|---------|---------|
|Microsoft 365-Aufbewahrungsrichtlinien, die auf Exchange-Postfächer, öffentliche Exchange-Ordner und Chats von Teams angewendet werden    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   Organisationsweite Aufbewahrungsrichtlinien, die auf Exchange-Postfächer, öffentliche Exchange-Ordner und 1xN-Chats in Microsoft Teams angewendet werden, werden durch GUIDs identifiziert, die mit dem `mbx` Präfix beginnen. Hinweis 1xN-Chats werden im Postfach der einzelnen Chat Teilnehmer gespeichert.      |
|Microsoft 365-Aufbewahrungsrichtlinie, die auf Microsoft 365-Gruppen und Teams-Kanal Nachrichten angewendet wird     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    Organisationsweite Aufbewahrungsrichtlinien, die auf Microsoft 365-Gruppen und Kanal Nachrichten in Microsoft Teams angewendet werden, werden durch GUIDs identifiziert, die mit dem `grp` Präfix beginnen. Hinweis Kanal Nachrichten werden im Gruppenpostfach gespeichert, das einem Microsoft-Team zugeordnet ist.     |

Weitere Informationen zu Aufbewahrungsrichtlinien, die auf Microsoft Teams angewendet werden, finden Sie im Abschnitt "Teams-Standort" unter [Übersicht über Aufbewahrungsrichtlinien](create-retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Grundlegendes zum Format des InPlaceHolds-Werts für Aufbewahrungsrichtlinien

Zusätzlich zum Präfix (MBX, SKP oder GRP), das ein Element in der InPlaceHolds-Eigenschaft als Microsoft 365-Aufbewahrungsrichtlinie identifiziert, enthält der Wert auch ein Suffix, das den Typ der Aufbewahrungsaktion identifiziert, die für die Richtlinie konfiguriert ist. Beispielsweise wird das Aktions Suffix in den folgenden Beispielen fett dargestellt:

   `skp127d7cf1076947929bf136b7a2a8c36f`**: 1**

   `mbx7cfb30345d454ac0a989ab3041051209`**: 2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**: 3**

In der folgenden Tabelle werden die drei möglichen Aufbewahrungsaktionen definiert:

|Wert  |Beschreibung  |
|---------|---------|
|**1**     | Gibt an, dass die Aufbewahrungsrichtlinie zum Löschen von Elementen konfiguriert ist. Die Richtlinie behält keine Elemente bei.        |
|**2**    |    Gibt an, dass die Aufbewahrungsrichtlinie zum Speichern von Elementen konfiguriert ist. Die Richtlinie löscht keine Elemente nach Ablauf des Aufbewahrungszeitraums.     |
|**3**     |   Gibt an, dass die Aufbewahrungsrichtlinie so konfiguriert ist, dass Sie Elemente aufbewahrt und anschließend nach Ablauf des Aufbewahrungszeitraums gelöscht wird.      |

Weitere Informationen zu Aufbewahrungsaktionen finden Sie im Abschnitt "Aufbewahrung von Inhalten für einen bestimmten Zeitraum" in Übersicht über [Aufbewahrungsrichtlinien](create-retention-policies.md#retaining-content-for-a-specific-period-of-time).
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>Schritt 2: Verwenden der GUID zum Identifizieren des Haltestatus

Nachdem Sie die GUID für einen auf ein Postfach angewendeten Haltestatus abgerufen haben, besteht der nächste Schritt darin, diese GUID zum Identifizieren des Haltestatus zu verwenden. In den folgenden Abschnitten wird gezeigt, wie Sie den Namen des Haltestatus (und andere Informationen) mithilfe der Hold-GUID identifizieren.

### <a name="ediscovery-holds"></a>eDiscovery-Aufbewahrung

Führen Sie die folgenden Befehle in Security & Compliance Center PowerShell aus, um einen eDiscovery-Speicher zu identifizieren, der auf das Postfach angewendet wird. Verwenden Sie die GUID (ohne das UniH-Präfix) für den eDiscovery-Haltebereich, den Sie in Schritt 1 identifiziert haben. Der erste Befehl erstellt eine Variable, die Informationen zum Haltestatus enthält. Diese Variable wird in den anderen Befehlen verwendet. Der zweite Befehl zeigt den Namen des eDiscovery-Falls an, dem der Haltebereich zugeordnet ist. Der dritte Befehl zeigt den Namen des Haltestatus und eine Liste der Postfächer an, für die der Aufbewahrungsplatz gilt.

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

Informationen zum Herstellen einer Verbindung mit Security & Compliance Center PowerShell finden Sie unter [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

### <a name="in-place-holds"></a>In-Situ-Speicher

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um den in-situ-Speicher zu identifizieren, der auf das Postfach angewendet wird. Verwenden Sie die GUID für den in-situ-Speicher, den Sie in Schritt 1 identifiziert haben. Der Befehl zeigt den Namen des Haltestatus und eine Liste der Postfächer an, für die der Aufbewahrungsplatz gilt.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

Wenn die GUID für den in-situ-Speicher mit dem `cld` Präfix beginnt, achten Sie darauf, das Präfix beim Ausführen des vorherigen Befehls einzubeziehen.

> [!IMPORTANT]
> Da wir weiterhin auf verschiedene Arten investieren, um Postfachinhalte beizubehalten, kündigen wir den Ruhestand von in-Place-Speicher in der Exchange-Verwaltungskonsole an. Ab dem 1. Juli 2020 können Sie in Exchange Online keine neuen in-Place-Aufbewahrungsorte erstellen. Sie können jedoch weiterhin in-Place-Speicher in der Exchange-Verwaltungskonsole oder mithilfe des Cmdlets " **MailboxSearch** " in Exchange Online PowerShell verwalten. Ab dem 1. Oktober 2020 können Sie jedoch keine in-Place-Speicher verwalten. Sie werden nur in der Exchange-Verwaltungskonsole oder mithilfe des Cmdlets **Remove-MailboxSearch** entfernt. Weitere Informationen zum Ruhestand von in-Place-Archiven finden Sie unter [Retirement of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md).

### <a name="microsoft-365-retention-policies"></a>Microsoft 365-Aufbewahrungsrichtlinien

Führen Sie den folgenden Befehl in Security & Compliance Center PowerShell aus, um die Microsoft 365-Aufbewahrungsrichtlinie (organisationsweit oder an einem bestimmten Speicherort) zu identifizieren, die auf das Postfach angewendet wird. Verwenden Sie die GUID (ohne das in Schritt 1 identifizierte MBX-, SKP-oder GfK-Präfix oder das Aktions Suffix).

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Identifizieren von Postfächern in der Warteschleife, da eine Aufbewahrungs Bezeichnung auf einen Ordner oder ein Element angewendet wurde

Wenn ein Benutzer eine Aufbewahrungs Bezeichnung anwendet, die so konfiguriert ist, dass Inhalte beibehalten oder beibehalten und anschließend Inhalt in einem beliebigen Ordner oder Element in seinem Postfach gelöscht werden, wird die *ComplianceTagHoldApplied* -Postfacheigenschaft auf **true**festgelegt. Wenn dies geschieht, wird das Postfach als in der Warteschleife gehalten, als ob es in das Beweissicherungsverfahren gestellt oder einer Microsoft 365-Aufbewahrungsrichtlinie zugewiesen wurde. Wenn die *ComplianceTagHoldApplied* -Eigenschaft auf **true**festgelegt ist, können die folgenden Dinge auftreten:

- Wenn das Postfach oder das Benutzerkonto des Benutzers gelöscht wird, wird das Postfach zu einem [inaktiven Postfach](inactive-mailboxes-in-office-365.md).
- Sie können das Postfach nicht deaktivieren (entweder das primäre Postfach oder das Archivpostfach, sofern es aktiviert ist).
- Elemente im Postfach können länger als erwartet aufbewahrt werden. Dies liegt daran, dass das Postfach in der Warteschleife ist und daher keine Elemente endgültig gelöscht (bereinigt) werden.

Um den Wert der *ComplianceTagHoldApplied* -Eigenschaft anzuzeigen, führen Sie den folgenden Befehl in Exchange Online PowerShell aus:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Weitere Informationen zu Aufbewahrungs Bezeichnungen finden Sie unter [Overview of Microsoft 365 Retention Labels](labels.md).

## <a name="managing-mailboxes-on-delay-hold"></a>Verwalten von Postfächern in Verzögerungs speichern

Nachdem ein Aufbewahrungs aus einem Postfach entfernt wurde, wird ein *Verzögerungs* Speicher angewendet. Dies bedeutet, dass die tatsächliche Entfernung des Haltestatus für 30 Tage verzögert wird, um zu verhindern, dass Daten endgültig aus dem Postfach gelöscht (bereinigt) werden. Dadurch erhalten Administratoren die Möglichkeit, Postfachelemente zu suchen oder wiederherzustellen, die nach dem Entfernen eines Haltestatus gelöscht werden. Das nächste Mal, wenn der Assistent für verwaltete Ordner das Postfach verarbeitet und festgestellt hat, dass ein Haltebereich entfernt wurde, wird ein Verzögerungs Speicher für ein Postfach festgehalten. Insbesondere wird eine Verzögerungs Sperre auf ein Postfach angewendet, wenn der Assistent für verwaltete Ordner eine der folgenden Postfacheigenschaften auf **true**festlegt:

- **DelayHoldApplied:** Diese Eigenschaft bezieht sich auf e-Mail-bezogene Inhalte (die von Personen mit Outlook und Outlook im Internet generiert werden), die im Postfach eines Benutzers gespeichert sind.

- **DelayReleaseHoldApplied:** Diese Eigenschaft bezieht sich auf cloudbasierten Inhalte (die von nicht-Outlook-apps wie Microsoft Teams, Microsoft Forms und Microsoft jammern generiert werden), die im Postfach eines Benutzers gespeichert sind. Von einer Microsoft-App generierte clouddaten werden normalerweise in einem verborgenen Ordner im Postfach eines Benutzers gespeichert.
 
 Wenn ein Verzögerungs Speicher für das Postfach gesetzt wird (wenn eine der vorherigen Eigenschaften auf " **true**" festgelegt ist), wird das Postfach weiterhin für eine unbegrenzte Aufbewahrungsdauer als aufbewahrt, als ob das Postfach das Beweissicherungsverfahren aufweist. Nach 30 Tagen läuft die Verzögerungsdauer ab, und Microsoft 365 versucht automatisch, die Verzögerungszeit zu entfernen (indem die DelayHoldApplied-oder DelayReleaseHoldApplied-Eigenschaft auf **false**festgelegt wird), sodass der Haltebereich entfernt wird. Nachdem eine dieser Eigenschaften auf " **false**" festgelegt wurde, werden die entsprechenden Elemente, die zum Entfernen markiert sind, beim nächsten verarbeiten des Postfachs vom Assistenten für verwaltete Ordner gelöscht.

Um die Werte für die Eigenschaften DelayHoldApplied und DelayReleaseHoldApplied für ein Postfach anzuzeigen, führen Sie den folgenden Befehl in Exchange Online PowerShell aus.

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

Um die Verzögerung zu entfernen, bevor Sie abläuft, können Sie je nach der Eigenschaft, die Sie ändern möchten, ein (oder beide) die folgenden Befehle in Exchange Online PowerShell ausführen: 
 
```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Oder
 
```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Sie müssen die Rolle "Legal Hold" in Exchange Online zugewiesen haben, um die Parameter *RemoveDelayHoldApplied* oder *RemoveDelayReleaseHoldApplied* zu verwenden. 

Um die Verzögerung für ein inaktives Postfach zu entfernen, führen Sie einen der folgenden Befehle in Exchange Online PowerShell aus:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

Oder

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> Die beste Möglichkeit zum Angeben eines inaktiven Postfachs im vorherigen Befehl ist die Verwendung des Distinguished Name oder Exchange GUID-Werts. Durch Verwenden eines dieser Werte können Sie verhindern, versehentlich das falsche Postfach anzugeben. 

Weitere Informationen zur Verwendung dieser Parameter zum Verwalten von Verzögerungs speichern finden Sie unter [festlegen-Postfach](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).

Beachten Sie beim Verwalten eines Postfachs bei Verzögerung die folgenden Punkte:

- Wenn die DelayHoldApplied-oder die DelayReleaseHoldApplied-Eigenschaft auf **true** festgelegt ist und ein Postfach (oder das entsprechende Benutzerkonto) gelöscht wird, wird das Postfach zu einem inaktiven Postfach. Das liegt daran, dass ein Postfach als gesperrt gilt, wenn eine der beiden Eigenschaften auf " **true**" festgelegt ist, und das Löschen eines Postfachs in einem Haltestatus ein inaktives Postfach ergibt. Um ein Postfach zu löschen und es nicht zu einem inaktiven Postfach zu machen, müssen Sie beide Eigenschaften auf **false**festlegen.

- Wie bereits erwähnt, wird ein Postfach für eine unbegrenzte Aufbewahrungsdauer als in der Warteschleife betrachtet, wenn entweder die DelayHoldApplied-oder die DelayReleaseHoldApplied-Eigenschaft auf **true**festgelegt ist. Dies bedeutet jedoch nicht, dass *alle* Inhalte im Postfach beibehalten werden. Dies hängt vom Wert ab, der auf die einzelnen Eigenschaften festgelegt wird. Angenommen, beide Eigenschaften sind auf **true** festgelegt, da haltebereiche aus dem Postfach entfernt werden. Anschließend entfernen Sie nur die Warteschleife, die auf nicht-Outlook-clouddaten angewendet wird (mithilfe des *RemoveDelayReleaseHoldApplied* -Parameters). Wenn der Assistent für verwaltete Ordner das nächste Mal das Postfach verarbeitet, werden die zum Entfernen markierten nicht-Outlook-Elemente gelöscht. Alle zum Entfernen markierten Outlook-Elemente werden nicht gelöscht, da die DelayHoldApplied-Eigenschaft weiterhin auf **true**festgelegt ist. Das Gegenteil wäre auch der Fall: Wenn DelayHoldApplied auf **false** festgelegt ist und DelayReleaseHoldApplied auf **true**festgelegt ist, werden nur Outlook-Elemente, die zum Entfernen markiert sind, gelöscht.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die auf ein Postfach angewendeten Haltestatus identifiziert haben, können Sie Aufgaben wie das Ändern der Aufbewahrungsdauer, das vorübergehende oder permanente Entfernen des Haltestatus oder das Ausschließen eines inaktiven Postfachs aus einer Microsoft 365-Aufbewahrungsrichtlinie ausführen. Weitere Informationen zum Durchführen von Aufgaben im Zusammenhang mit Holds finden Sie in einem der folgenden Themen:

- Führen Sie das>-Befehl für das [ \< Benutzerpostfach "festlegen-RetentionCompliancePolicy-AddExchangeLocationException](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy?view=exchange-ps) " in Security & Compliance Center PowerShell aus, um ein Postfach aus einer organisationsweiten Microsoft 365-Aufbewahrungsrichtlinie auszuschließen. Dieser Befehl kann nur für Aufbewahrungsrichtlinien verwendet werden, bei denen der Wert für die *ExchangeLocation* -Eigenschaft gleich ist `All` .

- Führen Sie die [ExcludeFromOrgHolds \< Hold-GUID ohne Präfix oder Suffix>](https://docs.microsoft.com/powershell/module/exchange/set-mailbox?view=exchange-ps) Befehl in Exchange Online PowerShell aus, um ein inaktives Postfach aus einer organisationsweiten Microsoft 365-Aufbewahrungsrichtlinie auszuschließen.

- [Ändern der Aufbewahrungsdauer für ein inaktives Postfach](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Löschen eines inaktiven Postfachs](delete-an-inactive-mailbox.md)

- [Löschen von Elementen im Ordner „Wiederherstellbare Elemente“ für cloudbasierte aufzubewahrende Postfächer](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
