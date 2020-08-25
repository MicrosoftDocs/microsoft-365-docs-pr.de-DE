---
title: Antispoofingschutz Häufig gestellte Fragen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können häufig gestellte Fragen und Antworten zum Schutz vor Spoofing in Exchange Online Protection (EoP) anzeigen.
ms.openlocfilehash: 3547b0a0af6d2e541d4ec3546d9bbd4aa34c3a6b
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867139"
---
# <a name="anti-spoofing-protection-faq"></a>Antispoofingschutz Häufig gestellte Fragen

Dieser Artikel enthält häufig gestellte Fragen und Antworten zum Schutz vor Spoofing für Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächern.

Fragen und Antworten zum Antispamschutz finden Sie unter [Anti-Spam Protection FAQ](anti-spam-protection-faq.md).

Fragen und Antworten zum Schutz vor Schadsoftware finden Sie unter [Anti-Malware Protection FAQ](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Warum hat Microsoft sich für Junk-nicht authentifizierte eingehende e-Mails entschieden?

Microsoft ist der Ansicht, dass das Risiko, weiterhin nicht authentifizierte eingehende e-Mails zuzulassen, höher ist als das Risiko, dass legitime eingehende e-Mails verloren gehen.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Bewirkt junking nicht authentifizierte eingehende e-Mails, dass legitime e-Mails als Spam gekennzeichnet werden?

Wenn Microsoft dieses Feature in 2018 aktiviert hat, sind einige falsch positive Ergebnisse aufgetreten (gute Nachrichten wurden als ungültig markiert). Im Laufe der Zeit wurden die Absender jedoch an die Anforderungen angepasst. Die Anzahl der Nachrichten, die fälschlicherweise als gefälscht identifiziert wurden, wurden für die meisten e-Mail-Pfade vernachlässigbar.

Microsoft selbst hat die neuen e-Mail-Authentifizierungsanforderungen mehrere Wochen vor der Bereitstellung an Kunden übernommen. Zunächst gab es zwar Störungen, diese gingen jedoch allmählich zurück.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a>Sind Spoof Intelligence für Microsoft 365-Kunden ohne ATP verfügbar?

Ja. Ab Oktober 2018 steht Spoof Intelligence für alle Organisationen mit Postfächern in Exchange Online und eigenständigen EoP-Organisationen ohne Exchange Online Postfächer zur Verfügung.

Anti-Spoofing-Technologie war anfänglich nur in Office 365 Advanced Threat Protection verfügbar. Beispielsweise Microsoft E5-Abonnements oder ATP-Add-ons.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Wie kann ich Spamnachrichten oder Nachrichten, die kein Spam sind, an Microsoft melden?

Siehe [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Ich bin Administrator und kenne nicht alle Quellen für Nachrichten in meiner e-Mail-Domäne!

[Sie wissen nicht, alle Quellen für Ihre e-Mail](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Was geschieht, wenn ich den Schutz gegen Spoofing für meine Organisation deaktiviere?

Es wird nicht empfohlen, den Schutz gegen Spoofing zu deaktivieren. Durch das Deaktivieren des Schutzes können mehr Phishing-und Spamnachrichten in Ihrer Organisation zugestellt werden. Nicht alle Phishing-Spoofing ist, und nicht alle gefälschten Nachrichten werden nicht verpasst. Allerdings ist Ihr Risiko höher.

Da nun die [Erweiterte Filterung für Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) verfügbar ist, wird empfohlen, den Schutz vor Spoofing nicht mehr zu deaktivieren, wenn Ihre e-Mails vor EoP durch einen anderen Dienst weitergeleitet werden.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Bedeutet der Schutz vor Spoofing, dass ich vor allen Phishing-Daten geschützt werde?

Leider Nein. Angreifer passen sich an die Verwendung anderer Techniken an (beispielsweise kompromittierte Konten oder Konten in kostenlosen e-Mail-Diensten). Der Schutz vor Phishing funktioniert jedoch wesentlich besser, um diese anderen Arten von Phishing-Methoden zu erkennen. Die Schutzebenen in EoP sind zusammenarbeiten entworfen und übereinander aufgebaut.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Blockieren andere große e-Mail-Dienste nicht authentifizierte eingehende e-Mails?

Fast alle großen e-Mail-Dienste implementieren herkömmliche SPF-, DKIM-und DMARC-Prüfungen. Einige Dienste haben andere, strengere Prüfungen, aber nur wenige gehen so weit, dass Sie nicht authentifizierte e-Mails blockieren und als gefälschte Nachrichten behandeln EoP. Allerdings wird die Branche in Bezug auf Probleme mit nicht authentifizierten e-Mails, insbesondere aufgrund des Problems der Phishing-Problematik, immer stärker bewusst.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Muss ich dennoch die erweiterte Spam Filter Einstellung "SPF Record: Hard Fail" (_MarkAsSpamSpfRecordHardFail_) aktivieren, wenn ich Antispoofing aktiviere?

Nein. Diese ASF-Einstellung ist nicht mehr erforderlich. Der Schutz vor Spoofing hält sowohl SPF-Fehler als auch eine viel breitere Gruppe von Kriterien für erforderlich. Wenn Sie Antispoofing und **SPF-Eintrag: Schwerer Fehler** (_MarkAsSpamSpfRecordHardFail_) aktiviert haben, erhalten Sie wahrscheinlich mehr falsch positive Ergebnisse.

Es wird empfohlen, dieses Feature zu deaktivieren, da es fast keine zusätzlichen Vorteile für das Erkennen von Spam-oder Phishing-Nachrichten bietet und stattdessen meistens falsch positive Ergebnisse generiert. Weitere Informationen finden Sie unter [Advanced Spam Filter (ASF) Settings in EoP](advanced-spam-filtering-asf-options.md).

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Hilft das Programm zum Umschreiben von Absendern beim Beheben weitergeleiteter e-Mails?

Mit SRS kann das Problem mit weitergeleiteten E-Mails nur teilweise behoben werden. Durch das Umschreiben der SMTP **-e-Mail von**kann SRS sicherstellen, dass die weitergeleitete Nachricht SPF am nächsten Ziel übergibt. Da Antispoofing jedoch auf der **von** -Adresse in Kombination mit der Domäne **"Mail from** " oder "DKIM-Signing" (oder anderen Signalen) basiert, reicht es nicht aus, zu verhindern, dass SRS weitergeleitete e-Mails als gefälscht gekennzeichnet werden.
