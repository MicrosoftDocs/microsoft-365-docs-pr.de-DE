---
title: Vorbereiten von Daten für Office 365 Advanced eDiscovery
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
description: 'Erfahren Sie, wie Sie das Microsoft 365 &amp; Security Compliance Center verwenden, um Office 365 Daten für die Analyse mit Office 365 Advanced eDiscovery vorzubereiten. '
ms.openlocfilehash: 6407b6f2a2bbe9bc69842057232ec01569ef64c8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597762"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a>Vorbereiten von Daten für Office 365 Advanced eDiscovery

In diesem Thema wird beschrieben, wie Sie die Ergebnisse einer Inhaltssuche in einen Fall in Advanced eDiscovery laden. 
  
> [!IMPORTANT]
> Da wir weiterhin in neuere Versionen von Advanced eDiscovery investieren, kündigen wir den Ruhestand Office 365 Advanced eDiscovery (auch bekannt als *Advanced eDiscovery v 1.0*) an. Wenn Sie noch Advanced eDiscovery v 1.0 verwenden, wechseln Sie so bald wie möglich zu [Advanced eDiscovery v 2.0](overview-ediscovery-20.md) (auch als *Erweiterte eDiscovery-Lösung in Microsoft 365*bezeichnet). Advanced eDiscovery 2,0 enthält ähnliche Funktionen wie in Advanced eDiscovery v 1.0, bietet aber auch viele neue Features wie Depotverwaltung, Kommunikationsverwaltung und Überprüfungs Sätze. Weitere Informationen zum Ruhestand von Advanced eDiscovery v 1.0 finden Sie unter [Retirement of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).  
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a>Schritt 1: Vorbereiten Office 365 Daten für Advanced eDiscovery

Zum &amp; Analysieren von Daten mit Advanced eDiscovery können Sie die Ergebnisse einer Inhaltssuche verwenden, die Sie im Microsoft 365 Security Compliance Center (aufgeführt auf der Seite " **Inhaltssuche** " im Microsoft 365 Security &amp; Compliance Center) oder einer Suche im Zusammenhang mit einem eDiscovery-Fall (aufgeführt auf der Seite " **eDiscovery** " im Security &amp; Compliance Center) ausführen. 
  
Die detaillierten Schritte zum Vorbereiten von Suchergebnissen für die Analyse in Advanced eDiscovery finden Sie unter [Vorbereiten von Suchergebnissen für Office 365 Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).
  
> [!NOTE]
> Wenn Sie Daten außerhalb von Office 365 haben und in Office 365 importieren möchten, damit Sie Sie in Advanced eDiscovery vorbereiten und analysieren können, sehen Sie sich eine [Übersicht über das Importieren von PST-Dateien in Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) und [Archivieren von drittanbieterdaten in Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918)an. 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>Schritt 2: Laden von Suchergebnis Daten in einen Fall in Advanced eDiscovery

Nachdem Sie die Suchergebnisse im Security &amp; Compliance Center für die Analyse vorbereitet haben, müssen Sie im nächsten Schritt die Suchergebnisse in einen Fall in Advanced eDiscovery laden. Ausführlichere Informationen finden Sie unter [Ausführen des Prozess Moduls](run-the-process-module-in-advanced-ediscovery.md).
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto bei Office 365 an.
    
3. Klicken Sie im Security &amp; Compliance Center auf **Suche &amp; Untersuchung** \> **eDiscovery**, um die Liste der Fälle in Ihrem Unternehmen anzuzeigen. 
    
4. Klicken Sie neben dem Fall, in dem Sie Daten laden möchten in Advanced eDiscovery auf **Öffnen** . 
    
5. Klicken Sie auf der Seite **Start** für den Fall auf **Advanced eDiscovery**. 
    
    ![Klicken Sie auf zu Erweiterte eDiscovery wechseln, um die Anfrage in Advanced eDiscovery zu öffnen.](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Die **Verbindung mit der erweiterten eDiscovery** -Statusleiste wird angezeigt. Wenn Sie mit Advanced eDiscovery verbunden sind, wird auf der Seite Setup für den Fall eine Liste mit Containern angezeigt. 
    
    ![Der Fall wird in Advanced eDiscovery angezeigt.](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Diese Container stellen die Suchergebnisse dar, die Sie für die Analyse in Advanced eDiscovery in Schritt 1 vorbereitet haben. Beachten Sie, dass der Name des Containers denselben Namen hat wie die Inhaltssuche im Fall im Security &amp; Compliance Center. Die Container in der Liste sind diejenigen, die Sie vorbereitet haben. Wenn ein anderer Benutzer Suchergebnisse für Advanced eDiscovery vorbereitet hat, werden die entsprechenden Container nicht in die Liste aufgenommen. 
    
6. Wenn Sie die Suchergebnis Daten aus einem Container in den Fall in Advanced eDiscovery laden möchten, wählen Sie einen Container aus, und klicken Sie dann auf **verarbeiten**.
    
Nachdem die Suchergebnisse aus dem Security &amp; Compliance Center dem Fall in Advanced eDiscovery hinzugefügt wurden, besteht der nächste Schritt darin, die Tools in Advanced eDiscovery zu verwenden, um die für den Fall relevanten Daten zu analysieren und zu filtern. 
  
## <a name="see-also"></a>Siehe auch

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Einrichten von Benutzern und Fällen](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[Analysieren von Falldaten](analyze-case-data-with-advanced-ediscovery.md)
  
[Verwalten des Relevanz-Setups](manage-relevance-setup-in-advanced-ediscovery.md)
  
[Verwenden des Relevanzmoduls](use-relevance-in-advanced-ediscovery.md)
  
[Exportieren von Falldaten](export-case-data-in-advanced-ediscovery.md)

