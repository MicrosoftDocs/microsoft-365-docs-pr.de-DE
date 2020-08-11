---
title: Spambenachrichtigungen für Endbenutzer in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
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
description: Administratoren können Informationen zu Endbenutzer-Spambenachrichtigungen für isolierte Nachrichten in Exchange Online Protection (EoP) erhalten.
ms.openlocfilehash: b196a9e11d54d9d86acc991ba877279f1fa3d115
ms.sourcegitcommit: 51f040a4edb8dd52521a5d7b0f7a975986a1af10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46608299"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="1a91e-103">Verwenden von Spambenachrichtigungen für Benutzer zum Freigeben und melden von Nachrichten in Quarantäne</span><span class="sxs-lookup"><span data-stu-id="1a91e-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="1a91e-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="1a91e-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="1a91e-105">Weitere Informationen finden Sie unter [Quarantined Messages in EoP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="1a91e-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="1a91e-106">Standardmäßig sind Spambenachrichtigungen für Endbenutzer in Anti-Spam-Richtlinien deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1a91e-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="1a91e-107">Wenn ein Administrator [Spambenachrichtigungen für Endbenutzer aktiviert](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), erhalten die Empfänger (einschließlich freigegebener Postfächer mit aktivierter Automapping) regelmäßig Benachrichtigungen über Ihre Nachrichten, die als Spam, Massen-e-Mails oder (ab April 2020) als Phishing-Nachricht isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="1a91e-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="1a91e-108">Nachrichten, die als vertrauenswürdiges Phishing, Schadsoftware oder Nachrichtenfluss Regeln (auch bekannt als Transportregeln) unter Quarantäne gestellt wurden, stehen nur Administratoren zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1a91e-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="1a91e-109">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="1a91e-109">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="1a91e-110">Eine spambenachrichtigung für Endbenutzer enthält für jede isolierte Nachricht die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="1a91e-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="1a91e-111">**Sender**: der Absender Name und die e-Mail-Adresse der isolierten Nachricht.</span><span class="sxs-lookup"><span data-stu-id="1a91e-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="1a91e-112">**Betreff**: der Text der Betreffzeile der isolierten Nachricht.</span><span class="sxs-lookup"><span data-stu-id="1a91e-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="1a91e-113">**Date**: das Datum und die Uhrzeit (in UTC), in denen die Nachricht isoliert wurde.</span><span class="sxs-lookup"><span data-stu-id="1a91e-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="1a91e-114">**Absender blockieren**: Klicken Sie auf diesen Link, um den Absender der Liste blockierter Absender hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1a91e-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="1a91e-115">Weitere Informationen finden Sie unter [Blockieren eines e-Mail-Absenders](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="1a91e-115">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="1a91e-116">**Release**: bei Spamnachrichten (keine Phishing-Nachrichten) können Sie die Nachricht hier freigeben, ohne das Sicherheits & Compliance Center zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="1a91e-116">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="1a91e-117">**Review**: Klicken Sie auf diesen Link, um im Security & Compliance Center auf Quarantäne zu wechseln, wo Sie (je nachdem, warum die Nachricht unter Quarantäne gestellt wurde) die isolierten Nachrichten anzeigen, freigeben, löschen oder melden können.</span><span class="sxs-lookup"><span data-stu-id="1a91e-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="1a91e-118">Weitere Informationen finden Sie unter [Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer in EoP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="1a91e-118">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Beispiel-spambenachrichtigung für Endbenutzer](../../media/end-user-spam-notification.png)
