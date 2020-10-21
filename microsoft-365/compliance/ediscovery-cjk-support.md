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
description: Erfahren Sie, wie Advanced eDiscovery in Microsoft 365 die Sprachen Chinesisch, Japanisch und Koreanisch (CJK) unterstützt, die einen Doppelbyte-Zeichensatz verwenden.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626935"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>Unterstützung für CJK-Sprachen für erweiterte eDiscovery

Advanced eDiscovery unterstützt Doppelbyte-Zeichensatz Sprachen (darunter vereinfachtes Chinesisch, traditionelles Chinesisch, Japanisch und Koreanisch, die als *cjk* -Sprachen bezeichnet werden) für die folgenden erweiterten Szenarien in einem Überprüfungs Satz:

- Wenn Sie [die Daten in einem Überprüfungs Satzes Abfragen](review-set-search.md).

- Wenn Sie [Dokumente in einem Überprüfungs Satzes markieren](tagging-documents.md).

- Wenn Sie [Falldaten in einer Überprüfungsgruppe](analyzing-data-in-review-set.md) mithilfe von nahezu doppelter Erkennung, e-Mail-Threading und Design Analyse analysieren.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wie erstelle ich eine Suche zum Sammeln von Elementen, die CJK-Zeichen enthalten?**

Bei der Suche nach Inhalten in Advanced eDiscovery können Sie CJK-Zeichen für [Stichwortsuche](building-search-queries.md#keyword-searches), [Stichwortabfragen und Suchbedingungen](keyword-queries-and-search-conditions.md) verwenden. Die Suche nach CJK-Zeichen wird auch bei der Suche nach Inhalten in der zentralen eDiscovery-und Inhaltssuche unterstützt.

Wir bieten CJK-Unterstützung für alle [Suchoperatoren](keyword-queries-and-search-conditions.md#search-operators) und [Suchbedingungen](keyword-queries-and-search-conditions.md#search-conditions), einschließlich der booleschen Operatoren **and**, **or**, **Not**und **near**.

Wenn Sie sicher sind, dass Inhaltsspeicher oder-Elemente CJK-Zeichen enthalten, die Suche jedoch keine Ergebnisse zurückgibt, klicken Sie auf das Symbol Abfragesprache – Land/Region ![Abfragesprache – Land/Region-Symbol in der Inhaltssuche](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) aus, und wählen Sie den entsprechenden Kultur Codewert für Sprache/Land für die Suche aus. Die standardmäßige Sprache/Region ist neutral.

**Kann ich gleichzeitig nach mehreren Sprachen suchen?**

Dies hängt von Ihrem Such Szenario ab.

- Wenn Sie [Daten in einer Überprüfungsgruppe](review-set-search.md) in Advanced eDiscovery Abfragen, können Sie nach mehreren Sprachen suchen.

- Wenn Sie [eine Suche zum Erfassen von Daten erstellen](create-search-to-collect-data.md), erstellen Sie eine separate Suche für jede Sprache, für die Sie sich interessieren. Wenn Sie beispielsweise nach einem Dokument suchen, das sowohl Chinesisch als auch Koreanisch enthält, wählen Sie Chinesisch für Ihre erste Abfrage aus, und wählen Sie Koreanisch für die zweite Abfrage aus.

**Das Symbol Abfragesprache-Land/Region wird nicht angezeigt, um eine Sprache für Abfragen in einem Überprüfungs Satzes auszuwählen. Wie kann ich eine Abfragesprache in einer Überprüfungs Sätze-Suche angeben?**

Zum Überprüfen von Abfrage Sätzen müssen Sie keine Dokumentsprache angeben. Erweiterte eDiscovery erkennt Dokumentsprachen automatisch, wenn Sie einem Überprüfungs Satzes Inhalte hinzufügen. Auf diese Weise können Sie Ihre Abfrageergebnisse in einem Überprüfungspaket optimieren.

**Kann ich erkannte Sprachen in [Datei Metadaten](view-documents-in-review-set.md#file-metadata)anzeigen?**

Nein, erkannte Sprachen werden in Datei Metadaten nicht angezeigt.

**Kann ich nach Dokumentsprachen in einem Überprüfungs Satzes Filtern**?

Nein, Sie können nicht nach Dokumentsprachen in einem Überprüfungs Satzes filtern, Sortieren oder durchsuchen.

**Betrifft diese cjk-Version für die Überprüfung Szenarien Festlegen einer meiner vorhandenen suchen und Überprüfungs Sätze?**

Nein, keines der vorhandenen Such-und Überprüfungs Sätze wird geändert. Sie müssen keine vorhandenen Daten neu indizieren, und die Suchergebnisse für den englischen Text sind identisch.

**Wie ändere ich meine Anzeigesprache in Chinesisch, Japanisch oder Koreanisch?**

Informationen zum Ändern der Anzeigesprache und der Zeitzone finden Sie unter [Vorgehensweise Festlegen von Sprach-und Regionseinstellungen für Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).

## <a name="known-issues"></a>Bekannte Probleme

- OCR unterstützt keine CJK-Zeichen aus Bilddateien

- E-Mail-Dateien (wie *. eml und *. msg) in [anmerkungsansicht](view-documents-in-review-set.md#annotate-view) werden für CJK-Sprachen nicht unterstützt.

- Die Hervorhebung von Suchtreffern in der [Text Ansicht](view-documents-in-review-set.md#text-view) wird für CJK-Sprachen nicht unterstützt.

- Das zum Analysieren von Daten verwendete [Relevanz-Modul](using-relevance.md) unterstützt keine CJK-Sprachen.

- [Abfragebasierte Aufbewahrungen](managing-holds.md#manage-non-custodial-holds) werden für CJK-Sprachen nicht unterstützt. 
