---
title: Vermeiden von ungültigen Zeichen in ihren Spamfilterregeln und der Spamfilterrichtlinie
f1.keywords:
- NOCSH
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
ms.openlocfilehash: f1841eb86583a48acecde0770f030b626323fa8e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599112"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="e17ce-103">Vermeiden von ungültigen Zeichen in ihren spamfilterregeln und Spamfilter Richtlinien</span><span class="sxs-lookup"><span data-stu-id="e17ce-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="e17ce-104">Zuvor haben Office 365 Administratoren mithilfe der Exchange-Verwaltungskonsole spamfilterregeln und die Spamfilter Richtlinie eingerichtet und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e17ce-104">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange admin center (EAC).</span></span> <span data-ttu-id="e17ce-105">Jetzt verwenden Sie das Security &amp; Compliance Center, um Ihre Anti-Spam-Konfiguration zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e17ce-105">Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration.</span></span> <span data-ttu-id="e17ce-106">Die folgenden Zeichen wurden in der Exchange-Verwaltungskonsole unterstützt, werden jedoch nicht für &amp; die Verwendung im Security Compliance Center unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e17ce-106">The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="e17ce-107">**Ungültige Zeichen:**</span><span class="sxs-lookup"><span data-stu-id="e17ce-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="e17ce-108">Wenn Ihre spamfilterregeln oder Ihre Spamfilter Richtlinie ungültige Zeichen enthalten, treten möglicherweise einige oder alle dieser Probleme auf:</span><span class="sxs-lookup"><span data-stu-id="e17ce-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="e17ce-109">Möglicherweise können Sie die Richtlinie oder Regeln nicht im Security &amp; Compliance Center finden.</span><span class="sxs-lookup"><span data-stu-id="e17ce-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="e17ce-110">Möglicherweise werden Fehler angezeigt, wenn Sie versuchen, die Regeln oder Richtlinien mithilfe von Windows PowerShell abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e17ce-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="e17ce-111">Möglicherweise stellen Sie fest, dass die Richtlinie oder die Einstellungen nicht wie erwartet ausgeführt werden oder ausführen.</span><span class="sxs-lookup"><span data-stu-id="e17ce-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="e17ce-112">Entfernen der ungültigen Zeichen aus der Spamfilter Richtlinie und-Regeln</span><span class="sxs-lookup"><span data-stu-id="e17ce-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="e17ce-113">Nachdem Sie die Richtlinien und Regeln identifiziert haben, die ungültige Zeichen enthalten, können Sie die Namen mithilfe der Windows PowerShell-Cmdlets ändern.</span><span class="sxs-lookup"><span data-stu-id="e17ce-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="e17ce-114">Stellen [Sie mithilfe von Remote-PowerShell eine Verbindung zu Exchange Online her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e17ce-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="e17ce-115">Führen Sie das Cmdlet "hostedcontentfilterpolicy dient zum" wie folgt aus, um den Namen der Spamfilter Richtlinie zu ändern:</span><span class="sxs-lookup"><span data-stu-id="e17ce-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```powershell
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="e17ce-116">Um den Namen einer Spamfilter Regel zu ändern, führen Sie das Cmdlet "HostedContentFilterRule" wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e17ce-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```powershell
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="e17ce-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e17ce-117">For more information</span></span>

[<span data-ttu-id="e17ce-118">Threat Management im Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e17ce-118">Threat management in the Security &amp; Compliance Center</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="e17ce-119">Gruppe-hostedcontentfilterpolicy dient zum</span><span class="sxs-lookup"><span data-stu-id="e17ce-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)

[<span data-ttu-id="e17ce-120">Gruppe-HostedContentFilterRule</span><span class="sxs-lookup"><span data-stu-id="e17ce-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule)
