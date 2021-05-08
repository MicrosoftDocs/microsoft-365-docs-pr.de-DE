---
title: Ausführen und Anpassen geplanter und bei Bedarf durchgeführter Scans
description: Anpassen und Initiieren Microsoft Defender Antivirus Überprüfungen auf Endpunkten im gesamten Netzwerk.
keywords: Scannen, Planen, Anpassen, Ausschlüsse, Dateien ausschließen, Korrekturen, Scanergebnisse, Quarantäne, Bedrohung entfernen, Schnellscan, vollständige Überprüfung, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 31dbfa2ac6d5537f6d42c0bad612be5ef059368d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275276"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>Anpassen, Initiieren und Überprüfen der Ergebnisse Microsoft Defender Antivirus Überprüfungen und Korrekturen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können Gruppenrichtlinien, PowerShell und Windows Management Instrumentation (WMI) verwenden, um Microsoft Defender Antivirus konfigurieren. 

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

Thema | Beschreibung
---|---
[Konfigurieren und Überprüfen von Datei-, Ordner- und prozess geöffneten Dateiausschlüssen in Microsoft Defender Antivirus Scans](configure-exclusions-microsoft-defender-antivirus.md) | Sie können Dateien (einschließlich Dateien, die von bestimmten Prozessen geändert wurden) und Ordner von Bedarfsscans, geplanten Scans und der Überwachung und Überprüfung des Immer-On-Schutzes in Echtzeit ausschließen.
[Konfigurieren der Scanoptionen von Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Sie können Microsoft Defender Antivirus so konfigurieren, dass bestimmte Typen von E-Mail-Speicherdateien, Back-up- oder Reparse-Punkte und archivierte Dateien (z. B. .zip Dateien) in Scans enthalten sind. Sie können auch die Überprüfung von Netzwerkdatei aktivieren.
[Konfigurieren der Korrektur für Scans](configure-remediation-microsoft-defender-antivirus.md) | Konfigurieren, Microsoft Defender Antivirus, was beim Erkennen einer Bedrohung und wie lange isolierte Dateien im Quarantäneordner aufbewahrt werden sollen
[Konfigurieren geplanter Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Einrichten von wiederkehrenden (geplanten) Scans, einschließlich der Ausführung und der Ausführung als vollständige oder schnelle Scans
[Konfigurieren und Ausführen von Scans](run-scan-microsoft-defender-antivirus.md) | Ausführen und Konfigurieren von Bedarfsscans mithilfe von PowerShell, Windows Management Instrumentation oder einzeln auf Endpunkten mit der Windows-Sicherheit App
[Überprüfen der Scanergebnisse](review-scan-results-microsoft-defender-antivirus.md) | Überprüfen der Ergebnisse von Scans mit Microsoft Endpoint Configuration Manager, Microsoft Intune oder der Windows-Sicherheit App