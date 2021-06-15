---
title: Führen Sie geplante scans und Bedarfsscans aus, und passen Sie sie an.
description: Anpassen und Initiieren Microsoft Defender Antivirus Scans auf Endpunkten in Ihrem Netzwerk
keywords: Scannen, planen, anpassen, Ausschlüsse, Dateien ausschließen, Korrektur, Scanergebnisse, Quarantäne, Bedrohung entfernen, Schnellscan, vollständiger Scan, Microsoft Defender Antivirus
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
ms.openlocfilehash: bce3fe1b6490803cb571a1a8a2387c19cc589114
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926247"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus Überprüfungen und Korrekturen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können Gruppenrichtlinien, PowerShell und Windows-Verwaltungsinstrumentation (WMI) verwenden, um Microsoft Defender Antivirus Scans zu konfigurieren. 

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

Thema | Beschreibung
---|---
[Konfigurieren und Überprüfen von Datei-, Ordner- und prozesseröffnten Dateiausschlüssen in Microsoft Defender Antivirus Scans](configure-exclusions-microsoft-defender-antivirus.md) | Sie können Dateien (einschließlich Dateien, die von angegebenen Prozessen geändert wurden) und Ordner von Bedarfsscans, geplanten Scans und always-on-Echtzeitschutzüberwachung und -überprüfung ausschließen.
[Konfigurieren der Scanoptionen von Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Sie können Microsoft Defender Antivirus so konfigurieren, dass bestimmte Typen von E-Mail-Speicherdateien, Sicherungs- oder Analysepunkte und archivierte Dateien (z. B. .zip Dateien) in Scans einbezogen werden. Sie können auch die Netzwerkdateiüberprüfung aktivieren.
[Konfigurieren der Problembehebung für Scans](configure-remediation-microsoft-defender-antivirus.md) | Konfigurieren, was Microsoft Defender Antivirus tun sollten, wenn eine Bedrohung erkannt wird und wie lange isolierte Dateien im Quarantäneordner aufbewahrt werden sollen
[Konfigurieren von geplanten Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Einrichten von wiederkehrenden (geplanten) Scans, z. B. wann sie ausgeführt werden sollen und ob sie als vollständige oder schnelle Scans ausgeführt werden sollen
[Konfigurieren und Ausführen von Scans](run-scan-microsoft-defender-antivirus.md) | Ausführen und Konfigurieren von Scans bei Bedarf mithilfe von PowerShell, Windows Verwaltungsinstrumentation oder einzeln auf Endpunkten mit der Windows-Sicherheit-App
[Überprüfen der Scanergebnisse](review-scan-results-microsoft-defender-antivirus.md) | Überprüfen der Ergebnisse von Scans mit Microsoft Endpoint Configuration Manager, Microsoft Intune oder der Windows-Sicherheit-App