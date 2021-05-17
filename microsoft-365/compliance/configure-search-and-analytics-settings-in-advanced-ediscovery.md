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
description: Konfigurieren Advanced eDiscovery einstellungen, die für alle Überprüfungssatz in einem Fall gelten. Dies umfasst Einstellungen für die Analyse und optische Zeichenerkennung.
ms.openlocfilehash: 11932d2172d797ae1913cf28e713d57805ace122
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751302"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>Konfigurieren von Such- und Analyseeinstellungen in Advanced eDiscovery

Sie können Einstellungen für jeden Advanced eDiscovery konfigurieren, um die folgenden Funktionen zu steuern.

- Erkennung von Quasiduplikaten und E-Mail-Threading

- Designs

- Automatisch generierte Prüfdateisatz-Abfrage

- Ignorieren von Text

- Optical Character Recognition (optische Zeichenerkennung)

So konfigurieren Sie die Such-und Analyseeinstellungen für einen Fall:

1. Wählen Sie auf der Seite **Advanced eDiscovery** den Fall aus.

2. Klicken Sie unter der Registerkarte **Einstellungen** unter **Suche und Analysen** auf **Auswählen**.

   Die Seite "Falleinstellungen" wird angezeigt. Diese Einstellungen werden in einem Fall auf alle Überprüfungssätze angewendet.

   ![Konfigurieren von Analyse- und Sucheinstellungen für einen Advanced eDiscovery Fall](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>Erkennung von Quasiduplikaten und E-Mail-Threading

In diesem Abschnitt können Sie Parameter für die Duplikaterkennung, die Beinaheerkennung von Duplikaten und das E-Mail-Threading festlegen. Weitere Informationen finden Sie unter [Near duplicate detection](near-duplicate-detection-in-advanced-ediscovery.md) and Email [threading](email-threading-in-advanced-ediscovery.md).

- **In der Nähe von Duplikaten/E-Mail-Threading:** Wenn dies aktiviert ist, werden die Duplikaterkennung, die Erkennung von Duplikaten und das E-Mail-Threading als Teil des Workflows einbezogen, wenn Sie Analysen für die Daten in einem Überprüfungssatz ausführen.

- **Schwellenwert für dokument- und E-Mail-Ähnlichkeit:** Wenn die Ähnlichkeitsstufe für zwei Dokumente über dem Schwellenwert liegt, werden beide Dokumente in demselben fast doppelten Satz gesetzt.

- **Minimale/maximale Anzahl von Wörtern:** Diese Einstellungen geben an, dass beinahe duplikate und E-Mail-Threading-Analyse nur für Dokumente ausgeführt werden, die mindestens die minimale Anzahl von Wörtern und höchstens die maximale Anzahl von Wörtern haben.

## <a name="themes"></a>Designs

In diesem Abschnitt können Sie Parameter für Designs festlegen. Weitere Informationen finden Sie unter [Designs](themes-in-advanced-ediscovery.md).

- **Designs:** Wenn dies aktiviert ist, wird das Clustering von Designs als Teil des Workflows ausgeführt, wenn Sie Analysen für die Daten in einem Überprüfungssatz ausführen.

- **Maximale Anzahl von Designs:** Gibt die maximale Anzahl von Designs an, die generiert werden können, wenn Sie Analysen für die Daten in einem Überprüfungssatz ausführen.

- **Fügen Sie Zahlen in Designs ein:** Wenn dies aktiviert ist, werden Zahlen (die ein Design identifizieren) beim Generieren von Designs eingeschlossen. 

- **Passen Sie die maximale Anzahl von Designs dynamisch an:** In bestimmten Situationen sind möglicherweise nicht genügend Dokumente in einem Überprüfungssatz enthalten, um die gewünschte Anzahl von Designs zu erzeugen. Wenn diese Einstellung aktiviert ist, passt Advanced eDiscovery die maximale Anzahl von Designs dynamisch an, anstatt zu versuchen, die maximale Anzahl von Designs zu erzwingen.

## <a name="review-set-query"></a>Prüfdateisatz-Abfrage

Wenn Sie das Kontrollkästchen Gespeicherte **Suche** nach Analyse automatisch erstellen aktivieren, Advanced eDiscovery überprüfungssatzabfrage namens **For Review automatisch generiert.** 

![Die automatisch generierte For Review-Abfrage](../media/AeDForReviewQuery.png)

Diese Abfrage filtert im Wesentlichen doppelte Elemente aus dem Überprüfungssatz heraus. Auf diese Weise können Sie die eindeutigen Elemente im Überprüfungssatz überprüfen. Diese Abfrage wird nur erstellt, wenn Sie einen Prüfdateisatz innerhalb des Falls einer Analyse unterziehen. Weitere Informationen zu Überprüfungssatzabfragen finden Sie unter [Query the data in a review set](review-set-search.md).

## <a name="ignore-text"></a>Ignorieren von Text

Es gibt Situationen, in denen bestimmten Text die Qualität der Analyse verringert, z. B. langwierige Haftungsausschlüsse, die E-Mail-Nachrichten unabhängig vom Inhalt der E-Mail hinzugefügt werden. Wenn Sie wollen, dass bestimmte Textzeichenfolgen ignoriert werden soll, können Sie diese aus der Analyse ausschließen, indem Sie die Textzeichenfolgen und die Analysefunktionen (Erkennung von Quasiduplikaten, E-Mail-Threading, Designs und Relevanz) angeben, für die der Text ausgeschlossen werden soll. Die Verwendung regulärer Ausdrücke (RegEx) als ignorierter Text wird ebenfalls unterstützt. 

## <a name="optical-character-recognition-ocr"></a>Optical Character Recognition (OCR; optische Zeichenerkennung)

Wenn diese Einstellung aktiviert ist, wird die OCR-Verarbeitung für Bilddateien ausgeführt. Die OCR-Verarbeitung wird in den folgenden Situationen ausgeführt:

- Wenn verwahrer und nicht [verwahrte Datenquellen](non-custodial-data-sources.md) zu einem Fall hinzugefügt werden. Die OCR-Verarbeitung wird während des erweiterten Indizierungsprozesses ausgeführt. Dies bedeutet, dass Text in Bilddateien, die den Suchkriterien entsprechen, in einer Auflistungssuche zurückgegeben wird.

- Wenn Inhalte aus anderen Datenquellen (die keinem Verwahrer zugeordnet sind und dem Fall in einer nicht verwahrten Datenquelle hinzugefügt werden) einem Überprüfungssatz hinzugefügt werden.

Nachdem Einem Überprüfungssatz Daten hinzugefügt wurden, kann der Bildtext überprüft, durchsucht, markiert und analysiert werden. Sie können den extrahierten Text in der Textanzeige der ausgewählten Bilddatei im Überprüfungssatz anzeigen. Weitere Informationen finden Sie unter:

- [Erweiterte Indizierung der Daten von Verwaltungsberechtigten](indexing-custodian-data.md)

- [Hinzufügen von Suchergebnissen zu einem Prüfdateisatz](add-data-to-review-set.md#optical-character-recognition)

- [Unterstützte Bilddateitypen](supported-filetypes-ediscovery20.md#image)
