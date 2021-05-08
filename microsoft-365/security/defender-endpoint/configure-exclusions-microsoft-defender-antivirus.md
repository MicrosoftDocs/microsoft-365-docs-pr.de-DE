---
title: Einrichten von Ausschlüssen für Microsoft Defender Antivirus Scans
description: Sie können Dateien (einschließlich Dateien, die von angegebenen Prozessen geändert wurden) und Ordner davon ausschließen, dass sie von der Microsoft Defender Antivirus. Überprüfen Sie Ihre Ausschlüsse mit PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275120"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender Antivirus Scans

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können bestimmte Dateien, Ordner, Prozesse und vom Prozess geöffnete Dateien aus Microsoft Defender Antivirus ausschließen. Solche Ausschlüsse gelten für [geplante](scheduled-catch-up-scans-microsoft-defender-antivirus.md)Scans, [Bedarfsscans](run-scan-microsoft-defender-antivirus.md)und [Immer-on-Echtzeitschutz und -überwachung.](configure-real-time-protection-microsoft-defender-antivirus.md) Ausschlüsse für vom Prozess geöffnete Dateien gelten nur für den Echtzeitschutz.

## <a name="configure-and-validate-exclusions"></a>Konfigurieren und Überprüfen von Ausschlüssen

Informationen zum Konfigurieren und Überprüfen von Ausschlüssen finden Sie im Folgenden:

- [Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateinamen, Erweiterung und Ordnerspeicherort](configure-extension-file-exclusions-microsoft-defender-antivirus.md). Sie können Dateien von Microsoft Defender Antivirus dateierweiterung, Dateinamen oder Speicherort ausschließen.

- [Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) Sie können Dateien von Scans ausschließen, die von einem bestimmten Prozess geöffnet wurden.

## <a name="recommendations-for-defining-exclusions"></a>Empfehlungen zum Definieren von Ausschlüssen

> [!IMPORTANT]
> Microsoft Defender Antivirus umfasst viele automatische Ausschlüsse basierend auf bekannten Betriebssystemverhalten und typischen Verwaltungsdateien, z. B. in unternehmensweitem Management, Datenbankverwaltung und anderen Unternehmensszenarien und -situationen.  
> 
> Durch das Definieren von Ausschlüssen wird der von der Microsoft Defender Antivirus. Sie sollten immer die Risiken bewerten, die mit der Implementierung von Ausschlüssen verbunden sind, und Sie sollten nur Dateien ausschließen, von deren Ausführung Sie sicher sind, dass sie nicht bösartig sind.

Beachten Sie beim Definieren von Ausschlüssen die folgenden Punkte:  

- Ausschlüsse sind technisch eine Schutzlücke. Berücksichtigen Sie beim Definieren von Ausschlüssen immer Gegenmaßnahmen. Andere Gegenmaßnahmen können so einfach sein, dass sichergestellt wird, dass der ausgeschlossene Speicherort über die entsprechenden Zugriffssteuerungslisten (Access Control Lists, ACLs), Überwachungsrichtlinien, von einer aktuellen Software usw. verarbeitet wird.

- Überprüfen Sie die Ausschlüsse regelmäßig. Überprüfen und erzwingen Sie die Gegenmaßnahmen im Rahmen des Überprüfungsprozesses erneut.

- Vermeiden Sie im Idealfall das Definieren von Ausschlüssen, die proaktiv sein sollen. Schließen Sie beispielsweise etwas nicht aus, nur weil Sie denken, dass es in Zukunft ein Problem sein könnte. Verwenden Sie Ausschlüsse nur für bestimmte Probleme, z. B. für Leistungs- oder Anwendungskompatibilität, die durch Ausschlüsse verringert werden könnten.

- Überwachen sie die Änderungen an der Ausschlussliste. Der Sicherheitsadministrator sollte genügend Kontext beibehalten, um zu verstehen, warum ein bestimmter Ausschluss hinzugefügt wurde. Sie sollten in der Lage sein, eine Antwort mit einer bestimmten Begründung zu geben, warum ein bestimmter Pfad ausgeschlossen wurde.

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft Defender Antivirus Ausschlüsse auf Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Häufige Fehler, die beim Festlegen von Ausschlüssen vermieden werden sollten](common-exclusion-mistakes-microsoft-defender-antivirus.md)
