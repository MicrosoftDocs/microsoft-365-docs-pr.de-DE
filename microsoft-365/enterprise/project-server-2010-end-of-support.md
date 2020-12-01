---
title: Project Server 2010-Roadmap zum Ende des Supports
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
description: Unterstützung endet für Project Server 2010 endet am 13. April 2021. Verwenden Sie diesen Artikel als Leitfaden für ein Upgrade auf Project Online oder eine neuere Version von Project Server lokal.
ms.openlocfilehash: 239b3d93cfa6a1184ea21225fa97732712b8eb14
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519702"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 – Roadmap zum Supportende

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Project Server 2010 wird am **13. April 2021** am Ende der Unterstützung erreichen. Dieses Datum wurde vom vorherigen End-of-Support-Datum vom 13. Oktober 2020 verlängert. Wenn Sie Project Server 2010 derzeit verwenden, beachten Sie, dass diese verwandten Produkte über die folgenden End-of-Support-Termine verfügen:

|Produkt |Ende des Support Datums|
|---|---|
|Project 2010 Standard|13. Oktober 2020|
|Project 2010 Professional|13. Oktober 2020|

Weitere Informationen zum Erreichen des Endes der Unterstützung finden Sie unter [Upgrade von Office 2010-Servern und-Clientprodukten](plan-upgrade-previous-versions-office.md).

## <a name="what-does-end-of-support-mean"></a>Was bedeutet das *Ende der Unterstützung* ?

Fast alle Microsoft-Produkte verfügen über einen Support-Lebenszyklus, in dem Sie neue Features, Bugfixes und Sicherheitsupdates erhalten. Dieser Lebenszyklus dauert in der Regel 10 Jahre nach der ersten Version des Produkts. Das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Nachdem Project Server 2010 am 13. April 2021 das Ende der Unterstützung erreicht hat, stellt Microsoft nicht mehr Folgendes bereit:

- Technischer Support für Probleme, die auftreten können.

- Fehlerbehebungen für entdeckte Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können.

- Sicherheitsfixes für Sicherheitsanfälligkeiten, die erkannt werden und die den Server möglicherweise anfällig für Sicherheitsverletzungen machen.

- Zeitzonenaktualisierungen.

Die Installation von Project Server 2010 wird weiterhin nach diesem Datum ausgeführt. Aufgrund der zuvor aufgeführten Änderungen wird jedoch dringend empfohlen, dass Sie so bald wie möglich von Project Server 2010 migrieren.

## <a name="what-are-my-options"></a>Was sind meine Optionen?

Ihre Migrationsoptionen sind:

- Migrieren zu Project Online

- Migrieren zu einer neueren lokalen Version von Project Server (vorzugsweise Project Server 2019)

Hier sind die beiden Wege, die Sie ergreifen können, um das Ende der Unterstützung für Project Server 2010 zu vermeiden.

![Project Server 2010 Aktualisierungspfade](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Warum sollte ich lieber zu Project Server 2019 migrieren?|Warum sollte ich lieber zu Project Online migrieren?|
|---|---|
|Geschäftsregeln beschränken mich auf das betreiben meines Unternehmens in der Cloud.  <br/><br/>  Ich benötige die Kontrolle über Updates für meine Umgebung.|Ich habe Mobile oder Remote-Benutzer.<br/><br/>  Die Kosten für die Migration lokaler Server stellen ein erhebliches Problem dar (Hardware, Software, Zeit und Aufwand für die Implementierung usw.). <br/><br/>  Nach der Migration sind Kosten für die Wartung meiner Umgebung ein Problem (beispielsweise automatische Updates, garantierte Betriebszeit usw.).|

> [!NOTE]
> Weitere Informationen zu ihren Migrationsoptionen finden Sie unter [Ressourcen, die Ihnen beim Upgrade von Office 2010 Servern und Clients helfen](upgrade-from-office-2010-servers-and-products.md). Beachten Sie, dass Project Server keine Hybrid Konfiguration unterstützt, da Project Server und Project Online nicht denselben Ressourcenpool freigeben können.

### <a name="what-are-my-options-for-project-client"></a>Welche Optionen habe ich für den Projekt Client?

Wenn Sie Project Professional 2010 oder Project Standard 2010 verwenden, stehen Ihnen die folgenden Optionen zur Verfügung:

- Wechsel zu einer neueren Version von Project Professional oder Project Standard
- Navigieren zu einer Online Lösung wie Project Online oder Project für das Internet

#### <a name="move-to-a-newer-version-of-project-client"></a>Wechsel zu einer neueren Version des Projekt Clients

Wenn Sie eine Migration von Project Standard 2010 durchführen, können Sie zu einer neueren Version von Project Standard (Project Standard 2016 oder Project Standard 2019) wechseln. Es wird empfohlen, dass Sie zu der neuesten Version übergehen, um die neuesten Funktionen nutzen zu können. Die Migration zu einer Version mit einer niedrigeren Stromstärke (Project Standard 2016) bedeutet auch, dass Sie die Migration früher wiederholen müssen.

Ebenso können Sie, wenn Sie von Project Professional 2010 migrieren, zu einer neueren Version (Project Professional 2019 oder Project Professional 2016) wechseln. Kehren Sie nach Möglichkeit erneut zur neuesten Version zurück. Wenn Sie Project Professional zum Herstellen einer Verbindung mit Project Server verwenden, stellen Sie sicher, dass Sie zu einer Version von Project Professional migrieren, die mit der Version von Project Server verbindet, die Sie verwenden.

Project Professional 2010 Benutzer können auch zum Project Online-Desktop Client migrieren, bei dem es sich um eine abonnementbasierte Version von Project Professional 2019 handelt. Er ist in Project Plan 3-und Project Plan 5-Abonnements enthalten.

#### <a name="move-to-an-online-solution"></a>Wechsel zu einer Online Lösung

Sie können auch von Project Professional 2010 oder Project Standard 2010 zu einer auf dem Projekt Abonnement basierenden Online Lösung migrieren. Projektplan 3 und Plan 5 umfassen Project Online und das neueste Cloud-Angebot, [Project für das Internet](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Beide bieten neue Features und Vorteile, die es zu erkunden lohnt.

Weitere Informationen zu Features und Lizenzen finden Sie unter [Microsoft Project-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description).

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Wichtige Überlegungen für die Migration von Project Server 2010

Berücksichtigen Sie beim Planen der Migration von Project Server 2010 Folgendes:

- **Erhalten Sie Hilfe von einem Microsoft Solution Provider** – ein Upgrade von Project Server 2010 kann eine Herausforderung darstellen. Es erfordert viel Vorbereitung und Planung. Es kann eine besondere Herausforderung darstellen, wenn Sie nicht die Person sind, die Project Server 2010 ursprünglich eingerichtet hat. Microsoft Solution Provider stehen Ihnen zur Verfügung, unabhängig davon, ob Sie eine Migration zu Project Server 2019 oder zu Project Online planen. Suchen Sie im [Microsoft Solution Provider Center](https://go.microsoft.com/fwlink/p/?linkid=841249)nach einem Lösungsanbieter.

- **Planen der Anpassungen** – Anpassungen in Ihrer Project Server 2010 Umgebung funktionieren möglicherweise nicht, wenn Sie zu Project Server 2019 oder Project Online migrieren. Es gibt erhebliche Unterschiede bei der Architektur von Project Server zwischen Versionen. Außerdem unterscheiden sich die erforderlichen Betriebssysteme, Datenbankserver und Webbrowser, die mit den Versionen funktionieren. Planen Sie, wie Sie Ihre Anpassungen in der neuen Umgebung testen oder neu erstellen. Nutzen Sie diese Gelegenheit, um festzustellen, ob bestimmte Anpassungen noch erforderlich sind. Weitere Informationen finden Sie unter [Create a plan for current customizations during upgrade to SharePoint 2013](https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013).

- **Zeit und Geduld** : das Upgrade von Planung, Ausführung und Tests erfordert erheblich Zeit und Aufwand, insbesondere für ein Upgrade auf Project Server 2019. Wenn Sie von Project Server 2010 zu Project Server 2019 migrieren, müssen Sie zunächst zu Project Server 2013 migrieren, Ihre Daten überprüfen und dann zu Project Server 2016 und dann zu Project Server 2019 migrieren. Möglicherweise möchten Sie sich mit einem Microsoft Solution Provider für einen Zeitrahmen und die geschätzten Kosten für die Unterstützung erkundigen.

## <a name="migrate-to-project-online"></a>Migrieren zu Project Online

Wenn Sie von Project Server 2010 zu Project Online migrieren möchten, können Sie die folgenden Schritte ausführen, um die Projektplandaten manuell zu migrieren:

1. Speichern Sie Ihre Projektpläne in Project Server 2010 im MPP-Format.

2. Wenn Sie Project Professional 2016, Project Professional 2019 oder den Project Online-Desktop-Client verwenden, öffnen Sie jede MPP-Datei, und speichern und veröffentlichen Sie Sie dann in Project online.

Sie können die PWA-Konfiguration manuell in Project online erstellen (beispielsweise alle erforderlichen benutzerdefinierten Felder oder Enterprise-Kalender neu erstellen). Microsoft Solution Provider können diesen Prozess auch unterstützen.

Wichtige Ressourcen:

|Ressource|Beschreibung|
|---|---|
|[Erste Schritte mit Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Einrichten und Verwenden von Project Online|
|[Project Online-Dienstbeschreibung](https://go.microsoft.com/fwlink/p/?linkid=829088)|Informationen zu den verschiedenen verfügbaren Project Online Plänen|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrieren zu einer neueren lokalen Version von Project Server

Wir sind der festen Überzeugung, dass Sie mit der Migration zu Project Online den besten nutzen und die optimale Benutzererfahrung erzielen. Wir wissen jedoch auch, dass einige Organisationen Projektdaten lokal aufbewahren müssen. Wenn Sie Ihre Projektdaten lokal beibehalten möchten, können Sie Ihre Project Server 2010 Umgebung zu Project Server 2013, Project Server 2016 oder Project Server 2019 migrieren.

Wenn Sie nicht zu Project Online migrieren können, wird empfohlen, dass Sie zu Project Server 2019 migrieren. Project Server 2019 umfasst die meisten wichtigen Features in früheren Versionen von Project Server. Und Sie entspricht am ehesten der mit Project online verfügbaren Funktionalität, obwohl einige Features nur in Project online verfügbar sind.

Nachdem Sie jede Migration abgeschlossen haben, stellen Sie sicher, dass die Daten erfolgreich migriert wurden.

> [!NOTE]
> Wenn Sie auf eine lokale Lösung und nur auf die Migration zu Project Server 2013 beschränkt sind, beachten Sie, dass diese Version nur noch ein paar Jahre Support hat. Das Ende der Unterstützung Datum für Project Server 2013 mit Service Pack 2 Oktober 2023. Weitere Informationen zu End-of-Support-Terminen finden Sie unter [Microsoft Product Lifecycle Policy](https://go.microsoft.com/fwlink/p/?linkid=842066).

### <a name="how-do-i-migrate-to-project-server-2019"></a>Wie kann ich zu Project Server 2019 migrieren?

Die architektonischen Unterschiede zwischen Project Server 2010 und Project Server 2019 verhindern einen direkten Migrationspfad. Sie müssen also Ihre Project Server 2010 Daten zu jeder nachfolgenden Version von Project Server migrieren, bis Sie Project Server 2019 erreichen. Schritte zum Upgrade Project Server 2010 auf Project Server 2019:

1. Migrieren Sie zu Project Server 2013.

2. Migrieren von Project Serve 2013 zu Project Server 2016.

3. Migrieren von Project Server 2016 zu Project Server 2019.

Nachdem Sie jede Migration abgeschlossen haben, stellen Sie sicher, dass die Daten erfolgreich migriert wurden.

### <a name="step-1-migrate-to-project-server-2013"></a>Schritt 1: Migrieren zu Project Server 2013

Umfassende Informationen zum Upgrade von Project Server 2010 auf Project Server 2013 finden Sie unter [Upgrade to Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822).

Wichtige Ressourcen:

- [Übersicht über den Project Server 2013-Upgradevorgang](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Hier erhalten Sie eine allgemeine Übersicht über das Upgrade von Project Server 2010 auf Project Server 2013.
- [Planen des Upgrades auf Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823)

  Schauen Sie sich Planungsüberlegungen beim Upgrade von Project Server 2010 auf Project Server 2013 an, einschließlich Systemanforderungen.

- [Was ist neu in Project Server 2013-Upgrade](https://go.microsoft.com/fwlink/p/?linkid=841824) umfasst wichtige Änderungen für diese Version, einschließlich:

   - Es gibt kein direktes Upgrade auf Project Server 2013. Die Methode der Datenbankanfügung ist die einzige unterstützte Möglichkeit zum Upgrade von Project Server 2010 auf Project Server 2013.

   - Durch den Upgradeprozess werden nicht nur Ihre Project Server 2010 Daten in Project Server 2013 Format konvertiert, sondern auch die vier Project Server 2010 Datenbanken werden in einer einzigen Project Web App Datenbank konsolidiert.

   - Sowohl SharePoint Server 2013 als auch Project Server 2013 wurden in die anspruchsbasierte Authentifizierung aus der vorherigen Version geändert. Wenn Sie die klassische Authentifizierung verwenden, müssen Sie dies beim Upgrade berücksichtigen. Weitere Informationen finden Sie unter [Migrieren von der klassischen Authentifizierung zur anspruchsbasierten Authentifizierung in SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Wichtige Ressourcen:

- [Übersicht über den Prozess zum Upgrade auf Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [Upgrade der Datenbanken und Project Web App-Websitesammlungen (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Microsoft Project Server-Aktualisierungsprozess (Diagramm)](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [Die große Datenbankkonsolidierung Project Server 2010 zu 2013 Migration in 8 einfachen Schritten](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Schritt 2: Migrieren zu Project Server 2016

Nachdem Sie zu Project Server 2013 verschoben und sichergestellt haben, dass Ihre Daten erfolgreich migriert wurden, besteht der nächste Schritt in der Migration zu Project Server 2016.

Weitere Informationen finden Sie unter [Upgrade auf Project Server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Wichtige Ressourcen:

- [Übersicht über den Project Server 2016-Upgradevorgang](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Erfahren Sie, was Sie für ein Upgrade von Project Server 2013 auf Project Server 2016 tun müssen.

- [Planen des Upgrades auf Project Server 2016](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Sehen Sie sich die Planungsüberlegungen beim Upgrade von Project Server 2013 auf Project Server 2016 an.

[Dinge, die Sie über das Project Server 2016-Upgrade wissen müssen](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) , umfassen wichtige Änderungen für das Upgrade auf diese Version, einschließlich:

- Beachten Sie beim Erstellen der Project Server 2016-Umgebung, dass die Installationsdateien für Project Server 2016 in SharePoint Server 2016 enthalten sind. Weitere Informationen finden Sie unter [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).

- Ressourcenpläne sind in Project Server 2016 veraltet. Ihre Project Server 2013 Ressourcenpläne werden zu Ressourcen Projekten in Project Server 2016 und in Project Online migriert. Weitere Informationen finden Sie unter [Übersicht: Ressourcen Engagements](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) .

### <a name="step-3-migrate-to-project-server-2019"></a>Schritt 3: Migrieren zu Project Server 2019

Nachdem Sie zu Project Server 2016 migriert und sichergestellt haben, dass die Daten erfolgreich migriert wurden, besteht der nächste Schritt darin, Ihre Daten zu Project Server 2019 zu migrieren.

Informationen zu den Schritten, die Sie für ein Upgrade von Project Server 2016 auf Project Server 2019 benötigen, finden Sie unter [Upgrade to Project Server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Wichtige Ressourcen:

- [Übersicht über den Upgradeprozess für Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Erfahren Sie, wie Sie ein Upgrade von Project Server 2013 auf Project Server 2016 durchführen müssen.

- [Planen des Upgrades auf Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Sehen Sie sich die Planungsüberlegungen für das Upgrade von Project Server 2016 auf Project Server 2019 an.

- [Dinge, die Sie über das Upgrade von Project Server 2019 wissen müssen](https://go.microsoft.com/fwlink/p/?linkid=841827)<br/><br/>Erfahren Sie mehr über wichtige Änderungen beim Upgrade auf diese Version, einschließlich:

   - Durch den Upgradeprozess werden Ihre Daten aus Ihrer Project Server 2016-Datenbank in die SharePoint Server 2019-Inhaltsdatenbank migriert.  Project Server 2019 erstellt keine eigene Project Server-Datenbank mehr in der SharePoint Server Farm.

   - Beachten Sie nach dem Upgrade mehrere Änderungen in Project Web App.  Ausführliche Informationen finden Sie unter [What es New in Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

**Weitere Ressourcen**:

- [Project Online Service Beschreibungen](https://go.microsoft.com/fwlink/p/?linkid=841280): siehe die in Project Server 2016 und Project Online Premium enthaltenen Portfolio Verwaltungsfunktionen.

- [Migrationshandbuch für Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Zusammenfassung der Optionen für Office 2010 Client und Server und Windows 7

Eine visuelle Zusammenfassung der Optionen für Upgrades, Migration und die Cloud für Office 2010-Clients und -Server sowie für Windows 7 finden Sie auf unter dem [Poster zum Supportende](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Ende der Unterstützung für Office 2010-Clients und-Server und Windows 7 Poster](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Dieses Poster zeigt die verschiedenen Wege, die Sie ergreifen können, um das Ende der Unterstützung für Office 2010 Client-und Serverprodukte und Windows 7 zu vermeiden, wobei bevorzugte Pfade und Options Unterstützung in Microsoft 365 Enterprise hervorgehoben werden.

Sie können dieses Poster auch [herunterladen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) und im Format "Letter", "Legal" oder "Tabloid" (11 x 17) ausdrucken.

## <a name="related-topics"></a>Verwandte Themen

[Upgrade von SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Upgrade von Office 2010-Servern und -Clients](upgrade-from-office-2010-servers-and-products.md)
