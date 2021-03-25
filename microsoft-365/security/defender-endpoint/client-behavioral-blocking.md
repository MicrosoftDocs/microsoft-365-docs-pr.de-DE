---
title: Clientverhaltensblockierung
description: Das Blockieren von Clientverhalten ist Teil der Funktionen zum Blockieren und Eindähen von Verhaltensweisen in Microsoft Defender ATP
keywords: Verhaltensblockierung, schneller Schutz, Clientverhalten, Microsoft Defender ATP
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: c37a1180f9def51daa4229418b05abe7cf787aa3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165261"
---
# <a name="client-behavioral-blocking"></a>Clientverhaltensblockierung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Übersicht

Die Clientverhaltensblockierung ist eine Komponente von Funktionen zum [Blockieren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) und Eindämmung von Verhaltensweisen in Defender for Endpoint. Da verdächtige Verhaltensweisen auf Geräten (auch als Clients oder Endpunkte bezeichnet) erkannt werden, werden Artefakte (z. B. Dateien oder Anwendungen) automatisch blockiert, überprüft und behoben. 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Cloud- und Clientschutz":::

Antivirusschutz funktioniert am besten, wenn er mit Cloudschutz gekoppelt ist.

## <a name="how-client-behavioral-blocking-works"></a>Funktionsweise der Clientverhaltensblockierung

[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) kann verdächtiges Verhalten, bösartigen Code, Datei- und Speicherangriffe und vieles mehr auf einem Gerät erkennen. Wenn verdächtige Verhaltensweisen erkannt werden, überwacht und sendet Microsoft Defender Antivirus diese verdächtigen Verhaltensweisen und ihre Prozessstrukturen an den Cloudschutzdienst. Maschinelles Lernen unterscheidet zwischen schädlichen Anwendungen und gutem Verhalten innerhalb von Millisekunden und klassiert jedes Artefakt. Sobald sich ein Artefakt als schädlich herausgefunden hat, wird es in fast Echtzeit auf dem Gerät blockiert. 

Wenn ein verdächtiges Verhalten erkannt wird, wird [eine](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) Warnung generiert und ist im Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) sichtbar.

Die Clientverhaltensblockierung ist effektiv, da sie nicht nur den Start eines Angriffs verhindert, sondern auch dazu beitragen kann, einen Angriff zu beenden, der mit der Ausführung begonnen hat. Und mit der [Blockierung von Feedbackschleifen](feedback-loop-blocking.md) (eine weitere Funktion der Verhaltensblockierung und -eindämmung) werden Angriffe auf andere Geräte in Ihrer Organisation verhindert.

## <a name="behavior-based-detections"></a>Verhaltensbasierte Erkennungen

Verhaltensbasierte Erkennungen werden gemäß der [MITRE ATT-&CK Matrix for Enterprise benannt.](https://attack.mitre.org/matrices/enterprise) Die Benennungskonvention hilft dabei, die Angriffsphase zu identifizieren, in der das schädliche Verhalten beobachtet wurde:


|Taktik |   Name der Erkennungsbedrohung |
|----|----|
|Anfänglicher Zugriff | Verhalten:Win32/InitialAccess.*!ml |
|Ausführung  | Behavior:Win32/Execution.*!ml |
|Persistenz    | Behavior:Win32/Persistence.*!ml |
|Berechtigungseskalation   | Verhalten:Win32/PrivilegeEscalation.*!ml |
|Schutzhinterziehung    | Behavior:Win32/DefenseEvasion.*!ml |
|Zugriff auf Anmeldeinformationen  | Verhalten:Win32/CredentialAccess.*!ml |
|Suche  | Behavior:Win32/Discovery.*!ml |
|Laterale Bewegung | Verhalten:Win32/LateralMovement.*!ml |
|Auflistung |   Behavior:Win32/Collection.*!ml |
|Befehl und Steuerelement | Verhalten:Win32/CommandAndControl.*!ml |
|Exfiltration   | Verhalten:Win32/Exfiltration.*!ml |
|Auswirkung | Behavior:Win32/Impact.*!ml |
|Nicht kategorisiert  | Verhalten:Win32/Generic.*!ml |

> [!TIP]
> Weitere Informationen zu bestimmten Bedrohungen finden Sie unter **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.


## <a name="configuring-client-behavioral-blocking"></a>Konfigurieren von Clientverhaltensblockierung

Wenn Ihre Organisation Defender for Endpoint verwendet, ist die Clientverhaltensblockierung standardmäßig aktiviert. Um jedoch von allen Defender for [](behavioral-blocking-containment.md)Endpoint-Funktionen zu profitieren, einschließlich der Verhaltensblockierung und -eindämmung, stellen Sie sicher, dass die folgenden Features und Funktionen von Defender for Endpoint aktiviert und konfiguriert sind:

- [Defender for Endpoint-Baselines](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [In Defender for Endpoint integrierte Geräte](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [EDR im Blockmodus](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Reduzierung der Angriffsfläche](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [Schutz der nächsten Generation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (Antivirus)

## <a name="related-articles"></a>Verwandte Artikel

- [Verhaltensblockierung und -eindämmung](behavioral-blocking-containment.md)

- [Blockieren von Feedbackschleifen](feedback-loop-blocking.md)

- [(Blog) Verhaltensblockierung und -eindämmung: Transformieren von Optik in Schutz](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [Hilfreiche Defender for Endpoint-Ressourcen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
