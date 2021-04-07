---
title: Verwalten von Gruppen in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Administratoren in eigenständigen Exchange Online Protection (EOP)-Organisationen können erfahren, wie Sie Verteilergruppen und E-Mail-aktivierte Sicherheitsgruppen im Exchange Admin Center (EAC) und in der eigenständigen Exchange Online Protection (EOP) PowerShell erstellen, ändern und entfernen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b9d83f2fb59ee8f8d2d3035045ed438d5ba45851
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599569"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="87757-103">Verwalten von Gruppen in EOP</span><span class="sxs-lookup"><span data-stu-id="87757-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="87757-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="87757-104">**Applies to**</span></span>
-  [<span data-ttu-id="87757-105">Exchange Online Protection eigenständig</span><span class="sxs-lookup"><span data-stu-id="87757-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="87757-106">In eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer können Sie die folgenden Gruppentypen erstellen, ändern und entfernen:</span><span class="sxs-lookup"><span data-stu-id="87757-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="87757-107">**Verteilergruppen:** Eine Sammlung von E-Mail-Benutzern oder anderen Verteilergruppen.</span><span class="sxs-lookup"><span data-stu-id="87757-107">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="87757-108">Beispielsweise Teams oder andere Ad-hoc-Gruppen, die E-Mails in einem europäischen Bereich empfangen oder senden müssen.</span><span class="sxs-lookup"><span data-stu-id="87757-108">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="87757-109">Verteilergruppen dienen ausschließlich der Verteilung von E-Mail-Nachrichten und sind keine Sicherheitsprinzipale (ihnen können keine Berechtigungen zugewiesen werden).</span><span class="sxs-lookup"><span data-stu-id="87757-109">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="87757-110">**E-Mail-aktivierte Sicherheitsgruppen:** Eine Sammlung von E-Mail-Benutzern und anderen Sicherheitsgruppen, die Zugriffsberechtigungen für Administratorrollen benötigen.</span><span class="sxs-lookup"><span data-stu-id="87757-110">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="87757-111">Beispielsweise möchten Sie bestimmten Benutzergruppen Administratorberechtigungen erteilen, damit sie Antispam- und Anti-Malware-Einstellungen konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="87757-111">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="87757-112">Standardmäßig weisen neue E-Mail-aktivierte Sicherheitsgruppen Nachrichten von externen (nicht authentifizierten) Absendern zurück.</span><span class="sxs-lookup"><span data-stu-id="87757-112">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="87757-113">Fügen Sie keine Verteilergruppen zu E-Mail-aktivierten Sicherheitsgruppen hinzu.</span><span class="sxs-lookup"><span data-stu-id="87757-113">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="87757-114">Sie können Gruppen im Exchange Admin Center (EAC) und in der eigenständigen EOP PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="87757-114">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="87757-115">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="87757-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="87757-116">Informationen zum Öffnen des Exchange Admin Centers finden Sie unter [Exchange Admin Center im eigenständigen EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="87757-116">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="87757-117">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="87757-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="87757-118">Wenn Sie Gruppen in eigenständigen EOP PowerShell verwalten, kann es zu Drosselungsaktionen führen.</span><span class="sxs-lookup"><span data-stu-id="87757-118">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="87757-119">Die PowerShell-Verfahren in diesem Artikel verwenden eine Batchverarbeitungsmethode, die zu einer Übertragungsverzögerung von einigen Minuten führt, bevor die Ergebnisse der Befehle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="87757-119">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="87757-120">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online Protection die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="87757-120">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="87757-121">Insbesondere benötigen Sie die **Rolle Verteilergruppen,** die standardmäßig  den Rollengruppen **Organisationsverwaltung** und Empfängerverwaltung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="87757-121">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="87757-122">Weitere Informationen finden Sie unter [Permissions in standalone EOP](feature-permissions-in-eop.md) und [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="87757-122">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="87757-123">Informationen zu Tastenkombinationen, die für die Verfahren in diesem Artikel gelten können, finden Sie unter [Tastenkombinationen für](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)das Exchange Admin Center in Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="87757-123">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="87757-124">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="87757-124">Having problems?</span></span> <span data-ttu-id="87757-125">Bitten Sie im [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)-Forum um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="87757-125">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="87757-126">Verwalten von Verteilergruppen mithilfe des Exchange Admin Centers</span><span class="sxs-lookup"><span data-stu-id="87757-126">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="87757-127">Erstellen von Gruppen mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="87757-127">Use the EAC to create groups</span></span>

1. <span data-ttu-id="87757-128">Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="87757-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="87757-129">Klicken **Sie auf Neues** Symbol , und wählen Sie dann eine der folgenden Optionen ![ ](../../media/ITPro-EAC-AddIcon.png) aus:</span><span class="sxs-lookup"><span data-stu-id="87757-129">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="87757-130">**Verteilergruppe**</span><span class="sxs-lookup"><span data-stu-id="87757-130">**Distribution group**</span></span>

   - <span data-ttu-id="87757-131">**E-Mail-aktivierte Sicherheitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="87757-131">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="87757-132">Konfigurieren Sie auf der neuen Gruppenseite, die geöffnet wird, die folgenden Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="87757-132">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="87757-133">Mit einem gekennzeichnete <sup>\*</sup> Einstellungen sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="87757-133">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="87757-134"><sup>\*</sup>**Anzeigename**: Dieser Name wird im Adressbuch Ihrer Organisation, in der Zeile An: angezeigt, wenn E-Mails an diese Gruppe gesendet werden, und in der Liste Gruppen in der EAC. </span><span class="sxs-lookup"><span data-stu-id="87757-134"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="87757-135">Der Anzeigename ist erforderlich, muss eindeutig sein und benutzerfreundlich sein, damit die Benutzer erkennen, was er ist.</span><span class="sxs-lookup"><span data-stu-id="87757-135">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="87757-136"><sup>\*</sup>**Alias**: Geben Sie in diesem Feld den Namen des Alias für die Gruppe ein.</span><span class="sxs-lookup"><span data-stu-id="87757-136"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="87757-137">Der Alias darf 64 Zeichen nicht überschreiten und muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="87757-137">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="87757-138">Wenn ein Benutzer den Alias in die Zeile An einer E-Mail-Nachricht einräumt, wird er in den Anzeigenamen der Gruppe aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="87757-138">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="87757-139"><sup>\*</sup>**E-Mail-Adresse:** Die E-Mail-Adresse besteht aus dem Alias auf der linken Seite des @-Symbols und einer Domäne auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="87757-139"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="87757-140">Standardmäßig wird der Wert **von Alias** für den Aliaswert verwendet, Sie können ihn jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="87757-140">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="87757-141">Klicken Sie für den Domänenwert auf die Dropdownliste, und wählen Sie eine akzeptierte Domäne in Ihrer Organisation aus.</span><span class="sxs-lookup"><span data-stu-id="87757-141">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="87757-142">**Beschreibung**: Diese Beschreibung wird im Adressbuch und im Detailbereich in der EAC angezeigt.</span><span class="sxs-lookup"><span data-stu-id="87757-142">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="87757-143"><sup>\*</sup>**Besitzer:** Ein Gruppenbesitzer kann die Gruppenmitgliedschaft verwalten.</span><span class="sxs-lookup"><span data-stu-id="87757-143"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="87757-144">Standardmäßig ist die Person, die eine Gruppe erstellt, deren Besitzer.</span><span class="sxs-lookup"><span data-stu-id="87757-144">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="87757-145">Jede Gruppe muss mindestens einen Besitzer aufweisen.</span><span class="sxs-lookup"><span data-stu-id="87757-145">All groups must have at least one owner.</span></span>

     <span data-ttu-id="87757-146">Klicken Sie zum Hinzufügen von Besitzern **auf Hinzufügen** ![ -Symbol ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="87757-146">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="87757-147">Suchen Und wählen Sie im angezeigten Dialogfeld einen Empfänger oder eine Gruppe aus, und klicken Sie dann **auf Hinzufügen ->**.</span><span class="sxs-lookup"><span data-stu-id="87757-147">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="87757-148">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="87757-148">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="87757-149">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="87757-149">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="87757-150">Wählen Sie zum Entfernen eines Besitzers den Besitzer aus, und klicken Sie dann **auf Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) (Symbol) entfernen.</span><span class="sxs-lookup"><span data-stu-id="87757-150">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="87757-151">**Mitglieder**: Hinzufügen und Entfernen von Gruppenmitgliedern.</span><span class="sxs-lookup"><span data-stu-id="87757-151">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="87757-152">Klicken Sie zum Hinzufügen von Mitgliedern auf **Hinzufügen** ![ -Symbol ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="87757-152">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="87757-153">Suchen Und wählen Sie im angezeigten Dialogfeld einen Empfänger oder eine Gruppe aus, und klicken Sie dann **auf Hinzufügen ->**.</span><span class="sxs-lookup"><span data-stu-id="87757-153">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="87757-154">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="87757-154">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="87757-155">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="87757-155">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="87757-156">Wählen Sie zum Entfernen eines Mitglieds das Element aus, und klicken Sie dann auf **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) (Symbol).</span><span class="sxs-lookup"><span data-stu-id="87757-156">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="87757-157">Klicken Sie nach Abschluss des Abschlusses auf **Speichern,** um die Verteilergruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="87757-157">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="87757-158">Ändern von Verteilergruppen mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="87757-158">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="87757-159">Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="87757-159">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="87757-160">Wählen Sie in der Liste der Gruppen die Verteilergruppe oder E-Mail-aktivierte Sicherheitsgruppe aus, die Sie ändern möchten, und klicken Sie dann auf **Bearbeiten** ![ -Symbol ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="87757-160">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="87757-161">Klicken Sie auf der geöffneten Eigenschaftenseite der Verteilergruppe auf eine der folgenden Registerkarten, um Eigenschaften anzeigen oder ändern zu können.</span><span class="sxs-lookup"><span data-stu-id="87757-161">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="87757-162">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="87757-162">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="87757-163">Allgemein</span><span class="sxs-lookup"><span data-stu-id="87757-163">General</span></span>

<span data-ttu-id="87757-164">Verwenden Sie diese Registerkarte, um grundlegende Informationen zur Gruppe anzuzeigen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="87757-164">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="87757-165">**Anzeigename**: Dieser Name wird im Adressbuch, in der Zeile An, wenn E-Mails an diese Gruppe gesendet werden, und in der **Liste Gruppen angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="87757-165">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="87757-166">Der Anzeigename ist erforderlich und sollte benutzerfreundlich sein, damit die Benutzer erkennen, was er ist.</span><span class="sxs-lookup"><span data-stu-id="87757-166">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="87757-167">Sie muss auch in Ihrer Domäne eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="87757-167">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="87757-168">Wenn Sie eine Gruppenbenennungsrichtlinie implementiert haben, muss der Anzeigename dem von der Richtlinie definierten Namensformat entsprechen.</span><span class="sxs-lookup"><span data-stu-id="87757-168">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="87757-169">**Alias**: Dies ist der Teil der E-Mail-Adresse, der links neben dem @-Symbol angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="87757-169">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="87757-170">Wenn Sie den Alias ändern, wird die primäre SMTP-Adresse für die Gruppe ebenfalls geändert, die dann den neuen Alias enthält.</span><span class="sxs-lookup"><span data-stu-id="87757-170">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="87757-171">Zusätzlich bleibt die E-Mail-Adresse mit dem vorherigen Alias als Proxyadresse für die Gruppe erhalten.</span><span class="sxs-lookup"><span data-stu-id="87757-171">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="87757-172">**E-Mail-Adresse:** Die E-Mail-Adresse besteht aus dem Alias auf der linken Seite des @-Symbols und einer Domäne auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="87757-172">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="87757-173">Standardmäßig wird der Wert **von Alias** für den Aliaswert verwendet, Sie können ihn jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="87757-173">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="87757-174">Klicken Sie für den Domänenwert auf die Dropdownliste, und wählen Sie eine akzeptierte Domäne in Ihrer Organisation aus.</span><span class="sxs-lookup"><span data-stu-id="87757-174">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="87757-175">**Beschreibung**: Diese Beschreibung wird im Adressbuch und im Detailbereich in der EAC angezeigt.</span><span class="sxs-lookup"><span data-stu-id="87757-175">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="87757-176">Besitz</span><span class="sxs-lookup"><span data-stu-id="87757-176">Ownership</span></span>

<span data-ttu-id="87757-177">Verwenden Sie diese Registerkarte, um Gruppenbesitzer zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="87757-177">Use this tab to assign group owners.</span></span> <span data-ttu-id="87757-178">Ein Gruppenbesitzer kann die Gruppenmitgliedschaft verwalten.</span><span class="sxs-lookup"><span data-stu-id="87757-178">A group owner can manage group membership.</span></span> <span data-ttu-id="87757-179">Standardmäßig ist die Person, die eine Gruppe erstellt, deren Besitzer.</span><span class="sxs-lookup"><span data-stu-id="87757-179">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="87757-180">Jede Gruppe muss mindestens einen Besitzer aufweisen.</span><span class="sxs-lookup"><span data-stu-id="87757-180">All groups must have at least one owner.</span></span>

<span data-ttu-id="87757-181">Klicken Sie zum Hinzufügen von Besitzern **auf Hinzufügen** ![ -Symbol ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="87757-181">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="87757-182">Suchen Und wählen Sie im angezeigten Dialogfeld einen Empfänger aus, und klicken Sie dann **auf Hinzufügen ->**.</span><span class="sxs-lookup"><span data-stu-id="87757-182">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="87757-183">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="87757-183">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="87757-184">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="87757-184">When you're finished, click **OK**.</span></span>

<span data-ttu-id="87757-185">Wählen Sie zum Entfernen eines Besitzers den Besitzer aus, und klicken Sie dann **auf Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) (Symbol) entfernen.</span><span class="sxs-lookup"><span data-stu-id="87757-185">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="87757-186">Mitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="87757-186">Membership</span></span>

<span data-ttu-id="87757-187">Verwenden Sie diese Registerkarte, um Gruppenmitglieder hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="87757-187">Use this tab to add or remove group members.</span></span> <span data-ttu-id="87757-188">Gruppenbesitzer müssen keine Mitglieder der Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="87757-188">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="87757-189">Klicken Sie zum Hinzufügen von Mitgliedern auf **Hinzufügen** ![ -Symbol ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="87757-189">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="87757-190">Suchen Und wählen Sie im angezeigten Dialogfeld einen Empfänger oder eine Gruppe aus, und klicken Sie dann **auf Hinzufügen ->**.</span><span class="sxs-lookup"><span data-stu-id="87757-190">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="87757-191">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="87757-191">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="87757-192">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="87757-192">When you're finished, click **OK**.</span></span>

<span data-ttu-id="87757-193">Wählen Sie zum Entfernen eines Mitglieds das Element aus, und klicken Sie dann auf **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) (Symbol).</span><span class="sxs-lookup"><span data-stu-id="87757-193">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="87757-194">Entfernen von Gruppen mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="87757-194">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="87757-195">Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="87757-195">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="87757-196">Wählen Sie in der Liste der Gruppen die Verteilergruppe aus, die Sie entfernen möchten, und klicken Sie dann auf **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) (Symbol) entfernen.</span><span class="sxs-lookup"><span data-stu-id="87757-196">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="87757-197">Verwenden von PowerShell zum Verwalten von Gruppen</span><span class="sxs-lookup"><span data-stu-id="87757-197">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="87757-198">Verwenden der eigenständigen EOP PowerShell zum Anzeigen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="87757-198">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="87757-199">Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller Verteilergruppen und E-Mail-aktivierten Sicherheitsgruppen in der eigenständigen EOP PowerShell zurückzukehren:</span><span class="sxs-lookup"><span data-stu-id="87757-199">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="87757-200">Ersetzen Sie zum Zurückgeben der Liste der Gruppenmitglieder durch den Namen, alias oder die E-Mail-Adresse der Gruppe, und \<GroupIdentity\> führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="87757-200">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="87757-201">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-Recipient](/powershell/module/exchange/get-recipient) und [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="87757-201">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="87757-202">Verwenden der eigenständigen EOP PowerShell zum Erstellen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="87757-202">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="87757-203">Verwenden Sie die folgende Syntax, um Verteilergruppen oder E-Mail-aktivierte Sicherheitsgruppen in eigenständigen EOP PowerShell zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="87757-203">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="87757-204">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="87757-204">**Notes**:</span></span>

- <span data-ttu-id="87757-205">Der _Parameter Name_ ist erforderlich, hat eine maximale Länge von 64 Zeichen und muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="87757-205">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="87757-206">Wenn Sie den _DisplayName_-Parameter nicht verwenden, wird der Wert des _Name_-Parameters für den Anzeigenamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="87757-206">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="87757-207">Wenn Sie den _Parameter Alias_ nicht verwenden, wird der _Name-Parameter_ für den Aliaswert verwendet.</span><span class="sxs-lookup"><span data-stu-id="87757-207">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="87757-208">Leerzeichen werden entfernt, und nicht unterstützte Zeichen werden in Fragezeichen (?) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="87757-208">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="87757-209">Wenn Sie den _Parameter PrimarySmtpAddress_ nicht verwenden, wird der Aliaswert im _PrimarySmtpAddress-Parameter_ verwendet.</span><span class="sxs-lookup"><span data-stu-id="87757-209">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="87757-210">Wenn Sie den Parameter _Type_ nicht verwenden, ist der Standardwert Distribution.</span><span class="sxs-lookup"><span data-stu-id="87757-210">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="87757-211">In diesem Beispiel wird eine Verteilergruppe namens "IT Administrators" mit den angegebenen Eigenschaften erstellt.</span><span class="sxs-lookup"><span data-stu-id="87757-211">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="87757-212">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).</span><span class="sxs-lookup"><span data-stu-id="87757-212">For detailed syntax and parameter information, see [New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="87757-213">Verwenden der eigenständigen EOP PowerShell zum Ändern von Gruppen</span><span class="sxs-lookup"><span data-stu-id="87757-213">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="87757-214">Verwenden Sie die folgende Syntax, um Gruppen in eigenständigen EOP PowerShell zu ändern:</span><span class="sxs-lookup"><span data-stu-id="87757-214">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="87757-215">In diesem Beispiel wird die primäre SMTP-Adresse (auch als Antwortadresse bezeichnet) für die Gruppe Seattle Employees verwendet, um sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="87757-215">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="87757-216">In diesem Beispiel werden die aktuellen Mitglieder der Gruppe "Sicherheitsteam" durch Kitty Petersen und Tyson Fawcett ersetzt.</span><span class="sxs-lookup"><span data-stu-id="87757-216">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="87757-217">In diesem Beispiel wird der Gruppe "Security Team" ein neuer Benutzer namens Tyson Fawcett bei Beibehaltung der aktuellen Mitglieder der Gruppe hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="87757-217">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="87757-218">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-EOPDistributionGroup](/powershell/module/exchange/set-eopdistributiongroup) und [Update-EOPDistributionGroupMember](/powershell/module/exchange/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="87757-218">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="87757-219">Entfernen einer Gruppe mithilfe von remote Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="87757-219">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="87757-220">In diesem Beispiel wird die Verteilergruppe mit dem Namen "IT-Administratoren" entfernt.</span><span class="sxs-lookup"><span data-stu-id="87757-220">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="87757-221">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-EOPDistributionGroup](/powershell/module/exchange/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="87757-221">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="87757-222">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="87757-222">How do you know these procedures worked?</span></span>

<span data-ttu-id="87757-223">Gehen Sie wie folgt vor, um zu überprüfen, ob Sie eine Verteilergruppe oder eine E-Mail-aktivierte Sicherheitsgruppe erfolgreich erstellt, geändert oder entfernt haben:</span><span class="sxs-lookup"><span data-stu-id="87757-223">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="87757-224">Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="87757-224">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="87757-225">Überprüfen Sie, ob die Gruppe aufgeführt ist (oder nicht), und überprüfen Sie den **Gruppentypwert.**</span><span class="sxs-lookup"><span data-stu-id="87757-225">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="87757-226">Wählen Sie die Gruppe aus, und zeigen  Sie die Informationen im Detailbereich an, oder klicken Sie auf Bearbeiten ![ (Symbol ](../../media/ITPro-EAC-AddIcon.png) bearbeiten), um die Einstellungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="87757-226">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="87757-227">Führen Sie in der eigenständigen EOP PowerShell den folgenden Befehl aus, um zu überprüfen, ob die Gruppe aufgeführt ist (oder nicht aufgeführt ist):</span><span class="sxs-lookup"><span data-stu-id="87757-227">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="87757-228">Ersetzen Sie durch den Namen, alias oder die E-Mail-Adresse der Gruppe, und führen Sie den folgenden Befehl aus, \<GroupIdentity\> um die Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="87757-228">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="87757-229">Ersetzen Sie zum Anzeigen der Gruppenmitglieder durch den Namen, alias oder die E-Mail-Adresse der Gruppe, und \<GroupIdentity\> führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="87757-229">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```