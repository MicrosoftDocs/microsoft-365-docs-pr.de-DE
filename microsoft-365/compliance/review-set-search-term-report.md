---
title: Generieren eines Suchausdrucks Berichts für eine Überprüfungsgruppe
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: bb65745f92d1f77e6cc3224832c0a9871e567ca5
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558472"
---
# <a name="generate-search-term-report-for-a-review-set"></a>Generieren eines Suchausdrucks Berichts für eine Überprüfungsgruppe

In eDiscovery ist eine der am häufigsten verwendeten Bedingungen für das Abfragen von Dokumenten die Verwendung von Stichwort Suchbegriffen. Durch die Identifizierung von Dokumenten, die die spezifischen Stichwörter (auch *Begriffe*genannt) enthalten, die für einen Fall wichtig sind, können Bearbeiter damit beginnen, eine allgemeine Vorstellung davon zu erhalten, was Ihnen zusteht. In Advanced eDiscovery in Microsoft 365 können Sie genau dies tun, indem Sie Suchbegriffs Berichte zu gespeicherten Abfragen innerhalb eines Überprüfungs Satzes generieren.

## <a name="step-1-create-a-saved-query-in-the-review-set"></a>Schritt 1: Erstellen einer gespeicherten Abfrage in der Überprüfungsgruppe

Erstellen Sie zum Generieren eines aussagekräftigen Suchausdrucks Berichts eine gespeicherte Abfrage, die die Gruppe von Dokumenten in der Überprüfungsgruppe definiert, für die Sie einen Suchausdrucks Bericht generieren möchten. Sie können beispielsweise einen Datumsbereich oder die tatsächlichen Suchbegriffe (mithilfe der Bedingungsliste für Stichwörter) verwenden, um die Abfrage zu erstellen. Weitere Informationen zum Überprüfen von Mengen Abfragen finden Sie unter [Abfragen der Daten in einem Überprüfungs Satzes](review-set-search.md).

## <a name="step-2-generate-a-search-term-report"></a>Schritt 2: Generieren eines Suchausdrucks Berichts

Es gibt zwei verschiedene Methoden zum Generieren eines Suchausdrucks Berichts: über das Kontextmenü der gespeicherten Abfrage, die Sie in Schritt 1 erstellt haben, oder über die Suchbegriffs Berichts-Verwaltungskonsole.

- Um das Kontextmenü zu verwenden, öffnen Sie das Kontextmenü der gespeicherten Abfrage, die Sie in Schritt 1 erstellt haben, und klicken Sie auf **Suchausdrucks Bericht generieren**.

- Um die Verwaltungskonsole zu verwenden, wechseln Sie zu **Manage Review Sets #a0 anzeigen von Suchbegriffs Berichten**, klicken Sie auf **neu**, und wählen Sie dann die gespeicherte Abfrage aus, die Sie in Schritt 1 erstellt haben.

Geben Sie dann die Begriffe ein, über die Sie berichten möchten, getrennt durch NewLine; Wenn die gespeicherte Abfrage, die Sie in Schritt 1 verwendeter Stichwort-Konditions Karte erstellt haben, wird die Flyout-Seite vorab mit den Begriffen aus der ersten Keyword-Bedingungs Karte aufgefüllt, die in der gespeicherten Abfrage verwendet wird.

Wählen Sie dann bis zu drei Pivots für die Berichterstellung aus, und klicken Sie auf **generieren**, um den Auftrag zum Generieren von Suchbegriffs Berichten zu starten.

### <a name="what-is-a-pivot"></a>Was ist ein Pivot?

Pivots ist die Art und Weise, wie der Bericht organisiert wird. Sehen Sie sich das folgende Beispiel an:

- Die gespeicherte Abfrage ruft 10 Dokumente ab: DOC1 bis doc10.

- DOC1, Dokument2, doc3, doc4, doc5, doc6 und DOC7 enthalten den Begriff "eDiscovery".

- doc6, DOC7, doc8, doc9 und doc10 enthalten den Begriff "Untersuchung".

- DOC1, doc3, doc5, DOC7, doc9 sind aus Depotbank A.

- Dokument2, doc4, doc6, doc8, doc10 sind aus Depotbank B.

Wenn Sie in diesem Fall einen Suchausdrucks Bericht zu den Begriffen "eDiscovery" und "Untersuchung" generieren und auf Depotbanken pivotieren, wäre der Suchbegriff Bericht wie folgt organisiert:

- "eDiscovery"-Depot A: 4 Dokumente

- "eDiscovery"-Verwalter B: 3 Dokumente

- "Untersuchung"-Depot A: 2 Dokumente

- "Untersuchung"-Verwalter B: 3 Dokumente

## <a name="step-3-download-report"></a>Schritt 3: Herunterladen des Berichts

In der Suchbegriffs-Verwaltungskonsole können Sie den Status eines zuvor erstellten Berichtsauftrags für den Suchbegriff nachverfolgen. Sobald der Auftrag abgeschlossen ist, können Sie auf die Zeile für den Suchbegriff Bericht klicken und auf "herunterladen" klicken, um den Suchbegriff Bericht in einem CSV-Format herunterzuladen. Es wird eine Zeile pro (Suchbegriff, Pivots) Tupel geben, und jede Zeile enthält die folgenden Informationen:

- Wie viele Dokumente wurden abgerufen?

- Wie oft wurde der Suchbegriff in den Dokumenten gefunden?

- Was ist das Gesamtvolumen der abgerufenen Dokumente?

- Wie viele Familien wurden abgerufen?

- Was ist die Gesamtanzahl von Dokumenten dieser Familien, einschließlich der Dokumente, die nicht den Suchbegriff hatten?

- Was ist das Gesamtvolumen der oben genannten?