---
title: Melden von Spam-, Nichtspam- und Phishingnachrichten an Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Administratoren können sich über die verschiedenen Möglichkeiten zum Melden von guten und fehlerhaften Nachrichten und Dateien an Microsoft zur Analyse informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a89ea8a41a31c9544284566fade0e603d48af759
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082816"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="d2061-103">Melden von Nachrichten und Dateien an Microsoft</span><span class="sxs-lookup"><span data-stu-id="d2061-103">Report messages and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d2061-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="d2061-104">**Applies to**</span></span>
- [<span data-ttu-id="d2061-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d2061-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d2061-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="d2061-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d2061-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2061-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d2061-108">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer verfügen Benutzer und Administratoren über verschiedene Methoden zum Melden von E-Mail-Nachrichten und Dateien an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d2061-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, both users and admins have several different methods for reporting email messages and files to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="d2061-109">Methode</span><span class="sxs-lookup"><span data-stu-id="d2061-109">Method</span></span>|<span data-ttu-id="d2061-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2061-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="d2061-111">Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln</span><span class="sxs-lookup"><span data-stu-id="d2061-111">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="d2061-112">Die empfohlene Berichtsmethode für Administratoren in Organisationen mit Exchange Online Postfächern (nicht in eigenständiger EOP verfügbar).</span><span class="sxs-lookup"><span data-stu-id="d2061-112">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="d2061-113">Aktivieren der Add-Ins "Berichtnachricht" oder "Phishing melden"</span><span class="sxs-lookup"><span data-stu-id="d2061-113">Enable the Report Message or the Report Phishing add-ins</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="d2061-114">Funktioniert mit Outlook und Outlook im Web (früher als Outlook Web App bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="d2061-114">Works with Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <p> <span data-ttu-id="d2061-115">Je nach Abonnement sind Nachrichten, die Benutzer mit den Add-Ins gemeldet haben, im [Portal für Administratorübermittlungen,](admin-submission.md)in air-Ergebnissen [(Automated investigation and response),](air-view-investigation-results.md)im [Bericht "Benutzerbericht"](view-email-security-reports.md#user-reported-messages-report)und im [Explorer](threat-explorer-views.md#email--submissions)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d2061-115">Depending on your subscription, messages that users reported with the add-ins are available in [the Admin Submissions portal](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Explorer](threat-explorer-views.md#email--submissions).</span></span> <p> <span data-ttu-id="d2061-116">Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen angegebenes Postfach kopiert oder umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="d2061-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="d2061-117">Weitere Informationen finden Sie unter [Richtlinien für Benutzerübermittlungen.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="d2061-117">For more information, see [User submissions policies](user-submission.md).</span></span>
|[<span data-ttu-id="d2061-118">Melden falsch positiver und falsch negativer Ergebnisse in Outlook</span><span class="sxs-lookup"><span data-stu-id="d2061-118">Report false positives and false negatives in Outlook</span></span>](report-false-positives-and-false-negatives.md)|<span data-ttu-id="d2061-119">Senden Sie falsch positive Ergebnisse (gute E-Mails, die blockiert oder an Junk-Ordner gesendet wurden) und falsch negative Ergebnisse (unerwünschte E-Mails oder Phishingnachrichten, die an den Posteingang übermittelt wurden) mithilfe der Funktion "Nachricht melden" an Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="d2061-119">Submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP) using the Report Message feature.</span></span>|
|[<span data-ttu-id="d2061-120">Manuelles Übermitteln von Nachrichten zur Analyse an Microsoft</span><span class="sxs-lookup"><span data-stu-id="d2061-120">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="d2061-121">Senden Sie angefügte Nachrichten manuell an bestimmte Microsoft-E-Mail-Adressen für Spam, nicht für Spam und Phishing.</span><span class="sxs-lookup"><span data-stu-id="d2061-121">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span>|
|[<span data-ttu-id="d2061-122">Verwenden von Nachrichtenflussregeln, um anzuzeigen, was Ihre Benutzer an Microsoft melden</span><span class="sxs-lookup"><span data-stu-id="d2061-122">Use mail flow rules to see what users are reporting to Microsoft</span></span>](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|<span data-ttu-id="d2061-123">Erfahren Sie, wie Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet) erstellen, die Sie benachrichtigt, wenn Benutzer Nachrichten zur Analyse an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="d2061-123">Learn how to create a mail flow rule (also known as a transport rule) that notifies you when users report messages to Microsoft for analysis.</span></span>|
|[<span data-ttu-id="d2061-124">Übermitteln von Schadsoftware und Nicht-Schadsoftware zur Analyse an Microsoft</span><span class="sxs-lookup"><span data-stu-id="d2061-124">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="d2061-125">Verwenden Sie die Microsoft Security Intelligence Website, um Anlagen und andere Dateien zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="d2061-125">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="d2061-126">Wenn die Spam- oder Phishingnachrichten in Quarantäne gestellt wurden, anstatt zugestellt zu werden, können Benutzer die Nachrichten aus der Quarantäne im Microsoft 365 Defender-Portal an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="d2061-126">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from Quarantine in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="d2061-127">Ausführliche Informationen finden Sie unter [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Microsoft 365.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="d2061-127">For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d2061-128">Daten aus Übermittlungen an Microsoft befinden sich in der Office 365 Compliance-Grenze in nordamerikanischen Rechenzentren.</span><span class="sxs-lookup"><span data-stu-id="d2061-128">Data from submissions to Microsoft resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="d2061-129">Die Daten werden von Analysten des Entwicklungsteams überprüft, um die Effektivität der Filter zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="d2061-129">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>
