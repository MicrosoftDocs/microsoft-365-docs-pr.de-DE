---
title: Wechseln von nicht von Microsoft stammendem Endpunktschutz zu Microsoft Defender für Endpunkt
description: Wechseln Sie zu Microsoft Defender für Endpunkt. In diesem Artikel finden Sie eine Übersicht.
keywords: Migration, Windows Defender Advanced Endpoint Protection, für Endpunkt, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-overview
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 06/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 2953103cb3812103740f98a6db5b8f4d369731e3
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930307"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>Wechseln von nicht von Microsoft stammendem Endpunktschutz zu Microsoft Defender für Endpunkt

Wenn Sie überlegen, von einer nicht von Microsoft stammenden Endpunktschutzlösung zu [Microsoft Defender für Endpunkt](microsoft-defender-endpoint.md) (Defender für Endpunkt) zu wechseln, sind Sie am richtigen Ort. Verwenden Sie diesen Artikel als Leitfaden.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Übersicht über die Migration zu Defender für Endpunkt":::

Wenn Sie zu Defender für Endpunkt wechseln, beginnen Sie mit ihrer Nicht-Microsoft-Lösung, die im aktiven Modus arbeitet. Anschließend konfigurieren Sie Defender für Endpunkt im passiven Modus und integrieren Ihre Geräte in Defender für Endpunkt. Als Nächstes legen Sie Defender für Endpunkt auf den aktiven Modus fest. Schließlich entfernen Sie die nicht von Microsoft stammende Lösung.

## <a name="the-migration-process"></a>Der Migrationsprozess

Der Prozess der Migration zu Defender für Endpunkt kann in drei Phasen unterteilt werden, wie in der folgenden Tabelle beschrieben:

![Migrationsphasen – Vorbereiten, Einrichten, Onboarding](images/phase-diagrams/migration-phases.png)

|Phase |Beschreibung |
|--|--|
|[Vorbereiten der Migration](switch-to-microsoft-defender-prepare.md) |Während [der **Vorbereitungsphase:**](switch-to-microsoft-defender-prepare.md) <p>1. Aktualisieren Sie die Geräte Ihrer Organisation. <p>2. Rufen Sie Defender für Endpunkt ab. <p>3. Planen Sie Ihre Rollen und Berechtigungen, und gewähren Sie Zugriff auf die Microsoft Defender Security Center. <p>4. Konfigurieren Sie Ihre Geräteproxy- und Interneteinstellungen, um die Kommunikation zwischen den Geräten Ihrer Organisation und Defender für Endpunkt zu ermöglichen. |
|[Einrichten von Defender für Endpunkt](switch-to-microsoft-defender-setup.md) |Während [der **Einrichtungsphase:**](switch-to-microsoft-defender-setup.md) <p>1. Microsoft Defender Antivirus aktivieren/neu installieren. <p>2. Konfigurieren von Defender für Endpunkt. <p>3. Fügen Sie Defender für Endpunkt zur Ausschlussliste für Ihre vorhandene Lösung hinzu. <p>4. Fügen Sie Ihre vorhandene Lösung der Ausschlussliste für Microsoft Defender Antivirus hinzu. <p>5. Richten Sie Gerätegruppen, Sammlungen und Organisationseinheiten ein. <p>6. Konfigurieren Sie Ihre Antischadsoftwarerichtlinien und Echtzeitschutzeinstellungen.|
|[Onboarding in Defender für Endpunkt](switch-to-microsoft-defender-onboard.md) |Während [der **Onboarding-Phase:**](switch-to-microsoft-defender-onboard.md) <p>1. Integrieren Sie Ihre Geräte in Defender für Endpunkt. <p>2. Führen Sie einen Erkennungstest aus. <p>3. Vergewissern Sie sich, dass Microsoft Defender Antivirus im passiven Modus ausgeführt wird. <p>4. Abrufen von Updates für Microsoft Defender Antivirus. <p>5. Deinstallieren Sie Ihre vorhandene Endpunktschutzlösung. <p>6. Stellen Sie sicher, dass Defender für Endpunkt ordnungsgemäß funktioniert. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Was ist in Microsoft Defender für Endpunkt enthalten?

In diesem Migrationshandbuch konzentrieren wir uns auf [die Schutz-](microsoft-defender-antivirus-in-windows-10.md) und [EDR](overview-endpoint-detection-response.md) Funktionen der nächsten Generation als Ausgangspunkt für den Wechsel zu Defender für Endpunkt. Defender für Endpunkt umfasst jedoch viel mehr als Antivirus- und Endpunktschutz. Defender für Endpunkt ist eine einheitliche Plattform für präventiven Schutz, Erkennung nach einem Angriff, automatisierte Untersuchung und Reaktion. In der folgenden Tabelle sind die Features und Funktionen in Defender für Endpunkt zusammengefasst. 

| Feature/Funktion | Beschreibung |
|---|---|
| [Bedrohungs- und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md): | Bedrohungs-& Sicherheitsrisikomanagement-Funktionen helfen dabei, Schwachstellen auf Ihren Endpunkten (z. B. Geräte) zu erkennen, zu bewerten und zu beheben. |
| [Verringerung der Angriffsfläche](overview-attack-surface-reduction.md): | Regeln zur Verringerung der Angriffsfläche tragen dazu bei, die Geräte und Anwendungen Ihrer Organisation vor Cyberbedrohungen und Angriffen zu schützen. |
| [Schutz der nächsten Generation](microsoft-defender-antivirus-in-windows-10.md) | Der Schutz der nächsten Generation umfasst Microsoft Defender Antivirus, um Bedrohungen und Schadsoftware zu blockieren. |
| [Erkennung und Reaktion am Endpunkt](overview-endpoint-detection-response.md) | Endpunkterkennungs- und -reaktionsfunktionen erkennen, untersuchen und reagieren auf Angriffsversuche und aktive Sicherheitsverletzungen.  |
| [Erweiterte Suche](advanced-hunting-overview.md) | Erweiterte Suchfunktionen ermöglichen Es Ihrem Sicherheitsteam, Indikatoren und Entitäten bekannter oder potenzieller Bedrohungen zu finden. |
| [Verhaltensbasiertes Blockieren und Eindämmen](behavioral-blocking-containment.md) | Funktionen zum Blockieren und Eindämmen von Verhaltensweisen helfen dabei, Bedrohungen basierend auf ihren Verhaltensweisen und Prozessstrukturen zu erkennen und zu stoppen, selbst wenn die Bedrohung mit der Ausführung begonnen hat. |
| [Automatisierte Untersuchung und Korrektur](automated-investigations.md) | Automatisierte Untersuchungs- und Reaktionsfunktionen untersuchen Warnungen und ergreifen sofortige Abhilfemaßnahmen, um Verstöße zu beheben. |
| [Dienst für die Bedrohungssuche](microsoft-threat-experts.md) (Microsoft-Bedrohungsexperten) | Dienste für die Bedrohungssuche bieten Sicherheitsteams eine Überwachung und Analyse auf Expertenebene, um sicherzustellen, dass kritische Bedrohungen nicht übersehen werden. |

**Möchten Sie mehr erfahren? Siehe [Defender für Endpunkt.](microsoft-defender-endpoint.md)**

## <a name="next-step"></a>Nächster Schritt

- Fahren Sie mit [der Vorbereitung ihrer Migration](switch-to-microsoft-defender-prepare.md)fort.
