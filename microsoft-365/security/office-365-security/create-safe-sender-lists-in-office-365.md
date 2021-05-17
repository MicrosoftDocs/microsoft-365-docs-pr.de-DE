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
description: Administratoren können sich über die verfügbaren und bevorzugten Optionen informieren, um eingehende Nachrichten in Exchange Online Protection (EOP) zu ermöglichen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5473f8c37b4edcf6c2451cf995b430edbe09533
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205987"
---
# <a name="create-safe-sender-lists-in-eop"></a>Erstellen von Listen sicherer Absender in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Wenn Sie ein Microsoft 365-Kunde mit Postfächern in Exchange Online oder ein eigenständiger Exchange Online Protection (EOP)-Kunde ohne Exchange Online-Postfächer sind, bietet EOP mehrere Möglichkeiten, um sicherzustellen, dass Benutzer E-Mails von vertrauenswürdigen Absendern empfangen. Diese Optionen umfassen Exchange Nachrichtenflussregeln (auch als Transportregeln bezeichnet), Outlook Sichere Absender, die IP-Zugelassene Liste (Verbindungsfilterung) und zugelassene Absenderlisten oder zulässige Domänenlisten in Antispamrichtlinien. Zusammen können Sie diese Optionen als Listen sicherer _Absender sehen._

Die verfügbaren Listen sicherer Absender werden in der folgenden Liste in der Reihenfolge der am meisten empfohlenen bis am wenigsten empfohlenen beschrieben:

1. Nachrichtenflussregeln
2. Outlook Sichere Absender
3. IP-Zulässige Liste (Verbindungsfilterung)
4. Zugelassene Absenderlisten oder zulässige Domänenlisten (Antispamrichtlinien)

Nachrichtenflussregeln ermöglichen die größte Flexibilität, um sicherzustellen, dass nur die richtigen Nachrichten zulässig sind. Zugelassene Absender- und zulässige Domänenlisten in Antispamrichtlinien sind nicht so sicher wie die IP-Zugelassene Liste, da die E-Mail-Domäne des Absenders leicht gefälscht werden kann. Die Liste der zulässigen IP-Adressen stellt  jedoch auch ein Risiko dar, da E-Mails von einer beliebigen Domäne, die von dieser IP-Adresse gesendet wird, die Spamfilterung umgehen.

> [!IMPORTANT]
>
> - Achten Sie darauf, alle *Ausnahmen,* die Sie bei der Spamfilterung mit Listen sicherer Absender treffen, genau zu überwachen.
>
> - Obwohl Sie Listen sicherer Absender verwenden können, um falsch positive Ergebnisse zu vermeiden (gute E-Mails sind als schlecht gekennzeichnet), sollten Sie die Verwendung von Listen sicherer Absender als temporäre Lösung betrachten, die nach Möglichkeit vermieden werden sollte. Es wird nicht empfohlen, falsch positive Ergebnisse mithilfe von Listen sicherer Absender zu verwalten, da Ausnahmen von der Spamfilterung Ihre Organisation für Spoofing und andere Angriffe öffnen können. Wenn Sie darauf bestehen, Listen sicherer Absender zu verwenden, um falsch positive Ergebnisse zu verwalten, müssen Sie aufmerksam sein und das Thema Nachrichten und Dateien an [Microsoft](report-junk-email-messages-to-microsoft.md) melden bereit halten.
>
> - Damit eine Domäne nicht authentifizierte E-Mails senden kann (Anti-Spoofing-Schutz umgehen), aber keine Antispam- und Schadsoftwareprüfungen umgehen, können Sie sie der [Liste "AllowedToSpoof safe sender" hinzufügen.](walkthrough-spoof-intelligence-insight.md)
>
> - EOP und Outlook verschiedene Nachrichteneigenschaften überprüfen, um den Absender der Nachricht zu ermitteln. Weitere Informationen finden Sie im [Abschnitt Überlegungen für Massen-E-Mails](#considerations-for-bulk-email) weiter unten in diesem Artikel.

Im Gegensatz dazu haben Sie auch mehrere Optionen, um E-Mails von bestimmten Quellen mithilfe blockierter _Absenderlisten zu blockieren._ Weitere Informationen finden Sie unter [Erstellen von Listen blockierter Absender in EOP](create-block-sender-lists-in-office-365.md).

## <a name="recommended-use-mail-flow-rules"></a>(Empfohlen) Verwenden von Nachrichtenflussregeln

Nachrichtenflussregeln in Exchange Online und eigenständigen EOP verwenden Bedingungen und Ausnahmen, um Nachrichten zu identifizieren, und Aktionen, um anzugeben, was mit diesen Nachrichten geschehen soll. Weitere Informationen finden Sie unter [Mail flow rules (transport rules) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

Im folgenden Beispiel wird davon ausgegangen, dass Sie E-Mails von contoso.com zum Überspringen der Spamfilterung benötigen. Konfigurieren Sie dazu die folgenden Einstellungen:

1. **Bedingung:** **Die** \> **Absenderdomäne ist** \> contoso.com.

2. Konfigurieren Sie eine der folgenden Einstellungen:

   - **Bedingung der Nachrichtenflussregel:** **Ein Nachrichtenkopf** enthält eines der folgenden Wörter \>  \> **Headername**: `Authentication-Results` \> **Headerwert**: `dmarc=pass` oder `dmarc=bestguesspass` .

     Diese Bedingung überprüft den E-Mail-Authentifizierungsstatus der sendenden E-Mail-Domäne, um sicherzustellen, dass die sendende Domäne nicht gefälscht wird. Weitere Informationen zur E-Mail-Authentifizierung finden Sie unter [SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md).

   - **IP-Zulässige Liste**: Geben Sie die Quell-IP-Adresse oder den Adressbereich in der Verbindungsfilterrichtlinie an.

     Verwenden Sie diese Einstellung, wenn die sendende Domäne keine E-Mail-Authentifizierung verwendet. Machen Sie sich so restriktiv wie möglich, wenn es um die Quell-IP-Adressen in der LISTE der zulässigen IP-Adressen geht. Wir empfehlen einen IP-Adressbereich von /24 oder weniger (weniger ist besser). Verwenden Sie keine IP-Adressbereiche, die zu Verbraucherdiensten (z. B. outlook.com) oder gemeinsam genutzten Infrastrukturen gehören.

   > [!IMPORTANT]
   >
   > - Konfigurieren Sie niemals Nachrichtenflussregeln mit *nur* der Absenderdomäne als Bedingung zum Überspringen der Spamfilterung. Dadurch erhöht  sich die Wahrscheinlichkeit, dass Angreifer die sendende Domäne spoofen (oder die vollständige E-Mail-Adresse imitieren), alle Spamfilter überspringen und Absenderauthentifizierungsprüfungen überspringen können, damit die Nachricht im Posteingang des Empfängers eintrifft.
   >
   > - Verwenden Sie keine Domänen, die Sie besitzen (auch als akzeptierte Domänen bezeichnet) oder beliebte Domänen (z. B. microsoft.com) als Bedingungen in Nachrichtenflussregeln. Dies gilt als hohes Risiko, da angreifern die Möglichkeit eröffnet wird, E-Mails zu senden, die andernfalls gefiltert würden.
   >
   > - Wenn Sie eine IP-Adresse zulassen, die sich hinter einem Nat-Gateway (Network Address Translation, Netzwerkadressenübersetzung) befindet, müssen Sie die Server kennen, die am NAT-Pool beteiligt sind, um den Umfang Ihrer IP-Zulässigen Liste zu kennen. IP-Adressen und NAT-Teilnehmer können sich ändern. Sie müssen ihre Einträge in der Liste der zulässigen IP-Adressen im Rahmen Ihrer standardmäßigen Wartungsprozeduren regelmäßig überprüfen.

3. **Optionale Bedingungen**:

   - **Der Absender** \> **ist intern/extern** \> **Außerhalb der Organisation:** Diese Bedingung ist implizit, aber es ist in Ordnung, sie für lokale E-Mail-Server zu verwenden, die möglicherweise nicht ordnungsgemäß konfiguriert sind.

   - **Betreff oder Textkörper** \> **Betreff oder Textkörper enthält eines dieser Wörter** \> : Wenn Sie die Nachrichten durch Schlüsselwörter oder Ausdrücke in der Betreffzeile oder dem Nachrichtentext weiter einschränken können, können Sie diese \<keywords\> Wörter als Bedingung verwenden.

4. **Aktion**: Konfigurieren Sie beide dieser Aktionen in der Regel:

   a. **Ändern der Nachrichteneigenschaften** \> **Festlegen der Spamsicherheitsstufe (Spam Confidence Level, SCL)** \> **Umgehen der Spamfilterung**.

   b. **Ändern der Nachrichteneigenschaften** \> **Festlegen einer Nachrichtenkopfzeile**: **Legen Sie den Nachrichtenkopf** \<CustomHeaderName\> **auf den Wert .** \<CustomHeaderValue\>

      Beispiel: `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Wenn die Regel mehrere Domänen enthält, können Sie den Kopfzeilentext entsprechend anpassen.

      Wenn eine Nachricht die Spamfilterung aufgrund einer Nachrichtenflussregel überspringt, wird der Wert `SFV:SKN` im **X-Forefront-Antispam-Report-Header** gestempelt. Wenn die Nachricht von einer Quelle stammt, die sich in der Liste der zulässigen IP-Adressen befindet, wird der `IPV:CAL` Wert ebenfalls hinzugefügt. Diese Werte können Ihnen bei der Problembehandlung helfen.

![Nachrichtenflussregeleinstellungen in der EAC zum Umgehen der Spamfilterung.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Verwenden Outlook sicherer Absender

> [!CAUTION]
> Diese Methode führt zu einem hohen Risiko, dass Angreifer erfolgreich E-Mails an den Posteingang senden, die andernfalls gefiltert würden. Die Listen sicherer Absender oder sicherer Domänen des Benutzers verhindern jedoch nicht, dass Schadsoftware oder Phishingnachrichten mit hoher Sicherheit gefiltert werden.

Anstelle einer Organisationseinstellung können Benutzer oder Administratoren die Absender-E-Mail-Adressen der Liste sicherer Absender im Postfach hinzufügen. Anweisungen finden Sie unter [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md). Dies ist in den meisten Situationen nicht wünschenswert, da Absender Teile des Filterstapels umgehen. Obwohl Sie dem Absender vertrauen, kann der Absender weiterhin gefährdet sein und schädliche Inhalte senden. Es ist am besten, dass Sie unsere Filter das tun lassen, was erforderlich ist, um jede Nachricht zu überprüfen und dann das falsch [positive/negative](report-junk-email-messages-to-microsoft.md) Ergebnis an Microsoft zu melden, wenn unsere Filter dies falsch gemacht haben. Das Umgehen des Filterstapels wirkt sich auch auf [ZAP aus.](zero-hour-auto-purge.md)

Wenn Nachrichten die Spamfilterung aufgrund der Liste sicherer Absender eines Benutzers überspringen, enthält das Kopfzeilenfeld **X-Forefront-Antispam-Report** den Wert , der angibt, dass die Filterung nach Spam, Spoof und Phishing umgangen `SFV:SFE` wurde.

## <a name="use-the-ip-allow-list"></a>Verwenden der Liste der zulässigen IP-Adressen

Wenn Sie nachrichtenflussregeln nicht wie zuvor beschrieben verwenden können, besteht die nächste beste Option in der Verbindungsfilterrichtlinie, den Quell-E-Mail-Server oder -Server der IP-Zulässigen Liste hinzuzufügen. Weitere Informationen finden Sie unter [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).

**Hinweise**:

- Es ist wichtig, dass Sie die Anzahl der zulässigen IP-Adressen auf ein Minimum beschränken. Vermeiden Sie daher, wann immer möglich, ganze IP-Adressbereiche zu verwenden.

- Verwenden Sie keine IP-Adressbereiche, die zu Verbraucherdiensten (z. B. outlook.com) oder gemeinsam genutzten Infrastrukturen gehören.

- Überprüfen Sie regelmäßig die Einträge in der Liste der zulässigen IP-Adressen, und entfernen Sie die Einträge, die Sie nicht mehr benötigen.

> [!CAUTION]
> Ohne zusätzliche Überprüfung wie Nachrichtenflussregeln überspringt E-Mails von Quellen in der LISTE der zulässigen IP-Adressen die Spamfilterung und die Absenderauthentifizierung (SPF, DKIM, DMARC). Dies führt zu einem hohen Risiko, dass Angreifer erfolgreich E-Mails an den Posteingang senden, die andernfalls gefiltert würden. Die Liste der zulässigen IP-Adressen verhindert jedoch nicht, dass Schadsoftware oder Phishingnachrichten mit hoher Vertrauenssicherheit gefiltert werden.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Verwenden zulässiger Absenderlisten oder zulässiger Domänenlisten

Die am wenigsten wünschenswerte Option ist die Verwendung der Liste der zulässigen Absender oder der zulässigen Domänen in Antispamrichtlinien. Sie sollten diese  Option nach Möglichkeit vermeiden, da Absender alle Spam-, Spoof- und Phishingschutz- und Absenderauthentifizierung (SPF, DKIM, DMARC) umgehen. Diese Methode eignet sich nur für temporäre Tests. Die detaillierten Schritte finden Sie unter [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md) topic.

Die maximale Grenze für diese Listen beträgt ca. 1.000 Einträge. Sie können jedoch nur 30 Einträge in das Portal eingeben. Sie müssen PowerShell verwenden, um mehr als 30 Einträge hinzuzufügen.

> [!CAUTION]
>
> - Diese Methode führt zu einem hohen Risiko, dass Angreifer erfolgreich E-Mails an den Posteingang senden, die andernfalls gefiltert würden. Die Liste der zulässigen Absender oder zulässigen Domänen verhindert jedoch nicht, dass Schadsoftware oder Phishingnachrichten mit hoher Vertrauen gefiltert werden.
>
> - Verwenden Sie keine Domänen, die Sie besitzen (auch als akzeptierte Domänen bezeichnet) oder beliebte Domänen (z. B. microsoft.com) in zulässigen Domänenlisten.

## <a name="considerations-for-bulk-email"></a>Überlegungen zu Massen-E-Mails

Eine standardmäßige SMTP-E-Mail besteht aus einem *Nachrichten-Envelope* und dem Nachrichteninhalt. Der Nachrichtenumschlag enthält Informationen, die für die Übertragung und Übermittlung der Nachricht zwischen SMTP-Servern erforderlich sind. Der Nachrichteninhalt enthält Nachrichtenkopffelder (zusammenfassend als *Nachrichtenkopf* bezeichnet) sowie den Nachrichtentext. Der Nachrichtenumschlag wird in RFC 5321 beschrieben, und der Nachrichtenkopf wird in RFC 5322 beschrieben. Empfänger sehen nie den tatsächlichen Nachrichtenumschlag, da er durch den Nachrichtenübermittlungsprozess generiert wird und nicht teil der Nachricht ist.

- Die Adresse (auch bekannt `5321.MailFrom` als MAIL **FROM-Adresse,** P1-Absender oder Umschlagsender) ist die E-Mail-Adresse, die bei der SMTP-Übertragung der Nachricht verwendet wird. Diese **E-Mail-Adresse** wird in der Regel im Kopfzeilenfeld Return-Path im Nachrichtenkopf aufgezeichnet (obwohl der Absender eine andere **Return-Path-E-Mail-Adresse** festlegen kann). Wenn die Nachricht nicht zugestellt werden kann, ist sie der Empfänger für den Unzustellbarkeitsbericht (auch als Unzustellbarkeitsbericht oder Unzustellbarkeitsnachricht bekannt).

- The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.

Häufig sind die Adressen und die Adressen identisch (Kommunikation zwischen `5321.MailFrom` `5322.From` Personen). Wenn E-Mails jedoch im Auftrag einer anderen Person gesendet werden, können die Adressen unterschiedlich sein. Dies geschieht am häufigsten bei Massen-E-Mail-Nachrichten.

Angenommen, Blue Yonder Airlines hat Margie's Travel für das Senden seiner E-Mail-Werbung eingestellt. Die Nachricht, die Sie in Ihrem Posteingang erhalten, hat die folgenden Eigenschaften:

- Die `5321.MailFrom` Adresse ist blueyonder.airlines@margiestravel.com.

- Die Adresse ist blueyonder@news.blueyonderairlines.com, was sie in der `5322.From` Outlook.

Listen sicherer Absender und listen sicherer Domänen in Antispamrichtlinien in EOP überprüfen nur die Adressen. Dies ähnelt Outlook sicheren Absendern, die die Adresse `5322.From` `5322.From` verwenden.

Um zu verhindern, dass diese Nachricht gefiltert wird, können Sie die folgenden Schritte ausführen:

- Fügen blueyonder@news.blueyonderairlines.com (die `5322.From` Adresse) als sicherer Outlook hinzu.

- [Verwenden Sie eine Nachrichtenflussregel](#recommended-use-mail-flow-rules) mit einer Bedingung, die nach Nachrichten von blueyonder@news.blueyonderairlines.com (adresse, `5322.From` blueyonder.airlines@margiestravel.com ( ) oder `5321.MailFrom` beides sucht.

Weitere Informationen finden Sie unter [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).