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
description: Administratoren können erfahren, wie Sie Berechtigungen im Exchange Admin Center (EAC) in Exchange Online Protection zuweisen oder entfernen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b53023521f477b5e864424ec648ccf7e5b749d0c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166987"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="c9c68-103">Verwalten von Rollengruppen in EOP als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="c9c68-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c9c68-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="c9c68-104">**Applies to**</span></span>
-  [<span data-ttu-id="c9c68-105">Exchange Online Protection als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="c9c68-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="c9c68-106">In eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer können Sie das Exchange Admin Center (EAC) verwenden, um Benutzer zu Rollengruppen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c9c68-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="c9c68-107">Durch das Hinzufügen eines Benutzers zu einer Rollengruppe erhält der Benutzer Berechtigungen zum Ausführen bestimmter Administratoraufgaben.</span><span class="sxs-lookup"><span data-stu-id="c9c68-107">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="c9c68-108">Sie können auch Benutzer aus Rollengruppen entfernen.</span><span class="sxs-lookup"><span data-stu-id="c9c68-108">You can also remove users from role groups.</span></span>

<span data-ttu-id="c9c68-109">Weitere Informationen zu Rollen und Rollengruppen finden Sie unter ["Berechtigungen" in EOP als eigenständige Lösung.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="c9c68-109">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c9c68-110">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="c9c68-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c9c68-111">Informationen zum Öffnen des Exchange Admin Centers (EAC) finden Sie im [Exchange Admin Center in EOP als eigenständige Lösung.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="c9c68-111">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="c9c68-112">Informationen zum Öffnen der eigenständigen EOP PowerShell finden Sie unter [Herstellen einer Verbindung mit Exchange Online Protection PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="c9c68-112">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c9c68-113">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online Protection die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="c9c68-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="c9c68-114">Insbesondere benötigen Sie die Rolle **"Rollenverwaltung",** die standardmäßig der **Rollengruppe** "Organisationsverwaltung" zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c9c68-114">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="c9c68-115">Weitere Informationen finden Sie unter "Berechtigungen [in EOP als eigenständige](feature-permissions-in-eop.md) Lösung", und ändern Sie mithilfe der EAC die Liste der Mitglieder in [Rollengruppen.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="c9c68-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="c9c68-116">Informationen zu Tastenkombinationen, die für die Verfahren in diesem Artikel gelten können, finden Sie unter Tastenkombinationen für das [Exchange Admin Center in Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="c9c68-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="c9c68-117">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="c9c68-117">Having problems?</span></span> <span data-ttu-id="c9c68-118">Bitten Sie im [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)-Forum um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="c9c68-118">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="c9c68-119">Verwalten von Rollengruppen mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="c9c68-119">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="c9c68-120">Anzeigen von Rollengruppen mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="c9c68-120">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="c9c68-121">Wechseln Sie in der EAC **zu** Administratorrollen \> **"Berechtigungen".**</span><span class="sxs-lookup"><span data-stu-id="c9c68-121">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="c9c68-122">Alle Rollengruppen in Ihrer Organisation werden hier aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c9c68-122">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="c9c68-123">Wählen Sie eine Rollengruppe aus.</span><span class="sxs-lookup"><span data-stu-id="c9c68-123">Select a role group.</span></span> <span data-ttu-id="c9c68-124">Im Detailbereich werden **der Name,** **die Beschreibung** **,** die zugewiesenen Rollen und **verwaltet von** der Rollengruppe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c9c68-124">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="c9c68-125">Sie können diese Informationen auch  anzeigen, indem Sie auf das Symbol ![ "Bearbeiten" ](../../media/ITPro-EAC-EditIcon.png) klicken.</span><span class="sxs-lookup"><span data-stu-id="c9c68-125">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="c9c68-126">Erstellen von Rollengruppen mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="c9c68-126">Use the EAC to create role groups</span></span>

<span data-ttu-id="c9c68-127">Wenn Sie eine neue Rollengruppe erstellen, können Sie alle Einstellungen selbst konfigurieren (während der Erstellung der Gruppe oder danach).</span><span class="sxs-lookup"><span data-stu-id="c9c68-127">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="c9c68-128">Sie können auch eine vorhandene Rollengruppe kopieren und ändern.</span><span class="sxs-lookup"><span data-stu-id="c9c68-128">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="c9c68-129">Wechseln Sie in der EAC zu **Administratorrollen** "Berechtigungen", und gehen Sie dann \> wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="c9c68-129">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="c9c68-130">**Manuelles Erstellen einer neuen Rollengruppe:** Klicken Sie **auf das Symbol "Hinzufügen".** ![ ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="c9c68-130">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="c9c68-131">**Kopieren Sie eine vorhandene Rollengruppe:** Wählen Sie die Rollengruppe aus, die Sie kopieren möchten, und klicken Sie dann auf **das** Symbol ![ "Kopieren". ](../../media/ITPro-EAC-CopyIcon.png)</span><span class="sxs-lookup"><span data-stu-id="c9c68-131">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="c9c68-132">Konfigurieren Sie **im angezeigten** Fenster "Neue Rollengruppe" die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="c9c68-132">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="c9c68-133">**Name**: Geben Sie einen eindeutigen Namen für die Rollengruppe ein.</span><span class="sxs-lookup"><span data-stu-id="c9c68-133">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="c9c68-134">**Beschreibung:** Geben Sie eine optionale Beschreibung für die Rollengruppe ein.</span><span class="sxs-lookup"><span data-stu-id="c9c68-134">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="c9c68-135">**Rollen:** **Klicken** Sie auf das Symbol "Hinzufügen" oder "Entfernen", um die Rollen auszuwählen oder zu ändern, die ![ ](../../media/ITPro-EAC-AddIcon.png) der  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Rollengruppe zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="c9c68-135">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="c9c68-136">**Mitglieder**: Klicken Sie auf das **Symbol** ![ "Hinzufügen" ](../../media/ITPro-EAC-AddIcon.png) oder  ![ "Entfernen", ](../../media/ITPro-EAC-RemoveIcon.gif) um die Rollengruppenmitgliedschaft zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c9c68-136">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="c9c68-137">Wenn Sie fertig sind, klicken Sie auf **"Speichern",** um die Rollengruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c9c68-137">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="c9c68-138">Ändern von Rollengruppen mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="c9c68-138">Use the EAC to modify role groups</span></span>

<span data-ttu-id="c9c68-139">Wechseln Sie in der EAC zu **Administratorrollen** für Berechtigungen, wählen Sie die Rollengruppe aus, die Sie ändern möchten, und klicken Sie dann auf das Symbol \>   ![ "Bearbeiten". ](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="c9c68-139">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="c9c68-140">Beim Ändern von Rollengruppen stehen dieselben Optionen zur Verfügung wie beim Erstellen von Rollengruppen.</span><span class="sxs-lookup"><span data-stu-id="c9c68-140">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="c9c68-141">Sie können:</span><span class="sxs-lookup"><span data-stu-id="c9c68-141">You can:</span></span>

- <span data-ttu-id="c9c68-142">Ändern Sie den Namen und die Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="c9c68-142">Change the name and description.</span></span>

- <span data-ttu-id="c9c68-143">Hinzufügen und Entfernen von Verwaltungsrollen (Erstellen oder Entfernen von Rollenzuweisungen).</span><span class="sxs-lookup"><span data-stu-id="c9c68-143">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="c9c68-144">Mitglieder hinzufügen und entfernen.</span><span class="sxs-lookup"><span data-stu-id="c9c68-144">Add and remove members.</span></span>

<span data-ttu-id="c9c68-145">**Hinweis:** Einige Rollengruppen (z. B. Organisationsverwaltung) schränken die Rollen ein, die Sie aus der Gruppe entfernen können.</span><span class="sxs-lookup"><span data-stu-id="c9c68-145">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="c9c68-146">Ändern der Mitgliederliste in Rollengruppen mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="c9c68-146">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="c9c68-147">Wechseln Sie in der EAC zu **Administratorrollen** für Berechtigungen, wählen Sie die Rollengruppe aus, die Sie ändern möchten, und klicken Sie dann auf das Symbol \>   ![ ](../../media/ITPro-EAC-EditIcon.png) "Bearbeiten".</span><span class="sxs-lookup"><span data-stu-id="c9c68-147">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="c9c68-148">Gehen Sie auf der Seite mit  den Rollengruppeneigenschaften, die geöffnet wird, im Abschnitt "Mitglieder" einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c9c68-148">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="c9c68-149">Klicken Sie **auf "Hinzufügen"** ![ (Symbol) ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="c9c68-149">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="c9c68-150">Suchen Sie auf der angezeigten Seite den Benutzer, den Sie hinzufügen möchten, und klicken Sie dann auf **"Add->".**</span><span class="sxs-lookup"><span data-stu-id="c9c68-150">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="c9c68-151">Wählen Sie Benutzer aus, und klicken Sie **bei >** auf "Add->".</span><span class="sxs-lookup"><span data-stu-id="c9c68-151">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="c9c68-152">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9c68-152">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="c9c68-153">Wählen Sie die Benutzer aus, die  Sie entfernen möchten, und klicken Sie dann auf ![ "Entfernen". ](../../media/ITPro-EAC-RemoveIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="c9c68-153">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="c9c68-154">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c9c68-154">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c9c68-155">Nachdem Sie Mitglieder hinzugefügt oder aus der Rollengruppe entfernt haben, müssen sich die betroffenen Benutzer möglicherweise abmelden und dann erneut anmelden, um die Änderung ihrer Administratorrechten zu sehen.</span><span class="sxs-lookup"><span data-stu-id="c9c68-155">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="c9c68-156">Entfernen von Rollengruppen mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="c9c68-156">Use the EAC to remove role groups</span></span>

<span data-ttu-id="c9c68-157">Sie können keine integrierten Rollengruppen entfernen, aber sie können benutzerdefinierte Rollengruppen entfernen, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="c9c68-157">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="c9c68-158">Wechseln Sie in der EAC **zu** Administratorrollen \> **"Berechtigungen".**</span><span class="sxs-lookup"><span data-stu-id="c9c68-158">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="c9c68-159">Wählen Sie die Rollengruppe aus, die Sie entfernen möchten, und klicken Sie dann auf **das** Symbol ![ "Löschen". ](../../media/ITPro-EAC-DeleteIcon.png)</span><span class="sxs-lookup"><span data-stu-id="c9c68-159">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="c9c68-160">Klicken **Sie im** angezeigten Bestätigungsfenster auf "Ja".</span><span class="sxs-lookup"><span data-stu-id="c9c68-160">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="c9c68-161">Verwenden von PowerShell zum Verwalten von Rollengruppen</span><span class="sxs-lookup"><span data-stu-id="c9c68-161">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="c9c68-162">Verwenden der eigenständigen EOP PowerShell zum Anzeigen von Rollengruppen</span><span class="sxs-lookup"><span data-stu-id="c9c68-162">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="c9c68-163">Verwenden Sie die folgende Syntax, um eine Rollengruppe anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="c9c68-163">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="c9c68-164">In diesem Beispiel wird eine Übersichtsliste aller Rollengruppen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c9c68-164">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="c9c68-165">In diesem Beispiel werden detaillierte Informationen für die Rollengruppe "Recipient Administrators" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c9c68-165">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="c9c68-166">In diesem Beispiel werden alle Rollengruppen zurückgegeben, bei denen die Benutzerin Julia Mitglied ist.</span><span class="sxs-lookup"><span data-stu-id="c9c68-166">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="c9c68-167">Sie müssen den DistinguishedName (DN)-Wert für Julia verwenden, den Sie finden, indem Sie den folgenden Befehl ausführen: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="c9c68-167">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="c9c68-168">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="c9c68-168">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="c9c68-169">Verwenden der eigenständigen EOP PowerShell zum Erstellen von Rollengruppen</span><span class="sxs-lookup"><span data-stu-id="c9c68-169">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="c9c68-170">Wenn Sie eine neue Rollengruppe erstellen, können Sie alle Einstellungen manuell konfigurieren (während der Erstellung der Gruppe oder danach).</span><span class="sxs-lookup"><span data-stu-id="c9c68-170">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="c9c68-171">Sie können auch eine vorhandene Rollengruppe kopieren und ändern.</span><span class="sxs-lookup"><span data-stu-id="c9c68-171">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="c9c68-172">Verwenden Sie die folgende Syntax, um eine neue Rollengruppe manuell zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="c9c68-172">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="c9c68-173">Der _Parameter "Roles"_ gibt die Verwaltungsrollen an, die der Rollengruppe mithilfe der folgenden Syntax zugewiesen `"Role1","Role1",..."RoleN"` werden.</span><span class="sxs-lookup"><span data-stu-id="c9c68-173">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="c9c68-174">Sie können die verfügbaren Rollen mit dem Cmdlet **Get-ManagementRole** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c9c68-174">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="c9c68-175">Der _Parameter "Members"_ gibt die Mitglieder der Rollengruppe mithilfe der folgenden Syntax `"Member1","Member2",..."MemberN"` an:</span><span class="sxs-lookup"><span data-stu-id="c9c68-175">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="c9c68-176">Sie können Benutzer, Mail-aktivierte universelle Sicherheitsgruppen (USGs) oder andere Rollengruppen (Sicherheitsprinzipale) angeben.</span><span class="sxs-lookup"><span data-stu-id="c9c68-176">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="c9c68-177">In diesem Beispiel wird eine neue Rollengruppe namens "Limited Recipient Management" mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="c9c68-177">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="c9c68-178">Der Rollengruppe wird die Rolle "Mail Recipients" zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c9c68-178">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="c9c68-179">Die Benutzer Kim und Martin werden als Mitglieder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c9c68-179">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="c9c68-180">Gehen Sie wie folgt vor, um eine vorhandene Rollengruppe zu kopieren:</span><span class="sxs-lookup"><span data-stu-id="c9c68-180">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="c9c68-181">Speichern Sie die Rollengruppe, die Sie kopieren wollen, mithilfe der folgenden Syntax in einer Variablen:</span><span class="sxs-lookup"><span data-stu-id="c9c68-181">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="c9c68-182">Erstellen Sie die neue Rollengruppe mithilfe der folgenden Syntax:</span><span class="sxs-lookup"><span data-stu-id="c9c68-182">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="c9c68-183">Der _Parameter "Members"_ gibt die Mitglieder der Rollengruppe mithilfe der folgenden Syntax `"Member1","Member2",..."MemberN"` an:</span><span class="sxs-lookup"><span data-stu-id="c9c68-183">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="c9c68-184">Sie können Benutzer, Mail-aktivierte universelle Sicherheitsgruppen (USGs) oder andere Rollengruppen (Sicherheitsprinzipale) angeben.</span><span class="sxs-lookup"><span data-stu-id="c9c68-184">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="c9c68-185">In diesem Beispiel wird die Rollengruppe "Organization Management" in die neue Rollengruppe "Limited Organization Management" kopiert.</span><span class="sxs-lookup"><span data-stu-id="c9c68-185">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="c9c68-186">Die Rollengruppenmitglieder sind Isabelle, Carter undAbel.</span><span class="sxs-lookup"><span data-stu-id="c9c68-186">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="c9c68-187">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="c9c68-187">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="c9c68-188">Verwenden der eigenständigen EOP PowerShell zum Ändern der Mitgliederliste in Rollengruppen</span><span class="sxs-lookup"><span data-stu-id="c9c68-188">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="c9c68-189">Mit **den Cmdlets "Add-RoleGroupMember"** und **"Remove-RoleGroupMember"** werden einzelne Mitglieder einzeln hinzugefügt oder entfernt.</span><span class="sxs-lookup"><span data-stu-id="c9c68-189">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="c9c68-190">Das **Cmdlet "Update-RoleGroupMember"** kann die vorhandene Mitgliederliste ersetzen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="c9c68-190">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="c9c68-191">Die Mitglieder einer Rollengruppe können Benutzer, E-Mail-aktivierte universelle Sicherheitsgruppen (Universal Security Groups, USGs) oder andere Rollengruppen (Sicherheitsprinzipale) sein.</span><span class="sxs-lookup"><span data-stu-id="c9c68-191">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="c9c68-192">Verwenden Sie die folgende Syntax, um die Mitglieder einer Rollengruppe zu ändern:</span><span class="sxs-lookup"><span data-stu-id="c9c68-192">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="c9c68-193">Verwenden _Sie die_ folgende Syntax, um die vorhandene Mitgliederliste durch die angegebenen Werte zu ersetzen: `"Member1","Member2",..."MemberN"`</span><span class="sxs-lookup"><span data-stu-id="c9c68-193">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="c9c68-194">Verwenden _Sie die folgende_ Syntax, um die vorhandene Mitgliederliste selektiv zu ändern: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`</span><span class="sxs-lookup"><span data-stu-id="c9c68-194">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="c9c68-195">In diesem Beispiel werden alle aktuellen Mitglieder der Rollengruppe "Help Desk" durch die angegebenen Benutzer ersetzt.</span><span class="sxs-lookup"><span data-stu-id="c9c68-195">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="c9c68-196">In diesem Beispiel wird Daigoro Akai hinzugefügt und Valeria Barrio aus der Mitgliederliste der Rollengruppe "Help Desk" entfernt.</span><span class="sxs-lookup"><span data-stu-id="c9c68-196">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="c9c68-197">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="c9c68-197">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="c9c68-198">Verwenden der eigenständigen EOP PowerShell zum Entfernen von Rollengruppen</span><span class="sxs-lookup"><span data-stu-id="c9c68-198">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="c9c68-199">Sie können keine integrierten Rollengruppen entfernen, aber sie können benutzerdefinierte Rollengruppen entfernen, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="c9c68-199">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="c9c68-200">Verwenden Sie die folgende Syntax, um eine benutzerdefinierte Rollengruppe zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="c9c68-200">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="c9c68-201">In diesem Beispiel wird die Rollengruppe "Training Administrators" entfernt.</span><span class="sxs-lookup"><span data-stu-id="c9c68-201">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="c9c68-202">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="c9c68-202">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c9c68-203">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="c9c68-203">How do you know these procedures worked?</span></span>

<span data-ttu-id="c9c68-204">Gehen Sie wie folgt vor, um sicherzustellen, dass Sie eine Rollengruppe erfolgreich kopiert haben:</span><span class="sxs-lookup"><span data-stu-id="c9c68-204">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="c9c68-205">Wechseln Sie in der EAC zu **Administratorrollen** "Berechtigungen", und stellen Sie sicher, dass die Rollengruppe aufgeführt \> (oder nicht aufgeführt) ist.</span><span class="sxs-lookup"><span data-stu-id="c9c68-205">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="c9c68-206">Wählen Sie die Rollengruppe aus, und überprüfen  Sie die Einstellungen im Detailbereich, oder klicken Sie auf das ![ Bearbeitungssymbol, ](../../media/ITPro-EAC-EditIcon.png) um die Einstellungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c9c68-206">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="c9c68-207">Ersetzen Sie in Exchange Online PowerShell den Namen der Rollengruppe, und führen Sie den folgenden Befehl aus, um zu überprüfen, ob die Rollengruppe vorhanden (oder nicht vorhanden) ist, und überprüfen Sie die \<Role Group Name\> Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="c9c68-207">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
