---
title: Ende der Unterstützung für PerformancePoint Server 2007 – Roadmap
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- PSV120
- PDD140
- MET150
ms.assetid: 89d9feee-2285-419c-8c14-0f7f583536e0
f1.keywords:
- NOCSH
description: PerformancePoint Server 2007 haben ProClarity und SharePoint Server 2007 das Ende der Unterstützung erreicht. Lesen Sie diesen Artikel, um Das Upgrade Ihrer BI-Lösung zu planen.
ms.openlocfilehash: aa6adae24d78b6be72f17fd56c272b1293e6fcdc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927336"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>Ende der Unterstützung für PerformancePoint Server 2007 – Roadmap

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Office 2007-Server und -Anwendungen haben ihr Ende der Unterstützung erreicht, einschließlich Server und Anwendungen, die Sie möglicherweise als Teil Ihrer Business Intelligence (BI)-Lösungen verwenden. In der folgenden Tabelle sind die betroffenen BI-Anwendungen aufgeführt:
  
|**Microsoft BI-Anwendungen**|**Datum, an dem die Unterstützung beendet wurde**|
|:-----|:-----|
|ProClarity Analytics Server 6.3 Service Pack 3  <br/> ProClarity Desktop Professional 6.3  <br/> ProClarity SharePoint Viewer 6.3  <br/> |11. Juli 2017  <br/> |
|SharePoint Server 2007 Service Pack 3  <br/> |10. Oktober 2017  <br/> |
|PerformancePoint Server 2007 Service Pack 3  <br/> |09. Januar 2018  <br/> |
   
Weitere Informationen finden Sie unter [Resources to help you upgrade from Office 2007 servers and clients](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>Was bedeutet *das Ende der Unterstützung?*

Wie die meisten #A0 verfügen PerformancePoint Server 2007 SP3, ProClarity-Software und SharePoint Server 2007 SP3 über einen Supportlebenszyklus, in dem Microsoft neue Features, Fehlerbehebungen und Sicherheitsupdates bietet. Der Lebenszyklus für ein Produkt dauert in der Regel 10 Jahre nach der ersten Produktversion. Das Ende dieses Lebenszyklus wird als Ende des Support für das Produkt bezeichnet. Da ProClarity, PerformancePoint Server und SharePoint Server 2007 ihr Ende der Unterstützung erreicht haben, bietet Microsoft nicht mehr:
  
- Technischer Support für Probleme, die auftreten können.
    
- Fehlerbehebungen für probleme, die erkannt werden und die sich auf die Stabilität und Benutzerfreundlichkeit von Servern auswirken können.
    
- Sicherheitsbehebungen für gefundene Sicherheitsrisiken, die Server oder Anwendungen anfällig für Sicherheitsverletzungen machen können.
    
- Zeitzonenupdates.
    
Ihre Installation von ProClarity, SharePoint Server 2007 SP3 und PerformancePoint Server 2007 SP3 wird weiterhin ausgeführt, obwohl die Unterstützung beendet wurde. Es wird jedoch dringend empfohlen, so bald wie möglich von diesen Anwendungen zu migrieren.
  
## <a name="what-are-my-options"></a>Was sind meine Optionen?

Seit 2007 wurden zahlreiche Änderungen an Microsoft BI-Anwendungen vorgenommen, und Sie haben mehrere Optionen zu berücksichtigen, wie in der folgenden Tabelle zusammengefasst.
  
|**Wenn Sie dies verwendet haben ...**|**Entdecken Sie diese Optionen ...**|**Beachten Sie dies ...**|
|:-----|:-----|:-----|
| PerformancePoint Server 2007 Monitoring &amp; Analytics-Funktionen, einschließlich:<br/>- PerformancePoint Monitoring Server <br/>- PerformancePoint Dashboard Designer<br/>– Dashboardanzeige für SharePoint Services (wird zum Rendern von PerformancePoint-Dashboards, Scorecards und Berichten verwendet)<br/> |**Excel mit Excel in einem Browser** (in der Cloud oder lokal). Eine Übersicht finden Sie unter [BI-Funktionen in Excel und Microsoft 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx).<br/><br/> **Power BI** (in der Cloud oder lokal). Eine Übersicht finden Sie unter [Was ist Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting Services** (lokal). Eine Übersicht finden Sie unter [SQL Server Reporting Services (SSRS): Erstellen, Bereitstellen](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)und Verwalten mobiler und paginierter Berichte . <br/><br/> **PerformancePoint-Dienste** (lokal). Eine Übersicht finden Sie unter [What's new for PerformancePoint-Dienste (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14)). <br/> |Excel ist als online (cloudbasierte) oder lokale Lösung verfügbar. Viele Berichts- und Dashboardanforderungen können mit Excel erfüllt werden.  <br/><br/> Power BI ist als Online- oder lokale Lösung verfügbar. Power BI ist nicht in Microsoft 365 enthalten. Sie können power BI jedoch kostenlos verwenden. Je nach Ihren Datennutzungs- und Geschäftsanforderungen können Sie später ein Upgrade auf Power BI Pro mit Microsoft 365 E5 durchführen.<br/> <br/> Reporting Services und PerformancePoint-Dienste sind beide lokale Lösungen. <br/><br/> PerformancePoint-Dienste ist in SharePoint Server 2010, SharePoint Server 2013 und SharePoint Server 2016 verfügbar. <br/> <br/> Einige Features und Berichtstypen, die in PerformancePoint Server 2007 verfügbar waren, sind in Excel, Power BI, Reporting Services oder PerformancePoint-Dienste. Überprüfen Sie die verfügbaren Features, um die beste Lösung für Ihre Geschäftlichen Anforderungen zu ermitteln. <br/> |
| ProClarity-Software, einschließlich:<br/>- ProClarity Desktop Professional<br/> – ProClarity Analytics Server<br/>- ProClarity SharePoint Viewer<br/> |**Arbeiten Sie mit einem Microsoft-Partner zusammen,** um eine Lösung zu ermitteln, die Ihren Anforderungen am besten entspricht. Besuchen Sie [das Microsoft Partner Center](https://go.microsoft.com/fwlink/?linkid=841249). <br/><br/> Sie können auch die Verwendung von Excel mit Excel in einem Browser, Power BI, SQL Server Reporting Services oder PerformancePoint-Dienste.  <br/> |Mehrere, aber nicht alle Features der ProClarity-Software sind in anderen Microsoft-Angeboten verfügbar, einschließlich Excel, Power BI, Reporting Services und PerformancePoint-Dienste.  <br/> |
|SharePoint Server 2007-KPIs (auch MOSS-KPIs genannt)  <br/> |**Excel mit Excel Services**. Eine Übersicht finden Sie [unter Business Intelligence in Excel and Excel Services (SharePoint Server 2013)](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx). <br/> |MOSS-KPIs, die mit SharePoint Server 2007 erstellt wurden, können in SharePoint Server 2010, SharePoint Server 2013 und SharePoint Server 2016 verwendet werden. Sie können jedoch keine neuen MOSS-KPIs erstellen.  <br/> |
|Excel 2007  <br/> |**Excel** (in der Cloud oder lokal). Eine Übersicht finden Sie unter [BI-Funktionen in Excel und Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx). <br/><br/> **Power BI** (in der Cloud oder lokal). Eine Übersicht finden Sie unter [Was ist Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |Sowohl Excel als auch Power BI bieten Ihrer Organisation cloudbasierte und lokale Lösungen mit Unterstützung für eine Vielzahl von Datenquellen.  <br/> |
   
### <a name="help-selecting-a-solution"></a>Hilfe beim Auswählen einer Lösung

Bei so vielen verfügbaren BI-Auswahlmöglichkeiten scheint es überwältigend zu sein, zu bestimmen, welche Option am besten ist. Wir haben eine Onlineanleitung zur Verfügung. Weitere [Informationen finden Sie unter Auswählen von Microsoft Business Intelligence (BI)-Tools für Analyse und Berichterstellung.](/sql/reporting-services/choosing-microsoft-business-intelligence-bi-tools-for-analysis-and-reporting)
  
### <a name="what-if-i-dont-upgrade-now"></a>Was passiert, wenn ich jetzt kein Upgrade durchführen kann?

Sie können das Upgrade nicht sofort durchführen. Ihre vorhandenen Server und Anwendungen werden weiterhin ausgeführt. Sie erhalten jedoch keine weiteren Updates, einschließlich Sicherheitsupdates, da die Unterstützung beendet wurde. Und wenn bei Ihren Serveranwendungen etwas schief geht, können Sie keine Hilfe vom technischen Support von Microsoft erhalten.
  
## <a name="how-do-i-plan-my-upgrade"></a>Wie plane ich mein Upgrade?

Nachdem Sie ihre Upgradeoptionen untersucht haben, besteht der nächste Schritt in der Vorbereitung eines Upgradeplans. Die folgenden Abschnitte enthalten Informationen und zusätzliche Ressourcen zur Unterstützung. Sie haben vier Hauptoptionen, darunter zwei, die sowohl in der Cloud als auch lokal funktionieren, und zwei, die nur lokal sind:
  
|**Option**|**In der Cloud oder lokal?**|
|:-----|:-----|
|[Excel mit SharePoint Server (lokal)](#excel-with-sharepoint-server-on-premises) <br/> |In beide Richtungen  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |In beide Richtungen  <br/> |
|[Reporting Services](#use-reporting-services-on-premises) <br/> |Nur lokal  <br/> |
|[PerformancePoint Services](#use-performancepoint-services-on-premises) <br/> |Nur lokal  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>Verwenden von Excel (in der Cloud oder lokal)

Mit Excel, das auch als *Excel Services* in SharePoint Server bezeichnet wird, können Sie Arbeitsmappen in einem Browserfenster anzeigen und verwenden, auch wenn Excel nicht auf dem Computer installiert ist. Sie können Excel zum Erstellen von Berichten, Scorecards und Dashboards verwenden. Teilen Sie Dann Ihre Arbeitsmappen mit anderen Personen, die Excel in einem Browser verwenden können, unabhängig davon, ob sie SharePoint Online als Teil von Microsoft 365 oder SharePoint Server lokal verwenden. Sie können lokal oder in der Cloud gespeicherte Daten verwenden, wodurch Sie eine Vielzahl von Datenquellen verwenden können.
  
In der folgenden Tabelle werden die wichtigsten Vorteile der Verwendung von Excel mit Microsoft 365 mit der Verwendung von Excel mit SharePoint Server verglichen. Weitere Informationen folgen.
  
|**Excel mit Microsoft 365 (in der Cloud)**|**Excel mit SharePoint Server (lokal)**|
|:-----|:-----|
|**Sie erhalten die neueste, beste Version von Excel**. Mit Microsoft 365 erhalten Sie die neueste Version von Excel, die leistungsstarke neue Diagrammtypen, die Möglichkeit zum schnellen und einfachen Erstellen von Diagrammen und Tabellen sowie unterstützung für weitere Datenquellen umfasst. <br/> <br/> **Das Setup ist wesentlich einfacher.** Excel ist in Microsoft 365 Business enthalten, sodass Es keine großen Hebesätze gibt. Melden Sie sich an und melden Sie sich an, und Sie werden schneller und effizienter ausgeführt als beim Upgrade Ihrer lokalen Server. <br/> <br/> **Personen haben überall Zugriff auf ihre Arbeitsmappen.** Benutzer können Arbeitsmappen sicher von überall aus anzeigen, indem sie ihren Computer, Ihr Smartphone und ihr Tablet verwenden. <br/> <br/> **Es gibt mehr!** Weitere [Informationen finden Sie unter BI-Funktionen in Excel und Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx). <br/> |**Sie verwalten Ihre globalen Einstellungen**. Als SharePoint-Administrator können Sie globale Einstellungen angeben, z. B. Sicherheit, Lastenausgleich, Sitzungsverwaltung, Zwischenspeichern von Arbeitsmappen und externe Datenverbindungen. <br/> <br/> **Sie können Excel Services mit PerformancePoint-Dienste.** Sie können Excel Services und PerformancePoint-Dienste als Teil Ihrer SharePoint Server-Installation konfigurieren und Excel Services-Berichte in Ihre PerformancePoint-Dashboards hinzufügen. <br/> <br/> **Es gibt mehr!** Weitere [Informationen finden Sie unter Business Intelligence in Excel and Excel Services (SharePoint Server 2013).](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>Excel mit Microsoft 365 (in der Cloud)

Wenn Sie zu Microsoft 365 wechseln, verfügen Sie über die neuesten Dienste und Anwendungen, einschließlich Excel 2016. PerformancePoint-Dienste in Microsoft 365 nicht verfügbar ist, ersetzen Sie daher Ihre PerformancePoint-Dashboardinhalte durch Excel-Arbeitsmappen oder andere Berichte. Die gute Nachricht ist, dass Excel 2016 viele neue Diagrammtypen bietet, und es ist einfacher denn je, beeindruckende Dashboards in Excel zu erstellen. Und neue Features werden regelmäßig hinzugefügt. Weitere Informationen finden Sie unter [What's New in Excel 2016 for Windows](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx).
  
Wenn Sie außerdem 50 Oder mehr Von Microsoft 365-Plätzen erwerben, kann Ihnen das Microsoft FastTrack-Team bei der Einrichtung helfen. Weitere Informationen finden Sie unter [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365).
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>Excel mit SharePoint Server (lokal)

Wenn Sie ein Upgrade auf eine neuere Version von SharePoint durchführen, können Sie Excel mit Excel Services oder in einem Browser wie folgt verwenden:
  
- Excel Services in SharePoint Server 2010
    
- Excel Services in SharePoint Server 2013
    
- Excel, das Teil von Office Online Server ist, separat von SharePoint Server 2016 installiert
    
Sie können PerformancePoint-Dienste auch in Ihrer neuen Version von SharePoint Server konfigurieren und diese zusammen mit Excel verwenden.
  
Weitere Informationen zu Ihren SharePoint-Upgradeoptionen finden Sie unter [SharePoint Server 2007 End of Support Roadmap](sharepoint-2007-end-of-support.md).
  
Weitere Informationen zu Excel Services finden Sie unter [Excel Services overview (SharePoint Server 2010).](/previous-versions/office/sharepoint-server-2010/ee424405(v=office.14))
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>Verwenden von Power BI (in der Cloud oder lokal)

Power BI ist eine Suite von Business Analytics-Tools, um Daten zu analysieren und Einblicke zu teilen. Mit Power BI können Sie lokale oder Onlinedatenquellen verwenden, um interaktive Berichte und Dashboards zu erstellen. Benutzer können Ihre Berichte und Dashboards auf ihren Computern oder mobilen Geräten anzeigen und verwenden.
  
Power BI ist nicht Teil von Microsoft 365 oder SharePoint Server. Es ist ein separates Angebot, das Power BI Desktop, Power BI-Gateways und den Power BI-Dienst umfasst. Power BI kann auch in SharePoint Online integriert werden. Sie können kostenlos mit Power BI beginnen. Basierend auf Ihren Datennutzungs- und Geschäftsanforderungen können Sie später ein Upgrade auf Power BI Pro mit Microsoft 365 E5 durchführen. Weitere Informationen finden Sie unter [Was ist Power BI?](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>Verwenden von Reporting Services (lokal)

SQL Server Reporting Services bietet eine robuste Berichtslösung. Sie können Reporting Services entweder im systemeigenen oder im sharePoint-integrierten Modus konfigurieren. Sie können verschiedene Tools zum Erstellen von Berichten verwenden, z. B. Berichts-Designer, Berichts-Generator und Power View. Mit der neuesten Version von SQL Server können Sie auch SQL Server Mobile Report Publisher verwenden, um Berichte zu liefern, die auf eine beliebige Bildschirmgröße skaliert werden. Dadurch können Benutzer Berichte auf ihren mobilen Geräten nutzen. Weitere Informationen finden Sie [unter SQL Server Reporting Services (SSRS): Erstellen, Bereitstellen](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)und Verwalten mobiler und paginierter Berichte .
  
### <a name="use-performancepoint-services-on-premises"></a>Verwenden PerformancePoint-Dienste (lokal)

PerformancePoint Server 2007 wurde separat von SharePoint Server 2007 verkauft. Ab SharePoint Server 2010 ist PerformancePoint-Dienste eine Dienstanwendung in SharePoint Server. Sie müssen also keine separaten Serverlizenzen oder Hardware erwerben, um PerformancePoint-Dienste.
  
Um von PerformancePoint Server 2007 zu PerformancePoint-Dienste wechseln, wechseln Sie zu einer neueren Version von SharePoint Server, und konfigurieren PerformancePoint-Dienste. Die Version von SharePoint Server, zu der Sie wechseln, bestimmt, ob Sie ihre vorhandenen Dashboardinhalte aus PerformancePoint Server 2007 in PerformancePoint-Dienste.
  
- Wenn Sie ein Upgrade auf SharePoint Server 2010 durchführen, können Sie Ihre PerformancePoint-Dashboardinhalte von PerformancePoint Server 2007 auf PerformancePoint-Dienste in SharePoint Server 2010 importieren. Weitere Informationen finden Sie unter [Import Wizard: PerformancePoint Server 2007 content to SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/ee681485(v=office.14)).
    
- Wenn Sie zu SharePoint Server 2013 oder SharePoint Server 2016 wechseln, müssen Sie höchstwahrscheinlich neue Dashboardinhalte (Datenquellen, Berichte, Scorecards und Dashboardseiten) erstellen.
    
Informationen zu den ersten PerformancePoint-Dienste finden Sie in den folgenden Ressourcen:
  
- [SharePoint Server 2007 end of support Roadmap](sharepoint-2007-end-of-support.md)
    
- Wenn Sie wissen, zu welcher Version von SharePoint Sie umstiegen, lesen Sie den entsprechenden Artikel für PerformancePoint-Dienste:
    
  - [Planen für PerformancePoint Services (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee681486(v=office.14))
    
  - [PerformancePoint-Dienste in SharePoint Server 2013 übersicht](/sharepoint/administration/performancepoint-services-overview)
    
  - [Übersicht über PerformancePoint-Dienste in SharePoint Server 2016](/sharepoint/administration/performancepoint-services-overview)
    
Wenn Sie ein Upgrade auf PerformancePoint-Dienste, erhalten Sie mehrere neue Features und Verbesserungen. PerformancePoint-Dienste bietet verbesserte Scorecards; neue Visualisierungen, z. B. der Bericht "Analysestruktur" und "KPI-Details"; weitere Diagrammtypen; bessere Funktionen für die Zeitintelligenzfilterung; und verbesserte Barrierefreiheitskonformität. Weitere Informationen finden Sie unter [What's new for PerformancePoint-Dienste (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14)).
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>Wo kann ich Hilfe bei meinem Upgrade erhalten?

Unabhängig davon, ob Sie ein lokales Upgrade durchführen oder zu Microsoft 365 wechseln, wird empfohlen, mit einem Microsoft-Partner zu arbeiten. Ein qualifizierter Partner kann Ihnen dabei helfen, die Lösung zu identifizieren, die Ihren Geschäftlichen Anforderungen am besten entspricht, und Bei der Bereitstellung helfen. Besuchen Sie [das Microsoft Partner Center,](https://go.microsoft.com/fwlink/?linkid=841249)und verwenden Sie die Suchfilter, um einen Lösungsanbieter zu finden.
  
## <a name="related-topics"></a>Verwandte Themen

[Ressourcen, die Ihnen beim Upgrade von Office 2007-Servern und -Clients helfen](upgrade-from-office-2007-servers-and-products.md)