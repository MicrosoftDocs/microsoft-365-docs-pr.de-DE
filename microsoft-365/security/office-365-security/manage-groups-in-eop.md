---
title: Verwalten von Gruppen in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Administratoren in eigenständigen Exchange Online Schutzorganisationen können Informationen zum Erstellen, ändern und Entfernen von Verteilergruppen und e-Mail-aktivierten Sicherheitsgruppen in der Exchange-Verwaltungskonsole (EAC) und in der eigenständigen Exchange Online Protection (EoP) PowerShell EoP.
ms.openlocfilehash: fc3f3807216b269a9868e87c5ec784d75385f878
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209019"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="7cafe-103">Verwalten von Gruppen in EOP</span><span class="sxs-lookup"><span data-stu-id="7cafe-103">Manage groups in EOP</span></span>

<span data-ttu-id="7cafe-104">In Organisationen mit eigenständigen Exchange Online Schutz (EoP) ohne Exchange Online Postfächer können Sie die folgenden Gruppentypen erstellen, ändern und entfernen:</span><span class="sxs-lookup"><span data-stu-id="7cafe-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="7cafe-105">**Verteilergruppen**: eine Sammlung von e-Mail-Benutzern oder anderen Verteilergruppen.</span><span class="sxs-lookup"><span data-stu-id="7cafe-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="7cafe-106">Beispielsweise Teams oder andere Ad-hoc-Gruppen, die in einem gemeinsamen Interessenbereich e-Mails empfangen oder senden müssen.</span><span class="sxs-lookup"><span data-stu-id="7cafe-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="7cafe-107">Verteilergruppen dienen ausschließlich zum Verteilen von e-Mail-Nachrichten und sind keine Sicherheitsprinzipale (Ihnen können keine Berechtigungen zugewiesen werden).</span><span class="sxs-lookup"><span data-stu-id="7cafe-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="7cafe-108">**E-Mail-aktivierte Sicherheitsgruppen**: eine Sammlung von e-Mail-Benutzern und anderen Sicherheitsgruppen, die Zugriffsberechtigungen für Administratorrollen benötigen.</span><span class="sxs-lookup"><span data-stu-id="7cafe-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="7cafe-109">Beispielsweise können Sie bestimmten Gruppen von Benutzern Administratorberechtigungen erteilen, damit diese Einstellungen für Antispam-und Antischadsoftware konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="7cafe-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <ul><li><span data-ttu-id="7cafe-110">Standardmäßig lehnen neue e-Mail-aktivierte Sicherheitsgruppen Nachrichten von externen (nicht authentifizierten) Absendern ab.</span><span class="sxs-lookup"><span data-stu-id="7cafe-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span></li><li><span data-ttu-id="7cafe-111">Fügen Sie keine Verteilergruppen zu e-Mail-aktivierten Sicherheitsgruppen hinzu.</span><span class="sxs-lookup"><span data-stu-id="7cafe-111">Don't add distribution groups to mail-enabled security groups.</span></span></li></ul><span data-ttu-id="7cafe-112">.</span><span class="sxs-lookup"><span data-stu-id="7cafe-112">.</span></span>

<span data-ttu-id="7cafe-113">Sie können Gruppen in der Exchange-Verwaltungskonsole (EAC) und in der eigenständigen EoP PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="7cafe-113">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7cafe-114">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="7cafe-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7cafe-115">Informationen zum Öffnen des Exchange Admin Center finden Sie unter [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="7cafe-115">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="7cafe-116">Informationen zum Herstellen einer Verbindung mit einer eigenständigen EoP PowerShell finden Sie unter [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="7cafe-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7cafe-117">Wenn Sie Gruppen in eigenständigen EoP PowerShell verwalten, treten möglicherweise Einschränkungen auf.</span><span class="sxs-lookup"><span data-stu-id="7cafe-117">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="7cafe-118">In den PowerShell-Verfahren in diesem Thema wird eine Batch Verarbeitungsmethode verwendet, die zu einer Ausbreitungs Verzögerung von ein paar Minuten führt, bevor die Ergebnisse der Befehle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7cafe-118">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="7cafe-119">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="7cafe-119">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="7cafe-120">Insbesondere benötigen Sie die Rolle "Verteilergruppen", die standardmäßig den Rollengruppenmitglied (globale Administratoren) und RecipientManagement zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="7cafe-120">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="7cafe-121">Weitere Informationen finden Sie unter [Berechtigungen in eigenständigen EoP](feature-permissions-in-eop.md) und [Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="7cafe-121">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="7cafe-122">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="7cafe-122">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="7cafe-123">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="7cafe-123">Having problems?</span></span> <span data-ttu-id="7cafe-124">Fragen Sie im Forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) nach Hilfe.</span><span class="sxs-lookup"><span data-stu-id="7cafe-124">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="7cafe-125">Verwalten von Verteilergruppen mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="7cafe-125">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="7cafe-126">Erstellen von Gruppen mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="7cafe-126">Use the EAC to create groups</span></span>

1. <span data-ttu-id="7cafe-127">Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="7cafe-127">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="7cafe-128">Klicken Sie auf **Neues** ![ Neues Symbol ](../../media/ITPro-EAC-AddIcon.png) , und wählen Sie dann eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="7cafe-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="7cafe-129">**Verteilergruppe**</span><span class="sxs-lookup"><span data-stu-id="7cafe-129">**Distribution group**</span></span>

   - <span data-ttu-id="7cafe-130">**E-Mail-aktivierte Sicherheitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="7cafe-130">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="7cafe-131">Konfigurieren Sie auf der Seite neue Gruppe, die geöffnet wird, die folgenden Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="7cafe-131">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="7cafe-132">Mit einem markierte Einstellungen <sup>\*</sup> sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7cafe-132">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="7cafe-133"><sup>\*</sup>**Anzeigename**: dieser Name wird im Adressbuch Ihrer Organisation, in der an:-Adresse angezeigt, wenn e-Mail an diese Gruppe gesendet wird, und in der Liste **Gruppen** in der Exchange-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="7cafe-133"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="7cafe-134">Der Anzeigename ist erforderlich, muss eindeutig sein und sollte benutzerfreundlich sein, damit Personen erkennen, was er ist.</span><span class="sxs-lookup"><span data-stu-id="7cafe-134">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="7cafe-135"><sup>\*</sup>**Alias**: Geben Sie in diesem Feld den Namen des Alias für die Gruppe ein.</span><span class="sxs-lookup"><span data-stu-id="7cafe-135"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="7cafe-136">Der Alias darf 64 Zeichen nicht überschreiten und muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="7cafe-136">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="7cafe-137">Wenn ein Benutzer den Alias in der an-Codezeile einer e-Mail-Nachricht eingibt, wird er in den Anzeigenamen der Gruppe aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="7cafe-137">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="7cafe-138"><sup>\*</sup>**E-Mail-Adresse**: die e-Mail-Adresse besteht aus dem Alias links neben dem @-Symbol und einer Domäne auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="7cafe-138"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="7cafe-139">Standardmäßig wird der Wert von **Alias** für den Alias Wert verwendet, aber Sie können ihn ändern.</span><span class="sxs-lookup"><span data-stu-id="7cafe-139">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="7cafe-140">Klicken Sie für den Wert Domäne auf die Dropdownliste und dann auf die Domäne auswählen und akzeptieren in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="7cafe-140">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="7cafe-141">**Beschreibung**: Diese Beschreibung wird im Adressbuch und im Detailbereich der Exchange-Verwaltungskonsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7cafe-141">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="7cafe-142"><sup>\*</sup>**Besitzer**: ein Gruppenbesitzer kann Gruppenmitgliedschaften verwalten.</span><span class="sxs-lookup"><span data-stu-id="7cafe-142"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="7cafe-143">Standardmäßig ist die Person, die eine Gruppe erstellt, deren Besitzer.</span><span class="sxs-lookup"><span data-stu-id="7cafe-143">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="7cafe-144">Jede Gruppe muss mindestens einen Besitzer aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7cafe-144">All groups must have at least one owner.</span></span>

     <span data-ttu-id="7cafe-145">Klicken Sie zum Hinzufügen von Besitzern auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="7cafe-145">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="7cafe-146">Suchen Sie im angezeigten Dialogfeld einen Empfänger oder eine Gruppe, und wählen Sie ihn aus, und klicken Sie dann auf **Add->**.</span><span class="sxs-lookup"><span data-stu-id="7cafe-146">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="7cafe-147">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="7cafe-147">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="7cafe-148">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7cafe-148">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="7cafe-149">Wenn Sie einen Besitzer entfernen möchten, wählen Sie den Besitzer aus, und klicken Sie dann auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="7cafe-149">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="7cafe-150">**Mitglieder**: Gruppenmitglieder hinzufügen und entfernen.</span><span class="sxs-lookup"><span data-stu-id="7cafe-150">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="7cafe-151">Klicken Sie zum Hinzufügen von Mitgliedern auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="7cafe-151">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="7cafe-152">Suchen Sie im angezeigten Dialogfeld einen Empfänger oder eine Gruppe, und wählen Sie ihn aus, und klicken Sie dann auf **Add->**.</span><span class="sxs-lookup"><span data-stu-id="7cafe-152">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="7cafe-153">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="7cafe-153">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="7cafe-154">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7cafe-154">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="7cafe-155">Wenn Sie ein Mitglied entfernen möchten, wählen Sie das Mitglied aus, und klicken Sie dann auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="7cafe-155">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="7cafe-156">Wenn Sie fertig sind, klicken Sie auf **Speichern** , um die Verteilergruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7cafe-156">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="7cafe-157">Ändern von Verteilergruppen mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="7cafe-157">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="7cafe-158">Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="7cafe-158">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="7cafe-159">Wählen Sie in der Liste der Gruppen die Verteilergruppe oder die e-Mail-aktivierte Sicherheitsgruppe aus, die Sie ändern möchten, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="7cafe-159">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="7cafe-160">Klicken Sie auf der Seite Eigenschaften der Verteilergruppe, die geöffnet wird, auf eine der folgenden Registerkarten, um Eigenschaften anzuzeigen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7cafe-160">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="7cafe-161">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7cafe-161">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="7cafe-162">Allgemein</span><span class="sxs-lookup"><span data-stu-id="7cafe-162">General</span></span>

<span data-ttu-id="7cafe-163">Verwenden Sie diese Registerkarte, um grundlegende Informationen zur Gruppe anzuzeigen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7cafe-163">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="7cafe-164">**Anzeigename**: dieser Name wird im Adressbuch, in der an-Adresse angezeigt, wenn e-Mail-Nachrichten an diese Gruppe gesendet werden, und in der **Liste Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="7cafe-164">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="7cafe-165">Der Anzeigename ist erforderlich und sollte benutzerfreundlich sein, damit Personen erkennen, was es ist.</span><span class="sxs-lookup"><span data-stu-id="7cafe-165">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="7cafe-166">Es muss auch in Ihrer Domäne eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="7cafe-166">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="7cafe-167">Wenn Sie eine Gruppenbenennungsrichtlinie implementiert haben, muss der Anzeigename dem von der Richtlinie definierten Namensformat entsprechen.</span><span class="sxs-lookup"><span data-stu-id="7cafe-167">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="7cafe-168">**Alias**: Dies ist der Teil der e-Mail-Adresse, der Links neben dem @-Symbol angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7cafe-168">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="7cafe-169">Wenn Sie den Alias ändern, wird die primäre SMTP-Adresse für die Gruppe ebenfalls geändert, die dann den neuen Alias enthält.</span><span class="sxs-lookup"><span data-stu-id="7cafe-169">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="7cafe-170">Zusätzlich bleibt die E-Mail-Adresse mit dem vorherigen Alias als Proxyadresse für die Gruppe erhalten.</span><span class="sxs-lookup"><span data-stu-id="7cafe-170">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="7cafe-171">**E-Mail-Adresse**: die e-Mail-Adresse besteht aus dem Alias links neben dem @-Symbol und einer Domäne auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="7cafe-171">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="7cafe-172">Standardmäßig wird der Wert von **Alias** für den Alias Wert verwendet, aber Sie können ihn ändern.</span><span class="sxs-lookup"><span data-stu-id="7cafe-172">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="7cafe-173">Klicken Sie für den Wert Domäne auf die Dropdownliste und dann auf die Domäne auswählen und akzeptieren in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="7cafe-173">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="7cafe-174">**Beschreibung**: Diese Beschreibung wird im Adressbuch und im Detailbereich der Exchange-Verwaltungskonsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7cafe-174">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="7cafe-175">Besitz</span><span class="sxs-lookup"><span data-stu-id="7cafe-175">Ownership</span></span>

<span data-ttu-id="7cafe-176">Verwenden Sie diese Registerkarte, um Gruppenbesitzer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="7cafe-176">Use this tab to assign group owners.</span></span> <span data-ttu-id="7cafe-177">Ein Gruppenbesitzer kann Gruppenmitgliedschaften verwalten.</span><span class="sxs-lookup"><span data-stu-id="7cafe-177">A group owner can manage group membership.</span></span> <span data-ttu-id="7cafe-178">Standardmäßig ist die Person, die eine Gruppe erstellt, deren Besitzer.</span><span class="sxs-lookup"><span data-stu-id="7cafe-178">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="7cafe-179">Jede Gruppe muss mindestens einen Besitzer aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7cafe-179">All groups must have at least one owner.</span></span>

<span data-ttu-id="7cafe-180">Klicken Sie zum Hinzufügen von Besitzern auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="7cafe-180">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="7cafe-181">Suchen und wählen Sie im daraufhin angezeigten Dialogfeld einen Empfänger aus, und klicken Sie dann auf **Add->**.</span><span class="sxs-lookup"><span data-stu-id="7cafe-181">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="7cafe-182">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="7cafe-182">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="7cafe-183">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7cafe-183">When you're finished, click **OK**.</span></span>

<span data-ttu-id="7cafe-184">Wenn Sie einen Besitzer entfernen möchten, wählen Sie den Besitzer aus, und klicken Sie dann auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="7cafe-184">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="7cafe-185">Mitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="7cafe-185">Membership</span></span>

<span data-ttu-id="7cafe-186">Verwenden Sie diese Registerkarte, um Gruppenmitglieder hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="7cafe-186">Use this tab to add or remove group members.</span></span> <span data-ttu-id="7cafe-187">Gruppenbesitzer müssen nicht Mitglieder der Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="7cafe-187">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="7cafe-188">Klicken Sie zum Hinzufügen von Mitgliedern auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="7cafe-188">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="7cafe-189">Suchen Sie im angezeigten Dialogfeld einen Empfänger oder eine Gruppe, und wählen Sie ihn aus, und klicken Sie dann auf **Add->**.</span><span class="sxs-lookup"><span data-stu-id="7cafe-189">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="7cafe-190">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="7cafe-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="7cafe-191">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7cafe-191">When you're finished, click **OK**.</span></span>

<span data-ttu-id="7cafe-192">Wenn Sie ein Mitglied entfernen möchten, wählen Sie das Mitglied aus, und klicken Sie dann auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="7cafe-192">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="7cafe-193">Entfernen von Gruppen mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="7cafe-193">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="7cafe-194">Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="7cafe-194">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="7cafe-195">Wählen Sie in der Liste der Gruppen die Verteilergruppe aus, die Sie entfernen möchten, und klicken Sie dann auf entfernen Symbol **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="7cafe-195">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="7cafe-196">Verwenden von PowerShell zum Verwalten von Gruppen</span><span class="sxs-lookup"><span data-stu-id="7cafe-196">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="7cafe-197">Verwenden eigenständiger EoP PowerShell zum Anzeigen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="7cafe-197">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="7cafe-198">Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller Verteilergruppen und e-Mail-aktivierten Sicherheitsgruppen in eigenständiger EoP PowerShell zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="7cafe-198">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="7cafe-199">Um die Liste der Gruppenmitglieder zurückzugeben, ersetzen Sie \< GroupIdentity \> durch den Namen, den Alias oder die e-Mail-Adresse der Gruppe, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7cafe-199">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="7cafe-200">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) und [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="7cafe-200">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="7cafe-201">Verwenden eigenständiger EoP PowerShell zum Erstellen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="7cafe-201">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="7cafe-202">Verwenden Sie die folgende Syntax, um Verteilergruppen oder e-Mail-aktivierte Sicherheitsgruppen in eigenständigen EoP PowerShell zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7cafe-202">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="7cafe-203">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="7cafe-203">**Notes**:</span></span>

- <span data-ttu-id="7cafe-204">Der _Name_ -Parameter ist erforderlich, hat eine maximale Länge von 64 Zeichen und muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="7cafe-204">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="7cafe-205">Wenn Sie den _DisplayName_-Parameter nicht verwenden, wird der Wert des _Name_-Parameters für den Anzeigenamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="7cafe-205">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="7cafe-206">Wenn Sie den Parameter _Alias_ nicht verwenden, wird der _Name_ -Parameter für den Alias-Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="7cafe-206">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="7cafe-207">Leerzeichen werden entfernt, und nicht unterstützte Zeichen werden in Fragezeichen (?) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7cafe-207">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="7cafe-208">Wenn Sie den Parameter _PrimarySmtpAddress_ nicht verwenden, wird der Alias Wert im Parameter _PrimarySmtpAddress_ verwendet.</span><span class="sxs-lookup"><span data-stu-id="7cafe-208">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="7cafe-209">Wenn Sie den Parameter _Type_ nicht verwenden, lautet der Standardwert Distribution.</span><span class="sxs-lookup"><span data-stu-id="7cafe-209">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="7cafe-210">In diesem Beispiel wird eine Verteilergruppe mit dem Namen "IT Administrators" mit den angegebenen Eigenschaften erstellt.</span><span class="sxs-lookup"><span data-stu-id="7cafe-210">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="7cafe-211">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup).</span><span class="sxs-lookup"><span data-stu-id="7cafe-211">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="7cafe-212">Verwenden eigenständiger EoP PowerShell zum Ändern von Gruppen</span><span class="sxs-lookup"><span data-stu-id="7cafe-212">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="7cafe-213">Verwenden Sie die folgende Syntax, um Gruppen in eigenständigen EoP PowerShell zu ändern:</span><span class="sxs-lookup"><span data-stu-id="7cafe-213">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="7cafe-214">In diesem Beispiel wird die primäre SMTP-Adresse (auch als Antwortadresse bezeichnet) für die Gruppe "Seattle Employees" in Sea.Employees@contoso.com verwendet.</span><span class="sxs-lookup"><span data-stu-id="7cafe-214">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="7cafe-215">In diesem Beispiel werden die aktuellen Mitglieder der Sicherheits Team Gruppe durch Kitty Petersen und Tyson Fawcett ersetzt.</span><span class="sxs-lookup"><span data-stu-id="7cafe-215">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="7cafe-216">In diesem Beispiel wird der Gruppe "Security Team" ein neuer Benutzernamens "Tyson Fawcett" hinzugefügt, während die aktuellen Mitglieder der Gruppe beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="7cafe-216">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="7cafe-217">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup) und [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="7cafe-217">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="7cafe-218">Entfernen einer Gruppe mithilfe von Remote Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7cafe-218">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="7cafe-219">In diesem Beispiel wird die Verteilergruppe "IT-Administratoren" entfernt.</span><span class="sxs-lookup"><span data-stu-id="7cafe-219">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="7cafe-220">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="7cafe-220">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="7cafe-221">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="7cafe-221">How do you know these procedures worked?</span></span>

<span data-ttu-id="7cafe-222">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie eine Verteilergruppe oder eine e-Mail-aktivierte Sicherheitsgruppe erfolgreich erstellt, geändert oder entfernt haben:</span><span class="sxs-lookup"><span data-stu-id="7cafe-222">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="7cafe-223">Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="7cafe-223">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="7cafe-224">Stellen Sie sicher, dass die Gruppe aufgeführt (oder nicht aufgeführt) ist, und überprüfen Sie den Wert des **Gruppentyps** .</span><span class="sxs-lookup"><span data-stu-id="7cafe-224">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="7cafe-225">Wählen Sie die Gruppe aus, und zeigen Sie die Informationen im Detailbereich an, oder klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-AddIcon.png) , um die Einstellungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7cafe-225">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="7cafe-226">Führen Sie in eigenständiger EoP-PowerShell den folgenden Befehl aus, um zu überprüfen, ob die Gruppe aufgeführt (oder nicht aufgeführt) ist:</span><span class="sxs-lookup"><span data-stu-id="7cafe-226">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="7cafe-227">Ersetzen \< \> Sie GroupIdentity durch den Namen, den Alias oder die e-Mail-Adresse der Gruppe, und führen Sie den folgenden Befehl aus, um die Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="7cafe-227">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="7cafe-228">Um die Gruppenmitglieder anzuzeigen, ersetzen Sie \< GroupIdentity \> durch den Namen, den Alias oder die e-Mail-Adresse der Gruppe, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7cafe-228">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
