---
title: Migrieren von Symantec zu Microsoft Defender for Endpoint
description: Hier erhalten Sie eine Übersicht über den Wechsel von Symantec zu Microsoft Defender for Endpoint
keywords: Migration, windows defender advanced threat protection, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
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
- m365solution-symantecmigrate
- m365solution-overview
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 6517359c805bb449d075e401283a79a791461630
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218808"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a>Migrieren von Symantec zu Microsoft Defender for Endpoint
Wenn Sie planen, von Symantec Endpoint Protection (Symantec) zu [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender for Endpoint) zu wechseln, sind Sie an der richtigen Stelle. Verwenden Sie diesen Artikel als Leitfaden.

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

:::image type="content" source="images/symantec-mde-migration.png" alt-text="Übersicht über die Migration von Symantec zu Defender for Endpoint":::

Wenn Sie von Symantec zu Defender for Endpoint wechseln, beginnen Sie mit Ihrer Symantec-Lösung im aktiven Modus, konfigurieren Defender for Endpoint im passiven Modus, onboard zu Defender for Endpoint, und legen Sie dann Defender für Endpoint auf den aktiven Modus und Symantec entfernt.

## <a name="the-migration-process"></a>Der Migrationsprozess

Wenn Sie von Symantec zu Microsoft Defender for Endpoint wechseln, führen Sie einen Prozess durch, der in drei Phasen unterteilt werden kann, wie in der folgenden Tabelle beschrieben:

![Migrationsphasen – Vorbereiten, Einrichten, Onboarding](images/phase-diagrams/migration-phases.png)

|Phase |Beschreibung |
|--|--|
|[Vorbereiten der Migration](symantec-to-microsoft-defender-atp-prepare.md) |Während der **Vorbereitungsphase** erhalten Sie Microsoft Defender for Endpoint, planen Ihre Rollen und Berechtigungen und gewähren Zugriff auf das Microsoft Defender Security Center. Außerdem konfigurieren Sie den Geräteproxy und die Interneteinstellungen, um die Kommunikation zwischen den Geräten Ihrer Organisation und Microsoft Defender for Endpoint zu ermöglichen. |
|[Einrichten von Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-setup.md) |Während der **Setupphase** konfigurieren Sie Einstellungen und Ausschlüsse für Microsoft Defender Antivirus, Microsoft Defender for Endpoint und Symantec Endpoint Protection. Außerdem erstellen Sie Gerätegruppen, Sammlungen und Organisationseinheiten. Schließlich konfigurieren Sie Ihre Antischalwarerichtlinien und Echtzeitschutzeinstellungen.|
|[Onboarding bei Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-onboard.md) |Während der **Onboardphase** integrieren Sie Ihre Geräte in Microsoft Defender for Endpoint und überprüfen, ob diese Geräte mit Microsoft Defender for Endpoint kommunizieren. Zuletzt deinstallieren Sie Symantec, und stellen Sie sicher, dass sich der Schutz über Microsoft Defender for Endpoint im aktiven Modus befindet. |

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

- Fahren Sie mit [Prepare for your migration fort.](symantec-to-microsoft-defender-atp-prepare.md)
