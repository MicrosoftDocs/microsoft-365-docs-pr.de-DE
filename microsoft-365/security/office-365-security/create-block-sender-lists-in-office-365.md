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
description: Administratoren können sich über die verfügbaren und bevorzugten Optionen zum Blockieren eingehender Nachrichten in EOP Exchange Online Protection (EOP) informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c844378a19ba7995cbd616f615e8a84994f9bf26
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624082"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Erstellen blockierter Absenderlisten in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer bietet EOP mehrere Möglichkeiten, E-Mails von unerwünschten Absendern zu blockieren. Diese Optionen umfassen Outlook blockierte Absender, blockierte Absenderlisten oder blockierte Domänenlisten in Antispamrichtlinien, Exchange Nachrichtenflussregeln (auch als Transportregeln bekannt) und die IP-Sperrliste (Verbindungsfilterung). Zusammen können Sie diese Optionen als blockierte _Absenderlisten sehen._

Die beste Methode zum Blockieren von Absendern variiert je nach Wirkungsbereich. Für einen einzelnen Benutzer könnte die richtige Lösung Outlook Blockierte Absender sein. Für viele Benutzer wäre eine der anderen Optionen geeigneter. Die folgenden Optionen werden nach Wirkungsbereich und Breite bewertet. Die Liste geht von schmal zu breit, aber lesen *Sie die Spezifischen* für vollständige Empfehlungen.

1. Outlook Blockierte Absender (die Liste blockierter Absender, die in jedem Postfach gespeichert ist)

2. Blockierte Absenderlisten oder blockierte Domänenlisten (Antispamrichtlinien)

3. Nachrichtenflussregeln

4. Die IP-Sperrliste (Verbindungsfilterung)

> [!NOTE]
> Sie können zwar organisationsweite Blockeinstellungen verwenden, um falsch negative Negative (verpasster Spam) zu adressieren, sie sollten diese Nachrichten jedoch auch zur Analyse an Microsoft übermitteln. Die Verwaltung falsch negativer Werte mithilfe von Sperrlisten erhöht den Verwaltungsaufwand erheblich. Wenn Sie Sperrlisten verwenden, um verpassten Spam zu verhindern, müssen Sie das Thema Nachrichten und Dateien an [Microsoft](report-junk-email-messages-to-microsoft.md) melden bereithalten.

Im Gegensatz dazu haben Sie auch mehrere Optionen, um E-Mails von bestimmten Quellen mit Listen sicherer _Absender immer zu erlauben._ Weitere Informationen finden Sie unter [Erstellen von Listen sicherer Absender](create-safe-sender-lists-in-office-365.md).

## <a name="email-message-basics"></a>Grundlagen für E-Mail-Nachrichten

Eine standardmäßige SMTP-E-Mail besteht aus einem *Nachrichten-Envelope* und dem Nachrichteninhalt. Der Nachrichtenumschlag enthält Informationen, die für die Übertragung und Übermittlung der Nachricht zwischen SMTP-Servern erforderlich sind. Der Nachrichteninhalt enthält Nachrichtenkopffelder (zusammenfassend als *Nachrichtenkopf* bezeichnet) sowie den Nachrichtentext. Der Nachrichtenumschlag wird in RFC 5321 beschrieben, und der Nachrichtenkopf wird in RFC 5322 beschrieben. Empfänger sehen nie den tatsächlichen Nachrichtenumschlag, da er durch den Nachrichtenübermittlungsprozess generiert wird und nicht teil der Nachricht ist.

- Die Adresse (auch bekannt `5321.MailFrom` als MAIL **FROM-Adresse,** P1-Absender oder Umschlagsender) ist die E-Mail-Adresse, die bei der SMTP-Übertragung der Nachricht verwendet wird. Diese **E-Mail-Adresse** wird in der Regel im Kopfzeilenfeld Return-Path im Nachrichtenkopf aufgezeichnet (obwohl der Absender eine andere **Return-Path-E-Mail-Adresse** festlegen kann). Wenn die Nachricht nicht zugestellt werden kann, ist sie der Empfänger für den Unzustellbarkeitsbericht (auch als Unzustellbarkeitsbericht oder Unzustellbarkeitsnachricht bekannt).

- The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.

Häufig sind die Adressen und die Adressen identisch (Kommunikation zwischen `5321.MailFrom` `5322.From` Personen). Wenn E-Mails jedoch im Auftrag einer anderen Person gesendet werden, können die Adressen unterschiedlich sein.

Blockierte Absenderlisten und blockierte Domänenlisten in Antispamrichtlinien in EOP überprüfen sowohl die Adressen `5321.MailFrom` als auch `5322.From` die Adressen. Outlook Blockierte Absender verwenden nur die `5322.From` Adresse.

## <a name="use-outlook-blocked-senders"></a>Verwenden Outlook blockierter Absender

Wenn nur eine kleine Anzahl von Benutzern unerwünschte E-Mails empfangen hat, können Benutzer oder Administratoren die Absender-E-Mail-Adressen der Liste blockierter Absender im Postfach hinzufügen. Anweisungen finden Sie unter [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).

Wenn Nachrichten aufgrund der Liste blockierter Absender eines Benutzers erfolgreich blockiert werden, enthält das **Kopfzeilenfeld X-Forefront-Antispam-Report** den Wert `SFV:BLK` .

> [!NOTE]
> Wenn es sich bei den unerwünschten Nachrichten um Newsletter aus einer seriösen und wiedererkennbaren Quelle handelt, ist das Deaktivieren der E-Mail eine weitere Option, um den Benutzer am Empfang der Nachrichten zu stoppen.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Verwenden blockierter Absenderlisten oder blockierter Domänenlisten

Wenn mehrere Benutzer betroffen sind, ist der Bereich breiter, sodass die nächste beste Option blockierte Absenderlisten oder blockierte Domänenlisten in Antispamrichtlinien sind. Nachrichten von Absendern in den Listen werden als Spam mit hoher Vertrauenssicherheit **gekennzeichnet,** und die Aktion, die Sie für das Spamfilter-Filter-Urteil mit hoher Sicherheit konfiguriert haben, wird für die Nachricht verwendet.  Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).

Die maximale Grenze für diese Listen beträgt ca. 1.000 Einträge.

## <a name="use-mail-flow-rules"></a>Verwenden von Nachrichtenflussregeln

Wenn Sie Nachrichten blockieren müssen, die an bestimmte Benutzer oder die gesamte Organisation gesendet werden, können Sie Nachrichtenflussregeln verwenden. Nachrichtenflussregeln sind flexibler als Blockierung von Absenderlisten oder blockierten Absenderdomänenlisten, da sie auch nach Schlüsselwörtern oder anderen Eigenschaften in den unerwünschten Nachrichten suchen können.

Unabhängig von den Bedingungen oder Ausnahmen, die Sie zum Identifizieren der Nachrichten verwenden, konfigurieren Sie die Aktion so, dass die Spamsicherheitsstufe (Spam Confidence Level, SCL) der Nachricht auf 9 festgelegt wird, wodurch die Nachricht als Spam mit hoher Sicherheit markiert **wird.** Weitere Informationen finden Sie unter [Verwenden von Nachrichtenflussregeln zum Festlegen der SCL in Nachrichten](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

> [!IMPORTANT]
> Es ist einfach, Regeln zu erstellen, die zu *aggressiv* sind. Daher ist es wichtig, dass Sie nur die Nachrichten identifizieren, die Sie blockieren möchten, indem Sie ganz bestimmte Kriterien verwenden. Aktivieren Sie außerdem die Überwachung der Regel, und testen Sie die Ergebnisse der Regel, um sicherzustellen, dass alles wie erwartet funktioniert.

## <a name="use-the-ip-block-list"></a>Verwenden der IP-Sperrliste

Wenn es nicht möglich ist, eine der anderen Optionen zum Blockieren eines Absenders zu *verwenden,* sollten Sie nur dann die IP-Sperrliste in der Verbindungsfilterrichtlinie verwenden. Weitere Informationen finden Sie unter [Configure the connection filter policy](configure-the-connection-filter-policy.md). Es ist wichtig, die Anzahl blockierter IPs auf ein Minimum zu beschränken, daher wird das Blockieren ganzer IP-Adressbereiche *nicht* empfohlen.

Sie  sollten insbesondere das Hinzufügen von IP-Adressbereichen vermeiden, die zu Verbraucherdiensten (z. B. outlook.com) oder gemeinsam genutzten Infrastrukturen gehören, und außerdem sicherstellen, dass Sie die Liste der blockierten IP-Adressen im Rahmen der regelmäßigen Wartung überprüfen.
