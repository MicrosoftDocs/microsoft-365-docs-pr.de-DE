---
title: Zuverlässigkeitseinblicke
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8ecc117b2bc6e7cec3dcf0470a6d3c61ad34adf0
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "39634032"
---
# <a name="reliability-insights"></a>Zuverlässigkeitseinblicke

In dieser Ansicht erhalten Sie eine Zusammenfassung der Integrität Ihrer verwalteten Geräte. Um Zuverlässigkeitsdaten anzuzeigen, wählen Sie die Registerkarte **Zuverlässigkeit** aus.


![Zuverlässigkeits Bereich](images/insights_reliability.png)

Der Abschnitt " **Zuverlässigkeit für alle Geräte** " bietet eine Schnellübersicht über die Integrität Ihrer Bereitstellung in den letzten 14 Tagen, indem er den Prozentsatz der als "fehlerfrei" erachteten Geräte und die durchschnittliche Zeit seit dem letzten gemeldeten Fehler meldet. 

 
Der Graph " **Zuverlässigkeit über Zeit** " auf der rechten Seite gibt die Anzahl der Geräte mit kritischen Fehlern und die Gesamtzahl der beobachteten kritischen Fehler im Laufe der Zeit an.

Im Abschnitt **häufigsten Probleme** werden bestimmte erkannte Probleme erläutert, die sich auf mindestens 5% der verwalteten Geräte auswirken. Zu den gemeldeten Details gehören:

- Der Typ des Problems
    - Anwendungsabstürze, bei denen eine APP nicht mehr funktioniert oder unerwartet angehalten wird
    - Anwendung hängt an, wobei eine Anwendung nicht mehr auf Eingabe reagiert
    - Kritische Fehler, die auftreten, wenn ein Problem bei Windows aufgetreten ist, von dem keine Wiederherstellung möglich ist
- Die Anzahl der Geräte, die von dem gleichen Problem betroffen sind.
- Der Prozentsatz der verwalteten Geräte, die die Zahl darstellt
- Die Gesamtanzahl der Vorkommen des jeweiligen Problems.
- Die Softwarekomponente, die als Ursache des Problems angezeigt wird
- Die Kategorie des erkannten Problems:
    - Browser (Edge, Chrome, IE)
    - Unbekannt (nicht-Microsoft-Komponenten)
    - Treiber (Audio, Grafik oder andere Treiber)
    - Produktivität (slack, G-Suites, Microsoft Office und seine Add-ons oder Erweiterungen, Teams)
    - Medien (Bild-, Musik-oder Video-apps
    - Sicherheit (Windows-Sicherheitskomponenten)
- Der aktuelle Status als von Microsoft verwaltete Desktop Vorgänge untersucht und korrigiert das Problem

