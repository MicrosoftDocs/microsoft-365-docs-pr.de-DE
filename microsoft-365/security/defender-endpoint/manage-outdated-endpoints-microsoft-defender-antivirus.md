---
title: Anwenden von Microsoft Defender AV-Schutzupdates auf veraltete Endpunkte
description: Definieren Sie, wann und wie Updates für Endpunkte angewendet werden sollen, die in einer Weile nicht aktualisiert wurden.
keywords: updates, protection, out-of-date, outdated, old, catch-up
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4199f55488ef0dc5989af88e8be83a3d51190d1f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275060"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>Verwalten von Updates und Scans von Microsoft Defender Antivirus für veraltete Endpunkte

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus können Sie definieren, wie lange ein Endpunkt ein Update vermeiden kann oder wie viele Scans er verpassen kann, bevor er selbst aktualisiert und überprüft werden muss. Dies ist besonders in Umgebungen hilfreich, in denen Geräte nicht häufig mit einem Unternehmens- oder externen Netzwerk verbunden sind oder geräte, die nicht täglich verwendet werden.

Beispielsweise ist ein Mitarbeiter, der einen bestimmten PC verwendet, drei Tage in Der Pause und loggt sich während dieser Zeit nicht bei ihrem PC an.

Wenn der Benutzer zur Arbeit zurückkehrt und sich am PC anmeldet, Microsoft Defender Antivirus sofort die neuesten Schutzupdates überprüfen und herunterladen und eine Überprüfung ausführen.

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>Einrichten von Nachholschutzupdates für Endpunkte, die eine Weile nicht aktualisiert wurden

Wenn Microsoft Defender Antivirus schutzupdates für einen bestimmten Zeitraum nicht heruntergeladen haben, können Sie es so einrichten, dass das neueste Update bei der nächsten Anmeldung automatisch überprüft und heruntergeladen wird. Dies ist nützlich, wenn Sie beim Start [die Downloads automatischer Updates global deaktiviert haben.](manage-event-based-updates-microsoft-defender-antivirus.md)

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>Konfigurieren von Nachholschutzupdates mithilfe von Configuration Manager

1.  Öffnen Sie Microsoft Endpoint Manager der Microsoft Endpoint Manager-Konsole die Richtlinie für Antischarten, die Sie ändern möchten (klicken Sie im Navigationsbereich links auf Ressourcen und Kompatibilität, und erweitern Sie dann die Struktur auf Übersicht   >  **Endpoint Protection**  >  **Antischalwarerichtlinien**)

2.  Wechseln Sie zum Abschnitt **Sicherheitsintelligenzupdates,** und konfigurieren Sie die folgenden Einstellungen:

    1. Legen **Sie Force a security intelligence update fest, wenn der Clientcomputer für** mehr als zwei aufeinander folgende geplante Updates offline ist, auf **Ja**.
    2. Geben Sie  **für if Configuration Manager als** Quelle für Sicherheitsintelligenzupdates... die Stunden an, bevor die von Configuration Manager übermittelten Schutzupdates als veraltet betrachtet werden sollten. Dadurch wird der nächste Aktualisierungsspeicherort basierend auf der definierten [Fallbackquellenreihenfolge verwendet.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)

3. Klicken Sie auf **OK**.

4.  [Stellen Sie die aktualisierte Richtlinie wie gewohnt aus.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>Aktivieren und Konfigurieren des Nachholupdatefeatures mithilfe von Gruppenrichtlinien

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

3. Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**

4. Erweitern Sie die Struktur, **Windows komponenten > Microsoft Defender Antivirus > Signaturupdates .**

5. Doppelklicken Sie auf Die Anzahl **der** Tage definieren, nach denen ein Nachholupdate für die Sicherheitsintelligenz erforderlich ist, und legen Sie die Option auf **Aktiviert fest.** Geben Sie die Anzahl der Tage ein, nach denen Microsoft Defender AV das neueste Schutzupdate überprüfen und herunterladen soll.

6. Klicken Sie auf **OK**.

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>Konfigurieren von Nachholschutzupdates mithilfe von PowerShell-Cmdlets

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

Unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets](/powershell/module/defender/) finden Sie weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>Konfigurieren von Nachholschutzupdates mithilfe Windows Management Instruction (WMI)

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
SignatureUpdateCatchupInterval
```

Weitere Informationen und zulässige Parameter finden Sie im Folgenden:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>Festlegen der Anzahl von Tagen, bevor der Schutz als veraltet gemeldet wird

Sie können auch die Anzahl der Tage angeben, nach denen Microsoft Defender Antivirus schutz als alt oder veraltet betrachtet wird. Nach der angegebenen Anzahl von Tagen wird der Client sich selbst als veraltet melden und dem Benutzer des PCs einen Fehler anzeigen. Es kann auch dazu führen, dass Microsoft Defender Antivirus versuchen, ein Update [](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)aus anderen Quellen herunterzuladen (basierend auf der definierten Fallback-Quellreihenfolge), z. B. wenn MMPC als sekundäre Quelle verwendet wird, nachdem WSUS oder Microsoft Update als erste Quelle festgelegt wurde.

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>Verwenden von Gruppenrichtlinien zum Angeben der Anzahl von Tagen, bevor der Schutz als veraltet angesehen wird

1.  Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

3.  Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

4.  Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**

5.  Erweitern Sie die **Struktur, Windows Komponenten > Microsoft Defender Antivirus > Signaturupdates** hinzufügen und die folgenden Einstellungen konfigurieren:

    1.  Doppelklicken Sie auf Die Anzahl der Tage **definieren,** bevor Spywaredefinitionen als veraltet angesehen werden, und legen Sie die Option auf **Aktiviert fest.** Geben Sie die Anzahl der Tage ein, nach denen Microsoft Defender AV spyware Security Intelligence als veraltet betrachten soll.

    2. Klicken Sie auf **OK**.

    3.  Doppelklicken Sie auf Die Anzahl der Tage **definieren,** bevor Virendefinitionen als veraltet angesehen werden, und legen Sie die Option auf **Aktiviert fest.** Geben Sie die Anzahl der Tage ein, nach denen Microsoft Defender AV Virensicherheitsintelligenz als veraltet betrachten soll.

    4. Klicken Sie auf **OK**.


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>Einrichten von Nachholscans für Endpunkte, die eine Weile nicht überprüft wurden

Sie können die Anzahl der aufeinander folgenden geplanten Scans festlegen, die verpasst werden können, Microsoft Defender Antivirus eine Überprüfung erzwingen.

Der Vorgang zum Aktivieren dieses Features ist:

1. Richten Sie mindestens einen geplanten Scan ein (siehe [thema Schedule scans).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
2. Aktivieren Sie das Nachholscanfeature.
3. Definieren Sie die Anzahl der Scans, die übersprungen werden können, bevor eine Nachholscan durchgeführt wird.

Dieses Feature kann sowohl für vollständige als auch für schnelle Scans aktiviert werden.

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>Aktivieren und Konfigurieren des Nachholscanfeatures mithilfe von Gruppenrichtlinien

1.  Stellen Sie sicher, dass Sie mindestens einen geplanten Scan eingerichtet haben.

2.  Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

3.  Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

4.  Klicken **Sie auf Richtlinien** und dann auf Administrative **Vorlagen.**

5.  Erweitern Sie die Struktur, **Windows komponenten > Microsoft Defender Antivirus > überprüfen** und die folgenden Einstellungen konfigurieren:

    1.  Wenn Sie geplante Schnellscans eingerichtet haben, doppelklicken Sie auf die Einstellung Nachhol-Schnellscan aktivieren, und legen Sie die Option auf **Aktiviert fest.**  
    2. Wenn Sie geplante vollständige Scans eingerichtet haben, doppelklicken Sie auf die Einstellung Vollständige Nachholvorgang aktivieren, und legen Sie die Option auf **Aktiviert fest.**  Klicken Sie auf **OK**.
    3. Doppelklicken Sie auf Die Anzahl **der** Tage definieren, nach denen eine Nachholscan erzwungen wird, und legen Sie die Option auf **Aktiviert fest.** 
    4. Geben Sie die Anzahl der Scans ein, die verpasst werden können, bevor eine Überprüfung automatisch ausgeführt wird, wenn sich der Benutzer das nächste Mal am PC anmeldet. Der ausgeführte Scantyp wird durch das Angeben des Scantyps bestimmt, der für einen geplanten Scan verwendet werden soll **(siehe** Thema [Schedule scans).](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Klicken Sie auf **OK**.

> [!NOTE]
> Der Titel der Gruppenrichtlinieneinstellung bezieht sich auf die Anzahl der Tage. Die Einstellung wird jedoch auf die Anzahl der Scans (keine Tage) angewendet, bevor die Nachholscan ausgeführt wird.

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>Konfigurieren von Nachholscans mithilfe von PowerShell-Cmdlets

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus und [Defender-Cmdlets](/powershell/module/defender/) finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>Konfigurieren von Nachholscans mithilfe Windows Management Instruction (WMI)

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

Weitere Informationen und zulässige Parameter finden Sie im Folgenden:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>Konfigurieren von Nachholscans mithilfe von Configuration Manager

1.  Öffnen Sie Microsoft Endpoint Manager der Microsoft Endpoint Manager-Konsole die Richtlinie für Antischarten, die Sie ändern möchten (klicken Sie im Navigationsbereich links auf Ressourcen und Kompatibilität, und erweitern Sie dann die Struktur auf Übersicht   >  **Endpoint Protection**  >  **Antischalwarerichtlinien**)

2.  Wechseln Sie zum **Abschnitt Geplante Scans,** und erzwingen Sie eine Überprüfung des ausgewählten Scantyps, wenn **der Clientcomputer offline ist...** zu **Ja**. 

3. Klicken Sie auf **OK**.

4.  [Stellen Sie die aktualisierte Richtlinie wie gewohnt aus.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="related-articles"></a>Verwandte Artikel

- [Bereitstellen Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Baselines](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Verwalten von ereignisbasierten erzwungenen Updates](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)