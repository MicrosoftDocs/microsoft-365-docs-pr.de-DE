---
title: Verwalten von Rollengruppen in EoP
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
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Administratoren können erfahren, wie Sie Berechtigungen in der Exchange-Verwaltungskonsole (EAC) in Exchange Online Protection zuweisen oder entfernen.
ms.openlocfilehash: ba2d053e1e75bd8867ebb9eb7f426cde92abd3e8
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352335"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Verwalten von Rollengruppen in EOP als eigenständige Lösung

In Organisationen mit eigenständigen Exchange Online Schutz (EoP) ohne Exchange Online Postfächer können Sie die Exchange-Verwaltungskonsole verwenden, um Benutzer zu Rollengruppen hinzuzufügen. Durch das Hinzufügen von Benutzern zu einer Rollengruppe erhalten die Benutzerberechtigungen für bestimmte Administratoraufgaben. Sie können Benutzer auch aus Rollengruppen entfernen.

Weitere Informationen zu Rollen und Rollengruppen finden Sie unter [Permissions in Standalone EoP](feature-permissions-in-eop.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Informationen zum Öffnen des Exchange Admin Center (EAC) finden Sie unter [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Informationen zum Öffnen eigenständiger EoP PowerShell finden Sie unter [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Rolle "Rollenverwaltung", die standardmäßig der Rollengruppe Mitglied (globale Administratoren) zugewiesen ist. Weitere Informationen finden Sie unter [Berechtigungen in eigenständigen EoP](feature-permissions-in-eop.md) und [Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Liegt ein Problem vor? Fragen Sie im Forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) nach Hilfe.

## <a name="use-the-eac-to-manage-role-groups"></a>Verwalten von Rollengruppen mithilfe der Exchange-Verwaltungskonsole

### <a name="use-the-eac-to-view-role-groups"></a>Anzeigen von Rollengruppen mithilfe der Exchange-Verwaltungskonsole

1. Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**. Alle Rollengruppen in Ihrer Organisation werden hier aufgelistet.

2. Wählen Sie eine Rollengruppe aus. Im Detailbereich werden der **Name**, die **Beschreibung**, die **zugewiesenen Rollen**und die von der Rollengruppe **verwaltete** angezeigt. Sie können diese Informationen auch anzeigen, indem Sie auf Bearbeitungssymbol **Bearbeiten** klicken ![ ](../../media/ITPro-EAC-EditIcon.png) .

### <a name="use-the-eac-to-create-role-groups"></a>Erstellen von Rollengruppen mithilfe der Exchange-Verwaltungskonsole

Wenn Sie eine neue Rollengruppe erstellen, können Sie alle Einstellungen selbst konfigurieren (während der Erstellung der Gruppe oder danach). Sie können auch eine vorhandene Rollengruppe kopieren und ändern.

1. Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**, und führen Sie einen der folgenden Schritte aus:

   - **Manuelles Erstellen einer neuen Rollengruppe**: Klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) .

   - **Kopieren einer vorhandenen Rollengruppe**: Wählen Sie die Rollengruppe aus, die Sie kopieren möchten, und klicken Sie **dann auf Kopie kopieren (** ![ Symbol ](../../media/ITPro-EAC-CopyIcon.png) ).

2. Konfigurieren Sie im Fenster **neue Rollengruppe** , das angezeigt wird, die folgenden Einstellungen:

    - **Name**: Geben Sie einen eindeutigen Namen für die Rollengruppe ein.

    - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Rollengruppe ein.

    - **Rollen**: Klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) oder **Remove** ![ ITPro-EAC-RemoveIcon. gif entfernen ](../../media/ITPro-EAC-RemoveIcon.gif) , um die Rollen auszuwählen oder zu ändern, die der Rollengruppe zugewiesen sind.

    - **Mitglieder**: Klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) oder **Remove** ![ ITPro-EAC-RemoveIcon. gif entfernen ](../../media/ITPro-EAC-RemoveIcon.gif) , um die Rollengruppenmitgliedschaft zu ändern.

3. Wenn Sie fertig sind, klicken Sie auf **Speichern** , um die Rollengruppe zu erstellen.

### <a name="use-the-eac-to-modify-role-groups"></a>Ändern von Rollengruppen mithilfe der Exchange-Verwaltungskonsole

Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**, wählen Sie die Rollengruppe aus, die Sie ändern möchten, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-EditIcon.png) .

Dieselben Optionen stehen zur Verfügung, wenn Sie Rollengruppen wie beim Erstellen von Rollengruppen ändern. Sie können:

- Ändern Sie den Namen und die Beschreibung.

- Hinzufügen und Entfernen von Verwaltungsrollen (Rollenzuweisungen erstellen oder entfernen).

- Hinzufügen und Entfernen von Mitgliedern.

**Hinweis**: einige Rollengruppen (beispielsweise Organisationsverwaltung) schränken die Rollen ein, die Sie aus der Gruppe entfernen können.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen

1. Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**, wählen Sie die Rollengruppe aus, die Sie ändern möchten, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-EditIcon.png) .

2. Führen Sie auf der Seite Eigenschaften der Rollengruppe, die geöffnet wird, im Abschnitt **memebers** einen der folgenden Schritte aus:

   - Klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) . Suchen Sie auf der angezeigten Seite den Benutzer, den Wou hinzufügen möchten, und klicken Sie dann auf **Add->**. Wählen Sie Benutzer aus, und klicken Sie nach Bedarf viele Male auf **Add->** . Klicken Sie nach Abschluss des Vorgangs auf **OK**.

   - Wählen Sie die Benutzer aus, die Sie entfernen möchten, und klicken Sie dann auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

3. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   > [!NOTE]
   > Nachdem Sie Mitglieder hinzugefügt oder aus der Rollengruppe entfernt haben, müssen sich die betroffenen Benutzer möglicherweise abmelden und dann erneut anmelden, um die Änderung ihrer Administratorrechten zu sehen.

### <a name="use-the-eac-to-remove-role-groups"></a>Entfernen von Rollengruppen mithilfe der Exchange-Verwaltungskonsole

Sie können keine integrierten Rollengruppen entfernen, aber Sie können benutzerdefinierte Rollengruppen entfernen, die Sie erstellt haben.

1. Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**.

2. Wählen Sie die Rollengruppe aus, die Sie entfernen möchten, und klicken Sie **dann auf Delete** ![ Delete Icon ](../../media/ITPro-EAC-DeleteIcon.png) .

3. Klicken Sie im Bestätigungsfenster, das angezeigt wird, auf **Ja** .

## <a name="use-powershell-to-manage-role-groups"></a>Verwenden von PowerShell zum Verwalten von Rollengruppen

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Verwenden eigenständiger EoP PowerShell zum Anzeigen von Rollengruppen

Verwenden Sie die folgende Syntax, um eine Rollengruppe anzuzeigen:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Rollengruppen zurückgegeben.

```PowerShell
Get-RoleGroup
```

In diesem Beispiel werden detaillierte Informationen für die Rollengruppe mit dem Namen "Recipient Administrators" zurückgegeben.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

In diesem Beispiel werden alle Rollengruppen zurückgegeben, in denen der Benutzer Julia Mitglied ist. Sie müssen den distinguishedName (DN)-Wert für Julia verwenden, den Sie finden können, indem Sie den folgenden Befehl ausführen: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Verwenden eigenständiger EoP PowerShell zum Erstellen von Rollengruppen

Wenn Sie eine neue Rollengruppe erstellen, können Sie alle Einstellungen manuell konfigurieren (während der Erstellung der Gruppe oder nach). Sie können auch eine vorhandene Rollengruppe kopieren und ändern.

- Verwenden Sie die folgende Syntax, um eine neue Rollengruppe manuell zu erstellen:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Der Parameter _roles_ gibt die Verwaltungsrollen an, die der Rollengruppe mithilfe der folgenden Syntax zugewiesen werden sollen `"Role1","Role1",..."RoleN"` . Sie können die verfügbaren Rollen mithilfe des Cmdlets **Get-ManagementRole** anzeigen.

  - Der Parameter _Members_ gibt die Mitglieder der Rollengruppe mithilfe der folgenden Syntax an: `"Member1","Member2",..."MemberN"` . Sie können Benutzer, universelle Sicherheitsgruppen für e-Mail-aktivierte oder andere Rollengruppen (Sicherheitsprinzipale) angeben.

  In diesem Beispiel wird eine neue Rollengruppe mit dem Namen "Limited Recipient Management" mit den folgenden Einstellungen erstellt:

  - Der Rollengruppe wird die Rolle "Mail Recipients" zugewiesen.

  - Die Benutzer Kim und Martin werden als Mitglieder hinzugefügt.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Führen Sie die folgenden Schritte aus, um eine vorhandene Rollengruppe zu kopieren:

  1. Speichern Sie die Rollengruppe, die Sie kopieren wollen, mithilfe der folgenden Syntax in einer Variablen:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Erstellen Sie die neue Rollengruppe mit der folgenden Syntax:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     Der Parameter _Members_ gibt die Mitglieder der Rollengruppe mithilfe der folgenden Syntax an: `"Member1","Member2",..."MemberN"` . Sie können Benutzer, universelle Sicherheitsgruppen für e-Mail-aktivierte oder andere Rollengruppen (Sicherheitsprinzipale) angeben.

     In diesem Beispiel wird die Rollengruppe "Organisationsverwaltung" in die neue Rollengruppe mit dem Namen "Limited Organization Management" kopiert. Die Mitglieder der Rollengruppe sind Isabelle, Carter und Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Verwenden eigenständiger EoP PowerShell ändern der Liste der Mitglieder in Rollengruppen

- Mit den Cmdlets **Add-RoleGroupMember** und **Remove-RoleGroupMember** werden einzelne Mitglieder einzeln hinzugefügt oder entfernt. Das Cmdlet **Update-RoleGroupMember** kann die vorhandene Liste der Mitglieder ersetzen oder ändern.

- Die Mitglieder einer Rollengruppe können Benutzer, universelle Sicherheitsgruppen (Universal Security Groups, USGS) oder andere Rollengruppen (Sicherheitsprinzipale) sein.

Verwenden Sie die folgende Syntax, um die Mitglieder einer Rollengruppe zu ändern:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Verwenden Sie die folgende Syntax, um die vorhandene Liste der Elemente durch die angegebenen Werte zu _ersetzen_ : `"Member1","Member2",..."MemberN"` .

- Verwenden Sie die folgende Syntax, um die vorhandene Liste der Elemente _selektiv zu ändern_ : `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

In diesem Beispiel werden alle aktuellen Mitglieder der Help Desk-Rollengruppe durch die angegebenen Benutzer ersetzt.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

In diesem Beispiel wird Daigoro Akai hinzugefügt und Valeria Barrio aus der Liste der Mitglieder der Rollengruppe "Helpdesk" entfernt.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Verwenden eigenständiger EoP PowerShell zum Entfernen von Rollengruppen

Sie können keine integrierten Rollengruppen entfernen, aber Sie können benutzerdefinierte Rollengruppen entfernen, die Sie erstellt haben.

Verwenden Sie die folgende Syntax, um eine benutzerdefinierte Rollengruppe zu entfernen:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

In diesem Beispiel wird die Rollengruppe "Schulungs Administratoren" entfernt.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).

### <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie eine Rollengruppe erfolgreich kopiert haben:

- Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**, und überprüfen Sie, ob die Rollengruppe aufgeführt (oder nicht aufgeführt) ist. Wählen Sie die Rollengruppe aus, und überprüfen Sie die Einstellungen im Detail **Edit** Bereich, oder klicken Sie auf ![ Bearbeitungssymbol bearbeiten ](../../media/ITPro-EAC-EditIcon.png) , um die Einstellungen zu überprüfen.

- Ersetzen Sie in Exchange Online PowerShell den Namen der \< Rollengruppe \> durch den Namen der Rollengruppe, und führen Sie den folgenden Befehl aus, um zu überprüfen, ob die Rollengruppe vorhanden ist (oder nicht vorhanden ist), und überprüfen Sie die Einstellungen:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
