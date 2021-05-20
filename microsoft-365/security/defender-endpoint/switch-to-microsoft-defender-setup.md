---
title: Wechseln zu Microsoft Defender for Endpoint – Setup
description: Phase 2, der Einrichtungsprozess, beim Wechsel zu Microsoft Defender for Endpoint.
keywords: Migration, Microsoft Defender for Endpoint, edr, Windows Defender
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
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: e8abf10bd036b5e6e76d08e86ab4963629d2f994
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537991"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Wechseln zu Microsoft Defender for Endpoint – Phase 2: Setup

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Phase 1: Vorbereiten](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Phase 1: Vorbereiten](switch-to-microsoft-defender-prepare.md) |![Phase 2: Einrichten](images/phase-diagrams/setup.png)<br/>Phase 2: Einrichten |[![Phase 3: Onboard3](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Phase 3: Onboarding](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
||*Sie sind hier!* | |

**Willkommen bei der Setupphase des [Wechsels zu Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)**. Diese Phase umfasst die folgenden Schritte:

1. [Installieren/Aktivieren Microsoft Defender Antivirus auf Ihren Endpunkten](#reinstallenable-microsoft-defender-antivirus-on-your-endpoints).

2. [Konfigurieren von Defender für Endpoint](#configure-defender-for-endpoint).

3. [Fügen Sie Defender for Endpoint der Ausschlussliste für Ihre vorhandene Lösung hinzu.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)

4. [Fügen Sie Ihre vorhandene Lösung der Ausschlussliste für Microsoft Defender Antivirus](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus).

5. [Richten Sie Ihre Gerätegruppen, Gerätesammlungen und Organisationseinheiten ein.](#set-up-your-device-groups-device-collections-and-organizational-units)

6. [Konfigurieren von Antischalwarerichtlinien und Echtzeitschutz](#configure-antimalware-policies-and-real-time-protection).


## <a name="reinstallenable-microsoft-defender-antivirus-on-your-endpoints"></a>Neuinstallation/Microsoft Defender Antivirus auf Ihren Endpunkten

Bei bestimmten Versionen von Windows wird Microsoft Defender Antivirus wahrscheinlich deinstalliert oder deaktiviert, wenn Ihre Nicht-Microsoft-Antiviren-/Antischalwarelösung installiert wurde. Weitere Informationen finden Sie unter [Microsoft Defender Antivirus Kompatibilität](microsoft-defender-antivirus-compatibility.md).

Wenn Windows-Clients eine Nicht-Microsoft-Antiviren-/Antischalwarelösung installiert ist, wird Microsoft Defender Antivirus automatisch deaktiviert, bis diese Geräte in Defender for Endpoint onboarded werden. Wenn die Clientendpunkte in Defender for Endpoint onboarded werden, wechselt Microsoft Defender Antivirus in den passiven Modus, bis die Nicht-Microsoft-Antivirenlösung deinstalliert wird. Microsoft Defender Antivirus sollte weiterhin installiert werden, ist aber wahrscheinlich zu diesem Zeitpunkt des Migrationsprozesses deaktiviert. Wenn Microsoft Defender Antivirus nicht deinstalliert wurde, müssen Sie keine Aktionen für Ihre Windows ergreifen.

Wenn auf Windows installierte Antiviren-/Antischalsoftware nicht von Microsoft installiert ist, wird Microsoft Defender Antivirus manuell deaktiviert (falls nicht deinstalliert). Die folgenden Aufgaben tragen dazu bei, dass Microsoft Defender Antivirus auf dem Server installiert und auf den passiven Windows festgelegt wird.

- [Festlegen von DisableAntiSpyware auf false auf Windows Server](#set-disableantispyware-to-false-on-windows-server) (nur bei Bedarf)

- [Neuinstallation Microsoft Defender Antivirus auf Windows Server](#reinstall-microsoft-defender-antivirus-on-windows-server) 

- [Festlegen Microsoft Defender Antivirus passiven Modus auf Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Festlegen von DisableAntiSpyware auf false auf Windows Server

Der [DisableAntiSpyware-Registrierungsschlüssel](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wurde in der Vergangenheit verwendet, um Microsoft Defender Antivirus zu deaktivieren und ein anderes Antivirenprodukt wie McAfee, Symantec oder andere zu implementieren. Im Allgemeinen sollten Sie diesen Registrierungsschlüssel nicht auf Ihren Windows und Endpunkten verwenden. Wenn Sie jedoch konfiguriert haben, gehen Sie wie hier vor, um den Wert auf `DisableAntiSpyware` false zu setzen:

1. Öffnen Sie auf Windows Server-Gerät den Registrierungs-Editor.

2. Navigieren Sie zu `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.

3. Suchen Sie in diesem Ordner nach einem DWORD-Eintrag namens **DisableAntiSpyware**.
   - Wenn dieser Eintrag nicht zu sehen ist, sind Sie alle festgelegt.
   - Wenn **DisableAntiSpyware zu sehen ist,** fahren Sie mit Schritt 4 fort.

4. Klicken Sie mit der rechten Maustaste auf disableAntiSpyware DWORD, und wählen Sie dann **Ändern aus.**

5. Legen Sie den Wert auf `0` . (Mit dieser Aktion wird der Wert des Registrierungsschlüssels auf *false gesetzt.)*

> [!TIP]
> Weitere Informationen zu diesem Registrierungsschlüssel finden Sie unter [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware).

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Neuinstallation Microsoft Defender Antivirus auf Windows Server

> [!IMPORTANT]
> Das folgende Verfahren gilt nur für Endpunkte oder Geräte, auf der die folgenden Versionen von Windows:
> - Windows Server 2019
> - Windows Server, Version 1803 (nur Kernmodus)
> - Windows Server 2016 (siehe folgenden Abschnitt: [Verwenden Sie Windows Server 2016?](#are-you-using-windows-server-2016))

1. Öffnen Sie als lokaler Administrator auf dem Endpunkt oder Gerät Windows PowerShell.

2. Führen Sie die folgenden PowerShell-Cmdlets aus: <br/>   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <p>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
 
    > [!NOTE]
    > Wenn Sie den BEFEHL DISM innerhalb einer Tasksequenz verwenden, in der PS ausgeführt wird, ist der folgende Pfad cmd.exe erforderlich.
    > Beispiel:<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<p>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Verwenden Sie das folgende PowerShell-Cmdlet, um zu überprüfen, ob Microsoft Defender Antivirus ausgeführt wird: <br/>
   `Get-Service -Name windefend`

   Suchen Sie nach dem Status *Running*.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Festlegen Microsoft Defender Antivirus passiven Modus auf Windows Server

1. Öffnen Sie den Registrierungs-Editor, und navigieren Sie dann zu <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Bearbeiten (oder erstellen) Sie einen DWORD-Eintrag namens **ForcePassiveMode,** und geben Sie die folgenden Einstellungen an:
   - Legen Sie den Wert des DWORD auf **1 .**
   - Wählen **Sie unter Basis** die Option **Hexadezimal aus.**

> [!NOTE]
> Nach dem Onboarding in Defender for Endpoint müssen Sie möglicherweise Microsoft Defender Antivirus passiven Modus auf dem Windows festlegen.

### <a name="are-you-using-windows-server-2016"></a>Verwenden Sie Windows Server 2016?

Wenn Endpunkte ausgeführt Windows Server 2016, können Sie Microsoft Defender Antivirus nicht mit einer Nicht-Microsoft-Antiviren-/Antischalwarelösung ausführen. Microsoft Defender Antivirus kann nicht im passiven Modus auf Windows Server 2016. In diesem Fall müssen Sie die Nicht-Microsoft-Antiviren-/Antischalwarelösung deinstallieren und stattdessen Microsoft Defender Antivirus. Weitere Informationen finden Sie unter [Kompatibilität der Antiviruslösung mit Defender for Endpoint](microsoft-defender-antivirus-compatibility.md).

Wenn Sie Windows Server 2016 verwenden und Probleme beim Aktivieren Microsoft Defender Antivirus haben, verwenden Sie das folgende PowerShell-Cmdlet:

`mpcmdrun -wdenable`

Weitere Informationen finden Sie [unter Microsoft Defender Antivirus auf Windows Server](microsoft-defender-antivirus-on-windows-server.md).

## <a name="configure-defender-for-endpoint"></a>Konfigurieren von Defender for Endpoint

Dieser Schritt des Migrationsprozesses umfasst das Konfigurieren Microsoft Defender Antivirus für Ihre Endpunkte. Es wird empfohlen, Intune zu verwenden. Sie können jedoch eine der Methoden verwenden, die in der folgenden Tabelle aufgeführt sind:

|Methode  |Vorgehensweise  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**HINWEIS**: Intune ist jetzt Teil Microsoft Endpoint Manager. | 1. Wechseln Sie zum [Microsoft Endpoint Manager Admin Center,](https://go.microsoft.com/fwlink/?linkid=2109431) und melden Sie sich an.<p> 2. Wählen Sie  >  **Gerätekonfigurationsprofile** aus, und wählen Sie dann den Profiltyp aus, den Sie konfigurieren möchten. Wenn Sie noch keinen Profiltyp für Geräteeinschränkungen erstellt haben oder einen neuen erstellen möchten, lesen Sie Konfigurieren von Geräteeinschränkungseinstellungen [in Microsoft Intune](/intune/device-restrictions-configure). <p> 3. Wählen Sie **Eigenschaften** aus, und wählen Sie dann **Konfigurationseinstellungen: Bearbeiten aus.**<p> 4. Erweitern **Sie Microsoft Defender Antivirus**. <p> 5. Aktivieren des **in der Cloud übermittelten Schutzes**.<p> 6. Wählen Sie im **Dropdownmenü Benutzer vor der Beispielübermittlung** anforderen die Option **Alle Beispiele automatisch senden aus.**<p> 7. Wählen Sie im **Dropdownmenü Potenziell unerwünschte Anwendungen erkennen** die Option **Aktivieren** oder **Überwachen aus.**<p> 8. Wählen Sie **Überprüfen + Speichern** aus, und wählen Sie dann Speichern **aus.**<p>**TIPP**: Weitere Informationen zu Intune-Geräteprofilen, einschließlich der Erstellung und Konfiguration ihrer Einstellungen, finden Sie unter Was [sind Microsoft Intune Geräteprofile?](/intune/device-profiles).|
|Systemsteuerung in Windows     |Folgen Sie den Anweisungen hier: [Aktivieren sie Microsoft Defender Antivirus](/mem/intune/user-help/turn-on-defender-windows). <p>**HINWEIS**: In einigen Versionen *von Windows Defender Antivirus* *Microsoft Defender Antivirus* möglicherweise Windows.        |
|[Erweiterte Gruppenrichtlinienverwaltung](/microsoft-desktop-optimization-pack/agpm/) <br/>oder<br/>[Gruppenrichtlinien-Verwaltungskonsole](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  | 1. Wechseln Sie zu **Computerkonfiguration**  >  **Administrative Vorlagen Windows** Komponenten  >    >  **Microsoft Defender Antivirus**. <p> 2. Suchen Sie nach einer Richtlinie namens **Deaktivieren Microsoft Defender Antivirus**.<p> 3. Wählen Sie **Richtlinieneinstellung bearbeiten** aus, und stellen Sie sicher, dass die Richtlinie deaktiviert ist. Diese Aktion aktiviert Microsoft Defender Antivirus. <p>**HINWEIS**: In einigen Versionen *von Windows Defender Antivirus* *Microsoft Defender Antivirus* möglicherweise Windows. |

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>Hinzufügen von Microsoft Defender für Endpoint zur Ausschlussliste für Ihre vorhandene Lösung

Dieser Schritt des Setupprozesses umfasst das Hinzufügen von Defender for Endpoint zur Ausschlussliste für Ihre vorhandene Endpunktschutzlösung und alle anderen Sicherheitsprodukte, die Ihre Organisation verwendet. 

> [!TIP]
> Hilfe zum Konfigurieren von Ausschlüssen finden Sie in der Dokumentation Ihres Lösungsanbieters.

Die spezifischen zu konfigurierenden Ausschlüsse hängen davon ab, Windows Ihre Endpunkte oder Geräte ausgeführt werden, und sind in der folgenden Tabelle aufgeführt:

|Betriebssystem |Ausschlüsse |
|--|--|
|Windows 10, [Version 1803](/windows/release-health/status-windows-10-1803) oder höher (Siehe [Windows 10 Release information](/windows/release-health/release-information))<p>Windows 10 Version 1703 oder 1709 mit [installierter KB4493441](https://support.microsoft.com/help/4493441) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Server, Version 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<p>  |
|[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <p>[Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<p>**HINWEIS**: Die temporären Überwachungshostdateien 6\45 können unterschiedliche nummerierte Unterordner sein. <p>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Fügen Sie Ihre vorhandene Lösung der Ausschlussliste für Microsoft Defender Antivirus

In diesem Schritt des Setupprozesses fügen Sie ihre vorhandene Lösung der Microsoft Defender Antivirus hinzu. Sie können aus mehreren Methoden auswählen, um Ihre Ausschlüsse Microsoft Defender Antivirus hinzuzufügen, wie in der folgenden Tabelle aufgeführt:

|Methode | Vorgehensweise|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**HINWEIS**: Intune ist jetzt Teil Microsoft Endpoint Manager. | 1. Wechseln Sie zum [Microsoft Endpoint Manager Admin Center,](https://go.microsoft.com/fwlink/?linkid=2109431) und melden Sie sich an.<p> 2. Wählen Sie  >  **Gerätekonfigurationsprofile** aus, und wählen Sie dann das Profil aus, das Sie konfigurieren möchten.<p> 3. Wählen Sie **unter Verwalten** die Option **Eigenschaften aus.**<p> 4. Wählen Sie **Konfigurationseinstellungen aus: Bearbeiten**.<p> 5. Erweitern **Sie Microsoft Defender Antivirus**, und erweitern Sie dann **Microsoft Defender Antivirus Ausschlüsse .**<p> 6. Geben Sie die Dateien und Ordner, Erweiterungen und Prozesse an, die von den Scans Microsoft Defender Antivirus werden. Referenz finden Sie unter [Microsoft Defender Antivirus Ausschlüsse .](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<p> 7. Wählen Sie **Überprüfen + Speichern** aus, und wählen Sie dann Speichern **aus.**  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) | 1. Wechseln Sie mit der [Configuration Manager-Konsole](/mem/configmgr/core/servers/manage/admin-console)zu **Assets and Compliance**  >  **Endpoint Protection**  >  **Anmalware Policies**, und wählen Sie dann die Richtlinie aus, die Sie ändern möchten. <p> 2. Geben Sie Ausschlusseinstellungen für Dateien und Ordner, Erweiterungen und Prozesse an, die von Microsoft Defender Antivirus ausgeschlossen werden. |
|[Gruppenrichtlinienobjekt](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](https://technet.microsoft.com/library/cc731212.aspx)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann Bearbeiten **aus.**<p> 2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**<p> 3. Erweitern Sie die Struktur, **um Windows komponenten > Microsoft Defender Antivirus > zu erweitern.**<br/>**HINWEIS**: In einigen Versionen *von Windows Defender Antivirus* *Microsoft Defender Antivirus* möglicherweise Windows.<p> 4. Doppelklicken Sie auf die **Einstellung Pfadausschlüsse,** und fügen Sie die Ausschlüsse hinzu.<br/>- Legen Sie die Option auf **Aktiviert .**<br/>- Wählen Sie **im Abschnitt Optionen** die Option **Anzeigen...** aus.<br/>- Geben Sie jeden Ordner in einer eigenen Zeile unter der **Spalte Wertname** an.<br/>– Wenn Sie eine Datei angeben, stellen Sie sicher, dass Sie einen vollqualifizierten Pfad zur Datei eingeben, einschließlich Laufwerkbuchstabe, Ordnerpfad, Dateinamen und Erweiterung. Geben **Sie 0** in die **Spalte Wert** ein.<p> 5. Wählen Sie **OK aus.**<p> 6. Doppelklicken Sie auf die **Einstellung Erweiterungsausschlüsse,** und fügen Sie die Ausschlüsse hinzu.<br/>- Legen Sie die Option auf **Aktiviert .**<br/>- Wählen Sie **im Abschnitt Optionen** die Option **Anzeigen...** aus.<br/>- Geben Sie jede Dateierweiterung in einer eigenen Zeile unter der **Spalte Wertname** ein.  Geben **Sie 0** in die **Spalte Wert** ein.<p> 7. Wählen Sie **OK aus.** |
|Lokales Gruppenrichtlinienobjekt |1. Öffnen Sie auf dem Endpunkt oder Gerät den Editor für lokale Gruppenrichtlinien. <p>2. Wechseln Sie zu **Computerkonfiguration**  >  **Administrative Vorlagen** Windows  >  **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Ausschlüsse .**<p>**HINWEIS**: In einigen Versionen *von Windows Defender Antivirus* *Microsoft Defender Antivirus* möglicherweise Windows.<p>3. Geben Sie Ihre Pfad- und Prozessausschlüsse an. |
|Registrierungsschlüssel |1. Exportieren Sie den folgenden Registrierungsschlüssel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<p>2. Importieren Sie den Registrierungsschlüssel. Im Folgenden zwei Beispiele:<br/>- Lokaler Pfad: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Netzwerkfreigabe: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

### <a name="keep-the-following-points-about-exclusions-in-mind"></a>Beachten Sie die folgenden Punkte zu Ausschlüssen.

Wenn Sie [Ausschlüsse zu Microsoft Defender Antivirus hinzufügen,](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)sollten Sie Pfad- und Prozessausschlüsse hinzufügen. Beachten Sie die folgenden Punkte:

- *Pfadausschlüsse* schließen bestimmte Dateien und den Zugriff auf diese Dateien aus.

- *Prozessausschlüsse* schließen jegliche Berührungen eines Prozesses aus, schließen den Prozess selbst jedoch nicht aus.

- Listen Sie Ihre Prozessausschlüsse mithilfe des vollständigen Pfads auf, und nicht nur anhand ihres Namens. (Die Nur-Name-Methode ist weniger sicher.)

- Wenn Sie jede ausführbare Datei (.exe) sowohl als Pfadausschluss als auch als Prozessausschluss auflisten, werden der Prozess und alles, was er berührt, ausgeschlossen.


## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Einrichten von Gerätegruppen, Gerätesammlungen und Organisationseinheiten

Gerätegruppen, Gerätesammlungen und Organisationseinheiten ermöglichen Es Ihrem Sicherheitsteam, Sicherheitsrichtlinien effizient und effektiv zu verwalten und zuzuordnen. In der folgenden Tabelle werden die einzelnen Gruppen und deren Konfiguration beschrieben. Ihre Organisation verwendet möglicherweise nicht alle drei Auflistungstypen.

| Sammlungstyp | Vorgehensweise |
|--|--|
|[Gerätegruppen](/microsoft-365/security/defender-endpoint/machine-groups) (früher als Computergruppen *bezeichnet)* ermöglichen Ihrem Sicherheitsbetriebsteam die Konfiguration von Sicherheitsfunktionen, z. B. automatisierte Untersuchung und Behebung.<p>Gerätegruppen sind auch hilfreich, um diesen Geräten Zugriff zu zuweisen, damit Ihr Sicherheitsbetriebsteam bei Bedarf Abhilfemaßnahmen ausführen kann. <p>Gerätegruppen werden in der [Microsoft Defender Security Center.](microsoft-defender-security-center.md) |1. Wechseln Sie zum Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<p>2. Wählen Sie im Navigationsbereich auf der linken Seite die **Option Einstellungen**  >  **Berechtigungen**  >  **Gerätegruppen aus.**  <p>3. Wählen Sie **+ Gerätegruppe hinzufügen aus.**<p>4. Geben Sie einen Namen und eine Beschreibung für die Gerätegruppe an.<p>5. Wählen Sie in der **Liste Automatisierungsebene** eine Option aus. (Es wird **empfohlen, vollständig – Bedrohungen automatisch zu be behebung.)** Weitere Informationen zu den verschiedenen Automatisierungsebenen finden Sie unter [Wie Bedrohungen behoben werden.](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<p>6. Geben Sie Bedingungen für eine übereinstimmende Regel an, um zu bestimmen, welche Geräte zur Gerätegruppe gehören. Sie können beispielsweise eine Domäne, Betriebssystemversionen oder sogar [Gerätetags verwenden.](/microsoft-365/security/defender-endpoint/machine-tags)<p>7. Geben Sie auf der Registerkarte **Benutzerzugriff** Rollen an, die Zugriff auf die Geräte haben sollen, die in der Gerätegruppe enthalten sind. <p>8. Wählen Sie **Fertig aus.** |
|[Gerätesammlungen](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) ermöglichen Ihrem Sicherheitsbetriebsteam die Verwaltung von Anwendungen, die Bereitstellung von Kompatibilitätseinstellungen oder das Installieren von Softwareupdates auf den Geräten in Ihrer Organisation.<p>Gerätesammlungen werden mithilfe von [Configuration Manager erstellt.](/mem/configmgr/) |Führen Sie die Schritte unter [Create a collection aus.](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create) |
|[Mit Organisationseinheiten](/azure/active-directory-domain-services/create-ou) können Sie Objekte wie Benutzerkonten, Dienstkonten oder Computerkonten logisch gruppieren. Anschließend können Sie bestimmten Organisationseinheiten Administratoren zuweisen und Gruppenrichtlinien anwenden, um gezielte Konfigurationseinstellungen zu erzwingen.<p> Organisationseinheiten werden in den [Azure Active Directory definiert.](/azure/active-directory-domain-services) | Führen Sie die Schritte unter [Create an Organizational Unit in an Azure Active Directory Domain Services managed domain aus.](/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Konfigurieren von Antischalwarerichtlinien und Echtzeitschutz

Konfigurieren Sie mithilfe von Configuration Manager und Ihren Gerätesammlungen Die Antischalwarerichtlinien.

- Weitere Informationen finden Sie unter Create [and deploy anmalware policies for Endpoint Protection in Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies).

- Während Sie Ihre Antischalwarerichtlinien erstellen und [](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) konfigurieren, überprüfen Sie unbedingt die Echtzeitschutzeinstellungen, und aktivieren Sie blocken Sie [beim ersten Blick.](configure-block-at-first-sight-microsoft-defender-antivirus.md)

> [!TIP]
> Sie können die Richtlinien vor den Geräten Ihrer Organisation auf onboarded bereitstellen.

## <a name="next-step"></a>Nächster Schritt

**Herzlichen Glückwunsch!** Sie haben die Setupphase des [Wechsels zu Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)! abgeschlossen.

- [Fahren Sie mit Phase 3: Onboarding zu Defender for Endpoint fort.](switch-to-microsoft-defender-onboard.md)
