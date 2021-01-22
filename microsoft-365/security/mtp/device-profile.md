---
title: Geräteprofil im Microsoft 365-Sicherheitsportal
description: Zeigen Sie die Risiko- und Risikostufen für ein Gerät in Ihrer Organisation an. Analysieren Sie vergangene und aktuelle Bedrohungen, und schützen Sie das Gerät mit den neuesten Updates.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Microsoft Threat Protection, MTP, Security Center, Microsoft Defender ATP, Office 365 ATP, Azure ATP, Geräteseite, Geräteprofil, Computerseite, Computerprofil
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 40897185ab885ee2b6880ecd5f25d95fbe3d771e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929574"
---
# <a name="device-profile-page"></a>Seite "Geräteprofil"

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Das Microsoft 365-Sicherheitsportal stellt Ihnen Geräteprofilseiten zur Verfügung, sodass Sie den Zustand und Status von Geräten in Ihrem Netzwerk schnell bewerten können.

> [!IMPORTANT]
> Je nachdem, ob das Gerät in Microsoft Defender für Endpoint, Microsoft Defender for Identity oder beides registriert ist, kann die Seite mit dem Geräteprofil etwas anders angezeigt werden.

Wenn das Gerät in Microsoft Defender for Endpoint registriert ist, können Sie auch die Geräteprofilseite verwenden, um einige allgemeine Sicherheitsaufgaben auszuführen.

## <a name="navigating-the-device-profile-page"></a>Navigieren auf der Geräteprofilseite

Die Profilseite ist in mehrere breite Abschnitte unterteilt.

![Abbildung der Geräteprofilseite mit (1) Registerkartenbereich (2) Randleiste und (3) Rot hervorgehobenen Aktionen](../../media/mtp-device-profile/hybrid-device-overall.png)

In der Randleiste (1) sind grundlegende Details zum Gerät aufgeführt.

Der Hauptinhaltsbereich (2) enthält Registerkarten, die Sie umschalten können, um verschiedene Arten von Informationen über das Gerät anzuzeigen.

Wenn das Gerät in Microsoft Defender for Endpoint registriert ist, wird auch eine Liste der Antwortaktionen (3) angezeigt. Mit Reaktionsaktionen können Sie allgemeine sicherheitsbezogene Aufgaben ausführen.

## <a name="sidebar"></a>Randleiste

Neben dem Hauptinhaltsbereich der Geräteprofilseite befindet sich die Seitenleiste.

![Abbildung der Registerkarte "Sidebar" für das Geräteprofil](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

Die Randleiste listet den vollständigen Namen und die Belichtungsstufe des Geräts auf. Es enthält auch einige wichtige grundlegende Informationen in kleinen Unterabschnitten, die geöffnet oder geschlossen umschalten können, z. B.:

* **Tags** – Beliebige Microsoft Defender für Endpoint, Microsoft Defender for Identity oder benutzerdefinierte Tags, die dem Gerät zugeordnet sind. Tags aus Microsoft Defender for Identity können nicht bearbeitet werden.
* **Sicherheitsinformationen** – Öffnen von Vorfällen und aktiven Warnungen. Geräte, die in Microsoft Defender for Endpoint registriert sind, zeigen auch die Belichtungsstufe und die Risikostufe an.

> [!TIP]
> Die Gefährdungsstufe bezieht sich darauf, wie weit das Gerät sicherheitsempfehlungen entspricht, während die Risikostufe basierend auf einer Reihe von Faktoren berechnet wird, einschließlich der Typen und des Schweregrads aktiver Warnungen.

* **Gerätedetails** – Domäne, Betriebssystem, Zeitstempel für das erste Anzeigen des Geräts, IP-Adressen, Ressourcen. Geräte, die in Microsoft Defender for Endpoint registriert sind, zeigen auch den Integritätsstatus an. Geräte, die in Microsoft Defender for Identity registriert sind, zeigen den Namen des Sam und einen Zeitstempel an, als das Gerät zum ersten Mal erstellt wurde.
* **Netzwerkaktivität** – Zeitstempel zum ersten und letzten Mal, als das Gerät im Netzwerk gesehen wurde.
* **Verzeichnisdaten** ( nur für Geräte, die *in Microsoft Defender for Identity* registriert sind) – [UAC-Flags,](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names)und Gruppenmitgliedschaften.

## <a name="response-actions"></a>Antwortaktionen

Reaktionsaktionen bieten eine schnelle Möglichkeit, sich vor Bedrohungen zu schützen und sie zu analysieren.

![Abbildung der Aktionsleiste für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [Antwortaktionen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) sind nur verfügbar, wenn das Gerät in Microsoft Defender for Endpoint registriert ist.
> * Geräte, die in Microsoft Defender for Endpoint registriert sind, zeigen je nach Betriebssystem und Versionsnummer des Geräts möglicherweise eine unterschiedliche Anzahl von Antwortaktionen an.

Auf der Seite "Geräteprofil" sind folgende Aktionen verfügbar:

* **Tags verwalten** – Aktualisiert benutzerdefinierte Tags, die Sie auf dieses Gerät angewendet haben.
* **Gerät isolieren** – Isoliert das Gerät vom Netzwerk Ihrer Organisation, während es mit Microsoft Defender for Endpoint verbunden bleibt. Sie können festlegen, dass Outlook, Teams und Skype for Business ausgeführt werden können, während das Gerät isoliert ist, um Kommunikationszwecken zu ermöglichen.
* **Aktionscenter** – Anzeigen des Status der übermittelten Aktionen. Nur verfügbar, wenn bereits eine andere Aktion ausgewählt wurde.
* **Einschränken der App-Ausführung:** Verhindert die Ausführung von Anwendungen, die nicht von Microsoft signiert sind.
* **Ausführen eines Antivirenscans** – Updates Windows Defender Antivirusdefinitionen und führen sofort einen Antivirenscan aus. Wählen Sie zwischen Schnellscan oder vollständiger Überprüfung.
* **Untersuchungspaket sammeln** – Sammelt Informationen über das Gerät. Wenn die Untersuchung abgeschlossen ist, können Sie sie herunterladen.
* **Initiieren einer Liveantwortsitzung** – Lädt eine Remoteshell auf dem Gerät für [eingehende Sicherheitsuntersuchungen.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* **Initiieren einer automatisierten** Untersuchung [– Bedrohungen werden automatisch](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)untersucht und behoben. Sie können zwar automatisierte Untersuchungen manuell von dieser Seite aus [auslösen,](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) bestimmte Warnungsrichtlinien lösen jedoch selbst automatische Untersuchungen aus.
* **Info-Center:** Zeigt Informationen zu allen Derzeit ausgeführten Antwortaktionen an.

## <a name="tabs-section"></a>Tabs section

Auf den Registerkarten des Geräteprofils können Sie eine Übersicht über Sicherheitsdetails zum Gerät und Tabellen mit einer Liste von Warnungen anzeigen.

Geräte, die in Microsoft Defender for Endpoint registriert sind, zeigen auch Registerkarten an, die eine Zeitachse, eine Liste von Sicherheitsempfehlungen, ein Softwareinventar, eine Liste der ermittelten Sicherheitsrisiken und fehlende KBs (Sicherheitsupdates) enthalten.

### <a name="overview-tab"></a>Registerkarte "Übersicht"

Die Standardregisterkarte ist **Übersicht**. Es bietet einen schnellen Überblick über die wichtigsten Sicherheitsrisiken des Geräts.

![Abbildung der Registerkarte "Übersicht" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

Hier erhalten Sie einen schnellen Überblick über die aktiven Warnungen des Geräts und alle aktuell angemeldeten Benutzer.

Wenn das Gerät in Microsoft Defender for Endpoint registriert ist, werden auch die Risikostufe des Geräts und alle verfügbaren Daten in Sicherheitsbewertungen angezeigt. In den Sicherheitsbewertungen wird die Gefährdungsstufe des Geräts beschrieben, Sicherheitsempfehlungen gegeben, betroffene Software und ermittelte Sicherheitsrisiken aufgeführt.

### <a name="alerts-tab"></a>Registerkarte "Warnungen"

Die **Registerkarte** "Warnungen" enthält eine Liste der Warnungen, die auf dem Gerät ausgelöst wurden, sowohl von Microsoft Defender for Identity als auch von Microsoft Defender für Endpunkt.

![Abbildung der Registerkarte "Warnungen" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

Sie können die Anzahl der angezeigten Elemente sowie die Spalten anpassen, die für jedes Element angezeigt werden. Standardmäßig werden 30 Elemente pro Seite aufgeführt.

Die Spalten auf dieser Registerkarte enthalten Informationen zum Schweregrad der Bedrohung, die die Warnung ausgelöst hat, sowie Status, Untersuchungsstatus und wem die Warnung zugewiesen wurde.

Die *Spalte "Betroffene Entitäten"* bezieht sich auf das Gerät (Entität), dessen Profil Sie gerade anzeigen, sowie alle anderen Geräte in Ihrem Netzwerk, die betroffen sind.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, das noch mehr Informationen zur ausgewählten Warnung enthält.

Diese Liste kann nach Schweregrad, Status oder dem Benutzer gefiltert werden, dem die Warnung zugewiesen wurde.

### <a name="timeline-tab"></a>Registerkarte "Zeitachse"

Die **Registerkarte "Zeitachse"** enthält ein interaktives, chronologisches Diagramm aller ereignisse, die auf dem Gerät ausgelöst wurden. Durch Verschieben des hervorgehobenen Bereichs des Diagramms nach links oder rechts können Sie Ereignisse über verschiedene Zeiträume anzeigen. Sie können auch einen benutzerdefinierten Datumsbereich aus dem Dropdownmenü zwischen dem interaktiven Diagramm und der Ereignisliste auswählen.

Unterhalb des Diagramms befindet sich eine Liste der Ereignisse für den ausgewählten Datumsbereich.

![Abbildung der Registerkarte "Zeitachse" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

Die Anzahl der angezeigten Elemente und die Spalten in der Liste können angepasst werden. Die Standardspalten enthalten die Ereigniszeit, den aktiven Benutzer, den Aktionstyp, Entitäten (Prozesse) und zusätzliche Informationen zum Ereignis.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, in dem ein Diagramm mit Ereignisentitäten angezeigt wird, in dem die übergeordneten und untergeordneten Prozesse des Ereignisses angezeigt werden.

Die Liste kann nach dem jeweiligen Ereignistyp gefiltert werden. z. B. Registrierungsereignisse oder Smart screen-Ereignisse.

Die Liste kann auch zum Download in eine CSV-Datei exportiert werden. Die Datei ist zwar nicht durch die Anzahl der Ereignisse beschränkt, der maximale Zeitraum, den Sie exportieren können, beträgt jedoch sieben Tage.

### <a name="security-recommendations-tab"></a>Registerkarte "Sicherheitsempfehlungen"

Auf **der Registerkarte "Sicherheitsempfehlungen"** sind Aktionen aufgeführt, die Sie zum Schutz des Geräts ergreifen können. Wenn Sie ein Element in dieser Liste auswählen, wird ein Flyout geöffnet, in dem Sie Anweisungen zum Anwenden der Empfehlung erhalten.

![Abbildung der Registerkarte "Sicherheitsempfehlungen" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

Wie bei den vorherigen Registerkarten kann die Anzahl der pro Seite angezeigten Elemente sowie die sichtbaren Spalten angepasst werden.

Die Standardansicht enthält Spalten, in der die sicherheitsrelevanten Schwachstellen, die zugeordnete Bedrohung, die zugehörige Komponente oder Software, die von der Bedrohung betroffen ist, und vieles mehr beschrieben werden. Elemente können nach dem Status der Empfehlung gefiltert werden.

### <a name="software-inventory"></a>Softwarebestand

Auf **der Registerkarte "Softwareinventar"** wird die auf dem Gerät installierte Software aufgeführt.

![Abbildung der Registerkarte "Softwareinventar" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

In der Standardansicht werden der Softwareanbieter, die installierte Versionsnummer, die Anzahl bekannter Softwareschwächen, Bedrohungseinblicke, Produktcode und Tags angezeigt. Die Anzahl der angezeigten Elemente und die angezeigten Spalten können angepasst werden.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, das weitere Details zur ausgewählten Software sowie den Pfad und Zeitstempel für das letzte Mal enthält, als die Software gefunden wurde.

Diese Liste kann nach Produktcode gefiltert werden.

### <a name="discovered-vulnerabilities-tab"></a>Registerkarte "Ermittelte Sicherheitsrisiken"

Auf **der Registerkarte "Ermittelte Sicherheitsrisiken"** werden alle allgemeinen Sicherheitsrisiken und Exploits (Common Vulnerabilities and Exploits, CVEs) aufgeführt, die sich auf das Gerät auswirken können.

![Abbildung der Registerkarte "Ermittelte Sicherheitsrisiken" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

In der Standardansicht werden der Schweregrad des CVE, das allgemeine Sicherheitsrisikoergebnis (Common Vulnerability Score, CVS), die Software im Zusammenhang mit dem CVE, der Veröffentlichung des CVE, der letzte Aktualisierung des CVE und bedrohungen im Zusammenhang mit cvE aufgeführt.

Wie bei den vorherigen Registerkarten kann die Anzahl der angezeigten Elemente und die sichtbaren Spalten angepasst werden.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, das den CVE beschreibt.

### <a name="missing-kbs"></a>Fehlende KBs

Auf **der Registerkarte "Fehlende KBs"** werden alle Microsoft Updates aufgeführt, die noch auf das Gerät angewendet werden müssen. Bei den "KBs" handelt es sich um [Knowledge Base-Artikel,](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) in denen diese Updates beschrieben werden. Beispiel: [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![Abbildung der Registerkarte "Fehlende KBs" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

In der Standardansicht wird das Bulletin mit updates, Betriebssystemversion, betroffenen Produkten, adressierte CVEs, der KB-Nummer und Tags aufgeführt.

Die Anzahl der pro Seite angezeigten Elemente und die angezeigten Spalten können angepasst werden.

Wenn Sie ein Element auswählen, wird ein Flyout geöffnet, das mit dem Update verknüpft ist.

## <a name="related-topics"></a>Verwandte Themen

* [Übersicht über Microsoft 365 Defender](microsoft-threat-protection.md)
* [Aktivieren von Microsoft 365 Defender](mtp-enable.md)
* [Untersuchen von Entitäten auf Geräten mithilfe von Liveantworten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Automatisierte Untersuchung und Reaktion (AIR) in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
