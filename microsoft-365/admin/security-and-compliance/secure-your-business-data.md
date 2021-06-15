---
title: Die 10 wichtigsten Möglichkeiten zum Sichern von Microsoft 365 für Business-Pläne
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: So schützen Sie Ihre Geschäftlichen E-Mails und Daten vor Cyberbedrohungen, einschließlich Ransomware, Phishing und bösartigen Anlagen.
ms.openlocfilehash: a5d87c907d47be2d8edc12642ad4e93afb0eb142
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924623"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>Die 10 wichtigsten Möglichkeiten zum Sichern von Microsoft 365 für Business-Pläne

Wenn Sie eine kleine oder mittelständische Organisation sind, die einen der Geschäftspläne von Microsoft verwendet und Ihre Art von Organisation von Cyberkriminellen und Hackern ausgerichtet ist, verwenden Sie die Anleitung in diesem Artikel, um die Sicherheit Ihrer Organisation zu erhöhen. Dieser Leitfaden hilft Ihrer Organisation, die ziele zu erreichen, die im Handbuch zur [Cybersicherheitskampagne](https://go.microsoft.com/fwlink/p/?linkid=2015598)der Schule "Schule" beschrieben sind.

Microsoft empfiehlt, die in der folgenden Tabelle aufgeführten Aufgaben auszuführen, die für Ihren Serviceplan gelten.

|*Number*|Aufgabe|Microsoft 365 Business Standard|Microsoft 365 Business Premium|
|---|---|---|---|
|1|[Einrichten der mehrstufigen Authentifizierung](secure-your-business-data.md#setup)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2|[Schulen der Benutzer](secure-your-business-data.md#train)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[Verwenden dedizierter Administratorkonten](secure-your-business-data.md#admin)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4 |[Erhöhen des Schutzes vor Schadsoftware in E-Mails](secure-your-business-data.md#malware)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5 |[Schutz vor Ransomware](secure-your-business-data.md#ransomware)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[Beenden der automatischen Weiterleitung für E-Mails](secure-your-business-data.md#forwarding)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[Verwenden Office Nachrichtenverschlüsselung](secure-your-business-data.md#encryption)||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[Schützen Ihrer E-Mails vor Phishingangriffen](secure-your-business-data.md#phishing)||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[Schutz vor bösartigen Anlagen und Dateien mit sicheren Anlagen](secure-your-business-data.md#atp)||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10|[Schutz vor Phishingangriffen mit sicheren Links](secure-your-business-data.md#phishingatp)||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

Wenn Sie über Microsoft Business Premium verfügen, können Sie die Sicherheit am schnellsten einrichten und mit der sicheren Zusammenarbeit beginnen, wenn Sie die Anweisungen in dieser Bibliothek befolgen: [Microsoft 365 für kleinere Unternehmen und Kampagnen](../../campaigns/index.md). Diese Anleitung wurde in Zusammenarbeit mit dem Microsoft-Team „Defending Democracy“ entwickelt, um alle kleinen Unternehmenskunden vor Cyberbedrohungen zu schützen, die von raffinierten Hackern gestartet werden.

Bevor Sie beginnen, überprüfen Sie Ihre [Microsoft 365 Sicherheitsbewertung](../../security/defender/microsoft-secure-score.md) im Microsoft 365 Security Center. Über ein zentrales Dashboard können Sie die Sicherheit Ihrer Microsoft 365 Identitäten, Daten, Apps, Geräte und Infrastruktur überwachen und verbessern. Sie erhalten Punkte für die Konfiguration empfohlener Sicherheitsfeatures, das Ausführen sicherheitsrelevanter Aufgaben (z. B. das Anzeigen von Berichten) oder das Adressieren von Empfehlungen mit einer Drittanbieteranwendung oder -software. Mit zusätzlichen Einblicken und mehr Einblicken in eine breitere Palette von Microsoft-Produkten und -Diensten können Sie sich sicher über die Sicherheitsintegrität Ihrer Organisation berichten.

![Screenshot der Microsoft-Sicherheitsbewertung](../../media/secure-score.png)

## <a name="1-set-up-multi-factor-authentication"></a>1: Einrichten der mehrstufigen Authentifizierung
<a name="setup"> </a>

Die Verwendung der mehrstufigen Authentifizierung ist eine der einfachsten und effektivsten Methoden, um die Sicherheit Ihrer Organisation zu erhöhen. Es ist einfacher, als es klingt – wenn Sie sich anmelden, bedeutet die mehrstufige Authentifizierung, dass Sie einen Code von Ihrem Telefon eingeben, um Zugriff auf Microsoft 365 zu erhalten. Dies kann verhindern, dass Hacker die Übernahme übernehmen, wenn sie Ihr Kennwort kennen. Die mehrstufige Authentifizierung wird auch als zweistufige Überprüfung bezeichnet. Einzelpersonen können den meisten Konten problemlos eine zweistufige Überprüfung hinzufügen, z. B. zu ihren Google- oder Microsoft-Konten. Hier erfahren Sie, wie [Sie Ihrem persönlichen Microsoft-Konto eine zweistufige Überprüfung hinzufügen.](https://go.microsoft.com/fwlink/p/?linkid=2016403)

Fügen Sie für Unternehmen, die Microsoft 365 verwenden, eine Einstellung hinzu, die erfordert, dass sich Ihre Benutzer mithilfe der mehrstufigen Authentifizierung anmelden. Wenn Sie diese Änderung vornehmen, werden Die Benutzer aufgefordert, ihr Telefon für die zweistufige Authentifizierung einzurichten, wenn sie sich das nächste Mal anmelden.
Ein Schulungsvideo zum Einrichten von MFA und zum Abschließen der Einrichtung durch die Benutzer finden Sie unter Einrichten der [MFA](../../business-video/turn-on-mfa.md) und [der Benutzereinrichtung.](../../business-video/set-up-mfa.md)

Um die mehrstufige Authentifizierung einzurichten, aktivieren Sie die Sicherheitsstandards:

In den meisten Organisationen bieten Sicherheitsstandards ein gutes Maß an zusätzlicher Anmeldesicherheit. Weitere Informationen hierzu finden Sie unter [Was sind Sicherheitsstandards?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Wenn Ihr Abonnement neu ist, sind die Sicherheitsstandards möglicherweise bereits automatisch für Sie aktiviert.

Die Standardsicherheitseinstellungen können Sie im Azure-Portal im Bereich **Einstellungen** für Active Directory (Azure AD) aktivieren oder deaktivieren.

1. Melden Sie sich mit den Anmeldeinformationen des globalen Administrators beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.
2. Wählen Sie im linken Navigationsbereich **Alle anzeigen** und dann unter **Admin Center** die Option **Azure Active Directory** aus.
3. Im **Azure Active Directory Admin Center** wählen Sie dann **Azure Active Directory** > **Eigenschaften** aus.
4. Wählen Sie unten auf der Seite **Sicherheitsstandards verwalten** aus.
5. Wählen Sie **Ja** aus, um die zu aktivieren oder **Nein**, um die Sicherheitsstandards zu deaktivieren. Klicken Sie anschließend auf **Speichern**.

Nachdem Sie die mehrstufige Authentifizierung für Ihre Organisation eingerichtet haben, müssen die Benutzer auf ihren Geräten die Prüfung in zwei Schritten einrichten. Weitere Informationen finden Sie unter Einrichten der [zweistufigen Überprüfung für Microsoft 365.](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)

Ausführliche Informationen und vollständige Empfehlungen finden Sie unter Einrichten der [mehrstufigen Authentifizierung für Benutzer.](set-up-multi-factor-authentication.md)

## <a name="2-train-your-users"></a>2: Schulen Ihrer Benutzer
<a name="train"> </a>

Das [Cybersicherheitskampagnenhandbuch](https://go.microsoft.com/fwlink/p/?linkid=2015598) der Schule Stellt hervorragende Anleitungen zum Aufbau einer starken Kultur des Sicherheitsbewusstseins in Ihrer Organisation bereit, einschließlich der Schulung von Benutzern zur Identifizierung von Phishingangriffen.

Zusätzlich zu diesem Leitfaden empfiehlt Microsoft Ihren Benutzern, die in diesem Artikel beschriebenen Maßnahmen zu ergreifen: [Schützen Ihres Kontos und Ihrer Geräte vor Hackern und Schadsoftware.](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6) Diese setzen sich wie folgt zusammen:

- Verwenden sicherer Kennwörter

- Schützen von Geräten

- Aktivieren von Sicherheitsfeatures auf Windows 10 und Mac-PCs

Microsoft empfiehlt außerdem, dass Benutzer ihre persönlichen E-Mail-Konten schützen, indem sie die in den folgenden Artikeln empfohlenen Maßnahmen ergreifen:

- [Schützen Ihres Outlook.com-E-Mail-Kontos](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Schützen Ihres Gmail-Kontos mit zweistufiger Überprüfung](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="3-use-dedicated-admin-accounts"></a>3: Verwenden dedizierter Administratorkonten
<a name="admin"> </a>

Zu den Verwaltungskonten, die Sie zum Verwalten Ihrer Microsoft 365 Umgebung verwenden, gehören erhöhte Rechte. Dies sind wertvolle Ziele für Hacker und Cyberkriminelle. Verwenden Sie Administratorkonten nur für die Verwaltung. Administratoren sollten über ein separates Benutzerkonto für die regelmäßige, nicht administrative Verwendung verfügen und ihr Administratorkonto nur dann verwenden, wenn dies erforderlich ist, um eine Aufgabe auszuführen, die mit ihrer Auftragsfunktion verknüpft ist. Zusätzliche Empfehlungen:

- Stellen Sie sicher, dass Administratorkonten auch für die mehrstufige Authentifizierung eingerichtet sind.

- Schließen Sie vor der Verwendung von Administratorkonten alle Browsersitzungen und Apps, die keine Beziehung haben, einschließlich persönlicher E-Mail-Konten.

- Stellen Sie nach Abschluss der Administratoraufgaben sicher, dass Sie sich bei der Browsersitzung abmelden.

## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4: Erhöhen des Schutzes vor Schadsoftware in E-Mails
<a name="malware"> </a>

Ihre Microsoft 365-Umgebung umfasst Schutz vor Schadsoftware. Sie können diesen Schutz jedoch erhöhen, indem Sie Anlagen mit Dateitypen blockieren, die häufig für Schadsoftware verwendet werden. Um den Schutz vor Schadsoftware in E-Mails zu verbessern, zeigen Sie ein [kurzes Schulungsvideo](../../business-video/anti-malware.md)an, oder führen Sie die folgenden Schritte aus:

1. Rufen Sie ihre <https://protection.office.com> Administratorkontoanmeldeinformationen auf, und melden Sie sich an.

2. Wählen Sie im Security & Compliance Center im linken Navigationsbereich unter **"Bedrohungsmanagement"** **die Option "Richtlinie** \> **antischadsoftware"** aus.

3. Doppelklicken Sie auf die Standardrichtlinie, um diese unternehmensweite Richtlinie zu bearbeiten.

4. Wählen Sie **Einstellungen** aus.

5. Wählen Sie unter **Filter für allgemeine Anlagentypen** die Option **"Ein"** aus. Die blockierten Dateitypen werden im Fenster direkt unterhalb dieses Steuerelements aufgelistet. Sie können Dateitypen später bei Bedarf hinzufügen oder löschen.

6. Wählen Sie **"Speichern" aus.**

Weitere Informationen finden Sie unter [Antischadsoftwareschutz in EOP.](../../security/office-365-security/anti-malware-protection.md)

## <a name="5-protect-against-ransomware"></a>5: Schutz vor Ransomware
<a name="ransomware"> </a>

Ransomware schränkt den Zugriff auf Daten ein, indem Dateien verschlüsselt oder Computerbildschirme gesperrt werden. Anschließend wird versucht, Geld von Denkzwecken zu erpressen, indem ein "Lösegeld" gefordert wird, in der Regel in Form von Enumerationen wie Demenzen, im Austausch für den Zugriff auf Daten.

Sie können sich vor Ransomware schützen, indem Sie eine oder mehrere Nachrichtenflussregeln erstellen, um Dateierweiterungen zu blockieren, die häufig für Ransomware verwendet werden, oder um Benutzer zu warnen, die diese Anlagen in E-Mails erhalten. Ein guter Ausgangspunkt ist das Erstellen von zwei Regeln:

- Warnen Sie Benutzer vor dem Öffnen Office Dateianlagen, die Makros enthalten. Ransomware kann in Makros verborgen sein, daher warnen wir Benutzer davor, diese Dateien von Personen zu öffnen, die sie nicht kennen.

- Blockieren Sie Dateitypen, die Ransomware oder anderen schädlichen Code enthalten könnten. Wir beginnen mit einer allgemeinen Liste ausführbarer Dateien (in der folgenden Tabelle aufgeführt). Wenn Ihre Organisation einen dieser ausführbaren Typen verwendet und Sie davon ausgehen, dass diese per E-Mail gesendet werden, fügen Sie diese zur vorherigen Regel hinzu (Warnen von Benutzern).

Um eine E-Mail-Transportregel zu erstellen, zeigen Sie ein [kurzes Schulungsvideo](../../business-video/prevent-ransom-in-email.md)an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie zum [Exchange Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. Wählen Sie in der **Nachrichtenflusskategorie** **Regeln** aus.

3. Wählen Sie **+** aus, und erstellen Sie dann **eine neue Regel.**

4. Wählen Sie am unteren Rand des Dialogfelds die Option aus, um den vollständigen Satz von Optionen anzuzeigen.

5. Wenden Sie die Einstellungen in der folgenden Tabelle für jede Regel an. Behalten Sie die restlichen Einstellungen standardmäßig bei, es sei denn, Sie möchten diese ändern.

6. Wählen Sie **Speichern** aus.
    
| Setting | Warnen von Benutzern vor dem Öffnen von Anlagen Office Dateien | Blockieren von Dateitypen, die Ransomware oder anderen schädlichen Code enthalten könnten |
|:-----|:-----|:-----|
|Name  <br/> |Anti-Ransomware-Regel: Benutzer warnen  <br/> |Anti-Ransomware-Regel: Blockieren von Dateitypen  <br/> |
|Wenden Sie diese Regel an, wenn . . .  <br/> |Jede Anlage . . . Dateierweiterung stimmt überein. . .  <br/> |Jede Anlage . . . Dateierweiterung stimmt überein. . .  <br/> |
|Angeben von Wörtern oder Ausdrücken  <br/> |Fügen Sie diese Dateitypen hinzu:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/> |Fügen Sie diese Dateitypen hinzu:  <br/> ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif  <br/> |
|Führen Sie die folgenden Schritte aus. . .  <br/> |Vorangestellter Haftungsausschluss  <br/> |Die Nachricht blockieren. . . Ablehnen der Nachricht und Einfügen einer Erklärung  <br/> |
|Bereitstellen von Nachrichtentext  <br/> |Öffnen Sie diese Dateitypen nur, wenn Sie sie erwartet haben, da die Dateien bösartigen Code enthalten können und der Absender nicht sicher ist.  <br/> ||
   
> [!TIP]
> Sie können auch die Dateien, die Sie blockieren möchten, der Liste der Antischadsoftware in [Schritt 4](#4-raise-the-level-of-protection-against-malware-in-mail)hinzufügen.

Weitere Informationen finden Sie unter:

- [Ransomware: So verringern Sie Risiken](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Wiederherstellen der OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="6-stop-auto-forwarding-for-email"></a>6: Beenden der automatischen Weiterleitung für E-Mails
<a name="forwarding"> </a>

Hacker, die Zugriff auf das Postfach eines Benutzers erhalten, können E-Mails exfiltrieren, indem sie das Postfach so konfigurieren, dass E-Mails automatisch weitergeleitet werden. Dies kann auch ohne das Bewusstsein des Benutzers erfolgen. Sie können dies verhindern, indem Sie eine Nachrichtenflussregel konfigurieren.

So erstellen Sie eine E-Mail-Transportregel:

1. Wechseln Sie zum [Exchange Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. Wählen Sie in der **Nachrichtenflusskategorie** **Regeln** aus.

3. Wählen Sie **+** aus, und erstellen Sie dann **eine neue Regel.**

4. Wählen Sie unten im Dialogfeld **weitere Optionen** aus, um den vollständigen Satz von Optionen anzuzeigen.

5. Wenden Sie die Einstellungen in der folgenden Tabelle an. Behalten Sie die restlichen Einstellungen standardmäßig bei, es sei denn, Sie möchten diese ändern.

6. Wählen Sie **Speichern** aus.

|Setting|Ablehnen der automatischen Weiterleitung von E-Mails an externe Domänen|
|---|---|
|Name|Verhindern der automatischen Weiterleitung von E-Mails an externe Domänen|
|Wenden Sie diese Regel an, wenn ...|Der Absender . . . ist extern/intern. . . Innerhalb der Organisation|
|Bedingung hinzufügen|Der Empfänger . . . ist extern/intern. . . Außerhalb der Organisation|
|Bedingung hinzufügen|Die Nachrichteneigenschaften . . . schließen Sie den Nachrichtentyp ein. . . Automatische Weiterleitung|
|Führen Sie die folgenden Schritte aus...|Die Nachricht blockieren. . . die Nachricht ablehnen und eine Erklärung einfügen.|
|Bereitstellen von Nachrichtentext|Die automatische Weiterleitung von E-Mails außerhalb dieser Organisation wird aus Sicherheitsgründen verhindert.|

## <a name="7-use-office-message-encryption"></a>7: Verwenden Office Nachrichtenverschlüsselung
<a name="encryption"> </a>

Office Nachrichtenverschlüsselung ist in Microsoft 365 enthalten. Sie ist bereits eingerichtet. Mit Office Nachrichtenverschlüsselung kann Ihre Organisation verschlüsselte E-Mail-Nachrichten zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen. Die Office 365-Nachrichtenverschlüsselung funktioniert mit Outlook.com, Yahoo!, Gmail und anderen E-Mail-Diensten. Die E-Mail-Nachrichtenverschlüsselung sorgt dafür, dass nur vorgesehene Empfänger verschlüsselte Nachrichten ansehen können.

Office Die Nachrichtenverschlüsselung bietet zwei Schutzoptionen beim Senden von E-Mails:

- Nicht weiterleiten

- Verschlüsseln

Möglicherweise hat Ihre Organisation zusätzliche Optionen konfiguriert, die eine Bezeichnung auf E-Mails anwenden, z. B. vertraulich.

### <a name="to-send-protected-email"></a>So senden Sie geschützte E-Mails

**Wählen** Sie in Outlook für PC optionen in der E-Mail aus, und wählen Sie dann **Berechtigungen** aus.

![E-Mail-Nachrichtenverschlüsselung in Outlook](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)

Wählen Sie in Outlook.com in der E-Mail die Option **"Schützen"** aus. Der Standardschutz lautet **"Nicht weiterleiten".** Wenn Sie dies in "Verschlüsseln" ändern möchten, wählen Sie **"Berechtigungen** \> **verschlüsseln"** aus.

![E-Mail-Nachrichtenverschlüsselung in Outlook.com](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)

### <a name="to-receive-encrypted-email"></a>So empfangen Sie verschlüsselte E-Mails

Wenn der Empfänger über Outlook 2013 oder Outlook 2016 und ein Microsoft-E-Mail-Konto verfügt, wird eine Warnung zu den eingeschränkten Berechtigungen des Elements im Lesebereich angezeigt. Nach dem Öffnen der Nachricht kann der Empfänger die Nachricht wie jede andere anzeigen.

Wenn der Empfänger einen anderen E-Mail-Client oder ein anderes E-Mail-Konto verwendet, z. B. Gmail oder Yahoo, wird ein Link angezeigt, über den er sich entweder anmelden kann, um die E-Mail-Nachricht zu lesen oder eine einmalige Kennung anzufordern, um die Nachricht in einem Webbrowser anzuzeigen. Wenn Benutzer die E-Mail nicht erhalten, müssen sie ihren Spam- oder Junk-Ordner überprüfen lassen.

Weitere Informationen finden Sie unter [Senden, Anzeigen und Antworten auf verschlüsselte Nachrichten in Outlook für PCs.](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)

## <a name="8-protect-your-email-from-phishing-attacks"></a>8. Schützen Ihrer E-Mails vor Phishingangriffen
<a name="phishing"> </a>

Wenn Sie eine oder mehrere benutzerdefinierte Domänen für Ihre Microsoft 365 Umgebung konfiguriert haben, können Sie den gezielten Antiphishingschutz konfigurieren. Der Antiphishingschutz, ein Bestandteil von Microsoft Defender für Office 365, kann Ihre Organisation vor böswilligen Phishingangriffen auf Identitätswechsel und anderen Phishingangriffen schützen. Wenn Sie keine benutzerdefinierte Domäne konfiguriert haben, müssen Sie dies nicht tun.

Wir empfehlen Ihnen, mit diesem Schutz zu beginnen, indem Sie eine Richtlinie zum Schutz Ihrer wichtigsten Benutzer und Ihrer benutzerdefinierten Domäne erstellen.

![Erstellen einer Antiphishingrichtlinie in Microsoft Defender für Office 365](../../media/security-and-compliance-center.png)

Um eine Antiphishingrichtlinie in Defender für Office 365 zu erstellen, zeigen Sie ein [kurzes Schulungsvideo](../../business-video/setup-anti-phishing.md)an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie zu <https://protection.office.com>.

2. Wählen Sie im Security & Compliance Center im linken Navigationsbereich unter **"Bedrohungsmanagement"** die Option **"Richtlinie"** aus.

3. Wählen Sie auf der Seite "Richtlinie" die Option **"Antiphishing"** aus.

4. Wählen Sie auf der Seite "Antiphishing" die Option **+ Erstellen** aus. Ein Assistent startet, der Sie durch die Definition Ihrer Antiphishingrichtlinie führt.

5. Geben Sie den Namen, die Beschreibung und die Einstellungen für Ihre Richtlinie wie im folgenden Diagramm empfohlen an. Weitere Informationen zu den Optionen für Office 365 finden Sie unter "Informationen zur [Antiphishingrichtlinie in Microsoft Defender".](../../security/office-365-security/set-up-anti-phishing-policies.md)

6. Nachdem Sie Ihre Einstellungen überprüft haben, wählen **Sie diese Richtlinie** erstellen oder **speichern** aus.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Domänen- und wertvollste Kampagnenmitarbeiter|
|Beschreibung|Stellen Sie sicher, dass die wichtigsten Mitarbeiter und unsere Domäne nicht imitiert werden.|
|Zu schützende Benutzer hinzufügen|Select **+ Add a condition, The recipient is**. Geben Sie Benutzernamen ein, oder geben Sie die E-Mail-Adresse des Kandidaten, Kampagnenmanagers und anderer wichtiger Mitarbeiter ein. Sie können bis zu 20 interne und externe Adressen hinzufügen, die Sie vor Identitätswechsel schützen möchten.|
|Zu schützende Domänen hinzufügen|Wählen Sie **+ Bedingung hinzufügen, die Empfängerdomäne lautet**. Geben Sie die benutzerdefinierte Domäne ein, die Ihrem Microsoft 365-Abonnement zugeordnet ist, sofern Sie eine definiert haben. Sie können mehrere Domänen eingeben.|
|Aktionen auswählen|Wenn E-Mails von einem imitierten Benutzer gesendet werden: Wählen Sie **"Nachricht an eine andere E-Mail-Adresse umleiten"** aus, und geben Sie dann die E-Mail-Adresse des Sicherheitsadministrators ein. Beispielsweise securityadmin@contoso.com. <br/> Wenn E-Mails von einer imitierten Domäne gesendet werden: Wählen Sie **"Quarantänenachricht"** aus.|
|Mailbox Intelligence|Standardmäßig wird die Mailbox Intelligence ausgewählt, wenn Sie eine neue Anti-Phishing-Richtlinie erstellen. Lassen Sie diese Einstellung auf **Ein**, um optimale Ergebnisse zu erzielen.|
|Vertrauenswürdige Absender und Domänen hinzufügen|Definieren Sie in diesem Beispiel keine Außerkraftsetzungen.|
|Angewendet auf|Wählen Sie **Die Domäne des Empfängers ist** aus. Wählen Sie unter **Einer dieser**, **Auswählen** aus. Wählen Sie **+ Hinzufügen** aus. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, z. B. contoso.com, in der Liste, und wählen Sie dann **Hinzufügen** aus. Wählen Sie **Fertig** aus.|
|

Weitere Informationen finden Sie unter [Einrichten von Antiphishingrichtlinien in Defender für Office 365.](../../security/office-365-security/configure-atp-anti-phishing-policies.md)

## <a name="9-protect-against-malicious-attachments-and-files-with-safe-attachments"></a>9: Schutz vor bösartigen Anlagen und Dateien mit sicheren Anlagen
<a name="atp"> </a>

Personen senden, empfangen und teilen regelmäßig Anlagen, z. B. Dokumente, Präsentationen, Tabellenkalkulationen und vieles mehr. Es ist nicht immer einfach, anhand einer E-Mail-Nachricht zu erkennen, ob eine Anlage sicher oder bösartig ist. Microsoft Defender für Office 365 umfasst den Schutz sicherer Anlagen, dieser Schutz ist jedoch nicht standardmäßig aktiviert. Es wird empfohlen, eine neue Regel zu erstellen, um mit der Verwendung dieses Schutzes zu beginnen. Dieser Schutz gilt für Dateien in SharePoint, OneDrive und Microsoft Teams.

Um eine Richtlinie für sichere Anlagen zu erstellen, zeigen Sie ein [kurzes Schulungsvideo](../../business-video/safe-attachments.md)an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie zu <https://protection.office.com> Ihrem Administratorkonto, und melden Sie sich an.

2. Wählen Sie im Security & Compliance Center im linken Navigationsbereich unter **"Bedrohungsmanagement"** die Option **"Richtlinie"** aus.

3. Wählen Sie auf der Seite "Richtlinie" die Option **"Sichere Anlagen" aus.**

4. Wenden Sie diesen Schutz auf der Seite "Sichere Anlagen" allgemein an, indem Sie das Kontrollkästchen **ATP für SharePoint, OneDrive und Microsoft Teams** aktivieren.

5. Wählen Sie **+** diese Option aus, um eine neue Richtlinie zu erstellen.

6. Wenden Sie die Einstellungen in der folgenden Tabelle an.

7. Nachdem Sie Ihre Einstellungen überprüft haben, wählen **Sie diese Richtlinie** erstellen oder **speichern** aus.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Blockieren Sie aktuelle und zukünftige E-Mails mit erkannter Schadsoftware.|
|Beschreibung|Blockieren Sie aktuelle und zukünftige E-Mails und Anlagen mit erkannter Schadsoftware.|
|Speichern von Anlagen mit unbekannter Schadsoftwareantwort|Select **Block - Block the current and future emails and attachments with detected malware**.|
|Anlage bei Erkennung umleiten|Umleitung aktivieren (aktivieren Sie dieses Kontrollkästchen) <br/> Geben Sie das Administratorkonto oder eine Postfacheinrichtung für die Quarantäne ein. <br/> Wenden Sie die oben genannte Auswahl an, wenn bei der Schadsoftwareüberprüfung nach Anlagen ein Zeitüberschreitung auftritt oder ein Fehler auftritt (aktivieren Sie dieses Kontrollkästchen).|
|Angewendet auf|Die Empfängerdomäne lautet . . . Wählen Sie Ihre Domäne aus.|
|

Weitere Informationen finden Sie unter [Einrichten von Antiphishingrichtlinien in Defender für Office 365.](../../security/office-365-security/configure-atp-anti-phishing-policies.md)

## <a name="10-protect-against-phishing-attacks-with-safe-links"></a>10: Schutz vor Phishingangriffen mit sicheren Links
<a name="phishingatp"> </a>

Hacker blenden manchmal schädliche Websites in Links in E-Mails oder anderen Dateien aus. Sichere Links, Teil von Microsoft Defender für Office 365, können Zum Schutz Ihrer Organisation beitragen, indem die Zeit-für-Klick-Überprüfung von Webadressen (URLs) in E-Mail-Nachrichten und Office Dokumenten bereitgestellt wird. Der Schutz wird durch Richtlinien für sichere Links definiert.

Es wird empfohlen, Folgendes zu tun:

- Ändern Sie die Standardrichtlinie, um den Schutz zu erhöhen.

- Fügen Sie allen Empfängern in Ihrer Domäne eine neue Richtlinie hinzu.

Um zu sicheren Links zu gelangen, zeigen Sie ein [kurzes Schulungsvideo](../../business-video/safe-links.md)an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie zu <https://protection.office.com> Ihrem Administratorkonto, und melden Sie sich an.

2. Wählen Sie im Security & Compliance Center im linken Navigationsbereich unter **"Bedrohungsmanagement"** die Option **"Richtlinie"** aus.

3. Wählen Sie auf der Seite "Richtlinie" die Option **"Sichere Links" aus.**

So ändern Sie die Standardrichtlinie:

1. Doppelklicken Sie auf der Seite "Sichere Links" unter **"Richtlinien", die für die gesamte Organisation gelten,** auf die **Standardrichtlinie.**

2. Geben Sie unter **Einstellungen, die für Inhalte über Office 365 hinweg gelten,** eine zu blockierende URL ein, z. _B. example.com,_ und wählen Sie **+** aus.

3. Wählen Sie **unter Einstellungen, die für Inhalte mit Ausnahme von E-Mails gelten,** **Office 365 Anwendungen** aus, verfolgen **Sie nicht, wenn Benutzer auf sichere Links klicken,** und **lassen Sie Benutzer nicht durch sichere Links zur ursprünglichen URL klicken.**

4. Wählen Sie **Speichern** aus.

So erstellen Sie eine neue Richtlinie für alle Empfänger in Ihrer Domäne:

1. Wählen Sie auf der Seite "Sichere Links" unter **"Richtlinien, die für bestimmte Empfänger gelten"** aus, **+** um eine neue Richtlinie zu erstellen.

2. Wenden Sie die in der folgenden Tabelle aufgeführten Einstellungen an.

3. Wählen Sie **Speichern** aus.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Richtlinie für sichere Links für alle Empfänger in der Domäne|
|Wählen Sie die Aktion für unbekannte potenziell schädliche URLs in Nachrichten aus.|Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.|
|Anwenden der Echtzeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen|Aktivieren Sie dieses Kontrollkästchen.|
|Angewendet auf|Die Empfängerdomäne lautet . . . Wählen Sie Ihre Domäne aus.|
|

Weitere Informationen finden Sie unter ["Sichere Links" in Microsoft Defender für Office 365.](../../security/office-365-security/atp-safe-links.md)

## <a name="related-content"></a>Verwandte Inhalte

[Mehrstufige Authentifizierung für Microsoft 365](multi-factor-authentication-microsoft-365.md) (Artikel)\
Verwalten und Überwachen von [Prioritätskonten](../setup/priority-accounts.md) (Artikel)\
[Microsoft 365 Berichte im Admin Center](../activity-reports/activity-reports.md) (Video)