---
title: Melden von Junk- und Phishing-E-Mails in Outlook für iOS und Android
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratoren können sich über die integrierten Junk-E-Mail-, nicht Junk- und Phishing-E-Mail-Berichtsoptionen in Outlook für iOS und Android informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3e3a2d77c978649e7496d09f78301add397fb9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289173"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="7f186-103">Melden von Junk- und Phishing-E-Mails in Outlook für iOS und Android in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7f186-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7f186-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="7f186-104">**Applies to**</span></span>
- [<span data-ttu-id="7f186-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7f186-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7f186-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="7f186-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="7f186-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f186-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="7f186-108">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder lokalen Postfächern, die moderne Hybridauthentifizierung [verwenden,](../../enterprise/hybrid-modern-auth-overview.md)können Sie die integrierten Berichtsoptionen in Outlook für iOS und Android verwenden, um falsch positive Ergebnisse (gute E-Mails, die als Spam gekennzeichnet sind), falsch negative Ergebnisse (ungültige E-Mails sind zulässig) und Phishingnachrichten an Exchange Online Protection (EOP) zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="7f186-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7f186-109">Was müssen Sie wissen, bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="7f186-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="7f186-110">Für eine optimale Benutzerübermittlung empfehlen wir die Verwendung der Add-Ins "Nachricht melden" und "Phishing melden". Weitere Informationen finden Sie unter "Aktivieren [des Berichtsnachrichten-Add-Ins"](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) und ["Aktivieren des Phishing-Add-Ins".](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in)</span><span class="sxs-lookup"><span data-stu-id="7f186-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) and [Enable the Report Phishing add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) for more information.</span></span>

- <span data-ttu-id="7f186-111">Wenn Sie ein Administrator in einer Organisation mit Exchange Online-Postfächern sind, empfehlen wir die Verwendung des Übermittlungsportals im Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="7f186-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="7f186-112">Weitere Informationen finden Sie unter ["Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft ".](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="7f186-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="7f186-113">Sie können gemeldete Nachrichten so konfigurieren, dass sie kopiert oder an ein von Ihnen festgelegtes Postfach umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="7f186-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="7f186-114">Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="7f186-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="7f186-115">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter ["Melden von Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="7f186-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="7f186-116">Wenn die Junk-E-Mail-Berichterstellung für Outlook in der Benutzerübermittlungsrichtlinie deaktiviert ist, werden Junk- oder Phishingnachrichten in den Junk-E-Mail-Ordner verschoben und nicht an Ihren Administrator oder Microsoft gemeldet.</span><span class="sxs-lookup"><span data-stu-id="7f186-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>