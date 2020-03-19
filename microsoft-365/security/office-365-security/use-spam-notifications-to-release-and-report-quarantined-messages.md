---
title: Spambenachrichtigungen für Endbenutzer in Office 36
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
description: Wenn ein Administrator Spambenachrichtigungen für Endbenutzer in Anti-Spam-Richtlinien aktiviert, erhalten die Nachrichtenempfänger regelmäßig Benachrichtigungen über Ihre isolierten Nachrichten.
ms.openlocfilehash: 67dbf311c37ae61c007b78110522033d79c0b161
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857145"
---
# <a name="end-user-spam-notifications-in-office-365"></a><span data-ttu-id="94f42-103">Spambenachrichtigungen für Endbenutzer in Office 365</span><span class="sxs-lookup"><span data-stu-id="94f42-103">End-user spam notifications in Office 365</span></span>

<span data-ttu-id="94f42-104">In Quarantäne werden potenziell gefährliche oder unerwünschte Nachrichten in Office 365 Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="94f42-104">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="94f42-105">Weitere Informationen finden Sie unter [Quarantine in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="94f42-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="94f42-106">Standardmäßig sind Spambenachrichtigungen für Endbenutzer in Anti-Spam-Richtlinien deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="94f42-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="94f42-107">Wenn ein Administrator [Spambenachrichtigungen für Endbenutzer aktiviert](configure-your-spam-filter-policies.md), erhalten die Nachrichtenempfänger regelmäßig Benachrichtigungen über Ihre Nachrichten, die als Spam, Massen-e-Mails oder (ab April 2020) als Phishing isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="94f42-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md), message recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="94f42-108">Im Oktober 2019 wurde die Möglichkeit, isolierte Nachrichten direkt von Endbenutzer-Spambenachrichtigungen freizugeben, entfernt.</span><span class="sxs-lookup"><span data-stu-id="94f42-108">In October 2019, we removed the ability to release quarantined messages directly from end-user spam notifications.</span></span> <span data-ttu-id="94f42-109">Stattdessen können Benutzer nun zum Office 365 Security & Compliance Center wechseln, um Ihre isolierten Nachrichten freizugeben (entweder direkt oder durch Klicken auf **überprüfen** in der Benachrichtigung).</span><span class="sxs-lookup"><span data-stu-id="94f42-109">Instead, users can now go to the Office 365 Security & Compliance Center to release their quarantined messages (either directly, or by clicking **Review** in the notification).</span></span> <span data-ttu-id="94f42-110">Weitere Informationen finden Sie unter [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="94f42-110">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span> <br/><br/> <span data-ttu-id="94f42-111">Nachrichten, die als vertrauenswürdiges Phishing, Schadsoftware oder Nachrichtenfluss Regeln (auch bekannt als Transportregeln) unter Quarantäne gestellt wurden, stehen nur Administratoren zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="94f42-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="94f42-112">Weitere Informationen finden Sie unter [Suchen und Freigeben von isolierten Nachrichten als Administrator in Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span><span class="sxs-lookup"><span data-stu-id="94f42-112">For more information, see [Find and release quarantined messages as an admin in Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>

<span data-ttu-id="94f42-113">Eine spambenachrichtigung für Endbenutzer enthält für jede isolierte Nachricht die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="94f42-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="94f42-114">**Sender**: der Absender Name und die e-Mail-Adresse der isolierten Nachricht.</span><span class="sxs-lookup"><span data-stu-id="94f42-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="94f42-115">**Betreff**: der Text der Betreffzeile der isolierten Nachricht.</span><span class="sxs-lookup"><span data-stu-id="94f42-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="94f42-116">**Date**: das Datum und die Uhrzeit (in UTC), in denen die Nachricht isoliert wurde.</span><span class="sxs-lookup"><span data-stu-id="94f42-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="94f42-117">**Absender blockieren**: Klicken Sie auf diesen Link, um den Absender der Liste blockierter Absender hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="94f42-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span>

- <span data-ttu-id="94f42-118">**Review**: Klicken Sie auf diesen Link, um die Quarantäne im Security & Compliance Center zu wechseln, in der Sie Ihre isolierten Nachrichten freigeben, löschen oder melden können.</span><span class="sxs-lookup"><span data-stu-id="94f42-118">**Review**: Click this link to go the the Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span>

![Beispiel-spambenachrichtigung für Endbenutzer](../../media/end-user-spam-notification.png)
