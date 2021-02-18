---
title: Erstellen von Listen blockierter Absender
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
description: Administratoren können sich über die verfügbaren und bevorzugten Optionen zum Blockieren eingehender Nachrichten in Exchange Online Protection (EOP) informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5c95b49db811807a0cb46dce5363b8ae2dbe5602
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287281"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Erstellen von Listen blockierter Absender in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer bietet EOP mehrere Möglichkeiten zum Blockieren von E-Mails von unerwünschten Absendern. Diese Optionen umfassen blockierte Absender in Outlook, Listen blockierter Absender oder blockierte Domänen in Antispamrichtlinien, Exchange-Nachrichtenflussregeln (auch als Transportregeln bekannt) und die IP-Sperrliste (Verbindungsfilterung). Zusammen können Sie sich diese Optionen als Listen _blockierter Absender ausdingen._

Die beste Methode zum Blockieren von Absendern hängt vom Wirkungsbereich ab. Für einen einzelnen Benutzer können blockierte Absender in Outlook die richtige Lösung sein. Für viele Benutzer wäre eine der anderen Optionen besser geeignet. Die folgenden Optionen werden nach Wirkungsbereich und Umfang bewertet. Die Liste reicht von schmal bis breit, aber lesen *Sie die Spezifischen,* um vollständige Empfehlungen zu erhalten.

1. Blockierte Absender in Outlook (die Liste blockierter Absender, die in jedem Postfach gespeichert ist)

2. Listen blockierter Absender oder blockierter Domänen (Antispamrichtlinien)

3. Nachrichtenflussregeln

4. Die Liste blockierter IP-Adressen (Verbindungsfilterung)

> [!NOTE]
> Sie können zwar organisationsweite Blockierungseinstellungen verwenden, um falsch negative Ergebnisse (verpasste Spamnachrichten) zu adressieren, sie sollten diese Nachrichten jedoch auch zur Analyse an Microsoft übermitteln. Die Verwaltung falsch negativer Meldungen mithilfe von Sperrlisten erhöht den Verwaltungsaufwand erheblich. Wenn Sie Sperrlisten verwenden, um verpasste Spamnachrichten zu entschärfen, müssen Sie das Thema "Nachrichten und Dateien an [Microsoft](report-junk-email-messages-to-microsoft.md) melden" bereithalten.

Im Gegensatz dazu haben Sie auch mehrere Optionen, um E-Mails aus bestimmten Quellen immer mithilfe von Listen sicherer _Absender zu erlauben._ Weitere Informationen finden Sie unter [Erstellen von Listen sicherer Absender](create-safe-sender-lists-in-office-365.md).

## <a name="email-message-basics"></a>Grundlagen von E-Mail-Nachrichten

Eine standardmäßige SMTP-E-Mail besteht aus einem *Nachrichten-Envelope* und dem Nachrichteninhalt. Der Nachrichtenumschlag enthält Informationen, die für die Übermittlung und Übermittlung der Nachricht zwischen den SMTP-Servern erforderlich sind. Der Nachrichteninhalt enthält Nachrichtenkopffelder (zusammenfassend als *Nachrichtenkopf* bezeichnet) sowie den Nachrichtentext. Der Nachrichtenumschlag wird in RFC 5321 beschrieben, und der Nachrichtenkopf wird in RFC 5322 beschrieben. Empfänger sehen nie den tatsächlichen Nachrichtenumschlag, da er vom Nachrichtenübermittlungsprozess generiert wird und nicht tatsächlich Teil der Nachricht ist.

- Die Adresse (auch als `5321.MailFrom` MAIL **FROM-Adresse,** Absender von E-Mails oder Umschlagsender bezeichnet) ist die E-Mail-Adresse, die bei der SMTP-Übermittlung der Nachricht verwendet wird. Diese E-Mail-Adresse wird in der Regel im Kopfzeilenfeld **"Return-Path"** im Nachrichtenkopf aufgezeichnet (obwohl der Absender eine andere **Absender-E-Mail-Adresse** festlegen kann). Wenn die Nachricht nicht zugestellt werden kann, ist dies der Empfänger für den Unzustellbarkeitsbericht (auch als NDR oder Unzustellbarkeitsnachricht bekannt).

- The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.

Häufig sind die `5321.MailFrom` `5322.From` Und-Adressen identisch (Kommunikation zwischen Personen). Wenn E-Mails jedoch im Auftrag einer anderen Person gesendet werden, können die Adressen unterschiedlich sein.

Listen blockierter Absender und blockierter Domänen in Antispamrichtlinien in EOP überprüfen sowohl die `5321.MailFrom` Adressliste als auch `5322.From` die Adressen. Blockierte Absender von Outlook verwenden nur die `5322.From` Adresse.

## <a name="use-outlook-blocked-senders"></a>Verwenden von blockierten Absendern in Outlook

Wenn nur eine kleine Anzahl von Benutzern unerwünschte E-Mails erhalten hat, können Benutzer oder Administratoren die Absender-E-Mail-Adressen der Liste blockierter Absender im Postfach hinzufügen. Anweisungen finden Sie unter [Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online-Postfächer.](configure-junk-email-settings-on-exo-mailboxes.md)

Wenn Nachrichten aufgrund der Liste blockierter Absender eines Benutzers erfolgreich blockiert werden, enthält das **Kopfzeilenfeld X-Forefront-Antispam-Report** den `SFV:BLK` Wert.

> [!NOTE]
> Wenn es sich bei den unerwünschten Nachrichten um Newsletter aus einer seriösen und wiedererkennbaren Quelle handelt, ist das Abbestellen der E-Mail eine weitere Option, um zu verhindern, dass der Benutzer die Nachrichten empfängt.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Verwenden von Listen blockierter Absender oder blockierter Domänen

Wenn mehrere Benutzer betroffen sind, ist der Bereich breiter, sodass die nächste beste Option blockierte Absenderlisten oder Blockierte Domänenlisten in Antispamrichtlinien sind. Nachrichten von Absendern in den Listen werden als **Spam** gekennzeichnet, und  die Aktion, die Sie für die Spamfilter-Filter-Entscheidung konfiguriert haben, wird für die Nachricht verwendet. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).

Der Höchstwert für diese Listen beträgt ca. 1.000 Einträge.

## <a name="use-mail-flow-rules"></a>Verwenden von Nachrichtenflussregeln

Wenn Sie Nachrichten blockieren müssen, die an bestimmte Benutzer oder die gesamte Organisation gesendet werden, können Sie Nachrichtenflussregeln verwenden. Nachrichtenflussregeln sind flexibler als Listen blockierter Absender oder blockierter Absenderdomänen, da sie auch nach Schlüsselwörtern oder anderen Eigenschaften in den unerwünschten Nachrichten suchen können.

Unabhängig von den Bedingungen oder Ausnahmen, die Sie zum Identifizieren der Nachrichten verwenden, konfigurieren Sie die Aktion, um die SCL (Spam Confidence Level) der Nachricht auf 9 zu setzen, wodurch die Nachricht als Spam mit hoher Confidence markiert **wird.** Weitere Informationen finden Sie unter [Verwenden von Nachrichtenflussregeln zum Festlegen der SCL in Nachrichten.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

> [!IMPORTANT]
> Es ist einfach, Regeln zu erstellen, die zu *aggressiv* sind. Daher ist es wichtig, dass Sie nur die Nachrichten identifizieren, die Sie mithilfe sehr spezifischer Kriterien blockieren möchten. Aktivieren Sie außerdem die Überwachung der Regel, und testen Sie die Ergebnisse der Regel, um sicherzustellen, dass alles wie erwartet funktioniert.

## <a name="use-the-ip-block-list"></a>Verwenden der Liste blockierter IP-Adressen

Wenn es nicht möglich ist, eine der anderen Optionen zum Blockieren eines Absenders zu *verwenden,* sollten Sie nur dann die IP-Sperrliste in der Verbindungsfilterrichtlinie verwenden. Weitere Informationen finden Sie unter [Configure the connection filter policy](configure-the-connection-filter-policy.md). Es ist wichtig, die Anzahl der blockierten IPs auf ein Minimum zu beschränken, daher wird das Blockieren ganzer IP-Adressbereiche *nicht* empfohlen.

Sie  sollten insbesondere das Hinzufügen von IP-Adressbereichen vermeiden, die zu Verbraucherdiensten (z. B. outlook.com) oder gemeinsam genutzten Infrastrukturen gehören, und außerdem sicherstellen, dass Sie die Liste der blockierten IP-Adressen im Rahmen der regelmäßigen Wartung überprüfen.
