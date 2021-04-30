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
description: Konfigurieren des Informationsschutzes in Microsoft 365 datenschutzbestimmungen wie der DSGVO und dem California Consumer Privacy Act (CCPA), einschließlich Microsoft Teams, SharePoint und E-Mail.
ms.openlocfilehash: cae3a559c2bce39ecb02afa9be0878ff5e19ba48
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100771"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Bereitstellen des Informationsschutzes für Datenschutzbestimmungen mit Microsoft 365

Ihre Organisation unterliegt möglicherweise regionalen Datenschutzbestimmungen, nach denen Sie Rechte und Kontrolle über in Ihrer IT-Infrastruktur gespeicherte persönliche Informationen, einschließlich lokal und in der Cloud, schützen, verwalten und bereitstellen müssen. Das beste Beispiel für eine Datenschutzverordnung ist die Datenschutz-Grundverordnung (DSGVO) der Europäischen Union. Die Nichteinhaltung von Datenschutzbestimmungen kann zu erheblichen Bußgeldern führen.

Beispiele für die Typen von Daten in Microsoft 365 sind Chatsitzungen in Microsoft Teams, E-Mails in Exchange und Dateien in SharePoint und OneDrive. Diese Lösung bietet Anleitungen zum Bewerten von Risiken und zum Ergreifen geeigneter Maßnahmen zum Schutz personenbezogener Daten in Microsoft 365. Dazu gehört das Identifizieren personenbezogener Informationen, damit Sie Datenschutzvorfälle schützen, steuern und darauf reagieren können.

![Was ist Informationsschutz für Datenschutzbestimmungen?](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png#lightbox)

Darüber hinaus werden zusätzliche Informationen zur Verwendung von Microsoft 365, Geräten und Bedrohungsschutzkontrollen für Ihre Datenschutzanforderungen bereitgestellt. 

Diese Microsoft 365 und Features helfen Ihnen, die Kriterien für den Schutz von Informationen zu erfüllen.

| Funktion oder Feature | Beschreibung | Lizenzierung |
|:-------|:-----|:-------|
| Compliance-Manager | Verwalten Sie Aktivitäten zur Einhaltung gesetzlicher Vorschriften, erhalten Sie eine Gesamtpunktzahl Ihrer aktuellen Compliancekonfiguration und finden Sie Empfehlungen zur Verbesserung. Dies ist ein workflowbasiertes Risikobewertungstool im Microsoft 365 Compliance Center. | Microsoft 365 E3 und E5 |
| Microsoft Defender für Office 365 | Schützen Sie Ihre Microsoft 365-Apps und-Daten vor Angriffen, beispielsweise E-Mails, Office-Dokumente und Tools für die Zusammenarbeit. | Microsoft 365 E3 und E5 | 
| Vertraulichkeitsbezeichnungen | Klassifizieren und schützen Sie die Daten Ihrer Organisation, ohne die Produktivität der Benutzer und ihre Fähigkeit zur Zusammenarbeit zu beeinträchtigen. Platzieren Sie Bezeichnungen mit verschiedenen Schutzebenen für E-Mails, Dateien oder Websites. | Microsoft 365 E3 und E5 |
| Schutz vor Datenverlust (DLP) | Erkennen, warnen und blockieren Sie riskante, unbeabsichtigte oder unangemessene Freigabe von Daten, die persönliche Informationen enthalten, sowohl intern als auch extern. | Microsoft 365 E3 und E5 | 
| Aufbewahrungsbezeichnungen und Bezeichnungsrichtlinien | Implementieren von Steuerungssteuerelementen für die Informationsverwaltung. Dazu kann auch die Bestimmung gehören, wie lange Daten (z. B. personenbezogene Daten im Zusammenhang mit Kunden) gespeichert werden müssen, um die Richtlinien oder Datenbestimmungen Ihrer Organisation einzuhalten. | Microsoft 365 E3 und E5 |
| E-Mail-Verschlüsselung | Schützen Sie personenbezogene Daten, indem Sie verschlüsselte E-Mail-Nachrichten zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen. | Microsoft 365 E3 und E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>Organisation der Anleitungen in dieser Lösung

Damit Sie die verfügbaren tools Microsoft 365, die Ihnen bei der Erfüllung einer oder mehreren datenschutzbezogenen Bestimmungen helfen, sind diese Anleitungen in Abschnitte unterteilt.
 
![Schritte zum Implementieren des Informationsschutzes für Datenschutzbestimmungen](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

Jeder dieser Abschnitte entspricht einem separaten Artikel in dieser Lösung.

>[!Note]
>Wenn Sie bereits mit Ihren Datenschutzverpflichtungen vertraut sind und gegen einen vorhandenen Plan ausgeführt werden, sollten Sie sich auf die Richtlinien Prevent, Protect, Retain und Investigate konzentrieren.

>[!Important]
>Die Einhaltung dieser Anleitungen führt nicht unbedingt dazu, dass Sie mit einer Datenschutzverordnung konform sind, insbesondere unter Berücksichtigung der Anzahl der erforderlichen Schritte, die außerhalb des Kontexts der Features liegen. Sie sind dafür verantwortlich, Ihre Compliance sicherzustellen und Ihre Rechts- und Complianceteams zu konsultieren oder Sichten und Rat von Dritten zu erkundigen, die sich auf Compliance spezialisieren.
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Plan: Bewerten von Datenschutzrisiken und Identifizieren vertraulicher Elemente

Die Bewertung von Datenschutzbestimmungen und Risiken, denen Ihre Organisation unterliegt, ist ein wichtiger erster Schritt, bevor Sie mit der Implementierung von Verbesserungen beginnen, einschließlich der Konfiguration von Funktionen in Microsoft 365. Diese Arbeit kann eine allgemeine Bereitschaftsbewertung oder Identifikation bestimmter vertraulicher Informationstypen umfassen, die behördlichen Kontrollen unterliegen, die Ihre Organisation erfüllen muss.

Weitere Informationen finden Sie unter [Bewerten von Datenschutzrisiken und Identifizieren vertraulicher Elemente.](information-protection-deploy-assess.md)

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>Track: Führen Sie Risikobewertungen aus, und überprüfen Sie Ihre Compliancebewertung.

Der Compliance-Manager, der im Microsoft 365 Compliance Center verfügbar ist, bietet Ihnen die integrierte Möglichkeit, Verbesserungsmaßnahmen insgesamt sowie im Zusammenhang mit mehreren Datenschutzbestimmungen, die für Sie gelten, nachverfolgt und zu verwalten.

Sie können integrierte Bewertungsvorlagen verwenden, die für jede Verordnung spezifisch sind. Hier können Sie Aktionselemente für jede ausgewählte Bewertungsvorlage nachverfolgen sowie bestimmte behördliche Steuerelemente anzeigen und mit bestimmten Aktionen in Beziehung setzen.

Weitere Informationen finden Sie unter [Use Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).

## <a name="prevent-protect-personal-data"></a>Verhindern: Schützen von personenbezogenen Daten

Microsoft 365 bietet Identitäts-, Geräte- und Bedrohungsschutzfunktionen, mit deren Hilfe Sie die Einhaltung gesetzlicher Datenschutzbestimmungen unterstützen können. 

Weitere Informationen finden Sie unter [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).

In diesem Artikel wird kurz beschrieben, was die Datenschutzbestimmungen in diesen Bereichen im Allgemeinen erfordern, und enthält eine Liste verwandter Microsoft 365-Lösungen mit Links zu weiteren Informationen, die Ihnen bei der Lösung aller Implementierungsanforderungen helfen. 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>Datenschutzbestimmungen unterliegende Informationen schützen

Datenschutzbestimmungen diktieren eine Reihe von Kontrollen zum Schutz personenbezogener Informationen, die in Ihrer Umgebung verwendet werden können, einschließlich mehr als 40 Kontrollen zum Schutz von Informationen in nur den vier Datenschutzbestimmungen in unserem Beispielsatz von DSGVO, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States Health Care Privacy Act) und dem Brazil Data Protection Act (LGPD).

Weitere Informationen finden Sie unter [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).

In diesem Artikel werden die wichtigsten Kontrollschemas beschrieben, die für die Behandlung der Anforderungen des Informationsschutzes an den Datenschutz in Ihrer Organisation verwendet werden können.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Aufbewahrung: Regeln von Informationen, die der Datenschutzverordnung unterliegen

Datenschutzbestimmungen fordern Steuerungssteuerelemente für persönliche Informationen, die in Ihrer Umgebung verwendet werden können, einschließlich mehr als 24 Kontrollen in den vier Datenschutzbestimmungen in unserem Beispielsatz von DSGVO, CCPA, HIPAA-HITECH und LGPD.

Weitere Informationen finden Sie unter [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).

Während die Datenschutzbestimmungen im Hinblick auf informationspolitische Steuerung, wie z. B. zwecks Aufbewahrung, Löschung und Archivierung, vage sein können, enthält dieser Artikel die primären Kontrollschemas, die Sie für den Datenschutz in Ihrer Organisation verwenden &mdash; &mdash; können.

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>Untersuchen: Überwachen, Untersuchen und Reagieren auf Datenschutzvorfälle

Es stehen Microsoft 365 zur Verfügung, mit deren Hilfe Sie Datenschutzvorfälle in Ihrer Organisation überwachen, untersuchen und darauf reagieren können, während Sie verwandte Funktionen operationalisieren. 

Prozesse, Verfahren und andere Dokumentationen für die Verwendung dieser Features können wichtig sein, um die Einhaltung von Vorschriften zu demonstrieren.

Weitere Informationen finden Sie unter Überwachen und Reagieren auf Datenschutzvorfälle [in Ihrer Organisation.](information-protection-deploy-monitor-respond.md)
