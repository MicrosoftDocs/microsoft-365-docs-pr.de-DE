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
description: PerformancePoint Server 2007, ProClarity und SharePoint Server 2007 haben das Ende der Unterstützung erreicht. Lesen Sie diesen Artikel, um Ihr BI-lösungsupgrade zu planen.
ms.openlocfilehash: b9718630ff92b8093fa3940b12dde1b34486616c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695920"
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
  
## <a name="what-does-end-of-support-mean"></a>Was bedeutet das Ende der Unterstützung?

Microsoft-Produkte wie PerformancePoint Server 2007 SP3, ProClarity-Software und SharePoint Server 2007 SP3 hatten alle einen Support-Lebenszyklus, in dem Microsoft neue Features, Bugfixes und Sicherheitsupdates bereitstellt. Der Lebenszyklus für ein Produkt dauert normalerweise 10 Jahre ab dem Datum der ursprünglichen Produktversion, und das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Da ProClarity, PerformancePoint Server und SharePoint Server 2007 ihre Unterstützung erreicht haben, bietet Microsoft nicht mehr Folgendes:
  
- Technischer Support für Probleme, die auftreten können
    
- Fehlerbehebungen für erkannte Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit von Servern auswirken können
    
- Sicherheitsfixes für erkannte Sicherheitsanfälligkeiten, die Server oder Anwendungen anfällig für Sicherheitsverletzungen machen können
    
- Zeitzonenaktualisierungen
    
Die Installation von ProClarity, SharePoint Server 2007 SP3 und PerformancePoint Server 2007 SP3 wird weiterhin ausgeführt, obwohl die Unterstützung beendet wurde. Es wird jedoch dringend empfohlen, dass Sie so bald wie möglich von diesen Anwendungen migrieren.
  
## <a name="what-are-my-options"></a>Was sind meine Optionen?

Wenn diese BI-Anwendungen das Ende des Supports erreichen, ist dies ein guter Zeitpunkt, um Ihre Optionen zu erkunden und einen Upgradeplan vorzubereiten. Es wurden viele Änderungen an Microsoft BI-Anwendungen seit 2007, und Sie haben mehrere Optionen zu prüfen, wie in der folgenden Tabelle zusammengefasst:
  
|**Wenn Sie diese verwenden...**|**Erkunden Sie diese Optionen...**|**Und denken Sie daran...**|
|:-----|:-----|:-----|
| PerformancePoint Server 2007 Analysefunktionen für die Überwachung &amp; , einschließlich:  <br/><br/>  PerformancePoint Monitoring Server  <br/><br/>  PerformancePoint Dashboard-Designer  <br/><br/>  Dashboard-Viewer für SharePoint-Dienste (zum Rendern von PerformancePoint-Dashboards, Scorecards und Berichten verwendet)  <br/> |**Excel mit Excel in einem Browser** (in der Cloud oder lokal). Eine Übersicht finden Sie unter [BI-Funktionen in Excel und Microsoft 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/><br/> **Power BI** (in der Cloud oder lokal). Eine Übersicht finden Sie unter [Was ist Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting Services** (lokal). Eine Übersicht finden Sie unter [SQL Server Reporting Services (SSRS): erstellen, bereitstellen und Verwalten von mobilen und paginierten Berichten](https://go.microsoft.com/fwlink/?linkid=841342) <br/><br/> **PerformancePoint-Dienste** (lokal). Eine Übersicht finden Sie unter [What es New for PerformancePoint-Dienste (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841343) <br/> |Excel ist entweder als Online (Cloud-basiert) oder als lokale Lösung verfügbar. Viele Berichts-und Dashboard-Anforderungen können mit den Funktionen von Excel erfüllt werden.  <br/><br/> Power BI ist entweder als Online-oder als lokale Lösung verfügbar. Power BI ist nicht in Microsoft 365 enthalten, aber Sie können mit der Nutzung von Power BI kostenlos beginnen und dann, je nach Datennutzung und geschäftlichen Anforderungen, ein Upgrade auf Power BI pro mit Microsoft 365 E5 durchführen. <br/> <br/> Reporting Services und PerformancePoint-Dienste sind lokale Lösungen.  <br/><br/> PerformancePoint-Dienste steht in SharePoint Server 2010, SharePoint Server 2013 und SharePoint Server 2016 zur Verfügung. <br/> <br/> Einige Features und Berichtstypen, die in PerformancePoint Server 2007 verfügbar waren, stehen in Excel, Power BI, Reporting Services oder PerformancePoint-Dienste nicht zur Verfügung. Sie sollten die verfügbaren Features überprüfen, um die beste Lösung für Ihre geschäftlichen Anforderungen zu ermitteln.  <br/> |
| ProClarity-Software, einschließlich: <br/> <br/>  ProClarity Desktop Professional  <br/> <br/> ProClarity Analytics Server  <br/> <br/> ProClarity SharePoint Viewer  <br/> |**Arbeiten Sie mit einem Microsoft-Partner zusammen** , um eine Lösung zu finden, die Ihren Anforderungen am besten entspricht. Besuchen Sie das [Microsoft Partner Center](https://go.microsoft.com/fwlink/?linkid=841249) <br/><br/> Sie können auch Excel mit Excel in einem Browser, Power BI, SQL Server Reporting Services oder PerformancePoint-Dienste verwenden.  <br/> |Mehrere, aber nicht alle Features und Funktionen, die in der ProClarity-Software verfügbar waren, stehen in anderen Microsoft-angeboten zur Verfügung, einschließlich Excel, Power BI, Reporting Services und PerformancePoint-Dienste.  <br/> |
|SharePoint Server 2007 KPIs (auch als Moss-KPIs bezeichnet)  <br/> |**Excel mit Excel Services**. Eine Übersicht finden Sie unter [Business Intelligence in Excel und Excel Services (SharePoint Server 2013)](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) <br/> |Moss-KPIs, die mit SharePoint Server 2007 erstellt wurden, können in SharePoint Server 2010, SharePoint Server 2013 und SharePoint Server 2016 verwendet werden. Es können jedoch keine neuen MOSS-KPIs erstellt werden.  <br/> |
|Excel 2007  <br/> |**Excel** (in der Cloud oder lokal). Eine Übersicht finden Sie unter [BI-Funktionen in Excel und Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/><br/> **Power BI** (in der Cloud oder lokal). Eine Übersicht finden Sie unter [Was ist Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |Sowohl Excel als auch Power BI bieten Ihre Organisation Cloud-basierte und lokale Lösungen mit Unterstützung für eine Vielzahl von Datenquellen.  <br/> |
   
### <a name="what-if-i-need-help-selecting-a-solution"></a>Was geschieht, wenn ich Hilfe bei der Auswahl einer Lösung benötige?

Da so viele BI-Auswahlmöglichkeiten zur Verfügung stehen, kann es überwältigend erscheinen, zu bestimmen, welche Option am besten geeignet ist. Ihnen steht ein Online-Leitfaden zur Verfügung. Weitere Informationen finden Sie unter [Choosing Microsoft Business Intelligence (BI) Tools for Analysis and Reporting](https://go.microsoft.com/fwlink/?linkid=839877).
  
### <a name="what-happens-if-i-dont-upgrade-now"></a>Was passiert, wenn ich jetzt kein Upgrade durchführen kann?

Sie können zu diesem Zeitpunkt ein Upgrade auswählen. Ihre vorhandenen Server und Anwendungen werden weiterhin ausgeführt. Allerdings erhalten Sie keine weiteren Updates – einschließlich Sicherheitsupdates – nach Beendigung der Unterstützung. Wenn bei ihren Serveranwendungen ein Fehler auftritt, können Sie keine Hilfe vom technischen Support von Microsoft erhalten.
  
## <a name="how-do-i-plan-my-upgrade"></a>Wie plane ich mein Upgrade?

Nachdem Sie die Upgrade-Optionen untersucht haben, besteht der nächste Schritt darin, einen Upgradeplan vorzubereiten. Die folgenden Abschnitte enthalten Informationen und Links zu weiteren Ressourcen, die Sie bei der Planung Ihrer Lösung unterstützen. Wenn es um Microsoft BI-Anwendungen geht, haben Sie vier Hauptoptionen, darunter zwei, die sowohl in der Cloud oder lokal als auch in zwei lokalen Lösungen funktionieren:
  
|**Option**|**In der Cloud oder lokal?**|
|:-----|:-----|
|[Excel](#excel-with-sharepoint-server-on-premises) <br/> |In beide Richtungen  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or on-premises) <br/> |In beide Richtungen  <br/> |
|[Reporting Services](#use-reporting-services-on-premises) <br/> |Nur lokal  <br/> |
|[PerformancePoint Services](#use-performancepoint-services-on-premises) <br/> |Nur lokal  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>Verwenden von Excel (in der Cloud oder lokal)

Mit Excel – auch als Excel Services in SharePoint Server bezeichnet – können Benutzer Arbeitsmappen in einem Browserfenster anzeigen und verwenden, selbst wenn Excel nicht auf Ihrem Computer installiert ist. Sie können Excel zum Erstellen von Berichten, Scorecards und Dashboards verwenden und dann Ihre Arbeitsmappen für andere freigeben, indem Sie Excel in einem Browser verwenden, unabhängig davon, ob Sie SharePoint Online als Teil von Microsoft 365 oder SharePoint Server lokal verwenden. Sie können auch lokale oder in der Cloud gespeicherte Daten verwenden, wodurch Sie die Möglichkeit haben, eine Vielzahl von Datenquellen zu verwenden.
  
In der folgenden Tabelle werden die wichtigsten Vorteile der Verwendung von Excel mit Microsoft 365 für die Verwendung von Excel mit SharePoint Server mit weiteren Informationen verglichen.
  
|**Excel mit Microsoft 365 (in der Cloud)**|**Excel mit SharePoint Server (lokal)**|
|:-----|:-----|
|**Sie erhalten die neueste, beste Version von Excel**. Mit Microsoft 365 erhalten Sie die neueste Version von Excel, die leistungsstarke, neue Diagrammtypen, die Möglichkeit zum schnellen und einfachen Erstellen von Diagrammen und Tabellen sowie Unterstützung für weitere Datenquellen enthält. <br/> <br/> **Das Setup ist viel einfacher**. Excel ist im Lieferumfang von Microsoft 365 for Business enthalten, daher gibt es keine schwerwiegenden Anhebungen ihrerseits. Registrieren Sie sich, und melden Sie sich an, und Sie werden schneller und effizienter ausgeführt als ein Upgrade Ihrer lokalen Server. <br/> <br/> **Personen haben überall Zugriff auf Ihre Arbeitsmappen**. Benutzer können Arbeitsmappen mit Ihrem Computer, Smartphone und Tablet sicher von überall anzeigen, wo Sie sich befinden. <br/> <br/> **Es gibt noch mehr**! Siehe [BI-Funktionen in Excel und Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/> |**Sie verwalten Ihre globalen Einstellungen**. Als SharePoint-Administrator können Sie globale Einstellungen wie Sicherheit, Lastenausgleich, Sitzungsverwaltung, Arbeitsmappen-Caching und externe Datenverbindungen angeben. <br/> <br/> **Sie können Excel Services mit PerformancePoint-Dienste verwenden**. Sie können Excel Services und PerformancePoint-Dienste im Rahmen der SharePoint Server Installation konfigurieren und Excel Services Berichte in Ihre PerformancePoint-Dashboards einschließen. <br/> <br/> **Es gibt noch mehr**! Siehe [Business Intelligence in Excel und Excel Services (SharePoint Server 2013)](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>Excel mit Microsoft 365 (in der Cloud)

Wenn Sie zu Microsoft 365 migrieren, verfügen Sie über die aktuellsten Dienste und Anwendungen, einschließlich Excel 2016. PerformancePoint-Dienste ist in Microsoft 365 nicht verfügbar, daher ersetzen Sie den PerformancePoint-Dashboard-Inhalt durch Excel-Arbeitsmappen oder andere Berichte. Die gute Nachricht ist, Excel 2016 verfügt über viele neue Diagrammtypen und das Erstellen beeindruckender Dashboards in Excel ist einfacher als je zuvor. Und neue Features werden regelmäßig hinzugefügt. Weitere Informationen finden Sie unter [What es New in Excel 2016 für Windows](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx).
  
Wenn Sie 50-Sitze oder mehr von Microsoft 365 erwerben, kann Ihnen das Microsoft schnell Team bei der Einrichtung behilflich sein. Weitere Informationen finden Sie unter [schneller.](https://www.microsoft.com/fasttrack/microsoft-365)
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>Excel mit SharePoint Server (lokal)

Wenn Sie ein Upgrade auf eine neuere Version von SharePoint durchführen, können Sie Excel mit Excel Services oder in einem Browser wie folgt verwenden:
  
- Excel Services in SharePoint Server 2010
    
- Excel Services in SharePoint Server 2013
    
- Excel, das Teil von Office Online Server ist, separat von SharePoint Server 2016 installiert
    
Sie können PerformancePoint-Dienste auch in ihrer neuen Version von SharePoint Server konfigurieren und diese zusammen mit Excel verwenden.
  
Weitere Informationen zu den SharePoint-Upgrade-Optionen finden Sie unter [SharePoint Server 2007 Ende der Support-Roadmap](sharepoint-2007-end-of-support.md).
  
Weitere Informationen zu Excel Services finden Sie unter [Excel Services Overview (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841362).
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>Verwenden von Power BI (in der Cloud oder lokal)

Power BI ist eine Sammlung von Business Analytics-Tools, um Daten zu analysieren und Erkenntnisse freizugeben. Mit Power BI können Sie interaktive Berichte und Dashboards mit lokalen oder Online-Datenquellenerstellen. Personen können Ihre Berichte und Dashboards mit ihren Computern oder mobilen Geräten anzeigen und verwenden.
  
Power BI ist nicht in Microsoft 365 oder SharePoint Server enthalten, sondern ist ein separates Angebot, das Power BI-Desktop, Power BI-Gateways und den Power BI-Dienst umfasst. Power BI integriert sich auch in SharePoint Online. Sie können mit Power BI kostenlos beginnen und je nach Datennutzung und geschäftlichen Anforderungen ein Upgrade auf Power BI pro mit Microsoft 365 E5 durchführen. Weitere Informationen finden Sie unter [Was ist Power BI?](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>Verwenden von Reporting Services (lokal)

SQL Server Reporting Services bietet eine stabile Berichtslösung sowie die Möglichkeit, Reporting Services im einheitlichen Modus oder im integrierten SharePoint-Modus zu installieren und zu konfigurieren. Sie können Berichte mithilfe verschiedener Tools erstellen, einschließlich Berichts-Designer, Berichts-Generator und Power View. Mit der neuesten Version von SQL Server können Sie auch SQL Server Mobile Report Publisher verwenden, um Berichte zu übermitteln, die auf jede Bildschirmgröße skaliert werden, sodass Ihre Organisation Berichte auf Ihren mobilen Geräten nutzen kann. Weitere Informationen finden Sie unter [SQL Server Reporting Services (SSRS): erstellen, bereitstellen und Verwalten von mobilen und paginierten Berichten](https://go.microsoft.com/fwlink/?linkid=841342).
  
### <a name="use-performancepoint-services-on-premises"></a>Verwenden von PerformancePoint-Dienste (lokal)

Wie Sie wissen, wurde PerformancePoint Server 2007 separat von SharePoint Server 2007 erworben. Beginnend mit SharePoint Server 2010 ist PerformancePoint-Dienste eine Dienstanwendung in SharePoint Server. Dies bedeutet, dass Sie keine separaten Server Lizenzen oder Hardware erwerben müssen, um PerformancePoint-Dienste verwenden zu können.
  
Um von PerformancePoint Server 2007 zu PerformancePoint-Dienste zu gelangen, navigieren Sie zu einer neueren Version von SharePoint Server und konfigurieren PerformancePoint-Dienste. Die Version von SharePoint Server, in die Sie verschieben, bestimmt, ob Sie den vorhandenen Dashboard-Inhalt aus PerformancePoint Server 2007 in PerformancePoint-Dienste importieren können.
  
- Wenn Sie ein Upgrade auf SharePoint Server 2010 durchführen, können Sie den PerformancePoint-Dashboard-Inhalt von PerformancePoint Server 2007 in PerformancePoint-Dienste in SharePoint Server 2010 importieren. Weitere Informationen zur Funktionsweise finden Sie unter [Import Wizard: PerformancePoint Server 2007 Content to SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=838873).
    
- Wenn Sie zu SharePoint Server 2013 oder SharePoint Server 2016 wechseln, müssen Sie wahrscheinlich neue Dashboard-Inhalte erstellen (Datenquellen, Berichte, Scorecards und Dashboardseiten).
    
Informationen zu den ersten Schritten mit dem PerformancePoint-Dienste-Upgradeplan finden Sie in den folgenden Ressourcen:
  
1. [SharePoint Server 2007-Roadmap für das Ende des Supports](sharepoint-2007-end-of-support.md)
    
2. Wenn Sie wissen, zu welcher Version von SharePoint Sie wechseln, lesen Sie den entsprechenden Artikel für PerformancePoint-Dienste:
    
  - [Planen für PerformancePoint Services (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841363)
    
  - [PerformancePoint-Dienste in SharePoint Server 2013 Übersicht](https://go.microsoft.com/fwlink/?linkid=841551)
    
  - [Übersicht über PerformancePoint-Dienste in SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=874704)
    
Wenn Sie ein Upgrade auf PerformancePoint-Dienste durchführen, können Sie mehrere neue Features und Verbesserungen nutzen. PerformancePoint-Dienste bietet verbesserte Scorecards, neue Visualisierungen wie den Analysebaum, einen KPI-Detailbericht und mehr Diagrammtypen, bessere Zeitintelligenz-Filterfunktionen und verbesserte Zugänglichkeits Kompatibilität. Weitere Informationen finden Sie unter [What es New for PerformancePoint-Dienste (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841343).
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>Wo erhalte ich Hilfe zu meinem Upgrade?

Unabhängig davon, ob Sie lokal ein Upgrade durchführen oder zu Microsoft 365 wechseln, wird empfohlen, mit einem Microsoft-Partner zusammenzuarbeiten. Ein qualifizierter Partner kann Ihnen dabei helfen, die Lösung zu finden, die Ihre geschäftlichen Anforderungen am besten erfüllt und Ihre Bereitstellung unterstützt. Besuchen Sie das [Microsoft Partner Center](https://go.microsoft.com/fwlink/?linkid=841249), und verwenden Sie die Suchfilter, um einen Lösungsanbieter zu finden.
  
## <a name="related-topics"></a>Verwandte Themen

[Ressourcen für das Upgrade von Office 2007-Servern und-Clients](upgrade-from-office-2007-servers-and-products.md)