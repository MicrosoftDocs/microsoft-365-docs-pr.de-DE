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
description: PerformancePoint Server 2007, ProClarity und SharePoint Server 2007 haben das Ende der Unterstützung erreicht. Lesen Sie diesen Artikel, um die Planung Ihres BI-Lösungs Upgrades zu unterstützen.
ms.openlocfilehash: 4a13e6f8a40de78c0d98b03369b52a78899fc7a9
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519597"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>Ende der Unterstützung für PerformancePoint Server 2007 – Roadmap

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Office 2007 Server und Anwendungen haben ihr Ende der Unterstützung erreicht, einschließlich der Server und Anwendungen, die Sie möglicherweise als Teil Ihrer Business Intelligence (BI)-Lösungen verwenden. In der folgenden Tabelle sind die betroffenen BI-Anwendungen aufgeführt:
  
|**Microsoft BI-Anwendungen**|**Datum-Unterstützung beendet**|
|:-----|:-----|
|ProClarity Analytics Server 6,3 Service Pack 3  <br/> ProClarity Desktop Professional 6,3  <br/> ProClarity SharePoint Viewer 6,3  <br/> |11. Juli 2017  <br/> |
|SharePoint Server 2007 Service Pack 3  <br/> |10. Oktober 2017  <br/> |
|PerformancePoint Server 2007 Service Pack 3  <br/> |09. Januar 2018  <br/> |
   
Weitere Informationen finden Sie unter [Ressourcen, die Sie beim Upgrade von Office 2007 Servern und Clients unterstützen](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>Was bedeutet das *Ende der Unterstützung* ?

Wie bei den meisten Microsoft-Produkten verfügen PerformancePoint Server 2007 SP3, die ProClarity-Software und SharePoint Server 2007 SP3 über einen Support-Lebenszyklus, in dem Microsoft neue Features, Bugfixes und Sicherheitsupdates bereitstellt. Der Lebenszyklus für ein Produkt dauert in der Regel 10 Jahre nach der ersten Version des Produkts. Das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Da ProClarity, PerformancePoint Server und SharePoint Server 2007 ihren Supportende erreicht haben, bietet Microsoft nicht mehr Folgendes:
  
- Technischer Support für Probleme, die auftreten können.
    
- Fehlerbehebungen für erkannte Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit von Servern auswirken können.
    
- Sicherheitsfixes für erkannte Sicherheitsanfälligkeiten, die Server oder Anwendungen anfällig für Sicherheitsverletzungen machen können.
    
- Zeitzonenaktualisierungen.
    
Die Installation von ProClarity, SharePoint Server 2007 SP3 und PerformancePoint Server 2007 SP3 wird weiterhin ausgeführt, obwohl die Unterstützung beendet wurde. Es wird jedoch dringend empfohlen, dass Sie so bald wie möglich von diesen Anwendungen migrieren.
  
## <a name="what-are-my-options"></a>Was sind meine Optionen?

Es wurden viele Änderungen an Microsoft BI-Anwendungen seit 2007, und Sie haben mehrere Optionen zu prüfen, wie in der folgenden Tabelle zusammengefasst.
  
|**Wenn Sie diese verwenden...**|**Erkunden Sie diese Optionen...**|**Und denken Sie daran...**|
|:-----|:-----|:-----|
| PerformancePoint Server 2007 Analysefunktionen für die Überwachung &amp; , einschließlich:<br/>-PerformancePoint Monitoring Server <br/>-PerformancePoint Dashboard-Designer<br/>-Dashboard-Viewer für SharePoint-Dienste (wird zum Rendern von PerformancePoint-Dashboards, Scorecards und Berichten verwendet)<br/> |**Excel mit Excel in einem Browser** (in der Cloud oder lokal). Eine Übersicht finden Sie unter [BI-Funktionen in Excel und Microsoft 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx).<br/><br/> **Power BI** (in der Cloud oder lokal). Eine Übersicht finden Sie unter [Was ist Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting Services** (lokal). Eine Übersicht finden Sie unter [SQL Server Reporting Services (SSRS): erstellen, bereitstellen und Verwalten von mobilen und paginierten Berichten](https://go.microsoft.com/fwlink/?linkid=841342). <br/><br/> **PerformancePoint-Dienste** (lokal). Eine Übersicht finden Sie unter [What es New for PerformancePoint-Dienste (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841343). <br/> |Excel steht als Online-(Cloud-basierte) oder lokale Lösung zur Verfügung. Viele Berichts-und Dashboard-Anforderungen können mit Excel erfüllt werden.  <br/><br/> Power BI steht als Online-oder lokale Lösung zur Verfügung. Power BI ist in Microsoft 365 nicht enthalten. Sie können jedoch Power BI kostenlos nutzen. Je nach Datennutzung und geschäftlichen Anforderungen können Sie zu einem späteren Zeitpunkt ein Upgrade auf Power BI pro mit Microsoft 365 E5 durchführen.<br/> <br/> Reporting Services und PerformancePoint-Dienste sind lokale Lösungen. <br/><br/> PerformancePoint-Dienste steht in SharePoint Server 2010, SharePoint Server 2013 und SharePoint Server 2016 zur Verfügung. <br/> <br/> Einige Features und Berichtstypen, die in PerformancePoint Server 2007 verfügbar waren, sind in Excel, Power BI, Reporting Services oder PerformancePoint-Dienste nicht verfügbar. Überprüfen Sie die verfügbaren Features, um die beste Lösung für Ihre geschäftlichen Anforderungen zu ermitteln. <br/> |
| ProClarity-Software, einschließlich:<br/>-ProClarity Desktop Professional<br/> -ProClarity Analytics Server<br/>-ProClarity SharePoint Viewer<br/> |**Arbeiten Sie mit einem Microsoft-Partner zusammen** , um eine Lösung zu finden, die Ihren Anforderungen am besten entspricht. Besuchen Sie das [Microsoft Partner Center](https://go.microsoft.com/fwlink/?linkid=841249). <br/><br/> Sie können auch Excel mit Excel in einem Browser, Power BI, SQL Server Reporting Services oder PerformancePoint-Dienste verwenden.  <br/> |Einige, jedoch nicht alle Features von ProClarity-Software sind in anderen Microsoft-angeboten verfügbar, einschließlich Excel, Power BI, Reporting Services und PerformancePoint-Dienste.  <br/> |
|SharePoint Server 2007 KPIs (auch als Moss-KPIs bezeichnet)  <br/> |**Excel mit Excel Services**. Eine Übersicht finden Sie unter [Business Intelligence in Excel und Excel Services (SharePoint Server 2013)](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx). <br/> |Moss-KPIs, die mit SharePoint Server 2007 erstellt wurden, können in SharePoint Server 2010, SharePoint Server 2013 und SharePoint Server 2016 verwendet werden. Sie können jedoch keine neuen MOSS-KPIs erstellen.  <br/> |
|Excel 2007  <br/> |**Excel** (in der Cloud oder lokal). Eine Übersicht finden Sie unter [BI-Funktionen in Excel und Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx). <br/><br/> **Power BI** (in der Cloud oder lokal). Eine Übersicht finden Sie unter [Was ist Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |Sowohl Excel als auch Power BI bieten Ihre Organisation Cloud-basierte und lokale Lösungen mit Unterstützung für eine Vielzahl von Datenquellen.  <br/> |
   
### <a name="help-selecting-a-solution"></a>Hilfe bei der Auswahl einer Lösung

Da so viele BI-Auswahlmöglichkeiten zur Verfügung stehen, kann es überwältigend erscheinen, zu bestimmen, welche Option am besten geeignet ist. Ihnen steht ein Online-Leitfaden zur Verfügung. Weitere Informationen finden Sie unter [Choosing Microsoft Business Intelligence (BI) Tools for Analysis and Reporting](https://go.microsoft.com/fwlink/?linkid=839877).
  
### <a name="what-if-i-dont-upgrade-now"></a>Was geschieht, wenn ich jetzt kein Upgrade durchführen möchte?

Sie können auswählen, dass kein Upgrade sofort durchführen wird. Ihre vorhandenen Server und Anwendungen werden weiterhin ausgeführt. Sie erhalten jedoch keine weiteren Updates, einschließlich Sicherheitsupdates, da die Unterstützung beendet wurde. Wenn bei ihren Serveranwendungen etwas schief geht, können Sie keine Hilfe vom technischen Support von Microsoft erhalten.
  
## <a name="how-do-i-plan-my-upgrade"></a>Wie plane ich mein Upgrade?

Nachdem Sie die Upgrade-Optionen untersucht haben, besteht der nächste Schritt in der Vorbereitung eines Upgrade-Plans. Die folgenden Abschnitte enthalten Informationen und zusätzliche Ressourcen, die Sie unterstützen können. Sie verfügen über vier Hauptoptionen, darunter zwei, die sowohl in der Cloud als auch in der lokalen Version funktionieren, und zwei, die nur lokal sind:
  
|**Option**|**In der Cloud oder lokal?**|
|:-----|:-----|
|[Excel mit SharePoint Server (lokal)](#excel-with-sharepoint-server-on-premises) <br/> |In beide Richtungen  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |In beide Richtungen  <br/> |
|[Reporting Services](#use-reporting-services-on-premises) <br/> |Nur lokal  <br/> |
|[PerformancePoint Services](#use-performancepoint-services-on-premises) <br/> |Nur lokal  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>Verwenden von Excel (in der Cloud oder lokal)

Mit Excel, das auch als *Excel Services* in SharePoint Server bezeichnet wird, können Sie Arbeitsmappen in einem Browserfenster anzeigen und verwenden, selbst wenn Excel nicht auf dem Computer installiert ist. Sie können Excel zum Erstellen von Berichten, Scorecards und Dashboards verwenden. Geben Sie dann Ihre Arbeitsmappen für andere frei, die Excel in einem Browser verwenden können, unabhängig davon, ob Sie SharePoint Online als Teil von Microsoft 365 oder SharePoint Server lokal verwenden. Sie können Daten, die lokal oder in der Cloud gespeichert sind, verwenden, sodass Sie eine Vielzahl von Datenquellen verwenden können.
  
In der folgenden Tabelle werden die wichtigsten Vorteile der Verwendung von Excel mit Microsoft 365 für die Verwendung von Excel mit SharePoint Server verglichen. Weitere Informationen folgen.
  
|**Excel mit Microsoft 365 (in der Cloud)**|**Excel mit SharePoint Server (lokal)**|
|:-----|:-----|
|**Sie erhalten die neueste, beste Version von Excel**. Mit Microsoft 365 erhalten Sie die neueste Version von Excel, die leistungsstarke neue Diagrammtypen, die Möglichkeit zum schnellen und einfachen Erstellen von Diagrammen und Tabellen sowie Unterstützung für weitere Datenquellen enthält. <br/> <br/> **Das Setup ist viel einfacher**. Excel ist im Lieferumfang von Microsoft 365 for Business enthalten, daher gibt es keine schwerwiegenden Anhebungen ihrerseits. Registrieren Sie sich, und melden Sie sich an, und Sie werden schneller und effizienter ausgeführt, als wenn Sie Ihre lokalen Server aktualisieren. <br/> <br/> **Personen haben überall Zugriff auf Ihre Arbeitsmappen**. Benutzer können Arbeitsmappen mit Ihrem Computer, Smartphone und Tablet sicher von überall anzeigen, wo Sie sich befinden. <br/> <br/> **Es gibt noch mehr!** Weitere Informationen finden Sie unter [BI-Funktionen in Excel und Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx). <br/> |**Sie verwalten Ihre globalen Einstellungen**. Als SharePoint-Administrator können Sie globale Einstellungen wie Sicherheit, Lastenausgleich, Sitzungsverwaltung, Arbeitsmappen-Caching und externe Datenverbindungen angeben. <br/> <br/> **Sie können Excel Services mit PerformancePoint-Dienste verwenden**. Sie können Excel Services und PerformancePoint-Dienste im Rahmen der SharePoint Server Installation konfigurieren und Excel Services Berichte in Ihre PerformancePoint-Dashboards einschließen. <br/> <br/> **Es gibt noch mehr!** Weitere Informationen finden Sie unter [Business Intelligence in Excel und Excel Services (SharePoint Server 2013)](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx). <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>Excel mit Microsoft 365 (in der Cloud)

Wenn Sie zu Microsoft 365 migrieren, verfügen Sie über die aktuellsten Dienste und Anwendungen, einschließlich Excel 2016. PerformancePoint-Dienste ist in Microsoft 365 nicht verfügbar, daher ersetzen Sie den PerformancePoint-Dashboard-Inhalt durch Excel-Arbeitsmappen oder andere Berichte. Die gute Nachricht ist, dass Excel 2016 viele neue Diagrammtypen aufweist, und es ist einfacher als je zuvor, beeindruckende Dashboards in Excel zu erstellen. Und neue Features werden regelmäßig hinzugefügt. Weitere Informationen finden Sie unter [What es New in Excel 2016 für Windows](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx).
  
Wenn Sie 50-Sitze oder mehr von Microsoft 365 erwerben, kann Ihnen das Microsoft-Team für Schnelleinstieg bei der Einrichtung behilflich sein. Weitere Informationen finden Sie unter [schneller.](https://www.microsoft.com/fasttrack/microsoft-365)
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>Excel mit SharePoint Server (lokal)

Wenn Sie ein Upgrade auf eine neuere Version von SharePoint durchführen, können Sie Excel mit Excel Services oder in einem Browser wie folgt verwenden:
  
- Excel Services in SharePoint Server 2010
    
- Excel Services in SharePoint Server 2013
    
- Excel, das Teil von Office Online Server ist, separat von SharePoint Server 2016 installiert
    
Sie können PerformancePoint-Dienste auch in ihrer neuen Version von SharePoint Server konfigurieren und diese zusammen mit Excel verwenden.
  
Weitere Informationen zu den SharePoint-Upgrade-Optionen finden Sie unter [SharePoint Server 2007 Ende der Support-Roadmap](sharepoint-2007-end-of-support.md).
  
Weitere Informationen zu Excel Services finden Sie unter [Excel Services Overview (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841362).
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>Verwenden von Power BI (in der Cloud oder lokal)

Power BI ist eine Sammlung von Business Analytics-Tools, um Daten zu analysieren und Erkenntnisse freizugeben. Mit Power BI können Sie lokale oder Online-Datenquellen verwenden, um interaktive Berichte und Dashboards zu erstellen. Personen können Ihre Berichte und Dashboards auf ihren Computern oder mobilen Geräten anzeigen und verwenden.
  
Power BI ist nicht Teil von Microsoft 365 oder SharePoint Server. Es handelt sich um ein separates Angebot, das Power BI-Desktop, Power BI-Gateways und den Power BI-Dienst umfasst. Power BI integriert sich auch in SharePoint Online. Sie können mit Power BI kostenlos loslegen. Basierend auf den Anforderungen Ihrer Datennutzung und Ihres Unternehmens können Sie später mit Microsoft 365 E5 ein Upgrade auf Power BI pro durchführen. Weitere Informationen finden Sie unter [Was ist Power BI?](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>Verwenden von Reporting Services (lokal)

SQL Server Reporting Services bietet eine stabile Berichtslösung. Sie können Reporting Services entweder im einheitlichen Modus oder im integrierten SharePoint-Modus konfigurieren. Sie können verschiedene Tools zum Erstellen von Berichten verwenden, einschließlich Berichts-Designer, Berichts-Generator und Power View. Mit der neuesten Version von SQL Server können Sie auch SQL Server Mobile Report Publisher verwenden, um Berichte zu übermitteln, die auf jede Bildschirmgröße skaliert werden. Auf diese Weise können Betrachter Berichte auf Ihren mobilen Geräten nutzen. Weitere Informationen finden Sie unter [SQL Server Reporting Services (SSRS): erstellen, bereitstellen und Verwalten von mobilen und paginierten Berichten](https://go.microsoft.com/fwlink/?linkid=841342).
  
### <a name="use-performancepoint-services-on-premises"></a>Verwenden von PerformancePoint-Dienste (lokal)

PerformancePoint Server 2007 wurde separat von SharePoint Server 2007 verkauft. Beginnend mit SharePoint Server 2010 ist PerformancePoint-Dienste eine Dienstanwendung in SharePoint Server. Sie müssen also keine separaten Server Lizenzen oder Hardware erwerben, um PerformancePoint-Dienste verwenden zu können.
  
Um von PerformancePoint Server 2007 zu PerformancePoint-Dienste zu gelangen, navigieren Sie zu einer neueren Version von SharePoint Server und konfigurieren PerformancePoint-Dienste. Die SharePoint Server Version, die Sie umstellen, um festzustellen, ob Sie den vorhandenen Dashboard-Inhalt aus PerformancePoint Server 2007 in PerformancePoint-Dienste importieren können.
  
- Wenn Sie ein Upgrade auf SharePoint Server 2010 durchführen, können Sie den PerformancePoint-Dashboard-Inhalt von PerformancePoint Server 2007 in PerformancePoint-Dienste in SharePoint Server 2010 importieren. Weitere Informationen finden Sie unter [Import Wizard: PerformancePoint Server 2007 Content to SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=838873).
    
- Wenn Sie zu SharePoint Server 2013 oder SharePoint Server 2016 migrieren, müssen Sie wahrscheinlich neue Dashboard-Inhalte erstellen (Datenquellen, Berichte, Scorecards und Dashboardseiten).
    
Informationen zu den ersten Schritten mit dem PerformancePoint-Dienste-Upgradeplan finden Sie in den folgenden Ressourcen:
  
- [SharePoint Server 2007-Roadmap für das Ende des Supports](sharepoint-2007-end-of-support.md)
    
- Wenn Sie wissen, zu welcher Version von SharePoint Sie wechseln, lesen Sie den entsprechenden Artikel für PerformancePoint-Dienste:
    
  - [Planen für PerformancePoint Services (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841363)
    
  - [PerformancePoint-Dienste in SharePoint Server 2013 Übersicht](https://go.microsoft.com/fwlink/?linkid=841551)
    
  - [Übersicht über PerformancePoint-Dienste in SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=874704)
    
Wenn Sie ein Upgrade auf PerformancePoint-Dienste durchführen, erhalten Sie mehrere neue Features und Verbesserungen. PerformancePoint-Dienste bietet verbesserte Scorecards; Neue Visualisierungen, wie der Analysebaum und der KPI-Detailbericht; mehr Diagrammtypen; bessere Zeitintelligenz-Filterfunktionen; und verbesserte Zugänglichkeits Kompatibilität. Weitere Informationen finden Sie unter [What es New for PerformancePoint-Dienste (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841343).
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>Wo erhalte ich Hilfe zu meinem Upgrade?

Unabhängig davon, ob Sie lokal ein Upgrade durchführen oder zu Microsoft 365 wechseln, wird empfohlen, dass Sie mit einem Microsoft-Partner zusammenarbeiten. Ein qualifizierter Partner kann Ihnen dabei helfen, die Lösung zu finden, die Ihren geschäftlichen Anforderungen am besten entspricht, und Ihnen bei der Bereitstellung behilflich sein. Besuchen Sie das [Microsoft Partner Center](https://go.microsoft.com/fwlink/?linkid=841249), und verwenden Sie die Suchfilter, um einen Lösungsanbieter zu finden.
  
## <a name="related-topics"></a>Verwandte Themen

[Ressourcen für das Upgrade von Office 2007-Servern und-Clients](upgrade-from-office-2007-servers-and-products.md)