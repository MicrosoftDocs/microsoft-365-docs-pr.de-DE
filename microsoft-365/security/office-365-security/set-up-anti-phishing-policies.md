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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die Anti-Phishing-Richtlinien informieren, die in Exchange Online Protection (EoP) und Office 365 Advanced Threat Protection (Office 365 ATP) zur Verfügung stehen.
ms.openlocfilehash: 498b6e27b3fca66e388eaa27ba7895056ef7f0fc
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326937"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Anti-Phishing-Richtlinien in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Richtlinien zum Konfigurieren von Einstellungen zum Schutz vor Phishing stehen in Microsoft 365-Organisationen mit Exchange Online-Postfächern, eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächern und Office 365 Advanced Threat Protection (Office 365 ATP)-Organisationen zur Verfügung.

ATP-Anti-Phishing-Richtlinien sind nur in Organisationen verfügbar, die Office 365 ATP haben. Beispiel:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Office 365 ATP als Add-on](https://products.office.com/exchange/advance-threat-protection)

Alle anderen Organisationen verfügen über Anti-Phishing-Richtlinien.

In der folgenden Tabelle werden die allgemeinen Unterschiede zwischen Anti-Phishing-Richtlinien und ATP-AntiPhishing-Richtlinien beschrieben:

****

|Feature|Antiphishing-Richtlinien|Richtlinien für ATP-Anti-Phishing|
|---|:---:|:---:|
|Automatisch erstellte Standardrichtlinie|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Erstellen benutzerdefinierter Richtlinien|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Richtlinieneinstellungen<sup>\*</sup>|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Einstellungen für Identitätswechsel||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Spoof-Einstellungen|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Erweiterte Phishing-Schwellenwerte||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup> In der Standardrichtlinie sind der Richtlinienname und die Beschreibung schreibgeschützt (die Beschreibung ist leer), und Sie können nicht angeben, für wen die Richtlinie gilt (die Standardrichtlinie gilt für alle Empfänger).

Informationen zum Konfigurieren von Anti-Phishing-Richtlinien finden Sie in den folgenden Artikeln:

- [Konfigurieren von Anti-Phishing-Richtlinien in EoP](configure-anti-phishing-policies-eop.md)

- [Konfigurieren von Richtlinien für die ATP-Anti-Phishing in Microsoft 365](configure-atp-anti-phishing-policies.md)

Im Rest dieses Artikels werden die Einstellungen beschrieben, die in Anti-Phishing-Richtlinien und Richtlinien für die ATP-Anti-Phishing verfügbar sind.

## <a name="policy-settings"></a>Richtlinieneinstellungen

Die folgenden Richtlinieneinstellungen sind in Anti-Phishing-Richtlinien und Richtlinien für die ATP-Anti-Phishing verfügbar:

- **Name**: Sie können die standardmäßige Anti-Phishing-Richtlinie nicht umbenennen, aber Sie können benutzerdefinierte Richtlinien benennen und umbenennen, die Sie erstellen.

- **Beschreibung** Sie können keine Beschreibung zur Standard-Anti-Phishing-Richtlinie hinzufügen, aber Sie können die Beschreibung für benutzerdefinierte Richtlinien, die Sie erstellen, hinzufügen und ändern.

- **Angewendet auf**: identifiziert interne Empfänger, auf die die AntiPhishing-Richtlinie angewendet wird. Dieser Wert ist in benutzerdefinierten Richtlinien erforderlich und in der Standardrichtlinie nicht verfügbar (die Standardrichtlinie gilt für alle Empfänger).

  Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

  - **Empfänger ist**: ein oder mehrere Postfächer, e-Mail-Benutzer oder e-Mail-Kontakte in Ihrer Organisation.
  - **Der Empfänger ist Mitglied von**: eine oder mehrere Gruppen in Ihrer Organisation.
  - **Die Empfängerdomäne ist**: eine oder mehrere der konfigurierten akzeptierten Domänen in Microsoft 365.

  - **Ausnahme**: Ausnahmen für die Regel. Die Einstellungen und das Verhalten sind genau wie die Bedingungen:

    - **Empfänger lautet**
    - **Der Empfänger ist Mitglied von**
    - **Die Empfängerdomäne ist**

  > [!NOTE]
  > Die Einstellung **angewendet auf** ist in benutzerdefinierten Richtlinien zum Schutz vor Phishing erforderlich, um die Nachrichten **Empfänger** zu identifizieren <u>, auf die die Richtlinie angewendet</u>wird. Für ATP-Anti-Phishing-Richtlinien gibt es auch Einstellungen für den [Identitätswechsel](#impersonation-settings-in-atp-anti-phishing-policies) , in denen Sie einzelne Absender-e-Mail-Adressen oder Absenderdomänen angeben können <u>, die den Identitätswechsel Schutz erhalten,</u> wie weiter unten in diesem Thema beschrieben wird.

## <a name="spoof-settings"></a>Spoof-Einstellungen

Spoofing ist, wenn die von-Adresse in einer e-Mail-Nachricht (die Absenderadresse, die in e-Mail-Clients angezeigt wird) nicht mit der Domäne der e-Mail-Quelle übereinstimmt. Weitere Informationen zur Spoofing finden Sie unter [Anti-Spoofing Protection in Microsoft 365](anti-spoofing-protection.md).

Die folgenden spoofeinstellungen stehen unter Anti-Phishing-Richtlinien und ATP-AntiPhishing-Richtlinien zur Verfügung:

- **Schutz gegen Spoofing**: aktiviert oder deaktiviert den Schutz vor Spoofing. Es wird empfohlen, die Option aktiviert zu lassen. Verwenden Sie die **Spoof Intelligence-Richtlinie** , um bestimmte gefälschte interne und externe Absender zuzulassen oder zu blockieren. Weitere Informationen finden Sie unter [Konfigurieren der Spoofintelligenz in Microsoft 365](learn-about-spoof-intelligence.md).

  > [!NOTE]
  > Spoofeinstellungen sind standardmäßig in der standardmäßigen Anti-Phishing-Richtlinie in EoP, der standardmäßigen ATP-antiphishingpolitik und in neuen benutzerdefinierten Anti-Phishing-Richtlinien oder von Ihnen erstellten Richtlinien für das Anti-Phishing-Konzept von ATP aktiviert. <br/><br/> Sie müssen den Schutz vor Spoofing nicht deaktivieren, wenn Ihr MX-Eintrag nicht auf Microsoft 365 verweist; Stattdessen aktivieren Sie die erweiterte Filterung für Connectors. Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

  Für Nachrichten von blockierten gefälschten Absendern können Sie auch die Aktion angeben, die für die Nachrichten ausgeführt werden soll:

  - **Nachricht in den Junk-e-Mail-Ordner umlegen**: Dies ist der Standardwert. Die Nachricht wird an das Postfach übermittelt und in den Junk-e-Mail-Ordner verschoben. In Exchange Online wird die Nachricht in den Junk-e-Mail-Ordner verschoben, wenn die Junk-e-Mail-Regel für das Postfach aktiviert ist (Sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-e-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Nachricht in Quarantäne verschieben**: sendet die Nachricht an die Quarantäne statt an die vorgesehenen Empfänger. Weitere Informationen zur Quarantäne finden Sie in den folgenden Artikeln:

    - [Quarantäne in Microsoft 365](quarantine-email-messages.md)
    - [Verwalten von isolierten Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- Nicht **authentifizierter Absender**: Informationen finden Sie im nächsten Abschnitt.

### <a name="unauthenticated-sender"></a>Nicht authentifizierter Absender

Die nicht authentifizierte Absender Identifikation ist Teil der [spoofeinstellungen](#spoof-settings) , die in Anti-Phishing-Richtlinien und ATP-AntiPhishing-Richtlinien zur Verfügung stehen, wie im vorherigen Abschnitt beschrieben.

Die Einstellung nicht **authentifizierter Absender** aktiviert oder deaktiviert die nicht authentifizierte Absender Identifikation in Outlook. Insbesondere gilt:

- Dem Foto des Absenders wird ein Fragezeichen (?) hinzugefügt, wenn die Nachricht keine SPF-oder DKIM-Prüfungen übergibt **und** die Nachricht nicht DMARC oder die [kombinierte Authentifizierung](email-validation-and-authentication.md#composite-authentication)übergibt. Durch Deaktivieren der nicht authentifizierten Absender Identifikation wird verhindert, dass das Fragezeichen dem Foto des Absenders hinzugefügt wird.

- Das Via-Tag (Chris@contoso.com <u>über</u> Michelle@fabrikam.com) wird hinzugefügt, wenn die Domäne in der von-Adresse (der Absender der Nachricht, der in e-Mail-Clients angezeigt wird) sich von der Domäne in der DKIM-Signatur oder der **e-Mail-** Adresse unterscheidet. Weitere Informationen zu diesen Adressen finden Sie unter [Übersicht über Standards für e-Mail-Nachrichten](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

  Durch Deaktivieren der nicht authentifizierten Absender Identifikation wird nicht verhindert, dass das via-Tag hinzugefügt wird, wenn sich die Domäne in der von-Adresse von der Domäne in der DKIM-Signatur oder der e-Mail-Adresse unterscheidet.

Um zu verhindern, dass das Fragezeichen oder das über-Tag zu Nachrichten von bestimmten Absendern hinzugefügt wird, stehen Ihnen die folgenden Optionen zur Verfügung:

- Zulassen, dass Absender Spoofing in der Spoof Intelligence-Richtlinie vortäuscht. Durch diese Aktion wird verhindert, dass das via-Tag in Nachrichten vom Absender angezeigt wird, wenn die nicht authentifizierte Absender Identifikation deaktiviert ist. Anweisungen finden Sie unter [configure Spoof Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

- [Konfigurieren Sie die e-Mail-Authentifizierung](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) für die Absenderdomäne.
  
  - Für das Fragezeichen im Foto des Absenders sind SPF oder DKIM die wichtigsten.
  - Bestätigen Sie für das via-Tag die Domäne in der DKIM-Signatur oder die **e-Mail-** Adresse Übereinstimmungen (oder ist eine Unterdomäne von) der Domäne in der von-Adresse.

Weitere Informationen finden Sie unter [Identifizieren von verdächtigen Nachrichten in Outlook.com und Outlook im Internet](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206) .

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a>Exklusive Einstellungen in ATP-Richtlinien zum Schutz vor Phishing

In diesem Abschnitt werden die Richtlinieneinstellungen beschrieben, die nur in Richtlinien für ATP-AntiPhishing verfügbar sind.

> [!NOTE]
> Standardmäßig sind die exklusiven ATP-Einstellungen nicht selbst in der Standardrichtlinie konfiguriert oder aktiviert. Um diese Funktionen nutzen zu können, müssen Sie Sie in der standardmäßigen ATP-AntiPhishing-Richtlinie aktivieren und konfigurieren oder benutzerdefinierte ATP-Richtlinien für die Phishing-Abwehr erstellen und konfigurieren.

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Identitätswechseleinstellungen in ATP-Richtlinien zum Schutz vor Phishing

Bei einem Identitätswechsel sieht der Absender oder die e-Mail-Domäne des Absenders in einer Nachricht wie ein echter Absender oder eine reale Domäne aus:

- Ein Beispiel für einen Identitätswechsel der Domäne contoso.com ist ćóntoso.com.
- Ein Beispiel für einen Identitätswechsel der Benutzerin michelle@contoso.com ist michele@contoso.com.

Eine imitierte Domäne kann ansonsten als seriös gelten (registrierte Domäne, konfigurierte E-Mail-Authentifizierungseinträge usw.). Der Unterschied besteht darin, dass damit Empfänger getäuscht werden sollen.

Die folgenden Identitätswechseleinstellungen sind nur in Richtlinien für ATP-Anti-Phishing verfügbar:

- **Zu schützende Benutzer**: verhindert, dass die angegebene interne oder externe e-Mail-Adresse **als Absender**von Nachrichten imitiert wird. Beispielsweise Führungskräfte (interne Absender) und Verwaltungsratsmitglieder (externe Absender). Sie können bis zu 60 interne und externe Absender-e-Mail-Adressen zum Schutz vor Identitätswechsel hinzufügen. Diese Liste von **Absendern** , die vor Identitätswechsel geschützt sind, unterscheidet sich von der Liste der **Empfänger** , auf die die Richtlinie angewendet wird.

  Die Standardrichtlinie gilt für Nachrichten, die an alle Empfänger gesendet werden, während benutzerdefinierte Richtlinien nur auf Nachrichten angewendet werden, die Sie in der Einstellung **angewendet auf,** wie im Abschnitt [Richtlinieneinstellungen](#policy-settings) beschrieben, an die Empfänger gesendet haben.

  Standardmäßig sind keine Absender-e-Mail-Adressen für den Identitätswechsel Schutz in **Benutzern konfiguriert, die geschützt werden sollen**. Daher werden standardmäßig keine Absender-e-Mail-Adressen durch den Identitätswechsel Schutz in der Standardrichtlinie oder in benutzerdefinierten Richtlinien abgedeckt.

  Wenn Sie der Liste der **zu schützenden Benutzer** interne oder externe e-Mail-Adressen hinzufügen, unterliegen Nachrichten von diesen **Absendern** den Identitätswechsel-Schutzprüfungen. Die Nachricht wird auf den Identitätswechsel überprüft, **Wenn** die Nachricht an einen **Empfänger** gesendet wird, auf den die Richtlinie angewendet wird (alle Empfänger für die Standardrichtlinie; **Auf** Empfänger in benutzerdefinierten Richtlinien angewendet). Wenn der Identitätswechsel in der e-Mail-Adresse des Absenders erkannt wird, werden die Aktionen des Identitätswechsel Schutzes für Benutzer auf die Nachricht angewendet (die Aktion in der Nachricht, der Sicherheitstipp "imitierte Benutzer" usw.).

- **Zu schützende Domänen**: verhindert, dass die angegebenen Domänen **in der Domäne des Nachrichtenabsenders**imitiert werden. Beispielsweise alle Domänen, die Sie besitzen ([akzeptierte Domänen](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) oder bestimmte Domänen (Domänen, die Sie besitzen oder Partnerdomänen). Diese Liste von **Absenderdomänen** , die vor Identitätswechsel geschützt sind, unterscheidet sich von der Liste der **Empfänger** , auf die die Richtlinie angewendet wird.

  Die Standardrichtlinie gilt für Nachrichten, die an alle Empfänger gesendet werden, während benutzerdefinierte Richtlinien nur auf Nachrichten angewendet werden, die Sie in der Einstellung **angewendet auf,** wie im Abschnitt [Richtlinieneinstellungen](#policy-settings) beschrieben, an die Empfänger gesendet haben.

  Standardmäßig sind keine Absenderdomänen für den Identitätswechsel Schutz in Domänen konfiguriert **, die geschützt werden sollen**. Daher werden standardmäßig keine Absenderdomänen durch den Identitätswechsel Schutz in der Standardrichtlinie oder in benutzerdefinierten Richtlinien behandelt.

  Wenn Sie Domänen zu Domänen hinzufügen, um die Liste zu **schützen** , unterliegen Nachrichten von **Absendern in diesen Domänen** den Identitätswechsel-Schutzprüfungen. Die Nachricht wird auf den Identitätswechsel überprüft, **Wenn** die Nachricht an einen **Empfänger** gesendet wird, auf den die Richtlinie angewendet wird (alle Empfänger für die Standardrichtlinie; **Auf** Empfänger in benutzerdefinierten Richtlinien angewendet). Wenn der Identitätswechsel in der Domäne des Absenders erkannt wird, werden die Schutzaktionen für den Identitätswechsel für Domänen auf die Nachricht angewendet (die Aktion in der Nachricht, der Sicherheitstipp "imitierte Domänen" usw.).

- **Aktionen für geschützte Benutzer oder Domänen**: Wählen Sie die Aktion aus, die für eingehende Nachrichten ausgeführt werden soll, die Identitätswechsel Versuche für geschützte Benutzer und geschützte Domänen in der Richtlinie enthalten. Sie können verschiedene Aktionen für den Identitätswechsel von geschützten Benutzern im Vergleich zum Identitätswechsel geschützter Domänen angeben:

  - **Keine Aktion anwenden**

  - **Nachricht an andere e-Mail-Adressen umleiten**: sendet die Nachricht an die angegebenen Empfänger anstelle der vorgesehenen Empfänger.

  - **Nachricht in Junk-e-Mail-Ordner verschieben**: die Nachricht wird an das Postfach übermittelt und in den Junk-e-Mail-Ordner verschoben. In Exchange Online wird die Nachricht in den Junk-e-Mail-Ordner verschoben, wenn die Junk-e-Mail-Regel für das Postfach aktiviert ist (Sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-e-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

    - **Nachricht in Quarantäne verschieben**: sendet die Nachricht an die Quarantäne statt an die vorgesehenen Empfänger. Weitere Informationen zur Quarantäne finden Sie in den folgenden Artikeln:

    - [Quarantäne in Microsoft 365](quarantine-email-messages.md)
    - [Verwalten von isolierten Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Übermitteln Sie die Nachricht, und fügen Sie der Zeile Bcc weitere Adressen hinzu**: senden Sie die Nachricht an die beabsichtigten Empfänger, und übermitteln Sie die Nachricht automatisch an die angegebenen Empfänger.

  - **Löschen Sie die Nachricht, bevor Sie zugestellt**wird: Löscht die gesamte Nachricht, einschließlich aller Anlagen, automatisch.

- **Sicherheitstipps**: aktiviert oder deaktiviert die folgenden Sicherheitstipps für Identitätswechsel, die Nachrichten angezeigt werden, bei denen die Identitätswechsel Prüfung fehlschlägt:

  - **Imitierte Benutzer**: die Absenderadresse enthält einen geschützten Benutzer.
  - **Imitierte Domänen**: die Absenderadresse enthält eine geschützte Domäne.
  - **Ungewöhnliche Zeichen**: die from-Adresse enthält ungewöhnliche Zeichensätze (beispielsweise mathematische Symbole und Text oder eine Mischung aus Groß-und Kleinbuchstaben) in einem geschützten Absender oder in einer Domäne.

  > [!NOTE]
  > Selbst wenn die Sicherheitstipps für Identitätswechsel deaktiviert sind, können Sie eine e-Mail-Fluss Regel (auch als Transportregel bezeichnet) verwenden, um Nachrichten eine Nachrichtenkopfzeile mit dem Namen **X-MS-Exchange-EnableFirstContactSafetyTip** hinzuzufügen. Es werden spezielle Sicherheitstipps angezeigt, in denen Empfänger benachrichtigt werden, dass Sie häufig keine e-Mails vom Absender erhalten, oder in Fällen, in denen der Empfänger zum ersten Mal eine e-Mail vom Absender erhält.

- **Post Fach Intelligenz**: aktiviert oder deaktiviert künstliche Intelligenz (AI), die Benutzer-e-Mail-Muster mit ihren häufigen Kontakten bestimmt. Diese Einstellung unterstützt die KI zwischen legitimen und gefälschten e-Mails von diesen Kontakten. Die Post Fach Intelligenz steht nur für Exchange Online Postfächer zur Verfügung.

- **Post Fachnachrichten basierter Identitätswechsel Schutz**: aktiviert oder deaktiviert erweiterte Identitätswechsel Ergebnisse basierend auf den einzelnen Absender Karten der einzelnen Benutzer. Diese Intelligenz ermöglicht es Microsoft 365, die Erkennung von Benutzer Identitätswechseln anzupassen und besser mit falsch positiven Ergebnissen zu umgehen. Wenn ein Benutzeridentitätswechsel erkannt wird, können Sie eine bestimmte Aktion definieren, die für die Nachricht ausgeführt werden soll:

  - **Keine Aktion anwenden**
  - **Weiterleiten von Nachrichten an andere e-Mail-Adressen**
  - **Nachricht in Junk-E-Mail-Ordner verschieben**
  - **Nachricht isolieren**
  - **Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**
  - **Löschen der Nachricht vor der Zustellung**

- **Vertrauenswürdige Absender und Domänen**: Ausnahmen für die Schutzeinstellungen für den Identitätswechsel. Nachrichten von den angegebenen Absendern und Absenderdomänen werden nie als Identitätswechsel basierte Angriffe durch die Richtlinie klassifiziert. Mit anderen Worten: die Aktion für geschützte Absender, geschützte Domänen oder den Post Fachnachrichten Schutz wird nicht auf diese vertrauenswürdigen Absender oder Absenderdomänen angewendet. Der maximale Grenzwert für diese Listen beträgt ca. 1000 Einträge.

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a>Erweiterte Phishing-Schwellenwerte in ATP-Richtlinien zum Schutz vor Phishing

Die folgenden erweiterten Phishing-Schwellenwerte sind nur in ATP-AntiPhishing-Richtlinien verfügbar, um die Empfindlichkeit beim Anwenden von maschinellen Lernmodellen auf Nachrichten zur Bestimmung eines Phishing-Urteils zu steuern:

- **1-Standard**: Dies ist der Standardwert. Der Schweregrad der Aktion, die für die Nachricht ausgeführt wird, hängt vom Grad der Vertrauenswürdigkeit der Nachricht ab (niedrig, Mittel, hoch oder sehr hohes Vertrauen). Nachrichten, die als Phishing mit einem sehr hohen Vertrauensgrad identifiziert werden, weisen beispielsweise die schwersten Aktionen auf, während Nachrichten, die als Phishing mit einem niedrigen Vertrauensgrad identifiziert werden, weniger schwerwiegende Aktionen angewendet haben.

- **2-aggressiv**: Nachrichten, die als Phishing mit einem hohen Maß an Vertrauen identifiziert werden, werden so behandelt, als ob Sie mit einem sehr hohen Maß an Zuverlässigkeit identifiziert wurden.

- **3-aggressiver**: Nachrichten, die als Phishing mit mittlerem oder hohem Vertrauensgrad identifiziert werden, werden so behandelt, als wären Sie mit einem sehr hohen Maß an Vertrauen gekennzeichnet.

- **4-am aggressivsten**: Nachrichten, die als Phishing mit niedrigem, mittlerem oder hohem Maß an Zuverlässigkeit identifiziert werden, werden so behandelt, als wären Sie mit einem sehr hohen Maß an Zuverlässigkeit identifiziert worden.

Die Wahrscheinlichkeit, dass falsch positive Ergebnisse (gute Nachrichten, die als ungültig markiert werden) erhöht wird, wenn Sie diese Einstellung erhöhen. Informationen zu den empfohlenen Einstellungen finden Sie unter [ATP Anti-Phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).
