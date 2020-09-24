---
title: Funktionsweise des ATP-Features für sichere Links
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Das Feature "sichere Links" bietet eine Zeit-für-Mausklick-Überprüfung von Hyperlinks in Office-Dokumenten und e-Mail-Nachrichten. Lesen Sie diesen Artikel, um zu erfahren, wie ATP-sichere Links funktionieren.
ms.openlocfilehash: e19d3a1f93d11cd9873e6b5fad9952b018e0a481
ms.sourcegitcommit: 1522a6471e0c5254a6d0f592e1f4dfacd1dd473a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "48245881"
---
# <a name="how-atp-safe-links-works"></a>Funktionsweise des ATP-Features für sichere Links

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT] 
> Damit Office 365 ATP-sichere Links ordnungsgemäß funktioniert, müssen alle Dienste dieselbe Version aufweisen.
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>So funktioniert ATP-sichere Links mit URLs in e-Mails

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 mit URLs in e-Mail

Auf einer hohen Ebene funktioniert der Schutz für [ATP-sichere Links](atp-safe-links.md) für URLs in e-Mails (in Office 365 gehostet, nicht lokal):
  
1. Personen erhalten e-Mail-Nachrichten, von denen einige URLs enthalten.
    
2. Alle e-Mails werden Exchange Online Schutz durchlaufen, wobei IP-und Briefumschlag Filter, signaturbasierter Malware Schutz, Antispam-und Antischadsoftware-Filter angewendet werden. 
    
3. E-Mail kommt in Postfächern der Benutzer.
    
4. Ein Benutzer meldet sich bei Office 365 an und wechselt in den e-Mail-Posteingang.
    
5. Der Benutzer öffnet eine e-Mail-Nachricht und klickt auf eine URL in der e-Mail-Nachricht.
    
6. Das Feature "ATP-sichere Links" überprüft die URL unmittelbar vor dem Öffnen der Website. Die URL wird als blockiert, bösartig oder sicher identifiziert.
        
   - Wenn die URL zu einer Website gehört, die in der [Liste benutzerdefinierte blockierte URLs](set-up-a-custom-blocked-urls-list-atp.md)der Organisation enthalten ist, wird eine [Warn Seite](atp-safe-links-warning-pages.md) geöffnet. 
    
   - Wenn die URL zu einer Website gehört, die als bösartig eingestuft wurde, wird eine [Warn Seite](atp-safe-links-warning-pages.md) geöffnet. 
    
   - Wenn die URL zu einer herunterladbaren Datei wechselt und die [Richtlinien für ATP-sichere Links](set-up-atp-safe-links-policies.md) in Ihrer Organisation für die Überprüfung solcher Inhalte konfiguriert sind, wird die herunterladbare Datei überprüft. 
    
   - Wenn die URL als sicher eingestuft wird, wird die Website geöffnet.
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>So funktioniert ATP-sichere Links mit URLs in Office-Dokumenten

Auf hohem Niveau funktioniert der Schutz von [ATP-Links](atp-safe-links.md) für URLs in Microsoft 365-Apps für Enterprise-oder Business Premium-Anwendungen (aktuelle Versionen von Word, Excel und PowerPoint unter Windows, Mac oder in einem Browser, Office-Apps auf IOS-oder Android-Geräten, Visio unter Windows, OneNote in einem Browser):
  
1. Benutzer haben Microsoft 365-Apps für Enterprise oder Business Premium auf Ihrem Computer, Smartphone oder Tablet installiert. (Oder Sie verwenden Office in Ihrem Browser.)
    
2. Ein Benutzer öffnet ein Word-, Excel-, PowerPoint-, OneNote-(im Browser) oder Visio (auf dem Desktop) und meldet sich bei Office 365 Enterprise über sein Arbeits-oder Schulkonto an. Das Dokument enthält URLs.
    
3. Wenn der Benutzer auf eine URL im Dokument klickt, wird der Link vom ATP-Dienst für sichere Links überprüft.
    
   - Wenn die URL zu einer Website gehört, die in der [Liste benutzerdefinierte blockierte URLs](set-up-a-custom-blocked-urls-list-atp.md)der Organisation enthalten ist, wird der Benutzer zu einer [Warnungsseite](atp-safe-links-warning-pages.md)geleitet.
    
   - Wenn die URL zu einer Website gehört, die als bösartig eingestuft wurde, wird der Benutzer zu einer [Warnungsseite](atp-safe-links-warning-pages.md)geleitet.
    
   - Wenn die URL zu einer herunterladbaren Datei wechselt und die [Richtlinien für ATP-sichere Links](set-up-atp-safe-links-policies.md) für die Überprüfung solcher Downloads konfiguriert sind, wird die herunterladbare Datei überprüft. 
    
   - Wenn die URL als sicher eingestuft wird, wird der Benutzer zur Website geleitet.
      
   - Wenn die URL-Prüfung fehlschlägt, wird der Schutz für sichere Links nicht ausgelöst. Auf den Desktop Clients wird der Benutzer gewarnt, bevor er mit der Website fortfahren kann.
      
> [!NOTE]
> Es kann einige Sekunden zu Beginn jeder Sitzung dauern, um sicherzustellen, dass der Benutzer über ATP-sichere Links für Office Enabled verfügt. 
      
