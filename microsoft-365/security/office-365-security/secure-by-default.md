---
title: Standardmäßig sicher in Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Weitere Informationen zur Standardmäßigen Einstellung "Sicherheit" in Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a507abce8c18657794b56570241570e5048b89d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288513"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="8605a-103">Standardmäßig sicher in Office 365</span><span class="sxs-lookup"><span data-stu-id="8605a-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8605a-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="8605a-104">**Applies to**</span></span>
- [<span data-ttu-id="8605a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8605a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8605a-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="8605a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="8605a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8605a-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="8605a-108">"Standardmäßig sicher" ist ein Begriff, der verwendet wird, um die Standardeinstellungen zu definieren, die möglichst sicher sind.</span><span class="sxs-lookup"><span data-stu-id="8605a-108">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="8605a-109">Sicherheit muss jedoch mit Produktivität abgewogen werden.</span><span class="sxs-lookup"><span data-stu-id="8605a-109">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="8605a-110">Dies kann einen Ausgleich zwischen:</span><span class="sxs-lookup"><span data-stu-id="8605a-110">This can include balancing across:</span></span>

- <span data-ttu-id="8605a-111">**Benutzerfreundlichkeit:** Einstellungen sollten der Benutzerproduktivität nicht im Wege kommen.</span><span class="sxs-lookup"><span data-stu-id="8605a-111">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="8605a-112">**Risiko:** Sicherheit blockiert möglicherweise wichtige Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="8605a-112">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="8605a-113">**Legacyeinstellungen:** Einige Konfigurationen für ältere Produkte und Features müssen möglicherweise aus geschäftlichen Gründen beibehalten werden, auch wenn neue, moderne Einstellungen verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="8605a-113">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="8605a-114">Microsoft 365-Organisationen mit Postfächern in Exchange Online sind durch Exchange Online Protection (EOP) geschützt.</span><span class="sxs-lookup"><span data-stu-id="8605a-114">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="8605a-115">Dieser Schutz umfasst:</span><span class="sxs-lookup"><span data-stu-id="8605a-115">This protection includes:</span></span>

- <span data-ttu-id="8605a-116">E-Mails mit mutmaßlicher Schadsoftware werden automatisch unter Quarantäne gestellt, und Empfänger werden benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="8605a-116">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="8605a-117">Weitere [Informationen finden Sie unter "Konfigurieren von An malware-Richtlinien in EOP".](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="8605a-117">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="8605a-118">E-Mails, die als Phishing mit hoher Confidence identifiziert werden, werden gemäß der Antispamrichtlinienaktion behandelt.</span><span class="sxs-lookup"><span data-stu-id="8605a-118">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="8605a-119">Weitere [Informationen finden Sie unter Konfigurieren von Antispamrichtlinien in EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="8605a-119">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="8605a-120">Weitere Informationen zu EOP finden Sie in [der Exchange Online Protection-Übersicht.](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8605a-120">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="8605a-121">Da Microsoft unsere Kunden standardmäßig schützen möchte, werden einige Mandanten nicht auf Schadsoftware oder Phishing mit hoher Sicherheit angewendet.</span><span class="sxs-lookup"><span data-stu-id="8605a-121">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="8605a-122">Zu diesen Außerkraftsetzungen gehören:</span><span class="sxs-lookup"><span data-stu-id="8605a-122">These overrides include:</span></span>

- <span data-ttu-id="8605a-123">Listen zulässiger Absender oder zulässiger Domänen (Antispamrichtlinien)</span><span class="sxs-lookup"><span data-stu-id="8605a-123">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="8605a-124">Sichere Absender in Outlook</span><span class="sxs-lookup"><span data-stu-id="8605a-124">Outlook Safe Senders</span></span>
- <span data-ttu-id="8605a-125">LISTE der zulässigen IP-Adressen (Verbindungsfilterung)</span><span class="sxs-lookup"><span data-stu-id="8605a-125">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="8605a-126">Weitere Informationen zu diesen Außerkraftsetzungen finden Sie unter "Listen [sicherer Absender erstellen".](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="8605a-126">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8605a-127">We're in the process of deprecating the **Move message to Junk Email folder action** for a High confidence phishing **email** verdict in EOP anti-spam policies.</span><span class="sxs-lookup"><span data-stu-id="8605a-127">We're in the process of deprecating the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="8605a-128">Antispamrichtlinien, die diese Aktion für Phishingnachrichten mit hoher Sicherheit verwenden, werden in **Quarantänenachrichten konvertiert.**</span><span class="sxs-lookup"><span data-stu-id="8605a-128">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="8605a-129">Die **Aktion "Nachricht an E-Mail-Adresse** umleiten" für Phishingnachrichten mit hoher Confidence ist davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="8605a-129">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="8605a-130">"Sicherheit" ist standardmäßig keine Einstellung, die aktiviert oder deaktiviert werden kann, aber unsere Filterung funktioniert so, dass potenziell gefährliche oder unerwünschte Nachrichten aus Ihren Postfächern herausgefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="8605a-130">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="8605a-131">Schadsoftware und Phishingnachrichten mit hoher Sicherheit sollten unter Quarantäne gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8605a-131">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="8605a-132">Nur Administratoren können Nachrichten verwalten, die als Schadsoftware oder Phishing mit hoher Sicherheit isoliert sind, und sie können von dort auch falsch positive Ergebnisse an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="8605a-132">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="8605a-133">Weitere Informationen finden Sie unter ["Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP"](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="8605a-133">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="8605a-134">Weitere Informationen dazu, warum wir dies tun</span><span class="sxs-lookup"><span data-stu-id="8605a-134">More on why we're doing this</span></span>

<span data-ttu-id="8605a-135">Der Standardwert für Sicherheit ist: Wir ergreifen dieselbe Aktion für die Nachricht, die Sie ergreifen würden, wenn Sie die Nachricht als bösartig einwünssten, auch wenn eine konfigurierte Ausnahme andernfalls die Zugestellt werden würde.</span><span class="sxs-lookup"><span data-stu-id="8605a-135">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="8605a-136">Dies ist der gleiche Ansatz, den wir immer für Schadsoftware verwendet haben, und jetzt erweitern wir dieses Verhalten auf Phishingnachrichten mit hoher Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="8605a-136">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="8605a-137">Unsere Daten deuten darauf hin, dass ein Benutzer 30 Mal häufiger auf einen schädlichen Link in Nachrichten im Junk-E-Mail-Ordner im Vergleich zur Quarantäne klickt.</span><span class="sxs-lookup"><span data-stu-id="8605a-137">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="8605a-138">Unsere Daten weisen auch darauf hin, dass die Rate falsch positiver Ergebnisse (gute Nachrichten, die als schlecht gekennzeichnet sind) für Phishingnachrichten mit hoher Confidence sehr niedrig ist, und Administratoren alle falsch positiven Ergebnisse mit Administratorübermittlungen beheben können.</span><span class="sxs-lookup"><span data-stu-id="8605a-138">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="8605a-139">Außerdem haben wir festgestellt, dass die Listen zulässiger Absender und zulässiger Domänen in Antispamrichtlinien und sicheren Absendern in Outlook zu breit waren und mehr Schaden als Schaden anrichten.</span><span class="sxs-lookup"><span data-stu-id="8605a-139">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="8605a-140">Anders ausgedrückt: Als Sicherheitsdienst handeln wir in Ihrem Namen, um zu verhindern, dass Ihre Benutzer gefährdet werden.</span><span class="sxs-lookup"><span data-stu-id="8605a-140">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span> 

## <a name="exceptions"></a><span data-ttu-id="8605a-141">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="8605a-141">Exceptions</span></span>

<span data-ttu-id="8605a-142">Die einzige Außerkraftsetzung, die eine Umgehung der Filterung durch Phishingnachrichten mit hoher Sicherheit ermöglicht, sind Exchange-Nachrichtenflussregeln (auch als Transportregeln bekannt).</span><span class="sxs-lookup"><span data-stu-id="8605a-142">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="8605a-143">Informationen zur Verwendung von Nachrichtenflussregeln zum Umgehen der Filterung finden Sie unter Verwenden von Nachrichtenflussregeln zum Festlegen der [SCL in Nachrichten.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="8605a-143">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="8605a-144">Sie sollten die Verwendung von Außerkraftsetzungen nur in den folgenden Szenarien in Betracht ziehen:</span><span class="sxs-lookup"><span data-stu-id="8605a-144">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="8605a-145">Phishingsimulationen: Simulierte Angriffe können Ihnen dabei helfen, anfällige Benutzer zu identifizieren, bevor sich ein tatsächlicher Angriff auf Ihre Organisation ausdingt.</span><span class="sxs-lookup"><span data-stu-id="8605a-145">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="8605a-146">Security/SecOps-Postfächer: Dedizierte Postfächer, die von Sicherheitsteams verwendet werden, um ungefilterte Nachrichten (sowohl gut als auch schlecht) zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8605a-146">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="8605a-147">Teams können dann überprüfen, ob sie schädliche Inhalte enthalten.</span><span class="sxs-lookup"><span data-stu-id="8605a-147">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="8605a-148">Filter von Drittanbietern: "Sicherheit" gilt standardmäßig nicht, wenn der MX-Eintrag der Domäne nicht auf Office 365 verweisen soll.</span><span class="sxs-lookup"><span data-stu-id="8605a-148">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="8605a-149">Falsch positive Ergebnisse: Möglicherweise möchten Sie vorübergehend bestimmte Nachrichten zulassen, die noch von Microsoft über [Administratorübermittlungen analysiert werden.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="8605a-149">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="8605a-150">Wie bei allen Außerkraftsetzungen wird empfohlen, dass sie temporär sind.</span><span class="sxs-lookup"><span data-stu-id="8605a-150">As with all overrides, it is recommended that they are temporary.</span></span>
