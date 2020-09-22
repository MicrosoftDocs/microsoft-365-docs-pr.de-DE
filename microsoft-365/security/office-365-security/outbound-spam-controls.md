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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können Informationen zu den ausgehenden Spam Steuerelementen in Exchange Online Protection (EoP) und was tun, wenn Sie Massensendungen senden müssen.
ms.openlocfilehash: 1097b768b955f2fa99c552ceda7564bef33a1aa7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202387"
---
# <a name="outbound-spam-protection-in-eop"></a>Ausgehenden Spam Schutz in EoP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer nehmen wir die Verwaltung von ausgehenden Spam-Mails ernst. Ein Kunde, der absichtlich oder unabsichtlich Spam aus seiner Organisation sendet, kann die Reputation des gesamten Diensts beeinträchtigen und die e-Mail-Zustellung für andere Kunden beeinträchtigen.

In diesem Thema werden die Steuerelemente und Benachrichtigungen beschrieben, die dazu dienen, ausgehenden Spam zu verhindern, und was Sie tun können, wenn Sie Massensendungen senden müssen.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Was Administratoren zum Steuern von ausgehenden Spam Aktionen tun können

- **Integrierte Benachrichtigungen verwenden**: Wenn ein Benutzer die Sende Grenzen des Diensts oder [der](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) [ausgehenden Spam Richtlinien](configure-the-outbound-spam-policy.md) überschreitet und das Senden von e-Mails beschränkt ist, sendet die standardmäßige Warnungs Richtlinie mit dem Namen " **Benutzer eingeschränkt vom Senden von e-Mail** " e-Mail-Benachrichtigungen an Mitglieder der Gruppe " **TenantAdmins** " (**globale Administratoren**). Weitere Informationen zum Konfigurieren der Empfänger dieser Benachrichtigungen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Außerdem werden die standardmäßigen Warnungsrichtlinien mit dem Namen " **e-Mail-Sende Grenzwert** " und " **verdächtige e-Mail-Sende Muster wurden erkannt** an Mitglieder der Gruppe **TenantAdmins** (**globale Administratoren**) gesendet. Weitere Informationen über Benachrichtigungsrichtlinien finden Sie unter [Benachrichtigungsrichtlinien im Security & Compliance Center](../../compliance/alert-policies.md).

- **Überprüfen von Spam Beschwerden von Drittanbieter-e-Mail-Anbietern**: viele e-Mail-Dienste wie Outlook.com, Yahoo und AOL bieten eine Feedbackschleife, bei der ein Benutzer in seinem Dienst eine e-Mail von Microsoft 365 als Spam markiert, die Nachricht verpackt und zur Überprüfung zurückgesendet wird. Weitere Informationen zur Absender Unterstützung für Outlook.com finden Sie unter <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>Wie EoP ausgehende Spam Steuerelemente steuert

- **Trennung des ausgehenden e-Mail-Datenverkehrs**: jede ausgehende Nachricht, die über den Dienst gesendet wird, wird auf Spam überprüft. Wenn die Nachricht als Spam eingestuft wird, wird Sie von einem sekundären, nicht seriösen IP-Adresspool mit dem Namen " _hoher Risiko-Zustellungs Pool_" übermittelt. Weitere Informationen finden Sie unter [Zustellungspool mit höherem Risiko für ausgehende Nachrichten](high-risk-delivery-pool-for-outbound-messages.md).

- Über **Wachen der Reputation der Quell-IP-Adresse**: Microsoft 365 fragt verschiedene IP-Sperrlisten von Drittanbietern ab. Eine Warnung wird generiert, wenn eine der IP-Adressen, die für ausgehende e-Mails verwendet werden, in diesen Listen angezeigt wird. Auf diese Weise können wir schnell reagieren, wenn Spam unsere Reputation verschlechtert hat. Wenn eine Warnung generiert wird, haben wir eine interne Dokumentation, in der erläutert wird, wie Sie die IP-Adressen aus Sperrlisten entfernen (deaufgelistet).

- **Deaktivieren von Konten, die zu viel Spam senden** <sup>\*</sup> : Obwohl wir ausgehende Spam-Mails in den Pool mit hoher Risikoverteilung einteilen, können wir nicht zulassen, dass ein Konto (oftmals ein kompromittiertes Konto) unbegrenzt Spam sendet. Wir überwachen Konten, die Spam senden, und wenn Sie einen nicht gebuchten Grenzwert überschreiten, wird das Senden von e-Mails durch das Konto blockiert. Für einzelne Benutzer und den gesamten Mandanten gibt es unterschiedliche Schwellenwerte.

- **Deaktivieren von Konten, die zu viele e-Mails zu schnell senden** <sup>\*</sup> : Zusätzlich zu den Grenzwerten, die nach Nachrichten suchen, die als Spam gekennzeichnet sind, gibt es auch Grenzwerte, mit denen Konten blockiert werden, wenn Sie eine allgemeine Grenze für ausgehende Nachrichten erreichen, unabhängig vom Spamfilter Urteil für ausgehende Nachrichten. Ein kompromittiertes Konto kann den vom Spamfilter verpassten Zero-Day (zuvor nicht erkannte) Spam senden. Da es schwierig sein kann, eine legitime Massen-e-Mail-Kampagne vs. eine Spam Kampagne zu identifizieren, helfen diese Grenzwerte, mögliche Schäden zu minimieren.

<sup>\*</sup> Wir werben nicht für die genauen Grenzwerte, sodass Spammer das System nicht spielen können, und daher können wir die Grenzwerte je nach Bedarf erweitern oder verringern. Die Grenzwertesind hoch genug, um zu verhindern, dass ein durchschnittlicher Geschäftsbenutzer Sie jemals überschreitet, und Sie sind niedrig genug, um den durch einen Spammer verursachten Schaden zu reduzieren.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Empfehlungen für Kunden, die Massensendungen über EoP senden möchten

Es ist schwierig, ein Gleichgewichtzwischen Kunden zu finden, die eine große Anzahl von e-Mails senden möchten, und den Dienst vor kompromittierten Konten und Massen-e-Mail-Absendern mit schlechten Empfänger-Akquisitions Praktiken schützen. Die Kosten einer Microsoft 365-e-Mail-Quelle, die auf einer IP-Sperrliste eines Drittanbieters landet, sind größer als das Blockieren eines Benutzers, der zu viele e-Mails sendet.

Wie in der [Exchange Online-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)beschrieben, ist die Verwendung von EoP zum Senden von Massen-e-Mails keine unterstützte Nutzung des Diensts und nur auf der Grundlage einer "Best-Effort"-Basis zulässig. Für Kunden, die Massen-e-Mails senden möchten, empfehlen wir die folgenden Lösungen:

- **Senden von Massen-e-Mails über lokale e-Mail-Server**: Dies bedeutet, dass Kunden ihre eigene e-Mail-Infrastruktur für Massensendungen aufrecht erhalten müssen.

- **Verwenden Sie einen Massen-e-Mail-Anbieter eines Dritt**Anbieters: Es gibt mehrere Drittanbieter-Massen-e-Mail-Lösungsanbieter, die Sie zum Senden von Massennachrichten verwenden können. Diese Unternehmen haben ein begründetes Interesse an der Zusammenarbeit mit Kunden, um gute e-Mail-Sende Praktiken sicherzustellen.

Die Anti-Abuse Working Group (Messaging, Mobile, MAAWG) veröffentlicht ihre Mitgliederliste unter <https://www.maawg.org/about/roster> . Mehrere Massen-e-Mail-Anbieter befinden sich in der Liste und sind bekanntermaßen verantwortliche Internet Bürger.
