---
title: Bereitstellen von Microsoft Teams für Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: Durchlaufen Sie den Prozess der Planung, Einführung und Wertschöpfung von Microsoft Teams in Microsoft 365 Enterprise in Ihrem Unternehmen.
ms.openlocfilehash: 1e7519817a10eb4aa710dff2d4c74c9390c9f6f6
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072855"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a>Bereitstellen von Microsoft Teams für Microsoft 365 Enterprise

*Diese Workload ist in den Versionen E3 und E5 von Microsoft 365 Enterprise enthalten.*

In Microsoft Teams werden Chats, Konferenzen, Dokumentfreigabe und Diskussionsthreads derart kombiniert, dass das Erstellen und Freigeben von Inhalten über Gruppen hinweg erleichtert wird. Teams ermöglicht Teamarbeit und Zusammenarbeit für Microsoft 365 Enterprise und ist ein Schlüsselelement für den Ansatz „Built for Teamwork“ von Microsoft 365. Wenn Sie noch nicht mit Teams vertraut sind, lesen Sie die Informationen unter [Übersicht über Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).
 
Wenn Sie derzeit Skype for Business verwenden, wird Sie interessieren, dass wir Skype for Business-Funktionen in Teams entwickeln. Dies ist ein stufenweiser Prozess, und am Ende ist Teams die einzige Clientoberfläche. Als geschätzter Skype for Business-Kunde möchte Microsoft Sie unterstützen. Weitere Informationen finden Sie unter [Der Weg von Skype for Business zu Microsoft Teams](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams).

Die folgenden Phasen und Schritte führen Sie durch den Prozess der Betrachtung der Rolle von Teams in Ihrer Organisation, des Onboardings Ihrer Organisation in Teams über eine Reihe progressiver Einführungen sowie die Förderung der Nutzung von Teams und dessen Wert für Ihre Endbenutzer. 

Bevor Sie beginnen, stellen Sie sicher, dass Sie die richtigen [Foundation-Infrastruktur](deploy-foundation-infrastructure.md)-Phasen konfiguriert haben, sodass Ihren Teams die erforderlichen Sicherheitsfunktionen zur Verfügung stehen.

## <a name="phase-1-envision"></a>Phase 1: Betrachten

In dieser Phase bringen Sie die Personen für Ihre Teams-Bereitstellung zusammen und bestimmen, wie Teams in Ihrer Organisation verwendet wird, um deren Geschäftsanforderungen zu erfüllen.

### <a name="step-1-gather-your-teams-deployment-members"></a>Schritt 1: Zusammenbringen der Teams-Bereitstellungsmitglieder
Für eine erfolgreiche Bereitstellung von Teams auf der Grundlage der Microsoft 365 [Fundamentinfrastruktur](deploy-foundation-infrastructure.md) benötigen Sie die richtigen Personen für Input und Feedback. Dazu gehören Entscheidungsträger im Unternehmen, IT-Mitarbeiter, wie z. B. Architekten und Implementierer, und Fürsprecher für Ihre Endbenutzer. 

Diese drei Gruppen stellen sicher, dass Ihre Teams-Bereitstellung Aspekte umfasst, die sich mit den geschäftlichen Anforderungen sowie technischen Aspekten der Lizenzierung und Sicherheit befassen, und dass Teams etwas ist, was Ihre typischen Benutzer verwenden.

#### <a name="result"></a>Ergebnis

Eine Liste von Personen, die die unternehmerischen und technischen Aspekte sowie die Endbenutzer Ihrer Organisation darstellen.

### <a name="step-2-determine-and-prioritize-your-teams-business-scenarios"></a>Schritt 2: Ermitteln und Priorisieren Ihrer Teams-Geschäftsszenarien
Teams kann für unterschiedliche Zwecke verwendet werden. Sie müssen herausfinden, welcher Zweck Ihren Geschäftsanforderungen auf den unterschiedlichen Ebenen Ihrer Organisation, Ihren Unternehmensgruppen, Abteilungen und einzelnen Arbeits- und Projektteams entspricht. Beispiele, mit denen Sie Teams-Szenarios definieren können, finden Sie unter [Microsoft 365-Produktivitätsbibliothek](https://www.microsoft.com/microsoft-365/success/?rtc=1). 

Teams sollte für sich schnell entwickelnde und stark vernetzte Teams verwendet eingesetzt werden, die eng zusammen arbeiten und viel mehr Funktionen benötigen als nur E-Mail mit Exchange Online liefern kann. Beispiele sind Live-Gruppenchats mit einen aufgezeichneten Verlauf und ein allgemeiner und leicht auffindbarer Ort zum Speichern von Dateien und Notizen. 

Eine Möglichkeit, die Vorteile von Teams aufzuzeigen, besteht darin zu untersuchen, wie ein Team oder ein V-Team heute interagiert und dann ein entsprechendes Teams-Szenario zu suchen, das die Interaktion ersetzt und einfachere Möglichkeiten zur Zusammenarbeit sowie zusätzliche Funktionen bietet.

Teams ermöglich die folgenden strategischen Geschäftsszenarien für Microsoft 365 Enterprise:

- Kommunikation mit Ihrem Team, um auf den Laufenden zu bleiben, Feedback anzufordern, den Zusammenhalt zu stärken und einen Konsens zu erreichen
- Einbinden der Mitarbeiter in Service und Produktion zur Förderung der digitalen Transformation
- Verstehen Ihrer Arbeitsgewohnheiten zur Verbesserung Ihres Einflusses und Ihres Eindrucks

Weitere Informationen finden Sie unter [Digitale Transformation mit Microsoft 365](http://transform.microsoft.com). 

#### <a name="microsoft-teams-for-highly-regulated-data"></a>Microsoft Teams für Daten mit strengen Sicherheitsbestimmungen

Daten mit strengen Sicherheitsbestimmungen unterliegen regionalen Vorschriften oder sind die wertvollsten Daten für Ihre Organisation, z. B. Geschäftsgeheimnisse, Finanz- oder Personaldaten und Unternehmensstrategie. Sie können ein Team für eingeschränkten Zugriff, Datenklassifizierung, Schutz vor Datenverlust und Verschlüsselung für diese Art von Daten konfigurieren. Einzelheiten hierzu finden Sie unter [Microsoft Teams- und SharePoint Online-Websites für Daten mit strengen Sicherheitsbestimmungen](teams-sharepoint-online-sites-highly-regulated-data.md).

#### <a name="result"></a>Ergebnis

Eine Liste von Teams-Szenarios, die sich mit den Anforderungen Ihrer Organisation im Hinblick auf Zusammenarbeit und Gruppenarbeit befassen.

## <a name="phase-2-onboard"></a>Phase 2: Onboarding

In dieser Phase werden die technischen Aspekte einer Teams-Bereitstellung geplant, und es wird mit der Einführung von Teams für ausgewählte Benutzergruppen begonnen.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Voraussetzungen: Konfigurationen für den Identitäts- und Gerätezugriff

Um den Zugriff auf die Teams zu schützen, stellen Sie sicher, dass Sie [Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md) und die [empfohlenen SharePoint Online-Zugriffsrichtlinien](sharepoint-file-access-policies.md) konfiguriert haben.

### <a name="step-1-complete-your-technical-planning"></a>Schritt 1: Abschließen der technischen Planung

Bevor Sie mit der technischen Planung beginnen, sollten Sie festlegen, ob Sie FastTrack verwenden möchten. Wenn Ihre Organisation über mehr als 50 Arbeitsplätze verfügt und Teil eines [qualifizierenden Programms](https://technet.microsoft.com/library/dn783224.aspx) ist, können Sie das [FastTrack-Programm für Microsoft 365](https://fasttrack.microsoft.com/microsoft365) nutzen, das ohne zusätzliche Kosten zur Verfügung steht und Sie durch die Planung, Bereitstellung und Diensteinführung führt. Sie können diese Aufgaben auch selbst mithilfe unserer FastTrack-Onboarding-Assistenten ausführen, die unter [FastTrack](https://fasttrack.microsoft.com/) verfügbar sind, nachdem Sie sich mit Ihrem Office 365-Konto angemeldet haben.

Wenn Sie Ihre eigene Planung (oder in Verbindung mit FastTrack) vornehmen, müssen Sie ermitteln, ob Ihr Netzwerk und Ihre Organisation für Teams bereit sind. Sie müssen unbedingt die Beendigungskriterien für Netzwerke in Ihrer [Fundamentinfrastruktur](deploy-foundation-infrastructure.md) erfüllen. Besonderes Augenmerk liegt dabei auf der Bandbreite, dem Durchsatz und Datenverkehrverzögerungen zur Maximierung der Leistung für Teams-basierte Besprechungen.

Verwenden Sie die folgenden Ressourcen, um die technischen Aspekte Ihrer Organisation für eine Teams-Einführung vorzubereiten: 

- [Überprüfen der Bereitschaft Ihrer Umgebung für Teams](https://docs.microsoft.com/MicrosoftTeams/environment-readiness)
- [Vorbereiten Ihres Netzwerks für Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)
- [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

Um ein besseres Verständnis der Sicherheit in Teams zu erlangen, sehen Sie sich die folgenden zusätzlichen Ressourcen an:

- [Überblick über Sicherheit und Compliance in Teams](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview)
- [Office 365-Gruppen und Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)
- [Gastzugriff in Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)

Verwenden Sie diese Ressourcen dann, um die Teams-Lizenzierung zu verstehen und Teams für Ihre Organisation einzurichten:

- [Office 365-Lizenzierung für Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)
- [Verwalten des Benutzerzugriffs auf Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/user-access)
- [Clients für Microsoft Teams abrufen](https://docs.microsoft.com/MicrosoftTeams/get-clients)
- [Aktivieren von Microsoft Teams in Ihrer Office 365-Organisation](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up)
- [Verwalten von Microsoft Teams-Features in Ihrer Office 365-Organisation](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365)

#### <a name="result"></a>Ergebnis

Netzwerk und Sicherheit sind bereit, und die Office 365-Lizenzierungsplanung ist abgeschlossen. Sie können Teams nur für ausgewählte Gruppen in Ihrer Organisation einführen.

### <a name="step-2-run-an-it-pilot"></a>Schritt 2: Ausführen eines IT-Pilotprojekts

In den meisten mittelständischen und großen Unternehmen bietet es sich an, ein IT-Pilotprojekt mit den Projektbeteiligten aus Phase 1, Erstanwendern und Technikliebhabern durchzuführen.

- Wählen Sie ein Teams-Geschäftsszenario aus, an dem die Teilnehmer des IT-Pilotprojekts üben können. Ideen finden Sie unter [Microsoft Teams-Kit für erste Schritte](http://microsoft.com/download/56505).
- Geben Sie den Teilnehmern an der Pilotphase eine Reihe von Übungen, um Teams-basierte Chats, Dateispeicherung, Besprechungen und andere Funktionen zu testen.
- Bestimmen Sie Ihre Änderungsverwaltungsstrategie, und erstellen Sie Materialien, um die organisationsweite Benutzerakzeptanz zu fördern. Änderungen für die Änderungsverwaltung können E-Mail-Ankündigungen, interne Schulungspläne, Plakate und Präsentationen umfassen. Durch diese Materialien wird Ihre Organisation über Teams und seine Vorteile informiert; außerdem wird die Sensibilität und die Nutzung gefördert. Unter [Änderungsverwaltungsstrategie für Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) finden Sie einige Ideen.
- Lassen Sie die Teilnehmer an Ihrem IT-Pilotprojekt die Materialien der Änderungsverwaltungsstrategie basierend auf ihren Erfahrungen überarbeiten. Sie können Tipps zu bewährten Methoden und Ratschläge dazu geben, wie die Vorteile von Teams und dessen Einsatz für Zusammenarbeit und Gruppenarbeit am besten beschrieben werden können.

#### <a name="result"></a>Ergebnis

Ihr Teams-IT-Pilot ist abgeschlossen, und die Materialien für die Änderungsverwaltung wurden entwickelt, überprüft und optimiert.

### <a name="step-3-roll-out-to-a-business-group"></a>Schritt 3: Einführung in eine Unternehmensgruppe

Nach Abschluss des IT-Pilotprojekts führen Sie Teams in einer Unternehmensgruppe oder Abteilung in Ihrer Organisation ein. Diese Einführung umfasst Folgendes:

- Identifizierung von wichtigen Geschäftsszenarien für Teams innerhalb der Unternehmensgruppe.
- Ankündigungsaktivitäten, um Benutzer über die Erwartungen und Zeitpläne für die Teams-Nutzung für Abteilungen sowie Arbeits- und Projektteams zu informieren.
- Direkte Benutzerschulung zu Teams oder Links zu Ressourcen zur Einführung von Teams und dessen Verwendung.
- Ein Feedbackmechanismus, z. B. ein zentrales Team, das alle Personen in der Unternehmensgruppe enthält, um Kommentare und Probleme von Benutzern in der Unternehmensgruppe zu sammeln.

Während der Einführung können Sie Ihre Änderungsverwaltungsmaterialien in Vorbereitung auf die organisationsweite Einführung optimieren.

#### <a name="result"></a>Ergebnis

Eine Unternehmensgruppe verwendet Teams, und die Änderungsverwaltungsmaterialien wurden getestet und optimiert.

## <a name="phase-3-drive-value"></a>Phase 3: Wertschöpfung

In dieser Phase wird die Einführung von Teams in Ihrer Organisation abgeschlossen, und Benutzer werden so unterstützt, dass sie dessen Vorteile sehen können.

### <a name="step-1-roll-out-teams-to-the-rest-of-your-organization"></a>Schritt 1: Einführung von Teams in der restlichen Organisation

Nachdem Sie die Einführung für eine gezielte Unternehmensgruppe abgeschlossen haben, wird Teams für den Rest der Organisation eingeführt. Diese Einführung umfasst Folgendes:

- Identifizierung wichtiger Geschäftsszenarien für Teams innerhalb der unterschiedlichen Unternehmensgruppen.
- Verwendung der optimierten Änderungsverwaltungsmaterialien für Ankündigungsaktivitäten, um Ihre Organisation über die Erwartungen und Zeitpläne für die Teams-Nutzung für Abteilungen sowie Arbeits- und Projektteams zu informieren.
- Bereitstellung von Benutzerschulungen zu Teams oder Links zu Ressourcen zur Einführung von Teams und dessen Verwendung. Sehen Sie sich die Schulungsressourcen unter [Endbenutzerschulung für Microsoft Teams](https://docs.microsoft.com/microsoftteams/enduser-training) an.
- Ein Feedbackmechanismus, z. B. ein zentrales Team, das alle Personen in der Unternehmensgruppe enthält, um Kommentare und Probleme von Benutzern in der Organisation zu sammeln und darauf zu reagieren. Wenn Ihre Organisation weniger als 2500 Einzelpersonen umfasst, verwenden Sie einen öffentlichen Kanal in Teams. Andernfalls verwenden Sie eine öffentliche Gruppe in Yammer.

#### <a name="result"></a>Ergebnis

Teams wurde in Ihrer Organisation eingeführt und läuft, und Ihre Strategie für die Änderungsverwaltung wird verwendet, um Benutzer zu informieren, zu schulen und ihnen die Möglichkeit zu geben, mit der Verwendung von Teams zu beginnen.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Schritt 2: Messen der Nutzung, Verwalten der Zufriedenheit und Fördern der Akzeptanz

Nachdem Teams in der gesamten Organisation eingeführt wurde, müssen Sie Ihre Strategie für die Änderungsverwaltung weiterhin verwenden, um:

- Dafür zu sorgen, dass Ihre Führungskräfte Teams als Tool für Zusammenarbeit und Gruppenarbeit für die Organisation vorantreiben.
- Einzelpersonen anzuregen, Teams für die Kommunikation und Zusammenarbeit in der Unternehmensgruppe, der Abteilung sowie im Arbeits- und Projektteam zu nutzen.

Nachfolgend finden Sie einige Vorschläge:

- Weitere Informationen zu allgemeinen bewährten Methoden für die Einführung von Clouddiensten finden Sie im [Office 365-Einführungsleitfaden](https://aka.ms/successfactors). 
- Informationen zur Office 365-Dienstnutzung in Ihrer Organisation finden Sie unter [Office 365-Aktivitätsberichte](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263). Wenn Sie kein globaler Administrator für Office 365 für Ihre Organisation sind, bitten Sie eine Person, die globaler Administrator ist, Ihrem Benutzerkonto Berichteleserberechtigungen zu gewähren, damit Sie auf Aktivitätsberichte zugreifen können.
- Überwachen Sie das Feedback (einen öffentlichen Kanal in einem zentralen Team oder Yammer) auf Probleme oder Feedback von Personen im Zusammenhang mit ihrer Erfahrung mit Teams. Reagieren Sie so schnell wie möglich auf Fragen und Probleme, um Frustrationen zu verhindern, die dazu führen können, dass sich Benutzer von Teams abwenden.
- Identifizieren und schulen Sie Ihre Experten in jeder Unternehmensgruppe, und heben Sie deren Leistungen und bewährte Methoden bei der Verwendung von Teams hervor. Reflektieren Sie diese Erfolgserlebnisse für die Organisation, um Projekterfolge und Akzeptanz aufzuzeigen. Eine Bestätigung von technischen Experten in einer Unternehmensgruppe kann einen wesentlichen Einfluss auf Führungskräfte und Mitarbeiter ausüben.

#### <a name="result"></a>Ergebnis

Ihre Organisation hat Teams als Tool für die Zusammenarbeit und die Gruppenarbeit übernommen.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Erhalten Sie einen Einblick in die Arbeit von Microsoft, und erfahren Sie, wie das Unternehmen Microsoft Teams für die Zusammenarbeit bereitstellte und verwendet, indem Sie die folgenden Artikel lesen:

- [Bereitstellung von Microsoft Teams optimiert die Zusammenarbeit optimiert und verbessert die Zusammenarbeit](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [Microsoft Teams fördert die Zusammenarbeit am modernen Arbeitsplatz bei Microsoft](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

## <a name="next-steps"></a>Nächste Schritte

- [Verwalten von Microsoft Teams-Features in Ihrer Office 365-Organisation](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [Administratorschulung für Microsoft Teams](https://docs.microsoft.com/microsoftteams/itadmin-readiness)
