---
title: Migrieren von HIPS eines Drittanbieters zu ASR-Regeln
description: Beschreibt, wie eine Migration von einer Host Intrusion Prevention System (HIPS)-Lösung eines Drittanbieters zu ASR-Regeln erfolgt.
keywords: Attack Surface Reduction-Regeln, Asr-, Asr-Regeln, Hips, Host Intrusion Prevention-System, Schutzregeln, Anti-Exploit, Antiexploit, Exploit, Infektionsverhinderung, Microsoft Defender für Endpunkt
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
ms.openlocfilehash: fd7c6a217c1bc1ce3b278afb911988b94a6951e0
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062153"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>Migrieren von HIPS eines Drittanbieters zu ASR-Regeln

Dieser Artikel hilft Ihnen beim Zuordnen allgemeiner Regeln zu Microsoft Defender für Endpunkt.

## <a name="scenarios-when-migrating-from-a-third-party-hips-product-to-asr-rules"></a>Szenarien bei der Migration von einem HIPS-Produkt eines Drittanbieters zu ASR-Regeln

### <a name="block-creation-of-specific-files-and-registry-keys"></a>Blockieren der Erstellung bestimmter Dateien und Registrierungsschlüssel

- **Gilt für**– Alle Prozesse
- **Vorgang**– Dateierstellung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**- *.ze crypto, *.odin, *.locky, *.jaff, *.lukitus, *.wnry, *.krab
- **Attack Surface Reduction-Regeln**– ASR-Regeln blockieren die Angriffstechniken und nicht die Indikatoren für Kompromittierung (Indicators of Compromise, IOC). Das Blockieren einer bestimmten Dateierweiterung ist nicht immer nützlich, da sie keine Kompromittierung eines Geräts verhindert. Ein Angriff wird nur teilweise verhindert, bis Angreifer einen neuen Erweiterungstyp für die Nutzlast erstellen.
- **Weitere empfohlene Features**– Die Aktivierung von Microsoft Defender AV sowie cloudbasierter Schutz und Verhaltensanalysen wird dringend empfohlen. Es wird empfohlen, eine andere Verhinderung zu verwenden, z. B. die ASR-Regel "Erweiterten Schutz vor Ransomware verwenden". Dies bietet einen besseren Schutz vor Ransomware-Angriffen. Darüber hinaus werden viele dieser Registrierungsschlüssel von Microsoft Defender für Endpunkt überwacht, z. B. ASEP-Techniken, die bestimmte Warnungen auslösen. Die verwendeten Registrierungsschlüssel erfordern ein Minimum an Berechtigungen für lokale Administratoren oder vertrauenswürdige Installationsprogramme, die geändert werden können. Es wird empfohlen, eine gesperrte Umgebung mit minimalen Administratorkonten oder -rechten zu verwenden. Andere Systemkonfigurationen können aktiviert werden, einschließlich "Deaktivieren von SeDebug für nicht erforderliche Rollen", die Teil unserer umfassenderen Sicherheitsempfehlungen sind.

### <a name="block-creation-of-specific-files-and-registry-keys"></a>Blockieren der Erstellung bestimmter Dateien und Registrierungsschlüssel

- **Gilt für**– Alle Prozesse
- **Prozesse**– N/A
- **Operation**– Registrierungsänderungen
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste** -  *\Software*,HKCU\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs *\StartExe, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options*\Debugger, HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit*\MonitorProcessExit
- **Attack Surface Reduction-Regeln**– ASR-Regeln blockieren die Angriffstechniken und nicht die Indikatoren für Kompromittierung (Indicators of Compromise, IOC). Das Blockieren einer bestimmten Dateierweiterung ist nicht immer nützlich, da sie keine Kompromittierung eines Geräts verhindert. Ein Angriff wird nur teilweise verhindert, bis Angreifer einen neuen Erweiterungstyp für die Nutzlast erstellen.
- **Weitere empfohlene Features**– Die Aktivierung von Microsoft Defender AV sowie cloudbasierter Schutz und Verhaltensanalysen wird dringend empfohlen. Es wird empfohlen, zusätzliche Prävention zu verwenden, z. B. die ASR-Regel "Erweiterten Schutz vor Ransomware verwenden". Dies bietet einen besseren Schutz vor Ransomware-Angriffen. Darüber hinaus werden einige dieser Registrierungsschlüssel von Microsoft Defender für Endpunkt überwacht, z. B. ASEP-Techniken, die bestimmte Warnungen auslösen. Darüber hinaus erfordern die verwendeten Registrierungsschlüssel ein Minimum an Berechtigungen für lokale Administratoren oder vertrauenswürdige Installationsprogramme, die geändert werden können. Es wird empfohlen, eine gesperrte Umgebung mit minimalen Administratorkonten oder -rechten zu verwenden. Andere Systemkonfigurationen können aktiviert werden, einschließlich "Deaktivieren von SeDebug für nicht erforderliche Rollen", die Teil unserer umfassenderen Sicherheitsempfehlungen sind.

### <a name="block-untrusted-programs-from-running-from-removable-drives"></a>Blockieren der Ausführung nicht vertrauenswürdiger Programme von Wechseldatenträgern

- **Gilt für**– Nicht vertrauenswürdige Programme von USB
- **Prozesse**– *
- **Operation**– Prozessausführung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste:-*
- **Attack Surface Reduction-Regeln**– ASR-Regeln verfügen über eine integrierte Regel, um das Starten von nicht vertrauenswürdigen und nicht signierten Programmen von Wechseldatenträgern zu verhindern: "Blockieren von nicht vertrauenswürdigen und nicht signierten Prozessen, die über USB ausgeführt werden", GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4".
- **Weitere empfohlene Features**– Weitere Steuerelemente für USB-Geräte und andere Wechselmedien mit Microsoft Defender für Endpunkt: So steuern Sie [USB-Geräte und andere Wechselmedien mit Microsoft Defender für Endpunkt.](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)

### <a name="block-mshta-from-launching-certain-child-processes"></a>Blockieren, dass Mshta bestimmte untergeordnete Prozesse startet

- **Gilt für**– Mshta
- **Prozesse**– mshta.exe
- **Operation**– Prozessausführung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**– powershell.exe, cmd.exe, regsvr32.exe
- **Attack Surface Reduction-Regeln**– ASR-Regeln enthalten keine bestimmte Regel, um zu verhindern, dass untergeordnete Prozesse "mshta.exe". Dieses Steuerelement liegt im Zuständigkeitsbereich von Exploit-Schutz oder Windows Defender Anwendungssteuerung.
- **Weitere empfohlene Features:** Aktivieren Sie Windows Defender Anwendungssteuerung, um zu verhindern, dass mshta.exe vollständig ausgeführt werden. Wenn Ihre Organisation "mshta.exe" für Branchen-Apps erfordert, konfigurieren Sie eine bestimmte Windows Defender Exploit-Schutz-Regel, um zu verhindern, dass mshta.exe untergeordnete Prozesse starten.

### <a name="block-outlook-from-launching-child-processes"></a>Verhindern, dass Outlook untergeordnete Prozesse starten

- **Gilt für**– Outlook
- **Prozesse**– outlook.exe
- **Operation**– Prozessausführung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**– powershell.exe
- **Attack Surface Reduction-Regeln**– ASR-Regeln verfügen über eine integrierte Regel, die verhindert, dass Office Kommunikations-Apps (Outlook, Skype und Teams) untergeordnete Prozesse starten: "Blockieren Office Kommunikationsanwendung am Erstellen untergeordneter Prozesse", GUID "26190899-1602-49e8-8b27-eb1d0a1ce869".
- **Weitere empfohlene Features**– Es wird empfohlen, den eingeschränkten Sprachmodus für PowerShell zu aktivieren, um die Angriffsfläche von PowerShell zu minimieren.


### <a name="block-office-apps-from-launching-child-processes-and-from-creating-executable-content"></a>Verhindern, dass Office Apps untergeordnete Prozesse starten und ausführbare Inhalte erstellen

- **Gilt für**– Office  
- **Prozesse**– winword.exe, powerpnt.exe, excel.exe
- **Operation**– Prozessausführung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**– powershell.exe, cmd.exe, wscript.exe, mshta.exe, EQNEDT32.EXE, regsrv32.exe
- **Attack Surface Reduction-Regeln**– ASR-Regeln verfügen über eine integrierte Regel, um zu verhindern, dass Office Apps untergeordnete Prozesse starten: "Alle Office Anwendungen am Erstellen untergeordneter Prozesse hindern", GUID "D4F940AB-401B-4EFC-AADC-AD5F3C50688A".
- **Weitere empfohlene Features**– Nicht angemeldet
    
### <a name="block-office-apps-from-launching-child-processes-and-from-creating-executable-content"></a>Verhindern, dass Office Apps untergeordnete Prozesse starten und ausführbare Inhalte erstellen

- **Gilt für**– Office
- **Prozesse**– winword.exe, powerpnt.exe, excel.exe
- **Vorgang**– Dateierstellung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**- C:\Users *\AppData **.exe, C:\ProgramData**.exe, C:\ProgramData**.com, C:\Users* AppData\Local\Temp **.com, C:\Users*\Downloads**.exe, C:\Users *\AppData **.scf, C:\ProgramData**.scf, C:\Users\Public*.exe, C:\Users*\Desktop\.exe
- **Attack Surface Reduction-Regeln**– N/A.

### <a name="block-wscript-from-reading-certain-types-of-files"></a>Blockieren des Lesens bestimmter Dateitypen durch Wscript

- **Gilt für**– Wscript
- **Prozesse**– wscript.exe
- **Operation**– Datei lesen
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**– C:\Users *\AppData**.js, C:\Users*\Downloads**.js
- **Attack Surface Reduction-Regeln–** Aufgrund von Zuverlässigkeits- und Leistungsproblemen können ASR-Regeln nicht verhindern, dass ein bestimmter Prozess einen bestimmten Skriptdateityp liest. Wir verfügen über eine Regel, um Angriffsvektoren zu verhindern, die aus diesen Szenarien stammen können. Der Regelname lautet "Verhindern, dass JavaScript oder VBScript heruntergeladene ausführbare Inhalte startet" (GUID "D3E037E1-3EB8-44C8-A917-57927947596" "Block execution of potentially obfuscated scripts" (GUID " 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC").
- **Weitere empfohlene Features**– Obwohl es bestimmte ASR-Regeln gibt, die bestimmte Angriffsvektoren in diesen Szenarien mindern, ist es wichtig zu erwähnen, dass AV Skripts (PowerShell, Windows Script Host, JavaScript, VBScript und mehr) standardmäßig über die Antischadsoftwarescanschnittstelle (Antimalware Scan Interface, AMSI) in Echtzeit überprüfen kann. Weitere Informationen finden Sie hier: [Antischadsoftware-Scanschnittstelle (ANTIMALWARE Scan Interface, AMSI).](/windows/win32/amsi/antimalware-scan-interface-portal)

### <a name="block-launch-of-child-processes"></a>Blockieren des Starts untergeordneter Prozesse

- **Gilt für**– Adobe Adobe Acrobat
- **Prozesse**– AcroRd32.exe, Acrobat.exe
- **Operation**– Prozessausführung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**– cmd.exe, powershell.exe, wscript.exe
- **Attack Surface Reduction-Regeln–** ASR-Regeln ermöglichen das Blockieren von Adobe Reader am Starten untergeordneter Prozesse. Der Regelname lautet "Adobe Reader am Erstellen untergeordneter Prozesse hindern", GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c".
- **Weitere empfohlene Features**– Nicht angemeldet


### <a name="block-download-or-creation-of-executable-content"></a>Herunterladen oder Erstellen ausführbarer Inhalte blockieren

- **Gilt für**– CertUtil: Herunterladen oder Erstellen von ausführbaren Dateien blockieren 
- **Prozesse**– certutil.exe
- **Vorgang**– Dateierstellung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**– *.exe
- **Attack Surface Reduction-Regeln**– ASR-Regeln unterstützen diese Szenarien nicht, da sie Teil Microsoft Defender Antivirus Schutzes sind.
- **Andere empfohlene Features**– Microsoft Defender AV verhindert, dass CertUtil ausführbare Inhalte erstellt oder herunterlädt.


### <a name="block-processes-from-stopping-critical-system-components"></a>Verhindern, dass Prozesse kritische Systemkomponenten beenden

- **Gilt für**– Alle Prozesse
- **Prozesse**– *
- **Vorgang**– Prozessbeendigung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**– MsSense.exe, MsMpEng.exe, NisSrv.exe, svchost.exe*, services.exe, csrss.exe, smss.exe, wininit.exe und vieles mehr.
- **Attack Surface Reduction-Regeln**– ASR-Regeln unterstützen diese Szenarien nicht, da sie durch Windows 10 integrierten Sicherheitsschutz geschützt sind.
- **Weitere empfohlene Features:** ELAM (Early Launch AntiMalware), PPL (Protection Process Light), PPL AntiMalware Light und System Guard.

### <a name="block-specific-launch-process-attempt"></a>Blockieren eines bestimmten Startvorgangsversuchs

- **Gilt für**– bestimmte Prozesse
- **Prozesse**– "Benennen Des Prozesses"
- **Operation**– Prozessausführung
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**– tor.exe, bittorrent.exe, cmd.exe, powershell.exe und mehr
- **Attack Surface Reduction-Regeln**– ASR-Regeln sind insgesamt nicht für die Funktion als Anwendungs-Manager konzipiert.
- **Weitere empfohlene Features**– Um zu verhindern, dass Benutzer bestimmte Prozesse oder Programme starten, wird empfohlen, Windows Defender Anwendungssteuerung zu verwenden. Microsoft Defender für Endpunktdatei- und Zertifikatsindikatoren können in einem Vorfallreaktionsszenario verwendet werden (sollten nicht als Mechanismus zur Anwendungssteuerung betrachtet werden).
    
### <a name="block-unauthorized-changes-to-microsoft-defender-antivirus-configurations"></a>Blockieren nicht autorisierter Änderungen an Microsoft Defender Antivirus Konfigurationen

- **Gilt für**– Alle Prozesse
- **Prozesse**– *
- **Operation**– Registrierungsänderungen
- **Beispiele für Dateien/Ordner, Registrierungsschlüssel/Werte, Prozesse, Dienste**– HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware, HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring usw.
- **Attack Surface Reduction-Regeln**– ASR-Regeln decken diese Szenarien nicht ab, da sie Teil des integrierten Microsoft Defender für Endpunkt-Schutzes sind.
- **Andere empfohlene Features**– Manipulationsschutz (Opt-In, verwaltet von Intune) verhindert nicht autorisierte Änderungen an den Registrierungsschlüsseln DisableAntiVirus, DisableAntiSpyware, DisableRealtimeMonitoring, DisableOnAccessProtection, DisableBehaviorMonitoring und DisableIOAVProtection (und mehr).

Siehe auch

- [Häufig gestellte Fragen zur Verringerung der Angriffsfläche](attack-surface-reduction-faq.yml)
- [Aktivieren der Regeln zur Verringerung der Angriffsfläche](enable-attack-surface-reduction.md)
- [Auswerten der Regeln zur Verringerung der Angriffsfläche](evaluate-attack-surface-reduction.md)
