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
description: 'Zusammenfassung: Rufen Sie IT-Poster ab, auf denen die Architekturmodelle, die Bereitstellung und Plattformoptionen für SharePoint, Exchange, Skype for Business und Lync beschrieben werden.'
ms.openlocfilehash: 67f1018c70dfc86306b0d1e7ceb6061a166b3db8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690689"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Architekturmodelle für SharePoint, Exchange, Skype for Business und Lync

Auf diesen IT-Postern werden die Architekturmodelle und Bereitstellungsoptionen für SharePoint, Exchange, Skype for Business und Lync beschrieben und Entwurfsinformationen für die Bereitstellung von SharePoint in Microsoft Azure zur Verfügung gestellt.
  
Mit Microsoft 365 können Sie die Dienste für Zusammenarbeit und Kommunikation, mit denen Ihre Benutzern vertraut sind, als cloudbasierten Dienst bereitstellen. Mit wenigen Ausnahmen bleibt die Benutzererfahrung gleich, unabhängig davon, ob Sie eine lokale Bereitstellung beibehalten oder Microsoft 365 verwenden. Diese einheitliche Benutzeroberfläche macht es nicht ganz so einfach zu entscheiden, wo jede Verarbeitungslast platziert werden soll, und es ergeben sich Fragen wie:
  
- Wie entscheiden Sie, welche Plattform für Ihre einzelnen Verarbeitungslasten verwendet werden soll?
    
- Ist es sinnvoll, Dienste lokal beizubehalten?
    
- In welchen Szenarien ist eine Hybridbereitstellung geeignet?
    
- Wie passt Microsoft Azure ins Bild?
    
- Was sind die unterstützten Konfigurationen für Office Server-Arbeitslasten in Azure?
    
> [!TIP]
> Die meisten der Poster auf dieser Seite sind in mehreren Sprachen erhältlich, darunter Chinesisch, Englisch, Französisch, Deutsch, Italienisch, Japanisch, Koreanisch, Portugiesisch, Russisch und Spanisch. Um ein Poster in einer dieser Sprachen herunterzuladen, klicken Sie auf den Link **Weitere Sprachen** für das betreffende Poster.
  
Geben Sie uns Feedback, indem Sie eine E-Mail an [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com) senden. 
  
Diese Seite ist mit den folgenden Postern verknüpft:
  
- **Poster zu Architekturmodellen** Sie können diese Ressourcen verwenden, um Ihre ideale Plattform und Konfiguration für SharePoint 2016 und Skype for Business 2015 zu bestimmen.
    
  - [Microsoft SharePoint 2016-Architekturmodelle](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [SharePoint Server 2016-Datenbanken](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Architekturmodelle für Microsoft Skype for Business 2015](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Poster zu Plattformoptionen** Sie können diese Ressourcen verwenden, um Ihre ideale Plattform und Konfiguration für SharePoint 2013, Exchange 2013 und Lync 2013 zu bestimmen.
    
  - [SharePoint 2013-Plattformoptionen](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Exchange 2013-Plattformoptionen](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Lync 2013-Plattformoptionen](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **Poster zu SharePoint Server 2013 in Azure-Lösungen** Sie können diese IT-Poster verwenden, um den Entwurf und die Konfiguration für SharePoint Server 2013-Arbeitslasten in Azure-Infrastrukturdiensten zu bestimmen.
    
  - [Internetwebsites in Microsoft Azure mit SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Entwurfsbeispiel: Internetwebsites in Microsoft Azure für SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [SharePoint-Notfallwiederherstellung in Microsoft Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Poster zu Architekturmodellen

Diese neuen IT-Poster für SharePoint 2016 und Skype for Business 2015 bieten eine Möglichkeit, die unterschiedlichen Bereitstellungsmethoden in einem einfach zu druckenden Format zu vergleichen. Jedes Poster enthält eine Liste aller zur Verfügung stehenden Konfigurationen oder Plattformoptionen und bietet Ihnen die folgenden Informationen für die einzelnen Optionen:
  
- **Übersicht** Eine kurze Zusammenfassung der Plattform, z. B. ein konzeptionelles Diagramm.
    
- **Am besten für** Gängige Szenarien, die für die jeweilige Plattform ideal geeignet sind.
    
- **Lizenzanforderungen** Die Lizenzen, die Sie für die Bereitstellung benötigen.
    
- **Architekturaufgaben** Die Entscheidungen, die Sie als Architekt treffen müssen.
    
- **IT Pro-Aufgaben und -Zuständigkeiten** Die täglichen Aufgaben, die Ihre IT-Mitarbeiter planen müssen.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-2016-architectural-models"></a>Microsoft SharePoint 2016-Architekturmodelle

|**Element**|**Beschreibung**|
|:-----|:-----|
|[![Miniaturansicht der Architekturmodellposter für SharePoint 2016](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=52650) <br/> | Dieses IT-Poster beschreibt SharePoint Online-, Microsoft Azure- und lokale SharePoint-Konfigurationen, die Entscheidungsträger im Unternehmen und Lösungsarchitekten kennen müssen. <br/><br/> - **SharePoint Online (SaaS)** – Nutzen Sie SharePoint über ein SaaS-Abonnementmodell (Software as a Service). <br/> - **SharePoint-Hybrid** – Verschieben Sie Ihre SharePoint-Websites und -Apps nach Ihrem eigenen Zeitplan in die Cloud. <br/> - **SharePoint in Azure (IaaS)** – Sie erweitern Ihre lokale Umgebung in Microsoft Azure und stellen SharePoint 2016-Server dort bereit. (Dies wird für hohe Verfügbarkeit/Notfallwiederherstellung und Test-/Entwicklungsumgebungen empfohlen.)<br/> - **SharePoint lokal** – Die Planung, Bereitstellung, Verwaltung und Anpassung Ihrer SharePoint-Umgebung erfolgt in einem von Ihnen verwalteten Rechenzentrum. <br/> |
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>SharePoint Server 2016-Datenbanken

|**Element**|**Beschreibung**|
|:-----|:-----|
|[![Miniaturansicht des SharePoint Server 2016-Datenbankposters](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)          ](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=55041) <br/> | Dieses IT-Poster ist eine Kurzübersicht für SharePoint Server 2016-Datenbanken. Jede Datenbank weist die folgenden Details auf: <br/><br/> – Größe <br/> – Hilfestellung zur Skalierung <br/> – E/A-Muster <br/> – Anforderungen <br/><br/>  Die erste Seite enthält die SharePoint-Systemdatenbanken und die Dienstanwendungen, die mehrere Datenbanken aufweisen. Auf der zweiten Seite sind alle Dienstanwendungen verzeichnet, die über Einzeldatenbanken verfügen.<br/><br/>  Weitere Informationen zu den SharePoint Server 2016-Datenbanken finden Sie unter [Datenbanktypen und -beschreibungen in SharePoint Server 2016](https://docs.microsoft.com/SharePoint/technical-reference/database-types-and-descriptions). <br/> |
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Architekturmodelle für Microsoft Skype for Business 2015

|**Element**|**Beschreibung**|
|:-----|:-----|
|[![Miniaturansicht der Architekturmodellposter für Skype for Business](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)          ](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=55022) <br/> |Dieses Poster beschreibt die Konfiguration von Skype for Business Online, lokale Konfigurationen sowie Hybrid- und Cloud-PBX-Konfigurationen und deren Integration in Exchange- und SharePoint-Konfigurationen, die Entscheidungsträger im Unternehmen und Lösungsarchitekten kennen müssen. <br/><br/> Es richtet sich an IT-Experten und soll auf die unterschiedlichen Architekturmodelle aufmerksam machen, über die Skype for Business Online sowie eine lokale Skype for Business-Konfiguration genutzt werden können. <br/><br/>Beginnen Sie mit der Konfiguration, die sich optimal für die Anforderungen und Zukunftspläne Ihrer Organisation eignet. Ziehen Sie bei Bedarf andere Konfigurationen in Erwägung. Es kann beispielsweise sinnvoll sein, die Integration mit Exchange und SharePoint oder eine Lösung in Betracht zu ziehen, die das Angebot von Microsoft für eine Nebenstellenanlage in der Cloud nutzt.  <br/> |
   
## <a name="platform-options-posters"></a>Poster zu Plattformoptionen 

Diese IT-Poster für SharePoint 2013, Exchange 2013 und Lync 2013 bieten eine Möglichkeit, die unterschiedlichen Bereitstellungsmethoden auf einen Blick auf einem großen Poster zu vergleichen. Jedes Poster enthält eine Liste aller zur Verfügung stehenden Konfigurationen oder Plattformoptionen und bietet Ihnen die folgenden Informationen für die einzelnen Optionen:
  
- **Übersicht** Eine kurze Zusammenfassung der Plattform, z. B. ein konzeptionelles Diagramm.
    
- **Am besten für** Gängige Szenarien, die für die jeweilige Plattform ideal geeignet sind.
    
- **Lizenzanforderungen** Die Lizenzen, die Sie für die Bereitstellung benötigen.
    
- **Architekturaufgaben** Die Entscheidungen, die Sie als Architekt treffen müssen.
    
- **IT Pro-Aufgaben und -Zuständigkeiten** Die täglichen Aufgaben, die Ihre IT-Mitarbeiter planen müssen.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>SharePoint 2013-Plattformoptionen

****

|**Element**|**Beschreibung**|
|:-----|:-----|
|[![Miniaturansicht der SharePoint 2013-Plattformoptionen](../media/SP-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=40332) <br/> |Für Entscheidungsträger in Unternehmen und Architekten zeigt dieses Modell die Plattformoptionen für SharePoint 2013, SharePoint in Microsoft 365, lokale Hybridumgebungen mit Microsoft 365, Azure und reine lokale Bereitstellungen. Es enthält einen Überblick über jede Architektur, Empfehlungen, Lizenzanforderungen und Listen der Aufgaben von Architekten und IT-Experten für jede Plattform. Mehrere SharePoint-Lösungen auf Azure werden hervorgehoben. <br/> |
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Exchange 2013-Plattformoptionen

****

|**Element**|**Beschreibung**|
|:-----|:-----|
|[![Miniaturansicht der Exchange-Plattformoptionen](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=42676) <br/> |Für Entscheidungsträger in Unternehmen und Architekten beschreibt dieses Modell die verfügbaren Plattformoptionen für Exchange 2013. Kunden können zwischen Exchange Online mit Microsoft 365, hybridem Exchange, lokalem Exchange Server und gehostetem Exchange wählen. Das Poster enthält Details zu jeder Architekturoption, einschließlich der jeweils idealen Szenarios für die jeweilige Option, die Lizenzvoraussetzungen und die Zuständigkeiten von IT-Experten. <br/> |
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Lync 2013-Plattformoptionen

****

|**Element**|**Beschreibung**|
|:-----|:-----|
|[![Miniaturansicht der Lync-Plattformoptionen](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=41677) <br/> |Für Entscheidungsträger in Unternehmen und Architekten beschreibt dieses Modell die verfügbaren Plattformoptionen für Lync 2013. Kunden können zwischen Lync Online mit Microsoft 365, hybridem Lync, lokalem Lync Server und gehostetem Lync wählen. Das IT-Poster enthält Details zu jeder Architekturoption, einschließlich der jeweils idealen Szenarios für die jeweilige Option, die Lizenzvoraussetzungen und die Zuständigkeiten von IT-Experten.  <br/> |
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Poster zu SharePoint in Azure-Lösungen

Auf diesen IT-Postern sind Azure-basierte Lösungen, die SharePoint Server 2013 verwenden, im Großformat dargestellt.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Internetwebsites in Microsoft Azure mit SharePoint Server 2013

****

|**Element**|**Beschreibung**|
|:-----|:-----|
|[![Bild der Internetwebsites in Azure mit SharePoint](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=41992) <br/> |Dieses Poster stellt wichtige Designaktivitäten und empfohlene Architekturentscheidungen für Websites in Azure heraus.  <br/><br/> Weitere Informationen finden Sie in den folgenden Artikeln:  <br/><br/> - [Internetwebsites in Microsoft Azure mit SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Microsoft Azure-Architekturen für SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) <br/> |
   
<a name="DesignSampleInternetSites"> </a>
### <a name="design-sample-internet-sites-in-microsoft-azure-for-sharepoint-2013"></a>Entwurfsbeispiel: Internetwebsites in Microsoft Azure für SharePoint 2013

****

|**Element**|**Beschreibung**|
|:-----|:-----|
|[![Bild des Entwurfsbeispiels: Internetwebsites in Microsoft Azure für SharePoint 2013](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=41991) <br/> |Verwenden Sie dieses Designbeispiel als Ausgangspunkt für Ihre eigene Architekturwebsite in Azure mit SharePoint Server 2013. <br/><br/> Weitere Informationen finden Sie in den folgenden Artikeln:  <br/><br/> - [Internetwebsites in Microsoft Azure mit SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Microsoft Azure-Architekturen für SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) <br/> |
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>SharePoint-Notfallwiederherstellung in Microsoft Azure

****

|**Element**|**Beschreibung**|
|:-----|:-----|
|[![SharePoint-Notfallwiederherstellungsvorgang zu Azure](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=41993) <br/> |Dieses IT-Poster stellt Architekturprinzipien für eine Notfallwiederherstellungsumgebung in Azure dar. <br/><br/> Weitere Informationen finden Sie in den folgenden Artikeln:  <br/><br/> - [SharePoint Server 2013 – Notfallwiederherstellung in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Microsoft Azure-Architekturen für SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) <br/> |
   
## <a name="see-also"></a>Siehe auch

[Microsoft 365 Lösungs- und Architektur-Center](../solutions/solution-architecture-center.md)
  
[Illustrationen zu Microsoft Cloud für Enterprise-Architekten](../solutions/cloud-architecture-models.md)
  
[Microsoft 365 Test Umgebungs Anleitungen](m365-enterprise-test-lab-guides.md)
  
[Hybridlösungen](hybrid-solutions.md)

