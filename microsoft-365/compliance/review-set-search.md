---
title: Abfragen der Daten in einem Prüfdateisatz
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
description: ''
ms.openlocfilehash: 4005b1e379b138f4eb22bb5c11e1f278185dc65e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597612"
---
# <a name="query-the-data-in-a-review-set"></a>Abfragen der Daten in einem Prüfdateisatz

In den meisten Fällen ist es hilfreich, die Daten in einer Überprüfungsgruppe tiefer zu analysieren und diese Daten zu organisieren, um eine effizientere Überprüfung zu ermöglichen. Mithilfe von Abfragen in einem Überprüfungs Satz können Sie sich auf eine Teilmenge von Dokumenten konzentrieren, die die Kriterien ihrer Überprüfung erfüllen.

## <a name="creating-and-running-a-query-in-a-review-set"></a>Erstellen und Durchführen einer Abfrage in einem Überprüfungs Satzes

Wenn Sie eine Abfrage für die Dokumente in einem Überprüfungs Satzes erstellen und ausführen möchten, klicken Sie in der Überprüfungsgruppe auf **neue Abfrage** . Nachdem Sie die Abfrage benannt und die Bedingungen definiert haben, klicken Sie auf **Speichern** , um die Abfrage zu speichern und auszuführen. Wenn Sie eine zuvor gespeicherte Abfrage ausführen möchten, klicken Sie auf eine gespeicherte Abfrage.

![Überprüfen von Mengen Abfragen](media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>Erstellen einer Überprüfungs Sätze-Abfrage

Sie können eine Abfrage erstellen, indem Sie eine Kombination aus Konditions Karten und Abfragesprache in der Konditions Karte Stichwörter verwenden. Sie können auch Bedingungs Karten zusammen als Block (eine *Bedingungsgruppe*) gruppieren, um eine komplexere Abfrage zu erstellen. Eine Liste und eine Beschreibung der Metadaten-Eigenschaften, die Sie durchsuchen können, finden Sie unter [Document Metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

### <a name="condition-cards"></a>Konditions Karten

Jedes durchsuchbare Feld in einem Überprüfungs-Datensatz verfügt über eine entsprechende Bedingungs Karte, die Sie zum Erstellen Ihrer Abfrage verwenden können.

Es gibt mehrere Arten von Konditions Karten:

- FREETEXT: eine FREETEXT-Bedingungs Karte wird für Textfelder wie Betreff verwendet. Sie können mehrere Suchbegriffe auflisten, indem Sie Sie durch ein Komma voneinander trennen.

- Datum: eine Datums-Konditions Karte wird für Datumsfelder wie Datum der letzten Änderung verwendet.

- Suchoptionen: eine Bedingungs Karte für Suchoptionen enthält eine Liste der möglichen Werte für das jeweilige Feld im Überprüfungs. Dies wird für Felder wie Absender verwendet, bei denen eine begrenzte Anzahl möglicher Werte in ihrer Überprüfungsgruppe vorhanden ist.

- Stichwort: eine Keyword-Bedingungs Karte ist eine bestimmte Instanz der FREETEXT-Konditions Karte, mit der Sie nach Begriffen suchen oder KQL-ähnliche Abfragesprache in verwenden können. Weitere Details finden Sie weiter unten.

### <a name="query-language"></a>Abfragesprache

Zusätzlich zu den Konditions Karten können Sie eine KQL-ähnliche Abfragesprache in der Stichwörter Karte verwenden, um Ihre Abfrage zu erstellen. Die Abfragesprache für Review-Mengen Abfragen unterstützt Standard boolesche Operatoren wie **and**, **or**, **Not**und **near**. Außerdem wird ein Platzhalter mit einem einzelnen Zeichen (?) und ein mehr stelliger Platzhalter (*) unterstützt.

## <a name="using-filters"></a>Verwenden von Filtern

Zusätzlich zu den Abfragen, die Sie speichern können, können Sie mithilfe von Filtersätzen für eine Überprüfungs Satz Abfrage schnell zusätzliche Bedingungen anwenden. Auf diese Weise können Sie die Ergebnisse, die von einer Abfrage mit Überprüfungs Sätzen angezeigt werden, weiter verfeinern.

![Überprüfen von Filtersätzen](media/AeDReviewSetFilters.png)

Filter unterscheiden sich in zwei wichtigen Punkten von Abfragen:

- Filter sind vorübergehend. Sie bleiben außerhalb der vorhandenen Sitzung bestehen. Mit anderen Worten: Sie können einen Filter nicht speichern. Abfragen werden in der Überprüfungsgruppe gespeichert und greifen beim Öffnen des Überprüfungs Satzes auf diese zu.

- Filter sind immer additiv. Filter werden zusätzlich zur aktuellen Überprüfungs Satz Abfrage angewendet. Durch das Anwenden einer anderen Abfrage werden die Ergebnisse ersetzt, die von der aktuellen Abfrage zurückgegeben werden.
