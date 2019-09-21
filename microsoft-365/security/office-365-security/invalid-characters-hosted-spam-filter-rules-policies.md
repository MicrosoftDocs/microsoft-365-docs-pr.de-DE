---
title: Vermeiden ungültiger Zeichen in ihren spamfilterregeln und der Spamfilter Richtlinie
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/24/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Enthält Hilfestellung für Administratoren, die ungültige Zeichen in ihrer Antispamsoftware haben und bei der Verwendung des Security &amp; Compliance Centers in Problemen ausgeführt werden.
ms.openlocfilehash: 286a96814e0be5857499d7c54839d20142d0dd60
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081220"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="1a2b7-103">Vermeiden von ungültigen Zeichen in ihren spamfilterregeln und Spamfilter Richtlinien</span><span class="sxs-lookup"><span data-stu-id="1a2b7-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="1a2b7-104">Zuvor haben Office 365 Administratoren mithilfe der Exchange-Verwaltungskonsole spamfilterregeln und die Spamfilter Richtlinie eingerichtet und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="1a2b7-104">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange admin center (EAC).</span></span> <span data-ttu-id="1a2b7-105">Jetzt verwenden Sie das Security &amp; Compliance Center, um Ihre Anti-Spam-Konfiguration zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="1a2b7-105">Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration.</span></span> <span data-ttu-id="1a2b7-106">Die folgenden Zeichen wurden in der Exchange-Verwaltungskonsole unterstützt, werden jedoch nicht für &amp; die Verwendung im Security Compliance Center unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1a2b7-106">The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="1a2b7-107">**Ungültige Zeichen:**</span><span class="sxs-lookup"><span data-stu-id="1a2b7-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="1a2b7-108">Wenn Ihre spamfilterregeln oder Ihre Spamfilter Richtlinie ungültige Zeichen enthalten, treten möglicherweise einige oder alle dieser Probleme auf:</span><span class="sxs-lookup"><span data-stu-id="1a2b7-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="1a2b7-109">Möglicherweise können Sie die Richtlinie oder Regeln nicht im Security &amp; Compliance Center finden.</span><span class="sxs-lookup"><span data-stu-id="1a2b7-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="1a2b7-110">Möglicherweise werden Fehler angezeigt, wenn Sie versuchen, die Regeln oder Richtlinien mithilfe von Windows PowerShell abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1a2b7-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="1a2b7-111">Möglicherweise stellen Sie fest, dass die Richtlinie oder die Einstellungen nicht wie erwartet ausgeführt werden oder ausführen.</span><span class="sxs-lookup"><span data-stu-id="1a2b7-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="1a2b7-112">Entfernen der ungültigen Zeichen aus der Spamfilter Richtlinie und-Regeln</span><span class="sxs-lookup"><span data-stu-id="1a2b7-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="1a2b7-113">Nachdem Sie die Richtlinien und Regeln identifiziert haben, die ungültige Zeichen enthalten, können Sie die Namen mithilfe der Windows PowerShell-Cmdlets ändern.</span><span class="sxs-lookup"><span data-stu-id="1a2b7-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="1a2b7-114">Stellen [Sie mithilfe von Remote-PowerShell eine Verbindung zu Exchange Online her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="1a2b7-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="1a2b7-115">Führen Sie das Cmdlet "hostedcontentfilterpolicy dient zum" wie folgt aus, um den Namen der Spamfilter Richtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="1a2b7-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="1a2b7-116">Um den Namen einer Spamfilter Regel zu ändern, führen Sie das Cmdlet "HostedContentFilterRule" wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="1a2b7-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="1a2b7-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a2b7-117">For more information</span></span>

[<span data-ttu-id="1a2b7-118">Threat Management im Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1a2b7-118">Threat management in the Security &amp; Compliance Center</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="1a2b7-119">Gruppe-hostedcontentfilterpolicy dient zum</span><span class="sxs-lookup"><span data-stu-id="1a2b7-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[<span data-ttu-id="1a2b7-120">Gruppe-HostedContentFilterRule</span><span class="sxs-lookup"><span data-stu-id="1a2b7-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)
