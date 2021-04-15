---
title: Konfigurieren der Korrektur für Microsoft Defender Antivirus-Erkennungen
description: Konfigurieren, was Microsoft Defender Antivirus beim Erkennen einer Bedrohung tun soll und wie lange isolierte Dateien im Quarantäneordner aufbewahrt werden sollen
keywords: Beheben, Beheben, Entfernen, Bedrohungen, Quarantäne, Scannen, Wiederherstellen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 98bc079bcfd772ada52d699d5f873a187d4ab4c1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765059"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Konfigurieren der Korrektur für Microsoft Defender Antivirus-Erkennungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Wenn Microsoft Defender Antivirus eine Überprüfung ausgeführt hat, versucht es, erkannte Bedrohungen zu beseitigen oder zu entfernen. Sie können konfigurieren, wie Microsoft Defender Antivirus bestimmte Bedrohungen adressieren soll, ob vor der Behebung ein Wiederherstellungspunkt erstellt werden soll und wann Bedrohungen entfernt werden sollen.

In diesem Artikel wird beschrieben, wie Diese Einstellungen mithilfe von Gruppenrichtlinien konfiguriert werden. Sie können jedoch auch [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) und Microsoft Intune [verwenden.](/intune/device-restrictions-configure) 

Sie können diese Einstellungen auch mithilfe des [ `Set-MpPreference` PowerShell-Cmdlets](/powershell/module/defender/set-mppreference) oder der [ `MSFT_MpPreference` WMI-Klasse](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) konfigurieren.

## <a name="configure-remediation-options"></a>Konfigurieren von Korrekturoptionen

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**

3. Erweitern Sie die Struktur auf **Windows-Komponenten**  >  **Microsoft Defender Antivirus**. 

4. Wählen Sie in der folgenden Tabelle einen Speicherort aus, und bearbeiten Sie die Richtlinie nach Bedarf. 

5. Wählen Sie **OK** aus.

|Speicherort | Einstellung | Beschreibung | Standardeinstellung (wenn nicht konfiguriert) |
|:---|:---|:---|:---|
|Überprüfung | Erstellen eines Systemwiederherstellungspunkts | Ein Systemwiederherstellungspunkt wird jeden Tag erstellt, bevor eine Bereinigung oder Überprüfung versucht wird | Deaktiviert|
|Überprüfung | Aktivieren des Entfernens von Elementen aus dem Ordner "Scanverlauf" | Angeben, wie viele Tage Elemente im Scanverlauf aufbewahrt werden sollen | 30 Tage |
|Root | Deaktivieren der Routinebehebung | Sie können angeben, ob Microsoft Defender Antivirus Bedrohungen automatisch abwehrt oder ob der Endpunktbenutzer gefragt werden soll, was er tun soll. | Deaktiviert (Bedrohungen werden automatisch behoben) |
|Quarantäne | Konfigurieren des Entfernens von Elementen aus dem Quarantäneordner | Angeben, wie viele Tage Elemente in Quarantäne aufbewahrt werden sollen, bevor sie entfernt werden | 90 Tage |
|Risiken | Angeben von Warnungsstufen für Bedrohungen, bei denen beim Erkennen keine Standardaktion ergriffen werden soll | Jeder Bedrohung, die von Microsoft Defender Antivirus erkannt wird, wird eine Bedrohungsstufe zugewiesen (niedrig, mittel, hoch oder schwer). Mit dieser Einstellung können Sie definieren, wie alle Bedrohungen für jede Bedrohungsebene behoben werden sollen (isoliert, entfernt oder ignoriert) | Nicht zutreffend |
|Risiken | Angeben von Bedrohungen, bei denen die Standardaktion beim Erkennen nicht ergriffen werden soll | Geben Sie an, wie bestimmte Bedrohungen (mithilfe ihrer Bedrohungs-ID) behoben werden sollen. Sie können angeben, ob die bestimmte Bedrohung isoliert, entfernt oder ignoriert werden soll. | Nicht zutreffend |

> [!IMPORTANT]
> Microsoft Defender Antivirus erkennt und saniert Dateien basierend auf vielen Faktoren. Manchmal erfordert das Abschließen einer Korrektur einen Neustart. Auch wenn die Erkennung später als falsch positiv ermittelt wird, muss der Neustart abgeschlossen sein, um sicherzustellen, dass alle zusätzlichen Korrekturschritte abgeschlossen wurden.
>
> Wenn Sie sicher sind, dass Microsoft Defender Antivirus eine Datei basierend auf einem falsch positiven Ergebnis isoliert hat, können Sie die Datei nach dem Neustart des Geräts aus der Quarantäne wiederherstellen. Weitere [Informationen finden Sie unter Restore quarantined files in Microsoft Defender Antivirus](restore-quarantined-files-microsoft-defender-antivirus.md).
> 
> Um dieses Problem in Zukunft zu vermeiden, können Sie Dateien aus den Scans ausschließen. Weitere [Informationen finden Sie unter Configure and validate exclusions for Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md).

Weitere Informationen [finden Sie unter Configure remediation-required scheduled full Microsoft Defender Antivirus scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) for more remediation related settings.

## <a name="see-also"></a>Siehe auch

- [Konfigurieren von Microsoft Defender Antivirus-Überprüfungsoptionen](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Konfigurieren geplanter Microsoft Defender Antivirus-Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Konfigurieren und Ausführen von Bedarfsscans von Microsoft Defender Antivirus](run-scan-microsoft-defender-antivirus.md)
- [Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden](configure-notifications-microsoft-defender-antivirus.md)
- [Konfigurieren der Microsoft Defender Antivirus-Endbenutzerinteraktion](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus-Scans und -Korrekturen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)