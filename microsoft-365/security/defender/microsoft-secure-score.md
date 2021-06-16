---
title: Microsoft-Sicherheitsbewertung
description: Beschreibt die Microsoft-Sicherheitsbewertung im Microsoft 365 Security Center, wie Sie Ihren Sicherheitsstatus verbessern und was Sicherheitsadministratoren erwarten können.
keywords: Microsoft-Sicherheitsbewertung, Sicherheitsbewertung, Office 365-Sicherheitsbewertung, Microsoft-Sicherheitsbewertung, Microsoft 365 Security Center, Verbesserungsmaßnahmen
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
ms.openlocfilehash: 1b03c2671939a3e8e3011b78b8f1484ef02979ea
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930187"
---
# <a name="microsoft-secure-score"></a>Microsoft-Sicherheitsbewertung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden. Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).

Wenn Sie den Empfehlungen der Sicherheitsbewertung folgen, können Sie Ihre Organisation vor Bedrohungen schützen. Über ein zentrales Dashboard im Microsoft 365 Security Center können Organisationen die Sicherheit ihrer Microsoft 365 Identitäten, Apps und Geräte überwachen und daran arbeiten.

Sicherheitsbewertung hilft Organisationen auf diese Arten:  

* Berichtet über den aktuellen Sicherheitsstatus der Organisation.
* Verbessert den Sicherheitsstatus durch Auffindbarkeit, Transparenz, Anleitung und Kontrolle.  
* Ermöglicht Vergleiche mit Benchmarks und erstellt KPIs (Key Performance Indicators).

Organisationen erhalten Zugriff auf zuverlässige Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, einen Vergleich mit ähnlichen Organisationen und vieles mehr. Die Bewertung zeigt auch, wenn Lösungen von Drittanbietern empfohlene Maßnahmen behandelt haben.

![Startseite der Sicherheitsbewertung](../../media/secure-score/secure-score-home-page.png)

## <a name="how-it-works"></a>So funktioniert's

Sie erhalten Punkte für die folgenden Aktionen:

- Konfigurieren empfohlener Sicherheitsfeatures
- Ausführen sicherheitsrelevanter Aufgaben
- Behandeln der Verbesserungsmaßnahmen mit einer Drittanbieteranwendung oder -software oder einer alternativen Gegenmaßnahme

Einige Verbesserungsmaßnahmen liefern nur Punkte, wenn sie vollständig abgeschlossen sind. Einige geben Teilpunkte zurück, wenn sie für einige Geräte oder Benutzer abgeschlossen sind. Wenn Sie eine der Verbesserungsmaßnahmen nicht ausführen können oder möchten, können Sie das Risiko oder das verbleibende Risiko akzeptieren.

Wenn Sie über eine Lizenz für eines der unterstützten Microsoft-Produkte verfügen, werden Empfehlungen für diese Produkte angezeigt. Wir zeigen Ihnen den vollständigen Satz möglicher Verbesserungen für ein Produkt, unabhängig von der Lizenzversion, dem Abonnement oder dem Plan. Auf diese Weise können Sie bewährte Methoden für die Sicherheit verstehen und Ihre Bewertung verbessern. Ihr absoluter Sicherheitsstatus, der durch die Sicherheitsbewertung dargestellt wird, bleibt gleich, unabhängig davon, welche Lizenzen Ihre Organisation für ein bestimmtes Produkt besitzt. Bitte bedenken Sie: Sicherheit sollte mit Benutzerfreundlichkeit in Einklang gebracht werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung.

Ihre Bewertung wird in Echtzeit aktualisiert, um die Informationen auf den Seiten Visualisierung und Verbesserungsmaßnahmen darzustellen. Sicherheitsbewertung wird auch täglich synchronisiert, um Systemdaten zu Ihren erreichten Punkten für jede Aktion zu erhalten.

### <a name="key-scenarios"></a>Schlüsselszenarien

- [Überprüfen Des aktuellen Bewertungsergebnisses](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Vergleichen Sie Ihre Bewertung mit Organisationen wie Ihrer](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Anzeigen von Verbesserungsmaßnahmen und Festlegen eines Aktionsplanes](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Initiieren von Arbeitsflüssen zur Untersuchung oder Implementierung](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>Wie Verbesserungsmaßnahmen bewertet werden

Jede Verbesserungsmaßnahme ist mindestens 10 Punkte wert, und die meisten werden binär bewertet. Wenn Sie die Verbesserungsmaßnahme implementieren, z. B. eine neue Richtlinie erstellen oder eine bestimmte Einstellung aktivieren, erhalten Sie 100 % der Punkte. Bei anderen Verbesserungsmaßnahmen werden Punkte als Prozentsatz der Gesamtkonfiguration gegeben.

Eine Verbesserungsmaßnahme gibt beispielsweise an, dass Sie 10 Punkte erhalten, indem Sie alle Ihre Benutzer mit mehrstufiger Authentifizierung schützen. Sie haben nur 50 von insgesamt 100 Benutzern geschützt, sodass Sie eine Partielle Bewertung von 5 Punkten erhalten (50 geschützte / 100 insgesamt * 10 maximale Pts = 5 Pts).

### <a name="products-included-in-secure-score"></a>Produkte in Sicherheitsbewertung

Derzeit gibt es Empfehlungen für die folgenden Produkte:

- Microsoft 365 (einschließlich Exchange Online)
- Azure Active Directory
- Microsoft Defender für Endpunkt
- Microsoft Defender for Identity
- Cloud-App-Sicherheit
- Microsoft Teams

Empfehlungen für andere Sicherheitsprodukte werden in Kürze verfügbar sein. Die Empfehlungen umfassen nicht alle Angriffsflächen, die mit jedem Produkt verbunden sind, aber sie sind eine gute Basislinie. Sie können die Verbesserungsmaßnahmen auch als „über Drittanbieter abgedeckt“ oder „ durch alternative Korrektur abgedeckt“ markieren.

### <a name="security-defaults"></a>Sicherheitsstandards

Die Microsoft-Sicherheitsbewertung hat Verbesserungsmaßnahmen aktualisiert, um [Sicherheitsstandards in Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)zu unterstützen, wodurch es einfacher ist, Ihre Organisation mit vorkonfigurierten Sicherheitseinstellungen für häufige Angriffe zu schützen.

Wenn Sie die Sicherheitsstandards aktivieren, erhalten Sie alle Punkte für die folgenden Verbesserungsmaßnahmen:

- Sicherstellen, dass alle Benutzer die mehrstufige Authentifizierung für den sicheren Zugriff abschließen können (9 Punkt)
- MFA für Administratorrollen erforderlich (10 Punkte)
- Richtlinie zum Blockieren der Legacyauthentifizierung aktivieren (7 Punkte)

>[!IMPORTANT]
>Zu den Sicherheitsstandards gehören Sicherheitsfeatures, die ähnliche Sicherheit wie die Verbesserungsmaßnahmen "Anmelderisikorichtlinie" und "Benutzerrisikorichtlinie" bieten. Anstatt diese Richtlinien über die Sicherheitsstandards hinaus einzurichten, empfehlen wir, deren Status auf "Gelöst durch alternative Gegenmaßnahmen" zu aktualisieren.

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Um die Zugriffsberechtigung auf die Microsoft-Sicherheitsbewertung zu erhalten, müssen Sie eine der folgenden Rollen in Azure Active Directory besitzen.

### <a name="read-and-write-roles"></a>Rollen "Lesen und Schreiben"

Mit Lese- und Schreibzugriff können Sie Änderungen vornehmen und mit Sicherheitsbewertung direkt interagieren. Sie können anderen Benutzern auch schreibgeschützten Zugriff zuweisen.

* Globaler Administrator
* Sicherheitsadministrator
* Exchange-Administrator
* SharePoint-Administrator

### <a name="read-only-roles"></a>Schreibgeschützte Rollen

Mit schreibgeschütztem Zugriff können Sie status oder Notizen für eine Verbesserungsmaßnahme nicht bearbeiten, keine Bewertungszonen bearbeiten oder benutzerdefinierte Vergleiche bearbeiten.

* Helpdesk-Administrator
* Benutzeradministrator
* Dienstsupportadministrator
* Benutzer mit Leseberechtigung für Sicherheitsfunktionen
* Sicherheitsoperator
* Globaler Leser

## <a name="risk-awareness"></a>Risikobewusstsein

Die Microsoft-Sicherheitsbewertung ist eine numerische Zusammenfassung Ihres Sicherheitsstatus basierend auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsrelevanten Messungen. Es ist keine absolute Maßeinheit dafür, wie wahrscheinlich ein System- oder Datenverstoß ist. Vielmehr stellt es das Ausmaß dar, in dem Sie Sicherheitskontrollen in Ihrer Microsoft-Umgebung eingeführt haben, die dazu beitragen können, das Risiko von Sicherheitsverletzungen zu erhöhen. Kein Onlinedienst ist gegen Sicherheitsverstöße immun, und die Sicherheitsbewertung sollte in keiner Weise als Garantie gegen Sicherheitsverletzungen interpretiert werden.

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, teilen Sie uns dies durch Veröffentlichung in der [Community für Sicherheit, Datenschutz & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) mit. Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Zugreifen auf Ihren Sicherheitsstatus](microsoft-secure-score-improvement-actions.md)
- [Nachverfolgen des Microsoft-Verlaufs der Sicherheitsbewertung und Erreichen der Ziele](microsoft-secure-score-history-metrics-trends.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
- [Neuerungen](microsoft-secure-score-whats-new.md)
