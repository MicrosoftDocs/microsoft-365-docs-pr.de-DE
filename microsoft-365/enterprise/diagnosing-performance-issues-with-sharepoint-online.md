---
title: Diagnose von Leistungsproblemen mit SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: In diesem Artikel erfahren Sie, wie Sie häufig auftretende Probleme mit Ihrer SharePoint Online Website mithilfe Internet Explorer Entwicklertools diagnostizieren können.
ms.openlocfilehash: a8a79afd860006a16874370b1124696550dab029
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690514"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a>Diagnose von Leistungsproblemen mit SharePoint Online

In diesem Artikel erfahren Sie, wie Sie häufig auftretende Probleme mit Ihrer SharePoint Online Website mithilfe Internet Explorer Entwicklertools diagnostizieren können.
  
Es gibt drei verschiedene Möglichkeiten, um festzustellen, ob eine Seite auf einer SharePoint Online Website ein Leistungsproblem mit den Anpassungen aufweist.
  
- Die F12-Toolleiste Netzwerkmonitor

- Vergleich mit einer nicht angepassten Baseline

- Metriken für SharePoint Online Antwortheader

In diesem Thema wird beschrieben, wie Sie diese Methoden zum Diagnostizieren von Leistungsproblemen verwenden. Nachdem Sie die Ursache des Problems herausgefunden haben, können Sie mit den Artikeln zur Verbesserung der SharePoint-Leistung, die Sie finden können, auf eine Lösung hinarbeiten https://aka.ms/tune .
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a>Diagnostizieren der Leistung in SharePoint Online mithilfe der F12-Symbolleiste
<a name="F12ToolInfo"> </a>

In diesem Artikel verwenden wir Internet Explorer 11. Versionen der F12-Entwicklertools in anderen Browsern weisen ähnliche Features auf, die sich jedoch möglicherweise geringfügig unterscheiden. Informationen zu den F12-Entwicklertools finden Sie unter:
  
- [Neuerungen in F12-Tools](https://go.microsoft.com/fwlink/p/?LinkId=522545)

- [Verwenden der F12-Entwicklertools](https://go.microsoft.com/fwlink/p/?LinkId=522546)

Drücken Sie **F12** , um die Entwicklertools aufzurufen, und klicken Sie dann auf das Symbol WLAN:
  
![Screenshot von F12 Developer Tools WiFi-Symbol](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
Drücken Sie auf der Registerkarte **Netzwerk** die grüne Wiedergabe-Schaltfläche, um eine Seite zu laden. Das Tool gibt alle Dateien zurück, die der Browser anfordert, um die von Ihnen gewünschte Seite abzurufen. Der folgende Screenshot zeigt eine solche Liste.
  
![Screenshot der Liste der Dateien, die mit einer Seitenanforderung zurückgegeben werden.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
Sie können auch die Downloadzeiten der Dateien auf der rechten Seite sehen, wie in diesem Screenshot gezeigt.
  
![Diagramm mit der Zeit, die zum Laden der angeforderten Seiten aus SharePoint benötigt wird](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
Dadurch erhalten Sie eine visuelle Darstellung der Dauer der Datei zum Laden. Die grüne Leiste stellt dar, wann die Seite für den Browser gerendert werden kann. Dadurch erhalten Sie einen schnellen Überblick über die verschiedenen Dateien, die zu langsamen Seitenlasten auf Ihrer Website führen könnten.
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a>Einrichten einer nicht angepassten Baseline für SharePoint Online
<a name="F12ToolInfo"> </a>

Die beste Möglichkeit, die Leistung Schwachstellen Ihrer Website zu ermitteln, besteht darin, eine vollständig vordefinierte Websitesammlung in SharePoint Online einzurichten. Auf diese Weise können Sie alle verschiedenen Aspekte Ihrer Website mit dem vergleichen, was Sie ohne Anpassung auf der Seite erhalten würden. Die OneDrive für Unternehmen Homepage ist ein gutes Beispiel für eine separate Websitesammlung, die wahrscheinlich keine Anpassungen aufweist.
  
## <a name="viewing-sharepoint-response-header-information"></a>Anzeigen von SharePoint-Antwortheader Informationen
<a name="F12ToolInfo"> </a>

In SharePoint Online können Sie auf die Informationen zugreifen, die in der Antwort Kopfzeile für jede Datei an den Browser zurückgesendet werden. Der nützlichste Wert für die Diagnose von Leistungsproblemen ist **SPRequestDuration**, mit dem die Zeitdauer angezeigt wird, die die Anforderung auf dem zu verarbeitenden Server benötigt. Dies kann helfen, festzustellen, ob die Anforderung sehr schwer ist und ressourcenintensiv ist. Dies ist die beste Einblicke in die Arbeit, die der Server für die Bereitstellung der Seite leistet.

### <a name="to-view-sharepoint-response-header-information"></a>So zeigen Sie Informationen zum SharePoint-Antwortheader an
  
1. Stellen Sie sicher, dass die F12-Tools installiert sind. Weitere Informationen zum herunterladen und Installieren dieser Tools finden Sie unter [What es New in F12 Tools](https://go.microsoft.com/fwlink/p/?LinkId=522545).

2. Drücken Sie in den F12-Tools auf der Registerkarte **Netzwerk** die grüne Wiedergabe-Schaltfläche, um eine Seite zu laden.

3. Klicken Sie auf eine der ASPX-Dateien, die vom Tool zurückgegeben werden, und klicken Sie dann auf **Details**.

    ![Zeigt Details des Antwortheaders an.](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. Klicken Sie auf **Antwortheader**.

    ![Diagramm mit der URL des Antwortheaders](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a>Was verursacht Leistungsprobleme in SharePoint Online?
<a name="F12ToolInfo"> </a>

Die Artikel [Navigationsoptionen für SharePoint Online](navigation-options-for-sharepoint-online.md) zeigen ein Beispiel für die Verwendung des SPRequestDuration-Werts, um festzustellen, ob die komplizierte strukturelle Navigation dazu führte, dass die Verarbeitung auf dem Server auf der Seite lange dauert. Durch die Verwendung eines Werts für eine Baseline-Website (ohne Anpassung) können Sie ermitteln, ob eine bestimmte Datei viel Zeit zum Laden braucht. Das Beispiel, das in [Navigationsoptionen für SharePoint Online](navigation-options-for-sharepoint-online.md) verwendet wird, ist die Datei "Main. aspx". Diese Datei enthält die meisten ASP.NET-Code, der für die Seiten Lade ausgeführt wird. Je nach verwendeter Websitevorlage kann dies "Start. aspx", "Home. aspx", "default. aspx" oder ein anderer Name sein, wenn Sie die Homepage anpassen. Wenn diese Zahl erheblich höher ist als die Baseline-Website, ist dies ein guter Hinweis darauf, dass in Ihrer Seite ein Komplex vorgeht, der Leistungsprobleme verursacht.
  
Nachdem Sie festgestellt haben, dass es sich um ein für Ihre Website spezifisches Problem handelt, ist die empfohlene Vorgehensweise, um herauszufinden, was eine schlechte Leistung verursacht, darin, alle möglichen Ursachen wie Seiten Anpassungen zu beseitigen und Sie dann nacheinander wieder der Website hinzuzufügen. Nachdem Sie genügend Anpassungen entfernt haben, die die Seite gut ausführt, können Sie einzelne Anpassungen nacheinander hinzufügen.
  
Wenn Sie beispielsweise eine sehr komplexe Navigation haben, versuchen Sie, die Navigation so zu ändern, dass Unterwebsites nicht angezeigt werden, und überprüfen Sie die Entwicklertools, um zu sehen, ob dies einen Unterschied macht. Oder wenn Sie eine große Menge an Inhalts-Roll-ups haben, versuchen Sie, diese von Ihrer Seite zu entfernen und zu sehen, ob dies die Dinge verbessert. Wenn Sie alle möglichen Ursachen beseitigen und gleichzeitig wieder hinzufügen, können Sie ganz einfach ermitteln, welche Funktionen das größte Problem darstellen, und dann auf eine Lösung hinarbeiten.
