---
title: Wiederholen einer Inhaltssuche zum Beheben eines Inhaltsspeicherortfehlers
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
description: Während einer Untersuchung können Sie die Schaltfläche Wiederholen verwenden, um Inhaltssuchen mit Fehlern beim Speicherort von Inhalten zu beheben.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb85a882ef111aa38a73dbe155a9ad0ef57dd3de
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311820"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>Wiederholen einer Inhaltssuche zum Beheben eines Inhaltsspeicherortfehlers

Wenn Sie die Inhaltssuche im Security and Compliance Center zum Durchsuchen einer großen Anzahl von Postfächern verwenden, werden möglicherweise Suchfehler angezeigt, die dem Fehler ähneln:

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

Diese Fehler (mit Fehlercodes von CS001-002, CS003-002, CS008-009, CS012-002 und anderen Fehlern des Formulars CS0XX-0XX) deuten darauf hin, dass die Inhaltssuche bestimmte Inhaltsorte nicht durchsucht hat. In diesem Beispiel wurden zwei Postfächer nicht durchsucht. Diese Fehler werden auf der Flyoutseite für Statusdetails der Inhaltssuche angezeigt.

## <a name="cause-of-content-location-errors"></a>Ursache von Fehlern beim Speicherort von Inhalten

Beim Durchsuchen einer großen Anzahl von Postfächern wird die Suche auf Tausende von Servern in einem Microsoft-Rechenzentrum verteilt. Zu einem beliebigen Zeitpunkt könnten sich bestimmte Server im Neustartzustand befinden oder einen Fehler bei redundanten Kopien durchführen. In einem dieser Fälle ist die Anforderung der Inhaltssuche zum Abrufen von Daten zu einem Zeitergebnis. Im vorherigen Beispiel waren die Fehler für die fehlgeschlagenen Postfächer das Ergebnis des Timeouts der Suche.

## <a name="resolving-content-location-errors"></a>Beheben von Fehlern beim Speicherort von Inhalten

Ein Neustart der Suche führt häufig zu ähnlichen Fehlern auf verschiedenen Servern. Klicken Sie anstatt die Suche neu zu starten, klicken Sie auf die Schaltfläche **Wiederholen,** die oben auf der Suchergebnissetseite angezeigt wird.

![Klicken Sie auf die Schaltfläche Wiederholen, um Fehler beim Speicherort von Inhalten zu beheben.](../media/retrycontentsearch3.png)

Dies führt dazu, dass die Suche nur nach den fehlgeschlagenen Postfächern erneutversucht wird. Wenn Sie die Suche wiederholen, werden die anderen Ergebnisse, die erfolgreich zurückgegeben wurden, beibehalten.

## <a name="tips-to-avoid-content-location-errors"></a>Tipps, um Fehler beim Speicherort von Inhalten zu vermeiden

Im Folgenden finden Sie einige zusätzliche Ursachen für Fehler beim Speicherort von Inhalten und einige Tipps, die Sie beim Durchsuchen einer großen Anzahl von Postfächern vermeiden können.

- Das durchsuchte Postfach ist möglicherweise aufgrund von Benutzeraktivitäten ausgelastet. In diesem Fall kann der Suchdienst sich selbst drosseln, um zu verhindern, dass das Postfach nicht verfügbar wird. Um dies zu vermeiden, versuchen Sie, Suchbegriffe außerhalb der Geschäftszeiten zu führen.

- Die Suchabfrage ruft möglicherweise zu viel Inhalt aus dem Postfach ab. Versuchen Sie nach Möglichkeit, den Suchbereich mithilfe von Schlüsselwörtern, Datumsbereichen und Suchbedingungen zu einenten.

- Zu viele Schlüsselwörter oder Stichwortausdrücke, wenn Sie eine Suchabfrage mithilfe der [Stichwörterliste erstellen.](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches) Wenn Sie eine Suchabfrage ausführen, die die Stichwörterliste verwendet, führt der Dienst im Wesentlichen eine separate Suche für jede Zeile in der Stichwortliste aus, sodass Statistiken generiert werden können. Wenn Sie die Stichwörterliste in Suchabfragen verwenden, minimieren Sie die Anzahl der Zeilen in der Stichwortliste, oder teilen Sie die Stichwörter in kleinere Listen auf, und erstellen Sie eine andere Suche für jede Stichwortliste.

  > [!NOTE]
  > Um Probleme zu reduzieren, die durch große Stichwortlisten verursacht werden, sind Sie jetzt auf maximal 20 Zeilen in der Stichwortliste einer Suchabfrage beschränkt.

- Es werden zu viele Suchdurchsuchungen für dasselbe Postfach gleichzeitig ausgeführt. Versuchen Sie nach Möglichkeit, eine Suche für jedes Postfach gleichzeitig ausführen.

- Zu viele Postfächer in einer einzigen Suche durchsuchen. Die Wahrscheinlichkeit von Fehlern beim Speicherort von Inhalten steigt beim Durchsuchen einer großen Anzahl von Postfächern. Versuchen Sie nach Möglichkeit, mehrere Suchen ausführen, sodass jede Suche eine Teilmenge von Postfächern in Ihrer Organisation enthält.

- Die erforderliche Wartung wird für das Postfach ausgeführt. Obwohl diese Ursache wahrscheinlich selten auftritt, warten Sie ein wenig, nachdem Sie den Fehler zum Speicherort des Inhalts erhalten haben, und wiederholen Sie dann die Suche.
