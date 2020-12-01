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
description: Hier finden Sie Informationen und Ressourcen für ein Upgrade von SharePoint 2010 und SharePoint Server 2010. Unterstützung für beide Enden 13. April 2021.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fba095a15164f8a09ce1e0a1cbd5ee9cd298aa74
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519763"
---
# <a name="upgrading-from-sharepoint-2010"></a>Upgrade von SharePoint 2010

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft SharePoint 2010 und SharePoint Server 2010 werden am **13. April 2021** am Ende der Unterstützung erreichen. In diesem Artikel finden Sie Ressourcen, die Sie beim Migrieren Ihrer vorhandenen SharePoint Server 2010 Daten zu SharePoint Online in Microsoft 365 oder beim Upgrade Ihrer lokalen SharePoint Server 2010 Umgebung unterstützen.

## <a name="what-is-end-of-support"></a>Was ist das *Ende der Unterstützung*?

Die meisten Microsoft-Produkte haben einen Support-Lebenszyklus, in dem Sie neue Funktionen, Bugfixes, Sicherheitsfixes usw. erhalten. Nach dem End-of-Support-Datum wird das Produkt nicht mehr funktionsfähig, aber Microsoft bietet nicht mehr Folgendes:

- Technischer Support für Probleme, die auftreten können.

- Fehlerbehebungen für Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können.

- Sicherheitsfixes für Sicherheitsanfälligkeiten, die den Server möglicherweise anfällig für Sicherheitsverletzungen machen.

- Zeitzonenaktualisierungen.

Das bedeutet, dass es keine weiteren Updates, Patches oder Fixes für das Produkt geben wird (einschließlich Sicherheitspatches/Fixes). Der Microsoft-Support hat seine Support Bemühungen auf neuere Versionen vollständig verschoben.

Löschen Sie als Ende der Unterstützung SharePoint Server 2010 Ansätze Daten, die Sie nicht mehr benötigen, bevor Sie das Produkt aktualisieren und wichtige Daten migrieren.

> [!NOTE]
> Ein Software-Lebenszyklus dauert in der Regel zehn Jahre ab der ersten Version. [Microsoft Solution Provider](https://go.microsoft.com/fwlink/?linkid=841249) können Ihnen helfen, ein Upgrade auf die nächste Version der Software durchführen oder zu Microsoft 365 Migration (oder beides) migrieren. Stellen Sie sicher, dass Sie über End-of-Support-Termine für wichtige zugrunde liegende Technologien informiert sind, insbesondere für die Version von Microsoft SQL Server, die Sie mit SharePoint verwenden. Weitere Informationen finden Sie unter [Fixed Lifecycle Policy](https://support.microsoft.com/help/14085).

## <a name="plan-ahead"></a>Vorausschauend planen

Überprüfen Sie die Termine, die Unterstützung für die [Produktlebenszyklus-Website](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010)endet. Planen Sie Ihre Upgrades oder Migrationen mit diesen Terminen im Hinterkopf. Denken Sie daran, dass Ihr Produkt am angegebenen Datum *nicht mehr funktioniert* . Da Ihre Installation jedoch nach diesem Datum nicht mehr gepatcht wird, sollten Sie einen reibungslosen Übergang zur nächsten Produktversion planen.

Diese Matrix hilft beim Plotten eines Kurses unter Migrationsoptionen:

|Ende des Support Produkts|Gut |Optimal|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (lokal)|SharePoint Online|
||SharePoint Server 2013 Hybrid mit SharePoint Online|SharePoint Server 2016 (lokal)|
|||SharePoint-Cloud-Hybrid Suche|

Wenn Sie eine Option am unteren Ende der Skala (gut) auswählen, müssen Sie mit der Planung eines weiteren Upgrades bald nach der Migration von SharePoint Server 2010 beginnen.

Hier sind die drei Pfade, die Sie ausführen können, um das Ende der Unterstützung für SharePoint Server 2010 zu vermeiden.

![SharePoint Server 2010 Aktualisierungspfade](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> Das Ende der Unterstützung für SharePoint Server 2010 und SharePoint Foundation 2010 ist derzeit für April 2021 geplant. Stellen Sie jedoch sicher, dass Sie auf der [Produktlebenszyklus-Website](https://support.microsoft.com/lifecycle) nach den aktuellsten Terminen suchen.

## <a name="whats-next"></a>Nächste Schritte

SharePoint Server 2013 und SharePoint Foundation 2013 können lokal auf Ihren eigenen Servern installiert werden. Sie können auch SharePoint Online verwenden, bei dem es sich um einen Online Dienst handelt, der Teil von Microsoft 365 ist. Sie können Folgendes auswählen:

- Migrieren Sie zu SharePoint Online.

- Upgrade SharePoint Server oder SharePoint Foundation lokal.

- Führen Sie beide der oben genannten Aufgaben aus.

- Implementieren Sie eine [SharePoint-Hybrid](https://docs.microsoft.com/sharepoint/hybrid/hybrid) Lösung.

Halten Sie sich an die versteckten Kosten für die Verwaltung einer Serverfarm, einschließlich der Verwaltung oder Migration von Anpassungen und dem Upgrade von Hardware. Wenn Sie diese Faktoren berücksichtigt haben, ist es einfacher, lokal zu aktualisieren. Wenn Sie die Farm auf älteren SharePoint-Servern ohne starke Anpassung ausführen, können Sie von einer geplanten Migration zu SharePoint Online profitieren. Für eine lokale SharePoint Server Umgebung können Sie auch einige Daten in SharePoint Online verschieben, um den Hardware Verwaltungsaufwand zu reduzieren.

> [!NOTE]
> SharePoint-Administratoren können ein Microsoft 365-Abonnement erstellen, neue SharePoint Online Websites einrichten und dann SharePoint Server 2010 sauber abschneiden, wobei nur die wichtigen Dokumente für die neuen Websites berücksichtigt werden. Anschließend können alle verbleibenden Daten von der SharePoint Server 2010 Website in lokale Archive entwässert werden.

|SharePoint Online|SharePoint Server lokal|
|---|---|
|Hohe Kosten in der Zeit (Planung/Ausführung/Überprüfung)|Hohe Kosten in der Zeit (Planung/Ausführung/Überprüfung)|
|Geringere Kosten in Fonds (keine hardwarekäufe)|Höhere Kosten in Fonds (hardwarekäufe)|
|Einmalige Kosten bei der Migration|Wiederholte einmalige Kosten pro künftiger Migration|
|Niedrige Total Cost of Ownership/Maintenance|Hohe Gesamtbetriebskosten/Wartung|

Eine einmalige Umstellung auf Microsoft 365 wird höhere Kosten verursachen, während Sie Daten organisieren und entscheiden, was Sie in die Cloud übernehmen und was Sie zurücklassen möchten. Nachdem Ihre Daten migriert wurden, werden zukünftige Upgrades jedoch automatisch durchführen, da Sie keine Hardware-und Softwareupdates mehr verwalten müssen. Und die Dauer der Farm wird durch eine [Vereinbarung zum Service Level (SLA) von Microsoft](https://go.microsoft.com/fwlink/?linkid=843153)gesichert.

### <a name="migrate-to-sharepoint-online"></a>Migrieren zu SharePoint Online

Stellen Sie sicher, dass SharePoint Online alle Funktionen bietet, die Sie benötigen. Siehe [SharePoint-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).

Sie können nicht direkt von SharePoint Server 2010 (oder SharePoint Foundation 2010) zu SharePoint Online migrieren. Ein Großteil der Migrationsarbeit ist manuell. In dieser Phase haben Sie jedoch die Möglichkeit, Daten und Websites zu löschen, die vor dem Wechsel nicht mehr benötigt werden. Sie können andere Daten in den Speicher archivieren. 

Beachten Sie, dass SharePoint Server 2010 und SharePoint Foundation 2010 am Ende der Unterstützung nicht mehr funktionieren. Administratoren können also einen Zeitraum haben, in dem SharePoint noch läuft, wenn Ihre Kunden vergessen, einige Ihrer Daten zu verlegen.

Wenn Sie ein Upgrade auf SharePoint Server 2013 oder SharePoint Server 2016 durchführen und beschließen, Daten in SharePoint Online zu übertragen, können Sie die [SharePoint-Migrations-API](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) verwenden, um Informationen in OneDrive für Unternehmen zu migrieren.

|SharePoint Online Vorteil|SharePoint Online Nachteil|
|---|---|
|Microsoft liefert SPO-Hardware und die gesamte Hardwareverwaltung.|Die verfügbaren Features können zwischen SharePoint Server lokal und SPO unterschiedlich sein.|
|Sie sind der globale Administrator Ihres Abonnements und können Administratoren den SPO-Websites zuweisen.|Einige Aktionen, die einem Farmadministrator in SharePoint Server lokal zur Verfügung stehen, sind in der SharePoint-Administratorrolle in Microsoft 365 nicht vorhanden (oder sind nicht erforderlich). SharePoint-Verwaltung, Websitesammlungsverwaltung und Website Besitz sind jedoch lokal für Ihre Organisation.|
|Microsoft wendet Patches, Fixes und Updates auf zugrunde liegende Hardware und Software an, einschließlich SQL-Servern, auf denen SharePoint Online ausgeführt wird.|Da der Zugriff auf das zugrunde liegende Dateisystem im Dienst nicht möglich ist, ist die Anpassung begrenzt.|
|Microsoft veröffentlicht [Vereinbarungen zum Service Level](https://go.microsoft.com/fwlink/?linkid=843153) und wird schnell zur Lösung von Vorfällen auf Dienstebene verschoben.|Sicherungs-und Wiederherstellungsoptionen werden vom Dienst in SharePoint Online automatisiert. Sicherungen werden überschrieben, wenn Sie nicht verwendet werden.|
|Sicherheitstests und Server Leistungsoptimierung werden von Microsoft kontinuierlich im Dienst ausgeführt.|Änderungen an der Benutzeroberfläche und anderen SharePoint-Features werden vom Dienst installiert und müssen möglicherweise aktiviert oder deaktiviert werden.|
|Microsoft 365 erfüllt viele Branchenstandards: [Microsoft Compliance-Angebote](https://go.microsoft.com/fwlink/?linkid=843165).|Die [Pannen](https://go.microsoft.com/fwlink/?linkid=518597) Unterstützung für die Migration ist limitiert.  <br/> Ein Großteil des Upgrades erfolgt manuell oder über die SPO-Migrations-API, die in der [Roadmap SharePoint Online and OneDrive Migration Content](https://go.microsoft.com/fwlink/?linkid=843184)beschrieben wird.|
|Microsoft-Support Techniker und Mitarbeiter des Rechenzentrums haben keinen uneingeschränkten Administratorzugriff auf Ihr Abonnement.|Es kann zusätzliche Kosten entstehen, wenn die Hardware Infrastruktur aktualisiert werden muss, um die neuere Version von SharePoint zu unterstützen, oder wenn eine sekundäre Farm für das Upgrade erforderlich ist.|
|Lösungsanbieter können Ihnen bei der einmaligen Migration Ihrer Daten zu SharePoint Online helfen.|Nicht alle Änderungen an SharePoint Online befinden sich in Ihrem Steuerelement. Nach der Migration können sich Design Unterschiede in Menüs, Bibliotheken und anderen Features vorübergehend auf die Benutzerfreundlichkeit auswirken.|
|Online Produkte werden automatisch im gesamten Dienst aktualisiert. Features können veraltet sein, aber es gibt kein True End of Support Lifecycle.|Es gibt einen End-of-Support-Lebenszyklus für SharePoint Server oder SharePoint Foundation und zugrunde liegende SQL-Server.|

Wenn Sie sich entschieden haben, eine neue Microsoft 365-Website zu erstellen und die Daten nach Bedarf manuell zu migrieren, überprüfen Sie die [Microsoft 365-Optionen](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>Upgrade SharePoint Server lokal

Ab SharePoint Server 2019 müssen Upgrades  *seriell* durchlaufen. Es gibt keine Möglichkeit, direkt von SharePoint Server 2010 auf SharePoint Server 2016 oder auf SharePoint 2019 zu aktualisieren. Pfad für serielles Upgrade:

- SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Es dauert Zeit und plant, den gesamten Pfad von SharePoint 2010 zu SharePoint Server 2016 zu verfolgen. Upgrades beinhalten Kosten für Hardware (SQL Server müssen ebenfalls aktualisiert werden), Software und Verwaltung. Außerdem müssen Anpassungen möglicherweise aktualisiert oder sogar aufgegeben werden. Stellen Sie sicher, dass Sie wichtige Anpassungen vor dem Upgrade Ihrer SharePoint Server Farm dokumentieren.

> [!NOTE]
> Es ist möglich, Ihre End-of-Support-SharePoint 2010 Farm beizubehalten, eine SharePoint Server 2016-Farm auf neuer Hardware zu installieren (damit die separaten Farmen nebeneinander ausgeführt werden) und dann eine manuelle Inhaltsmigration zu planen und auszuführen (beispielsweise zum herunterladen und erneuten Hochladen von Inhalten). Es gibt jedoch potenzielle Gefahren für diese manuellen Verschiebungen, beispielsweise Dokumente, die von 2010 mit einem aktuellen Konto mit der letzten Änderung mit dem Alias des Kontos, das die manuelle Verschiebung ausführt, vorliegen. Einige Aufgaben müssen im Voraus erfolgen, beispielsweise das Neuerstellen von Websites, Unterwebsites, Berechtigungen und Listenstrukturen. Achten Sie darauf, Ihre Umgebung vor dem Upgrade zu säubern. Berücksichtigen Sie, welche Daten Sie in den Speicher umlegen oder nicht mehr benötigen. Dadurch können die Auswirkungen der Migration reduziert werden. Stellen Sie sicher, dass Ihre vorhandene Farm funktionsfähig ist, bevor Sie ein Upgrade durchführen, und (sicherlich) bevor Sie außer Betrieb nehmen!

Denken Sie daran, die *unterstützten und nicht unterstützten Upgrade-Pfade* zu überprüfen:

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Wenn Sie *Anpassungen* haben, ist es wichtig, dass Sie die einzelnen Schritte im Migrationspfad planen:

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|Lokaler Vorteil|Lokale Benachteiligung|
|---|---|
|Vollzugriff auf alle Aspekte der SharePoint-Farm (und deren SQL), von der Server Hardware bis hin.|Alle Unterbrechungen und Fixes liegen in der Verantwortung Ihres Unternehmens. Sie können jedoch den kostenpflichtigen Microsoft-Support einbinden, wenn Ihr Produkt nicht am Ende der Unterstützung vorbei ist.|
|Vollständiger Funktionsumfang von SharePoint Server lokal mit der Option zum Verbinden Ihrer lokalen Farm mit einem SharePoint Online-Abonnement über Hybrid.|Upgrade, Patches, Sicherheitsfixes, Hardwareupgrades und die gesamte Wartung von SharePoint Server und seiner SQL-Farm werden lokal verwaltet.|
|Vollzugriff für größere Anpassungsoptionen als bei SharePoint Online.|[Microsoft Compliance-Angebote](https://go.microsoft.com/fwlink/?linkid=843165) müssen lokal manuell konfiguriert werden.|
|Sicherheitstests und Server-Leistungsoptimierung werden vor Ort unter ihrer Kontrolle ausgeführt.|Microsoft 365 kann Features für SharePoint Online zur Verfügung stellen, die nicht mit SharePoint Server vor Ort zusammenarbeiten.|
|Lösungsanbieter können die Migration von Daten zur nächsten Version von SharePoint Server (und darüber hinaus) unterstützen.|Auf Ihren SharePoint Server Websites werden nicht automatisch [SSL/TLS-](https://go.microsoft.com/fwlink/?linkid=843167) Zertifikate verwendet, wie in SharePoint Online angezeigt wird.|
|Vollzugriff auf Benennungskonventionen sowie Sicherungs-und Wiederherstellungsoptionen und andere Wiederherstellungsoptionen in SharePoint Server lokal.|SharePoint Server lokal reagiert auf Produktlebenszyklen.|

### <a name="upgrade-resources"></a>Aktualisieren von Ressourcen

Vergleichen Sie zunächst die Hardware-und Softwareanforderungen. Wenn Ihre aktuelle Umgebung nicht die grundlegendenAnforderungen erfüllt, müssen Sie möglicherweise zuerst die Hardware in der Farm oder den SQL-Servern aktualisieren. 

Sie können beschließen, einige ihrer Websites auf die "Evergreen"-Hardware von SharePoint Online zu migrieren. Nachdem Sie Ihre Bewertung vorgenommen haben, befolgen Sie die unterstützten Aktualisierungspfade und-Methoden.

- *Hardware-/Softwareanforderungen für:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *Software Beschränkungen und-Grenzen für:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *Die Übersicht über den Updateprozess für:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>Erstellen einer Hybridlösung mit SharePoint Online und SharePoint Server lokal

Ein Hybrid-Setup bietet das Beste aus lokalen und Online für einige Migrationsanforderungen. Sie können SharePoint Server 2013-, 2016-oder 2019-Farmen mit SharePoint Online verbinden, um eine SharePoint-Hybridlösung zu erstellen: [erfahren Sie mehr über SharePoint-Hybridlösungen](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).

Wenn es sich bei einer hybriden SharePoint Server Farm um ein Migrationsziel handelt, sollten Sie herausfinden, welche Websites und Benutzer online zu migrieren sind und welche lokal bleiben müssen. Die Rangfolge Ihrer SharePoint Server Farm Inhalte als hohe, mittlere oder geringe Auswirkung auf Ihr Unternehmen kann bei dieser Entscheidung helfen. Sie müssen möglicherweise nur Benutzerkonten für die Anmeldung und den SharePoint Server-Suchdienst Index mit SharePoint Online freigeben. Dieser Faktor ist jedoch möglicherweise erst dann erkennbar, wenn Sie sich ansehen, wie Ihre Websites verwendet werden. Wenn Ihr Unternehmen später entscheidet, alle Ihre Inhalte in SharePoint Online zu migrieren, können Sie alle verbleibenden Konten und Daten Online verschieben und Ihre lokale Farm außer Betrieb nehmen. Die Verwaltung/Verwaltung der SharePoint-Farm erfolgt von diesem Ort aus über Microsoft 365-Konsolen.

Stellen Sie sicher, dass Sie sich mit den vorhandenen Hybrid Typen vertraut machen und die Verbindung zwischen Ihrer lokalen SharePoint-Farm und Ihrem Microsoft 365-Abonnement konfigurieren.

|Option|Beschreibung|
|---|---|
|[Microsoft Compliance-Angebote](https://go.microsoft.com/fwlink/?linkid=843165).|Die [Pannen](https://www.microsoft.com/fasttrack/microsoft-365) Unterstützung für die Migration ist limitiert.<br/><br/> Ein Großteil des Upgrades erfolgt manuell oder über die SPO-Migrations-API, die in der [Roadmap SharePoint Online and OneDrive Migration Content](https://go.microsoft.com/fwlink/?linkid=843184)beschrieben wird.|
|Microsoft-Support Techniker und Mitarbeiter des Rechenzentrums haben keinen uneingeschränkten Administratorzugriff auf Ihr Abonnement.|Es gibt möglicherweise zusätzliche Kosten, wenn die Hardware Infrastruktur aktualisiert werden muss, um die neuere Version von SharePoint zu unterstützen, oder wenn eine sekundäre Farm erforderlich ist.|
|Partner können mit der einmaligen Aufgabe der Migration Ihrer Daten zu SharePoint Online behilflich sein.||
|Online Produkte werden automatisch im gesamten Dienst aktualisiert. Features können veraltet sein, aber es gibt kein echtes Ende der Unterstützung.||

Wenn Sie sich entschieden haben, eine neue Microsoft 365-Website zu erstellen und die Daten nach Bedarf manuell zu migrieren, überprüfen Sie die [Microsoft 365-Optionen](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>Upgrade SharePoint Server lokal

Es gibt keine Möglichkeit, Versionen in SharePoint-Upgrades zu überspringen. Das bedeutet, dass Upgrades seriell gehen:

- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Um den gesamten Pfad von SharePoint 2007 auf SharePoint Server 2016 zu übertragen, bedeutet dies eine erhebliche Investition von Zeit und umfasst Hardware (SQL Server müssen ebenfalls aktualisiert werden), Software und Verwaltungskosten. Anpassungen müssen entsprechend der Wichtigkeit des Features aktualisiert oder aufgegeben werden.

> [!NOTE]
> Es ist möglich, Ihre End-of-Life-SharePoint 2007-Farm beizubehalten, eine SharePoint Server 2016-Farm auf neuer Hardware zu installieren (damit die separaten Farmen nebeneinander ausgeführt werden) und dann eine manuelle Inhaltsmigration zu planen und auszuführen (beispielsweise zum herunterladen und erneuten Hochladen von Inhalten). Es gibt jedoch einige Nachteile dieser manuellen Verschiebungen, wie beispielsweise Verschiebungen von Dokumenten, die das letzte geänderte Konto durch den Alias des Kontos ersetzen, das die manuelle Verschiebung ausführt. Viel Arbeit muss im Voraus erfolgen, beispielsweise das Neuerstellen von Websites, Unterwebsites, Berechtigungen und Listenstrukturen. Berücksichtigen Sie in jedem Fall die Daten, die Sie in den Speicher umlegen können, oder die Auswirkungen der Migration nicht mehr reduzieren müssen.

Stellen Sie sicher, dass Ihre Umgebung vor dem Upgrade bereinigt wird. Stellen Sie sicher, dass Ihre vorhandene Farm funktionsfähig ist, bevor Sie ein Upgrade durchführen, und zwar vor der Außerbetriebnahme!

Denken Sie daran, die *unterstützten und nicht unterstützten Upgrade-Pfade* zu überprüfen:

- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Wenn Sie *Anpassungen* haben, ist es wichtig, das Upgrade für jeden Schritt im Migrationspfad zu planen:

- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|Lokale pro|Lokale con|
|---|---|
|Vollzugriff auf alle Aspekte der SharePoint-Farm, von der Server Hardware bis hin.|Alle Unterbrechungen und Fixes liegen in der Verantwortung Ihres Unternehmens. (Sie können jedoch den kostenpflichtigen Microsoft-Support einbinden, wenn Ihr Produkt nicht am Ende der Unterstützung vorbei ist.)|
|Vollständiger Funktionsumfang von SharePoint Server lokal mit der Option zum Verbinden Ihrer lokalen Farm mit einem SharePoint Online-Abonnement über Hybrid.|Upgrade, Patches, Sicherheitspatches und alle Wartung von SharePoint Server lokal verwaltet.|
|Vollzugriff für eine größere Anpassung.|[Microsoft Compliance-Angebote](https://go.microsoft.com/fwlink/?linkid=843165) müssen lokal manuell konfiguriert werden.|
|Sicherheitstests und die Optimierung der Serverleistung werden vor Ort unter ihrer Kontrolle ausgeführt.|Microsoft 365 kann Features für SharePoint Online zur Verfügung stellen, die nicht mit SharePoint Server lokal zusammenarbeiten.|
|Partner können bei der Migration von Daten zur nächsten Version von SharePoint Server (und darüber hinaus) helfen.|Auf Ihren SharePoint Server Websites werden nicht automatisch [SSL/TLS-](https://go.microsoft.com/fwlink/?linkid=843167) Zertifikate verwendet, wie in SharePoint Online angezeigt wird.|
|Vollzugriff auf Benennungskonventionen sowie Sicherungs-und Wiederherstellungsoptionen und andere Wiederherstellungsoptionen in SharePoint Server lokal.|SharePoint Server lokal reagiert auf Produktlebenszyklen.|

### <a name="upgrade-resources"></a>Aktualisieren von Ressourcen

Beginnen Sie mit dem wissen, dass Sie die Hardware-und Softwareanforderungen erfüllen und dann unterstützte Upgrade-Methoden ausführen.

- *Hardware-/Softwareanforderungen für*:

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *Software Beschränkungen und-Grenzen für*:

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *Die Übersicht über den Updateprozess für*:

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Erstellen einer SharePoint-Hybridlösung zwischen SharePoint Online und lokal

Wenn die Antwort auf Ihre Migrationsanforderungen irgendwo zwischen dem Steuerelement, das lokal angeboten wird, und den niedrigeren von SharePoint Online angebotenen Besitzkosten liegt, können Sie SharePoint Server 2013-oder 2016-Farmen mit SharePoint Online über Hybriden verbinden. [Informationen zu SharePoint-Hybridlösungen](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Wenn Sie entscheiden, dass eine hybride SharePoint Server Farm Ihrem Unternehmen zugute kommt, machen Sie sich mit den vorhandenen Hybrid Typen vertraut und konfigurieren Sie die Verbindung zwischen Ihrer lokalen SharePoint-Farm und Ihrem Microsoft 365-Abonnement.

Möglicherweise möchten Sie eine Microsoft 365-Entwicklungs-/Testumgebung erstellen, die Sie mit [testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)einrichten können. Nachdem Sie eine Testversion oder ein erworbenes Microsoft 365-Abonnement erhalten haben, können Sie die Websitesammlungen, Webs und Dokumentbibliotheken in SharePoint Online erstellen, in der Sie Daten migrieren können. Sie können mithilfe der Migrations-API manuell migrieren oder, wenn Sie meine Website Inhalte zu OneDrive für Unternehmen migrieren möchten, über den Hybrid-Assistenten.

> [!NOTE]
> Um die Hybrid Option verwenden zu können, muss Ihre SharePoint Server 2010 Farm zunächst lokal auf SharePoint Server 2013 oder 2016 aktualisiert werden. SharePoint Foundation 2010 und SharePoint Foundation 2013 unterstützen keine Hybrid Verbindungen mit SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Zusammenfassung der Optionen für Office 2010 Client und Server und Windows 7

Eine visuelle Zusammenfassung der Optionen für Upgrades, Migration und die Cloud für Office 2010-Clients und -Server sowie für Windows 7 finden Sie auf unter dem [Poster zum Supportende](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Ende der Unterstützung für Office 2010-Clients und-Server und Windows 7 Poster](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Dieses Poster zeigt die verschiedenen Pfade, die Sie ergreifen können, um Office 2010 Client-und Serverprodukte und Windows 7 Ende der Unterstützung zu vermeiden, wobei bevorzugte Pfade und Options Unterstützungen in Microsoft 365 Enterprise hervorgehoben werden.

Sie können dieses Poster auch [herunterladen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) und im Format "Letter", "Legal" oder "Tabloid" (11 x 17) ausdrucken.

## <a name="related-articles"></a>Verwandte Artikel

[Ressourcen zum Upgraden von Office 2007-oder 2010-Servern und-Clients](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)

[Bewährte Methoden beim Upgrade von SharePoint 2010 auf SharePoint 2013](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)

[Behandeln von Problemen beim Datenbankupgrade in SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)

[Suchen nach Microsoft Solution Providern zur Unterstützung des Upgrades](https://go.microsoft.com/fwlink/?linkid=841249)

[Aktualisierte Produktwartungsrichtlinie für SharePoint 2013](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)

[Aktualisierte Produktwartungsrichtlinie für SharePoint Server 2016](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
