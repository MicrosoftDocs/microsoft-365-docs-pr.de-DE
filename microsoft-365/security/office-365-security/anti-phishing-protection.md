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
ms.service: O365-seccomp
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
description: Administratoren können Informationen zu den Features zum Schutz vor Phishing in Exchange Online Protection (EoP) und Microsoft Defender für Office 365 erhalten.
ms.openlocfilehash: 5b175a252f95c62a40348a78e694628ee58488bd
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614991"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="dedf3-103">Anti-Phishing-Schutz in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dedf3-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="dedf3-104">Bei *Phishing* handelt es sich um E-Mail-Angriffe, bei denen versucht wird, vertrauliche Informationen mittels Nachrichten zu stehlen, die scheinbar von legitimen oder vertrauenswürdigen Absendern stammen.</span><span class="sxs-lookup"><span data-stu-id="dedf3-104">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="dedf3-105">Es gibt bestimmte Kategorien von Phishing.</span><span class="sxs-lookup"><span data-stu-id="dedf3-105">There are specific categories of phishing.</span></span> <span data-ttu-id="dedf3-106">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dedf3-106">For example:</span></span>

- <span data-ttu-id="dedf3-107">**Spear-Phishing** verwendet fokussierte, angepasste Inhalte, die speziell auf die Zielempfänger zugeschnitten sind (in der Regel nach Aufklärung der Empfänger durch den Angreifer).</span><span class="sxs-lookup"><span data-stu-id="dedf3-107">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="dedf3-108">**Walfang** richtet sich an Führungskräfte oder andere hochwertige Ziele innerhalb einer Organisation für maximale Wirkung.</span><span class="sxs-lookup"><span data-stu-id="dedf3-108">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="dedf3-109">**Business eMail Kompromiss (BEC)** verwendet gefälschte vertrauenswürdige Absender (Finanzmitarbeiter, Kunden, vertrauenswürdige Partner usw.), um Empfänger in die Genehmigung von Zahlungen, die Übertragung von Guthaben oder das Aufdecken von Kundendaten zu betrügen.</span><span class="sxs-lookup"><span data-stu-id="dedf3-109">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span>

- <span data-ttu-id="dedf3-110">**Ransomware** , die Ihre Daten verschlüsselt und die Zahlung zur Entschlüsselung verlangt. fast immer beginnt in Phishing-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="dedf3-110">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="dedf3-111">Der Schutz vor Phishing kann Ihnen nicht dabei helfen, verschlüsselte Dateien zu entschlüsseln, aber er kann bei der Erkennung der anfänglichen Phishing-Nachrichten helfen, die der Ransomware-Kampagne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="dedf3-111">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="dedf3-112">Weitere Informationen zum Wiederherstellen nach einem Ransomware-Angriff finden Sie unter [Recover by a Ransomware Attack in Microsoft 365](recover-from-ransomware.md).</span><span class="sxs-lookup"><span data-stu-id="dedf3-112">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="dedf3-113">Aufgrund der wachsenden Komplexität von Angriffen ist es für geschulte Benutzer sogar schwierig, anspruchsvolle Phishing-Nachrichten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="dedf3-113">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="dedf3-114">Glücklicherweise können Exchange Online Protection (EoP) und die zusätzlichen Features in Microsoft Defender für Office 365 hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="dedf3-114">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="dedf3-115">Antiphishingschutz in EOP</span><span class="sxs-lookup"><span data-stu-id="dedf3-115">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="dedf3-116">EoP (Microsoft 365-Organisationen ohne Microsoft Defender für Office 365) enthält Features, mit denen Ihre Organisation vor Phishing-Bedrohungen geschützt werden kann:</span><span class="sxs-lookup"><span data-stu-id="dedf3-116">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="dedf3-117">**Spoofing Intelligence**: Überprüfen Sie gefälschte Nachrichten von Absendern in internen und externen Domänen und lassen Sie diese Absender zu oder blockieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="dedf3-117">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="dedf3-118">Weitere Informationen finden Sie unter [configure Spoof Intelligence in EoP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="dedf3-118">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="dedf3-119">**Anti-Phishing-Richtlinien in EoP**: Aktivieren oder deaktivieren Sie Spoof Intelligence, aktivieren oder deaktivieren Sie die nicht authentifizierte Absender Identifikation in Outlook, und geben Sie die Aktion für blockierte gefälschte Absender an (in den Ordner "Junk-e-Mail" oder "Quarantäne" verschieben).</span><span class="sxs-lookup"><span data-stu-id="dedf3-119">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="dedf3-120">Weitere Informationen finden Sie unter [configure Anti-Phishing Policies in EoP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="dedf3-120">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="dedf3-121">**Implizite e-Mail-Authentifizierung**: EoP verbessert standardmäßige e-Mail-Authentifizierungsüberprüfungen für eingehende e-Mails ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md)) mit Absenderzuverlässigkeit, Absender Verlauf, Empfänger Verlauf, Verhaltensanalyse und anderen erweiterten Techniken zur Identifizierung gefälschter Absender.</span><span class="sxs-lookup"><span data-stu-id="dedf3-121">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="dedf3-122">Weitere Informationen finden Sie unter [E-Mail-Authentifizierung in Microsoft 365](email-validation-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="dedf3-122">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="dedf3-123">Zusätzlicher Schutz gegen Phishing in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="dedf3-123">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="dedf3-124">Microsoft Defender für Office 365 enthält zusätzliche und erweiterte Features zum Schutz vor Phishing:</span><span class="sxs-lookup"><span data-stu-id="dedf3-124">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="dedf3-125">**Anti-Phishing-Richtlinien in Microsoft Defender für Office 365**: Erstellen neuer benutzerdefinierter Richtlinien, Konfigurieren von Einstellungen für die Anti-Identitätswechsel (schützen von Benutzern und Domänen vor Identitätswechsel), Post Fachnachrichten Einstellungen und anpassbaren erweiterten Phishing-Schwellenwerten.</span><span class="sxs-lookup"><span data-stu-id="dedf3-125">**Anti-phishing policies in Microsoft Defender for Office 365**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="dedf3-126">Weitere Informationen finden Sie unter [configure Anti-Phishing Policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dedf3-126">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="dedf3-127">Weitere Informationen zu den Unterschieden zwischen Anti-Phishing-Richtlinien in EoP und Anti-Phishing-Richtlinien in Defender für Office 365 finden Sie unter [Anti-Phishing Policies in Microsoft 365](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dedf3-127">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="dedf3-128">**Kampagnen Ansichten**: Maschinelles Lernen und andere Heuristiken identifizieren und analysieren Nachrichten, die an koordinierten Phishing-Angriffen für den gesamten Dienst und Ihre Organisation beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="dedf3-128">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="dedf3-129">Weitere Informationen finden Sie unter [Kampagnen Ansichten in Microsoft Defender für Office 365](campaigns.md).</span><span class="sxs-lookup"><span data-stu-id="dedf3-129">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="dedf3-130">**Angriffs Simulator**: Administratoren können gefälschte Phishing-Nachrichten erstellen und Sie als Schulungstool an interne Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="dedf3-130">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="dedf3-131">Weitere Informationen finden Sie unter [Attack Simulator in Microsoft Defender für Office 365](attack-simulator.md).</span><span class="sxs-lookup"><span data-stu-id="dedf3-131">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="dedf3-132">Weitere Anti-Phishing-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="dedf3-132">Other anti-phishing resources</span></span>

- <span data-ttu-id="dedf3-133">Für Endbenutzer: [schützen Sie sich vor Phishing-Schemas und anderen Formen von Onlinebetrug](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span><span class="sxs-lookup"><span data-stu-id="dedf3-133">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="dedf3-134">[Wie Microsoft 365 die Absenderadresse überprüft, um Phishing zu verhindern](how-office-365-validates-the-from-address.md).</span><span class="sxs-lookup"><span data-stu-id="dedf3-134">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
