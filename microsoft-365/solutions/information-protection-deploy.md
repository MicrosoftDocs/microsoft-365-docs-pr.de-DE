---
title: Bereitstellen des Informationsschutzes für Datenschutzbestimmungen mit Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Konfigurieren Sie die Sicherheits-und Dienstinfrastruktur, um Ihre Informationen zu schützen und Datenschutzbestimmungen einzuhalten.
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695108"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Bereitstellen des Informationsschutzes für Datenschutzbestimmungen mit Microsoft 365

Diese Lösung enthält Anleitungen für die Planung und den Schutz personenbezogener Daten, die in Microsoft 365-Diensten gespeichert sind und möglicherweise Datenschutzbestimmungen unterliegen, beispielsweise die allgemeine Datenschutzverordnung (dsgvo) der Europäischen Union. Diese Lösung konzentriert sich auf die anwendbaren Features von Microsoft Information Protection und Compliance, die Microsoft-Konformitätsbewertung und die Bewertungstools, die Ihnen dabei helfen, Ihre Daten zu kennen. 
 
Weitere Informationen finden Sie auch im Hinblick auf die Verwendung von Microsoft-Identitäts-, Geräte-und Bedrohungsschutz-Steuerelementen für Ihre Datenschutzanforderungen sowie Daten Ermittlungs-und-Antwort Tools. 

## <a name="organization-of-this-guidance-material"></a>Organisation dieses Anleitungs Materials

Damit Sie sich mit den Microsoft 365-Tools vertraut machen können, die zum identifizieren, verwalten, Steuern und Überwachen von personenbezogenen Daten unter einer oder mehreren datenschutzbezogenen Bestimmungen verfügbar sind, sind diese Anleitungen in Abschnitten gegliedert.
 
![Bereitstellen des Informationsschutzes für Datenschutzbestimmungen](../media/information-protection-deploy/information-protection-deploy-grid.png)

Jeder dieser Abschnitte entspricht einem separaten Artikel in dieser Lösung.

>[!Note]
>Wenn Sie bereits mit ihren Datenschutzverpflichtungen vertraut sind und gegen einen vorhandenen Plan ausgeführt werden, können Sie sich auf die Anleitungen zum verhindern, schützen, beibehalten und untersuchen konzentrieren.

>[!Important]
>Wenn Sie diese Anleitung befolgen, müssen Sie nicht unbedingt mit den Datenschutzbestimmungen konform sein, insbesondere im Hinblick auf die Anzahl der erforderlichen Schritte, die außerhalb des Kontexts der Features liegen. Sie sind dafür verantwortlich, dass Sie Ihre Einhaltung sicherstellen und ihre Rechts-und Compliance-Teams konsultieren oder sich von Drittanbietern beraten lassen, die sich auf die Einhaltung von Richtlinien spezialisieren.
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Plan: Bewerten der Datenschutzrisiken und identifizieren vertraulicher Elemente 

Die Bewertung der Datenschutzbestimmungen und der Risiken, denen Ihre Organisation unterliegt, ist ein wichtiger erster Schritt, bevor Sie mit der Implementierung von Verbesserungen beginnen, einschließlich der durch die Konfiguration von Microsoft 365 erreichbaren. Dies kann eine allgemeine Eignungsbewertung oder die Identifizierung bestimmter vertraulicher Informationstypen sein, die den von Ihrer Organisation einzuhaltenden behördlichen Kontrollen unterliegen, sowie deren Auftreten in Ihrer Microsoft 365-Umgebung.

Weitere Informationen finden Sie unter [bewerten von Datenschutzrisiken und identifizieren vertraulicher Elemente](information-protection-deploy-assess.md).

## <a name="track-use-compliance-score-and-compliance-manager"></a>Track: Use Compliance Score and Compliance Manager 

Compliance-Score und Compliance-Manager bieten eine integrierte Reihe von Tools, die im Microsoft 365 Compliance Admin Center und in Services Trust Portal zur Verfügung stehen. Gemeinsam bieten Ihnen diese Tools eine integrierte Möglichkeit zum Nachverfolgen und Verwalten von Verbesserungs Aktionen insgesamt sowie in Bezug auf mehrere Datenschutzbestimmungen, denen Sie unterliegen.

Mit den Tools können Sie auch integrierte Bewertungs Vorlagen verwenden, die für jede Verordnung spezifisch sind, wobei Sie Aktionselemente für jede ausgewählte Bewertungs Vorlage nachverfolgen sowie bestimmte regulatorische Steuerelemente anzeigen und diese mit bestimmten Aktionen verknüpfen können.

Weitere Informationen finden Sie unter [use Compliance Score and Compliance Manager zur Verwaltung von Verbesserungs Aktionen](information-protection-deploy-compliance.md).

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Verhindern: Verwenden von Identitäts-, Geräte-und Bedrohungsschutz für die Datenschutzverordnung

Microsoft 365 bietet eine Reihe von Identitäts-, Geräte-und Bedrohungsschutz Funktionen, mit denen Sie die Einhaltung von Datenschutzbestimmungen in Einklang bringen können. 

Weitere Informationen finden Sie unter [Verwenden von Identität, Gerät und Bedrohungsschutz für die Datenschutzverordnung](information-protection-deploy-identity-device-threat.md).

In diesem Artikel wird kurz beschrieben, was die Datenschutzbestimmungen in diesen Bereichen allgemein betreffen, und enthält eine Liste der zugehörigen Microsoft 365-Lösungen mit Links zu weiteren Informationen, die Sie bei der Erfüllung von Implementierungsanforderungen unterstützen. 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>Schützen von Informationen unterliegen der Datenschutzverordnung

Die Datenschutzbestimmungen diktieren eine Reihe von Steuerelementen für den Schutz personenbezogener Daten, die in Ihrer Umgebung eingesetzt werden können, einschließlich mehr als 40 Schutz von Informations Steuerelementen in den vier Datenschutzbestimmungen in unserem Beispielsatz von dsgvo, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States Health Care Privacy Act) und dem Brazil Data Protection Act (LGPD).

Weitere Informationen finden Sie unter [Schützen von Informationen unterliegender Datenschutzbestimmungen in Ihrer Organisation](information-protection-deploy-protect-information.md).

In diesem Artikel werden die wichtigsten steuerungsschemas erläutert, die für die Adressierung von Informationsschutz Anforderungen für den Datenschutz in Ihrer Organisation verwendet werden können.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Beibehalten: Informationen zur Datenschutzrichtlinie unterliegen Regeln

Datenschutzbestimmungen rufen Sie die Steuerelemente für die Steuerung personenbezogener Informationen, die in Ihrer Umgebung eingesetzt werden können, einschließlich mehr als vierundzwanzig Steuerelemente in den vier Datenschutzbestimmungen in unserem Beispielsatz von dsgvo, CCPA, HIPAA-HITECH und LGPD auf.

Weitere Informationen finden Sie unter [Steuern von Informationen unterliegen der Datenschutzbestimmungen in Ihrer Organisation](information-protection-deploy-govern.md).

Während die Datenschutzbestimmungen vage hinsichtlich der Informationssteuerung sein können &mdash; , wie zum Beispiel gezielte Aufbewahrung, Löschung und Archivierung, werden &mdash; in diesem Artikel die primären steuerungsschemas erläutert, die Sie für den Datenschutz in Ihrer Organisation mit den Anforderungen an die Informationssteuerung verwenden können.

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a>Untersuchen: überwachen und reagieren unterliegender Datenschutzverordnung

Es stehen Microsoft 365-Features zur Verfügung, die Sie bei der Überprüfung, Untersuchung und Reaktion auf Datenschutz Vorfälle in Ihrer Organisation unterstützen, wenn Sie verwandte Funktionen nutzen. 

Es kann wichtig sein, Prozesse, Verfahren und andere Dokumentationen für diese zu untersuchen, um die Einhaltung von Regulierungsstellen zu demonstrieren.

Weitere Informationen finden Sie unter [überwachen und reagieren auf Datenschutz Vorfälle in Ihrer Organisation](information-protection-deploy-monitor-respond.md).
