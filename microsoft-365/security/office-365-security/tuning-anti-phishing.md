---
title: Optimieren des Schutzes gegen Phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: Administratoren können lernen, die Gründe zu identifizieren, warum und wie eine Phishingnachricht in Microsoft 365 durchfing, und was sie tun müssen, um in Zukunft weitere Phishingnachrichten zu verhindern.
ms.openlocfilehash: 758945c64966763991bfdfba0d70a60ca1c2ddca
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865044"
---
# <a name="tune-anti-phishing-protection"></a>Optimieren des Schutzes gegen Phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Obwohl Microsoft 365 eine Vielzahl von Standardmäßig aktivierten Antiphishingfeatures bietet, ist es möglich, dass einige Phishingnachrichten weiterhin in Ihre Postfächer übergestellt werden. In diesem Thema wird beschrieben, was Sie tun können, um zu ermitteln, warum eine Phishingnachricht passiert ist, und was Sie tun können, um die Antiphishingeinstellungen in Ihrer Microsoft 365-Organisation anzupassen, ohne dies versehentlich zu verschlimmern.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Erste Dinge: Umgang mit gefährdeten Konten und Sicherstellen, dass Sie verhindern, dass weitere Phishingnachrichten durchkommt

Wenn das Konto eines Empfängers durch die Phishingnachricht gefährdet wurde, führen Sie die Schritte zum Reagieren auf ein gefährdetes E-Mail-Konto [in Microsoft 365 aus.](responding-to-a-compromised-email-account.md)

Wenn Ihr Abonnement Microsoft Defender für Office 365 umfasst, können Sie [Office 365 Threat Intelligence](office-365-ti.md) verwenden, um andere Benutzer zu identifizieren, die auch die Phishingnachricht erhalten haben. Sie haben weitere Optionen, um Phishingnachrichten zu blockieren:

- [Sichere Links in Microsoft Defender für Office 365](set-up-atp-safe-links-policies.md)

- [Sichere Anlagen in Microsoft Defender für Office 365](set-up-atp-safe-attachments-policies.md)

- [Antiphishingrichtlinien in Microsoft Defender für Office 365](configure-atp-anti-phishing-policies.md). Beachten Sie, dass Sie die Schwellenwerte für erweiterte **Phishingversuche** in der Richtlinie vorübergehend von **Standard** auf **Aggressive**, **Aggressiver** oder **Aggressiver erhöhen können.**

Überprüfen Sie, ob diese Defender für Office 365-Features aktiviert sind.

## <a name="report-the-phishing-message-to-microsoft"></a>Melden der Phishingnachricht an Microsoft

Das Melden von Phishingnachrichten ist hilfreich bei der Optimierung der Filter, die zum Schutz aller Kunden in Microsoft 365 verwendet werden. Anweisungen finden Sie unter ["Melden von Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)

## <a name="inspect-the-message-headers"></a>Überprüfen der Nachrichtenkopfzeilen

Sie können die Kopfzeilen der Phishingnachricht überprüfen, um zu sehen, ob Sie alles selbst tun können, um zu verhindern, dass weitere Phishingnachrichten durch kommen. Mit anderen Worten, wenn Sie die Nachrichtenkopfzeilen untersuchen, können Sie alle Einstellungen in Ihrer Organisation identifizieren, die für das Zulassen der Phishingnachrichten verantwortlich waren.

Insbesondere sollten Sie das Kopfzeilenfeld **X-Forefront-Antispam-Report** in den Nachrichtenkopfzeilen auf Anzeichen für eine übersprungene Filterung für Spam oder Phishing im Wert "Spam Filtering Verdict" (SFV) überprüfen. Nachrichten, die die Filterung überspringen, haben einen Eintrag von , was bedeutet, dass eine Ihrer Einstellungen diese Nachricht durch Außerkraftsetzen der Spam- oder Phishing-Verdingungen, die vom Dienst `SCL:-1` bestimmt wurden, zugelassen hat. Weitere Informationen zum Erhalten von Nachrichtenkopfzeilen und die vollständige Liste aller verfügbaren Antispam- und Antiphishingnachrichtenkopfzeilen finden Sie [unter "Antispam-Nachrichtenkopfzeilen" in Microsoft 365.](anti-spam-message-headers.md)

## <a name="best-practices-to-stay-protected"></a>Bewährte Methoden zum Schutz

- Führen Sie monatlich die [Sicherheitsnote aus,](../mtp/microsoft-secure-score.md) um die Sicherheitseinstellungen Ihrer Organisation zu bewerten.

- Für Nachrichten, die irrtsprechend in Quarantäne gestellt werden, oder für Nachrichten, die durchgef?en sind, wird empfohlen, im Bedrohungs-Explorer und in Echtzeit nach diesen Nachrichten zu [suchen.](threat-explorer.md) Sie können nach Absender, Empfänger oder Nachrichten-ID suchen. Nachdem Sie die Nachricht gefunden haben, wechseln Sie zu Details, indem Sie auf den Betreff klicken. Suchen Sie nach einer Nachricht in Quarantäne, um zu sehen, was die "Erkennungstechnologie" war, damit Sie die entsprechende Methode verwenden können, um sie außer Kraft zu setzen. Suchen Sie nach einer zulässigen Nachricht, um zu sehen, welche Richtlinie die Nachricht zugelassen hat.

- Gefälschte E-Mails werden in Defender für Office 365 als Phishing gekennzeichnet. Manchmal ist Spoofing gutartig, und manchmal möchten Benutzer es nicht unter Quarantäne stellen. Um die Auswirkungen auf Benutzer zu minimieren, überprüfen Sie regelmäßig den [Spoofing Intelligence-Bericht.](learn-about-spoof-intelligence.md) Nachdem Sie alle erforderlichen Außerkraftsetzungen überprüft und vorgenommen haben,  können Sie [spoofing intelligence](set-up-anti-phishing-policies.md#spoof-settings) so konfigurieren, dass verdächtige Nachrichten isoliert werden, anstatt sie an den Junk-E-Mail-Ordner des Benutzers zu senden.

- Sie können den obigen Schritt für Identitätswechsel (Domäne oder Benutzer) wiederholen. Der Identitätswechselbericht befindet sich unter **Threat Management** \> **Dashboard** \> **Insights**.

- Überprüfen Sie regelmäßig den [Threat Protection Status-Bericht.](view-reports-for-atp.md#threat-protection-status-report)

- Einige Kunden lassen versehentlich Phishingnachrichten zu, indem sie ihre eigenen Domänen in die Liste "Absender zulassen" oder "Domäne zulassen" in Antispamrichtlinien setzen. Diese Konfiguration lässt zwar einige legitime Nachrichten zu, lässt aber auch schädliche Nachrichten zu, die normalerweise von den Spam- und/oder Phishingfiltern blockiert würden. Anstatt die Domäne zu erlauben, sollten Sie das zugrunde liegende Problem beheben.

  Die beste Möglichkeit zum Umgang mit legitimen Nachrichten, die von Microsoft 365 blockiert werden (falsch positive Ergebnisse), die Absender in Ihrer Domäne  betreffen, besteht in der vollständigen und vollständigen Konfiguration der SPF-, DKIM- und DMARC-Einträge in DNS für alle Ihre E-Mail-Domänen:

  - Stellen Sie sicher,  dass Ihr SPF-Eintrag alle E-Mail-Quellen für Absender in Ihrer Domäne identifiziert (vergessen Sie nicht Dienste von Drittanbietern!).

  - Verwenden Sie hard fail (alle), um sicherzustellen, dass nicht autorisierte Absender von E-Mail-Systemen zurückgewiesen werden, die dafür \- konfiguriert sind. Sie können [Spoofintelligenz](learn-about-spoof-intelligence.md) verwenden, um Absender zu identifizieren, die Ihre Domäne verwenden, sodass Sie autorisierte Absender von Drittanbietern in Ihren SPF-Eintrag eintragen können.

  Konfigurationsanweisungen finden Sie unter:

  - [Einrichten von SPF zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne gesendet werden](use-dkim-to-validate-outbound-email.md)

  - [Verwenden von DMARC zum Überprüfen von E-Mails](use-dmarc-to-validate-email.md)

- Wenn möglich, wird empfohlen, E-Mails für Ihre Domäne direkt an Microsoft 365 zu senden. Mit anderen Worten: Verweisen Sie den Microsoft 365-Domänen-MX-Eintrag auf Microsoft 365. Exchange Online Protection (EOP) ist in der Lage, ihren Cloudbenutzern den besten Schutz zu bieten, wenn ihre E-Mails direkt an Microsoft 365 zugestellt werden. Wenn Sie ein E-Mail-Hygienesystem eines Drittanbieters vor EOP verwenden müssen, verwenden Sie die erweiterte Filterung für Connectors. Anweisungen finden Sie unter ["Erweiterte Filterung für Connectors in Exchange Online".](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- Benutzer sollten das [Add-In "Nachricht melden"](enable-the-report-message-add-in.md) oder das ["Phishing melden"-Add-In](enable-the-report-phish-add-in.md) verwenden, um Nachrichten an Microsoft zu melden, das unser System schulen kann. Administratoren sollten auch die [Administratorübermittlungsfunktionen](admin-submission.md) nutzen.

- Die mehrstufige Authentifizierung (Multi Factor Authentication, MFA) ist eine gute Möglichkeit, um gefährdete Konten zu verhindern. Sie sollten dringend erwägen, MFA für alle Benutzer zu aktivieren. Für einen phasenweise Ansatz aktivieren Sie zunächst MFA für Ihre sensibelsten Benutzer (Administratoren, Führungskräfte usw.), bevor Sie MFA für alle Aktivieren. Anweisungen finden Sie unter [Einrichten der mehrstufigen Authentifizierung.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- Weiterleitungsregeln an externe Empfänger werden häufig von Angreifern zum Extrahieren von Daten verwendet. Verwenden Sie **die Informationen zu Postfach-Weiterleitungsregeln** in [der Microsoft-Sicherheitsbewertung,](../mtp/microsoft-secure-score.md) um Weiterleitungsregeln an externe Empfänger zu suchen und sogar zu verhindern. Weitere Informationen finden Sie unter ["Minderung externer Client-Weiterleitungsregeln mit Sicherheitsergebnis".](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)
