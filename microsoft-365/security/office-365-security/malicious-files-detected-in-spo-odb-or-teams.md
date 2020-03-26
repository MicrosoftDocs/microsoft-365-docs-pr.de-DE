---
title: Anzeigen von Informationen zu bösartigen Dateien, die in SharePoint, OneDrive oder Microsoft Teams erkannt wurden
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wo Sie Informationen zu schädlichen Dateien anzeigen können, die in SharePoint, OneDrive oder Teams erkannt wurden, und wie Sie Aktionen für diese Dateien durchführen.
ms.openlocfilehash: 3a14c7d69c7081be6bd08840eb8f52c5e11d4be7
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955555"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>Anzeigen von Informationen zu bösartigen Dateien, die in SharePoint, OneDrive oder Microsoft Teams erkannt wurden

[Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md) schützt Ihre Organisation vor bösartigen Dateien in Dokumentbibliotheken und Teamwebsites. Wenn eine bösartige Datei erkannt wird, wird diese Datei blockiert, sodass niemand Sie öffnen, kopieren, weiterleiten oder freigeben kann, bis weitere Aktionen vom Sicherheitsteam der Organisation ausgeführt werden. In diesem Artikel erfahren Sie, wie Sie Informationen zu erkannten Dateien anzeigen und welche Aktionen ausgeführt werden. 

Damit Sie die in diesem Artikel beschriebenen Aufgaben ausführen können, müssen Sie über die erforderlichen [Berechtigungen für das Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)verfügen. 
  
## <a name="view-reports-with-information-about-detected-files"></a>Anzeigen von Berichten mit Informationen zu erkannten Dateien

Zum Anzeigen des Status und detaillierter Informationen zu Dateien, die von Office 365 ATP erkannt wurden, können Sie den Threat Protection-Statusbericht verwenden.
  
1. Wählen Sie im [Office 365 &amp; Security Compliance Center](https://protection.office.com)die Option **Reports** \> **Dashboard** \> **Threat Protection Status**aus.
    
2. Wählen Sie in der oberen rechten Ecke des Berichts die Option **Details-Tabelle anzeigen**aus.
    
3. Zeigt die Liste der Dateien an, die im Bericht erkannt wurden.
    
4. Wählen Sie ein Element in der Liste aus, um detaillierte Informationen anzuzeigen, einschließlich der ausgeführten Aktionen, des Datei namens, des Dateipfads und vieles mehr.
    
5. Klicken Sie auf die Registerkarte **Erweiterte Analyse** , um Informationen wie beobachtetes Verhalten und Analysedetails anzuzeigen. 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>Anzeigen und Ausführen von Aktionen für Dateien in der Quarantäne

1. Wählen Sie im Office 365 &amp; Security Compliance Center die Option **Threat Management** \> **Review** \> **Quarantine**aus. (Sie können auch direkt zu [https://protection.office.com/quarantine](https://protection.office.com/quarantine)wechseln.)
    
2. Ändern Sie in der oberen linken Ecke das Dropdownmenü von **e-Mails** in **Dateien**. Wenn die Liste der Ergebnisse zu viele Elemente enthält, verwenden Sie die **Filter** Funktionalität, um die Auswahl einzuschränken.
    
3. Wählen Sie ein Element in der Liste aus, um detaillierte Informationen anzuzeigen, einschließlich der URL der Datei.
    
4. Wählen Sie eine verfügbare Aktion aus.
    
    - Wählen Sie **Datei freigeben** aus, um die Datei zu entsperren. 

      Wählen Sie **Bericht an Microsoft senden** aus, um die Datei als falsch positiv an Microsoft zu melden. 

    - Wählen Sie **Datei herunterladen** aus, um die Datei weiter zu untersuchen. 

    - Wählen Sie **aus Quarantäne entfernen** aus, um die Datei aus der Liste der isolierten Elemente zu entfernen. Wenn Sie diese Option auswählen, müssen Sie die Datei auch in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams aus der entsprechenden Bibliothek löschen. Mit dieser Option wird das Öffnen oder Freigeben einer Datei nicht aufgehoben. 
    
5. Wählen Sie **Schließen** aus, um die Details für ein ausgewähltes Element zu schließen. 
  
  

