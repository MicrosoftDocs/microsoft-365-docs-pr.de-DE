---
title: Standardmäßig sichern in Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Hier erfahren Sie, wie Sie e-Mail-Sicherheitsberichte für Ihre Organisation suchen und verwenden. E-Mail-Sicherheitsberichte sind im Security & Compliance Center verfügbar.
ms.openlocfilehash: 0e38091981cd379dfc912be429c00d168dff775c
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944481"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="b29a2-104">Standardmäßig sichern in Office 365</span><span class="sxs-lookup"><span data-stu-id="b29a2-104">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b29a2-105">"Standardmäßig sichern" ist ein Begriff, der verwendet wird, um die Standardeinstellungen zu definieren, die möglichst sicher sind.</span><span class="sxs-lookup"><span data-stu-id="b29a2-105">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span> 

<span data-ttu-id="b29a2-106">Die Sicherheit muss jedoch mit der Produktivität ausgeglichen werden.</span><span class="sxs-lookup"><span data-stu-id="b29a2-106">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="b29a2-107">Dies kann das Balancing in folgenden Bereichen umfassen:</span><span class="sxs-lookup"><span data-stu-id="b29a2-107">This can include balancing across:</span></span>
- <span data-ttu-id="b29a2-108">Usability: die Einstellungen sollten nicht die Produktivität des Benutzers in den Weg legen.</span><span class="sxs-lookup"><span data-stu-id="b29a2-108">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="b29a2-109">Risiko: Sicherheit blockiert möglicherweise wichtige Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="b29a2-109">Risk: security might block important activities.</span></span>
- <span data-ttu-id="b29a2-110">Legacy Einstellungen: einige Konfigurationen für ältere Produkte und Features müssen möglicherweise aus geschäftlichen Gründen verwaltet werden, selbst wenn neue, moderne Einstellungen verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="b29a2-110">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span> 

<span data-ttu-id="b29a2-111">Microsoft 365-Organisationen mit Postfächern in Exchange Online sind durch Exchange Online Protection (EoP) geschützt.</span><span class="sxs-lookup"><span data-stu-id="b29a2-111">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="b29a2-112">Dieser Schutz umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b29a2-112">This  protection includes:</span></span>
1. <span data-ttu-id="b29a2-113">E-Mails mit mutmaßlicher Schadsoftware werden automatisch isoliert, und Empfänger werden benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="b29a2-113">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="b29a2-114">Weitere Informationen finden Sie unter [configure Anti-Malware Policies in EoP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="b29a2-114">See [Configure anti-malware policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span></span>
1. <span data-ttu-id="b29a2-115">Phishing-e-Mails, die als "hohes Vertrauen" identifiziert werden, werden gemäß der Antispampolitik-Aktion verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b29a2-115">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="b29a2-116">Weitere Informationen finden Sie unter [configure Anti-Spam Policies in EoP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="b29a2-116">See [Configure anti-spam policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="b29a2-117">Da Microsoft unsere Kunden standardmäßig schützen möchte, werden einige Mandanten Außerkraftsetzungen nicht auf Schadsoftware oder Phishing mit hoher Zuverlässigkeit angewendet.</span><span class="sxs-lookup"><span data-stu-id="b29a2-117">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="b29a2-118">Zu diesen Außerkraftsetzungen gehören:</span><span class="sxs-lookup"><span data-stu-id="b29a2-118">These overrides include:</span></span>
- <span data-ttu-id="b29a2-119">Zugelassene Absenderlisten oder zugelassene Domänenlisten (Anti-Spam-Richtlinien)</span><span class="sxs-lookup"><span data-stu-id="b29a2-119">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="b29a2-120">Outlook-sichere Absender</span><span class="sxs-lookup"><span data-stu-id="b29a2-120">Outlook Safe senders</span></span>
- <span data-ttu-id="b29a2-121">IP-Zulassungsliste (Verbindungsfilterung)</span><span class="sxs-lookup"><span data-stu-id="b29a2-121">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="b29a2-122">Weitere Informationen zu diesen Außerkraftsetzungen finden Sie unter [Create Safe Sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="b29a2-122">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="b29a2-123">Secure standardmäßig ist hier keine Einstellung, die aktiviert oder deaktiviert werden könnte, aber die Art und Weise, wie unsere Filterung funktioniert, um potenziell gefährliche oder unerwünschte Nachrichten aus ihren Postfächern zu halten.</span><span class="sxs-lookup"><span data-stu-id="b29a2-123">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="b29a2-124">Schadsoftware und Phishing mit hoher Zuverlässigkeit sollten an die Quarantäne gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b29a2-124">Malware and high confidence phish should be sent to quarantine.</span></span> <span data-ttu-id="b29a2-125">Nur Administratoren können Nachrichten verwalten, die als Schadsoftware oder Phishing für hohe Vertrauenswürdigkeit isoliert wurden, und Sie können von dort aus auch falsch positive Ergebnisse an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="b29a2-125">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="b29a2-126">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EoP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="b29a2-126">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="b29a2-127">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="b29a2-127">Exceptions</span></span>
<span data-ttu-id="b29a2-128">Die einzigen Außerkraftsetzungen, die alle Filter umgehen werden, umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b29a2-128">The only overrides that will bypass all filters include:</span></span>
- <span data-ttu-id="b29a2-129">Exchange-Transport Regeln (ETR)/Mail-Flussregeln.</span><span class="sxs-lookup"><span data-stu-id="b29a2-129">Exchange Transport Rules (ETR)/mail flow rules.</span></span>  <span data-ttu-id="b29a2-130">Verwenden Sie Nachrichtenfluss Regeln, um die SCL-Bewertung (Spam Confidence Level) in Nachrichten in EoP festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b29a2-130">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.</span></span>
- <span data-ttu-id="b29a2-131">Mandanten-Zulassungs-und Sperrliste: Verwalten von URLs und Dateien in der Liste Mandanten-Allow/Block.</span><span class="sxs-lookup"><span data-stu-id="b29a2-131">Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.</span></span>


<span data-ttu-id="b29a2-132">Diese Arten von Außerkraftsetzungen sind für Folgendes nützlich:</span><span class="sxs-lookup"><span data-stu-id="b29a2-132">These types of overrides are useful for:</span></span>
- <span data-ttu-id="b29a2-133">Phishing-Simulationen: Simulierte Angriffe können Sie bei der Identifizierung von anfälligen Benutzern unterstützen, bevor ein echter Angriff Ihre Organisation beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="b29a2-133">Phish simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="b29a2-134">Security/Cops Mailboxes: dedizierte Postfächer, die von Sicherheitsteams verwendet werden, um nicht gefilterte Nachrichten (sowohl gut als auch schlecht) abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b29a2-134">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="b29a2-135">Teams können dann überprüfen, ob Sie schädlichen Inhalt enthalten.</span><span class="sxs-lookup"><span data-stu-id="b29a2-135">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="b29a2-136">Drittanbieter Filter: einige Drittanbieter empfehlen das Deaktivieren von EoP (SCL =-1), da der Filter eines Drittanbieters die e-Mail-Filterung verwalten wird.</span><span class="sxs-lookup"><span data-stu-id="b29a2-136">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span>  <span data-ttu-id="b29a2-137">Microsoft rät davon ab, EoP zu deaktivieren, da EoP für Defender für Office 365 erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b29a2-137">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span> 
- <span data-ttu-id="b29a2-138">Falsch positive Ergebnisse: möglicherweise möchten Sie bestimmte Nachrichten zulassen, die von Microsoft [über Administrator übermittungen](admin-submission.md)noch analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="b29a2-138">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="b29a2-139">Wie bei allen Außerkraftsetzungen wird empfohlen, dass Sie temporär sind.</span><span class="sxs-lookup"><span data-stu-id="b29a2-139">As with all overrides, it is recommended that they are temporary.</span></span>
