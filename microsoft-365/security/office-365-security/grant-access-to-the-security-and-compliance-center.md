---
title: Freigeben des Benutzerzugriffs auf das Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Benutzer müssen Berechtigungen im Microsoft 365 Security & Compliance Center zugewiesen werden, bevor Sie alle Sicherheits-und Kompatibilitätsfeatures verwalten können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d21fef9458c02bd09d6d5ce2129b95571e0f8371
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826601"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Freigeben des Benutzerzugriffs auf das Security & Compliance Center

Benutzer müssen im Security & Compliance Center Berechtigungen zugewiesen werden, bevor Sie alle Sicherheits-und Kompatibilitätsfeatures verwalten können. Als globaler Administrator oder Mitglied der Mitglied-Rollengruppe im Security & Compliance Center können Sie diese Berechtigungen Benutzern erteilen. Benutzer können nur die Sicherheits-oder Kompatibilitätsfeatures verwalten, auf die Sie Zugriff haben.

Weitere Informationen zu den verschiedenen Berechtigungen, die Sie Benutzern im Security & Compliance Center erteilen können, finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie müssen ein globaler Administrator oder ein Mitglied der Rollengruppe Mitglied im Security & Compliance Center sein, um die Schritte in diesem Artikel ausführen zu können.

- Rollengruppen für das Security & Compliance Center haben möglicherweise ähnliche Namen wie die Rollengruppen in Exchange Online, sind aber nicht identisch.

- Rollengruppenmitgliedschaften werden nicht zwischen Exchange Online und dem Security & Compliance Center freigegeben.

- Partner mit delegierter Zugriffsberechtigung (Delegated Access Permission, DAP), die über „Administer On Behalf OF“(AOBO)-Berechtigungen verfügen, können nicht auf das Security & Compliance Center zugreifen.

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>Verwenden des Admin Centers, um einem anderen Benutzer Zugriff auf das Security & Compliance Center zu gewähren

1. [Melden Sie sich an, und wechseln Sie zum Admin Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).

2. Öffnen Sie im Microsoft 365 Admin Center **Admin** Center, und klicken Sie dann auf **Sicherheit & Kompatibilität**.

3. Wechseln Sie im Security & Compliance Center zu **Berechtigungen**.

4. Wählen Sie in der Liste die Rollengruppe aus, der Sie den Benutzer hinzufügen möchten, und klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

5. Klicken Sie auf der Eigenschaftenseite der Rollengruppe unter **Mitglieder**auf Add-Symbol **Hinzufügen**, ![ ](../../media/ITPro-EAC-AddIcon.gif) und wählen Sie den Namen des Benutzers (oder der Benutzer) aus, den Sie hinzufügen möchten.

6. Wenn Sie alle Benutzer ausgewählt haben, die Sie der Rollengruppe hinzufügen möchten, klicken Sie auf **hinzu \> fügen** und dann auf **OK**.

7. Klicken Sie auf **Speichern**, um die Änderungen an der Rollengruppe zu speichern.

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

1. Wechseln Sie im Security & Compliance Center zu **Berechtigungen**.

2. Wählen Sie in der Liste die Rollengruppe aus, um die Mitglieder anzuzeigen.

3. Auf der rechten Seite in den Rollengruppen Details können Sie die Mitglieder der Rollengruppe anzeigen.

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Verwenden von PowerShell, um einem anderen Benutzer Zugriff auf das Security & Compliance Center zu gewähren

1. [Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Verwenden Sie den Befehl **Add-RoleGroupMember** , um einen Benutzer zur Rolle "Organisationsverwaltung" hinzuzufügen, wie im folgenden Beispiel dargestellt.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **Parameter**:

   - _Identity_ ist die Rollengruppe, der Sie ein Mitglied hinzufügen möchten.

   - _Mitglied_ ist das Postfach, die universelle Sicherheitsgruppe (Universal Security Group, USG) oder der Computer, der der Rollengruppe hinzugefügt werden soll. Sie können immer nur ein Element angeben.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember).

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Verwenden Sie das Cmdlet **Get-RoleGroupMember** , um die Mitglieder in der Rollengruppe "Organisationsverwaltung" anzuzeigen, um zu überprüfen, ob Sie Benutzern Zugriff auf das Security & Compliance Center gegeben haben, wie im folgenden Beispiel dargestellt.

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).
