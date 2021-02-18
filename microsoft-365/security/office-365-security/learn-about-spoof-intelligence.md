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
description: Administratoren können mehr über Spoofing Intelligence in Exchange Online Protection (EOP) erfahren, wo Sie bestimmte gefälschte Absender zulassen oder blockieren können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a65400d1b48abfc6ac0e4dd38a8245dd7b4f87b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289687"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Konfigurieren der Spoofintelligenz in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden eingehende E-Mail-Nachrichten ab Oktober 2018 automatisch durch EOP vor Spoofing geschützt. EOP verwendet Spoofintelligenz als Teil der allgemeinen Verteidigung Ihrer Organisation gegen Phishing. Weitere Informationen finden Sie unter [Antis spoofing protection in EOP](anti-spoofing-protection.md).

Wenn ein Absender eine E-Mail-Adresse spoofiert, scheint er ein Benutzer in einer der Domänen Ihrer Organisation oder ein Benutzer in einer externen Domäne zu sein, der E-Mails an Ihre Organisation sendet. Angreifer, die Absender zum Senden von Spam- oder Phishing-E-Mails gefälscht haben, müssen blockiert werden. Es gibt jedoch Szenarien, in denen legitime Absender Spoofing verwenden. Zum Beispiel:

- Legitime Szenarien für Spoofing interner Domänen:

  - Absender von Drittanbietern verwenden Ihre Domäne, um Massen-E-Mails für Unternehmensumfragen an Ihre eigenen Mitarbeiter zu senden.
  - Ein externes Unternehmen generiert und sendet Werbung oder Produktupdates in Ihrem Auftrag.
  - Ein Assistent muss regelmäßig E-Mails an eine andere Person in Ihrer Organisation senden.
  - Eine interne Anwendung sendet E-Mail-Benachrichtigungen.

- Legitime Szenarien für Spoofing externer Domänen:

  - Der Absender befindet sich in einer Mailingliste (auch als Diskussionsliste bezeichnet), und die Mailingliste leitet E-Mails vom ursprünglichen Absender an alle Teilnehmer in der Mailingliste weiter.
  - Ein externes Unternehmen sendet E-Mails im Auftrag eines anderen Unternehmens (z. B. einen automatisierten Bericht oder ein Software-as-a-Service-Unternehmen).

Spoofing intelligence, und insbesondere die standardmäßige (und einzige) Spoofing Intelligence-Richtlinie, trägt dazu bei, sicherzustellen, dass die von legitimen Absendern gesendeten gefälschten E-Mails nicht in #A0 oder externen E-Mail-Systemen auffangen, während Ihre Benutzer vor Spam- oder Phishingangriffen geschützt werden.

Sie können Spoofintelligenz im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange & ) verwalten.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://protection.office.com/antispam>. Um direkt zur **Antiphishingseite zu** wechseln, verwenden Sie <https://protection.office.com/antiphishing> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Um die Spoofintelligenzrichtlinie zu ändern oder Spoofintelligenz zu aktivieren oder zu deaktivieren, müssen Sie Mitglied der Rollengruppe **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Für den schreibgeschützten Zugriff auf die Spoofintelligenzrichtlinie müssen Sie Mitglied der Rollengruppe "Globaler Leser" oder **"Sicherheitsleser"** sein. 

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweise**:

  - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Die empfohlenen Einstellungen für spoofing intelligence finden Sie unter [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Verwenden des Security & Compliance Center zum Verwalten von gefälschten Absendern

> [!NOTE]
> Wenn Sie über ein Microsoft 365 Enterprise E5-Abonnement verfügen oder ein Microsoft Defender für Office 365-Add-On separat erworben haben, können Sie auch Absender verwalten, die Ihre Domäne über den Einblick in [Spoof Intelligence](walkthrough-spoof-intelligence-insight.md)gefälscht haben.

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie **auf der Seite "Antispameinstellungen"** auf das Symbol "Erweitern", ![ um die ](../../media/scc-expand-icon.png) **Spoofing-Intelligence-Richtlinie zu erweitern.**

   ![Auswählen der Spoofintelligenzrichtlinie](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Treffen Sie eine der folgenden Optionen:

   - **Überprüfen neuer Absender**
   - **Absender anzeigen, die ich bereits überprüft habe**

4. Wählen Sie **im angezeigten Flyout** "Entscheiden, ob diese Absender Ihren Benutzern spoofing dürfen" eine der folgenden Registerkarten aus:

   - **Ihre Domänen:** Absender fälscht Benutzer in Ihren internen Domänen.
   - **Externe Domänen:** Absender, die Benutzer in externen Domänen gefälscht haben.

5. Klicken ![ Sie in der Spalte ](../../media/scc-expand-icon.png) **"Spoofing** zugelassen" auf das Symbol "Erweitern". Wählen **Sie "Ja"** aus, um den gefälschten Absender zu erlauben, oder wählen Sie **"Nein"** aus, um die Nachricht als spoofing zu markieren. Die Aktion wird durch die standardmäßige Antiphishingrichtlinie oder benutzerdefinierte Antiphishingrichtlinien gesteuert (der Standardwert ist "Nachricht in Junk-E-Mail-Ordner **verschieben").** Weitere Informationen finden Sie unter ["Spoofing"-Einstellungen in Antiphishingrichtlinien.](set-up-anti-phishing-policies.md#spoof-settings)

   ![Screenshot des Flyouts für gefälschte Absender und Angaben dazu, ob der Absender Spoofing verwenden darf](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   Die angezeigten Spalten und Werte werden in der folgenden Liste erläutert:

   - **Gefälschter Benutzer:** Das Benutzerkonto, das gefälscht wird. Dies ist der Absender der Nachricht in der Absenderadresse (auch als Adresse bezeichnet), die `5322.From` in E-Mail-Clients angezeigt wird. Die Gültigkeit dieser Adresse wird von SPF nicht überprüft.

     - Auf der **Registerkarte "Ihre Domänen"** enthält der Wert eine einzelne E-Mail-Adresse, oder wenn der Quell-E-Mail-Server mehrere Benutzerkonten gefälscht hat, enthält er **mehrere**.

     - Auf der **Registerkarte "Externe Domänen"** enthält der Wert die Domäne des gefälschten Benutzers, nicht die vollständige E-Mail-Adresse.

   - **Sendende Infrastruktur:** Die Domäne in einem Reverse-DNS-Lookup (PTR-Eintrag) der QUELL-E-Mail-Server-IP-Adresse. Wenn die Quell-IP-Adresse keinen PTR-Eintrag hat, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).

     Weitere Informationen zu Nachrichtenquellen und Nachrichtensendern finden Sie in [einer Übersicht über E-Mail-Nachrichtenstandards.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

   - **Anzahl der Nachrichten:** Die Anzahl der Nachrichten von der sendenden Infrastruktur an Ihre Organisation, die die angegebenen gefälschten Absender oder Absender innerhalb der letzten 30 Tage enthalten.

   - **Anzahl der Benutzerbeschwerden:** Beschwerden, die von Ihren Benutzern innerhalb der letzten 30 Tage gegen diesen Absender eingereicht wurden. Beschwerden werden in der Regel in Form von Junk-E-Mails an Microsoft gesendet.

   - **Authentifizierungsergebnis:** Einer der folgenden Werte:
      - **Übergeben:** Der Absender hat E-Mail-Authentifizierungsprüfungen (SPF oder DKIM) des Absenders bestanden.
      - **Fehler: Der** Absender hat die EOP-Absender-Authentifizierungsprüfungen nicht durchgeführt.
      - **Unbekannt:** Das Ergebnis dieser Überprüfungen ist nicht bekannt.

   - **Entscheidungssatz:** Zeigt an, wer bestimmt hat, ob die sendende Infrastruktur den Benutzer spoofen darf:
       - **Spoofing Intelligence Policy** (automatisch)
       - **Administrator** (manuell)

   - **Zuletzt gesehen:** Das letzte Datum, an dem eine Nachricht von der sendenden Infrastruktur empfangen wurde, die den gefälschten Benutzer enthält.

   - **Spoofing zulässig?**: Die hier angezeigten Werte sind:
     - **Ja:** Nachrichten aus der Kombination aus gefälschten Benutzern und sendender Infrastruktur sind zulässig und werden nicht als gefälschte E-Mails behandelt.
     - **Nein:** Nachrichten aus der Kombination aus gefälschten Benutzern und sendender Infrastruktur werden als Spoofing gekennzeichnet. Die Aktion wird durch die standardmäßige Antiphishingrichtlinie oder benutzerdefinierte Antiphishingrichtlinien gesteuert (der Standardwert ist "Nachricht in Junk-E-Mail-Ordner **verschieben").** Weitere Informationen finden Sie im nächsten Abschnitt.

     - **Einige Benutzer** (nur Registerkarte **"Ihre** Domänen"): Eine sendende Infrastruktur fälscht mehrere Benutzer, wobei einige gefälschte Benutzer zulässig sind und andere nicht. Verwenden Sie die **Registerkarte "Detail",** um die spezifischen Adressen zu sehen.

6. Klicken Sie unten auf der Seite auf **Speichern**.

## <a name="use-powershell-to-manage-spoofed-senders"></a>Verwenden von PowerShell zum Verwalten von gefälschten Absendern

Verwenden Sie die folgende Syntax, um zugelassene und blockierte Absender in Spoofintelligenz anzeigen zu können:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

In diesem Beispiel werden detaillierte Informationen zu allen Absendern zurückgegeben, die Benutzer in Ihren Domänen spoofen dürfen.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).

Führen Sie die folgenden Schritte aus, um zugelassene und blockierte Absender in Spoofing Intelligence zu konfigurieren:

1. Erfassen Sie die aktuelle Liste der erkannten gefälschten Absender, indem Sie die Ausgabe des **Cmdlets "Get-PhishFilterPolicy"** in eine CSV-Datei schreiben:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Bearbeiten Sie die CSV-Datei, um die **Werte "SpoofedUser"** (E-Mail-Adresse) und **"AllowedToSpoof"** (Ja oder Nein) hinzuzufügen oder zu ändern. Speichern Sie die Datei, lesen Sie die Datei, und speichern Sie den Inhalt als Variable mit dem Namen `$UpdateSpoofedSenders` :

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Verwenden Sie die `$UpdateSpoofedSenders` Variable, um die Spoofintelligenzrichtlinie zu konfigurieren:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Konfigurieren der Spoofintelligenz mithilfe des Security & Compliance Center

Die Konfigurationsoptionen für Spoofintelligenz werden in [den Spoofeinstellungen in Antiphishingrichtlinien beschrieben.](set-up-anti-phishing-policies.md#spoof-settings)

Sie können Einstellungen für die Spoofintelligenz in der standardmäßigen Antiphishingrichtlinie und auch in benutzerdefinierten Richtlinien konfigurieren. Anweisungen basierend auf Ihrem Abonnement finden Sie unter einem der folgenden Themen:

- [Konfigurieren von Antiphishingrichtlinien in EOP](configure-anti-phishing-policies-eop.md).

- [Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365](configure-atp-anti-phishing-policies.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Um sicherzustellen, dass Sie spoofing intelligence mit Absendern konfiguriert haben, die spoofing dürfen und nicht spoofing dürfen, und ob Sie die Einstellungen für spoofing intelligence konfiguriert haben, verwenden Sie einen der folgenden Schritte:

- Wechseln Sie im Security & Compliance  Center zu Richtlinie zur \>  \> Bedrohungsverwaltung **Antispam** erweitern \> **Spoofing Intelligence Policy** select Show me \> **senders I already reviewed** select the Your \> **Domains** or **External Domains** tab, and verify the Allowed to **spoof?** value for the sender.

- Führen Sie in PowerShell die folgenden Befehle aus, um die Absender anzuzeigen, die spoofing dürfen und nicht:

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

- Wechseln Sie im Security & Compliance Center zu "Threat **Management** \> **Policy** \> **Anti-phishing"** oder **"ATP anti-phishing",** und gehen Sie zu einem der folgenden Schritte:  

  - Wählen Sie eine Richtlinie aus der Liste aus. Überprüfen Sie im angezeigten Flyout die Werte im Abschnitt **"Spoofing".**
  - Klicken Sie **auf "Standardrichtlinie".** Überprüfen Sie im angezeigten Flyout die Werte im Abschnitt **"Spoofing".**

- Ersetzen Sie in Exchange Online PowerShell durch Office365 AntiPhish Default oder den Namen einer benutzerdefinierten Richtlinie, und führen Sie den folgenden Befehl aus, um die \<Name\> Einstellungen zu überprüfen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Weitere Möglichkeiten zum Verwalten von Spoofing und Phishing

Sind Sie sorgfältig im Thema Spoofing und Phishingschutz. Hier finden Sie verwandte Möglichkeiten zum Überprüfen von Absendern, die Ihre Domäne gefälscht haben, und um zu verhindern, dass sie Ihre Organisation beschädigen:

- Überprüfen Sie den **Spoof-E-Mail-Bericht.** Sie können diesen Bericht häufig zum Anzeigen und Verwalten von gefälschten Absendern verwenden. Weitere Informationen finden Sie im [Bericht über Spooferkennungen.](view-email-security-reports.md#spoof-detections-report)

- Überprüfen Sie die Konfiguration des Sender Policy Framework (SPF). Eine kurze Einführung in SPF und seine schnelle Konfiguration finden Sie unter [Einrichten von SPF in Microsoft 365 zur Verhinderung von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Ausführlichere Informationen zur Verwendung von SPF durch Office 365 oder zur Problembehandlung oder zu nicht standardmäßigen Bereitstellungen, z. B. Hybridbereitstellungen, finden Sie unter [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

- Überprüfen Sie Ihre Konfiguration der DKIM (DomainKeys Identified Mail). Sie sollten DKIM zusätzlich zu SPF und DMARC verwenden, um zu verhindern, dass Angreifer Nachrichten senden, die so aussehen, als würden sie von Ihrer Domäne kommen. Mit DKIM können Sie E-Mail-Nachrichten in der Kopfzeile der Nachricht eine digitale Signatur hinzufügen. Weitere Informationen finden Sie unter Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von [Ihrer benutzerdefinierten Domäne in Office 365 gesendet werden.](use-dkim-to-validate-outbound-email.md)

- Überprüfen Sie Ihre Domänen-basierte Konfiguration für Nachrichtenauthentifizierung, Berichterstellung und Konformität (DMARC). Die Implementierung von DMARC zusammen mit SPF und DKIM bietet zusätzlichen Schutz vor Spoofing- und Phishing-E-Mails. DMARC unterstützt die E-Mail-Systeme der Empfänger bei der Behandlung von Nachrichten, die von Ihrer Domäne gesendet wurden, jedoch die SPF- oder DKIM-Prüfungen nicht bestanden haben. Weitere Informationen finden Sie unter [Verwenden von DMARC zum Überprüfen von E-Mails in Office 365.](use-dmarc-to-validate-email.md)
