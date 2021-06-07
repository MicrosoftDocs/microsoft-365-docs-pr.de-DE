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
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739783"
---
# <a name="reliability-insights"></a>Zuverlässigkeitseinblicke

In dieser Ansicht erhalten Sie eine Integritätszusammenfassung ihrer verwalteten Geräte. Wählen Sie zum Anzeigen von Zuverlässigkeitsdaten die Registerkarte **"Zuverlässigkeit"** aus.


![Zuverlässigkeitsbereich: Zuverlässigkeit auf allen Geräten oben links, Zuverlässigkeitsdiagramm im Zeitverlauf oben rechts, Tabelle mit den oberen Problemen unten. Hilfe- und Feedbackschaltflächen unten rechts.](../../media/insights_reliability.png)

Der Abschnitt **"Zuverlässigkeit geräteübergreifend"** bietet eine schnelle Integritätszusammenfassung ihrer Bereitstellung in den letzten 14 Tagen, indem der Prozentsatz der als "fehlerfrei" eingestuften Geräte und die seit dem letzten gemeldeten Fehler beobachtete Mittlere Zeit gemeldet wird. 

 
Das Diagramm **"Zuverlässigkeit im Zeitverlauf"** auf der rechten Seite meldet die Anzahl der Geräte mit kritischen Fehlern und die Gesamtzahl der beobachteten kritischen Fehler im Laufe der Zeit.

Im Abschnitt **"Häufigste Probleme"** werden bestimmte erkannte Probleme beschrieben, die sich auf mindestens 5 % Ihrer verwalteten Geräte auswirken. Zu den gemeldeten Details gehören:

- Der Typ des Problems
    - Anwendungsabstürze, bei denen eine App nicht mehr funktioniert oder unerwartet beendet wird
    - Anwendung hängt an, wo eine Anwendung nicht mehr auf Eingaben reagiert
    - Kritische Fehler, die auftreten, wenn Windows ein Problem aufgetreten ist, von dem es nicht wiederhergestellt werden kann
- Die Anzahl der Geräte, die von demselben Problem betroffen sind
- Der Prozentsatz der verwalteten Geräte, die diese Anzahl darstellt
- Die Gesamtanzahl der Vorkommen des spezifischen Problems
- Die Softwarekomponente, die die Ursache des Problems zu sein scheint
- Die Kategorie des erkannten Problems:
    - Browser (Edge, Chrome, IE)
    - Unbekannt (Nicht-Microsoft-Komponenten)
    - Treiber (Audio, Grafiken oder andere Treiber)
    - Produktivität (Slack, G-Suites, Microsoft Office und seine Add-Ons oder Erweiterungen Teams)
    - Medien (Bild-, Musik- oder Video-Apps
    - Sicherheitskomponenten (Windows)
- Der aktuelle Status als Microsoft Managed Desktop Vorgänge untersucht und behebt das Problem.

