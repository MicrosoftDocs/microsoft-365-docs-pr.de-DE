---
title: Was &apos; ist der Unterschied zwischen Junk-e-Mails und Massen-e-Mails?
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
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die Unterschiede zwischen Junk-e-Mails (Spam) und Massen-e-Mails (Gray Mail) in Exchange Online Protection (EoP) informieren.
ms.openlocfilehash: c1f5ca724f7a41d9fc11ed0c93f52a79a6ecc8e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819436"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="590b0-103">Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mails in EoP?</span><span class="sxs-lookup"><span data-stu-id="590b0-103">What's the difference between junk email and bulk email in EOP?</span></span>

<span data-ttu-id="590b0-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer Fragen Kunden manchmal: "Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mails?"</span><span class="sxs-lookup"><span data-stu-id="590b0-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="590b0-105">In diesem Thema wird der Unterschied erläutert und die Steuerelemente beschrieben, die in EoP zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="590b0-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="590b0-106">**Junk-e-** Mails sind Spam, bei denen es sich um unerwünschte und universell unerwünschte Nachrichten handelt (wenn Sie richtig identifiziert werden).</span><span class="sxs-lookup"><span data-stu-id="590b0-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="590b0-107">Standardmäßig lehnt der EoP Spam basierend auf der Reputation des Quell-e-Mail-Servers ab.</span><span class="sxs-lookup"><span data-stu-id="590b0-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="590b0-108">Wenn eine Nachricht die Quell-IP-Prüfung übergibt, wird Sie an die Spamfilterung gesendet.</span><span class="sxs-lookup"><span data-stu-id="590b0-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="590b0-109">Wenn die Nachricht durch Spamfilterung als Spam klassifiziert wird, wird die Nachricht (standardmäßig) an die beabsichtigten Empfänger übermittelt und in Ihren Junk-e-Mail-Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="590b0-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="590b0-110">Sie können die Aktionen konfigurieren, die für Spamfilter Urteile ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="590b0-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="590b0-111">Anweisungen finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="590b0-111">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="590b0-112">Wenn Sie mit dem Spam Filterungs Urteil nicht einverstanden sind, können Sie Nachrichten, die Sie als Spam oder als nicht-Spam eingestuft haben, auf verschiedene Weise als Spam oder als nicht-Spam für Microsoft melden, wie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="590b0-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="590b0-113">**Massen-e-** Mails (auch als _graue e-Mail_bezeichnet) ist schwieriger zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="590b0-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="590b0-114">Während Spam eine ständige Bedrohung darstellt, handelt es sich bei Massen-e-Mails häufig um einmalige Werbung oder Marketingnachrichten.</span><span class="sxs-lookup"><span data-stu-id="590b0-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="590b0-115">Einige Benutzer möchten Massen-e-Mails (und tatsächlich haben Sie sich absichtlich für den Empfang angemeldet), während andere Benutzer Massen-e-Mails als Spam einschätzen.</span><span class="sxs-lookup"><span data-stu-id="590b0-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="590b0-116">Einige Benutzer möchten beispielsweise Werbenachrichten von der Contoso Corporation oder Einladungen zu einer bevorstehenden Konferenz über Cyber Security erhalten, während andere Benutzer dieselben Nachrichten als Spam einstufen.</span><span class="sxs-lookup"><span data-stu-id="590b0-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="590b0-117">Weitere Informationen zur Identifizierung von Massen-e-Mails finden Sie unter [Bulk Complaint Level (BCL) in EoP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="590b0-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="590b0-118">Umgang mit Massen-E-Mails</span><span class="sxs-lookup"><span data-stu-id="590b0-118">How to manage bulk email</span></span>

<span data-ttu-id="590b0-119">Aufgrund der gemischten Reaktion auf Massen-e-Mails gibt es keine universellen Anleitungen für jede Organisation.</span><span class="sxs-lookup"><span data-stu-id="590b0-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="590b0-120">Anti-Spam-Richtlinien haben einen standardmäßigen BCL-Schwellenwert, der verwendet wird, um Massen-e-Mails als Spam zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="590b0-120">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="590b0-121">Administratoren können den Schwellenwert erweitern oder verringern.</span><span class="sxs-lookup"><span data-stu-id="590b0-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="590b0-122">Weitere Informationen hierzu finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="590b0-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="590b0-123">[Konfigurieren von Anti-Spam-Richtlinien in EoP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="590b0-123">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="590b0-124">EoP-Anti-Spam-Richtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="590b0-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="590b0-125">Eine weitere Option, die leicht übersehen werden kann: Wenn ein Benutzer über das Empfangen von Massen-e-Mails klagt, aber die Nachrichten von seriösen Absendern sind, die Spamfilterung in EoP übergeben, muss der Benutzer nach einer Option zum Abmelden in der Massen-e-Mail-Nachricht suchen.</span><span class="sxs-lookup"><span data-stu-id="590b0-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
