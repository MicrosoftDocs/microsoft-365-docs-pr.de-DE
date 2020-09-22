---
title: Geräteprofil im Microsoft 365-Sicherheitsportal
description: Anzeigen von Risiko-und Expositions Ebenen für ein Gerät in Ihrer Organisation. Analysieren Sie vergangene und gegenwärtige Bedrohungen, und schützen Sie das Gerät mit den neuesten Updates.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Microsoft Threat Protection, MTP, Sicherheitscenter, Microsoft Defender ATP, Office 365 ATP, Azure ATP, Geräteseite, Geräteprofil, Computer Seite, Computer Profil
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: f6b79d3252084b298f94e01b18ebe3505f83b480
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196857"
---
# <a name="device-profile-page"></a>Geräteprofil Seite

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Das Microsoft 365-Sicherheitsportal bietet Ihnen Geräteprofil Seiten, sodass Sie die Integrität und den Status von Geräten in Ihrem Netzwerk schnell bewerten können.

> [!IMPORTANT]
> Die Geräteprofil Seite erscheint möglicherweise geringfügig anders, je nachdem, ob das Gerät in Microsoft Defender ATP, Azure ATP oder in beiden registriert ist.

Wenn das Gerät in Microsoft Defender ATP registriert ist, können Sie auch die Geräteprofil Seite verwenden, um einige allgemeine Sicherheitsaufgaben auszuführen.

## <a name="navigating-the-device-profile-page"></a>Navigieren auf der Geräteprofil Seite

Die Profilseite ist in mehrere allgemeine Abschnitte unterteilt.

![Bild der Geräteprofil Seite mit (1) Registerkartenbereich (2) Sidebar und (3) Aktionen in rot hervorgehoben](../../media/mtp-device-profile/hybrid-device-overall.png)

In der Sidebar (1) werden grundlegende Details zum Gerät aufgelistet.

Der Hauptinhaltsbereich (2) enthält Registerkarten, die Sie umschalten können, um verschiedene Arten von Informationen zum Gerät anzuzeigen.

Wenn das Gerät in Microsoft Defender ATP registriert ist, wird auch eine Liste der Antwort Aktionen angezeigt (3). Mit Antwort Aktionen können Sie häufige sicherheitsbezogene Aufgaben ausführen.

## <a name="sidebar"></a>Randleiste

Neben dem Hauptinhaltsbereich der Geräteprofil Seite befindet sich die Sidebar.

![Registerkarte "Bild der Sidebar" für Geräteprofil](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

In der Sidebar werden der vollständige Name und die Expositions Ebene des Geräts aufgeführt. Sie enthält auch einige wichtige grundlegende Informationen in kleinen Unterabschnitten, die geöffnet oder geschlossen umgeschaltet werden können, beispielsweise:

* **Tags** – alle Microsoft Defender ATP-, Azure ATP-oder Custom-Tags, die dem Gerät zugeordnet sind. Tags aus Azure ATP können nicht bearbeitet werden.
* **Sicherheitsinformationen** – offene Vorfälle und aktive Warnungen. Geräte, die in Microsoft Defender ATP registriert sind, zeigen außerdem die Expositions Ebene und das Risikoniveau an.

> [!TIP]
> Die Expositions Ebene bezieht sich darauf, wie viel das Gerät Sicherheitsempfehlungen einhält, während das Risikoniveau basierend auf einer Reihe von Faktoren berechnet wird, einschließlich der Typen und des Schweregrads aktiver Warnungen.

* **Gerätedetails** – Domäne, Betriebssystem, Zeitstempel für das erste erkennen des Geräts, IP-Adressen, Ressourcen. Für Geräte, die in Microsoft Defender ATP registriert sind, wird auch der Integritätsstatus angezeigt. In Azure ATP eingeschriebene Geräte zeigen Sam-Namen und einen Zeitstempel für den Zeitpunkt an, zu dem das Gerät erstmalig erstellt wurde.
* **Netzwerkaktivität** – Zeitstempel zum ersten Mal und zum letzten Mal, als das Gerät im Netzwerk angezeigt wurde.
* **Verzeichnisdaten** (*nur für Geräte, die in Azure ATP registriert*sind) – [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) -Flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names)und Gruppenmitgliedschaften.

## <a name="response-actions"></a>Antwort Aktionen

Reaktions Aktionen bieten eine schnelle Möglichkeit, Bedrohungen zu schützen und zu analysieren.

![Bild der Aktionsleiste für Geräteprofil](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [Antwort Aktionen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) sind nur verfügbar, wenn das Gerät in Microsoft Defender ATP registriert ist.
> * Geräte, die in Microsoft Defender ATP registriert sind, können basierend auf dem Betriebssystem und der Versionsnummer des Geräts unterschiedliche Nummern von Antwort Aktionen anzeigen.

Die auf der Geräteprofil Seite verfügbaren Aktionen umfassen Folgendes:

* **Tags verwalten** – aktualisiert benutzerdefinierte Tags, die Sie auf dieses Gerät angewendet haben.
* **Gerät isolieren** – isoliert das Gerät aus dem Netzwerk Ihrer Organisation, während es mit dem Advanced Threat Protection von Microsoft Defender verbunden bleibt. Sie können festlegen, dass Outlook, Teams und Skype for Business während der Isolierung des Geräts zu Kommunikationszwecken ausgeführt werden.
* **Action Center** – zeigt den Status der übermittelten Aktionen an. Nur verfügbar, wenn bereits eine andere Aktion ausgewählt wurde.
* **Einschränken der APP-Ausführung** – verhindert, dass von Microsoft nicht signierte Anwendungen ausgeführt werden.
* **Antivirus-Scan ausführen** – aktualisiert die Antivirus-Definitionen von Windows Defender und führt sofort eine Antivirus-Überprüfung aus. Wählen Sie zwischen Schnellscan oder vollständiger Scan aus.
* **Ermittlungs Paket sammeln** – sammelt Informationen zum Gerät. Wenn die Untersuchung abgeschlossen ist, können Sie Sie herunterladen.
* **Live-Antwort-Sitzung initiieren** – lädt eine Remote-Shell auf dem Gerät für [eingehende Sicherheitsuntersuchungen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).
* **Initiieren der automatischen Untersuchung** – Automatisches [untersuchen und Beheben von Bedrohungen](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air). Sie können zwar manuell automatisierte Untersuchungen auslösen, die von dieser Seite ausgeführt werden, aber [bestimmte Warnungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) lösen selbst automatische Untersuchungen aus.
* **Action Center** – zeigt Informationen zu allen derzeit ausgeführten Reaktions Aktionen an.

## <a name="tabs-section"></a>Tabs section

Auf den Registerkarten für Geräteprofile können Sie eine Übersicht über Sicherheitsdetails zu dem Gerät und Tabellen mit einer Liste von Warnungen wechseln.

Für Geräte, die in Microsoft Defender ATP registriert sind, werden auch Registerkarten mit einer Zeitachse, eine Liste mit Sicherheitsempfehlungen, eine Softwareinventur, eine Liste der ermittelten Sicherheitsanfälligkeiten und fehlende KBS (Sicherheitsupdates) angezeigt.

### <a name="overview-tab"></a>Registerkarte "Übersicht"

Die Standardregisterkarte ist **Overview**. Es bietet einen schnellen Überblick über die wichtigsten Sicherheitsfakten zum Gerät.

![Registerkarte ' Bild der Übersicht ' für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

Hier erhalten Sie einen kurzen Überblick über die aktiven Warnungen des Geräts sowie alle derzeit angemeldeten Benutzer.

Wenn das Gerät in Microsoft Defender ATP registriert ist, sehen Sie auch die Risikostufe des Geräts sowie alle verfügbaren Daten zu Sicherheitsbewertungen. In den Sicherheitsbewertungen wird die Expositions Stufe des Geräts beschrieben, Sicherheitsempfehlungen bereitgestellt und die betroffene Software sowie entdeckte Sicherheitsrisiken aufgelistet.

### <a name="alerts-tab"></a>Registerkarte "Warnungen"

Die Registerkarte **Benachrichtigungen** enthält eine Liste der Warnungen, die auf dem Gerät ausgelöst wurden, sowohl von Azure ATP als auch von Microsoft Defender ATP.

![Registerkarte ' Bild der Benachrichtigungen ' für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

Sie können die Anzahl der angezeigten Elemente sowie die für jedes Element angezeigten Spalten anpassen. Das Standardverhalten besteht darin, 30 Elemente pro Seite aufzulisten.

Die Spalten auf dieser Registerkarte enthalten Informationen über den Schweregrad der Bedrohung, die die Warnung ausgelöst hat, sowie den Status, den Untersuchungs Zustand und die Person, der die Warnung zugewiesen wurde.

Die Spalte betroffene *Entitäten* bezieht sich auf das Gerät (Entität), dessen Profil Sie derzeit anzeigen, sowie alle anderen Geräte in Ihrem Netzwerk, die betroffen sind.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, in dem noch weitere Informationen zur ausgewählten Warnung angezeigt werden.

Diese Liste kann nach Schweregrad, Status oder der Person, der die Benachrichtigung zugewiesen wurde, gefiltert werden.

### <a name="timeline-tab"></a>Registerkarte "Timeline"

Die Registerkarte **Zeitachse** enthält ein interaktives, Chronologisches Diagramm aller Ereignisse, die auf dem Gerät ausgelöst wurden. Wenn Sie den markierten Bereich des Diagramms nach links oder rechts verschieben, können Sie Ereignisse über verschiedene Zeiträume hinweg anzeigen. Sie können auch einen benutzerdefinierten Datumsbereich aus dem Dropdownmenü zwischen dem interaktiven Diagramm und der Liste der Ereignisse auswählen.

Unter dem Diagramm finden Sie eine Liste der Ereignisse für den ausgewählten Datumsbereich.

![Registerkarte ' Bild der Zeitachse ' für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

Die Anzahl der angezeigten Elemente und die Spalten in der Liste können angepasst werden. In den Standardspalten werden die Ereigniszeit, der aktive Benutzer, der Aktionstyp, Entitäten (Prozesse) und zusätzliche Informationen zum Ereignis aufgelistet.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, in dem ein Ereignis Entitäten Diagramm mit den übergeordneten und untergeordneten Prozessen angezeigt wird, die an dem Ereignis beteiligt sind.

Die Liste kann nach der spezifischen Art des Ereignisses gefiltert werden; beispielsweise Registrierungs Ereignisse oder Smart Screen-Ereignisse.

Die Liste kann auch als Download in eine CSV-Datei exportiert werden. Obwohl die Datei nicht durch die Anzahl der Ereignisse limitiert ist, beträgt der maximale Zeitbereich, den Sie exportieren können, sieben Tage.

### <a name="security-recommendations-tab"></a>Registerkarte "Sicherheitsempfehlungen"

Auf der Registerkarte **Sicherheitsempfehlungen** werden Aktionen aufgeführt, die Sie zum Schutz des Geräts ausführen können. Wenn Sie ein Element in dieser Liste auswählen, wird ein Flyout geöffnet, in dem Sie Anweisungen dazu erhalten, wie Sie die Empfehlung anwenden können.

![Registerkarte Bild der Sicherheitsempfehlungen für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

Wie bei den vorherigen Registerkarten kann auch die Anzahl der Elemente, die pro Seite angezeigt werden, sowie die sichtbaren Spalten angepasst werden.

Die Standardansicht enthält Spalten, in denen die Sicherheitsschwächen, die zugehörige Bedrohung, die zugehörige Komponente oder Software, die von der Bedrohung betroffen ist, detailliert beschrieben werden und vieles mehr. Elemente können nach dem Status der Empfehlung gefiltert werden.

### <a name="software-inventory"></a>Softwarebestand

Auf der Registerkarte **Softwareinventur** sind auf dem Gerät installierte Software aufgeführt.

![Abbildung der Registerkarte "Softwareinventur" für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

In der Standardansicht werden der Softwarehersteller, die installierte Versionsnummer, die Anzahl bekannter Software Schwächen, Einblicke in Bedrohungen, Produktcode und Tags angezeigt. Die Anzahl der angezeigten Elemente und die angezeigten Spalten können angepasst werden.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout mit weiteren Details zur ausgewählten Software sowie der Pfad und der Zeitstempel zum letzten Mal geöffnet, an dem die Software gefunden wurde.

Diese Liste kann nach Produktcode gefiltert werden.

### <a name="discovered-vulnerabilities-tab"></a>Registerkarte "erkannte Sicherheitsanfälligkeiten"

Auf der Registerkarte **erkannte Sicherheitsanfälligkeiten** werden alle gängigen Sicherheitsanfälligkeiten und Exploits (CVEs) aufgelistet, die sich auf das Gerät auswirken können.

![Registerkarte "Abbild der entdeckten Sicherheitsanfälligkeiten" für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

In der Standardansicht werden der Schweregrad von CVE, das Common Vulnerability Score (CVS), die Software im Zusammenhang mit CVE, der Veröffentlichung von CVE, der Zeitpunkt der letzten Aktualisierung von CVE und mit dem CVE verbundene Bedrohungen aufgelistet.

Wie bei den vorherigen Registerkarten kann auch die Anzahl der angezeigten Elemente und der sichtbaren Spalten angepasst werden.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, in dem das CVE beschrieben wird.

### <a name="missing-kbs"></a>Fehlende KBS

Auf der Registerkarte " **fehlende KBS** " werden alle Microsoft-Updates aufgelistet, die noch nicht auf das Gerät angewendet wurden. Bei der fraglichen "KBS" handelt es sich um [Knowledge Base-Artikel](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) , in denen diese Updates beschrieben werden. Beispiel: [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![Abbildung fehlender KBS-Registerkarten für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

In der Standardansicht wird das Bulletin mit den Updates, der Betriebssystemversion, betroffenen Produkten, CVEs, der KB-Nummer und Tags aufgelistet.

Die Anzahl der Elemente, die pro Seite angezeigt werden, und die angezeigten Spalten können angepasst werden.

Durch die Auswahl eines Elements wird ein Flyout geöffnet, das auf das Update verweist.

## <a name="related-topics"></a>Verwandte Themen

* [Übersicht über Microsoft Threat Protection](microsoft-threat-protection.md)
* [Aktivieren von Microsoft Threat Protection](mtp-enable.md)
* [Untersuchen von Entitäten auf Geräten mithilfe von Live-Antwort](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Automatische Untersuchung und Reaktion (Air) in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
