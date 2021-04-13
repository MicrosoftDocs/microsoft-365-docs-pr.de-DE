---
title: Konfigurieren von Überprüfungsoptionen für Microsoft Defender AV
description: Sie können Microsoft Defender AV so konfigurieren, dass E-Mail-Speicherdateien, Back-up- oder Reparsepunkte, Netzwerkdateien und archivierte Dateien (z. B. ZIP-Dateien) gescannt werden.
keywords: Erweiterte Scans, Überprüfung, E-Mail, Archiv, ZIP, Rar, Archiv, Erneute Überprüfung
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 625c84e79efe53cae2bc8f511726ad3f384ea505
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690457"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Konfigurieren von Microsoft Defender Antivirus-Überprüfungsoptionen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Konfigurieren von Überprüfungsoptionen mithilfe von Microsoft Intune

Weitere Informationen finden Sie [unter Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and Microsoft Defender Antivirus device restriction settings for Windows [10 in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Konfigurieren von Überprüfungsoptionen mithilfe von Microsoft Endpoint Manager

Weitere [Informationen zum Konfigurieren von](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) Microsoft Endpoint Manager (current branch) finden Sie unter Erstellen und Bereitstellen von Antischalwarerichtlinien: Überprüfen Sie die Einstellungen.

## <a name="use-group-policy-to-configure-scanning-options"></a>Konfigurieren von Überprüfungsoptionen mithilfe von Gruppenrichtlinien

So konfigurieren Sie die in der folgenden Tabelle beschriebenen Gruppenrichtlinieneinstellungen:

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.

3. Erweitern Sie die Struktur auf **Windows-Komponenten >**  Microsoft Defender Antivirus und dann den in der folgenden Tabelle angegebenen Speicherort.

4. Doppelklicken Sie auf die **Richtlinieneinstellung,** wie in der folgenden Tabelle angegeben, und legen Sie die Option auf die gewünschte Konfiguration fest. Klicken **Sie auf OK,** und wiederholen Sie dies für alle anderen Einstellungen.

Beschreibung | Speicherort und Einstellung | Standardeinstellung (wenn nicht konfiguriert) | `Set-MpPreference`PowerShell-Parameter oder WMI-Eigenschaft für `MSFT_MpPreference` Klasse
---|---|---|---
E-Mail-Überprüfung Siehe [E-Mail-Überprüfungseinschränkungen](#ref1)| Überprüfen > Aktivieren der E-Mail-Überprüfung | Deaktiviert | `-DisableEmailScanning`
Überprüfen [von Überprüfungspunkten](/windows/win32/fileio/reparse-points) | Überprüfen > Aktivieren der Überprüfung von Reparaturpunkts | Deaktiviert | Nicht verfügbar
Überprüfen zugeordneter Netzwerklaufwerke | Scan > Ausführen der vollständigen Überprüfung auf zugeordneten Netzwerklaufwerken | Deaktiviert | `-DisableScanningMappedNetworkDrivesForFullScan`
 Überprüfen von Archivdateien (z. B. ZIP- oder RAR-Dateien). Die [Ausschlussliste für Erweiterungen](configure-extension-file-exclusions-microsoft-defender-antivirus.md) hat Vorrang vor dieser Einstellung. | Scannen > Archivdateien | Aktiviert | `-DisableArchiveScanning`
Überprüfen von Dateien im Netzwerk | Scannen > Netzwerkdateien | Deaktiviert | `-DisableScanningNetworkFiles`
Scannen von verpackten ausführbaren Dateien | Scannen > von verpackten ausführbaren Dateien | Aktiviert | Nicht verfügbar
Scannen von Wechseldatenträgern nur bei vollständigen Scans | Überprüfen > von Wechseldatenträgern | Deaktiviert | `-DisableRemovableDriveScanning`
Angeben der Ebene der Unterordner in einem zu überprüfenden Archivordner | Scan > Die maximale Tiefe zum Scannen von Archivdateien angeben | 0 | Nicht verfügbar
 Geben Sie die maximale CPU-Auslastung (als Prozentsatz) während einer Überprüfung an. Hinweis: Dies ist keine harte Grenze, sondern eine Anleitung für das Scanmodul, dieses Maximum im Durchschnitt nicht zu überschreiten. | Scan > Geben Sie den maximalen Prozentsatz der CPU-Auslastung während eines Scans an. | 50 |  `-ScanAvgCPULoadFactor`
 Geben Sie die maximale Größe (in Kilobyte) von Archivdateien an, die gescannt werden sollen. Der **Standardwert, 0**, gilt ohne Beschränkung. | Scan > Geben Sie die maximale Größe der zu scannende Archivdateien an. | Keine Begrenzung | Nicht verfügbar
 Konfigurieren einer niedrigen CPU-Priorität für geplante Scans | Scan > Konfigurieren einer niedrigen CPU-Priorität für geplante Scans | Deaktiviert | Nicht verfügbar
 
> [!NOTE]
> Wenn der Echtzeitschutz aktiviert ist, werden Die Dateien überprüft, bevor auf sie zugegriffen und ausgeführt wird. Der Überprüfungsbereich umfasst alle Dateien, einschließlich Dateien auf bereitgestellten Wechselmedien, z. B. USB-Laufwerke. Wenn das Gerät, das die Überprüfung durchführen, über echtzeit- oder Zugriffsschutz verfügt, enthält die Überprüfung auch Netzwerkfreigaben.

## <a name="use-powershell-to-configure-scanning-options"></a>Konfigurieren von Überprüfungsoptionen mithilfe von PowerShell

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwalten von Microsoft Defender Antivirus mit [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>Konfigurieren von Überprüfungsoptionen mithilfe von WMI

Informationen zur Verwendung von WMI-Klassen finden Sie [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a>Einschränkungen bei der E-Mail-Überprüfung

Die E-Mail-Überprüfung ermöglicht das Scannen von E-Mail-Dateien, die von Outlook und anderen E-Mail-Clients bei Bedarf und geplanten Scans verwendet werden. Eingebettete Objekte in einer E-Mail-Datei (z. B. Anlagen und archivierte Dateien) werden ebenfalls überprüft. Die folgenden Dateiformattypen können gescannt und behoben werden:

- DBX
- MBX
- MIME

Pst-Dateien, die von Outlook 2003 oder älter verwendet werden (wobei der Archivtyp auf Nicht-Unicode festgelegt ist), werden ebenfalls überprüft, aber Windows Defender kann bedrohungen, die in PST-Dateien erkannt wurden, nicht behoben werden.

Wenn Microsoft Defender Antivirus eine Bedrohung innerhalb einer E-Mail erkennt, werden Ihnen die folgenden Informationen zur Verfügung stehen, die Ihnen bei der Identifizierung der gefährdeten E-Mails helfen, sodass Sie die Bedrohung manuell abwehren können:

- E-Mail-Betreff
- Anlagenname

## <a name="related-topics"></a>Verwandte Themen

- [Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus-Scans und -Korrekturen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Konfigurieren und Ausführen von Bedarfsscans von Microsoft Defender Antivirus](run-scan-microsoft-defender-antivirus.md)
- [Konfigurieren geplanter Microsoft Defender Antivirus-Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)