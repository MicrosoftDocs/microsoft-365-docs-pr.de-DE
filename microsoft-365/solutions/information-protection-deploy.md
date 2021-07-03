---
title: Bereitstellen des Informationsschutzes für Datenschutzbestimmungen mit Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: Konfigurieren Sie den Informationsschutz in Microsoft 365 für Datenschutzbestimmungen wie die DSGVO und den California Consumer Privacy Act (CCPA), einschließlich Microsoft Teams, SharePoint und E-Mails.
ms.openlocfilehash: c0ffe7cf850ec6e7ae8c974f983ce43668bf6f30
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287711"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Bereitstellen des Informationsschutzes für Datenschutzbestimmungen mit Microsoft 365

Ihre Organisation unterliegt möglicherweise regionalen Datenschutzbestimmungen, die sie zum Schutz, zur Verwaltung und zur Bereitstellung von Rechten und zur Kontrolle über personenbezogene Informationen, die in Ihrer IT-Infrastruktur gespeichert sind, einschließlich lokaler und in der Cloud, erfordern. Das beste Beispiel für eine Datenschutz-Verordnung ist die Datenschutz-Grundverordnung (DSGVO) der Europäischen Union. Wenn die Datenschutzbestimmungen nicht eingehalten werden, kann dies zu erheblichen Bußgeldern führen.

Beispiele für die Datentypen in Microsoft 365 sind Chatsitzungen in Microsoft Teams, E-Mails in Exchange und Dateien in SharePoint und OneDrive. Diese Lösung enthält Anleitungen zum Bewerten von Risiken und zum Ergreifen geeigneter Maßnahmen zum Schutz personenbezogener Daten in Microsoft 365. Dazu gehört die Identifizierung persönlicher Informationen, damit Sie Datenschutzvorfälle schützen, steuern und darauf reagieren können.

![Was ist Informationsschutz für Datenschutzbestimmungen?](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png#lightbox)

Darüber hinaus werden zusätzliche Informationen zur Verwendung Microsoft 365 Identitäts-, Geräte- und Bedrohungsschutz-Steuerelemente für Ihre Datenschutzanforderungen bereitgestellt.

Schauen Sie sich dieses Video an, um einen Überblick über den Bereitstellungsprozess zu erhalten.
<br>
<br>
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4NHCQ]

Diese Microsoft 365 Funktionen und Features helfen Ihnen, die Kriterien für den Schutz von Informationen zu erfüllen.

| Funktion oder Feature | Beschreibung | Lizenzierung |
|:-------|:-----|:-------|
| Compliance-Manager | Verwalten Sie Aktivitäten zur Einhaltung gesetzlicher Vorschriften, erhalten Sie eine Gesamtbewertung Ihrer aktuellen Compliancekonfiguration und finden Sie Verbesserungsempfehlungen. Dies ist ein workflowbasiertes Tool zur Risikobewertung im Microsoft 365 Compliance Center. | Microsoft 365 E3 und E5 |
| Microsoft Defender für Office 365 | Schützen Sie Ihre Microsoft 365-Apps und-Daten vor Angriffen, beispielsweise E-Mails, Office-Dokumente und Tools für die Zusammenarbeit. | Microsoft 365 E3 und E5 |
| Vertraulichkeitsbezeichnungen | Klassifizieren und schützen Sie die Daten Ihrer Organisation, ohne die Produktivität der Benutzer und ihre Fähigkeit zur Zusammenarbeit zu beeinträchtigen. Platzieren Sie Bezeichnungen mit verschiedenen Schutzebenen für E-Mails, Dateien oder Websites. | Microsoft 365 E3 und E5 |
| Schutz vor Datenverlust (DLP) | Erkennen, Warnen und Blockieren riskanter, unbeabsichtigter oder unangemessener Freigabe von Daten, die persönliche Informationen enthalten, sowohl intern als auch extern. | Microsoft 365 E3 und E5 |
| Aufbewahrungsbezeichnungen und Bezeichnungsrichtlinien | Implementieren von Informationsgovernance-Steuerelementen. Dazu kann es gehören, zu bestimmen, wie lange Daten (z. B. personenbezogene Daten im Zusammenhang mit Kunden) zur Einhaltung der Richtlinien oder Datenbestimmungen Ihrer Organisation beibehalten werden. | Microsoft 365 E3 und E5 |
| E-Mail-Verschlüsselung | Schützen Sie personenbezogene Daten, indem Sie verschlüsselte E-Mail-Nachrichten zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen. | Microsoft 365 E3 und E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>Organisation der Anleitungen in dieser Lösung

Um die Microsoft 365 verfügbaren Tools zu verstehen, mit denen Sie eine oder mehrere Datenschutzbestimmungen erfüllen können, ist diese Anleitung in Abschnitte unterteilt.

![Schritte zur Implementierung des Informationsschutzes für Datenschutzbestimmungen](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

Jeder dieser Abschnitte entspricht einem separaten Artikel in dieser Lösung.

> [!NOTE]
> Wenn Sie bereits mit Ihren Datenschutzverpflichtungen vertraut sind und mit einem vorhandenen Plan ausgeführt werden, sollten Sie sich auf die Anleitung zum Verhindern, Schützen, Aufbewahren und Untersuchen konzentrieren.

> [!IMPORTANT]
> Wenn Sie diese Anleitung befolgen, werden Sie nicht unbedingt mit datenschutzbestimmungen konform sein, insbesondere in Bezug auf die Anzahl der erforderlichen Schritte, die sich außerhalb des Kontexts der Features befinden. Sie sind dafür verantwortlich, Ihre Compliance sicherzustellen und Sich an Ihre Rechts- und Complianceteams zu wenden oder sich von Drittanbietern, die sich auf Compliance spezialisiert haben, zu beraten.

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Plan: Bewerten von Datenschutzrisiken und Identifizieren vertraulicher Elemente

Die Bewertung von Datenschutzbestimmungen und Risiken, denen Ihre Organisation unterliegt, ist ein wichtiger erster Schritt, bevor Sie mit der Implementierung von Verbesserungen beginnen, einschließlich der Konfiguration von Funktionen in Microsoft 365. Diese Arbeit kann eine allgemeine Bereitschaftsbewertung oder Identifizierung bestimmter vertraulicher Informationstypen umfassen, die gesetzlichen Kontrollen unterliegen, die Ihre Organisation einhalten muss.

Weitere Informationen finden Sie unter [Bewerten von Datenschutzrisiken und Identifizieren vertraulicher Elemente.](information-protection-deploy-assess.md)

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>Nachverfolgen: Durchführen von Risikobewertungen und Überprüfen Ihrer Compliancebewertung

Compliance-Manager, der im Microsoft 365 Compliance Center verfügbar ist, bietet Ihnen eine integrierte Möglichkeit, Verbesserungsmaßnahmen insgesamt sowie diejenigen im Zusammenhang mit mehreren Datenschutzbestimmungen, die für Sie gelten, nachzuverfolgen und zu verwalten.

Sie können integrierte, für jede Verordnung spezifische Bewertungsvorlagen verwenden, in denen Sie Aktionselemente für jede ausgewählte Bewertungsvorlage nachverfolgen sowie bestimmte regulatorische Kontrollen anzeigen und diese mit bestimmten Aktionen in Beziehung setzen können.

Weitere Informationen finden Sie unter [Verwenden des Compliance-Managers zum Verwalten von Verbesserungsmaßnahmen.](information-protection-deploy-compliance.md)

## <a name="prevent-protect-personal-data"></a>Verhindern: Schützen von personenbezogenen Daten

Microsoft 365 bietet Identitäts-, Geräte- und Bedrohungsschutzfunktionen, die Sie verwenden können, um die Einhaltung gesetzlicher Vorschriften für den Datenschutz zu gewährleisten.

Weitere Informationen finden Sie unter [Verwenden von Identität, Gerät und Bedrohungsschutz für Datenschutzbestimmungen.](information-protection-deploy-identity-device-threat.md)

Dieser Artikel beschreibt kurz, was die Datenschutzbestimmungen in diesen Bereichen im Allgemeinen fordern, und enthält eine Liste verwandter Microsoft 365 Lösungen mit Links zu weiteren Informationen, die Ihnen bei der Erfüllung von Implementierungsanforderungen helfen.

## <a name="protect-information-subject-to-data-privacy-regulation"></a>Schützen von Informationen, die der Datenschutzbestimmungen unterliegen

Datenschutzbestimmungen bestimmen eine Reihe von Steuerelementen zum Schutz personenbezogener Informationen, die in Ihrer Umgebung eingesetzt werden können, einschließlich mehr als 40 Kontrollen zum Schutz von Informationen über nur die vier Datenschutzbestimmungen in unseren Beispielen DSGVO, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States Health Care Privacy Act) und dem Brazil Data Protection Act (LGPD).

Weitere Informationen finden Sie unter ["Schützen von Informationen, die den Datenschutzbestimmungen in Ihrer Organisation unterliegen".](information-protection-deploy-protect-information.md)

In diesem Artikel werden die wichtigsten Steuerungsschemas beschrieben, die zum Erfüllen von Informationsschutzanforderungen für den Datenschutz in Ihrer Organisation verwendet werden können.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Aufbewahren: Regeln von Informationen, die der Datenschutzbestimmungen unterliegen

Datenschutzbestimmungen fordern Steuerelemente für die Governance personenbezogener Informationen, die in Ihrer Umgebung eingesetzt werden können, einschließlich mehr als 24 Kontrollen in den vier Datenschutzbestimmungen in unserem Beispielsatz von DSGVO, CCPA, HIPAA-HITECH und LGPD.

Weitere Informationen finden Sie unter ["Verwalten von Informationen, die den Datenschutzbestimmungen in Ihrer Organisation unterliegen".](information-protection-deploy-govern.md)

Während die Datenschutzbestimmungen hinsichtlich der Informationsgovernance, wie z. B. die absichtliche Aufbewahrung, Löschung und Archivierung, verwendbar sein &mdash; können, &mdash; werden in diesem Artikel die primären Kontrollschemas beschrieben, die Sie verwenden können, um die Anforderungen der Informationsgovernance für den Datenschutz in Ihrer Organisation zu erfüllen.

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>Untersuchen: Überwachen, Untersuchen und Reagieren auf Datenschutzvorfälle

Es stehen Microsoft 365 Features zur Verfügung, mit denen Sie Datenschutzvorfälle in Ihrer Organisation überwachen, untersuchen und darauf reagieren können, während Sie verwandte Funktionen operationalisieren.

Prozesse, Verfahren und andere Dokumentationen für die Verwendung dieser Features können wichtig sein, um die Einhaltung von Vorschriften nachzuweisen.

Weitere Informationen finden Sie unter [Überwachen und Reagieren auf Datenschutzvorfälle in Ihrer Organisation.](information-protection-deploy-monitor-respond.md)

## <a name="training-for-administrators"></a>Schulung für Administratoren

Diese Schulungsmodule von Microsoft Learn helfen Ihnen dabei, zu erfahren, welche Funktionen für den Informationsschutz wichtig sind.


#### <a name="information-protection"></a>Information Protection

|Ausbildung:|Schützen von Unternehmensinformationen mit Microsoft 365|
|:---|:---|
|![Schulungssymbol für Teams Infoschutz](../media/protect-enterprise-information-microsoft-365.svg)|Es ist schwieriger als je zuvor, die Informationen Ihrer Organisation zu schützen und zu sichern. Im Lernpfad Schützen von Unternehmensinformationen mit Microsoft 365 wird erläutert, wie Sie Ihre vertraulichen Informationen vor versehentlichem Teilen oder Missbrauch schützen, wie Sie Daten erkennen und klassifizieren, wie Sie sie mit Vertraulichkeitsbezeichnungen schützen können und wie Sie vertrauliche Informationen überwachen und analysieren können, um sich gegen den Verlust dieser Daten zu schützen. Dieser Lernpfad kann Ihnen helfen, sich auf die Zertifizierungen Microsoft 365 Certified: Security Administrator Associate und Microsoft 365 Certified: Enterprise Administration Expert vorzubereiten.<br><br>1 Std. – Learning Pfad – 5 Module|

> [!div class="nextstepaction"]
> [Starten >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>Identität und Zugriff

|Ausbildung:|Identität schützen und Zugriff mit Azure Active Directory|
|:---|:---|
|![Identitäts- und Zugriffsschulungssymbol](../media/protect-identity-and-access-with-microsoft-365.svg)|Der Lernpfad Identität und Zugriff umfasst die neuesten Identitäts- und Zugriffstechnologien, Tools zur Stärkung der Authentifizierung und Anleitungen zum Identitätsschutz in Ihrer Organisation. Die Zugriffs- und Identitätstechnologien von Microsoft ermöglichen es Ihnen, die Identität Ihrer Organisation zu schützen, ob vor Ort oder in der Cloud, und ermöglichen es Ihren Benutzern, von jedem Standort aus sicher zu arbeiten. Dieser Lernpfad kann Ihnen bei der Vorbereitung für die Microsoft 365-Zertifizierung: Security Administrator Associate und Microsoft 365 Zertifizierung: Enterprise Administration Expert helfen.<br><br>2 Std. 52 Min. – Learning Pfad – 6 Module|

> [!div class="nextstepaction"]
> [Starten >](/learn/modules/m365-identity-overview/introduction/)