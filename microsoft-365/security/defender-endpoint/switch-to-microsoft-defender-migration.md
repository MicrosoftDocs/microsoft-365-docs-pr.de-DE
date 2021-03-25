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
ms.date: 02/11/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 2c6029a1aada8f5f5fb27723c868f28c3de6f8aa
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218652"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a>Wechseln von einer Nicht-Microsoft-Endpunktlösung zu Microsoft Defender for Endpoint

Wenn Sie planen, von einer Nicht-Microsoft-Lösung für den Endpunktschutz zu Microsoft Defender for Endpoint (Defender for [Endpoint)](https://docs.microsoft.com/windows/security/threat-protection) zu wechseln, sind Sie an der richtigen Stelle. Verwenden Sie diesen Artikel als Leitfaden.

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
|[Einrichten von Microsoft Defender for Endpoint](switch-to-microsoft-defender-setup.md) |Während [  ](switch-to-microsoft-defender-setup.md)der Setupphase aktivieren Sie Microsoft Defender Antivirus und stellen sicher, dass es sich im passiven Modus befindet, und Sie konfigurieren Einstellungen & Ausschlüssen für Microsoft Defender Antivirus, Microsoft Defender for Endpoint und Ihre vorhandene Endpunktschutzlösung. Außerdem erstellen Sie Gerätegruppen, Sammlungen und Organisationseinheiten. Schließlich konfigurieren Sie Ihre Antischalwarerichtlinien und Echtzeitschutzeinstellungen.|
|[Onboarding bei Microsoft Defender for Endpoint](switch-to-microsoft-defender-onboard.md) |Während [der **Onboardphase**](switch-to-microsoft-defender-onboard.md)integrieren Sie Ihre Geräte in Microsoft Defender for Endpoint und überprüfen, ob diese Geräte mit Microsoft Defender for Endpoint kommunizieren. Zuletzt deinstallieren Sie Ihre vorhandene Endpunktschutzlösung, und stellen Sie sicher, dass sich der Schutz über Microsoft Defender Antivirus & Microsoft Defender for Endpoint im aktiven Modus befindet. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Was ist in Microsoft Defender for Endpoint enthalten?

In diesem Migrationshandbuch konzentrieren wir uns [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) auf [Schutz-](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) und Endpunkterkennungs- und Reaktionsfunktionen der nächsten Generation als Ausgangspunkt für den Wechsel zu Microsoft Defender for Endpoint. Microsoft Defender for Endpoint umfasst jedoch viel mehr als Antivirus- und Endpunktschutz. Microsoft Defender für Endpunkt ist eine einheitliche Plattform für präventiven Schutz, die Erkennung nach einem Angriff, die automatisierte Untersuchung und Reaktion. In der folgenden Tabelle sind die Features und Funktionen in Microsoft Defender for Endpoint zusammengefasst. 

| Feature/Funktion | Beschreibung |
|---|---|
| [Sicherheitsrisikoverwaltung & Bedrohungen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | Funktionen & zur Verwaltung von Sicherheitslücken helfen, Schwachstellen auf Ihren Endpunkten (z. B. Geräten) zu identifizieren, zu bewerten und zu beheben. |
| [Reduzierung der Angriffsfläche](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | Regeln zur Reduzierung der Angriffsfläche schützen die Geräte und Anwendungen Ihrer Organisation vor Cyberangriffen und Angriffen. |
| [Schutz der nächsten Generation](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | Der Schutz der nächsten Generation umfasst Microsoft Defender Antivirus, um Bedrohungen und Schadsoftware zu blockieren. |
| [Endpunkterkennung und -antwort](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | Erkennungs- und Reaktionsfunktionen für Endpunkte erkennen, untersuchen und reagieren auf Angriffsversuche und aktive Verstöße.  |
| [Erweiterte Suche](advanced-hunting-overview.md) | Erweiterte Suchesfunktionen ermöglichen Es Ihrem Sicherheitsteam, Indikatoren und Entitäten bekannter oder potenzieller Bedrohungen zu finden. |
| [Verhaltensblockierung und -eindämmung](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | Verhaltensblockierungs- und -eindämmungsfunktionen helfen, Bedrohungen basierend auf ihrem Verhalten und ihren Prozessstrukturen zu identifizieren und zu beenden, selbst wenn die Bedrohung mit der Ausführung begonnen hat. |
| [Automatisierte Untersuchung und Behebung](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | Automatisierte Untersuchungs- und Reaktionsfunktionen untersuchen Warnungen und ergreifen sofortige Abhilfemaßnahmen, um Verstöße zu beheben. |
| [Threat Hunting Service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts) | Bedrohungssuchen bieten Sicherheitsteams Überwachung und Analyse auf Expertenebene, um sicherzustellen, dass kritische Bedrohungen nicht übersehen werden. |

**Möchten Sie mehr erfahren? Weitere [Informationen finden Sie unter Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).**

## <a name="next-step"></a>Nächster Schritt

- Fahren Sie mit [Prepare for your migration fort.](switch-to-microsoft-defender-prepare.md)
