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
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Benutzern müssen berechtigungen im Microsoft 365 Security & Compliance Center zugewiesen werden, bevor sie ihre Sicherheits- oder Compliancefeatures verwalten können.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9e19825ce0f8224b2aee8e1419ef5d1ad425aadb
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165415"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Freigeben des Benutzerzugriffs auf das Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Benutzern müssen berechtigungen im Security & Compliance Center zugewiesen werden, bevor sie ihre Sicherheits- oder Compliancefeatures verwalten können. Als globaler Administrator oder Mitglied der Rollengruppe "OrganizationManagement" im Security & Compliance Center können Sie benutzern diese Berechtigungen erteilen. Benutzer können nur die Sicherheits- oder Compliancefeatures verwalten, auf die Sie ihnen Zugriff geben.

Weitere Informationen zu den verschiedenen Berechtigungen, die Sie Benutzern im Security & Compliance Center erteilen können, finden Sie im [Security & Compliance Center.](permissions-in-the-security-and-compliance-center.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie müssen ein globaler Administrator oder Mitglied der Rollengruppe "OrganizationManagement" im Security & Compliance Center sein, um die Schritte in diesem Artikel ausführen zu können.

- Rollengruppen für das Security & Compliance Center haben möglicherweise ähnliche Namen wie die Rollengruppen in Exchange Online, sind aber nicht identisch.

- Rollengruppenmitgliedschaften werden nicht zwischen Exchange Online und dem Security & Compliance Center gemeinsam genutzt.

- Partner mit delegierter Zugriffsberechtigung (Delegated Access Permission, DAP), die über „Administer On Behalf OF“(AOBO)-Berechtigungen verfügen, können nicht auf das Security & Compliance Center zugreifen.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Verwenden des Security & Compliance Center, um einem anderen Benutzer Zugriff auf das Security & Compliance Center zu geben

1. Öffnen Sie das Security & Compliance Center, und wechseln Sie <https://protection.office.com> dann zu **"Berechtigungen".** Um direkt zur Registerkarte **"Berechtigungen" zu** wechseln, öffnen Sie <https://protection.office.com/permissions> .

2. Wählen Sie in der Liste der Rollengruppen die Rollengruppe aus, und klicken Sie dann auf **das** ![ Bearbeitungssymbol. ](../../media/O365-MDM-CreatePolicy-EditIcon.gif)

3. Klicken Sie auf der Eigenschaftenseite der Rollengruppe unter "Mitglieder" auf "Hinzufügen", und wählen Sie den Namen des Benutzers (oder der Benutzer) **aus,** den ![ Sie hinzufügen ](../../media/ITPro-EAC-AddIcon.gif) möchten.

4. Wenn Sie alle Benutzer ausgewählt haben, die Sie der Rollengruppe hinzufügen möchten, klicken Sie auf **"Hinzufügen" \>** und dann auf **"OK".**

5. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Verwenden von Security & Compliance Center PowerShell, um einem anderen Benutzer Zugriff auf das Security & Compliance Center zu geben

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

Ausführliche Informationen zu Syntax- und Parameterproblemen finden Sie unter ["Add-RoleGroupMember".](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Gehen Sie wie folgt vor, um sicherzustellen, dass Sie den Zugriff auf das Security & Compliance Center erfolgreich erteilt haben:

- Wechseln Sie im Security & Compliance Center zu **"Berechtigungen",** und wählen Sie die Rollengruppe aus. Überprüfen Sie im geöffneten Detailf flyout die Mitglieder der Rollengruppe.

- Ersetzen Sie & Security & Compliance Center PowerShell durch den Namen der Rollengruppe, und führen \<RoleGroupName\> Sie den folgenden Befehl aus:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).
