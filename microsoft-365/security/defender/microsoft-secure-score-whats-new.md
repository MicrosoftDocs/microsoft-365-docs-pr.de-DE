---
title: Neuerungen in der Microsoft-Sicherheitsbewertung
description: Beschreibt, welche neuen Änderungen an der Microsoft-Sicherheitsbewertung im Microsoft 365 Security Center vorgenommen wurden.
keywords: Microsoft-Sicherheitsbewertung, Sicherheitsbewertung, Office 365-Sicherheitsbewertung, Microsoft-Sicherheitsbewertung, Microsoft 365 Security Center
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 2f02de4b738d9d61ef9f98cd03d15bd91709339e
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314428"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Neuerungen in der Microsoft-Sicherheitsbewertung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Damit die Microsoft-Sicherheitsbewertung zu einem besseren Ansprechpartner für Ihren Sicherheitsstatus wird, haben wir einige Änderungen vorgenommen. Wenn Sie mehr über geplante Änderungen wissen möchten, lesen Sie [Bald in der Microsoft-Sicherheitsbewertung verfügbar](microsoft-secure-score-whats-coming.md)

Die Microsoft-Sicherheitsbewertung finden Sie https://security.microsoft.com/securescore im [Microsoft 365 Security Center.](overview-security-center.md)

## <a name="june-2021"></a>Juni 2021

### <a name="remove-improvement-action-related-to-microsoft-cloud-app-security"></a>Entfernen von Verbesserungsmaßnahmen im Zusammenhang mit Microsoft Cloud App Security

- Verwenden Sie Cloud App Security, um anomales Verhalten zu erkennen.

## <a name="february-2021"></a>Februar 2021

### <a name="compatibility-with-graph-api"></a>Kompatibilität mit Graph-API

Empfehlungen für die Microsoft-Sicherheitsbewertung, die über Graph API bereitgestellt werden, werden genauso aussehen und gewichtet wie die Empfehlungen, die Sie derzeit im Microsoft 365 Security Center sehen.

## <a name="january-2021"></a>Januar 2021

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>Unsere erste Sicherheitsempfehlung für Microsoft Teams hinzugefügt

Microsoft Teams Kunden wird "Anonyme Benutzer am Teilnehmen an Besprechungen hindern" als neue Verbesserungsmaßnahme in der Sicherheitsbewertung angezeigt.

## <a name="december-2020"></a>Dezember 2020

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint"></a>Sechs kontobezogene Verbesserungsmaßnahmen für Microsoft Defender für Endpunkt hinzugefügt:

- Festlegen der Mindestlänge des Kennworts auf "14 oder mehr Zeichen"
- Legen Sie "Kennwortverlauf erzwingen" auf "24 oder mehr Kennwörter" fest.
- Legen Sie "Maximales Kennwortalter" auf "60 oder weniger Tage, aber nicht 0" fest.
- Festlegen des Mindestkennwortalters auf "1 oder mehr Tage"
- Deaktivieren des integrierten Administratorkontos
- Deaktivieren des integrierten Gastkontos

## <a name="november-2020"></a>November 2020

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Die Möglichkeit zum Erstellen von ServiceNow-Tickets über die Sicherheitsbewertung wurde entfernt. 

Die Möglichkeit, ServiceNow-Tickets über die Sicherheitsbewertung zu erstellen, indem **Sie > ServiceNow freigeben,** ist nicht mehr verfügbar. Vielen Dank für Ihr Feedback und den fortgesetzten Support, während wir die nächsten Schritte festlegen.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint"></a>Es wurden drei dienstbezogene Verbesserungsmaßnahmen für Microsoft Defender für Endpunkt hinzugefügt:

- Beheben des Pfads für nicht aufgeführte Dienste für Windows Dienste
- Ändern des ausführbaren Dienstpfads in einen gemeinsamen geschützten Speicherort
- Ändern des Dienstkontos, um zwischengespeicherte Kennwörter in der Windows-Registrierung zu vermeiden

## <a name="october-2020"></a>Oktober 2020

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Entfernen von Verbesserungsmaßnahmen im Zusammenhang mit Microsoft Defender für Endpunkt

- Festlegen Microsoft Defender SmartScreen Windows Store Überprüfung von App-Webinhalten auf Warnungen

## <a name="august-2020"></a>August 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Aktualisierte Verbesserungsmaßnahmen für Azure Active Directory

- Richtlinie zum Blockieren veralteter Authentifizierung aktivieren

## <a name="incompatibility-with-identity-secure-score"></a>Inkompatibilität mit der Identitätssicherungsbewertung

In der letzten Version von Microsoft-Sicherheitsbewertung wurde ein verbessertes Bewertungsmodell veröffentlicht. Diese Änderungen ermöglichen eine flexiblere und präzisere Ansicht Ihres Sicherheitsstatus. Diese Updates haben die Microsoft-Sicherheitsbewertung jedoch vorübergehend mit der Identitätssicherungsbewertung inkompatibel gemacht.

Mit der Zeit übernimmt die Identitätssicherungsbewertung das neue Bewertungsmodell. Bis dahin werden die Kunden Unterschiede in den Bewertungen sehen, die von der Microsoft-Sicherheitsbewertung und der Identitäts-Sicherheitsbewertung gemeldet werden. Wir entschuldigen uns für alle Unannehmlichkeiten, die hierdurch verursacht werden, und arbeiten an der Sicherstellung, dass diese Erfahrungen zukünftig kompatibler sein werden.

## <a name="updated-improvement-actions"></a>Aktualisierte Verbesserungsmaßnahmen

- Azure Active Directory-Verbesserungsmaßnahmen hinzugefügt
- Verbesserungsmaßnahmen für Microsoft Defender for Identity hinzugefügt
- Unterstützung für Sicherheitsempfehlungen für Microsoft Defender for Endpoint [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Alle von TVM bereitgestellten Sicherheitsempfehlungen, die freigegeben wurden, sind nun verfügbar.

## <a name="updated-interface-and-functionality"></a>Benutzeroberfläche und Funktionalität aktualisiert

* Völlig neue Metriken und Trend-Ansichten für CISO und Lead Level-Diskussionen
* Neue Möglichkeiten zum Nachverfolgen und Benchmarken Ihrer Bewertung
* Bessere Nachverfolgung und besseres Verständnis von Bewertungsverschlechterungen
* Filtern, Taggen, Suchen und Gruppieren von Verbesserungsmaßnahmen
* Verwalten Sie Ihre zukünftigen Ziele mithilfe von Score-Projektionen und geplanten Maßnahmen
* Und mehr!

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, teilen Sie uns dies durch Veröffentlichung in der [Community für Sicherheit, Datenschutz & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) mit. Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Zugreifen auf Ihren Sicherheitsstatus](microsoft-secure-score-improvement-actions.md)
- [Nachverfolgen des Microsoft-Verlaufs der Sicherheitsbewertung und Erreichen der Ziele](microsoft-secure-score-history-metrics-trends.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
