---
title: Konfigurieren von Such-und Analyse Einstellungen – Advanced eDiscovery
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
ms.custom: seo-marvel-mar2020
description: Konfigurieren Sie erweiterte eDiscovery-Einstellungen, die für alle Überprüfungs Sätze in einem Fall gelten. Dies umfasst Einstellungen für die Analyse und die optische Zeichenerkennung.
ms.openlocfilehash: dfacab79f635a817b127614f524d00b0297981fb
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277083"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>Konfigurieren von Such-und Analyse Einstellungen in Advanced eDiscovery

Sie können Einstellungen für jeden erweiterten eDiscovery-Fall konfigurieren, um die folgenden Funktionen zu steuern.

- Erkennung von Quasiduplikaten und E-Mail-Threading

- Designs

- Automatisch generierte Prüfdateisatz-Abfrage

- Ignorieren von Text

- Optical Character Recognition (optische Zeichenerkennung)

So konfigurieren Sie die Such-und Analyseeinstellungen für einen Fall:

1. Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus.

2. Klicken Sie unter der Registerkarte **Einstellungen** unter **Suche und Analysen** auf **Auswählen**.

   Die Seite Fall Einstellungen wird angezeigt. Diese Einstellungen werden in einem Fall auf alle Überprüfungs Sätze angewendet.

   ![Konfigurieren von Analyse-und Sucheinstellungen für einen erweiterten eDiscovery-Fall](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>Erkennung von Quasiduplikaten und E-Mail-Threading

In diesem Abschnitt können Sie Parameter für die doppelte Erkennung, in der Nähe der doppelten Erkennung und beim e-Mail-Threading festlegen. Weitere Informationen finden Sie [in der Nähe der doppelten Erkennung](near-duplicates.md) und des [e-Mail-Threadings](email-threading.md).

- **In der Nähe von Duplikaten/e-Mail-Threading:** Wenn die Analyse für die Daten in einem Überprüfungs Satzes ausgeführt wird, werden die doppelte Erkennung, die Erkennung in der Nähe von Duplikaten und das e-Mail-Threading als Teil des Workflows einbezogen.

- **Schwellenwert für die Dokument-und e-Mail-Ähnlichkeit:** Wenn sich die Ähnlichkeits Ebene für zwei Dokumente über dem Schwellenwert befindet, werden beide Dokumente in derselben nahe doppelten Gruppe platziert.

- **Minimale/maximale Anzahl von Wörtern:** Mit diesen Einstellungen wird angegeben, dass nahe Duplikate und die e-Mail-Thread Analyse nur für Dokumente ausgeführt werden, die mindestens die minimale Anzahl von Wörtern und höchstens die maximale Anzahl von Wörtern aufweisen.

## <a name="themes"></a>Designs

In diesem Abschnitt können Sie Parameter für Designs festlegen. Weitere Informationen finden Sie unter [Designs](themes-in-advanced-ediscovery.md).

- **Designs:** Wenn Sie aktiviert ist, wird das Thema Clustering als Teil des Workflows ausgeführt, wenn Sie Analysen für die Daten in einem Überprüfungs Satzes ausführen.

- **Maximale Anzahl von Designs:** Gibt die maximale Anzahl von Designs an, die beim Ausführen von Analytics für die Daten in einem Überprüfungs Satz generiert werden können.

- **Zahlen in Designs einbeziehen:** Wenn diese Option aktiviert ist, werden beim Generieren von Designs Zahlen (zur Identifizierung eines Designs) einbezogen. 

- **Anpassen der maximalen Anzahl von Designs dynamisch:** In bestimmten Situationen kann es in einem Überprüfungs möglicherweise nicht genügend Dokumente geben, um die gewünschte Anzahl von Designs zu erstellen. Wenn diese Einstellung aktiviert ist, passt Advanced eDiscovery die maximale Anzahl von Designs dynamisch an, anstatt zu versuchen, die maximale Anzahl von Designs zu erzwingen.

## <a name="review-set-query"></a>Prüfdateisatz-Abfrage

Wenn Sie das Kontrollkästchen **für Überprüfung gespeicherte Suche nach Analyse automatisch erstellen** aktivieren, wird Advanced eDiscovery autogenet Review Sets Query benannt **zur Überprüfung.** 

![Die automatisch generierte Abfrage zur Überprüfung](../media/AeDForReviewQuery.png)

Diese Abfrage filtert im wesentlichen doppelte Elemente aus dem Überprüfungs Satzes. Auf diese Weise können Sie die eindeutigen Elemente in der Überprüfungsgruppe überprüfen. Diese Abfrage wird nur erstellt, wenn Sie einen Prüfdateisatz innerhalb des Falls einer Analyse unterziehen. Weitere Informationen zum Überprüfen von Mengen Abfragen finden Sie unter [Abfragen der Daten in einem Überprüfungs Satzes](review-set-search.md).

## <a name="ignore-text"></a>Ignorieren von Text

Es gibt Situationen, in denen ein bestimmter Text die Qualität der Analyse verringert, beispielsweise langwierige Haftungsausschlüsse, die zu e-Mail-Nachrichten hinzugefügt werden, unabhängig vom Inhalt der e-Mail. Wenn Sie wollen, dass bestimmte Textzeichenfolgen ignoriert werden soll, können Sie diese aus der Analyse ausschließen, indem Sie die Textzeichenfolgen und die Analysefunktionen (Erkennung von Quasiduplikaten, E-Mail-Threading, Designs und Relevanz) angeben, für die der Text ausgeschlossen werden soll. Das Verwenden regulärer Ausdrücke (Regex) als ignorierter Text wird ebenfalls unterstützt. 

## <a name="optical-character-recognition-ocr"></a>Optical Character Recognition (OCR; optische Zeichenerkennung)

Wenn diese Einstellung aktiviert ist, wird die OCR-Verarbeitung für Bilddateien ausgeführt. Die OCR-Verarbeitung wird in den folgenden Situationen ausgeführt:

- Wenn Verwalter und [Datenquellen ohne Freiheitsentzug](non-custodial-data-sources.md) einem Fall hinzugefügt werden. Die OCR-Verarbeitung wird während des erweiterten Indizierungsprozesses ausgeführt. Dies bedeutet, dass Text in Bilddateien, der mit den Suchkriterien übereinstimmt, in einer Sammlungs Suche zurückgegeben wird.

- Wenn Inhalte aus anderen Datenquellen (die nicht einer Depotstelle zugeordnet sind und dem Fall in einer Datenquelle ohne Freiheitsentzug hinzugefügt werden) zu einem Überprüfungs Satzes hinzugefügt werden.

Nachdem dem Überprüfungs Satzes Daten hinzugefügt wurden, kann der Bildtext überprüft, durchsucht, markiert und analysiert werden. Sie können den extrahierten Text im Text Betrachter der ausgewählten Bilddatei im überprüfungsordner anzeigen. Weitere Informationen finden Sie unter:

- [Erweiterte Indizierung der Daten von Verwaltungsberechtigten](indexing-custodian-data.md)

- [Hinzufügen von Suchergebnissen zu einem Prüfdateisatz](add-data-to-review-set.md#optical-character-recognition)

- [Unterstützte Bilddateitypen](supported-filetypes-ediscovery20.md#image)
