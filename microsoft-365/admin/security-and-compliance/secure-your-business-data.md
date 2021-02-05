---
title: Die 10 besten Methoden zum Sichern von Microsoft 365 Business-Plänen
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
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
description: 'Schützen Sie Ihre Geschäftlichen E-Mails und Daten vor Cyberbedrohungen, einschließlich Ransomware, Phishing und schädlichen Anlagen. '
ms.openlocfilehash: 3ae6d896d5ef060e2f077167f81e2029a3a143ac
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114405"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>Die 10 besten Methoden zum Sichern von Microsoft 365 Business-Plänen

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Wenn Sie eine kleine oder mittelständische Organisation sind, die einen der Geschäftspläne von Microsoft verwendet, und Ihre Art von Organisation von Cyberkriminellen und Hackern ausgerichtet ist, verwenden Sie die Anleitungen in diesem Artikel, um die Sicherheit Ihrer Organisation zu erhöhen. Dieser Leitfaden hilft Ihrer Organisation, die ziele zu erreichen, die im Handbuch zur [Cybersicherheitskampagne der "University Cybersecurity Campaign" beschrieben sind.](https://go.microsoft.com/fwlink/p/?linkid=2015598)

Microsoft empfiehlt, die in der folgenden Tabelle aufgeführten Aufgaben auszuführen, die für Ihren Serviceplan gelten.

||Aufgabe|Microsoft 365 Business Standard|Microsoft 365 Business Premium|
|---|---|---|---|
|1|[Einrichten der mehrstufigen Authentifizierung](secure-your-business-data.md#setup)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2|[Schulen der Benutzer](secure-your-business-data.md#train)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[Verwenden dedizierter Administratorkonten](secure-your-business-data.md#admin)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4 |[Erhöhen des Schutzniveaus vor Schadsoftware in E-Mails](secure-your-business-data.md#malware)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5 |[Schutz vor Ransomware](secure-your-business-data.md#ransomware)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[Beenden der automatischen Weiterleitung für E-Mails](secure-your-business-data.md#forwarding)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[Verwenden der Office-Nachrichtenverschlüsselung](secure-your-business-data.md#encryption)||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[Schützen Ihrer E-Mails vor Phishingangriffen](secure-your-business-data.md#phishing)||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[Schutz vor schädlichen Anlagen und Dateien mit sicheren Anlagen](secure-your-business-data.md#atp)||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10 |[Schutz vor Phishingangriffen mit sicheren Links](secure-your-business-data.md#phishingatp)||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

Bevor Sie beginnen, überprüfen Sie Ihre [Microsoft 365-Sicherheitsüberprüfung](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) im Microsoft 365 Security Center. Über ein zentrales Dashboard können Sie die Sicherheit für Ihre Microsoft 365-Identitäten, -Daten, -Apps, -Geräte und -Infrastruktur überwachen und verbessern. Sie erhalten Punkte zum Konfigurieren empfohlener Sicherheitsfeatures, zum Ausführen sicherheitsbezogener Aufgaben (z. B. zum Anzeigen von Berichten) oder zum Adressieren von Empfehlungen mit einer Drittanbieteranwendung oder -software. Mit zusätzlichen Einblicken und mehr Einblick in eine breitere Palette von Produkten und Diensten von Microsoft können Sie sicher sein, dass Sie über den Sicherheitszustand Ihrer Organisation berichten.

![Screenshot der Microsoft Secure Score](../../media/secure-score.png)

## <a name="1-set-up-multi-factor-authentication"></a>1: Einrichten der mehrstufigen Authentifizierung
<a name="setup"> </a>

Die Verwendung der mehrstufigen Authentifizierung ist eine der einfachsten und effektivsten Methoden, um die Sicherheit Ihrer Organisation zu erhöhen. Es ist einfacher, als es klingt. Wenn Sie sich anmelden, bedeutet die mehrstufige Authentifizierung, dass Sie einen Code von Ihrem Telefon eingeben, um Zugriff auf Microsoft 365 zu erhalten. Dies kann verhindern, dass Hacker die Kontrolle übernimmt, wenn sie Ihr Kennwort kennen. Die mehrstufige Authentifizierung wird auch als Überprüfung in zwei Schritten bezeichnet. Einzelpersonen können die Überprüfung in zwei Schritten den meisten Konten problemlos hinzufügen, z. B. ihren Google- oder Microsoft-Konten. Hier erfahren Sie, wie [Sie Ihrem persönlichen Microsoft-Konto die](https://go.microsoft.com/fwlink/p/?linkid=2016403)Überprüfung in zwei Schritten hinzufügen.

Für Unternehmen, die Microsoft 365 verwenden, fügen Sie eine Einstellung hinzu, die erfordert, dass sich Ihre Benutzer mit der mehrstufigen Authentifizierung anmelden. Wenn Sie diese Änderung ändern, werden Benutzer aufgefordert, ihr Telefon bei der nächsten Anmeldung für die zweistufige Authentifizierung zu einrichten.
Ein Schulungsvideo zum Einrichten von MFA und zum Abschließen der Einrichtung durch Benutzer finden Sie unter Einrichten von [MFA](https://support.microsoft.com/office/e12187b8-216a-4490-9e3b-df34a06fb787) und [Benutzersetset.](https://support.microsoft.com/office/a32541df-079c-420d-9395-9d59354f7225)

Zum Einrichten der mehrstufigen Authentifizierung aktivieren Sie die Sicherheitseinstellungen:

In den meisten Organisationen bieten Sicherheitsstandards ein gutes Maß an zusätzlicher Anmeldesicherheit. Weitere Informationen hierzu finden Sie unter [Was sind Sicherheitsstandards?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Wenn Ihr Abonnement neu ist, sind die Sicherheitsstandards möglicherweise bereits automatisch für Sie aktiviert.

Die Standardsicherheitseinstellungen können Sie im Azure-Portal im Bereich **Einstellungen** für Active Directory (Azure AD) aktivieren oder deaktivieren.

1. Melden Sie sich mit den Anmeldeinformationen des globalen Administrators beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.
2. Wählen Sie im linken Navigationsbereich **Alle anzeigen** und dann unter **Admin Center** die Option **Azure Active Directory** aus.
3. Im **Azure Active Directory Admin Center** wählen Sie dann **Azure Active Directory** > **Eigenschaften** aus.
4. Wählen Sie unten auf der Seite **Sicherheitsstandards verwalten** aus.
5. Wählen Sie **Ja** aus, um die zu aktivieren oder **Nein**, um die Sicherheitsstandards zu deaktivieren. Klicken Sie anschließend auf **Speichern**.

Nachdem Sie die mehrstufige Authentifizierung für Ihre Organisation eingerichtet haben, müssen die Benutzer auf ihren Geräten die Prüfung in zwei Schritten einrichten. Weitere Informationen finden Sie unter Einrichten der Überprüfung in zwei Schritten [für Microsoft 365.](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)

Ausführliche Informationen und vollständige Empfehlungen finden Sie unter [Einrichten der mehrstufigen Authentifizierung für Benutzer.](set-up-multi-factor-authentication.md)

## <a name="2-train-your-users"></a>2: Schulen Der Benutzer
<a name="train"> </a>

Das Handbuch zur Cybersicherheitskampagne der "University [OfEnding](https://go.microsoft.com/fwlink/p/?linkid=2015598) School" bietet hervorragende Anleitungen zum Einrichten einer starken Kultur des Sicherheitsbewusstseins in Ihrer Organisation, einschließlich der Schulung von Benutzern zur Identifizierung von Phishingangriffen.

Zusätzlich zu dieser Anleitung empfiehlt Microsoft Ihren Benutzern, die in diesem Artikel beschriebenen Aktionen zu ergreifen: Schützen Ihres Kontos und Ihrer Geräte [vor Hackern und Schadsoftware.](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6) Diese setzen sich wie folgt zusammen:

- Verwenden von starken Kennwörtern

- Schützen von Geräten

- Aktivieren von Sicherheitsfeatures auf Windows 10- und Mac-PCs

Microsoft empfiehlt benutzern außerdem, ihre persönlichen E-Mail-Konten zu schützen, indem sie die in den folgenden Artikeln empfohlenen Aktionen ausführen:

- [Schützen Ihres E Outlook.com-E-Mail-Kontos](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Schützen Ihres Gmail-Kontos mit der Überprüfung in zwei Schritten](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="3-use-dedicated-admin-accounts"></a>3: Verwenden dedizierter Administratorkonten
<a name="admin"> </a>

Die Administratorkonten, die Sie zum Verwalten Ihrer Microsoft 365-Umgebung verwenden, umfassen erhöhte Rechte. Dies sind wertvolle Ziele für Hacker und Cyberkriminellen. Verwenden Sie Administratorkonten nur für die Verwaltung. Administratoren sollten über ein separates Benutzerkonto für die reguläre, nicht administrative Verwendung verfügen und ihr Administratorkonto nur verwenden, wenn dies erforderlich ist, um eine Aufgabe zu erfüllen, die mit ihrer Auftragsfunktion verknüpft ist. Zusätzliche Empfehlungen:

- Stellen Sie sicher, dass auch Administratorkonten für die mehrstufige Authentifizierung eingerichtet sind.

- Schließen Sie vor der Verwendung von Administratorkonten alle nicht verbundenen Browsersitzungen und Apps, einschließlich persönlicher E-Mail-Konten.

- Melden Sie sich nach Abschluss der Administratoraufgaben unbedingt von der Browsersitzung ab.

## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4: Erhöhen des Schutzes vor Schadsoftware in E-Mails
<a name="malware"> </a>

Ihre Microsoft 365-Umgebung bietet Schutz vor Schadsoftware. Sie können diesen Schutz jedoch erhöhen, indem Sie Anlagen mit Dateitypen blockieren, die häufig für Schadsoftware verwendet werden. Um den Schutz vor Schadsoftware in E-Mails zu ergänzen, sehen Sie sich ein [kurzes](https://support.microsoft.com/office/02b5783a-eea0-42e8-8856-62440718c3f0)Schulungsvideo an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie <https://protection.office.com> zu Und melden Sie sich mit Ihren Administratorkontoanmeldeinformationen an.

2. Wählen Sie im Security & Compliance Center im linken Navigationsbereich unter "Bedrohungsverwaltung" die Option "Richtlinie  \> **an malware " aus.**

3. Doppelklicken Sie auf die Standardrichtlinie, um diese unternehmensweite Richtlinie zu bearbeiten.

4. Wählen Sie **Einstellungen** aus.

5. Wählen **Sie unter "Common Attachment Types Filter"** die Option **"Ein" aus.** Die gesperrten Dateitypen werden im Fenster direkt unterhalb dieses Steuerelements aufgeführt. Sie können Dateitypen bei Bedarf später hinzufügen oder löschen.

6. Wählen Sie **"Speichern" aus.**

Weitere Informationen finden Sie unter [An malware protection in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection).

## <a name="5-protect-against-ransomware"></a>5: Schutz vor Ransomware
<a name="ransomware"> </a>

Ransomware schränkt den Zugriff auf Daten ein, indem Dateien verschlüsselt oder Computerbildschirme gesperrt werden. Sie versucht dann, Geld von Opfer zu erpressen, indem sie "Lösegeld" in Form von Kryptos wie Etwa im Austausch für den Zugriff auf Daten anfordert.

Sie können vor Ransomware schützen, indem Sie eine oder mehrere Nachrichtenflussregeln erstellen, um Dateierweiterungen zu blockieren, die häufig für Ransomware verwendet werden, oder um Benutzer zu warnen, die diese Anlagen per E-Mail erhalten. Ein guter Ausgangspunkt ist das Erstellen von zwei Regeln:

- Warnen Sie Benutzer vor dem Öffnen von Office-Dateianlagen, die Makros enthalten. Ransomware kann in Makros ausgeblendet werden, daher warnen wir Benutzer davor, diese Dateien von Personen zu öffnen, die sie nicht kennen.

- Blockieren sie Dateitypen, die Ransomware oder anderen schädlichen Code enthalten können. Wir beginnen mit einer allgemeinen Liste von ausführbaren Dateien (in der folgenden Tabelle aufgeführt). Wenn Ihre Organisation einen dieser ausführbaren Typen verwendet und Sie davon aus gehen, dass diese in E-Mails gesendet werden, fügen Sie diese der vorherigen Regel hinzu (warnen Sie die Benutzer).

Um eine E-Mail-Transportregel zu erstellen, zeigen Sie ein [kurzes](https://support.microsoft.com/office/a9ecca03-42a6-4867-b9fd-38e3f6bb06ad)Schulungsvideo an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie zum [Exchange Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. Wählen Sie **in der Kategorie "Nachrichtenfluss"** Regeln **aus.**

3. Wählen **+** Sie diese Option aus, und erstellen Sie dann eine neue **Regel.**

4. Wählen Sie **** am unteren Rand des Dialogfelds aus, um den vollständigen Satz von Optionen anzuzeigen.

5. Wenden Sie die Einstellungen in der folgenden Tabelle für jede Regel an. Lassen Sie die restlichen Einstellungen auf den Standardwert festgelegt, es sei denn, Sie möchten diese ändern.

6. Klicken Sie auf **Speichern**.
    
| Setting | Warnen von Benutzern vor dem Öffnen von Anlagen von Office-Dateien | Blockieren von Dateitypen, die Ransomware oder anderen schädlichen Code enthalten könnten |
|:-----|:-----|:-----|
|Name  <br/> |Anti-Ransomware-Regel: Benutzer warnen  <br/> |Anti-Ransomware-Regel: Blockieren von Dateitypen  <br/> |
|Wenden Sie diese Regel an, wenn . . .  <br/> |Eine Anlage . . . Dateierweiterung entspricht . . .  <br/> |Eine Anlage . . . Dateierweiterung entspricht . . .  <br/> |
|Angeben von Wörtern oder Ausdrücken  <br/> |Fügen Sie die folgenden Dateitypen hinzu:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/> |Fügen Sie die folgenden Dateitypen hinzu:  <br/> ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif  <br/> |
|Gehen Sie wie folgt vor. . .  <br/> |Haftungsausschluss voraus  <br/> |Nachricht blockieren . . . Die Nachricht ablehnen und eine Erklärung enthalten  <br/> |
|Bereitstellen von Nachrichtentext  <br/> |Öffnen Sie diese Dateitypen nur, wenn Sie sie erwartet haben, da die Dateien möglicherweise schädlichen Code enthalten und wissen, dass der Absender keine Garantie für Sicherheit ist.  <br/> ||
   
> [!TIP]
> Sie können auch die Dateien, die Sie blockieren möchten, in Schritt 4 zur Liste der [Schadsoftware hinzufügen.](#4-raise-the-level-of-protection-against-malware-in-mail)

Weitere Informationen finden Sie unter:

- [Ransomware: Verringern des Risikos](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Wiederherstellen Ihres OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="6-stop-auto-forwarding-for-email"></a>6: Beenden der automatischen Weiterleitung für E-Mails
<a name="forwarding"> </a>

Hacker, die Zugriff auf das Postfach eines Benutzers erhalten, können E-Mails exfiltrieren, indem sie das Postfach so konfigurieren, dass E-Mails automatisch weitergeleitet werden. Dies kann auch ohne die Sensibilisierung des Benutzers geschehen. Sie können dies verhindern, indem Sie eine Nachrichtenflussregel konfigurieren.

So erstellen Sie eine E-Mail-Transportregel:

1. Wechseln Sie zum [Exchange Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. Wählen Sie **in der Kategorie "Nachrichtenfluss"** Regeln **aus.**

3. Wählen **+** Sie diese Option aus, und erstellen Sie dann eine neue **Regel.**

4. Wählen **Sie unten im** Dialogfeld weitere Optionen aus, um den vollständigen Satz von Optionen anzuzeigen.

5. Wenden Sie die Einstellungen in der folgenden Tabelle an. Lassen Sie die restlichen Einstellungen auf den Standardwert festgelegt, es sei denn, Sie möchten diese ändern.

6. Klicken Sie auf **Speichern**.

|Setting|Ablehnen automatischer Weiterleitung von E-Mails an externe Domänen|
|---|---|
|Name|Verhindern der automatischen Weiterleitung von E-Mails an externe Domänen|
|Wenden Sie diese Regel an, wenn ...|Der Absender . . . ist extern/intern . . . Innerhalb der Organisation|
|Bedingung hinzufügen|Der Empfänger . . . ist extern/intern . . . Außerhalb der Organisation|
|Bedingung hinzufügen|Die Nachrichteneigenschaften . . . den Nachrichtentyp enthalten. . . Automatische Weiterleitung|
|Gehen Sie wie folgt vor...|Nachricht blockieren . . . die Nachricht ablehnen und eine Erklärung enthalten.|
|Bereitstellen von Nachrichtentext|Die automatische Weiterleitung von E-Mails außerhalb dieser Organisation wird aus Sicherheitsgründen verhindert.|

## <a name="7-use-office-message-encryption"></a>7: Verwenden der Office-Nachrichtenverschlüsselung
<a name="encryption"> </a>

Die Office-Nachrichtenverschlüsselung ist in Microsoft 365 enthalten. Sie ist bereits eingerichtet. Mit der Office-Nachrichtenverschlüsselung kann Ihre Organisation verschlüsselte E-Mail-Nachrichten zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen. Die Office 365-Nachrichtenverschlüsselung funktioniert mit Outlook.com, Yahoo!, Gmail und anderen E-Mail-Diensten. Die E-Mail-Nachrichtenverschlüsselung sorgt dafür, dass nur vorgesehene Empfänger verschlüsselte Nachrichten ansehen können.

Die Office-Nachrichtenverschlüsselung bietet zwei Schutzoptionen beim Senden von E-Mails:

- Nicht weiterleiten

- Verschlüsseln

Möglicherweise hat Ihre Organisation zusätzliche Optionen konfiguriert, die eine Bezeichnung auf E-Mails anwenden, z. B. "Vertraulich".

### <a name="to-send-protected-email"></a>So senden Sie geschützte E-Mails

Wählen Sie in Outlook für PC in der **E-Mail** "Optionen" und dann **"Berechtigungen" aus.**

![Verschlüsselung von E-Mail-Nachrichten in Outlook](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)

Wählen Outlook.com "Schützen" in der **E-Mail** aus. Der Standardschutz ist **"Nicht weiterleiten".** Um dies zu verschlüsseln, wählen Sie **"Berechtigungen** verschlüsseln \> **ändern" aus.**

![Verschlüsselung von E-Mail-Nachrichten in Outlook.com](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)

### <a name="to-receive-encrypted-email"></a>So empfangen Sie verschlüsselte E-Mails

Wenn der Empfänger über Outlook 2013 oder Outlook 2016 und ein Microsoft-E-Mail-Konto verfügt, wird im Lesebereich eine Warnung zu den eingeschränkten Berechtigungen des Elements angezeigt. Nach dem Öffnen der Nachricht kann der Empfänger die Nachricht wie jede andere anzeigen.

Wenn der Empfänger einen anderen E-Mail-Client oder ein anderes E-Mail-Konto verwendet, z. B. Gmail oder Yahoo, wird ein Link angezeigt, über den er sich entweder anmelden kann, um die E-Mail-Nachricht zu lesen, oder eine einmalkennung anfordern kann, um die Nachricht in einem Webbrowser anzuzeigen. Wenn Benutzer die E-Mail nicht erhalten, lassen Sie sie ihren Spam- oder Junk-Ordner überprüfen.

Weitere Informationen finden Sie unter Senden, Anzeigen und Antworten auf verschlüsselte [Nachrichten in Outlook für PC.](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)

## <a name="8-protect-your-email-from-phishing-attacks"></a>8. Schützen Ihrer E-Mails vor Phishingangriffen
<a name="phishing"> </a>

Wenn Sie eine oder mehrere benutzerdefinierte Domänen für Ihre Microsoft 365-Umgebung konfiguriert haben, können Sie den gezielten Antiphishingschutz konfigurieren. Der Antiphishingschutz, ein Bestandteil von Microsoft Defender für Office 365, kann Ihre Organisation vor phishingbasierten Phishingangriffen auf Identitätswechsel und anderen Phishingangriffen schützen. Wenn Sie keine benutzerdefinierte Domäne konfiguriert haben, müssen Sie dies nicht tun.

Es wird empfohlen, mit diesem Schutz zu beginnen, indem Sie eine Richtlinie zum Schutz Ihrer wichtigsten Benutzer und Ihrer benutzerdefinierten Domäne erstellen.

![Erstellen einer Antiphishingrichtlinie in Microsoft Defender für Office 365](../../media/security-and-compliance-center.png)

Um eine Antiphishingrichtlinie in Defender für Office 365 zu erstellen, sehen Sie sich ein kurzes Schulungsvideo [an,](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie zu <https://protection.office.com>.

2. Wählen Sie im Security & Compliance Center im linken Navigationsbereich unter **Bedrohungsverwaltung** **"Richtlinie" aus.**

3. Wählen Sie auf der Seite "Richtlinie" die Option **"Antiphishing" aus.**

4. Wählen Sie auf der Seite "Antiphishing" die Option **+Erstellen aus.** Ein Assistent startet, der Sie durch die Definition Ihrer Antiphishingrichtlinie führt.

5. Geben Sie den Namen, die Beschreibung und die Einstellungen für Ihre Richtlinie wie im folgenden Diagramm empfohlen an. Weitere Informationen finden Sie unter "Informationen zur [Antiphishingrichtlinie in Microsoft Defender für Office 365".](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)

6. Nachdem Sie Ihre Einstellungen überprüft haben, wählen **Sie** diese Richtlinie erstellen oder **speichern**(entsprechend).

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Domänen- und wertvollste Kampagnenmitarbeiter|
|Beschreibung|Stellen Sie sicher, dass die wichtigsten Mitarbeiter und unsere Domäne nicht imitiert werden.|
|Zu schützende Benutzer hinzufügen|Select **+ Add a condition, The recipient is**. Geben Sie Benutzernamen ein, oder geben Sie die E-Mail-Adresse des Kandidaten, Kampagnenmanagers und anderer wichtiger Mitarbeiter ein. Sie können bis zu 20 interne und externe Adressen hinzufügen, die Sie vor Identitätswechsel schützen möchten.|
|Zu schützende Domänen hinzufügen|Select **+ Add a condition, The recipient domain is**. Geben Sie die benutzerdefinierte Domäne ein, die Ihrem Microsoft 365-Abonnement zugeordnet ist, wenn Sie eine definiert haben. Sie können mehrere Domänen eingeben.|
|Aktionen auswählen|Wenn E-Mails von einem imitierten Benutzer gesendet werden: Wählen Sie "Nachricht an eine andere E-Mail-Adresse umleiten" **aus,** und geben Sie dann die E-Mail-Adresse des Sicherheitsadministrators ein. Beispiel: securityadmin@contoso.com. <br/> Wenn E-Mails von einer imitierten Domäne gesendet werden: Wählen Sie **"Nachricht isolieren" aus.**|
|Mailbox Intelligence|Standardmäßig wird die Mailbox Intelligence ausgewählt, wenn Sie eine neue Anti-Phishing-Richtlinie erstellen. Lassen Sie diese Einstellung auf **Ein**, um optimale Ergebnisse zu erzielen.|
|Vertrauenswürdige Absender und Domänen hinzufügen|Definieren Sie in diesem Beispiel keine Außerkraftsetzungen.|
|Angewendet auf|Wählen Sie **Die Domäne des Empfängers ist** aus. Wählen Sie unter **Einer dieser**, **Auswählen** aus. Wählen Sie **+ Hinzufügen** aus. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, z. B. contoso.com in der Liste, und wählen Sie dann **Hinzufügen aus.** Wählen Sie **Fertig** aus.|
|

Weitere Informationen finden Sie unter [Einrichten von Antiphishingrichtlinien in Defender für Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies)

## <a name="9-protect-against-malicious-attachments-and-files-with-safe-attachments"></a>9: Schutz vor schädlichen Anlagen und Dateien mit sicheren Anlagen
<a name="atp"> </a>

Personen senden, empfangen und geben Anlagen wie Dokumente, Präsentationen, Tabellenkalkulationen und vieles mehr regelmäßig weiter. Es ist nicht immer einfach zu wissen, ob eine Anlage sicher oder schädlich ist, indem Sie sich eine E-Mail-Nachricht anschauen. Microsoft Defender für Office 365 bietet sicheren Anlagenschutz, ist jedoch nicht standardmäßig aktiviert. Es wird empfohlen, eine neue Regel zu erstellen, um mit der Verwendung dieses Schutzes zu beginnen. Dieser Schutz erstreckt sich auf Dateien in SharePoint, OneDrive und Microsoft Teams.

Um eine Richtlinie für sichere Anlagen zu erstellen, zeigen Sie ein [kurzes](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)Schulungsvideo an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie <https://protection.office.com> zu Ihrem Administratorkonto, und melden Sie sich mit ihrem Administratorkonto an.

2. Wählen Sie im Security & Compliance Center im linken Navigationsbereich unter **Bedrohungsverwaltung** **"Richtlinie" aus.**

3. Wählen Sie auf der Seite "Richtlinie" die Option **"Sichere Anlagen" aus.**

4. Wenden Sie diesen Schutz auf der Seite "Sichere Anlagen" allgemein an, indem Sie das Kontrollkästchen ATP für **SharePoint, OneDrive** und Microsoft Teams aktivieren.

5. Wählen Sie **+** diese Option aus, um eine neue Richtlinie zu erstellen.

6. Wenden Sie die Einstellungen in der folgenden Tabelle an.

7. Nachdem Sie Ihre Einstellungen überprüft haben, wählen **Sie** diese Richtlinie erstellen oder **speichern**(entsprechend).

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Blockieren Sie aktuelle und zukünftige E-Mails mit erkannter Schadsoftware.|
|Beschreibung|Blockieren Sie aktuelle und zukünftige E-Mails und Anlagen mit erkannter Schadsoftware.|
|Speichern von Anlagen unbekannte Schadsoftwareantwort|Select **Block - Block the current and future emails and attachments with detected malware**.|
|Anlage bei Erkennung umleiten|Umleitung aktivieren (aktivieren Sie dieses Kontrollkästchen) <br/> Geben Sie das Administratorkonto oder ein Postfach für die Quarantäne ein. <br/> Wenden Sie die oben aufgeführte Auswahl an, wenn bei der Schadsoftwareprüfung auf Anlagen ein Zeitfehler auftritt oder ein Fehler auftritt (aktivieren Sie dieses Kontrollkästchen).|
|Angewendet auf|Die Empfängerdomäne ist . . . wählen Sie Ihre Domäne aus.|
|

Weitere Informationen finden Sie unter [Einrichten von Antiphishingrichtlinien in Defender für Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies)

## <a name="10-protect-against-phishing-attacks-with-safe-links"></a>10: Schutz vor Phishingangriffen mit sicheren Links
<a name="phishingatp"> </a>

Hacker blenden manchmal schädliche Websites in Links in E-Mails oder anderen Dateien aus. Sichere Links, Teil von Microsoft Defender für Office 365, können Zum Schutz Ihrer Organisation beitragen, indem sie die Überprüfung von Webadressen (URLs) per Mausklick in E-Mail-Nachrichten und Office-Dokumenten bereitstellen. Der Schutz wird durch Richtlinien für sichere Links definiert.

Es wird empfohlen, die folgenden Schritte zu tun:

- Ändern Sie die Standardrichtlinie, um den Schutz zu erhöhen.

- Fügen Sie eine neue Richtlinie für alle Empfänger in Ihrer Domäne hinzu.

Um zu sicheren Links zu kommen, sehen Sie sich ein [kurzes](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)Schulungsvideo an, oder führen Sie die folgenden Schritte aus:

1. Wechseln Sie <https://protection.office.com> zu Ihrem Administratorkonto, und melden Sie sich mit ihrem Administratorkonto an.

2. Wählen Sie im Security & Compliance Center im linken Navigationsbereich unter **Bedrohungsverwaltung** **"Richtlinie" aus.**

3. Wählen Sie auf der Seite "Richtlinie" die Option **"Sichere Links" aus.**

So ändern Sie die Standardrichtlinie:

1. Doppelklicken Sie auf der Seite "Sichere Links" unter "Richtlinien, **die** für die gesamte Organisation gelten" auf die **Standardrichtlinie.**

2. Geben Sie unter Einstellungen, die für Inhalte **in Office 365** gelten, eine URL ein, die blockiert werden soll, z. B. example.com _,_ und wählen Sie **+** aus.

3. Wählen **Sie** unter Einstellungen, die für Inhalte außer E-Mail gelten, **Office 365-Anwendungen** **aus,** und verfolgen Sie nicht, wenn Benutzer auf sichere Links klicken, und lassen Sie benutzer nicht durch sichere Links zu der ursprünglichen **URL klicken.**

4. Klicken Sie auf **Speichern**.

So erstellen Sie eine neue Richtlinie für alle Empfänger in Ihrer Domäne:

1. Wählen Sie auf der Seite "Sichere Links" unter **"Richtlinien, die für** bestimmte Empfänger gelten" die Option zum Erstellen einer neuen Richtlinie **+** aus.

2. Wenden Sie die in der folgenden Tabelle aufgeführten Einstellungen an.

3. Klicken Sie auf **Speichern**.

|Einstellung oder Option|Empfohlene Einstellung|
|---|---|
|Name|Richtlinie für sichere Links für alle Empfänger in der Domäne|
|Auswählen der Aktion für unbekannte potenziell schädliche URLs in Nachrichten|Select **On - URLs werden umgeschrieben** und mit einer Liste bekannter bösartiger Links überprüft, wenn der Benutzer auf den Link klickt.|
|Anwenden der Echtzeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen|Aktivieren Sie dieses Feld.|
|Angewendet auf|Die Empfängerdomäne ist . . . wählen Sie Ihre Domäne aus.|
|

Weitere Informationen finden Sie unter ["Sichere Links" in Microsoft Defender für Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)
