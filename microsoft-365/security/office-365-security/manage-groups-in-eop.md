---
title: Verwalten von Gruppen in EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: Sie können Exchange Online Protection (EOP) zur Erstellung E-Mail-aktivierter Gruppen für eine Exchange-Organisation verwenden. Sie können EOP auch verwenden, um Gruppeneigenschaften zu definieren oder zu aktualisieren, über die Mitgliedschaften, E-Mail-Adressen und andere Aspekte von Gruppen festgelegt werden.
ms.openlocfilehash: 06813daae3270df61b9aa5aaf67ef322e14a623b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082523"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="c76e5-104">Verwalten von Gruppen in EOP</span><span class="sxs-lookup"><span data-stu-id="c76e5-104">Manage groups in EOP</span></span>

 <span data-ttu-id="c76e5-p102">Sie können Exchange Online Protection (EOP) zur Erstellung E-Mail-aktivierter Gruppen für eine Exchange-Organisation verwenden. Sie können EOP auch verwenden, um Gruppeneigenschaften zu definieren oder zu aktualisieren, über die Mitgliedschaften, E-Mail-Adressen und andere Aspekte von Gruppen festgelegt werden. Sie können je nach Bedarf Verteiler- oder Sicherheitsgruppen anlegen. Diese Gruppen können mithilfe des Exchange Admin Center (EAC) oder über Windows Remote-PowerShell erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c76e5-p102">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization. You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups. You can create distribution groups and security groups, depending on your needs. These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span>
  
## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="c76e5-109">Arten von E-Mail-aktivierten Gruppen</span><span class="sxs-lookup"><span data-stu-id="c76e5-109">Types of mail-enabled groups</span></span>

<span data-ttu-id="c76e5-110">Sie können für Ihre Exchange-Organisation zwei Arten von Gruppen erstellen:</span><span class="sxs-lookup"><span data-stu-id="c76e5-110">You can create two types of groups for your Exchange organization:</span></span>
  
- <span data-ttu-id="c76e5-111">Verteilergruppen sind Sammlungen von e-Mail-Benutzern, beispielsweise ein Team oder eine andere Ad-hoc-Gruppe, die e-Mails zu einem gemeinsamen Interessenbereich empfangen oder senden müssen.</span><span class="sxs-lookup"><span data-stu-id="c76e5-111">Distribution groups are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest.</span></span> <span data-ttu-id="c76e5-112">Verteilergruppen sind exklusiv für die Verteilung von E-Mail-Nachrichten vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="c76e5-112">Distribution groups are exclusively for distributing email messages.</span></span> <span data-ttu-id="c76e5-113">In EOP wird mit dem Begriff "Verteilergruppe" jede E-Mail-aktivierte Gruppe bezeichnet, egal, ob sie sich in einem Sicherheitskontext befindet oder nicht.</span><span class="sxs-lookup"><span data-stu-id="c76e5-113">In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>

- <span data-ttu-id="c76e5-114">Sicherheitsgruppen sind Sammlungen von e-Mail-Benutzern, die Zugriffsberechtigungen für Administratorrollen benötigen.</span><span class="sxs-lookup"><span data-stu-id="c76e5-114">Security groups are collections of email users who need access permissions for Admin roles.</span></span> <span data-ttu-id="c76e5-115">Sie könnten z. B. bestimmten Gruppen von Benutzern Berechtigungen für Administratorrollen gewähren, sodass diese Benutzer dann Anti-Span- und Anti-Malware-Einstellungen konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="c76e5-115">For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c76e5-p105">Standardmäßig ist für alle neuen E-Mail-aktivierten Sicherheitsgruppen die Authentifizierung aller Absender erforderlich. Auf diese Weise wird verhindert, dass externe Absender Nachrichten an E-Mail-aktivierte Sicherheitsgruppen senden können.</span><span class="sxs-lookup"><span data-stu-id="c76e5-p105">By default, all new mail-enabled security groups require that all senders be authenticated. This prevents external senders from sending messages to mail-enabled security groups.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="c76e5-118">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="c76e5-118">Before you begin</span></span>

- <span data-ttu-id="c76e5-p106">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter Eintrag "Verteilergruppen und Sicherheitsgruppen" im Thema [Featureberechtigungen in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="c76e5-p106">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="c76e5-121">Informationen zum Öffnen des Exchange Admin Center finden Sie unter [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="c76e5-121">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="c76e5-122">Beachten Sie, dass beim Erstellen und Verwalten von Gruppen mithilfe von Exchange Online Protection PowerShell-Cmdlets möglicherweise Einschränkungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="c76e5-122">Be aware that when creating and managing groups by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="c76e5-123">In den PowerShell-Verfahren in diesem Thema wird eine Batch Verarbeitungsmethode verwendet, die zu einer Ausbreitungs Verzögerung von ein paar Minuten führt, bevor die Ergebnisse der Befehle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c76e5-123">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="c76e5-124">Wie Sie mit Windows PowerShell eine Verbindung mit Exchange Online Protection herstellen, können Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) nachlesen.</span><span class="sxs-lookup"><span data-stu-id="c76e5-124">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>

- <span data-ttu-id="c76e5-125">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="c76e5-125">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="c76e5-126">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="c76e5-126">Having problems?</span></span> <span data-ttu-id="c76e5-127">Fragen Sie im Forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) nach Hilfe.</span><span class="sxs-lookup"><span data-stu-id="c76e5-127">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span> 
  
## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="c76e5-128">Erstellen einer Gruppe im EAC</span><span class="sxs-lookup"><span data-stu-id="c76e5-128">Create a group in the EAC</span></span>

1. <span data-ttu-id="c76e5-129">Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="c76e5-129">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="c76e5-130">Klicken \*\*\*\* ![Sie auf neues](../media/ITPro-EAC-AddIcon.gif)Symbol hinzufügen, und klicken Sie dann je nach Ihren Anforderungen auf **Verteilergruppe** oder **Sicherheitsgruppe**.</span><span class="sxs-lookup"><span data-stu-id="c76e5-130">Click **New** ![Add Icon](../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span>

3. <span data-ttu-id="c76e5-131">Konfigurieren Sie auf der Seite **neue Verteilergruppe** oder **neue Sicherheitsgruppe** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="c76e5-131">On the **New distribution group** or **New security group** page, configure the following settings:</span></span>

   - <span data-ttu-id="c76e5-132">**Anzeigename**: Geben Sie einen Anzeigenamen ein, der für Ihre Organisation eindeutig ist und für EoP-Benutzer sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="c76e5-132">**Display name**: Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="c76e5-133">Der Anzeigename ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c76e5-133">The display name is required.</span></span>

   - <span data-ttu-id="c76e5-134">**Alias**: Geben Sie einen Gruppen Alias mit bis zu 64 Zeichen ein, der für Ihre Organisation eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="c76e5-134">**Alias**: Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="c76e5-135">Wenn ein EOP-Benutzer diesen Alias in die Zeile An: einer E-Mail eingibt, wird er in den Anzeigenamen der Gruppe aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="c76e5-135">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="c76e5-136">Wenn Sie den Alias ändern, wird die primäre SMTP-Adresse für die Gruppe ebenfalls geändert und enthält dann den neuen Alias.</span><span class="sxs-lookup"><span data-stu-id="c76e5-136">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="c76e5-137">Der Alias ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c76e5-137">The alias is required.</span></span> 

   - <span data-ttu-id="c76e5-138">**Beschreibung**: Geben Sie eine Beschreibung der Gruppe ein, damit Benutzer den Zweck der Gruppe kennen.</span><span class="sxs-lookup"><span data-stu-id="c76e5-138">**Description**: Type a description of the group so that people will know the purpose of the group.</span></span> 

   - <span data-ttu-id="c76e5-139">**Besitzer**: Standardmäßig ist die Person, die die Gruppe erstellt, der Besitzer.</span><span class="sxs-lookup"><span data-stu-id="c76e5-139">**Owners**: By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="c76e5-140">Sie können einen Besitzer hinzufügen, indem Sie hinzu](../media/ITPro-EAC-AddIcon.gif)fügen **Symbol hinzufügen auswählen.** ![</span><span class="sxs-lookup"><span data-stu-id="c76e5-140">You can add an owner by choosing **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="c76e5-141">Jede Gruppe muss mindestens einen Besitzer aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c76e5-141">All groups must have at least one owner.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c76e5-142">Besitzer von Gruppen müssen kein Mitglied der jeweiligen Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="c76e5-142">Owners don't have to be members of the group.</span></span>
  
   - <span data-ttu-id="c76e5-143">**Mitglieder**: in diesem Abschnitt können Sie Gruppenmitglieder hinzufügen und angeben, ob eine Genehmigung erforderlich ist, damit Personen der Gruppe beitreten oder diese verlassen können.</span><span class="sxs-lookup"><span data-stu-id="c76e5-143">**Members**: Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="c76e5-144">Um der Gruppe Mitglieder hinzuzufügen, klicken Sie auf Add](../media/ITPro-EAC-AddIcon.gif)-Symbol **Hinzufügen** ![.</span><span class="sxs-lookup"><span data-stu-id="c76e5-144">To add members to the group, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="c76e5-145">Klicken Sie auf **OK**, um zur Ursprungsseite zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="c76e5-145">Click **OK** to return to the original page.</span></span>

5. <span data-ttu-id="c76e5-p112">Wenn Sie fertig sind, klicken Sie auf **Speichern**, um die Gruppe zu erstellen. Die neue Gruppe sollte in der Liste der Gruppen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c76e5-p112">When you've finished, click **Save** to create the group. The new group should appear in the list of groups.</span></span>

## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="c76e5-148">Bearbeiten oder Entfernen einer Gruppe im EAC</span><span class="sxs-lookup"><span data-stu-id="c76e5-148">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="c76e5-149">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Empfänger** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="c76e5-149">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="c76e5-150">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c76e5-150">Do one of the following steps:</span></span>

   - <span data-ttu-id="c76e5-151">So bearbeiten Sie eine Gruppe: Klicken Sie in der Liste der Gruppen auf die Gruppe, die Sie anzeigen oder ändern möchten, und \*\*\*\* ![klicken Sie dann](../media/ITPro-EAC-EditIcon.gif)auf Bearbeitungssymbol bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c76e5-151">To edit a group: In the list of groups, click the group that you want to view or change, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="c76e5-152">Sie können allgemeine Einstellungen aktualisieren, Gruppenbesitzer hinzufügen oder entfernen sowie Gruppenmitglieder bei Bedarf hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="c76e5-152">You can update general settings, add or remove group owners, and add or remove group members as needed.</span></span>

   - <span data-ttu-id="c76e5-153">So entfernen Sie eine Gruppe: Wählen Sie die Gruppe \*\*\*\* ![aus, und](../media/ITPro-EAC-RemoveIcon.gif)klicken Sie auf entfernen-Symbol entfernen.</span><span class="sxs-lookup"><span data-stu-id="c76e5-153">To remove a group: Select the group and click **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="c76e5-154">Wenn Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c76e5-154">When you're finished making your changes, click **Save**.</span></span>

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="c76e5-155">Erstellen, Bearbeiten oder Entfernen einer Gruppe mithilfe von Windows Remote-PowerShell</span><span class="sxs-lookup"><span data-stu-id="c76e5-155">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="c76e5-156">Dieser Abschnitt enthält Informationen zum Erstellen von Gruppen und zum Ändern der Eigenschaften in Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c76e5-156">This section provides information about creating groups and changing their properties in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="c76e5-157">Es wird außerdem gezeigt, wie eine vorhandene Gruppe entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="c76e5-157">It also shows how to remove an existing group.</span></span>
  
### <a name="create-a-group-using-remote-windows-powershell"></a><span data-ttu-id="c76e5-158">Erstellen einer Gruppe mithilfe von Remote Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c76e5-158">Create a group using remote Windows PowerShell</span></span>
  
<span data-ttu-id="c76e5-p115">In diesem Beispiel wird das [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup)-Cmdlet verwendet, um eine Verteilergruppe mit dem Alias "itadmin" und dem Namen "IT Administrators" zu erstellen. Außerdem werden Benutzer als Mitglieder der Gruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c76e5-p115">This example uses the [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators. It also adds users as members of the group.</span></span>
  
```Powershell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

<span data-ttu-id="c76e5-161">**Hinweis**: Wenn Sie anstelle einer Verteilergruppe eine Sicherheitsgruppe erstellen möchten, verwenden Sie `Security` den Wert für den *Type* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="c76e5-161">**Note**: To create a security group instead of a distribution group, use the value `Security` for the *Type* parameter.</span></span>
  
<span data-ttu-id="c76e5-162">Um sicherzustellen, dass Sie die Gruppe IT-Administratoren erfolgreich erstellt haben, führen Sie den folgenden Befehl aus, um Informationen über die neue Gruppe anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="c76e5-162">To verify that you've successfully created the IT Administrators group, run the following command to display information about the new group:</span></span>
  
```Powershell
Get-Recipient "IT Administrators" | Format-List
```

<span data-ttu-id="c76e5-163">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span><span class="sxs-lookup"><span data-stu-id="c76e5-163">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span></span>

<span data-ttu-id="c76e5-164">Um eine Liste der Mitglieder in der Gruppe abzurufen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c76e5-164">To get a list of members in the group, run the following command:</span></span>
  
```Powershell
Get-DistributionGroupMember "IT Administrators"
```

<span data-ttu-id="c76e5-165">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="c76e5-165">For detailed syntax and parameter information, see [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

<span data-ttu-id="c76e5-166">Um eine vollständige Liste aller ihrer Gruppen zu erhalten, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c76e5-166">To get a full list of all your groups, run the following command:</span></span>
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a><span data-ttu-id="c76e5-167">Ändern der Eigenschaften einer Gruppe mithilfe von Remote Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c76e5-167">Change the properties of a group using remote Windows PowerShell</span></span>
  
<span data-ttu-id="c76e5-168">Ein Vorteil der Verwendung von PowerShell anstelle der Exchange-Verwaltungskonsole ist die Möglichkeit, Eigenschaften für mehrere Gruppen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c76e5-168">An advantage of using PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span>
  
<span data-ttu-id="c76e5-169">Im folgenden finden Sie einige Beispiele für die Verwendung von Exchange Online Protection PowerShell zum Ändern von Gruppeneigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c76e5-169">Here are some examples of using Exchange Online Protection PowerShell to change group properties.</span></span>
  
<span data-ttu-id="c76e5-170">In diesem Beispiel wird die primäre SMTP-Adresse (auch als Antwortadresse bezeichnet) für die Gruppe "Seattle Employees" in Sea.Employees@contoso.com verwendet.</span><span class="sxs-lookup"><span data-stu-id="c76e5-170">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>
  
```Powershell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="c76e5-171">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="c76e5-171">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span></span>

<span data-ttu-id="c76e5-172">Um zu überprüfen, ob Sie die Eigenschaften für die Gruppe erfolgreich geändert haben, führen Sie den folgenden Befehl aus, um den neuen Wert zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="c76e5-172">To verify that you've successfully changed the properties for the group, run the following command to verify the new value:</span></span>
  
```Powershell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

<span data-ttu-id="c76e5-173">In diesem Beispiel werden alle Mitglieder der Gruppe "Seattle Employees" aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c76e5-173">This example updates all the members of the Seattle Employees group.</span></span> <span data-ttu-id="c76e5-174">Verwenden Sie ein Komma, um alle Mitglieder voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="c76e5-174">Use a comma to separate all members.</span></span>
  
```Powershell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

<span data-ttu-id="c76e5-175">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Update-EOPDistributionGroupMember](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="c76e5-175">For detailed syntax and parameter information, see [Update-EOPDistributionGroupMember](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

<span data-ttu-id="c76e5-176">Um eine Liste aller Mitglieder in der Gruppe "Seattle Employees" abzurufen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c76e5-176">To get the list of all the members in the group Seattle Employees, run the following command:</span></span> 
  
```Powershell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="c76e5-177">Entfernen einer Gruppe mithilfe von Remote Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c76e5-177">Remove a group using remote Windows PowerShell</span></span>
  
<span data-ttu-id="c76e5-178">In diesem Beispiel wird die Verteilergruppe "IT-Administratoren" entfernt.</span><span class="sxs-lookup"><span data-stu-id="c76e5-178">This example uses removes the distribution group named IT Administrators.</span></span>
  
```Powershell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="c76e5-179">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="c76e5-179">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

<span data-ttu-id="c76e5-180">Um zu überprüfen, ob die Gruppe entfernt wurde, führen Sie den folgenden Befehl aus, und vergewissern Sie sich, dass die Gruppe (in diesem Fall "IT-Administratoren") gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="c76e5-180">To verify that the group was removed, run the following command, and confirm that the group (in this case "It Administrators") was deleted.</span></span>
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
