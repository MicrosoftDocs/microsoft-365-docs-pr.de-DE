---
title: Client-Verhaltensblockierung
description: Das Blockieren von Clientverhalten ist Teil der Funktionen zum Blockieren und Eindämmen von Verhaltensweisen in Microsoft Defender für Endpunkt.
keywords: Verhaltensblockierung, schneller Schutz, Clientverhalten, Microsoft Defender für Endpunkt
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
ms.openlocfilehash: 4e416aa9484f251280649035247a59dcc82ce750
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795958"
---
# <a name="client-behavioral-blocking"></a>Client-Verhaltensblockierung

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Übersicht

Das Blockieren von Clientverhalten ist eine Komponente der Funktionen zum [Blockieren und Eindämmen](behavioral-blocking-containment.md) von Verhaltensweisen in Defender für Endpunkt. Da verdächtige Verhaltensweisen auf Geräten erkannt werden (auch als Clients oder Endpunkte bezeichnet), werden Artefakte (z. B. Dateien oder Anwendungen) automatisch blockiert, überprüft und behoben. 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Cloud- und Clientschutz":::

Antivirusschutz funktioniert am besten, wenn er mit Cloudschutz kombiniert wird.

## <a name="how-client-behavioral-blocking-works"></a>Funktionsweise der Blockierung von Clientverhalten

[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) können verdächtiges Verhalten, bösartigen Code, Datei- und Speicherangriffe und vieles mehr auf einem Gerät erkennen. Wenn verdächtige Verhaltensweisen erkannt werden, überwacht und sendet Microsoft Defender Antivirus diese verdächtigen Verhaltensweisen und deren Prozessstrukturen an den Cloudschutzdienst. Machine Learning unterscheidet zwischen schädlichen Anwendungen und gutem Verhalten innerhalb von Millisekunden und klassifiziert jedes Artefakt. Sobald ein Artefakt als bösartig eingestuft wird, wird es nahezu in Echtzeit auf dem Gerät blockiert. 

Wenn ein verdächtiges Verhalten erkannt wird, wird eine [Warnung](alerts-queue.md) generiert und ist im Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) sichtbar.

Das Blockieren von Clientverhalten ist effektiv, da es nicht nur dazu beiträgt, den Start eines Angriffs zu verhindern, es kann auch dazu beitragen, einen Angriff zu stoppen, der mit der Ausführung begonnen hat. Und mit der Blockierung von [Feedbackschleifen](feedback-loop-blocking.md) (eine weitere Möglichkeit zum Blockieren und Eindämmen von Verhaltensweisen) werden Angriffe auf anderen Geräten in Ihrer Organisation verhindert.

## <a name="behavior-based-detections"></a>Verhaltensbasierte Erkennungen

Verhaltensbasierte Erkennungen werden gemäß der [MITRE ATT-&CK-Matrix für Enterprise](https://attack.mitre.org/matrices/enterprise)benannt. Die Benennungskonvention hilft bei der Identifizierung der Angriffsphase, in der das böswillige Verhalten beobachtet wurde:


|Taktik |   Name der Erkennungsgefahr |
|----|----|
|Anfänglicher Zugriff | `Behavior:Win32/InitialAccess.*!ml` |
|Ausführung  | `Behavior:Win32/Execution.*!ml` |
|Persistenz    | `Behavior:Win32/Persistence.*!ml` |
|Berechtigungseskalation   | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|DefenseSynekte    | `Behavior:Win32/DefenseEvasion.*!ml` |
|Zugriff auf Anmeldeinformationen  | `Behavior:Win32/CredentialAccess.*!ml` |
|Suche  | `Behavior:Win32/Discovery.*!ml` |
|Lateralverschiebung | `Behavior:Win32/LateralMovement.*!ml` |
|Auflistung |   `Behavior:Win32/Collection.*!ml` |
|Befehl und Steuerelement | `Behavior:Win32/CommandAndControl.*!ml` |
|Exfiltration   | `Behavior:Win32/Exfiltration.*!ml` |
|Auswirkung | `Behavior:Win32/Impact.*!ml` |
|Uncategorized  | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> Weitere Informationen zu bestimmten Bedrohungen finden Sie unter **[den aktuellen globalen Bedrohungsaktivitäten.](https://www.microsoft.com/wdsi/threats)**


## <a name="configuring-client-behavioral-blocking"></a>Konfigurieren der Blockierung von Clientverhalten

Wenn Ihre Organisation Defender für Endpunkt verwendet, ist die Blockierung von Clientverhalten standardmäßig aktiviert. Um jedoch von allen Defender für Endpunkt-Funktionen zu profitieren, einschließlich [verhaltensbasierter Blockierung und Eindämmung,](behavioral-blocking-containment.md)stellen Sie sicher, dass die folgenden Features und Funktionen von Defender für Endpunkt aktiviert und konfiguriert sind:

- [Baselines für Defender für Endpunkt](configure-machines-security-baseline.md)

- [Geräte, die in Defender für Endpunkt integriert sind](onboard-configure.md)

- [EDR im Blockmodus](edr-in-block-mode.md)

- [Verringerung der Angriffsfläche](attack-surface-reduction.md):

- [Schutz](configure-microsoft-defender-antivirus-features.md) der nächsten Generation (Antivirus, Antischadsoftware und andere Bedrohungsschutzfunktionen)

