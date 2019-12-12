---
title: Listen sicherer und blockierter Absender in Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Als Exchange Online- oder Exchange Online Protection-Administrator (EOP) können Sie sicherstellen, dass eine E-Mail-Nachricht, die den Dienst durchläuft, nicht als Spam gekennzeichnet wird. Eine Möglichkeit hierzu ist das Erstellen von Listen mit sicheren Absendern und blockierten Absendern für die Personen in Ihrer Organisation.
ms.openlocfilehash: 5530fa8c8ee5a83c4e8515a8f31f91e45b2ec97b
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971673"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="63751-104">Listen sicherer und blockierter Absender in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="63751-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="63751-p102">Als Exchange Online- oder Exchange Online Protection-Administrator (EOP) können Sie sicherstellen, dass eine E-Mail-Nachricht, die den Dienst durchläuft, nicht als Spam gekennzeichnet wird. Eine Möglichkeit hierzu ist das Erstellen von Listen mit sicheren Absendern und blockierten Absendern für die Personen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="63751-p102">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam. One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span>

<span data-ttu-id="63751-107">*Lesen Sie die aktualisierte Version der Tipps und Verfahren für die Verwendung dieser Listen als Administrator* , [um zu verhindern, dass gute e-Mails in Office 365 als Spam gekennzeichnet werden](https://docs.microsoft.com/microsoft-365/compliance/prevent-email-from-being-marked-as-spam).</span><span class="sxs-lookup"><span data-stu-id="63751-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [How to prevent good email from being marked as spam in Office 365](https://docs.microsoft.com/microsoft-365/compliance/prevent-email-from-being-marked-as-spam).</span></span>

<span data-ttu-id="63751-108">Wenn Sie kein Administrator sind und nur Ihre eigenen Junk-e-Mails in Outlook mithilfe einer Liste sicherer Absender verwalten möchten, lesen Sie die Schritte in der Übersicht über[den Junk-e-Mail-Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span><span class="sxs-lookup"><span data-stu-id="63751-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in the[Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="63751-109">Was sind die Grenzwerte sicherer und blockierter Absender in Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="63751-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="63751-p103">Die Grenzwerte sicherer und blockierter Absender in Exchange Online unterscheiden sich von den Grenzwerten von Active Directory und Outlook. Dies sind:</span><span class="sxs-lookup"><span data-stu-id="63751-p103">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits. They are:</span></span>

- <span data-ttu-id="63751-112">Grenzwert sicherer Absender: 1.024</span><span class="sxs-lookup"><span data-stu-id="63751-112">Safe sender limit: 1,024</span></span>

- <span data-ttu-id="63751-113">Grenzwert blockierter Absender: 500</span><span class="sxs-lookup"><span data-stu-id="63751-113">Blocked sender limit: 500</span></span>

<span data-ttu-id="63751-114">Hinweis:</span><span class="sxs-lookup"><span data-stu-id="63751-114">Note:</span></span>

<span data-ttu-id="63751-115">Sie können den in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)beschriebenen Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="63751-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="63751-116">Um dieses Problem zu beheben, deaktivieren Sie das Kontrollkästchen „E-Mails von meinen Kontakten vertrauen".</span><span class="sxs-lookup"><span data-stu-id="63751-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="63751-117">Alternativ verringern Sie die Anzahl der e-Mail-Adressen, die sich in Ihrem Standardordner Kontakte befinden, so, dass Sie innerhalb des zulässigen Höchstwerts von 1024 in Exchange Online, die für das Attribut "Parameter MaxSafeSenders" festgelegt sind, zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="63751-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="63751-118">Weitere Informationen über dieses Attribut und das Cmdlet „Set-Mailbox" finden Sie in dem folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="63751-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>

[<span data-ttu-id="63751-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="63751-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a><span data-ttu-id="63751-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63751-120">See also</span></span>

[<span data-ttu-id="63751-121">Absenderfilterung in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="63751-121">Sender filtering in Exchange Server</span></span>](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
