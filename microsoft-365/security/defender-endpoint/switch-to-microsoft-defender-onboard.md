---
title: Wechseln zu Microsoft Defender for Endpoint – Onboard
description: Dies ist Phase 3, Onboard, für die Migration von einer Nicht-Microsoft-Lösung zu Microsoft Defender for Endpoint.
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
- m365solution-migratetomdatp
ms.custom: migrationguides
ms.topic: article
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 0ba6f3da326223dcefb1c29f91c5a631ec8a866c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539167"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Wechseln zu Microsoft Defender for Endpoint – Phase 3: Onboard

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Phase 1: Prepare3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Phase 1: Vorbereiten](switch-to-microsoft-defender-prepare.md) | [![Phase 2: Einrichten](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Phase 2: Einrichten](switch-to-microsoft-defender-setup.md) | ![Phase 3: Onboarding](images/phase-diagrams/onboard.png)<br/>Phase 3: Onboarding |
|--|--|--|
|| |*Sie sind hier!* |


**Willkommen bei Phase 3 des [Wechsels zu Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)**. Diese Migrationsphase umfasst die folgenden Schritte:

1. [Onboarding von Geräten in Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).

2. [Führen Sie einen Erkennungstest aus.](#run-a-detection-test)

3. [Bestätigen Sie, Microsoft Defender Antivirus sich auf Ihren Endpunkten im passiven Modus befindet.](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints)

4. [Updates für Microsoft Defender Antivirus](#get-updates-for-microsoft-defender-antivirus).

5. [Deinstallieren Sie Ihre Nicht-Microsoft-Lösung.](#uninstall-your-non-microsoft-solution) 

6. [Stellen Sie sicher, dass Defender for Endpoint ordnungsgemäß funktioniert.](#make-sure-defender-for-endpoint-is-working-correctly)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Geräte in Microsoft Defender für Endpunkt onboarden

1. Wechseln Sie zum Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) und melden Sie sich an.

2. Wählen **Einstellungen**  >  **Geräteverwaltung**  >  **Onboarding aus.** 

3. Wählen Sie **in der Liste Betriebssystem zum Starten des Onboardingprozesses** auswählen ein Betriebssystem aus. 

4. Wählen **Sie unter Bereitstellungsmethode** eine Option aus. Folgen Sie den Links und Aufforderungen zum Onboarding der Geräte Ihrer Organisation. Benötigen Sie Hilfe? Weitere [Informationen finden Sie unter Onboarding-Methoden](#onboarding-methods) (in diesem Artikel).

### <a name="onboarding-methods"></a>Onboardingmethoden
 
Die Bereitstellungsmethoden variieren je nach Betriebssystem und bevorzugten Methoden. In der folgenden Tabelle sind Ressourcen aufgeführt, die Ihnen beim Onboarding bei Defender for Endpoint helfen:

|Betriebssysteme  |Methoden  |
|---------|---------|
| Windows 10     | [Gruppenrichtlinie](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[Verwaltung mobiler Geräte (Intune)](configure-endpoints-mdm.md)<p>[Lokales Skript](configure-endpoints-script.md) <p>**HINWEIS:** Ein lokales Skript eignet sich für einen Nachweis des Konzepts, sollte jedoch nicht für die Produktionsbereitstellung verwendet werden. Für eine Produktionsbereitstellung wird die Verwendung von Gruppenrichtlinien, Microsoft Endpoint Configuration Manager oder Intune empfohlen.         |
| Windows 8.1 Enterprise <p>Windows 8.1 Pro <p>Windows 7 SP1-Enterprise <p>Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<p>**HINWEIS:** Microsoft Monitoring Agent ist jetzt Azure Log Analytics Agent. Weitere Informationen finden Sie unter [Log Analytics Agent Overview](/azure/azure-monitor/platform/log-analytics-agent).        |
| Windows Server 2019 und höher <p>Windows Server 2019 Core Edition <p>Windows Serverversion 1803 und höher | [Lokales Skript](configure-endpoints-script.md) <p>[Gruppenrichtlinie](configure-endpoints-gp.md) <p>[Configuration Manager](configure-endpoints-sccm.md) <p>[System Center Configuration Manager](configure-endpoints-sccm.md) <p>[VDI-Onboardingskripts für nicht persistente Geräte](configure-endpoints-vdi.md) <p>**HINWEIS:** Ein lokales Skript eignet sich für einen Nachweis des Konzepts, sollte jedoch nicht für die Produktionsbereitstellung verwendet werden. Für eine Produktionsbereitstellung wird die Verwendung von Gruppenrichtlinien, Microsoft Endpoint Configuration Manager oder Intune empfohlen.    |
| Windows Server 2016 <p>Windows Server 2012 R2 <p>Windows Server 2008 R2 SP1  | [Microsoft Defender Security Center](configure-server-endpoints.md)<p>[Azure Defender](/azure/security-center/security-center-wdatp) |
|macOS:<p>11.3.1 (Big Sur) <p>10.15 (Catalina)<p>10.14 (Mojave)|[Onboarding von Nicht-Windows-Geräten](configure-endpoints-non-windows.md)  |
|iOS |[Onboarding von Nicht-Windows-Geräten](configure-endpoints-non-windows.md)  |
|Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS oder höher LTS<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |[Onboarding von Nicht-Windows-Geräten](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Ausführen eines Erkennungstests

Um sicherzustellen, dass Ihre integrierten Geräte ordnungsgemäß mit Defender for Endpoint verbunden sind, können Sie einen Erkennungstest ausführen.

|Betriebssystem  |Richtlinien  |
|---------|---------|
| Windows 10 <p>Windows Server 2019 <p>Windows Server, Version 1803 <p>Windows Server 2016 <p>Windows Server 2012 R2     | Weitere [Informationen finden Sie unter Ausführen eines Erkennungstests.](run-detection-test.md) <p>Besuchen Sie die Defender for Endpoint-Demoszenarien-Website ( ) und testen Sie eines [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) oder mehrere der Szenarien. Testen Sie beispielsweise das **Demoszenario für den Cloud-zugestellten** Schutz.         |
| macOS:<p>11.3.1 (Big Sur) <p>10.15 (Catalina)<p>10.14 (Mojave)    |Laden Sie die HEIMWERKER-App unter herunter und verwenden Sie [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) sie. <p>Weitere Informationen finden Sie unter [Defender for Endpoint unter macOS](microsoft-defender-endpoint-mac.md).        |
| Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS oder höher LTS<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |1. Führen Sie den folgenden Befehl aus, und suchen Sie nach einem Ergebnis von **1:** <br/>`mdatp health --field real_time_protection_enabled`. <p>2. Öffnen Sie ein Terminalfenster, und führen Sie den folgenden Befehl aus: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. Führen Sie den folgenden Befehl aus, um erkannte Bedrohungen auflisten: <br/>`mdatp threat list`. <p>Weitere Informationen finden Sie unter [Defender for Endpoint unter Linux](microsoft-defender-endpoint-linux.md). |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>Bestätigen, Microsoft Defender Antivirus sich auf Ihren Endpunkten im passiven Modus befindet

Nachdem Ihre Endpunkte nun in Defender for Endpoint onboarded wurden, müssen Sie im nächsten Schritt sicherstellen, dass Microsoft Defender Antivirus im passiven Modus ausgeführt wird. Sie können entweder die Eingabeaufforderung oder PowerShell verwenden, um diese Aufgabe auszuführen, wie in der folgenden Tabelle beschrieben:

|Methode  |Vorgehensweise  |
|---------|---------|
|Eingabeaufforderung     | 1. Öffnen Sie auf Windows Gerät die Eingabeaufforderung als Administrator.<p>2. Geben Sie `sc query windefend` ein , und drücken Sie dann die EINGABETASTE.<p>3. Überprüfen Sie die Ergebnisse, um zu bestätigen, Microsoft Defender Antivirus im passiven Modus ausgeführt wird.         |
|PowerShell     | 1. Öffnen Sie auf Windows Gerät Windows PowerShell Administrator.<p>2. Führen Sie das [Cmdlet Get-MpComputerStatus](/powershell/module/defender/Get-MpComputerStatus) aus. <p>3. Suchen Sie in der Liste der Ergebnisse nach **AMRunningMode: Passive Mode** oder **AMRunningMode: SxS Passive Mode**.          |

> [!NOTE]
> In einigen *Versionen von* Windows Defender Antivirus *Microsoft Defender Antivirus* möglicherweise Windows.

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>Manuelles Microsoft Defender Antivirus auf Windows Server in den passiven Modus festlegen

Führen Sie die folgenden Schritte aus, um Microsoft Defender Antivirus den passiven Modus auf Windows Server, Version 1803 oder neuer oder Windows Server 2019, zu setzen:

1. Öffnen Sie den Registrierungs-Editor, und navigieren Sie dann zu <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Bearbeiten (oder erstellen) Sie einen DWORD-Eintrag namens **ForcePassiveMode,** und geben Sie die folgenden Einstellungen an:
   - Legen Sie den Wert des DWORD auf **1 .**
   - Wählen **Sie unter Basis** die Option **Hexadezimal aus.**

> [!NOTE]
> Sie können andere Methoden zum Festlegen des Registrierungsschlüssels verwenden, z. B.:
>- [Gruppenrichtlinieneinstellung](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Objekttool für lokale Gruppenrichtlinien](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Ein Paket im Configuration Manager](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Starten Microsoft Defender Antivirus auf Windows Server 2016

Wenn Sie eine Windows Server 2016, müssen Sie möglicherweise manuell Microsoft Defender Antivirus starten. Dazu verwenden Sie das PowerShell-Cmdlet `mpcmdrun.exe -wdenable` auf dem Gerät.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Updates für Microsoft Defender Antivirus

Die Microsoft Defender Antivirus ist wichtig, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind, auch wenn Microsoft Defender Antivirus im passiven Modus [ausgeführt wird.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Es gibt zwei Arten von Updates, die Microsoft Defender Antivirus aktualisiert werden:
- Sicherheitsintelligenzupdates
- Produktupdates

Um Ihre Updates zu erhalten, folgen Sie den Anweisungen unter [Manage Microsoft Defender Antivirus updates and apply baselines](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).

## <a name="uninstall-your-non-microsoft-solution"></a>Deinstallieren Ihrer Nicht-Microsoft-Lösung

Nachdem Sie die Geräte Ihrer Organisation in Defender for Endpoint integrierte haben und Microsoft Defender Antivirus installiert und aktiviert ist, besteht der nächste Schritt in der Deinstallation Ihrer Nicht-Microsoft-Endpunktschutzlösung. Um Hilfe bei dieser Aufgabe zu erhalten, erreichen Sie das technische Supportteam Ihres Lösungsanbieters.

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>Sicherstellen, dass Defender for Endpoint ordnungsgemäß funktioniert

Nachdem Sie nun ein Onboarding für Defender for Endpoint ausgeführt haben und Ihre frühere Nicht-Microsoft-Lösung deinstalliert haben, müssen Sie als nächstes sicherstellen, dass Defender for Endpoint ordnungsgemäß funktioniert. Eine gute Möglichkeit dazu ist der Besuch der Defender for Endpoint-Demoszenarien-Website ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Testen Sie mindestens eines der Demoszenarien auf dieser Seite, einschließlich mindestens der folgenden:
- Aus der Cloud gelieferter Schutz
- Potenziell unerwünschte Anwendungen (PUA)
- Network Protection (NP)

## <a name="next-steps"></a>Nächste Schritte

**Herzlichen Glückwunsch!** Sie haben die Migration [zu Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)abgeschlossen! 

- [Besuchen Sie Ihr Sicherheitsbetriebsdashboard](security-operations-dashboard.md) im Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

- [Verwalten von Defender for Endpoint, post migration](manage-atp-post-migration.md).
