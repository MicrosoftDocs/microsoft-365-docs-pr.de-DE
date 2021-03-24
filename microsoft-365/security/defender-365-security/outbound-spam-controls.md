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
description: Administratoren können sich über die Steuerelemente für ausgehende Spamnachrichten in Exchange Online Protection (EOP) informieren und wissen, was sie tun müssen, wenn Sie Massensendungen senden müssen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e84cd636abee42a03ff8590091542c96714f2d8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065160"
---
# <a name="outbound-spam-protection-in-eop"></a>Ausgehender Spamschutz in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer nehmen wir die Verwaltung ausgehender Spamnachrichten ernst. Ein Kunde, der absichtlich oder unbeabsichtigt Spam von seiner Organisation sendet, kann die Reputation des gesamten Diensts beeinträchtigen und die E-Mail-Zustellung für andere Kunden beeinträchtigen.

In diesem Thema werden die Steuerelemente und Benachrichtigungen beschrieben, die dazu beitragen sollen, ausgehenden Spam zu verhindern, und was Sie tun können, wenn Sie Massensendungen senden müssen.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Was Administratoren tun können, um ausgehenden Spam zu steuern

- Integrierte Benachrichtigungen verwenden: Wenn ein [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) Benutzer die Sendebeschränkungen des Diensts oder ausgehender  Spamrichtlinien überschreitet und das Senden von E-Mails eingeschränkt ist, sendet die Standardmäßige Benachrichtigungsrichtlinie mit dem Namen Benutzer, der das Senden von **E-Mails** beschränkt hat, E-Mail-Benachrichtigungen an Mitglieder der **Gruppe TenantAdmins** (**Globale** Administratoren). [](configure-the-outbound-spam-policy.md) Informationen zum Konfigurieren, wer diese Benachrichtigungen erhält, finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) Außerdem wurden die  Standardbenachrichtigungsrichtlinien mit  dem Namen E-Mail-Sendegrenzwert überschritten und Verdächtige E-Mail-Sendemuster erkannt, die E-Mail-Benachrichtigungen an Mitglieder der **Gruppe TenantAdmins** (**Globale** Administratoren) senden. Weitere Informationen über Benachrichtigungsrichtlinien finden Sie unter [Benachrichtigungsrichtlinien im Security & Compliance Center](../../compliance/alert-policies.md).

- Spambeschwerden von E-Mail-Anbietern von Drittanbietern **überprüfen:** Viele E-Mail-Dienste wie Outlook.com, Yahoo und AOL bieten eine Feedbackschleife, in der benutzer in ihrem Dienst eine E-Mail von Microsoft 365 als Spam markieren, wird die Nachricht verpackt und zur Überprüfung an uns zurückgeschickt. Weitere Informationen zur Absenderunterstützung für Outlook.com finden Sie unter <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>So steuert EOP ausgehenden Spam

- **Trennung des ausgehenden** E-Mail-Datenverkehrs: Jede ausgehende Nachricht, die über den Dienst gesendet wird, wird auf Spam überprüft. Wenn die Nachricht als Spam erkannt wird, wird sie von einem sekundären, weniger seriösen IP-Adresspool namens _"High-Risk Delivery Pool" zugestellt._ Weitere Informationen finden Sie unter [Zustellungspool mit höherem Risiko für ausgehende Nachrichten](high-risk-delivery-pool-for-outbound-messages.md).

- **Überwachen der Quell-IP-Adressre reputation:** Microsoft 365 fragt verschiedene IP-Blocklisten von Drittanbietern ab. Eine Warnung wird generiert, wenn eine der für ausgehende E-Mails verwendeten IP-Adressen in diesen Listen angezeigt wird. Auf diese Weise können wir schnell reagieren, wenn spam unsere Reputation beeinträchtigt hat. Wenn eine Warnung generiert wird, verfügen wir über eine interne Dokumentation, in der beschrieben wird, wie unsere IP-Adressen aus Blocklisten entfernt (delistiert) werden.

- Deaktivieren von Konten, die zu viel Spam senden: Auch wenn ausgehende Spamnachrichten in den Pool mit hohem Risiko getrennt werden, können wir einem Konto (häufig ein gefährdetes Konto) nicht erlauben, Spam auf unbestimmte Zeit zu <sup>\*</sup> senden. Wir überwachen Konten, die Spam senden, und wenn sie einen nicht bezeichneten Grenzwert überschreiten, wird das Konto am Senden von E-Mails blockiert. Es gibt unterschiedliche Schwellenwerte für einzelne Benutzer und den gesamten Mandanten.

- Deaktivieren von Konten, die zu viel E-Mails zu schnell senden: Zusätzlich zu den Grenzwerten, die nach Nachrichten suchen, die als Spam gekennzeichnet sind, gibt es auch Beschränkungen, die Konten blockieren, wenn sie einen allgemeinen Grenzwert für ausgehende Nachrichten erreichen, unabhängig von der Spamfilterung für die ausgehenden <sup>\*</sup> Nachrichten. Ein gefährdetes Konto kann Zero-Day-Spam (bisher nicht erkannt) senden, der vom Spamfilter verpasst wird. Da es schwierig sein kann, eine legitime Massenmailkampagne im Vergleich zu einer Spamkampagne zu identifizieren, helfen diese Grenzwerte, potenzielle Schäden zu minimieren.

<sup>\*</sup> Wir werben nicht mit den genauen Grenzwerten, damit Spammer das System nicht spielen können, sodass wir die Grenzwerte bei Bedarf erhöhen oder verringern können. Die Grenzwerte sind hoch genug, um zu verhindern, dass ein durchschnittlicher Geschäftsbenutzer sie jemals überschreitet, und niedrig genug, um den durch einen Spammer verursachten Schaden eindämmen zu können.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Empfehlungen für Kunden, die Massensendungen über EOP senden möchten

Es ist schwierig, ein Gleichgewicht zwischen Kunden zu finden, die eine große Menge an E-Mails senden möchten, und dem Schutz des Diensts vor gefährdeten Konten und Massen-E-Mail-Absendern mit schlechten Empfängererwerbspraktiken. Die Kosten einer Microsoft 365-E-Mail-Quelle, die auf einer Ip-Blockliste eines Drittanbieters landet, sind größer als das Blockieren eines Benutzers, der zu viele E-Mails sendet.

Wie in der [Exchange Online-Dienstbeschreibung](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)beschrieben, ist die Verwendung von EOP zum Senden von Massen-E-Mails keine unterstützte Verwendung des Diensts und nur auf "best-effort"-Basis zulässig. Für Kunden, die Massen-E-Mails senden möchten, empfehlen wir die folgenden Lösungen:

- **Massen-E-Mails über lokale E-Mail-Server** senden: Dies bedeutet, dass Kunden ihre eigene E-Mail-Infrastruktur für Massensendungen verwalten müssen.

- **Verwenden Eines Drittanbieters für Massen-E-Mail:** Es gibt mehrere Anbieter von Massen-E-Mail-Lösungen von Drittanbietern, die Sie zum Senden von Massenmailings verwenden können. Diese Unternehmen haben ein interessesfreies Interesse an der Zusammenarbeit mit Kunden, um gute E-Mail-Sendepraktiken sicherzustellen.

Die Arbeitsgruppe "Messaging, Mobile, Malware Anti-Abuse" (MAAWG) veröffentlicht ihre Mitgliederliste unter <https://www.maawg.org/about/roster> . Mehrere Massen-E-Mail-Anbieter sind auf der Liste und sind als verantwortliche Internet-Bürger bekannt.