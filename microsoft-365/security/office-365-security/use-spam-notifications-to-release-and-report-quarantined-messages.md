---
title: Verwenden von Spambenachrichtigungen für Benutzer zum Freigeben und Melden von isolierten Nachrichten in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: Wenn Ihr Administrator die Benachrichtigungen für Benutzer aktiviert, erhalten Sie eine Benachrichtigungsmeldung, in der Nachrichten aufgelistet werden, die an Ihr Postfach gesendet wurden, die als Spam-, Massen-oder Phishing-Nachrichten identifiziert wurden. Nach der Benachrichtigung können Sie Nachrichten freigeben oder melden.
ms.openlocfilehash: 499af3ae2934eed19e421918af07a45b72fe2518
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082137"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a>Verwenden von Spambenachrichtigungen für Benutzer zum Freigeben und Melden von isolierten Nachrichten in Office 365

Wenn Ihr Administrator Spambenachrichtigungen für Benutzer aktiviert, erhalten Sie eine Benachrichtigungsmeldung, in der an Ihr Postfach adressierte Nachrichten aufgelistet werden, die stattdessen als Spam identifiziert und isoliert wurden.
  
> [!TIP]
> Wenn Sie Administrator sind und dieses Feature aktivieren möchten, können Sie die Option auswählen, wenn Sie [eine standardmäßige Anti-Spam-Richtlinie ändern](https://go.microsoft.com/fwlink/?LinkId=800313). 
  
Die empfangene Nachricht enthält die Anzahl der Spam isolierten Nachrichten, die Sie haben, und das Datum und die Uhrzeit (in Universal Coordinated Time oder UTC) der letzten Nachricht in der Liste. Die Liste enthält für jede Nachricht Folgendes:
  
- **Absender** Der Absender Name und die e-Mail-Adresse der isolierten Nachricht. 
    
- **Betreff** Der Betreffzeilentext der in Quarantäne verschobenen Nachricht. 
    
- **Datum** Datum und Uhrzeit (UTC-Angabe) der Verschiebung der Nachricht in Quarantäne. 
    
- **Größe** Die Größe der Nachricht in Kilobyte (KBS). 
    
Dies sind die Aktionen, die Sie mit einer isolierten Nachricht durchführen können:

- Zeigen Sie **eine Vorschau** der Nachricht an, wenn Sie eine Vorschau des Inhalts oder des Headers vor dem Ausführen der Aktion anzeigen möchten.

- **Laden** Sie die Nachricht herunter, wenn Sie die Nachricht und Anlagen (falls vorhanden) auf Ihrem Gerät überprüfen möchten, bevor Sie Maßnahmen ergreifen.

- **Release** wenn es sich bei der Nachricht nicht um Spam handelt und Sie möchten, dass Office 365 die Nachricht an Ihr Postfach sendet.

- **Freigabe #a0 Absender zulassen** , wenn die Nachricht kein Spam ist, und Sie möchten, dass Office 365 den Absender zu Ihrer Liste sicherer Absender und Empfänger für zukünftige e-Mails hinzufügen. Beachten Sie, dass Ihr Administrator möglicherweise andere organisationsweite Allow/Block-Konfigurationen hat, die Ihre Liste sicherer Absender außer Kraft setzen.

- Geben Sie **#a0 Bericht frei**, wenn es sich bei der Nachricht nicht um Spam handelt und Sie die Nachricht an Ihr Postfach senden und an Microsoft zur Analyse melden möchten.

- **Absender blockieren** , wenn Office 365 den Absender zu Ihrer Liste blockierter Absender hinzufügen möchten.

Beachten Sie Folgendes:
  
- Nachrichten, die in Quarantäne verschoben werden, da Sie einer Nachrichtenfluss Regel entsprechen, werden nicht in Nachrichten mit Benutzerquarantäne eingeschlossen. Es werden nur Spamquarantäne-Nachrichten aufgeführt.
    
- Sie können eine Nachricht nur einmal freigeben und als falsch positiv markiert (keine Junk-E-Mail) melden.
    

