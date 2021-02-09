---
title: Beheben des Einblicks in langsame Nachrichtenflussregeln
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie den Einblick in langsame Nachrichtenflussregeln im Security & Compliance Center verwenden, um ineffiziente oder beschädigte Nachrichtenflussregeln (auch als Transportregeln bezeichnet) in ihrer Organisation zu identifizieren und zu beheben.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7f084735decda922b5bcc57c029f2b384114d30
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150784"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Beheben von Einblicken in langsame Nachrichtenflussregeln im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Ineffiziente Nachrichtenflussregeln (auch als Transportregeln bezeichnet) können zu Verzögerungen beim Nachrichtenfluss für Ihre Organisation führen. In diesem Einblick werden Nachrichtenflussregeln berichtet, die sich auf den E-Mail-Fluss In Ihrer Organisation auswirken. Beispiele für diese Arten von Regeln sind:

- Bedingungen, die **"Is" für große** Gruppen verwenden.
- Bedingungen, die den Mustervergleich komplexer regulärer Ausdrücke (regex) verwenden.
- Bedingungen, die die Inhaltsüberprüfung in Anlagen verwenden.

Der **Einblick** in den Einblick  in langsame [](mail-flow-insights-v2.md) Nachrichtenflussregeln im Bereich "Empfohlen für Sie" des Dashboards für den Nachrichtenfluss im Security [& Compliance Center](https://protection.office.com) benachrichtigt Sie, wenn eine Nachrichtenflussregel zu lange zum Abschließen des Vorgangs ins Spiel kommt.

Dieser Einblick wird erst angezeigt, nachdem die Bedingung erkannt wurde (wenn Sie keine E-Mail-Schleifen haben, wird der Einblick nicht angezeigt).

Sie können diese Benachrichtigung verwenden, um Nachrichtenflussregeln zu identifizieren und zu optimieren, um Verzögerungen beim Nachrichtenfluss zu verringern.

![Beheben der Einblicke in langsame Nachrichtenflussregeln im Bereich "Empfohlen für Sie" des Dashboards für den Nachrichtenfluss](../../media/mfi-fix-slow-mail-flow-rules.png)

Wenn Sie im **Widget auf Details** anzeigen klicken, wird ein Flyout mit weiteren Informationen angezeigt:

- **Regel:** Sie können mit der Maus auf die Zusammenfassung zeigen, um alle Bedingungen, Ausnahmen und Aktionen der Regel zu sehen. Sie können auf die Zusammenfassung klicken, um die Regel im Exchange Admin Center (EAC) zu bearbeiten.
- **Anzahl der ausgewerteten** Nachrichten: Sie können [](message-trace-scc.md) auf "Beispielmeldungen anzeigen" klicken, um die Ergebnisse der Nachrichtenverfolgung für eine Stichprobe der nachrichten, die von der Regel betroffen waren, zu sehen. 
- **Durchschnittliche Zeit für jede Nachricht**
- **Median der Zeit für eine** Nachricht: Der mittlere Wert, der die obere Hälfte von der unteren Hälfte der Zeitdaten trennt.

![Details-Flyout, das nach dem Klicken auf "Details anzeigen" im Einblick "Langsamen Nachrichtenfluss beheben" angezeigt wird](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Weitere Informationen zu Bedingungen und Ausnahmen in Nachrichtenflussregeln finden Sie unter [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)
