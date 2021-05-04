---
title: Löschen eines inaktiven Postfachs
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Wenn Sie den Inhalt eines inaktiven Postfachs Microsoft 365 müssen, können Sie das inaktive Postfach dauerhaft löschen.
ms.openlocfilehash: 077a71bfdd82721e0992e5d14073aa037b7cfd1b
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100824"
---
# <a name="delete-an-inactive-mailbox"></a>Löschen eines inaktiven Postfachs

Ein inaktives Postfach wird verwendet, um die E-Mails eines ehemaligen Mitarbeiters zu erhalten, nachdem sie Ihre Organisation verlassen haben. Wenn Sie die Inhalte eines inaktiven Postfachs nicht mehr aufbewahren müssen, können Sie das inaktive Postfach durch Entfernen des Haltebereichs endgültig löschen. Darüber hinaus ist es möglich, mehrere Haltebereiche für ein inaktives Postfach festzulegen. Beispielsweise kann für ein inaktives Postfach ein Beweissicherungsverfahren aktiviert oder das Postfach in einem oder mehreren In-Situ-Speichern abgelegt werden. Darüber hinaus kann eine Aufbewahrungsrichtlinie (erstellt im Security and Compliance Center in Office 365 oder Microsoft 365) auf das inaktive Postfach angewendet werden. Sie müssen alle Aufbewahrungs- und Aufbewahrungsrichtlinien aus einem inaktiven Postfach entfernen, um es zu löschen. Nach dem Entfernen der Haltebereiche und Aufbewahrungsrichtlinien wird das inaktive Postfach zum Löschen markiert und endgültig gelöscht, nachdem es verarbeitet wurde.
  
> [!IMPORTANT]
> Da wir weiterhin auf unterschiedliche Weise investieren, um Postfachinhalte zu erhalten, wird die Rente von In-Place Holds im Exchange Admin Center angekündigt. Das bedeutet, dass Sie zum Erstellen eines inaktiven Postfachs Aufbewahrungs- und Aufbewahrungsrichtlinien verwenden sollten. Ab dem 1. Juli 2020 können Sie keine neuen In-Place in Exchange Online. Sie können jedoch weiterhin die Haltedauer eines In-Place inaktiven Postfachs ändern. Ab dem 1. Oktober 2020 können Sie die Haltedauer jedoch nicht mehr ändern. Sie können nur ein inaktives Postfach löschen, indem Sie die In-Place entfernen. Vorhandene inaktive Postfächer, die sich im In-Place befinden, bleiben bis zum Entfernen des Haltespeichers erhalten. Weitere Informationen zum Austritt von In-Place finden Sie unter [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).
  
Eine Beschreibung dessen, was geschieht, wenn Haltebereiche von einem inaktiven Postfach entfernt werden, finden Sie im Abschnitt [Weitere Informationen](#more-information).
  
## <a name="before-you-delete-an-inactive-mailbox"></a>Vor dem Löschen eines inaktiven Postfachs

- Sie müssen Exchange Online PowerShell zum Entfernen eines Beweissicherungsverfahrens für ein inaktives Postfach verwenden. Sie können nicht die Exchange-Verwaltungskonsole (EAC) verwenden. Schrittweise Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Sie können die Inhalte eines inaktiven Postfachs in ein anderes Postfach kopieren, bevor Sie den Haltebereich entfernen und ein inaktives Postfach löschen. Weitere Informationen finden Sie unter [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).

- Wenn Sie die Aufbewahrungs- oder Aufbewahrungsrichtlinie aus einem inaktiven Postfach entfernen und der Aufbewahrungszeitraum für das dauerhaft gelöschte Postfach für das Postfach abgelaufen ist, wird das Postfach endgültig gelöscht. Nachdem es gelöscht wurde, kann es nicht wiederhergestellt werden. Stellen Sie vor dem Entfernen des Haltebereichs sicher, dass Sie die Inhalte im Postfach nicht mehr benötigen. Wenn Sie ein inaktives Postfach reaktivieren möchten, können Sie es wiederherstellen. Weitere Informationen finden Sie unter [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).

- Weitere Informationen zu inaktiven Postfächern finden Sie unter [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Schritt 1: Identifizieren der Haltebereiche für ein inaktives Postfach

Wie bereits erwähnt, kann für ein inaktives Postfach In-Place Aufbewahrungs- oder Aufbewahrungsrichtlinie für Rechtsstreitigkeiten aktiviert werden. Der erste Schritt besteht darin, die Haltebereiche für ein inaktives Postfach zu identifizieren.
  
Führen Sie den folgenden Befehl aus, um die Informationen zu Haltebereichen für alle inaktiven Postfächer in Ihrer Organisation anzuzeigen.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

Der Wert **True** für die Eigenschaft **LitigationHoldEnabled** gibt an, dass für das inaktive Postfach ein Beweissicherungsverfahren aktiviert ist. Wenn ein In-Situ-Speicher für ein inaktives Postfach aktiviert ist, wird die GUID für den Haltebereich als Wert für die Eigenschaft **InPlaceHolds** angezeigt. Die folgenden Ergebnisse für zwei inaktive Postfächer zeigen beispielsweise, dass ann Beebe ein Prozessaufbewahrungsverfahren besteht und dass eine In-Place-Aufbewahrungs- und Aufbewahrungsrichtlinie auf Pilar Pinilla gesetzt wird.
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> Wenn viele In-Place oder Aufbewahrungsrichtlinien für ein inaktives Postfach platziert werden, werden nicht alle In-Place-GUIDs angezeigt. Sie können den folgenden Befehl ausführen, um alle GUIDs in der InPlaceHolds-Eigenschaft anzeigen:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
Weitere Informationen zum Identifizieren von Haltefächern finden Sie unter [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Schritt 2: Entfernen eines Haltebereichs von einem inaktiven Postfach

Nachdem Sie ermittelt haben, welche Art von Haltebereich für das inaktive Postfach aktiviert ist (und ob es mehrere Haltebereiche gibt), werden im nächsten Schritt die Haltebereiche für das Postfach entfernt. Wie bereits erwähnt, müssen Sie alle Haltebereiche entfernen, um ein inaktives Postfach endgültig zu entfernen.
  
### <a name="remove-a-litigation-hold"></a>Entfernen eines Beweissicherungsverfahrens

Wie bereits erwähnt, müssen Sie Windows PowerShell verwenden, um ein Beweissicherungsverfahren von einem inaktiven Postfach zu entfernen. Sie können nicht die EAC verwenden. Führen Sie den folgenden Befehl aus, um ein Beweissicherungsverfahren zu entfernen.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> Die beste Methode zum Identifizieren eines inaktiven Postfachs ist die Verwendung des Distinguished Name oder des Exchange-GUID-Werts. Durch Verwenden eines dieser Werte können Sie verhindern, versehentlich das falsche Postfach anzugeben. 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a>Entfernen eines inaktiven Postfachs aus einer Aufbewahrungsrichtlinie

Das Verfahren zum Entfernen eines inaktiven Postfachs aus Microsoft 365 Aufbewahrungsrichtlinie hängt davon ab, ob die dem inaktiven Postfach zugewiesene Aufbewahrungsrichtlinie organisationsweit oder explizit ist. für den Typ der Aufbewahrungsrichtlinie, die dem inaktiven Postfach zugewiesen ist.

- Organisationsweite Aufbewahrungsrichtlinien, die allen Postfächern in der Organisation zugewiesen sind. Verwenden Sie **das Cmdlet Get-OrganizationConfig** in Exchange Online PowerShell, um Informationen zu organisationsweiten Aufbewahrungsrichtlinien zu erhalten.

- Bestimmte Aufbewahrungsrichtlinien für Speicherorte, die bestimmten Postfächern zugewiesen sind. Dies sind Richtlinien, die den Inhaltsstandorten bestimmter Benutzer zugewiesen sind. Verwenden Sie **das Cmdlet Get-Mailbox -IncludeInactiveMailbox** in Exchange Online PowerShell, um Informationen zu Aufbewahrungsrichtlinien zu erhalten, die bestimmten inaktiven Postfächern zugewiesen sind.

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a>Entfernen eines inaktiven Postfachs aus einer organisationsweiten Aufbewahrungsrichtlinie

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um ein inaktives Postfach aus einer organisationsweiten Aufbewahrungsrichtlinie auszuschließen.

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

Weitere Informationen zur Identifizierung organisationsweiter Aufbewahrungsrichtlinien, die auf ein inaktives Postfach angewendet werden, und zum Abrufen der GUID für eine Aufbewahrungsrichtlinie finden Sie im Abschnitt "Get-OrganizationConfig" unter [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).

Alternativ können Sie den folgenden Befehl ausführen, um das inaktive Postfach aus allen organisationsweiten Richtlinien zu entfernen:

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a>Entfernen eines inaktiven Postfachs aus einer bestimmten Aufbewahrungsrichtlinie für Speicherorte

Führen Sie den folgenden Befehl in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) aus, um ein inaktives Postfach aus einer expliziten Aufbewahrungsrichtlinie zu entfernen.

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

Weitere Informationen zum Identifizieren bestimmter Aufbewahrungsrichtlinien für Speicherorte, die auf ein inaktives Postfach angewendet werden, und zum Abrufen der GUID für eine Aufbewahrungsrichtlinie finden Sie im Abschnitt "Get-Mailbox" unter [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).

### <a name="remove-in-place-holds"></a>Entfernen der In-Situ-Aufbewahrung

 Es gibt zwei Möglichkeiten, um einen In-Situ-Speicher von einem inaktiven Postfach zu entfernen: 
  
- **Löschen sie In-Place Hold-Objekt**. Wenn das inaktive Postfach, das Sie dauerhaft löschen möchten, das einzige Quellpostfach für ein In-Place-Archiv ist, können Sie einfach das In-Place löschen. 

    > [!NOTE]
    > Sie müssen den Haltebereich deaktivieren, bevor Sie ein In-Situ-Speicherobjekt löschen können. Wenn Sie versuchen, ein In-Situ-Speicherobjekt zu löschen, dessen Haltebereich aktiviert ist, wird eine Fehlermeldung angezeigt. 
  
- **Entfernen Sie das inaktive Postfach als Quellpostfach eines In-Place Archivs.** Wenn Sie andere Quellpostfächer für einen In-Place beibehalten möchten, können Sie das inaktive Postfach aus der Liste der Quellpostfächer entfernen und das In-Place beibehalten.

#### <a name="delete-an-in-place-hold"></a>Löschen eines In-Place-Halte

1. Erstellen Sie eine Variable, die die Eigenschaften des zu löschenden In-Situ-Speichers enthält. Verwenden Sie die In-Situ-Speicher-GUID, die Sie in [Schritt 1: Identifizieren der Haltebereiche für ein inaktives Postfach](#step-1-identify-the-holds-on-an-inactive-mailbox) abgerufen haben.

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. Deaktivieren Sie den Haltebereich für den In-Situ-Speicher.

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. Löschen Sie den In-Situ-Speicher.

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a>Entfernen eines inaktiven Postfachs aus In-Place Archiv

Wenn der In-Situ-Speicher eine große Anzahl von Postfächern enthält, ist das inaktive Postfach möglicherweise nicht auf der Seite **Quellen** in der Exchange-Verwaltungskonsole aufgelistet. Bis zu 3.000 Postfächer werden auf der Seite **Quellen** angezeigt, wenn Sie einen In-Situ-Speicher bearbeiten. Wenn ein inaktives Postfach nicht auf der Seite **Quellen** aufgelistet ist, können Sie Exchange Online PowerShell verwenden, um es aus dem In-Situ-Speicher zu entfernen. 
  
1. Erstellen Sie eine Variable, die die Eigenschaften des In-Situ-Speichers enthält, der dem inaktiven Postfach zugeordnet ist. Verwenden Sie die In-Situ-Speicher-GUID, die Sie in [Schritt 1: Identifizieren der Haltebereiche für ein inaktives Postfach](#step-1-identify-the-holds-on-an-inactive-mailbox) abgerufen haben.

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. Stellen Sie sicher, dass das inaktive Postfach als ein Quellpostfach für den In-Situ-Speicher aufgelistet ist. 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > Die Eigenschaft *Sources* des In-Situ-Speichers identifiziert die Quellpostfächer nach der Eigenschaft *LegacyExchangeDN*. Da diese Eigenschaft inaktive Postfächer eindeutig identifiziert, können Sie mit der Eigenschaft *Sources* des In-Situ-Speichers verhindern, das falsche Postfach zu entfernen. Außerdem vermeiden Sie auch Probleme, wenn zwei Postfächer über denselben Alias oder dieselbe SMTP-Adresse verfügen. 

3. Entfernen Sie das inaktive Postfach aus der Liste der Quellpostfächer in der Variablen. Achten Sie darauf, die Eigenschaft **LegacyExchangeDN** des inaktiven Postfachs zu verwenden, die von dem Befehl im vorherigen Schritt zurückgegeben wurde. 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    Der folgende Befehl entfernt z. B. das inaktive Postfach für Pilar Pinilla.

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. Stellen Sie sicher, dass das inaktive Postfach aus der Liste der Quellpostfächer in der Variable entfernt wird.

   ```powershell
   $InPlaceHold.Sources
   ```

5. Ändern Sie den In-Situ-Speicher mit der aktualisierten Liste der Quellpostfächer, die das inaktive Postfach nicht enthält.

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. Stellen Sie sicher, dass das inaktive Postfach aus der Liste der Quellpostfächer für den In-Situ-Speicher entfernt wird.

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>Weitere Informationen

- **Ein inaktives Postfach ist ein Typ des vorläufig gelöschten Postfachs.** In Exchange Online ist ein vorläufig gelöschtes Postfach, das zwar gelöscht wurde, aber innerhalb einer bestimmten Beibehaltungsdauer wiederhergestellt werden kann. Ein zuvor inaktives Postfach steht als soft-deleted-Postfach in Exchange Online 183 Tage zur Verfügung. Dies bedeutet, dass das Postfach innerhalb von 183 Tagen nach dem Soft-Deleted wiederhergestellt werden kann. Nach 183 Tagen wird ein unbefristetes Postfach zum dauerhaften Löschen markiert und kann nicht wiederhergestellt werden.

- **Was geschieht, nachdem Sie den Haltebereich für ein inaktives Postfach entfernt haben?** Das Postfach wird wie andere soft-deleted-Postfächer behandelt und nach Ablauf des Aufbewahrungszeitraums von 183 -tägigen soft-deleted-Postfächern zum dauerhaften Löschen markiert. Dieser Aufbewahrungszeitraum beginnt an dem Datum, an dem das Postfach erstmals inaktiv gemacht wurde. Dieses Datum wird als datumsaktiv gelöscht bezeichnet, d. h. das Datum, an dem das entsprechende Benutzerkonto gelöscht wurde, oder wenn das Exchange Online-Postfach mit dem **Cmdlet Remove-Mailbox** gelöscht wurde. Das Datum für das vorläufige Löschen ist nicht das Datum, an dem Sie den Haltebereich entfernt haben.

- **Wird ein inaktives Postfach sofort nach dem Entfernen des Haltebereichs dauerhaft gelöscht?** Ein zuvor inaktives Postfach steht 183 Tage lang im Zustand "Soft-Deleted" zur Verfügung. Nach 183 Tagen wird das Postfach zum dauerhaften Löschen markiert.

- **Wie können Informationen über ein inaktives Postfach angezeigt werden, nachdem der Haltebereich entfernt wurde?** Nachdem ein Haltefeld entfernt wurde und das inaktive Postfach wieder auf ein soft-deleted-Postfach zurückgesetzt wurde, wird es nicht mithilfe des  *Parameters InactiveMailboxOnly*  mit dem **Cmdlet Get-Mailbox** zurückgegeben. Sie können jedoch Informationen über das Postfach anzeigen, indem Sie den Befehl **Get-Mailbox -SoftDeletedMailbox** verwenden. Beispiel:

  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox,WasInactiveMailbox,InactiveMailboxRetireTime
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 6/16/2020 1:19:04 AM
  IsInactiveMailbox      : False
  WasInactiveMailbox     : True
  InactiveMailboxRetireTime : 9/30/2020 11:16:23 PM
  ```

  Im obigen Beispiel identifiziert die *WhenSoftDeleted-Eigenschaft* das datumsweich gelöschte Datum, das in diesem Beispiel den 16. Juni 2020 ist. Die *WasInactiveMailbox-Eigenschaft* wird als `True` aufgelistet, da sie zuvor ein inaktives Postfach war. Das Postfach wird 183 Tage nach dem 30. September 2020 endgültig gelöscht.

