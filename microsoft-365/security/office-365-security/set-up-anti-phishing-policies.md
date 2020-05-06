---
title: Antiphishing-Richtlinien
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie den Schutz gegen Phishing in Microsoft 365 einrichten, um Ihre Organisation vor böswilligen Phishing-Angriffen zu schützen.
ms.openlocfilehash: bbde781114cadb6535bdb09c133d834ce23793a3
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035332"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Anti-Phishing-Richtlinien in Microsoft 365

Richtlinien zum Konfigurieren von Einstellungen zum Schutz vor Phishing sind in Microsoft 365-Organisationen mit Exchange Online-Postfächern, eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächern und Office 365 Advanced Threat Protection (ATP)-Organisationen verfügbar.

ATP-Anti-Phishing-Richtlinien sind nur in Organisationen verfügbar, die Office 365 ATP haben. Zum Beispiel:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Office 365 ATP als Add-on](https://products.office.com/exchange/advance-threat-protection)

Alle anderen Organisationen verfügen über Anti-Phishing-Richtlinien.

In der folgenden Tabelle werden die allgemeinen Unterschiede zwischen Anti-Phishing-Richtlinien und ATP-AntiPhishing-Richtlinien beschrieben:

||||
|---|:---:|:---:|
|**Feature**|**Antiphishing-Richtlinien**|**Richtlinien für ATP-Anti-Phishing**|
|Automatisch erstellte Standardrichtlinie|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Erstellen benutzerdefinierter Richtlinien|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Richtlinieneinstellungen<sup>\*</sup>|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Einstellungen für Identitätswechsel||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Spoof-Einstellungen|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Erweiterte Phishing-Schwellenwerte||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup>In der Standardrichtlinie sind der Richtlinienname und die Beschreibung schreibgeschützt (die Beschreibung ist leer), und Sie können nicht angeben, für wen die Richtlinie gilt (die Standardrichtlinie gilt für alle Empfänger).

Informationen zum Konfigurieren von Anti-Phishing-Richtlinien finden Sie in den folgenden Themen:

- [Konfigurieren von Anti-Phishing-Richtlinien in EoP](configure-anti-phishing-policies-eop.md)

- [Konfigurieren von Richtlinien für die ATP-Anti-Phishing in Microsoft 365](configure-atp-anti-phishing-policies.md)

Im weiteren Verlauf dieses Themas werden die Einstellungen beschrieben, die in Anti-Phishing-Richtlinien und ATP-Anti-Phishing-Richtlinien verfügbar sind.

## <a name="spoof-settings"></a>Spoof-Einstellungen

Spoofing ist, wenn die von-Adresse in einer e-Mail-Nachricht (die Absenderadresse, die in e-Mail-Clients angezeigt wird) nicht mit der Domäne der e-Mail-Quelle übereinstimmt. Weitere Informationen zur Spoofing finden Sie unter [Anti-Spoofing Protection in Microsoft 365](anti-spoofing-protection.md).

Die folgenden spoofeinstellungen stehen unter Anti-Phishing-Richtlinien und ATP-AntiPhishing-Richtlinien zur Verfügung:

- **Schutz gegen Spoofing**: aktiviert oder deaktiviert den Schutz vor Spoofing. Es wird empfohlen, die Option aktiviert zu lassen. Verwenden Sie die **Spoof Intelligence-Richtlinie** , um bestimmte gefälschte interne und externe Absender zuzulassen oder zu blockieren. Weitere Informationen finden Sie unter [Konfigurieren der Spoofintelligenz in Microsoft 365](learn-about-spoof-intelligence.md).

  > [!NOTE]
  > Spoofeinstellungen sind standardmäßig in der standardmäßigen Anti-Phishing-Richtlinie in EoP, der standardmäßigen ATP-antiphishingpolitik und in neuen benutzerdefinierten Anti-Phishing-Richtlinien oder von Ihnen erstellten Richtlinien für das Anti-Phishing-Konzept von ATP aktiviert. <br/><br/> Sie müssen den Schutz vor Spoofing nicht deaktivieren, wenn Ihr MX-Eintrag nicht auf Microsoft 365 verweist; Stattdessen aktivieren Sie die erweiterte Filterung für Connectors. Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

  Für Nachrichten von blockierten gefälschten Absendern können Sie auch die Aktion angeben, die für die Nachrichten ausgeführt werden soll:

  - **Nachricht in den Junk-e-Mail-Ordner umlegen**: Dies ist der Standardwert. Die Nachricht wird an das Postfach übermittelt und in den Junk-e-Mail-Ordner verschoben. In Exchange Online wird die Nachricht in den Junk-e-Mail-Ordner verschoben, wenn die Junk-e-Mail-Regel für das Postfach aktiviert ist (Sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-e-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Nachricht in Quarantäne verschieben**: sendet die Nachricht an die Quarantäne statt an die vorgesehenen Empfänger. Informationen zur Quarantäne finden Sie in den folgenden Themen:

    - [Quarantäne in Microsoft 365](quarantine-email-messages.md)
    - [Verwalten von isolierten Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- Nicht **authentifizierter Absender**: aktiviert oder deaktiviert die Unbekannte Absender Identifikation in Outlook. Insbesondere gilt:

  - Dem Foto des Absenders wird ein Fragezeichen (?) hinzugefügt, wenn die Nachricht keine SPF-oder DKIM-Prüfungen übergibt **und** die Nachricht nicht DMARC oder die [kombinierte Authentifizierung](email-validation-and-authentication.md#composite-authentication)übergibt.

  - Das Via-Tag (Chris@contoso.com <u>über</u> Michelle@fabrikam.com) wird hinzugefügt, wenn die Domäne in der von-Adresse (der Absender der Nachricht, der in e-Mail-Clients angezeigt wird) sich von der Domäne in der DKIM-Signatur oder der **e-Mail-** Adresse unterscheidet. Weitere Informationen zu diesen Adressen finden Sie unter [Übersicht über Standards für e-Mail-Nachrichten](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

  Um zu verhindern, dass diese Bezeichner Nachrichten von bestimmten Absendern hinzugefügt werden, stehen Ihnen die folgenden Optionen zur Verfügung:

  - Zulassen, dass Absender Spoofing in der Spoof Intelligence-Richtlinie vortäuscht. Anweisungen finden Sie unter [configure Spoof Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

  - [Konfigurieren Sie die e-Mail-Authentifizierung](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) für die Absenderdomäne.
  
    - Für das Fragezeichen im Foto des Absenders sind SPF oder DKIM die wichtigsten.
    - Bestätigen Sie für das via-Tag die Domäne in der DKIM-Signatur oder die **e-Mail-** Adresse Übereinstimmungen (oder ist eine Unterdomäne von) der Domäne in der von-Adresse.

  Weitere Informationen finden Sie unter [Identifizieren von verdächtigen Nachrichten in Outlook.com und Outlook im Internet](https://support.office.com/article/3d44102b-6ce3-4f7c-a359-b623bec82206) .

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a>Exklusive Einstellungen in ATP-Richtlinien zum Schutz vor Phishing

In diesem Abschnitt werden die Richtlinieneinstellungen beschrieben, die nur in Richtlinien für ATP-AntiPhishing verfügbar sind.

> [!NOTE]
> Standardmäßig sind die exklusiven ATP-Einstellungen nicht selbst in der Standardrichtlinie konfiguriert oder aktiviert. Um diese Funktionen nutzen zu können, müssen Sie Sie in der standardmäßigen ATP-AntiPhishing-Richtlinie aktivieren und konfigurieren oder benutzerdefinierte ATP-Richtlinien für die Phishing-Abwehr erstellen und konfigurieren.

### <a name="policy-settings-in-atp-anti-phishing-policies"></a>Richtlinieneinstellungen in ATP-Richtlinien zum Schutz vor Phishing

Die folgenden Richtlinieneinstellungen sind nur in Richtlinien für ATP-Anti-Phishing verfügbar:

- **Name**: Sie können die standardmäßige Anti-Phishing-Richtlinie nicht umbenennen, aber Sie können benutzerdefinierte Richtlinien benennen und umbenennen, die Sie erstellen.

- **Beschreibung** Sie können keine Beschreibung zur Standard-Anti-Phishing-Richtlinie hinzufügen, aber Sie können die Beschreibung für benutzerdefinierte Richtlinien, die Sie erstellen, hinzufügen und ändern.

- **Angewendet auf**: identifiziert interne Empfänger, für die die ATP-AntiPhishing-Richtlinie gilt. Dieser Wert ist in benutzerdefinierten Richtlinien erforderlich und in der Standardrichtlinie nicht verfügbar (die Standardrichtlinie gilt für alle Empfänger).

    Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

  - **Empfänger ist**: ein oder mehrere Postfächer, e-Mail-Benutzer oder e-Mail-Kontakte in Ihrer Organisation.
  - **Der Empfänger ist Mitglied von**: eine oder mehrere Gruppen in Ihrer Organisation.
  - **Die Empfängerdomäne ist**: eine oder mehrere der konfigurierten akzeptierten Domänen in Microsoft 365.

  - **Ausnahme**: Ausnahmen für die Regel. Die Einstellungen und das Verhalten sind genau wie die Bedingungen:

    - **Empfänger lautet**
    - **Der Empfänger ist Mitglied von**
    - **Die Empfängerdomäne ist**

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Identitätswechseleinstellungen in ATP-Richtlinien zum Schutz vor Phishing

Identitätswechsel: der Absender oder die e-Mail-Domäne des Absenders in einer Nachricht ähnelt einem tatsächlichen Absender oder einer echten Domäne:

- Ein Beispiel für einen Identitätswechsel der Domäne contoso.com ist ćóntoso.com.

- Ein Beispiel für den Identitätswechsel des Benutzers Michelle@contoso.com ist Michele@contoso.com.

Eine imitierte Domäne wird andernfalls möglicherweise als rechtmäßig (registrierte Domäne, konfigurierte e-Mail-Authentifizierungs Einträge usw.) betrachtet, mit dem Unterschied, dass die Empfänger betrogen werden sollen.

Die folgenden Identitätswechseleinstellungen sind nur in Richtlinien für ATP-Anti-Phishing verfügbar:

- **Zu schützende Benutzer**: verhindert, dass die Identität der angegebenen internen oder externen Benutzer imitiert wird. Beispiel: Führungskräfte (intern) und Verwaltungsratsmitglieder (extern). Sie können bis zu 60 interne und externe Adressen hinzufügen. Diese Liste geschützter Benutzer unterscheidet sich von der Liste der Empfänger, für die die Richtlinie in der Einstellung **angewendet auf** gilt.

  Sie geben beispielsweise Felipe Apodaca (felipea@contoso.com) als geschützten Benutzer in einer Richtlinie an, die für die Gruppe "Führungskräfte" gilt. Eingehende Nachrichten, die an Mitglieder der Gruppe "Führungskräfte" gesendet werden, in der die Identität, in der Felipe Apodaca imitiert wird, von der Richtlinie verarbeitet wird (die Aktion, die Sie für imitierte Benutzer konfigurieren).

- **Zu schützende Domänen**: verhindern, dass die Identität der angegebenen Domänen imitiert wird. Beispielsweise alle Domänen, die Sie besitzen ([akzeptierte Domänen](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) oder bestimmte Domänen (Domänen, die Sie besitzen oder Partnerdomänen). Diese Liste geschützter Domänen unterscheidet sich von der Liste der Domänen, für die die Richtlinie in der Einstellung **angewendet auf** gilt.

  Beispielsweise geben Sie tailspintoys.com als geschützte Domäne in einer Richtlinie an, die für Mitglieder der Gruppe "Führungskräfte" gilt. Eingehende Nachrichten, die an Mitglieder der Gruppe "Führungskräfte" gesendet werden, in der die Identität des Where tailspintoys.com von der Richtlinie verarbeitet wird (die Aktion, die Sie für imitierte Domänen konfigurieren).

- **Aktionen für geschützte Benutzer oder Domänen**: Wählen Sie die Aktion aus, die für eingehende Nachrichten ausgeführt werden soll, die Identitätswechsel Versuche für geschützte Benutzer und geschützte Domänen in der Richtlinie enthalten. Sie können verschiedene Aktionen für den Identitätswechsel von geschützten Benutzern im Vergleich zum Identitätswechsel geschützter Domänen angeben:

  - **Keine Aktion anwenden**

  - **Nachricht an andere e-Mail-Adressen umleiten**: sendet die Nachricht an die angegebenen Empfänger anstelle der vorgesehenen Empfänger.

  - **Nachricht in Junk-e-Mail-Ordner verschieben**: die Nachricht wird an das Postfach übermittelt und in den Junk-e-Mail-Ordner verschoben. In Exchange Online wird die Nachricht in den Junk-e-Mail-Ordner verschoben, wenn die Junk-e-Mail-Regel für das Postfach aktiviert ist (Sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-e-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

    - **Nachricht in Quarantäne verschieben**: sendet die Nachricht an die Quarantäne statt an die vorgesehenen Empfänger. Informationen zur Quarantäne finden Sie in den folgenden Themen:

    - [Quarantäne in Microsoft 365](quarantine-email-messages.md)
    - [Verwalten von isolierten Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Übermitteln Sie die Nachricht, und fügen Sie der Zeile Bcc weitere Adressen hinzu**: senden Sie die Nachricht an die beabsichtigten Empfänger, und übermitteln Sie die Nachricht automatisch an die angegebenen Empfänger.

  - **Löschen Sie die Nachricht, bevor Sie zugestellt**wird: Löscht die gesamte Nachricht, einschließlich aller Anlagen, automatisch.

- **Sicherheitstipps**: aktiviert oder deaktiviert die folgenden Sicherheitstipps für Identitätswechsel, die Nachrichten angezeigt werden, bei denen die Identitätswechsel Prüfung fehlschlägt:

  - **Imitierte Benutzer**: die Absenderadresse enthält einen geschützten Benutzer.
  - **Imitierte Domänen**: die Absenderadresse enthält eine geschützte Domäne.
  - **Ungewöhnliche Zeichen**: die from-Adresse enthält ungewöhnliche Zeichensätze (beispielsweise mathematische Symbole und Text oder eine Mischung aus Groß-und Kleinbuchstaben) in einem geschützten Absender oder in einer Domäne.

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

Die folgenden erweiterten Phishing-Schwellenwerte sind nur in Richtlinien für ATP-AntiPhishing verfügbar, um anzugeben, wie erkannte Phishing-Nachrichten behandelt werden sollen:

- **1-Standard**: Dies ist der Standardwert. Der Schweregrad der Aktion, die für die Nachricht ausgeführt wird, hängt vom Grad der Vertrauenswürdigkeit der Nachricht ab (niedrig, Mittel, hoch oder sehr hohes Vertrauen). Nachrichten, die als Phishing mit einem sehr hohen Vertrauensgrad identifiziert werden, weisen beispielsweise die schwersten Aktionen auf, während Nachrichten, die als Phishing mit einem niedrigen Vertrauensgrad identifiziert werden, weniger schwerwiegende Aktionen angewendet haben.

- **2-aggressiv**: Nachrichten, die als Phishing mit einem hohen Maß an Vertrauen identifiziert werden, werden so behandelt, als ob Sie mit einem sehr hohen Maß an Zuverlässigkeit identifiziert wurden.

- **3-aggressiver**: Nachrichten, die als Phishing mit mittlerem oder hohem Vertrauensgrad identifiziert werden, werden so behandelt, als wären Sie mit einem sehr hohen Maß an Vertrauen gekennzeichnet.

- **4-am aggressivsten**: Nachrichten, die als Phishing mit niedrigem, mittlerem oder hohem Maß an Zuverlässigkeit identifiziert werden, werden so behandelt, als wären Sie mit einem sehr hohen Maß an Zuverlässigkeit identifiziert worden.

Die Wahrscheinlichkeit, dass falsch positive Ergebnisse (gute Nachrichten, die als ungültig markiert werden) erhöht wird, wenn Sie diese Einstellung erhöhen. Informationen zu den empfohlenen Einstellungen finden Sie unter [Einstellungen für Anti-Phishing-Richtlinien für Office ATP](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).