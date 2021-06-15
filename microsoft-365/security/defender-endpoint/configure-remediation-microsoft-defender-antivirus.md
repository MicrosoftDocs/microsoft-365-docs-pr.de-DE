---
title: Festlegen von Gegenmaßnahmen für Microsoft Defender Antivirus-Erkennungen
description: Konfigurieren, was Microsoft Defender Antivirus tun sollten, wenn eine Bedrohung erkannt wird und wie lange isolierte Dateien im Quarantäneordner aufbewahrt werden sollen
keywords: Korrektur, beheben, entfernen, Bedrohungen, Quarantäne, Scannen, Wiederherstellen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 9b765d14e31d6c4890aeace41e4fe79bafdd889e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925575"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Festlegen von Gegenmaßnahmen für Microsoft Defender Antivirus-Erkennungen


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Wenn Microsoft Defender Antivirus eine Überprüfung ausführt, wird versucht, erkannte Bedrohungen zu beheben oder zu entfernen. Sie können konfigurieren, wie Microsoft Defender Antivirus bestimmte Bedrohungen behandeln, ob vor der Behebung ein Wiederherstellungspunkt erstellt und wann Bedrohungen entfernt werden sollen.

In diesem Artikel wird beschrieben, wie Sie diese Einstellungen mithilfe von Gruppenrichtlinien konfigurieren. Sie können jedoch auch [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) und [Microsoft Intune](/intune/device-restrictions-configure)verwenden. 

Sie können diese Einstellungen auch mit dem [ `Set-MpPreference` PowerShell-Cmdlet](/powershell/module/defender/set-mppreference) oder der [ `MSFT_MpPreference` WMI-Klasse](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) konfigurieren.

## <a name="configure-remediation-options"></a>Konfigurieren von Korrekturoptionen

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen** aus.

3. Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus.** 

4. Wählen Sie in der folgenden Tabelle einen Speicherort aus, und bearbeiten Sie die Richtlinie nach Bedarf. 

5. Wählen Sie **OK** aus.

|Speicherort | Einstellung | Beschreibung | Standardeinstellung (falls nicht konfiguriert) |
|:---|:---|:---|:---|
|Überprüfung | Erstellen eines Systemwiederherstellungspunkts | Ein Systemwiederherstellungspunkt wird jeden Tag erstellt, bevor eine Bereinigung oder Überprüfung versucht wird. | Deaktiviert|
|Überprüfung | Aktivieren des Entfernens von Elementen aus dem Scanverlaufsordner | Angeben, wie viele Tage Elemente im Scanverlauf aufbewahrt werden sollen | 30 Tage |
|wurzel | Turn off routine remediation | Sie können angeben, ob Microsoft Defender Antivirus Bedrohungen automatisch behebt oder ob der Endpunktbenutzer gefragt werden soll, was zu tun ist. | Deaktiviert (Bedrohungen werden automatisch behoben) |
|Quarantäne | Konfigurieren des Entfernens von Elementen aus dem Quarantäneordner | Angeben, wie viele Tage Elemente in Quarantäne bleiben sollen, bevor sie entfernt werden | 90 Tage |
|Risiken | Angeben von Bedrohungswarnungsebenen, bei denen bei Erkennung keine Standardaktion ausgeführt werden soll | Jeder Bedrohung, die von Microsoft Defender Antivirus erkannt wird, wird eine Bedrohungsstufe zugewiesen (niedrig, mittel, hoch oder schwerwiegend). Sie können diese Einstellung verwenden, um zu definieren, wie alle Bedrohungen für die einzelnen Bedrohungsebenen behoben werden sollen (isoliert, entfernt oder ignoriert). | Nicht zutreffend |
|Risiken | Angeben von Bedrohungen, bei denen bei Erkennung keine Standardaktion ausgeführt werden soll | Geben Sie an, wie bestimmte Bedrohungen (unter Verwendung ihrer Bedrohungs-ID) behoben werden sollen. Sie können angeben, ob die spezifische Bedrohung unter Quarantäne gestellt, entfernt oder ignoriert werden soll. | Nicht zutreffend |

> [!IMPORTANT]
> Microsoft Defender Antivirus erkennt und behebt Dateien basierend auf vielen Faktoren. Manchmal ist für den Abschluss einer Korrektur ein Neustart erforderlich. Auch wenn die Erkennung später als falsch positiv eingestuft wird, muss der Neustart abgeschlossen sein, um sicherzustellen, dass alle zusätzlichen Korrekturschritte abgeschlossen wurden.
>
> Wenn Sie sicher sind, Microsoft Defender Antivirus eine Datei basierend auf einem falsch positiven Ergebnis unter Quarantäne gestellt wurde, können Sie die Datei nach dem Neustart des Geräts aus der Quarantäne wiederherstellen. Siehe [Wiederherstellen von isolierten Dateien in Microsoft Defender Antivirus](restore-quarantined-files-microsoft-defender-antivirus.md).
> 
> Um dieses Problem in Zukunft zu vermeiden, können Sie Dateien von den Scans ausschließen. Weitere Informationen finden Sie unter [Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender Antivirus Scans.](configure-exclusions-microsoft-defender-antivirus.md)

Weitere Informationen finden Sie unter [Configure remediation-required scheduled full Microsoft Defender Antivirus scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) for more remediation-related settings.

## <a name="see-also"></a>Siehe auch

- [Konfigurieren der Scanoptionen von Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Konfigurieren von geplanten Microsoft Defender Antivirus Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Konfigurieren und Ausführen von bedarfsgesteuerten Scans durch Microsoft Defender Antivirus](run-scan-microsoft-defender-antivirus.md)
- [Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden](configure-notifications-microsoft-defender-antivirus.md)
- [Konfigurieren der Endbenutzerinteraktion Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus Überprüfungen und Korrekturen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
