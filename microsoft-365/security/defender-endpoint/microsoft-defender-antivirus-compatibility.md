---
title: Microsoft Defender Antivirus Kompatibilität mit anderen Sicherheitsprodukten
description: Erfahren Sie mehr über Microsoft Defender Antivirus mit anderen Sicherheitsprodukten und betriebssystemen.
keywords: Windows Defender, Defender für Endpunkt, nächste Generation, Antivirus, Kompatibilität, passiver Modus
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 05/08/2021
ms.openlocfilehash: f03fab3f296f98b448693c6a5d0886f409201703
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288479"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender Antivirus Kompatibilität

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

## <a name="summary"></a>Zusammenfassung

Microsoft Defender Antivirus wird automatisch aktiviert und auf Endpunkten und Geräten installiert, auf denen Windows 10 ausgeführt wird. Aber was geschieht, wenn eine andere (nicht von Microsoft stammende) Antiviren-/Antischadsoftware-Lösung verwendet wird? Dies hängt davon ab, ob Sie [Microsoft Defender für Endpunkt](microsoft-defender-endpoint.md) zusammen mit Ihrem Antivirenschutz verwenden. In diesem Artikel wird beschrieben, was mit Antiviren-/Antischadsoftwarelösungen geschieht, wenn Endpunkte in Microsoft Defender für Endpunkt integriert werden.

## <a name="keep-the-following-points-in-mind"></a>Beachten Sie die folgenden Punkte:

- Im aktiven Modus wird Microsoft Defender Antivirus als Antiviren-App auf dem Computer verwendet. Alle Konfigurationen, die mit Configuration Manager, Gruppenrichtlinien, Intune oder anderen Verwaltungsprodukten vorgenommen wurden, gelten. Dateien werden gescannt und Bedrohungen behoben, und Erkennungsinformationen werden in Ihrem Konfigurationstool gemeldet (z. B. Configuration Manager oder die Microsoft Defender Antivirus-App auf dem Computer selbst).

- Im passiven Modus wird Microsoft Defender Antivirus nicht als Antiviren-App verwendet, und Bedrohungen werden von Microsoft Defender Antivirus nicht behoben. Dateien werden gescannt, und Berichte werden für Bedrohungserkennungen bereitgestellt, die für den Microsoft Defender für Endpunkt-Dienst freigegeben sind. Möglicherweise werden im [Sicherheitscenter](microsoft-defender-security-center.md) Warnungen angezeigt, die Microsoft Defender Antivirus als Quelle anzeigen, auch wenn sich Microsoft Defender Antivirus im passiven Modus befindet.

- Wenn [EDR im Blockierungsmodus](edr-in-block-mode.md) aktiviert ist und Microsoft Defender Antivirus nicht die primäre Antivirenlösung ist, werden schädliche Elemente erkannt und behoben. EDR im Blockmodus erfordert, dass Microsoft Defender Antivirus entweder im aktiven oder im passiven Modus aktiviert ist.

- Wenn diese Option deaktiviert ist, wird Microsoft Defender Antivirus nicht als Antiviren-App verwendet. Dateien werden nicht gescannt, und Bedrohungen werden nicht behoben. Das Deaktivieren/Deinstallieren Microsoft Defender Antivirus wird im Allgemeinen nicht empfohlen. Behalten Sie nach Möglichkeit Microsoft Defender Antivirus im passiven Modus bei, wenn Sie eine Antischadsoftware-/Antivirenlösung verwenden, die nicht von Microsoft verwendet wird.

- Wenn Sie bei Microsoft Defender für Endpunkt registriert sind und ein Antischadsoftwareprodukt eines Drittanbieters verwenden, ist der passive Modus aktiviert. Der Dienst erfordert eine allgemeine Informationsfreigabe von Microsoft Defender Antivirus Dienst, um Ihre Geräte und Ihr Netzwerk ordnungsgemäß auf Angriffsversuche und Angriffe zu überwachen. Weitere Informationen finden Sie [unter Microsoft Defender Antivirus Kompatibilität mit Microsoft Defender für Endpunkt.](defender-compatibility.md) 

- Wenn sich Microsoft Defender Antivirus im passiven Modus befindet, können Sie [weiterhin Updates für Microsoft Defender Antivirus verwalten.](manage-updates-baselines-microsoft-defender-antivirus.md) Sie können jedoch Microsoft Defender Antivirus nicht in den aktiven Modus verschieben, wenn Ihre Geräte über ein aktuelles, nicht von Microsoft stammendes Antivirenprodukt verfügen, das Echtzeitschutz vor Schadsoftware bietet. Um eine optimale Sicherheit und Erkennungseffizienz zu gewährleisten, müssen Sie den [Microsoft Defender Antivirus Schutz (Security Intelligence Update, Engine und Platform)](manage-updates-baselines-microsoft-defender-antivirus.md) auch dann aktualisieren, wenn Microsoft Defender Antivirus im passiven Modus ausgeführt wird.

- Wenn Microsoft Defender Antivirus automatisch deaktiviert wird, kann es automatisch wieder aktiviert werden, wenn der Schutz eines Nicht-Microsoft-Antivirenprodukts abläuft oder anderweitig aufhört, Echtzeitschutz vor Viren, Schadsoftware oder anderen Bedrohungen bereitzustellen. Die automatische Erneute Aktivierung trägt dazu bei, sicherzustellen, dass der Virenschutz auf Ihren Geräten aufrechterhalten wird. Außerdem können Sie [eingeschränkte regelmäßige Überprüfungen](limited-periodic-scanning-microsoft-defender-antivirus.md)aktivieren, die das Microsoft Defender Antivirus-Modul verwenden, um zusätzlich zu Ihrer Haupt-Antiviren-App regelmäßig auf Bedrohungen zu prüfen.

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender Antivirus- und Nicht-Microsoft-Antiviren-/Antischadsoftwarelösungen

In der folgenden Tabelle wird zusammengefasst, was mit Microsoft Defender Antivirus geschieht, wenn nicht von Microsoft stammende Antiviren-/Antischadsoftwarelösungen zusammen oder ohne Microsoft Defender für Endpunkt verwendet werden. 

| Windows-Version   | Antiviren-/Antischadsoftwarelösung  | Onboarded to <br/> Defender für Endpunkt? | Microsoft Defender Antivirus Status     |
|------|------|-------|-------|
| Windows 10  | Microsoft Defender Antivirus | Ja  | Aktiver Modus | 
| Windows 10  | Microsoft Defender Antivirus | Nein   | Aktiver Modus |
| Windows 10  | Eine Antiviren-/Antischadsoftware-Lösung, die nicht von Microsoft verwendet wird | Ja  | Passiver Modus (automatisch) |
| Windows 10  | Eine Antiviren-/Antischadsoftware-Lösung, die nicht von Microsoft verwendet wird | Nein   | Deaktivierter Modus (automatisch)    |
| Windows Server, Version 1803 oder höher <p> Windows Server 2019 | Microsoft Defender Antivirus  | Ja |         Aktiver Modus  |
| Windows Server, Version 1803 oder höher <p> Windows Server 2019 | Microsoft Defender Antivirus | Nein  | Aktiver Modus |
| Windows Server, Version 1803 oder höher <p> Windows Server 2019 | Eine Antiviren-/Antischadsoftware-Lösung, die nicht von Microsoft verwendet wird | Ja  | Microsoft Defender Antivirus muss auf den passiven Modus (manuell) <sup> [[1](#fn1)] festgelegt werden.<sup>  | 
| Windows Server, Version 1803 oder höher <p> Windows Server 2019 | Eine Antiviren-/Antischadsoftware-Lösung, die nicht von Microsoft verwendet wird | Nein  | Microsoft Defender Antivirus müssen deaktiviert werden (manuell) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server 2016 | Microsoft Defender Antivirus | Ja | Aktiver Modus |
| Windows Server 2016 | Microsoft Defender Antivirus | Nein | Aktiver Modus |
| Windows Server 2016 | Eine Antiviren-/Antischadsoftware-Lösung, die nicht von Microsoft verwendet wird | Ja | Microsoft Defender Antivirus müssen deaktiviert werden (manuell) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Eine Antiviren-/Antischadsoftware-Lösung, die nicht von Microsoft verwendet wird | Nein | Microsoft Defender Antivirus müssen deaktiviert werden (manuell) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) Auf Windows Server, Version 1803 oder höher, oder Windows Server 2019 wechselt Microsoft Defender Antivirus nicht automatisch in den passiven Modus, wenn Sie ein Nicht-Microsoft-Antivirenprodukt installieren. Legen Sie in diesen Fällen [Microsoft Defender Antivirus auf den passiven Modus](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) fest, um Probleme zu vermeiden, die durch die Installation mehrerer Antivirenprodukte auf einem Server verursacht werden. Sie können Microsoft Defender Antivirus mithilfe von PowerShell, Gruppenrichtlinien oder einem Registrierungsschlüssel auf den passiven Modus festlegen.

Wenn Sie Windows Server, Version 1803 oder höher, oder Windows Server 2019 verwenden, können Sie Microsoft Defender Antivirus auf den passiven Modus festlegen, indem Sie den folgenden Registrierungsschlüssel festlegen:
- Pfad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Name: `ForceDefenderPassiveMode`
- Typ: `REG_DWORD`
- Wert: `1`

> [!NOTE]
> Der passive Modus wird für Windows Server 2016 nicht unterstützt. Der `ForceDefenderPassiveMode` Registrierungsschlüssel kann auf Windows Server, Version 1803 oder höher oder Windows Server 2019, aber nicht Windows Server 2016 verwendet werden. 

(<a id="fn2">2</a>) Wenn Sie auf Windows Server 2016 ein Antivirenprodukt verwenden, das nicht von Microsoft ist, können Sie Microsoft Defender Antivirus weder im passiven noch im aktiven Modus ausführen. [Deaktivieren/deinstallieren Sie in](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) solchen Fällen Microsoft Defender Antivirus manuell, um Probleme zu vermeiden, die durch die Installation mehrerer Antivirenprodukte auf einem Server verursacht werden.

Unter [Microsoft Defender Antivirus auf Windows Server](microsoft-defender-antivirus-on-windows-server.md) finden Sie die wichtigsten Unterschiede und Verwaltungsoptionen für Windows Serverinstallationen.

> [!IMPORTANT]
> Microsoft Defender Antivirus ist nur auf Geräten mit Windows 10, Windows Server 2016, Windows Server, Version 1803 oder höher und Windows Server 2019 verfügbar.
>
> In Windows 8.1 und Windows Server 2012 wird der Antivirenschutz auf Unternehmensebene als [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))angeboten, der über Microsoft Endpoint Configuration Manager verwaltet wird.
>
> Windows Defender wird auch für [Heimanwendergeräte auf Windows 8.1 und Windows Server 2012](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)angeboten, obwohl es keine Verwaltung auf Unternehmensebene (oder eine Schnittstelle auf Windows Server 2012 Server Core-Installationen) bereitstellt.

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Wie sich Microsoft Defender Antivirus auf die Defender für Endpunkt-Funktionalität auswirkt

In der Tabelle in diesem Abschnitt sind die Funktionen und Features zusammengefasst, die in den einzelnen Zuständen verfügbar sind. Die Tabelle ist so konzipiert, dass sie nur informationsbezogene Informationen enthält. Es soll die Features & Funktionen beschreiben, die aktiv funktionieren oder nicht, je nach ob sich Microsoft Defender Antivirus im aktiven Modus, im passiven Modus oder deaktiviert/deinstalliert befindet. 

> [!IMPORTANT]
> Deaktivieren Sie funktionen wie Echtzeitschutz, über die Cloud bereitgestellten Schutz oder eingeschränkte regelmäßige Überprüfungen nicht, wenn Sie Microsoft Defender Antivirus im passiven Modus oder EDR im Blockierungsmodus verwenden. 

|Schutz |Aktiver Modus |Passiver Modus |EDR im Blockmodus |Deaktiviert oder deinstalliert |
|:---|:---|:---|:---|:---|
| [Echtzeitschutz](configure-real-time-protection-microsoft-defender-antivirus.md) und [über die Cloud bereitgestellter Schutz](enable-cloud-protection-microsoft-defender-antivirus.md) | Ja | Nein <sup> [[3](#fn3)]<sup> | Nein | Nein |
| [Eingeschränkte regelmäßige Überprüfungsverfügbarkeit](limited-periodic-scanning-microsoft-defender-antivirus.md) | Nein | Nein | Nein | Ja |
| [Dateiüberprüfungs- und Erkennungsinformationen](customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | Ja | Ja | Ja | Nein |
|  [Bedrohungsbehebung](configure-remediation-microsoft-defender-antivirus.md) | Ja | Siehe Hinweis <sup> [[4](#fn4)]<sup> | Ja | Nein |
| [Security Intelligence-Updates](manage-updates-baselines-microsoft-defender-antivirus.md) | Ja | Ja | Ja | Nein |

(<a id="fn3">3</a>) Wenn sich Microsoft Defender Antivirus im passiven Modus befindet, bietet der Echtzeitschutz im Allgemeinen keine Blockierung oder Erzwingung, obwohl er aktiviert ist und sich im passiven Modus befindet. 

(<a id="fn4">4</a>) Wenn sich Microsoft Defender Antivirus im passiven Modus befindet, sind Features zur Bedrohungsbehebung nur bei geplanten scans oder On-Demand-Scans aktiv.

> [!NOTE]
> [Microsoft 365 Schutz vor Datenverlust am Endpunkt](/microsoft-365/compliance/endpoint-dlp-learn-about) funktioniert weiterhin normal, wenn sich Microsoft Defender Antivirus im aktiven oder passiven Modus befindet.

## <a name="why-defender-for-endpoint-matters"></a>Warum Defender für Endpunkt wichtig ist

Erwägen Sie das Onboarding Ihrer Endpunkte in Defender für Endpunkt, auch wenn Sie eine Antiviren-/Antischadsoftware-Lösung verwenden, die nicht von Microsoft verwendet wird. Wenn Sie Ihre Geräte in Defender für Endpunkt integrieren, können Sie in den meisten Fällen Microsoft Defender Antivirus zusammen mit Ihrer Antivirenlösung verwenden, die nicht von Microsoft verwendet wird, um zusätzlichen Schutz zu bieten. Sie können beispielsweise [EDR im Blockierungsmodus](edr-in-block-mode.md)verwenden, der bösartige Artefakte blockiert und behebt, die Ihre primäre Antivirenlösung möglicherweise übersehen hat. 

Funktionsweise:

- Wenn die Clientgeräte Ihrer Organisation durch eine Nicht-Microsoft-Antiviren-/Antimkonfliktwarelösung geschützt sind, wechselt Microsoft Defender Antivirus automatisch in den passiven Modus, wenn diese Geräte in Defender für Endpunkt integriert sind. In diesem Fall treten Bedrohungserkennungen auf, aber Echtzeitschutz und Bedrohungen werden nicht durch Microsoft Defender Antivirus behoben. **HINWEIS:** Dieses bestimmte Szenario gilt nicht für Endpunkte, die Windows Server ausgeführt werden.

- Wenn die Clientgeräte Ihrer Organisation durch eine Nicht-Microsoft-Antiviren-/Antischadsoftwarelösung geschützt sind und diese Geräte nicht in Microsoft Defender für Endpunkt integriert sind, wechselt Microsoft Defender Antivirus automatisch in den deaktivierten Modus. In diesem Fall werden Bedrohungen von Microsoft Defender Antivirus nicht erkannt oder behoben. **HINWEIS:** Dieses bestimmte Szenario gilt nicht für Endpunkte, die Windows Server ausgeführt werden.

- Wenn die Endpunkte Ihrer Organisation Windows Server ausgeführt werden und diese Endpunkte durch eine Nicht-Microsoft-Antiviren-/Antischadsoftwarelösung geschützt sind, wechselt Microsoft Defender Antivirus beim Onboarding dieser Endpunkte in Defender für Endpunkt nicht automatisch in den passiven modus oder in den deaktivierten Modus. In diesem bestimmten Szenario müssen Sie Ihre Windows Server-Endpunkte entsprechend konfigurieren. 

   - Auf Windows Server, Version 1803 oder höher, und Windows Server 2019 können Sie festlegen, dass Microsoft Defender Antivirus im passiven Modus ausgeführt wird. 
   - Auf Windows Server 2016 muss Microsoft Defender Antivirus deaktiviert sein (der passive Modus wird auf Windows Server 2016 nicht unterstützt).

- Wenn die Endpunkte Ihrer Organisation durch eine Antiviren-/Antischadsoftware-Lösung geschützt sind, die nicht von Microsoft verwendet wird, blockiert und behebt Defender für Endpunkt, wenn diese Geräte in Defender für Endpunkt integriert sind [und EDR im Blockierungsmodus](/microsoft-365/security/defender-endpoint/edr-in-block-mode) aktiviert sind. **HINWEIS:** Dieses bestimmte Szenario gilt nicht für Windows Server 2016. EDR im Blockmodus erfordert, dass Microsoft Defender Antivirus entweder im aktiven oder im passiven Modus aktiviert ist.


> [!WARNING]
> Deaktivieren, beenden oder ändern Sie keine zugeordneten Dienste, die von Microsoft Defender Antivirus, Microsoft Defender für Endpunkt oder der Windows-Sicherheit-App verwendet werden. Diese Empfehlung umfasst die Dienste und Prozesse *wscsvc*, *SecurityHealthService*, *MsSense*, *Sense*, *WinDefend* oder *MsMpEng.* Das manuelle Ändern dieser Dienste kann zu schwerwiegender Instabilität auf Ihren Geräten führen und Ihr Netzwerk anfällig machen. Das Deaktivieren, Beenden oder Ändern dieser Dienste kann auch Probleme bei der Verwendung von Antivirenlösungen verursachen, die nicht von Microsoft stammen, und dazu, wie ihre Informationen in der [Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md)angezeigt werden.


## <a name="see-also"></a>Siehe auch

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus auf Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EDR im Blockmodus](edr-in-block-mode.md)
- [Konfigurieren Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt](defender-endpoint-false-positives-negatives.md)
- [Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)](/microsoft-365/compliance/endpoint-dlp-learn-about)
