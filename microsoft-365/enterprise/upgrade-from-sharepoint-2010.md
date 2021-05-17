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
description: Hier finden Sie Informationen und Ressourcen zum Upgrade von SharePoint 2010 und Sharepoint Server 2010. Unterstützung für beide endet am 13. April 2021.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4fa82fb0e382a244cdc126609ac62d17280b9702
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925332"
---
# <a name="upgrading-from-sharepoint-2010"></a>Upgrade von SharePoint 2010

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft SharePoint 2010 und SharePoint Server 2010 endet am **13. April 2021.** Dieser Artikel enthält Ressourcen, mit deren Hilfe Sie Ihre vorhandenen SharePoint Server 2010-Daten zu SharePoint Online in Microsoft 365 migrieren oder Ihre lokale SharePoint Server 2010-Umgebung aktualisieren können.

## <a name="what-is-end-of-support"></a>Was ist *das Ende der Unterstützung?*

Die meisten #A0 haben einen Supportlebenszyklus, in dem sie neue Features, Fehlerbehebungen, Sicherheitskorrekturen und so weiter erhalten. Nach dem End-of-Support-Datum funktioniert das Produkt nicht mehr, aber Microsoft bietet nicht mehr:

- Technischer Support für Probleme, die auftreten können.

- Fehlerbehebungen für Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können.

- Sicherheitsbehebungen für Sicherheitsrisiken, die den Server anfällig für Sicherheitsverletzungen machen können.

- Zeitzonenupdates.

Das bedeutet, dass es keine weiteren Updates, Patches oder Fixes für das Produkt gibt (einschließlich Sicherheitspatches/Fixes). Der Microsoft Support hat seine Unterstützungsbemühungen vollständig auf neuere Versionen verlagert.

Wenn sich das Ende der Unterstützung von SharePoint Server 2010 nähert, löschen Sie daten, die Sie nicht mehr benötigen, bevor Sie das Produkt aktualisieren und Ihre wichtigen Daten migrieren.

> [!NOTE]
> Ein Softwarelebenszyklus dauert in der Regel zehn Jahre ab der ersten Version. [Microsoft-Lösungsanbieter](https://go.microsoft.com/fwlink/?linkid=841249) können Ihnen dabei helfen, auf die nächste Version der Software zu aktualisieren oder zu Microsoft 365 Migration (oder beides) zu migrieren. Stellen Sie sicher, dass Sie auch die End-of-Support-Datumsangaben für wichtige zugrunde liegende Technologien kennen, insbesondere für die Version von Microsoft SQL Server, die Sie mit SharePoint. Weitere Informationen finden Sie unter [Fixed Lifecycle Policy](https://support.microsoft.com/help/14085).

## <a name="plan-ahead"></a>Planen sie voraus

Überprüfen Sie die Datumsangaben, die auf der [Product Lifecycle-Website enden.](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010) Planen Sie Ihre Upgrades oder Migrationen mit diesen Datumsangaben. Denken Sie daran, dass Ihr Produkt *am angegebenen* Datum nicht mehr funktioniert. Da Ihre Installation jedoch nach diesem Datum nicht mehr gepatcht wird, sollten Sie einen reibungslosen Übergang zur nächsten Version des Produkts planen.

Diese Matrix hilft beim Plotten eines Kurses zwischen Migrationsoptionen:

|Ende des Supportprodukts|Gut |Optimal|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (lokal)|SharePoint Online|
||SharePoint Server 2013-Hybrid mit SharePoint Online|SharePoint Server 2016 (lokal)|
|||SharePoint Cloudhybridsuche|

Wenn Sie eine Option am niedrigen Ende der Skalierung (gut) auswählen, müssen Sie bald nach der Migration von SharePoint Server 2010 mit der Planung eines weiteren Upgrades beginnen.

Hier sind die drei Pfade, die Sie gehen können, um das Ende der Unterstützung für SharePoint Server 2010 zu vermeiden.

![SharePoint Server 2010-Upgradepfade](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> Das Ende der Unterstützung für SharePoint Server 2010 und SharePoint Foundation 2010 ist derzeit für den 13. April 2021 geplant. Achten Sie jedoch darauf, die [Product Lifecycle-Website auf](https://support.microsoft.com/lifecycle) die aktuellen Datumsangaben zu überprüfen.

## <a name="whats-next"></a>Nächste Schritte

SharePoint Server 2013 und SharePoint Foundation 2013 können lokal auf Ihren eigenen Servern installiert werden. Sie können auch SharePoint Online verwenden, bei dem es sich um einen Onlinedienst handelt, der Teil der Microsoft 365. Sie haben folgende Auswahlmöglichkeiten:

- Migrieren Sie zu SharePoint Online.

- Upgrade SharePoint Server oder SharePoint Foundation lokal.

- Gehen Sie wie oben beschrieben vor.

- Implementieren sie [SharePoint Hybridlösung.](/sharepoint/hybrid/hybrid)

Berücksichtigen Sie die verborgenen Kosten für die Verwaltung einer Serverfarm, einschließlich der Wartung oder Migration von Anpassungen und des Upgrades der Hardware. Wenn Sie diese Faktoren berücksichtigt haben, ist es einfacher, ein lokales Upgrade zu durchführen. Wenn Sie Ihre Farm auf Legacyservern SharePoint ohne große Anpassungen ausführen, könnten Sie von einer geplanten Migration zu SharePoint Online profitieren. Für eine lokale SharePoint Serverumgebung können Sie auch das Verschieben einiger Daten in SharePoint Online in Betracht ziehen, um den Hardwareverwaltungsaufwand zu reduzieren.

> [!NOTE]
> SharePoint Administratoren können ein Microsoft 365-Abonnement erstellen, neue SharePoint Onlinewebsites einrichten und dann von SharePoint Server 2010 sauber abschneiden und nur wichtige Dokumente auf die neuen Websites übertragen. Anschließend können alle verbleibenden Daten aus dem Server 2010 SharePoint server 2010-Standort in lokale Archive entleert werden.

|SharePoint Online|SharePoint Server lokal|
|---|---|
|Hohe Zeitkosten (Plan/Ausführung/Überprüfung)|Hohe Zeitkosten (Plan/Ausführung/Überprüfung)|
|Niedrigere Kosten in Guthaben (keine Hardwarekäufe)|Höhere Kosten in Guthaben (Hardwarekäufe)|
|Einmalkosten bei der Migration|Einmalkosten, die pro zukünftiger Migration wiederholt werden|
|Niedrige Gesamtbetriebskosten/Wartung|Hohe Gesamtbetriebskosten/Wartung|

Ein einmaler Wechsel zu Microsoft 365 kosten höhere Kosten, während Sie Daten organisieren und entscheiden, was in der Cloud verwendet werden soll und was sie hinterlassen sollen. Nachdem Ihre Daten migriert wurden, werden zukünftige Upgrades jedoch automatisch, da Sie hardware- und softwareupdates nicht mehr verwalten müssen. Und die Betriebszeit Ihrer Farm wird durch einen [Microsoft Service Level Agreement (SLA) gesichert.](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)

### <a name="migrate-to-sharepoint-online"></a>Migrieren zu SharePoint Online

Stellen Sie sicher, SharePoint Online alle benötigten Features bietet. Siehe [SharePoint Dienstbeschreibung](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).

Sie können nicht direkt von SharePoint Server 2010 (oder SharePoint Foundation 2010) zu SharePoint migrieren. Der Große Teil der Migrationsarbeit ist manuell. In dieser Phase haben Sie jedoch die Möglichkeit, Daten und Websites zu löschen, die vor dem Verschieben nicht mehr benötigt werden. Sie können andere Daten im Speicher archivieren. 

Denken Sie daran SharePoint Server 2010 und SharePoint Foundation 2010 am Ende des Support nicht mehr funktionieren. Administratoren können also einen Zeitraum haben, SharePoint weiterhin ausgeführt wird, wenn ihre Kunden vergessen, einige ihrer Daten zu verschieben.

Wenn Sie ein Upgrade auf SharePoint Server 2013 oder SharePoint Server 2016 durchführen und daten in SharePoint Online speichern möchten, können Sie die [SharePoint-Migrations-API](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) verwenden, um Informationen zu OneDrive for Business.

|SharePoint Onlinevorteil|SharePoint Onlinenachteil|
|---|---|
|Microsoft stellt SPO-Hardware und alle Hardwareverwaltungen zur Verf scht.|Die verfügbaren Features können zwischen SharePoint server lokal und SPO variieren.|
|Sie sind der globale Administrator Ihres Abonnements und können Administratoren spo-Websites zuweisen.|Einige Aktionen, die einem Farmadministrator in SharePoint Server lokal verfügbar sind, sind nicht in der SharePoint-Administratorrolle in Microsoft 365. Aber SharePoint Verwaltung, Verwaltung von Websitesammlungen und Websitebesitz sind in Ihrer Organisation lokal.|
|Microsoft wendet Patches, Fixes und Updates auf zugrunde liegende Hardware und Software an, einschließlich SQL Servern, auf denen SharePoint Online ausgeführt wird.|Da der Dienst keinen Zugriff auf das zugrunde liegende Dateisystem hat, ist die Anpassung eingeschränkt.|
|Microsoft veröffentlicht [Vereinbarungen zum Servicelevel und](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) bewegt sich schnell, Um Vorfälle auf Serviceebene zu beheben.|Sicherungs- und Wiederherstellungsoptionen und andere Wiederherstellungsoptionen werden vom Dienst in SharePoint Online automatisiert. Sicherungen werden überschrieben, wenn sie nicht verwendet werden.|
|Sicherheitstests und Die Leistungsoptimierung des Servers werden von Microsoft kontinuierlich im Dienst durchgeführt.|Änderungen an der Benutzeroberfläche und anderen SharePoint werden vom Dienst installiert und müssen möglicherweise ein- oder ausgeschaltet werden.|
|Microsoft 365 erfüllt viele Branchenstandards: [Microsoft Compliance-Angebote](/compliance/regulatory/offering-home).|[Die FastTrack-Unterstützung](https://go.microsoft.com/fwlink/?linkid=518597) für die Migration ist begrenzt.  <br/> Ein Teil des Upgrades erfolgt manuell oder über die in SharePoint Online und OneDrive [Migration Content Roadmap beschriebene SPO-Migrations-API.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)|
|Microsoft SupportTechniker und Mitarbeiter des Rechenzentrums haben keinen uneingeschränkten Administratorzugriff auf Ihr Abonnement.|Es können zusätzliche Kosten entstehen, wenn die Hardwareinfrastruktur aktualisiert werden muss, um die neuere Version von SharePoint zu unterstützen, oder wenn eine sekundäre Farm für das Upgrade erforderlich ist.|
|Lösungsanbieter können bei der einmalen Migration Ihrer Daten zu SharePoint helfen.|Nicht alle Änderungen an SharePoint Online befinden sich in Ihrem Steuerelement. Nach der Migration können sich Entwurfsunterschiede in Menüs, Bibliotheken und anderen Features vorübergehend auf die Benutzerfreundlichkeit auswirken.|
|Onlineprodukte werden automatisch im gesamten Dienst aktualisiert. Features sind möglicherweise veraltet, aber es gibt kein echtes Ende des Supportlebenszyklus.|Es gibt einen End-of-Support-Lebenszyklus für SharePoint Server oder SharePoint Foundation sowie zugrunde liegende SQL Server.|

Wenn Sie sich entschieden haben, eine neue Microsoft 365 zu erstellen und Daten manuell zu dieser website migrieren, wenn [dies erforderlich](https://www.microsoft.com/microsoft-365/)ist, überprüfen Sie ihre Microsoft 365 Optionen .

### <a name="upgrade-sharepoint-server-on-premises"></a>Upgrade SharePoint lokalen Servers

Ab SharePoint Server 2019 müssen Upgrades *seriell verwendet werden.* Es gibt keine Möglichkeit, ein Upgrade von SharePoint Server 2010 auf SharePoint Server 2016 oder direkt auf SharePoint 2019 zu durchführen. Serieller Upgradepfad:

- SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Es dauert und plant, den gesamten Pfad von SharePoint 2010 bis SharePoint Server 2016 zu folgen. Upgrades verursachen Kosten für Hardware (SQL Server müssen ebenfalls aktualisiert werden), Software und Verwaltung. Außerdem müssen Anpassungen möglicherweise aktualisiert oder sogar abgebrochen werden. Stellen Sie sicher, dass Sie wichtige Anpassungen dokumentieren, bevor Sie die serverfarm SharePoint aktualisieren.

> [!NOTE]
> Es ist möglich, Die End-of-Support SharePoint 2010-Farm zu verwalten, eine SharePoint Server 2016-Farm auf neuer Hardware zu installieren (sodass die separaten Farmen nebeneinander ausgeführt werden), und dann eine manuelle Migration von Inhalten planen und ausführen (z. B. zum Herunterladen und erneuten Hochladen von Inhalten). Es gibt jedoch potenzielle Fallstricke für diese manuellen Bewegungen, z. B. Dokumente aus 2010, die ein aktuelles zuletzt geändertes Konto mit dem Alias des Kontos haben, das die manuelle Bewegung vor sich hat. Und einige Aufgaben müssen im Voraus erledigt werden, z. B. das Erstellen von Websites, Unterwebsites, Berechtigungen und Listenstrukturen. Achten Sie darauf, ihre Umgebung vor dem Upgrade zu bereinigen. Überlegen Sie, welche Daten Sie in den Speicher verschieben können oder nicht mehr benötigen. Dadurch können die Auswirkungen der Migration reduziert werden. Gehen Sie sicher, dass Ihre vorhandene Farm funktionsfähig ist, bevor Sie ein Upgrade durchführen, und (sicherlich) vor der Außerbetriebnahme!

Denken Sie daran, die *unterstützten und nicht unterstützten Upgradepfade zu überprüfen:*

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

Wenn Sie Anpassungen *haben,* ist es wichtig, dass Sie für jeden Schritt im Migrationspfad planen:

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|Lokale Vorteile|Lokale Nachteile|
|---|---|
|Vollständige Kontrolle über alle Aspekte ihrer SharePoint Farm (und ihrer SQL) von der Serverhardware aus.|Alle Unterbrechungen und Korrekturen liegen in der Verantwortung Ihres Unternehmens. Sie können jedoch den kostenpflichtigen Microsoft-Support ins Unternehmen einmischen, wenn Ihr Produkt nicht über das Ende des Supportendes liegt.|
|Vollständiger Funktionssatz von SharePoint Server lokal mit der Option, Ihre lokale Farm mit einem SharePoint Onlineabonnement über Hybrid zu verbinden.|Upgrade, Patches, Sicherheitskorrekturen, Hardwareupgrades und alle Wartungen von SharePoint Server und seiner SQL werden lokal verwaltet.|
|Vollzugriff für größere Anpassungsoptionen als bei SharePoint Online.|[Microsoft-Complianceangebote](/compliance/regulatory/offering-home) müssen manuell lokal konfiguriert werden.|
|Sicherheitstests und Serverleistungsoptimierungen werden in Ihrer Lokalen unter Ihrer Kontrolle durchgeführt.|Microsoft 365 können Features für SharePoint Online verfügbar machen, die nicht mit dem lokalen SharePoint Server zusammenarbeiten.|
|Lösungsanbieter können bei der Migration von Daten zur nächsten Version von SharePoint Server (und darüber hinaus) helfen.|Ihre SharePoint Serverwebsites verwenden nicht automatisch [SSL/TLS-Zertifikate,](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) wie in SharePoint Online zu sehen ist.|
|Vollständige Kontrolle über Benennungskonventionen, Sicherungs- und Wiederherstellungsoptionen und andere Wiederherstellungsoptionen in SharePoint Server lokal.|SharePoint Der lokale Server ist für Produktlebenszyklen sensibel.|

### <a name="upgrade-resources"></a>Upgraderessourcen

Vergleichen Sie zunächst die Hardware- und Softwareanforderungen. Wenn Ihre aktuelle Umgebung die grundlegenden Anforderungen nicht erfüllt, müssen Sie möglicherweise zuerst die Hardware in der Farm oder den SQL aktualisieren. 

Sie können einige Ihrer Websites auf die "immergrüne" Hardware von SharePoint Verschieben. Nachdem Sie Ihre Bewertung vorgenommen haben, folgen Sie den unterstützten Upgradepfaden und -methoden.

- *Hardware-/Softwareanforderungen für:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *Softwarebeschränkungen und -grenzen für:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *Übersicht über den Upgradeprozess für:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>Erstellen einer Hybridlösung mit SharePoint Online und SharePoint Server lokal

Ein Hybrid-Setup bietet das Beste sowohl lokal als auch online für einige Migrationsanforderungen. Sie können SharePoint Server 2013-, 2016- oder 2019-Farmen mit SharePoint Online verbinden, um eine SharePoint-Hybrid zu erstellen: Erfahren Sie mehr über [SharePoint Hybridlösungen](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).

Wenn eine hybride SharePoint Serverfarm Ihr Migrationsziel ist, können Sie herausfinden, welche Websites und Benutzer online bewegt werden sollen und welche lokal bleiben müssen. Die Bewertung SharePoint Serverfarminhalts als hohe, mittlere oder niedrige Auswirkungen auf Ihr Unternehmen kann bei dieser Entscheidung hilfreich sein. Sie müssen möglicherweise nur Benutzerkonten für die Anmeldung und den SharePoint Server-Suchindex mit SharePoint Online freigeben. Dieser Faktor ist jedoch möglicherweise erst klar, wenn Sie sehen, wie Ihre Websites verwendet werden. Wenn Ihr Unternehmen später beschließt, alle Ihre Inhalte zu SharePoint Online zu migrieren, können Sie alle verbleibenden Konten und Daten online verschieben und Ihre lokale Farm außer Betrieb lassen. Die Verwaltung/Verwaltung der SharePoint erfolgt ab diesem Zeitpunkt über Microsoft 365 Konsolen.

Machen Sie sich unbedingt mit den vorhandenen Hybridtypen vertraut und erfahren Sie, wie Sie die Verbindung zwischen Ihrer lokalen SharePoint-Farm und Ihrem Microsoft 365 konfigurieren.

|Option|Beschreibung|
|---|---|
|[Microsoft Compliance-Angebote](/compliance/regulatory/offering-home).|[Die FastTrack-Unterstützung](https://www.microsoft.com/fasttrack/microsoft-365) für die Migration ist begrenzt.<br/><br/> Ein Teil des Upgrades erfolgt manuell oder über die in SharePoint Online und OneDrive [Migration Content Roadmap beschriebene SPO-Migrations-API.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)|
|Microsoft SupportTechniker und Mitarbeiter des Rechenzentrums haben keinen uneingeschränkten Administratorzugriff auf Ihr Abonnement.|Es können zusätzliche Kosten entstehen, wenn die Hardwareinfrastruktur aktualisiert werden muss, um die neuere Version von SharePoint zu unterstützen, oder wenn eine sekundäre Farm erforderlich ist.|
|Partner können ihnen bei der einmalen Migration Ihrer Daten zu SharePoint helfen.||
|Onlineprodukte werden automatisch im gesamten Dienst aktualisiert. Features sind möglicherweise veraltet, aber es gibt kein echtes Ende der Unterstützung.||

Wenn Sie sich entschieden haben, eine neue website Microsoft 365 zu erstellen und Daten manuell zu dieser zu migrieren, wenn [dies erforderlich](https://www.microsoft.com/microsoft-365/)ist, überprüfen Sie ihre Microsoft 365 Optionen .

### <a name="upgrade-sharepoint-server-on-premises"></a>Upgrade SharePoint lokalen Servers

Es gibt keine Möglichkeit, Versionen in SharePoint überspringen. Das bedeutet, dass Upgrades seriell verwendet werden:

- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Um den gesamten Pfad von SharePoint 2007 zu SharePoint Server 2016 zu übernehmen, bedeutet dies eine erhebliche Zeitinvestition und Hardware (SQL Server müssen ebenfalls aktualisiert werden), Software und Verwaltungskosten. Anpassungen müssen entsprechend der Kritischität des Features aktualisiert oder abgebrochen werden.

> [!NOTE]
> Es ist möglich, Ihre SharePoint 2007-Farm zu verwalten, eine SharePoint Server 2016-Farm auf neuer Hardware zu installieren (sodass die separaten Farmen nebeneinander ausgeführt werden), und dann eine manuelle Migration von Inhalten planen und ausführen (z. B. zum Herunterladen und erneuten Hochladen von Inhalten). Diese manuellen Bewegungen haben jedoch einige Nachteile, z. B. das Verschieben von Dokumenten, die das zuletzt geänderte Konto durch den Alias des Kontos ersetzen, das die manuelle Bewegung vor sich hat. Und viel Arbeit muss im Voraus erledigt werden, z. B. das Erstellen von Websites, Unterwebsites, Berechtigungen und Listenstrukturen. Überlegen Sie auf jeden Fall, welche Daten Sie in den Speicher verschieben können oder die Auswirkungen der Migration nicht mehr reduzieren müssen.

Stellen Sie sicher, dass Ihre Umgebung vor dem Upgrade bereinigt wird. Gehen Sie sicher, dass Ihre vorhandene Farm funktionsfähig ist, bevor Sie ein Upgrade durchführen, und schon gar nicht vor der Außerbetriebnahme!

Denken Sie daran, die *unterstützten und nicht unterstützten Upgradepfade zu überprüfen:*

- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

Wenn Sie Anpassungen *haben,* ist es wichtig, das Upgrade für jeden Schritt im Migrationspfad zu planen:

- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|Lokale Pro|Lokales Con|
|---|---|
|Vollständige Kontrolle über alle Aspekte der SharePoint Farm, von der Serverhardware bis zur Serverhardware.|Alle Unterbrechungen und Korrekturen liegen in der Verantwortung Ihres Unternehmens. (Sie können jedoch den kostenpflichtigen Microsoft-Support ins Unternehmen einmischen, wenn Ihr Produkt nicht mehr am Ende des Supportes liegt.)|
|Vollständiger Funktionssatz von SharePoint Server lokal mit der Option, Ihre lokale Farm mit einem SharePoint Onlineabonnement über Hybrid zu verbinden.|Upgrade, Patches, Sicherheitskorrekturen und die SharePoint lokalen Server.|
|Vollzugriff für eine größere Anpassung.|[Microsoft-Complianceangebote](/compliance/regulatory/offering-home) müssen manuell lokal konfiguriert werden.|
|Sicherheitstests und Serverleistungsoptimierungen werden an Ihrem Standort unter Ihrer Kontrolle durchgeführt.|Microsoft 365 können Features für SharePoint Online verfügbar machen, die nicht mit dem lokalen SharePoint Server zusammenarbeiten.|
|Partner können bei der Migration von Daten zur nächsten Version von SharePoint Server (und darüber hinaus) helfen.|Ihre SharePoint Serverwebsites verwenden nicht automatisch [SSL/TLS-Zertifikate,](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) wie in SharePoint Online zu sehen ist.|
|Vollständige Kontrolle über Benennungskonventionen, Sicherungs- und Wiederherstellungsoptionen und andere Wiederherstellungsoptionen in SharePoint Server lokal.|SharePoint Der lokale Server ist für Produktlebenszyklen sensibel.|

### <a name="upgrade-resources"></a>Upgraderessourcen

Beginnen Sie mit dem Wissen, dass Sie Hardware- und Softwareanforderungen erfüllen, und befolgen Sie dann unterstützte Upgrademethoden.

- *Hardware-/Softwareanforderungen für:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *Softwarebeschränkungen und -grenzen für:*

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *Übersicht über den Upgradeprozess für:*

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Erstellen einer SharePoint Hybridlösung zwischen SharePoint Online und lokal

Wenn die Antwort auf Ihre Migrationsanforderungen zwischen dem steuerelement, das lokal angeboten wird, und den niedrigeren Betriebskosten von SharePoint Online liegt, können Sie SharePoint Server 2013- oder 2016-Farmen über Hybriden eine Verbindung mit SharePoint Online herstellen. [Erfahren Sie mehr SharePoint Hybridlösungen](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Wenn Sie entscheiden, dass eine hybride SharePoint Serverfarm Ihrem Unternehmen vorteilet, machen Sie sich mit den vorhandenen Hybridtypen vertraut und erfahren Sie, wie Sie die Verbindung zwischen Ihrer lokalen SharePoint-Farm und Ihrem Microsoft 365-Abonnement konfigurieren.

Möglicherweise möchten Sie eine Microsoft 365/Testumgebung erstellen, die Sie mit Test lab [Guides einrichten können.](m365-enterprise-test-lab-guides.md) Nachdem Sie ein Test- oder Microsoft 365 erworben haben, können Sie die Websitesammlungen, Webs und Dokumentbibliotheken in SharePoint Online erstellen, zu denen Sie Daten migrieren können. Sie können manuell, mithilfe der Migrations-API oder, wenn Sie Meine Websiteinhalte zu OneDrive for Business, über den Hybrid-Assistenten migrieren.

> [!NOTE]
> Um die Hybridoption zu verwenden, muss ihre SharePoint Server 2010-Farm zuerst lokal auf SharePoint Server 2013 oder 2016 aktualisiert werden. SharePoint Foundation 2010 und SharePoint Foundation 2013 unterstützen keine Hybridverbindungen mit SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Zusammenfassung der Optionen für Office 2010-Client und -Server und Windows 7

Eine visuelle Zusammenfassung der Optionen für Upgrades, Migration und die Cloud für Office 2010-Clients und -Server sowie für Windows 7 finden Sie auf unter dem [Poster zum Supportende](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Ende der Unterstützung für Office 2010-Clients und -Server und Windows 7 Poster](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Dieses Poster veranschaulicht die verschiedenen Pfade, die Sie unternehmen können, um Office 2010-Client- und Serverprodukte und Windows 7-Ende der Unterstützung zu vermeiden, mit bevorzugten Pfaden und Optionsunterstützungen in Microsoft 365 Enterprise hervorgehoben.

Sie können dieses [Poster auch](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) herunterladen und im Letter-, Legal- oder Tabloidformat (11 x 17) drucken.

## <a name="related-articles"></a>Verwandte Artikel

[Ressourcen, die Ihnen beim Upgrade von Office 2007- oder 2010-Servern und -Clients helfen](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](/SharePoint/upgrade-and-update/overview-of-the-upgrade-process-from-sharepoint-2010-to-sharepoint-2013)

[Bewährte Methoden beim Upgrade von SharePoint 2010 auf SharePoint 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)

[Behandeln von Problemen beim Datenbankupgrade in SharePoint 2013](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)

[Suchen nach Microsoft-Lösungsanbietern, die Bei Ihrem Upgrade helfen](https://go.microsoft.com/fwlink/?linkid=841249)

[Aktualisierte Produktwartungsrichtlinie für SharePoint 2013](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-2013)

[Aktualisierte Produktwartungsrichtlinie für SharePoint Server 2016](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-server-2016)