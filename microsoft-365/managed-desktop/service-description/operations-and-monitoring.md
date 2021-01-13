---
title: Microsoft Managed Desktop – Vorgänge und Überwachung
description: Wer was für verschiedene Änderungsprozesse macht
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
ms.openlocfilehash: 5d7c6a7b836d0044ba9cde188170dd51f117dd2b
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840373"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Desktop – Vorgänge und Überwachung

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Change Management

In einem Dienstangebot liegt die Verantwortlichkeit für Bereiche wie Wartung der Hardware und Sicherheitsupdates bei dem Dienstanbieter (Microsoft), und nicht bei dem Kunden (Ihnen). Sie müssen jedoch sicherstellen, dass Nicht-Microsoft- und benutzerdefinierte Software weiterhin wie erwartet funktionieren, wenn Updates veröffentlicht werden.

Bei lokalen Produkten übernimmt Ihre Organisation sämtliche Verantwortung für die Verwaltung von Änderungen.

### <a name="balance-of-responsibility"></a>Verantwortlichkeitsgleichheit

Responsibility | Microsoft Managed Desktop Service | Microsoft 365-Clientsoftware | Lokale Clients und Server | Nicht von Microsoft und benutzerdefinierte Software
----- | ----- | ----- | ----- | -----
Bereitstellen neue Funktionalität | Microsoft | Microsoft | In beide Richtungen | Kunde
Testen neuer Features zum Sicherstellen der Qualität |  Microsoft | Microsoft | In beide Richtungen | Kunde
Kommunikation zu neuen Features | In beide Richtungen | In beide Richtungen | In beide Richtungen | Kunde
Integrieren von benutzerdefinierten Software | In beide Richtungen | In beide Richtungen | Kunde | Kunde
Anwenden von Sicherheitsupdates | Microsoft | Microsoft | Kunde | Kunde
Warten von Systemsoftware | Microsoft | Microsoft | Kunde | Kunde
Paket für die Bereitstellung | Microsoft | Microsoft | Kunde | Kunde


### <a name="change-process-overview"></a>Übersicht über den Änderungsprozess

Hier ist eine Zusammenfassung der Art und Weise, wie der Änderungsprozess von Microsoft und Kunden gemeinsam genutzt wird: 



<table>
<tr><th></th><th><p>Rolle von Microsoft:</p></th><th><p>Rolle des Kunden:</p></th></tr>
<tr><td>Vor einer Änderung</td><td><ul><li>Festlegen der Erwartungen an Dienständerungen</li><li>Benachrichtigen Sie Kunden 5 Tage im Voraus über Änderungen, die eine Administratoraktion erfordern.</li><li>Wenden Sie bei Notfalländerungen vor der Benachrichtigung eine Gegenmaßnahmen an.</li></ul></td><td><ul><li>Verstehen der zu erwartenden Änderungen und Kommunikation</li><li>Lesen Sie das Microsoft Managed Desktop Message Center regelmäßig.</li><li>Überprüfen und Aktualisieren interner Change Management-Prozesse</li><li>Verstehen und Überprüfen der Einhaltung der Microsoft Managed Desktop-Anforderungen. </li><li>Bestätigen und genehmigen Sie, falls erforderlich.</li></ul></td></tr><tr><td>Während einer Änderung</td><td><ul><li>Veröffentlichen und bereitstellen Sie monatliche Sicherheits- und nicht sicherheitsfreie Updates für Windows 10- und Office 365-Clients.</li><li>Überwachen von Datensignalen und Unterstützen von Warteschlangen auf Auswirkungen.</li></ul></td><td><ul><li>Überprüfen Sie das Microsoft Managed Desktop Message Center, und überprüfen Sie alle zusätzlichen Informationen.</li><li>   Ergreifen Sie ggf. erforderliche Maßnahmen, und testen Sie Anwendungen.</li><li>Wenn ein Break/Fix-Szenario vor liegt, erstellen Sie eine Supportanfrage.</li></ul></td></tr><tr><td>Nach einer Änderung</td><td><ul><li>Sammeln Sie Kundenfeedback, um die Einführung zukünftiger Änderungen zu verbessern.</li><li>Überwachen Von Datensignalen und Unterstützungswarteschlangen auf Auswirkungen.</li></ul></td><td><ul><li>Arbeiten Sie mit Personen in Ihrer Organisation zusammen, um die Änderung zu übernehmen.</li><li>   Überprüfen Sie Änderungs- und Übernahmeverwaltungsprozesse auf Möglichkeiten zur Effizienzsteigerung.</li><li>Geben Sie allgemeines Feedback und spezifisches Feedback im Administratorfeedbacktool.</li><li>Schulen Sie Benutzer, app-spezifisches Feedback mithilfe des Windows-Feedback-Hubs und der Schaltfläche "Schmunzeln" in Office-Apps zu geben.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Änderungstypen

Es gibt verschiedene Arten von Änderungen, die wir regelmäßig am Dienst vornehmen. Der Kommunikationskanal für diese Änderungen und die Aktionen, für die Sie verantwortlich sind, variieren.

Nicht alle Änderungen wirken sich gleichermaßen auf die Benutzer aus und erfordern eine Aktion. Einige sind geplant, andere ungeplant (nicht sicherheitssenkte Updates und Sicherheitsupdates sind in der Regel nicht geplant). Je nach Art der Änderung kann der Kommunikationskanal variieren. In der folgenden Tabelle sind die Arten von Änderungen aufgeführt, die Sie für den Microsoft Managed Desktop Service erwarten können.

|   | Funktionalität |   Nicht sicherheitsrelevante Sicherheitsupdates |  Sicherheit
--- | --- | --- | ---
**Art der Änderung** | – Featureupdates<br>– Neue Features oder Anwendungen<br>– Veraltete Features | Client-Hotfixes für Probleme | Sicherheitsupdates
**Vorankündigung** | 5 Tage Benachrichtigung für Änderungen, die eine Aktion erfordern | Nein, solche Änderungen sind in der monatlichen Version enthalten.    | Nein, Änderungen sind in der monatlichen Version enthalten. 
**Kommunikationskanal** | - Nachrichtencenter<br>– E-Mail-Benachrichtigung | - Nachrichtencenter<br>– E-Mail-Benachrichtigung | - Nachrichtencenter<br>– E-Mail-Benachrichtigung
**Erfordert globale Administratoraktion** | Manchmal |  Nur selten |    Nur selten 
**Aktionstyp** | Ändern der Einstellungen | Kommunizieren der Änderungen an Benutzer | Ändern der Administratoreinstellungen     
**Erfordert Tests** | Überprüfen von Geschäftsanwendungen, einschließlich Remotezugriffsdiensten |  Manchmal – Testen des Fix im Hinblick auf die Prozesse und Anpassungen |   Nur selten 
**Beispiele für Änderungen** | - Featureupdates: Vereinfachte Supportticketübermittlung und -überprüfung im IT Admin Portal<br>– Neue Features oder Anwendungen: Semi-Annual eines Windows 10-Funktionsupdates | Hotfixes basierend auf den von Kunden gemeldeten Fehlern |  


## <a name="standard-operating-procedures"></a>Standardbetriebsverfahren

Der Microsoft Managed Desktop Service wird von Microsoft in Ihrer Microsoft-Cloud-Instanz implementiert und betrieben, in der Sie möglicherweise andere administrative Aktivitäten durchführen. Microsoft ist ausschließlich für die Einrichtung, Konfiguration und den Betrieb von Microsoft Managed Desktop verantwortlich. 

Bei lokalen Produkten übernimmt Ihre Organisation sämtliche Verantwortung für die Verwaltung von Setup- und Konfigurations- und Betriebsaktivitäten.

Kategorien |    Microsoft wird | Der Kunde wird
--- | --- | ---
Netzwerk (Proxy, Paketprüfung, VPN)  | Empfehlen und planen Sie mit Kunden, um das Risiko für Geschäftsbenutzer zu minimieren. | – Erstellen Sie eine Supportanfrage, die Informationen zu einer geplanten Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Operations bewertet und empfohlen wurde.
Dienstkonten |– Implementieren, sicheres Speichern und Verwalten der Anmeldeinformationen.<br> – Teilen Sie Ihrem Sicherheitsteam nicht autorisierten Zugriff oder die Verwendung dieser Anmeldeinformationen mit. | – Erstellen Sie eine Supportanfrage, die Informationen zu einer geplanten Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Operations bewertet und empfohlen wurde.<br>– Zuweisen von Richtlinien, mehrstufiger Authentifizierung, bedingter Zugriff oder Anwendungsbereitstellung zu den Microsoft Managed Desktop Service-Konten nicht.<br>– Setzen Sie das Kennwort nicht zurück, oder verwenden Sie die Anmeldeinformationen.<br>– Öffnen Sie eine Sev C-Supportanfrage an Microsoft Managed Desktop Operations, wenn verdächtige Aktivitäten in Intune- oder #A0 im Zusammenhang mit diesen Dienstkonten beobachtet werden.
Gerätegruppen | – Implementieren und Verwalten der Mitgliedschaft von Geräten in Microsoft Managed Desktop-Gruppen.<br>– Verwenden Sie die Microsoft Managed Desktop-Gruppen, um die Zuweisung und Freigabe von Konfigurationen und Updates für Geräte zu verwalten. | – Erstellen Sie eine Supportanfrage, die Informationen zu einer geplanten Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Operations bewertet und empfohlen wurde.<br>– Die Mitgliedschaft einer Microsoft Managed Desktop-Gruppe wird nicht geändert.<br>– Verwenden Sie die Gruppen nur zum Zuweisen von Unternehmenszertifikaten für Dienste wie VPN, Windows Hello for Business oder E-Mail-Verschlüsselung oder Wi-Fi Profilkonfiguration.<br>– Wenn co-management vorhanden ist, schließen Sie alle Microsoft Managed Desktop-Gruppen explizit aus, wenn Sie den Configuration Manager-Client bereitstellen.
Richtlinien |  – Implementieren und Verwalten der Microsoft Managed Desktop-Richtlinien, die den Konfigurationsstatus von Geräten innerhalb des Diensts steuern.<br>– Bereitstellen von Updates für Richtlinien oder Windows inkrementell mithilfe von Gerätegruppen.<br> – Explizites Ausschließen von Nicht-Microsoft Managed Desktop-Gruppen. | – Erstellen Sie eine Supportanfrage, die Informationen zu einer geplanten Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Operations bewertet und empfohlen wurde.<br>– Microsoft Managed Desktop-Richtlinien nicht bearbeiten oder Geräten oder Benutzern zuweisen, die nicht vom Microsoft Managed Desktop Service verwaltet werden.
Microsoft Defender für Endpunkt | Überwachen und Untersuchen von Geräten im Rahmen des Microsoft Managed Desktop-Diensts. | – Erstellen Sie eine Supportanfrage, die Informationen zu einer geplanten Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Operations bewertet und empfohlen wurde
Microsoft Store für Unternehmen |  Konfigurieren und verwalten Sie das Windows -Autopilot-Profil für den Microsoft Managed Desktop-Dienst. | – Erstellen Sie eine Supportanfrage, die Informationen zu einer geplanten Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Operations bewertet und empfohlen wurde.<br>– Ändern Sie nicht die Konfiguration des Microsoft Managed Desktop Windows Autopilot-Profils, oder fügen Sie zugewiesene Geräte hinzu bzw. entfernen Sie sie nicht.
Zertifikate | | – Erstellen Sie 60 Tage vor Ablauf eines Zertifikats eine Supportanfrage, und fordern Sie Informationen zu einer geplanten Konfigurationsänderung an, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Operations bewertet und empfohlen wurde.<br>– Aktualisieren Sie alle Zertifikate, die zum Konfigurieren von Zertifikatprofilen, VPN-Profilen und Wi-Fi erforderlich sind.




## <a name="device-wipe-with-factory-reset"></a>Gerätezurücksetzung mit Zurücksetzung auf Werkseinstellungen

Das Microsoft Managed Desktop Operations-Team kann bei Bedarf eine Zurücksetzung auf Werkseinstellungen für Geräte durchführen, die für den Dienst registriert sind. Das Zurücksetzen ist hilfreich, wenn Sie ein Gerät an einen anderen Mitarbeiter senden müssen oder wenn ein Mitarbeiter Ihr Unternehmen verlässt. 

Es gibt einige Anforderungen:

- Ihr globaler Administrator muss eine Serviceanfrage übermitteln.
- Schließen Sie den Computernamen des Geräts in die Anforderung ein.
- Das Benutzerkonto muss sich in Azure AD benennen, bevor wir das Gerät zurücksetzen.

Das Team für verwaltete Desktopvorgänge geht wie folgt vor:

- Suchen des Gerätenamens in Intune
- Senden des Befehls zum Zurücksetzen auf die Werkseinstellungen an das Gerät

>[!NOTE]
>Entfernen Sie das Benutzerkonto nicht aus Azure AD, bevor das Gerät zurückgesetzt wird. Wenn sich der Benutzer nicht in Azure AD befindet, kann Intune den Befehl zum Zurücksetzen auf die Werkseinstellungen nicht an das Gerät senden. 

Das Gerät startet in der "Out-of-Box-Erfahrung", und alle vorinstallierten Anwendungen und Einstellungen werden erneut angewendet. Der Benutzer des Geräts muss erneut Informationen zum anfänglichen Setup bereitstellen. 

Wenn das Gerät zurückgesetzt wurde, können Sie es an eine andere Person in Ihrer Organisation senden. Keine der Daten oder Unternehmensdaten des vorherigen Benutzers ist auf dem Gerät enthalten. Der nächste Benutzer wird den gleichen Prozess wie die vorherige Person mit einem neuen Microsoft Managed Desktop-Gerät durchgehen.

BitLocker ist eine wichtige Komponente der Datensicherheit in diesem Prozess. Mit der BitLocker-Verschlüsselung auf Microsoft Managed Desktop-Geräten bleiben die Daten auf dem Laufwerk auch nach dem Zurücksetzen auf die Werkseinstellungen sicher. Alle Daten, die auf dem Laufwerk gespeichert waren, stehen dem nächsten Benutzer des Geräts nicht zur Verfügung. Weitere Informationen finden Sie in der [BitLocker-Übersicht.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)

Weitere Informationen finden Sie unter Zurücksetzen eines [Geräts über die Werkseinstellungen.](https://docs.microsoft.com/intune/remote-actions/devices-wipe#factory-reset-a-device) 