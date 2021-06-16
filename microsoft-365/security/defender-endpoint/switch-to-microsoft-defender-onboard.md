---
title: Wechseln zu Microsoft Defender für Endpunkt – Onboarding
description: Dies ist Phase 3, Onboarding, für die Migration von einer nicht von Microsoft stammenden Lösung zu Microsoft Defender für Endpunkt.
keywords: Migration, Microsoft Defender für Endpunkt, edr
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
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.custom: migrationguides
ms.topic: article
ms.date: 06/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 832414e9b2a88114cafafbba78e22ea656cc7949
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930463"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Wechseln zu Microsoft Defender für Endpunkt – Phase 3: Onboarding

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Phase 1: Vorbereiten3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Phase 1: Vorbereiten](switch-to-microsoft-defender-prepare.md) | [![Phase 2: Einrichten](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Phase 2: Einrichten](switch-to-microsoft-defender-setup.md) | ![Phase 3: Onboarding](images/phase-diagrams/onboard.png)<br/>Phase 3: Onboarding |
|--|--|--|
|| |*Sie sind hier!* |


**Willkommen bei Phase 3 des [Wechsels zu Defender für Endpunkt.](switch-to-microsoft-defender-migration.md#the-migration-process)** Diese Migrationsphase umfasst die folgenden Schritte:

1. [Onboarding von Geräten in Defender für Endpunkt](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Führen Sie einen Erkennungstest](#run-a-detection-test)aus.
3. [Vergewissern Sie sich, dass sich Microsoft Defender Antivirus auf Ihren Endpunkten im passiven Modus befindet.](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints)
4. [Updates für Microsoft Defender Antivirus](#get-updates-for-microsoft-defender-antivirus)abrufen.
5. [Deinstallieren Sie Ihre Nicht-Microsoft-Lösung.](#uninstall-your-non-microsoft-solution) 
6. [Stellen Sie sicher, dass Defender für Endpunkt ordnungsgemäß funktioniert.](#make-sure-defender-for-endpoint-is-working-correctly)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Geräte in Microsoft Defender für Endpunkt onboarden

1. Wechseln Sie zum Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ), und melden Sie sich an.

2. Wählen Sie **Einstellungen**  >  **Geräteverwaltungs-Onboarding**  >  **aus.** 

3. Wählen Sie in der Liste "Betriebssystem auswählen" ein Betriebssystem aus, um mit dem **Onboarding zu beginnen.** 

4. Wählen Sie unter **"Bereitstellungsmethode"** eine Option aus. Folgen Sie den Links und Aufforderungen zum Onboarding der Geräte Ihrer Organisation. Benötigen Sie Hilfe? Siehe [Onboarding-Methoden](#onboarding-methods) (in diesem Artikel).

### <a name="onboarding-methods"></a>Onboarding-Methoden
 
Bereitstellungsmethoden variieren je nach Betriebssystem und bevorzugten Methoden. In der folgenden Tabelle sind Ressourcen aufgeführt, die Ihnen beim Onboarding in Defender für Endpunkt helfen:

|Betriebssysteme  |Methoden  |
|---------|---------|
| Windows 10     | [Gruppenrichtlinie](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[Verwaltung mobiler Geräte (Intune)](configure-endpoints-mdm.md)<p>[Lokales Skript](configure-endpoints-script.md) <p>**HINWEIS:** Ein lokales Skript eignet sich für einen Machbarkeitsstudie, sollte jedoch nicht für die Produktionsbereitstellung verwendet werden. Für eine Produktionsbereitstellung empfehlen wir die Verwendung von Gruppenrichtlinien, Microsoft Endpoint Configuration Manager oder Intune.         |
| Windows 8.1 Enterprise <p>Windows 8.1 Pro <p>Windows 7 SP1-Enterprise <p>Windows 7 SP1-Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<p>**HINWEIS:** Microsoft Monitoring Agent ist jetzt Azure Log Analytics-Agent. Weitere Informationen finden Sie in der [Übersicht über den Log Analytics-Agent.](/azure/azure-monitor/platform/log-analytics-agent)        |
| Windows Server 2019 und höher <p>Windows Server 2019 Core Edition <p>Windows Serverversion 1803 und höher | [Lokales Skript](configure-endpoints-script.md) <p>[Gruppenrichtlinie](configure-endpoints-gp.md) <p>[Configuration Manager](configure-endpoints-sccm.md) <p>[System Center Configuration Manager](configure-endpoints-sccm.md) <p>[VDI-Integrationsskripts für nicht persistente Geräte](configure-endpoints-vdi.md) <p>**HINWEIS:** Ein lokales Skript eignet sich für einen Machbarkeitsstudie, sollte jedoch nicht für die Produktionsbereitstellung verwendet werden. Für eine Produktionsbereitstellung empfehlen wir die Verwendung von Gruppenrichtlinien, Microsoft Endpoint Configuration Manager oder Intune.    |
| Windows Server 2016 <p>Windows Server 2012 R2 <p>Windows Server 2008 R2 SP1  | [Microsoft Defender Security Center](configure-server-endpoints.md)<p>[Azure Defender](/azure/security-center/security-center-wdatp) |
| Macos:<p>11.3.1 (Big Sur) <p>10.15 (Git)<p>10.14 (Mojave) | [Onboarding von Nicht-Windows-Geräten](configure-endpoints-non-windows.md)  |
| iOS | [Onboarding von Nicht-Windows-Geräten](configure-endpoints-non-windows.md)  |
| Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS oder höher LTS<p>SLES ab 12 Jahren<p>Ubuntu 9+<p>Oracle Linux 7.2 | [Onboarding von Nicht-Windows-Geräten](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Ausführen eines Erkennungstests

Um zu überprüfen, ob Ihre integrierten Geräte ordnungsgemäß mit Defender für Endpunkt verbunden sind, können Sie einen Erkennungstest ausführen.

|Betriebssystem  |Richtlinien  |
|---------|---------|
| Windows 10 <p>Windows Server 2019 <p>Windows Server, Version 1803 <p>Windows Server 2016 <p>Windows Server 2012 R2     | Siehe ["Ausführen eines Erkennungstests".](run-detection-test.md) <p>Besuchen Sie die Demoszenariowebsite () von Defender für Endpunkt, [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) und testen Sie eines oder mehrere der Szenarien. Testen Sie beispielsweise das Demoszenario für den über die **Cloud bereitgestellten Schutz.**    |
| Macos:<p>11.3.1 (Big Sur) <p>10.15 (Git)<p>10.14 (Mojave)    | Laden Sie die DANN-App herunter, und verwenden Sie sie unter [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <p>Weitere Informationen finden Sie unter [Defender für Endpunkt unter macOS.](microsoft-defender-endpoint-mac.md)        |
| Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS oder höher LTS<p>SLES ab 12 Jahren<p>Ubuntu 9+<p>Oracle Linux 7.2 | 1. Führen Sie den folgenden Befehl aus, und suchen Sie nach einem Ergebnis von **1:** <br/>`mdatp health --field real_time_protection_enabled`. <p>2. Öffnen Sie ein Terminalfenster, und führen Sie den folgenden Befehl aus: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. Führen Sie den folgenden Befehl aus, um erkannte Bedrohungen aufzuführen: <br/>`mdatp threat list`. <p>Weitere Informationen finden Sie unter [Defender für Endpunkt unter Linux.](microsoft-defender-endpoint-linux.md) |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>Vergewissern Sie sich, dass sich Microsoft Defender Antivirus auf Ihren Endpunkten im passiven Modus befindet

Nachdem Ihre Endpunkte nun in Defender für Endpunkt integriert wurden, müssen Sie im nächsten Schritt sicherstellen, dass Microsoft Defender Antivirus im passiven Modus ausgeführt wird. Sie können zum Ausführen dieser Aufgabe entweder eine Eingabeaufforderung oder PowerShell verwenden, wie in der folgenden Tabelle beschrieben:

| Methode  | Vorgehensweise  |
|:-------|:-------|
|Eingabeaufforderung     | 1. Öffnen Sie auf einem Windows Gerät die Eingabeaufforderung als Administrator.<p>2. Geben Sie `sc query windefend` ein, und drücken Sie dann die EINGABETASTE.<p>3. Überprüfen Sie die Ergebnisse, um zu bestätigen, dass Microsoft Defender Antivirus im passiven Modus ausgeführt wird.         |
| PowerShell     | 1. Öffnen Sie auf einem Windows Gerät Windows PowerShell als Administrator.<p>2. Führen Sie das Cmdlet ["Get-MpComputerStatus" aus.](/powershell/module/defender/Get-MpComputerStatus) <p>3. Suchen Sie in der Ergebnisliste entweder nach **AMRunningMode: Passiver Modus** oder **AMRunningMode: SxS Passive Mode.**    |

> [!NOTE]
> In einigen Versionen *von* Windows wird möglicherweise *Windows Defender Antivirus* anstelle von Microsoft Defender Antivirus angezeigt.

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>Manuelles Festlegen von Microsoft Defender Antivirus auf Windows Server in den passiven Modus

Führen Sie die folgenden Schritte aus, um Microsoft Defender Antivirus auf Windows Server, Version 1803 oder höher oder Windows Server 2019 auf den passiven Modus festzulegen:

1. Öffnen Sie den Registrierungs-Editor, und navigieren Sie dann zu <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Bearbeiten (oder erstellen) Sie einen DWORD-Eintrag namens **ForcePassiveMode,** und geben Sie die folgenden Einstellungen an:
   - Legen Sie den DWORD-Wert auf **1** fest.
   - Wählen Sie unter **Basis** die Option **Hexadezimal** aus

> [!NOTE]
> Sie können andere Methoden verwenden, um den Registrierungsschlüssel festzulegen, z. B. die folgenden:
>- [Gruppenrichtlinieneinstellung](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Tool für lokale Gruppenrichtlinienobjekt](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Ein Paket in Configuration Manager](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Start Microsoft Defender Antivirus on Windows Server 2016

Wenn Sie Windows Server 2016 verwenden, müssen Sie Microsoft Defender Antivirus möglicherweise manuell starten. Dazu können Sie das PowerShell-Cmdlet `mpcmdrun.exe -wdenable` auf dem Gerät verwenden.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Abrufen von Updates für Microsoft Defender Antivirus

Es ist wichtig, Microsoft Defender Antivirus auf dem neuesten Stand zu halten, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind, auch wenn Microsoft Defender Antivirus im passiven Modus ausgeführt wird. (Siehe [Microsoft Defender Antivirus Kompatibilität.)](microsoft-defender-antivirus-compatibility.md)

Es gibt zwei Arten von Updates, um Microsoft Defender Antivirus auf dem neuesten Stand zu halten:

- Security Intelligence-Updates
- Produktupdates

Um Ihre Updates zu erhalten, befolgen Sie die Anleitungen unter [Verwalten Microsoft Defender Antivirus Updates und wenden Basispläne an.](manage-updates-baselines-microsoft-defender-antivirus.md)

## <a name="uninstall-your-non-microsoft-solution"></a>Deinstallieren Ihrer Nicht-Microsoft-Lösung

Wenn Sie zu diesem Zeitpunkt Folgendes haben:

- Die Geräte Ihrer Organisation wurden in Defender für Endpunkt integriert und 
- Microsoft Defender Antivirus installiert und aktiviert ist, 

Der nächste Schritt besteht dann darin, Ihre nicht von Microsoft stammende Endpunktschutzlösung zu deinstallieren. 

Um Hilfe zu dieser Aufgabe zu erhalten, wenden Sie sich an das technische Supportteam Ihres Lösungsanbieters.

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>Stellen Sie sicher, dass Defender für Endpunkt ordnungsgemäß funktioniert

Nachdem Sie nun in Defender für Endpunkt integriert und Ihre frühere Nicht-Microsoft-Lösung deinstalliert haben, müssen Sie im nächsten Schritt sicherstellen, dass Defender für Endpunkt ordnungsgemäß funktioniert. Eine gute Möglichkeit hierfür ist ein Besuch der Demoszenarienwebsite für Defender für Endpunkt ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Probieren Sie eines oder mehrere der Demoszenarien auf dieser Seite aus, einschließlich mindestens der folgenden:

- Aus der Cloud gelieferter Schutz
- Potenziell unerwünschte Anwendungen (PUA)
- Netzwerkschutz (Network Protection, NP)

## <a name="next-steps"></a>Nächste Schritte

**Herzlichen Glückwunsch!** Sie haben Ihre [Migration zu Defender für Endpunkt](switch-to-microsoft-defender-migration.md#the-migration-process)abgeschlossen! 

- [Besuchen Sie Ihr Dashboard für Sicherheitsvorgänge](security-operations-dashboard.md) im Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). 
- [Verwalten von Defender für Endpunkt, nach der Migration.](manage-atp-post-migration.md)
