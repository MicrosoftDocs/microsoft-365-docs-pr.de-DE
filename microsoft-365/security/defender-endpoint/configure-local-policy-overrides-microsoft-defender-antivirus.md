---
title: Konfigurieren lokaler Außerkraftsetzungen für Microsoft Defender AV-Einstellungen
description: Aktivieren oder Deaktivieren von Benutzer lokal ändernden Einstellungen in Microsoft Defender AV.
keywords: lokale Außerkraftsetzung, lokale Richtlinie, Gruppenrichtlinie, GPO, Sperren, Zusammenführen, Listen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 02/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 045cadf06533197fda09baa7352bf03f14dd5ba2
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690287"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen für Microsoft Defender Antivirus lokal ändern

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Standardmäßig verhindern Microsoft Defender Antivirus-Einstellungen, die über ein Gruppenrichtlinienobjekt für die Endpunkte in Ihrem Netzwerk bereitgestellt werden, dass Benutzer die Einstellungen lokal ändern. Sie können dies in einigen Fällen ändern.

Beispielsweise kann es erforderlich sein, bestimmten Benutzergruppen (z. B. Sicherheitsforschern und Bedrohungsermittlern) eine weitere Kontrolle über einzelne Einstellungen auf den von ihnen verwendeten Endpunkten zu ermöglichen.

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>Konfigurieren lokaler Außerkraftsetzungen für Microsoft Defender Antivirus-Einstellungen

Die Standardeinstellung für diese Richtlinien ist **Disabled**.

Wenn sie auf **Aktiviert** festgelegt sind, können Benutzer auf Endpunkten Änderungen an der zugeordneten Einstellung mit der [Windows Security-App,](microsoft-defender-security-center-antivirus.md) lokalen Gruppenrichtlinieneinstellungen und PowerShell-Cmdlets vornehmen (sofern dies angemessen ist).

In der folgenden Tabelle sind die einzelnen Einstellungen für die Außerkraftsetzungsrichtlinie und die Konfigurationsanweisungen für das zugeordnete Feature oder die zugehörige Einstellung aufgeführt.

So konfigurieren Sie diese Einstellungen:

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.

3. Erweitern Sie die Struktur auf **Windows-Komponenten >**  Microsoft Defender Antivirus und dann den in der folgenden Tabelle angegebenen Speicherort.

4. Doppelklicken Sie auf die **Richtlinieneinstellung,** wie in der folgenden Tabelle angegeben, und legen Sie die Option auf die gewünschte Konfiguration fest. Klicken **Sie auf OK,** und wiederholen Sie dies für alle anderen Einstellungen.

5. Stellen Sie das Gruppenrichtlinienobjekt wie gewohnt aus.

Speicherort | Einstellung | Artikel
---|---|---|---
MAPS | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die Berichterstellung an Microsoft MAPS | [Aktivieren des in der Cloud übermittelten Schutzes](enable-cloud-protection-microsoft-defender-antivirus.md)
Quarantäne | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für das Entfernen von Elementen aus dem Quarantäneordner | [Konfigurieren der Korrektur für Scans](configure-remediation-microsoft-defender-antivirus.md)
Echtzeitschutz | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für Überwachungsdatei- und Programmaktivitäten auf Ihrem Computer | [Aktivieren und Konfigurieren des ständig aktivierten Schutzes und der Überwachung von Microsoft Defender Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md)
Echtzeitschutz | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die Überwachung eingehender und ausgehender Dateiaktivitäten | [Aktivieren und Konfigurieren des ständig aktivierten Schutzes und der Überwachung von Microsoft Defender Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md)
Echtzeitschutz | Konfigurieren der Außerkraftsetzung lokaler Einstellungen zum Scannen aller heruntergeladenen Dateien und Anlagen | [Aktivieren und Konfigurieren des ständig aktivierten Schutzes und der Überwachung von Microsoft Defender Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md)
Echtzeitschutz | Konfigurieren der Außerkraftsetzung lokaler Einstellungen zum Aktivieren der Verhaltensüberwachung | [Aktivieren und Konfigurieren des ständig aktivierten Schutzes und der Überwachung von Microsoft Defender Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md)
Echtzeitschutz | Konfigurieren der Außerkraftsetzung lokaler Einstellungen zum Aktivieren des Echtzeitschutzes | [Aktivieren und Konfigurieren des ständig aktivierten Schutzes und der Überwachung von Microsoft Defender Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md)
Korrektur | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die Uhrzeit, um einen geplanten vollständigen Scan zum Abschließen der Korrektur ausführen zu können | [Konfigurieren der Korrektur für Scans](configure-remediation-microsoft-defender-antivirus.md)
Überprüfung | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für den maximalen Prozentsatz der CPU-Auslastung | [Konfigurieren und Ausführen von Scans](run-scan-microsoft-defender-antivirus.md)
Überprüfung | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für den Zeitplanscantag | [Konfigurieren geplanter Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Überprüfung | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die geplante Schnellscanzeit | [Konfigurieren geplanter Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Überprüfung | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die geplante Scanzeit | [Konfigurieren geplanter Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Überprüfung | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für den Scantyp, der für eine geplante Überprüfung verwendet werden soll | [Konfigurieren geplanter Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>Konfigurieren, wie lokal und global definierte Bedrohungsbehebungs- und Ausschlusslisten zusammengeführt werden

Sie können auch konfigurieren, wie lokal definierte Listen mit global definierten Listen kombiniert oder zusammengeführt werden. Diese Einstellung gilt für [Ausschlusslisten,](configure-exclusions-microsoft-defender-antivirus.md) [angegebene Korrekturlisten](configure-remediation-microsoft-defender-antivirus.md)und [Reduzierung der Angriffsfläche.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

Standardmäßig werden Listen, die in der lokalen Gruppenrichtlinie und der Windows Security-App konfiguriert wurden, mit Listen zusammengeführt, die durch das entsprechende Gruppenrichtlinienobjekt definiert sind, das Sie in Ihrem Netzwerk bereitgestellt haben. Bei Konflikten hat die global definierte Liste Vorrang.

Sie können diese Einstellung deaktivieren, um sicherzustellen, dass nur global definierte Listen (z. B. solche von bereitgestellten Gruppenrichtlinienobjekten) verwendet werden.

### <a name="use-group-policy-to-disable-local-list-merging"></a>Verwenden von Gruppenrichtlinien zum Deaktivieren des Zusammenführens lokaler Listen

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.

3. Erweitern Sie die Struktur auf **Windows-Komponenten > Microsoft Defender Antivirus**.

4. Doppelklicken Sie auf **Lokales Administratorzusammenführungsverhalten** für Listen konfigurieren, und legen Sie die Option auf **Deaktiviert .** Klicken Sie auf **OK**.

> [!NOTE]
> Wenn Sie das Zusammenführen lokaler Listen deaktivieren, überschreiben sie die Einstellungen für den kontrollierten Ordnerzugriff. Außerdem werden alle geschützten Ordner oder zugelassenen Apps überschrieben, die vom lokalen Administrator festgelegt wurden. Weitere Informationen zu einstellungen für den kontrollierten Ordnerzugriff finden Sie unter [Allow a blocked app in Windows Security](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security).

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)