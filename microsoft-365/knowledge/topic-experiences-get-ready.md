---
title: Bereiten Sie Ihre Umgebung für Microsoft Viva-Themen vor
description: Machen Sie Ihre Umgebung bereit, damit Sie mit Microsoft Viva Topics so viele Inhalte wie möglich für Ihre Benutzer bereitstellen können.
ms.author: samanro
author: samanro
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 2db8654bf7bb1bc5ef4759c1617a84ae2153553a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917392"
---
# <a name="get-your-environment-ready-for-microsoft-viva-topics"></a>Bereiten Sie Ihre Umgebung für Microsoft Viva-Themen vor

Damit Sie die Inhalte von "Viva Topics" so gut wie möglich nutzen können, sollten Sie so viele Inhalte wie möglich für die Themenerkennung enthalten, damit Sie über eine reihe von Themen für Ihre Benutzer verfügen können. Welche Inhalte sollten jedoch für die Themenerkennung verwendet werden? Wie maximieren Sie den indizierten Inhalt, während Sie die Kontrolle erhalten? Die Erkenntnisse der künstlichen Intelligenz sind besser, um so mehr Inhalte im Umfang enthalten sind. Dieser Artikel führt Sie durch Planungsschritte, um sicherzustellen, dass Sie die entsprechenden Inhalte enthalten und dass Sie über die richtigen Personen und Ressourcen verfügen, um eine gute Benutzererfahrung zu ermöglichen.

Zum Planen von Themen von "Viva" müssen Sie:

![Migrieren, Verbinden, Modernisieren, Sichern und Identifizieren von Schritten für das Onboarding in die Wissensverwaltung](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Migrieren von Inhalten zu SharePoint](#1-migrate-content-to-microsoft-365)
    - Die Themenindizierung umfasst nur Inhalte auf SharePoint Websites.
      - Migrieren Sie nach Möglichkeit wertvolle Inhalte aus externen SharePoint online.
      - Priorisieren sie Inhaltsquellen mit hohem Potenzial für stillschweigendes Wissen.
      - Heben Sie die Vorteile des Wissensmanagements auf, um Benutzer zum Verschieben von Inhalten von OneDrive auf SharePoint zu ermutigen.

2. [Verbinden Informationen an Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - In Zukunft können externe Inhalte in das Wissensdiagramm ein- und verfügbar werden.
    - Bei Inhalten, die nicht verschoben werden können, sollten Sie Graph Connectors verwenden, um die Suche zu verbessern und sich auf die zukünftige Inklusion vorzubereiten.

3. [Modernisieren SharePoint Seiten](#3-modernize-sharepoint-pages)
    - Themenkarten können nur auf modernen Seiten angezeigt werden.
    - Identifizieren Sie hochrangige klassische Seiten, bei der es sich um Modernisierungskandidaten handelt.

4. [Angemessenes Sichern von Inhalten](#4-secure-content-appropriately)
    - Themenressourcen werden basierend auf den Berechtigungen eines Benutzers sicherheitsbeschnitten.
    - Identifizieren Von Inhalten, die möglicherweise fälschlicherweise über umfassende oder restriktive Berechtigungen verfügen:
      - Ermutigen von Websitebesitzern, die Freigabeberichte zum Überprüfen von Berechtigungen zu verwenden
      - Verwalten von allgemein freigegebenen Inhalten durch Administratoren mithilfe der Suche
      - Ermutigen Sie Die Besitzer von Inhalten, Inhalte zu teilen, die nicht vertraulich sind und möglicherweise einen größeren Nutzen für die Organisation haben.
    - Überprüfen Sie Ihre Microsoft Graph für Benutzer und Inhalte:
      - Bei der Themenindizierung wird die Konfiguration berücksichtigt, die Inhalte aus der Suche oder Delve (z. B. NOINDEX) aus. Überprüfen Sie, ob diese Konfigurationen noch relevant sind.

5. [Identifizieren von Wissensmanagern und Themen](#5-identify-knowledge-managers-and-topics)
    - Verwenden Sie vorhandene Taxonomien, um Manuell Themen zu erstellen, oder helfen Sie bei der Bestätigung von AI-vorgeschlagenen Themen.
    - Identifizieren von Experten für Themen (SMEs) für erwartete oder seeded-Themen.
    - Identifizieren Sie Websites, die eine große Menge wertvoller Daten abdecken, die zum Pilotthema Mining verwendet werden können.
    - Engagieren Sie Wissensmanager und Communitys der Praxis.

## <a name="1-migrate-content-to-microsoft-365"></a>1. Migrieren von Inhalten zu Microsoft 365

Es gibt mehrere Tools und Dienste, die Ihnen bei der Migration [helfen:](/sharepointmigration/migrate-to-sharepoint-online)Sie erhalten eine Übersicht und Informationen zur Migration unter Migrate your content to Microsoft 365 . Zu den Migrationstools gehören:

- [Migrations-Manager](/sharepointmigration/mm-get-started)
- [SharePoint-Migrationstool (SPMT)](/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Tools und Dienste für die Partnermigration](https://www.microsoft.com/solution-providers)

Nutzen Sie Ihre Migration:

- Migrieren Sie zu einer modernen Website, die Microsoft Teams. Während die Indizierung auf jeder SharePoint-Website (klassisch oder modern) erfolgen kann, erfolgt die Anzeige von Themen für Benutzer durch Hervorhebungen und Karten nur auf modernen Seiten.
- Verwalten von Benutzernamen – mit den meisten Migrationstools können Sie Benutzeridentitäten innerhalb der Migration zuordnungen, sodass Eigenschaften wie Created By oder Modified By nach der Migration beibehalten werden. Dies ist wichtig für Themen, da die Erstellung von Dateien verwendet wird, um die Experten zu identifizieren, die einer Themenseite oder -karte hinzugefügt werden. 
- Beschreiben von Dienstkontonamen – Es gibt einige Fälle, in denen die Verwaltung von Benutzernamen nicht möglich ist. Wenn Sie beispielsweise Inhalte migrieren, die von einer Person erstellt wurden, die kein Mitarbeiter der Organisation mehr ist. In diesem Fall verschieben die meisten Migrationstools eine Datei so, als ob sie von einem Administratorkonto oder einem Dienstkonto erstellt worden wäre. Wenn dies häufig der Fall ist, könnte dieses Dienstkonto dann für Themen als Experte aufgelistet werden. Hier wird die Benennung dieses Kontos wirklich wichtig. Wenn Sie es beschreiben, ist das Vorhandensein dieser nicht menschlichen Konten für Ihre Benutzer verständlich, die Themen verwenden.

## <a name="2-connect-information-to-microsoft-graph"></a>2. Verbinden Informationen an Microsoft Graph

Wenn Sie einige Inhalte nicht migrieren können, verbinden Sie sie mit der Microsoft-Graph:

- Erwägen Sie die [Implementierung Graph Inhaltsconnectors](/microsoftsearch/connectors-overview). Mithilfe von Connectors können externe Inhalte in die Microsoft-Graph indiziert werden, wo Benutzer sie dann über Microsoft Search ermitteln können.
- Zukünftige Entwicklungen werden externe Daten in "Viva Topics" bringen.

## <a name="3-modernize-sharepoint-pages"></a>3. Modernisieren SharePoint Seiten

Da Themenkarten und Highlights nur auf modernen Seiten angezeigt werden können, aktualisieren Sie alle Seiten, die Sie in "Viva Topics" enthalten möchten, von klassisch bis modern. Weitere [Informationen finden Sie unter Modernize your classic SharePoint sites](/sharepoint/dev/transform/modernize-classic-sites). Sie können den Scanner SharePoint [Modernisierung verwenden,](/sharepoint/dev/transform/modernize-scanner) um Ihre klassischen Websites auf die Modernisierung vorzubereiten.

Wenn Sie über viele klassische Websites verfügen, sollten Sie Seiten mit hohem Informationsgehalt priorisieren, um sie auf modern zu konvertieren.

## <a name="4-secure-content-appropriately"></a>4. Entsprechendes Sichern von Inhalten

Wenn Benutzer mit einer Themenkarte oder einer Themenseite interagieren, werden möglicherweise unterschiedliche Ressourcen angezeigt. Dies liegt daran, dass sie Zugriff auf verschiedene Dateien haben, die dem Thema zugeordnet sind. Wenn Ihre zugrunde liegenden Berechtigungen zu streng sind, könnten die serendipitous Aspekte der Informationserkennung durch Themen verringert werden. Wenn sie andererseits zu breit sind, könnte ein Thema inhalt für einen Benutzer angezeigt werden, den Sie nicht sehen möchten.
Eine gute Berechtigungsverwaltung ist hier von entscheidender Bedeutung. Und eine gute Berechtigungsverwaltung basiert auf einer fortlaufenden Partnerschaft zwischen Administratoren und Inhaltsbesitzern. Dies kann zwar eine laufende Aktivität sein, es gibt jedoch einige praktische Schritte, die Sie bei der Vorbereitung auf Themen ausführen können:

- Ermuntern Sie Websitebesitzer, die Freigabe und Berechtigungen zu überprüfen.

  SharePoint Websitebesitzer können einen Freigabebericht für ihre Website überprüfen, der vollständige Details aller auf der Website konfigurierten Berechtigungen und Freigabelinks enthält, siehe [Freigabeberichte](/sharepoint/sharing-reports). Hier werden interne und externe Benutzer (Gastbenutzer) aufgeführt.

  Websitebesitzer können auch sehen, wer über Berechtigungen  für die Website verfügt, indem sie zu den Seiten Websiteberechtigungen **und erweiterte Berechtigungen Einstellungen** gehen.

  1. Wählen Sie auf Ihrer Website **Einstellungen**  >  **Websiteberechtigungen aus.** Überprüfen Sie, wer unter Websitebesitzer, Websitemitglieder und Websitebesucher aufgeführt ist. Überprüfen Sie, ob Gastbenutzer vorhanden sind.
  2. Wählen Sie auf der Seite **Berechtigungen** **Erweiterte Berechtigungseinstellungen** aus. Sie können nach eindeutigen Berechtigungen suchen und sehen, wer eingeschränkten Zugriff auf beliebige Elemente in der Website hat.

- Überwachen Sie Microsoft 365-Gruppen und -Teams, um sicherzustellen, dass sie ordnungsgemäß als öffentliche oder private Gruppen oder Teams eingestellt sind. Neue Teams und Microsoft 365 Gruppen sind standardmäßig auf privat festgelegt, aber bei der ersten Öffentlichen Öffentlichen Version. Wenn Sie zuvor diese Technologien verwendet haben, sollten Sie dies überprüfen. Außerdem entwickelt sich die Funktion eines Teams im Laufe seines Lebenszyklus oft weiter, und die Einstellung muss möglicherweise aktualisiert werden, um die aktuelle Verwendung des Teams widerzuspiegeln.
- Überprüfen Sie die Verwendung von "jeder", "jeder außer externen Benutzern" oder breiten Sicherheitsgruppen. Inhalte werden möglicherweise nicht ordnungsgemäß für diese Werte freigegeben. Um die Verwendung dieser Gruppen zu überprüfen, können Sie:
  - Erstellen eines Kontos ohne Gruppenmitgliedschaften
  - Die Suche mit diesem Konto verwenden, um allgemein freigegebene Inhalte zu finden.
  - Wenn für dieses Konto unangemessene Inhalte über die Suche sichtbar sind, können Sie mit den Websitebesitzern zusammenarbeiten, um die Berechtigungskonfiguration zu korrigieren.

Zusätzlich zu Berechtigungen können Sie auch den Umfang der Informationen steuern, die in Themen zu finden sind. Sie haben immer die Kontrolle darüber, was indiziert ist.

Administratoren können die Indizierung im Microsoft 365 konfigurieren. Wenn Sie Wissensverwaltung [einrichten,](set-up-topic-experiences.md)können Sie:

- Suche für alle SharePoint-Websites zulassen oder Websites angeben, die als Themaquellen ein- oder ausgeschlossen werden.
- Wenn Sie mit vertraulichen Begriffen arbeiten, können Sie Themen auch nach Name ausschließen. Wenn Sie beispielsweise den Namen eines vertraulichen Projekts haben, bei dem Sie nicht möchten, dass eine Hervorhebung oder eine Karte erscheint, unabhängig von den Rechten des Benutzers, können Sie diesen Projektnamen ausschließen.

Auf der Inhaltsebene können Sie auch steuern, was auf der Ebene des Erkennens zu finden ist. Alle Konfigurationen, die Sie zum Ausschließen von Inhalten aus der Suche durchgeführt haben, werden auch von der Inhaltsermittlung verwendet. Wenn Sie beispielsweise ausgeschlossen haben, dass eine bestimmte Dokumentbibliothek in Suchergebnissen angezeigt wird, wird diese Dokumentbibliothek nicht für die Themenermittlung verwendet.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. Identifizieren von Wissensmanagern und Themen

Die Verwaltung von Themen umfasst drei Schlüsselrollen, darunter zwei neue Azure Active Directory (AAD)-Rollen: Wissensadministrator und Knowledge Manager:

- Der Knowledge Administrator (KA) ist eine technische Rolle, in der Regel in der IT. Diese Rolle ermöglicht das Einrichten der Themen von "Viva" im M365 Admin Center sowie die Konfiguration der Themenerkennung und -sichtbarkeit.
- Der Knowledge Manager (KM) arbeitet mit den Themen selbst zusammen und überwacht deren Qualität und Vollständigkeit.
- Mitwirkende für Themen (TCs) basieren nicht auf einer AAD-Rolle, sondern auf Berechtigungen im Admin Center. Sie sind Experten, die inhalte zu Themen kuratieren und Ressourcen und Personen hinzufügen können.

Je nach Organisation sind in diesen Rollen möglicherweise nur wenige oder viele Personen tätig. Für einige Organisationen sind dies möglicherweise dieselben Personen.

| Wissensadministrator | Wissensmanager | Themenmitwirkender |
|:-------|:-------|:-------|:-------|
| AAD-Rolle | AAD-Rolle | SME |
| Zugriff auf das Admin Center | Zugriff auf das Admin Center | Kein Zugriff auf das Admin Center |
| Einrichten von Themen zu "Viva" | Eigene Verwaltung und Qualität von Themen | Trägt basierend auf ihrem Fachwissen zu Themen bei. |
| Stellt sicher, dass Sicherheits- und Compliancestandards durchgesetzt werden und die Lizenzierungsvereinbarung verstanden wird.| Führt Aufgaben zur Themenverwaltung aus, z. B. Erstellen, Bearbeiten, Löschen und Ablehnen von Themen. Unterstützt Topic-Mitwirkende bei ihren Aufgaben. | Curates the information and content on topic pages, including which people and resources are pinned to that topic. |

Momente und Karten werden Benutzern im Kontext ihrer Arbeit angezeigt, z. B. wenn sie moderne Seiten in SharePoint. Sie steuern die Endbenutzererfahrung für Themen.

- Wer können Themen sehen? Die Thementransparenz ist im Microsoft 365 Admin Center konfiguriert. Wählen Sie aus, welche Gruppen sie zum Sehen von Themen zulassen:
  - Jeder in meiner Organisation. "Jeder" enthält keine Gäste, sondern alle internen Benutzer in Ihrem Verzeichnis.
  - Nur Ausgewählte Personen oder Sicherheitsgruppen (diese Option ist gut, während Sie noch "Viva Topics" ausrollen, sodass Sie mit einer Teilmenge von Benutzern testen können). Wenn Gäste Themen anzeigen möchten, müssen Sie die Option "Ausgewählte Personen oder Sicherheitsgruppen" verwenden und ihnen eine Lizenz erteilen.
  - Mit niemandem.

    Alle Benutzer, auch Gastbenutzer, müssen über eine Lizenz verfügen, um die Themenerfahrung anzeigen zu können. Und denken Sie daran, dass Berechtigungen immer steuern, was zu sehen ist.

- Welche Themen sind sichtbar? Sie haben folgende Auswahlmöglichkeiten:
  - Alle Themen von Kandidaten anzeigen.
  - Nur bestätigte Themen anzeigen.

Jetzt, da wir die Manager, Experten und Benutzer haben, können wir über die Themen selbst sprechen.

- Es ist eine bewährte Methode, Themen in Ihre Themenliste zu seeden. Die Qualität und Quantität der Themen basiert auf Ihren Inhalten – sie werden nur als Thema erstellt, wenn sie in den Inhalt aufgenommen werden, der sich im Bereich befindet. Wenn genügend Informationen und Nachweise für das Thema vorhanden sind, wird es von der AI erstellt. Bei Seedingthemen können der Knowledge Manager und Experten für Themen hilfreich sein. Die Kombination von menschlichem Wissen mit der KI ist der beste Weg für Qualitätsthemen. Wenn es also Themen gibt, die Sie erwarten, können Sie diese manuell im Themencenter erstellen. Dies gibt der KI ein starkes Signal für die Relevanz dieses Themas und identifiziert Ressourcen und Personen, die diesem Thema zugeordnet werden sollen.
- Verwenden Sie vorhandene Taxonomien, um Ihre Themenplanung zu unterstützen, entweder von SharePoint oder an anderer Stelle. Vorhandene Taxonomien umfassen häufig organisatorische Begriffe, Produkte, Betreffbereiche und so weiter. Quellen für Themen können auch aus Listen von Projekten, vorhandenen Suchmarken und so weiter stammen.