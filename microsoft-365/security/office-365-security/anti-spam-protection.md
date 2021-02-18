---
title: Antispamschutz
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die Antispameinstellungen und -filter informieren, mit deren Hilfe Spam in Exchange Online Protection (EOP) verhindert werden kann.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f82e3f36d00994a68ed579779bed314318c51f47
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288945"
---
# <a name="anti-spam-protection-in-eop"></a>Antispamschutz in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> Dieses Thema richtet sich an Administratoren. Themen für Endbenutzer finden Sie unter Übersicht über den [Junk-E-Mail-Filter](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) und [Informationen zu Junk-E-Mails und Phishing.](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden E-Mail-Nachrichten automatisch durch EOP vor Spam (Junk-E-Mail) geschützt.

Die Roadmap zur E-Mail-Sicherheit von Microsoft beinhaltet einen neuen produktübergreifenden Ansatz. Die Antispam- und Antiphishingtechnologie von EOP wird auf unsere E-Mail-Plattformen angewendet, um Benutzern die neuesten Antispam- und Antiphishingtools und Innovationen im gesamten Netzwerk zur Verfügung zu stellen. Das Ziel für EOP ist ein umfassender und nutzbarer E-Mail-Dienst, der Ihnen hilft, Junk-E-Mails, betrügerische E-Mail-Gefahren (Phishing) und Schadsoftware zu erkennen und Benutzer davor zu schützen.

Zusammen mit der E-Mail-Verwendung ist auch der E-Mail-Missbrauch gestiegen. Nicht überwachte Junk-E-Mails können Postfächer und Netzwerke verstopfen, sich auf die Benutzerzufriedenheit auswirken und die Effektivität der seriösen E-Mail-Kommunikation behindern. Deshalb investiert Microsoft weiter in Anti-Spam-Technologien. Einfach ausgedrückt beginnt alles mit dem Speichern und Filtern von Junk-E-Mails.

> [!TIP]
> Die folgenden Antispamtechnologien sind hilfreich, wenn Sie Nachrichten basierend auf dem Nachrichtenumschlag zulassen oder blockieren möchten (z. B. die Domäne des Absenders oder die Quell-IP-Adresse der Nachricht). Um Nachrichten basierend auf der Nutzlast zu erlauben oder zu blockieren (z. B. URLs in der Nachricht oder angefügten Dateien), sollten Sie das [Mandanten-Allow/Block List-Portal verwenden.](tenant-allow-block-list.md)

## <a name="anti-spam-technologies-in-eop"></a>Antispamtechnologien in EOP

Um junk-E-Mails zu reduzieren, umfasst EOP Junk-E-Mail-Schutz, der proprietäre Spamfiltertechnologien verwendet, um Junk-E-Mails zu identifizieren und von legitimen E-Mails zu trennen. Die EOP-Spamfilterung lernt aus bekannten Spam- und Phishingbedrohungen und Benutzerfeedback von unserer Verbraucherplattform, Outlook.com. Kontinuierliches Feedback von EOP-Benutzern im Junk-E-Mail-Klassifizierungsprogramm hilft dabei, sicherzustellen, dass die EOP-Technologien kontinuierlich trainiert und verbessert werden.

Die Antispameinstellungen in EOP werden mit den folgenden Technologien verwendet:

- **Verbindungsfilterung:** Identifiziert gute und ungültige E-Mail-Quellserver frühzeitig in der eingehenden E-Mail-Verbindung über die IP-Liste, die Liste blockierter IP-Adressen und die Liste sicherer Adressen *(eine* dynamische, aber nicht bearbeitbare Liste vertrauenswürdiger Absender, die von Microsoft verwaltet werden). Sie konfigurieren diese Einstellungen in der Verbindungsfilterrichtlinie. Weitere Informationen finden Sie unter [Konfigurieren der Verbindungsfilterung.](configure-the-connection-filter-policy.md)

  > [!NOTE]
  > Spoofing intelligence uses connection filtering to create allow and block lists of senders who are spoofing your email domain. Weitere Informationen finden Sie unter [Weitere Informationen zur Spoofingintelligenz in Microsoft 365.](learn-about-spoof-intelligence.md)

- **Spamfilterung (Inhaltsfilterung):** EOP verwendet die Spamfilterungs-E-Mails **"Spam",**"Spam mit hoher **Spamsicherheit",**"Massen-E-Mail",  **"Phishing-E-Mail"** und **"Phishing-E-Mail** mit hoher Confidence", um Nachrichten zu klassifizieren. Sie können die zu ergreifenden Aktionen basierend auf diesen Bekn nkungen konfigurieren, und Sie können die Benachrichtigungsoptionen für Endbenutzer für Nachrichten konfigurieren, die in Quarantäne gestellt wurden, anstatt zugestellt zu werden. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in Microsoft 365.](configure-your-spam-filter-policies.md)

  > [!NOTE]
  > Standardmäßig ist die Spamfilterung so konfiguriert, dass Nachrichten, die als Spam gekennzeichnet wurden, an den Junk-E-Mail-Ordner des Empfängers gesendet werden. In Hybridumgebungen, in denen EOP lokale Exchange-Postfächer schützt, müssen Sie jedoch zwei Nachrichtenflussregeln (auch als Transportregeln bezeichnet) in Ihrer lokalen Exchange-Organisation konfigurieren, um die EOP-Spamheader zu erkennen, die Nachrichten hinzugefügt werden. Ausführliche Informationen finden Sie unter [Konfigurieren eigenständiger EOP zum Verschieben von Spam in den Junk-E-Mail-Ordner in Hybridumgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- **Filterung ausgehender** Spamnachrichten: EOP überprüft auch, ob Ihre Benutzer keine Spamnachrichten senden, weder im Inhalt ausgehender Nachrichten noch durch Überschreiten der Grenzwerte für ausgehende Nachrichten. Weitere Informationen finden Sie unter [Konfigurieren der Filterung ausgehender Spamnachrichten in Microsoft 365.](configure-the-outbound-spam-policy.md)

- **Spoofintelligenz:** Weitere Informationen finden Sie unter [Weitere Informationen zur Spoofintelligenz in Microsoft 365.](learn-about-spoof-intelligence.md)

## <a name="manage-errors-in-spam-filtering"></a>Verwalten von Fehlern bei der Spamfilterung

Es ist möglich, dass gute Nachrichten als Spam (auch als falsch positive Ergebnisse bezeichnet) identifiziert werden können oder dass Spam an den Posteingang zugestellt werden kann. Sie können die Vorschläge in den folgenden Abschnitten verwenden, um herauszufinden, was passiert ist, und um zu verhindern, dass dies in Der Zukunft geschieht.

Hier sind einige bewährte Methoden, die für beide Szenarien gelten:

- Übermitteln Sie immer falsch klassifizierte Nachrichten an Microsoft. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

- Untersuchen Sie die Antispam-Nachrichtenkopfzeilen: Diese Werte geben Ihnen an, warum eine Nachricht als Spam gekennzeichnet wurde oder warum sie die Spamfilterung übersprungen hat.  Weitere Informationen finden Sie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md).

- Verweisen Sie Ihren MX-Eintrag auf **Microsoft 365:** Damit EOP den besten Schutz bietet, empfehlen wir immer, dass Sie zuerst E-Mails an Microsoft 365 zugestellt haben. Anweisungen finden Sie unter [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Microsoft 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

  Wenn der MX-Eintrag auf einen anderen Speicherort verweist (z. B. eine Antispamlösung oder Appliance eines Drittanbieters), ist es für EOP schwierig, eine genaue Spamfilterung zu bieten. In diesem Szenario müssen Sie die erweiterte Filterung für Connectors (auch als Skip _Listing bekannt) konfigurieren._ Anweisungen finden Sie unter ["Erweiterte Filterung für Connectors in Exchange Online".](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- **Verwenden Sie** E-Mail-Authentifizierung: Wenn Sie eine E-Mail-Domäne besitzen, können Sie DNS verwenden, um zu sicher, dass Nachrichten von Absendern in dieser Domäne legitim sind. Verwenden Sie alle folgenden E-Mail-Authentifizierungsmethoden, um Spam und unerwünschtes Spoofing in EOP zu verhindern:

  - **SPF:** Sender Policy Framework überprüft die Quell-IP-Adresse der Nachricht mit dem Besitzer der sendenden Domäne. Eine kurze Einführung in SPF und eine schnelle Konfiguration finden Sie unter Einrichten von [SPF, um Spoofing zu verhindern.](set-up-spf-in-office-365-to-help-prevent-spoofing.md) Ausführlichere Informationen zur Verwendung von SPF durch Microsoft 365 oder zur Problembehandlung oder zu nicht standardmäßigen Bereitstellungen, z. B. Hybridbereitstellungen, finden Sie unter [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM:** DomainKeys Identified Mail fügt dem Nachrichtenkopf von Nachrichten, die von Ihrer Domäne gesendet werden, eine digitale Signatur hinzu. Weitere Informationen finden Sie unter Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von [Ihrer benutzerdefinierten Domäne in Microsoft 365 gesendet werden.](use-dkim-to-validate-outbound-email.md)

  - **DMARC**: Domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität hilft Ziel-E-Mail-Systemen zu bestimmen, was mit Nachrichten, die SPF- oder DKIM-Überprüfungen nicht durchführen, zu tun sind, und bietet Ihren E-Mail-Partnern eine weitere Vertrauensebene. Weitere Informationen finden Sie unter Verwenden von [DMARC zum Überprüfen von E-Mails in Microsoft 365.](use-dmarc-to-validate-email.md)

- Überprüfen Sie Ihre Massen-E-Mail-Einstellungen: Der Schwellenwert für die massenkonforme Ebene (Bulk Compliant Level, BCL), den Sie in Antispamrichtlinien konfigurieren, bestimmt, ob Massen-E-Mails (auch als graue E-Mails _bezeichnet)_ als Spam gekennzeichnet sind.  Die powerShell-only-Einstellung _MarkAsSpamBulkMail,_ die standardmäßig aktiviert ist, trägt ebenfalls zu den Ergebnissen bei. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Verhindern der Zustellung von Spam an den Posteingang

- **Überprüfen Sie die** Einstellungen Ihrer Organisation: Achten Sie auf Einstellungen, mit denen Nachrichten die Spamfilterung überspringen können (z. B. wenn Sie Ihre eigene Domäne zur Liste der zulässigen Domänen in Antispamrichtlinien hinzufügen). Die empfohlenen Einstellungen finden Sie unter "Empfohlene Einstellungen für EOP und [Microsoft Defender für Office 365-Sicherheit"](recommended-settings-for-eop-and-office365-atp.md) und "Listen sicherer Absender [erstellen".](create-safe-sender-lists-in-office-365.md)

- **Überprüfen** Sie, ob die Junk-E-Mail-Regel im Postfach des Benutzers aktiviert ist: Sie ist standardmäßig aktiviert, aber wenn sie deaktiviert ist, können als Junk markierte Nachrichten nicht in den Junk-E-Mail-Ordner verschoben werden. Weitere Informationen finden Sie unter ["Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365".](configure-junk-email-settings-on-exo-mailboxes.md)

- **Verwenden Sie die verfügbaren Listen blockierter Absender:** Weitere Informationen finden Sie unter [Erstellen von Listen blockierter Absender.](create-block-sender-lists-in-office-365.md)

- **Kündigen von Massen-E-Mails** Wenn die Nachricht etwas war, für das sich der Benutzer angemeldet hat (Newsletter, Produktankündigungen usw.) und einen Link zum Kündigen von Abonnements von einer seriösen Quelle enthält, sollten Sie ihn bitten, das Abonnement einfach zu kündigen.

- Eigenständiges EOP: Erstellen von Nachrichtenflussregeln in lokalen Exchange für EOP-Spamfilter-Beannnungen: In eigenständigen EOP-Umgebungen, in denen EOP lokale Exchange-Postfächer schützt, müssen Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet) im lokalen Exchange konfigurieren, um die EOP-Spamfilter-Filterung zu übersetzen, damit die Junk-E-Mail-Regel die Nachricht in den **Junk-E-Mail-Ordner** verschieben kann. Ausführliche Informationen finden Sie unter [Konfigurieren eigenständiger EOP zum Verschieben von Spam in den Junk-E-Mail-Ordner in Hybridumgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Verhindern, dass eine gute E-Mail als Spam identifiziert wird

Hier sind einige Schritte, die Sie ausführen können, um falsch positive Ergebnisse zu verhindern:

- **Überprüfen Sie die Outlook-Junk-E-Mail-Filtereinstellungen des Benutzers:**

  - **Überprüfen Sie, ob der Junk-E-Mail-Filter** von Outlook deaktiviert ist: Wenn der Outlook-Junk-E-Mail-Filter auf den Standardwert "Keine automatische Filterung" festgelegt **ist,** versucht Outlook nicht, Spam als Spam zu klassifizieren.  Wenn er auf  "Niedrig" oder "Hoch" festgelegt **ist,** verwendet der Outlook-Junk-E-Mail-Filter seine eigene SmartScreen-Filtertechnologie, um Spam zu identifizieren und in den Junk-E-Mail-Ordner zu verschieben, damit Sie falsch positive Ergebnisse erhalten können. Beachten Sie, dass Microsoft die Erstellung von Spamdefinitionsupdates für die SmartScreen-Filter in Exchange und Outlook im November 2016 beendet hat. Die vorhandenen SmartScreen-Spamdefinitionen wurden noch vorhanden, aber ihre Effektivität wird im Laufe der Zeit wahrscheinlich beeinträchtigt werden.

  - Überprüfen Sie, ob die Einstellung "Nur sichere **Listen"** in Outlook deaktiviert ist: Wenn diese Einstellung aktiviert ist, werden nur Nachrichten von Absendern in der Liste sicherer Absender oder der Liste sicherer Empfänger des Benutzers an den Posteingang zugestellt. E-Mails von allen anderen Werden automatisch in den Junk-E-Mail-Ordner verschoben.

  Weitere Informationen zu diesen Einstellungen finden Sie unter "Konfigurieren von Junk-E-Mail-Einstellungen [für Exchange Online-Postfächer in Microsoft 365".](configure-junk-email-settings-on-exo-mailboxes.md)

- **Verwenden Sie die verfügbaren Listen sicherer Absender:** Weitere Informationen finden Sie unter [Erstellen von Listen sicherer Absender.](create-safe-sender-lists-in-office-365.md)

- **Stellen Sie sicher,** dass sich Die Benutzer innerhalb der Sende- und Empfangsgrenzwerte befinden, wie in den Empfangs- und [Sendegrenzwerte](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) in der Exchange Online-Dienstbeschreibung beschrieben.

- **Eigenständiges EOP: Verzeichnissynchronisierung** verwenden: Wenn Sie eigenständiges EOP zum Schutz Ihrer lokalen Exchange-Organisation verwenden, sollten Sie Benutzereinstellungen mithilfe der Verzeichnissynchronisierung mit dem Dienst synchronisieren. Auf diese Weise wird sichergestellt, dass die Liste der sicheren Absender des Benutzers von EOP berücksichtigt wird. Weitere Informationen finden Sie unter [Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).

## <a name="anti-spam-legislation"></a>Antispamgesetze

Bei Microsoft sind wir der Meinung, dass die Entwicklung neuer Technologien und die Selbstverwaltung die Unterstützung effektiver Regierungsziele und rechtlicher Rahmen erfordert. Die weltweite Spamvermehrung hat zahlreiche Behörden dazu bemüht, kommerzielle E-Mails zu reguliert. In vielen Ländern gibt es nun Gesetze zur Bekämpfung von Spam. Die Vereinigten Staaten haben sowohl Bundes- als auch Landesgesetze, die Spam regeln. Dieser ergänzende Ansatz hilft dabei, Spam zu drosseln und gleichzeitig legitimen E-Commerce-Zugang zu ermöglichen. Das CAN-SPAM Act erweitert die verfügbaren Tools zum Eindämmen betrügerischer und betrügerischer E-Mail-Nachrichten.
