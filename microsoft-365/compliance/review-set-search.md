---
title: Abfragen der Daten in einem Prüfdateisatz
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In diesem Artikel erfahren Sie, wie Sie eine Abfrage in einem Überprüfungspaket erstellen und ausführen, um Daten für eine effizientere Überprüfung in einem erweiterten eDiscovery-Fall zu organisieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 508e8e9fdb4a558a998a33aa561dc3755edcc40d
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816718"
---
# <a name="query-the-data-in-a-review-set"></a>Abfragen der Daten in einem Prüfdateisatz

In den meisten Fällen ist es hilfreich, die Daten in einer Überprüfungsgruppe tiefer zu analysieren und diese Daten zu organisieren, um eine effizientere Überprüfung zu ermöglichen. Mithilfe von Abfragen in einem Überprüfungs Satz können Sie sich auf eine Teilmenge von Dokumenten konzentrieren, die die Kriterien ihrer Überprüfung erfüllen.

## <a name="creating-and-running-a-query-in-a-review-set"></a>Erstellen und Durchführen einer Abfrage in einem Überprüfungs Satzes

Wenn Sie eine Abfrage für die Dokumente in einem Überprüfungs Satzes erstellen und ausführen möchten, wählen Sie **neue Abfrage** in der Überprüfungsgruppe aus. Nachdem Sie die Abfrage benannt und die Bedingungen definiert haben, wählen Sie **Speichern** aus, um die Abfrage zu speichern und auszuführen. Wenn Sie eine zuvor gespeicherte Abfrage ausführen möchten, wählen Sie eine gespeicherte Abfrage aus.

![Überprüfen von Mengen Abfragen](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>Erstellen einer Überprüfungs Sätze-Abfrage

Sie können eine Abfrage erstellen, indem Sie eine Kombination aus Konditions Karten und Abfragesprache in der Konditions Karte Stichwörter verwenden. Sie können auch Bedingungs Karten zusammen als Block (eine *Bedingungsgruppe*) gruppieren, um eine komplexere Abfrage zu erstellen. Eine Liste und Beschreibung der Metadaten-Eigenschaften, die Sie durchsuchen können, finden Sie unter [Dokumentmetadatenfeldern in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

### <a name="condition-cards"></a>Konditions Karten

Jedes durchsuchbare Feld in einem Überprüfungs-Datensatz verfügt über eine entsprechende Bedingungs Karte, die Sie zum Erstellen Ihrer Abfrage verwenden können.

Es gibt mehrere Arten von Konditions Karten:

- FREETEXT: eine FREETEXT-Bedingungs Karte wird für Textfelder wie Betreff verwendet. Sie können mehrere Suchbegriffe auflisten, indem Sie Sie durch ein Komma voneinander trennen.

- Datum: eine Datums-Konditions Karte wird für Datumsfelder wie Datum der letzten Änderung verwendet.

- Suchoptionen: eine Bedingungs Karte für Suchoptionen enthält eine Liste der möglichen Werte für das jeweilige Feld im Überprüfungs. Dies wird für Felder wie Absender verwendet, bei denen eine begrenzte Anzahl möglicher Werte in ihrer Überprüfungsgruppe vorhanden ist.

- Stichwort: eine Keyword-Bedingungs Karte ist eine bestimmte Instanz der FREETEXT-Konditions Karte, mit der Sie nach Begriffen suchen oder KQL-ähnliche Abfragesprache in verwenden können. Weitere Details finden Sie weiter unten.

### <a name="query-language"></a>Abfragesprache

Zusätzlich zu den Konditions Karten können Sie eine KQL-ähnliche Abfragesprache in der Stichwörter Karte verwenden, um Ihre Abfrage zu erstellen. Die Abfragesprache für Review-Mengen Abfragen unterstützt Standard boolesche Operatoren wie **and**, **or**, **Not**und **near**. Außerdem wird ein Platzhalter mit einem einzelnen Zeichen (?) und ein mehr stelliger Platzhalter (*) unterstützt.

## <a name="filters"></a>Filter

Zusätzlich zu den Abfragen, die Sie speichern können, können Sie mithilfe von Filtersätzen für eine Überprüfungs Satz Abfrage schnell zusätzliche Bedingungen anwenden. Mithilfe von Filtern können Sie die Ergebnisse, die von einer Abfrage mit Überprüfungs Sätzen angezeigt werden, weiter verfeinern.

![Überprüfen von Filtersätzen](../media/AeDReviewSetFilters.png)

Filter unterscheiden sich in zwei wichtigen Punkten von Abfragen:

- Filter sind vorübergehend. Sie bleiben außerhalb der vorhandenen Sitzung bestehen. Mit anderen Worten: Sie können einen Filter nicht speichern. Abfragen werden in der Überprüfungsgruppe gespeichert und greifen beim Öffnen des Überprüfungs Satzes auf diese zu.

- Filter sind immer additiv. Filter werden zusätzlich zur aktuellen Prüfdateisatz-Abfrage angewendet. Durch das Anwenden einer anderen Abfrage werden die von der aktuellen Abfrage zurückgegebenen Ergebnisse ersetzt.
