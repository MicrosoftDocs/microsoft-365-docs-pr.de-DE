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
description: Erfahren Sie, wie die Zustellungspools zum Schutz der Reputation von E-Mail-Servern in den Microsoft 365-Rechenzentren verwendet werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5480916f55fc180a6f08d3c420cb92c730e4065b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167539"
---
# <a name="outbound-delivery-pools"></a>Pools für die Zustellung ausgehender Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

E-Mail-Server in den Microsoft 365-Rechenzentren können vorübergehend keine Spamnachrichten senden. Beispiel: Schadsoftware oder böswilliger Spamangriff in einer lokalen E-Mail-Organisation, die ausgehende E-Mails über Microsoft 365 sendet, oder gefährdete Microsoft 365-Konten. Angreifer versuchen auch, die Erkennung zu vermeiden, indem sie Nachrichten über die Microsoft 365-Weiterleitung weiterleiten.

Diese Szenarien können dazu führen, dass die IP-Adresse der betroffenen Microsoft 365-Rechenzentrumsserver in Sperrlisten von Drittanbietern angezeigt wird. Ziel-E-Mail-Organisationen, die diese Sperrlisten verwenden, lehnen E-Mails von diesen Nachrichtenquellen ab.

## <a name="high-risk-delivery-pool"></a>Pool für besonders riskante Zustellung
Um dies zu verhindern, werden alle ausgehenden Nachrichten von Microsoft 365-Rechenzentrumsservern, [](configure-the-outbound-spam-policy.md) die als Spam ermittelt wurden oder die Sendegrenzwerte des Diensts oder der Richtlinien für ausgehende Spam überschreiten, über den Pool für besonders riskante Zustelldienste gesendet. [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

Der Pool für besonders riskante Zustellungen ist ein separater IP-Adresspool für ausgehende E-Mails, der nur zum Senden von Nachrichten niedriger Qualität (z. B. Spam und [Rückscatter) verwendet wird.](backscatter-messages-and-eop.md) Die Verwendung des Pools für besonders riskante Zustellung verhindert, dass der normale IP-Adresspool für ausgehende E-Mails Spam sendet. Der normale IP-Adresspool für ausgehende E-Mails behält die "hohe Qualität"-Nachricht-Reputation bei, wodurch die Wahrscheinlichkeit reduziert wird, dass diese IP-Adresse in den Listen blockierter IP-Adressen angezeigt wird.

Die sehr reale Möglichkeit, dass die IP-Adressen im Pool für besonders riskante Zustellungen in Listen blockierter IP-Adressen platziert werden, ist jedoch entwurfsweise. Die Zustellung an die vorgesehenen Empfänger ist nicht garantiert, da viele E-Mail-Organisationen keine Nachrichten aus dem Pool für besonders riskante Zustellnachrichten akzeptieren.

Weitere Informationen finden Sie unter [Steuern ausgehender Spamnachrichten.](outbound-spam-controls.md)

> [!NOTE]
> Nachrichten, bei denen die Quell-E-Mail-Domäne keinen A-Eintrag und keinen im öffentlichen DNS definierten MX-Eintrag hat, werden immer über den Pool für besonders riskante Übermittlungen geroutet, unabhängig von ihrer Spam- oder Sendegrenzwert-Disposition.

### <a name="bounce-messages"></a>Unzustellbarkeitsnachrichten

Der Pool für ausgehende Besonders riskante Zustellung verwaltet die Zustellung für alle Unzustellbarkeitsberichte (auch bekannt als Unzustellbarkeitsberichte, Unzustellbarkeitsnachrichten, Benachrichtigungen über den Zustellungsstatus oder DSNs).

Mögliche Ursachen für einen Anstieg der Unbndrs sind:

- Eine Spoofingkampagne, die sich auf einen der Kunden auswirkt, die den Dienst verwenden.
- Ein Verzeichnis-Harvest-Angriff.
- Ein Spamangriff.
- Ein nicht autorisierter E-Mail-Server.

All diese Probleme können dazu führen, dass die Anzahl der unbndrs, die vom Dienst verarbeitet werden, plötzlich erhöht wird. Viele Male scheinen diese NDRs anderen E-Mail-Servern und -Diensten (auch als Rückläufer bekannt) Spam zu _[sein.](backscatter-messages-and-eop.md)_

## <a name="relay-pool"></a>Relaypool

Nachrichten, die von Microsoft 365 weitergeleitet oder weitergeleitet werden, werden über einen speziellen Relaypool gesendet, da das endgültige Ziel Microsoft 365 nicht als tatsächlichen Absender betrachten sollte. Es ist uns auch wichtig, diesen Datenverkehr zu isolieren, da es legitime und ungültige Szenarien für das automatischeForwarding oder die Weiterleitung von E-Mails aus Microsoft 365 gibt. Ähnlich wie beim Pool für besonders riskante Zustellung wird ein separater IP-Adresspool für relayierte E-Mails verwendet. Dieser Adresspool wird nicht veröffentlicht, da er sich häufig ändern kann.

Microsoft 365 muss überprüfen, ob der ursprüngliche Absender legitim ist, damit wir die weitergeleitete Nachricht sicher zu senden können. Dazu muss die E-Mail-Authentifizierung (SPF, DKIM und DMARC) übergeben werden, wenn die Nachricht an uns gesendet wird. In Fällen, in denen wir den Absender authentifizieren können, verwenden wir Sender Rewriting, um dem Empfänger zu helfen, zu wissen, dass die weitergeleitete Nachricht von einer vertrauenswürdigen Quelle stammt. Weitere Informationen dazu, wie dies funktioniert und was Sie tun können, um sicherzustellen, dass die sendende Domäne die Authentifizierung im [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)besteht, finden Sie hier.
