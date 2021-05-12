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
ms.date: 05/10/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 0a8e1f11cdb9d7363e6b47d1e671c546e5eac9b4
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327502"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a>Wechseln von einer Nicht-Microsoft-Endpunktlösung zu Microsoft Defender for Endpoint

Wenn Sie planen, von einer Nicht-Microsoft-Lösung für den Endpunktschutz zu Microsoft Defender for Endpoint (Defender for [Endpoint)](microsoft-defender-endpoint.md) zu wechseln, sind Sie an der richtigen Stelle. Verwenden Sie diesen Artikel als Leitfaden.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Übersicht über die Migration zu Defender for Endpoint":::

Wenn Sie zu Defender for Endpoint wechseln, beginnen Sie mit Ihrer Nicht-Microsoft-Lösung im aktiven Modus, konfigurieren Defender für Endpoint im passiven Modus, onboard zu Defender für Endpoint, und legen Sie dann Defender für Endpoint auf den aktiven Modus und entfernen Sie die Nicht-Microsoft-Lösung.

> [!TIP]
> - Wenn Sie derzeit McAfee Endpoint Security (McAfee) verwenden, lesen Sie Migrieren von [McAfee zu Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md).
> - Wenn Sie derzeit Symantec Endpoint Protection (Symantec) verwenden, lesen [Sie Migrieren von Symantec zu Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md).

## <a name="the-migration-process"></a>Der Migrationsprozess

Wenn Sie zu Microsoft Defender for Endpoint wechseln, führen Sie einen Prozess durch, der in drei Phasen unterteilt werden kann, wie in der folgenden Tabelle beschrieben:

![Migrationsphasen – Vorbereiten, Einrichten, Onboarding](images/phase-diagrams/migration-phases.png)

|Phase |Beschreibung |
|--|--|
|[Vorbereiten der Migration](switch-to-microsoft-defender-prepare.md) |Während [der **Vorbereitungsphase**](switch-to-microsoft-defender-prepare.md)aktualisieren Sie die Geräte Ihrer Organisation, erhalten Microsoft Defender for Endpoint, planen Ihre Rollen und Berechtigungen und gewähren Zugriff auf das Microsoft Defender Security Center. Außerdem konfigurieren Sie den Geräteproxy und die Interneteinstellungen, um die Kommunikation zwischen den Geräten Ihrer Organisation und Microsoft Defender for Endpoint zu ermöglichen. |
|[Einrichten von Microsoft Defender for Endpoint](switch-to-microsoft-defender-setup.md) |Während [der **Setupphase**](switch-to-microsoft-defender-setup.md)aktivieren Sie Microsoft Defender Antivirus und stellen sicher, dass es sich im passiven Modus befindet. Sie konfigurieren auch Einstellungen & für Microsoft Defender Antivirus und Ihre vorhandene Endpunktschutzlösung. Anschließend erstellen Sie Ihre Gerätegruppen, Sammlungen und Organisationseinheiten. Schließlich konfigurieren Sie Ihre Antischalwarerichtlinien und Echtzeitschutzeinstellungen.|
|[Onboarding bei Microsoft Defender for Endpoint](switch-to-microsoft-defender-onboard.md) |Während [der **Onboardphase**](switch-to-microsoft-defender-onboard.md)integrieren Sie Ihre Geräte in Microsoft Defender for Endpoint und überprüfen, ob diese Geräte mit Microsoft Defender for Endpoint kommunizieren. Zuletzt deinstallieren Sie Ihre vorhandene Endpunktschutzlösung, und stellen Sie sicher, dass sich der Schutz über Microsoft Defender Antivirus & Microsoft Defender for Endpoint im aktiven Modus befindet. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Was ist in Microsoft Defender for Endpoint enthalten?

In diesem Migrationshandbuch konzentrieren wir uns [](overview-endpoint-detection-response.md) auf [Schutz-](microsoft-defender-antivirus-in-windows-10.md) und Endpunkterkennungs- und Reaktionsfunktionen der nächsten Generation als Ausgangspunkt für den Wechsel zu Microsoft Defender for Endpoint. Microsoft Defender for Endpoint umfasst jedoch viel mehr als Antivirus- und Endpunktschutz. Microsoft Defender für Endpunkt ist eine einheitliche Plattform für präventiven Schutz, die Erkennung nach einem Angriff, die automatisierte Untersuchung und Reaktion. In der folgenden Tabelle sind die Features und Funktionen in Microsoft Defender for Endpoint zusammengefasst. 

| Feature/Funktion | Beschreibung |
|---|---|
| [Bedrohungs- und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md): | Funktionen & zur Verwaltung von Sicherheitslücken helfen, Schwachstellen auf Ihren Endpunkten (z. B. Geräten) zu identifizieren, zu bewerten und zu beheben. |
| [Verringerung der Angriffsfläche](overview-attack-surface-reduction.md): | Regeln zur Reduzierung der Angriffsfläche schützen die Geräte und Anwendungen Ihrer Organisation vor Cyberangriffen und Angriffen. |
| [Schutz der nächsten Generation](microsoft-defender-antivirus-in-windows-10.md) | Der Schutz der nächsten Generation umfasst Microsoft Defender Antivirus, um Bedrohungen und Schadsoftware zu blockieren. |
| [Erkennung und Reaktion am Endpunkt](overview-endpoint-detection-response.md) | Erkennungs- und Reaktionsfunktionen für Endpunkte erkennen, untersuchen und reagieren auf Angriffsversuche und aktive Verstöße.  |
| [Erweiterte Suche](advanced-hunting-overview.md) | Erweiterte Suchesfunktionen ermöglichen Es Ihrem Sicherheitsteam, Indikatoren und Entitäten bekannter oder potenzieller Bedrohungen zu finden. |
| [Verhaltensbasiertes Blockieren und Eindämmen](behavioral-blocking-containment.md) | Verhaltensblockierungs- und -eindämmungsfunktionen helfen, Bedrohungen basierend auf ihrem Verhalten und ihren Prozessstrukturen zu identifizieren und zu beenden, selbst wenn die Bedrohung mit der Ausführung begonnen hat. |
| [Automatisierte Untersuchung und Behebung](automated-investigations.md) | Automatisierte Untersuchungs- und Reaktionsfunktionen untersuchen Warnungen und ergreifen sofortige Abhilfemaßnahmen, um Verstöße zu beheben. |
| [Threat Hunting Service](microsoft-threat-experts.md) (Microsoft Threat Experts) | Bedrohungssuchen bieten Sicherheitsteams Überwachung und Analyse auf Expertenebene, um sicherzustellen, dass kritische Bedrohungen nicht übersehen werden. |

**Möchten Sie mehr erfahren? Weitere [Informationen finden Sie unter Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Nächster Schritt

- Fahren Sie mit [Prepare for your migration fort.](switch-to-microsoft-defender-prepare.md)
