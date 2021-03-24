---
title: Pools für die Zustellung ausgehender Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie die Übermittlungspools zum Schutz der Reputation von E-Mail-Servern in den Microsoft 365-Rechenzentren verwendet werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 461b5f9aa0407c5115ab84a075c793139a8b4305
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063368"
---
# <a name="outbound-delivery-pools"></a>Pools für die Zustellung ausgehender Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

E-Mail-Server in den Microsoft 365-Rechenzentren können sich vorübergehend für das Senden von Spam entschuldigen. Beispielsweise ein Schadsoftware- oder bösartiger Spamangriff in einer lokalen E-Mail-Organisation, die ausgehende E-Mails über Microsoft 365 sendet, oder gefährdete Microsoft 365-Konten. Angreifer versuchen außerdem, die Erkennung zu vermeiden, indem Sie Nachrichten über die Microsoft 365-Weiterleitung weiterleiten.

Diese Szenarien können dazu führen, dass die IP-Adresse der betroffenen Microsoft 365-Rechenzentrumsserver in Blocklisten von Drittanbietern angezeigt wird. Ziel-E-Mail-Organisationen, die diese Sperrlisten verwenden, lehnen E-Mails aus diesen Nachrichtenquellen ab.

## <a name="high-risk-delivery-pool"></a>Pool mit hohem Risiko
Um dies zu verhindern, werden alle ausgehenden Nachrichten von Microsoft 365-Rechenzentrumsservern, [](configure-the-outbound-spam-policy.md) die als Spam festgelegt sind oder die Sendegrenzwerte des Diensts oder ausgehender Spamrichtlinien überschreiten, über den Pool mit hohem Risiko gesendet. [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

Der Pool mit hohem Risiko ist ein separater IP-Adresspool für ausgehende E-Mails, der nur zum Senden von Nachrichten niedriger Qualität (z. B. Spam und [Backscatter) verwendet wird.](backscatter-messages-and-eop.md) Die Verwendung des Pools für die Zustellung mit hohem Risiko verhindert, dass der normale IP-Adresspool für ausgehende E-Mails Spam sendet. Der normale IP-Adresspool für ausgehende E-Mails behält die Reputation bei, die Nachrichten mit hoher Qualität sendet, wodurch die Wahrscheinlichkeit reduziert wird, dass diese IP-Adresse in IP-Sperrlisten angezeigt wird.

Die sehr reale Möglichkeit, dass IP-Adressen im Pool mit hohem Risiko in IP-Sperrlisten platziert werden, bleibt, aber dies ist entwurfsweise. Die Zustellung an die vorgesehenen Empfänger ist nicht garantiert, da viele E-Mail-Organisationen keine Nachrichten aus dem Pool mit hohem Risiko annehmen.

Weitere Informationen finden Sie unter [Steuern von ausgehenden Spamnachrichten.](outbound-spam-controls.md)

> [!NOTE]
> Nachrichten, bei denen die Quell-E-Mail-Domäne keinen A-Eintrag und keinen im öffentlichen DNS definierten MX-Eintrag hat, werden immer über den Pool mit hohem Risiko geroutet, unabhängig von ihrer Spam- oder Sendelimitdisposition.

### <a name="bounce-messages"></a>Unzustellbarkeitsnachrichten

Der Pool für ausgehende Zustellung mit hohem Risiko verwaltet die Zustellung für alle Unzustellbarkeitsberichte (auch als Unzustellbarkeitsberichte, Unzustellbarkeitsnachrichten, Zustellungsstatusbenachrichtigungen oder DSNs bekannt).

Mögliche Ursachen für einen Anstieg von Unerschbungs- und

- Eine Spoofingkampagne, die sich auf einen der Kunden auswirkt, die den Dienst verwenden.
- Ein Verzeichnisleseangriff.
- Ein Spamangriff.
- Ein nicht autorisierter E-Mail-Server.

All diese Probleme können zu einer plötzlichen Zunahme der Anzahl von Unntkräften führen, die vom Dienst verarbeitet werden. Viele Male scheinen diese Unntsprechenden Spam für andere E-Mail-Server und -Dienste (auch als _[Backscatter bekannt) zu sein.](backscatter-messages-and-eop.md)_

## <a name="relay-pool"></a>Relaypool

Nachrichten, die von Microsoft 365 weitergeleitet oder weitergeleitet werden, werden über einen speziellen Relaypool gesendet, da das endgültige Ziel Microsoft 365 nicht als tatsächlichen Absender betrachten sollte. Es ist auch wichtig, dass wir diesen Datenverkehr isolieren, da es legitime und ungültige Szenarien für die automatische Weiterleitung oder das Relay von E-Mails aus Microsoft 365 gibt. Ähnlich wie beim Pool mit hohem Risiko wird ein separater IP-Adresspool für relayierte E-Mails verwendet. Dieser Adresspool wird nicht veröffentlicht, da er sich häufig ändern kann.

Microsoft 365 muss überprüfen, ob der ursprüngliche Absender legitim ist, damit wir die weitergeleitete Nachricht sicher senden können. Dazu muss die E-Mail-Authentifizierung (SPF, DKIM und DMARC) übergeben werden, wenn die Nachricht an uns kommt. In Fällen, in denen wir den Absender authentifizieren können, verwenden wir Sender Rewriting, um dem Empfänger zu helfen, zu wissen, dass die weitergeleitete Nachricht von einer vertrauenswürdigen Quelle stammt. Weitere Informationen dazu, wie dies funktioniert und was Sie tun können, um sicherzustellen, dass die sendende Domäne die Authentifizierung übergibt, finden Sie unter [Sender Rewriting Scheme (SRS).](/office365/troubleshoot/antispam/sender-rewriting-scheme)