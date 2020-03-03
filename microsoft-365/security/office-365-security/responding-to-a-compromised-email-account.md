---
title: Reagieren auf ein angegriffenes E-Mail-Konto in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom: TopSMBIssues
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Erfahren Sie, wie Sie ein angegriffenes E-Mail-Konto in Office 365 erkennen und darauf reagieren.
ms.openlocfilehash: b19d48046834e3f1387490774babb40dcbd92acc
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372483"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>Reagieren auf ein angegriffenes E-Mail-Konto in Office 365

**Zusammenfassung** Erfahren Sie, wie Sie ein angegriffenes E-Mail-Konto in Office 365 erkennen und darauf reagieren.

## <a name="what-is-a-compromised-email-account-in-office-365"></a>Was ist ein angegriffenes E-Mail-Konto in Office 365?

Der Zugriff auf Office 365-Postfächer, Daten und andere Dienste wird mithilfe von Anmeldeinformationen gesteuert, z. B. einem Benutzernamen und einem Kennwort oder einer PIN. Wenn es einer anderen Person gelingt, diese Anmeldeinformationen zu stehlen, gelten die Anmeldeinformationen als kompromittiert. Mit ihnen kann sich der Angreifer als der ursprüngliche Benutzer anmelden und unerlaubte Aktionen ausführen.
Mit den gestohlenen Anmeldeinformationen kann der Angreifer zudem auf das Office 365-Postfach des Benutzers sowie auf SharePoint-Ordner oder -Dateien im OneDrive des Benutzers zugreifen. Angreifer senden häufig E-Mails im Namen des ursprünglichen Benutzers an Empfänger innerhalb und außerhalb der Organisation. Wenn der Angreifer Daten an externe Empfänger sendet, wird dies als Daten-Exfiltration bezeichnet.

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>Symptome eines angegriffenen Office 365-E-Mail-Kontos

Benutzer stellen möglicherweise ungewöhnliche Aktivitäten in ihren Office 365-Postfächern fest und melden diese. Hier sind einige häufige Symptome:

- Verdächtige Aktivitäten, z. B. fehlende oder gelöschte E-Mails.

- Andere Benutzer haben möglicherweise E-Mails von dem angegriffenen Konto erhalten, ohne dass die entsprechende E-Mail im Ordner **Gesendete Elemente** des Absenders vorhanden ist.

- Das Vorhandensein von Posteingangsregeln, die nicht vom entsprechenden Benutzer oder Administrator erstellt wurden. Diese Regeln können automatisch E-Mails an unbekannte Adressen weiterleiten oder sie in die Ordner **Notizen**, **Junk-E-Mail** oder **RSS-Abonnements** verschieben.

- Der Anzeigename des Benutzers wurde möglicherweise in der globalen Adressliste geändert.

- Es können keine E-Mails aus dem Postfach des Benutzers gesendet werden.

- Die Ordner „Gesendete Elemente“ oder „Gelöschte Elemente“ in Microsoft Outlook oder Outlook im Web (früher als Outlook Web App bezeichnet) enthalten Nachrichten, die häufig im Zusammenhang mit gehackten Kontos stehen, z. B. „Ich sitze in London fest, sende Geld.“

- Ungewöhnliche Profiländerungen, z. B. wurden der Name, die Telefonnummer oder die Postleitzahl aktualisiert.

- Ungewöhnliche Änderungen der Anmeldeinformationen, z. B. sind mehrere Kennwortänderungen erforderlich.

- Eine E-Mail-Weiterleitung wurde kürzlich hinzugefügt.

- Eine ungewöhnliche Signatur wurde kürzlich hinzugefügt, z. B. eine gefälschte Banksignatur oder eine Signatur für ein verschreibungspflichtiges Medikament.

Wenn ein Benutzer eines der oben genannten Symptome meldet, sollten Sie weitere Untersuchungen durchführen. Das Microsoft 365 Security & Compliance Center und das Azure-Portal bieten Tools, mit denen Sie die Aktivität eines Benutzerkontos untersuchen können, von dem Sie vermuten, dass es angegriffen wurde.

- **Office 365 Unified Audit Logs im Security & Compliance Center**: Überprüfen Sie alle Aktivitäten des verdächtigen Kontos, indem Sie die Ergebnisse nach dem Datumsbereich (unmittelbar vor dem Auftreten der verdächtigen Aktivität bis zum aktuellen Datum) filtern. Filtern Sie die Aktivitäten nicht während der Suche.

- **Office 365-Administratorüberwachungsprotokolle im EAC**: In Exchange Online können Sie im Exchange Admin Center (EAC) Einträge im Administratorüberwachungsprotokoll durchsuchen und anzeigen. Im Administratorüberwachungsprotokoll werden bestimmte Aktionen aufgezeichnet, die basierend auf den jeweiligen Exchange Online PowerShell-Cmdlets von Administratoren und Benutzern mit Administratorrechten ausgeführt werden. In Einträgen im Administratorüberwachungsprotokoll finden Sie Informationen dazu, welches Cmdlet ausgeführt wurde, welche Parameter verwendet wurden, wer das Cmdlet ausgeführt hat und welche Objekte betroffen sind.

- **Azure AD-Anmeldeprotokolle und andere Risikoberichte im Azure AD-Portal**: Überprüfen Sie die Werte in den folgenden Spalten:

  - IP-Adresse überprüfen

  - Anmeldeorte

  - Anmeldezeiten

  - Anmeldeerfolge oder -fehler

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>Sichern und Wiederherstellen der E-Mail-Funktion für ein vermutlich angegriffenes Office 365-Konto und -Postfach

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Selbst nachdem Sie wieder Zugriff auf Ihr Konto haben, hat der Angreifer möglicherweise versteckte Zugangsmöglichkeiten hinzugefügt, durch die er wieder die Kontrolle über das Konto übernehmen kann.

Sie müssen so früh wie möglich die folgenden Schritte durchführen, um wieder Zugriff auf Ihr Konto zu erhalten. So stellen Sie sicher, dass der Angreifer nicht wieder die Kontrolle über Ihr Konto übernimmt. Mit diesen Schritten können Sie alle versteckten Zugangsmöglichkeiten entfernen, die der Angreifer möglicherweise zu Ihrem Konto hinzugefügt hat. Nachdem Sie diese Schritte ausgeführt haben, empfehlen wir, dass Sie einen Virusscan durchführen, um sicherzustellen, dass Ihr Computer nicht beeinträchtigt ist.

### <a name="step-1-reset-the-users-password"></a>Schritt 1: Setzen Sie das Benutzerkennwort zurück.

> [!WARNING]
> Senden Sie das neue Kennwort nicht per E-Mail an den vorgesehenen Benutzer, da der Angreifer weiterhin Zugriff auf das Postfach hat.

1. Befolgen Sie die Anweisungen zu „Zurücksetzen eines Office 365 Business-Kennworts für eine andere Person“ unter [Zurücksetzen von Office 365 Business-Kennwörtern](https://docs.microsoft.com/office365/admin/add-users/reset-passwords).

**Hinweise**:

- Stellen Sie sicher, dass das Kennwort sicher ist und dass es Groß- und Kleinbuchstaben, mindestens eine Zahl und mindestens ein Sonderzeichen enthält.

- Verwenden Sie nicht eines Ihrer letzten fünf Kennwörter wieder. Obwohl die Kennwortverlaufsanforderung die Verwendung eines aktuelleren Kennworts zulässt, sollten Sie eines auswählen, das der Angreifer nicht erraten kann.

- Wenn Ihre lokale Identität mit Office 365 verbunden ist, müssen Sie das Kennwort lokal ändern und dann Ihren Administrator über den Angriff benachrichtigen.

> [!TIP]
> Es wird dringend empfohlen, dass Sie die mehrstufige Authentifizierung (MFA) aktivieren, um Angriffe zu verhindern, insbesondere für Konten mit Administratorrechten.  Weitere Informationen zu MFA finden Sie [hier](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Schritt 2: Entfernen Sie verdächtige E-Mail-Weiterleitungsadressen.

1. Öffnen Sie **Microsoft 365 Admin Center > Aktive Benutzer**.

2. Suchen Sie das betroffene Benutzerkonto und erweitern Sie **E-Mail-Einstellungen**.

3. Klicken Sie für **E-Mail-Weiterleitung** auf **Bearbeiten**.

4. Entfernen Sie verdächtige Weiterleitungsadressen.

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>Schritt 3: Entfernen Sie verdächtige Posteingangsregeln.

1. Melden Sie sich beim Postfach des Benutzers mithilfe von Outlook im Web an.

2. Klicken Sie auf das Zahnradsymbol, und klicken Sie auf **E-Mail**.

3. Klicken Sie auf **Posteingangs- und Aufräumregeln**, und überprüfen Sie die Regeln.

4. Deaktivieren oder löschen Sie verdächtige Regeln.

### <a name="step-4-unblock-the-user-from-sending-mail"></a>Schritt 4: Sorgen Sie dafür, dass der Benutzer wieder E-Mails senden kann.

Wenn das vermutlich angegriffene Postfach unerlaubt zum Senden von Spam-E-Mails verwendet wurde, ist es wahrscheinlich, dass das Senden von E-Mails aus dem Postfach gesperrt wurde.

Um die Sperre aufzuheben, führen Sie die Schritte unter [Entfernen von Benutzern, Domänen oder IP-Adressen aus einer Sperrliste nach dem Senden von Spamnachrichten](removing-user-from-restricted-users-portal-after-spam.md) durch.

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>Schritt 5 (optional): Sperren Sie die Anmeldung beim Benutzerkonto.

> [!IMPORTANT]
> Sie können die Anmeldung bei dem vermutlich angegriffenen Konto sperren, bis Sie glauben, dass es sicher ist, den Zugriff wieder zu erlauben.

1. Gehen Sie zum Microsoft 365 Admin Center.

2. Wählen Sie im Microsoft 365 Admin Center, **Benutzer** aus.

3. Wählen Sie zuerst den Mitarbeiter aus, den Sie blockieren möchten, und wählen Sie dann im Benutzerbereich neben **Anmeldestatus** die Option **Bearbeiten** aus.

4. Wählen Sie im Bereich **Anmeldestatus** die Option **Anmeldung blockiert** und dann **Speichern** aus.

5. Erweitern Sie im Admin Center unten links im Navigationsbereich die Struktur von **Admin Center**, und wählen Sie **Exchange** aus.

6. Navigieren Sie im Exchange Admin Center zu **Empfänger > Postfächer**.

7. Wählen Sie den Benutzer aus, klicken Sie auf der Seite der Benutzereigenschaften unter **Mobile Geräte** auf **Exchange ActivcSync deaktivieren** und **OWA für Geräte deaktivieren**, und wählen Sie dann für beide Optionen **Ja** aus.

8. Klicken Sie unter **E-Mail-Konnektivität** auf **Deaktivieren**, und wählen Sie **Ja** aus.

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Schritt 6 (optional): Entfernen Sie das vermutlich angegriffen Konto aus allen Administratorrollengruppen.

> [!NOTE]
> Die Mitgliedschaft bei der Administratorrollengruppe kann wiederhergestellt werden, nachdem das Konto gesichert wurde.

1. Melden Sie sich mit einem globalen Administratorkonto beim Microsoft 365 Admin Center an, und öffnen Sie **Aktive Benutzer**.

2. Suchen Sie nach dem vermutlich angegriffenen Konto und überprüfen Sie manuell, ob dem Konto Administratorrollen zugewiesen sind.

3. Öffnen Sie das **Security & Compliance Center**.

4. Klicken Sie auf **Berechtigungen**.

5. Überprüfen Sie manuell die Rollengruppen, um festzustellen, ob das vermutlich angegriffene Konto einer dieser Gruppen angehört.  Wenn er auf:

   a. Klicken Sie auf die Rollengruppe, und klicken Sie auf **Rollengruppe bearbeiten**.

   b. Klicken Sie auf **Mitglieder auswählen** und **Bearbeiten** zum Entfernen des Benutzers aus der Rollengruppe.

6. Öffnen Sie das **Exchange Admin Center**.

7. Klicken Sie auf **Berechtigungen**.

8. Überprüfen Sie manuell die Rollengruppen, um festzustellen, ob das vermutlich angegriffene Konto einer dieser Gruppen angehört. Wenn er auf:

   a. Klicken Sie auf die Rollengruppe, und klicken Sie auf **Bearbeiten**.

   b. Verwenden Sie den Abschnitt **Mitglieder** zum Entfernen des Benutzers aus der Rollengruppe.

### <a name="step-7-optional-additional-precautionary-steps"></a>Schritt 7 (optional): Zusätzliche Vorsichtsmaßnahmen

1. Stellen Sie sicher, dass Sie die gesendeten Elemente überprüfen. Möglicherweise müssen Sie Personen in Ihrer Kontaktliste informieren, dass Ihr Konto manipuliert wurde. Angreifer können sie um Geld gebeten haben, z. B. unter dem Vorwand, dass Sie in einem anderen Land in einer Notsituation sind und Geld benötigen, oder der Angreifer hat ihnen möglicherweise einen Virus gesendet, um auch ihren Computer anzugreifen.

2. Alle anderen Dienste, die dieses Exchange-Konto als alternatives E-Mail-Konto verwendet haben, wurden möglicherweise auch manipuliert. Führen Sie zunächst diese Schritte für Ihr Office 365-Abonnement aus, und führen Sie sie dann für Ihre anderen Konten aus.

3. Stellen Sie sicher, dass Ihre Kontaktinformationen, z. B. Telefonnummern und Adressen, richtig sind.

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Sichern von Office 365 wie ein Profi für Internetsicherheit

Ihr Office 365-Abonnement bietet eine Reihe von leistungsfähigen Funktionen für Sicherheit, die Sie zum Schutz Ihrer Daten und Ihrer Benutzer verwenden können.  Verwenden Sie die [Office 365-Sicherheits-Roadmap: Top-Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](security-roadmap.md) zum Implementieren von empfohlenen Microsoft-Best-Practices für den Schutz Ihres Office 365-Mandanten.

- Aufgaben, die in den ersten 30 Tagen ausgeführt werden sollten.  Diese sind unmittelbar gültig und haben nur geringe Auswirkungen für die Benutzer.

- Aufgaben, die innerhalb von 90 Tagen ausgeführt werden sollten. Diese erfordern etwas mehr Zeit für Planung und Implementierung, stärken die Sicherheit Ihres Unternehmens jedoch erheblich.

- Über 90 Tage hinaus. Diese Verbesserungen werden in den ersten 90 Tagen Ihrer Arbeit umgesetzt.

## <a name="see-also"></a>Siehe auch

- [Erkennen und Korrigieren von Outlook-Regeln und benutzerdefinierten Formularen für Einschleusungsangriffe in Office 365](detect-and-remediate-outlook-rules-forms-attack.md)

- [Internet Crime Complaint Center](https://www.ic3.gov/preventiontips.aspx)

- [Securities and Exchange Commission – Phishing-Betrug](https://www.sec.gov/investor/pubs/phishing.htm)

- Um Spam direkt an Microsoft und Ihren Admin zu melden, [verwenden Sie das Report Message-Add-In](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
