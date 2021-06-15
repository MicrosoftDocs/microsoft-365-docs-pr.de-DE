---
title: Konfigurieren lokaler Außerkraftsetzungen für Microsoft Defender AV-Einstellungen
description: Aktivieren oder deaktivieren Sie das lokale Ändern von Einstellungen in Microsoft Defender AV.
keywords: lokale Außerkraftsetzung, lokale Richtlinie, Gruppenrichtlinie, Gruppenrichtlinien, Sperrmodus, Zusammenführen, Listen
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
ms.date: 02/13/2020
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 2d23ca6d98d86666d72b75723a2205fcd83b08d7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924243"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>Verhindern oder zulassen, dass Benutzer Microsoft Defender Antivirus Richtlinieneinstellungen lokal ändern


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Standardmäßig verhindern Microsoft Defender Antivirus Einstellungen, die über ein Gruppenrichtlinienobjekt für die Endpunkte in Ihrem Netzwerk bereitgestellt werden, das lokale Ändern der Einstellungen durch Benutzer. Sie können dies in einigen Fällen ändern.

Beispielsweise kann es erforderlich sein, bestimmten Benutzergruppen (z. B. Sicherheitsexperten und Bedrohungsermittlern) eine weitere Kontrolle über einzelne Einstellungen auf den von ihnen verwendeten Endpunkten zu ermöglichen.

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>Konfigurieren lokaler Außerkraftsetzungen für Microsoft Defender Antivirus-Einstellungen

Die Standardeinstellung für diese Richtlinien ist **deaktiviert.**

Wenn sie auf **"Aktiviert"** festgelegt sind, können Benutzer auf Endpunkten Änderungen an der zugeordneten Einstellung mit der [Windows-Sicherheit-App,](microsoft-defender-security-center-antivirus.md) lokalen Gruppenrichtlinieneinstellungen und PowerShell-Cmdlets vornehmen (sofern zutreffend).

In der folgenden Tabelle sind die einzelnen Außerkraftsetzungsrichtlinieneinstellungen und die Konfigurationsanweisungen für das zugeordnete Feature oder die zugehörige Einstellung aufgeführt.

So konfigurieren Sie diese Einstellungen:

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und klicken Sie auf **"Administrative Vorlagen".**

3. Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus** und dann den in der folgenden Tabelle angegebenen **Speicherort.**

4. Doppelklicken Sie auf die **Richtlinieneinstellung,** wie in der folgenden Tabelle angegeben, und legen Sie die Option auf die gewünschte Konfiguration fest. Klicken Sie auf **"OK",** und wiederholen Sie dies für alle anderen Einstellungen.

5. Stellen Sie das Gruppenrichtlinienobjekt wie gewohnt bereit.

Speicherort | Setting | Artikel
---|---|---|---
Karten | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die Berichterstellung an Microsoft MAPS | [Aus der Cloud bereitgestellten Schutz aktivieren](enable-cloud-protection-microsoft-defender-antivirus.md)
Quarantäne | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für das Entfernen von Elementen aus dem Quarantäneordner | [Konfigurieren der Problembehebung für Scans](configure-remediation-microsoft-defender-antivirus.md)
Echtzeitschutz | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die Überwachung von Datei- und Programmaktivitäten auf Ihrem Computer | [Aktivieren und Konfigurieren Microsoft Defender Antivirus Always-On-Schutz und -Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md)
Echtzeitschutz | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die Überwachung eingehender und ausgehender Dateiaktivitäten | [Aktivieren und Konfigurieren Microsoft Defender Antivirus Always-On-Schutz und -Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md)
Echtzeitschutz | Konfigurieren der Außerkraftsetzung der lokalen Einstellung zum Überprüfen aller heruntergeladenen Dateien und Anlagen | [Aktivieren und Konfigurieren Microsoft Defender Antivirus Always-On-Schutz und -Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md)
Echtzeitschutz | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die Aktivierung der Verhaltensüberwachung | [Aktivieren und Konfigurieren Microsoft Defender Antivirus Always-On-Schutz und -Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md)
Echtzeitschutz | Konfigurieren der Außerkraftsetzung lokaler Einstellungen zum Aktivieren des Echtzeitschutzes | [Aktivieren und Konfigurieren Microsoft Defender Antivirus Always-On-Schutz und -Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md)
Sanierung | Konfigurieren der Außerkraftsetzung der lokalen Einstellung für die Tageszeit, um einen geplanten vollständigen Scan auszuführen, um die Wartung abzuschließen | [Konfigurieren der Problembehebung für Scans](configure-remediation-microsoft-defender-antivirus.md)
Überprüfung | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für den maximalen Prozentsatz der CPU-Auslastung | [Konfigurieren und Ausführen von Scans](run-scan-microsoft-defender-antivirus.md)
Überprüfung | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für den scan-Tag planen | [Konfigurieren von geplanten Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Überprüfung | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für geplante Schnellscanzeit | [Konfigurieren von geplanten Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Überprüfung | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die geplante Scanzeit | [Konfigurieren von geplanten Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Überprüfung | Konfigurieren der Außerkraftsetzung der lokalen Einstellung für den Scantyp, der für einen geplanten Scan verwendet werden soll | [Konfigurieren von geplanten Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>Konfigurieren der Zusammenführung von lokal und global definierten Listen zur Bedrohungsbehebung und Ausschlüssen

Sie können auch konfigurieren, wie lokal definierte Listen kombiniert oder mit global definierten Listen zusammengeführt werden. Diese Einstellung gilt für [Ausschlusslisten,](configure-exclusions-microsoft-defender-antivirus.md) [angegebene Korrekturlisten](configure-remediation-microsoft-defender-antivirus.md)und [Verringerung der Angriffsfläche.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

Standardmäßig werden Listen, die in der lokalen Gruppenrichtlinie konfiguriert wurden, und die Windows-Sicherheit-App mit Listen zusammengeführt, die durch das entsprechende Gruppenrichtlinienobjekt definiert sind, das Sie in Ihrem Netzwerk bereitgestellt haben. Wenn Konflikte bestehen, hat die global definierte Liste Vorrang.

Sie können diese Einstellung deaktivieren, um sicherzustellen, dass nur global definierte Listen (z. B. von bereitgestellten GRUPPENrichtlinienobjekten) verwendet werden.

### <a name="use-group-policy-to-disable-local-list-merging"></a>Verwenden von Gruppenrichtlinien zum Deaktivieren der zusammenführung lokaler Listen

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und klicken Sie auf **"Administrative Vorlagen".**

3. Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus.**

4. Doppelklicken Sie auf **"Lokales Administratorzusammenführungsverhalten für Listen konfigurieren",** und legen Sie die Option auf **"Deaktiviert"** fest. Klicken Sie auf **OK**.

> [!NOTE]
> Wenn Sie das Zusammenführen lokaler Listen deaktivieren, werden die Einstellungen für den kontrollierten Ordnerzugriff überschrieben. Außerdem werden alle geschützten Ordner oder zulässigen Apps überschrieben, die vom lokalen Administrator festgelegt wurden. Weitere Informationen zu einstellungen für den kontrollierten Ordnerzugriff finden Sie unter [Zulassen einer blockierten App in Windows-Sicherheit](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security).

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)
