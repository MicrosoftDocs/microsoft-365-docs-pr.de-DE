---
title: Optimieren des Schutzes gegen Phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Administratoren können lernen, die Gründe zu identifizieren, warum und wie eine Phishing-Nachricht in Microsoft 365 durchgekommen ist, und was Sie tun müssen, um weitere Phishing-Nachrichten zukünftig zu verhindern.
ms.openlocfilehash: b7a68eb3ab3cf7dbb7156059416cca04d80bb3a8
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588440"
---
# <a name="tune-anti-phishing-protection"></a>Optimieren des Schutzes gegen Phishing

Obwohl Microsoft 365 mit einer Vielzahl von Antiphishingfunktionen ausgeliefert wird, die standardmäßig aktiviert sind, ist es möglich, dass einige Phishing-Nachrichten weiterhin zu ihren Postfächern gelangen. In diesem Thema wird beschrieben, was Sie tun können, um zu ermitteln, warum eine Phishing-Nachricht durchgekommen ist, und was Sie tun können, um die antiphishingeinstellungen in Ihrer Microsoft 365-Organisation anzupassen, _ohne versehentlich die Dinge noch schlimmer zu machen_.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>First things first: befassen Sie sich mit kompromittierten Konten und stellen Sie sicher, dass Sie das durchlaufen weiterer Phishing-Nachrichten blockieren.

Wenn das Konto eines Empfängers aufgrund der Phishing-Nachricht kompromittiert wurde, führen Sie die Schritte unter [reagieren auf ein kompromittiertes e-Mail-Konto in Microsoft 365](responding-to-a-compromised-email-account.md)aus.

Wenn Ihr Abonnement Advanced Threat Protection (ATP) enthält, können Sie [Office 365 Threat Intelligence](office-365-ti.md) verwenden, um andere Benutzer zu identifizieren, die auch die Phishing-Nachricht erhalten haben. Sie haben zusätzliche Optionen zum Blockieren von Phishing-Nachrichten:

- [ATP-sichere Links](set-up-atp-safe-links-policies.md)

- [Sichere Anlagen in ATP](set-up-atp-safe-attachments-policies.md)

- [Richtlinien für ATP-Anti-Phishing in Microsoft 365](configure-atp-anti-phishing-policies.md). Beachten Sie, dass Sie die **erweiterten Phishing-Schwellenwerte** in der Richtlinie vorübergehend **von Standard** zu aggressiv **,** aggressiver oder **Most aggressive**aggressiver vergrössern können. **Aggressive**

Stellen Sie sicher, dass diese ATP-Funktionen aktiviert sind.

## <a name="report-the-phishing-message-to-microsoft"></a>Melden der Phishing-Nachricht an Microsoft

Das Melden von Phishing-Nachrichten ist hilfreich beim Optimieren der Filter, die zum Schutz aller Kunden in Microsoft 365 verwendet werden. Anweisungen finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="inspect-the-message-headers"></a>Überprüfen der Nachrichtenkopfzeilen

Sie können die Kopfzeilen der Phishing-Nachricht überprüfen, um festzustellen, ob Sie selbst etwas tun können, um zu verhindern, dass mehr Phishing-Nachrichten durchkommen. Das bedeutet, dass die Überprüfung der Nachrichtenkopfzeilen Ihnen helfen kann, alle Einstellungen in Ihrer Organisation zu identifizieren, die für das Zulassen von Phishing-Nachrichten in zuständig waren.

Insbesondere sollten Sie das Kopfzeilenfeld **X-Forefront-Antispam-Report** in den Nachrichtenkopfzeilen für Hinweise auf übersprungene Spam-oder Phishing-Filterung im Wert Spamfilter Urteil (SFV) überprüfen. Nachrichten, die die Filterung überspringen, haben einen Eintrag von `SCL:-1` , was bedeutet, dass eine Ihrer Einstellungen diese Nachricht durch durch außer Kraft setzen der Spam-oder Phishing-Urteile erlaubt, die vom Dienst bestimmt wurden. Weitere Informationen zum Abrufen von Nachrichtenkopfzeilen und der vollständigen Liste aller verfügbaren Anti-Spam-und Anti-Phishing-Nachrichtenkopfzeilen finden Sie unter [Antispam-Nachrichtenkopfzeilen in Microsoft 365](anti-spam-message-headers.md).

## <a name="best-practices-to-stay-protected"></a>Bewährte Methoden, um geschützt zu bleiben

- Führen Sie auf monatlicher Basis [Secure Score](../mtp/microsoft-secure-score.md) aus, um die Sicherheitseinstellungen Ihrer Organisation zu bewerten.

- Überprüfen Sie den [Spoof Intelligence-Bericht](learn-about-spoof-intelligence.md) regelmäßig, und [Konfigurieren Sie Spoof Intelligence](set-up-anti-phishing-policies.md#spoof-settings) , um verdächtige Nachrichten zu **isolieren** , anstatt Sie an den Junk-e-Mail-Ordner des Benutzers zu senden

- Überprüfen Sie den [Threat Protection-Status Bericht](view-reports-for-atp.md#threat-protection-status-report)regelmäßig.

- Einige Kunden lassen versehentlich Phishing-Nachrichten durch, indem Sie Ihre eigenen Domänen in die Liste Absender zulassen oder Domänen zulassen in den antispamregeln umsetzen. Wenn Sie sich dafür entscheiden, müssen Sie äußerste Vorsicht walten lassen. Obwohl durch diese Konfiguration einige legitime Nachrichten über zulässig sind, werden auch böswillige Nachrichten zugelassen, die normalerweise durch die Spam-und/oder Phishingfilter blockiert würden.

  Die beste Möglichkeit zum Umgang mit legitimen Nachrichten, die von Microsoft 365 (falsch positive Ergebnisse) blockiert werden, die Absender in Ihrer Domäne umfassen, besteht darin, die SPF-, DKIM-und DMARC-Einträge in DNS für _alle_ e-Mail-Domänen vollständig und vollständig zu konfigurieren:

  - Stellen Sie sicher, dass Ihr SPF-Eintrag _alle_ e-Mail-Quellen für Absender in Ihrer Domäne identifiziert (Drittanbieterdienste nicht vergessen!).

  - Verwenden Sie "harter Fehler \- " (), um sicherzustellen, dass nicht autorisierte Absender von e-Mail-Systemen abgelehnt werden, die dafür konfiguriert sind. Sie können [Spoof Intelligence](learn-about-spoof-intelligence.md) verwenden, um die Absender zu identifizieren, die Ihre Domäne verwenden, sodass Sie autorisierte Drittanbieter-Absender in ihren SPF-Eintrag aufnehmen können.

  Konfigurationsanweisungen finden Sie unter:
  
  - [Einrichten von SPF zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne gesendet werden](use-dkim-to-validate-outbound-email.md)

  - [Verwenden von DMARC zum Überprüfen von E-Mails](use-dmarc-to-validate-email.md)

- Wann immer möglich, wird empfohlen, e-Mails für Ihre Domäne direkt an Microsoft 365 zu übertragen. Mit anderen Worten, richten Sie den MX-Eintrag Ihrer Microsoft 365-Domäne auf Microsoft 365. Exchange Online Protection (EoP) ist in der Lage, den besten Schutz für Ihre Cloud-Benutzer bereitzustellen, wenn Ihre e-Mails direkt an Microsoft 365 übermittelt werden. Wenn Sie ein e-Mail-Hygienesystem eines Drittanbieters vor EoP verwenden müssen, verwenden Sie die erweiterte Filterung für Connectors. Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- Die mehrstufige Authentifizierung (MFA) ist ein guter Weg, um kompromittierte Konten zu verhindern. Sie sollten die Aktivierung von MFA für alle Ihre Benutzer unbedingt in Betracht gezogen. Für einen phasenweisen Ansatz beginnen Sie damit, dass Sie MFA für Ihre sensibelsten Benutzer (Administratoren, Führungskräfte usw.) aktivieren, bevor Sie MFA für alle aktivieren. Anweisungen finden Sie unter [Einrichten der mehr](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)stufigen Authentifizierung.

- Weiterleitungsregeln an externe Empfänger werden häufig von Angreifern zum Extrahieren von Daten verwendet. Verwenden Sie die Informationen zur **Überarbeitung von Post Fach Weiterleitungsregeln** in [Microsoft Secure Score](../mtp/microsoft-secure-score.md) , um Weiterleitungsregeln an externe Empfänger zu finden und sogar zu verhindern. Weitere Informationen finden Sie unter [mildernde Client-externe Weiterleitungsregeln mit Secure Score](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score).
