---
title: Anwenden von Microsoft Defender AV-Schutzupdates auf veraltete Endpunkte
description: Legen Sie fest, wann und wie Updates für Endpunkte angewendet werden sollen, die seit einer Weile nicht aktualisiert wurden.
keywords: Updates, Schutz, veraltet, veraltet, alt, Nachholbedarf
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
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b141c9b745e560b3c2236a9d073a7b2f3500623c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926043"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>Verwalten von Updates und Scans von Microsoft Defender Antivirus für veraltete Endpunkte

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus können Sie definieren, wie lange ein Endpunkt ein Update vermeiden kann oder wie viele Scans es verpassen kann, bevor er sich aktualisieren und scannen muss. Dies ist besonders nützlich in Umgebungen, in denen Geräte häufig nicht mit einem Unternehmensnetzwerk oder externen Netzwerk verbunden sind oder nicht täglich verwendet werden.

Beispielsweise befindet sich ein Mitarbeiter, der einen bestimmten PC verwendet, drei Tage in der Pause und meldet sich während dieser Zeit nicht an ihrem PC an.

Wenn der Benutzer zur Arbeit zurückkehrt und sich auf dem PC anmeldet, werden Microsoft Defender Antivirus sofort die neuesten Schutzupdates überprüfen und herunterladen und eine Überprüfung ausführen.

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>Einrichten von Nachholschutzupdates für Endpunkte, die eine Weile nicht aktualisiert wurden

Wenn Microsoft Defender Antivirus für einen bestimmten Zeitraum keine Schutzupdates heruntergeladen haben, können Sie es so einrichten, dass das neueste Update bei der nächsten Anmeldung automatisch überprüft und heruntergeladen wird. Dies ist nützlich, wenn Sie automatische [Updatedownloads beim Start global deaktiviert](manage-event-based-updates-microsoft-defender-antivirus.md)haben.

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>Verwenden von Configuration Manager zum Konfigurieren von Nachholschutzupdates

1.  Öffnen Sie in ihrer Microsoft Endpoint Manager Konsole die Antischadsoftwarerichtlinie, die Sie ändern möchten (klicken Sie im Navigationsbereich auf der linken Seite auf **"Ressourcen und Kompatibilität",** und erweitern Sie dann die Struktur auf **"Übersicht** Endpoint Protection Richtlinien für  >    >  **Antischadsoftware")**

2.  Wechseln Sie zum Abschnitt **"Security Intelligence Updates",** und konfigurieren Sie die folgenden Einstellungen:

    1. Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.
    2. Geben Sie für den  **If Configuration Manager als Quelle für Sicherheitsupdates an...** die Stunden, vor denen die von Configuration Manager bereitgestellten Schutzupdates als veraltet betrachtet werden sollen. Dadurch wird der nächste Updatespeicherort basierend auf der definierten [Fallbackquellreihenfolge](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)verwendet.

3. Klicken Sie auf **OK**.

4.  [Stellen Sie die aktualisierte Richtlinie wie gewohnt bereit.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>Verwenden von Gruppenrichtlinien zum Aktivieren und Konfigurieren des Nachholupdatefeatures

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**

3. Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**

4. Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Signaturupdates.**

5. Doppelklicken Sie auf die Einstellung **"Anzahl der Tage definieren", nach denen ein Update zur Nachholaktualisierung erforderlich ist,** und legen Sie die Option auf **"Aktiviert"** fest. Geben Sie die Anzahl der Tage ein, nach denen Microsoft Defender AV das neueste Schutzupdate suchen und herunterladen soll.

6. Klicken Sie auf **OK**.

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>Verwenden von PowerShell-Cmdlets zum Konfigurieren von Nachholschutzupdates

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus und [Defender-Cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>Verwenden Windows Management Instruction (WMI) zum Konfigurieren von Nachholschutzupdates

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
SignatureUpdateCatchupInterval
```

Weitere Informationen und zulässige Parameter finden Sie in den folgenden Themen:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>Festlegen der Anzahl von Tagen, bevor der Schutz als veraltet gemeldet wird

Sie können auch die Anzahl der Tage angeben, nach denen Microsoft Defender Antivirus Schutz als veraltet oder veraltet betrachtet wird. Nach der angegebenen Anzahl von Tagen meldet sich der Client selbst als veraltet und zeigt dem Benutzer des PCs einen Fehler an. Es kann auch dazu führen, dass Microsoft Defender Antivirus versuchen, ein Update aus anderen Quellen herunterzuladen (basierend auf der definierten [Fallbackquellreihenfolge), z.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)B. wenn MMPC als sekundäre Quelle verwendet wird, nachdem WSUS oder Microsoft Update als erste Quelle festgelegt wurde.

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>Verwenden von Gruppenrichtlinien zum Angeben der Anzahl von Tagen, bevor der Schutz als veraltet eingestuft wird

1.  Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

3.  Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**

4.  Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**

5.  Erweitern Sie die Struktur bis **Windows Komponenten > Microsoft Defender Antivirus > Signaturupdates,** und konfigurieren Sie die folgenden Einstellungen:

    1.  Doppelklicken Sie auf **"Anzahl der Tage definieren", bevor Spywaredefinitionen als veraltet gelten,** und legen Sie die Option auf **"Aktiviert"** fest. Geben Sie die Anzahl der Tage ein, nach denen Microsoft Defender AV die Spyware Security Intelligence als veraltet betrachten soll.

    2. Klicken Sie auf **OK**.

    3.  Doppelklicken Sie auf **"Anzahl der Tage definieren", bevor Virendefinitionen als veraltet gelten,** und legen Sie die Option auf **"Aktiviert"** fest. Geben Sie die Anzahl der Tage ein, nach denen Microsoft Defender AV die Virensicherheitserkennung als veraltet betrachten soll.

    4. Klicken Sie auf **OK**.


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>Einrichten von Nachholscans für Endpunkte, die eine Weile nicht gescannt wurden

Sie können die Anzahl der aufeinanderfolgenden geplanten Scans festlegen, die verpasst werden können, bevor Microsoft Defender Antivirus eine Überprüfung erzwingen.

Der Prozess zum Aktivieren dieses Features lautet:

1. Richten Sie mindestens einen geplanten Scan ein (siehe Das Thema ["Scans planen").](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
2. Aktivieren Sie die Funktion für den Nachholscan.
3. Definieren Sie die Anzahl der Scans, die übersprungen werden können, bevor ein Nachholscan durchgeführt wird.

Dieses Feature kann sowohl für vollständige als auch für schnelle Scans aktiviert werden.

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>Verwenden von Gruppenrichtlinien zum Aktivieren und Konfigurieren des Nachholscanfeatures

1.  Stellen Sie sicher, dass Sie mindestens einen geplanten Scan eingerichtet haben.

2.  Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

3.  Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**

4.  Klicken Sie auf **"Richtlinien"** und dann auf **"Administrative Vorlagen".**

5.  Erweitern Sie die Struktur, um komponenten > Microsoft Defender Antivirus > Scan zu **Windows,** und konfigurieren Sie die folgenden Einstellungen:

    1.  Wenn Sie geplante Schnellscans eingerichtet haben, doppelklicken Sie auf die Einstellung **"Nachholscan aktivieren",** und legen Sie die Option auf **"Aktiviert"** fest. 
    2. Wenn Sie geplante vollständige Scans eingerichtet haben, doppelklicken Sie auf die Einstellung **"Nachholvorgang für vollständige Überprüfung** aktivieren", und legen Sie die Option auf **"Aktiviert"** fest. Klicken Sie auf **OK**.
    3. Doppelklicken Sie auf **die Anzahl der Tage definieren, nach denen eine Nachholüberprüfung erzwungen wird,** und legen Sie die Option auf **"Aktiviert"** fest. 
    4. Geben Sie die Anzahl der Scans ein, die übersehen werden können, bevor ein Scan automatisch ausgeführt wird, wenn sich der Benutzer das nächste Mal am PC anmeldet. Der Typ des ausgeführten Scans wird durch die **Angabe des Scantyps bestimmt, der für eine geplante Überprüfung verwendet werden soll** (siehe Das Thema ["Scans planen").](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Klicken Sie auf **OK**.

> [!NOTE]
> Der Titel der Gruppenrichtlinieneinstellung bezieht sich auf die Anzahl der Tage. Die Einstellung wird jedoch auf die Anzahl der Scans (nicht Tage) angewendet, bevor der Nachholscan ausgeführt wird.

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>Verwenden von PowerShell-Cmdlets zum Konfigurieren von Nachholscans

Verwenden Sie die folgenden Cmdlets:

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Verwalten von Microsoft Defender Antivirus und [Defender-Cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>Verwenden Windows Management Instruction (WMI) zum Konfigurieren von Nachholscans

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) für die folgenden Eigenschaften:

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

Weitere Informationen und zulässige Parameter finden Sie in den folgenden Themen:
- [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>Verwenden von Configuration Manager zum Konfigurieren von Nachholscans

1.  Öffnen Sie in ihrer Microsoft Endpoint Manager Konsole die Antischadsoftwarerichtlinie, die Sie ändern möchten (klicken Sie im Navigationsbereich auf der linken Seite auf **"Ressourcen und Kompatibilität",** und erweitern Sie dann die Struktur auf **"Übersicht** Endpoint Protection Richtlinien für  >    >  **Antischadsoftware")**

2.  Wechseln Sie zum Abschnitt **"Geplante Scans",** und **erzwingen Sie eine Überprüfung des ausgewählten Scantyps, wenn der Clientcomputer offline ist...** auf **"Ja".** 

3. Klicken Sie auf **OK**.

4.  [Stellen Sie die aktualisierte Richtlinie wie gewohnt bereit.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="related-articles"></a>Verwandte Artikel

- [Bereitstellen von Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Verwalten von ereignisbasierten erzwungenen Updates](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)