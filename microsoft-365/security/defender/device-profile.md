---
title: Geräteprofil im Microsoft 365 Sicherheitsportal
description: Anzeigen von Risiken und Belichtungsstufen für ein Gerät in Ihrer Organisation. Analysieren Sie frühere und aktuelle Bedrohungen, und schützen Sie das Gerät mit den neuesten Updates.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Microsoft 365 Defender, Security Center, Microsoft Defender für Endpunkt, Microsoft Defender für Office 365, Microsoft Defender for Identity, Geräteseite, Geräteprofil, Computerseite, Computerprofil
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 47b25ba541264d79216748753e9f41fb7435fc10
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229479"
---
# <a name="device-profile-page"></a>Seite "Geräteprofil"

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Das Microsoft 365-Sicherheitsportal bietet Ihnen Geräteprofilseiten, sodass Sie den Status und Status von Geräten in Ihrem Netzwerk schnell bewerten können.

> [!IMPORTANT]
> Die Seite "Geräteprofil" kann geringfügig anders angezeigt werden, je nachdem, ob das Gerät bei Microsoft Defender für Endpunkt, Microsoft Defender for Identity oder bei beiden registriert ist.

Wenn das Gerät in Microsoft Defender für Endpunkt registriert ist, können Sie auch die Geräteprofilseite verwenden, um einige allgemeine Sicherheitsaufgaben auszuführen.

## <a name="navigating-the-device-profile-page"></a>Navigieren auf der Geräteprofilseite

Die Profilseite ist in mehrere breite Abschnitte unterteilt.

![Abbildung der Geräteprofilseite mit (1) Tab-Bereich (2) Randleiste und (3) Rot hervorgehobene Aktionen](../../media/mtp-device-profile/hybrid-device-overall.png)

In der Randleiste (1) sind grundlegende Details zum Gerät aufgeführt.

Der Hauptinhaltsbereich (2) enthält Registerkarten, die Sie umschalten können, um verschiedene Arten von Informationen über das Gerät anzuzeigen.

Wenn das Gerät in Microsoft Defender für Endpunkt registriert ist, wird auch eine Liste der Antwortaktionen angezeigt (3). MitHilfe von Reaktionsaktionen können Sie allgemeine sicherheitsrelevante Aufgaben ausführen.

## <a name="sidebar"></a>Seitenleiste

Neben dem Hauptinhaltsbereich der Geräteprofilseite befindet sich die Randleiste.

![Abbildung der Seitenleistenregisterkarte für Das Geräteprofil](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

Die Randleiste listet den vollständigen Namen und die Belichtungsebene des Geräts auf. Außerdem werden einige wichtige grundlegende Informationen in kleinen Unterabschnitten bereitgestellt, die geöffnet oder geschlossen werden können, z. B.:

* **Tags** – alle Microsoft Defender für Endpunkt, Microsoft Defender for Identity oder benutzerdefinierte Tags, die dem Gerät zugeordnet sind. Tags aus Microsoft Defender for Identity können nicht bearbeitet werden.
* **Sicherheitsinformationen –** Offene Vorfälle und aktive Warnungen. Geräte, die in Microsoft Defender für Endpunkt registriert sind, zeigen auch die Belichtungsstufe und das Risikoniveau an.

> [!TIP]
> Die Gefährdungsstufe bezieht sich darauf, wie weit das Gerät den Sicherheitsempfehlungen entspricht, während das Risikoniveau basierend auf einer Reihe von Faktoren berechnet wird, einschließlich der Typen und des Schweregrads aktiver Warnungen.

* **Gerätedetails** – Domäne, Betriebssystem, Zeitstempel, wann das Gerät zum ersten Mal angezeigt wurde, IP-Adressen, Ressourcen. Geräte, die in Microsoft Defender für Endpunkt registriert sind, zeigen auch den Integritätsstatus an. Geräte, die in Microsoft Defender for Identity registriert sind, zeigen den SAM-Namen und einen Zeitstempel für den Zeitpunkt an, zu dem das Gerät zum ersten Mal erstellt wurde.
* **Netzwerkaktivität** – Zeitstempel zum ersten Mal und zum letzten Mal, wenn das Gerät im Netzwerk angezeigt wurde.
* **Verzeichnisdaten** ( nur für Geräte, die *in Microsoft Defender for Identity registriert sind)*– [UAC-Flags,](/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPNs](/windows/win32/ad/service-principal-names)und Gruppenmitgliedschaften.

## <a name="response-actions"></a>Antwortaktionen

Reaktionsaktionen bieten eine schnelle Möglichkeit, sich vor Bedrohungen zu schützen und diese zu analysieren.

![Abbildung der Aktionsleiste für Geräteprofil](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [Antwortaktionen](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) sind nur verfügbar, wenn das Gerät in Microsoft Defender für Endpunkt registriert ist.
> * Geräte, die in Microsoft Defender für Endpunkt registriert sind, zeigen je nach Betriebssystem und Versionsnummer des Geräts möglicherweise unterschiedliche Anzahl von Antwortaktionen an.

Zu den auf der Geräteprofilseite verfügbaren Aktionen gehören:

* **Verwalten von Tags** – Aktualisiert benutzerdefinierte Tags, die Sie auf dieses Gerät angewendet haben.
* **Gerät isolieren** – Isoliert das Gerät aus dem Netzwerk Ihrer Organisation, während es mit Microsoft Defender für Endpunkt verbunden ist. Sie können die Ausführung Outlook, Teams und Skype for Business zulassen, während das Gerät isoliert ist, für Kommunikationszwecke.
* **Info-Center** – Zeigen Sie den Status der übermittelten Aktionen an. Nur verfügbar, wenn bereits eine andere Aktion ausgewählt wurde.
* **Einschränken der App-Ausführung** – Verhindert die Ausführung von Anwendungen, die nicht von Microsoft signiert sind.
* **Führen Sie einen Antivirusscan aus:** Aktualisiert Windows Defender Antivirus Definitionen und führt sofort einen Antivirenscan aus. Wählen Sie zwischen "Schnellscan" oder "Vollständiger Scan".
* **Erfassen des Untersuchungspakets** – Sammelt Informationen über das Gerät. Wenn die Untersuchung abgeschlossen ist, können Sie sie herunterladen.
* **Initiieren einer Live-Antwortsitzung** – Lädt eine Remoteshell auf dem Gerät für [eingehende Sicherheitsuntersuchungen.](/microsoft-365/security/defender-endpoint/live-response)
* **Automatische Untersuchung initiieren** – Bedrohungen automatisch [untersuchen und beheben.](../office-365-security/office-365-air.md) Sie können zwar manuell automatische Untersuchungen auslösen, um von dieser Seite aus ausgeführt zu werden, [bestimmte Warnungsrichtlinien](../../compliance/alert-policies.md#default-alert-policies) lösen jedoch automatische Untersuchungen selbst aus.
* **Info-Center** – Zeigt Informationen zu allen derzeit ausgeführten Antwortaktionen an.

## <a name="tabs-section"></a>Tabs section

Mithilfe der Geräteprofilregisterkarten können Sie eine Übersicht über Sicherheitsdetails zum Gerät und Tabellen mit einer Liste von Warnungen durchschalten.

Geräte, die bei Microsoft Defender für Endpunkt registriert sind, zeigen auch Registerkarten mit einer Zeitachse, einer Liste von Sicherheitsempfehlungen, einem Softwareinventar, einer Liste der ermittelten Sicherheitsrisiken und fehlenden KBs (Sicherheitsupdates) an.

### <a name="overview-tab"></a>Registerkarte „Übersicht“

Die Standardregisterkarte ist **Übersicht.** Es bietet einen kurzen Überblick über die wichtigsten Sicherheitsinformationen zum Gerät.

![Abbildung der Registerkarte "Übersicht" für Das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

Hier erhalten Sie einen kurzen Überblick über die aktiven Warnungen des Geräts und alle derzeit angemeldeten Benutzer.

Wenn das Gerät in Microsoft Defender für Endpunkt registriert ist, werden auch die Risikostufe des Geräts und alle verfügbaren Daten zu Sicherheitsbewertungen angezeigt. Die Sicherheitsbewertungen beschreiben die Gefährdungsstufe des Geräts, geben Sicherheitsempfehlungen und listen betroffene Software und erkannte Sicherheitsrisiken auf.

### <a name="alerts-tab"></a>Registerkarte "Warnungen"

Die Registerkarte **"Warnungen"** enthält eine Liste der Warnungen, die auf dem Gerät ausgelöst wurden, sowohl von Microsoft Defender for Identity als auch von Microsoft Defender für Endpunkt.

![Abbildung der Registerkarte "Warnungen" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

Sie können die Anzahl der angezeigten Elemente sowie die Spalten anpassen, die für jedes Element angezeigt werden. Standardmäßig werden 30 Elemente pro Seite aufgeführt.

Die Spalten auf dieser Registerkarte enthalten Informationen zum Schweregrad der Bedrohung, die die Warnung ausgelöst hat, sowie status, untersuchungsstatus und wem die Warnung zugewiesen wurde.

Die *betroffene Entitätenspalte* bezieht sich auf das Gerät (Entität), dessen Profil Sie derzeit anzeigen, sowie auf alle anderen Geräte in Ihrem Netzwerk, die betroffen sind.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, das noch mehr Informationen zur ausgewählten Warnung enthält.

Diese Liste kann nach Schweregrad, Status oder der Person gefiltert werden, der die Warnung zugewiesen wurde.

### <a name="timeline-tab"></a>Registerkarte "Zeitachse"

Die Registerkarte **"Zeitachse"** enthält ein interaktives, chronologisches Diagramm aller Ereignisse, die auf dem Gerät ausgelöst werden. Durch Verschieben des hervorgehobenen Bereichs des Diagramms nach links oder rechts können Sie Ereignisse über verschiedene Zeiträume hinweg anzeigen. Sie können auch einen benutzerdefinierten Datumsbereich aus dem Dropdownmenü zwischen dem interaktiven Diagramm und der Liste der Ereignisse auswählen.

Unterhalb des Diagramms befindet sich eine Liste der Ereignisse für den ausgewählten Datumsbereich.

![Abbildung der Zeitachsenregisterkarte für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

Die Anzahl der angezeigten Elemente und die Spalten in der Liste können beide angepasst werden. In den Standardspalten sind die Ereigniszeit, der aktive Benutzer, der Aktionstyp, Entitäten (Prozesse) und zusätzliche Informationen zum Ereignis aufgeführt.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout mit einem Diagramm "Ereignisentitäten" geöffnet, in dem die übergeordneten und untergeordneten Prozesse angezeigt werden, die an dem Ereignis beteiligt sind.

Die Liste kann nach der jeweiligen Art des Ereignisses gefiltert werden. Beispielsweise Registrierungsereignisse oder SmartScreen-Ereignisse.

Die Liste kann auch zum Download in eine CSV-Datei exportiert werden. Obwohl die Datei nicht durch die Anzahl der Ereignisse begrenzt ist, beträgt der maximale Zeitraum, den Sie exportieren möchten, sieben Tage.

### <a name="security-recommendations-tab"></a>Registerkarte "Sicherheitsempfehlungen"

Die Registerkarte **"Sicherheitsempfehlungen"** enthält Aktionen, die Sie zum Schutz des Geräts ausführen können. Wenn Sie ein Element in dieser Liste auswählen, wird ein Flyout geöffnet, in dem Sie Anweisungen zur Anwendung der Empfehlung erhalten können.

![Abbildung der Registerkarte "Sicherheitsempfehlungen" für Das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

Wie bei den vorherigen Registerkarten kann auch die Anzahl der pro Seite angezeigten Elemente sowie die sichtbaren Spalten angepasst werden.

Die Standardansicht enthält Spalten, in denen die behobenen Sicherheitsschwächen, die zugehörige Bedrohung, die zugehörige Komponente oder Software, die von der Bedrohung betroffen sind, und vieles mehr aufgeführt sind. Elemente können nach dem Status der Empfehlung gefiltert werden.

### <a name="software-inventory"></a>Softwarebestand

Auf der Registerkarte **"Softwareinventur"** ist die auf dem Gerät installierte Software aufgeführt.

![Abbildung der Registerkarte "Softwareinventur" für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

Die Standardansicht zeigt den Softwareanbieter, die installierte Versionsnummer, die Anzahl bekannter Softwareschwächen, Bedrohungserkenntnisse, Denkcode und Tags an. Die Anzahl der angezeigten Elemente und die angezeigten Spalten können beide angepasst werden.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout mit weiteren Details zur ausgewählten Software sowie dem Pfad und Zeitstempel für das letzte Mal geöffnet, in dem die Software gefunden wurde.

Diese Liste kann nach dem Produktcode gefiltert werden.

### <a name="discovered-vulnerabilities-tab"></a>Registerkarte "Ermittelte Sicherheitsrisiken"

Auf der Registerkarte **"Ermittelte Sicherheitsrisiken"** sind alle allgemeinen Sicherheitsrisiken und Exploits (Common Vulnerabilities and Exploits, CVEs) aufgeführt, die sich auf das Gerät auswirken können.

![Abbildung der Registerkarte "Ermittelte Sicherheitsrisiken" für Das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

In der Standardansicht sind der Schweregrad von CVE, die Common Vulnerability Score (CVS), die Software im Zusammenhang mit CVE, die Veröffentlichung der CVE, die letzte Aktualisierung der CVE und bedrohungsbezogene Bedrohungen aufgeführt.

Wie bei den vorherigen Registerkarten kann die Anzahl der angezeigten Elemente und die sichtbaren Spalten angepasst werden.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, das die CVE beschreibt.

### <a name="missing-kbs"></a>Fehlende KBs

Auf der Registerkarte **"Fehlende KBs"** sind alle Microsoft-Updates aufgeführt, die noch auf das Gerät angewendet werden müssen. Die betreffenden "KBs" sind [Knowledge Base-Artikel,](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) in denen diese Updates beschrieben werden. Beispielsweise [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![Abbildung der fehlenden KBS-Registerkarte für Das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

In der Standardansicht wird dasBulletin mit den Updates, der Betriebssystemversion, den betroffenen Produkten, den adressierten CVEs, der KB-Nummer und den Tags aufgelistet.

Die Anzahl der pro Seite angezeigten Elemente und welche Spalten angezeigt werden, kann angepasst werden.

Wenn Sie ein Element auswählen, wird ein Flyout geöffnet, das mit dem Update verknüpft ist.

## <a name="related-topics"></a>Verwandte Themen

* [Übersicht über Microsoft 365 Defender](microsoft-365-defender.md)
* [Microsoft 365 Defender aktivieren](m365d-enable.md)
* [Untersuchen von Entitäten auf Geräten mithilfe von Liveantworten](../defender-endpoint/live-response.md)
* [Automatisierte Untersuchung und Reaktion (AIR) in Office 365](../office-365-security/office-365-air.md)
