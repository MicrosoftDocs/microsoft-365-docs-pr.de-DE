---
title: Wechseln von einer Nicht-Microsoft-Endpunktlösung zu Microsoft Defender for Endpoint
description: Wechseln Sie zu Microsoft Defender for Endpoint. In diesem Artikel finden Sie eine Übersicht.
keywords: migration, windows defender advanced endpoint protection, for Endpoint, edr
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
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 013205a1b5b9db204f626a6fe6ab76ad07378558
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538003"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a>Wechseln von einer Nicht-Microsoft-Endpunktlösung zu Microsoft Defender for Endpoint

Wenn Sie planen, von einer Nicht-Microsoft-Lösung für den Endpunktschutz zu Microsoft Defender for Endpoint (Defender for [Endpoint)](microsoft-defender-endpoint.md) zu wechseln, sind Sie an der richtigen Stelle. Verwenden Sie diesen Artikel als Leitfaden.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Übersicht über die Migration zu Defender for Endpoint":::

Wenn Sie zu Defender for Endpoint wechseln, beginnen Sie mit Ihrer Nicht-Microsoft-Lösung im aktiven Modus, konfigurieren Defender für Endpoint im passiven Modus, onboard zu Defender für Endpoint, und legen Sie dann Defender für Endpoint auf den aktiven Modus und entfernen Sie die Nicht-Microsoft-Lösung.

> [!TIP]
> - Wenn Sie derzeit McAfee Endpoint Security (McAfee) verwenden, lesen Sie [Migrieren von McAfee zu Defender for Endpoint](mcafee-to-microsoft-defender-migration.md).
> - Wenn Sie derzeit Symantec Endpoint Protection (Symantec) verwenden, lesen [Sie Migrieren von Symantec zu Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md).

## <a name="the-migration-process"></a>Der Migrationsprozess

Wenn Sie zu Defender for Endpoint wechseln, führen Sie einen Prozess aus, der in drei Phasen unterteilt werden kann, wie in der folgenden Tabelle beschrieben:

![Migrationsphasen – Vorbereiten, Einrichten, Onboarding](images/phase-diagrams/migration-phases.png)

|Phase |Beschreibung |
|--|--|
|[Vorbereiten der Migration](switch-to-microsoft-defender-prepare.md) |Während [der **Vorbereitungsphase**](switch-to-microsoft-defender-prepare.md)aktualisieren Sie die Geräte Ihrer Organisation, erhalten Defender for Endpoint, planen Ihre Rollen und Berechtigungen und gewähren Zugriff auf Microsoft Defender Security Center. Außerdem konfigurieren Sie den Geräteproxy und die Interneteinstellungen, um die Kommunikation zwischen den Geräten Ihrer Organisation und Defender for Endpoint zu ermöglichen. |
|[Einrichten von Defender for Endpoint](switch-to-microsoft-defender-setup.md) |Während [der **Setupphase**](switch-to-microsoft-defender-setup.md)aktivieren Sie Microsoft Defender Antivirus und legen ihn in den passiven Modus. Sie konfigurieren auch Einstellungen & Ausschlüssen für Microsoft Defender Antivirus und Ihre vorhandene Endpunktschutzlösung. Anschließend erstellen Sie Ihre Gerätegruppen, Sammlungen und Organisationseinheiten. Schließlich konfigurieren Sie Ihre Antischalwarerichtlinien und Echtzeitschutzeinstellungen.|
|[Onboarding bei Defender for Endpoint](switch-to-microsoft-defender-onboard.md) |Während [der **Onboardphase**](switch-to-microsoft-defender-onboard.md)onboardieren Sie Ihre Geräte in Defender for Endpoint, bestätigen, dass Microsoft Defender Antivirus im passiven Modus ausgeführt wird, und vergewissern Sie sich, dass Ihre Endpunkte mit Defender for Endpoint kommunizieren. Anschließend deinstallieren Sie Ihre vorhandene Endpunktschutzlösung, und stellen Sie sicher, dass Defender for Endpoint ordnungsgemäß funktioniert. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Was ist in Microsoft Defender for Endpoint enthalten?

In diesem Migrationshandbuch konzentrieren [](microsoft-defender-antivirus-in-windows-10.md) wir uns auf den Schutz der nächsten Generation [und EDR](overview-endpoint-detection-response.md) als Ausgangspunkt für den Wechsel zu Defender for Endpoint. Defender for Endpoint umfasst jedoch viel mehr als Antivirus- und Endpunktschutz. Defender for Endpoint ist eine einheitliche Plattform für vorbeugenden Schutz, erkennung nach Sicherheitsverletzungen, automatisierte Untersuchung und Reaktion. In der folgenden Tabelle sind die Features und Funktionen in Defender for Endpoint zusammengefasst. 

| Feature/Funktion | Beschreibung |
|---|---|
| [Bedrohungs- und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md): | Mithilfe & Sicherheitsrisikomanagement Bedrohungsschutzfunktionen können Sie Schwachstellen auf Ihren Endpunkten (z. B. Geräten) identifizieren, bewerten und beheben. |
| [Verringerung der Angriffsfläche](overview-attack-surface-reduction.md): | Regeln zur Reduzierung der Angriffsfläche schützen die Geräte und Anwendungen Ihrer Organisation vor Cyberangriffen und Angriffen. |
| [Schutz der nächsten Generation](microsoft-defender-antivirus-in-windows-10.md) | Der Schutz der nächsten Generation umfasst Microsoft Defender Antivirus, um Bedrohungen und Schadsoftware zu blockieren. |
| [Erkennung und Reaktion am Endpunkt](overview-endpoint-detection-response.md) | Erkennungs- und Reaktionsfunktionen für Endpunkte erkennen, untersuchen und reagieren auf Angriffsversuche und aktive Verstöße.  |
| [Erweiterte Suche](advanced-hunting-overview.md) | Erweiterte Suchesfunktionen ermöglichen Es Ihrem Sicherheitsteam, Indikatoren und Entitäten bekannter oder potenzieller Bedrohungen zu finden. |
| [Verhaltensbasiertes Blockieren und Eindämmen](behavioral-blocking-containment.md) | Verhaltensblockierungs- und -eindämmungsfunktionen helfen, Bedrohungen basierend auf ihrem Verhalten und ihren Prozessstrukturen zu identifizieren und zu beenden, selbst wenn die Bedrohung mit der Ausführung begonnen hat. |
| [Automatisierte Untersuchung und Behebung](automated-investigations.md) | Automatisierte Untersuchungs- und Reaktionsfunktionen untersuchen Warnungen und ergreifen sofortige Abhilfemaßnahmen, um Verstöße zu beheben. |
| [Bedrohungssuche](microsoft-threat-experts.md) (Microsoft-Bedrohungsexperten) | Bedrohungssuchen bieten Sicherheitsteams Überwachung und Analyse auf Expertenebene, um sicherzustellen, dass kritische Bedrohungen nicht übersehen werden. |

**Möchten Sie mehr erfahren? Weitere Informationen [finden Sie unter Defender for Endpoint](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Nächster Schritt

- Fahren Sie mit [Prepare for your migration fort.](switch-to-microsoft-defender-prepare.md)
