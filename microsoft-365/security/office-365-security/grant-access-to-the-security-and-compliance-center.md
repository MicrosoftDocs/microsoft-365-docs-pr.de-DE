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
ms.openlocfilehash: 1bf8da85a0e090a9d74934ea5084f547d6a8794f
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616608"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Freigeben des Benutzerzugriffs auf das Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Benutzer müssen im Security & Compliance Center Berechtigungen zugewiesen werden, bevor Sie alle Sicherheits-und Kompatibilitätsfeatures verwalten können. Als globaler Administrator oder Mitglied der Mitglied-Rollengruppe im Security & Compliance Center können Sie diese Berechtigungen Benutzern erteilen. Benutzer können nur die Sicherheits-oder Kompatibilitätsfeatures verwalten, auf die Sie Zugriff haben.

Weitere Informationen zu den verschiedenen Berechtigungen, die Sie Benutzern im Security & Compliance Center erteilen können, finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie müssen ein globaler Administrator oder ein Mitglied der Rollengruppe Mitglied im Security & Compliance Center sein, um die Schritte in diesem Artikel ausführen zu können.

- Rollengruppen für das Security & Compliance Center haben möglicherweise ähnliche Namen wie die Rollengruppen in Exchange Online, sind aber nicht identisch.

- Rollengruppenmitgliedschaften werden nicht zwischen Exchange Online und dem Security & Compliance Center freigegeben.

- Partner mit delegierter Zugriffsberechtigung (Delegated Access Permission, DAP), die über „Administer On Behalf OF“(AOBO)-Berechtigungen verfügen, können nicht auf das Security & Compliance Center zugreifen.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Verwenden Sie das Security & Compliance Center, um einem anderen Benutzer Zugriff auf das Security & Compliance Center zu gewähren.

1. Öffnen Sie das Security & Compliance Center unter, <https://protection.office.com> und wechseln Sie dann zu **Berechtigungen**. Wenn Sie direkt zur Registerkarte **Berechtigungen** wechseln möchten, öffnen Sie <https://protection.office.com/permissions> .

2. Wählen Sie in der Liste der Rollengruppen die Rollengruppe aus, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

3. Klicken Sie auf der Eigenschaftenseite der Rollengruppe unter **Mitglieder** auf Add-Symbol **Hinzufügen**, ![ ](../../media/ITPro-EAC-AddIcon.gif) und wählen Sie den Namen des Benutzers (oder der Benutzer) aus, den Sie hinzufügen möchten.

4. Wenn Sie alle Benutzer ausgewählt haben, die Sie der Rollengruppe hinzufügen möchten, klicken Sie auf **hinzu \> fügen** und dann auf **OK**.

5. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Verwenden Sie Security & Compliance Center PowerShell, um einem anderen Benutzer Zugriff auf das Security & Compliance Center zu gewähren.

1. [Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Verwenden Sie die folgende Syntax:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie erfolgreich Zugriff auf das Compliance Center für Sicherheits & erhalten haben:

- Wechseln Sie im Security & Compliance Center zu **Berechtigungen** , und wählen Sie die Rollengruppe aus. Überprüfen Sie im Detail Flyout, das geöffnet wird, die Mitglieder der Rollengruppe.

- Ersetzen Sie in Security & Compliance Center PowerShell \<RoleGroupName\> durch den Namen der Rollengruppe, und führen Sie den folgenden Befehl aus:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).
