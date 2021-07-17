---
title: Testen Sie Microsoft Defender for Identity, richten Sie Konfigurationsbenchmarks, Standards, Richtlinien und Lernprogramme zum Erkennen und Beheben verschiedener Identitätsbedrohungen wie Reconnaissance, kompromittierte Anmeldeinformationen, laterale Bewegung, Domänendominanz und Exfiltrationswarnungen ein, führen Sie eine Untersuchung von Benutzer-, Computer-, Entitäts- und lateralen Bewegungspfaden durch.
description: Testen Sie Microsoft Defender for Identity, legen Sie Benchmarks fest, nehmen Sie Lernprogramme zu Reconnaissance, kompromittierten Anmeldeinformationen, lateraler Bewegung, Domänendominanz und Exfiltrationswarnungen vor.
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
ms.openlocfilehash: 14c5b9252e980d1f693139393d26b9405cb1b812
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458056"
---
# <a name="pilot-microsoft-defender-for-identity"></a>Pilot-Microsoft Defender for Identity


**Gilt für:**
- Microsoft 365 Defender

Dieser Artikel ist [Schritt 3 von 3](eval-defender-identity-overview.md) beim Einrichten der Evaluierungsumgebung für Microsoft Defender for Identity. Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-identity-overview.md)

Führen Sie die folgenden Schritte aus, um das Pilotprojekt für Microsoft Defender for Identity einzurichten und zu konfigurieren. Beachten Sie, dass die Empfehlungen nicht das Einrichten einer Pilotgruppe umfassen. Die bewährte Methode besteht darin, den Sensor auf allen Servern zu installieren, auf denen Active Directory Domain Services (AD DS) und Active Directory-Verbunddienste (AD FS) ausgeführt werden.

![Schritte zum Hinzufügen von Microsoft Defender for Identity zur Defender-Evaluierungsumgebung](../../media/defender/m365-defender-identity-pilot-steps.png)

In der folgenden Tabelle werden die Schritte in der Abbildung beschrieben.

- [Schritt 1: Konfigurieren von Benchmarkempfehlungen für Ihre Identitätsumgebung](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [Schritt 2: Testen von Funktionen – Exemplarische Anleitungen zum Identifizieren und Beheben verschiedener Angriffstypen ](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a>Schritt 1. Konfigurieren von Benchmarkempfehlungen für Ihre Identitätsumgebung

Microsoft bietet Empfehlungen für Sicherheits-Benchmark für Kunden, die Microsoft Cloud Services verwenden. Der [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) bietet vordefinierte bewährte Methoden und Empfehlungen, um die Sicherheit von Workloads, Daten und Diensten in Azure zu verbessern.

Diese Benchmarkempfehlungen umfassen [Azure-Sicherheitsgrundwerte für Microsoft Defender for Identity.](/security/benchmark/azure/baselines/defender-for-identity-security-baseline) Die Implementierung dieser Empfehlungen kann einige Zeit in Anspruch nehmen, um sie zu planen und zu implementieren. Obwohl diese die Sicherheit Ihrer Identitätsumgebung erheblich erhöhen, sollten sie Sie nicht daran hindern, Microsoft Defender for Identity weiter auszuwerten und zu implementieren. Diese werden hier für Ihr Bewusstsein bereitgestellt.

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a>Schritt 2. Testen von Funktionen – Exemplarische Lernprogramme zum Identifizieren und Beheben verschiedener Angriffstypen

Die Microsoft Defender for Identity-Dokumentation enthält eine Reihe von Lernprogrammen, die den Prozess der Identifizierung und Behebung verschiedener Angriffstypen durchlaufen.

Testen Sie Defender for Identity-Lernprogramme:
- [Reconnaissance-Warnungen](/defender-for-identity/reconnaissance-alerts)
- [Warnungen bei kompromittierten Anmeldeinformationen](/defender-for-identity/compromised-credentials-alerts)
- [Warnungen bei lateralen Bewegungen](/defender-for-identity/lateral-movement-alerts)
- [Domänendominanzwarnungen](/defender-for-identity/domain-dominance-alerts)
- [Exfiltrationswarnungen](/defender-for-identity/exfiltration-alerts)
- [Untersuchen eines Benutzers](/defender-for-identity/investigate-a-user)
- [Untersuchen eines Computers](/defender-for-identity/investigate-a-computer)
- [Untersuchen lateraler Bewegungspfade](/defender-for-identity/investigate-lateral-movement-path)
- [Untersuchen von Entitäten](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a>Nächste Schritte

[Auswerten von Microsoft Defender für Office 365](eval-defender-office-365-overview.md)

Kehren Sie zur Übersicht für ["Auswerten von Microsoft Defender für Office 365"](eval-defender-office-365-overview.md) zurück.

Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)