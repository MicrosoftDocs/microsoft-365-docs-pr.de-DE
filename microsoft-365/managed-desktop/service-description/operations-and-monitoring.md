---
title: Microsoft verwalteter Desktop Vorgänge und Überwachung
description: ''
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 12/18/2018
ms.openlocfilehash: 66945d44df150b5be9af9a9dfe52daa4d7468298
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867733"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft verwalteter Desktop Vorgänge und Überwachung

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Änderungsmanagement

In einem Dienst anbietet, das Gleichgewicht Zuständigkeitsbereich z. B. Hardwarewartung und Sicherheit für Updates verschiebt an den Dienstanbieter (Microsoft) anstelle der Kunde (Sie). Allerdings müssen Sie dennoch, Drittanbieter-sicherstellen und benutzerdefiniertes Software funktioniert wie erwartet, wenn Updates eingeführt werden weiterhin.

Für lokale-Produkte verantwortlich Ihrer Organisation für die Verwaltung von ändern.

### <a name="balance-of-responsibility"></a>Verteilen der Verantwortung

Responsibility | Microsoft verwalteter Desktop-Dienst | Microsoft-365-Clientsoftware | Lokale Clients und Server | 3. Partei und benutzerdefinierte software
----- | ----- | ----- | ----- | -----
Bereitstellen neue Funktionalität | Microsoft | Microsoft | Beide | Kunde
Testen neuer Features zum Sicherstellen der Qualität |  Microsoft | Microsoft | Beide | Kunde
Kommunikation zu neuen Features | Beide | Beide | Beide | Kunde
Integrieren von benutzerdefinierten Software | Beide | Beide | Kunde | Kunde
Anwenden von Sicherheitsupdates | Microsoft | Microsoft | Kunde | Kunde
Warten von Systemsoftware | Microsoft | Microsoft | Kunde | Kunde
Paket für die Bereitstellung | Microsoft | Microsoft | Kunde | Kunde


### <a name="change-process-overview"></a>Übersicht über den Upgradeprozess ändern

Es folgt eine Zusammenfassung der wie der Prozess der Änderung von Microsoft und Kunden gemeinsam genutzt wird. 



<table>
<tr><th></th><th><p>Die Rolle von Microsoft:</p></th><th><p>Rolle des Kunden:</p></th></tr>
<tr><td>Vor einer Änderung</td><td><ul><li>Festlegen der Erwartungen an Dienständerungen</li><li>Benachrichtigen Sie Kunden 5 Tage im Voraus für Änderungen, die Administrator-Aktion erfordern.</li><li>Notruf Änderungen Anwenden einer Risikominderung vor benachrichtigen.</li></ul></td><td><ul><li>Verstehen der zu erwartenden Änderungen und Kommunikation</li><li>Lesen Microsoft verwalteten Desktops Nachrichtencenter regelmäßig.</li><li>Überprüfen und Aktualisieren interner Change Management-Prozesse</li><li>Verstehen Sie und überprüfen Sie der Kompatibilität mit Microsoft verwalteter Desktop Anforderungen. </li><li>Bestätigen Sie und genehmigen Sie, wenn erforderlich.</li></ul></td></tr><tr><td>Während einer Änderung</td><td><ul><li>Freigeben und monatliche Sicherheitsupdates und nicht sicherheitsrelevante Updates für Windows 10 und Office 365-Clients bereitstellen.</li><li>Signale Daten überwachen und Warteschlangen Auswirkungen unterstützen.</li></ul></td><td><ul><li>Überprüfen Sie der Microsoft Managed Desktop Message Center und alle zusätzlichen Informationen.</li><li>   Keine Aktion erforderlich, falls zutreffend, und Testen von Anwendungen.</li><li>Wenn ein Szenario Problembehebung aufgetreten ist, erstellen Sie eine Supportanfrage.</li></ul></td></tr><tr><td>Nach einer Änderung</td><td><ul><li>Sammeln von Feedback von Kunden zur Verbesserung der Einführung von zukünftigen Änderungen.</li><li>Signale Daten überwachen und Warteschlangen Auswirkungen unterstützen.</li></ul></td><td><ul><li>Arbeiten Sie mit Personen in Ihrer Organisation, um die Änderung zu übernehmen.</li><li>   Überprüfen Sie ändern und Annahme Verwaltungsprozesse für Verkaufschancen, Effizienz zu erhalten.</li><li>Geben Sie allgemeine Kommentare und bestimmte Feedback in das Verwaltungstool Feedback.</li><li>Schulen von Benutzern an den Windows-Hub Feedback und die Schaltfläche Smiley in Office-apps mit app-spezifischen Feedback geben möchten.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Änderungstypen

Es gibt verschiedene Arten von Änderungen, die mit dem Dienst in regelmäßigen Abständen vorgenommen werden. Hängt von der Kommunikationskanal für diese Änderungen und die Aktionen, denen Kunden für zuständig sind.

Nicht alle Änderungen haben die gleiche Auswirkung auf die Benutzer oder Aktion erforderlich. Geplante und einige ungeplante aufgrund ihrer Beschaffenheit einige (nicht sicherheitsrelevante Updates und Sicherheitsupdates sind nicht in der Regel geplant). Je nach Art der Änderung kann der Kommunikationskanal variieren. Die folgende Tabelle enthält die Arten von Änderungen, die Sie für den Dienst Microsoft verwalteter Desktop erwarten können.

|   | Funktionalität |   Nicht sicherheitsrelevante Sicherheitsupdates |  Sicherheit
--- | --- | --- | ---
**Art der Änderung** | -Feature updates<br>-Neue Features und Anwendungen<br>-Veraltete features | Client-Hotfixes für Probleme | Sicherheitspatches
**Voraus** | 5 Tage beachten, damit die Änderungen, die eine Aktion erfordern |    Nein, dies in der monatlichen Version enthalten   | Nein, dies in der monatlichen Version enthalten 
**Kommunikationskanal** | -Nachrichtencenter<br>-E-Mail Benachrichtigung | -Nachrichtencenter<br>-E-Mail Benachrichtigung | -Nachrichtencenter<br>-E-Mail Benachrichtigung<br>-Sicherheitsbulletin oder CVE 
**Erfordert Mandanten Administratoraktion** | Manchmal |  Nur selten |    Nur selten 
**Typ der Aktion** | Ändern der Einstellungen | Kommunizieren der Änderungen an Benutzer | Ändern der Administratoreinstellungen     
**Erfordert Tests** | Überprüfen von Geschäftsanwendungen, einschließlich RAS-Dienste |  Manchmal – Testen des Fix im Hinblick auf die Prozesse und Anpassungen |   Nur selten 
**Beispiele für Änderung** | -Feature-Updates: IT-Admin-Portal vereinfacht Support Ticket einreichen und überprüfen<br>-Neue Features oder Applications: halb jährliche Version eines Updates Feature Windows 10 | Hotfixes basierend auf den von Kunden gemeldeten Fehlern |  


## <a name="standard-operating-procedures"></a>Standardverfahren

Der Dienst Microsoft verwalteter Desktop implementiert und von Microsoft betrieben wird in der Microsoft-Cloud-Instanz, in dem Sie andere administrativen Aktivitäten durchführen können. Microsoft ist verantwortlich für Microsoft Managed Desktop-spezifische Installation, Konfiguration und Vorgang. 

Für lokale-Produkte übernimmt alle die Verantwortung für die Verwaltung von Setup und Konfiguration und betriebliche Aktivitäten Ihrer Organisation.

Categories |    Wird von Microsoft | Kunden werden
--- | --- | ---
Netzwerk (Proxy, Paketinspektion, VPN)  | Advise- und mit Kunden Minimieren von Risiken für Geschäftsbenutzer planen. | -Erstellen Sie eine Supportanfrage Anfordern von Informationen für eine geplante konfigurationsänderung, einschließlich der Konfigurationsdetails, Bereich, Zeitplan und anderen relevanten Details für Microsoft um zu prüfen.<br>– Nur gelten Sie eine Änderung sobald Microsoft verwalteten Desktops Operations bewertet und empfohlen hat.
Dienstkonten |-Implementieren, sicher speichern und die Anmeldeinformationen verwalten.<br> -Kommunizieren Sie vor unbefugten Zugriffen oder Verwendung von diese Anmeldeinformationen an Ihr Team Sicherheitsoperationen. | -Erstellen Sie eine Supportanfrage Anfordern von Informationen für eine geplante konfigurationsänderung, einschließlich der Konfigurationsdetails, Bereich, Zeitplan und anderen relevanten Details für Microsoft um zu prüfen.<br>– Nur gelten Sie eine Änderung sobald Microsoft verwalteten Desktops Operations bewertet und empfohlen hat.<br>-Nicht weisen Sie Richtlinie, mehrstufige Authentifizierung, bedingten Zugriff oder Bereitstellung der Anwendung Microsoft verwalteten Desktops Dienstkonten.<br>-Nicht zurückzusetzen Sie das Kennwort, oder verwenden Sie die Anmeldeinformationen.<br>-Öffnen Sie eine Sev C Supportanfrage an Microsoft verwalteten Desktops Operations, wenn verdächtiger Aktivitäten Intune oder Azure Überwachungsprotokolle im Zusammenhang mit dieser Dienstkonten festgestellt wird.
Device-Gruppen | -Implementieren und Verwalten der Mitgliedschaft der Geräte innerhalb von Microsoft verwalteten Desktops Gruppen.<br>-Verwenden Sie die Gruppen Microsoft verwalteter Desktop, um die Zuordnung und Freigabe von Konfiguration und Updates für Geräte verwalten. | -Erstellen Sie eine Supportanfrage Anfordern von Informationen für eine geplante konfigurationsänderung, einschließlich der Konfigurationsdetails, Bereich, Zeitplan und anderen relevanten Details für Microsoft um zu prüfen.<br>– Nur gelten Sie eine Änderung sobald Microsoft verwalteten Desktops Operations bewertet und empfohlen hat.<br>-Ändern Sie die Mitgliedschaft einer beliebigen Gruppe verwalteter Microsoft-Desktop nicht.<br>– Verwenden Sie nur die Gruppen, um im Unternehmen Zertifikate für Dienste wie VPN, Windows Hello für Business oder e-Mail-Verschlüsselung oder corporate Wi-Fi-Profilkonfiguration zuzuweisen.<br>-Co-Management wenn vorhanden ist, alle Microsoft verwalteter Desktop Gruppen explizit ausschließen, bei der Bereitstellung von Configuration Manager-Client.
Policies |  -Implementieren und Verwalten der Microsoft verwalteter Desktop-Richtlinien, die den Konfigurationsstatus Geräte im Dienst steuern.<br>-Bereitstellung von Updates, auf die Richtlinie oder Windows inkrementell mit Device-Gruppen.<br> -Schließen Sie aus explizit für nicht - Microsoft verwalteter Desktop Gruppen. | -Erstellen Sie eine Supportanfrage Anfordern von Informationen für eine geplante konfigurationsänderung, einschließlich der Konfigurationsdetails, Bereich, Zeitplan und anderen relevanten Details für Microsoft um zu prüfen.<br>– Nur gelten Sie eine Änderung sobald Microsoft verwalteten Desktops Operations bewertet und empfohlen hat.<br>-Nicht bearbeiten, oder Geräte oder Benutzer nicht vom Microsoft verwalteter Desktop-Dienst verwaltet Microsoft verwalteter Desktop Richtlinien zuweisen.
Windows Defender Advanced Threat Protection | Überwachung und die Überprüfung der Geräte innerhalb des Bereichs des Diensts Microsoft verwalteter Desktop. | -Erstellen Sie eine Supportanfrage Anfordern von Informationen für eine geplante konfigurationsänderung, einschließlich der Konfigurationsdetails, Bereich, Zeitplan und anderen relevanten Details für Microsoft um zu prüfen.<br>– Anwenden Sie eine Änderung nur, wenn Microsoft verwalteten Desktops Operations bewertet geraten und hat
Microsoft Store für Unternehmen |  Konfigurieren und Verwalten des Windows-Autopilot Profils für den Dienst Microsoft verwalteter Desktop. | -Erstellen Sie eine Supportanfrage Anfordern von Informationen für eine geplante konfigurationsänderung, einschließlich der Konfigurationsdetails, Bereich, Zeitplan und anderen relevanten Details für Microsoft um zu prüfen.<br>– Nur gelten Sie eine Änderung sobald Microsoft verwalteten Desktops Operations bewertet und empfohlen hat.<br>-Ändern Sie die Konfiguration des Profils Microsoft verwalteten Desktops Windows Autopilot nicht oder zugeordneten Geräte hinzufügen/entfernen.
Zertifikate | | -Erstellen Sie eine Supportanfrage 60 Tage, bevor Sie ein Zertifikat abläuft, wobei die Informationen für eine geplante konfigurationsänderung, einschließlich der Konfigurationsdetails, Bereich, Zeitplan und anderen relevanten Details für Microsoft um zu prüfen.<br>– Nur gelten Sie eine Änderung sobald Microsoft verwalteten Desktops Operations bewertet und empfohlen hat.<br>-Aktualisieren Sie alle Zertifikate, die für das Zertifikat, VPN-Profile, und Wi-Fi-Profile konfigurieren erforderlich sind.




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
