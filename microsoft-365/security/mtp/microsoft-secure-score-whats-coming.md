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
ms.openlocfilehash: 234ae17ab31d56d1bbd65f1aa8ed29475e9cd155
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583715"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Was Microsoft-Sicherheitsbewertung in Kürze verfügbar ist

Um [Microsoft Secure Score](microsoft-secure-score.md) zu einem besseren Vertreter ihrer Sicherheitsposition zu machen und die Benutzerfreundlichkeit zu verbessern, werden wir in naher Zukunft einige Änderungen vornehmen. Ihre Bewertung und die maximale Punktzahl werden geändert. Dies bedeutet jedoch nicht, dass sich Ihr Sicherheitsstatus ändert.

Wenn Sie mehr über die neuesten Änderungen wissen möchten, lesen Sie [Neuerungen in Microsoft-Sicherheitsbewertung](microsoft-secure-score.md#whats-new).

## <a name="april-21st-2020"></a>21. April 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Verbesserungsmaßnahmen, die die Erwartungen an zuverlässige Messungen nicht erfüllen oder keine nützlichen Darstellung des Sicherheitsstatus bieten, wurden entfernt.

Um sicherzustellen, dass Microsoft-Sicherheitsbewertung aussagekräftig ist und jede Verbesserungsmaßnahme messbar und zuverlässig ist, entfernen wir die folgenden Verbesserungsmaßnahmen.

- IRM-Schutz auf Dokumente anwenden
- Richtlinien zur Verhinderung von Datenverlust anwenden

### <a name="adding-azure-ad-improvement-action-to-preview"></a>Hinzufügen von Azure AD Verbesserungs Aktion zur Vorschau

Hinzufügen der folgenden Azure Active Directory-Verbesserungs Aktion zur [Vorschauversion von Microsoft Secure Score](microsoft-secure-score-preview.md):

- Nicht zulassen, dass Benutzer nicht verwalteten Anwendungen zustimmen (zurzeit in der veröffentlichten Version verfügbar)

### <a name="adding-azure-atp-improvement-actions-to-preview"></a>Hinzufügen von Azure ATP-Verbesserungs Aktionen zur Vorschau

Hinzufügen der folgenden Azure Advanced Threat Protection-Verbesserungs Aktionen zur [Vorschauversion von Microsoft Secure Score](microsoft-secure-score-preview.md):

- Druckerspoolerdienst auf Domänencontrollern deaktivieren
- Unsichere Kerberos-Delegierungen ändern, um einen Identitätswechsel zu verhindern
- Lokale Administratorkennwörter mit Microsoft LAPS schützen und verwalten
- Risiko des lateralen Bewegungspfads auf sensible Entitäten reduzieren
- Ruhende Konten aus sensiblen Gruppen entfernen
- Unsichere SID-Verlaufsattribute aus Entitäten entfernen
- Unsichere Kontoattribute auflösen
- Offenlegung von Anmeldeinformationen in Klartext verhindern
- Kommunikation über Legacy-Protokolle verhindern
- Verwendung schwacher Verschlüsselung verhindern

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-preview"></a>Unterstützung für Microsoft Defender ATP Threat & Vulnerability Management (TVM) Sicherheitsempfehlungen in der Vorschau

Alle veröffentlichten Sicherheitsempfehlungen von TVM werden nun auch [in der Preview-Version von Microsoft Secure Score](microsoft-secure-score-preview.md)zur Verfügung gestellt.
