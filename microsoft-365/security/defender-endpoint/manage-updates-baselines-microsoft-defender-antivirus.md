---
title: Verwalten Microsoft Defender Antivirus Updates und Anwenden von Baselines
description: Verwalten, Microsoft Defender Antivirus Schutz- und Produktupdates erhält.
keywords: updates, security baselines, protection, schedule updates, force updates, mobile updates, wsus
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
ms.date: 05/08/2021
ms.openlocfilehash: 4f2b931018d49affa2d94ddf1a147c4fd2e02085
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302076"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>Verwalten Microsoft Defender Antivirus Updates und Anwenden von Baselines

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender Antivirus

Es gibt zwei Arten von Updates, die Microsoft Defender Antivirus aktualisiert werden:

- Sicherheitsintelligenzupdates
- Produktupdates

> [!IMPORTANT]
> Die Microsoft Defender Antivirus ist wichtig, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind.
> 
> Achten Sie darauf, den Antivirenschutz zu aktualisieren, auch wenn Microsoft Defender Antivirus im [passiven Modus ausgeführt wird.](./microsoft-defender-antivirus-compatibility.md)
> 
> Informationen zum aktuellen Modul, zur Plattform und zum Signaturdatum finden Sie unter [Security Intelligence updates for Microsoft Defender Antivirus and other Microsoft anmalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).

## <a name="security-intelligence-updates"></a>Sicherheitsintelligenzupdates

Microsoft Defender Antivirus verwendet [von der Cloud](cloud-protection-microsoft-defender-antivirus.md) übermittelten Schutz (auch Microsoft Advanced Protection Service oder MAPS genannt) und lädt regelmäßig Sicherheitsintelligenzupdates herunter, um Schutz zu bieten.

> [!NOTE]
> Updates werden unter den folgenden KB-Nummern veröffentlicht:  
> - Microsoft Defender Antivirus: KB2267602  
> - System Center Endpoint Protection: KB2461484

Der von der Cloud übermittelte Schutz ist immer aktiviert und erfordert eine aktive Verbindung mit dem Internet, um zu funktionieren. Sicherheitsintelligenzupdates erfolgen in einer geplanten Schrittfrequenz (konfigurierbar über die Richtlinie). Weitere Informationen finden Sie unter [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md). 

Eine Liste der aktuellen Sicherheitsintelligenzupdates finden Sie unter [Security Intelligence updates for Microsoft Defender Antivirus and other Microsoft anmalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).

Modulupdates sind in Sicherheitsintelligenzupdates enthalten und werden monatlich veröffentlicht.

## <a name="product-updates"></a>Produktupdates

Microsoft Defender Antivirus erfordert [monatliche Updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (auch als Plattformupdates *bezeichnet)* und erhält wichtige Featureupdates neben Windows 10 Versionen.

Sie können die Verteilung von Updates über eine der folgenden Methoden verwalten: 

- [Windows Server Update Service (WSUS)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- Die übliche Methode, die Sie zum Bereitstellen von Microsoft und Windows für Endpunkte in Ihrem Netzwerk verwenden.

Weitere Informationen finden Sie unter [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).

> [!NOTE]
> Monatliche Updates werden in Phasen veröffentlicht, was zu mehreren Paketen führt, die in Ihren [Window Server Update Services angezeigt werden.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)

## <a name="monthly-platform-and-engine-versions"></a>Monatliche Plattform- und Modulversionen

Informationen zum Aktualisieren oder Installieren des Plattformupdates finden Sie unter [Update for Windows Defender anmalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).

Alle unsere Updates enthalten 
- Leistungsverbesserungen;
- Verbesserungen bei der Dienstbarkeit; und 
- Integrationsverbesserungen (Cloud, Microsoft 365 Defender).
<br/>
<details>
<summary> April-2021 (Plattform: 4.18.2104.9| Modul: 1.1.18100.5)</summary>

&ensp;Version des Security Intelligence-Updates: **1.337.2.0**  
&ensp;Veröffentlicht: **1. April 2021**  
&ensp;Plattform: **4.18.2104.9**  
&ensp;Modul: **1.1.18100.5**  
&ensp;Supportphase: **Sicherheits- und kritische Updates**
    
### <a name="whats-new"></a>Neuerungen
- Zusätzliche Verhaltensüberwachungslogik
- Verbesserte Keyloggererkennung im Kernelmodus

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
- Risikominderungen für Brute-Force-Attack im erweiterten Netzwerk 
- Zusätzliche fehlgeschlagene Manipulationsversuchsereignisgenerierung, [wenn Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) aktiviert ist

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
- Erweitern des Schutzes von Manipulationen

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a>Updates früherer Versionen: Nur support für technische Upgrades

Nachdem eine neue Paketversion veröffentlicht wurde, wird die Unterstützung für die beiden vorherigen Versionen auf den technischen Support reduziert. Versionen, die älter sind als die in diesem Abschnitt aufgeführten, werden nur für technischen Upgradesupport bereitgestellt. 
<br/><br/>
<details>
<summary> Januar-2021 (Plattform: 4.18.2101.9 | Modul: 1.1.17800.5)</summary>

&ensp;Updateversion der Sicherheitsintelligenz: **1.327.1854.0**  
&ensp;Veröffentlicht: **2. Februar 2021**  
&ensp;Plattform: **4.18.2101.9**  
&ensp;Modul: **1.1.17800.5**  
&ensp;Supportphase: **Support für technische Upgrades (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Verbesserungen bei der Erkennung von Shellcode-Exploits
- Verbesserte Sichtbarkeit für Versuche zum Stehlen von Anmeldeinformationen
- Verbesserungen bei Antitamperingfeatures in Microsoft Defender Antivirus Diensten
- Verbesserte Unterstützung für ARM x64-Emulation
- Fix: EDR Sperrbenachrichtigung verbleibt im Bedrohungsverlauf, nachdem der Echtzeitschutz die ersterkennung durchgeführt hat

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details><details>
<summary> November-2020 (Plattform: 4.18.2011.6 | Modul: 1.1.17700.4)</summary>

&ensp;Updateversion der Sicherheitsintelligenz: **1.327.1854.0**  
&ensp;Veröffentlicht: **03. Dezember 2020**  
&ensp;Plattform: **4.18.2011.6**  
&ensp;Modul: **1.1.17700.4**  
&ensp;Supportphase: **Support für technische Upgrades (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Verbesserte [Unterstützung der SmartScreen-Statusprotokollierung](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details><details>
<summary> Oktober-2020 (Plattform: 4.18.2010.7 | Modul: 1.1.17600.5)</summary>

&ensp;Version des Security Intelligence-Updates: **1.327.7.0**  
&ensp;Veröffentlicht: **29. Oktober 2020**  
&ensp;Plattform: **4.18.2010.7**  
&ensp;Modul: **1.1.17600.5**  
&ensp;Supportphase: **Support für technische Upgrades (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Neue Beschreibungen für spezielle Bedrohungskategorien
- Verbesserte Emulationsfunktionen
- Verbesserte Funktionen zum Zulassen/Blockieren von Hostadressen
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
&ensp;Supportphase: **Support für technische Upgrades (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Administratorberechtigungen sind erforderlich, um Dateien in Quarantäne wiederherzustellen
- XML-formatierte Ereignisse werden jetzt unterstützt
- CSP-Unterstützung für das Ignorieren von Ausschlusszusammenführungen
- Neue Verwaltungsschnittstellen für:
   - UDP-Prüfung
   - Netzwerkschutz auf Server 2019
   - IP-Adressausschlüsse für Netzwerkschutz
- Verbesserte Sichtbarkeit von TPM-Messungen
- Verbesserte überprüfung Office VBA-Moduls

### <a name="known-issues"></a>Bekannte Probleme

Keine bekannten Probleme  
<br/>
</details>
<details>
<summary> August-2020 (Plattform: 4.18.2008.9 | Modul: 1.1.17400.5)</summary>

&ensp;Updateversion der Sicherheitsintelligenz: **1.323.9.0**  
&ensp;Veröffentlicht: **27. August 2020**  
&ensp;Plattform: **4.18.2008.9**  
&ensp;Modul: **1.1.17400.5**  
&ensp;Supportphase: **Support für technische Upgrades (nur)**

### <a name="whats-new"></a>Neuerungen

- Hinzufügen von weiteren Telemetrieereignissen
- Verbesserte Telemetrie des Scanereigniss
- Verbesserte Verhaltensüberwachung für Speicherscans
- Verbesserte Überprüfung von Makrodatenströmen
- Hinzugefügt `AMRunningMode` zu Get-MpComputerStatus PowerShell-Cmdlet
- [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wird ignoriert. Microsoft Defender Antivirus automatisch deaktiviert, wenn ein anderes Antivirenprogramm erkannt wird.


### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details>

<details>
<summary> Juli-2020 (Plattform: 4.18.2007.8 | Modul: 1.1.17300.4)</summary>

&ensp;Version des Security Intelligence-Updates: **1.321.30.0**  
&ensp;Veröffentlicht: **28. Juli 2020**  
&ensp;Plattform: **4.18.2007.8**  
&ensp;Modul: **1.1.17300.4**  
&ensp;Supportphase: **Support für technische Upgrades (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Verbesserte Telemetrie für BITS
- Verbesserte Validierung von Authenticode-Codesignaturzertifikaten

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details>

<details>
<summary> Juni-2020 (Plattform: 4.18.2006.10 | Modul: 1.1.17200.2)</summary>

&ensp;Version des Security Intelligence-Updates: **1.319.20.0**  
&ensp;Veröffentlicht: **22. Juni 2020**  
&ensp;Plattform: **4.18.2006.10**  
&ensp;Modul: **1.1.17200.2**  
&ensp;Supportphase: **Support für technische Upgrades (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Möglichkeit zum Angeben des [Speicherorts der Supportprotokolle](./collect-diagnostic-data.md)
- Überspringen der aggressiven Nachholscan im passiven Modus.
- Zulassen, dass Defender bei gemessenen Verbindungen aktualisiert wird
- Leistungsoptimierung behoben, wenn die Zwischenspeicherung deaktiviert ist 
- Registrierungsabfrage wurde behoben 
- Randomisierung der Scanzeit in ADMX behoben

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details>

<details>
<summary> Mai-2020 (Plattform: 4.18.2005.4 | Modul: 1.1.17100.2)</summary>

&ensp;Version des Security Intelligence-Updates: **1.317.20.0**  
&ensp;Veröffentlicht: **26. Mai 2020**  
&ensp;Plattform: **4.18.2005.4**  
&ensp;Modul: **1.1.17100.2**  
&ensp;Supportphase: **Support für technische Upgrades (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Verbesserte Protokollierung für Scanereignisse
- Verbesserte Absturzbehandlung im Benutzermodus.
- Ereignisablaufverfolgung für Manipulationsschutz hinzugefügt
- AmSI-Beispielübermittlung wurde behoben
- Blockierung der AMSI-Cloud behoben
- Installationsprotokoll für Sicherheitsupdates behoben

### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme  
<br/>
</details>

<details>
<summary> April-2020 (Plattform: 4.18.2004.6 | Modul: 1.1.17000.2)</summary>

&ensp;Version des Security Intelligence-Updates: **1.315.12.0**  
&ensp;Veröffentlicht: **30. April 2020**  
&ensp;Plattform: **4.18.2004.6**  
&ensp;Modul: **1.1.17000.2**  
&ensp;Supportphase: **Support für technische Upgrades (nur)**
    
### <a name="whats-new"></a>Neuerungen
- Verbesserungen bei WDfilter
- Hinzufügen von ereignisfähigeren Ereignisdaten zum Angriff auf Erkennungsereignisse zur Oberflächenreduzierung
- Informationen zu festen Versionen in Diagnosedaten und WMI
- Falsche Plattformversion in der Benutzeroberfläche nach dem Plattformupdate behoben
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
&ensp;Supportphase: **Support für technische Upgrades (nur)**
    
### <a name="whats-new"></a>Neuerungen

- Zu [MpCmdRun hinzugefügte CPU-Einschränkungsoption](./command-line-arguments-microsoft-defender-antivirus.md)
- Verbessern der Diagnosefunktion
- Reduzieren des Timeouts für Sicherheitsintelligenz (5 Min.)
- Erweitern der internen Protokollfunktion des AMSI-Moduls
- Verbessern der Benachrichtigung für prozessblockierung
   
### <a name="known-issues"></a>Bekannte Probleme
[**Fixed**] Microsoft Defender Antivirus beim Ausführen einer Überprüfung werden Dateien übersprungen.

<br/>
</details>

<details>

<summary> Februar-2020 (Plattform: - | Modul: 1.1.16800.2)</summary>
  

&ensp;Version des Security Intelligence-Updates: **1.311.4.0**   
&ensp;Veröffentlicht: **25. Februar 2020**  
&ensp;Plattform/Client: **-**  
&ensp;Modul: **1.1.16800.2**  
&ensp;Supportphase: **Support für technische Upgrades (nur)**
     
### <a name="whats-new"></a>Neuerungen

  
### <a name="known-issues"></a>Bekannte Probleme
Keine bekannten Probleme
<br/>
</details>

<details>
<summary> Januar-2020 (Plattform: 4.18.2001.10 | Modul: 1.1.16700.2)</summary>
  

Version des Security Intelligence-Updates: **1.309.32.0**  
Veröffentlicht: **30. Januar 2020**  
Plattform/Client: **4.18.2001.10**  
Modul: **1.1.16700.2**  
&ensp;Supportphase: **Support für technische Upgrades (nur)**
     
### <a name="whats-new"></a>Neuerungen

- BSOD auf WS2016 mit Exchange
- Unterstützen von Plattformupdates, wenn TMP zum Netzwerkpfad umgeleitet wird
- Plattform- und Modulversionen werden [WDSI hinzugefügt](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- Erweitern des Notfallsignaturupdates auf [den passiven Modus](./microsoft-defender-antivirus-compatibility.md)
- Fix 4.18.1911.3 hang
   
### <a name="known-issues"></a>Bekannte Probleme

[**Fixed**] Geräte, [die](/windows-hardware/design/device-experiences/modern-standby) den modernen Standbymodus verwenden, können mit dem Windows Defender-Filtertreibers hängen, was zu einer Schutzlücke führt.  Betroffene Computer scheinen dem Kunden nicht auf die neueste Antischalwareplattform aktualisiert zu sein.  
<br/>
> [!IMPORTANT]
> Dieses Update ist:
> - wird von RS1-Geräten mit niedrigerer Version der Plattform benötigt, um SHA2 zu unterstützen;
> - verfügt über ein Neustart-Flag für Systeme mit hängenden Problemen.
> - wird im April 2020 erneut veröffentlicht und wird nicht durch neuere Updates ersetzt, um die zukünftige Verfügbarkeit zu gewährleisten.  
> - wird aufgrund der Neustartanforderung als Update kategorisiert; und
> - wird nur mit dem [update Windows angeboten.](https://support.microsoft.com/help/4027667/windows-10-update)
<br/>
</details>

<details>
<summary> November-2019 (Plattform: 4.18.1911.3 | Modul: 1.1.16600.7)</summary>

Version des Security Intelligence-Updates: **1.307.13.0**  
Veröffentlicht: **7. Dezember 2019**  
Plattform: **4.18.1911.3**  
Modul: **1.1.17000.7**  
Supportphase: **Keine Unterstützung**  
     
### <a name="whats-new"></a>Neuerungen

- Feste MpCmdRun-Ablaufverfolgungsstufe
- Informationen zur WDFilter-Version behoben
- Verbessern von Benachrichtigungen (PUA)
- Hinzufügen von MRT-Protokollen zur Unterstützung von Dateien
   
### <a name="known-issues"></a>Bekannte Probleme
Wenn dieses Update installiert ist, benötigt das Gerät das Sprungpaket 4.10.2001.10, um auf die neueste Plattformversion aktualisieren zu können.
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Microsoft Defender Antivirus Plattformunterstützung
Plattform- und Modulupdates werden monatlich bereitgestellt. Um vollständig unterstützt zu werden, halten Sie die neuesten Plattformupdates auf dem neuesten Stand. Unsere Supportstruktur ist dynamisch und entwickelt sich je nach Verfügbarkeit der neuesten Plattformversion in zwei Phasen:

- **Wartungsphase** für Sicherheits- und kritische Updates– Wenn Sie die neueste Plattformversion ausführen, sind Sie berechtigt, sowohl Sicherheitsupdates als auch kritische Updates für die Anti-Malware-Plattform zu erhalten.
 
- **Phase des technischen Support (nur)** – Nachdem eine neue Plattformversion veröffentlicht wurde, wird die Unterstützung für ältere Versionen (N-2) auf nur noch technischen Support reduziert. Plattformversionen, die älter als N-2 sind, werden nicht mehr unterstützt.*

\*Der technische Support wird weiterhin für Upgrades von der Windows 10-Version (siehe Plattformversion, die in [Windows 10](#platform-version-included-with-windows-10-releases)Versionen enthalten ist) auf die neueste Plattformversion bereitgestellt.

Während der Phase des technischen Support (nur) werden kommerziell angemessene Supportvorfälle über den Microsoft Customer Service & Support und die von Microsoft verwalteten Supportangebote (z. B. Premier Support) bereitgestellt. Wenn für einen Supportvorfall eine Eskalation zur Entwicklung erforderlich ist, ein nicht sicherheitsunsicherheitsupdate erforderlich ist oder ein Sicherheitsupdate erforderlich ist, werden Kunden aufgefordert, ein Upgrade auf die neueste Plattformversion oder ein Zwischenupdate (*) zu durchführen.

### <a name="platform-version-included-with-windows-10-releases"></a>Plattformversion, die in Windows 10 enthalten ist
Die folgende Tabelle enthält die Microsoft Defender Antivirus Plattform- und Modulversionen, die mit den neuesten Versionen der Windows 10 ausgeliefert werden:    

|Windows 10 Release  |Plattformversion  |Modulversion |Supportphase |
|:---|:---|:---|:---|
|2004 (20H1/20H2) |4.18.1909.6 |1.1.17000.2 | Support für technische Upgrades (nur) |
|1909 (19H2) |4.18.1902.5 |1.1.16700.3 | Support für technische Upgrades (nur) |
|1903 (19H1) |4.18.1902.5 |1.1.15600.4 | Support für technische Upgrades (nur) |
|1809 (RS5) |4.18.1807.18075 |1.1.15000.2 | Support für technische Upgrades (nur) |
|1803 (RS4) |4.13.17134.1 |1.1.14600.4 | Support für technische Upgrades (nur) |
|1709 (RS3) |4.12.16299.15 |1.1.14104.0 | Support für technische Upgrades (nur) |
|1703 (RS2) |4.11.15603.2 |1.1.13504.0 | Support für technische Upgrades (nur) |
|1607 (RS1) |4.10.14393.3683 |1.1.12805.0 | Support für technische Upgrades (nur) |  

Informationen Windows 10 Veröffentlichung finden Sie im [Windows-Lifecycle-Factsheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>Updates für die Bereitstellungsimagewartung und -verwaltung (DISM)

Es wird empfohlen, ihre Windows 10 (Enterprise-, Pro- und Home-Editionen), Windows Server 2019 und Windows Server 2016 Betriebssysteminstallationsabbilder mit den neuesten Antiviren- und Antischalwareupdates zu aktualisieren. Wenn Sie Ihre Betriebssysteminstallationsabbilder auf dem neuesten Stand halten, können Sie eine Lücke beim Schutz vermeiden. 

Weitere Informationen finden Sie unter [Microsoft Defender update for Windows installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).

<details>
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
- Unterstützung für Windows 10 RS1 oder höher hinzugefügt.  
<br/>
</details>

## <a name="additional-resources"></a>Zusätzliche Ressourcen

| Artikel | Beschreibung  |
|:---|:---|
|[Microsoft Defender Update für Windows Betriebssysteminstallationsabbilder](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | Überprüfen Sie Antischadwareupdatepakete für Ihre Betriebssysteminstallationsabbilder (WIM- und VHD-Dateien). Erhalten Microsoft Defender Antivirus Updates für Windows 10 (Enterprise, Pro und Home-Editionen), Windows Server 2019 und Windows Server 2016 Installationsabbilder.  |
|[Verwalten, wie Schutzupdates heruntergeladen und angewendet werden](manage-protection-updates-microsoft-defender-antivirus.md) | Schutzupdates können über viele Quellen zugestellt werden. |
|[Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen](manage-protection-update-schedule-microsoft-defender-antivirus.md) | Sie können planen, wann Schutzupdates heruntergeladen werden sollen. |
|[Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md) | Wenn ein Endpunkt ein Update oder einen geplanten Scan verpasst, können Sie ein Update erzwingen oder bei der nächsten Benutzeran meldet. |
|[Verwalten von ereignisbasierten erzwungenen Updates](manage-event-based-updates-microsoft-defender-antivirus.md) | Sie können festlegen, dass Schutzupdates beim Start oder nach bestimmten in der Cloud übermittelten Schutzereignissen heruntergeladen werden. |
|[Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| Sie können Einstellungen angeben, z. B. ob Updates für die Akkuleistung erfolgen sollen, die besonders für mobile Geräte und virtuelle Computer nützlich sind. |
