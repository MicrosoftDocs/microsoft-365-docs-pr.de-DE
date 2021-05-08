---
title: Microsoft Defender Antivirus Bereitstellungshandbuch für virtuelle Desktopinfrastruktur
description: Erfahren Sie, wie Microsoft Defender Antivirus in einer virtuellen Desktopumgebung bereitgestellt werden, um eine optimale Balance zwischen Schutz und Leistung zu erzielen.
keywords: vdi, hyper-v, vm, virtual machine, windows defender, antivirus, av, virtual desktop, rds, remote desktop
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4ecd14e055646804d81e22da7c192988cf1e6f6f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275252"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Bereitstellungshandbuch für Microsoft Defender Antivirus in einer VDI-Umgebung (Virtual Desktop Infrastructure)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Zusätzlich zu lokalen Standardkonfigurationen oder Hardwarekonfigurationen können Sie Microsoft Defender Antivirus auch in einer Remotedesktopumgebung (RDS) oder einer virtuellen Desktopinfrastruktur (Virtual Desktop Infrastructure, VDI) verwenden.

Weitere [Windows zur Unterstützung von](/azure/virtual-desktop) Diensten und Microsoft-Remotedesktop VDI finden Sie unter Windows Virtual Desktop Documentation.

Informationen zu azurebasierten virtuellen Computern finden Sie unter [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).

Mit der Möglichkeit, Updates auf VMs, die in VDIs ausgeführt werden, einfach bereitstellen zu können, haben wir dieses Handbuch verkürzt, um uns darauf zu konzentrieren, wie Sie Updates auf Ihren Computern schnell und einfach erhalten können. Sie müssen keine goldenen Bilder mehr regelmäßig erstellen und versiegeln, da Updates in ihre Komponentenbits auf dem Hostserver erweitert und dann direkt auf den virtuellen Computer heruntergeladen werden, wenn er aktiviert ist.

In diesem Handbuch wird beschrieben, wie Sie Ihre virtuellen Computer für optimalen Schutz und optimale Leistung konfigurieren. Dazu gehören u. a.:

- [Einrichten einer dedizierten VDI-Dateifreigabe für Sicherheitsintelligenzupdates](#set-up-a-dedicated-vdi-file-share)
- [Randomisieren geplanter Scans](#randomize-scheduled-scans)
- [Verwenden von Schnellscans](#use-quick-scans)
- [Verhindern von Benachrichtigungen](#prevent-notifications)
- [Deaktivieren von Scans nach jedem Update](#disable-scans-after-an-update)
- [Überprüfen veralteter Computer oder Computer, die eine Weile offline waren](#scan-vms-that-have-been-offline)
- [Anwenden von Ausschlüssen](#exclusions)

Sie können auch das whitepaper [Microsoft Defender Antivirus on Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)herunterladen, das sich mit dem neuen Feature für das Update der gemeinsamen Sicherheitsintelligenz sowie Leistungstests und Anleitungen zum Testen der Antivirusleistung in Ihrem eigenen VDI beschäftigt.

> [!IMPORTANT]
> Obwohl der VDI auf Windows Server 2012 oder Windows Server 2016 gehostet werden kann, sollten die virtuellen Computer (VMs) mindestens Windows 10, 1607, ausgeführt werden, da die Schutztechnologien und -features in früheren Versionen von Windows nicht verfügbar sind.<br/>Es gibt Leistungs- und Funktionsverbesserungen bei der Art und Weise, wie Microsoft Defender AV auf virtuellen Computern in Windows 10 Insider Preview, Build 18323 (und höher) arbeitet. Wir identifizieren in diesem Handbuch, ob Sie einen Insider #A0 verwenden müssen. Wenn sie nicht angegeben wird, ist die mindestens erforderliche Version für den besten Schutz und die optimale Leistung Windows 10 1607.

## <a name="set-up-a-dedicated-vdi-file-share"></a>Einrichten einer dedizierten VDI-Dateifreigabe

In Windows 10, Version 1903, haben wir das Feature für gemeinsame Sicherheitsintelligenz eingeführt, das das Auspacken heruntergeladener Sicherheitsintelligenzupdates auf einen Hostcomputer auslädt, wodurch frühere CPU-, Datenträger- und Arbeitsspeicherressourcen auf einzelnen Computern gespeichert werden. Dieses Feature wurde zurückportiert und funktioniert jetzt in Windows 10 Version 1703 und höher. Sie können dieses Feature mit einer Gruppenrichtlinie oder PowerShell festlegen.

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a>Verwenden Sie Gruppenrichtlinien, um das Feature für gemeinsame Sicherheit in der Sicherheitsintelligenz zu aktivieren:

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die Gruppenrichtlinienverwaltungskonsole, klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **Bearbeiten**.

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

3. Klicken Sie **auf Administrative Vorlagen**.

4. Erweitern Sie die Struktur, **Windows komponenten**  >  **Microsoft Defender Antivirus**  >  **Security Intelligence Updates .**

5. Doppelklicken Sie **auf Speicherort der Sicherheitsintelligenz für VDI-Clients definieren,** und legen Sie dann die Option auf **Aktiviert fest.** Ein Feld wird automatisch angezeigt.

6. Geben `\\<sharedlocation\>\wdav-update` Sie ein (Hilfe zu diesem Wert finden Sie unter [Herunterladen und Auspacken](#download-and-unpackage-the-latest-updates)).

7. Klicken Sie auf **OK**.

8. Stellen Sie das Gruppenrichtlinienobjekt auf den virtuellen Computer, die Sie testen möchten.

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a>Verwenden von PowerShell zum Aktivieren des Features für gemeinsame Sicherheitsintelligenz

Verwenden Sie das folgende Cmdlet, um das Feature zu aktivieren. Sie müssen dies dann pushen, da Sie normalerweise PowerShell-basierte Konfigurationsrichtlinien auf die virtuellen Computer pushen würden:

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

Informationen dazu [finden](#download-and-unpackage-the-latest-updates) Sie im Abschnitt Herunterladen und \<shared location\> Entpacken.

## <a name="download-and-unpackage-the-latest-updates"></a>Herunterladen und Entpacken der neuesten Updates

Jetzt können Sie mit dem Herunterladen und Installieren neuer Updates beginnen. Wir haben unten ein PowerShell-Beispielskript für Sie erstellt. Dieses Skript ist die einfachste Möglichkeit, neue Updates herunterzuladen und für Ihre virtuellen Computer zu bereiten. Anschließend sollten Sie festlegen, dass das Skript zu einem bestimmten Zeitpunkt auf dem Verwaltungscomputer mithilfe einer geplanten Aufgabe ausgeführt wird (oder Wenn Sie mit der Verwendung von PowerShell-Skripts in Azure, Intune oder SCCM vertraut sind, können Sie diese Skripts auch verwenden).

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

Sie können festlegen, dass ein geplanter Vorgang einmal täglich ausgeführt wird, sodass die virtuellen Computer das neue Update erhalten, wenn das Paket heruntergeladen und entpackt wird. Wir empfehlen, einmal am Tag zu beginnen. Sie sollten jedoch mit dem Erhöhen oder Verringern der Häufigkeit experimentieren, um die Auswirkungen zu verstehen. 

Security Intelligence-Pakete werden in der Regel alle drei bis vier Stunden veröffentlicht. Das Festlegen einer Häufigkeit von weniger als vier Stunden wird nicht empfohlen, da dadurch der Netzwerkaufwand auf Dem Verwaltungscomputer ohne Nutzen erhöht wird.

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a>Festlegen eines geplanten Vorgangs zum Ausführen des PowerShell-Skripts

1. Öffnen Sie auf dem Verwaltungscomputer das Menü Start, und geben Sie **Task Scheduler ein.** Öffnen Sie sie, und wählen **Sie Aufgabe erstellen... aus.** auf der Seitenleiste.

2. Geben Sie den Namen als **Security Intelligence Unpacker ein.** Wechseln Sie zur **Registerkarte Trigger.** Wählen **Sie Neu aus...** > **Täglich**, und wählen Sie **OK aus.**

3. Wechseln Sie zur **Registerkarte Aktionen.** Wählen **Sie Neu aus...** Geben **Sie PowerShell** in das **Feld Programm/Skript** ein. Geben `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` Sie in das Feld Argumente **hinzufügen** ein. Wählen Sie **OK** aus.

4. Sie können bei Wunsch zusätzliche Einstellungen konfigurieren.

5. Wählen **Sie OK** aus, um den geplanten Vorgang zu speichern.
 
Sie können das Update manuell initiieren, indem Sie mit der rechten Maustaste auf die Aufgabe klicken und auf **Ausführen klicken.**

### <a name="download-and-unpackage-manually"></a>Manuelles Herunterladen und Entpacken

Wenn Sie es vorziehen, alles manuell auszuführen, müssen Sie das Verhalten des Skripts replizieren:

1. Erstellen Sie einen neuen Ordner im Systemstamm, der zum Speichern von Nachrichtenupdates aufgerufen wird, z. B. `wdav_update` erstellen Sie den Ordner `c:\wdav_update` .

2. Erstellen eines Unterordners *unter wdav_update* mit einem GUID-Namen, z. B. `{00000000-0000-0000-0000-000000000000}`

Hier ein Beispiel: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`

   > [!NOTE]
   > Im Skript legen wir es so fest, dass die letzten 12 Ziffern der GUID das Jahr, den Monat, den Tag und die Uhrzeit sind, zu der die Datei heruntergeladen wurde, sodass jedes Mal ein neuer Ordner erstellt wird. Sie können dies so ändern, dass die Datei jedes Mal in denselben Ordner heruntergeladen wird.

3. Laden Sie ein Security Intelligence-Paket [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  aus in den GUID-Ordner herunter. Die Datei sollte den Namen `mpam-fe.exe` haben.

4. Öffnen Sie ein Cmd-Eingabeaufforderungsfenster, und navigieren Sie zu dem erstellten GUID-Ordner. Verwenden Sie den /X-Extraktionsbefehl, um die Dateien zu extrahieren, z. B.  `mpam-fe.exe /X` .

   > [!NOTE]
   > Die virtuellen Computer nehmen das aktualisierte Paket auf, wenn ein neuer GUID-Ordner mit einem extrahierten Updatepaket erstellt wird oder wenn ein vorhandener Ordner mit einem neuen extrahierten Paket aktualisiert wird.

## <a name="randomize-scheduled-scans"></a>Randomisieren geplanter Scans

Geplante Scans werden zusätzlich zu [Echtzeitschutz und -überprüfung ausgeführt.](configure-real-time-protection-microsoft-defender-antivirus.md)

Die Startzeit des Scans selbst basiert weiterhin auf der geplanten Scanrichtlinie (**ScheduleDay**, **ScheduleTime** und **ScheduleQuickScanTime**). Die Randomisierung Microsoft Defender Antivirus, dass die Überprüfung auf jedem Computer innerhalb eines 4-Stunden-Fensters nach der für die geplante Überprüfung festgelegten Zeit gestartet wird.

Weitere [Konfigurationsoptionen für](scheduled-catch-up-scans-microsoft-defender-antivirus.md) geplante Scans finden Sie unter Planen von Scans.

## <a name="use-quick-scans"></a>Verwenden von Schnellscans

Sie können den Typ der Überprüfung angeben, die während einer geplanten Überprüfung durchgeführt werden soll. Schnelle Scans sind der bevorzugte Ansatz, da sie so konzipiert sind, dass sie an allen Stellen aussehen, an denen Schadsoftware gespeichert werden muss, um aktiv zu sein. Im folgenden Verfahren wird das Einrichten von Schnellscans mithilfe von Gruppenrichtlinien beschrieben.

1. Wechseln Sie im Gruppenrichtlinien-Editor zu **Administrative Vorlagen Windows** Komponenten  >    >  **Microsoft Defender Antivirus**  >  **Scan**.

2. Wählen **Sie Den Scantyp angeben aus, der für eine geplante** Überprüfung verwendet werden soll, und bearbeiten Sie dann die Richtlinieneinstellung.

3. Legen Sie die Richtlinie auf **Aktiviert**, und wählen Sie dann unter **Optionen** die Option **Schnellscan aus.**

4. Wählen Sie **OK** aus. 

5. Stellen Sie Ihr Gruppenrichtlinienobjekt wie üblich zur Bereitstellung.

## <a name="prevent-notifications"></a>Verhindern von Benachrichtigungen

Manchmal können Microsoft Defender Antivirus Benachrichtigungen an mehrere Sitzungen gesendet oder beibehalten werden. Um dieses Problem zu minimieren, können Sie die Benutzeroberfläche Microsoft Defender Antivirus sperren. Im folgenden Verfahren wird beschrieben, wie Benachrichtigungen mit Gruppenrichtlinien unterdrückt werden.

1. Wechseln Sie im Gruppenrichtlinien-Editor zu **Windows komponenten**  >  **Microsoft Defender Antivirus**  >  **Clientschnittstelle**.

2. Wählen **Sie Alle Benachrichtigungen unterdrücken** aus, und bearbeiten Sie dann die Richtlinieneinstellungen. 

3. Legen Sie die Richtlinie auf **Aktiviert**, und wählen Sie dann **OK aus.**

4. Stellen Sie Ihr Gruppenrichtlinienobjekt wie üblich zur Bereitstellung.

Das Unterdrücken von Benachrichtigungen verhindert, Microsoft Defender Antivirus Benachrichtigungen im Aktionscenter am Windows 10 angezeigt werden, wenn Scans durchgeführt oder Korrekturaktionen ausgeführt werden. Ihr Sicherheitsbetriebsteam sieht jedoch die Ergebnisse der Überprüfung in der Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

> [!TIP]
> Gehen Sie wie folgt vor, um Windows 10 Aktionscenter zu öffnen:
> - Wählen Sie am rechten Ende der Taskleiste das Symbol Aktionscenter aus.
> - Drücken Sie die Windows+A-Taste.
> - Wischen Sie auf einem Touchscreengerät vom rechten Rand des Bildschirms ein.

## <a name="disable-scans-after-an-update"></a>Deaktivieren von Scans nach einem Update

Durch deaktivieren eines Scans nach einem Update wird verhindert, dass nach dem Empfang eines Updates eine Überprüfung stattfindet. Sie können diese Einstellung beim Erstellen des Basisimages anwenden, wenn Sie auch einen Schnellscan ausgeführt haben. Auf diese Weise können Sie verhindern, dass der neu aktualisierte virtuelle Computer erneut eine Überprüfung durchführen kann (wie Sie ihn bereits beim Erstellen des Basisimages überprüft haben).

> [!IMPORTANT]
> Das Ausführen von Scans nach einem Update hilft Ihnen, sicherzustellen, dass Ihre virtuellen Computer mit den neuesten Security Intelligence-Updates geschützt sind. Wenn Sie diese Option deaktivieren, wird die Schutzstufe Ihrer virtuellen Computer reduziert und sollte nur beim ersten Erstellen oder Bereitstellen des Basisimages verwendet werden.

1. Wechseln Sie im Gruppenrichtlinien-Editor zu **Windows komponenten**  >  **Microsoft Defender Antivirus**  >  **Security Intelligence Updates**.

2. Wählen **Sie Scan aktivieren nach dem Update der Sicherheitsintelligenz aus,** und bearbeiten Sie dann die Richtlinieneinstellung.

3. Legen Sie die Richtlinie auf **Deaktiviert .**

4. Wählen Sie **OK** aus.

5. Stellen Sie Ihr Gruppenrichtlinienobjekt wie üblich zur Bereitstellung.

Diese Richtlinie verhindert, dass eine Überprüfung unmittelbar nach einem Update ausgeführt wird.

## <a name="scan-vms-that-have-been-offline"></a>Überprüfen von virtuellen Computer, die offline waren

1. Wechseln Sie im Gruppenrichtlinien-Editor zu Windows **komponenten**  >  **Microsoft Defender Antivirus**  >  **Scan**.

2. Wählen **Sie Nachhol-Schnellscan aktivieren aus,** und bearbeiten Sie dann die Richtlinieneinstellung.

3. Legen Sie die Richtlinie auf **Aktiviert .**

4. Wählen Sie **OK** aus.

5. Stellen Sie Ihr Gruppenrichtlinienobjekt wie gewöhnlich zur Bereitstellung.

Diese Richtlinie erzwingt eine Überprüfung, wenn der virtuelle Computer zwei oder mehr aufeinander folgende geplante Scans verpasst hat.

## <a name="enable-headless-ui-mode"></a>Aktivieren des kopflosen Benutzeroberflächenmodus

1. Wechseln Sie im Gruppenrichtlinien-Editor zu **Windows komponenten**  >  **Microsoft Defender Antivirus**  >  **Clientschnittstelle**.

2. Wählen **Sie Kopflose Benutzeroberflächenmodus aktivieren aus,** und bearbeiten Sie die Richtlinie.

3. Legen Sie die Richtlinie auf **Aktiviert .**

4. Klicken Sie auf **OK**.

5. Stellen Sie Ihr Gruppenrichtlinienobjekt wie gewöhnlich zur Bereitstellung.
 
Diese Richtlinie blendet die gesamte Microsoft Defender Antivirus von Endbenutzern in Ihrer Organisation aus.

## <a name="exclusions"></a>Ausschlüsse

Ausschlüsse können ihren Anforderungen entsprechend hinzugefügt, entfernt oder angepasst werden.

Weitere Informationen finden Sie unter [Configure Microsoft Defender Antivirus exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- [Tech Community Blog: Configuring Microsoft Defender Antivirus for non-persistent VDI machines](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [TechNet-Foren zu Remotedesktopdiensten und VDI](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [SignatureDownloadCustomTask PowerShell-Skript](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)