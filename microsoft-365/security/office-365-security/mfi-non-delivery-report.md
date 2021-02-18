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
description: Administratoren können erfahren, wie Sie den Bericht über Unzustellbarkeitsdetails im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um die am häufigsten aufgetretenen Fehlercodes in Unzustellbarkeitsberichten (auch als Unzustellbarkeitsnachrichten bezeichnet) von Absendern in Ihrer Organisation zu überwachen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e31e7dfcbd3c0cacaa6020464ed315f466a849b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287889"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Unzustellungsbericht im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Der  Unzustellbarkeitsbericht [](mail-flow-insights-v2.md) im Nachrichtenflussdashboard im [Security & Compliance Center](https://protection.office.com) zeigt die häufigsten Fehlercodes in Unzustellbarkeitsberichten (auch NDRs oder Unzustellbarkeitsnachrichten bezeichnet) für Benutzer in Ihrer Organisation an. Dieser Bericht enthält die Details von Unzustellungsberichten, damit Sie Probleme mit der Zustellung von E-Mails beheben können.

![Unzustellungsbericht-Widget im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>Berichtsansicht für den Unzustellungsbericht

Wenn Sie auf das **Widget "Unzustellungsbericht"** klicken, werden Sie zum Unzustellungsbericht **angezeigt.**

Standardmäßig wird die Aktivität für alle Fehlercodes angezeigt. Wenn Sie auf **"Daten anzeigen" klicken,** können Sie in der Dropdownliste einen bestimmten Fehlercode auswählen.

Wenn Sie an einem bestimmten Tag im Diagramm auf eine bestimmte Farbe (Fehlercode) zeigen, wird die Gesamtanzahl der Meldungen für den Fehler angezeigt.

![Berichtsansicht im Bericht "Nicht akzeptierte Domäne"](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>Detailtabelle für den Unzustellungsbericht

Wenn Sie in einer **Berichtsansicht auf "Details anzeigen"** klicken, werden die folgenden Informationen angezeigt:

- **Date**
- **Unzustellungsberichtscode**
- **Count**
- **Beispielmeldungen:** Die Nachrichten-IDs eines Beispiels betroffener Nachrichten.

Wenn Sie in einer **Detailtabelle auf** Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Klicken Sie auf "Herunterladen anfordern", um den Bericht für einen bestimmten Datumsbereich per E-Mail an einen oder mehrere Empfänger **zu senden.**

Wenn Sie eine Zeile in der Tabelle auswählen, wird ein Flyout mit den folgenden Informationen angezeigt:

- **Date**
- **Unzustellungsberichtscode:** Klicken Sie auf den Link, um weitere Informationen zu den Ursachen und Lösungen für den jeweiligen Fehlercode zu erhalten.
- **Count**
- **Beispielmeldungen:** Sie können auf "Beispielmeldungen **anzeigen"** klicken, um die Ergebnisse der Nachrichtenverfolgung für ein Beispiel der betroffenen Nachrichten zu sehen. [](message-trace-scc.md)

![Details flyout after selecting a row in Details table view in the Non-delivery report](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>Verwandte Themen

Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)
