---
title: Was &apos; ist der Unterschied zwischen Junk-E-Mails und Massen-E-Mails?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die Unterschiede zwischen Junk-E-Mails (Spam) und Massen-E-Mails (graue E-Mails) in Exchange Online Protection (EOP) informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc9c94946c3da2f9a14f45070a86c557a5c7dc85
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206974"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="185e7-103">Was ist der Unterschied zwischen Junk-E-Mails und Massen-E-Mails in EOP?</span><span class="sxs-lookup"><span data-stu-id="185e7-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="185e7-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="185e7-104">**Applies to**</span></span>
- [<span data-ttu-id="185e7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="185e7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="185e7-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="185e7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="185e7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="185e7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="185e7-108">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer fragen Kunden manchmal: "Was ist der Unterschied zwischen Junk-E-Mails und Massen-E-Mails?"</span><span class="sxs-lookup"><span data-stu-id="185e7-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="185e7-109">In diesem Thema wird der Unterschied erläutert und die Steuerelemente beschrieben, die in EOP verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="185e7-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="185e7-110">**Junk-E-Mails** sind Spam, bei denen es sich um unerwünschte und universell unerwünschte Nachrichten handelt (wenn sie ordnungsgemäß identifiziert werden).</span><span class="sxs-lookup"><span data-stu-id="185e7-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="185e7-111">Standardmäßig lehnt das EOP Spam basierend auf der Reputation des Quell-E-Mail-Servers ab.</span><span class="sxs-lookup"><span data-stu-id="185e7-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="185e7-112">Wenn eine Nachricht die Quell-IP-Prüfung übergibt, wird sie an die Spamfilterung gesendet.</span><span class="sxs-lookup"><span data-stu-id="185e7-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="185e7-113">Wenn die Nachricht durch Spamfilterung als Spam klassifiziert wird, wird die Nachricht (standardmäßig) an die beabsichtigten Empfänger zugestellt und in ihren Junk-E-Mail-Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="185e7-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="185e7-114">Sie können die Aktionen für Spamfilterungs-Urteile konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="185e7-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="185e7-115">Anweisungen finden Sie unter [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="185e7-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="185e7-116">Wenn Sie mit dem Spamfilter-Urteil nicht einverstanden sind, können Sie Nachrichten, die Sie als Spam oder Nichtspam betrachten, auf verschiedene Weise an Microsoft melden, wie unter Melden von Nachrichten und Dateien an [Microsoft beschrieben.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="185e7-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="185e7-117">**Massen-E-Mails** (auch als _graue E-Mails_ bezeichnet) sind schwieriger zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="185e7-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="185e7-118">Während Spam eine konstante Bedrohung ist, sind Massen-E-Mails häufig einmal Werbung oder Marketingnachrichten.</span><span class="sxs-lookup"><span data-stu-id="185e7-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="185e7-119">Einige Benutzer möchten Massen-E-Mail-Nachrichten (und tatsächlich haben sie sich absichtlich angemeldet, um sie zu empfangen), während andere Benutzer Massen-E-Mails als Spam betrachten.</span><span class="sxs-lookup"><span data-stu-id="185e7-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="185e7-120">Beispielsweise möchten einige Benutzer Werbenachrichten von der Contoso Corporation oder Einladungen zu einer bevorstehenden Konferenz zur Cybersicherheit empfangen, während andere Benutzer diese Nachrichten als Spam betrachten.</span><span class="sxs-lookup"><span data-stu-id="185e7-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="185e7-121">Weitere Informationen dazu, wie Massen-E-Mails identifiziert werden, finden Sie unter [Bulk Complaint Level (BCL) in EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="185e7-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="185e7-122">Umgang mit Massen-E-Mails</span><span class="sxs-lookup"><span data-stu-id="185e7-122">How to manage bulk email</span></span>

<span data-ttu-id="185e7-123">Aufgrund der gemischten Reaktion auf Massen-E-Mails gibt es nicht universelle Anleitungen, die für jede Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="185e7-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="185e7-124">Antispampolizistinnen verfügen über einen standardmäßigen BCL-Schwellenwert, der zum Identifizieren von Massen-E-Mails als Spam verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="185e7-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="185e7-125">Administratoren können den Schwellenwert erhöhen oder verringern.</span><span class="sxs-lookup"><span data-stu-id="185e7-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="185e7-126">Weitere Informationen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="185e7-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="185e7-127">[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="185e7-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="185e7-128">EOP-Antispamrichtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="185e7-128">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

<span data-ttu-id="185e7-129">Eine weitere Option, die leicht übersehen werden kann: Wenn ein Benutzer sich über den Empfang von Massen-E-Mails beschwert, die Nachrichten jedoch von seriösen Absendern stammten, die die Spamfilterung in EOP übergeben, lassen Sie den Benutzer in der Massen-E-Mail-Nachricht nach einer Abmeldeoption suchen.</span><span class="sxs-lookup"><span data-stu-id="185e7-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
