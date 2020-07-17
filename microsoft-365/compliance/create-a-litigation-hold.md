---
title: Erstellen einer Aufbewahrung für juristische Zwecke
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: Hier erfahren Sie, wie Sie ein Postfach auf das Beweissicherungsverfahren setzen und während einer Untersuchung alle Postfachinhalte beibehalten.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 9c62dfcd9e4cf1e3cc75e029b250c7abe80de6df
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818044"
---
# <a name="create-a-litigation-hold"></a>Erstellen einer Aufbewahrung für juristische Zwecke

Sie können ein Postfach auf das Beweissicherungsverfahren setzen, um alle Postfachinhalte einschließlich der gelöschten Elemente und der ursprünglichen Versionen geänderter Elemente beizubehalten. Wenn Sie ein Benutzerpostfach auf das Beweissicherungsverfahren setzen, wird der Inhalt im Archivpostfach des Benutzers (sofern aktiviert) ebenfalls beibehalten. Wenn Sie einen Haltestatus erstellen, können Sie eine Aufbewahrungsdauer angeben (auch als *zeitbasierter Haltestatus*bezeichnet), sodass gelöschte und geänderte Elemente für einen bestimmten Zeitraum aufbewahrt und dann endgültig aus dem Postfach gelöscht werden. Oder Sie können Inhalte auf unbestimmte Zeit beibehalten (als *endlos Sperre*bezeichnet) oder bis das Beweissicherungsverfahren entfernt wird. Wenn Sie einen Zeitraum für die Aufbewahrungsdauer angeben, wird er ab dem Datum berechnet, an dem eine Nachricht empfangen oder ein Postfachelement erstellt wird. 
  
Hier erfahren Sie, was passiert, wenn Sie ein Beweissicherungsverfahren erstellen.
  
- Elemente, die vom Benutzer dauerhaft gelöscht werden, werden für die Dauer des Haltestatus im Ordner "refundable Items" im Postfach des Benutzers aufbewahrt.
    
- Elemente, die vom Benutzer aus dem Ordner "refundable Items" gelöscht werden, werden für die Dauer des Haltestatus aufbewahrt.
    
- Das Speicherkontingent für den Ordner "refundable Items" wird von 30 GB auf 110 GB erhöht.
    
- Elemente in der primären und der Archivpostfächer des Benutzers werden beibehalten.
    
## <a name="assign-an-exchange-online-plan-2-license"></a>Zuweisen einer Lizenz für Exchange Online Plan 2

- Um ein Exchange Online Postfach in das Beweissicherungsverfahren einzufügen, muss ihm eine Exchange Online Plan 2-Lizenz zugewiesen werden. Wenn einem Postfach eine Exchange Online Plan 1-Lizenz zugewiesen ist, müssen Sie ihm eine separate Exchange Online-Archivierungslizenz zuweisen, um ihn in die Warteschleife zu versetzen.
    

## <a name="place-a-mailbox-on-litigation-hold"></a>Aktivieren des Beweissicherungsverfahrens für ein Postfach

Hier finden Sie die Schritte zum Aufbewahren eines Postfachs für das Beweissicherungsverfahren mithilfe der Exchange-Verwaltungskonsole.

1. Wechseln Sie zu, [https://outlook.office.com/ecp](https://outlook.office.com/ecp) und melden Sie sich mit ihrem globalen Administratorkonto an.

2. Klicken Sie im linken Navigationsbereich auf **Empfänger > Postfächer** .

3. Wählen Sie das Postfach aus, das Sie in das Beweissicherungsverfahren einordnen möchten, und klicken Sie dann auf **Bearbeiten**.

4. Klicken Sie auf der Eigenschaftenseite des Postfachs auf **Postfachfunktionen**.
    
5. Klicken Sie unter **Beweissicherungsverfahren: Deaktiviert** auf **Aktivieren**, um für das Postfach das Beweissicherungsverfahren zu aktivieren.
    
6. Geben Sie auf der Seite **Beweissicherungsverfahren** die folgenden optionalen Informationen ein: 
    
    - **Dauer des beweissicherungsverfahrens (Tage)** – verwenden Sie dieses Feld, um einen zeitbasierten Speicher zu erstellen und anzugeben, wie lange Postfachelemente aufbewahrt werden, wenn das Postfach auf das Beweissicherungsverfahren festgelegt wird. Der Zeitraum beginnt mit dem Datum, an dem das Postfachelement empfangen oder erstellt wurde. Wenn die Aufbewahrungsdauer für ein bestimmtes Element abläuft, wird das Element nicht mehr beibehalten. Wenn Sie dieses Feld leer lassen, werden Elemente auf unbestimmte Zeit beibehalten oder bis der Haltebereich entfernt wird. Geben Sie die Dauer in Tagen an.
    
    - **Hinweis** : Verwenden Sie dieses Feld, um dem Benutzer mitzuteilen, dass sein Postfach auf das Beweissicherungsverfahren festgehalten wird. Die Notiz wird auf der Seite Kontoinformationen im Postfach des Benutzers angezeigt, wenn Sie Outlook 2010 oder höher verwenden. Um auf diese Seite zuzugreifen, können Benutzer in Outlook auf **Datei** klicken.
    
    - **URL** – verwenden Sie dieses Feld, um den Benutzer zu einer Website zu leiten, um weitere Informationen zur Aufbewahrung von Beweissicherungsverfahren zu erhalten. Diese URL wird auf der Seite Kontoinformationen im Postfach des Benutzers angezeigt, wenn Sie Outlook 2010 oder höher verwenden. Um auf diese Seite zuzugreifen, können Benutzer in Outlook auf **Datei** klicken..

7. Klicken Sie auf der Seite **Beweissicherungsverfahren** auf **Speichern** , und klicken Sie dann auf der Seite Postfacheigenschaften auf **Speichern** .

### <a name="create-a-litigation-hold-using-powershell"></a>Erstellen eines beweissicherungsverfahrens mithilfe von PowerShell

Sie können auch ein Beweissicherungsverfahren erstellen, indem Sie den folgenden Befehl in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)ausführen:

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

Der vorherige Befehl behält Elemente auf unbestimmte Zeit bei, da die Aufbewahrungsdauer nicht angegeben ist. Zum Erstellen eines zeitbasierten haltebereichs mit dem folgenden Befehl:

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

Weitere Informationen finden Sie unter [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).

## <a name="how-does-litigation-hold-work"></a>Wie funktioniert das Beweissicherungsverfahren?

Beim normalen Löschworkflow wird ein dauerhaft gelöschtes (UMSCHALT+ENTF) oder aus dem Ordner „Gelöschte Elemente" gelöschtes Postfachelement in den Unterordner „Löschvorgänge" des Ordners „Wiederherstellbare Elemente" verschoben. Beim Anwenden einer Löschrichtlinie (hierbei handelt es sich um ein Aufbewahrungstag mit einer konfigurierten Aufbewahrungsaktion) werden Elemente auch nach Ablauf des Aufbewahrungszeitraums in den Unterordner „Löschvorgänge" verschoben. Beim dauerhaften Löschen eines Elements im Ordner „Wiederherstellbare Elemente" durch einen Benutzer oder nach Ablauf der Aufbewahrungsdauer wird das Element in den Unterordner „Endgültige Löschvorgänge" des Ordners „Wiederherstellbare Elemente" verschoben und zum endgültigen Löschen markiert. Das Element wird beim nächsten Verarbeiten des Postfachs vom Assistenten für verwalteten Ordner aus Exchange dauerhaft gelöscht.

Ist für das Postfach das Beweissicherungsverfahren aktiviert, werden die Elemente im Unterordner „Endgültige Löschvorgänge" für die für das Beweissicherungsverfahren angegebene Aufbewahrungsdauer aufbewahrt. Die Aufbewahrungsdauer wird anhand des ursprünglichen Datums berechnet,an dem ein Element empfangen oder erstellt wurde und legt fest, wie lange die Elemente im Unterordner „Endgültige Löschvorgänge" aufbewahrt werden. Wenn die Aufbewahrungsdauer für ein Element im Unterordner „Endgültige Löschvorgänge" abläuft, wird das Element zum endgültigen Löschen vorgemerkt und beim nächsten Verarbeiten des Postfachs vom Assistenten für verwalteten Ordner dauerhaft aus Exchange gelöscht. Wenn die dauerhafte Aufbewahrung für ein Postfach aktiviert ist, werden die Elemente nicht aus dem Unterordner „Endgültige Löschvorgänge" gelöscht.

Die folgende Abbildung zeigt die Unterordner in den Ordnern „Wiederherstellbare Elemente" und den Aufbewahrungsworkflowprozess.

![Lebenszyklus von Beweissicherungsverfahren](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> Wenn ein Haltebereich, der einem eDiscovery-Fall zugeordnet ist, in einem Postfach abgelegt wird, werden gelöschte Elemente aus dem Unterordner "Deletions" in den Unterordner DiscoveryHolds verschoben und bleiben erhalten, bis das Postfach aus der eDiscovery-Aufbewahrungsstelle freigegeben wird.
  
