---
title: 'Ausführen eines Administrator-Rollengruppenberichts in EOP '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: Administratoren können erfahren, wie Sie einen Administratorrollengruppen Bericht in Exchange Online Protection (EoP) ausführen. Dieser Bericht protokolliert, wenn ein Administrator Mitglieder zu Administratorrollengruppen hinzufügt oder diese entfernt, protokolliert Microsoft Exchange Online Schutz (EoP) jedes Vorkommen.
ms.openlocfilehash: d9e7db8accae259b3eb332ce17c52c6749c2bec2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598542"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>Ausführen eines Administrator-Rollengruppenberichts in EOP

 Wenn ein Administrator Mitglieder zu Administratorrollengruppen hinzufügt oder diese entfernt, protokolliert Exchange Online Protection (EoP) jedes Vorkommen. Wenn Sie einen Administratorrollengruppen Bericht im Exchange Admin Center (EAC) ausführen, werden Einträge als Suchergebnisse angezeigt und umfassen die betroffenen Rollengruppen, die die Rollengruppenmitgliedschaft geändert haben und wann und welche Mitgliedschafts Aktualisierungen vorgenommen wurden. Mithilfe dieses Berichts können Sie Änderungen an den Administratorberechtigungen überwachen, die den Benutzern in der Organisation zugewiesen sind.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Geschätzte Zeit bis zum Abschließen des Vorgangs: 2 Minuten

- Informationen zum Öffnen des Exchange Admin Center finden Sie unter [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Berichte" im Thema [Featureberechtigungen in EOP](feature-permissions-in-eop.md).

- Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Liegt ein Problem vor? Fragen Sie im Forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) nach Hilfe.

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Ausführen eines Administrator-Rollengruppenberichts mithilfe der Exchange-Verwaltungskonsole

Führen Sie den Bericht Administratorrollengruppe aus, um die Änderungen an Verwaltungsrollengruppen in Ihrer Organisation innerhalb eines bestimmten Zeitrahmens zu finden.

1. Wählen Sie in der Exchange-Verwaltungskonsole **Verwaltung der Richtlinientreue** \> **Überwachung** aus, und klicken Sie anschließend auf **Administrator-Rollengruppenbericht ausführen**.

2. Legen Sie **Startdatum** und **Enddatum** fest. Standardmäßig sucht der Bericht nach Änderungen, die innerhalb der letzten zwei Wochen an Administratorrollengruppen vorgenommen wurden.

3. Um die Änderungen für eine bestimmte Rollengruppe anzuzeigen, klicken Sie auf **Rollengruppen auswählen**. Wählen Sie im nachfolgenden Dialogfeld die Rollengruppe (oder -gruppen) aus, und klicken Sie auf **OK**. Sie können das Feld auch leer lassen, um nach allen geänderten Rollengruppen zu suchen.

4. Klicken Sie auf **Suchen**.

Wenn Änderungen gefunden werden, die mit den angegebenen Kriterien übereinstimmen, werden sie im Ergebnisbereich angezeigt. Klicken Sie auf eine Rollengruppe in den Suchergebnissen, um die Änderungen im Detailbereich anzuzeigen.

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Wenn Sie einen Administrator-Rollengruppenbericht erfolgreich ausgeführt haben, werden die Rollengruppen, die innerhalb des Datumsbereichs geändert wurden, im Suchergebnisbereich angezeigt. Wenn keine Ergebnisse angezeigt werden, wurden im angegebenen Datumsbereich keine Änderungen an Rollengruppen vorgenommen. Wenn Sie davon ausgehen, dass Ergebnisse angezeigt werden sollten, ändern Sie den Datumsbereich, und führen Sie den Bericht erneut aus.

## <a name="monitor-changes-to-role-group-membership"></a>Überwachen von Änderungen an der Rollengruppenmitgliedschaft

Wenn einer Rollengruppe Mitglieder hinzugefügt oder daraus entfernt werden, wird in den im Detailbereich angezeigten Suchergebnissen angegeben, dass die Rollengruppenmitgliedschaft aktualisiert wurde, und die aktuellen Mitglieder werden aufgelistet. In den Ergebnissen ist nicht angegeben, welcher Benutzer hinzugefügt oder entfernt wurde.

Wenn Sie ermitteln möchten, ob ein Benutzer hinzugefügt oder entfernt wurde, müssen zwei separate Einträge im Bericht verglichen werden. Sehen Sie sich beispielsweise die folgenden Protokolleinträge für die Rollengruppe **HelpDesk** an:

> 1/27/2018 4:43 Uhr <br> Administrator <br> Aktualisierte Mitglieder: Administrator;annb,florencef;pilarp <br> 2/06/2018 10:09 Uhr <br> Administrator <br> Aktualisierte Mitglieder: Administrator;annb;florencef;pilarp;tonip <br> 2/19/2018 2:12 Uhr <br> Administrator <br> Aktualisierte Mitglieder: Administrator;annb;florencef;tonip

In diesem Beispiel wurden mit dem Administratorbenutzerkonto folgende Änderungen vorgenommen:

- Am 2/06/2018 wurde der Benutzer tonip hinzugefügt.

- Am 2/19/2018 wurde der Benutzer pilarp entfernt.
