---
title: Anwenden Microsoft Defender Antivirus Updates nach bestimmten Ereignissen
description: Verwalten, Microsoft Defender Antivirus Sicherheitsintelligenzupdates nach dem Starten oder Empfangen von in der Cloud übermittelten Erkennungsberichten angewendet werden.
keywords: updates, protection, force updates, events, startup, check for latest, notifications
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 624e32bfebfce02021f1dcb1dbdde9446472239a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274700"
---
# <a name="manage-event-based-forced-updates"></a>Verwalten von ereignisbasierten erzwungenen Updates

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus können Sie bestimmen, ob Updates nach bestimmten Ereignissen auftreten sollten (oder nicht), z. B. beim Start oder nach dem Empfangen bestimmter Berichte vom cloudbasierten Schutzdienst.

## <a name="check-for-protection-updates-before-running-a-scan"></a>Überprüfen sie vor dem Ausführen einer Überprüfung auf Schutzupdates.

Sie können Microsoft Endpoint Configuration Manager, Gruppenrichtlinien, PowerShell-Cmdlets und WMI verwenden, um zu erzwingen, dass Microsoft Defender Antivirus Schutzupdates überprüfen und herunterladen, bevor Sie eine geplante Überprüfung ausführen.

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>Verwenden von Configuration Manager zum Überprüfen von Schutzupdates vor dem Ausführen einer Überprüfung

1. Öffnen Sie Microsoft Endpoint Manager der Microsoft Endpoint Manager-Konsole die Richtlinie für Antischarten, die Sie ändern möchten (klicken Sie im Navigationsbereich links auf Ressourcen und Kompatibilität, und erweitern Sie dann die Struktur auf Übersicht   >  **Endpoint Protection**  >  **Antischalwarerichtlinien**)

2. Wechseln Sie zum **Abschnitt Geplante Scans,** und legen Sie Auf die neuesten Sicherheitsintelligenzupdates **überprüfen fest,** bevor Sie eine Überprüfung auf **Ja ausführen.**

3. Klicken Sie auf **OK**.

4. [Stellen Sie die aktualisierte Richtlinie wie gewohnt aus.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>Verwenden von Gruppenrichtlinien zum Überprüfen von Schutzupdates vor dem Ausführen einer Überprüfung

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie **mit dem Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

3. Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**

4. Erweitern Sie die Struktur, **Windows komponenten Microsoft Defender Antivirus**  >    >  **scannen**.

5. Doppelklicken Sie auf **Die neuesten Viren-** und Spywaredefinitionen überprüfen, bevor Sie einen geplanten Scan ausführen, und legen Sie die Option auf Aktiviert **fest.**

6. Klicken Sie auf **OK**.

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>Verwenden von PowerShell-Cmdlets zum Überprüfen von Schutzupdates vor dem Ausführen einer Überprüfung

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

Weitere Informationen finden Sie unter [PowerShell-Cmdlets verwenden, um Microsoft Defender Antivirus zu konfigurieren und auszuführen](use-powershell-cmdlets-microsoft-defender-antivirus.md) und unter [Defender-Cmdlets](/powershell/module/defender/index).

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>Verwenden Windows Management Instruction (WMI), um vor dem Ausführen einer Überprüfung nach Schutzupdates zu suchen

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
CheckForSignaturesBeforeRunningScan
```

Weitere Informationen finden Sie unter [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="check-for-protection-updates-on-startup"></a>Überprüfen auf Schutzupdates beim Start

Sie können Gruppenrichtlinien verwenden, um Microsoft Defender Antivirus, schutzupdates zu überprüfen und herunterzuladen, wenn der Computer gestartet wird.

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie **mit dem Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

3. Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**

4. Erweitern Sie die Struktur, **Windows komponenten**  >  **Microsoft Defender Antivirus**  >  **Security Intelligence Updates .**

5. Doppelklicken Sie **auf Die neuesten Viren-** und Spywaredefinitionen beim Start überprüfen, und legen Sie die Option auf **Aktiviert .** 

6. Klicken Sie auf **OK**.

Sie können auch Gruppenrichtlinien, PowerShell oder WMI verwenden, um Microsoft Defender Antivirus zu konfigurieren, um beim Start nach Updates zu suchen, auch wenn sie nicht ausgeführt wird.

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Verwenden von Gruppenrichtlinien zum Herunterladen von Updates, Microsoft Defender Antivirus nicht vorhanden ist

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie **mit dem Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

3. Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**

4. Erweitern Sie die Struktur, **Windows komponenten**  >  **Microsoft Defender Antivirus**  >  **Security Intelligence Updates .**

5. Doppelklicken Sie beim **Start auf Sicherheitsintelligenzupdate initiieren,** und legen Sie die Option auf **Aktiviert .**

6. Klicken Sie auf **OK**.

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Verwenden von PowerShell-Cmdlets zum Herunterladen von Updates, Microsoft Defender Antivirus nicht vorhanden ist

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

Weitere Informationen finden Sie unter [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Verwenden Windows Management Instruction (WMI) zum Herunterladen von Updates, Microsoft Defender Antivirus nicht vorhanden ist

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

Weitere Informationen finden Sie unter [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>Zulassen von Ad-hoc-Änderungen am Schutz basierend auf cloudbasiertem Schutz

Microsoft Defender AV kann änderungen an seinem Schutz basierend auf cloudbasiertem Schutz vornehmen. Solche Änderungen können außerhalb normaler oder geplanter Schutzupdates auftreten.

Wenn Sie den in der Cloud übermittelten Schutz aktiviert haben, sendet Microsoft Defender AV Dateien, die verdächtig sind, an die Windows Defender Cloud. Wenn der Clouddienst meldet, dass die Datei schädlich ist und die Datei in einem aktuellen Schutzupdate erkannt wird, können Sie mithilfe von Gruppenrichtlinien Microsoft Defender AV so konfigurieren, dass dieses Schutzupdate automatisch empfangen wird. Es können auch andere wichtige Schutzupdates angewendet werden.

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>Verwenden von Gruppenrichtlinien zum automatischen Herunterladen aktueller Updates basierend auf cloudbasiertem Schutz

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie **mit dem Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

3. Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**

4. Erweitern Sie die Struktur, **Windows komponenten**  >  **Microsoft Defender Antivirus**  >  **Security Intelligence Updates .**

5. Doppelklicken Sie **auf Echtzeit-Sicherheitsintelligenzupdates** basierend auf Berichten an Microsoft MAPS zulassen, und legen Sie die Option auf Aktiviert **.** Klicken Sie anschließend auf **OK**.

6. **Zulassen, dass Benachrichtigungen definitionsbasierte Berichte für Microsoft MAPS** deaktivieren und die Option auf Aktiviert **festlegen.** Klicken Sie anschließend auf **OK**.
    
> [!NOTE]
> **Wenn Sie Benachrichtigungen zum Deaktivieren definitionsbasierter Berichte** zulassen, können sie von Microsoft MAPS deaktiviert werden, wenn bekannt ist, dass falsch positive Berichte verursacht werden. Sie müssen Ihren Computer so konfigurieren, dass er Microsoft MAPS beitritt, damit diese Funktion funktioniert.

## <a name="see-also"></a>Siehe auch

- [Bereitstellen Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Baselines](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)