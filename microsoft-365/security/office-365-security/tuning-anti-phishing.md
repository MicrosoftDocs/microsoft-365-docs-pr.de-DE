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
description: Administratoren können lernen, die Gründe zu ermitteln, warum und wie eine Phishingnachricht in Microsoft 365 und was sie tun müssen, um in Zukunft weitere Phishingnachrichten zu verhindern.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8d8f3f93b3fe1643467a12f90123b839addad2ed
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537847"
---
# <a name="tune-anti-phishing-protection"></a>Optimieren des Schutzes gegen Phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Obwohl Microsoft 365 eine Vielzahl von Standardmäßig aktivierten Antiphishingfeatures bietet, ist es möglich, dass einige Phishingnachrichten weiterhin ihre Postfächer erreichen. In diesem Thema wird beschrieben, was Sie tun können, um zu ermitteln, warum eine Phishingnachricht durch ist, und was Sie tun können, um die Antiphishingeinstellungen in Ihrer Microsoft 365-Organisation anzupassen, ohne dies versehentlich zu _verschlimmern._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Erstes: Umgang mit allen gefährdeten Konten und Sicherstellen, dass Sie verhindern, dass weitere Phishingnachrichten durchkommt

Wenn das Konto eines Empfängers durch die Phishingnachricht gefährdet wurde, führen Sie die Schritte unter Antworten auf ein gefährdetes E-Mail-Konto [in Microsoft 365.](responding-to-a-compromised-email-account.md)

Wenn Ihr Abonnement Microsoft Defender für Office 365 enthält, können Sie [Office 365 Threat Intelligence](office-365-ti.md) verwenden, um andere Benutzer zu identifizieren, die auch die Phishingnachricht erhalten haben. Sie haben zusätzliche Optionen zum Blockieren von Phishingnachrichten:

- [Sichere Links in Microsoft Defender für Office 365](set-up-safe-links-policies.md)

- [Sichere Anlagen in Microsoft Defender für Office 365](set-up-safe-attachments-policies.md)

- [Antiphishingrichtlinien in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md). Beachten Sie, dass Sie die erweiterten Phishingschwellenwerte **in** der Richtlinie vorübergehend von **Standard** auf **Aggressive,** **Aggressiver** oder **Aggressiver erhöhen können.**

Überprüfen Sie, ob diese Defender Office 365 aktiviert sind.

## <a name="report-the-phishing-message-to-microsoft"></a>Melden der Phishingnachricht an Microsoft

Das Melden von Phishingnachrichten ist hilfreich bei der Optimierung der Filter, die zum Schutz aller Kunden in Microsoft 365. Anweisungen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="inspect-the-message-headers"></a>Überprüfen der Nachrichtenkopfzeilen

Sie können die Kopfzeilen der Phishingnachricht untersuchen, um zu sehen, ob Sie selbst etwas tun können, um zu verhindern, dass weitere Phishingnachrichten durch kommen. Mit anderen Worten, das Untersuchen der Nachrichtenkopfzeilen kann Ihnen helfen, alle Einstellungen in Ihrer Organisation zu identifizieren, die für das Zulassen der Phishingnachrichten verantwortlich waren.

Insbesondere sollten Sie das **Kopfzeilenfeld X-Forefront-Antispam-Report** in den Nachrichtenkopfzeilen auf Hinweise für eine übersprungene Filterung für Spam oder Phishing im Spam Filtering Verdict (SFV)-Wert überprüfen. Nachrichten, die die Filterung überspringen, haben den Eintrag , d. h. eine Ihrer Einstellungen hat diese Nachricht durch Überschreiben der spam- oder phishing-Urteile, die vom Dienst bestimmt wurden, `SCL:-1` durchgelassen. Weitere Informationen zum Erhalten von Nachrichtenkopfzeilen und die vollständige Liste aller verfügbaren Antispam- und Antiphishingnachrichtenkopfzeilen finden Sie unter Antispamnachrichtenkopfzeilen [in Microsoft 365](anti-spam-message-headers.md).

## <a name="best-practices-to-stay-protected"></a>Bewährte Methoden, um geschützt zu bleiben

- Führen Sie monatlich Secure [Score](../defender/microsoft-secure-score.md) aus, um die Sicherheitseinstellungen Ihrer Organisation zu bewerten.

- Bei Nachrichten, die aus Versehen in Quarantäne bzw. nach Nachrichten, die durchgehen dürfen, wird empfohlen, im Bedrohungs-Explorer und in Echtzeit nach diesen Nachrichten [zu suchen.](threat-explorer.md) Sie können nach Absender, Empfänger oder Nachrichten-ID suchen. Nachdem Sie die Nachricht gefunden haben, wechseln Sie zu Details, indem Sie auf den Betreff klicken. Suchen Sie nach einer Nachricht in Quarantäne, um zu sehen, was die "Erkennungstechnologie" war, damit Sie die entsprechende Methode zum Überschreiben verwenden können. Suchen Sie nach einer zulässigen Nachricht, um zu sehen, welche Richtlinie die Nachricht zugelassen hat.

- E-Mails von gefälschten Absendern (die Absenderadresse der Nachricht ist nicht mit der Quelle der Nachricht übereinstimmend) werden in Defender for Office 365. Manchmal ist Spoofing gutartig, und manchmal möchten Benutzer nicht, dass Nachrichten von bestimmten gefälschten Absendern in Quarantäne gestellt werden. Um die Auswirkungen auf Die Benutzer zu minimieren, überprüfen Sie regelmäßig den Einblick in [spoof intelligence,](learn-about-spoof-intelligence.md)die Registerkarte **Spoof** in der Mandanten-Allow/Block [List](tenant-allow-block-list.md)und den [Bericht spoof detections](view-email-security-reports.md#spoof-detections-report). Nachdem Sie zugelassene und blockierte gefälschte Absender überprüft und alle erforderlichen Außerkraftsetzungen vorgenommen haben,  können Sie sicher sein, spoof intelligence in Antiphishingrichtlinien so zu konfigurieren, dass verdächtige Nachrichten isoliert werden, anstatt sie an den Junk-E-Mail-Ordner des Benutzers zu senden. [](set-up-anti-phishing-policies.md#spoof-settings)

- Sie können den obigen Schritt für Identitätswechsel (Domäne oder Benutzer) in Microsoft Defender für Office 365. Der Identitätswechselbericht finden Sie unter **Threat Management** \> **Dashboard** \> **Insights**.

- Überprüfen Sie in regelmäßigen Abständen [den Threat Protection Status-Bericht](view-reports-for-mdo.md#threat-protection-status-report).

- Einige Kunden erlauben versehentlich Phishingnachrichten, indem sie ihre eigenen Domänen in die Liste Absender zulassen oder Domänen zulassen in Antispamrichtlinien setzen. Diese Konfiguration lässt zwar einige legitime Nachrichten zu, erlaubt aber auch bösartige Nachrichten, die normalerweise von den Spam- und/oder Phishingfiltern blockiert würden. Anstatt die Domäne zu erlauben, sollten Sie das zugrunde liegende Problem beheben.

  Die beste Möglichkeit zum Umgang mit legitimen Nachrichten, die von Microsoft 365 blockiert werden (falsch positive Ergebnisse), die Absender in Ihrer Domäne betreffen,  besteht in der vollständigen und vollständigen Konfiguration der SPF-, DKIM- und DMARC-Einträge in DNS für alle E-Mail-Domänen:

  - Vergewissern Sie sich,  dass Ihr SPF-Eintrag alle E-Mail-Quellen für Absender in Ihrer Domäne identifiziert (vergessen Sie nicht Dienste von Drittanbietern!).

  - Verwenden Sie hard fail ( all), um sicherzustellen, dass nicht autorisierte Absender von E-Mail-Systemen zurückgewiesen werden, die dafür \- konfiguriert sind. Sie können den Einblick in [spoof intelligence](learn-about-spoof-intelligence.md) verwenden, um Absender zu identifizieren, die Ihre Domäne verwenden, sodass Sie autorisierte Absender von Drittanbietern in Ihren SPF-Eintrag eintragen können.

  Konfigurationsanweisungen finden Sie unter:

  - [Einrichten von SPF zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne gesendet werden](use-dkim-to-validate-outbound-email.md)

  - [Verwenden von DMARC zum Überprüfen von E-Mails](use-dmarc-to-validate-email.md)

- Wann immer möglich, wird empfohlen, E-Mails für Ihre Domäne direkt an Microsoft 365. Mit anderen Worten, verweisen Sie Microsoft 365 MX-Eintrag Ihrer Domäne auf Microsoft 365. Exchange Online Protection (EOP) ist in der Lage, ihren Cloudbenutzern den besten Schutz zu bieten, wenn ihre E-Mails direkt an die Microsoft 365. Wenn Sie ein E-Mail-Hygienesystem eines Drittanbieters vor EOP verwenden müssen, verwenden Sie erweiterte Filterung für Connectors. Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- Benutzer sollten das [Add-In "Nachricht](enable-the-report-message-add-in.md) melden" oder das [Phishing-Add-In](enable-the-report-phish-add-in.md) melden, um Nachrichten an Microsoft zu melden, die unser System schulen können. Administratoren sollten auch die [](admin-submission.md) Administrator-Übermittlungsfunktionen nutzen.

- Die mehrstufige Authentifizierung (Multi Factor Authentication, MFA) ist eine gute Möglichkeit, um gefährdete Konten zu verhindern. Sie sollten dringend erwägen, MFA für alle Benutzer zu aktivieren. Für einen schrittweisen Ansatz aktivieren Sie zunächst MFA für Ihre sensibelsten Benutzer (Administratoren, Führungskräfte usw.), bevor Sie MFA für alle Benutzer aktivieren. Anweisungen finden Sie unter [Einrichten der mehrstufigen Authentifizierung](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

- Weiterleitungsregeln an externe Empfänger werden häufig von Angreifern zum Extrahieren von Daten verwendet. Verwenden Sie **die Informationen zu Postfach weiterleitungsregeln** überprüfen in Microsoft Secure [Score,](../defender/microsoft-secure-score.md) um Weiterleitungsregeln an externe Empfänger zu finden und sogar zu verhindern. Weitere Informationen finden Sie unter [Minderung externer Client forwarding Rules with Secure Score](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score).
