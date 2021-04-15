---
title: Planen von Microsoft Defender Antivirus-Schutzupdates
description: Planen des Tages, der Uhrzeit und des Intervalls für den Zeitpunkt des Herunterladens von Schutzupdates
keywords: Updates, Sicherheitsgrundwerte, Zeitplanupdates
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 327974c4db4166301820cf148811aceda1700513
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765347"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>Verwalten des Zeitplans für den Download und die Anwendung von Schutzupdates

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Mit Microsoft Defender Antivirus können Sie bestimmen, wann Updates suchen und heruntergeladen werden sollen.

Sie können Updates für Ihre Endpunkte planen, indem Sie: 

- Angeben des Wochentags, der auf Schutzupdates überprüft werden soll 
- Angeben des Intervalls, das auf Schutzupdates überprüft werden soll
- Angeben der Zeit für die Überprüfung auf Schutzupdates

Sie können auch die Zeiten randomisieren, zu denen jeder Endpunkt Schutzupdates überprüft und herunterlässt. Weitere Informationen [finden](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Sie im Thema Zeitplanscans.

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Planen von Schutzupdates mithilfe von Configuration Manager

1.  Öffnen Sie in der Microsoft Endpoint Manager-Konsole die Richtlinie  für Antischarten, die Sie ändern möchten (klicken Sie im Navigationsbereich links auf Ressourcen und Kompatibilität, und erweitern Sie dann die Struktur zu **Übersicht**  >  **Endpoint Protection**  >  **Anmalware Policies**)

2.  Wechseln Sie zum Abschnitt **Security Intelligence Updates.**

3. So überprüfen und laden Sie Updates zu einem bestimmten Zeitpunkt herunter:
      1. Legen **Sie die Überprüfung auf Endpoint Protection Security Intelligence-Updates in einem bestimmten Intervall... auf** **0 fest.**
      2. Legen **Sie täglich check for Endpoint Protection security intelligence updates at...** auf den Zeitpunkt, zu dem Updates überprüft werden sollen.
      3
4. Um Updates in einem kontinuierlichen Intervall zu überprüfen und herunterzuladen, legen Sie Die Überprüfung auf Endpoint Protection-Sicherheitsintelligenzupdates in einem bestimmten Intervall **fest...** auf die Anzahl der Stunden, die zwischen Updates auftreten sollten.

5.  [Stellen Sie die aktualisierte Richtlinie wie gewohnt aus.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="use-group-policy-to-schedule-protection-updates"></a>Planen von Schutzupdates mithilfe von Gruppenrichtlinien

> [!IMPORTANT]
> Standardmäßig sucht Microsoft Defender Antivirus 15 Minuten vor dem Zeitpunkt geplanter Scans nach einem Update. Wenn Sie diese Einstellungen aktivieren, wird diese Standardeinstellung überschrieben.

1.  Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

3.  Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

4.  Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**

5.  Erweitern Sie die Struktur auf **Windows-Komponenten**  >  **Microsoft Defender Antivirus** Signature Intelligence  >  **Updates,** und konfigurieren Sie die folgenden Einstellungen:

    1. Doppelklicken Sie auf die Einstellung Tag **der** Woche angeben, um nach Sicherheitsintelligenzupdates zu suchen, und legen Sie die Option auf **Aktiviert fest.** Geben Sie den Wochentag ein, um nach Updates zu suchen. Klicken Sie auf **OK**.
    2. Doppelklicken Sie auf die Einstellung Intervall **angeben, um nach** Sicherheitsintelligenzupdates zu suchen, und legen Sie die Option auf **Aktiviert fest.** Geben Sie die Anzahl der Stunden zwischen Updates ein. Klicken Sie auf **OK**.
    3. Doppelklicken Sie auf die Einstellung Zeit **zum Überprüfen** von Sicherheitsintelligenzupdates angeben, und legen Sie die Option auf **Aktiviert fest.** Geben Sie den Zeitpunkt ein, zu dem Updates überprüft werden sollen. Die Uhrzeit basiert auf der Ortszeit des Endpunkts. Klicken Sie auf **OK**.


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>Verwenden von PowerShell-Cmdlets zum Planen von Schutzupdates

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>Planen von Schutzupdates mithilfe von Windows Management Instruction (WMI)

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

Weitere Informationen und zulässige Parameter finden Sie im Folgenden:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>Verwandte Artikel

- [Bereitstellen von Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Basiswerten](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Verwalten ereignisbasierter erzwungener Updates](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Verwalten von Updates für mobile Geräte und virtuelle Computer (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)