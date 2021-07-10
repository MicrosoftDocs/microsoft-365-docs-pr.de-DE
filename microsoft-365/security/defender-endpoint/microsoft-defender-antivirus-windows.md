---
title: Microsoft Defender Antivirus
description: Erfahren Sie, wie Sie Microsoft Defender Antivirus, integrierte Antischadsoftware und Antivirenschutz verwalten, konfigurieren und verwenden.
keywords: Microsoft Defender Antivirus, Windows Defender, Antischadsoftware, SCEP, System Center Endpoint Protection, System Center Configuration Manager, Virus, Schadsoftware, Bedrohung, Erkennung, Schutz, Sicherheit
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: ceaf694d8b81e6b06ffe74efc4ad3d4d73471752
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322759"
---
# <a name="microsoft-defender-antivirus-in-windows"></a>Microsoft Defender Antivirus in Windows

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus ist eine wichtige Schutzkomponente der nächsten Generation in Microsoft Defender für Endpunkt. Dieser Schutz vereint maschinelles Lernen, Big Data-Analysen, tiefgehende Untersuchungen zur Bedrohungsresistenz und die Microsoft-Cloudinfrastruktur zum Schutz von Geräten (oder Endpunkten) in Ihrer Organisation. Microsoft Defender Antivirus ist in Windows integriert und sorgt in Kombination mit Microsoft Defender für Endpunkt für Schutz auf Ihrem Gerät und in der Cloud. 

## <a name="compatibility-with-other-antivirus-products"></a>Kompatibilität mit anderen Antivirenprodukten

Wenn Sie auf Ihrem Gerät ein Antiviren-/Antischadsoftware-Produkt verwenden, das nicht von Microsoft stammt, können Sie möglicherweise Microsoft Defender Antivirus im passiven Modus zusammen mit dieser Antivirenlösung ausführen. Dies hängt vom verwendeten Betriebssystem und davon ab, ob Ihr Gerät in Defender für Endpunkt eingebunden ist. Weitere Informationen finden Sie unter [Kompatibilität mit Microsoft Defender Antivirus](microsoft-defender-antivirus-compatibility.md).

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a>Vergleich von aktivem, passivem und deaktiviertem Modus

In der folgenden Tabelle wird erläutert, was zu erwarten ist, wenn sich Microsoft Defender Antivirus im aktiven, passiven oder deaktivierten Modus befindet.

| Modus  | Folge  |
|---------|---------|
| Aktiver Modus | Im aktiven Modus wird Microsoft Defender Antivirus als primäre Antiviren-Anwendung auf dem Gerät verwendet. Dateien werden überprüft, Maßnahmen gegen Bedrohungen ergriffen, und erkannte Bedrohungen werden in den Sicherheitsberichten Ihrer Organisation und in Ihrer Windows-Sicherheit-App aufgeführt. |
| Passiver Modus | Im passiven Modus wird Microsoft Defender Antivirus nicht als primäre Antiviren-Anwendung auf dem Gerät verwendet. Dateien werden überprüft, und erkannte Bedrohungen werden gemeldet jedoch nicht von Microsoft Defender Antivirus behoben.   |
| Deaktiviert oder deinstalliert  | Bei Deaktivierung oder Deinstallation wird Microsoft Defender Antivirus nicht verwendet. Dateien werden nicht überprüft, und gegen Bedrohungen werden keine Maßnahmen ergriffen. Im Allgemeinen wird davon abgeraten, Microsoft Defender Antivirus zu deaktivieren oder zu deinstallieren.  |

Weitere Informationen finden Sie unter [Kompatibilität mit Microsoft Defender Antivirus](microsoft-defender-antivirus-compatibility.md).

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a>Überprüfen des Status von Microsoft Defender Antivirus auf Ihrem Gerät

Sie können den Status von Microsoft Defender Antivirus auf Ihrem Gerät auf unterschiedliche Weise überprüfen, z. B. über die Windows-Sicherheit-App oder mithilfe von Windows PowerShell.

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a>Verwenden der Windows-Sicherheit-App zum Überprüfen des Status von Microsoft Defender Antivirus

1. Wählen Sie auf Ihrem Windows-Gerät das Startmenü aus, und beginnen Sie mit der Eingabe von `Security`. Öffnen Sie dann die Windows-Sicherheit-App in den angezeigten Ergebnissen.

2. Wählen Sie **Viren- und Bedrohungsschutz** aus.

3. Wählen Sie unter **Einstellungen für Viren- & Bedrohungsschutz** die Option **Einstellungen verwalten** aus.

Der Name Ihrer Antiviren-/Antischadsoftware-Lösung wird auf der Einstellungsseite angezeigt.

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a>Verwenden von PowerShell zum Überprüfen des Status von Microsoft Defender Antivirus

1. Wählen Sie das Startmenü aus, und beginnen Sie mit der Eingabe von `PowerShell`. Öffnen Sie dann Windows PowerShell in den angezeigten Ergebnissen.

2. Geben Sie `Get-MpComputerStatus` ein.

3. Sehen Sie sich in der Ergebnisliste die Zeile **AMRunningMode** an.

   - **Normal** bedeutet, dass Microsoft Defender Antivirus im aktiven Modus ausgeführt wird.
   - **Passive mode** bedeutet, dass Microsoft Defender Antivirus ausgeführt wird, aber nicht das primäre Antiviren-/Antischadsoftwareprodukt auf Ihrem Gerät ist.
   - **EDR Block Mode** bedeutet, dass Microsoft Defender Antivirus ausgeführt wird und eine als "EDR im Blockmodus" bezeichnete Funktion in Microsoft Defender für Endpunkt aktiviert ist. (Siehe [Endpunkterkennung und -reaktion (Endpoint Detection and Response, EDR) im Blockmodus](edr-in-block-mode.md).)
   - **SxS Passive Mode** bedeutet, dass Microsoft Defender Antivirus neben einem anderen Antiviren-/Antischadsoftwareprodukt im passiven Modus ausgeführt wird, und dass Ihr Gerät nicht in Microsoft Defender für Endpunkt eingebunden ist. In diesem Fall findet im Hinblick auf Microsoft Defender Antivirus ein eingeschränkter regelmäßiger Scan statt. Weitere Informationen finden Sie unter [Verwendung von eingeschränkten periodischen Scans in Microsoft Defender Antivirus](limited-periodic-scanning-microsoft-defender-antivirus.md).

Weitere Informationen zum PowerShell-Cmdlet "Get-MpComputerStatus" finden Sie im Referenzartikel [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).

## <a name="get-your-antivirusantimalware-platform-updates"></a>Beziehen von Antiviren-/Antischadsoftware-Plattformupdates

Es ist wichtig, Microsoft Defender Antivirus oder andere Antiviren-/Antischadsoftware-Lösungen auf dem neuesten Stand zu halten. Microsoft veröffentlicht regelmäßige Updates, um sicherzustellen, dass Ihre Geräte über die neueste Technologie zum Schutz vor neuer Schadsoftware und Angriffstechniken verfügen. Weitere Informationen finden Sie unter [Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Baselines](manage-updates-baselines-microsoft-defender-antivirus.md). 

## <a name="see-also"></a>Siehe auch

- [Microsoft Defender Antivirus auf Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [Verwaltung und Konfiguration von Microsoft Defender Antivirus](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus-Schutz beurteilen](evaluate-microsoft-defender-antivirus.md)
