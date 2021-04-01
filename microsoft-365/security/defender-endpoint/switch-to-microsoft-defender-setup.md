---
title: Wechseln zu Microsoft Defender for Endpoint – Setup
description: Dies ist Phase 2, Setup, für den Wechsel zu Microsoft Defender for Endpoint.
keywords: Migration, windows defender advanced threat protection, atp, edr
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
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 6f2104e38bd55806e0873166b07a31aff46e9c24
ms.sourcegitcommit: 847b0920016ae20c82a0501bda6019cd940482df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51484756"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Wechseln zu Microsoft Defender for Endpoint – Phase 2: Setup

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Phase 1: Vorbereiten](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Phase 1: Vorbereiten](switch-to-microsoft-defender-prepare.md) |![Phase 2: Einrichten](images/phase-diagrams/setup.png)<br/>Phase 2: Einrichten |[![Phase 3: Onboard3](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Phase 3: Onboarding](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
||*Sie sind hier!* | |

**Willkommen bei der Setupphase des [Wechsels zu Microsoft Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)**. Diese Phase umfasst die folgenden Schritte:
1. [Aktivieren Sie Microsoft Defender Antivirus, und bestätigen Sie, dass es sich im passiven Modus befindet.](#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)
2. [Hier finden Sie Updates für Microsoft Defender Antivirus](#get-updates-for-microsoft-defender-antivirus).
3. [Fügen Sie Microsoft Defender for Endpoint der Ausschlussliste für Ihre vorhandene Endpunktlösung hinzu.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)
4. [Fügen Sie Ihre vorhandene Lösung der Ausschlussliste für Microsoft Defender Antivirus hinzu.](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus)
5. [Fügen Sie Ihre vorhandene Lösung der Ausschlussliste für Microsoft Defender for Endpoint hinzu.](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-for-endpoint)
6. [Richten Sie Ihre Gerätegruppen, Gerätesammlungen und Organisationseinheiten ein.](#set-up-your-device-groups-device-collections-and-organizational-units)
7. [Konfigurieren von Antischalwarerichtlinien und Echtzeitschutz](#configure-antimalware-policies-and-real-time-protection).

## <a name="enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode"></a>Aktivieren von Microsoft Defender Antivirus und Bestätigen des passiven Modus

Unter bestimmten Versionen von Windows, z. B. Windows Server, wurde Microsoft Defender Antivirus möglicherweise deinstalliert oder deaktiviert, als Ihre McAfee-Lösung installiert wurde. Dies liegt daran, dass Microsoft Defender Antivirus nicht in den passiven oder deaktivierten Modus wechselt, wenn Sie ein Antivirenprodukt eines Drittanbieters, z. B. McAfee, installieren. (Weitere Informationen dazu finden Sie unter [Microsoft Defender Antivirus-Kompatibilität](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).)

Dieser Schritt des Migrationsprozesses umfasst die folgenden Aufgaben:
- [Festlegen von DisableAntiSpyware auf false unter Windows Server](#set-disableantispyware-to-false-on-windows-server)
- [Erneutes Installieren von Microsoft Defender Antivirus auf Windows Server](#reinstall-microsoft-defender-antivirus-on-windows-server);
- [Festlegen des passiven Modus von Microsoft Defender Antivirus unter Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)
- [Aktivieren von Microsoft Defender Antivirus auf Ihren Windows-Clientgeräten;](#enable-microsoft-defender-antivirus-on-your-windows-client-devices) und
- [Bestätigen, dass Microsoft Defender Antivirus auf den passiven Modus festgelegt ist.](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode)  

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Festlegen von DisableAntiSpyware auf false unter Windows Server

Der [Registrierungsschlüssel DisableAntiSpyware](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wurde in der Vergangenheit verwendet, um Microsoft Defender Antivirus zu deaktivieren und ein anderes Antivirenprodukt wie McAfee zu bereitstellen. Im Allgemeinen sollte dieser Registrierungsschlüssel nicht auf Ihren #A0 und -Endpunkten vorhanden sein. Wenn Sie jedoch konfiguriert haben, gehen Sie wie hier vor, um den Wert auf `DisableAntiSpyware` false zu setzen:

1. Öffnen Sie auf Ihrem Windows Server-Gerät den Registrierungs-Editor.
2. Navigieren Sie zu `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.
3. Suchen Sie in diesem Ordner nach einem DWORD-Eintrag namens **DisableAntiSpyware**.
   - Wenn dieser Eintrag nicht zu sehen ist, sind Sie alle festgelegt.
   - Wenn **DisableAntiSpyware zu sehen ist,** fahren Sie mit Schritt 4 fort.
4. Klicken Sie mit der rechten Maustaste auf disableAntiSpyware DWORD, und wählen Sie dann **Ändern aus.**
5. Legen Sie den Wert auf `0` . (Dadurch wird der Wert des Registrierungsschlüssels auf *false gesetzt.)*

> [!TIP]
> Weitere Informationen zu diesem Registrierungsschlüssel finden Sie unter [DisableAntiSpyware](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware).

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Installieren von Microsoft Defender Antivirus auf Windows Server

> [!NOTE]
> Das folgende Verfahren gilt nur für Endpunkte oder Geräte mit den folgenden Versionen von Windows:
> - Windows Server 2019
> - Windows Server, Version 1803 (nur Kernmodus)
> - Windows Server 2016

1. Öffnen Sie als lokaler Administrator auf dem Endpunkt oder Gerät Windows PowerShell.
2. Führen Sie die folgenden PowerShell-Cmdlets aus: <br/>   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
   > [!NOTE]
   > Wenn Sie den BEFEHL DISM innerhalb einer Tasksequenz verwenden, in der PS ausgeführt wird, ist der folgende Pfad cmd.exe erforderlich.
   > Beispiel:<br/>
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>
3. Verwenden Sie das folgende PowerShell-Cmdlet, um zu überprüfen, ob Microsoft Defender Antivirus ausgeführt wird: <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>Verwenden Sie Windows Server 2016?

Wenn Sie Windows Server 2016 verwenden und Probleme beim Aktivieren von Microsoft Defender Antivirus haben, verwenden Sie das folgende PowerShell-Cmdlet:

`mpcmdrun -wdenable`

> [!TIP]
> Benötigen Sie weitere Hilfe? Weitere [Informationen finden Sie unter Microsoft Defender Antivirus auf Windows Server](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016).

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Festlegen des passiven Modus von Microsoft Defender Antivirus unter Windows Server

Da Ihre Organisation ihre vorhandene Endpunktschutzlösung weiterhin verwendet, müssen Sie Microsoft Defender Antivirus auf den passiven Modus festlegen. Auf diese Weise können Ihre vorhandene Lösung und Microsoft Defender Antivirus nebeneinander ausgeführt werden, bis Sie das Onboarding für Microsoft Defender for Endpoint abgeschlossen haben.

1. Öffnen Sie den Registrierungs-Editor, und navigieren Sie dann zu <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.
2. Bearbeiten (oder erstellen) Sie einen DWORD-Eintrag namens **ForceDefenderPassiveMode,** und geben Sie die folgenden Einstellungen an:
   - Legen Sie den Wert des DWORD auf **1 .**
   - Wählen **Sie unter Basis** die Option **Hexadezimal aus.**

> [!NOTE]
> Sie können andere Methoden zum Festlegen des Registrierungsschlüssels verwenden, z. B.:
>- [Gruppenrichtlinieneinstellung](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Objekttool für lokale Gruppenrichtlinien](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Ein Paket im Configuration Manager](https://docs.microsoft.com/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="enable-microsoft-defender-antivirus-on-your-windows-client-devices"></a>Aktivieren von Microsoft Defender Antivirus auf Ihren Windows-Clientgeräten

Da Ihre Organisation eine Nicht-Microsoft-Antivirenlösung verwendet hat, ist Microsoft Defender Antivirus höchstwahrscheinlich auf den Windows-Geräten Ihrer Organisation deaktiviert. Dieser Schritt des Migrationsprozesses umfasst die Aktivierung von Microsoft Defender Antivirus. 

Um Microsoft Defender Antivirus zu aktivieren, wird die Verwendung von Intune empfohlen. Sie können jedoch eine der Methoden verwenden, die in der folgenden Tabelle aufgeführt sind:

|Methode  |Vorgehensweise  |
|---------|---------|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**HINWEIS:** Intune ist jetzt Microsoft Endpoint Manager. |1. Wechseln Sie zum [Microsoft Endpoint Manager Admin Center,](https://go.microsoft.com/fwlink/?linkid=2109431) und melden Sie sich an.<br/>2. Wählen Sie  >  **Gerätekonfigurationsprofile** aus, und wählen Sie dann den Profiltyp aus, den Sie konfigurieren möchten. Wenn Sie noch keinen Profiltyp für Geräteeinschränkungen erstellt haben oder einen neuen erstellen möchten, lesen Sie Konfigurieren von Geräteeinschränkungseinstellungen [in Microsoft Intune](https://docs.microsoft.com/intune/device-restrictions-configure). <br/>3. Wählen Sie **Eigenschaften** aus, und wählen Sie dann **Konfigurationseinstellungen: Bearbeiten aus.**<br/>4. Erweitern **Sie Microsoft Defender Antivirus**. <br/>5. Aktivieren des **in der Cloud übermittelten Schutzes**.<br/>6. Wählen Sie im **Dropdownmenü Benutzer vor der Beispielübermittlung** anforderen die Option **Alle Beispiele automatisch senden aus.**<br/>7. Wählen Sie im **Dropdownmenü Potenziell unerwünschte Anwendungen erkennen** die Option **Aktivieren** oder **Überwachen aus.**<br/>8. Wählen Sie **Überprüfen + Speichern** aus, und wählen Sie dann Speichern **aus.**<br/>**TIPP**: Weitere Informationen zu Intune-Geräteprofilen, einschließlich der Erstellung und Konfiguration ihrer Einstellungen, finden Sie unter [Was sind Microsoft Intune-Geräteprofile?](https://docs.microsoft.com/intune/device-profiles).|
|Systemsteuerung in Windows     |Folgen Sie den Anweisungen hier: [Aktivieren Sie Microsoft Defender Antivirus](https://docs.microsoft.com/mem/intune/user-help/turn-on-defender-windows). <br/>**HINWEIS:** In einigen Versionen von Windows *Windows Defender möglicherweise* ein Antivirus anstelle von Microsoft Defender *Antivirus* angezeigt.        |
|[Erweiterte Gruppenrichtlinienverwaltung](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) <br/>oder<br/>[Gruppenrichtlinien-Verwaltungskonsole](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. Wechseln Sie zu **Computerkonfiguration**  >  **Administrative Vorlagen**  >  **Windows-Komponenten** Microsoft Defender  >  **Antivirus**. <br/>2. Suchen Sie nach einer Richtlinie namens **Deaktivieren von Microsoft Defender Antivirus**.<br/>3. Wählen Sie **Richtlinieneinstellung bearbeiten** aus, und stellen Sie sicher, dass die Richtlinie deaktiviert ist. Dadurch wird Microsoft Defender Antivirus aktiviert. <br/>**HINWEIS:** In einigen Versionen von Windows *Windows Defender möglicherweise* ein Antivirus anstelle von Microsoft Defender *Antivirus* angezeigt. |

### <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Bestätigen, dass sich Microsoft Defender Antivirus im passiven Modus befindet

Microsoft Defender Antivirus kann zusammen mit Ihrer vorhandenen Endpunktschutzlösung ausgeführt werden, wenn Sie Microsoft Defender Antivirus in den passiven Modus festlegen. Sie können entweder die Eingabeaufforderung oder PowerShell verwenden, um diese Aufgabe auszuführen, wie in der folgenden Tabelle beschrieben:

|Methode  |Vorgehensweise  |
|---------|---------|
|Eingabeaufforderung     |1. Öffnen Sie auf einem Windows-Gerät die Eingabeaufforderung als Administrator. <br/>2. Geben Sie `sc query windefend` ein , und drücken Sie dann die EINGABETASTE.<br/>3. Überprüfen Sie die Ergebnisse, um zu bestätigen, dass Microsoft Defender Antivirus im passiven Modus ausgeführt wird.         |
|PowerShell     |1. Öffnen Sie auf einem Windows-Gerät Windows PowerShell administrator.<br/>2. Führen Sie das [Cmdlet Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/Get-MpComputerStatus) aus. <br/>3. Suchen Sie in der Liste der Ergebnisse nach **AMRunningMode: Passive Mode** oder **AMRunningMode: SxS Passive Mode**.          |

> [!NOTE]
> In einigen Versionen *von Windows Windows Defender antivirus* anstelle von Microsoft Defender *Antivirus* angezeigt.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Herunterladen von Updates für Microsoft Defender Antivirus

Microsoft Defender Antivirus auf dem neuesten Stand zu halten, ist wichtig, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuen Schadsoftware- und Angriffstechniken erforderlich sind, auch wenn Microsoft Defender Antivirus im passiven Modus [ausgeführt wird.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Es gibt zwei Arten von Updates im Zusammenhang mit der Aktualisierung von Microsoft Defender Antivirus:
- Sicherheitsintelligenzupdates
- Produktupdates

Um Ihre Updates zu erhalten, folgen Sie den Anweisungen unter Verwalten von [Microsoft Defender Antivirus-Updates und Anwenden von Baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>Hinzufügen von Microsoft Defender für Endpoint zur Ausschlussliste für Ihre vorhandene Lösung

Dieser Schritt des Setupprozesses umfasst das Hinzufügen von Microsoft Defender für Endpoint zur Ausschlussliste für Ihre vorhandene Endpunktschutzlösung und alle anderen Sicherheitsprodukte, die Ihre Organisation verwendet. 

> [!TIP]
> Hilfe zum Konfigurieren von Ausschlüssen finden Sie in der Dokumentation Ihres Lösungsanbieters.

Die spezifischen zu konfigurierenden Ausschlüsse hängen davon ab, welche Version von Windows Ihre Endpunkte oder Geräte ausgeführt werden, und sind in der folgenden Tabelle aufgeführt:

|Betriebssystem |Ausschlüsse |
|--|--|
|- Windows 10, [Version 1803](https://docs.microsoft.com/windows/release-health/status-windows-10-1803) oder höher (Siehe [Windows 10 Release Information](https://docs.microsoft.com/windows/release-health/release-information))<br/>- Windows 10, Version 1703 oder [1709](https://docs.microsoft.com/windows/release-health/status-windows-10-1709) mit [installierter KB4493441](https://support.microsoft.com/help/4493441) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server, Version 1803](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/>  |
|- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>- [Windows 7](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/>**HINWEIS**: Dabei können temporäre Überwachungshostdateien 6\45 unterschiedliche nummerierte Unterordner sein.<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Hinzufügen Ihrer vorhandenen Lösung zur Ausschlussliste für Microsoft Defender Antivirus

In diesem Schritt des Setupprozesses fügen Sie Ihre vorhandene Lösung der Ausschlussliste von Microsoft Defender Antivirus hinzu. 

Wenn Sie [Ausschlüsse zu Microsoft Defender Antivirus-Scans hinzufügen,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)sollten Sie Pfad- und Prozessausschlüsse hinzufügen. Beachten Sie die folgenden Punkte:
- Pfadausschlüsse schließen bestimmte Dateien und den Zugriff auf diese Dateien aus.
- Prozessausschlüsse schließen jegliche Berührungen eines Prozesses aus, schließen den Prozess selbst jedoch nicht aus.
- Wenn Sie jede ausführbare Datei (EXE) sowohl als Pfadausschluss als auch als Prozessausschluss auflisten, werden der Prozess und alles, was er berührt, ausgeschlossen.
- Listen Sie Ihre Prozessausschlüsse mithilfe des vollständigen Pfads auf, und nicht nur anhand ihres Namens. (Die Nur-Name-Methode ist weniger sicher.)

Sie können aus mehreren Methoden auswählen, um Ihre Ausschlüsse zu Microsoft Defender Antivirus hinzuzufügen, wie in der folgenden Tabelle aufgeführt:

|Methode | Vorgehensweise|
|--|--|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**HINWEIS:** Intune ist jetzt Microsoft Endpoint Manager. |1. Wechseln Sie zum [Microsoft Endpoint Manager Admin Center,](https://go.microsoft.com/fwlink/?linkid=2109431) und melden Sie sich an.<br/>2. Wählen Sie  >  **Gerätekonfigurationsprofile** aus, und wählen Sie dann das Profil aus, das Sie konfigurieren möchten.<br/>3. Wählen Sie **unter Verwalten** die Option **Eigenschaften aus.** <br/>4. Wählen Sie **Konfigurationseinstellungen aus: Bearbeiten**.<br/>5. Erweitern **Sie Microsoft Defender Antivirus,** und erweitern Sie **dann Microsoft Defender Antivirus-Ausschlüsse**.<br/>6. Geben Sie die Dateien und Ordner, Erweiterungen und Prozesse an, die von Microsoft Defender Antivirus-Scans ausgeschlossen werden. Referenz finden Sie unter [Microsoft Defender Antivirus-Ausschlüsse](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions).<br/>7. Wählen Sie **Überprüfen + Speichern** aus, und wählen Sie dann Speichern **aus.**  |
|[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/) |1. Wechseln Sie mit der [Configuration Manager-Konsole](https://docs.microsoft.com/mem/configmgr/core/servers/manage/admin-console)zu Ressourcen und **Compliance-Endpoint**  >  **Protection-Antischalwarerichtlinien,** und wählen Sie dann die Richtlinie aus, die  >  Sie ändern möchten. <br/>2. Geben Sie Ausschlusseinstellungen für Dateien und Ordner, Erweiterungen und Prozesse an, die von Microsoft Defender Antivirus-Scans ausgeschlossen werden. |
|[Gruppenrichtlinienobjekt](https://docs.microsoft.com/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](https://technet.microsoft.com/library/cc731212.aspx)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.<br/>2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.<br/>3. Erweitern Sie die Struktur auf **Windows-Komponenten**  >  **Microsoft Defender Antivirus**  >  **Exclusions**.<br/>**HINWEIS:** In einigen Versionen von Windows *Windows Defender möglicherweise* ein Antivirus anstelle von Microsoft Defender *Antivirus* angezeigt.<br/>4. Doppelklicken Sie auf die **Einstellung Pfadausschlüsse,** und fügen Sie die Ausschlüsse hinzu.<br/>- Legen Sie die Option auf **Aktiviert .**<br/>- Klicken Sie **im Abschnitt Optionen** auf **Anzeigen...**.<br/>- Geben Sie jeden Ordner in einer eigenen Zeile unter der **Spalte Wertname** an.<br/>– Wenn Sie eine Datei angeben, stellen Sie sicher, dass Sie einen vollqualifizierten Pfad zur Datei eingeben, einschließlich Laufwerkbuchstabe, Ordnerpfad, Dateinamen und Erweiterung. Geben **Sie 0** in die **Spalte Wert** ein.<br/>5. Klicken Sie auf **OK**.<br/>6. Doppelklicken Sie auf die **Einstellung Erweiterungsausschlüsse,** und fügen Sie die Ausschlüsse hinzu.<br/>- Legen Sie die Option auf **Aktiviert .**<br/>- Klicken Sie **im Abschnitt Optionen** auf **Anzeigen...**.<br/>- Geben Sie jede Dateierweiterung in einer eigenen Zeile unter der **Spalte Wertname** ein.  Geben **Sie 0** in die **Spalte Wert** ein.<br/>7. Klicken Sie auf **OK**. |
|Lokales Gruppenrichtlinienobjekt |1. Öffnen Sie auf dem Endpunkt oder Gerät den Editor für lokale Gruppenrichtlinien. <br/>2. Wechseln Sie zu **Computerkonfiguration**  >  **Administrative Vorlagen**  >  **Windows-Komponenten** Microsoft Defender  >    >  **Antivirus-Ausschlüsse**. <br/>**HINWEIS:** In einigen Versionen von Windows *Windows Defender möglicherweise* ein Antivirus anstelle von Microsoft Defender *Antivirus* angezeigt.<br/>3. Geben Sie Ihre Pfad- und Prozessausschlüsse an. |
|Registrierungsschlüssel |1. Exportieren Sie den folgenden Registrierungsschlüssel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<br/>2. Importieren Sie den Registrierungsschlüssel. Im Folgenden zwei Beispiele:<br/>- Lokaler Pfad: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Netzwerkfreigabe: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>Hinzufügen Ihrer vorhandenen Lösung zur Ausschlussliste für Microsoft Defender for Endpoint

Zum Hinzufügen von Ausschlüssen zu Microsoft Defender for Endpoint erstellen Sie [Indikatoren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files).

1. Wechseln Sie zum Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) und melden Sie sich an.
2. Wählen Sie im Navigationsbereich  >  **Einstellungsregeln**  >  **Indikatoren aus.**
3.  Wählen Sie auf der Registerkarte **Dateihashes** die Option **Indikator hinzufügen aus.**
4. Geben Sie **auf der** Registerkarte Indikator die folgenden Einstellungen an:
   - Dateihash (Benötigen Sie Hilfe? Weitere [Informationen finden Sie unter Suchen eines Dateihashs mithilfe von CMPivot](#find-a-file-hash-using-cmpivot) in diesem Artikel.)
   - Wählen **Sie unter Expires on (UTC)** die Option **Nie aus.**
5. Geben Sie **auf** der Registerkarte Aktion die folgenden Einstellungen an:
   - **Reaktionsaktion**: **Zulassen**
   - Titel und Beschreibung
6. Wählen Sie **auf der** Registerkarte Bereich unter **Gerätegruppen** entweder **Alle Geräte in meinem** Bereich oder **Select from list aus aus.**
7. Überprüfen Sie **auf der** Registerkarte Zusammenfassung die Einstellungen, und klicken Sie dann auf **Speichern**.

### <a name="find-a-file-hash-using-cmpivot"></a>Suchen eines Dateihashs mithilfe von CMPivot

CMPivot ist ein Konsolenprogramm für Configuration Manager. CMPivot bietet Zugriff auf den Echtzeitstatus von Geräten in Ihrer Umgebung. Es führt sofort eine Abfrage auf allen derzeit verbundenen Geräten in der Zielsammlung aus und gibt die Ergebnisse zurück. Weitere Informationen finden Sie unter [CMPivot overview](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot-overview).

Führen Sie die folgenden Schritte aus, um CMPivot zum Herunterladen des Dateihashs zu verwenden:

1. Überprüfen Sie [die Voraussetzungen](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#prerequisites).
2. [Starten Sie CMPivot](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot). 
3. Herstellen einer Verbindung mit Configuration Manager ( `SCCM_ServerName.DomainName.com` ).
4. Wählen Sie die **Registerkarte Abfrage** aus.
5. Wählen Sie **in der Liste Gerätesammlung** alle **Systeme (Standard) aus.**
6. Geben Sie im Abfragefeld die folgende Abfrage ein:<br/>

   ```kusto
   File(c:\\windows\\notepad.exe)
   | project Hash
   ```
   
   > [!NOTE]
   > Ersetzen Sie in der obigen *Abfragenotepad.exe* durch den Namen des Drittanbieter-Sicherheitsproduktprozesses. 

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Einrichten von Gerätegruppen, Gerätesammlungen und Organisationseinheiten

| Sammlungstyp | Vorgehensweise |
|--|--|
|[Gerätegruppen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) (früher als Computergruppen bezeichnet) ermöglichen Ihrem Sicherheitsbetriebsteam die Konfiguration von Sicherheitsfunktionen, z. B. automatisierte Untersuchung und Behebung.<br/> Gerätegruppen sind auch hilfreich, um diesen Geräten Zugriff zu zuweisen, damit Ihr Sicherheitsbetriebsteam bei Bedarf Abhilfemaßnahmen ausführen kann. <br/>Gerätegruppen werden im Microsoft Defender Security Center erstellt. |1. Wechseln Sie zum Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<br/>2. Wählen Sie im Navigationsbereich auf der linken Seite **Einstellungen**  >  **Berechtigungen**  >  **Gerätegruppen aus.**  <br/>3. Wählen Sie **+ Gerätegruppe hinzufügen aus.**<br/>4. Geben Sie einen Namen und eine Beschreibung für die Gerätegruppe an.<br/>5. Wählen Sie in der **Liste Automatisierungsebene** eine Option aus. (Es wird **empfohlen, vollständig – Bedrohungen automatisch zu be behebung.)** Weitere Informationen zu den verschiedenen Automatisierungsebenen finden Sie unter [Wie Bedrohungen behoben werden.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<br/>6. Geben Sie Bedingungen für eine übereinstimmende Regel an, um zu bestimmen, welche Geräte zur Gerätegruppe gehören. Sie können beispielsweise eine Domäne, Betriebssystemversionen oder sogar [Gerätetags verwenden.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags) <br/>7. Geben Sie auf der Registerkarte **Benutzerzugriff** Rollen an, die Zugriff auf die Geräte haben sollen, die in der Gerätegruppe enthalten sind. <br/>8. Wählen Sie **Fertig aus.** |
|[Gerätesammlungen](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/introduction-to-collections) ermöglichen Ihrem Sicherheitsbetriebsteam die Verwaltung von Anwendungen, die Bereitstellung von Kompatibilitätseinstellungen oder das Installieren von Softwareupdates auf den Geräten in Ihrer Organisation. <br/>Gerätesammlungen werden mithilfe von [Configuration Manager erstellt.](https://docs.microsoft.com/mem/configmgr/) |Führen Sie die Schritte unter [Create a collection aus.](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create) |
|[Mit Organisationseinheiten](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou) können Sie Objekte wie Benutzerkonten, Dienstkonten oder Computerkonten logisch gruppieren. Anschließend können Sie bestimmten Organisationseinheiten Administratoren zuweisen und Gruppenrichtlinien anwenden, um gezielte Konfigurationseinstellungen zu erzwingen.<br/> Organisationseinheiten sind in [Azure Active Directory Domain Services definiert.](https://docs.microsoft.com/azure/active-directory-domain-services) | Führen Sie die Schritte unter [Erstellen einer Organisationseinheit in einer verwalteten Azure Active Directory Domain Services-Domäne aus.](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Konfigurieren von Antischalwarerichtlinien und Echtzeitschutz

Konfigurieren Sie mithilfe von Configuration Manager und Ihren Gerätesammlungen Die Antischalwarerichtlinien.
- Weitere [Informationen finden Sie unter Create and deploy anmalware policies for Endpoint Protection in Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies).
- Während Sie Ihre Antischalwarerichtlinien erstellen und [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) konfigurieren, überprüfen Sie unbedingt die Echtzeitschutzeinstellungen, und aktivieren Sie blocken Sie [beim ersten Blick.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

> [!TIP]
> Sie können die Richtlinien vor den Geräten Ihrer Organisation auf onboarded bereitstellen.

## <a name="next-step"></a>Nächster Schritt

**Herzlichen Glückwunsch!** Sie haben die Setupphase des [Wechsels zu Microsoft Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)! abgeschlossen.

- [Fahren Sie mit Phase 3: Onboarding zu Microsoft Defender for Endpoint fort.](switch-to-microsoft-defender-onboard.md)
