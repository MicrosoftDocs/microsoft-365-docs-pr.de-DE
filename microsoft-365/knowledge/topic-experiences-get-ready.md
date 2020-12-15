---
title: Vorbereiten der Umgebung für Themen Erlebnisse (Vorschau)
description: Stellen Sie Ihre Umgebung bereit, damit Sie möglichst viel Inhalt für Ihre Benutzer bereitstellen können, indem Sie die Themen Erfahrungen (Preview) nutzen.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX
ms.openlocfilehash: 19112b222be328eb75b7eea807bea94e524fd56d
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683438"
---
# <a name="get-your-environment-ready-for-topic-experiences-preview"></a>Vorbereiten der Umgebung für Themen Erlebnisse (Vorschau)

> [!Note]
> Der Inhalt dieses Artikels ist für Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).

Damit Sie das meiste aus Themenbereichen machen können, möchten Sie möglichst viele Inhalte für die Themen Ermittlung enthalten, damit Sie für Ihre Benutzer eine Vielzahl von Themen haben. Welche Inhalte sollten jedoch für die Themen Erkennung verwendet werden? Wie maximieren Sie den indizierten Inhalt, während Sie die Kontrolle übernehmen? Je mehr Inhalt im Bereich ist, desto besser sind die Einblicke, die die künstliche Intelligenz generieren kann. Dieser Artikel führt Sie durch die Planungsschritte, um sicherzustellen, dass Sie den entsprechenden Inhalt einbinden, und dass Sie über die richtigen Personen und Ressourcen verfügen, um für Ihre Benutzer eine gute Erfahrung zu machen.

Um Themen Erfahrungen (Preview) zu planen, müssen Sie Folgendes tun:

![Migrieren, verbinden, modernisieren, sichern und Identifizieren von Schritten für das Onboarding in Knowledge Management](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Migrieren von Inhalten zu SharePoint](#1-migrate-content-to-microsoft-365)
    - Das Thema Mining umfasst nur Inhalte auf SharePoint-Websites.
      - Migrieren Sie nach Möglichkeit wertvolle Inhalte aus externen Quellen in SharePoint Online.
      - Priorisieren von Inhaltsquellen mit hohem Potenzial für implizites Wissen
      - Heben Sie die Vorteile des Wissensmanagements hervor, um Benutzer zu ermutigen, Inhalte von OneDrive zu SharePoint-Websites zu migrieren.

2. [Verbinden von Informationen mit Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - In Zukunft können externe Inhalte in das Knowledge Graph eingefügt und verfügbar gemacht werden.
    - Für Inhalte, die nicht verschoben werden können, sollten Sie Graph-Konnektoren verwenden, um die Suche zu verbessern und auf zukünftige Inklusion vorzubereiten.

3. [Modernisieren von SharePoint-Seiten](#3-modernize-sharepoint-pages)
    - Thema Karten können nur auf modernen Seiten aufgetaucht werden.
    - Identifizieren Sie klassische Seiten mit hohem Profil, die Modernisierungs Kandidaten sind.

4. [Geschützter Inhalt entsprechend](#4-secure-content-appropriately)
    - Thema Ressourcen werden basierend auf den Berechtigungen eines Benutzers auf Sicherheit getrimmt.
    - Identifizieren Sie alle Inhalte, die möglicherweise falsche allgemeine oder einschränkende Berechtigungen haben:
      - Ermutigen von Websitebesitzern, die Freigabe Berichte zum Überprüfen von Berechtigungen zu verwenden
      - Verwenden von Administratoren zum Überwachen von weitgehend freigegebenem Inhalt mithilfe der Suche
      - Ermutigen Sie Inhaltsbesitzer, Inhalte freizugeben, die nicht vertraulich sind und möglicherweise breitere Vorteile für die Organisation haben.
    - Überprüfen Sie Ihre Microsoft Graph-Konfiguration für Benutzer und Inhalte:
      - Thema Mining ehrt die Konfiguration ohne Inhalte aus der Suche oder dem vertiefen. Überprüfen Sie, ob diese Konfigurationen weiterhin relevant sind.

5. [Ermitteln von Wissensmanagern und Themen](#5-identify-knowledge-managers-and-topics)
    - Verwenden Sie vorhandene Taxonomien, um Themen manuell zu erstellen.
    - Ermitteln von Fachleuten (KMU) für erwartete oder geseedte Themen.
    - Identifizieren von Websites, die einen großen Hauptteil von wertvollen Daten umfassen, die für Pilot Themen Mining verwendet werden können.
    - Einbinden von Wissensmanagern und Communities of Practice.

## <a name="1-migrate-content-to-microsoft-365"></a>1. Migrieren von Inhalten zu Microsoft 365

Es gibt verschiedene Tools und Dienste, die Sie bei der Migration unterstützen können – Sie erhalten eine Übersicht und Informationen zum Migrieren [ihrer Inhalte zu Microsoft 365](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online). Zu den Migrationstools gehören:

- [Migrations-Manager](https://docs.microsoft.com/sharepointmigration/mm-get-started)
- [SharePoint-Migrationstool (SPMT)](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365)
- [Partner Migrationstools und-Dienste](https://www.microsoft.com/solution-providers)

Nutzen Sie die Migration optimal:

- Migrieren Sie zu einer modernen Website, die Microsoft Teams umfasst. Während die Indizierung auf einer beliebigen SharePoint-Website (klassisch oder modern) erfolgen kann, erfolgt die Anzeige von Themen für Benutzer über Highlights und Karten nur auf modernen Seiten.
- Verwalten von Benutzernamen – die meisten Migrationstools ermöglichen es Ihnen, Benutzeridentitäten über die Migration hinweg zuzuordnen, sodass Eigenschaften wie "erstellt von" oder "geändert von" nach der Migration beibehalten werden. Dies ist für Themen wichtig, da die Erstellung von Dateien verwendet wird, um die Experten zu identifizieren, die einer Themen Seite oder-Karte hinzugefügt werden. 
- Aussagekräftige Dienstkontonamen – es gibt einige Fälle, in denen die Verwaltung von Benutzernamen nicht möglich ist. Wenn Sie beispielsweise Inhalte migrieren, die von einer Person erstellt wurden, die kein Mitarbeiter der Organisation mehr ist. In dieser Instanz verschiebt die meiste Migrationstools eine Datei so, als ob Sie von einem Administratorkonto oder einem Dienstkonto erstellt wurde. Wenn dies häufig geschieht, kann dieses Dienstkonto dann als Experte gegen Themen aufgelistet werden. Hier wird die Benennung dieses Kontos wirklich wichtig. Wenn Sie es beschreibend machen, ist das vorhanden sein dieser nicht-menschlichen Konten für Benutzer verständlich, die Themen verwenden.

## <a name="2-connect-information-to-microsoft-graph"></a>2. Verbinden von Informationen mit Microsoft Graph

Wenn Sie einige Inhalte nicht migrieren können, verbinden Sie Sie mit dem Microsoft Graph:

- Sie sollten die [Grafik Inhalts-Konnektoren](https://docs.microsoft.com/microsoftsearch/connectors-overview)implementieren. Mithilfe von Connectors können externe Inhalte in Microsoft Graph indiziert werden, wo Sie von den Benutzern dann über die Microsoft-Suche erkannt werden können.
- Durch zukünftige Entwicklungen werden externe Daten in thematischen Erfahrungen integriert.

## <a name="3-modernize-sharepoint-pages"></a>3. Modernisierung von SharePoint-Seiten

Da Themenkarten und Highlights nur auf modernen Seiten angezeigt werden können, aktualisieren Sie alle Seiten, die Sie in Themen Erfahrungen von klassisch bis modern einbeziehen möchten. Weitere Informationen finden Sie unter [modernisieren ihrer klassischen SharePoint-Websites](https://docs.microsoft.com/sharepoint/dev/transform/modernize-classic-sites). Sie können den [SharePoint-Modernisierungs Scanner](https://docs.microsoft.com/sharepoint/dev/transform/modernize-scanner) verwenden, um Ihre klassischen Websites für die Modernisierung vorzubereiten.

Wenn Sie viele klassische Websites haben, priorisieren Sie hohe Profilseiten für die Konvertierung in modern.

## <a name="4-secure-content-appropriately"></a>4. sichere Inhalte entsprechend

Wenn Benutzer mit einer Themenkarte oder einer Themen Seite interagieren, werden möglicherweise verschiedene Ressourcen angezeigt. Dies liegt daran, dass Sie Zugriff auf verschiedene Dateien haben, die dem Thema zugeordnet sind. Wenn die zugrunde liegenden Berechtigungen zu streng sind, könnten die Serendipitous Aspekte der Informationsermittlung durch Themen verringert werden. Wenn Sie dagegen zu umfassend sind, kann ein Thema Inhalte für einen Benutzer aufteilen, die nicht angezeigt werden sollen.
Hier ist die Verwaltung guter Berechtigungen entscheidend. Und ein gutes Berechtigungsmanagement basiert auf einer laufenden Partnerschaft zwischen Administratoren und Inhaltsbesitzern. Dies kann zwar eine fortlaufende Aktivität sein, es gibt jedoch einige praktische Schritte, die Sie bei der Vorbereitung auf Themen durchführen können:

- Ermutigen Sie Websitebesitzer, die Freigabe und Berechtigungen zu überprüfen.

  SharePoint-Websitebesitzer können einen Freigabe Bericht für Ihre Website überprüfen, in dem alle Details aller Berechtigungen und Freigabelinks angezeigt werden, die auf der Website konfiguriert sind, siehe [Freigeben von Berichten](https://docs.microsoft.com/sharepoint/sharing-reports). Dies listet interne und externe Benutzer (Gast) auf.

  Websitebesitzer können auch anzeigen, wer über Berechtigungen für die Website verfügt, indem Sie auf die Seiten **Websiteberechtigungen** und **Erweiterte Berechtigungseinstellungen** wechseln.

  1. Wählen Sie auf Ihrer Website **Einstellungen**  >  **Websiteberechtigungen** aus. Überprüfen Sie, wer Unterwebsite Besitzern, Websitemitgliedern und Websitebesuchern aufgeführt ist. Suchen Sie nach Gastbenutzern.
  2. Wählen Sie auf der Seite **Berechtigungen** die Option **Erweiterte Berechtigungseinstellungen** aus. Sie können nach eindeutigen Berechtigungen suchen und sehen, wer über einen begrenzten Zugriff auf Elemente in der Website verfügt.

- Überwachen Sie Microsoft 365-Gruppen und-Teams, um sicherzustellen, dass diese ordnungsgemäß als öffentliche oder private Gruppen oder Teams festgelegt sind. Neue Teams und Microsoft 365-Gruppen werden standardmäßig auf privat festgelegt, aber bei der ersten Veröffentlichung wurden standardmäßig öffentlich. Wenn Sie zuvor diese Technologien übernommen haben, sollten Sie dies möglicherweise überprüfen. Außerdem wird die Funktion eines Teams häufig über den Lebenszyklus entwickelt, und die Einstellung muss möglicherweise aktualisiert werden, um die aktuelle Verwendung des Teams widerzuspiegeln.
- Überprüfen Sie die Verwendung von "jeder", "jeder außer externen Benutzern" oder breiter Sicherheitsgruppen. Inhalte werden möglicherweise fälschlicherweise für diese Werte freigegeben. Um die Verwendung dieser Gruppen zu überprüfen, können Sie Folgendes tun:
  - Erstellen eines Kontos ohne Gruppenmitgliedschaften
  - Verwenden Sie die Suche mit diesem Konto, um Inhalte zu ermitteln, die weitgehend freigegeben sind.
  - Wenn für dieses Konto ungeeignete Inhalte durchsuchen angezeigt werden, können Sie mit den Websitebesitzern zusammenarbeiten, um die Berechtigungskonfiguration zu korrigieren.

Zusätzlich zu den Berechtigungen können Sie auch den Bereich dessen bestimmen, was über Themen auffindbar ist. Sie haben immer die Kontrolle über das, was indiziert wird.

Administratoren können die Indizierung im Microsoft 365 Admin Center konfigurieren. Beim Einrichten der [Wissensverwaltung](set-up-topic-experiences.md)haben Sie folgende Möglichkeiten:

- Lassen Sie die Ermittlung auf allen SharePoint-Websites zu, oder geben Sie Websites an, die als Themen Quellen einbezogen oder ausgeschlossen werden sollen.
- Wenn Sie vertrauliche Ausdrücke haben, können Sie Themen auch nach Namen ausschließen. Wenn Sie beispielsweise den Namen eines vertraulichen Projekts haben, in dem kein Highlight oder eine Karte angezeigt werden soll, ohne Rücksicht auf die Berechtigungen des Benutzers, können Sie diesen Projektnamen ausschließen.

Auf Inhaltsebene können Sie auch steuern, was erkannt werden kann. Jede Konfiguration, die Sie zum Ausschließen von Inhalten aus der Suche durchgeführt haben, wird auch von der Inhaltsermittlung verwendet. Wenn Sie beispielsweise ausschließen, dass eine bestimmte Dokumentbibliothek in den Suchergebnissen angezeigt wird, wird diese Dokumentbibliothek nicht für die Themen Ermittlung verwendet.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. Identifizieren von Knowledge Managern und Themen

Das Verwalten von Themen umfasst drei wichtige Rollen, darunter zwei neue Azure Active Directory (AAD)-Rollen: Knowledge Administrator und Knowledge Manager:

- Der Wissens Verwalter (KA) ist eine technische Rolle, in der Regel darin. Diese Rolle ermöglicht das Einrichten des Themas "Experiences" im M365 Admin Center sowie die Konfiguration der Themen Erkennung und-Sichtbarkeit.
- Der Knowledge Manager (km) arbeitet mit den Themen selbst zusammen und überwacht deren Qualität und Vollständigkeit.
- "Topic Contributors" (TCS) basieren nicht auf einer Aad-Rolle, sondern auf Berechtigungen im Admin Center. Sie sind Fachexperten, die in der Lage sind, Inhalte zu Themen zu unterstützen, Ressourcen und Personen hinzuzufügen.

Je nach Organisation haben Sie möglicherweise nur wenige oder viele Personen, die in diesen Rollen handeln. Für einige Organisationen können diese dieselben Personen sein.

| Wissens Administrator | Knowledge Manager | Thema Mitwirkender |
|:-------|:-------|:-------|:-------|
| Aad-Rolle | Aad-Rolle | KMU |
| Zugriff auf das Admin Center | Zugriff auf das Admin Center | Kein Zugriff auf das Admin Center |
| Richtet Themen Erfahrungen ein. | Besitzt Verwaltung und Qualität der Themen | Trägt zu Themen auf der Grundlage ihrer Expertise bei. |
| Stellt sicher, dass Sicherheits-und Konformitätsstandards erzwungen werden und den Lizenzvertrag verstehen.| Führt Themen Verwaltungsaufgaben wie erstellen, bearbeiten, löschen und ablehnen aus. Unterstützt Themen Mitwirkende bei ihren Aufgaben. | Kuratiert die Informationen und Inhalte auf Themenseiten, einschließlich der Personen und Ressourcen, die an dieses Thema angeheftet sind. |

Die Highlights und Karten werden Benutzern im Kontext ihrer Arbeit angezeigt, beispielsweise, wenn Sie moderne Seiten in SharePoint durchsuchen. Sie steuern die Benutzeroberfläche für Themen.

- Wer kann Themen sehen? Die Sichtbarkeit des Themas wird im Microsoft 365 Admin Center konfiguriert. Wählen Sie aus, welche Gruppen zum Anzeigen von Themen zugelassen werden sollen:
  - Jeder in meiner Organisation. "Jeder" schließt keine Gäste ein, sondern alle internen Benutzer in Ihrem Verzeichnis.
  - Nur ausgewählte Personen oder Sicherheitsgruppen (diese Option ist gut, wenn Sie noch Themen Erfahrungen bereitstellen, damit Sie mit einer Teilmenge von Benutzern testen können). Wenn Sie möchten, dass die Gäste Themen anzeigen, müssen Sie die Option "ausgewählte Personen oder Sicherheitsgruppen" verwenden und Ihnen eine Lizenz erteilen.
  - Mit niemandem.

    Für alle Benutzer, auch für Gastbenutzer, muss eine Lizenz angewendet werden, um die Themenerfahrung anzeigen zu können. Und denken Sie daran, dass Berechtigungen immer steuern, was gesehen werden kann.

- Welche Themen sind sichtbar? Sie können Folgendes auswählen:
  - Alle Kandidaten Themen anzeigen.
  - Nur bestätigte Themen anzeigen.

Da wir nun über die Manager, Experten und Benutzer verfügen, können wir über die Themen selbst sprechen.

- Es empfiehlt sich, Themen in ihrer Themenliste zu seeden. Die Qualität und Quantität der Themen basiert auf ihren Inhalten – Sie wird nur als Thema erstellt, wenn Sie in dem Inhalt enthalten ist, der im Bereich liegt. Wenn genügend Informationen und Beweise für das Thema vorhanden sind, wird es von der AI erstellt. In den Themen zum Seeding können der Knowledge Manager und die Experten für Fachfragen helfen. Die Kombination von menschlichem Wissen mit der AI ist die beste Route für Qualitätsthemen. Wenn Sie also Themen haben, die Sie vorhersehen, können Sie diese im Themen Center manuell erstellen. Dadurch wird die KI ein starkes Signal für die Relevanz dieses Themas geben, und es werden Ressourcen und Personen identifiziert, die mit diesem Thema verknüpft werden sollen.
- Verwenden Sie vorhandene Taxonomien, um Ihre Themen Planung zu unterstützen, sei es in SharePoint oder anderswo. Vorhandene Taxonomien umfassen häufig organisatorische Begriffe, Produkte, Themenbereiche usw. Quellen für Themen können auch aus Listen von Projekten, vorhandenen Such Lesezeichen usw. stammen.
