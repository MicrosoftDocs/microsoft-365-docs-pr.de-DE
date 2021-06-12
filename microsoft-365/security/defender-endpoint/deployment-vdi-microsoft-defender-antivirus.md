---
title: Microsoft Defender Antivirus Bereitstellungshandbuch für virtuelle Desktopinfrastruktur
description: Erfahren Sie, wie Sie Microsoft Defender Antivirus in einer virtuellen Desktopumgebung bereitstellen, um ein optimales Gleichgewicht zwischen Schutz und Leistung zu erzielen.
keywords: vdi, hyper-v, vm, virtueller Computer, Windows Defender, Antivirus, AV, virtueller Desktop, RDS, Remotedesktop
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/11/2021
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ce200ca12bacc3ae8d9f7b48d36274ca54322586
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908029"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Bereitstellungshandbuch für Microsoft Defender Antivirus in einer VDI-Umgebung (Virtual Desktop Infrastructure)

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Zusätzlich zu standardmäßigen lokalen konfigurationen oder Hardwarekonfigurationen können Sie Microsoft Defender Antivirus auch in einer Remotedesktopumgebung (RDS) oder VDI-Umgebung (Virtual Desktop Infrastructure) verwenden.

Weitere Informationen zur Unterstützung von Microsoft-Remotedesktop Services und VDI finden Sie in Windows [Virtual Desktop-Dokumentation.](/azure/virtual-desktop)

Informationen zu Azure-basierten virtuellen Computern finden Sie unter [Installieren Endpoint Protection in Azure Defender.](/azure/security-center/security-center-install-endpoint-protection)

Mit der Möglichkeit, Updates auf einfachen Weise auf VMs bereitzustellen, die in VDIs ausgeführt werden, haben wir dieses Handbuch gekürzt, um uns darauf zu konzentrieren, wie Sie Updates schnell und einfach auf Ihren Computern abrufen können. Sie müssen keine goldenen Bilder mehr regelmäßig erstellen und versiegeln, da Updates auf dem Hostserver in ihre Komponentenbits erweitert und dann direkt auf die VM heruntergeladen werden, wenn sie aktiviert ist.

In diesem Leitfaden wird beschrieben, wie Sie Ihre virtuellen Computer für optimalen Schutz und optimale Leistung konfigurieren, einschließlich:

- [Einrichten einer dedizierten VDI-Dateifreigabe für Security Intelligence-Updates](#set-up-a-dedicated-vdi-file-share)
- [Zufällige geplante Scans](#randomize-scheduled-scans)
- [Verwenden von Schnellscans](#use-quick-scans)
- [Verhindern von Benachrichtigungen](#prevent-notifications)
- [Deaktivieren von Scans nach jedem Update](#disable-scans-after-an-update)
- [Scannen veralteter Computer oder Computer, die eine Weile offline waren](#scan-vms-that-have-been-offline)
- [Anwenden von Ausschlüssen](#exclusions)

Sie können auch das Whitepaper [Microsoft Defender Antivirus zur Virtuellen Desktopinfrastruktur](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)herunterladen, das sich mit dem neuen feature shared Security Intelligence Update befasst, zusammen mit Leistungstests und Anleitungen zum Testen der Antivirusleistung auf Ihrer eigenen VDI.

> [!IMPORTANT]
> Obwohl die VDI auf Windows Server 2012 oder Windows Server 2016 gehostet werden kann, sollten die virtuellen Computer (VMs) aufgrund erhöhter Schutztechnologien und -features, die in früheren Versionen von Windows 10 Windows nicht verfügbar sind, mindestens 1607 ausgeführt werden.<br/>Es gibt Leistungs- und Featureverbesserungen bei der Funktionsweise von Microsoft Defender AV auf virtuellen Computern in Windows 10 Insider Preview, Build 18323 (und höher). Wir werden in diesem Leitfaden ermitteln, ob Sie einen Insider Preview-Build verwenden müssen. wenn sie nicht angegeben ist, ist die mindest erforderliche Version für den besten Schutz und die beste Leistung Windows 10 1607.

## <a name="set-up-a-dedicated-vdi-file-share"></a>Einrichten einer dedizierten VDI-Dateifreigabe

In Windows 10, Version 1903, haben wir das feature "Shared Security Intelligence" eingeführt, das das Entpacken heruntergeladener Security Intelligence-Updates auf einem Hostcomputer auslädt und somit die vorherige CPU-, Datenträger- und Speicherressourcen auf einzelnen Computern speichert. Dieses Feature wurde zurückportiert und funktioniert jetzt in Windows 10 Version 1703 und höher. Sie können dieses Feature mit einer Gruppenrichtlinie oder PowerShell festlegen.

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a>Verwenden Von Gruppenrichtlinien zum Aktivieren des Features für die gemeinsame Sicherheitsintelligenz:

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die Gruppenrichtlinien-Verwaltungskonsole, klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **Bearbeiten.**

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**

3. Klicken Sie auf **"Administrative Vorlagen".**

4. Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Security Intelligence Updates.**

5. Doppelklicken Sie auf **"Security Intelligence-Speicherort für VDI-Clients definieren",** und legen Sie die Option auf **"Aktiviert"** fest. Ein Feld wird automatisch angezeigt.

6. Geben Sie `\\<sharedlocation\>\wdav-update` eine Eingabe ein (Hilfe zu diesem Wert finden Sie unter ["Herunterladen und Entpacken").](#download-and-unpackage-the-latest-updates)

7. Klicken Sie auf **OK**.

8. Stellen Sie das Gruppenrichtlinienobjekt für die virtuellen Computer bereit, die Sie testen möchten.

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a>Verwenden von PowerShell zum Aktivieren des Features für die gemeinsame Sicherheitsintelligenz

Verwenden Sie das folgende Cmdlet, um das Feature zu aktivieren. Sie müssen dies dann pushen, da Sie normalerweise PowerShell-basierte Konfigurationsrichtlinien auf die virtuellen Computer übertragen würden:

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

Informationen dazu finden Sie im Abschnitt ["Herunterladen und Entpacken".](#download-and-unpackage-the-latest-updates) \<shared location\>

## <a name="download-and-unpackage-the-latest-updates"></a>Herunterladen und Entpacken der neuesten Updates

Jetzt können Sie mit dem Herunterladen und Installieren neuer Updates beginnen. Wir haben unten ein PowerShell-Beispielskript für Sie erstellt. Dieses Skript ist die einfachste Möglichkeit, neue Updates herunterzuladen und für Ihre virtuellen Computer vorzubereiten. Sie sollten dann festlegen, dass das Skript zu einem bestimmten Zeitpunkt auf dem Verwaltungscomputer mithilfe einer geplanten Aufgabe ausgeführt wird (oder wenn Sie mit der Verwendung von PowerShell-Skripts in Azure, Intune oder SCCM vertraut sind, können Sie auch diese Skripts verwenden).

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

Sie können festlegen, dass eine geplante Aufgabe einmal täglich ausgeführt wird, damit die virtuellen Computer das neue Update erhalten, sobald das Paket heruntergeladen und entpackt wird. Wir empfehlen, mit einmal am Tag zu beginnen. Sie sollten jedoch damit experimentieren, die Häufigkeit zu erhöhen oder zu verringern, um die Auswirkungen zu verstehen. 

Security Intelligence-Pakete werden in der Regel alle drei bis vier Stunden veröffentlicht. Das Festlegen einer Häufigkeit von weniger als vier Stunden wird nicht empfohlen, da dadurch der Netzwerkaufwand auf Ihrem Verwaltungscomputer ohne Nutzen erhöht wird.

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a>Festlegen einer geplanten Aufgabe zum Ausführen des PowerShell-Skripts

1. Öffnen Sie auf dem Verwaltungscomputer das Startmenü, und geben Sie **"Aufgabenplaner" ein.** Öffnen Sie sie, und wählen Sie **"Aufgabe erstellen" aus...** im Seitenbereich.

2. Geben Sie den Namen als **Security Intelligence-Entpacker** ein. Wechseln Sie zur Registerkarte **"Trigger".** Wählen Sie **"Neu" aus...** > **Täglich,** und wählen Sie **OK**.

3. Wechseln Sie zur Registerkarte **"Aktionen".** Wählen Sie **"Neu" aus...** Geben Sie **PowerShell** in das **Feld "Programm/Skript"** ein. Geben Sie `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` das **Feld Argumente hinzufügen** ein. Wählen Sie **OK** aus.

4. Sie können bei Bedarf zusätzliche Einstellungen konfigurieren.

5. Wählen Sie **"OK"** aus, um den geplanten Vorgang zu speichern.
 
Sie können das Update manuell initiieren, indem Sie mit der rechten Maustaste auf die Aufgabe klicken und auf **"Ausführen"** klicken.

### <a name="download-and-unpackage-manually"></a>Manuelles Herunterladen und Entpacken

Wenn Sie es vorziehen, alles manuell zu tun, müssen Sie das Verhalten des Skripts folgendermaßen replizieren:

1. Erstellen Sie einen neuen Ordner im Systemstamm, der `wdav_update` zum Speichern von Intelligence-Updates aufgerufen wird, z. B. erstellen Sie den `c:\wdav_update` Ordner.

2. Erstellen eines Unterordners unter *wdav_update* mit einem GUID-Namen, z. B. `{00000000-0000-0000-0000-000000000000}`

Hier ist ein Beispiel: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`

   > [!NOTE]
   > Im Skript legen wir fest, dass die letzten 12 Ziffern der GUID das Jahr, der Monat, der Tag und die Uhrzeit sind, zu der die Datei heruntergeladen wurde, sodass jedes Mal ein neuer Ordner erstellt wird. Sie können dies ändern, sodass die Datei jedes Mal in denselben Ordner heruntergeladen wird.

3. Laden Sie ein Security Intelligence-Paket [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  in den GUID-Ordner herunter. Die Datei sollte den Namen `mpam-fe.exe` haben.

4. Öffnen Sie ein cmd-Eingabeaufforderungsfenster, und navigieren Sie zum erstellten GUID-Ordner. Verwenden  Sie den /X-Extraktionsbefehl, um die Dateien zu extrahieren, `mpam-fe.exe /X` z. B. .

   > [!NOTE]
   > Die virtuellen Computer nehmen das aktualisierte Paket immer dann auf, wenn ein neuer GUID-Ordner mit einem extrahierten Updatepaket erstellt wird oder wenn ein vorhandener Ordner mit einem neuen extrahierten Paket aktualisiert wird.

## <a name="randomize-scheduled-scans"></a>Zufällige geplante Scans

Geplante Scans werden zusätzlich zum [Echtzeitschutz und zum Scannen](configure-real-time-protection-microsoft-defender-antivirus.md)ausgeführt.

Die Startzeit des Scans selbst basiert weiterhin auf der geplanten Scanrichtlinie (**ScheduleDay**, **ScheduleTime** und **ScheduleQuickScanTime**). Die Zufälligisierung führt dazu, dass Microsoft Defender Antivirus innerhalb eines 4-Stunden-Fensters ab dem für den geplanten Scan festgelegten Zeitraum auf jedem Computer einen Scan starten.

Weitere Konfigurationsoptionen, die für geplante Scans verfügbar sind, finden Sie unter ["Planen](scheduled-catch-up-scans-microsoft-defender-antivirus.md) von Scans".

## <a name="use-quick-scans"></a>Verwenden von Schnellscans

Sie können den Typ des Scans angeben, der während eines geplanten Scans ausgeführt werden soll. Schnellscans sind der bevorzugte Ansatz, da sie so konzipiert sind, dass sie an allen Stellen suchen, an denen sich Schadsoftware befinden muss, um aktiv zu sein. Im folgenden Verfahren wird beschrieben, wie Sie Schnellscans mithilfe von Gruppenrichtlinien einrichten.

1. Wechseln Sie im Gruppenrichtlinien-Editor zu **administrativen Vorlagen**  >  **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Scannen.**

2. Wählen Sie **den Zu verwendenden Scantyp für einen geplanten Scan** aus, und bearbeiten Sie dann die Richtlinieneinstellung.

3. Legen Sie die Richtlinie auf **"Aktiviert"** fest, und wählen Sie dann unter **"Optionen"** die Option  **"Schnellscan"** aus.

4. Wählen Sie **OK** aus. 

5. Stellen Sie Ihr Gruppenrichtlinien-Objekt bereit, so wie Sie dies normalerweise tun.

## <a name="prevent-notifications"></a>Verhindern von Benachrichtigungen

Manchmal können Microsoft Defender Antivirus Benachrichtigungen an mehrere Sitzungen gesendet oder dort gespeichert werden. Um dieses Problem zu minimieren, können Sie die Microsoft Defender Antivirus Benutzeroberfläche sperren. Im folgenden Verfahren wird beschrieben, wie Sie Benachrichtigungen mit gruppenrichtlinien unterdrücken.

1. Wechseln Sie im Gruppenrichtlinien-Editor zu **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Clientschnittstelle.**

2. Wählen Sie **"Alle Benachrichtigungen unterdrücken"** aus, und bearbeiten Sie dann die Richtlinieneinstellungen. 

3. Legen Sie die Richtlinie auf **"Aktiviert"** fest, und wählen Sie dann **"OK"** aus.

4. Stellen Sie Ihr Gruppenrichtlinien-Objekt bereit, so wie Sie dies normalerweise tun.

Durch das Unterdrücken von Benachrichtigungen wird verhindert, dass Benachrichtigungen von Microsoft Defender Antivirus im Info-Center auf Windows 10 angezeigt werden, wenn Scans durchgeführt oder Korrekturmaßnahmen ausgeführt werden. Ihr Sicherheitsteam sieht jedoch die Ergebnisse der Überprüfung im [Microsoft 365 Defender-Portal.](microsoft-defender-security-center.md)

> [!TIP]
> Führen Sie einen der folgenden Schritte aus, um das Info-Center für Windows 10 zu öffnen:
> - Wählen Sie am rechten Ende der Taskleiste das Info-Center-Symbol aus.
> - Drücken Sie die Windows Logotaste + A.
> - Wischen Sie auf einem Touchscreengerät vom rechten Rand des Bildschirms ein.

## <a name="disable-scans-after-an-update"></a>Deaktivieren von Scans nach einem Update

Durch deaktivieren einer Überprüfung nach einem Update wird verhindert, dass eine Überprüfung nach Erhalt eines Updates durchgeführt wird. Sie können diese Einstellung beim Erstellen des Basisimages anwenden, wenn Sie auch einen Schnellscan ausgeführt haben. Auf diese Weise können Sie verhindern, dass der neu aktualisierte virtuelle Computer erneut eine Überprüfung durchführt (wie Sie ihn bereits beim Erstellen des Basisimages gescannt haben).

> [!IMPORTANT]
> Das Ausführen von Scans nach einem Update trägt dazu bei, dass Ihre VMs mit den neuesten Security Intelligence-Updates geschützt sind. Durch deaktivieren dieser Option wird die Schutzebene Ihrer VMs reduziert und sollte nur beim ersten Erstellen oder Bereitstellen des Basisimages verwendet werden.

1. Wechseln Sie in Ihrem Gruppenrichtlinien-Editor zu **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Security Intelligence-Updates.**

2. Wählen Sie "Scan nach Update zur **Sicherheitsintelligenz aktivieren"** aus, und bearbeiten Sie dann die Richtlinieneinstellung.

3. Legen Sie die Richtlinie auf **Deaktiviert** fest.

4. Wählen Sie **OK** aus.

5. Stellen Sie Ihr Gruppenrichtlinien-Objekt bereit, so wie Sie dies normalerweise tun.

Diese Richtlinie verhindert, dass ein Scan unmittelbar nach einem Update ausgeführt wird.

## <a name="scan-vms-that-have-been-offline"></a>Scannen von virtuellen Computern, die offline waren

1. Wechseln Sie im Gruppenrichtlinien-Editor zu **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Scannen.**

2. Wählen Sie **"Nachhol-Schnellscan** aktivieren" aus, und bearbeiten Sie dann die Richtlinieneinstellung.

3. Legen Sie die Richtlinie auf **"Aktiviert"** fest.

4. Wählen Sie **OK** aus.

5. Stellen Sie Das Gruppenrichtlinienobjekt wie gewohnt bereit.

Diese Richtlinie erzwingt eine Überprüfung, wenn der virtuelle Computer mindestens zwei aufeinanderfolgende geplante Scans verpasst hat.

## <a name="enable-headless-ui-mode"></a>Aktivieren des Headless UI-Modus

1. Wechseln Sie im Gruppenrichtlinien-Editor zu **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Clientschnittstelle.**

2. Wählen Sie **"Headless UI-Modus aktivieren"** aus, und bearbeiten Sie die Richtlinie.

3. Legen Sie die Richtlinie auf **"Aktiviert"** fest.

4. Klicken Sie auf **OK**.

5. Stellen Sie Das Gruppenrichtlinienobjekt wie gewohnt bereit.
 
Diese Richtlinie blendet die gesamte Microsoft Defender Antivirus Benutzeroberfläche von Endbenutzern in Ihrer Organisation aus.

## <a name="exclusions"></a>Ausschlüsse

Ausschlüsse können ihren Anforderungen entsprechend hinzugefügt, entfernt oder angepasst werden.

Weitere Informationen finden Sie unter [Konfigurieren Microsoft Defender Antivirus Ausschlüsse auf Windows Server.](configure-exclusions-microsoft-defender-antivirus.md)

## <a name="additional-resources"></a>Weitere Ressourcen

- [Tech Community Blog: Konfigurieren von Microsoft Defender Antivirus für nicht persistente VDI-Computer](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [TechNet-Foren auf Remotedesktopdiensten und VDI](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [SignatureDownloadCustomTask PowerShell-Skript](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)