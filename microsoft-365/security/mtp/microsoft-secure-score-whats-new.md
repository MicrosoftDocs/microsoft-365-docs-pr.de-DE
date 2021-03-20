---
title: Neues in Microsoft Secure Score
description: Beschreibt, welche neuen Änderungen an Microsoft Secure Score im Microsoft 365 Security Center vorgenommen wurden.
keywords: Microsoft Secure Score, Secure Score, Office 365 Secure Score, Microsoft Security Score, microsoft 365 Security Center
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
ms.openlocfilehash: 7d24d010f7c16d6db0fd4f9e4817768529ed29d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906746"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Neues in Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Damit die Microsoft-Sicherheitsbewertung zu einem besseren Ansprechpartner für Ihren Sicherheitsstatus wird, haben wir einige Änderungen vorgenommen. Wenn Sie mehr über geplante Änderungen wissen möchten, lesen Sie [Bald in der Microsoft-Sicherheitsbewertung verfügbar](microsoft-secure-score-whats-coming.md)

Microsoft Secure Score finden Sie im https://security.microsoft.com/securescore [Microsoft 365 Security Center](overview-security-center.md).
    
## <a name="february-2021"></a>Februar 2021

### <a name="compatibility-with-graph-api"></a>Kompatibilität mit der Graph-API

Microsoft Secure Score-Empfehlungen, die über die Graph-API bereitgestellt werden, werden genauso aussehen und gewichtet wie die Empfehlungen, die derzeit im Microsoft 365 Security Center angezeigt werden.

## <a name="january-2021"></a>Januar 2021

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>Unsere erste Sicherheitsempfehlung für Microsoft Teams wurde hinzugefügt.

Microsoft Teams-Kunden sehen "Einschränken der Teilnahme anonymer Benutzer an Besprechungen" als neue Verbesserungsaktion in Secure Score.

## <a name="december-2020"></a>Dezember 2020

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Es wurden sechs kontenbezogene Verbesserungsmaßnahmen für Microsoft Defender for Endpoint (zuvor Microsoft Defender ATP) hinzugefügt:

- Festlegen der Mindestkennwortlänge auf "14 oder mehr Zeichen"
- Festlegen von "Kennwortverlauf erzwingen" auf "24 oder mehr Kennwort(n)"
- Festlegen des maximalen Kennwortalters auf "60 oder weniger Tage, aber nicht auf 0"
- Festlegen des Mindestkennwortalters auf "1 oder mehr Tage".
- Deaktivieren des integrierten Administratorkontos
- Deaktivieren des integrierten Gastkontos

## <a name="november-2020"></a>November 2020

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Die Möglichkeit zum Erstellen von ServiceNow-Tickets über secure Score wurde entfernt. 

Die Möglichkeit, ServiceNow-Tickets über Secure Score zu erstellen, indem Sie zu **Share > ServiceNow** gehen, ist nicht mehr verfügbar. Vielen Dank für Ihr Feedback und ihren weiteren Support, während wir die nächsten Schritte festlegen.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Es wurden drei dienstbezogene Verbesserungsmaßnahmen für Microsoft Defender for Endpoint (zuvor Microsoft Defender ATP) hinzugefügt:

- Fix unquoted service path for Windows services
- Ändern des ausführbaren Pfads des Diensts zu einem gemeinsamen geschützten Speicherort
- Ändern des Dienstkontos, um zwischengespeichertes Kennwort in der Windows-Registrierung zu vermeiden

## <a name="october-2020"></a>Oktober 2020

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Entfernen von Verbesserungsmaßnahmen im Zusammenhang mit Microsoft Defender for Endpoint

- Festlegen der Microsoft Defender SmartScreen Windows Store-Webinhaltsprüfung auf Warnmodus

## <a name="august-2020"></a>August 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Aktualisierte Verbesserungsaktion für Azure Active Directory

- Richtlinie zum Blockieren veralteter Authentifizierung aktivieren

## <a name="incompatibility-with-identity-secure-score"></a>Inkompatibilität mit identitätssicherer Bewertung

In der letzten Version von Microsoft-Sicherheitsbewertung wurde ein verbessertes Bewertungsmodell veröffentlicht. Diese Änderungen ermöglichen eine flexiblere und präzisere Ansicht Ihres Sicherheitsstatus. Aufgrund dieser Updates ist Microsoft Secure Score jedoch vorübergehend mit der Identitätssicheren Bewertung nicht kompatibel.

Mit der Zeit wird identity Secure Score das neue Bewertungsmodell übernehmen. Bis dahin werden Kunden Unterschiede in den von Microsoft Secure Score und der Identitätssicheren Bewertung gemeldeten Noten sehen. Wir entschuldigen uns für alle Unannehmlichkeiten, die hierdurch verursacht werden, und arbeiten an der Sicherstellung, dass diese Erfahrungen zukünftig kompatibler sein werden.

## <a name="updated-improvement-actions"></a>Aktualisierte Verbesserungsmaßnahmen

- Azure Active Directory-Verbesserungsmaßnahmen hinzugefügt
- Microsoft Defender for Identity-Verbesserungsaktionen hinzugefügt
- Support für Microsoft Defender for Endpoint [Threat & Security Recommendations](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Alle von TVM bereitgestellten Sicherheitsempfehlungen, die freigegeben wurden, sind nun verfügbar.

## <a name="updated-interface-and-functionality"></a>Benutzeroberfläche und Funktionalität aktualisiert

* Völlig neue Metriken und Trend-Ansichten für CISO und Lead Level-Diskussionen
* Neue Möglichkeiten zum Nachverfolgen und Benchmarken Ihrer Bewertung
* Bessere Nachverfolgung und besseres Verständnis von Bewertungsverschlechterungen
* Filtern, Taggen, Suchen und Gruppieren von Verbesserungsmaßnahmen
* Verwalten Sie Ihre zukünftigen Ziele mithilfe von Score-Projektionen und geplanten Maßnahmen
* Und mehr!

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, teilen Sie uns dies mit, indem Sie in der [Community für Sicherheit, Datenschutz und & veröffentlichen.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Zugreifen auf Ihren Sicherheitsstatus](microsoft-secure-score-improvement-actions.md)
- [Nachverfolgen Ihres Microsoft Secure Score-Verlaufs und Erreichen von Zielen](microsoft-secure-score-history-metrics-trends.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)