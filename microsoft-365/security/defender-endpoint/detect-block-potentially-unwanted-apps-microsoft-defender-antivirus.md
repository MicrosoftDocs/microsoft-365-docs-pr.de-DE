---
title: Blockieren potenziell unerwünschter Anwendungen mit Microsoft Defender Antivirus
description: Aktivieren Sie das Antivirus-Feature für potentiell unerwünschte Anwendungen (PUA), um unerwünschte Software wie z. B. Adware zu blockieren.
keywords: PUA, aktivieren, unerwünschte Software, unerwünschte Apps, Adware, Browser-Symbolleiste, erkennen, blockieren, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: fbd897b025db2317dd1c213e5adf5d64ba88e7ac
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275240"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>Erkennen und Blockieren potenziell unerwünschter Anwendungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

Potenziell unerwünschte Anwendungen (PUA) sind eine Kategorie von Software, die Ihren Computer verlangsamen, unerwartete Werbung anzeigen oder schlimmstenfalls andere Software installieren kann, die unerwartet oder unerwünscht ist. PUA werden nicht als Virus, Schadsoftware oder eine andere Art von Bedrohung angesehen, aber sie können Aktionen auf Endgeräten durchführen, welche die Leistung oder Nutzung von Endgeräten beeinträchtigen. Der Ausdruck *PUA* kann sich auch auf eine Anwendung beziehen, die aufgrund bestimmter unerwünschten Verhaltensweisen einen schlechten Ruf hat (gemäß Bewertung von Microsoft Defender für Endpunkt).

Hier sind einige Beispiele:

- **Werbe-Software**, welche Werbung oder Aktionen anzeigt, einschließlich Software, die Werbung in Webseiten einfügt.
- **Bündelung-Software**, die anbietet, andere Software zu installieren, die nicht von der gleichen Entität digital signiert ist. Ebenfalls Software, die anbietet, andere Software zu installieren, die als PUA eingestuft wird.
- **Umgehungssoftware**, die aktiv versucht, sich der Erkennung durch Sicherheitsprodukte zu entziehen, einschließlich Software, die sich bei Vorhandensein von Sicherheitsprodukten anders verhält.

> [!TIP]
> Weitere Beispiele und eine Diskussion der Kriterien, die wir verwenden, um Anwendungen für die besondere Aufmerksamkeit von Sicherheitsfeatures zu kennzeichnen, finden Sie unter [Wie Microsoft Schadsoftware und potenziell unerwünschte Anwendungen identifiziert](/windows/security/threat-protection/intelligence/criteria).

Potenziell unerwünschte Anwendungen können das Risiko erhöhen, dass Ihr Netzwerk durch echte Schadsoftware infiziert wird, gestalten die Identifizierung von Schadsoftware-Infektionen schwieriger oder verschwenden IT-Ressourcen für deren Bereinigung. PUA-Schutz wird in Windows 10, Windows Server 2019 und Windows Server 2016 unterstützt. In Windows 10 (Version 2004 oder höher) blockiert Microsoft Defender Antivirus standardmäßig Apps, die für Geräte von Unternehmen (E5) als PUA angesehen werden.

## <a name="microsoft-edge"></a>Microsoft Edge

Der [neue Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), der Chromium-basiert ist, blockiert das Herunterladen von potenziell unerwünschten Anwendungen und zugehöriger Ressourcen-URLs. Dieses Feature wird über [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) zur Verfügung gestellt.

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>PUA-Schutz im Chromium-basierten Microsoft Edge aktivieren

Obwohl der Schutz vor potentiell unerwünschten Anwendungen in Microsoft Edge (Chromium-basiert, Version 80.0.361.50) standardmäßig deaktiviert ist, kann er einfach aus dem Browser heraus aktiviert werden.

1. Wählen Sie in Ihrem Microsoft Edge-Browser die Ellipsen aus und dann **Einstellungen**.

2. Wählen Sie **Datenschutz, Suche und Dienste** aus.

3. Aktivieren Sie unter dem Abschnitt **Sicherheit** die Option **Blockieren potenziell unerwünschter Apps**.

> [!TIP]
> Wenn Sie Microsoft Edge (Chromium-basiert) verwenden, können Sie die URL-Blockierungsfunktion des PUA-Schutzes sicher erkunden, indem Sie diese auf einer unserer [Microsoft Defender SmartScreen-Demoseiten ausprobieren](https://demo.smartscreen.msft.net/).

### <a name="block-urls-with-microsoft-defender-smartscreen"></a>URLs blockieren mit Microsoft Defender SmartScreen

Im Chromium-basierten Microsoft Edge mit aktiviertem PUA-Schutz schützt Microsoft Defender SmartScreen Sie vor mit PUA assoziierten URLs.

Sicherheitsadministratoren können [konfigurieren](/DeployEdge/configure-microsoft-edge), wie Microsoft Edge und Microsoft Defender SmartScreen zusammenarbeiten, um Gruppen von Benutzern vor mit PUA assoziierten URLs zu schützen. Für Microsoft Defender SmartScreen sind mehrere [Gruppenrichtlinieneinstellungen](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explizit verfügbar, einschließlich [eine zum Blockieren von PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled). Zusätzlich können Administratoren [Microsoft Defender SmartScreen als Ganzes konfigurieren](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen), indem Sie Gruppenrichtlinieneinstellungen verwenden, um Microsoft Defender SmartScreen zu aktivieren oder deaktivieren.

Obwohl Microsoft Defender für Endpunkt über eine eigene Sperrliste verfügt, die auf einem von Microsoft verwalteten Dataset basiert, können Sie diese Liste basierend auf Ihren eigenen Bedrohungsinformationen anpassen. Wenn Sie im Microsoft Defender für Endpunkt-Portal [Indikatoren erstellen und verwalten](manage-indicators.md), berücksichtigt Microsoft Defender SmartScreen die neuen Einstellungen.

## <a name="microsoft-defender-antivirus-and-pua-protection"></a>Microsoft Defender Antivirus und PUA-Schutz

Die Schutzfunktion gegen potentiell unerwünschte Anwendungen (PUA) in Microsoft Defender Antivirus kann PUA auf Endpunkten in Ihrem Netzwerk erkennen und blockieren.

> [!NOTE]
> Dieses Feature ist verfügbar in Windows 10, Windows Server 2019 und Windows Server 2016.

Microsoft Defender Antivirus blockiert erkannte PUA-Dateien und jeden Versuch, diese herunterzuladen, zu verschieben, auszuführen oder zu installieren. Blockierte PUA-Dateien werden dann unter Quarantäne gestellt. Wenn eine PUA-Datei auf einem Endpunkt erkannt wird, sendet Microsoft Defender Antivirus eine Benachrichtigung an den Benutzer ([außer wenn Benachrichtigungen deaktiviert wurden](configure-notifications-microsoft-defender-antivirus.md)), im gleichen Format wir für andere Bedrohungserkennungen. Der Benachrichtigung wird `PUA:` vorangestellt, um ihren Inhalt anzuzeigen.

Die Benachrichtigung erscheint in der üblichen [Quarantäneliste innerhalb der Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md).

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Konfigurieren des PUA-Schutzes in Microsoft Defender Antivirus

Sie können den PUA-Schutz mit [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), einer [Gruppenrichtlinie](/azure/active-directory-domain-services/manage-group-policy) oder mittels [PowerShell-Cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps) aktivieren.

Sie können den PUA-Schutz ebenfalls im Überwachungsmodus verwenden, um potenziell unerwünschte Anwendungen zu erkennen, ohne sie zu blockieren. Die Erkennungen werden im Windows-Ereignisprotokoll aufgezeichnet.

> [!TIP]
> Besuchen Sie die Demowebsite von Microsoft Defender für Endpunkt unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep), um zu bestätigen, dass das Feature funktioniert, und es bei der Arbeit zu sehen.

Der PUA-Schutz im Überwachungsmodus ist nützlich, wenn Ihr Unternehmen eine interne Software-Sicherheitsüberprüfung durchführt und Sie Fehlalarme vermeiden möchten.

### <a name="use-intune-to-configure-pua-protection"></a>Verwenden von Intune zum Konfigurieren des PUA-Schutzes

Für mehr Details lesen Sie [Konfigurieren von Einstellungen für Geräteeinschränkungen in Microsoft Intune](/intune/device-restrictions-configure) und [Einstellungen für Microsoft Defender Antivirus-Geräteeinschränkungen für Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).

### <a name="use-configuration-manager-to-configure-pua-protection"></a>Verwenden des Configuration Manager zum Konfigurieren des PUA-Schutzes

Der PUA-Schutz ist standardmäßig im Microsoft Endpoint Manager (Aktueller Branch) aktiviert.

Für Details zur Konfiguration des Microsoft Endpoint Manager (Aktueller Branch) lesen Sie [Erstellen und Bereitstellen von Antimalware-Richtlinien: Einstellungen für geplante Scans](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings).

Für den Configuration Manager des System Center 2012 lesen Sie [Bereitstellen einer Schutzrichtlinie für potenziell unerwünschte Anwendungen für den Endpunktschutz im Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).

> [!NOTE]
> Von Microsoft Defender Antivirus blockierte PUA-Ereignisse werden in der Windows-Ereignisanzeige gemeldet und nicht im Microsoft Endpoint Configuration Manager.

### <a name="use-group-policy-to-configure-pua-protection"></a>Verwenden einer Gruppenrichtlinie zum Konfigurieren des PUA-Schutzes

1. Herunterladen und Installieren der [Administrativen Vorlagen (.admx) für Windows 10, Oktober 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

3. Wählen Sie das Gruppenrichtlinien-Objekt aus, das Sie konfigurieren wollen, und wählen Sie dann **Bearbeiten** aus.

4. Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computerkonfiguration**, und wählen Sie **Administrative Vorlagen** aus.

5. Erweitern Sie die Struktur bis zu **Windows-Komponenten > ****Microsoft Defender Antivirus**.

6. Doppelklicken Sie auf **Erkennung für potentiell unerwünschte Anwendungen konfigurieren**.

7. Wählen Sie **Aktiviert** aus, um den PUA-Schutz zu aktivieren.

8. Wählen Sie unter **Optionen** die Option **Blockieren** aus, um potentiell unerwünschte Anwendungen zu blockieren, oder wählen Sie **Überwachungsmodus** aus, um zu testen, wie sich die Einstellung in Ihrer Umgebung auswirken. Wählen Sie **OK** aus.

9. Stellen Sie Ihr Gruppenrichtlinien-Objekt bereit, so wie Sie dies normalerweise tun.

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>Verwenden von PowerShell-Cmdlets zum Konfigurieren des PUA-Schutzes

#### <a name="to-enable-pua-protection"></a>So aktivieren Sie den PUA-Schutz

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

Wenn der Wert für dieses Cmdlet auf `Enabled` eingestellt wird, aktiviert dies das Feature, wenn es deaktiviert war.

#### <a name="to-set-pua-protection-to-audit-mode"></a>So stellen Sie den PUA-Schutz auf den Überwachungsmodus ein

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

Die Einstellung `AuditMode` erkennt PUAs, ohne sie zu blockieren.

#### <a name="to-disable-pua-protection"></a>So deaktivieren Sie den PUA-Schutz

Wir empfehlen, den PUA-Schutz aktiviert zu halten. Sie können ihn jedoch mit dem folgenden Cmdlet deaktivieren:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

Wenn der Wert für dieses Cmdlet auf `Disabled` eingestellt wird, deaktiviert dies das Feature, wenn es aktiviert war.

Weitere Informationen finden Sie unter [PowerShell-Cmdlets verwenden, um Microsoft Defender Antivirus zu konfigurieren und auszuführen](use-powershell-cmdlets-microsoft-defender-antivirus.md) und unter [Defender-Cmdlets](/powershell/module/defender/index).

## <a name="view-pua-events-using-powershell"></a>PUA-Ereignisse mittels PowerShell anzeigen

PUA-Ereignisse werden in der Windows-Ereignisanzeige gemeldet, aber nicht in Microsoft Endpoint Manager oder Intune. Sie können auch das `Get-MpThreat`-Cmdlet verwenden, um Bedrohungen anzuzeigen, die Microsoft Defender Antivirus behandelt hat. Hier ist ein Beispiel:

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

## <a name="get-email-notifications-about-pua-detections"></a>E-Mail-Benachrichtigungen über PUA-Erkennungen erhalten

Sie können E-Mail-Benachrichtigungen aktivieren, um E-Mails über PUA-Erkennungen zu erhalten.

Weitere Details zum Anzeigen von Microsoft Defender Antivirus-Ereignissen finden Sie unter [Problembehandlung von Ereignis-IDs](troubleshoot-microsoft-defender-antivirus.md). PUA-Ereignisse werden mit der Ereignis-ID **1160** aufgezeichnet.

## <a name="view-pua-events-using-advanced-hunting"></a>PUA-Ereignisse mittels der erweiterte Bedrohungssuche anzeigen

Wenn Sie [Microsoft Defender für Endpunkt](microsoft-defender-endpoint.md) verwenden, können Sie eine Abfrage zur erweiterten Bedrohungssuche verwenden, um PUA-Ereignisse anzuzeigen. Hier ist eine Beispielabfrage:

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

Weiter Informationen über die erweiterte Bedrohungssuche finden Sie unter [Proaktive Suche nach Bedrohungen mit der erweiterten Bedrohungssuche](advanced-hunting-overview.md).

## <a name="exclude-files-from-pua-protection"></a>Dateien vom PUA-Schutz ausschließen

Manchmal wird eine Datei fälschlicherweise vom PUA-Schutz blockiert, oder ein Feature einer PUA wird benötigt, um eine Aufgabe zu erledigen. In diesen Fällen kann eine Datei zur Ausschlussliste hinzugefügt werden.

Weitere Informationen finden Sie unter [Konfigurieren und Validieren von Ausschlüssen basierend auf Dateierweiterung und Ordnerspeicherorten](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

## <a name="see-also"></a>Siehe auch

- [Schutz der nächsten Generation](microsoft-defender-antivirus-in-windows-10.md)
- [Konfigurieren von verhaltensbasiertem, heuristischem und Echtzeit-Schutz](configure-protection-features-microsoft-defender-antivirus.md)