---
title: Stellen Sie Exchange Online für Microsoft 365 Enterprise bereit
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Strat_O365_Enterprise
description: Führen Sie durch den Prozess der Planung, Rollout und den Wert der Exchange Online in Microsoft 365 Enterprise in Ihrer Organisation gesteuert.
ms.openlocfilehash: 36b24290acd4467400eab86b4c2760ccad65deab
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868181"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Stellen Sie Exchange Online für Microsoft 365 Enterprise bereit

Exchange Online ist Ihre primäre Cloud-Dienst für e-Mail und Kalenderfunktionen, hilft die Benutzern zusammenarbeiten Möglichkeiten, die erfordern keinen in Echtzeit chatten oder zentralisierte Speicherung von Dokumenten. Exchange Online ist, woher einzelne und kleine Gruppe kurzlebige Kommunikation und Planen von und ist ein Schlüsselelement des integrierten für Zusammenarbeit einem Wert von Microsoft 365 Enterprise. Exchange Online können Sie mehr erreichen und eine effektivere Zusammenarbeit mit bekannten Outlook-Anwendung, unabhängig davon, welches Gerät Sie sich befinden.

Exchange Online hat auch die erweiterte Sicherheitsfunktionen, einschließlich Anti-Malware und Filtern von Anti-Spam-Postfächer zu schützen und Data Loss Prevention-Funktionen, die verhindern, dass Benutzer versehentlich vertraulichen Informationen an nicht autorisierte Personen senden. Exchange Online-Sicherheit ist ein Schlüsselelement des Werts intelligenten Sicherheit von Microsoft 365 Enterprise.

Wenn Sie mit Exchange Online sind, finden Sie unter [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).

Die folgenden Phasen und Schritte führen Sie durch den Prozess von der Rolle von Exchange Online in Ihrer Organisation, Onboarding Ihrer Organisation zu Exchange Online über eine Reihe von schrittweisen Einführungen Entwurfsprozess und fördern der Verwendung von Exchange Online und seine der Wert für die Endbenutzer.

>[!Note]
>Nur, nachdem Sie Ihre [Foundation-Infrastruktur](deploy-foundation-infrastructure.md) für Microsoft 365 Enterprise abgeschlossen haben, sollte diese Bereitstellung Anweisungen folgen.
>

## <a name="phase-1-envision"></a>Phase 1: Betrachten

In dieser Phase sammeln Sie die Personen für Ihre Bereitstellung von Exchange Online und fest, wie Ihre Organisation Exchange Online seiner geschäftlichen Anforderungen gerecht werden.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Schritt 1: Sammeln der Mitglieder einer Exchange Online-Bereitstellung

Für eine erfolgreiche Bereitstellung von Exchange Online auf der Microsoft 365 [Foundation-Infrastruktur](deploy-foundation-infrastructure.md)müssen Sie die richtigen Personen für Eingabe- und Feedback erhalten. Wichtige Personen gehören Entscheidungsträger, IT-Mitarbeiter wie konstruiert und Implementierer und Fürsprecher für die Endbenutzer. 

Diese drei Gruppen stellen Sie sicher, dass Ihre Exchange Online Bereitstellung Aspekte das aufgelistet geschäftlichen Anforderungen, technische Aspekte der Migration von Postfächern und Sicherheit und umfasst, dass das Ergebnis etwas wird, die die meisten Benutzer verwenden.

#### <a name="result"></a>Ergebnis

Eine Liste von Personen, die die unternehmerischen und technischen Aspekte sowie die Endbenutzer Ihrer Organisation darstellen.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>Schritt 2: Bestimmen Sie und Priorisieren Sie Ihre Exchange Online Geschäftsszenarien

Exchange Online können für verschiedene Zwecke verwendet werden. Sie müssen herausfinden, welche Zwecke Ihrer geschäftlichen Anforderungen auf separaten Ebenen in Ihrer Organisation, Ihre Geschäftsbereichen, Abteilungen oder einzelne arbeiten und Project-Teams zuordnen. Sie sollten Exchange Online, um Ihre einzelnen und kleine Gruppe kurzlebige Kommunikation und Planen von Anforderungen aufgelistet adressieren. 

Eine Möglichkeit, die Vorteile von Exchange Online finden Sie unter ist untersuchen, wie Personen, Teams oder V-Team heute interagieren, und suchen Sie dann eine entsprechende Szenarios, in dem bietet einfachere Möglichkeiten, geplante Besprechungen, Kommunikation und Zusammenarbeit. Beachten Sie, dass [Microsoft-Teams,](teams-workload.md) die bessere Wahl für einige Szenarien für die Zusammenarbeit möglicherweise beibehalten.

Exchange Online ermöglicht die folgenden strategischen Geschäftsszenarien für Microsoft 365 Enterprise:

- Zusammenarbeiten an Dokumenten in Echtzeit oder in Ihrem eigenen Tempo, um den Mitgestaltungsprozess zu vereinfachen
- Verwalten von Projekten, Aufgaben und Terminen, um Ihre Geschäftsziele zu erreichen
- Verstehen Ihrer Arbeitsgewohnheiten zur Verbesserung Ihres Einflusses und Ihres Eindrucks
- Kommunikation mit Ihrem Team, um auf dem Laufenden zu bleiben, Feedback anzufordern, den Zusammenhalt zu stärken und einen Konsens zu erreichen
- Speichern und Freigeben von Dateien innerhalb und außerhalb Ihrer Organisation für eine nahtlose Zusammenarbeit über Organisationsgrenzen hinweg
- Sicheres Arbeiten überall und jederzeit von Ihrem Gerät aus, um bei einem flexiblen Arbeitsstil produktiver zu arbeiten
- Schützen Ihrer Informationen und Reduzierung des Risikos von Datenverlusten
- Erkennung von und Schutz gegen externe Bedrohungen 
- Überwachen, Berichten und Analysieren von Aktivität zum umgehend reagieren, um die Sicherheit in der Organisation bereitstellen
- Unterstützen Ihrer Organisation mit verbessertem Datenschutz und Compliance, um die Datenschutz-Grundverordnung (DSGVO) zu erfüllen

Weitere Informationen finden Sie unter [Digitale Transformation mit Microsoft 365](http://transform.microsoft.com). 

#### <a name="result"></a>Ergebnis
Eine Liste mit Exchange Online Situationen, in denen der Anforderungen Ihrer Organisation, planen, Zusammenarbeit und Kommunikation kurzlebige.

## <a name="phase-2-onboard"></a>Phase 2: Onboarding

In dieser Phase für den technischen Aspekten der Exchange Online-Bereitstellung planen und einführungsmethoden für ausgewählte Gruppen von Benutzern zu starten.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Voraussetzungen: Konfiguration des Zugriffs durch Identität und Geräte

Um Zugriff auf Exchange Online-Postfächer zu schützen, stellen Sie sicher, dass Sie die [Identität und Gerät RAS-Richtlinien](identity-access-policies.md) und die [empfohlene Richtlinien für den Exchange Online](secure-email-recommended-policies.md)konfiguriert haben.

### <a name="step-1-complete-your-technical-planning"></a>Schritt 1: Abschließen der technischen Planung

Bevor Sie beginnen, technische Planung, bestimmen Sie, ob Sie schnelle verwenden möchten. Wenn die Organisation über mehr als 50 Arbeitsplätzen und eines [qualifizierten Plan](https://technet.microsoft.com/library/dn783224.aspx)beteiligt ist, können Sie [schnell für Microsoft 365](https://fasttrack.microsoft.com/microsoft365), ohne zusätzliche Kosten durch die Planung, Bereitstellung und Service Annahme leiten verfügbar. Alternativ können Sie diesen Vorgang ausführen selbst mithilfe der schnelle Onboarding-Assistenten, die aus [der schnelle](https://fasttrack.microsoft.com/) verfügbar sind, sobald Sie sich mit Ihrem Office 365-Konto anmelden.

Wenn Sie Ihre eigene Planung ausführen oder in Verbindung mit der schnelle, müssen Sie ermitteln, ob Ihr Netzwerk und Ihre Organisation für Exchange Online bereit sind. Es ist besonders wichtig, dass Sie die abschlusskriterien für Netzwerke in Ihrer Infrastruktur Foundation mit besonders auf die Internetbandbreite, Durchsatz und Datenverkehr Verzögerungen für Maximierung der Leistung für die zusätzlichen Datenverkehr für Exchange erfüllen Online-basierten e-Mails und Anhängen.

Verwenden Sie diese Ressourcen, um für den technischen Aspekten der Exchange Online-Rollout vorzubereiten: 

- [Methoden zum Migrieren mehrerer E-Mail-Konten zu Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)
- [Office 365 e-Mail-Migration advisor](https://portal.office.com/onboarding/mailsetupadvisor#/) (muss bei Ihrem Office 365-Abonnement angemeldet sein)
- [Zusammenarbeit in Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)
- [Empfänger in Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)

Lesen Sie für ein besseres Verständnis der Sicherheit in Exchange Online die folgenden Ressourcen:

- [Berechtigungen in Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx) 
- [Sicherheit und Richtlinientreue für Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx) 
- [Antispam- und Antischadsoftwareschutz](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)

Im nächsten Schritt verwenden Sie diese Ressourcen um zu Exchange Online postfachverwaltung zu verstehen:

- [Erstellen von Benutzerpostfächern in Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)
- [Verwalten von Benutzerpostfächern](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx) 
- [Erstellen und Verwalten von Verteilergruppen](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a>Ergebnis

Sie verstehen Migration von Postfächern, Sicherheit und Verwaltung und können mit Einführung der ausgewählten Gruppen in Ihrer Organisation Exchange Online beginnen.

### <a name="step-2-run-an-it-pilot"></a>Schritt 2: Ausführen eines IT-Pilotprojekts

In den meisten mittelständischen und großen Unternehmen bietet es sich an, ein IT-Pilotprojekt mit den Projektbeteiligten aus Phase 1, Erstanwendern und Technikliebhabern durchzuführen.

- Wählen Sie ein Exchange Online Business Szenario, in dem die Teilnehmer an der Pilotphase IT üben können.
- Geben Sie die Teilnehmer an der Pilotphase Office 365-Lizenzen, und migrieren Sie ihre lokalen Postfächer zu Exchange Online.
- Geben Sie die Teilnehmer an der Pilotphase eine Reihe von Übungen So testen Sie Exchange Online-e-Mail-Planung und andere Funktionen.
- Bestimmen Sie der Change-Management-Strategie und erzeugen Sie Materialien organisationsweiten Benutzer Akzeptanz von Exchange Online zu. Änderung Management Materialien können e-Mail-Ankündigungstext, interne Schulungspläne, Gang Poster und Präsentationen enthalten. Dieses Material werden Ihrer Organisation zu Exchange Online und seine Vorteile durch die Ziele der auslösen zur Förderung des Bekanntheitsgrads und treibende Verwendungsanalyse darüber informieren. Finden Sie im Artikel [Ändern Management-Strategie für das Microsoft-Teams,](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) einige Ideen.
- Haben Sie Ihre IT pilot Teilnehmer die Änderung Management Materialien basierend auf ihren Erfahrungen überprüfen. Sie können auf best Practices Tipps und Ratschläge, wie Sie am besten beschreiben die Vorteile von Exchange Online und für die Kommunikation und-Planung Verwendungsweise bereitstellen.

#### <a name="result"></a>Ergebnis

Der Exchange Online für IT-Pilotphase abgeschlossen ist und die anfängliche Änderung Management Materialien wurden entwickelt, geprüft und eingeschränkt.

### <a name="step-3-roll-out-to-a-business-group"></a>Schritt 3: Einführung in eine Unternehmensgruppe

Klicken Sie nach Abschluss der Pilotphase IT, Einführung von Exchange Online Business Gruppe oder Abteilung in Ihrer Organisation. Wenn Ihre Organisation einen lokale e-Mail-Dienst wie Exchange Server verwendet wird, besteht die Implementierung Migration von Postfächern aus. Einführung sollten Folgendes umfassen:

- Kennung für wichtige Geschäftsszenarien für Exchange Online innerhalb der Unternehmensgruppe.
- Ankündigung Aktivitäten aus, die Benutzer über die Erwartungen und Zeitrahmen für Exchange Online-Nutzung für Abteilungen und Arbeit "oder" Project-Teams zu informieren.
- Migration von lokalen Postfächern der Mitglieder Ihrer Business zu Exchange Online.
- Versendung benutzerschulungen zu Exchange Online oder Links zu Ressourcen, eine Einführung in Exchange Online und dessen Verwendung.
- Ein Feedbackmechanismus, z. B. ein zentrales Microsoft Teams-Team, das alle Personen in der Unternehmensgruppe enthält, um Kommentare von Benutzern in der Unternehmensgruppe zu sammeln und Probleme zu beheben.

Während der Einführung können Sie Ihre Änderungsverwaltungsmaterialien in Vorbereitung auf die organisationsweite Einführung optimieren.

#### <a name="result"></a>Ergebnis

Eine Unternehmensgruppe ist nicht gedrückt und Ausführung mit Exchange Online und die Änderung Management Materialien getestet und eingeschränkt wurden.

## <a name="phase-3-drive-value"></a>Phase 3: Wertschöpfung

In dieser Phase abgeschlossen die Einführung von Exchange Online und unterstützen Ihre Benutzer, mit denen sie die Vorteile auszuschöpfen.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Schritt 1: Einführung von Exchange Online für den Rest Ihrer Organisation

Das Rollout in der restlichen Organisation sollte Folgendes beinhalten:

- Kennung für wichtige Geschäftsszenarien für Exchange Online in separaten Geschäftsbereichen.
- Verwendung von Ihrer eingeschränkten Änderung Management Referenzmaterial für Ankündigung Aktivitäten aus, die Ihrer Organisation der erwartet zu informieren und Zeitachsen für die Verwendung von Exchange Online.
- Migration der Postfächer für den Rest Ihrer Organisation zu Exchange Online.
- Spielt die Schulung von Benutzern auf Exchange Online, oder geben Sie Links zu Ressourcen, die eine Einführung in Exchange Online und dessen Verwendung.
- Ein Feedbackmechanismus, z. B. ein zentrales Team, das alle Personen in der Unternehmensgruppe enthält, um Kommentare und Probleme von Benutzern in der Organisation zu sammeln. Wenn Ihre Organisation weniger als 2500 Einzelpersonen umfasst, verwenden Sie einen öffentlichen Kanal in Teams. Andernfalls verwenden Sie eine öffentliche Gruppe in Yammer.

#### <a name="result"></a>Ergebnis

Ihrer Organisation ist nicht gedrückt und ausgeführt werden und Ihre Strategie für die Änderung Management direkt zu informieren und Schulen Aktivieren von Benutzern zum Verwenden von Exchange Online ist.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Schritt 2: Messen der Nutzung, Verwalten der Zufriedenheit und Fördern der Akzeptanz

Nach der Einführung der Exchange Online in der gesamten Organisation, müssen Sie weiterhin Ihre Änderung-Strategie einsetzen:

- Haben Sie Ihre führende Exchange Online als primäres Tool für die einzelnen und kurzlebige Kommunikation fördern und planen.
- Fördern Sie Personen für die Verwendung für Unternehmensgruppe, Abteilung, Work, und project Team Communications, Kalender und Zusammenarbeit.

Nachfolgend finden Sie einige Vorschläge:

- Weitere Informationen zu allgemeinen bewährten Methoden für die Einführung von Clouddiensten finden Sie im [Office 365-Einführungsleitfaden](https://aka.ms/successfactors). 
- Informationen zur Office 365-Dienstnutzung in Ihrer Organisation finden Sie unter [Office 365-Aktivitätsberichte](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263). Wenn Sie kein globaler Administrator für Office 365 für Ihre Organisation sind, bitten Sie eine Person, die globaler Administrator ist, Ihrem Benutzerkonto Berichteleserberechtigungen zu gewähren, damit Sie auf Aktivitätsberichte zugreifen können.
- Überwachen Sie Ihr Feedback Veranstaltungsort (einen öffentlichen Kanal in einem zentralen Teams Team- oder Yammer) Informationen zu Problemen und Feedback von Personen zu ihren Erfahrungen mit Exchange Online. Beheben Sie so schnell wie möglich, um zu verhindern, dass frustrierte Einzelpersonen und demonstrieren die Unterstützung für das Rollout Fragen und Probleme.
- Identifizieren und Champions in jeder Gruppe Business Mentorenprogramme und markieren Sie ihre erreichten und bewährte Methoden, die mit Exchange Online. Entsprechend ihren Erfolge, für die Organisation Projekterfolg und Annahme anzeigen. Billigung durch technischen Leiter innerhalb einer Unternehmensgruppe kann einen starken Einfluss über Führungskräfte und Peers ausüben.

#### <a name="result"></a>Ergebnis

Ihre Organisation hat Exchange Online als primäre einzelne und kleine Gruppe kurzlebige Kommunikation und Planungstool eingeführt.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Um Microsoft verkürzt, und erfahren, wie das Unternehmen zu Exchange Online migriert und Exchange Online Protection zum Schutz vor Angriffen im Internet verwendet, finden Sie unter:

- [Microsoft migriert 150.000 Postfächer nach Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft verwendet Informationen zu Bedrohungen, um Bedrohungen zu erkennen, auf diese zu reagieren und vor diesen zu schützen](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft verhindert Phishingangriffe mit Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>Nächste Schritte

Finden Sie diese Ressourcen für die Wartung von Exchange Online:

- [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx) 
- [Überwachung, Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)
- [Sichern von E-Mails in Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx) 
