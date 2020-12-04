---
title: Anzeigen und Freigeben von isolierten Nachrichten in freigegebenen Postfächern
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Benutzer können erfahren, wie Sie in Quarantäne befindliche Nachrichten anzeigen und bearbeiten, die an freigegebene Postfächer gesendet wurden, für die Sie Berechtigungen besitzen.
ms.openlocfilehash: 0c165395edc3a3032ece603cb8d9aac875443d7d
ms.sourcegitcommit: 26c2f01d6f88f6c288b04f9f08062d68dd1e67e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "49570942"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="d372a-103">Anzeigen und Freigeben von isolierten Nachrichten in freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="d372a-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="d372a-104">Die in diesem Artikel beschriebenen Features sind derzeit in der Vorschau, stehen nicht für alle zur Verfügung und können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d372a-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="d372a-105">Benutzer können isolierte Nachrichten verwalten, wenn Sie zu den Empfängern gehören, wie unter [Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer in EoP](find-and-release-quarantined-messages-as-a-user.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d372a-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="d372a-106">Was ist aber mit freigegebenen Postfächern, bei denen der Benutzer über die Berechtigungen "Vollzugriff" und "Senden als" oder "Senden im Auftrag von" für das Postfach verfügt, wie in [freigegebenen Exchange Online Postfächern](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="d372a-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="d372a-107">Die Möglichkeit für Benutzer, isolierte Nachrichten, die an ein freigegebenes Postfach gesendet wurden, zu verwalten, erforderte Administrators, damit die automatische Zuordnung für das freigegebene Postfach aktiviert bleibt (Sie ist standardmäßig aktiviert, wenn ein Administrator einem Benutzer Zugriff auf ein anderes Postfach gewährt).</span><span class="sxs-lookup"><span data-stu-id="d372a-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="d372a-108">Je nach Größe und Anzahl der Postfächer, auf die der Benutzer Zugriff hat, kann die Leistung jedoch beeinträchtigt werden, wenn Ausblicke versucht, *alle* Postfächer zu öffnen, auf die der Benutzer Zugriff hat.</span><span class="sxs-lookup"><span data-stu-id="d372a-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="d372a-109">Aus diesem Grund entscheiden sich viele Administratoren für das [Entfernen der automatischen Zuordnung für freigegebene Postfächer](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="d372a-109">For this reason, many admins choose to [remove automapping for shared mailboxes](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="d372a-110">Nun ist die automatische Zuordnung nicht mehr erforderlich, damit Benutzer isolierte Nachrichten verwalten können, die an freigegebene Postfächer gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="d372a-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="d372a-111">Es funktioniert einfach.</span><span class="sxs-lookup"><span data-stu-id="d372a-111">It just works.</span></span> <span data-ttu-id="d372a-112">Es gibt zwei verschiedene Methoden für den Zugriff auf isolierte Nachrichten, die an ein freigegebenes Postfach gesendet wurden:</span><span class="sxs-lookup"><span data-stu-id="d372a-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="d372a-113">Wenn der Administrator [Spambenachrichtigungen für Endbenutzer](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in Anti-Spam-Richtlinien aktiviert hat, können alle Benutzer, die Zugriff auf die Spambenachrichtigungen für Endbenutzer im freigegebenen Postfach haben, auf die Schaltfläche **überprüfen** in der Benachrichtigung klicken, um im Sicherheits & Compliance Center in Quarantäne zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="d372a-113">If the admin has [enabled end-user spam notifications](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="d372a-114">Beachten Sie, dass mit dieser Methode nur Benutzer isolierte Nachrichten verwalten können, die an das freigegebene Postfach gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="d372a-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="d372a-115">Benutzer können in diesem Kontext keine eigenen Quarantäne Nachrichten verwalten.</span><span class="sxs-lookup"><span data-stu-id="d372a-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="d372a-116">Der Benutzer kann [im Sicherheits & Compliance Center zur Quarantäne wechseln](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="d372a-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="d372a-117">Standardmäßig werden nur Nachrichten angezeigt, die an den Benutzer gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="d372a-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="d372a-118">Der Benutzer kann jedoch die **Sortierergebnisse** (die **Schaltfläche Nachrichten-ID** standardmäßig) in **Empfänger e-Mail-Adresse** ändern, die e-Mail-Adresse des freigegebenen Postfachs eingeben und dann auf **Aktualisieren** klicken, um die an das freigegebene Postfach gesendeten Nachrichten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d372a-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![Sortieren von isolierten Nachrichten nach Empfänger-e-Mail-Adresse.](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="d372a-120">Unabhängig von der Methode können Benutzer Verwirrung vermeiden, indem Sie die **Empfänger** Spalte für isolierte Nachrichten einschließen.</span><span class="sxs-lookup"><span data-stu-id="d372a-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="d372a-121">Die maximale Anzahl von anzuzeigenden Spalten ist 7, sodass der Benutzer auf **Spalten ändern**, eine vorhandene Spalte entfernen (beispielsweise **Richtlinientyp**), **Empfänger** auswählen und dann auf **Speichern** oder **als Standard speichern** klicken muss.</span><span class="sxs-lookup"><span data-stu-id="d372a-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![Entfernen Sie die Spalte Richtlinientyp, und fügen Sie die Spalte Empfänger der Quarantäne hinzu.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="d372a-123">Dabei ist Folgendes zu berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="d372a-123">Things to keep in mind</span></span>

- <span data-ttu-id="d372a-124">Der erste Benutzer, der in der isolierten Nachricht agiert, entscheidet über das Schicksal der Nachricht für jeden, der das freigegebene Postfach verwendet.</span><span class="sxs-lookup"><span data-stu-id="d372a-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="d372a-125">Wenn beispielsweise ein freigegebenes Postfach von zehn Benutzern verwendet wird und ein Benutzer entscheidet, die Quarantäne Nachricht zu löschen, wird die Nachricht für alle 10 Benutzer gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d372a-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="d372a-126">Wenn ein Benutzer sich entschließt, die Nachricht zu veröffentlichen, wird dieser ebenfalls für das freigegebene Postfach freigegeben und ist für alle anderen Benutzer des freigegebenen Postfachs zugänglich.</span><span class="sxs-lookup"><span data-stu-id="d372a-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="d372a-127">Wenn ein Benutzer mehrere in Quarantäne befindliche Nachrichten auswählt, die an das freigegebene Postfach gesendet wurden, werden die folgenden irreführenden Fehler zurückgegeben, wenn der Benutzer auf **Freigabe Meldungen** klickt oder **Nachrichten** im Flyout für **Massenaktionen** löscht:</span><span class="sxs-lookup"><span data-stu-id="d372a-127">Currently, if a user selects multiple quarantined messages that were sent to the shared mailbox, the following misleading errors are returned when the user clicks **Release messages** or **Delete messages** in the **Bulk actions** flyout:</span></span>

  > <span data-ttu-id="d372a-128">Sie verfügen nicht über die Berechtigung, alle ausgewählten isolierten Nachrichten freizugeben.</span><span class="sxs-lookup"><span data-stu-id="d372a-128">You do not have permission to release all selected quarantined messages.</span></span>
  >
  > <span data-ttu-id="d372a-129">Sie verfügen nicht über die Berechtigung zum Löschen aller ausgewählten isolierten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="d372a-129">You do not have permission to delete all selected quarantined messages.</span></span>

  <span data-ttu-id="d372a-130">Unabhängig vom Fehler wird die Aktion auf die Nachrichten angewendet, und der Fehler kann ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="d372a-130">Regardless of the error, the action is taken on the messages, and the error can be ignored.</span></span>

  ![Falscher Fehler beim Massen freigeben oder Löschen von isolierten Nachrichten, die an ein freigegebenes Postfach gesendet werden.](../../media/quarantine-bulk-action-error.png)

- <span data-ttu-id="d372a-132">Derzeit steht die Schaltfläche " **Absender blockieren** " im **Detail** -Flyout für in Quarantäne befindliche Nachrichten, die an das freigegebene Postfach gesendet wurden, nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d372a-132">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="d372a-133">Zum Verwalten von Nachrichten in Quarantäne für das freigegebene Postfach in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)muss der Endbenutzer das Cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) mit freigegebener e-Mail-Adresse des Postfachs für den Wert des Parameters _RecipientAddress_ verwenden, um die Nachrichten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d372a-133">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="d372a-134">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d372a-134">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="d372a-135">Anschließend kann der Endbenutzer eine isolierte Nachricht aus der Liste auswählen, um Sie anzuzeigen oder Maßnahmen für diese Aktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="d372a-135">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="d372a-136">In diesem Beispiel werden alle Nachrichten in Quarantäne angezeigt, die an das freigegebene Postfach gesendet wurden, und dann wird die erste Nachricht in der Liste aus der Quarantäne freigegeben (die erste Nachricht in der Liste ist 0, die zweite ist 1 usw.).</span><span class="sxs-lookup"><span data-stu-id="d372a-136">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="d372a-137">Ausführliche Informationen zu Syntax und Parametern finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="d372a-137">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="d372a-138">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="d372a-138">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="d372a-139">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="d372a-139">Get-QuarantineMessageHeader</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="d372a-140">Vorschau-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="d372a-140">Preview-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="d372a-141">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="d372a-141">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
