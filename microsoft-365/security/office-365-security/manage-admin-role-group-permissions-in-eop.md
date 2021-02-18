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
ms.openlocfilehash: ce272985f195f44c57848e6861cefb64431698b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289925"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Verwalten von Rollengruppen in EOP als eigenständige Lösung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection als eigenständige Lösung](exchange-online-protection-overview.md)

In eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer können Sie das Exchange Admin Center (EAC) verwenden, um Benutzer zu Rollengruppen hinzuzufügen. Durch das Hinzufügen eines Benutzers zu einer Rollengruppe erhält der Benutzer Berechtigungen zum Ausführen bestimmter Administratoraufgaben. Sie können auch Benutzer aus Rollengruppen entfernen.

Weitere Informationen zu Rollen und Rollengruppen finden Sie unter ["Berechtigungen" in EOP als eigenständige Lösung.](feature-permissions-in-eop.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Informationen zum Öffnen des Exchange Admin Centers (EAC) finden Sie im [Exchange Admin Center in EOP als eigenständige Lösung.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Informationen zum Öffnen der eigenständigen EOP PowerShell finden Sie unter [Herstellen einer Verbindung mit Exchange Online Protection PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online Protection die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Rolle **"Rollenverwaltung",** die standardmäßig der Rollengruppe **"Organisationsverwaltung"** zugewiesen ist. Weitere Informationen finden Sie unter "Berechtigungen [in EOP als eigenständige](feature-permissions-in-eop.md) Lösung", und ändern Sie mithilfe der EAC die Liste der Mitglieder in [Rollengruppen.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Informationen zu Tastenkombinationen, die für die Verfahren in diesem Artikel gelten können, finden Sie unter Tastenkombinationen für das [Exchange Admin Center in Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Liegt ein Problem vor? Bitten Sie im [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)-Forum um Hilfe.

## <a name="use-the-eac-to-manage-role-groups"></a>Verwalten von Rollengruppen mithilfe der EAC

### <a name="use-the-eac-to-view-role-groups"></a>Anzeigen von Rollengruppen mithilfe der EAC

1. Wechseln Sie in der EAC **zu** Administratorrollen \> **"Berechtigungen".** Alle Rollengruppen in Ihrer Organisation werden hier aufgelistet.

2. Wählen Sie eine Rollengruppe aus. Im Detailbereich werden **der Name,** **die Beschreibung** **,** die zugewiesenen Rollen und **verwaltet von** der Rollengruppe angezeigt. Sie können diese Informationen auch  anzeigen, indem Sie auf das Symbol ![ "Bearbeiten" ](../../media/ITPro-EAC-EditIcon.png) klicken.

### <a name="use-the-eac-to-create-role-groups"></a>Erstellen von Rollengruppen mithilfe der EAC

Wenn Sie eine neue Rollengruppe erstellen, können Sie alle Einstellungen selbst konfigurieren (während der Erstellung der Gruppe oder danach). Sie können auch eine vorhandene Rollengruppe kopieren und ändern.

1. Wechseln Sie in der EAC zu **Administratorrollen** "Berechtigungen", und gehen Sie dann \> wie folgt vor:

   - **Manuelles Erstellen einer neuen Rollengruppe:** Klicken Sie **auf das Symbol "Hinzufügen".** ![ ](../../media/ITPro-EAC-AddIcon.png)

   - **Kopieren Sie eine vorhandene Rollengruppe:** Wählen Sie die Rollengruppe aus, die Sie kopieren möchten, und klicken Sie dann auf **das** Symbol ![ "Kopieren". ](../../media/ITPro-EAC-CopyIcon.png)

2. Konfigurieren Sie **im angezeigten** Fenster "Neue Rollengruppe" die folgenden Einstellungen:

    - **Name**: Geben Sie einen eindeutigen Namen für die Rollengruppe ein.

    - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Rollengruppe ein.

    - **Rollen:** **Klicken** Sie auf das ![ Symbol "Hinzufügen" oder "Entfernen", um die Rollen auszuwählen oder zu ändern, die ](../../media/ITPro-EAC-AddIcon.png) der  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Rollengruppe zugewiesen sind.

    - **Mitglieder**: Klicken Sie auf das **Symbol** ![ "Hinzufügen" ](../../media/ITPro-EAC-AddIcon.png) oder  ![ "Entfernen", ](../../media/ITPro-EAC-RemoveIcon.gif) um die Rollengruppenmitgliedschaft zu ändern.

3. Wenn Sie fertig sind, klicken Sie auf **"Speichern",** um die Rollengruppe zu erstellen.

### <a name="use-the-eac-to-modify-role-groups"></a>Ändern von Rollengruppen mithilfe der EAC

Wechseln Sie in der EAC zu **Administratorrollen** für Berechtigungen, wählen Sie die Rollengruppe aus, die Sie ändern möchten, und klicken Sie dann auf das Symbol \>   ![ "Bearbeiten". ](../../media/ITPro-EAC-EditIcon.png)

Beim Ändern von Rollengruppen stehen dieselben Optionen zur Verfügung wie beim Erstellen von Rollengruppen. Sie können:

- Ändern Sie den Namen und die Beschreibung.

- Hinzufügen und Entfernen von Verwaltungsrollen (Erstellen oder Entfernen von Rollenzuweisungen).

- Mitglieder hinzufügen und entfernen.

**Hinweis:** Einige Rollengruppen (z. B. Organisationsverwaltung) schränken die Rollen ein, die Sie aus der Gruppe entfernen können.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Ändern der Mitgliederliste in Rollengruppen mithilfe der EAC

1. Wechseln Sie in der EAC zu **Administratorrollen** für Berechtigungen, wählen Sie die Rollengruppe aus, die Sie ändern möchten, und klicken Sie dann auf das Symbol \>   ![ ](../../media/ITPro-EAC-EditIcon.png) "Bearbeiten".

2. Gehen Sie auf der Seite mit  den Rollengruppeneigenschaften, die geöffnet wird, im Abschnitt "Mitglieder" einen der folgenden Schritte aus:

   - Klicken Sie **auf "Hinzufügen"** ![ ](../../media/ITPro-EAC-AddIcon.png) (Symbol). Suchen Sie auf der angezeigten Seite den Benutzer, den Sie hinzufügen möchten, und klicken Sie dann auf **"Add->".** Wählen Sie Benutzer aus, und klicken Sie **bei >** auf "Add->". Klicken Sie nach Abschluss des Vorgangs auf **OK**.

   - Wählen Sie die Benutzer aus, die  Sie entfernen möchten, und klicken Sie dann auf ![ "Entfernen". ](../../media/ITPro-EAC-RemoveIcon.gif)

3. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   > [!NOTE]
   > Nachdem Sie Mitglieder hinzugefügt oder aus der Rollengruppe entfernt haben, müssen sich die betroffenen Benutzer möglicherweise abmelden und dann erneut anmelden, um die Änderung ihrer Administratorrechten zu sehen.

### <a name="use-the-eac-to-remove-role-groups"></a>Entfernen von Rollengruppen mithilfe der EAC

Sie können keine integrierten Rollengruppen entfernen, aber sie können benutzerdefinierte Rollengruppen entfernen, die Sie erstellt haben.

1. Wechseln Sie in der EAC **zu** Administratorrollen \> **"Berechtigungen".**

2. Wählen Sie die Rollengruppe aus, die Sie entfernen möchten, und klicken Sie dann auf **das** Symbol ![ "Löschen". ](../../media/ITPro-EAC-DeleteIcon.png)

3. Klicken **Sie im** angezeigten Bestätigungsfenster auf "Ja".

## <a name="use-powershell-to-manage-role-groups"></a>Verwenden von PowerShell zum Verwalten von Rollengruppen

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Verwenden von eigenständiger EOP PowerShell zum Anzeigen von Rollengruppen

Verwenden Sie die folgende Syntax, um eine Rollengruppe anzuzeigen:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

In diesem Beispiel wird eine Übersichtsliste aller Rollengruppen zurückgegeben.

```PowerShell
Get-RoleGroup
```

In diesem Beispiel werden detaillierte Informationen für die Rollengruppe "Recipient Administrators" zurückgegeben.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

In diesem Beispiel werden alle Rollengruppen zurückgegeben, bei denen die Benutzerin Julia Mitglied ist. Sie müssen den DistinguishedName (DN)-Wert für Julia verwenden, den Sie finden, indem Sie den folgenden Befehl ausführen: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Verwenden von eigenständiger EOP PowerShell zum Erstellen von Rollengruppen

Wenn Sie eine neue Rollengruppe erstellen, können Sie alle Einstellungen manuell konfigurieren (während der Erstellung der Gruppe oder danach). Sie können auch eine vorhandene Rollengruppe kopieren und ändern.

- Verwenden Sie die folgende Syntax, um eine neue Rollengruppe manuell zu erstellen:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Der _Parameter "Roles"_ gibt die Verwaltungsrollen an, die der Rollengruppe mithilfe der folgenden Syntax zugewiesen `"Role1","Role1",..."RoleN"` werden. Sie können die verfügbaren Rollen mit dem Cmdlet **Get-ManagementRole** anzeigen.

  - Der _Parameter "Members"_ gibt die Mitglieder der Rollengruppe mithilfe der folgenden Syntax `"Member1","Member2",..."MemberN"` an: Sie können Benutzer, Mail-aktivierte universelle Sicherheitsgruppen (USGs) oder andere Rollengruppen (Sicherheitsprinzipale) angeben.

  In diesem Beispiel wird eine neue Rollengruppe namens "Limited Recipient Management" mit den folgenden Einstellungen erstellt:

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

  2. Erstellen Sie die neue Rollengruppe mithilfe der folgenden Syntax:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     Der _Parameter "Members"_ gibt die Mitglieder der Rollengruppe mithilfe der folgenden Syntax `"Member1","Member2",..."MemberN"` an: Sie können Benutzer, Mail-aktivierte universelle Sicherheitsgruppen (USGs) oder andere Rollengruppen (Sicherheitsprinzipale) angeben.

     In diesem Beispiel wird die Rollengruppe "Organization Management" in die neue Rollengruppe "Limited Organization Management" kopiert. Die Rollengruppenmitglieder sind Isabelle, Carter undAbella.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Verwenden der eigenständigen EOP PowerShell zum Ändern der Mitgliederliste in Rollengruppen

- Mit **den Cmdlets "Add-RoleGroupMember"** und **"Remove-RoleGroupMember"** werden einzelne Mitglieder einzeln hinzugefügt oder entfernt. Das **Cmdlet "Update-RoleGroupMember"** kann die vorhandene Mitgliederliste ersetzen oder ändern.

- Die Mitglieder einer Rollengruppe können Benutzer, E-Mail-aktivierte universelle Sicherheitsgruppen (Universal Security Groups, USGs) oder andere Rollengruppen (Sicherheitsprinzipale) sein.

Verwenden Sie die folgende Syntax, um die Mitglieder einer Rollengruppe zu ändern:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Verwenden _Sie die_ folgende Syntax, um die vorhandene Mitgliederliste durch die angegebenen Werte zu ersetzen: `"Member1","Member2",..."MemberN"`

- Verwenden _Sie die folgende_ Syntax, um die vorhandene Mitgliederliste selektiv zu ändern: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`

In diesem Beispiel werden alle aktuellen Mitglieder der Rollengruppe "Help Desk" durch die angegebenen Benutzer ersetzt.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

In diesem Beispiel wird Daigoro Akai hinzugefügt und Valeria Barrio aus der Mitgliederliste der Rollengruppe "Help Desk" entfernt.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Verwenden der eigenständigen EOP PowerShell zum Entfernen von Rollengruppen

Sie können keine integrierten Rollengruppen entfernen, aber sie können benutzerdefinierte Rollengruppen entfernen, die Sie erstellt haben.

Verwenden Sie die folgende Syntax, um eine benutzerdefinierte Rollengruppe zu entfernen:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

In diesem Beispiel wird die Rollengruppe "Training Administrators" entfernt.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).

### <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Gehen Sie wie folgt vor, um sicherzustellen, dass Sie eine Rollengruppe erfolgreich kopiert haben:

- Wechseln Sie in der EAC zu **Administratorrollen** für Berechtigungen, und stellen Sie sicher, dass die \> Rollengruppe aufgeführt (oder nicht aufgeführt) ist. Wählen Sie die Rollengruppe aus, und überprüfen  Sie die Einstellungen im Detailbereich, oder klicken Sie auf das Bearbeitungssymbol, ![ um die Einstellungen zu ](../../media/ITPro-EAC-EditIcon.png) überprüfen.

- Ersetzen Sie in Exchange Online PowerShell den Namen der Rollengruppe, und führen Sie den folgenden Befehl aus, um zu überprüfen, ob die Rollengruppe vorhanden (oder nicht vorhanden) ist, und überprüfen Sie die \<Role Group Name\> Einstellungen:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
