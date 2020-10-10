---
title: E-Mail-Nachrichten in Quarantäne
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
- m365-initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratoren können Informationen zur Quarantäne in Exchange Online Protection (EoP) erhalten, die potenziell gefährliche oder unerwünschte Nachrichten enthält.
ms.openlocfilehash: a5e18ff4b1573e8aa2e7c6b58ab291d3dfb84d81
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412418"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="8c9f0-103">Isolierte e-Mail-Nachrichten in EoP</span><span class="sxs-lookup"><span data-stu-id="8c9f0-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8c9f0-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer steht die Quarantäne zur Verfügung, um potenziell gefährliche oder unerwünschte Nachrichten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8c9f0-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="8c9f0-105">Anti-Malware-Richtlinien isolieren eine Nachricht automatisch *, wenn eine* Anlage Schadsoftware enthält.</span><span class="sxs-lookup"><span data-stu-id="8c9f0-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="8c9f0-106">Weitere Informationen finden Sie unter [configure Anti-Malware Policies in EoP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8c9f0-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="8c9f0-107">Standardmäßig werden Phishing-Nachrichten von Anti-Spam Policies isoliert und Spam-und Massen-e-Mails an den Junk-e-Mail-Ordner des Benutzers übermittelt.</span><span class="sxs-lookup"><span data-stu-id="8c9f0-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="8c9f0-108">Sie können jedoch auch Anti-Spam-Richtlinien erstellen und anpassen, um Spam und Massen-e-Mails zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="8c9f0-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="8c9f0-109">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8c9f0-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="8c9f0-110">Sowohl Benutzer als auch Administratoren können mit unter Quarantäne gestellten Nachrichten arbeiten:</span><span class="sxs-lookup"><span data-stu-id="8c9f0-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="8c9f0-111">Administratoren können mit allen Typen von isolierten Nachrichten für alle Benutzer arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8c9f0-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="8c9f0-112">Nur Administratoren können mit Nachrichten arbeiten, die als Schadsoftware, als hochgradig vertrauenswürdiges Phishing oder als Ergebnis von Nachrichtenfluss Regeln (auch bekannt als Transportregeln) isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="8c9f0-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="8c9f0-113">Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="8c9f0-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="8c9f0-114">Benutzer können mit isolierten Nachrichten arbeiten, bei denen es sich um einen Empfänger handelt, wenn die Nachricht als Spam, Massen-e-Mails oder (ab April 2020) als Phishing isoliert wurde.</span><span class="sxs-lookup"><span data-stu-id="8c9f0-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="8c9f0-115">Weitere Informationen finden Sie unter [Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer in EoP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="8c9f0-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="8c9f0-116">Um zu verhindern, dass Benutzer ihre eigenen isolierten Phishing-Nachrichten verwalten, können Administratoren eine andere Aktion für das **Phishing-e-Mail-** Filter Urteil in Anti-Spam-Richtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8c9f0-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="8c9f0-117">Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8c9f0-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="8c9f0-118">Administratoren und Benutzer können falsch positive Ergebnisse an Microsoft in der Quarantäne melden.</span><span class="sxs-lookup"><span data-stu-id="8c9f0-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="8c9f0-119">Weitere Informationen zur Quarantäne finden Sie unter [Quarantine FAQ](quarantine-faq.md).</span><span class="sxs-lookup"><span data-stu-id="8c9f0-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
