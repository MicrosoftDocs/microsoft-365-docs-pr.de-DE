---
title: Ende der Unterstützung für Project Server 2007 – Roadmap
ms.author: efrene
author: efrene
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
ms.assetid: d379018f-72b7-4284-b40a-6c23c8ae38fe
description: Am 10. Oktober 2017 wurde die Unterstützung für Project Server 2007, Project Portfolio Server und Project 2007 beendet. Verwenden Sie diesen Artikel, um Ihr Upgrade jetzt zu planen.
ms.openlocfilehash: f59b319ec39c6b2d1df0876c916332491f1bb0f6
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519799"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Ende der Unterstützung für Project Server 2007 – Roadmap

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Die Unterstützung für Office 2007 Server und Anwendungen in 2017 wurde beendet, und Sie müssen Pläne für die Migration in Frage stellen. Wenn Sie Project Server 2007 und Verwandte Produkte derzeit verwenden, beachten Sie die folgenden End-of-Support-Termine:
  
|**Produkt**|**Ende des Support Datums**|
|:-----|:-----|
|Project Server 2007  <br/> |10. Oktober 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10. Oktober 2017  <br/> |
|Project 2007 Standard  <br/> |10. Oktober 2017  <br/> |
|Project 2007 Professional  <br/> |10. Oktober 2017  <br/> |
   
Weitere Informationen zu Office 2007 Servern, die in den Ruhestand gelangen, finden Sie unter [Upgrade von Office 2007-Servern und-Clientprodukten](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>Was bedeutet das *Ende der Unterstützung* ?

Die meisten Microsoft-Produkte haben einen Support-Lebenszyklus, in dem Sie neue Funktionen, Bugfixes, Sicherheitsfixes usw. erhalten. Dieser Lebenszyklus dauert in der Regel 10 Jahre nach der ersten Version des Produkts. Das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Da Project Server 2007 das Ende der Unterstützung am 10. Oktober 2017 erreicht hat, bietet Microsoft nicht mehr Folgendes:
  
- Technischer Support für Probleme, die auftreten können.
    
- Fehlerbehebungen für Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können.
    
- Sicherheitsfixes für Sicherheitsanfälligkeiten, die den Server möglicherweise anfällig für Sicherheitsverletzungen machen.
    
- Zeitzonenaktualisierungen.
    
Die Installation von Project Server 2007 wird weiterhin nach diesem Datum ausgeführt. Aufgrund der zuvor aufgeführten Änderungen wird jedoch dringend empfohlen, dass Sie die Migration von Project Server 2007 so schnell wie möglich durchführen.
  
## <a name="what-are-my-options"></a>Was sind meine Optionen?

Wenn Sie Project Server 2007 verwenden, müssen Sie die folgenden Migrationsoptionen untersuchen:
  
- Migrieren zu Project Online
    
- Migrieren zu einer neueren lokalen Version von Project Server (vorzugsweise Project Server 2016)
    
|**Warum sollte ich lieber zu Project Online migrieren?**|**Warum sollte ich lieber zu Project Server 2016 migrieren?**|
|:-----|:-----|
| Ich habe mobile Benutzer.  <br/> <br/>Die zu migrierenden Kostenstellen ein erhebliches Problem dar (Hardware, Software, Stunden und Aufwand für die Implementierung). <br/><br/>  Nach der Migration sind die Kosten für die Wartung meiner Umgebung ein wichtiges Anliegen (beispielsweise automatische Updates, garantierte Betriebszeit usw.).  <br/> | Geschäftsregeln beschränken mich auf das betreiben meines Unternehmens in der Cloud.<br/><br/>  Ich benötige die Kontrolle über Updates für meine Umgebung.  |
   
> [!NOTE]
> Weitere Informationen zu den Optionen für den Wechsel von Ihren Office 2007 Servern finden Sie unter [Ressourcen, die Ihnen beim Upgrade von Office 2007-Servern und-Clients helfen](upgrade-from-office-2007-servers-and-products.md). Beachten Sie, dass Project Server keine Hybrid Konfiguration unterstützt, da Project Server und Project Online nicht denselben Ressourcenpool freigeben können. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Wichtige Überlegungen bei der Migration von Project Server 2007

Berücksichtigen Sie beim Planen der Migration von Project Server 2007 Folgendes:
  
- **Erhalten von Hilfe von einem Microsoft-Partner – ein** Upgrade von Project Server 2007 kann eine Herausforderung darstellen und erfordert viel Vorbereitung und Planung. Es kann eine besondere Herausforderung sein, wenn Sie nicht die Person sind, die Project Server 2007 ursprünglich eingerichtet hat. Glücklicherweise gibt es Microsoft-Partner, die helfen können, ob Sie eine Migration zu Project Server 2016 oder zu Project Online planen. Suchen Sie nach einem Microsoft-Partner, der Sie bei der Migration im [Microsoft Partner Center](https://go.microsoft.com/fwlink/p/?linkid=841249)unterstützt. Suchen Sie im Begriff  *Gold Project and Portfolio Management* , um eine Liste aller Microsoft-Partner anzuzeigen, die über Fachwissen in Project verfügen. 
    
- **Planen Sie Ihre Anpassungen** – viele der Anpassungen, die Sie in Ihrer Project Server 2007-Umgebung vorgenommen haben, funktionieren möglicherweise nicht, wenn Sie zu Project Server 2016 oder Project Online migrieren. Es gibt erhebliche Unterschiede bei der Architektur von Project Server zwischen Versionen. Die unterstützten erforderlichen Betriebssysteme, Datenbankserver und Client Webbrowser unterscheiden sich ebenfalls. Planen, wie Sie Ihre Anpassungen für die neue Umgebung testen oder neu erstellen. Die Planung bietet auch eine gute Gelegenheit zu prüfen, ob jede Anpassung noch benötigt wird. Weitere Informationen finden Sie unter [Create a plan for current customizations during upgrade to SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=842061). 
    
- **Zeit und Geduld** : das Upgrade von Planung, Ausführung und Tests erfordert Zeit und Mühe, vor allem, wenn Sie ein Upgrade auf Project Server 2016 durchführen. Wenn Sie beispielsweise von Project Server 2007 zu Project Server 2016 migrieren, müssen Sie zunächst zu Project Server 2010 migrieren, Ihre Daten überprüfen und dann dasselbe Verfahren ausführen, wenn Sie zu jeder nachfolgenden Version migrieren. Wenden Sie sich an einen Microsoft-Partner, um Schätzungen darüber zu erhalten, wie lange das dauert und was es Kosten wird.
    
## <a name="migrate-to-project-online"></a>Migrieren zu Project Online

Wenn Sie eine Migration von Project Server 2007 zu Project online durchführen, können Sie die folgenden Schritte ausführen, um die Projektplandaten manuell zu migrieren:
  
1. Speichern Sie Ihre Projektpläne in Project Server 2003 im Format. mpp.
    
2. Öffnen Sie in Project Professional 2013 Project Professional 2016 oder den Project Online-Desktop Client jede MPP-Datei, und speichern und veröffentlichen Sie Sie dann in Project online.
    
Sie können Ihre Microsoft Project Web App (PWA)-Konfiguration in Project Online manuell erstellen. Erstellen Sie beispielsweise alle erforderlichen benutzerdefinierten Felder oder Enterprise-Kalender neu. Microsoft-Partner können diesen Prozess auch unterstützen.
  
Wichtige Ressourcen:
  
|**Ressource**|**Beschreibung**|
|:-----|:-----|
|[Erste Schritte mit Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Einrichten und Verwenden von Project Online <br/> |
|[Project Online Dienstbeschreibungen](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Informationen zu den verschiedenen Project Online Plänen, die Ihnen zur Verfügung stehen <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrieren zu einer neueren lokalen Version von Project Server

Wir sind der festen Überzeugung, dass Sie mit der Migration zu Project Online den besten nutzen und die optimale Benutzererfahrung erzielen. Wir wissen jedoch auch, dass einige Organisationen Projektdaten in einer lokalen Umgebung aufbewahren müssen. Wenn Sie Ihre Projektdaten lokal beibehalten möchten, können Sie Ihre Project Server 2007-Umgebung zu Project Server 2010, Project Server 2013 oder Project Server 2016 migrieren.
  
Wenn Sie nicht zu Project Online migrieren können, wird empfohlen, dass Sie zu Project Server 2016 migrieren. Project Server 2016 enthält alle Features früherer Versionen von Project Server. Sie entspricht am ehesten der mit Project online verfügbaren Funktionalität, obwohl einige Features nur in Project online verfügbar sind.
  
Nach jeder Migration sollten Sie überprüfen, ob die Daten erfolgreich migriert wurden.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Wie kann ich zu Project Server 2016 migrieren?

Architektonische Unterschiede zwischen Project Server 2007 und Project Server 2016 verhindern einen direkten Migrationspfad. Sie müssen also Ihre Project Server 2007-Daten zu jeder nachfolgenden Version von Project Server migrieren, bis Sie Project Server 2016 erreichen.
  
Führen Sie die folgenden Schritte zu Project Server 2016 aus:
  
1. Migrieren von Project Server 2007 zu Project Server 2010.
    
2. Migrieren von Project Serve 2010 zu Project Server 2013.
    
3. Migrieren von Project Server 2013 zu Project Server 2016.
    
Stellen Sie nach jeder Migration sicher, dass die Daten erfolgreich migriert wurden.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Schritt 1: Migrieren von Project Server 2007 zu Project Server 2010

Eine umfassende Beschreibung der Schritte, die Sie für ein Upgrade von Project Server 2007 auf Project Server 2010 ausführen müssen, finden Sie unter [Upgrade to Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812).
  
Wichtige Ressourcen:
  
|**Ressource**|**Beschreibung**|
|:-----|:-----|
|[Project Server 2010-Upgrade (Übersicht)](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |Eine allgemeine Übersicht über die erforderlichen Schritte zum Upgrade von Project Server 2007 auf Project Server 2010 <br/> |
|[Planen des Upgrades auf Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |Planungsüberlegungen beim Upgrade von Project Server 2007 auf Project Server 2010, einschließlich System Anforderungen  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Wie aktualisiere ich?

Ausführliche Informationen finden Sie unter [Upgrade auf Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812). Es ist jedoch wichtig zu wissen, dass es zwei verschiedene Methoden gibt, mit denen Sie ein Upgrade durchführen können:
  
- **Upgrade mit Datenbankanfügung:** Diese Methode aktualisiert nur den Inhalt für Ihre Umgebung, nicht die Konfigurationseinstellungen. Dies ist erforderlich, wenn Sie ein Upgrade von Office Project Server 2007 bereitstellen, die auf Hardware bereitgestellt werden und nur ein 32-Bit-Server Betriebssystem unterstützt. Es gibt zwei Arten von Upgrades durch Datenbankanfügungen:
    
  - ***Vollständiges Upgrade* mit Datenbankanfügung** : migriert die in den Office Project Server 2007 Datenbanken gespeicherten Projektdaten sowie die in einer SharePoint-Inhaltsdatenbank gespeicherten Microsoft Project Web App-Website Daten.
    
  - ***Core-Upgrade* mit Datenbankanfügung** – migriert nur die Projektdaten, die in den Project Server-Datenbanken gespeichert sind.
    
- **Direktes Upgrade**: die Konfigurationsdaten für die Farm und alle Inhalte in der Farm werden auf der vorhandenen Hardware in einer festen Reihenfolge aktualisiert. Wenn Sie den Upgradevorgang starten, wird die gesamte Farm vom Setup-Programm offline geschaltet. Die Websites und Microsoft Project Web App-Websites sind erst verfügbar, wenn das Upgrade abgeschlossen ist, und dann startet Setup den Server neu. Nachdem Sie ein direktes Upgrade gestartet haben, können Sie das Upgrade nicht anhalten oder ein Rollback zur vorherigen Version durchführen. Es empfiehlt sich, ein gespiegeltes Abbild Ihrer Produktionsumgebung zu erstellen und das in-Place-Upgrade auf diese Umgebung durchzuführen, nicht in Ihrer Produktionsumgebung. 
    
Zusätzliche Ressourcen:
  
- [Superflow für Microsoft Project Server 2010-Upgrade](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [Migration von Project Server 2007 auf Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Überlegungen zu Upgrades für Project Web App Webparts](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [Project Software Development Kit (SDK)](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>Schritt 2: Migrieren zu Project Server 2013

Nachdem Sie sichergestellt haben, dass die Daten erfolgreich migriert wurden, müssen Sie im nächsten Schritt zu Project Server 2013 migrieren.
  
Eine umfassende Beschreibung der Schritte, die Sie für ein Upgrade von Project Server 2010 auf Project Server 2013 ausführen müssen, finden Sie unter [Upgrade to Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822). 
  
Wichtige Ressourcen:
  
|**Ressource**|**Beschreibung**|
|:-----|:-----|
|[Übersicht über den Project Server 2013-Upgradevorgang](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |Übersicht über die erforderlichen Schritte zum Upgrade von Project Server 2010 auf Project Server 2013  <br/> |
|[Planen des Upgrades auf Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |Planungsüberlegungen beim Upgrade von Project Server 2010 auf Project Server 2013, einschließlich System Anforderungen <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Wissenswerte zum Upgrade auf diese Version

[Was ist neu in Project Server 2013-Upgrade](https://go.microsoft.com/fwlink/p/?linkid=841824) beschreibt wichtige Änderungen für das Upgrade für diese Version. Die bemerkenswertesten sind: 
  
- Es gibt kein direktes Upgrade auf Project Server 2013. Die Methode der Datenbankanfügung ist die einzige unterstützte Methode für ein Upgrade von Project Server 2010 auf Project Server 2013.
    
- Durch den Upgradeprozess werden nicht nur Ihre Project Server 2010 Daten in Project Server 2013 Format konvertiert, sondern auch die vier Project Server 2010 Datenbanken werden in einer einzigen Project Web App Datenbank konsolidiert.
    
- In den 2013-Versionen wurden sowohl SharePoint Server als auch Project Server in die anspruchsbasierte Authentifizierung geändert. Wenn Sie die klassische Authentifizierung verwenden, müssen Sie diesen Faktor für Ihr Upgrade berücksichtigen. Weitere Informationen finden Sie unter [Migrieren von der klassischen Authentifizierung zur anspruchsbasierten Authentifizierung in SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=841825).
    
Zusätzliche Ressourcen:
  
- [Übersicht über den Prozess zum Upgrade auf Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Upgrade der Datenbanken und Project Web App-Websitesammlungen (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Microsoft Project Server-Aktualisierungsprozess (Diagramm)](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [Die große Datenbankkonsolidierung Project Server 2010 zu 2013 Migration in 8 einfachen Schritten](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Schritt 3: Migrieren zu Project Server 2016

Nachdem Sie sichergestellt haben, dass die Daten erfolgreich migriert wurden, müssen Sie im nächsten Schritt zu Project Server 2016 migrieren.
  
Eine umfassende Beschreibung der Schritte, die Sie für ein Upgrade von Project Server 2013 auf Project Server 2016 ausführen müssen, finden Sie unter [Upgrade to Project Server 2016](https://docs.microsoft.com//project/upgrading-to-project-server-2016).
  
Wichtige Ressourcen:
  
|**Ressource**|**Beschreibung**|
|:-----|:-----|
|[Übersicht über den Project Server 2016-Upgradevorgang](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |Übersicht über die erforderlichen Schritte zum Upgrade von Project Server 2013 auf Project Server 2016 <br/> |
|[Planen des Upgrades auf Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |Planungsüberlegungen für ein Upgrade von Project Server 2013 auf Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Wissenswerte zum Upgrade auf diese Version

[Dinge, die Sie über das Project Server 2016-Upgrade wissen müssen](https://go.microsoft.com/fwlink/p/?linkid=841827) , enthalten einige wichtige Änderungen für das Upgrade für diese Version, einschließlich:
  
- Wenn Sie Ihre Project Server 2016-Umgebung erstellen, in der Sie Ihre Project Server 2013 Daten migrieren, sind die Project Server 2016-Installationsdateien in SharePoint Server 2016 enthalten. Weitere Informationen finden Sie unter [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).
    
- Ressourcenpläne sind in Project Server 2016 veraltet. Ihre Project Server 2013 Ressourcenpläne werden zu Ressourcen Projekten in Project Server 2016 und in Project Online migriert. Weitere Informationen finden Sie unter [Übersicht: Ressourcen Engagements](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) . 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migrieren von Portfolio Server 2007

Project Portfolio Server 2007 wurde zusammen mit Project Server 2007 für Portfolio Strategie, Priorisierung und Optimierung verwendet. Nach dieser Version wurden keine weiteren Versionen von Project Portfolio Server erstellt. Portfolio Verwaltungsfeatures sind jedoch in Project Server 2016 und der Premium-Version von Project online verfügbar. Daten aus dem Project-Portfolio Server 2007 können aber auch nicht zu migriert werden. Daten wie Geschäftstreiber müssen neu erstellt werden.
  
Weitere Ressourcen:
  
- [Project Online Dienstbeschreibungen:](https://go.microsoft.com/fwlink/p/?linkid=841280) Weitere Informationen finden Sie in den Features zur Portfolioverwaltung, die in Project Server 2016 und Project Online Premium enthalten sind.
    
- [Migrationshandbuch für Microsoft Office Project Portfolio Server 2007.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Verwandte Themen

[SharePoint Server 2007-Roadmap für das Ende des Supports](sharepoint-2007-end-of-support.md)
  
[Ressourcen für das Upgrade von Office 2007-Servern und-Clients](upgrade-from-office-2007-servers-and-products.md)
  
