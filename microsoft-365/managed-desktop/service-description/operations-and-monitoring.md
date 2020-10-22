---
title: Microsoft Managed Desktop-Vorgänge und-Überwachung
description: ''
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
ms.openlocfilehash: 01a43b35d272aaebce4c6866e3edfb04664b1801
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655723"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Desktop-Vorgänge und-Überwachung

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Change Management

In einem Dienstangebot liegt die Verantwortlichkeit für Bereiche wie Wartung der Hardware und Sicherheitsupdates bei dem Dienstanbieter (Microsoft), und nicht bei dem Kunden (Ihnen). Sie müssen jedoch dennoch sicherstellen, dass Drittanbieter-und benutzerdefinierte Software weiterhin wie erwartet funktionieren, wenn Updates ausgeführt werden.

Für lokale Produkte übernimmt Ihre Organisation die gesamte Verantwortung für die Verwaltung von Änderungen.

### <a name="balance-of-responsibility"></a>Haftungs Ausgleich

Responsibility | Microsoft Managed Desktop-Dienst | Microsoft 365-Client Software | Lokale Clients und Server | Drittanbieter-und benutzerdefinierte Software
----- | ----- | ----- | ----- | -----
Bereitstellen neue Funktionalität | Microsoft | Microsoft | In beide Richtungen | Kunde
Testen neuer Features zum Sicherstellen der Qualität |  Microsoft | Microsoft | In beide Richtungen | Kunde
Kommunikation zu neuen Features | In beide Richtungen | In beide Richtungen | In beide Richtungen | Kunde
Integrieren von benutzerdefinierten Software | In beide Richtungen | In beide Richtungen | Kunde | Kunde
Anwenden von Sicherheitsupdates | Microsoft | Microsoft | Kunde | Kunde
Warten von Systemsoftware | Microsoft | Microsoft | Kunde | Kunde
Paket für die Bereitstellung | Microsoft | Microsoft | Kunde | Kunde


### <a name="change-process-overview"></a>Übersicht über den Änderungsprozess

Im folgenden finden Sie eine Zusammenfassung der Art und Weise, wie der Änderungsprozess von Microsoft und Kunden gemeinsam genutzt wird. 



<table>
<tr><th></th><th><p>Rolle von Microsoft:</p></th><th><p>Rolle des Kunden:</p></th></tr>
<tr><td>Vor einer Änderung</td><td><ul><li>Festlegen der Erwartungen an Dienständerungen</li><li>Benachrichtigen Sie Kunden 5 Tage im Voraus über Änderungen, die eine Administratoraktion erfordern.</li><li>Wenden Sie bei Notfalländerungen vor der Benachrichtigung eine Minderung an.</li></ul></td><td><ul><li>Verstehen der zu erwartenden Änderungen und Kommunikation</li><li>Lesen Sie regelmäßig das Microsoft Managed Desktop-Nachrichten Center.</li><li>Überprüfen und Aktualisieren interner Change Management-Prozesse</li><li>Verstehen und Überprüfen der Kompatibilität mit den Anforderungen von Microsoft Managed Desktops. </li><li>Bestätigen und genehmigen bei Bedarf.</li></ul></td></tr><tr><td>Während einer Änderung</td><td><ul><li>Veröffentlichen und Bereitstellen von monatlichen Sicherheits-und nicht sicherheitsrelevanten Updates für Windows 10-und Office 365-Clients.</li><li>Überwachen von Datensignalen und unterstützen von Warteschlangen für Auswirkungen</li></ul></td><td><ul><li>Überprüfen Sie das Microsoft Managed Desktop-Nachrichten Center, und überprüfen Sie weitere Informationen.</li><li>   Nehmen Sie gegebenenfalls erforderliche Aktionen vor, und testen Sie Anwendungen.</li><li>Wenn ein Unterbrechungs-oder Korrektur Szenario vorliegt, erstellen Sie eine Support Anfrage.</li></ul></td></tr><tr><td>Nach einer Änderung</td><td><ul><li>Sammeln von Kundenfeedback, um die Einführung künftiger Änderungen zu verbessern</li><li>Überwachen von Datensignalen und unterstützen von Warteschlangen für Auswirkungen</li></ul></td><td><ul><li>Arbeiten Sie mit Personen in Ihrer Organisation zusammen, um die Änderung zu übernehmen.</li><li>   Überprüfen Sie Änderungs-und Adoptions Verwaltungsprozesse auf Möglichkeiten zur Effizienzsteigerung.</li><li>Geben Sie Allgemeines Feedback und spezifisches Feedback im Feedback Tool für Administratoren an.</li><li>Schulen von Benutzern zum Bereitstellen von App-spezifischem Feedback mithilfe des Windows-Feedback Hubs und der smile-Schaltfläche in Office-Apps.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Änderungstypen

Es gibt verschiedene Arten von Änderungen, die in regelmäßigen Abständen an dem Dienst vorgenommen werden. Der Kommunikationskanal für diese Änderungen und die Aktionen, für die Kunden zuständig sind, sind unterschiedlich.

Nicht alle Änderungen wirken sich gleichermaßen auf die Benutzer aus und erfordern eine Aktion. Einige sind geplant und einige ungeplante (nicht sicherheitsrelevante Updates und Sicherheitsupdates sind in der Regel nicht geplant). Je nach Art der Änderung kann der Kommunikationskanal variieren. In der folgenden Tabelle sind die Arten von Änderungen aufgeführt, die Sie für den Microsoft Managed Desktop-Dienst erwarten können.

|   | Funktionalität |   Nicht sicherheitsrelevante Sicherheitsupdates |  Sicherheit
--- | --- | --- | ---
**Art der Änderung** | -Feature-Updates<br>-Neue Features oder Anwendungen<br>-Veraltete Features | Client-Hotfixes für Probleme | Sicherheitspatches
**Vorankündigung** | 5 Tage Benachrichtigung für Änderungen, die eine Aktion erfordern |    Nein, diese sind in der monatlichen Version enthalten.   | Nein, diese sind in der monatlichen Version enthalten. 
**Kommunikationskanal** | -Nachrichten Center<br>-E-Mail-Benachrichtigung | -Nachrichten Center<br>-E-Mail-Benachrichtigung | -Nachrichten Center<br>-E-Mail-Benachrichtigung
**Globale Administratoraktion erforderlich** | Manchmal |  Nur selten |    Nur selten 
**Typ der Aktion** | Ändern der Einstellungen | Kommunizieren der Änderungen an Benutzer | Ändern der Administratoreinstellungen     
**Erfordert Tests** | Überprüfen von Geschäftsanwendungen, einschließlich RAS-Diensten |  Manchmal – Testen des Fix im Hinblick auf die Prozesse und Anpassungen |   Nur selten 
**Beispiele für Änderungen** | -Feature-Updates: vereinfachte Unterstützung von IT-Verwaltungs Portalen und Überprüfung<br>-Neue Features oder Anwendungen: Semi-Annual Version eines Windows 10-Feature-Updates | Hotfixes basierend auf den von Kunden gemeldeten Fehlern |  


## <a name="standard-operating-procedures"></a>Standard mäßige Betriebsverfahren

Der Microsoft Managed Desktop-Dienst wird von Microsoft in Ihrer Microsoft Cloud-Instanz implementiert und betrieben, in der Sie andere administrative Aktivitäten ausführen können. Microsoft ist ausschließlich für Microsoft Managed Desktop-spezifische Setup, Konfiguration und Betrieb verantwortlich. 

Für lokale Produkte übernimmt Ihre Organisation die gesamte Verantwortung für die Verwaltung von Setup sowie für Konfigurations-und Betriebsaktivitäten.

Categories |    Microsoft wird | Kunde wird
--- | --- | ---
Netzwerk (Proxy, Paketüberprüfung, VPN)  | Beraten und planen Sie Kunden, um Risiken für Geschäftsbenutzer zu minimieren. | -Erstellen Sie eine Supportanfrage, in der Informationen für eine geplante Konfigurationsänderung angefordert werden, einschließlich Konfigurationsdetails, Bereich, Zeitachse und anderer relevanter Details, die von Microsoft überprüft werden sollen.<br>-Wenden Sie nur eine Änderung an, wenn Microsoft Managed Desktop Operations bewertet und empfohlen wurde.
Dienstkonten |-Implementieren, sicher speichern und Verwalten der Anmeldeinformationen.<br> – Kommunizieren Sie nicht autorisierten Zugriff oder die Verwendung dieser Anmeldeinformationen für Ihr Sicherheits Betriebsteam. | -Erstellen Sie eine Supportanfrage, in der Informationen für eine geplante Konfigurationsänderung angefordert werden, einschließlich Konfigurationsdetails, Bereich, Zeitachse und anderer relevanter Details, die von Microsoft überprüft werden sollen.<br>-Wenden Sie nur eine Änderung an, wenn Microsoft Managed Desktop Operations bewertet und empfohlen wurde.<br>-Zuweisen von Richtlinien, mehrstufiger Authentifizierung, bedingtem Zugriff oder Anwendungsbereitstellung zu den Microsoft Managed Desktop-Dienstkonten.<br>-Setzen Sie das Kennwort nicht zurück, oder verwenden Sie die Anmeldeinformationen.<br>-Öffnen Sie eine SEV C-Supportanfrage für Microsoft Managed Desktop Operations, wenn in InTune-oder Azure-Überwachungsprotokollen, die sich auf diese Dienstkonten beziehen, verdächtige Aktivitäten beobachtet werden.
Gerätegruppen | -Implementieren und Verwalten der Mitgliedschaft von Geräten in Microsoft Managed Desktop-Gruppen.<br>-Verwenden Sie die Microsoft Managed Desktop-Gruppen, um die Zuweisung und Freigabe von Konfigurationen und Updates für Geräte zu verwalten. | -Erstellen Sie eine Supportanfrage, in der Informationen für eine geplante Konfigurationsänderung angefordert werden, einschließlich Konfigurationsdetails, Bereich, Zeitachse und anderer relevanter Details, die von Microsoft überprüft werden sollen.<br>-Wenden Sie nur eine Änderung an, wenn Microsoft Managed Desktop Operations bewertet und empfohlen wurde.<br>-Ändern Sie nicht die Mitgliedschaft einer beliebigen Microsoft Managed Desktop-Gruppe.<br>-Verwenden Sie die Gruppen nur zum Zuweisen von Unternehmens Zertifikaten für Dienste wie VPN, Windows Hello for Business oder e-Mail-Verschlüsselung oder für die Konfiguration von Unternehmens Wi-Fi Profilen.<br>– Wenn die gemeinsame Verwaltung vorhanden ist, schließen Sie beim Bereitstellen des Configuration Manager-Clients explizit alle von Microsoft verwalteten Desktop Gruppen aus.
Richtlinien |  -Implementieren und verwalten Sie die Microsoft Managed Desktop-Richtlinien, die den Konfigurationsstatus von Geräten in Service steuern.<br>– Bereitstellen von Updates, Richtlinien oder Fenstern, inkrementelle Verwendung von Gerätegruppen.<br> – Explizite Ausrichtung auf nicht von Microsoft verwaltete Desktop Gruppen ausschließen. | -Erstellen Sie eine Supportanfrage, in der Informationen für eine geplante Konfigurationsänderung angefordert werden, einschließlich Konfigurationsdetails, Bereich, Zeitachse und anderer relevanter Details, die von Microsoft überprüft werden sollen.<br>-Wenden Sie nur eine Änderung an, wenn Microsoft Managed Desktop Operations bewertet und empfohlen wurde.<br>-Nicht bearbeiten oder Zuweisen von Microsoft Managed Desktop-Richtlinien zu Geräten oder Benutzern, die nicht vom Microsoft Managed Desktop-Dienst verwaltet werden.
Microsoft Defender Advanced Threat Protection   | Überwachen und untersuchen von Geräten im Rahmen des Microsoft Managed Desktop-Diensts. | -Erstellen Sie eine Supportanfrage, in der Informationen für eine geplante Konfigurationsänderung angefordert werden, einschließlich Konfigurationsdetails, Bereich, Zeitachse und anderer relevanter Details, die von Microsoft überprüft werden sollen.<br>-Nur eine Änderung anwenden, nachdem Microsoft Managed Desktop Operations bewertet und empfohlen wurde
Microsoft Store für Unternehmen |  Konfigurieren und Verwalten des Windows Autopilot-Profils für den Microsoft Managed Desktop-Dienst. | -Erstellen Sie eine Supportanfrage, in der Informationen für eine geplante Konfigurationsänderung angefordert werden, einschließlich Konfigurationsdetails, Bereich, Zeitachse und anderer relevanter Details, die von Microsoft überprüft werden sollen.<br>-Wenden Sie nur eine Änderung an, wenn Microsoft Managed Desktop Operations bewertet und empfohlen wurde.<br>-Ändern Sie nicht die Konfiguration des Microsoft Managed Desktop-Windows-Autopilot-Profils, oder fügen Sie zugewiesene Geräte hinzu.
Zertifikate | | -Erstellen einer Supportanforderung 60 Tage vor Ablauf eines Zertifikats, Anfordern von Informationen für eine geplante Konfigurationsänderung, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die von Microsoft überprüft werden sollen.<br>-Wenden Sie nur eine Änderung an, wenn Microsoft Managed Desktop Operations bewertet und empfohlen wurde.<br>-Aktualisieren aller Zertifikate, die zum Konfigurieren von Zertifikat Profilen, VPN-Profilen und Wi-Fi Profilen erforderlich sind.




## <a name="device-wipe-with-factory-reset"></a>Gerätezurücksetzung mit Factory-Reset

Das Microsoft Managed Desktop Operations-Team kann bei Bedarf ein werksseitiges Zurücksetzen der in den Dienst eingeschriebenen Geräte durchführen. Dies ist hilfreich, wenn Sie einem anderen Mitarbeiter ein Gerät geben müssen oder wenn ein Mitarbeiter Ihr Unternehmen verlässt. 

Es gibt einige Voraussetzungen:

- Ihr globaler Administrator muss eine Serviceanfrage übermitteln.
- Schließen Sie den Computernamen des Geräts in die Anforderung ein.
- Das Benutzerkonto muss sich in Azure AD befinden, bevor das Gerät zurückgesetzt wird.

Das Team für verwaltete Desktop Vorgänge führt die folgenden Aktionen aus:

- Nachschlagen des Gerätenamens in InTune
- Senden des Befehls "Factory Reset" an das Gerät

>[!NOTE]
>Entfernen Sie das Benutzerkonto nicht aus Azure AD, bevor das Gerät zurückgesetzt wird. Wenn sich der Benutzer nicht in Azure AD befindet, kann InTune den Factory Reset-Befehl nicht an das Gerät senden. 

Das Gerät startet in der "Out-of-Box"-Umgebung, und alle vorinstallierten Anwendungen und Einstellungen werden erneut angewendet. Der Benutzer des Geräts muss erneut erste Setupinformationen bereitstellen. 

Wenn das Gerät zurückgesetzt wurde, können Sie es an eine andere Person in Ihrer Organisation übergeben. Keine der Daten oder Unternehmensdaten des vorherigen Benutzers befinden sich auf dem Gerät. Der nächste Benutzer durchläuft denselben Vorgang, den die vorherige Person mit einem neuen von Microsoft verwalteten Desktop-Gerät ausgeführt hat.

BitLocker ist eine wichtige Komponente der Datensicherheit in diesem Prozess. Bei der BitLocker-Verschlüsselung auf Microsoft Managed Desktop-Geräten bleiben Daten auf dem Laufwerk auch dann sicher, wenn das Gerät als Factory zurückgesetzt wurde. Alle Daten, die sich auf dem Laufwerk befanden, sind für den nächsten Benutzer des Geräts nicht verfügbar. Weitere Informationen finden Sie unter [Übersicht über BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).

Weitere Informationen finden Sie unter [Factory Reset a Device](https://docs.microsoft.com/intune/remote-actions/devices-wipe#factory-reset-a-device). 