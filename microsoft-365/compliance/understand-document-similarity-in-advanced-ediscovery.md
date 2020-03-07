---
title: Grundlegendes zur Ähnlichkeit von Dokumenten in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 'Lesen Sie, wie der Ähnlichkeitswert von Dokumenten, die minimale Ähnlichkeit zweier Dateien, die als nahe Duplikate betrachtet werden müssen, in Office 365 Advanced eDiscovery funktioniert. '
ms.openlocfilehash: e15eb119a569c7cd296f9d3546969848808652da
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557665"
---
# <a name="understand-document-similarity-in-advanced-ediscovery-classic"></a>Grundlegendes zur Ähnlichkeit von Dokumenten in Advanced eDiscovery (klassisch)

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In Advanced eDiscovery ist die Ähnlichkeit mit Dokumenten die minimale Ähnlichkeits Stufe, die erforderlich ist, damit zwei Dokumente als nahe Duplikate betrachtet werden.
  
> [!TIP]
> Für die meisten Geschäftsanwendungen empfiehlt es sich, einen Ähnlichkeitswert von 60%-75% zu verwenden. Bei sehr schlechter Qualität des optischen Zeichen Erkennungs Materials (Optical Character Recognition, OCR) können niedrigere ähnlichkeitswerte angewendet werden. 
  
> [!NOTE]
> Nachdem Sie für einen bestimmten Fall festgelegt und ausgeführt wurde, kann der Ähnlichkeitswert nicht geändert werden. 
  
In einem nahe gelegenen Duplikat (ND) können Dokumente mit einer Ähnlichkeits Ebene unterhalb des Schwellenwerts für die Ähnlichkeit vorhanden sein. Damit ein Dokument einer ND-Gruppe beitreten kann, muss mindestens ein Dokument im ND-Paket mit einer Ähnlichkeits Ebene vorhanden sein, die die Ähnlichkeit überschreitet. 
  
Angenommen, die Ähnlichkeit wird auf 80% festgelegt, Dokument F1 ähnelt dem Dokument F2 auf einer Ebene von 85%, und das Dokument F2 ähnelt dem Dokument F3 auf einer Ebene von 90%. 
  
Das Dokument F1 ähnelt jedoch möglicherweise dem Dokument F3 auf einer Ebene von nur 70%, die sich unterhalb des Schwellenwerts befindet. In diesem Beispiel werden jedoch alle Dokumente F1, F2 und F3 in dem ersten ND-festgelegt. Ähnlich haben wir unter Verwendung eines Ähnlichkeits Werts von 80% möglicherweise zwei Sätze erstellt, EquiSet-1 und EquiSet-2. EquiSet-1 enthält die Dokumente E1 und E2. Equiset-2 enthält die Dokumente F1, F2 und F3. 
  
Die Ähnlichkeits Grade werden wie folgt dargestellt:
  
![Dokument Ähnlichkeit](../media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
Es wird davon ausgegangen, dass ein anderes Dokument, x1, jetzt eingefügt wird. Die Ähnlichkeit zwischen x1 und E3 beträgt 87%. Ähnlich ist die Ähnlichkeit zwischen x1 und F1 92%. Dadurch werden EquiSet-1, EquiSet-2 und x1 nun zu einem ND-Paket zusammengefasst.
  
![Dokument Ähnlichkeit](../media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> Wenn zwei Dokumente einem ND-Satz zugewiesen werden, bleiben Sie in demselben ND-Satz zusammen, auch wenn dem Satz zusätzliche Dokumente hinzugefügt werden oder wenn die Sätze zusammengeführt werden. 
  
Nachdem Mengen zusammengeführt wurden, kann sich das Pivot-Dokument ändern, wenn einem Satz neue Dokumente hinzugefügt werden. 
  
## <a name="see-also"></a>Siehe auch

[Advanced eDiscovery (klassisch)](office-365-advanced-ediscovery.md)
  
[Festlegen von Analyseoptionen](set-analyze-options-in-advanced-ediscovery.md)
  
[Festlegen von Text ignorieren](set-ignore-text-in-advanced-ediscovery.md)
  
[Einstellungen für die erweiterte Analyse Einstellung](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Anzeigen von Analyseergebnissen](view-analyze-results-in-advanced-ediscovery.md)

