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
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>Worin besteht der Unterschied zwischen Junk- und Massen-E-Mail?

Kunden fragen mitunter, worin der Unterschied zwischen Junk-E-Mail und Massen-E-Mail bestehe. Zweck dieses Themas ist die Erläuterung des Unterschieds und Bereitstellung von Informationen zu den verschiedenen Optionen, die sowohl in Exchange Online als auch Exchange Online Protection (EOP) zur Verfügung stehen.
  
 **Was ist Junk-E-Mail?**
  
Junk-E-Mail-Nachrichten sind Spamnachrichten, d. h. unerwünschte E-Mail-Nachrichten, die vom Dienst herausgefiltert werden. Standardmäßig weist der Dienst Spamnachrichten basierend auf der Zuverlässigkeit der IP-Adresse des Absenders zurück. Doch wenn eine Nachricht die IP-Adressüberprüfung besteht, aber von den Inhaltsfiltern als Spam eingestuft wird, dann wird die Nachricht in den Junk-E-Mail-Ordner der vorgesehenen Empfänger gesendet. 
  
> [!NOTE]
> Die für Inhalts gefilterte Nachrichten ausgeführte Aktion kann über Inhaltsfilter Richtlinien in der Exchange-Verwaltungskonsole (EAC) konfiguriert werden, wie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md)beschrieben. Wenn Sie mit der Spam Klassifizierung nicht einverstanden sind, können Sie Nachrichten, die Sie als Spam oder nicht-Spam bezeichnen, auf verschiedene Weise an Microsoft melden, wie unter [Submit Spam, Non-Spam und Phishing Scam messages to Microsoft for Analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)beschrieben. 
  
 **Was ist Massen-E-Mail?**
  
Massen-E-Mail ist ein Typ von E-Mail-Nachrichten, der schwieriger zu klassifizieren ist. Während Junk-E-Mail eine ständige Bedrohung darstellt, enthalten Massen-E-Mails eine Werbe- oder Marketingbotschaft, die meist nicht wiederholt gesendet wird. Massen-E-Mail wird von einigen Benutzern gewünscht, die sich ggf. sogar absichtlich für den Empfang dieser Nachrichten angemeldet haben, während andere Benutzer diese Nachrichtentypen als Spam betrachten. Einige Benutzer möchten beispielsweise Werbe-E-Mails von der Contoso Corporation oder Einladungen zu einer bevorstehenden Konferenz zur Internetsicherheit erhalten, während für andere Benutzer diese Nachrichten Spam sind.
  
## <a name="how-to-manage-bulk-email"></a>Umgang mit Massen-E-Mails

Der Umgang mit Massen-E-Mails ist nicht ganz einfach, denn wenn alle Massen-E-Mails als Spam eingestuft werden, beschweren sich ggf. die Benutzer, die diese erhalten möchten, und melden sie als falsch positive (Nicht-Spam) Nachricht, die fälschlicherweise als Spam eingestuft wurde. Wenn sämtliche Massen-E-Mails dagegen zugelassen werden, beschweren sich ggf. die Benutzer, die diese nicht wollen, und melden sie als nicht abgefangene Spamnachricht, die fälschlicherweise in ihrem Posteingang gelandet ist.
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a>Aktivieren der erweiterten Option zur Filterung von Spam-Massensendungen

Je nach Richtlinie Ihres Unternehmens für Massen-e-Mail-Nachrichten können Administratoren einen Schwellenwert auswählen, um die Massen-e-Mail zuzuweisen. Die Einstellung kann über Inhaltsfilter Richtlinien in der Exchange-Verwaltungskonsole konfiguriert werden. Weitere Informationen finden Sie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md) for the steps. Sie können eine Schwellenwerteinstellung von 1-9 auswählen, wobei 1 die meisten Massen-e-Mails als Spam markiert, und 9 ermöglicht die Zustellung der meisten Massen-e-Mails. Der Dienst führt dann die konfigurierte Aktion aus, z. B. das Verschieben der Nachricht in den Junk-E-Mail-Ordner des Empfängers. 
  

