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
ms.openlocfilehash: 44472d49936f400ee16227f3f29141738ad28daa
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51571020"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Antiphishingrichtlinien in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Richtlinien zum Konfigurieren von Antiphishingschutzeinstellungen sind in Microsoft 365-Organisationen mit Exchange Online-Postfächern, eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächern und Microsoft Defender für Office 365-Organisationen verfügbar.

Antiphishingrichtlinien in Microsoft Defender für Office 365 sind nur in Organisationen mit Defender for Office 365 verfügbar. Beispiel:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5 usw.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender für Office 365 als Add-On](https://products.office.com/exchange/advance-threat-protection)

Die großen Unterschiede zwischen Antiphishingrichtlinien in EOP und Antiphishingrichtlinien in Microsoft Defender für Office 365 werden in der folgenden Tabelle beschrieben:

****

|Feature|Antiphishingrichtlinien in EOP|Antiphishingrichtlinien in Microsoft Defender für Office 365|
|---|:---:|:---:|
|Automatisch erstellte Standardrichtlinie|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|Erstellen Sie benutzerdefinierte Richtlinien|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|Richtlinieneinstellungen<sup>\*</sup>|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|Identitätswechseleinstellungen||![Häkchen](../../media/checkmark.png)|
|Spoofeinstellungen|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|Erweiterte Phishingschwellenwerte||![Häkchen](../../media/checkmark.png)|
|

<sup>\*</sup> In der Standardrichtlinie sind der Richtlinienname und die Beschreibung schreibgeschützt (die Beschreibung ist leer), und Sie können nicht angeben, auf wen die Richtlinie angewendet wird (die Standardrichtlinie gilt für alle Empfänger).

Informationen zum Konfigurieren von Antiphishingrichtlinien finden Sie in den folgenden Artikeln:

- [Konfigurieren von Anti-Phishing-Richtlinien in EOP](configure-anti-phishing-policies-eop.md)

- [Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365](configure-atp-anti-phishing-policies.md)

Der Rest dieses Artikels beschreibt die Einstellungen, die in Antiphishingrichtlinien in EOP und Defender für Office 365 verfügbar sind.

## <a name="policy-settings"></a>Richtlinieneinstellungen

Die folgenden Richtlinieneinstellungen sind in Antiphishingrichtlinien in EOP und Microsoft Defender für Office 365 verfügbar:

- **Name**: Sie können die Standardmäßige Antiphishingrichtlinie nicht umbenennen. Nachdem Sie eine benutzerdefinierte Antiphishingrichtlinie erstellt haben, können Sie die Richtlinie im Security & Compliance Center nicht umbenennen.

- **Beschreibung** Sie können der Standardmäßigen Antiphishingrichtlinie keine Beschreibung hinzufügen, aber Sie können die Beschreibung für benutzerdefinierte Richtlinien, die Sie erstellen, hinzufügen und ändern.

- **Applied to**: Identifies internal recipients that the anti-phishing policy applies to. Dieser Wert ist in benutzerdefinierten Richtlinien erforderlich und in der Standardrichtlinie nicht verfügbar (die Standardrichtlinie gilt für alle Empfänger).

  Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

  - **Empfänger ist**: Ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.
  - **Recipient ist Mitglied von**: Einer oder mehreren Gruppen in Ihrer Organisation.
  - **Die Empfängerdomäne ist**: Eine oder mehrere der konfigurierten akzeptierten Domänen in Microsoft 365.

  - **Außer wenn**: Ausnahmen für die Regel. Die Einstellungen und das Verhalten sind genau wie die Bedingungen:

    - **Empfänger lautet**
    - **Recipient ist Mitglied von**
    - **Die Empfängerdomäne ist**

  > [!NOTE]
  > Die **Einstellung Angewendet auf** ist in benutzerdefinierten Antiphishingrichtlinien erforderlich, um die Nachrichtenempfänger zu identifizieren, auf die die Richtlinie angewendet  <u>wird.</u> Antiphishingrichtlinien in Microsoft Defender für Office [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 365 verfügen auch über Identitätswechseleinstellungen, <u></u> in denen Sie einzelne Absender-E-Mail-Adressen oder Absenderdomänen angeben können, die Identitätswechselschutz erhalten, wie weiter unten in diesem Artikel beschrieben.

## <a name="spoof-settings"></a>Spoofeinstellungen

Spoofing ist, wenn die Absenderadresse in einer E-Mail-Nachricht (die Absenderadresse, die in E-Mail-Clients angezeigt wird) nicht mit der Domäne der E-Mail-Quelle übereinstimmen. Weitere Informationen zum Spoofing finden Sie unter [Anti-Spoofing Protection in Microsoft 365](anti-spoofing-protection.md).

Die folgenden Spoofeinstellungen sind in Antiphishingrichtlinien in EOP und Microsoft Defender für Office 365 verfügbar:

- **Anti-Spoofing-Schutz:** Aktiviert oder deaktiviert den Schutz vor Spoofing. Es wird empfohlen, die Option aktiviert zu lassen. Sie verwenden die **Spoof Intelligence-Richtlinie,** um bestimmte spoofierte interne und externe Absender zu erlauben oder zu blockieren. Weitere Informationen finden Sie unter [Konfigurieren der Spoofintelligenz in Microsoft 365](learn-about-spoof-intelligence.md).

  > [!NOTE]
  >
  > - Der Antis spoofing-Schutz ist standardmäßig in der Standardmäßigen Antiphishingrichtlinie und in allen neuen benutzerdefinierten Antiphishingrichtlinien aktiviert, die Sie erstellen.
  >
  > - Sie müssen den Schutz vor Spoofing nicht deaktivieren, wenn Ihr #A0 nicht auf Microsoft 365 verweisen soll. Stattdessen aktivieren Sie erweiterte Filterung für Connectors. Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).
  >
  > - Durch deaktivieren des Antis spoofing-Schutzes wird nur impliziter Spoofingschutz von [zusammengesetzten Authentifizierungsüberprüfungen](email-validation-and-authentication.md#composite-authentication) deaktiviert. Wenn der Absender einen expliziten [DMARC](use-dmarc-to-validate-email.md) nicht überprüft, wo die Richtlinie auf Quarantäne oder Ablehnung festgelegt ist, wird die Nachricht weiterhin isoliert oder abgelehnt.

  Für Nachrichten von blockierten spoofierten Absendern können Sie auch die Aktion für die Nachrichten angeben:

  - **Nachricht in Junk-E-Mail-Ordner verschieben:** Dies ist der Standardwert. Die Nachricht wird an das Postfach zugestellt und in den Junk-E-Mail-Ordner verschoben. In Exchange Online wird die Nachricht in den Junk-E-Mail-Ordner verschoben, wenn die Junk-E-Mail-Regel für das Postfach aktiviert ist (standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Nachricht unter Quarantäne stellen:** Sendet die Nachricht an die Quarantäne anstatt an die beabsichtigten Empfänger. Informationen zur Quarantäne finden Sie in den folgenden Artikeln:

    - [Quarantäne in Microsoft 365](quarantine-email-messages.md)
    - [Verwalten isolierter Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Suchen und Veröffentlichen isolierter Nachrichten als Benutzer in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Nicht authentifizierter Absender:** Weitere Informationen finden Sie im nächsten Abschnitt.

### <a name="unauthenticated-sender"></a>Nicht authentifizierter Absender

Die Identifizierung nicht authentifizierter Absender ist Teil der [Spoofeinstellungen,](#spoof-settings) die in Antiphishingrichtlinien in EOP und Microsoft Defender für Office 365 verfügbar sind, wie im vorherigen Abschnitt beschrieben.

Die **Einstellung Nicht authentifizierter Absender** aktiviert oder deaktiviert die identifikation nicht authentifizierter Absender in Outlook. Insbesondere gilt:

- Dem Foto des Absenders wird ein Fragezeichen (?) hinzugefügt, wenn die  Nachricht keine SPF- oder DKIM-Prüfungen besteht und die Nachricht keine DMARC- oder zusammengesetzte Authentifizierung [besteht.](email-validation-and-authentication.md#composite-authentication) Das Deaktivieren der nicht authentifizierten Absenderidentifikation verhindert, dass das Fragezeichen dem Foto des Absenders hinzugefügt wird.

- Das via-Tag (chris@contoso.com <u>über</u> fabrikam.com) wird hinzugefügt, wenn sich die Domäne in der Absenderadresse (der Nachrichtensender, der in E-Mail-Clients angezeigt wird) von der Domäne in der DKIM-Signatur oder der **MAIL FROM-Adresse** ab unterscheiden. Weitere Informationen zu diesen Adressen finden Sie unter [Eine Übersicht über E-Mail-Nachrichtenstandards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

  Das Deaktivieren der nicht authentifizierten Absenderidentifikation verhindert nicht, dass das via-Tag hinzugefügt wird, wenn sich die Domäne in der Absenderadresse von der Domäne in der DKIM-Signatur oder der MAIL FROM-Adresse unterscheiden.

Um zu verhindern, dass Nachrichten von bestimmten Absendern das Fragezeichen oder das Tag hinzugefügt wird, haben Sie die folgenden Optionen:

- Zulassen, dass der Absender in der Spoof Intelligence-Richtlinie spooft. Mit dieser Aktion wird verhindert, dass das via-Tag in Nachrichten des Absenders angezeigt wird, wenn die Identifikation nicht authentifizierter Absender deaktiviert ist. Anweisungen finden Sie unter [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

- [Konfigurieren der E-Mail-Authentifizierung](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) für die Absenderdomäne.
  - Für das Fragezeichen auf dem Foto des Absenders sind SPF oder DKIM die wichtigsten.
  - Bestätigen Sie für das via-Tag die Domäne in der DKIM-Signatur oder die **MAIL FROM-Adresse** entspricht (oder ist eine Unterdomäne von) der Domäne in der Von-Adresse.

Weitere Informationen finden Sie unter Identifizieren verdächtiger [Nachrichten in Outlook.com und Outlook im Web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Exklusive Einstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365

In diesem Abschnitt werden die Richtlinieneinstellungen beschrieben, die nur in Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügbar sind.

> [!NOTE]
> Die standardmäßige Antiphishingrichtlinie in Microsoft Defender für Office 365 bietet [Spoofschutz](set-up-anti-phishing-policies.md#spoof-settings) und Postfachintelligenz für alle Empfänger. Die anderen verfügbaren [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Identitätswechselschutzfeatures und erweiterten Einstellungen sind jedoch in der Standardrichtlinie nicht konfiguriert oder aktiviert. [](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Um alle Schutzfunktionen zu aktivieren, ändern Sie die Standardmäßige Antiphishingrichtlinie, oder erstellen Sie zusätzliche Antiphishingrichtlinien.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Identitätswechseleinstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365

Der Identitätswechsel ist der Ort, an dem der Absender oder die E-Mail-Domäne des Absenders in einer Nachricht einem tatsächlichen Absender oder einer echten Domäne ähnelt:

- Ein Beispiel für einen Identitätswechsel der Domäne contoso.com ist ćóntoso.com.
- Ein Beispiel für einen Identitätswechsel der Benutzerin michelle@contoso.com ist michele@contoso.com.

Eine imitierte Domäne kann ansonsten als seriös gelten (registrierte Domäne, konfigurierte E-Mail-Authentifizierungseinträge usw.). Der Unterschied besteht darin, dass damit Empfänger getäuscht werden sollen.

Die folgenden Identitätswechseleinstellungen sind nur in Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügbar:

- **Zu schützende Benutzer:** Verhindert, dass die angegebenen internen oder externen E-Mail-Adressen als **Nachrichtensender imitiert werden.** Sie erhalten beispielsweise eine E-Mail-Nachricht vom Vice President Ihres Unternehmens, in der Sie aufgefordert werden, ihr einige interne Unternehmensinformationen zu senden. Würdest du es tun? Viele Personen würden die Antwort senden, ohne darüber nachzudenken.

  Sie können geschützte Benutzer verwenden, um interne und externe Absender-E-Mail-Adressen hinzuzufügen, um vor Identitätswechseln zu schützen. Diese Liste der Absender, die vor Benutzerwechsel geschützt sind, ist anders als die Liste der Empfänger, auf die  die Richtlinie angewendet [](#policy-settings) wird (alle Empfänger für die Standardrichtlinie; bestimmte Empfänger, wie in der Einstellung Angewendet auf im Abschnitt Richtlinieneinstellungen konfiguriert).  

  > [!NOTE]
  >
  > - In jeder Antiphishingrichtlinie können Sie maximal 60 geschützte Benutzer (Absender-E-Mail-Adressen) angeben. Sie können denselben geschützten Benutzer nicht in mehreren Richtlinien angeben. Unabhängig davon, wie viele Richtlinien für einen Empfänger gelten, beträgt die maximale Anzahl geschützter Benutzer (Absender-E-Mail-Adressen) für jeden einzelnen Empfänger also 60. Weitere Informationen zur Richtlinienpriorität und dazu, wie die Richtlinienverarbeitung nach der Anwendung der ersten Richtlinie beendet wird, finden Sie unter [Reihenfolge und Rangfolge des E-Mail-Schutzes.](how-policies-and-protections-are-combined.md)
  >
  > - Benutzerwechselschutz funktioniert nicht, wenn Absender und Empfänger zuvor per E-Mail kommuniziert haben. Wenn Absender und Empfänger nie per E-Mail kommuniziert haben, wird die Nachricht als Identitätswechselversuch identifiziert.

  Standardmäßig sind keine Absender-E-Mail-Adressen für den Identitätswechselschutz in **Benutzer zum Schützen konfiguriert.** Daher werden standardmäßig keine Absender-E-Mail-Adressen vom Identitätswechselschutz abgedeckt, weder in der Standardrichtlinie noch in benutzerdefinierten Richtlinien.

  Wenn Sie der Liste Benutzer  interne oder externe E-Mail-Adressen hinzufügen, um die Liste zu schützen, unterliegen Nachrichten von diesen Absendern Identitätswechselschutzprüfungen.  Die Nachricht wird auf  Identitätswechsel überprüft, wenn  die Nachricht an einen Empfänger gesendet wird, für den die Richtlinie gilt (alle Empfänger für die Standardrichtlinie; **Angewendet auf Empfänger** in benutzerdefinierten Richtlinien). Wenn der Identitätswechsel in der E-Mail-Adresse des Absenders erkannt wird, werden die Aktionen zum Identitätswechselschutz für Benutzer auf die Nachricht angewendet (was mit der Nachricht zu tun ist, ob Sicherheitstipps für imitierte Benutzer angezeigt werden sollen usw.).

- **Zu schützende** Domänen: Verhindert, dass die angegebenen Domänen in der Domäne des Nachrichtensenders **als identitätswechselt werden.** Beispielsweise alle Domänen, die Sie besitzen ([akzeptierte](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)Domänen ) oder bestimmte Domänen (Domänen, die Sie besitzen oder Partnerdomänen). Diese Liste  der Absenderdomänen, die vor Identitätswechsel  geschützt sind, ist anders als die Liste der Empfänger, auf die die [](#policy-settings) Richtlinie angewendet wird (alle Empfänger für die Standardrichtlinie; bestimmte Empfänger, wie in der Einstellung Angewendet auf im Abschnitt Richtlinieneinstellungen konfiguriert). 

  > [!NOTE]
  > Die maximale Anzahl geschützter Domänen, die Sie in allen Antiphishingrichtlinien definieren können, beträgt 50.

  Standardmäßig sind keine Absenderdomänen für den Identitätswechselschutz in Domänen zum **Schützen konfiguriert.** Daher werden standardmäßig keine Absenderdomänen vom Identitätswechselschutz abgedeckt, weder in der Standardrichtlinie noch in benutzerdefinierten Richtlinien.

  Wenn Sie der  Liste Domänen zum Schutz domänen hinzufügen, unterliegen Nachrichten von **Absendern in** diesen Domänen Identitätswechselschutzprüfungen. Die Nachricht wird auf  Identitätswechsel überprüft, wenn  die Nachricht an einen Empfänger gesendet wird, für den die Richtlinie gilt (alle Empfänger für die Standardrichtlinie; **Angewendet auf Empfänger** in benutzerdefinierten Richtlinien). Wenn der Identitätswechsel in der Domäne des Absenders erkannt wird, werden die Identitätswechselschutzaktionen für Domänen auf die Nachricht angewendet (was mit der Nachricht zu tun ist, ob Sicherheitstipps für imitierte Benutzer angezeigt werden sollen usw.).

- **Aktionen für geschützte Benutzer** oder Domänen: Wählen Sie die Aktion für eingehende Nachrichten aus, die Identitätswechselversuche gegen die geschützten Benutzer und geschützten Domänen in der Richtlinie enthalten. Sie können verschiedene Aktionen für den Identitätswechsel geschützter Benutzer und den Identitätswechsel geschützter Domänen angeben:

  - **Keine Aktion anwenden**

  - **Nachricht an andere E-Mail-Adressen umleiten:** Sendet die Nachricht an die angegebenen Empfänger anstatt an die beabsichtigten Empfänger.

  - **Nachricht in Junk-E-Mail-Ordner** verschieben: Die Nachricht wird an das Postfach zugestellt und in den Junk-E-Mail-Ordner verschoben. In Exchange Online wird die Nachricht in den Junk-E-Mail-Ordner verschoben, wenn die Junk-E-Mail-Regel für das Postfach aktiviert ist (standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

    - **Nachricht unter Quarantäne stellen:** Sendet die Nachricht an die Quarantäne anstatt an die beabsichtigten Empfänger. Informationen zur Quarantäne finden Sie in den folgenden Artikeln:

    - [Quarantäne in Microsoft 365](quarantine-email-messages.md)
    - [Verwalten isolierter Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Suchen und Veröffentlichen isolierter Nachrichten als Benutzer in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Senden Sie die Nachricht, und fügen** Sie der Zeile Bcc weitere Adressen hinzu: Senden Sie die Nachricht an die beabsichtigten Empfänger, und senden Sie die Nachricht automatisch an die angegebenen Empfänger.

  - **Löschen Sie die Nachricht, bevor sie zugestellt wird:** Löscht automatisch die gesamte Nachricht, einschließlich aller Anlagen.

- **Sicherheitstipps:** Aktiviert oder deaktiviert die folgenden Identitätswechselsicherheitstipps, die Nachrichten angezeigt werden, bei deren Identitätswechselprüfungen fehlschlagen:

  - **Imitierte Benutzer:** Die From-Adresse enthält einen geschützten Benutzer.
  - **Identitätswechseldomänen:** Die From-Adresse enthält eine geschützte Domäne.
  - **Ungewöhnliche Zeichen:** Die From-Adresse enthält ungewöhnliche Zeichensätze (z. B. mathematische Symbole und Text oder eine Kombination aus Groß- und Kleinbuchstaben) in einem geschützten Absender oder einer geschützten Domäne.

  > [!IMPORTANT]
  >
  > Selbst wenn die Identitätswechselsicherheitstipps deaktiviert **sind,** wird empfohlen, eine Nachrichtenflussregel (auch als Transportregel bezeichnet) zu verwenden, um einen Nachrichtenkopf mit dem Namen **X-MS-Exchange-EnableFirstContactSafetyTip** mit **wertaktiviertem** Wert für Nachrichten hinzuzufügen. Ein Sicherheitstipp benachrichtigt Empfänger, wenn sie zum ersten Mal eine Nachricht vom Absender erhalten oder wenn sie nicht häufig Nachrichten vom Absender erhalten. Diese Funktion bietet zusätzlichen Sicherheitsschutz vor potenziellen Identitätswechselangriffen.
  >
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="Der Text der Sicherheitstipps für den Identitätswechselschutz mit mehreren Empfängern.":::

- **Postfachintelligenz:** Aktiviert oder deaktiviert künstliche Intelligenz (KI), die Benutzer-E-Mail-Muster mit ihren häufigen Kontakten bestimmt. Diese Einstellung hilft der KI, zwischen Nachrichten von legitimen und identitätswechselten Absendern zu unterscheiden.

  Beispielsweise ist Gabriela Laureano (glaureano@contoso.com) die CEO Ihres Unternehmens, daher fügen Sie sie  als geschützten Absender in die Benutzer ein, um die Einstellungen der Richtlinie zu schützen. Einige der Empfänger, für die die Richtlinie gilt, kommunizieren jedoch regelmäßig mit einem Anbieter, der auch "Gabriela Laureano" (glaureano@fabrikam.com) heißt. Da diese Empfänger über einen Kommunikationsverlauf mit glaureano@fabrikam.com verfügen, identifiziert die Postfachintelligenz Nachrichten aus glaureano@fabrikam.com nicht als Identitätswechselversuch glaureano@contoso.com Empfängern.

  Um häufige Kontakte zu verwenden, die von der Postfachintelligenz (und deren  Fehlen) gelernt wurden, um Benutzer vor  Identitätswechselangriffen zu schützen, können Sie den Identitätswechselschutz für Postfachintelligenz aktivieren und die zu ergreifende Aktion angeben, wenn Sie auch **Mailbox Intelligence aktivieren.**

- **Postfachintelligenz-basierter Identitätswechselschutz:** Aktivieren Sie diese Einstellung, um die Aktion für Nachrichten für Identitätswechselerkennungen aus Ergebnissen der Postfachintelligenz anzugeben:

  - **Keine Aktion** anwenden: Beachten Sie, dass dieser Wert dasselbe Ergebnis hat wie das Aktivieren der Postfachintelligenz, aber das Deaktivieren des Identitätswechselschutzes für  Postfachintelligenz. 
  - **Umleiten von Nachrichten an andere E-Mail-Adressen**
  - **Nachricht in Junk-E-Mail-Ordner verschieben**
  - **Isolieren der Nachricht**
  - **Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**
  - **Löschen der Nachricht, bevor sie zugestellt wird**

- **Vertrauenswürdige Absender und Domänen:** Ausnahmen von den Identitätswechselschutzeinstellungen. Nachrichten von den angegebenen Absender- und Absenderdomänen werden von der Richtlinie nie als identitätswechselbasierte Angriffe klassifiziert. Anders ausgedrückt: Die Aktion für geschützte Absender, geschützte Domänen oder Postfachintelligenzschutz wird nicht auf diese vertrauenswürdigen Absender oder Absenderdomänen angewendet. Die maximale Grenze für diese Listen beträgt ca. 1.000 Einträge.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Erweiterte Phishingschwellenwerte in Antiphishingrichtlinien in Microsoft Defender für Office 365

Die folgenden erweiterten Phishingschwellenwerte sind nur in Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügbar. Diese Schwellenwerte steuern die Vertraulichkeit für das Anwenden von Machine Learning-Modellen auf Nachrichten zum Bestimmen eines Phishing-Urteils:

- **1 – Standard**: Dies ist der Standardwert. Der Schweregrad der Aktion, die für die Nachricht ergriffen wird, hängt vom Grad der Sicherheit ab, dass es sich bei der Nachricht um Phishing handelt (niedrig, mittel, hoch oder sehr hoch). Nachrichten, die mit einem sehr hohen Grad an Vertrauen als Phishing identifiziert werden, haben beispielsweise die schwersten Aktionen, während Nachrichten, die als Phishing mit einem niedrigen Grad an Vertrauen identifiziert werden, weniger schwerwiegende Aktionen angewendet werden.

- **2 – Aggressiv:** Nachrichten, die mit einem hohen Grad an Vertrauen als Phishing identifiziert werden, werden so behandelt, als würden sie mit einem sehr hohen Grad an Vertrauen identifiziert.

- **3 – Aggressiver:** Nachrichten, die als Phishing mit mittlerem oder hohem Grad an Vertrauen identifiziert werden, werden so behandelt, als würden sie mit einem sehr hohen Grad an Vertrauen identifiziert.

- **4 –** Am aggressivsten: Nachrichten, die als Phishing mit einem niedrigen, mittleren oder hohen Grad an Vertrauen identifiziert werden, werden so behandelt, als würden sie mit einem sehr hohen Grad an Vertrauen identifiziert.

Die Wahrscheinlichkeit falsch positiver Ergebnisse (gute Nachrichten, die als schlecht gekennzeichnet sind) erhöht sich, wenn Sie diese Einstellung erhöhen. Informationen zu den empfohlenen Einstellungen finden Sie unter [Antiphishingrichtlinie in Microsoft Defender für Office 365-Einstellungen](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).
