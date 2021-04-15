---
title: Microsoft Defender Antivirus-Kompatibilität mit anderen Sicherheitsprodukten
description: Was Sie von Microsoft Defender Antivirus mit anderen Sicherheitsprodukten und den verwendeten Betriebssystemen erwarten sollten.
keywords: Windows Defender, nächste Generation, Antivirus, Kompatibilität, passiver Modus
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 131b9970572b1034ba5c9907a001f0497d450339
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765443"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender Antivirus-Kompatibilität

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

## <a name="overview"></a>Übersicht

Microsoft Defender Antivirus wird automatisch aktiviert und auf Endpunkten und Geräten mit Windows 10 installiert. Was geschieht jedoch, wenn eine andere Antiviren-/Antischasoftwarelösung verwendet wird? Es hängt davon ab, ob Sie [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) zusammen mit Ihrem Antivirenschutz verwenden.
- Wenn die Endpunkte und Geräte Ihrer Organisation durch eine Nicht-Microsoft-Antiviren-/Antischalwarelösung geschützt sind und Microsoft Defender for Endpoint nicht verwendet wird, wechselt Microsoft Defender Antivirus automatisch in den deaktivierten Modus.
- Wenn Ihre Organisation Microsoft Defender for Endpoint zusammen mit einer Nicht-Microsoft-Antiviren-/Antischalwarelösung verwendet, wechselt Microsoft Defender Antivirus automatisch in den passiven Modus. (Echtzeitschutz und Bedrohungen werden von Microsoft Defender Antivirus nicht behoben.)
- Wenn Ihre Organisation Microsoft Defender for Endpoint zusammen mit einer nicht von Microsoft verwendeten Antiviren-/Antischasoftwarelösung verwendet und [EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) im Blockmodus aktiviert ist, wird Microsoft Defender for Endpoint immer dann aktiv, wenn ein schädliches Artefakt erkannt wird, um das Artefakt zu blockieren und zu abwehren.

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>Antivirus und Microsoft Defender for Endpoint

In der folgenden Tabelle wird zusammengefasst, was mit Microsoft Defender Antivirus geschieht, wenn Antivirenprodukte von Drittanbietern zusammen oder ohne Microsoft Defender for Endpoint verwendet werden. 


| Windows-Version   | Schutz vor Schadsoftware  | Microsoft Defender for Endpoint-Registrierung | Microsoft Defender Antivirus-Status     |
|------|------|-------|-------|
| Windows 10  | Ein Drittanbieterprodukt, das nicht von Microsoft angeboten oder entwickelt wird | Ja  | Passiver Modus  |
| Windows 10  | Ein Drittanbieterprodukt, das nicht von Microsoft angeboten oder entwickelt wird | Nein   | Automatisch deaktivierter Modus     |
| Windows 10  | Microsoft Defender Antivirus | Ja  | Aktiver Modus | 
| Windows 10  | Microsoft Defender Antivirus | Nein   | Aktiver Modus |
| Windows Server, Version 1803 oder neuer, oder Windows Server 2019 | Ein Drittanbieterprodukt, das nicht von Microsoft angeboten oder entwickelt wird | Ja  | Muss auf den passiven Modus festgelegt werden (manuell) <sup> [[1](#fn1)]<sup>  | 
| Windows Server, Version 1803 oder neuer, oder Windows Server 2019 | Ein Drittanbieterprodukt, das nicht von Microsoft angeboten oder entwickelt wird | Nein  | Muss deaktiviert sein (manuell) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server, Version 1803 oder neuer, oder Windows Server 2019 | Microsoft Defender Antivirus  | Ja |         Aktiver Modus  |
| Windows Server, Version 1803 oder neuer, oder Windows Server 2019 | Microsoft Defender Antivirus | Nein  | Aktiver Modus |
| Windows Server 2016 | Microsoft Defender Antivirus | Ja | Aktiver Modus |
| Windows Server 2016 | Microsoft Defender Antivirus | Nein | Aktiver Modus |
| Windows Server 2016 | Ein Drittanbieterprodukt, das nicht von Microsoft angeboten oder entwickelt wird | Ja | Muss deaktiviert sein (manuell) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Ein Drittanbieterprodukt, das nicht von Microsoft angeboten oder entwickelt wird | Nein | Muss deaktiviert sein (manuell) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) Unter Windows Server, Version 1803 oder neuer, oder Windows Server 2019 wechselt Microsoft Defender Antivirus nicht automatisch in den passiven Modus, wenn Sie ein Nicht-Microsoft-Antivirenprodukt installieren. Legen Sie in diesen Fällen den passiven [Modus für Microsoft Defender Antivirus](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) ein, um Probleme zu vermeiden, die durch die Installation mehrerer Antivirenprodukte auf einem Server verursacht werden.

Wenn Sie Windows Server, Version 1803 oder neuer, oder Windows Server 2019 verwenden, können Sie Microsoft Defender Antivirus auf den passiven Modus festlegen, indem Sie den folgenden Registrierungsschlüssel festlegen:
- Pfad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Name: `ForcePassiveMode`
- Typ: `REG_DWORD`
- Wert: `1`

> [!NOTE]
> Der `ForcePassiveMode` Registrierungsschlüssel wird unter Windows Server 2016 nicht unterstützt.

(<a id="fn2">2</a>) Unter Windows Server 2016 wechselt Microsoft Defender Antivirus nicht automatisch in den passiven Modus, wenn Sie ein Nicht-Microsoft-Antivirenprodukt installieren. Darüber hinaus wird Microsoft Defender Antivirus im passiven Modus nicht unterstützt. Deaktivieren/deinstallieren Sie in diesen Fällen [Microsoft Defender Antivirus](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) manuell, um Probleme zu vermeiden, die durch die Installation mehrerer Antivirenprodukte auf einem Server verursacht werden.

Wichtige [Unterschiede und Verwaltungsoptionen](microsoft-defender-antivirus-on-windows-server.md) für Windows Server-Installationen finden Sie unter Microsoft Defender Antivirus auf Windows Server.

> [!IMPORTANT]
> Microsoft Defender Antivirus ist nur auf Geräten mit Windows 10, Windows Server 2016, Windows Server, Version 1803 oder höher und Windows Server 2019 verfügbar.
>
> In Windows 8.1 und Windows Server 2012 wird der Antivirusschutz für Endpunkte auf Unternehmensebene als [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))angeboten, der über Microsoft Endpoint Configuration Manager verwaltet wird.
>
> Windows Defender wird auch für Consumergeräte auf [Windows 8.1](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)und Windows Server 2012 angeboten, obwohl es keine Verwaltung auf Unternehmensebene (oder eine Schnittstelle in server core-Installationen) Windows Server 2012 bietet.

## <a name="functionality-and-features-available-in-each-state"></a>Funktionen und Features, die in jedem Zustand verfügbar sind

In der Tabelle in diesem Abschnitt werden die Funktionen und Features zusammengefasst, die in den einzelnen Status verfügbar sind. Die Tabelle ist nur informationell konzipiert. Es soll die Features & Funktionen beschreiben, die aktiv funktionieren oder nicht, je nach, ob sich Microsoft Defender Antivirus im aktiven Modus, im passiven Modus oder deaktiviert/deinstalliert befindet. 

> [!IMPORTANT]
> Deaktivieren Sie keine Funktionen, z. B. Echtzeitschutz, cloudbasierter Schutz oder eingeschränkte regelmäßige Überprüfungen, wenn Sie Microsoft Defender Antivirus im passiven Modus verwenden oder EDR im Blockmodus verwenden. 

|Schutz |Aktiver Modus |Passiver Modus |EDR im Blockmodus |Deaktiviert oder deinstalliert |
|:---|:---|:---|:---|:---|
| [Echtzeitschutz und](./configure-real-time-protection-microsoft-defender-antivirus.md) [cloudbasierter Schutz](./enable-cloud-protection-microsoft-defender-antivirus.md) | Ja | No <sup> [[3](#fn3)]<sup> | Nein | Nein |
| [Eingeschränkte regelmäßige Überprüfungsverfügbarkeit](./limited-periodic-scanning-microsoft-defender-antivirus.md) | Nein | Nein | Nein | Ja |
| [Dateiprüfungs- und Erkennungsinformationen](./customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | Ja | Ja | Ja | Nein |
|  [Bedrohungsbehebung](./configure-remediation-microsoft-defender-antivirus.md) | Ja | Siehe Hinweis <sup> [[4](#fn4)]<sup> | Ja | Nein |
| [Sicherheitsintelligenzupdates](./manage-updates-baselines-microsoft-defender-antivirus.md) | Ja | Ja | Ja | Nein |

(<a id="fn3">3</a>) Wenn sich Microsoft Defender Antivirus im passiven Modus befindet, bietet der Echtzeitschutz im Allgemeinen keine Blockierung oder Erzwingung, obwohl er aktiviert und im passiven Modus ist. 

(<a id="fn4">4</a>) Wenn sich Microsoft Defender Antivirus im passiven Modus befindet, sind Features zur Bedrohungsbehebung nur während geplanter scans oder bei Bedarf aktiv.

> [!NOTE]
> [Microsoft 365 Endpoint Data Loss Prevention Protection](/microsoft-365/compliance/endpoint-dlp-learn-about) funktioniert weiterhin normal, wenn Microsoft Defender Antivirus im aktiven oder passiven Modus ist.

## <a name="keep-the-following-points-in-mind"></a>Beachten Sie die folgenden Punkte:

- Im aktiven Modus wird Microsoft Defender Antivirus als Antiviren-App auf dem Computer verwendet. Alle Konfigurationen, die mit Configuration Manager, Gruppenrichtlinien, Intune oder anderen Verwaltungsprodukten vorgenommen wurden, gelten. Dateien werden gescannt und Bedrohungen behoben, und In Ihrem Konfigurationstool werden Erkennungsinformationen gemeldet (z. B. Configuration Manager oder die Microsoft Defender Antivirus-App auf dem Computer selbst).

- Im passiven Modus wird Microsoft Defender Antivirus nicht als Antiviren-App verwendet, und Bedrohungen werden nicht von Microsoft Defender Antivirus behoben. Dateien werden überprüft, und Berichte werden für Bedrohungserkennungen bereitgestellt, die für den Microsoft Defender for Endpoint-Dienst freigegeben sind. Daher können Warnungen in der Security Center-Konsole mit Microsoft Defender Antivirus als Quelle auftreten, auch wenn sich Microsoft Defender Antivirus im passiven Modus befindet.

- Wenn [EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) im Blockmodus aktiviert ist und Microsoft Defender Antivirus nicht die primäre Antivirenlösung ist, kann es weiterhin schädliche Elemente erkennen und abwehren.

- Wenn sie deaktiviert ist, wird Microsoft Defender Antivirus nicht als Antiviren-App verwendet. Dateien werden nicht gescannt, und Bedrohungen werden nicht behoben. Das Deaktivieren/Deinstallieren von Microsoft Defender Antivirus wird im Allgemeinen nicht empfohlen. Halten Sie Microsoft Defender Antivirus nach Möglichkeit im passiven Modus, wenn Sie eine Nicht-Microsoft-Antimalware-/Antiviruslösung verwenden.

- Wenn Sie in Microsoft Defender for Endpoint registriert sind und ein Antischalwareprodukt eines Drittanbieters verwenden, ist der passive Modus aktiviert. [Der Dienst erfordert eine allgemeine Informationsfreigabe](/microsoft-365/security/defender-endpoint/defender-compatibility) durch den Microsoft Defender Antivirus-Dienst, um Ihre Geräte und Ihr Netzwerk ordnungsgemäß auf Angriffsversuche und Angriffe zu überwachen.

- Wenn Microsoft Defender Antivirus automatisch deaktiviert wird, kann es automatisch wieder aktiviert werden, wenn der von einem Nicht-Microsoft-Antivirenprodukt angebotene Schutz abläuft oder anderweitig aufhört, Echtzeitschutz vor Viren, Schadsoftware oder anderen Bedrohungen zu bieten. Die automatische Erneute Aktivierung trägt dazu bei, sicherzustellen, dass der Virenschutz auf Ihren Geräten beibehalten wird. Außerdem können Sie eine eingeschränkte regelmäßige Überprüfung [aktivieren,](limited-periodic-scanning-microsoft-defender-antivirus.md)die das Microsoft Defender Antivirus-Modul verwendet, um zusätzlich zu Ihrer Haupt-Antivirus-App regelmäßig nach Bedrohungen zu suchen.

- Wenn sich Microsoft Defender Antivirus im passiven Modus befindet, können Sie weiterhin Updates [für Microsoft Defender Antivirus verwalten.](manage-updates-baselines-microsoft-defender-antivirus.md) Sie können Microsoft Defender Antivirus jedoch nicht in den aktiven Modus verschieben, wenn Ihre Geräte über ein aktuelles, nicht von Microsoft entferntes Antivirenprodukt verfügen, das Echtzeitschutz vor Schadsoftware bietet. Stellen Sie sicher, dass Sie den Microsoft Defender [Antivirus-Schutz (Security Intelligence Update, Engine and Platform)](./manage-updates-baselines-microsoft-defender-antivirus.md) auch dann aktualisieren, wenn Microsoft Defender Antivirus im passiven Modus ausgeführt wird, um eine optimale Sicherheitsebene zu gewährleisten.

   Wenn Sie das Nicht-Microsoft-Antivirenprodukt deinstallieren und Microsoft Defender Antivirus zum Schutz Ihrer Geräte verwenden, wechselt Microsoft Defender Antivirus automatisch in den normalen aktiven Modus.

> [!WARNING]
> Deaktivieren, beenden oder ändern Sie keine der zugeordneten Dienste, die von Microsoft Defender Antivirus, Microsoft Defender for Endpoint oder der Windows Security-App verwendet werden. Diese Empfehlung umfasst *die wscsvc-,* *SecurityHealthService-,* *MsSense-,* *Sense-,* *WinDefend-* oder *MsMpEng-Dienste* und -Prozesse. Das manuelle Ändern dieser Dienste kann zu schwerwiegenden Instabilitäten auf Ihren Geräten führen und Ihr Netzwerk anfällig machen. Das Deaktivieren, Beenden oder Ändern dieser Dienste kann auch Probleme verursachen, wenn Nicht-Microsoft-Antivirenlösungen verwendet werden und wie ihre Informationen in der [Windows Security App angezeigt werden.](microsoft-defender-security-center-antivirus.md)


## <a name="see-also"></a>Siehe auch

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus auf Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EDR im Blockmodus](edr-in-block-mode.md)
- [Konfigurieren von Endpunktschutz](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt](defender-endpoint-false-positives-negatives.md)
- [Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)](/microsoft-365/compliance/endpoint-dlp-learn-about)