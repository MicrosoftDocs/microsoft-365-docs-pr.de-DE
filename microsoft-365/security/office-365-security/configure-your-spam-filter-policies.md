---
title: Konfigurieren von Spamfilterrichtlinien
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Zu den grundlegenden Spamfiltereinstellungen zählt das Festlegen der Aktionen, die im Hinblick auf als Spam identifizierte Nachrichten durchgeführt werden sollen.
ms.openlocfilehash: 027cea45159131ebe4718dfb2209d8be15f8e355
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637712"
---
# <a name="configure-anti-spam-policies"></a>Konfigurieren von Antispamrichtlinien

Wenn Sie ein Microsoft 365-Kunde mit Postfächern in Exchange Online oder ein Kunde des eigenständigen Exchange Online Protection-Produkts (EOP) ohne Exchange Online-Postfächer sind, werden eingehende E-Mail-Nachrichten automatisch von EOP vor Spam geschützt. EOP verwendet Antispamrichtlinien (auch als Spamfilterrichtlinien oder Inhaltsfilterrichtlinien bezeichnet) als Teil des allgemeinen Schutzes Ihrer Organisation gegen Spam. Weitere Informationen finden Sie unter [Antispamschutz](anti-spam-protection.md).

Administratoren können die standardmäßige Antispamrichtlinie anzeigen, bearbeiten und konfigurieren (aber nicht löschen). Um eine höhere Granularität zu erzielen, können Sie auch benutzerdefinierte Antispamrichtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten. Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.

Sie können Antispamrichtlinien im Security & Compliance Center oder in PowerShell konfigurieren (Exchange Online PowerShell für Microsoft 365-Kunden, Exchange Online Protection PowerShell für eigenständige EOP-Kunden).

## <a name="anti-spam-policies-in-the-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a>Antispamrichtlinien im Security & Compliance Center im Vergleich zu Exchange Online PowerShell oder Exchange Online Protection PowerShell

Die grundlegenden Elemente einer Antispamrichtlinie in EOP sind:

- **Die Spamfilterrichtlinie**: gibt die Aktionen für Spamfilterbewertungen und die Benachrichtigungsoptionen an.

- **Die Spamfilterregel**: gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) für eine Spamfilterrichtlinie an.

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Antispamrichtlinien im Security & Compliance Center verwalten:

- Beim Erstellen einer Antispamrichtlinie im Security & Compliance Center erstellen Sie tatsächlich gleichzeitig eine Spamfilterregel und die zugehörige Spamfilterrichtlinie, beide mit demselben Namen.

- Wenn Sie eine Antispamrichtlinie im Security & Compliance Center ändern, ändern die Einstellungen im Zusammenhang mit Name, Priorität, aktiviert oder deaktiviert und Empfängerfilter tatsächlich die Spamfilterregel. Alle anderen Einstellungen ändern die zugehörige Spamfilterrichtlinie.

- Wenn Sie eine Antispamrichtlinie aus dem Security & Compliance Center entfernen, werden die Spamfilterregel und die zugeordnete Spamfilterrichtlinie entfernt.

In Exchange Online PowerShell oder der eigenständigen Exchange Online Protection PowerShell wird der Unterschied zwischen Spamfilterrichtlinien und Spamfilterregeln deutlich. Sie verwalten Spamfilterrichtlinien mithilfe der **\*-HostedContentFilterPolicy**-Cmdlets, und Sie verwalten Spamfilterregeln mithilfe der **\*-HostedContentFilterRule**-Cmdlets.

- In PowerShell erstellen Sie zuerst die Spamfilterrichtlinie und dann die Spamfilterregel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.

- In PowerShell ändern Sie die Einstellungen in der Spamfilterrichtlinie und der Spamfilterregel separat.

- Wenn Sie eine Spamfilterrichtlinie aus PowerShell entfernen, wird die entsprechende Spamfilterregel nicht automatisch entfernt und umgekehrt.

### <a name="default-anti-spam-policy"></a>Standard-Antispamrichtlinie

Jede Organisation verfügt über eine integrierte Antispamrichtlinie namens „Standard“ mit folgenden Eigenschaften:

- Die Spamfilterrichtlinie namens „Standard“ wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine Spamfilterregel (kein Empfängerfilter) zugeordnet ist.

- Die Richtlinie namens „Standard“ weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet). Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer Vorrang vor der Richtlinie „Standard“.

- Die Richtlinie namens „Standard“ ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.

Wenn Sie die Effektivität der Spamfilterung erhöhen möchten, können Sie benutzerdefinierte Antispamrichtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://protection.office.com/antispam>.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Um Antispamrichtlinien hinzuzufügen, zu ändern oder zu löschen, müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung** oder **Sicherheitsadministrator** sein. Für den schreibgeschützten Zugriff auf Antispamrichtlinien müssen Sie Mitglied der Rollengruppe **Sicherheitsleseberechtigter** sein. Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Die empfohlenen Einstellungen für Richtlinien für Antischadsoftware finden Sie unter [EOP-Antispam-Richtlinieneinstellungen](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a>Verwenden des Security & Compliance Centers zum Erstellen von Antispamrichtlinien

Beim Erstellen einer benutzerdefinierten Antispamrichtlinie im Security & Compliance Center werden gleichzeitig die Spamfilterregel und die zugehörige Spamfilterrichtlinie mit demselben Namen erstellt.

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie auf der Seite **Antispameinstellungen** auf **Richtlinie erstellen**.

3. Konfigurieren Sie im sich öffnenden Flyout **Neue Spamfilterrichtlinie** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein. Verwenden Sie nicht die folgenden Zeichen: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.

      Wenn Sie zuvor Antispamrichtlinien im Exchange Admin Center (EAC) erstellt haben, die diese Zeichen enthalten, müssen Sie die Antispamrichtlinie in PowerShell umbenennen. Anweisungen hierzu finden Sie im Abschnitt [Verwenden von PowerShell zum Ändern von Spamfilterregeln](#use-powershell-to-modify-spam-filter-rules) weiter unten in diesem Thema.

   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

4. (Optional) Erweitern Sie den Abschnitt **Spam- und Massenaktionen**, und überprüfen oder konfigurieren Sie die folgenden Einstellungen:

   - **Wählen Sie die für eingehende Spam- und Massen-E-Mails auszuführende Aktion aus**: Wählen oder überprüfen Sie die Aktion, die für Nachrichten auf der Grundlage der folgenden Spamfilterbewertungen ausgeführt werden soll:

     - **Spam**
     - **Nachricht mit hoher Spamwahrscheinlichkeit**
     - **Phishing-E-Mail**
     - **Nachricht mit hoher Phishingwahrscheinlichkeit**
     - **Massen-E-Mail**

     In der folgenden Tabelle sind die verfügbaren Aktionen für die Spamfilterbewertungen beschrieben.

     - Ein Häkchen ( ![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) gibt an, dass die Aktion verfügbar ist (nicht alle Aktionen sind für alle Spamfilterbewertungen verfügbar).
     - Ein Sternchen ( <sup>\*</sup> ) nach dem Häkchen kennzeichnet die Standardaktion für die Spamfilterbewertung.

    |||||||
    |:---|:---:|:---:|:---:|:---:|:---:|
    ||**Spam**|**Hohe<br/>Spam-<br/>wahrscheinlichkeit**|**Phishing-<br/>E-Mail**|**Hohe<br/>Phishing-<br/>wahrscheinlich-<br/>keit**|**Massen-<br/>E-Mail**|
    |**Nachricht in Junk-E-Mail-Ordner verschieben**: Die Nachricht wird an das Postfach übermittelt und in den Junk-E-Mail-Ordner verschoben.<sup>1</sup>|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
    |**X-Header hinzufügen**: Fügt dem Nachrichtenheader einen X-Header hinzu und übermittelt die Nachricht an das Postfach. <br/> Sie geben den Namen des X-Header-Felds (nicht den Wert) zu einem späteren Zeitpunkt in das Feld **Diesen X-Header-Text hinzufügen** ein. <br/><br/> Bei den Bewertungen **Spam** und **Nachricht mit hoher Spamwahrscheinlichkeit** wird die Nachricht in den Junk-E-Mail-Ordner verschoben.<sup>1,2</sup>|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
    |**Text in Betreffzeile voranstellen**: Fügt Text am Anfang der Betreffzeile der Nachricht ein. Die Nachricht wird an das Postfach übermittelt und in den Junk-E-Mail-Ordner verschoben.<sup>1,2</sup> <br/> Sie geben den Text später im Feld **Text in Betreffzeile voranstellen** ein.|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |**Nachricht an E-Mail-Adresse umleiten**: Sendet die Nachricht an andere Empfänger statt an die vorgesehenen Empfänger. <br/> Sie geben die Empfänger später im Feld **An diese E-Mail-Adresse umleiten** an.|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |**Nachricht löschen:** Löscht automatisch die gesamte Nachricht, einschließlich aller Anlagen.|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |**Nachricht in Quarantäne verschieben**: Verschiebt die Nachricht in Quarantäne, anstatt sie an die vorgesehenen Empfänger zu senden. <br/> Wie lange die Nachricht in Quarantäne bleiben soll, geben Sie später im Feld **Quarantäne** an.|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |**Keine Aktion**|||||![Häkchen](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |

    > <sup>1</sup> In Exchange Online wird die Nachricht in den Junk-E-Mail-Ordner verschoben, wenn die Junk-E-Mail-Regel für das Postfach aktiviert ist (sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).<br/>In Umgebungen mit eigenständigem EOP, in denen EOP lokale Exchange-Postfächer schützt, müssen Sie im lokalen Exchange Nachrichtenflussregeln zur Übersetzung der EOP-Spamfilterbewertung konfigurieren (auch als Transportregeln bezeichnet), damit die Junk-E-Mail-Regel die Nachricht in den Junk-E-Mail-Ordner verschieben kann. Ausführliche Informationen finden Sie unter [Konfigurieren eigenständiger EOP zur Zustellung von Spam in den Junk-E-Mail-Ordner in Hybridumgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).<br/><br/><sup>2</sup> Sie können diesen Wert als Bedingung in Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, um die Nachricht zu filtern oder weiterzuleiten.

   - **Schwellenwert auswählen**: Gibt das Massenbeschwerdeniveau (Bulk Complaint Level, BCL) einer Nachricht an, das die angegebene Aktion für die Spamfilterbewertung **Massen-E-Mail** auslöst (größer als der angegebene Wert, nicht größer als oder gleich). Ein höherer Wert gibt an, dass die Nachricht weniger erwünscht ist (eher Spam ähnelt). Der Standardwert ist 7. Weitere Informationen finden Sie unter [BCL-Werte (Bulk Complaint Level) in Office 365](bulk-complaint-level-values.md) und [Worin besteht der Unterschied zwischen Junk- und Massen-E-Mail?](what-s-the-difference-between-junk-email-and-bulk-email.md).

     Standardmäßig hat die ausschließliche PowerShell-Einstellung _MarkAsSpamBulkMail_ in Antispamrichtlinien den Wert `On`. Diese Einstellung hat einen wesentlichen Einfluss auf die Ergebnisse einer Filterungsbewertung **Massen-E-Mail-**:

     - **_MarkAsSpamBulkMail_ ist Ein**: Ein BCL-Wert, der größer als der Schwellenwert ist, wird in einen SCL-Wert 6 konvertiert, der einer Filterungsbewertung **Spam** entspricht, und die Aktion für die Filterungsbewertung **Massen-E-Mail** wird für Nachricht ausgeführt.

     - **_MarkAsSpamBulkMail_ ist Aus**: Die Nachricht wird mit dem BCL gestempelt, aber _keine Aktion_ wird für eine Filterungsbewertung **Massen-E-Mail** ausgeführt. Tatsächlich sind der BCL-Schwellenwert und die Aktion für die Filterungsbewertung **Massen-E-Mail** irrelevant.

   - **Quarantäne**: Gibt an, wie lange die Nachricht in Quarantäne bleibt, wenn Sie **Nachricht in Quarantäne verschieben** als Aktion für eine Spamfilterbewertung ausgewählt haben. Nach Ablauf des Zeitraums wird die Nachricht gelöscht. Die Standardeinstellung beträgt 30 Tage. Ein gültiger Wert liegt zwischen 1 und 30 Tagen. Informationen zur Quarantäne finden Sie in den folgenden Themen:

     - [Quarantäne in Office 365](quarantine-email-messages.md)
     - [Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365](manage-quarantined-messages-and-files.md)
     - [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Office 365](find-and-release-quarantined-messages-as-a-user.md)

   - **Diesen X-Header-Text hinzufügen**: Dieses Feld ist nur dann erforderlich und verfügbar, wenn Sie **X-Header hinzufügen** als Aktion für eine Spamfilterbewertung ausgewählt haben. Der von Ihnen angegebene Wert ist der Headerfeld-*Name*, der dem Nachrichtenheader hinzugefügt wird. Der Headerfeld-*Wert* lautet immer `This message appears to be spam`.

     Die maximale Länge beträgt 255 Zeichen, und der Wert darf keine Leerzeichen oder Doppelpunkte (:) enthalten.

     Wenn Sie beispielsweise den Wert `X-This-is-my-custom-header` eingeben, wird der Nachricht der X-Header `X-This-is-my-custom-header: This message appears to be spam.` hinzugefügt.

     Wenn Sie einen Wert eingeben, der Leerzeichen oder Doppelpunkte (:) enthält, wird der eingegebene Wert ignoriert, und der Nachricht wird der standardmäßige X-Header (`X-This-Is-Spam: This message appears to be spam.`) hinzugefügt.

   - **Der Betreffzeile folgenden Text voranstellen**: Dieses Feld ist nur dann erforderlich und verfügbar, wenn Sie **Der Betreffzeile folgenden Text voranstellen** als Aktion für eine Spamfilterbewertung ausgewählt haben. Geben Sie den Text ein, der am Anfang der Betreffzeile der Nachricht hinzugefügt werden soll.

   - **An diese E-Mail-Adresse umleiten**: Dieses Feld ist nur dann erforderlich und verfügbar, wenn Sie **An diese E-Mail-Adresse umleiten** als Aktion für eine Spamfilterbewertung ausgewählt haben. Geben Sie die E-Mail-Adresse ein, an die Sie die Nachricht senden möchten. Mehrere Werte können durch Semikolons (;) getrennt angegeben werden.

   - **Sicherheitstipps**: Standardmäßig sind Sicherheitstipps aktiviert, Sie können sie jedoch deaktivieren, indem Sie das Kontrollkästchen **Ein** deaktivieren. Weitere Informationen zu Sicherheitstipps finden Sie unter [Sicherheitstipps in E-Mail-Nachrichten in Office 365](safety-tips-in-office-365.md).

   Einstellungen für **Automatische Bereinigung zur Nullstunde (ZAP)**: ZAP erkennt Nachrichten, die bereits an Exchange Online-Postfächer übermittelt wurden, und ergreift Maßnahmen für diese. Weitere Informationen zu ZAP finden Sie unter [Automatische Bereinigung zur Nullstunde – Schutz vor Spam und Schadsoftware](zero-hour-auto-purge.md).

   - **Spam-ZAP**: Standardmäßig ist ZAP für Spamerkennungen aktiviert, Sie können es aber deaktivieren, indem Sie das Kontrollkästchen **Ein** deaktivieren.

   - **Phishing-ZAP**: Standardmäßig ist ZAP für Phishingerkennungen aktiviert, Sie können es aber deaktivieren, indem Sie das Kontrollkästchen **Ein** deaktivieren.

5. (Optional) Erweitern Sie den Abschnitt **Zulassungslisten**, um Nachrichtenabsender anhand der E-Mail-Adresse oder der E-Mail-Domäne zu konfigurieren, die die Spamfilterung überspringen dürfen:

   > [!CAUTION]
   > <ul><li>Überlegen Sie es sich genau, bevor Sie hier Domänen hinzufügen. Weitere Informationen finden Sie unter [Erstellen von Listen sicherer Absender in Office 365](create-safe-sender-lists-in-office-365.md).</li><li>Fügen Sie der Liste der zulässigen Domänen niemals akzeptierte Domänen (Domänen, die Sie besitzen) oder allgemeine Domänen (z. B. microsoft.com oder office.com) hinzu. Auf diese Weise könnten Angreifer E-Mails senden, die die Spamfilterung in Ihrer Organisation umgehen.</li></ul>

   - **Absender zulassen**: Klicken Sie auf **Bearbeiten**. Führen Sie im angezeigten Flyout **Liste der zulässigen Absender** Folgendes aus:

      a. Geben Sie die E-Mail-Adresse des Absenders ein. Mehrere E-Mail-Adressen können durch Semikolons (;) getrennt angegeben werden.

      b. Click ![Hinzufügen (Symbol)](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) um die Absender hinzuzufügen.

      Wiederholen Sie diese Schritte so oft wie nötig.

      Die von Ihnen hinzugefügten Absender werden im Flyout im Abschnitt **Zulässiger Absender** angezeigt. Zum Löschen eines Absenders klicken Sie auf ![Entfernen (Symbol)](../../media/scc-remove-icon.png).

      Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - **Domäne zulassen**: Klicken Sie auf **Bearbeiten**. Führen Sie im angezeigten Flyout **Liste zulässiger Domänen** folgende Schritte aus:

      a. Geben Sie die Domäne ein. Mehrere Domänen können durch Semikolons (;) getrennt angegeben werden.

      b. Click ![Hinzufügen (Symbol)](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) um die Domänen hinzuzufügen.

      Wiederholen Sie diese Schritte so oft wie nötig.

      Die von Ihnen hinzugefügten Domänen werden im Flyout im Abschnitt **Zulässige Domäne** angezeigt. Wenn Sie eine Domäne löschen möchten, klicken Sie auf ![Entfernen (Symbol)](../../media/scc-remove-icon.png).

      Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

6. (Optional) Erweitern Sie den Abschnitt **Sperrlisten**, um Nachrichtenabsender nach E-Mail-Adresse oder E-Mail-Domäne zu konfigurieren, die immer als Nachricht mit hoher Spamwahrscheinlichkeit gekennzeichnet werden:

   > [!NOTE]
   > Das manuelle Sperren von Domänen ist nicht gefährlich, kann jedoch zusätzliche Verwaltungsarbeit bedeuten. Weitere Informationen finden Sie unter [Erstellen von Listen blockierter Absender in Office 365](create-block-sender-lists-in-office-365.md).

   - **Absender blockieren**: Klicken Sie auf **Bearbeiten**. Führen Sie im angezeigten Flyout **Liste blockierter Absender** folgende Schritte aus:

      a. Geben Sie die E-Mail-Adresse des Absenders ein. Mehrere E-Mail-Adressen können durch Semikolons (;) getrennt angegeben werden. Platzhalter (*) sind nicht zulässig.

      b. Click ![Hinzufügen (Symbol)](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) um die Absender hinzuzufügen.

      Wiederholen Sie diese Schritte so oft wie nötig.

      Die von Ihnen hinzugefügten Absender werden im Flyout im Abschnitt **Blockierter Absender** angezeigt. Zum Löschen eines Absenders klicken Sie auf ![Schaltfläche „Entfernen“](../../media/scc-remove-icon.png).

      Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - **Domäne blockieren**: Klicken Sie auf **Bearbeiten**. Führen Sie im angezeigten Flyout **Liste blockierter Domänen** Folgendes aus:

      a. Geben Sie die Domäne ein. Mehrere Domänen können durch Semikolons (;) getrennt angegeben werden. Platzhalter (*) sind nicht zulässig.

      b. Click ![Hinzufügen (Symbol)](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) um die Domänen hinzuzufügen.

      Wiederholen Sie diese Schritte so oft wie nötig.

      Die hinzugefügten Domänen werden im Flyout in der Liste **Blockierte Domäne** angezeigt. Wenn Sie eine Domäne löschen möchten, klicken Sie auf ![Schaltfläche „Entfernen“](../../media/scc-remove-icon.png).

      Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

7. (Optional) Erweitern Sie den Abschnitt **Internationale Spamnachrichten**, um die E-Mail-Sprachen bzw. Quellländer zu konfigurieren, die durch Spamfilterung blockiert werden:

   - **E-Mails in den folgenden Sprachen filtern**: Diese Einstellung ist standardmäßig deaktiviert (**Status: AUS**). Klicken Sie auf **Bearbeiten**. Konfigurieren Sie im daraufhin angezeigten Flyout **Internationale Spameinstellungen** die folgenden Einstellungen:

     - **E-Mails in den folgenden Sprachen filtern**: Aktivieren Sie das Kontrollkästchen, um diese Einstellung zu aktivieren. Deaktivieren Sie das Kontrollkästchen, um diese Einstellung zu deaktivieren.

     - Klicken Sie in das Feld *Name*, und beginnen Sie mit der Eingabe des Namens der Sprache. Eine gefilterte Liste der unterstützten Sprachen wird zusammen mit dem entsprechenden ISO 639-2-Sprachcode angezeigt. Wenn Sie die gesuchte Sprache gefunden haben, wählen Sie sie aus. Wiederholen Sie diesen Schritt so oft wie nötig.

       Die Liste der Sprachen, die Sie ausgewählt haben, wird im Flyout angezeigt. Klicken Sie zum Löschen einer Sprache auf ![Schaltfläche "Entfernen"](../../media/scc-remove-icon.png).

     Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - **E-Mails aus den folgenden Ländern oder Regionen filtern**: Diese Einstellung ist standardmäßig deaktiviert (**Status: AUS**). Klicken Sie zum Aktivieren auf **Bearbeiten**. Konfigurieren Sie im daraufhin angezeigten Flyout **Internationale Spameinstellungen** die folgenden Einstellungen:

     - **E-Mails aus den folgenden Ländern oder Regionen filtern**: Aktivieren Sie das Kontrollkästchen, um diese Einstellung zu aktivieren. Deaktivieren Sie das Kontrollkästchen, um diese Einstellung zu deaktivieren.

     - Klicken Sie in das Feld *Name*, und beginnen Sie mit der Eingabe des Namens des Landes oder der Region. Eine gefilterte Liste der unterstützten Länder wird zusammen mit dem entsprechenden aus zwei Buchstaben bestehenden Ländercode nach ISO 3166-1 angezeigt. Wenn Sie das gewünschte Land oder die Region finden, wählen Sie sie aus. Wiederholen Sie diesen Schritt so oft wie nötig.

       Die Liste der Länder, die Sie ausgewählt haben, wird im Flyout angezeigt. Klicken Sie zum Löschen eines Landes oder einer Region auf ![Schaltfläche "Entfernen"](../../media/scc-remove-icon.png).

     Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

8. Der optionale Abschnitt **Spameigenschaften** enthält erweiterte Einstellungen für Spamfilter (Advanced Spam Filter, ASF), die standardmäßig deaktiviert sind. ASF-Einstellungen werden demnächst nicht mehr unterstützt, und ihre Funktionalität wird in andere Teile des Filterstapels übernommen. Wir empfehlen, alle diese ASF-Einstellungen in Ihren Antispamrichtlinien deaktiviert zu lassen.

   Ausführliche Informationen zu diesen Einstellungen finden Sie unter [Einstellungen für erweiterte Spam Filter (ASF) in Office 365](advanced-spam-filtering-asf-options.md).

9. (Erforderlich) Erweitern Sie den Abschnitt **Angewendet auf**, um die internen Empfänger zu identifizieren, auf die die Richtlinie angewendet wird.

    Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

    Um alle verfügbaren Bedingungen anzuzeigen, ist es am einfachsten, wenn Sie auf **Bedingung hinzufügen** klicken. Sie können auf ![Schaltfläche „Entfernen“](../../media/scc-remove-icon.png) klicken, um Bedingungen zu entfernen, die Sie nicht konfigurieren möchten.

    - **Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Office 365 an. Klicken Sie in das Feld **Tag hinzufügen**, um eine Domäne anzuzeigen und auszuwählen. Klicken Sie erneut auf das Feld **Tag hinzufügen**, um weitere Domänen auszuwählen, falls mehrere Domänen verfügbar sind.

    - **Der Empfänger ist**: Gibt ein oder mehrere Postfächer, einen oder mehrere E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation an. Klicken Sie auf **Tag hinzufügen**, und beginnen Sie mit der Eingabe, um die Liste zu filtern. Klicken Sie erneut auf das Feld **Tag hinzufügen**, um weitere Empfänger auszuwählen.

    - **Der Empfänger ist Mitglied von **: Gibt eine oder mehrere Gruppen in Ihrer Organisation an. Klicken Sie auf **Tag hinzufügen**, und beginnen Sie mit der Eingabe, um die Liste zu filtern. Klicken Sie erneut auf das Feld **Tag hinzufügen**, um weitere Empfänger auszuwählen.

    - **Außer wenn**: Klicken Sie zum Angeben von Ausnahmen für die Regel dreimal auf **Bedingung hinzufügen**, um alle verfügbaren Ausnahmen anzuzeigen. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

10. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a>Verwenden des Security & Compliance Centers zum Anzeigen von Antispamrichtlinien

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie auf der Seite **Antispameinstellungen** auf ![Erweitern (Symbol)](../../media/scc-expand-icon.png), um eine Antispamrichtlinie zu erweitern:

   - Die Standardrichtlinie namens **Standard-Spamfilterrichtlinie**.

   - Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei die Spalte **Typ** den Wert **Benutzerdefinierte Antispamrichtlinie** enthält.

3. Die wichtigen Richtlinieneinstellungen werden in den erweiterten Richtliniendetails angezeigt, die eingeblendet werden. Wenn Sie weitere Details anzeigen möchten, klicken Sie auf **Richtlinie bearbeiten**.

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a>Verwenden des Security & Compliance Centers zum Ändern von Antispamrichtlinien

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie auf der Seite **Antispameinstellungen** auf ![Erweitern (Symbol)](../../media/scc-expand-icon.png), um eine Antispamrichtlinie zu erweitern:

   - Die Standardrichtlinie namens **Standard-Spamfilterrichtlinie**.

   - Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei die Spalte **Typ** den Wert **Benutzerdefinierte Antispamrichtlinie** enthält.

3. Klicken Sie auf **Richtlinie bearbeiten**.

Bei benutzerdefinierten Antispamrichtlinien sind die verfügbaren Einstellungen im eingeblendeten Flyout mit denen identisch, die im Abschnitt [Verwenden des Security & Compliance Centers zum Erstellen von Antispamrichtlinien](#use-the-security--compliance-center-to-create-anti-spam-policies) beschrieben sind.

Bei der standardmäßigen Antispamrichtlinie namens **Standard-Spamfilterrichtlinie** ist der Abschnitt **Angewendet auf** nicht verfügbar (die Richtlinie gilt für alle), und Sie können die Richtlinie nicht umbenennen.

Informationen zum Aktivieren oder Deaktivieren einer Richtlinie, zum Festlegen der Prioritätsreihenfolge der Richtlinien oder zum Konfigurieren der Quarantänebenachrichtigungen für Endbenutzer finden Sie in den folgenden Abschnitten.

### <a name="enable-or-disable-anti-spam-policies"></a>Aktivieren oder Deaktivieren von Antispamrichtlinien

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie auf der Seite **Antispameinstellungen** auf ![Erweitern (Symbol)](../../media/scc-expand-icon.png), um eine benutzerdefinierte Richtlinie zu erweitern, die Sie erstellt haben (der Wert in der Spalte **Typ** ist **Benutzerdefinierte Antispamrichtlinie**).

3. Achten Sie in den angezeigten erweiterten Richtliniendetails auf den Wert in der Spalte **Ein**.

   Schieben Sie die Umschaltfläche nach links, um die Richtlinie zu deaktivieren: ![Umschaltfläche aus](../../media/scc-toggle-off.png)

   Schieben Sie die Umschaltfläche nach rechts, um die Richtlinie zu aktivieren: ![Umschaltfläche ein](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

Die Standard-Antispamrichtlinie kann nicht deaktiviert werden.

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>Festlegen der Priorität von benutzerdefinierten Antispamrichtlinien

Standardmäßig erhalten Antispamrichtlinien eine Priorität, die auf der Reihenfolge ihrer Erstellung basiert (neuere Richtlinien haben eine niedrigere Priorität als ältere). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Zwei Richtlinien können nicht dieselbe Priorität haben.

Benutzerdefinierte Antispamrichtlinien werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Priorität**-Wert 0). Die Standard-Antispamrichtlinie namens **Standard-Spamfilterrichtlinie** hat den Prioritätswert **Niedrigste**. Dies kann nicht geändert werden.

 **Hinweis**: Im Security & Compliance Center können Sie die Priorität der Antispamrichtlinie erst nach der Erstellung ändern. In PowerShell können Sie die standardmäßige Priorität bereits beim Erstellen der Spamfilterregel überschreiben (was sich auf die Priorität vorhandener Regeln auswirken kann).

Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Suchen Sie auf der Seite **Antispameinstellungen** nach den Richtlinien, bei denen die Spalte **Typ** den Wert **Benutzerdefinierte Antispamrichtlinie** enthält. Beachten Sie die Werte in der Spalte **Priorität**:

   - Die benutzerdefinierte Antispamrichtlinie mit der höchsten Priorität hat den Wert ![Abwärtspfeil](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - Die benutzerdefinierte Antispamrichtlinie mit der niedrigsten Priorität hat den Wert ![Aufwärtspfeil](../../media/ITPro-EAC-UpArrowIcon.png) **n** (z. B. ![Aufwärtspfeil](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Bei drei oder mehr benutzerdefinierten Antispamrichtlinien haben die Richtlinien zwischen der höchsten und der niedrigsten Priorität die Werte ![Aufwärtspfeil](../../media/ITPro-EAC-UpArrowIcon.png)![Abwärtspfeil](../../media/ITPro-EAC-DownArrowIcon.png) **n** (beispielsweise ![Aufwärtspfeil](../../media/ITPro-EAC-UpArrowIcon.png)![Abwärtspfeil](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. Klicken Sie auf ![Pfeil-nach-oben-Symbol](../../media/ITPro-EAC-UpArrowIcon.png) oder ![Pfeil-nach-unten-Symbol,](../../media/ITPro-EAC-DownArrowIcon.png) um die benutzerdefinierte Antispamrichtlinie nach oben oder nach unten in der Prioritätsliste zu verschieben.

### <a name="configure-end-user-spam-notifications"></a>Konfigurieren von Spambenachrichtigungen für Endbenutzer

Wenn eine Nachricht durch eine Spamfilterbewertung in Quarantäne versetzt wird, können Sie Spambenachrichtigungen für Endbenutzer konfigurieren, damit die Empfänger wissen, was mit Nachrichten passiert ist, die an sie gesendet wurden. Weitere Informationen zu diesen Benachrichtigungen finden Sie unter [Spambenachrichtigungen für Endbenutzer in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie auf der Seite **Antispameinstellungen** auf ![Erweitern (Symbol)](../../media/scc-expand-icon.png), um eine Antispamrichtlinie zu erweitern:

   - Die Standardrichtlinie namens **Standard-Spamfilterrichtlinie**.

   - Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei die Spalte **Typ** den Wert **Benutzerdefinierte Antispamrichtlinie** enthält.

3. Klicken Sie in den angezeigten erweiterten Richtliniendetails auf **Spambenachrichtigungen für Endbenutzer konfigurieren**.

4. Konfigurieren Sie im daraufhin geöffneten Dialogfeld **\<Richtlinienname\>** die folgenden Einstellungen:

   - **Spambenachrichtigungen für Endbenutzer aktivieren**: Aktivieren Sie das Kontrollkästchen, um Benachrichtigungen zu aktivieren. Deaktivieren Sie das Kontrollkästchen, um Benachrichtigungen zu deaktivieren.

   - **Spambenachrichtigungen für Endbenutzer senden alle (Tage)**: Wählen Sie aus, wie häufig Benachrichtigungen gesendet werden. Die Standardeinstellung beträgt 3 Tage. Sie können 1 bis 15 Tage eingeben.
   
     Es gibt 3 Zyklen der Spambenachrichtigung für Endbenutzer innerhalb eines 24-Stunden-Zeitraums, die zu den folgenden Zeiten beginnen: 01:00 UTC, 08:00 UTC und 16:00 UTC. 
    
     > [!NOTE]
     > Wenn eine Benachrichtigung während eines vorherigen Zyklus ausgelassen wurde, wird die Benachrichtigung durch einen nachfolgenden Zyklus per Push gesendet. Dies kann dazu führen, dass mehrere Benachrichtigungen am selben Tag auftreten.

   - **Benachrichtigungssprache**: Klicken Sie auf die Dropdownliste, und wählen Sie eine verfügbare Sprache aus. Der Standardwert ist **Standard**, was bedeutet, dass die Quarantänebenachrichtigungen für Endbenutzer die Standardsprache der EOP-Organisation verwenden.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a>Verwenden des Security & Compliance Centers zum Entfernen von Antispamrichtlinien

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie auf der Seite **Antispameinstellungen** auf ![Erweitern (Symbol)](../../media/scc-expand-icon.png), um eine benutzerdefinierte Richtlinie zu erweitern, die Sie löschen möchten (die Spalte **Typ** enthält den Wert **Benutzerdefinierte Antispamrichtlinie**).

3. Klicken Sie in den angezeigten erweiterten Richtliniendetails auf **Richtlinie löschen**.

4. Klicken Sie im angezeigten Dialogfeld mit der Warnung auf **Ja**.

Die Standardrichtlinie kann nicht entfernt werden.

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-anti-spam-policies"></a>Verwenden von Exchange Online PowerShell oder Exchange Online Protection PowerShell zum Konfigurieren von Antispamrichtlinien

Die folgenden Einstellungen für Antispamrichtlinien sind nur in PowerShell verfügbar:

- Der Parameter _MarkAsSpamBulkMail_, der standardmäßig `On` ist. Die Auswirkungen dieser Einstellung wurden im Abschnitt [Verwenden des Security & Compliance Centers zum Erstellen von Antispamrichtlinien](#use-the-security--compliance-center-to-create-anti-spam-policies) weiter oben in diesem Thema erläutert.

- Die folgenden Einstellungen für Spam-Quarantänebenachrichtigungen für Endbenutzer:

  - Der Parameter _DownloadLink_, der den Link zum Junk-E-Mail-Berichtstool für Outlook anzeigt oder ausblendet.

  - Der Parameter _EndUserSpamNotificationCustomSubject_, den Sie verwenden können, um die Betreffzeile der Benachrichtigung anzupassen.

### <a name="use-powershell-to-create-anti-spam-policies"></a>Verwenden von PowerShell zum Erstellen von Antispamrichtlinien

Das Erstellen einer Antispamrichtlinie in PowerShell ist ein zweistufiger Vorgang:

1. Erstellen Sie die Spamfilterrichtlinie.

2. Erstellen Sie die Spamfilterregel, die die Spamfilterrichtlinie angibt, auf die die Regel angewendet wird.

 **Hinweise**:

- Sie können eine neue Spamfilterregel erstellen und ihr eine vorhandene, nicht zugeordnete Spamfilterrichtlinie zuweisen. Eine Spamfilterregel kann nicht mit mehreren Spamfilterrichtlinien verknüpft werden.

- Sie können die folgenden Einstellungen für neue Spamfilterrichtlinien in PowerShell konfigurieren, die erst dann im Security & Compliance Center verfügbar sind, wenn Sie die Richtlinie erstellt haben:

  - Erstellen Sie die neue Richtlinie als deaktiviert (_Aktiviert_ `$false` im Cmdlet **New-HostedContentFilterRule**).

  - Legen Sie die Priorität der Richtlinie bei der Erstellung fest (_Priority_ _\<Number\>_) im Cmdlet **New-HostedContentFilterRule**).

- Eine neue Spamfilterrichtlinie, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, nachdem Sie die Richtlinie einer Spamfilterregel zugewiesen haben.

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>Schritt 1: Verwenden von PowerShell zum Erstellen einer Spamfilterrichtlinie

Verwenden Sie zum Erstellen einer Spamfilterrichtlinie folgende Syntax:

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In diesem Beispiel wird eine Spamfilterrichtlinie namens Contoso Executives mit den folgenden Einstellungen erstellt:

- Nachrichten werden in Quarantäne gestellt, wenn die Spamfilterbewertung „Spam“ oder „Nachricht mit hoher Spamwahrscheinlichkeit“ lautet.

- BCL 6 löst die Aktion für eine Spamfilterbewertung „Massen-E-Mail“ aus.

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> **New-HostedContentFilterPolicy** und **Set-HostedContentFilterPolicy** enthalten einen älteren _ZapEnabled_-Parameter sowie neuere _PhishZapEnabled_ und _SpamZapEnabled_-Parameter. Der Parameter _ZapEnabled_ gilt seit Februar 2020 als veraltet. Die Parameter _PhishZapEnabled_ und _SpamZapEnabled_ haben bisher ihre Werte aus dem Parameter _ZapEnabled_ geerbt. Wenn Sie aber die Parameter _PhishZapEnabled_ und _SpamZapEnabled_ in einem Befehl verwenden oder wenn Sie die Einstellungen **Spam ZAP** oder **Phish ZAP** in der Antispamrichtlinie im Security & Compliance Center verwenden, wird der Wert des Parameters _ZapEnabled_ ignoriert. Verwenden Sie also nicht den Parameter _ZapEnabled_. Verwenden Sie stattdessen die Parameter _PhishZapEnabled_ und _SpamZapEnabled_.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy).

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterrule).

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterpolicy).

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterrule).

### <a name="use-powershell-to-modify-spam-filter-policies"></a>Verwenden von PowerShell zum Ändern von Spamfilterrichtlinien

Abgesehen von den folgenden Elementen stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Schadsoftware-Filterrichtlinie in PowerShell ändern, wie wenn Sie die Richtlinie wie in Abschnitt [Schritt 1: Verwenden von PowerShell zum Erstellen einer Spamfilterrichtlinie](#step-1-use-powershell-to-create-a-spam-filter-policy) weiter oben in diesem Thema beschrieben erstellen.

- Die Option _MakeDefault_, mit der die angegebene Richtlinie zur Standardrichtlinie erklärt wird (angewendet auf alle, immer **Niedrigste** Priorität, und Sie können sie nicht löschen), steht nur zur Verfügung, wenn Sie eine Spamfilterrichtlinie in PowerShell ändern.

- Sie können eine Spamfilterrichtlinie nicht umbenennen (das Cmdlet **Set-HostedContentFilterPolicy** hat keinen _Name_-Parameter). Wenn Sie eine Antispamrichtlinie im Security & Compliance Center umbenennen, benennen Sie nur die Spamfilter_regel_ um.

Verwenden Sie zum Ändern einer Spamfilterrichtlinie folgende Syntax:

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy).

### <a name="use-powershell-to-modify-spam-filter-rules"></a>Verwenden von PowerShell zum Ändern von Spamfilterregeln

Die einzige Einstellung, die beim Ändern einer Spamfilterregel in PowerShell nicht verfügbar ist, ist der Parameter _Enabled_, mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Spamfilterregeln finden Sie im nächsten Abschnitt.

Ansonsten stehen keine zusätzlichen Einstellungen zur Verfügung, wenn Sie eine Spamfilterregel in PowerShell ändern. Die gleichen Einstellungen stehen zur Verfügung, wenn Sie eine Regel wie im Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen einer Spamfilterregel](#step-2-use-powershell-to-create-a-spam-filter-rule) weiter oben in diesem Thema beschrieben erstellen.

Verwenden Sie zum Ändern einer Spamfilterregel folgende Syntax:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

In diesem Beispiel wird die vorhandene Spamfilterregel namens `{Fabrikam Spam Filter}` umbenannt, die im Security & Compliance Center zu Problemen führen kann.

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule).

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedcontentfilterrule) und [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedcontentfilterrule).

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>Verwenden von PowerShell zum Festlegen der Priorität von Spamfilterregeln

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterpolicy).

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>Senden einer GTUBE-Nachricht, um die Einstellungen für die Spamrichtlinie zu testen

> [!NOTE]
> Diese Schritte funktionieren nur, wenn die E-Mail-Organisation, von der Sie die GTUBE-Nachricht senden, nicht nach ausgehenden Spam-E-Mails sucht. Wenn sie dies tut, kann die Testnachricht nicht gesendet werden.

GTUBE (Generic Test for Unsolicited Bulk Email) ist eine Textzeichenfolge, die Sie in eine Testnachricht einschließen, um die Antispameinstellungen Ihrer Organisation zu überprüfen. Eine GTUBE-Nachricht ähnelt der EICAR-Textdatei (European Institute for Computer Antivirus Research) zum Testen der Schadsoftwareeinstellungen.

Geben Sie den folgenden GTUBE-Text in eine E-Mail in einer Zeile ohne Leerzeichen und Zeilenumbrüche ein:

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a>Zulassungs- und Sperrlisten

Es kann vorkommen, dass eine Nachricht von unseren Filtern übersehen wird, oder dass es einige Zeit dauert, bis sich unsere Systeme darauf einstellen. Für diese Fälle bietet die Antispamrichtlinie Zulassungs- und Sperrlisten, um die aktuelle Bewertung außer Kraft zu setzen. Diese Option sollte sehr sparsam genutzt werden, weil die Verwaltung der Listen mühsam werden kann, und nur vorübergehend, da unser Filter-Stack seinen Zweck normalerweise wie vorgesehen erfüllen sollte.

> [!TIP]
> Es kann vorkommen, dass Ihre Organisation mit einer Bewertung von Seiten des Dienstes nicht einverstanden ist. In diesem Fall können Sie die Zulassungs- bzw. Sperrlisteneinträge dauerhaft beibehalten. Wenn Sie allerdings beabsichtigen, eine Domäne einer Zulassungsliste für längere Zeiträume hinzuzufügen, sollten Sie den Sender bitten, sicherzustellen, dass seine Domäne authentifiziert ist und, falls dies nicht der Fall ist, die DMARC-Option „Ablehnen“ dafür festlegen.
