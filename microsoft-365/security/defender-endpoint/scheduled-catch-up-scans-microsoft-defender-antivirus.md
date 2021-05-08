---
title: Planen regelmäßiger schneller und vollständiger Scans mit Microsoft Defender Antivirus
description: Einrichten von wiederkehrenden (geplanten) Scans, einschließlich der Ausführung und der Ausführung als vollständige oder schnelle Scans
keywords: Schnellscan, vollständiger Scan, Schnell- und Vollscan, Zeitplanscan, täglich, wöchentlich, Zeit, geplant, serienmäßig, normal
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1748a33be2c27123eb0437784dcdb2cb7905616a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274688"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Konfigurieren geplanter schneller oder vollständiger Microsoft Defender Antivirus-Scans

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> Standardmäßig wird Microsoft Defender Antivirus 15 Minuten vor dem Zeitpunkt geplanter Scans auf ein Update überprüft. Sie können [den Zeitplan verwalten, wann](manage-protection-update-schedule-microsoft-defender-antivirus.md) Schutzupdates heruntergeladen und angewendet werden sollen, um diese Standardeinstellung außer Kraft zu setzen. 

Neben dem immer-on-Echtzeitschutz und [Denkscans](run-scan-microsoft-defender-antivirus.md) bei Bedarf können Sie regelmäßige, geplante Scans einrichten. 

Sie können den Typ der Überprüfung konfigurieren, wann die Überprüfung erfolgen [](manage-protection-updates-microsoft-defender-antivirus.md) soll und ob die Überprüfung nach einem Schutzupdate erfolgen soll oder ob der Endpunkt verwendet wird. Sie können auch angeben, wann spezielle Scans durchgeführt werden sollen, um die Korrektur durchzuführen.

In diesem Artikel wird beschrieben, wie Geplante Scans mit Gruppenrichtlinien, PowerShell-Cmdlets und WMI konfiguriert werden. Sie können auch Zeitplänescans mit [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) oder [Microsoft Intune.](/mem/intune/configuration/device-restrictions-windows-10)

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>So konfigurieren Sie die in diesem Artikel beschriebenen Gruppenrichtlinieneinstellungen

1. Wechseln Sie auf dem Computer für die Gruppenrichtlinienverwaltung im Gruppenrichtlinien-Editor zu Computerkonfiguration Administrative Vorlagen Windows  >    >  **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Scan**.

2. Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten aus.**

3. Geben Sie Einstellungen für das Gruppenrichtlinienobjekt an, und wählen Sie dann **OK aus.** 

4. Wiederholen Sie die Schritte 1 bis 4 für jede Einstellung, die Sie konfigurieren möchten.

5. Stellen Sie ihr Gruppenrichtlinienobjekt wie gewohnt zur Bereitstellung. Wenn Sie Hilfe zu Gruppenrichtlinienobjekten benötigen, lesen [Sie Erstellen eines Gruppenrichtlinienobjekts](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).

Weitere Informationen finden Sie [unter Manage when protection updates should be download and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and Prevent or allow users to locally modify policy settings [topics.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>Schnellscan im Vergleich zu vollständiger Überprüfung und benutzerdefinierter Überprüfung

Wenn Sie geplante Scans einrichten, können Sie festlegen, ob es sich bei der Überprüfung um eine vollständige oder eine schnelle Überprüfung gehen soll.


|Schnellscan  |Vollständiger Scan  | Benutzerdefinierte Überprüfung |
|---------|---------|---------|
|Eine schnelle Überprüfung sucht nach allen Speicherorten, an denen Schadsoftware registriert werden könnte, um mit dem System zu beginnen, z. B. Registrierungsschlüssel und bekannte Windows Startordner. <p>In den meisten Fällen ist eine schnelle Überprüfung ausreichend und wird für geplante Scans empfohlen. |Eine vollständige Überprüfung beginnt mit einer schnell ausgeführten Überprüfung und wird dann mit einer sequenziellen Dateiscan aller bereitgestellten Festplatten und Wechseldatenträger/Netzwerklaufwerke fortgesetzt (sofern die vollständige Überprüfung dafür konfiguriert ist). <p>Eine vollständige Überprüfung kann je nach Menge und Art der zu überprüfende Daten einige Stunden oder Tage dauern.<p>Nach Abschluss der vollständigen Überprüfung ist neue Sicherheitsintelligenz verfügbar, und es ist eine neue Überprüfung erforderlich, um sicherzustellen, dass keine weiteren Bedrohungen mit der neuen Sicherheitsintelligenz erkannt werden.   | Bei einer benutzerdefinierten Überprüfung handelt es sich um eine Schnellscan, die für die angegebenen Dateien und Ordner ausgeführt wird. Sie können beispielsweise ein USB-Laufwerk oder einen bestimmten Ordner auf dem lokalen Laufwerk Ihres Geräts überprüfen. <p> | 

>[!NOTE]
>Standardmäßig werden Schnellscans auf angeschlossenen Wechselmedien ausgeführt, z. B. USB-Laufwerken.

### <a name="how-do-i-know-which-scan-type-to-choose"></a>Wo finde ich den zu wählende Scantyp?

Verwenden Sie die folgende Tabelle, um einen Scantyp zu wählen.


|Szenario  |Empfohlener Scantyp  |
|---------|---------|
|Sie möchten regelmäßige, geplante Scans einrichten     | Schnellscan <p>Bei einer schnell durchgeführten Überprüfung werden die Prozesse, der Arbeitsspeicher, die Profile und bestimmte Speicherorte auf dem Gerät überprüft. In Kombination [mit dem Immer-On-Echtzeitschutz](configure-real-time-protection-microsoft-defender-antivirus.md)bietet eine schnelle Überprüfung eine starke Abdeckung sowohl für Schadsoftware, die mit dem System beginnt, als auch für Schadsoftware auf Kernelebene. Der Echtzeitschutz überprüft Dateien, wenn sie geöffnet und geschlossen werden und wann immer ein Benutzer zu einem Ordner navigiert.         |
|Bedrohungen, z. B. Schadsoftware, werden auf einem Gerät erkannt     | Vollständiger Scan <p>Bei einer vollständigen Überprüfung kann ermittelt werden, ob es inaktive Komponenten gibt, für die eine gründlichere Bereinigung erforderlich ist.         |
|Sie möchten eine [Anforderungsscan ausführen](run-scan-microsoft-defender-antivirus.md)     | Vollständiger Scan  <p>Bei einer vollständigen Überprüfung werden alle Dateien auf dem Gerätedatenträger betrachtet, einschließlich veralteter, archivierter und nicht täglich zugänglicher Dateien.      |
| Sie möchten sicherstellen, dass ein tragbares Gerät, z. B. ein USB-Laufwerk, keine Schadsoftware enthält. | Benutzerdefinierte Überprüfung <p>Mit einer benutzerdefinierten Überprüfung können Sie bestimmte Speicherorte, Ordner oder Dateien auswählen und eine schnelle Überprüfung durchführen. |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>Was muss ich sonst noch über schnelle und vollständige Scans wissen?

- Schädliche Dateien können an Speicherorten gespeichert werden, die nicht in einer Schnellscan enthalten sind. Der always-on-Echtzeitschutz überprüft jedoch alle geöffneten und geschlossenen Dateien sowie alle Dateien, die sich in Ordnern befinden, auf die von einem Benutzer zugegriffen wird. Die Kombination aus Echtzeitschutz und schneller Überprüfung hilft dabei, einen starken Schutz vor Schadsoftware zu bieten.

- Der On-Access-Schutz mit cloudbasiertem Schutz trägt dazu bei, dass alle dateien, auf die auf das System zugegriffen wird, mit den neuesten Sicherheitsintelligenz- und Cloud Machine [Learning-Modellen](cloud-protection-microsoft-defender-antivirus.md) überprüft werden.

- Wenn der Echtzeitschutz Schadsoftware erkennt und der Umfang der betroffenen Dateien zunächst nicht bestimmt wird, Microsoft Defender Antivirus im Rahmen des Korrekturprozesses eine vollständige Überprüfung initiiert.

- Bei einer vollständigen Überprüfung können schädliche Dateien erkannt werden, die von anderen Scans nicht erkannt wurden, z. B. eine Schnellscan. Eine vollständige Überprüfung kann jedoch eine Weile dauern und wertvolle Systemressourcen zum Abschließen verwenden.

- Wenn ein Gerät über einen längeren Zeitraum offline ist, kann eine vollständige Überprüfung länger dauern. 

## <a name="set-up-scheduled-scans"></a>Einrichten geplanter Scans

Geplante Scans werden an dem von Ihnen angegebenen Tag und der angegebenen Uhrzeit ausgeführt. Sie können Gruppenrichtlinien, PowerShell und WMI verwenden, um geplante Scans zu konfigurieren.

> [!NOTE]
> Wenn ein Gerät während einer geplanten vollständigen Überprüfung getrennt wird und während der geplanten vollständigen Überprüfung mit Akku ausgeführt wird, wird die geplante Überprüfung mit dem Ereignis 1002 beendet, das besagt, dass die Überprüfung vor Abschluss beendet wurde. Microsoft Defender Antivirus wird zum nächsten geplanten Zeitpunkt eine vollständige Überprüfung ausgeführt.

### <a name="use-group-policy-to-schedule-scans"></a>Planen von Scans mithilfe von Gruppenrichtlinien

|Speicherort | Einstellung | Beschreibung | Standardeinstellung (wenn nicht konfiguriert) |
|:---|:---|:---|:---|
|Überprüfung | Angeben des Scantyps, der für eine geplante Überprüfung verwendet werden soll | Schnellscan |
|Überprüfung | Angeben des Wochentags zum Ausführen einer geplanten Überprüfung | Geben Sie den Tag (oder nie) an, an dem eine Überprüfung ausgeführt werden soll. | Nie |
|Überprüfung | Angeben der Uhrzeit für die Ausführung einer geplanten Überprüfung | Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 1 Uhr ein). | 2:00 Uhr |
|Root | Randomisieren geplanter Vorgangszeiten |In Microsoft Defender Antivirus die Startzeit der Überprüfung auf ein Intervall von 0 bis 4 Stunden randomisieren. <p>In [SCEP,](/mem/intune/protect/certificates-scep-configure)randomize scans to any interval plus or minus 30 minutes. Dies kann bei virtuellen Computern oder VDI-Bereitstellungen hilfreich sein. | Aktiviert |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>Verwenden von PowerShell-Cmdlets zum Planen von Scans

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Weitere Informationen finden Sie unter [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Verwenden Windows Management Instruction (WMI) zum Planen von Scans

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Weitere Informationen und zulässige Parameter finden Sie [unter Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


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

Weitere Informationen finden Sie unter [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi"></a>Verwenden Windows Management Instruction (WMI)

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
ScanOnlyIfIdleEnabled
```

Weitere Informationen zu APIs und zulässigen Parametern finden Sie [unter Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>Konfigurieren, wann vollständige Überprüfungen ausgeführt werden sollen, um die Korrektur durchzuführen

Einige Bedrohungen erfordern möglicherweise eine vollständige Überprüfung, um ihre Entfernung und Behebung abschließen zu können. Sie können angeben, wann diese Überprüfungen mit Gruppenrichtlinien, PowerShell oder WMI durchgeführt werden sollen.

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

Unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets](/powershell/module/defender/) finden Sie weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi"></a>Verwenden Windows Management Instruction (WMI)

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).


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

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Use PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and run Microsoft Defender Antivirus and Defender [cmdlets](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Verwenden Windows Management Instruction (WMI) zum Planen täglicher Scans

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
ScanScheduleQuickScanTime
```

Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).


## <a name="enable-scans-after-protection-updates"></a>Aktivieren von Scans nach Schutzupdates

Sie können erzwingen, dass eine Überprüfung nach jedem Schutzupdate [mit Gruppenrichtlinien](manage-protection-updates-microsoft-defender-antivirus.md) erfolgt.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>Verwenden von Gruppenrichtlinien zum Planen von Scans nach Schutzupdates

|Speicherort | Einstellung | Beschreibung | Standardeinstellung (wenn nicht konfiguriert)|
|:---|:---|:---|:---|
|Signaturupdates | Aktivieren der Überprüfung nach dem Update der Sicherheitsintelligenz | Eine Überprüfung erfolgt unmittelbar nach dem Herunterladen eines neuen Schutzupdates. | Aktiviert |

## <a name="see-also"></a>Siehe auch

- [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [Konfigurieren und Ausführen von bedarfsgesteuerten Scans durch Microsoft Defender Antivirus](run-scan-microsoft-defender-antivirus.md)
- [Konfigurieren der Scanoptionen von Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Baselines](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)