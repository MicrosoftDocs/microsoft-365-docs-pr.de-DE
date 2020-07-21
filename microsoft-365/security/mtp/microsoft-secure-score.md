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
ms.openlocfilehash: 862a25eddda6048349df937641914377cb25874f
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200038"
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

Wenn Sie über eine Lizenz für eines der unterstützten Microsoft-Produkte verfügen, werden Ihnen Empfehlungen für diese Produkte angezeigt. Wir zeigen Ihnen den vollständigen Überblick über mögliche Verbesserungen für ein Produkt, unabhängig von Lizenzedition, Abonnement oder Plan, damit Sie bewährte Methoden für die Sicherheit verstehen und Ihre Punktzahl verbessern können. Ihre absolute Sicherheitsposition wird durch Secure Score dargestellt, was unabhängig von den Lizenzen, die Ihre Organisation für ein bestimmtes Produkt besitzt, gleich bleibt. Bitte bedenken Sie: Sicherheit sollte mit Benutzerfreundlichkeit in Einklang gebracht werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung.

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

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, informieren Sie uns mit einem Beitrag in der Community für [Sicherheit, Datenschutz und Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy). Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Bewerten Ihrer Sicherheitsposition](microsoft-secure-score-improvement-actions.md)
- [Verfolgen des Microsoft Secure Score-Verlaufs und erreichen der Ziele](microsoft-secure-score-history-metrics-trends.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
- [Neuigkeiten](microsoft-secure-score-whats-new.md)
