---
title: Was Microsoft-Sicherheitsbewertung in Kürze verfügbar ist
description: Beschreibt Microsoft-Sicherheitsbewertung im Microsoft 365 Security Center, erläutert die Berechnung von Details und was Sicherheitsadministratoren erwarten dürfen.
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
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372003"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Was Microsoft-Sicherheitsbewertung in Kürze verfügbar ist

Um Microsoft-Sicherheitsbewertung zu einem besseren Anlaufpunkt für Ihren Sicherheitsstatus zu machen und die Benutzerfreundlichkeit zu verbessern, nehmen wir in naher Zukunft einige Änderungen vor. Ihre Bewertung und die maximale Punktzahl werden geändert. Dies bedeutet jedoch nicht, dass sich Ihr Sicherheitsstatus ändert.

Wenn Sie mehr über die neuesten Änderungen wissen möchten, lesen Sie [Neuerungen in Microsoft-Sicherheitsbewertung](microsoft-secure-score.md#whats-new).

## <a name="march-16th-2020"></a>16. März 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Verbesserungsmaßnahmen, die die Erwartungen an zuverlässige Messungen nicht erfüllen oder keine nützlichen Darstellung des Sicherheitsstatus bieten, wurden entfernt.

Um sicherzustellen, dass Microsoft-Sicherheitsbewertung aussagekräftig ist und jede Verbesserungsmaßnahme messbar und zuverlässig ist, entfernen wir die folgenden Verbesserungsmaßnahmen.

- Benutzerdokumente in OneDrive for Business speichern
- Office 365 ATP-Richtlinien für sichere Anlagen einrichten
- Sichere Links zum Überprüfen von URLs in Office 365 einrichten
- Postfachdelegierung nicht zulassen
- Anonyme Gastfreigabelinks für Websites und Dokumente zulassen
- Cloud App Security-Konsole aktivieren
- Ablaufzeit für externe Freigabelinks konfigurieren

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Sicherheitsstandards für Azure AD-Verbesserungsmaßnahmen unterstützen

Microsoft-Sicherheitsbewertung aktualisiert Verbesserungsmaßnahmen zur Unterstützung von [Sicherheitsstandards in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), die es einfacher machen, Ihre Organisation mit vorkonfigurierten Sicherheitseinstellungen für häufige Angriffe zu schützen.

Dies betrifft die folgenden Verbesserungsmaßnahmen:

- Sicherstellen, dass alle Benutzer die mehrstufige Authentifizierung für sicheren Zugriff durchführen können
- MFA für Administratorrollen erzwingen
- Richtlinie zum Blockieren veralteter Authentifizierung aktivieren
