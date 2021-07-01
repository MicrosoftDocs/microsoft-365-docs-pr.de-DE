---
title: Project Roadmap für das Ende des Supports für Server 2010
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
description: Der Support für Project Server 2010 endet am 13. April 2021. Verwenden Sie diesen Artikel als Leitfaden für das Upgrade auf Project Online oder eine neuere version von Project Server lokal.
ms.openlocfilehash: 0ca37d00ee670a8a3f7c83d75864b5af19587951
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229755"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 – Roadmap zum Supportende

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Project Server 2010 wird am **13. April 2021** das Ende des Supports erreichen. Dieses Datum wurde ab dem vorherigen Supportendedatum vom 13. Oktober 2020 verlängert. Wenn Sie derzeit Project Server 2010 verwenden, beachten Sie, dass diese verwandten Produkte die folgenden Supportendedaten aufweisen:

|Produkt |Ende des Supportdatums|
|---|---|
|Project 2010 Standard|13. Oktober 2020|
|Project 2010 Professional|13. Oktober 2020|

Weitere Informationen zum Erreichen des Endes des Supports finden Sie unter [Upgrade von Office 2010-Servern und Clientprodukten.](plan-upgrade-previous-versions-office.md)

## <a name="what-does-end-of-support-mean"></a>Was bedeutet das *Ende des Supports?*

Fast alle Microsoft-Produkte verfügen über einen Supportlebenszyklus, in dem sie neue Features, Fehlerbehebungen und Sicherheitsupdates erhalten. Dieser Lebenszyklus dauert in der Regel 10 Jahre ab der ersten Veröffentlichung des Produkts. Das Ende dieses Lebenszyklus wird als Ende des Supports für das Produkt bezeichnet. Nachdem Project Server 2010 am 13. April 2021 das Ende des Supports erreicht hat, bietet Microsoft nicht mehr:

- Technischer Support für Probleme, die auftreten können.

- Fehlerbehebungen für Probleme, die erkannt werden und sich auf die Stabilität und Nutzbarkeit des Servers auswirken können.

- Sicherheitsfixes für Sicherheitsrisiken, die erkannt werden und den Server anfällig für Sicherheitsverletzungen machen können.

- Zeitzonenupdates.

Die Installation von Project Server 2010 wird nach diesem Datum weiterhin ausgeführt. Aufgrund der zuvor aufgeführten Änderungen wird jedoch dringend empfohlen, dass Sie so bald wie möglich von Project Server 2010 migrieren.

## <a name="what-are-my-options"></a>Welche Optionen habe ich?

Ihre Migrationsoptionen sind:

- Migrieren zu Project Online

- Migrieren zu einer neueren lokalen Version von Project Server (vorzugsweise Project Server 2019)

Hier sind die beiden Pfade, die Sie verwenden können, um das Ende der Unterstützung für Project Server 2010 zu vermeiden.

![Project Server 2010-Upgradepfade](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Warum möchte ich lieber zu Project Server 2019 migrieren?|Warum möchte ich lieber zu Project Online migrieren?|
|---|---|
|Geschäftsregeln schränken mich davon ab, mein Unternehmen in der Cloud zu betreiben.  <br/><br/>  Ich benöte die Kontrolle über Updates für meine Umgebung.|Ich habe Mobile- oder Remotebenutzer.<br/><br/>  Die Kosten für die Migration lokaler Server sind ein wichtiges Problem (Hardware, Software, Zeit und Aufwand für die Implementierung usw.). <br/><br/>  Nach der Migration sind die Kosten für die Wartung meiner Umgebung ein Problem (z. B. automatische Updates, garantierte Betriebszeit usw.).|

> [!NOTE]
> Weitere Informationen zu Ihren Migrationsoptionen finden Sie unter [Ressourcen, die Ihnen beim Upgrade von Office 2010-Servern und -Clients helfen.](upgrade-from-office-2010-servers-and-products.md) Beachten Sie, dass Project Server die Hybridkonfiguration nicht unterstützt, da Project Server und Project Online denselben Ressourcenpool nicht gemeinsam verwenden können.

### <a name="what-are-my-options-for-project-client"></a>Welche Optionen habe ich für Project Client?

Wenn Sie Project Professional 2010 oder Project Standard 2010 verwenden, stehen Ihnen folgende Optionen zur Verfügung:

- Wechseln zu einer neueren Version von Project Professional oder Project Standard
- Wechseln zu einer Onlinelösung, z. B. Project Online oder Project für das Web

#### <a name="move-to-a-newer-version-of-project-client"></a>Wechseln zu einer neueren Version von Project-Client

Wenn Sie von Project Standard 2010 migrieren, können Sie zu einer neueren Version von Project Standard wechseln (Project Standard 2016 oder Project Standard 2019). Es wird empfohlen, zur neuesten Version zu wechseln, um die neuesten Features zu nutzen. Die Migration zu einer weniger aktuellen Version (Project Standard 2016) bedeutet auch, dass Sie früher erneut migrieren müssen.

Entsprechend können Sie bei der Migration von Project Professional 2010 zu einer neueren Version wechseln (Project Professional 2019 oder Project Professional 2016). Wechseln Sie nach Möglichkeit erneut zur neuesten Version. Wenn Sie Project Professional verwenden, um eine Verbindung mit Project Server herzustellen, stellen Sie sicher, dass Sie zu einer Version von Project Professional migrieren, die eine Verbindung mit der version von Project Server herstellt, die Sie verwenden.

Project Professional 2010 können Benutzer auch zum Project Online Desktopclient migrieren, bei dem es sich um eine abonnementbasierte Version von Project Professional 2019 handelt. Es ist in Project Plan 3- und Project Plan 5-Abonnements enthalten.

#### <a name="move-to-an-online-solution"></a>Wechseln zu einer Onlinelösung

Sie können auch von Project Professional 2010 oder Project Standard 2010 zu einer Project abonnementbasierten Onlinelösung migrieren. Sowohl Project Plan 3 als auch Plan 5 umfassen Project Online und das neueste [Cloudangebot, Project für das Web.](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1) Beide bieten neue Features und Vorteile, die sie erkunden können.

Weitere Informationen zu Features und Lizenzen finden Sie unter [Microsoft Project Dienstbeschreibung.](/office365/servicedescriptions/project-online-service-description/project-online-service-description)

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Wichtige Überlegungen für die Migration von Project Server 2010

Berücksichtigen Sie Folgendes, wenn Sie eine Migration von Project Server 2010 planen:

- **Hilfe von einem Microsoft-Lösungsanbieter** erhalten – Ein Upgrade von Project Server 2010 kann eine Herausforderung sein. Dies erfordert viel Vorbereitung und Planung. Es kann besonders schwierig sein, wenn Sie nicht die Person waren, die ursprünglich Project Server 2010 eingerichtet hat. Microsoft-Lösungsanbieter stehen ihnen zur Verfügung, unabhängig davon, ob Sie zu Project Server 2019 oder zu Project Online migrieren möchten. Suchen Sie im Microsoft Solution Provider Center nach einem [Lösungsanbieter.](https://go.microsoft.com/fwlink/p/?linkid=841249)

- **Planen Ihrer Anpassungen** – Anpassungen in Ihrer Project Server 2010-Umgebung funktionieren möglicherweise nicht, wenn Sie zu Project Server 2019 oder Project Online migrieren. Es gibt erhebliche Unterschiede bei der Project Serverarchitektur zwischen den Versionen. Außerdem unterscheiden sich die erforderlichen Betriebssysteme, Datenbankserver und Webbrowser, die mit den Versionen arbeiten. Planen Sie, wie Sie Ihre Anpassungen in der neuen Umgebung testen oder neu erstellen. Nutzen Sie diese Gelegenheit, um festzustellen, ob bestimmte Anpassungen noch erforderlich sind. Weitere Informationen finden Sie unter [Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013).

- **Zeit und Geduld** – Die Planung, Ausführung und Tests von Upgrades dauern erheblich, insbesondere für ein Upgrade auf Project Server 2019. Wenn Sie von Project Server 2010 zu Project Server 2019 migrieren, müssen Sie zuerst zu Project Server 2013 migrieren, Ihre Daten überprüfen, dann zu Project Server 2016 und dann zu Project Server 2019 migrieren. Möglicherweise sollten Sie sich bei einem Microsoft-Lösungsanbieter nach einem Zeitrahmen und geschätzten Kosten für diese fragen.

## <a name="migrate-to-project-online"></a>Migrieren zu Project Online

Wenn Sie sich für die Migration von Project Server 2010 zu Project Online entscheiden, können Sie die folgenden Schritte ausführen, um Ihre Projektplandaten manuell zu migrieren:

1. Speichern Sie Ihre Projektpläne aus Project Server 2010 im MPP-Format.

2. Öffnen Sie mit Project Professional 2016, Project Professional 2019 oder dem Project Online Desktopclient jede MPP-Datei, und speichern und veröffentlichen Sie sie dann in Project Online.

Sie können Ihre PWA Konfiguration manuell in Project Online erstellen (z. B. alle erforderlichen benutzerdefinierten Felder oder Unternehmenskalender neu erstellen). Microsoft-Lösungsanbieter können auch bei diesem Prozess helfen.

Wichtige Ressourcen:

|Ressource|Beschreibung|
|---|---|
|[Erste Schritte mit Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Einrichten und Verwenden von Project Online|
|[Project Online-Dienstbeschreibung](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|Informationen zu den verschiedenen verfügbaren Project Online Plänen|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrieren zu einer neueren lokalen Version von Project Server

Wir sind fest davon überzeugt, dass Sie durch die Migration zu Project Online den besten Nutzen und die beste Benutzererfahrung erzielen. Wir wissen aber auch, dass einige Organisationen Projektdaten lokal aufbewahren müssen. Wenn Sie ihre Projektdaten lokal beibehalten möchten, können Sie Ihre Project Server 2010-Umgebung zu Project Server 2013, Project Server 2016 oder Project Server 2019 migrieren.

Wenn Sie nicht zu Project Online migrieren können, wird empfohlen, zu Project Server 2019 zu migrieren. Project Server 2019 enthält die meisten der wichtigsten Features in früheren Versionen von Project Server. Und es entspricht am besten der benutzererfahrung, die mit Project Online verfügbar ist, obwohl einige Features nur in Project Online verfügbar sind.

Stellen Sie nach Abschluss jeder Migration sicher, dass Ihre Daten erfolgreich migriert wurden.

> [!NOTE]
> Wenn Sie auf eine lokale Lösung beschränkt sind und nur eine Migration zu Project Server 2013 in Betracht ziehen, beachten Sie, dass diese Version nur noch ein paar Jahre Support hat. Das Ende des Supportdatums für Project Server 2013 mit Service Pack am 13. Oktober 2023. Weitere Informationen zu End-of-Support-Terminen finden Sie unter [Microsoft Product Lifecycle-Richtlinie.](/lifecycle/)

### <a name="how-do-i-migrate-to-project-server-2019"></a>Wie kann ich zu Project Server 2019 migrieren?

Die Architekturunterschiede zwischen Project Server 2010 und Project Server 2019 verhindern einen direkten Migrationspfad. Daher müssen Sie Ihre Project Server 2010-Daten zu jeder nachfolgenden Version von Project Server migrieren, bis Sie Project Server 2019 erreichen. Schritte zum Upgrade von Project Server 2010 auf Project Server 2019:

1. Migrieren sie zu Project Server 2013.

2. Migrieren Sie von Project Serve 2013 zu Project Server 2016.

3. Migrieren von Project Server 2016 zu Project Server 2019.

Stellen Sie nach Abschluss jeder Migration sicher, dass Ihre Daten erfolgreich migriert wurden.

### <a name="step-1-migrate-to-project-server-2013"></a>Schritt 1: Migrieren zu Project Server 2013

Umfassende Informationen zum Upgrade von Project Server 2010 auf Project Server 2013 finden Sie unter [Upgrade auf Project Server 2013.](/project/upgrade-to-project-server-2016)

Wichtige Ressourcen:

- [Übersicht über den Project Server 2013-Upgradevorgang](/project/upgrade-to-project-server-2016)

  Hier erhalten Sie eine allgemeine Übersicht über das Upgrade von Project Server 2010 auf Project Server 2013.
- [Planen eines Upgrades auf Project Server 2013](/project/plan-for-upgrade-to-project-server-2016)

  Sehen Sie sich Planungsüberlegungen beim Upgrade von Project Server 2010 auf Project Server 2013 an, einschließlich der Systemanforderungen.

- [Neuerungen bei Project Server 2013-Upgrade](/project/what-s-new-in-project-server-2013-upgrade) umfassen wichtige Änderungen für diese Version, einschließlich:

  - Es gibt kein direktes Upgrade auf Project Server 2013. Die Datenbankanfügungsmethode ist die einzige unterstützte Methode zum Upgrade von Project Server 2010 auf Project Server 2013.

  - Der Upgradevorgang konvertiert nicht nur Ihre Project Server 2010-Daten in Project Server 2013-Format, sondern konsolidiert auch die vier Project Server 2010-Datenbanken in einer einzigen Project Web App-Datenbank.

  - Sowohl SharePoint Server 2013 als auch Project Server 2013 wurden aus der vorherigen Version in anspruchsbasierte Authentifizierung geändert. Wenn Sie die klassische Authentifizierung verwenden, müssen Sie dies beim Upgrade berücksichtigen. Weitere Informationen finden Sie unter [Migrieren von der klassischen Authentifizierung zur anspruchsbasierten Authentifizierung in SharePoint 2013](/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Wichtige Ressourcen:

- [Übersicht über den Prozess zum Upgrade auf Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)

- [Upgrade der Datenbanken und Project Web App-Websitesammlungen (Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Microsoft Project Diagramm des Serverupgradeprozesses](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [Die hervorragende Datenbankkonsolidierung Project Server 2010-2013-Migration in 8 einfachen Schritten](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Schritt 2: Migrieren zu Project Server 2016

Nachdem Sie zu Project Server 2013 gewechselt und sich vergewissert haben, dass Ihre Daten erfolgreich migriert wurden, besteht der nächste Schritt darin, zu Project Server 2016 zu migrieren.

Weitere Informationen finden Sie unter [Upgrade auf Project Server 2016](/Project/upgrade-to-project-server-2016).

Wichtige Ressourcen:

- [Übersicht über den Project Server 2016-Upgradevorgang](/Project/overview-of-the-project-server-2016-upgrade-process)

  Verstehen Sie, was Sie tun müssen, um ein Upgrade von Project Server 2013 auf Project Server 2016 durchzuführen.

- [Planen des Upgrades auf Project Server 2016](/Project/plan-for-upgrade-to-project-server-2016)

  Sehen Sie sich die Planungsüberlegungen an, die Beim Upgrade von Project Server 2013 auf Project Server 2016 zu berücksichtigen sind.

[Dinge, die Sie über Project Server 2016 Upgrade wissen müssen,](/project/plan-for-upgrade-to-project-server-2016#thingknow) umfassen wichtige Änderungen für das Upgrade auf diese Version, einschließlich:

- Beachten Sie beim Erstellen der Project Server 2016 Umgebung, dass die Project Server 2016 Installationsdateien in SharePoint Server 2016 enthalten sind. Weitere Informationen finden Sie unter [Bereitstellen Project Server 2016](/project/deploy-project-server-2016).

- Ressourcenpläne sind in Project Server 2016 veraltet. Ihre Project Server 2013-Ressourcenpläne werden in Project Server 2016 und in Project Online zu Resource Engagements migriert. Weitere Informationen finden Sie [unter "Übersicht: Ressourcenengagements".](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870)

### <a name="step-3-migrate-to-project-server-2019"></a>Schritt 3: Migrieren zu Project Server 2019

Nachdem Sie zu Project Server 2016 migriert und überprüft haben, ob die Daten erfolgreich migriert wurden, besteht der nächste Schritt darin, Ihre Daten zu Project Server 2019 zu migrieren.

Informationen dazu, was Sie tun müssen, um ein Upgrade von Project Server 2016 auf Project Server 2019 durchzuführen, finden Sie unter [Upgrade auf Project Server 2019.](/Project/upgrade-to-project-server-2016)

Wichtige Ressourcen:

- [Übersicht über den Upgradeprozess für Project Server 2019](/project/overview-of-the-project-server-2019-upgrade-process)

  Erfahren Sie, was Sie tun müssen, um ein Upgrade von Project Server 2013 auf Project Server 2016 durchzuführen.

- [Planen des Upgrades auf Project Server 2019](/project/plan-for-upgrade-to-project-server-2019)

  Sehen Sie sich Planungsüberlegungen für das Upgrade von Project Server 2016 auf Project Server 2019 an.

- [Wichtige Informationen zu Project Server 2019-Upgrade](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>Erfahren Sie mehr über wichtige Änderungen für das Upgrade auf diese Version, einschließlich:

  - Durch den Upgradevorgang werden Ihre Daten von Ihrer Project Server 2016-Datenbank in die SharePoint Server 2019 Inhaltsdatenbank migriert.  Project Server 2019 erstellt keine eigene Project Serverdatenbank mehr in der SharePoint Serverfarm.

  - Beachten Sie nach dem Upgrade mehrere Änderungen in Project Web App.  Ausführliche Informationen finden Sie unter [Neuigkeiten in Project Server 2019.](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)

**Weitere Ressourcen:**

- [Project Online Dienstbeschreibungen:](/office365/servicedescriptions/project-online-service-description/project-online-service-description)Sehen Sie sich die Portfolioverwaltungsfunktionen an, die in Project Server 2016 und Project Online Premium enthalten sind.

- [Migrationshandbuch für Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Zusammenfassung der Optionen für Office 2010-Client und -Server und Windows 7

Eine visuelle Zusammenfassung der Optionen für Upgrades, Migration und die Cloud für Office 2010-Clients und -Server sowie für Windows 7 finden Sie auf unter dem [Poster zum Supportende](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Ende des Supports für Office 2010-Clients und -Server und Poster Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Dieses Poster zeigt die verschiedenen Pfade, die Sie verwenden können, um das Ende der Unterstützung für Office 2010-Client- und Serverprodukte und Windows 7 zu vermeiden, wobei bevorzugte Pfade und Optionsunterstützung in Microsoft 365 Enterprise hervorgehoben sind.

Sie können dieses Poster auch [herunterladen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) und im Format "Brief", "Legal" oder "Tabloid" (11 x 17) drucken.

## <a name="related-topics"></a>Verwandte Themen

[Upgrade von SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Upgrade von Office 2010-Servern und -Clients](upgrade-from-office-2010-servers-and-products.md)
