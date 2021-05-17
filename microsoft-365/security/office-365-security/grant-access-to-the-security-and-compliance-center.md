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
ms.openlocfilehash: 7cd36ac0dec20851a423acd58e5ad7d38cb65d93
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599923"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="076f1-103">Freigeben des Benutzerzugriffs auf das Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="076f1-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="076f1-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="076f1-104">**Applies to**</span></span>
- [<span data-ttu-id="076f1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="076f1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="076f1-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="076f1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="076f1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="076f1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="076f1-108">Benutzern müssen berechtigungen im Security & Compliance Center zugewiesen werden, bevor sie sicherheits- oder compliancefeatures verwalten können.</span><span class="sxs-lookup"><span data-stu-id="076f1-108">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="076f1-109">Als globaler Administrator oder Mitglied der Rollengruppe OrganizationManagement im Security & Compliance Center können Sie benutzern diese Berechtigungen erteilen.</span><span class="sxs-lookup"><span data-stu-id="076f1-109">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="076f1-110">Benutzer können nur die Sicherheits- oder Compliancefeatures verwalten, auf die Sie zugriffen.</span><span class="sxs-lookup"><span data-stu-id="076f1-110">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="076f1-111">Weitere Informationen zu den verschiedenen Berechtigungen, die Sie Benutzern im Security & Compliance Center erteilen können, finden Sie unter Berechtigungen im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="076f1-111">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="076f1-112">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="076f1-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="076f1-113">Sie müssen ein globaler Administrator oder Mitglied der Rollengruppe OrganizationManagement im Security & Compliance Center sein, um die Schritte in diesem Artikel ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="076f1-113">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="076f1-114">Rollengruppen für das Security & Compliance Center haben möglicherweise ähnliche Namen wie die Rollengruppen in Exchange Online, aber sie sind nicht identisch.</span><span class="sxs-lookup"><span data-stu-id="076f1-114">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="076f1-115">Rollengruppenmitgliedschaften werden nicht zwischen Exchange Online und dem Security & Compliance Center freigegeben.</span><span class="sxs-lookup"><span data-stu-id="076f1-115">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="076f1-116">Partner mit delegierter Zugriffsberechtigung (Delegated Access Permission, DAP), die über „Administer On Behalf OF“(AOBO)-Berechtigungen verfügen, können nicht auf das Security & Compliance Center zugreifen.</span><span class="sxs-lookup"><span data-stu-id="076f1-116">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="076f1-117">Verwenden des Security & Compliance Center, um einem anderen Benutzer Zugriff auf das Security & Compliance Center zu geben</span><span class="sxs-lookup"><span data-stu-id="076f1-117">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="076f1-118">Öffnen Sie das Security & Compliance Center <https://protection.office.com> unter, und wechseln Sie dann zu **Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="076f1-118">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="076f1-119">Öffnen Sie , um direkt zur Registerkarte **Berechtigungen** zu <https://protection.office.com/permissions> wechseln.</span><span class="sxs-lookup"><span data-stu-id="076f1-119">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="076f1-120">Wählen Sie in der Liste der Rollengruppen die Rollengruppe aus, und klicken Sie dann auf **Bearbeiten** ![ (Symbol). ](../../media/O365-MDM-CreatePolicy-EditIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="076f1-120">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="076f1-121">Klicken Sie auf der Eigenschaftenseite der Rollengruppe unter **Mitglieder** auf Hinzufügensymbol, und wählen Sie den Namen des Benutzers (oder der Benutzer) aus, den ![ Sie hinzufügen ](../../media/ITPro-EAC-AddIcon.gif) möchten.</span><span class="sxs-lookup"><span data-stu-id="076f1-121">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="076f1-122">Wenn Sie alle Benutzer ausgewählt haben, die Sie der Rollengruppe hinzufügen möchten, klicken Sie **auf \> hinzufügen-** und dann **auf OK**.</span><span class="sxs-lookup"><span data-stu-id="076f1-122">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="076f1-123">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="076f1-123">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="076f1-124">Verwenden von Security & Compliance Center PowerShell, um einem anderen Benutzer Zugriff auf das Security & Compliance Center zu geben</span><span class="sxs-lookup"><span data-stu-id="076f1-124">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="076f1-125">[Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="076f1-125">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="076f1-126">Verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="076f1-126">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="076f1-127">Ausführliche Syntax- und Parameterprobleme finden Sie unter [Add-RoleGroupMember.](/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="076f1-127">For detailed syntax and parameter issues, see [Add-RoleGroupMember](/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="076f1-128">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="076f1-128">How do you know this worked?</span></span>

<span data-ttu-id="076f1-129">Gehen Sie wie folgt vor, um zu überprüfen, ob Sie erfolgreich Zugriff auf das Security & Compliance Center gewährt haben:</span><span class="sxs-lookup"><span data-stu-id="076f1-129">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="076f1-130">Wechseln Sie im Security & Compliance Center zu **Berechtigungen,** und wählen Sie die Rollengruppe aus.</span><span class="sxs-lookup"><span data-stu-id="076f1-130">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="076f1-131">Überprüfen Sie im geöffneten Detailf flyout die Mitglieder der Rollengruppe.</span><span class="sxs-lookup"><span data-stu-id="076f1-131">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="076f1-132">Ersetzen & In Security & Compliance Center PowerShell durch den Namen der \<RoleGroupName\> Rollengruppe, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="076f1-132">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="076f1-133">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="076f1-133">For detailed syntax and parameter information, see [Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember).</span></span>