---
title: Wiederholen einer Inhaltssuche zum Beheben eines Inhaltsspeicher Fehlers
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Während einer Untersuchung können Sie die Schaltfläche Wiederholen verwenden, um Inhalts Suchvorgänge mit Inhaltsspeicherort Fehlern aufzulösen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b3aed9c1d2d1fe3c40adb64b4854ef359f931bcb
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357555"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>Wiederholen einer Inhaltssuche zum Beheben eines Inhaltsspeicher Fehlers

Wenn Sie die Inhaltssuche im Security and Compliance Center verwenden, um eine große Anzahl von Postfächern zu durchsuchen, erhalten Sie möglicherweise Suchfehler, die dem Fehler ähneln:

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

Diese Fehler (mit Fehlercodes von CS001-002, CS003-002, CS008-009, CS012-002 und anderen Fehlern im Format CS0XX-0xx) deuten darauf hin, dass die Inhaltssuche keine bestimmten inhaltsspeicherorte durchsucht; in diesem Beispiel wurden zwei Postfächer nicht durchsucht. Diese Fehler werden auf der Dropdown Seite Statusdetails der Inhaltssuche angezeigt.

## <a name="cause-of-content-location-errors"></a>Ursache für Fehler bei Inhaltsverzeichnissen

Beim Durchsuchen einer großen Anzahl von Postfächern wird die Suche auf Tausende von Servern in einem Microsoft-Rechenzentrum verteilt. Zu einem bestimmten Zeitpunkt können bestimmte Server im Neustart Zustand sein oder bei einem Failover auf redundante Kopien. In beiden Fällen wird bei der Anforderung der Inhaltssuche zum Abrufen von Daten ein Timeout auftritt. Im vorherigen Beispiel waren die Fehler für die Postfächer, bei denen ein Fehler aufgetreten ist, das Ergebnis der Such Zeitüberschreitung.

## <a name="resolving-content-location-errors"></a>Beheben von Inhaltsspeicherort Fehlern

Das Neustarten der Suche führt häufig zu ähnlichen Fehlern auf unterschiedlichen Servern. Anstatt die Suche neu zu starten, klicken Sie auf die Schaltfläche wieder **holen** , die oben auf der Suchergebnisseite angezeigt wird.

![Klicken Sie auf die Schaltfläche wiederholen, um Fehler des Inhaltsspeichers zu beheben](../media/retrycontentsearch3.png)

Dies führt dazu, dass die Suche nur für die nicht erfolgreichen Postfächer erneut versucht wird. Wenn Sie die Suche wiederholen, werden die anderen Ergebnisse, die erfolgreich zurückgegeben wurden, beibehalten.

## <a name="tips-to-avoid-content-location-errors"></a>Tipps zum Vermeiden von Inhaltsspeicherort Fehlern

Hier finden Sie einige zusätzliche Ursachen für Fehler bei der Inhalts Lokalisierung und einige Tipps, die Sie beim Durchsuchen einer großen Anzahl von Postfächern vermeiden können.

- Das durchsuchte Postfach ist aufgrund von Benutzeraktivitäten möglicherweise ausgelastet. In diesem Fall kann sich der Suchdienst selbst Drosseln, um zu verhindern, dass das Postfach nicht mehr verfügbar ist. Um dies zu vermeiden, versuchen Sie, Suchvorgänge außerhalb der Geschäftszeiten auszuführen.

- Die Suchabfrage Ruft möglicherweise zu viel Inhalt aus dem Postfach ab. Versuchen Sie nach Möglichkeit, den Suchbereich mithilfe von Schlüsselwörtern, Datumsbereichen und Suchbedingungen einzuschränken.

- Zu viele Stichwörter oder Keyword-Phrasen beim Erstellen einer Suchabfrage mithilfe der [Liste Stichwörter](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches). Wenn Sie eine Suchabfrage ausführen, die die Liste Stichwörter verwendet, führt der Dienst im Wesentlichen eine separate Suche für jede Zeile in der Stichwortliste aus, sodass Statistiken generiert werden können. Wenn Sie die Liste Stichwörter in Suchabfragen verwenden, minimieren Sie die Anzahl der Zeilen in der Stichwortliste, oder Teilen Sie die Zahlen Schlüsselwörter in kleinere Listen auf, und erstellen Sie eine andere Suche für jede Stichwortliste.

  > [!NOTE]
  > Um Probleme aufgrund großer Stichwortlisten zu verringern, sind Sie jetzt auf maximal 20 Zeilen in der Stichwortliste einer Suchabfrage eingeschränkt.

- Zu viele Suchvorgänge werden gleichzeitig für dasselbe Postfach ausgeführt. Versuchen Sie nach Möglichkeit, eine Suche auf einem Postfach gleichzeitig auszuführen.

- Durchsuchen zu vieler Postfächer in einer einzigen Suche. Die Wahrscheinlichkeit von Inhaltsspeicherort Fehlern steigt beim Durchsuchen einer großen Anzahl von Postfächern. Versuchen Sie nach Möglichkeit, mehrere Suchvorgänge auszuführen, damit jede Suche eine Teilmenge von Postfächern in Ihrer Organisation enthält.

- Die erforderliche Wartung wird für das Postfach ausgeführt. Obwohl diese Ursache wahrscheinlich selten auftritt, warten Sie eine Weile, nachdem Sie den Inhaltsspeicherort Fehler erhalten haben, und wiederholen Sie die Suche.
