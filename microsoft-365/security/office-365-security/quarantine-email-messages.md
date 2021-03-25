---
title: Isolierte E-Mail-Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die Quarantäne in Exchange Online Protection (EOP) informieren, die potenziell gefährliche oder unerwünschte Nachrichten enthält.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd748871cc09905f9878d5917351b1c185cc1106
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205783"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="57f65-103">Isolierte E-Mail-Nachrichten in EOP</span><span class="sxs-lookup"><span data-stu-id="57f65-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="57f65-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="57f65-104">**Applies to**</span></span>
- [<span data-ttu-id="57f65-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="57f65-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="57f65-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="57f65-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="57f65-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57f65-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="57f65-108">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer steht Die Quarantäne für potenziell gefährliche oder unerwünschte Nachrichten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="57f65-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="57f65-109">An malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span><span class="sxs-lookup"><span data-stu-id="57f65-109">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="57f65-110">Weitere Informationen finden Sie unter [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="57f65-110">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="57f65-111">Standardmäßig unter quarantänen AntispampolizistInnen Phishingnachrichten und senden Spam- und Massen-E-Mail-Nachrichten an den Junk-E-Mail-Ordner des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="57f65-111">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="57f65-112">Sie können jedoch auch Antispamrichtlinien erstellen und anpassen, um Spam- und Massen-E-Mail-Nachrichten unter Quarantäne zu stellen.</span><span class="sxs-lookup"><span data-stu-id="57f65-112">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="57f65-113">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="57f65-113">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="57f65-114">Sowohl Benutzer als auch Administratoren können mit Nachrichten in Quarantäne arbeiten:</span><span class="sxs-lookup"><span data-stu-id="57f65-114">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="57f65-115">Administratoren können mit allen Arten von isolierten Nachrichten für alle Benutzer arbeiten.</span><span class="sxs-lookup"><span data-stu-id="57f65-115">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="57f65-116">Nur Administratoren können mit Nachrichten arbeiten, die als Schadsoftware, Phishing mit hoher Sicherheit oder als Ergebnis von Nachrichtenflussregeln (auch als Transportregeln bekannt) isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="57f65-116">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="57f65-117">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="57f65-117">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="57f65-118">Benutzer können mit isolierten Nachrichten arbeiten, bei denen sie Empfänger sind, wenn die Nachricht als Spam, Massen-E-Mail oder (ab April 2020) Phishing isoliert wurde.</span><span class="sxs-lookup"><span data-stu-id="57f65-118">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="57f65-119">Weitere Informationen finden Sie unter [Suchen und Veröffentlichen isolierter Nachrichten als Benutzer in EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="57f65-119">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="57f65-120">Um zu verhindern, dass Benutzer ihre eigenen Phishingnachrichten in Quarantäne  verwalten, können Administratoren eine andere Aktion für das Phishing-E-Mail-Filter-Urteil in Antispamrichtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="57f65-120">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="57f65-121">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="57f65-121">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="57f65-122">Administratoren und Benutzer können falsch positive Ergebnisse an Microsoft in Quarantäne melden.</span><span class="sxs-lookup"><span data-stu-id="57f65-122">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="57f65-123">Weitere Informationen zum Thema Quarantäne finden Sie unter [Quarantine FAQ](quarantine-faq.md).</span><span class="sxs-lookup"><span data-stu-id="57f65-123">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
