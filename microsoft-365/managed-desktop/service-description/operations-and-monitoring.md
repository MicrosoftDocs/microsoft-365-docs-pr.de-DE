---
title: Microsoft Managed Desktop-Vorgänge und -Überwachung
description: Wer was für verschiedene Änderungsprozesse tut
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 3e56066f0b4e63fc9b73bbecf5aaa3180ffd2e4f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920420"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Desktop-Vorgänge und -Überwachung

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Change Management

In einem Dienstangebot liegt die Verantwortlichkeit für Bereiche wie Wartung der Hardware und Sicherheitsupdates bei dem Dienstanbieter (Microsoft), und nicht bei dem Kunden (Ihnen). Sie müssen jedoch weiterhin sicherstellen, dass nicht von Microsoft und benutzerdefinierter Software beim Roll out von Updates weiterhin wie erwartet funktioniert.

Bei lokalen Produkten übernimmt Ihre Organisation alle Verantwortung für die Verwaltung von Änderungen.

### <a name="balance-of-responsibility"></a>Verantwortlichkeitsausgleich

Zuständigkeit | Microsoft Managed Desktop Service | Microsoft 365-Clientsoftware | Lokale Clients und Server | Nicht-Microsoft und benutzerdefinierte Software
----- | ----- | ----- | ----- | -----
Bereitstellen neue Funktionalität | Microsoft | Microsoft | In beide Richtungen | Kunde
Testen neuer Features zum Sicherstellen der Qualität |  Microsoft | Microsoft | In beide Richtungen | Kunde
Kommunikation zu neuen Features | In beide Richtungen | In beide Richtungen | In beide Richtungen | Kunde
Integrieren von benutzerdefinierten Software | In beide Richtungen | In beide Richtungen | Kunde | Kunde
Anwenden von Sicherheitsupdates | Microsoft | Microsoft | Kunde | Kunde
Warten von Systemsoftware | Microsoft | Microsoft | Kunde | Kunde
Paket für die Bereitstellung | Microsoft | Microsoft | Kunde | Kunde


### <a name="change-process-overview"></a>Übersicht über den Änderungsprozess

Hier ist eine Zusammenfassung der Gemeinsamen Verwendung des Änderungsprozesses zwischen Microsoft und Kunden: 



<table>
<tr><th></th><th><p>Rolle von Microsoft:</p></th><th><p>Rolle des Kunden:</p></th></tr>
<tr><td>Vor einer Änderung</td><td><ul><li>Festlegen der Erwartungen an Dienständerungen</li><li>Benachrichtigen Sie Kunden 5 Tage im Voraus über Änderungen, die Administratoraktion erfordern.</li><li>Wenden Sie bei Notfalländerungen vor der Benachrichtigung eine Risikominderung an.</li></ul></td><td><ul><li>Verstehen der zu erwartenden Änderungen und Kommunikation</li><li>Lesen Sie Microsoft Managed Desktop Message Center regelmäßig.</li><li>Überprüfen und Aktualisieren interner Change Management-Prozesse</li><li>Verstehen und Überprüfen der Einhaltung der Microsoft Managed Desktop-Anforderungen. </li><li>Bestätigen und genehmigen, falls erforderlich.</li></ul></td></tr><tr><td>Während einer Änderung</td><td><ul><li>Veröffentlichen und Bereitstellen monatlicher Sicherheits- und nicht sicherheitsfreier Updates für Windows 10- und Office 365-Clients.</li><li>Überwachen Sie Datensignale und unterstützen Sie Warteschlangen auf Auswirkungen.</li></ul></td><td><ul><li>Überprüfen Sie das Microsoft Managed Desktop Message Center, und überprüfen Sie alle zusätzlichen Informationen.</li><li>   Ergreifen Sie ggf. erforderliche Aktionen und Testanwendungen.</li><li>Wenn ein Unterbrechungs-/Behebungsszenario vor sich geht, erstellen Sie eine Supportanfrage.</li></ul></td></tr><tr><td>Nach einer Änderung</td><td><ul><li>Sammeln sie Kundenfeedback, um die Einführung zukünftiger Änderungen zu verbessern.</li><li>Überwachen Sie Datensignale und unterstützen Sie Warteschlangen auf Auswirkungen.</li></ul></td><td><ul><li>Arbeiten Sie mit Personen in Ihrer Organisation zusammen, um die Änderung zu übernehmen.</li><li>   Überprüfen Sie Änderungs- und Einführungsverwaltungsprozesse auf Möglichkeiten zur Effizienzsteigerung.</li><li>Geben Sie allgemeines Feedback und spezifisches Feedback im Administratorfeedbacktool.</li><li>Schulen Sie Benutzer, um app-spezifisches Feedback mithilfe des Windows Feedback Hubs und der Schaltfläche Smile in Office-Apps zu geben.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Änderungstypen

Es gibt verschiedene Arten von Änderungen, die wir regelmäßig am Dienst vornehmen. Der Kommunikationskanal für diese Änderungen und die Aktionen, für die Sie verantwortlich sind, variieren.

Nicht alle Änderungen wirken sich gleichermaßen auf die Benutzer aus und erfordern eine Aktion. Einige sind geplant, andere sind nicht geplant (nicht Sicherheitsupdates und Sicherheitsupdates sind in der Regel nicht geplant). Je nach Änderungstyp kann der Kommunikationskanal variieren. In der folgenden Tabelle sind die Arten von Änderungen aufgeführt, die Sie für den Microsoft Managed Desktop-Dienst erwarten können.

|   | Funktionalität |   Nicht sicherheitsrelevante Sicherheitsupdates |  Sicherheit
--- | --- | --- | ---
**Art der Änderung** | - Featureupdates<br>– Neue Features oder Anwendungen<br>– Veraltete Features | Client-Hotfixes für Probleme | Sicherheitsupdates
**Vorankündigung** | 5 Tage Benachrichtigung über Änderungen, die eine Aktion erfordern | Nein, solche Änderungen sind in der monatlichen Version enthalten.    | Nein, Änderungen sind in der monatlichen Version enthalten 
**Kommunikationskanal** | - Nachrichtencenter<br>- E-Mail-Warnung | - Nachrichtencenter<br>- E-Mail-Warnung | - Nachrichtencenter<br>- E-Mail-Warnung
**Erfordert globale Administratoraktion** | Manchmal |  Nur selten |    Nur selten 
**Aktionstyp** | Ändern der Einstellungen | Kommunizieren der Änderungen an Benutzer | Ändern der Administratoreinstellungen     
**Erfordert Tests** | Überprüfen von Geschäftsanwendungen, einschließlich Remotezugriffsdiensten |  Manchmal – Testen des Fix im Hinblick auf die Prozesse und Anpassungen |   Nur selten 
**Beispiele für Änderungen** | - Featureupdates: Vereinfachte Supportticketübermittlung und -überprüfung im IT Admin Portal<br>– Neue Features oder Anwendungen: Semi-Annual version eines Windows 10-Featureupdates | Hotfixes basierend auf den von Kunden gemeldeten Fehlern |  


## <a name="standard-operating-procedures"></a>Standardbetriebsverfahren

Der Microsoft Managed Desktop-Dienst wird von Microsoft in Ihrer Microsoft-Cloudinstanz implementiert und betrieben, in der Sie möglicherweise andere administrative Aktivitäten durchführen. Microsoft ist allein für die Einrichtung, Konfiguration und den Betrieb von Microsoft Managed Desktop verantwortlich. 

Bei lokalen Produkten übernimmt Ihre Organisation die verantwortung für die Verwaltung der Einrichtung sowie für konfigurations- und betriebsbereite Aktivitäten.

Kategorien |    Microsoft wird | Der Kunde wird
--- | --- | ---
Netzwerk (Proxy, Paketprüfung, VPN)  | Beraten Und planen Sie mit Kunden, um das Risiko für Geschäftsbenutzer zu minimieren. | – Erstellen Sie eine Supportanfrage, die Informationen für eine geplante Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Operations bewertet und beraten wurde.
Dienstkonten |– Implementieren, speichern und verwalten Sie die Anmeldeinformationen.<br> – Teilen Sie Ihrem Security Operations-Team nicht autorisierten Zugriff oder die Verwendung dieser Anmeldeinformationen mit. | – Erstellen Sie eine Supportanfrage, die Informationen für eine geplante Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Operations bewertet und beraten wurde.<br>– Zuweisen von Richtlinien, mehrstufiger Authentifizierung, bedingter Zugriff oder Anwendungsbereitstellung zu den Microsoft Managed Desktop Service Accounts nicht.<br>– Setzen Sie das Kennwort nicht zurück, oder verwenden Sie die Anmeldeinformationen.<br>– Öffnen Sie eine Sev C-Supportanfrage an Microsoft Managed Desktop Operations, wenn verdächtige Aktivitäten in Intune- oder #A0 im Zusammenhang mit diesen Dienstkonten beobachtet werden.
Gerätegruppen | – Implementieren und Verwalten der Mitgliedschaft von Geräten in Microsoft Managed Desktop-Gruppen.<br>– Verwenden Sie die Microsoft Managed Desktop-Gruppen, um die Zuweisung und Freigabe von Konfigurationen und Updates auf Geräten zu verwalten. | – Erstellen Sie eine Supportanfrage, die Informationen für eine geplante Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Operations bewertet und beraten wurde.<br>– Die Mitgliedschaft in einer Microsoft Managed Desktop-Gruppe wird nicht geändert.<br>- Verwenden Sie die Gruppen nur, um Unternehmenszertifikate für Dienste wie VPN, Windows Hello for Business oder E-Mail-Verschlüsselung oder Wi-Fi zuzuordnen.<br>– Schließen Sie bei der Bereitstellung des Configuration Manager-Clients explizit alle Microsoft Managed Desktop-Gruppen aus.
Richtlinien |  – Implementieren und Verwalten der Microsoft Managed Desktop-Richtlinien, die den Konfigurationsstatus von Geräten innerhalb des Diensts steuern.<br>– Bereitstellen von Updates für Richtlinien oder Windows mithilfe von Gerätegruppen inkrementell.<br> – Explizites Ausschließen von Nicht-Microsoft Managed Desktop-Gruppen. | – Erstellen Sie eine Supportanfrage, die Informationen für eine geplante Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Operations bewertet und beraten wurde.<br>– Bearbeiten oder Zuweisen von Microsoft Managed Desktop-Richtlinien nicht zu Geräten oder Benutzern, die nicht vom Microsoft Managed Desktop-Dienst verwaltet werden.
Microsoft Defender für Endpunkt | Überwachen und untersuchen Sie Geräte im Rahmen des Microsoft Managed Desktop-Diensts. | – Erstellen Sie eine Supportanfrage, die Informationen für eine geplante Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Operations bewertet und beraten wurde.
Microsoft Store für Unternehmen |  Konfigurieren und Verwalten des Windows Autopilot-Profils für den Microsoft Managed Desktop-Dienst. | – Erstellen Sie eine Supportanfrage, die Informationen für eine geplante Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Operations bewertet und beraten wurde.<br>- Die Konfiguration des Microsoft Managed Desktop Windows Autopilot-Profils nicht ändern oder zugewiesene Geräte hinzufügen/entfernen.
Zertifikate | | – Erstellen Sie eine Supportanfrage 60 Tage vor Ablauf eines Zertifikats, und fordern Sie Informationen zu einer geplanten Konfigurationsänderung an, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderen relevanten Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Operations bewertet und beraten wurde.<br>- Aktualisieren Sie alle Zertifikate, die zum Konfigurieren von Zertifikatprofilen, VPN-Profilen und Wi-Fi erforderlich sind.




## <a name="device-wipe-with-factory-reset"></a>Gerätezurücksetzung mit Werkszurücksetzung

Das Microsoft Managed Desktop Operations-Team kann bei Bedarf eine Werkszurücksetzung von Geräten ausführen, die beim Dienst registriert sind. Das Zurücksetzen ist hilfreich, wenn Sie einem anderen Mitarbeiter ein Gerät geben müssen oder wenn ein Mitarbeiter Ihr Unternehmen verlässt. 

Es gibt einige Anforderungen:

- Ihr globaler Administrator muss eine Dienstanforderung übermitteln.
- Schließen Sie den Computernamen des Geräts in die Anforderung ein.
- Das Benutzerkonto muss sich in Azure AD begnnen, bevor wir das Gerät zurücksetzen.

Das Team für verwaltete Desktopvorgänge geht wie folgt vor:

- Suchen des Gerätenamens in Intune
- Senden des Werkszurücksetzungsbefehls an das Gerät

>[!NOTE]
>Entfernen Sie das Benutzerkonto nicht aus Azure AD, bevor das Gerät zurückgesetzt wird. Wenn sich der Benutzer nicht in Azure AD befindet, kann Intune den Befehl zur Werkszurücksetzung nicht an das Gerät senden. 

Das Gerät startet in die "out-of-box"-Umgebung, und alle vorinstallierten Anwendungen und Einstellungen werden erneut angewendet. Der Benutzer des Geräts muss erneut erste Setupinformationen bereitstellen. 

Wenn das Gerät zurückgesetzt wurde, können Sie es einer anderen Person in Ihrer Organisation geben. Keine der Daten oder Unternehmensdaten des vorherigen Benutzers ist auf dem Gerät enthalten. Der nächste Benutzer wird den gleichen Prozess wie die vorherige Person mit einem neuen Microsoft Managed Desktop-Gerät durchgehen.

BitLocker ist eine wichtige Komponente der Datensicherheit in diesem Prozess. Mit der BitLocker-Verschlüsselung auf Microsoft Managed Desktop-Geräten bleiben die Daten auf dem Laufwerk auch nach dem Zurücksetzen des Geräts sicher. Alle Daten, die auf dem Laufwerk vorhanden waren, stehen dem nächsten Benutzer des Geräts nicht zur Verfügung. Weitere Informationen finden Sie unter [BitLocker overview](/windows/security/information-protection/bitlocker/bitlocker-overview).

Weitere Informationen finden Sie unter [Factory reset a device](/intune/remote-actions/devices-wipe#factory-reset-a-device).