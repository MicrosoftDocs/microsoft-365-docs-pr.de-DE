---
title: Bereitstellen von Exchange Online für Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: Durchlaufen Sie den Prozess der Planung, Einführung und Einführung des Werts von Exchange Online in Microsoft 365 Enterprise in Ihrer Organisation.
ms.openlocfilehash: c54c80a955d86028ac473857cbdcb8b1a8f272d3
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072285"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Bereitstellen von Exchange Online für Microsoft 365 Enterprise

*Diese Workload ist in den Versionen E3 und E5 von Microsoft 365 Enterprise enthalten.*

Exchange Online ist Ihr primärer clouddienst für e-Mail-und Kalenderfunktionen, die Ihren Benutzern bei der Zusammenarbeit auf eine Art und Weise helfen, in der kein Echtzeit-Chat oder zentraler Dokumentspeicher erforderlich ist. Exchange Online ist die Art und Weise, wie Sie die Kommunikation und Planung von einzelnen und kleinen Gruppen durchführen, und ist ein wichtiger Bestandteil des Werts von Microsoft 365 Enterprise für die Zusammenarbeit. Mit Exchange Online können Sie mehr erreichen und effektiver mit der bekannten Outlook-Anwendung arbeiten, unabhängig davon, auf welchem Gerät Sie sich gerade befinden.

Exchange Online verfügt außerdem über erweiterte Sicherheitsfunktionen wie Antischadsoftware und Antispamfilter zum Schutz von Postfächern und Funktionen zur Verhinderung von Datenverlust, die verhindern, dass Benutzer vertrauliche Informationen fälschlicherweise an unbefugte Personen senden. Exchange Online Security ist ein zentrales Element des intelligenten Sicherheits Werts von Microsoft 365 Enterprise.

Wenn Sie eine neue Marke für Exchange Online haben, lesen Sie [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).

Die folgenden Phasen und Schritte führen Sie durch den Prozess der Planung der Rolle von Exchange Online in Ihrer Organisation, das Onboarding Ihrer Organisation zu Exchange Online über eine Reihe von fortschrittlichen Rollouts und die Nutzung von Exchange Online und deren Wert für die Endbenutzer.

>[!Note]
>Diese Bereitstellungsanweisungen sollten erst befolgt werden, nachdem Sie die [Phase 2-Identität](identity-infrastructure.md) der Microsoft 365 Enterprise Foundation-Infrastruktur abgeschlossen haben.
>

## <a name="phase-1-envision"></a>Phase 1: Betrachten

In dieser Phase erfassen Sie die Personen für Ihre Exchange Online-Bereitstellung und bestimmen, wie Ihre Organisation Exchange Online verwendet, um Ihre geschäftlichen Anforderungen zu erfüllen.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Schritt 1: Sammeln Ihrer Exchange Online-Bereitstellungs Mitglieder

Für eine erfolgreiche Bereitstellung von Exchange Online über [Phase 2 – Identität](identity-infrastructure.md) der Microsoft 365 Enterprise Foundation-Infrastruktur müssen Sie die richtigen Mitarbeiter für Eingabe und Feedback erhalten. Zu den wichtigsten Personen zählt die Entscheidungsträger für Unternehmen, IT-Mitarbeiter wie Architekten und Implementierer sowie Fürsprecher für Ihre Endbenutzer. 

Diese drei Gruppen stellen sicher, dass Ihre Exchange Online-Bereitstellung Überlegungen beinhaltet, die geschäftliche Anforderungen, technische Aspekte der Migration und Sicherheit von Postfächern berücksichtigen, und dass das Ergebnis ein typisches Beispiel für Benutzer ist.

#### <a name="result"></a>Ergebnis

Eine Liste von Personen, die die unternehmerischen und technischen Aspekte sowie die Endbenutzer Ihrer Organisation darstellen.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>Schritt 2: ermitteln und Priorisieren Ihrer Exchange Online-Geschäftsszenarien

Exchange Online kann zu unterschiedlichen Zwecken verwendet werden. Sie müssen herausfinden, welche Zwecke Ihren geschäftlichen Anforderungen auf den getrennten Ebenen Ihrer Organisation, ihren Geschäftsgruppen, ihren Abteilungen oder einzelnen Arbeits-und Projektteams zugeordnet werden. Sie sollten Exchange Online anvisieren, um Ihre individuellen und kleinen Gruppen mit kurzlebigen Kommunikations-und Planungsanforderungen zu erfüllen. 

Eine Möglichkeit, die Vorteile von Exchange Online anzuzeigen, besteht darin, zu untersuchen, wie Einzelpersonen, ein Team oder ein v-Team heute interagieren, und dann ein geeignetes Szenario zu finden, das einfachere Möglichkeiten zur Kommunikation, zum Planen von Besprechungen und zur Zusammenarbeit bietet. Beachten Sie, dass [Microsoft Teams](teams-workload.md) für einige ihrer Zusammenarbeitsszenarien möglicherweise besser geeignet ist.

Exchange Online ermöglicht die folgenden strategischen Geschäftsszenarien für Microsoft 365 Enterprise:

- Zusammenarbeiten an Dokumenten in Echtzeit oder in Ihrem eigenen Tempo, um den Mitgestaltungsprozess zu vereinfachen
- Verwalten von Projekten, Aufgaben und Terminen, um Ihre Geschäftsziele zu erreichen
- Verstehen Ihrer Arbeitsgewohnheiten zur Verbesserung Ihres Einflusses und Ihres Eindrucks
- Kommunikation mit Ihrem Team, um auf dem Laufenden zu bleiben, Feedback anzufordern, den Zusammenhalt zu stärken und einen Konsens zu erreichen
- Speichern und Freigeben von Dateien innerhalb und außerhalb Ihrer Organisation für eine nahtlose Zusammenarbeit über Organisationsgrenzen hinweg
- Sicheres Arbeiten überall und jederzeit von Ihrem Gerät aus, um bei einem flexiblen Arbeitsstil produktiver zu arbeiten
- Schützen Ihrer Informationen und Reduzierung des Risikos von Datenverlusten
- Schutz vor externen Bedrohungen 
- Überwachen, melden und Analysieren der Aktivität, um umgehend auf die organisatorische Sicherheit zu reagieren
- Unterstützen Ihrer Organisation mit verbessertem Datenschutz und Compliance, um die Datenschutz-Grundverordnung (DSGVO) zu erfüllen

Weitere Informationen finden Sie unter [Digitale Transformation mit Microsoft 365](http://transform.microsoft.com). 

#### <a name="result"></a>Ergebnis
Eine Liste der Exchange Online-Szenarien, die die Anforderungen Ihrer Organisation an Kommunikation, Terminplanung und Zusammenarbeit in kurzer Zeit erfüllen.

## <a name="phase-2-onboard"></a>Phase 2: Onboarding

In dieser Phase planen Sie die technischen Aspekte einer Exchange Online-Bereitstellung und beginnen mit der Einführung in ausgewählte Benutzergruppen.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Voraussetzungen: Konfigurationen für den Identitäts- und Gerätezugriff

Um den Zugriff auf Exchange Online-Postfächer zu schützen, stellen Sie sicher, dass Sie [Identitäts-und Gerätezugriffs Richtlinien](identity-access-policies.md) und die [empfohlenen Exchange Online-Zugriffsrichtlinien](secure-email-recommended-policies.md)konfiguriert haben.

### <a name="step-1-complete-your-technical-planning"></a>Schritt 1: Abschließen der technischen Planung

Bevor Sie mit der technischen Planung beginnen, legen Sie fest, ob Sie die Kurzhilfe verwenden möchten. Wenn Ihre Organisation über 50 Arbeitsplätze hat und an einem [berechtigten Plan](https://technet.microsoft.com/library/dn783224.aspx)teilnimmt, können Sie [für Microsoft 365](https://fasttrack.microsoft.com/microsoft365), ohne zusätzliche Kosten, zur Verfügung stehen, um Sie durch Planung, Bereitstellung und Dienst Einführung zu führen. Sie können diese Arbeit auch selbst abschließen, indem Sie Onboarding-Assistenten verwenden, die bei [](https://fasttrack.microsoft.com/) der Anmeldung mit Ihrem Office 365-Konto bei der Verbindung zur Verfügung stehen.

Wenn Sie Ihre eigene Planung oder in Verbindung mit der Überführung durchführen, müssen Sie ermitteln, ob Ihr Netzwerk und Ihre Organisation für Exchange Online bereit sind. Es ist besonders wichtig, dass Sie die Beendigungskriterien für das Netzwerk in ihrer Foundation-Infrastruktur erfüllen, mit besonderem Augenmerk auf die Internet Bandbreite, den Durchsatz und die Datenverkehrs Verzögerungen, um die Leistung für den zusätzlichen Datenverkehr für Exchange zu maximieren. Online basierte e-Mails und Anlagen.

Verwenden Sie diese Ressourcen, um sich auf die technischen Aspekte eines Exchange Online-Rollouts vorzubereiten: 

- [Methoden zum Migrieren mehrerer E-Mail-Konten zu Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Zusammenarbeit in Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)
- [Empfänger in Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)

Ein besseres Verständnis der Sicherheit in Exchange Online finden Sie in den folgenden Ressourcen:

- [Berechtigungen in Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx) 
- [Sicherheit und Richtlinientreue für Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx) 
- [Antispam- und Antischadsoftwareschutz](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)

Verwenden Sie als nächstes die folgenden Ressourcen, um die Exchange Online-Postfachverwaltung zu verstehen:

- [Erstellen von Benutzerpostfächern in Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)
- [Verwalten von Benutzerpostfächern](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx) 
- [Erstellen und Verwalten von Verteilergruppen](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a>Ergebnis

Sie verstehen die Migration, Sicherheit und Verwaltung von Postfächern und können mit der Einführung von Exchange Online zu ausgewählten Gruppen in Ihrer Organisation beginnen.

### <a name="step-2-run-an-it-pilot"></a>Schritt 2: Ausführen eines IT-Pilotprojekts

In den meisten mittelständischen und großen Unternehmen bietet es sich an, ein IT-Pilotprojekt mit den Projektbeteiligten aus Phase 1, Erstanwendern und Technikliebhabern durchzuführen.

- Wählen Sie ein Exchange Online-Geschäftsszenario aus, in dem Ihre IT-Pilot Teilnehmer üben können.
- Erteilen Sie Ihren Pilot Teilnehmern Office 365-Lizenzen, und migrieren Sie Ihre lokalen Postfächer zu Exchange Online.
- Geben Sie Ihren Piloten Teilnehmern eine Reihe von Übungen, um Exchange Online-e-Mails, Terminplanung und andere Funktionen zu testen.
- Bestimmen Sie Ihre Change Management-Strategie, und erstellen Sie Materialien, die die organisationsweite Benutzerakzeptanz von Exchange Online fördern. Änderungs Verwaltungs Materialien können e-Mail-Ankündigungstext, interne Schulungspläne, Flur Poster und Präsentationen sein. Diese Materialien informieren Sie Ihre Organisation über Exchange Online und Ihre Vorteile mit dem Ziel, das Bewusstsein zu schärfen und die Nutzung zu verbessern. Einige Ideen finden Sie im Artikel [Change Management Strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) .
- Lassen Sie Ihre IT-Pilot Teilnehmer die Änderungs Verwaltungs Materialien basierend auf Ihren Erfahrungen überarbeiten. Sie bieten Tipps zu bewährten Methoden und Ratschläge, wie Sie die Vorteile von Exchange Online am besten beschreiben und wie Sie es für Kommunikation und Terminplanung verwenden können.

#### <a name="result"></a>Ergebnis

Ihr Exchange Online-IT-Pilotprojekt ist abgeschlossen, und die anfänglichen Änderungs Verwaltungs Materialien wurden entwickelt, überprüft und optimiert.

### <a name="step-3-roll-out-to-a-business-group"></a>Schritt 3: Einführung in eine Unternehmensgruppe

Nachdem Sie Ihr IT-Pilotprojekt abgeschlossen haben, müssen Sie Exchange Online für eine Unternehmensgruppe oder Abteilung in Ihrer Organisation bereitstellen. Wenn Ihre Organisation einen lokalen e-Mail-Dienst wie Exchange Server verwendet, besteht dieser Rollout aus der Postfachmigration. Dieser Rollout sollte Folgendes umfasst:

- Identifizierung der wichtigsten Geschäftsszenarien für Exchange Online innerhalb der Unternehmensgruppe.
- Ankündigungs Aktivitäten, um Benutzer über die Erwartungen und Zeitpläne für die Exchange Online-Nutzung für Abteilungen und Arbeits-oder Projektteams zu informieren.
- Migration von lokalen Postfächern Ihrer Geschäftsgruppen Mitglieder zu Exchange Online.
- Bereitstellen von Benutzerschulungen in Exchange Online oder Links zu Ressourcen zur Einführung von Exchange Online und zur Verwendung.
- Ein Feedbackmechanismus, z. B. ein zentrales Microsoft Teams-Team, das alle Personen in der Unternehmensgruppe enthält, um Kommentare von Benutzern in der Unternehmensgruppe zu sammeln und Probleme zu beheben.

Während der Einführung können Sie Ihre Änderungsverwaltungsmaterialien in Vorbereitung auf die organisationsweite Einführung optimieren.

#### <a name="result"></a>Ergebnis

Eine Unternehmensgruppe wird mit Exchange Online eingerichtet, und die Änderungs Verwaltungs Materialien wurden getestet und optimiert.

## <a name="phase-3-drive-value"></a>Phase 3: Wertschöpfung

In dieser Phase schließen Sie den Rollout von Exchange Online ab und unterstützen Ihre Benutzer bei der Realisierung ihrer Vorteile.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Schritt 1: Bereitstellen von Exchange Online in der restlichen Organisation

Das Rollout in der restlichen Organisation sollte Folgendes beinhalten:

- Identifizierung von wichtigen Geschäftsszenarien für Exchange Online innerhalb separater Unternehmensgruppen.
- Verwenden Sie ihr verfeinertes Change Management-Material für Ankündigungs Aktivitäten, um Ihre Organisation über die Erwartungen und Zeitpläne für die Exchange Online-Nutzung zu informieren.
- Migration der Postfächer für den Rest Ihrer Organisation zu Exchange Online.
- Bereitstellen von Benutzerschulungen in Exchange Online oder Bereitstellung von Links zu Ressourcen zur Einführung von Exchange Online und zur Verwendung.
- Ein Feedbackmechanismus, z. B. ein zentrales Team, das alle Personen in der Unternehmensgruppe enthält, um Kommentare und Probleme von Benutzern in der Organisation zu sammeln. Wenn Ihre Organisation weniger als 2500 Einzelpersonen umfasst, verwenden Sie einen öffentlichen Kanal in Teams. Andernfalls verwenden Sie eine öffentliche Gruppe in Yammer.

#### <a name="result"></a>Ergebnis

Ihre Organisation ist in Betrieb und ihre Change Management-Strategie ist vorhanden, um Benutzer zu informieren, zu Schulen und Ihnen die Verwendung von Exchange Online zu ermöglichen.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Schritt 2: Messen der Nutzung, Verwalten der Zufriedenheit und Fördern der Akzeptanz

Nach der Einführung von Exchange Online für Ihre gesamte Organisation müssen Sie Ihre Change Management-Strategie weiterhin für Folgendes verwenden:

- Führen Sie eine Unterstützung für Exchange Online als primäres Tool für die individuelle und kurzlebige Kommunikation und Terminplanung aus.
- Ermutigen Sie Einzelpersonen, die IT für die Kommunikation, das kalendering und die Zusammenarbeit von Unternehmensgruppen, Abteilungen, Mitarbeitern und Projekten zu verwenden.

Nachfolgend finden Sie einige Vorschläge:

- Weitere Informationen zu allgemeinen bewährten Methoden für die Einführung von Clouddiensten finden Sie im [Office 365-Einführungsleitfaden](https://aka.ms/successfactors). 
- Informationen zur Office 365-Dienstnutzung in Ihrer Organisation finden Sie unter [Office 365-Aktivitätsberichte](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports). Wenn Sie kein globaler Administrator für Office 365 für Ihre Organisation sind, bitten Sie eine Person, die globaler Administrator ist, Ihrem Benutzerkonto Berichteleserberechtigungen zu gewähren, damit Sie auf Aktivitätsberichte zugreifen können.
- Überwachen Sie Ihren Feedback-Veranstaltungsort (einen öffentlichen Kanal in einem zentralen Teams-Team oder jammern) auf Probleme und Feedback von Personen über ihre Erfahrungen mit Exchange Online. Beheben Sie Fragen und Probleme so schnell wie möglich, um frustrierte Personen zu verhindern und die Unterstützung für die Einführung zu demonstrieren.
- Identifizieren und pflegen Sie Champions in jeder Geschäftsgruppe, und heben Sie Ihre Leistungen und bewährten Methoden mit Exchange Online hervor. Reflektieren Sie Ihre Erfolge an der Organisation, um Projekterfolg und-Annahme zu zeigen. Die Unterstützung durch technische Leiter innerhalb einer Unternehmensgruppe kann Einfluss auf Führungskräfte und Peers haben.

#### <a name="result"></a>Ergebnis

Ihre Organisation hat Exchange Online als primäres, individuelles und kleineres Kommunikations-und Planungstool für kurze Zeit verwendet.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Wenn Sie sich in Microsoft Einblicken und erfahren möchten, wie das Unternehmen zu Exchange Online migriert wurde und Exchange Online Protection zum Schutz vor Cyber-Angriffen verwendet, lesen Sie:

- [Microsoft migriert 150.000 Postfächer nach Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft verwendet Informationen zu Bedrohungen, um Bedrohungen zu erkennen, auf diese zu reagieren und vor diesen zu schützen](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft verhindert Phishingangriffe mit Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>Nächste Schritte

Lesen Sie diese Ressourcen für die laufende Wartung von Exchange Online:

- [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx) 
- [Überwachung, Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)
- [Sichern von E-Mails in Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx) 
