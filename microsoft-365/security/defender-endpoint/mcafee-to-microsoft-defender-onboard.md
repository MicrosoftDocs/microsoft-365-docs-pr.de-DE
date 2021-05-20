---
title: McAfee zu Microsoft Defender for Endpoint – Onboard
description: Dies ist Phase 3, Onboard, für die Migration von McAfee zu Microsoft Defender for Endpoint.
keywords: migration, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-McAfeemigrate
- m365solution-scenario
ms.custom: migrationguides
ms.topic: article
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 8a9d1ea36ae0778892768e3b39f4ffbed2a8d732
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538027"
---
# <a name="migrate-from-mcafee---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Migrieren von McAfee – Phase 3: Onboarding zu Microsoft Defender for Endpoint

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


|[![Phase 1: Vorbereiten](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)<br/>[Phase 1: Vorbereiten](mcafee-to-microsoft-defender-prepare.md) |[![Phase 2: Einrichten](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[Phase 2: Einrichten](mcafee-to-microsoft-defender-setup.md) |![Phase 3: Onboarding](images/phase-diagrams/onboard.png)<br/>Phase 3: Onboarding |
|--|--|--|
|| |*Sie sind hier!* |

**Willkommen bei Phase 3 der [Migration von McAfee Endpoint Security (McAfee) zu Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)**. Diese Migrationsphase umfasst die folgenden Schritte:

1. [Onboarding von Geräten in Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).

2. [Führen Sie einen Erkennungstest aus.](#run-a-detection-test)

3. [Bestätigen Sie, Microsoft Defender Antivirus sich im passiven Modus befindet.](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode)

4. [Updates für Microsoft Defender Antivirus](#get-updates-for-microsoft-defender-antivirus).

5. [Deinstallieren Von McAfee](#uninstall-mcafee).

6. [Stellen Sie sicher, dass Defender for Endpoint ordnungsgemäß funktioniert.](#make-sure-defender-for-endpoint-is-working-correctly)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Geräte in Microsoft Defender für Endpunkt onboarden

1. Wechseln Sie zum Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) und melden Sie sich an.

2. Wählen **Einstellungen**  >  **Geräteverwaltung**  >  **Onboarding aus.** 

3. Wählen Sie **in der Liste Betriebssystem zum Starten des Onboardingprozesses** auswählen ein Betriebssystem aus. 

4. Wählen **Sie unter Bereitstellungsmethode** eine Option aus. Folgen Sie den Links und Aufforderungen zum Onboarding der Geräte Ihrer Organisation. Benötigen Sie Hilfe? Weitere [Informationen finden Sie unter Onboarding-Methoden](#onboarding-methods) (in diesem Artikel).

### <a name="onboarding-methods"></a>Onboardingmethoden
 
Die Bereitstellungsmethoden variieren, je nachdem, welches Betriebssystem ausgewählt ist. Weitere Informationen zum Onboarding finden Sie in den ressourcen, die in der folgenden Tabelle aufgeführt sind.

| Betriebssystem  |Methode  |
|---------|---------|
| Windows 10     | [Gruppenrichtlinie](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[Verwaltung mobiler Geräte (Intune)](configure-endpoints-mdm.md)<p>[Lokales Skript](configure-endpoints-script.md) <br/>**HINWEIS:** Ein lokales Skript eignet sich für einen Nachweis des Konzepts, sollte jedoch nicht für die Produktionsbereitstellung verwendet werden. Für eine Produktionsbereitstellung wird die Verwendung von Gruppenrichtlinien, Microsoft Endpoint Configuration Manager oder Intune empfohlen.         |
| Windows 8.1 Enterprise <p>Windows 8.1 Pro <p>Windows 7 SP1-Enterprise<p>Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<br/>**HINWEIS:** Microsoft Monitoring Agent ist jetzt Azure Log Analytics Agent. Weitere Informationen finden Sie unter [Log Analytics Agent Overview](/azure/azure-monitor/platform/log-analytics-agent).        |
| Windows Server 2019 und höher<p>Windows Server 2019 Core Edition<p>Windows Serverversion 1803 und höher | [Lokales Skript](configure-endpoints-script.md)<p>[Gruppenrichtlinie](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[System Center Configuration Manager](configure-endpoints-sccm.md)<p>[VDI-Onboardingskripts für nicht persistente Geräte](configure-endpoints-vdi.md) <br/>**HINWEIS:** Ein lokales Skript eignet sich für einen Nachweis des Konzepts, sollte jedoch nicht für die Produktionsbereitstellung verwendet werden. Für eine Produktionsbereitstellung wird die Verwendung von Gruppenrichtlinien, Microsoft Endpoint Configuration Manager oder Intune empfohlen.    |
| Windows Server 2016 <p>Windows Server 2012 R2<p>Windows Server 2008 R2 SP1  | [Microsoft Defender Security Center](configure-server-endpoints.md)<p>[Azure Defender](/azure/security-center/security-center-wdatp) |
|macOS:<p>11.3.1 (Big Sur)<p>10.15 (Catalina)<p>10.14 (Mojave) |[Onboarding von Nicht-Windows-Geräten](configure-endpoints-non-windows.md)  |
|iOS |[Onboarding von Nicht-Windows-Geräten](configure-endpoints-non-windows.md)  |
|Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS oder höher LTS<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |[Onboarding von Nicht-Windows-Geräten](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Ausführen eines Erkennungstests

Um sicherzustellen, dass Ihre integrierten Geräte ordnungsgemäß mit Microsoft Defender for Endpoint verbunden sind, können Sie einen Erkennungstest ausführen.

|Betriebssystem  |Richtlinien  |
|---------|---------|
| Windows 10<p>Windows Server 2019 <p>Windows Server, Version 1803 <p>Windows Server 2016 <p>Windows Server 2012 R2     |Weitere [Informationen finden Sie unter Ausführen eines Erkennungstests.](run-detection-test.md) <p>Besuchen Sie die Microsoft Defender for Endpoint-Demoszenarien-Website ( ) und testen Sie eines [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) oder mehrere der Szenarien. Testen Sie beispielsweise das **Demoszenario für den Cloud-zugestellten** Schutz.         |
|macOS<p>11.3.1 (Big Sur)<p>10.15 (Catalina)<p>10.14 (Mojave)     |Laden Sie die HEIMWERKER-App unter herunter und verwenden Sie [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) sie. <p>Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint auf Mac](microsoft-defender-endpoint-mac.md).        |
|Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS oder höher LTS<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |1. Führen Sie den folgenden Befehl aus, und suchen Sie nach einem Ergebnis von **1:** <br/>`mdatp health --field real_time_protection_enabled`. <p>2. Öffnen Sie ein Terminalfenster, und führen Sie den folgenden Befehl aus: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. Führen Sie den folgenden Befehl aus, um erkannte Bedrohungen auflisten: <br/>`mdatp threat list`. <p>Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint unter Linux](microsoft-defender-endpoint-linux.md). |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Bestätigen, Microsoft Defender Antivirus sich im passiven Modus befindet

Nachdem Ihre Endpunkte nun in Defender for Endpoint onboarded wurden, müssen Sie im nächsten Schritt sicherstellen, dass Microsoft Defender Antivirus im passiven Modus ausgeführt wird. Sie können entweder die Eingabeaufforderung oder PowerShell verwenden, um diese Aufgabe auszuführen, wie in der folgenden Tabelle beschrieben:

|Methode  |Vorgehensweise  |
|---------|---------|
|Eingabeaufforderung     |1. Öffnen Sie auf Windows Gerät die Eingabeaufforderung als Administrator.<p> 2. Geben Sie `sc query windefend` ein , und drücken Sie dann die EINGABETASTE.<p> 3. Überprüfen Sie die Ergebnisse, um zu bestätigen, Microsoft Defender Antivirus im passiven Modus ausgeführt wird.         |
|PowerShell     |1. Öffnen Sie auf Windows Gerät Windows PowerShell Administrator.<p> 2. Führen Sie das [Cmdlet Get-MpComputerStatus](/powershell/module/defender/Get-MpComputerStatus) aus. <p> 3. Suchen Sie in der Liste der Ergebnisse nach **AMRunningMode: Passive Mode** oder **AMRunningMode: SxS Passive Mode**.|

> [!NOTE]
> In einigen *Versionen von* Windows Defender Antivirus *Microsoft Defender Antivirus* möglicherweise Windows.

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>Manuelles Microsoft Defender Antivirus auf Windows Server in den passiven Modus festlegen

Führen Sie die folgenden Schritte aus, um Microsoft Defender Antivirus den passiven Modus auf Windows Server, Version 1803 oder neuer oder Windows Server 2019, zu setzen:

1. Öffnen Sie den Registrierungs-Editor, und navigieren Sie dann zu `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` .

2. Bearbeiten (oder erstellen) Sie einen DWORD-Eintrag namens **ForcePassiveMode,** und geben Sie die folgenden Einstellungen an:

   - Legen Sie den Wert des DWORD auf `1` .
   - Wählen **Sie unter Basis** die Option **Hexadezimal aus.**
 
   > [!NOTE]
   > Sie können andere Methoden zum Festlegen des Registrierungsschlüssels verwenden, z. B.:
   > - Gruppenrichtlinieneinstellung
   > - Objekttool für lokale Gruppenrichtlinien
   > - Ein Paket im Configuration Manager

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Starten Microsoft Defender Antivirus auf Windows Server 2016

Wenn Sie eine Windows Server 2016, müssen Sie möglicherweise manuell Microsoft Defender Antivirus starten. Dazu verwenden Sie das PowerShell-Cmdlet `mpcmdrun.exe -wdenable` auf dem Gerät.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Updates für Microsoft Defender Antivirus

Die Microsoft Defender Antivirus ist wichtig, um sicherzustellen, dass Ihre Geräte über die neueste Technologie und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind, auch wenn Microsoft Defender Antivirus im passiven Modus ausgeführt wird.

Es gibt zwei Arten von Updates, die Microsoft Defender Antivirus aktualisiert werden:
- Sicherheitsintelligenzupdates
- Produktupdates

Um Ihre Updates zu erhalten, folgen Sie den Anweisungen unter [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).


## <a name="uninstall-mcafee"></a>Deinstallieren von McAfee

Nachdem Sie die Geräte Ihrer Organisation in Microsoft Defender for Endpoint integrierte haben, besteht der nächste Schritt in der Deinstallation von McAfee. Um Hilfe zu diesem Schritt zu erhalten, wechseln Sie zu Ihrem McAfee ServicePortal ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) ).

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>Sicherstellen, dass Defender for Endpoint ordnungsgemäß funktioniert

Nachdem Sie McAfee deinstalliert haben, müssen Sie im nächsten Schritt sicherstellen, dass Microsoft Defender Antivirus und EDR aktiviert sind und im aktiven Modus sind.

Besuchen Sie dazu die Microsoft Defender for Endpoint-Demoszenarien-Website ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Testen Sie mindestens eines der Demoszenarien auf dieser Seite, einschließlich mindestens der folgenden:
- Aus der Cloud gelieferter Schutz
- Potenziell unerwünschte Anwendungen (PUA)
- Network Protection (NP)

> [!IMPORTANT]
> Wenn Sie eine Windows Server 2016, müssen Sie möglicherweise manuell Microsoft Defender Antivirus starten. Dazu verwenden Sie das PowerShell-Cmdlet `mpcmdrun.exe -wdenable` auf dem Gerät.

## <a name="next-steps"></a>Nächste Schritte

**Herzlichen Glückwunsch!** Sie haben die Migration [von McAfee zu Microsoft Defender for Endpoint abgeschlossen!](mcafee-to-microsoft-defender-migration.md#the-migration-process) 

- [Besuchen Sie Ihr Sicherheitsbetriebsdashboard](security-operations-dashboard.md) im Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Verwalten von Microsoft Defender for Endpoint, post migration](manage-atp-post-migration.md).
