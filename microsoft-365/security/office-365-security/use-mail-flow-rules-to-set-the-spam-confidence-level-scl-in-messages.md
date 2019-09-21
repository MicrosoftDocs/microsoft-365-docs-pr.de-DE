---
title: Verwenden von Nachrichtenflussregeln zum Festlegen der SCL-Bewertung (Spam Confidence Level) in Nachrichten
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie die SCL-Bewertung von Nachrichten in Exchange Online Schutz festlegen.
ms.openlocfilehash: 627284a1c2a7463989ca3050b2becbff780cf3d6
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082389"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="76958-103">Verwenden von Nachrichtenflussregeln zum Festlegen der SCL-Bewertung (Spam Confidence Level) in Nachrichten</span><span class="sxs-lookup"><span data-stu-id="76958-103">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="76958-104">Sie können eine e-Mail-Fluss Regel (auch als Transportregel bezeichnet) erstellen, mit der die SCL-Bewertung (Spam Confidence Level) einer e-Mail-Nachricht festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="76958-104">You can create a mail flow rule (also known as a transport rule) that sets the spam confidence level (SCL) of an email message.</span></span> <span data-ttu-id="76958-105">Die SCL-Bewertung ist ein Maßstab dafür, wie wahrscheinlich es ist, dass es sich bei einer Nachricht um Spam handelt.</span><span class="sxs-lookup"><span data-stu-id="76958-105">The SCL is a measure of how likely a message is to be spam.</span></span> <span data-ttu-id="76958-106">Spam sind unverlangt zugesandte (und normalerweise unerwünschte) E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="76958-106">Spam is unsolicited (and typically unwanted) email messages.</span></span> <span data-ttu-id="76958-107">Dieser Dienst kann verschiedene Aktionen für eine Nachricht ausführen, die von ihrer SCL-Bewertung abhängen.</span><span class="sxs-lookup"><span data-stu-id="76958-107">The service takes different action on a message depending on its SCL rating.</span></span> <span data-ttu-id="76958-108">Beispielsweise können Sie die Spam Inhaltsfilterung für Nachrichten umgehen, die von Personen innerhalb Ihrer Organisation gesendet werden, da Sie darauf vertrauen, dass eine intern von einem Kollegen gesendete Nachricht kein Spam ist.</span><span class="sxs-lookup"><span data-stu-id="76958-108">For example, you might want to bypass spam content filtering for messages that are sent from people inside your organization because you trust that a message sent internally from a colleague isn't spam.</span></span> <span data-ttu-id="76958-109">Durch die Verwendung von Nachrichtenfluss Regeln zum Festlegen des SCL-Werts einer Nachricht erhalten Sie eine erhöhte Kontrolle bei der Verarbeitung von Spam.</span><span class="sxs-lookup"><span data-stu-id="76958-109">Using mail flow rules to set the SCL value of a message gives you increased control in handling spam.</span></span> 
  
 <span data-ttu-id="76958-110">**Was sollten Sie wissen, bevor Sie beginnen?**</span><span class="sxs-lookup"><span data-stu-id="76958-110">**What do you need to know before you begin?**</span></span>
  
- <span data-ttu-id="76958-111">Geschätzte Zeit bis zum Abschließen dieses Verfahrens: 10 Minuten.</span><span class="sxs-lookup"><span data-stu-id="76958-111">Estimated time to complete this procedure: 10 minutes.</span></span>
    
- <span data-ttu-id="76958-112">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="76958-112">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="76958-113">Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Nachrichtenfluss Regeln" in [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) oder [Feature Permissions in EoP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="76958-113">To see what permissions you need, see the "Mail flow rules" entry in [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) or [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span> 
    
- <span data-ttu-id="76958-114">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="76958-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
    
### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="76958-115">So erstellen Sie eine Nachrichtenfluss Regel, die den SCL-Wert einer Nachricht festlegt</span><span class="sxs-lookup"><span data-stu-id="76958-115">To create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="76958-116">Navigieren Sie in der Exchange-Verwaltungskonsole (EAC) zu **Nachrichtenfluss** \> **Regeln**.</span><span class="sxs-lookup"><span data-stu-id="76958-116">In the Exchange admin center (EAC), choose **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="76958-117">Klicken Sie auf **Neu**![Hinzufügen (Symbol)](../media/ITPro-EAC-AddIcon.gif), und wählen Sie dann **Eine neue Regel erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="76958-117">Choose **New**![Add Icon](../media/ITPro-EAC-AddIcon.gif), and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="76958-118">Geben Sie einen Namen für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="76958-118">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="76958-119">Klicken Sie auf **Weitere Optionen**, und geben Sie anschließend unter **Diese Regel anwenden, wenn** eine Bedingung an, durch die die Aktion ausgelöst wird, die Sie für diese Regel festlegen (in diesem Falle die Festlegung des SCL-Werts).</span><span class="sxs-lookup"><span data-stu-id="76958-119">Choose **More options**, and then under **Apply this rule if**, specify a condition that will trigger the action you'll be setting for this rule (which is to set the SCL value).</span></span>
    
    <span data-ttu-id="76958-120">Sie können z. B. festlegen **Der Absender** \> **ist intern/extern** und anschließend im Dialogfeld **Absenderposition auswählen** auf die Option **Innerhalb meiner Organisation** und auf **OK** klicken.</span><span class="sxs-lookup"><span data-stu-id="76958-120">For example, you can set **The sender** \> **is internal/external**, and then in the **select sender location** dialog box, select **Inside the organization**, and choose **ok**.</span></span><br/>
    <span data-ttu-id="76958-121">![Absenderstandort auswählen](../media/EOP-ETR-SetSCL-1.jpg)</span><span class="sxs-lookup"><span data-stu-id="76958-121">![Select sender location](../media/EOP-ETR-SetSCL-1.jpg)</span></span>
  
5. <span data-ttu-id="76958-122">Wählen Sie unter **Gehen Sie folgendermaßen vor...** die Option **Nachrichteneigenschaften ändern** \> **SCL-Bewertung (Spam Confidence Level) festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="76958-122">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
  
6. <span data-ttu-id="76958-123">Wählen sie im Dialogfeld **SCL angeben** einen der folgenden Werte aus, und klicken Sie auf **OK**:</span><span class="sxs-lookup"><span data-stu-id="76958-123">In the **specify SCL** dialog box, select one of the following values, and choose **ok**:</span></span>
    
  - <span data-ttu-id="76958-124">**Spamfilter umgehen** - Mit dieser Option wird der SCL-Wert auf -1 gesetzt, was bedeutet, dass keine Inhaltsfilterung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="76958-124">**Bypass spam filtering** - This sets the SCL to -1, which means that content filtering won't be performed.</span></span> 
    
  - <span data-ttu-id="76958-125">**0-4** - Wenn Sie den SCL auf einen dieser Werte setzen, wird die Nachricht zur weiteren Verarbeitung an den Inhaltsfilter weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="76958-125">**0-4** - When you set the SCL to one of these values, the message will be passed along to the content filter for additional processing.</span></span> 
    
  - <span data-ttu-id="76958-p103">**5, 6** - Wenn Sie den SCL auf einen dieser Werte setzen, wird die Aktion durchgeführt, die in der entsprechenden Inhaltsfilterrichtlinie für **Spam** festgelegt ist. Die Standardaktion ist das Senden der Nachricht an den Junk-E-Mail-Ordner des Empfängers.</span><span class="sxs-lookup"><span data-stu-id="76958-p103">**5, 6** - When you set the SCL to one of these values, the action specified for **Spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
  - <span data-ttu-id="76958-p104">**7-9** - Wenn Sie den SCL auf einen dieser Werte setzen, wird die Aktion durchgeführt, die in der entsprechenden Inhaltsfilterrichtlinie für **Nachricht mit hoher Spamwahrscheinlichkeit** festgelegt ist. Die Standardaktion ist das Senden der Nachricht an den Junk-E-Mail-Ordner des Empfängers.</span><span class="sxs-lookup"><span data-stu-id="76958-p104">**7-9** - When you set the SCL to one of these values, the action specified for **High confidence spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
    <span data-ttu-id="76958-p105">Weitere Informationen zum Konfigurieren Ihrer Inhaltsfilterrichtlinien finden Sie unter [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md). Weitere Informationen zu SCL-Werten in diesem Dienst finden Sie unter [SCL-Bewertungen (Spam Confidence Level)](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="76958-p105">For more information about configuring your content filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
7. <span data-ttu-id="76958-132">Geben Sie zusätzliche Eigenschaften für die Regel an, und wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="76958-132">Specify additional properties for the rule, and choose **save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="76958-133">Weitere Informationen zu den zusätzlichen Eigenschaften, die Sie für diese Regel auswählen oder angeben können, finden Sie unter [Verwenden der Exchange-Verwaltungskonsole zum Erstellen von Nachrichtenfluss Regeln](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="76958-133">For more information about the additional properties you can select or specify for this rule, see [Use the EAC to create mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules).</span></span> 
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="76958-134">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="76958-134">How do you know this worked?</span></span>

<span data-ttu-id="76958-p106">Wenn Sie verifizieren möchten, dass das Verfahren ordnungsgemäß funktioniert, senden Sie eine E-Mail-Nachricht an einen Mitarbeiter in Ihrer Organisation, und prüfen Sie, ob die erwartete Aktion mit der Nachricht durchgeführt wird. Wenn Sie z. B. **den SCL-Wert (Spam Confidence Level)** auf **Spamfilterung umgehen** setzen, sollte die Nachricht an das Postfach des angegebenen Empfängers gesendet werden. Wenn Sie allerdings **den SCL-Wert (Spam Confidence Level)** auf **9** gesetzt haben und die Aktion in der entsprechenden Inhaltsfilterungsrichtlinie für eine **Nachricht mit hoher Spamwahrscheinlichkeit** darin besteht, die Nachricht in den Junk-E-Mail-Ordner zu verschieben, sollte die Nachricht an den Junk-E-Mail-Ordner des angegebenen Empfängers gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="76958-p106">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected. For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox. However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span> 
  

