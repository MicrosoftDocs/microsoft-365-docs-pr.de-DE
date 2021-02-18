---
title: Einblick in den Nachrichtenfluss ausgehender und eingehender Nachrichten im Nachrichtenflussdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Administratoren können sich über den Einblick in den Nachrichtenfluss ausgehender und eingehender Nachrichten im Dashboard für den Nachrichtenfluss im Security & Compliance Center informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 87c5bd9ab0d550f50feabbb96176debbe04863e5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289449"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Einblick in den Ausgehenden und eingehenden Nachrichtenfluss im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Der **Einblick** in ausgehende und [](mail-flow-insights-v2.md) eingehende Nachrichten im Nachrichtenflussdashboard im Security [](view-mail-flow-reports.md#connector-report) [& Compliance Center](https://protection.office.com) kombiniert die Informationen aus dem Connectorbericht und dem früheren **TLS-Übersichtsbericht** an einem Ort.

Das Widget zeigt die TLS-Verschlüsselung an, die für die Verbindung verwendet wird, wenn Nachrichten an Und von Ihrer Organisation zugestellt werden. Die Verbindungen, die mit anderen E-Mail-Diensten hergestellt werden, werden von TLS verschlüsselt, wenn TLS von beiden Seiten angeboten wird. Das Widget bietet eine Momentaufnahme der letzten Woche des Nachrichtenflusses.

![Widget für ausgehenden und eingehenden Nachrichtenfluss im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

Die Informationen im Widget stehen im Zusammenhang mit Connectors und dem Schutz von TLS-Nachrichten in Microsoft 365. Weitere Informationen finden Sie unter den folgenden Themen:

- [Konfigurieren des Nachrichtenflusses mit Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Wie Exchange Online mithilfe von TLS E-Mail-Verbindungen schützt](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [Technische Referenzdetails zur Verschlüsselung in Microsoft 365](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a>Nachricht, die bei der Übertragung geschützt ist (durch TLS)

Wenn Sie **auf** "Details anzeigen" im Widget klicken, wird im Flyout "Nachricht, die während der Übertragung **(durch TLS)** geschützt ist" der TLS-Schutz für Nachrichten angezeigt, die in Ihre Organisation ein- und austritten.

![Nachrichten, die bei der Übertragung (durch TLS) geschützt sind und angezeigt werden, nachdem Sie im Widget für ausgehende und eingehende E-Mails auf Details anzeigen geklickt haben](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

Derzeit ist TLS 1.2 die sicherste Version von TLS, die von Microsoft 365 angeboten wird. Häufig müssen Sie die TLS-Verschlüsselung kennen, die für Compliance-Überwachungen verwendet wird. Wahrscheinlich haben Sie keine direkte Beziehung zu den meisten Quell- und Ziel-E-Mail-Servern (Sie besitzen sie nicht, und microsoft auch nicht), sodass Sie nicht viele Optionen haben, um die von diesen Servern verwendete TLS-Verschlüsselung zu verbessern.

Sie können jedoch Connectors [verwenden,](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) um den besten verfügbaren TLS-Schutz für Nachrichten sicherzustellen, die zwischen Ihren E-Mail-Servern und Microsoft 365 gesendet werden. Der E-Mail-Fluss zwischen Microsoft 365 und Ihren eigenen E-Mail-Servern oder -Servern, die Zu Ihren Partnern gehören, ist häufig wichtiger und vertraulicher als normale Nachrichten, daher sollten Sie zusätzliche Sicherheit und Anzance auf diese Nachrichten anwenden.

Sie können Ihre eigenen E-Mail-Server aktualisieren oder korrigieren, um die verwendete TLS-Verschlüsselung zu verbessern, oder sich an Ihre Partner zu halten, um dies zu tun. Im **Connectorbericht werden** sowohl das Nachrichtenflussvolumen als auch die TLS-Verschlüsselung für Nachrichten angezeigt, die Ihre Microsoft 365-Connectors verwenden.

Sie können auf den **Connectorberichtslink** klicken, um zum [Connectorbericht zu wechseln.](view-mail-flow-reports.md#connector-report) Die folgenden Erkenntnisse sind möglicherweise auf der Seite **"Connectorbericht"** verfügbar, wenn die zugeordnete Bedingung erkannt wurde:

- **Eingehender Partnerconnector mit erheblichem TLS1.0-Nachrichtenfluss**
- **Eingehender OnPremises-Connector mit erheblichem TLS1.0-Nachrichtenfluss**

Für TLS 1.0-Verbindungen müssen Sie ihren E-Mail-Server oder den Server Ihres Partners wirklich upgraden oder beheben, um Probleme zu vermeiden, wenn die TLS 1.0-Unterstützung in Microsoft 365 möglicherweise nicht mehr unterstützt wird.

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)
