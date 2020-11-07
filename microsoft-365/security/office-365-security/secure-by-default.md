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
description: Erfahren Sie mehr über die Einstellung "standardmäßig sicher" in Exchange Online Protection (EoP).
ms.openlocfilehash: 50d1c64e4d8343fdb9b25bfcbeee5d988ddc6b8a
ms.sourcegitcommit: 9dbc6a08177aaca112e84d30dbaa79a0a8e9dbf8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "48945330"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="92a46-103">Standardmäßig sichern in Office 365</span><span class="sxs-lookup"><span data-stu-id="92a46-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="92a46-104">"Standardmäßig sichern" ist ein Begriff, der verwendet wird, um die Standardeinstellungen zu definieren, die möglichst sicher sind.</span><span class="sxs-lookup"><span data-stu-id="92a46-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="92a46-105">Die Sicherheit muss jedoch mit der Produktivität ausgeglichen werden.</span><span class="sxs-lookup"><span data-stu-id="92a46-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="92a46-106">Dies kann das Balancing in folgenden Bereichen umfassen:</span><span class="sxs-lookup"><span data-stu-id="92a46-106">This can include balancing across:</span></span>

- <span data-ttu-id="92a46-107">Usability: die Einstellungen sollten nicht die Produktivität des Benutzers in den Weg legen.</span><span class="sxs-lookup"><span data-stu-id="92a46-107">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="92a46-108">Risiko: Sicherheit blockiert möglicherweise wichtige Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="92a46-108">Risk: security might block important activities.</span></span>
- <span data-ttu-id="92a46-109">Legacy Einstellungen: einige Konfigurationen für ältere Produkte und Features müssen möglicherweise aus geschäftlichen Gründen verwaltet werden, selbst wenn neue, moderne Einstellungen verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="92a46-109">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="92a46-110">Microsoft 365-Organisationen mit Postfächern in Exchange Online sind durch Exchange Online Protection (EoP) geschützt.</span><span class="sxs-lookup"><span data-stu-id="92a46-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="92a46-111">Dieser Schutz umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="92a46-111">This protection includes:</span></span>

1. <span data-ttu-id="92a46-112">E-Mails mit mutmaßlicher Schadsoftware werden automatisch isoliert, und Empfänger werden benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="92a46-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="92a46-113">Weitere Informationen finden Sie unter [configure Anti-Malware Policies in EoP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="92a46-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
1. <span data-ttu-id="92a46-114">Phishing-e-Mails, die als "hohes Vertrauen" identifiziert werden, werden gemäß der Antispampolitik-Aktion verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="92a46-114">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="92a46-115">Weitere Informationen finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="92a46-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="92a46-116">Da Microsoft unsere Kunden standardmäßig schützen möchte, werden einige Mandanten Außerkraftsetzungen nicht auf Schadsoftware oder Phishing mit hoher Zuverlässigkeit angewendet.</span><span class="sxs-lookup"><span data-stu-id="92a46-116">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="92a46-117">Zu diesen Außerkraftsetzungen gehören:</span><span class="sxs-lookup"><span data-stu-id="92a46-117">These overrides include:</span></span>

- <span data-ttu-id="92a46-118">Zugelassene Absenderlisten oder zugelassene Domänenlisten (Anti-Spam-Richtlinien)</span><span class="sxs-lookup"><span data-stu-id="92a46-118">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="92a46-119">Outlook-sichere Absender</span><span class="sxs-lookup"><span data-stu-id="92a46-119">Outlook Safe senders</span></span>
- <span data-ttu-id="92a46-120">IP-Zulassungsliste (Verbindungsfilterung)</span><span class="sxs-lookup"><span data-stu-id="92a46-120">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="92a46-121">Weitere Informationen zu diesen Außerkraftsetzungen finden Sie unter [Create Safe Sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="92a46-121">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="92a46-122">Secure standardmäßig ist hier keine Einstellung, die aktiviert oder deaktiviert werden könnte, aber die Art und Weise, wie unsere Filterung funktioniert, um potenziell gefährliche oder unerwünschte Nachrichten aus ihren Postfächern zu halten.</span><span class="sxs-lookup"><span data-stu-id="92a46-122">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="92a46-123">Schadsoftware und Phishing mit hoher Zuverlässigkeit sollten an die Quarantäne gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="92a46-123">Malware and high confidence phish should be sent to quarantine.</span></span> <span data-ttu-id="92a46-124">Nur Administratoren können Nachrichten verwalten, die als Schadsoftware oder Phishing für hohe Vertrauenswürdigkeit isoliert wurden, und Sie können von dort aus auch falsch positive Ergebnisse an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="92a46-124">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="92a46-125">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EoP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="92a46-125">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="92a46-126">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="92a46-126">Exceptions</span></span>

<span data-ttu-id="92a46-127">Die einzigen Außerkraftsetzungen, die alle Filter umgehen werden, umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="92a46-127">The only overrides that will bypass all filters include:</span></span>

- <span data-ttu-id="92a46-128">Exchange-Transport Regeln (ETR)/Mail-Flussregeln.</span><span class="sxs-lookup"><span data-stu-id="92a46-128">Exchange Transport Rules (ETR)/mail flow rules.</span></span> <span data-ttu-id="92a46-129">Verwenden Sie Nachrichtenfluss Regeln, um die SCL-Bewertung (Spam Confidence Level) in Nachrichten in EoP festzulegen.</span><span class="sxs-lookup"><span data-stu-id="92a46-129">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.</span></span>
- <span data-ttu-id="92a46-130">Mandanten-Zulassungs-und Sperrliste: Verwalten von URLs und Dateien in der Liste Mandanten-Allow/Block.</span><span class="sxs-lookup"><span data-stu-id="92a46-130">Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="92a46-131">Diese Arten von Außerkraftsetzungen sind für Folgendes nützlich:</span><span class="sxs-lookup"><span data-stu-id="92a46-131">These types of overrides are useful for:</span></span>

- <span data-ttu-id="92a46-132">Phishing-Simulationen: Simulierte Angriffe können Sie bei der Identifizierung von anfälligen Benutzern unterstützen, bevor ein echter Angriff Ihre Organisation beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="92a46-132">Phish simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="92a46-133">Security/Cops Mailboxes: dedizierte Postfächer, die von Sicherheitsteams verwendet werden, um nicht gefilterte Nachrichten (sowohl gut als auch schlecht) abzurufen.</span><span class="sxs-lookup"><span data-stu-id="92a46-133">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="92a46-134">Teams können dann überprüfen, ob Sie schädlichen Inhalt enthalten.</span><span class="sxs-lookup"><span data-stu-id="92a46-134">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="92a46-135">Drittanbieter Filter: einige Drittanbieter empfehlen das Deaktivieren von EoP (SCL =-1), da der Filter eines Drittanbieters die e-Mail-Filterung verwalten wird.</span><span class="sxs-lookup"><span data-stu-id="92a46-135">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span> <span data-ttu-id="92a46-136">Microsoft rät davon ab, EoP zu deaktivieren, da EoP für Defender für Office 365 erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="92a46-136">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span>
- <span data-ttu-id="92a46-137">Falsch positive Ergebnisse: möglicherweise möchten Sie bestimmte Nachrichten zulassen, die von Microsoft [über Administrator übermittungen](admin-submission.md)noch analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="92a46-137">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="92a46-138">Wie bei allen Außerkraftsetzungen wird empfohlen, dass Sie temporär sind.</span><span class="sxs-lookup"><span data-stu-id="92a46-138">As with all overrides, it is recommended that they are temporary.</span></span>
