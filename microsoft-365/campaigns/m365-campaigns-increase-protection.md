---
title: Erhöhen des Bedrohungsschutzes
f1.keywords:
- NOCSH
ms.author: sharik
author: Skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: Hilfe zum Erhöhen des Schutzniveaus in Microsoft 365
ms.openlocfilehash: a1f4714d5b7dcd8d6a22a07c118055e13b27e069
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398277"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a>Erhöhen des Bedrohungsschutzes für Microsoft 365 Abonnement

Dieser Artikel hilft Ihnen, den Schutz in Ihrem Microsoft 365 zu erhöhen, um sich vor Phishing, Schadsoftware und anderen Bedrohungen zu schützen. Diese Empfehlungen sind für Organisationen mit erhöhtem Sicherheitsbedarf geeignet, z. B. für politische Kampagnen, Anwaltskanzleien und Gesundheitseinrichtungen.

Bevor Sie beginnen, überprüfen Sie Ihre Microsoft Secure Score. Microsoft Secure Score analysiert die Sicherheit Ihrer Organisation basierend auf Ihren regulären Aktivitäten und Sicherheitseinstellungen und weist eine Bewertung zu. Notieren Sie sich zunächst Ihre aktuelle Bewertung. Wenn Sie die in diesem Artikel empfohlenen Aktionen ausführen, wird Ihre Bewertung erhöht. Das Ziel ist nicht, die maximale Punktzahl zu erreichen, sondern die Möglichkeiten zum Schutz Ihrer Umgebung zu kennen, die sich nicht negativ auf die Produktivität ihrer Benutzer auswirken.

Weitere Informationen finden Sie unter [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Erhöhen des Schutzniveaus vor Schadsoftware in E-Mails

Ihre Office 365 oder Microsoft 365 umfasst Schutz vor Schadsoftware. Sie können diesen Schutz jedoch erhöhen, indem Sie Anlagen mit Dateitypen blockieren, die häufig für Schadsoftware verwendet werden. So stoßen Sie den Schutz vor Schadsoftware in E-Mails an:

1. Wechseln Sie <https://protection.office.com> zu und melden Sie sich mit Ihren Administratorkontoanmeldeinformationen an.

2. Wählen Sie im Security & Compliance Center im linken Navigationsbereich unter Bedrohungsverwaltung die Option  \> **Richtlinien-Anti-Malware aus.**

3. Doppelklicken Sie auf die Standardrichtlinie, um diese unternehmensweite Richtlinie zu bearbeiten.

4. Klicken Sie auf **Einstellungen**.

5. Wählen **Sie unter Filter für allgemeine Anlagentypen** die Option Ein **aus.** Die blockierten Dateitypen werden im Fenster direkt unterhalb dieses Steuerelements aufgeführt. Stellen Sie sicher, dass Sie die folgenden Dateitypen hinzufügen:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Sie können Dateitypen bei Bedarf später hinzufügen oder löschen.

6. Klicken Sie auf **Speichern**.

Weitere Informationen finden Sie unter [Schutz vor Schadsoftware in EOP](../security/office-365-security/anti-malware-protection.md).

## <a name="protect-against-ransomware"></a>Schutz vor Ransomware

Ransomware schränkt den Zugriff auf Daten ein, indem Dateien verschlüsselt oder Computerbildschirme gesperrt werden. Anschließend versucht sie, Geld von Denkgeschädigten zu erpressen, indem sie "Lösegeld" fordert, in der Regel in Form von Kryptowährungen wie z. B. Bitcoin, im Austausch für den Zugriff auf Daten.

Sie können vor Ransomware schützen, indem Sie eine oder mehrere Nachrichtenflussregeln erstellen, um Dateierweiterungen zu blockieren, die häufig für Ransomware verwendet werden (diese wurden im Erhöhen des Schutzniveaus vor Schadsoftware [im](#raise-the-level-of-protection-against-malware-in-mail) E-Mail-Schritt hinzugefügt) oder um Benutzer zu warnen, die diese Anlagen in E-Mails erhalten.

Zusätzlich zu den Dateien, die Sie im vorherigen Schritt blockiert haben, ist es auch eine bewährte Methode, eine Regel zum Warnen von Benutzern zu erstellen, bevor sie Office Dateianlagen öffnen, die Makros enthalten. Ransomware kann in Makros ausgeblendet werden, daher warnen Sie Benutzer davor, diese Dateien vor Personen zu öffnen, die sie nicht kennen.

So erstellen Sie eine E-Mail-Transportregel:

1. Wechseln Sie zum Admin Center <https://admin.microsoft.com> unter, und wählen Sie **Admin Center** \> **Exchange**.

2. Klicken Sie **in der** Kategorie Nachrichtenfluss auf **Regeln**.

3. Klicken **+** Sie auf , und klicken Sie dann auf Neue Regel **erstellen**.

4. Klicken **Sie unten im** Dialogfeld auf Weitere Optionen, um den vollständigen Satz von Optionen anzuzeigen.

5. Wenden Sie die Einstellungen in der folgenden Tabelle für die Regel an. Lassen Sie die restlichen Einstellungen bei der Standardeinstellung, es sei denn, Sie möchten sie ändern.

6. Klicken Sie auf **Speichern**.

|Setting|Warnen Von Benutzern vor dem Öffnen von Anlagen Office Dateien|
|---|---|
|Name|Anti-Ransomware-Regel: Benutzer warnen|
|Wenden Sie diese Regel an, wenn . . .|Jede Anlage . . . Dateierweiterung entspricht . . .|
|Angeben von Wörtern oder Ausdrücken|Fügen Sie die folgenden Dateitypen hinzu: <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|Gehen Sie wie folgt vor. . .|Empfänger durch Nachricht benachrichtigen|
|Bereitstellen von Nachrichtentext|Öffnen Sie diese Dateitypen nicht von Personen, die Sie nicht kennen, da sie Möglicherweise Makros mit bösartigem Code enthalten.|

Weitere Informationen finden Sie unter:

- [Ransomware: Verringern des Risikos](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Wiederherstellen ihrer OneDrive](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>Beenden der automatischen Weiterleitung für E-Mails

Hacker, die Zugriff auf das Postfach eines Benutzers erhalten, können Ihre E-Mails stehlen, indem sie das Postfach so festlegen, dass E-Mails automatisch weitergeleitet werden. Dies kann auch ohne das Bewusstsein des Benutzers geschehen. Sie können dies verhindern, indem Sie eine Nachrichtenflussregel konfigurieren.

Um eine E-Mail-Transportregel zu erstellen, sehen Sie sich entweder [dieses kurze Video an,](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) oder führen Sie die folgenden Schritte aus:

1. Klicken Sie Microsoft 365 Admin Center auf **Admin Center** \> **Exchange**.

2. Klicken Sie **in der** Kategorie Nachrichtenfluss auf **Regeln**.

3. Klicken **+** Sie auf , und klicken Sie dann auf Neue Regel **erstellen**.

4. Klicken **Sie unten im** Dialogfeld auf Weitere Optionen, um den vollständigen Satz von Optionen anzuzeigen.

5. Wenden Sie die Einstellungen in der folgenden Tabelle an. Lassen Sie die restlichen Einstellungen bei der Standardeinstellung, es sei denn, Sie möchten sie ändern.

6. Klicken Sie auf **Speichern**.

|Setting|Warnen Von Benutzern vor dem Öffnen von Anlagen Office Dateien|
|---|---|
|Name|Verhindern der automatischen Weiterleitung von E-Mails an externe Domänen|
|Wenden Sie diese Regel an, wenn ...|Der Absender . . . ist extern/intern . . . Innerhalb der Organisation|
|Bedingung hinzufügen|Die Nachrichteneigenschaften . . . geben Sie den Nachrichtentyp ein. . . Automatische Weiterleitung|
|Gehen Sie wie folgt vor...|Blockieren der Nachricht . . . die Nachricht ablehnen und eine Erläuterung enthalten.|
|Bereitstellen von Nachrichtentext|Die automatische Weiterleitung von E-Mails außerhalb dieser Organisation wird aus Sicherheitsgründen verhindert.|

## <a name="protect-your-email-from-phishing-attacks"></a>Schützen Ihrer E-Mails vor Phishingangriffen

Wenn Sie eine oder mehrere benutzerdefinierte Domänen für Ihre Office 365 oder Microsoft 365 konfiguriert haben, können Sie gezielten Antiphishingschutz konfigurieren. Der Antiphishingschutz, der Teil von Microsoft Defender for Office 365 ist, kann Ihre Organisation vor phishingbasierten Phishingangriffen und anderen Phishingangriffen durch böswilligen Identitätswechsel schützen. Wenn Sie keine benutzerdefinierte Domäne konfiguriert haben, müssen Sie dies nicht tun.

Es wird empfohlen, mit diesem Schutz zu beginnen, indem Sie eine Richtlinie zum Schutz Ihrer wichtigsten Benutzer und Ihrer benutzerdefinierten Domäne erstellen.

Um eine Antiphishingrichtlinie in Defender for Office 365 zu erstellen, sehen Sie sich dieses kurze Schulungsvideo [an,](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie zu <https://protection.office.com>.

2. Wählen Sie im Security & Compliance Center im linken Navigationsbereich unter Bedrohungsverwaltung die Option **Richtlinie aus.**

3. Wählen Sie **auf der** Seite Richtlinie die Option **Antiphishing aus.**

4. Wählen Sie **auf der Seite Antiphishing** die Option **+ Erstellen aus.** Ein Assistent startet Sie durch die Definition Ihrer Antiphishingrichtlinie.

5. Geben Sie den Namen, die Beschreibung und die Einstellungen für Ihre Richtlinie wie im folgenden Diagramm empfohlen an. Weitere Informationen finden Sie [unter Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/office-365-security/set-up-anti-phishing-policies.md).

6. Nachdem Sie Ihre Einstellungen überprüft haben, wählen Sie Diese Richtlinie **erstellen** oder **Speichern** aus.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Domäne und wertvollste Mitarbeiter|
|Beschreibung|Stellen Sie sicher, dass die wichtigsten Mitarbeiter und unsere Domäne nicht als Identitätswechsel verwendet werden.|
|Zu schützende Benutzer hinzufügen|Select **+ Add a condition, The recipient is**. Geben Sie Benutzernamen ein, oder geben Sie die E-Mail-Adresse der Geschäftsbesitzer, Partner oder Kandidaten, Manager und anderer wichtiger Mitarbeiter ein. Sie können bis zu 20 interne und externe Adressen hinzufügen, die Sie vor Identitätswechseln schützen möchten.|
|Zu schützende Domänen hinzufügen|Select **+ Add a condition, The recipient domain is**. Geben Sie die benutzerdefinierte Domäne ein, die Ihrem Microsoft 365 zugeordnet ist, wenn Sie eine definiert haben. Sie können mehrere Domänen eingeben.|
|Aktionen auswählen|Wenn E-Mails von einem identitätswechselten Benutzer gesendet werden: Wählen Sie **Nachricht** an eine andere E-Mail-Adresse umleiten aus, und geben Sie dann die E-Mail-Adresse des Sicherheitsadministrators ein. Beispiel: *Alice <span> <span> @contoso.com*. <br/> Wenn eine E-Mail von einer imitierten Domäne gesendet wird: Wählen Sie **Nachricht in Quarantäne verschieben** aus.|
|Mailbox Intelligence|Standardmäßig wird die Mailbox Intelligence ausgewählt, wenn Sie eine neue Anti-Phishing-Richtlinie erstellen. Lassen Sie diese Einstellung auf **Ein**, um optimale Ergebnisse zu erzielen.|
|Vertrauenswürdige Absender und Domänen hinzufügen|Hier können Sie Ihre eigene Domäne oder andere vertrauenswürdige Domänen hinzufügen.|
|Angewendet auf|Wählen Sie **Die Domäne des Empfängers ist** aus. Wählen Sie unter **Einer dieser**, **Auswählen** aus. Wählen Sie **+ Hinzufügen** aus. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, z. B. *contoso. <span> <span> com*, in der Liste, und wählen Sie dann **Hinzufügen aus.** Wählen Sie **Fertig** aus.|

Weitere Informationen finden Sie unter [Einrichten von Antiphishingrichtlinien in Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a>Schutz vor schädlichen Anlagen, Dateien und Links mit Defender for Office 365

![Banner, das auf https://aka.ms/aboutM365preview .](../media/m365admincenterchanging.png)

Stellen Sie zunächst sicher, dass sie im Admin Center aktiviert ist, wenn die Vorschau des <https://admin.microsoft.com> neuen Admin Centers aktiviert ist. Aktivieren Sie den Umschalter neben dem Text **Das neue Admin Center**.

   ![Die neue Admin Center-Vorschau auf.](../media/previewon.png)

Wenn die Seite Setup  mit Karten in Ihrem Mandanten noch nicht angezeigt wird, erfahren Sie, wie Sie diese Schritte im Security & Compliance Center ausführen. Weitere Informationen finden Sie unter Einrichten sicherer Anlagen [im Security & Compliance Center](#set-up-safe-attachments-in-the-security--compliance-center) und Einrichten sicherer Links im Security & Compliance [Center](#set-up-safe-links-in-the-security--compliance-center).

1. Wählen Sie im linken Navigationsgerät **Setup aus.**
2. Wählen Sie **auf der Seite Setup** die Option **Ansicht** auf der Karte Schutz vor **erweiterten Bedrohungen** erhöhen aus.

   ![Wählen Sie Ansicht unter Erhöhen des Schutzes vor erweiterten Bedrohungen aus.](../media/startatp.png)

3. Wählen Sie **auf der Seite Schutz vor erweiterten Bedrohungen** erhöhen die Option Erste Schritte **aus.**
4. Aktivieren Sie im geöffneten Bereich die Kontrollkästchen links **and attachments in email**, Scan files in **SharePoint, OneDrive, and Teams** und Scan links in Office desktop and Office Online **apps** under Scan items for **malicious content**.

   Geben **Sie unter Links und Anlagen in E-Mail** alle Benutzer oder die bestimmten Benutzer ein, deren E-Mails gescannt werden sollen.

   ![Aktivieren Sie alle Kontrollkästchen unter Erhöhen des Schutzes vor erweiterten Bedrohungen.](../media/setatp.png)

5. Wählen **Sie Richtlinien erstellen** aus, um sichere Anlagen und sichere Links zu aktivieren.

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a>Einrichten sicherer Anlagen im Security & Compliance Center

Personen senden, empfangen und teilen anlagen, z. B. Dokumente, Präsentationen, Tabellen und vieles mehr. Es ist nicht immer einfach zu bestimmen, ob eine Anlage sicher oder bösartig ist, indem Sie sich eine E-Mail-Nachricht anschauen. Microsoft Defender for Office 365 enthält sicheren Anlagenschutz, dieser Schutz ist jedoch nicht standardmäßig aktiviert. Es wird empfohlen, eine neue Regel zu erstellen, um mit der Verwendung dieses Schutzes zu beginnen. Dieser Schutz erstreckt sich auf Dateien in SharePoint, OneDrive und Microsoft Teams.

Um eine Richtlinie für sichere Anlagen zu erstellen, sehen Sie sich entweder dieses [kurze](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)Video an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie <https://protection.office.com> zu, und melden Sie sich mit Ihrem Administratorkonto an.

2. Wählen Sie im Security & Compliance Center im linken Navigationsbereich unter Bedrohungsverwaltung die Option **Richtlinie aus.**

3. Wählen Sie auf der Seite Richtlinie die Option **Sichere Anlagen aus.**

4. Wenden Sie diesen Schutz auf der Seite Sichere Anlagen allgemein an, indem Sie das Kontrollkästchen ATP für **SharePoint,** OneDrive und Microsoft Teams aktivieren aktivieren.

5. Wählen **+** Sie diese Option aus, um eine neue Richtlinie zu erstellen.

6. Wenden Sie die Einstellungen in der folgenden Tabelle an.

7. Nachdem Sie Ihre Einstellungen überprüft haben, wählen Sie **Diese Richtlinie erstellen** oder **Speichern** aus, wenn dies der Richtige ist.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Blockieren Sie aktuelle und zukünftige E-Mails mit erkannter Schadsoftware.|
|Beschreibung|Blockieren Sie aktuelle und zukünftige E-Mails und Anlagen mit erkannter Schadsoftware.|
|Speichern von Anlagen unbekannte Schadsoftwareantwort|Wählen Sie Blockieren – Blockieren der aktuellen und zukünftigen **E-Mails und Anlagen mit erkannter Schadsoftware aus.**|
|Umleitungsanlage bei Erkennung|Umleitung aktivieren (aktivieren Sie dieses Feld) <br/> Geben Sie das Administratorkonto oder eine Postfacheinrichtung für die Quarantäne ein. <br/> Wenden Sie die oben aufgeführte Auswahl an, wenn bei der Schadsoftwareprüfung auf Anlagen ein Zeitfehler auftritt oder ein Fehler auftritt (aktivieren Sie dieses Feld).|
|Angewendet auf|Die Empfängerdomäne ist . . . Wählen Sie Ihre Domäne aus.|

Weitere Informationen finden Sie unter [Einrichten von Antiphishingrichtlinien in Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).

### <a name="set-up-safe-links-in-the-security--compliance-center"></a>Einrichten sicherer Links im Security & Compliance Center

Hacker verbergen bösartige Websites manchmal in Links in E-Mails oder anderen Dateien. Sichere Links, die Teil von Microsoft Defender for Office 365 sind, können Zum Schutz Ihrer Organisation beitragen, indem Sie die Überprüfung von Webadressen (URLs) in E-Mail-Nachrichten und dokumenten Office bereitstellen. Der Schutz wird durch Richtlinien für sichere Links definiert.

Es wird empfohlen, die folgenden Schritte zu tun:

- Ändern Sie die Standardrichtlinie, um den Schutz zu erhöhen.

- Fügen Sie eine neue Richtlinie für alle Empfänger in Ihrer Domäne hinzu.

Zum Einrichten sicherer Links sehen Sie sich [dieses kurze Schulungsvideo an,](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie <https://protection.office.com> zu, und melden Sie sich mit Ihrem Administratorkonto an.

2. Wählen Sie im Security & Compliance Center im linken Navigationsbereich unter Bedrohungsverwaltung die Option **Richtlinie aus.**

3. Wählen Sie auf der Seite Richtlinie die Option **Sichere Links aus.**

So ändern Sie die Standardrichtlinie:

1. Wählen Sie auf der Seite Sichere Links unter **Richtlinien, die für** die gesamte Organisation gelten, die **Standardrichtlinie** aus.

2. Wählen **Einstellungen, die für Inhalte** außer E-Mail gelten, **Microsoft 365 Apps for Enterprise, Office für iOS und Android aus.**

3. Klicken Sie auf **Speichern**.

So erstellen Sie eine neue Richtlinie für alle Empfänger in Ihrer Domäne:

1. Klicken Sie auf der Seite Sichere Links unter **Richtlinien, die für** die gesamte Organisation gelten, auf, **+** um eine neue Richtlinie zu erstellen.

2. Wenden Sie die in der folgenden Tabelle aufgeführten Einstellungen an.

3. Klicken Sie auf **Speichern**.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Richtlinie für sichere Links für alle Empfänger in der Domäne|
|Auswählen der Aktion für unbekannte potenziell schädliche URLs in Nachrichten|Select **On – URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.|
|Verwenden sicherer Anlagen zum Überprüfen herunterladbarer Inhalte|Wählen Sie dieses Feld aus.|
|Angewendet auf|Die Empfängerdomäne ist . . . Wählen Sie Ihre Domäne aus.|

Weitere Informationen finden Sie unter [Safe Links in Defender for Office 365](../security/office-365-security/safe-links.md).

## <a name="turn-on-the-unified-audit-log"></a>Aktivieren des einheitlichen Überwachungsprotokolls

Nachdem Sie die Überwachungsprotokollsuche im Security & Compliance Center aktivieren, können Sie den Administrator und andere Benutzeraktivitäten im Protokoll beibehalten und durchsuchen.

Ihnen muss die Rolle Überwachungsprotokolle in Exchange Online zugewiesen werden, um die Überwachungsprotokollsuche in Ihrem Abonnement Microsoft 365 aktivieren oder deaktivieren. Diese Rolle wird standardmäßig den Rollengruppen Complianceverwaltung und Organisationsverwaltung auf der Seite Berechtigungen im Exchange zugewiesen. Globale Administratoren in Microsoft 365 sind standardmäßig Mitglieder dieser Gruppe.

1. Um die Überwachungsprotokollsuche zu aktivieren, wechseln Sie zum Admin Center unter, und wählen Sie dann Sicherheit unter <https://admin.microsoft.com> **Admin Center** im linken  Navigationsgerät aus.
2. Wählen Sie Microsoft 365 **Seite Sicherheit** die Option **Weitere** Ressourcen aus, und öffnen Sie dann auf der Office 365 **Security & Compliance Center-Karte.** 

    ![Wählen Sie Auf der Sicherheits-&-Autos öffnen aus.](../media/gotosecandcomp.png)
3. Wählen Sie auf der Seite Sicherheit und Compliance die Option **Suchen** und dann **Überwachungsprotokollsuche aus.**
4. Wählen Sie oben auf der Seite **Überwachungsprotokollsuche** die Option Überwachung **aktivieren aus.**

Nachdem das Feature aktiviert wurde, können Sie nach Dateien, Ordnern und vielen Aktivitäten suchen. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls](../compliance/search-the-audit-log-in-security-and-compliance.md).

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders&quot;></a>Optimieren der Einstellungen für die anonyme Freigabe SharePoint und OneDrive Dateien und Ordnern

(Ändern Sie den Standardmäßigen Ablauf anonymer Links auf 14 Tage, ändern Sie den Standardfreigabetyp in &quot;Bestimmte Personen") So ändern Sie die Freigabeeinstellungen für OneDrive und SharePoint:

1. Wechseln Sie zum Admin Center unter, und wählen Sie dann SharePoint im linken Navigations navi unter <https://admin.microsoft.com> Admin **Center** aus. 
2. Wechseln Sie SharePoint Admin Center zu  \> **Richtlinienfreigabe**.
3. Wählen  Sie auf der Seite Freigabe unter Datei- und Ordnerlinks die Option Bestimmte Personen aus, und wählen Sie unter Erweiterte Einstellungen für **"Jeder"-Links** die Option Diese Links müssen innerhalb dieser vielen Tage ablaufen **und** geben Sie in 14 (oder eine andere Anzahl von Tagen, auf die Sie die Linklebensdauer beschränken möchten) ein. 

   ![Wählen Sie Bestimmte Personen aus, und legen Sie den Linkablauf auf 14 Tage an.](../media/anyonelinks.png)

## <a name="activity-alerts"></a>Aktivitätswarnungen

Sie können Aktivitätswarnungen verwenden, um Administrator- und Benutzeraktivitäten nachverfolgt und Schadsoftware- und Verhinderungsvorfälle in Ihrer Organisation zu erkennen. Ihr Abonnement enthält eine Reihe von Standardrichtlinien, Sie können jedoch auch benutzerdefinierte Richtlinien erstellen. Weitere Informationen finden Sie unter [Warnungsrichtlinien](../compliance/alert-policies.md). Wenn Sie z. B. eine wichtige Datei in SharePoint speichern, die von niemandem extern gemeinsam verwendet werden soll, können Sie eine Benachrichtigung erstellen, die Sie benachrichtigt, wenn sie von jemandem gemeinsam verwendet wird.

Die folgende Abbildung zeigt die Standardrichtlinien, die in der Microsoft 365.

![Standardmäßige Benachrichtigungsrichtlinien, die in Microsoft 365](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>Deaktivieren oder Verwalten der Kalenderfreigabe

Sie können verhindern, dass Personen in Ihrer Organisation ihre Kalender freigeben, oder Sie können auch verwalten, was sie freigeben können. Beispielsweise können Sie die Freigabe nur auf Frei/Gebucht-Zeiten beschränken.

1. Wechseln Sie zum Admin Center <https://admin.microsoft.com> unter, und wählen **Sie Einstellungen** \> **Org Einstellungen**.
2. Wählen Sie **auf** der Seite Dienste kalender **aus,** und wählen Sie aus, ob Personen in Ihrer Organisation ihre Kalender für Personen außerhalb von Personen freigeben können, die Office 365 oder Exchange oder für andere Personen haben.

   Wenn Sie die Freigabe für alle Benutzer auswählen, können Sie auch nur Frei/Gebucht-Informationen freigeben.

3. Klicken **Sie unten auf** der Seite auf Änderungen speichern.

   Die folgende Abbildung zeigt, dass die Kalenderfreigabe nicht zulässig ist.

   ![Screenshot der Anzeige der externen Kalenderfreigabe als nicht zulässig.](../media/nocalendarsharing.png)

   Die folgende Abbildung zeigt die Einstellungen, wenn die Kalenderfreigabe mit einem E-Mail-Link mit nur Frei/Gebucht-Informationen zulässig ist.

   ![Screenshot der Frei/Gebucht-Freigabe des Kalenders für alle Personen.](../media/sharefreebusy.png)

Wenn Ihre Benutzer ihre Kalender freigeben [](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) dürfen, lesen Sie diese Anweisungen zum Freigeben von Outlook im Web.
