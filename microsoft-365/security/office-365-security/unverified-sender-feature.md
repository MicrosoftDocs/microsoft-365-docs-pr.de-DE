---
title: Nicht überprüfter Absender
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel wird beschrieben, wie Sie verhindern können, dass Phishing-Nachrichten Ihr Postfach, Outlook.com und Outlook im Internet erreichen.
ms.openlocfilehash: b49cc27685f62f5fb5d123a8a7aa4e51e0065e64
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588336"
---
# <a name="unverified-sender"></a>Nicht überprüfter Absender

> [!NOTE]
> Diese Updates werden jetzt ausgerollt und sind möglicherweise nicht für alle Benutzer verfügbar. Dieses Feature wird für Enterprise-Outlook.com und Enterprise Outlook Win32-Desktopbenutzer unterstützt. Es steht derzeit nicht für Consumer Office 365-Benutzer zur Verfügung.

Um zu verhindern, dass Phishing-Nachrichten Ihr Postfach erreichen, überprüft Office 365, ob die Absender die Personen sind, die Sie sagen, und verdächtige Nachrichten als Junk-e-Mail markieren.

> [!IMPORTANT]
> Wenn eine Nachricht als Phishing-Betrug markiert ist, zeigt Outlook eine Warnung oben auf der Seite an, aber alle Links in der Nachricht können weiterhin geöffnet werden.

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a>Wie kann ich eine verdächtige Nachricht im Posteingang identifizieren?

Outlook zeigt Indikatoren an, wenn der Absender einer Nachricht entweder nicht identifiziert werden kann oder sich Ihre Identität von dem unterscheidet, was Sie in der von-Adresse sehen.

## <a name="you-see-a--in-the-sender-image"></a>Im Absender Bild wird ein "?" angezeigt.

Wenn Office 365 die Identität des Absenders nicht mithilfe von e-Mail-Authentifizierungstechniken überprüfen können, wird im Absender Bild ein '? ' angezeigt.

![Nachricht hat die Überprüfung nicht übergeben](../../media/message-did-not-pass-verification.jpg)

Nicht jede Nachricht, die nicht authentifiziert werden kann, ist bösartig. Sie sollten jedoch mit der Interaktion mit Nachrichten vorsichtig sein, die nicht authentifiziert werden, wenn Sie den Absender nicht erkennen. Oder wenn Sie einen Absender erkennen, der normalerweise nicht über ein "?" im Absender Bild verfügt, aber Sie ihn plötzlich sehen, könnte dies ein Zeichen sein, bei dem der Absender gefälscht wird.

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a>Vorgehensweise Verwalten der Nachrichten, die nicht überprüfte Absender Behandlung erhalten 

Wenn Sie ein Office 365er Kunde sind, können Sie dieses Feature über das Office 365 Security & Compliance Center verwalten.

- Im Security & Compliance Center können globale oder Sicherheitsadministratoren das Feature durch Schutz vor Spoofing unter der Anti-Phishing-Richtlinie aktivieren oder deaktivieren. Darüber hinaus können Sie das Cmdlet " **AntiPhishPolicy** " in Exchange Online PowerShell verwenden. Ausführliche Informationen finden Sie unter [Anti-Phishing Protection in Office 365](anti-phishing-protection.md) und [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/set-antiphishpolicy).

    ![Bearbeiten von nicht authentifizierten Absendern in der grafischen Benutzeroberfläche.](../../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- Wenn ein Administrator ein falsch positives Ergebnis erkannt hat und ein Absender nicht überprüfte Absender Behandlung erhalten soll, können Sie eine der folgenden Aktionen ausführen, um den Absender zur Spoof-Zulassungsliste "Spoof Intelligence" hinzuzufügen:

  - Fügen Sie das Domänenpaar über die Spoof Intelligence-Einblicke hinzu. Ausführliche Informationen finden Sie unter [Exemplarische Vorgehensweise: Spoof Intelligence Insight](walkthrough-spoof-intelligence-insight.md).

  - Fügen Sie das Domänenpaar über das Cmdlet " **PhishFilterPolicy** " in Exchange Online PowerShell hinzu. Ausführliche Informationen finden Sie unter [Festlegen von PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy) und [Einrichten Office 365 ATP-Richtlinien für Anti-Phishing und Anti-Phishing](set-up-anti-phishing-policies.md).

Darüber hinaus wird die nicht verifizierte Absender Behandlung nicht angewendet, wenn die Nachricht über Nachrichtenfluss Regeln (auch bekannt als Transportregeln) oder über die Liste sicherer Domänen (Anti-Spam Policies) an den Posteingang übermittelt wurde.

## <a name="how-to-manage-the-via-tag"></a>Verwalten des "Via"-Tags 

Wenn Sie ein Office 365er Kunde sind, können Sie diese Funktion über das Office 365 Security & Compliance Center verwalten, genauso wie Sie die nicht überprüfte Absender Behandlung verwalten. Wenn Sie den Absender der Spoof-Spoofing-Zulassungsliste hinzufügen, wird die "über"-Behandlung nicht angewendet.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="what-criteria-does-outlookcom-and-outlook-win32-desktop-use-to-add-the--and-the-via-properties"></a>Welche Kriterien verwendet Outlook.com und Outlook-Win32-Desktop, um die Eigenschaften "?" und "Via" hinzuzufügen?

Für das "?" im Absender Bild: Outlook.com erfordert, dass die Nachricht entweder die SPF-oder die DKIM-Authentifizierung übergibt und entweder einen dmarc-Pass oder eine kombinierte Authentifizierungs Übergabe von Office 365 Spoof Intelligence erhält. Ausführliche Informationen finden Sie unter [Einrichten von SPF in Office 365 zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) und [Verwenden von DKIM zum Überprüfen von ausgehenden e-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet wurden](use-dkim-to-validate-outbound-email.md).

Für das via-Tag: Wenn sich die Domäne in der von-Adresse von der Domäne in der DKIM-Signatur oder von der SMTP-e-Mail-Nachricht unterscheidet, zeigt Outlook.com die Domäne in einem dieser beiden Felder an (es wird die DKIM-Signatur bevorzugt).

### <a name="how-do-i-remove-the--without-utilizing-the-spoof-intelligence-spoof-allow-list"></a>Wie entferne ich das "?", ohne die Spoofing-Zulassungsliste "Spoof Intelligence" zu verwenden?

Für das "?" im Absender Bild: als Absender sollten Sie die Nachricht entweder mit SPF oder DKIM authentifizieren.

Für das via-Tag: als Absender sollten Sie sicherstellen, dass entweder die Domäne in der DKIM-Signatur oder die SMTP-e-Mail von dieselbe oder eine Unterdomäne der Domäne in der von-Adresse ist.

### <a name="do-outlookcom-and-outlook-win32-desktop-show-this-for-every-message-that-doesnt-pass-authentication"></a>Wird dies für jede Nachricht, die die Authentifizierung nicht übergibt, von Outlook.com und Outlook Win32 Desktop angezeigt?

Nicht unbedingt. Office 365 möglicherweise andere Eigenschaften in der Nachricht zur Authentifizierung des Absenders.

## <a name="related-topics"></a>Verwandte Themen

[Schützen Ihres Outlook.com-e-Mail-Kontos](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[Umgang mit Phishing oder Spoofing in Outlook.com](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[Filtern von Junk-e-Mails und Spam in Outlook im Internet](https://support.microsoft.com/office/db786e79-54e2-40cc-904f-d89d57b7f41d)
