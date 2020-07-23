---
title: Bereitstellen von SharePoint und OneDrive für Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/11/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: Durchlaufen Sie den Prozess der Planung, Einführung und Wertschöpfung von SharePoint in Ihrem Unternehmen.
ms.openlocfilehash: 77beb26065a9ecfd37acf976e7415cc870ff8ea4
ms.sourcegitcommit: fe20f5ed07f38786c63df0f73659ca472e69e478
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201498"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a>Bereitstellen von SharePoint und OneDrive für Microsoft 365 Enterprise

*Diese Workload ist in den Versionen E3 und E5 von Microsoft 365 Enterprise enthalten.*

In SharePoint und Microsoft Teams können Sie Dateien speichern und freigeben, Inhalte verwalten und zusammenarbeiten. Beide sind wesentliche Bestandteile des Mehrwerts Built for Teamwork von Microsoft 365 Enterprise. 

SharePoint verfügt zudem über erweiterte Sicherheitsfunktionen, einschließlich Zugriffssteuerung mit Berechtigungen und Verschlüsselung von Daten bei der Übertragung und im Ruhezustand. SharePoint-Sicherheit ist ein Schlüsselelement des Mehrwerts Intelligente Sicherheit von Microsoft 365 Enterprise.

Wenn Sie über keinerlei Erfahrung mit SharePoint verfügen, finden Sie unter [SharePoint](https://products.office.com/sharepoint/collaboration) und [Erste Schritte mit SharePoint](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121) weitere Informationen.

Die folgenden Phasen und Schritte führen Sie durch den Prozess der Betrachtung der Rolle von SharePoint in Ihrer Organisation, des Onboardings Ihrer Organisation über eine Reihe progressiver Einführungen sowie die Förderung der Nutzung und dessen Wert für Ihre Endbenutzer. Bevor Sie beginnen, stellen Sie sicher, dass Sie die richtigen [Foundation-Infrastruktur](deploy-workloads.md#foundation-infrastructure-prerequisites)-Phasen konfiguriert haben, sodass Ihre SharePoint-Websites die erforderlichen Sicherheitsfunktionen aufweisen. 

Anleitungen zum Bereitstellen von OneDrive für Microsoft 365 Enterprise finden Sie im [OneDrive-Leitfaden für Unternehmen](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).

## <a name="phase-1-envision"></a>Phase 1: Betrachten
In dieser Phase bringen Sie die Organisationspartner für Ihre SharePoint-Bereitstellung zusammen und bestimmen, wie SharePoint in Ihrer Organisation verwendet werden wird, um deren Geschäftsanforderungen zu erfüllen.

### <a name="step-1-gather-your-sharepoint-deployment-members"></a>Schritt 1: Zusammenbringen der SharePoint-Bereitstellungsmitglieder

Für eine erfolgreiche Bereitstellung von SharePoint auf der Grundlage der [Microsoft 365 Enterprise Fundamentinfrastruktur](deploy-foundation-infrastructure.md) benötigen Sie die richtigen Personen für Input und Feedback. Dazu gehören Entscheidungsträger im Unternehmen, IT-Mitarbeiter, wie z. B. Architekten und Implementierer, und Fürsprecher für Ihre Endbenutzer. 

Diese drei Gruppen stellen sicher, dass Ihre Bereitstellung Aspekte umfasst, die sich mit den geschäftlichen Anforderungen und technischen Aspekten der Migration von Ordnern sowie Dokumenten und Sicherheit befassen, und dass Ergebnis etwas ist, was typische Benutzer verwenden.

#### <a name="result"></a>Ergebnis

Eine Liste von Personen, die die unternehmerischen und technischen Perspektiven sowie die Endbenutzer Ihrer Organisation darstellen.

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a>Schritt 2: Ermitteln und Priorisieren Ihrer SharePoint-Geschäftsszenarien

SharePoint kann für unterschiedliche Zwecke verwendet werden. Sie müssen herausfinden, welche Anforderungen Ihres Unternehmens erfüllt werden können. Sie können SharePoint für das Speichern und Teilen von Dokumenten, das Content Management und die Zusammenarbeit Ihrer Teams, Ihrer Abteilung oder der gesamten Organisation einsetzen. 

Die Liste der Szenarien und Funktionen finden Sie unter [SharePoint](https://products.office.com/sharepoint/collaboration ).

Die folgenden Geschäftssäulen können den Anforderungen Ihrer Organisation gerecht werden:

|||
|:-----|:-----|
| Freigabe und Zusammenarbeit | Nutzen Sie Teamwebsites, Kommunikationswebsites und Synchronisierung. |
| Informieren und Einbinden | Informationen werden zu einem späteren Zeitpunkt bereitgestellt. |
| Transformation | Verwendet Flow zum Erstellen automatisierter Workflows zwischen Apps und Diensten. |
| Nutzung von kollektivem Wissen | Verwenden Sie die Suche, um innerhalb Ihrer Organisation die gewünschten Ergebnisse zu erhalten. |
| Schützen | Stellen Sie sicher, dass Ihr Unternehmen geschützt ist und über die richtige Compliance verfügt. |
|||

Unter [SharePoint-Admin](https://docs.microsoft.com/sharepoint/sharepoint-online) finden Sie Ressourcen zum Konfigurieren von SharePoint für Ihre Anforderungen.

Sie können die Vorteile von SharePoint ermitteln, indem Sie die aktuelle Interaktionsweise von Personen, eines Teams, einer Abteilung oder der gesamten Organisation untersuchen und dann ein entsprechendes Szenario suchen, das einfachere Methoden zum Speichern und Freigeben von Dateien bietet. Beachten Sie, dass [Microsoft Teams](teams-workload.md) für einige Szenarien die bessere Wahl sein kann.

#### <a name="result"></a>Ergebnis
Eine Liste der SharePoint-Szenarien, in denen die Anforderungen Ihrer Organisation in Bezug auf die Speicherung und Freigabe von Dokumenten, das Content-Management, die Zusammenarbeit und die Sicherheit behandelt werden.

## <a name="phase-2-onboard"></a>Phase 2: Onboarding

In dieser Phase werden die technischen Aspekte einer SharePoint-Bereitstellung geplant, und es wird mit der Einführung der Programme für ausgewählte Benutzergruppen begonnen.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Voraussetzungen: Konfigurationen für den Identitäts- und Gerätezugriff

Um den Zugriff auf die SharePoint-Websites zu schützen, stellen Sie sicher, dass Sie [Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md) und die [empfohlenen SharePoint-Zugriffsrichtlinien](sharepoint-file-access-policies.md) konfiguriert haben.

### <a name="step-1-complete-your-technical-planning"></a>Schritt 1: Abschließen der technischen Planung

Bevor Sie mit der Planung beginnen, legen Sie fest, ob Sie FastTrack verwenden möchten. Wenn Ihre Organisation über mehr als 50 Arbeitsplätze und einen [berechtigten Plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365) verfügt, können Sie kostenlos verfügbare FastTrack-Vorteile nutzen, die Sie bei der Planung, Migration, Bereitstellung und Diensteinführung unterstützen. Sie können diese Aufgaben auch selbst durchführen, indem Sie FastTrack-Onboarding-Assistenten nutzen, die Ihnen nach der Anmeldung mit Ihrem Office 365-Konto unter [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) zur Verfügung stehen.

Wenn Sie Ihre eigene Planung (oder in Verbindung mit FastTrack) vornehmen, müssen Sie ermitteln, ob Ihr Netzwerk und Ihre Organisation für SharePoint bereit sind. Sie müssen unbedingt die [Beendigungskriterien für Netzwerke](networking-exit-criteria.md) in Ihrer Foundation-Infrastruktur erfüllen. Besonderes Augenmerk liegt dabei auf der Internetbandbreite, dem Durchsatz und Datenverkehrverzögerungen zur Maximierung der Leistung für den zusätzlichen Verkehr von SharePoint-basierten Dokumenten.

Verwenden Sie [Migrieren zu SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online), um sich auf Ihr SharePoint-Rollout vorzubereiten.

Sehen Sie sich für ein besseres Verständnis der Sicherheit in SharePoint die folgenden Ressourcen an:
- [So schützen SharePoint und OneDrive Ihre Daten in der Cloud](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
- [Datenverschlüsselung in OneDrive und SharePoint](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)

#### <a name="result"></a>Ergebnis

Sie erfahren mehr über die Migration und Sicherheit von SharePoint-Websites und lokalen Ordnern sowie Dokumenten und können mit der Einführung von SharePoint in ausgewählten Gruppen Ihrer Organisation beginnen.

### <a name="step-2-run-an-it-pilot"></a>Schritt 2: Ausführen eines IT-Pilotprojekts

In den meisten mittelständischen und großen Unternehmen bietet es sich an, ein IT-Pilotprojekt mit den Projektbeteiligten aus Phase 1, Erstanwendern und Technikliebhabern durchzuführen. Während des IT-Pilotprojekts:

- Wählen Sie ein SharePoint-Geschäftsszenario, in dem die Teilnehmer der IT-Pilotphase üben können.
- Geben Sie den Teilnehmern der Pilotphase eine Reihe von Übungen, um das Speichern von Dokumenten, Freigeben, Zusammenarbeiten und andere Funktionen in SharePoint zu testen.
- Ermitteln Sie Ihre Strategie für das Änderungsmanagement, und erstellen Sie Materialien, die für eine organisationsweite Benutzerakzeptanz von SharePoint sorgen. Materialien für das Änderungsmanagement können E-Mail-Ansagetexte, interne Schulungspläne, Flurplakate und Präsentationen umfassen. Diese Materialien informieren Ihre Organisation über SharePoint und dessen Vorteile und haben den Zweck, zu sensibilisieren und die Verwendung zu steigern. Informationen zum Einstieg finden Sie unter [SharePoint-Ressourcen für die Anwenderakzeptanz](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/).
- Lassen Sie Ihre IT-Pilotmitglieder anhand Ihrer Erfahrungen das Änderungsmanagement-Material überprüfen. Sie können Tipps zu bewährten Methoden und Ratschläge dazu teilen, wie Sie die Vorteile von SharePoint und dessen Verwendung am besten beschreiben.

#### <a name="result"></a>Ergebnis

Ihr SharePoint-IT-Pilot ist abgeschlossen, und die Materialien für die Änderungsverwaltung wurden entwickelt, überprüft und optimiert.

### <a name="step-3-roll-out-to-a-business-group"></a>Schritt 3: Einführung in eine Unternehmensgruppe

Nach Abschluss des IT-Pilotprojekts führen Sie SharePoint in einer Unternehmensgruppe oder Abteilung in Ihrer Organisation ein. Dieser Rollout sollte Folgendes umfassen:

- Identifizierung von wichtigen Geschäftsszenarien für SharePoint innerhalb der Unternehmensgruppe.
- Ankündigungsaktivitäten, um Benutzer über die Erwartungen und Zeitpläne für die SharePoint-Nutzung für Abteilungen sowie Arbeits- und Projektteams zu informieren.
- Migration von lokalen Ordnern und Dokumenten der Mitglieder Ihrer Geschäftsgruppe zu SharePoint.
- Angebot einer Benutzerschulung oder Links zu Ressourcen, um Sharepoint und seine Verwendung vorzustellen. Siehe [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23)-Videoschulungen.
- Ein Feedbackmechanismus, z. B. ein zentrales Microsoft Teams-Team, das alle Personen in der Unternehmensgruppe enthält, um Kommentare von Benutzern in der Unternehmensgruppe zu sammeln und Probleme zu beheben.
 
Während der Einführung können Sie Ihre Änderungsverwaltungsmaterialien in Vorbereitung auf die organisationsweite Einführung optimieren.

#### <a name="result"></a>Ergebnis

Eine Unternehmensgruppe verwendet SharePoint, und die Änderungsverwaltungsmaterialien wurden getestet und optimiert.

## <a name="phase-3-drive-value"></a>Phase 3: Wertschöpfung

In dieser Phase führen Sie das Rollout von SharePoint aus und helfen Anwendern dabei, seine Vorteile zu ergründen.

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>Schritt 1: Einführung in der restlichen Organisation

Das Rollout in der restlichen Organisation sollte Folgendes beinhalten:

- Identifizierung von wichtigen Geschäftsszenarien für SharePoint innerhalb separater Unternehmensgruppen.
- Verwendung der optimierten Änderungsverwaltungsmaterialien für Ankündigungsaktivitäten, um Ihre Organisation über die Erwartungen und Zeitpläne für die Nutzung zu informieren.
- Migration von Ordnern und Dokumenten für den Rest Ihrer Organisation zu SharePoint.
- Bieten Sie eine Endbenutzerschulung an oder stellen Sie Links zu Ressourcen bereit, um SharePoint und dessen Verwendung vorzustellen.
- Ein Feedbackmechanismus, z. B. ein zentrales Team, das alle Personen in der Unternehmensgruppe enthält, um Kommentare und Probleme von Benutzern in der Organisation zu sammeln. Wenn Ihre Organisation weniger als 2500 Einzelpersonen umfasst, verwenden Sie einen öffentlichen Kanal in Teams. Andernfalls verwenden Sie eine öffentliche Gruppe in Yammer.

#### <a name="result"></a>Ergebnis
Teams wurde in Ihrer Organisation eingeführt und läuft, und Ihre Strategie für die Änderungsverwaltung wird verwendet, um Benutzer zu informieren, zu schulen und ihnen die Möglichkeit zu geben, mit der Verwendung von SharePoint zu beginnen.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Schritt 2: Messen der Nutzung, Verwalten der Zufriedenheit und Fördern der Akzeptanz

Nach der Einführung in der gesamten Organisation, müssen Sie Ihre Strategie für die Änderungsverwaltung weiterhin verwenden, damit:

- Lassen Sie Ihre Führungskräfte SharePoint als wichtigstes Tool für die Dokumentspeicherung und -Freigabe bewerben.
- Ermutigen Sie Einzelpersonen dazu, es zur Speicherung von Dokumenten und für die Freigabe zwischen Geschäftsgruppen, Abteilungen sowie Arbeits- und Projektteams zu verwenden.

Nachfolgend finden Sie einige Vorschläge:

- Weitere Informationen zu allgemeinen bewährten Methoden für die Einführung von Clouddiensten finden Sie in [Erfolgsfaktoren für Microsoft 365](https://aka.ms/successfactors). 
- Informationen zur Dienstnutzung in Ihrer Organisation finden Sie unter [Microsoft 365-Berichte im Admin Center](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports). Wenn Sie kein globaler Administrator für Ihre Organisation sind, bitten Sie eine Person, die globaler Administrator ist, Ihrem Benutzerkonto Berichteleserberechtigungen zu gewähren, damit Sie auf Aktivitätsberichte zugreifen können.
- Überwachen Sie Ihren Feedback-Kanal (ein öffentlicher Kanal in einem zentralen Teams-Team oder Yammer) auf Fragen und Feedback von Einzelpersonen zu ihren Erfahrungen mit SharePoint. Behandeln Sie Fragen und Probleme so schnell wie möglich, um eine frustrierende Erfahrung für Einzelpersonen zu verhindern und Unterstützung für den Rollout zu demonstrieren.
- Ermitteln und pflegen Sie Champions in jeder Geschäftsgruppe und heben Sie deren Erfolge und bewährte Methoden bei der Verwendung von SharePoint hervor. Zeigen Sie der Organisation ihre Erfolge, um den Erfolg und die Akzeptanz des Projekts zu zeigen. Die Bestätigung durch technische Leiter innerhalb einer Unternehmensgruppe kann einen starken Einfluss auf Führungskräfte und Kollegen ausüben.

#### <a name="result"></a>Ergebnis

Ihre Organisation hat SharePoint in Microsoft 365 Enterprise zur Unterstützung der Dokumentationsspeicherung und Zusammenarbeit eingeführt.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Wenn Sie einen Einblick in Microsoft erhalten und erfahren möchten, wie wir SharePoint bereitgestellt haben, lesen Sie bitte [SharePoint in der Cloud: Erfahren Sie, wie Microsoft seine eigene Migration ausführte](https://www.microsoft.com/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration).

## <a name="next-steps"></a>Nächste Schritte

Diese Ressourcen bieten Informationen zur kontinuierlichen Wartung von SharePoint: 

- [Grundlegendes zu Berechtigungsstufen in SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [Anpassen von SharePoint-Websiteberechtigungen](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [Aktivieren und Deaktivieren der externen Freigabe für SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [Einrichten und Verwalten der Funktion „Zugriffsanforderungen“](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
