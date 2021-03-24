---
title: Spambenachrichtigungen für Endbenutzer in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich in Exchange Online Protection (EOP) über Spambenachrichtigungen für Endbenutzer für isolierte Nachrichten informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9cff91be399bd98eb7e6e5a2a6d91a4a8bb602ec
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061864"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="2342e-103">Verwenden von Spambenachrichtigungen von Benutzern zum Veröffentlichen und Melden isolierter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="2342e-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2342e-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="2342e-104">**Applies to**</span></span>
- [<span data-ttu-id="2342e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2342e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2342e-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="2342e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2342e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2342e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2342e-108">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="2342e-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="2342e-109">Weitere Informationen finden Sie unter [Quarantined messages in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="2342e-109">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="2342e-110">Standardmäßig sind Spambenachrichtigungen für Endbenutzer in Antispamrichtlinien deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2342e-110">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="2342e-111">Wenn ein Administrator [Spambenachrichtigungen](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)für Endbenutzer aktiviert, erhalten Empfänger (einschließlich freigegebener Postfächer mit aktivierter automatischemMapping) regelmäßig Benachrichtigungen zu ihren Nachrichten, die als Spam, Massen-E-Mail oder (ab April 2020) Phishing isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="2342e-111">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="2342e-112">Bei freigegebenen Postfächern werden Spambenachrichtigungen für Endbenutzer nur für Benutzer unterstützt, denen die Berechtigung FullAccess für das freigegebene Postfach erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="2342e-112">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="2342e-113">Weitere Informationen finden Sie unter [Verwenden der EAC zum Bearbeiten der freigegebenen Postfachdelegierung](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span><span class="sxs-lookup"><span data-stu-id="2342e-113">For more information, see [Use the EAC to edit shared mailbox delegation](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="2342e-114">Spambenachrichtigungen für Endbenutzer werden für Gruppen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2342e-114">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="2342e-115">Nachrichten, die als Phishing mit hoher Sicherheit, Schadsoftware oder durch Nachrichtenflussregeln (auch transport rules bezeichnet) isoliert wurden, stehen nur Administratoren zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2342e-115">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="2342e-116">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="2342e-116">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="2342e-117">Eine Spambenachrichtigung für Endbenutzer enthält die folgenden Informationen für jede isolierte Nachricht:</span><span class="sxs-lookup"><span data-stu-id="2342e-117">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="2342e-118">**Sender**: Der Sendename und die E-Mail-Adresse der isolierten Nachricht.</span><span class="sxs-lookup"><span data-stu-id="2342e-118">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="2342e-119">**Betreff**: Der Betreffzeilentext der isolierten Nachricht.</span><span class="sxs-lookup"><span data-stu-id="2342e-119">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="2342e-120">**Date**: Das Datum und die Uhrzeit (in UTC), zu der die Nachricht isoliert wurde.</span><span class="sxs-lookup"><span data-stu-id="2342e-120">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="2342e-121">**Absender blockieren**: Klicken Sie auf diesen Link, um den Absender ihrer Liste blockierter Absender hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2342e-121">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="2342e-122">Weitere Informationen finden Sie unter [Blockieren eines E-Mail-Absenders.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)</span><span class="sxs-lookup"><span data-stu-id="2342e-122">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="2342e-123">**Release**: Für Spamnachrichten (keine Phishing)-Nachrichten können Sie die Nachricht hier veröffentlichen, ohne das Security & Compliance Center unter Quarantäne zu stellen.</span><span class="sxs-lookup"><span data-stu-id="2342e-123">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="2342e-124">**Review**: Klicken Sie auf diesen Link, um zu Quarantäne im Security & Compliance Center zu wechseln, in dem Sie (je nachdem, warum die Nachricht isoliert wurde) Ihre isolierten Nachrichten anzeigen, veröffentlichen, löschen oder melden können.</span><span class="sxs-lookup"><span data-stu-id="2342e-124">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="2342e-125">Weitere Informationen finden Sie unter [Suchen und Veröffentlichen isolierter Nachrichten als Benutzer in EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="2342e-125">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Beispiel für Spambenachrichtigungen für Endbenutzer](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="2342e-127">Ein blockierter Absender kann Ihnen weiterhin E-Mails senden.</span><span class="sxs-lookup"><span data-stu-id="2342e-127">A blocked sender can still send you mail.</span></span> <span data-ttu-id="2342e-128">Alle Nachrichten von diesem Absender, die es in Ihr Postfach senden, werden sofort in den Junk-E-Mail-Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="2342e-128">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="2342e-129">Zukünftige Nachrichten von diesem Absender werden in Ihren Junk-E-Mail-Ordner oder in die Endbenutzerquarantäne verschoben.</span><span class="sxs-lookup"><span data-stu-id="2342e-129">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="2342e-130">Wenn Sie diese Nachrichten bei der Ankunft löschen möchten, anstatt sie zu quarantinieren, verwenden Sie Nachrichtenflussregeln [(auch](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) als Transportregeln bezeichnet), um die Nachrichten bei der Ankunft zu löschen.</span><span class="sxs-lookup"><span data-stu-id="2342e-130">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>