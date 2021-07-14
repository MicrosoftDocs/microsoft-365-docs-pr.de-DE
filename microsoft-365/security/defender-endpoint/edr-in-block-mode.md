---
title: Endpunkterkennung und -antwort im Blockierungsmodus
description: Informationen zu EDR im Blockierungsmodus
keywords: Microsoft Defender für Endpunkt, MDE, EDR im Blockierungsmodus, Blockieren des passiven Modus
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 07/13/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 1915a57becb1cba14605f4512ff123c1bca846bb
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415599"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Endpunkterkennung und -antwort (EDR) im Blockierungsmodus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Was ist EDR im Blockierungsmodus?

[Die Endpunkterkennung und -reaktion](overview-endpoint-detection-response.md) (EDR) im Blockierungsmodus bietet zusätzlichen Schutz vor bösartigen Artefakten, wenn Microsoft Defender Antivirus nicht das primäre Antivirenprodukt ist und im passiven Modus ausgeführt wird. EDR im Blockierungsmodus behebt bösartige Artefakte, die mit EDR erkannt werden. Solche Artefakte wurden möglicherweise vom primären, nicht von Microsoft stammenden Antivirenprodukt übersehen. EDR im Blockierungsmodus funktioniert im Hintergrund, um bösartige Artefakte zu beheben, die auf einem Gerät erkannt werden, nach einer Verletzung. 

> [!IMPORTANT]
> EDR im Blockierungsmodus bietet nicht den gesamten Schutz, der verfügbar ist, wenn Microsoft Defender Antivirus Echtzeitschutz aktiviert ist. Alle Features, die von Microsoft Defender Antivirus als aktive Antivirenlösung abhängen, funktionieren nicht, einschließlich der folgenden wichtigen Beispiele: 
> 
> - Echtzeitschutz, einschließlich Überprüfung beim Zugriff, ist nicht verfügbar, wenn sich Microsoft Defender Antivirus im passiven Modus befindet. Weitere Informationen zu Richtlinieneinstellungen für Echtzeitschutz finden Sie unter **[Aktivieren und Konfigurieren Microsoft Defender Antivirus Always-On-Schutz.](configure-real-time-protection-microsoft-defender-antivirus.md)**
> - Features wie **[Netzwerkschutz-](network-protection.md)** und **[Attack Surface Reduction-Regeln](attack-surface-reduction.md)** sind nur verfügbar, wenn Microsoft Defender Antivirus im aktiven Modus ausgeführt wird. 
> 
> Es wird erwartet, dass Ihre Nicht-Microsoft-Antivirenlösung diese Funktionen bereitstellt. 

EDR im Blockierungsmodus ist in [& Sicherheitsrisikomanagement für Bedrohungen](next-gen-threat-and-vuln-mgt.md)integriert. Das Sicherheitsteam Ihrer Organisation erhält eine [Sicherheitsempfehlung,](tvm-security-recommendation.md) EDR im Blockierungsmodus zu aktivieren, wenn es noch nicht aktiviert ist. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="Empfehlung, EDR im Blockierungsmodus zu aktivieren":::

> [!TIP]
> Um den besten Schutz zu erhalten, stellen Sie sicher, dass **[Sie Microsoft Defender für Endpunktgrundwerte bereitstellen.](configure-machines-security-baseline.md)**

## <a name="what-happens-when-something-is-detected"></a>Was geschieht, wenn etwas erkannt wird?

Wenn EDR im Blockmodus aktiviert ist und ein böswilliges Artefakt erkannt wird, blockiert und behebt Microsoft Defender für Endpunkt dieses Artefakt. Ihr Sicherheitsteam sieht den Erkennungsstatus als **blockiert** oder **verhindert** im [Info-Center,](respond-machine-alerts.md#check-activity-details-in-action-center)aufgeführt als abgeschlossene Aktionen.

Die folgende Abbildung zeigt eine Instanz unerwünschter Software, die im Blockierungsmodus durch EDR erkannt und blockiert wurde:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR im Blockierungsmodus wurde etwas erkannt":::


## <a name="enable-edr-in-block-mode"></a>Aktivieren EDR im Blockierungsmodus

> [!TIP]
> Stellen Sie sicher, dass die [Anforderungen](#requirements-for-edr-in-block-mode) erfüllt sind, bevor Sie EDR im Blockierungsmodus aktivieren.

1. Wechseln Sie zum Microsoft 365 Defender-Portal ( [https://security.microsoft.com/](https://security.microsoft.com/) ), und melden Sie sich an. 

2. Wählen Sie **Einstellungen**  >  **Allgemeinen erweiterten**  >    >  **Endpunktfeatures** aus.

3. Scrollen Sie nach unten, und aktivieren Sie dann EDR **im Blockierungsmodus.**

> [!NOTE]
> EDR im Blockierungsmodus können nur im Microsoft 365 Defender-Portal ( ) oder im früheren Microsoft Defender Security Center ( ) aktiviert [https://security.microsoft.com](https://security.microsoft.com) [https://securitycenter.windows.com](https://securitycenter.windows.com) werden. Sie können Registrierungsschlüssel, Microsoft Intune oder Gruppenrichtlinien nicht verwenden, um EDR im Blockierungsmodus zu aktivieren oder zu deaktivieren.

## <a name="requirements-for-edr-in-block-mode"></a>Anforderungen für EDR im Blockierungsmodus

| Anforderung  | Details  |
|---------|---------|
| Berechtigungen | Sie müssen die Rolle "Globaler Administrator" oder "Sicherheitsadministrator" in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)zugewiesen haben. Weitere Informationen finden Sie unter ["Grundlegende Berechtigungen".](basic-permissions.md) |
| Betriebssystem     | Auf Geräten muss eine der folgenden Versionen von Windows ausgeführt werden: <br/>– Windows 10 (alle Versionen) <br/>– Windows Server, Version 1803 oder höher <br/>- Windows Server 2019 <br/>– Windows Server 2016 (nur, wenn sich Microsoft Defender Antivirus im aktiven Modus befindet)     |
| Microsoft Defender für Endpunkt     | Geräte müssen in Defender für Endpunkt integriert werden. Siehe [Mindestanforderungen für Microsoft Defender für Endpunkt.](minimum-requirements.md)       |
| Microsoft Defender Antivirus  | Geräte müssen Microsoft Defender Antivirus installiert sein und im aktiven oder passiven Modus ausgeführt werden. [Vergewissern Sie sich, dass Microsoft Defender Antivirus sich im aktiven oder passiven Modus befindet.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
| Aus der Cloud gelieferter Schutz | Microsoft Defender Antivirus müssen so konfiguriert sein, dass der über die [Cloud bereitgestellte Schutz aktiviert ist.](enable-cloud-protection-microsoft-defender-antivirus.md) |
| Microsoft Defender Antivirus-Plattform | Geräte müssen auf dem neuesten Stand sein. Um zu bestätigen, führen Sie mithilfe von PowerShell das Cmdlet ["Get-MpComputerStatus"](/powershell/module/defender/get-mpcomputerstatus) als Administrator aus. In der **ZEILE "AMProductVersion"** sollte **4.18.2001.10** oder höher angezeigt werden. <p> Weitere Informationen finden Sie unter [Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Baselines](manage-updates-baselines-microsoft-defender-antivirus.md). |
| Microsoft Defender Antivirus-Modul | Geräte müssen auf dem neuesten Stand sein. Um zu bestätigen, führen Sie mithilfe von PowerShell das Cmdlet ["Get-MpComputerStatus"](/powershell/module/defender/get-mpcomputerstatus) als Administrator aus. In der **ZEILE AMEngineVersion** sollte **1.1.16700.2** oder höher angezeigt werden. <p> Weitere Informationen finden Sie unter [Verwalten von Microsoft Defender Antivirus-Updates und Anwenden von Baselines](manage-updates-baselines-microsoft-defender-antivirus.md). |

> [!IMPORTANT]
> Um den besten Schutzwert zu erhalten, stellen Sie sicher, dass Ihre Antivirenlösung so konfiguriert ist, dass sie regelmäßige Updates und wichtige Features erhält, und dass Ihre [Ausschlüsse konfiguriert sind.](configure-exclusions-microsoft-defender-antivirus.md) EDR im Blockmodus berücksichtigt Ausschlüsse, die für Microsoft Defender Antivirus definiert sind, jedoch keine [Indikatoren,](manage-indicators.md) die für Microsoft Defender für Endpunkt definiert sind.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>Muss ich EDR im Blockierungsmodus aktivieren, wenn Microsoft Defender Antivirus auf Geräten ausgeführt wird?

Der Hauptzweck der EDR im Blockierungsmodus besteht darin, Erkennungen nach einem Angriff zu beheben, die von einem Nicht-Microsoft-Antivirenprodukt übersehen wurden. Es wird jedoch empfohlen, EDR im Blockmodus aktiviert zu halten, unabhängig davon, ob Microsoft Defender Antivirus im passiven oder im aktiven Modus ausgeführt wird. 

- Wenn sich Microsoft Defender Antivirus im passiven Modus befindet, bietet EDR im Blockierungsmodus zusammen mit Microsoft Defender für Endpunkt eine weitere Schutzebene. 
- Wenn sich Microsoft Defender Antivirus im aktiven Modus befindet, bietet EDR im Blockierungsmodus keine zusätzliche Überprüfung, aber Es ermöglicht Defender für Endpunkt, automatische Aktionen bei Erkennungen nach einer Verletzung, verhaltensbasierten EDR zu ergreifen.

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>Wirkt sich EDR im Blockierungsmodus auf den Antivirenschutz eines Benutzers aus? 

EDR im Blockierungsmodus wirkt sich nicht auf den Antivirenschutz von Drittanbietern aus, der auf den Geräten der Benutzer ausgeführt wird. EDR im Blockierungsmodus funktioniert, wenn die primäre Antivirenlösung einen Fehler aufweist oder wenn eine Erkennung nach der Verletzung vorliegt. EDR im Blockmodus funktioniert genauso wie Microsoft Defender Antivirus im passiven Modus, mit der Ausnahme, dass EDR im Blockmodus auch erkannte böswillige Artefakte oder Verhaltensweisen blockiert und behebt.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Warum muss ich Microsoft Defender Antivirus auf dem neuesten Stand halten? 

Da Microsoft Defender Antivirus schädliche Elemente erkennt und behebt, ist es wichtig, sie auf dem neuesten Stand zu halten. Damit EDR im Blockmodus effektiv sind, werden die neuesten Gerätelernmodelle, Verhaltenserkennungen und Heuristiken verwendet. Der [Defender für Endpunkt-Stapel](microsoft-defender-endpoint.md) von Funktionen funktioniert auf integrierte Weise. Um den besten Schutzwert zu erhalten, sollten Sie Microsoft Defender Antivirus auf dem neuesten Stand halten. Weitere Informationen finden Sie unter [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen.](manage-updates-baselines-microsoft-defender-antivirus.md) 

### <a name="why-do-we-need-cloud-protection-maps-on"></a>Warum benötigen wir Cloudschutz (MAPS) auf? 

Cloudschutz ist erforderlich, um das Feature auf dem Gerät zu aktivieren. Cloudschutz ermöglicht [Defender für Endpunkt](microsoft-defender-endpoint.md) die Bereitstellung des neuesten und besten Schutzes basierend auf unserer Breite und Tiefe der Sicherheitsintelligenz sowie Verhaltens- und Gerätelernmodellen.

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>Was ist der Unterschied zwischen aktivem und passivem Modus?

Für Endpunkte, die Windows 10, Windows Server, Version 1803 oder höher oder Windows Server 2019 ausgeführt werden, wird Microsoft Defender Antivirus im aktiven Modus als primäres Antivirenprogramm auf dem Gerät verwendet. Wenn Microsoft Defender Antivirus im passiven Modus ausgeführt wird, ist dies nicht das primäre Antivirenprodukt. In diesem Fall werden Bedrohungen nicht durch Microsoft Defender Antivirus in Echtzeit behoben.

> [!NOTE]
> Microsoft Defender Antivirus können nur im passiven Modus ausgeführt werden, wenn das Gerät in Microsoft Defender für Endpunkt integriert ist.

Weitere Informationen finden Sie unter [Microsoft Defender Antivirus Kompatibilität.](microsoft-defender-antivirus-compatibility.md)

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Wie kann ich bestätigen, dass sich Microsoft Defender Antivirus im aktiven oder passiven Modus befindet?

Um zu überprüfen, ob Microsoft Defender Antivirus im aktiven oder passiven Modus ausgeführt wird, können Sie die Eingabeaufforderung oder PowerShell auf einem Gerät verwenden, auf dem Windows ausgeführt wird.

|Methode  |Verfahren  |
|---------|---------|
| PowerShell     | 1. Wählen Sie die Startmenü aus, beginnen Sie mit `PowerShell` der Eingabe, und öffnen Sie dann Windows PowerShell in den Ergebnissen. <p>2. Typ `Get-MpComputerStatus` . <p>3. Suchen Sie in der Ergebnisliste in der Zeile **"AMRunningMode"** nach einem der folgenden Werte: <br/>- `Normal` <br/>- `Passive Mode` <p>Weitere Informationen finden Sie unter [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).        |
|Eingabeaufforderung     | 1. Wählen Sie die Startmenü aus, beginnen Sie mit `Command Prompt` der Eingabe, und öffnen Sie dann Windows Eingabeaufforderung in den Ergebnissen. <p>2. Typ `sc query windefend` . <p>3. Vergewissern Sie sich in der Ergebnisliste in der Zeile **"STATE",** dass der Dienst ausgeführt wird.         |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>Wie kann ich bestätigen, dass EDR im Blockierungsmodus mit Microsoft Defender Antivirus im passiven Modus aktiviert ist?

Sie können PowerShell verwenden, um zu bestätigen, dass EDR im Blockierungsmodus aktiviert ist, während Microsoft Defender Antivirus im passiven Modus ausgeführt wird.

1. Wählen Sie die Startmenü aus, beginnen Sie mit `PowerShell` der Eingabe, und öffnen Sie dann Windows PowerShell in den Ergebnissen. 

2. Geben Sie `Get-MPComputerStatus | select AMRunningMode` ein.

3. Vergewissern Sie sich, dass das Ergebnis `EDR Block Mode` angezeigt wird.

   > [!TIP]
   > Wenn sich Microsoft Defender Antivirus im aktiven Modus befindet, wird `Normal` anstelle von `EDR Block Mode` . Weitere Informationen finden Sie unter [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>Wird EDR im Blockierungsmodus für Windows Server 2016 unterstützt?

Wenn Microsoft Defender Antivirus im aktiven oder passiven Modus ausgeführt wird, wird EDR im Blockierungsmodus von den folgenden Versionen von Windows unterstützt:

- Windows 10 (alle Versionen)
- Windows Server, Version 1803 oder höher 
- Windows Server 2019 

#### <a name="what-about-windows-server-2016"></a>Was ist mit Windows Server 2016? 

Wenn Windows Server 2016 Microsoft Defender Antivirus im aktiven Modus ausgeführt wird und der Endpunkt in Defender für Endpunkt integriert ist, wird EDR im Blockierungsmodus technisch unterstützt. EDR im Blockierungsmodus ist jedoch als zusätzlicher Schutz gedacht, wenn Microsoft Defender Antivirus nicht die primäre Antivirenlösung auf einem Endpunkt ist. In diesen Fällen wird Microsoft Defender Antivirus im passiven Modus ausgeführt. 

Derzeit wird das Ausführen Microsoft Defender Antivirus im passiven Modus für Windows Server 2016 nicht unterstützt. Weitere Informationen finden Sie unter Microsoft Defender Antivirus und nicht von Microsoft stammende [Antiviren-/Antischadsoftwarelösungen.](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Wie lange dauert es, bis EDR im Blockierungsmodus deaktiviert ist?

Wenn Sie sich dafür entscheiden, EDR im Blockierungsmodus zu deaktivieren, kann es bis zu 30 Minuten dauern, bis das System diese Funktion deaktiviert hat.

## <a name="see-also"></a>Siehe auch

- [Tech Community Blog: Einführung in EDR im Blockierungsmodus: Verhindern von Angriffen im Hintergrund](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Verhaltensbasiertes Blockieren und Eindämmen](behavioral-blocking-containment.md)

