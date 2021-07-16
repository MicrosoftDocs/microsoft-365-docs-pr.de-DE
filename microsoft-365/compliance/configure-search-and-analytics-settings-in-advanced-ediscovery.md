---
title: Konfigurieren von Such- und Analyseeinstellungen – Advanced eDiscovery
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
description: Konfigurieren Sie Advanced eDiscovery Einstellungen, die für alle Prüfdateigruppen in einem Fall gelten. Dies umfasst Einstellungen für Analysen und optische Zeichenerkennung.
ms.openlocfilehash: 2b9c438e28b8d9b84ec8cc29bf85911e5bdc3c8d
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453897"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>Konfigurieren von Such- und Analyseeinstellungen in Advanced eDiscovery

Sie können einstellungen für jeden Advanced eDiscovery Fall konfigurieren, um die folgenden Funktionen zu steuern.

- Erkennung von Quasiduplikaten und E-Mail-Threading

- Designs

- Automatisch generierte Prüfdateisatz-Abfrage

- Ignorieren von Text

- Optical Character Recognition (optische Zeichenerkennung)

So konfigurieren Sie die Such-und Analyseeinstellungen für einen Fall:

1. Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus.

2. Klicken Sie unter der Registerkarte **Einstellungen** unter **Suche und Analysen** auf **Auswählen**.

   Die Seite "Falleinstellungen" wird angezeigt. Diese Einstellungen werden in einem Fall auf alle Prüfdateisätze angewendet.

   ![Konfigurieren von Analyse- und Sucheinstellungen für einen Advanced eDiscovery Fall](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>Erkennung von Quasiduplikaten und E-Mail-Threading

In diesem Abschnitt können Sie Parameter für die Duplikaterkennung, die Erkennung von Quasiduplikaten und E-Mail-Threading festlegen. Weitere Informationen finden Sie unter ["Erkennung von Quasiduplikaten"](near-duplicate-detection-in-advanced-ediscovery.md) und ["E-Mail-Threading".](email-threading-in-advanced-ediscovery.md)

- **Fast Duplikate/E-Mail-Threading:** Wenn diese Option aktiviert ist, sind die Duplikaterkennung, die Erkennung von Quasiduplikaten und E-Mail-Threading Teil des Workflows, wenn Sie Analysen zu den Daten in einem Prüfdateisatz ausführen.

- **Schwellenwert für Dokument- und E-Mail-Ähnlichkeit:** Wenn die Ähnlichkeitsstufe für zwei Dokumente über dem Schwellenwert liegt, werden beide Dokumente in den gleichen nahezu doppelten Satz gesetzt.

- **Minimale/maximale Anzahl von Wörtern:** Diese Einstellungen geben an, dass nahezu duplizierte Und E-Mail-Threading-Analysen nur für Dokumente ausgeführt werden, die mindestens die mindeste Anzahl von Wörtern und höchstens die maximale Anzahl von Wörtern enthalten.

## <a name="themes"></a>Designs

In diesem Abschnitt können Sie Parameter für Designs festlegen. Weitere Informationen finden Sie unter [Designs](themes-in-advanced-ediscovery.md).

- **Designs:** Wenn das Design aktiviert ist, wird das Clustering von Designs als Teil des Workflows ausgeführt, wenn Sie Analysen für die Daten in einem Prüfdateisatz ausführen.

- **Maximale Anzahl von Designs:** Gibt die maximale Anzahl von Designs an, die generiert werden können, wenn Sie Analysen zu den Daten in einem Prüfdateisatz ausführen.

- **Zahlen in Designs einschließen:** Wenn sie aktiviert ist, werden Zahlen (die ein Design identifizieren) beim Generieren von Designs einbezogen. 

- **Passen Sie die maximale Anzahl von Designs dynamisch an:** In bestimmten Situationen sind möglicherweise nicht genügend Dokumente in einem Prüfdateisatz vorhanden, um die gewünschte Anzahl von Designs zu erzeugen. Wenn diese Einstellung aktiviert ist, passt Advanced eDiscovery die maximale Anzahl von Designs dynamisch an, anstatt zu versuchen, die maximale Anzahl von Designs zu erzwingen.

## <a name="review-set-query"></a>Prüfdateisatz-Abfrage

Wenn Sie nach der Analyse das Kontrollkästchen **"Automatisches Erstellen einer gespeicherten Suche zur Überprüfung erstellen"** aktivieren, Advanced eDiscovery die Abfrage des Prüfdateisatzes mit dem Namen **"For Review"** automatisch generiert. 

![Die automatisch generierte Abfrage "For Review"](../media/AeDForReviewQuery.png)

Diese Abfrage filtert im Wesentlichen doppelte Elemente aus dem Prüfdateisatz heraus. Auf diese Weise können Sie die eindeutigen Elemente im Prüfdateisatz überprüfen. Diese Abfrage wird nur erstellt, wenn Sie einen Prüfdateisatz innerhalb des Falls einer Analyse unterziehen. Weitere Informationen zu Überprüfungssatzabfragen finden Sie unter [Abfragen der Daten in einem Prüfdateisatz.](review-set-search.md)

## <a name="ignore-text"></a>Ignorieren von Text

Es gibt Situationen, in denen bestimmte Texte die Qualität der Analysen beeinträchtigen, z. B. lange Haftungsausschlüsse, die E-Mail-Nachrichten hinzugefügt werden, unabhängig vom Inhalt der E-Mail. Wenn Sie wollen, dass bestimmte Textzeichenfolgen ignoriert werden soll, können Sie diese aus der Analyse ausschließen, indem Sie die Textzeichenfolgen und die Analysefunktionen (Erkennung von Quasiduplikaten, E-Mail-Threading, Designs und Relevanz) angeben, für die der Text ausgeschlossen werden soll. Die Verwendung regulärer Ausdrücke (RegEx) als ignorierter Text wird ebenfalls unterstützt.

## <a name="optical-character-recognition-ocr"></a>Optical Character Recognition (OCR; optische Zeichenerkennung)

Wenn diese Einstellung aktiviert ist, wird die OCR-Verarbeitung für Bilddateien ausgeführt. Die OCR-Verarbeitung wird in den folgenden Situationen ausgeführt:

- Wenn Verwahrer und [nicht verwahrte Datenquellen](non-custodial-data-sources.md) zu einem Fall hinzugefügt werden. Wenn OCR auf Bilddateien angewendet wird, kann der Text in diesen Dateien während einer Sammlung durchsucht werden. Die OCR-Verarbeitung wird während des [erweiterten Indizierungsprozesses](indexing-custodian-data.md) ausgeführt. OCR wird nur für Elemente ausgeführt, die während der erweiterten Indizierung verarbeitet werden. Wenn beispielsweise eine große PDF-Datei, die teilweise indiziert ist oder andere Indizierungsfehler aufweist, während der erweiterten Indizierung verarbeitet wird, wird auch OCR auf die Datei angewendet. Anders ausgedrückt erfolgt die OCR-Verarbeitung nur für Dateien, die während des erweiterten Indizierungsprozesses neu indiziert werden. Dies bedeutet, dass es Situationen geben kann, in denen einem Fall Verwahrer hinzugefügt werden, einige E-Mail-Anlagen jedoch nicht für OCR verarbeitet werden, da diese Dateien während der erweiterten Indizierung nicht verarbeitet werden.

- Wenn Inhalte aus anderen Datenquellen (die keinem Verwahrer zugeordnet sind und dem Fall in einer Nicht-Verwahrer-Datenquelle hinzugefügt werden) einem Prüfdateisatz hinzugefügt werden.

Nachdem Daten zu einem Prüfdateisatz hinzugefügt wurden, kann Bildtext überprüft, durchsucht, markiert und analysiert werden. Sie können den extrahierten Text in der Textanzeige der ausgewählten Bilddatei im Prüfdateisatz anzeigen. Weitere Informationen finden Sie unter:

- [Erweiterte Indizierung der Daten von Verwaltungsberechtigten](indexing-custodian-data.md)

- [Hinzufügen von Suchergebnissen zu einem Prüfdateisatz](add-data-to-review-set.md#optical-character-recognition)

- [Unterstützte Bilddateitypen](supported-filetypes-ediscovery20.md#image)
