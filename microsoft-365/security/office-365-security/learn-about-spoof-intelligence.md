---
title: Konfigurieren der Spoofintelligenz
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über Spoof Intelligence in Exchange Online Protection (EOP) informieren, wo Sie bestimmte gefälschte Absender zulassen oder blockieren können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c13c080829236b9a27b6a1a82e1c27256749b5c2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204234"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Konfigurieren von Spoof Intelligence in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden eingehende E-Mail-Nachrichten ab Oktober 2018 automatisch vor Spoofing durch EOP geschützt. EOP verwendet Spoof Intelligence als Teil der allgemeinen Verteidigung Ihrer Organisation gegen Phishing. Weitere Informationen finden Sie unter Schutz vor [Spoofing in EOP](anti-spoofing-protection.md).

Wenn ein Absender eine E-Mail-Adresse spooft, scheint er ein Benutzer in einer der Domänen Ihrer Organisation oder ein Benutzer in einer externen Domäne zu sein, die E-Mails an Ihre Organisation sendet. Angreifer, die Absender zum Senden von Spam- oder Phishing-E-Mails spoofen, müssen blockiert werden. Es gibt jedoch Szenarien, in denen legitime Absender Spoofing verwenden. Beispiel:

- Legitime Szenarien für das Spoofing interner Domänen:

  - Drittanbietersender verwenden Ihre Domäne, um Massen-E-Mails für Unternehmensumfragen an Ihre eigenen Mitarbeiter zu senden.
  - Ein externes Unternehmen generiert und sendet Werbe- oder Produktupdates in Ihrem Auftrag.
  - Ein Assistent muss regelmäßig E-Mails für eine andere Person in Ihrer Organisation senden.
  - Eine interne Anwendung sendet E-Mail-Benachrichtigungen.

- Legitime Szenarien für das Spoofing externer Domänen:

  - Der Absender befindet sich in einer Mailingliste (auch als Diskussionsliste bezeichnet), und die Mailingliste leitet E-Mails vom ursprünglichen Absender an alle Teilnehmer in der Mailingliste weiter.
  - Ein externes Unternehmen sendet E-Mails im Auftrag eines anderen Unternehmens (z. B. einen automatisierten Bericht oder ein Software-as-a-Service-Unternehmen).

Spoof Intelligence, insbesondere die standardmäßige (und nur) Spoof Intelligence-Richtlinie, trägt dazu bei, sicherzustellen, dass die gefälschten E-Mails, die von legitimen Absendern gesendet werden, nicht in EOP-Spamfilter oder externe E-Mail-Systeme versenkt werden, während Ihre Benutzer vor Spam- oder Phishingangriffen geschützt werden.

Sie können Spoof Intelligence im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange &) verwalten.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://protection.office.com/antispam>. Um direkt zur Seite **"Antiphishing" zu** wechseln, verwenden Sie <https://protection.office.com/antiphishing> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:
  - Um die Spoof Intelligence-Richtlinie zu ändern oder Spoof Intelligence zu  aktivieren oder zu deaktivieren, müssen Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein.
  - Für den schreibgeschützten Zugriff auf die Spoof Intelligence-Richtlinie müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweise**:

  - Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Unsere empfohlenen Einstellungen für spoof intelligence finden Sie unter [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Verwenden des Security & Compliance Center zum Verwalten gefälschter Absender

> [!NOTE]
> Wenn Sie über ein Microsoft 365 Enterprise E5-Abonnement verfügen oder ein Microsoft Defender for Office 365-Add-On separat erworben haben, können Sie auch Absender verwalten, die Ihre Domäne spoofen, über den [Spoof](walkthrough-spoof-intelligence-insight.md)Intelligence-Einblick.

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie auf der Seite **Antispameinstellungen** auf ![ Symbol erweitern, ](../../media/scc-expand-icon.png) um die **Spoof Intelligence-Richtlinie zu erweitern.**

   ![Auswählen der Spoof Intelligence-Richtlinie](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Treffen Sie eine der folgenden Auswahlen:

   - **Überprüfen neuer Absender**
   - **Absender anzeigen, die ich bereits überprüft habe**

4. Wählen Sie im angezeigten Flyout "Entscheiden, ob diese Absender ihre Benutzer-Flyouts **spoofen** dürfen" eine der folgenden Registerkarten aus:

   - **Ihre Domänen:** Absender, die Benutzer in Ihren internen Domänen spoofieren.
   - **Externe Domänen:** Absender, die Benutzer in externen Domänen spoofieren.

5. Klicken ![ Sie in der Spalte ](../../media/scc-expand-icon.png) **Spoofing?** auf Erweitern(Symbol). Wählen **Sie Ja** aus, um den gefälschten Absender zu erlauben, oder wählen Sie **Nein** aus, um die Nachricht als spoofed zu markieren. Die Aktion wird durch die standardmäßige Antiphishingrichtlinie oder benutzerdefinierte Antiphishingrichtlinien gesteuert (der Standardwert ist **Move message to Junk Email folder**). Weitere Informationen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).

   ![Screenshot des Flyouts von spoofierten Absendern und der Frage, ob der Absender spoofen darf](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   Die angezeigten Spalten und Werte werden in der folgenden Liste erläutert:

   - **Spoofed user:** Das Benutzerkonto, das gefälscht wird. Dies ist der Absender der Nachricht in der Absenderadresse (auch als Adresse bezeichnet), die `5322.From` in E-Mail-Clients angezeigt wird. Die Gültigkeit dieser Adresse wird von SPF nicht überprüft.

     - Auf der Registerkarte Ihre **Domänen** enthält der Wert eine einzelne E-Mail-Adresse, oder wenn der Quell-E-Mail-Server mehrere Benutzerkonten spoofiert, enthält er **mehrere**.

     - Auf der **Registerkarte Externe Domänen** enthält der Wert die Domäne des spoofierten Benutzers, nicht die vollständige E-Mail-Adresse.

   - **Sendeinfrastruktur**: Die Domäne, die in einer Reverse-DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers gefunden wurde. Wenn die Quell-IP-Adresse keinen PTR-Eintrag enthält, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).

     Weitere Informationen zu Nachrichtenquellen und Nachrichtensendern finden Sie unter [Eine Übersicht über E-Mail-Nachrichtenstandards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

   - **Anzahl der Nachrichten**: Die Anzahl der Nachrichten aus der sendenden Infrastruktur an Ihre Organisation, die den angegebenen gefälschten Absender oder Absender innerhalb der letzten 30 Tage enthalten.

   - **# der Benutzerbeschwerden**: Beschwerden, die von Ihren Benutzern gegen diesen Absender innerhalb der letzten 30 Tage eingereicht wurden. Beschwerden werden in der Regel in Form von Junk-Übermittlungen an Microsoft eingereicht.

   - **Authentifizierungsergebnis**: Einer der folgenden Werte:
      - **Übergeben:** Der Absender hat E-Mail-Authentifizierungsprüfungen (SPF oder DKIM) bestanden.
      - **Fehler:** Fehler beim EOP-Absenderauthentifizierungsüberprüfungen.
      - **Unbekannt:** Das Ergebnis dieser Prüfungen ist nicht bekannt.

   - **Entscheidungssatz von**: Zeigt an, wer ermittelt hat, ob die sendende Infrastruktur den Benutzer spoofen darf:
       - **Spoof Intelligence Policy** (automatisch)
       - **Administrator** (manuell)

   - **Zuletzt gesehen:** Das letzte Datum, an dem eine Nachricht von der sendenden Infrastruktur empfangen wurde, die den spoofierten Benutzer enthält.

   - **Darf ges spooft werden?**: Die hier angezeigten Werte sind:
     - **Ja:** Nachrichten aus der Kombination aus spoofierten Benutzern und sendender Infrastruktur sind zulässig und werden nicht als spoofierte E-Mails behandelt.
     - **Nein:** Nachrichten aus der Kombination aus spoofiertem Benutzer und sendender Infrastruktur werden als Spoofing gekennzeichnet. Die Aktion wird durch die standardmäßige Antiphishingrichtlinie oder benutzerdefinierte Antiphishingrichtlinien gesteuert (der Standardwert ist **Move message to Junk Email folder**). Weitere Informationen finden Sie im nächsten Abschnitt.

     - **Einige Benutzer** (**Nur Registerkarte "Ihre** Domänen"): Eine sendende Infrastruktur fälscht mehrere Benutzer, wobei einige spoofierte Benutzer zulässig sind und andere nicht. Verwenden Sie die **Registerkarte Detail,** um die spezifischen Adressen zu sehen.

6. Klicken Sie unten auf der Seite auf **Speichern**.

## <a name="use-powershell-to-manage-spoofed-senders"></a>Verwenden von PowerShell zum Verwalten gefälschter Absender

Verwenden Sie die folgende Syntax, um zugelassene und blockierte Absender in Spoof Intelligence zu sehen:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

In diesem Beispiel werden detaillierte Informationen zu allen Absendern zurückgegeben, die Benutzer in Ihren Domänen spoofen dürfen.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).

Führen Sie die folgenden Schritte aus, um zugelassene und blockierte Absender in Spoof Intelligence zu konfigurieren:

1. Erfassen Sie die aktuelle Liste der erkannten gefälschten Absender, indem Sie die Ausgabe des **Get-PhishFilterPolicy-Cmdlets** in eine CSV-Datei schreiben:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Bearbeiten Sie die CSV-Datei, um die **Werte SpoofedUser** (E-Mail-Adresse) und **AllowedToSpoof** (Ja oder Nein) hinzuzufügen oder zu ändern. Speichern Sie die Datei, lesen Sie die Datei, und speichern Sie den Inhalt als Variable namens `$UpdateSpoofedSenders` :

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Verwenden Sie die `$UpdateSpoofedSenders` Variable, um die Spoof Intelligence-Richtlinie zu konfigurieren:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Konfigurieren von Spoof Intelligence mithilfe & Security & Compliance Center

Die Konfigurationsoptionen für spoof intelligence werden unter [Spoofeinstellungen in Antiphishingrichtlinien beschrieben.](set-up-anti-phishing-policies.md#spoof-settings)

Sie können Einstellungen für spoof intelligence in der Standardmäßigen Antiphishingrichtlinie und auch in benutzerdefinierten Richtlinien konfigurieren. Anweisungen basierend auf Ihrem Abonnement finden Sie in einem der folgenden Themen:

- [Konfigurieren von Antiphishingrichtlinien in EOP](configure-anti-phishing-policies-eop.md).

- [Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365](configure-atp-anti-phishing-policies.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Verwenden Sie einen der folgenden Schritte, um zu überprüfen, ob Sie spoof intelligence mit Absendern konfiguriert haben, die spoofen dürfen und nicht spoofen dürfen, und ob Sie die Einstellungen für spoof intelligence konfiguriert haben:

- Wechseln Sie im Security & Compliance  Center zu Bedrohungsverwaltungsrichtlinie \>  \> **Antispam** erweitern \> **Spoof Intelligence Policy** select Show me \> **senders I already reviewed** select the Your \> **Domains** or **External Domains,** and verify the **Allowed to spoof?** value for the sender.

- Führen Sie in PowerShell die folgenden Befehle aus, um die Absender anzuzeigen, die spoofen dürfen und nicht dürfen:

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- Führen Sie in PowerShell den folgenden Befehl aus, um die Liste aller gefälschten Absender in eine CSV-Datei zu exportieren:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- Wechseln Sie im Security & Compliance  Center zu Bedrohungsverwaltungsrichtlinie \>  \> **Antiphishing** oder **ATP-Antiphishing,** und gehen Sie wie folgt vor:  

  - Wählen Sie eine Richtlinie aus der Liste aus. Überprüfen Sie im angezeigten Flyout die Werte im **Abschnitt Spoof.**
  - Klicken Sie **auf Standardrichtlinie**. Überprüfen Sie im angezeigten Flyout die Werte im **Abschnitt Spoof.**

- Ersetzen Sie in Exchange Online PowerShell durch Office365 AntiPhish Default oder den Namen einer benutzerdefinierten Richtlinie, und führen Sie den folgenden Befehl aus, um die \<Name\> Einstellungen zu überprüfen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Weitere Möglichkeiten zum Verwalten von Spoofing und Phishing

Sind Sie sorgfältig beim Thema Spoofing und Phishingschutz. Hier finden Sie verwandte Möglichkeiten zum Überprüfen von Absendern, die Ihre Domäne spoofieren, und um zu verhindern, dass diese Ihre Organisation beschädigen:

- Überprüfen Sie **den Spoof-E-Mail-Bericht**. Sie können diesen Bericht häufig zum Anzeigen und Verwalten gefälschter Absender verwenden. Weitere Informationen finden Sie unter [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).

- Überprüfen Sie die Konfiguration des Sender Policy Framework (SPF). Eine kurze Einführung in SPF und seine schnelle Konfiguration finden Sie unter [Einrichten von SPF in Microsoft 365 zur Verhinderung von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Ausführlichere Informationen zur Verwendung von SPF durch Office 365 oder zur Problembehandlung oder zu nicht standardmäßigen Bereitstellungen, z. B. Hybridbereitstellungen, finden Sie unter [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

- Überprüfen Sie Die Konfiguration von "DomainKeys Identified Mail" (DKIM). Sie sollten DKIM zusätzlich zu SPF und DMARC verwenden, um zu verhindern, dass Angreifer Nachrichten senden, die so aussehen, als würden sie von Ihrer Domäne kommen. Mit DKIM können Sie E-Mail-Nachrichten in der Kopfzeile der Nachricht eine digitale Signatur hinzufügen. Weitere Informationen finden Sie unter [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).

- Überprüfen Sie Die Domänenbasierte Nachrichtenauthentifizierung, -berichterstellung und -konformität (DMARC). Die Implementierung von DMARC zusammen mit SPF und DKIM bietet zusätzlichen Schutz vor Spoofing- und Phishing-E-Mails. DMARC unterstützt die E-Mail-Systeme der Empfänger bei der Behandlung von Nachrichten, die von Ihrer Domäne gesendet wurden, jedoch die SPF- oder DKIM-Prüfungen nicht bestanden haben. Weitere Informationen finden Sie unter [Verwenden von DMARC zum Überprüfen von E-Mails in Office 365](use-dmarc-to-validate-email.md).