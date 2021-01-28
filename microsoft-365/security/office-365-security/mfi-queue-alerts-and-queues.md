---
title: Einblick in Warteschlangen im Nachrichtenflussdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Administratoren können erfahren, wie Sie das Widget "Warteschlangen" im Dashboard für den Nachrichtenfluss im Security & Compliance Center verwenden, um den nicht erfolgreichen Nachrichtenfluss über ausgehende Connectors zu ihrer lokalen oder Partnerorganisation zu überwachen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 73e97cbbd05e298013e9e686053a969d587ad5cf
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029150"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>Einblicke in Warteschlangen im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Wenn Nachrichten nicht über Connectors von Ihrer Organisation an Ihre lokalen oder Partner-E-Mail-Server gesendet werden können, werden die Nachrichten in microsoft 365 in die Warteschlange gestellt. Häufige Beispiele für diese Bedingung sind:

- Der Connector ist falsch konfiguriert.
- In Ihrer lokalen Umgebung wurden Netzwerk- oder Firewalländerungen vorgenommen.

Microsoft 365 retry to delivery for 24 hours. Nach 24 Stunden laufen die Nachrichten ab und werden in Unzustellbarkeitsberichten (auch als Unzustellbarkeitsnachrichten oder Unzustellbarkeitsnachrichten bekannt) an die Absender zurückgesendet.

Wenn das E-Mail-Volume in der Warteschlange den vordefinierten Schwellenwert überschreitet (der Standardwert ist 200 Nachrichten), stehen die Informationen an den folgenden Stellen zur Verfügung:

- Der **Einblick in Warteschlangen** im [Nachrichtenflussdashboard](mail-flow-insights-v2.md) im [Security & Compliance Center.](https://protection.office.com) Weitere Informationen finden Sie in den Einblicken in Warteschlangen im Abschnitt zum [Nachrichtenflussdashboard](#queues-insight-in-the-mail-flow-dashboard) in diesem Artikel.

- Eine Warnung wird  im Dashboard "Warnungen" im Security & Compliance Center **(Dashboard** für Warnungen oder ) in [den](https://protection.office.com) letzten Warnungen \>  <https://protection.office.com/alertsdashboard> angezeigt.

  ![Aktuelle Warnungen im Benachrichtigungsdashboard im Security & Compliance Center](../../media/mfi-queued-messages-alert.png)

- Administratoren erhalten eine E-Mail-Benachrichtigung, die auf der Konfiguration der standardmäßigen Warnungsrichtlinie namens **"Nachrichten wurden verzögert" basiert.** Informationen zum Konfigurieren der Benachrichtigungseinstellungen für diese Warnung finden Sie im nächsten Abschnitt.

  Weitere Informationen zu Warnungsrichtlinien finden Sie unter [Warnungsrichtlinien im Security & Compliance Center](../../compliance/alert-policies.md).

## <a name="customize-queue-alerts"></a>Anpassen von Warteschlangenwarnungen

1. Wechseln Sie [im Security & Compliance Center](https://protection.office.com)zu Warnungsrichtlinien, oder öffnen Sie  \>  . <https://protection.office.com/alertpolicies>

2. Suchen Und wählen **Sie auf der** Seite "Warnungsrichtlinien" die Richtlinie mit dem Namen **"Nachrichten wurden verzögert" aus.**

3. Im **flyout "Nachricht wurde verzögert",** das geöffnet wird, können Sie die Warnung aktivieren oder deaktivieren und die Benachrichtigungseinstellungen konfigurieren.

   ![Nachrichten wurden verzögert Warnungsrichtliniendetails im Security & Compliance Center](../../media/mfi-queued-messages-alert-policy.png)

   - **Status:** Sie können die Warnung ein- oder ausschalten.

   - **E-Mail-Empfänger** **und Grenzwert für tägliche Benachrichtigungen:** Klicken Sie auf **"Bearbeiten",** um die folgenden Einstellungen zu konfigurieren:

4. Klicken Sie auf Bearbeiten, um die Benachrichtigungseinstellungen **zu konfigurieren.** Konfigurieren Sie **im angezeigten** Flyout "Richtlinie bearbeiten" die folgenden Einstellungen:

   - **E-Mail-Benachrichtigungen** senden: Der Standardwert ist aktiviert.
   - **E-Mail-Empfänger:** Der Standardwert ist **TenantAdmins**.
   - **Grenzwert für tägliche** Benachrichtigungen: Der Standardwert ist **"No limit".**
   - **Schwellenwert:** Der Standardwert ist 200.

   ![Benachrichtigungseinstellungen in den Nachrichten wurden verzögert Warnungsrichtlinie Details im Security & Compliance Center](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. Wenn Sie fertig sind, klicken Sie auf **"Speichern"** und **"Schließen".**

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>Einblick in Warteschlangen im Nachrichtenflussdashboard

Auch wenn das Nachrichtenvolume in der Warteschlange den Schwellenwert nicht überschritten  und eine Warnung [](mail-flow-insights-v2.md) generiert hat, können Sie die Einblicke in Warteschlangen im Nachrichtenflussdashboard verwenden, um Nachrichten anzuzeigen, die länger als eine Stunde in die Warteschlange eingereiht wurden, und Maßnahmen ergreifen, bevor die Anzahl der in die Warteschlange eingereihten Nachrichten zu groß wird.

![Warteschlangen-Widget im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-queues-widget.png)

Wenn Sie auf die Anzahl der  Nachrichten im Widget klicken, wird ein Flyout in der Warteschlange mit den folgenden Informationen angezeigt:

- **Anzahl der Nachrichten in der Warteschlange**
- **Connectorname:** Klicken Sie auf den Connectornamen, um den Connector im Exchange Admin Center (EAC) zu verwalten.
- **Startzeit der Warteschlange**
- **Älteste Nachrichten sind abgelaufen**
- **Zielserver**
- **Letzte IP-Adresse**
- **Letzter Fehler**
- **Problembehebt:** Häufige Probleme und Lösungen sind verfügbar. If is a **Fix it now** link is available, click it to fix the problem. Klicken Sie andernfalls auf alle verfügbaren Links, um weitere Informationen zu dem Fehler und möglichen Lösungen zu erhalten.

![Details nach dem Klicken auf den Einblick "Warteschlangen" im Nachrichtenflussdashboard](../../media/mfi-queues-details.png)

Das gleiche Flyout wird angezeigt, nachdem Sie **in** den Details einer Benachrichtigung auf "Warteschlange anzeigen" **geklickt** haben.

![Nachrichten wurden im Security & Compliance Center verzögert](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)
