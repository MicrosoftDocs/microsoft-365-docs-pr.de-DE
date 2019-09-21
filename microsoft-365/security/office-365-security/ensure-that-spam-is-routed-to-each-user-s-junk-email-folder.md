---
title: Sicherstellen, dass Spam an die Junk-E-Mail-Ordner der einzelnen Benutzer geleitet wird
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Spam an Benutzer-Junk-e-Mail-Ordner in Exchange Online Schutz weiterleiten.
ms.openlocfilehash: dc37f2428e009f00a2d6d9dd15d5d2cd505f267a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081311"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="8263a-103">Sicherstellen, dass Spam an die Junk-E-Mail-Ordner der einzelnen Benutzer geleitet wird</span><span class="sxs-lookup"><span data-stu-id="8263a-103">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8263a-p101">Dieses Thema bezieht sich nur auf Exchange Online Protection (EOP)-Kunden, die Postfächer lokal in einer Hybridbereitstellung hosten. Exchange Online-Kunden, deren Postfächer vollständig in Office 365 gehostet werden, müssen diese Befehle nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="8263a-p101">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment. Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span> 
  
<span data-ttu-id="8263a-106">Die standardmäßige Antispamaktion für EOP-Kunden ist das Verschieben von Spamnachrichten in den Junk-E-Mail-Ordner der Empfänger.</span><span class="sxs-lookup"><span data-stu-id="8263a-106">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder.</span></span> <span data-ttu-id="8263a-107">Damit diese Aktion mit lokalen Postfächern funktioniert, müssen Sie Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln) auf Ihren lokalen Edge-oder Hub-Servern konfigurieren, um von EoP hinzugefügte Spam Kopfzeilen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="8263a-107">In order for this action to work with on-premises mailboxes, you must configure Exchange mail flow rules (also known as transport rules) on your on-premises Edge or Hub servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="8263a-108">Mit diesen Nachrichtenfluss Regeln wird die SCL-Bewertung (Spam Confidence Level) festgelegt, die von der SclJunkThreshold-Eigenschaft des Cmdlets-OrganizationConfig verwendet wird, um Spam in den Junk-e-Mail-Ordner jedes Postfachs zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="8263a-108">These mail flow rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span> 
  
### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="8263a-109">So fügen Sie Nachrichtenfluss Regeln hinzu, um sicherzustellen, dass Spam mithilfe von Windows PowerShell in den Junk-e-Mail-Ordner verschoben wird</span><span class="sxs-lookup"><span data-stu-id="8263a-109">To add mail flow rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="8263a-p103">Greifen Sie auf den Exchange-Verwaltungsshell für den lokalen Exchange-Server zu. Wie eine Exchange-Verwaltungsshell in Ihrer lokalen Exchange-Organisation geöffnet wird, erfahren Sie unter **Open the Shell**.</span><span class="sxs-lookup"><span data-stu-id="8263a-p103">Access the Exchange Management Shell for your on-premises Exchange server. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>
    
2. <span data-ttu-id="8263a-112">Führen Sie den folgenden Befehl aus, um bei der Inhaltsfilterung erkannte Spamnachrichten in den Junk-E-Mail-Ordner weiterzuleiten:</span><span class="sxs-lookup"><span data-stu-id="8263a-112">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    <span data-ttu-id="8263a-113">Dabei ist  _NameForRule_ der Name für die neue Regel, z. B. „JunkContentFilteredMail".</span><span class="sxs-lookup"><span data-stu-id="8263a-113">Where  _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span> 
    
3. <span data-ttu-id="8263a-114">Führen Sie den folgenden Befehl aus, um als Spam markierte Nachrichten vor dem Erreichen des Inhaltsfilters in den Junk-E-Mail-Ordner weiterzuleiten:</span><span class="sxs-lookup"><span data-stu-id="8263a-114">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    <span data-ttu-id="8263a-115">Dabei ist  _NameForRule_ der Name für die neue Regel, z. B. „JunkMailBeforeReachingContentFilter".</span><span class="sxs-lookup"><span data-stu-id="8263a-115">Where  _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span> 
    
4. <span data-ttu-id="8263a-116">Führen Sie den folgenden Befehl aus, um sicherzustellen, dass Nachrichten von Absendern in einer Sperrliste in der Spamfilterrichtlinie, z. B. in der Liste **blockierter Absender**, in den Junk-E-Mail-Ordner weitergeleitet werden:</span><span class="sxs-lookup"><span data-stu-id="8263a-116">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span> 
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    <span data-ttu-id="8263a-117">Dabei ist  _NameForRule_ der Name für die neue Regel, z. B. „JunkMailInSenderBlockList".</span><span class="sxs-lookup"><span data-stu-id="8263a-117">Where  _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span> 
    
<span data-ttu-id="8263a-p104">Wenn die Aktion **Nachricht in Junk-E-Mail-Ordner verschieben** nicht verwendet werden soll, können Sie eine andere Aktion in den Inhaltsfilterrichtlinien in der Exchange-Verwaltungskonsole auswählen. Weitere Informationen finden Sie unter [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md). Weitere Informationen zu diesen Feldern in der Nachrichtenkopfzeile finden Sie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="8263a-p104">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
  

> [!TIP]
> <span data-ttu-id="8263a-121">Wenn Sie die Aktion **Nachricht in Junk-e-Mail-Ordner bewegen** nicht verwenden möchten, können Sie eine andere Aktion in den Inhaltsfilter Richtlinien im Exchange Admin Center auswählen.</span><span class="sxs-lookup"><span data-stu-id="8263a-121">If you don't want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="8263a-122">Weitere Informationen finden Sie unter [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8263a-122">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="8263a-123">Weitere Informationen zu diesen Feldern in der Nachrichtenkopfzeile finden Sie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="8263a-123">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
> 
## <a name="see-also"></a><span data-ttu-id="8263a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8263a-124">See also</span></span>

[<span data-ttu-id="8263a-125">New-TransportRule-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8263a-125">New-TransportRule cmdlet</span></span>](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

