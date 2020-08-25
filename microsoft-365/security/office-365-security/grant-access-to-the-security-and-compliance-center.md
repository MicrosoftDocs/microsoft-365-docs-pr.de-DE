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
ms.openlocfilehash: b51007221257b9adac46c31295e13b20b12342ab
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868921"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="83196-103">Freigeben des Benutzerzugriffs auf das Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="83196-103">Give users access to the Security & Compliance Center</span></span>

<span data-ttu-id="83196-104">Benutzer müssen im Security & Compliance Center Berechtigungen zugewiesen werden, bevor Sie alle Sicherheits-und Kompatibilitätsfeatures verwalten können.</span><span class="sxs-lookup"><span data-stu-id="83196-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="83196-105">Als globaler Administrator oder Mitglied der Mitglied-Rollengruppe im Security & Compliance Center können Sie diese Berechtigungen Benutzern erteilen.</span><span class="sxs-lookup"><span data-stu-id="83196-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="83196-106">Benutzer können nur die Sicherheits-oder Kompatibilitätsfeatures verwalten, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="83196-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="83196-107">Weitere Informationen zu den verschiedenen Berechtigungen, die Sie Benutzern im Security & Compliance Center erteilen können, finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="83196-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="83196-108">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="83196-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="83196-109">Sie müssen ein globaler Administrator oder ein Mitglied der Rollengruppe Mitglied im Security & Compliance Center sein, um die Schritte in diesem Artikel ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="83196-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="83196-110">Rollengruppen für das Security & Compliance Center haben möglicherweise ähnliche Namen wie die Rollengruppen in Exchange Online, sind aber nicht identisch.</span><span class="sxs-lookup"><span data-stu-id="83196-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="83196-111">Rollengruppenmitgliedschaften werden nicht zwischen Exchange Online und dem Security & Compliance Center freigegeben.</span><span class="sxs-lookup"><span data-stu-id="83196-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="83196-112">Partner mit delegierter Zugriffsberechtigung (Delegated Access Permission, DAP), die über „Administer On Behalf OF“(AOBO)-Berechtigungen verfügen, können nicht auf das Security & Compliance Center zugreifen.</span><span class="sxs-lookup"><span data-stu-id="83196-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="83196-113">Verwenden Sie das Security & Compliance Center, um einem anderen Benutzer Zugriff auf das Security & Compliance Center zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="83196-113">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="83196-114">Öffnen Sie das Security & Compliance Center unter, <https://protection.office.com> und wechseln Sie dann zu **Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="83196-114">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="83196-115">Wenn Sie direkt zur Registerkarte **Berechtigungen** wechseln möchten, öffnen Sie <https://protection.office.com/permissions> .</span><span class="sxs-lookup"><span data-stu-id="83196-115">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="83196-116">Wählen Sie in der Liste der Rollengruppen die Rollengruppe aus, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="83196-116">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="83196-117">Klicken Sie auf der Eigenschaftenseite der Rollengruppe unter **Mitglieder**auf Add-Symbol **Hinzufügen**, ![ ](../../media/ITPro-EAC-AddIcon.gif) und wählen Sie den Namen des Benutzers (oder der Benutzer) aus, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="83196-117">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="83196-118">Wenn Sie alle Benutzer ausgewählt haben, die Sie der Rollengruppe hinzufügen möchten, klicken Sie auf **hinzu \> fügen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="83196-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="83196-119">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="83196-119">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="83196-120">Verwenden Sie Security & Compliance Center PowerShell, um einem anderen Benutzer Zugriff auf das Security & Compliance Center zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="83196-120">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="83196-121">[Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="83196-121">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="83196-122">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="83196-122">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="83196-123">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="83196-123">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="83196-124">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="83196-124">How do you know this worked?</span></span>

<span data-ttu-id="83196-125">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie erfolgreich Zugriff auf das Compliance Center für Sicherheits & erhalten haben:</span><span class="sxs-lookup"><span data-stu-id="83196-125">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="83196-126">Wechseln Sie im Security & Compliance Center zu **Berechtigungen** , und wählen Sie die Rollengruppe aus.</span><span class="sxs-lookup"><span data-stu-id="83196-126">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="83196-127">Überprüfen Sie im Detail Flyout, das geöffnet wird, die Mitglieder der Rollengruppe.</span><span class="sxs-lookup"><span data-stu-id="83196-127">In the details flyout that opens, verify the members of the role group.</span></span> 

- <span data-ttu-id="83196-128">Ersetzen Sie in Security & Compliance Center PowerShell \<RoleGroupName\> durch den Namen der Rollengruppe, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="83196-128">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="83196-129">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="83196-129">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
