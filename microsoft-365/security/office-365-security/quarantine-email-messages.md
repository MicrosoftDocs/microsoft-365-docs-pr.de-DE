---
title: Quarantäne in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: Quarantäne in Office 365 hält potenziell gefährliche oder unerwünschte Nachrichten. Administratoren und Endbenutzer können auf die Quarantäne zugreifen.
ms.openlocfilehash: d3db036210886f7a4607f477bba2cf9f450ed90c
ms.sourcegitcommit: c876d58b34454f211b50ae5d06f193c1a1e5c4ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2020
ms.locfileid: "43230937"
---
# <a name="quarantine-in-office-365"></a><span data-ttu-id="47e56-104">Quarantäne in Office 365</span><span class="sxs-lookup"><span data-stu-id="47e56-104">Quarantine in Office 365</span></span>

<span data-ttu-id="47e56-105">Wenn Sie ein Office 365 Kunde mit Postfächern in Exchange Online oder einem eigenständigen Exchange Online Schutz-Kunden (EoP) ohne Exchange Online Postfächer sind, ist die Quarantäne verfügbar, um potenziell gefährliche oder unerwünschte Nachrichten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="47e56-105">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="47e56-106">Anti-Malware-Richtlinien isolieren eine Nachricht automatisch *, wenn eine* Anlage Schadsoftware enthält.</span><span class="sxs-lookup"><span data-stu-id="47e56-106">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="47e56-107">Weitere Informationen finden Sie unter [configure Anti-Malware Policies in Office 365](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="47e56-107">For more information, see [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="47e56-108">Standardmäßig werden Phishing-Nachrichten in antispamregeln unter Quarantäne gestellt und Spam-und Massen-e-Mails an den Junk-e-Mail-Ordner des Benutzers übermittelt.</span><span class="sxs-lookup"><span data-stu-id="47e56-108">By default, anti-spam policies quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="47e56-109">Sie können jedoch auch Anti-Spam-Richtlinien erstellen und anpassen, um Spam und Massen-e-Mails zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="47e56-109">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="47e56-110">Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="47e56-110">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="47e56-111">Sowohl Benutzer als auch Administratoren können mit unter Quarantäne gestellten Nachrichten arbeiten:</span><span class="sxs-lookup"><span data-stu-id="47e56-111">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="47e56-112">Administratoren können mit allen Typen von isolierten Nachrichten für alle Benutzer arbeiten.</span><span class="sxs-lookup"><span data-stu-id="47e56-112">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="47e56-113">Nur Administratoren können mit Nachrichten arbeiten, die als Schadsoftware, als hochgradig vertrauenswürdiges Phishing oder als Ergebnis von Nachrichtenfluss Regeln (auch bekannt als Transportregeln) isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="47e56-113">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="47e56-114">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="47e56-114">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="47e56-115">Benutzer können mit isolierten Nachrichten arbeiten, bei denen es sich um einen Empfänger handelt, wenn die Nachricht als Spam, Massen-e-Mails oder (ab April 2020) als Phishing isoliert wurde.</span><span class="sxs-lookup"><span data-stu-id="47e56-115">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="47e56-116">Weitere Informationen finden Sie unter [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="47e56-116">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="47e56-117">Um zu verhindern, dass Benutzer ihre eigenen isolierten Phishing-Nachrichten verwalten, können Administratoren eine andere Aktion für das **Phishing-e-Mail-** Filter Urteil in Anti-Spam-Richtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="47e56-117">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="47e56-118">Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="47e56-118">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="47e56-119">Administratoren und Benutzer können falsch positive Ergebnisse an Microsoft in der Quarantäne melden.</span><span class="sxs-lookup"><span data-stu-id="47e56-119">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="47e56-120">Weitere Informationen zur Quarantäne finden Sie unter [Quarantine FAQ](quarantine-faq.md).</span><span class="sxs-lookup"><span data-stu-id="47e56-120">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
