---
title: Ausführen und Anpassen geplanter und bei Bedarf durchgeführter Scans
description: Anpassen und Initiieren von Microsoft Defender Antivirus-Scans auf Endpunkten im gesamten Netzwerk.
keywords: Scannen, Planen, Anpassen, Ausschlüsse, Ausschließen von Dateien, Korrektur, Scanergebnisse, Quarantäne, Bedrohung entfernen, Schnellscan, vollständige Überprüfung, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 115a8ee56ca5e9768b3aba11c37f8423ef31a67b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765695"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus-Scans und -Korrekturen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können Gruppenrichtlinien, PowerShell und Windows Management Instrumentation (WMI) verwenden, um Microsoft Defender Antivirus-Scans zu konfigurieren. 

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

Thema | Beschreibung
---|---
[Konfigurieren und Überprüfen von Datei-, Ordner- und prozess geöffneten Dateiausschlüssen in Microsoft Defender Antivirus-Scans](configure-exclusions-microsoft-defender-antivirus.md) | Sie können Dateien (einschließlich Dateien, die von bestimmten Prozessen geändert wurden) und Ordner von Bedarfsscans, geplanten Scans und der Überwachung und Überprüfung des Immer-On-Schutzes in Echtzeit ausschließen.
[Konfigurieren von Microsoft Defender Antivirus-Überprüfungsoptionen](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Sie können Microsoft Defender Antivirus so konfigurieren, dass bestimmte Typen von E-Mail-Speicherdateien, Back-up- oder Reparse-Punkte und archivierte Dateien (z. B. ZIP-Dateien) in Scans enthalten sind. Sie können auch die Überprüfung von Netzwerkdatei aktivieren.
[Konfigurieren der Korrektur für Scans](configure-remediation-microsoft-defender-antivirus.md) | Konfigurieren, was Microsoft Defender Antivirus beim Erkennen einer Bedrohung tun soll und wie lange isolierte Dateien im Quarantäneordner aufbewahrt werden sollen
[Konfigurieren geplanter Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Einrichten von wiederkehrenden (geplanten) Scans, einschließlich der Ausführung und der Ausführung als vollständige oder schnelle Scans
[Konfigurieren und Ausführen von Scans](run-scan-microsoft-defender-antivirus.md) | Ausführen und Konfigurieren von Bedarfsscans mithilfe von PowerShell, Windows Management Instrumentation oder einzeln auf Endpunkten mit der Windows Security App
[Überprüfen der Scanergebnisse](review-scan-results-microsoft-defender-antivirus.md) | Überprüfen der Ergebnisse von Scans mit Microsoft Endpoint Configuration Manager, Microsoft Intune oder der Windows Security App