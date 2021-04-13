---
title: Konfigurieren von Ausschlüssen für Dateien, die von bestimmten Prozessen geöffnet werden
description: Sie können Dateien von Scans ausschließen, wenn sie von einem bestimmten Prozess geöffnet wurden.
keywords: Microsoft Defender Antivirus, Prozess, Ausschluss, Dateien, Scans
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 4a117d2743436381029d047693f81303e5908b2b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690338"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>Konfigurieren von Ausschlüssen für Dateien, die von Prozessen geöffnet werden

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können Dateien, die von bestimmten Prozessen geöffnet wurden, aus Microsoft Defender Antivirus-Scans ausschließen. Weitere [Informationen finden Sie unter Empfehlungen zum Definieren von Ausschlüssen,](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) bevor Sie Ihre Ausschlusslisten definieren.

In diesem Artikel wird beschrieben, wie Ausschlusslisten konfiguriert werden. 

## <a name="examples-of-exclusions"></a>Beispiele für Ausschlüsse

|Ausschluss | Beispiel |
|---|---|
|Jede Datei auf dem Computer, die von einem beliebigen Prozess mit einem bestimmten Dateinamen geöffnet wird | Die Angabe `test.exe` würde Dateien ausschließen, die von: <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|Jede Datei auf dem Computer, die von einem beliebigen Prozess unter einem bestimmten Ordner geöffnet wird | Die Angabe `c:\test\sample\*` würde Dateien ausschließen, die von:<br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|Jede Datei auf dem Computer, die von einem bestimmten Prozess in einem bestimmten Ordner geöffnet wird | Durch angeben `c:\test\process.exe` würden nur geöffnete Dateien ausgeschlossen. `c:\test\process.exe` |


Wenn Sie der Prozessausschlussliste einen Prozess hinzufügen, werden von Microsoft Defender Antivirus geöffnete Dateien nicht gescannt, unabhängig davon, wo sich die Dateien befinden. Der Prozess selbst wird jedoch überprüft, es sei denn, er wurde auch der Dateiausschlussliste [hinzugefügt.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

Die Ausschlüsse gelten nur für [den Immer-on-Echtzeitschutz und die Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md). Sie gelten nicht für geplante oder on-Demand-Scans.

Änderungen, die mit Gruppenrichtlinien an den Ausschlusslisten vorgenommen **wurden,** werden in den Listen in der [Windows Security App angezeigt.](microsoft-defender-security-center-antivirus.md) In der Windows-Sicherheits-App vorgenommene Änderungen **werden jedoch nicht** in den Gruppenrichtlinienlisten angezeigt.

Sie können die Listen in Gruppenrichtlinien, Microsoft Endpoint Configuration Manager, Microsoft Intune und mit der Windows-Sicherheits-App hinzufügen, entfernen und auf Ausschlüsse überprüfen, und Sie können Platzhalter verwenden, um die Listen weiter anzupassen.

Sie können auch PowerShell-Cmdlets und WMI verwenden, um die Ausschlusslisten zu konfigurieren, einschließlich der Überprüfung Ihrer Listen.

Standardmäßig werden lokale Änderungen an den Listen (von Benutzern mit Administratorrechten, mit PowerShell und WMI vorgenommene Änderungen) mit den Listen zusammengeführt, wie von Gruppenrichtlinien, Configuration Manager oder Intune definiert (und bereitgestellt). Die Gruppenrichtlinienlisten haben bei Konflikten Vorrang.

Sie können [konfigurieren, wie lokal und global definierte Ausschlusslisten](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) zusammengeführt werden, damit lokale Änderungen verwaltete Bereitstellungseinstellungen außer Kraft setzen können.

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>Konfigurieren der Liste der Ausschlüsse für Dateien, die von angegebenen Prozessen geöffnet wurden

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Verwenden von Microsoft Intune zum Ausschließen von Dateien, die von angegebenen Prozessen geöffnet wurden, von Scans

Weitere Informationen finden Sie [unter Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and Microsoft Defender Antivirus device restriction settings for Windows [10 in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Verwenden von Microsoft Endpoint Manager zum Ausschließen von Dateien, die von angegebenen Prozessen geöffnet wurden, von Scans

Weitere [Informationen zum Konfigurieren von](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) Microsoft Endpoint Manager (current branch) finden Sie unter Erstellen und Bereitstellen von Antischalwarerichtlinien: Ausschlusseinstellungen.

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Verwenden von Gruppenrichtlinien zum Ausschließen von Dateien, die von angegebenen Prozessen geöffnet wurden, von Scans

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.

3. Erweitern Sie die Struktur auf **Windows-Komponenten > Microsoft Defender Antivirus > Ausschlüsse .**

4. Doppelklicken Sie **auf Prozessausschlüsse,** und fügen Sie die Ausschlüsse hinzu:

    1. Legen Sie die Option auf **Aktiviert .**
    2. Klicken Sie **im Abschnitt** Optionen auf **Anzeigen...**.
    3. Geben Sie jeden Prozess in einer eigenen Zeile unter der **Spalte Wertname** ein. In der Beispieltabelle finden Sie die verschiedenen Arten von Prozessausschlüssen.  Geben **Sie 0** in die **Spalte Wert** für alle Prozesse ein.

5. Klicken Sie auf **OK**.

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Verwenden von PowerShell-Cmdlets zum Ausschließen von Dateien, die von angegebenen Prozessen geöffnet wurden, von Scans

Die Verwendung von PowerShell zum Hinzufügen oder Entfernen von Ausschlüssen für Dateien, die von Prozessen geöffnet wurden, erfordert die Verwendung einer Kombination von drei Cmdlets mit dem `-ExclusionProcess` Parameter. Die Cmdlets befinden sich alle im [Defender-Modul.](/powershell/module/defender/)

Das Format für die Cmdlets ist:

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

Die folgenden Sind als \<cmdlet> zulässig:

|Konfigurationsaktion | PowerShell-Cmdlet |
|---|---|
|Erstellen oder Überschreiben der Liste | `Set-MpPreference` |
|Zur Liste hinzufügen | `Add-MpPreference` |
|Entfernen von Elementen aus der Liste | `Remove-MpPreference` |

>[!IMPORTANT]
>Wenn Sie eine Liste mit oder erstellt haben, überschreibt das `Set-MpPreference` `Add-MpPreference` Cmdlet erneut die vorhandene `Set-MpPreference` Liste.

Der folgende Codeausschnitt würde z. B. dazu führen, dass Microsoft Defender AV-Scans alle Dateien ausschließen, die durch den angegebenen Prozess geöffnet werden:

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Manage antivirus with PowerShell [cmdlets and Microsoft Defender Antivirus cmdlets](/powershell/module/defender).

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Verwenden von Windows Management Instruction (WMI) zum Ausschließen von Dateien, die von angegebenen Prozessen geöffnet wurden, von Scans

Verwenden Sie [ **die Methoden Set,** **Add** und **Remove** der **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
ExclusionProcess
```

Die Verwendung von **Set,** **Add** und **Remove** entspricht ihren Entsprechungen in PowerShell: `Set-MpPreference` , und `Add-MpPreference` `Remove-MpPreference` .

Weitere Informationen und zulässige Parameter finden Sie  [unter Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Verwenden der Windows Security-App zum Ausschließen von Dateien, die von angegebenen Prozessen geöffnet wurden, von Scans

Anweisungen [finden Sie unter Hinzufügen von Ausschlüssen in der Windows Security-App.](microsoft-defender-security-center-antivirus.md)

## <a name="use-wildcards-in-the-process-exclusion-list"></a>Verwenden von Platzhaltern in der Prozessausschlussliste

Die Verwendung von Platzhaltern in der Prozessausschlussliste ist von der Verwendung in anderen Ausschlusslisten verschieden.

Insbesondere können Sie das Fragezeichen ( ) nicht verwenden, und das Sternchen ( ) kann nur am Ende eines vollständigen `?` `*` Pfads verwendet werden. Sie können umgebungsvariablen (z. B. ) weiterhin als Platzhalter verwenden, wenn Sie Elemente in der Prozessausschlussliste `%ALLUSERSPROFILE%` definieren.

In der folgenden Tabelle wird beschrieben, wie die Platzhalter in der Prozessausschlussliste verwendet werden können:

|Platzhalter | Beispiel für die Verwendung | Beispiel für Übereinstimmungen |
|:---|:---|:---|
|`*` (Sternchen) <br/><br/> Ersetzt eine beliebige Anzahl von Zeichen | `C:\MyData\*` | Jede Datei, die von geöffnet wird `C:\MyData\file.exe` |
|Umgebungsvariablen <br/><br/> Die definierte Variable wird als Pfad aufgefüllt, wenn der Ausschluss ausgewertet wird | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | Jede Datei, die von geöffnet wird `C:\ProgramData\CustomLogFiles\file.exe` |

## <a name="review-the-list-of-exclusions"></a>Überprüfen der Liste der Ausschlüsse

Sie können die Elemente in der Ausschlussliste mit MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure)oder der Windows Security [App abrufen.](microsoft-defender-security-center-antivirus.md)

Wenn Sie PowerShell verwenden, können Sie die Liste auf zwei Arten abrufen:

- Rufen Sie den Status aller Microsoft Defender Antivirus-Einstellungen ab. Jede liste wird in separaten Zeilen angezeigt, aber die Elemente in jeder Liste werden in derselben Zeile kombiniert.
- Schreiben Sie den Status aller Einstellungen in eine Variable, und verwenden Sie diese Variable, um nur die bestimmte Liste auf aufruft, an der Sie interessiert sind. Jede Verwendung `Add-MpPreference` von wird in eine neue Zeile geschrieben.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>Überprüfen der Ausschlussliste mithilfe von MpCmdRun

Verwenden Sie den folgenden Befehl, um Ausschlüsse mit dem [dedizierten Befehlszeilentool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)zu überprüfen:

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> Das Überprüfen von Ausschlüssen mit MpCmdRun erfordert Microsoft Defender Antivirus CAMP, Version 4.18.1812.3 (veröffentlicht im Dezember 2018) oder höher.


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>Überprüfen der Liste der Ausschlüsse zusammen mit allen anderen Microsoft Defender Antivirus-Einstellungen mithilfe von PowerShell

Verwenden Sie das folgende Cmdlet:

```PowerShell
Get-MpPreference
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender)

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>Abrufen einer bestimmten Ausschlussliste mithilfe von PowerShell

Verwenden Sie den folgenden Codeausschnitt (geben Sie jede Zeile als separaten Befehl ein); Ersetzen **Sie WDAVprefs** durch die Bezeichnung, die Sie der Variablen nennen möchten:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender)

## <a name="related-articles"></a>Verwandte Artikel

- [Konfigurieren und Überprüfen von Ausschlüssen in Microsoft Defender Antivirus-Scans](configure-exclusions-microsoft-defender-antivirus.md)
- [Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateinamen, Erweiterung und Ordnerspeicherort](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurieren von Microsoft Defender Antivirus-Ausschlüssen unter Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Häufige Fehler beim Definieren von Ausschlüssen](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus-Scans und -Korrekturen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)