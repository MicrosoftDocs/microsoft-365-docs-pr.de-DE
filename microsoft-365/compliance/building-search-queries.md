---
title: Erstellen von Suchabfragen in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: Verwenden Sie Stichwörter und Bedingungen, um den Umfang der Suche einzuschränken, wenn Sie mithilfe von Advanced eDiscovery in Microsoft 365 nach Daten suchen.
ms.openlocfilehash: 8ec1e099625bb081f8a915f08ac818fddcc2b60d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751112"
---
# <a name="build-search-collection-queries-in-advanced-ediscovery"></a>Erstellen von Such Sammlungsabfragen in Advanced eDiscovery

Beim Erstellen von Suchabfragen zum Erfassen von Daten in einem erweiterten eDiscovery-Fall können Sie Stichwörter verwenden, um bestimmte Inhalte und Bedingungen zu finden, um den Umfang der Suche einzuschränken, um Elemente zurückzugeben, die für ihre rechtliche Untersuchung am relevantesten sind.

![Verwenden von Stichwörtern und Bedingungen zum Einschränken der Ergebnisse einer Suche](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>Schlüsselwortsuchen

Geben Sie eine Stichwortabfrage in das Feld **Schlüsselwörter** in der Suchabfrage ein. Sie können Schlüsselwörter, Eigenschaften von e-Mail-Nachrichten wie gesendete und empfangene Datumsangaben oder Dokumenteigenschaften angeben, beispielsweise Dateinamen oder das Datum, an dem ein Dokument zuletzt geändert wurde. Sie können auch komplexere Abfragen mit booleschen Operatoren wie **AND**, **OR**, **NOT** und **NEAR** verwenden. Sie können auch nach vertraulichen Informationen (beispielsweise Sozialversicherungsnummern) in Dokumenten in SharePoint und OneDrive (nicht in e-Mail-Nachrichten) suchen oder nach Dokumenten suchen, die extern freigegeben wurden. Wenn Sie das Feld **Schlüsselwörter** leer lassen, werden alle Inhalte in den angegebenen Inhaltsspeicherorten in die Suchergebnisse einbezogen.

## <a name="keyword-list"></a>Stichwortliste

Alternativ können Sie das Kontrollkästchen **Schlüsselwort Liste anzeigen** aktivieren und in jeder Zeile einen Stichwort-oder stichwortausdruck eingeben. Die Schlüsselwörter in jeder Zeile werden durch einen logischen Operator (der in der Suchabfrage Syntax als *c:s* dargestellt wird) verbunden, der in der Funktionalität des **or** -Operators in der erstellten Suchabfrage ähnelt. Dies bedeutet, dass Elemente, die ein beliebiges Schlüsselwort in einer beliebigen Zeile enthalten, in den Suchergebnissen enthalten sind. Sie können bis zu 180 Zeilen in der Liste Stichwort in Erweiterte eDiscovery-Suchabfragen hinzufügen.

![Verwenden der Stichwortliste zum Abrufen von Statistiken zu jedem Stichwort in der Abfrage](../media/KeywordListSearch.png)

Gründe für die Verwendung der Schlüsselwortliste Sie können Statistiken abrufen, die zeigen, wie viele Elemente in der Stichwortliste mit jedem Stichwort übereinstimmen. Dies kann Ihnen helfen, schnell die Schlüsselwörter zu identifizieren, die am häufigsten (und am wenigsten) effektiv sind. Sie können auch eine Stichwort Phrase (umgeben von Klammern) in einer Zeile in der Liste Stichwörter verwenden. Weitere Informationen zu Suchstatistiken finden Sie unter [Suchstatistiken](search-statistics-in-advanced-ediscovery.md).

## <a name="conditions"></a>Bedingungen

Sie können Suchbedingungen hinzufügen, um den Umfang einer Suche einzuschränken und eine verfeinerte Ergebnismenge zurückzugeben. Jede Bedingung fügt eine Klausel zur Suchabfrage hinzu, die beim Starten der Suche erstellt und ausgeführt wird. Eine Bedingung ist logisch mit der Stichwortabfrage verbunden, die im Feld Stichwort von einem logischen Operator angegeben wird (der in der Suchabfrage Syntax als *c:c* dargestellt wird), der in der Funktionalität für den **and-** Operator ähnlich ist. Das bedeutet, dass Elemente sowohl die Stichwortabfrage als auch eine oder mehrere Bedingungen erfüllen müssen, die in den Suchergebnissen enthalten sein sollen. Auf diese Weise können die Suchergebnisse mithilfe von Bedingungen weiter eingegrenzt werden. Eine Liste und eine Beschreibung der Bedingungen, die Sie in einer Suchabfrage verwenden können, finden Sie im Abschnitt "Suchbedingungen" unter [Stichwortabfragen und Suchbedingungen](keyword-queries-and-search-conditions.md#search-conditions).
