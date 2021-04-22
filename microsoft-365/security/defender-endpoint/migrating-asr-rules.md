---
title: Migrieren von einem Drittanbieter-HIPS zu ASR-Regeln
description: Beschreibt, wie Sie eine Migration von einer Host Intrusion Prevention System (HIPS)-Lösung eines Drittanbieters in ASR-Regeln nähern.
keywords: Attack surface reduction rules, asr, asr rules, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, infection prevention, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.topic: article
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: de65c134560ecca219de9174ff222d31dd578d31
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933781"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>Migrieren von einem Drittanbieter-HIPS zu ASR-Regeln

Dieser Artikel hilft Ihnen bei der Zuordnung gängiger Regeln zu Microsoft Defender for Endpoint.

## <a name="scenarios-when-migrating-from-a-third-party-hips-product-to-asr-rules"></a>Szenarien bei der Migration von einem Drittanbieter-HIPS-Produkt zu ASR-Regeln

### <a name="block-creation-of-specific-files-and-registry-keys"></a>Blockieren der Erstellung bestimmter Dateien und Registrierungsschlüssel

- **Gilt für**– Alle Prozesse
- **Vorgang**– Dateierstellung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**- *.zepto, *.odin, *.locky, *.jaff, *.lukitus, *.wnry, *.krab
- **Attack Surface Reduction-Regeln**– ASR-Regeln blockieren die Angriffstechniken und nicht die Indikatoren für Kompromisse (IOC). Das Blockieren einer bestimmten Dateierweiterung ist nicht immer hilfreich, da es nicht verhindert, dass ein Gerät gefährdet wird. Es vereitelt einen Angriff nur teilweise, bis Angreifer einen neuen Erweiterungstyp für die Nutzlast erstellen.
- **Weitere empfohlene Features**– Microsoft Defender AV aktiviert zu haben, sowie Cloud Protection und Verhaltensanalyse wird dringend empfohlen. Es wird empfohlen, andere Präventionsmaßnahmen zu verwenden, z. B. die ASR-Regel "Erweiterten Schutz vor Ransomware verwenden". Dies bietet ein höheres Maß an Schutz vor Ransomware-Angriffen. Darüber hinaus werden viele dieser Registrierungsschlüssel von Microsoft Defender for Endpoint überwacht, z. B. ASEP-Techniken, die bestimmte Warnungen auslösen. Die verwendeten Registrierungsschlüssel erfordern mindestens lokale Administrator- oder Vertrauenswürdige Installer-Berechtigungen, die geändert werden können. Es wird empfohlen, eine gesperrte Umgebung mit minimalen Administratorkonten oder -rechten zu verwenden. Andere Systemkonfigurationen können aktiviert werden, einschließlich "Deaktivieren von SeDebug für nicht erforderliche Rollen", die Teil unserer umfassenderen Sicherheitsempfehlungen sind.

### <a name="block-creation-of-specific-files-and-registry-keys"></a>Blockieren der Erstellung bestimmter Dateien und Registrierungsschlüssel

- **Gilt für**– Alle Prozesse
- **Prozesse**– N/A
- **Vorgang**– Registrierungsänderungen
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste** -  *\Software*,HKCU\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs *\StartExe, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options*\Debugger, HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit*\MonitorProcess
- **Attack Surface Reduction-Regeln**– ASR-Regeln blockieren die Angriffstechniken und nicht die Indikatoren für Kompromisse (IOC). Das Blockieren einer bestimmten Dateierweiterung ist nicht immer hilfreich, da es nicht verhindert, dass ein Gerät gefährdet wird. Es vereitelt einen Angriff nur teilweise, bis Angreifer einen neuen Erweiterungstyp für die Nutzlast erstellen.
- **Weitere empfohlene Features**– Microsoft Defender AV aktiviert zu haben, sowie Cloud Protection und Verhaltensanalyse wird dringend empfohlen. Es wird empfohlen, zusätzliche Prävention zu verwenden, z. B. die ASR-Regel "Erweiterten Schutz vor Ransomware verwenden". Dies bietet ein höheres Maß an Schutz vor Ransomware-Angriffen. Darüber hinaus werden mehrere dieser Registrierungsschlüssel von Microsoft Defender for Endpoint überwacht, z. B. ASEP-Techniken, die bestimmte Warnungen auslösen. Darüber hinaus erfordern die verwendeten Registrierungsschlüssel, dass mindestens lokale Administrator- oder Vertrauenswürdige Installer-Berechtigungen geändert werden können. Es wird empfohlen, eine gesperrte Umgebung mit minimalen Administratorkonten oder -rechten zu verwenden. Andere Systemkonfigurationen können aktiviert werden, einschließlich "Deaktivieren von SeDebug für nicht erforderliche Rollen", die Teil unserer umfassenderen Sicherheitsempfehlungen sind.

### <a name="block-untrusted-programs-from-running-from-removable-drives"></a>Blockieren der Ausführung nicht vertrauenswürdiger Programme von Wechseldatenträgern

- **Gilt für**: Nicht vertrauenswürdige Programme von USB
- **Prozesse**– *
- **Vorgang**– Prozessausführung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste:-*
- **Attack Surface Reduction-Regeln**– ASR-Regeln verfügen über eine integrierte Regel, um das Starten nicht vertrauenswürdiger und nicht signierter Programme an Wechseldatenträgern zu verhindern: "Nicht vertrauenswürdige und nicht signierte Prozesse blockieren, die über USB ausgeführt werden", GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4".
- **Weitere empfohlene Features**: Weitere Steuerelemente für USB-Geräte und andere Wechselmedien mithilfe von Microsoft Defender for Endpoint: Steuern von USB-Geräten und anderen Wechselmedien mithilfe von [Microsoft Defender for Endpoint](/windows/security/threat-protection/device-control/control-usb-devices-using-intune).

### <a name="block-mshta-from-launching-certain-child-processes"></a>Blockieren des Startens bestimmter untergeordneter Prozesse durch Mshta

- **Gilt für**- Mshta
- **Prozesse**– mshta.exe
- **Vorgang**– Prozessausführung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse,** Dienste – powershell.exe, cmd.exe, regsvr32.exe
- **Attack Surface Reduction rules**– ASR rules don't contain any specific rule to prevent child processes from "mshta.exe". Dieses Steuerelement befindet sich im Aufgabenbereich von Exploit Protection oder Windows Defender Application Control.
- **Weitere empfohlene Features**: Aktivieren Windows Defender Anwendungssteuerung, um zu verhindern, mshta.exe vollständig ausgeführt werden. Wenn Ihre Organisation "mshta.exe" für Business-Apps erfordert, konfigurieren Sie eine bestimmte Windows Defender Exploit Protection-Regel, um zu verhindern, dass mshta.exe untergeordnete Prozesse starten.

### <a name="block-outlook-from-launching-child-processes"></a>Blockieren des Startens von untergeordneten Prozessen durch Outlook

- **Gilt für**– Outlook
- **Prozesse**– outlook.exe
- **Vorgang**– Prozessausführung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**– powershell.exe
- **Attack Surface Reduction rules**– ASR rules have a built-in rule to prevent Office communication apps (Outlook, Skype, and Teams) from launching child processes: "Block Office communication application from creating child processes", GUID "26190899-1602-49e8-8b27-eb1d0a1ce869".
- **Weitere empfohlene Features:** Es wird empfohlen, den eingeschränkten Sprachmodus von PowerShell zu aktivieren, um die Angriffsfläche von PowerShell zu minimieren.


### <a name="block-office-apps-from-launching-child-processes-and-from-creating-executable-content"></a>Blockieren von Office Apps am Starten untergeordneter Prozesse und am Erstellen ausführbarer Inhalte

- **Gilt für**- Office  
- **Prozesse**– winword.exe, powerpnt.exe, excel.exe
- **Vorgang**– Prozessausführung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse,** Dienste – powershell.exe, cmd.exe, wscript.exe, mshta.exe, EQNEDT32.EXE, regsrv32.exe
- **Attack Surface Reduction rules**– ASR rules have a built-in rule to prevent Office apps from launching child processes: "Block all Office applications from creating child processes", GUID "D4F940AB-401B-4EFC-AADC-AD5F3C50688A".
- **Weitere empfohlene Features**– N/A
    
### <a name="block-office-apps-from-launching-child-processes-and-from-creating-executable-content"></a>Blockieren von Office Apps am Starten untergeordneter Prozesse und am Erstellen ausführbarer Inhalte

- **Gilt für**- Office
- **Prozesse**– winword.exe, powerpnt.exe, excel.exe
- **Vorgang**– Dateierstellung
- Beispiele für **Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse,** Dienste - C:\Users *\AppData **.exe, C:\ProgramData**.exe, C:\ProgramData**.com, C:\Users* AppData\Local\Temp **.com, C:\Users*\Downloads**.exe, C:\Users *\AppData **.scf, C:\ProgramData**.scf, C:\Users\Public*.exe, C:\Users*\Desktop***.exe
- **Attack Surface Reduction Rules**– N/A.

### <a name="block-wscript-from-reading-certain-types-of-files"></a>Blockieren des Lesens bestimmter Dateitypen durch Wscript

- **Gilt für**- Wscript
- **Prozesse**– wscript.exe
- **Vorgang**– Datei lesen
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**- C:\Users *\AppData**.js, C:\Users*\Downloads**.js
- **Attack Surface Reduction-Regeln**– Aufgrund von Zuverlässigkeits- und Leistungsproblemen können ASR-Regeln nicht verhindern, dass ein bestimmter Prozess einen bestimmten Skriptdateityp liest. Wir verfügen über eine Regel, um Angriffsvektoren zu verhindern, die aus diesen Szenarien stammen können. Der Regelname ist "JavaScript oder VBScript vom Starten heruntergeladener ausführbarer Inhalte blockieren" (GUID "D3E037E1-3EB8-44C8-A917-57927947596 "Block execution of potentially obfuscated scripts" (GUID " 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC").
- **Weitere** empfohlene Features – Obwohl es bestimmte ASR-Regeln gibt, die bestimmte Angriffsvektoren in diesen Szenarien mindern, ist es wichtig zu erwähnen, dass AV standardmäßig Skripts (PowerShell, Windows Script Host, JavaScript, VBScript und mehr) über die Antischantischungsscanschnittstelle (AmSI) in Echtzeit überprüfen kann. Weitere Informationen finden Sie hier: [AntischalwareScan Interface (AMSI)](/windows/win32/amsi/antimalware-scan-interface-portal).

### <a name="block-launch-of-child-processes"></a>Blockieren des Startes von untergeordneten Prozessen

- **Gilt für**– Adobe Acrobat
- **Prozesse**– AcroRd32.exe, Acrobat.exe
- **Vorgang**– Prozessausführung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse,** Dienste – cmd.exe, powershell.exe, wscript.exe
- **Attack Surface Reduction Rules**– ASR-Regeln ermöglichen das Blockieren des Startens untergeordneter Prozesse durch Adobe Reader. Der Regelname ist "Adobe Reader am Erstellen untergeordneter Prozesse blockieren", GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c".
- **Weitere empfohlene Features**– N/A


### <a name="block-download-or-creation-of-executable-content"></a>Herunterladen oder Erstellen ausführbarer Inhalte blockieren

- **Gilt für**- CertUtil: Herunterladen oder Erstellen von ausführbaren Dateien blockieren 
- **Prozesse**– certutil.exe
- **Vorgang**– Dateierstellung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**- *.exe
- **Attack Surface Reduction-Regeln**– ASR-Regeln unterstützen diese Szenarien nicht, da sie Teil des Microsoft Defender Antivirus-Schutzes sind.
- **Weitere empfohlene Features**: Microsoft Defender AV hindert CertUtil am Erstellen oder Herunterladen ausführbarer Inhalte.


### <a name="block-processes-from-stopping-critical-system-components"></a>Blockieren des Beendens kritischer Systemkomponenten durch Prozesse

- **Gilt für**– Alle Prozesse
- **Prozesse**– *
- **Vorgang**– Prozessendigung
- Beispiele für **Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse,** Dienste – MsSense.exe, MsMpEng.exe, NisSrv.exe, svchost.exe*, services.exe, csrss.exe, smss.exe, wininit.exe und mehr.
- **Attack Surface Reduction-Regeln**– ASR-Regeln unterstützen diese Szenarien nicht, da sie durch integrierten Windows 10-Sicherheitsschutz geschützt sind.
- **Weitere empfohlene Features:** ELAM (Early Launch AnMalware), PPL (Protection Process Light), PPL AnMalware Light und System Guard.

### <a name="block-specific-launch-process-attempt"></a>Block specific launch Process Attempt

- **Gilt für**– spezifische Prozesse
- **Prozesse**– "Name Ihres Prozesses"
- **Vorgang**– Prozessausführung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse,** Dienste – tor.exe, bittorrent.exe, cmd.exe, powershell.exe und mehr
- **Attack Surface Reduction-Regeln**– Allgemeine AsR-Regeln sind nicht für die Funktion als Anwendungs-Manager konzipiert.
- **Weitere empfohlene Features:** Um zu verhindern, dass Benutzer bestimmte Prozesse oder Programme starten, wird empfohlen, Windows Defender Anwendungssteuerung zu verwenden. Microsoft Defender für Endpunktdatei- und #A0 kann in einem Szenario für die Reaktion auf Vorfälle verwendet werden (sollte nicht als Anwendungssteuerungsmechanismus gesehen werden).
    
### <a name="block-unauthorized-changes-to-microsoft-defender-antivirus-configurations"></a>Blockieren nicht autorisierter Änderungen an Microsoft Defender Antivirus-Konfigurationen

- **Gilt für**– Alle Prozesse
- **Prozesse**– *
- **Vorgang**– Registrierungsänderungen
- Beispiele für **Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse,** Dienste - HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware, HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring und so weiter.
- **Attack Surface Reduction-Regeln**– ASR-Regeln decken diese Szenarien nicht ab, da sie Teil des integrierten Microsoft Defender for Endpoint-Schutzes sind.
- Weitere empfohlene Features **–** Tamper Protection (Opt-In, verwaltet von Intune) verhindert nicht autorisierte Änderungen an DisableAntiVirus, DisableAntiSpyware, DisableRealtimeMonitoring, DisableOnAccessProtection, DisableBehaviorMonitoring und DisableIOAVProtection-Registrierungsschlüsseln (und mehr).

Siehe auch

- [FAQ zu Verringerung der Angriffsfläche](attack-surface-reduction-faq.md)
- [Aktivieren der Regeln zur Verringerung der Angriffsfläche](enable-attack-surface-reduction.md)
- [Auswerten der Regeln zur Verringerung der Angriffsfläche](evaluate-attack-surface-reduction.md)
