---
title: Upgrade von SharePoint 2010
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- WSU140
- OSU140
ms.assetid: 985a357f-6db7-401f-bf7a-1bafdf1f312c
f1.keywords:
- NOCSH
description: Hier finden Sie Informationen und Ressourcen für ein Upgrade von SharePoint 2010 und SharePoint Server 2010 als Unterstützung für beide Enden am 13. Oktober 2020.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 57e44cf14a74f6a5a2098512e0a2339037d70655
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690277"
---
# <a name="upgrading-from-sharepoint-2010"></a>Upgrade von SharePoint 2010

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft SharePoint 2010 und SharePoint Server 2010 werden am **13. April 2021**am Ende der Unterstützung erreichen. In diesem Artikel werden die Ressourcen erläutert, die Sie beim Migrieren Ihrer vorhandenen SharePoint Server 2010 Daten zu SharePoint Online in Microsoft 365 oder beim Upgrade Ihrer lokalen SharePoint Server 2010 Umgebung unterstützen.
  
## <a name="what-is-end-of-support"></a>Was ist das Ende der Unterstützung?

Wenn Ihre SharePoint Server 2010 und SharePoint Foundation 2010 Software das Ende Ihres Support-Lebenszyklus erreicht (die Zeit, in der Microsoft neue Funktionen, Bugfixes, Sicherheitsfixes usw. bereitstellt), wird dies als "Ende der Unterstützung" der Software oder manchmal als "Ruhestand" bezeichnet. Nach Abschluss der Unterstützung (oder EOS) eines Produkts wird nichts tatsächlich beendet oder funktioniert nicht mehr. am Ende der Softwareunterstützung stellt Microsoft jedoch nicht mehr Folgendes bereit:
  
- Technischer Support für Probleme, die auftreten können;
    
- Fehlerbehebungen für erkannte Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können;
    
- Sicherheitsfixes für Sicherheitsanfälligkeiten, die erkannt werden und die den Server möglicherweise anfällig für Sicherheitsverletzungen machen;
    
- Zeitzonenaktualisierungen.
    
Das heißt, es werden keine weiteren Updates, Patches oder Fixes für das Produkt ausgeliefert (einschließlich Sicherheitspatches/Fixes), und der Microsoft-Support hat seine Support Bemühungen in neuere Versionen vollständig verschoben. Als Ende der Unterstützung SharePoint Server 2010 Ansätze sollten Sie die Möglichkeiten nutzen, um Daten zu kürzen, die Sie vor dem Upgrade des Produkts nicht mehr benötigen, und/oder Ihre wichtigen Daten migrieren.
  
> [!NOTE]
> Ein Software-Lebenszyklus dauert in der Regel zehn Jahre ab dem Datum der ersten Veröffentlichung des Produkts. Sie können nach [Microsoft Solution Providern](https://go.microsoft.com/fwlink/?linkid=841249) suchen, die beim Upgrade auf die nächste Version Ihrer Software helfen können, oder mit Microsoft 365 Migration (oder beides). Stellen Sie sicher, dass Sie wissen, dass Sie unter Stützungs Termine für wichtige zugrunde liegende Technologien kennen, insbesondere der Version von SQL Server, die Sie mit SharePoint verwenden. Unter [Fixed Lifecycle Policy](https://support.microsoft.com/help/14085) erfahren Sie, wie Sie den Produktlebenszyklus detailliert verstehen.
  
## <a name="what-are-my-options"></a>Was sind meine Optionen?

Überprüfen Sie zunächst das Datum, an dem der Support auf der [Produktlebenszyklus-Website](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010)endet. Stellen Sie als nächstes sicher, dass Sie Ihr Upgrade oder Ihre Migrationszeit mit Kenntnis dieses Datums planen. Denken Sie daran, dass Ihr Produkt am angegebenen Datum  *nicht mehr funktioniert*  , und Sie können seine Verwendung fortsetzen, aber da Ihre Installation nach diesem Datum nicht mehr gepatcht wird, benötigen Sie eine Strategie, die Ihnen einen reibungslosen Übergang zur nächsten Version des Produkts erleichtern wird. 
  
Diese Matrix hilft beim Plotten eines Kurses, wenn es um die Migration von Produktfeatures und Benutzerdaten geht:
  
| Ende des Support Produkts | Gut | Optimal |
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013 (lokal)  <br/> |SharePoint Online  <br/> |
||SharePoint Server 2013 Hybrid mit SharePoint Online  <br/> |SharePoint Server 2016 (lokal)  <br/> |
| | |SharePoint-Cloud-Hybrid Suche  <br/> |
   
Wenn Sie Optionen am unteren Ende der Skala (gute Optionen) auswählen, müssen Sie mit der Planung eines weiteren Upgrades beginnen, sobald die Migration von SharePoint Server 2010 abgeschlossen ist. 

Hier sind die drei Pfade, die Sie ausführen können, um das Ende der Unterstützung für SharePoint Server 2010 zu vermeiden.

![SharePoint Server 2010 Aktualisierungspfade](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

>[!Note]
>Das Ende der Unterstützung für SharePoint Server 2010 und SharePoint Foundation 2010 sind für den 13. April 2021 geplant, *Bitte* beachten Sie jedoch, dass Sie immer auf der [Produktlebenszyklus-Website](https://support.microsoft.com/lifecycle) nach den aktuellsten Terminen suchen sollten.
>

  
## <a name="where-should-i-go-next"></a>Wohin sollte ich als nächstes wechseln?

SharePoint Server 2013 und SharePoint Foundation 2013 können lokal auf Ihren eigenen Servern installiert werden. Andernfalls können Sie SharePoint Online verwenden, bei dem es sich um einen Online Dienst handelt, der Bestandteil von Microsoft Microsoft 365 ist. Sie können Folgendes auswählen:
  
- Migrieren zu SharePoint Online
    
- Upgrade SharePoint Server oder SharePoint Foundation lokal
    
- Beides
    
- Implementieren einer [SharePoint-Hybrid](https://docs.microsoft.com/sharepoint/hybrid/hybrid) Lösung 
    
Beachten Sie die versteckten Kosten, die im Zusammenhang mit der Wartung einer Serverfarm in Zukunft, beim warten oder Migrieren von Anpassungen und beim Upgraden der Hardware, von der SharePoint Server abhängt, abhängen. Wenn Sie alle diese Informationen kennen und berücksichtigt haben, ist es einfacher, das Upgrade lokal fortzusetzen. Andernfalls können Sie von einer geplanten Migration zu SharePoint Online profitieren, wenn Sie die Farm auf älteren SharePoint-Servern ohne starke Anpassung ausführen. Es ist auch möglich, dass Sie für Ihre lokale SharePoint Server Umgebung möglicherweise einige Daten in SharePoint Online einfügen, um die Hardwareverwaltung zu reduzieren, die alle lokalen Daten umfasst. Es ist möglicherweise sparsamer, einige Ihrer Daten in SharePoint Online zu verlagern.
  
> [!NOTE]
> SharePoint-Administratoren erstellen möglicherweise ein Microsoft 365-Abonnement, richten eine brandneue SharePoint Online Website ein und schneiden dann sauber von SharePoint Server 2010 ab, wobei nur die wichtigsten Dokumente auf die neuen SharePoint Online Websites übermittelt werden. Von dort aus können alle verbleibenden Daten von der SharePoint Server 2010 Website in lokale Archive entwässert werden. 
  
|**SharePoint Online**|**SharePoint Server lokal**|
|:-----|:-----|
|Hohe Kosten in der Zeit (Planung/Ausführung/Überprüfung)  <br/> |Hohe Kosten in der Zeit (Planung/Ausführung/Überprüfung)  <br/> |
|Geringere Kosten in Fonds (keine hardwarekäufe)  <br/> |Höhere Kosten in Fonds (hardwarekäufe)  <br/> |
|Einmalige Kosten bei der Migration  <br/> |Wiederholte einmalige Kosten pro künftiger Migration  <br/> |
|Niedrige Total Cost of Ownership/Maintenance  <br/> |Hohe Gesamtbetriebskosten/Wartung  <br/> |
   
Wenn Sie eine Migration zu Microsoft 365 durchführen, wird der Zeitaufwand für die einmalige Planung höher (während Sie Daten organisieren und entscheiden, was Sie in die Cloud übernehmen und was Sie zurücklassen müssen). Nachdem Ihre Daten migriert wurden, werden Upgrades dann automatisch von diesem Zeitpunkt aus durchführen, da Sie keine Hardware-und Softwareupdates mehr verwalten müssen und die Dauer der Farm durch eine Vereinbarung zum Service Level ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)) von Microsoft gesichert wird.
  
### <a name="migrate-to-sharepoint-online"></a>Migrieren zu SharePoint Online

Stellen Sie sicher, dass SharePoint Online alle erforderlichen Funktionen bietet, indem Sie die zugehörige [Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description)überprüfen.
  
Es gibt derzeit kein Mittel, mit dem Sie direkt von SharePoint Server 2010 (oder SharePoint Foundation 2010) zu SharePoint Online migrieren können, sodass ein Großteil der Arbeit manuell erfolgt. Dadurch erhalten Sie die Möglichkeit, Daten und Websites, die nicht mehr benötigt werden, vor dem Wechsel zu archivieren und zu löschen. Sie können andere Daten in den Speicher archivieren. Denken Sie auch daran, dass weder SharePoint Server 2010 noch SharePoint Foundation 2010 am Ende der Unterstützung nicht mehr funktioniert, sodass Administratoren einen Zeitraum haben können, in dem SharePoint noch ausgeführt wird, wenn Ihre Kunden vergessen, einige Ihrer Daten zu verlegen.
  
Wenn Sie ein Upgrade auf SharePoint Server 2013 oder SharePoint Server 2016 durchführen und sich dafür entscheiden, Daten in SharePoint Online zu übertragen, kann ihre Verlagerung auch die Verwendung der [SharePoint-Migrations-API](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) (zum Migrieren von Informationen zu OneDrive für Unternehmen) umfassen. 
  
|**SharePoint Online Vorteil**|**SharePoint Online Nachteil**|
|:-----|:-----|
|Microsoft liefert SPO-Hardware und die gesamte Hardwareverwaltung.  <br/> |Die verfügbaren Features können zwischen SharePoint Server lokal und SPO unterschiedlich sein.  <br/> |
|Sie sind der globale Administrator Ihres Abonnements und können Administratoren den SPO-Websites zuweisen.  <br/> |Einige Aktionen, die einem Farm Administrator in SharePoint Server lokal zur Verfügung stehen, sind in der SharePoint-Administratorrolle in Microsoft 365 nicht vorhanden (oder sind nicht erforderlich), SharePoint-Verwaltung, Websitesammlungsverwaltung und Website Besitz sind jedoch lokal in Ihrer Organisation.  <br/> |
|Microsoft wendet Patches, Fixes und Updates auf zugrunde liegende Hardware und Software an (einschließlich SQL-Servern, auf denen SharePoint Online ausgeführt wird).  <br/> |Da es keinen Zugriff auf das zugrunde liegende Dateisystem im Dienst gibt, sind einige Anpassungen begrenzt.  <br/> |
|Microsoft veröffentlicht [Vereinbarungen zum Service Level](https://go.microsoft.com/fwlink/?linkid=843153) und wird schnell zur Lösung von Vorfällen auf Dienstebene verschoben.  <br/> |Sicherungs-und Wiederherstellungsoptionen und andere Wiederherstellungsoptionen werden vom Dienst in SharePoint Online automatisiert – Sicherungen werden überschrieben, wenn Sie nicht verwendet werden.  <br/> |
|Sicherheitstests und die Optimierung der Serverleistung werden laufend im Dienst von Microsoft ausgeführt.  <br/> |Änderungen an der Benutzeroberfläche und anderen SharePoint-Features werden vom Dienst installiert und müssen möglicherweise aktiviert oder deaktiviert werden.  <br/> |
|Microsoft 365 erfüllt viele Branchenstandards: [Microsoft Compliance-Angebote](https://go.microsoft.com/fwlink/?linkid=843165).  <br/> |Die [Pannen](https://go.microsoft.com/fwlink/?linkid=518597) Unterstützung für die Migration ist limitiert.  <br/> Ein Großteil des Upgrades wird manuell durchführen oder über die SPO-Migrations-API, die in der [Roadmap für Migrations Inhalte für SharePoint Online und OneDrive](https://go.microsoft.com/fwlink/?linkid=843184)beschrieben wird.  <br/> |
|Weder Microsoft-Support Techniker noch Mitarbeiter im Rechenzentrum haben uneingeschränkten Administratorzugriff auf Ihr Abonnement.  <br/> |Es kann zusätzliche Kosten entstehen, wenn die Hardware Infrastruktur aktualisiert werden muss, um die neuere Version von SharePoint zu unterstützen, oder wenn eine sekundäre Farm für das Upgrade erforderlich ist.  <br/> |
|Lösungsanbieter können die einmalige Aufgabe der Migration Ihrer Daten zu SharePoint Online unterstützen.  <br/> |Nicht alle Änderungen an SharePoint Online befinden sich in Ihrem Steuerelement. Nach der Migration können sich Design Unterschiede in Menüs, Bibliotheken und anderen Features vorübergehend auf die Benutzerfreundlichkeit auswirken.  <br/> |
|Online Produkte werden automatisch über den Dienst aktualisiert, was bedeutet, dass Features zwar veraltet sein können, es jedoch keinen wirklichen Ende des Supportlebenszyklus gibt.  <br/> |Für SharePoint Server (oder SharePoint Foundation) und den zugrunde liegenden SQL-Servern wird ein Support-Lebenszyklus beendet.  <br/> |
   
Wenn Sie sich entschieden haben, eine neue Microsoft 365-Website zu erstellen und die Daten nach Bedarf manuell zu migrieren, können Sie sich Ihre [Microsoft 365-Optionen](https://www.microsoft.com/microsoft-365/)ansehen.
  

  
### <a name="upgrade-sharepoint-server-on-premises"></a>Upgrade SharePoint Server lokal

Ab der neuesten Version des lokalen SharePoint-Produkts (SharePoint Server 2019) müssen SharePoint Server Upgrades  *seriell*ausgeführt werden, was bedeutet, dass es keine Möglichkeit gibt, direkt von SharePoint Server 2010 auf SharePoint Server 2016 oder auf SharePoint 2019 zu aktualisieren. 
  
Pfad für serielles Upgrade: 

- SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Wenn Sie den vollständigen Pfad von SharePoint 2010 zu SharePoint Server 2016 ausführen möchten, dauert dies Zeit und wird geplant. Upgrades beinhalten Kosten in Bezug auf eine aktualisierte Hardware (Beachten Sie, dass auch SQL-Server aktualisiert werden müssen), Software und Verwaltung. Außerdem müssen Anpassungen möglicherweise aktualisiert oder sogar aufgegeben werden. Stellen Sie sicher, dass Sie vor dem Upgrade Ihrer SharePoint Server Farm Notizen zu allen wichtigen Anpassungen sammeln.
  
> [!NOTE]
> Es ist möglich, das Ende der Unterstützung SharePoint 2010 Farm beizubehalten, eine SharePoint Server 2016-Farm auf neuer Hardware zu installieren (damit die separaten Farmen nebeneinander ausgeführt werden) und dann eine manuelle Inhaltsmigration zu planen und auszuführen (beispielsweise zum herunterladen und erneuten Hochladen von Inhalten). Es gibt potenzielle Gefahren für diese manuellen Verschiebungen (beispielsweise Dokumente, die von 2010 mit einem aktuellen zuletzt geänderten Konto mit dem Alias des Kontos ausgeführt werden, das die manuelle Verschiebung ausführt), und einige arbeiten müssen im Voraus erfolgen (Neuerstellen von Websites, Unterwebsites, Berechtigungen und Listenstrukturen). Es ist eine gute Zeit, um zu prüfen, welche Daten Sie in den Speicher umlegen können oder nicht mehr benötigen. Dadurch können die Auswirkungen der Migration reduziert werden. Reinigen Sie in beiden Fällen Ihre Umgebung vor dem Upgrade. Stellen Sie sicher, dass Ihre vorhandene Farm funktionsfähig ist, bevor Sie ein Upgrade durchführen, und (sicher) bevor Sie außer Betrieb nehmen! 
  
Denken Sie daran, die **unterstützten und nicht unterstützten Upgrade-Pfade**zu überprüfen: 
  
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Wenn Sie **Anpassungen**haben, ist es wichtig, dass Sie ein Upgrade für jeden Schritt im Migrationspfad planen: 
  
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Lokaler Vorteil**|**Lokale Benachteiligung**|
|:-----|:-----|
|Vollzugriff auf alle Aspekte Ihrer SharePoint-Farm (und Ihrer SQL), von der Server Hardware bis.  <br/> |Alle Unterbrechungen und Fixes liegen in der Verantwortung Ihres Unternehmens (Sie können jedoch den kostenpflichtigen Microsoft-Support einbinden, wenn Ihr Produkt nicht am Ende der Unterstützung steht):  <br/> |
|Vollständiger Funktionsumfang von SharePoint Server lokal mit der Option zum Verbinden Ihrer lokalen Farm mit einem SharePoint Online-Abonnement über Hybrid.  <br/> |Upgrade, Patches, Sicherheitsfixes, Hardwareupgrades und die gesamte Wartung von SharePoint Server und seiner SQL-Farm werden lokal verwaltet.  <br/> |
|Vollzugriff für größere Anpassungsoptionen als bei SharePoint Online.  <br/> |[Microsoft Compliance-Angebote](https://go.microsoft.com/fwlink/?linkid=843165) müssen lokal manuell konfiguriert werden.  <br/> |
|Sicherheitstests und Server Leistungsoptimierung, die vor Ort (unter ihrer Kontrolle) ausgeführt werden.  <br/> |Microsoft 365 kann Features für SharePoint Online zur Verfügung stellen, die nicht mit SharePoint Server lokal zusammenarbeiten.  <br/> |
|Lösungsanbieter können die Migration von Daten zur nächsten Version von SharePoint Server (und darüber hinaus) unterstützen.  <br/> |Auf Ihren SharePoint Server Websites werden nicht automatisch [SSL/TLS-](https://go.microsoft.com/fwlink/?linkid=843167) Zertifikate verwendet, wie in SharePoint Online angezeigt wird.  <br/> |
|Vollzugriff auf Benennungskonventionen, Sicherung und Wiederherstellung und andere Wiederherstellungsoptionen in SharePoint Server lokal.  <br/> |SharePoint Server lokal reagiert auf Produktlebenszyklen.  <br/> |
   
### <a name="upgrade-resources"></a>Aktualisieren von Ressourcen

Vergleichen Sie zunächst die Hardware-und Softwareanforderungen. Wenn Sie die grundlegendenAnforderungen für das Upgrade auf der aktuellen Hardware nicht erfüllen, kann dies bedeuten, dass Sie zuerst die Hardware in der Farm oder in SQL-Servern aktualisieren müssen, oder dass Sie einen Prozentsatz Ihrer Websites auf die "Evergreen"-Hardware von SharePoint Online umstellen können. Nachdem Sie Ihre Bewertung vorgenommen haben, befolgen Sie die unterstützten Aktualisierungspfade und-Methoden.
  
- **Hardware-/Softwareanforderungen für**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Software Beschränkungen und-Grenzen für**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Die Übersicht über den Updateprozess für**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-sharepoint-server-on-premises"></a>Erstellen einer SharePoint-Hybridlösung zwischen SharePoint Online und SharePoint Server lokal

Eine weitere Option (eine, die sowohl für lokale als auch für Online-Umgebungen am besten geeignet ist) ist eine hybride, Sie können SharePoint Server 2013-oder 2016-oder 2019-Farmen mit SharePoint Online verbinden, um eine SharePoint-Hybridlösung zu erstellen: [erfahren Sie mehr über SharePoint-Hybridlösungen](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).
  
Wenn Sie sich für eine hybride SharePoint Server Farm als Migrationsziel entscheiden, müssen Sie unbedingt planen, welche Websites und Benutzer Sie Online umstellen sollten und welche lokal bleiben müssen. Bei dieser Entscheidung kann es hilfreich sein, die Inhalte Ihrer SharePoint Server Farm zu überprüfen und zu bewerten (feststellen, welche Daten hoch, Mittel oder niedrig für Ihr Unternehmen sind). Es kann sein, dass das einzige, was Sie für SharePoint Online freigeben müssen, (a) Benutzerkonten für die Anmeldung und (b) den SharePoint Server-Suchdienst Index sind – dies ist möglicherweise erst nach der Verwendung Ihrer Websites erkennbar. Wenn Ihr Unternehmen später entscheidet, alle Ihre Inhalte in SharePoint Online zu migrieren, können Sie alle verbleibenden Konten und Daten Online verschieben und Ihre lokale Farm außer Betrieb nehmen, und die Verwaltung/Verwaltung der SharePoint-Farm erfolgt von diesem Zeitpunkt an über Microsoft 365-Konsolen.
  
Stellen Sie sicher, dass Sie sich mit den vorhandenen Hybrid Typen vertraut machen und die Verbindung zwischen Ihrer lokalen SharePoint-Farm und Ihrem Microsoft 365-Abonnement konfigurieren.

| Option | Beschreibung |
|:-----|:-----|
|[Microsoft Compliance-Angebote](https://go.microsoft.com/fwlink/?linkid=843165).  <br/> |Die [Pannen](https://www.microsoft.com/fasttrack/microsoft-365) Unterstützung für die Migration ist limitiert.  <br/> Ein Großteil des Upgrades wird manuell durchführen oder über die SPO-Migrations-API, die in der [Roadmap für Migrations Inhalte für SharePoint Online und OneDrive](https://go.microsoft.com/fwlink/?linkid=843184)beschrieben wird.  <br/> |
|Weder Microsoft-Support Techniker noch Mitarbeiter im Rechenzentrum haben uneingeschränkten Administratorzugriff auf Ihr Abonnement.  <br/> |Es kann zusätzliche Kosten entstehen, wenn die Hardware Infrastruktur aktualisiert werden muss, um die neuere Version von SharePoint zu unterstützen, oder wenn eine sekundäre Farm für das Upgrade erforderlich ist.  <br/> |
|Partner können mit der einmaligen Aufgabe der Migration Ihrer Daten zu SharePoint Online behilflich sein.  <br/> ||
|Online Produkte werden automatisch über den Dienst aktualisiert, was bedeutet, dass Features zwar veraltet sein können, es jedoch kein echtes Ende der Unterstützung gibt.  <br/> ||
   
Wenn Sie sich entschieden haben, eine neue Microsoft 365-Website zu erstellen und die Daten nach Bedarf manuell zu migrieren, können Sie sich Ihre [Microsoft 365-Optionen](https://www.microsoft.com/microsoft-365/)ansehen.
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Upgrade SharePoint Server lokal

Es gibt historisch keine Möglichkeit, Versionen in SharePoint-Upgrades zu überspringen, zumindest nicht ab der Veröffentlichung von SharePoint Server 2016. Das bedeutet, dass Upgrades seriell gehen:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Um den gesamten Pfad von SharePoint 2007 auf SharePoint Server 2016 zu übernehmen, bedeutet dies eine erhebliche Investition von Zeit und erfordert eine Kosteneinsparung hinsichtlich der aktualisierten Hardware (Beachten Sie, dass auch SQL-Server aktualisiert werden müssen), Software und Verwaltung. Anpassungen müssen entsprechend der Wichtigkeit des Features aktualisiert oder aufgegeben werden.
  
> [!NOTE]
> Es ist möglich, Ihre End-of-Life-SharePoint 2007-Farm beizubehalten, eine SharePoint Server 2016-Farm auf neuer Hardware zu installieren (damit die separaten Farmen nebeneinander ausgeführt werden) und dann eine manuelle Inhaltsmigration zu planen und auszuführen (beispielsweise zum herunterladen und erneuten Hochladen von Inhalten). Beachten Sie einige der Fallstricke von manuellen Verschiebungen (beispielsweise Verschiebungen von Dokumenten, die das zuletzt geänderte Konto durch den Alias des Kontos ersetzen, das die manuelle Verschiebung ausführt), sowie die Arbeit, die im Vorfeld ausgeführt werden muss (beispielsweise das Neuerstellen von Websites, Unterwebsites, Berechtigungen und Listenstrukturen). Nun ist es an der Zeit zu prüfen, welche Daten Sie in den Speicher oder nicht mehr benötigen, eine Aktion, die die Auswirkungen der Migration reduzieren kann.
  
Reinigen Sie in beiden Fällen Ihre Umgebung vor dem Upgrade. Stellen Sie sicher, dass Ihre vorhandene Farm funktionsfähig ist, bevor Sie ein Upgrade durchführen, und (sicher) bevor Sie außer Betrieb nehmen! 
  
Denken Sie daran, die **unterstützten und nicht unterstützten Upgrade-Pfade**zu überprüfen: 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Wenn Sie **Anpassungen**haben, ist es wichtig, dass Sie ein Upgrade für jeden Schritt im Migrationspfad planen: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Lokale pro**|**Lokale con**|
|:-----|:-----|
|Vollzugriff auf alle Aspekte der SharePoint-Farm, von der Server Hardware bis hin.  <br/> |Alle Pausen und Fixes liegen in der Verantwortung Ihres Unternehmens (Sie können den kostenpflichtigen Microsoft-Support einbinden, wenn Ihr Produkt nicht am Ende der Unterstützung steht):  <br/> |
|Vollständiger Funktionsumfang von SharePoint Server lokal mit der Option zum Verbinden Ihrer lokalen Farm mit einem SharePoint Online-Abonnement über Hybrid.  <br/> |Upgrade, Patches, Sicherheitspatches und alle Wartung von SharePoint Server lokal verwaltet.  <br/> |
|Vollzugriff für eine größere Anpassung.  <br/> |[Microsoft Compliance-Angebote](https://go.microsoft.com/fwlink/?linkid=843165) müssen lokal manuell konfiguriert werden.  <br/> |
|Sicherheitstests und die Optimierung der Serverleistung, die vor Ort ausgeführt werden (unter ihrer Kontrolle).  <br/> |Microsoft 365 kann Features für SharePoint Online zur Verfügung stellen, die nicht mit SharePoint Server lokal zusammenarbeiten.  <br/> |
|Partner können die Migration von Daten zur nächsten Version von SharePoint Server (und darüber hinaus) unterstützen.  <br/> |Auf Ihren SharePoint Server Websites werden nicht automatisch [SSL/TLS-](https://go.microsoft.com/fwlink/?linkid=843167) Zertifikate verwendet, wie in SharePoint Online angezeigt wird.  <br/> |
|Vollzugriff auf Benennungskonventionen, Sicherung und Wiederherstellung und andere Wiederherstellungsoptionen in SharePoint Server lokal.  <br/> |SharePoint Server lokal reagiert auf Produktlebenszyklen.  <br/> |
   
### <a name="upgrade-resources"></a>Aktualisieren von Ressourcen

Beginnen Sie mit dem wissen, dass Sie die Hardware-und Softwareanforderungen erfüllen und dann unterstützte Upgrade-Methoden ausführen.
  
- **Hardware-/Softwareanforderungen für**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Software Beschränkungen und-Grenzen für**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Die Übersicht über den Updateprozess für**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Erstellen einer SharePoint-Hybridlösung zwischen SharePoint Online und lokal

Wenn die Antwort auf Ihre Migrationsanforderungen irgendwo zwischen der Selbstkontrolle durch das lokale System und den niedrigeren Betriebskosten liegt, die von SharePoint Online angeboten werden, können Sie SharePoint Server 2013-oder 2016-Farmen über Hybriden mit SharePoint Online verbinden. [Informationen zu SharePoint-Hybridlösungen](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Wenn Sie entscheiden, dass eine hybride SharePoint Server Farm Ihrem Unternehmen zugute kommt, machen Sie sich mit den vorhandenen Hybrid Typen vertraut und konfigurieren Sie die Verbindung zwischen Ihrer lokalen SharePoint-Farm und Ihrem Microsoft 365-Abonnement.
  
Eine gute Möglichkeit, um zu sehen, wie dies funktioniert, ist das Erstellen einer Microsoft 365-Entwicklungs-/Testumgebung, die Sie mit [Test Labor Handbüchern](m365-enterprise-test-lab-guides.md)einrichten können. Nachdem Sie eine Testversion oder ein erworbenes Microsoft 365-Abonnement erstellt haben, sind Sie auf dem Weg zum Erstellen der Websitesammlungen, Webs und Dokumentbibliotheken in SharePoint Online, auf die Sie Daten migrieren können (entweder manuell, mithilfe der Migrations-API oder – wenn Sie meine Website Inhalte zu OneDrive für Unternehmen migrieren möchten – über den Hybrid-Assistenten).
  
> [!NOTE]
> Denken Sie daran, dass Ihre SharePoint Server 2010 Farm zunächst lokal aktualisiert werden muss, um entweder SharePoint Server 2013 oder SharePoint Server 2016, um die Hybrid Option zu verwenden. SharePoint Foundation 2010 und SharePoint Foundation 2013 können keine Hybrid Verbindungen mit SharePoint Online erstellen. 

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Zusammenfassung der Optionen für Office 2010 Client und Server und Windows 7

Eine visuelle Zusammenfassung der Optionen für Upgrades, Migration und die Cloud für Office 2010-Clients und -Server sowie für Windows 7 finden Sie auf unter dem [Poster zum Supportende](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Bild des Posters zum Ende des Supports für Office 2010-Clients und -Server sowie Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Dieses einseitige Poster veranschaulicht auf einfache Weise, welche verschiedenen Pfade Sie wählen können, um zu verhindern, dass Office 2010-Clients und -Serverprodukte sowie Windows 7 das Ende des Supports erreichen. Bevorzugte Pfade und unterstützte Optionen in Microsoft 365 Enterprise sind hervorgehoben.

Sie können dieses Poster in den Formaten „Brief“, „Legal“ oder „Tabloid“ (27,94 x 43,18 cm) [herunterladen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf) und ausdrucken.
        
## <a name="related-topics"></a>Verwandte Themen

[Ressourcen zum Upgraden von Office 2007-oder 2010-Servern und-Clients](upgrade-from-office-2010-servers-and-products.md)
  
[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)
  
[Bewährte Methoden beim Upgrade von SharePoint 2010 auf SharePoint 2013](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)
  
[Behandeln von Problemen beim Datenbankupgrade in SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)
  
[Suchen nach Microsoft Solution Providern zur Unterstützung des Upgrades](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Aktualisierte Produktwartungsrichtlinie für SharePoint 2013](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)
  
[Aktualisierte Produktwartungsrichtlinie für SharePoint Server 2016](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
  

