---
title: Konfigurieren von Überprüfungsoptionen für Microsoft Defender Antivirus
description: Sie können Microsoft Defender AV so konfigurieren, dass E-Mail-Speicherdateien, Sicherungs- oder Analysepunkte, Netzwerkdateien und archivierte Dateien (z. B. .zip Dateien) gescannt werden.
keywords: Erweiterte Scans, Scannen, E-Mail, Archiv, ZIP, Rar, Archiv, Analysescans
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
ms.openlocfilehash: 96e4dab96f8ceb149916c908991079bb2dfa866f
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964897"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Konfigurieren der Scanoptionen von Microsoft Defender Antivirus

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Verwenden von Microsoft Intune zum Konfigurieren von Überprüfungsoptionen

Weitere Informationen finden Sie unter [Konfigurieren von Geräteeinschränkungseinstellungen in Microsoft Intune](/intune/device-restrictions-configure) und Microsoft Defender Antivirus [Geräteeinschränkungseinstellungen für Windows 10 in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Verwenden von Microsoft Endpoint Manager zum Konfigurieren von Überprüfungsoptionen

Ausführliche Informationen zum Konfigurieren von Microsoft Endpoint Manager (current branch) finden Sie unter [Erstellen und Bereitstellen von Antischadsoftwarerichtlinien: Scaneinstellungen.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)

## <a name="use-group-policy-to-configure-scanning-options"></a>Verwenden von Gruppenrichtlinien zum Konfigurieren von Überprüfungsoptionen

1. Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.

3. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und klicken Sie auf **"Administrative Vorlagen".**

4. Erweitern Sie die Struktur bis **Windows Komponenten**  >  **Microsoft Defender Antivirus,** und wählen Sie dann einen Speicherort aus (siehe [Einstellungen und Speicherorte](#settings-and-locations) in diesem Artikel).


5. Bearbeiten Sie das Richtlinienobjekt. 

6. Klicken Sie auf **"OK",** und wiederholen Sie dies für alle anderen Einstellungen.

### <a name="settings-and-locations"></a>Einstellungen und Standorte

| Richtlinienelement und -speicherort | Standardeinstellung (falls nicht konfiguriert) | PowerShell-Parameter `Set-MpPreference` oder WMI-Eigenschaft für `MSFT_MpPreference` Klasse |
|---|---|---|
| E-Mail-Überprüfung <p> **Scannen**  >  **Aktivieren der E-Mail-Überprüfung**<p>Siehe [Einschränkungen bei der E-Mail-Überprüfung](#email-scanning-limitations) (in diesem Artikel) | Deaktiviert | `-DisableEmailScanning` |
|Überprüfen [von Analysepunkten](/windows/win32/fileio/reparse-points) <p> **Scannen**  >  **Aktivieren der Analysepunktüberprüfung** | Deaktiviert | Nicht verfügbar <p>Siehe ["Analysepunkte"](/windows/win32/fileio/reparse-points)  |
| Scannen zugeordneter Netzwerklaufwerke <p> **Scannen**  >  **Vollständige Überprüfung auf zugeordneten Netzlaufwerken ausführen** | Deaktiviert | `-DisableScanningMappedNetworkDrivesForFullScan`|
| Archivdateien scannen (z. B. .zip oder .rar).  <p> **Scannen**  >  **Archivdateien überprüfen** | Enabled | `-DisableArchiveScanning` <p>Die [Erweiterungsausschlussliste](configure-extension-file-exclusions-microsoft-defender-antivirus.md) hat Vorrang vor dieser Einstellung.|
| Scannen von Dateien im Netzwerk <p> **Scannen**  >  **Scannen von Netzwerkdateien** | Deaktiviert | `-DisableScanningNetworkFiles` |
| Scannen von gepackten ausführbaren Dateien <p> **Scannen**  >  **Scannen von gepackten ausführbaren Dateien** | Enabled | Nicht verfügbar |
| Scannen von Wechseldatenträgern nur bei vollständigen Scans <p> **Scannen**  >  **Scannen von Wechseldatenträgern** | Deaktiviert | `-DisableRemovableDriveScanning` |
| Angeben der Ebene von Unterordnern innerhalb eines zu scannenden Archivordners <p>**Scannen**  >  **Angeben der maximalen Tiefe zum Scannen von Archivdateien** | 0 | Nicht verfügbar |
| Geben Sie die maximale CPU-Auslastung (als Prozentsatz) während einer Überprüfung an. <p> **Scannen**  >  **Angeben des maximalen Prozentsatzes der CPU-Auslastung während einer Überprüfung** | 50 |  `-ScanAvgCPULoadFactor` <p>**HINWEIS:** Die maximale CPU-Auslastung ist kein hartes Limit, aber es wird empfohlen, dass das Scanmodul das Maximum im Durchschnitt nicht überschreitet. Manuelle Scans ignorieren diese Einstellung und werden ohne CPU-Beschränkungen ausgeführt. |
| Geben Sie die maximale Größe (in KB) von Archivdateien an, die gescannt werden sollen. <p> **Scannen**  >  **Angeben der maximalen Größe der zu scannenden Archivdateien** | Keine Begrenzung | Nicht verfügbar <p>Der Standardwert 0 gilt ohne Grenzwert. |
| Konfigurieren einer niedrigen CPU-Priorität für geplante Scans <p> **Scannen**  >  **Konfigurieren einer niedrigen CPU-Priorität für geplante Scans** | Deaktiviert | Nicht verfügbar |

 
> [!NOTE]
> Wenn der Echtzeitschutz aktiviert ist, werden Dateien vor dem Zugriff auf und der Ausführung gescannt. Der Überprüfungsbereich umfasst alle Dateien, einschließlich Dateien auf bereitgestellten Wechselmedien, z. B. USB-Laufwerke. Wenn auf dem Gerät, auf dem die Überprüfung ausgeführt wird, der Echtzeitschutz oder der On-Access-Schutz aktiviert ist, enthält die Überprüfung auch Netzwerkfreigaben.

## <a name="use-powershell-to-configure-scanning-options"></a>Verwenden von PowerShell zum Konfigurieren von Scanoptionen


Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter

- [Verwalten von Microsoft Defender Antivirus mit PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender-Cmdlets](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>Verwenden von WMI zum Konfigurieren von Überprüfungsoptionen

Siehe [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="email-scanning-limitations"></a>Einschränkungen bei der E-Mail-Überprüfung

Die E-Mail-Überprüfung ermöglicht das Scannen von E-Mail-Dateien, die von Outlook und anderen E-Mail-Clients während bedarfsgesteuerter und geplanter Überprüfungen verwendet werden. Eingebettete Objekte in E-Mails (z. B. Anlagen und archivierte Dateien) werden ebenfalls gescannt. Die folgenden Dateiformattypen können gescannt und korrigiert werden:

- Dbx
- Mbx
- MIME

PST-Dateien, die von Outlook 2003 oder älter verwendet werden (wobei der Archivtyp auf Nicht-Unicode festgelegt ist), werden ebenfalls gescannt, Microsoft Defender Antivirus können jedoch keine Bedrohungen beheben, die in PST-Dateien erkannt werden.

Wenn Microsoft Defender Antivirus eine Bedrohung innerhalb einer E-Mail erkennt, werden ihnen die folgenden Informationen angezeigt, die Sie bei der Identifizierung der gefährdeten E-Mail unterstützen, damit Sie die Bedrohung manuell beheben können:

- E-Mail-Betreff
- Anlagenname


## <a name="scanning-mapped-network-drives"></a>Scannen zugeordneter Netzwerklaufwerke

Auf jedem Betriebssystem werden nur die Netzwerklaufwerke gescannt, die auf Systemebene zugeordnet sind. Zugeordnete Netzlaufwerke auf Benutzerebene werden nicht gescannt. Zugeordnete Netzlaufwerke auf Benutzerebene sind die Laufwerke, die ein Benutzer in seiner Sitzung manuell und mithilfe seiner eigenen Anmeldeinformationen zuordbare.

## <a name="see-also"></a>Siehe auch


- [Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus Überprüfungen und Korrekturen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Konfigurieren und Ausführen von bedarfsgesteuerten Scans durch Microsoft Defender Antivirus](run-scan-microsoft-defender-antivirus.md)
- [Konfigurieren von geplanten Microsoft Defender Antivirus Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
