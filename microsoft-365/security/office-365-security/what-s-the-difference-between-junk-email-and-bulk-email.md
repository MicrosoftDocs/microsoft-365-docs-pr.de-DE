---
title: Worin besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: In diesem Thema wird der Unterschied zwischen Junk-e-Mails (Spam) und Massen-e-Mails sowie die zugehörigen Steuerelemente in Office 365 erläutert.
ms.openlocfilehash: 41dedd02febc40b73dc585961487f89bbc6db54a
ms.sourcegitcommit: c876d58b34454f211b50ae5d06f193c1a1e5c4ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2020
ms.locfileid: "43230956"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a><span data-ttu-id="c26f4-103">Worin besteht der Unterschied zwischen Junk- und Massen-E-Mails?</span><span class="sxs-lookup"><span data-stu-id="c26f4-103">What's the difference between junk email and bulk email?</span></span>

<span data-ttu-id="c26f4-104">Office 365 Kunden mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutz-Kunden (EoP) ohne Exchange Online Postfächer manchmal Fragen: "Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mails?"</span><span class="sxs-lookup"><span data-stu-id="c26f4-104">Office 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="c26f4-105">In diesem Thema wird der Unterschied erläutert und die Steuerelemente beschrieben, die in EoP zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="c26f4-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="c26f4-106">**Junk-e-** Mails sind Spam, bei denen es sich um unerwünschte und universell unerwünschte Nachrichten handelt (wenn Sie richtig identifiziert werden).</span><span class="sxs-lookup"><span data-stu-id="c26f4-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="c26f4-107">Standardmäßig lehnt der EoP Spam basierend auf der Reputation des Quell-e-Mail-Servers ab.</span><span class="sxs-lookup"><span data-stu-id="c26f4-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="c26f4-108">Wenn eine Nachricht die Quell-IP-Prüfung übergibt, wird Sie an die Spamfilterung gesendet.</span><span class="sxs-lookup"><span data-stu-id="c26f4-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="c26f4-109">Wenn die Nachricht durch Spamfilterung als Spam klassifiziert wird, wird die Nachricht (standardmäßig) an die beabsichtigten Empfänger übermittelt und in Ihren Junk-e-Mail-Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="c26f4-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="c26f4-110">Sie können die Aktionen konfigurieren, die für Spamfilter Urteile ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c26f4-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="c26f4-111">Anweisungen finden Sie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c26f4-111">For instructions, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="c26f4-112">Wenn Sie mit dem Spam Filterungs Urteil nicht einverstanden sind, können Sie Nachrichten, die Sie als Spam oder als nicht-Spam eingestuft haben, auf verschiedene Weise als Spam oder als nicht-Spam für Microsoft melden, wie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c26f4-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="c26f4-113">**Massen-e-** Mails (auch als _graue e-Mail_bezeichnet) ist schwieriger zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="c26f4-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="c26f4-114">Während Spam eine ständige Bedrohung darstellt, handelt es sich bei Massen-e-Mails häufig um einmalige Werbung oder Marketingnachrichten.</span><span class="sxs-lookup"><span data-stu-id="c26f4-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="c26f4-115">Einige Benutzer möchten Massen-e-Mails (und tatsächlich haben Sie sich absichtlich für den Empfang angemeldet), während andere Benutzer Massen-e-Mails als Spam einschätzen.</span><span class="sxs-lookup"><span data-stu-id="c26f4-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="c26f4-116">Einige Benutzer möchten beispielsweise Werbenachrichten von der Contoso Corporation oder Einladungen zu einer bevorstehenden Konferenz über Cyber Security erhalten, während andere Benutzer dieselben Nachrichten als Spam einstufen.</span><span class="sxs-lookup"><span data-stu-id="c26f4-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="c26f4-117">Weitere Informationen zur Identifizierung von Massen-e-Mails finden Sie unter [Bulk Complaint Level (BCL) in Office 365](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="c26f4-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="c26f4-118">Umgang mit Massen-E-Mails</span><span class="sxs-lookup"><span data-stu-id="c26f4-118">How to manage bulk email</span></span>

<span data-ttu-id="c26f4-119">Aufgrund der gemischten Reaktion auf Massen-e-Mails gibt es keine universellen Anleitungen für jede Organisation.</span><span class="sxs-lookup"><span data-stu-id="c26f4-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="c26f4-120">Anti-Spam-Richtlinien weisen einen standardmäßigen BCL-Schwellenwert auf, mit dem Massen-e-Mails als Spam identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="c26f4-120">Anti-spam policies have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="c26f4-121">Administratoren können den Schwellenwert erweitern oder verringern.</span><span class="sxs-lookup"><span data-stu-id="c26f4-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="c26f4-122">Weitere Informationen hierzu finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c26f4-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="c26f4-123">[Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c26f4-123">[Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="c26f4-124">EoP-Anti-Spam-Richtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="c26f4-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="c26f4-125">Eine weitere Option, die leicht übersehen werden kann: Wenn ein Benutzer über das Empfangen von Massen-e-Mails klagt, aber die Nachrichten von seriösen Absendern sind, die Spamfilterung in EoP übergeben, muss der Benutzer nach einer Option zum Abmelden in der Massen-e-Mail-Nachricht suchen.</span><span class="sxs-lookup"><span data-stu-id="c26f4-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
