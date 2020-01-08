---
title: Suchstatistiken
ms.author: markjjo
author: esclee
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
ms.openlocfilehash: fe4d1c92230bcc4e6e1136eeb43c99cc6d8297ca
ms.sourcegitcommit: af7950d9674f0eab3aee03f9afccff9ca2f4709a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971350"
---
# <a name="search-statistics"></a>Suchstatistiken

Eine Möglichkeit, Ihre Suchergebnisse zu validieren, besteht darin, die Statistiken rund um Ihre Ergebnisse zu prüfen, um sicherzustellen, dass Sie Ihren Erwartungen entsprechen. Wenn eine Suche abgeschlossen ist, werden allgemeine Statistiken im Flyout "Suchdetails" angezeigt:
- Anzahl und Umfang der von der Suche abgerufenen Elemente
- Anzahl und Volumen der teilweise indizierten/nicht indizierten Elemente, die in den Suchspeicherorten gefunden wurden
- Anzahl der durchsuchten Postfächer und Speicherorte.
Um detailliertere Statistiken anzuzeigen, klicken Sie im Flyout "Suchdetails" auf "Statistik".

## <a name="summary"></a>Zusammenfassung

In der Zusammenfassungsansicht werden die Suchergebnisse nach Speicherorttyp (beispielsweise Exchange) aufgeschlüsselt angezeigt. Für jeden Standorttyp können Sie Folgendes sehen:
- Anzahl von Speicherorten mit Elementen, die mit den Suchbedingungen übereinstimmen
- Anzahl der Elemente aus diesen Speicherorten, die den Suchbedingungen entsprechen
- Gesamtvolumen der Elemente, die den Suchbedingungen entsprechen.

## <a name="top-locations"></a>Top-Standorte

In der Ansicht "Top Locations" werden die einzelnen Standorte mit den meisten Übereinstimmungen angezeigt. Für jeden Standort wird Folgendes angezeigt:
- Speicherort Name (beispielsweise SharePoint-URL)
- Speicherorttyp
- Anzahl der Elemente, die mit den Suchbedingungen übereinstimmen
- Gesamtvolumen der Elemente, die den Suchbedingungen entsprechen.

## <a name="queries"></a>Abfragen

Wenn Sie (c:s) Schlüsselwort-oder Stichwort Zeilen in Ihrer Abfrage verwendet haben, können Sie den aufschlüsseln der Abfrage in der Ansicht Abfragen pro Standorttyp sehen. Für jeden Standorttyp werden die folgenden Aufgaben angezeigt:

- Part: in dieser Spalte wird entweder das Wort "Primary" oder "Keyword" angegeben. "Primary" bedeutet, dass die Zeile Statistiken für die gesamte Abfrage enthält, wobei "Stichwort" eine der Abfragekomponenten ist.

- Query: die tatsächliche Abfragekomponente, auf die sich die Zeile bezieht. Wenn Part "Primary" ist, handelt es sich um die gesamte Abfrage; Wenn Teil "Stichwort" war, wird eine der Abfragekomponenten hier angezeigt.
  
  - Wenn Sie alle Inhalts-Postfächer durchsuchen (indem Sie keine Stichwörter angeben), lautet die tatsächliche Abfrage (Size >= 0), sodass alle Elemente zurückgegeben werden.
  
  - Wenn Sie SharePoint Online-und OneDrive für Unternehmen-Websites Durchsuchen, werden die beiden folgenden Komponenten hinzugefügt:
    
    - Not IsExternalContent: 1 – schließt alle Inhalte einer lokalen SharePoint-Organisation aus
    
    - Not isOneNotePage: 1 – schließt alle OneNote-Dateien aus, da es sich dabei um Duplikate eines Dokuments handeln würde, das mit der Suchabfrage übereinstimmt.

- Die Anzahl der Speicherorte, an denen Elemente mit den Suchbedingungen übereinstimmen.

- Die Anzahl der Elemente aus diesen Speicherorten, die den Suchbedingungen entsprechen.

- Gesamtvolumen der Elemente, die den Suchbedingungen entsprechen.