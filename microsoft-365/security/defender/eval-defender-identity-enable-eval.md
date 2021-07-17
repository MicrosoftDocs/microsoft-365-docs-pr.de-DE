---
title: Aktivieren sie die Evaluierungsumgebung für Microsoft Defender for Identity, richten Sie die MDI-Instanz ein, installieren und konfigurieren Sie den MDI-Sensor, und lassen Sie den MDI-Sensor lokale Administratoren erkennen.
description: Richten Sie Microsoft Defender for Identity in Microsoft 365 Defender Testumgebung oder Pilotumgebung ein, indem Sie & Konfigurieren des Sensors installieren und lokale Administratoren auf anderen Computern ermitteln.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458073"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a>Aktivieren der Evaluierungsumgebung für Microsoft Defender for Identity

**Gilt für:**
- Microsoft 365 Defender

Dieser Artikel ist [Schritt 2 von 2](eval-defender-identity-overview.md) beim Einrichten der Evaluierungsumgebung für Microsoft Defender for Identity. Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-identity-overview.md)

Führen Sie die folgenden Schritte aus, um Ihre Microsoft Defender for Identity-Umgebung einzurichten. 

![Schritte zum Aktivieren von Microsoft Defender for Identity in der Microsoft Defender-Evaluierungsumgebung](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [Schritt 1. Einrichten der Defender for Identity-Instanz](#step-1-set-up-the-defender-for-identity-instance)
- [Schritt 2. Installieren und Konfigurieren des Sensors](#step-2-install-and-configure-the-sensor)
- [Schritt 3. Konfigurieren von Ereignisprotokoll- und Proxyeinstellungen auf Computern mit dem Sensor](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [Schritt 4. Zulassen, dass Defender for Identity lokale Administratoren auf anderen Computern identifiziert](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a>Schritt 1. Einrichten der Defender for Identity-Instanz

Melden Sie sich beim Defender for Identity-Portal an, um Ihre Instanz zu erstellen, und verbinden Sie diese Instanz mit Ihrer Active Directory-Umgebung. 

|  |Schritt     |Weitere Informationen  |
|---------|---------|---------|
|1     | Erstellen der Defender for Identity-Instanz        | [Schnellstart: Erstellen Ihrer Microsoft Defender for Identity-Instanz](/defender-for-identity/install-step1)        |
|2     | Verbinden der Defender for Identity-Instanz zu Ihrer Active Directory-Gesamtstruktur   | [Schnellstart: Verbinden zu Ihrer Active Directory-Gesamtstruktur](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a>Schritt 2. Installieren und Konfigurieren des Sensors

Laden Sie als Nächstes den Defender for Identity-Sensor auf den Domänencontrollern und AD FS-Servern in Ihrer lokalen Umgebung herunter, installieren und konfigurieren Sie diesen.

|  |Schritt     |Weitere Informationen  |
|---------|---------|---------|
|1     | Ermitteln Sie, wie viele Microsoft Defender for Identity-Sensoren Sie benötigen.        | [Planen der Kapazität für Microsoft Defender for Identity](/defender-for-identity/capacity-planning)   |
|2     | Herunterladen des Sensoreinrichtungspakets  |  [Schnellstart: Herunterladen des Setuppakets für den Microsoft Defender for Identity-Sensor](/defender-for-identity/install-step3)   |
|3     | Installieren des Defender for Identity-Sensors    |  [Schnellstart: Installieren des Microsoft Defender for Identity-Sensors](/defender-for-identity/install-step4)       |
|4      | Konfigurieren des Sensors       |  [Konfigurieren von Microsoft Defender for Identity-Sensoreinstellungen ](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a>Schritt 3: Konfigurieren von Ereignisprotokoll- und Proxyeinstellungen auf Computern mit dem Sensor

Konfigurieren Sie auf den Computern, auf denen Sie den Sensor installiert haben, Windows Ereignisprotokollsammlung und Internetproxyeinstellungen, um erkennungsfunktionen zu aktivieren und zu verbessern.

|  |Schritt     |Weitere Informationen  |
|---------|---------|---------|
|1     | Konfigurieren Windows Ereignisprotokollsammlung         | [Konfigurieren Windows-Ereignissammlung](/defender-for-identity/configure-windows-event-collection)        |
|2     | Konfigurieren von Internetproxyeinstellungen        | [Konfigurieren von Endpunktproxy- und Internetkonnektivitätseinstellungen für Ihren Microsoft Defender for Identity Sensor](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a>Schritt 4. Zulassen, dass Defender for Identity lokale Administratoren auf anderen Computern identifiziert

Die Lateral Movement Path-Erkennung von Microsoft Defender for Identity basiert auf Abfragen, die lokale Administratoren auf bestimmten Computern identifizieren. Diese Abfragen werden mit dem SAM-R-Protokoll unter Verwendung des Defender for Identity Service-Kontos ausgeführt. 

Um sicherzustellen Windows Clients und Server Ihrem Defender for Identity-Konto die Ausführung von SAM-R gestatten, muss eine Änderung an der Gruppenrichtlinie vorgenommen werden, um das Defender for Identity-Dienstkonto zusätzlich zu den konfigurierten Konten hinzuzufügen, die in der Netzwerkzugriffsrichtlinie aufgeführt sind. Stellen Sie sicher, dass Gruppenrichtlinien auf alle Computer **außer Domänencontrollern** angewendet werden.

Anweisungen hierzu finden Sie unter [Konfigurieren von Microsoft Defender for Identity für Remoteaufrufe an SAM.](/defender-for-identity/install-step8-samr) 

## <a name="next-steps"></a>Nächste Schritte

Schritt 3 von 3: Testen von [Microsoft Defender for Identity](eval-defender-identity-pilot.md)

Kehren Sie zur Übersicht für ["Auswerten von Microsoft Defender for Identity"](eval-defender-identity-overview.md) zurück.

Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)