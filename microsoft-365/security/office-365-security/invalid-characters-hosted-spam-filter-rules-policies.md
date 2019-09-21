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
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>Vermeiden von ungültigen Zeichen in ihren spamfilterregeln und Spamfilter Richtlinien 

Zuvor haben Office 365 Administratoren mithilfe der Exchange-Verwaltungskonsole spamfilterregeln und die Spamfilter Richtlinie eingerichtet und konfiguriert. Jetzt verwenden Sie das Security &amp; Compliance Center, um Ihre Anti-Spam-Konfiguration zu verwalten. Die folgenden Zeichen wurden in der Exchange-Verwaltungskonsole unterstützt, werden jedoch nicht für &amp; die Verwendung im Security Compliance Center unterstützt.  

**Ungültige Zeichen:**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

Wenn Ihre spamfilterregeln oder Ihre Spamfilter Richtlinie ungültige Zeichen enthalten, treten möglicherweise einige oder alle dieser Probleme auf:
- Möglicherweise können Sie die Richtlinie oder Regeln nicht im Security &amp; Compliance Center finden.
- Möglicherweise werden Fehler angezeigt, wenn Sie versuchen, die Regeln oder Richtlinien mithilfe von Windows PowerShell abzurufen.
- Möglicherweise stellen Sie fest, dass die Richtlinie oder die Einstellungen nicht wie erwartet ausgeführt werden oder ausführen.

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>Entfernen der ungültigen Zeichen aus der Spamfilter Richtlinie und-Regeln

Nachdem Sie die Richtlinien und Regeln identifiziert haben, die ungültige Zeichen enthalten, können Sie die Namen mithilfe der Windows PowerShell-Cmdlets ändern. 

1. Stellen [Sie mithilfe von Remote-PowerShell eine Verbindung zu Exchange Online her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
    
2. Führen Sie das Cmdlet "hostedcontentfilterpolicy dient zum" wie folgt aus, um den Namen der Spamfilter Richtlinie zu ändern:
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. Um den Namen einer Spamfilter Regel zu ändern, führen Sie das Cmdlet "HostedContentFilterRule" wie folgt aus:
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>Weitere Informationen

[Threat Management im Security &amp; Compliance Center](protect-against-threats.md)
  
[Gruppe-hostedcontentfilterpolicy dient zum](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[Gruppe-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)
