---
title: Suchen und Visualisieren personenbezogener Daten in der Microsoft-Datenschutzverwaltung (Vorschau)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Erfahren Sie mehr über die Übersicht und das Datenprofil im Datenschutzmanagement und wie Sie Einblicke in die personenbezogenen Daten in der Microsoft 365 Umgebung Ihrer Organisation erhalten.
ms.openlocfilehash: d8ea8d3306840244aff7621a12702d0ca19062c0
ms.sourcegitcommit: 022d9d91263994c48efcebe08a84319573dc3a8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53378562"
---
# <a name="find-and-visualize-personal-data-in-privacy-management-preview"></a>Suchen und Visualisieren personenbezogener Daten in der Datenschutzverwaltung (Vorschau)

In diesem Artikel: Erfahren Sie mehr über die Features der **Übersichts-** und **Datenprofilseiten** und wie diese Einblicke in Ihre Daten geben können.

## <a name="purpose-of-the-overview-and-data-profile"></a>Zweck der Übersicht und des Datenprofils

Microsoft 365 Datenschutzverwaltung bietet Ihnen Funktionen zum Suchen und Visualisieren der personenbezogenen Daten in Ihrer Umgebung. Die Lösung automatisiert die Ermittlung personenbezogener Datenressourcen in Exchange, SharePoint, OneDrive und Teams und bietet Dashboards, die wichtige Einblicke in die Daten bieten. Ihre Datenschutzadministratoren können auf diese Erkenntnisse reagieren, um den Ansatz Ihrer Organisation für den Datenschutz zu stärken und Risiken zu verringern.

### <a name="overview-page"></a>Übersichtsseite

Die Übersichtsseite dient als allgemeines Dashboard für die Datenschutzverwaltungslösung und bietet dynamische Einblicke über das Ökosystem ihrer Organisation aus personenbezogenen Daten. Datenschutzadministratoren können Datentrends und -aktivitäten überwachen, potenzielle Risiken für personenbezogene Daten erkennen und untersuchen und wichtige Aktivitäten wie Richtlinienverwaltung oder Anträge betroffener Personen berücksichtigen. Weitere Informationen zur Übersichtsseite finden Sie auf [der Übersichtsseite.](#explore-the-overview-page)

### <a name="data-profile-page"></a>Datenprofilseite

Die Seite "Datenprofil" in der Datenverwaltung bietet eine Momentaufnahme der personenbezogenen Daten, die Ihre Organisation in Microsoft 365 speichert. Auf diese Weise können Sie visualisieren, wo personenbezogene Daten gespeichert sind, welche Typen in Ihrer Organisation am häufigsten vorkommen und wie viele verschiedene Typen in Ihren Microsoft 365-Diensten vorhanden sind. Sie können auch personenbezogene Daten von diesem Ort aus erkunden. Weitere Informationen finden Sie auf [der Seite "Datenprofil"](#explore-the-data-profile-page).

## <a name="explore-the-overview-page"></a>Erkunden der Übersichtsseite

Die Übersichtsseite besteht aus drei Hauptabschnitten. Kacheln oben auf der Seite stellen wichtige aktuelle Statistiken zu Ihren Daten bereit. Der Abschnitt mit den wichtigsten Erkenntnissen bietet Untersuchungsmöglichkeiten zu Trends und Bereichen von zentralem Interesse. Weitere Informationen zu Ihrer Datenumgebung finden Sie in den Trendliniendiagrammen. Weitere Informationen zu diesen Bereichen finden Sie in den folgenden Abschnitten.

### <a name="top-tiles"></a>Top-Kacheln

#### <a name="policy-matches-over-past-7-days"></a>Richtlinienüberstimmungen in den letzten 7 Tagen

Wenn Richtlinien innerhalb der Datenschutzverwaltung festgelegt werden, werden Ihre Daten für bestimmte Bedingungen ausgewertet, die Datenschutzrisiken darstellen können. Richtlinienüberstimmungen deuten auf Datenentdeckungen hin, die möglicherweise einer weiteren Überprüfung oder Korrektur bedürfen. Diese Karte zeigt die Anzahl aller Richtlinienübersprechungen an, die innerhalb der letzten sieben Tage aufgetreten sind. Hier werden Übereinstimmungen angezeigt, unabhängig davon, ob Richtlinien aktiviert sind oder im Testmodus ausgeführt werden, damit Sie die Ergebnisse aller aktiven Richtlinien sehen können. Wenn Sie auf diese Kachel klicken, gelangen Sie zu einer gefilterten Ansicht der Seite "Richtlinien" der Datenschutzverwaltung, auf der die Richtlinien angezeigt werden, bei denen innerhalb der letzten sieben Tage eine Übereinstimmung aufgetreten ist.

#### <a name="items-with-personal-data"></a>Elemente mit personenbezogenen Daten

Um die automatisierten Ermittlungsfunktionen der Datenschutzverwaltungslösung bei der Arbeit anzuzeigen, überprüfen Sie die Kachel "Elemente mit persönlichen Daten". Dadurch wird angezeigt, wie viele neue Elemente, die personenbezogene Daten enthalten, in der Microsoft 365 Umgebung Ihrer Organisation in den letzten sieben Tagen entdeckt wurden. Durch Klicken auf diese Kachel wird eine Ansicht der neuesten 100 ermittelten Elemente geladen.

#### <a name="subject-rights-requests"></a>Anträge auf Rechte von Antragstellern

Die oberen Kacheln der Übersichtsseite enthalten zwei Kacheln im Zusammenhang mit Denkberechtigungsanforderungen. Die erste zeigt die Anzahl der Anforderungen, die in den letzten sieben Tagen erstellt wurden. Die zweite Kachel löst Anforderungen aus, die überfällig sind und möglicherweise sofortige Aufmerksamkeit erfordern. Wenn Sie auf diese Kacheln klicken, erhalten Benutzer die entsprechenden Berechtigungen für die Seite "Antragstellerrechte anfordern" der Datenschutzverwaltung.

### <a name="key-insights"></a>Wichtige Erkenntnisse

#### <a name="content-items-with-the-most-personal-data"></a>Inhaltselemente mit den persönlichsten Daten

Inhalte in der Microsoft 365 Umgebung Ihrer Organisation, die eine große Menge an personenbezogenen Daten enthalten, können ein höheres Risiko einer Gefährdung darstellen. Sie können diese Elemente überprüfen, um sicherzustellen, dass sie von einer Datenschutzrichtlinie abgedeckt werden. Um diese Elemente auf Sich aufmerksam zu machen, bietet die Übersichtsseite eine Ansicht ihrer Inhaltselemente, die die persönlichsten Daten enthalten. Hier sehen Sie die Anzahl der erkannten eindeutigen personenbezogenen Datentypen, wie viele eindeutige Inhaltsbesitzer identifiziert wurden und wie viele betroffene Personen gemäß den Datenabgleichseinstellungen für Anträge betroffener Personen identifiziert wurden.

Wählen Sie "Zusammenfassung anzeigen" aus, um eine Zusammenfassungsansicht der gefundenen Elemente anzuzeigen. Sie können diese Ergebnisse auch erkunden, um eine Vorschau einzelner Dateien anzuzeigen. In dieser Ansicht werden maximal 100 Elemente angezeigt. Benutzer in der Rollengruppe "Datenschutzverwaltung" können Dateien auswählen, um Details zu überprüfen und die Relevanz zu ermitteln, und die Liste im .csv Format zur Referenz exportieren.

#### <a name="policies-with-the-most-matches-in-the-last-week"></a>Richtlinien mit den meisten Übereinstimmungen in der letzten Woche

Diese Einblicke zeigen, welche Richtlinien in den letzten sieben Tagen am häufigsten abgeglichen wurden, sei es im "Ein"-Modus oder im "Testen". Dies hilft ihnen, die Leistung Ihrer Richtlinien und die Auswirkungen der laufenden Arbeit zu veranschaulichen, wenn Ihre Benutzer des Datenschutzmanagements Schulungen erhalten und in der Lage sind, Probleme mit Inhalten zu beheben und ihr Datenschutzverhalten zu verfeinern.

Wählen Sie "Zusammenfassung anzeigen" aus, um eine Zusammenfassung der 10 am häufigsten gefundenen Richtlinien und der Inhaltsbesitzer der zugeordneten Inhalte anzuzeigen. Außerdem wird angezeigt, wie viele Benutzerbenachrichtigungen aufgrund dieser Richtlinienüberstimmungen gesendet wurden und wie viele Benutzeraktionen ausgeführt wurden. Wählen Sie "Untersuchen" aus, um die Seite "Richtlinien" in der Datenschutzverwaltung anzuzeigen, gefiltert, um die Richtlinien aus der Zusammenfassungsansicht anzuzeigen. In dieser Untersuchungsansicht werden Statistiken für die gesamte Lebensdauer der Richtlinie angezeigt. Wählen Sie ihn aus, um Details anzuzeigen, z. B. wann übereinstimmende Elemente anfänglich erkannt wurden.

#### <a name="users-with-the-most-policy-matched-in-the-last-week"></a>Benutzer, deren Richtlinie in der letzten Woche am häufigsten abgeglichen wurde

Dieser Einblick befasst sich auch mit Übereinstimmungen aus Richtlinien im "Testmodus" oder im "Ein"-Modus. Sie können eine Zusammenfassung der Benutzer mit den meisten Richtlinienübereinstimmungen in der letzten Woche anzeigen und welche Richtlinien sie abgleichen. Dies umfasst Summen der eindeutigen Inhaltsbesitzer, an diese Benutzer gesendete Benachrichtigungen und wie viele Aktionen aus diesen Benachrichtigungen ausgeführt wurden. Wenn Sie "Untersuchen" auswählen, gelangen Sie zur Seite "Richtlinien", gefiltert, um die Richtlinien aus der Zusammenfassungsansicht anzuzeigen. In der Untersuchungsansicht finden Sie keine Benutzerinformationen, aber Sie können eine Richtlinie auswählen, um Richtliniendetails im Zusammenhang mit diesen Übereinstimmungen anzuzeigen.

#### <a name="items-with-the-most-data-subject-content"></a>Elemente mit den meisten Inhalten betroffener Personen

Dieser Einblick betrifft Informationen aus der Datenübereinstimmungsfunktion in Anträgen auf Rechte von Betroffenen und oberflächent Elemente, die in Microsoft 365 gefunden werden, die die meisten betroffenen Personen in ihren Inhalten enthalten. Weitere Informationen zu dieser Einstellung finden Sie unter [Verwalten von Antragstellerrechten.](privacy-management-subject-rights-requests.md)

Diese Elemente können Ihnen helfen, Ihre Datenabgleichskonfiguration zu bestätigen und Datenschutzrisiken im Zusammenhang mit diesen Elementen zu mindern. Wählen Sie Zusammenfassung anzeigen für eine Zusammenfassungsansicht aus. Wählen Sie "Erkunden" aus, um eine detaillierte Ansicht von bis zu 100 dieser Elemente zu finden. Hier können Sie eine Vorschau dieser Elemente anzeigen und die Relevanz ermitteln und die Liste im .csv Format exportieren.

### <a name="trendline-graphs"></a>Trendliniendiagramme

Dynamische Visualisierungen von Trends, die in den Daten Ihrer Organisation zu finden sind, finden Sie in den Trendliniendiagrammen. Diese Diagramme können nach Merkmalen gefiltert werden, die für die bereitgestellten Informationen relevant sind, z. B. Zeiträume, Datentyp oder Speicherorte von Daten. Verwenden Sie die bereitgestellten Dropdowns, um Ihre Ansicht anzupassen. Wenn Sie mit dem Mauszeiger über Linien im Diagramm zeigen, können Sie Statistiken anzeigen, die sich auf diesen bestimmten Zeitpunkt beziehen.

Zu den Ergebnissen im Zusammenhang mit Richtlinien gehören Daten aus Richtlinien im Modus "Test" und "Ein". Wenn keine Richtlinien eines bestimmten Typs aktiv sind, werden in den zugehörigen Diagrammen keine Ergebnisse angezeigt.

#### <a name="active-policy-alerts"></a>Warnungen bei aktiven Richtlinien

In diesem Bereich wird eine Momentaufnahme der aktiven Warnungen angezeigt, die durch Richtlinienübersprechung ausgelöst werden. Mit der Zeit können Sie mit dieser Ansicht Anomalien leichter erkennen, z. B. große Mengenspitzen. Wählen Sie Warnungen anzeigen aus, um zur Seite "Richtlinien" innerhalb der Datenschutzverwaltung zu navigieren, auf der Sie Warnungen weiter untersuchen und Probleme für die Behebung erstellen können.

#### <a name="personal-data-found-in-organization"></a>In der Organisation gefundene personenbezogene Daten

Dieses Diagramm zeigt Trends in bezug darauf, wie viele personenbezogene Daten im Laufe der Zeit in Ihrer Microsoft 365 Umgebung ermittelt wurden und wo sie sich befinden. Sie beginnt mit dem Auffüllen, nachdem die Datenverwaltung ausreichend lange ausgeführt wurde und nachdem Inhalte mit personenbezogenen Daten innerhalb SharePoint, OneDrive, Teams und/oder Exchange gefunden wurden.

#### <a name="data-transfers-detected-in-organization"></a>In der Organisation erkannte Datenübertragungen

Dieses Diagramm bezieht sich auf Datenübertragungsrichtlinien. Es bietet eine Übersicht darüber, wie Daten innerhalb Ihrer Organisation verschoben werden, entweder zwischen Abteilungen oder zwischen Regionen für Multi-Geo-Organisationen.

#### <a name="unused-personal-data"></a>Nicht verwendete personenbezogene Daten

Dieses Diagramm bezieht sich auf Richtlinien zur Datenminimierung. Es bietet Einblicke, wie Ihre Organisation Inhalte mit personenbezogenen Daten speichert und wie Ihre Richtlinien den Umgang mit diesen Daten im Laufe der Zeit verbessern können.

#### <a name="overexposed-personal-data"></a>Überlastete personenbezogene Daten

Dieses Diagramm bezieht sich auf Datenüberlastungsrichtlinien. Es kann Ihnen helfen, Freigabeverhalten im Laufe der Zeit innerhalb Ihrer Organisation und Speicherorte zu identifizieren, an denen Inhalte mit personenbezogenen Daten möglicherweise überlastet sind, z. B. indem sie öffentlich, für einen externen Benutzer freigegeben oder in Ihrer Organisation umfassend freigegeben werden.

#### <a name="subject-rights-requests-by-regulation"></a>Anträge betroffener Personen nach Verordnung

Diese Ansicht bietet Einblicke in die Vorschriften, die ihre Anträge auf Rechte betroffener Personen im Laufe der Zeit am häufigsten vorantreiben. Die Legende dieses Diagramms zeigt verschiedene Bestimmungen. Wenn Sie mit dem Mauszeiger über die Trendlinien zeigen, werden die Gesamtsummen der Anträge betroffener Personen angezeigt, die während der ausgewählten Zeit für diese Verordnung geöffnet wurden.

#### <a name="subject-rights-requests-by-status"></a>Anträge von Antragstellerrechten nach Status

Dieses Diagramm zeigt, wie Ihre Organisation mit der Erledigung von Anträgen auf Betreffrechte arbeitet, aufgeteilt in Anforderungen, die entweder aktiv, geschlossen oder überfällig sind. Die hier vorgestellten Ergebnisse können ihnen helfen, anzugeben, wo Sie von der Zuweisung weiterer Ressourcen profitieren könnten, um Ihre Anforderungen zu schließen und Ziele zu erfüllen.

### <a name="additional-data-views"></a>Zusätzliche Datenansichten

#### <a name="subject-rights-requests-at-a-glance"></a>Anträge auf Rechte betroffener Personen auf einen Blick

Diese Ansicht bietet eine allgemeine Übersicht über anträge aktiver Antragstellerrechte, einschließlich der verbleibenden Zeit zum Abschließen von Anforderungen bis zu ihren definierten Stichtagen. Es wird zusammengefasst, wie viele Anforderungen Sie insgesamt haben, wie viele aktiv sind und wie viele geschlossen sind. Wählen Sie "Alle Anforderungen anzeigen" aus, um zur Seite zur Anforderung von Betreffrechten zu wechseln, auf der Sie weitere Details anzeigen und an den aktiven Anforderungen arbeiten können, um sie bis zum Abschluss zu führen.

#### <a name="subject-rights-requests-by-residency"></a>Anträge betroffener Personen nach Dementhaltung

Diese Kartenansicht hilft Ihnen bei der Visualisierung Ihres Umfangs von Anträgen auf Rechte von Betroffenen durch den Wohnsitz der betroffenen Personen. Wenn Sie mit dem Mauszeiger auf eine Blase zeigen, werden die Region und die Gesamtzahl der Anträge betroffener Personen identifiziert, die im Auftrag von Dort ansässigen Personen geöffnet wurden.

## <a name="explore-the-data-profile-page"></a>Erkunden der Datenprofilseite

### <a name="personal-data-type-instances-detected-in-microsoft-365"></a>In Microsoft 365 erkannte Instanzen des persönlichen Datentyps

Mit dieser Karte können Sie visualisieren, wie viele personenbezogene Daten in Ihrer Microsoft 365 Umgebung vorhanden sind und wie diese Daten über Exchange, OneDrive, SharePoint und Teams verteilt werden.

Das Balkendiagramm zeigt die ungefähre Aggregatanzahl eindeutiger Instanzen des persönlichen Datentyps, die in Ihren Inhalten gefunden werden. Beispiele für Datentypen können z. B. Kreditkartennummern und Sozialversicherungsnummern sein. Daher würde eine ermittelte Datei, die drei Kreditkartennummern und eine Sozialversicherungsnummer enthält, zwei eindeutige personenbezogene Datentypen und vier Instanzen enthalten. Die untere Person dieser Karte zeigt die eindeutigen persönlichen Datentypen an jedem Microsoft 365 Speicherort an. Sie bietet einen Einblick in die Vielfalt der personenbezogenen Datentypen, die in den Inhalten Ihrer Organisation erkannt werden.

### <a name="top-personal-data-types-across-your-organization"></a>Die wichtigsten typen personenbezogener Daten in Ihrer Organisation

Diese Karte enthält eine Momentaufnahme der wichtigsten in Ihrer Umgebung erkannten personenbezogenen Datentypen sowie Informationen dazu, wie viele Elemente diesen persönlichen Datentyp enthalten und an welchen Speicherorten.

### <a name="personal-data-by-region"></a>Personenbezogene Daten nach Region

Bei Multi-Geo-Umgebungen aggregiert diese Karte instanzen des typs "personenbezogener Daten" regional, die sich in Ihren Inhalten befinden, basierend auf den Regionen, in denen diese Inhalte gehostet werden. Für Organisationen mit einer Region zeigt diese Karte einen Punkt an, der Ihren Microsoft 365 Dienststandort darstellt. Wenn Sie auf der Karte auf Punkte zeigen, wird die ungefähre Anzahl der in dieser Region entdeckten Instanzen des typs "Personenbezogener Datentyp" angezeigt.

### <a name="exploring-content"></a>Erkunden von Inhalten

Wenn Sie **"Durchsuchen"** auf einer beliebigen Datenprofilkarte auswählen, wird der Inhalts-Explorer geöffnet. Zu diesem Zeitpunkt können Sie nicht nach einem bestimmten Inhaltselement suchen, und in dieser Ansicht werden keine Teams Daten angezeigt. Dies bedeutet, dass Zahlen im Inhalts-Explorer möglicherweise nicht mit den auf der Datenprofilseite angezeigten Zahlen übereinstimmen, da die Datenprofilseite Teams Inhalt enthält. Datenschutzadministratoren, die weitere Einblicke in ihre Datenschutzdaten erhalten möchten, können dies hier basierend auf dem persönlichen Datentyp (Typ vertraulicher Informationen) oder nach Standort (Exchange, OneDrive oder SharePoint) tun.
