---
title: Fluss eingehender und ausgehender E-Mails
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 8/7/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 'Administratoren können sich über das Widget für ausgehende und eingehende Nachrichten im Nachrichtenfluss-Dashboard im Security #a0 Compliance Center informieren.'
ms.openlocfilehash: ceb85b9e83596c6c300c35ba471b04282074c82f
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970801"
---
# <a name="outbound-and-inbound-mail-flow"></a>Fluss eingehender und ausgehender E-Mails

Das Widget für **ausgehende und eingehende Nachrichtenübermittlung** kombiniert die Informationen aus dem **connectorbericht** und dem früheren TLS-Übersichts **Bericht** an einer Stelle.

![Der Bericht über den ausgehenden und eingehenden Nachrichtenfluss im Nachrichtenfluss-Dashboard im Security #a0 Compliance Center](../media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

Die Informationen im Widget beziehen sich auf Konnektoren und TLS-Nachrichtenschutz in Office 365. Weitere Informationen finden Sie unter den folgenden Themen:

- [Konfigurieren des Nachrichtenflusses mit Connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

- [Wie Exchange Online mithilfe von TLS E-Mail-Verbindungen in Office 365 sichert](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)

## <a name="message-protected-in-transit-by-tls"></a>Nachricht ist bei der Übertragung geschützt (durch TLS)

Das Widget für **ausgehende und eingehende Nachrichtenübermittlung** zeigt die TLS-Verschlüsselung an, die für die Verbindung verwendet wird, wenn Nachrichten an und von Ihrer Office 365 Organisation übermittelt werden. Die Verbindungen, die mit anderen e-Mail-Diensten hergestellt werden, werden durch TLS verschlüsselt, wenn beide Seiten TLS anbieten. Das Widget bietet eine Momentaufnahme der letzten Woche des Nachrichtenflusses. Wenn Sie auf **Details anzeigen**klicken, zeigt das Flyout **Nachricht geschützt im Transit (über TLS)** den TLS-Schutz für Nachrichten an, die in Ihre Organisation eingehen und diese verlassen.

![Das Flyout "Nachrichten in Transit (über TLS) geschützt im Security #a0 Compliance Center"](../media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

Derzeit ist TLS 1,2 die sicherste Version von TLS, die von Office 365 angeboten wird. Häufig müssen Sie die TLS-Verschlüsselung kennen, die für Compliance-Überprüfungen verwendet wird. Sie haben wahrscheinlich keine direkte Beziehung zu den meisten Quell-und Ziel-e-Mail-Servern (Sie besitzen diese nicht und auch nicht Microsoft), sodass Sie nicht viele Optionen zum Verbessern der TLS-Verschlüsselung haben, die von diesen Servern verwendet wird.

Sie können jedoch [Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) verwenden, um den bestmöglichen TLS-Schutz für Nachrichten sicherzustellen, die zwischen Ihren e-Mail-Servern und Office 365 gesendet werden. Der e-Mail-Fluss zwischen Office 365 und ihren eigenen e-Mail-Servern oder Servern, die zu ihren Partnern gehören, ist häufig wichtiger und sensibler als reguläre Nachrichten, daher sollten Sie zusätzliche Sicherheit und Wachsamkeit für diese Nachrichten anwenden. Sie können ein Upgrade oder eine Korrektur ihrer eigenen e-Mail-Server durchführen, um die verwendete TLS-Verschlüsselung zu verbessern oder Ihre Partner zu erreichen, um dasselbe zu tun. Im **Bericht "Connector** " werden sowohl das Nachrichtenfluss Volumen als auch die TLS-Verschlüsselung für Nachrichten angezeigt, die Ihre Office 365-Konnektoren verwenden.

## <a name="connector-report"></a>Connector-Bericht

Wenn Sie auf den Link **connectorbericht** im Flyout **Nachricht Protected in Transit (by TLS)** klicken, zeigt der Bericht Informationen zu Nachrichten an, die an und von Ihrer Office 365 Organisation mithilfe von Connectors übermittelt werden. Sie verwenden Connectors zwischen ihren eigenen e-Mail-Servern und Office 365 oder den Servern und Office 365 Ihres Partners. Das Nachrichtenvolumen für jeden Connector und die TLS-Verschlüsselung für die Verbindung ist verfügbar. Darüber hinaus können Sie auch Daten für Nachrichten anzeigen, die in Office 365 gesendet oder empfangen wurden, ohne einen Connector zu verwenden.

In der Ansicht **Nachrichtenfluss** wird die Anzahl der Nachrichten über den Connector für die vergangene Woche angezeigt. Sie können den Datumsbereich ändern, indem Sie **Filter** auswählen, in dem Sie den Bereich auf maximal 30 Tage erweitern können. In der Ansicht " **alle e-Mail-Fluss** " wird der gesamte Nachrichtenfluss zu und von Ihrer Office 365 Organisation über alle Connectors angezeigt. Sie können einen bestimmten Konnektor im Dropdownmenü nach Namen auswählen.

Sie können die Ansicht **TLS-Einsatz** in der Dropdownliste auswählen, um die Aufschlüsselung des TLS-Schutzes für Nachrichten über den Connector anzuzeigen. Wie beim Bericht **über TLS** -Übersichtsberichte wird in dieser Ansicht der Prozentsatz der verschiedenen TLS-Versionen angezeigt. Für TLS 1,0-Verbindungen müssen Sie Ihren e-Mail-Server oder den Server Ihres Partners wirklich aktualisieren oder reparieren lassen, um Probleme zu vermeiden, wenn die TLS 1,0-Unterstützung in Office 365 endgültig veraltet ist. Weitere Informationen finden Sie unter [technische Referenzdetails zur Verschlüsselung in Office 365](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption).

Einblicke verweisen auf Connectors, um Ihre Aufmerksamkeit auf mögliche TLS-Verschlüsselungsprobleme für den Connector zu lenken. Die Einblicke sind: **kein TLS ist über 25%** oder **TLS 1,0 liegt über 50%**. Wenn diese Einblicke angezeigt werden, müssen Sie die dem Connector zugeordneten e-Mail-Server überprüfen oder Ihre Partnerorganisation erreichen.

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen e-Mail-Fluss-Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security #a0 Compliance Center](mail-flow-insights-v2.md).
