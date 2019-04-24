---
title: Microsoft Managed Desktop-Vorgänge und-Überwachung
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 12/18/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 391c5cca9f1d440a806fa094633b50c3256c2a26
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291460"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Desktop-Vorgänge und-Überwachung

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Änderungsverwaltung

In einem Dienstangebot liegt die Verantwortlichkeit für Bereiche wie Wartung der Hardware und Sicherheitsupdates bei dem Dienstanbieter (Microsoft), und nicht bei dem Kunden (Ihnen). Allerdings müssen Sie sicherstellen, dass Drittanbieter-und benutzerdefinierte Software weiterhin wie erwartet funktioniert, wenn Updates ausgeführt werden.

Für lokale Produkte übernimmt Ihre Organisation alle Verantwortung für die Verwaltung von Änderungen.

### <a name="balance-of-responsibility"></a>Verantwortungs Ausgleich

Responsibility | Microsoft Managed Desktop-Dienst | Microsoft 365-Client Software | Lokale Clients und Server | Drittanbieter-und benutzerdefinierte Software
----- | ----- | ----- | ----- | -----
Bereitstellen neue Funktionalität | Microsoft | Microsoft | In beide Richtungen | Kunde
Testen neuer Features zum Sicherstellen der Qualität |  Microsoft | Microsoft | In beide Richtungen | Kunde
Kommunikation zu neuen Features | In beide Richtungen | In beide Richtungen | In beide Richtungen | Kunde
Integrieren von benutzerdefinierten Software | In beide Richtungen | In beide Richtungen | Kunde | Kunde
Anwenden von Sicherheitsupdates | Microsoft | Microsoft | Kunde | Kunde
Warten von Systemsoftware | Microsoft | Microsoft | Kunde | Kunde
Paket für die Bereitstellung | Microsoft | Microsoft | Kunde | Kunde


### <a name="change-process-overview"></a>Änderungsprozess Übersicht

Im folgenden finden Sie eine Zusammenfassung der Freigabe des Änderungsprozesses zwischen Microsoft und Kunden. 



<table>
<tr><th></th><th><p>Rolle von Microsoft:</p></th><th><p>Rolle des Kunden:</p></th></tr>
<tr><td>Vor einer Änderung</td><td><ul><li>Festlegen der Erwartungen an Dienständerungen</li><li>Informieren Sie die Kunden 5 Tage im Voraus über Änderungen, die eine Administratoraktion erfordern.</li><li>Wenden Sie bei Notfalländerungen eine Minderung vor der Benachrichtigung an.</li></ul></td><td><ul><li>Verstehen der zu erwartenden Änderungen und Kommunikation</li><li>Regelmäßiges Lesen des Microsoft Managed Desktop-Nachrichten Centers.</li><li>Überprüfen und Aktualisieren interner Change Management-Prozesse</li><li>Verstehen und Überprüfen der Einhaltung der Anforderungen von Microsoft Managed Desktop. </li><li>Bestätigen und genehmigen, falls erforderlich.</li></ul></td></tr><tr><td>Während einer Änderung</td><td><ul><li>Veröffentlichen Sie monatliche Sicherheits-und nicht sicherheitsrelevante Updates für Windows 10-und Office 365-Clients.</li><li>Überwachen von Datensignalen und unterstützen von Warteschlangen.</li></ul></td><td><ul><li>Überprüfen Sie das Microsoft Managed Desktop-Nachrichten Center, und überprüfen Sie zusätzliche Informationen.</li><li>   Führen Sie ggf. erforderliche Aktionen aus, und testen Sie Anwendungen.</li><li>Wenn ein Break/Fix-Szenario erlebt wird, erstellen Sie eine Support Anfrage.</li></ul></td></tr><tr><td>Nach einer Änderung</td><td><ul><li>Sammeln von Kundenfeedback zur Verbesserung der Einführung zukünftiger Änderungen.</li><li>Überwachen von Datensignalen und unterstützen von Warteschlangen.</li></ul></td><td><ul><li>Arbeiten Sie mit Personen in Ihrer Organisation zusammen, um die Änderung zu übernehmen.</li><li>   Überwachen von Change-und Adoptions Verwaltungsprozessen für Möglichkeiten zur Effizienzsteigerung.</li><li>Geben Sie Allgemeines Feedback und spezifisches Feedback im Tool zum Administrator Feedback.</li><li>Schulen Sie Benutzer, um App-spezifisches Feedback mithilfe des Windows Feedback-Hubs und der smile-Schaltfläche in Office-Apps bereitzustellen.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Änderungstypen

Es gibt verschiedene Arten von Änderungen, die in regelmäßigen Abständen an dem Dienst vorgenommen werden. Der Kommunikationskanal für diese Änderungen und die Aktionen, für die Kunden verantwortlich sind, variieren.

Nicht alle Änderungen wirken sich gleichermaßen auf die Benutzer aus und erfordern eine Aktion. Einige sind geplant und einige nicht geplant (nicht sicherheitsrelevante Updates und Sicherheitsupdates sind in der Regel nicht geplant). Je nach Art der Änderung kann der Kommunikationskanal variieren. In der folgenden Tabelle sind die Arten von Änderungen aufgeführt, die Sie für den Microsoft Managed Desktop-Dienst erwarten können.

|   | Funktionalität |   Nicht sicherheitsrelevante Updates |  Sicherheit
--- | --- | --- | ---
**Art der Änderung** | -Feature-Updates<br>-Neue Features oder Anwendungen<br>-VerAltete Features | Client-Hotfixes für Probleme | Sicherheitspatches
**Vorankündigung** | 5 Tage Hinweis für Änderungen, die eine Aktion erfordern |    Nein, diese sind in der monatlichen Freigabe enthalten.   | Nein, diese sind in der monatlichen Freigabe enthalten. 
**Kommunikationskanal** | -Nachrichten Center<br>-E-Mail-Benachrichtigung | -Nachrichten Center<br>-E-Mail-Benachrichtigung | -Nachrichten Center<br>-E-Mail-Benachrichtigung
**Erfordert mandantenadministrator Aktion** | Manchmal |  Nur selten |    Nur selten 
**Aktionstyp** | Ändern der Einstellungen | Kommunizieren der Änderungen an Benutzer | Ändern der Administratoreinstellungen     
**Tests erforderlich** | Überprüfen von Geschäftsanwendungen, einschließlich RAS-Diensten |  Manchmal – Testen des Fix im Hinblick auf die Prozesse und Anpassungen |   Nur selten 
**Beispiele für Änderungen** | -Feature-Updates: vereinfachte Unterstützung des Support Tickets und der Überprüfungen durch das IT-Verwaltungs Portal<br>-Neue Features oder Anwendungen: halbjährliche Version eines Windows 10-Funktionsupdates | Hotfixes basierend auf den von Kunden gemeldeten Fehlern |  


## <a name="standard-operating-procedures"></a>Standard-Betriebsverfahren

Der Microsoft Managed Desktop-Dienst wird von Microsoft in Ihrer Microsoft-Cloud-Instanz implementiert und betrieben, in der Sie andere administrative Aktivitäten durchführen können. Microsoft ist ausschließlich für Microsoft Managed Desktop-spezifische Einrichtung, Konfiguration und Betrieb verantwortlich. 

Für lokale Produkte übernimmt Ihre Organisation die gesamte Verantwortung für die Verwaltung von Setup sowie für Konfigurations-und Betriebsaktivitäten.

Kategorien |    Microsoft wird | Kunde wird
--- | --- | ---
Netzwerk (Proxy, Paketprüfung, VPN)  | Beratung und Planung mit Kunden zur Minimierung des Risikos für geschäftliche Benutzer. | -Erstellen Sie eine Supportanfrage, in der Informationen zu einer geplanten Konfigurationsänderung angefordert werden, einschließlich Konfigurationsdetails, Umfang, Zeitachsen und anderen relevanten Details, die von Microsoft überprüft werden müssen.<br>-Wenden Sie nur eine Änderung an, nachdem Microsoft Managed Desktop-Vorgänge bewertet und empfohlen haben.
Dienstkonten |-Implementieren, sicheres Speichern und Verwalten der Anmeldeinformationen.<br> -Kommunizieren Sie nicht autorisierten Zugriff oder die Verwendung dieser Anmeldeinformationen für Ihr Sicherheitsteam. | -Erstellen Sie eine Supportanfrage, in der Informationen zu einer geplanten Konfigurationsänderung angefordert werden, einschließlich Konfigurationsdetails, Umfang, Zeitachsen und anderen relevanten Details, die von Microsoft überprüft werden müssen.<br>-Wenden Sie nur eine Änderung an, nachdem Microsoft Managed Desktop-Vorgänge bewertet und empfohlen haben.<br>-Weisen Sie keine Richtlinie, mehrstufige Authentifizierung, bedingten Zugriff oder Anwendungsbereitstellung zu den Microsoft Managed Desktop-Dienstkonten zu.<br>-Das Kennwort nicht zurücksetzen oder die Anmeldeinformationen verwenden.<br>-Öffnen Sie eine SEV C-Supportanforderung für Microsoft Managed Desktop-Vorgänge, wenn in InTune-oder Azure-Überwachungsprotokollen, die sich auf diese Dienstkonten beziehen, verdächtige Aktivitäten beobachtet werden.
Gerätegruppen | -Implementieren und Verwalten der Mitgliedschaft von Geräten in Microsoft Managed Desktop-Gruppen<br>-Verwenden Sie die Microsoft Managed Desktop-Gruppen, um die Zuweisung und Freigabe von Konfigurationen und Updates für Geräte zu verwalten. | -Erstellen Sie eine Supportanfrage, in der Informationen zu einer geplanten Konfigurationsänderung angefordert werden, einschließlich Konfigurationsdetails, Umfang, Zeitachsen und anderen relevanten Details, die von Microsoft überprüft werden müssen.<br>-Wenden Sie nur eine Änderung an, nachdem Microsoft Managed Desktop-Vorgänge bewertet und empfohlen haben.<br>-Die Mitgliedschaft in einer Gruppe von Microsoft-verwalteten Desktops wird nicht geändert.<br>-Verwenden Sie die Gruppen nur, um Unternehmenszertifikate für Dienste wie VPN, Windows Hello for Business oder e-Mail-Verschlüsselung oder die Firmen-WLAN-Profilkonfiguration zuzuweisen.<br>-Wenn die Co-Verwaltung vorhanden ist, schließen Sie bei der Bereitstellung des Configuration Manager-Clients explizit alle Microsoft Managed Desktop-Gruppen aus.
Richtlinien |  -Implementieren und Verwalten der von Microsoft verwalteten Desktop Richtlinien, die den Konfigurationsstatus der Geräte innerhalb des Diensts steuern.<br>-Bereitstellen von Updates, in Richtlinien oder Windows, schrittweise Verwendung von Gerätegruppen.<br> – Explizites Ausschließen von Zielgruppen für nicht von Microsoft verwaltete Desktops. | -Erstellen Sie eine Supportanfrage, in der Informationen zu einer geplanten Konfigurationsänderung angefordert werden, einschließlich Konfigurationsdetails, Umfang, Zeitachsen und anderen relevanten Details, die von Microsoft überprüft werden müssen.<br>-Wenden Sie nur eine Änderung an, nachdem Microsoft Managed Desktop-Vorgänge bewertet und empfohlen haben.<br>-Nicht bearbeiten oder Zuweisen von Microsoft Managed Desktop-Richtlinien zu Geräten oder Benutzern, die nicht vom Microsoft Managed Desktop Service verwaltet werden.
Windows Defender Advanced Threat Protection | Überwachen und untersuchen Sie Geräte innerhalb des Bereichs des Microsoft Managed Desktop-Diensts. | -Erstellen Sie eine Supportanfrage, in der Informationen zu einer geplanten Konfigurationsänderung angefordert werden, einschließlich Konfigurationsdetails, Umfang, Zeitachsen und anderen relevanten Details, die von Microsoft überprüft werden müssen.<br>-Nur eine Änderung anwenden, nachdem Microsoft Managed Desktop-Vorgänge bewertet und empfohlen haben
Microsoft Store für Unternehmen |  Konfigurieren und verwalten Sie das Windows Autopilot-Profil für den Microsoft Managed Desktop-Dienst. | -Erstellen Sie eine Supportanfrage, in der Informationen zu einer geplanten Konfigurationsänderung angefordert werden, einschließlich Konfigurationsdetails, Umfang, Zeitachsen und anderen relevanten Details, die von Microsoft überprüft werden müssen.<br>-Wenden Sie nur eine Änderung an, nachdem Microsoft Managed Desktop-Vorgänge bewertet und empfohlen haben.<br>-Ändern Sie nicht die Konfiguration des Microsoft Managed Desktop-Windows Autopilot-Profils oder Hinzufügen/Entfernen von zugewiesenen Geräten.
Zertifikate | | -Erstellen einer Supportanfrage 60 Tage vor Ablauf des Zertifikats, Anfordern von Informationen für eine geplante Konfigurationsänderung, einschließlich Konfigurationsdetails, Umfang, Zeitachsen und anderer relevanter Details, die von Microsoft überprüft werden müssen.<br>-Wenden Sie nur eine Änderung an, nachdem Microsoft Managed Desktop-Vorgänge bewertet und empfohlen haben.<br>-Aktualisieren Sie alle Zertifikate, die zum Konfigurieren von Zertifikat Profilen, VPN-Profilen und WLAN-Profilen erforderlich sind.




## <a name="device-wipe-with-factory-reset"></a>Gerätezurücksetzung mit Factory-Reset

Das Managed Desktop Operations-Team kann eine Factory-Zurücksetzung auf von Microsoft verwalteten Desktop-verwalteten Geräten durchführen, die neu abbildet werden müssen. Dies ist hilfreich, wenn Sie einem anderen Mitarbeiter ein Gerät zuweisen müssen oder wenn ein Mitarbeiter Ihr Unternehmen verlässt. 

Es gibt einige Anforderungen:

- Der mandantenadministrator des Kunden muss eine Serviceanfrage übermitteln.
- Wir benötigen den Computernamen für das Gerät.
- Benutzerkonto muss in Azure AD vor dem Zurücksetzen

Das Team für verwaltete Desktop Vorgänge wird Folgendes tun:

- Nachschlagen des Gerätenamens in InTune
- Senden des Factory-Reset-Befehls an das Gerät

>[!NOTE]
>Entfernen Sie das Benutzerkonto nicht aus Azure AD, bevor Sie das Werk zurücksetzen. Wenn der Benutzer nicht in Azure AD ist, kann InTune den Factory-Reset-Befehl nicht an das Gerät senden. 

Das Gerät wird in OOBE gestartet, und alle vorinstallierten Anwendungen und Einstellungen werden erneut angewendet. Der Benutzer des Geräts muss erneut die ersten Informationen einrichten. 

Wenn das Gerät zurückgesetzt wurde, können Sie es einer anderen Person in Ihrer Organisation übergeben. Keine der Daten des vorherigen Benutzers oder Enterprise-Daten befinden sich auf dem Gerät. Der nächste Benutzer wird den gleichen Prozess durchlaufen, den die vorherige Person mit einem neuen von Microsoft verwalteten Desktop Gerät ausgeführt hat.

BitLocker ist ein wichtiger Bestandteil der Datensicherheit in diesem Prozess. Mit der BitLocker-Verschlüsselung auf verwalteten Desktop Geräten von Microsoft bleiben Daten auf dem Laufwerk auch nach dem Zurücksetzen der Factory auf dem Gerät sicher. Alle Daten auf dem Laufwerk stehen dem nächsten Benutzer des Geräts nicht zur Verfügung. Weitere Informationen finden Sie unter [BitLocker Overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).

Weitere Informationen finden Sie unter [Factory Reset a Device](https://docs.microsoft.com/intune/devices-wipe#factory-reset-a-device). 
