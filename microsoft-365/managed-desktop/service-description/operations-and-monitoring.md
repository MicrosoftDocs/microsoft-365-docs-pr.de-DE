---
title: Microsoft Managed Desktop Vorgänge und Überwachung
description: Wer erledigt dies für verschiedene Änderungsprozesse
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
ms.openlocfilehash: e8fc583feb0d1ae1fc4ec4aa970b9dc19ae46fd9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286897"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Desktop Vorgänge und Überwachung

<!-- Operations and monitoring: -->

## <a name="change-management"></a>Change Management

In einem Dienstangebot liegt die Verantwortlichkeit für Bereiche wie Wartung der Hardware und Sicherheitsupdates bei dem Dienstanbieter (Microsoft), und nicht bei dem Kunden (Ihnen). Sie müssen jedoch weiterhin sicherstellen, dass nicht von Microsoft stammende und benutzerdefinierte Software weiterhin wie erwartet funktionieren, wenn Updates bereitgestellt werden.

Bei lokalen Produkten übernimmt Ihre Organisation die gesamte Verantwortung für die Verwaltung von Änderungen.

### <a name="balance-of-responsibility"></a>Lastenausgleich

Zuständigkeit | Microsoft Managed Desktop Dienst | Microsoft 365-Clientsoftware | Lokale Clients und Server | Nicht-Microsoft- und benutzerdefinierte Software
----- | ----- | ----- | ----- | -----
Bereitstellen neue Funktionalität | Microsoft | Microsoft | In beide Richtungen | Kunde
Testen neuer Features zum Sicherstellen der Qualität |  Microsoft | Microsoft | In beide Richtungen | Kunde
Kommunikation zu neuen Features | In beide Richtungen | In beide Richtungen | In beide Richtungen | Kunde
Integrieren von benutzerdefinierten Software | In beide Richtungen | In beide Richtungen | Kunde | Kunde
Anwenden von Sicherheitsupdates | Microsoft | Microsoft | Kunde | Kunde
Warten von Systemsoftware | Microsoft | Microsoft | Kunde | Kunde
Paket für die Bereitstellung | Microsoft | Microsoft | Kunde | Kunde

### <a name="change-process-overview"></a>Übersicht über den Änderungsprozess

Hier ist eine Zusammenfassung, wie der Änderungsprozess zwischen Microsoft und Den Kunden geteilt wird: 

<table>
<tr><th></th><th><p>Rolle von Microsoft:</p></th><th><p>Rolle des Kunden:</p></th></tr>
<tr><td>Vor einer Änderung</td><td><ul><li>Festlegen der Erwartungen an Dienständerungen</li><li>Benachrichtigen Sie Kunden 5 Tage im Voraus über Änderungen, die eine Administratoraktion erfordern.</li><li>Wenden Sie für Notfalländerungen vor der Benachrichtigung eine Gegenmaßnahme an.</li></ul></td><td><ul><li>Verstehen der zu erwartenden Änderungen und Kommunikation</li><li>Lesen Sie regelmäßig Microsoft Managed Desktop Nachrichtencenter.</li><li>Überprüfen und Aktualisieren interner Change Management-Prozesse</li><li>Verstehen und Überprüfen der Einhaltung Microsoft Managed Desktop Anforderungen. </li><li>Bestätigen und genehmigen Sie, falls erforderlich.</li></ul></td></tr><tr><td>Während einer Änderung</td><td><ul><li>Veröffentlichen und Bereitstellen monatlicher und nicht sicherheitsrelevanter Updates für Windows 10- und Office 365-Clients.</li><li>Überwachen Sie Datensignale und Supportwarteschlangen auf Auswirkungen.</li></ul></td><td><ul><li>Überprüfen Sie das Microsoft Managed Desktop Nachrichtencenter, und überprüfen Sie alle zusätzlichen Informationen.</li><li>Führen Sie ggf. alle erforderlichen Maßnahmen aus, und testen Sie Anwendungen.</li><li>Wenn ein Unterbrechungs-/Behebungsszenario auftritt, erstellen Sie eine Supportanfrage.</li></ul></td></tr><tr><td>Nach einer Änderung</td><td><ul><li>Sammeln Sie Kundenfeedback, um das Rollout zukünftiger Änderungen zu verbessern.</li><li>Überwachen Sie Datensignale und Supportwarteschlangen auf Auswirkungen.</li></ul></td><td><ul><li>Arbeiten Sie mit Personen in Ihrer Organisation, um die Änderung zu übernehmen.</li><li>Überprüfen Sie die Änderungs- und Einführungsverwaltungsprozesse, um Effizienz zu erzielen.</li><li>Geben Sie allgemeines Feedback und spezifisches Feedback im Tool für Administratorfeedback.</li><li>Schulen Sie Benutzer, app-spezifisches Feedback mithilfe der Windows-Feedback-Hub und der Schaltfläche "Stellen" in Office Apps bereitzustellen.</li></ul></td></tr>
<table> 

### <a name="change-types"></a>Änderungstypen

Es gibt verschiedene Arten von Änderungen, die wir regelmäßig an dem Dienst vornehmen. Der Kommunikationskanal für diese Änderungen und die Aktionen, für die Sie verantwortlich sind, variieren.

Nicht alle Änderungen wirken sich gleichermaßen auf die Benutzer aus und erfordern eine Aktion. Einige sind geplant und einige von ihnen nicht geplant (nicht sicherheitsrelevante Updates und Sicherheitsupdates sind in der Regel nicht geplant). Je nach Art der Änderung kann der Kommunikationskanal variieren. In der folgenden Tabelle sind die Arten von Änderungen aufgeführt, die Sie für den Microsoft Managed Desktop-Dienst erwarten können.

|   | Funktionalität | Nicht sicherheitsrelevante Sicherheitsupdates | Sicherheit
--- | --- | --- | ---
**Art der Änderung** | – Featureupdates<br>– Neue Features oder Anwendungen<br>– Veraltete Features | Client-Hotfixes für Probleme | Sicherheitsupdates
**Vorankündigung** | 5 Tage Benachrichtigung für Änderungen, die eine Aktion erfordern | Nein, solche Änderungen sind in der monatlichen Version enthalten | Nein, Änderungen sind in der monatlichen Version enthalten 
**Kommunikationskanal** | - Nachrichtencenter<br>– E-Mail-Warnung | - Nachrichtencenter<br>– E-Mail-Warnung | - Nachrichtencenter<br>– E-Mail-Warnung
**Erfordert eine globale Administratoraktion** | Manchmal | Nur selten | Nur selten 
**Aktionstyp** | Ändern der Einstellungen | Kommunizieren der Änderungen an Benutzer | Ändern der Administratoreinstellungen  
**Erfordert Tests** | Überprüfen von Geschäftsanwendungen, einschließlich Remotezugriffsdiensten | Manchmal – Testen des Fix im Hinblick auf die Prozesse und Anpassungen | Nur selten 
**Beispiele für Änderungen** | - Featureupdates: Vereinfachtes Übermitteln und Überprüfen von Supporttickets im IT-Verwaltungsportal<br>– Neue Features oder Anwendungen: Semi-Annual Version eines Windows 10 Featureupdates | Hotfixes basierend auf den von Kunden gemeldeten Fehlern |

## <a name="standard-operating-procedures"></a>Standardvorgehensweisen

Der Microsoft Managed Desktop Dienst wird von Microsoft in Ihrer Microsoft-Cloudinstanz implementiert und betrieben, in der Sie möglicherweise andere administrative Aktivitäten ausführen. Microsoft ist allein für Microsoft Managed Desktop-spezifische Einrichtung, Konfiguration und Betrieb verantwortlich.

Bei lokalen Produkten übernimmt Ihre Organisation die gesamte Verantwortung für die Verwaltung der Einrichtung sowie der Konfiguration und der betrieblichen Aktivitäten.

Kategorien | Microsoft wird | Der Kunde wird
--- | --- | ---
Netzwerk (Proxy, Paketüberprüfung, VPN)  | Beraten und planen Sie mit Kunden, um risiken für Geschäftsbenutzer zu minimieren. | – Erstellen Sie eine Supportanfrage, die Informationen zu einer geplanten Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Vorgänge bewertet und empfohlen wurde.
Dienstkonten |– Implementieren, sicheres Speichern und Verwalten der Anmeldeinformationen.<br> – Teilen Sie Ihrem Sicherheitsteam den nicht autorisierten Zugriff oder die Verwendung dieser Anmeldeinformationen mit. | – Erstellen Sie eine Supportanfrage, die Informationen zu einer geplanten Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Vorgänge bewertet und empfohlen wurde.<br>– Weisen Sie den Microsoft Managed Desktop Dienstkonten keine Richtlinie, mehrstufige Authentifizierung, bedingten Zugriff oder Anwendungsbereitstellung zu.<br>– Setzen Sie das Kennwort nicht zurück oder verwenden Sie die Anmeldeinformationen.<br>– Öffnen Sie eine Sev C-Supportanfrage für Microsoft Managed Desktop Vorgänge, wenn verdächtige Aktivitäten in Intune- oder Azure-Überwachungsprotokollen im Zusammenhang mit diesen Dienstkonten beobachtet werden.
Gerätegruppen | – Implementieren und Verwalten der Mitgliedschaft von Geräten in Microsoft Managed Desktop-Gruppen.<br>– Verwenden Sie die Microsoft Managed Desktop-Gruppen, um die Zuweisung und Freigabe von Konfiguration und Updates für Geräte zu verwalten. | – Erstellen Sie eine Supportanfrage, die Informationen zu einer geplanten Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Vorgänge bewertet und empfohlen wurde.<br>– Die Mitgliedschaft in einer Microsoft Managed Desktop Gruppe wird nicht geändert.<br>– Verwenden Sie die Gruppen nur zum Zuweisen von Unternehmenszertifikaten für Dienste wie VPN, Windows Hello für Unternehmen oder E-Mail-Verschlüsselung oder unternehmenseigene Wi-Fi Profilkonfiguration.<br>– Wenn co-management vorhanden ist, schließen Sie explizit alle Microsoft Managed Desktop-Gruppen bei der Bereitstellung des Configuration Manager-Clients aus.
Richtlinien | – Implementieren und Verwalten der Microsoft Managed Desktop Richtlinien, die den Konfigurationsstatus von Geräten innerhalb des Diensts steuern.<br>– Bereitstellen von Updates für Richtlinien oder Windows inkrementell mithilfe von Gerätegruppen.<br> – Explizites Ausschließen der Zielgruppenadressierung für Nicht-Microsoft Managed Desktop-Gruppen. | – Erstellen Sie eine Supportanfrage, die Informationen zu einer geplanten Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Vorgänge bewertet und empfohlen wurde.<br>– Microsoft Managed Desktop Richtlinien nicht bearbeiten oder Geräten oder Benutzern zuweisen, die nicht vom Microsoft Managed Desktop Dienst verwaltet werden.
Microsoft Defender für Endpunkt | Überwachen und Untersuchen von Geräten im Rahmen des Microsoft Managed Desktop Diensts. | – Erstellen Sie eine Supportanfrage, die Informationen zu einer geplanten Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Vorgänge bewertet und empfohlen wurden.
Microsoft Store für Unternehmen | Konfigurieren und verwalten Sie das Windows Autopilot-Profils für den Microsoft Managed Desktop Dienst. | – Erstellen Sie eine Supportanfrage, die Informationen zu einer geplanten Konfigurationsänderung anfordert, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Vorgänge bewertet und empfohlen wurde.<br>– Die Konfiguration des Microsoft Managed Desktop Windows Autopilot-Profils nicht ändern oder zugewiesene Geräte hinzufügen/entfernen.
Zertifikate | | – Erstellen Sie eine Supportanfrage 60 Tage vor Ablauf eines Zertifikats, und fordern Sie Informationen zu einer geplanten Konfigurationsänderung an, einschließlich Konfigurationsdetails, Umfang, Zeitachse und anderer relevanter Details, die Microsoft überprüfen kann.<br>– Wenden Sie eine Änderung nur an, nachdem Microsoft Managed Desktop Vorgänge bewertet und empfohlen wurde.<br>– Aktualisieren Sie alle Zertifikate, die zum Konfigurieren von Zertifikatprofilen, VPN-Profilen und Wi-Fi Profilen erforderlich sind.

## <a name="device-wipe-with-factory-reset"></a>Zurücksetzen des Geräts mit Zurücksetzung auf die Werkseinstellungen

Das Microsoft Managed Desktop Operations-Team kann bei Bedarf eine Zurücksetzung von Geräten durchführen, die im Dienst registriert sind. Das Zurücksetzen ist hilfreich, wenn Sie einem anderen Mitarbeiter ein Gerät zuweisen müssen oder wenn ein Mitarbeiter Ihr Unternehmen verlässt.

Es gibt einige Anforderungen:

- Ihr globaler Administrator muss eine Serviceanfrage senden.
- Schließen Sie den Computernamen des Geräts in die Anforderung ein.
- Das Benutzerkonto muss sich in Azure AD befinden, bevor wir das Gerät zurücksetzen.

Das Team für verwaltete Desktopvorgänge führt die folgenden Schritte aus:

- Nachschlagen des Gerätenamens in Intune
- Senden des Zurücksetzungsbefehls auf die Werkseinstellungen an das Gerät

> [!NOTE]
> Entfernen Sie das Benutzerkonto nicht aus Azure AD, bevor das Gerät zurückgesetzt wird. Wenn sich der Benutzer nicht in Azure AD befindet, kann Intune den Befehl zum Zurücksetzen der Werkseinstellungen nicht an das Gerät senden.

Das Gerät startet in der "Out-of-Box-Umgebung", und alle vorinstallierten Anwendungen und Einstellungen werden erneut angewendet. Der Benutzer des Geräts muss erneut Informationen zur Ersteinrichtung bereitstellen. 

Wenn das Gerät zurückgesetzt wurde, können Sie es einer anderen Person in Ihrer Organisation zuweisen. Keine daten des vorherigen Benutzers oder Unternehmensdaten sind auf dem Gerät vorhanden. Der nächste Benutzer durchläuft denselben Prozess wie die vorherige Person mit einem neuen Microsoft Managed Desktop Gerät.

BitLocker ist eine wichtige Komponente der Datensicherheit in diesem Prozess. Mit der BitLocker-Verschlüsselung auf Microsoft Managed Desktop Geräten bleiben Daten auf dem Laufwerk auch nach dem Zurücksetzen auf die Werkseinstellungen sicher. Alle Daten, die sich auf dem Laufwerk befanden, sind für den nächsten Benutzer des Geräts nicht verfügbar. Weitere Informationen finden Sie in der [BitLocker-Übersicht.](/windows/security/information-protection/bitlocker/bitlocker-overview)

Weitere Informationen finden Sie unter ["Zurücksetzen eines Geräts auf Werkseinstellungen".](/intune/remote-actions/devices-wipe#factory-reset-a-device)
