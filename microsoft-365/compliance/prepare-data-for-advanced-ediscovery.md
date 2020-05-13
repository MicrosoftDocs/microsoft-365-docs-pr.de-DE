---
title: Vorbereiten von Daten für Advanced eDiscovery
f1.keywords:
- NOCSH
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
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: 'Erfahren Sie, wie Sie mithilfe des Security &amp; Compliance Center Daten für die Analyse mit Advanced eDiscovery vorbereiten. '
ms.openlocfilehash: 25b500e88e53dfae9b8fa9d504a402f4e2f7ce12
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208099"
---
# <a name="prepare-data-for-advanced-ediscovery-classic"></a>Vorbereiten von Daten für Advanced eDiscovery (klassisch)

In diesem Thema wird beschrieben, wie Sie die Ergebnisse einer Inhaltssuche in einen Fall in Advanced eDiscovery (Classic) laden. 
  
> [!IMPORTANT]
> Während wir weiterhin in neuere Versionen von Advanced eDiscovery investieren, kündigen wir jetzt die Deaktivierung von Advanced eDiscovery (auch bekannt als *Advanced eDiscovery (Classic)* oder *Advanced eDiscovery v1.0*) an. Wenn Sie noch mit Advanced eDiscovery v1.0 arbeiten, wechseln Sie so bald wie möglich zu [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (auch bekannt als *Advanced eDiscovery-Lösung in Microsoft 365*). Advanced eDiscovery 2.0 enthält ähnliche Funktionen wie Advanced eDiscovery v1.0, bietet aber auch viele neue Funktionen wie z. B. Verwahrerverwaltung, Kommunikationsverwaltung und Prüfungssätze. Um mehr über die Deaktivierung von Advanced eDiscovery v1.0 zu erfahren, siehe [Deaktivierung von veralteten eDiscovery-Tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).   
  
## <a name="step-1-prepare-data-for-advanced-ediscovery"></a>Schritt 1: Vorbereiten von Daten für erweiterte eDiscovery

Zum Analysieren von Daten mit Advanced eDiscovery können Sie die Ergebnisse einer Inhaltssuche verwenden, die Sie im Microsoft 365 Security &amp; Compliance Center (aufgeführt auf der Seite " **Inhaltssuche** " im Microsoft 365 Security &amp; Compliance Center) oder einer Suche im Zusammenhang mit einem eDiscovery-Fall (aufgeführt auf der Seite " **eDiscovery** " im Security &amp; Compliance Center) ausführen. 
  
Die detaillierten Schritte zum Vorbereiten von Suchergebnissen für die Analyse in Advanced eDiscovery finden Sie unter [Prepare Search results for Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).
  
> [!NOTE]
> Wenn Sie Daten außerhalb von Microsoft 365 haben und diese in Microsoft 365 importieren möchten, damit Sie Sie in Advanced eDiscovery vorbereiten und analysieren können, sehen Sie sich eine [Übersicht über das Importieren von PST-Dateien in Microsoft 365 und zum](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365) [Archivieren von drittanbieterdaten](https://go.microsoft.com/fwlink/p/?linkid=716918)an. 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>Schritt 2: Laden von Suchergebnis Daten in einen Fall in Advanced eDiscovery

Nachdem Sie die Suchergebnisse im Security &amp; Compliance Center für die Analyse vorbereitet haben, müssen Sie im nächsten Schritt die Suchergebnisse in einen Fall in Advanced eDiscovery laden. Ausführlichere Informationen finden Sie unter [Ausführen des Prozess Moduls](run-the-process-module-in-advanced-ediscovery.md).
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto an.
    
3. Klicken Sie im Security &amp; Compliance Center auf **Suche &amp; Untersuchung** \> **eDiscovery**, um die Liste der Fälle in Ihrem Unternehmen anzuzeigen. 
    
4. Klicken Sie neben dem Fall, in dem Sie Daten laden möchten in Advanced eDiscovery auf **Öffnen** . 
    
5. Klicken Sie auf der Seite **Start** für den Fall auf **Advanced eDiscovery**. 
    
    ![Klicken Sie auf zu Erweiterte eDiscovery wechseln, um die Anfrage in Advanced eDiscovery zu öffnen.](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Die **Verbindung mit der erweiterten eDiscovery** -Statusleiste wird angezeigt. Wenn Sie mit Advanced eDiscovery verbunden sind, wird auf der Seite Setup für den Fall eine Liste mit Containern angezeigt. 
    
    ![Der Fall wird in Advanced eDiscovery angezeigt.](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Diese Container stellen die Suchergebnisse dar, die Sie für die Analyse in Advanced eDiscovery in Schritt 1 vorbereitet haben. Beachten Sie, dass der Name des Containers denselben Namen hat wie die Inhaltssuche im Fall im Security &amp; Compliance Center. Die Container in der Liste sind diejenigen, die Sie vorbereitet haben. Wenn ein anderer Benutzer Suchergebnisse für Advanced eDiscovery vorbereitet hat, werden die entsprechenden Container nicht in die Liste aufgenommen. 
    
6. Wenn Sie die Suchergebnis Daten aus einem Container in den Fall in Advanced eDiscovery laden möchten, wählen Sie einen Container aus, und klicken Sie dann auf **verarbeiten**.
    
Nachdem die Suchergebnisse aus dem Security &amp; Compliance Center dem Fall in Advanced eDiscovery hinzugefügt wurden, besteht der nächste Schritt darin, die Tools in Advanced eDiscovery zu verwenden, um die für den Fall relevanten Daten zu analysieren und zu filtern. 
  
## <a name="see-also"></a>Siehe auch

[Advanced eDiscovery (Classic)](office-365-advanced-ediscovery.md)
  
[Einrichten von Benutzern und Fällen](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[Analysieren von Falldaten](analyze-case-data-with-advanced-ediscovery.md)
  
[Verwalten des Relevanz-Setups](manage-relevance-setup-in-advanced-ediscovery.md)
  
[Verwenden des Relevanzmoduls](use-relevance-in-advanced-ediscovery.md)
  
[Exportieren von Falldaten](export-case-data-in-advanced-ediscovery.md)

