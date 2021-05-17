---
title: Migrieren von McAfee zu Microsoft Defender for Endpoint
description: Wechseln Sie von McAfee zu Microsoft Defender for Endpoint. In diesem Artikel finden Sie eine Übersicht.
keywords: migration, Microsoft Defender for Endpoint, edr
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
- m365solution-mcafeemigrate
- m365solution-overview
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 3d26e2c134f5f9794f7acd41e49c27bd9f331153
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932643"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a>Migrieren von McAfee zu Microsoft Defender for Endpoint

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Wenn Sie planen, von McAfee Endpoint Security (McAfee) zu [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender for Endpoint) zu wechseln, sind Sie an der richtigen Stelle. Verwenden Sie diesen Artikel als Leitfaden.


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="Übersicht über die Migration von McAfee zu Defender for Endpoint":::

Wenn Sie von McAfee zu Defender for Endpoint wechseln, beginnen Sie mit Ihrer McAfee-Lösung im aktiven Modus, konfigurieren Defender for Endpoint im passiven Modus, onboard zu Defender for Endpoint, und legen Sie dann Defender for Endpoint auf den aktiven Modus und McAfee entfernt.

## <a name="the-migration-process"></a>Der Migrationsprozess

Wenn Sie von McAfee zu Microsoft Defender for Endpoint wechseln, führen Sie einen Prozess durch, der in drei Phasen unterteilt werden kann: Vorbereiten, Einrichten und Onboarding. 

![Migrationsphasen – Vorbereiten des Setups onboard](images/phase-diagrams/migration-phases.png)

|Phase |Beschreibung |
|--|--|
|[Vorbereiten der Migration](mcafee-to-microsoft-defender-prepare.md) |Während der [**Vorbereitungsphase**](mcafee-to-microsoft-defender-prepare.md) aktualisieren Sie die Geräte Ihrer Organisation, erhalten Microsoft Defender for Endpoint, planen Ihre Rollen und Berechtigungen und gewähren Zugriff auf Microsoft Defender Security Center. Außerdem konfigurieren Sie den Geräteproxy und die Interneteinstellungen, um die Kommunikation zwischen den Geräten Ihrer Organisation und Microsoft Defender for Endpoint zu ermöglichen. |
|[Einrichten von Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-setup.md) |Während [](mcafee-to-microsoft-defender-setup.md) der Setupphase aktivieren Sie Microsoft Defender Antivirus und stellen sicher, dass es sich im passiven Modus befindet, und Sie konfigurieren Einstellungen & Ausschlüssen für Microsoft Defender Antivirus, Microsoft Defender for Endpoint und McAfee. Außerdem erstellen Sie Gerätegruppen, Sammlungen und Organisationseinheiten. Schließlich konfigurieren Sie Ihre Antischalwarerichtlinien und Echtzeitschutzeinstellungen.|
|[Onboarding bei Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-onboard.md) |Während der [**Onboardphase**](mcafee-to-microsoft-defender-onboard.md) integrieren Sie Ihre Geräte in Microsoft Defender for Endpoint und überprüfen, ob diese Geräte mit Microsoft Defender for Endpoint kommunizieren. Zuletzt deinstallieren Sie McAfee, und stellen Sie sicher, dass Microsoft Defender Antivirus & Microsoft Defender for Endpoint im aktiven Modus ist. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Was ist in Microsoft Defender for Endpoint enthalten?

In diesem Migrationshandbuch konzentrieren [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) wir uns auf schutz und [EDR](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) der nächsten Generation als Ausgangspunkt für den Wechsel zu Microsoft Defender for Endpoint. Microsoft Defender for Endpoint umfasst jedoch viel mehr als Antivirus- und Endpunktschutz. Microsoft Defender für Endpunkt ist eine einheitliche Plattform für präventiven Schutz, die Erkennung nach einem Angriff, die automatisierte Untersuchung und Reaktion. In der folgenden Tabelle sind die Features und Funktionen in Microsoft Defender for Endpoint zusammengefasst. 

| Feature/Funktion | Beschreibung |
|---|---|
| [Bedrohungs- und Sicherheitsrisikomanagement](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt): | Mithilfe & Sicherheitsrisikomanagement Bedrohungsschutzfunktionen können Sie Schwachstellen auf Ihren Endpunkten (z. B. Geräten) identifizieren, bewerten und beheben. |
| [Verringerung der Angriffsfläche](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction): | Regeln zur Reduzierung der Angriffsfläche schützen die Geräte und Anwendungen Ihrer Organisation vor Cyberangriffen und Angriffen. |
| [Schutz der nächsten Generation](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | Der Schutz der nächsten Generation umfasst Microsoft Defender Antivirus, um Bedrohungen und Schadsoftware zu blockieren. |
| [Erkennung und Reaktion am Endpunkt](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | Erkennungs- und Reaktionsfunktionen für Endpunkte erkennen, untersuchen und reagieren auf Angriffsversuche und aktive Verstöße.  |
| [Erweiterte Suche](advanced-hunting-overview.md) | Erweiterte Suchesfunktionen ermöglichen Es Ihrem Sicherheitsteam, Indikatoren und Entitäten bekannter oder potenzieller Bedrohungen zu finden. |
| [Verhaltensbasiertes Blockieren und Eindämmen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | Verhaltensblockierungs- und -eindämmungsfunktionen helfen, Bedrohungen basierend auf ihrem Verhalten und ihren Prozessstrukturen zu identifizieren und zu beenden, selbst wenn die Bedrohung mit der Ausführung begonnen hat. |
| [Automatisierte Untersuchung und Behebung](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | Automatisierte Untersuchungs- und Reaktionsfunktionen untersuchen Warnungen und ergreifen sofortige Abhilfemaßnahmen, um Verstöße zu beheben. |
| [Bedrohungssuche](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft-Bedrohungsexperten) | Bedrohungssuchen bieten Sicherheitsteams Überwachung und Analyse auf Expertenebene, um sicherzustellen, dass kritische Bedrohungen nicht übersehen werden. |

**Möchten Sie mehr erfahren? Weitere [Informationen finden Sie unter Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).**

## <a name="next-step"></a>Nächster Schritt

- Fahren Sie mit [Prepare for your migration fort.](mcafee-to-microsoft-defender-prepare.md)
