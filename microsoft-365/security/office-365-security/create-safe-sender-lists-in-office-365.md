---
title: Erstellen sicherer Absenderlisten in Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 4/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: Wenn Sie sicherstellen möchten, dass Sie e-Mails von einem bestimmten Absender empfangen, da Sie diesen und ihren Nachrichten Vertrauen, können Sie die Zulassungsliste in einer Spamfilter Richtlinie anpassen.
ms.openlocfilehash: 727c0eec837627bdf7da05411f619f7705425fe7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083433"
---
# <a name="create-safe-sender-lists-in-office-365"></a>Erstellen sicherer Absenderlisten in Office 365

Wenn Sie sicherstellen möchten, dass Benutzer e-Mails von einem bestimmten Absender oder Absender empfangen, weil Sie Ihnen und ihren Nachrichten Vertrauen, stehen Ihnen mehrere Methoden zur Verfügung, aus denen Sie auswählen können. Zu diesen Optionen gehören Exchange-Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet), Outlook-sichere Absender, IP-Zulassungslisten, Absender-und Domänen Zulassungslisten für Spam Schutz.

> [!IMPORTANT]
> Zwar können Organisations Zulassungslisten verwendet werden, um falsch positive Ergebnisse zu beheben, dies sollte jedoch als vorübergehende Lösung betrachtet und nach Möglichkeit vermieden werden. Die Verwaltung von falsch positiven Ergebnissen mithilfe von Zulassungslisten wird nicht empfohlen, da Sie Ihre Organisation versehentlich bis hin zu Spoofing, Identitätswechsel und anderen Angriffen öffnen kann. Wenn Sie für diesen Zweck eine Zulassungsliste verwenden, müssen Sie wachsam sein und den Artikel zum [Senden von Spam-, nicht-Spam-und Phishing-Mails an Microsoft zur Analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)parat halten.

Die empfohlene Methode zum Konfigurieren einer Liste sicherer Absender ist die Verwendung von Nachrichtenfluss Regeln, da dies die meiste Flexibilität bietet, um sicherzustellen, dass nur die richtigen Nachrichten zugelassen werden. Die e-Mail-Adresse und *domänenbasierte Zulassungslisten* für *Anti-Spam-Richtlinien* sind nicht so sicher wie *IP-Adress basierte Listen* , da Domänen einfach gefälscht werden können. Aber auch die IP-basierten Listen für Anti-Spam-Richtlinien stellen Risiken dar, da Sie es allen Domänen ermöglichen, die über diese IP gesendet werden, um die Spamfilterung zu umgehen. Achten Sie darauf, dass *alle* getroffenen Ausnahmen sorgfältig überwacht werden.

> [!IMPORTANT]
> • Informationen zum Erstellen einer **Liste blockierter Absender** finden Sie [hier](create-block-sender-lists-in-office-365.md). <br/><br/> • Wenn Sie zulassen möchten, dass eine Absenderdomäne nicht authentifizierte e-Mails sendet (Schutz vor Spoofing schützt), aber keine Anti-Spam-und Anti-Malware-Überprüfungen umgeht, können Sie Sie der [Liste sicherer Absender von AllowedToSpoof](walkthrough-spoof-intelligence-insight.md)hinzufügen.

## <a name="options-from-most-to-least-recommended"></a>Optionen von den meisten zu den am wenigsten empfohlenen

Sie sollten ihre Zulassungslisten immer einschränken, da Sie viele Sicherheitsmaßnahmen umgehen. Sie müssen alle Zulassungslisten als Bestandteil ihrer Standardwartung erneut überprüfen, damit Sie wissen, wer umgehen darf. Die Empfehlung besteht darin, nach Möglichkeit restriktiven Nachrichtenfluss Regeln zu verwenden.

- Exchange-Nachrichtenfluss Regeln
- Outlook-sichere Absender
- Anti-Spam-Richtlinie: IP-Zulassungslisten
- Anti-Spam-Richtlinie: Zulassungslisten für Absender/Domänen

## <a name="using-exchange-mail-flow-rules-to-allow-specific-senders-recommended"></a>Verwenden von Exchange-Nachrichtenfluss Regeln zum Zulassen bestimmter Absender (empfohlen)

Um sicherzustellen, dass nur berechtigte Nachrichten in Ihrer Organisation zulässig sind, sollte die Bedingung einer der folgenden sein:

- Verwenden Sie den Absender Authentifizierungsstatus der sendenden Domäne. Hierzu überprüfen Sie die Kopfzeile der Authentifizierungsergebnisse, um sicherzustellen, dass Sie "dmarc = Pass" oder "dmarc = bestguesspass" enthält. Dadurch wird sichergestellt, dass die sendende Domäne authentifiziert wurde und nicht gefälscht ist. Klicken Sie hier, um weitere Informationen zur e-Mail-Authentifizierung [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC](use-dmarc-to-validate-email.md) zu erhalten.

- Wenn die sendende Domäne keine Authentifizierung aufweist, verwenden Sie die sendende Domäne *sowie* eine sendende IP-Adresse (oder einen IP-Bereich). Stellen Sie sicher, dass Sie so *restriktiv wie möglich*sind, das Ziel ist, dass Sie dies so sicher wie möglich tun. Ein IP-Bereich größer als/24 wird *nicht* empfohlen. Vermeiden Sie das Hinzufügen von IP-Adressbereichen, die zu Consumer-Diensten oder gemeinsam genutzten Infrastrukturen gehören.

> [!IMPORTANT]
> Wenn Sie eine IP-Adresse zulassen, die NATted ist, sollten Sie die Computer kennen, die an diesem NAT-Pool beteiligt sind, um den Bereich ihrer Allow zu kennen. Beachten Sie, dass sich IP-Adressen möglicherweise ändern und NAT-Teilnehmer ebenfalls möglicherweise. Sie müssen alle Zulassungslisten erneut überprüfen, einschließlich der IP-Adresse, die als Teil ihrer Standardwartung zulässig ist.

- *Optional*können Sie eine Bedingung hinzufügen, dass die Nachricht von außerhalb der Organisation stammt (Dies ist implizit, aber es ist in Ordnung, Sie als Bedingung hinzuzufügen, um lokale Server zu berücksichtigen, die möglicherweise nicht ordnungsgemäß konfiguriert sind).

- Wenn Sie eindeutige Stichwörter oder Ausdrücke im e-Mail-Betreff oder-Textkörper identifizieren können, verwenden Sie diese Informationen *optional*als zusätzliche Bedingung, um die von der Nachrichtenfluss Regel zugelassenen e-Mail-Nachrichten weiter einzuschränken.

Die Aktion für die Regel muss diesem Muster entsprechen:

1. Legen Sie die SCL-Bewertung (Spam Confidence Level) auf-1 (Spamfilterung umgehen) fest.

2. Fügen Sie einen X-Header hinzu, um zu sagen, was die Regel bewirkt. Im folgenden Beispiel können Sie eine einfache Kopfzeile `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`hinzufügen. Wenn Sie mehr als eine Domäne in dieser Regel haben, können Sie den Kopfzeilentext entsprechend ändern. **Wenn eine Nachricht die Filterung aufgrund einer e-Mail-Fluss Regel überspringt, stempelt Sie SFV: SKN im X-Forefront-Antispam-Report-Header** (**Wenn Sie sich in einer IP-Zulassungsliste befindet, stempelt Sie auch IPV: Cal**). Dies hilft bei der Problembehandlung.

![GUI zur Umgehung der Spamfilterung.](../../media/1-AllowList-SkipFilteringFromContoso.png)

> [!CAUTION]
> Konfigurieren Sie Nachrichtenfluss Regeln nur mit *der Absenderdomäne* als Bedingung zum Überspringen der Spamfilterung. Diese Methode erhöht erheblich das Risiko, dass Spammer die sendende Domäne spoofen können (oder die vollständige e-Mail-Adresse annehmen), alle Spamfilterung überspringen, Absender Authentifizierungsprüfungen und die Nachricht wird im Posteingang einer Person eingehen.

![Vorgehensweise zum Festlegen des SCL auf minus eins.](../../media/2-AllowList-SetsSCLMinus1.png)

Fügen Sie keine Domänen, die Sie besitzen, oder beliebte Domänen ( `microsoft.com`beispielsweise) zur Nachrichtenfluss Regel als Bedingung hinzu. Dies wird als hohes Risiko betrachtet, da es Gelegenheiten für fehlerhafte Akteure schafft, Ihnen e-Mails zu senden, die andernfalls herausgefiltert würden.

Weitere Informationen finden Sie unter [Verwenden von Nachrichtenfluss Regeln zum Festlegen der SCL-Bewertung in Nachrichten](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

## <a name="use-outlook-safe-senders-end-user-managed"></a>Verwenden von sicheren Outlook-Absendern (Endbenutzer verwaltet)

Anstatt eine Adresse, eine Domäne oder eine IP-Adresse Global zu autorisieren, können Endbenutzer auch das Senden von Adressen über Outlook-sichere Absender zulassen. Die Schritte zum Einrichten dieser Einstellung unterscheiden sich zwischen [Outlook im Internet](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) und dem [Outlook-Client](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). **Wenn Nachrichten aufgrund sicherer Absender erfolgreich autorisiert wurden, wird SFV: SFE im X-Forefront-Antispam-Report angezeigt** , der angibt, dass die Spam/Spoof/Phishing-Filterung umgangen wird.

## <a name="use-anti-spam-policy-ip-allow-lists"></a>Verwenden von IP-Zulassungslisten für Anti-Spam-Richtlinien

Wenn es nicht möglich ist, Nachrichtenfluss Regeln zu verwenden, um einen bestimmten Absender Global zuzulassen, während die Absenderauthentifizierung überprüft wird, oder indem Sie eine Domäne und eine IP zusammenbinden, ist die nächste beste Option das Hinzufügen des Absenders zur *IP-Zulassungsliste für Anti-Spam-Richtlinien*. Die detaillierten Schritte unter [Konfigurieren der Verbindungsfilter Richtlinie](configure-the-connection-filter-policy.md)finden Sie unter. Es ist wichtig, die Anzahl der zulässigen IP-Adressen auf ein Minimum zu beschränken, sodass keine gesamten IP-Adressbereiche verwendet werden. Außerdem sollten Sie keine IP-Adressbereiche hinzufügen, die zu Consumer Services oder gemeinsam genutzten Infrastrukturen gehören, und Sie sollten außerdem *sicherstellen* , dass Sie die Liste der zulässigen IP-Adressen regelmäßig überprüfen und die nicht mehr benötigten Objekte entfernen.

> [!CAUTION]
> Wenn Sie Anti-Spam Policies so konfigurieren, dass Sie nur basierend auf der IP-Adresse des Absenders zugelassen werden, wird die Spam Filterung für alle Nachrichten von dieser IP-Adresse in der Zulassungsregel übersprungen. Dies führt zu einem hohen Risiko, dass ungültige Akteure e-Mails senden, die andernfalls herausgefiltert würden. Diese Methode überspringt auch alle Spamfilterung, Absender Authentifizierungsprüfungen und die Nachricht landet im Posteingang eines Benutzers, wodurch das Risiko erhöht wird.

## <a name="use-anti-spam-policy-senderdomain-allow-lists"></a>Verwenden von Absender-/Domänen Zulassungslisten für Anti-Spam-Richtlinien

Die am wenigsten wünschenswerte Option besteht darin, nach Absender/Domäne zu autorisieren. Diese Option sollte *möglichst vermieden werden, da* Spam/Spoof/Phishing-Schutz vollständig umgangen wird und die Absenderauthentifizierung nicht ausgewertet wird. Diese Methode erhöht das Risiko, dass e-Mails von fehlerhaften Akteuren empfangen werden, und wird am besten vorübergehend und nur beim Testen empfohlen. Die detaillierten Schritte finden Sie im Thema [configure your Spamfilter Policies](configure-your-spam-filter-policies.md) .

Die Höchstgrenze für diese Listen beträgt ungefähr 1000 Einträge; Sie können jedoch nur 30 Einträge in das Portal eingeben. Sie müssen PowerShell verwenden, um mehr als 30 Einträge hinzuzufügen.

> [!IMPORTANT]
> • Das Konfigurieren von Anti-Spam-Richtlinien zum *Zulassen der Absender-/Zulassungs Domäne* führt dazu, dass Nachrichten Spam Filterung für a) Nachrichten von Absendern in der Zulassungsliste oder b) alle Absender aus einer zulässigen Domäne überspringen. Diese Methode erhöht erheblich das Risiko, dass Spammer die sendende Domäne spoofen können (oder die vollständige e-Mail-Adresse imitieren), die alle Spamfilterung, Absender Authentifizierungsprüfungen überspringt und die Nachricht direkt an den Posteingang einer Person sendet. <br/><br/>• Fügen Sie keine Domänen, die Sie besitzen oder beliebter `microsoft.com`Domänen (beispielsweise) zur Nachrichtenfluss Regel als Bedingung hinzu. Diese Methode wird als hohes Risiko betrachtet, da Sie Gelegenheiten für fehlerhafte Akteure schafft, Ihnen e-Mails zu senden, die andernfalls herausgefiltert würden, wodurch das Risiko erhöht würde. <br/><br/>• Informationen zum Erstellen einer **Liste blockierter Absender** finden Sie [hier](create-block-sender-lists-in-office-365.md).
