---
title: Verwenden des Listenentfernungsportals, um sich selbst aus der Liste der blockierten Absender von Office 365 zu entfernen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
description: Erhalten Sie eine Fehlermeldung, wenn Sie versuchen, eine E-Mail an einen Empfänger zu senden, dessen E-Mail-Adresse sich in Office 365 befindet? Wenn Sie glauben, dass Sie die Fehlermeldung nicht erhalten sollten, können Sie das Listenentfernungsportal verwenden, um sich selbst aus der Liste der blockierten Absender von Office 365 zu entfernen.
ms.openlocfilehash: cd85a06bfd4122dcacd798a48f5a1755e2969b4a
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895083"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a>Verwenden des Listenentfernungsportals, um sich selbst aus der Liste der blockierten Absender von Office 365 zu entfernen

Erhalten Sie eine Fehlermeldung, wenn Sie versuchen, eine E-Mail an einen Empfänger zu senden, dessen E-Mail-Adresse sich in Office 365 befindet? Wenn Sie glauben, dass Sie die Fehlermeldung nicht erhalten sollten, können Sie das Listenentfernungsportal verwenden, um sich selbst aus der Liste der blockierten Absender von Office 365 zu entfernen.

## <a name="what-is-the-office-365-blocked-senders-list"></a>Was ist die Liste der blockierten Absender von Office 365?

Microsoft verwendet die Liste der blockierten Absender, um seine Kunden vor Spam, Spoofing und Phishingangriffen zu schützen. Die IP-Adresse Ihres E-Mail-Servers, d. h. die Adresse, mit der sich Ihr E-Mail-Server im Internet identifiziert, wurde aus einem von vielen möglichen Gründen als mögliche Bedrohung für Office 365 kategorisiert. Wenn Office 365 die IP-Adresse zu der Liste hinzufügt, wird jede weitere Kommunikation zwischen der IP-Adresse und unseren Kunden über unsere Rechenzentren verhindert.

Sie merken, dass Sie der Liste hinzugefügt wurden, wenn Sie auf eine E-Mail eine Antwort erhalten, die in etwa folgende Fehlermeldung enthält:

> 550 5.7.606-649 Zugriff verweigert, verbannte Absender IP [_IP-Adresse_]; Wenn Sie die Entfernung aus dieser Liste anfordern https://sender.office.com/ möchten, besuchen Sie die Anweisungen, und befolgen Sie diese. Weitere Informationen finden Sie unter [e-Mail-Unzustellbarkeitsberichte in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

wobei  _IP address_ die IP-Adresse des Computers ist, auf dem der E-Mail-Server ausgeführt wird.

### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>So verwenden Sie das Listenentfernungsportal von Office 365, um sich selbst aus der Liste der blockierten Absender zu entfernen

1. Wechseln Sie in einem Webbrowser zu [https://sender.office.com](https://sender.office.com).

2. Folgen Sie den Anweisungen auf dem Bildschirm. Verwenden Sie die E-Mail-Adresse, an die die Fehlermeldung gesendet wurde, und die IP-Adresse, die in der Fehlermeldung angegeben ist. Sie können nur eine E-Mail-Adresse und eine IP-Adresse pro Besuch eingeben.

3. Klicken Sie auf **Senden**.

    Das Portal sendet eine E-Mail an die E-Mail-Adresse, die Sie angeben. Die e-Mail sieht in etwa wie folgt aus: ![Screenshot der empfangenen e-Mail, wenn Sie eine Anforderung über das Delist-Portal senden](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Klicken Sie auf den Bestätigungslink in der E-Mail, die vom Listenentfernungsportal an Sie gesendet wurde.

    Damit kehren Sie zum Azure-Listenentfernungsportal zurück.

5. Klicken Sie im Listenentfernungsportal auf **IP aus Liste entfernen**.

    Nachdem Sie die IP-Adresse aus der Liste der blockierten Absender entfernt haben, werden E-Mails von dieser IP-Adresse Empfängern mit Office 365 wieder zugestellt. Stellen Sie daher sicher, dass die E-Mails von dieser IP-Adresse keine beleidigenden oder böswilligen Inhalte aufweisen, da die IP-Adresse anderenfalls erneut blockiert werden kann.

    > [!NOTE]
    > Es kann bis zu 24 Stunden dauern, oder die Ergebnisse können stark variieren, bevor Einschränkungen entfernt werden.

Weitere Informationen finden Sie unter [Create Safe Sender Lists in Office 365](create-safe-sender-lists-in-office-365.md) and [Outbound Spam Protection in Office 365](outbound-spam-controls.md) , um zu verhindern, dass IP auf die schwarze Liste gesetzt wird.
