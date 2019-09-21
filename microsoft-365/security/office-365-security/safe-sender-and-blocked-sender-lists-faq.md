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
ms.openlocfilehash: 5b1082e0a8f492da1ebc559b0958a6ef76f9a70c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082570"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="8e83b-104">Listen sicherer und blockierter Absender in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8e83b-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="8e83b-p102">Als Exchange Online- oder Exchange Online Protection-Administrator (EOP) können Sie sicherstellen, dass eine E-Mail-Nachricht, die den Dienst durchläuft, nicht als Spam gekennzeichnet wird. Eine Möglichkeit hierzu ist das Erstellen von Listen mit sicheren Absendern und blockierten Absendern für die Personen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="8e83b-p102">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam. One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span> 
  
 <span data-ttu-id="8e83b-107">*Informationen zum Verwenden dieser Listen als Administrator finden Sie in der aktuellen Version der Tipps und Verfahren unter* [Verhindern der Kennzeichnung von falsch positiver E-Mail als Spam mithilfe einer Liste sicherer Adressen oder anderer Techniken](https://go.microsoft.com/fwlink/p/?LinkID=534224).</span><span class="sxs-lookup"><span data-stu-id="8e83b-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [Prevent false positive email marked as spam with a safelist or other techniques](https://go.microsoft.com/fwlink/p/?LinkID=534224).</span></span> 
  
<span data-ttu-id="8e83b-108">Wenn Sie kein Administrator sind und einfach nur Ihre eigenen Junk-E-Mails in Outlook mithilfe einer Liste sicherer Absender verwalten möchten, sehen Sie sich die Schritte in diesem Überblick [der Junk-Filter](https://go.microsoft.com/fwlink/?LinkId=817222) an.</span><span class="sxs-lookup"><span data-stu-id="8e83b-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in this overview of [the Junk Email Filter](https://go.microsoft.com/fwlink/?LinkId=817222).</span></span> 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="8e83b-109">Was sind die Grenzwerte sicherer und blockierter Absender in Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="8e83b-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="8e83b-p103">Die Grenzwerte sicherer und blockierter Absender in Exchange Online unterscheiden sich von den Grenzwerten von Active Directory und Outlook. Dies sind:</span><span class="sxs-lookup"><span data-stu-id="8e83b-p103">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits. They are:</span></span>
  
- <span data-ttu-id="8e83b-112">Grenzwert sicherer Absender: 1.024</span><span class="sxs-lookup"><span data-stu-id="8e83b-112">Safe sender limit: 1,024</span></span>
    
- <span data-ttu-id="8e83b-113">Grenzwert blockierter Absender: 500</span><span class="sxs-lookup"><span data-stu-id="8e83b-113">Blocked sender limit: 500</span></span>
    
<span data-ttu-id="8e83b-114">Hinweis:</span><span class="sxs-lookup"><span data-stu-id="8e83b-114">Note:</span></span>
  
<span data-ttu-id="8e83b-115">Sie können den in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)beschriebenen Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="8e83b-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="8e83b-116">Um dieses Problem zu beheben, deaktivieren Sie das Kontrollkästchen „E-Mails von meinen Kontakten vertrauen".</span><span class="sxs-lookup"><span data-stu-id="8e83b-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="8e83b-117">Alternativ verringern Sie die Anzahl der e-Mail-Adressen, die sich in Ihrem Standardordner Kontakte befinden, so, dass Sie innerhalb des zulässigen Höchstwerts von 1024 in Exchange Online, die für das Attribut "Parameter MaxSafeSenders" festgelegt sind, zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8e83b-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="8e83b-118">Weitere Informationen über dieses Attribut und das Cmdlet „Set-Mailbox" finden Sie in dem folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="8e83b-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>
  
[<span data-ttu-id="8e83b-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="8e83b-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)
  
## <a name="see-also"></a><span data-ttu-id="8e83b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e83b-120">See also</span></span>

[<span data-ttu-id="8e83b-121">Sender filtering in Exchange 2016</span><span class="sxs-lookup"><span data-stu-id="8e83b-121">Sender filtering in Exchange 2016</span></span>](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)

