---
title: Konfigurieren von Spamfilterrichtlinien
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Administratoren erfahren, wie Sie Anti-Spam-Richtlinien in Exchange Online Protection (EOP) anzeigen, erstellen, ändern und löschen können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 910923e693804c96c109c52606b62d92af51abeb
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228663"
---
# <a name="configure-anti-spam-policies-in-eop"></a>Konfigurieren von Antispamrichtlinien in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder Organisationen mit dem eigenständigen Exchange Online Protection-Produkt (EOP) ohne Exchange Online-Postfächer werden eingehende E-Mail-Nachrichten automatisch von EOP vor Spam geschützt. EOP verwendet Antispamrichtlinien (auch als Spamfilterrichtlinien oder Inhaltsfilterrichtlinien bezeichnet) als Teil des allgemeinen Schutzes Ihrer Organisation gegen Spam. Weitere Informationen finden Sie unter [Antispamschutz](anti-spam-protection.md).

Administratoren können die standardmäßige Antispamrichtlinie anzeigen, bearbeiten und konfigurieren (aber nicht löschen). Um eine höhere Granularität zu erzielen, können Sie auch benutzerdefinierte Antispamrichtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten. Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.

Sie können Antispamrichtlinien im Microsoft 365 Defender-Portal oder in PowerShell konfigurieren (Exchange Online-PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP-PowerShell für Organisationen ohne Exchange Online-Postfächer).

Die grundlegenden Elemente einer Antispamrichtlinie sind:

- **Die Spamfilterrichtlinie**: gibt die Aktionen für Spamfilterbewertungen und die Benachrichtigungsoptionen an.
- **Die Spamfilterregel**: gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) für eine Spamfilterrichtlinie an.

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Antispamrichtlinien im Microsoft 365 Defender-Portal verwalten:

- Beim Erstellen einer Antispamrichtlinie erstellen Sie tatsächlich gleichzeitig eine Spamfilterregel und die zugehörige Spamfilterrichtlinie, beide mit demselben Namen.
- Wenn Sie eine Antispamrichtlinie ändern, dann ändern Einstellungen in Bezug auf Name, Priorität, aktiviert oder deaktiviert und Empfängerfilter die Spamfilterregel. Alle anderen Einstellungen ändern die zugehörige Spamfilterrichtlinie.
- Wenn Sie eine Antispamrichtlinie entfernen, werden die Spamfilterregel und die zugeordnete Spamfilterrichtlinie entfernt.

In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt. Weitere Informationen finden Sie im Abschnitt [Verwenden von Exchange Online PowerShell oder eigenständige EOP PowerShell zum Konfigurieren von Antispamrichtlinien](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) weiter unten in diesem Artikel.

Jede Organisation verfügt über eine integrierte Antispamrichtlinie namens "Standard" mit folgenden Eigenschaften:

- Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine Spamfilterregel (kein Empfängerfilter) zugeordnet ist.
- Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet). Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität.
- Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.

Wenn Sie die Effektivität der Spamfilterung erhöhen möchten, können Sie benutzerdefinierte Antispamrichtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>. Wechseln Sie direkt zur Seite **Antispamrichtlinien**, verwenden Sie <https://security.microsoft.com/antispam>.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:
  - Um Antispamrichtlinien hinzuzufügen, zu ändern oder zu löschen, müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung** oder **Sicherheitsadministrator** sein.
  - Für den schreibgeschützten Zugriff auf Antispamrichtlinien müssen Sie Mitglied der Rollengruppe **Globaler Leseberechtigter** oder **Sicherheitsleseberechtigter** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweise**:

  - Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Die empfohlenen Einstellungen für Richtlinien für Antispam finden Sie unter [EOP-Antispam-Richtlinieneinstellungen](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-spam-policies"></a>Verwenden Sie das Microsoft 365 Defender-Portal, um Anti-Spam-Richtlinien zu erstellen

Beim Erstellen einer benutzerdefinierten Antispamrichtlinie im Microsoft 365 Defender-Portal werden gleichzeitig die Spamfilterregel und die zugehörige Spamfilterrichtlinie mit demselben Namen erstellt.

1. Wechseln Sie im Microsoft 365 Defender-Portal zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** Seite \> **Richtlinien** Abschnitt \> **Antispam**.

2. Klicken Sie auf der Seite **Antispamrichtlinien** auf das ![Symbol „Erstellen“](../../media/m365-cc-sc-create-icon.png) **Richtlinie erstellen**, und wählen Sie dann **Eingehend** aus der Dropdownliste aus.

3. Der Richtlinienassistent wird geöffnet. Konfigurieren Sie auf der Seite **Benennen Sie Ihre Richtlinie** diese Einstellungen:
   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.
   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

4. Auf der dann angezeigten Seite **Benutzer, Gruppen und Domänen** identifizieren Sie die internen Empfänger, für welche die Richtlinie gilt (Empfängerbedingungen):
   - **Benutzer**: Die angegebenen Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.
   - **Gruppen**: Die angegebenen Verteilergruppen, E-Mail-aktivierten Sicherheitsgruppen oder Microsoft 365-Gruppen in Ihrer Organisation.
   - **Domänen**: Alle Empfänger in der angegebenen [akzeptierten Domäne](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in Ihrer Organisation.

   Klicken Sie auf das entsprechende Feld, beginnen Sie mit der Eingabe eines Wertes, und wählen Sie den gewünschten Wert aus den Ergebnissen aus. Wiederholen Sie diesen Vorgang so oft wie nötig. Um einen vorhandenen Wert zu entfernen, klicken Sie auf das ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

   Für Benutzer oder Gruppen können Sie die meisten Bezeichner verwenden (Name, Anzeigename, Alias, E-Mail-Adresse, Kontoname usw.), aber in den Ergebnissen wird der entsprechende Anzeigename angezeigt. Geben Sie für Benutzer einen einzelnen Stern (\*) ein, um alle verfügbaren Werte anzuzeigen.

   Mehreren Werten in der gleichen Bedingung verwenden die „ODER“-Logik (z. B. _\<recipient1\>_ ODER _\<recipient2\>_). Unterschiedlichen Bedingungen verwenden die „UND“-Logik (z. B. _\<recipient1\>_ UND _\<member of group 1\>_).

   - **Ausschließen dieser Benutzer, Gruppen und Domänen**: Um Ausnahmen für die internen Empfänger hinzuzufügen, für welche die Richtlinie gilt (Empfängerausnahmen), wählen Sie diese Option und konfigurieren Sie die Ausnahmen. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

5. Konfigurieren Sie auf der Seite **Massen-E-Mail-Schwellenwert und Spam-Eigenschaften**, die erscheint, die folgenden Einstellungen:

   - **Massen-E-Mail-Schwellenwert**: Gibt das Massenbeschwerdeniveau (Bulk Complaint Level, BCL) einer Nachricht an, das die angegebene Aktion für die **Massen**-Spamfilterbewertung auslöst (größer als, nicht größer als oder gleich wie der angegebene Wert). Ein höherer Wert gibt an, dass die Nachricht weniger erwünscht ist (eher Spam ähnelt). Der Standardwert ist 7. Weitere Informationen finden Sie unter [BCL-Werte (Bulk Complaint Level) in EOP](bulk-complaint-level-values.md) und [Worin besteht der Unterschied zwischen Junk- und Massen-E-Mail?](what-s-the-difference-between-junk-email-and-bulk-email.md).

     Standardmäßig hat die ausschließliche PowerShell-Einstellung _MarkAsSpamBulkMail_ in Antispamrichtlinien den Wert `On`. Diese Einstellung hat einen wesentlichen Einfluss auf die Ergebnisse einer **Massen**-Filterbewertung:

     - **_MarkAsSpamBulkMail_ ist „Ein“**: Ein BCL-Wert, der größer als der Schwellenwert ist, wird in einen SCL-Wert 6 konvertiert, der einer Filterbewertung **Spam** entspricht, und die Aktion für die **Massen**-Filterbewertung wird für Nachricht ausgeführt.
     - **_MarkAsSpamBulkMail_ ist „Aus“**: Die Nachricht wird mit dem BCL gestempelt, aber es wird _keine Aktion_ für eine **Massen**-Filterbewertung ausgeführt. Tatsächlich sind der BCL-Schwellenwert und die Aktion für die **Massen**-Filterbewertung irrelevant.

   - **Spam-Bewertung erhöhen**, **Als Spam markieren**<sup>\*</sup> und **Testmodus**: Enthalten die Einstellungen für den erweiterten Spamfilter (Advanced Spam Filter, ASF), die standardmäßig deaktiviert sind. ASF-Einstellungen werden demnächst nicht mehr unterstützt, und ihre Funktionalität wird in andere Teile des Filterstapels übernommen. Wir empfehlen, alle diese ASF-Einstellungen in Ihren Antispamrichtlinien deaktiviert zu lassen.

     Ausführliche Informationen zu diesen Einstellungen finden Sie unter [Einstellungen für erweiterte Spam Filter (ASF) in EOP](advanced-spam-filtering-asf-options.md).

      <sup>\*</sup> **Enthält bestimmte Sprachen** und **Aus diesen Ländern** sind nicht Teil der ASF-Einstellungen.

   - **Enthält bestimmte Sprachen**: Klicken Sie auf das Feld und wählen Sie **Ein** oder **Aus** in der Dropdownliste aus. Wenn Sie die Option aktivieren, erscheint ein Feld. Beginnen Sie mit der Eingabe des Namens einer Sprache im Feld. Eine gefilterte Liste unterstützter Sprachen wird angezeigt. Wenn Sie die Sprache finden, die Sie suchen, wählen Sie diese aus. Wiederholen Sie diesen Schritt so oft wie nötig. Um einen bestehenden Wert zu entfernen, klicken Sie „entfernen“ ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

   - **Aus diesen Ländern** _: Klicken Sie auf das Feld und wählen Sie _ *Ein** oder **Aus** in der Dropdownliste aus. Wenn Sie die Option aktivieren, erscheint ein Feld. Beginnen Sie mit der Eingabe des Namens eines Landes im Feld. Eine gefilterte Liste der unterstützten Länder wird angezeigt. Wenn Sie das Land finden, das Sie suchen, wählen Sie es aus. Wiederholen Sie diesen Schritt so oft wie nötig. Um einen bestehenden Wert zu entfernen, klicken Sie „entfernen“ ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

6. Konfigurieren Sie auf der angezeigten Seite **Aktionen** die folgenden Einstellungen:

   - **Nachrichtenaktionen**: Wählen oder überprüfen Sie die Aktion, die für Nachrichten auf der Grundlage der folgenden Spamfilterbewertungen ausgeführt werden soll:
     - **Spam**
     - **Nachricht mit hoher Spamwahrscheinlichkeit**
     - **Phishing**
     - **Hohe Phishing-Konfidenz**
     - **Masse**

     In der folgenden Tabelle sind die verfügbaren Aktionen für die Spamfilterbewertungen beschrieben.

     - Ein Häkchen ( ![Häkchen](../../media/checkmark.png) ) gibt an, dass die Aktion verfügbar ist (nicht alle Aktionen sind für alle Bewertungen verfügbar).
     - Ein Sternchen ( <sup>\*</sup> ) nach dem Häkchen kennzeichnet die Standardaktion für die Spamfilterbewertung.

     <br>

     ****

     |Aktion|Spam|Hoch<br>Konfidenz<br>Spam|Phishing|Hoch<br>Konfidenz<br>Phishing|Masse|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**Nachricht in Junk-E-Mail-Ordner verschieben**: Die Nachricht wird an das Postfach übermittelt und in den Junk-E-Mail-Ordner verschoben.<sup>1</sup>|![Häkchen](../../media/checkmark.png)<sup>\*</sup>|![Häkchen](../../media/checkmark.png)<sup>\*</sup>|![Häkchen](../../media/checkmark.png)||![Häkchen](../../media/checkmark.png)<sup>\*</sup>|
     |**X-Header hinzufügen**: Fügt dem Nachrichtenheader einen X-Header hinzu und übermittelt die Nachricht an das Postfach. <p> Sie geben den Namen des X-Header-Felds (nicht den Wert) zu einem späteren Zeitpunkt in das Feld **Diesen X-Header-Text hinzufügen** ein. <p> Bei den Bewertungen **Spam** und **Nachricht mit hoher Spamwahrscheinlichkeit** wird die Nachricht in den Junk-E-Mail-Ordner verschoben.<sup>1,2</sup>|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)||![Häkchen](../../media/checkmark.png)<sup>\*</sup>|
     |**Text in Betreffzeile voranstellen**: Fügt Text am Anfang der Betreffzeile der Nachricht ein. Die Nachricht wird an das Postfach übermittelt und in den Junk-E-Mail-Ordner verschoben.<sup>1,2</sup> <p> Sie geben den Text später im Feld **Text in Betreffzeile voranstellen** ein.|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)||![Häkchen](../../media/checkmark.png)|
     |**Nachricht an E-Mail-Adresse umleiten**: Sendet die Nachricht an andere Empfänger statt an die vorgesehenen Empfänger. <p> Sie geben die Empfänger später im Feld **An diese E-Mail-Adresse umleiten** an.|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
     |**Nachricht löschen:** Löscht automatisch die gesamte Nachricht, einschließlich aller Anlagen.|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)||![Häkchen](../../media/checkmark.png)|
     |**Nachricht in Quarantäne verschieben**: Verschiebt die Nachricht in Quarantäne, anstatt sie an die vorgesehenen Empfänger zu senden. <p> Wie lange die Nachricht in Quarantäne bleiben soll, geben Sie später im Feld **Quarantäne** an.|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)<sup>\*</sup>|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
     |**Keine Aktion**|||||![Häkchen](../../media/checkmark.png)|
     |

     > <sup>1</sup> In Exchange Online wird die Nachricht in den Junk-E-Mail-Ordner verschoben, wenn die Junk-E-Mail-Regel für das Postfach aktiviert ist (sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer](configure-junk-email-settings-on-exo-mailboxes.md).
     >
     > In Hybridumgebungen, in denen EOP lokale Exchange-Postfächer schützt, müssen Sie im lokalen Exchange Nachrichtenflussregeln zur Übersetzung der EOP-Spamfilterbewertung konfigurieren (auch als Transportregeln bezeichnet), damit die Junk-E-Mail-Regel die Nachricht in den Junk-E-Mail-Ordner verschieben kann. Ausführliche Informationen finden Sie unter [Konfigurieren von EOP zum Verschieben von Spam in den Junk-E-Mail-Ordner in Hybridumgebungen](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).
     >
     > <sup>2</sup> Sie können diesen Wert als Bedingung in Nachrichtenflussregeln verwenden, um die Nachricht zu filtern oder weiterzuleiten.

   - **Spam für so viele Tage in Quarantäne aufbewahren**: Gibt an, wie lange die Nachricht in Quarantäne bleibt, wenn Sie **Nachricht in Quarantäne verschieben** als Aktion für eine Spamfilterbewertung ausgewählt haben. Nach Ablauf des Zeitraums wird die Nachricht gelöscht. Die Standardeinstellung beträgt 30 Tage. Ein gültiger Wert liegt zwischen 1 und 30 Tagen. Informationen zur Quarantäne finden Sie in den folgenden Themen:

     - [In Quarantäne befindliche Nachrichten in EOP](quarantine-email-messages.md)
     - [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md)
     - [Suchen und Freigeben von isolierten Nachrichten als Benutzer in EOP](find-and-release-quarantined-messages-as-a-user.md)

   - **Diesen X-Header-Text hinzufügen**: Dieses Feld ist nur dann erforderlich und verfügbar, wenn Sie **X-Header hinzufügen** als Aktion für eine Spamfilterbewertung ausgewählt haben. Der von Ihnen angegebene Wert ist der Headerfeld-*Name*, der dem Nachrichtenheader hinzugefügt wird. Der Headerfeld-*Wert* lautet immer `This message appears to be spam`.

     Die maximale Länge beträgt 255 Zeichen, und der Wert darf keine Leerzeichen oder Doppelpunkte (:) enthalten.

     Wenn Sie beispielsweise den Wert `X-This-is-my-custom-header` eingeben, wird der Nachricht der X-Header `X-This-is-my-custom-header: This message appears to be spam.` hinzugefügt.

     Wenn Sie einen Wert eingeben, der Leerzeichen oder Doppelpunkte (:) enthält, wird der eingegebene Wert ignoriert, und der Nachricht wird der standardmäßige X-Header (`X-This-Is-Spam: This message appears to be spam.`) hinzugefügt.

   - **Der Betreffzeile folgenden Text voranstellen**: Dieses Feld ist nur dann erforderlich und verfügbar, wenn Sie **Der Betreffzeile folgenden Text voranstellen** als Aktion für eine Spamfilterbewertung ausgewählt haben. Geben Sie den Text ein, der am Anfang der Betreffzeile der Nachricht hinzugefügt werden soll.

   - **An diese E-Mail-Adresse umleiten**: Dieses Feld ist nur dann erforderlich und verfügbar, wenn Sie **An diese E-Mail-Adresse umleiten** als Aktion für eine Spamfilterbewertung ausgewählt haben. Geben Sie die E-Mail-Adresse ein, an die Sie die Nachricht senden möchten. Mehrere Werte können durch Semikolons (;) getrennt angegeben werden.

   - **Sicherheitstipps aktivieren**: Standardmäßig sind Sicherheitstipps aktiviert, Sie können sie jedoch deaktivieren, indem Sie das Kontrollkästchen löschen.

   - **Automatische Bereinigung zur Nullstunde (Zero-Hour Auto Purge, ZAP) aktivieren**: ZAP erkennt Nachrichten, die bereits an Exchange Online-Postfächer übermittelt wurden, und ergreift Maßnahmen für diese. Weitere Informationen finden Sie unter [Automatische Bereinigung zur Nullstunde – Schutz vor Spam und Schadsoftware](zero-hour-auto-purge.md).

     ZAP ist standardmäßig aktiviert. Wenn ZAP aktiviert ist, sind die folgenden Einstellungen verfügbar:

     - **ZAP für Phishing-Nachrichten aktivieren**: Standardmäßig ist ZAP für das Erkennen von Phishing aktiviert, aber Sie können dies deaktivieren, indem Sie das Kontrollkästchen löschen.
     - **ZAP für Spam-Nachrichten aktivieren**: Standardmäßig ist ZAP für das Erkennen von Spam aktiviert, aber Sie können dies deaktivieren, indem Sie das Kontrollkästchen löschen.

   - **Endbenutzer-Spam-Benachrichtigungen aktivieren**: Weitere Informationen finden Sie im Abschnitt [Konfigurieren von Endbenutzer-Spam-Benachrichtigungen](#configure-end-user-spam-notifications) später in diesem Thema.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

7. Im angezeigten Flyout **Zulassungs- und Blockierungsliste** können Sie Absender von Nachrichten nach E-Mail-Adresse oder E-Mail-Domäne konfigurieren, welche die Spamfilterung überspringen dürfen.

   Im Abschnitt **Zugelassen** können Sie erlaubte Absender und Domänen konfigurieren. Im Abschnitt **Blockiert** können Sie blockierte Absender und Domänen hinzufügen.

   > [!IMPORTANT]
   >
   > Überlegen Sie es sich genau, bevor Sie Domänen zur Liste der erlaubten Domänen hinzufügen. Weitere Informationen finden Sie unter [Erstellen sicherer Absenderlisten in EOP](create-safe-sender-lists-in-office-365.md).
   >
   > Fügen Sie der Liste der zulässigen Domänen niemals Ihre eigenen [akzeptierte Domänen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) oder allgemeine Domänen (z. B. microsoft.com oder office.com) hinzu. Wenn diese Domänen die Spam-Filterung umgehen dürfen, können Angreifer problemlos Nachrichten senden, die diese vertrauenswürdigen Domänen in Ihr Unternehmen spoofen.
   >
   > Das manuelle Sperren von Domänen durch das Hinzufügen zur Liste der blockierten Domänen ist nicht gefährlich, kann jedoch zusätzliche Verwaltungsarbeit bedeuten. Weitere Informationen finden Sie unter [Erstellen von Listen blockierter Absender in EOP](create-block-sender-lists-in-office-365.md).
   >
   > Es kann vorkommen, dass eine Nachricht von unseren Filtern übersehen wird, dass Sie nicht mit der Filterbewertung einverstanden sind, oder dass es einige Zeit dauert, bis sich unsere Systeme darauf einstellen. In diesen Fällen stehen die Zulassungsliste und die Blockierungsliste zur Verfügung, um die aktuelle Filterbewertung zu überschreiben. Sie sollten diese Listen aber sparsam und zeitlich begrenzt einsetzen: Lange Listen können unübersichtlich werden, und unser Filterstapel sollte das tun, wofür er vorgesehen ist. Wenn Sie eine zugelassene Domäne über einen längeren Zeitraum behalten wollen, sollten Sie den Sender bitten, zu verifizieren, dass seine Domäne authentifiziert ist und, falls dies nicht der Fall ist, die DMARC-Option „Ablehnen“ dafür festzulegen.

   Die Schritte, um einen Eintrag zu einer beliebigen Liste hinzuzufügen, sind die gleichen:

   1. Klicken Sie auf den Link für die Liste, die Sie konfigurieren wollen:
      - **Zugelassene** \> **Absender**: Klicken Sie auf **Verwalten von (nn) Absender(n)**.
      - **Zugelassene** \> **Domänen**: Klicken Sie auf **Zugelassene Domänen**.
      - **Blockierte** \> **Absender**: Klicken Sie auf **Verwalten von (nn) Absender(n)**.
      - **Blockierte** \> **Domänen**: Klicken Sie auf **Blockierte Domänen**.

   2. Führen Sie im angezeigten Flyout folgende Schritte aus:
      1. Klicken Sie auf ![Symbol „Erstellen“](../../media/m365-cc-sc-create-icon.png) **Absender hinzufügen** oder **Domäne hinzufügen**.
      2. Geben Sie im angezeigten Flyout **Absender hinzufügen** oder **Domäne hinzufügen** die E-Mail-Adresse des Absenders im Feld **Absender** ein, oder die Domäne im Feld **Domäne**. Während Sie tippen, erscheint der Wert unter dem Feld. Wenn Sie mit der Eingabe der E-Mail-Adresse oder Domäne fertig sind, wählen Sie den Wert unter dem Feld aus.
      3. Wiederholen Sie den vorstehenden Schritt so oft wie nötig. Um einen vorhandenen Wert zu entfernen, klicken Sie auf das ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

      Wenn Sie den Vorgang abgeschlossen haben, klicken Sie auf **Absender hinzufügen** oder **Domäne hinzufügen**.

      Zurück im Haupt-Flyout werden die von Ihnen hinzugefügten Absender oder Domänen auf der Seite aufgelistet. Um einen Eintrag von dieser Seite zu entfernen, führen Sie die folgenden Schritte aus:

      1. Wählen Sie mindestens einen Eintrag aus der Liste aus. Sie können auch das Feld **Suchen** verwenden, um Werte in der Liste zu finden.
      2. Nachdem Sie mindestens einen Eintrag ausgewählt haben, wird das Löschsymbol ![Symbol „Löschen“](../../media/m365-cc-sc-delete-icon.png) angezeigt.
      3. Klicken Sie auf das Löschsymbol ![Symbol „Löschen“](../../media/m365-cc-sc-delete-icon.png) , um die ausgewählten Einträge zu entfernen.

      Wenn Sie den Vorgang abgeschlossen haben, klicken Sie auf **Fertig**.

      Zurück auf der Seite **Zulassungs- und Blockierungsliste** klicken Sie auf **Weiter**, wenn Sie bereit sind, fortzufahren.

8. Überprüfen Sie auf der angezeigten Seite **Überprüfung** Ihre Einstellungen. Sie können in jedem Abschnitt **Bearbeiten** auswählen, um die Einstellungen in diesem Abschnitt zu ändern. Alternativ können Sie auf **Zurück** klicken oder die entsprechende Seite im Assistenten auswählen.

   Wenn Sie den Vorgang abgeschlossen haben, klicken Sie auf **Erstellen**.

9. Klicken Sie in der angezeigten Bestätigungsseite auf **Fertig**.

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-spam-policies"></a>Verwenden Sie das Microsoft 365 Defender-Portal, um Anti-Spam-Richtlinien anzuzeigen

1. Wechseln Sie im Microsoft 365 Defender-Portal zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** Seite \> **Richtlinien** Abschnitt \> **Antispam**.

2. Suchen Sie auf der Seite **Antispamrichtlinien** nach einem der folgenden Werte:
   - Der Wert für **Typ** ist **Benutzerdefinierte Antispamrichtlinie**
   - Der Wert für **Name** ist **Eingehende Antispamrichtlinie (Standard)**

   Die folgenden Eigenschaften werden in der Liste der Antispamrichtlinien angezeigt:

   - **Name**
   - **Status**
   - **Priorität**
   - **Typ**

3. Wenn Sie eine Antispamrichtlinie durch Klicken auf den Namen auswählen, werden die Richtlinieneinstellungen in einem Flyout angezeigt.

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-spam-policies"></a>Verwenden Sie das Microsoft 365 Defender-Portal, um Anti-Spam-Richtlinien zu ändern

1. Wechseln Sie im Microsoft 365 Defender-Portal zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** Seite \> **Richtlinien** Abschnitt \> **Antispam**.

2. Wählen Sie auf der Seite **Antispamrichtlinien** eine Antispamrichtlinie aus der Liste aus, indem Sie auf den Namen klicken:
   - Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei die Spalte **Typ** den Wert **Benutzerdefinierte Antispamrichtlinie** enthält.
   - Die Standardrichtlinie mit dem Namen **Eingehende Antispamrichtlinie (Standard)**.

3. Wählen Sie im angezeigten Flyout für die Richtliniendetails in jedem Abschnitt die Option **Bearbeiten** aus, um die Einstellungen innerhalb des Abschnitts zu ändern. Weitere Informationen zu den Einstellungen finden Sie im vorherigen Abschnitt [Verwenden des Microsoft 365 Defender-Portal zum Erstellen von Antispamrichtlinien](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) in diesem Artikel.

   Bei der Standard-Antispamrichtlinie ist der Abschnitt **Angewendet auf** nicht verfügbar (die Richtlinie gilt für alle), und Sie können die Richtlinie nicht umbenennen.

Informationen zum Aktivieren oder Deaktivieren einer Richtlinie, zum Festlegen der Prioritätsreihenfolge der Richtlinien oder zum Konfigurieren der Quarantänebenachrichtigungen für Endbenutzer finden Sie in den folgenden Abschnitten.

### <a name="enable-or-disable-anti-spam-policies"></a>Aktivieren oder Deaktivieren von Antispamrichtlinien

Die Standard-Antispamrichtlinie kann nicht deaktiviert werden.

1. Wechseln Sie im Microsoft 365 Defender-Portal zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** Seite \> **Richtlinien** Abschnitt \> **Antispam**.

2. Wählen Sie auf der Seite **Antispamrichtlinie** eine Richtlinie mit dem **Typenwert** **Benutzerdefinierte Antispamrichtlinie** aus der Liste aus, indem Sie auf den Namen klicken.

3. Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie einen der folgenden Werte sehen:
   - **Richtlinie deaktiviert**: Um die Richtlinie zu aktivieren, klicken Sie auf ![Symbol „Aktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivieren**.
   - **Richtlinie aktiviert**: Um die Richtlinie zu deaktivieren, klicken Sie auf ![Symbol „Deaktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Deaktivieren**.

4. Klicken Sie im angezeigten Bestätigungsdialog auf **Aktivieren** oder **Deaktivieren**.

5. Klicken Sie im Flyout der Richtliniendetails auf **Schließen**.

Zurück auf der Richtlinien-Hauptseite wird der Wert **Status** der Richtlinie **Aktiviert** oder **Deaktiviert** sein.

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>Festlegen der Priorität von benutzerdefinierten Antispamrichtlinien

Standardmäßig erhalten Antispamrichtlinien eine Priorität, die auf der Reihenfolge ihrer Erstellung basiert (neuere Richtlinien haben eine niedrigere Priorität als ältere). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Um die Priorität einer Richtlinie zu ändern, klicken Sie in den Eigenschaften einer Richtlinie auf **Priorität erhöhen** oder **Priorität verringern** (Sie können den Zahlenwert der **Priorität** im Microsoft 365 Defender-Portal nicht direkt modifizieren). Die Priorität einer Richtlinie zu verändern macht nur Sinn, wenn Sie mehrere Richtlinien haben.

 **Anmerkungen**:

- Im Microsoft 365 Defender-Portal können Sie die Priorität der Antispamrichtlinie erst nach deren Erstellung ändern. In PowerShell können Sie die standardmäßige Priorität bereits beim Erstellen der Spamfilterregel überschreiben (was sich auf die Priorität vorhandener Regeln auswirken kann).
- Antispamrichtlinien werden in der Reihenfolge verarbeitet, in der sie angezeigt werden (die erste Richtlinie hat den **Prioritätswert** 0). Die Standard-Antispamrichtlinie hat den Prioritätswert **Am niedrigsten**, und Sie können dies nicht ändern.

1. Wechseln Sie im Microsoft 365 Defender-Portal zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** Seite \> **Richtlinien** Abschnitt \> **Antispam**.

2. Wählen Sie auf der Seite **Antispamrichtlinie** eine Richtlinie mit dem **Typenwert** **Benutzerdefinierte Antispamrichtlinie** aus der Liste aus, indem Sie auf den Namen klicken.

3. Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie **Priorität erhöhen** oder **Priorität verringern** sehen, abhängig vom aktuellen Prioritätswert und der Anzahl der benutzerdefinierten Richtlinien:
   - Der Antispamrichtlinie mit dem **Prioritätswert** **0** steht nur die Option **Priorität verringern** zur Verfügung.
   - Der Antispamrichtlinie mit dem tiefsten **Prioritätswert** (beispielsweise **3**) steht nur die Option **Priorität erhöhen** zur Verfügung.
   - Wenn Sie drei oder mehr Antispamrichtlinien haben, stehen für die Richtlinien zwischen dem höchsten und dem niedrigsten Prioritätswert sowohl die Option **Priorität erhöhen** als auch die Option **Priorität vermindern** zur Verfügung.

   Klicken Sie auf ![Symbol „Priorität erhöhen“](../../media/m365-cc-sc-increase-icon.png) **Priorität erhöhen** oder ![Symbol „Priorität verringern“](../../media/m365-cc-sc-decrease-icon.png) **Priorität verringern**, um den **Prioritätswert** zu ändern.

4. Wenn Sie den Vorgang abgeschlossen haben, klicken Sie im Flyout der Richtliniendetails auf **Schließen**.

### <a name="configure-end-user-spam-notifications"></a>Konfigurieren von Spambenachrichtigungen für Endbenutzer

Wenn eine Nachricht durch eine Spamfilterbewertung in Quarantäne versetzt wird, können Sie Spambenachrichtigungen für Endbenutzer konfigurieren, damit die Empfänger wissen, was mit Nachrichten passiert ist, die an sie gesendet wurden. Weitere Informationen zu diesen Benachrichtigungen finden Sie unter [Spambenachrichtigungen für Endbenutzer in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. Wechseln Sie im Microsoft 365 Defender-Portal zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** Seite \> **Richtlinien** Abschnitt \> **Antispam**.

2. Wählen Sie auf der Seite **Antispamrichtlinien** eine Antispamrichtlinie aus der Liste aus, indem Sie auf den Namen klicken:
   - Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei die Spalte **Typ** den Wert **Benutzerdefinierte Antispamrichtlinie** enthält.
   - Die Standardrichtlinie mit dem Namen **Eingehende Antispamrichtlinie (Standard)**.

3. Klicken Sie im angezeigten Flyout der Richtliniendetails im Abschnitt **Aktionen** auf **Bearbeiten**. Konfigurieren Sie im angezeigten Flyout **Aktionen** die folgenden Einstellungen:

   - **Spambenachrichtigungen für Endbenutzer aktivieren**: Wählen Sie das Kontrollkästchen aus, um Benachrichtigungen zu aktivieren, oder löschen Sie es, um Benachrichtigungen zu deaktivieren. Wenn Sie das Kontrollkästchen aktivieren, werden die folgenden zusätzlichen Einstellungen angezeigt:

     - **Spambenachrichtigungen für Endbenutzer senden alle (Tage)**: Wählen Sie aus, wie häufig Benachrichtigungen gesendet werden. Die Standardeinstellung beträgt 3 Tage. Sie können 1 bis 15 Tage eingeben.

       Es gibt 3 Zyklen der Spambenachrichtigung für Endbenutzer innerhalb eines 24-Stunden-Zeitraums, die zu den folgenden Zeiten beginnen: 01:00 UTC, 08:00 UTC und 16:00 UTC.

       > [!NOTE]
       > Wenn eine Benachrichtigung während eines vorherigen Zyklus ausgelassen wurde, wird die Benachrichtigung durch einen nachfolgenden Zyklus per Push gesendet. Dies könnte dazu führen, dass mehrere Benachrichtigungen am selben Tag erscheinen.

     - **Sprache**: Klicken Sie auf die Dropdownliste, und wählen Sie eine verfügbare Sprache aus. Der Standardwert ist **Standard**, d. h. Englisch.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

4. Zurück auf dem Flyout der Richtliniendetails klicken Sie auf **Schließen**.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-spam-policies"></a>Verwenden Sie das Microsoft 365 Defender-Portal, um benutzerdefinierte Anti-Spam-Richtlinien zu entfernen

Wenn Sie das Microsoft 365 Defender-Portal verwenden, um eine benutzerdefinierte Antispamrichtlinie zu entfernen, werden sowohl die Spamfilterregel als auch die entsprechende Spamfilterrichtlinie gelöscht. Die Standard-Antispamrichtlinie kann nicht entfernt werden.

1. Wechseln Sie im Microsoft 365 Defender-Portal zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** Seite \> **Richtlinien** Abschnitt \> **Antispam**.

2. Wählen Sie auf der Seite **Antispamrichtlinie** eine Richtlinie mit dem **Typenwert** **Benutzerdefinierte Antispamrichtlinie** aus der Liste aus, indem Sie auf den Namen klicken. Ganz oben auf dem angezeigten Flyout der Richtliniendetails klicken Sie auf ![Symbol „Weiter Aktionen“](../../media/m365-cc-sc-more-actions-icon.png) **Weitere Aktionen** \> ![Symbol „Richtlinie löschen“](../../media/m365-cc-sc-delete-icon.png) **Richtlinie löschen**.

3. Klicken Sie im angezeigten Bestätigungsdialog auf **Ja**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Verwenden von Exchange Online PowerShell oder eigenständige EOP PowerShell zum Konfigurieren von Antispamrichtlinien

Wie bereits beschrieben, besteht eine Antispamrichtlinie aus einer Spamfilterrichtlinie und einer Spamfilterregel.

In Exchange Online PowerShell oder der eigenständigen Exchange Online Protection PowerShell wird der Unterschied zwischen Spamfilterrichtlinien und Spamfilterregeln deutlich. Sie verwalten Spamfilterrichtlinien mithilfe der **\*-HostedContentFilterPolicy**-Cmdlets, und Sie verwalten Spamfilterregeln mithilfe der **\*-HostedContentFilterRule**-Cmdlets.

- In PowerShell erstellen Sie zuerst die Spamfilterrichtlinie und dann die Spamfilterregel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.
- In PowerShell ändern Sie die Einstellungen in der Spamfilterrichtlinie und der Spamfilterregel separat.
- Wenn Sie eine Spamfilterrichtlinie aus PowerShell entfernen, wird die entsprechende Spamfilterregel nicht automatisch entfernt und umgekehrt.

Die folgenden Einstellungen für Antispamrichtlinien sind nur in PowerShell verfügbar:

- Der Parameter _MarkAsSpamBulkMail_, der standardmäßig `On` ist. Die Auswirkungen dieser Einstellung wurden im Abschnitt [Verwenden des Microsoft 365 Defender-Portal zum Erstellen von Antispamrichtlinien](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) weiter oben in diesem Artikel erläutert.

- Die folgenden Einstellungen für Spam-Quarantänebenachrichtigungen für Endbenutzer:
  - Der Parameter _DownloadLink_, der den Link zum Junk-E-Mail-Berichtstool für Outlook anzeigt oder ausblendet.
  - Der Parameter _EndUserSpamNotificationCustomSubject_, den Sie verwenden können, um die Betreffzeile der Benachrichtigung anzupassen.

### <a name="use-powershell-to-create-anti-spam-policies"></a>Verwenden von PowerShell zum Erstellen von Antispamrichtlinien

Das Erstellen einer Antispamrichtlinie in PowerShell ist ein zweistufiger Vorgang:

1. Erstellen Sie die Spamfilterrichtlinie.
2. Erstellen Sie die Spamfilterregel, die die Spamfilterrichtlinie angibt, auf die die Regel angewendet wird.

 **Hinweise**:

- Sie können eine neue Spamfilterregel erstellen und ihr eine vorhandene, nicht zugeordnete Spamfilterrichtlinie zuweisen. Eine Spamfilterregel kann nicht mit mehreren Spamfilterrichtlinien verknüpft werden.
- Sie können die folgenden Einstellungen für neue Spamfilterrichtlinien in PowerShell konfigurieren, die erst dann im Microsoft 365 Defender-Portal verfügbar sind, wenn Sie die Richtlinie erstellt haben:
  - Erstellen Sie die neue Richtlinie als deaktiviert (_Aktiviert_ `$false` im Cmdlet **New-HostedContentFilterRule**).
  - Legen Sie die Priorität der Richtlinie bei der Erstellung fest (_Priority_ _\<Number\>_) im Cmdlet **New-HostedContentFilterRule**).

- Eine neue Spamfilterrichtlinie, die Sie in PowerShell erstellen, wird erst im Microsoft 365 Defender-Portal angezeigt, nachdem Sie die Richtlinie einer Spamfilterregel zugewiesen haben.

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>Schritt 1: Verwenden von PowerShell zum Erstellen einer Spamfilterrichtlinie

Verwenden Sie zum Erstellen einer Spamfilterrichtlinie folgende Syntax:

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In diesem Beispiel wird eine Spamfilterrichtlinie namens Contoso Executives mit den folgenden Einstellungen erstellt:

- Nachrichten werden in Quarantäne gestellt, wenn die Spamfilterbewertung „Spam“ oder „Nachricht mit hoher Spamwahrscheinlichkeit“ lautet.
- BCL 7, 8 oder 9 lösen die Aktion für eine Spamfilterbewertung „Massen-E-Mail“ aus.

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a>Schritt 2: Verwenden von PowerShell zum Erstellen einer Spamfilterregel

Verwenden Sie zum Erstellen einer Spamfilterregel folgende Syntax:

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In diesem Beispiel wird eine neue Spamfilterregel namens Contoso Executives mit den folgenden Einstellungen erstellt:

- Die Spamfilterrichtlinie namens Contoso Executives ist der Regel zugeordnet.
- Die Regel gilt für Mitglieder der Gruppe mit dem Namen „Contoso Executive Group“.

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule).

### <a name="use-powershell-to-view-spam-filter-policies"></a>Verwenden von PowerShell zum Anzeigen von Spamfilterrichtlinien

Führen Sie den folgenden Befehl aus, um eine Übersichtsliste aller Spamfilterrichtlinien anzuzeigen:

```PowerShell
Get-HostedContentFilterPolicy
```

Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Spamfilterrichtlinie zurückzugeben:

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

Dieses Beispiel gibt alle Eigenschaftswerte für die Spamfilterrichtlinie namens „Executives“ zurück.

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).

### <a name="use-powershell-to-view-spam-filter-rules"></a>Verwenden von PowerShell zum Anzeigen von Spamfilterregeln

Verwenden Sie zum Anzeigen vorhandener Spamfilterregeln die folgende Syntax:

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

Führen Sie den folgenden Befehl aus, um eine Übersichtsliste aller Spamfilterregeln anzuzeigen:

```PowerShell
Get-HostedContentFilterRule
```

Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Spamfilterregel zurückzugeben:

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

Dieses Beispiel gibt alle Eigenschaftswerte für die Spamfilterregel namens „Contoso Executives“ zurück.

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule).

### <a name="use-powershell-to-modify-spam-filter-policies"></a>Verwenden von PowerShell zum Ändern von Spamfilterrichtlinien

Abgesehen von den nachfolgenden Elementen stehen beim Ändern einer Spamfilterrichtlinie in PowerShell dieselben Einstellungen zur Verfügung, wie wenn Sie die Richtlinie erstellen gemäß Abschnitt [Schritt 1: Verwenden von PowerShell zum Erstellen einer Spamfilterrichtlinie](#step-1-use-powershell-to-create-a-spam-filter-policy) weiter oben in diesem Artikel.

- Die Option _MakeDefault_, mit der die angegebene Richtlinie zur Standardrichtlinie erklärt wird (angewendet auf alle, immer **Niedrigste** Priorität, und Sie können sie nicht löschen), steht nur zur Verfügung, wenn Sie eine Spamfilterrichtlinie in PowerShell ändern.
- Sie können eine Spamfilterrichtlinie nicht umbenennen (das Cmdlet **Set-HostedContentFilterPolicy** hat keinen _Name_-Parameter). Wenn Sie eine Antispamrichtlinie im Microsoft 365 Defender-Portal umbenennen, benennen Sie nur die _Regel_ für den Spamfilter um.

Verwenden Sie zum Ändern einer Spamfilterrichtlinie folgende Syntax:

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).

### <a name="use-powershell-to-modify-spam-filter-rules"></a>Verwenden von PowerShell zum Ändern von Spamfilterregeln

Die einzige Einstellung, die beim Ändern einer Spamfilterregel in PowerShell nicht verfügbar ist, ist der Parameter _Enabled_, mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Spamfilterregeln finden Sie im nächsten Abschnitt.

Ansonsten stehen keine zusätzlichen Einstellungen zur Verfügung, wenn Sie eine Spamfilterregel in PowerShell ändern. Die gleichen Einstellungen stehen zur Verfügung, wenn Sie eine Regel erstellen gemäß Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen einer Spamfilterregel](#step-2-use-powershell-to-create-a-spam-filter-rule) weiter oben in diesem Artikel.

Verwenden Sie zum Ändern einer Spamfilterregel folgende Syntax:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

In diesem Beispiel wird die vorhandene Spamfilterregel namens `{Fabrikam Spam Filter}` umbenannt.

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule).

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Spamfilterregeln

Durch das Aktivieren oder Deaktivieren einer Spamfilterregel in PowerShell wird die gesamte Antispamrichtlinie (die Spamfilterregel und die zugewiesene Spamfilterrichtlinie) aktiviert bzw. deaktiviert. Die Standard-Antispamrichtlinie kann nicht aktiviert oder deaktiviert werden (sie wird immer auf alle Empfänger angewendet).

Verwenden Sie die folgende Syntax, um eine Spamfilterregel in PowerShell zu aktivieren bzw. zu deaktivieren:

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die Spamfilterregel namens „Marketing Department“ deaktiviert.

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) und [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule).

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>Verwenden von PowerShell zum Festlegen der Priorität von Spamfilterregeln

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie zum Festlegen der Priorität einer Spamfilterregel in PowerShell die folgende Syntax:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

**Hinweise**:

- Verwenden Sie stattdessen den Parameter _Priority_ im Cmdlet **New-HostedContentFilterRule**, um die Priorität einer neuen Regel bei ihrer Erstellung festzulegen.
- Die Standard-Spamfilterrichtlinie weist keine entsprechende Spamfilterregel auf und hat immer den nicht änderbaren Prioritätswert **Niedrigste**.

### <a name="use-powershell-to-remove-spam-filter-policies"></a>Verwenden von PowerShell zum Entfernen von Spamfilterrichtlinien

Wenn Sie eine Spamfilterrichtlinie mithilfe von PowerShell entfernen, wird die entsprechende Spamfilterregel nicht entfernt.

Verwenden Sie folgende Syntax, um eine Spamfilterrichtlinie in PowerShell zu entfernen:

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Spamfilterrichtlinie namens „Marketing Department“ entfernt.

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy).

### <a name="use-powershell-to-remove-spam-filter-rules"></a>Verwenden von PowerShell zum Entfernen von Spamfilterregeln

Wenn Sie eine Spamfilterregel mithilfe von PowerShell entfernen, wird die entsprechende Spamfilterrichtlinie nicht entfernt.

Verwenden Sie folgende Syntax, um eine Spamfilterregel in PowerShell zu entfernen:

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die Spamfilterregel namens „Marketing Department“ entfernt.

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>Senden einer GTUBE-Nachricht, um die Einstellungen für die Spamrichtlinie zu testen

> [!NOTE]
> Diese Schritte funktionieren nur, wenn die E-Mail-Organisation, von der Sie die GTUBE-Nachricht senden, nicht nach ausgehenden Spam-E-Mails sucht. Wenn sie dies tut, können Sie die Testnachricht nicht senden.

GTUBE (Generic Test for Unsolicited Bulk Email) ist eine Textzeichenfolge, die Sie in eine Testnachricht einschließen, um die Antispameinstellungen Ihrer Organisation zu überprüfen. Eine GTUBE-Nachricht ähnelt der EICAR-Textdatei (European Institute for Computer Antivirus Research) zum Testen der Schadsoftwareeinstellungen.

Geben Sie den folgenden GTUBE-Text in eine E-Mail in einer Zeile ohne Leerzeichen und Zeilenumbrüche ein:

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```
