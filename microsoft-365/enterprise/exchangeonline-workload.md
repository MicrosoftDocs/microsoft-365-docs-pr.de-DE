---
title: Bereitstellen von Exchange Online für Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/29/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: Durchlaufen Sie den Prozess der Planung, Einführung und Steuerung des Werts von Exchange Online in Microsoft 365 Enterprise innerhalb Ihrer Organisation.
ms.openlocfilehash: a13cb36dd313ef3e6763c6c48720bb2b3e935880
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981876"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Bereitstellen von Exchange Online für Microsoft 365 Enterprise

*Diese Workload ist in den Versionen E3 und E5 von Microsoft 365 Enterprise enthalten.*

Exchange Online ist Ihr primärer clouddienst für e-Mail und Kalender, mit dem Ihre Benutzer auf eine Weise zusammenarbeiten können, für die kein Echtzeitchat oder zentralisierter Dokumentspeicher erforderlich ist. Exchange Online ist die Art und Weise, wie Sie eine kurzlebige Kommunikation und Terminplanung für einzelne und kleine Gruppen ausführen und ist ein zentrales Element des Werts "Built for Teamwork" von Microsoft 365 Enterprise. Mit Exchange Online können Sie mehr erreichen und effektiver mit der bekannten Outlook-Anwendung arbeiten, unabhängig von dem Gerät, auf dem Sie sich befinden.

Exchange Online verfügt darüber hinaus über erweiterte Sicherheitsfunktionen wie Antischadsoftware und Anti-Spam-Filterung zum Schutz von Postfächern und Verhinderung von Datenverlusten, die verhindern, dass Benutzer vertrauliche Informationen versehentlich an unbefugte Personen senden. Exchange Online Sicherheit ist ein zentrales Element des intelligenten Sicherheits Werts von Microsoft 365 Enterprise.

Wenn Sie Exchange Online neu sind, finden Sie weitere Informationen unter [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).

Die folgenden Phasen und Schritte führen Sie durch den Prozess der Vorstellung der Rolle von Exchange Online in Ihrer Organisation, der Onboarding Ihrer Organisation zur Exchange Online durch eine Reihe von progressiven Rollouts und die Verwendung von Exchange Online und deren Wert für die Endbenutzer.

>[!Note]
>Diese Bereitstellungsanweisungen sollten nur befolgt werden, nachdem Sie [Phase 2-Identität](identity-infrastructure.md) der Microsoft 365 Enterprise Foundation-Infrastruktur abgeschlossen haben.
>

## <a name="phase-1-envision"></a>Phase 1: Betrachten

In dieser Phase sammeln Sie die Personen für Ihre Exchange Online-Bereitstellung und bestimmen, wie Ihre Organisation Exchange Online verwendet, um Ihre geschäftlichen Anforderungen zu erfüllen.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Schritt 1: Sammeln der Exchange Online-Bereitstellungs Mitglieder

Für eine erfolgreiche Bereitstellung von Exchange Online oberhalb von [Phase 2 – Identität](identity-infrastructure.md) der Microsoft 365 Enterprise Foundation-Infrastruktur, müssen Sie die richtigen Personen für Eingabe und Feedback erhalten. Zu den wichtigsten Personen zählen Geschäfts Entscheidungsträger, IT-Mitarbeiter wie Architekten und Implementierungen sowie Fürsprecher für Ihre Endbenutzer. 

Diese drei Gruppen stellen sicher, dass Ihre Exchange Online-Bereitstellung Überlegungen zum Umgang mit geschäftlichen Anforderungen, zu technischen Aspekten der Postfachmigration und Sicherheit umfasst und dass das Ergebnis von typischen Benutzern verwendet wird.

#### <a name="result"></a>Ergebnis

Eine Liste von Personen, die die unternehmerischen und technischen Aspekte sowie die Endbenutzer Ihrer Organisation darstellen.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>Schritt 2: ermitteln und Priorisieren Ihrer Exchange Online Geschäftsszenarien

Exchange Online können für verschiedene Zwecke verwendet werden. Sie müssen herausfinden, welche Zwecke Ihren geschäftlichen Anforderungen auf den separaten Ebenen Ihrer Organisation, ihrer Geschäftsgruppen, ihrer Abteilungen oder einzelner Arbeits-und Projektteams zugeordnet werden. Sie sollten Exchange Online gezielt auf Ihre individuellen und kleinen Gruppen mit kurzer Lebensdauer für Kommunikation und Terminplanung ausrichten. 

Eine Möglichkeit, die Vorteile von Exchange Online zu sehen, besteht darin zu untersuchen, wie Einzelpersonen, ein Team oder ein v-Team heute interagieren, und dann ein geeignetes Szenario zu finden, das einfachere Möglichkeiten zur Kommunikation, zum Planen von Besprechungen und zur Zusammenarbeit bietet. Beachten Sie, dass [Microsoft Teams](teams-workload.md) möglicherweise eine bessere Wahl für einige ihrer Szenarien für die Zusammenarbeit darstellt.

#### <a name="result"></a>Ergebnis
Eine Liste von Exchange Online Szenarien, die die Anforderungen Ihrer Organisation an Kommunikation, Planung und kurzlebige Zusammenarbeit erfüllen.

## <a name="phase-2-onboard"></a>Phase 2: Onboarding

In dieser Phase planen Sie die technischen Aspekte einer Exchange Online-Bereitstellung und beginnen mit dem Rollout an ausgewählte Benutzergruppen.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Voraussetzungen: Konfigurationen für den Identitäts- und Gerätezugriff

Um den Zugriff auf Exchange Online Postfächer zu schützen, stellen Sie sicher, dass Sie [Identitäts-und Gerätezugriffs Richtlinien](identity-access-policies.md) und die [empfohlenen Exchange Online Zugriffsrichtlinien](secure-email-recommended-policies.md)konfiguriert haben.

### <a name="step-1-complete-your-technical-planning"></a>Schritt 1: Abschließen der technischen Planung

Bevor Sie mit der technischen Planung beginnen, müssen Sie feststellen, ob Sie die Kurzhilfe verwenden möchten. Wenn Ihre Organisation über 50 Sitze hat und an einem [berechtigten Plan](https://technet.microsoft.com/library/dn783224.aspx)teilnimmt, können Sie den raschen Einsatz [für Microsoft 365](https://fasttrack.microsoft.com/microsoft365)verwenden, der Sie ohne zusätzliche Kosten durch Planung, Bereitstellung und Dienst Einführung zur Verfügung stellt. Oder Sie können diese Arbeit selbst mithilfe von Kurzhilfe-Onboarding-Assistenten abschließen, die [bei der](https://fasttrack.microsoft.com/) Anmeldung mit Ihrem Office 365 Konto verfügbar sind.

Wenn Sie Ihre eigene Planung oder in Verbindung mit dem kurzstand durchführen, müssen Sie ermitteln, ob Ihr Netzwerk und Ihre Organisation für Exchange Online geeignet sind. Es ist besonders wichtig, dass Sie die Beendigungskriterien für Netzwerke in ihrer Foundation-Infrastruktur mit besonderem Augenmerk auf Internet Bandbreite, Durchsatz und Datenverkehrs Verzögerungen erfüllen, um die Leistung für den zusätzlichen Datenverkehr für Exchange zu maximieren. Online basierte e-Mails und Anlagen.

Verwenden Sie diese Ressourcen, um sich auf die technischen Aspekte eines Exchange Online-Rollout vorzubereiten: 

- [Methoden zum Migrieren mehrerer E-Mail-Konten zu Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Zusammenarbeit in Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)
- [Empfänger in Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)

Lesen Sie die folgenden Ressourcen, um ein besseres Verständnis der Sicherheit in Exchange Online zu erhalten:

- [Berechtigungen in Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx) 
- [Sicherheit und Compliance für Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx) 
- [Antispam- und Antischadsoftwareschutz](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)

Verwenden Sie als nächstes die folgenden Ressourcen, um Exchange Online Postfachverwaltung zu verstehen:

- [Erstellen von Benutzerpostfächern in Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)
- [Verwalten von Benutzerpostfächern](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx) 
- [Erstellen und Verwalten von Verteilergruppen](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a>Ergebnis

Sie verstehen die Migration, Sicherheit und Verwaltung von Postfächern und können mit dem Rollout Exchange Online an ausgewählte Gruppen in Ihrer Organisation beginnen.

### <a name="step-2-run-an-it-pilot"></a>Schritt 2: Ausführen eines IT-Pilotprojekts

In den meisten mittelständischen und großen Unternehmen bietet es sich an, ein IT-Pilotprojekt mit den Projektbeteiligten aus Phase 1, Erstanwendern und Technikliebhabern durchzuführen.

- Wählen Sie ein Exchange Online Geschäftsszenario aus, in dem Ihre IT-Pilot Teilnehmer üben können.
- Erteilen Sie Ihren Pilot Teilnehmern Office 365 Lizenzen, und migrieren Sie Ihre lokalen Postfächer zu Exchange Online.
- Geben Sie Ihren Pilot Teilnehmern eine Reihe von Übungen zum Testen Exchange Online e-Mail, der Planung und anderer Funktionen.
- Bestimmen Sie Ihre Strategie für die Änderungsverwaltung, und erstellen Sie Materialien, um die Einführung von Exchange Online durch den organisationsweiten Benutzer zu fördern. Änderungs Verwaltungsmaterial kann e-Mail-Ansagetext, interne Schulungspläne, Flur Poster und Präsentationen umfassen. Diese Materialien informieren Ihre Organisation über Exchange Online und deren Vorteile mit dem Ziel, das Bewusstsein zu schärfen und die Nutzung zu verbessern. Einige Ideen finden Sie im Artikel [Change Management Strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) .
- Lassen Sie Ihre IT-Pilot-Teilnehmer die Änderungs Verwaltungs Materialien basierend auf Ihren Erfahrungen überprüfen. Sie können Tipps zu bewährten Methoden und Ratschlägen zur optimalen Beschreibung der Vorteile von Exchange Online und zur Verwendung für Kommunikation und Terminplanung bereitstellen.

#### <a name="result"></a>Ergebnis

Ihr Exchange Online IT-Pilot ist abgeschlossen, und die anfänglichen Änderungs Verwaltungs Materialien wurden entwickelt, überprüft und optimiert.

### <a name="step-3-roll-out-to-a-business-group"></a>Schritt 3: Einführung in eine Unternehmensgruppe

Stellen Sie nach Abschluss Ihres IT-Pilotprojekts Exchange Online für eine Unternehmensgruppe oder Abteilung in Ihrer Organisation bereit. Wenn Ihre Organisation einen lokalen e-Mail-Dienst wie Exchange Server verwendet, besteht diese Einführung aus der Postfachmigration. Dieser Rollout sollte Folgendes umfassen:

- Identifikation wichtiger Geschäftsszenarien für Exchange Online innerhalb der Unternehmensgruppe.
- Ankündigungs Aktivitäten, um Benutzer über die Erwartungen und Zeitpläne für Exchange Online Nutzung für Abteilungen und Arbeits-oder Projektteams zu informieren.
- Migration von lokalen Postfächern Ihrer Geschäftsgruppen Mitglieder zu Exchange Online.
- Bereitstellen von Benutzerschulungen auf Exchange Online oder Links zu Ressourcen, um Exchange Online und deren Verwendung einzuführen.
- Ein Feedbackmechanismus, z. B. ein zentrales Microsoft Teams-Team, das alle Personen in der Unternehmensgruppe enthält, um Kommentare von Benutzern in der Unternehmensgruppe zu sammeln und Probleme zu beheben.

Während der Einführung können Sie Ihre Änderungsverwaltungsmaterialien in Vorbereitung auf die organisationsweite Einführung optimieren.

#### <a name="result"></a>Ergebnis

Eine Unternehmensgruppe wird mit Exchange Online gestartet und die Änderungs Verwaltungs Materialien wurden getestet und verfeinert.

## <a name="phase-3-drive-value"></a>Phase 3: Wertschöpfung

In dieser Phase führen Sie das Rollout von Exchange Online durch und unterstützen Ihre Benutzer dabei, Ihre Vorteile zu verwirklichen.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Schritt 1: Rollout Exchange Online auf den Rest Ihrer Organisation

Das Rollout in der restlichen Organisation sollte Folgendes beinhalten:

- Identifikation wichtiger Geschäftsszenarien für Exchange Online in separaten Geschäftsgruppen.
- Verwenden Sie Ihre verfeinerten Änderungs Verwaltungs Materialien für Ankündigungs Aktivitäten, um Ihre Organisation über die Erwartungen und Zeitpläne für Exchange Online Nutzung zu informieren.
- Migration der Postfächer für den Rest Ihrer Organisation zu Exchange Online.
- Bereitstellung von Benutzerschulungen auf Exchange Online oder Bereitstellen von Links zu Ressourcen, um Exchange Online und deren Verwendung einzuführen.
- Ein Feedbackmechanismus, z. B. ein zentrales Team, das alle Personen in der Unternehmensgruppe enthält, um Kommentare und Probleme von Benutzern in der Organisation zu sammeln. Wenn Ihre Organisation weniger als 2500 Einzelpersonen umfasst, verwenden Sie einen öffentlichen Kanal in Teams. Andernfalls verwenden Sie eine öffentliche Gruppe in Yammer.

#### <a name="result"></a>Ergebnis

Ihre Organisation ist in Betrieb und ihre Change Management-Strategie ist vorhanden, um Benutzern die Verwendung von Exchange Online zu informieren, zu Schulen und zu ermöglichen.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Schritt 2: Messen der Nutzung, Verwalten der Zufriedenheit und Fördern der Akzeptanz

Nachdem Sie Exchange Online für Ihre gesamte Organisation bereitstellen, müssen Sie Ihre Change Management-Strategie weiterhin für Folgendes einsetzen:

- Lassen Sie Ihre Führungskräfte Exchange Online als das primäre Tool für die individuelle und kurzlebige Kommunikation und Terminplanung fördern.
- Ermutigen Sie einzelne Personen, es für Geschäftsgruppen-, Abteilungs-, Arbeits-und Projektteam Kommunikation, Kalender und Zusammenarbeit zu verwenden.

Nachfolgend finden Sie einige Vorschläge:

- Weitere Informationen zu allgemeinen bewährten Methoden für die Einführung von Clouddiensten finden Sie im [Office 365-Einführungsleitfaden](https://aka.ms/successfactors). 
- Informationen zur Office 365-Dienstnutzung in Ihrer Organisation finden Sie unter [Office 365-Aktivitätsberichte](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports). Wenn Sie kein globaler Administrator für Office 365 für Ihre Organisation sind, bitten Sie eine Person, die globaler Administrator ist, Ihrem Benutzerkonto Berichteleserberechtigungen zu gewähren, damit Sie auf Aktivitätsberichte zugreifen können.
- Überwachen Sie Ihren Feedback-Veranstaltungsort (ein öffentlicher Kanal in einem Team für zentrale Teams oder ein jammern) auf Probleme und Feedback von Einzelpersonen über ihre Erfahrungen mit Exchange Online. Beheben Sie Fragen und Probleme so schnell wie möglich, um frustrierte Personen zu verhindern und die Unterstützung für das Rollout zu demonstrieren.
- Identifizieren und pflegen Sie Champions in jeder Unternehmensgruppe, und heben Sie deren Errungenschaften und bewährte Methoden mithilfe von Exchange Online hervor. Reflektieren Sie Ihre Erfolge an die Organisation, um den Erfolg und die Akzeptanz von Projekten zu zeigen. Die Befürwortung durch technische Führungskräfte innerhalb einer Unternehmensgruppe kann einen starken Einfluss auf Führungskräfte und Kollegen ausüben.

#### <a name="result"></a>Ergebnis

Ihre Organisation hat Exchange Online als primäre einzelne und kleine Gruppe von Kommunikations-und Planungstools mit kurzer Lebensdauer übernommen.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Wenn Sie in Microsoft Einblicken und erfahren möchten, wie das Unternehmen zu Exchange Online migriert und Exchange Online Schutz vor Cyber-Angriffen schützt, lesen Sie Folgendes:

- [Microsoft migriert 150.000 Postfächer nach Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft verwendet Informationen zu Bedrohungen, um Bedrohungen zu erkennen, auf diese zu reagieren und vor diesen zu schützen](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft verhindert Phishingangriffe mit Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>Nächste Schritte

Lesen Sie diese Ressourcen für die laufende Wartung von Exchange Online:

- [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx) 
- [Überwachung, Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)
- [Sichern von E-Mails in Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx) 
