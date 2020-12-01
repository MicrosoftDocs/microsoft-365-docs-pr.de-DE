---
title: Ende der Unterstützung für SharePoint Server 2007 – Roadmap
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 01/28/2019
audience: ITPro
ms.topic: conceptual
f1.keywords:
- CSH
ms.custom:
- vsemail
- MS_WSS_DirectoryManagement
- MS_WSS_ConfigEmail
- globalemailconfig
- configssc
- AppDefToBDC
- seo-marvel-apr2020
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- OFU120
- SPS150
- OSU140
- WSU120
- OSR120
- SPO160
- PJW120
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: ba124775-d5c0-4d68-b88d-8458ad4c3717
description: Die Unterstützung für SharePoint Server 2007 endete im Oktober 2017. In diesem Artikel erfahren Sie mehr über die Upgrade-, Migrations-und Supportoptionen.
ms.openlocfilehash: aa09669d1c7b90f70e6c136a85d06ef2a516e4b5
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519634"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Ende der Unterstützung für SharePoint Server 2007 – Roadmap

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Am **10. Oktober 2017** Microsoft Office SharePoint Server 2007 das Ende der Unterstützung erreicht. Wenn Sie nicht von SharePoint Server 2007 zu Microsoft 365 oder einer neueren Version von SharePoint Server lokal migriert haben, können Sie jetzt mit der Planung beginnen. In diesem Artikel finden Sie Ressourcen, die Sie bei der Migration von Daten zu SharePoint Online oder beim Upgrade Ihrer SharePoint Server lokal unterstützen.
  
## <a name="what-does-end-of-support-mean"></a>Was bedeutet das *Ende der Unterstützung* ?

SharePoint Server, wie die meisten Microsoft-Produkte, verfügt über einen Support-Lebenszyklus, in dem Microsoft neue Features, Fehlerbehebungen, Sicherheitsfixes usw. bereitstellt. Dieser Lebenszyklus dauert in der Regel 10 Jahre nach der ersten Version des Produkts. Das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Nach dem Ende der Unterstützung bietet Microsoft nicht mehr Folgendes:
  
- Technischer Support für Probleme, die auftreten können.
    
- Fehlerbehebungen für Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können.
    
- Sicherheitsfixes für Sicherheitsanfälligkeiten, die den Server möglicherweise anfällig für Sicherheitsverletzungen machen.
    
- Zeitzonenaktualisierungen.
    
Ihre SharePoint Server 2007-Farm ist nach dem 10. Oktober 2017 weiterhin funktionsfähig, aber es werden keine weiteren Updates, Patches oder Fixes für das Produkt veröffentlicht, einschließlich Sicherheitspatches/Fixes. Der Microsoft-Support hat die Unterstützung für neuere Versionen des Produkts vollständig verschoben. Da Ihre Installation nicht mehr unterstützt oder gepatcht wird, sollten Sie ein Upgrade des Produkts durchführen oder wichtige Daten migrieren.
  
> [!TIP]
> Wenn Sie noch nicht für ein Upgrade oder eine Migration geplant haben, finden Sie unter: [SharePoint 2007-Migrationsoptionen](sharepoint-2007-migration-options.md) einige Beispiele für den Anfang. Sie können auch nach [Microsoft-Partnern](https://go.microsoft.com/fwlink/?linkid=841249) suchen, die bei einem Upgrade oder einer Microsoft 365-Migration helfen können (oder beides).
  
Weitere Informationen zu Office 2007 Servern und zum Ende der Unterstützung finden Sie unter [Ressourcen, die Ihnen beim Upgrade von Office 2007-Servern und-Clients helfen](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>Was sind meine Optionen?

Der erste Stopp sollte die [Produktlebenszyklus-Website](https://go.microsoft.com/fwlink/?linkid=843148)sein. Wenn Sie ein lokales Microsoft-Produkt haben, das veraltet ist, überprüfen Sie das Datum der letzten Unterstützung, damit Sie ein Jahr planen oder ein Upgrade oder eine Migration planen können. Wenn Sie den nächsten Schritt auswählen, sollten Sie berücksichtigen, welche Produktfeatures gut genug, besser und am besten geeignet wären. Hier ein Beispiel: 
  
|**Gut**|**Besser**|**Optimal**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||SharePoint-Hybridlösung  <br/> |SharePoint Server 2016  <br/> |
| | |SharePoint-Hybridlösung  <br/> |
   
Wenn Sie die Option "gut genug" auswählen, müssen Sie bald mit der Planung eines weiteren Upgrades beginnen, nachdem die Migration von SharePoint Server 2007 abgeschlossen wurde. 

>[!NOTE] 
>Termine für das Ende des Supports können geändert werden. Überprüfen Sie die [Produktlebenszyklus-Website](https://support.microsoft.com/lifecycle).
  
## <a name="where-can-i-go-next"></a>Wie geht es weiter?

SharePoint Server können lokal auf Ihren eigenen Servern installiert werden. Sie können auch SharePoint Online verwenden, bei dem es sich um einen Online Dienst handelt, der Teil von Microsoft 365 ist. Folgende Optionen sind verfügbar:
  
- Migrieren Sie zu SharePoint Online.
    
- Upgrade SharePoint Server lokal.
    
- Führen Sie beide der oben genannten Aufgaben aus.
    
- Implementieren Sie eine [SharePoint-Hybrid](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx) Lösung.
    
Beachten Sie die versteckten Kosten im Zusammenhang mit der Verwaltung einer Serverfarm, dem warten oder Migrieren von Anpassungen und dem Upgraden der Hardware, die SharePoint Server benötigt. Eine lokale SharePoint Server Farm lohnt sich, wenn es erforderlich ist. Wenn Sie die Farm jedoch auf älteren SharePoint-Servern ohne starke Anpassung ausführen, können Sie von der Migration zu SharePoint Online profitieren.
  
> [!IMPORTANT]
> Es gibt eine weitere Option, wenn der Inhalt in SharePoint 2007 selten verwendet wird. Einige SharePoint-Administratoren beschließen, ein Microsoft 365-Abonnement zu erstellen, eine neue SharePoint Online Website einzurichten und dann sauber von SharePoint 2007 zu trennen, wobei nur die wichtigen Dokumente für die neuen SharePoint Online Websites zur Verfügung stehen. Daten können dann aus der SharePoint 2007-Website in Archive entwässert werden. Überprüfen Sie, wie Ihre Benutzer mit Daten aus Ihrer SharePoint 2007-Installation arbeiten. Es gibt möglicherweise kreative Möglichkeiten, Ihre Anforderungen zu verwalten.
  
|**SharePoint Online (SPO)**|**SharePoint Server lokal**|
|:-----|:-----|
|Hohe Kosten in der Zeit (Planung/Ausführung/Überprüfung)  <br/> |Hohe Kosten in der Zeit (Planung/Ausführung/Überprüfung)  <br/> |
|Geringere Kosten in Fonds (keine hardwarekäufe)  <br/> |Höhere Kosten in Fonds (Hardware + Entwickler/Administratoren)  <br/> |
|Einmalige Kosten bei der Migration  <br/> |Wiederholte einmalige Kosten pro künftiger Migration  <br/> |
|Niedrige Total Cost of Ownership/Maintenance  <br/> |Hohe Gesamtbetriebskosten/Wartung  <br/> |
   
Wenn Sie eine Migration zu Microsoft 365 durchführen, haben die einmaligen Schritte einen höheren Kostenaufwand als Voraussetzung, während Sie Daten organisieren und entscheiden, was Sie in die Cloud übernehmen und was Sie zurücklassen möchten. Aber zukünftige Upgrades werden automatisch durchführen, und Sie müssen keine Hardware-und Softwareupdates mehr verwalten. Außerdem wird die Dauer der Farm durch eine Vereinbarung zum Service Level ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)) von Microsoft unterstützt.
  
### <a name="migrate-to-sharepoint-online"></a>Migrieren zu SharePoint Online

Stellen Sie sicher, dass SharePoint Online über alle erforderlichen Funktionen verfügt. Weitere Informationen finden Sie unter [Microsoft 365 und Office 365-Dienstbeschreibungen](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library).
  
Sie können nicht direkt von SharePoint 2007 zu SharePoint Online migrieren. Die Umstellung auf SharePoint Online erfolgt manuell. Wenn Sie ein Upgrade auf SharePoint Server 2013 oder SharePoint Server 2016 durchführen, können Sie die SharePoint-Migrations-API verwenden (beispielsweise zum Migrieren von Informationen in OneDrive für Unternehmen).
  
|**Online-pro**|**Online con**|
|:-----|:-----|
|Microsoft liefert SPO-Hardware und die gesamte Hardwareverwaltung.  <br/> |Die verfügbaren Features können zwischen SharePoint Server lokal und SPO unterschiedlich sein.  <br/> |
|Sie sind der globale Administrator Ihres Abonnements und können Administratoren den SPO-Websites zuweisen.  <br/> |Einige Aktionen, die einem Farmadministrator in SharePoint Server lokal zur Verfügung stehen, sind nicht vorhanden oder sind nicht unbedingt in der SharePoint-Administratorrolle in Microsoft 365 enthalten.  <br/> |
|Microsoft wendet Patches, Fixes und Updates auf zugrunde liegende Hardware und Software an. <br/> |Da der Zugriff auf das zugrunde liegende Dateisystem im Dienst nicht möglich ist, ist die Anpassung begrenzt.  <br/> |
|Microsoft veröffentlicht [Vereinbarungen zum Service Level](https://go.microsoft.com/fwlink/?linkid=843153) und wird schnell zur Lösung von Vorfällen auf Dienstebene verschoben. <br/> |Sicherungs-und Wiederherstellungsoptionen werden vom Dienst in SharePoint Online automatisiert. Sicherungen werden überschrieben, wenn Sie nicht verwendet werden. <br/> |
|Sicherheitstests und die Optimierung der Serverleistung werden laufend im Dienst von Microsoft ausgeführt. <br/> |Änderungen an der Benutzeroberfläche und anderen SharePoint-Features werden vom Dienst installiert und müssen möglicherweise aktiviert oder deaktiviert werden. <br/> |
|Microsoft 365 erfüllt viele Branchenstandards: [Microsoft Compliance-Angebote](https://go.microsoft.com/fwlink/?linkid=843165).  <br/> |Die [Pannen](https://www.microsoft.com/fasttrack/microsoft-365) Unterstützung für die Migration ist limitiert.  <br/> Ein Großteil des Upgrades erfolgt manuell oder über die SPO-Migrations-API, die in der [Roadmap SharePoint Online and OneDrive Migration Content](https://go.microsoft.com/fwlink/?linkid=843184)beschrieben wird.  <br/> |
|Microsoft-Support Techniker und Mitarbeiter des Rechenzentrums haben keinen uneingeschränkten Administratorzugriff auf Ihr Abonnement. <br/> |Es kann zusätzliche Kosten entstehen, wenn die Hardware aktualisiert werden muss, um die neuere Version von SharePoint zu unterstützen, oder wenn eine sekundäre Farm für das Upgrade erforderlich ist.  <br/> |
|Partner können mit der einmaligen Aufgabe der Migration Ihrer Daten zu SharePoint Online behilflich sein.  <br/> ||
|Online Produkte werden automatisch aktualisiert. Obwohl Features veraltet sein können, gibt es kein echtes Ende der Unterstützung. <br/> ||
   
Wenn Sie sich entschieden haben, eine neue Microsoft 365-Website zu erstellen und die Daten nach Bedarf manuell zu migrieren, überprüfen Sie die [Microsoft 365-Optionen](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Upgrade SharePoint Server lokal

Es gibt keine Möglichkeit, Versionen in SharePoint-Upgrades zu überspringen. Upgrades gehen Seriell:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Um von SharePoint 2007 auf SharePoint Server 2016 zu wechseln, bedeutet eine erhebliche Investition von Zeit und kostet die Hardware (SQL Server müssen ebenfalls aktualisiert werden), Software und Verwaltung. Anpassungen müssen aktualisiert oder aufgegeben werden.
  
> [!NOTE]
> Es ist möglich, Ihre End-of-Life-SharePoint 2007-Farm beizubehalten, eine SharePoint Server 2016-Farm auf neuer Hardware zu installieren (damit die separaten Farmen nebeneinander ausgeführt werden) und dann eine manuelle Inhaltsmigration zu planen und auszuführen (beispielsweise zum herunterladen und erneuten Hochladen von Inhalten). Vorsicht vor einigen der Tücken von manuellen Verschiebungen, wie Verschiebungen von Dokumenten, die das Konto mit der letzten Änderung durch den Alias des Kontos ersetzen, das die manuelle Verschiebung ausführt. Berücksichtigen Sie auch die Arbeit, die im Voraus erfolgen muss, beispielsweise das Neuerstellen von Websites, Unterwebsites, Berechtigungen und Listenstrukturen. Überprüfen Sie vorab, welche Daten Sie in den Speicher oder das Löschen migrieren können, um die Auswirkungen der Migration zu reduzieren.
  
Es ist wichtig, die Umgebung vor dem Upgrade zu bereinigen. Stellen Sie sicher, dass Ihre vorhandene Farm funktionsfähig ist, bevor Sie ein Upgrade durchführen, und zwar vor der Außerbetriebnahme!
  
Denken Sie daran, die *unterstützten und nicht unterstützten Upgrade-Pfade* zu überprüfen: 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Wenn Sie Anpassungen haben, ist es wichtig, dass Sie einen Plan für jeden Schritt im Migrationspfad haben: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Lokale pro**|**Lokale con**|
|:-----|:-----|
|Vollzugriff auf alle Aspekte der SharePoint-Farm, von der Server Hardware bis hin.  <br/> |Alle Unterbrechungen und Fixes liegen in der Verantwortung Ihres Unternehmens (Sie können den kostenpflichtigen Microsoft-Support einbinden, wenn Ihr Produkt nicht hinter dem Ende des Supports steht).  <br/> |
|Vollständiger Funktionsumfang von SharePoint Server lokal mit der Option zum Verbinden Ihrer lokalen Farm mit einem SharePoint Online-Abonnement über Hybrid.  <br/> |Upgrade, Patches, Sicherheitspatches und alle Wartung von SharePoint Server lokal verwaltet.  <br/> |
|Vollzugriff für eine größere Anpassung.  <br/> |[Microsoft Compliance-Angebote](https://go.microsoft.com/fwlink/?linkid=843165) müssen lokal manuell konfiguriert werden.  <br/> |
|Sicherheitstests und die Server Leistungsoptimierung werden vor Ort (unter ihrer Kontrolle) ausgeführt.  <br/> |Microsoft 365 kann Features für SharePoint Online zur Verfügung stellen, die nicht mit SharePoint Server lokal zusammenarbeiten.  <br/> |
|Partner können die Migration von Daten zur nächsten Version von SharePoint Server (und darüber hinaus) unterstützen.  <br/> |Auf Ihren SharePoint Server Websites werden nicht automatisch [SSL/TLS-](https://go.microsoft.com/fwlink/?linkid=843167) Zertifikate verwendet, wie in SharePoint Online angezeigt wird.  <br/> |
|Vollzugriff auf Benennungskonventionen, Sicherung und Wiederherstellung sowie andere Wiederherstellungsoptionen in SharePoint Server lokal.  <br/> |SharePoint Server lokal reagiert auf Produktlebenszyklen.  <br/> |
   
### <a name="upgrade-resources"></a>Aktualisieren von Ressourcen

Stellen Sie sicher, dass Ihre Umgebung Hardware-und Softwareanforderungen erfüllt, und führen Sie dann unterstützte Upgrade-Methoden aus.
  
- **Hardware-/Softwareanforderungen für**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Software Beschränkungen und-Grenzen für**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Die Übersicht über den Updateprozess für**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Erstellen einer SharePoint-Hybridlösung zwischen SharePoint Online und lokal

Wenn die Antwort auf Ihre Migrationsanforderungen irgendwo zwischen der Selbstkontrolle durch die lokale Bereitstellung und den niedrigeren Kosten des Besitzes liegt, die von SharePoint Online angeboten werden, können Sie SharePoint Server 2013-oder 2016-Farmen über Hybriden mit SharePoint Online verbinden. [Erfahren Sie mehr über SharePoint-Hybridlösungen](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).
  
Wenn Sie entscheiden, dass eine hybride SharePoint Server Farm Ihrem Unternehmen zugute kommt, machen Sie sich mit den vorhandenen Hybrid Typen vertraut und konfigurieren Sie die Verbindung zwischen Ihrer lokalen SharePoint-Farm und Ihrem Microsoft 365-Abonnement.
  
| Option | Beschreibung |
|:-----|:-----|
[Microsoft Compliance-Angebote](https://go.microsoft.com/fwlink/?linkid=843165)  <br/> |Die [Pannen](https://www.microsoft.com/fasttrack/microsoft-365) Unterstützung für die Migration ist limitiert.  <br/> Ein Großteil des Upgrades wird manuell durchführen oder über die SPO-Migrations-API, die in der [Roadmap für Migrations Inhalte für SharePoint Online und OneDrive](https://go.microsoft.com/fwlink/?linkid=843184)beschrieben wird.  <br/> |
|Microsoft-Support Techniker und Mitarbeiter des Rechenzentrums haben keinen uneingeschränkten Administratorzugriff auf Ihr Abonnement.<br/> |Es kann zusätzliche Kosten entstehen, wenn die Hardware Infrastruktur aktualisiert werden muss, um die neuere Version von SharePoint zu unterstützen, oder wenn eine sekundäre Farm für das Upgrade erforderlich ist.  <br/> |
|Partner können mit der einmaligen Aufgabe der Migration Ihrer Daten zu SharePoint Online behilflich sein.  <br/> ||
|Online Produkte werden automatisch im gesamten Dienst aktualisiert. Obwohl Features veraltet sein können, gibt es kein echtes Ende der Unterstützung.<br/> ||
   
Wenn Sie sich entschieden haben, eine neue Microsoft 365-Website zu erstellen und die Daten nach Bedarf manuell zu migrieren, überprüfen Sie die [Microsoft 365-Optionen](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Upgrade SharePoint Server lokal

Es gibt keine Möglichkeit, Versionen in SharePoint-Upgrades zu überspringen. Upgrades gehen Seriell:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Um von SharePoint 2007 auf SharePoint Server 2016 zu wechseln, bedeutet eine erhebliche Investition von Zeit und erfordert Kosten für die Hardware (SQL Server müssen ebenfalls aktualisiert werden), Software und Verwaltung. Anpassungen müssen aktualisiert oder aufgegeben werden.
  
> [!NOTE]
> Es ist möglich, Ihre End-of-Life-SharePoint 2007-Farm beizubehalten, eine SharePoint Server 2016-Farm auf neuer Hardware zu installieren (damit die separaten Farmen nebeneinander ausgeführt werden) und dann eine manuelle Inhaltsmigration zu planen und auszuführen (beispielsweise zum herunterladen und erneuten Hochladen von Inhalten). Beachten Sie jedoch mögliche Fallstricke von manuellen Verschiebungen, wie etwa Verschiebungen von Dokumenten, die das Konto mit der letzten Änderung durch den Alias des Kontos ersetzen, das die manuelle Verschiebung ausführt, und die Arbeit, die im Voraus erfolgen muss, beispielsweise das Neuerstellen von Websites, Unterwebsites, Berechtigungen und Listenstrukturen. Berücksichtigen Sie, welche Daten Sie in Speicher oder Löschungen umsetzen können, um die Auswirkungen der Migration zu verringern.
  
Reinigen Sie die Umgebung vor dem Upgrade. Stellen Sie sicher, dass Ihre vorhandene Farm funktionsfähig ist, bevor Sie ein Upgrade durchführen, und zwar bevor Sie außer Betrieb nehmen! 
  
Denken Sie daran, die *unterstützten und nicht unterstützten Upgrade-Pfade* zu überprüfen: 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Wenn Sie *Anpassungen* haben, ist es wichtig, dass Sie ein Upgrade für jeden Schritt im Migrationspfad planen: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Lokale pro**|**Lokale con**|
|:-----|:-----|
|Vollzugriff auf alle Aspekte der SharePoint-Farm, von der Server Hardware bis hin.  <br/> |Alle Unterbrechungen und Fixes liegen in der Verantwortung Ihres Unternehmens. (Sie können den kostenpflichtigen Microsoft-Support einbinden, wenn Ihr Produkt nicht am Ende der Unterstützung vorbei ist.)  <br/> |
|Vollständiger Funktionsumfang von SharePoint Server lokal mit der Option zum Verbinden Ihrer lokalen Farm mit einem SharePoint Online-Abonnement über Hybrid.  <br/> |Upgrade, Patches, Sicherheitspatches und alle Wartung von SharePoint Server lokal verwaltet.  <br/> |
|Vollzugriff für eine größere Anpassung.  <br/> |[Microsoft Compliance-Angebote](https://go.microsoft.com/fwlink/?linkid=843165) müssen lokal manuell konfiguriert werden.  <br/> |
|Sicherheitstests und Server-Leistungsoptimierung werden vor Ort unter ihrer Kontrolle ausgeführt.  <br/> |Microsoft 365 kann Features für SharePoint Online zur Verfügung stellen, die nicht mit SharePoint Server lokalen Diensten zusammenarbeiten.  <br/> |
|Partner können bei der Migration von Daten zur nächsten Version von SharePoint Server (und darüber hinaus) helfen.  <br/> |Auf Ihren SharePoint Server Websites werden nicht automatisch [SSL/TLS-](https://go.microsoft.com/fwlink/?linkid=843167) Zertifikate verwendet, wie in SharePoint Online angezeigt wird.  <br/> |
|Vollzugriff auf Benennungskonventionen, Sicherung und Wiederherstellung sowie andere Wiederherstellungsoptionen in SharePoint Server lokal.  <br/> |SharePoint Server lokal reagiert auf Produktlebenszyklen.  <br/> |
   
### <a name="upgrade-resources"></a>Aktualisieren von Ressourcen

Stellen Sie sicher, dass Ihre Umgebung Hardware-und Softwareanforderungen erfüllt. Führen Sie dann die unterstützten Upgrade-Methoden aus.
  
- **Hardware-/Softwareanforderungen für:** 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Software Beschränkungen und-Grenzen für:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Die Übersicht über den Updateprozess für:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Erstellen einer SharePoint-Hybridlösung zwischen SharePoint Online und lokal

Wenn die Antwort auf Ihre Migrationsanforderungen irgendwo zwischen der Selbstkontrolle durch die lokale Bereitstellung und den niedrigeren Kosten des Besitzes liegt, die von SharePoint Online angeboten werden, können Sie SharePoint Server 2013-oder 2016-Farmen über Hybriden mit SharePoint Online verbinden. [Informationen zu SharePoint-Hybridlösungen](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Wenn Sie entscheiden, dass eine hybride SharePoint Server Farm Ihrem Unternehmen zugute kommt, machen Sie sich mit den vorhandenen Hybrid Typen vertraut und konfigurieren Sie die Verbindung zwischen Ihrer lokalen SharePoint-Farm und Ihrem Microsoft 365-Abonnement.
  
Eine gute Möglichkeit, um zu sehen, wie dies funktioniert, ist das Erstellen einer Microsoft 365-Entwicklungs-/Testumgebung, die Sie mit [testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)einrichten können. Nachdem Sie eine Testversion oder ein erworbenes Microsoft 365-Abonnement erhalten haben, können Sie die Websitesammlungen, Webs und Dokumentbibliotheken in SharePoint Online erstellen, in der Sie Daten migrieren können. Sie können mithilfe der Migrations-API manuell migrieren oder, wenn Sie meine Website Inhalte zu OneDrive für Unternehmen migrieren möchten, über den Hybrid-Assistenten.
  
> [!NOTE]
> Beachten Sie, dass die SharePoint 2007-Farm für die Verwendung der Hybrid Option lokal auf SharePoint Server 2013 oder SharePoint Server 2016 aktualisiert werden muss.
  
## <a name="related-topics"></a>Verwandte Themen

[Problembehandlung und Fortsetzen des Upgrades (Office SharePoint Server 2007)](https://go.microsoft.com/fwlink/?linkid=843192)
  
[Behandeln von Problemen beim Upgrade (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=843194)
  
[Behandeln von Problemen beim Datenbankupgrade in SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)
  
[Suchen nach Microsoft-Partnern zur Unterstützung des Upgrades](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Ressourcen für das Upgrade von Office 2007-Servern und-Clients](upgrade-from-office-2007-servers-and-products.md)
  
