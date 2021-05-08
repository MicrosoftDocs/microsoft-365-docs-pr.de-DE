---
title: Erhöhen des Bedrohungsschutzes für Microsoft 365 Business
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
description: Richten Sie Microsoft Defender für Office 365 und schützen Sie vertrauliche Daten vor Phishing, Schadsoftware und anderen Bedrohungen.
ms.openlocfilehash: 4b5142efbf4392f017cd9b96f6a9c36ef2000bb7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245142"
---
# <a name="increase-threat-protection"></a>Erhöhen des Bedrohungsschutzes

Dieser Artikel hilft Ihnen, den Schutz in Ihrem Microsoft 365 zu erhöhen, um sich vor Phishing, Schadsoftware und anderen Bedrohungen zu schützen. Diese Empfehlungen sind für Organisationen mit erhöhtem Sicherheitsbedarf geeignet, z. B. für Anwaltskanzleien und Gesundheitseinrichtungen.

Bevor Sie beginnen, überprüfen Sie Office 365 Secure Score. Office 365 Secure Score analysiert die Sicherheit Ihrer Organisation basierend auf Ihren regulären Aktivitäten und Sicherheitseinstellungen und weist eine Bewertung zu. Notieren Sie sich zunächst Ihre aktuelle Bewertung. Um Ihre Bewertung zu erhöhen, führen Sie die in diesem Artikel empfohlenen Aktionen aus. Das Ziel ist nicht, die maximale Punktzahl zu erreichen, sondern die Möglichkeiten zum Schutz Ihrer Umgebung zu kennen, die sich nicht negativ auf die Produktivität ihrer Benutzer auswirken.

Weitere Informationen finden Sie unter [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Erhöhen des Schutzniveaus vor Schadsoftware in E-Mails

Ihre Office 365 oder Microsoft 365 umfasst Schutz vor Schadsoftware. Sie können diesen Schutz erhöhen, indem Sie Anlagen mit Dateitypen blockieren, die häufig für Schadsoftware verwendet werden. So erhöhen Sie den Schadsoftwareschutz in E-Mails:

1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu und melden Sie sich mit Ihren Administratorkontoanmeldeinformationen an.

2. Wählen Sie im Security Compliance Center im linken Navigationsbereich unter Bedrohungsverwaltung die Option &amp; **Policy**  \> **Anti-Malware aus.**

3. Doppelklicken Sie auf die Standardrichtlinie, um diese unternehmensweite Richtlinie zu bearbeiten.

4. Wählen Sie **Einstellungen** aus.

5. Wählen **Sie unter Filter für allgemeine Anlagentypen** die Option Ein **aus.** Die blockierten Dateitypen werden im Fenster direkt unterhalb dieses Steuerelements aufgeführt. Stellen Sie sicher, dass Sie die folgenden Dateitypen hinzufügen:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Bei Bedarf können Sie später Dateitypen hinzufügen oder löschen.

6. Wählen Sie **Speichern aus.**

Weitere Informationen finden Sie unter [Schutz vor Schadsoftware in EOP](../security/office-365-security/anti-malware-protection.md).

## <a name="protect-against-ransomware"></a>Schutz vor Ransomware

Ransomware schränkt den Zugriff auf Daten ein, indem Dateien verschlüsselt oder Computerbildschirme gesperrt werden. Anschließend versucht sie, Geld von Denkgeschädigten zu erpressen, indem sie "Lösegeld" fordert, in der Regel in Form von Kryptowährungen wie z. B. Bitcoin, im Austausch für den Zugriff auf Daten.

Erstellen Sie zum Schutz vor Ransomware eine oder mehrere Nachrichtenflussregeln, um Dateierweiterungen zu blockieren, die häufig für Ransomware verwendet werden. (Sie haben diese Regeln im Schritt erhöhen des Schutzes vor [Schadsoftware in E-Mail hinzugefügt.)](#raise-the-level-of-protection-against-malware-in-mail) Sie können auch Benutzer warnen, die diese Anlagen in E-Mails erhalten.

Zusätzlich zu den Dateien, die Sie im vorherigen Schritt blockiert haben, ist es eine bewährte Methode, eine Regel zum Warnen von Benutzern zu erstellen, bevor sie Office Dateianlagen öffnen, die Makros enthalten. Ransomware kann in Makros ausgeblendet werden, also warnen Sie Benutzer davor, diese Dateien von Personen zu öffnen, die sie nicht kennen.

So erstellen Sie eine E-Mail-Transportregel:

1. Wechseln Sie zum Admin Center unter <https://admin.microsoft.com> , und wählen Sie Admin Center  \> **Exchange**.

2. Wählen Sie **in der** Kategorie Nachrichtenfluss Regeln **aus.**

3. Wählen **+** Sie aus, und wählen Sie **dann Neue Regel erstellen aus.**

4. Wählen **Sie unten im** Dialogfeld weitere Optionen aus, um den vollständigen Satz von Optionen anzuzeigen.

5. Wenden Sie die Einstellungen in der folgenden Tabelle für die Regel an. Verwenden Sie die Standardwerte für die restlichen Einstellungen, es sei denn, Sie möchten sie ändern.

6. Klicken Sie auf **Speichern**.

|Einstellung|Warnen Von Benutzern vor dem Öffnen von Anlagen Office Dateien||
|---|---|---|
|Name|Anti-Ransomware-Regel: Benutzer warnen|
|Wenden Sie diese Regel an, wenn . . .|Jede Anlage . . . Dateierweiterung entspricht . . .|
|Angeben von Wörtern oder Ausdrücken|Fügen Sie die folgenden Dateitypen hinzu:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|Gehen Sie wie folgt vor. . .|Empfänger durch Nachricht benachrichtigen|
|Bereitstellen von Nachrichtentext|Öffnen Sie diese Dateitypen nicht von Personen, die Sie nicht kennen, da sie Möglicherweise Makros mit bösartigem Code enthalten.|

Weitere Informationen finden Sie unter:

- [Ransomware: Verringern des Risikos](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Wiederherstellen ihrer OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Beenden der automatischen Weiterleitung für E-Mails

Hacker, die Zugriff auf das Postfach eines Benutzers erhalten, können E-Mails stehlen, indem sie das Postfach so festlegen, dass E-Mails automatisch weitergeleitet werden. Dies kann auch ohne das Bewusstsein des Benutzers geschehen. Um dies zu verhindern, konfigurieren Sie eine Nachrichtenflussregel.

Um eine E-Mail-Transportregel zu erstellen, sehen Sie sich entweder [dieses kurze Video an,](../business-video/stop-email-auto-forward.md) oder führen Sie die folgenden Schritte aus:

1. Wählen Sie Microsoft 365 Admin Center admin center **Exchange** \> aus.

2. Wählen Sie **in der** Kategorie Nachrichtenfluss Regeln **aus.**

3. Wählen **+** Sie aus, und wählen Sie **dann Neue Regel erstellen aus.**

4. Um alle Optionen anzuzeigen, **wählen** Sie unten im Dialogfeld weitere Optionen aus.

5. Wenden Sie die Einstellungen in der folgenden Tabelle an. Verwenden Sie die Standardwerte für die restlichen Einstellungen, es sei denn, Sie möchten sie ändern.

6. Klicken Sie auf **Speichern**.

|Einstellung|Warnen Von Benutzern vor dem Öffnen von Anlagen Office Dateien|
|---|---|
|Name|Verhindern der automatischen Weiterleitung von E-Mails an externe Domänen|
|Wenden Sie diese Regel an, wenn ...|Der Absender . . . ist extern/intern . . . Innerhalb der Organisation|
|Bedingung hinzufügen|Die Nachrichteneigenschaften . . . geben Sie den Nachrichtentyp ein. . . Automatische Weiterleitung|
|Gehen Sie wie folgt vor...|Blockieren der Nachricht . . . die Nachricht ablehnen und eine Erläuterung enthalten.|
|Bereitstellen von Nachrichtentext|Die automatische Weiterleitung von E-Mails außerhalb dieser Organisation wird aus Sicherheitsgründen verhindert.|


## <a name="protect-your-email-from-phishing-attacks"></a>Schützen Ihrer E-Mails vor Phishingangriffen

Wenn Sie eine oder mehrere benutzerdefinierte Domänen für Ihre Office 365 oder Microsoft 365 konfiguriert haben, können Sie gezielten Antiphishingschutz konfigurieren. Der Antiphishingschutz, der Teil von Microsoft Defender for Office 365 ist, kann Ihre Organisation vor phishingbasierten Phishingangriffen und anderen Phishingangriffen durch böswilligen Identitätswechsel schützen. Wenn Sie keine benutzerdefinierte Domäne konfiguriert haben, müssen Sie dies nicht tun.

Es wird empfohlen, mit diesem Schutz zu beginnen, indem Sie eine Richtlinie zum Schutz Ihrer wichtigsten Benutzer und Ihrer benutzerdefinierten Domäne erstellen.

Um eine Antiphishingrichtlinie in Microsoft Defender for Office 365 zu erstellen, sehen Sie sich dieses kurze Schulungsvideo [an,](../business-video/setup-anti-phishing.md)oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).

2. Wählen Sie im Security Compliance Center im linken Navigationsbereich unter &amp; Bedrohungsverwaltung die Option Richtlinie **aus.** 

3. Wählen Sie **auf der** Seite Richtlinie die Option **Antiphishing aus.**

4. Wählen Sie **auf der Seite Antiphishing** die Option **+ Erstellen aus.** Ein Assistent startet Sie durch die Definition Ihrer Antiphishingrichtlinie.

5. Geben Sie den Namen, die Beschreibung und die Einstellungen für Ihre Richtlinie wie in der folgenden Tabelle empfohlen an. Weitere Informationen finden Sie [unter Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/office-365-security/set-up-anti-phishing-policies.md).

6. Nachdem Sie Ihre Einstellungen überprüft haben, wählen Sie Diese Richtlinie **erstellen** oder **Speichern** aus.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Domänen- und wertvollste Mitarbeiter für Kampagnen|
|Beschreibung|Stellen Sie sicher, dass die wichtigsten Mitarbeiter und unsere Domäne nicht als Identitätswechsel verwendet werden.|
|Zu schützende Benutzer hinzufügen|Select **+ Add a condition, The recipient is**. Geben Sie Benutzernamen ein, oder geben Sie die E-Mail-Adresse des Kandidaten, des Kampagnenmanagers und anderer wichtiger Mitarbeiter ein. Sie können bis zu 20 interne und externe Adressen hinzufügen, die Sie vor Identitätswechseln schützen möchten.|
|Zu schützende Domänen hinzufügen|Select **+ Add a condition, The recipient domain is**. Geben Sie die benutzerdefinierte Domäne ein, die Ihrem Microsoft 365 zugeordnet ist, wenn Sie eine definiert haben. Sie können mehrere Domänen eingeben.|
|Aktionen auswählen|Wenn E-Mails von einem identitätswechselten Benutzer gesendet werden: Wählen Sie **Nachricht** an eine andere E-Mail-Adresse umleiten aus, und geben Sie dann die E-Mail-Adresse des Sicherheitsadministrators ein. Beispiel: *Alice <span> <span> @contoso.com*. Wenn eine E-Mail von einer imitierten Domäne gesendet wird: Wählen Sie **Nachricht in Quarantäne verschieben** aus.|
|Mailbox Intelligence|Standardmäßig wird die Mailbox Intelligence ausgewählt, wenn Sie eine neue Anti-Phishing-Richtlinie erstellen. Lassen Sie diese Einstellung auf **Ein**, um optimale Ergebnisse zu erzielen.|
|Vertrauenswürdige Absender und Domänen hinzufügen|Hier können Sie Ihre eigene Domäne oder andere vertrauenswürdige Domänen hinzufügen.|
|Angewendet auf|Wählen Sie **Die Domäne des Empfängers ist** aus. Wählen Sie unter **Einer dieser**, **Auswählen** aus. Wählen Sie **+ Hinzufügen** aus. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, z. B. *contoso. <span> <span> com*, in der Liste, und wählen Sie dann **Hinzufügen aus.** Wählen Sie **Fertig** aus.|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>Schützen vor schädlichen Anlagen und Dateien mit sicheren Anlagen

Personen senden, empfangen und teilen anlagen, z. B. Dokumente, Präsentationen, Tabellen und vieles mehr. Es ist nicht immer einfach zu bestimmen, ob eine Anlage sicher oder bösartig ist, indem Sie sich eine E-Mail-Nachricht anschauen. Microsoft Defender for Office 365 enthält sicheren Anlagenschutz, dieser Schutz ist jedoch nicht standardmäßig aktiviert. Es wird empfohlen, eine neue Regel zu erstellen, um mit der Verwendung dieses Schutzes zu beginnen. Dieser Schutz erstreckt sich auf Dateien in SharePoint, OneDrive und Microsoft Teams.

Um eine Richtlinie für sichere Anlagen zu erstellen, sehen Sie sich entweder dieses [kurze](../business-video/safe-attachments.md)Video an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu , und melden Sie sich mit Ihrem Administratorkonto an.

2. Wählen Sie im Security Compliance Center im linken Navigationsbereich unter &amp; Bedrohungsverwaltung die Option Richtlinie **aus.** 

3. Wählen Sie auf der Seite Richtlinie die Option **Sichere Anlagen aus.**

4. Wenden Sie diesen Schutz auf der Seite Sichere Anlagen allgemein an, indem Sie das Kontrollkästchen ATP für **SharePoint,** OneDrive und Microsoft Teams aktivieren aktivieren.

5. Wählen **+** Sie diese Option aus, um eine neue Richtlinie zu erstellen.

6. Wenden Sie die Einstellungen in der folgenden Tabelle an.

7. Nachdem Sie Ihre Einstellungen überprüft haben, wählen Sie Diese Richtlinie **erstellen** oder **Speichern** aus, wenn dies der Richtige ist.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Blockieren Sie aktuelle und zukünftige E-Mails mit erkannter Schadsoftware.|
|Beschreibung|Blockieren Sie aktuelle und zukünftige E-Mails und Anlagen mit erkannter Schadsoftware.|
|Speichern von Anlagen unbekannte Schadsoftwareantwort|Wählen Sie Blockieren – Blockieren der aktuellen und zukünftigen **E-Mails und Anlagen mit erkannter Schadsoftware aus.**|
|Umleitungsanlage bei Erkennung|Umleitung aktivieren (aktivieren Sie dieses Feld) Geben Sie das Administratorkonto oder ein Postfach für die Quarantäne ein.          Wenden Sie die oben aufgeführte Auswahl an, wenn bei der Schadsoftwareprüfung auf Anlagen ein Zeitfehler auftritt oder ein Fehler auftritt (aktivieren Sie dieses Feld).|
|Angewendet auf|Die Empfängerdomäne ist . . . Wählen Sie Ihre Domäne aus.|

Weitere Informationen finden Sie unter [Einrichten von Antiphishingrichtlinien in Microsoft Defender für Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).

## <a name="protect-against-phishing-attacks-with-safe-links"></a>Schützen vor Phishingangriffen mit sicheren Links

Hacker verbergen bösartige Websites manchmal in Links in E-Mails oder anderen Dateien. Sichere Links, die Teil von Microsoft Defender for Office 365 sind, können Zum Schutz Ihrer Organisation beitragen, indem Sie die Überprüfung von Webadressen (URLs) in E-Mail-Nachrichten und dokumenten Office bereitstellen. Der Schutz wird durch Richtlinien für sichere Links definiert.

Es wird empfohlen, die folgenden Schritte zu tun:

- Ändern Sie die Standardrichtlinie, um den Schutz zu erhöhen.

- Fügen Sie eine neue Richtlinie für alle Empfänger in Ihrer Domäne hinzu.

Zum Einrichten sicherer Links sehen Sie sich [dieses kurze Schulungsvideo an,](../business-video/safe-links.md)oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu , und melden Sie sich mit Ihrem Administratorkonto an.

2. Wählen Sie im Security Compliance Center im linken Navigationsbereich unter &amp; Bedrohungsverwaltung die Option Richtlinie **aus.** 

3. Wählen Sie auf der Seite Richtlinie die Option **Sichere Links aus.**

So ändern Sie die Standardrichtlinie:

1. Wählen Sie auf der Seite Sichere Links unter **Richtlinien, die für** die gesamte Organisation gelten, die **Standardrichtlinie** aus.

2. Wählen **Einstellungen, die für Inhalte** außer E-Mail gelten, **Microsoft 365 Apps for Enterprise, Office für iOS und Android aus.**

3. Klicken Sie auf **Speichern**.

So erstellen Sie eine neue Richtlinie für alle Empfänger in Ihrer Domäne:

1. Wählen Sie auf der Seite Sichere Links unter **Richtlinien, die für** die gesamte Organisation gelten, aus, **+** um eine neue Richtlinie zu erstellen.

2. Wenden Sie die in der folgenden Tabelle aufgeführten Einstellungen an.

3. Klicken Sie auf **Speichern**.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Richtlinie für sichere Links für alle Empfänger in der Domäne|
|Auswählen der Aktion für unbekannte potenziell schädliche URLs in Nachrichten|Select **On – URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.|
|Verwenden sicherer Anlagen zum Überprüfen herunterladbarer Inhalte|Wählen Sie dieses Feld aus.|
|Angewendet auf|Die Empfängerdomäne ist . . . Wählen Sie Ihre Domäne aus.|

Weitere Informationen finden Sie unter [Sichere Links](../security/office-365-security/safe-links.md).

## <a name="go-to-intune-admin-center"></a>Wechseln sie zu Intune Admin Center

1. Melden Sie sich beim [Azure-Portal an.](https://portal.azure.com/)

2. Wählen **Sie Alle Dienste** aus, und geben Sie in *Intune* im **Suchfeld ein.**

3. Sobald die Ergebnisse angezeigt werden, wählen Sie den Start neben **Microsoft Intune,** um ihn zu einem Favoriten zu machen und später leicht zu finden.

Zusätzlich zum Admin Center können Sie Intune verwenden, um die Geräte Ihrer Organisation zu registrieren und zu verwalten. Weitere Informationen finden Sie unter [Capabilities by enrollment method for Windows devices](/intune/enrollment/enrollment-method-capab) and Enrollment options for devices managed by [Intune](/intune/enrollment-options).
