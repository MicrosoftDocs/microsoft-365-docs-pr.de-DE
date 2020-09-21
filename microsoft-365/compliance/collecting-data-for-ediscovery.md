---
title: Sammeln von Daten für einen Fall in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In diesem Artikel erfahren Sie, wie Sie eine Dokumentenmappe zur Überprüfung in einer Untersuchung mithilfe des Such Tools in Advanced eDiscovery identifizieren.
ms.custom: seo-marvel-2020
ms.openlocfilehash: 725c289324a8e4d5bd4d7a7b9ddd9e091b6d6241
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956198"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>Sammeln von Daten für einen Fall in Advanced eDiscovery

Nachdem Sie Verwalter und Datenquellen identifiziert haben, die für Ihren Fall von Interesse sind, müssen Sie die Dokumente identifizieren, in die Sie eintauchen möchten. Sie können das Such Tool in Advanced eDiscovery verwenden, um relevante Dokumente aus Freiheits-und nicht-Freiheits Speicherorten in Microsoft 365 zu identifizieren.

Nachdem Sie eine Suche ausgeführt haben, können Sie Statistiken zu den abgerufenen Elementen anzeigen, beispielsweise die Speicherorte mit den meisten Elementen, die mit der Suchabfrage übereinstimmen. Sie können auch eine Vorschau einer Teilmenge der Ergebnisse anzeigen. Wenn Sie die Gruppe von Dokumenten identifiziert haben, die Sie weiter untersuchen möchten, können Sie die Suchergebnisse zu einem Überprüfungs Sätze hinzufügen, um Sie zu sammeln und zu verarbeiten.

## <a name="create-a-search"></a>Erstellen einer Suche

Wenn Sie auf der Registerkarte **Suchen** die Option **neue Suche** auswählen, wird ein Assistent gestartet, der Sie durch das Erstellen einer Suche führt. Ausführliche Informationen zum Erstellen einer Suche finden Sie unter [Erstellen einer Suche zum Erfassen von Daten](create-search-to-collect-data.md).

Nachdem eine Suche erstellt wurde, wird eine Flyout-Seite mit Details angezeigt. Die Schaltflächen **Statistik** und **Vorschau** sind anfänglich nicht verfügbar, da die Suche noch nicht abgeschlossen wurde. Sie können den Fortschritt der Suche auf der Registerkarte **Suchen** verfolgen.

## <a name="view-search-results-and-statistics"></a>Anzeigen von Suchergebnissen und Statistiken

Es gibt zwei Komponenten einer Inhaltssuche: Statistik (Schätzungen) und Vorschau. Nachdem jede dieser Komponenten abgeschlossen ist, wird der Status angezeigt, der in den entsprechenden Spalten auf der Registerkarte **Suchvorgänge** von über **mittelte** in **in Bearbeitung** geändert in **abgeschlossen**angezeigt wird.

Wenn die Such Schätzung abgeschlossen ist, wählen Sie die Suche aus, um die Flyout-Seite anzuzeigen, in der einige allgemeine Statistiken zu den Ergebnissen der Suche angezeigt werden. Zu diesem Zeitpunkt ist die Schaltfläche **Statistik** aktiv. Sie können ihn auswählen, um Suchstatistiken anzuzeigen, beispielsweise:

- Zusammenfassung
- Top-Standorte
- Abfragen

Weitere Informationen zu Suchstatistiken finden Sie unter [Suchstatistiken](search-statistics.md).

Sobald die Vorschau abgeschlossen ist, wird die Schaltfläche **Vorschau** aktiv. Wählen Sie diese Option aus, um eine ausgewählte Teilmenge der Ergebnisse in der Vorschau anzuzeigen.

## <a name="add-search-results-to-a-review-set"></a>Hinzufügen von Suchergebnissen zu einem Prüfdateisatz

Wenn Sie bereit sind, die gesamten Ergebnisse einer Suche zu sammeln und zu verarbeiten, können Sie dies tun, indem Sie es zu einem Überprüfungs Satzes hinzufügen. Ausführliche Informationen finden Sie unter [Hinzufügen von Daten zu einem Überprüfungs Sätze](add-data-to-review-set.md).

## <a name="add-non-microsoft-365-data-to-a-review-set"></a>Hinzufügen von nicht-Microsoft 365-Daten zu einem Überprüfungs Satzes

Im Rahmen des Sammlungsprozesses für einen Fall können Sie auch nicht Office 365 Daten zu einer Überprüfungsgruppe hinzufügen und überprüfen und zusammen mit den Office 365 Daten analysieren, die Sie mithilfe des Such Tools gesammelt haben. Wenn Sie nicht-Office 365 hinzufügen, müssen Sie ihn einer bestimmten Depotbank in dem Fall zuordnen. Weitere Informationen finden Sie unter [Laden von nicht-Microsoft 365-Daten in einen Überprüfungs Satzes](load-non-Office-365-data-into-a-review-set.md).
