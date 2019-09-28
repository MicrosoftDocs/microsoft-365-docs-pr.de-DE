---
title: 'Erteilen von Benutzern den Zugriff auf das Compliance Center für Office 365 Security #a0'
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 'Benutzer müssen Berechtigungen im Office 365 Security #a0 Compliance Center zugewiesen werden, bevor Sie alle Sicherheits-und Kompatibilitätsfeatures verwalten können.'
ms.openlocfilehash: 5f9688662714a4a33f2c6e3483cf902e0f61def9
ms.sourcegitcommit: 84d88a857e82b1a8a0d466057a2e330e8b1692e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37305949"
---
# <a name="give-users-access-to-the-office-365-security--compliance-center"></a>Erteilen von Benutzern den Zugriff auf das Compliance Center für Office 365 Security #a0

Benutzer müssen Berechtigungen im Office 365 Security #a0 Compliance Center zugewiesen werden, bevor Sie alle Sicherheits-und Kompatibilitätsfeatures verwalten können. Als Office 365 globaler Administrator oder Mitglied der Mitglied-Rollengruppe im Security #a0 Compliance Center können Sie diese Berechtigungen Benutzern erteilen. Benutzer können nur die Sicherheits-oder Kompatibilitätsfeatures verwalten, auf die Sie Zugriff haben.

Weitere Informationen zu den verschiedenen Berechtigungen, die Sie Benutzern im Security #a0 Compliance Center erteilen können, finden Sie unter [Berechtigungen im Office 365 Security #a1 Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie müssen ein Office 365 globaler Administrator oder ein Mitglied der Rollengruppe Mitglied im Security #a0 Compliance Center sein, um die Schritte in diesem Artikel ausführen zu können.

- Rollengruppen für das Security #a0 Compliance Center haben möglicherweise ähnliche Namen wie die Rollengruppen in Exchange Online, sind aber nicht identisch.

- Rollengruppenmitgliedschaften werden nicht zwischen Exchange Online und dem Security #a0 Compliance Center freigegeben.

- Partner mit Delegierten Zugriffsberechtigungen (DAP) mit verwalten im Namen von (AOBO) Berechtigungen können nicht auf das Sicherheits #a0 Compliance Center zugreifen.

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>Verwenden des Admin Centers, um einem anderen Benutzer Zugriff auf das Security #a0 Compliance Center zu gewähren

1. [Melden Sie sich bei Office 365 an, und wechseln Sie zum Admin Center](https://go.microsoft.com/fwlink/p/?LinkId=525275).

2. Öffnen Sie im Microsoft 365 Admin Center **Admin** Center, und klicken Sie dann auf **Sicherheit #a0 Kompatibilität**.

3. Wechseln Sie im Security #a0 Compliance Center zu **Berechtigungen**.

4. Wählen Sie in der Liste die Rollengruppe aus, der Sie den Benutzer hinzufügen möchten, **** ![und klicken Sie](../media/O365-MDM-CreatePolicy-EditIcon.gif)auf Bearbeitungssymbol bearbeiten.

5. Klicken Sie auf der Eigenschaftenseite der Rollengruppe unter **Mitglieder**auf Add-](../media/ITPro-EAC-AddIcon.gif) Symbol **Hinzufügen**![, und wählen Sie den Namen des Benutzers (oder der Benutzer) aus, den Sie hinzufügen möchten.

6. Wenn Sie alle Benutzer ausgewählt haben, die Sie der Rollengruppe hinzufügen möchten, klicken Sie auf **hinzu\> fügen** und dann auf **OK**.

7. Klicken Sie auf **Speichern**, um die Änderungen an der Rollengruppe zu speichern.

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

1. Wechseln Sie im Security #a0 Compliance Center zu **Berechtigungen**.

2. Wählen Sie in der Liste die Rollengruppe aus, um die Mitglieder anzuzeigen.

3. Auf der rechten Seite in den Rollengruppen Details können Sie die Mitglieder der Rollengruppe anzeigen.

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Verwenden von PowerShell, um einem anderen Benutzer Zugriff auf das Security #a0 Compliance Center zu gewähren

1. Stellen [Sie eine Verbindung mit Office 365 Security #a0 Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

2. Verwenden Sie den Befehl **Add-RoleGroupMember** , um einen Benutzer zur Rolle "Organisationsverwaltung" hinzuzufügen, wie im folgenden Beispiel dargestellt.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **Parameter**:

   - _Identity_ ist die Rollengruppe, der Sie ein Mitglied hinzufügen möchten.

   - _Mitglied_ ist das Postfach, die universelle Sicherheitsgruppe (Universal Security Group, USG) oder der Computer, der der Rollengruppe hinzugefügt werden soll. Sie können immer nur ein Element angeben.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Verwenden Sie das Cmdlet **Get-RoleGroupMember** , um die Mitglieder in der Rollengruppe "Organisationsverwaltung" anzuzeigen, um zu überprüfen, ob Sie Benutzern Zugriff auf das Security #a0 Compliance Center gegeben haben, wie im folgenden Beispiel dargestellt.

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).
