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
description: Administratoren können sich über die integrierten Junk- und nicht Junk- und Phishing-E-Mail-Berichtsoptionen in Outlook für iOS und Android informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2c95f7b32d0d395e164d218c994b1608d36018d5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206611"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="900eb-103">Melden von Junk- und Phishing-E-Mails in Outlook für iOS und Android in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="900eb-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="900eb-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="900eb-104">**Applies to**</span></span>
- [<span data-ttu-id="900eb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="900eb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="900eb-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="900eb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="900eb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="900eb-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="900eb-108">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder lokalen Postfächern [](../../enterprise/hybrid-modern-auth-overview.md)mit moderner Hybridauthentifizierung können Sie falsch positive Nachrichten (gute E-Mails, die als Spam gekennzeichnet sind), falsch negative Nachrichten (ungültige E-Mails zulässig) und Phishingnachrichten an Exchange Online Protection (EOP) senden.</span><span class="sxs-lookup"><span data-stu-id="900eb-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="900eb-109">Was müssen Sie wissen, bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="900eb-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="900eb-110">Für eine optimale Benutzerübermittlung empfehlen wir die Verwendung der Berichtsnachricht und der Phishing-Add-Ins melden. Weitere [Informationen finden Sie unter Enable the Report Message add-in](./enable-the-report-message-add-in.md) und Enable the Report Phishing [add-in.](./enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="900eb-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](./enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](./enable-the-report-phish-add-in.md) for more information.</span></span>

- <span data-ttu-id="900eb-111">Wenn Sie ein Administrator in einer Organisation mit Exchange Online sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="900eb-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="900eb-112">Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="900eb-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="900eb-113">Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen festgelegtes Postfach kopiert oder umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="900eb-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="900eb-114">Weitere Informationen finden Sie unter [Richtlinien für Benutzerübermittlungen](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="900eb-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="900eb-115">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="900eb-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="900eb-116">Wenn die Junk-E-Mail Outlook in der Benutzerübermittlungsrichtlinie deaktiviert ist, werden Junk- oder Phishingnachrichten in den Junkordner verschoben und nicht an Ihren Administrator oder Microsoft gemeldet.</span><span class="sxs-lookup"><span data-stu-id="900eb-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>