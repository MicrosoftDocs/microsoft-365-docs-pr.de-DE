---
title: Erstellen von Listen sicherer Absender
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die verfügbaren und bevorzugten Optionen zum Zulassen eingehender Nachrichten in Exchange Online Protection (EOP) informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 92229f0324eb9c05b233e5c4b0bc9f1bd7ab2e39
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165559"
---
# <a name="create-safe-sender-lists-in-eop"></a>Erstellen von Listen sicherer Absender in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Wenn Sie ein Microsoft 365-Kunde mit Postfächern in Exchange Online oder ein eigenständiger Exchange Online Protection (EOP)-Kunde ohne Exchange Online-Postfächer sind, bietet EOP mehrere Möglichkeiten, um sicherzustellen, dass Benutzer E-Mails von vertrauenswürdigen Absendern erhalten. Diese Optionen umfassen Exchange-Nachrichtenflussregeln (auch als Transportregeln bezeichnet), Outlook-sichere Absender, die Liste zugelassener IP-Adressen (Verbindungsfilterung) und Listen zulässiger Absender oder zugelassener Domänen in Antispamrichtlinien. Sie können sich diese Optionen gemeinsam als Listen sicherer _Absender ausdingen._

Die verfügbaren Listen sicherer Absender werden in der folgenden Liste in der Reihenfolge beschrieben, in der sie am wenigsten empfohlen werden:

1. Nachrichtenflussregeln
2. Sichere Absender in Outlook
3. LISTE der zulässigen IP-Adressen (Verbindungsfilterung)
4. Listen zulässiger Absender oder zulässiger Domänen (Antispamrichtlinien)

Nachrichtenflussregeln ermöglichen die größte Flexibilität, um sicherzustellen, dass nur die richtigen Nachrichten zulässig sind. Listen zulässiger Absender und zulässiger Domänen in Antispamrichtlinien sind nicht so sicher wie die LISTE zugelassener IP-Adressen, da die E-Mail-Domäne des Absenders leicht gefälscht werden kann. Die Liste der zulässigen IP-Adressen stellt  jedoch auch ein Risiko dar, da E-Mails von allen Domänen, die von dieser IP-Adresse gesendet werden, die Spamfilterung umgehen.

> [!IMPORTANT]
>
> - Achten Sie darauf, alle *Ausnahmen,* die Sie bei der Spamfilterung mit Listen sicherer Absender machen, genau zu überwachen.
>
> - Obwohl Sie Listen sicherer Absender verwenden können, um falsch positive Ergebnisse zu vermeiden (gute E-Mails sind als schlecht gekennzeichnet), sollten Sie die Verwendung von Listen sicherer Absender als temporäre Lösung in Betracht ziehen, die nach Möglichkeit vermieden werden sollte. Es wird nicht empfohlen, falsch positive Ergebnisse mithilfe von Listen sicherer Absender zu verwalten, da Ausnahmen von der Spamfilterung Ihre Organisation für Spoofing und andere Angriffe öffnen können. Wenn Sie weiterhin Listen sicherer Absender verwenden, um falsch positive Ergebnisse zu verwalten, müssen Sie vorsichtig sein und das Thema "Nachrichten und Dateien an [Microsoft](report-junk-email-messages-to-microsoft.md) melden" bereithalten.
>
> - Damit eine Domäne nicht authentifizierte E-Mails senden kann (Antispoofingschutz umgehen), aber keine Antispam- und Antischsoftwareprüfungen umgehen kann, können Sie sie der Liste der sicheren Absender ["AllowedToSpoof"](walkthrough-spoof-intelligence-insight.md) hinzufügen.
>
> - EOP und Outlook überprüfen verschiedene Nachrichteneigenschaften, um den Absender der Nachricht zu ermitteln. Weitere Informationen finden Sie im Abschnitt ["Überlegungen für Massen-E-Mail"](#considerations-for-bulk-email) weiter unten in diesem Artikel.

Im Gegensatz dazu haben Sie auch mehrere Optionen, um E-Mails aus bestimmten Quellen mithilfe von Listen _blockierter Absender zu blockieren._ Weitere Informationen finden Sie unter [Erstellen von Listen blockierter Absender in EOP](create-block-sender-lists-in-office-365.md).

## <a name="recommended-use-mail-flow-rules"></a>(Empfohlen) Verwenden von Nachrichtenflussregeln

Nachrichtenflussregeln in Exchange Online und EOP als eigenständige Lösung verwenden Bedingungen und Ausnahmen, um Nachrichten zu identifizieren, und Aktionen, um anzugeben, was mit diesen Nachrichten geschehen soll. Weitere Informationen finden Sie unter [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

Im folgenden Beispiel wird davon ausgegangen, dass Sie E-Mails von contoso.com, um die Spamfilterung zu überspringen. Konfigurieren Sie dazu die folgenden Einstellungen:

1. **Bedingung:** **Die** \> **Absenderdomäne ist** \> contoso.com.

2. Konfigurieren Sie eine der folgenden Einstellungen:

   - **Nachrichtenflussregelbedingung:** **Eine Nachrichtenkopfzeile** enthält eines der folgenden Wörter \>  \> **Headername:** `Authentication-Results` \> **Kopfzeilenwert**: `dmarc=pass` oder `dmarc=bestguesspass` .

     Diese Bedingung überprüft den E-Mail-Authentifizierungsstatus der sendenden E-Mail-Domäne, um sicherzustellen, dass die sendende Domäne nicht gefälscht wird. Weitere Informationen zur E-Mail-Authentifizierung finden Sie unter [SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md).

   - **IP Allow List**: Geben Sie die Quell-IP-Adresse oder den Adressbereich in der Verbindungsfilterrichtlinie an.

     Verwenden Sie diese Einstellung, wenn die sendende Domäne keine E-Mail-Authentifizierung verwendet. Geben Sie bei den Quell-IP-Adressen in der Liste der zulässigen IP-Adressen so restriktiv wie möglich vor. Wir empfehlen einen IP-Adressbereich von /24 oder weniger (weniger ist besser). Verwenden Sie keine IP-Adressbereiche, die zu Verbraucherdiensten (z. B. outlook.com) oder gemeinsam genutzten Infrastrukturen gehören.

   > [!IMPORTANT]
   >
   > - Konfigurieren Sie nachrichtenflussregeln niemals *nur* mit der Absenderdomäne als Bedingung, um die Spamfilterung zu überspringen. Dadurch wird  die Wahrscheinlichkeit erheblich erhöht, dass Angreifer die sendende Domäne täuschen (oder die vollständige E-Mail-Adresse imitieren), alle Spamfilter überspringen und Die Absenderauthentifizierungsprüfungen überspringen können, damit die Nachricht im Posteingang des Empfängers eintrifft.
   >
   > - Verwenden Sie keine Domänen, die Sie besitzen (auch als akzeptierte Domänen bezeichnet) oder beliebte Domänen (z. B. microsoft.com) als Bedingungen in Nachrichtenflussregeln. Dies gilt als hohes Risiko, da es Angreifern Möglichkeiten bietet, E-Mails zu senden, die andernfalls gefiltert würden.
   >
   > - Wenn Sie eine IP-Adresse zulassen, die sich hinter einem Netzwerkadressenübersetzungsgateway (Network Address Translation, NAT) befindet, müssen Sie die Server kennen, die am Netzwerkadressenpool beteiligt sind, um den Bereich Ihrer Liste zulässiger IP-Adressen zu kennen. Ip-Adressen und NAT-Teilnehmer können geändert werden. Sie müssen ihre Einträge in der Liste der zulässigen IP-Adressen regelmäßig im Rahmen der standardmäßigen Wartungsverfahren überprüfen.

3. **Optionale Bedingungen:**

   - **Der Absender** \> **intern/extern** \> **Außerhalb der Organisation:** Diese Bedingung ist implizit, aber es ist in Ordnung, damit lokale E-Mail-Server berücksichtigt werden, die möglicherweise nicht ordnungsgemäß konfiguriert sind.

   - **Betreff oder Textkörper** \> **Betreff oder Textkörper enthält eines dieser Wörter** \> : Wenn Sie die Nachrichten durch Schlüsselwörter oder Ausdrücke in der Betreffzeile oder im Nachrichtentext weiter einschränken können, können Sie diese Wörter \<keywords\> als Bedingung verwenden.

4. **Aktion:** Konfigurieren Sie diese beiden Aktionen in der Regel:

   a. **Ändern der Nachrichteneigenschaften** \> **Festlegen der SCL (Spam Confidence Level)** \> **Spamfilter umgehen.**

   b. **Ändern der Nachrichteneigenschaften** \> **Nachrichtenkopf festlegen:** **Nachrichtenkopf auf** \<CustomHeaderName\> **Wert festlegen.** \<CustomHeaderValue\>

      Beispiel: `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Wenn die Regel mehrere Domänen enthält, können Sie den Headertext entsprechend anpassen.

      Wenn eine Nachricht die Spamfilterung aufgrund einer Nachrichtenflussregel überspringt, wird der Wert `SFV:SKN` im **X-Forefront-Antispam-Report-Header gestempelt.** Wenn die Nachricht von einer Quelle stammt, die sich in der Liste der zulässigen IP-Adressen befindet, wird der `IPV:CAL` Wert ebenfalls hinzugefügt. Diese Werte können Ihnen bei der Problembehandlung helfen.

![Nachrichtenflussregeleinstellungen in der EAC zum Umgehen der Spamfilterung.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Verwenden von sicheren Absendern in Outlook

> [!CAUTION]
> Diese Methode stellt ein hohes Risiko dar, dass Angreifer erfolgreich E-Mails an den Posteingang senden, die andernfalls gefiltert würden. Die Listen sicherer Absender oder sicherer Domänen des Benutzers verhindern jedoch nicht, dass Schadsoftware oder Besonders vertrauenswürdige Phishingnachrichten gefiltert werden.

Anstelle einer Organisationseinstellung können Benutzer oder Administratoren die Absender-E-Mail-Adressen der Liste sicherer Absender im Postfach hinzufügen. Anweisungen finden Sie unter ["Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online-Postfächer in Office 365".](configure-junk-email-settings-on-exo-mailboxes.md) Dies ist in den meisten Situationen nicht wünschenswert, da Absender Teile des Filterstapels umgehen. Obwohl Sie dem Absender vertrauen, kann der Absender weiterhin gefährdet sein und schädliche Inhalte senden. Am besten lassen Sie unsere Filter die erforderlichen Maßnahmen zum Überprüfen jeder Nachricht zu und melden dann das falsch [positive/negative](report-junk-email-messages-to-microsoft.md) Ergebnis an Microsoft, wenn unsere Filter falsch sind. Das Umgehen des Filterstapels wirkt sich auch auf [ZAP aus.](zero-hour-auto-purge.md)

Wenn Nachrichten die Spamfilterung aufgrund der Liste sicherer Absender eines Benutzers überspringen, enthält das Kopfzeilenfeld **X-Forefront-Antispam-Report** den Wert, der angibt, dass die Filterung nach `SFV:SFE` Spam, Spoofing und Phishing umgangen wurde.

## <a name="use-the-ip-allow-list"></a>Verwenden der Liste der zulässigen IP-Adressen

Wenn Sie Nachrichtenflussregeln nicht wie zuvor beschrieben verwenden können, besteht die nächste beste Option im Hinzufügen des Quell-E-Mail-Servers oder der Quell-E-Mail-Server zur LISTE der zulässigen IP-Adressen in der Verbindungsfilterrichtlinie. Weitere Informationen finden Sie unter [Konfigurieren der Verbindungsfilterung in EOP](configure-the-connection-filter-policy.md).

**Hinweise**:

- Es ist wichtig, dass Sie die Anzahl der zulässigen IP-Adressen auf ein Minimum beschränken. Vermeiden Sie daher, wann immer möglich, ganze IP-Adressbereiche zu verwenden.

- Verwenden Sie keine IP-Adressbereiche, die zu Verbraucherdiensten (z. B. outlook.com) oder gemeinsam genutzten Infrastrukturen gehören.

- Überprüfen Sie regelmäßig die Einträge in der LISTE der zulässigen IP-Adressen, und entfernen Sie die Einträge, die Sie nicht mehr benötigen.

> [!CAUTION]
> Ohne zusätzliche Überprüfung wie Nachrichtenflussregeln überspringt die E-Mail-Nachricht von Quellen in der Liste der zulässigen IP-Adressen Spamfilterung und Absenderauthentifizierung (SPF, DKIM, DMARC). Dies führt zu einem hohen Risiko, dass Angreifer erfolgreich E-Mails an den Posteingang senden, die andernfalls gefiltert würden. Die Liste der zulässigen IP-Adressen verhindert jedoch nicht, dass Schadsoftware oder Phishingnachrichten mit hoher Confidence gefiltert werden.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Verwenden von Listen zulässiger Absender oder zulässiger Domänen

Die am wenigsten wünschenswerte Option besteht in der Verwendung der Liste zulässiger Absender oder zulässiger Domänen in Antispamrichtlinien. Sie sollten diese  Option nach Möglichkeit vermeiden, da Absender sämtlichen Spam-, Spoof- und Phishingschutz sowie die Absenderauthentifizierung (SPF, DKIM, DMARC) umgehen. Diese Methode eignet sich nur für temporäre Tests. Die detaillierten Schritte finden Sie unter ["Konfigurieren von Antispamrichtlinien" im EOP-Thema.](configure-your-spam-filter-policies.md)

Die maximale Grenze für diese Listen beträgt ca. 1.000 Einträge. Sie können jedoch nur 30 Einträge in das Portal eingeben. Sie müssen PowerShell verwenden, um mehr als 30 Einträge hinzuzufügen.

> [!CAUTION]
>
> - Diese Methode stellt ein hohes Risiko dar, dass Angreifer erfolgreich E-Mails an den Posteingang senden, die andernfalls gefiltert würden. Die Listen der zulässigen Absender oder zulässigen Domänen verhindern jedoch nicht, dass Schadsoftware oder Phishing-Nachrichten mit hoher vertrauenswürdiger Sicherheit gefiltert werden.
>
> - Verwenden Sie keine Domänen, die Sie besitzen (auch als akzeptierte Domänen bezeichnet) oder beliebte Domänen (z. B. microsoft.com) in listen zulässigen Domänen.

## <a name="considerations-for-bulk-email"></a>Überlegungen zu Massen-E-Mails

Eine standardmäßige SMTP-E-Mail besteht aus einem *Nachrichten-Envelope* und dem Nachrichteninhalt. Der Nachrichtenumschlag enthält Informationen, die für die Übermittlung und Übermittlung der Nachricht zwischen den SMTP-Servern erforderlich sind. Der Nachrichteninhalt enthält Nachrichtenkopffelder (zusammenfassend als *Nachrichtenkopf* bezeichnet) sowie den Nachrichtentext. Der Nachrichtenumschlag wird in RFC 5321 beschrieben, und der Nachrichtenkopf wird in RFC 5322 beschrieben. Empfänger sehen den tatsächlichen Nachrichtenumschlag nie, da er vom Nachrichtenübermittlungsprozess generiert wird und nicht tatsächlich Teil der Nachricht ist.

- Die Adresse (auch als `5321.MailFrom` MAIL **FROM-Adresse,** Absender von E-Mails oder Umschlagsender bezeichnet) ist die E-Mail-Adresse, die bei der SMTP-Übermittlung der Nachricht verwendet wird. Diese **E-Mail-Adresse** wird in der Regel im Kopfzeilenfeld "Return-Path" im Nachrichtenkopf aufgezeichnet (obwohl der Absender eine andere **Absender-E-Mail-Adresse** festlegen kann). Wenn die Nachricht nicht zugestellt werden kann, ist dies der Empfänger für den Unzustellbarkeitsbericht (auch als NDR oder Unzustellbarkeitsnachricht bekannt).

- The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.

Häufig sind die `5321.MailFrom` Und-Adressen identisch (Kommunikation von Person `5322.From` zu Person). Wenn E-Mails jedoch im Auftrag einer anderen Person gesendet werden, können die Adressen unterschiedlich sein. Dies geschieht am häufigsten bei Massen-E-Mail-Nachrichten.

Angenommen, Blue Yonder Airlines hat Margie's Travel eingestellt, um E-Mail-Werbung zu senden. Die Nachricht, die Sie in Ihrem Posteingang erhalten, hat die folgenden Eigenschaften:

- Die `5321.MailFrom` Adresse ist blueyonder.airlines@margiestravel.com.

- Die Adresse ist blueyonder@news.blueyonderairlines.com, was in `5322.From` Outlook angezeigt wird.

Listen sicherer Absender und Listen sicherer Domänen in Antispamrichtlinien in EOP überprüfen nur die Adressen. Dies ist mit outlook-sicheren Absendern vergleichbar, die `5322.From` die Adresse `5322.From` verwenden.

Um zu verhindern, dass diese Nachricht gefiltert wird, können Sie die folgenden Schritte ausführen:

- Fügen blueyonder@news.blueyonderairlines.com (die `5322.From` Adresse) als outlooksicherer Absender hinzu.

- [Verwenden Sie eine Nachrichtenflussregel](#recommended-use-mail-flow-rules) mit einer Bedingung, die nach Nachrichten von blueyonder@news.blueyonderairlines.com (adresse, blueyonder.airlines@margiestravel.com (die ) oder `5322.From` `5321.MailFrom` beides sucht.

Weitere Informationen finden Sie unter [Erstellen von Listen sicherer Absender in EOP](create-safe-sender-lists-in-office-365.md).
