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
ms.openlocfilehash: a97d95ab4d7cf0146ea6d6d008230ee6aa678d80
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166381"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Antiphishingrichtlinien in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Richtlinien zum Konfigurieren von Antiphishingschutzeinstellungen sind in Microsoft 365-Organisationen mit Exchange Online-Postfächern, eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächern und Microsoft Defender für Office 365-Organisationen verfügbar.

Antiphishingrichtlinien in Microsoft Defender für Office 365 sind nur in Organisationen verfügbar, die über Defender für Office 365 verfügen. Zum Beispiel:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5 usw.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender für Office 365 als Add-On](https://products.office.com/exchange/advance-threat-protection)

Die hohen Unterschiede zwischen Antiphishingrichtlinien in EOP und Antiphishingrichtlinien in Microsoft Defender für Office 365 werden in der folgenden Tabelle beschrieben:

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

Im restlichen Teil dieses Artikels werden die Einstellungen beschrieben, die in Antiphishingrichtlinien in EOP und Defender für Office 365 verfügbar sind.

## <a name="policy-settings"></a>Richtlinieneinstellungen

Die folgenden Richtlinieneinstellungen sind in Antiphishingrichtlinien in EOP und Microsoft Defender für Office 365 verfügbar:

- **Name:** Sie können die standardmäßige Antiphishingrichtlinie nicht umbenennen, aber Sie können benutzerdefinierte Richtlinien, die Sie erstellen, benennen und umbenennen.

- **Beschreibung** Sie können der standardmäßigen Antiphishingrichtlinie keine Beschreibung hinzufügen, aber Sie können die Beschreibung für benutzerdefinierte Richtlinien, die Sie erstellen, hinzufügen und ändern.

- **Angewendet auf:** Identifiziert interne Empfänger, für die die Antiphishingrichtlinie gilt. Dieser Wert ist in benutzerdefinierten Richtlinien erforderlich und in der Standardrichtlinie nicht verfügbar (die Standardrichtlinie gilt für alle Empfänger).

  Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

  - **Empfänger:** Ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.
  - **Der Empfänger ist Mitglied von**: Einer oder mehreren Gruppen in Ihrer Organisation.
  - **Die Empfängerdomäne ist:** Eine oder mehrere der konfigurierten akzeptierten Domänen in Microsoft 365.

  - **Außer wenn**: Ausnahmen für die Regel. Die Einstellungen und das Verhalten sind genau wie die Bedingungen:

    - **Empfänger lautet**
    - **Der Empfänger ist Mitglied von**
    - **Die Empfängerdomäne ist**

  > [!NOTE]
  > Die **Einstellung "Angewendet auf"** ist in benutzerdefinierten Antiphishingrichtlinien erforderlich, um die Nachrichtenempfänger zu identifizieren, auf  <u>die die Richtlinie angewendet wird.</u> Antiphishingrichtlinien in Microsoft Defender für Office [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 365 verfügen auch über Identitätswechseleinstellungen, <u></u> in denen Sie einzelne Absender-E-Mail-Adressen oder Absenderdomänen angeben können, die Identitätswechselschutz erhalten, wie weiter unten in diesem Artikel beschrieben.

## <a name="spoof-settings"></a>Spoofeinstellungen

Spoofing ist, wenn die Absenderadresse in einer E-Mail-Nachricht (die Absenderadresse, die in E-Mail-Clients angezeigt wird) nicht mit der Domäne der E-Mail-Quelle übereinstimmen. Weitere Informationen zum Spoofing finden Sie unter [Antis spoofing protection in Microsoft 365](anti-spoofing-protection.md).

Die folgenden Spoofeinstellungen sind in Antiphishingrichtlinien in EOP und Microsoft Defender für Office 365 verfügbar:

- **Antis spoofing protection:** Aktiviert oder deaktiviert den Antis spoofing-Schutz. Es wird empfohlen, die Option aktiviert zu lassen. Sie verwenden die **Spoofing-Intelligence-Richtlinie,** um bestimmte gefälschte interne und externe Absender zu erlauben oder zu blockieren. Weitere Informationen finden Sie unter [Konfigurieren der Spoofintelligenz in Microsoft 365](learn-about-spoof-intelligence.md).

  > [!NOTE]
  >
  > - Antis spoofing protection is enabled by default in the default anti-phishing policy and in any new custom anti-phishing policies that you create.
  >
  > - Sie müssen den Antis spoofingschutz nicht deaktivieren, wenn Ihr #A0 nicht auf Microsoft 365 verweisen kann. stattdessen aktivieren Sie die erweiterte Filterung für Connectors. Anweisungen finden Sie unter ["Erweiterte Filterung für Connectors in Exchange Online".](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)
  >
  > - Durch das Deaktivieren des Antis spoofing-Schutzes wird nur der implizite Spoofingschutz von [zusammengesetzten Authentifizierungsprüfungen](email-validation-and-authentication.md#composite-authentication) deaktiviert. Wenn der Absender explizite [DMARC-Überprüfungen](use-dmarc-to-validate-email.md) nicht besteht, bei denen die Richtlinie auf Quarantäne oder Zurückweisen festgelegt ist, wird die Nachricht weiterhin isoliert oder abgelehnt.

  Für Nachrichten von blockierten gefälschten Absendern können Sie auch die Aktion für die Nachrichten angeben:

  - **Nachricht in Junk-E-Mail-Ordner verschieben:** Dies ist der Standardwert. Die Nachricht wird an das Postfach zugestellt und in den Junk-E-Mail-Ordner verschoben. In Exchange Online wird die Nachricht in den Junk-E-Mail-Ordner verschoben, wenn die Junk-E-Mail-Regel für das Postfach aktiviert ist (sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter ["Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365".](configure-junk-email-settings-on-exo-mailboxes.md)

  - **Nachricht isolieren:** Sendet die Nachricht in Quarantäne anstatt der vorgesehenen Empfänger. Informationen zur Quarantäne finden Sie in den folgenden Artikeln:

    - [Quarantäne in Microsoft 365](quarantine-email-messages.md)
    - [Verwalten von Isolierten Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Suchen und Veröffentlichen von Nachrichten in Quarantäne als Benutzer in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Nicht authentifizierter Absender:** Informationen finden Sie im nächsten Abschnitt.

### <a name="unauthenticated-sender"></a>Nicht authentifizierter Absender

Die Identifizierung nicht authentifizierter Absender ist Teil der [Spoofeinstellungen,](#spoof-settings) die in Antiphishingrichtlinien in EOP und Microsoft Defender für Office 365 verfügbar sind, wie im vorherigen Abschnitt beschrieben.

Die **Einstellung "Nicht authentifizierter Absender"** aktiviert oder deaktiviert die Identifizierung nicht authentifizierter Absender in Outlook. Insbesondere gilt:

- Dem Foto des Absenders wird ein Fragezeichen (?) hinzugefügt, wenn die  Nachricht keine SPF- oder DKIM-Überprüfungen besteht und die Nachricht keine DMARC- oder zusammengesetzte Authentifizierung [besteht.](email-validation-and-authentication.md#composite-authentication) Durch das Deaktivieren der Identifikation nicht authentifizierter Absender wird verhindert, dass das Fragezeichen dem Foto des Absenders hinzugefügt wird.

- Das "Via"-Tag (chris@contoso.com <u>über</u> fabrikam.com) wird hinzugefügt, wenn sich die Domäne in der "Von"-Adresse (der Nachrichtensender, der in E-Mail-Clients angezeigt wird) von der Domäne in der "DKIM"-Signatur oder der **MAIL -FROM-Adresse** unterscheiden. Weitere Informationen zu diesen Adressen finden Sie unter ["Übersicht über E-Mail-Nachrichtenstandards".](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

  Das Deaktivieren der Identifizierung nicht authentifizierter Absender verhindert nicht, dass das "via"-Tag hinzugefügt wird, wenn sich die Domäne in der "Von"-Adresse von der Domäne in der "DKIM"-Signatur oder der MAIL -FROM-Adresse unterscheiden.

Um zu verhindern, dass das Fragezeichen oder das Tag Nachrichten von bestimmten Absendern hinzugefügt werden, haben Sie die folgenden Optionen:

- Zulassen des Spoofings des Absenders in der Spoofing-Intelligence-Richtlinie. Diese Aktion verhindert, dass das "Via"-Tag in Nachrichten des Absenders angezeigt wird, wenn die Identifizierung nicht authentifizierter Absender deaktiviert ist. Anweisungen finden Sie unter [Konfigurieren von Spoofing Intelligence in Microsoft 365.](learn-about-spoof-intelligence.md)

- [Konfigurieren Sie die E-Mail-Authentifizierung](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) für die Absenderdomäne.
  - Für das Fragezeichen auf dem Foto des Absenders sind SPF oder DKIM die wichtigsten.
  - Bestätigen Sie für das "via"-Tag die Domäne in der DKIM-Signatur oder die **MAIL FROM-Adresse,** die der Domäne in der "Von"-Adresse entspricht (oder eine Unterdomäne ist).

Weitere Informationen finden Sie unter ["Identifizieren verdächtiger Nachrichten in Outlook.com und Outlook im Web"](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Exklusive Einstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365

In diesem Abschnitt werden die Richtlinieneinstellungen beschrieben, die nur in Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügbar sind.

> [!NOTE]
> Die standardmäßige Antiphishingrichtlinie in Microsoft Defender für Office 365 bietet [Spoofschutz](set-up-anti-phishing-policies.md#spoof-settings) und Postfachintelligenz für alle Empfänger. Die anderen verfügbaren Identitätswechselschutzfeatures und erweiterten Einstellungen [sind](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) jedoch in der Standardrichtlinie nicht konfiguriert oder aktiviert. [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Um alle Schutzfunktionen zu aktivieren, ändern Sie die standardmäßige Antiphishingrichtlinie, oder erstellen Sie zusätzliche Antiphishingrichtlinien.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Identitätswechseleinstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365

Der Identitätswechsel ist der Ort, an dem der Absender oder die E-Mail-Domäne des Absenders in einer Nachricht einem echten Absender oder einer echten Domäne ähnelt:

- Ein Beispiel für einen Identitätswechsel der Domäne contoso.com ist ćóntoso.com.
- Ein Beispiel für einen Identitätswechsel der Benutzerin michelle@contoso.com ist michele@contoso.com.

Eine imitierte Domäne kann ansonsten als seriös gelten (registrierte Domäne, konfigurierte E-Mail-Authentifizierungseinträge usw.). Der Unterschied besteht darin, dass damit Empfänger getäuscht werden sollen.

Die folgenden Identitätswechseleinstellungen sind nur in Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügbar:

- **Zu schützende Benutzer:** Verhindert, dass die angegebene interne oder externe E-Mail-Adresse als **Nachrichtensender imitiert wird.** Sie erhalten beispielsweise eine E-Mail-Nachricht vom Stellvertretenden President Ihres Unternehmens, in der Sie aufgefordert werden, ihr interne Unternehmensinformationen zu senden. Würdest du es tun? Viele Personen würden die Antwort senden, ohne zu denken.

  Sie können geschützte Benutzer verwenden, um interne und externe Absender-E-Mail-Adressen zum Schutz vor Identitätswechsel hinzuzufügen. Diese Liste der Absender, die vor Benutzerwechsel geschützt sind, ist anders als die Liste der Empfänger, auf die  die Richtlinie angewendet [](#policy-settings) wird (alle Empfänger für die Standardrichtlinie; bestimmte Empfänger, wie in der Einstellung "Angewendet auf" im Abschnitt "Richtlinieneinstellungen" konfiguriert).  

  > [!NOTE]
  >
  > - In jeder Antiphishingrichtlinie können Sie maximal 60 geschützte Benutzer (Absender-E-Mail-Adressen) angeben. Sie können nicht denselben geschützten Benutzer in mehreren Richtlinien angeben. Unabhängig davon, wie viele Richtlinien für einen Empfänger gelten, beträgt die maximale Anzahl geschützter Benutzer (Absender-E-Mail-Adressen) für jeden einzelnen Empfänger also 60. Weitere Informationen zur Richtlinienpriorität und dazu, wie die Richtlinienverarbeitung beendet wird, nachdem die erste Richtlinie angewendet wurde, finden Sie unter "Reihenfolge und [Rangfolge des E-Mail-Schutzes".](how-policies-and-protections-are-combined.md)
  >
  > - Der Schutz vor Identitätswechsel funktioniert nicht, wenn der Absender und der Empfänger zuvor per E-Mail kommuniziert haben. Wenn Absender und Empfänger nie per E-Mail kommuniziert haben, wird die Nachricht als Identitätswechselversuch identifiziert.

  Standardmäßig sind keine Absender-E-Mail-Adressen für identitätswechselschutz in **Benutzer zum Schutz konfiguriert.** Daher werden E-Mail-Adressen von Absendern standardmäßig nicht durch Identitätswechselschutz abgedeckt, weder in der Standardrichtlinie noch in benutzerdefinierten Richtlinien.

  Wenn Sie der Liste "Benutzer" interne oder externe  E-Mail-Adressen zum Schutz hinzufügen, unterliegen Nachrichten von diesen Absendern Überprüfungen zum Identitätswechselschutz.  Die Nachricht wird auf  Identitätswechsel überprüft, wenn  die Nachricht an einen Empfänger gesendet wird, für den die Richtlinie gilt (alle Empfänger für die Standardrichtlinie; **Angewendet auf Empfänger** in benutzerdefinierten Richtlinien). Wenn ein Identitätswechsel in der E-Mail-Adresse des Absenders erkannt wird, werden die Aktionen zum Schutz vor Identitätswechsel für Benutzer auf die Nachricht angewendet (was mit der Nachricht zu tun ist, ob Sicherheitstipps für imitierte Benutzer angezeigt werden sollen usw.).

- **Zu schützende** Domänen: Verhindert, dass die angegebenen Domänen in der Domäne des Absenders der **Nachricht imitiert werden.** Beispielsweise alle Domänen, die Sie besitzen[(](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)akzeptierte Domänen ) oder bestimmte Domänen (Domänen, die Sie besitzen oder Partnerdomänen). Diese Liste  der Absenderdomänen, die vor Identitätswechsel  geschützt sind, ist anders als die Liste der Empfänger, auf die die [](#policy-settings) Richtlinie angewendet wird (alle Empfänger für die Standardrichtlinie; bestimmte Empfänger, wie in der Einstellung "Angewendet auf" im Abschnitt "Richtlinieneinstellungen" konfiguriert). 

  > [!NOTE]
  > Die maximale Anzahl geschützter Domänen, die Sie in allen Antiphishingrichtlinien definieren können, beträgt 50.

  Standardmäßig sind keine Absenderdomänen für identitätswechselschutz in Domänen zum **Schutz konfiguriert.** Daher werden standardmäßig keine Absenderdomänen vom Identitätswechselschutz abgedeckt, weder in der Standardrichtlinie noch in benutzerdefinierten Richtlinien.

  Wenn Sie der Liste **"Domänen"** Domänen zum Schutz hinzufügen, unterliegen Nachrichten von Absendern **in** diesen Domänen Überprüfungen zum Identitätswechselschutz. Die Nachricht wird auf  Identitätswechsel überprüft, wenn  die Nachricht an einen Empfänger gesendet wird, für den die Richtlinie gilt (alle Empfänger für die Standardrichtlinie; **Angewendet auf Empfänger** in benutzerdefinierten Richtlinien). Wenn in der Domäne des Absenders ein Identitätswechsel erkannt wird, werden die Identitätswechselschutzaktionen für Domänen auf die Nachricht angewendet (was mit der Nachricht zu tun ist, ob Sicherheitstipps für imitierte Benutzer angezeigt werden sollen usw.).

- **Aktionen für geschützte Benutzer** oder Domänen: Wählen Sie die Aktion für eingehende Nachrichten aus, die Identitätswechselversuche für die geschützten Benutzer und geschützten Domänen in der Richtlinie enthalten. Sie können unterschiedliche Aktionen für den Identitätswechsel geschützter Benutzer im Vergleich zum Identitätswechsel geschützter Domänen angeben:

  - **Keine Aktion anwenden**

  - **Nachricht an andere E-Mail-Adressen umleiten:** Sendet die Nachricht an die angegebenen Empfänger und nicht an die vorgesehenen Empfänger.

  - **Nachricht in Junk-E-Mail-Ordner** verschieben: Die Nachricht wird an das Postfach zugestellt und in den Junk-E-Mail-Ordner verschoben. In Exchange Online wird die Nachricht in den Junk-E-Mail-Ordner verschoben, wenn die Junk-E-Mail-Regel für das Postfach aktiviert ist (sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter ["Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365".](configure-junk-email-settings-on-exo-mailboxes.md)

    - **Nachricht isolieren:** Sendet die Nachricht in Quarantäne anstatt der vorgesehenen Empfänger. Informationen zur Quarantäne finden Sie in den folgenden Artikeln:

    - [Quarantäne in Microsoft 365](quarantine-email-messages.md)
    - [Verwalten von Isolierten Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Suchen und Veröffentlichen von Nachrichten in Quarantäne als Benutzer in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - Senden Sie die Nachricht, und fügen Sie der **Zeile "Bcc"** weitere Adressen hinzu: Stellen Sie die Nachricht an die vorgesehenen Empfänger zu, und senden Sie die Nachricht im Hintergrund an die angegebenen Empfänger.

  - **Löschen Sie die Nachricht, bevor** sie zugestellt wird: Löscht im Hintergrund die gesamte Nachricht, einschließlich aller Anlagen.

- **Sicherheitstipps:** Aktiviert oder deaktiviert die folgenden Sicherheitstipps für Identitätswechsel, die Meldungen enthalten, bei deren Identitätswechselprüfungen fehler auftreten:

  - **Imitierte Benutzer:** Die "Von"-Adresse enthält einen geschützten Benutzer.
  - **Imitierte Domänen:** Die "Von"-Adresse enthält eine geschützte Domäne.
  - **Ungewöhnliche Zeichen:** Die Absenderadresse enthält ungewöhnliche Zeichensätze (z. B. mathematische Symbole und Text oder eine Kombination aus Groß- und Kleinbuchstaben) in einem geschützten Absender oder einer geschützten Domäne.

  > [!IMPORTANT]
  >
  > Selbst wenn die Identitätswechselsicherheitstipps deaktiviert **sind,** wird empfohlen, eine Nachrichtenflussregel (auch als Transportregel bezeichnet) zu verwenden, um einen Nachrichtenkopf namens  **"X-MS-Exchange-EnableFirstContactSafetyTip"** mit aktiviertem Wert für Nachrichten hinzuzufügen. Ein Sicherheitstipp benachrichtigt Empfänger, wenn sie zum ersten Mal eine Nachricht vom Absender erhalten oder wenn sie nicht oft Nachrichten vom Absender erhalten.
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="Der Text des Sicherheitstipps zum Identitätswechselschutz mit mehreren Empfängern.":::

- **Postfachintelligenz:** Aktiviert oder deaktiviert künstliche Intelligenz (AI), die Benutzer-E-Mail-Muster mit ihren häufigen Kontakten bestimmt. Diese Einstellung hilft der KI, zwischen legitimen und gefälschten E-Mails von diesen Kontakten zu unterscheiden. Die Postfachintelligenz ist nur für Exchange Online-Postfächer verfügbar.

- **Schutz vor postfachintelligenzbasiertem Identitätswechsel:** Aktiviert oder deaktiviert erweiterte Identitätswechselergebnisse basierend auf der individuellen Absenderzuordnung jedes Benutzers. Mit dieser Intelligenz kann Microsoft 365 die Erkennung von Benutzerwechseln anpassen und falsch positive Ergebnisse besser verarbeiten. Wenn ein Benutzerwechsel erkannt wird, können Sie eine bestimmte Aktion definieren, die für die Nachricht verwendet werden soll:

  - **Keine Aktion anwenden**
  - **Umleiten von Nachrichten an andere E-Mail-Adressen**
  - **Nachricht in Junk-E-Mail-Ordner verschieben**
  - **Isolieren der Nachricht**
  - **Benachrichtigung und Hinzufügen weiterer Adressen zur Zeile "Bcc"**
  - **Löschen der Nachricht, bevor sie zugestellt wird**

- **Vertrauenswürdige Absender und Domänen:** Ausnahmen für die Identitätswechselschutzeinstellungen. Nachrichten von den angegebenen Absender- und Absenderdomänen werden von der Richtlinie nie als identitätswechselbasierte Angriffe klassifiziert. Anders ausgedrückt: Die Aktion für geschützte Absender, geschützte Domänen oder Postfachintelligenzschutz wird nicht auf diese vertrauenswürdigen Absender oder Absenderdomänen angewendet. Der Höchstwert für diese Listen beträgt ca. 1.000 Einträge.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Erweiterte Phishingschwellenwerte in Antiphishingrichtlinien in Microsoft Defender für Office 365

Die folgenden erweiterten Phishingschwellenwerte sind nur in Antiphishingrichtlinien in Microsoft Defender für Office 365 verfügbar. Diese Schwellenwerte steuern die Vertraulichkeit für die Anwendung von Machine Learning-Modellen auf Nachrichten zur Ermittlung einer Phishing-Beurteilung:

- **1 – Standard:** Dies ist der Standardwert. Der Schweregrad der Aktion, die für die Nachricht ergriffen wird, hängt vom Grad der Konfidenz ab, mit der die Nachricht phishing ist (niedrig, mittel, hoch oder sehr hoch). Nachrichten, die als Phishing mit einem sehr hohen Grad an Vertrauen identifiziert werden, werden beispielsweise am stärksten angewendet, während Nachrichten, die als Phishing mit geringem Vertrauensgrad identifiziert werden, weniger schwerwiegende Aktionen angewendet werden.

- **2 – Aggressiv:** Nachrichten, die mit einem hohen Grad an Vertrauen als Phishing identifiziert werden, werden so behandelt, als wären sie mit einem sehr hohen Grad an Vertrauen identifiziert worden.

- **3 – Aggressiver:** Nachrichten, die als Phishing mit mittlerem oder hohem Vertrauensgrad identifiziert werden, werden so behandelt, als wären sie mit einem sehr hohen Grad an Vertrauen identifiziert worden.

- **4 – Am aggressivsten:** Nachrichten, die als Phishing mit niedrigem, mittlerem oder hohem Vertrauensgrad identifiziert werden, werden so behandelt, als wären sie mit einem sehr hohen Grad an Vertrauen identifiziert worden.

Die Wahrscheinlichkeit falsch positiver Ergebnisse (gute Nachrichten sind als schlecht gekennzeichnet) steigt, wenn Sie diese Einstellung erhöhen. Informationen zu den empfohlenen Einstellungen finden Sie unter ["Antiphishingrichtlinie" in den Microsoft Defender für Office 365-Einstellungen.](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)
