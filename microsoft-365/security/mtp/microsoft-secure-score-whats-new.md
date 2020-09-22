---
title: Neuerungen in Microsoft Secure Score
description: Beschreibt, welche neuen Änderungen mit Microsoft Secure Score im Microsoft 365 Security Center geschehen sind.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitsbewertung, Security Center, Verbesserungsmaßnahmen
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: b85b8b801401c7f067de6a8a7d5ea96557225c44
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196277"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Neuerungen in Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Damit die Microsoft-Sicherheitsbewertung zu einem besseren Ansprechpartner für Ihren Sicherheitsstatus wird, haben wir einige Änderungen vorgenommen. Wenn Sie mehr über geplante Änderungen wissen möchten, lesen Sie [Bald in der Microsoft-Sicherheitsbewertung verfügbar](microsoft-secure-score-whats-coming.md).

## <a name="august-2020"></a>August 2020

### <a name="update-improvement-action-for-azure-active-directory"></a>Update Verbesserungs Aktion für Azure Active Directory

- Richtlinie zum Blockieren veralteter Authentifizierung aktivieren

## <a name="july-2020"></a>Juli 2020

### <a name="adding-improvement-actions-for-azure-advanced-threat-protection"></a>Hinzufügen von Verbesserungs Aktionen für Azure Advanced Threat Protection

- Riskante laterale Bewegungspfade
- Unsichere Kontoattribute
- Aktivieren von Sicherheitsfunktionen in Active Directory-Vertrauensstellungen
- Unsichere SID-Verlaufsattribute aus Entitäten entfernen

## <a name="june-2020"></a>Juni 2020

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Verbesserungs Aktion für Microsoft Defender Advanced Threat Protection entfernt

* Regeln zur Verringerung der Angriffsfläche aktivieren

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Verbesserungs Aktionen für Microsoft Defender Advanced Threat Protection hinzugefügt

* Adobe Reader am Erstellen von untergeordneten Prozessen hindern
* Erweiterten Schutz vor Ransomware verwenden
* Alle Office-Anwendungen am Erstellen von untergeordneten Prozessen hindern
* Office-Anwendungen am Erstellen ausführbarer Inhalte hindern
* JavaScript und VBScript am Starten heruntergeladener ausführbarer Inhalte hindern
* Ausführung potenziell verborgener Skripts blockieren
* Ausführbare Inhalte aus E-Mail-Client und Web-E-Mail blockieren
* Office-Kommunikationsanwendung am Erstellen von untergeordneten Prozessen hindern
* Nicht vertrauenswürdige und nicht signierte Prozess, die von USB ausgeführt werden, blockieren
* Persistenz durch WMI-Ereignisabonnement blockieren
* Office-Anwendungen am Einfügen von Code in untergeordnete Prozesse hindern
* Ausführbare Dateien an der Ausführung hindern, außer sie erfüllen ein Verbreitungs-, Alters- oder vertrauenswürdige Listen-Kriterium
* Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren
* Diebstahl von Anmeldeinformationen aus dem Subsystem für die lokale Sicherheitsautorität (lsass.exe) blockieren
* Win32-API-Aufrufe von Office-Makros blockieren

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Inkompatibilität mit der Identitätssicherheitsbewertung und der Graph-API

In der letzten Version von Microsoft-Sicherheitsbewertung wurde ein verbessertes Bewertungsmodell veröffentlicht. Diese Änderungen ermöglichen eine flexiblere und präzisere Ansicht Ihres Sicherheitsstatus. Diese Updates haben jedoch zu einer vorübergehenden Inkompatibilität der Microsoft-Sicherheitsbewertung mit der Identitätssicherheitsbewertung und der Graph-API geführt.

Im Laufe der Zeit werden die Identitätssicherheitsbewertung und die Graph-API das neue Bewertungsmodell übernehmen. Bis dahin werden Kunden Unterschiede bei den von der Microsoft-Sicherheitsbewertung, der Identitätssicherheitsbewertung und der Graph-API gemeldeten Bewertungen feststellen. Wir entschuldigen uns für alle Unannehmlichkeiten, die hierdurch verursacht werden, und arbeiten an der Sicherstellung, dass diese Erfahrungen zukünftig kompatibler sein werden.

## <a name="updated-improvement-actions"></a>Aktualisierte Verbesserungsmaßnahmen

- Azure Active Directory-Verbesserungsmaßnahmen hinzugefügt
- Azure Advanced Threat Protection-Verbesserungsmaßnahmen hinzugefügt
- Unterstützung der Sicherheitsempfehlungen von Microsoft Defender ATP [Threat & Vulnerability Management (TVM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Alle von TVM bereitgestellten Sicherheitsempfehlungen, die freigegeben wurden, sind nun verfügbar.

## <a name="updated-interface-and-functionality"></a>Benutzeroberfläche und Funktionalität aktualisiert

* Völlig neue Metriken und Trend-Ansichten für CISO und Lead Level-Diskussionen
* Neue Möglichkeiten zum Nachverfolgen und Benchmarken Ihrer Bewertung
* Bessere Nachverfolgung und besseres Verständnis von Bewertungsverschlechterungen
* Filtern, Taggen, Suchen und Gruppieren von Verbesserungsmaßnahmen
* Verwalten Sie Ihre zukünftigen Ziele mithilfe von Score-Projektionen und geplanten Maßnahmen
* Und mehr!

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, lassen Sie es uns wissen, indem Sie in der [Sicherheits-, Datenschutz-& Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) -Community veröffentlichen. Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Zugreifen auf Ihren Sicherheitsstatus](microsoft-secure-score-improvement-actions.md)
- [Verfolgen des Microsoft Secure Score-Verlaufs und erreichen der Ziele](microsoft-secure-score-history-metrics-trends.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
