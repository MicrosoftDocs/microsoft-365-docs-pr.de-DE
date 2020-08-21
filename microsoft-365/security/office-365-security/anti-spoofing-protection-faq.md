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
ms.openlocfilehash: 66dbedaf638154c4a35359a4e5bc66c326c04d1e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826673"
---
# <a name="anti-spoofing-protection-faq"></a>Antispoofingschutz Häufig gestellte Fragen

Dieses Thema enthält häufig gestellte Fragen und Antworten zum Schutz vor Spoofing für Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächern.

Fragen und Antworten zum Antispamschutz finden Sie unter [Anti-Spam Protection FAQ](anti-spam-protection-faq.md).

Fragen und Antworten zum Schutz vor Schadsoftware finden Sie unter [Anti-Malware Protection FAQ](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Warum hat Microsoft sich für Junk-nicht authentifizierte eingehende e-Mails entschieden?

Aufgrund der Auswirkungen von Phishing-Angriffen und weil die e-Mail-Authentifizierung seit mehr als 15 Jahren besteht, ist Microsoft der Ansicht, dass das Risiko, weiterhin nicht authentifizierte eingehende e-Mails zuzulassen, höher ist als das Risiko, dass legitime eingehende e-Mails verloren gehen.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Bewirkt junking nicht authentifizierte eingehende e-Mails, dass legitime e-Mails als Spam gekennzeichnet werden?

Wenn Microsoft dieses Feature in 2018 aktiviert hat, sind einige falsch positive Ergebnisse aufgetreten (gute Nachrichten wurden als ungültig markiert). Im Laufe der Zeit wurden Absender jedoch mit den neuen Anforderungen an die Absenderauthentifizierung angepasst, und die Anzahl der Nachrichten, die fälschlicherweise als gefälscht identifiziert wurden, wurde für die meisten e-Mail-Pfade vernachlässigbar.

Microsoft selbst hat die neuen e-Mail-Authentifizierungsanforderungen mehrere Wochen vor der Bereitstellung an Kunden übernommen. Zunächst gab es zwar Störungen, diese gingen jedoch allmählich zurück.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a>Sind Spoof Intelligence für Microsoft 365-Kunden ohne ATP verfügbar?

Ja. Ab Oktober 2018 steht Spoof Intelligence für alle Organisationen mit Postfächern in Exchange Online und eigenständigen EoP-Organisationen ohne Exchange Online Postfächer zur Verfügung.

Die Anti-Spoofing-Technologie wurde anfänglich nur für Organisationen bereitgestellt, die Office 365 Enterprise E5-Abonnements oder das Office 365 Advanced Threat Protection (Office 365 ATP)-Add-on für Ihr Abonnement hatten.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Wie kann ich Spamnachrichten oder Nachrichten, die kein Spam sind, an Microsoft melden?

Siehe [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Ich bin Administrator und kenne nicht alle Quellen für Nachrichten in meiner e-Mail-Domäne!

[Sie wissen nicht, alle Quellen für Ihre e-Mail](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Was geschieht, wenn ich den Schutz gegen Spoofing für meine Organisation deaktiviere?

Dies wird nicht empfohlen, da dies dazu führt, dass mehr Nachrichten nicht als Phishing- und Spamnachrichten erkannt werden. Nicht alle Phishingnachrichten sind Spoofingnachrichten und nicht alle Spoofingnachrichten werden übersehen. Ihr Risiko ist jedenfalls höher als bei einem Kunden, der Antispoofing aktiviert.

Da nun die [Erweiterte Filterung für Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) verfügbar ist, wird empfohlen, dass Sie den Schutz vor Spoofing nicht mehr deaktivieren, wenn Ihr MX-Eintrag auf einen anderen Server oder Dienst verweist, bevor Sie eine e-Mail an EoP senden.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Bedeutet der Schutz vor Spoofing, dass ich vor allen Phishing-Daten geschützt werde?

Leider Nein. Angreifer passen sich an die Verwendung anderer Techniken an (beispielsweise kompromittierte Konten oder Konten in kostenlosen e-Mail-Diensten). Der Schutz vor Phishing funktioniert jedoch wesentlich besser, um diese anderen Arten von Phishing-Methoden zu erkennen. Die Schutzebenen in EoP sind zusammenarbeiten entworfen und übereinander aufgebaut.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Blockieren andere große e-Mail-Dienste nicht authentifizierte eingehende e-Mails?

Fast alle großen e-Mail-Dienste implementieren herkömmliche SPF-, DKIM-und DMARC-Prüfungen. Einige Dienste haben andere, strengere Überprüfungen, aber nur wenige gehen so weit, dass Sie nicht authentifizierte e-Mails blockieren und Sie als gefälschte Nachrichten behandeln EoP. Allerdings wird die Branche in Bezug auf Probleme mit nicht authentifizierten e-Mails, insbesondere aufgrund des Problems der Phishing-Problematik, immer stärker bewusst.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Muss ich dennoch die erweiterte Spam Filter Einstellung "SPF Record: Hard Fail" (_MarkAsSpamSpfRecordHardFail_) aktivieren, wenn ich Antispoofing aktiviere?

Nein. Diese ASF-Einstellung ist nicht mehr erforderlich, da bei der Antispoofing-Funktion nicht nur SPF-schwer Fehler, sondern eine weitaus umfassendere Gruppe von Kriterien berücksichtigt werden. Wenn Sie Antispoofing und **SPF-Eintrag: Schwerer Fehler** (_MarkAsSpamSpfRecordHardFail_) aktiviert haben, erhalten Sie wahrscheinlich mehr falsch positive Ergebnisse.

Es wird empfohlen, dieses Feature zu deaktivieren, da es fast keine zusätzlichen Vorteile für das Erkennen von Spam-oder Phishing-Nachrichten bietet und stattdessen meistens falsch positive Ergebnisse generiert. Weitere Informationen finden Sie unter [Advanced Spam Filter (ASF) Settings in EoP](advanced-spam-filtering-asf-options.md).

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Hilft das Programm zum Umschreiben von Absendern beim Beheben weitergeleiteter e-Mails?

Mit SRS kann das Problem mit weitergeleiteten E-Mails nur teilweise behoben werden. Durch das Umschreiben der SMTP **-e-Mail von**kann SRS sicherstellen, dass die weitergeleitete Nachricht SPF am nächsten Ziel übergibt. Da Antispoofing jedoch auf der **von** -Adresse in Kombination mit der Domäne **"Mail from** " oder "DKIM-Signing" (oder anderen Signalen) basiert, reicht es nicht aus, zu verhindern, dass SRS weitergeleitete e-Mails als gefälscht gekennzeichnet werden.
