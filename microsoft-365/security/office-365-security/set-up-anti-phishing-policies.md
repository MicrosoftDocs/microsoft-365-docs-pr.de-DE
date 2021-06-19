---
title: Antiphishing-Richtlinien
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die Antiphishingrichtlinien informieren, die in Exchange Online Protection (EOP) und Microsoft Defender für Office 365 verfügbar sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 846043be72be741e60c09c85fba14dbf291612a1
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029369"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Antiphishingrichtlinien in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Richtlinien zum Konfigurieren von Antiphishingschutzeinstellungen sind in Microsoft 365 Organisationen mit Exchange Online Postfächern, eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer und Microsoft Defender für Office 365 Organisationen verfügbar.

Antiphishingrichtlinien in Microsoft Defender für Office 365 sind nur in Organisationen verfügbar, die Defender für Office 365 haben. Beispiel:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5 usw.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender für Office 365 als Add-On](https://products.office.com/exchange/advance-threat-protection)

Die allgemeinen Unterschiede zwischen Antiphishingrichtlinien in EOP und Antiphishingrichtlinien in Microsoft Defender für Office 365 werden in der folgenden Tabelle beschrieben:

****

|Feature|Antiphishingrichtlinien in EOP|Antiphishingrichtlinien in Microsoft Defender für Office 365|
|---|:---:|:---:|
|Automatisch erstellte Standardrichtlinie|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|Erstellen Sie benutzerdefinierte Richtlinien|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|Richtlinieneinstellungen<sup>\*</sup>|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|Identitätswechseleinstellungen||![Häkchen](../../media/checkmark.png)|
|Spoofingeinstellungen|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|Erweiterte Phishing-Schwellenwerte||![Häkchen](../../media/checkmark.png)|
|

<sup>\*</sup> In der Standardrichtlinie sind der Richtlinienname und die Beschreibung schreibgeschützt (die Beschreibung ist leer), und Sie können nicht angeben, für wen die Richtlinie gilt (die Standardrichtlinie gilt für alle Empfänger).

Informationen zum Konfigurieren von Antiphishingrichtlinien finden Sie in den folgenden Artikeln:

- [Konfigurieren von Anti-Phishing-Richtlinien in EOP](configure-anti-phishing-policies-eop.md)

- [Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365](configure-mdo-anti-phishing-policies.md)

Der Rest dieses Artikels beschreibt die Einstellungen, die in Antiphishingrichtlinien in EOP und Defender für Office 365 verfügbar sind.

## <a name="policy-settings"></a>Richtlinieneinstellungen

Die folgenden Richtlinieneinstellungen sind in Antiphishingrichtlinien in EOP und Microsoft Defender für Office 365 verfügbar:

- **Name:** Sie können die Standardmäßige Antiphishingrichtlinie nicht umbenennen. Nachdem Sie eine benutzerdefinierte Antiphishingrichtlinie erstellt haben, können Sie die Richtlinie nicht im Security & Compliance Center umbenennen.

- **Beschreibung** Sie können der standardmäßigen Antiphishingrichtlinie keine Beschreibung hinzufügen, aber Sie können die Beschreibung für benutzerdefinierte Richtlinien, die Sie erstellen, hinzufügen und ändern.

- **Angewendet auf:** Identifiziert interne Empfänger, für die die Antiphishingrichtlinie gilt. Dieser Wert ist in benutzerdefinierten Richtlinien erforderlich und in der Standardrichtlinie nicht verfügbar (die Standardrichtlinie gilt für alle Empfänger).

  Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

  - **Empfänger ist:** ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.
  - **Der Empfänger ist Mitglied von**: Eine oder mehrere Gruppen in Ihrer Organisation.
  - **Die Empfängerdomäne lautet:** eine oder mehrere der konfigurierten akzeptierten Domänen in Microsoft 365.

  - **Außer wenn:** Ausnahmen für die Regel. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen:

    - **Empfänger lautet**
    - **Recipient is a member of**
    - **Die Empfängerdomäne ist**

  > [!NOTE]
  > Die Einstellung **"Angewendet auf"** ist in benutzerdefinierten Antiphishingrichtlinien erforderlich, um die **Nachrichtenempfänger** zu <u>identifizieren, für die die Richtlinie gilt.</u> Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügen auch [über Identitätswechseleinstellungen,](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) in denen Sie einzelne Absender-E-Mail-Adressen oder Absenderdomänen angeben <u>können, die den Identitätswechselschutz erhalten,</u> wie weiter unten in diesem Artikel beschrieben.

## <a name="spoof-settings"></a>Spoofingeinstellungen

Spoofing ist der Fall, wenn die Absenderadresse in einer E-Mail-Nachricht (die Absenderadresse, die in E-Mail-Clients angezeigt wird) nicht mit der Domäne der E-Mail-Quelle übereinstimmt. Weitere Informationen zum Spoofing finden Sie unter [Antispoofingschutz in Microsoft 365](anti-spoofing-protection.md).

Die folgenden Spoofingeinstellungen sind in Antiphishingrichtlinien in EOP und Microsoft Defender für Office 365 verfügbar:

- **Spoofintelligenz aktivieren?**: Aktiviert oder deaktiviert die Spoofintelligenz. Es wird empfohlen, die Option aktiviert zu lassen.

  Wenn die Spoofintelligenz aktiviert ist, zeigt der Einblick in die **Spoofintelligenz** gefälschte Absender an, die automatisch erkannt und durch Spoofintelligenz zugelassen oder blockiert wurden. Sie können die Spoofintelligenzbewertung manuell außer Kraft setzen, um die erkannten gefälschten Absender innerhalb des Einblicks zuzulassen oder zu blockieren. Wenn Sie dies jedoch tun, wird der gefälschte Absender aus dem Einblick in die Spoofintelligenz ausgeblendet und ist jetzt nur auf der Registerkarte **"Spoofing"** in der Mandanten-Zulassungs-/Sperrliste sichtbar. Sie können auch einträge für gefälschte Absender in der Mandanten-Zulassungs-/Sperrliste manuell erstellen oder blockieren. Weitere Informationen finden Sie in den folgenden Themen:

  - [Einblick in die Spoofintelligenz in EOP](learn-about-spoof-intelligence.md)
  - [Verwalten der Mandanten-Zulassungs-/Sperrliste in EOP](tenant-allow-block-list.md)

  > [!NOTE]
  >
  > - Der Antispoofingschutz ist in der Standard-Antiphishingrichtlinie und in allen neuen benutzerdefinierten Antiphishingrichtlinien, die Sie erstellen, standardmäßig aktiviert.
  >
  > - Sie müssen den Antispoofingschutz nicht deaktivieren, wenn Ihr MX-Eintrag nicht auf Microsoft 365 verweist. Aktivieren Sie stattdessen die erweiterte Filterung für Connectors. Anweisungen finden Sie unter ["Erweiterte Filterung für Connectors" in Exchange Online.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)
  >
  > - Durch das Deaktivieren des Antispoofingschutzes wird nur der implizite Spoofingschutz von [zusammengesetzten Authentifizierungsprüfungen](email-validation-and-authentication.md#composite-authentication) deaktiviert. Wenn der Absender keine expliziten [DMARC-Prüfungen](use-dmarc-to-validate-email.md) vorgibt, in denen die Richtlinie unter Quarantäne gestellt oder abgelehnt wird, wird die Nachricht weiterhin unter Quarantäne gestellt oder abgelehnt.

- **Einstellungen für nicht authentifizierte Absender:** Weitere Informationen finden Sie im nächsten Abschnitt.

- **Aktionen:** Für Nachrichten von blockierten gefälschten Absendern (automatisch durch Spoofintelligenz blockiert oder manuell in der Mandanten-Zulassungs-/Sperrliste blockiert) können Sie auch die Aktion angeben, die für die Nachrichten ausgeführt werden soll:

  - **Verschieben von Nachrichten in die Junk-E-Mail-Ordner des Empfängers:** Dies ist der Standardwert. Die Nachricht wird an das Postfach übermittelt und in den Junk-E-Mail-Ordner verschoben. In Exchange Online wird die Nachricht in den Junk-E-Mail-Ordner verschoben, wenn die Junk-E-Mail-Regel für das Postfach aktiviert ist (sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online Postfächer in Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

  - **Die Nachricht unter Quarantäne** stellen: Sendet die Nachricht an die Quarantäne anstelle der vorgesehenen Empfänger. Informationen zur Quarantäne finden Sie in den folgenden Artikeln:

    - [Quarantäne in Microsoft 365](quarantine-email-messages.md)
    - [Verwalten von isolierten Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

### <a name="unauthenticated-sender"></a>Nicht authentifizierter Absender

Nicht authentifizierte Absendereinstellungen sind Teil der [Spoofingeinstellungen,](#spoof-settings) die in Antiphishingrichtlinien in EOP und Microsoft Defender für Office 365 verfügbar sind, wie im vorherigen Abschnitt beschrieben.

- **Aktivieren Sie das Fragezeichen (?) für nicht authentifizierte Absender?**: Wenn diese Einstellung aktiviert ist, wird dem Foto des Absenders im Feld "Von" ein Fragezeichen hinzugefügt, wenn die Nachricht keine SPF- oder DKIM-Prüfungen besteht **und** die Nachricht keine DMARC- oder [zusammengesetzte Authentifizierung](email-validation-and-authentication.md#composite-authentication)besteht. Wenn diese Einstellung deaktiviert ist, wird das Fragezeichen nicht zum Foto des Absenders hinzugefügt.

- **Aktivieren Sie das "via"-Tag?** <sup>\*</sup> : Wenn diese Einstellung aktiviert ist, wird das Via-Tag (chris@contoso.com <u>über</u> fabrikam.com) im Feld "Von" hinzugefügt, wenn sich die Domäne in der Absenderadresse (der Absender der Nachricht, der in E-Mail-Clients angezeigt wird) von der Domäne in der DKIM-Signatur oder der **MAIL FROM-Adresse** unterscheidet. Weitere Informationen zu diesen Adressen finden Sie unter [Einer Übersicht über E-Mail-Nachrichtenstandards.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

Um zu verhindern, dass das Fragezeichen oder tag nachrichten von bestimmten Absendern hinzugefügt wird, haben Sie die folgenden Optionen:

- Allow the spoofed sender in the [spoof intelligence insight](learn-about-spoof-intelligence.md) or manually in the [Tenant Allow/Block List](tenant-allow-block-list.md). Wenn der gefälschte Absender zugelassen wird, wird verhindert, dass das Via-Tag in Nachrichten des Absenders angezeigt wird, wenn die nicht authentifizierte Absenderidentifikation deaktiviert ist.

- Konfigurieren sie die [E-Mail-Authentifizierung](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) für die Absenderdomäne.
  - Für das Fragezeichen im Foto des Absenders sind SPF oder DKIM das wichtigste.
  - Bestätigen Sie für das Via-Tag die Domäne in der DKIM-Signatur oder die **MAIL FROM-Adresse** mit der Domäne in der Absenderadresse (oder ist eine Unterdomäne der Domäne).

Weitere Informationen finden Sie unter [Identifizieren verdächtiger Nachrichten in Outlook.com und Outlook im Web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Exklusive Einstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365

In diesem Abschnitt werden die Richtlinieneinstellungen beschrieben, die nur in Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügbar sind.

> [!NOTE]
> Die standardmäßige Antiphishingrichtlinie in Microsoft Defender für Office 365 bietet [Spoofschutz](set-up-anti-phishing-policies.md#spoof-settings) und Postfachintelligenz für alle Empfänger. Die anderen verfügbaren [Identitätswechselschutzfeatures](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) und [erweiterten Einstellungen](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) sind jedoch in der Standardrichtlinie nicht konfiguriert oder aktiviert. Um alle Schutzfunktionen zu aktivieren, ändern Sie die Standardmäßige Antiphishingrichtlinie, oder erstellen Sie zusätzliche Antiphishingrichtlinien.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Identitätswechseleinstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365

Der Identitätswechsel ist der Ort, an dem der Absender oder die E-Mail-Domäne des Absenders in einer Nachricht einem echten Absender oder einer echten Domäne ähnelt:

- Ein Beispiel für einen Identitätswechsel der Domäne contoso.com ist ćóntoso.com.
- Ein Beispiel für einen Identitätswechsel der Benutzerin michelle@contoso.com ist michele@contoso.com.

Eine imitierte Domäne kann ansonsten als seriös gelten (registrierte Domäne, konfigurierte E-Mail-Authentifizierungseinträge usw.). Der Unterschied besteht darin, dass damit Empfänger getäuscht werden sollen.

Die folgenden Identitätswechseleinstellungen sind nur in Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügbar:

- **Benutzer zum Schutz hinzufügen:** Verhindert, dass die angegebenen internen oder externen E-Mail-Adressen **als Absender** von Nachrichten imitiert werden. Sie erhalten beispielsweise eine E-Mail-Nachricht vom Vice President Ihres Unternehmens, in der Sie aufgefordert werden, ihr interne Unternehmensinformationen zu senden. Würdest du es tun? Viele Personen würden die Antwort senden, ohne zu denken.

  Sie können geschützte Benutzer verwenden, um interne und externe Absender-E-Mail-Adressen hinzuzufügen, um den Identitätswechsel zu schützen. Diese Liste der Absender, die vor **Benutzeridentitätswechsel** geschützt sind, unterscheidet sich von der Liste der **Empfänger,** auf die die Richtlinie angewendet wird (alle Empfänger für die Standardrichtlinie; bestimmte Empfänger wie in der Einstellung **"Angewendet auf"** im Abschnitt ["Richtlinieneinstellungen"](#policy-settings) konfiguriert).

  > [!NOTE]
  >
  > - In jeder Antiphishingrichtlinie können Sie maximal 60 geschützte Benutzer (Absender-E-Mail-Adressen) angeben. Sie können nicht denselben geschützten Benutzer in mehreren Richtlinien angeben. Unabhängig davon, wie viele Richtlinien für einen Empfänger gelten, beträgt die maximale Anzahl geschützter Benutzer (Absender-E-Mail-Adressen) für jeden einzelnen Empfänger 60. Weitere Informationen zur Richtlinienpriorität und zum Beenden der Richtlinienverarbeitung nach Anwendung der ersten Richtlinie finden Sie unter [Reihenfolge und Rangfolge des E-Mail-Schutzes.](how-policies-and-protections-are-combined.md)
  >
  > - Der Schutz vor Benutzeridentitätswechsel funktioniert nicht, wenn Absender und Empfänger zuvor per E-Mail kommuniziert haben. Wenn Absender und Empfänger nie per E-Mail kommuniziert haben, wird die Nachricht als Identitätswechselversuch identifiziert.

  Standardmäßig sind keine Absender-E-Mail-Adressen für den Identitätswechselschutz in **Benutzern konfiguriert, um sie zu schützen.** Daher werden standardmäßig keine Absender-E-Mail-Adressen vom Identitätswechselschutz abgedeckt, entweder in der Standardrichtlinie oder in benutzerdefinierten Richtlinien.

  Wenn Sie der Liste **"Benutzer"** interne oder externe E-Mail-Adressen zum Schutz hinzufügen, unterliegen Nachrichten von diesen **Absendern Überprüfungen** des Identitätswechselschutzes. Die Nachricht wird auf Identitätswechsel **überprüft, wenn** die Nachricht an einen **Empfänger** gesendet wird, für den die Richtlinie gilt (alle Empfänger für die Standardrichtlinie; **Angewendet auf** Empfänger in benutzerdefinierten Richtlinien). Wenn der Identitätswechsel in der E-Mail-Adresse des Absenders erkannt wird, werden die Identitätswechselschutzaktionen für Benutzer auf die Nachricht angewendet (was mit der Nachricht zu tun ist, ob Sicherheitstipps für imitierte Benutzer angezeigt werden sollen usw.).

- **Zu schützende Domänen hinzufügen:** Verhindert, dass die angegebenen Domänen **in der Domäne des Absenders der Nachricht** imitiert werden. Beispielsweise alle Domänen, die Sie besitzen[(akzeptierte Domänen)](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)oder bestimmte Domänen (Domänen, die Sie besitzen oder Partnerdomänen). Diese Liste der **Absenderdomänen,** die vor Identitätswechsel geschützt sind, unterscheidet sich von der Liste der **Empfänger,** auf die die Richtlinie angewendet wird (alle Empfänger für die Standardrichtlinie; bestimmte Empfänger wie in der Einstellung **"Angewendet auf"** im Abschnitt ["Richtlinieneinstellungen"](#policy-settings) konfiguriert).

  > [!NOTE]
  > Die maximale Anzahl geschützter Domänen, die Sie in allen Antiphishingrichtlinien definieren können, ist 50.

  Standardmäßig sind keine Absenderdomänen für den Identitätswechselschutz in **Domänen konfiguriert, um sie zu schützen.** Daher werden standardmäßig keine Absenderdomänen vom Identitätswechselschutz abgedeckt, weder in der Standardrichtlinie noch in benutzerdefinierten Richtlinien.

  Wenn Sie der Liste **"Domänen"** Domänen zum Schutz hinzufügen, unterliegen Nachrichten von **Absendern in diesen Domänen** identitätswechselschutzprüfungen. Die Nachricht wird auf Identitätswechsel **überprüft, wenn** die Nachricht an einen **Empfänger** gesendet wird, für den die Richtlinie gilt (alle Empfänger für die Standardrichtlinie; **Angewendet auf** Empfänger in benutzerdefinierten Richtlinien). Wenn der Identitätswechsel in der Domäne des Absenders erkannt wird, werden die Identitätswechselschutzaktionen für Domänen auf die Nachricht angewendet (was mit der Nachricht zu tun ist, ob Sicherheitstipps für imitierte Benutzer angezeigt werden sollen usw.).

- **Aktionen:** Wählen Sie die Aktion aus, die bei eingehenden Nachrichten ausgeführt werden soll, die Identitätswechselversuche gegen die geschützten Benutzer und geschützten Domänen in der Richtlinie enthalten. Sie können verschiedene Aktionen für den Identitätswechsel geschützter Benutzer im Vergleich zum Identitätswechsel geschützter Domänen angeben:

  - **Keine Aktion anwenden**

  - **Umleiten der Nachricht an andere E-Mail-Adressen:** Sendet die Nachricht an die angegebenen Empfänger anstelle der vorgesehenen Empfänger.

  - **Verschieben von Nachrichten in die Junk-E-Mail-Ordner des Empfängers:** Die Nachricht wird an das Postfach übermittelt und in den Junk-E-Mail-Ordner verschoben. In Exchange Online wird die Nachricht in den Junk-E-Mail-Ordner verschoben, wenn die Junk-E-Mail-Regel für das Postfach aktiviert ist (sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online Postfächer in Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

  - **Die Nachricht unter Quarantäne** stellen: Sendet die Nachricht an die Quarantäne anstelle der vorgesehenen Empfänger. Informationen zur Quarantäne finden Sie in den folgenden Artikeln:
    - [Quarantäne in Microsoft 365](quarantine-email-messages.md)
    - [Verwalten von isolierten Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Übermitteln Sie die Nachricht, und fügen Sie der Bcc-Zeile weitere Adressen** hinzu: Übermitteln Sie die Nachricht an die gewünschten Empfänger, und übermitteln Sie die Nachricht im Hintergrund an die angegebenen Empfänger.

  - **Löschen Sie die Nachricht, bevor sie zugestellt wird:** Löscht im Hintergrund die gesamte Nachricht, einschließlich aller Anlagen.

- **Sicherheitstipps** für Identitätswechsel aktivieren oder deaktivieren: Aktivieren oder deaktivieren Sie die folgenden Sicherheitstipps für Identitätswechsel, bei denen Meldungen angezeigt werden, bei denen Identitätswechselüberprüfungen nicht erfolgreich sind:
  - **Tipp für imitierte Benutzer anzeigen:** Die Absenderadresse enthält einen geschützten Benutzer.
  - **Tipp für imitierte Domänen anzeigen:** Die Absenderadresse enthält eine geschützte Domäne.
  - **Show tip for unusual characters:** The From address contains unusual character sets (for example, mathematical symbols and text or a mix of uppercase and lowercase letters) in a protected sender or domain.

  > [!IMPORTANT]
  > Auch wenn die Tipps zur Identitätswechselsicherheit deaktiviert sind, **empfehlen wir,** dass Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet) verwenden, um Nachrichten den folgenden Nachrichtenkopf hinzuzufügen:
  >
  > - Headername: **X-MS-Exchange-EnableFirstContactSafetyTip**
  > - Headerwert: **Enable**
  >
  > Ein Sicherheitstipp benachrichtigt Empfänger, wenn sie zum ersten Mal eine Nachricht vom Absender erhalten oder wenn sie nicht oft Nachrichten vom Absender erhalten. Diese Funktion fügt eine zusätzliche Sicherheitsebene vor potenziellen Identitätswechselangriffen hinzu.
  >
  > ![Der Text des Sicherheitstipp für identitätswechselschutz mit mehreren Empfängern.](../../media/safety-tip-first-contact-multiple-recipients.png)

- **Postfachintelligenz:** Aktiviert oder deaktiviert künstliche Intelligenz (KI), die Benutzer-E-Mail-Muster mit ihren häufigen Kontakten bestimmt. Diese Einstellung hilft der KI, zwischen Nachrichten von legitimen und imitierten Absendern zu unterscheiden.

  Beispielsweise ist Sie CEO Ihres Unternehmens glaureano@contoso.com, sodass Sie sie als geschützten Absender in den Benutzern hinzufügen, um die Einstellungen der Richtlinie **zu schützen.** Einige der Empfänger, für die die Richtlinie gilt, müssen jedoch regelmäßig mit einem Anbieter kommunizieren, der auch als "Gabriela Laureano" (glaureano@fabrikam.com) bezeichnet wird. Da diese Empfänger über einen Kommunikationsverlauf mit glaureano@fabrikam.com verfügen, identifiziert die Postfachintelligenz nachrichten von glaureano@fabrikam.com nicht als Identitätswechselversuch der glaureano@contoso.com für diese Empfänger.

  Um häufige Kontakte zu verwenden, die von der Postfachintelligenz gelernt wurden (und die nicht vorhanden sind), um Benutzer vor Identitätswechselangriffen zu schützen, können Sie den Schutz **vor Identitätswechsel** in Mailbox Intelligence aktivieren und die auszuführende Aktion **angeben, wenn** Sie auch **die Postfachintelligenz** aktivieren.

- **Postfachintelligenz basierender Identitätswechselschutz:** Aktivieren Sie diese Einstellung, um die Aktion für Nachrichten für Identitätswechselerkennungen aus Ergebnissen der Postfachintelligenz anzugeben:

  - **Wenden Sie keine Aktion** an: Beachten Sie, dass dieser Wert dasselbe Ergebnis hat wie das Aktivieren der **Postfachintelligenz,** aber das Deaktivieren des **schutzbasierten Identitätswechsels der Postfachintelligenz.**
  - **Umleiten von Nachrichten an andere E-Mail-Adressen**
  - **Verschieben der Nachricht in die Junk-E-Mail-Ordner des Empfängers**
  - **Quarantäne der Nachricht**
  - **Übermitteln der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**
  - **Löschen der Nachricht, bevor sie zugestellt wird**

- **Hinzufügen von vertrauenswürdigen Absendern und Domänen:** Ausnahmen zu den Einstellungen für den Identitätswechselschutz. Nachrichten von den angegebenen Absender- und Absenderdomänen werden von der Richtlinie niemals als identitätswechselbasierte Angriffe klassifiziert. Anders ausgedrückt: Die Aktion für geschützte Absender, geschützte Domänen oder Denkschutz der Postfachintelligenz wird nicht auf diese vertrauenswürdigen Absender oder Absenderdomänen angewendet. Die maximale Beschränkung für diese Listen beträgt ca. 1000 Einträge.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Erweiterte Phishingschwellenwerte in Antiphishingrichtlinien in Microsoft Defender für Office 365

Die folgenden erweiterten Phishingschwellenwerte sind nur in Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügbar. Diese Schwellenwerte steuern die Vertraulichkeit beim Anwenden von Machine Learning-Modellen auf Nachrichten zur Ermittlung eines Phishing-Diktats:

- **1 – Standard:** Dies ist der Standardwert. Der Schweregrad der Aktion, die für die Nachricht ausgeführt wird, hängt vom Grad der Konfidenz ab, dass die Nachricht Phishing ist (niedrig, mittel, hoch oder sehr hoch). Nachrichten, die als Phishing mit sehr hohem Konfidenzgrad identifiziert werden, weisen beispielsweise die schwerwiegendsten Aktionen auf, während Nachrichten, die als Phishing mit einem niedrigen Grad an Konfidenz identifiziert werden, weniger schwerwiegende Aktionen anwenden.

- **2 - Aggressiv:** Nachrichten, die als Phishing mit einem hohen Grad an Konfidenz identifiziert werden, werden so behandelt, als ob sie mit einem sehr hohen Grad an Konfidenz identifiziert würden.

- **3 – Aggressiver:** Nachrichten, die als Phishing mit mittlerem oder hohem Konfidenzgrad identifiziert werden, werden so behandelt, als ob sie mit einem sehr hohen Grad an Konfidenz identifiziert würden.

- **4 – Am aggressivsten:** Nachrichten, die als Phishing mit einem niedrigen, mittleren oder hohen Grad an Konfidenz identifiziert werden, werden so behandelt, als ob sie mit einem sehr hohen Vertrauensgrad identifiziert würden.

Die Wahrscheinlichkeit falsch positiver Ergebnisse (als schlecht markierte gute Nachrichten) erhöht sich, wenn Sie diese Einstellung erhöhen. Informationen zu den empfohlenen Einstellungen finden Sie [unter Antiphishingrichtlinie in Microsoft Defender für Office 365 Einstellungen.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)
