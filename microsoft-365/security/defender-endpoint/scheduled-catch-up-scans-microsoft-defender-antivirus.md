---
title: Planen regelmäßiger schneller und vollständiger Scans mit Microsoft Defender Antivirus
description: Einrichten von wiederkehrenden (geplanten) Scans, z. B. wann sie ausgeführt werden sollen und ob sie als vollständige oder schnelle Scans ausgeführt werden sollen
keywords: Schnellscan, vollständiger Scan, schnell und vollständig, Scan planen, täglich, wöchentlich, Zeit, geplant, serieell, regelmäßig
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f1344026878b7fbd6242d82b1afb0e6671c32073
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789268"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Konfigurieren geplanter schneller oder vollständiger Microsoft Defender Antivirus-Scans

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> Standardmäßig sucht Microsoft Defender Antivirus 15 Minuten vor dem Zeitpunkt geplanter Überprüfungen nach einem Update. Sie können den Zeitplan für das Herunterladen und Anwenden von [Schutzupdates verwalten,](manage-protection-update-schedule-microsoft-defender-antivirus.md) um diese Standardeinstellung außer Kraft zu setzen. 

Zusätzlich zu always-on-Echtzeitschutz und [On-Demand-Scans](run-scan-microsoft-defender-antivirus.md) können Sie regelmäßige, geplante Scans einrichten. 

Sie können den Scantyp konfigurieren, wann der Scan durchgeführt werden soll und ob der Scan nach einem [Schutzupdate](manage-protection-updates-microsoft-defender-antivirus.md) durchgeführt werden soll oder ob der Endpunkt verwendet wird. Sie können auch angeben, wann spezielle Scans durchgeführt werden sollen, um die Korrektur abzuschließen.

In diesem Artikel wird beschrieben, wie Sie geplante Scans mit Gruppenrichtlinien, PowerShell-Cmdlets und WMI konfigurieren. Sie können auch Zeitpläneüberprüfungen mit [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) oder [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10)konfigurieren.

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>So konfigurieren Sie die in diesem Artikel beschriebenen Gruppenrichtlinieneinstellungen

1. Wechseln Sie auf dem Computer für die Gruppenrichtlinienverwaltung im Gruppenrichtlinien-Editor zu Administrative Vorlagen für die **Computerkonfiguration**  >    >  **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Überprüfung.**

2. Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.

3. Geben Sie Einstellungen für das Gruppenrichtlinienobjekt an, und wählen Sie dann **OK** aus. 

4. Wiederholen Sie die Schritte 1 bis 4 für jede Einstellung, die Sie konfigurieren möchten.

5. Stellen Sie Das Gruppenrichtlinienobjekt wie gewohnt bereit. Wenn Sie Hilfe zu Gruppenrichtlinienobjekten benötigen, lesen [Sie Erstellen eines Gruppenrichtlinienobjekts .](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)

Weitere Informationen finden Sie unter ["Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen"](manage-protection-update-schedule-microsoft-defender-antivirus.md) und ["Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern".](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>Schnellscan im Vergleich zum vollständigen Scan und benutzerdefinierter Scan

Wenn Sie geplante Scans einrichten, können Sie festlegen, ob es sich bei der Überprüfung um einen vollständigen oder einen Schnellscan handeln soll.


|Schnellscan  |Vollständiger Scan  | Benutzerdefinierter Scan |
|---------|---------|---------|
|Ein Schnellscan untersucht alle Speicherorte, an denen Schadsoftware registriert werden könnte, um mit dem System zu beginnen, z. B. Registrierungsschlüssel und bekannte Windows Startordner. <p>In den meisten Fällen ist ein Schnellscan ausreichend und wird für geplante Scans empfohlen. |Eine vollständige Überprüfung beginnt mit einer Schnellüberprüfung und wird dann mit einer sequenziellen Dateiüberprüfung aller bereitgestellten Festplatten und Wechseldatenträger/Netzlaufwerke fortgesetzt (wenn der vollständige Scan dafür konfiguriert ist). <p>Ein vollständiger Scan kann einige Stunden oder Tage dauern, abhängig von der Menge und dem Typ der Daten, die gescannt werden müssen.<p>Wenn der vollständige Scan abgeschlossen ist, sind neue Sicherheitsinformationen verfügbar, und es ist ein neuer Scan erforderlich, um sicherzustellen, dass keine anderen Bedrohungen mit der neuen Sicherheitsintelligenz erkannt werden.   | Ein benutzerdefinierter Scan ist ein Schnellscan, der für die von Ihnen angegebenen Dateien und Ordner ausgeführt wird. Sie können z. B. ein USB-Laufwerk oder einen bestimmten Ordner auf dem lokalen Laufwerk Ihres Geräts scannen. <p> | 

>[!NOTE]
>Standardmäßig werden Schnellscans auf bereitgestellten Wechselmedien wie USB-Laufwerken ausgeführt.

### <a name="how-do-i-know-which-scan-type-to-choose"></a>Woher weiß ich, welcher Scantyp ausgewählt werden soll?

Verwenden Sie die folgende Tabelle, um einen Scantyp auszuwählen.


|Szenario  |Empfohlener Scantyp  |
|---------|---------|
|Sie möchten regelmäßige, geplante Scans einrichten.     | Schnellscan <p>Ein Schnellscan überprüft die Prozesse, den Arbeitsspeicher, die Profile und bestimmten Speicherorte auf dem Gerät. In Kombination mit [einem immer aktivierten Echtzeitschutz](configure-real-time-protection-microsoft-defender-antivirus.md)bietet ein Schnellscan eine starke Abdeckung sowohl für Schadsoftware, die mit dem System beginnt, als auch für Schadsoftware auf Kernelebene. Der Echtzeitschutz überprüft Dateien, wenn sie geöffnet und geschlossen werden und wenn ein Benutzer zu einem Ordner navigiert.         |
|Bedrohungen wie Schadsoftware werden auf einem einzelnen Gerät erkannt.     | Schnellscan <p>In den meisten Fällen erfasst und bereinigt ein Schnellscan erkannte Schadsoftware.   |
|Sie möchten eine [Überprüfung nach Bedarf](run-scan-microsoft-defender-antivirus.md) ausführen     | Schnellscan       |
| Sie möchten sicherstellen, dass ein tragbares Gerät, z. B. ein USB-Laufwerk, keine Schadsoftware enthält. | Benutzerdefinierter Scan <p>Mit einer benutzerdefinierten Überprüfung können Sie bestimmte Speicherorte, Ordner oder Dateien auswählen und einen Schnellscan ausführen. |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>Was muss ich sonst noch über schnelle und vollständige Scans wissen?

- Schädliche Dateien können an Speicherorten gespeichert werden, die nicht in einem Schnellscan enthalten sind. Der immer aktivierte Echtzeitschutz überprüft jedoch alle Dateien, die geöffnet und geschlossen werden, sowie alle Dateien, die sich in Ordnern befinden, auf die ein Benutzer zugegriffen hat. Die Kombination aus Echtzeitschutz und schnellem Scan bietet starken Schutz vor Schadsoftware.

- Der Schutz beim Zugriff mit über die [Cloud bereitgestellten Schutz](cloud-protection-microsoft-defender-antivirus.md) trägt dazu bei, sicherzustellen, dass alle Dateien, auf die auf dem System zugegriffen wird, mit den neuesten Sicherheitsintelligenz- und Cloud Machine Learning-Modellen gescannt werden.

- Wenn der Echtzeitschutz Schadsoftware erkennt und das Ausmaß der betroffenen Dateien zunächst nicht bestimmt wird, initiiert Microsoft Defender Antivirus im Rahmen des Korrekturprozesses eine vollständige Überprüfung.

- Ein vollständiger Scan kann schädliche Dateien erkennen, die von anderen Scans nicht erkannt wurden, z. B. ein Schnellscan. Eine vollständige Überprüfung kann jedoch einige Zeit in Anspruch nehmen und wertvolle Systemressourcen nutzen, um diesen Vorgang abzuschließen.

- Wenn ein Gerät über einen längeren Zeitraum offline ist, kann ein vollständiger Scan länger dauern. 

## <a name="set-up-scheduled-scans"></a>Einrichten von geplanten Scans

Geplante Scans werden an dem von Ihnen angegebenen Tag und der angegebenen Uhrzeit ausgeführt. Sie können gruppenrichtlinien, PowerShell und WMI verwenden, um geplante Scans zu konfigurieren.

> [!NOTE]
> Wenn ein Gerät während eines geplanten vollständigen Scans angeschlossen wird und mit Akku betrieben wird, wird der geplante Scan mit Dem Ereignis 1002 beendet, das besagt, dass der Scan vor Abschluss beendet wurde. Microsoft Defender Antivirus führt zum nächsten geplanten Zeitpunkt eine vollständige Überprüfung durch.

### <a name="use-group-policy-to-schedule-scans"></a>Verwenden von Gruppenrichtlinien zum Planen von Scans

|Standort | Einstellung | Beschreibung | Standardeinstellung (falls nicht konfiguriert) |
|:---|:---|:---|:---|
|Überprüfung | Angeben des Für einen geplanten Scan zu verwendenden Scantyps | Schnellscan |
|Überprüfung | Angeben des Wochentags, an dem eine geplante Überprüfung ausgeführt werden soll | Geben Sie den Tag (oder nie) an, an dem eine Überprüfung ausgeführt werden soll. | Nie |
|Überprüfung | Angeben der Tageszeit zum Ausführen eines geplanten Scans | Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 1 Uhr ein). | 2:00 Uhr |
|wurzel | Zufällige Zeitplanung für geplante Aufgaben |In Microsoft Defender Antivirus die Startzeit des Scans in ein beliebiges Intervall zwischen 0 und 4 Stunden zufällig festlegen. <p>In [SCEP](/mem/intune/protect/certificates-scep-configure)randomisieren Sie Scans in ein beliebiges Intervall plus oder minus 30 Minuten. Dies kann bei virtuellen Computern oder VDI-Bereitstellungen hilfreich sein. | Aktiviert |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>Verwenden von PowerShell-Cmdlets zum Planen von Scans

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Weitere Informationen finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/) Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Verwenden Windows Management Instruction (WMI) zum Planen von Scans

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>Starten von geplanten Scans nur, wenn der Endpunkt nicht verwendet wird

Sie können festlegen, dass der geplante Scan nur ausgeführt wird, wenn der Endpunkt aktiviert ist, aber nicht mit Gruppenrichtlinien, PowerShell oder WMI verwendet wird.

> [!NOTE]
> Diese Überprüfungen berücksichtigen nicht die CPU-Drosselungskonfiguration und nutzen die verfügbaren Ressourcen, um den Scan so schnell wie möglich abzuschließen.

### <a name="use-group-policy-to-schedule-scans"></a>Verwenden von Gruppenrichtlinien zum Planen von Scans

|Standort | Einstellung | Beschreibung | Standardeinstellung (falls nicht konfiguriert) |
|:---|:---|:---|:---|
|Überprüfung | Starten Sie den geplanten Scan nur, wenn der Computer aktiviert ist, aber nicht verwendet wird | Geplante Scans werden nur ausgeführt, wenn der Computer aktiviert ist, aber nicht verwendet wird. | Aktiviert |

### <a name="use-powershell-cmdlets"></a>Verwenden von PowerShell-Cmdlets

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Weitere Informationen finden Sie unter [PowerShell-Cmdlets verwenden, um Microsoft Defender Antivirus zu konfigurieren und auszuführen](use-powershell-cmdlets-microsoft-defender-antivirus.md) und unter [Defender-Cmdlets](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi"></a>Verwenden Windows-Verwaltungsanweisung (WMI)

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
ScanOnlyIfIdleEnabled
```

Weitere Informationen zu APIs und zulässigen Parametern finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>Konfigurieren, wann vollständige Scans ausgeführt werden sollen, um die Korrektur abzuschließen

Einige Bedrohungen erfordern möglicherweise eine vollständige Überprüfung, um deren Entfernung und Behebung abzuschließen. Sie können angeben, wann diese Überprüfungen mit der Gruppenrichtlinie, PowerShell oder WMI durchgeführt werden sollen.

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>Verwenden von Gruppenrichtlinien zum Planen von Überprüfungen, die für die Wartung erforderlich sind

| Standort | Einstellung | Beschreibung | Standardeinstellung (falls nicht konfiguriert) |
|---|---|---|---|
|Sanierung | Geben Sie den Wochentag an, an dem ein geplanter vollständiger Scan ausgeführt werden soll, um die Korrektur abzuschließen. | Geben Sie den Tag (oder nie) an, an dem eine Überprüfung ausgeführt werden soll. | Nie |
|Sanierung | Geben Sie die Tageszeit an, zu der ein geplanter vollständiger Scan ausgeführt werden soll, um die Wartung abzuschließen. | Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 01:00 Uhr ein) | 2:00 Uhr |

### <a name="use-powershell-cmdlets"></a>Verwenden von PowerShell-Cmdlets

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen](use-powershell-cmdlets-microsoft-defender-antivirus.md) von Microsoft Defender Antivirus und [Defender-Cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi"></a>Verwenden Windows-Verwaltungsanweisung (WMI)

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-up-daily-quick-scans"></a>Einrichten täglicher Schnellscans

Sie können einen täglichen Schnellscan aktivieren, der zusätzlich zu Ihren anderen geplanten Scans mithilfe von Gruppenrichtlinien, PowerShell oder WMI ausgeführt werden kann.

### <a name="use-group-policy-to-schedule-daily-scans"></a>Verwenden von Gruppenrichtlinien zum Planen von täglichen Scans

|Standort | Einstellung | Beschreibung | Standardeinstellung (falls nicht konfiguriert) |
|:---|:---|:---|:---|
|Überprüfung | Angeben des Intervalls zum Ausführen von Schnellscans pro Tag | Geben Sie an, wie viele Stunden vor dem nächsten Schnellscan verstrichen sein sollen. Wenn Sie beispielsweise alle zwei Stunden ausführen möchten, geben Sie **2** ein, geben Sie einmal täglich **24** ein. Geben Sie **0** ein, um nie einen täglichen Schnellscan auszuführen. | Nie |
|Überprüfung | Angeben der Zeit für einen täglichen Schnellscan | Geben Sie die Anzahl der Minuten nach Mitternacht an (geben Sie z. B. **60** für 01:00 Uhr ein) | 2:00 Uhr |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>Verwenden von PowerShell-Cmdlets zum Planen von täglichen Scans

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Verwenden von Windows Management Instruction (WMI) zum Planen von täglichen Scans

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
ScanScheduleQuickScanTime
```

Weitere Informationen und zulässige Parameter finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a>Aktivieren von Scans nach Schutzupdates

Sie können erzwingen, dass nach jedem [Schutzupdate](manage-protection-updates-microsoft-defender-antivirus.md) mithilfe von Gruppenrichtlinien eine Überprüfung durchgeführt wird.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>Verwenden von Gruppenrichtlinien zum Planen von Scans nach Schutzupdates

|Standort | Einstellung | Beschreibung | Standardeinstellung (falls nicht konfiguriert)|
|:---|:---|:---|:---|
|Signaturupdates | Aktivieren des Scans nach dem Security Intelligence-Update | Eine Überprüfung erfolgt unmittelbar nach dem Herunterladen eines neuen Schutzupdates. | Aktiviert |

## <a name="see-also"></a>Siehe auch

- [Verhindern oder Zulassen der lokalen Änderung von Richtlinieneinstellungen durch Benutzer](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [Konfigurieren und Ausführen von bedarfsgesteuerten Scans durch Microsoft Defender Antivirus](run-scan-microsoft-defender-antivirus.md)
- [Konfigurieren der Scanoptionen von Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)