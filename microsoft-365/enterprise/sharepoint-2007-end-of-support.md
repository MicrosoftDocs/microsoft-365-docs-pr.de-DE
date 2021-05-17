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
description: Die Unterstützung für SharePoint Server 2007 wurde im Oktober 2017 beendet. In diesem Artikel erfahren Sie mehr über Ihre Upgrade-, Migrations- und Supportoptionen.
ms.openlocfilehash: 224b0af90d6a314aa15a2c0dab7b60626e5abde8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924868"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Ende der Unterstützung für SharePoint Server 2007 – Roadmap

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Am **10. Oktober 2017** hat Microsoft Office SharePoint Server 2007 das Ende der Unterstützung erreicht. Wenn Sie nicht von SharePoint Server 2007 zu Microsoft 365 oder einer neueren Version von SharePoint Server lokal migriert haben, können Sie jetzt mit der Planung beginnen. Dieser Artikel enthält Ressourcen, mit deren Hilfe Sie Daten zu SharePoint Online migrieren oder Ihr SharePoint Server lokal aktualisieren können.
  
## <a name="what-does-end-of-support-mean"></a>Was bedeutet *das Ende der Unterstützung?*

SharePoint Server verfügt wie die meisten #A0 über einen Supportlebenszyklus, in dem Microsoft neue Features, Fehlerbehebungen, Sicherheitskorrekturen und so weiter bietet. Dieser Lebenszyklus dauert in der Regel 10 Jahre nach der ersten Produktversion. Das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Nach Dem Ende des Support bietet Microsoft nicht mehr:
  
- Technischer Support für Probleme, die auftreten können.
    
- Fehlerbehebungen für Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können.
    
- Sicherheitsbehebungen für Sicherheitsrisiken, die den Server anfällig für Sicherheitsverletzungen machen können.
    
- Zeitzonenupdates.
    
Ihre SharePoint Server 2007-Farm ist nach dem 10. Oktober 2017 weiterhin funktionsfähig, es werden jedoch keine weiteren Updates, Patches oder Korrekturen für das Produkt veröffentlicht, einschließlich Sicherheitspatches/-fixes. Der Microsoft Support hat seine Unterstützungsbemühungen vollständig auf aktuellere Versionen des Produkts verlagert. Da Ihre Installation nicht mehr unterstützt oder gepatcht wird, sollten Sie das Produkt aktualisieren oder wichtige Daten migrieren.
  
> [!TIP]
> Wenn Sie noch nicht ein Upgrade oder eine Migration geplant haben, finden Sie unter SharePoint [2007-Migrationsoptionen](sharepoint-2007-migration-options.md) einige Beispiele für den Anfang. Sie können auch nach [Microsoft-Partnern suchen,](https://go.microsoft.com/fwlink/?linkid=841249) die bei der Upgrade- oder Microsoft 365 Migration (oder beides) helfen können.
  
Weitere Informationen zu Office 2007-Servern und zum Ende des Support finden Sie unter Ressourcen, die Ihnen beim Upgrade von [Office 2007-Servern und -Clients helfen.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-are-my-options"></a>Was sind meine Optionen?

Ihr erster Stopp sollte die [Product Lifecycle-Website sein.](/lifecycle/products/?alpha=Microsoft+Office+SharePoint+Server+2007) Wenn Sie über ein lokales Microsoft-Produkt verfügen, das in die Jahre gekommen ist, überprüfen Sie das Ende des Supportdatums, damit Sie ein Jahr zeit haben, um ein Upgrade oder eine Migration zu planen. Wenn Sie den nächsten Schritt auswählen, überlegen Sie, welche Produktfeatures gut genug, besser und am besten wären. Hier ist ein Beispiel: 
  
|**Gut**|**Besser**|**Optimal**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||SharePoint-Hybridlösung  <br/> |SharePoint Server 2016  <br/> |
| | |SharePoint-Hybridlösung  <br/> |
   
Wenn Sie eine Option "gut genug" auswählen, müssen Sie bald mit der Planung eines weiteren Upgrades beginnen, nachdem die Migration von SharePoint Server 2007 abgeschlossen ist. 

>[!NOTE] 
>End-of-Support-Datumsangaben können geändert werden. Überprüfen Sie die [Product Lifecycle-Website](https://support.microsoft.com/lifecycle).
  
## <a name="where-can-i-go-next"></a>Wie geht es weiter?

SharePoint Server kann lokal auf Ihren eigenen Servern installiert werden. Sie können auch SharePoint Online verwenden, bei dem es sich um einen Onlinedienst handelt, der Teil der Microsoft 365. Folgende Optionen sind verfügbar:
  
- Migrieren Sie zu SharePoint Online.
    
- Aktualisieren SharePoint lokalen Servers.
    
- Gehen Sie wie oben beschrieben vor.
    
- Implementieren sie [SharePoint Hybridlösung.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
    
Beachten Sie verborgene Kosten im Zusammenhang mit der Wartung einer Serverfarm, der Wartung oder Migration von Anpassungen und dem Upgrade der Hardware, die SharePoint Server benötigt. Das Erstellen einer lokalen SharePoint Serverfarm ist bei Bedarf lohnend. Wenn Sie Ihre Farm jedoch auf älteren SharePoint server ohne große Anpassung ausführen, können Sie von der Migration zu SharePoint Profitieren.
  
> [!IMPORTANT]
> Es gibt eine weitere Option, wenn der Inhalt in SharePoint 2007 selten verwendet wird. Einige SharePoint-Administratoren möchten ein Microsoft 365-Abonnement erstellen, eine neue SharePoint Online-Website einrichten und dann von SharePoint 2007 sauber abschneiden, indem sie nur wichtige Dokumente auf die neuen SharePoint Online-Websites verwenden. Daten können dann von der SharePoint 2007-Website in Archive entleert werden. Überlegen Sie, wie Ihre Benutzer mit Daten aus Ihrer SharePoint 2007-Installation arbeiten. Es gibt möglicherweise kreative Möglichkeiten, Ihre Anforderungen zu verwalten.
  
|**SharePoint Online (SPO)**|**SharePoint Server lokal**|
|:-----|:-----|
|Hohe Zeitkosten (Plan/Ausführung/Überprüfung)  <br/> |Hohe Zeitkosten (Plan/Ausführung/Überprüfung)  <br/> |
|Niedrigere Kosten in Guthaben (keine Hardwarekäufe)  <br/> |Höhere Kosten in Geldmitteln (Hardware + Devs/Admins)  <br/> |
|Einmalkosten bei der Migration  <br/> |Einmalkosten, die pro zukünftiger Migration wiederholt werden  <br/> |
|Niedrige Gesamtbetriebskosten/Wartung  <br/> |Hohe Gesamtbetriebskosten/Wartung  <br/> |
   
Wenn Sie zu Microsoft 365 migrieren, hat die einmal verschieben höhere Kosten im Vor- und Nachher, während Sie Daten organisieren und entscheiden, was sie in die Cloud nehmen und was sie hinterlassen sollen. Zukünftige Upgrades werden jedoch automatisch sein, und Sie müssen keine Hardware- und Softwareupdates mehr verwalten. Außerdem wird die Betriebszeit Ihrer Farm durch einen Microsoft Service Level Agreement[(SLA) gesichert.](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)
  
### <a name="migrate-to-sharepoint-online"></a>Migrieren zu SharePoint Online

Stellen Sie sicher, SharePoint Online über alle benötigten Features verfügt. Siehe [Microsoft 365 und Office 365 Dienstbeschreibungen](/office365/servicedescriptions/office-365-service-descriptions-technet-library).
  
Sie können nicht direkt von SharePoint 2007 zu SharePoint Migrieren. Der Wechsel zu SharePoint Online erfolgt manuell. Wenn Sie ein Upgrade auf SharePoint Server 2013 oder SharePoint Server 2016 durchführen, können Sie die SharePoint-Migrations-API verwenden (z. B. zum Migrieren von Informationen OneDrive for Business).
  
|**Online-Pro**|**Online con**|
|:-----|:-----|
|Microsoft stellt SPO-Hardware und alle Hardwareverwaltungen zur Verf scht.  <br/> |Die verfügbaren Features können zwischen SharePoint server lokal und SPO variieren.  <br/> |
|Sie sind der globale Administrator Ihres Abonnements und können Administratoren spo-Websites zuweisen.  <br/> |Einige Aktionen, die einem Farmadministrator in SharePoint Server lokal zur Verfügung stehen, sind nicht vorhanden oder sind nicht unbedingt in der SharePoint Administratorrolle in Microsoft 365.  <br/> |
|Microsoft wendet Patches, Fixes und Updates auf zugrunde liegende Hardware und Software an. <br/> |Da der Dienst keinen Zugriff auf das zugrunde liegende Dateisystem hat, ist die Anpassung eingeschränkt.  <br/> |
|Microsoft veröffentlicht [Vereinbarungen zum Servicelevel und](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) bewegt sich schnell, Um Vorfälle auf Serviceebene zu beheben. <br/> |Sicherungs- und Wiederherstellungsoptionen und andere Wiederherstellungsoptionen werden vom Dienst in SharePoint Online automatisiert. Sicherungen werden überschrieben, wenn sie nicht verwendet werden. <br/> |
|Sicherheitstests und Serverleistungsoptimierung werden fortlaufend im Dienst von Microsoft durchgeführt. <br/> |Änderungen an der Benutzeroberfläche und anderen SharePoint werden vom Dienst installiert und müssen möglicherweise ein- oder ausgeschaltet werden. <br/> |
|Microsoft 365 erfüllt viele Branchenstandards: [Microsoft Compliance-Angebote](/compliance/regulatory/offering-home).  <br/> |[Die FastTrack-Unterstützung](https://www.microsoft.com/fasttrack/microsoft-365) für die Migration ist begrenzt.  <br/> Ein Teil des Upgrades erfolgt manuell oder über die in SharePoint Online und OneDrive [Migration Content Roadmap beschriebene SPO-Migrations-API.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)  <br/> |
|Microsoft-Supporttechniker und Mitarbeiter des Rechenzentrums haben keinen uneingeschränkten Administratorzugriff auf Ihr Abonnement. <br/> |Es können zusätzliche Kosten entstehen, wenn die Hardware aktualisiert werden muss, um die neuere Version von SharePoint zu unterstützen, oder wenn eine sekundäre Farm für das Upgrade erforderlich ist.  <br/> |
|Partner können ihnen bei der einmalen Migration Ihrer Daten zu SharePoint helfen.  <br/> ||
|Onlineprodukte werden automatisch aktualisiert. Obwohl Features möglicherweise veraltet sind, gibt es kein echtes Ende der Unterstützung. <br/> ||
   
Wenn Sie sich entschieden haben, eine neue Microsoft 365 zu erstellen und Daten manuell zu dieser website migrieren, wenn [dies erforderlich](https://www.microsoft.com/microsoft-365/)ist, überprüfen Sie ihre Microsoft 365 Optionen .
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Upgrade SharePoint lokalen Servers

Es gibt keine Möglichkeit, Versionen in SharePoint überspringen. Upgrades werden seriell verwendet:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Um von SharePoint 2007 zu SharePoint Server 2016 zu wechseln, bedeutet dies eine erhebliche Zeitinvestition und Kosten für Hardware (SQL Server müssen ebenfalls aktualisiert werden), Software und Verwaltung. Anpassungen müssen aktualisiert oder abgebrochen werden.
  
> [!NOTE]
> Es ist möglich, Ihre SharePoint 2007-Farm zu verwalten, eine SharePoint Server 2016-Farm auf neuer Hardware zu installieren (sodass die separaten Farmen nebeneinander ausgeführt werden), und dann eine manuelle Migration von Inhalten planen und ausführen (z. B. zum Herunterladen und erneuten Hochladen von Inhalten). Sie sollten sich jedoch vor einigen Tücken manueller Bewegungen hüten, z. B. beim Verschieben von Dokumenten, die das zuletzt geänderte Konto durch den Alias des Kontos ersetzen, das die manuelle Bewegung vor sich hat. Berücksichtigen Sie außerdem die Arbeit, die im Voraus erledigt werden muss, z. B. das Erstellen von Websites, Unterwebsites, Berechtigungen und Listenstrukturen. Überlegen Sie im Voraus, welche Daten Sie in den Speicher verschieben oder löschen können, um die Auswirkungen der Migration zu reduzieren.
  
Es ist wichtig, ihre Umgebung vor dem Upgrade zu bereinigen. Gehen Sie sicher, dass Ihre vorhandene Farm funktionsfähig ist, bevor Sie ein Upgrade durchführen, und schon gar nicht vor der Außerbetriebnahme!
  
Denken Sie daran, die *unterstützten und nicht unterstützten Upgradepfade zu überprüfen:* 
  
- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
Wenn Sie Anpassungen haben, ist es wichtig, einen Plan für jeden Schritt im Migrationspfad zu haben: 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**Lokale Pro**|**Lokales Con**|
|:-----|:-----|
|Vollständige Kontrolle über alle Aspekte der SharePoint Farm, von der Serverhardware bis zur Serverhardware.  <br/> |Alle Unterbrechungen und Korrekturen liegen in der Verantwortung Ihres Unternehmens (Sie können kostenpflichtigen Microsoft-Support ins Gespräch kommen, wenn Ihr Produkt nicht über das Ende des Supportes liegt).  <br/> |
|Vollständiger Funktionssatz von SharePoint Server lokal mit der Option, Ihre lokale Farm mit einem SharePoint Onlineabonnement über Hybrid zu verbinden.  <br/> |Upgrade, Patches, Sicherheitskorrekturen und die SharePoint lokalen Server.  <br/> |
|Vollzugriff für eine größere Anpassung.  <br/> |[Microsoft-Complianceangebote](/compliance/regulatory/offering-home) müssen manuell lokal konfiguriert werden.  <br/> |
|Sicherheitstests und Serverleistungsoptimierung werden vor Ort (unter Ihrer Kontrolle) durchgeführt.  <br/> |Microsoft 365 können Features für SharePoint Online verfügbar machen, die nicht mit dem lokalen SharePoint Server zusammenarbeiten.  <br/> |
|Partner können beim Migrieren von Daten zur nächsten Version von SharePoint Server (und darüber hinaus) helfen.  <br/> |Ihre SharePoint Serverwebsites verwenden nicht automatisch [SSL/TLS-Zertifikate,](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) wie in SharePoint Online zu sehen ist.  <br/> |
|Vollständige Kontrolle über Benennungskonventionen, Sicherung und Wiederherstellung sowie andere Wiederherstellungsoptionen in SharePoint Server lokal.  <br/> |SharePoint Der lokale Server ist für Produktlebenszyklen sensibel.  <br/> |
   
### <a name="upgrade-resources"></a>Upgraderessourcen

Stellen Sie sicher, dass Ihre Umgebung die Hardware- und Softwareanforderungen erfüllt, und befolgen Sie dann unterstützte Upgrademethoden.
  
- **Hardware-/Softwareanforderungen für:** 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **Softwarebeschränkungen und -grenzen für:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **Übersicht über den Upgradeprozess für:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Erstellen einer SharePoint Hybridlösung zwischen SharePoint Online und lokal

Wenn die Antwort auf Ihre Migrationsanforderungen zwischen der lokalen Selbstkontrolle und den niedrigeren Betriebskosten von SharePoint Online liegt, können Sie SharePoint Server 2013- oder 2016-Farmen über Hybride mit SharePoint Online verbinden. [Erfahren Sie mehr SharePoint Hybridlösungen](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).
  
Wenn Sie entscheiden, dass eine hybride SharePoint Serverfarm Ihrem Unternehmen vorteilet, machen Sie sich mit den vorhandenen Hybridtypen vertraut und erfahren Sie, wie Sie die Verbindung zwischen Ihrer lokalen SharePoint-Farm und Ihrem Microsoft 365-Abonnement konfigurieren.
  
| Option | Beschreibung |
|:-----|:-----|
[Microsoft Compliance-Angebote](/compliance/regulatory/offering-home)  <br/> |[Die FastTrack-Unterstützung](https://www.microsoft.com/fasttrack/microsoft-365) für die Migration ist begrenzt.  <br/> Ein Teil des Upgrades erfolgt manuell oder über die in SharePoint Online and OneDrive Migration Content Roadmap beschriebene [SPO-Migrations-API.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)  <br/> |
|Microsoft SupportTechniker und Mitarbeiter des Rechenzentrums haben keinen uneingeschränkten Administratorzugriff auf Ihr Abonnement.<br/> |Es können zusätzliche Kosten entstehen, wenn die Hardwareinfrastruktur aktualisiert werden muss, um die neuere Version von SharePoint zu unterstützen, oder wenn eine sekundäre Farm für das Upgrade erforderlich ist.  <br/> |
|Partner können ihnen bei der einmalen Migration Ihrer Daten zu SharePoint helfen.  <br/> ||
|Onlineprodukte werden automatisch im gesamten Dienst aktualisiert. Obwohl Features möglicherweise veraltet sind, gibt es kein echtes Ende der Unterstützung.<br/> ||
   
Wenn Sie sich entschieden haben, eine neue Microsoft 365 zu erstellen und Daten manuell zu dieser website migrieren, wenn [dies erforderlich](https://www.microsoft.com/microsoft-365/)ist, überprüfen Sie ihre Microsoft 365 Optionen .
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Upgrade SharePoint lokalen Servers

Es gibt keine Möglichkeit, Versionen in SharePoint überspringen. Upgrades werden seriell verwendet:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Um von SharePoint 2007 auf SharePoint Server 2016 zu wechseln, bedeutet dies eine erhebliche Zeitinvestition und Kosten für Hardware (SQL Server müssen ebenfalls aktualisiert werden), Software und Verwaltung. Anpassungen müssen aktualisiert oder abgebrochen werden.
  
> [!NOTE]
> Es ist möglich, Ihre SharePoint 2007-Farm zu verwalten, eine SharePoint Server 2016-Farm auf neuer Hardware zu installieren (sodass die separaten Farmen nebeneinander ausgeführt werden), und dann eine manuelle Migration von Inhalten planen und ausführen (z. B. zum Herunterladen und erneuten Hochladen von Inhalten). Sie sollten sich jedoch vor möglichen Fallstricken manueller Bewegungen hüten, z. B. beim Verschieben von Dokumenten, die das zuletzt geänderte Konto durch den Alias des Kontos ersetzen, das die manuelle Bewegung vor sich hat, und vor der Arbeit, die im Voraus erledigt werden muss, z. B. das Erstellen von Websites, Unterwebsites, Berechtigungen und Listenstrukturen. Überlegen Sie, welche Daten Sie in Speicher verschieben oder löschen können, um die Auswirkungen der Migration zu reduzieren.
  
Bereinigen Sie Ihre Umgebung vor dem Upgrade. Gehen Sie sicher, dass Ihre vorhandene Farm funktionsfähig ist, bevor Sie ein Upgrade durchführen und vor der Außerbetriebnahme! 
  
Denken Sie daran, die *unterstützten und nicht unterstützten Upgradepfade zu überprüfen:* 
  
- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
Wenn Sie Anpassungen *haben,* ist es wichtig, dass Sie ein Upgrade für jeden Schritt im Migrationspfad planen: 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**Lokale Pro**|**Lokales Con**|
|:-----|:-----|
|Vollständige Kontrolle über alle Aspekte der SharePoint Farm, von der Serverhardware bis zur Serverhardware.  <br/> |Alle Unterbrechungen und Korrekturen liegen in der Verantwortung Ihres Unternehmens. (Sie können den kostenpflichtigen Microsoft-Support ins Unternehmen einmischen, wenn Ihr Produkt nicht mehr am Ende des Support ist.)  <br/> |
|Vollständiger Funktionssatz von SharePoint Server lokal mit der Option, Ihre lokale Farm mit einem SharePoint Onlineabonnement über Hybrid zu verbinden.  <br/> |Upgrade, Patches, Sicherheitskorrekturen und die SharePoint lokalen Server.  <br/> |
|Vollzugriff für eine größere Anpassung.  <br/> |[Microsoft-Complianceangebote](/compliance/regulatory/offering-home) müssen manuell lokal konfiguriert werden.  <br/> |
|Sicherheitstests und Serverleistungsoptimierungen werden in Ihrer Lokalen unter Ihrer Kontrolle durchgeführt.  <br/> |Microsoft 365 können Features für SharePoint Online verfügbar machen, die nicht mit dem lokalen SharePoint Server zusammenarbeiten  <br/> |
|Partner können bei der Migration von Daten zur nächsten Version von SharePoint Server (und darüber hinaus) helfen.  <br/> |Ihre SharePoint Serverwebsites verwenden nicht automatisch [SSL/TLS-Zertifikate,](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) wie in SharePoint Online zu sehen ist.  <br/> |
|Vollständige Kontrolle über Benennungskonventionen, Sicherung und Wiederherstellung sowie andere Wiederherstellungsoptionen in SharePoint Server lokal.  <br/> |SharePoint Der lokale Server ist für Produktlebenszyklen sensibel.  <br/> |
   
### <a name="upgrade-resources"></a>Upgraderessourcen

Stellen Sie sicher, dass Ihre Umgebung die Hardware- und Softwareanforderungen erfüllt. Befolgen Sie dann die unterstützten Upgrademethoden.
  
- **Hardware-/Softwareanforderungen für:** 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **Softwarebeschränkungen und -grenzen für:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **Übersicht über den Upgradeprozess für:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Erstellen einer SharePoint Hybridlösung zwischen SharePoint Online und lokal

Wenn die Antwort auf Ihre Migrationsanforderungen zwischen der lokalen Selbstkontrolle und den niedrigeren Betriebskosten von SharePoint Online liegt, können Sie SharePoint Server 2013- oder 2016-Farmen über Hybride mit SharePoint Online verbinden. [Erfahren Sie mehr SharePoint Hybridlösungen](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Wenn Sie entscheiden, dass eine hybride SharePoint Serverfarm Ihrem Unternehmen vorteilet, machen Sie sich mit den vorhandenen Hybridtypen vertraut und erfahren Sie, wie Sie die Verbindung zwischen Ihrer lokalen SharePoint-Farm und Ihrem Microsoft 365-Abonnement konfigurieren.
  
Eine gute Möglichkeit, um zu sehen, wie dies funktioniert, ist das Erstellen einer Microsoft 365 Entwicklungs-/Testumgebung, die Sie mit Test Lab [Guides einrichten können.](m365-enterprise-test-lab-guides.md) Nachdem Sie ein Test- oder Microsoft 365 erworben haben, können Sie die Websitesammlungen, Webs und Dokumentbibliotheken in SharePoint Online erstellen, zu denen Sie Daten migrieren können. Sie können manuell, mithilfe der Migrations-API oder, wenn Sie Meine Websiteinhalte zu OneDrive for Business, über den Hybrid-Assistenten migrieren.
  
> [!NOTE]
> Denken Sie daran, dass Ihre SharePoint 2007-Farm lokal auf SharePoint Server 2013 oder SharePoint Server 2016 aktualisiert werden muss, um die Hybridoption verwenden zu können.
  
## <a name="related-topics"></a>Verwandte Themen

[Problembehandlung und Fortsetzung des Upgrades (Office SharePoint Server 2007)](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262967(v=office.12))
  
[Problembehandlung bei Upgradeproblemen (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/cc262967(v=office.14))
  
[Behandeln von Problemen beim Datenbankupgrade in SharePoint 2013](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)
  
[Suchen nach Microsoft-Partnern zur Unterstützung beim Upgrade](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Ressourcen, die Ihnen beim Upgrade von Office 2007-Servern und -Clients helfen](upgrade-from-office-2007-servers-and-products.md)
