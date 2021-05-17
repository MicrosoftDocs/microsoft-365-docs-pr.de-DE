---
title: Verwalten von E-Mail-Benutzern in EOP als eigenständige Lösung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Erfahren Sie, wie Sie E-Mail-Benutzer in Exchange Online Protection (EOP) verwalten, einschließlich der Verwendung von Verzeichnissynchronisierung, EAC und PowerShell zum Verwalten von Benutzern.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203987"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="6cc8d-103">Verwalten von E-Mail-Benutzern in EOP als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="6cc8d-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6cc8d-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-104">**Applies to**</span></span>
-  [<span data-ttu-id="6cc8d-105">Exchange Online Protection eigenständig</span><span class="sxs-lookup"><span data-stu-id="6cc8d-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="6cc8d-106">In eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online sind E-Mail-Benutzer der grundlegende Typ des Benutzerkontos.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="6cc8d-107">Ein E-Mail-Benutzer verfügt über Kontoanmeldeinformationen in Ihrer eigenständigen EOP-Organisation und kann auf Ressourcen zugreifen (berechtigungen zugewiesen haben).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-107">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="6cc8d-108">Die E-Mail-Adresse eines E-Mail-Benutzers ist extern (z. B. in Ihrer lokalen E-Mail-Umgebung).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-108">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="6cc8d-109">Wenn Sie einen E-Mail-Benutzer erstellen, ist das entsprechende Benutzerkonto im Microsoft 365 Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-109">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6cc8d-110">Wenn Sie ein Benutzerkonto im Microsoft 365 Admin Center erstellen, können Sie dieses Konto nicht zum Erstellen eines E-Mail-Benutzers verwenden.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-110">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="6cc8d-111">Die empfohlene Methode zum Erstellen und Verwalten von E-Mail-Benutzern in eigenständigem EOP ist die Verwendung der Verzeichnissynchronisierung, wie weiter unten in diesem Artikel im Abschnitt Verwenden der Verzeichnissynchronisierung zum Verwalten von [E-Mail-Benutzern](#use-directory-synchronization-to-manage-mail-users) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-111">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="6cc8d-112">Für eigenständige EOP-Organisationen mit einer kleinen Anzahl von Benutzern können Sie E-Mail-Benutzer im Exchange Admin Center (EAC) oder in der eigenständigen EOP PowerShell hinzufügen und verwalten, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-112">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6cc8d-113">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="6cc8d-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6cc8d-114">Informationen zum Öffnen Exchange Admin Center (EAC) finden Sie [unter Exchange Admin Center im eigenständigen EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-114">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="6cc8d-115">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="6cc8d-116">Wenn Sie E-Mail-Benutzer in EOP PowerShell erstellen, kann eine Einschränkung auftreten.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-116">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="6cc8d-117">Außerdem verwenden die EOP PowerShell-Cmdlets eine Batchverarbeitungsmethode, die zu einer Übertragungsverzögerung von einigen Minuten führt, bevor die Ergebnisse der Befehle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-117">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="6cc8d-118">Bevor Sie die Verfahren in diesem Artikel Exchange Online Protection, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="6cc8d-119">Insbesondere benötigen Sie die Rollen **E-Mail-Empfängererstellung** (erstellen) und E-Mail-Empfänger (ändern),  die standardmäßig den Rollengruppen Organisationsverwaltung **(globale** Administratoren) und Empfängerverwaltung zugewiesen sind. </span><span class="sxs-lookup"><span data-stu-id="6cc8d-119">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="6cc8d-120">Weitere Informationen finden Sie unter [Permissions in standalone EOP](feature-permissions-in-eop.md) und [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="6cc8d-121">Informationen zu Tastenkombinationen, die für die Verfahren in diesem Artikel gelten können, finden Sie unter Tastenkombinationen für das [Exchange Admin Center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="6cc8d-122">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="6cc8d-122">Having problems?</span></span> <span data-ttu-id="6cc8d-123">Bitten Sie in den Exchange-Foren um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-123">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="6cc8d-124">Besuchen Sie [das Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) Forum.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-124">Visit the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="6cc8d-125">Verwenden des Exchange Admin Center zum Verwalten von E-Mail-Benutzern</span><span class="sxs-lookup"><span data-stu-id="6cc8d-125">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="6cc8d-126">Erstellen von E-Mail-Benutzern mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="6cc8d-126">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="6cc8d-127">Wechseln Sie in der  EAC zu \> **Empfängerkontakte**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-127">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="6cc8d-128">Klicken Sie **auf Neues** Neues ![ Symbol ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="6cc8d-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="6cc8d-129">Konfigurieren Sie **auf der Seite** Neuer E-Mail-Benutzer, die geöffnet wird, die folgenden Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-129">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="6cc8d-130">Einstellungen, die mit einem <sup>\*</sup> gekennzeichnet sind, sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-130">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="6cc8d-131">**Vorname**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-131">**First name**</span></span>

   - <span data-ttu-id="6cc8d-132">**Initialen**: Die mittlere Initiale der Person.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-132">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="6cc8d-133">**Nachname**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-133">**Last name**</span></span>

   - <span data-ttu-id="6cc8d-134"><sup>\*</sup>**Anzeigename**: Standardmäßig werden in diesem Feld die Werte aus den Feldern **Vorname,** **Initialen** und **Nachname** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-134"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="6cc8d-135">Sie können diesen Wert akzeptieren oder ändern.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-135">You can accept this value or change it.</span></span> <span data-ttu-id="6cc8d-136">Der Wert sollte eindeutig sein und eine maximale Länge von 64 Zeichen haben.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-136">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="6cc8d-137"><sup>\*</sup>**Alias**: Geben Sie einen eindeutigen Alias mit bis zu 64 Zeichen für den Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-137"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="6cc8d-138">**Externe E-Mail-Adresse:** Geben Sie die E-Mail-Adresse des Benutzers ein.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-138">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="6cc8d-139">Die Domäne sollte sich außerhalb Ihrer cloudbasierten Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-139">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="6cc8d-140"><sup>\*</sup>**Benutzer-ID**: Geben Sie das Konto ein, mit dem sich die Person beim Dienst anmeldet.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-140"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="6cc8d-141">Die Benutzer-ID besteht aus einem Benutzernamen auf der linken Seite des @-Symbols (@) und einer Domäne auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-141">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="6cc8d-142"><sup>\*</sup>**Neues Kennwort** und Kennwort bestätigen: Geben Sie das <sup>\*</sup> Kontokennwort ein, und geben Sie es erneut ein.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-142"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="6cc8d-143">Stellen Sie sicher, dass das Kennwort den Kennwortlängen-, Komplexitäts- und Verlaufsanforderungen Ihrer Organisation entspricht.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-143">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="6cc8d-144">Wenn Sie fertig sind, klicken Sie auf **Speichern**, um den E-Mail-Benutzer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-144">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="6cc8d-145">Ändern von E-Mail-Benutzern mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="6cc8d-145">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="6cc8d-146">Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-146">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="6cc8d-147">Wählen Sie den E-Mail-Benutzer aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten** ![ (Symbol). ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="6cc8d-147">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="6cc8d-148">Klicken Sie auf der seite E-Mail-Benutzereigenschaften, die geöffnet wird, auf eine der folgenden Registerkarten, um Eigenschaften anzeigen oder ändern zu können.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-148">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="6cc8d-149">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-149">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="6cc8d-150">Allgemein</span><span class="sxs-lookup"><span data-stu-id="6cc8d-150">General</span></span>

<span data-ttu-id="6cc8d-151">Verwenden Sie die **Registerkarte Allgemein,** um grundlegende Informationen zum E-Mail-Benutzer ein- oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-151">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="6cc8d-152">**Vorname**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-152">**First name**</span></span>

- <span data-ttu-id="6cc8d-153">**Initialen**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-153">**Initials**</span></span>

- <span data-ttu-id="6cc8d-154">**Nachname**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-154">**Last name**</span></span>

- <span data-ttu-id="6cc8d-155">**Anzeigename**: Dieser Name wird im Adressbuch Ihrer Organisation, in den Zeilen An: und Von: in E-Mail und in der Liste der Kontakte in der EAC angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-155">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="6cc8d-156">Dieser Name darf keine Leerzeichen vor oder nach dem Anzeigenamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-156">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="6cc8d-157">**Benutzer-ID**: Dies ist das Konto des Benutzers in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-157">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="6cc8d-158">Sie können diesen Wert hier nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-158">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="6cc8d-159">Kontaktinformationen</span><span class="sxs-lookup"><span data-stu-id="6cc8d-159">Contact information</span></span>

<span data-ttu-id="6cc8d-160">Verwenden Sie **die Registerkarte Kontaktinformationen,** um die Kontaktinformationen des Benutzers ein- oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-160">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="6cc8d-161">Die Informationen auf dieser Seite werden im Adressbuch angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-161">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="6cc8d-162">**Straße**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-162">**Street**</span></span>
- <span data-ttu-id="6cc8d-163">**City**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-163">**City**</span></span>
- <span data-ttu-id="6cc8d-164">**Bundesland/Kanton**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-164">**State/Province**</span></span>
- <span data-ttu-id="6cc8d-165">**PLZ**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-165">**ZIP/Postal code**</span></span>
- <span data-ttu-id="6cc8d-166">**Land/Region**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-166">**Country/Region**</span></span>
- <span data-ttu-id="6cc8d-167">**Telefon (geschäftlich)**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-167">**Work phone**</span></span>
- <span data-ttu-id="6cc8d-168">**Mobiltelefon**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-168">**Mobile phone**</span></span>
- <span data-ttu-id="6cc8d-169">**Fax**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-169">**Fax**</span></span>
- <span data-ttu-id="6cc8d-170">**Weitere Optionen**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-170">**More options**</span></span>

  - <span data-ttu-id="6cc8d-171">**Office**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-171">**Office**</span></span>
  - <span data-ttu-id="6cc8d-172">**Telefon (privat)**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-172">**Home phone**</span></span>
  - <span data-ttu-id="6cc8d-173">**Webseite**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-173">**Web page**</span></span>
  - <span data-ttu-id="6cc8d-174">**Notizen**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-174">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="6cc8d-175">Organisation</span><span class="sxs-lookup"><span data-stu-id="6cc8d-175">Organization</span></span>

<span data-ttu-id="6cc8d-176">Verwenden Sie **die Registerkarte Organisation,** um detaillierte Informationen zur Rolle des Benutzers in der Organisation zu aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-176">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="6cc8d-177">**Titel**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-177">**Title**</span></span>
- <span data-ttu-id="6cc8d-178">**Abteilung**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-178">**Department**</span></span>
- <span data-ttu-id="6cc8d-179">**Company**</span><span class="sxs-lookup"><span data-stu-id="6cc8d-179">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="6cc8d-180">Entfernen von E-Mail-Benutzern mithilfe der EAC</span><span class="sxs-lookup"><span data-stu-id="6cc8d-180">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="6cc8d-181">Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-181">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="6cc8d-182">Wählen Sie den E-Mail-Benutzer aus, den Sie entfernen möchten, und klicken Sie dann auf **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) (Symbol).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-182">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="6cc8d-183">Verwalten von E-Mail-Benutzern mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cc8d-183">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="6cc8d-184">Verwenden der eigenständigen EOP PowerShell zum Anzeigen von E-Mail-Benutzern</span><span class="sxs-lookup"><span data-stu-id="6cc8d-184">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="6cc8d-185">Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller E-Mail-Benutzer in eigenständigem EOP PowerShell zurück zu geben:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-185">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="6cc8d-186">Ersetzen Sie zum Anzeigen detaillierter Informationen zu einem bestimmten E-Mail-Benutzer durch den Namen, Alias oder Kontonamen des E-Mail-Benutzers, und führen Sie \<MailUserIdentity\> die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-186">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="6cc8d-187">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-Recipient](/powershell/module/exchange/get-recipient) und [Get-User](/powershell/module/exchange/get-user).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-187">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-User](/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="6cc8d-188">Verwenden der eigenständigen EOP PowerShell zum Erstellen von E-Mail-Benutzern</span><span class="sxs-lookup"><span data-stu-id="6cc8d-188">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="6cc8d-189">Verwenden Sie die folgende Syntax, um E-Mail-Benutzer in eigenständiger EOP PowerShell zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-189">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="6cc8d-190">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-190">**Notes**:</span></span>

- <span data-ttu-id="6cc8d-191">Der _Parameter Name_ ist erforderlich, hat eine maximale Länge von 64 Zeichen und muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-191">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="6cc8d-192">Wenn Sie den _DisplayName_-Parameter nicht verwenden, wird der Wert des _Name_-Parameters für den Anzeigenamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-192">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="6cc8d-193">Wenn Sie den _Parameter Alias_ nicht verwenden, wird die linke Seite des _Parameters MicrosoftOnlineServicesID_ für den Alias verwendet.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-193">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="6cc8d-194">Wenn Sie den _Parameter ExternalEmailAddress_ nicht verwenden, wird der _MicrosoftOnlineServicesID-Wert_ für die externe E-Mail-Adresse verwendet.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-194">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="6cc8d-195">In diesem Beispiel wird ein E-Mail-Benutzer mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-195">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="6cc8d-196">Der Name ist JeffreyZeng, und der Anzeigename ist Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-196">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="6cc8d-197">Der Vorname ist "Jeffrey" und der Nachname ist "Zeng".</span><span class="sxs-lookup"><span data-stu-id="6cc8d-197">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="6cc8d-198">Der Alias ist "jeffreyz".</span><span class="sxs-lookup"><span data-stu-id="6cc8d-198">The alias is jeffreyz.</span></span>
- <span data-ttu-id="6cc8d-199">Die externe E-Mail-Adresse ist "jzeng@tailspintoys.com".</span><span class="sxs-lookup"><span data-stu-id="6cc8d-199">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="6cc8d-200">Der Kontoname ist jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-200">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="6cc8d-201">Das Kennwort lautet "Pa$$word1".</span><span class="sxs-lookup"><span data-stu-id="6cc8d-201">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="6cc8d-202">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-202">For detailed syntax and parameter information, see [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="6cc8d-203">Verwenden der eigenständigen EOP PowerShell zum Ändern von E-Mail-Benutzern</span><span class="sxs-lookup"><span data-stu-id="6cc8d-203">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="6cc8d-204">Verwenden Sie die folgende Syntax, um vorhandene E-Mail-Benutzer in der eigenständigen EOP PowerShell zu ändern:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-204">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="6cc8d-205">In diesem Beispiel wird die externe E-Mail-Adresse für Pilar Pinella festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-205">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="6cc8d-206">In diesem Beispiel wird die Eigenschaft "Company" für alle E-Mail-Benutzer in "Contoso" geändert.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-206">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="6cc8d-207">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-207">For detailed syntax and parameter information, see [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="6cc8d-208">Verwenden der eigenständigen EOP PowerShell zum Entfernen von E-Mail-Benutzern</span><span class="sxs-lookup"><span data-stu-id="6cc8d-208">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="6cc8d-209">Um E-Mail-Benutzer in eigenständiger EOP PowerShell zu entfernen, ersetzen Sie durch den Namen, Alias oder Kontonamen des E-Mail-Benutzers, und führen Sie den \<MailUserIdentity\> folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-209">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="6cc8d-210">In diesem Beispiel wird der E-Mail-Benutzer für Jeffrey Zeng entfernt.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-210">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="6cc8d-211">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-211">For detailed syntax and parameter information, see [Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6cc8d-212">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="6cc8d-212">How do you know these procedures worked?</span></span>

<span data-ttu-id="6cc8d-213">Verwenden Sie eines der folgenden Verfahren, um zu überprüfen, ob E-Mail-Benutzer im eigenständigen EOP erfolgreich erstellt, geändert oder entfernt wurden:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-213">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="6cc8d-214">Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-214">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="6cc8d-215">Stellen Sie sicher, dass der E-Mail-Benutzer aufgeführt ist (oder nicht aufgeführt ist).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-215">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="6cc8d-216">Wählen Sie den E-Mail-Benutzer aus,  und zeigen Sie die Informationen im Detailbereich an, oder klicken Sie auf Bearbeiten (Symbol bearbeiten), ![ um die Einstellungen ](../../media/ITPro-EAC-AddIcon.png) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-216">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="6cc8d-217">Führen Sie in der eigenständigen EOP PowerShell den folgenden Befehl aus, um zu überprüfen, ob der E-Mail-Benutzer aufgeführt ist (oder nicht aufgeführt ist):</span><span class="sxs-lookup"><span data-stu-id="6cc8d-217">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="6cc8d-218">Ersetzen Sie durch den Namen, Alias oder Kontonamen des E-Mail-Benutzers, und führen Sie die folgenden Befehle aus, um \<MailUserIdentity\> die Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-218">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="6cc8d-219">Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="6cc8d-219">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="6cc8d-220">In eigenständigem EOP ist die Verzeichnissynchronisierung für Kunden mit lokalem Active Directory verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-220">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="6cc8d-221">Sie können diese Konten mit Azure Active Directory (Azure AD) synchronisieren, in dem Kopien der Konten in der Cloud gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-221">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="6cc8d-222">Wenn Sie Ihre vorhandenen Benutzerkonten mit Azure Active Directory synchronisieren, können  Sie diese Benutzer im Bereich Empfänger im Exchange Admin Center (EAC) oder in der eigenständigen EOP PowerShell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-222">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="6cc8d-223">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-223">**Notes**:</span></span>

- <span data-ttu-id="6cc8d-224">Wenn Sie die Verzeichnissynchronisierung zum Verwalten Ihrer Empfänger verwenden, können Sie weiterhin Benutzer im Microsoft 365 Admin Center hinzufügen und verwalten, aber sie werden nicht mit Ihrem lokalen Active Directory synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-224">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="6cc8d-225">Dies liegt daran, dass die Verzeichnissynchronisierung nur Empfänger aus Ihrem lokalen Active Directory mit der Cloud synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-225">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="6cc8d-226">Für die folgenden Funktionen wird empfohlen, Verzeichnissynchronisierung zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="6cc8d-226">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="6cc8d-227">**Outlook Listen** sicherer Absender und Listen blockierter Absender : Bei der Synchronisierung mit dem Dienst haben diese Listen Vorrang vor der Spamfilterung im Dienst.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-227">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="6cc8d-228">Auf diese Weise können Benutzer ihre eigene Liste sicherer Absender und die Liste blockierter Absender mit einzelnen Absender- und Domäneneinträgen verwalten.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-228">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="6cc8d-229">Weitere Informationen finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-229">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="6cc8d-230">**Directory Based Edge Blocking (DBEB)**: Weitere Informationen zu DBEB finden Sie unter [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-230">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="6cc8d-231">**Endbenutzerzugriff auf Quarantäne:** Für den Zugriff auf ihre isolierten Nachrichten müssen Empfänger über eine gültige Benutzer-ID und ein Kennwort im Dienst verfügen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-231">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="6cc8d-232">Weitere Informationen zur Quarantäne finden Sie unter [Suchen und Veröffentlichen isolierter](find-and-release-quarantined-messages-as-a-user.md)Nachrichten als Benutzer.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-232">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="6cc8d-233">**Nachrichtenflussregeln (auch** als Transportregeln bezeichnet): Wenn Sie die Verzeichnissynchronisierung verwenden, werden Ihre vorhandenen Active Directory-Benutzer und -Gruppen automatisch in die Cloud hochgeladen, und Sie können dann Nachrichtenflussregeln für bestimmte Benutzer und/oder Gruppen erstellen, ohne sie manuell in den Dienst hinzufügen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-233">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="6cc8d-234">Bitte beachten Sie, dass [dynamische Verteilungsgruppen](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) nicht über die Verzeichnissynchronisierung synchronisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-234">Note that [dynamic distribution groups](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="6cc8d-235">Erhalten Sie die erforderlichen Berechtigungen, und bereiten Sie sich auf die Verzeichnissynchronisierung vor, wie unter [Was ist Hybrididentität mit Azure Active Directory? beschrieben.](/azure/active-directory/hybrid/whatis-hybrid-identity)</span><span class="sxs-lookup"><span data-stu-id="6cc8d-235">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="6cc8d-236">Synchronisieren von Verzeichnissen mit Azure Active Directory Verbinden (AAD Verbinden)</span><span class="sxs-lookup"><span data-stu-id="6cc8d-236">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="6cc8d-237">Aktivieren Sie die Verzeichnissynchronisierung, wie in [Azure AD Verbinden Synchronisierung beschrieben: Verstehen und Anpassen der Synchronisierung](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-237">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="6cc8d-238">Installieren und Konfigurieren eines lokalen Computers zum Ausführen von AAD-Verbinden wie unter [Voraussetzungen für Azure AD Verbinden](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="6cc8d-238">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="6cc8d-239">[Wählen Sie aus, welcher Installationstyp für Azure AD Verbinden:](/azure/active-directory/hybrid/how-to-connect-install-select-installation)</span><span class="sxs-lookup"><span data-stu-id="6cc8d-239">[Select which installation type to use for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="6cc8d-240">Express</span><span class="sxs-lookup"><span data-stu-id="6cc8d-240">Express</span></span>](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="6cc8d-241">Custom</span><span class="sxs-lookup"><span data-stu-id="6cc8d-241">Custom</span></span>](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="6cc8d-242">Pass-Through-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="6cc8d-242">Pass-through authentication</span></span>](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="6cc8d-p121">Wenn Sie den Konfigurationsassistent für Azure Active Directory-Synchronisierungstool abschließen, wird in Ihrer Active Directory-Gesamtstruktur das Konto **MSOL_AD_SYNC** erstellt. Dieses Konto wird zum Lesen und Synchronisieren der lokalen Active Directory-Informationen verwendet. Damit die Verzeichnissynchronisierung ordnungsgemäß ausgeführt wird, müssen Sie sicherstellen, dass TCP 443 auf dem lokalen Verzeichnissynchronisierungsserver geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="6cc8d-246">Stellen Sie nach dem Konfigurieren der Synchronisierung sicher, dass Verbinden AAD ordnungsgemäß synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-246">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="6cc8d-247">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Empfänger** \> **Kontakte**, und vergewissern Sie sich, dass die Liste der Benutzer in Ihrer lokalen Umgebung korrekt synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="6cc8d-247">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>