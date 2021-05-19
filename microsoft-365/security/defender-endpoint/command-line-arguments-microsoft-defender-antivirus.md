---
title: Verwenden der Befehlszeile zum Verwalten Microsoft Defender Antivirus
description: Führen Microsoft Defender Antivirus und konfigurieren Sie den Schutz der nächsten Generation mit einem dedizierten Befehlszeilenprogramm.
keywords: Ausführen der Windows Defender-Überprüfung, Ausführen der Antivirenscan über die Befehlszeile, Ausführen der Windows Defender-Überprüfung über die Befehlszeile, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/17/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: eb7fa7fdf5b88bd9361176003817116bcbb1a087
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538903"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Konfigurieren und Verwalten von Microsoft Defender Antivirus mit mpcmdrun.exe Befehlszeilentool

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können verschiedene Microsoft Defender Antivirus mit dem dedizierten **Befehlszeilentool** mpcmdrun.exe. Dieses Hilfsprogramm ist nützlich, wenn Sie die Verwendung Microsoft Defender Antivirus möchten. Das Hilfsprogramm finden Sie unter `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Sie müssen ihn über eine Eingabeaufforderung ausführen.

> [!NOTE]
> Möglicherweise müssen Sie eine Administratorversion der Eingabeaufforderung öffnen. Wenn Sie im Menü **Start** nach Eingabeaufforderung suchen, wählen Sie **Als Administrator ausführen aus.**
> Wenn Sie eine aktualisierte Microsoft Defender Platform-Version ausführen, führen Sie sie `**MpCmdRun**` an folgendem Speicherort aus: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` .
> Weitere Informationen zur Antischalwareplattform finden Sie [unter Microsoft Defender Antivirus updates and baselines](manage-updates-baselines-microsoft-defender-antivirus.md).

Das Hilfsprogramm MpCmdRun verwendet die folgende Syntax:

```console
MpCmdRun.exe [command] [-options]
```

Hier ist ein Beispiel:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| Befehl  | Beschreibung   |
|:----|:----|
| `-?` **oder** `-h`   | Zeigt alle verfügbaren Optionen für dieses Tool an. |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Sucht nach schadhafter Software. Die Werte **für ScanType** sind:<p>**0** Standard gemäß Ihrer Konfiguration<p>**-1** Schnellscan<p>**-2** Vollständiger Scan<p>**-3** Benutzerdefinierte Datei- und Verzeichnisscan.<p>CpuThrottling berücksichtigt die konfigurierte CPU-Einschränkung aus der Richtlinie |
| `-Trace [-Grouping #] [-Level #]` | Startet die Diagnoseablaufverfolgung |
| `-GetFiles [-SupportLogLocation <path>]` | Sammelt Supportinformationen. Siehe '[Sammeln von Diagnosedaten](collect-diagnostic-data.md)'  |
| `-GetFilesDiagTrack`  | Identisch mit `-GetFiles` , aber Ausgaben in temporären DiagTrack-Ordner |
| `-RemoveDefinitions [-All]` | Stellt die installierte Sicherheitsintelligenz in einer früheren Sicherungskopie oder im ursprünglichen Standardsatz wieder her. |
| `-RemoveDefinitions [-DynamicSignatures]` | Entfernt nur die dynamisch heruntergeladene Sicherheitsintelligenz |
| `-RemoveDefinitions [-Engine]` | Wiederherstellung des vorherigen installierten Moduls |
| `-SignatureUpdate [-UNC \| -MMPC]` | Sucht nach neuen Security Intelligence-Updates |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | Wiederherstellen oder Auflisten isolierter Elemente |
| `-AddDynamicSignature [-Path]` | Lädt dynamische Sicherheitsintelligenz |
| `-ListAllDynamicSignatures` | Listet die geladene dynamische Sicherheitsintelligenz auf. |
| `-RemoveDynamicSignature [-SignatureSetID]` | Entfernt dynamische Sicherheitsintelligenz |
| `-CheckExclusion -path <path>` | Überprüft, ob ein Pfad ausgeschlossen ist |
| `-ValidateMapsConnection` | Überprüft, ob Ihr Netzwerk mit dem Microsoft Defender Antivirus kommunizieren kann. Dieser Befehl funktioniert nur für Windows 10 Version 1703 oder höher.|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>Häufige Fehler beim Ausführen von Befehlen mpcmdrun.exe 

|Fehlermeldung | Möglicher Grund
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | Der Microsoft Defender Antivirus ist deaktiviert. Aktivieren Sie den Dienst, und versuchen Sie es erneut. <br>   **Hinweis:**  In Windows 10 1909 oder älter und Windows Server 2019 oder älter wurde der Dienst früher als Windows Defender Antivirus *bezeichnet.*|
| `0x80070667` | Sie ausführen den Befehl von einem Computer, der Windows 10 Version 1607 oder älter oder älter `-ValidateMapsConnection` Windows Server 2016 ist. Führen Sie den Befehl auf einem Computer aus, Windows 10 Version 1703 oder neuer ist, oder Windows Server 2019 oder neuer.|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | Das Tool muss entweder ausgeführt werden: oder (wobei sich möglicherweise unterscheiden, da Plattformupdates monatlich `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` sind, außer im März)|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | Zu wenig Rechte. Verwenden Sie die Eingabeaufforderung (cmd.exe) als Administrator.|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | Die Firewall blockiert die Verbindung oder führt eine SSL-Überprüfung durch. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | Mögliche netzwerkbezogene Probleme, wie Probleme bei der Namensauflösung|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | Die Firewall blockiert die Verbindung oder führt eine SSL-Überprüfung durch. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | Die Firewall blockiert die Verbindung oder führt eine SSL-Überprüfung durch. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | Die Firewall blockiert die Verbindung oder führt eine SSL-Überprüfung durch. |

## <a name="see-also"></a>Siehe auch

- [Konfigurieren von Microsoft Defender Antivirus-Features](configure-microsoft-defender-antivirus-features.md)
- [Verwalten Microsoft Defender Antivirus in Ihrem Unternehmen](configuration-management-reference-microsoft-defender-antivirus.md)
- [Referenzthemen für Verwaltungs- und Konfigurationstools](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)