---
title: Abfragen der Daten in einem Prüfdateisatz
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
ms.openlocfilehash: 446f3f2588a79cb328476db490f1f555448b5ce7
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082574"
---
# <a name="query-the-data-in-a-review-set"></a>Abfragen der Daten in einem Prüfdateisatz

In den meisten Fällen wird es hilfreich sein, tiefer in die Inhalte einer Überprüfungsgruppe eingreifen und diese für eine effizientere Überprüfung organisieren zu können. Abfragen in einem Überprüfungs Satz ermöglichen es Ihnen, sich auf eine Teilmenge von Dokumenten zu konzentrieren, die die von Ihnen auf einmal definierten Kriterien erfüllen.

## <a name="creating-and-running-a-query-within-a-review-set"></a>Erstellen und Durchführen einer Abfrage innerhalb eines Überprüfungs Satzes

Wenn Sie eine Abfrage innerhalb Ihres Überprüfungs Satzes erstellen und ausführen möchten, klicken Sie in der Überprüfungsgruppe auf "neue Abfrage". Nachdem Sie die Abfrage benannt und die Bedingungen definiert haben, klicken Sie auf "Speichern", um die Abfrage auszuführen. Wenn Sie eine zuvor gespeicherte Abfrage ausführen möchten, klicken Sie einfach auf die gespeicherte Abfrage. Eine Liste der Metadaten, nach denen Sie suchen können, finden Sie unter [Document Metadata fields](document-metadata-fields.md) .

## <a name="building-your-query"></a>Erstellen der Abfrage

Sie können Ihre Abfrage mit einer Kombination aus Konditions Karten und Abfragesprache in der Bedingungs Karte Stichwörter erstellen. Sie können Konditions Karten zusammen als Block gruppieren, um eine komplexere Abfrage zu entwerfen.

### <a name="condition-card"></a>Konditions Karte

Jedes durchsuchbare Feld in einem Überprüfungs-Datensatz verfügt über eine entsprechende Bedingungs Karte, die Sie zum Erstellen Ihrer Abfrage verwenden können.

Es gibt mehrere Arten von Konditions Karten:
- FREETEXT: FREETEXT-Bedingungs Karte wird für Textfelder wie Betreff verwendet. Sie können mehrere Suchbegriffe auflisten, indem Sie Sie durch ein Komma voneinander trennen.
- Datum: Datum Konditions Karte wird für Datumsfelder wie Datum der letzten Änderung verwendet.
- Suchoptionen: auf der Bedingungs Karte für Suchoptionen wird eine Liste der möglichen Werte für das jeweilige Feld in der Überprüfungsgruppe bereitgestellt. Dies wird für Felder wie Absender verwendet, bei denen eine begrenzte Anzahl möglicher Werte in ihrer Überprüfungsgruppe vorhanden ist.
- Stichwort: Bedingungs Karte für Schlüsselwörter ist eine bestimmte Instanz der FREETEXT-Bedingungs Karte, die Sie verwenden können, um nach Begriffen zu suchen, oder verwenden Sie die KQL-ähnliche Abfragesprache in. Weitere Details finden Sie weiter unten.

### <a name="query-language"></a>Abfragesprache

Zusätzlich zu den Konditions Karten können Sie eine KQL-ähnliche Abfragesprache in der Stichwörter Karte verwenden, um Ihre Abfrage zu gestalten. Die Abfragesprache unterstützt die standardmäßige KQL-Syntax wie and, or, Not und Near (n). Es unterstützt auch Einzelplatz Platzhalter (?) und mehrstellige Platzhalterzeichen (*).

## <a name="filter"></a>Filter

Zusätzlich zu den Abfragen, die Sie speichern können, können Sie mithilfe von Filtern zusätzliche Bedingungen in der Fliege mit Ihren Abfrageergebnissen überlagern. Filter unterscheiden sich in einigen wichtigen Punkten von Abfragen:
- Filter sind vorübergehend (d. h., Sie werden nicht in verschiedenen Sitzungen gespeichert), während Abfragen in der Überprüfungsgruppe gespeichert werden.
- Filter sind immer Additiv; Filter werden oben auf die Abfrage angewendet, die Sie zurzeit anwenden, während durch das Anwenden einer Abfrage die Abfrage wirksam ersetzt wird.