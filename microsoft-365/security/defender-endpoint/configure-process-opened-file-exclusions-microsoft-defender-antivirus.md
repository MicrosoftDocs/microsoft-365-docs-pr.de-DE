---
title: Konfigurieren von Ausschlüssen für Dateien, die von bestimmten Prozessen geöffnet werden
description: Sie können Dateien von Scans ausschließen, wenn sie von einem bestimmten Prozess geöffnet wurden.
keywords: Microsoft Defender Antivirus, Prozess, Ausschluss, Dateien, Scans
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 0470f4f03ba5fd6fc768a1e652f51b8c44207107
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925555"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>Konfigurieren von Ausschlüssen für Dateien, die von Prozessen geöffnet werden


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können Dateien, die von bestimmten Prozessen geöffnet wurden, von Microsoft Defender Antivirus Scans ausschließen. Informationen zum [Definieren von Ausschlüssen](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) finden Sie unter Empfehlungen, bevor Sie Ihre Ausschlusslisten definieren.

In diesem Artikel wird beschrieben, wie Ausschlusslisten konfiguriert werden. 

## <a name="examples-of-exclusions"></a>Beispiele für Ausschlüsse

|Ausschluss | Beispiel |
|---|---|
|Jede Datei auf dem Computer, die von einem beliebigen Prozess mit einem bestimmten Dateinamen geöffnet wird | Durch angabe `test.exe` würden Dateien ausgeschlossen, die geöffnet werden von: <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|Jede Datei auf dem Computer, die von einem Beliebigen Prozess unter einem bestimmten Ordner geöffnet wird | Durch angabe `c:\test\sample\*` würden Dateien ausgeschlossen, die geöffnet werden von:<br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|Jede Datei auf dem Computer, die von einem bestimmten Prozess in einem bestimmten Ordner geöffnet wird | Angeben `c:\test\process.exe` würde Dateien ausschließen, die nur von `c:\test\process.exe` |


Wenn Sie der Prozessausschlussliste einen Prozess hinzufügen, werden von Microsoft Defender Antivirus keine dateien gescannt, die von diesem Prozess geöffnet wurden, unabhängig davon, wo sich die Dateien befinden. Der Prozess selbst wird jedoch überprüft, es sei denn, er wurde auch der [Dateiausschlussliste](configure-extension-file-exclusions-microsoft-defender-antivirus.md)hinzugefügt.

Die Ausschlüsse gelten nur für [Always-On-Echtzeitschutz und -Überwachung.](configure-real-time-protection-microsoft-defender-antivirus.md) Sie gelten nicht für geplante scans oder On-Demand-Scans.

Änderungen, die mit der Gruppenrichtlinie an den Ausschlusslisten vorgenommen **wurden, werden** in den Listen in der [Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md)angezeigt. Änderungen an der Windows-Sicherheit App werden jedoch nicht in den Gruppenrichtlinienlisten **angezeigt.**

Sie können die Listen für Ausschlüsse in Gruppenrichtlinien, Microsoft Endpoint Configuration Manager, Microsoft Intune und mit der Windows-Sicherheit-App hinzufügen, entfernen und überprüfen, und Sie können Platzhalter verwenden, um die Listen weiter anzupassen.

Sie können auch PowerShell-Cmdlets und WMI verwenden, um die Ausschlusslisten zu konfigurieren, einschließlich der Überprüfung Ihrer Listen.

Standardmäßig werden lokale Änderungen, die an den Listen vorgenommen werden (von Benutzern mit Administratorrechten; Änderungen, die mit PowerShell und WMI vorgenommen wurden) mit den Listen zusammengeführt, die durch Gruppenrichtlinien, Configuration Manager oder Intune definiert (und bereitgestellt) werden. Bei Konflikten haben die Gruppenrichtlinienlisten Vorrang.

Sie können [konfigurieren, wie lokal und global definierte Ausschlusslisten zusammengeführt werden,](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) damit lokale Änderungen verwaltete Bereitstellungseinstellungen außer Kraft setzen können.

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>Konfigurieren der Liste der Ausschlüsse für Dateien, die von angegebenen Prozessen geöffnet werden

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Verwenden sie Microsoft Intune, um Dateien, die von angegebenen Prozessen geöffnet wurden, von Überprüfungen auszuschließen.

Für mehr Details lesen Sie [Konfigurieren von Einstellungen für Geräteeinschränkungen in Microsoft Intune](/intune/device-restrictions-configure) und [Einstellungen für Microsoft Defender Antivirus-Geräteeinschränkungen für Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Verwenden sie Microsoft Endpoint Manager, um Dateien, die von angegebenen Prozessen geöffnet wurden, von Überprüfungen auszuschließen.

Weitere Informationen zum Konfigurieren von Microsoft Endpoint Manager (current branch) finden Sie unter Erstellen und Bereitstellen von Richtlinien für [Antischadsoftware: Ausschlusseinstellungen.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Verwenden von Gruppenrichtlinien zum Ausschließen von Dateien, die von angegebenen Prozessen von Überprüfungen geöffnet wurden

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und klicken Sie auf **"Administrative Vorlagen".**

3. Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Ausschlüsse.**

4. Doppelklicken Sie auf **"Prozessausschlüsse",** und fügen Sie die Ausschlüsse hinzu:

    1. Legen Sie die Option auf **"Aktiviert"** fest.
    2. Klicken Sie im Abschnitt **"Optionen"** auf **"Anzeigen".**
    3. Geben Sie jeden Prozess in einer eigenen Zeile unter der Spalte **Wertname** ein. In der Beispieltabelle finden Sie die verschiedenen Arten von Prozessausschlüssen.  Geben Sie 0 in die **Spalte Wert** für alle Prozesse ein. 

5. Klicken Sie auf **OK**.

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Verwenden von PowerShell-Cmdlets zum Ausschließen von Dateien, die von angegebenen Prozessen von Überprüfungen geöffnet wurden

Die Verwendung von PowerShell zum Hinzufügen oder Entfernen von Ausschlüssen für Dateien, die von Prozessen geöffnet wurden, erfordert die Verwendung einer Kombination von drei Cmdlets mit dem `-ExclusionProcess` Parameter. Die Cmdlets befinden sich alle im [Defender-Modul.](/powershell/module/defender/)

Das Format für die Cmdlets lautet:

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

Folgende Werte sind \<cmdlet> zulässig:

|Konfigurationsaktion | PowerShell-Cmdlet |
|---|---|
|Erstellen oder Überschreiben der Liste | `Set-MpPreference` |
|Zur Liste hinzufügen | `Add-MpPreference` |
|Entfernen von Elementen aus der Liste | `Remove-MpPreference` |

>[!IMPORTANT]
>Wenn Sie eine Liste erstellt haben, entweder mit `Set-MpPreference` oder `Add-MpPreference` , überschreibt die verwendung des `Set-MpPreference` Cmdlets erneut die vorhandene Liste.

Der folgende Codeausschnitt würde beispielsweise dazu führen, dass Microsoft Defender AV-Scans alle Dateien ausschließen, die vom angegebenen Prozess geöffnet werden:

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwalten von Antivirus mit PowerShell-Cmdlets und [Microsoft Defender Antivirus Cmdlets.](/powershell/module/defender)

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Verwenden Windows Management Instruction (WMI) zum Ausschließen von Dateien, die von angegebenen Prozessen von Überprüfungen geöffnet wurden

Verwenden Sie die Methoden [ **"Set",** **"Add"** und **"Remove"** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
ExclusionProcess
```

Die Verwendung von **"Festlegen",** **"Hinzufügen"** und **"Entfernen"** entspricht ihren Entsprechungen in PowerShell: `Set-MpPreference` , und `Add-MpPreference` `Remove-MpPreference` .

Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Verwenden der Windows-Sicherheit-App zum Ausschließen von Dateien, die von angegebenen Prozessen geöffnet wurden, von Überprüfungen

Anweisungen finden [Sie unter Hinzufügen von Ausschlüssen in der Windows-Sicherheit-App.](microsoft-defender-security-center-antivirus.md)

## <a name="use-wildcards-in-the-process-exclusion-list"></a>Verwenden von Platzhaltern in der Prozessausschlussliste

Die Verwendung von Platzhaltern in der Prozessausschlussliste unterscheidet sich von der Verwendung in anderen Ausschlusslisten.

Insbesondere können Sie das Fragezeichen ( ) nicht `?` verwenden, und der Sternchen - `*` ) Platzhalter kann nur am Ende eines vollständigen Pfads verwendet werden. Sie können weiterhin `%ALLUSERSPROFILE%` Umgebungsvariablen (z. B. ) als Platzhalter verwenden, wenn Sie Elemente in der Prozessausschlussliste definieren.

In der folgenden Tabelle wird beschrieben, wie die Platzhalter in der Prozessausschlussliste verwendet werden können:

|Platzhalter | Beispielverwendung | Beispielüberstimmungen |
|:---|:---|:---|
|`*` (Sternchen) <br/><br/> Ersetzt eine beliebige Anzahl von Zeichen | `C:\MyData\*` | Jede Datei, die von `C:\MyData\file.exe` |
|Umgebungsvariablen <br/><br/> Die definierte Variable wird als Pfad aufgefüllt, wenn der Ausschluss ausgewertet wird. | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | Jede Datei, die von `C:\ProgramData\CustomLogFiles\file.exe` |

## <a name="review-the-list-of-exclusions"></a>Überprüfen der Liste der Ausschlüsse

Sie können die Elemente in der Ausschlussliste mit MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure)oder der [Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md)abrufen.

Wenn Sie PowerShell verwenden, können Sie die Liste auf zwei Arten abrufen:

- Rufen Sie den Status aller Microsoft Defender Antivirus Einstellungen ab. Jede der Listen wird in separaten Zeilen angezeigt, aber die Elemente in jeder Liste werden in derselben Zeile kombiniert.
- Schreiben Sie den Status aller Einstellungen in eine Variable, und verwenden Sie diese Variable, um nur die spezifische Liste aufzurufen, an der Sie interessiert sind. Jede Verwendung `Add-MpPreference` wird in eine neue Zeile geschrieben.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>Überprüfen der Ausschlussliste mithilfe von MpCmdRun

Verwenden Sie den folgenden Befehl, um Ausschlüsse mit dem dedizierten [Befehlszeilentool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)zu überprüfen:

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> Die Überprüfung von Ausschlüssen mit MpCmdRun erfordert Microsoft Defender Antivirus CAMP-Version 4.18.1812.3 (veröffentlicht im Dezember 2018) oder höher.


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>Überprüfen Sie die Liste der Ausschlüsse zusammen mit allen anderen Microsoft Defender Antivirus-Einstellungen mithilfe von PowerShell.

Verwenden Sie das folgende Cmdlet:

```PowerShell
Get-MpPreference
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus und [Defender-Cmdlets.](/powershell/module/defender)

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>Abrufen einer bestimmten Ausschlussliste mithilfe von PowerShell

Verwenden Sie den folgenden Codeausschnitt (geben Sie jede Zeile als separaten Befehl ein); Ersetzen Sie **WDAVprefs** durch die Bezeichnung, die Sie für die Variable verwenden möchten:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus und [Defender-Cmdlets.](/powershell/module/defender)

## <a name="related-articles"></a>Verwandte Artikel

- [Konfigurieren und Überprüfen von Ausschlüssen in Microsoft Defender Antivirus Scans](configure-exclusions-microsoft-defender-antivirus.md)
- [Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateiname, Erweiterung und Ordnerspeicherort](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurieren Microsoft Defender Antivirus Ausschlüsse auf Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Häufige Fehler, die beim Festlegen von Ausschlüssen vermieden werden sollten](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus Überprüfungen und Korrekturen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
