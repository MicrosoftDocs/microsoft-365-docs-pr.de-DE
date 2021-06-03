---
title: Abfragen des Inhalts in einem Prüfdateisatz
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
description: Erfahren Sie, wie Sie eine Abfrage in einem Prüfdateisatz erstellen und ausführen, um Inhalte für eine effizientere Überprüfung in einem Advanced eDiscovery Fall zu organisieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64dbeb8ad68f4188e5768a0a7e0e80ca6c22760b
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736422"
---
# <a name="query-and-filter-content-in-a-review-set"></a>Abfragen und Filtern von Inhalten in einem Prüfdateisatz

In den meisten Fällen ist es hilfreich, sich eingehender mit den Inhalten in einem Prüfdateisatz zu befassen und sie zu organisieren, um eine effizientere Überprüfung zu ermöglichen. Mithilfe von Filtern und Abfragen in einem Prüfdateisatz können Sie sich auf eine Teilmenge von Dokumenten konzentrieren, die den Kriterien Ihrer Rezension entsprechen.

## <a name="default-filters"></a>Standardfilter

In einem Prüfdateisatz gibt es fünf Standardfilter, die im Prüfdateisatz vorinstalliert sind:

- Schlüsselwörter
- Datum
- Absender/Autor
- Betreff/Titel
- Tags

![Standardfiltertypen](../media/DefaultFilterTypes.png)

Klicken Sie auf jeden Filter, um ihn zu erweitern und einen Wert zuzuweisen. Klicken Sie außerhalb des Filters, um den Filter automatisch auf den Prüfdateisatz anzuwenden. Der folgende Screenshot zeigt den Datumsfilter, der so konfiguriert ist, dass Dokumente innerhalb eines Datumsbereichs angezeigt werden.

![Erweiterter Standardfilter](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a>Hinzufügen oder Entfernen von Filtern

Um Filter hinzuzufügen oder zu entfernen, die für den Prüfdateisatz angezeigt werden, wählen Sie **Filter** aus, um den Filterbereich zu öffnen, der auf einer Flyoutseite angezeigt wird. 

![Filterbereich](../media/FilterPanel.png)

Die verfügbaren Filter sind in vier Abschnitten unterteilt:

- **Suche:** Filter, die unterschiedliche Suchfunktionen bereitstellen.

- **Analyse & vorhersagebasierte Codierung:** Filter für Eigenschaften, die generiert und zu Dokumenten hinzugefügt werden, wenn Sie das **Dokument & E-Mail-Analyseauftrag** ausführen oder Modelle für die Vorhersagecodierung verwenden.

- **IDs:** Filtert nach allen ID-Eigenschaften von Dokumenten.

- **Elementeigenschaften:** Filter für Dokumenteigenschaften. 

Erweitern Sie jeden Abschnitt, und wählen Oder deaktivieren Sie Filter, um sie im Filtersatz hinzuzufügen oder zu entfernen. Wenn Sie einen Filter hinzufügen, wird er im Filtersatz angezeigt. 

![Liste der Filterabschnitte und Eigenschaften im Filterbereich](../media/FilterPanel2.png)

> [!NOTE]
> Wenn Sie einen Abschnitt im Filterbereich erweitern, werden Sie feststellen, dass die Standardfiltertypen ausgewählt sind. Sie können diese ausgewählt lassen oder die Auswahl aufheben und sie aus dem Filtersatz entfernen. 

## <a name="filter-types"></a>Filtertypen

Jedes durchsuchbare Feld in einem Prüfdateisatz verfügt über einen entsprechenden Filter, den Sie für Filterelemente verwenden können, die auf einem bestimmten Feld basieren.

Es gibt mehrere Filtertypen:

- **Freetext:** Auf Textfelder wie "Subject" wird ein Freitextfilter angewendet. Sie können mehrere Suchbegriffe auflisten, indem Sie sie durch ein Komma trennen.

- **Datum:** Ein Datumsfilter wird für Datumsfelder wie "Datum der letzten Änderung" verwendet.

- **Suchoptionen:** Ein Suchoptionenfilter stellt eine Liste möglicher Werte (jeder Wert wird mit einem Kontrollkästchen angezeigt, das Sie auswählen können) für bestimmte Felder in der Rezension bereit. Dieser Filter wird für Felder wie "Sender" verwendet, in denen eine begrenzte Anzahl möglicher Werte im Prüfdateisatz vorhanden ist.

- **Schlüsselwort:** Eine Schlüsselwortbedingung ist eine bestimmte Instanz der Freitextbedingung, die Sie verwenden können, um nach Begriffen zu suchen. Sie können auch KQL-ähnliche Abfragesprache in diesem Filtertyp verwenden. Weitere Informationen finden Sie in den Abschnitten "Abfragesprache" und "Erweiterter Abfrage-Generator" in diesem Thema.

## <a name="include-and-exclude-filter-relationships"></a>Einschließen und Ausschließen von Filterbeziehungen

Sie haben die Möglichkeit, die Ein- und Ausschließen-Beziehung für einen bestimmten Filter zu ändern. Im Tag-Filter können Sie beispielsweise Elemente ausschließen, die mit einem bestimmten Tag markiert sind, indem Sie im Dropdownfilter **"Gleich"** auswählen. 

![Tagfilter ausschließen](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a>Speichern von Filtern als Abfragen

Nachdem Sie mit Ihren Filtern zufrieden sind, können Sie die Filterkombination als Filterabfrage speichern. Auf diese Weise können Sie den Filter in zukünftigen Überprüfungssitzungen anwenden.

Wählen Sie zum Speichern eines Filters **die Option "Abfrage speichern"** aus, und nennen Sie sie. Sie oder andere Prüfer können zuvor gespeicherte Filterabfragen ausführen, indem Sie die Dropdownliste **"Gespeicherte Filterabfragen"** und eine Filterabfrage auswählen, die auf Prüfdateisatzdokumente angewendet werden soll. 

![Speichern einer Filterabfrage](../media/SaveFilterQuery.png)

Um eine Filterabfrage zu löschen, öffnen Sie den Filterbereich, und wählen Sie neben der Abfrage das Papierkorbsymbol aus.

![Löschen einer Filterabfrage](../media/DeleteFilterQuery.png)

## <a name="query-language"></a>Abfragesprache

Zusätzlich zur Verwendung von Filtern können Sie auch eine KQL-ähnliche Abfragesprache im Filter "Schlüsselwörter" verwenden, um die Suchabfrage für den Prüfdateisatz zu erstellen. Die Abfragesprache für Überprüfungssatzabfragen unterstützt standardmäßige boolesche Operatoren wie **AND**, **OR**, **NOT** und **NEAR**. Es unterstützt auch einen einstelligen Platzhalter (?) und einen mehrstelligen Platzhalter (*).

## <a name="advanced-query-builder"></a>Erweiterter Abfrage-Generator

Sie können auch erweiterte Abfragen erstellen, um nach Dokumenten in einem Prüfdateisatz zu suchen.

1. Öffnen Sie den Filterbereich, wählen Sie **Filter** aus, und erweitern Sie den **Suchabschnitt.**

  ![Hinzufügen eines KQL-Filters](../media/AddKQLFilter.png)

2. Wählen Sie den **KQL-Filter** aus, und klicken Sie auf **"Abfrage-Generator öffnen".**

   In diesem Bereich können Sie komplexe KQL-Abfragen mithilfe des Abfrage-Generators erstellen. Sie können Bedingungen hinzufügen oder Bedingungsgruppen hinzufügen, die aus mehreren Bedingungen bestehen, die logisch durch **AND-** oder **OR-Beziehungen** verbunden sind.

   ![Verwenden des Abfrage-Generators zum Konfigurieren komplexer Filterabfragen](../media/ComplexQuery.png)
