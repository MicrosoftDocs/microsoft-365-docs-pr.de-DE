---
title: Bereiten Sie Ihre Umgebung für Microsoft -Themen vor
description: Bereiten Sie Ihre Umgebung vor, damit Sie ihren Benutzern mit Microsoft Topics so viele Inhalte wie möglich zur Verfügung stellen können.
ms.author: samanro
author: samanro
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 5a13af3e78848471b436d44ab051eca945176c74
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107696"
---
# <a name="get-your-environment-ready-for-microsoft-viva-topics"></a>Bereiten Sie Ihre Umgebung für Microsoft -Themen vor

Um Dies zu erreichen, sollten Sie so viel Inhalt wie möglich für die Themenermittlung zur Verfügung haben, damit Sie eine umfangreiche Reihe von Themen für Ihre Benutzer haben können. Aber welche Inhalte sollten für die Themenermittlung verwendet werden? Wie maximieren Sie den indizierten Inhalt, während Sie die Kontrolle erhalten? Wenn sich mehr Inhalte im Umfang befindet, desto besser sind die Erkenntnisse, die die künstliche Intelligenz entdecken kann. Dieser Artikel führt Sie durch die Planungsschritte, um sicherzustellen, dass Sie die entsprechenden Inhalte enthalten und über die richtigen Personen und Ressourcen verfügen, um ihren Benutzern eine gute Erfahrung zu bieten.

Um Themen zu planen, müssen Sie:

![Migrieren, Verbinden, Modernisieren, Sichern und Identifizieren von Schritten für das Onboarding in die Wissensverwaltung](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Migrieren von Inhalten zu SharePoint](#1-migrate-content-to-microsoft-365)
    - Die Themenindizierung umfasst nur Inhalte auf SharePoint-Websites.
      - Migrieren Sie nach Möglichkeit wertvolle Inhalte aus externen Quellen zu SharePoint Online.
      - Priorisieren Sie Inhaltsquellen mit hohem Potenzial für implizites Wissen.
      - Hervorheben der Vorteile des Wissensmanagements, um Benutzer zum Verschieben von Inhalten von OneDrive auf #A0 zu ermutigen.

2. [Verbinden von Informationen mit Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - In Zukunft können externe Inhalte in das Wissensdiagramm gebracht und verfügbar werden.
    - Für Inhalte, die nicht verschoben werden können, erwägen Sie die Verwendung von Graph Connectors, um die Suche zu verbessern und sich auf die zukünftige Einbindung vorzubereiten.

3. [Modernisieren von SharePoint-Seiten](#3-modernize-sharepoint-pages)
    - Themenkarten können nur auf modernen Seiten angezeigt werden.
    - Identifizieren Sie profilige klassische Seiten, die Modernisierungskandidaten sind.

4. [Angemessenes Sichern von Inhalten](#4-secure-content-appropriately)
    - Themenressourcen werden basierend auf den Berechtigungen eines Benutzers aus Sicherheitsgründen gekürzt.
    - Identifizieren Sie alle Inhalte, die möglicherweise fälschlicherweise über umfassende oder restriktive Berechtigungen verfügen:
      - Ermutigen von Websitebesitzern, die Freigabeberichte zum Überprüfen von Berechtigungen zu verwenden
      - Administratoren müssen allgemein freigegebene Inhalte mithilfe der Suche überwachen
      - Ermutigen Sie Die Besitzer von Inhalten, Inhalte zu teilen, die nicht vertraulich sind und möglicherweise einen größeren Vorteil für die Organisation haben.
    - Überprüfen Sie Ihre Microsoft Graph-Konfiguration für Benutzer und Inhalte:
      - Bei der Themenindizierung wird die Konfiguration berücksichtigt, bei der Inhalte aus Der Suche oder Delve ausgeschlossen werden (z. B. NOINDEX). Überprüfen Sie, ob diese Konfigurationen noch relevant sind.

5. [Ermitteln von Wissensmanagern und Themen](#5-identify-knowledge-managers-and-topics)
    - Verwenden Sie vorhandene Taxonomien zum manuellen Erstellen von Themen oder zur Bestätigung von themen vorgeschlagenen AI-Themen.
    - Identifizieren von Experten für Themen, die im Voraus geplant oder im Seeding bzw. im Seeding enthalten sind.
    - Identifizieren Sie Websites, die eine große Menge wertvoller Daten abdecken, die zum Pilotthemamining verwendet werden können.
    - Sie können Wissensmanager und Praxisgemeinschaften an sich beteiligen.

## <a name="1-migrate-content-to-microsoft-365"></a>1. Migrieren von Inhalten zu Microsoft 365

Es gibt verschiedene Tools und Dienste, die Ihnen bei der Migration helfen. Unter "Migrieren Ihrer Inhalte zu [Microsoft 365"](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)erhalten Sie eine Übersicht und Informationen zur Migration. Migrationstools umfassen:

- [Migrations-Manager](https://docs.microsoft.com/sharepointmigration/mm-get-started)
- [SharePoint-Migrationstool (SPMT)](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Partnermigrationstools und -dienste](https://www.microsoft.com/solution-providers)

Nutzen Sie Die Migration so gut wie immer:

- Migrieren Sie zu einer modernen Website, die Microsoft Teams umfasst. Während die Indizierung auf jeder beliebigen SharePoint-Website (klassisch oder modern) möglich ist, erfolgt die Anzeige von Themen für Benutzer über Highlights und Karten nur auf modernen Seiten.
- Verwalten von Benutzernamen – mit den meisten Migrationstools können Sie Benutzeridentitäten innerhalb der Migration zuordnungen, sodass Eigenschaften wie "Erstellt von" oder "Geändert von" nach der Migration beibehalten werden. Dies ist wichtig für Themen, da die Erstellung von Dateien verwendet wird, um die Experten zu identifizieren, die einer Themenseite oder -karte hinzugefügt werden. 
- Beschreiben von Dienstkontonamen– In einigen Fällen ist die Verwaltung von Benutzernamen nicht möglich. Wenn Sie beispielsweise Inhalte migrieren, die von einer Person erstellt wurden, die kein Mitarbeiter der Organisation mehr ist. In diesem Fall verschieben die meisten Migrationstools eine Datei so, als ob sie von einem Administrator- oder Dienstkonto erstellt worden wäre. Wenn dies häufig der Fall ist, könnte dieses Dienstkonto für Themen als Experte aufgeführt werden. Hier wird die Benennung dieses Kontos wirklich wichtig. Wenn Sie es beschreiben, ist das Vorhandensein dieser nicht menschlichen Konten für Ihre Benutzer verständlich, die Themen verwenden.

## <a name="2-connect-information-to-microsoft-graph"></a>2. Verbinden von Informationen mit Microsoft Graph

Wenn Sie inhalte nicht migrieren können, verbinden Sie sie mit Microsoft Graph:

- Erwägen Sie die Implementierung [von Graph Content Connectors.](https://docs.microsoft.com/microsoftsearch/connectors-overview) Mithilfe von Connectors können externe Inhalte in Microsoft Graph indiziert werden, wo Benutzer sie dann über Microsoft Search ermitteln können.
- Künftige Entwicklungen werden externe Daten in Themen zu Themen bringen.

## <a name="3-modernize-sharepoint-pages"></a>3. Modernisieren von SharePoint-Seiten

Da Themenkarten und -highlights nur auf modernen Seiten angezeigt werden können, aktualisieren Sie alle Seiten, die Sie in thementhemen von klassisch zu modern hinzufügen möchten. Weitere [Informationen finden Sie unter Modernisieren Ihrer klassischen SharePoint-Websites.](https://docs.microsoft.com/sharepoint/dev/transform/modernize-classic-sites) Sie können den [SharePoint-Modernisierungsscanner](https://docs.microsoft.com/sharepoint/dev/transform/modernize-scanner) verwenden, um Ihre klassischen Websites für die Modernisierung vorzubereiten.

Wenn Sie über viele klassische Websites verfügen, priorisieren Sie Profilseiten, um sie in moderne Websites zu konvertieren.

## <a name="4-secure-content-appropriately"></a>4. Geeignetes Sichern von Inhalten

Wenn Benutzer mit einer Themenkarte oder einer Themenseite interagieren, werden ihnen möglicherweise unterschiedliche Ressourcen angezeigt. Dies liegt daran, dass sie Zugriff auf verschiedene Dateien haben, die dem Thema zugeordnet sind. Wenn Ihre zugrunde liegenden Berechtigungen zu streng sind, könnten die serendipitous Aspekte der Informationsermittlung über Themen eingeschränkt werden. Wenn sie dagegen zu breit sind, könnte ein Thema Inhalte für einen Benutzer anzeigen, den sie nicht sehen möchten.
Eine gute Berechtigungsverwaltung ist hier von entscheidender Bedeutung. Und eine gute Berechtigungsverwaltung basiert auf einer kontinuierlichen Partnerschaft zwischen Administratoren und Inhaltsbesitzern. Dies kann zwar eine laufende Aktivität sein, es gibt jedoch einige praktische Schritte, die Sie bei der Vorbereitung auf Themen ausführen können:

- Ermutigen Sie Websitebesitzer, Freigabe und Berechtigungen zu überprüfen.

  Besitzer von SharePoint-Websites können einen Freigabebericht für ihre Website überprüfen, der vollständige Details zu allen Berechtigungen und Freigabelinks enthält, die auf der Website konfiguriert sind. Weitere Informationen finden Sie unter ["Freigabeberichte".](https://docs.microsoft.com/sharepoint/sharing-reports) Hier werden interne und externe Benutzer (Gastbenutzer) aufgeführt.

  Websitebesitzer können auch sehen, wer über Berechtigungen für die Website verfügt, indem sie die Seiten mit den Einstellungen für Websiteberechtigungen und **erweiterte** **Berechtigungen** besuchen.

  1. Wählen Sie auf Ihrer Website die **Berechtigungen**  >  **"Einstellungswebsite" aus.** Überprüfen Sie, wer unter Websitebesitzer, Websitemitglieder und Websitebesucher aufgeführt ist. Suchen Sie nach Gastbenutzern.
  2. Wählen Sie **auf der Seite** "Berechtigungen" die Option **"Erweiterte Berechtigungseinstellungen" aus.** Sie können nach eindeutigen Berechtigungen suchen und sehen, wer eingeschränkten Zugriff auf Elemente auf der Website hat.

- Überwachen Sie Microsoft 365-Gruppen und -Teams, um sicherzustellen, dass sie entsprechend als öffentliche oder private Gruppen oder Teams festgelegt sind. Neue Teams und Microsoft 365-Gruppen sind standardmäßig auf "Privat" festgelegt, wurden jedoch bei der ersten Öffentlichen Version standardmäßig veröffentlicht. Wenn Sie diese Technologien bereits verwendet haben, sollten Sie dies überprüfen. Außerdem wird die Funktion eines Teams im Laufe seines Lebenszyklus häufig weiterentwickelt, und die Einstellung muss möglicherweise aktualisiert werden, um die aktuelle Verwendung des Teams widerspiegeln zu können.
- Überprüfen Sie die Verwendung von "jeder", "jeder außer externen Benutzern" oder breiten Sicherheitsgruppen. Inhalte werden möglicherweise fälschlicherweise für diese Werte freigegeben. Um die Verwendung dieser Gruppen zu überprüfen, können Sie:
  - Erstellen eines Kontos ohne Gruppenmitgliedschaften
  - Verwenden Sie die Suche mit diesem Konto, um Inhalte zu ermitteln, die allgemein freigegeben sind.
  - Wenn unangemessene Inhalte für dieses Konto durch die Suche sichtbar sind, können Sie mit den Websitebesitzern zusammenarbeiten, um die Berechtigungskonfiguration zu korrigieren.

Zusätzlich zu Berechtigungen können Sie auch den Bereich steuern, was in Themen zu finden ist. Sie haben immer die Kontrolle darüber, was indiziert wird.

Administratoren können die Indizierung im Microsoft 365 Admin Center konfigurieren. Beim Einrichten von [Knowledge Management](set-up-topic-experiences.md)können Sie:

- Ermöglichen Sie die Suche auf allen SharePoint-Websites, oder geben Sie Websites an, die als Themenquellen ein- oder ausgeschlossen werden.
- Wenn Sie über vertrauliche Begriffe verfügen, können Sie Auch Themen nach Namen ausschließen. Wenn Sie beispielsweise den Namen eines vertraulichen Projekts haben, bei dem unabhängig von den Berechtigungen des Benutzers keine Hervorhebung oder Karte angezeigt werden soll, können Sie diesen Projektnamen ausschließen.

Auf der Inhaltsebene können Sie auch steuern, was auf der Anderen zu finden ist. Alle Konfigurationen, die Sie zum Ausschließen von Inhalten aus der Suche durchgeführt haben, werden auch von der Inhaltsermittlung verwendet. Wenn Sie beispielsweise eine bestimmte Dokumentbibliothek aus der Suche ausgeschlossen haben, wird diese Dokumentbibliothek nicht für die Themenermittlung verwendet.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. Identifizieren von Wissensmanagern und Themen

Das Verwalten von Themen umfasst drei Schlüsselrollen, darunter zwei neue Azure Active Directory (AAD)-Rollen: Knowledge Administrator und Knowledge Manager:

- Der Knowledge Administrator (KA) ist eine technische Rolle, in der Regel in der IT. Diese Rolle ermöglicht das Einrichten der Themen im M365 Admin Center sowie die Konfiguration der Themenermittlung und Sichtbarkeit.
- Der Knowledge Manager (KM) arbeitet mit den Themen selbst zusammen und überwacht deren Qualität und Vollständigkeit.
- Mitwirkende von Themen (TCs) basieren nicht auf einer AAD-Rolle, sondern auf Berechtigungen im Admin Center. Sie sind Experten, die in der Lage sind, die Inhalte zu Themen zu krümmen und Ressourcen und Personen zu hinzufügen.

Je nach Organisation sind möglicherweise nur wenige oder viele Personen in diesen Rollen tätig. Für einige Organisationen sind dies möglicherweise die gleichen Personen.

| Wissensadministrator | Knowledge Manager | Mitwirkender des Themas |
|:-------|:-------|:-------|:-------|
| Rolle "AAD" | Rolle "AAD" | MITTELSTAND |
| Hat Zugriff auf das Admin Center | Hat Zugriff auf das Admin Center | Kein Zugriff auf das Admin Center |
| Einrichten von "Themen" | Eigene Verwaltung und Qualität von Themen | Trägt basierend auf ihrem Fachwissen zu Themen bei. |
| Stellt sicher, dass Sicherheits- und Compliancestandards durchgesetzt werden, und versteht den Lizenzvertrag.| Führt Aufgaben zur Themenverwaltung aus, z. B. Erstellen, Bearbeiten, Löschen und Ablehnen von Themen. Unterstützt Mitwirkende von Themen mit ihren Aufgaben. | Enthält Informationen und Inhalte auf Themenseiten, einschließlich der Personen und Ressourcen, die an dieses Thema angeheftet sind. |

Highlights und Karten werden Benutzern im Kontext ihrer Arbeit angezeigt, z. B. wenn sie moderne Seiten in SharePoint durchsuchen. Sie steuern die Endbenutzererfahrung für Themen.

- Wer kann Themen sehen? Die Sichtbarkeit von Themen wird im Microsoft 365 Admin Center konfiguriert. Wählen Sie aus, welche Gruppen Themen sehen können:
  - Jeder in meiner Organisation. "Jeder" enthält keine Gäste, sondern alle internen Benutzer in Ihrem Verzeichnis.
  - Nur ausgewählte Personen oder Sicherheitsgruppen (diese Option ist gut, während Sie noch themenbereichsroll out sind, sodass Sie mit einer Teilmenge von Benutzern testen können). Wenn Sie möchten, dass Gäste Themen anzeigen, müssen Sie die Option "Ausgewählte Personen oder Sicherheitsgruppen" verwenden und ihnen eine Lizenz erteilen.
  - Mit niemandem.

    Alle Benutzer, auch Gastbenutzer, müssen über eine Lizenz verfügen, um die Themenerfahrung anzeigen zu können. Und denken Sie daran, dass Berechtigungen immer steuern, was zu sehen ist.

- Welche Themen sind sichtbar? Sie haben die Wahl zwischen:
  - Alle Kandidatenthemen anzeigen.
  - Nur bestätigte Themen anzeigen.

Nun, da wir die Manager, Experten und Benutzer haben, können wir über die Themen selbst sprechen.

- Es ist eine bewährte Methode, Themen in Ihre Themenliste zu seeden. Qualität und Menge der Themen basieren auf Ihren Inhalten. Sie werden nur als Thema erstellt, wenn sie in den Inhalt einbezogen werden, der sich im Bereich befindet. Wenn ausreichend Informationen und Nachweise für das Thema vorhanden sind, wird es von der KI erstellt. In Den Themen zum Seeding können der Knowledge Manager und Fachexperten hilfreich sein. Die Kombination von menschlichem Wissen mit ki ist die beste Route für Qualitätsthemen. Wenn Es also Themen gibt, die Sie erwarten, können Sie diese manuell im Themencenter erstellen. Dies gibt der KI ein starkes Signal für die Relevanz dieses Themas und identifiziert Ressourcen und Personen, die diesem Thema zugeordnet werden sollen.
- Verwenden Sie vorhandene Taxonomien, um Ihre Themenplanung zu unterstützen, entweder aus SharePoint oder an anderer Stelle. Zu den vorhandenen Taxonomien gehören häufig Organisatorische Begriffe, Produkte, Themenbereiche und so weiter. Quellen für Themen können auch aus Listen von Projekten, vorhandenen Suchlesezeichen und so weiter stammen.
