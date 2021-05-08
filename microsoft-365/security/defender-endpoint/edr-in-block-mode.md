---
title: Endpunkterkennung und -reaktion im Blockmodus
description: Informationen zur Erkennung und Reaktion von Endpunkten im Blockmodus
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
ms.date: 05/06/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 78201fd20d689a6774eb5395aa787a2b15147972
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274484"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Endpunkterkennung und -antwort (EDR) im Blockmodus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Was ist EDR im Blockmodus?

[Endpunkterkennung und -reaktion](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (Endpoint Detection and Response, EDR) im Blockmodus bietet Schutz vor schädlichen Artefakten, auch wenn Microsoft Defender Antivirus im passiven Modus ausgeführt wird. Bei aktivierter EDR im Blockmodus werden schädliche Artefakte oder Verhaltensweisen blockiert, die auf einem Gerät erkannt werden. EDR im Blockmodus arbeitet hinter den Kulissen, um bösartige Artefakte zu bewerkden, die nach der Verletzung erkannt werden. 

EDR im Blockmodus ist auch in die Bedrohungsverwaltung [& integriert.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) Das Sicherheitsteam Ihrer Organisation [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) erhalten eine Sicherheitsempfehlung zum Aktivieren von EDR im Sperrmodus, wenn es noch nicht aktiviert ist. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="Empfehlung zum Aktivieren von EDR im Blockmodus":::

> [!NOTE]
> Um den bestmöglichen Schutz zu erhalten, stellen Sie sicher, dass **[Sie Microsoft Defender for Endpoint-Baselines bereitstellen.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**

## <a name="what-happens-when-something-is-detected"></a>Was geschieht, wenn etwas erkannt wird?

Wenn EDR im Blockmodus aktiviert ist und ein bösartiges Artefakt erkannt wird, blockiert und besengt Microsoft Defender for Endpoint dieses Artefakt. Ihr Sicherheitsbetriebsteam sieht den Erkennungsstatus **"Blockiert"** oder **"Verhindert"** im [Aktionscenter](respond-machine-alerts.md#check-activity-details-in-action-center), das als abgeschlossene Aktionen aufgeführt ist.

Die folgende Abbildung zeigt eine Instanz unerwünschter Software, die im Blockmodus über EDR erkannt und blockiert wurde:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR im Blockmodus hat etwas erkannt":::


## <a name="enable-edr-in-block-mode"></a>Aktivieren von EDR im Blockmodus

> [!IMPORTANT]
> Stellen Sie [sicher, dass die Anforderungen](#requirements-for-edr-in-block-mode) erfüllt sind, bevor Sie EDR im Blockmodus aktivieren.

1. Wechseln Sie zum Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) und melden Sie sich an. 

2. Wählen **Sie Einstellungen** Erweiterte Features  >  **aus.**

3. Aktivieren Sie **EDR im Blockmodus.**

> [!NOTE]
> EDR im Blockmodus kann nur im Microsoft Defender Security Center aktiviert werden. Registrierungsschlüssel, Intune oder Gruppenrichtlinien können nicht verwendet werden, um EDR im Blockmodus zu aktivieren oder zu deaktivieren.

## <a name="requirements-for-edr-in-block-mode"></a>Anforderungen für EDR im Blockmodus

|Anforderung  |Details  |
|---------|---------|
|Berechtigungen |Globale Administrator- oder Sicherheitsadministratorrolle, die in [Azure Active Directory zugewiesen ist.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) Weitere [Informationen finden Sie unter Grundlegende Berechtigungen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions). |
|Betriebssystem     |Eine der folgenden Versionen: <br/>- Windows 10 (alle Versionen) <br/>- Windows Server, Version 1803 oder neuer <br/>- Windows Server 2019 <br/>– Windows Server 2016 (nur, wenn Sich Microsoft Defender Antivirus im aktiven Modus befindet)     |
|Windows E5-Registrierung     |Windows E5 ist in den folgenden Abonnements enthalten: <br/>- Microsoft 365 E5 <br/>– Microsoft 365 E3 zusammen mit dem Identity & Threat Protection-Angebot <br/><br/>Weitere [Informationen finden](/microsoft-365/enterprise/microsoft-365-overview#components) Sie unter Komponenten und Features und Funktionen für jeden [Plan.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Microsoft Defender Antivirus  |Microsoft Defender Antivirus muss entweder im aktiven oder passiven Modus installiert und ausgeführt werden. (Sie können Microsoft Defender Antivirus zusammen mit einer Nicht-Microsoft-Antivirenlösung verwenden.) [Vergewissern Sie sich, dass sich Microsoft Defender Antivirus im aktiven oder passiven Modus befindet.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|Aus der Cloud gelieferter Schutz |Stellen Sie sicher, dass Microsoft Defender Antivirus so konfiguriert ist, dass der über die [Cloud übermittelte Schutz aktiviert ist.](enable-cloud-protection-microsoft-defender-antivirus.md) |
|Microsoft Defender Antivirus-Antischasoftwareclient |Stellen Sie sicher, dass Ihr Client auf dem neuesten Stand ist. Führen Sie mithilfe von PowerShell das [Cmdlet Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) als Administrator aus. In der **Zeile AMProductVersion** sollten **Sie 4.18.2001.10** oder höher sehen. |
|Microsoft Defender Antivirus-Modul |Stellen Sie sicher, dass Ihr Modul auf dem neuesten Stand ist. Führen Sie mithilfe von PowerShell das [Cmdlet Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) als Administrator aus. In der **Zeile AMEngineVersion** sollten **Sie 1.1.16700.2** oder höher sehen. |

> [!IMPORTANT]
> Um den besten Schutzwert zu erhalten, stellen Sie sicher, dass Ihre Antivirenlösung so konfiguriert ist, dass sie regelmäßige Updates und wichtige Features erhält, und dass Ihre Ausschlüsse [konfiguriert sind.](configure-exclusions-microsoft-defender-antivirus.md) EDR im Blockmodus respektiert Ausschlüsse, die für Microsoft Defender Antivirus definiert sind.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>Muss ich EDR im Blockmodus aktivieren, auch wenn Microsoft Defender Antivirus auf Geräten ausgeführt wird?

Es wird empfohlen, EDR im Blockmodus zu aktivieren, unabhängig davon, ob Microsoft Defender Antivirus im passiven oder im aktiven Modus ausgeführt wird. EDR im Blockmodus bietet eine weitere Verteidigungsebene mit Microsoft Defender for Endpoint. Es ermöglicht Defender for Endpoint, Aktionen basierend auf Erkennungen von Verhaltens-EDR nach der Verletzung zu ergreifen. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>Hat EDR im Blockmodus Auswirkungen auf den Antivirenschutz eines Benutzers? 

EDR im Blockmodus wirkt sich nicht auf den Antivirenschutz von Drittanbietern aus, der auf den Geräten der Benutzer ausgeführt wird. EDR im Blockmodus funktioniert, wenn die primäre Antivirenlösung etwas verpasst oder eine Erkennung nach der Verletzung vor liegt. EDR im Blockmodus funktioniert genau wie Microsoft Defender Antivirus im [passiven](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)Modus, mit der Ausnahme, dass auch schädliche Artefakte oder Verhaltensweisen blockiert und behoben werden, die erkannt werden. 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Warum muss ich Microsoft Defender Antivirus auf dem neuesten Stand halten? 

Da Microsoft Defender Antivirus schädliche Elemente erkennt und abwehrt, ist es wichtig, sie auf dem neuesten Stand zu halten. Damit EDR im Blockmodus wirksam ist, werden die neuesten Gerätelernmodelle, Verhaltenserkennungen und Heuristiken verwendet. Der [Defender for Endpoint-Stapel](microsoft-defender-endpoint.md) von Funktionen funktioniert auf integrierte Weise. Um einen bestmöglichen Schutzwert zu erhalten, sollten Sie Microsoft Defender Antivirus auf dem neuesten Stand halten. Weitere [Informationen finden Sie unter Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md). 

### <a name="why-do-we-need-cloud-protection-on"></a>Warum benötigen wir Cloudschutz? 

Cloudschutz ist erforderlich, um das Feature auf dem Gerät zu aktivieren. Der Cloudschutz ermöglicht [Defender for Endpoint](microsoft-defender-endpoint.md) die Bereitstellung des neuesten und höchsten Schutzes basierend auf unserer Breite und Tiefe der Sicherheitsintelligenz sowie Verhaltens- und Gerätelernmodellen.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Wie set i set Microsoft Defender Antivirus to passive mode?

Je nach Betriebssystem kann Microsoft Defender Antivirus automatisch in den passiven Modus wechseln, wenn Geräte, auf denen eine Nicht-Microsoft-Antiviren-/Antischalwarelösung ausgeführt wird, in Defender for Endpoint onboarded werden. Weitere Informationen finden Sie unter [Antivirus und Microsoft Defender for Endpoint](microsoft-defender-antivirus-compatibility.md#antivirus-and-microsoft-defender-for-endpoint). 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Wie kann ich bestätigen, dass sich Microsoft Defender Antivirus im aktiven oder passiven Modus befindet?

Um zu bestätigen, ob Microsoft Defender Antivirus im aktiven oder passiven Modus ausgeführt wird, können Sie die Eingabeaufforderung oder PowerShell auf einem Gerät mit Windows verwenden.


|Methode  |Verfahren  |
|---------|---------|
| PowerShell     | 1. Wählen Sie das Menü Start aus, beginnen Sie mit der Eingabe, und öffnen Sie `PowerShell` dann Windows PowerShell in den Ergebnissen. <p>2. Geben Sie `Get-MpComputerStatus` ein. <p>3. Suchen Sie in der Ergebnisliste in der Zeile **AMRunningMode** nach einem der folgenden Werte: <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>Weitere Informationen finden Sie unter [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).        |
|Eingabeaufforderung     | 1. Wählen Sie das Startmenü aus, beginnen Sie mit der Eingabe und öffnen Sie dann die `Command Prompt` Windows-Eingabeaufforderung in den Ergebnissen. <p>2. Geben Sie `sc query windefend` ein. <p>3. Bestätigen Sie in der Liste der Ergebnisse in der Zeile **STATE,** dass der Dienst ausgeführt wird.         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Wie viel Zeit dauert es, bis EDR im Blockmodus deaktiviert ist?

Wenn Sie EDR im Blockmodus deaktivieren möchten, kann es bis zu 30 Minuten dauern, bis das System diese Funktion deaktiviert.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>Wird EDR im Blockmodus unter Windows Server 2016 unterstützt?

Wenn Microsoft Defender Antivirus im aktiven oder passiven Modus ausgeführt wird, wird EDR im Blockmodus von den folgenden Versionen von Windows unterstützt:

- Windows 10 (alle Versionen)
- Windows Server, Version 1803 oder neuer 
- Windows Server 2019 

Wenn In Windows Server 2016 Microsoft Defender Antivirus im aktiven Modus ausgeführt wird und der Endpunkt in Defender for Endpoint onboarded ist, wird EDR im Blockmodus unterstützt. EDR im Blockmodus soll jedoch zusätzlichen Schutz bieten, wenn Microsoft Defender Antivirus nicht die primäre Antivirenlösung auf einem Endpunkt ist. 

## <a name="see-also"></a>Siehe auch

- [Tech Community-Blog: Einführung in EDR im Blockmodus: Beenden von Angriffen in ihren Spuren](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Verhaltensbasiertes Blockieren und Eindämmen](behavioral-blocking-containment.md)
- [Noch besser zusammen: Microsoft Defender Antivirus und Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

