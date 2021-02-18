---
title: Ausgehender Spamschutz
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die Steuerelemente für ausgehende Spamnachrichten in Exchange Online Protection (EOP) informieren und erfahren, was sie tun müssen, wenn Sie Massen-E-Mails senden müssen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f9d434c858f7c66f82dd4f551bac99458b9e5c8c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287629"
---
# <a name="outbound-spam-protection-in-eop"></a>Schutz vor ausgehenden Spamnachrichten in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer nehmen wir die Verwaltung ausgehender Spamnachrichten ernst. Ein Kunde, der absichtlich oder unbeabsichtigt Spam von seiner Organisation sendet, kann den Ruf des gesamten Diensts beeinträchtigen und die E-Mail-Zustellung für andere Kunden beeinträchtigen.

In diesem Thema werden die Steuerelemente und Benachrichtigungen beschrieben, mit deren Hilfe ausgehende Spamnachrichten verhindert werden sollen, und was Sie tun können, wenn Sie Massensendungen senden müssen.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Was Administratoren tun können, um ausgehenden Spam zu steuern

- Verwenden Sie integrierte Benachrichtigungen: Wenn [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) ein Benutzer die Sendegrenzwerte des Diensts oder der  Richtlinien für ausgehende Spamnachrichten überschreitet und das Senden von E-Mails eingeschränkt ist, sendet die standardmäßige Benachrichtigungsrichtlinie mit dem Namen "Benutzer, der am Senden von E-Mails eingeschränkt ist" **E-Mail-Benachrichtigungen** an Mitglieder der Gruppe **"TenantAdmins** ( [](configure-the-outbound-spam-policy.md) **Globale** Administratoren) ". Informationen zum Konfigurieren, wer diese Benachrichtigungen erhält, finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) Außerdem wurden die Standardmäßigen Benachrichtigungsrichtlinien  namens "Grenzwert für das Senden von E-Mails" überschritten, und es wurden verdächtige Muster für das Senden von E-Mails erkannt, um E-Mail-Benachrichtigungen an Mitglieder der Gruppe **"TenantAdmins** (**Globale** Administratoren) zu senden".  Weitere Informationen über Benachrichtigungsrichtlinien finden Sie unter [Benachrichtigungsrichtlinien im Security & Compliance Center](../../compliance/alert-policies.md).

- Überprüfen Sie Spambeschwerden von E-Mail-Anbietern von **Drittanbietern:** Viele E-Mail-Dienste wie Outlook.com, Yahoo und AOL stellen eine Feedbackschleife zur Verfügung, bei der benutzer in ihrem Dienst eine E-Mail von Microsoft 365 als Spam markieren, die Nachricht verpackt und zur Überprüfung an uns zurückgeschickt wird. Weitere Informationen zur Absenderunterstützung für Outlook.com finden Sie unter <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>So steuert EOP ausgehenden Spam

- **Trennung des ausgehenden E-Mail-Datenverkehrs:** Jede ausgehende Nachricht, die über den Dienst gesendet wird, wird auf Spam überprüft. Wenn die Nachricht als Spam ermittelt wird, wird sie von einem sekundären, weniger seriösen IP-Adresspool namens _"High-Risk Delivery Pool" zugestellt._ Weitere Informationen finden Sie unter [Zustellungspool mit höherem Risiko für ausgehende Nachrichten](high-risk-delivery-pool-for-outbound-messages.md).

- **Überwachen der Quell-IP-Adress-Reputation:** Microsoft 365 fragt verschiedene Listen blockierter IP-Adressen von Drittanbietern ab. Eine Warnung wird generiert, wenn eine der IP-Adressen, die wir für ausgehende E-Mails verwenden, in diesen Listen angezeigt wird. Dies ermöglicht es uns, schnell zu reagieren, wenn spam die Reputation beeinträchtigt hat. Wenn eine Warnung generiert wird, verfügen wir über eine interne Dokumentation, in der beschrieben wird, wie unsere IP-Adressen aus Sperrlisten entfernt (aufgelistet) werden.

- Deaktivieren Sie Konten, die zu viel Spam senden: Auch wenn ausgehende Spamnachrichten in den Pool für besonders riskante Zustellnachrichten getrennt werden, können wir einem Konto (häufig ein gefährdetes Konto) das unbegrenzte Senden von Spam nicht <sup>\*</sup> gestatten. Wir überwachen Konten, die Spam senden, und wenn sie einen nicht entsperrten Grenzwert überschreiten, wird das Senden von E-Mails für das Konto blockiert. Es gibt unterschiedliche Schwellenwerte für einzelne Benutzer und den gesamten Mandanten.

- Deaktivieren von Konten, die zu viele E-Mails zu schnell senden: Zusätzlich zu den Grenzwerten, die nach Nachrichten suchen, die als Spam gekennzeichnet sind, gibt es auch Beschränkungen, die Konten blockieren, wenn sie einen Grenzwert für ausgehende Nachrichten erreichen, unabhängig von der Spamfilterungsauswertung für ausgehende <sup>\*</sup> Nachrichten. Ein gefährdetes Konto könnte Zero-Day-Spam (zuvor nicht erkannt) senden, der vom Spamfilter verpasst wird. Da es schwierig sein kann, eine legitime Massensendungskampagne im Vergleich zu einer Spamkampagne zu identifizieren, helfen diese Grenzwerte, potenzielle Schäden zu minimieren.

<sup>\*</sup> Die genauen Grenzwerte werden nicht angekündigt, damit Spammer das System nicht spielen können, sodass wir die Grenzwerte bei Bedarf erhöhen oder verringern können. Die Grenzwerte sind hoch genug, um zu verhindern, dass ein durchschnittlicher Geschäftsbenutzer sie jemals überschreitet, und niedrig genug, um den von einem Spammer verursachten Schaden eindämmen zu können.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Empfehlungen für Kunden, die Massensendungen über EOP senden möchten

Es ist schwierig, ein Gleichgewicht zwischen Kunden, die eine große Menge an E-Mails senden möchten, im Vergleich zum Schutz des Diensts vor gefährdeten Konten und Massen-E-Mail-Absendern mit schlechten Methoden zum Erwerb von Empfängern zu finden. Die Kosten einer Microsoft 365-E-Mail-Quelle, die auf einer Liste blockierter Drittanbieter-IP-Adressen landet, sind höher als das Blockieren eines Benutzers, der zu viele E-Mails sendet.

Wie in der [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)Service Description beschrieben, wird die Verwendung von EOP zum Senden von Massen-E-Mails nicht unterstützt und ist nur nach bestem Aufwand zulässig. Für Kunden, die Massen-E-Mails senden möchten, empfehlen wir die folgenden Lösungen:

- **Massen-E-Mails über lokale E-Mail-Server** senden: Das bedeutet, dass Kunden ihre eigene E-Mail-Infrastruktur für Massensendungen verwalten müssen.

- **Verwenden Sie einen Drittanbieter für Massen-E-Mail:** Es gibt mehrere Drittanbieter für Massen-E-Mail-Lösungen, die Sie zum Senden von Massen-E-Mails verwenden können. Diese Unternehmen haben ein interessesfreies Interesse an der Zusammenarbeit mit Kunden, um gute E-Mail-Sendepraktiken sicherzustellen.

Die Messaging-, Mobile- und Malware Anti-Abuse Working Group (MAAWG) veröffentlicht ihre Mitgliederliste unter <https://www.maawg.org/about/roster> . Auf der Liste sind mehrere Massen-E-Mail-Anbieter aufgeführt, die als verantwortliche Internetnutzer bekannt sind.
