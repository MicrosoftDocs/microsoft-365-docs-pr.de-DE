---
title: Einblicke in ausgehenden und eingehenden Nachrichtenfluss im Nachrichtenflussdashboard
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
description: Administratoren können sich im Dashboard für den Nachrichtenfluss im Security & Compliance Center über den Einblick in den Nachrichtenfluss ausgehender und eingehender Nachrichten informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a3117223e466a4a7aad7edf25ecdbcf0a3de719
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204137"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Einblicke in ausgehende und eingehende E-Mails im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Der **Einblick** in ausgehende und [](mail-flow-insights-v2.md) eingehende Nachrichten im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) kombiniert die Informationen aus dem [Connectorbericht](view-mail-flow-reports.md#connector-report) und dem früheren **TLS-Übersichtsbericht** an einem Ort.

Das Widget zeigt die TLS-Verschlüsselung an, die für die Verbindung verwendet wird, wenn Nachrichten an Und von Ihrer Organisation zugestellt werden. Die Verbindungen, die mit anderen E-Mail-Diensten hergestellt werden, werden von TLS verschlüsselt, wenn TLS von beiden Seiten angeboten wird. Das Widget bietet eine Momentaufnahme der letzten Woche des Nachrichtenflusses.

![Widget für ausgehenden und eingehenden Nachrichtenfluss im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

Die Informationen im Widget stehen im Zusammenhang mit Connectors und dem TLS-Nachrichtenschutz in Microsoft 365. Weitere Informationen finden Sie unter den folgenden Themen:

- [Konfigurieren des Nachrichtenflusses mit Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Wie Exchange Online mithilfe von TLS E-Mail-Verbindungen schützt](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [Technische Referenzdetails zur Verschlüsselung in Microsoft 365](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a>Nachricht, die bei der Übertragung geschützt ist (durch TLS)

Wenn Sie **im** Widget auf Details anzeigen klicken, zeigt ihnen das Flyout Message **protected in transit (by TLS)** den TLS-Schutz für Nachrichten, die Ihre Organisation betreten und verlassen.

![Nachrichten, die bei der Übertragung (durch TLS) geschützt sind und angezeigt werden, nachdem Sie im Widget Ausgehende und eingehende E-Mails auf Details anzeigen geklickt haben](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

Derzeit ist TLS 1.2 die sicherste Version von TLS, die von Microsoft 365. Häufig müssen Sie die TLS-Verschlüsselung kennen, die für Compliance-Audits verwendet wird. Wahrscheinlich haben Sie keine direkte Beziehung zu den meisten Quell- und Ziel-E-Mail-Servern (Sie besitzen sie nicht, und Microsoft auch nicht), daher haben Sie nicht viele Optionen, um die von diesen Servern verwendete TLS-Verschlüsselung zu verbessern.

Sie können jedoch Connectors [verwenden,](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) um den besten verfügbaren TLS-Schutz für Nachrichten sicherzustellen, die zwischen Ihren E-Mail-Servern und Microsoft 365. Der E-Mail-Fluss zwischen Microsoft 365 und Ihren eigenen E-Mail-Servern oder Servern, die Zu Ihren Partnern gehören, ist häufig wichtiger und vertraulicher als normale Nachrichten, daher sollten Sie zusätzliche Sicherheit und Überwachung auf diese Nachrichten anwenden.

Sie können Ihre eigenen E-Mail-Server aktualisieren oder beheben, um die verwendete TLS-Verschlüsselung zu verbessern, oder Ihre Partner kontaktieren, um dies zu tun. Der **Connectorbericht zeigt** sowohl das Volumen des Nachrichtenflusses als auch die TLS-Verschlüsselung für Nachrichten an, die Ihre Microsoft 365 verwenden.

Sie können auf den **Link Connectorbericht klicken,** um zum [Connectorbericht zu wechseln.](view-mail-flow-reports.md#connector-report) Die folgenden Einblicke stehen möglicherweise auf der Seite **Connectorbericht** zur Verfügung, wenn die zugeordnete Bedingung erkannt wurde:

- **Eingehender Partnerconnector mit erheblichem TLS1.0-E-Mail-Fluss**
- **Eingehender OnPremises-Connector mit erheblichem TLS1.0-E-Mail-Fluss**

Für TLS 1.0-Verbindungen müssen Sie ihren E-Mail-Server oder den Server Ihres Partners wirklich aktualisiert oder behoben haben, um Probleme zu vermeiden, wenn die TLS 1.0-Unterstützung in diesem Fall nicht mehr Microsoft 365.

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).