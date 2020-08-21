---
title: Verwalten von Rollengruppen in EoP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Administratoren können erfahren, wie Sie Berechtigungen in der Exchange-Verwaltungskonsole (EAC) in Exchange Online Protection zuweisen oder entfernen.
ms.openlocfilehash: 8d452eb85d59bbe82cc6685d652617bc857c1ddf
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825689"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="9a561-103">Verwalten von Rollengruppen in EOP als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="9a561-103">Manage role groups in standalone EOP</span></span>

<span data-ttu-id="9a561-104">In Organisationen mit eigenständigen Exchange Online Schutz (EoP) ohne Exchange Online Postfächer können Sie die Exchange-Verwaltungskonsole verwenden, um Benutzer zu Rollengruppen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9a561-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="9a561-105">Durch das Hinzufügen von Benutzern zu einer Rollengruppe erhalten die Benutzerberechtigungen für bestimmte Administratoraufgaben.</span><span class="sxs-lookup"><span data-stu-id="9a561-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="9a561-106">Sie können Benutzer auch aus Rollengruppen entfernen.</span><span class="sxs-lookup"><span data-stu-id="9a561-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="9a561-107">Weitere Informationen zu Rollen und Rollengruppen finden Sie unter [Permissions in Standalone EoP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="9a561-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9a561-108">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="9a561-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9a561-109">Informationen zum Öffnen des Exchange Admin Center (EAC) finden Sie unter [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="9a561-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="9a561-110">Informationen zum Öffnen eigenständiger EoP PowerShell finden Sie unter [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9a561-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9a561-111">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="9a561-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="9a561-112">Insbesondere benötigen Sie die Rolle "Rollenverwaltung", die standardmäßig der Rollengruppe Mitglied (globale Administratoren) zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="9a561-112">Specifically, you need the Role Management role, which is assigned to the OrganizationManagement (global admins) role group by default.</span></span> <span data-ttu-id="9a561-113">Weitere Informationen finden Sie unter [Berechtigungen in eigenständigen EoP](feature-permissions-in-eop.md) und [Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="9a561-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="9a561-114">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="9a561-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="9a561-115">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="9a561-115">Having problems?</span></span> <span data-ttu-id="9a561-116">Bitten Sie im [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)-Forum um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="9a561-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="9a561-117">Verwalten von Rollengruppen mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="9a561-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="9a561-118">Anzeigen von Rollengruppen mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="9a561-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="9a561-119">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**.</span><span class="sxs-lookup"><span data-stu-id="9a561-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="9a561-120">Alle Rollengruppen in Ihrer Organisation werden hier aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="9a561-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="9a561-121">Wählen Sie eine Rollengruppe aus.</span><span class="sxs-lookup"><span data-stu-id="9a561-121">Select a role group.</span></span> <span data-ttu-id="9a561-122">Im Detailbereich werden der **Name**, die **Beschreibung**, die **zugewiesenen Rollen**und die von der Rollengruppe **verwaltete** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9a561-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="9a561-123">Sie können diese Informationen auch anzeigen, indem Sie auf Bearbeitungssymbol **Bearbeiten** klicken ![ ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9a561-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="9a561-124">Erstellen von Rollengruppen mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="9a561-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="9a561-125">Wenn Sie eine neue Rollengruppe erstellen, können Sie alle Einstellungen selbst konfigurieren (während der Erstellung der Gruppe oder danach).</span><span class="sxs-lookup"><span data-stu-id="9a561-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="9a561-126">Sie können auch eine vorhandene Rollengruppe kopieren und ändern.</span><span class="sxs-lookup"><span data-stu-id="9a561-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="9a561-127">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**, und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9a561-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="9a561-128">**Manuelles Erstellen einer neuen Rollengruppe**: Klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9a561-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="9a561-129">**Kopieren einer vorhandenen Rollengruppe**: Wählen Sie die Rollengruppe aus, die Sie kopieren möchten, und klicken Sie **dann auf Kopie kopieren (** ![ Symbol ](../../media/ITPro-EAC-CopyIcon.png) ).</span><span class="sxs-lookup"><span data-stu-id="9a561-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="9a561-130">Konfigurieren Sie im Fenster **neue Rollengruppe** , das angezeigt wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="9a561-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="9a561-131">**Name**: Geben Sie einen eindeutigen Namen für die Rollengruppe ein.</span><span class="sxs-lookup"><span data-stu-id="9a561-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="9a561-132">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Rollengruppe ein.</span><span class="sxs-lookup"><span data-stu-id="9a561-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="9a561-133">**Rollen**: Klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) oderITPro-EAC-RemoveIcon.gif**Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) , um die Rollen auszuwählen oder zu ändern, die der Rollengruppe zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="9a561-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="9a561-134">**Mitglieder**: Klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) oderITPro-EAC-RemoveIcon.gif**Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) , um die Rollengruppenmitgliedschaft zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9a561-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="9a561-135">Wenn Sie fertig sind, klicken Sie auf **Speichern** , um die Rollengruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9a561-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="9a561-136">Ändern von Rollengruppen mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="9a561-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="9a561-137">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**, wählen Sie die Rollengruppe aus, die Sie ändern möchten, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9a561-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="9a561-138">Dieselben Optionen stehen zur Verfügung, wenn Sie Rollengruppen wie beim Erstellen von Rollengruppen ändern.</span><span class="sxs-lookup"><span data-stu-id="9a561-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="9a561-139">Sie können:</span><span class="sxs-lookup"><span data-stu-id="9a561-139">You can:</span></span>

- <span data-ttu-id="9a561-140">Ändern Sie den Namen und die Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="9a561-140">Change the name and description.</span></span>

- <span data-ttu-id="9a561-141">Hinzufügen und Entfernen von Verwaltungsrollen (Rollenzuweisungen erstellen oder entfernen).</span><span class="sxs-lookup"><span data-stu-id="9a561-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="9a561-142">Hinzufügen und Entfernen von Mitgliedern.</span><span class="sxs-lookup"><span data-stu-id="9a561-142">Add and remove members.</span></span>

<span data-ttu-id="9a561-143">**Hinweis**: einige Rollengruppen (beispielsweise Organisationsverwaltung) schränken die Rollen ein, die Sie aus der Gruppe entfernen können.</span><span class="sxs-lookup"><span data-stu-id="9a561-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="9a561-144">Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen</span><span class="sxs-lookup"><span data-stu-id="9a561-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="9a561-145">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**, wählen Sie die Rollengruppe aus, die Sie ändern möchten, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9a561-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="9a561-146">Führen Sie auf der Seite Eigenschaften der Rollengruppe, die geöffnet wird, im Abschnitt **Mitglieder** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9a561-146">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="9a561-147">Klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9a561-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="9a561-148">Suchen Sie auf der angezeigten Seite den Benutzer, den Wou hinzufügen möchten, und klicken Sie dann auf **Add->**.</span><span class="sxs-lookup"><span data-stu-id="9a561-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="9a561-149">Wählen Sie Benutzer aus, und klicken Sie nach Bedarf viele Male auf **Add->** .</span><span class="sxs-lookup"><span data-stu-id="9a561-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="9a561-150">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a561-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="9a561-151">Wählen Sie die Benutzer aus, die Sie entfernen möchten, und klicken Sie dann auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="9a561-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="9a561-152">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="9a561-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9a561-153">Nachdem Sie Mitglieder hinzugefügt oder aus der Rollengruppe entfernt haben, müssen sich die betroffenen Benutzer möglicherweise abmelden und dann erneut anmelden, um die Änderung ihrer Administratorrechten zu sehen.</span><span class="sxs-lookup"><span data-stu-id="9a561-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="9a561-154">Entfernen von Rollengruppen mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="9a561-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="9a561-155">Sie können keine integrierten Rollengruppen entfernen, aber Sie können benutzerdefinierte Rollengruppen entfernen, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="9a561-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="9a561-156">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**.</span><span class="sxs-lookup"><span data-stu-id="9a561-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="9a561-157">Wählen Sie die Rollengruppe aus, die Sie entfernen möchten, und klicken Sie **dann auf Delete** ![ Delete Icon ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9a561-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="9a561-158">Klicken Sie im Bestätigungsfenster, das angezeigt wird, auf **Ja** .</span><span class="sxs-lookup"><span data-stu-id="9a561-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="9a561-159">Verwenden von PowerShell zum Verwalten von Rollengruppen</span><span class="sxs-lookup"><span data-stu-id="9a561-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="9a561-160">Verwenden eigenständiger EoP PowerShell zum Anzeigen von Rollengruppen</span><span class="sxs-lookup"><span data-stu-id="9a561-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="9a561-161">Verwenden Sie die folgende Syntax, um eine Rollengruppe anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="9a561-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="9a561-162">In diesem Beispiel wird eine Zusammenfassungsliste aller Rollengruppen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9a561-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="9a561-163">In diesem Beispiel werden detaillierte Informationen für die Rollengruppe mit dem Namen "Recipient Administrators" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9a561-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="9a561-164">In diesem Beispiel werden alle Rollengruppen zurückgegeben, in denen der Benutzer Julia Mitglied ist.</span><span class="sxs-lookup"><span data-stu-id="9a561-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="9a561-165">Sie müssen den distinguishedName (DN)-Wert für Julia verwenden, den Sie finden können, indem Sie den folgenden Befehl ausführen: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="9a561-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="9a561-166">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="9a561-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="9a561-167">Verwenden eigenständiger EoP PowerShell zum Erstellen von Rollengruppen</span><span class="sxs-lookup"><span data-stu-id="9a561-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="9a561-168">Wenn Sie eine neue Rollengruppe erstellen, können Sie alle Einstellungen manuell konfigurieren (während der Erstellung der Gruppe oder nach).</span><span class="sxs-lookup"><span data-stu-id="9a561-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="9a561-169">Sie können auch eine vorhandene Rollengruppe kopieren und ändern.</span><span class="sxs-lookup"><span data-stu-id="9a561-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="9a561-170">Verwenden Sie die folgende Syntax, um eine neue Rollengruppe manuell zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="9a561-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="9a561-171">Der Parameter _roles_ gibt die Verwaltungsrollen an, die der Rollengruppe mithilfe der folgenden Syntax zugewiesen werden sollen `"Role1","Role1",..."RoleN"` .</span><span class="sxs-lookup"><span data-stu-id="9a561-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="9a561-172">Sie können die verfügbaren Rollen mit dem Cmdlet **Get-ManagementRole** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9a561-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="9a561-173">Der Parameter _Members_ gibt die Mitglieder der Rollengruppe mithilfe der folgenden Syntax an: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="9a561-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="9a561-174">Sie können Benutzer, Mail-aktivierte universelle Sicherheitsgruppen (USGs) oder andere Rollengruppen (Sicherheitsprinzipale) angeben.</span><span class="sxs-lookup"><span data-stu-id="9a561-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="9a561-175">In diesem Beispiel wird eine neue Rollengruppe mit dem Namen "Limited Recipient Management" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="9a561-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="9a561-176">Der Rollengruppe wird die Rolle "Mail Recipients" zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9a561-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="9a561-177">Die Benutzer Kim und Martin werden als Mitglieder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9a561-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="9a561-178">Führen Sie die folgenden Schritte aus, um eine vorhandene Rollengruppe zu kopieren:</span><span class="sxs-lookup"><span data-stu-id="9a561-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="9a561-179">Speichern Sie die Rollengruppe, die Sie kopieren wollen, mithilfe der folgenden Syntax in einer Variablen:</span><span class="sxs-lookup"><span data-stu-id="9a561-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="9a561-180">Erstellen Sie die neue Rollengruppe mit der folgenden Syntax:</span><span class="sxs-lookup"><span data-stu-id="9a561-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="9a561-181">Der Parameter _Members_ gibt die Mitglieder der Rollengruppe mithilfe der folgenden Syntax an: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="9a561-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="9a561-182">Sie können Benutzer, Mail-aktivierte universelle Sicherheitsgruppen (USGs) oder andere Rollengruppen (Sicherheitsprinzipale) angeben.</span><span class="sxs-lookup"><span data-stu-id="9a561-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="9a561-183">In diesem Beispiel wird die Rollengruppe "Organisationsverwaltung" in die neue Rollengruppe mit dem Namen "Limited Organization Management" kopiert.</span><span class="sxs-lookup"><span data-stu-id="9a561-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="9a561-184">Die Mitglieder der Rollengruppe sind Isabelle, Carter und Lukas.</span><span class="sxs-lookup"><span data-stu-id="9a561-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="9a561-185">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="9a561-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="9a561-186">Verwenden eigenständiger EoP PowerShell ändern der Liste der Mitglieder in Rollengruppen</span><span class="sxs-lookup"><span data-stu-id="9a561-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="9a561-187">Mit den Cmdlets **Add-RoleGroupMember** und **Remove-RoleGroupMember** werden einzelne Mitglieder einzeln hinzugefügt oder entfernt.</span><span class="sxs-lookup"><span data-stu-id="9a561-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="9a561-188">Das Cmdlet **Update-RoleGroupMember** kann die vorhandene Liste der Mitglieder ersetzen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="9a561-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="9a561-189">Die Mitglieder einer Rollengruppe können Benutzer, universelle Sicherheitsgruppen (Universal Security Groups, USGS) oder andere Rollengruppen (Sicherheitsprinzipale) sein.</span><span class="sxs-lookup"><span data-stu-id="9a561-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="9a561-190">Verwenden Sie die folgende Syntax, um die Mitglieder einer Rollengruppe zu ändern:</span><span class="sxs-lookup"><span data-stu-id="9a561-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="9a561-191">Verwenden Sie die folgende Syntax, um die vorhandene Liste der Elemente durch die angegebenen Werte zu _ersetzen_ : `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="9a561-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="9a561-192">Verwenden Sie die folgende Syntax, um die vorhandene Liste der Elemente _selektiv zu ändern_ : `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="9a561-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="9a561-193">In diesem Beispiel werden alle aktuellen Mitglieder der Help Desk-Rollengruppe durch die angegebenen Benutzer ersetzt.</span><span class="sxs-lookup"><span data-stu-id="9a561-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="9a561-194">In diesem Beispiel wird Daigoro Akai hinzugefügt und Valeria Barrio aus der Liste der Mitglieder der Rollengruppe "Helpdesk" entfernt.</span><span class="sxs-lookup"><span data-stu-id="9a561-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="9a561-195">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="9a561-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="9a561-196">Verwenden eigenständiger EoP PowerShell zum Entfernen von Rollengruppen</span><span class="sxs-lookup"><span data-stu-id="9a561-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="9a561-197">Sie können keine integrierten Rollengruppen entfernen, aber Sie können benutzerdefinierte Rollengruppen entfernen, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="9a561-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="9a561-198">Verwenden Sie die folgende Syntax, um eine benutzerdefinierte Rollengruppe zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="9a561-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="9a561-199">In diesem Beispiel wird die Rollengruppe "Schulungs Administratoren" entfernt.</span><span class="sxs-lookup"><span data-stu-id="9a561-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="9a561-200">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="9a561-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9a561-201">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="9a561-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="9a561-202">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie eine Rollengruppe erfolgreich kopiert haben:</span><span class="sxs-lookup"><span data-stu-id="9a561-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="9a561-203">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Berechtigungen** \> **Administratorrollen**, und überprüfen Sie, ob die Rollengruppe aufgeführt (oder nicht aufgeführt) ist.</span><span class="sxs-lookup"><span data-stu-id="9a561-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="9a561-204">Wählen Sie die Rollengruppe aus, und überprüfen Sie die Einstellungen im Detail **Edit** Bereich, oder klicken Sie auf ![ Bearbeitungssymbol bearbeiten ](../../media/ITPro-EAC-EditIcon.png) , um die Einstellungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9a561-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="9a561-205">Ersetzen Sie in Exchange Online PowerShell \<Role Group Name\> durch den Namen der Rollengruppe, und führen Sie den folgenden Befehl aus, um zu überprüfen, ob die Rollengruppe vorhanden ist (oder nicht vorhanden ist), und überprüfen Sie die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="9a561-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
