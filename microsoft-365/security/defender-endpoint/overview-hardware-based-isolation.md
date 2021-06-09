---
title: Hardwarebasierte Isolation (Windows 10)
ms.reviewer: ''
description: Erfahren Sie, wie die hardwarebasierte Isolation in Windows 10 zur Bekämpfung von Schadsoftware beiträgt.
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: b3babf858ac19e70119a2dc6a58b25359f1b05c1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842986"
---
# <a name="hardware-based-isolation-in-windows-10"></a>Hardwarebasierte Isolation in Windows 10

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Die hardwarebasierte Isolation trägt zum Schutz der Systemintegrität in Windows 10 bei und ist in Microsoft Defender für Endpunkt integriert. 

| Feature | Beschreibung |
|------------|-------------|
| [Windows Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | Application Guard schützt Ihr Gerät vor erweiterten Angriffen und hält Sie produktiv. Mithilfe eines eindeutigen hardwarebasierten Isolationsansatzes besteht das Ziel darin, nicht vertrauenswürdige Websites und PDF-Dokumente in einem einfachen Container zu isolieren, der über die systemeigene Windows Hypervisor vom Betriebssystem getrennt ist. Wenn sich eine nicht vertrauenswürdige Website oder ein PDF-Dokument als bösartig herausstellt, bleibt es weiterhin im sicheren Container von Application Guard enthalten, und der Desktop-PC wird geschützt und der Angreifer wird von Ihren Unternehmensdaten fern gehalten. |
| [Windows Defender System Guard](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | System Guard schützt und verwaltet die Integrität des Systems beim Start und nach der Ausführung und überprüft die Systemintegrität mithilfe des Nachweiss.  |

