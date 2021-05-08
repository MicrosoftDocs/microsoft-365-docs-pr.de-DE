---
title: Microsoft Defender Antivirus Kompatibilität mit anderen Sicherheitsprodukten
description: Erfahren Sie mehr Microsoft Defender Antivirus mit anderen Sicherheitsprodukten und betriebssystemen.
keywords: Windows Defender, Defender für Endpunkt, nächste Generation, Antivirus, Kompatibilität, passiver Modus
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr
ms.topic: article
manager: dansimp
ms.technology: mde
ms.date: 05/06/2021
ms.openlocfilehash: 885844b46d603dc318dbaf877cd445b5caaa4e46
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280981"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender Antivirus Kompatibilität

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

## <a name="summary"></a>Zusammenfassung

Microsoft Defender Antivirus wird automatisch aktiviert und auf Endpunkten und Geräten installiert, auf Windows 10. Was geschieht jedoch, wenn eine andere (nicht von Microsoft) verwendete Antiviren-/Antischalwarelösung verwendet wird? Es hängt davon ab, ob Sie [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) zusammen mit Ihrem Antivirenschutz verwenden. In diesem Artikel wird beschrieben, was mit Antiviren-/Antischalwarelösungen geschieht, wenn Endpunkte in Microsoft Defender for Endpoint onboardiert werden.

## <a name="why-defender-for-endpoint-matters"></a>Warum Defender for Endpoint wichtig ist

Erwägen Sie das Onboarding Ihrer Endpunkte in Defender for Endpoint, auch wenn Sie eine Nicht-Microsoft-Antiviren-/Antischalwarelösung verwenden. Wenn Sie Ihre Geräte in Defender for Endpoint integrieren, können Sie in den meisten Fällen Microsoft Defender Antivirus ihrer Nicht-Microsoft-Antivirenlösung für zusätzlichen Schutz verwenden. Sie können z. B. EDR im Blockmodus [verwenden,](edr-in-block-mode.md)der schädliche Artefakte blockiert und repariert, die Ihre primäre Antivirenlösung möglicherweise verpasst hat. 

Funktionsweise:

- Wenn die Clientgeräte Ihrer Organisation durch eine Nicht-Microsoft-Antiviren-/Antimwalware-Lösung geschützt sind, wechselt Microsoft Defender Antivirus automatisch in den passiven Modus, wenn diese Geräte in Defender for Endpoint integrierte werden. In diesem Fall treten Bedrohungserkennungen auf, aber Echtzeitschutz und Bedrohungen werden nicht von der Microsoft Defender Antivirus. **HINWEIS:** Dieses spezielle Szenario gilt nicht für Endpunkte, die Windows Server ausführen.

- Wenn die Clientgeräte Ihrer Organisation durch eine Nicht-Microsoft-Antiviren-/Antischalwarelösung geschützt sind und diese Geräte nicht in Microsoft Defender for Endpoint integrierte werden, wechselt Microsoft Defender Antivirus automatisch in den deaktivierten Modus. In diesem Fall werden Bedrohungen nicht von der Microsoft Defender Antivirus. **HINWEIS:** Dieses spezielle Szenario gilt nicht für Endpunkte, die Windows Server ausführen.

- Wenn die Endpunkte Ihrer Organisation Windows Server ausgeführt werden und diese Endpunkte durch eine Nicht-Microsoft-Antiviren-/Antischalwarelösung geschützt sind, wechselt Microsoft Defender Antivirus nicht automatisch in den passiven oder deaktivierten Modus, wenn diese Endpunkte in Defender for Endpoint onboarded werden. In diesem speziellen Szenario müssen Sie Ihre Windows Server-Endpunkte entsprechend konfigurieren. 

   - Auf Windows Server, Version 1803 oder neuer, und Windows Server 2019 können Sie festlegen, dass Microsoft Defender Antivirus im passiven Modus ausgeführt wird. 
   - Bei Windows Server 2016 muss Microsoft Defender Antivirus deaktiviert sein (der passive Modus wird auf der Windows Server 2016.

- Wenn die Endpunkte Ihrer Organisation durch eine Nicht-Microsoft-Antiviren-/Antischalwarelösung geschützt sind, wenn diese Geräte in Defender for Endpoint mit [aktivierter EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) im Blockmodus onboardiert werden, blockiert und repariert Defender for Endpoint schädliche Artefakte. **HINWEIS**: Dieses spezielle Szenario gilt nicht für Windows Server 2016. EDR im Blockmodus muss Microsoft Defender Antivirus im aktiven oder passiven Modus aktiviert sein.

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>Antivirus und Microsoft Defender for Endpoint

In der folgenden Tabelle wird zusammengefasst, was mit Microsoft Defender Antivirus geschieht, wenn Nicht-Microsoft-Antiviren-/Antischalwarelösungen zusammen oder ohne Microsoft Defender for Endpoint verwendet werden. 

| Windows-Version   | Antivirus-/Antischalwarelösung  | Onboarded to <br/> Defender for Endpoint? | Microsoft Defender Antivirus Status     |
|------|------|-------|-------|
| Windows 10  | Microsoft Defender Antivirus | Ja  | Aktiver Modus | 
| Windows 10  | Microsoft Defender Antivirus | Nein   | Aktiver Modus |
| Windows 10  | Eine Nicht-Microsoft-Antiviren-/Antischalwarelösung | Ja  | Passiver Modus (automatisch) |
| Windows 10  | Eine Nicht-Microsoft-Antiviren-/Antischalwarelösung | Nein   | Deaktivierter Modus (automatisch)    |
| Windows Server, Version 1803 oder neuer <p> Windows Server 2019 | Microsoft Defender Antivirus  | Ja |         Aktiver Modus  |
| Windows Server, Version 1803 oder neuer <p> Windows Server 2019 | Microsoft Defender Antivirus | Nein  | Aktiver Modus |
| Windows Server, Version 1803 oder neuer <p> Windows Server 2019 | Eine Nicht-Microsoft-Antiviren-/Antischalwarelösung | Ja  | Microsoft Defender Antivirus muss auf den passiven Modus festgelegt werden (manuell) <sup> [[1](#fn1)]<sup>  | 
| Windows Server, Version 1803 oder neuer <p> Windows Server 2019 | Eine Nicht-Microsoft-Antiviren-/Antischalwarelösung | Nein  | Microsoft Defender Antivirus muss deaktiviert sein (manuell) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server 2016 | Microsoft Defender Antivirus | Ja | Aktiver Modus |
| Windows Server 2016 | Microsoft Defender Antivirus | Nein | Aktiver Modus |
| Windows Server 2016 | Eine Nicht-Microsoft-Antiviren-/Antischalwarelösung | Ja | Microsoft Defender Antivirus muss deaktiviert sein (manuell) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Eine Nicht-Microsoft-Antiviren-/Antischalwarelösung | Nein | Microsoft Defender Antivirus muss deaktiviert sein (manuell) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) Auf Windows Server, Version 1803 oder neuer, oder Windows Server 2019 wechselt Microsoft Defender Antivirus nicht automatisch in den passiven Modus, wenn Sie ein Nicht-Microsoft-Antivirenprodukt installieren. Legen Sie in diesen Fällen [Microsoft Defender Antivirus passiven](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) Modus ein, um Probleme zu vermeiden, die durch die Installation mehrerer Antivirenprodukte auf einem Server verursacht werden. Sie können Microsoft Defender Antivirus mit PowerShell, Gruppenrichtlinien oder einem Registrierungsschlüssel auf den passiven Modus festlegen.

Wenn Sie Windows Server, Version 1803 oder neuer, oder Windows Server 2019 verwenden, können Sie Microsoft Defender Antivirus auf den passiven Modus festlegen, indem Sie den folgenden Registrierungsschlüssel festlegen:
- Pfad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Name: `ForceDefenderPassiveMode`
- Typ: `REG_DWORD`
- Wert: `1`

> [!NOTE]
> Der passive Modus wird auf der Windows Server 2016. Der `ForcePassiveMode` Registrierungsschlüssel kann auf Windows Server, Version 1803 oder neuer oder Windows Server 2019, aber nicht auf Windows Server 2016. 

(<a id="fn2">2</a>) Wenn Windows Server 2016 ein Nicht-Microsoft-Antivirenprodukt verwenden, können Sie Microsoft Defender Antivirus nicht im passiven oder aktiven Modus ausführen. Deaktivieren/deinstallieren Sie in [Microsoft Defender Antivirus,](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) um Probleme zu vermeiden, die durch die Installation mehrerer Antivirenprodukte auf einem Server verursacht werden.

Unter [Microsoft Defender Antivirus auf Windows Server finden](microsoft-defender-antivirus-on-windows-server.md) Sie wichtige Unterschiede und Verwaltungsoptionen für Windows Serverinstallationen.

> [!IMPORTANT]
> Microsoft Defender Antivirus ist nur auf Geräten mit Windows 10, Windows Server 2016, Windows Server, Version 1803 oder höher und Windows Server 2019 verfügbar.
>
> In Windows 8.1 und Windows Server 2012 wird der Antivirusschutz für Endpunkte auf Unternehmensebene als System Center Endpoint Protection [angeboten,](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))der über eine Microsoft Endpoint Configuration Manager.
>
> Windows Defender wird auch für Consumergeräte auf Windows 8.1 und [Windows Server 2012](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)angeboten, obwohl es keine Verwaltung auf Unternehmensebene (oder eine Schnittstelle auf Windows Server 2012 Server Core-Installationen) bietet.

## <a name="functionality-and-features-available-in-each-state"></a>Funktionen und Features, die in jedem Zustand verfügbar sind

In der Tabelle in diesem Abschnitt werden die Funktionen und Features zusammengefasst, die in den einzelnen Status verfügbar sind. Die Tabelle ist nur informationell konzipiert. Es soll die Features & Funktionen beschreiben, die aktiv funktionieren oder nicht, je nach, ob Microsoft Defender Antivirus sich im aktiven Modus, im passiven Modus oder deaktiviert/deinstalliert befindet. 

> [!IMPORTANT]
> Deaktivieren Sie keine Funktionen, z. B. Echtzeitschutz, cloudbasierter Schutz oder eingeschränkte regelmäßige Überprüfungen, wenn Sie Microsoft Defender Antivirus im passiven Modus verwenden oder EDR im Blockmodus verwenden. 

|Schutz |Aktiver Modus |Passiver Modus |EDR im Blockmodus |Deaktiviert oder deinstalliert |
|:---|:---|:---|:---|:---|
| [Echtzeitschutz und](configure-real-time-protection-microsoft-defender-antivirus.md) [cloudbasierter Schutz](enable-cloud-protection-microsoft-defender-antivirus.md) | Ja | No <sup> [[3](#fn3)]<sup> | Nein | Nein |
| [Eingeschränkte regelmäßige Überprüfungsverfügbarkeit](limited-periodic-scanning-microsoft-defender-antivirus.md) | Nein | Nein | Nein | Ja |
| [Dateiprüfungs- und Erkennungsinformationen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | Ja | Ja | Ja | Nein |
|  [Bedrohungsbehebung](configure-remediation-microsoft-defender-antivirus.md) | Ja | Siehe Hinweis <sup> [[4](#fn4)]<sup> | Ja | Nein |
| [Sicherheitsintelligenzupdates](manage-updates-baselines-microsoft-defender-antivirus.md) | Ja | Ja | Ja | Nein |

(<a id="fn3">3</a>) Wenn sich Microsoft Defender Antivirus im passiven Modus befindet, bietet der Echtzeitschutz im Allgemeinen keine Blockierung oder Erzwingung, obwohl er aktiviert und im passiven Modus ist. 

(<a id="fn4">4</a>) Wenn Microsoft Defender Antivirus sich im passiven Modus befindet, sind Features zur Bedrohungsbehebung nur während geplanter scans oder bei Bedarf aktiv.

> [!NOTE]
> [Microsoft 365 Endpoint Data Loss Prevention](/microsoft-365/compliance/endpoint-dlp-learn-about) Protection funktioniert weiterhin normal, wenn Microsoft Defender Antivirus aktiv oder passiv ist.

## <a name="keep-the-following-points-in-mind"></a>Beachten Sie die folgenden Punkte:

- Im aktiven Modus wird Microsoft Defender Antivirus als Antiviren-App auf dem Computer verwendet. Alle Konfigurationen, die mit Configuration Manager, Gruppenrichtlinien, Intune oder anderen Verwaltungsprodukten vorgenommen wurden, gelten. Dateien werden gescannt und Bedrohungen behoben, und In Ihrem Konfigurationstool werden Erkennungsinformationen gemeldet (z. B. Configuration Manager oder die Microsoft Defender Antivirus-App auf dem Computer selbst).

- Im passiven Modus Microsoft Defender Antivirus nicht als Antiviren-App verwendet, und Bedrohungen werden nicht von Microsoft Defender Antivirus. Dateien werden überprüft, und Berichte werden für Bedrohungserkennungen bereitgestellt, die für den Microsoft Defender for Endpoint-Dienst freigegeben sind. Möglicherweise werden Warnungen im [Sicherheitscenter](microsoft-defender-security-center.md) angezeigt, die Microsoft Defender Antivirus als Quelle anzeigen, auch wenn Microsoft Defender Antivirus sich im passiven Modus befindet.

- Wenn EDR im [Blockmodus](edr-in-block-mode.md) aktiviert ist und Microsoft Defender Antivirus nicht die primäre Antivirenlösung ist, werden schädliche Elemente erkannt und behoben. EDR im Blockmodus muss Microsoft Defender Antivirus im aktiven oder passiven Modus aktiviert sein.

- Wenn die App Microsoft Defender Antivirus deaktiviert ist, wird sie nicht als Antiviren-App verwendet. Dateien werden nicht gescannt, und Bedrohungen werden nicht behoben. Das Deaktivieren/Deinstallieren Microsoft Defender Antivirus wird im Allgemeinen nicht empfohlen. Wenn möglich, behalten Sie Microsoft Defender Antivirus passiven Modus bei, wenn Sie eine Nicht-Microsoft-Antimalware-/Antiviruslösung verwenden.

- Wenn Sie in Microsoft Defender for Endpoint registriert sind und ein Antischalwareprodukt eines Drittanbieters verwenden, ist der passive Modus aktiviert. Der Dienst erfordert eine allgemeine Informationsfreigabe Microsoft Defender Antivirus Diensts, um Ihre Geräte und Ihr Netzwerk ordnungsgemäß auf Angriffsversuche und Angriffe zu überwachen. Weitere Informationen finden Sie [unter Microsoft Defender Antivirus Kompatibilität mit Microsoft Defender for Endpoint](defender-compatibility.md). 

- Wenn Microsoft Defender Antivirus sich im passiven Modus befindet, können Sie weiterhin Updates [für Microsoft Defender Antivirus](manage-updates-baselines-microsoft-defender-antivirus.md); Sie können jedoch nicht Microsoft Defender Antivirus in den aktiven Modus verschieben, wenn Ihre Geräte über ein aktuelles, nicht von Microsoft entferntes Antivirenprodukt verfügen, das Echtzeitschutz vor Schadsoftware bietet. Um eine optimale Sicherheit und Erkennungseffizienz zu gewährleisten, müssen Sie den [Microsoft Defender Antivirus-Schutz (Security Intelligence Update, Engine und Platform) aktualisieren,](manage-updates-baselines-microsoft-defender-antivirus.md) auch wenn Microsoft Defender Antivirus im passiven Modus ausgeführt wird.

- Wenn Microsoft Defender Antivirus automatisch deaktiviert ist, kann sie automatisch wieder aktiviert werden, wenn der von einem Nicht-Microsoft-Antivirenprodukt angebotene Schutz abläuft oder anderweitig nicht mehr den Echtzeitschutz vor Viren, Schadsoftware oder anderen Bedrohungen bietet. Die automatische Erneute Aktivierung trägt dazu bei, sicherzustellen, dass der Virenschutz auf Ihren Geräten beibehalten wird. Außerdem können Sie eine eingeschränkte regelmäßige Überprüfung [aktivieren,](limited-periodic-scanning-microsoft-defender-antivirus.md)die das Microsoft Defender Antivirus-Modul verwendet, um zusätzlich zu Ihrer Haupt-Antivirus-App regelmäßig nach Bedrohungen zu suchen.

> [!WARNING]
> Deaktivieren, beenden oder ändern Sie keine der zugeordneten Dienste, die von Microsoft Defender Antivirus, Microsoft Defender for Endpoint oder der Windows-Sicherheit werden. Diese Empfehlung umfasst *die wscsvc-,* *SecurityHealthService-,* *MsSense-,* *Sense-,* *WinDefend-* oder *MsMpEng-Dienste* und -Prozesse. Das manuelle Ändern dieser Dienste kann zu schwerwiegenden Instabilitäten auf Ihren Geräten führen und Ihr Netzwerk anfällig machen. Das Deaktivieren, Beenden oder Ändern dieser Dienste kann auch Probleme bei der Verwendung von Nicht-Microsoft-Antivirenlösungen und bei der Anzeige ihrer Informationen in der Windows-Sicherheit [verursachen.](microsoft-defender-security-center-antivirus.md)


## <a name="see-also"></a>Siehe auch

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus auf Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EDR im Blockmodus](edr-in-block-mode.md)
- [Konfigurieren Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt](defender-endpoint-false-positives-negatives.md)
- [Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)](/microsoft-365/compliance/endpoint-dlp-learn-about)
