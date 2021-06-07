---
title: Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen
description: Verwalten, wie Microsoft Defender Antivirus Schutz- und Produktupdates erhält.
keywords: Updates, Sicherheitsgrundwerte, Schutz, Updates planen, Updates erzwingen, mobile Updates, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 06/03/2021
ms.openlocfilehash: e67f783552cca5cc36c1563f5e5557796028ea18
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772017"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender Antivirus

Es gibt zwei Arten von Updates, um Microsoft Defender Antivirus auf dem neuesten Stand zu halten:

- Security Intelligence-Updates
- Produktupdates

> [!IMPORTANT]
> Es ist wichtig, Microsoft Defender Antivirus auf dem neuesten Stand zu halten, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind.
> 
> Aktualisieren Sie den Virenschutz auch dann, wenn Microsoft Defender Antivirus im [passiven Modus](./microsoft-defender-antivirus-compatibility.md)ausgeführt wird.
> 
> Informationen zum aktuellen Modul, zur Plattform und zum Signaturdatum finden Sie in den [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware](https://www.microsoft.com/en-us/wdsi/defenderupdates)von Microsoft.

## <a name="security-intelligence-updates"></a>Security Intelligence-Updates

Microsoft Defender Antivirus verwendet über die Cloud bereitgestellten Schutz (auch als Microsoft Advanced Protection Service oder MAPS bezeichnet) und lädt regelmäßig Security [Intelligence-Updates](cloud-protection-microsoft-defender-antivirus.md) herunter, um Schutz bereitzustellen.

> [!NOTE]
> Updates werden unter den folgenden KB-Nummern veröffentlicht:  
> - Microsoft Defender Antivirus: KB2267602  
> - System Center Endpoint Protection: KB2461484

Der über die Cloud bereitgestellte Schutz ist immer aktiviert und erfordert eine aktive Verbindung mit dem Internet, damit er funktioniert. Security Intelligence-Updates erfolgen in einem geplanten Zeitplan (konfigurierbar über die Richtlinie). Weitere Informationen finden Sie unter Verwenden des von [Microsoft in der Cloud bereitgestellten Schutzes in Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md) 

Eine Liste der neuesten Sicherheitsupdates finden Sie unter [Security Intelligence-Updates für Microsoft Defender Antivirus und andere Antischadsoftware](https://www.microsoft.com/en-us/wdsi/defenderupdates)von Microsoft.

Modulupdates sind in Security Intelligence-Updates enthalten und werden monatlich veröffentlicht.

## <a name="product-updates"></a>Produktupdates

Microsoft Defender Antivirus erfordert [monatliche Updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (als *Plattformupdates* bezeichnet) und erhält wichtige Funktionsupdates zusammen mit Windows 10 Versionen.

Sie können die Verteilung von Updates über eine der folgenden Methoden verwalten: 

- [Windows Server Update Service (WSUS)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- Die übliche Methode zum Bereitstellen von Microsoft und Windows Updates für Endpunkte in Ihrem Netzwerk.

Weitere Informationen finden Sie unter [Verwalten der Quellen für Microsoft Defender Antivirus Schutzupdates.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)

> [!NOTE]
> Monatliche Updates werden in Phasen veröffentlicht, was dazu führt, dass mehrere Pakete in Ihren [Windows Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)angezeigt werden.

## <a name="monthly-platform-and-engine-versions"></a>Monatliche Plattform- und Modulversionen

Informationen zum Aktualisieren oder Installieren des Plattformupdates finden Sie unter [Update für Windows Defender Antischadsoftwareplattform.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)

Alle unsere Updates enthalten 
- Leistungsverbesserungen;
- Verbesserungen der Dienstbarkeit; Und 
- Integrationsverbesserungen (Cloud, Microsoft 365 Defender).
<br/>
<details>
<summary> April-2021 (Plattform: 4.18.2104.14 | Modul: 1.1.18100.5)</summary>

&ensp;Security Intelligence Update Version: **1.337.2.0**  
&ensp;Veröffentlicht: **1. April 2021**  
&ensp;Plattform: **4.18.2104.14**  
&ensp;Modul: **1.1.18100.5**  
&ensp;Supportphase: **Sicherheits- und kritische Updates**
    
### <a name="whats-new"></a>Neuerungen
- Zusätzliche Verhaltensüberwachungslogik
- Verbesserte Kernelmodus-Keyloggererkennung

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details>

<details>
<summary> März-2021 (Plattform: 4.18.2103.7 | Modul: 1.1.18000.5)</summary>

&ensp;Version des Security Intelligence-Updates: **1.335.36.0**  
&ensp;Veröffentlicht: **1. April 2021**  
&ensp;Plattform: **4.18.2103.7**  
&ensp;Modul: **1.1.18000.5**  
&ensp;Supportphase: **Sicherheits- und kritische Updates**
    
### <a name="whats-new"></a>Neuerungen

- Verbesserung des Verhaltensüberwachungsmoduls 
- Erweiterte Brute-Force-Attack-Gegenmaßnahmen im Netzwerk 
- Weitere fehlgeschlagene Ereignisgenerierung bei Manipulationsversuch, wenn [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md) aktiviert ist

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details><details>
<summary> Februar-2021 (Plattform: 4.18.2102.3 | Modul: 1.1.17900.7)</summary>

&ensp;Version des Security Intelligence-Updates: **1.333.7.0**  
&ensp;Veröffentlicht: **9. März 2021**  
&ensp;Plattform: **4.18.2102.3**  
&ensp;Modul: **1.1.17900.7**  
&ensp;Supportphase: **Sicherheits- und kritische Updates**
    
### <a name="whats-new"></a>Neuerungen

- Verbesserte Dienstwiederherstellung durch [Manipulationsschutz](prevent-changes-to-security-settings-with-tamper-protection.md)
- Erweitern des Umfangs des Manipulationsschutzes

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a>Frühere Versionsupdates: Nur Support für technische Upgrades

Nachdem eine neue Paketversion veröffentlicht wurde, wird der Support für die vorherigen beiden Versionen auf den technischen Support reduziert. Ältere Versionen sind in diesem Abschnitt aufgeführt und werden nur für technischen Upgrade-Support bereitgestellt. 
<br/><br/>
<details>
<summary> Januar -2021 (Plattform: 4.18.2101.9 | Modul: 1.1.17800.5)</summary>

&ensp;Version des Security Intelligence-Updates: **1.327.1854.0**  
&ensp;Veröffentlicht: **2. Februar 2021**  
&ensp;Plattform: **4.18.2101.9**  
&ensp;Modul: **1.1.17800.5**  
&ensp;Supportphase: **Technischer Upgrade-Support (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Verbesserungen bei der Shellcode-Exploit-Erkennung
- Erhöhte Sichtbarkeit für Diebstahlsversuche von Anmeldeinformationen
- Verbesserungen bei Antistempelfunktionen in Microsoft Defender Antivirus-Diensten
- Verbesserte Unterstützung für ARM x64-Emulation
- Fix: EDR Benachrichtigung blockieren bleibt im Bedrohungsverlauf, nachdem der Echtzeitschutz die erste Erkennung durchgeführt hat

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details><details>
<summary> November-2020 (Plattform: 4.18.2011.6 | Modul: 1.1.17700.4)</summary>

&ensp;Version des Security Intelligence-Updates: **1.327.1854.0**  
&ensp;Veröffentlicht: **03. Dezember 2020**  
&ensp;Plattform: **4.18.2011.6**  
&ensp;Modul: **1.1.17700.4**  
&ensp;Supportphase: **Technischer Upgrade-Support (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Verbesserte [SmartScreen-Statusunterstützung](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) für die Protokollierung

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details><details>
<summary> Oktober-2020 (Plattform: 4.18.2010.7 | Modul: 1.1.17600.5)</summary>

&ensp;Security Intelligence Update-Version: **1.327.7.0**  
&ensp;Veröffentlicht: **29. Oktober 2020**  
&ensp;Plattform: **4.18.2010.7**  
&ensp;Modul: **1.1.17600.5**  
&ensp;Supportphase: **Technischer Upgrade-Support (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Neue Beschreibungen für besondere Bedrohungskategorien
- Verbesserte Emulationsfunktionen
- Verbesserte Hostadressen-Allow/Block-Funktionen
- Neue Option in Defender CSP zum Ignorieren der Zusammenführung lokaler Benutzerausschlüsse

### <a name="known-issues"></a>Bekannte Probleme

Keine bekannten Probleme  
<br/>
</details><details>
<summary> September-2020 (Plattform: 4.18.2009.7 | Modul: 1.1.17500.4)</summary>

&ensp;Version des Security Intelligence-Updates: **1.325.10.0**  
&ensp;Veröffentlicht: **01. Oktober 2020**  
&ensp;Plattform: **4.18.2009.7**  
&ensp;Modul: **1.1.17500.4**  
&ensp;Supportphase: **Technischer Upgrade-Support (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Zum Wiederherstellen von Dateien in Quarantäne sind Administratorberechtigungen erforderlich.
- XML-formatierte Ereignisse werden jetzt unterstützt
- CSP-Unterstützung für das Ignorieren von Ausschlusszusammenführungen
- Neue Verwaltungsschnittstellen für:
   - UDP-Prüfung
   - Netzwerkschutz auf Server 2019
   - IP-Adressausschlüsse für Netzwerkschutz
- Verbesserte Sichtbarkeit von TPM-Messungen
- Verbesserte Office VBA-Modulüberprüfung

### <a name="known-issues"></a>Bekannte Probleme

Keine bekannten Probleme  
<br/>
</details>
<details>
<summary> August-2020 (Plattform: 4.18.2008.9 | Modul: 1.1.17400.5)</summary>

&ensp;Security Intelligence-Updateversion: **1.323.9.0**  
&ensp;Veröffentlicht: **27. August 2020**  
&ensp;Plattform: **4.18.2008.9**  
&ensp;Modul: **1.1.17400.5**  
&ensp;Supportphase: **Technischer Upgrade-Support (nur)**

### <a name="whats-new"></a>Neuerungen

- Hinzufügen weiterer Telemetrieereignisse
- Verbesserte Telemetrie für Scanereignisse
- Verbesserte Verhaltensüberwachung für Speicherscans
- Verbessertes Scannen von Makrodatenströmen
- `AMRunningMode`Zu Get-MpComputerStatus PowerShell-Cmdlet hinzugefügt
- [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wird ignoriert. Microsoft Defender Antivirus schaltet sich automatisch aus, wenn ein anderes Antivirenprogramm erkannt wird.


### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details>

<details>
<summary> Juli-2020 (Plattform: 4.18.2007.8 | Modul: 1.1.17300.4)</summary>

&ensp;Security Intelligence Update-Version: **1.321.30.0**  
&ensp;Veröffentlicht: **28. Juli 2020**  
&ensp;Plattform: **4.18.2007.8**  
&ensp;Modul: **1.1.17300.4**  
&ensp;Supportphase: **Technischer Upgrade-Support (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Verbesserte Telemetrie für BITS
- Verbesserte Authenticode-Codesignaturzertifikatüberprüfung

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details>

<details>
<summary> Juni -2020 (Plattform: 4.18.2006.10 | Modul: 1.1.17200.2)</summary>

&ensp;Version des Security Intelligence-Updates: **1.319.20.0**  
&ensp;Veröffentlicht: **22. Juni 2020**  
&ensp;Plattform: **4.18.2006.10**  
&ensp;Modul: **1.1.17200.2**  
&ensp;Supportphase: **Technischer Upgrade-Support (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Möglichkeit, den [Speicherort der Supportprotokolle](./collect-diagnostic-data.md) anzugeben
- Überspringen des aggressiven Nachholscans im passiven Modus.
- Zulassen, dass Defender bei getakteten Verbindungen aktualisiert wird
- Leistungsoptimierung bei deaktivierter Zwischenspeicherung mit fester Leistung 
- Feste Registrierungsabfrage 
- Randomisierung der Scanzeit in ADMX behoben

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details>

<details>
<summary> Mai-2020 (Plattform: 4.18.2005.4 | Modul: 1.1.17100.2)</summary>

&ensp;Security Intelligence Update-Version: **1.317.20.0**  
&ensp;Veröffentlicht: **26. Mai 2020**  
&ensp;Plattform: **4.18.2005.4**  
&ensp;Modul: **1.1.17100.2**  
&ensp;Supportphase: **Technischer Upgrade-Support (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Verbesserte Protokollierung für Scanereignisse
- Verbesserte Absturzbehandlung im Benutzermodus.
- Ereignisablaufverfolgung für Manipulationsschutz hinzugefügt
- Amsi-Beispielübermittlung wurde behoben
- Amsi Cloud-Blockierung wurde behoben
- Installationsprotokoll für feste Sicherheitsupdates

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details>

<details>
<summary> April-2020 (Plattform: 4.18.2004.6 | Modul: 1.1.17000.2)</summary>

&ensp;Security Intelligence Update-Version: **1.315.12.0**  
&ensp;Veröffentlicht: **30. April 2020**  
&ensp;Plattform: **4.18.2004.6**  
&ensp;Modul: **1.1.17000.2**  
&ensp;Supportphase: **Technischer Upgrade-Support (nur)**
    
### <a name="whats-new"></a>Neuerungen
- WDfilter-Verbesserungen
- Hinzufügen von Ereignisdaten mit aktionen erfordernden Aktionen zu Angriffsflächenreduzierungsereignissen
- Informationen zur festen Version in Diagnosedaten und WMI
- Fehler bei der Plattformversion in der Benutzeroberfläche nach dem Plattformupdate behoben
- Dynamic URL intel for Fileless Threat Protection
- UEFI-Scanfunktion
- Erweitern der Protokollierung für Updates

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details>

<details>
<summary> März-2020 (Plattform: 4.18.2003.8 | Modul: 1.1.16900.2)</summary>

&ensp;Version des Security Intelligence-Updates: **1.313.8.0**  
&ensp;Veröffentlicht: **24. März 2020**  
&ensp;Plattform: **4.18.2003.8**  
&ensp;Modul: **1.1.16900.4**  
&ensp;Supportphase: **Technischer Upgrade-Support (nur)**
    
### <a name="whats-new"></a>Neuerungen

- CPU-Einschränkungsoption zu [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md) hinzugefügt
- Verbessern der Diagnosefunktion
- Reduzieren des Timeouts für Sicherheitsinformationen (5 Min.)
- Erweitern der internen Protokollfunktion des AMSI-Moduls
- Verbessern der Benachrichtigung für das Blockieren von Prozessen
   
### <a name="known-issues"></a>Bekannte Probleme
[**Fixed**] Microsoft Defender Antivirus überspringt Dateien beim Ausführen einer Überprüfung.

<br/>
</details>

<details>

<summary> Februar-2020 (Plattform: - | Modul: 1.1.16800.2)</summary>
  

&ensp;Version des Security Intelligence-Updates: **1.311.4.0**   
&ensp;Veröffentlicht: **25. Februar 2020**  
&ensp;Plattform/Client: **-**  
&ensp;Modul: **1.1.16800.2**  
&ensp;Supportphase: **Technischer Upgrade-Support (nur)**
     
### <a name="whats-new"></a>Neuerungen

  
### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme
<br/>
</details>

<details>
<summary> Januar -2020 (Plattform: 4.18.2001.10 | Modul: 1.1.16700.2)</summary>
  

Security Intelligence Update-Version: **1.309.32.0**  
Veröffentlicht: **30. Januar 2020**  
Plattform/Client: **4.18.2001.10**  
Modul: **1.1.16700.2**  
&ensp;Supportphase: **Technischer Upgrade-Support (nur)**
     
### <a name="whats-new"></a>Neuerungen

- BSOD in WS2016 mit Exchange behoben
- Unterstützen von Plattformupdates, wenn TMP an den Netzwerkpfad umgeleitet wird
- Plattform- und Modulversionen werden [zu WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) hinzugefügt <!-- The preceding URL must include "/en-us" -->
- Erweitern des Notfallsignaturupdates auf [den passiven Modus](./microsoft-defender-antivirus-compatibility.md)
- Fix 4.18.1911.3 hang
   
### <a name="known-issues"></a>Bekannte Probleme

[**Behoben**] Geräte, die den [modernen Standbymodus verwenden,](/windows-hardware/design/device-experiences/modern-standby) können mit dem Windows Defender Filtertreiber hängen bleiben, was zu einer Schutzlücke führt.  Betroffene Computer scheinen dem Kunden nicht auf die neueste Antischadsoftwareplattform aktualisiert zu haben.  
<br/>
> [!IMPORTANT]
> Dieses Update ist:
> - von RS1-Geräten mit niedrigerer Version der Plattform zur Unterstützung von SHA2 benötigt werden;
> - verfügt über ein Neustart-Flag für Systeme mit hängenden Problemen;
> - wird im April 2020 erneut veröffentlicht und wird nicht durch neuere Updates abgelöst, um die zukünftige Verfügbarkeit zu erhalten;  
> - wird aufgrund der Neustartanforderung als Update kategorisiert; Und
> - wird nur mit [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update)angeboten.
<br/>
</details>

<details>
<summary> November-2019 (Plattform: 4.18.1911.3 | Modul: 1.1.16600.7)</summary>

Security Intelligence Update-Version: **1.307.13.0**  
Veröffentlicht: **7. Dezember 2019**  
Plattform: **4.18.1911.3**  
Modul: **1.1.17000.7**  
Supportphase: **Keine Unterstützung**  
     
### <a name="whats-new"></a>Neuerungen

- MpCmdRun-Ablaufverfolgungsebene wurde behoben
- WDFilter-Versionsinformationen wurden behoben
- Verbessern von Benachrichtigungen (PUA)
- Hinzufügen von MRT-Protokollen zur Unterstützung von Dateien
   
### <a name="known-issues"></a>Bekannte Probleme
Wenn dieses Update installiert ist, benötigt das Gerät das Sprungpaket 4.10.2001.10, um auf die neueste Plattformversion aktualisieren zu können.
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Microsoft Defender Antivirus Plattformunterstützung
Plattform- und Modulupdates werden monatlich bereitgestellt. Um vollständig unterstützt zu werden, bleiben Sie mit den neuesten Plattformupdates auf dem laufenden. Unsere Supportstruktur ist dynamisch und entwickelt sich je nach Verfügbarkeit der neuesten Plattformversion in zwei Phasen:

- **Wartungsphase für Sicherheits- und kritische Updates:** Wenn Sie die neueste Plattformversion ausführen, sind Sie berechtigt, sowohl Sicherheitsupdates als auch kritische Updates für die Antischadsoftwareplattform zu erhalten.
 
- Phase des **technischen Supports (nur)** – Nach der Veröffentlichung einer neuen Plattformversion wird der Support für ältere Versionen (N-2) auf den technischen Support reduziert. Plattformversionen, die älter als N-2 sind, werden nicht mehr unterstützt.*

\*Für Upgrades von der Windows 10-Version (siehe [Plattformversion, die in Windows 10-Versionen enthalten ist)](#platform-version-included-with-windows-10-releases)auf die neueste Plattformversion wird weiterhin technischer Support bereitgestellt.

Während der Phase des technischen Supports (nur) werden kommerzielle angemessene Supportvorfälle über den Microsoft-Kundendienst & Support und die verwalteten Supportangebote von Microsoft (z. B. Premier Support) bereitgestellt. Wenn ein Supportvorfall eine Eskalation zur Entwicklung erfordert, um weitere Anleitungen zu erhalten, ein nicht sicherheitsrelevantes Update oder ein Sicherheitsupdate erfordert, werden Kunden aufgefordert, auf die neueste Plattformversion oder ein Zwischenupdate (*) zu aktualisieren.

### <a name="platform-version-included-with-windows-10-releases"></a>In Windows 10-Versionen enthaltene Plattformversion
Die folgende Tabelle enthält die Microsoft Defender Antivirus Plattform- und Modulversionen, die mit den neuesten Windows 10 Versionen ausgeliefert werden:    

|Windows 10-Version  |Plattformversion  |Modulversion |Supportphase |
|:---|:---|:---|:---|
|2004 (20H1/20H2) |4.18.1909.6 |1.1.17000.2 | Support für technische Upgrades (nur) |
|1909 (19H2) |4.18.1902.5 |1.1.16700.3 | Support für technische Upgrades (nur) |
|1903 (19H1) |4.18.1902.5 |1.1.15600.4 | Support für technische Upgrades (nur) |
|1809 (RS5) |4.18.1807.18075 |1.1.15000.2 | Support für technische Upgrades (nur) |
|1803 (RS4) |4.13.17134.1 |1.1.14600.4 | Support für technische Upgrades (nur) |
|1709 (RS3) |4.12.16299.15 |1.1.14104.0 | Support für technische Upgrades (nur) |
|1703 (RS2) |4.11.15603.2 |1.1.13504.0 | Support für technische Upgrades (nur) |
|1607 (RS1) |4.10.14393.3683 |1.1.12805.0 | Support für technische Upgrades (nur) |  

Informationen zu Windows 10 Version finden Sie im [Windows-Lifecycle-Informationsblatt.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>Updates für die Abbildverwaltung für die Bereitstellung (Deployment Image Servicing and Management, DISM)

Es wird empfohlen, ihre Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016 Betriebssysteminstallationsimages mit den neuesten Antiviren- und Antischadsoftwareupdates zu aktualisieren. Wenn Sie Ihre Betriebssysteminstallationsimages auf dem neuesten Stand halten, vermeiden Sie eine Lücke beim Schutz. 

Weitere Informationen finden Sie unter [Microsoft Defender Update für Windows Installationsimages](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)des Betriebssystems.

<details>
<summary>1.1.2106.01</summary>

&ensp;Paketversion: **1.1.2106.01**    
&ensp;Plattformversion: **4.18.2104.14**   
&ensp;Modulversion: **1.1.18100.6**  
&ensp;Signaturversion: **1.339.1923.0**    
    
### <a name="fixes"></a>Behebungen
- Keine

### <a name="additional-information"></a>Weitere Informationen
- Keine  
<br/>
</details><details>
<summary>1.1.2105.01</summary>

&ensp;Paketversion: **1.1.2105.01**    
&ensp;Plattformversion: **4.18.2103.7**   
&ensp;Modulversion: **1.1.18100.6**  
&ensp;Signaturversion: **1.339.42.0**    
    
### <a name="fixes"></a>Behebungen
- Keine

### <a name="additional-information"></a>Weitere Informationen
- Keine  
<br/>
</details><details>
<summary>1.1.2104.01</summary>

&ensp;Paketversion: **1.1.2104.01**    
&ensp;Plattformversion: **4.18.2102.4**   
&ensp;Modulversion: **1.1.18000.5**  
&ensp;Signaturversion: **1.335.232.0**    
    
### <a name="fixes"></a>Behebungen
- Keine

### <a name="additional-information"></a>Weitere Informationen
- Keine  
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;Paketversion: **1.1.2103.01**    
&ensp;Plattformversion: **4.18.2101.9**   
&ensp;Modulversion: **1.1.17800.5**  
&ensp;Signaturversion: **1.331.2302.0**    
    
### <a name="fixes"></a>Behebungen
- Keine

### <a name="additional-information"></a>Weitere Informationen
- Keine  
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;Paketversion: **1.1.2102.03**    
&ensp;Plattformversion: **4.18.2011.6**   
&ensp;Modulversion: **1.1.17800.5**  
&ensp;Signaturversion: **1.331.174.0**    
    
### <a name="fixes"></a>Behebungen
- Keine

### <a name="additional-information"></a>Weitere Informationen
- Keine  
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;Paketversion: **1.1.2101.02**    
&ensp;Plattformversion: **4.18.2011.6**   
&ensp;Modulversion: **1.1.17700.4**  
&ensp;Signaturversion: **1.329.1796.0**    
    
### <a name="fixes"></a>Behebungen
- Keine

### <a name="additional-information"></a>Weitere Informationen
- Keine  
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;Paketversion: **1.1.2012.01**    
&ensp;Plattformversion: **4.18.2010.7**   
&ensp;Modulversion: **1.1.17600.5**  
&ensp;Signaturversion: **1.327.1991.0**    
    
### <a name="fixes"></a>Behebungen
- Keine

### <a name="additional-information"></a>Weitere Informationen
- Keine  
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;Paketversion: **1.1.2011.02**    
&ensp;Plattformversion: **4.18.2010.7**   
&ensp;Modulversion: **1.1.17600.5**  
&ensp;Signaturversion: **1.327.658.0**    
    
### <a name="fixes"></a>Behebungen
- Keine

### <a name="additional-information"></a>Weitere Informationen
- Aktualisierte Microsoft Defender Antivirus Signaturen  
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;Paketversion: **1.1.2011.01**    
&ensp;Plattformversion: **4.18.2009.7**  
&ensp;Modulversion: **1.1.17600.5**  
&ensp;Signaturversion: **1.327.344.0**    
    
### <a name="fixes"></a>Behebungen
- Keine

### <a name="additional-information"></a>Weitere Informationen
- Keine  
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;Paketversion: **1.1.2011.01**    
&ensp;Plattformversion: **4.18.2008.9**   
&ensp;Modulversion: **1.1.17400.5**  
&ensp;Signaturversion: **1.327.2216.0**    
    
### <a name="fixes"></a>Behebungen
- Keine

### <a name="additional-information"></a>Weitere Informationen
- Unterstützung für Windows 10 RS1 oder neuere Betriebssysteminstallationsimages hinzugefügt.  
<br/>
</details>

## <a name="additional-resources"></a>Weitere Ressourcen

| Artikel | Beschreibung  |
|:---|:---|
|[Microsoft Defender-Update für Windows Betriebssysteminstallationsimages](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | Überprüfen Sie Die Antischadsoftware-Updatepakete für Ihre Betriebssysteminstallationsimages (WIM- und VHD-Dateien). Rufen Sie Microsoft Defender Antivirus Updates für Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016-Installationsimages ab.  |
|[Verwalten, wie Schutzupdates heruntergeladen und angewendet werden](manage-protection-updates-microsoft-defender-antivirus.md) | Schutzupdates können über viele Quellen bereitgestellt werden. |
|[Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen](manage-protection-update-schedule-microsoft-defender-antivirus.md) | Sie können planen, wann Schutzupdates heruntergeladen werden sollen. |
|[Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md) | Wenn ein Endpunkt einen Update- oder geplanten Scan verpasst, können Sie ein Update erzwingen oder die Überprüfung durchführen, wenn sich ein Benutzer das nächste Mal anmeldet. |
|[Verwalten von ereignisbasierten erzwungenen Updates](manage-event-based-updates-microsoft-defender-antivirus.md) | Sie können festlegen, dass Schutzupdates beim Start oder nach bestimmten über die Cloud bereitgestellten Schutzereignissen heruntergeladen werden. |
|[Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| Sie können Einstellungen angeben, z. B. ob Updates bei Akkubetrieb erfolgen sollen, die besonders für mobile Geräte und virtuelle Computer nützlich sind. |
