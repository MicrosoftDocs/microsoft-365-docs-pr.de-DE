---
title: Erhöhter Bedrohungsschutz für Microsoft 365 for Business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Richten Sie Office 365 Advanced Threat Protection ein, und schützen Sie vertrauliche Daten vor Phishing, Schadsoftware und anderen Bedrohungen.
ms.openlocfilehash: d56a5371bc5fc4da22f4625024769cc0325a25ca
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948586"
---
# <a name="increase-threat-protection"></a>Erhöhen des Bedrohungsschutzes

Dieser Artikel unterstützt Sie bei der Verbesserung des Schutzes Ihres Microsoft 365-Abonnements zum Schutz vor Phishing, Schadsoftware und anderen Bedrohungen. Diese Empfehlungen sind für Organisationen mit einem erhöhten Sicherheitsbedürfnis geeignet, wie zum Beispiel Anwaltskanzleien und Kliniken für das Gesundheitswesen.

Bevor Sie beginnen, überprüfen Sie Ihr Office 365 sicheres Ergebnis. Office 365 Secure Score analysiert die Sicherheit Ihrer Organisation basierend auf Ihren regulären Aktivitäten und Sicherheitseinstellungen und weist eine Bewertung zu. Notieren Sie sich zunächst Ihre aktuelle Bewertung. Um die Punktzahl zu verbessern, führen Sie die in diesem Artikel empfohlenen Aktionen aus. Ziel ist nicht die maximale Punktzahl, sondern die Möglichkeiten zum Schutz Ihrer Umgebung, die sich negativ auf die Produktivität Ihrer Benutzer auswirken.

Weitere Informationen finden Sie unter [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Erhöhen des Schutzniveaus gegen Schadsoftware in Mail

Ihre Office 365-oder Microsoft 365-Umgebung umfasst den Schutz vor Schadsoftware. Sie können diesen Schutz verbessern, indem Sie Anlagen mit Dateitypen blockieren, die häufig für Schadsoftware verwendet werden. So verbessern Sie den Schutz vor Schadsoftware in e-Mails:

1. Wechseln Sie zu, [https://protection.office.com](https://protection.office.com) und melden Sie sich mit den Anmeldeinformationen Ihres Administratorkontos an.

2. &amp;Wählen Sie im Security Compliance Center im linken Navigationsbereich unter **Threat Management**die Option **Policy** \> **Anti-Malware**aus.

3. Doppelklicken Sie auf die Standardrichtlinie, um diese unternehmensweite Richtlinie zu bearbeiten.

4. Wählen Sie **Einstellungen** aus.

5. Wählen Sie unter **Allgemeine Filter für Anlagentypen**die Option **ein**aus. Die blockierten Dateitypen werden im Fenster direkt unterhalb dieses Steuerelements aufgeführt. Stellen Sie sicher, dass Sie diese Dateitypen hinzufügen:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Bei Bedarf können Sie später Dateitypen hinzufügen oder löschen.

6. Wählen Sie **Speichern aus.**

Weitere Informationen finden Sie unter [Schutz vor Schadsoftware in EoP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection).

## <a name="protect-against-ransomware"></a>Schutz vor Ransomware

Ransomware schränkt den Zugriff auf Daten ein, indem Dateien verschlüsselt oder Computerbildschirme gesperrt werden. Er versucht dann, Geld von den Opfern zu erpressen, indem er nach "Lösegeld" fragt, normalerweise in Form von cryptocurrencies wie Bitcoin, im Gegenzug für den Zugriff auf Daten.

Zum Schutz vor Ransomware erstellen Sie eine oder mehrere Nachrichtenfluss Regeln zum Blockieren von Dateierweiterungen, die häufig für Ransomware verwendet werden. (Sie haben diese Regeln im [e-Mail-Schritt zum Heraufstufen des Schutzes vor Schadsoftware](#raise-the-level-of-protection-against-malware-in-mail) hinzugefügt.) Sie können auch Benutzer warnen, die diese Anlagen in e-Mails empfangen.

Zusätzlich zu den Dateien, die Sie im vorherigen Schritt blockiert haben, empfiehlt es sich, eine Regel zu erstellen, um Benutzer vor dem Öffnen von Office-Dateianlagen zu warnen, die Makros enthalten. Ransomware können in Makros ausgeblendet werden, sodass Benutzer gewarnt werden, diese Dateien nicht von Personen zu öffnen, die Sie nicht kennen.

So erstellen Sie eine e-Mail-Transportregel:

1. Wechseln Sie zum Admin Center unter <https://admin.microsoft.com> , und wählen Sie **Admin Center** \> **Exchange**aus.

2. Wählen Sie in der Kategorie **Nachrichtenfluss** die Option **Regeln**aus.

3. Wählen Sie aus **+** , und wählen Sie dann **neue Regel erstellen**aus.

4. Wählen Sie im unteren Bereich des Dialogfelds **Weitere Optionen** aus, um den vollständigen Optionssatz anzuzeigen.

5. Wenden Sie die Einstellungen in der folgenden Tabelle für die Regel an. Verwenden Sie die Standardwerte für die restlichen Einstellungen, es sei denn, Sie möchten Sie ändern.

6. Wählen Sie **Speichern** aus.

|Einstellung|Benutzer vor dem Öffnen von Anlagen von Office-Dateien warnen||
|---|---|---|
|Name|Anti-Ransomware-Regel: Benutzer warnen|
|Wenden Sie diese Regel an, wenn. . .|Jede Anlage. . . Dateierweiterung entspricht. . .|
|Angeben von Wörtern oder Ausdrücken|Fügen Sie diese Dateitypen hinzu:  <br/> DOTM, DOCM, XLSM, sltm, XLA, xlam, XLL, PPTM, POTM, PPAM, PPSM, sldm|
|Führen Sie die folgenden Schritte aus. . .|Empfänger durch Nachricht benachrichtigen|
|Nachrichtentext bereitstellen|Öffnen Sie diese Dateitypen nicht von Personen, die Sie nicht kennen, da Sie möglicherweise Makros mit bösartigem Code enthalten.|

Weitere Informationen finden Sie unter:

- [Ransomware: Verringern des Risikos](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Wiederherstellen der OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Beenden der automatischen Weiterleitung für e-Mail

Hacker, die Zugriff auf das Postfach eines Benutzers erhalten, können e-Mails stehlen, indem Sie das Postfach so festlegen, dass e-Mails automatisch weitergeleitet werden. Dies kann auch ohne das Bewusstsein des Benutzers geschehen. Um dies zu verhindern, konfigurieren Sie eine e-Mail-Fluss Regel.

Um eine e-Mail-Transportregel zu erstellen, schauen Sie sich [Dieses kurze Video](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) an, oder führen Sie die folgenden Schritte aus:

1. Wählen Sie im Microsoft 365 Admin Center die Option **Admin Center** \> **Exchange**aus.

2. Wählen Sie in der Kategorie **Nachrichtenfluss** die Option **Regeln**aus.

3. Wählen Sie aus **+** , und wählen Sie dann **neue Regel erstellen**aus.

4. Um alle Optionen anzuzeigen, wählen Sie am unteren Rand des Dialogfelds **Weitere Optionen** aus.

5. Wenden Sie die Einstellungen in der folgenden Tabelle an. Verwenden Sie die Standardwerte für die restlichen Einstellungen, es sei denn, Sie möchten Sie ändern.

6. Wählen Sie **Speichern** aus.

|Einstellung|Benutzer vor dem Öffnen von Anlagen von Office-Dateien warnen|
|---|---|
|Name|Verhindern der automatischen Weiterleitung von e-Mails an externe Domänen|
|Diese Regel anwenden, wenn...|Absender. . . ist extern/intern. . . Innerhalb der Organisation|
|Bedingung hinzufügen|Die Nachrichteneigenschaften. . . Geben Sie den Nachrichtentyp ein. . . Automatische Weiterleitung|
|Führen Sie die folgenden Schritte aus...|Blockiert die Nachricht. . . die Nachricht ablehnen und eine Erklärung einschließen.|
|Nachrichtentext bereitstellen|Die automatische Weiterleitung von e-Mails außerhalb dieser Organisation wird aus Sicherheitsgründen verhindert.|


## <a name="protect-your-email-from-phishing-attacks"></a>Schützen Ihrer e-Mails vor Phishing-Angriffen

Wenn Sie eine oder mehrere benutzerdefinierte Domänen für Ihre Office 365-oder Microsoft 365-Umgebung konfiguriert haben, können Sie den gezielten Schutz gegen Phishing konfigurieren. Der ATP-Schutz gegen Phishing, ein Teil Office 365 Advanced Threat Protection, kann zum Schutz Ihrer Organisation vor böswilligen Identitätswechsel basierten Phishing-Angriffen und anderen Phishing-Angriffen beitragen. Wenn Sie keine benutzerdefinierte Domäne konfiguriert haben, müssen Sie dies nicht tun.

Es wird empfohlen, dass Sie mit diesem Schutz beginnen, indem Sie eine Richtlinie zum Schutz ihrer wichtigsten Benutzer und Ihrer benutzerdefinierten Domäne erstellen.

Um eine ATP-Anti-Phishing-Richtlinie zu erstellen, schauen Sie sich  [Dieses kurze Schulungsvideo](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).

2. &amp;Wählen Sie im Security Compliance Center im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinie**aus.

3. Wählen Sie auf der Seite **Richtlinie** die Option **ATP Anti-Phishing**aus.

4. Wählen Sie auf der Seite **Anti-Phishing** die Option **+ Create**aus. Ein Assistent wird gestartet, der Sie schrittweise durch die Definition ihrer Anti-Phishing-Richtlinie führt.

5. Geben Sie den Namen, die Beschreibung und die Einstellungen für Ihre Richtlinie an, wie in der folgenden Tabelle empfohlen. Weitere Informationen finden Sie unter [Learn about ATP Anti-Phishing Policy Options](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

6. Nachdem Sie Ihre Einstellungen überprüft haben, wählen Sie **Erstellen Sie diese Richtlinie** oder **Speichern**, je nach Bedarf.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Domäne und die wertvollsten Kampagnen Mitarbeiter|
|Beschreibung|Stellen Sie sicher, dass die meisten wichtigen Mitarbeiter und unsere Domäne nicht angenommen werden.|
|Zu schützende Benutzer hinzufügen|Wählen Sie **+ Bedingung hinzufügen, ist der Empfänger**. Geben Sie Benutzernamen ein, oder geben Sie die e-Mail-Adresse des Kandidaten, des Kampagnen Managers und anderer wichtiger Mitarbeiter ein. Sie können bis zu 20 interne und externe Adressen hinzufügen, die Sie vor dem Identitätswechsel schützen möchten.|
|Zu schützende Domänen hinzufügen|Wählen Sie **+ Bedingung hinzufügen, die Empfängerdomäne ist**. Geben Sie die benutzerdefinierte Domäne, die Ihrem Microsoft 365-Abonnement zugeordnet ist, ein, wenn Sie eine definiert haben. Sie können mehr als eine Domäne eingeben.|
|Aktionen auswählen|Wenn e-Mail von einem imitierten Benutzer gesendet wird: Wählen Sie **Nachricht an eine andere e-Mail-Adresse umleiten**aus, und geben Sie dann die e-Mail-Adresse des Sicherheitsadministrators ein. Beispiel: *Alice <span> <span> @contoso. com*. Wenn eine E-Mail von einer imitierten Domäne gesendet wird: Wählen Sie **Nachricht in Quarantäne verschieben**aus.|
|Mailbox Intelligence|Standardmäßig wird die Mailbox Intelligence ausgewählt, wenn Sie eine neue Anti-Phishing-Richtlinie erstellen. Lassen Sie diese Einstellung auf **Ein**, um optimale Ergebnisse zu erzielen.|
|Vertrauenswürdige Absender und Domänen hinzufügen|Hier können Sie Ihre eigene Domäne oder andere vertrauenswürdige Domänen hinzufügen.|
|Angewendet auf|Wählen Sie **Die Domäne des Empfängers ist** aus. Wählen Sie unter **Einer dieser**, **Auswählen** aus. Wählen Sie **+ Hinzufügen** aus. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, beispielsweise *contoso. <span> <span> com*in der Liste aus, und wählen Sie dann **Hinzufügen**aus. Wählen Sie **Fertig** aus.|

## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>Schutz vor böswilligen Anlagen und Dateien mit sicheren ATP-Anlagen

Personen senden, empfangen und teilen regelmäßig Anlagen wie Dokumente, Präsentationen, Tabellenkalkulationen und vieles mehr. Es ist nicht immer einfach zu erkennen, ob eine Anlage sicher oder böswillig ist, indem nur eine e-Mail-Nachricht angezeigt wird. Office 365 Advanced Threat Protection umfasst den Schutz von ATP-Sicherheitsanlagen, dieser Schutz ist jedoch nicht standardmäßig aktiviert. Es wird empfohlen, dass Sie eine neue Regel erstellen, um mit diesem Schutz zu beginnen. Dieser Schutz erstreckt sich auf Dateien in SharePoint, OneDrive und Microsoft Teams.

Um eine Richtlinie für eine ATP-sichere Anlage zu erstellen, schauen Sie sich [Dieses kurze Video](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com) , und melden Sie sich mit Ihrem Administratorkonto an.

2. &amp;Wählen Sie im Security Compliance Center im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinie**aus.

3. Wählen Sie auf der Seite Richtlinie die Option **ATP-sichere Anlagen**aus.

4. Wenden Sie diesen Schutz auf der Seite sichere Anlagen allgemein an, indem Sie das Kontrollkästchen **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren** aktivieren.

5. Wählen Sie diese Option aus **+** , um eine neue Richtlinie zu erstellen.

6. Wenden Sie die Einstellungen in der folgenden Tabelle an.

7. Nachdem Sie Ihre Einstellungen überprüft haben, wählen Sie **Erstellen Sie diese Richtlinie** oder **Speichern**, je nach Bedarf.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Blockiert aktuelle und zukünftige e-Mails mit erkannter Schadsoftware.|
|Beschreibung|Blockiert aktuelle und zukünftige e-Mails und Anlagen mit erkannter Schadsoftware.|
|Anhänge speichern unbekannte Schadsoftware-Antwort|Wählen Sie **die Option Blockieren der aktuellen und zukünftigen e-Mails und Anlagen mit erkannter Schadsoftware**aus.|
|Umleitungs Anlage bei der Erkennung|Umleitung aktivieren (aktivieren Sie dieses Kontrollkästchen) geben Sie das Administratorkonto oder ein Post Fach Setup für Quarantäne ein.          Wenden Sie die obige Auswahl an, wenn bei der Malwareüberprüfung nach Anlagen ein Timeout oder ein Fehler auftritt (aktivieren Sie dieses Kontrollkästchen).|
|Angewendet auf|Die Empfängerdomäne ist. . . Wählen Sie Ihre Domäne aus.|

Weitere Informationen finden Sie unter [Einrichten von Office 365 ATP-Richtlinien zum Schutz vor Phishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a>Schutz vor Phishing-Angriffen durch ATP-sichere Links

Hacker verbergen manchmal böswillige Websites in Links in e-Mails oder anderen Dateien. Office 365 ATP-sichere Links (ATP-sichere Links), ein Teil Office 365 Advanced Threat Protection, können zum Schutz Ihrer Organisation beitragen, indem Sie die Zeit-für-Klick-Überprüfung von Webadressen (URLs) in e-Mail-Nachrichten und Office-Dokumenten ermöglichen. Der Schutz wird durch Richtlinien für ATP-sichere Links definiert.

Es wird empfohlen, dass Sie die folgenden Schritte ausführen:

- Ändern Sie die Standardrichtlinie, um den Schutz zu verbessern.

- Fügen Sie eine neue Richtlinie hinzu, die für alle Empfänger in Ihrer Domäne vorgesehen ist.

Um ATP-sichere Links einzurichten, schauen Sie sich [Dieses kurze Schulungsvideo](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com) , und melden Sie sich mit Ihrem Administratorkonto an.

2. &amp;Wählen Sie im Security Compliance Center im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinie**aus.

3. Wählen Sie auf der Seite Richtlinie die Option **ATP-sichere Links**aus.

So ändern Sie die Standardrichtlinie:

1. Wählen Sie auf der Seite sichere Links unter **Richtlinien, die für die gesamte Organisation gelten**, die **Standard** Richtlinie aus.

2. Wählen Sie unter **Einstellungen für Inhalt außer e-Mail**die Option **Microsoft 365 apps for Enterprise, Office für IOS und Android**aus.

3. Wählen Sie **Speichern** aus.

So erstellen Sie eine neue Richtlinie, die für alle Empfänger in Ihrer Domäne vorgesehen ist:

1. Wählen Sie auf der Seite sichere Links unter **Richtlinien, die für die gesamte Organisation gelten**, die Option aus, **+** um eine neue Richtlinie zu erstellen.

2. Wenden Sie die in der folgenden Tabelle aufgeführten Einstellungen an.

3. Wählen Sie **Speichern** aus.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Richtlinie für sichere Links für alle Empfänger in der Domäne|
|Auswählen der Aktion für unbekannte potenziell bösartige URLs in Nachrichten|Select **on-URLs werden umgeschrieben und anhand einer Liste bekannter böswilliger Links überprüft, wenn der Benutzer auf den Link klickt**.|
|Verwenden sicherer Anlagen zum Überprüfen herunterladbarer Inhalte|Aktivieren Sie dieses Kontrollkästchen.|
|Angewendet auf|Die Empfängerdomäne ist. . . Wählen Sie Ihre Domäne aus.|

Weitere Informationen finden Sie unter [Office 365 ATP-sichere Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links).

## <a name="go-to-intune-admin-center"></a>Wechseln Sie zu InTune Admin Center

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com/)an.

2. Wählen Sie **alle Dienste** aus, und geben Sie *InTune* in das **Suchfeld**ein.

3. Sobald die Ergebnisse angezeigt werden, wählen Sie den Start neben **Microsoft InTune** aus, um ihn zu einem bevorzugten und leicht zu findenden späteren Zeitpunkt zu machen.

Zusätzlich zum Admin Center können Sie InTune verwenden, um die Geräte Ihrer Organisation zu registrieren und zu verwalten. Weitere Informationen finden Sie unter [Funktionen nach Registrierungsmethode für Windows-Geräte](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) und [Registrierungsoptionen für Geräte, die von InTune verwaltet](https://docs.microsoft.com/intune/enrollment-options)werden.
