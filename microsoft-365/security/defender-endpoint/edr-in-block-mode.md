---
title: Endpunkterkennung und -reaktion im Blockmodus
description: Informationen zum EDR im Blockmodus
keywords: Microsoft Defender for Endpoint, mde, EDR im Blockmodus, Blockieren des passiven Modus
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
ms.date: 05/08/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 86bb27005365b625ee07feaa067c0ac488c3bb4b
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302040"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Endpunkterkennung und -antwort (EDR) im Blockmodus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Was ist EDR im Blockmodus?

[Endpunkterkennung und -reaktion](overview-endpoint-detection-response.md) (EDR) im Blockmodus bietet Schutz vor schädlichen Artefakten, auch wenn Microsoft Defender Antivirus im passiven Modus ausgeführt wird. Bei aktivierter EDR Blockmodus schädliche Artefakte oder Verhaltensweisen blockiert, die auf einem Gerät erkannt werden. EDR im Blockmodus funktioniert hinter den Kulissen, um bösartige Artefakte zu bewerkden, die nach der Verletzung erkannt werden. 

EDR im Blockmodus ist auch in [bedrohungsbedrohungen & Sicherheitsrisikomanagement.](next-gen-threat-and-vuln-mgt.md) Das Sicherheitsteam Ihrer Organisation [](tvm-security-recommendation.md) wird eine Sicherheitsempfehlung erhalten, um EDR im Blockmodus zu aktivieren, wenn es noch nicht aktiviert ist. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="Empfehlung zum Aktivieren EDR im Blockmodus":::

> [!NOTE]
> Um den bestmöglichen Schutz zu erhalten, stellen Sie sicher, dass **[Sie Microsoft Defender for Endpoint-Baselines bereitstellen.](configure-machines-security-baseline.md)**

## <a name="what-happens-when-something-is-detected"></a>Was geschieht, wenn etwas erkannt wird?

Wenn EDR im Blockmodus aktiviert ist und ein bösartiges Artefakt erkannt wird, blockiert und besengt Microsoft Defender for Endpoint dieses Artefakt. Ihr Sicherheitsbetriebsteam sieht den Erkennungsstatus **"Blockiert"** oder **"Verhindert"** im [Aktionscenter](respond-machine-alerts.md#check-activity-details-in-action-center), das als abgeschlossene Aktionen aufgeführt ist.

Die folgende Abbildung zeigt eine Instanz unerwünschter Software, die im Blockmodus EDR erkannt und blockiert wurde:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR im Blockmodus etwas erkannt":::


## <a name="enable-edr-in-block-mode"></a>Aktivieren EDR im Blockmodus

> [!IMPORTANT]
> Stellen Sie [sicher, dass die Anforderungen](#requirements-for-edr-in-block-mode) erfüllt sind, bevor Sie EDR im Blockmodus aktivieren.

1. Wechseln Sie zum Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) und melden Sie sich an. 

2. Wählen **Einstellungen**  >  **Erweiterte Features aus.**

3. Aktivieren sie **EDR im Blockmodus**.

> [!NOTE]
> EDR im Blockmodus können nur in der Microsoft Defender Security Center. Registrierungsschlüssel, Intune oder Gruppenrichtlinien können nicht verwendet werden, um EDR zu aktivieren oder zu deaktivieren.

## <a name="requirements-for-edr-in-block-mode"></a>Anforderungen für EDR im Blockmodus

|Anforderung  |Details  |
|---------|---------|
|Berechtigungen |Globale Administrator- oder Sicherheitsadministratorrolle, die in [Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) Weitere [Informationen finden Sie unter Grundlegende Berechtigungen](basic-permissions.md). |
|Betriebssystem     |Eine der folgenden Versionen: <br/>- Windows 10 (alle Versionen) <br/>- Windows Server, Version 1803 oder neuer <br/>- Windows Server 2019 <br/>- Windows Server 2016 (nur, wenn Microsoft Defender Antivirus aktiv ist)     |
|Windows E5-Registrierung     |Windows E5 ist in den folgenden Abonnements enthalten: <br/>- Microsoft 365 E5 <br/>– Microsoft 365 E3 zusammen mit dem Identity & Threat Protection-Angebot <br/><br/>Weitere [Informationen finden](/microsoft-365/enterprise/microsoft-365-overview#components) Sie unter Komponenten und Features und Funktionen für jeden [Plan.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Microsoft Defender Antivirus  |Microsoft Defender Antivirus muss entweder im aktiven oder passiven Modus installiert und ausgeführt werden. (Sie können Microsoft Defender Antivirus einer Nicht-Microsoft-Antivirenlösung verwenden.) [Bestätigen Microsoft Defender Antivirus sich im aktiven oder passiven Modus befindet.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|Aus der Cloud gelieferter Schutz |Stellen Sie sicher, Microsoft Defender Antivirus so konfiguriert ist, dass [der in der Cloud zugestellte Schutz aktiviert ist.](enable-cloud-protection-microsoft-defender-antivirus.md) |
|Microsoft Defender Antivirus Antischalwareclient |Stellen Sie sicher, dass Ihr Client auf dem neuesten Stand ist. Führen Sie mithilfe von PowerShell das [Cmdlet Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) als Administrator aus. In der **Zeile AMProductVersion** sollten **Sie 4.18.2001.10** oder höher sehen. |
|Microsoft Defender Antivirus Modul |Stellen Sie sicher, dass Ihr Modul auf dem neuesten Stand ist. Führen Sie mithilfe von PowerShell das [Cmdlet Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) als Administrator aus. In der **Zeile AMEngineVersion** sollten **Sie 1.1.16700.2** oder höher sehen. |

> [!IMPORTANT]
> Um den besten Schutzwert zu erhalten, stellen Sie sicher, dass Ihre Antivirenlösung so konfiguriert ist, dass sie regelmäßige Updates und wichtige Features erhält, und dass Ihre Ausschlüsse [konfiguriert sind.](configure-exclusions-microsoft-defender-antivirus.md) EDR im Blockmodus respektiert Ausschlüsse, die für die Microsoft Defender Antivirus.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>Muss ich die EDR im Blockmodus aktivieren, auch wenn ich Microsoft Defender Antivirus auf Geräten ausgeführt habe?

Es wird empfohlen, EDR im Blockmodus zu halten, unabhängig davon, ob Microsoft Defender Antivirus im passiven modus oder im aktiven Modus ausgeführt wird. EDR im Blockmodus bietet eine weitere Verteidigungsebene mit Microsoft Defender for Endpoint. Es ermöglicht Defender for Endpoint, Aktionen basierend auf Verhaltenserkennungen nach EDR durchführen. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>Hat EDR im Blockmodus Auswirkungen auf den Antivirenschutz eines Benutzers? 

EDR im Blockmodus wirkt sich nicht auf den Antivirenschutz von Drittanbietern aus, der auf den Geräten der Benutzer ausgeführt wird. EDR im Blockmodus funktioniert, wenn die primäre Antivirenlösung etwas verpasst oder eine Erkennung nach einer Sicherheitsverletzung vor liegt. EDR im Blockmodus funktioniert genau wie Microsoft Defender Antivirus im passiven Modus, mit der Ausnahme, dass auch schädliche Artefakte oder Verhaltensweisen blockiert und behoben werden, die erkannt werden.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Warum muss ich die Microsoft Defender Antivirus auf dem neuesten Stand halten? 

Da Microsoft Defender Antivirus Schadsoftware erkennt und besengt, ist es wichtig, sie auf dem neuesten Stand zu halten. Damit EDR im Blockmodus wirksam ist, werden die neuesten Gerätelernmodelle, Verhaltenserkennungen und Heuristiken verwendet. Der [Defender for Endpoint-Stapel](microsoft-defender-endpoint.md) von Funktionen funktioniert auf integrierte Weise. Um einen bestmöglichen Schutzwert zu erhalten, sollten Sie Microsoft Defender Antivirus auf dem neuesten Stand halten. Weitere Informationen finden Sie unter Manage [Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md). 

### <a name="why-do-we-need-cloud-protection-on"></a>Warum benötigen wir Cloudschutz? 

Cloudschutz ist erforderlich, um das Feature auf dem Gerät zu aktivieren. Der Cloudschutz ermöglicht [Defender for Endpoint](microsoft-defender-endpoint.md) die Bereitstellung des neuesten und höchsten Schutzes basierend auf unserer Breite und Tiefe der Sicherheitsintelligenz sowie Verhaltens- und Gerätelernmodellen.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Wie kann ich Microsoft Defender Antivirus passiven Modus festlegen?

Je nach Betriebssystem können Geräte, auf denen eine Nicht-Microsoft-Antiviren-/Antischsoftwarelösung ausgeführt wird, in Defender for Endpoint Microsoft Defender Antivirus automatisch in den passiven Modus wechseln. Weitere Informationen finden Sie unter [How Microsoft Defender Antivirus affects Defender for Endpoint functionality](microsoft-defender-antivirus-compatibility.md#how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality). 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Wie kann ich bestätigen, Microsoft Defender Antivirus sich im aktiven oder passiven Modus befindet?

Um zu bestätigen, Microsoft Defender Antivirus im aktiven oder passiven Modus ausgeführt wird, können Sie die Eingabeaufforderung oder PowerShell auf einem Gerät verwenden, auf dem Windows.


|Methode  |Verfahren  |
|---------|---------|
| PowerShell     | 1. Wählen Sie das Menü Start aus, beginnen Sie mit der Eingabe, und öffnen Sie `PowerShell` dann Windows PowerShell in den Ergebnissen. <p>2. Geben Sie `Get-MpComputerStatus` ein. <p>3. Suchen Sie in der Ergebnisliste in der Zeile **AMRunningMode** nach einem der folgenden Werte: <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>Weitere Informationen finden Sie unter [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).        |
|Eingabeaufforderung     | 1. Wählen Sie das Menü Start aus, beginnen Sie mit der Eingabe, und öffnen Sie `Command Prompt` dann Windows Eingabeaufforderung in den Ergebnissen. <p>2. Geben Sie `sc query windefend` ein. <p>3. Bestätigen Sie in der Liste der Ergebnisse in der Zeile **STATE,** dass der Dienst ausgeführt wird.         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Wie viel Zeit dauert es, EDR im Blockmodus deaktiviert ist?

Wenn Sie sich dafür entschieden haben, EDR im Blockmodus zu deaktivieren, kann es bis zu 30 Minuten dauern, bis das System diese Funktion deaktiviert.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>Wird EDR im Blockmodus auf der Windows Server 2016?

Wenn Microsoft Defender Antivirus im aktiven oder passiven Modus ausgeführt wird, wird EDR im Blockmodus von den folgenden Versionen von Windows:

- Windows 10 (alle Versionen)
- Windows Server, Version 1803 oder neuer 
- Windows Server 2019 

Wenn Windows Server 2016 im Microsoft Defender Antivirus ausgeführt wird und der Endpunkt in Defender for Endpoint onboarded ist, wird EDR im Blockmodus technisch unterstützt. Die EDR im Blockmodus ist jedoch als zusätzlicher Schutz gedacht, wenn Microsoft Defender Antivirus nicht die primäre Antivirenlösung auf einem Endpunkt ist. In diesen Fällen wird Microsoft Defender Antivirus im passiven Modus ausgeführt. Derzeit wird das Ausführen Microsoft Defender Antivirus im passiven Modus auf der Windows Server 2016. Weitere Informationen finden Sie [unter Microsoft Defender Antivirus und Nicht-Microsoft-Antiviren-/Antischalwarelösungen](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions).

## <a name="see-also"></a>Siehe auch

- [Tech Community blog: Introducing EDR in block mode: Stopping attacks in their tracks](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Verhaltensbasiertes Blockieren und Eindämmen](behavioral-blocking-containment.md)

