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
description: Administratoren können erfahren, wie Sie die Informationen zum Beheben von langsamen Nachrichtenflussregeln im Security & Compliance Center verwenden, um ineffiziente oder beschädigte Nachrichtenflussregeln (auch Transportregeln bezeichnet) in ihrer Organisation zu identifizieren und zu beheben.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 51ffa92402fd3e7c9e76115642426d3cce0a9e19
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061984"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Beheben von Einblicken in langsame Nachrichtenflussregeln im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Ineffiziente Nachrichtenflussregeln (auch als Transportregeln bezeichnet) können zu Verzögerungen beim Nachrichtenfluss für Ihre Organisation führen. In diesem Einblick werden Nachrichtenflussregeln berichtet, die auswirkungen auf den Nachrichtenfluss Ihrer Organisation haben. Beispiele für diese Arten von Regeln sind:

- Bedingungen, die **Is-Mitglied für** große Gruppen verwenden.
- Bedingungen, die einen Musterabgleich mit komplexen regulären Ausdrücken (Regex) verwenden.
- Bedingungen, die die Inhaltsüberprüfung in Anlagen verwenden.

Der **Einblick** in langsame  Nachrichtenflussregeln beheben [](mail-flow-insights-v2.md) im Bereich Empfohlen für Sie im Dashboard für den Nachrichtenfluss im Security [& Compliance Center](https://protection.office.com) benachrichtigt Sie, wenn eine Nachrichtenflussregel zu lange in Die Füllung geht.

Diese Einsicht wird erst angezeigt, nachdem die Bedingung erkannt wurde (wenn Sie keine E-Mail-Schleifen haben, wird der Einblick nicht angezeigt).

Mithilfe dieser Benachrichtigung können Sie Nachrichtenflussregeln identifizieren und optimieren, um Verzögerungen beim Nachrichtenfluss zu reduzieren.

![Beheben des Einblicks zu langsamen Nachrichtenflussregeln im Bereich Empfohlen für Sie im Dashboard für den Nachrichtenfluss](../../media/mfi-fix-slow-mail-flow-rules.png)

Wenn Sie auf **Details im** Widget anzeigen klicken, wird ein Flyout mit weiteren Informationen angezeigt:

- **Regel**: Sie können den Mauszeiger auf die Zusammenfassung zeigen, um alle Bedingungen, Ausnahmen und Aktionen der Regel zu sehen. Sie können auf die Zusammenfassung klicken, um die Regel im Exchange Admin Center (EAC) zu bearbeiten.
- **Anzahl der ausgewerteten** Nachrichten: Sie können [](message-trace-scc.md) auf Beispielnachrichten **anzeigen** klicken, um die Ergebnisse der Nachrichtenverfolgung für ein Beispiel der Nachrichten zu sehen, die von der Regel betroffen waren.
- **Durchschnittliche Zeit für jede Nachricht**
- **Mediane Zeit für eine Nachricht:** Der mittlere Wert, der die obere Hälfte von der unteren Hälfte der Zeitdaten trennt.

![Details-Flyout, das angezeigt wird, nachdem Sie auf Details anzeigen in der Einblicke in die Informationen zu langsamen Nachrichtenflussregeln korrigieren geklickt haben](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Weitere Informationen zu Bedingungen und Ausnahmen in Nachrichtenflussregeln finden Sie unter [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).