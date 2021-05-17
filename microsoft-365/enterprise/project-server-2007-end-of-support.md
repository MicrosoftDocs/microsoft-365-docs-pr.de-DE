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
description: Am 10. Oktober 2017 wurde der Support für Project Server 2007, Project Portfolio Server und Project 2007 beendet. Verwenden Sie diesen Artikel, um ihr Upgrade jetzt zu planen.
ms.openlocfilehash: 12447eb2a021b3f92e3557b2c3ea87e859841346
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927348"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Ende der Unterstützung für Project Server 2007 – Roadmap

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Die Unterstützung für Office 2007-Server und -Anwendungen wurde 2017 beendet, und Sie müssen Pläne für die Migration berücksichtigen. Wenn Sie derzeit Project Server 2007 und verwandte Produkte verwenden, beachten Sie die folgenden End-of-Support-Datumsangaben:
  
|**Produkt**|**Ende des Supportdatums**|
|:-----|:-----|
|Project Server 2007  <br/> |10. Oktober 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10. Oktober 2017  <br/> |
|Project 2007 Standard  <br/> |10. Oktober 2017  <br/> |
|Project 2007 Professional  <br/> |10. Oktober 2017  <br/> |
   
Weitere Informationen zu Office 2007-Servern, die die Rente erreichen, finden Sie unter [Upgrade from Office 2007 servers and client products](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>Was bedeutet *das Ende der Unterstützung?*

Die meisten #A0 verfügen über einen Supportlebenszyklus, in dem sie neue Features, Fehlerbehebungen, Sicherheitskorrekturen und so weiter erhalten. Dieser Lebenszyklus dauert in der Regel 10 Jahre nach der ersten Produktversion. Das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Da Project Server 2007 am 10. Oktober 2017 sein Ende erreicht hat, bietet Microsoft nicht mehr:
  
- Technischer Support für Probleme, die auftreten können.
    
- Fehlerbehebungen für Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können.
    
- Sicherheitsbehebungen für Sicherheitsrisiken, die den Server anfällig für Sicherheitsverletzungen machen können.
    
- Zeitzonenupdates.
    
Die Installation von Project Server 2007 wird nach diesem Datum fortgesetzt. Aufgrund der zuvor aufgeführten Änderungen wird jedoch dringend empfohlen, von Project Server 2007 so bald wie möglich zu migrieren.
  
## <a name="what-are-my-options"></a>Was sind meine Optionen?

Wenn Sie Project Server 2007 verwenden, müssen Sie die folgenden Migrationsoptionen erkunden:
  
- Migrieren zu Project Online
    
- Migrieren zu einer neueren lokalen Version von Project Server (vorzugsweise Project Server 2016)
    
|**Warum würde ich es vorziehen, zu Project Online**|**Warum würde ich es vorziehen, zu Project Server 2016**|
|:-----|:-----|
| Ich habe mobile Benutzer.  <br/> <br/>Die Kosten für die Migration sind ein wesentliches Problem (Hardware, Software, Stunden und Implementierungsaufwand). <br/><br/>  Nach der Migration sind die Kosten für die Wartung meiner Umgebung ein hauptanliegend (z. B. automatische Updates, garantierte Uptime, und so weiter).  <br/> | Geschäftsregeln beschränken mich am Betrieb meines Unternehmens in der Cloud.<br/><br/>  Ich muss die Kontrolle über Updates für meine Umgebung haben.  |
   
> [!NOTE]
> Weitere Informationen zu Optionen für den Wechsel von Ihren Office 2007-Servern finden Sie unter Ressourcen, die Ihnen beim Upgrade von [Office 2007-Servern](upgrade-from-office-2007-servers-and-products.md)und -Clients helfen. Beachten Sie, Project Server keine Hybridkonfiguration unterstützt, da Project Server und Project Online nicht denselben Ressourcenpool gemeinsam nutzen können. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Wichtige Überlegungen bei der Migration von Project Server 2007

Berücksichtigen Sie folgendes, wenn Sie eine Migration von Project Server 2007 planen:
  
- **Hilfe von einem Microsoft-Partner** erhalten – Das Upgrade von Project Server 2007 kann eine Herausforderung sein und erfordert viel Vorbereitung und Planung. Es kann besonders schwierig sein, wenn Sie nicht die Person waren, die server 2007 ursprünglich Project eingerichtet hat. Glücklicherweise gibt es Microsoft-Partner, die ihnen helfen können, unabhängig davon, ob Sie eine Migration zu Project Server 2016 oder zu Project Online. Suchen Sie nach einem Microsoft Partner, der Ihnen bei der Migration im [Microsoft Partner Center hilft.](https://go.microsoft.com/fwlink/p/?linkid=841249) Suchen Sie nach dem Begriff *Gold Project portfolio management,* um eine Liste aller Microsoft-Partner zu sehen, die über Fachwissen in Project. 
    
- **Planen Ihrer** Anpassungen – Viele der Anpassungen, die Sie in Ihrer Project Server 2007-Umgebung vorgenommen haben, funktionieren möglicherweise nicht, wenn Sie zu Project Server 2016 oder Project Online. Es gibt erhebliche Unterschiede in Project Serverarchitektur zwischen den Versionen. Die erforderlichen Betriebssysteme, Datenbankserver und Clientwebbrowser, die unterstützt werden, unterscheiden sich ebenfalls. Planen, wie Sie Ihre Anpassungen für die neue Umgebung testen oder neu erstellen. Die Planung bietet auch eine gute Möglichkeit, zu überlegen, ob jede Anpassung noch erforderlich ist. Weitere Informationen finden Sie unter [Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013). 
    
- **Zeit und Geduld** – Upgradeplanung, -ausführung und -tests werden Zeit und Mühe erfordern, insbesondere wenn Sie ein Upgrade auf Project Server 2016. Wenn Sie beispielsweise von Project Server 2007 zu Project Server 2016 migrieren, müssen Sie zuerst zu Project Server 2010 migrieren, Ihre Daten überprüfen und dann dasselbe tun, wenn Sie zu jeder nachfolgenden Version migrieren. Möglicherweise möchten Sie sich mit einem Microsoft-Partner informieren, um Schätzungen darüber zu erhalten, wie lange es dauern wird und was es kosten wird.
    
## <a name="migrate-to-project-online"></a>Migrieren zu Project Online

Wenn Sie von Project Server 2007 zu Project Online migrieren, können Sie die folgenden Schritte ausführen, um Ihre Projektplandaten manuell zu migrieren:
  
1. Speichern Sie Ihre Projektpläne aus Project Server 2003 in das MPP-Format.
    
2. In Project Professional 2013 öffnen Project Professional 2016 oder der Project Online-Desktopclient jede MPP-Datei, und speichern und veröffentlichen Sie sie dann in Project Online.
    
Sie können Ihre Microsoft Project Web App (PWA) manuell in einer Project Online. Erstellen Sie beispielsweise alle erforderlichen benutzerdefinierten Felder oder Unternehmenskalender neu. Microsoft Partners kann bei diesem Prozess ebenfalls hilfreich sein.
  
Wichtige Ressourcen:
  
|**Resource**|**Beschreibung**|
|:-----|:-----|
|[Erste Schritte mit Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Einrichten und Verwenden von Project Online <br/> |
|[Project Online Dienstbeschreibungen](/office365/servicedescriptions/project-online-service-description/project-online-service-description) <br/> |Informationen zu den verschiedenen Project Online, die Ihnen zur Verfügung stehen <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrieren zu einer neueren lokalen Version von Project Server

Wir sind fest davon überzeugt, dass Sie den besten Nutzen und die beste Benutzererfahrung erhalten, indem Sie zu Project Online. Wir wissen aber auch, dass einige Organisationen Projektdaten in einer lokalen Umgebung speichern müssen. Wenn Sie Ihre Projektdaten lokal speichern möchten, können Sie Ihre Project Server 2007-Umgebung zu Project Server 2010, Project Server 2013 oder Project Server 2016.
  
Wenn Sie nicht zu Project Online migrieren können, wird empfohlen, zu Project Server 2016. Project Server 2016 enthält alle Features früherer Versionen von Project Server. Es entspricht am besten der mit Project Online, obwohl einige Features nur in der Project Online.
  
Nach jeder Migration sollten Sie überprüfen, ob Ihre Daten erfolgreich migriert wurden.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Wie kann ich zu Project Server 2016?

Architekturunterschiede zwischen Project Server 2007 und Project Server 2016 verhindern einen direkten Migrationspfad. Daher müssen Sie Ihre Project Server 2007-Daten zu jeder nachfolgenden Version von Project Server migrieren, bis Sie Project Server 2016.
  
Führen Sie die folgenden Schritte aus, Project Server 2016:
  
1. Migrieren Sie von Project Server 2007 zu Project Server 2010.
    
2. Migrieren Sie von Project Serve 2010 zu Project Server 2013.
    
3. Migrieren Sie von Project Server 2013 zu Project Server 2016.
    
Stellen Sie nach jeder Migration sicher, dass Ihre Daten erfolgreich migriert wurden.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Schritt 1: Migrieren von Project Server 2007 zu Project Server 2010

Eine umfassende Beschreibung der Zum Upgrade von Project Server 2007 auf Project Server 2010 müssen Sie unter [Upgrade to Project Server 2010](/previous-versions/office/project-server-2010/gg502590(v=office.14))ausführen.
  
Wichtige Ressourcen:
  
|**Resource**|**Beschreibung**|
|:-----|:-----|
|[Project Übersicht über das Server 2010-Upgrade](/previous-versions/office/project-server-2010/ee662496(v=office.14)) <br/> |Eine ansicht auf hoher Ebene, was Sie zum Upgrade von Project Server 2007 auf Project Server 2010 tun müssen <br/> |
|[Planen eines Upgrades auf Project Server 2010](/previous-versions/office/project-server-2010/ff603505(v=office.14)) <br/> |Planungsüberlegungen beim Upgrade von Project Server 2007 auf Project Server 2010, einschließlich Systemanforderungen  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Wie kann ich ein Upgrade durchführen?

Weitere Informationen finden Sie unter [Upgrade to Project Server 2010](/previous-versions/office/project-server-2010/gg502590(v=office.14)). Es ist jedoch wichtig zu wissen, dass es zwei unterschiedliche Methoden gibt, die Sie zum Upgrade verwenden können:
  
- **Upgrade durch Datenbank-Anfügen:** Diese Methode aktualisiert nur den Inhalt für Ihre Umgebung, nicht die Konfigurationseinstellungen. Dies ist erforderlich, wenn Sie ein Upgrade von Office Project Server 2007 durchführen, der auf Hardware bereitgestellt wird, die nur ein 32-Bit-Serverbetriebssystem unterstützt. Es gibt zwei Arten von Upgrademethoden zum Anfügen von Datenbanken:
    
  - **** Vollständiges Upgrade durch Datenbank anfügen – Migriert die in den Office Project Server 2007-Datenbanken gespeicherten Projektdaten sowie die Microsoft Project Web App-Websitedaten, die in einer SharePoint gespeichert sind.
    
  - **Datenbank-Anfügen *eines Kernupgrades*** – Migriert nur die projektdaten, die in den Project Serverdatenbanken gespeichert sind.
    
- **In-Place-Upgrade:** Die Konfigurationsdaten für die Farm und alle Inhalte in der Farm werden auf der vorhandenen Hardware in einer festen Reihenfolge aktualisiert. Wenn Sie den Upgradevorgang starten, wird die gesamte Farm vom Setup offline geschaltet. Die Websites und Microsoft Project Web -App-Websites sind nicht verfügbar, bis das Upgrade abgeschlossen ist, und dann wird der Server neu gestartet. Nachdem Sie mit einem tatsächlichen Upgrade begonnen haben, können Sie das Upgrade nicht anhalten oder ein Rollback zur vorherigen Version durchführen. Es ist am besten, ein gespiegeltes Bild Ihrer Produktionsumgebung zu erstellen und das in-place-Upgrade auf diese Umgebung zu durchführen, nicht in Ihrer Produktionsumgebung. 
    
Zusätzliche Ressourcen:
  
- [SuperFlow für Microsoft Project Server 2010-Upgrade](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Migration von Project Server 2007 zu Project Server 2010](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Überlegungen zum Upgrade Project Web App Webparts](/previous-versions/office/project-server-2010/gg314581(v=office.14))
    
- [Project Software Development Kit (SDK)](/previous-versions/office/developer/office-2010/ms481966(v=office.14))
    
### <a name="step-2-migrate-to-project-server-2013"></a>Schritt 2: Migrieren zu Project Server 2013

Nachdem Sie überprüft haben, ob Ihre Daten erfolgreich migriert wurden, besteht der nächste Schritt in der Migration zu Project Server 2013.
  
Eine umfassende Beschreibung der für das Upgrade von Project Server 2010 auf Project Server 2013 benötigten Maßnahmen finden Sie unter [Upgrade to Project Server 2013](/project/upgrade-to-project-server-2016). 
  
Wichtige Ressourcen:
  
|**Resource**|**Beschreibung**|
|:-----|:-----|
|[Übersicht über den Project Server 2013-Upgradevorgang](/project/upgrade-to-project-server-2016) <br/> |Übersicht über die Zum Upgrade von Project Server 2010 auf Project Server 2013  <br/> |
|[Planen eines Upgrades auf Project Server 2013](/project/plan-for-upgrade-to-project-server-2016) <br/> |Planungsüberlegungen beim Upgrade von Project Server 2010 auf Project Server 2013, einschließlich Systemanforderungen <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Informationen zum Upgrade auf diese Version

[Neuerungen in Project Server 2013-Upgrades](/project/what-s-new-in-project-server-2013-upgrade) beschreiben wichtige Änderungen für das Upgrade für diese Version. Die wichtigsten sind: 
  
- Es gibt kein in-place-Upgrade auf Project Server 2013. Die Database-Attach-Methode ist die einzige unterstützte Methode für das Upgrade von Project Server 2010 auf Project Server 2013.
    
- Der Upgradeprozess konvertiert nicht nur Ihre Project Server 2010-Daten in das Project Server 2013-Format, sondern konsolidiert auch die vier Project Server 2010-Datenbanken in einer einzelnen Project Web App-Datenbank.
    
- In den Versionen von 2013 wurden sowohl SharePoint Server als auch Project Server in anspruchsbasierte Authentifizierung geändert. Wenn Sie die klassische Authentifizierung verwenden, müssen Sie diesen Faktor für Ihr Upgrade berücksichtigen. Weitere Informationen finden Sie unter [Migrieren von der klassischen Authentifizierung zur anspruchsbasierten Authentifizierung in SharePoint 2013](/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server).
    
Zusätzliche Ressourcen:
  
- [Übersicht über den Prozess zum Upgrade auf Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)
    
- [Upgrade der Datenbanken und Project Web App-Websitesammlungen (Project Server 2013)](/project/upgrading-to-project-server-2016)
    
- [Microsoft Project Diagramm des Serverupgradeprozesses](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [The Great Database Consolidation, Project Server 2010 to 2013 migration in 8 easy steps](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Schritt 3: Migrieren zu Project Server 2016

Nachdem Sie sichergestellt haben, dass Ihre Daten erfolgreich migriert wurden, besteht der nächste Schritt in der Migration zu Project Server 2016.
  
Eine umfassende Beschreibung der Zum Upgrade von Project Server 2013 auf Project Server 2016 finden Sie unter [Upgrade to Project Server 2016](//project/upgrading-to-project-server-2016).
  
Wichtige Ressourcen:
  
|**Resource**|**Beschreibung**|
|:-----|:-----|
|[Übersicht über den Project Server 2016-Upgradevorgang](/previous-versions/office/project-server-2010/ee662104(v=office.14)) <br/> |Übersicht darüber, was Sie tun müssen, um ein Upgrade von Project Server 2013 auf Project Server 2016 <br/> |
|[Planen des Upgrades auf Project Server 2016](/project/plan-for-upgrade-to-project-server-2016) <br/> |Planungsüberlegungen, die Sie von Project Server 2013 auf Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Informationen zum Upgrade auf diese Version

[Was Sie über das upgrade Project Server 2016 wissen](/project/plan-for-upgrade-to-project-server-2016) müssen, enthält einige wichtige Änderungen für das Upgrade für diese Version, die Folgendes umfassen:
  
- Wenn Sie Ihre Project Server 2016 erstellen, zu der Sie Ihre Project Server 2013-Daten migrieren, sind die Project Server 2016-Installationsdateien in SharePoint Server 2016 enthalten. Weitere Informationen finden Sie unter [Deploy Project Server 2016](/project/deploy-project-server-2016).
    
- Ressourcenpläne sind in der Project Server 2016. Ihre Project Server 2013-Ressourcenpläne werden zu Ressourcen engagements in Project Server 2016 und in Project Online. Weitere [Informationen finden Sie unter Overview: Resource engagements.](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migrieren von Portfolio Server 2007

Project Portfolio Server 2007 wurde zusammen mit Project Server 2007 für Portfoliostrategie, Priorisierung und Optimierung verwendet. Nach dieser Version Project keine weiteren Versionen von Portfolio Server erstellt. Portfolioverwaltungsfeatures sind jedoch in Project Server 2016 und der Premium version von Project Online. Daten aus Project Portfolio Server 2007 können jedoch nicht zu beiden migriert werden. Daten wie z. B. Geschäftstreiber müssen neu erstellt werden.
  
Weitere Ressourcen:
  
- [Project Online Dienstbeschreibungen:](/office365/servicedescriptions/project-online-service-description/project-online-service-description) Sehen Sie sich die Portfolioverwaltungsfeatures an, die in Project Server 2016 und Project Online Premium.
    
- [Microsoft Office Project Portfolio Server 2007-Migrationshandbuch.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Verwandte Themen

[SharePoint Roadmap zum Ende des Support für Server 2007](sharepoint-2007-end-of-support.md)
  
[Ressourcen, die Ihnen beim Upgrade von Office 2007-Servern und -Clients helfen](upgrade-from-office-2007-servers-and-products.md)
