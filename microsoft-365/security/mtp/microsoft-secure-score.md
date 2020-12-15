---
title: Microsoft-Sicherheitsbewertung
description: Beschreibt Microsoft Secure Score im Microsoft 365 Security Center, wie Sie Ihre Sicherheitsposition verbessern und welche Sicherheitsadministratoren erwarten können.
keywords: Microsoft Secure Score, Secure Score, Office 365 Secure Score, Microsoft Security Score, Microsoft 365 Security Center, Improvement Actions
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
ms.openlocfilehash: 7fe5be065ee45700a1f08a39c8050757c3843f7b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682571"
---
# <a name="microsoft-secure-score"></a>Microsoft-Sicherheitsbewertung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Die Microsoft-Sicherheitsbewertung ist ein Maßstab für den Sicherheitsstatus eines Unternehmens. Eine höhere Zahl bedeutet, dass mehr Verbesserungsmaßnahmen vorgenommen wurden. Sie finden sie unter https://security.microsoft.com/securescore im [Microsoft 365 Security Center ](overview-security-center.md).

Wenn Sie die Secure Score-Empfehlungen befolgen, können Sie Ihre Organisation vor Bedrohungen schützen. Von einem zentralisierten Dashboard im Microsoft 365 Security Center aus können Organisationen die Sicherheit Ihrer Microsoft 365-Identitäten,-Apps und-Geräte überwachen und daran arbeiten.

Sicherheitsbewertung hilft Organisationen auf diese Arten:  

* Berichtet über den aktuellen Sicherheitsstatus der Organisation.
* Verbessert den Sicherheitsstatus durch Auffindbarkeit, Transparenz, Anleitung und Kontrolle.  
* Ermöglicht Vergleiche mit Benchmarks und erstellt KPIs (Key Performance Indicators).

Organisationen erhalten Zugriff auf zuverlässige Visualisierungen von Metriken und Trends, die Integration in andere Microsoft-Produkte, einen Vergleich mit ähnlichen Organisationen und vieles mehr. Die Bewertung zeigt auch, wenn Lösungen von Drittanbietern empfohlene Maßnahmen behandelt haben.

![Startseite der Sicherheitsbewertung](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Funktionsweise

Für die folgenden Aktionen werden Punkte angegeben:

- Konfigurieren von empfohlenen Sicherheitsfeatures
- Durchführen von sicherheitsbezogenen Aufgaben
- Beheben der Verbesserungs Aktion mit einer Anwendung oder Software eines Drittanbieters oder einer alternativen Minderung

Einige Verbesserungs Aktionen geben nur dann Punkte an, wenn Sie vollständig abgeschlossen sind. Einige geben partielle Punkte an, wenn Sie für einige Geräte oder Benutzer abgeschlossen sind. Wenn Sie eine der Verbesserungs Aktionen nicht ausführen können oder möchten, können Sie das Risiko oder das verbleibende Risiko akzeptieren.

Wenn Sie über eine Lizenz für eines der unterstützten Microsoft-Produkte verfügen, werden Ihnen Empfehlungen für diese Produkte angezeigt. Wir zeigen Ihnen den vollständigen Umfang möglicher Verbesserungen für ein Produkt, unabhängig von Lizenzedition, Abonnement oder Plan. Auf diese Weise können Sie bewährte Methoden für die Sicherheit verstehen und Ihre Punktzahl verbessern. Ihre absolute Sicherheitsposition, dargestellt durch Secure Score, bleibt gleich, unabhängig davon, welche Lizenzen Ihre Organisation für ein bestimmtes Produkt besitzt. Bitte bedenken Sie: Sicherheit sollte mit Benutzerfreundlichkeit in Einklang gebracht werden, und nicht jede Empfehlung funktioniert für Ihre Umgebung.

Ihre Bewertung wird in Echtzeit aktualisiert, um die Informationen auf den Seiten Visualisierung und Verbesserungsmaßnahmen darzustellen. Sicherheitsbewertung wird auch täglich synchronisiert, um Systemdaten zu Ihren erreichten Punkten für jede Aktion zu erhalten.

### <a name="key-scenarios"></a>Schlüsselszenarien

- [Überprüfen der aktuellen Bewertung](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Vergleichen Sie Ihre Punktzahl mit Organisationen wie Ihrem](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Anzeigen von Verbesserungs Aktionen und Festlegen eines Aktionsplans](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Initiieren von Workflows zur Untersuchung oder Implementierung](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Microsoft 365 Security Center und ServiceNow-Integration](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>Wie Verbesserungsmaßnahmen bewertet werden

Jede Verbesserungs Aktion ist 10 oder mehr Punkte Wert, und die meisten werden auf binäre Weise bewertet. Wenn Sie die Verbesserungs Aktion implementieren, wie Sie eine neue Richtlinie erstellen oder eine bestimmte Einstellung aktivieren, erhalten Sie 100% der Punkte. Bei anderen Verbesserungsmaßnahmen werden Punkte als Prozentsatz der Gesamtkonfiguration gegeben.

Beispielsweise besagt eine Verbesserungs Aktion, dass Sie 10 Punkte erhalten, indem Sie alle Ihre Benutzer mit mehrstufiger Authentifizierung schützen. Sie haben nur 50 von 100 Gesamtanzahl der Benutzer geschützt, sodass Sie einen Teil der Punktzahl von 5 Punkten erhalten (50 Protected/100 total * 10 max PTS = 5 Pkt.).

### <a name="products-included-in-secure-score"></a>Produkte in Sicherheitsbewertung

Derzeit gibt es Empfehlungen für Microsoft 365 (einschließlich Exchange Online), Azure Active Directory, Microsoft Defender for Endpoint, Microsoft Defender for Identity und Cloud App Security. Empfehlungen für andere Sicherheitsprodukte werden in Kürze verfügbar sein. Die Empfehlungen decken nicht alle Angriffsflächen ab, die jedem Produkt zugeordnet sind, sind jedoch ein guter Ausgangswert. Sie können die Verbesserungsmaßnahmen auch als „über Drittanbieter abgedeckt“ oder „ durch alternative Korrektur abgedeckt“ markieren.

### <a name="security-defaults"></a>Sicherheitsstandards

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

Mit schreibgeschütztem Zugriff können Sie den Status oder die Notizen für eine Verbesserungs Aktion nicht bearbeiten, Bewertungs Zonen bearbeiten oder benutzerdefinierte Vergleiche bearbeiten.

* Helpdesk-Administrator
* Benutzeradministrator
* Service-Administrator
* Benutzer mit Leseberechtigung für Sicherheitsfunktionen
* Sicherheitsoperator
* Globaler Leser

## <a name="risk-awareness"></a>Risikobewusstsein

Microsoft Secure Score ist eine numerische Zusammenfassung Ihrer Sicherheitsposition basierend auf Systemkonfigurationen, Benutzerverhalten und anderen sicherheitsbezogenen Messungen. Es ist keine absolute Maßeinheit dafür, wie wahrscheinlich ein System oder Daten verletzt werden. Sie stellt vielmehr das Ausmaß dar, in dem Sie Sicherheitssteuerelemente in Ihrer Microsoft-Umgebung übernommen haben, um das Risiko von Verstößen auszugleichen. Kein Onlinedienst ist vollständig immun gegen Sicherheitsverletzungen, und Secure Score sollte nicht als Garantie gegen Sicherheitsverletzungen in irgendeiner Weise interpretiert werden.

## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Wenn Sie Probleme haben, lassen Sie es uns wissen, indem Sie in der [Sicherheits-, Datenschutz-& Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) -Community veröffentlichen. Die Communitybeiträge werden überwacht und wir sind ständig bemüht, Ihnen zu helfen.

## <a name="related-resources"></a>Verwandte Ressourcen

- [Zugreifen auf Ihren Sicherheitsstatus](microsoft-secure-score-improvement-actions.md)
- [Verfolgen des Microsoft Secure Score-Verlaufs und erreichen der Ziele](microsoft-secure-score-history-metrics-trends.md)
- [Was in Kürze verfügbar ist](microsoft-secure-score-whats-coming.md)
- [Neuerungen](microsoft-secure-score-whats-new.md)
