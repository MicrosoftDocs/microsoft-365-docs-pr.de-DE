---
title: Planen Microsoft Defender Antivirus Von Schutzupdates
description: Planen des Tages, der Uhrzeit und des Intervalls für den Zeitpunkt des Herunterladens von Schutzupdates
keywords: Updates, Sicherheitsgrundwerte, Zeitplanupdates
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 26b88b8677c27a5d6615776a371326e37034afd4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275036"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>Verwalten des Zeitplans für Download und Anwendung von Schutzupdates

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus können Sie bestimmen, wann updates suchen und heruntergeladen werden sollen.

Sie können Updates für Ihre Endpunkte planen, indem Sie: 

- Angeben des Wochentags, der auf Schutzupdates überprüft werden soll 
- Angeben des Intervalls, das auf Schutzupdates überprüft werden soll
- Angeben der Zeit für die Überprüfung auf Schutzupdates

Sie können auch die Zeiten randomisieren, zu denen jeder Endpunkt Schutzupdates überprüft und herunterlässt. Weitere Informationen [finden](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Sie im Thema Zeitplanscans.

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Planen von Schutzupdates mithilfe von Configuration Manager

1.  Öffnen Sie Microsoft Endpoint Manager der Microsoft Endpoint Manager-Konsole die Richtlinie für Antischarten, die Sie ändern möchten (klicken Sie im Navigationsbereich links auf Ressourcen und Kompatibilität, und erweitern Sie dann die Struktur auf Übersicht   >  **Endpoint Protection**  >  **Antischalwarerichtlinien**)

2.  Wechseln Sie zum Abschnitt **Security Intelligence Updates.**

3. So überprüfen und laden Sie Updates zu einem bestimmten Zeitpunkt herunter:
      1. Legen **Sie überprüfen Endpoint Protection Sicherheitsintelligenzupdates in einem bestimmten** Intervall fest... auf **0**.
      2. Legen **Sie check for Endpoint Protection security intelligence updates daily at...** auf den Zeitpunkt, zu dem Updates überprüft werden sollen.
      3
4. Um Updates in einem kontinuierlichen Intervall zu überprüfen und herunterzuladen, legen Sie die Überprüfung auf Endpoint Protection Sicherheitsintelligenzupdates in einem bestimmten Intervall **fest...** auf die Anzahl der Stunden, die zwischen Updates auftreten sollten.

5.  [Stellen Sie die aktualisierte Richtlinie wie gewohnt aus.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="use-group-policy-to-schedule-protection-updates"></a>Planen von Schutzupdates mithilfe von Gruppenrichtlinien

> [!IMPORTANT]
> Standardmäßig wird Microsoft Defender Antivirus 15 Minuten vor dem Zeitpunkt geplanter Scans auf ein Update überprüft. Wenn Sie diese Einstellungen aktivieren, wird diese Standardeinstellung überschrieben.

1.  Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

3.  Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

4.  Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**

5.  Erweitern Sie die **Struktur, Windows komponenten**  >  **Microsoft Defender Antivirus**  >  **Signature Intelligence Updates** und konfigurieren Sie die folgenden Einstellungen:

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

Unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets](/powershell/module/defender/) finden Sie weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus.

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>Verwenden Windows Management Instruction (WMI) zum Planen von Schutzupdates

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

Weitere Informationen und zulässige Parameter finden Sie im Folgenden:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>Verwandte Artikel

- [Bereitstellen Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Baselines](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Verwalten von ereignisbasierten erzwungenen Updates](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)