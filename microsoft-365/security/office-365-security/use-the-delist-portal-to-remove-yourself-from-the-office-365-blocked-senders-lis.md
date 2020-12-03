---
title: Sich selbst aus der Liste der blockierten Absender entfernen
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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie sich mithilfe des Listenentfernungsportals selbst aus der Microsoft 365-Liste der blockierten Absender entfernen können.
ms.openlocfilehash: f4e7bcc13ac6c133880eb0ebe69ba3f724d0a84e
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561423"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Verwenden des Listenentfernungsportals, um sich selbst aus der Liste der blockierten Absender zu entfernen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Erhalten Sie eine Fehlermeldung, wenn Sie versuchen, eine E-Mail an einen Empfänger zu senden, dessen E-Mail-Adresse sich in Microsoft 365 befindet? Wenn Sie glauben, dass Sie die Fehlermeldung nicht erhalten sollten, können Sie das Listenentfernungsportal verwenden, um sich selbst aus der Liste der blockierten Absender zu entfernen.

## <a name="what-is-the-blocked-senders-list"></a>Um was handelt es sich bei der Liste der blockierten Absender?

Microsoft verwendet die Liste der blockierten Absender, um seine Kunden vor Spam, Spoofing und Phishingangriffen zu schützen. Ihre IP-Adresse, d. h. die Adresse, mit der sich Ihr Computer im Internet identifiziert, wurde aus einem von vielen möglichen Gründen als mögliche Bedrohung für Microsoft 365 kategorisiert. Wenn Microsoft 365 die IP-Adresse zu der Liste hinzufügt, wird jede weitere Kommunikation zwischen der IP-Adresse und unseren Kunden über unsere Rechenzentren verhindert.

Sie merken, dass Sie der Liste hinzugefügt wurden, wenn Sie auf eine E-Mail eine Antwort erhalten, die in etwa folgende Fehlermeldung enthält:

> 550 5.7.606-649 Zugriff verweigert, gesperrte IP-Absenderadresse [_IP address_]. Um die Entfernung aus der Liste anzufordern, besuchen Sie <https://sender.office.com/>, und folgen Sie den Anweisungen. Weitere Informationen hierzu finden Sie unter [E-Mail-Unzustellbarkeitsberichte in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

wobei _IP address_ die IP-Adresse des Computers ist, auf dem der E-Mail-Server ausgeführt wird.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Verwenden des Listenentfernungsportals, um sich selbst aus der Liste der blockierten Absender zu entfernen

1. Wechseln Sie in einem Webbrowser zu <https://sender.office.com>.

2. Folgen Sie den Anweisungen auf dem Bildschirm. Verwenden Sie die E-Mail-Adresse, an die die Fehlermeldung gesendet wurde, und die IP-Adresse, die in der Fehlermeldung angegeben ist. Sie können nur eine E-Mail-Adresse und eine IP-Adresse pro Besuch eingeben.

3. Klicken Sie auf **Absenden**.

    Das Portal sendet eine E-Mail an die E-Mail-Adresse, die Sie angeben. Die E-Mail wird in etwa wie folgt aussehen: ![Screenshot einer E-Mail, die Sie beim Senden einer Anforderung über das Listenentfernungsportal erhalten](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png).

4. Klicken Sie auf den Bestätigungslink in der E-Mail, die vom Listenentfernungsportal an Sie gesendet wurde.

    Damit kehren Sie zum Azure-Listenentfernungsportal zurück.

5. Klicken Sie im Listenentfernungsportal auf **IP aus Liste entfernen**.

    Nachdem Sie die IP-Adresse aus der Liste der blockierten Absender entfernt haben, werden E-Mails von dieser IP-Adresse Empfängern, die Microsoft 365 verwenden, wieder zugestellt. Stellen Sie daher sicher, dass die E-Mails von dieser IP-Adresse keine beleidigenden oder böswilligen Inhalte aufweisen, da die IP-Adresse anderenfalls erneut blockiert werden kann.

    > [!NOTE]
    > Es kann bis zu 24 Stunden dauern oder die Ergebnisse können sehr unterschiedlich ausfallen, bevor die Beschränkungen aufgehoben werden.

Weitere Informationen finden Sie unter [Create Safe Sender Lists in EoP](create-safe-sender-lists-in-office-365.md) und [Outbound Spam Protection in EoP](outbound-spam-controls.md) , um zu verhindern, dass IP blockiert wird.
