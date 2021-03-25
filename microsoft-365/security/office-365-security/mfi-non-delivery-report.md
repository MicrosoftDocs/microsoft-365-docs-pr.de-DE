---
title: Unzustellungsbericht im Nachrichtenflussdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren erfahren, wie Sie den Bericht "Unzustellbarkeitsdetails" im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um die am häufigsten aufgetretenen Fehlercodes in Unzustellbarkeitsberichten (auch als Unzustellbarkeitsberichte bezeichnet) von Absendern in Ihrer Organisation zu überwachen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d25f11051606139c2ee8b88cade18963de599d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206321"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Unzustellungsbericht im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Der  Unzustellbarkeitsbericht [](mail-flow-insights-v2.md) im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) zeigt die am häufigsten aufgetretenen Fehlercodes in Unzustellbarkeitsberichten (auch als Unzustellbarkeitsberichte oder Unzustellbarkeitsnachrichten bezeichnet) für Benutzer in Ihrer Organisation an. Dieser Bericht zeigt die Details von Unzustellungssberichten, damit Sie Probleme mit der E-Mail-Zustellung beheben können.

![Widget für nicht zugestellte Berichte im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>Berichtsansicht für den Unzustellungsbericht

Wenn Sie auf das **Widget "Unzustellungsbericht"** klicken, werden Sie zum **Unzustellungsbericht angezeigt.**

Standardmäßig wird die Aktivität für alle Fehlercodes angezeigt. Wenn Sie auf **Daten anzeigen für klicken,** können Sie in der Dropdownliste einen bestimmten Fehlercode auswählen.

Wenn Sie an einem bestimmten Tag im Diagramm auf eine bestimmte Farbe (Fehlercode) zeigen, wird die Gesamtanzahl der Meldungen für den Fehler angezeigt.

![Berichtsansicht im Nicht akzeptierten Domänenbericht](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>Detailtabelle für den Unzustellungsbericht

Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:

- **Date**
- **Unzustellungsberichtscode**
- **Count**
- **Beispielnachrichten:** Die Nachrichten-IDs eines Beispiels betroffener Nachrichten.

Wenn Sie in einer **Detailtabelle** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Klicken Sie auf Herunterladen anfordern, um den Bericht für einen bestimmten Datumsbereich an einen oder mehrere **Empfänger zu senden.**

Wenn Sie eine Zeile in der Tabelle auswählen, wird ein Flyout mit den folgenden Informationen angezeigt:

- **Date**
- **Code für nicht zustellfreie** Berichte: Sie können auf den Link klicken, um weitere Informationen zu den Ursachen und Lösungen für den spezifischen Fehlercode zu erhalten.
- **Count**
- **Beispielnachrichten:** Sie können auf **Beispielnachrichten anzeigen klicken,** um die Ergebnisse der Nachrichtenverfolgung für ein Beispiel der betroffenen Nachrichten zu sehen. [](message-trace-scc.md)

![Detailf flyout nach dem Auswählen einer Zeile in der Detailtabelle in der Unzustellungsbericht](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>Verwandte Themen

Weitere Informationen zu anderen Erkenntnissen im Nachrichtenflussdashboard finden Sie unter Einblicke in den Nachrichtenfluss [im Security & Compliance Center](mail-flow-insights-v2.md).
