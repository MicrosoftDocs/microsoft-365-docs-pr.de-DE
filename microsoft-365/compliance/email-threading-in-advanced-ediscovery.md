---
title: E-Mail-Threading
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
ms.assetid: ''
description: ''
ms.openlocfilehash: 7bfae202886d4c1af5914f4b49d0e4d528b8975d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081510"
---
# <a name="email-threading"></a><span data-ttu-id="a6d5e-102">E-Mail-Threading</span><span class="sxs-lookup"><span data-stu-id="a6d5e-102">Email threading</span></span>

<span data-ttu-id="a6d5e-103">Ziehen Sie eine e-Mail-Unterhaltung in Frage, die schon eine Weile vorgeht.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-103">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="a6d5e-104">In den meisten Fällen enthält die letzte e-Mail im Thread die Inhalte aller vorherigen e-Mails. Wenn Sie die letzte e-Mail überprüfen, erhalten Sie einen vollständigen Kontext der Unterhaltung, die im Thread aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-104">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="a6d5e-105">E-Mail-Threading identifiziert solche e-Mails, sodass Bearbeiter einen Bruchteil der gesammelten Dokumente überprüfen können, ohne dass ein Kontext verloren geht.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-105">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="a6d5e-106">Was bewirkt das e-Mail-Threading?</span><span class="sxs-lookup"><span data-stu-id="a6d5e-106">What does email threading do?</span></span>

<span data-ttu-id="a6d5e-107">E-Mail-Threading analysiert jede e-Mail und desconstructs Sie an einzelne Nachrichten; jede e-Mail ist eine Kette einzelner Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-107">Email threading parses each email and desconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="a6d5e-108">Anschließend werden alle e-Mails in der Überprüfungsgruppe analysiert, um festzustellen, ob eine e-Mail über eindeutige Inhalte verfügt oder ob die Kette vollständig in einer anderen e-Mail enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-108">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="a6d5e-109">Am Ende werden e-Mails in vier Kategorien unterteilt:</span><span class="sxs-lookup"><span data-stu-id="a6d5e-109">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="a6d5e-110">**Inclusive**: die letzte Nachricht in der e-Mail weist eindeutige Inhalte auf, und die e-Mail enthält alle Anlagen, die in anderen e-Mails enthalten waren, in denen der Inhalt vollständig in dieser e-Mail enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-110">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>


- <span data-ttu-id="a6d5e-111">**Inclusive minus**: die letzte Nachricht in der e-Mail hat eindeutige Inhalte, aber die e-Mail enthält nicht einige der Anlagen, die in anderen e-Mails enthalten waren, in denen der Inhalt vollständig in dieser e-Mail enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-111">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="a6d5e-112">**Inklusive Kopie**: eine exakte Kopie einer inclusive/inklusive minus-e-Mail</span><span class="sxs-lookup"><span data-stu-id="a6d5e-112">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="a6d5e-113">**None**: der Inhalt dieser e-Mail-Nachricht ist vollständig in mindestens einer e-Mail enthalten, die als inclusive/inclusive minus gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-113">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="a6d5e-114">Wie unterscheidet er sich von den Unterhaltungen in Outlook?</span><span class="sxs-lookup"><span data-stu-id="a6d5e-114">How is it different from conversations in Outlook?</span></span>
<span data-ttu-id="a6d5e-115">Dies klingt auf einen Blick ähnlich wie Konversations Gruppierungen in Outlook.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-115">At a glance, this sounds very similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="a6d5e-116">Es gibt jedoch einige wichtige Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-116">However, there are some important distinctions.</span></span> <span data-ttu-id="a6d5e-117">Halten Sie sich an eine e-Mail-Unterhaltung, die in zwei Unterhaltungen verzweigt wurde. Beispielsweise hat jemand auf eine e-Mail geantwortet, die nicht die neueste in der Unterhaltung ist, sodass die letzten beiden e-Mails in der Unterhaltung über eindeutige Inhalte verfügen.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-117">Consider an email conversation that got forked into two conversation; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="a6d5e-118">Outlook würde die e-Mails weiterhin in einer einzigen Unterhaltung gruppieren. Wenn Sie nur die letzte e-Mail lesen, würde das Fehlen des Kontexts der vorletzte e-Mail bedeuten, die auch eindeutige Inhalte enthält.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-118">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="a6d5e-119">Da das e-Mail-Threading jede e-Mail in einzelne Komponenten analysiert und diese vergleicht, würde das e-Mail-Threading beide letzten e-Mails als inklusivzeichen markieren, um sicherzustellen, dass Sie keinen Kontext verpassen, solange Sie alle als inklusiv markierten e-Mails lesen.</span><span class="sxs-lookup"><span data-stu-id="a6d5e-119">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusives, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>