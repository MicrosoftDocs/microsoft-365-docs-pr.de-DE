---
title: Suchstatistiken in Advance eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Überprüfen Sie Ihre Suchergebnisse, indem Sie die Statistiken anzeigen, die nach dem Ausführen einer Sammlungssuche in Advanced eDiscovery.
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750776"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>Suchstatistiken in Advanced eDiscovery

Eine Möglichkeit, Ihre Suchergebnisse zu überprüfen, besteht in der Überprüfung der Statistiken um Ihre Ergebnisse, um sicherzustellen, dass sie ihren Erwartungen entsprechen. Wenn eine Suche abgeschlossen ist, werden im Flyout für Suchdetails umfassende Statistiken angezeigt:

- Anzahl und Volumen der von der Suche abgerufenen Elemente

- Anzahl und Volumen teilweise indizierter oder nicht indizierter Elemente, die in den Suchpositionen gefunden wurden

- Anzahl der durchsuchten Postfächer und Speicherorte.
Um detailliertere Statistiken anzuzeigen, klicken Sie im Flyout für Suchdetails auf "Statistik".

## <a name="summary-view"></a>Zusammenfassungsansicht

In der Zusammenfassungsansicht werden die Suchergebnisse nach Standorttyp aufgeschlüsselt angezeigt (z. B. Exchange). Für jeden Standorttyp sehen Sie:

- Anzahl der Speicherorte mit Elementen, die den Suchbedingungen entsprechen

- Anzahl der Elemente aus diesen Speicherorten, die den Suchbedingungen entsprechen

- Gesamtvolumen der Elemente, die den Suchbedingungen entsprechen.

## <a name="top-locations-view"></a>Ansicht "Top Locations"

In der Ansicht Top locations werden die einzelnen Speicherorte mit den meisten Übereinstimmungen angezeigt. Für jeden Standort werden sie sehen:

- Ortsname (z. B. SharePoint URL)

- Speicherorttyp

- Anzahl der Elemente, die den Suchbedingungen entsprechen

- Gesamtvolumen der Elemente, die den Suchbedingungen entsprechen.

## <a name="queries-view"></a>Ansicht "Abfragen"

Wenn Sie (c:s) Schlüsselwort- oder Schlüsselwortzeilen in Ihrer Abfrage verwendet haben, können Sie die Aufschlüsselung Ihrer Abfrage in der Abfrageansicht nach Standorttyp anzeigen. Für jeden Standorttyp sehen Sie:

- Teil: Diese Spalte hat entweder das Wort "Primary" oder "Keyword". "Primär" bedeutet, dass die Zeile Statistiken für die gesamte Abfrage enthält, während "Schlüsselwort" eine der Abfragekomponenten bedeutet.

- Query: die tatsächliche Abfragekomponente, auf die sich die Zeile bezieht. Wenn Part "Primary" ist, ist dies die gesamte Abfrage. Wenn Part "Keyword" war, wird hier eine der Abfragekomponenten angezeigt.
  
  - Wenn Sie alle Inhalte in Postfächern durchsuchen (indem Sie keine Schlüsselwörter angeben), ist die tatsächliche Abfrage (Größe >= 0), sodass alle Elemente zurückgegeben werden.
  
  - Wenn Sie nach SharePoint Online- und OneDrive for Business suchen, werden die beiden folgenden Komponenten hinzugefügt:
    
    - NOT IsExternalContent:1 – schließt inhalte aus einer lokalen Organisation SharePoint aus
    
    - NOT isOneNotePage: 1 – schließt alle OneNote aus, da es sich dabei um Duplikate eines Dokuments handelt, das der Suchabfrage entspricht.

- Anzahl der Speicherorte mit Elementen, die den Suchbedingungen entsprechen.

- Die Anzahl der Elemente aus diesen Speicherorten, die den Suchbedingungen entsprechen.

- Gesamtvolumen der Elemente, die den Suchbedingungen entsprechen.
