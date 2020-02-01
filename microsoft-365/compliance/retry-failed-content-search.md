---
title: Wiederholen einer Inhaltssuche zum Beheben eines Inhaltsspeicher Fehlers
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Verwenden Sie die Schaltfläche Wiederholen zum Auflösen von Inhalts suchen mit fehlerhaften Inhaltsverzeichnissen.
ms.openlocfilehash: ce88749a887fea57e977e210de1eda40268cb832
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601622"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>Wiederholen einer Inhaltssuche zum Beheben eines Inhaltsspeicher Fehlers

Wenn Sie die Inhaltssuche im Security and Compliance Center verwenden, um eine große Anzahl von Postfächern zu durchsuchen, erhalten Sie möglicherweise ähnliche Suchfehler wie die folgenden:

```text
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

Diese Fehler (mit Fehlercodes von CS001-002, CS003-002, CS008-009, CS012-002 und anderen Fehlern im Format CS0XX-0xx) deuten darauf hin, dass die Inhaltssuche keine bestimmten inhaltsspeicherorte durchsucht; in diesem Beispiel wurden zwei Postfächer nicht durchsucht. Diese Fehler werden auf der Dropdown Seite Statusdetails der Inhaltssuche angezeigt.

## <a name="cause-of-content-location-errors"></a>Ursache für Fehler bei Inhaltsverzeichnissen

Beim Durchsuchen einer großen Anzahl von Postfächern wird die Suche auf Tausende von Servern in einem Microsoft-Rechenzentrum verteilt. Zu einem bestimmten Zeitpunkt können bestimmte Server im Neustart Zustand sein oder bei einem Failover auf redundante Kopien. In beiden Fällen wird die Anforderung der Inhaltssuche zum Abrufen von Daten Timeout. Im vorherigen Beispiel waren die Fehler für die Postfächer, bei denen ein Fehler aufgetreten ist, das Ergebnis der Such Zeitüberschreitung.

## <a name="resolving-content-location-errors"></a>Beheben von Inhaltsspeicherort Fehlern

Das Neustarten der Suche führt häufig zu ähnlichen Fehlern auf unterschiedlichen Servern. Anstatt die Suche neu zu starten, klicken Sie auf die Schaltfläche wieder **holen** , die oben auf der Suchergebnisseite angezeigt wird.

![Klicken Sie auf die Schaltfläche wiederholen, um Fehler des Inhaltsspeichers zu beheben](media/retrycontentsearch3.png)

Dies führt dazu, dass die Suche nur für die nicht erfolgreichen Postfächer erneut versucht wird. Wenn Sie die Suche wiederholen, werden die anderen Ergebnisse, die erfolgreich zurückgegeben wurden, beibehalten.

## <a name="tips-to-avoid-content-location-errors"></a>Tipps zum Vermeiden von Inhaltsspeicherort Fehlern

Im folgenden finden Sie einige Ursachen für Fehler bei der Inhalts Lokalisierung und einige Tipps, die Ihnen beim Durchsuchen einer großen Anzahl von Postfächern helfen sollen, dies zu vermeiden.

- Das durchsuchte Postfach ist aufgrund von Benutzeraktivitäten möglicherweise ausgelastet. In diesem Fall kann sich der Suchdienst selbst Drosseln, um zu verhindern, dass das Postfach nicht mehr verfügbar ist. Um dies zu vermeiden, versuchen Sie, Suchvorgänge außerhalb der Geschäftszeiten auszuführen.

- Die Suchabfrage Ruft möglicherweise zu viel Inhalt aus dem Postfach ab. Versuchen Sie nach Möglichkeit, den Suchbereich mithilfe von Schlüsselwörtern, Datumsbereichen und Suchbedingungen einzuschränken.

- Zu viele Stichwörter oder Keyword-Phrasen beim Erstellen einer Suchabfrage mithilfe der [Liste Stichwörter](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches). Wenn Sie eine Suchabfrage ausführen, die die Liste Stichwörter verwendet, führt der Dienst im Wesentlichen eine separate Suche für jede Zeile in der Stichwortliste aus, sodass Statistiken generiert werden können. Wenn Sie die Liste Stichwörter in Suchabfragen verwenden, minimieren Sie die Anzahl der Zeilen in der Stichwortliste, oder Teilen Sie die Zahlen Schlüsselwörter in kleinere Listen auf, und erstellen Sie eine andere Suche für jede Stichwortliste.

  > [!NOTE]
  > Um Probleme aufgrund großer Stichwortlisten zu verringern, sind Sie jetzt auf maximal 20 Zeilen in der Stichwortliste einer Suchabfrage eingeschränkt.

- Zu viele Suchvorgänge werden gleichzeitig für dasselbe Postfach ausgeführt. Versuchen Sie nach Möglichkeit, eine Suche auf einem Postfach gleichzeitig auszuführen.

- Durchsuchen zu vieler Postfächer in einer einzigen Suche. Die Wahrscheinlichkeit von Inhaltsspeicherort Fehlern steigt beim Durchsuchen einer sehr großen Anzahl von Postfächern. Versuchen Sie nach Möglichkeit, mehrere Suchvorgänge auszuführen, damit jede Suche eine Teilmenge von Postfächern in Ihrer Organisation enthält.

- Die erforderliche Wartung wird für das Postfach ausgeführt. Obwohl diese Ursache wahrscheinlich selten auftritt, warten Sie eine Weile, nachdem Sie den Inhaltsspeicherort Fehler erhalten haben, und wiederholen Sie die Suche.
