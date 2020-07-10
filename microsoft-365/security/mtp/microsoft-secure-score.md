---
title: Microsoft Secure Score
description: Beschreibt Microsoft Secure Score im Microsoft 365 Security Center, wie Sie Ihre Sicherheitsposition verbessern und welche Sicherheitsadministratoren erwarten können.
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
ms.openlocfilehash: 212cefebfa3b4954f30d114419f82a5862e98a4f
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094798"
---
# <a name="microsoft-secure-score"></a>Microsoft-Sicherheitsbewertung

Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden. Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).

Wenn Sie die Secure Score-Empfehlungen befolgen, können Sie Ihre Organisation vor Bedrohungen schützen. Über ein zentrales Dashboard im Microsoft 365 Security Center können Organisationen die Sicherheit ihrer Microsoft 365-Identitäten, Daten, Apps, Geräte und Infrastruktur überwachen und daran arbeiten.

Sicherheitsbewertung hilft Organisationen auf diese Arten:  

* Berichtet über den aktuellen Sicherheitsstatus der Organisation.
* Verbessert den Sicherheitsstatus durch Auffindbarkeit, Transparenz, Anleitung und Kontrolle.  
* Ermöglicht Vergleiche mit Benchmarks und erstellt KPIs (Key Performance Indicators).

Organisationen erhalten Zugriff auf zuverlässige Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, einen Vergleich mit ähnlichen Organisationen und vieles mehr. Die Bewertung zeigt auch, wenn Lösungen von Drittanbietern empfohlene Maßnahmen behandelt haben.

![Startseite der Sicherheitsbewertung](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Funktionsweise

Sie erhalten Punkte für die Konfiguration empfohlener Sicherheitsfunktionen, die Ausführung sicherheitsrelevanter Aufgaben oder die Behandlung von Verbesserungsmaßnahmen mit einer Drittanbieteranwendung oder -software oder einer alternativen Korrektur. Einige Verbesserungsmaßnahmen geben nur Punkte, wenn sie vollständig abgeschlossen sind, und einige geben schon Punkte, auch wenn sie nur für einige Geräte oder Benutzer abgeschlossen sind. Wenn Sie eine der Verbesserungsmaßnahmen nicht ausführen können oder möchten, können Sie sich entschließen, das Risiko bzw. das Restrisiko zu übernehmen.

Wir zeigen Ihnen die vollständige Palette möglicher Verbesserungen – unabhängig von der Lizenz –, damit Sie bewährte Methoden für die Sicherheit verstehen und Ihre Punktzahl verbessern können. Sicherheitsbewertung stellt Ihren absoluten Sicherheitsstatus dar, der unverändert bleibt, unabhängig von den Lizenzen Ihrer Organisation. Bitte bedenken Sie: Sicherheit sollte mit Benutzerfreundlichkeit in Einklang gebracht werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung.

Ihre Bewertung wird in Echtzeit aktualisiert, um die Informationen auf den Seiten Visualisierung und Verbesserungsmaßnahmen darzustellen. Sicherheitsbewertung wird auch täglich synchronisiert, um Systemdaten zu Ihren erreichten Punkten für jede Aktion zu erhalten.

### <a name="key-scenarios"></a>Schlüsselszenarien

- [Überprüfen der aktuellen Bewertung](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Vergleichen Sie Ihre Punktzahl mit Organisationen wie Ihrem](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Anzeigen von Verbesserungs Aktionen und Festlegen eines Aktionsplans](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Initiieren von Workflows zur Untersuchung oder Implementierung](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Microsoft 365 Security Center und ServiceNow-Integration](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>Wie Verbesserungsmaßnahmen bewertet werden

Jede Verbesserungsmaßnahme hat einen Wert von höchstens 10 Punkten. Die meisten werden auf binäre Art bewertet – wenn Sie die Verbesserungsmaßnahme umsetzen, wie z. B. eine neue Richtlinie erstellen oder eine bestimmte Einstellung aktivieren –, erhalten Sie die volle Punktzahl. Bei anderen Verbesserungsmaßnahmen werden Punkte als Prozentsatz der Gesamtkonfiguration gegeben. Wenn beispielsweise die Verbesserungs Aktion besagt, dass Sie 10 Punkte erhalten, indem Sie alle Ihre Benutzer mit mehrstufiger Authentifizierung schützen und nur 50 von 100 Gesamtanzahl der Benutzer geschützt haben, erhalten Sie einen Teil der Punktzahl von 5 Punkten (50 Protected/100 total * 10 max PTS = 5 Pkt Partial Score).

### <a name="products-included-in-secure-score"></a>Produkte in Sicherheitsbewertung

Derzeit gibt es Empfehlungen für Microsoft 365 (einschließlich Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP und Cloud App Security. Empfehlungen für andere Sicherheitsprodukte werden in Kürze verfügbar sein. Die Empfehlungen umfassen nicht alle Angriffsflächen, die jedem Produkt zugeordnet sind, sind aber ein guter Ausgangsbasis. Sie können die Verbesserungsmaßnahmen auch als „über Drittanbieter abgedeckt“ oder „ durch alternative Korrektur abgedeckt“ markieren.

### <a name="security-defaults"></a>Standardsicherheitseinstellungen 

Microsoft Secure Score enthält aktualisierte Verbesserungs Aktionen zur Unterstützung von [Sicherheitsstandards in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), die es einfacher machen, Ihre Organisation mit vorkonfigurierten Sicherheitseinstellungen für häufige Angriffe zu schützen.

Wenn Sie Sicherheitsstandards aktivieren, erhalten Sie vollständige Punkte für die folgenden Verbesserungs Aktionen:

- Sicherstellen, dass alle Benutzer die mehrstufige Authentifizierung für sicheren Zugriff abschließen können (9 Punkte)
- MFA für Administratorrollen erforderlich (10 Punkte)
- Aktivieren einer Richtlinie zum Blockieren der Legacy Authentifizierung (7 Punkte)

>[!IMPORTANT]
>Zu den Sicherheitsstandards gehören Sicherheitsfeatures, die der Verbesserungs Aktion "Anmeldungs Risiko Richtlinie" und "Benutzer Risiko Richtlinie" ähnliche Sicherheit bieten. Anstatt diese Richtlinien zusätzlich zu den Sicherheitsstandards einzurichten, empfehlen wir, ihre Status auf "durch alternative Schadensbegrenzende Maßnahmen behoben" zu aktualisieren.

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Um die Zugriffsberechtigung auf die Microsoft-Sicherheitsbewertung zu erhalten, müssen Sie eine der folgenden Rollen in Azure Active Directory besitzen.

### <a name="read-and-write-roles"></a>Rollen "Lesen und Schreiben"

Mit Lese- und Schreibzugriff können Sie Änderungen vornehmen und mit Sicherheitsbewertung direkt interagieren. Sie können anderen Benutzern auch schreibgeschützten Zugriff zuweisen.

* Globaler Administrator
* Sicherheitsadministrator
* Exchange-Administrator
* SharePoint-Administrator
* Kontoadministrator

### <a name="read-only-roles"></a>Schreibgeschützte Rollen

Bei schreibgeschütztem Zugriff können Sie den Status oder die Notizen für eine Verbesserungsmaßnahme nicht bearbeiten, sowie keine Ergebniszonen oder benutzerdefinierte Vergleiche bearbeiten.

* Helpdesk-Administrator
* Benutzeradministrator
* Service-Administrator
* Benutzer mit Leseberechtigung für Sicherheitsfunktionen
* Sicherheitsoperator
* Globaler Leser

## <a name="risk-awareness"></a>Risikobewusstsein

Die Microsoft-Sicherheitsbewertung ist eine numerische Zusammenfassung Ihres Sicherheitsstatus, die auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsrelevanten Maßstäben basiert. Hierbei handelt es sich nicht um eine absolute Messung, wie wahrscheinlich eine Sicherheitsverletzung Ihres System oder Ihrer Daten ist. Vielmehr stellt Sie das Ausmaß dar, in dem Sie Sicherheitskontrollen in Ihrer Microsoft-Umgebung eingeführt haben, die das Risiko einer Sicherheitsverletzung ausgleichen können. Kein Onlinedienst ist vollkommen immun gegen Sicherheitsverstöße, und Sicherheitsbewertung sollte in keiner Weise als Garantie gegen Sicherheitsverstöße interpretiert werden.

## <a name="whats-new"></a>Was sind die Neuerungen? 

Damit die Microsoft-Sicherheitsbewertung zu einem besseren Ansprechpartner für Ihren Sicherheitsstatus wird, haben wir einige Änderungen vorgenommen. Wenn Sie mehr über geplante Änderungen wissen möchten, lesen Sie [Bald in der Microsoft-Sicherheitsbewertung verfügbar](microsoft-secure-score-whats-coming.md).

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Inkompatibilität mit der Identitätssicherheitsbewertung und der Graph-API

In der letzten Version von Microsoft-Sicherheitsbewertung wurde ein verbessertes Bewertungsmodell veröffentlicht. Diese Änderungen ermöglichen eine flexiblere und präzisere Ansicht Ihres Sicherheitsstatus. Diese Updates haben jedoch zu einer vorübergehenden Inkompatibilität der Microsoft-Sicherheitsbewertung mit der Identitätssicherheitsbewertung und der Graph-API geführt.

Im Laufe der Zeit werden die Identitätssicherheitsbewertung und die Graph-API das neue Bewertungsmodell übernehmen. Bis dahin werden Kunden Unterschiede bei den von der Microsoft-Sicherheitsbewertung, der Identitätssicherheitsbewertung und der Graph-API gemeldeten Bewertungen feststellen. Wir entschuldigen uns für alle Unannehmlichkeiten, die hierdurch verursacht werden, und arbeiten an der Sicherstellung, dass diese Erfahrungen zukünftig kompatibler sein werden.

### <a name="updated-improvement-actions"></a>Aktualisierte Verbesserungsmaßnahmen

- Azure Active Directory-Verbesserungsmaßnahmen hinzugefügt
- Azure Advanced Threat Protection-Verbesserungsmaßnahmen hinzugefügt
- Unterstützung der Sicherheitsempfehlungen von Microsoft Defender ATP [Threat & Vulnerability Management (TVM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Alle von TVM bereitgestellten Sicherheitsempfehlungen, die freigegeben wurden, sind nun verfügbar.

### <a name="updated-interface-and-functionality"></a>Benutzeroberfläche und Funktionalität aktualisiert

* Völlig neue Metriken und Trend-Ansichten für CISO und Lead Level-Diskussionen
* Neue Möglichkeiten zum Nachverfolgen und Benchmarken Ihrer Bewertung
* Bessere Nachverfolgung und besseres Verständnis von Bewertungsverschlechterungen
* Filtern, Taggen, Suchen und Gruppieren von Verbesserungsmaßnahmen
* Verwalten Sie Ihre zukünftigen Ziele mithilfe von Score-Projektionen und geplanten Maßnahmen
* Und mehr!

### <a name="june-2020"></a>Juni 2020

#### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Verbesserungs Aktion für Microsoft Defender Advanced Threat Protection entfernt

* Regeln zur Verringerung der Angriffsfläche aktivieren

#### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Verbesserungs Aktionen für Microsoft Defender Advanced Threat Protection hinzugefügt

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

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, informieren Sie uns mit einem Beitrag in der Community für [Sicherheit, Datenschutz und Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy). Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Erhalten Sie Einblicke in Ihren Sicherheitsstatus](microsoft-secure-score-improvement-actions.md)
- [Verfolgen des Microsoft Secure Score-Verlaufs und erreichen der Ziele](microsoft-secure-score-history-metrics-trends.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
