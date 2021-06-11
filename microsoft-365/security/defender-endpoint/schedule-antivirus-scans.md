---
title: Planen regelmäßiger schneller und vollständiger Scans mit Microsoft Defender Antivirus
description: Einrichten von wiederkehrenden (geplanten) Scans, z. B. wann sie ausgeführt werden sollen und ob sie als vollständige oder schnelle Scans ausgeführt werden sollen
keywords: Schnellscan, vollständiger Scan, schnell und vollständig, Scan planen, täglich, wöchentlich, Zeit, geplant, serieell, regelmäßig
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 5566050e4a64713f6f8b4ac2cb4a7188d3a241c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879724"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Konfigurieren geplanter schneller oder vollständiger Microsoft Defender Antivirus-Scans

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Zusätzlich zu always-on, Echtzeitschutz und [On-Demand Antivirus-Scans](run-scan-microsoft-defender-antivirus.md) können Sie regelmäßige, geplante Antivirenscans einrichten. Sie können den Scantyp konfigurieren, wann der Scan durchgeführt werden soll und ob der Scan nach einem [Schutzupdate](manage-protection-updates-microsoft-defender-antivirus.md) oder wenn kein Endpunkt verwendet wird. Sie können auch spezielle Scans einrichten, um ggf. Korrekturmaßnahmen auszuführen.

## <a name="what-do-you-want-to-do"></a>Was möchten Sie machen?

- [Erfahren Sie mehr über Schnellscans, vollständige Scans und benutzerdefinierte Scans](#quick-scan-full-scan-and-custom-scan)
- [Verwenden von Gruppenrichtlinien zum Planen von Antivirusscans](schedule-antivirus-scans-group-policy.md)
- [Verwenden von Windows PowerShell zum Planen von Antivirusscans](schedule-antivirus-scans-powershell.md)
- [Verwenden Windows-Verwaltungsinstrumentation zum Planen von Antivirenscans](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a>Beachten Sie die folgenden Punkte:

- Standardmäßig sucht Microsoft Defender Antivirus 15 Minuten vor dem Zeitpunkt geplanter Scans nach einem Update. Sie können den Zeitplan für das Herunterladen und Anwenden von [Schutzupdates verwalten,](manage-protection-update-schedule-microsoft-defender-antivirus.md) um diese Standardeinstellung außer Kraft zu setzen. 

- Wenn ein Gerät während eines geplanten vollständigen Scans angeschlossen wird und mit Akku betrieben wird, wird der geplante Scan mit Dem Ereignis 1002 beendet, das besagt, dass der Scan vor Abschluss beendet wurde. Microsoft Defender Antivirus führt zum nächsten geplanten Zeitpunkt eine vollständige Überprüfung durch.

## <a name="quick-scan-full-scan-and-custom-scan"></a>Schnellscan, vollständiger Scan und benutzerdefinierter Scan

Wenn Sie geplante Scans einrichten, können Sie angeben, ob es sich bei der Überprüfung um einen vollständigen oder einen Schnellscan handeln soll. In den meisten Fällen wird eine Schnellüberprüfung empfohlen. 

| Schnellscan  | Vollständiger Scan  | Benutzerdefinierter Scan |
|---------|---------|---------|
| (Empfohlen) Ein Schnellscan überprüft alle Speicherorte, an denen Schadsoftware registriert werden könnte, um mit dem System zu beginnen, z. B. Registrierungsschlüssel und bekannte Windows Startordner. <p>In Kombination mit always-on-Echtzeitschutz, der Dateien überprüft, wenn sie geöffnet und geschlossen werden, und wenn ein Benutzer zu einem Ordner navigiert, bietet ein Schnellscan starken Schutz vor Schadsoftware, die mit dem System und Schadsoftware auf Kernelebene beginnt. <p>In den meisten Fällen ist ein Schnellscan ausreichend und die empfohlene Option für geplante Scans. | Eine vollständige Überprüfung beginnt mit einer Schnellüberprüfung und wird dann mit einer sequenziellen Dateiüberprüfung aller bereitgestellten Festplatten und Wechseldatenträger/Netzlaufwerke fortgesetzt (wenn der vollständige Scan dafür konfiguriert ist). <p>Ein vollständiger Scan kann einige Stunden oder Tage dauern, abhängig von der Menge und dem Typ der Daten, die gescannt werden müssen.<p>Wenn der vollständige Scan abgeschlossen ist, ist neue Sicherheitsintelligenz verfügbar, und dann ist eine neue Überprüfung erforderlich, um sicherzustellen, dass keine anderen Bedrohungen mit der neuen Sicherheitsintelligenz erkannt werden. <p>Aufgrund der Zeit und der Ressourcen, die mit einer vollständigen Überprüfung verbunden sind, empfiehlt Microsoft im Allgemeinen nicht, vollständige Scans zu planen.  | Ein benutzerdefinierter Scan ist ein Schnellscan, der für die von Ihnen angegebenen Dateien und Ordner ausgeführt wird. Sie können z. B. ein USB-Laufwerk oder einen bestimmten Ordner auf dem lokalen Laufwerk Ihres Geräts scannen. <p> | 

> [!NOTE]
> Standardmäßig werden Schnellscans auf bereitgestellten Wechselmedien wie USB-Laufwerken ausgeführt.

## <a name="how-do-i-know-which-scan-type-to-choose"></a>Woher weiß ich, welcher Scantyp ausgewählt werden soll?

Verwenden Sie die folgende Tabelle, um einen Scantyp auszuwählen.

| Szenario  | Empfohlener Scantyp  |
|---------|---------|
| Sie möchten regelmäßige, geplante Scans einrichten.     | Schnellscan <p>Ein Schnellscan überprüft die Prozesse, den Arbeitsspeicher, die Profile und bestimmten Speicherorte auf dem Gerät. In Kombination mit [einem immer aktivierten Echtzeitschutz](configure-real-time-protection-microsoft-defender-antivirus.md)bietet ein Schnellscan eine starke Abdeckung sowohl für Schadsoftware, die mit dem System beginnt, als auch für Schadsoftware auf Kernelebene. Der Echtzeitschutz überprüft Dateien, wenn sie geöffnet und geschlossen werden und wenn ein Benutzer zu einem Ordner navigiert.         |
| Bedrohungen wie Schadsoftware werden auf einem einzelnen Gerät erkannt.     | Schnellscan <p>In den meisten Fällen erfasst und bereinigt ein Schnellscan erkannte Schadsoftware.   |
| Sie möchten eine [Überprüfung nach Bedarf](run-scan-microsoft-defender-antivirus.md) ausführen     | Schnellscan       |
| Sie möchten sicherstellen, dass ein tragbares Gerät, z. B. ein USB-Laufwerk, keine Schadsoftware enthält. | Benutzerdefinierter Scan <p>Mit einer benutzerdefinierten Überprüfung können Sie bestimmte Speicherorte, Ordner oder Dateien auswählen und einen Schnellscan ausführen. |

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>Was muss ich sonst noch über schnelle und vollständige Scans wissen?

- Schädliche Dateien können an Speicherorten gespeichert werden, die nicht in einem Schnellscan enthalten sind. Der immer aktivierte Echtzeitschutz überprüft jedoch alle Dateien, die geöffnet und geschlossen werden, sowie alle Dateien, die sich in Ordnern befinden, auf die ein Benutzer zugegriffen hat. Die Kombination aus Echtzeitschutz und schnellem Scan bietet starken Schutz vor Schadsoftware.

- Der Schutz beim Zugriff mit über die [Cloud bereitgestellten Schutz](cloud-protection-microsoft-defender-antivirus.md) trägt dazu bei, sicherzustellen, dass alle Dateien, auf die auf dem System zugegriffen wird, mit den neuesten Sicherheitsintelligenz- und Cloud Machine Learning-Modellen gescannt werden.

- Wenn der Echtzeitschutz Schadsoftware erkennt und das Ausmaß der betroffenen Dateien zunächst nicht bestimmt wird, initiiert Microsoft Defender Antivirus im Rahmen des Korrekturprozesses eine vollständige Überprüfung.

- Ein vollständiger Scan kann schädliche Dateien erkennen, die von anderen Scans nicht erkannt wurden, z. B. ein Schnellscan. Eine vollständige Überprüfung kann jedoch einige Zeit in Anspruch nehmen und wertvolle Systemressourcen nutzen, um diesen Vorgang abzuschließen.

- Wenn ein Gerät über einen längeren Zeitraum offline ist, kann ein vollständiger Scan länger dauern. 

