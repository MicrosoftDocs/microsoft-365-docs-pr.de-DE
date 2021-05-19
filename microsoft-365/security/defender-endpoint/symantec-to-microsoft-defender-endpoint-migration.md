---
title: Migrieren von Symantec zu Microsoft Defender for Endpoint
description: Hier erhalten Sie eine Übersicht über den Wechsel von Symantec zu Microsoft Defender for Endpoint
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
- m365solution-symantecmigrate
- m365solution-overview
ms.topic: article
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 62a916fcf89432a512ada1b85002cce401e4dd23
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530898"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a>Migrieren von Symantec zu Microsoft Defender for Endpoint
Wenn Sie planen, von Symantec Endpoint Protection (Symantec) zu [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Microsoft Defender for Endpoint) zu wechseln, sind Sie an der richtigen Stelle. Verwenden Sie diesen Artikel als Leitfaden.

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
|[Vorbereiten der Migration](symantec-to-microsoft-defender-atp-prepare.md) |Während der **Vorbereitungsphase** aktualisieren Sie die Geräte Ihrer Organisation, erhalten Microsoft Defender for Endpoint, planen Ihre Rollen und Berechtigungen und gewähren Zugriff auf Microsoft Defender Security Center. Außerdem konfigurieren Sie den Geräteproxy und die Interneteinstellungen, um die Kommunikation zwischen den Geräten Ihrer Organisation und Defender for Endpoint zu ermöglichen. |
|[Einrichten von Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-setup.md) |Während der **Setupphase** aktivieren Sie Microsoft Defender Antivirus und legen ihn in den passiven Modus. Sie konfigurieren auch Einstellungen & Ausschlüssen für Microsoft Defender Antivirus und Symantec Endpoint Protection. Anschließend erstellen Sie Ihre Gerätegruppen, Sammlungen und Organisationseinheiten. Schließlich konfigurieren Sie Ihre Antischalwarerichtlinien und Echtzeitschutzeinstellungen.|
|[Onboarding bei Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-onboard.md) |Während der **Onboard-Phase** integrieren Sie Ihre Geräte in Microsoft Defender for Endpoint, bestätigen, dass Microsfot Defender Antivirus im passiven Modus ausgeführt wird, und vergewissern Sie sich, dass Ihre Endpunkte mit Defender for Endpoint kommunizieren. Anschließend deinstallieren Sie Symantec, und stellen Sie sicher, dass Defender for Endpoint ordnungsgemäß funktioniert. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Was ist in Microsoft Defender for Endpoint enthalten?

In diesem Migrationshandbuch konzentrieren [](microsoft-defender-antivirus-in-windows-10.md) wir uns auf schutz und [EDR](overview-endpoint-detection-response.md) der nächsten Generation als Ausgangspunkt für den Wechsel zu Microsoft Defender for Endpoint. Microsoft Defender for Endpoint umfasst jedoch viel mehr als Antivirus- und Endpunktschutz. Microsoft Defender für Endpunkt ist eine einheitliche Plattform für präventiven Schutz, die Erkennung nach einem Angriff, die automatisierte Untersuchung und Reaktion. In der folgenden Tabelle sind die Features und Funktionen in Microsoft Defender for Endpoint zusammengefasst. 

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

**Möchten Sie mehr erfahren? Weitere [Informationen finden Sie unter Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Nächster Schritt

- Fahren Sie mit [Prepare for your migration fort.](symantec-to-microsoft-defender-atp-prepare.md)
