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
ms.openlocfilehash: 61f066b2fff2798e78e6379bbca46e48e93ff017
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895441"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Was Microsoft-Sicherheitsbewertung in Kürze verfügbar ist

Um Microsoft-Sicherheitsbewertung zu einem besseren Anlaufpunkt für Ihren Sicherheitsstatus zu machen und die Benutzerfreundlichkeit zu verbessern, nehmen wir in naher Zukunft einige Änderungen vor. Ihre Bewertung und die maximale Punktzahl werden geändert. Dies bedeutet jedoch nicht, dass sich Ihr Sicherheitsstatus ändert.

Wenn Sie mehr über die neuesten Änderungen wissen möchten, lesen Sie [Neuerungen in Microsoft-Sicherheitsbewertung](microsoft-secure-score.md#whats-new).

## <a name="april-21st-2020"></a>21. April 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Verbesserungsmaßnahmen, die die Erwartungen an zuverlässige Messungen nicht erfüllen oder keine nützlichen Darstellung des Sicherheitsstatus bieten, wurden entfernt.

Um sicherzustellen, dass Microsoft-Sicherheitsbewertung aussagekräftig ist und jede Verbesserungsmaßnahme messbar und zuverlässig ist, entfernen wir die folgenden Verbesserungsmaßnahmen.

- Löschen/Blockieren von Konten, die in den letzten 30 Tagen nicht verwendet werden
- Festlegen weniger als 5 globaler Administratoren
- Anwenden von IRM-Schutz auf Dokumente
- Anwenden von Richtlinien zur Verhinderung von Datenverlust

### <a name="adding-additional-control-support-in-the-preview-version"></a>Hinzufügen zusätzlicher Steuerelementunterstützung in der Vorschauversion
- Zulassen, dass Benutzer keine Zustimmung zu nicht verwalteten Anwendungen erteilen (derzeit in der veröffentlichten Version verfügbar)

#### <a name="support-for-additional-microsoft-cloud-app-security-improvement-actions"></a>Unterstützung für zusätzliche Microsoft Cloud App-Sicherheits Verbesserungs Aktionen
- Deaktivieren des Druck Warteschlangendiensts auf Domänencontrollern
- Ändern unsicherer Kerberos-Delegierungen zum Verhindern eines Identitätswechsels
- Schützen und Verwalten von lokalen Administratorkennwörtern mit Microsoft Laps
- Verringern des Risikos von lateralen Bewegungspfaden auf vertrauliche Entitäten
- Entfernen ruhender Konten aus vertraulichen Gruppen
- Entfernen von ungesicherten sid-Verlaufsattributen aus Entitäten
- Auflösen von ungesicherten Kontoattributen
- Stop Clear Text Credentials Exposure
- Kommunikation mit Legacy Protokollen beenden
- Schwache Verschlüsselungs Verwendung beenden

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a>Unterstützung für Sicherheitsempfehlungen für Microsoft Defender ATP Threat & Vulnerability Management (TVM)
- Alle veröffentlichten Sicherheitsempfehlungen, die von TVM bereitgestellt werden, werden nun auch in Microsoft Secure Score verfügbar sein.
