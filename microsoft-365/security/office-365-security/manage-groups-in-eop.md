---
title: Verwalten von Gruppen in EOP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: Sie können Exchange Online Protection (EOP) zur Erstellung E-Mail-aktivierter Gruppen für eine Exchange-Organisation verwenden. Sie können EOP auch verwenden, um Gruppeneigenschaften zu definieren oder zu aktualisieren, über die Mitgliedschaften, E-Mail-Adressen und andere Aspekte von Gruppen festgelegt werden.
ms.openlocfilehash: 1efbb32635d6dd2a66c1039b04f57c4910d927c4
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441522"
---
# <a name="manage-groups-in-eop"></a>Verwalten von Gruppen in EOP

 Sie können Exchange Online Protection (EOP) zur Erstellung E-Mail-aktivierter Gruppen für eine Exchange-Organisation verwenden. Sie können EOP auch verwenden, um Gruppeneigenschaften zu definieren oder zu aktualisieren, über die Mitgliedschaften, E-Mail-Adressen und andere Aspekte von Gruppen festgelegt werden. Sie können je nach Bedarf Verteiler- oder Sicherheitsgruppen anlegen. Diese Gruppen können mithilfe des Exchange Admin Center (EAC) oder über Windows Remote-PowerShell erstellt werden.

## <a name="types-of-mail-enabled-groups"></a>Arten von E-Mail-aktivierten Gruppen

Sie können für Ihre Exchange-Organisation zwei Arten von Gruppen erstellen:

- Verteilergruppen sind Sammlungen von e-Mail-Benutzern, beispielsweise ein Team oder eine andere Ad-hoc-Gruppe, die e-Mails zu einem gemeinsamen Interessenbereich empfangen oder senden müssen. Verteilergruppen sind exklusiv für die Verteilung von E-Mail-Nachrichten vorgesehen. In EOP wird mit dem Begriff "Verteilergruppe" jede E-Mail-aktivierte Gruppe bezeichnet, egal, ob sie sich in einem Sicherheitskontext befindet oder nicht.

- Sicherheitsgruppen sind Sammlungen von e-Mail-Benutzern, die Zugriffsberechtigungen für Administratorrollen benötigen. Sie könnten z. B. bestimmten Gruppen von Benutzern Berechtigungen für Administratorrollen gewähren, sodass diese Benutzer dann Anti-Span- und Anti-Malware-Einstellungen konfigurieren können.

    > [!NOTE]
    > Standardmäßig ist für alle neuen E-Mail-aktivierten Sicherheitsgruppen die Authentifizierung aller Absender erforderlich. Auf diese Weise wird verhindert, dass externe Absender Nachrichten an E-Mail-aktivierte Sicherheitsgruppen senden können.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter Eintrag "Verteilergruppen und Sicherheitsgruppen" im Thema [Featureberechtigungen in EOP](feature-permissions-in-eop.md).

- Informationen zum Öffnen des Exchange Admin Center finden Sie unter [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Beachten Sie, dass beim Erstellen und Verwalten von Gruppen mithilfe von Exchange Online Protection PowerShell-Cmdlets möglicherweise Einschränkungen auftreten.

- In den PowerShell-Verfahren in diesem Thema wird eine Batch Verarbeitungsmethode verwendet, die zu einer Ausbreitungs Verzögerung von ein paar Minuten führt, bevor die Ergebnisse der Befehle angezeigt werden.

- Wie Sie mit Windows PowerShell eine Verbindung mit Exchange Online Protection herstellen, können Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) nachlesen.

- Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Liegt ein Problem vor? Fragen Sie im Forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) nach Hilfe.

## <a name="create-a-group-in-the-eac"></a>Erstellen einer Gruppe im EAC

1. Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.

2. Klicken **** ![Sie auf neues](../media/ITPro-EAC-AddIcon.gif)Symbol hinzufügen, und klicken Sie dann je nach Ihren Anforderungen auf **Verteilergruppe** oder **Sicherheitsgruppe**.

3. Konfigurieren Sie auf der Seite **neue Verteilergruppe** oder **neue Sicherheitsgruppe** die folgenden Einstellungen:

   - **Anzeigename**: Geben Sie einen Anzeigenamen ein, der für Ihre Organisation eindeutig ist und für EoP-Benutzer sinnvoll ist. Der Anzeigename ist erforderlich.

   - **Alias**: Geben Sie einen Gruppen Alias mit bis zu 64 Zeichen ein, der für Ihre Organisation eindeutig ist. Wenn ein EOP-Benutzer diesen Alias in die Zeile An: einer E-Mail eingibt, wird er in den Anzeigenamen der Gruppe aufgelöst. Wenn Sie den Alias ändern, wird die primäre SMTP-Adresse für die Gruppe ebenfalls geändert und enthält dann den neuen Alias. Der Alias ist erforderlich.

   - **Beschreibung**: Geben Sie eine Beschreibung der Gruppe ein, damit Benutzer den Zweck der Gruppe kennen.

   - **Besitzer**: Standardmäßig ist die Person, die die Gruppe erstellt, der Besitzer. Sie können einen Besitzer hinzufügen, indem Sie hinzu](../media/ITPro-EAC-AddIcon.gif)fügen **Symbol hinzufügen auswählen.** ![ Jede Gruppe muss mindestens einen Besitzer aufweisen.

     > [!NOTE]
     > Besitzer von Gruppen müssen kein Mitglied der jeweiligen Gruppe sein.

   - **Mitglieder**: in diesem Abschnitt können Sie Gruppenmitglieder hinzufügen und angeben, ob eine Genehmigung erforderlich ist, damit Personen der Gruppe beitreten oder diese verlassen können. Um der Gruppe Mitglieder hinzuzufügen, klicken Sie auf Add](../media/ITPro-EAC-AddIcon.gif)-Symbol **Hinzufügen** ![.

4. Klicken Sie auf **OK**, um zur Ursprungsseite zurückzukehren.

5. Wenn Sie fertig sind, klicken Sie auf **Speichern**, um die Gruppe zu erstellen. Die neue Gruppe sollte in der Liste der Gruppen angezeigt werden.

## <a name="edit-or-remove-a-group-in-the-eac"></a>Bearbeiten oder Entfernen einer Gruppe im EAC

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Empfänger** \> **Gruppen**.

2. Führen Sie einen der folgenden Schritte aus:

   - So bearbeiten Sie eine Gruppe: Klicken Sie in der Liste der Gruppen auf die Gruppe, die Sie anzeigen oder ändern möchten, und **** ![klicken Sie dann](../media/ITPro-EAC-EditIcon.gif)auf Bearbeitungssymbol bearbeiten. Sie können allgemeine Einstellungen aktualisieren, Gruppenbesitzer hinzufügen oder entfernen sowie Gruppenmitglieder bei Bedarf hinzufügen oder entfernen.

   - So entfernen Sie eine Gruppe: Wählen Sie die Gruppe **** ![aus, und](../media/ITPro-EAC-RemoveIcon.gif)klicken Sie auf entfernen-Symbol entfernen.

3. Wenn Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>Erstellen, Bearbeiten oder Entfernen einer Gruppe mithilfe von Windows Remote-PowerShell

Dieser Abschnitt enthält Informationen zum Erstellen von Gruppen und zum Ändern der Eigenschaften in Exchange Online Protection PowerShell. Es wird außerdem gezeigt, wie eine vorhandene Gruppe entfernt wird.

### <a name="create-a-group-using-remote-windows-powershell"></a>Erstellen einer Gruppe mithilfe von Remote Windows PowerShell

In diesem Beispiel wird das [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup)-Cmdlet verwendet, um eine Verteilergruppe mit dem Alias "itadmin" und dem Namen "IT Administrators" zu erstellen. Außerdem werden Benutzer als Mitglieder der Gruppe hinzugefügt.

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

**Hinweis**: Wenn Sie anstelle einer Verteilergruppe eine Sicherheitsgruppe erstellen möchten, verwenden Sie `Security` den Wert für den *Type* -Parameter.

Um sicherzustellen, dass Sie die Gruppe IT-Administratoren erfolgreich erstellt haben, führen Sie den folgenden Befehl aus, um Informationen über die neue Gruppe anzuzeigen:

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).

Um eine Liste der Mitglieder in der Gruppe abzurufen, führen Sie den folgenden Befehl aus:

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).

Um eine vollständige Liste aller ihrer Gruppen zu erhalten, führen Sie den folgenden Befehl aus:

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a>Ändern der Eigenschaften einer Gruppe mithilfe von Remote Windows PowerShell

Ein Vorteil der Verwendung von PowerShell anstelle der Exchange-Verwaltungskonsole ist die Möglichkeit, Eigenschaften für mehrere Gruppen zu ändern.

Im folgenden finden Sie einige Beispiele für die Verwendung von Exchange Online Protection PowerShell zum Ändern von Gruppeneigenschaften.

In diesem Beispiel wird die primäre SMTP-Adresse (auch als Antwortadresse bezeichnet) für die Gruppe "Seattle Employees" in Sea.Employees@contoso.com verwendet.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).

Um zu überprüfen, ob Sie die Eigenschaften für die Gruppe erfolgreich geändert haben, führen Sie den folgenden Befehl aus, um den neuen Wert zu überprüfen:

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

In diesem Beispiel werden alle Mitglieder der Gruppe "Seattle Employees" aktualisiert. Verwenden Sie ein Komma, um alle Mitglieder voneinander zu trennen.

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Update-EOPDistributionGroupMember](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).

Um eine Liste aller Mitglieder in der Gruppe "Seattle Employees" abzurufen, führen Sie den folgenden Befehl aus:

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a>Entfernen einer Gruppe mithilfe von Remote Windows PowerShell

In diesem Beispiel wird die Verteilergruppe "IT-Administratoren" entfernt.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).

Um zu überprüfen, ob die Gruppe entfernt wurde, führen Sie den folgenden Befehl aus, und vergewissern Sie sich, dass die Gruppe (in diesem Fall "IT-Administratoren") gelöscht wurde.

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
