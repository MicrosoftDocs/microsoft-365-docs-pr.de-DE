---
title: Festlegen von erweiterten Einstellungen für die Analyse in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: 'In diesem Artikel erfahren Sie, wie Sie erweiterte Einstellungen, einschließlich nahe Duplikate, e-Mail-Threads und Designs, für den Analyseprozess in Office 365 Advanced eDiscovery konfigurieren. '
ms.openlocfilehash: 06ee57542bfdb87b8bea77b3e4271adf02490046
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802818"
---
# <a name="set-analyze-advanced-settings-in-office-365-advanced-ediscovery"></a>Festlegen von erweiterten Einstellungen für die Analyse in Office 365 Advanced eDiscovery

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Advanced eDiscovery bietet standardmäßig erweiterte Parameter für Analysemodul Einstellungen. Im folgenden Verfahren werden die Einstellungen beschrieben, die angegeben werden können.
  
1. Klicken Sie auf der Registerkarte **analyze \> \> -Setup vorbereiten** auf **Erweiterte Einstellungen** (unten auf der Seite). Der folgende Bereich wird angezeigt. 
    
    ![Erweiterte Einstellungen für ANALYZE festlegen](media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. Wählen Sie im **Parameter near-Duplicates und e-Mail-Threads**nach Bedarf Werte für Folgendes aus:
    
  - **Minimale Anzahl von Wörtern**: Mindestanzahl für Wörter, unterhalb derer eine Datei nicht für die nahe duplizierte Analyse übermittelt wird. 
    
  - **Maximale Anzahl von Wörtern**: maximale Anzahl von Wörtern, über der eine Datei nicht für die nahe duplizierte Analyse übermittelt wird.
    
  - **E-Mail-Ähnlichkeit**: minimale Ähnlichkeits Ebene, damit zwei e-Mails als ähnlich betrachtet werden. Der Wert ist immer gleich oder größer als die Ähnlichkeit des Dokuments. Der Standardwert ist 90%.
    
3. Aktivieren Sie unter **Designs-Parameter**das Kontrollkästchen **Zahlen in Design Analyse einbeziehen** , um während der Analyse Zahlen in die Verarbeitung von Designs einzubeziehen. 
    
4. Klicken Sie auf **Speichern**. 
    
## <a name="see-also"></a>Siehe auch

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Grundlegendes zur Dokument Ähnlichkeit](understand-document-similarity-in-advanced-ediscovery.md)
  
[Festlegen von Analyseoptionen](set-analyze-options-in-advanced-ediscovery.md)
  
[Festlegen von Text ignorieren](set-ignore-text-in-advanced-ediscovery.md)
  
[Anzeigen von Analyseergebnissen](view-analyze-results-in-advanced-ediscovery.md)

