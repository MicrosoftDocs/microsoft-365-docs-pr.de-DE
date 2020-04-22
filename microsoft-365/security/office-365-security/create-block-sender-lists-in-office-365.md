---
title: Erstellen von Listen blockierter Absender
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: Administratoren können sich über die verfügbaren Optionen in Microsoft 365 und EOP informieren, um eingehende Nachrichten zu blockieren.
ms.openlocfilehash: 626eff3a1ea28cc16b12acaaa2ba52f7d094a347
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637688"
---
# <a name="create-blocked-sender-lists"></a>Erstellen von Listen blockierter Absender

Wenn Sie ein Microsoft 365-Kunde mit Postfächern in Exchange Online oder ein eigenständiger Exchange Online Schutz (EoP)-Kunde ohne Exchange Online Postfächer sind, bietet EoP mehrere Möglichkeiten zum Blockieren von e-Mails von unerwünschten Absendern. Zu diesen Optionen gehören blockierte Absender in Outlook, blockierte Absenderlisten oder blockierte Domänenlisten in den antispamregeln, Exchange-Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) und die IP-Sperrliste (Verbindungsfilterung). Sie können diese Optionen gemeinsam als _Blockierte Absenderlisten_betrachten.

Die beste Methode zum Blockieren von Absendern variiert im Wirkungsbereich. Für einen einzelnen Benutzer kann es sich bei der richtigen Lösung um von Outlook blockierte Absender handeln. Für viele Benutzer wäre eine der anderen Optionen besser geeignet. Die folgenden Optionen werden sowohl nach Wirkungsbereich als auch in der Breite bewertet. Die Liste wird von schmal zu breit, aber *Lesen Sie die Details* für vollständige Empfehlungen.

1. In Outlook blockierte Absender (die Liste der blockierten Absender, die in jedem Postfach gespeichert ist)

2. Listen blockierter Absender oder blockierter Domänen (Anti-Spam-Richtlinien)

3. Nachrichtenflussregeln

4. Die IP-Sperrliste (Verbindungsfilterung)

> [!NOTE]
> Sie können zwar organisationsweite Block Einstellungen zum Beheben von falsch negativen (verpassten Spam) verwenden, Sie sollten diese Nachrichten jedoch auch zur Analyse an Microsoft übermitteln. Durch das Verwalten von falsch negativen mithilfe von Sperrlisten wird der Verwaltungsaufwand erheblich gesteigert. Wenn Sie Sperrlisten verwenden, um verpasste Spam abzulenken, müssen Sie das Thema [Berichtsmeldungen und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md) weitergeben.

Im Gegensatz dazu können Sie auch mehrere Optionen verwenden, um e-Mails aus bestimmten Quellen mithilfe _sicherer Absenderlisten_immer zuzulassen. Weitere Informationen finden Sie unter [Create Safe Sender lists](create-safe-sender-lists-in-office-365.md).

## <a name="use-outlook-blocked-senders"></a>Verwenden von Outlook-blockierten Absendern

Wenn nur eine kleine Anzahl von Benutzern unerwünschte e-Mails empfangen hat, können Benutzer oder Administratoren die Absender-e-Mail-Adressen der Liste blockierter Absender im Postfach hinzufügen. Anweisungen finden Sie unter [Konfigurieren von Junk-e-Mail-Einstellungen für Exchange Online-Postfächer](configure-junk-email-settings-on-exo-mailboxes.md).

Wenn Nachrichten aufgrund der Liste blockierter Absender eines Benutzers erfolgreich blockiert werden, enthält das Kopfzeilenfeld **X-Forefront-Antispam-Report** den Wert `SFV:BLK`.

> [!NOTE]
> Wenn es sich bei den unerwünschten Nachrichten um Newsletter von einer seriösen und erkennbaren Quelle handelt, ist das kündigen der e-Mail eine weitere Option, um den Empfang der Nachrichten durch den Benutzer zu beenden.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Verwenden blockierter Absenderlisten oder blockierter Domänenlisten

Wenn mehrere Benutzer betroffen sind, ist der Bereich breiter, daher lautet die nächste beste Option "Listen blockierter Absender" oder "Blockierte Domänen" in den Antispam-Richtlinien. Nachrichten von Absendern in den Listen werden als **Spam**gekennzeichnet, und die Aktion, die Sie für das **Spam** Filter-Urteil konfiguriert haben, wird in der Nachricht vorgenommen. Weitere Informationen finden Sie unter [configure Anti-Spam Policies](configure-your-spam-filter-policies.md).

Der maximale Grenzwert für diese Listen beträgt ca. 1000 Einträge.

## <a name="use-mail-flow-rules"></a>Verwenden von Nachrichtenfluss Regeln

Wenn Sie Nachrichten blockieren müssen, die an bestimmte Benutzer oder in der gesamten Organisation gesendet werden, können Sie Nachrichtenfluss Regeln verwenden. Nachrichtenfluss Regeln sind flexibler als Block Absenderlisten oder blockierte Absenderdomänen Listen, da Sie auch nach Stichwörtern oder anderen Eigenschaften in den unerwünschten Nachrichten suchen können.

Unabhängig von den Bedingungen oder Ausnahmen, die Sie zum Identifizieren der Nachrichten verwenden, konfigurieren Sie die Aktion, um die SCL-Bewertung (Spam Confidence Level) der Nachricht auf 9 festzulegen, wodurch die Nachricht als **Spam mit hoher Vertrauens**Würdigkeit gekennzeichnet wird. Weitere Informationen finden Sie unter [Verwenden von Nachrichtenfluss Regeln zum Festlegen der SCL-Bewertung in Nachrichten](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

> [!IMPORTANT]
> Es ist ganz einfach, *übermäßig* aggressive Regeln zu erstellen, daher ist es wichtig, dass Sie nur die Nachrichten identifizieren, die Sie mit ganz bestimmten Kriterien blockieren möchten. Achten Sie außerdem darauf, die Überwachung für die Regel zu aktivieren und die Ergebnisse der Regel zu testen, um sicherzustellen, dass alles wie erwartet funktioniert.

## <a name="use-the-ip-block-list"></a>Verwenden der IP-Sperrliste

Wenn es nicht möglich ist, eine der anderen Optionen zum Blockieren eines Absenders zu verwenden *, sollten Sie* die IP-Sperrliste in der Verbindungsfilter Richtlinie verwenden. Weitere Informationen finden Sie unter [Configure the connection filter policy](configure-the-connection-filter-policy.md). Es ist wichtig, die Anzahl der blockierten IPS auf ein Minimum zu beschränken, sodass die Blockierung ganzer IP-Adressbereiche *nicht* empfohlen wird.

Sie sollten *insbesondere* vermeiden, IP-Adressbereiche hinzuzufügen, die zu Verbraucher Diensten (beispielsweise Outlook.com) oder gemeinsam genutzten Infrastrukturen gehören, und außerdem sicherstellen, dass Sie die Liste blockierter IP-Adressen im Rahmen der regulären Wartung überprüfen.
