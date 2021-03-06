---
title: Konfigurieren Microsoft Defender Antivirus mit Gruppenrichtlinien
description: Erfahren Sie, wie Sie eine Gruppenrichtlinie zum Konfigurieren und Verwalten Microsoft Defender Antivirus Endpunkten in Microsoft Defender for Endpoint verwenden.
keywords: Gruppenrichtlinie, Gruppenrichtlinienobjekt, Konfiguration, Einstellungen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/08/2021
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 74f58959c22313806ebc95aef14e8ccb2d75326b
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302100"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>Verwenden von Gruppenrichtlinieneinstellungen zum Konfigurieren und Verwalten Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können [Gruppenrichtlinien verwenden,](/windows/win32/srvnodes/group-policy) um Diebst Microsoft Defender Antivirus Endpunkten zu konfigurieren und zu verwalten.

## <a name="configure-microsoft-defender-antivirus-using-group-policy"></a>Konfigurieren Microsoft Defender Antivirus mithilfe von Gruppenrichtlinien

Im Allgemeinen können Sie das folgende Verfahren verwenden, um gruppenrichtlinieneinstellungen Microsoft Defender Antivirus zu konfigurieren oder zu ändern:

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.

2. Wechseln Sie **mit dem Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

3. Klicken Sie **auf Administrative Vorlagen**.

4. Erweitern Sie die Struktur, **Windows komponenten**  >  **Microsoft Defender Antivirus.**

5. Erweitern Sie den Abschnitt (in der Tabelle **in** diesem Thema als Speicherort bezeichnet), der die zu konfigurierende Einstellung enthält, doppelklicken Sie auf die Einstellung, um sie zu öffnen, und nehmen Sie Konfigurationsänderungen vor.

6. [Stellen Sie das aktualisierte Gruppenrichtlinienobjekt wie gewohnt bereitstellen.](/windows/win32/srvnodes/group-policy) 

## <a name="group-policy-settings-and-resources"></a>Gruppenrichtlinieneinstellungen und -ressourcen

In der folgenden Tabelle in diesem Thema sind die gruppenrichtlinieneinstellungen aufgeführt, die in Windows 10, Version 1703, verfügbar sind, und enthält Links zum entsprechenden Thema in dieser Dokumentationsbibliothek (sofern zutreffend). 

> [!TIP]
> [Laden Sie das Gruppenrichtlinien-Einstellungen-Referenzkalkulationstabelle für Windows 10 May 2020 Update (2004) herunter.](https://www.microsoft.com/download/101451) In dieser Tabellenkalkulation sind die Richtlinieneinstellungen für Computer- und Benutzerkonfigurationen aufgeführt, die in den administrativen Vorlagendateien enthalten sind, die für Windows 10 May 2020 Update (2004) ausgeliefert wurden. Sie können beim Bearbeiten von Gruppenrichtlinienobjekten den Bezug auf die Kalkulationstabelle konfigurieren.

| Speicherort | Setting | Artikel |
|:---|:---|:---|
| Clientschnittstelle | Aktivieren des kopflosen Benutzeroberflächenmodus | [Verhindern, dass Benutzer die Benutzeroberfläche Microsoft Defender Antivirus sehen oder interagieren](prevent-end-user-interaction-microsoft-defender-antivirus.md) |
| Clientschnittstelle | Anzeigen von zusätzlichem Text für Clients, wenn sie eine Aktion ausführen müssen | [Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden](configure-notifications-microsoft-defender-antivirus.md) |
| Clientschnittstelle | Unterdrücken aller Benachrichtigungen | [Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden](configure-notifications-microsoft-defender-antivirus.md) |
| Clientschnittstelle | Unterdrückt Neustartbenachrichtigungen | [Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden](configure-notifications-microsoft-defender-antivirus.md) |
| Ausschlüsse | Erweiterungsausschlüsse | [Konfigurieren und Überprüfen von Ausschlüssen in Microsoft Defender Antivirus Scans](configure-exclusions-microsoft-defender-antivirus.md) |
| Ausschlüsse | Pfadausschlüsse | [Konfigurieren und Überprüfen von Ausschlüssen in Microsoft Defender Antivirus Scans](configure-exclusions-microsoft-defender-antivirus.md) |
| Ausschlüsse | Prozessausschlüsse | [Konfigurieren und Überprüfen von Ausschlüssen in Microsoft Defender Antivirus Scans](configure-exclusions-microsoft-defender-antivirus.md) | 
| Ausschlüsse | Automatische Ausschlüsse deaktivieren | [Konfigurieren und Überprüfen von Ausschlüssen in Microsoft Defender Antivirus Scans](configure-exclusions-microsoft-defender-antivirus.md) |
| MAPS | Konfigurieren des Features "Bei erster Sicht blockieren" | [Aktivieren von Block bei erster Sicht](configure-block-at-first-sight-microsoft-defender-antivirus.md) |
| MAPS | Microsoft MAPS beitreten | [Aus der Cloud bereitgestellten Schutz aktivieren](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPS | Senden von Dateibeispielen, wenn eine weitere Analyse erforderlich ist | [Aus der Cloud bereitgestellten Schutz aktivieren](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPS | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die Berichterstellung an Microsoft MAPS | [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| MpEngine | Konfigurieren der erweiterten Cloudüberprüfung | [Konfigurieren des Timeoutzeitraums für Cloudblockierung](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) |
| MpEngine | Auswählen der Cloudschutzstufe | [Stufe des über die Cloud bereitgestellten Schutzes festlegen](specify-cloud-protection-level-microsoft-defender-antivirus.md) |
| Netzwerkinspektionssystem | Angeben zusätzlicher Definitionssätze für die Überprüfung des Netzwerkdatenverkehrs | [Angeben zusätzlicher Definitionssätze für die Überprüfung des Netzwerkdatenverkehrs](specify-additional-definitions-network-traffic-inspection-mdav.md) |
| Netzwerkinspektionssystem | Aktivieren der Definitionentgrenzung | [Konfigurieren der Definitionentgrenzung](turn-on-definition-retirement.md)  |
| Netzwerkinspektionssystem | Aktivieren der Protokollerkennung | [Aktivieren der Protokollerkennung](turn-on-protocol-recognition.md)  |
| Quarantäne | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für das Entfernen von Elementen aus dem Quarantäneordner | [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Quarantäne | Konfigurieren des Entfernens von Elementen aus dem Quarantäneordner | [Konfigurieren der Korrektur für Microsoft Defender Antivirus Scans](configure-remediation-microsoft-defender-antivirus.md) |
| Echtzeitschutz | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für Überwachungsdatei- und Programmaktivitäten auf Ihrem Computer | [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Echtzeitschutz | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die Überwachung eingehender und ausgehender Dateiaktivitäten | [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Echtzeitschutz | Konfigurieren der Außerkraftsetzung lokaler Einstellungen zum Scannen aller heruntergeladenen Dateien und Anlagen | [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Echtzeitschutz | Konfigurieren der Außerkraftsetzung lokaler Einstellungen zum Aktivieren der Verhaltensüberwachung | [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Echtzeitschutz | Konfigurieren der Außerkraftsetzung lokaler Einstellungen zum Aktivieren des Echtzeitschutzes | [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Echtzeitschutz | Definieren der maximalen Größe der heruntergeladenen Dateien und Anlagen, die überprüft werden sollen | [Aktivieren und Konfigurieren Microsoft Defender Antivirus immer aktivierten Schutzes und Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Echtzeitschutz | Überwachen von Datei- und Programmaktivitäten auf Ihrem Computer | [Aktivieren und Konfigurieren Microsoft Defender Antivirus immer aktivierten Schutzes und Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Echtzeitschutz | Überprüfen aller heruntergeladenen Dateien und Anlagen | [Aktivieren und Konfigurieren Microsoft Defender Antivirus immer aktivierten Schutzes und Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Echtzeitschutz | Deaktivieren des Echtzeitschutzes | [Aktivieren und Konfigurieren Microsoft Defender Antivirus immer aktivierten Schutzes und Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Echtzeitschutz | Aktivieren der Verhaltensüberwachung | [Aktivieren und Konfigurieren Microsoft Defender Antivirus immer aktivierten Schutzes und Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Echtzeitschutz | Aktivieren der Prozessprüfung, wenn Echtzeitschutz aktiviert ist | [Aktivieren und Konfigurieren Microsoft Defender Antivirus immer aktivierten Schutzes und Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Echtzeitschutz | Aktivieren von unformatierte Volume-Schreibbenachrichtigungen | [Aktivieren und Konfigurieren Microsoft Defender Antivirus immer aktivierten Schutzes und Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Echtzeitschutz | Konfigurieren der Überwachung für eingehende und ausgehende Datei- und Programmaktivitäten | [Aktivieren und Konfigurieren Microsoft Defender Antivirus immer aktivierten Schutzes und Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Korrektur | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die Uhrzeit, um einen geplanten vollständigen Scan zum Abschließen der Korrektur ausführen zu können | [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Korrektur | Angeben des Wochentags zum Ausführen einer geplanten vollständigen Überprüfung zum Abschließen der Korrektur | [Konfigurieren geplanter Microsoft Defender Antivirus Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Korrektur | Angeben der Uhrzeit für die Ausführung einer geplanten vollständigen Überprüfung zum Abschließen der Korrektur | [Konfigurieren geplanter Microsoft Defender Antivirus Scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Reporting | Deaktivieren erweiterter Benachrichtigungen | [Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden](configure-notifications-microsoft-defender-antivirus.md)
| Root | Deaktivieren Microsoft Defender Antivirus | Nicht verwendet (Diese Einstellung  muss auf Nicht konfiguriert sein, um sicherzustellen, dass installierte Antiviren-Apps von Drittanbietern ordnungsgemäß funktionieren)
| Root | Definieren von Adressen zum Umgehen des Proxyservers | Nicht verwendet |
| Root | Definieren der proxy autoconfig (.pac) für die Verbindung mit dem Netzwerk | Nicht verwendet |
| Root | Definieren des Proxyservers für die Verbindung mit dem Netzwerk | Nicht verwendet |
| Root | Konfigurieren des Zusammenführungsverhaltens lokaler Administratoren für Listen | [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Root | Starten des Antischalwarediensts mit normaler Priorität zulassen | [Konfigurieren der Korrektur für Microsoft Defender Antivirus Scans](configure-remediation-microsoft-defender-antivirus.md) |
| Root | Zulassen, dass der Antischalwaredienst immer ausgeführt wird | [Konfigurieren der Korrektur für Microsoft Defender Antivirus Scans](configure-remediation-microsoft-defender-antivirus.md) |
| Root | Deaktivieren der Routinebehebung | [Konfigurieren der Korrektur für Microsoft Defender Antivirus Scans](configure-remediation-microsoft-defender-antivirus.md) |
| Root | Randomisieren geplanter Vorgangszeiten | [Konfigurieren geplanter Scans für Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Überprüfung | Zulassen, dass Benutzer die Überprüfung anhalten | [Verhindern, dass Benutzer die Benutzeroberfläche Microsoft Defender Antivirus](prevent-end-user-interaction-microsoft-defender-antivirus.md) sehen oder mit ihr interagieren (wird nicht auf der Windows 10) |
| Überprüfung | Überprüfen Sie vor dem Ausführen einer geplanten Überprüfung nach den neuesten Viren- und Spywaredefinitionen. | [Verwalten von ereignisbasierten erzwungenen Updates](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Überprüfung | Definieren der Anzahl der Tage, nach denen eine Nachholscan erzwungen wird | [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Überprüfung | Aktivieren der vollständigen Nachholscan | [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Überprüfung | Aktivieren der Schnellscan-Nachholung | [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Überprüfung | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für den maximalen Prozentsatz der CPU-Auslastung | [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Überprüfung | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für den Zeitplanscantag | [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Überprüfung | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die geplante Schnellscanzeit | [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Überprüfung | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für die geplante Scanzeit | [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Überprüfung | Konfigurieren der Außerkraftsetzung lokaler Einstellungen für den Scantyp, der für eine geplante Überprüfung verwendet werden soll | [Verhindern oder Zulassen, dass Benutzer Richtlinieneinstellungen lokal ändern](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Überprüfung | Erstellen eines Systemwiederherstellungspunkts | [Konfigurieren der Korrektur für Microsoft Defender Antivirus Scans](configure-remediation-microsoft-defender-antivirus.md) |
| Überprüfung | Aktivieren des Entfernens von Elementen aus dem Ordner "Scanverlauf" | [Konfigurieren der Korrektur für Microsoft Defender Antivirus Scans](configure-remediation-microsoft-defender-antivirus.md) |
| Überprüfung | Aktivieren von Heuristiken | [Aktivieren und Konfigurieren Microsoft Defender Antivirus immer aktivierten Schutzes und Überwachung](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Überprüfung | Aktivieren der E-Mail-Überprüfung | [Konfigurieren von Überprüfungsoptionen in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Überprüfung | Aktivieren der Überprüfung von Reparse point | [Konfigurieren von Überprüfungsoptionen in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Überprüfung | Ausführen der vollständigen Überprüfung auf zugeordneten Netzwerklaufwerken | [Konfigurieren von Überprüfungsoptionen in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Überprüfung | Überprüfen von Archivdateien | [Konfigurieren von Überprüfungsoptionen in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Überprüfung | Überprüfen von Netzwerkdateien | [Konfigurieren von Überprüfungsoptionen in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Überprüfung | Scannen von verpackten ausführbaren Dateien | [Konfigurieren von Überprüfungsoptionen in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Überprüfung | Scannen von Wechseldatenträgern | [Konfigurieren von Überprüfungsoptionen in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Überprüfung | Angeben der maximalen Tiefe zum Überprüfen von Archivdateien | [Konfigurieren von Überprüfungsoptionen in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Überprüfung | Angeben des maximalen Prozentsatzes der CPU-Auslastung während einer Überprüfung | [Konfigurieren von Überprüfungsoptionen in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Überprüfung | Angeben der maximalen Größe der zu scannende Archivdateien | [Konfigurieren von Überprüfungsoptionen in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Überprüfung | Angeben des Wochentags zum Ausführen einer geplanten Überprüfung | [Konfigurieren geplanter Scans für Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Überprüfung | Angeben des Intervalls zum Ausführen von Schnellscans pro Tag | [Konfigurieren geplanter Scans für Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Überprüfung | Angeben des Scantyps, der für eine geplante Überprüfung verwendet werden soll | [Konfigurieren geplanter Scans für Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Überprüfung | Angeben der Uhrzeit für einen täglichen Schnellscan | [Konfigurieren geplanter Scans für Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Überprüfung | Angeben der Uhrzeit für die Ausführung einer geplanten Überprüfung | [Konfigurieren geplanter Scans für Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Überprüfung | Starten der geplanten Überprüfung nur, wenn der Computer zwar installiert ist, aber nicht verwendet wird | [Konfigurieren geplanter Scans für Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Zulassen von Sicherheitsintelligenzupdates von Microsoft Update | [Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Zulassen von Sicherheitsintelligenzupdates bei Akkubetrieb | [Verwalten von Updates für Mobilgeräte und virtuelle Computer (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Zulassen, dass Benachrichtigungen definitionsbasierte Berichte für Microsoft MAPS deaktivieren | [Verwalten von ereignisbasierten erzwungenen Updates](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Zulassen von Sicherheitsintelligenzupdates in Echtzeit basierend auf Berichten an Microsoft MAPS | [Verwalten von ereignisbasierten erzwungenen Updates](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Überprüfen der neuesten Viren- und Spywaredefinitionen beim Start | [Verwalten von ereignisbasierten erzwungenen Updates](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Definieren von Dateifreigaben für das Herunterladen von Sicherheitsintelligenzupdates | [Verwalten Microsoft Defender Antivirus von Schutz- und Sicherheitsintelligenzupdates](manage-protection-updates-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Definieren der Anzahl von Tagen, nach denen ein Nachholupdate für sicherheitsintelligenz erforderlich ist | [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Definieren der Anzahl von Tagen, bevor Spywaredefinitionen als veraltet betrachtet werden | [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Definieren der Anzahl von Tagen, bevor Virendefinitionen als veraltet betrachtet werden | [Verwalten von Updates für veraltete Endpunkte](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Definieren der Reihenfolge der Quellen für das Herunterladen von Sicherheitsintelligenzupdates | [Verwalten Microsoft Defender Antivirus von Schutz- und Sicherheitsintelligenzupdates](manage-protection-updates-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Initiieren von Sicherheitsintelligenzupdates beim Start | [Verwalten von ereignisbasierten erzwungenen Updates](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Angeben des Wochentags, an dem nach Sicherheitsintelligenzupdates überprüft werden soll | [Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Angeben des Intervalls, das auf Sicherheitsintelligenzupdates überprüft werden soll | [Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Angeben der Zeit für die Überprüfung auf Sicherheitsintelligenzupdates | [Verwalten, wann Schutzupdates heruntergeladen und angewendet werden sollen](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Sicherheitsintelligenzupdates | Aktivieren der Überprüfung nach dem Update der Sicherheitsintelligenz | [Konfigurieren geplanter Scans für Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Risiken | Angeben von Warnungsstufen für Bedrohungen, bei denen beim Erkennen keine Standardaktion ergriffen werden soll | [Konfigurieren der Korrektur für Microsoft Defender Antivirus Scans](configure-remediation-microsoft-defender-antivirus.md) |
| Risiken | Angeben von Bedrohungen, bei denen die Standardaktion beim Erkennen nicht ergriffen werden soll | [Konfigurieren der Korrektur für Microsoft Defender Antivirus Scans](configure-remediation-microsoft-defender-antivirus.md) |

## <a name="see-also"></a>Siehe auch

- [Referenzthemen für Verwaltungs- und Konfigurationstools](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
