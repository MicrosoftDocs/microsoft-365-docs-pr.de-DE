---
title: Neues in der Microsoft Secure Score
description: Beschreibt, welche neuen Änderungen an der Microsoft Secure Score im Microsoft 365 Security Center vorgenommen wurden.
keywords: Microsoft-Sicherheitsergebnis, Sicherheitsergebnis, Office 365-Sicherheitsergebnis, Microsoft-Sicherheitsergebnis, Microsoft 365 Security Center
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
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
ms.openlocfilehash: 039ec1c3f9b0ba233f950d11b9d58be341b28121
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930594"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Neues in der Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Damit die Microsoft-Sicherheitsbewertung zu einem besseren Ansprechpartner für Ihren Sicherheitsstatus wird, haben wir einige Änderungen vorgenommen. Wenn Sie mehr über geplante Änderungen wissen möchten, lesen Sie [Bald in der Microsoft-Sicherheitsbewertung verfügbar](microsoft-secure-score-whats-coming.md)

Die Microsoft Secure Score finden Sie https://security.microsoft.com/securescore im [Microsoft 365 Security Center.](overview-security-center.md)

## <a name="january-2021"></a>Januar 2021

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>Unsere erste Sicherheitsempfehlung für Microsoft Teams wurde hinzugefügt.

Microsoft Teams-Kunden sehen "Einschränken der Teilnahme anonymer Benutzer an Besprechungen" als neue Verbesserungsaktion in der Sicherheitsergebnis-Bewertung.

## <a name="december-2020"></a>Dezember 2020

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Sechs kontenbezogene Verbesserungsmaßnahmen für Microsoft Defender for Endpoint (zuvor Microsoft Defender ATP) hinzugefügt:

- "Minimale Kennwortlänge" auf "14 oder mehr Zeichen" festlegen
- Legen Sie "Kennwortverlauf erzwingen" auf "24 oder mehr Kennwörter"
- Legen Sie "Maximales Kennwortalter" auf "60 oder weniger Tage, aber nicht auf 0" festgelegt.
- Festlegen des Mindestkennwortalters auf "1 oder mehr Tage".
- Deaktivieren des integrierten Administratorkontos
- Deaktivieren des integrierten Gastkontos

## <a name="november-2020"></a>November 2020

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Die Möglichkeit zum Erstellen von "ServiceNow"-Tickets über secure Score wurde entfernt. 

Die Möglichkeit zum Erstellen von "ServiceNow"-Tickets über die Sicherheitspunktzahl über **"Share > ServiceNow"** ist nicht mehr verfügbar. Vielen Dank für Ihr Feedback und ihren weiteren Support, während wir die nächsten Schritte festlegen.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Drei dienstbezogene Verbesserungsmaßnahmen für Microsoft Defender for Endpoint (zuvor Microsoft Defender ATP) hinzugefügt:

- Beheben des Nicht-Anführungszeichen-Dienstpfads für Windows-Dienste
- Ändern des Pfads der ausführbaren Dienstdatei zu einem gemeinsamen geschützten Speicherort
- Ändern des Dienstkontos, um zwischengespeichertes Kennwort in der Registrierung von Windows zu vermeiden

## <a name="october-2020"></a>Oktober 2020

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Entfernen von Verbesserungsmaßnahmen im Zusammenhang mit Microsoft Defender for Endpoint

- Festlegen der Microsoft Defender SmartScreen Windows Store-App-Webinhaltsüberprüfung auf "Warnen"

## <a name="august-2020"></a>August 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Aktualisierte Verbesserungsaktion für Azure Active Directory

- Richtlinie zum Blockieren veralteter Authentifizierung aktivieren

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Inkompatibilität mit der Identitätssicherheitsbewertung und der Graph-API

In der letzten Version von Microsoft-Sicherheitsbewertung wurde ein verbessertes Bewertungsmodell veröffentlicht. Diese Änderungen ermöglichen eine flexiblere und präzisere Ansicht Ihres Sicherheitsstatus. Diese Updates haben jedoch zu einer vorübergehenden Inkompatibilität der Microsoft-Sicherheitsbewertung mit der Identitätssicherheitsbewertung und der Graph-API geführt.

Im Laufe der Zeit werden die Identitätssicherheitsbewertung und die Graph-API das neue Bewertungsmodell übernehmen. Bis dahin werden Kunden Unterschiede bei den von der Microsoft-Sicherheitsbewertung, der Identitätssicherheitsbewertung und der Graph-API gemeldeten Bewertungen feststellen. Wir entschuldigen uns für alle Unannehmlichkeiten, die hierdurch verursacht werden, und arbeiten an der Sicherstellung, dass diese Erfahrungen zukünftig kompatibler sein werden.

## <a name="updated-improvement-actions"></a>Aktualisierte Verbesserungsmaßnahmen

- Azure Active Directory-Verbesserungsmaßnahmen hinzugefügt
- Microsoft Defender for Identity improvement actions hinzugefügt
- Unterstützung für Sicherheitsempfehlungen für Microsoft Defender für Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Alle von TVM bereitgestellten Sicherheitsempfehlungen, die freigegeben wurden, sind nun verfügbar.

## <a name="updated-interface-and-functionality"></a>Benutzeroberfläche und Funktionalität aktualisiert

* Völlig neue Metriken und Trend-Ansichten für CISO und Lead Level-Diskussionen
* Neue Möglichkeiten zum Nachverfolgen und Benchmarken Ihrer Bewertung
* Bessere Nachverfolgung und besseres Verständnis von Bewertungsverschlechterungen
* Filtern, Taggen, Suchen und Gruppieren von Verbesserungsmaßnahmen
* Verwalten Sie Ihre zukünftigen Ziele mithilfe von Score-Projektionen und geplanten Maßnahmen
* Und mehr!

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, teilen Sie uns dies mit, indem Sie sie in der [Community "Sicherheit& Datenschutzrichtlinien"](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) veröffentlichen. Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Zugreifen auf Ihren Sicherheitsstatus](microsoft-secure-score-improvement-actions.md)
- [Verfolgen Des Verlaufs der Microsoft Secure Score und Erreichen der Ziele](microsoft-secure-score-history-metrics-trends.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
