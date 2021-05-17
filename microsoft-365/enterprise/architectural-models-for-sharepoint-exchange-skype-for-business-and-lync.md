---
title: Architekturmodelle für SharePoint, Exchange, Skype for Business und Lync
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
ms.assetid: 5b49fa68-f8f2-4705-af96-5f5475e8539a
search.appverid:
- MET150
description: Hier erhalten Sie IT-Poster, die die Architekturmodelle, Bereitstellungs- und Plattformoptionen für SharePoint, Exchange, Skype for Business und Lync beschreiben.
ms.openlocfilehash: 6c8aea1f6389c5007adb1800639488972483d5fb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905512"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Architekturmodelle für Microsoft Office SharePoint Online, Exchange, Skype for Business und Lync

Die IT-Poster in diesem Artikel beschreiben die Architekturmodelle und Bereitstellungsoptionen für SharePoint, Exchange, Skype for Business und Lync. Außerdem stellen sie Entwurfsinformationen für die Bereitstellung von SharePoint in Microsoft Azure.
  
Mit Microsoft 365 können Sie über die Cloud vertraute Zusammenarbeits- und Kommunikationsdienste bereitstellen. Mit einigen Ausnahmen bleibt die Benutzeroberfläche unabhängig davon, ob Sie eine lokale Bereitstellung verwalten oder eine Microsoft 365. 

Diese einheitliche Benutzeroberfläche erschwert die Entscheidung, wo die einzelnen Arbeitsauslastungen stattfinden. Sie wirft außerdem Fragen auf:
  
- Wie wählen Sie eine Plattform für einzelne Arbeitsauslastungen aus?
    
- Ist es sinnvoll, Dienste lokal beizubehalten?
    
- In welchem Szenario ist eine Hybridbereitstellung geeignet?
    
- Wie passt Azure in das Bild?
    
- Welche Konfigurationen Office Serverworkloads werden von Azure unterstützt?
    
> [!TIP]
> Die meisten Poster in diesem Artikel sind in mehreren Sprachen verfügbar. Verfügbare Sprachen sind Chinesisch, Englisch, Französisch, Deutsch, Italienisch, Japanisch, Koreanisch, Portugiesisch, Russisch und Spanisch. Wenn Sie ein Poster in einer dieser Sprachen herunterladen möchten, wählen Sie unter dem Miniaturbild des Posters **Weitere Sprachen aus.**
  
Geben Sie uns Feedback, indem Sie eine E-Mail an [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com) senden. 
  
Verwenden Sie die folgenden Links, um die benötigten Poster zu erhalten:
  
- **Architekturmodelle:** Verwenden Sie diese Ressourcen, um Ihre ideale Plattform und Konfiguration für SharePoint 2016 und Skype for Business 2015 zu bestimmen.
    
  - [Microsoft SharePoint 2016-Architekturmodelle](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [SharePoint Server 2016-Datenbanken](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Microsoft Skype for Business 2015-Architekturmodelle](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Plattform**: Verwenden Sie diese Ressourcen, um Ihre ideale Plattform und Konfiguration für SharePoint 2013, Exchange 2013 und Lync 2013 zu bestimmen.
    
  - [SharePoint 2013-Plattformoptionen](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Exchange 2013-Plattformoptionen](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Lync 2013-Plattformoptionen](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **SharePoint Server 2013 in Azure**: Verwenden Sie diese IT-Poster, um SharePoint Server 2013-Workloads in Azure-Infrastrukturdiensten zu entwerfen und zu konfigurieren.
    
  - [Internetwebsites in Azure mit SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Entwurfsbeispiel: Internetwebsites in Azure für SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [SharePoint Notfallwiederherstellung in Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Poster zu Architekturmodellen

Die IT-Poster für SharePoint 2016 und Skype for Business 2015 bieten eine Möglichkeit, Bereitstellungsmethoden in einem einfach zu druckenden Format zu vergleichen. Auf den Postern sind alle Konfigurationsoptionen oder Plattformoptionen aufgeführt. Sie enthalten die folgenden Informationen für jede Option:
  
- **Übersicht**: Eine kurze Zusammenfassung der Plattform, einschließlich eines konzeptionellen Diagramms.
    
- **Am besten für:** Allgemeine Szenarien, die ideal für die Plattform geeignet sind.
    
- **Lizenzanforderungen:** Die Lizenzen, die Sie für die Bereitstellung benötigen.
    
- **Architekturaufgaben:** Die Entscheidungen, die Sie als Architekt treffen müssen.
    
- **Aufgaben oder Zuständigkeiten von IT-Mitarbeitern:** Die täglichen Zuständigkeiten, die Ihre IT-Mitarbeiter planen müssen.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Microsoft SharePoint Server 2016-Architekturmodelle

|Element|Beschreibung|
|---|---|
|[![Miniaturansicht für das SharePoint Server 2016 Architectural Models.](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=52650)|Dieses IT-Poster beschreibt die SharePoint Online-, Azure- und SharePoint lokalen Konfigurationen, die Entscheidungsträger und Lösungsarchitekten kennen müssen. <br/><br/> - **SharePoint Online (SaaS):** Nutzen sie SharePoint software as a service (SaaS)-Abonnementmodell. <br/> - **SharePoint Hybrid:** Verschieben Sie Ihre SharePoint und Apps in Ihrem eigenen Tempo in die Cloud. <br/> - **SharePoint in Azure (IaaS):** Erweitern Sie Ihre lokale Umgebung auf Azure, und stellen Sie SharePoint 2016-Server bereit. (Dieses Modell wird für Umgebungen mit hoher Verfügbarkeit oder Notfallwiederherstellung und Entwicklungs-/Testumgebungen empfohlen.) <br/> - **SharePoint lokal**: Planen, Bereitstellen, Warten und Anpassen Ihrer SharePoint in einem Rechenzentrum, das Sie verwalten.|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>SharePoint Server 2016-Datenbanken

|Element|Beschreibung|
|---|---|
|[![Miniaturansicht für das SharePoint Server 2016 Databases.](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=55041)|Dieses IT-Poster ist eine Kurzübersicht für SharePoint Server 2016-Datenbanken. Details zu jeder Datenbank werden angezeigt: <br/><br/> – Größe <br/> – Hilfestellung zur Skalierung <br/> – E/A-Muster <br/> – Anforderungen <br/><br/>  Die erste Seite zeigt die SharePoint Systemdatenbanken und die Dienstanwendungen mit mehreren Datenbanken. Die zweite Seite zeigt alle Dienstanwendungen mit einzelnen Datenbanken. <br/><br/>  Weitere Informationen finden Sie unter [Datenbanktypen und Beschreibungen in SharePoint Server 2016](/SharePoint/technical-reference/database-types-and-descriptions).|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Architekturmodelle für Microsoft Skype for Business 2015

|Element|Beschreibung|
|---|---|
|[![Miniaturansicht für das poster Skype for Business Architekturmodelle.](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=55022)|Dieses Poster beschreibt Skype for Business online, lokal, hybrid und Cloud Private Branch Exchange (PBX). Außerdem wird die Integration in Exchange und SharePoint beschrieben, die Entscheidungsträger und Lösungsarchitekten in Unternehmen kennen müssen. <br/><br/> Das Poster richtet sich an IT-Profis, um die grundlegenden Architekturmodelle zu sensibilisieren, mit denen Skype for Business Online und Skype for Business lokal genutzt werden können. <br/><br/>Beginnen Sie mit der Konfiguration, die den Anforderungen und Plänen Ihrer Organisation am besten entspricht. Berücksichtigen und verwenden Sie bei Bedarf andere Konfigurationen. Beispielsweise sollten Sie die Integration in Exchange und SharePoint oder eine Lösung in Betracht ziehen, die das Microsoft Cloud PBX-Angebot nutzt.|
   
## <a name="platform-options-posters"></a>Poster zu Plattformoptionen 

Die IT-Poster für SharePoint 2013, Exchange 2013 und Lync 2013 bieten eine Möglichkeit, die Bereitstellungsmethoden auf einen Blick zu vergleichen. Jedes Poster listet alle Konfigurationen oder Plattformoptionen auf. Es enthält die folgenden Informationen für jede Option:
  
- **Übersicht**: Eine kurze Zusammenfassung der Plattform, einschließlich eines konzeptionellen Diagramms.
    
- **Am besten für:** Allgemeine Szenarien, die ideal für die Plattform geeignet sind.
    
- **Lizenzanforderungen:** Die Lizenzen, die Sie für die Bereitstellung benötigen.
    
- **Architekturaufgaben:** Die Entscheidungen, die Sie als Architekt treffen müssen.
    
- **Aufgaben oder Zuständigkeiten von IT-Mitarbeitern:** Die täglichen Zuständigkeiten, die Ihre IT-Mitarbeiter planen müssen.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>SharePoint 2013-Plattformoptionen

|Element|Beschreibung|
|---|---|
|[![Miniaturansicht des Posters SharePoint 2013-Plattformoptionen.](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=40332)|Für Entscheidungsträger und Architekten in Unternehmen zeigt dieses Poster die Plattformoptionen für SharePoint 2013, SharePoint in Microsoft 365, lokale Hybridbereitstellung mit Microsoft 365, Azure und lokalen Bereitstellungen. Es enthält eine Übersicht über die einzelnen Architekturen, Empfehlungen, Lizenzanforderungen und Listen mit Architektur- und IT-Pro-Aufgaben für jede Plattform. Das Poster zeigt verschiedene SharePoint Lösungen in Azure.|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Exchange 2013-Plattformoptionen

|Element|Beschreibung|
|---|---|
|[![Miniaturansicht des Posters Exchange Plattformoptionen.](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=42676)|Für Entscheidungsträger und Architekten in Unternehmen beschreibt dieses Poster die Plattformoptionen für Exchange 2013. Kunden können zwischen Exchange Online mit Microsoft 365, hybriden Exchange, Exchange Server lokalen und gehosteten Exchange. Auf dem Poster werden die einzelnen Architekturoptionsoptionsdetails beschrieben, einschließlich der idealen Szenarien für die einzelnen Architekturszenarien, der Lizenzanforderungen und der Verantwortlichkeiten von IT-Profis.|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Lync 2013-Plattformoptionen

|Element|Beschreibung|
|---|---|
|[![Miniaturansicht des Lync 2013-Plattformoptionen-Posters.](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=41677)|Für Entscheidungsträger und Architekten in Unternehmen beschreibt dieses Poster die Plattformoptionen für Lync 2013. Kunden können zwischen Lync Online mit Microsoft 365, Lync-Hybrid,Lync Server lokal und gehosteten Lync wählen. Das IT-Poster enthält details zu jeder Architekturoption, einschließlich der idealen Szenarien für die einzelnen, der Lizenzanforderungen und der Verantwortlichkeiten von IT-Profis.|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Poster zu SharePoint in Azure-Lösungen

Die IT-Poster für SharePoint in Azure zeigen Azure-basierte Lösungen, die SharePoint Server 2013 verwenden.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Internetsites in Microsoft Azure Using SharePoint Server 2013

|Element|Beschreibung|
|---|---|
|[![Abbildung der Internetwebsites in Azure mithilfe SharePoint Server 2013-Posters.](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=41992)|In diesem Poster werden die wichtigsten Entwurfsaktivitäten und die empfohlene Architektur für Internetwebsites in Azure erläutert.  <br/><br/> Weitere Informationen finden Sie in den folgenden Artikeln:  <br/><br/> - [Internetwebsites in Azure mit SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Azure-Architekturen für SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>Internetwebsites in Azure für SharePoint 2013

|Element|Beschreibung|
|---|---|
|[![Abbildung der Internetwebsites in Microsoft Azure für SharePoint Server 2013 Poster.](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=41991)|Verwenden Sie dieses Entwurfsbeispiel als Ausgangspunkt für Ihre eigene Architektur einer mit dem Internet in Azure verbundenen Website mithilfe von SharePoint Server 2013. <br/><br/> Weitere Informationen finden Sie in den folgenden Artikeln:  <br/><br/> - [Internetwebsites in Azure mit SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Azure-Architekturen für SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>SharePoint-Notfallwiederherstellung in Microsoft Azure

|Element|Beschreibung|
|---|---|
|[![Abbildung des Posters für SharePoint Wiederherstellung in Azure.](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=41993)|Dieses IT-Poster stellt Architekturprinzipien für eine Notfallwiederherstellungsumgebung in Azure dar. <br/><br/> Weitere Informationen finden Sie in den folgenden Artikeln:  <br/><br/> - [SharePoint Server 2013-Notfallwiederherstellung in Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Azure-Architekturen für SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>Siehe auch

- [Microsoft 365-Lösungs- und Architekturcenter](../solutions/index.yml)
  
- [Microsoft Cloud-Architekturmodelle](../solutions/cloud-architecture-models.md)
  
- [Microsoft 365 Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)
  
- [Hybridlösungen](hybrid-solutions.md)