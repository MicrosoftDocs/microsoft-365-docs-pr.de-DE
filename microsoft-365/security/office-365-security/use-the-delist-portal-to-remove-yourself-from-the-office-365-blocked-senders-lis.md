---
title: Entfernen Sie sich selbst aus der Liste der blockierten Absender.
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
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie das Delist-Portal verwenden, um sich selbst aus der Liste der blockierten Absender von Microsoft 365 zu entfernen.
ms.openlocfilehash: 700382a494865b80116cfd8419213ed43b35b8a1
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034986"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Verwenden des Listenentfernungsportals, um sich selbst aus der Liste der blockierten Absender zu entfernen

Erhalten Sie eine Fehlermeldung, wenn Sie versuchen, eine e-Mail an einen Empfänger zu senden, dessen e-Mail-Adresse sich in Microsoft 365 befindet? Wenn Sie der Meinung sind, dass Sie die Fehlermeldung nicht erhalten sollten, können Sie das Delist-Portal verwenden, um sich selbst aus der Liste blockierter Absender zu entfernen.

## <a name="what-is-the-blocked-senders-list"></a>Was ist die Liste blockierter Absender?

Microsoft verwendet die Liste blockierter Absender zum Schutz seiner Kunden vor Spam, Spoofing und Phishing-Angriffen. Die IP-Adresse Ihres e-Mail-Servers, also die Adresse, die Ihr e-Mail-Server verwendet, um sich selbst im Internet zu identifizieren, wurde aus einer Vielzahl von Gründen als potenzielle Bedrohung für Microsoft 365 gekennzeichnet. Wenn Microsoft 365 die IP-Adresse zur Liste hinzufügt, wird die gesamte weitere Kommunikation zwischen der IP-Adresse und einem unserer Kunden durch unsere Rechenzentren verhindert.

Sie merken, dass Sie der Liste hinzugefügt wurden, wenn Sie auf eine E-Mail eine Antwort erhalten, die in etwa folgende Fehlermeldung enthält:

> 550 5.7.606-649 Zugriff verweigert, gesperrte IP-Absenderadresse [_IP address_]. Um die Entfernung aus der Liste anzufordern, besuchen Sie https://sender.office.com/, und folgen Sie den Anweisungen. Weitere Informationen hierzu finden Sie unter [E-Mail-Unzustellbarkeitsberichte in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

wobei _IP address_ die IP-Adresse des Computers ist, auf dem der E-Mail-Server ausgeführt wird.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>So verwenden Sie das Delist-Portal, um sich selbst aus der Liste blockierter Absender zu entfernen

1. Wechseln Sie in einem Webbrowser zu [https://sender.office.com](https://sender.office.com).

2. Folgen Sie den Anweisungen auf dem Bildschirm. Verwenden Sie die E-Mail-Adresse, an die die Fehlermeldung gesendet wurde, und die IP-Adresse, die in der Fehlermeldung angegeben ist. Sie können nur eine E-Mail-Adresse und eine IP-Adresse pro Besuch eingeben.

3. Klicken Sie auf **Absenden**.

    Das Portal sendet eine E-Mail an die E-Mail-Adresse, die Sie angeben. Die E-Mail wird in etwa wie folgt aussehen: ![Screenshot einer E-Mail, die Sie beim Senden einer Anforderung über das Listenentfernungsportal erhalten](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png).

4. Klicken Sie auf den Bestätigungslink in der E-Mail, die vom Listenentfernungsportal an Sie gesendet wurde.

    Damit kehren Sie zum Azure-Listenentfernungsportal zurück.

5. Klicken Sie im Listenentfernungsportal auf **IP aus Liste entfernen**.

    Nachdem die IP-Adresse aus der Liste blockierter Absender entfernt wurde, werden e-Mail-Nachrichten von dieser IP-Adresse an Empfänger übermittelt, die Microsoft 365 verwenden. Stellen Sie daher sicher, dass die E-Mails von dieser IP-Adresse keine beleidigenden oder böswilligen Inhalte aufweisen, da die IP-Adresse anderenfalls erneut blockiert werden kann.

    > [!NOTE]
    > Es kann bis zu 24 Stunden dauern oder die Ergebnisse können sehr unterschiedlich ausfallen, bevor die Beschränkungen aufgehoben werden.

Informationen dazu, wie Sie verhindern, dass die IP gesperrt wird, finden Sie unter [Erstellen von Listen sicherer Absender in Office 365](create-safe-sender-lists-in-office-365.md) und [Schutz vor ausgehenden Spam in Office 365](outbound-spam-controls.md).
