---
title: Microsoft-Sicherheitsbewertung
description: Beschreibt microsoft Secure Score im Microsoft 365 Security Center, wie Sie Ihre Sicherheitslage verbessern und was Sicherheitsadministratoren erwarten können.
keywords: Microsoft Secure Score, Secure Score, Office 365 Secure Score, Microsoft Security Score, microsoft 365 Security Center, Verbesserungsmaßnahmen
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
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
ms.openlocfilehash: 98f335a38b2e4f581d4b08def39353e53e1bafd4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064608"
---
# <a name="microsoft-secure-score"></a>Microsoft-Sicherheitsbewertung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden. Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).

Wenn Sie den Empfehlungen der Sicherheitsbewertung folgen, können Sie Ihre Organisation vor Bedrohungen schützen. Über ein zentrales Dashboard im Microsoft 365 Security Center können Organisationen die Sicherheit ihrer Microsoft 365-Identitäten, Apps und Geräte überwachen und arbeiten.

Sicherheitsbewertung hilft Organisationen auf diese Arten:  

* Berichtet über den aktuellen Sicherheitsstatus der Organisation.
* Verbessert den Sicherheitsstatus durch Auffindbarkeit, Transparenz, Anleitung und Kontrolle.  
* Ermöglicht Vergleiche mit Benchmarks und erstellt KPIs (Key Performance Indicators).

Organisationen erhalten Zugriff auf zuverlässige Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, einen Vergleich mit ähnlichen Organisationen und vieles mehr. Die Bewertung zeigt auch, wenn Lösungen von Drittanbietern empfohlene Maßnahmen behandelt haben.

![Startseite der Sicherheitsbewertung](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Funktionsweise

Sie erhalten Punkte für die folgenden Aktionen:

- Konfigurieren empfohlener Sicherheitsfeatures
- Ausführen sicherheitsbezogener Aufgaben
- Adressieren der Verbesserungsaktion mit einer Drittanbieteranwendung oder -software oder einer alternativen Gegenmaßnahmen

Einige Verbesserungsmaßnahmen geben nur Punkte, wenn sie vollständig abgeschlossen sind. Einige geben Teilpunkte, wenn sie für einige Geräte oder Benutzer abgeschlossen sind. Wenn Sie eine der Verbesserungsmaßnahmen nicht ausführen können oder möchten, können Sie das Risiko oder das verbleibende Risiko akzeptieren.

Wenn Sie über eine Lizenz für eines der unterstützten Microsoft-Produkte verfügen, werden Empfehlungen für diese Produkte erhalten. Wir zeigen Ihnen den vollständigen Satz möglicher Verbesserungen für ein Produkt, unabhängig von der Lizenz edition, dem Abonnement oder dem Plan. Auf diese Weise können Sie bewährte Methoden für die Sicherheit verstehen und Ihre Bewertung verbessern. Ihre absolute Sicherheitshaltung, dargestellt durch Secure Score, bleibt unabhängig davon, welche Lizenzen Ihre Organisation für ein bestimmtes Produkt besitzt, gleich. Bitte bedenken Sie: Sicherheit sollte mit Benutzerfreundlichkeit in Einklang gebracht werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung.

Ihre Bewertung wird in Echtzeit aktualisiert, um die Informationen auf den Seiten Visualisierung und Verbesserungsmaßnahmen darzustellen. Sicherheitsbewertung wird auch täglich synchronisiert, um Systemdaten zu Ihren erreichten Punkten für jede Aktion zu erhalten.

### <a name="key-scenarios"></a>Schlüsselszenarien

- [Überprüfen Ihrer aktuellen Bewertung](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Vergleichen Ihrer Bewertung mit Organisationen wie Ihrer](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Anzeigen von Verbesserungsmaßnahmen und Festlegen eines Aktionsplans](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Initiieren von Arbeitsflüssen zur Untersuchung oder Implementierung](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>Wie Verbesserungsmaßnahmen bewertet werden

Jede Verbesserungsaktion hat einen Wert von 10 Punkten oder weniger, und die meisten werden auf binäre Weise erzielt. Wenn Sie die Verbesserungsaktion implementieren, z. B. eine neue Richtlinie erstellen oder eine bestimmte Einstellung aktivieren, erhalten Sie 100 % der Punkte. Bei anderen Verbesserungsmaßnahmen werden Punkte als Prozentsatz der Gesamtkonfiguration gegeben.

Eine Verbesserungsaktion beispielsweise besagt, dass Sie 10 Punkte erhalten, indem Sie alle Benutzer mit mehrstufiger Authentifizierung schützen. Sie haben nur 50 von insgesamt 100 Benutzern geschützt, sodass Sie eine Teilpunktzahl von 5 Punkten erhalten (50 geschützte /100 insgesamt * 10 max. Pts = 5 Pts).

### <a name="products-included-in-secure-score"></a>Produkte in Sicherheitsbewertung

Derzeit gibt es Empfehlungen für die folgenden Produkte:

- Microsoft 365 (einschließlich Exchange Online)
- Azure Active Directory
- Microsoft Defender für Endpunkt
- Microsoft Defender for Identity
- Cloud-App-Sicherheit
- Microsoft Teams

Empfehlungen für andere Sicherheitsprodukte werden in Kürze verfügbar sein. Die Empfehlungen umfassen nicht alle Angriffsflächen, die mit jedem Produkt verknüpft sind, aber sie sind eine gute Basis. Sie können die Verbesserungsmaßnahmen auch als „über Drittanbieter abgedeckt“ oder „ durch alternative Korrektur abgedeckt“ markieren.

### <a name="security-defaults"></a>Sicherheitsstandards

Microsoft Secure Score hat Verbesserungsmaßnahmen aktualisiert, um Sicherheitseinstellungen [in Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)zu unterstützen, die es einfacher machen, Ihre Organisation mit vorkonfigurierten Sicherheitseinstellungen für häufige Angriffe zu schützen.

Wenn Sie Sicherheitseinstellungen aktivieren, erhalten Sie vollständige Punkte für die folgenden Verbesserungsmaßnahmen:

- Sicherstellen, dass alle Benutzer die mehrstufige Authentifizierung für sicheren Zugriff abschließen können (9 Punkte)
- MFA für Administrative Rollen erforderlich (10 Punkte)
- Aktivieren der Richtlinie zum Blockieren der Legacyauthentifizierung (7 Punkte)

>[!IMPORTANT]
>Sicherheitseinstellungen umfassen Sicherheitsfeatures, die ähnliche Sicherheit wie die Verbesserungsmaßnahmen "Anmelderisikorichtlinie" und "Benutzerrisikorichtlinie" bieten. Anstatt diese Richtlinien über die Sicherheitseinstellungen hinaus zu erstellen, wird empfohlen, ihre Status auf "Durch alternative Gegenmaßnahmen aufgelöst" zu aktualisieren.

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

Mit schreibgeschützten Zugriffen können Sie status oder Notizen für eine Verbesserungsaktion, Bewertungszonen oder benutzerdefinierte Vergleiche nicht bearbeiten.

* Helpdesk-Administrator
* Benutzeradministrator
* Service-Administrator
* Benutzer mit Leseberechtigung für Sicherheitsfunktionen
* Sicherheitsoperator
* Globaler Leser

## <a name="risk-awareness"></a>Risikobewusstsein

Microsoft Secure Score ist eine numerische Zusammenfassung Ihrer Sicherheitslage basierend auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsbezogenen Messungen. Es handelt sich nicht um eine absolute Maßeinheit für die Wahrscheinlichkeit, dass Ihr System oder Ihre Daten verletzt werden. Sie stellt vielmehr das Ausmaß dar, in dem Sie Sicherheitskontrollen in Ihrer Microsoft-Umgebung übernommen haben, um das Risiko einer Verletzung zu kompensieren. Kein Onlinedienst ist immun gegen Sicherheitsverletzungen, und die Bewertung der Sicherheit sollte nicht als Garantie gegen Sicherheitsverletzungen interpretiert werden.

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, teilen Sie uns dies mit, indem Sie in der [Community für Sicherheit, Datenschutz und & veröffentlichen.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Zugreifen auf Ihren Sicherheitsstatus](microsoft-secure-score-improvement-actions.md)
- [Nachverfolgen Ihres Microsoft Secure Score-Verlaufs und Erreichen von Zielen](microsoft-secure-score-history-metrics-trends.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
- [Neuerungen](microsoft-secure-score-whats-new.md)