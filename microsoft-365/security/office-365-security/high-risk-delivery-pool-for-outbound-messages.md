---
title: Pool für besonders riskante Zustellungen für ausgehende Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie der Pool mit hoher Risikoverteilung verwendet wird, um die Reputation von e-Mail-Servern in den Office 365-Rechenzentren zu schützen.
ms.openlocfilehash: 5d1bd2b14eb17ed74ee1cf1e44967f660f4595b8
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895359"
---
# <a name="high-risk-delivery-pool-for-outbound-messages-in-office-365"></a>Hochriskanter Zustellungs Pool für ausgehende Nachrichten in Office 365

E-Mail-Server in den Office 365-Rechenzentren sind möglicherweise vorübergehend für das Senden von Spam schuldig. Beispielsweise eine Schadsoftware oder ein böswilliger Spamangriff in einer lokalen e-Mail-Organisation, die ausgehende e-Mails über Office 365 oder kompromittierte Office 365 Konten sendet. Diese Szenarien können dazu führen, dass die IP-Adresse der betroffenen Office 365 Datacenter-Server in Blocklisten von Drittanbietern angezeigt wird. Ziel-e-Mail-Organisationen, die diese Sperrlisten verwenden, lehnen e-Mails von diesen Nachrichtenquellen ab.

Um dies zu verhindern, werden alle ausgehenden Nachrichten von Office 365 Datacenter-Servern, die als Spam festgestellt werden oder die die Sende Grenzen des [Diensts](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) oder der [ausgehenden Spam-Richtlinien](configure-the-outbound-spam-policy.md) überschreiten, über den _hochriskanten Zustellungs Pool_gesendet.

Der Pool mit hoher Risikoverteilung ist ein sekundärer IP-Adresspool für ausgehende e-Mails, der nur zum Senden von Nachrichten mit niedriger Qualität verwendet wird (beispielsweise Spam und [Backscatter](backscatter-messages-and-eop.md)). Die Verwendung des Pools mit hoher Risikoverteilung verhindert, dass der normale IP-Adresspool für ausgehende e-Mails Spam sendet. Der normale IP-Adresspool für ausgehende e-Mails behält die Reputation, die Nachrichten mit hoher Qualität sendet, wodurch die Wahrscheinlichkeit verringert wird, dass diese IP-Adresse in IP-Sperrlisten angezeigt wird.

Die reale Möglichkeit, dass IP-Adressen im hochriskanten Zustellungs Pool in IP-Sperrlisten eingefügt werden, bleibt jedoch im Entwurf. Die Zustellung an die vorgesehenen Empfänger ist nicht gewährleistet, da viele e-Mail-Organisationen keine Nachrichten aus dem Pool mit hoher Risikoverteilung annehmen.

Weitere Informationen finden Sie unter [Steuern von ausgehenden Spamnachrichten in Office 365](outbound-spam-controls.md).

> [!NOTE]
> Nachrichten, bei denen die Quell-e-Mail-Domäne keinen Datensatz und keinen im öffentlichen DNS definierten MX-Eintrag enthält, werden immer über den risikoreichen Zustellungs Pool weitergeleitet, unabhängig von ihrer Spam-oder sende Grenzwert-Disposition.

## <a name="bounce-messages"></a>Bounce-Nachrichten

Der ausgehende Pool mit hoher Risikoverteilung verwaltet die Zustellung für alle Unzustellbarkeitsberichte (auch bekannt als NDR, Unzustellbarkeitsnachrichten, Benachrichtigungen über Zustellungsstatus oder DSNs).

Zu den möglichen Ursachen für einen Anstieg bei Unzustellbarkeitsberichten gehören:

- Eine Spoofing-Kampagne, die sich auf einen Kunden auswirkt, der den Dienst verwendet.

- Ein Verzeichnis Lese Angriff.

- Ein Spamangriff.

- Ein Rogue-e-Mail-Server.

Alle diese Probleme können zu einer plötzlichen Vergrößerung der Anzahl von Unzustellbarkeitsberichten führen, die vom Dienst verarbeitet werden. Viele Male scheinen diese Unzustellbarkeitsberichte Spam auf andere e-Mail-Server und-Dienste zu sein (auch bekannt als _[Backscatter](backscatter-messages-and-eop.md)_).
