---
title: Worin besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/7/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: Kunden manchmal askwhat ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mail-Nachrichten? In diesem Thema werden die Unterschiede erläutert und Informationen zu den verschiedenen Optionen bereitgestellt, die sowohl in Exchange Online als auch in Exchange Online Protection verfügbar sind (EoP).
ms.openlocfilehash: 55924ac5e83ca109fd66d1723cdb7c5f43f20df6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895035"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a><span data-ttu-id="08fd5-103">Worin besteht der Unterschied zwischen Junk- und Massen-E-Mail?</span><span class="sxs-lookup"><span data-stu-id="08fd5-103">What's the difference between junk email and bulk email?</span></span>

<span data-ttu-id="08fd5-p101">Kunden fragen mitunter, worin der Unterschied zwischen Junk-E-Mail und Massen-E-Mail bestehe. Zweck dieses Themas ist die Erläuterung des Unterschieds und Bereitstellung von Informationen zu den verschiedenen Optionen, die sowohl in Exchange Online als auch Exchange Online Protection (EOP) zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="08fd5-p101">Customers sometimes ask "what's the difference between junk email and bulk email messages?" The purpose of this topic is to explain the difference and to provide information about the different options that are available for both in Exchange Online and Exchange Online Protection (EOP).</span></span>
  
 <span data-ttu-id="08fd5-106">**Was ist Junk-E-Mail?**</span><span class="sxs-lookup"><span data-stu-id="08fd5-106">**What's junk email?**</span></span>
  
<span data-ttu-id="08fd5-p102">Junk-E-Mail-Nachrichten sind Spamnachrichten, d. h. unerwünschte E-Mail-Nachrichten, die vom Dienst herausgefiltert werden. Standardmäßig weist der Dienst Spamnachrichten basierend auf der Zuverlässigkeit der IP-Adresse des Absenders zurück. Doch wenn eine Nachricht die IP-Adressüberprüfung besteht, aber von den Inhaltsfiltern als Spam eingestuft wird, dann wird die Nachricht in den Junk-E-Mail-Ordner der vorgesehenen Empfänger gesendet.</span><span class="sxs-lookup"><span data-stu-id="08fd5-p102">Junk email messages are "spam" messages, which are unsolicited (and typically unwanted) email messages that are filtered by the service. By default, the service rejects the spam message based on the reputation of the sending IP address. However, if it passes IP inspection but is classified as spam by the content filters, the message is sent to the Junk Email folder of the intended recipients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="08fd5-110">Die für Inhalts gefilterte Nachrichten ausgeführte Aktion kann über Inhaltsfilter Richtlinien in der Exchange-Verwaltungskonsole (EAC) konfiguriert werden, wie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="08fd5-110">The action performed on content-filtered messages is configurable via content filter policies in the Exchange admin center (EAC), as described in [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="08fd5-111">Wenn Sie mit der Spam Klassifizierung nicht einverstanden sind, können Sie Nachrichten, die Sie als Spam oder nicht-Spam bezeichnen, auf verschiedene Weise an Microsoft melden, wie unter [Submit Spam, Non-Spam und Phishing Scam messages to Microsoft for Analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="08fd5-111">Also, if you disagree with the spam classification, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> 
  
 <span data-ttu-id="08fd5-112">**Was ist Massen-E-Mail?**</span><span class="sxs-lookup"><span data-stu-id="08fd5-112">**What's bulk email?**</span></span>
  
<span data-ttu-id="08fd5-p104">Massen-E-Mail ist ein Typ von E-Mail-Nachrichten, der schwieriger zu klassifizieren ist. Während Junk-E-Mail eine ständige Bedrohung darstellt, enthalten Massen-E-Mails eine Werbe- oder Marketingbotschaft, die meist nicht wiederholt gesendet wird. Massen-E-Mail wird von einigen Benutzern gewünscht, die sich ggf. sogar absichtlich für den Empfang dieser Nachrichten angemeldet haben, während andere Benutzer diese Nachrichtentypen als Spam betrachten. Einige Benutzer möchten beispielsweise Werbe-E-Mails von der Contoso Corporation oder Einladungen zu einer bevorstehenden Konferenz zur Internetsicherheit erhalten, während für andere Benutzer diese Nachrichten Spam sind.</span><span class="sxs-lookup"><span data-stu-id="08fd5-p104">Bulk email, also referred to as gray mail, is a type of email message that's more difficult to classify. Whereas junk email is a constant threat, bulk email is typically comprised of an advertisement or marketing message that's not likely to get sent repeatedly. Bulk email is wanted by some users, and in fact they may have deliberately signed up to receive these messages, while other users may consider these types of messages to be spam. For example, some users want to receive advertising emails from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider such emails to be spam.</span></span>
  
## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="08fd5-117">Umgang mit Massen-E-Mails</span><span class="sxs-lookup"><span data-stu-id="08fd5-117">How to manage bulk email</span></span>

<span data-ttu-id="08fd5-p105">Der Umgang mit Massen-E-Mails ist nicht ganz einfach, denn wenn alle Massen-E-Mails als Spam eingestuft werden, beschweren sich ggf. die Benutzer, die diese erhalten möchten, und melden sie als falsch positive (Nicht-Spam) Nachricht, die fälschlicherweise als Spam eingestuft wurde. Wenn sämtliche Massen-E-Mails dagegen zugelassen werden, beschweren sich ggf. die Benutzer, die diese nicht wollen, und melden sie als nicht abgefangene Spamnachricht, die fälschlicherweise in ihrem Posteingang gelandet ist.</span><span class="sxs-lookup"><span data-stu-id="08fd5-p105">How to manage bulk email isn't a clear cut decision, because if all bulk email is classified as spam, the users that want it may complain and submit it as a false positive (non-spam) message that was wrongly marked as spam. On the other hand, if all bulk email is let through, the users that don't want it may complain and submit it as a missed spam message (false negative) that wrongly arrived in their inbox.</span></span>
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a><span data-ttu-id="08fd5-120">Aktivieren der erweiterten Option zur Filterung von Spam-Massensendungen</span><span class="sxs-lookup"><span data-stu-id="08fd5-120">Enable bulk mail sensitivity control in the content filter policy</span></span>

<span data-ttu-id="08fd5-121">Je nach Richtlinie Ihres Unternehmens für Massen-e-Mail-Nachrichten können Administratoren einen Schwellenwert auswählen, um die Massen-e-Mail zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="08fd5-121">Depending on your company's policy on bulk email messages, admins can select a threshold to assign the bulk email.</span></span> <span data-ttu-id="08fd5-122">Die Einstellung kann über Inhaltsfilter Richtlinien in der Exchange-Verwaltungskonsole konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="08fd5-122">The setting is configurable via content filter policies in the EAC.</span></span> <span data-ttu-id="08fd5-123">Weitere Informationen finden Sie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md) for the steps.</span><span class="sxs-lookup"><span data-stu-id="08fd5-123">Check out [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md) for the steps.</span></span> <span data-ttu-id="08fd5-124">Sie können eine Schwellenwerteinstellung von 1-9 auswählen, wobei 1 die meisten Massen-e-Mails als Spam markiert, und 9 ermöglicht die Zustellung der meisten Massen-e-Mails.</span><span class="sxs-lookup"><span data-stu-id="08fd5-124">You can choose a threshold setting from 1-9, where 1 marks most bulk email as spam, and 9 allows most bulk email to be delivered.</span></span> <span data-ttu-id="08fd5-125">Der Dienst führt dann die konfigurierte Aktion aus, z. B. das Verschieben der Nachricht in den Junk-E-Mail-Ordner des Empfängers.</span><span class="sxs-lookup"><span data-stu-id="08fd5-125">The service then performs the configured action, such as sending the message to the recipient's Junk Email folder.</span></span> 
  

