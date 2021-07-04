---
title: Verwenden der Befehlszeile zum Verwalten von Microsoft Defender Antivirus
description: Führen Sie Microsoft Defender Antivirus Scans aus, und konfigurieren Sie den Schutz der nächsten Generation mit einem dedizierten Befehlszeilenprogramm.
keywords: Ausführen des Windows Defender-Scans, Ausführen eines Antivirusscans über die Befehlszeile, Ausführen des Windows Defender-Scans über die Befehlszeile, mpcmdrun, Defender
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
ms.date: 05/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: efeb49b2741bdc45f7924032c2deb8a27458ca29
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289415"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Konfigurieren und Verwalten von Microsoft Defender Antivirus mit dem Befehlszeilentool mpcmdrun.exe

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können verschiedene Funktionen in Microsoft Defender Antivirus mithilfe des dedizierten Befehlszeilentools **mpcmdrun.exe** ausführen. Dieses Hilfsprogramm ist nützlich, wenn Sie Microsoft Defender Antivirus Aufgaben automatisieren möchten. Sie finden das Hilfsprogramm unter `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Führen Sie ihn über eine Eingabeaufforderung aus.

> [!TIP]
> Möglicherweise müssen Sie eine Version der Eingabeaufforderung auf Administratorebene öffnen. Wenn Sie im Startmenü nach **eingabeaufforderung** suchen, wählen Sie **als Administrator ausführen** aus. Wenn Sie eine aktualisierte Version von Microsoft Defender Platform ausführen, führen Sie `MpCmdRun` den folgenden Speicherort aus: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` . Weitere Informationen zur Antischadsoftwareplattform finden Sie unter [Microsoft Defender Antivirus Updates und Baselines.](manage-updates-baselines-microsoft-defender-antivirus.md)

Das Hilfsprogramm MpCmdRun verwendet die folgende Syntax:

```console
MpCmdRun.exe [command] [-options]
```

Hier ist ein Beispiel:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

In unserem Beispiel startet das Hilfsprogramm MpCmdRun eine vollständige Antivirenprüfung auf dem Gerät.

## <a name="commands"></a>Befehle

| Befehl  | Beschreibung   |
|:----|:----|
| `-?`**oder**`-h`   | Zeigt alle verfügbaren Optionen für das MpCmdRun-Tool an. |
| `-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Sucht nach Schadsoftware. Die Werte für **ScanType** sind:<p>**0** Standard, gemäß Ihrer Konfiguration<p>**1** Schnellscan<p>**2** Vollständige Überprüfung<p>**3** Benutzerdefinierte Datei- und Verzeichnisüberprüfung.<p>CpuThrottling wird gemäß Richtlinienkonfigurationen ausgeführt |
| `-Trace [-Grouping #] [-Level #]` | Startet die Diagnoseablaufverfolgung |
| `-GetFiles [-SupportLogLocation <path>]` | Sammelt Supportinformationen. Siehe["Sammeln von Diagnosedaten"](collect-diagnostic-data.md)  |
| `-GetFilesDiagTrack`  | Identisch mit `-GetFiles` , gibt aber in temporären DiagTrack-Ordner aus |
| `-RemoveDefinitions [-All]` | Stellt die installierte Security Intelligence mit einer vorherigen Sicherungskopie oder dem ursprünglichen Standardsatz wieder her. |
| `-RemoveDefinitions [-DynamicSignatures]` | Entfernt nur die dynamisch heruntergeladene Sicherheitsintelligenz |
| `-RemoveDefinitions [-Engine]` | Stellt das zuvor installierte Modul wieder her |
| `-SignatureUpdate [-UNC \| -MMPC]` | Sucht nach neuen Security Intelligence-Updates |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | Wiederherstellen oder Auflisten von isolierten Elementen |
| `-AddDynamicSignature [-Path]` | Lädt dynamische Sicherheitsintelligenz |
| `-ListAllDynamicSignatures` | Listet die geladene dynamische Sicherheitsintelligenz auf. |
| `-RemoveDynamicSignature [-SignatureSetID]` | Entfernt dynamische Sicherheitsintelligenz |
| `-CheckExclusion -path <path>` | Überprüft, ob ein Pfad ausgeschlossen ist |
| `-ValidateMapsConnection` | Überprüft, ob Ihr Netzwerk mit dem Microsoft Defender Antivirus Clouddienst kommunizieren kann. Dieser Befehl funktioniert nur für Windows 10, Version 1703 oder höher.|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>Häufige Fehler beim Ausführen von Befehlen über mpcmdrun.exe 

In der folgenden Tabelle sind häufige Fehler aufgeführt, die bei Verwendung des MpCmdRun-Tools auftreten können.

|Fehlermeldung | Mögliche Ursache |
|:----|:----|
| **ValidateMapsConnection-Fehler (800106BA)** oder **0x800106BA** | Der Microsoft Defender Antivirus Dienst ist deaktiviert. Aktivieren Sie den Dienst, und versuchen Sie es erneut. Wenn Sie Hilfe beim erneuten Aktivieren von Microsoft Defender Antivirus benötigen, lesen Sie ["Neu installieren/aktivieren" Microsoft Defender Antivirus auf Ihren Endpunkten.](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)<p> **TIPP:** In Windows 10 1909 oder älter und Windows Server 2019 oder älter wurde der Dienst früher *Windows Defender Antivirus* aufgerufen. |
| **0x80070667** | Sie führen den `-ValidateMapsConnection` Befehl auf einem Computer aus, der Windows 10 Version 1607 oder älter oder Windows Server 2016 oder älter ist. Führen Sie den Befehl von einem Computer aus, der Windows 10 Version 1703 oder höher oder Windows Server 2019 oder höher ist.|
| **MpCmdRun wird nicht als interner oder externer Befehl, funktionsfähiges Programm oder Batchdatei erkannt.** | Das Tool muss entweder `%ProgramFiles%\Windows Defender` oder `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (wo sich `2012.4-0` Plattformupdates mit Ausnahme von März monatlich unterscheiden können) ausgeführt werden.|
| **ValidateMapsConnection konnte keine Verbindung mit MAPS herstellen (hr=80070005 httpcode=450)** | Der Befehl wurde versucht, unzureichende Berechtigungen zu verwenden. Verwenden Sie die Eingabeaufforderung (cmd.exe) als Administrator.|
| **ValidateMapsConnection konnte keine Verbindung mit MAPS herstellen (hr=80070006 httpcode=451)** | Die Firewall blockiert die Verbindung oder führt eine SSL-Überprüfung durch. |
| **ValidateMapsConnection konnte keine Verbindung mit MAPS herstellen (hr=80004005 httpcode=450)** | Mögliche netzwerkbezogene Probleme, z. B. Probleme bei der Namensauflösung|
| **ValidateMapsConnection konnte keine Verbindung mit MAPS herstellen (hr=0x80508015** | Die Firewall blockiert die Verbindung oder führt eine SSL-Überprüfung durch. |
| **ValidateMapsConnection konnte keine Verbindung mit MAPS herstellen (hr=800722F0D** | Die Firewall blockiert die Verbindung oder führt eine SSL-Überprüfung durch. |
| **ValidateMapsConnection konnte keine Verbindung mit MAPS herstellen (hr=80072EE7 httpcode=451)** | Die Firewall blockiert die Verbindung oder führt eine SSL-Überprüfung durch. |

## <a name="see-also"></a>Weitere Informationen:

- [Konfigurieren von Microsoft Defender Antivirus-Features](configure-microsoft-defender-antivirus-features.md)
- [Konfigurieren und Überprüfen von Microsoft Defender Antivirus-Netzwerkverbindungen](configure-network-connections-microsoft-defender-antivirus.md)
- [Referenzthemen für Verwaltungs- und Konfigurationstools](configuration-management-reference-microsoft-defender-antivirus.md)
