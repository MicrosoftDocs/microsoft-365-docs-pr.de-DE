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
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie die verschiedenen Haltetypen identifizieren, die in einem Postfach Exchange Online in einem Microsoft 365.
ms.openlocfilehash: 0fdfbd4503a4ddffd2ce2dd97c6af42684aea293
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917535"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Identifizieren des Haltebereichs für ein Exchange Online-Postfach

In diesem Artikel wird erläutert, wie Haltefächer identifiziert werden, die Exchange Online Postfächern in Microsoft 365.

Microsoft 365 bietet verschiedene Möglichkeiten, wie Ihre Organisation verhindern kann, dass Postfachinhalte dauerhaft gelöscht werden. Auf diese Weise kann Ihre Organisation Inhalte zur Einhaltung von Compliancebestimmungen oder während rechtlicher und anderer Arten von Untersuchungen beibehalten. Hier ist eine Liste der Aufbewahrungsfunktionen (auch als *Haltefunktionen* bezeichnet) in Office 365:

- **[Litigation Hold](create-a-litigation-hold.md):** Haltefächer, die auf Benutzerpostfächer in einem Exchange Online.

- **[eDiscovery hold](create-ediscovery-holds.md):** Haltewerte, die einem Core eDiscovery-Fall im Security and Compliance Center zugeordnet sind. eDiscovery-Haltefächer können auf Benutzerpostfächer und das entsprechende Postfach für gruppen- und Microsoft 365 angewendet Microsoft Teams.

- **[In-Place Hold](/Exchange/security-and-compliance/create-or-remove-in-place-holds):** Haltefächer, die mithilfe des tools In-Place eDiscovery & im Exchange Admin Center in Exchange Online. 

   > [!NOTE]
   > In-Place Die Haltefächer wurden eingestellt, und Sie können keine In-Place archivieren oder auf Postfächer anwenden. Die In-Place können jedoch weiterhin auf Postfächer in Ihrer Organisation angewendet werden, weshalb sie in diesem Artikel enthalten sind. Weitere Informationen finden Sie unter [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center).

- **[Microsoft 365 Aufbewahrungsrichtlinien](retention.md):** Kann so konfiguriert werden, dass Inhalte in Benutzerpostfächern in Exchange Online und im entsprechenden Postfach für Microsoft 365-Gruppen und -Microsoft Teams. Sie können auch eine Aufbewahrungsrichtlinie zum Beibehalten Skype for Business Unterhaltungen erstellen, die in Benutzerpostfächern gespeichert sind.

  Es gibt zwei Arten von Microsoft 365 Aufbewahrungsrichtlinien, die Postfächern zugewiesen werden können.

    - **Spezifische Aufbewahrungsrichtlinien für Speicherorte:** Dies sind Richtlinien, die den Inhaltsstandorten bestimmter Benutzer zugewiesen sind. Sie verwenden das **Cmdlet Get-Mailbox** in Exchange Online PowerShell, um Informationen zu Aufbewahrungsrichtlinien zu erhalten, die bestimmten Postfächern zugewiesen sind. Weitere Informationen zu dieser Art von [Aufbewahrungsrichtlinie](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) finden Sie im Abschnitt Eine Richtlinie mit bestimmten Einschlüssen oder Ausschlüssen aus der Aufbewahrungsrichtliniendokumentation.

    - **Organisationsweite Aufbewahrungsrichtlinien:** Dies sind Richtlinien, die allen Inhaltsstandorten in Ihrer Organisation zugewiesen sind. Sie verwenden das **Cmdlet Get-OrganizationConfig** in Exchange Online PowerShell, um Informationen zu organisationsweiten Aufbewahrungsrichtlinien zu erhalten. Weitere Informationen zu dieser Art von Aufbewahrungsrichtlinie finden Sie im Abschnitt [Eine](create-retention-policies.md#a-policy-that-applies-to-entire-locations) Richtlinie, die für ganze Speicherorte gilt, in der Dokumentation zur Aufbewahrungsrichtlinie.

- **[Microsoft 365](retention.md)** Aufbewahrungsbezeichnungen: Wenn ein Benutzer eine Microsoft 365-Aufbewahrungsbezeichnung (eine Aufbewahrungsbezeichnung, die so konfiguriert ist, dass Inhalte beibehalten oder inhalte beibehalten und dann gelöscht werden) auf einen Ordner oder ein Element in ihrem Postfach angewendet, wird für das Postfach eine Aufbewahrungsaufbewahrung so platziert, als ob das Postfach in das Aufbewahrungsverfahren einbehalten oder einer Microsoft 365-Aufbewahrungsrichtlinie zugewiesen wäre.  Weitere Informationen finden Sie im Abschnitt Identifizieren von [Postfächern](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) im Haltebereich, da eine Aufbewahrungsbezeichnung auf einen Ordner oder ein Element in diesem Artikel angewendet wurde.

Um Postfächer im Haltezustand zu verwalten, müssen Sie möglicherweise den Aufbewahrungstyp für ein Postfach identifizieren, damit Sie Aufgaben wie das Ändern der Aufbewahrungsdauer, das vorübergehende oder dauerhafte Entfernen des Halteraums oder das Ausschließen eines Postfachs aus einer Microsoft 365-Aufbewahrungsrichtlinie ausführen können. In diesen Fällen besteht der erste Schritt in der Identifizierung des Typs des Archivs, der für das Postfach gilt. Und da mehrere Haltefächer (und verschiedene Arten von Haltefächern) für ein einzelnes Postfach platziert werden können, müssen Sie alle Haltefächer für ein Postfach identifizieren, wenn Sie einen Halteraum entfernen oder ändern möchten.

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>Schritt 1: Abrufen der GUID für Haltefächer in einem Postfach

Sie können die folgenden beiden Cmdlets in Exchange Online PowerShell ausführen, um die GUID der Haltefächer zu erhalten, die in einem Postfach platziert sind. Nachdem Sie eine GUID erhalten haben, verwenden Sie sie, um den spezifischen Halteraum in Schritt 2 zu identifizieren. Ein Prozesssicherungsverfahren wird von einer GUID nicht identifiziert. Die Rechtsstreitigkeiten sind für ein Postfach aktiviert oder deaktiviert.

- **Get-Mailbox:** Verwenden Sie dieses Cmdlet, um zu bestimmen, ob das Aufbewahrungsverfahren für ein Postfach aktiviert ist, und um die GUIDs für eDiscovery-Speicher, In-Place-Aufbewahrungs- und Microsoft 365-Aufbewahrungsrichtlinien zu erhalten, die speziell einem Postfach zugewiesen sind. Die Ausgabe dieses Cmdlets gibt außerdem an, ob ein Postfach explizit aus einer organisationsweiten Aufbewahrungsrichtlinie ausgeschlossen wurde.

- **Get-OrganizationConfig:** Verwenden Sie dieses Cmdlet, um die GUIDs für organisationsweite Aufbewahrungsrichtlinien zu erhalten.

Wie Sie eine Verbindung mit Exchange Online-PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

### <a name="get-mailbox"></a>Get-Mailbox

Führen Sie den folgenden Befehl aus, um Informationen zu den Aufbewahrungs- und Microsoft 365 aufbewahrungsrichtlinien zu erhalten, die auf ein Postfach angewendet werden.

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Wenn die InPlaceHolds-Eigenschaft zu viele Werte enthält und nicht alle angezeigt werden, können Sie den Befehl ausführen, um jede GUID in einer separaten `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` Zeile anzeigen zu können.

In der folgenden Tabelle wird beschrieben, wie unterschiedliche Haltetypen basierend auf den Werten in der *InPlaceHolds-Eigenschaft* identifiziert werden, wenn Sie das **Cmdlet Get-Mailbox** ausführen.

|Haltebereichstyp  |Beispielwert  |Identifizieren des Halteraums  |
|---------|---------|---------|
|Aufbewahrung für eventuelle Rechtsstreitigkeiten     |    `True`     |     Das Prozesssicherungsverfahren ist für ein Postfach aktiviert, wenn *die LitigationHoldEnabled-Eigenschaft* auf festgelegt `True` ist.    |
|eDiscovery-Hold     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   Die *InPlaceHolds-Eigenschaft* enthält die GUID eines beliebigen Halteraums, der einem eDiscovery-Fall im Security and Compliance Center zugeordnet ist. Sie können sehen, dass es sich um einen eDiscovery-Halteschutz handelt, da die GUID mit dem Präfix beginnt (das einen einheitlichen `UniH` Halteraum bezeichnet).      |
|Compliance-Archiv     |     `c0ba3ce811b6432a8751430937152491` <br/> oder <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     Die *InPlaceHolds-Eigenschaft* enthält die GUID der In-Place, die für das Postfach platziert wird. Sie können sehen, dass es sich um einen In-Place handelt, da die GUID entweder nicht mit einem Präfix oder mit dem Präfix `cld` beginnt.     |
|Microsoft 365 Aufbewahrungsrichtlinie, die speziell auf das Postfach angewendet wird     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> oder <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     Die InPlaceHolds-Eigenschaft enthält GUIDs einer bestimmten Aufbewahrungsrichtlinie für Speicherorte, die auf das Postfach angewendet werden. Sie können Aufbewahrungsrichtlinien identifizieren, da die GUID mit dem Präfix `mbx` oder dem Präfix `skp` beginnt. Das Präfix gibt an, dass die Aufbewahrungsrichtlinie auf Skype for Business `skp` Unterhaltungen im Postfach des Benutzers angewendet wird.    |
|Aus einer organisationsweiten Aufbewahrungsrichtlinie Microsoft 365 ausgeschlossen     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Wenn ein Postfach aus einer organisationsweiten Microsoft 365-Aufbewahrungsrichtlinie ausgeschlossen wird, wird die GUID für die Aufbewahrungsrichtlinie, von der das Postfach ausgeschlossen ist, in der InPlaceHolds-Eigenschaft angezeigt und durch das Präfix `-mbx` identifiziert.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Wenn die *InPlaceHolds-Eigenschaft* leer ist, wenn Sie das **Cmdlet Get-Mailbox** ausführen, wird möglicherweise weiterhin eine oder mehrere organisationsweite Microsoft 365 Aufbewahrungsrichtlinien auf das Postfach angewendet. Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Liste der GUIDs für organisationsweite aufbewahrungsrichtlinien Microsoft 365 erhalten.

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Wenn die InPlaceHolds-Eigenschaft zu viele Werte enthält und nicht alle angezeigt werden, können Sie den Befehl ausführen, um jede GUID in einer separaten `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` Zeile anzeigen zu können.

In der folgenden Tabelle werden die verschiedenen Arten von organisationsweiten Haltefächern beschrieben und beschrieben, wie Sie jeden Typ basierend auf den GUIDs in *der InPlaceHolds-Eigenschaft* identifizieren, wenn Sie das **Cmdlet Get-OrganizationConfig** ausführen.

|Haltebereichstyp  |Beispielwert  |Beschreibung  |
|---------|---------|---------|
|Microsoft 365 Aufbewahrungsrichtlinien, die Exchange Postfächern, Exchange öffentlichen Ordnern und Chats Teams werden    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   Organisationsweite Aufbewahrungsrichtlinien, die auf Exchange Postfächer, Exchange öffentliche Ordner und 1xN-Chats in Microsoft Teams angewendet werden, werden durch GUIDs identifiziert, die mit dem Präfix `mbx` beginnen. Hinweis 1xN-Chats werden im Postfach der einzelnen Chatteilnehmer gespeichert.      |
|Microsoft 365 Aufbewahrungsrichtlinie, die auf Microsoft 365 gruppen und Teams angewendet wird     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    Organisationsweite Aufbewahrungsrichtlinien, die auf Microsoft 365 Gruppen und Kanalnachrichten in Microsoft Teams werden durch GUIDs identifiziert, die mit dem Präfix `grp` beginnen. Hinweis Kanalnachrichten werden im Gruppenpostfach gespeichert, das einem Microsoft Team zugeordnet ist.     |

Weitere Informationen zu Aufbewahrungsrichtlinien, die auf Microsoft Teams angewendet werden, finden Sie [unter Learn about retention policies for Microsoft Teams](retention-policies-teams.md).

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Grundlegendes zum Format des InPlaceHolds-Werts für Aufbewahrungsrichtlinien

Neben dem Präfix (mbx, skp oder grp), das ein Element in der InPlaceHolds-Eigenschaft als Microsoft 365-Aufbewahrungsrichtlinie identifiziert, enthält der Wert auch ein Suffix, das den Typ der Aufbewahrungsaktion identifiziert, die für die Richtlinie konfiguriert ist. Das Aktionssuffix wird beispielsweise in den folgenden Beispielen fett formatiert hervorgehoben:

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

In der folgenden Tabelle werden die drei möglichen Aufbewahrungsaktionen definiert:

|Wert  |Beschreibung  |
|---------|---------|
|**1**     | Gibt an, dass die Aufbewahrungsrichtlinie zum Löschen von Elementen konfiguriert ist. Die Richtlinie behält keine Elemente bei.        |
|**2**    |    Gibt an, dass die Aufbewahrungsrichtlinie für das Halten von Elementen konfiguriert ist. Die Richtlinie löscht keine Elemente nach Ablauf des Aufbewahrungszeitraums.     |
|**3**     |   Gibt an, dass die Aufbewahrungsrichtlinie so konfiguriert ist, dass Elemente enthalten und nach Ablauf des Aufbewahrungszeitraums gelöscht werden.      |

Weitere Informationen zu Aufbewahrungsaktionen finden Sie im Abschnitt Aufbewahrung von Inhalten für einen [bestimmten](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) Zeitraum.
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>Schritt 2: Verwenden der GUID zum Identifizieren des Halteraums

Nachdem Sie die GUID für einen Halteraum erhalten haben, der auf ein Postfach angewendet wird, besteht der nächste Schritt in der Verwendung dieser GUID zum Identifizieren des Halteraums. In den folgenden Abschnitten wird gezeigt, wie Sie den Namen des Halteraums (und andere Informationen) mithilfe der Halte-GUID identifizieren.

### <a name="ediscovery-holds"></a>eDiscovery-Haltebereiche

Führen Sie die folgenden Befehle in Security & Compliance Center PowerShell aus, um ein eDiscovery-Archiv zu identifizieren, das auf das Postfach angewendet wird. Verwenden Sie die GUID (ohne das UniH-Präfix) für den eDiscovery-Halteraum, den Sie in Schritt 1 identifiziert haben. 

Eine Verbindung mit Security & Compliance Center PowerShell finden Sie [unter Verbinden security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).

Mit dem ersten Befehl wird eine Variable erstellt, die Informationen zum Halteraum enthält. Diese Variable wird in den anderen Befehlen verwendet. Der zweite Befehl zeigt den Namen des eDiscovery-Falls an, dem der Halteschutz zugeordnet ist. Der dritte Befehl zeigt den Namen des Halteraums und eine Liste der Postfächer an, für die das Archiv gilt.

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

### <a name="in-place-holds"></a>In-Situ-Speicher

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um die In-Place zu identifizieren, die auf das Postfach angewendet wird. Verwenden Sie die GUID für In-Place, die Sie in Schritt 1 identifiziert haben. Der Befehl zeigt den Namen des Halteraums und eine Liste der Postfächer an, für die der Halteraum gilt.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

Wenn die GUID für das In-Place mit dem Präfix beginnt, müssen Sie das Präfix beim Ausführen des `cld` vorherigen Befehls angeben.

> [!IMPORTANT]
> Da wir weiterhin auf unterschiedliche Weise investieren, um Postfachinhalte zu erhalten, wird die Rente von In-Place Holds im Exchange Admin Center (EAC) angekündigt. Ab dem 1. Juli 2020 können Sie keine neuen In-Place in Exchange Online. Sie können jedoch weiterhin die In-Place in der EAC oder mithilfe des **Cmdlets Set-MailboxSearch** in Exchange Online PowerShell verwalten. Ab dem 1. Oktober 2020 können Sie jedoch keine In-Place verwalten. Sie werden nur in der EAC oder mit dem **Cmdlet Remove-MailboxSearch** entfernt. Weitere Informationen zum Austritt von In-Place finden Sie unter [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).

### <a name="microsoft-365-retention-policies"></a>Microsoft 365 Aufbewahrungsrichtlinien

Führen Sie den folgenden Befehl in Security & Compliance Center PowerShell aus, um die auf das Postfach angewendete Microsoft 365-Aufbewahrungsrichtlinie (organisationsweit oder an einem bestimmten Speicherort) zu identitäten. Verwenden Sie die GUID (ohne das Präfix mbx, skp oder grp oder das Aktionssuffix), das Sie in Schritt 1 identifiziert haben.

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Identifizieren von Postfächern, die gespeichert sind, da eine Aufbewahrungsbezeichnung auf einen Ordner oder ein Element angewendet wurde

Wenn ein Benutzer eine Aufbewahrungsbezeichnung an wendet, die so konfiguriert ist, dass Inhalte beibehalten oder beibehalten und dann Inhalte auf einen Ordner oder ein Element in ihrem Postfach gelöscht werden, wird die *ComplianceTagHoldApplied-Postfacheigenschaft* auf **True festgelegt.** In diesem Fall wird das Postfach als in einem Halteverfahren betrachtet, als ob es in das Aufbewahrungsverfahren einbehalten oder einer Aufbewahrungsrichtlinie Microsoft 365 wurde. Wenn die *ComplianceTagHoldApplied-Eigenschaft* auf **True festgelegt** ist, kann Folgendes auftreten:

- Wenn das Postfach oder das Benutzerkonto des Benutzers gelöscht wird, wird das Postfach zu einem [inaktiven Postfach.](inactive-mailboxes-in-office-365.md)
- Sie können das Postfach nicht deaktivieren (entweder das primäre Postfach oder das Archivpostfach, wenn es aktiviert ist).
- Elemente im Postfach können länger aufbewahrt werden als erwartet. Dies liegt daran, dass das Postfach im Haltezustand ist und daher keine Elemente endgültig gelöscht (gelöscht) werden.

Führen Sie zum Anzeigen des Werts der *ComplianceTagHoldApplied-Eigenschaft* den folgenden Befehl in Exchange Online PowerShell aus:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Weitere Informationen zu Aufbewahrungsbezeichnungen finden Sie unter [Aufbewahrungsbezeichnungen](retention.md#retention-labels).

## <a name="managing-mailboxes-on-delay-hold"></a>Verwalten von Postfächern im Verzögerungsspeicher

Nachdem ein beliebiger Haltetyp aus einem Postfach entfernt wurde, wird ein *Verzögerungsspeicher* angewendet. Dies bedeutet, dass das tatsächliche Entfernen des Haltezustands um 30 Tage verzögert wird, um zu verhindern, dass Daten dauerhaft aus dem Postfach gelöscht (gelöscht) werden. Dadurch haben Administratoren die Möglichkeit, Postfachelemente zu suchen oder wiederherstellungen, die gelöscht werden, nachdem ein Haltebereich entfernt wurde. Ein Verzögerungsspeicher wird für ein Postfach platziert, wenn der Assistent für verwaltete Ordner das Postfach das nächste Mal verarbeitet und erkennt, dass ein Halteraum entfernt wurde. Insbesondere wird ein Verzögerungsspeicher auf ein Postfach angewendet, wenn der Assistent für verwaltete Ordner eine der folgenden Postfacheigenschaften auf **True legt:**

- **DelayHoldApplied:** Diese Eigenschaft gilt für E-Mail-bezogene Inhalte (generiert von Personen, die Outlook und Outlook im Web verwenden), die im Postfach eines Benutzers gespeichert sind.

- **DelayReleaseHoldApplied:** Diese Eigenschaft gilt für cloudbasierte Inhalte (generiert von nicht Outlook Apps wie Microsoft Teams, Microsoft Forms und Microsoft Yammer), die im Postfach eines Benutzers gespeichert sind. Von einer Microsoft-App generierte Clouddaten werden in der Regel in einem ausgeblendeten Ordner im Postfach eines Benutzers gespeichert.

Wenn für das Postfach ein Verzögerungsspeicher eingerichtet wird (wenn eine der vorherigen Eigenschaften auf **True** festgelegt ist), gilt das Postfach weiterhin als für eine unbegrenzte Haltedauer, als ob sich das Postfach im Prozesssicherungsverfahren befindet. Nach 30 Tagen läuft die Verzögerungsverzögerung ab, und Microsoft 365 versucht automatisch, die Verzögerungsverzögerung zu entfernen (indem die Eigenschaft DelayHoldApplied oder DelayReleaseHoldApplied auf **False** gesetzt wird), sodass der Halteraum entfernt wird. Nachdem eine dieser Eigenschaften auf **False** festgelegt wurde, werden die entsprechenden Elemente, die zum Entfernen markiert sind, beim nächsten Verarbeiten des Postfachs durch den Assistenten für verwaltete Ordner gelöscht.

Führen Sie zum Anzeigen der Werte für die Eigenschaften DelayHoldApplied und DelayReleaseHoldApplied für ein Postfach den folgenden Befehl in Exchange Online PowerShell aus.

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

Um die Verzögerungsverzögerung zu entfernen, bevor sie abläuft, können Sie einen (oder beide) der folgenden Befehle in Exchange Online PowerShell ausführen, je nachdem, welche Eigenschaft Sie ändern möchten:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Oder

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Ihnen muss die Rolle "Rechtlicher Halte"-Exchange Online zugewiesen werden, um die *Parameter RemoveDelayHoldApplied* oder *RemoveDelayReleaseHoldApplied verwenden* zu können. 

Um den Verzögerungsspeicher für ein inaktives Postfach zu entfernen, führen Sie einen der folgenden Befehle in Exchange Online PowerShell aus:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

Oder

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> Die beste Möglichkeit zum Angeben eines inaktiven Postfachs im vorherigen Befehl ist die Verwendung des Distinguished Name oder Exchange GUID-Werts. Durch Verwenden eines dieser Werte können Sie verhindern, versehentlich das falsche Postfach anzugeben. 

Weitere Informationen zur Verwendung dieser Parameter zum Verwalten von Verzögerungsspeichern finden Sie unter [Set-Mailbox](/powershell/module/exchange/set-mailbox).

Beachten Sie beim Verwalten eines Postfachs im Verzögerungsspeicher folgendes:

- Wenn die Eigenschaft DelayHoldApplied oder DelayReleaseHoldApplied auf **True** festgelegt ist und ein Postfach (oder das entsprechende Benutzerkonto) gelöscht wird, wird das Postfach zu einem inaktiven Postfach. Der Grund dafür ist, dass ein Postfach als inaktiv betrachtet wird, wenn eine der Eigenschaften auf **True** festgelegt ist, und das Löschen eines In-Hold-Postfachs zu einem inaktiven Postfach führt. Um ein Postfach zu löschen und nicht zu einem inaktiven Postfach zu machen, müssen Sie beide Eigenschaften auf **False festlegen.**

- Wie bereits erwähnt, gilt ein Postfach für eine unbegrenzte Haltedauer, wenn die Eigenschaft DelayHoldApplied oder DelayReleaseHoldApplied auf **True festgelegt ist.** Dies bedeutet jedoch nicht, dass *alle* Inhalte im Postfach beibehalten werden. Dies hängt vom Wert ab, der auf jede Eigenschaft festgelegt ist. Angenommen, beide Eigenschaften sind auf **True festgelegt,** da Haltefächer aus dem Postfach entfernt werden. Anschließend entfernen Sie nur den Verzögerungsspeicher, der auf Clouddaten angewendet wird, die nicht Outlook werden (mithilfe des *Parameters RemoveDelayReleaseHoldApplied).* Wenn der Assistent für verwaltete Ordner das Postfach das nächste Mal verarbeitet, werden die nicht Outlook zum Entfernen markierten Elemente gelöscht. Alle Outlook zum Entfernen markierten Elemente werden nicht gelöscht, da die Eigenschaft DelayHoldApplied weiterhin auf **True festgelegt ist.** Das Gegenteil wäre auch der Fall: Wenn DelayHoldApplied auf **False** und DelayReleaseHoldApplied auf **True** festgelegt ist, werden nur Outlook elemente gelöscht, die zum Entfernen markiert sind.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die Aufbewahrungsspeicher identifiziert haben, die auf ein Postfach angewendet werden, können Sie Aufgaben ausführen, z. B. das Ändern der Aufbewahrungsdauer, das vorübergehende oder dauerhafte Entfernen des Halteraums oder das Ausschließen eines inaktiven Postfachs aus einer Microsoft 365 Aufbewahrungsrichtlinie. Weitere Informationen zum Ausführen von Aufgaben im Zusammenhang mit Haltebereichen finden Sie in einem der folgenden Themen:

- Führen Sie den Befehl [Set-RetentionCompliancePolicy -Identity \<Policy Name> -AddExchangeLocationException \<user mailbox> ](/powershell/module/exchange/set-retentioncompliancepolicy) in Security & Compliance Center PowerShell aus, um ein Postfach aus einer organisationsweiten Microsoft 365 auszuschließen. Dieser Befehl kann nur für Aufbewahrungsrichtlinien verwendet werden, bei denen der Wert für die *ExchangeLocation-Eigenschaft* gleich `All` ist.

- [Ändern der Aufbewahrungsdauer für ein inaktives Postfach](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Löschen eines inaktiven Postfachs](delete-an-inactive-mailbox.md)

- [Löschen von Elementen im Ordner „Wiederherstellbare Elemente“ für cloudbasierte aufzubewahrende Postfächer](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)