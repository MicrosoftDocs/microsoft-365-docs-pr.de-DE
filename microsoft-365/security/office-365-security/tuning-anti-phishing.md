---
title: Optimieren des Schutzes gegen Phishing in Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Administratoren können lernen, die Gründe für die durchgeführten Phishing-Nachrichten zu identifizieren und zu verhindern, dass mehr Phishing-Nachrichten in der Zukunft vermieden werden.
ms.openlocfilehash: 03f4df5f552dab48283f18ec367ee6979afd9c89
ms.sourcegitcommit: 6ae69c40bafa6aef633789c3df0fa20590bdcf40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823847"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a>Optimieren des Schutzes gegen Phishing in Office 365

Obwohl Office 365 eine Vielzahl von Antiphishingfunktionen enthält, die standardmäßig aktiviert sind, können einige Phishing-Nachrichten möglicherweise dennoch an ihre Postfächer gesendet werden. In diesem Thema wird beschrieben, was Sie tun können, um zu ermitteln, warum eine Phishing-Nachricht durchgekommen ist, und was Sie tun können, um die antiphishingeinstellungen in Ihrer Exchange Online Organisation anzupassen, _ohne versehentlich die Dinge noch schlimmer zu machen_.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>First things first: befassen Sie sich mit kompromittierten Konten und stellen Sie sicher, dass Sie das durchlaufen weiterer Phishing-Nachrichten blockieren.

Wenn ein Empfängerkonto aufgrund der Phishing-Nachricht kompromittiert wurde, führen Sie die Schritte unter [Antworten auf ein kompromittiertes e-Mail-Konto in Office 365](responding-to-a-compromised-email-account.md)aus.

Wenn Ihr Abonnement Advanced Threat Protection (ATP) enthält, können Sie [Office 365 Threat Intelligence](office-365-ti.md) verwenden, um andere Benutzer zu identifizieren, die auch die Phishing-Nachricht erhalten haben. Sie haben zusätzliche Optionen zum Blockieren von Phishing-Nachrichten:

- [ATP-sichere Links](set-up-atp-safe-links-policies.md)

- [Sichere Anlagen in ATP](set-up-atp-safe-attachments-policies.md)

- [Anti-Phishing-Richtlinien für ATP](set-up-anti-phishing-policies.md). Beachten Sie, dass Sie die **erweiterten Phishing-Schwellenwerte** in der Richtlinie vorübergehend **von Standard** zu aggressiv **,** aggressiver oder **** aggressiver vergrössern können. ****

Stellen Sie sicher, dass diese ATP-Funktionen aktiviert sind.

## <a name="report-the-phishing-message-to-microsoft"></a>Melden der Phishing-Nachricht an Microsoft

Das Melden von Phishing-Nachrichten ist hilfreich beim Optimieren der Filter, die zum Schutz aller Kunden in Office 365 verwendet werden.

Senden Sie die Phishing-Nachricht _als Anlage_ in einer neuen, ansonsten leeren Nachricht an **Phish@office365.Microsoft.com**. Leiten Sie die ursprüngliche Nachricht nicht einfach weiter. Andernfalls können die ursprünglichen Nachrichtenkopfzeilen nicht untersucht werden. Sie können auch das Add-in " [Berichtsnachricht](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in) " in Outlook oder Outlook im Internet verwenden (früher bekannt als Outlook Web App).

Weitere Informationen finden Sie unter [Übermitteln von Spam-, Nicht-Spamnachrichten und Nachrichten, die als betrügerische Phishing-Angriffe angesehen werden, an Microsoft zur Analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="inspect-the-message-headers"></a>Überprüfen der Nachrichtenkopfzeilen

Sie können die Kopfzeilen der Phishing-Nachricht überprüfen, um festzustellen, ob Sie selbst etwas tun können, um zu verhindern, dass mehr Phishing-Nachrichten durchkommen. Das bedeutet, dass die Überprüfung der Nachrichtenkopfzeilen Ihnen helfen kann, alle Einstellungen in Ihrer Organisation zu identifizieren, die für das Zulassen von Phishing-Nachrichten in zuständig waren.

Insbesondere sollten Sie das Kopfzeilenfeld **X-Forefront-Antispam-Report** in den Nachrichtenkopfzeilen für Hinweise auf übersprungene Spam-oder Phishing-Filterung im Wert Spamfilter Urteil (SFV) überprüfen. Nachrichten, die die Filterung überspringen, `SCL:-1`haben einen Eintrag von, was bedeutet, dass eine Ihrer Einstellungen diese Nachricht durch durch außer Kraft setzen der Spam-oder Phishing-Urteile erlaubt, die vom Dienst bestimmt wurden. Weitere Informationen zum Abrufen von Nachrichtenkopfzeilen und der vollständigen Liste aller verfügbaren Anti-Spam-und Anti-Phishing-Nachrichtenkopfzeilen finden Sie unter [Antispam-Nachrichtenkopfzeilen](https://docs.microsoft.com/office365/SecurityCompliance/anti-spam-message-headers).

## <a name="best-practices-to-stay-protected"></a>Bewährte Methoden, um geschützt zu bleiben

- Führen Sie auf monatlicher Basis [Secure Score](../mtp/microsoft-secure-score.md) aus, um die Sicherheitseinstellungen Ihrer Office 365 Organisation zu bewerten.

- Überprüfen Sie den [Spoof Intelligence-Bericht](learn-about-spoof-intelligence.md) regelmäßig, und [Aktivieren Sie in der Anti-Phishing-Richtlinie den Schutz vor Spoofing](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy) , um verdächtige Nachrichten zu **isolieren** , anstatt Sie an den Junk-e-Mail-Ordner des Benutzers zu übermitteln.

- Überprüfen Sie den [Threat Protection-Status Bericht](view-reports-for-atp.md#threat-protection-status-report)regelmäßig.

- Einige Kunden lassen versehentlich Phishing-Nachrichten durch, indem Sie Ihre eigenen Domänen in die Liste Absender zulassen oder Domänen zulassen in den antispamregeln umsetzen. Wenn Sie sich dafür entscheiden, müssen Sie äußerste Vorsicht walten lassen. Obwohl durch diese Konfiguration einige legitime Nachrichten über zulässig sind, werden auch böswillige Nachrichten zugelassen, die normalerweise durch die Office 365 Spam-und/oder Phishingfilter blockiert würden.

  Die beste Möglichkeit zum Umgang mit legitimen Nachrichten, die von Office 365 blockiert werden (falsch positive Ergebnisse), die Absender in Ihrer Domäne umfassen, besteht darin, die SPF-, DKIM-und DMARC-Einträge in DNS für _alle_ e-Mail-Domänen in Office 365 vollständig und vollständig zu konfigurieren:

  - Stellen Sie sicher, dass Ihr SPF-Eintrag _alle_ e-Mail-Quellen für Absender in Ihrer Domäne identifiziert (Drittanbieterdienste nicht vergessen!).

  - Verwenden Sie "harter Fehler" (\-), um sicherzustellen, dass nicht autorisierte Absender von e-Mail-Systemen abgelehnt werden, die dafür konfiguriert sind. Sie können [Spoof Intelligence](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence) verwenden, um die Absender zu identifizieren, die Ihre Domäne verwenden, sodass Sie autorisierte Drittanbieter-Absender in ihren SPF-Eintrag aufnehmen können.

  Konfigurationsanweisungen finden Sie unter:
  
  - [Einrichten von SPF in Office 365 zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet werden](use-dkim-to-validate-outbound-email.md)

  - [Verwenden von DMARC zum Validieren von E-Mails in Office 365](use-dmarc-to-validate-email.md)

- Wann immer möglich, wird empfohlen, e-Mails für Ihre Domäne direkt an Office 365 zu übertragen. Mit anderen Worten, richten Sie den MX-Eintrag Ihrer Office 365 Domäne auf Office 365. Exchange Online Protection (EoP) ist in der Lage, den besten Schutz für Ihre Cloud-Benutzer bereitzustellen, wenn Ihre e-Mails direkt an Office 365 übermittelt werden. Wenn Sie vor EoP ein e-Mail-Hygienesystem eines Drittanbieters verwenden müssen, stellen Sie sicher, dass Sie die Anleitung [hier](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)befolgt haben.

- Mehrstufige Authentifizierung (MFA) ist eine wirklich gute Möglichkeit, um kompromittierte Konten zu verhindern. Sie sollten die Aktivierung von MFA für alle Ihre Benutzer unbedingt in Betracht gezogen. Für einen phasenweisen Ansatz beginnen Sie damit, dass Sie MFA für Ihre sensibelsten Benutzer (Administratoren, Führungskräfte usw.) aktivieren, bevor Sie MFA für alle aktivieren. Anweisungen finden Sie unter [Einrichten der mehr](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)stufigen Authentifizierung.

- Weiterleitungsregeln an externe Empfänger werden häufig von Angreifern zum Extrahieren von Daten verwendet. Verwenden Sie die Informationen zur **Überarbeitung von Post Fach Weiterleitungsregeln** in [Microsoft Secure Score](../mtp/microsoft-secure-score.md) , um Weiterleitungsregeln an externe Empfänger zu finden und sogar zu verhindern. Weitere Informationen finden Sie unter [mildernde Client-externe Weiterleitungsregeln mit Secure Score](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/).
