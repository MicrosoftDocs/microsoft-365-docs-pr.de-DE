---
title: Aktivieren und Konfigurieren Microsoft Defender Antivirus Schutzfeatures
description: Aktivieren Sie verhaltensbasierten, heuristischen und Echtzeitschutz in Microsoft Defender AV.
keywords: Heuristic, Machine Learning, Verhaltensüberwachung, Echtzeitschutz, always-on, Microsoft Defender Antivirus, Antischadsoftware, Sicherheit, Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: d8ce2ded8fd3270bcb095022c714f07d8030e1f7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925563"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Konfigurieren von verhaltensbasiertem, heuristischem und Echtzeitschutz


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus verwendet verschiedene Methoden zum Schutz vor Bedrohungen:

- Über die Cloud bereitgestellter Schutz für nahezu sofortige Erkennung und Blockierung neuer und neuer Bedrohungen
- Always-On-Überprüfung unter Verwendung der Datei- und Prozessverhaltensüberwachung und anderer Heuristiken (auch als "Echtzeitschutz" bezeichnet)
- Dedizierte Updates für den Schutz, die auf Machine Learning, von Personen oder automatisch durchgeführten Big Data-Analysen und umfassenden Forschungen zur Abwehr von Bedrohungen basieren

Sie können konfigurieren, wie Microsoft Defender Antivirus diese Methoden mit Gruppenrichtlinien, System Center Konfigurationsverwaltung, PowerShell-Cmdlets und Windows-Verwaltungsinstrumentation (Management Instrumentation, WMI) verwenden.

In diesem Abschnitt wird die Konfiguration für always-on-Scans behandelt, einschließlich der Erkennung und Blockierung von Apps, die als unsicher eingestuft werden, aber möglicherweise nicht als Schadsoftware erkannt werden.

Informationen zum Aktivieren und Konfigurieren von Microsoft Defender Antivirus über die Cloud bereitgestellten Schutz finden Sie unter "Verwenden von Technologien der nächsten Generation Microsoft Defender Antivirus über den über die [Cloud bereitgestellten Schutz".](cloud-protection-microsoft-defender-antivirus.md)

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

 Thema | Beschreibung
---|---
[Erkennen und Blockieren von potenziell unerwünschten Anwendungen](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Erkennen und Blockieren von Apps, die in Ihrem Netzwerk möglicherweise unerwünscht sind, z. B. Adware, Browsermodifizierer und Symbolleisten sowie nicht autorisierte oder gefälschte Antiviren-Apps
[Aktivieren und Konfigurieren Microsoft Defender Antivirus Schutzfunktionen](configure-real-time-protection-microsoft-defender-antivirus.md) | Aktivieren und Konfigurieren von Echtzeitschutz, Heuristiken und anderen ständig aktivierten Microsoft Defender Antivirus-Überwachungsfeatures
