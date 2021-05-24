---
title: Manage topics at scale in Microsoft Viva Topics
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: lauriellis
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Erfahren Sie mehr über bewährte Methoden zum Verwalten der vielen Themen in Ihrer Organisation mithilfe von "Viva Topics".
ms.openlocfilehash: 613c4ed85a62efd22ba104c810420a2d0af015c5
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624837"
---
# <a name="manage-topics-at-scale-in-microsoft-viva-topics"></a>Manage topics at scale in Microsoft Viva Topics

Wenn Sie Ihre SharePoint oder Ihre gesamte Organisation für "Viva Topics" indizieren, werden möglicherweise viele Themen generiert. Wenn dies geschieht und Tausende von  vorgeschlagenen Themen auf der Seite Themen verwalten angezeigt werden, kann es schwierig sein, zu wissen, wo sie beginnen sollen. In diesem Artikel wird beschrieben, wie Sie mit Themen von "Viva" optimieren können, welche Themen und Informationen Benutzern angezeigt werden, die nach Informationen suchen, auch in großen Organisationen mit einer großen Anzahl von Themen.

Zunächst eine Erinnerung an die [vier Phasen für Themen:](manage-topics.md#topic-stages)

- **Vorgeschlagen**: Ein Thema wurde von KI identifiziert und verfügt über genügend unterstützende Ressourcen, Verbindungen und Eigenschaften. (Diese werden in der Benutzeroberfläche **als vorgeschlagenes** Thema gekennzeichnet.)

- **Bestätigt**: Ein Thema, das von AI erkannt und überprüft wurde. Die Themenüberprüfung erfolgt, wenn eine der beiden:

   - Ein Knowledge Manager bestätigt ein Thema. Ein Knowledge Manager [bestätigt ein Thema auf](manage-topics.md#confirmed-topics) der Seite Themen **verwalten.**

   - Mehrere Benutzer bestätigen ein Thema. Es muss ein Netz von zwei positiven Stimmen von Benutzern sein, die mit dem Feedbackmechanismus auf der Themenkarte abgestimmt haben. Wenn beispielsweise ein Benutzer für ein bestimmtes Thema positiv und ein Benutzer für ein bestimmtes Thema negativ stimmte, benötigen Sie noch zwei weitere positive Stimmen, damit das Thema bestätigt wird.
 
- **Veröffentlicht**: Ein Thema, das kuratiert wurde. Manuelle Bearbeitungen wurden vorgenommen, um die Qualität zu verbessern, oder sie wurden von einem Benutzer erstellt.

- **Entfernt:** Ein Thema, das abgelehnt wurde und für die Betrachter nicht mehr sichtbar ist. Ein Thema kann in einem beliebigen Zustand entfernt werden (vorgeschlagen, bestätigt oder veröffentlicht). Das Entfernen von Themen erfolgt, wenn eine der beiden:

   - Ein Knowledge Manager entfernt ein Thema. Ein Knowledge Manager entfernt ein Thema auf der Seite **Themen** verwalten.

   - Mehrere Benutzer geben negative Stimmen mit dem Feedbackmechanismus auf der Themenkarte ab. Damit ein Thema entfernt werden kann, muss ein Netz von zwei negativen Stimmen von Benutzern empfangen werden. Wenn beispielsweise ein Benutzer negativ und ein Benutzer für ein bestimmtes Thema positiv stimmte, benötigen Sie noch zwei negative Stimmen, damit das Thema entfernt werden kann.

  Wenn ein veröffentlichtes Thema entfernt wird, muss die Seite mit den kuratierten Details manuell über die Seitenbibliothek des Themencenters gelöscht werden.

## <a name="knowledge-manager-role"></a>Rolle "Knowledge Manager" 

Beim Konfigurieren von Themen für "Viva" fügen Sie eine Gruppe von Benutzern hinzu, denen Berechtigungen zum Anzeigen der Seite **"Themen** verwalten" im Themencenter erteilt wurden. Es wird nur für diese Benutzer angezeigt, die die Rolle der primären Kuration für die Themen übernehmen. Sie haben Zugriff auf Daten zu den Themen und können Listen aller Themen sehen, auf die sie Zugriff haben, um sie zu überprüfen und zu kuratieren.

Mitarbeiter in dieser Rolle sollten über umfassende Berechtigungen zum Anzeigen einer breiten Palette von Themen verfügen. Wenn Berechtigungen segmentiert sind, können Sie eine Gruppe von Benutzern auswählen, die unterschiedliche Bereiche des Unternehmens darstellen und für ihre eigenen Bereiche kuratieren können.

Wenn Sie die Themen zum ersten Mal im Themencenter überprüfen, sind die vorgeschlagenen Themen rein KI-definiert. Möglicherweise möchten Wissensmanager die einzelnen Themen überprüfen, bevor sie "Viva Topics" für eine breite Benutzergemeinschaft ins Rollen bringen. Bei der skalierungsorientierten Arbeit ist dieser Ansatz aufgrund der Tausenden von Themen selten praktikabel.

Der empfohlene Ansatz besteht in der Suche nach einer Balance der relevantesten oder wichtigsten Themen für Ihre anfänglichen Benutzer, und konzentrieren Sie sich vor dem Rollout von "Viva Topics" auf die Kurierung dieser Themen. Beginnen Sie, Feedback von den Benutzern zu sammeln und crowdsourcing die Verwendungs- und Beitragsmuster Ihrer Benutzer zu bestimmen, um die in diesem Artikel vorgeschlagenen Strategien zu informieren.

Es ist wichtig zu erkennen, dass das System sowohl von AI vorgeschlagene als auch vom Menschen kuratierte veröffentlichte Themen für alle Benutzer identifiziert und zeigt. Dies bedeutet jedoch nicht, dass jedes vorgeschlagene Thema allen Endbenutzern angezeigt wird. Die eingerichteten Sicherheitseinstellungen zeigen nur die Themen an, auf die jeder Mitarbeiter basierend auf den Berechtigungen zugreifen kann, die für den Inhalt selbst festgelegt sind.

Als Knowledge Manager mit Berechtigungen  zum Anzeigen der Seite Themen verwalten wird möglicherweise eine viel größere Anzahl von Themen aufgrund Ihrer eigenen erhöhten Berechtigungen aufgelistet, abhängig von Ihrer Rolle in der Organisation und der Zugriffsebene. Sie haben auch Zugriff auf Ansichten, mit denen Sie Themen an einem einzigen Speicherort sehen können, anstatt mithilfe von Hervorhebungen oder suchen auf sie zu zugreifen.

Darüber hinaus gibt es wahrscheinlich einen kleineren Prozentsatz von Themen, die von den meisten Benutzern angezeigt werden, und eine größere Gruppe von mehr Themen, die aufgrund von Berechtigungen viel seltener angezeigt werden. Daher ist es gut, zunächst alle Kurationsaufgaben auf die Themen zu konzentrieren, die für Ihre Organisation am wichtigsten sind und die am ehesten allgemein zu sehen sind.

In diesem Artikel werden einige Strategien für die Kuration behandelt. Diese Strategien können bedeuten, dass die weniger häufigen oder weniger häufigen Themen möglicherweise nicht vollständig von Wissensmanagern behandelt werden. Diese vorgeschlagenen Themen bleiben jedoch nützlich und können Einblicke oder einen Zeiger auf eine Person bieten, wodurch mitarbeiterzeitig nach einem Ausgangspunkt gesucht werden kann. Das Zulassen von crowdsourced-Updates für Themen ist von Vorteil und bietet mehr Inhalt und Abdeckung für weniger häufige Themen.

Dieser Artikel enthält einige Anleitungen und bewährte Methoden zum Umgang mit der Themenverwaltung und -curation.

## <a name="understanding-suggested-topics"></a>Grundlegendes zu vorgeschlagenen Themen

Wenn Themen von AI erkannt werden, werden sie als  vorgeschlagenes Thema **gekennzeichnet,** sowohl auf der Seite Themen verwalten als auch in den Themenkarten, die Benutzern angezeigt werden. Alle Themen, die nicht als entfernt markiert wurden, werden Benutzern angezeigt– dazu gehören bestätigte, veröffentlichte und vorgeschlagene Themen. Themen in allen drei Zustände stehen Endbenutzern zur Verfügung.

Innerhalb einer Themenkarte oder Seite verwenden wir verschiedene Hinweise, um zu zeigen, wie die KI die Informationen generiert hat. Das System verwendet eine Vielzahl von Nachweisen, um die Ressourcen hinzuzufügen, hauptsächlich über den Inhalt selbst.

- Bezeichnungen zeigen, dass ein Thema vorgeschlagen wird und dass es von "Viva Topics" entdeckt wurde.  

   ![Beispielkarte mit einem vorgeschlagenen Thema und vorgeschlagenen Personen und vorgeschlagenen Ressourcen.](../media/knowledge-management/scale-topics-sample-card-suggested-topic.png)

- Informationen auf der Karte geben an, woher eine Definition stammt, indem sie ihre Quelle angeben.

- Vorgeschlagene Personen werden durch Aggregieren von Personen abgeleitet, die Dokumente mit Themenbeweis geschrieben oder bearbeitet haben. Wenn eine Person ein Dokument schreibt, das einen Themanamen im Titel enthält und viele Ansichten hat, kann es nur ein Dokument erfordern, um die Person als verwandt zu einrichten. In vielen Fällen sind jedoch mehr Nachweise besser, und die aufgelisteten Personen haben an mehreren Dokumenten gearbeitet.  

   ![Seite mit einem vorgeschlagenen Thema und vorgeschlagenen Personen, Dateien und Seiten.](../media/knowledge-management/scale-topics-sample-page-suggested-topic.png)

- Für die angezeigten Dateien und Seiten gibt das System an, wie oft das Thema im Dokument erwähnt wurde, aber das Thema muss auch in einem bestimmten Kontext erwähnt werden, der den Verweis auf das Thema eines bestimmten Typs (z. B. Projekt oder Team) identifiziert. Dies ist der Beweis für die KI. Das System berücksichtigt auch das Vorkommen eines Themanamens in den Titeln von Dokumenten, Dokumenttypen und anderen Analysefeatures (z. B. Ansichten).

   ![Abbildung eines Banners, das das Thema Vorgeschlagen enthält, und Microsoft Viva hat dieses Thema entdeckt.](../media/knowledge-management/scale-topics-suggested-you-have-access.png)

   ![Abbildung eines Banners mit dem Titel Vorgeschlagenes Thema und Bearbeiten dieser Seite, um Ihre Beteiligung an diesem Thema zu beschreiben.](../media/knowledge-management/scale-topics-suggested-describe-your-involvement.png)

   ![Abbildung eines Banners mit dem Titel Vorgeschlagenes Thema und Bearbeiten dieser Seite, wenn Sie Personen hinzufügen können, die mit dem Thema verbunden sind.](../media/knowledge-management/scale-topics-suggested-add-people.png)

Diese Attribute zeigen, dass der Inhalt von AI hinzugefügt wurde und wie die KI diese Bestimmung vorgenommen hat.

### <a name="communication"></a>Kommunikation

Bei der Kommunikation mit Ihren Benutzern über "Viva Topics" ist es wichtig, den Unterschied zwischen ki-vorgeschlagenen Themen und Inhalten und ihren kuratierten Entsprechungen zu verdeutlichen.

Als Leser sollten Sie vorgeschlagene Themen mit einem kritischen Auge anzeigen. Sie sollten nicht als autorisierende Quellen der Organisationswahrheit wahrgenommen werden. Vielmehr handelt es sich um ein Wegsuchentool für den Zugriff auf stillschweigende Kenntnisse, die über die Inhalte präsentiert werden, auf die Sie Zugriff haben. Die AI hat das Thema entdeckt und verfügt über genügend Nachweise, um es Ihnen zu zeigen, aber ihr Wert wurde von einer Person nicht bestätigt.

### <a name="crowdsourced-controls"></a>Crowdsourced-Steuerelemente

Vorgeschlagene Themen können durch die Kuration der Seite und durch crowdsourced Feedback zu dem Thema verbessert werden.

Wenn Benutzer mit einem vorgeschlagenen Thema interagieren, wird ihnen möglicherweise eine einfache Frage auf der Benutzeroberfläche gestellt. Beispiel: *War dieses Thema für die Seite relevant?* *Ist diese Person für das Thema relevant?* *War diese Definition richtig?* Durch die Verwendung des Feedbacks zu solchen Fragen kann die Genauigkeit der Themen erhöht werden, ohne dass eine benannte Person die Seite kuratieren muss.

Die Homepage eines Themencenters ist ein weiterer Ort, an dem Feedback zu vorgeschlagenen Themen gesammelt wird. Im Themencenter kann ein Benutzer die Themen sehen, denen er zugeordnet ist, und er kann diese Zuordnung entweder bestätigen oder entfernen lassen.

   ![Beispiel für das Themencenter, in dem vorgeschlagene Themen für den Benutzer angezeigt werden, um die Verbindung zu vorgeschlagenen Themen zu bestätigen oder zu entfernen.](../media/knowledge-management/scale-topics-topic-center-confirm-connections.png)

Wenn Sie ein umfassendes Crowdsourcing von Themen zulassen, sollten Sie die folgenden Faktoren berücksichtigen:

-   Benutzer sehen die Option **Bearbeiten** auf Themenseiten und können die Seiten in derselben Be benutzererfahrung wie andere moderne SharePoint bearbeiten.

-   Einige **vorgeschlagene Themenwebparts** können nicht entfernt werden. Der Themenname, alternative Namen, Definition, vorgeschlagene Personen und vorgeschlagene Ressourcen können nicht entfernt werden.

-   Es kann einige Zeit dauern, bis ein vorgeschlagenes oder  bestätigtes Thema, das veröffentlicht wurde, in die Veröffentlichte Liste auf der Seite **Themen verwalten verschoben** wird.

    -   Die geschätzte Zeit für das Anzeigen eines Themas in der Suche, Hervorhebungen, Hashtags oder Anmerkungen beträgt 2 Stunden.

    -   Die geschätzte Zeit, bis ein Thema  **in** der Veröffentlichten Liste auf der Seite Verwaltete Themen angezeigt wird, beträgt in den meisten Fällen nicht mehr als 24 Stunden. Sie sollten sie innerhalb von 2 Stunden sehen, aber da alle 24 Stunden eine vollständige Synchronisierung besteht, sollte die Wartezeit nicht länger als 24 Stunden sein.

-   Es ist möglich, dass ein Benutzer ein veröffentlichtes Thema in einem Ausgecheckten oder Bearbeitungsstatus belasse. Ein Knowledge Manager kann diese in der Seitenbibliothek des Themencenters anzeigen und entweder die Änderungen des Benutzers verwerfen, um das Thema erneut zu veröffentlichen, oder er kann diesen Benutzer kontaktieren, um zu fordern, dass er das Thema eincheckt.

### <a name="topic-visibility-and-content-is-based-on-a-users-permissions"></a>Sichtbarkeit und Inhalt eines Themas basieren auf den Berechtigungen eines Benutzers

Wenn Sie die Liste der vorgeschlagenen Themen als Knowledge Manager überprüfen, beachten Sie, dass der Inhalt eines vorgeschlagenen Themas dynamisch auf Berechtigungen basiert. Die vorgeschlagenen Inhalte und Personen, die Ihnen angezeigt werden, sind möglicherweise nicht mit denen identisch, die einem Benutzer oder einem anderen Wissensmanager angezeigt werden.

Basierend auf den Berechtigungen zum Anzeigen von Inhalten, die einem Thema zugeordnet sind, wird jedem Benutzer möglicherweise ein anderer Satz vorgeschlagener Ressourcen, Personen, alternativer Namen und Definition angezeigt.

## <a name="prioritize-the-topics-for-curation"></a>Priorisieren der Themen für die Kuration

Sie können die folgenden Strategien verwenden, um Themen zu identifizieren, die wahrscheinlich prominent sind und daher gute Kandidaten für die Kur sind. 

### <a name="taxonomies"></a>Taxonomien

Die Verwendung vorhandener Taxonomien kann eine Liste der Themen enthalten, die für Benutzer wahrscheinlich besonders hervor schen. Dies kann z. B. folgende sein:

-   Produkte und Dienste, die Ihre Organisation bietet

-   Teams in Ihrer Organisation

-   Hochwertige Projekte

Dieser Ansatz kann auch auf abteilungs- oder funktionaler Ebene mit Experten aus Fachbereichen verwendet werden, die diesen Bereich Ihrer Organisation verstehen. Das Ziel besteht nicht in der Überprüfung einer Auswahl oder aller Themen. Stattdessen bringen sie eigene Domänenkenntnisse mit, um die selektive Kuration zu leiten.

### <a name="search"></a>Suche

Häufig werden häufig Suchbegriffe als Themen erkannt. Mithilfe der [wichtigsten Abfrageberichte in Microsoft Search](/sharepoint/view-search-usage-reports)können Sie die häufigsten Suchbegriffe in Ihrer Organisation identifizieren. Wenn Themen für diese Begriffe gefunden wurden, sind sie gute Kandidaten für die Kuration. Diese Themen können in Microsoft Search als Antwortkarten dargestellt werden.

Wenn Sie derzeit [Microsoft Search-Lesezeichen verwenden,](/microsoftsearch/manage-bookmarks)sollten Sie überlegen, welche dieser Lesezeichen durch ein Thema ersetzt werden können. Eine Lesezeichenantwortkarte enthält einen Titel, eine Beschreibung und eine URL. Unter bestimmten Umständen kann eine Themenkarte für einen Benutzer nützlicher sein, und auf einer Themenkarte werden auch Ressourcen und Personen angezeigt.

Wenn ein Benutzer in der Suchfunktion eines Benutzers nach einem Begriff wie "Reisen" *sucht,* werden suchergebnisse in Microsoft Search in der folgenden Prioritätsreihenfolge angezeigt:

1.  Veröffentlichte oder bestätigte Themen

2.  Lesezeichen

3.  Vorgeschlagene Themen

### <a name="impressions-and-quality-score"></a>Impressionen und Qualitätsergebnis

Die [Anzahl der](manage-topics.md#impressions) Impressionen und die Qualität [sind](manage-topics.md#quality-score) wichtige Metriken für das Verständnis des Verhaltens eines Themas. Der Wert dieser Metriken ist begrenzt, wenn nur Wissensmanager oder IT-Teams Zugriff auf Themen haben. Wenn Sie Themen für eine Pilotgruppe von Benutzern verfügbar machen, werden repräsentativere Daten für diese Maßnahmen generiert.

Themen mit hoher Eindruckanzahl werden wahrscheinlich häufiger mit Themen interagiert. Die Qualitätsnote für diese Themen zeigt, wie reich diese Themen sind. Themen mit einer hohen Eindrucksanzahl und einer niedrigen Qualität sind gute Ziele für die Curation.

### <a name="key-terms-from-the-information-architecture-of-larger-organizational-sites"></a>Schlüsselbegriffe aus der Informationsarchitektur größerer Unternehmenswebsites

Größere Portalwebsites in Ihrer Organisation haben möglicherweise Zeit in die Organisation ihrer Informationsarchitektur und die Navigation ihrer Website in wichtigen Themenbereichen für ihre Geschäftseinheiten, Produktlinien, Hauptprojekte und so weiter investiert. Das Überprüfen dieser Begriffe und das Identifizieren und Krümmen von Themen für diese Begriffe können Benutzern helfen, die nach Informationen zu diesen Bereichen suchen.

### <a name="leverage-internal-knowledge-bases-or-wiki-sites"></a>Nutzen interner Wissensdatenbanken oder Wikiwebsites

Wenn Ihre Organisation in Wissensdatenbanken oder Wikiwebsites investiert hat, können diese eine Liste der Themen bereitstellen, die Sie für Ihre anfänglichen Kurationsbemühungen verwenden können. Wenn sie besonders groß sind, wählen Sie die am häufigsten angezeigten oder bearbeiteten Themen als Ausgangspunkt aus.

## <a name="see-also"></a>Siehe auch

[Themen im Topic Center verwalten](manage-topics.md)

[Themencenter-Übersicht](topic-center-overview.md)
