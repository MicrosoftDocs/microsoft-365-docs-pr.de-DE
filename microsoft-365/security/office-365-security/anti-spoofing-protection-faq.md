---
title: Häufig gestellte Fragen zum Antispoofingschutz
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können häufig gestellte Fragen und Antworten zum Schutz vor Spoofing in Exchange Online Protection (EOP) anzeigen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7e7163037029761a53a5461de592e46ab5ea0485
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917558"
---
# <a name="anti-spoofing-protection-faq"></a>Häufig gestellte Fragen zum Antispoofingschutz

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Dieser Artikel enthält häufig gestellte Fragen und Antworten zum Schutz vor Spoofing für Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer.

Fragen und Antworten zum Antispamschutz finden Sie unter Häufig gestellte Fragen zu [Antispamschutz](anti-spam-protection-faq.md).

Fragen und Antworten zum Schutz vor Schadsoftware finden Sie unter Häufig gestellte Fragen zum Schutz [vor Schadsoftware](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Warum hat Sich Microsoft dafür entscheiden, nicht authentifizierte eingehende E-Mails zu junken?

Microsoft ist der Meinung, dass das Risiko, weiterhin nicht authentifizierte eingehende E-Mails zu erlauben, höher ist als das Risiko, dass legitime eingehende E-Mails verloren geht.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Führt junking unauthenticated inbound email dazu, dass legitime E-Mails als Spam gekennzeichnet werden?

Als Microsoft dieses Feature im Jahr 2018 aktivierte, wurden einige falsch positive Ergebnisse (gute Nachrichten wurden als ungültig gekennzeichnet). Im Laufe der Zeit wurden die Absender jedoch an die Anforderungen angepasst. Die Anzahl der Nachrichten, die als spoofed falsch identifiziert wurden, wurde für die meisten E-Mail-Pfade vernachlässigbar.

Microsoft selbst hat die neuen E-Mail-Authentifizierungsanforderungen zunächst einige Wochen übernommen, bevor es für Kunden bereitgestellt wurde. Zunächst gab es zwar Störungen, diese gingen jedoch allmählich zurück.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>Ist Spoof Intelligence für Microsoft 365-Kunden ohne Defender für Office 365 verfügbar?

Ja. Ab Oktober 2018 steht Spoof Intelligence allen Organisationen mit Postfächern in Exchange Online und eigenständigen EOP-Organisationen ohne Exchange Online-Postfächer zur Verfügung.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Wie kann ich Spamnachrichten oder Nachrichten, die kein Spam sind, an Microsoft melden?

Siehe [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Ich bin Administrator und kenne nicht alle Quellen für Nachrichten in meiner E-Mail-Domäne!

Weitere [Informationen finden Sie unter You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Was geschieht, wenn ich den Anti-Spoofing-Schutz für meine Organisation deaktiviere?

Es wird nicht empfohlen, den Schutz vor Spoofing zu deaktivieren. Wenn Sie den Schutz deaktivieren, können mehr Phishing- und Spamnachrichten in Ihrer Organisation zugestellt werden. Nicht alle Phishing-Nachrichten sind Spoofing, und nicht alle gefälschten Nachrichten werden verpasst. Ihr Risiko ist jedoch höher.

Da nun [erweiterte Filterung](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) für Connectors verfügbar ist, wird nicht mehr empfohlen, den Antis spoofing-Schutz zu deaktivieren, wenn Ihre E-Mails über einen anderen Dienst vor EOP geroutet werden.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Bedeutet Anti-Spoofing-Schutz, dass ich vor allen Phishingangriffen geschützt werde?

Leider nein. Angreifer passen sich an andere Techniken an (z. B. gefährdete Konten oder Konten in kostenlosen E-Mail-Diensten). Der Antiphishingschutz funktioniert jedoch wesentlich besser, um diese anderen Arten von Phishingmethoden zu erkennen. Die Schutzebenen in EOP sind aufeinander aufbauend konzipiert.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Blockieren andere große E-Mail-Dienste nicht authentifizierte eingehende E-Mails?

Fast alle großen E-Mail-Dienste implementieren herkömmliche SPF-, DKIM- und DMARC-Prüfungen. Einige Dienste haben andere, strengere Prüfungen, aber nur wenige gehen bis EOP, um nicht authentifizierte E-Mails zu blockieren und sie als gefälschte Nachrichten zu behandeln. Die Branche wird jedoch zunehmend über Probleme mit nicht authentifizierten E-Mails informiert, insbesondere aufgrund des Problems von Phishing.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Muss ich weiterhin die Einstellung Advanced Spam Filter "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) aktivieren, wenn ich Antis spoofing aktiviert habe?

Nein. Diese ASF-Einstellung ist nicht mehr erforderlich. Der Antis spoofing-Schutz berücksichtigt sowohl SPF hard fails als auch eine viel umfassendere Reihe von Kriterien. Wenn Sie Antispoofing und **SPF-Eintrag: Schwerer Fehler** (_MarkAsSpamSpfRecordHardFail_) aktiviert haben, erhalten Sie wahrscheinlich mehr falsch positive Ergebnisse.

Es wird empfohlen, dieses Feature zu deaktivieren, da es fast keinen zusätzlichen Vorteil für das Erkennen von Spam oder Phishing bietet und stattdessen hauptsächlich falsch positive Ergebnisse generiert. Weitere Informationen finden Sie unter [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Hilft das Sender Rewriting Scheme beim Beheben weitergeleiteter E-Mails?

Mit SRS kann das Problem mit weitergeleiteten E-Mails nur teilweise behoben werden. Durch das Umschreiben von SMTP **MAIL FROM** kann SRS sicherstellen, dass die weitergeleitete Nachricht SPF am nächsten Ziel übergibt. Da antis spoofing jedoch auf der **Von-Adresse** in Kombination mit der **Mail FROM-** oder DKIM-Signierdomäne (oder anderen Signalen) basiert, reicht es nicht aus, um zu verhindern, dass weitergeleitete SRS-E-Mails als Spoofing gekennzeichnet werden.