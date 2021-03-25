---
title: Auf ein kompromittiertes E-Mail-Konto reagieren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
search.appverid:
- MET150
description: Erfahren Sie, wie Sie ein angegriffenes E-Mail-Konto mit den in Microsoft 365 verfügbaren Tools erkennen und darauf reagieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1bf2a5dbc7e1fdd447baf76fd051abff88b4b30
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205714"
---
# <a name="responding-to-a-compromised-email-account"></a>Auf ein kompromittiertes E-Mail-Konto reagieren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Zusammenfassung** Erfahren Sie, wie Sie ein angegriffenes E-Mail-Konto in Microsoft 365 erkennen und darauf reagieren.

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a>Was ist ein angegriffenes E-Mail-Konto in Microsoft 365?

Der Zugriff auf Microsoft 365-Postfächer, Daten und andere Dienste wird mithilfe von Anmeldeinformationen gesteuert, z. B. einem Benutzernamen und einem Kennwort oder einer PIN. Wenn es einer anderen Person gelingt, diese Anmeldeinformationen zu stehlen, gelten die Anmeldeinformationen als kompromittiert. Mit ihnen kann sich der Angreifer als der ursprüngliche Benutzer anmelden und unerlaubte Aktionen ausführen.
Mit den gestohlenen Anmeldeinformationen kann der Angreifer zudem auf das Microsoft 365-Postfach des Benutzers sowie auf SharePoint-Ordner oder -Dateien im OneDrive des Benutzers zugreifen. Angreifer senden häufig E-Mails im Namen des ursprünglichen Benutzers an Empfänger innerhalb und außerhalb der Organisation. Wenn der Angreifer Daten an externe Empfänger sendet, wird dies als Daten-Exfiltration bezeichnet.

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a>Symptome eines angegriffenen Microsoft-E-Mail-Kontos

Benutzer stellen möglicherweise ungewöhnliche Aktivitäten in ihren Microsoft 365-Postfächern fest und melden diese. Hier sind einige häufige Symptome:

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

- **Unified Audit Logs im Security & Compliance Center**: Überprüfen Sie alle Aktivitäten des verdächtigen Kontos, indem Sie die Ergebnisse nach dem Datumsbereich (unmittelbar vor dem Auftreten der verdächtigen Aktivität bis zum aktuellen Datum) filtern. Filtern Sie die Aktivitäten nicht während der Suche.

- **Administratorüberwachungsprotokolle im EAC**: In Exchange Online können Sie im Exchange Admin Center (EAC) Einträge im Administratorüberwachungsprotokoll durchsuchen und anzeigen. Im Administratorüberwachungsprotokoll werden bestimmte Aktionen aufgezeichnet, die basierend auf den jeweiligen Exchange Online PowerShell-Cmdlets von Administratoren und Benutzern mit Administratorrechten ausgeführt werden. In Einträgen im Administratorüberwachungsprotokoll finden Sie Informationen dazu, welches Cmdlet ausgeführt wurde, welche Parameter verwendet wurden, wer das Cmdlet ausgeführt hat und welche Objekte betroffen sind.

- **Azure AD-Anmeldeprotokolle und andere Risikoberichte im Azure AD-Portal**: Überprüfen Sie die Werte in den folgenden Spalten:

  - IP-Adresse überprüfen
  - Anmeldeorte
  - Anmeldezeiten
  - Anmeldeerfolge oder -fehler

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a>Sichern und Wiederherstellen der E-Mail-Funktion für ein vermutlich angegriffenes Microsoft 365-Konto und -Postfach

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Selbst nachdem Sie wieder Zugriff auf Ihr Konto haben, hat der Angreifer möglicherweise versteckte Zugangsmöglichkeiten hinzugefügt, durch die er wieder die Kontrolle über das Konto übernehmen kann.

Sie müssen so schnell wie möglich alle folgenden Schritte ausführen, um wieder Zugriff auf Ihr Konto zu erhalten. So stellen Sie sicher, dass der Angreifer nicht wieder die Kontrolle über Ihr Konto übernimmt. Mit diesen Schritten können Sie alle versteckten Zugangsmöglichkeiten entfernen, die der Angreifer möglicherweise zu Ihrem Konto hinzugefügt hat. Nachdem Sie diese Schritte ausgeführt haben, empfehlen wir, dass Sie einen Virenscan durchführen, um sicherzustellen, dass Ihr Computer nicht kompromittiert ist.

### <a name="step-1-reset-the-users-password"></a>Schritt 1: Setzen Sie das Benutzerkennwort zurück.

Folgen Sie den Verfahren unter [Zurücksetzen eines Geschäftskennworts für eine andere Person](../../admin/add-users/reset-passwords.md#reset-my-admin-password).

> [!IMPORTANT]
>
> - Senden Sie das neue Kennwort nicht per E-Mail an den vorgesehenen Benutzer, da der Angreifer weiterhin Zugriff auf das Postfach hat.
>
> - Stellen Sie sicher, dass das Kennwort sicher ist und dass es Groß- und Kleinbuchstaben, mindestens eine Zahl und mindestens ein Sonderzeichen enthält.
>
> - Verwenden Sie nicht eines Ihrer letzten fünf Kennwörter wieder. Obwohl die Kennwortverlaufsanforderung die Verwendung eines aktuelleren Kennworts zulässt, sollten Sie eines auswählen, das der Angreifer nicht erraten kann.
>
> - Wenn Ihre lokale Identität mit Microsoft 365 verbunden ist, müssen Sie das Kennwort lokal ändern und dann Ihren Administrator über den Angriff benachrichtigen.
>
> - Sorgen Sie dafür, dass App-Kennwörter aktualisiert werden. App-Kennwörter werden nicht automatisch widerrufen, wenn ein Benutzerkontokennwort zurückgesetzt wird. Der Benutzer sollte vorhandene App-Kennwörter löschen und neue erstellen. Anweisungen hierzu finden Sie unter [Erstellen und Löschen von App-Kennwörtern über die Seite "Zusätzliche Sicherheitsüberprüfung"](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).
>
> - Es wird dringend empfohlen, dass Sie die mehrstufige Authentifizierung (MFA) aktivieren, um Angriffe zu verhindern, insbesondere für Konten mit Administratorrechten. Weitere Informationen zu MFA finden Sie unter [Einrichten der mehrstufigen Authentifizierung](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Schritt 2: Entfernen Sie verdächtige E-Mail-Weiterleitungsadressen.

1. Öffnen Sie das Microsoft 365 Admin Center unter <https://admin.microsoft.com>.

2. Wechseln Sie zu **Benutzer** \> **Aktive Benutzer**. Suchen Sie das fragliche Benutzerkonto, und wählen Sie den Benutzer (Zeile) aus, ohne das Kontrollkästchen zu aktivieren.

3. Wählen Sie auf der daraufhin angezeigten Detail-Flyoutseite die Registerkarte **E-Mail** aus.

4. Wenn der Wert im Abschnitt **E-Mail-Weiterleitung** **Angewendet** lautet, klicken Sie auf **E-Mail-Weiterleitung verwalten**. Deaktivieren Sie auf der angezeigten **E-Mail-Weiterleitung**-Flyoutseite **Alle an dieses Postfach gesendeten E-Mails weiterleiten**, und klicken Sie dann auf **Änderungen speichern**.

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

1. Öffnen Sie das Microsoft 365 Admin Center, und gehen Sie zu **Benutzer** \> **Aktive Benutzer**.

2. Suchen Sie das Benutzerkonto, wählen Sie es aus, klicken Sie auf ![Mehr-Symbol](../../media/ITPro-EAC-MoreOptionsIcon.png), und wählen Sie dann **Anmeldestatus bearbeiten** aus.

3. Wählen Sie im daraufhin angezeigten Bereich **Anmeldung blockieren** die Option **Anmeldung für diesen Benutzer blockieren** aus, und klicken Sie auf **Änderungen speichern**.

4. Öffnen Sie das Exchange Admin Center (EAC) unter <admin.protection.outlook.com/ecp/>, und wechseln Sie zu **Empfänger > Postfächer**.

5. Suchen Sie den Benutzer und wählen Sie ihn aus. Führen Sie im Detailbereich die folgenden Schritte aus:

   - Führen Sie im Abschnitt **Telefon- und Sprachfunktionen** die folgenden Schritte aus:

     - Wählen Sie **Exchange ActiveSync deaktivieren** aus, und klicken Sie dann in der angezeigten Warnung auf **Ja**.
     - Wählen Sie **OWA für Geräte deaktivieren** aus, und klicken Sie dann in der angezeigten Warnung auf **Ja**.

   - Klicken Sie im Abschnitt **E-Mail-Konnektivität** für Outlook im Web auf **Deaktivieren**, und klicken Sie dann in der angezeigten Warnung auf **Ja**.

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Schritt 6 (optional): Entfernen Sie das vermutlich angegriffen Konto aus allen Administratorrollengruppen.

> [!NOTE]
> Die Mitgliedschaft bei der Administratorrollengruppe kann wiederhergestellt werden, nachdem das Konto gesichert wurde.

1. Melden Sie sich mit einem globalen Administratorkonto an:

2. Führen Sie im Microsoft 365 Admin Center die folgenden Schritte aus:

   1. Wechseln Sie zu **Benutzer** \> **Aktive Benutzer**.
   2. Suchen Sie das Benutzerkonto, wählen Sie es aus, klicken Sie auf ![Mehr-Symbol](../../media/ITPro-EAC-MoreOptionsIcon.png), und wählen Sie dann **Rollen verwalten** aus.
   3. Entfernen Sie alle Administratorrollen, die dem Konto zugewiesen sind. Klicken Sie nach Abschluss des Vorgangs auf **Änderungen speichern**.

3. Führen Sie im Security & Compliance Center unter <https://protection.office.com> die folgenden Schritte aus:

   Wählen Sie **Berechtigungen** aus, wählen Sie die einzelnen Rollengruppen in der Liste aus, und suchen Sie auf der daraufhin angezeigten Detail-Flyoutseite im Abschnitt **Mitglieder** nach dem Benutzerkonto. Führen Sie die folgenden Schritte aus, wenn die Rollengruppe das Benutzerkonto enthält:

   a. Klicken Sie neben **Mitglieder** auf **Bearbeiten**.
   b. Klicken Sie auf der daraufhin angezeigten Flyoutseite **Mitglieder auswählen bearbeiten** auf **Bearbeiten**.
   c. Wählen Sie auf der nun angezeigten Flyoutseite **Mitglieder auswählen** das Benutzerkonto aus, und klicken Sie dann auf **Entfernen**. Klicken Sie abschließend auf **Fertig**, **Speichern** und dann **Schließen**.

4. Führen Sie im EAC unter <admin.protection.outlook.com/ecp/> die folgenden Schritte aus:

   Wählen Sie **Berechtigungen** aus, wählen Sie die einzelnen Rollengruppen manuell aus, und überprüfen Sie im Detailbereich im Abschnitt **Mitglieder** die Benutzerkonten.  Führen Sie die folgenden Schritte aus, wenn die Rollengruppe das Benutzerkonto enthält:

   a. Wählen Sie die Rollengruppe aus, und klicken Sie auf **Bearbeiten** ![Symbol „Bearbeiten“](../../media/ITPro-EAC-EditIcon.png).
   b. Wählen Sie im Abschnitt **Mitglieder** das Benutzerkonto aus, und klicken Sie dann auf **Entfernen** ![Symbol „Entfernen“](../../media/ITPro-EAC-RemoveIcon.gif). Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

### <a name="step-7-optional-additional-precautionary-steps"></a>Schritt 7 (optional): Zusätzliche Vorsichtsmaßnahmen

1. Stellen Sie sicher, dass Sie die gesendeten Elemente überprüfen. Möglicherweise müssen Sie Personen in Ihrer Kontaktliste informieren, dass Ihr Konto manipuliert wurde. Angreifer können sie um Geld gebeten haben, z. B. unter dem Vorwand, dass Sie in einem anderen Land in einer Notsituation sind und Geld benötigen, oder der Angreifer hat ihnen möglicherweise einen Virus gesendet, um auch ihren Computer anzugreifen.

2. Alle anderen Dienste, die dieses Exchange-Konto als alternatives E-Mail-Konto verwendet haben, wurden möglicherweise auch manipuliert. Führen Sie diese Schritte zunächst für Ihr Microsoft 365-Abonnement aus, und danach für Ihre anderen Konten.

3. Stellen Sie sicher, dass Ihre Kontaktinformationen, z. B. Telefonnummern und Adressen, richtig sind.

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Sichern von Microsoft 365 wie ein Profi für Internetsicherheit

Ihr Microsoft 365-Abonnement bietet eine Reihe von leistungsfähigen Funktionen für Sicherheit, die Sie zum Schutz Ihrer Daten und Ihrer Benutzer verwenden können.  Verwenden Sie die [Microsoft 365-Sicherheits-Roadmap: Top-Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](security-roadmap.md) zum Implementieren von empfohlenen Microsoft-Best-Practices für den Schutz Ihres Microsoft 365-Mandanten.

- Aufgaben, die in den ersten 30 Tagen ausgeführt werden sollten.  Diese sind unmittelbar gültig und haben nur geringe Auswirkungen für die Benutzer.

- Aufgaben, die innerhalb von 90 Tagen ausgeführt werden sollten. Diese erfordern etwas mehr Zeit für Planung und Implementierung, stärken die Sicherheit Ihres Unternehmens jedoch erheblich.

- Über 90 Tage hinaus. Diese Verbesserungen werden in den ersten 90 Tagen Ihrer Arbeit umgesetzt.

## <a name="see-also"></a>Siehe auch

- [Erkennen und Korrigieren von Outlook-Regeln und benutzerdefinierten Formularen für Einschleusungsangriffe in Microsoft 365](detect-and-remediate-outlook-rules-forms-attack.md)

- [Internet Crime Complaint Center](https://www.ic3.gov/Home/Ransomware)

- [Securities and Exchange Commission – Phishing-Betrug](https://www.sec.gov/investor/pubs/phishing.htm)

- Um Spam direkt an Microsoft und Ihren Admin zu melden, [verwenden Sie das Report Message-Add-In](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)