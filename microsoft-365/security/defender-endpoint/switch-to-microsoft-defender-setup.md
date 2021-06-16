---
title: Wechseln zu Microsoft Defender für Endpunkt – Setup
description: Phase 2, der Einrichtungsprozess, beim Wechsel zu Microsoft Defender für Endpunkt.
keywords: Migration, Microsoft Defender für Endpunkt, edr, Windows Defender
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
ms.topic: article
ms.custom: migrationguides
ms.date: 06/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 82c734d8a394be048f9be862be114fae7f90e6b3
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930475"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Wechseln zu Microsoft Defender für Endpunkt – Phase 2: Setup

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Phase 1: Vorbereiten](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Phase 1: Vorbereiten](switch-to-microsoft-defender-prepare.md) |![Phase 2: Einrichten](images/phase-diagrams/setup.png)<br/>Phase 2: Einrichten |[![Phase 3: Onboard3](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Phase 3: Onboarding](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
||*Sie sind hier!* | |

**Willkommen bei der Einrichtungsphase des [Umstiegs auf Defender für Endpunkt.](switch-to-microsoft-defender-migration.md#the-migration-process)** Diese Phase umfasst die folgenden Schritte:

1. [Installieren/aktivieren Sie Microsoft Defender Antivirus auf Ihren Endpunkten](#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)neu.
2. [Konfigurieren Von Defender für Endpunkt](#configure-defender-for-endpoint).
3. [Fügen Sie Defender für Endpunkt zur Ausschlussliste für Ihre vorhandene Lösung](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)hinzu.
4. [Fügen Sie Ihre vorhandene Lösung der Ausschlussliste für Microsoft Defender Antivirus](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus)hinzu.
5. [Richten Sie Gerätegruppen, Gerätesammlungen und Organisationseinheiten ein.](#set-up-your-device-groups-device-collections-and-organizational-units)
6. [Konfigurieren Von Antischadsoftwarerichtlinien und Echtzeitschutz.](#configure-antimalware-policies-and-real-time-protection)


## <a name="reinstallenable-microsoft-defender-antivirus-on-your-endpoints"></a>Neuinstallation/Aktivierung Microsoft Defender Antivirus auf Ihren Endpunkten

In bestimmten Versionen von Windows wurde Microsoft Defender Antivirus wahrscheinlich deinstalliert oder deaktiviert, als Ihre Nicht-Microsoft-Antiviren-/Antischadsoftwarelösung installiert wurde. Es sei denn, und bis Geräte in Defender für Endpunkt integriert sind, wird Microsoft Defender Antivirus nicht zusammen mit einer Antivirenlösung ausgeführt, die nicht von Microsoft ist. Weitere Informationen finden Sie unter [Microsoft Defender Antivirus Kompatibilität.](microsoft-defender-antivirus-compatibility.md)

Da Sie nun planen, zu Defender für Endpunkt zu wechseln, müssen Sie möglicherweise bestimmte Schritte ausführen, um Microsoft Defender Antivirus neu zu installieren oder zu aktivieren. 


| Endpunkttyp  | Vorgehensweise  |
|---------|---------|
| Windows Clients (z. B. Endpunkte, die Windows 10 ausgeführt werden)     | Im Allgemeinen müssen Sie keine Maßnahmen für Windows Clients ergreifen (es sei denn, Microsoft Defender Antivirus wurde deinstalliert). Dies ist der Grund: <p>Microsoft Defender Antivirus sollte weiterhin installiert werden, ist aber wahrscheinlich an diesem Punkt des Migrationsprozesses deaktiviert.<p> Wenn eine Antiviren-/Antischadsoftwarelösung installiert ist, die nicht von Microsoft stammt, und die Clients noch nicht in Defender für Endpunkt integriert sind, wird Microsoft Defender Antivirus automatisch deaktiviert. <p>Wenn die Clientendpunkte später in Defender für Endpunkt integriert sind und diese Endpunkte eine Antivirenlösung ausführen, die nicht von Microsoft ist, wechselt Microsoft Defender Antivirus in den passiven Modus. <p>Wenn die nicht von Microsoft stammende Antivirenlösung deinstalliert wird, wechselt Microsoft Defender Antivirus automatisch in den aktiven Modus.  |
|Windows-Server     | Auf Windows Server müssen Sie Microsoft Defender Antivirus neu installieren und manuell auf den passiven Modus festlegen. Dies ist der Grund: <p>Wenn auf Windows Servern ein Nicht-Microsoft-Antivirus-/Antischadsoftware installiert ist, können Microsoft Defender Antivirus nicht zusammen mit der Antivirenlösung ausgeführt werden, die nicht von Microsoft stammt. In diesen Fällen wird Microsoft Defender Antivirus deaktiviert oder manuell deinstalliert. <p>Führen Sie die folgenden Schritte aus, um Microsoft Defender Antivirus auf Windows Server neu zu installieren oder zu aktivieren: <p>- [Legen Sie "DisableAntiSpyware" auf Windows Server auf "false"](#set-disableantispyware-to-false-on-windows-server) fest (nur bei Bedarf)<br/>- [Neuinstallation von Microsoft Defender Antivirus auf Windows Server](#reinstall-microsoft-defender-antivirus-on-windows-server)<br/>- [Festlegen Microsoft Defender Antivirus auf den passiven Modus auf Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)       |


Weitere Informationen zu Microsoft Defender Antivirus-Zuständen mit nicht von Microsoft stammendem Antivirusschutz finden Sie unter [Microsoft Defender Antivirus Kompatibilität.](microsoft-defender-antivirus-compatibility.md)

### <a name="set-disableantispyware-to-false-on-windows-server"></a>DisableAntiSpyware auf Windows Server auf "false" festlegen

Der [Registrierungsschlüssel "DisableAntiSpyware"](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wurde in der Vergangenheit verwendet, um Microsoft Defender Antivirus zu deaktivieren und ein anderes Antivirenprodukt wie McAfee, Symantec oder andere bereitzustellen. **Im Allgemeinen sollten Sie diesen Registrierungsschlüssel nicht auf Ihren Windows Geräten und Endpunkten haben;** Wenn *Sie* dies jedoch `DisableAntiSpyware` konfiguriert haben, wird folgendermaßen der Wert auf "false" festgelegt:

1. Öffnen Sie auf Ihrem Windows Servergerät den Registrierungs-Editor.

2. Navigieren Sie zu `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.

3. Suchen Sie in diesem Ordner nach einem DWORD-Eintrag namens **DisableAntiSpyware.**
   - Wenn dieser Eintrag nicht angezeigt wird, sind Sie alle festgelegt.
   - Wenn **"DisableAntiSpyware"** angezeigt wird, fahren Sie mit Schritt 4 fort.

4. Klicken Sie mit der rechten Maustaste auf "DisableAntiSpyware DWORD", und wählen Sie dann **"Ändern"** aus.

5. Legen Sie den Wert auf `0` . (Mit dieser Aktion wird der Wert des Registrierungsschlüssels auf *"false"* festgelegt.)

> [!TIP]
> Weitere Informationen zu diesem Registrierungsschlüssel finden Sie unter [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware).

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Neuinstallation Microsoft Defender Antivirus auf Windows Server

> [!IMPORTANT]
> Das folgende Verfahren gilt nur für Endpunkte oder Geräte, auf denen die folgenden Versionen von Windows ausgeführt werden:
> - Windows Server 2019
> - Windows Server, Version 1803 (nur Core-Modus)
> - Windows Server 2016 (siehe den folgenden Abschnitt: [Verwenden Sie Windows Server 2016?](#are-you-using-windows-server-2016))

1. Öffnen Sie als lokaler Administrator auf dem Endpunkt oder Gerät Windows PowerShell.

2. Führen Sie die folgenden PowerShell-Cmdlets aus: <br/>   

   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <p>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
 
   Bei Verwendung des DISM-Befehls in einer Tasksequenz mit PS ist der folgende Pfad zu cmd.exe erforderlich.
   Beispiel:<br/>
   
   `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<p>
   `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Verwenden Sie das folgende PowerShell-Cmdlet, um zu überprüfen, ob Microsoft Defender Antivirus ausgeführt wird: <br/>
   `Get-Service -Name windefend`

   Suchen Sie nach dem Status *"Ausführen".*

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Festlegen Microsoft Defender Antivirus auf den passiven Modus auf Windows Server

1. Öffnen Sie den Registrierungs-Editor, und navigieren Sie dann zu <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Bearbeiten (oder erstellen) Sie einen DWORD-Eintrag namens **ForcePassiveMode,** und geben Sie die folgenden Einstellungen an:

   - Legen Sie den DWORD-Wert auf **1** fest.
   - Wählen Sie unter **Basis** die Option **Hexadezimal** aus

> [!NOTE]
> Nach dem Onboarding in Defender für Endpunkt müssen Sie möglicherweise Microsoft Defender Antivirus auf Windows Server auf den passiven Modus festlegen.

### <a name="are-you-using-windows-server-2016"></a>Verwenden Sie Windows Server 2016?

Wenn Endpunkte Windows Server 2016 ausgeführt werden, können Sie Microsoft Defender Antivirus nicht zusammen mit einer Antiviren-/Antischadsoftwarelösung ausführen, die nicht von Microsoft bereitgestellt wird. Microsoft Defender Antivirus können auf Windows Server 2016 nicht im passiven Modus ausgeführt werden. In diesem Fall müssen Sie die nicht von Microsoft stammende Antiviren-/Antischadsoftwarelösung deinstallieren und stattdessen Microsoft Defender Antivirus installieren/aktivieren. Weitere Informationen finden Sie unter [Antivirus-Lösungskompatibilität mit Defender für Endpunkt.](microsoft-defender-antivirus-compatibility.md)

Wenn Sie Windows Server 2016 verwenden und Probleme beim Aktivieren von Microsoft Defender Antivirus haben, führen Sie die folgenden Schritte aus:

1. Öffnen Sie PowerShell auf dem Gerät als Administrator.

2. Geben Sie das folgende PowerShell-Cmdlet ein: `mpcmdrun -wdenable`

> [!TIP]
> Weitere Informationen finden Sie unter [Microsoft Defender Antivirus auf Windows Server.](microsoft-defender-antivirus-on-windows-server.md)

## <a name="configure-defender-for-endpoint"></a>Konfigurieren von Defender für Endpunkt

Dieser Schritt des Migrationsprozesses umfasst die Konfiguration Microsoft Defender Antivirus für Ihre Endpunkte. Es wird empfohlen, Intune zu verwenden. Sie können jedoch eine der In der folgenden Tabelle aufgeführten Methoden verwenden:

|Methode  |Vorgehensweise  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**HINWEIS:** Intune ist jetzt Teil von Microsoft Endpoint Manager. | 1. Wechseln Sie zum [Microsoft Endpoint Manager Admin Center,](https://go.microsoft.com/fwlink/?linkid=2109431) und melden Sie sich an.<p> 2. Wählen Sie  >  **Gerätekonfigurationsprofile aus,** und wählen Sie dann den Profiltyp aus, den Sie konfigurieren möchten. Wenn Sie noch keinen Profiltyp für **Geräteeinschränkungen** erstellt haben oder einen neuen erstellen möchten, lesen Sie die Informationen unter [Konfigurieren von Einstellungen für Geräteeinschränkungen in Microsoft Intune](/intune/device-restrictions-configure).<p> 3. Wählen Sie **Eigenschaften** und dann **Konfigurationseinstellungen aus: Bearbeiten**.<p> 4. Erweitern **Sie Microsoft Defender Antivirus**. <p> 5. Aktivieren Sie den über **die Cloud bereitgestellten Schutz.**<p> 6. Wählen Sie in der **Dropdownliste "Benutzer vor Beispielübermittlung auffordern"** die Option **"Alle Beispiele automatisch senden"** aus.<p> 7. Wählen Sie im Dropdownmenü **"Potenziell unerwünschte Anwendungen erkennen"** die Option **"Aktivieren"** oder **"Überwachen"** aus.<p> 8. Wählen Sie **"Überprüfen" + "Speichern"** und dann **"Speichern"** aus.<p>**TIPP:** Weitere Informationen zu Intune-Geräteprofilen, einschließlich der Erstellung und Konfiguration ihrer Einstellungen, finden Sie unter [Was sind Microsoft Intune Geräteprofile?](/intune/device-profiles).|
|Systemsteuerung in Windows     |Folgen Sie den Anweisungen hier: [Aktivieren Sie Microsoft Defender Antivirus](/mem/intune/user-help/turn-on-defender-windows). <p>**HINWEIS:** In einigen Versionen *von* Windows werden möglicherweise *Windows Defender Antivirus* anstelle von Microsoft Defender Antivirus angezeigt.        |
|[Erweiterte Gruppenrichtlinienverwaltung](/microsoft-desktop-optimization-pack/agpm/) <br/>oder<br/>[Gruppenrichtlinien-Verwaltungskonsole](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  | 1. Wechseln Sie zu Administrative Vorlagen für die **Computerkonfiguration**  >    >  **Windows Komponenten**  >  **Microsoft Defender Antivirus**. <p> 2. Suchen Sie nach einer Richtlinie namens **"Microsoft Defender Antivirus deaktivieren".**<p> 3. Wählen Sie **"Richtlinieneinstellung bearbeiten"** aus, und stellen Sie sicher, dass die Richtlinie deaktiviert ist. Diese Aktion aktiviert Microsoft Defender Antivirus. <p>**HINWEIS:** In einigen Versionen *von* Windows werden möglicherweise *Windows Defender Antivirus* anstelle von Microsoft Defender Antivirus angezeigt. |

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>Hinzufügen von Microsoft Defender für Endpunkt zur Ausschlussliste für Ihre vorhandene Lösung

Dieser Schritt des Einrichtungsprozesses umfasst das Hinzufügen von Defender für Endpunkt zur Ausschlussliste für Ihre vorhandene Endpunktschutzlösung und alle anderen Sicherheitsprodukte, die Ihre Organisation verwendet. 

> [!TIP]
> Hilfe beim Konfigurieren von Ausschlüssen finden Sie in der Dokumentation Ihres Lösungsanbieters.

Welche spezifischen Ausschlüsse konfiguriert werden müssen, hängt davon ab, welche Version von Windows Ihre Endpunkte oder Geräte ausgeführt werden, und werden in der folgenden Tabelle aufgeführt:

|Os |Ausschlüsse |
|--|--|
|Windows 10, Version [1803](/windows/release-health/status-windows-10-1803) oder höher (Siehe [Windows 10 Versionsinformationen)](/windows/release-health/release-information)<p>Windows 10, Version 1703 oder 1709 mit [installierter KB4493441](https://support.microsoft.com/help/4493441) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Server, Version 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<p>  |
|[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <p>[Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<p>**HINWEIS:** Das Überwachen temporärer Hostdateien 6\45 kann unterschiedliche nummerierte Unterordner sein. <p>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Hinzufügen ihrer vorhandenen Lösung zur Ausschlussliste für Microsoft Defender Antivirus

Während dieses Schritts des Setupprozesses fügen Sie Ihre vorhandene Lösung der Microsoft Defender Antivirus Ausschlussliste hinzu. Sie können aus mehreren Methoden auswählen, um Ihre Ausschlüsse Microsoft Defender Antivirus hinzuzufügen, wie in der folgenden Tabelle aufgeführt:

|Methode | Vorgehensweise|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**HINWEIS:** Intune ist jetzt Teil von Microsoft Endpoint Manager. | 1. Wechseln Sie zum [Microsoft Endpoint Manager Admin Center,](https://go.microsoft.com/fwlink/?linkid=2109431) und melden Sie sich an.<p> 2. Wählen Sie  >  **Gerätekonfigurationsprofile aus,** und wählen Sie dann das Profil aus, das Sie konfigurieren möchten.<p> 3. Wählen Sie unter **"Verwalten"** die Option **"Eigenschaften" aus.**<p> 4. **Konfigurationseinstellungen auswählen: Bearbeiten**.<p> 5. Erweitern Sie **Microsoft Defender Antivirus** und dann **Microsoft Defender Antivirus Ausschlüsse.**<p> 6. Geben Sie die Dateien und Ordner, Erweiterungen und Prozesse an, die von Microsoft Defender Antivirus Scans ausgeschlossen werden sollen. Eine Referenz finden Sie unter [Microsoft Defender Antivirus Ausschlüsse.](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<p> 7. Wählen Sie **"Überprüfen" und "Speichern"** und dann **"Speichern"** aus.  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) | 1. Wechseln Sie mithilfe der [Configuration Manager-Konsole](/mem/configmgr/core/servers/manage/admin-console)zu **Ressourcen und Compliance** Endpoint Protection Richtlinien für  >    >  **Antischadsoftware,** und wählen Sie dann die Richtlinie aus, die Sie ändern möchten. <p> 2. Geben Sie Ausschlusseinstellungen für Dateien und Ordner, Erweiterungen und Prozesse an, die von Microsoft Defender Antivirus Scans ausgeschlossen werden sollen. |
|[Group Policy-Objekt](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](https://technet.microsoft.com/library/cc731212.aspx)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.<p> 2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen** aus.<p> 3. Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Ausschlüsse.**<br/>**HINWEIS:** In einigen Versionen *von* Windows werden möglicherweise *Windows Defender Antivirus* anstelle von Microsoft Defender Antivirus angezeigt.<p> 4. Doppelklicken Sie auf die Einstellung **"Pfadausschlüsse",** und fügen Sie die Ausschlüsse hinzu.<br/>- Legen Sie die Option auf **"Aktiviert"** fest.<br/>- Wählen Sie im Abschnitt **"Optionen"** die Option **"Anzeigen" aus.**<br/>– Geben Sie jeden Ordner in einer eigenen Zeile unter der Spalte **"Wertname"** an.<br/>– Wenn Sie eine Datei angeben, müssen Sie einen vollqualifizierten Pfad zu der Datei eingeben, einschließlich Laufwerkbuchstabe, Ordnerpfad, Dateiname und Erweiterung. Geben Sie **0** in die Spalte **Wert** ein.<p> 5. Wählen Sie **OK** aus.<p> 6. Doppelklicken Sie auf die Einstellung **"Erweiterungsausschlüsse",** und fügen Sie die Ausschlüsse hinzu.<br/>- Legen Sie die Option auf **"Aktiviert"** fest.<br/>- Wählen Sie im Abschnitt **"Optionen"** die Option **"Anzeigen" aus.**<br/>– Geben Sie jede Dateierweiterung in eine eigene Zeile unter der Spalte **"Wertname"** ein.  Geben Sie **0** in die Spalte **Wert** ein.<p> 7. Wählen Sie **OK** aus. |
|Lokales Gruppenrichtlinienobjekt |1. Öffnen Sie auf dem Endpunkt oder Gerät den Editor für lokale Gruppenrichtlinien. <p>2. Wechseln Sie zu Administrative Vorlagen für die **Computerkonfiguration**  >    >  **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Ausschlüssen.**<p>**HINWEIS:** In einigen Versionen *von* Windows werden möglicherweise *Windows Defender Antivirus* anstelle von Microsoft Defender Antivirus angezeigt.<p>3. Geben Sie Pfad- und Prozessausschlüsse an. |
|Registrierungsschlüssel |1. Exportieren Sie den folgenden Registrierungsschlüssel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<p>2. Importieren Sie den Registrierungsschlüssel. Im Folgenden zwei Beispiele:<br/>- Lokaler Pfad: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>– Netzwerkfreigabe: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

### <a name="keep-the-following-points-about-exclusions-in-mind"></a>Beachten Sie die folgenden Punkte zu Ausschlüssen.

Wenn Sie [Ausschlüsse zu Microsoft Defender Antivirus Scans](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)hinzufügen, sollten Sie Pfad- und Prozessausschlüsse hinzufügen. 

Beachten Sie die folgenden Punkte:

- *Path exclusions* exclude specific files and whatever those files access.
- *Prozessausschlüsse* schließen alles aus, was ein Prozess berührt, schließt aber nicht den Prozess selbst aus.
- Listen Sie Ihre Prozessausschlüsse unter Verwendung ihres vollständigen Pfads und nicht nur anhand ihres Namens auf. (Die methode nur für den Namen ist weniger sicher.)
- Wenn Sie jede ausführbare Datei (.exe) sowohl als Pfadausschluss als auch als Prozessausschluss auflisten, werden der Prozess und alles, was er berührt, ausgeschlossen.


## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Einrichten von Gerätegruppen, Gerätesammlungen und Organisationseinheiten

Gerätegruppen, Gerätesammlungen und Organisationseinheiten ermöglichen Es Ihrem Sicherheitsteam, Sicherheitsrichtlinien effizient und effektiv zu verwalten und zuzuweisen. In der folgenden Tabelle werden die einzelnen Gruppen und ihre Konfiguration beschrieben. Ihre Organisation verwendet möglicherweise nicht alle drei Sammlungstypen.

| Sammlungstyp | Vorgehensweise |
|--|--|
|[Gerätegruppen](/microsoft-365/security/defender-endpoint/machine-groups) (früher als *Computergruppen* bezeichnet) ermöglichen Es Ihrem Sicherheitsteam, Sicherheitsfunktionen zu konfigurieren, z. B. automatische Untersuchung und Wartung.<p>Gerätegruppen eignen sich auch zum Zuweisen des Zugriffs auf diese Geräte, damit Ihr Sicherheitsteam bei Bedarf Korrekturmaßnahmen ergreifen kann. <p>Gerätegruppen werden im [Microsoft Defender Security Center](microsoft-defender-security-center.md)erstellt. |1. Wechseln Sie zum Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<p>2. Wählen Sie im Navigationsbereich auf der linken Seite **Einstellungen**  >    >  **Berechtigungsgerätegruppen** aus.  <p>3. Wählen Sie **+ Gerätegruppe hinzufügen** aus.<p>4. Geben Sie einen Namen und eine Beschreibung für die Gerätegruppe an.<p>5. Wählen Sie in der Liste **der Automatisierungsebenen** eine Option aus. (Wir empfehlen **"Vollständig" – Bedrohungen automatisch beheben.)** Weitere Informationen zu den verschiedenen Automatisierungsebenen finden Sie unter "Beheben von [Bedrohungen".](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<p>6. Geben Sie Bedingungen für eine übereinstimmungsregel an, um zu bestimmen, welche Geräte zur Gerätegruppe gehören. Sie können beispielsweise eine Domäne, Betriebssystemversionen oder sogar [Gerätetags](/microsoft-365/security/defender-endpoint/machine-tags)auswählen.<p>7. Geben Sie auf der Registerkarte **"Benutzerzugriff"** Rollen an, die Zugriff auf die Geräte haben sollen, die in der Gerätegruppe enthalten sind. <p>8. Wählen Sie **"Fertig" aus.** |
|[Gerätesammlungen](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) ermöglichen Es Ihrem Sicherheitsteam, Anwendungen zu verwalten, Complianceeinstellungen bereitzustellen oder Softwareupdates auf den Geräten in Ihrer Organisation zu installieren.<p>Gerätesammlungen werden mit configuration [Manager](/mem/configmgr/)erstellt. |Führen Sie die Schritte unter [Erstellen einer Auflistung](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create)aus. |
|[Organisationseinheiten](/azure/active-directory-domain-services/create-ou) ermöglichen es Ihnen, Objekte wie Benutzerkonten, Dienstkonten oder Computerkonten logisch zu gruppieren. Sie können dann Administratoren bestimmten Organisationseinheiten zuweisen und Gruppenrichtlinien anwenden, um gezielte Konfigurationseinstellungen zu erzwingen.<p> Organisationseinheiten sind in [Azure Active Directory Domain Services](/azure/active-directory-domain-services)definiert. | Führen Sie die Schritte unter [Create an Organizational Unit in an Azure Active Directory Domain Services managed domain](/azure/active-directory-domain-services/create-ou)aus. |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Konfigurieren von Antischadsoftwarerichtlinien und Echtzeitschutz

Konfigurieren Sie mit configuration Manager und Ihren Gerätesammlungen Ihre Antischadsoftwarerichtlinien.

- Weitere Informationen finden Sie unter [Erstellen und Bereitstellen von Richtlinien für Antischadsoftware für Endpoint Protection in Configuration Manager.](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- Während Sie Ihre Richtlinien für Antischadsoftware erstellen und konfigurieren, überprüfen Sie die [Echtzeitschutzeinstellungen,](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) und [aktivieren Sie "Bei erster Anzeige blockieren".](configure-block-at-first-sight-microsoft-defender-antivirus.md)

> [!TIP]
> Sie können die Richtlinien bereitstellen, bevor die Geräte Ihrer Organisation integriert sind.

## <a name="next-step"></a>Nächster Schritt

**Herzlichen Glückwunsch!** Sie haben die Einrichtungsphase des [Umstiegs auf Defender für Endpunkt](switch-to-microsoft-defender-migration.md#the-migration-process)abgeschlossen!

- [Fahren Sie mit Phase 3 fort: Onboarding in Defender für Endpunkt](switch-to-microsoft-defender-onboard.md)
