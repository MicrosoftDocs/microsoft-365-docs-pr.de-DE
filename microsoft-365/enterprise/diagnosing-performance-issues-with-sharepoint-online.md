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
description: In diesem Artikel erfahren Sie, wie Sie häufige Probleme mit Ihrer SharePoint Online-Website mithilfe von Internet Explorer-Entwicklertools diagnostizieren können.
ms.openlocfilehash: 6a29b8b2df54d74d8237418828a7aa89efdbcfaf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927612"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a>Diagnose von Leistungsproblemen mit SharePoint Online

In diesem Artikel erfahren Sie, wie Sie häufige Probleme mit Ihrer SharePoint Online-Website mithilfe von Internet Explorer-Entwicklertools diagnostizieren können.
  
Es gibt drei verschiedene Möglichkeiten, um zu erkennen, dass eine Seite auf einer SharePoint Onlinewebsite ein Leistungsproblem mit den Anpassungen hat.
  
- Der Netzwerkmonitor der F12-Toolleiste

- Vergleich mit einem nicht angepassten Basisplan

- SharePoint Metriken für Onlineantwortheader

In diesem Thema wird beschrieben, wie Sie mit jeder dieser Methoden Leistungsprobleme diagnostizieren. Nachdem Sie die Ursache des Problems gefunden haben, können Sie mithilfe der Artikel zur Verbesserung der SharePoint, die Sie finden, an einer Lösung https://aka.ms/tune arbeiten.
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a>Verwenden der F12-Toolleiste zum Diagnostizieren der Leistung in SharePoint Online
<a name="F12ToolInfo"> </a>

In diesem Artikel verwenden wir Internet Explorer 11. Versionen der F12-Entwicklertools in anderen Browsern verfügen über ähnliche Features, obwohl sie leicht unterschiedlich aussehen können. Informationen zu den F12-Entwicklertools finden Sie unter:
  
- [Neues in den F12-Tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))

- [Verwenden der F12-Entwicklertools](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))

Drücken Sie **F12,** um die Entwicklertools hoch zu bringen, und klicken Sie dann auf Wi-Fi Symbol:
  
![Screenshot des WLAN-Symbols für F12-Entwicklertools](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
Drücken Sie **auf der** Registerkarte Netzwerk die grüne Wiedergabeschaltfläche, um eine Seite zu laden. Das Tool gibt alle Dateien zurück, die der Browser anfordert, um die seite zu erhalten, nach der Sie gefragt haben. Der folgende Screenshot zeigt eine solche Liste.
  
![Screenshot der Liste der mit einer Seitenanforderung zurückgegebenen Dateien.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
Sie können auch die Downloadzeiten der Dateien auf der rechten Seite sehen, wie in diesem Screenshot gezeigt.
  
![Diagramm, das zeigt, wie lange das Laden der angeforderten Seiten aus dem SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
Dadurch erhalten Sie eine visuelle Darstellung der Ladezeit der Datei. Die grüne Linie gibt an, wann die Seite vom Browser gerendert werden kann. Dadurch erhalten Sie eine schnelle Ansicht der verschiedenen Dateien, die möglicherweise zu langsamen Seitenlasten auf Ihrer Website führen.
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a>Einrichten eines nicht angepassten Basisplans für SharePoint Online
<a name="F12ToolInfo"> </a>

Die beste Möglichkeit, die Leistungsschwächen Ihrer Website zu ermitteln, besteht in der Einrichtung einer vollständig out-of-the-box-Websitesammlung in SharePoint Online. Auf diese Weise können Sie alle verschiedenen Aspekte Ihrer Website mit dem vergleichen, was Sie ohne Anpassung auf der Seite erhalten würden. Die OneDrive for Business ist ein gutes Beispiel für eine separate Websitesammlung, die wahrscheinlich keine Anpassungen hat.
  
## <a name="viewing-sharepoint-response-header-information"></a>Anzeigen SharePoint Antwortkopfinformationen
<a name="F12ToolInfo"> </a>

In SharePoint Online können Sie auf die Informationen zugreifen, die im Antwortheader für jede Datei an den Browser gesendet werden. Der nützlichste Wert zum Diagnostizieren von Leistungsproblemen ist **SPRequestDuration**, der den Zeitraum anzeigt, den die Anforderung auf dem Server für die Verarbeitung in Sich nahm. Dadurch kann ermittelt werden, ob die Anforderung sehr schwer und ressourcenintensiv ist. Dies ist der beste Einblick, wie viel Arbeit der Server zum Bedienen der Seite macht.

### <a name="to-view-sharepoint-response-header-information"></a>So zeigen Sie SharePoint Antwortkopfinformationen an
  
1. Stellen Sie sicher, dass die F12-Tools installiert sind. Weitere Informationen zum Herunterladen und Installieren dieser Tools finden Sie unter [What's new in F12 tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85)).

2. Drücken Sie in den F12-Tools auf der Registerkarte **Netzwerk** die grüne Wiedergabeschaltfläche, um eine Seite zu laden.

3. Klicken Sie auf eine der vom Tool zurückgegebenen ASPX-Dateien, und klicken Sie dann auf **DETAILS**.

    ![Zeigt Details des Antwortheaders an](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. Klicken Sie **auf Antwortkopfzeilen**.

    ![Diagramm mit der URL des Antwortheaders](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a>Was verursacht Leistungsprobleme in SharePoint Online?
<a name="F12ToolInfo"> </a>

Der Artikel [Navigationsoptionen für SharePoint Online](navigation-options-for-sharepoint-online.md) zeigt ein Beispiel für die Verwendung des SPRequestDuration-Werts, um zu ermitteln, dass die komplizierte Strukturnavigation dazu führt, dass die Seite lange auf dem Server verarbeiten musste. Wenn Sie einen Wert für eine Basiswebsite (ohne Anpassung) verwenden, können Sie ermitteln, ob das Laden einer bestimmten Datei sehr viel Zeit in Sich nimmt. Das in [Navigationsoptionen für SharePoint Online](navigation-options-for-sharepoint-online.md) verwendete Beispiel ist die haupt-ASPX-Datei. Diese Datei enthält den großteil ASP.NET Code, der für das Laden der Seite ausgeführt wird. Je nach verwendeter Websitevorlage kann dies start.aspx, home.aspx, default.aspx oder ein anderer Name sein, wenn Sie die Startseite anpassen. Wenn diese Anzahl deutlich höher als Ihre Basiswebsite ist, ist dies ein guter Hinweis darauf, dass auf Ihrer Seite etwas komplexes vor sich geht, das Leistungsprobleme verursacht.
  
Nachdem Sie festgestellt haben, dass es sich um ein spezifisches Problem für Ihre Website handelt, empfiehlt es sich, herauszufinden, was zu einer leistungsärmeren Leistung führt, indem Sie alle möglichen Ursachen beseitigen, z. B. Seitenanpassungen, und diese dann der Website nach und nach hinzufügen. Nachdem Sie genügend Anpassungen entfernt haben, dass die Seite gut funktioniert, können Sie bestimmte Anpassungen nach und nach hinzufügen.
  
Wenn Sie beispielsweise über eine sehr komplexe Navigation verfügen, versuchen Sie, die Navigation so zu ändern, dass Keine Unterwebsites angezeigt werden, überprüfen Sie die Entwicklertools, um zu sehen, ob dies einen Unterschied macht. Oder wenn Sie über eine große Menge von Inhaltsrollups verfügen, versuchen Sie, sie von Ihrer Seite zu entfernen und zu sehen, ob dies die Dinge verbessert. Wenn Sie alle möglichen Ursachen eliminieren und sie in einem nach dem anderen hinzufügen, können Sie ganz einfach ermitteln, welche Features das größte Problem sind, und dann auf eine Lösung hinarbeiten.