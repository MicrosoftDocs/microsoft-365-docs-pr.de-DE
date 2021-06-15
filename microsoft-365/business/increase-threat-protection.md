---
title: Erhöhen des Bedrohungsschutzes für Microsoft 365 for Business
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Richten Sie Microsoft Defender für Office 365 ein und schützen Sie vertrauliche Daten vor Phishing, Schadsoftware und anderen Bedrohungen.
ms.openlocfilehash: a995063cef6fdc42ad62079d49d58edc9d07b52c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924317"
---
# <a name="increase-threat-protection"></a>Erhöhen des Bedrohungsschutzes

Dieser Artikel hilft Ihnen, den Schutz in Ihrem Microsoft 365-Abonnement zu erhöhen, um sich vor Phishing, Schadsoftware und anderen Bedrohungen zu schützen. Diese Empfehlungen eignen sich für Organisationen mit einem erhöhten Sicherheitsbedarf, z. B. Anwaltskanzleien und Kliniken.

Bevor Sie beginnen, überprüfen Sie Ihre Office 365 Sicherheitsbewertung. Office 365 Die Sicherheitsbewertung analysiert die Sicherheit Ihrer Organisation basierend auf Ihren regulären Aktivitäten und Sicherheitseinstellungen und weist eine Bewertung zu. Notieren Sie sich zunächst Ihre aktuelle Bewertung. Um Ihre Bewertung zu erhöhen, führen Sie die in diesem Artikel empfohlenen Aktionen aus. Das Ziel besteht nicht darin, die maximale Punktzahl zu erreichen, sondern sich der Möglichkeiten bewusst zu sein, Ihre Umgebung zu schützen, die sich nicht negativ auf die Produktivität Ihrer Benutzer auswirken.

Weitere Informationen finden Sie unter [Microsoft-Sicherheitsbewertung.](../security/defender/microsoft-secure-score.md)

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Erhöhen des Schutzes vor Schadsoftware in E-Mails

Ihre Office 365- oder Microsoft 365 umgebung umfasst schutz vor Schadsoftware. Sie können diesen Schutz erhöhen, indem Sie Anlagen mit Dateitypen blockieren, die häufig für Schadsoftware verwendet werden. So erhöhen Sie den Schutz vor Schadsoftware in E-Mails:

1. Rufen Sie ihre [https://protection.office.com](https://protection.office.com) Administratorkontoanmeldeinformationen auf, und melden Sie sich an.

2. Wählen Sie im Security &amp; Compliance Center im linken Navigationsbereich unter **"Bedrohungsmanagement"** **die Option** "Richtlinien-Antischadsoftware" \> aus.

3. Doppelklicken Sie auf die Standardrichtlinie, um diese unternehmensweite Richtlinie zu bearbeiten.

4. Wählen Sie **Einstellungen** aus.

5. Wählen Sie unter **Filter für allgemeine Anlagentypen** die Option **"Ein"** aus. Die blockierten Dateitypen werden im Fenster direkt unterhalb dieses Steuerelements aufgelistet. Stellen Sie sicher, dass Sie die folgenden Dateitypen hinzufügen:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Bei Bedarf können Sie später Dateitypen hinzufügen oder löschen.

6. Wählen Sie **"Speichern" aus.**

Weitere Informationen finden Sie unter [Antischadsoftwareschutz in EOP.](../security/office-365-security/anti-malware-protection.md)

## <a name="protect-against-ransomware"></a>Schutz vor Ransomware

Ransomware schränkt den Zugriff auf Daten ein, indem Dateien verschlüsselt oder Computerbildschirme gesperrt werden. Anschließend wird versucht, Geld von Opfer zu erpressen, indem "Lösegeld" gefordert wird, in der Regel in Form von Currencies wie Doppelklicken, im Austausch für den Zugriff auf Daten.

Erstellen Sie zum Schutz vor Ransomware eine oder mehrere Nachrichtenflussregeln, um Dateierweiterungen zu blockieren, die häufig für Ransomware verwendet werden. (Sie haben diese Regeln im [E-Mail-Schritt](#raise-the-level-of-protection-against-malware-in-mail) hinzugefügt, um den Schutz vor Schadsoftware zu erhöhen.) Sie können benutzer, die diese Anlagen erhalten, auch per E-Mail warnen.

Zusätzlich zu den Dateien, die Sie im vorherigen Schritt blockiert haben, empfiehlt es sich, eine Regel zum Warnen von Benutzern zu erstellen, bevor sie Office Dateianlagen öffnen, die Makros enthalten. Ransomware kann in Makros verborgen sein, also warnen Sie Benutzer davor, diese Dateien von Personen zu öffnen, die sie nicht kennen.

So erstellen Sie eine E-Mail-Transportregel:

1. Wechseln Sie zum Admin Center unter <https://admin.microsoft.com> , und wählen Sie Admin **Center** \> **Exchange** aus.

2. Wählen Sie in der **Nachrichtenflusskategorie** **Regeln** aus.

3. Wählen Sie **+** , und wählen Sie dann eine neue Regel **erstellen** aus.

4. Wählen Sie unten im Dialogfeld **weitere Optionen** aus, um den vollständigen Satz von Optionen anzuzeigen.

5. Wenden Sie die Einstellungen in der folgenden Tabelle für die Regel an. Verwenden Sie die Standardwerte für die restlichen Einstellungen, es sei denn, Sie möchten sie ändern.

6. Wählen Sie **Speichern** aus.

|Setting|Warnen von Benutzern vor dem Öffnen von Anlagen Office Dateien|
|---|---|
|Name|Anti-Ransomware-Regel: Benutzer warnen|
|Wenden Sie diese Regel an, wenn . . .|Jede Anlage . . . Dateierweiterung stimmt überein. . .|
|Angeben von Wörtern oder Ausdrücken|Fügen Sie diese Dateitypen hinzu:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|Führen Sie die folgenden Schritte aus. . .|Empfänger durch Nachricht benachrichtigen|
|Bereitstellen von Nachrichtentext|Öffnen Sie diese Dateitypen nicht von Personen, die Sie nicht kennen, da sie Möglicherweise Makros mit schädlichem Code enthalten.|

Weitere Informationen finden Sie unter:

- [Ransomware: So verringern Sie Risiken](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Wiederherstellen der OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Beenden der automatischen Weiterleitung für E-Mails

Hacker, die Zugriff auf das Postfach eines Benutzers erhalten, können E-Mails stehlen, indem sie festlegen, dass das Postfach E-Mails automatisch weiterleitet. Dies kann auch ohne das Bewusstsein des Benutzers erfolgen. Um dies zu verhindern, konfigurieren Sie eine Nachrichtenflussregel.

Um eine E-Mail-Transportregel zu erstellen, schauen Sie sich dieses [kurze Video](../business-video/stop-email-auto-forward.md) an, oder führen Sie die folgenden Schritte aus:

1. Wählen Sie im Microsoft 365 Admin Center **Admin Center** \> **Exchange** aus.

2. Wählen Sie in der **Nachrichtenflusskategorie** **Regeln** aus.

3. Wählen Sie **+** , und wählen Sie dann eine neue Regel **erstellen** aus.

4. Wählen Sie unten im Dialogfeld **weitere Optionen** aus, um alle Optionen anzuzeigen.

5. Wenden Sie die Einstellungen in der folgenden Tabelle an. Verwenden Sie die Standardwerte für die restlichen Einstellungen, es sei denn, Sie möchten sie ändern.

6. Wählen Sie **Speichern** aus.

|Setting|Warnen von Benutzern vor dem Öffnen von Anlagen Office Dateien|
|---|---|
|Name|Verhindern der automatischen Weiterleitung von E-Mails an externe Domänen|
|Wenden Sie diese Regel an, wenn ...|Der Absender . . . ist extern/intern. . . Innerhalb der Organisation|
|Bedingung hinzufügen|Die Nachrichteneigenschaften . . . schließen Sie den Nachrichtentyp ein. . . Automatische Weiterleitung|
|Führen Sie die folgenden Schritte aus...|Die Nachricht blockieren. . . die Nachricht ablehnen und eine Erklärung einfügen.|
|Bereitstellen von Nachrichtentext|Die automatische Weiterleitung von E-Mails außerhalb dieser Organisation wird aus Sicherheitsgründen verhindert.|


## <a name="protect-your-email-from-phishing-attacks"></a>Schützen Ihrer E-Mails vor Phishingangriffen

Wenn Sie eine oder mehrere benutzerdefinierte Domänen für Ihre Office 365 oder Microsoft 365 Umgebung konfiguriert haben, können Sie den gezielten Antiphishingschutz konfigurieren. Der Antiphishingschutz, Teil von Microsoft Defender für Office 365, kann Ihre Organisation vor phishing-Angriffen auf Basis von böswilligem Identitätswechsel und anderen Phishingangriffen schützen. Wenn Sie keine benutzerdefinierte Domäne konfiguriert haben, müssen Sie dies nicht tun.

Wir empfehlen Ihnen, mit diesem Schutz zu beginnen, indem Sie eine Richtlinie zum Schutz Ihrer wichtigsten Benutzer und Ihrer benutzerdefinierten Domäne erstellen.

Um eine Antiphishingrichtlinie in Microsoft Defender für Office 365 zu erstellen, schauen Sie sich [dieses kurze Schulungsvideo](../business-video/setup-anti-phishing.md)an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).

2. Wählen Sie im Security &amp; Compliance Center im linken Navigationsbereich unter **"Bedrohungsmanagement"** die Option **"Richtlinie"** aus.

3. Wählen Sie auf der Seite **"Richtlinie"** die Option **"Antiphishing"** aus.

4. Wählen Sie auf der **Seite "Antiphishing"** die Option **+ Erstellen** aus. Ein Assistent startet, der Sie durch die Definition Ihrer Antiphishingrichtlinie führt.

5. Geben Sie den Namen, die Beschreibung und die Einstellungen für Ihre Richtlinie wie in der folgenden Tabelle empfohlen an. Weitere Informationen finden Sie unter [Informationen zur Antiphishingrichtlinie in Microsoft Defender für Office 365 Optionen.](../security/office-365-security/set-up-anti-phishing-policies.md)

6. Nachdem Sie Ihre Einstellungen überprüft haben, wählen **Sie diese Richtlinie** erstellen oder **speichern,** je nach Bedarf.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Domänen- und wertvollste Kampagnenmitarbeiter|
|Beschreibung|Stellen Sie sicher, dass die wichtigsten Mitarbeiter und unsere Domäne nicht imitiert werden.|
|Zu schützende Benutzer hinzufügen|Select **+ Add a condition, The recipient is**. Geben Sie Benutzernamen ein, oder geben Sie die E-Mail-Adresse des Kandidaten, Kampagnenmanagers und anderer wichtiger Mitarbeiter ein. Sie können bis zu 20 interne und externe Adressen hinzufügen, die Sie vor Identitätswechsel schützen möchten.|
|Zu schützende Domänen hinzufügen|Wählen Sie **+ Bedingung hinzufügen, die Empfängerdomäne lautet**. Geben Sie die benutzerdefinierte Domäne ein, die Ihrem Microsoft 365-Abonnement zugeordnet ist, sofern Sie eine definiert haben. Sie können mehrere Domänen eingeben.|
|Aktionen auswählen|Wenn E-Mails von einem imitierten Benutzer gesendet werden: Wählen Sie **"Nachricht an eine andere E-Mail-Adresse umleiten"** aus, und geben Sie dann die E-Mail-Adresse des Sicherheitsadministrators ein. Beispielsweise *Alice <span> <span> @contoso.com*. Wenn eine E-Mail von einer imitierten Domäne gesendet wird: Wählen Sie **Nachricht in Quarantäne verschieben** aus.|
|Mailbox Intelligence|Standardmäßig wird die Mailbox Intelligence ausgewählt, wenn Sie eine neue Anti-Phishing-Richtlinie erstellen. Lassen Sie diese Einstellung auf **Ein**, um optimale Ergebnisse zu erzielen.|
|Vertrauenswürdige Absender und Domänen hinzufügen|Hier können Sie Ihre eigene Domäne oder andere vertrauenswürdige Domänen hinzufügen.|
|Angewendet auf|Wählen Sie **Die Domäne des Empfängers ist** aus. Wählen Sie unter **Einer dieser**, **Auswählen** aus. Wählen Sie **+ Hinzufügen** aus. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, *z. B. contoso. <span> <span> com*, in der Liste, und klicken Sie dann **auf Hinzufügen**. Wählen Sie **Fertig** aus.|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>Schutz vor bösartigen Anlagen und Dateien mit sicheren Anlagen

Personen senden, empfangen und teilen regelmäßig Anlagen, z. B. Dokumente, Präsentationen, Tabellenkalkulationen und vieles mehr. Es ist nicht immer einfach, anhand einer E-Mail-Nachricht zu erkennen, ob eine Anlage sicher oder bösartig ist. Microsoft Defender für Office 365 umfasst den Schutz sicherer Anlagen, dieser Schutz ist jedoch nicht standardmäßig aktiviert. Es wird empfohlen, eine neue Regel zu erstellen, um mit der Verwendung dieses Schutzes zu beginnen. Dieser Schutz gilt für Dateien in SharePoint, OneDrive und Microsoft Teams.

Um eine Richtlinie für sichere Anlagen zu erstellen, schauen Sie sich [dieses kurze Video](../business-video/safe-attachments.md)an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com) und melden Sie sich mit Ihrem Administratorkonto an.

2. Wählen Sie im Security &amp; Compliance Center im linken Navigationsbereich unter **"Bedrohungsmanagement"** die Option **"Richtlinie"** aus.

3. Wählen Sie auf der Seite "Richtlinie" die Option **"Sichere Anlagen" aus.**

4. Wenden Sie diesen Schutz auf der Seite "Sichere Anlagen" allgemein an, indem Sie das Kontrollkästchen **ATP für SharePoint, OneDrive und Microsoft Teams** aktivieren.

5. Wählen Sie **+** diese Option aus, um eine neue Richtlinie zu erstellen.

6. Wenden Sie die Einstellungen in der folgenden Tabelle an.

7. Nachdem Sie Ihre Einstellungen überprüft haben, wählen **Sie diese Richtlinie** erstellen oder **speichern,** je nach Bedarf.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Blockieren Sie aktuelle und zukünftige E-Mails mit erkannter Schadsoftware.|
|Beschreibung|Blockieren Sie aktuelle und zukünftige E-Mails und Anlagen mit erkannter Schadsoftware.|
|Speichern von Anlagen mit unbekannter Schadsoftwareantwort|Select **Block - Block the current and future emails and attachments with detected malware**.|
|Anlage bei Erkennung umleiten|Aktivieren Sie die Umleitung (aktivieren Sie dieses Feld) Geben Sie das Administratorkonto oder ein Postfach für die Quarantäne ein.          Wenden Sie die oben genannte Auswahl an, wenn bei der Schadsoftwareüberprüfung nach Anlagen ein Zeitüberschreitung auftritt oder ein Fehler auftritt (aktivieren Sie dieses Kontrollkästchen).|
|Angewendet auf|Die Empfängerdomäne lautet . . . Wählen Sie Ihre Domäne aus.|

Weitere Informationen finden Sie unter [Einrichten von Antiphishingrichtlinien in Microsoft Defender für Office 365.](../security/office-365-security/set-up-anti-phishing-policies.md)

## <a name="protect-against-phishing-attacks-with-safe-links"></a>Schutz vor Phishingangriffen mit sicheren Links

Hacker blenden manchmal schädliche Websites in Links in E-Mails oder anderen Dateien aus. Sichere Links, Teil von Microsoft Defender für Office 365, können Zum Schutz Ihrer Organisation beitragen, indem sie die Überprüfung von Webadressen (URLs) in E-Mail-Nachrichten und Office Dokumenten zum Zeitpunkt des Klickens bereitstellen. Der Schutz wird durch Richtlinien für sichere Links definiert.

Es wird empfohlen, Folgendes zu tun:

- Ändern Sie die Standardrichtlinie, um den Schutz zu erhöhen.

- Fügen Sie allen Empfängern in Ihrer Domäne eine neue Richtlinie hinzu.

Um sichere Links einzurichten, schauen Sie sich [dieses kurze Schulungsvideo](../business-video/safe-links.md)an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com) und melden Sie sich mit Ihrem Administratorkonto an.

2. Wählen Sie im Security &amp; Compliance Center im linken Navigationsbereich unter **"Bedrohungsmanagement"** die Option **"Richtlinie"** aus.

3. Wählen Sie auf der Seite "Richtlinie" die Option **"Sichere Links" aus.**

So ändern Sie die Standardrichtlinie:

1. Wählen Sie auf der Seite "Sichere Links" unter **"Richtlinien, die für die gesamte Organisation gelten"** die **Standardrichtlinie** aus.

2. Wählen Sie **unter Einstellungen, die für Inhalte mit Ausnahme von E-Mails gelten,** **Microsoft 365 Apps for Enterprise, Office für iOS und Android** aus.

3. Wählen Sie **Speichern** aus.

So erstellen Sie eine neue Richtlinie für alle Empfänger in Ihrer Domäne:

1. Wählen Sie auf der Seite "Sichere Links" unter **"Richtlinien, die für die gesamte Organisation gelten"** aus, **+** um eine neue Richtlinie zu erstellen.

2. Wenden Sie die in der folgenden Tabelle aufgeführten Einstellungen an.

3. Wählen Sie **Speichern** aus.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Richtlinie für sichere Links für alle Empfänger in der Domäne|
|Wählen Sie die Aktion für unbekannte potenziell schädliche URLs in Nachrichten aus.|Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.|
|Verwenden sicherer Anlagen zum Scannen von herunterladbaren Inhalten|Aktivieren Sie dieses Kontrollkästchen.|
|Angewendet auf|Die Empfängerdomäne lautet . . . Wählen Sie Ihre Domäne aus.|

Weitere Informationen finden Sie unter ["Sichere Links".](../security/office-365-security/safe-links.md)

## <a name="go-to-intune-admin-center"></a>Wechseln Sie zum Intune Admin Center

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com/)an.

2. Wählen Sie **alle Dienste** aus, und geben Sie *intune* im **Suchfeld ein.**

3. Sobald die Ergebnisse angezeigt werden, wählen Sie den Start neben **Microsoft Intune** aus, um ihn zu einem Favoriten zu machen und später leicht zu finden.

Zusätzlich zum Admin Center können Sie Intune verwenden, um die Geräte Ihrer Organisation zu registrieren und zu verwalten. Weitere Informationen finden Sie unter [Capabilities by enrollment method for Windows devices](/intune/enrollment/enrollment-method-capab) and Enrollment options for devices managed by [Intune](/intune/enrollment-options).
