---
title: Suchstatistiken
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
ms.openlocfilehash: c4ac15bcc83fcba7415eb37bccdac2904dcf5d6c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081950"
---
# <a name="search-statistics"></a>Suchstatistiken

Eine effektive Möglichkeit zum Überprüfen Ihrer Suchergebnisse bei der Untersuchung eines Daten Vorfalls besteht darin, die Statistiken zu Ihren Suchergebnissen anzuzeigen, um sicherzustellen, dass Sie Ihren Erwartungen entsprechen. Wenn eine Suche als abgeschlossen ausgeführt wird, werden die folgenden allgemeinen Statistiken unter **Status** auf der Flyout-Seite "Suchdetails" angezeigt:

![Statisics auf der Such Detail-Flyout-Seite suchen](media/SearchDetailsFlyout.png)

- Die geschätzte Anzahl und Größe der Elemente, die mit den Suchkriterien übereinstimmen.

- Anzahl und Größe der teilweise indizierten Elemente (auch als nicht indizierte *Elemente*bezeichnet), die nicht durchsuchbar sind, sondern in den Inhaltsspeicherorten gefunden wurden, die in die Suche einbezogen wurden.

- Die Anzahl der Postfächer und Websites, die durchsucht wurden.

Wenn Sie detailliertere Statistiken anzeigen möchten, klicken Sie auf der Flyout-Seite mit den Suchdetails auf **Statistik** . Auf der Seite **Suchstatistik** können Sie die Suchzusammenfassung, die erste Position mit Elementen, die mit den Suchergebnissen übereinstimmen, und detaillierte Statistiken zur Suchabfrage anzeigen.

![Dropdownliste "Suchstatistik"](media/SearchStatisticsDropDownList.png)

## <a name="summary"></a>Zusammenfassung

In der **Zusammenfassungs** Ansicht werden die Suchergebnisse nach Standorttypen aufgeschlüsselt angezeigt (beispielsweise Speicherorte wie Exchange-Postfächer und SharePoint-Websites). Die folgenden Informationen werden für jeden Location-Typ angezeigt:

- Die Anzahl der Speicherorte, an denen Elemente gefunden wurden, die den Suchkriterien entsprechen.

- Die Gesamtzahl der Elemente aus jedem Standorttyp, die mit den Suchkriterien übereinstimmen.

- Die Gesamtgröße der Elemente aus jedem Standorttyp, der mit den Suchkriterien übereinstimmt.

## <a name="top-locations"></a>Top-Standorte

In der Ansicht " **Top Locations** " werden die einzelnen inhaltsspeicherorte mit den meisten Elementen angezeigt, die mit den Suchkriterien übereinstimmen. Für jeden Inhaltsspeicherort werden die folgenden Informationen angezeigt:

- Der Name des Speicherorts; die e-Mail-Adresse für Postfächer und die URL für SharePoint-Websites

- Der Location-Typ

- Anzahl der Elemente, die mit den Suchkriterien übereinstimmen

- Die Gesamtgröße aller Elemente, die mit den Suchkriterien übereinstimmen.

## <a name="queries"></a>Abfragen

In der Ansicht **Abfragen** können Sie detaillierte Statistiken zu jeder Komponente der Suchabfrage anzeigen. Wenn Sie die Stichwortliste in der Suchabfrage verwendet haben, können Sie in der Ansicht **Abfragen** Erweiterte Statistiken anzeigen, in denen angezeigt wird, wie viele Elemente mit jedem Stichwort oder stichwortausdruck übereinstimmen. Auf diese Weise können Sie schnell erkennen, welche Teile der Abfrage am häufigsten (und am wenigsten) effektiv sind. 

Die folgenden Informationen werden in der Ansicht **Abfragen** angezeigt:

 - **Location Type** – der Typ des Inhaltsspeichers für die in der Zeile angezeigten Statistiken.

- **Part – in** dieser Spalte wird einer der folgenden Werte angezeigt: **Primary** oder **Keyword**. **Primäre** bedeutet, dass die Zeile Statistiken für die gesamte Abfrage enthält. **Schlüsselwort** bedeutet, dass die Statistik in der Zeile für eine der Abfragekomponenten gilt.

- **Condition** – die tatsächliche Abfragekomponente der Suchabfrage, auf die sich die Zeile bezieht. Wenn der Wert in der Spalte " **Part** " **primär**ist, werden die Statistiken für die gesamte Suchabfrage angezeigt; Wenn der Wert **Schlüsselwort**ist, werden die Statistiken für die in der **Abfrage** Spalte angezeigte Komponente der Abfrage angezeigt. Wenn beispielsweise die Stichwortliste verwendet wurde, wird die Statistik eines der Schlüsselwörter angezeigt.

  Hier sind einige andere Dinge, die Sie über die in der Spalte **Abfragen** angezeigte Statistik wissen sollten:
  
  - Wenn Sie nach allen Inhalten in Postfächern suchen (indem Sie keine Stichwörter angeben), lautet die tatsächliche Abfrage **(Size >= 0)** , sodass alle Elemente zurückgegeben werden.
  
  - Wenn Sie SharePoint-und OneDrive-Websites Durchsuchen, werden die beiden folgenden Komponenten zur Suchabfrage hinzugefügt:
    
    **Not IsExternalContent: 1** -Dies schließt jeglichen Inhalt aus einer lokalen SharePoint-Organisation aus
    
    **Not isOneNotePage: 1** -Dies schließt alle OneNote-Dateien aus, da es sich dabei um Duplikate eines Dokuments handeln würde, das mit der Suchabfrage übereinstimmt.

- **Standorte in der Suche** Die Anzahl der inhaltsspeicherorte mit Elementen, die mit der Suchabfrage für die in der Zeile angezeigte Komponente/Bedingung übereinstimmten. Beachten Sie, dass Archivpostfächer als separater Ort gezählt werden, wenn Sie Elemente enthalten, die den Suchkriterien entsprechen.

- **Items** – die Gesamtzahl der Elemente, die den Suchkriterien für die in der Zeile angezeigte Komponente/Bedingung entsprechen.

- **Size** – die Gesamtzahl der Elemente, die den Suchkriterien für die in der Zeile angezeigte Komponente/Bedingung entsprechen.

