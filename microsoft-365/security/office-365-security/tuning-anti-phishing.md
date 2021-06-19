---
title: Optimieren des Schutzes gegen Phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: Administratoren können erfahren, warum und wie eine Phishingnachricht in Microsoft 365 durchgekommen ist und was sie tun müssen, um weitere Phishingnachrichten in der Zukunft zu verhindern.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5093981c5f0166d3f53c3b6c7d24371312633c99
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029345"
---
# <a name="tune-anti-phishing-protection"></a>Optimieren des Schutzes gegen Phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Obwohl Microsoft 365 über eine Vielzahl von Antiphishingfunktionen verfügt, die standardmäßig aktiviert sind, ist es möglich, dass einige Phishingnachrichten trotzdem in Ihre Postfächer gelangen. In diesem Thema wird beschrieben, was Sie tun können, um zu ermitteln, warum eine Phishing-Nachricht durchgekommen ist, und was Sie tun können, um die Antiphishingeinstellungen in Ihrer Microsoft 365 Organisation anzupassen, _ohne versehentlich die Dinge zu verschlimmern._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Zunächst einmal: Umgang mit kompromittierten Konten und Sicherstellen, dass Sie verhindern, dass weitere Phishing-Nachrichten durchkommen

Wenn das Konto eines Empfängers aufgrund der Phishing-Nachricht kompromittiert wurde, führen Sie die Schritte unter [Reagieren auf ein kompromittiertes E-Mail-Konto in Microsoft 365](responding-to-a-compromised-email-account.md)aus.

Wenn Ihr Abonnement Microsoft Defender für Office 365 enthält, können Sie [Office 365 Threat Intelligence](office-365-ti.md) verwenden, um andere Benutzer zu identifizieren, die auch die Phishing-Nachricht erhalten haben. Sie haben zusätzliche Optionen, um Phishingnachrichten zu blockieren:

- [Safe Links in Microsoft Defender für Office 365](set-up-safe-links-policies.md)

- [Safe Anlagen in Microsoft Defender für Office 365](set-up-safe-attachments-policies.md)

- [Antiphishingrichtlinien in Microsoft Defender für Office 365](configure-mdo-anti-phishing-policies.md). Beachten Sie, dass Sie die **Advanced Phishing-Schwellenwerte** in der Richtlinie vorübergehend von **"Standard"** auf **"Aggressive",** **"Aggressiver"** oder **"Most aggressive"** erhöhen können.

Überprüfen Sie, ob diese Defender für Office 365 Features aktiviert sind.

## <a name="report-the-phishing-message-to-microsoft"></a>Melden der Phishingnachricht an Microsoft

Das Melden von Phishingnachrichten ist hilfreich, um die Filter zu optimieren, die zum Schutz aller Kunden in Microsoft 365 verwendet werden. Anweisungen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="inspect-the-message-headers"></a>Überprüfen der Nachrichtenkopfzeilen

Sie können die Kopfzeilen der Phishingnachricht untersuchen, um festzustellen, ob Sie selbst etwas tun können, um zu verhindern, dass mehr Phishingnachrichten durchkommen. Mit anderen Worten, die Untersuchung der Nachrichtenkopfzeilen kann Ihnen helfen, alle Einstellungen in Ihrer Organisation zu identifizieren, die für das Zulassen der Phishingnachrichten verantwortlich waren.

Insbesondere sollten Sie das **Kopfzeilenfeld "X-Forefront-Antispam-Report"** in den Nachrichtenkopfzeilen auf Hinweise auf übersprungene Filterung für Spam oder Phishing im SfV-Wert (Spam Filtering Verdict) überprüfen. Nachrichten, die die Filterung überspringen, verfügen über einen Eintrag von `SCL:-1` , was bedeutet, dass eine Ihrer Einstellungen diese Nachricht durch überschreiben der Spam- oder Phishingbewertungen, die vom Dienst bestimmt wurden, zugelassen hat. Weitere Informationen zum Abrufen von Nachrichtenkopfzeilen und der vollständigen Liste aller verfügbaren Antispam- und Antiphishing-Nachrichtenkopfzeilen finden Sie unter [Antispam-Nachrichtenkopfzeilen in Microsoft 365.](anti-spam-message-headers.md)

## <a name="best-practices-to-stay-protected"></a>Bewährte Methoden, um geschützt zu bleiben

- Führen Sie monatlich eine [Sicherheitsbewertung](../defender/microsoft-secure-score.md) aus, um die Sicherheitseinstellungen Ihrer Organisation zu bewerten.

- Für Nachrichten, die versehentlich in Quarantäne gestellt werden, oder für Nachrichten, die durchgelassen werden dürfen, empfehlen wir, im [Bedrohungs-Explorer nach](threat-explorer.md)diesen Nachrichten und Echtzeiterkennungen zu suchen. Sie können nach Absender, Empfänger oder Nachrichten-ID suchen. Nachdem Sie die Nachricht gefunden haben, gehen Sie zu den Details, indem Sie auf den Betreff klicken. Suchen Sie nach einer isolierten Nachricht, um zu sehen, was die "Erkennungstechnologie" war, damit Sie die entsprechende Methode zum Außerkraftsetzen verwenden können. Suchen Sie nach einer zulässigen Nachricht, um zu sehen, welche Richtlinie die Nachricht zugelassen hat.

- E-Mails von gefälschten Absendern (die Absenderadresse der Nachricht stimmt nicht mit der Quelle der Nachricht überein) werden in Defender für Office 365 als Phishing eingestuft. Manchmal ist Spoofing gutartig, und manchmal möchten Benutzer nicht, dass Nachrichten von bestimmten gefälschten Absendern unter Quarantäne gestellt werden. Um die Auswirkungen auf Benutzer zu minimieren, überprüfen Sie in regelmäßigen Abständen den Einblick in die [Spoofintelligenz,](learn-about-spoof-intelligence.md)die Registerkarte **"Spoofing"** in der [Mandanten-Zulassungs-/Sperrliste](tenant-allow-block-list.md)und den Bericht über [Spooferkennungen.](view-email-security-reports.md#spoof-detections-report) Nachdem Sie zulässige und blockierte gefälschte Absender überprüft und alle erforderlichen Außerkraftsetzungen vorgenommen haben, können Sie spoof intelligence in Antiphishingrichtlinien so konfigurieren, dass verdächtige Nachrichten **isoliert** werden, anstatt sie an den [Junk-E-Mail-Ordner](set-up-anti-phishing-policies.md#spoof-settings) des Benutzers zu übermitteln.

- Sie können den obigen Schritt für identitätswechsel (Domäne oder Benutzer) in Microsoft Defender für Office 365 wiederholen. Der Identitätswechselbericht befindet sich unter **Threat Management** \> **Dashboard** \> **Insights**.

- Überprüfen Sie in regelmäßigen Abständen den [Bedrohungsschutzstatusbericht.](view-reports-for-mdo.md#threat-protection-status-report)

- Einige Kunden lassen versehentlich Phishing-Nachrichten durch, indem sie ihre eigenen Domänen in die Liste "Absender zulassen" oder "Domäne zulassen" in Antispamrichtlinien einfügen. Obwohl diese Konfiguration einige seriöse Nachrichten durchlässt, werden auch schädliche Nachrichten zugelassen, die normalerweise durch die Spam- und/oder Phishingfilter blockiert werden. Anstatt die Domäne zuzulassen, sollten Sie das zugrunde liegende Problem beheben.

  Die beste Möglichkeit, mit seriösen Nachrichten umzugehen, die von Microsoft 365 (falsch positive Ergebnisse) blockiert werden, die Absender in Ihrer Domäne betreffen, besteht darin, die SPF-, DKIM- und DMARC-Einträge im DNS für _alle_ Ihre E-Mail-Domänen vollständig zu konfigurieren:

  - Stellen Sie sicher, dass Ihr SPF-Eintrag _alle_ E-Mail-Quellen für Absender in Ihrer Domäne identifiziert (vergessen Sie nicht die Dienste von Drittanbietern!).

  - Verwenden Sie "Hard Fail" \- (alle), um sicherzustellen, dass nicht autorisierte Absender von E-Mail-Systemen abgelehnt werden, die dafür konfiguriert sind. Sie können den Einblick in die [Spoofintelligenz](learn-about-spoof-intelligence.md) verwenden, um Absender zu identifizieren, die Ihre Domäne verwenden, damit Sie autorisierte Absender von Drittanbietern in Ihren SPF-Eintrag aufnehmen können.

  Konfigurationsanweisungen finden Sie unter:

  - [Einrichten von SPF zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne gesendet werden](use-dkim-to-validate-outbound-email.md)

  - [Verwenden von DMARC zum Überprüfen von E-Mails](use-dmarc-to-validate-email.md)

- Wenn möglich, empfehlen wir, dass Sie E-Mails für Ihre Domäne direkt an Microsoft 365 übermitteln. Mit anderen Worten, zeigen Sie den MX-Eintrag Ihrer Microsoft 365 Domäne auf Microsoft 365. Exchange Online Protection (EOP) bietet Ihren Cloudbenutzern den besten Schutz, wenn ihre E-Mails direkt an Microsoft 365 übermittelt werden. Wenn Sie ein E-Mail-Hygienesystem eines Drittanbieters vor EOP verwenden müssen, verwenden Sie erweiterte Filterung für Connectors. Anweisungen finden Sie unter ["Erweiterte Filterung für Connectors" in Exchange Online.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- Benutzer sollten das [Add-In "Nachricht melden"](enable-the-report-message-add-in.md) oder das [Add-In "Phishing melden"](enable-the-report-phish-add-in.md) verwenden, um Nachrichten an Microsoft zu melden, die unser System trainieren können. Administratoren sollten auch die Funktionen für [die Übermittlung](admin-submission.md) von Administratoren nutzen.

- Die mehrstufige Authentifizierung (Multi Factor Authentication, MFA) ist eine gute Möglichkeit, um kompromittierte Konten zu verhindern. Sie sollten dringend erwägen, MFA für alle Ihre Benutzer zu aktivieren. Für einen stufenweisen Ansatz sollten Sie zunächst die MFA für Ihre vertraulichsten Benutzer (Administratoren, Führungskräfte usw.) aktivieren, bevor Sie MFA für alle Aktivieren. Anweisungen finden Sie unter Einrichten der [mehrstufigen Authentifizierung.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- Weiterleitungsregeln an externe Empfänger werden häufig von Angreifern verwendet, um Daten zu extrahieren. Verwenden Sie die Informationen zur Überprüfung von **Postfachweiterleitungsregeln** in [der Microsoft-Sicherheitsbewertung,](../defender/microsoft-secure-score.md) um Weiterleitungsregeln für externe Empfänger zu finden und sogar zu verhindern. Weitere Informationen finden Sie unter ["Minimieren externer Clientweiterleitungsregeln mit Sicherheitsbewertung".](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)
