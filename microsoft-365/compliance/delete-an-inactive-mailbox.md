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
description: Wenn Sie den Inhalt eines inaktiven Microsoft 365-Postfachs nicht mehr beibehalten müssen, können Sie das inaktive Postfach dauerhaft löschen.
ms.openlocfilehash: d5acccbf37ee5b6958d282de14edafc0b9b00182
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717579"
---
# <a name="delete-an-inactive-mailbox"></a>Löschen eines inaktiven Postfachs

Ein inaktives Postfach wird verwendet, um die E-Mails eines ehemaligen Mitarbeiters zu erhalten, nachdem sie Ihre Organisation verlassen haben. Wenn Sie die Inhalte eines inaktiven Postfachs nicht mehr aufbewahren müssen, können Sie das inaktive Postfach durch Entfernen des Haltebereichs endgültig löschen. Darüber hinaus ist es möglich, mehrere Haltebereiche für ein inaktives Postfach festzulegen. Beispielsweise kann für ein inaktives Postfach ein Beweissicherungsverfahren aktiviert oder das Postfach in einem oder mehreren In-Situ-Speichern abgelegt werden. Darüber hinaus kann eine Aufbewahrungsrichtlinie (erstellt im Security and Compliance Center in Office 365 oder Microsoft 365) auf das inaktive Postfach angewendet werden. Sie müssen alle Aufbewahrungs- und Aufbewahrungsrichtlinien aus einem inaktiven Postfach entfernen, um es zu löschen. Nach dem Entfernen der Haltebereiche und Aufbewahrungsrichtlinien wird das inaktive Postfach zum Löschen markiert und endgültig gelöscht, nachdem es verarbeitet wurde.
  
> [!IMPORTANT]
> Da wir weiterhin auf unterschiedliche Weise investieren, um Postfachinhalte zu erhalten, wird der In-Place im Exchange Admin Center angekündigt. Das bedeutet, dass Sie zum Erstellen eines inaktiven Postfachs Aufbewahrungs- und Aufbewahrungsrichtlinien verwenden sollten. Ab dem 1. Juli 2020 können Sie keine neuen In-Place in Exchange Online erstellen. Sie können jedoch weiterhin die Haltedauer eines In-Place inaktiven Postfachs ändern. Ab dem 1. Oktober 2020 können Sie die Haltedauer jedoch nicht mehr ändern. Sie können nur ein inaktives Postfach löschen, indem Sie die In-Place entfernen. Vorhandene inaktive Postfächer, die sich im In-Place befinden, bleiben bis zum Entfernen des Haltespeichers erhalten. Weitere Informationen zum Austritt von In-Place finden Sie unter [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).
  
Eine Beschreibung dessen, was geschieht, wenn Haltebereiche von einem inaktiven Postfach entfernt werden, finden Sie im Abschnitt [Weitere Informationen](#more-information).
  
## <a name="before-you-delete-an-inactive-mailbox"></a>Vor dem Löschen eines inaktiven Postfachs

- Sie müssen Exchange Online PowerShell zum Entfernen eines Beweissicherungsverfahrens für ein inaktives Postfach verwenden. Sie können nicht die Exchange-Verwaltungskonsole (EAC) verwenden. Schrittweise Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

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

Das Verfahren zum Entfernen eines inaktiven Postfachs aus einer Microsoft 365-Aufbewahrungsrichtlinie hängt davon ab, ob die dem inaktiven Postfach zugewiesene Aufbewahrungsrichtlinie organisationsweit oder explizit ist. für den Typ der Aufbewahrungsrichtlinie, die dem inaktiven Postfach zugewiesen ist.

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

Führen Sie den folgenden Befehl in [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) aus, um ein inaktives Postfach aus einer expliziten Aufbewahrungsrichtlinie zu entfernen.

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

- **Ein inaktives Postfach ist ein Typ des vorläufig gelöschten Postfachs.** In Exchange Online ist ein vorläufig gelöschtes Postfach, das zwar gelöscht wurde, aber innerhalb einer bestimmten Beibehaltungsdauer wiederhergestellt werden kann. Die Aufbewahrungsdauer für vorläufig gelöschte Postfächer beträgt in Exchange Online 30 Tage. Das bedeutet, dass das Postfach innerhalb von 30 Tagen nach dem vorläufigen Löschen wiederhergestellt werden kann. Nach 30 Tagen wird ein vorläufig gelöschtes Postfach zum dauerhaften Löschen markiert und kann nicht wiederhergestellt werden.

- **Was geschieht, nachdem Sie den Haltebereich für ein inaktives Postfach entfernt haben?** Das Postfach wird wie andere vorläufig gelöschte Postfächer behandelt und wird für die dauerhafte Löschung markiert, nachdem die 30-tägige Beibehaltungsdauer für das vorläufig gelöschte Postfach abgelaufen ist. Dieser Aufbewahrungszeitraum beginnt an dem Datum, an dem das Postfach erstmals inaktiv gemacht wurde. Dieses Datum wird als datumsaktiv gelöscht bezeichnet, d. h. das Datum, an dem das entsprechende Benutzerkonto gelöscht wurde oder das Exchange Online-Postfach mit dem **Cmdlet Remove-Mailbox** gelöscht wurde. Das Datum für das vorläufige Löschen ist nicht das Datum, an dem Sie den Haltebereich entfernt haben.

- **Wird ein inaktives Postfach sofort nach dem Entfernen des Haltebereichs dauerhaft gelöscht?** Wenn das Datum für vorläufig gelöschte Elemente für ein inaktives Postfach mehr als 30 Tage zurückliegt, wird das Postfach nicht sofort dauerhaft gelöscht, sobald Sie den Haltebereich entfernen. Das Postfach wird zum endgültigen Löschen markiert und bei der nächsten Verarbeitung gelöscht.

- **Wie wirkt sich die Beibehaltungsdauer für das vorläufig gelöschte Postfach auf inaktive Postfächer aus?** Wenn das Datum für vorläufig gelöschte Elemente für ein inaktives Postfach über 30 Tage vor dem Datum liegt, an dem der Haltebereich entfernt wurde, wird das Postfach für die dauerhafte Löschung markiert. Wenn jedoch ein inaktives Postfach über ein Datum für das vorläufige Löschen innerhalb der letzten 30 Tage verfügt und Sie den Haltebereich entfernen, können Sie das Postfach bis zum Ablauf des Aufbewahrungszeitraums für das vorläufige Löschen wiederherstellen. Weitere Informationen finden Sie unter [Löschen oder Wiederherstellen von Benutzerpostfächern in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes). Nach Ablauf des Aufbewahrungszeitraums für weiche gelöschte Postfächer müssen Sie die Verfahren zum Wiederherstellen eines inaktiven Postfachs befolgen. Weitere Informationen finden Sie unter [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).

- **Wie können Informationen über ein inaktives Postfach angezeigt werden, nachdem der Haltebereich entfernt wurde?** Nachdem ein Haltefeld entfernt wurde und das inaktive Postfach wieder auf ein soft-deleted-Postfach zurückgesetzt wurde, wird es nicht mithilfe des  *Parameters InactiveMailboxOnly*  mit dem **Cmdlet Get-Mailbox** zurückgegeben. Sie können jedoch Informationen über das Postfach anzeigen, indem Sie den Befehl **Get-Mailbox -SoftDeletedMailbox** verwenden. Beispiel:

  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  Im obigen Beispiel identifiziert die *WhenSoftDeleted-Eigenschaft* das datumsweich gelöschte Datum, das in diesem Beispiel den 30. Oktober 2014 ist. Wenn dieses unbefristete Postfach zuvor ein inaktives Postfach war, für das das Archiv entfernt wurde, wird es 30 Tage nach dem Wert der *WhenSoftDeleted-Eigenschaft* endgültig gelöscht. In diesem Fall wird das Postfach nach dem 30. November 2014 endgültig gelöscht.
