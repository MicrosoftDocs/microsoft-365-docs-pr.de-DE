---
title: Project Roadmap zum Ende des Supportendes von Server 2010
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
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
description: Die Unterstützung für Project Server 2010 endet am 13. April 2021. Verwenden Sie diesen Artikel als Leitfaden zum Upgrade auf Project Online oder eine neuere Version von Project Server lokal.
ms.openlocfilehash: 807c09bff0cb6331b872474acc22f8d2c622a6c6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927372"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 – Roadmap zum Supportende

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Project Server 2010 endet am **13. April 2021.** Dieses Datum wurde vom vorherigen End-of-Support-Datum, dem 13. Oktober 2020, verlängert. Wenn Sie derzeit Project Server 2010 verwenden, beachten Sie, dass diese verwandten Produkte die folgenden End-of-Support-Datumsangaben haben:

|Produkt |Ende des Supportdatums|
|---|---|
|Project 2010 Standard|13. Oktober 2020|
|Project 2010 Professional|13. Oktober 2020|

Weitere Informationen zum Erreichen des Endes des Support finden Sie unter [Upgrade from Office 2010 servers and client products](plan-upgrade-previous-versions-office.md).

## <a name="what-does-end-of-support-mean"></a>Was bedeutet *das Ende der Unterstützung?*

Fast alle #A0 verfügen über einen Supportlebenszyklus, in dem sie neue Features, Fehlerbehebungen und Sicherheitsupdates erhalten. Dieser Lebenszyklus dauert in der Regel 10 Jahre nach der ersten Produktversion. Das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Nachdem Project Server 2010 am 13. April 2021 das Ende des Support erreicht hat, bietet Microsoft nicht mehr:

- Technischer Support für Probleme, die auftreten können.

- Fehlerbehebungen für probleme, die erkannt werden und die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können.

- Sicherheitsbehebungen für gefundene Sicherheitsrisiken, die den Server anfällig für Sicherheitsverletzungen machen können.

- Zeitzonenupdates.

Die Installation von Project Server 2010 wird nach diesem Datum fortgesetzt. Aufgrund der zuvor aufgeführten Änderungen wird jedoch dringend empfohlen, so bald wie möglich von Project Server 2010 zu migrieren.

## <a name="what-are-my-options"></a>Was sind meine Optionen?

Ihre Migrationsoptionen sind:

- Migrieren zu Project Online

- Migrieren zu einer neueren lokalen Version von Project Server (vorzugsweise Project Server 2019)

Hier sind die beiden Pfade, die Sie gehen können, um das Ende der Unterstützung für Project Server 2010 zu vermeiden.

![Project Server 2010-Upgradepfade](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Warum würde ich lieber zu Project Server 2019 migrieren?|Warum würde ich lieber zu einer Project Online?|
|---|---|
|Geschäftsregeln beschränken mich am Betrieb meines Unternehmens in der Cloud.  <br/><br/>  Ich muss die Kontrolle über Updates für meine Umgebung haben.|Ich habe mobile oder Remotebenutzer.<br/><br/>  Die Kosten für die Migration von lokalen Servern sind ein wesentliches Problem (Hardware, Software, Zeit und Aufwand für die Implementierung, und so weiter). <br/><br/>  Nach der Migration sind die Kosten für die Wartung meiner Umgebung ein Problem (z. B. automatische Updates, garantierte Uptime, und so weiter).|

> [!NOTE]
> Weitere Informationen zu Ihren Migrationsoptionen finden Sie unter Ressourcen, die Ihnen beim Upgrade von [Office 2010-Servern und -Clients helfen.](upgrade-from-office-2010-servers-and-products.md) Beachten Sie, Project Server keine Hybridkonfiguration unterstützt, da Project Server und Project Online nicht denselben Ressourcenpool gemeinsam nutzen können.

### <a name="what-are-my-options-for-project-client"></a>Was sind meine Optionen für Project Client?

Wenn Sie 2010 Project Professional 2010 oder Project Standard 2010 verwenden, stehen Ihnen die folgenden Optionen zur Verfügung:

- Wechseln zu einer neueren Version von Project Professional oder Project Standard
- Wechseln zu einer Onlinelösung, z. B. Project Online oder Project für das Web

#### <a name="move-to-a-newer-version-of-project-client"></a>Wechseln zu einer neueren Version Project Client

Wenn Sie von Project Standard 2010 migrieren, können Sie zu einer neueren Version von Project Standard (Project Standard 2016 oder Project Standard 2019) wechseln. Es wird empfohlen, zur neuesten Version zu wechseln, um die neuesten Features zu nutzen. Das Migrieren zu einer weniger aktuellen Version (Project Standard 2016) bedeutet auch, dass Sie früher erneut migrieren müssen.

Wenn Sie von Project Professional 2010 migrieren, können Sie auch zu einer neueren Version wechseln (Project Professional 2019 oder Project Professional 2016). Wechseln Sie nach Möglichkeit erneut zur neuesten Version. Wenn Sie Project Professional zum Herstellen einer Verbindung mit Project Server verwenden, stellen Sie sicher, dass Sie zu einer Version von Project Professional migrieren, die eine Verbindung mit der von Ihnen verwendeten Version von Project Server herstellt.

Project Professional 2010-Benutzer können auch zum Project Online-Desktopclient migrieren, bei dem es sich um eine abonnementbasierte Version von Project Professional 2019 handelt. Sie ist in Project Plan 3 und Project Plan 5 enthalten.

#### <a name="move-to-an-online-solution"></a>Wechseln zu einer Onlinelösung

Sie können auch von Project Professional 2010 oder Project Standard 2010 zu einer Project abonnementbasierten Onlinelösung migrieren. Sowohl Project Plan 3 als auch Plan 5 enthalten Project Online und das neueste Cloudangebot, [Project für das Web.](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1) Beide bieten neue Features und Vorteile, die einen Besuch wert sind.

Weitere Informationen zu Features und Lizenzen finden Sie [unter Microsoft Project Dienstbeschreibung](/office365/servicedescriptions/project-online-service-description/project-online-service-description).

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Wichtige Überlegungen für die Migration von Project Server 2010

Berücksichtigen Sie folgendes, wenn Sie die Migration von Project Server 2010 planen:

- **Hilfe von einem Microsoft-Lösungsanbieter** erhalten – Ein Upgrade von Project Server 2010 kann eine Herausforderung sein. Es erfordert viel Vorbereitung und Planung. Es kann besonders schwierig sein, wenn Sie nicht die Person waren, die server 2010 ursprünglich Project eingerichtet hat. Microsoft-Lösungsanbieter stehen ihnen zur Verfügung, unabhängig davon, ob Sie eine Migration zu Project Server 2019 oder zu Project Online. Suchen Sie im Microsoft Solution Provider Center nach [einem Lösungsanbieter.](https://go.microsoft.com/fwlink/p/?linkid=841249)

- **Planen Ihrer Anpassungen** – Anpassungen in Ihrer Project Server 2010-Umgebung funktionieren möglicherweise nicht, wenn Sie zu Project Server 2019 oder Project Online. Es gibt erhebliche Unterschiede in Project Serverarchitektur zwischen den Versionen. Außerdem unterscheiden sich die erforderlichen Betriebssysteme, Datenbankserver und Webbrowser, die mit den Versionen funktionieren. Planen Sie, wie Sie Ihre Anpassungen in der neuen Umgebung testen oder neu erstellen können. Nutzen Sie diese Gelegenheit, um festzustellen, ob bestimmte Anpassungen noch erforderlich sind. Weitere Informationen finden Sie unter [Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013).

- **Zeit und Geduld** – Upgradeplanung, -ausführung und -tests dauern viel Zeit und Mühe, insbesondere für ein Upgrade auf Project Server 2019. Wenn Sie von Project Server 2010 zu Project Server 2019 migrieren, müssen Sie zuerst zu Project Server 2013 migrieren, Ihre Daten überprüfen, dann zu Project Server 2016 und dann zu Project Server 2019 migrieren. Möglicherweise möchten Sie bei einem Microsoft-Lösungsanbieter nach einem Zeitrahmen und geschätzten Kosten suchen, die ihnen helfen.

## <a name="migrate-to-project-online"></a>Migrieren zu Project Online

Wenn Sie von Project Server 2010 zu Project Online migrieren, können Sie die folgenden Schritte ausführen, um Ihre Projektplandaten manuell zu migrieren:

1. Speichern Sie Ihre Projektpläne Project Server 2010 im MPP-Format.

2. Öffnen Project Professional 2016 ,Project Professional 2019 oder dem Project Online-Desktopclient jede MPP-Datei, und speichern und veröffentlichen Sie sie dann in Project Online.

Sie können Ihre PWA in Project Online (z. B. alle erforderlichen benutzerdefinierten Felder oder Unternehmenskalender neu erstellen). Microsoft-Lösungsanbieter können bei diesem Prozess ebenfalls hilfreich sein.

Wichtige Ressourcen:

|Ressource|Beschreibung|
|---|---|
|[Erste Schritte mit Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Einrichten und Verwenden von Project Online|
|[Project Online-Dienstbeschreibung](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|Informationen zu den verschiedenen Project Online verfügbaren Plänen|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrieren zu einer neueren lokalen Version von Project Server

Wir sind fest davon überzeugt, dass Sie den besten Nutzen und die beste Benutzererfahrung erhalten, indem Sie zu Project Online. Wir wissen aber auch, dass einige Organisationen Projektdaten lokal speichern müssen. Wenn Sie Ihre Projektdaten lokal speichern möchten, können Sie Ihre Project Server 2010-Umgebung zu Project Server 2013, Project Server 2016 oder Project Server 2019 migrieren.

Wenn Sie nicht zu Project Online migrieren können, wird empfohlen, zu Project Server 2019 zu migrieren. Project Server 2019 enthält die meisten wichtigen Features in früheren Versionen von Project Server. Und sie entspricht am besten der mit der Project Online, obwohl einige Features nur in der Project Online.

Stellen Sie nach Abschluss jeder Migration sicher, dass Ihre Daten erfolgreich migriert wurden.

> [!NOTE]
> Wenn Sie auf eine lokale Lösung beschränkt sind und nur eine Migration zu Project Server 2013 in Betracht ziehen, müssen Sie darauf acht geben, dass diese Version nur noch einige Jahre Unterstützung hat. Das Ende des Supportdatums für Project Server 2013 mit Service Pack 2 13. Oktober 2023. Weitere Informationen zu End-of-Support-Datumsangaben finden Sie unter [Microsoft Product Lifecycle Policy](/lifecycle/).

### <a name="how-do-i-migrate-to-project-server-2019"></a>Wie kann ich zu Project Server 2019 migrieren?

Die Architekturunterschiede zwischen Project Server 2010 und Project Server 2019 verhindern einen direkten Migrationspfad. Daher müssen Sie Ihre Project Server 2010-Daten zu jeder nachfolgenden Version von Project Server migrieren, bis Sie Project Server 2019 erreichen. Schritte zum Upgrade Project Server 2010 auf Project Server 2019:

1. Migrieren Sie zu Project Server 2013.

2. Migrieren Sie von Project Serve 2013 zu Project Server 2016.

3. Migrieren Sie von Project Server 2016 zu Project Server 2019.

Stellen Sie nach Abschluss jeder Migration sicher, dass Ihre Daten erfolgreich migriert wurden.

### <a name="step-1-migrate-to-project-server-2013"></a>Schritt 1: Migrieren zu Project Server 2013

Umfassende Informationen zum Upgrade von Project Server 2010 auf Project Server 2013 finden Sie unter [Upgrade to Project Server 2013](/project/upgrade-to-project-server-2016).

Wichtige Ressourcen:

- [Übersicht über den Project Server 2013-Upgradevorgang](/project/upgrade-to-project-server-2016)

  Erhalten Sie eine Übersicht über das Upgrade von Project Server 2010 auf Project Server 2013.
- [Planen eines Upgrades auf Project Server 2013](/project/plan-for-upgrade-to-project-server-2016)

  Berücksichtigen Sie Planungsüberlegungen beim Upgrade von Project Server 2010 auf Project Server 2013, einschließlich Systemanforderungen.

- [Neuerungen in Project Server 2013-Upgrades](/project/what-s-new-in-project-server-2013-upgrade) umfassen wichtige Änderungen für diese Version, einschließlich:

   - Es gibt kein in-place-Upgrade auf Project Server 2013. Die Methode zum Anfügen von Datenbanken ist die einzige unterstützte Methode zum Upgrade von Project Server 2010 auf Project Server 2013.

   - Der Upgradeprozess konvertiert nicht nur Ihre Project Server 2010-Daten in das Project Server 2013-Format, sondern konsolidiert auch die vier Project Server 2010-Datenbanken in einer einzelnen Project Web App-Datenbank.

   - Sowohl SharePoint Server 2013 als auch Project Server 2013 wurden von der vorherigen Version in anspruchsbasierte Authentifizierung geändert. Wenn Sie die klassische Authentifizierung verwenden, müssen Sie dies beim Upgrade berücksichtigen. Weitere Informationen finden Sie unter [Migrieren von der klassischen Authentifizierung zur anspruchsbasierten Authentifizierung in SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Wichtige Ressourcen:

- [Übersicht über den Prozess zum Upgrade auf Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)

- [Upgrade der Datenbanken und Project Web App-Websitesammlungen (Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Microsoft Project Diagramm des Serverupgradeprozesses](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [The Great Database Consolidation, Project Server 2010 to 2013 migration in 8 easy steps](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Schritt 2: Migrieren zu Project Server 2016

Nachdem Sie zu Project Server 2013 wechseln und überprüft haben, ob Ihre Daten erfolgreich migriert wurden, besteht der nächste Schritt in der Migration zu Project Server 2016.

Weitere Informationen finden Sie unter [Upgrade to Project Server 2016](/Project/upgrade-to-project-server-2016).

Wichtige Ressourcen:

- [Übersicht über den Project Server 2016-Upgradevorgang](/Project/overview-of-the-project-server-2016-upgrade-process)

  Verstehen Sie, was Sie tun müssen, um ein Upgrade von Project Server 2013 auf Project Server 2016.

- [Planen des Upgrades auf Project Server 2016](/Project/plan-for-upgrade-to-project-server-2016)

  Sehen Sie sich die Planungsüberlegungen an, die beim Upgrade von Project Server 2013 auf Project Server 2016.

[Wichtige Informationen zum Upgrade Project Server 2016 werden](/project/plan-for-upgrade-to-project-server-2016#thingknow) wichtige Änderungen für das Upgrade auf diese Version behandelt. Dazu gehören:

- Beachten Sie beim Erstellen Project Server 2016, dass Project Server 2016 Installationsdateien in SharePoint Server 2016 enthalten sind. Weitere Informationen finden Sie unter [Deploy Project Server 2016](/project/deploy-project-server-2016).

- Ressourcenpläne sind in der Project Server 2016. Ihre Project Server 2013-Ressourcenpläne werden zu Ressourcen engagements in Project Server 2016 und in Project Online. Weitere [Informationen finden Sie unter Overview: Resource engagements.](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870)

### <a name="step-3-migrate-to-project-server-2019"></a>Schritt 3: Migrieren zu Project Server 2019

Nachdem Sie zu Project Server 2016 migriert und überprüft haben, ob Ihre Daten erfolgreich migriert wurden, besteht der nächste Schritt in der Migration Ihrer Daten zu Project Server 2019.

Informationen zum Upgrade von Project Server 2016 auf Project Server 2019 finden Sie unter [Upgrade to Project Server 2019](/Project/upgrade-to-project-server-2016).

Wichtige Ressourcen:

- [Übersicht über den Project Server 2019-Upgradeprozesses](/project/overview-of-the-project-server-2019-upgrade-process)

  Erhalten Sie ein grundlegendes Verständnis davon, was Sie tun müssen, um ein Upgrade von Project Server 2013 auf Project Server 2016.

- [Planen des Upgrades auf Project Server 2019](/project/plan-for-upgrade-to-project-server-2019)

  Sehen Sie sich Planungsüberlegungen für das Upgrade von Project Server 2016 auf Project Server 2019 an.

- [Dinge, die Sie über das Server 2019-Upgrade Project wissen müssen](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>Erfahren Sie mehr über wichtige Änderungen für das Upgrade auf diese Version, die Folgendes umfassen:

   - Der Upgradeprozess migriert Ihre Daten aus ihrer Project Server 2016 zur SharePoint Server 2019 Inhaltsdatenbank.  Project Server 2019 erstellt keine eigene Project Serverdatenbank in der SharePoint Serverfarm.

   - Beachten Sie nach dem Upgrade mehrere Änderungen in Project Web App.  Weitere Informationen finden Sie unter [What's new in Project Server 2019](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

**Weitere Ressourcen**:

- [Project Online Service Descriptions](/office365/servicedescriptions/project-online-service-description/project-online-service-description): Sehen Sie sich die Portfolioverwaltungsfunktionen an, die in Project Server 2016 und Project Online Premium.

- [Microsoft Office Project Portfolio Server 2010-Migrationshandbuch](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Zusammenfassung der Optionen für Office 2010-Client und -Server und Windows 7

Eine visuelle Zusammenfassung der Optionen für Upgrades, Migration und die Cloud für Office 2010-Clients und -Server sowie für Windows 7 finden Sie auf unter dem [Poster zum Supportende](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Ende der Unterstützung für Office 2010-Clients und -Server und Windows 7 Poster](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Dieses Poster veranschaulicht die verschiedenen Pfade, die Sie gehen können, um das Ende der Unterstützung für Office 2010-Client- und Serverprodukte und Windows 7 zu vermeiden, mit bevorzugten Pfaden und Optionsunterstützung in Microsoft 365 Enterprise hervorgehoben.

Sie können dieses [Poster auch](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) herunterladen und im Letter-, Legal- oder Tabloidformat (11 x 17) drucken.

## <a name="related-topics"></a>Verwandte Themen

[Upgrade von SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Upgrade von Office 2010-Servern und -Clients](upgrade-from-office-2010-servers-and-products.md)