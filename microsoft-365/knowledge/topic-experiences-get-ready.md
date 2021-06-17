---
title: Vorbereiten Ihrer Umgebung für Microsoft Viva Topics
description: Bereiten Sie Ihre Umgebung vor, damit Sie ihren Benutzern so viele Inhalte wie möglich mit Microsoft Viva Topics bereitstellen können.
ms.author: samanro
author: samanro
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 8e1da50c120d333812014f6720f1168d4afb9741
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984880"
---
# <a name="get-your-environment-ready-for-microsoft-viva-topics"></a>Vorbereiten Ihrer Umgebung für Microsoft Viva Topics

Um Viva Topics optimal zu nutzen, möchten Sie so viele Inhalte wie möglich für die Themensuche verwenden, damit Sie eine vielzahl von Themen für Ihre Benutzer haben können. Aber welche Inhalte sollten für die Themensuche verwendet werden? Wie maximieren Sie den indizierten Inhalt, während Sie die Kontrolle haben? Je mehr Inhalte im Umfang enthalten sind, desto besser sind die Einblicke, die die künstliche Intelligenz entdecken kann. Dieser Artikel führt Sie durch die Planungsschritte, um sicherzustellen, dass Sie die entsprechenden Inhalte einschließen und über die richtigen Personen und Ressourcen verfügen, um Ihren Benutzern eine gute Erfahrung zu bieten.

Um Viva Topics zu planen, müssen Sie:

![Migrieren, Verbinden, Modernisieren, Sichern und Identifizieren von Schritten für das Onboarding zu Viva Topics.](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Migrieren von Inhalten zu SharePoint](#1-migrate-content-to-microsoft-365)
    - Die Themenindizierung enthält nur Inhalte auf SharePoint Websites.
      - Migrieren Sie nach Möglichkeit wertvolle Inhalte aus externen Quellen in SharePoint Online.
      - Priorisieren Sie Inhaltsquellen mit hohem Potenzial für implizites Wissen.
      - Heben Sie die Vorteile von Viva Topics hervor, um Benutzer zu ermutigen, Inhalte von OneDrive auf SharePoint Websites zu verschieben.

2. [Verbinden Informationen an Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - In Zukunft können externe Inhalte in das Wissensdiagramm aufgenommen und verfügbar gemacht werden.
    - Für Inhalte, die nicht verschoben werden können, sollten Sie die Verwendung von Graph Connectors in Betracht ziehen, um die Suche zu verbessern und sich auf die zukünftige Einbindung vorzubereiten.

3. [Modernisieren SharePoint Seiten](#3-modernize-sharepoint-pages)
    - Themenkarten können nur auf modernen Seiten angezeigt werden.
    - Identifizieren Sie klassische Seiten mit hohem Profil, die Modernisierungskandidaten sind.

4. [Angemessenes Sichern von Inhalten](#4-secure-content-appropriately)
    - Themenressourcen werden basierend auf den Berechtigungen eines Benutzers auf die Sicherheit gekürzt.
    - Identifizieren Von Inhalten, die möglicherweise nicht ordnungsgemäß umfassende oder restriktive Berechtigungen haben:
      - Ermutigen Von Websitebesitzern, die Freigabeberichte zum Überprüfen von Berechtigungen zu verwenden
      - Administratoren müssen mithilfe der Suche allgemein freigegebene Inhalte überwachen
      - Ermutigen Sie Inhaltsbesitzer, Inhalte freizugeben, die nicht vertraulich sind und für die Organisation von größerem Nutzen sein können.
    - Überprüfen Sie Ihre Microsoft Graph-Konfiguration für Benutzer und Inhalte:
      - Die Themenindizierung berücksichtigt die Konfiguration mit Ausnahme von Inhalten aus der Suche oder Delve (z. B. NOINDEX). Überprüfen Sie, ob diese Konfigurationen weiterhin relevant sind.

5. [Identifizieren von Wissensmanagern und Themen](#5-identify-knowledge-managers-and-topics)
    - Verwenden Sie vorhandene Taxonomien, um Themen manuell zu erstellen, oder helfen Sie, ki-vorgeschlagene Themen zu bestätigen.
    - Identifizieren Sie Fachexperten (Subject Matter Experts, SMEs) für erwartete oder ausgangse Themen.
    - Identifizieren Sie Websites, die eine große Menge wertvoller Daten abdecken, die zum Pilotthema-Mining verwendet werden können.
    - Binden Sie Wissensmanager und Praxisgemeinschaften ein.

## <a name="1-migrate-content-to-microsoft-365"></a>1. Migrieren von Inhalten zu Microsoft 365

Es gibt mehrere Tools und Dienste, die Sie bei der Migration unterstützen können. Sie erhalten eine Übersicht und Informationen zur Migration bei [Migrate your content to Microsoft 365.](/sharepointmigration/migrate-to-sharepoint-online) Zu den Migrationstools gehören:

- [Migrations-Manager](/sharepointmigration/mm-get-started)
- [SharePoint-Migrationstool (SPMT)](/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Tools und Dienste für die Partnermigration](https://www.microsoft.com/solution-providers)

Nutzen Sie Ihre Migration:

- Migrieren Sie zu einer modernen Website, die Microsoft Teams enthält. Während die Indizierung auf jeder SharePoint-Website (klassisch oder modern) erfolgen kann, erfolgt die Anzeige von Themen für Benutzer durch Hervorhebungen und Karten nur auf modernen Seiten.
- Verwalten von Benutzernamen – mit den meisten Migrationstools können Sie Benutzeridentitäten während der Migration zuordnen, sodass Eigenschaften wie "Erstellt von" oder "Geändert von" nach der Migration beibehalten werden. Dies ist für Themen wichtig, da die Erstellung von Dateien verwendet wird, um die Experten zu identifizieren, die einer Themenseite oder Karte hinzugefügt werden. 
- Beschreiben von Dienstkontonamen – es gibt einige Fälle, in denen die Verwaltung von Benutzernamen nicht möglich ist. Wenn Sie beispielsweise Inhalte migrieren, die von einer Person erstellt wurden, die kein Mitarbeiter der Organisation mehr ist. In diesem Fall verschieben die meisten Migrationstools eine Datei so, als ob sie von einem Administratorkonto oder einem Dienstkonto erstellt worden wäre. Wenn dies häufig der Fall ist, könnte dieses Dienstkonto als Experte für Themen aufgeführt werden. Hier wird die Benennung dieses Kontos wirklich wichtig. Wenn Sie es beschreiben, ist das Vorhandensein dieser nicht menschlichen Konten für Ihre Benutzer verständlich, die Themen verwenden.

## <a name="2-connect-information-to-microsoft-graph"></a>2. Verbinden Informationen an Microsoft Graph

Wenn Sie einige Inhalte nicht migrieren können, stellen Sie eine Verbindung mit dem Microsoft Graph her:

- Erwägen Sie die Implementierung [Graph Inhaltsconnectors.](/microsoftsearch/connectors-overview) Mithilfe von Connectors können externe Inhalte im Microsoft Graph indiziert werden, wo Benutzer sie dann über Microsoft Search entdecken können.
- Zukünftige Entwicklungen werden externe Daten in Viva Topics übertragen.

## <a name="3-modernize-sharepoint-pages"></a>3. Modernisieren SharePoint Seiten

Da Themenkarten und Highlights nur auf modernen Seiten angezeigt werden können, aktualisieren Sie alle Seiten, die Sie in Viva Topics einschließen möchten, von klassisch bis modern. Weitere Informationen finden Sie unter ["Modernisieren Ihrer klassischen SharePoint Websites".](/sharepoint/dev/transform/modernize-classic-sites) Sie können den [SharePoint Modernisierungsscanner](/sharepoint/dev/transform/modernize-scanner) verwenden, um Ihre klassischen Websites auf die Modernisierung vorzubereiten.

Wenn Sie über viele klassische Websites verfügen, sollten Sie Seiten mit hohem Informationsgehalt priorisieren, um sie auf modern zu konvertieren.

## <a name="4-secure-content-appropriately"></a>4. Angemessenes Sichern von Inhalten

Wenn Benutzer mit einer Themenkarte oder einer Themenseite interagieren, werden möglicherweise unterschiedliche Ressourcen angezeigt. Dies liegt daran, dass sie Zugriff auf verschiedene Dateien haben, die dem Thema zugeordnet sind. Wenn Ihre zugrunde liegenden Berechtigungen zu streng sind, können die serendienswerten Aspekte der Informationssuche durch Themen verringert werden. Wenn sie jedoch zu breit sind, könnte ein Thema Inhalte für einen Benutzer anzeigen, die sie nicht sehen möchten.
Eine gute Berechtigungsverwaltung ist hier von entscheidender Bedeutung. Eine gute Berechtigungsverwaltung basiert auf einer kontinuierlichen Partnerschaft zwischen Administratoren und Inhaltsbesitzern. Obwohl dies eine fortlaufende Aktivität sein kann, gibt es einige praktische Schritte, die Sie bei der Vorbereitung auf Themen ausführen können:

- Ermuntern Sie Websitebesitzer, die Freigabe und Berechtigungen zu überprüfen.

  SharePoint Websitebesitzer einen Freigabebericht für ihre Website überprüfen können, in dem vollständige Details aller Berechtigungen und Freigabelinks angezeigt werden, die auf der Website konfiguriert sind, finden Sie unter ["Freigabeberichte".](/sharepoint/sharing-reports) Hier werden interne und externe Benutzer (Gastbenutzer) aufgelistet.

  Websitebesitzer können auch sehen, wer über Berechtigungen für die Website verfügt, indem sie zu den Seiten **"Websiteberechtigungen"** und **"Erweiterte Berechtigungen" Einstellungen** wechseln.

  1. Wählen Sie auf Ihrer Website **Einstellungen**  >  **Websiteberechtigungen aus.** Überprüfen Sie, wer unter Websitebesitzer, Websitemitglieder und Websitebesucher aufgeführt ist. Überprüfen Sie, ob Gastbenutzer vorhanden sind.
  2. Wählen Sie auf der Seite **Berechtigungen** **Erweiterte Berechtigungseinstellungen** aus. Sie können nach eindeutigen Berechtigungen suchen und sehen, wer eingeschränkten Zugriff auf beliebige Elemente in der Website hat.

- Überwachen Sie Microsoft 365-Gruppen und -Teams, um sicherzustellen, dass sie ordnungsgemäß als öffentliche oder private Gruppen oder Teams eingestellt sind. Neue Teams und Microsoft 365 Gruppen sind standardmäßig auf "Privat" festgelegt, aber bei der ersten Veröffentlichung waren sie standardmäßig öffentlich. Wenn Sie diese Technologien früher verwendet haben, sollten Sie dies überprüfen. Außerdem entwickelt sich die Funktion eines Teams im Laufe seines Lebenszyklus oft weiter, und die Einstellung muss möglicherweise aktualisiert werden, um die aktuelle Verwendung des Teams widerzuspiegeln.
- Überprüfen Sie die Verwendung von "jeder", "jeder außer externen Benutzern" oder allgemeinen Sicherheitsgruppen. Inhalte werden möglicherweise nicht ordnungsgemäß für diese Werte freigegeben. Um die Verwendung dieser Gruppen zu überprüfen, können Sie:
  - Erstellen eines Kontos ohne Gruppenmitgliedschaften
  - Die Suche mit diesem Konto verwenden, um allgemein freigegebene Inhalte zu finden.
  - Wenn unangemessene Inhalte für dieses Konto über die Suche sichtbar sind, können Sie mit den Websitebesitzern zusammenarbeiten, um die Berechtigungskonfiguration zu korrigieren.

Zusätzlich zu Berechtigungen können Sie auch den Umfang der Inhalte steuern, die in Themen auffindbar sind. Sie haben immer die Kontrolle darüber, was indiziert wird.

Administratoren können die Indizierung im Microsoft 365 Admin Center konfigurieren. Wenn Sie [Viva Topics](set-up-topic-experiences.md)einrichten, haben Sie folgende Möglichkeiten:

- Suche für alle SharePoint-Websites zulassen oder Websites angeben, die als Themaquellen ein- oder ausgeschlossen werden.
- Wenn Sie mit vertraulichen Begriffen arbeiten, können Sie Themen auch nach Name ausschließen. Wenn Sie beispielsweise den Namen eines vertraulichen Projekts haben, bei dem Sie nicht möchten, dass eine Hervorhebung oder eine Karte erscheint, unabhängig von den Rechten des Benutzers, können Sie diesen Projektnamen ausschließen.

Auf der Inhaltsebene können Sie auch steuern, was auffindbar ist. Alle Konfigurationen, die Sie vorgenommen haben, um Inhalte von der Suche auszuschließen, werden auch von der Inhaltsermittlung verwendet. Wenn Sie z. B. eine bestimmte Dokumentbibliothek aus den Suchergebnissen ausgeschlossen haben, wird diese Dokumentbibliothek nicht für die Themensuche verwendet.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. Ermitteln von Wissensmanagern und Themen

Die Verwaltung von Themen umfasst drei Schlüsselrollen, darunter zwei neue Azure Active Directory (AAD)-Rollen: Wissensadministrator und Wissensmanager:

- Der Wissensadministrator (Knowledge Administrator, KA) ist eine technische Rolle, in der Regel in der IT. Diese Rolle ermöglicht die Einrichtung von Viva Topics im M365 Admin Center sowie die Konfiguration der Themensuche und Sichtbarkeit.
- Der Wissensmanager (Knowledge Manager, KM) arbeitet mit den Themen selbst zusammen und überwacht deren Qualität und Vollständigkeit.
- Themenmitwirkende (TCs) basieren nicht auf einer AAD-Rolle, sondern auf Berechtigungen im Admin Center. Sie sind Fachexperten, die die Inhalte zu Themen zusammenstellen und Ressourcen und Personen hinzufügen können.

Je nach Organisation sind möglicherweise nur wenige oder viele Personen in diesen Rollen tätig. Für einige Organisationen sind dies möglicherweise die gleichen Personen.

| Wissensadministrator | Wissensmanager | Themenmitwirkender |
|:-------|:-------|:-------|:-------|
| AAD-Rolle | AAD-Rolle | Kmu |
| Hat Zugriff auf das Admin Center | Hat Zugriff auf das Admin Center | Kein Zugriff auf das Admin Center |
| Einrichten von Viva Topics | Besitzt die Verwaltung und Qualität von Themen | Trägt basierend auf ihrer Expertise zu Themen bei. |
| Stellt sicher, dass Sicherheits- und Compliancestandards durchgesetzt werden und die Lizenzvereinbarung verstanden wird.| Führt Themenverwaltungsaufgaben wie Erstellen, Bearbeiten, Löschen und Ablehnen von Themen aus. Unterstützt Themenmitwirkende bei ihren Aufgaben. | Curates the information and content on topic pages, including which people and resources are pinned to that topic. |

Hervorhebungen und Karten werden Benutzern im Kontext ihrer Arbeit angezeigt, z. B. beim Durchsuchen moderner Seiten in SharePoint. Sie steuern die Endbenutzererfahrung für Themen.

- Wer können Themen anzeigen? Die Sichtbarkeit von Themen ist im Microsoft 365 Admin Center konfiguriert. Wählen Sie aus, welche Gruppen Themen anzeigen dürfen:
  - Jeder in meiner Organisation. "Jeder" enthält keine Gäste, es handelt sich um alle internen Benutzer in Ihrem Verzeichnis.
  - Nur ausgewählte Personen oder Sicherheitsgruppen (diese Option ist gut, während Sie Viva Topics noch einführen, sodass Sie mit einer Teilmenge von Benutzern testen können). Wenn Gäste Themen anzeigen sollen, müssen Sie die Option "Ausgewählte Personen oder Sicherheitsgruppen" verwenden und ihnen eine Lizenz erteilen.
  - Mit niemandem.

    Alle Benutzer, auch Gastbenutzer, benötigen eine Lizenz, um die Themenoberfläche anzuzeigen. Denken Sie daran, dass Berechtigungen immer steuern, was angezeigt wird.

- Welche Themen sind sichtbar? Sie haben folgende Auswahlmöglichkeiten:
  - Alle Themen von Kandidaten anzeigen.
  - Nur bestätigte Themen anzeigen.

Da wir nun über die Vorgesetzten, Experten und Benutzer verfügen, können wir über die Themen selbst sprechen.

- Es empfiehlt sich, Themen in Ihre Themenliste aufzunehmen. Die Qualität und Menge der Themen basiert auf Ihren Inhalten – sie werden nur als Thema erstellt, wenn sie in den Inhalten enthalten sind, die im Bereich enthalten sind. Wenn genügend Informationen und Nachweise für das Thema vorhanden sind, wird es von der KI erstellt. Bei Seeding-Themen können der Wissensmanager und Fachexperten helfen. Die Kombination von menschlichem Wissen mit der KI ist der beste Weg für Qualitätsthemen. Wenn Es also Themen gibt, die Sie erwarten, können Sie diese manuell im Themencenter erstellen. Dadurch erhält die KI ein starkes Signal für die Relevanz dieses Themas und identifiziert Ressourcen und Personen, die diesem Thema zugeordnet werden sollen.
- Verwenden Sie vorhandene Taxonomien, um Ihre Themenplanung zu unterstützen, entweder von SharePoint oder von einem anderen Ort aus. Vorhandene Taxonomien umfassen häufig Organisationsbegriffe, Produkte, Themenbereiche usw. Quellen für Themen können auch aus Listen von Projekten, vorhandenen Suchlesezeichen usw. stammen.