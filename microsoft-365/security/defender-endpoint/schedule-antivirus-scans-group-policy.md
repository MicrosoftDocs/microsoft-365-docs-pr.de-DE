---
title: Planen von Antivirusscans mithilfe von Gruppenrichtlinien
description: Verwenden von Gruppenrichtlinien zum Einrichten von Antivirenscans
keywords: Schnellscan, vollständiger Scan, Zeitplan, Gruppenrichtlinie, Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 6f6018ec8b514234ab4f98e3d5416b472ff88739
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879744"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a>Planen von Antivirusscans mithilfe von Gruppenrichtlinien

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

In diesem Artikel wird beschrieben, wie Sie geplante Scans mithilfe von Gruppenrichtlinien konfigurieren. Weitere Informationen zum Planen von Scans und zu Scantypen finden Sie unter [Konfigurieren geplanter schneller oder vollständiger Microsoft Defender Antivirus Scans.](schedule-antivirus-scans.md) 

## <a name="configure-antivirus-scans-using-group-policy"></a>Konfigurieren von Antivirusscans mithilfe von Gruppenrichtlinien

1. Wechseln Sie auf dem Computer für die Gruppenrichtlinienverwaltung im Gruppenrichtlinien-Editor zu **administrativen Vorlagen** für die Computerkonfiguration  >    >  **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Überprüfung.**

2. Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.

3. Geben Sie Einstellungen für das Gruppenrichtlinienobjekt an, und wählen Sie dann **OK** aus. 

4. Wiederholen Sie die Schritte 1 bis 4 für jede Einstellung, die Sie konfigurieren möchten.

5. Stellen Sie Das Gruppenrichtlinienobjekt wie gewohnt bereit. Wenn Sie Hilfe zu Gruppenrichtlinienobjekten benötigen, lesen [Sie Erstellen eines Gruppenrichtlinienobjekts .](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)

> [!TIP]
> Weitere Informationen finden Sie unter ["Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen"](manage-protection-update-schedule-microsoft-defender-antivirus.md) und ["Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern".](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="group-policy-settings-for-scheduling-scans"></a>Gruppenrichtlinieneinstellungen für die Planung von Scans

| Standort | Einstellung | Beschreibung | Standardeinstellung (falls nicht konfiguriert) |
|:---|:---|:---|:---|
| Überprüfung | Angeben des Für einen geplanten Scan zu verwendenden Scantyps | Schnellscan |
| Überprüfung | Angeben des Wochentags, an dem eine geplante Überprüfung ausgeführt werden soll | Geben Sie den Tag (oder nie) an, an dem eine Überprüfung ausgeführt werden soll. | Nie |
| Überprüfung | Angeben der Tageszeit zum Ausführen eines geplanten Scans | Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 1 Uhr ein). | 2:00 Uhr |
| wurzel | Zufällige Zeitplanung für geplante Aufgaben |In Microsoft Defender Antivirus die Startzeit des Scans in ein beliebiges Intervall zwischen 0 und 4 Stunden zufällig festlegen. <p>In [SCEP](/mem/intune/protect/certificates-scep-configure)randomisieren Sie Scans in ein beliebiges Intervall plus oder minus 30 Minuten. Dies kann bei virtuellen Computern oder VDI-Bereitstellungen hilfreich sein. | Aktiviert |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a>Gruppenrichtlinieneinstellungen für die Planung von Scans, wenn ein Endpunkt nicht verwendet wird

| Standort | Einstellung | Beschreibung | Standardeinstellung (falls nicht konfiguriert) |
|:---|:---|:---|:---|
| Überprüfung | Starten Sie den geplanten Scan nur, wenn der Computer aktiviert ist, aber nicht verwendet wird | Geplante Scans werden nur ausgeführt, wenn der Computer aktiviert ist, aber nicht verwendet wird. | Aktiviert |

> [!NOTE]
> Wenn Sie Scans für Zeiten planen, in denen Endpunkte nicht verwendet werden, berücksichtigen Scans nicht die CPU-Drosselungskonfiguration und nutzen die verfügbaren Ressourcen, um den Scan so schnell wie möglich abzuschließen.

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a>Gruppenrichtlinieneinstellungen für die Planung von Überprüfungen, die für die Wartung erforderlich sind

| Standort | Einstellung | Beschreibung | Standardeinstellung (falls nicht konfiguriert) |
|---|---|---|---|
| Sanierung | Geben Sie den Wochentag an, an dem ein geplanter vollständiger Scan ausgeführt werden soll, um die Korrektur abzuschließen. | Geben Sie den Tag (oder nie) an, an dem eine Überprüfung ausgeführt werden soll. | Nie |
| Sanierung | Geben Sie die Tageszeit an, zu der ein geplanter vollständiger Scan ausgeführt werden soll, um die Wartung abzuschließen. | Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 01:00 Uhr ein) | 2:00 Uhr |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a>Gruppenrichtlinieneinstellungen für die Planung von täglichen Scans

| Standort | Einstellung | Beschreibung | Standardeinstellung (falls nicht konfiguriert) |
|:---|:---|:---|:---|
| Überprüfung | Angeben des Intervalls zum Ausführen von Schnellscans pro Tag | Geben Sie an, wie viele Stunden vor dem nächsten Schnellscan verstrichen sein sollen. Wenn Sie beispielsweise alle zwei Stunden ausführen möchten, geben Sie **2** ein, geben Sie einmal täglich **24** ein. Geben Sie **0** ein, um nie einen täglichen Schnellscan auszuführen. | Nie |
| Überprüfung | Angeben der Zeit für einen täglichen Schnellscan | Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 01:00 Uhr ein) | 2:00 Uhr |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a>Gruppenrichtlinieneinstellungen für die Planung von Scans nach Schutzupdates

| Standort | Einstellung | Beschreibung | Standardeinstellung (falls nicht konfiguriert)|
|:---|:---|:---|:---|
| Signaturupdates | Aktivieren des Scans nach dem Security Intelligence-Update | Eine Überprüfung erfolgt unmittelbar nach dem Herunterladen eines neuen Schutzupdates. | Aktiviert |

