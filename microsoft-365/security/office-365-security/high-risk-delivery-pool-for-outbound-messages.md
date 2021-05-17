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
description: Erfahren Sie, wie die Übermittlungspools verwendet werden, um die Reputation von E-Mail-Servern in den Microsoft 365 zu schützen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599911"
---
# <a name="outbound-delivery-pools"></a>Pools für die Zustellung ausgehender Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

E-Mail-Server in Microsoft 365 datencentern sind möglicherweise vorübergehend an der Versendung von Spam schuld. Beispielsweise ein Schadsoftware- oder schadhafter Spamangriff in einer lokalen E-Mail-Organisation, die ausgehende E-Mails über Microsoft 365 oder Microsoft 365 sendet. Angreifer versuchen außerdem, die Erkennung zu vermeiden, indem sie Nachrichten über Microsoft 365 weiterleiten.

Diese Szenarien können dazu führen, dass die IP-Adresse der betroffenen Microsoft 365 datencenterserver auf Blocklisten von Drittanbietern angezeigt wird. Ziel-E-Mail-Organisationen, die diese Sperrlisten verwenden, lehnen E-Mails aus diesen Nachrichtenquellen ab.

## <a name="high-risk-delivery-pool"></a>Pool mit hohem Risiko
Um dies zu verhindern, werden alle ausgehenden Nachrichten von Microsoft 365-Datencenterservern, [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) die als [](configure-the-outbound-spam-policy.md) Spam festgelegt sind oder die Sendegrenzwerte des Diensts oder ausgehender Spamrichtlinien überschreiten, über den Pool mit hohem Risiko _gesendet._

Der Pool mit hohem Risiko ist ein separater IP-Adresspool für ausgehende E-Mails, der nur zum Senden von Nachrichten niedriger Qualität (z. B. Spam und [Backscatter) verwendet wird.](backscatter-messages-and-eop.md) Die Verwendung des Pools für die Zustellung mit hohem Risiko verhindert, dass der normale IP-Adresspool für ausgehende E-Mails Spam sendet. Der normale IP-Adresspool für ausgehende E-Mails behält die Reputation bei, die Nachrichten mit hoher Qualität sendet, wodurch die Wahrscheinlichkeit verringert wird, dass diese IP-Adresse auf IP-Sperrlisten angezeigt wird.

Die sehr reale Möglichkeit, dass IP-Adressen im Pool mit hohem Risiko auf IP-Sperrlisten platziert werden, bleibt, aber dies ist entwurfsweise. Die Zustellung an die vorgesehenen Empfänger ist nicht garantiert, da viele E-Mail-Organisationen keine Nachrichten aus dem Pool mit hohem Risiko annehmen.

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
