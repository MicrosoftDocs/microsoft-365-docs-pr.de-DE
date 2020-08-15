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
ms.openlocfilehash: 81588f803813d0da938d709e93e26b7dadc3b993
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695968"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Ende der Unterstützung für Project Server 2007 – Roadmap

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Die Unterstützung für Office 2007 Server und Anwendungen in 2017 wurde beendet, und Sie müssen Pläne für die Migration in Frage stellen. Wenn Sie Project Server 2007 derzeit verwenden, beachten Sie, dass es und diese anderen verwandten Produkte die folgenden End-of-Support-Daten hatten:
  
|**Product**|**Ende des Support Datums**|
|:-----|:-----|
|Project Server 2007  <br/> |10. Oktober 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10. Oktober 2017  <br/> |
|Project 2007 Standard  <br/> |10. Oktober 2017  <br/> |
|Project 2007 Professional  <br/> |10. Oktober 2017  <br/> |
   
Weitere Informationen zu Office 2007 Servern, die in den Ruhestand gelangen, finden Sie unter [Upgrade von Office 2007-Servern und-Clientprodukten](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>Was bedeutet das Ende der Unterstützung?

Project Server verfügt wie fast alle Microsoft-Produkte über einen Support-Lebenszyklus, in dem wir neue Features, Bugfixes, Sicherheitsfixes usw. bereitstellen. Dieser Lebenszyklus dauert in der Regel 10 Jahre ab dem Datum der ersten Produktversion, und das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Da Project Server 2007 das Ende der Unterstützung am 10. Oktober 2017 erreicht hat, bietet Microsoft nicht mehr Folgendes:
  
- Technischer Support für Probleme, die auftreten können.
    
- Fehlerbehebungen für entdeckte Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können.
    
- Sicherheitsfixes für Sicherheitsanfälligkeiten, die erkannt werden und die den Server möglicherweise anfällig für Sicherheitsverletzungen machen.
    
- Zeitzonenaktualisierungen.
    
Die Installation von Project Server 2007 wird weiterhin nach diesem Datum ausgeführt. Aufgrund der oben aufgeführten Änderungen wird jedoch dringend empfohlen, dass Sie so bald wie möglich von Project Server 2007 migrieren.
  
## <a name="what-are-my-options"></a>Was sind meine Optionen?

Wenn Sie Project Server 2007 verwenden, müssen Sie die folgenden Migrationsoptionen untersuchen:
  
- Migrieren zu Project Online
    
- Migrieren Sie zu einer neueren lokalen Version von Project Server (vorzugsweise Project Server 2016).
    
|**Warum sollte ich lieber zu Project Online migrieren?**|**Warum sollte ich lieber zu Project Server 2016 migrieren?**|
|:-----|:-----|
| Ich habe mobile Benutzer.  <br/>  Die zu migrierenden Kosten sind ein großes Problem (Hardware, Software, Stunden und Aufwand für die Implementierung usw.).  <br/>  Nach der Migration sind Kosten für die Wartung meiner Umgebung ein großes Problem (beispielsweise automatische Updates, garantierte Verfügbarkeit usw.).  <br/> | Geschäftsregeln beschränken mich auf das betreiben meines Unternehmens in der Cloud.  <br/>  Ich benötige die Kontrolle über Updates für meine Umgebung.  <br/> |
   
> [!NOTE]
> Weitere Informationen zu den Optionen für den Wechsel von Ihren Office 2007 Servern finden Sie unter [Ressourcen, die Ihnen beim Upgrade von Office 2007-Servern und-Clients helfen](upgrade-from-office-2007-servers-and-products.md). Beachten Sie, dass Project Server keine Hybrid Konfiguration unterstützt, da Project Server und Project Online nicht denselben Ressourcenpool freigeben können. 
  
## <a name="important-considerations-you-need-to-make-when-planning-to-migrate-from-project-server-2007"></a>Wichtige Überlegungen, die Sie bei der Planung der Migration von Project Server 2007 treffen müssen

Bei der Planung der Migration von Project Server 2007 müssen Sie Folgendes berücksichtigen:
  
- **Erhalten von Hilfe von einem Microsoft-Partner** – ein Upgrade von Project Server 2007 kann eine Herausforderung darstellen und erfordert viel Vorbereitung und Planung. Es kann eine besondere Herausforderung darstellen, wenn Sie Project Server 2007 ursprünglich nicht eingerichtet und konfiguriert haben. Glücklicherweise gibt es Microsoft-Partner, denen Sie sich zuwenden können, wer dies für einen Lebensunterhalt tut, unabhängig davon, ob Sie eine Migration zu Project Server 2016 oder zu Project Online planen. Sie können nach einem Microsoft-Partner suchen, der Sie bei der Migration im [Microsoft Partner Center](https://go.microsoft.com/fwlink/p/?linkid=841249)unterstützt. Sie können eine Auflistung aller Microsoft-Partner mit Know-how in Project abrufen, indem Sie den Begriff "  *Gold Project and Portfolio Management*  " Durchsuchen. 
    
- **Planen Sie Ihre Anpassungen** -beachten Sie, dass viele der Anpassungen, die Sie in Ihrer Project Server 2007-Umgebung verwenden, bei der Migration zu Project Server 2016 oder Project Online möglicherweise nicht funktionieren. Es gibt große Unterschiede in der Architektur von Project Server zwischen Versionen, sowie die erforderlichen Betriebssysteme, Datenbankserver und Client Webbrowser, die für die Verwendung der neueren Version unterstützt werden. Planen Sie, wie Sie Ihre Anpassungen nach Bedarf in ihrer neuen Umgebung testen oder neu erstellen. Die Planung für Ihr Upgrade stellt auch eine gute Gelegenheit dar, um zu überprüfen, ob eine bestimmte Anpassung beim Fortfahren wirklich benötigt wird. [Erstellen Sie einen Plan für aktuelle Anpassungen beim Upgrade auf SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=842061) enthält einige hervorragende allgemeine Informationen zum bewerten und Planen Ihrer aktuellen Anpassungen beim Upgrade. 
    
- **Zeit und Geduld** : das Upgrade von Planung, Ausführung und Tests erfordert viel Zeit und Mühe, vor allem, wenn Sie ein Upgrade auf Project Server 2016 durchführen. Wenn Sie beispielsweise von Project Server 2007 zu Project Server 2016 migrieren, müssen Sie zunächst von Project Server 2007 zu Project Server 2010 migrieren und dann Ihre Daten überprüfen und dann dasselbe Verfahren ausführen, wenn Sie zu jeder nachfolgenden Version migrieren. Möglicherweise möchten Sie sich mit einem Microsoft-Partner erkundigen, um Ihre Kosten mit ihren Schätzungen zu vergleichen, wie lange es für Sie dauern wird und zu welchen Kosten. 
    
## <a name="migrate-to-project-online"></a>Migrieren zu Project Online

Wenn Sie eine Migration von Project Server 2007 zu Project online durchführen, können Sie die folgenden Schritte ausführen, um die Projektplandaten manuell zu migrieren:
  
1. Speichern Sie Ihre Projektpläne von Project Server 2003 in. MPP-Format.
    
2. Wenn Sie Project Professional 2013, Project Professional 2016 oder den Project Online-Desktop-Client verwenden, öffnen Sie jede MPP-Datei, und speichern und veröffentlichen Sie Sie dann in Project online.
    
Sie können die PWA-Konfiguration manuell in Project online erstellen (beispielsweise alle erforderlichen benutzerdefinierten Felder oder Enterprise-Kalender neu erstellen). Auch Microsoft-Partner können Ihnen dabei helfen.
  
Wichtige Ressourcen:
  
|**Ressource**|**Beschreibung**|
|:-----|:-----|
|[Erste Schritte mit Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Vorgehensweise zum Einrichten und Verwenden von Project online.  <br/> |
|[Project Online Dienstbeschreibungen](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Informationen zu den verschiedenen Project Online Plänen, die Ihnen zur Verfügung stehen.  <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrieren zu einer neueren lokalen Version von Project Server

Wir sind zwar der festen Überzeugung, dass Sie durch die Migration zu Project Online den besten Wert und die Benutzeroberfläche erzielen können, aber wir verstehen auch, dass einige Organisationen Projektdaten in einer lokalen Umgebung aufbewahren müssen. Wenn Sie Ihre Projektdaten lokal beibehalten möchten, können Sie Ihre Project Server 2007-Umgebung zu Project Server 2010, Project Server 2013 oder Project Server 2016 migrieren.
  
Es wird empfohlen, zu Project Server 2016 zu migrieren, wenn Sie nicht zu Project Online migrieren können. Project Server 2016 enthält alle Features und Fortschritte, die in früheren Versionen von Project Server enthalten sind, und es entspricht am ehesten der mit Project online verfügbaren Funktionalität (einige Features sind jedoch nur in Project online verfügbar).
  
Nachdem Sie jede Migration abgeschlossen haben, sollten Sie Ihre Daten überprüfen, um sicherzustellen, dass Sie erfolgreich migriert wurden.
  
> [!NOTE]
> Wenn Sie nur die Migration zu Project Server 2010 erwägen, wenn Sie auf eine lokale Lösung beschränkt sind, ist es wichtig zu beachten, dass nur noch einige Jahre Support übrig geblieben sind. Project Server 2010 mit Service Pack 2 Ende des Support Datums ist 10/13/2020. Weitere Informationen zum Ende der Support Termine finden Sie unter [Microsoft Product Lifecycle Policy](https://go.microsoft.com/fwlink/p/?linkid=842066). 
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Wie kann ich zu Project Server 2016 migrieren?

Die architektonischen Unterschiede zwischen Project Server 2007 und Project Server 2016 verhindern einen direkten Migrationspfad. Dies bedeutet, dass Sie Ihre Project Server 2007-Daten in die nächste aufeinanderfolgende Version von Project Server migrieren müssen, bis Sie ein Upgrade auf Project Server 2016 durchführen.
  
Sie müssen die folgenden Schritte ausführen, um ein Upgrade auf Project Server 2016 durchführen zu können:
  
1. Schritt 1: Migrieren von Project Server 2007 zu Project Server 2010.
    
2. Schritt 2: Migrieren von Project Serve 2010 zu Project Server 2013.
    
3. Schritt 3: Migrieren von Project Server 2013 zu Project Server 2016.
    
Nachdem Sie jede Migration abgeschlossen haben, sollten Sie Ihre Daten überprüfen, um sicherzustellen, dass Sie erfolgreich migriert wurden.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Schritt 1: Migrieren von Project Server 2007 zu Project Server 2010

Ein umfassendes Verständnis der Schritte, die Sie für ein Upgrade von Project Server 2007 auf Project Server 2010 benötigen, finden Sie unter [Upgrade auf Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812) Inhaltspaket auf TechNet. 
  
Wichtige Ressourcen:
  
|**Ressource**|**Beschreibung**|
|:-----|:-----|
|[Project Server 2010-Upgrade (Übersicht)](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |Erfahren Sie mehr über die Schritte, die Sie für ein Upgrade von Project Server 2007 auf Project Server 2010 benötigen.  <br/> |
|[Planen des Upgrades auf Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |Sehen Sie sich die Planungsüberlegungen an, die Sie beim Upgrade von Project Server 2007 auf Project Server 2010, einschließlich System Anforderungen, vornehmen müssen.  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Wie aktualisiere ich?

Während im [Upgrade auf Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812) Inhalts Satzes Details zum Upgrade gefunden werden, müssen Sie sich bewusst sein, dass es zwei verschiedene Methoden gibt, mit denen Sie ein Upgrade durchführen können: 
  
- **Upgrade mit Datenbankanfügung:** Diese Methode aktualisiert nur den Inhalt Ihrer Umgebung und nicht die Konfigurationseinstellungen. Dies ist erforderlich, wenn Sie ein Upgrade von Office Project Server 2007 bereitstellen, die auf Hardware installiert ist, die nur ein 32-Bit-Server Betriebssystem unterstützt. Es gibt zwei Arten von Upgrades durch Datenbankanfügungen: 
    
  - **Vollständiges Upgrade mit Datenbankanfügung** : migriert die in den Office Project Server 2007 Datenbanken gespeicherten Projektdaten sowie die in einer SharePoint-Inhaltsdatenbank gespeicherten Microsoft Project Web App (PWA)-Website Daten. 
    
  - **Core-Upgrade mit Datenbankanfügung** – migriert nur die Projektdaten, die in den Project Server-Datenbanken gespeichert sind. 
    
- **Direktes Upgrade**: die Konfigurationsdaten für die Farm und alle Inhalte in der Farm werden in einer festen Reihenfolge auf der vorhandenen Hardware aktualisiert. Wenn Sie den Prozess der direkt Aktualisierung starten, wird die gesamte Farm offline geschaltet, und die Websites und Microsoft Project Web App-Websites sind erst verfügbar, wenn das Upgrade abgeschlossen ist, und dann wird der Server neu gestartet. Nach dem Start eines direkten Upgrades können Sie das Upgrade nicht anhalten oder die Installation auf die vorherige Version zurücksetzen. Es wird dringend empfohlen, ein gespiegeltes Abbild Ihrer Produktionsumgebung zu erstellen und das in-Place-Upgrade in dieser Umgebung und nicht in Ihrer Produktionsumgebung durchzuführen. 
    
Weitere Ressourcen:
  
- [Superflow für Microsoft Project Server 2010-Upgrade](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [Migration von Project Server 2007 auf Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Überlegungen zu Upgrades für Project Web App Webparts](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [Project Software Development Kit (SDK)](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>Schritt 2: Migrieren zu Project Server 2013

Nach der Migration zu Project Server 2010 und überprüfen, ob Ihre Daten erfolgreich migriert wurden, besteht der nächste Schritt darin, Ihre Daten zu Project Server 2013 zu migrieren.
  
Eine umfassende Erläuterung der Schritte, die Sie für ein Upgrade von Project Server 2010 auf Project Server 2013 ausführen müssen, finden Sie unter [Upgrade auf Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822) Inhaltspaket auf TechNet. 
  
Wichtige Ressourcen:
  
|**Ressource**|**Beschreibung**|
|:-----|:-----|
|[Übersicht über den Project Server 2013-Upgradevorgang](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |Hier erfahren Sie, was Sie für ein Upgrade von Project Server 2010 auf Project Server 2013 tun müssen.  <br/> |
|[Planen des Upgrades auf Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |Sehen Sie sich die Planungsüberlegungen an, die Sie beim Upgrade von Project Server 2010 auf Project Server 2013, einschließlich System Anforderungen, vornehmen müssen.  <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Wissenswerte zum Upgrade auf diese Version

[Was ist neu in Project Server 2013-Upgrade](https://go.microsoft.com/fwlink/p/?linkid=841824) gibt Ihnen einige wichtige Änderungen für das Upgrade für diese Version, das bemerkenswerteste: 
  
- Es gibt kein direktes Upgrade auf Project Server 2013. Die Methode der Datenbankanfügung ist die einzige unterstützte Methode für ein Upgrade von Project Server 2010 auf Project Server 2013.
    
- Durch den Upgradeprozess werden nicht nur Ihre Project Server 2010 Daten in Project Server 2013 Format konvertiert, sondern auch die vier Project Server 2010 Datenbanken werden in einer einzigen Project Web App Datenbank konsolidiert.
    
- Sowohl SharePoint Server 2013 als auch Project Server 2013 wurden in die anspruchsbasierte Authentifizierung aus der vorherigen Version geändert. Wenn Sie die klassische Authentifizierung verwenden, müssen Sie beim Upgrade Überlegungen vornehmen. Weitere Informationen finden Sie unter [Migrieren von der klassischen Authentifizierung zur anspruchsbasierten Authentifizierung in SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=841825).
    
Weitere Ressourcen:
  
- [Übersicht über den Prozess zum Upgrade auf Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Upgrade der Datenbanken und Project Web App-Websitesammlungen (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Microsoft Project Server-Aktualisierungsprozess (Diagramm)](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [Die große Datenbankkonsolidierung Project Server 2010 zu 2013 Migration in 8 einfachen Schritten](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Schritt 3: Migrieren zu Project Server 2016

Nach der Migration zu Project Server 2013 und überprüfen, ob Ihre Daten erfolgreich migriert wurden, besteht der nächste Schritt darin, Ihre Daten zu Project Server 2016 zu migrieren.
  
Ein umfassendes Verständnis der Schritte, die Sie für ein Upgrade von Project Server 2013 auf Project Server 2016 ausführen müssen, finden Sie unter Upgrade to Project Server 2016 Content Sets on TechNet.
  
Wichtige Ressourcen:
  
|**Ressource**|**Beschreibung**|
|:-----|:-----|
|[Übersicht über den Project Server 2016-Upgradevorgang](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |Erfahren Sie, wie Sie ein Upgrade von Project Server 2013 auf Project Server 2016 durchführen müssen.  <br/> |
|[Planen des Upgrades auf Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |Sehen Sie sich die Planungsüberlegungen an, die Sie beim Upgrade von Project Server 2013 auf Project Server 2016 vornehmen müssen, einschließlich.  <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Wissenswerte zum Upgrade auf diese Version

[Dinge, die Sie über das Project Server 2016-Upgrade wissen müssen](https://go.microsoft.com/fwlink/p/?linkid=841827) , enthalten einige wichtige Änderungen für das Upgrade für diese Version, einschließlich: 
  
- Beachten Sie beim Erstellen der Project Server 2016-Umgebung, in der die Project Server 2013 Daten migriert werden sollen, dass die Installationsdateien für Project Server 2016 in SharePoint Server 2016 enthalten sind. Weitere Informationen finden Sie unter [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).
    
- Ressourcenpläne sind in Project Server 2016 veraltet. Ihre Project Server 2013 Ressourcenpläne werden zu Ressourcen Projekten in Project Server 2016 und in Project Online migriert. Weitere Informationen finden Sie unter [Übersicht: Ressourcen Engagements](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) . 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migrieren von Portfolio Server 2007

Project Portfolio Server 2007 wurde zusammen mit Project Server 2007 für Portfolio Strategie, Priorisierung und Optimierung verwendet. Nach dieser Version wurden keine weiteren Versionen von Project Portfolio Server erstellt. Portfolio Verwaltungsfeatures sind jedoch sowohl in Project Server 2016 als auch in der Premium-Version von Project online verfügbar. Daten aus Project Portfolio Server 2007 können nicht zu einer migriert werden. Daten wie Geschäftstreiber müssen neu erstellt werden.
  
Weitere Ressourcen:
  
- [Project Online Service Beschreibungen](https://go.microsoft.com/fwlink/p/?linkid=841280): Weitere Informationen finden Sie in den Features zur Portfolioverwaltung, die in Project Server 2016 und Project Online Premium enthalten sind.
    
- [Migrationshandbuch für Microsoft Office Project Portfolio Server 2007](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Verwandte Themen

[SharePoint Server 2007-Roadmap für das Ende des Supports](sharepoint-2007-end-of-support.md)
  
[Ressourcen für das Upgrade von Office 2007-Servern und-Clients](upgrade-from-office-2007-servers-and-products.md)
  

