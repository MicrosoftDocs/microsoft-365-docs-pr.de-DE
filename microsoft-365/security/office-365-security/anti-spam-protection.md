---
title: Office 365-Antispamschutz für E-Mails
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: dansimp
ms.date: 6/29/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: Hier finden Sie Informationen zu den Antispameinstellungen und-Filtern, mit denen Sie Spam in Exchange Online und Office 365 verhindern können. Sie werden zu viel Spam in Office 365 einholen? Sie können Ihre Spamfilter und Anti-Spam-Richtlinieneinstellungen anpassen.
ms.openlocfilehash: b7ffb29d09a357cc0a2e407d1a66f29273fc950f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599862"
---
# <a name="office-365-email-anti-spam-protection"></a>Office 365-Antispamschutz für E-Mails

Machen Sie sich Gedanken über zu viel Spam in Office 365? Wir haben mehrere Spamfilter in Ihren Office 365-oder Exchange Online Protection-Dienst (EoP) integriert, sodass Ihre e-Mails ab dem Zeitpunkt, zu dem Sie Ihre erste Nachricht erhalten haben, geschützt sind. Um Spam in Office 365 zu verhindern, sollten Sie möglicherweise eine Schutzeinstellung für ein bestimmtes Problem in Ihrer Organisation ändern, beispielsweise, wenn Sie viel Spam von einem bestimmten Absender erhalten oder einfach Ihre Einstellungen so anpassen möchten, dass Sie zugeschnitten, um die Anforderungen Ihrer Organisation optimal zu erfüllen. Dazu können Sie die Antispameinstellungen im Office 365 Security &amp; Compliance Center ändern.

Dieser Artikel richtet sich an Office 365 Administratoren. Wenn Sie kein Administrator sind, Sie aber ein Office 365er Benutzer sind und erfahren möchten, wie Sie mit Spam umgehen, den Sie erhalten, ist dies nicht der Artikel, den Sie suchen. Wenn Sie stattdessen Outlook für PC oder Outlook für Mac verwenden, beginnen Sie mit [der Übersicht über den Junk-e-Mail-Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Wenn Sie Outlook im Internet verwenden, beginnen Sie mit [Informationen zu Junk-e-Mails und Phishing](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).

## <a name="these-options-help-you-prevent-spam-in-office-365"></a>Mithilfe dieser Optionen können Sie Spam in Office 365 verhindern.

 **Verbindungsfilterung**: Wenn Sie die Verbindungsfilterung verwenden, überprüft Office 365 die Reputation des Absenders, bevor eine Nachricht eingeht. Sie können eine Zulassungsliste oder eine Liste sicherer Absender erstellen, um sicherzustellen, dass Sie alle an Sie gesendeten Nachrichten von einer bestimmten IP-Adresse oder einem IP-Adressbereich empfangen. Sie können auch eine Liste der IP-Adressen erstellen, aus denen Nachrichten blockiert werden, die als Sperrliste bezeichnet werden. Weitere Informationen finden Sie unter [Configure the connection filter policy](configure-the-connection-filter-policy.md). Wenn Sie über Spam in Office 365 besorgt sind, verwenden Sie die Verbindungsfilterung, um Spam zu verhindern.

Für Kunden, die Office 365 Enterprise E5 haben oder Advanced Threat Protection (ATP)-Lizenzen erworben haben, wird die Verbindungsfilterung von Spoof Intelligence verwendet, um Zulassungs-und Sperrlisten von Absendern zu erstellen, die Ihre Domäne Spoofing durchführen. Weitere Informationen finden Sie unter [erfahren Sie mehr über Spoof Intelligence](learn-about-spoof-intelligence.md).

 **Spamfilterung**: Office 365 sucht nach Nachrichtenmerkmalen, die mit Spam im Einklang stehen, indem Sie die Spamfilterung verwenden. Sie können ändern, welche Aktionen für Nachrichten, die als Spam identifiziert werden, durchführen, und auswählen, ob Nachrichten gefiltert werden sollen, die in bestimmten Sprachen verfasst wurden oder aus bestimmten Ländern oder Regionen gesendet werden. Sie können auch erweiterte Spamfilter Optionen aktivieren, wenn Sie einen aggressiven Ansatz für die Spamfilterung verfolgen möchten. Darüber hinaus können Sie Spambenachrichtigungen für Endbenutzer so konfigurieren, dass Benutzer informiert werden, wenn die für Sie vorgesehenen Nachrichten stattdessen an die Quarantäne gesendet wurden. (Das Senden von Nachrichten an die Quarantäne ist eine der konfigurierbaren Aktionen.) Aus diesen Benachrichtigungen können Endbenutzer falsch positive Ergebnisse freigeben und diese an Microsoft zur Analyse melden. Weitere Informationen finden Sie unter [Konfigurieren Ihrer Richtlinien für Spamfilter](configure-your-spam-filter-policies.md). Um Spam in Office 365 zu verhindern, verwenden Sie Spamfilterung, wenn Sie über zu viel Spam in Office 365 besorgt sind, verwenden Sie die Verbindungsfilterung, um Spam zu verhindern.

> [!NOTE]
> Für EoP-eigenständige Kunden: Standardmäßig senden die EoP-Spamfilter Spam-erkannte Nachrichten an den Junk-e-Mail-Ordner jeder Empfänger. Um jedoch sicherzustellen, dass die Aktion **Nachricht in Junk-e-Mail-Ordner verschieben** mit lokalen Postfächern funktioniert, müssen Sie zwei Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln) auf Ihren lokalen Servern konfigurieren, um von EoP hinzugefügte Spam Kopfzeilen zu erkennen. Weitere Informationen finden Sie unter [Sicherstellen, dass Spam an die Junk-E-Mail-Ordner der einzelnen Benutzer geleitet wird](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>Zusätzliche Informationen, wenn Sie zu viel Spam in Office 365 erhalten

Das folgende Video bietet eine Übersicht über die Konfiguration der Spamfilterung in EoP.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]

Weitere Informationen finden Sie unter [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md).

## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>Überprüfen der ausgehenden Nachrichten, um Spam in Office 365 zu verhindern

 **Ausgehende Filterung**: Office 365 überprüft auch, um sicherzustellen, dass Ihre Benutzer keine Spam senden. Beispielsweise kann der Computer eines Benutzers mit Schadsoftware infiziert werden, die dazu führt, dass Spamnachrichten gesendet werden, sodass der Schutz vor dem aufgerufenen *ausgehenden Filter*erstellt wird. Sie können die ausgehende Filterung nicht deaktivieren, aber Sie können die unter [Konfigurieren der ausgehenden Spam Richtlinie](configure-the-outbound-spam-policy.md)beschriebenen Einstellungen konfigurieren. Wenn Sie über zu viel Spam in Office 365 besorgt sind, verwenden Sie die ausgehende Filterung, um Spam in Exchange Online zu verhindern.

## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>Über die Grundlagen hinaus: Weitere Möglichkeiten zum Verhindern von Spam in Office 365

 **Nachrichtenfluss Regeln**: Wenn Sie über die integrierte Spamfilterung hinausgehen und benutzerdefinierte Regeln erstellen möchten, die auf Ihren Geschäftsrichtlinien basieren, sind _[Nachrichtenfluss Regeln](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)_ (auch als _Transportregeln_bezeichnet) ein weiterer Filter, mit dem Sie Spam in Office 365 verhindern können. Sie können beispielsweise Nachrichtenfluss Regeln verwenden, um den SCL-Wert (Spam Confidence Level) für Nachrichten festzulegen, die bestimmten Bedingungen entsprechen, wie in [Verwenden von Nachrichtenfluss Regeln beschrieben, um die SCL-Bewertung (Spam Confidence Level) in Nachrichten festzulegen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

 **E-Mail-Authentifizierung**: Techniken, die die Domain Name System (DNS) zum Hinzufügen überprüfbarer Informationen zu e-Mail-Nachrichten über den Absender einer e-Mail-Nachricht verwenden, werden als e-Mail Erweiterte Office 365 Administratoren können die folgenden e-Mail-Authentifizierungsmethoden verwenden:

- **Sender Policy Framework (SPF)**: SPF überprüft den Ursprung von e-Mail-Nachrichten, indem die IP-Adresse des Absenders anhand des angeblichen Besitzers der sendenden Domäne überprüft wird. Eine kurze Einführung in SPF und seine schnelle Konfiguration finden Sie unter [Einrichten von SPF in Office 365 zur Verhinderung von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Ausführlichere Informationen zur Verwendung von SPF durch Office 365 oder zur Problembehandlung oder zu nicht standardmäßigen Bereitstellungen, z. B. Hybridbereitstellungen, finden Sie unter [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

- **DomainKeys Identified Mail (DKIM)**: DKIM ermöglicht das Anfügen einer digitalen Signatur an e-Mail-Nachrichten im Nachrichtenkopf von e-Mails, die Sie senden. E-Mail-Systeme, die e-Mails von Ihrer Domäne empfangen, verwenden diese digitale Signatur, um festzustellen, ob eingehende e-Mails, die Sie erhalten, legitim sind. Informationen zu DKIM und Office 365 finden Sie unter [Verwenden von DKIM zum Überprüfen von ausgehenden e-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet wurden](use-dkim-to-validate-outbound-email.md).

- **Domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität (DMARC)**: DMARC hilft beim Empfangen von e-Mail-Systemen bestimmen, was mit Nachrichten zu tun ist, die SPF-oder DKIM-Prüfungen nicht ausführen, und bietet eine weitere Vertrauensebene für Ihre e-Mail-Partner. Informationen zum Einrichten von DMARC finden Sie unter [Verwenden von DMARC zum Überprüfen von e-Mails in Office 365](use-dmarc-to-validate-email.md).

Wenn Sie sich Sorgen über Spam, Phishing und Spoofing in Office 365 machen, verwenden Sie SPF, DKIM und DMARC zusammen, um Spam und unerwünschte Spoofing zu verhindern.

 **Verwaltete Einstellungen für Endbenutzer**: Wenn Sie Informationen dazu benötigen, wie Endbenutzer ihre eigenen Spameinstellungen verwalten können, lesen Sie [Übersicht über den Junk-e-Mail-Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) (für Microsoft Outlook Benutzer) oder [erfahren Sie mehr über Junk-e-Mails und Phishing](https://support.microsoft.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31) (für Benutzer von Outlook im Internet). Wenn Sie EoP zum Schutz von lokalen Postfächern verwenden, müssen Sie unbedingt die Verzeichnissynchronisierung verwenden, um sicherzustellen, dass diese Einstellungen mit dem Dienst synchronisiert werden. Weitere Informationen zum Einrichten der Verzeichnissynchronisierung finden Sie unter "Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung" in [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).

## <a name="for-more-information"></a>Weitere Informationen

[Blog: Warum erhalten Spam und Phishing Office 365?](https://blogs.msdn.microsoft.com/tzink/2014/09/12/why-does-spam-and-phishing-get-through-office-365-and-what-can-be-done-about-it/)

[Häufig gestellte Fragen zum Antispamschutz](anti-spam-protection-faq.md)

[Verwenden einer Liste sicherer IP-Adressen oder anderer Techniken, um zu verhindern, dass falsch positive E-Mails als Spam markiert werden](prevent-email-from-being-marked-as-spam.md)

[Vorgehensweise Einrichten von Office 365 Spamfilterung zur Unterstützung der Blockierung von Junk-e-Mails](reduce-spam-email.md)

[Worin besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)

[Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md)

[Rückläufernachrichten und EOP](backscatter-messages-and-eop.md)

## <a name="more-resources"></a>Weitere Ressourcen

[Abrufen von Hilfe bei den Office 365-Community-Foren](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365)

[Administratoren: Melden Sie sich an, und erstellen Sie eine Serviceanfrage](https://portal.office.com/AdminPortal/Home?ref=support)

[AContact-Unterstützung für Business-Produkte – Administratorhilfe](https://docs.microsoft.com/Office365/Admin/contact-support-for-business-products)
