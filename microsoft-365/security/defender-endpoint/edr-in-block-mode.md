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
ms.date: 06/11/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: ae170ecf0fc0f354c9975300e5f2f7cd014b0c47
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339688"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Endpunkterkennung und -antwort (EDR) im Blockierungsmodus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Was ist EDR im Blockierungsmodus?

[Endpunkterkennung und -reaktion](overview-endpoint-detection-response.md) (EDR) im Blockierungsmodus bieten Schutz vor bösartigen Artefakten, auch wenn Microsoft Defender Antivirus im passiven Modus ausgeführt wird. Wenn sie aktiviert ist, blockiert EDR im Blockierungsmodus bösartige Artefakte oder Verhaltensweisen, die auf einem Gerät erkannt werden. EDR im Blockierungsmodus funktioniert im Hintergrund, um böswillige Artefakte zu beheben, die nach der Verletzung erkannt werden. 

EDR im Blockierungsmodus ist auch in [& Sicherheitsrisikomanagement für Bedrohungen](next-gen-threat-and-vuln-mgt.md)integriert. Das Sicherheitsteam Ihrer Organisation erhält eine [Sicherheitsempfehlung,](tvm-security-recommendation.md) EDR im Blockierungsmodus zu aktivieren, wenn es noch nicht aktiviert ist. 

:::image type="content" source="images/enable-edr-in-block-mode.png" alt-text="Empfehlung, EDR im Blockmodus zu aktivieren":::

> [!NOTE]
> Um den besten Schutz zu erhalten, stellen Sie sicher, dass **[Sie Microsoft Defender für Endpunktgrundwerte bereitstellen.](configure-machines-security-baseline.md)**

## <a name="what-happens-when-something-is-detected"></a>Was geschieht, wenn etwas erkannt wird?

Wenn EDR im Blockmodus aktiviert ist und ein böswilliges Artefakt erkannt wird, blockiert und behebt Microsoft Defender für Endpunkt dieses Artefakt. Ihr Sicherheitsteam sieht den Erkennungsstatus als **blockiert** oder **verhindert** im [Info-Center,](respond-machine-alerts.md#check-activity-details-in-action-center)aufgeführt als abgeschlossene Aktionen.

Die folgende Abbildung zeigt eine Instanz unerwünschter Software, die im Blockierungsmodus durch EDR erkannt und blockiert wurde:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR im Blockierungsmodus etwas erkannt haben":::


## <a name="enable-edr-in-block-mode"></a>Aktivieren EDR im Blockierungsmodus

> [!IMPORTANT]
> Stellen Sie sicher, dass die [Anforderungen](#requirements-for-edr-in-block-mode) erfüllt sind, bevor Sie EDR im Blockierungsmodus aktivieren.

1. Wechseln Sie zum [Microsoft 365 Defender-Portal,](microsoft-defender-security-center.md) und melden Sie sich an. 

2. Wählen Sie **Einstellungen**  >  **Erweiterte Features** aus.

3. Aktivieren Sie **EDR im Blockierungsmodus.**

> [!NOTE]
> EDR im Blockierungsmodus können nur im Microsoft 365 Defender-Portal aktiviert werden. Sie können Registrierungsschlüssel, Intune oder Gruppenrichtlinien nicht verwenden, um EDR im Blockierungsmodus zu aktivieren oder zu deaktivieren.

## <a name="requirements-for-edr-in-block-mode"></a>Anforderungen für EDR im Blockmodus

|Anforderung  |Details  |
|---------|---------|
|Berechtigungen |Rolle "Globaler Administrator" oder "Sicherheitsadministrator" in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)zugewiesen. Siehe ["Grundlegende Berechtigungen".](basic-permissions.md) |
|Betriebssystem     |Eine der folgenden Versionen: <br/>– Windows 10 (alle Versionen) <br/>– Windows Server, Version 1803 oder höher <br/>- Windows Server 2019 <br/>– Windows Server 2016 (nur, wenn sich Microsoft Defender Antivirus im aktiven Modus befindet)     |
|Windows E5-Registrierung     |Windows E5 ist in den folgenden Abonnements enthalten: <br/>- Microsoft 365 E5 <br/>– Microsoft 365 E3 zusammen mit dem Identity & Threat Protection-Angebot <br/><br/>Siehe [Komponenten](/microsoft-365/enterprise/microsoft-365-overview#components) und [Features und Funktionen für jeden Plan.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Microsoft Defender Antivirus  |Microsoft Defender Antivirus müssen entweder im aktiven oder passiven Modus installiert und ausgeführt werden. (Sie können Microsoft Defender Antivirus zusammen mit einer Nicht-Microsoft-Antivirenlösung verwenden.) [Vergewissern Sie sich, dass sich Microsoft Defender Antivirus im aktiven oder passiven Modus befindet.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|Aus der Cloud gelieferter Schutz |Stellen Sie sicher, dass Microsoft Defender Antivirus so konfiguriert ist, dass der über die [Cloud bereitgestellte Schutz aktiviert ist.](enable-cloud-protection-microsoft-defender-antivirus.md) |
|Microsoft Defender Antivirus Antischadsoftware-Client |Stellen Sie sicher, dass Ihr Client auf dem neuesten Stand ist. Führen Sie mithilfe von PowerShell das Cmdlet ["Get-MpComputerStatus"](/powershell/module/defender/get-mpcomputerstatus) als Administrator aus. In der **ZEILE "AMProductVersion"** sollte **4.18.2001.10** oder höher angezeigt werden. |
|Microsoft Defender Antivirus-Modul |Stellen Sie sicher, dass Ihr Modul auf dem neuesten Stand ist. Führen Sie mithilfe von PowerShell das Cmdlet ["Get-MpComputerStatus"](/powershell/module/defender/get-mpcomputerstatus) als Administrator aus. In der **ZEILE AMEngineVersion** sollte **1.1.16700.2** oder höher angezeigt werden. |

> [!IMPORTANT]
> Um den besten Schutzwert zu erhalten, stellen Sie sicher, dass Ihre Antivirenlösung so konfiguriert ist, dass sie regelmäßige Updates und wichtige Features erhält, und dass Ihre [Ausschlüsse konfiguriert sind.](configure-exclusions-microsoft-defender-antivirus.md) EDR im Blockmodus berücksichtigt Ausschlüsse, die für Microsoft Defender Antivirus definiert sind.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>Muss ich EDR im Blockierungsmodus aktivieren, auch wenn ich Microsoft Defender Antivirus auf Geräten ausgeführt habe?

Es wird empfohlen, EDR im Blockmodus eingeschaltet zu halten, unabhängig davon, ob Microsoft Defender Antivirus im passiven modus oder im aktiven Modus ausgeführt wird. EDR im Blockierungsmodus bietet eine weitere Schutzebene mit Microsoft Defender für Endpunkt. Es ermöglicht Defender für Endpunkt, Aktionen basierend auf Verhaltenserkennungen nach der Verletzung EDR zu ergreifen. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>Wirkt sich EDR im Blockierungsmodus auf den Antivirenschutz eines Benutzers aus? 

EDR im Blockierungsmodus wirkt sich nicht auf den Antivirenschutz von Drittanbietern aus, der auf den Geräten der Benutzer ausgeführt wird. EDR im Blockierungsmodus funktioniert, wenn die primäre Antivirenlösung einen Fehler aufweist oder wenn eine Erkennung nach der Verletzung vorliegt. EDR im Blockmodus funktioniert genauso wie Microsoft Defender Antivirus im passiven Modus, mit der Ausnahme, dass auch schädliche Artefakte oder Verhaltensweisen blockiert und behoben werden, die erkannt werden.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Warum muss ich Microsoft Defender Antivirus auf dem neuesten Stand halten? 

Da Microsoft Defender Antivirus schädliche Elemente erkennt und behebt, ist es wichtig, sie auf dem neuesten Stand zu halten. Damit EDR im Blockmodus effektiv sind, werden die neuesten Gerätelernmodelle, Verhaltenserkennungen und Heuristiken verwendet. Der [Defender für Endpunkt-Stapel](microsoft-defender-endpoint.md) von Funktionen funktioniert auf integrierte Weise. Um den besten Schutzwert zu erhalten, sollten Sie Microsoft Defender Antivirus auf dem neuesten Stand halten. Siehe [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen.](manage-updates-baselines-microsoft-defender-antivirus.md) 

### <a name="why-do-we-need-cloud-protection-on"></a>Warum benötigen wir Cloudschutz? 

Cloudschutz ist erforderlich, um das Feature auf dem Gerät zu aktivieren. Cloudschutz ermöglicht [Defender für Endpunkt](microsoft-defender-endpoint.md) die Bereitstellung des neuesten und besten Schutzes basierend auf unserer Breite und Tiefe der Sicherheitsintelligenz sowie Verhaltens- und Gerätelernmodellen.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Wie setiere ich Microsoft Defender Antivirus auf den passiven Modus?

Wenn Geräte, auf denen keine Microsoft-Antiviren-/Antischadsoftware-Lösung ausgeführt wird, in Defender für Endpunkt integriert sind, können Microsoft Defender Antivirus je nach Betriebssystem automatisch in den passiven Modus wechseln. Weitere Informationen finden Sie unter [Wie sich Microsoft Defender Antivirus auf die Defender für Endpunkt-Funktionalität auswirkt.](microsoft-defender-antivirus-compatibility.md#how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality) 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Wie kann ich bestätigen Microsoft Defender Antivirus sich im aktiven oder passiven Modus befindet?

Um zu überprüfen, ob Microsoft Defender Antivirus im aktiven oder passiven Modus ausgeführt wird, können Sie die Eingabeaufforderung oder PowerShell auf einem Gerät verwenden, auf dem Windows ausgeführt wird.


|Methode  |Verfahren  |
|---------|---------|
| PowerShell     | 1. Wählen Sie die Startmenü aus, beginnen Sie mit `PowerShell` der Eingabe, und öffnen Sie dann Windows PowerShell in den Ergebnissen. <p>2. Typ `Get-MpComputerStatus` . <p>3. Suchen Sie in der Ergebnisliste in der Zeile **"AMRunningMode"** nach einem der folgenden Werte: <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>Weitere Informationen finden Sie unter [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).        |
|Eingabeaufforderung     | 1. Wählen Sie die Startmenü aus, beginnen Sie mit `Command Prompt` der Eingabe, und öffnen Sie dann Windows Eingabeaufforderung in den Ergebnissen. <p>2. Typ `sc query windefend` . <p>3. Vergewissern Sie sich in der Ergebnisliste in der Zeile **"STATE",** dass der Dienst ausgeführt wird.         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Wie lange dauert es, bis EDR im Blockierungsmodus deaktiviert ist?

Wenn Sie sich entschieden haben, EDR im Blockierungsmodus zu deaktivieren, kann es bis zu 30 Minuten dauern, bis das System diese Funktion deaktiviert hat.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>Wird EDR im Blockierungsmodus für Windows Server 2016 unterstützt?

Wenn Microsoft Defender Antivirus im aktiven oder passiven Modus ausgeführt wird, wird EDR im Blockierungsmodus von den folgenden Versionen von Windows unterstützt:

- Windows 10 (alle Versionen)
- Windows Server, Version 1803 oder höher 
- Windows Server 2019 

Wenn Windows Server 2016 Microsoft Defender Antivirus im aktiven Modus ausgeführt wird und der Endpunkt in Defender für Endpunkt integriert ist, wird EDR im Blockierungsmodus technisch unterstützt. EDR im Blockierungsmodus ist jedoch als zusätzlicher Schutz gedacht, wenn Microsoft Defender Antivirus nicht die primäre Antivirenlösung auf einem Endpunkt ist. In diesen Fällen wird Microsoft Defender Antivirus im passiven Modus ausgeführt. Derzeit wird das Ausführen von Microsoft Defender Antivirus im passiven Modus für Windows Server 2016 nicht unterstützt. Weitere Informationen finden Sie unter [Microsoft Defender Antivirus und Antiviren-/Antischadsoftware-Lösungen,](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)die nicht von Microsoft stammen.

## <a name="see-also"></a>Siehe auch

- [Tech Community Blog: Einführung in EDR im Blockierungsmodus: Verhindern von Angriffen im Hintergrund](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Verhaltensbasiertes Blockieren und Eindämmen](behavioral-blocking-containment.md)

