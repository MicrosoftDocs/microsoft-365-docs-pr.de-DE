---
title: Konfigurieren von Überprüfungsoptionen für Microsoft Defender Antivirus
description: Sie können Microsoft Defender AV so konfigurieren, dass E-Mail-Speicherdateien, Back-up- oder Reparsepunkte, Netzwerkdateien und archivierte Dateien (z. B. .zip werden).
keywords: Erweiterte Scans, Überprüfung, E-Mail, Archiv, ZIP, Rar, Archiv, Erneute Überprüfung
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.date: 05/26/2021
ms.topic: how-to
ms.openlocfilehash: 34f423222068236271afdda13afb95cffa58b709
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683811"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Konfigurieren der Scanoptionen von Microsoft Defender Antivirus

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Verwenden Microsoft Intune zum Konfigurieren von Überprüfungsoptionen

Informationen finden Sie in den folgenden Ressourcen: 

- [Konfigurieren von Geräteeinschränkungseinstellungen in Microsoft Intune](/intune/device-restrictions-configure) 
- [Microsoft Defender Antivirus geräteeinschränkungseinstellungen für Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Verwenden Microsoft Endpoint Manager zum Konfigurieren von Überprüfungsoptionen

Weitere Informationen finden Sie unter Erstellen [und Bereitstellen von Antischalwarerichtlinien: Überprüfen von Einstellungen](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings).

## <a name="use-group-policy-to-configure-scanning-options"></a>Konfigurieren von Überprüfungsoptionen mithilfe von Gruppenrichtlinien

1. Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten aus.**

3. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.

4. Erweitern Sie die **Struktur, Windows Komponenten Microsoft Defender Antivirus**, und wählen Sie dann einen Speicherort aus (siehe Einstellungen  >  und [Speicherorte](#settings-and-locations) in diesem Artikel).

5. Bearbeiten Sie das Richtlinienobjekt. 

6. Klicken **Sie auf OK,** und wiederholen Sie dies für alle anderen Einstellungen.

### <a name="settings-and-locations"></a>Einstellungen und Speicherorte

| Richtlinienelement und -speicherort | Standardeinstellung (wenn nicht konfiguriert) | `Set-MpPreference`PowerShell-Parameter oder WMI-Eigenschaft für `MSFT_MpPreference` Klasse |
|---|---|---|
| E-Mail-Überprüfung <p> **Scannen**  >  **Aktivieren der E-Mail-Überprüfung**<p>Weitere [Informationen finden Sie unter Einschränkungen der E-Mail-Überprüfung](#email-scanning-limitations) (in diesem Artikel) | Deaktiviert | `-DisableEmailScanning` |
|Überprüfen [von Überprüfungspunkten](/windows/win32/fileio/reparse-points) <p> **Scannen**  >  **Aktivieren der Überprüfung von Reparse point** | Deaktiviert | Nicht verfügbar <p>Weitere [Informationen finden Sie unter Reparse points](/windows/win32/fileio/reparse-points)  |
| Überprüfen zugeordneter Netzwerklaufwerke <p> **Scannen**  >  **Ausführen der vollständigen Überprüfung auf zugeordneten Netzwerklaufwerken** | Deaktiviert | `-DisableScanningMappedNetworkDrivesForFullScan`|
| Überprüfen von Archivdateien (z. B. .zip oder .rar Dateien).  <p> **Scannen**  >  **Überprüfen von Archivdateien** | Aktiviert | `-DisableArchiveScanning` <p>Die [Ausschlussliste für Erweiterungen](configure-extension-file-exclusions-microsoft-defender-antivirus.md) hat Vorrang vor dieser Einstellung.|
| Überprüfen von Dateien im Netzwerk <p> **Scannen**  >  **Überprüfen von Netzwerkdateien** | Deaktiviert | `-DisableScanningNetworkFiles` |
| Scannen von verpackten ausführbaren Dateien <p> **Scannen**  >  **Scannen von verpackten ausführbaren Dateien** | Aktiviert | Nicht verfügbar |
| Scannen von Wechseldatenträgern nur bei vollständigen Scans <p> **Scannen**  >  **Scannen von Wechseldatenträgern** | Deaktiviert | `-DisableRemovableDriveScanning` |
| Angeben der Ebene der Unterordner in einem zu überprüfenden Archivordner <p>**Scannen**  >  **Angeben der maximalen Tiefe zum Überprüfen von Archivdateien** | 0 | Nicht verfügbar |
| Geben Sie die maximale CPU-Auslastung (als Prozentsatz) während einer Überprüfung an. <p> **Scannen**  >  **Angeben des maximalen Prozentsatzes der CPU-Auslastung während einer Überprüfung** | 50 |  `-ScanAvgCPULoadFactor` <p>**HINWEIS:** Die maximale CPU-Auslastung ist kein harter Grenzwert, sondern eine Anleitung für das Überprüfungsmodul, die maximale durchschnittliche Auslastung nicht zu überschreiten. Manuelles Ausführen von Scans ignoriert diese Einstellung und wird ohne CPU-Grenzwerte ausgeführt. |
| Geben Sie die maximale Größe (in Kilobyte) von Archivdateien an, die gescannt werden sollen. <p> **Scannen**  >  **Angeben der maximalen Größe der zu scannende Archivdateien** | Keine Begrenzung | Nicht verfügbar <p>Der Standardwert 0 gilt nicht |
| Konfigurieren einer niedrigen CPU-Priorität für geplante Scans <p> **Scannen**  >  **Konfigurieren einer niedrigen CPU-Priorität für geplante Scans** | Deaktiviert | Nicht verfügbar |
 
> [!NOTE]
> Wenn der Echtzeitschutz aktiviert ist, werden Die Dateien überprüft, bevor auf sie zugegriffen und ausgeführt wird. Der Überprüfungsbereich umfasst alle Dateien, einschließlich Dateien auf bereitgestellten Wechselmedien, z. B. USB-Laufwerke. Wenn das Gerät, das die Überprüfung durchführen, über echtzeit- oder Zugriffsschutz verfügt, enthält die Überprüfung auch Netzwerkfreigaben.

## <a name="use-powershell-to-configure-scanning-options"></a>Konfigurieren von Überprüfungsoptionen mithilfe von PowerShell

Informationen finden Sie in den folgenden Ressourcen:

- [Verwalten Microsoft Defender Antivirus mit PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender-Cmdlets](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>Konfigurieren von Überprüfungsoptionen mithilfe von WMI

Weitere [Windows Defender WMIv2-APIs finden Sie](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)unter .

## <a name="email-scanning-limitations"></a>Einschränkungen bei der E-Mail-Überprüfung

Die E-Mail-Überprüfung ermöglicht das Scannen von E-Mail-Dateien, die von Outlook und anderen E-Mail-Clients während bedarfs- und geplanten Scans verwendet werden. Eingebettete Objekte in E-Mails (z. B. Anlagen und archivierte Dateien) werden ebenfalls überprüft. Die folgenden Dateiformattypen können gescannt und behoben werden:

- DBX
- MBX
- MIME

PST-Dateien, die von Outlook 2003 oder älter verwendet werden (wobei der Archivtyp auf Nicht-Unicode festgelegt ist), werden ebenfalls überprüft, aber Microsoft Defender Antivirus kann bedrohungen, die in PST-Dateien erkannt werden, nicht be behebung.

Wenn Microsoft Defender Antivirus eine Bedrohung in einer E-Mail-Nachricht erkennt, werden die folgenden Informationen angezeigt, die Ihnen bei der Identifizierung der gefährdeten E-Mail helfen, sodass Sie die Bedrohung manuell 2013 2012 2013 2013 2014 2014 2014 2013 2014 2014 löschen können:

- E-Mail-Betreff
- Anlagenname

## <a name="see-also"></a>Weitere Artikel

- [Anpassen, Initiieren und Überprüfen der Ergebnisse Microsoft Defender Antivirus Überprüfungen und Korrekturen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Konfigurieren und Ausführen von bedarfsgesteuerten Scans durch Microsoft Defender Antivirus](run-scan-microsoft-defender-antivirus.md)
- [Konfigurieren geplanter Microsoft Defender Antivirus Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
