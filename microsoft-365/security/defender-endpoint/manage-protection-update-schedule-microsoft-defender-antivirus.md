---
title: Planen Microsoft Defender Antivirus Schutzupdates
description: Planen des Tages, der Uhrzeit und des Intervalls für den Download von Schutzupdates
keywords: Updates, Sicherheitsgrundwerte, Updates planen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: abb656586d6a7bd779b109fcad3c777016fef980
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926055"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>Verwalten des Zeitplans für Download und Anwendung von Schutzupdates

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus können Sie bestimmen, wann updates gesucht und heruntergeladen werden sollen.

Sie können Updates für Ihre Endpunkte planen, indem Sie: 

- Angeben des Wochentags, an dem nach Schutzupdates gesucht werden soll 
- Angeben des zu überprüfenden Intervalls für Schutzupdates
- Angeben der Zeit für die Suche nach Schutzupdates

Sie können auch zufällig festlegen, wann jeder Endpunkt Schutzupdates überprüft und herunterlädt. Weitere Informationen finden Sie im Thema ["Scans planen".](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Verwenden von Configuration Manager zum Planen von Schutzupdates

1.  Öffnen Sie in ihrer Microsoft Endpoint Manager Konsole die Antischadsoftwarerichtlinie, die Sie ändern möchten (klicken Sie im Navigationsbereich auf der linken Seite auf **"Ressourcen und Kompatibilität",** und erweitern Sie dann die Struktur auf **"Übersicht** Endpoint Protection Richtlinien für  >    >  **Antischadsoftware")**

2.  Wechseln Sie zum Abschnitt **"Security Intelligence Updates".**

3. So überprüfen und laden Sie Updates zu einem bestimmten Zeitpunkt herunter:
      1. Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.
      2. Legen **Sie Check for Endpoint Protection security intelligence updates daily** at... auf den Zeitpunkt fest, zu dem Updates überprüft werden sollen.
      3
4. Um Updates in einem kontinuierlichen Intervall zu überprüfen und herunterzuladen, legen **Sie die Suche nach Endpoint Protection Sicherheitsupdates in einem bestimmten Intervall...** auf die Anzahl der Stunden fest, die zwischen Updates auftreten sollten.

5.  [Stellen Sie die aktualisierte Richtlinie wie gewohnt bereit.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="use-group-policy-to-schedule-protection-updates"></a>Verwenden von Gruppenrichtlinien zum Planen von Schutzupdates

> [!IMPORTANT]
> Standardmäßig sucht Microsoft Defender Antivirus 15 Minuten vor dem Zeitpunkt geplanter Scans nach einem Update. Wenn Sie diese Einstellungen aktivieren, wird diese Standardeinstellung überschrieben.

1.  Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

3.  Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**

4.  Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**

5.  Erweitern Sie die Struktur bis **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Signature Intelligence Updates,** und konfigurieren Sie die folgenden Einstellungen:

    1. Doppelklicken Sie auf den Tag der Woche angeben, um nach der Einstellung **für Sicherheitsupdates zu suchen,** und legen Sie die Option auf **"Aktiviert"** fest. Geben Sie den Wochentag ein, an dem nach Updates gesucht werden soll. Klicken Sie auf **OK**.
    2. Doppelklicken Sie auf die Einstellung **"Intervall zum Suchen** nach Sicherheitsupdates angeben", und legen Sie die Option auf **"Aktiviert"** fest. Geben Sie die Anzahl der Stunden zwischen Updates ein. Klicken Sie auf **OK**.
    3. Doppelklicken Sie auf die Einstellung **"Zeitpunkt für die Überprüfung auf Sicherheitsupdates angeben",** und legen Sie die Option auf **"Aktiviert"** fest. Geben Sie den Zeitpunkt ein, zu dem Updates überprüft werden sollen. Die Uhrzeit basiert auf der Ortszeit des Endpunkts. Klicken Sie auf **OK**.


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>Verwenden von PowerShell-Cmdlets zum Planen von Schutzupdates

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus und [Defender-Cmdlets.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>Verwenden Windows Management Instruction (WMI) zum Planen von Schutzupdates

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

Weitere Informationen und zulässige Parameter finden Sie in den folgenden Themen:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>Verwandte Artikel

- [Bereitstellen von Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Verwalten von ereignisbasierten erzwungenen Updates](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)