---
title: Verwalten von Rollengruppen in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Administratoren erfahren, wie Sie Berechtigungen im Exchange Admin Center (EAC) in Exchange Online Protection zuweisen oder entfernen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e712c47d49508934ec7dd2438beff00eb6e1a20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926880"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Verwalten von Rollengruppen in EOP als eigenständige Lösung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection eigenständig](exchange-online-protection-overview.md)

In eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer können Sie das Exchange Admin Center (EAC) verwenden, um Benutzer zu Rollengruppen hinzuzufügen. Durch hinzufügen eines Benutzers zu einer Rollengruppe erhält der Benutzer Berechtigungen zum Ausführen bestimmter Administratoraufgaben. Sie können auch Benutzer aus Rollengruppen entfernen.

Weitere Informationen zu Rollen und Rollengruppen finden Sie unter [Permissions in standalone EOP](feature-permissions-in-eop.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Informationen zum Öffnen des Exchange Admin Center (EAC) finden Sie unter [Exchange Admin Center im eigenständigen EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Informationen zum Öffnen der eigenständigen EOP PowerShell finden Sie [unter Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online Protection die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie  die Rollenverwaltungsrolle, die standardmäßig der **Rollengruppe** Organisationsverwaltung zugewiesen ist. Weitere Informationen finden Sie unter [Permissions in standalone EOP](feature-permissions-in-eop.md) und [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Informationen zu Tastenkombinationen, die für die Verfahren in diesem Artikel gelten können, finden Sie unter [Tastenkombinationen für](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)das Exchange Admin Center in Exchange Online .

> [!TIP]
> Liegt ein Problem vor? Bitten Sie im [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)-Forum um Hilfe.

## <a name="use-the-eac-to-manage-role-groups"></a>Verwalten von Rollengruppen mithilfe der EAC

### <a name="use-the-eac-to-view-role-groups"></a>Anzeigen von Rollengruppen mithilfe der EAC

1. Wechseln Sie in der EAC zu **Berechtigungen** \> **Administratorrollen**. Alle Rollengruppen in Ihrer Organisation werden hier aufgelistet.

2. Wählen Sie eine Rollengruppe aus. Der Bereich Details zeigt **den Namen**, **Beschreibung**, **Zugewiesene Rollen** und **Verwaltet von** der Rollengruppe an. Sie können diese Informationen auch anzeigen, indem Sie auf Bearbeiten **(Symbol)** ![ ](../../media/ITPro-EAC-EditIcon.png) klicken.

### <a name="use-the-eac-to-create-role-groups"></a>Erstellen von Rollengruppen mithilfe der EAC

Wenn Sie eine neue Rollengruppe erstellen, können Sie alle Einstellungen selbst konfigurieren (während der Erstellung der Gruppe oder danach). Sie können auch eine vorhandene Rollengruppe kopieren und ändern.

1. Wechseln Sie in der EAC zu **Berechtigungen** \> **Administratorrollen,** und gehen Sie dann einen der folgenden Schritte aus:

   - **Manuelles Erstellen einer neuen Rollengruppe**: Klicken **Sie auf Hinzufügen** ![ -Symbol ](../../media/ITPro-EAC-AddIcon.png) .

   - **Kopieren einer vorhandenen Rollengruppe:** Wählen Sie die Rollengruppe aus, die Sie kopieren möchten, und klicken Sie dann auf **Kopiersymbol** ![ ](../../media/ITPro-EAC-CopyIcon.png) .

2. Konfigurieren Sie **im angezeigten** Fenster Neue Rollengruppen die folgenden Einstellungen:

    - **Name**: Geben Sie einen eindeutigen Namen für die Rollengruppe ein.

    - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Rollengruppe ein.

    - **Rollen**: Klicken Sie **auf Hinzufügen** (Symbol) oder Entfernen (Entfernen), um die Rollen auszuwählen oder zu ändern, die ![ der ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Rollengruppe zugewiesen sind.

    - **Mitglieder**: Klicken Sie **auf** ![ Hinzufügen(symbol) ](../../media/ITPro-EAC-AddIcon.png) oder **Entfernen** ![ (Symbol entfernen), ](../../media/ITPro-EAC-RemoveIcon.gif) um die Rollengruppenmitgliedschaft zu ändern.

3. Klicken Sie nach Abschluss des Abschlusses auf **Speichern,** um die Rollengruppe zu erstellen.

### <a name="use-the-eac-to-modify-role-groups"></a>Ändern von Rollengruppen mithilfe der EAC

Wechseln Sie in der EAC zu **Berechtigungen** Administratorrollen, wählen Sie die Rollengruppe aus, die Sie ändern möchten, und klicken Sie dann \> auf **Bearbeiten** ![ (Symbol ](../../media/ITPro-EAC-EditIcon.png) bearbeiten).

Beim Ändern von Rollengruppen stehen dieselben Optionen zur Verfügung wie beim Erstellen von Rollengruppen. Sie können:

- Ändern Sie den Namen und die Beschreibung.

- Hinzufügen und Entfernen von Verwaltungsrollen (Erstellen oder Entfernen von Rollenzuweisungen).

- Hinzufügen und Entfernen von Mitgliedern.

**Hinweis:** Einige Rollengruppen (z. B. Organisationsverwaltung) beschränken die Rollen, die Sie aus der Gruppe entfernen können.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Ändern der Liste der Mitglieder in Rollengruppen mithilfe der EAC

1. Wechseln Sie in der EAC **zu** Berechtigungen \> **Administratorrollen,** wählen Sie die  Rollengruppe aus, die Sie ändern möchten, und klicken Sie dann auf Bearbeiten ![ (Symbol). ](../../media/ITPro-EAC-EditIcon.png)

2. Gehen Sie auf der Seite rollengruppeneigenschaften, die im Abschnitt **Mitglieder** geöffnet wird, einen der folgenden Schritte aus:

   - Klicken **Sie auf Hinzufügen** ![ (Symbol) ](../../media/ITPro-EAC-AddIcon.png) . Suchen Sie auf der angezeigten Seite nach dem Benutzer, den wou hinzufügen möchte, und klicken Sie dann **auf Hinzufügen ->**. Wählen Sie Benutzer aus, und klicken **Sie >** bei Bedarf auf hinzufügen. Klicken Sie nach Abschluss des Vorgangs auf **OK**.

   - Wählen Sie die Benutzer aus, die Sie entfernen möchten, und klicken Sie dann auf **Entfernen** ![ -Symbol ](../../media/ITPro-EAC-RemoveIcon.gif) .

3. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   > [!NOTE]
   > Nachdem Sie Mitglieder hinzugefügt oder aus der Rollengruppe entfernt haben, müssen sich die betroffenen Benutzer möglicherweise abmelden und dann erneut anmelden, um die Änderung ihrer Administratorrechten zu sehen.

### <a name="use-the-eac-to-remove-role-groups"></a>Entfernen von Rollengruppen mithilfe der EAC

Sie können keine integrierten Rollengruppen entfernen, aber sie können benutzerdefinierte Rollengruppen entfernen, die Sie erstellt haben.

1. Wechseln Sie in der EAC zu **Berechtigungen** \> **Administratorrollen**.

2. Wählen Sie die Rollengruppe aus, die Sie entfernen möchten, und klicken Sie dann **auf Löschen** ![ -Symbol ](../../media/ITPro-EAC-DeleteIcon.png) .

3. Klicken **Sie im** angezeigten Bestätigungsfenster auf Ja.

## <a name="use-powershell-to-manage-role-groups"></a>Verwalten von Rollengruppen mithilfe von PowerShell

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Verwenden der eigenständigen EOP PowerShell zum Anzeigen von Rollengruppen

Verwenden Sie die folgende Syntax, um eine Rollengruppe anzuzeigen:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Rollengruppen zurückgegeben.

```PowerShell
Get-RoleGroup
```

In diesem Beispiel werden detaillierte Informationen für die Rollengruppe "Empfängeradministratoren" zurückgegeben.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

In diesem Beispiel werden alle Rollengruppen zurückgegeben, bei denen die Benutzerin Julia Mitglied ist. Sie müssen den DistinguishedName (DN)-Wert für Julia verwenden, den Sie finden, indem Sie den Befehl ausführen: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Verwenden der eigenständigen EOP PowerShell zum Erstellen von Rollengruppen

Wenn Sie eine neue Rollengruppe erstellen, können Sie alle Einstellungen manuell konfigurieren (während der Erstellung der Gruppe oder danach). Sie können auch eine vorhandene Rollengruppe kopieren und ändern.

- Verwenden Sie die folgende Syntax, um eine neue Rollengruppe manuell zu erstellen:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Der _Parameter Roles_ gibt die Verwaltungsrollen an, die der Rollengruppe mithilfe der folgenden Syntax zugewiesen werden. `"Role1","Role1",..."RoleN"` Sie können die verfügbaren Rollen mit dem Cmdlet **Get-ManagementRole** anzeigen.

  - Der _Parameter Members_ gibt die Mitglieder der Rollengruppe mithilfe der folgenden Syntax an: `"Member1","Member2",..."MemberN"` . Sie können Benutzer, Mail-aktivierte universelle Sicherheitsgruppen (USGs) oder andere Rollengruppen (Sicherheitsprinzipale) angeben.

  In diesem Beispiel wird eine neue Rollengruppe namens "Eingeschränkte Empfängerverwaltung" mit den folgenden Einstellungen erstellt:

  - Der Rollengruppe wird die Rolle "Mail Recipients" zugewiesen.

  - Die Benutzer Kim und Martin werden als Mitglieder hinzugefügt.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Gehen Sie wie folgt vor, um eine vorhandene Rollengruppe zu kopieren:

  1. Speichern Sie die Rollengruppe, die Sie kopieren wollen, mithilfe der folgenden Syntax in einer Variablen:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Erstellen Sie die neue Rollengruppe mit der folgenden Syntax:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     Der _Parameter Members_ gibt die Mitglieder der Rollengruppe mithilfe der folgenden Syntax an: `"Member1","Member2",..."MemberN"` . Sie können Benutzer, Mail-aktivierte universelle Sicherheitsgruppen (USGs) oder andere Rollengruppen (Sicherheitsprinzipale) angeben.

     In diesem Beispiel wird die Rollengruppe Organisationsverwaltung in die neue Rollengruppe mit dem Namen "Eingeschränkte Organisationsverwaltung" kopiert. Die Rollengruppenmitglieder sind Isabelle, Carter und Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-RoleGroup](/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Verwenden der eigenständigen EOP PowerShell Ändern der Liste der Mitglieder in Rollengruppen

- Die **Cmdlets Add-RoleGroupMember** und **Remove-RoleGroupMember** fügen einzelne Mitglieder einzeln hinzu oder entfernen diese. Das **Cmdlet Update-RoleGroupMember** kann die vorhandene Mitgliederliste ersetzen oder ändern.

- Die Mitglieder einer Rollengruppe können Benutzer, E-Mail-aktivierte universelle Sicherheitsgruppen (UNIVERSELLE Sicherheitsgruppen) oder andere Rollengruppen (Sicherheitsprinzipale) sein.

Verwenden Sie die folgende Syntax, um die Mitglieder einer Rollengruppe zu ändern:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Verwenden _Sie die_ folgende Syntax, um die vorhandene Liste der Mitglieder durch die angegebenen Werte zu ersetzen: `"Member1","Member2",..."MemberN"` .

- Verwenden _Sie die folgende_ Syntax, um die vorhandene Mitgliederliste selektiv zu ändern: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

In diesem Beispiel werden alle aktuellen Mitglieder der Rollengruppe HelpDesk durch die angegebenen Benutzer ersetzt.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

In diesem Beispiel wird Daigoro Akai hinzugefügt und Valeria Barrio aus der Liste der Mitglieder in der Rollengruppe HelpDesk entfernt.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Update-RoleGroupMember](/powershell/module/exchange/Update-RoleGroupMember).

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Verwenden der eigenständigen EOP PowerShell zum Entfernen von Rollengruppen

Sie können keine integrierten Rollengruppen entfernen, aber sie können benutzerdefinierte Rollengruppen entfernen, die Sie erstellt haben.

Verwenden Sie die folgende Syntax, um eine benutzerdefinierte Rollengruppe zu entfernen:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

In diesem Beispiel wird die Rollengruppe "Schulungsadministratoren" entfernt.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup).

### <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Gehen Sie wie folgt vor, um sicherzustellen, dass Sie eine Rollengruppe erfolgreich kopiert haben:

- Wechseln Sie in der EAC zu **Berechtigungen** Administratorrollen, und überprüfen Sie, ob die \> Rollengruppe aufgeführt ist (oder nicht aufgeführt). Wählen Sie die Rollengruppe aus, und überprüfen Sie die Einstellungen im Detailbereich, oder klicken Sie **auf** Bearbeiten ![ ](../../media/ITPro-EAC-EditIcon.png) (Symbol), um die Einstellungen zu überprüfen.

- Ersetzen Sie in Exchange Online PowerShell durch den Namen der Rollengruppe, und führen Sie den folgenden Befehl aus, um zu überprüfen, ob die Rollengruppe vorhanden (oder nicht vorhanden) ist, und überprüfen Sie die \<Role Group Name\> Einstellungen:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```