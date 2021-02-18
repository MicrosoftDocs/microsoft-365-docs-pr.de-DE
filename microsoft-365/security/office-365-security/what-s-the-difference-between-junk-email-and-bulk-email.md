---
title: Worin &apos; besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?
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
description: Administratoren können sich über die Unterschiede zwischen Junk-E-Mail (Spam) und Massen-E-Mail (graue E-Mail) in Exchange Online Protection (EOP) informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c656ed1807b451ae03ecfeb0f220f5d7b902c7ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290645"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="620ae-103">Worin besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail in EOP?</span><span class="sxs-lookup"><span data-stu-id="620ae-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="620ae-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="620ae-104">**Applies to**</span></span>
- [<span data-ttu-id="620ae-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="620ae-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="620ae-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="620ae-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="620ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="620ae-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="620ae-108">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer fragen Kunden manchmal: "Was ist der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?"</span><span class="sxs-lookup"><span data-stu-id="620ae-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="620ae-109">In diesem Thema wird der Unterschied erläutert und die in EOP verfügbaren Steuerelemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="620ae-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="620ae-110">**Junk-E-Mails** sind Spam, die unerwünschte und universell unerwünschte Nachrichten sind (wenn sie ordnungsgemäß identifiziert werden).</span><span class="sxs-lookup"><span data-stu-id="620ae-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="620ae-111">Standardmäßig weist EOP Spam basierend auf der Reputation des Quell-E-Mail-Servers zurück.</span><span class="sxs-lookup"><span data-stu-id="620ae-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="620ae-112">Wenn eine Nachricht die Quell-IP-Überprüfung besteht, wird sie an die Spamfilterung gesendet.</span><span class="sxs-lookup"><span data-stu-id="620ae-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="620ae-113">Wenn die Nachricht von der Spamfilterung als Spam klassifiziert wird, wird die Nachricht (standardmäßig) an die vorgesehenen Empfänger zugestellt und in ihren Junk-E-Mail-Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="620ae-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="620ae-114">Sie können die Aktionen konfigurieren, die bei Spamfilterungen zu ergreifen sind.</span><span class="sxs-lookup"><span data-stu-id="620ae-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="620ae-115">Anweisungen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="620ae-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="620ae-116">Wenn Sie mit der Spamfilterung nicht einverstanden sind, können Sie Nachrichten, die Sie als Spam oder Nichtspam betrachten, auf verschiedene Weise an Microsoft melden, wie in "Melden von Nachrichten und Dateien an [Microsoft" beschrieben.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="620ae-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="620ae-117">**Massen-E-Mail** (auch als _graue_ E-Mail bezeichnet) ist schwieriger zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="620ae-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="620ae-118">Während Spam eine konstante Bedrohung darstellt, sind Massen-E-Mails häufig nur einmal Ankündigungen oder Marketingnachrichten.</span><span class="sxs-lookup"><span data-stu-id="620ae-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="620ae-119">Einige Benutzer möchten Massen-E-Mail-Nachrichten (und tatsächlich haben sie sich absichtlich angemeldet, um sie zu empfangen), während andere Benutzer Massen-E-Mails als Spam betrachten.</span><span class="sxs-lookup"><span data-stu-id="620ae-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="620ae-120">Beispielsweise möchten einige Benutzer Werbenachrichten von der Contoso Corporation oder Einladungen zu einer bevorstehenden Konferenz zur Cybersicherheit empfangen, während andere Benutzer diese Nachrichten als Spam betrachten.</span><span class="sxs-lookup"><span data-stu-id="620ae-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="620ae-121">Weitere Informationen dazu, wie Massen-E-Mails identifiziert werden, finden Sie unter [Bulk Complaint Level (BCL) in EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="620ae-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="620ae-122">Umgang mit Massen-E-Mails</span><span class="sxs-lookup"><span data-stu-id="620ae-122">How to manage bulk email</span></span>

<span data-ttu-id="620ae-123">Aufgrund der gemischten Reaktion auf Massen-E-Mails gibt es nicht universelle Anleitungen, die für jede Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="620ae-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="620ae-124">Antispam-Policen verfügen über einen standardmäßigen BCL-Schwellenwert, der verwendet wird, um Massen-E-Mails als Spam zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="620ae-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="620ae-125">Administratoren können den Schwellenwert erhöhen oder verringern.</span><span class="sxs-lookup"><span data-stu-id="620ae-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="620ae-126">Weitere Informationen hierzu finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="620ae-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="620ae-127">[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="620ae-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="620ae-128">Antispamrichtlinieneinstellungen für EOP</span><span class="sxs-lookup"><span data-stu-id="620ae-128">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="620ae-129">Eine weitere Leicht zu übersehende Option: Wenn sich ein Benutzer über den Empfang von Massen-E-Mails beschwert, die Nachrichten jedoch von seriösen Absendern gesendet werden, die die Spamfilterung in EOP bestehen, lassen Sie den Benutzer in der Massen-E-Mail nach einer Option zum Kündigen des Abonnements suchen.</span><span class="sxs-lookup"><span data-stu-id="620ae-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
