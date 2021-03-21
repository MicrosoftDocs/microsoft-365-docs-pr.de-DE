---
title: Anzeigen und Veröffentlichen isolierter Nachrichten aus freigegebenen Postfächern
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Benutzer können erfahren, wie sie Nachrichten in Quarantäne anzeigen und verwenden, die an freigegebene Postfächer gesendet wurden, für die sie über Berechtigungen verfügen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cb42c887df384a418ab01e3a232cdb1f4a7b6e19
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922328"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="93994-103">Anzeigen und Veröffentlichen isolierter Nachrichten aus freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="93994-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="93994-104">Die in diesem Artikel beschriebenen Features befinden sich derzeit in Der Vorschau, sind nicht für alle verfügbar und können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="93994-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="93994-105">Benutzer können isolierte Nachrichten dort verwalten, wo sie einer der Empfänger sind, wie unter Suchen und Veröffentlichen von isolierten Nachrichten als Benutzer [in EOP beschrieben.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="93994-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="93994-106">Aber wie sieht es mit freigegebenen Postfächern aus, bei denen der Benutzer über vollzugriffs- und Sendeberechtigungen für das Postfach verfügt, wie unter Freigegebene Postfächer [in Exchange Online beschrieben?](/exchange/collaboration-exo/shared-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="93994-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="93994-107">Zuvor mussten Administratoren die Möglichkeit, isolierte Nachrichten, die an ein freigegebenes Postfach gesendet wurden, für das freigegebene Postfach aktiviert lassen (es ist standardmäßig aktiviert, wenn ein Administrator einem Benutzer Zugriff auf ein anderes Postfach gewährt).</span><span class="sxs-lookup"><span data-stu-id="93994-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="93994-108">Je nach Größe und Anzahl der Postfächer, auf die der Benutzer Zugriff hat,  kann die Leistung jedoch darunter leiden, wenn Outlook versucht, alle Postfächer zu öffnen, auf die der Benutzer Zugriff hat.</span><span class="sxs-lookup"><span data-stu-id="93994-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="93994-109">Aus diesem Grund entscheiden sich viele Administratoren dafür, die [automatischeMapping für freigegebene Postfächer zu entfernen.](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)</span><span class="sxs-lookup"><span data-stu-id="93994-109">For this reason, many admins choose to [remove automapping for shared mailboxes](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="93994-110">Jetzt ist das automatischeMapping nicht mehr erforderlich, damit Benutzer isolierte Nachrichten verwalten können, die an freigegebene Postfächer gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="93994-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="93994-111">Es funktioniert einfach.</span><span class="sxs-lookup"><span data-stu-id="93994-111">It just works.</span></span> <span data-ttu-id="93994-112">Es gibt zwei verschiedene Methoden für den Zugriff auf isolierte Nachrichten, die an ein freigegebenes Postfach gesendet wurden:</span><span class="sxs-lookup"><span data-stu-id="93994-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="93994-113">Wenn der Administrator Spambenachrichtigungen für Endbenutzer [in](configure-your-spam-filter-policies.md) Antispamrichtlinien aktiviert hat, kann jeder Benutzer, der  Zugriff auf die Spambenachrichtigungen für Endbenutzer im freigegebenen Postfach hat, auf die Schaltfläche Überprüfen in der Benachrichtigung klicken, um im Security & Compliance Center in Quarantäne zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="93994-113">If the admin has [enabled end-user spam notifications](configure-your-spam-filter-policies.md) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="93994-114">Beachten Sie, dass diese Methode benutzern nur die Verwaltung isolierter Nachrichten ermöglicht, die an das freigegebene Postfach gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="93994-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="93994-115">Benutzer können in diesem Kontext keine eigenen Quarantänenachrichten verwalten.</span><span class="sxs-lookup"><span data-stu-id="93994-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="93994-116">Der Benutzer kann [zur Quarantäne im Security & Compliance Center wechseln.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="93994-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="93994-117">Standardmäßig werden nur Nachrichten angezeigt, die an den Benutzer gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="93994-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="93994-118">Der Benutzer kann jedoch die Sortierergebnisse **(standardmäßig** die Schaltfläche  **Nachrichten-ID)** in Empfänger-E-Mail-Adresse **ändern,** die E-Mail-Adresse des freigegebenen Postfachs eingeben und dann auf Aktualisieren klicken, um die isolierten Nachrichten zu sehen, die an das freigegebene Postfach gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="93994-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![Sortieren von isolierten Nachrichten nach E-Mail-Adresse des Empfängers.](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="93994-120">Unabhängig von der Methode können Benutzer Verwirrung vermeiden, indem sie die **Spalte Empfänger** für isolierte Nachrichten verwenden.</span><span class="sxs-lookup"><span data-stu-id="93994-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="93994-121">Die maximale Anzahl der anzuzeigende Spalten ist 7. Daher muss der Benutzer auf Spalten **ändern,** eine vorhandene Spalte entfernen (z. B. Richtlinientyp), Empfänger auswählen und dann auf **Speichern** oder Als Standard speichern **klicken.** </span><span class="sxs-lookup"><span data-stu-id="93994-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![Entfernen Sie die Spalte Richtlinientyp, und fügen Sie die Spalte Empfänger zur Quarantäne hinzu.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="93994-123">Dabei ist Folgendes zu berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="93994-123">Things to keep in mind</span></span>

- <span data-ttu-id="93994-124">Der erste Benutzer, der auf die isolierte Nachricht eingreift, bestimmt das Schicksal der Nachricht für alle Benutzer, die das freigegebene Postfach verwenden.</span><span class="sxs-lookup"><span data-stu-id="93994-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="93994-125">Wenn beispielsweise 10 Benutzer auf ein freigegebenes Postfach zugreifen und ein Benutzer die Quarantänenachricht löschen will, wird die Nachricht für alle 10 Benutzer gelöscht.</span><span class="sxs-lookup"><span data-stu-id="93994-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="93994-126">Wenn sich ein Benutzer entschließen sollte, die Nachricht frei zu geben, wird sie für das freigegebene Postfach freigegeben und ist für alle anderen Benutzer des freigegebenen Postfachs zugänglich.</span><span class="sxs-lookup"><span data-stu-id="93994-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="93994-127">Derzeit ist die **Schaltfläche Absender blockieren** im **Flyout Details** für isolierte Nachrichten, die an das freigegebene Postfach gesendet wurden, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="93994-127">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="93994-128">Zum Verwalten isolierter Nachrichten für das freigegebene Postfach in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)muss der Endbenutzer das [Cmdlet Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) mit freigegebener Postfach-E-Mail-Adresse für den Wert des _Parameters RecipientAddress_ verwenden, um die Nachrichten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="93994-128">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="93994-129">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="93994-129">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="93994-130">Anschließend kann der Endbenutzer eine isolierte Nachricht aus der Liste auswählen, um eine Aktion zu sehen oder zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="93994-130">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="93994-131">In diesem Beispiel werden alle isolierten Nachrichten angezeigt, die an das freigegebene Postfach gesendet wurden, und dann die erste Nachricht in der Liste aus der Quarantäne freigegeben (die erste Nachricht in der Liste ist 0, die zweite ist 1 und so weiter).</span><span class="sxs-lookup"><span data-stu-id="93994-131">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="93994-132">Ausführliche Informationen zu Syntax und Parametern finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="93994-132">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="93994-133">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="93994-133">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="93994-134">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="93994-134">Get-QuarantineMessageHeader</span></span>](/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="93994-135">Preview-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="93994-135">Preview-QuarantineMessage</span></span>](/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="93994-136">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="93994-136">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)