---
title: Microsoft verwalteter Desktop Vorgänge und Überwachung
description: ''
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 00bdc95c191ce16be219cf0dc251f72eaf054e22
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867733"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft verwalteter Desktop Vorgänge und Überwachung

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Änderungsmanagement

Microsoft und Kunden werden Änderungsmanagement für den Dienst Microsoft verwalteter Desktop freigeben. Zuständigkeiten für ein Onlinedienst im Vergleich zu einem lokalen Server oder Client unterscheiden sich. 

### <a name="change-process-overview"></a>Übersicht über den Upgradeprozess ändern

Es folgt eine Zusammenfassung der wie der Prozess der Änderung von Microsoft und Kunden gemeinsam genutzt wird. 



<table>
<tr><th></th><th><p>Microsoft wird:</p></th><th><p>Kunden werden:</p></th></tr>
<tr><td>Vor einer Änderung</td><td><ul><li>Benachrichtigen Sie Kunden 5 Tage im Voraus für Änderungen, die Administrator-Aktion erfordern.</li><li>Notruf Änderungen Anwenden einer Risikominderung vor benachrichtigen.</li></ul></td><td><ul><li>Lesen Sie und verstehen Sie der e-Mail-Benachrichtigung.</li><li>Bestätigen Sie und genehmigen Sie, wenn erforderlich.</li></ul></td></tr><tr><td>Während einer Änderung</td><td><ul><li>Bereitstellen der Änderung für Windows 10 und Office, Version Sicherheitsupdates und nicht sicherheitsrelevante Updates, je nach Bedarf.</li><li>Überwachen der Telemetrie und Supporteskalation bei unerwarteten Problemen</li></ul></td><td><ul><li>Verwalten von internen Änderungsmanagementprozesses.</li><li>Erstellen Sie eine Supportanfrage, sofern erforderlich.</li></ul></td></tr><tr><td>Nach einer Änderung</td><td><ul><li>Sammeln von Feedback von Kunden zur Verbesserung der Einführung von zukünftigen Änderungen.</li><li>Überwachen der Telemetrie und Supporteskalation bei unerwarteten Problemen</li></ul></td><td><ul><li>Lesen Sie und verstehen Sie der e-Mail-Benachrichtigung.</li><li>Geben Sie allgemeine Kommentare und bestimmte Feedback in das Verwaltungstool Feedback.</li><li>Schulen von Benutzern an den Windows-Hub Feedback und die Schaltfläche Smiley in Office-apps mit app-spezifischen Feedback geben möchten.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Änderungstypen

Es gibt verschiedene Arten von Änderungen, die mit dem Dienst in regelmäßigen Abständen vorgenommen werden. Hängt von der Kommunikationskanal für diese Änderungen und die Aktionen, denen Kunden für zuständig sind.

Die folgenden Arten von Änderungen können erwartet werden:

Änderungstyp | Benachrichtigung | Kunden-Aktion
--- | --- | ---
Feature-Updates und neuen Dienstkomponenten | E-Mail | -Ändern Benutzern kommunizieren<br><br> -Act nach Bedarf von Microsoft<br><br> -Aktion muss innerhalb von 48 Stunden ausgeführt werden
Sicherheit aktualisiert werden, monatliche Updates und geplante Einstellungen | E-Mail, Security Bulletin oder Eintrag häufige Sicherheitsrisiken und Engagements (CVE) | -Monatliche Security Updates über unsere [Management Updatestrategie](updates.md)bereitgestellt werden.<br><br> -Einstellungen auf ein Risiko werden für die gesamte Organisation zum Schutz der Organisation bereitgestellt werden. (DIES WIRD NICHT UM EINE AKTION DES KUNDEN WERDEN ANGEZEIGT)
Qualität Updates, einschließlich Hotfixes, Service-Updates und nicht sicherheitsrelevante störenden Baselinerichtlinie | E-Mail | Werden zusätzliche bei Bedarf.
Emergency-Updates: Dienst, Konfiguration oder Software Updates erforderlich zum Abwehren von:<br><br> -Kritische Sicherheitsrisiko<br><br> -Potenzieller Datenverlust<br><br> -Zugriff auf Telemetriedaten für die Verwaltung von verwalteten Microsoft-Desktop-Geräte | Werden zusätzliche bei Bedarf.

## <a name="standard-operating-procedures"></a>Standardverfahren

Dieser Dienst wird implementiert und in Ihrer Umgebung, in dem Sie andere administrativen Aktivitäten abhalten, von Microsoft betrieben. Microsoft ist verantwortlich für Microsoft Managed Desktop-spezifische Installation, Konfiguration und Vorgang. 

Für lokale-Produkte übernimmt alle die Verantwortung für die Verwaltung von betrieblichen und Konfigurationsaktivitäten Ihrer Organisation.

Categories |    Aktionen
--- | ---
Dienstkonten |  Microsoft wird:<br><br> -Implementieren, sicher speichern und die Anmeldeinformationen verwalten<br><br> -Kommunikation vor unbefugten Zugriffen oder Verwendung von diese Anmeldeinformationen an Ihr Team Sicherheitsoperationen<br><br><br><br>Kunden werden:<br><br> -Öffnen einer Supportanfrage Informationszwecken mit Microsoft verwalteten Desktops Vorgänge bei der Planung einer Änderung, die die Konten auswirken können<br><br> -Nicht die Microsoft verwaltete Desktops-Dienstkonten weisen Sie Richtlinie, mehrstufige Authentifizierung, bedingten Zugriff oder Bereitstellung der Anwendung zu<br><br> -Nicht das Kennwort zurückgesetzt oder verwenden Sie die Anmeldeinformationen<br><br> -Öffnen Sie eine Sev C Supportanfrage an Microsoft verwalteter Desktop Vorgänge, wenn verdächtiger Aktivitäten Intune oder Azure Überwachungsprotokolle im Zusammenhang mit dieser Dienstkonten festgestellt wird
Device-Gruppen | Microsoft wird:<br><br> -Implementieren und Verwalten der Mitgliedschaft der Geräte innerhalb von Microsoft verwalteten Desktops Gruppen<br><br> – Verwendung von Microsoft verwalteten Desktops Gruppen zum Verwalten der Zuordnung und Freigabe von Konfigurations- und Updates für Geräte<br><br><br><br>Kunden werden:<br><br> -Öffnen einer Supportanfrage Informationszwecken mit Microsoft verwalteten Desktops Vorgänge bei der Planung einer Änderung, die die Gruppen auswirken können<br><br> -Ändern Sie die Mitgliedschaft einer beliebigen Gruppe verwalteter Microsoft-Desktop nicht<br><br> – Nur verwenden Sie die Gruppen, um im Unternehmen Zertifikate für Dienste wie VPN, Windows Hello für Business oder e-Mail-Verschlüsselung oder corporate Wi-Fi-Profilkonfiguration zuzuweisen<br><br> -Co-Management wo vorhanden ist, alle Microsoft verwalteter Desktop Gruppen explizit ausschließen, bei der Bereitstellung von Configuration Manager-client
Policies |  Microsoft wird:<br><br> -Implementieren und Verwalten der Microsoft verwalteter Desktop-Richtlinien, die den Konfigurationsstatus Geräte im Dienst steuern<br><br> -Bereitstellung von Updates zu Richtlinie oder inkrementell Gerätegruppen mit Windows<br><br> -Für nicht - Microsoft verwalteter Desktop Gruppen explizit ausschließen<br><br><br><br>Kunden werden:<br><br> -Öffnen Sie ein Informationszwecken Support-Ticket mit Microsoft verwalteten Desktops Vorgänge bei der Planung einer Änderung, die den Status der gewünschten Konfiguration der Geräte auswirken können<br><br> -Nicht bearbeiten oder Geräte oder Benutzer nicht vom Microsoft verwalteter Desktop-Dienst verwaltet Microsoft verwalteter Desktop Richtlinien zuweisen
Windows Defender Advanced Threat Protection | Microsoft wird:<br><br> -Überwachung und die Überprüfung der Geräte innerhalb des Bereichs des Diensts Microsoft verwalteten Desktops<br><br><br><br>Kunden werden:<br><br> -Öffnen Sie ein Informationszwecken Support-Ticket mit Microsoft verwalteten Desktops Vorgänge bei der Planung einer Änderung, die die überwachen oder genauer Funktionen von Microsoft Managed Desktop Security Operations Center auswirken können
Microsoft Store für Unternehmen |  Microsoft wird:<br><br> -Konfigurieren und Verwalten des Windows Autopilot Profils für den Dienst Microsoft verwalteten Desktops<br><br><br><br>Kunden werden:<br><br> -Öffnen Sie ein Informationszwecken Support-Ticket mit Microsoft verwalteten Desktops Vorgänge bei der Planung einer Änderung, dass Open möglicherweise den Zugriff auf den Informationsspeicher beeinträchtigen oder ändern Sie das Profil Microsoft verwalteten Desktops Windows Autopilot<br><br> -Ändern Sie die Konfiguration des Profils Microsoft verwalteten Desktops Windows Autopilot nicht oder zugeordneten Geräte hinzufügen/entfernen
Zertifikate |  Kunden werden:<br><br> -Öffnen Sie ein Informationszwecken Support-Ticket mit Microsoft verwalteten Desktops Vorgänge 60 Tage vor alle Zertifikat abläuft<br><br> -Alle Zertifikate, die erforderlich sind, so konfigurieren Sie aktualisieren: Profile, VPN und Wi-Fi-Profile,-Zertifikats



## <a name="device-wipe-with-factory-reset"></a>Löschen des Geräts mit Herstellerstandard

Verwaltete Desktops Betriebsteams ist möglich, eine Factory zurücksetzen auf Microsoft verwalteter Desktop verwalteten Geräten, die einem neuen Image versehen werden müssen. Dies ist hilfreich, wenn Sie ein Gerät an einem anderen Mitarbeiter erteilen müssen, oder wenn ein Mitarbeiter das Unternehmen verlässt. 

Es gibt einige Anforderungen:

- Der Kunde mandantenadministrator muss eine Anforderung einreichen.
- Wir brauchen den Computernamen für das Gerät
- Benutzerkonto muss in Azure AD, bevor wir das Zurücksetzen gemacht werden

Verwaltete Desktops Betriebsteams wird:

- Der Name des Aufnahmegeräts in Intune nachschlagen
- Senden Sie, dass die Factory Befehl auf das Gerät zurückzusetzen.

>[!NOTE]
>Entfernen Sie das Benutzerkonto nicht aus dem Azure Active Directory, bevor Sie auf den Herstellerstandard. Wenn der Benutzer in Azure Active Directory nicht ist, kann nicht Intune senden, dass die Factory Befehl auf dem Gerät zurückzusetzen. 

Das Gerät wird in OOBE gestartet, und alle vorinstallierten Anwendungen und Einstellungen werden erneut angewendet werden. Dem Benutzer das Gerät muss Anfangssatz Informationen erneut bereitstellen. 

Wenn das Gerät zurückgesetzt wurde, können Sie in Ihrer Organisation an einer anderen Person übergeben werden. Keines der vorherigen Benutzers Daten oder Enterprise-Daten werden auf dem Gerät. Der nächste Benutzer wird demselben Prozess durchlaufen, die die vorherige Person mit einer neuen Microsoft verwalteter Desktop Gerät haben.

BitLocker ist eine wichtige Komponente der datensicherheit in diesem Prozess. BitLocker-Verschlüsselung bei Microsoft verwalteter Desktop Geräte bleibt Daten auf dem Laufwerk sichere auch nach Herstellerstandard zurücksetzen auf das Gerät angewendet wurde. Alle Daten, die auf dem Laufwerk wurde verfügbar mit dem nächsten Benutzer des Geräts nicht. Weitere Informationen finden Sie unter [Übersicht über die BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).

Weitere Informationen finden Sie unter [Factory Zurücksetzen eines Geräts](https://docs.microsoft.com/intune/devices-wipe#factory-reset-a-device). 
