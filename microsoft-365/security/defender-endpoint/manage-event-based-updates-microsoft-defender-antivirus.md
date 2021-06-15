---
title: Anwenden Microsoft Defender Antivirus Updates nach bestimmten Ereignissen
description: Verwalten Sie, wie Microsoft Defender Antivirus Updates zur Sicherheitsintelligenz nach dem Starten oder Empfangen von über die Cloud bereitgestellten Erkennungsberichten anwendet.
keywords: Updates, Schutz, Updates erzwingen, Ereignisse, Starten, nach neuesten suchen, Benachrichtigungen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82aff7adedc9e490520851ad8c8e87fad60abf0a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926079"
---
# <a name="manage-event-based-forced-updates"></a>Verwalten von ereignisbasierten erzwungenen Updates

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

mit Microsoft Defender Antivirus können Sie ermitteln, ob Updates nach bestimmten Ereignissen erfolgen sollen (oder nicht), z. B. beim Start oder nach Erhalt bestimmter Berichte vom über die Cloud bereitgestellten Schutzdienst.

## <a name="check-for-protection-updates-before-running-a-scan"></a>Suchen nach Schutzupdates vor dem Ausführen einer Überprüfung

Sie können Microsoft Endpoint Configuration Manager, Gruppenrichtlinien, PowerShell-Cmdlets und WMI verwenden, um Microsoft Defender Antivirus zu erzwingen, Schutzupdates zu überprüfen und herunterzuladen, bevor Sie eine geplante Überprüfung ausführen.

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>Verwenden von Configuration Manager zum Suchen nach Schutzupdates vor dem Ausführen einer Überprüfung

1. Öffnen Sie in ihrer Microsoft Endpoint Manager Konsole die Antischadsoftwarerichtlinie, die Sie ändern möchten (klicken Sie im Navigationsbereich auf der linken Seite auf **"Ressourcen und Kompatibilität",** und erweitern Sie dann die Struktur auf **"Übersicht** Endpoint Protection Richtlinien für  >    >  **Antischadsoftware")**

2. Wechseln Sie zum Abschnitt **"Geplante Scans",** und legen **Sie "Überprüfen auf die neuesten Sicherheitsupdates"** fest, bevor Sie eine Überprüfung auf **"Ja"** ausführen.

3. Klicken Sie auf **OK**.

4. [Stellen Sie die aktualisierte Richtlinie wie gewohnt bereit.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>Verwenden von Gruppenrichtlinien zum Suchen nach Schutzupdates vor dem Ausführen einer Überprüfung

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Navigieren Sie mithilfe des **Gruppenrichtlinienverwaltungs-Editors** zur **Computerkonfiguration.**

3. Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**

4. Erweitern Sie die Struktur, um **komponenten Microsoft Defender Antivirus**  >  Scan **Windows.**  >  

5. Doppelklicken Sie auf **"Nach den neuesten Viren- und Spywaredefinitionen suchen", bevor Sie einen geplanten Scan ausführen,** und legen Sie die Option auf **"Aktiviert"** fest.

6. Klicken Sie auf **OK**.

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>Verwenden von PowerShell-Cmdlets zum Suchen nach Schutzupdates vor dem Ausführen einer Überprüfung

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

Weitere Informationen finden Sie unter [PowerShell-Cmdlets verwenden, um Microsoft Defender Antivirus zu konfigurieren und auszuführen](use-powershell-cmdlets-microsoft-defender-antivirus.md) und unter [Defender-Cmdlets](/powershell/module/defender/index).

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>Verwenden Windows Management Instruction (WMI) zum Suchen nach Schutzupdates vor dem Ausführen einer Überprüfung

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
CheckForSignaturesBeforeRunningScan
```

Weitere Informationen finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="check-for-protection-updates-on-startup"></a>Suchen nach Schutzupdates beim Start

Mithilfe von Gruppenrichtlinien können Sie erzwingen, dass Microsoft Defender Antivirus Schutzupdates beim Starten des Computers überprüfen und herunterladen.

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Navigieren Sie mithilfe des **Gruppenrichtlinienverwaltungs-Editors** zur **Computerkonfiguration.**

3. Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**

4. Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Security Intelligence Updates.**

5. Doppelklicken **Sie beim Start auf "Nach den neuesten Viren- und Spywaredefinitionen suchen",** und legen Sie die Option auf **"Aktiviert"** fest. 

6. Klicken Sie auf **OK**.

Sie können auch Gruppenrichtlinien, PowerShell oder WMI verwenden, um Microsoft Defender Antivirus zu konfigurieren, um beim Start nach Updates zu suchen, auch wenn sie nicht ausgeführt wird.

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Verwenden von Gruppenrichtlinien zum Herunterladen von Updates, wenn Microsoft Defender Antivirus nicht vorhanden ist

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Wechseln Sie mithilfe des **Gruppenrichtlinienverwaltungs-Editors** zur **Computerkonfiguration.**

3. Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**

4. Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Security Intelligence Updates.**

5. Doppelklicken Sie **beim Start auf "Security Intelligence Update initiieren",** und legen Sie die Option auf **"Aktiviert"** fest.

6. Klicken Sie auf **OK**.

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Verwenden von PowerShell-Cmdlets zum Herunterladen von Updates, wenn Microsoft Defender Antivirus nicht vorhanden ist

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

Weitere Informationen finden Sie unter [Verwenden von PowerShell-Cmdlets zum Verwalten von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets](/powershell/module/defender/index) für weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Verwenden Windows Management Instruction (WMI) zum Herunterladen von Updates, wenn Microsoft Defender Antivirus nicht vorhanden ist

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

Weitere Informationen finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>Zulassen von Ad-hoc-Änderungen am Schutz basierend auf dem über die Cloud bereitgestellten Schutz

Microsoft Defender AV kann Änderungen an seinem Schutz basierend auf dem über die Cloud bereitgestellten Schutz vornehmen. Solche Änderungen können außerhalb von normalen oder geplanten Schutzupdates auftreten.

Wenn Sie den über die Cloud bereitgestellten Schutz aktiviert haben, sendet Microsoft Defender AV Dateien, die verdächtig sind, an die Windows Defender Cloud. Wenn der Clouddienst meldet, dass die Datei bösartig ist und die Datei in einem kürzlichen Schutzupdate erkannt wird, können Sie Mithilfe von Gruppenrichtlinien Microsoft Defender AV so konfigurieren, dass dieses Schutzupdate automatisch empfangen wird. Es können auch andere wichtige Schutzupdates angewendet werden.

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>Verwenden von Gruppenrichtlinien zum automatischen Herunterladen der neuesten Updates basierend auf dem über die Cloud bereitgestellten Schutz

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Navigieren Sie mithilfe des **Gruppenrichtlinienverwaltungs-Editors** zur **Computerkonfiguration.**

3. Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**

4. Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Security Intelligence Updates.**

5. Doppelklicken Sie auf Updates zur **Echtzeitsicherheitserkennung basierend auf Berichten an Microsoft MAPS zulassen,** und legen Sie die Option auf **"Aktiviert"** fest. Klicken Sie anschließend auf **OK**.

6. **Zulassen, dass Benachrichtigungen definitionsbasierte Berichte an Microsoft MAPS deaktivieren** und die Option auf **"Aktiviert"** festlegen. Klicken Sie anschließend auf **OK**.
    
> [!NOTE]
> **Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports. Sie müssen Ihren Computer so konfigurieren, dass er Microsoft MAPS beitritt, damit diese Funktion funktioniert.

## <a name="see-also"></a>Siehe auch

- [Bereitstellen von Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)