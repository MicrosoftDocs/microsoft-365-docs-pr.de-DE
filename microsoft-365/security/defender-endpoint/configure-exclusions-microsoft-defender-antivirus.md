---
title: Einrichten von Ausschlüssen für Microsoft Defender AV-Scans
description: Sie können Dateien (einschließlich Dateien, die durch bestimmte Prozesse geändert wurden) und Ordner von Microsoft Defender AV aus der Scanung ausschließen. Überprüfen Sie Ihre Ausschlüsse mit PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 47db9b4451a885c92ca4fda0f87f0150415d3338
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690730"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender Antivirus-Scans

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können bestimmte Dateien, Ordner, Prozesse und prozessge öffnende Dateien aus Microsoft Defender Antivirus-Scans ausschließen. Solche Ausschlüsse gelten für [geplante](scheduled-catch-up-scans-microsoft-defender-antivirus.md)Scans, [Bedarfsscans](run-scan-microsoft-defender-antivirus.md)und [Immer-on-Echtzeitschutz und -überwachung.](configure-real-time-protection-microsoft-defender-antivirus.md) Ausschlüsse für vom Prozess geöffnete Dateien gelten nur für den Echtzeitschutz.

## <a name="configure-and-validate-exclusions"></a>Konfigurieren und Überprüfen von Ausschlüssen

Informationen zum Konfigurieren und Überprüfen von Ausschlüssen finden Sie im Folgenden:

- [Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateinamen, Erweiterung und Ordnerspeicherort](configure-extension-file-exclusions-microsoft-defender-antivirus.md). Auf diese Weise können Sie Dateien basierend auf der Dateierweiterung, dem Dateinamen oder dem Speicherort von Microsoft Defender Antivirus-Scans ausschließen.

- [Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) Auf diese Weise können Sie Dateien von Scans ausschließen, die von einem bestimmten Prozess geöffnet wurden.

## <a name="recommendations-for-defining-exclusions"></a>Empfehlungen zum Definieren von Ausschlüssen

Durch das Definieren von Ausschlüssen wird der von Microsoft Defender Antivirus gebotene Schutz gesenkt. Sie sollten immer die Risiken bewerten, die mit der Implementierung von Ausschlüssen verbunden sind, und Sie sollten nur Dateien ausschließen, von deren Ausführung Sie sicher sind, dass sie nicht bösartig sind.

Im Folgenden finden Sie eine Liste von Empfehlungen, die Sie beim Definieren von Ausschlüssen berücksichtigen sollten:  

- Ausschlüsse sind technisch eine Schutzlücke – berücksichtigen Sie bei der Definition von Ausschlüssen immer zusätzliche Gegenmaßnahmen. Zusätzliche Gegenmaßnahmen können so einfach sein, dass sichergestellt wird, dass der ausgeschlossene Speicherort über die entsprechenden Zugriffssteuerungslisten (Access Control Lists, ACLs), Überwachungsrichtlinien, von einer aktuellen Software usw. verarbeitet wird.

- Überprüfen Sie die Ausschlüsse regelmäßig. Überprüfen und erzwingen Sie die Gegenmaßnahmen im Rahmen des Überprüfungsprozesses erneut.

- Vermeiden Sie im Idealfall das Definieren proaktiver Ausschlüsse. Schließen Sie beispielsweise etwas nicht aus, nur weil Sie denken, dass es in Zukunft ein Problem sein könnte. Verwenden Sie Ausschlüsse nur für bestimmte Probleme– hauptsächlich im Zusammenhang mit der Leistung oder manchmal im Zusammenhang mit der Anwendungskompatibilität, die durch Ausschlüsse verringert werden könnten.

- Überwachen sie die Änderungen an der Ausschlussliste. Der Sicherheitsadministrator sollte genügend Kontext beibehalten, um zu verstehen, warum ein bestimmter Ausschluss hinzugefügt wurde. Sie sollten in der Lage sein, eine Antwort mit einer bestimmten Begründung zu geben, warum ein bestimmter Pfad ausgeschlossen wurde.

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft Defender Antivirus-Ausschlüsse unter Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Häufige Fehler beim Definieren von Ausschlüssen](common-exclusion-mistakes-microsoft-defender-antivirus.md)