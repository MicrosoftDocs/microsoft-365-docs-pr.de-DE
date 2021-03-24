---
title: Antiphishingschutz
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
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Administratoren können sich über die Antiphishingschutzfunktionen in Exchange Online Protection (EOP) und Microsoft Defender für Office 365 informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0ca7a83e8e8d66bd58fddfc46f53df32f4f623c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065567"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="5621f-103">Antiphishingschutz in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5621f-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5621f-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="5621f-104">**Applies to**</span></span>
- [<span data-ttu-id="5621f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5621f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5621f-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="5621f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5621f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5621f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5621f-108">Bei *Phishing* handelt es sich um E-Mail-Angriffe, bei denen versucht wird, vertrauliche Informationen mittels Nachrichten zu stehlen, die scheinbar von legitimen oder vertrauenswürdigen Absendern stammen.</span><span class="sxs-lookup"><span data-stu-id="5621f-108">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="5621f-109">Es gibt bestimmte Kategorien von Phishing.</span><span class="sxs-lookup"><span data-stu-id="5621f-109">There are specific categories of phishing.</span></span> <span data-ttu-id="5621f-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5621f-110">For example:</span></span>

- <span data-ttu-id="5621f-111">**Beim Phishing** werden gezielt angepasste Inhalte verwendet, die speziell auf die Zielempfänger zugeschnitten sind (in der Regel nach der Aufklärung der Empfänger durch den Angreifer).</span><span class="sxs-lookup"><span data-stu-id="5621f-111">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="5621f-112">**Der Walfang richtet** sich an Führungskräfte oder andere ziele mit hohem Wert innerhalb einer Organisation, um eine maximale Wirkung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="5621f-112">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="5621f-113">**Business Email Compromise (BEC)** verwendet gefälschte vertrauenswürdige Absender (Finanzbeamte, Kunden, vertrauenswürdige Partner usw.), um Empfänger dazu zu verwenden, Zahlungen zu genehmigen, Geld zu übertragen oder Kundendaten offen zu stellen.</span><span class="sxs-lookup"><span data-stu-id="5621f-113">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span>

- <span data-ttu-id="5621f-114">**Ransomware,** die Ihre Daten verschlüsselt und zahlungen zur Entschlüsselung fordert, beginnt fast immer mit Phishingnachrichten.</span><span class="sxs-lookup"><span data-stu-id="5621f-114">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="5621f-115">Antiphishingschutz hilft Ihnen nicht, verschlüsselte Dateien zu entschlüsseln, aber er kann dazu beitragen, die anfänglichen Phishingnachrichten zu erkennen, die der Ransomware-Kampagne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5621f-115">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="5621f-116">Weitere Informationen zum Wiederherstellen nach einem Ransomware-Angriff finden Sie unter [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span><span class="sxs-lookup"><span data-stu-id="5621f-116">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="5621f-117">Mit der zunehmenden Komplexität von Angriffen ist es für geschulte Benutzer sogar schwierig, anspruchsvolle Phishingnachrichten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5621f-117">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="5621f-118">Glücklicherweise können Exchange Online Protection (EOP) und die zusätzlichen Features in Microsoft Defender für Office 365 hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="5621f-118">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="5621f-119">Antiphishingschutz in EOP</span><span class="sxs-lookup"><span data-stu-id="5621f-119">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="5621f-120">EOP (d. h. Microsoft 365-Organisationen ohne Microsoft Defender für Office 365) enthält Features, die Ihre Organisation vor Phishingbedrohungen schützen können:</span><span class="sxs-lookup"><span data-stu-id="5621f-120">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="5621f-121">**Spoofing Intelligence**: Überprüfen Sie gefälschte Nachrichten von Absendern in internen und externen Domänen und lassen Sie diese Absender zu oder blockieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="5621f-121">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="5621f-122">Weitere Informationen finden Sie unter [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="5621f-122">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="5621f-123">**Antiphishingrichtlinien in EOP:** Aktivieren oder Deaktivieren der Spoofintelligenz, Aktivieren oder Deaktivieren der nicht authentifizierten Absenderidentifikation in Outlook und Angeben der Aktion für blockierte spoofierte Absender (Wechseln in Junk-E-Mail-Ordner oder Quarantäne).</span><span class="sxs-lookup"><span data-stu-id="5621f-123">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="5621f-124">Weitere Informationen finden Sie unter [Konfigurieren von Antiphishingrichtlinien in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="5621f-124">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="5621f-125">Implizite E-Mail-Authentifizierung: EOP verbessert standardmäßige E-Mail-Authentifizierungsüberprüfungen für eingehende E-Mails ([SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md)) mit Absenderverdingung, Absenderverlauf, Empfängerverlauf, Verhaltensanalyse und anderen erweiterten Techniken, um gefälschte Absender zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5621f-125">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="5621f-126">Weitere Informationen finden Sie unter [E-Mail-Authentifizierung in Microsoft 365](email-validation-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="5621f-126">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="5621f-127">Zusätzlicher Antiphishingschutz in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="5621f-127">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="5621f-128">Microsoft Defender für Office 365 enthält weitere und noch fortgeschrittenere Antiphishingfeatures:</span><span class="sxs-lookup"><span data-stu-id="5621f-128">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="5621f-129">**Antiphishingrichtlinien in Microsoft Defender für Office 365:** Erstellen neuer benutzerdefinierter Richtlinien, Konfigurieren von Einstellungen für den Identitätswechsel (Schutz von Benutzern und Domänen vor Identitätswechsel), Einstellungen für die Postfachintelligenz und anpassbare erweiterte Phishingschwellenwerte.</span><span class="sxs-lookup"><span data-stu-id="5621f-129">**Anti-phishing policies in Microsoft Defender for Office 365**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="5621f-130">Weitere Informationen finden Sie unter [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5621f-130">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="5621f-131">Weitere Informationen zu den Unterschieden zwischen Antiphishingrichtlinien in EOP und Antiphishingrichtlinien in Defender for Office 365 finden Sie unter [Antiphishingrichtlinien in Microsoft 365](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5621f-131">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="5621f-132">**Kampagnenansichten:** Maschinelles Lernen und andere Heuristiken identifizieren und analysieren Nachrichten, die an koordinierten Phishingangriffen gegen den gesamten Dienst und Ihre Organisation beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="5621f-132">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="5621f-133">Weitere Informationen finden Sie unter [Kampagnenansichten in Microsoft Defender für Office 365](campaigns.md).</span><span class="sxs-lookup"><span data-stu-id="5621f-133">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="5621f-134">**Angriffssimulator:** Administratoren können gefälschte Phishingnachrichten erstellen und als Bildungstool an interne Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="5621f-134">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="5621f-135">Weitere Informationen finden Sie unter [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span><span class="sxs-lookup"><span data-stu-id="5621f-135">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="5621f-136">Andere Antiphishingressourcen</span><span class="sxs-lookup"><span data-stu-id="5621f-136">Other anti-phishing resources</span></span>

- <span data-ttu-id="5621f-137">Für Endbenutzer: [Schützen Sie sich vor Phishingschemas und anderen Formen von Onlinebetrug.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)</span><span class="sxs-lookup"><span data-stu-id="5621f-137">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="5621f-138">[So überprüft Microsoft 365 die Von-Adresse, um Phishing zu verhindern.](how-office-365-validates-the-from-address.md)</span><span class="sxs-lookup"><span data-stu-id="5621f-138">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
