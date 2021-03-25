---
title: Einblicke in Warteschlangen im Nachrichtenflussdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Administratoren können erfahren, wie Sie das Widget Warteschlangen im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um den erfolglosen Nachrichtenfluss über ausgehende Connectors an ihre lokalen oder Partnerorganisationen zu überwachen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 14cadd0e8611fbbc65c3bdc9849beebf3a3eb34d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206944"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>Einblicke in Warteschlangen im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Wenn Nachrichten nicht über Connectors von Ihrer Organisation an Ihre lokalen oder Partner-E-Mail-Server gesendet werden können, werden die Nachrichten in Microsoft 365 in die Warteschlange eingereiht. Häufige Beispiele, die diese Bedingung verursachen, sind:

- Der Connector ist falsch konfiguriert.
- In Ihrer lokalen Umgebung wurden Netzwerk- oder Firewalländerungen vorgenommen.

Microsoft 365 wird weiterhin 24 Stunden lang die Zustellung wiederholen. Nach 24 Stunden laufen die Nachrichten ab und werden in Unzustellbarkeitsberichten (auch als Unzustellbarkeitsberichte oder Unzustellbarkeitsnachrichten bekannt) an die Absender zurückgegeben.

Wenn das E-Mail-Volume in der Warteschlange den vordefinierten Schwellenwert überschreitet (der Standardwert ist 200 Nachrichten), sind die Informationen an den folgenden Speicherorten verfügbar:

- Der **Einblick in Warteschlangen** im [Nachrichtenflussdashboard](mail-flow-insights-v2.md) im [Security & Compliance Center](https://protection.office.com). Weitere Informationen finden Sie im [Abschnitt Warteschlangen im Abschnitt Nachrichtenflussdashboard](#queues-insight-in-the-mail-flow-dashboard) in diesem Artikel.

- Eine Warnung wird im **Dashboard** "Benachrichtigungen" im [Security & Compliance Center](https://protection.office.com) (**Alerts** Dashboard oder \>  ) angezeigt. <https://protection.office.com/alertsdashboard>

  ![Aktuelle Warnungen im Benachrichtigungsdashboard im Security & Compliance Center](../../media/mfi-queued-messages-alert.png)

- Administratoren erhalten eine E-Mail-Benachrichtigung basierend auf der Konfiguration der Standardbenachrichtigungsrichtlinie mit dem Namen **Nachrichten wurden verzögert.** Informationen zum Konfigurieren der Benachrichtigungseinstellungen für diese Warnung finden Sie im nächsten Abschnitt.

  Weitere Informationen zu Warnungsrichtlinien finden Sie unter [Warnungsrichtlinien im Security & Compliance Center](../../compliance/alert-policies.md).

## <a name="customize-queue-alerts"></a>Anpassen von Warteschlangenwarnungen

1. Wechseln Sie [im Security & Compliance Center](https://protection.office.com)zu Warnungsbenachrichtigungsrichtlinien, oder öffnen Sie  \>  <https://protection.office.com/alertpolicies> .

2. Suchen Und **wählen Sie auf** der Seite Warnungsrichtlinien die Richtlinie mit dem Namen Nachrichten wurden **verzögert.**

3. Im **geöffneten Flyout** Message have been delayed können Sie die Warnung aktivieren oder deaktivieren und die Benachrichtigungseinstellungen konfigurieren.

   ![Nachrichten wurden verzögert Benachrichtigungsrichtlinie Details der Security & Compliance Center](../../media/mfi-queued-messages-alert-policy.png)

   - **Status**: Sie können die Warnung ein- oder ausschalten.

   - **E-Mail-Empfänger** **und Grenzwert für tägliche Benachrichtigungen**: Klicken Sie auf **Bearbeiten,** um die folgenden Einstellungen zu konfigurieren:

4. Klicken Sie zum Konfigurieren der Benachrichtigungseinstellungen auf **Bearbeiten**. Konfigurieren Sie **im angezeigten** Flyout Richtlinie bearbeiten die folgenden Einstellungen:

   - Senden von E-Mail-Benachrichtigungen: Der Standardwert ist aktiviert. 
   - **E-Mail-Empfänger:** Der Standardwert ist **TenantAdmins**.
   - **Tägliches Benachrichtigungslimit:** Der Standardwert ist **No limit**.
   - **Schwellenwert**: Der Standardwert ist 200.

   ![Benachrichtigungseinstellungen in der Richtlinie "Nachrichten wurden verzögert" enthalten Details zum Security & Compliance Center](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. Klicken Sie nach Abschluss des Abschlusses **auf Speichern** und **Schließen.**

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>Einblicke in Warteschlangen im Nachrichtenflussdashboard

Auch wenn das Nachrichtenvolume in der Warteschlange den Schwellenwert nicht überschritten  und eine Warnung [](mail-flow-insights-v2.md) generiert hat, können Sie die Einblicke in Warteschlangen im Nachrichtenflussdashboard weiterhin verwenden, um Nachrichten anzuzeigen, die länger als eine Stunde in die Warteschlange eingereiht wurden, und Maßnahmen ergreifen, bevor die Anzahl der in die Warteschlange eingereihten Nachrichten zu groß wird.

![Warteschlangen-Widget im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-queues-widget.png)

Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein **Flyout in** der Warteschlange für Nachrichten mit den folgenden Informationen angezeigt:

- **Anzahl der in die Warteschlange eingereihten Nachrichten**
- **Connectorname**: Klicken Sie auf den Connectornamen, um den Connector im Exchange Admin Center (EAC) zu verwalten.
- **Startzeit der Warteschlange**
- **Älteste Nachrichten abgelaufen**
- **Zielserver**
- **Letzte IP-Adresse**
- **Letzter Fehler**
- **So beheben Sie:** Häufige Probleme und Lösungen sind verfügbar. Wenn ein **Link Jetzt beheben verfügbar** ist, klicken Sie darauf, um das Problem zu beheben. Klicken Sie andernfalls auf alle verfügbaren Links, um weitere Informationen über den Fehler und mögliche Lösungen zu erhalten.

![Details nach dem Klicken auf den Einblick in Warteschlangen im Nachrichtenflussdashboard](../../media/mfi-queues-details.png)

Das gleiche Flyout wird angezeigt, nachdem Sie **in** den Details einer Nachricht auf Warteschlange anzeigen geklickt **haben.**

![Nachrichten wurden im Security & Compliance Center verzögert](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).
