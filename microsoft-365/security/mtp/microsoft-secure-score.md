---
title: Microsoft-Sicherheitsbewertung
description: Beschreibt die Microsoft Secure Score im Microsoft 365 Security Center, wie Sie Ihren Sicherheitsstand verbessern und was Sicherheitsadministratoren erwarten können.
keywords: Microsoft Secure Score, Secure Score, Office 365 Secure Score, Microsoft Security Score, Microsoft 365 Security Center, Verbesserungsmaßnahmen
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
ms.openlocfilehash: 39abcbde82c2902b091b42db3dbc8e1ee2cbd924
ms.sourcegitcommit: 8b3ff6e9f8931327b6f0541fd882107687cd123e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2021
ms.locfileid: "49942790"
---
# <a name="microsoft-secure-score"></a>Microsoft-Sicherheitsbewertung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden. Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).

Durch das Folgen der Empfehlungen für die Sicherheitspunktzahl kann Ihre Organisation vor Bedrohungen geschützt werden. Über ein zentrales Dashboard im Microsoft 365 Security Center können Organisationen die Sicherheit ihrer Microsoft 365-Identitäten, -Apps und -Geräte überwachen und an ihnen arbeiten.

Sicherheitsbewertung hilft Organisationen auf diese Arten:  

* Berichtet über den aktuellen Sicherheitsstatus der Organisation.
* Verbessert den Sicherheitsstatus durch Auffindbarkeit, Transparenz, Anleitung und Kontrolle.  
* Ermöglicht Vergleiche mit Benchmarks und erstellt KPIs (Key Performance Indicators).

Organisationen erhalten Zugriff auf zuverlässige Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, einen Vergleich mit ähnlichen Organisationen und vieles mehr. Die Bewertung zeigt auch, wenn Lösungen von Drittanbietern empfohlene Maßnahmen behandelt haben.

![Startseite der Sicherheitsbewertung](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Funktionsweise

Sie erhalten Punkte für die folgenden Aktionen:

- Konfigurieren empfohlener Sicherheitsfeatures
- Ausführen sicherheitsrelevanter Aufgaben
- Adressieren der Verbesserungsaktion mit einer Drittanbieteranwendung oder -software oder einer alternativen Gegenmaßnahmen

Einige Verbesserungsmaßnahmen geben nur Punkte, wenn sie vollständig abgeschlossen sind. Einige punkten teilweise, wenn sie für einige Geräte oder Benutzer abgeschlossen sind. Wenn Sie keine der Verbesserungsmaßnahmen durchführen können oder möchten, können Sie das Risiko oder das verbleibende Risiko übernehmen.

Wenn Sie über eine Lizenz für eines der unterstützten Microsoft-Produkte verfügen, werden Empfehlungen für diese Produkte erhalten. Wir zeigen Ihnen den vollständigen Satz möglicher Verbesserungen für ein Produkt, unabhängig von der Lizenzedition, dem Abonnement oder dem Plan. Auf diese Weise können Sie bewährte Methoden für die Sicherheit verstehen und Ihre Bewertung verbessern. Ihr absoluter Sicherheitsstand, dargestellt durch secure Score, bleibt unabhängig davon, welche Lizenzen Ihre Organisation für ein bestimmtes Produkt besitzt, gleich. Bitte bedenken Sie: Sicherheit sollte mit Benutzerfreundlichkeit in Einklang gebracht werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung.

Ihre Bewertung wird in Echtzeit aktualisiert, um die Informationen auf den Seiten Visualisierung und Verbesserungsmaßnahmen darzustellen. Sicherheitsbewertung wird auch täglich synchronisiert, um Systemdaten zu Ihren erreichten Punkten für jede Aktion zu erhalten.

### <a name="key-scenarios"></a>Schlüsselszenarien

- [Überprüfen Der aktuellen Bewertung](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Vergleichen Ihrer Bewertung mit Organisationen wie Ihrer](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Anzeigen von Verbesserungsmaßnahmen und Festlegen eines Aktionsplans](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Initiieren von Arbeitsflüssen zur Untersuchung oder Implementierung](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>Wie Verbesserungsmaßnahmen bewertet werden

Jede Verbesserungsaktion hat einen Wert von 10 Punkten oder weniger, und die meisten werden binär wertungiert. Wenn Sie die Verbesserungsaktion implementieren, z. B. eine neue Richtlinie erstellen oder eine bestimmte Einstellung aktivieren, erhalten Sie 100 % der Punkte. Bei anderen Verbesserungsmaßnahmen werden Punkte als Prozentsatz der Gesamtkonfiguration gegeben.

Eine Verbesserungsaktion gibt beispielsweise an, dass Sie 10 Punkte erhalten, indem Sie alle Benutzer mit mehrstufiger Authentifizierung schützen. Sie haben nur 50 von 100 Benutzern insgesamt geschützt, sodass Sie eine Teilpunktzahl von 5 Punkt erhalten würden (50 geschützte /100 insgesamt * 10 max Pts = 5 Pts).

### <a name="products-included-in-secure-score"></a>Produkte in Sicherheitsbewertung

Derzeit gibt es Empfehlungen für die folgenden Produkte:

- Microsoft 365 (einschließlich Exchange Online)
- Azure Active Directory
- Microsoft Defender für Endpunkt
- Microsoft Defender for Identity
- Cloud-App-Sicherheit
- Microsoft Teams

Empfehlungen für andere Sicherheitsprodukte werden in Kürze verfügbar sein. Die Empfehlungen decken nicht alle Angriffsflächen ab, die jedem Produkt zugeordnet sind, aber sie sind ein guter Basisplan. Sie können die Verbesserungsmaßnahmen auch als „über Drittanbieter abgedeckt“ oder „ durch alternative Korrektur abgedeckt“ markieren.

### <a name="security-defaults"></a>Sicherheitsstandards

Die Microsoft Secure Score hat Verbesserungsmaßnahmen zur Unterstützung von Sicherheitseinstellungen [in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)aktualisiert, die es einfacher machen, Ihre Organisation mit vorkonfigurierten Sicherheitseinstellungen für häufige Angriffe zu schützen.

Wenn Sie Sicherheitseinstellungen aktivieren, erhalten Sie vollständige Punkte für die folgenden Verbesserungsmaßnahmen:

- Sicherstellen, dass alle Benutzer die mehrstufige Authentifizierung für sicheren Zugriff abschließen können (9 Punkte)
- MFA für Administratorrollen erforderlich (10 Punkte)
- Aktivieren der Richtlinie zum Blockieren der Legacyauthentifizierung (7 Punkte)

>[!IMPORTANT]
>Sicherheitseinstellungen umfassen Sicherheitsfeatures, die ähnliche Sicherheit wie die "Anmelderisikorichtlinie" und Verbesserungsmaßnahmen der "Benutzerrisikorichtlinie" bieten. Anstatt diese Richtlinien über die Sicherheitseinstellungen hinaus zu erstellen, wird empfohlen, ihre Status auf "Gelöst durch alternative Gegenmaßnahmen" zu aktualisieren.

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

Mit schreibgeschützten Zugriff können Sie status oder Notizen für eine Verbesserungsaktion, Bewertungszonen oder benutzerdefinierte Vergleiche nicht bearbeiten.

* Helpdesk-Administrator
* Benutzeradministrator
* Service-Administrator
* Benutzer mit Leseberechtigung für Sicherheitsfunktionen
* Sicherheitsoperator
* Globaler Leser

## <a name="risk-awareness"></a>Risikobewusstsein

Die Microsoft Secure Score ist eine numerische Zusammenfassung Ihres Sicherheitsstands basierend auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsbezogenen Messungen. Es ist kein absolutes Maß für die Wahrscheinlichkeit, dass Ihr System oder Ihre Daten verletzt werden. Sie stellt vielmehr das Ausmaß dar, in dem Sie Sicherheitskontrollen in Ihrer Microsoft-Umgebung übernommen haben, die dazu beitragen können, das Risiko einer Verletzung zu kompensieren. Kein Onlinedienst ist von Sicherheitsverletzungen nicht geschützt, und die Sicherheitswertung sollte in keiner Weise als Garantie gegen Sicherheitsverletzungen interpretiert werden.

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, teilen Sie uns dies mit, indem Sie in der Community für [Sicherheit, Datenschutz und & veröffentlichen.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Zugreifen auf Ihren Sicherheitsstatus](microsoft-secure-score-improvement-actions.md)
- [Verfolgen Des Verlaufs der Microsoft Secure Score und Erreichen der Ziele](microsoft-secure-score-history-metrics-trends.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
- [Neuerungen](microsoft-secure-score-whats-new.md)
