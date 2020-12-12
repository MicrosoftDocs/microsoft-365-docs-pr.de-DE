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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: In diesem Artikel erfahren Sie, wie Sie e-Mail-Benutzer in Exchange Online Protection (EoP) verwalten, einschließlich der Verwendung der Verzeichnissynchronisierung, der Exchange-Verwaltungskonsole und PowerShell zum Verwalten von Benutzern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a8258a63fe0fbf4a6b5641fbdef213f25de2e4dd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658833"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="378ee-103">Verwalten von E-Mail-Benutzern in EOP als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="378ee-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="378ee-104">In Organisationen mit eigenständigen Exchange Online Schutz (EoP) ohne Exchange Online Postfächer sind e-Mail-Benutzer der grundlegende Typ des Benutzerkontos.</span><span class="sxs-lookup"><span data-stu-id="378ee-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="378ee-105">Ein e-Mail-Benutzer verfügt über Kontoanmeldeinformationen in ihrer eigenständigen EoP-Organisation und kann auf Ressourcen zugreifen (Berechtigungen zugewiesen).</span><span class="sxs-lookup"><span data-stu-id="378ee-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="378ee-106">Die e-Mail-Adresse eines e-Mail-Benutzers ist extern (beispielsweise in Ihrer lokalen e-Mail-Umgebung).</span><span class="sxs-lookup"><span data-stu-id="378ee-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="378ee-107">Wenn Sie einen e-Mail-Benutzer erstellen, ist das entsprechende Benutzerkonto im Microsoft 365 Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="378ee-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="378ee-108">Wenn Sie ein Benutzerkonto im Microsoft 365 Admin Center erstellen, können Sie dieses Konto nicht verwenden, um einen e-Mail-Benutzer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="378ee-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="378ee-109">Die empfohlene Methode zum Erstellen und Verwalten von e-Mail-Benutzern in eigenständigen EoP besteht in der Verwendung der Verzeichnissynchronisierung, wie im Abschnitt [Verwenden der Verzeichnissynchronisierung zum Verwalten von e-Mail-Benutzern](#use-directory-synchronization-to-manage-mail-users) weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="378ee-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="378ee-110">Für eigenständige EoP-Organisationen mit einer kleinen Anzahl von Benutzern können Sie e-Mail-Benutzer in der Exchange-Verwaltungskonsole (EAC) oder in der eigenständigen EoP-PowerShell hinzufügen und verwalten, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="378ee-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="378ee-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="378ee-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="378ee-112">Informationen zum Öffnen des Exchange Admin Center (EAC) finden Sie unter [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="378ee-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="378ee-113">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="378ee-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="378ee-114">Wenn Sie e-Mail-Benutzer in EoP PowerShell erstellen, stoßen Sie möglicherweise auf Drosselung.</span><span class="sxs-lookup"><span data-stu-id="378ee-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="378ee-115">Außerdem verwenden die EoP-PowerShell-Cmdlets eine Batch Verarbeitungsmethode, die zu einer Ausbreitungs Verzögerung von ein paar Minuten führt, bevor die Ergebnisse der Befehle sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="378ee-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="378ee-116">Sie müssen Berechtigungen in Exchange Online Protection zugewiesen werden, bevor Sie die Verfahren in diesem Artikel ausführen können.</span><span class="sxs-lookup"><span data-stu-id="378ee-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="378ee-117">Insbesondere benötigen Sie die Rollen für die **Erstellung von e-Mail-Empfängern** (Create) und **e-Mail-Empfänger** (ändern), die standardmäßig der Rollengruppe **Organisationsverwaltung** (Global Admins) und **Empfängerverwaltung** zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="378ee-117">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="378ee-118">Weitere Informationen finden Sie unter [Berechtigungen in eigenständigen EoP](feature-permissions-in-eop.md) und [Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="378ee-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="378ee-119">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Artikel gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="378ee-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="378ee-120">Liegt ein Problem vor?</span><span class="sxs-lookup"><span data-stu-id="378ee-120">Having problems?</span></span> <span data-ttu-id="378ee-121">Bitten Sie in den Exchange-Foren um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="378ee-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="378ee-122">Besuchen Sie das [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) -Forum.</span><span class="sxs-lookup"><span data-stu-id="378ee-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="378ee-123">Verwalten von e-Mail-Benutzern mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="378ee-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="378ee-124">Erstellen von e-Mail-Benutzern mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="378ee-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="378ee-125">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Empfänger** \> **Kontakte**</span><span class="sxs-lookup"><span data-stu-id="378ee-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="378ee-126">Klicken Sie auf **Neues** ![ Neues Symbol ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="378ee-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="378ee-127">Konfigurieren Sie auf der Seite **neuer e-Mail-Benutzer** , die geöffnet wird, die folgenden Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="378ee-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="378ee-128">Mit einem markierte Einstellungen <sup>\*</sup> sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="378ee-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="378ee-129">**Vorname**</span><span class="sxs-lookup"><span data-stu-id="378ee-129">**First name**</span></span>

   - <span data-ttu-id="378ee-130">**Initialen**: der mittlere Initialwert der Person.</span><span class="sxs-lookup"><span data-stu-id="378ee-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="378ee-131">**Nachname**</span><span class="sxs-lookup"><span data-stu-id="378ee-131">**Last name**</span></span>

   - <span data-ttu-id="378ee-132"><sup>\*</sup>**Anzeigename**: Standardmäßig werden in diesem Feld die Werte aus den Feldern **Vorname**, **Initialen** und **Nachname** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="378ee-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="378ee-133">Sie können diesen Wert akzeptieren oder ändern.</span><span class="sxs-lookup"><span data-stu-id="378ee-133">You can accept this value or change it.</span></span> <span data-ttu-id="378ee-134">Der Wert sollte eindeutig sein und hat eine maximale Länge von 64 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="378ee-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="378ee-135"><sup>\*</sup>**Alias**: Geben Sie einen eindeutigen Alias mit bis zu 64 Zeichen für den Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="378ee-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="378ee-136">**Externe e-Mail-Adresse**: Geben Sie die e-Mail-Adresse des Benutzers ein.</span><span class="sxs-lookup"><span data-stu-id="378ee-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="378ee-137">Die Domäne sollte sich außerhalb ihrer cloudbasierten Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="378ee-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="378ee-138"><sup>\*</sup>**Benutzer-ID**: Geben Sie das Konto ein, mit dem sich die Person beim Dienst anmelden wird.</span><span class="sxs-lookup"><span data-stu-id="378ee-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="378ee-139">Die Benutzer-ID besteht aus einem Benutzernamen auf der linken Seite des @-Symbols (@) und einer Domäne auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="378ee-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="378ee-140"><sup>\*</sup>**Neues Kennwort** und <sup>\*</sup> **Kennwort bestätigen**: Geben Sie das Kontokennwort ein, und geben Sie es erneut ein.</span><span class="sxs-lookup"><span data-stu-id="378ee-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="378ee-141">Stellen Sie sicher, dass das Kennwort den Anforderungen in Bezug auf Länge, Komplexität und Verlauf Ihrer Organisation entspricht.</span><span class="sxs-lookup"><span data-stu-id="378ee-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="378ee-142">Wenn Sie fertig sind, klicken Sie auf **Speichern**, um den E-Mail-Benutzer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="378ee-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="378ee-143">Ändern von e-Mail-Benutzern mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="378ee-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="378ee-144">Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.</span><span class="sxs-lookup"><span data-stu-id="378ee-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="378ee-145">Wählen Sie den e-Mail-Benutzer aus, den Sie ändern möchten, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="378ee-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="378ee-146">Klicken Sie auf der Seite Eigenschaften von e-Mail-Benutzer, die geöffnet wird, auf eine der folgenden Registerkarten, um Eigenschaften anzuzeigen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="378ee-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="378ee-147">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="378ee-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="378ee-148">Allgemein</span><span class="sxs-lookup"><span data-stu-id="378ee-148">General</span></span>

<span data-ttu-id="378ee-149">Verwenden Sie die Registerkarte **Allgemein** , um grundlegende Informationen zum e-Mail-Benutzer anzuzeigen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="378ee-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="378ee-150">**Vorname**</span><span class="sxs-lookup"><span data-stu-id="378ee-150">**First name**</span></span>

- <span data-ttu-id="378ee-151">**Initialen**</span><span class="sxs-lookup"><span data-stu-id="378ee-151">**Initials**</span></span>

- <span data-ttu-id="378ee-152">**Nachname**</span><span class="sxs-lookup"><span data-stu-id="378ee-152">**Last name**</span></span>

- <span data-ttu-id="378ee-153">**Anzeigename**: dieser Name wird im Adressbuch Ihrer Organisation, in den Zeilen "an:" und "von:" in e-Mail und in der Liste der Kontakte in der Exchange-Verwaltungskonsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="378ee-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="378ee-154">Dieser Name darf keine Leerzeichen vor oder nach dem Anzeigenamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="378ee-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="378ee-155">**Benutzer-ID**: Dies ist das Konto des Benutzers in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="378ee-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="378ee-156">Sie können diesen Wert hier nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="378ee-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="378ee-157">Kontaktinformationen</span><span class="sxs-lookup"><span data-stu-id="378ee-157">Contact information</span></span>

<span data-ttu-id="378ee-158">Verwenden Sie die Registerkarte **Kontaktinformationen** , um die Kontaktinformationen des Benutzers anzuzeigen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="378ee-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="378ee-159">Die Informationen auf dieser Seite werden im Adressbuch angezeigt.</span><span class="sxs-lookup"><span data-stu-id="378ee-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="378ee-160">**Straße**</span><span class="sxs-lookup"><span data-stu-id="378ee-160">**Street**</span></span>
- <span data-ttu-id="378ee-161">**City**</span><span class="sxs-lookup"><span data-stu-id="378ee-161">**City**</span></span>
- <span data-ttu-id="378ee-162">**Bundesland/Kanton**</span><span class="sxs-lookup"><span data-stu-id="378ee-162">**State/Province**</span></span>
- <span data-ttu-id="378ee-163">**PLZ**</span><span class="sxs-lookup"><span data-stu-id="378ee-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="378ee-164">**Land/Region**</span><span class="sxs-lookup"><span data-stu-id="378ee-164">**Country/Region**</span></span>
- <span data-ttu-id="378ee-165">**Telefon (geschäftlich)**</span><span class="sxs-lookup"><span data-stu-id="378ee-165">**Work phone**</span></span>
- <span data-ttu-id="378ee-166">**Mobiltelefon**</span><span class="sxs-lookup"><span data-stu-id="378ee-166">**Mobile phone**</span></span>
- <span data-ttu-id="378ee-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="378ee-167">**Fax**</span></span>
- <span data-ttu-id="378ee-168">**Weitere Optionen**</span><span class="sxs-lookup"><span data-stu-id="378ee-168">**More options**</span></span>

  - <span data-ttu-id="378ee-169">**Office**</span><span class="sxs-lookup"><span data-stu-id="378ee-169">**Office**</span></span>
  - <span data-ttu-id="378ee-170">**Telefon (privat)**</span><span class="sxs-lookup"><span data-stu-id="378ee-170">**Home phone**</span></span>
  - <span data-ttu-id="378ee-171">**Webseite**</span><span class="sxs-lookup"><span data-stu-id="378ee-171">**Web page**</span></span>
  - <span data-ttu-id="378ee-172">**Notizen**</span><span class="sxs-lookup"><span data-stu-id="378ee-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="378ee-173">Organisation</span><span class="sxs-lookup"><span data-stu-id="378ee-173">Organization</span></span>

<span data-ttu-id="378ee-174">Verwenden Sie die Registerkarte **Organisation** , um detaillierte Informationen zur Rolle des Benutzers in der Organisation aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="378ee-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="378ee-175">**Titel**</span><span class="sxs-lookup"><span data-stu-id="378ee-175">**Title**</span></span>
- <span data-ttu-id="378ee-176">**Abteilung**</span><span class="sxs-lookup"><span data-stu-id="378ee-176">**Department**</span></span>
- <span data-ttu-id="378ee-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="378ee-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="378ee-178">Entfernen von e-Mail-Benutzern mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="378ee-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="378ee-179">Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.</span><span class="sxs-lookup"><span data-stu-id="378ee-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="378ee-180">Wählen Sie den e-Mail-Benutzer aus, den Sie entfernen möchten, und klicken Sie dann auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="378ee-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="378ee-181">Verwenden von PowerShell zum Verwalten von e-Mail-Benutzern</span><span class="sxs-lookup"><span data-stu-id="378ee-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="378ee-182">Verwenden von eigenständigen EoP PowerShell zum Anzeigen von e-Mail-Benutzern</span><span class="sxs-lookup"><span data-stu-id="378ee-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="378ee-183">Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller e-Mail-Benutzer in eigenständiger EoP PowerShell zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="378ee-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="378ee-184">Wenn Sie detaillierte Informationen zu einem bestimmten e-Mail-Benutzer anzeigen möchten, ersetzen Sie \<MailUserIdentity\> durch den Namen, den Alias oder den Kontonamen des e-Mail-Benutzers, und führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="378ee-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="378ee-185">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) und [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span><span class="sxs-lookup"><span data-stu-id="378ee-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="378ee-186">Verwenden eigenständiger EoP PowerShell zum Erstellen von e-Mail-Benutzern</span><span class="sxs-lookup"><span data-stu-id="378ee-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="378ee-187">Verwenden Sie die folgende Syntax, um e-Mail-Benutzer in eigenständiger EoP PowerShell zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="378ee-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="378ee-188">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="378ee-188">**Notes**:</span></span>

- <span data-ttu-id="378ee-189">Der _Name_ -Parameter ist erforderlich, hat eine maximale Länge von 64 Zeichen und muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="378ee-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="378ee-190">Wenn Sie den _DisplayName_-Parameter nicht verwenden, wird der Wert des _Name_-Parameters für den Anzeigenamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="378ee-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="378ee-191">Wenn Sie den Parameter _Alias_ nicht verwenden, wird die linke Seite des _MicrosoftOnlineServicesID_ -Parameters für den Alias verwendet.</span><span class="sxs-lookup"><span data-stu-id="378ee-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="378ee-192">Wenn Sie den Parameter _ExternalEmailAddress_ nicht verwenden, wird der _MicrosoftOnlineServicesID_ -Wert für die externe e-Mail-Adresse verwendet.</span><span class="sxs-lookup"><span data-stu-id="378ee-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="378ee-193">In diesem Beispiel wird ein e-Mail-Benutzer mit den folgenden Einstellungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="378ee-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="378ee-194">Der Name lautet JeffreyZeng, und der Anzeigename ist Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="378ee-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="378ee-195">Der Vorname ist "Jeffrey" und der Nachname ist "Zeng".</span><span class="sxs-lookup"><span data-stu-id="378ee-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="378ee-196">Der Alias ist "jeffreyz".</span><span class="sxs-lookup"><span data-stu-id="378ee-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="378ee-197">Die externe E-Mail-Adresse ist "jzeng@tailspintoys.com".</span><span class="sxs-lookup"><span data-stu-id="378ee-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="378ee-198">Der Konto Name lautet jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="378ee-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="378ee-199">Das Kennwort lautet "Pa$$word1".</span><span class="sxs-lookup"><span data-stu-id="378ee-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="378ee-200">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="378ee-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="378ee-201">Verwenden eigenständiger EoP PowerShell zum Ändern von e-Mail-Benutzern</span><span class="sxs-lookup"><span data-stu-id="378ee-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="378ee-202">Verwenden Sie die folgende Syntax, um vorhandene e-Mail-Benutzer in eigenständiger EoP PowerShell zu ändern:</span><span class="sxs-lookup"><span data-stu-id="378ee-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="378ee-203">In diesem Beispiel wird die externe E-Mail-Adresse für Pilar Pinella festgelegt.</span><span class="sxs-lookup"><span data-stu-id="378ee-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="378ee-204">In diesem Beispiel wird die Eigenschaft "Company" für alle E-Mail-Benutzer in "Contoso" geändert.</span><span class="sxs-lookup"><span data-stu-id="378ee-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="378ee-205">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="378ee-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="378ee-206">Verwenden eigenständiger EoP PowerShell zum Entfernen von e-Mail-Benutzern</span><span class="sxs-lookup"><span data-stu-id="378ee-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="378ee-207">Wenn Sie e-Mail-Benutzer in eigenständiger EoP PowerShell entfernen möchten, ersetzen Sie \<MailUserIdentity\> durch den Namen, den Alias oder den Kontonamen des e-Mail-Benutzers, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="378ee-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="378ee-208">In diesem Beispiel wird der e-Mail-Benutzer für Jeffrey Zeng entfernt.</span><span class="sxs-lookup"><span data-stu-id="378ee-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="378ee-209">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="378ee-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="378ee-210">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="378ee-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="378ee-211">Verwenden Sie eines der folgenden Verfahren, um zu überprüfen, ob Sie e-Mail-Benutzer in eigenständigen EoP erfolgreich erstellt, geändert oder entfernt haben:</span><span class="sxs-lookup"><span data-stu-id="378ee-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="378ee-212">Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.</span><span class="sxs-lookup"><span data-stu-id="378ee-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="378ee-213">Stellen Sie sicher, dass der e-Mail-Benutzer aufgelistet ist (oder nicht aufgeführt ist).</span><span class="sxs-lookup"><span data-stu-id="378ee-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="378ee-214">Wählen Sie den e-Mail-Benutzer aus, und zeigen Sie die Informationen im Detailbereich an, oder klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-AddIcon.png) , um die Einstellungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="378ee-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="378ee-215">Führen Sie in eigenständiger EoP PowerShell den folgenden Befehl aus, um zu überprüfen, ob der e-Mail-Benutzer aufgelistet ist (oder nicht aufgeführt ist):</span><span class="sxs-lookup"><span data-stu-id="378ee-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="378ee-216">Ersetzen \<MailUserIdentity\> Sie durch den Namen, den Alias oder den Kontonamen des e-Mail-Benutzers, und führen Sie die folgenden Befehle aus, um die Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="378ee-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="378ee-217">Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="378ee-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="378ee-218">In eigenständigen EoP steht die Verzeichnissynchronisierung für Kunden mit lokalem Active Directory zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="378ee-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="378ee-219">Sie können diese Konten mit Azure Active Directory (Azure AD) synchronisieren, wobei Kopien der Konten in der Cloud gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="378ee-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="378ee-220">Wenn Sie Ihre vorhandenen Benutzerkonten mit Azure Active Directory synchronisieren, können Sie diese Benutzer im Bereich **Empfänger** des Exchange Admin Centers (EAC) oder in der eigenständigen EoP PowerShell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="378ee-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="378ee-221">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="378ee-221">**Notes**:</span></span>

- <span data-ttu-id="378ee-222">Wenn Sie die Verzeichnissynchronisierung zum Verwalten Ihrer Empfänger verwenden, können Sie dennoch Benutzer im Microsoft 365 Admin Center hinzufügen und verwalten, Sie werden jedoch nicht mit Ihrer lokalen Active Directory synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="378ee-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="378ee-223">Dies liegt daran, dass die Verzeichnissynchronisierung nur Empfänger von Ihrem lokalen Active Directory zur Cloud synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="378ee-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="378ee-224">Für die folgenden Funktionen wird empfohlen, Verzeichnissynchronisierung zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="378ee-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="378ee-225">Listen **sicherer Absender in Outlook und blockierte Absender**: Wenn Sie mit dem Dienst synchronisiert werden, haben diese Listen Vorrang vor der Spamfilterung im Dienst.</span><span class="sxs-lookup"><span data-stu-id="378ee-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="378ee-226">Dadurch können Benutzer ihre eigene Liste sicherer Absender und blockierte Absender mit einzelnen Absender-und Domäneneinträgen verwalten.</span><span class="sxs-lookup"><span data-stu-id="378ee-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="378ee-227">Weitere Informationen finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="378ee-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="378ee-228">**Verzeichnisbasierte Edge-Blockierung (Blockierung)**: Weitere Informationen zu Blockierung finden Sie unter [Verwenden der verzeichnisbasierten Edge-Blockierung zum ablehnen von Nachrichten, die an ungültige Empfänger gesendet](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)werden.</span><span class="sxs-lookup"><span data-stu-id="378ee-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="378ee-229">**Endbenutzer Zugriff auf Quarantäne**: für den Zugriff auf Ihre isolierten Nachrichten benötigen Empfänger eine gültige Benutzer-ID und ein Kennwort im Dienst.</span><span class="sxs-lookup"><span data-stu-id="378ee-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="378ee-230">Weitere Informationen zur Quarantäne finden Sie unter [Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="378ee-230">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="378ee-231">**Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet)**: Wenn Sie die Verzeichnissynchronisierung verwenden, werden die vorhandenen Active Directory Benutzer und Gruppen automatisch in die Cloud hochgeladen, und Sie können dann Nachrichtenfluss Regeln erstellen, die auf bestimmte Benutzer und/oder Gruppen abzielen, ohne diese manuell im Dienst hinzufügen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="378ee-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="378ee-232">Bitte beachten Sie, dass [dynamische Verteilungsgruppen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) nicht über die Verzeichnissynchronisierung synchronisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="378ee-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="378ee-233">Rufen Sie die erforderlichen Berechtigungen ab, und bereiten Sie die Verzeichnissynchronisierung vor, wie unter [Was ist Hybrid Identität mit Azure Active Directory beschrieben?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="378ee-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="378ee-234">Synchronisieren von Verzeichnissen mit Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="378ee-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="378ee-235">Aktivieren Sie die Verzeichnissynchronisierung, wie unter [Azure AD Connect Sync: Understand and Customize Synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="378ee-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="378ee-236">Installieren und konfigurieren Sie einen lokalen Computer für die Ausführung von Aad Connect, wie unter [Voraussetzungen für Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="378ee-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="378ee-237">[Wählen Sie den Installationstyp aus, der für Azure AD Connect verwendet werden soll](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span><span class="sxs-lookup"><span data-stu-id="378ee-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="378ee-238">Express</span><span class="sxs-lookup"><span data-stu-id="378ee-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="378ee-239">Custom</span><span class="sxs-lookup"><span data-stu-id="378ee-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="378ee-240">Pass-Through-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="378ee-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="378ee-p121">Wenn Sie den Konfigurationsassistent für Azure Active Directory-Synchronisierungstool abschließen, wird in Ihrer Active Directory-Gesamtstruktur das Konto **MSOL_AD_SYNC** erstellt. Dieses Konto wird zum Lesen und Synchronisieren der lokalen Active Directory-Informationen verwendet. Damit die Verzeichnissynchronisierung ordnungsgemäß ausgeführt wird, müssen Sie sicherstellen, dass TCP 443 auf dem lokalen Verzeichnissynchronisierungsserver geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="378ee-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="378ee-244">Vergewissern Sie sich nach dem Konfigurieren der Synchronisierung, dass Aad Connect ordnungsgemäß synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="378ee-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="378ee-245">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Empfänger** \> **Kontakte**, und vergewissern Sie sich, dass die Liste der Benutzer in Ihrer lokalen Umgebung korrekt synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="378ee-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
