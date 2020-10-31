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
ms.openlocfilehash: 1ead897d412af2356d8b57ab8494539a5ed9a019
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816568"
---
# <a name="query-the-data-in-a-review-set"></a>Abfragen der Daten in einem Prüfdateisatz

In den meisten Fällen ist es hilfreich, die Daten in einer Überprüfungsgruppe tiefer zu analysieren und diese Daten zu organisieren, um eine effizientere Überprüfung zu ermöglichen. Mithilfe von Abfragen in einem Überprüfungs Satz können Sie sich auf eine Teilmenge von Dokumenten konzentrieren, die die Kriterien ihrer Überprüfung erfüllen.

## <a name="creating-and-running-a-query-in-a-review-set"></a>Erstellen und Durchführen einer Abfrage in einem Überprüfungs Satzes

Wenn Sie eine Abfrage für die Dokumente in einem Überprüfungs Satzes erstellen und ausführen möchten, wählen Sie **neue Abfrage** in der Überprüfungsgruppe aus. Nachdem Sie die Abfrage benannt und die Bedingungen definiert haben, wählen Sie **Speichern** aus, um die Abfrage zu speichern und auszuführen. Wenn Sie eine zuvor gespeicherte Abfrage ausführen möchten, wählen Sie eine gespeicherte Abfrage aus.

![Überprüfen von Mengen Abfragen](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>Erstellen einer Überprüfungs Sätze-Abfrage

Sie können eine Abfrage mithilfe einer Kombination aus Schlüsselwörtern, Eigenschaften und Bedingungen in der Bedingung Schlüsselwörter erstellen. Sie können auch Bedingungen als Block (als *Bedingungsgruppe* bezeichnet) gruppieren, um eine komplexere Abfrage zu erstellen. Eine Liste und Beschreibung der Metadaten-Eigenschaften, die Sie durchsuchen können, finden Sie unter [Dokumentmetadatenfeldern in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

### <a name="conditions"></a>Bedingungen

Jedes durchsuchbare Feld in einem Überprüfungs Sätze verfügt über eine entsprechende Bedingung, die Sie zum Erstellen Ihrer Abfrage verwenden können.

Es gibt mehrere Arten von Bedingungen:

- FREETEXT: eine FREETEXT-Bedingung wird für Textfelder wie Betreff verwendet. Sie können mehrere Suchbegriffe auflisten, indem Sie Sie durch ein Komma voneinander trennen.

- Date: eine Datumsbedingung wird für Datumsfelder wie Datum der letzten Änderung verwendet.

- Suchoptionen: eine Bedingung für Suchoptionen stellt eine Liste der möglichen Werte für das jeweilige Feld in der Überprüfungsgruppe bereit. Dies wird für Felder wie Absender verwendet, bei denen eine begrenzte Anzahl möglicher Werte in ihrer Überprüfungsgruppe vorhanden ist.

- Stichwort: eine Schlüsselwort Bedingung ist eine bestimmte Instanz der FREETEXT-Bedingung, die Sie verwenden können, um nach Begriffen zu suchen oder die KQL-ähnliche Abfragesprache in zu verwenden. Weitere Details finden Sie weiter unten.

### <a name="query-language"></a>Abfragesprache

Nebenbedingungen können Sie eine KQL-ähnliche Abfragesprache in der Bedingung Schlüsselwörter verwenden, um Ihre Abfrage zu erstellen. Die Abfragesprache für Review-Mengen Abfragen unterstützt Standard boolesche Operatoren wie **and** , **or** , **Not** und **near** . Außerdem wird ein Platzhalter mit einem einzelnen Zeichen (?) und ein mehr stelliger Platzhalter (*) unterstützt.

## <a name="filters"></a>Filter

Zusätzlich zu den Abfragen, die Sie speichern können, können Sie mithilfe von Filtersätzen für eine Überprüfungs Satz Abfrage schnell zusätzliche Bedingungen anwenden. Mithilfe von Filtern können Sie die Ergebnisse, die von einer Abfrage mit Überprüfungs Sätzen angezeigt werden, weiter verfeinern.

![Überprüfen von Filtersätzen](../media/AeDReviewSetFilters.png)

Filter unterscheiden sich in zwei wichtigen Punkten von Abfragen:

- Filter sind vorübergehend. Sie bleiben außerhalb der vorhandenen Sitzung bestehen. Mit anderen Worten: Sie können einen Filter nicht speichern. Abfragen werden in der Überprüfungsgruppe gespeichert und greifen beim Öffnen des Überprüfungs Satzes auf diese zu.

- Filter sind immer additiv. Filter werden zusätzlich zur aktuellen Prüfdateisatz-Abfrage angewendet. Durch das Anwenden einer anderen Abfrage werden die von der aktuellen Abfrage zurückgegebenen Ergebnisse ersetzt.
