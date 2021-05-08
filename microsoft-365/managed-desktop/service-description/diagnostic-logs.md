---
title: Diagnoseprotokolle
description: Protokolle, die während der Problembehandlung von Geräten gesammelt werden und wie sie gespeichert werden
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272891"
---
# <a name="diagnostic-logs"></a>Diagnoseprotokolle

Wenn wir ein Problem auf einem von Microsoft Managed Desktop verwalteten Gerät behandeln, unabhängig davon, ob sie gemeldet oder von unserem Dienst identifiziert wurden, müssen wir möglicherweise bestimmte Diagnoseprotokolle vom Gerät ohne Eingreifen des Benutzers erfassen. Wir sammeln keine vom Benutzer generierten Inhalte oder Informationen aus Benutzerverzeichnissen. Wir erfassen nur Diagnose- und Protokolldaten, die den Gerätestatus und -status betrifft.

Wir speichern alle gesammelten Protokolle für 28 Tage und löschen sie dann. Wir verarbeiten alle Protokolle, die von einem Gerät gesammelt werden, nach unseren [Datenverarbeitungsstandards](privacy-personal-data.md).

## <a name="data-collected"></a>Gesammelte Daten

Diese Liste enthält alle Ordner, Ereignisprotokolle, ausführbaren Dateien oder Registrierungsstandorte, von der Microsoft Managed Desktop Diagnoseprotokolle erfassen kann. Die tatsächlich gesammelten Daten sind eine Teilmenge dieser Liste und hängen vom identifizierten Problem ab.

### <a name="registry-keys"></a>Registrierungsschlüssel

- HKLM \\ SYSTEM \\ CurrentControlSet \\ Services
- HKLM \\ SOFTWARE \\ Microsoft \\ Surface
- HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Windows \\ WindowsUpdate
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ MUI \\ UILanguages
- \\HKLM-Softwarerichtlinien \\ \\ Microsoft \\ WindowsStore
- HKLM \\ Software \\ Microsoft \\ Windows \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ AppModel
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ FirmwareResources
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ Appx
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion \\ Superfetch
- HKLM \\ SYSTEM \\ Setup
- HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension
- HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows Advanced Threat Protection
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ Authentication \\ LogonUI
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ -Interneteinstellungen
- HKLM \\ Software \\ Microsoft \\ Windows \\ CurrentVersion \\ Uninstall
- \\HKLM-Softwarerichtlinien \\
- HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Cryptography \\ Configuration \\ SSL
- HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Windows Advanced Threat Protection
- HKLM \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ Deinstallieren
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL

### <a name="commands"></a>Befehle

- %programfiles% \\ windows defendermpcmdrun.exe \\ -GetFiles
- %windir% \\ system32 \\certutil.exe -store
- %windir% \\ system32 \\certutil.exe -store -user my
- %windir% \\ system32 \\Dsregcmd.exe /status
- %windir% \\ system32 \\ipconfig.exe /all
- %windir% \\ system32 \\ipconfig.exe /displaydns
- %windir% \\ system32 \\mdmdiagnosticstool.exe
- %windir% \\ system32 \\msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log
- %windir% \\ system32 \\netsh.exe advfirewall alleProfile anzeigen
- %windir% \\ system32 \\netsh.exe advfirewall global anzeigen
- %windir% \\ system32 \\netsh.exe lan show profiles
- %windir% \\ system32 \\netsh.exe winhttp show proxy
- %windir% \\ system32 \\netsh.exe wlan show profiles
- %windir% \\ system32 \\netsh.exe wlan show wlanreport
- %windir% \\ system32 \\ping.exe -n 50 localhost
- %windir% \\ system32 \\powercfg.exe /batteryreport /output %temp% \\ MDMDiagnostics \\battery-report.html
- %windir% \\ system32 \\powercfg.exe /energy /output %temp% \\ MDMDiagnostics \\energy-report.html
- bitsadmin /list /allusers /verbose
- fltMC.exe
- bcdedit /enum all /v
- manage-bde -protectors -get
- Windows PowerShell Befehle:
    - Get-appxpackage -allusers
    - Get-appxpackage -packagetype bundle
    - Get-Service wuauserv
    - Get-NetFirewallRule
    - Get-WmiObject -Class win32 \_ product
    - Get-ComputerInfo
    - Get-Service
    - Get-Process
    - Get-WmiObject Win32 \_ PnPSignedDriver

### <a name="event-logs"></a>Ereignisprotokolle

- Anwendung
- Microsoft-Windows-AppLocker/EXE und DLL
- Microsoft-Windows-AppLocker/MSI und Script
- Microsoft-Windows-AppLocker/Packaged app-Deployment
- Microsoft-Windows-AppLocker/Packaged app-Execution
- Microsoft-Windows-Bitlocker/Bitlocker-Verwaltung
- Microsoft-Windows-SENSE/Operational
- Microsoft-Windows-SenseIR/Operational
- Setup
- System

### <a name="files"></a>Dateien

- %ProgramData% \\ Microsoft \\ DiagnosticLogCSP \\ Collectors \\ \* .etl
- %ProgramData% \\ Microsoft \\ IntuneManagementExtension \\ Logs \\ \* .\*
- %ProgramData% \\ Microsoft Windows Defender Support \\ \\ \\MpSupportFiles.cab
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReportwlan-report-latest.htm\\ l
- %ProgramData% \\ Microsoft \\ Windows \\ WLANReport -SourceFileName wlan-report-latest.html
- %windir% \\ ccm \\ logs \* .log
- %windir% \\ ccmsetup \\ logs \* .log
- %windir% \\ logs \\ CBS \\ cbs.log
- %windir% \\ logs \\ measuredboot \* .\*
- %windir% \\ Logs \\ WindowsUpdate \* .etl
- %windir% \\ inf \\ \* .log
- \\%windir%-Wartungssitzungen \\ \\ActionList.xml
- \\%windir%-Wartungssitzungen \\ \\Sessions.xml
- %windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log
- %windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb
- %windir% \\ logs \\ dism \\ dism.log
- %SystemRoot% \\ System32 \\ Winevt \\ Logs\\
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .etl
- %appdata% \\ Microsoft \\ Teams \\logs.txt
- %windir% \\ Windows \\ System32 \\ winevt \\ \* .\*