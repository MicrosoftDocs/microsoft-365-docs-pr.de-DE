---
title: Planen regelmäßiger schneller und vollständiger Scans mit Microsoft Defender Antivirus
description: Einrichten von wiederkehrenden (geplanten) Scans, einschließlich der Ausführung und der Ausführung als vollständige oder schnelle Scans
keywords: Schnellscan, vollständiger Scan, Schnell- und Vollscan, Zeitplanscan, täglich, wöchentlich, Zeit, geplant, serienmäßig, normal
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690628"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Konfigurieren geplanter schneller oder vollständiger Microsoft Defender Antivirus-Scans

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> Standardmäßig sucht Microsoft Defender Antivirus 15 Minuten vor dem Zeitpunkt geplanter Scans nach einem Update. Sie können [den Zeitplan verwalten, wann](manage-protection-update-schedule-microsoft-defender-antivirus.md) Schutzupdates heruntergeladen und angewendet werden sollen, um diese Standardeinstellung außer Kraft zu setzen. 

Neben dem immer-on-Echtzeitschutz und [Denkscans](run-scan-microsoft-defender-antivirus.md) bei Bedarf können Sie regelmäßige, geplante Scans einrichten. 

Sie können den Typ der Überprüfung konfigurieren, wann die Überprüfung erfolgen [](manage-protection-updates-microsoft-defender-antivirus.md) soll und ob die Überprüfung nach einem Schutzupdate erfolgen soll oder ob der Endpunkt verwendet wird. Sie können auch angeben, wann spezielle Scans durchgeführt werden sollen, um die Korrektur durchzuführen.

In diesem Artikel wird beschrieben, wie Geplante Scans mit Gruppenrichtlinien, PowerShell-Cmdlets und WMI konfiguriert werden. Sie können auch Zeitplänescans mit [Microsoft Endpoint Configuration Manager oder](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) Microsoft Intune [konfigurieren.](/mem/intune/configuration/device-restrictions-windows-10)

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>So konfigurieren Sie die in diesem Artikel beschriebenen Gruppenrichtlinieneinstellungen

1.  Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

3.  Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

4.  Klicken Sie **auf Administrative Vorlagen**.

5.  Erweitern Sie die Struktur auf **Windows-Komponenten >**  Microsoft Defender Antivirus und dann den in der folgenden Tabelle angegebenen Speicherort.

6. Doppelklicken Sie auf die **Richtlinieneinstellung,** wie in der folgenden Tabelle angegeben, und legen Sie die Option auf die gewünschte Konfiguration fest. 

7. Klicken **Sie auf OK,** und wiederholen Sie dies für alle anderen Einstellungen.

Weitere Informationen finden Sie [unter Manage when protection updates should be download and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and Prevent or allow users to locally modify policy settings [topics.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>Schnellscan im Vergleich zu vollständiger Überprüfung und benutzerdefinierter Überprüfung

Wenn Sie geplante Scans einrichten, können Sie festlegen, ob es sich bei der Überprüfung um eine vollständige oder eine schnelle Überprüfung gehen soll.

Schnellscans sehen sich alle Speicherorte an, an denen Schadsoftware registriert werden könnte, um mit dem System zu beginnen, z. B. Registrierungsschlüssel und bekannte Windows-Startordner. 

In Kombination mit der [Immer-On-Echtzeitschutzfunktion](configure-real-time-protection-microsoft-defender-antivirus.md) , die Dateien überprüft, wenn sie geöffnet und geschlossen werden, und wenn ein Benutzer zu einem Ordner navigiert, hilft ein Schnellscan, sowohl für Schadsoftware, die mit dem System beginnt, als auch für Schadsoftware auf Kernelebene eine starke Abdeckung zu bieten.  

In den meisten Fällen bedeutet dies, dass eine schnelle Überprüfung ausreichend ist, um Schadsoftware zu finden, die nicht vom Echtzeitschutz aufgegriffen wurde.

Eine vollständige Überprüfung kann für Endpunkte nützlich sein, die eine Schadsoftwarebedrohung festgestellt haben, um zu ermitteln, ob inaktive Komponenten enthalten sind, die eine gründlichere Bereinigung erfordern. In dieser Instanz können Sie eine vollständige Überprüfung verwenden, wenn Sie eine [On-Demand-Überprüfung ausführen.](run-scan-microsoft-defender-antivirus.md)

Mit einer benutzerdefinierten Überprüfung können Sie die zu scannenden Dateien und Ordner angeben, z. B. ein USB-Laufwerk. 

>[!NOTE]
>Standardmäßig werden Schnellscans auf angeschlossenen Wechselmedien ausgeführt, z. B. USB-Laufwerken.

## <a name="set-up-scheduled-scans"></a>Einrichten geplanter Scans

Geplante Scans werden zum angegebenen Tag und zur angegebenen Uhrzeit ausgeführt. Sie können Gruppenrichtlinien, PowerShell und WMI verwenden, um geplante Scans zu konfigurieren.

>[!NOTE]
>Wenn ein Computer während einer geplanten vollständigen Überprüfung getrennt wird und während der geplanten vollständigen Überprüfung mit dem Akku ausgeführt wird, wird die geplante Überprüfung mit dem Ereignis 1002 beendet, das besagt, dass die Überprüfung vor Abschluss beendet wurde. Microsoft Defender Antivirus wird zum nächsten geplanten Zeitpunkt eine vollständige Überprüfung ausführen.

### <a name="use-group-policy-to-schedule-scans"></a>Planen von Scans mithilfe von Gruppenrichtlinien

|Speicherort | Einstellung | Beschreibung | Standardeinstellung (wenn nicht konfiguriert) |
|:---|:---|:---|:---|
|Überprüfung | Angeben des Scantyps, der für eine geplante Überprüfung verwendet werden soll | Schnellscan |
|Überprüfung | Angeben des Wochentags zum Ausführen einer geplanten Überprüfung | Geben Sie den Tag (oder nie) an, an dem eine Überprüfung ausgeführt werden soll. | Nie |
|Überprüfung | Angeben der Uhrzeit für die Ausführung einer geplanten Überprüfung | Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 1 Uhr ein). | 2:00 Uhr |
|Root | Randomisieren geplanter Vorgangszeiten |In Microsoft Defender Antivirus: Randomize the start time of the scan to any interval from 0 to 4 hours. <br>In FEP/SCEP: randomisieren Sie auf ein beliebiges Intervall plus oder minus 30 Minuten. Dies kann in VM- oder VDI-Bereitstellungen hilfreich sein. | Aktiviert |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>Verwenden von PowerShell-Cmdlets zum Planen von Scans

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Verwenden von Windows Management Instruction (WMI) zum Planen von Scans

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Weitere Informationen und zulässige Parameter finden Sie im Folgenden:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>Geplante Scans nur starten, wenn der Endpunkt nicht verwendet wird

Sie können festlegen, dass die geplante Überprüfung nur stattfindet, wenn der Endpunkt aktiviert ist, jedoch nicht mit Gruppenrichtlinien, PowerShell oder WMI verwendet wird.

> [!NOTE]
> Bei diesen Überprüfungen wird die KONFIGURATION der CPU-Einschränkung nicht berücksichtigt und die verfügbaren Ressourcen genutzt, um den Scan so schnell wie möglich durchzuführen.

### <a name="use-group-policy-to-schedule-scans"></a>Planen von Scans mithilfe von Gruppenrichtlinien

|Speicherort | Einstellung | Beschreibung | Standardeinstellung (wenn nicht konfiguriert) |
|:---|:---|:---|:---|
|Überprüfung | Starten der geplanten Überprüfung nur, wenn der Computer zwar installiert ist, aber nicht verwendet wird | Geplante Scans werden nicht ausgeführt, es sei denn, der Computer ist in, aber nicht in Gebrauch. | Aktiviert |

### <a name="use-powershell-cmdlets"></a>Verwenden von PowerShell-Cmdlets

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi"></a>Verwenden von Windows Management Instruction (WMI)

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
ScanOnlyIfIdleEnabled
```

Weitere Informationen und zulässige Parameter finden Sie im Folgenden:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>Konfigurieren, wann vollständige Überprüfungen ausgeführt werden sollen, um die Korrektur durchzuführen

Einige Bedrohungen erfordern möglicherweise eine vollständige Überprüfung, um ihre Entfernung und Behebung abschließen zu können. Sie können planen, wann diese Überprüfungen mit Gruppenrichtlinien, PowerShell oder WMI durchgeführt werden sollen.

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>Planen der erforderlichen Überprüfungen mithilfe von Gruppenrichtlinien

| Speicherort | Einstellung | Beschreibung | Standardeinstellung (wenn nicht konfiguriert) |
|---|---|---|---|
|Korrektur | Angeben des Wochentags zum Ausführen einer geplanten vollständigen Überprüfung zum Abschließen der Korrektur | Geben Sie den Tag (oder nie) an, an dem eine Überprüfung ausgeführt werden soll. | Nie |
|Korrektur | Angeben der Uhrzeit für die Ausführung einer geplanten vollständigen Überprüfung zum Abschließen der Korrektur | Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 1:00 Uhr ein) | 2:00 Uhr |

### <a name="use-powershell-cmdlets"></a>Verwenden von PowerShell-Cmdlets

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi"></a>Verwenden von Windows Management Instruction (WMI)

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Weitere Informationen und zulässige Parameter finden Sie im Folgenden:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a>Einrichten täglicher Schnellscans

Sie können eine tägliche Schnellscan aktivieren, die zusätzlich zu ihren anderen geplanten Scans mit Gruppenrichtlinie, PowerShell oder WMI ausgeführt werden kann.


### <a name="use-group-policy-to-schedule-daily-scans"></a>Verwenden von Gruppenrichtlinien zum Planen täglicher Scans


|Speicherort | Einstellung | Beschreibung | Standardeinstellung (wenn nicht konfiguriert) |
|:---|:---|:---|:---|
|Überprüfung | Angeben des Intervalls zum Ausführen von Schnellscans pro Tag | Geben Sie an, wie viele Stunden vor dem nächsten Schnellscan verstreichen sollen. Wenn Sie beispielsweise alle zwei Stunden ausführen möchten, geben Sie **2** ein, und geben Sie einmal pro Tag **24 ein.** Geben **Sie 0** ein, um nie einen täglichen Schnellscan ausführen zu können. | Nie |
|Überprüfung | Angeben der Uhrzeit für einen täglichen Schnellscan | Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 1:00 Uhr ein) | 2:00 Uhr |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>Verwenden von PowerShell-Cmdlets zum Planen täglicher Scans

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Verwenden von Windows Management Instruction (WMI) zum Planen täglicher Scans

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
ScanScheduleQuickScanTime
```

Weitere Informationen und zulässige Parameter finden Sie im Folgenden:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a>Aktivieren von Scans nach Schutzupdates

Sie können erzwingen, dass eine Überprüfung nach jedem Schutzupdate [mit Gruppenrichtlinien](manage-protection-updates-microsoft-defender-antivirus.md) erfolgt.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>Verwenden von Gruppenrichtlinien zum Planen von Scans nach Schutzupdates

|Speicherort | Einstellung | Beschreibung | Standardeinstellung (wenn nicht konfiguriert)|
|:---|:---|:---|:---|
|Signaturupdates | Aktivieren der Überprüfung nach dem Update der Sicherheitsintelligenz | Eine Überprüfung erfolgt unmittelbar nach dem Herunterladen eines neuen Schutzupdates. | Aktiviert |

## <a name="see-also"></a>Siehe auch
- [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [Konfigurieren und Ausführen von Bedarfsscans von Microsoft Defender Antivirus](run-scan-microsoft-defender-antivirus.md)
- [Konfigurieren von Microsoft Defender Antivirus-Überprüfungsoptionen](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Basiswerten](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)