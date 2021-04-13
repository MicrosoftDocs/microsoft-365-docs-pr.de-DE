---
title: Aktivieren und Konfigurieren von Microsoft Defender Antivirus-Schutzfunktionen
description: Aktivieren Sie verhaltensbasierten, heuristischen und Echtzeitschutz in Microsoft Defender AV.
keywords: heuristic, machine-learning, behavior monitor, real-time protection, always-on, Microsoft Defender Antivirus, anmalware, security, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7a0e0571445e8ec753c3813a81dbcca9c698e7df
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690332"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Konfigurieren von Verhaltens-, Heuristik- und Echtzeitschutz

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus verwendet verschiedene Methoden zum Schutz vor Bedrohungen:

- In der Cloud zugestellter Schutz für die nahezu sofortige Erkennung und Blockierung neuer und neuer Bedrohungen
- Immer-on-Überprüfung unter Verwendung der Überwachung des Datei- und Prozessverhaltens und anderer Heuristiken (auch als "Echtzeitschutz" bezeichnet)
- Dedizierte Updates für den Schutz, die auf Machine Learning, von Personen oder automatisch durchgeführten Big Data-Analysen und umfassenden Forschungen zur Abwehr von Bedrohungen basieren

Sie können konfigurieren, wie Microsoft Defender Antivirus diese Methoden mit Gruppenrichtlinien, System Center Configuration Manage, PowerShell-Cmdlets und Windows Management Instrumentation (WMI) verwendet.

In diesem Abschnitt wird die Konfiguration für die immer eins zu verwendende Überprüfung behandelt, einschließlich der Erkennung und Blockierung von Apps, die als unsicher eingestuft werden, aber möglicherweise nicht als Schadsoftware erkannt werden.

Informationen zum Aktivieren und Konfigurieren des cloudbasierten Schutzes von Microsoft Defender Antivirus finden Sie unter Use [next-gen Microsoft Defender Antivirus technologies through cloud-delivered](cloud-protection-microsoft-defender-antivirus.md) protection.

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

 Thema | Beschreibung
---|---
[Erkennen und Blockieren potenziell unerwünschter Anwendungen](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Erkennen und Blockieren von Apps, die in Ihrem Netzwerk möglicherweise nicht erwünscht sind, z. B. Adware, Browsermodifizierer und Symbolleisten sowie nicht autorisierte oder gefälschte Antiviren-Apps
[Aktivieren und Konfigurieren von Microsoft Defender Antivirus-Schutzfunktionen](configure-real-time-protection-microsoft-defender-antivirus.md) | Aktivieren und Konfigurieren von Echtzeitschutz, Heuristik und anderen immer aktivierten Microsoft Defender Antivirus-Überwachungsfeatures