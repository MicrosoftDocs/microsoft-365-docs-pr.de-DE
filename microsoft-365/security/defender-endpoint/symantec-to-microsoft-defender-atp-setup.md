---
title: Symantec zu Microsoft Defender for Endpoint – Phase 2, Einrichten
description: Dies ist Phase 2, Setup, der Migration von Symantec zu Microsoft Defender for Endpoint
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 32ed277c87f5cca1a286cc24549dc331774cf03b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245732"
---
# <a name="migrate-from-symantec---phase-2-set-up-microsoft-defender-for-endpoint"></a>Migrieren von Symantec – Phase 2: Einrichten von Microsoft Defender for Endpoint

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Phase 1: Vorbereiten](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Phase 1: Vorbereiten](symantec-to-microsoft-defender-atp-prepare.md) |![Phase 2: Einrichten](images/phase-diagrams/setup.png)<br/>Phase 2: Einrichten |[![Phase 3: Onboarding](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Phase 3: Onboarding](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
||*Sie sind hier!* | |


**Willkommen bei der Setupphase der [Migration von Symantec zu Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**. Diese Phase umfasst die folgenden Schritte:
1. [Aktivieren oder neu installieren Microsoft Defender Antivirus (für bestimmte Versionen von Windows).](#enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows)
2. [Aktivieren Microsoft Defender Antivirus](#enable-microsoft-defender-antivirus).
3. [Updates für Microsoft Defender Antivirus](#get-updates-for-microsoft-defender-antivirus).
4. [Fügen Sie Microsoft Defender for Endpoint der Ausschlussliste für Symantec hinzu.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec)
5. [Fügen Sie Symantec zur Ausschlussliste für Microsoft Defender Antivirus](#add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus).
6. [Fügen Sie Symantec der Ausschlussliste für Microsoft Defender for Endpoint hinzu.](#add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint)
7. [Richten Sie Ihre Gerätegruppen, Gerätesammlungen und Organisationseinheiten ein.](#set-up-your-device-groups-device-collections-and-organizational-units)
8. [Konfigurieren von Antischalwarerichtlinien und Echtzeitschutz](#configure-antimalware-policies-and-real-time-protection).

## <a name="enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows"></a>Aktivieren oder neu installieren Microsoft Defender Antivirus (für bestimmte Versionen von Windows)

> [!TIP]
> Wenn Sie Windows 10 ausführen, müssen Sie diese Aufgabe nicht ausführen. Fahren Sie mit **[Aktivieren Microsoft Defender Antivirus fort.](#enable-microsoft-defender-antivirus)**

In bestimmten Versionen Windows Microsoft Defender Antivirus möglicherweise deinstalliert oder deaktiviert. Dies liegt daran, Microsoft Defender Antivirus nicht in den passiven oder deaktivierten Modus wechselt, wenn Sie ein Antivirenprodukt eines Drittanbieters, z. B. Symantec, installieren. Weitere Informationen finden Sie unter [Microsoft Defender Antivirus Kompatibilität](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility). 

Jetzt, da Sie von Symantec zu Microsoft Defender for Endpoint wechseln, müssen Sie den Microsoft Defender Antivirus aktivieren oder neu installieren und ihn auf den passiven Modus festlegen. 

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Neuinstallation Microsoft Defender Antivirus auf Windows Server

> [!NOTE]
> Das folgende Verfahren gilt nur für Endpunkte oder Geräte, auf der die folgenden Versionen von Windows:
> - Windows Server 2019
> - Windows Server, Version 1803 (nur Kernmodus)
> - Windows Server 2016
> 
> Microsoft Defender Antivirus ist in Windows 10, aber möglicherweise deaktiviert. Fahren Sie in diesem Fall mit Aktivieren [von Microsoft Defender Antivirus fort.](#enable-microsoft-defender-antivirus)

1. Öffnen Sie als lokaler Administrator auf dem Endpunkt oder Gerät Windows PowerShell.

1. Führen Sie die folgenden PowerShell-Cmdlets aus:<br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`

    > [!NOTE]
    > Wenn Sie den BEFEHL DISM innerhalb einer Tasksequenz verwenden, in der PS ausgeführt wird, ist der folgende Pfad cmd.exe erforderlich.
    > Beispiel:<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Verwenden Sie das folgende PowerShell-Cmdlet, um zu überprüfen, ob Microsoft Defender Antivirus ausgeführt wird: <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>Verwenden Sie Windows Server 2016?

Wenn Sie Windows Server 2016 verwenden und Probleme beim Aktivieren Microsoft Defender Antivirus haben, verwenden Sie das folgende PowerShell-Cmdlet:

`mpcmdrun -wdenable`

> [!TIP]
> Benötigen Sie weitere Hilfe? Siehe [Microsoft Defender Antivirus on Windows Server 2016 and 2019](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016).

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Festlegen Microsoft Defender Antivirus passiven Modus auf Windows Server

Da Ihre Organisation weiterhin Symantec verwendet, müssen Sie Microsoft Defender Antivirus passiven Modus festlegen. Auf diese Weise können Symantec und Microsoft Defender Antivirus nebeneinander ausgeführt werden, bis Sie das Onboarding bei Microsoft Defender for Endpoint abgeschlossen haben.

1. Öffnen Sie den Registrierungs-Editor, und navigieren Sie dann zu <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Bearbeiten (oder erstellen) Sie einen DWORD-Eintrag namens **ForceDefenderPassiveMode,** und geben Sie die folgenden Einstellungen an:
   - Legen Sie den Wert des DWORD auf **1 .**
   - Wählen **Sie unter Basis** die Option **Hexadezimal aus.**

> [!NOTE]
> Sie können andere Methoden zum Festlegen des Registrierungsschlüssels verwenden, z. B.:
>- [Gruppenrichtlinieneinstellung](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Objekttool für lokale Gruppenrichtlinien](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Ein Paket im Configuration Manager](/mem/configmgr/apps/deploy-use/packages-and-programs)

## <a name="enable-microsoft-defender-antivirus"></a>Aktivieren Microsoft Defender Antivirus

Da Ihre Organisation Symantec als primäre Antivirenlösung verwendet hat, ist Microsoft Defender Antivirus wahrscheinlich auf den Geräten Ihrer Organisation Windows deaktiviert. Dieser Schritt des Migrationsprozesses umfasst das Aktivieren Microsoft Defender Antivirus. 

Um die Microsoft Defender Antivirus zu aktivieren, empfehlen wir die Verwendung von Intune. Sie können jedoch eine der Methoden verwenden, die in der folgenden Tabelle aufgeführt sind:

|Methode  |Vorgehensweise  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**HINWEIS:** Intune ist jetzt Microsoft Endpoint Manager. |1. Wechseln Sie zum [Microsoft Endpoint Manager Admin Center,](https://go.microsoft.com/fwlink/?linkid=2109431) und melden Sie sich an.<br/><br/>2. Wählen Sie  >  **Gerätekonfigurationsprofile** aus, und wählen Sie dann den Profiltyp aus, den Sie konfigurieren möchten. Wenn Sie noch keinen Profiltyp für Geräteeinschränkungen erstellt haben oder einen neuen erstellen möchten, lesen Sie Konfigurieren von Geräteeinschränkungseinstellungen [in Microsoft Intune](/intune/device-restrictions-configure). <br/><br/>3. Wählen Sie **Eigenschaften** aus, und wählen Sie dann **Konfigurationseinstellungen: Bearbeiten aus.**<br/><br/>4. Erweitern **Sie Microsoft Defender Antivirus**. <br/><br/>5. Aktivieren des **in der Cloud übermittelten Schutzes**.<br/><br/>6. Wählen Sie im **Dropdownmenü Benutzer vor der Beispielübermittlung** anforderen die Option **Alle Beispiele automatisch senden aus.**<br/><br/>7. Wählen Sie im **Dropdownmenü Potenziell unerwünschte Anwendungen erkennen** die Option **Aktivieren** oder **Überwachen aus.**<br/><br/>8. Wählen Sie **Überprüfen + Speichern** aus, und wählen Sie dann Speichern **aus.**<br/>Weitere Informationen zu Intune-Geräteprofilen, einschließlich der Erstellung und Konfiguration ihrer Einstellungen, finden Sie unter Was [sind Microsoft Intune Geräteprofile?](/intune/device-profiles).|
|Systemsteuerung in Windows     |Folgen Sie den Anweisungen hier: [Aktivieren sie Microsoft Defender Antivirus](/mem/intune/user-help/turn-on-defender-windows). <br/>**HINWEIS**: In einigen Versionen *von Windows Defender Antivirus* *Microsoft Defender Antivirus* möglicherweise Windows.        |
|[Erweiterte Gruppenrichtlinienverwaltung](/microsoft-desktop-optimization-pack/agpm/) <br/>oder<br/>[Gruppenrichtlinien-Verwaltungskonsole](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. Wechseln Sie zu `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` . <br/><br/>2. Suchen Sie nach einer Richtlinie namens **Deaktivieren Microsoft Defender Antivirus**.<br/><br/>3. Wählen Sie **Richtlinieneinstellung bearbeiten** aus, und stellen Sie sicher, dass die Richtlinie deaktiviert ist. Dies ermöglicht Microsoft Defender Antivirus. <br/><br/>**HINWEIS**: In einigen Versionen *von Windows Defender Antivirus* *Microsoft Defender Antivirus* möglicherweise Windows. |

### <a name="verify-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Überprüfen, Microsoft Defender Antivirus sich im passiven Modus befindet

Microsoft Defender Antivirus können zusammen mit Symantec ausgeführt werden, wenn Sie Microsoft Defender Antivirus passiven Modus festlegen. Sie können entweder die Eingabeaufforderung oder PowerShell verwenden, um diese Aufgabe auszuführen, wie in der folgenden Tabelle beschrieben:

|Methode  |Vorgehensweise  |
|---------|---------|
|Eingabeaufforderung     |1. Öffnen Sie auf Windows Gerät die Eingabeaufforderung als Administrator. <br/><br/>2. Geben Sie `sc query windefend` ein , und drücken Sie dann die EINGABETASTE.<br/><br/>3. Überprüfen Sie die Ergebnisse, um zu bestätigen, Microsoft Defender Antivirus im passiven Modus ausgeführt wird.         |
|PowerShell     |1. Öffnen Sie auf Windows Gerät Windows PowerShell Administrator.<br/><br/>2. Führen Sie das [Cmdlet Get-MpComputerStatus](/powershell/module/defender/Get-MpComputerStatus) aus.<br/> <br/>3. Suchen Sie in der Liste der Ergebnisse nach **AMRunningMode: Passive Mode** oder **AMRunningMode: SxS Passive Mode**.|

> [!NOTE]
> In einigen *Versionen von* Windows Defender Antivirus *Microsoft Defender Antivirus* möglicherweise Windows.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Updates für Microsoft Defender Antivirus

Die Microsoft Defender Antivirus ist wichtig, um sicherzustellen, dass Ihre Geräte über die neuesten Technologien und Features verfügen, die zum Schutz vor neuer Schadsoftware und Angriffstechniken erforderlich sind, auch wenn Microsoft Defender Antivirus im passiven Modus [ausgeführt wird.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Es gibt zwei Arten von Updates, die Microsoft Defender Antivirus aktualisiert werden:
- Sicherheitsintelligenzupdates
- Produktupdates

Um Ihre Updates zu erhalten, folgen Sie den Anweisungen unter [Manage Microsoft Defender Antivirus updates and apply baselines](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec"></a>Hinzufügen von Microsoft Defender for Endpoint zur Ausschlussliste für Symantec

Dieser Schritt des Setupprozesses umfasst das Hinzufügen von Microsoft Defender für Endpoint zur Ausschlussliste für Symantec und alle anderen Sicherheitsprodukte, die Ihre Organisation verwendet. Die spezifischen zu konfigurierenden Ausschlüsse hängen davon ab, Windows Ihre Endpunkte oder Geräte ausgeführt werden, und sind in der folgenden Tabelle aufgeführt:

|Betriebssystem |Ausschlüsse |
|--|--|
|- Windows 10, [Version 1803](/windows/release-health/status-windows-10-1803) oder höher (Siehe [Windows 10 Versionsinformationen](/windows/release-health/release-information))<br/>- Windows 10 Version 1703 oder 1709 mit [installierter KB4493441](https://support.microsoft.com/help/4493441) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server, Version 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/><br/>  |
|- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/><br/>- [Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/><br/>- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/><br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/><br/>**HINWEIS**: Dabei können temporäre Überwachungshostdateien 6\45 unterschiedliche nummerierte Unterordner sein.<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Hinzufügen von Symantec zur Ausschlussliste für Microsoft Defender Antivirus

In diesem Schritt des Setupprozesses fügen Sie Symantec und Ihre anderen Sicherheitslösungen der Microsoft Defender Antivirus hinzu. 

> [!NOTE]
> Eine Vorstellung davon, welche Prozesse und Dienste ausgeschlossen werden, finden Sie unter Broadcom es [Processes and services used by Endpoint Protection 14](https://knowledge.broadcom.com/external/article/170706/processes-and-services-used-by-endpoint.html).

Wenn Sie [Ausschlüsse zu Microsoft Defender Antivirus hinzufügen,](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)sollten Sie Pfad- und Prozessausschlüsse hinzufügen. Beachten Sie die folgenden Punkte:
- Pfadausschlüsse schließen bestimmte Dateien und den Zugriff auf diese Dateien aus.
- Prozessausschlüsse schließen jegliche Berührungen eines Prozesses aus, schließen den Prozess selbst jedoch nicht aus.
- Wenn Sie jede ausführbare Datei (.exe) sowohl als Pfadausschluss als auch als Prozessausschluss auflisten, werden der Prozess und alles, was er berührt, ausgeschlossen.
- Listen Sie Ihre Prozessausschlüsse mithilfe des vollständigen Pfads auf, und nicht nur anhand ihres Namens. (Die Nur-Name-Methode ist weniger sicher.)

Sie können aus mehreren Methoden auswählen, um Ihre Ausschlüsse Microsoft Defender Antivirus hinzuzufügen, wie in der folgenden Tabelle aufgeführt:

|Methode | Vorgehensweise|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**HINWEIS:** Intune ist jetzt Microsoft Endpoint Manager. |1. Wechseln Sie zum [Microsoft Endpoint Manager Admin Center,](https://go.microsoft.com/fwlink/?linkid=2109431) und melden Sie sich an.<br/><br/>2. Wählen Sie  >  **Gerätekonfigurationsprofile** aus, und wählen Sie dann das Profil aus, das Sie konfigurieren möchten.<br/><br/>3. Wählen Sie **unter Verwalten** die Option **Eigenschaften aus.** <br/><br/>4. Wählen Sie **Konfigurationseinstellungen aus: Bearbeiten**.<br/><br/>5. Erweitern **Sie Microsoft Defender Antivirus**, und erweitern Sie dann **Microsoft Defender Antivirus Ausschlüsse .**<br/><br/>6. Geben Sie die Dateien und Ordner, Erweiterungen und Prozesse an, die von den Scans Microsoft Defender Antivirus werden. Referenz finden Sie unter [Microsoft Defender Antivirus Ausschlüsse .](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<br/><br/>7. Wählen Sie **Überprüfen + Speichern** aus, und wählen Sie dann Speichern **aus.**  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) |1. Wechseln Sie mit der [Configuration Manager-Konsole](/mem/configmgr/core/servers/manage/admin-console)zu **Assets and Compliance**  >  **Endpoint Protection**  >  **Anmalware Policies**, und wählen Sie dann die Richtlinie aus, die Sie ändern möchten. <br/><br/>2. Geben Sie Ausschlusseinstellungen für Dateien und Ordner, Erweiterungen und Prozesse an, die von Microsoft Defender Antivirus ausgeschlossen werden. |
|[Gruppenrichtlinienobjekt](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](https://technet.microsoft.com/library/cc731212.aspx)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.<br/><br/>2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.<br/><br/>3. Erweitern Sie die Struktur, **um Windows komponenten > Microsoft Defender Antivirus > zu erweitern.**<br/>**HINWEIS**: In einigen Versionen *von Windows Defender Antivirus* *Microsoft Defender Antivirus* möglicherweise Windows.<br/><br/>4. Doppelklicken Sie auf die **Einstellung Pfadausschlüsse,** und fügen Sie die Ausschlüsse hinzu.<br/><br/>- Legen Sie die Option auf **Aktiviert .**<br/><br/>- Klicken Sie **im Abschnitt Optionen** auf **Anzeigen...**.<br/><br/>- Geben Sie jeden Ordner in einer eigenen Zeile unter der **Spalte Wertname** an.<br/><br/>– Wenn Sie eine Datei angeben, stellen Sie sicher, dass Sie einen vollqualifizierten Pfad zur Datei eingeben, einschließlich Laufwerkbuchstabe, Ordnerpfad, Dateinamen und Erweiterung. Geben **Sie 0** in die **Spalte Wert** ein.<br/><br/>5. Klicken Sie auf **OK**.<br/><br/>6. Doppelklicken Sie auf die **Einstellung Erweiterungsausschlüsse,** und fügen Sie die Ausschlüsse hinzu.<br/><br/>- Legen Sie die Option auf **Aktiviert .**<br/><br/>- Klicken Sie **im Abschnitt Optionen** auf **Anzeigen...**.<br/><br/>- Geben Sie jede Dateierweiterung in einer eigenen Zeile unter der **Spalte Wertname** ein.  Geben **Sie 0** in die **Spalte Wert** ein.<br/>7. Klicken Sie auf **OK**. |
|Lokales Gruppenrichtlinienobjekt |1. Öffnen Sie auf dem Endpunkt oder Gerät den Editor für lokale Gruppenrichtlinien. <br/><br/>2. Wechseln Sie zu **Computerkonfiguration**  >  **Administrative Vorlagen** Windows  >  **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Ausschlüsse .** <br/>**HINWEIS**: In einigen Versionen *von Windows Defender Antivirus* *Microsoft Defender Antivirus* möglicherweise Windows.<br/><br/>3. Geben Sie Ihre Pfad- und Prozessausschlüsse an. |
|Registrierungsschlüssel |1. Exportieren Sie den folgenden Registrierungsschlüssel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<br/><br/>2. Importieren Sie den Registrierungsschlüssel. Im Folgenden zwei Beispiele:<br/>- Lokaler Pfad: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Netzwerkfreigabe: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>Hinzufügen von Symantec zur Ausschlussliste für Microsoft Defender for Endpoint

Zum Hinzufügen von Ausschlüssen zu Microsoft Defender for Endpoint erstellen Sie [Indikatoren](/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files).

1. Wechseln Sie zum Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) und melden Sie sich an.

1. Wählen Sie im Navigationsbereich **Einstellungen**  >    >  **Regelindikatoren aus.**

1.  Wählen Sie auf der Registerkarte **Dateihashes** die Option **Indikator hinzufügen aus.**

1. Geben Sie **auf der** Registerkarte Indikator die folgenden Einstellungen an:
   - Dateihash (Benötigen Sie Hilfe? Weitere [Informationen finden Sie unter Suchen eines Dateihashs mithilfe von CMPivot](#find-a-file-hash-using-cmpivot) in diesem Artikel.)
   - Wählen **Sie unter Expires on (UTC)** die Option **Nie aus.**
   
1. Geben Sie **auf** der Registerkarte Aktion die folgenden Einstellungen an:
   - **Reaktionsaktion**: **Zulassen**
   - Titel und Beschreibung

1. Wählen Sie **auf der** Registerkarte Bereich unter **Gerätegruppen** entweder **Alle Geräte in meinem** Bereich oder **Select from list aus aus.**

1. Überprüfen Sie **auf der** Registerkarte Zusammenfassung die Einstellungen, und klicken Sie dann auf **Speichern**.

### <a name="find-a-file-hash-using-cmpivot"></a>Suchen eines Dateihashs mithilfe von CMPivot

CMPivot ist ein Konsolenprogramm für Configuration Manager. CMPivot bietet Zugriff auf den Echtzeitstatus von Geräten in Ihrer Umgebung. Es führt sofort eine Abfrage auf allen derzeit verbundenen Geräten in der Zielsammlung aus und gibt die Ergebnisse zurück. Weitere Informationen finden Sie unter [CMPivot overview](/mem/configmgr/core/servers/manage/cmpivot-overview).

Führen Sie die folgenden Schritte aus, um CMPivot zum Herunterladen des Dateihashs zu verwenden:

1. Überprüfen Sie [die Voraussetzungen](/mem/configmgr/core/servers/manage/cmpivot#prerequisites).<br/>

2. [Starten Sie CMPivot](/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot). 

3. Verbinden configuration manager ( `SCCM_ServerName.DomainName.com` ).

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
|[Gerätegruppen](/microsoft-365/security/defender-endpoint/machine-groups) (früher als Computergruppen bezeichnet) ermöglichen Ihrem Sicherheitsbetriebsteam die Konfiguration von Sicherheitsfunktionen, z. B. automatisierte Untersuchung und Behebung.<br/> Gerätegruppen sind auch hilfreich, um diesen Geräten Zugriff zu zuweisen, damit Ihr Sicherheitsbetriebsteam bei Bedarf Abhilfemaßnahmen ausführen kann. <br/>Gerätegruppen werden in der Microsoft Defender Security Center. |1. Wechseln Sie zum Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<br/><br/>2. Wählen Sie im Navigationsbereich auf der linken Seite die **Option Einstellungen**  >  **Berechtigungen**  >  **Gerätegruppen aus.**  <br/><br/>3. Wählen Sie **+ Gerätegruppe hinzufügen aus.**<br/><br/>4. Geben Sie einen Namen und eine Beschreibung für die Gerätegruppe an.<br/><br/>5. Wählen Sie in der **Liste Automatisierungsebene** eine Option aus. (Es wird **empfohlen, vollständig – Bedrohungen automatisch zu be behebung.)** Weitere Informationen zu den verschiedenen Automatisierungsebenen finden Sie unter [Wie Bedrohungen behoben werden.](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<br/><br/>6. Geben Sie Bedingungen für eine übereinstimmende Regel an, um zu bestimmen, welche Geräte zur Gerätegruppe gehören. Sie können beispielsweise eine Domäne, Betriebssystemversionen oder sogar [Gerätetags verwenden.](/microsoft-365/security/defender-endpoint/machine-tags)<br/> <br/>7. Geben Sie auf der Registerkarte **Benutzerzugriff** Rollen an, die Zugriff auf die Geräte haben sollen, die in der Gerätegruppe enthalten sind. <br/><br/>8. Wählen Sie **Fertig aus.** |
|[Gerätesammlungen](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) ermöglichen Ihrem Sicherheitsbetriebsteam die Verwaltung von Anwendungen, die Bereitstellung von Kompatibilitätseinstellungen oder das Installieren von Softwareupdates auf den Geräten in Ihrer Organisation. <br/>Gerätesammlungen werden mithilfe von [Configuration Manager erstellt.](/mem/configmgr/) |Führen Sie die Schritte unter [Create a collection aus.](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create) |
|[Mit Organisationseinheiten](/azure/active-directory-domain-services/create-ou) können Sie Objekte wie Benutzerkonten, Dienstkonten oder Computerkonten logisch gruppieren. Anschließend können Sie bestimmten Organisationseinheiten Administratoren zuweisen und Gruppenrichtlinien anwenden, um gezielte Konfigurationseinstellungen zu erzwingen.<br/> Organisationseinheiten werden in den [Azure Active Directory definiert.](/azure/active-directory-domain-services) | Führen Sie die Schritte unter [Create an Organizational Unit in an Azure Active Directory Domain Services managed domain aus.](/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Konfigurieren von Antischalwarerichtlinien und Echtzeitschutz

Konfigurieren Sie mithilfe von Configuration Manager und Ihren Gerätesammlungen Die Antischalwarerichtlinien.

- Weitere Informationen finden Sie unter Create [and deploy anmalware policies for Endpoint Protection in Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies).

- Während Sie Ihre Antischalwarerichtlinien erstellen und [](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) konfigurieren, überprüfen Sie unbedingt die Echtzeitschutzeinstellungen, und aktivieren Sie blocken Sie [beim ersten Blick.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

> [!TIP]
> Sie können die Richtlinien vor den Geräten Ihrer Organisation auf onboarded bereitstellen.

## <a name="next-step"></a>Nächster Schritt

**Herzlichen Glückwunsch!** Sie haben die Setupphase der [Migration von Symantec zu Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)abgeschlossen.
- [Fahren Sie mit Phase 3: Onboarding zu Microsoft Defender for Endpoint fort.](symantec-to-microsoft-defender-atp-onboard.md)
