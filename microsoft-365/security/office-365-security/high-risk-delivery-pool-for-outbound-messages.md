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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie die Zustellungs Pools verwendet werden, um die Reputation von e-Mail-Servern in Microsoft 365-Rechenzentren zu schützen.
ms.openlocfilehash: b3016be7c1887536fe3e742b5ab4ec598b6a5f89
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201489"
---
# <a name="outbound-delivery-pools"></a>Pools für die Zustellung ausgehender Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


E-Mail-Server in den Microsoft 365-Rechenzentren sind möglicherweise vorübergehend für das Senden von Spam schuldig. Beispielsweise eine Schadsoftware oder ein böswilliger Spamangriff in einer lokalen e-Mail-Organisation, die ausgehende e-Mails über Microsoft 365 sendet oder Microsoft 365-Konten kompromittiert. Angreifer versuchen auch, die Erkennung durch Weiterleiten von Nachrichten über die Microsoft 365-Weiterleitung zu vermeiden.

Diese Szenarien können dazu führen, dass die IP-Adresse der betroffenen Microsoft 365 Datacenter-Server in Blocklisten von Drittanbietern angezeigt wird. Ziel-e-Mail-Organisationen, die diese Sperrlisten verwenden, lehnen e-Mails von diesen Nachrichtenquellen ab.

## <a name="high-risk-delivery-pool"></a>Hochriskanter Zustellungs Pool
Um dies zu verhindern, werden alle ausgehenden Nachrichten von Microsoft 365 Datacenter-Servern, die als Spam festgestellt werden oder die die Sende Grenzen des [Diensts](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) oder der [ausgehenden Spam Richtlinien](configure-the-outbound-spam-policy.md) überschreiten, über den _Pool mit hoher Risikoverteilung_gesendet.

Der Pool mit hoher Risikoverteilung ist ein separater IP-Adresspool für ausgehende e-Mails, der nur zum Senden von Nachrichten mit niedriger Qualität verwendet wird (beispielsweise Spam und [Backscatter](backscatter-messages-and-eop.md)). Die Verwendung des Pools mit hoher Risikoverteilung verhindert, dass der normale IP-Adresspool für ausgehende e-Mails Spam sendet. Der normale IP-Adresspool für ausgehende e-Mails behält die Reputation, die Nachrichten mit hoher Qualität sendet, wodurch die Wahrscheinlichkeit verringert wird, dass diese IP-Adresse in IP-Sperrlisten angezeigt wird.

Die reale Möglichkeit, dass IP-Adressen im hochriskanten Zustellungs Pool in IP-Sperrlisten eingefügt werden, bleibt jedoch im Entwurf. Die Zustellung an die vorgesehenen Empfänger ist nicht gewährleistet, da viele e-Mail-Organisationen keine Nachrichten aus dem Pool mit hoher Risikoverteilung annehmen.

Weitere Informationen finden Sie unter [Control Outbound Spam](outbound-spam-controls.md).

> [!NOTE]
> Nachrichten, bei denen die Quell-e-Mail-Domäne keinen Datensatz und keinen im öffentlichen DNS definierten MX-Eintrag enthält, werden immer über den risikoreichen Zustellungs Pool weitergeleitet, unabhängig von ihrer Spam-oder sende Grenzwert-Disposition.

### <a name="bounce-messages"></a>Bounce-Nachrichten

Der ausgehende Pool mit hoher Risikoverteilung verwaltet die Zustellung für alle Unzustellbarkeitsberichte (auch bekannt als NDR, Unzustellbarkeitsnachrichten, Benachrichtigungen über Zustellungsstatus oder DSNs).

Zu den möglichen Ursachen für einen Anstieg bei Unzustellbarkeitsberichten gehören:

- Eine Spoofing-Kampagne, die sich auf einen Kunden auswirkt, der den Dienst verwendet.
- Ein Verzeichnis Lese Angriff.
- Ein Spamangriff.
- Ein Rogue-e-Mail-Server.

Alle diese Probleme können zu einer plötzlichen Vergrößerung der Anzahl von Unzustellbarkeitsberichten führen, die vom Dienst verarbeitet werden. Viele Male scheinen diese Unzustellbarkeitsberichte Spam auf andere e-Mail-Server und-Dienste zu sein (auch bekannt als _[Backscatter](backscatter-messages-and-eop.md)_).

## <a name="relay-pool"></a>Relay-Pool

Nachrichten, die von Microsoft 365 weitergeleitet oder weitergeleitet werden, werden über einen speziellen Relay-Pool gesendet, da das endgültige Ziel Microsoft 365 nicht als tatsächlichen Absender berücksichtigen sollte. Es ist auch wichtig, dass wir diesen Datenverkehr isolieren, da es legitime und ungültige Szenarien für die Auto Weiterleitung oder das Weiterleiten von e-Mails von Microsoft 365 gibt. Ähnlich wie bei dem Pool mit hoher Risikoverteilung wird für weitergeleitete e-Mails ein separater IP-Adresspool verwendet. Dieser Adresspool wird nicht veröffentlicht, da er häufig geändert werden kann.

Microsoft 365 muss sicherstellen, dass der ursprüngliche Absender legitim ist, damit wir die weitergeleitete Nachricht zuverlässig übermitteln können. Um dies zu erreichen, muss die e-Mail-Authentifizierung (SPF, DKIM und DMARC) übergeben werden, wenn die Nachricht zu uns kommt. In Fällen, in denen der Absender authentifiziert werden kann, verwenden wir die Absender Umschreibung, um dem Empfänger zu helfen, zu wissen, dass die weitergeleitete Nachricht von einer vertrauenswürdigen Quelle stammt. Sie können mehr darüber erfahren, wie das funktioniert und was Sie tun können, um sicherzustellen, dass die sendende Domäne die Authentifizierung im [Absender umschreibungs Schema (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)übergibt.
