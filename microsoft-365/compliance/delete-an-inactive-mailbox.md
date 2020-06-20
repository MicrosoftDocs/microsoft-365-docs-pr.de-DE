---
title: Löschen eines inaktiven Postfachs
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
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
description: Wenn Sie den Inhalt eines inaktiven Microsoft 365-Postfachs nicht mehr aufbewahren müssen, können Sie das inaktive Postfach endgültig löschen.
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817894"
---
# <a name="delete-an-inactive-mailbox"></a>Löschen eines inaktiven Postfachs

Ein inaktives Postfach wird verwendet, um die E-Mails eines ehemaligen Mitarbeiters aufzubewahren, nachdem dieser die Organisation verlassen hat. Wenn Sie die Inhalte eines inaktiven Postfachs nicht mehr aufbewahren müssen, können Sie das inaktive Postfach durch Entfernen des Haltebereichs endgültig löschen. Darüber hinaus ist es möglich, mehrere Haltebereiche für ein inaktives Postfach festzulegen. Beispielsweise kann für ein inaktives Postfach ein Beweissicherungsverfahren aktiviert oder das Postfach in einem oder mehreren In-Situ-Speichern abgelegt werden. Darüber hinaus kann eine Aufbewahrungsrichtlinie (erstellt im Security and Compliance Center in Office 365 oder Microsoft 365) auf das inaktive Postfach angewendet werden. Sie müssen alle Haltestatus und Aufbewahrungsrichtlinien aus einem inaktiven Postfach entfernen, um es zu löschen. Nach dem Entfernen der Haltebereiche und Aufbewahrungsrichtlinien wird das inaktive Postfach zum Löschen markiert und endgültig gelöscht, nachdem es verarbeitet wurde.
  
> [!IMPORTANT]
> Da wir weiterhin auf verschiedene Arten investieren, um Postfachinhalte beizubehalten, kündigen wir den Ruhestand von in-Place-Speicher in der Exchange-Verwaltungskonsole an. Das heißt, Sie sollten Beweissicherungsverfahren und Aufbewahrungsrichtlinien verwenden, um ein inaktives Postfach zu erstellen. Ab dem 1. Juli 2020 können Sie in Exchange Online keine neuen in-Place-Aufbewahrungsorte erstellen. Sie können jedoch weiterhin die Aufbewahrungsdauer eines in-situ-Speichers ändern, der in einem inaktiven Postfach platziert wird. Ab dem 1. Oktober 2020 können Sie die Aufbewahrungsdauer jedoch nicht ändern. Sie können ein inaktives Postfach nur löschen, indem Sie den in-situ-Speicher entfernen. Vorhandene inaktive Postfächer, die sich im Compliance-Archiv befinden, werden weiterhin beibehalten, bis die Aufbewahrung aufgehoben wird. Weitere Informationen zum Ruhestand von in-Place-Archiven finden Sie unter [Retirement of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md).
  
Eine Beschreibung dessen, was geschieht, wenn Haltebereiche von einem inaktiven Postfach entfernt werden, finden Sie im Abschnitt [Weitere Informationen](#more-information).
  
## <a name="before-you-delete-an-inactive-mailbox"></a>Vor dem Löschen eines inaktiven Postfachs

- Sie müssen Exchange Online PowerShell zum Entfernen eines Beweissicherungsverfahrens für ein inaktives Postfach verwenden. Sie können nicht die Exchange-Verwaltungskonsole (EAC) verwenden. Eine Schritt-für-Schritt-Anleitung finden Sie unter [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Sie können die Exchange Online PowerShell oder die EAC verwenden, um einen In-Situ-Speicher von einem inaktiven Postfach zu entfernen. 
    
- Sie können die Inhalte eines inaktiven Postfachs in ein anderes Postfach kopieren, bevor Sie den Haltebereich entfernen und ein inaktives Postfach löschen. Ausführliche Informationen finden Sie unter [Wiederherstellen eines inaktiven Postfachs in Office 365](restore-an-inactive-mailbox.md).
    
- Wenn Sie den Haltestatus oder die Aufbewahrungsrichtlinie aus einem inaktiven Postfach entfernen und der Aufbewahrungszeitraum für vorläufig gelöschte Postfächer für das Postfach abgelaufen ist, wird das Postfach endgültig gelöscht. Nachdem es gelöscht wurde, kann es nicht wiederhergestellt werden. Stellen Sie vor dem Entfernen des Haltebereichs sicher, dass Sie die Inhalte im Postfach nicht mehr benötigen. Wenn Sie ein inaktives Postfach erneut aktivieren möchten, können Sie es wiederherstellen. Ausführliche Informationen finden Sie unter [Wiederherstellen eines inaktiven Postfachs in Office 365](recover-an-inactive-mailbox.md).
    
- Weitere Informationen zu inaktiven Postfächern finden Sie unter [inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Schritt 1: Identifizieren der Haltebereiche für ein inaktives Postfach

Wie bereits erwähnt, kann ein Beweissicherungsverfahren, ein in-situ-Speicher oder eine Aufbewahrungsrichtlinie für ein inaktives Postfach platziert werden. Der erste Schritt besteht darin, die Haltebereiche für ein inaktives Postfach zu identifizieren.
  
Führen Sie den folgenden Befehl aus, um die Informationen zu Haltebereichen für alle inaktiven Postfächer in Ihrer Organisation anzuzeigen.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property. For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla. 
  
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
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> Wenn viele In-Situ-Speicher für ein inaktives Postfach aktiviert werden, werden nicht alle In-Situ-Speicher-GUIDs angezeigt. Sie können den folgenden Befehl ausführen, um alle in-situ-Speicher-GUIDs anzuzeigen:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Schritt 2: Entfernen eines Haltebereichs von einem inaktiven Postfach

After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox. 
  
### <a name="remove-a-litigation-hold"></a>Entfernen eines Beweissicherungsverfahrens

As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox. 
  
### <a name="remove-in-place-holds"></a>Entfernen von In-Situ-Speichern

 Es gibt zwei Möglichkeiten, um einen In-Situ-Speicher von einem inaktiven Postfach zu entfernen: 
  
- **Löschen des in-situ-Aufbewahrungs Objekts** Wenn das inaktive Postfach, das Sie dauerhaft löschen möchten, das einzige Quellpostfach für einen in-situ-Speicher ist, können Sie einfach das in-situ-Speicherobjekt löschen. 
    
    > [!NOTE]
    > You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message. 
  
- **Entfernen des inaktiven Postfachs als Quellpostfach für einen In-Situ-Speicher** Wenn Sie andere Quellpostfächer für einen In-Situ-Speicher beibehalten möchten, können Sie das inaktive Postfach aus der Liste der Quellpostfächer entfernen und das In-Situ-Speicherobjekt beibehalten. 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>Verwenden der EAC zum Löschen eines In-Situ-Speichers

1. If you know the name of the In-Place Hold that you want to delete, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Wählen Sie den in-situ-Speicher aus, den Sie löschen möchten, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.
    
5. On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).
    
6. Klicken Sie in der Warnung auf **Ja**, um den In-Situ-Speicher zu löschen. 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>Verwenden von Exchange Online PowerShell zum Löschen eines In-Situ-Speichers

1. Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
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

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Verwenden der EAC zum Entfernen eines inaktiven Postfachs aus einem In-Situ-Speicher

1. If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Wählen Sie den in-situ-Speicher aus, der in dem inaktiven Postfach platziert wird, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.
    
5. Klicken Sie in der Liste der Quellpostfächer auf den Namen des inaktiven Postfachs, das Sie entfernen möchten, und dann auf **Entfernen**![Entfernen (Symbol)](../media/adf01106-cc79-475c-8673-065371c1897b.gif).
    
6. Click **Save** to save the change. A message is displayed saying the operation was successfully completed. 
    
7. Wiederholen Sie die Schritte 1 bis 6, um andere In-Situ-Speicher zu entfernen, die dem inaktiven Postfach zugeordnet sind.
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Verwenden der Exchange Online PowerShell zum Entfernen eines inaktiven Postfachs aus einem In-Situ-Speicher

If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC. Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold. If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold. 
  
1. Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. Stellen Sie sicher, dass das inaktive Postfach als ein Quellpostfach für den In-Situ-Speicher aufgelistet ist. 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   **Hinweis:** Die *Sources-Eigenschaft des* in-situ-Speichers identifiziert die Quellpostfächer nach Ihren *legacyExchangeDN* -Eigenschaften. Da diese Eigenschaft inaktive Postfächer eindeutig identifiziert, können Sie mit der Eigenschaft *Sources* des In-Situ-Speichers verhindern, das falsche Postfach zu entfernen. Außerdem vermeiden Sie auch Probleme, wenn zwei Postfächer über denselben Alias oder dieselbe SMTP-Adresse verfügen. 
   
3. Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step. 
    
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

- **An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered. 
    
- **Was geschieht, nachdem Sie den Haltebereich für ein inaktives Postfach entfernt haben?** Das Postfach wird wie andere vorläufig gelöschte Postfächer behandelt und wird für die dauerhafte Löschung markiert, nachdem die 30-tägige Beibehaltungsdauer für das vorläufig gelöschte Postfach abgelaufen ist. Dieser Aufbewahrungszeitraum beginnt an dem Datum, an dem das Postfach erstmals inaktiv gemacht wurde. Dieses Datum wird als vorläufig gelöschtes Datum bezeichnet, das das Datum ist, an dem das entsprechende Benutzerkonto gelöscht wurde, oder wenn das Exchange Online Postfach mit dem Cmdlet **Remove-Mailbox** gelöscht wurde. Das Datum für das vorläufige Löschen ist nicht das Datum, an dem Sie den Haltebereich entfernt haben. 
    
- **Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed. 
    
- **Wie wirkt sich die Beibehaltungsdauer für das vorläufig gelöschte Postfach auf inaktive Postfächer aus?** Wenn das Datum für vorläufig gelöschte Elemente für ein inaktives Postfach über 30 Tage vor dem Datum liegt, an dem der Haltebereich entfernt wurde, wird das Postfach für die dauerhafte Löschung markiert. Wenn jedoch ein inaktives Postfach über ein Datum für das vorläufige Löschen innerhalb der letzten 30 Tage verfügt und Sie den Haltebereich entfernen, können Sie das Postfach bis zum Ablauf des Aufbewahrungszeitraums für das vorläufige Löschen wiederherstellen. Ausführliche Informationen finden Sie unter [Löschen oder Wiederherstellen von Benutzerpostfächern in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). Nachdem die Beibehaltungsdauer für das vorläufig gelöschte Postfach abgelaufen ist, müssen Sie die Prozeduren für das Wiederherstellen eines inaktiven Postfachs befolgen. Ausführliche Informationen finden Sie unter [Wiederherstellen eines inaktiven Postfachs in Office 365](recover-an-inactive-mailbox.md).
    
- **Wie können Informationen über ein inaktives Postfach angezeigt werden, nachdem der Haltebereich entfernt wurde?** Nachdem ein Haltestatus entfernt wurde und das inaktive Postfach wieder auf ein vorläufig gelöschtes Postfach zurückgesetzt wird, wird es nicht mithilfe des *InactiveMailboxOnly* -Parameters mit dem Cmdlet **Get-Mailbox** zurückgegeben. Sie können jedoch Informationen über das Postfach anzeigen, indem Sie den Befehl **Get-Mailbox -SoftDeletedMailbox** verwenden. Beispiel: 
    
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

  Im obigen Beispiel gibt die *WhenSoftDeleted* -Eigenschaft das vorläufig gelöschte Datum an, das in diesem Beispiel 30. Oktober 2014 ist. Wenn es sich bei diesem vorläufig gelöschten Postfach um ein inaktives Postfach handelte, für das der Haltebereich entfernt wurde, wird es 30 Tage nach dem Wert der *WhenSoftDeleted* -Eigenschaft endgültig gelöscht. In diesem Fall wird das Postfach nach dem 30. November 2014 endgültig gelöscht.

