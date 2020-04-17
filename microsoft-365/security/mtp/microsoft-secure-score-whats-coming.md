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
ms.openlocfilehash: 1a5c5ae702f16bbf47be83837cf244cdd64278cd
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541107"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Was Microsoft-Sicherheitsbewertung in Kürze verfügbar ist

Um Microsoft-Sicherheitsbewertung zu einem besseren Anlaufpunkt für Ihren Sicherheitsstatus zu machen und die Benutzerfreundlichkeit zu verbessern, nehmen wir in naher Zukunft einige Änderungen vor. Ihre Bewertung und die maximale Punktzahl werden geändert. Dies bedeutet jedoch nicht, dass sich Ihr Sicherheitsstatus ändert.

Wenn Sie mehr über die neuesten Änderungen wissen möchten, lesen Sie [Neuerungen in Microsoft-Sicherheitsbewertung](microsoft-secure-score.md#whats-new).

## <a name="april-21st-2020"></a>21. April 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Verbesserungsmaßnahmen, die die Erwartungen an zuverlässige Messungen nicht erfüllen oder keine nützlichen Darstellung des Sicherheitsstatus bieten, wurden entfernt.

Um sicherzustellen, dass Microsoft-Sicherheitsbewertung aussagekräftig ist und jede Verbesserungsmaßnahme messbar und zuverlässig ist, entfernen wir die folgenden Verbesserungsmaßnahmen.

- IRM-Schutz auf Dokumente anwenden
- Richtlinien zur Verhinderung von Datenverlust anwenden

### <a name="adding-azure-ad-improvement-action-in-the-preview-version"></a>Hinzufügen von Azure AD Verbesserungs Aktion in der Vorschauversion

- Nicht zulassen, dass Benutzer nicht verwalteten Anwendungen zustimmen (zurzeit in der veröffentlichten Version verfügbar)

### <a name="adding-azure-atp-improvement-actions-in-the-preview-version"></a>Hinzufügen von Azure ATP-Verbesserungs Aktionen in der Vorschauversion

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

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-the-preview-version"></a>Unterstützung für Sicherheitsempfehlungen für Microsoft Defender ATP Threat & Vulnerability Management (TVM) in der Vorschauversion

- Alle von TVM bereitgestellten Sicherheitsempfehlungen sind nun auch in Microsoft-Sicherheitsbewertung verfügbar.
