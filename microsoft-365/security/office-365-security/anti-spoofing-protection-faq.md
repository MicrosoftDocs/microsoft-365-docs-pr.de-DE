---
title: Häufig gestellte Fragen zum Antispoofingschutz
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können häufig gestellte Fragen und Antworten zum Schutz vor Spoofing in Exchange Online Protection (EOP) anzeigen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2d307d201af8ad09a4faf7a865a29da8942bdf8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288909"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="c2a53-103">Häufig gestellte Fragen zum Antispoofingschutz</span><span class="sxs-lookup"><span data-stu-id="c2a53-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c2a53-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="c2a53-104">**Applies to**</span></span>
- [<span data-ttu-id="c2a53-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c2a53-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c2a53-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="c2a53-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c2a53-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2a53-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c2a53-108">Dieser Artikel enthält häufig gestellte Fragen und Antworten zum Schutz vor Spoofing für Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständige Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="c2a53-108">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="c2a53-109">Fragen und Antworten zum Antispamschutz finden Sie unter Häufig gestellte Fragen zum [Antispamschutz.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="c2a53-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="c2a53-110">Fragen und Antworten zum Schutz vor Schadsoftware finden Sie unter Häufig gestellte Fragen zum [Schutz vor Schadsoftware](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="c2a53-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="c2a53-111">Warum hat Microsoft sich für nicht authentifizierte eingehende E-Mails entscheiden?</span><span class="sxs-lookup"><span data-stu-id="c2a53-111">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="c2a53-112">Microsoft ist der Meinung, dass das Risiko, dass nicht authentifizierte eingehende E-Mails weiterhin zulässig sind, höher ist als das Risiko, dass legitime eingehende E-Mails verloren geht.</span><span class="sxs-lookup"><span data-stu-id="c2a53-112">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="c2a53-113">Führt junking unauthenticated inbound email cause legitimate email to be marked as spam?</span><span class="sxs-lookup"><span data-stu-id="c2a53-113">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="c2a53-114">Als Microsoft dieses Feature im Jahr 2018 aktiviert hat, sind einige falsch positive Ergebnisse passiert (gute Nachrichten wurden als ungültig gekennzeichnet).</span><span class="sxs-lookup"><span data-stu-id="c2a53-114">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="c2a53-115">Im Laufe der Zeit wurden die Absender jedoch an die Anforderungen angepasst.</span><span class="sxs-lookup"><span data-stu-id="c2a53-115">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="c2a53-116">Die Anzahl der Nachrichten, die als Spoofing falsch identifiziert wurden, war für die meisten E-Mail-Pfade vernachlässigbar.</span><span class="sxs-lookup"><span data-stu-id="c2a53-116">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="c2a53-117">Microsoft selbst hat die neuen E-Mail-Authentifizierungsanforderungen einige Wochen vor der Bereitstellung für Kunden übernommen.</span><span class="sxs-lookup"><span data-stu-id="c2a53-117">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="c2a53-118">Zunächst gab es zwar Störungen, diese gingen jedoch allmählich zurück.</span><span class="sxs-lookup"><span data-stu-id="c2a53-118">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="c2a53-119">Ist Spoofing Intelligence für Microsoft 365-Kunden ohne Defender für Office 365 verfügbar?</span><span class="sxs-lookup"><span data-stu-id="c2a53-119">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="c2a53-120">Ja</span><span class="sxs-lookup"><span data-stu-id="c2a53-120">Yes.</span></span> <span data-ttu-id="c2a53-121">Ab Oktober 2018 steht Spoofintelligenz für alle Organisationen mit Postfächern in Exchange Online und eigenständigen EOP-Organisationen ohne Exchange Online-Postfächer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c2a53-121">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="c2a53-122">Wie kann ich Spamnachrichten oder Nachrichten, die kein Spam sind, an Microsoft melden?</span><span class="sxs-lookup"><span data-stu-id="c2a53-122">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="c2a53-123">Siehe [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c2a53-123">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="c2a53-124">Ich bin Administrator und weiß nicht alle Quellen für Nachrichten in meiner E-Mail-Domäne!</span><span class="sxs-lookup"><span data-stu-id="c2a53-124">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="c2a53-125">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span><span class="sxs-lookup"><span data-stu-id="c2a53-125">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="c2a53-126">Was geschieht, wenn ich den Antis spoofingschutz für meine Organisation deaktiviere?</span><span class="sxs-lookup"><span data-stu-id="c2a53-126">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="c2a53-127">Es wird nicht empfohlen, den Anti-Spoofing-Schutz zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c2a53-127">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="c2a53-128">Wenn Sie den Schutz deaktivieren, können mehr Phishing- und Spamnachrichten in Ihrer Organisation zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c2a53-128">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="c2a53-129">Nicht alle Phishingnachrichten sind Spoofing, und nicht alle gefälschten Nachrichten werden verpasst.</span><span class="sxs-lookup"><span data-stu-id="c2a53-129">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="c2a53-130">Ihr Risiko ist jedoch höher.</span><span class="sxs-lookup"><span data-stu-id="c2a53-130">However, your risk will be higher.</span></span>

<span data-ttu-id="c2a53-131">Da nun [die erweiterte Filterung](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) für Connectors verfügbar ist, wird nicht mehr empfohlen, den Antis spoofingschutz zu deaktivieren, wenn Ihre E-Mails vor EOP über einen anderen Dienst geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="c2a53-131">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="c2a53-132">Bedeutet Antis spoofing-Schutz, dass ich vor allen Phishingversuchen geschützt wird?</span><span class="sxs-lookup"><span data-stu-id="c2a53-132">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="c2a53-133">Leider nein.</span><span class="sxs-lookup"><span data-stu-id="c2a53-133">Unfortunately, no.</span></span> <span data-ttu-id="c2a53-134">Angreifer passen sich an andere Techniken an (z. B. gefährdete Konten oder Konten in kostenlosen E-Mail-Diensten).</span><span class="sxs-lookup"><span data-stu-id="c2a53-134">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="c2a53-135">Der Antiphishingschutz funktioniert jedoch viel besser, um diese anderen Arten von Phishingmethoden zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="c2a53-135">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="c2a53-136">Die Schutzebenen in EOP arbeiten zusammen und bauen aufeinander auf.</span><span class="sxs-lookup"><span data-stu-id="c2a53-136">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="c2a53-137">Blockieren andere große E-Mail-Dienste nicht authentifizierte eingehende E-Mails?</span><span class="sxs-lookup"><span data-stu-id="c2a53-137">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="c2a53-138">Fast alle großen E-Mail-Dienste implementieren herkömmliche SPF-, DKIM- und DMARC-Prüfungen.</span><span class="sxs-lookup"><span data-stu-id="c2a53-138">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="c2a53-139">Einige Dienste haben andere, strengere Prüfungen, aber wenige gehen so weit wie EOP, um nicht authentifizierte E-Mails zu blockieren und als gefälschte Nachrichten zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="c2a53-139">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="c2a53-140">Allerdings wird die Branche zunehmend auf Probleme mit nicht authentifizierten E-Mails aufmerksam, insbesondere aufgrund des Phishingproblems.</span><span class="sxs-lookup"><span data-stu-id="c2a53-140">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="c2a53-141">Muss ich weiterhin die Einstellung "SPF record: hard fail"_(MarkAsSpamSpfRecordHardFail)_ für den erweiterten Spamfilter aktivieren, wenn ich Antis spoofing aktiviert habe?</span><span class="sxs-lookup"><span data-stu-id="c2a53-141">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="c2a53-142">Nein.</span><span class="sxs-lookup"><span data-stu-id="c2a53-142">No.</span></span> <span data-ttu-id="c2a53-143">Diese ASF-Einstellung ist nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c2a53-143">This ASF setting is no longer required.</span></span> <span data-ttu-id="c2a53-144">Antis spoofing protection berücksichtigt sowohl SPF Hard Fails als auch einen viel umfassenderen Satz von Kriterien.</span><span class="sxs-lookup"><span data-stu-id="c2a53-144">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="c2a53-145">Wenn Sie Antispoofing und **SPF-Eintrag: Schwerer Fehler** (_MarkAsSpamSpfRecordHardFail_) aktiviert haben, erhalten Sie wahrscheinlich mehr falsch positive Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="c2a53-145">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="c2a53-146">Es wird empfohlen, dieses Feature zu deaktivieren, da es fast keinen zusätzlichen Vorteil für die Erkennung von Spam- oder Phishingnachrichten bietet und stattdessen hauptsächlich falsch positive Ergebnisse generiert.</span><span class="sxs-lookup"><span data-stu-id="c2a53-146">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="c2a53-147">Weitere Informationen finden Sie unter [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span><span class="sxs-lookup"><span data-stu-id="c2a53-147">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="c2a53-148">Hilft das Sender Rewriting Scheme beim Beheben weitergeleiteter E-Mails?</span><span class="sxs-lookup"><span data-stu-id="c2a53-148">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="c2a53-149">Mit SRS kann das Problem mit weitergeleiteten E-Mails nur teilweise behoben werden.</span><span class="sxs-lookup"><span data-stu-id="c2a53-149">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="c2a53-150">Durch das Umschreiben von SMTP **MAIL FROM** kann SRS sicherstellen, dass die weitergeleitete Nachricht SPF am nächsten Ziel übergibt.</span><span class="sxs-lookup"><span data-stu-id="c2a53-150">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="c2a53-151">Da Antis spoofing jedoch auf der **"Von"-Adresse** in Kombination mit der **MAIL FROM-** oder DKIM-Signaturdomäne (oder anderen Signalen) basiert, reicht es nicht aus, um zu verhindern, dass weitergeleitete SRS-E-Mails als Spoofing gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="c2a53-151">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
