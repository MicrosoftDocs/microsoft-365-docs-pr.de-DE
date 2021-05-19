---
title: Verwalten von gefälschten Absendern mithilfe der Spoof Intelligence Policy und spoof intelligence insight
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie die Spoof Intelligence Policy und den Einblick in spoof intelligence verwenden, um erkannte spoofierte Absender zu erlauben oder zu blockieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 821488f79186e1b5c306b587764377989346eea5
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530886"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a>Verwalten von gefälschten Absendern mithilfe der Spoof Intelligence Policy und spoof intelligence insight in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> In diesem Artikel wird die ältere spoofierte Absenderverwaltungserfahrung beschrieben, die ersetzt wird. Weitere Informationen zur neuen Erfahrung finden Sie unter [Spoof Intelligence Insight in EOP](learn-about-spoof-intelligence.md)

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden eingehende E-Mail-Nachrichten ab Oktober 2018 automatisch vor Spoofing durch EOP geschützt. EOP verwendet **Spoof Intelligence** als Teil der allgemeinen Verteidigung Ihrer Organisation gegen Phishing. Weitere Informationen finden Sie unter Schutz vor [Spoofing in EOP](anti-spoofing-protection.md).

Die Standardmäßige (und einzige) **Spoof** intelligence-Richtlinie hilft sicherzustellen, dass die gefälschten E-Mails, die von legitimen Absendern gesendet werden, nicht in #A0 versenkt werden, während Ihre Benutzer vor Spam- oder Phishingangriffen geschützt werden. Sie können auch den Einblick in die **Spoof-Intelligenz** verwenden, um schnell zu ermitteln, welche externen Absender Ihnen legitimerweise nicht authentifizierte E-Mails senden (Nachrichten von Domänen, die keine SPF-, DKIM- oder DMARC-Prüfungen bestehen).

Sie können Spoof Intelligence im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer) verwalten.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.
  - Um direkt zur Seite **Antispameinstellungen** für die Spoof Intelligence-Richtlinie zu wechseln, verwenden Sie <https://protection.office.com/antispam> .
  - Verwenden Sie , um direkt zur **Seite Sicherheitsdashboard** zu wechseln, um einen Einblick in spoof intelligence zu <https://protection.office.com/searchandinvestigation/dashboard> erhalten.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:
  - Um die Spoof Intelligence-Richtlinie zu ändern oder Spoof Intelligence zu  aktivieren oder zu deaktivieren, müssen Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein.
  - Für den schreibgeschützten Zugriff auf die Spoof Intelligence-Richtlinie müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweise**:

  - Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Die Optionen für spoof intelligence werden unter [Spoofeinstellungen in Antiphishingrichtlinien beschrieben.](set-up-anti-phishing-policies.md#spoof-settings)

- Sie können die Einstellungen für spoof intelligence in Antiphishingrichtlinien aktivieren, deaktivieren und konfigurieren. Anweisungen basierend auf Ihrem Abonnement finden Sie in einem der folgenden Themen:

  - [Konfigurieren von Antiphishingrichtlinien in EOP](configure-anti-phishing-policies-eop.md).
  - [Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365.](configure-atp-anti-phishing-policies.md)

- Unsere empfohlenen Einstellungen für spoof intelligence finden Sie unter [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).

## <a name="manage-spoofed-senders"></a>Verwalten gefälschter Absender

Es gibt zwei Möglichkeiten, gefälschte Absender zu erlauben und zu blockieren:

- [Verwenden der Spoof Intelligence-Richtlinie](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [Verwenden der Einblicke in spoof intelligence](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a>Verwalten gefälschter Absender in der Spoof Intelligence-Richtlinie

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

#### <a name="use-powershell-to-manage-spoofed-senders"></a>Verwenden von PowerShell zum Verwalten gefälschter Absender

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

1. Erfassen Sie die aktuelle Liste der erkannten gefälschten Absender, indem Sie die Ausgabe des **Get-PhishFilterPolicy-Cmdlets** in eine CSV-Datei schreiben, indem Sie den folgenden Befehl ausführen:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Bearbeiten Sie die CSV-Datei, um die folgenden Werte hinzuzufügen oder zu ändern:
   - **Sender** (Domäne im PTR-Eintrag oder der IP/24-Adresse des Quellservers)
   - **SpoofedUser**: Einer der folgenden Werte:
     - Die E-Mail-Adresse des internen Benutzers.
     - Die E-Mail-Domäne des externen Benutzers.
     - Ein leerer Wert, der angibt, dass Sie spoofierte Nachrichten vom angegebenen **Absender** blockieren oder zulassen möchten, unabhängig von der gefälschten E-Mail-Adresse.
   - **AllowedToSpoof** (Ja oder Nein)
   - **SpoofType** (Intern oder Extern)

   Speichern Sie die Datei, lesen Sie die Datei, und speichern Sie den Inhalt als Variable `$UpdateSpoofedSenders` namens, indem Sie den folgenden Befehl ausführen:

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Verwenden Sie `$UpdateSpoofedSenders` die Variable, um die Spoof Intelligence-Richtlinie zu konfigurieren, indem Sie den folgenden Befehl ausführen:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a>Verwalten von gefälschten Absendern in der Einblicke in spoof intelligence

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Dashboard**.

2. Suchen Sie **in** der Zeile Insights nach einem der folgenden Elemente:

   - **Wahrscheinlich spoofierte Domänen in** den letzten sieben Tagen: Diese Einsicht gibt an, dass Spoofintelligenz aktiviert ist (standardmäßig aktiviert).
   - **Spoofschutz** aktivieren: Diese Einsicht zeigt an, dass die Spoofintelligenz deaktiviert ist, und wenn Sie auf die Einblicke klicken, können Sie die Spoofintelligenz aktivieren.

3. Die Einblicke im Dashboard zeigen Ihnen Informationen wie dies:

   ![Screenshot der Einblicke in spoof intelligence](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Diese Einsicht hat zwei Modi:

   - **Einblicksmodus:** Wenn spoof intelligence aktiviert ist, zeigt die Einsicht, wie viele Nachrichten in den letzten sieben Tagen von unseren Funktionen für spoof intelligence betroffen waren.
   - **Was wäre,** wenn Der Modus : Wenn die Spoofintelligenz deaktiviert ist, zeigt die Einsicht, wie viele Nachrichten in den letzten sieben Tagen von unseren Funktionen für spoof intelligence betroffen waren. 

   So oder so sind die spoofierten Domänen, die in der Einsicht angezeigt werden, in zwei Kategorien unterteilt: Verdächtige **Domänen** und **Nicht verdächtige Domänen.**

   - **Verdächtige Domänen**:
     - **Spoofing** mit hoher Vertrauenswürdigkeit: Basierend auf den historischen Sendemustern und der Reputationsnote der Domänen sind wir sehr sicher, dass die Domänen Spoofing sind, und Nachrichten von diesen Domänen sind mit hoher Wahrscheinlichkeit schädlich.
     - **Moderater** Konfidenzs spoof : Basierend auf historischen Sendemustern und der Reputationsnote der Domänen sind wir moderat davon überzeugt, dass die Domänen spoofing sind und dass nachrichten, die von diesen Domänen gesendet werden, legitim sind. Falsch positive Ergebnisse sind in dieser Kategorie wahrscheinlicher als spoof mit hoher Wahrscheinlichkeit.
   - **Nicht verdächtige Domänen:** Die explizite E-Mail-Authentifizierung der Domäne hat [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC nicht überprüft.](use-dmarc-to-validate-email.md) Die Domäne hat jedoch unsere impliziten E-Mail-Authentifizierungsprüfungen ([zusammengesetzte Authentifizierung](email-validation-and-authentication.md#composite-authentication)) bestanden. Aus diesem Grund wurde keine Antis spoofing-Aktion für die Nachricht ergriffen.

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a>Anzeigen detaillierter Informationen zu verdächtigen und nicht unauffälligen Domänen

1. Klicken Sie auf der Einblicksseite  spoof intelligence auf Verdächtige **Domänen** oder nicht verdächtige Domänen, um zur **Seite Spoof Intelligence Insight zu** wechseln. Die **Seite Spoof Intelligence Insight** enthält die folgenden Informationen:

   - **Spoofed domain:** Die Domäne des spoofierten Benutzers, die im Feld **Von** in E-Mail-Clients angezeigt wird. Diese Adresse wird auch als Adresse `5322.From` bezeichnet.
   - **Infrastruktur**: Wird auch als sendende _Infrastruktur bezeichnet._ Die Domäne in einer Reverse-DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers. Wenn die Quell-IP-Adresse keinen PTR-Eintrag enthält, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).
   - **Nachrichtenanzahl**: Die Anzahl der Nachrichten aus der sendenden Infrastruktur an Ihre Organisation, die die angegebene spoofed-Domäne innerhalb der letzten 7 Tage enthalten.
   - **Zuletzt gesehen:** Das letzte Datum, an dem eine Nachricht von der sendenden Infrastruktur empfangen wurde, die die spoofierte Domäne enthält.
   - **Spooftyp**: Dieser Wert ist **External**.
   - **Darf ges spooft werden?**: Die hier angezeigten Werte sind:
     - **Ja:** Nachrichten aus der Kombination aus der Domäne des spoofierten Benutzers und der Sendeinfrastruktur sind zulässig und werden nicht als gefälschte E-Mails behandelt.
     - **Nein:** Nachrichten aus der Kombination aus der Domäne des spoofierten Benutzers und der sendenden Infrastruktur werden als Spoofing gekennzeichnet. Die Aktion wird durch die standardmäßige Antiphishingrichtlinie oder benutzerdefinierte Antiphishingrichtlinien gesteuert (der Standardwert ist **Move message to Junk Email folder**).

2. Wählen Sie ein Element in der Liste aus, um Details zum Domänen-/Sendeinfrastrukturpaar in einem Flyout anzuzeigen. Die Informationen umfassen:
   - Warum wir dies erwischt haben.
   - Was Sie tun müssen.
   - Eine Domänenzusammenfassung.
   - WhoIs-Daten über den Absender.
   - Ähnliche Nachrichten, die wir in Ihrem Mandanten vom gleichen Absender gesehen haben.

   Von hier aus können Sie auch das Domänen-/Sendeinfrastrukturpaar aus der Liste zugelassener Absender **spoofieren** hinzufügen oder entfernen. Legen Sie einfach die Umschalte entsprechend ein.

   ![Screenshot einer Domäne im Detailbereich "Spoof Intelligence Insight"](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Verwenden Sie einen der folgenden Schritte, um sicherzustellen, dass Sie spoof intelligence mit Absendern konfiguriert haben, die spoofen dürfen und nicht spoofen dürfen:

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
