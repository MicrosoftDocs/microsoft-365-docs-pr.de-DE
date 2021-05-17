---
title: CJK/Double Byte-Unterstützung für Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie Advanced eDiscovery in Microsoft 365 sprachen Chinesisch, Japanisch und Koreanisch (CJK) unterstützt, die einen Doppel-Byte-Zeichensatz verwenden.
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926601"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>CJK-Sprachunterstützung für Advanced eDiscovery

Advanced eDiscovery unterstützt Doppel-Byte-Zeichensatzsprachen (dazu gehören vereinfachtes Chinesisch, traditionelles Chinesisch, Japanisch und Koreanisch, die gemeinsam als *CJK-Sprachen* bekannt sind) für die folgenden erweiterten Szenarien in einem Überprüfungssatz:

- Wenn Sie [die Daten in einem Überprüfungssatz abfragen.](review-set-search.md)

- Wenn Sie [Dokumente in einem Überprüfungssatz kennzeichnen.](tagging-documents.md)

- Wenn Sie [Falldaten in einem Überprüfungssatz](analyzing-data-in-review-set.md) mithilfe der Fast-Duplikaterkennung, des E-Mail-Threadings und der Designsanalyse analysieren.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wie erstelle ich eine Suche zum Sammeln von Elementen, die #A0 enthalten?**

Sie können #A0 [für](building-search-queries.md#keyword-searches) [Stichwortsuchen,](keyword-queries-and-search-conditions.md) Stichwortabfragen und Suchbedingungen verwenden, wenn Sie nach Inhalten in Advanced eDiscovery. Die Suche nach #A0 wird auch bei der Suche nach Inhalten in Core eDiscovery und Content Search unterstützt.

Wir bieten CJK-Unterstützung für [](keyword-queries-and-search-conditions.md#search-conditions)alle [Suchoperatoren](keyword-queries-and-search-conditions.md#search-operators) und Suchbedingungen, einschließlich der booleschen Operatoren **AND**, **OR**, **NOT** und **NEAR**.

Wenn Sie sicher sind, dass Inhaltsstandorte oder -elemente #A0 enthalten, Suchabfragen jedoch keine Ergebnisse zurückgeben, klicken Sie auf das Symbol Abfragesprache-Land/Region ![Abfragesprache-Land/Region-Symbol in der Inhaltssuche](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) und wählen Sie den entsprechenden Sprach-Länder-Kulturcodewert für die Suche aus. Die standardmäßige Sprache/Region ist neutral.

**Kann ich nach mehreren Sprachen gleichzeitig suchen?**

Dies hängt von Ihrem Suchszenario ab.

- Wenn Sie [Daten in einem Überprüfungssatz](review-set-search.md) in Advanced eDiscovery abfragen, können Sie nach mehreren Sprachen suchen.

- Wenn Sie [eine Suche zum Sammeln von Daten erstellen,](create-search-to-collect-data.md)erstellen Sie eine separate Suche für jede Zielsprache. Wenn Sie z. B. nach einem Dokument suchen, das Chinesisch und Koreanisch enthält, wählen Sie chinesisch für die erste Abfrage aus, und wählen Sie koreanisch für die zweite Abfrage aus.

**Das Symbol "Sprache/Land/Region der Abfrage" wird nicht angezeigt, um eine Sprache für Abfragen in einem Überprüfungssatz auszuwählen. Wie kann ich eine Abfragesprache in einer Überprüfungssatzsuche angeben?**

Für Überprüfungssatzabfragen müssen Sie keine Dokumentsprache angeben. Advanced eDiscovery automatisch Dokumentsprachen erkennt, wenn Sie Einem Überprüfungssatz Inhalte hinzufügen. Auf diese Weise können Sie Ihre Abfrageergebnisse in einem Überprüfungssatz optimieren.

**Kann ich erkannte Sprachen in [Dateimetadaten sehen?](view-documents-in-review-set.md#file-metadata)**

Nein, in Dateimetadaten werden keine erkannten Sprachen angezeigt.

**Kann ich in einem Überprüfungssatz nach Dokumentsprachen filtern?**

Nein, Sie können in einem Überprüfungssatz nicht nach Dokumentsprachen filtern, sortieren oder suchen.

**Wirkt sich diese #A0 für Überprüfungssatzszenarien auf meine vorhandenen Such- und Überprüfungssätze aus?**

Nein, keine der vorhandenen Such- und Überprüfungssätze ändert sich. Vorhandene Daten müssen nicht neu indiziert werden, und die Suchergebnisse für englischen Text sind identisch.

**Wie kann ich meine Anzeigesprache in Chinesisch, Japanisch oder Koreanisch ändern?**

Informationen zum Ändern von Anzeigesprache und Zeitzone finden Sie unter Festlegen von Sprach- und [Regioneneinstellungen für Office 365](/office365/troubleshoot/access-management/set-language-and-region).

## <a name="known-issues"></a>Bekannte Probleme

- OCR unterstützt keine #A0 aus Bilddateien

- E-Mail-Dateien (z. B. *.eml und *.msg) [in](view-documents-in-review-set.md#annotate-view) der Anmerkungsansicht werden für #A0 nicht unterstützt.

- Die Hervorhebung von Suchtreffer in der [Textansicht](view-documents-in-review-set.md#text-view) wird für CJK-Sprachen nicht unterstützt.

- Das [Relevanzmodul,](using-relevance.md) das zum Analysieren von Daten verwendet wird, unterstützt keine CJK-Sprachen.

- [Abfragebasierte Halte halte](managing-holds.md#manage-non-custodial-holds) werden für CJK-Sprachen nicht unterstützt.