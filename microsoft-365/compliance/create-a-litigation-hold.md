---
title: Erstellen einer Aufbewahrung für juristische Zwecke
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: Erfahren Sie, wie Sie ein Postfach in einem Prozesssicherungsverfahren platzieren und während einer Untersuchung alle Postfachinhalte beibehalten.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 81d3bf7bba0aadbcd2d52b5f7707caeea96e26c1
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750059"
---
# <a name="create-a-litigation-hold"></a>Erstellen einer Aufbewahrung für juristische Zwecke

Sie können ein Postfach in das Prozesssicherungsverfahren einbehalten, um alle Postfachinhalte, einschließlich gelöschter Elemente und der ursprünglichen Versionen geänderter Elemente, zu behalten. Wenn Sie ein Benutzerpostfach in das Prozesssicherungsverfahren einbehalten, werden auch Inhalte im Archivpostfach des Benutzers aufbewahrt (sofern aktiviert). Wenn Sie einen Haltezustand erstellen, können Sie eine Haltedauer (auch als zeitbasierter Haltezustand *bezeichnet)* angeben, damit gelöschte und geänderte Elemente für einen bestimmten Zeitraum aufbewahrt und dann endgültig aus dem Postfach gelöscht werden. Oder Sie können Inhalte einfach unbegrenzt beibehalten (als *unendlicher* Aufbewahrungsraum bezeichnet) oder bis das Prozesssicherungsverfahren aufgehoben wird. Wenn Sie einen Haltezeitraum angeben, wird er ab dem Datum berechnet, an dem eine Nachricht empfangen oder ein Postfachelement erstellt wird. 
  
Hier sehen Sie, was passiert, wenn Sie ein Prozesssicherungsverfahren erstellen.
  
- Elemente, die vom Benutzer dauerhaft gelöscht werden, werden für die Dauer des Haltezustands im Ordner "Wiederherstellbare Elemente" im Postfach des Benutzers aufbewahrt.

- Elemente, die vom Benutzer aus dem Ordner "Wiederherstellbare Elemente" gelöscht werden, werden für die Dauer der Haltedauer aufbewahrt.

- Das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" wird von 30 GB auf 110 GB erhöht.

- Elemente im primären Postfach des Benutzers und in den Archivpostfächern werden beibehalten.

## <a name="assign-an-exchange-online-plan-2-license"></a>Zuweisen einer Exchange Online Plan 2-Lizenz

Um ein Exchange Online in das Prozesssicherungsverfahren zu setzen, muss ihm eine Exchange Online Plan 2-Lizenz zugewiesen werden. Wenn einem Postfach eine Exchange Online Plan 1-Lizenz zugewiesen ist, müssen Sie ihm eine separate Exchange Online-Archivierung zuweisen, um es in die Warteschleife zu setzen.

> [!NOTE]
> Für Office 365 Education Organisationen wird das Prozesssicherungsverfahren in Office 365 A1 unterstützt, die eine Exchange Online Plan 1-Lizenz mit zusätzlichen Features enthalten. Weitere Informationen finden Sie im Abschnitt "Exchange Online Features" in der [Office 365 Education Dienstbeschreibung](/office365/servicedescriptions/office-365-platform-service-description/office-365-education#exchange-online-features).

## <a name="place-a-mailbox-on-litigation-hold"></a>Aktivieren des Beweissicherungsverfahrens für ein Postfach

Hier sind die Schritte zum Platzieren eines Postfachs im Prozesssicherungsverfahren mithilfe des Exchange Admin Center.

1. Wechseln Sie [https://outlook.office.com/ecp](https://outlook.office.com/ecp) zu, und melden Sie sich mit Ihrem globalen Administratorkonto an.

2. Klicken **Sie > im linken Navigationsbereich** auf Empfänger und Postfächer.

3. Wählen Sie das Postfach aus, das Sie im Prozesssicherungsverfahren platzieren möchten, und klicken Sie dann auf **Bearbeiten**.

4. Klicken Sie auf der Eigenschaftenseite des Postfachs auf **Postfachfunktionen**.
    
5. Klicken Sie unter **Beweissicherungsverfahren: Deaktiviert** auf **Aktivieren**, um für das Postfach das Beweissicherungsverfahren zu aktivieren.
    
6. Geben Sie **auf der** Seite Im Prozesssicherungsverfahren die folgenden optionalen Informationen ein: 
    
    - **Dauer des Rechtsstreitigkeitens (Tage)** – Verwenden Sie dieses Feld, um einen zeitbasierten Haltezeitspeicher zu erstellen und anzugeben, wie lange Postfachelemente gespeichert werden, wenn das Postfach in das Prozesssicherungsverfahren verschoben wird. Der Zeitraum beginnt mit dem Datum, an dem das Postfachelement empfangen oder erstellt wurde. Wenn die Haltedauer für ein bestimmtes Element abläuft, wird dieses Element nicht mehr beibehalten. Wenn Sie dieses Feld leer lassen, werden Elemente auf unbestimmte Zeit oder bis zum Entfernen des Haltefelds aufbewahrt. Geben Sie die Dauer in Tagen an.
    
    - **Hinweis** : Verwenden Sie dieses Feld, um den Benutzer darüber zu informieren, dass sich sein Postfach im Prozesssicherungsverfahren befindet. Die Notiz wird auf der Seite Kontoinformationen im Postfach des Benutzers angezeigt, wenn sie Outlook 2010 oder höher verwenden. Um auf diese Seite zu zugreifen, können Benutzer auf **Datei** in Outlook.
    
    - **URL** – Verwenden Sie dieses Feld, um den Benutzer zu einer Website zu führen, um weitere Informationen zum Prozesssicherungsverfahren zu erhalten. Diese URL wird auf der Seite Kontoinformationen im Postfach des Benutzers angezeigt, wenn Outlook 2010 oder höher verwendet. Um auf diese Seite zu zugreifen, können Benutzer auf **Datei** in Outlook.

7. Klicken **Sie auf** der Seite **Rechtsstreitigkeiten auf** Speichern, und klicken Sie dann auf der Seite Postfacheigenschaften auf Speichern. 

### <a name="create-a-litigation-hold-using-powershell"></a>Erstellen eines Rechtsstreits mit PowerShell

Sie können auch ein Prozesssicherungsverfahren erstellen, indem Sie den folgenden Befehl in [Exchange Online PowerShell ausführen:](/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

Der vorherige Befehl behält Elemente auf unbestimmte Zeit bei, da die Haltedauer nicht angegeben ist. Verwenden Sie den folgenden Befehl, um einen zeitbasierten Halteraum zu erstellen:

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

Weitere Informationen finden Sie unter [Set-Mailbox](/powershell/module/exchange/set-mailbox).

## <a name="how-does-litigation-hold-work"></a>Wie funktioniert das Beweissicherungsverfahren?

Beim normalen Löschworkflow wird ein dauerhaft gelöschtes (UMSCHALT+ENTF) oder aus dem Ordner „Gelöschte Elemente" gelöschtes Postfachelement in den Unterordner „Löschvorgänge" des Ordners „Wiederherstellbare Elemente" verschoben. Beim Anwenden einer Löschrichtlinie (hierbei handelt es sich um ein Aufbewahrungstag mit einer konfigurierten Aufbewahrungsaktion) werden Elemente auch nach Ablauf des Aufbewahrungszeitraums in den Unterordner „Löschvorgänge" verschoben. Beim dauerhaften Löschen eines Elements im Ordner „Wiederherstellbare Elemente" durch einen Benutzer oder nach Ablauf der Aufbewahrungsdauer wird das Element in den Unterordner „Endgültige Löschvorgänge" des Ordners „Wiederherstellbare Elemente" verschoben und zum endgültigen Löschen markiert. Das Element wird beim nächsten Verarbeiten des Postfachs vom Assistenten für verwalteten Ordner aus Exchange dauerhaft gelöscht.

Ist für das Postfach das Beweissicherungsverfahren aktiviert, werden die Elemente im Unterordner „Endgültige Löschvorgänge" für die für das Beweissicherungsverfahren angegebene Aufbewahrungsdauer aufbewahrt. Die Aufbewahrungsdauer wird anhand des ursprünglichen Datums berechnet,an dem ein Element empfangen oder erstellt wurde und legt fest, wie lange die Elemente im Unterordner „Endgültige Löschvorgänge" aufbewahrt werden. Wenn die Aufbewahrungsdauer für ein Element im Unterordner „Endgültige Löschvorgänge" abläuft, wird das Element zum endgültigen Löschen vorgemerkt und beim nächsten Verarbeiten des Postfachs vom Assistenten für verwalteten Ordner dauerhaft aus Exchange gelöscht. Wenn die dauerhafte Aufbewahrung für ein Postfach aktiviert ist, werden die Elemente nicht aus dem Unterordner „Endgültige Löschvorgänge" gelöscht.

Die folgende Abbildung zeigt die Unterordner in den Ordnern „Wiederherstellbare Elemente" und den Aufbewahrungsworkflowprozess.

![Lebenszyklus des "Litigation Hold"](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> Wenn ein einem eDiscovery-Fall zugeordnetes Archiv für ein Postfach platziert wird, werden gelöschte Elemente aus dem Unterordner Löschungen in den DiscoveryHolds-Unterordner verschoben und beibehalten, bis das Postfach aus dem eDiscovery-Archiv freigegeben wird.
