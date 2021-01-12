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
ms.service: O365-seccomp
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
ms.openlocfilehash: 8a978ece029de06bcb7b434de730b0baea33a5e1
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794328"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="364ad-103">Isolierte E-Mail-Nachrichten in EOP</span><span class="sxs-lookup"><span data-stu-id="364ad-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="364ad-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer steht die Quarantäne für potenziell gefährliche oder unerwünschte Nachrichten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="364ad-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="364ad-105">An malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span><span class="sxs-lookup"><span data-stu-id="364ad-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="364ad-106">Weitere Informationen finden Sie unter [Konfigurieren von An malware-Richtlinien in EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="364ad-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="364ad-107">Standardmäßig isolieren Antispampoliden Phishingnachrichten und senden Spam- und Massen-E-Mail-Nachrichten an den Junk-E-Mail-Ordner des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="364ad-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="364ad-108">Sie können jedoch auch Antispamrichtlinien erstellen und anpassen, um Spam- und Massen-E-Mail-Nachrichten zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="364ad-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="364ad-109">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="364ad-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="364ad-110">Sowohl Benutzer als auch Administratoren können mit Nachrichten in Quarantäne arbeiten:</span><span class="sxs-lookup"><span data-stu-id="364ad-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="364ad-111">Administratoren können mit allen Arten von isolierten Nachrichten für alle Benutzer arbeiten.</span><span class="sxs-lookup"><span data-stu-id="364ad-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="364ad-112">Nur Administratoren können mit Nachrichten arbeiten, die als Schadsoftware, Phishing mit hoher Sicherheit oder als Folge von Nachrichtenflussregeln (auch als Transportregeln bekannt) isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="364ad-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="364ad-113">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="364ad-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="364ad-114">Benutzer können mit isolierten Nachrichten arbeiten, bei denen sie Empfänger sind, wenn die Nachricht als Spam, Massen-E-Mail oder (ab April 2020) Phishing isoliert wurde.</span><span class="sxs-lookup"><span data-stu-id="364ad-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="364ad-115">Weitere Informationen finden Sie unter "Suchen und Veröffentlichen von Nachrichten in Quarantäne [als Benutzer in EOP".](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="364ad-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="364ad-116">Um zu verhindern, dass Benutzer ihre eigenen Phishingnachrichten in Quarantäne  verwalten, können Administratoren eine andere Aktion für die Phishing-E-Mail-Filterungs-Filterung in Antispamrichtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="364ad-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="364ad-117">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="364ad-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="364ad-118">Administratoren und Benutzer können falsch positive Ergebnisse in Quarantäne an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="364ad-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="364ad-119">Weitere Informationen zum Isolieren finden Sie unter ["Häufig gestellte Fragen zur Quarantäne".](quarantine-faq.md)</span><span class="sxs-lookup"><span data-stu-id="364ad-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
