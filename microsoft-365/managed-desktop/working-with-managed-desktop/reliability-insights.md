---
title: Zuverlässigkeitseinblicke
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950342"
---
# <a name="reliability-insights"></a>Zuverlässigkeitseinblicke

Diese Ansicht enthält eine Integritätszusammenfassung Ihrer verwalteten Geräte. Wählen Sie zum Anzeigen von Zuverlässigkeitsdaten die Registerkarte **Zuverlässigkeit** aus.


![Zuverlässigkeitsbereich: Zuverlässigkeit auf allen Geräten in der oberen linken Ecke, Diagramm "Zuverlässigkeit über Zeit" in der oberen rechten Ecke, Tabelle mit den obersten Problemen unten. Hilfe- und Feedbackschaltflächen unten rechts.](../../media/insights_reliability.png)

Der  Abschnitt Zuverlässigkeit auf allen Geräten bietet eine kurze Integritätszusammenfassung Ihrer Bereitstellung in den letzten 14 Tagen, indem der Prozentsatz der Geräte gemeldet wird, die als "fehlerfrei" betrachtet werden, und den Mittelwert seit dem letzten gemeldeten Fehler. 

 
Das **Diagramm Zuverlässigkeit über die** Zeit auf der rechten Seite gibt die Anzahl der Geräte mit kritischen Fehlern und die Gesamtzahl der im Laufe der Zeit beobachteten kritischen Fehler an.

Im **Abschnitt Top issues** werden bestimmte erkannte Probleme beschrieben, die mindestens 5 % ihrer verwalteten Geräte betreffen. Zu den gemeldeten Details gehören:

- Der Typ des Problems
    - Anwendungsabstürze, bei denen eine App nicht mehr funktioniert oder unerwartet beendet wird
    - Anwendung hängt ab, wobei eine Anwendung nicht mehr auf Eingaben reagiert
    - Kritische Fehler, die auftreten, wenn windows ein Problem festgestellt hat, von dem es nicht wiederherstellen kann
- Die Anzahl der geräte, die vom gleichen Problem betroffen sind
- Der Prozentsatz der verwalteten Geräte, die zahl stellt
- Die Gesamtanzahl der Vorkommen des spezifischen Problems
- Die Softwarekomponente, die die Ursache des Problems zu sein scheint
- Die Kategorie des erkannten Problems:
    - Browser (Edge, Chrome, IE)
    - Unbekannt (Nicht-Microsoft-Komponenten)
    - Treiber (Audio, Grafik oder andere Treiber)
    - Produktivität (Slack, G-Suites, Microsoft Office und seine Add-Ons oder Erweiterungen, Teams)
    - Medien (Bild-, Musik- oder Video-Apps)
    - Sicherheit (Windows-Sicherheitskomponenten)
- Der aktuelle Status als Microsoft Managed Desktop Operations untersucht und be beheben das Problem

