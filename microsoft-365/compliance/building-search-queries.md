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
description: Verwenden Sie Schlüsselwörter und Bedingungen, um den Suchbereich beim Suchen nach Daten mithilfe von Advanced eDiscovery in Microsoft 365.
ms.openlocfilehash: e0df319257776d3995a4b8e37781d7b5dad54d82
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838481"
---
# <a name="build-search-queries-for-collections-in-advanced-ediscovery"></a>Erstellen von Suchabfragen für Sammlungen in Advanced eDiscovery

Beim Konfigurieren der Suchabfrage beim Erstellen einer Auflistung [in](collections-overview.md) einem Advanced eDiscovery-Fall können Sie Schlüsselwörter verwenden, um bestimmte Inhalte und Bedingungen zu finden, um den Suchbereich zu einenten, um Elemente zurücksenden zu können, die für Ihre rechtliche Untersuchung am relevantesten sind.

![Verwenden von Schlüsselwörtern und Bedingungen zum Einen der Ergebnisse einer Suche](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>Schlüsselwortsuchen

Geben Sie eine Schlüsselwortabfrage in **das Feld Schlüsselwörter** in der Suchabfrage ein. Sie können Schlüsselwörter, E-Mail-Nachrichteneigenschaften wie gesendete und empfangene Datumsangaben oder Dokumenteigenschaften angeben, z. B. Dateinamen oder das Datum, an dem ein Dokument zuletzt geändert wurde. Sie können auch komplexere Abfragen mit booleschen Operatoren wie **AND**, **OR**, **NOT** und **NEAR** verwenden. Sie können auch nach vertraulichen Informationen (z. B. Sozialversicherungsnummern) in Dokumenten in SharePoint und OneDrive (nicht in E-Mail-Nachrichten) oder nach Extern freigegebenen Dokumenten suchen. Wenn Sie das Feld **Schlüsselwörter** leer lassen, werden alle Inhalte in den angegebenen Inhaltsspeicherorten in die Suchergebnisse einbezogen.

## <a name="keyword-list"></a>Stichwortliste

Alternativ können Sie  das Kontrollkästchen Stichwortliste anzeigen aktivieren und in jeder Zeile ein Schlüsselwort oder eine Schlüsselwortphrase eingeben. Die Schlüsselwörter in jeder Zeile werden durch einen logischen Operator (der in der Suchabfragesyntax als *c:s* dargestellt wird) verbunden, der in der Funktionalität mit dem **OR-Operator** in der erstellten Suchabfrage vergleichbar ist. Dies bedeutet, dass Elemente, die ein Beliebiges Schlüsselwort in einer Zeile enthalten, in den Suchergebnissen enthalten sind. Sie können bis zu 180 Zeilen in der Stichwortliste in Advanced eDiscovery hinzufügen.

![Verwenden der Stichwortliste zum Abfragen von Statistiken zu jedem Schlüsselwort in der Abfrage](../media/KeywordListSearch.png)

Gründe für die Verwendung der Schlüsselwortliste Sie können Statistiken erhalten, die anzeigen, wie viele Elemente mit jedem Schlüsselwort in der Stichwortliste übereinstimmen. Auf diese Weise können Sie die Stichwörter, die am effektivsten (und am wenigsten) sind, schnell identifizieren. Sie können auch einen Schlüsselwortbegriff (umgeben von Klammern) in einer Zeile in der Stichwörterliste verwenden. Weitere Informationen zu Suchstatistiken finden Sie unter [Suchstatistik](search-statistics-in-advanced-ediscovery.md).

## <a name="conditions"></a>Bedingungen

Sie können Suchbedingungen hinzufügen, um den Bereich einer Suche zu eindrücken und einen verfeinerteren Satz von Ergebnissen zurücksennen. Jede Bedingung fügt eine Klausel zur Suchabfrage hinzu, die beim Starten der Suche erstellt und ausgeführt wird. Eine Bedingung ist logisch mit der im Schlüsselwortfeld angegebenen Schlüsselwortabfrage durch einen logischen Operator (der in der Suchabfragesyntax als *c:c* dargestellt wird) verbunden, der in der Funktionalität mit dem **AND-Operator** vergleichbar ist. Das bedeutet, dass Elemente sowohl die Schlüsselwortabfrage als auch eine oder mehrere Bedingungen erfüllen müssen, die in die Suchergebnisse eingeschlossen werden sollen. Auf diese Weise können die Suchergebnisse mithilfe von Bedingungen weiter eingegrenzt werden. Eine Liste und Beschreibung der Bedingungen, die Sie in einer Suchabfrage verwenden können, finden Sie im Abschnitt "Suchbedingungen" unter [Schlüsselwortabfragen und Suchbedingungen](keyword-queries-and-search-conditions.md#search-conditions).
