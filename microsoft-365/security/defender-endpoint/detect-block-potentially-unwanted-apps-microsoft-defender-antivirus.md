---
title: Blockieren potenziell unerwünschter Anwendungen mit Microsoft Defender Antivirus
description: Aktivieren Sie das Antivirusfeature für potenziell unerwünschte Anwendungen (PUA), um unerwünschte Software wie z. B. Adware zu blockieren.
keywords: pua, enable, unerwünschte Software, unerwünschte Apps, Adware, Browsersymbolleiste, erkennen, blockieren, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 20d4767f9813b741c55109d617f78302feaa0f7e
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765023"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>Erkennen und Blockieren potenziell unerwünschter Anwendungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

> [!NOTE]
> Potenziell unerwünschte Anwendungen (PUA) sind eine Kategorie von Software, die dazu führen kann, dass Ihr Computer langsam ausgeführt wird, unerwartete Anzeigen anzeigen oder im schlechtesten Fall andere Software installieren kann, die unerwartet oder unerwünscht sein kann. In Windows 10 (Version 2004 und höher) blockiert Microsoft Defender Antivirus standardmäßig Apps, die als PUA gelten, für Enterprise (E5)-Geräte.

Potenziell unerwünschte Anwendungen (PUA) werden nicht als Viren, Schadsoftware oder andere Arten von Bedrohungen betrachtet, sie können jedoch Aktionen für Endpunkte ausführen, die sich negativ auf die Leistung oder Verwendung von Endpunkten auswirken. _PUA_ kann sich auch auf eine Anwendung beziehen, die aufgrund bestimmter Arten von unerwünschtem Verhalten einen schlechten Ruf hat, wie von Microsoft Defender for Endpoint bewertet.

Im Folgenden finden Sie einige Beispiele:

- **Werbesoftware,** die Werbung oder Werbeaktionen anzeigt, einschließlich Software, die Werbung auf Webseiten einfüge.
- **Bündelungssoftware,** die die Installation anderer Software anbietet, die nicht digital von derselben Entität signiert ist. Außerdem Software, die die Installation anderer Software anbietet, die als PUA qualifiziert ist.
- **Software zum** Ausweichen, die aktiv versucht, der Erkennung durch Sicherheitsprodukte zu entweichen, einschließlich Software, die sich bei Vorhandensein von Sicherheitsprodukten anders verhält.

> [!TIP]
> Weitere Beispiele und eine Beschreibung der Kriterien, die wir zum Beschriften von Anwendungen für besondere Aufmerksamkeit von Sicherheitsfeatures verwenden, finden Sie unter [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).

Potenziell unerwünschte Anwendungen können das Risiko erhöhen, dass Ihr Netzwerk mit tatsächlicher Schadsoftware infiziert wird, Schadsoftwareinfektionen schwieriger zu identifizieren oder IT-Ressourcen beim Bereinigen zu verschwenden. Der PUA-Schutz wird unter Windows 10, Windows Server 2019 und Windows Server 2016 unterstützt.

## <a name="microsoft-edge"></a>Microsoft Edge

Das [neue Auf Chromium-basierte Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)blockiert potenziell unerwünschte Anwendungsdownloads und zugeordnete Ressourcen-URLs. Dieses Feature wird über [Microsoft Defender SmartScreen bereitgestellt.](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>Aktivieren des PUA-Schutzes in Chromium-basiertem Microsoft Edge

Obwohl der potenziell unerwünschte Anwendungsschutz in Microsoft Edge (Chromium-basiert, Version 80.0.361.50) standardmäßig deaktiviert ist, kann er problemlos über den Browser aktiviert werden.

1. Wählen Sie die Ellipsen aus, und wählen Sie dann **Einstellungen aus.**
2. Wählen **Sie Datenschutz, Suche und Dienste aus.**
3. Aktivieren Sie **im Abschnitt Sicherheit** potenziell unerwünschte Apps **blockieren.**

> [!TIP]
> Wenn Sie Microsoft Edge (chromium-basiert) ausführen, können Sie das Feature zum Blockieren von URLs des PUA-Schutzes sicher erkunden, indem Sie es auf einer unserer [Microsoft Defender SmartScreen-Demoseiten testen.](https://demo.smartscreen.msft.net/)

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a>Blockieren von URLs mit Microsoft Defender SmartScreen

In Chromium-basiertem Edge mit aktiviertem PUA-Schutz schützt Microsoft Defender SmartScreen Sie vor PUA-zugeordneten URLs.

Sicherheitsadministratoren können [konfigurieren,](/DeployEdge/configure-microsoft-edge) wie Microsoft Edge und Microsoft Defender SmartScreen zusammenarbeiten, um Benutzergruppen vor PUA-zugeordneten URLs zu schützen. Es sind mehrere [Gruppenrichtlinieneinstellungen explizit](/DeployEdge/microsoft-edge-policies#smartscreen-settings) für Microsoft Defender SmartScreen verfügbar, einschließlich einer für das Blockieren [von PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled). Darüber hinaus können Administratoren [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) als Ganzes konfigurieren, indem Sie Gruppenrichtlinieneinstellungen verwenden, um Microsoft Defender SmartScreen ein- oder auszuschalten.

Obwohl Microsoft Defender for Endpoint über eine eigene Sperrliste basierend auf einem von Microsoft verwalteten Datensatz verfügt, können Sie diese Liste basierend auf Ihrer eigenen Bedrohungsintelligenz anpassen. Wenn Sie [Indikatoren im](/microsoft-365/security/defender-endpoint/manage-indicators) Microsoft Defender for Endpoint-Portal erstellen und verwalten, respektiert Microsoft Defender SmartScreen die neuen Einstellungen.

## <a name="microsoft-defender-antivirus"></a>Microsoft Defender Antivirus

Das Feature zum Schutz potenziell unerwünschter Anwendungen (PUA) in Microsoft Defender Antivirus kann PUAs auf Endpunkten in Ihrem Netzwerk erkennen und blockieren.

> [!NOTE]
> Dieses Feature ist unter Windows 10, Windows Server 2019 und Windows Server 2016 verfügbar.

Microsoft Defender Antivirus blockiert erkannte PUA-Dateien und alle Versuche, sie herunterzuladen, zu verschieben, ausführen oder zu installieren. Blockierte PUA-Dateien werden dann in quarantäne verschoben. Wenn eine PUA-Datei auf einem Endpunkt erkannt wird, sendet Microsoft Defender Antivirus eine Benachrichtigung[an](configure-notifications-microsoft-defender-antivirus.md)den Benutzer ( es sei denn, Benachrichtigungen wurden deaktiviert ) im gleichen Format wie andere Bedrohungserkennungen. Die Benachrichtigung ist mit vorkonfaced, `PUA:` um den Inhalt anzugeben.

Die Benachrichtigung wird in der üblichen [Quarantäneliste in der Windows Security App angezeigt.](microsoft-defender-security-center-antivirus.md)

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Konfigurieren des PUA-Schutzes in Microsoft Defender Antivirus

Sie können den PUA-Schutz mit [Microsoft Intune,](/mem/intune/protect/device-protect) [Microsoft Endpoint Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection) [Gruppenrichtlinien](/azure/active-directory-domain-services/manage-group-policy)oder [über PowerShell-Cmdlets aktivieren.](/powershell/module/defender/?preserve-view=true&view=win10-ps)

Sie können den PUA-Schutz auch im Überwachungsmodus verwenden, um potenziell unerwünschte Anwendungen zu erkennen, ohne sie zu blockieren. Die Erkennungen werden im Windows-Ereignisprotokoll erfasst.

> [!TIP]
> Besuchen Sie die Microsoft Defender for Endpoint-Demowebsite unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com/Page/UrlRep) um zu bestätigen, dass das Feature funktioniert, und sehen Sie es in Aktion.

PuA-Schutz im Überwachungsmodus ist nützlich, wenn Ihr Unternehmen eine interne Überprüfung der Softwaresicherheit durchführt und Sie falsch positive Ergebnisse vermeiden möchten.

#### <a name="use-intune-to-configure-pua-protection"></a>Konfigurieren des PUA-Schutzes mithilfe von Intune

Weitere Informationen finden Sie [unter Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and Microsoft Defender Antivirus device restriction settings for Windows [10 in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

#### <a name="use-configuration-manager-to-configure-pua-protection"></a>Konfigurieren des PUA-Schutzes mithilfe von Configuration Manager

Der PUA-Schutz ist standardmäßig im Microsoft Endpoint Manager (Current Branch) aktiviert.

Weitere Informationen zum Konfigurieren von Microsoft Endpoint Manager (Current Branch) finden Sie unter How [to create and deploy anmalware policies: Scheduled scans settings.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)

Informationen zu System Center 2012 Configuration Manager finden Sie unter Bereitstellen potenziell unerwünschter Anwendungsschutzrichtlinien [für Endpunktschutz in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).

> [!NOTE]
> Von Microsoft Defender Antivirus blockierte PUA-Ereignisse werden in der Windows-Ereignisanzeige und nicht in Microsoft Endpoint Configuration Manager gemeldet.

#### <a name="use-group-policy-to-configure-pua-protection"></a>Konfigurieren des PUA-Schutzes mithilfe von Gruppenrichtlinien

1. Herunterladen und Installieren [von administrativen Vorlagen (ADMX) für Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

3. Wählen Sie das Gruppenrichtlinienobjekt aus, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten aus.**

4. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**

5. Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus**.

6. Doppelklicken Sie **auf Erkennung für potenziell unerwünschte Anwendungen konfigurieren.**

7. Wählen **Sie Aktiviert** aus, um den PUA-Schutz zu aktivieren.

8. Wählen **Sie unter Optionen** die Option **Blockieren** aus, um potenziell unerwünschte Anwendungen zu blockieren, oder wählen Sie Überwachungsmodus aus, um zu testen, wie die Einstellung in Ihrer Umgebung funktioniert.  Wählen Sie **OK** aus.

9. Stellen Sie Ihr Gruppenrichtlinienobjekt wie üblich zur Bereitstellung.

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>Konfigurieren des PUA-Schutzes mithilfe von PowerShell-Cmdlets

##### <a name="to-enable-pua-protection"></a>So aktivieren Sie den PUA-Schutz

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

Wenn Sie den Wert für dieses Cmdlet festlegen, wird das `Enabled` Feature aktiviert, wenn es deaktiviert wurde.

##### <a name="to-set-pua-protection-to-audit-mode"></a>So legen Sie den PUA-Schutz auf den Überwachungsmodus

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

Die `AuditMode` Einstellung erkennt PUAs, ohne sie zu blockieren.

##### <a name="to-disable-pua-protection"></a>So deaktivieren Sie den PUA-Schutz

Es wird empfohlen, den PUA-Schutz aktiviert zu halten. Sie können sie jedoch mit dem folgenden Cmdlet deaktivieren:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

Wenn Sie den Wert für dieses Cmdlet festlegen, wird das `Disabled` Feature deaktiviert, wenn es aktiviert wurde.

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/index)

## <a name="view-pua-events"></a>Anzeigen von PUA-Ereignissen

PUA-Ereignisse werden in der Windows-Ereignisanzeige gemeldet, jedoch nicht im Microsoft Endpoint Manager oder in Intune. Sie können das Cmdlet auch zum Anzeigen von `Get-MpThreat` Bedrohungen verwenden, die von Microsoft Defender Antivirus behandelt wurden. Hier ein Beispiel:

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

Sie können E-Mail-Benachrichtigungen aktivieren, um E-Mails zu PUA-Erkennungen zu empfangen.

Weitere Informationen zum Anzeigen von Microsoft Defender Antivirus-Ereignissen finden Sie unter [Troubleshoot event IDs.](troubleshoot-microsoft-defender-antivirus.md) PUA-Ereignisse werden unter ereignis-ID **1160 aufgezeichnet.**

## <a name="excluding-files"></a>Ausschließen von Dateien

Manchmal wird eine Datei fälschlicherweise durch den PUA-Schutz blockiert, oder ein Feature einer PUA ist erforderlich, um eine Aufgabe auszuführen. In diesen Fällen kann einer Ausschlussliste eine Datei hinzugefügt werden.

Weitere Informationen finden Sie unter [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

## <a name="see-also"></a>Siehe auch

- [Schutz der nächsten Generation](microsoft-defender-antivirus-in-windows-10.md)
- [Konfigurieren von Verhaltens-, Heuristik- und Echtzeitschutz](configure-protection-features-microsoft-defender-antivirus.md)