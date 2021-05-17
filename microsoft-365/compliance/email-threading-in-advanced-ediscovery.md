---
title: E-Mail-Threading in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Beim Durchführen einer Advanced eDiscovery analysiert das E-Mail-Threading eine E-Mail-Unterhaltung und trennt jede Nachricht in verschiedene Kategorien.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285561"
---
# <a name="email-threading-in-advanced-ediscovery"></a><span data-ttu-id="519b9-103">E-Mail-Threading in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="519b9-103">Email threading in Advanced eDiscovery</span></span>

<span data-ttu-id="519b9-104">Betrachten Sie eine E-Mail-Unterhaltung, die seit einer Weile läuft.</span><span class="sxs-lookup"><span data-stu-id="519b9-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="519b9-105">In den meisten Fällen enthält die letzte E-Mail im Thread den Inhalt aller vorherigen E-Mails. Wenn Sie die letzte E-Mail überprüfen, erhalten Sie einen vollständigen Kontext der Unterhaltung, die im Thread passiert ist.</span><span class="sxs-lookup"><span data-stu-id="519b9-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="519b9-106">Durch E-Mail-Threading werden solche E-Mails identifiziert, sodass Prüfer einen Bruchteil der gesammelten Dokumente überprüfen können, ohne einen Kontext zu verlieren.</span><span class="sxs-lookup"><span data-stu-id="519b9-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="519b9-107">Was macht E-Mail-Threading?</span><span class="sxs-lookup"><span data-stu-id="519b9-107">What does email threading do?</span></span>

<span data-ttu-id="519b9-108">E-Mail-Threading analysiert jede E-Mail und destrukturiert sie an einzelne Nachrichten. Jede E-Mail ist eine Kette von einzelnen Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="519b9-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="519b9-109">Anschließend werden alle E-Mails im Überprüfungssatz analysiert, um festzustellen, ob eine E-Mail eindeutigen Inhalt hat oder ob die Kette vollständig in einer anderen E-Mail enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="519b9-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="519b9-110">Am Ende werden E-Mails in vier Kategorien unterteilt:</span><span class="sxs-lookup"><span data-stu-id="519b9-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="519b9-111">**Inklusiv**: Die letzte Nachricht der E-Mail hat einen eindeutigen Inhalt, und die E-Mail enthält alle Anhänge, die Teil anderer E-Mails waren, deren Inhalt vollständig in dieser E-Mail angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="519b9-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="519b9-112">**Inklusiv – Minus**: Die letzte Nachricht in der E-Mail hat einen eindeutigen Inhalt, aber einige Anhänge, die Teil anderer E-Mails waren, deren Inhalt vollständig in dieser E-Mail angezeigt wird, sind nicht in dieser E-Mail enthalten.</span><span class="sxs-lookup"><span data-stu-id="519b9-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="519b9-113">**Inklusiv – Kopie**: Eine genaue Kopie einer als „Inklusiv“ bzw. „Inklusiv – Minus“ gekennzeichneten E-Mail.</span><span class="sxs-lookup"><span data-stu-id="519b9-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="519b9-114">**Ohne**: Der Inhalt dieser E-Mail ist vollständig in mindestens einer als „Inklusiv“ bzw. „Inklusiv – Minus“ gekennzeichneten E-Mail enthalten.</span><span class="sxs-lookup"><span data-stu-id="519b9-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="519b9-115">Wie unterscheiden sie sich von Unterhaltungen in Outlook?</span><span class="sxs-lookup"><span data-stu-id="519b9-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="519b9-116">Auf einen Blick klingt dies ähnlich wie bei Unterhaltungsgruppen in Outlook.</span><span class="sxs-lookup"><span data-stu-id="519b9-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="519b9-117">Es gibt jedoch einige wichtige Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="519b9-117">However, there are some important distinctions.</span></span> <span data-ttu-id="519b9-118">Stellen Sie sich eine E-Mail-Unterhaltung vor, die in zwei Unterhaltungen gegabelt wurde. Beispielsweise hat jemand auf eine E-Mail geantwortet, die nicht die neueste in der Unterhaltung ist, sodass die letzten beiden E-Mails in der Unterhaltung jeweils eindeutige Inhalte haben.</span><span class="sxs-lookup"><span data-stu-id="519b9-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="519b9-119">Outlook die E-Mails weiterhin in einer einzigen Unterhaltung gruppieren. Wenn Sie nur die letzte E-Mail lesen, würde der Kontext der vorletzten E-Mail fehlen, die auch eindeutige Inhalte enthält.</span><span class="sxs-lookup"><span data-stu-id="519b9-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="519b9-120">Da das E-Mail-Threading jede E-Mail in einzelne Komponenten analysiert und vergleicht, würde das E-Mail-Threading die beiden letzten E-Mails als inklusive e-Mail markieren, um sicherzustellen, dass Sie keinen Kontext verpassen, solange Sie alle als inklusiv markierten E-Mails lesen.</span><span class="sxs-lookup"><span data-stu-id="519b9-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
