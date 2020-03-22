---
title: Computer Profil im Microsoft 365-Sicherheitsportal
description: Anzeigen von Risiko-und Expositions Ebenen für ein Gerät in Ihrer Organisation. Analysieren Sie vergangene und gegenwärtige Bedrohungen, und schützen Sie den Computer mit den neuesten Updates.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Microsoft Threat Protection, MTP, Sicherheitscenter, Microsoft Defender ATP, Office 365 ATP, Azure ATP, Machine-Seite, Computerliste, Computer Profil
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
ms.openlocfilehash: 1dfb567c8e6b8573397d503ae27c0aceb447c916
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895463"
---
# <a name="machine-profile-page"></a>Seite „Computerprofil“

Das Microsoft 365-Sicherheitsportal stellt Ihnen Computer Profilseiten zur Verfügung, damit Sie die Integrität und den Status von Geräten in Ihrem Netzwerk bewerten können. Jede Computer Profilseite enthält eine Vielzahl von Informationen über das Gerät.

Sie können ausführliche Informationen über die ausgeführten Software, alle vergangenen und aktuellen Sicherheitsereignisse oder Warnungen sowie Links zu relevanten Software-Patches lesen.

Sie können auch das Computer Profil verwenden, um allgemeine sicherheitsbezogene Aufgaben auszuführen und schnell grundlegende Details zum Gerät zu überprüfen.

## <a name="navigating-the-machine-profile-page"></a>Navigieren auf der Seite "Computer Profil"

Die Computer Profilseite ist in drei Abschnitte unterteilt.

![Bild der Computer Profilseite mit (1) Registerkartenbereich (2) Sidebar und (3) Aktionen in rot hervorgehoben](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

Der Hauptinhaltsbereich (1) enthält sieben Registerkarten, die Sie umschalten können, um verschiedene Arten von Informationen zum Computer anzuzeigen.

In der Sidebar (2) sind grundlegende Details zum Computer aufgeführt.

Es gibt auch Antwort Aktionen, die in einer Kopfzeile (3) vor der Sidebar und den Hauptinhalts Abschnitten verfügbar sind. Sie können die Aktionen in dieser Kopfzeile verwenden, um allgemeine sicherheitsbezogene Aufgaben auszuführen.

## <a name="tabs-section"></a>Tabs section

Auf den Registerkarten des Computer Profils können Sie eine Übersicht über die Sicherheitsdetails des Computers und Tabellen mit einer Liste von Warnungen, eine Zeitachse, eine Liste mit Sicherheitsempfehlungen, eine Softwareinventur, eine Liste der entdeckten Sicherheitsanfälligkeiten und fehlende KBS (Sicherheitsupdates).

### <a name="overview-tab"></a>Registerkarte "Übersicht"

Die Standardregisterkarte ist **Overview**. Es bietet einen schnellen Überblick über die wichtigsten Sicherheitsfakten zum Gerät.

![Registerkarte ' Bild der Übersicht ' für das Computer Profil](../../media/mtp-machine-profile/overview.png)

Hier finden Sie ein Diagramm der Risikostufe des Geräts und der aktiven Warnungen, der aktuell angemeldeten Benutzer, einer kurzen Liste mit den meisten und seltensten Benutzern sowie Sicherheitsbewertungen, in denen die Expositions Stufe des Geräts, Sicherheitsempfehlungen, betroffene Software und entdeckte Sicherheitsrisiken.

### <a name="alerts-tab"></a>Registerkarte "Warnungen"

Die Registerkarte **Benachrichtigungen** enthält eine Liste der Warnungen, die auf dem Gerät gemeldet wurden.

![Registerkarte ' Bild der Benachrichtigungen ' für das Computer Profil](../../media/mtp-machine-profile/alerts.png)

Sie können die Anzahl der angezeigten Elemente sowie die für jedes Element angezeigten Spalten anpassen. Das Standardverhalten besteht darin, 30 Elemente pro Seite aufzulisten und 11 Spalten zur Anzeige umzuschalten.

Die Spalten auf dieser Registerkarte enthalten Informationen über den Schweregrad der Bedrohung, die die Warnung ausgelöst hat, sowie den Status, den Untersuchungs Zustand und wer, wenn jemand der Warnung zugewiesen wurde.

Die Spalte betroffene *Entitäten* bezieht sich auf den Computer (Entität), dessen Profil Sie derzeit anzeigen, sowie auf alle anderen Computer in Ihrem Netzwerk, die betroffen sind.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Link zur ausgewählten Warnung geöffnet.

Diese Liste kann nach Schweregrad, Status oder Empfänger gefiltert werden.

### <a name="timeline-tab"></a>Registerkarte "Timeline"

Die Registerkarte **Zeitachse** enthält ein interaktives, Chronologisches Diagramm der Ereignisse, die auf dem Gerät ausgelöst wurden. Wenn Sie den markierten Bereich des Diagramms verschieben, können Sie Ereignisse in verschiedenen Zeitbereichen anzeigen. Sie können auch einen benutzerdefinierten Datumsbereich eingeben.

Unter dem Diagramm finden Sie eine Liste der Ereignisse für den ausgewählten Datumsbereich.

![Registerkarte "Bild der Zeitachse" für das Computer Profil](../../media/mtp-machine-profile/timeline.png)

Die Anzahl der angezeigten Elemente und die Spalten in der Liste können angepasst werden. In den Standardspalten werden die Ereigniszeit, der aktive Benutzer, der Aktionstyp, Entitäten (Prozesse) und zusätzliche Informationen zum Ereignis aufgelistet.

Wenn Sie ein Element aus der Liste auswählen, wird ein Flyout geöffnet, in dem ein Ereignis Entitäten Diagramm mit den übergeordneten und untergeordneten Prozessen angezeigt wird, die das Ereignis ausgelöst haben.

Diese Liste kann nach der spezifischen Art von Ereignis gefiltert werden; beispielsweise Registrierungs Ereignisse oder Smart Screen-Ereignisse.

### <a name="security-recommendations-tab"></a>Registerkarte "Sicherheitsempfehlungen"

Auf der Registerkarte **Sicherheitsempfehlungen** werden Aktionen aufgeführt, die Sie zum Schutz des Geräts ausführen können. Wenn Sie ein Element in dieser Liste auswählen, wird ein Flyout geöffnet, in dem Sie Anweisungen dazu erhalten, wie Sie die Empfehlung anwenden können.

![Registerkarte "Image of Security Recommendations" für Machine profile](../../media/mtp-machine-profile/security-recs.png)

Wie bei den vorherigen Registerkarten kann auch die Anzahl der pro Seite angezeigten Elemente und der sichtbaren Spalten angepasst werden.

Die Standardansicht enthält Spalten, in denen die Sicherheitsschwächen, die zugehörige Bedrohung, die zugehörige Komponente oder Software, die von der Bedrohung betroffen ist, detailliert beschrieben werden und vieles mehr. Elemente können nach dem Status der Empfehlung gefiltert werden.

### <a name="software-inventory"></a>Softwarebestand

Auf der Registerkarte **Softwareinventur** sind auf dem Gerät installierte Software aufgeführt.

![Abbildung der Registerkarte "Softwareinventur" für das Computer Profil](../../media/mtp-machine-profile/software-inventory.png)

In der Standardansicht werden der Softwarehersteller, die installierte Versionsnummer, die Anzahl bekannter Software Schwächen, Einblicke in Bedrohungen, Produktcode und Tags angezeigt. Die Anzahl der angezeigten Elemente und die angezeigten Spalten können angepasst werden.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout mit weiteren Details zur ausgewählten Software sowie der Pfad und der Zeitstempel zum letzten Mal geöffnet, an dem die Software gefunden wurde.

Diese Liste kann nach Produktcode gefiltert werden.

### <a name="discovered-vulnerabilities-tab"></a>Registerkarte "erkannte Sicherheitsanfälligkeiten"

Auf der Registerkarte **erkannte Sicherheitsanfälligkeiten** werden alle gängigen Sicherheitsanfälligkeiten und Exploits (CVEs) aufgelistet, die sich auf das Gerät auswirken können.

![Registerkarte "Abbild der entdeckten Sicherheitsanfälligkeiten" für das Computer Profil](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

In der Standardansicht werden der Schweregrad von CVE, das Common Vulnerability Score (CVS), die Software im Zusammenhang mit CVE, der Veröffentlichung von CVE, der Zeitpunkt der letzten Aktualisierung von CVE und mit dem CVE verbundene Bedrohungen aufgelistet.

Wie bei den vorherigen Registerkarten kann auch die Anzahl der angezeigten Elemente und der sichtbaren Spalten angepasst werden.

Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, in dem das CVE beschrieben wird.

### <a name="missing-kbs"></a>Fehlende KBS

Auf der Registerkarte " **fehlende KBS** " werden alle Microsoft-Updates aufgelistet, die noch nicht auf den Computer angewendet wurden. Bei der fraglichen "KBS" handelt es sich um [Knowledge Base-Artikel](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) , in denen diese Updates beschrieben werden. Beispiel: [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![Abbildung fehlender KBS-Registerkarten für das Computer Profil](../../media/mtp-machine-profile/missing-kbs.PNG)

In der Standardansicht wird das Bulletin mit den Updates, der Betriebssystemversion, betroffenen Produkten, CVEs, der KB-Nummer und Tags aufgelistet.

Die Anzahl der Elemente, die pro Seite angezeigt werden, und die angezeigten Spalten können angepasst werden.

Durch die Auswahl eines Elements wird ein Flyout geöffnet, das auf das Update verweist.

## <a name="sidebar"></a>Randleiste

Neben dem Hauptinhaltsbereich der Computer Profilseite befindet sich die Sidebar.

![Bild der Sidebar-Registerkarte für das Computer Profil](../../media/mtp-machine-profile/sidebar.png)

Die Sidebar enthält einige wichtige grundlegende Informationen in kleinen Unterabschnitten, die geöffnet oder geschlossen umgeschaltet werden können:

* **Tags** – alle dem Gerät zugeordneten Tags
* **Sicherheitsinformationen** – offene Vorfälle, aktive Warnungen, Expositions Ebene und Risikostufe
* **Gerätedetails** – Domäne, Betriebssystem, Objektgruppe, Integritätsstatus, Daten Empfindlichkeit und IP-Adressen
* **Netzwerkaktivität** -Zeitstempel zum ersten Mal und zum letzten Mal, als das Gerät im Netzwerk angezeigt wurde

Dieser Abschnitt enthält auch den Namen und die Expositions Ebene des Geräts sowie ein Symbol, um anzugeben, ob es derzeit im Netzwerk aktiv ist.

## <a name="response-actions"></a>Antwort Aktionen

Reaktions Aktionen bieten eine schnelle Möglichkeit, Bedrohungen zu schützen und zu analysieren.

![Bild der Sidebar-Registerkarte für das Computer Profil](../../media/mtp-machine-profile/actions.PNG)

Folgende Reaktions Aktionen stehen Ihnen zur Verfügung:

* **Tags verwalten** – aktualisiert benutzerdefinierte Tags, die Sie auf dieses Gerät angewendet haben.
* **Isolieren** Sie den Computer – isolieren Sie den Computer aus dem Netzwerk Ihrer Organisation, während er mit dem Advanced Threat Protection von Microsoft Defender verbunden bleibt. Sie können festlegen, dass Outlook, Teams und Skype for Business während der Isolierung des Computers zu Kommunikationszwecken ausgeführt werden.
* **Einschränken der APP-Ausführung** – verhindert, dass von Microsoft nicht signierte Anwendungen ausgeführt werden
* **Antivirus-Scan ausführen** – aktualisiert die Antivirus-Definitionen von Windows Defender und führt sofort eine Antivirus-Überprüfung aus. Wählen Sie zwischen Schnellscan oder vollständiger Scan aus.
* **Ermittlungs Paket sammeln** – sammelt Informationen zum Computer. Wenn die Untersuchung abgeschlossen ist, können Sie Sie herunterladen.
* **Live-Antwort-Sitzung initiieren** – lädt eine Remote-Shell auf dem Computer für ausführliche [Sicherheitsuntersuchungen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).
* **Initiieren der automatischen Untersuchung** – Automatisches [untersuchen und Beheben von Bedrohungen](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air). Sie können zwar manuell automatisierte Untersuchungen auslösen, die von dieser Seite ausgeführt werden, aber [bestimmte Warnungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) lösen selbst automatische Untersuchungen aus.
* **Action Center** – zeigt den Status der übermittelten Aktionen an. Nur verfügbar, wenn bereits eine andere Aktion ausgewählt wurde.

## <a name="related-topics"></a>Verwandte Themen

* [Übersicht über Microsoft Threat Protection](microsoft-threat-protection.md)
* [Aktivieren von Microsoft Threat Protection](mtp-enable.md)
* [Untersuchen von Entitäten auf Computern mit Live-Antwort](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Automatische Untersuchung und Reaktion (Air) in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
