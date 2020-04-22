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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: Hier erhalten Sie Informationen zu den Antispameinstellungen und-Filtern, mit denen Sie Spam in Exchange Online und Microsoft 365 verhindern können. Sie werden zu viel Spam in Microsoft 365? Sie können Ihre Spamfilter und Anti-Spam-Einstellungen anpassen.
ms.openlocfilehash: 3bb1c81af0061cc20b4c7bb2a963c0d06b7914e3
ms.sourcegitcommit: d4d082292dc711a579fe925ad989ea54ec2e27f4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43708571"
---
# <a name="anti-spam-protection-in-microsoft-365"></a>Anti-Spam-Schutz in Microsoft 365

> [!NOTE]
> Dieses Thema richtet sich an Microsoft 365-Administratoren. Informationen zu Endbenutzer Themen finden Sie unter [Übersicht über den Junk-e-Mail-Filter](https://support.Microsoft.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) und weitere Informationen [zu Junk-e-Mails und Phishing](https://support.Microsoft.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).

Wenn Sie ein Microsoft 365-Kunde mit Postfächern in Exchange Online oder ein eigenständiger Exchange Online Schutz (EoP)-Kunde ohne Exchange Online Postfächer sind, werden Ihre e-Mail-Nachrichten automatisch vor Spam (Junk-e-Mail) durch EoP geschützt.

Die Roadmap zur E-Mail-Sicherheit von Microsoft beinhaltet einen neuen produktübergreifenden Ansatz. EoP Anti-Spam-und Anti-Phishing-Technologie wird auf unseren e-Mail-Plattformen angewendet, um Benutzern die neuesten Antispam-und Antiphishing-Tools und Innovationen im gesamten Netzwerk bereitzustellen. Das Ziel für EOP ist ein umfassender und nutzbarer E-Mail-Dienst, der Ihnen hilft, Junk-E-Mails, betrügerische E-Mail-Gefahren (Phishing) und Schadsoftware zu erkennen und Benutzer davor zu schützen.

Zusammen mit der E-Mail-Verwendung ist auch der E-Mail-Missbrauch gestiegen. Nicht überwachte Junk-E-Mails können Postfächer und Netzwerke verstopfen, sich auf die Benutzerzufriedenheit auswirken und die Effektivität der seriösen E-Mail-Kommunikation behindern. Deshalb investiert Microsoft weiter in Anti-Spam-Technologien. Einfach ausgedrückt beginnt alles mit dem Speichern und Filtern von Junk-E-Mails.

## <a name="anti-spam-technologies-in-eop"></a>Anti-Spam-Technologien in EoP

Zur Verringerung von Junk-e-Mails umfasst EoP den Junk-e-Mail-Schutz, der proprietäre Spamfilter Technologien zum Identifizieren und trennen von Junk-e-Mails von legitimen e-Mails verwendet. EoP-Spamfilterung erfährt von bekannten Spam-und Phishing-Bedrohungen und Benutzer Feedback von unserer Consumer-Plattform, Outlook.com. Kontinuierliches Feedback von EOP-Benutzern im Junk-E-Mail-Klassifizierungsprogramm hilft dabei, sicherzustellen, dass die EOP-Technologien kontinuierlich trainiert und verbessert werden.

Die Anti-Spam-Einstellungen in EoP bestehen aus den folgenden Technologien:

- **Verbindungsfilterung**: identifiziert gute und ungültige e-Mail-Quellserver frühzeitig in der eingehenden e-Mail-Verbindung über die IP-Zulassungsliste, die IP-Sperrliste und die Liste *sicherer* Adressen (eine dynamische, aber nicht bearbeitbare Liste von vertrauenswürdigen Absendern, die von Microsoft verwaltet werden). Sie konfigurieren diese Einstellungen in der Verbindungsfilter Richtlinie. Weitere Informationen finden Sie unter [Konfigurieren der Verbindungsfilterung in Microsoft 365](configure-the-connection-filter-policy.md).

  > [!NOTE]
  > Spoof Intelligence verwendet Verbindungsfilterung zum Erstellen von Zulassungs-und Sperrlisten von Absendern, die Ihre e-Mail-Domäne manipulieren. Weitere Informationen finden Sie unter [erfahren Sie mehr über Spoof Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

- **Spamfilterung (Inhaltsfilterung)**: EoP verwendet die Spamfilter Urteile **Spam**, Spam mit **hoher Zuverlässigkeit**, **Massen-e**-Mails, **Phishing-e** -Mails und **Phishing-e-Mails mit hoher Vertrauens** Würdigkeit, um Nachrichten zu klassifizieren. Sie können die zu ergreifenden Aktionen basierend auf diesen Urteilen konfigurieren, und Sie können die Benachrichtigungsoptionen für Endbenutzer für Nachrichten konfigurieren, die nicht übermittelt, sondern isoliert wurden. Weitere Informationen finden Sie unter [configure Anti-Spam Policies in Microsoft 365](configure-your-spam-filter-policies.md).

  > [!NOTE]
  > Standardmäßig ist die Spamfilterung so konfiguriert, dass als Spam gekennzeichnete Nachrichten an den Junk-e-Mail-Ordner des Empfängers gesendet werden. In Hybrid Umgebungen, in denen EoP lokale Exchange-Postfächer schützt, müssen Sie in Ihrer lokalen Exchange-Organisation zwei Nachrichtenfluss Regeln (auch bekannt als Transportregeln) konfigurieren, um die EoP-Spam Kopfzeilen zu erkennen, die Nachrichten hinzugefügt werden. Ausführliche Informationen finden Sie unter [Konfigurieren eigenständiger EOP zur Zustellung von Spam in den Junk-E-Mail-Ordner in Hybridumgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- **Spamfilterung für ausgehende**e-Mails: EoP prüft außerdem, ob Ihre Benutzer keine Spamnachrichten senden, weder in ausgehenden Nachrichteninhalten noch durch Überschreitung von Grenzwerten für ausgehende Nachrichten. Weitere Informationen finden Sie unter [Konfigurieren der ausgehenden Spamfilterung in Microsoft 365](configure-the-outbound-spam-policy.md).

- **Spoof Intelligence**: Weitere Informationen finden Sie unter [erfahren Sie mehr über Spoof Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="manage-errors-in-spam-filtering"></a>Verwalten von Fehlern in der Spamfilterung

Es ist möglich, dass gute Nachrichten als Spam identifiziert werden können (auch bekannt als falsch positive Ergebnisse), oder dass Spam in den Posteingang übermittelt werden kann. Sie können die Vorschläge in den folgenden Abschnitten verwenden, um herauszufinden, was passiert ist, und um zu verhindern, dass es in Zukunft geschieht.

Im folgenden finden Sie einige bewährte Methoden, die für beide Szenarien gelten:

- Senden Sie immer falsch klassifizierte Nachrichten an Microsoft. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

- Über **prüfen Sie die Antispam-Nachrichtenkopfzeilen: anhand**dieser Werte erfahren Sie, warum eine Nachricht als Spam markiert wurde oder warum Sie die Spamfilterung übersprungen hat. Weitere Informationen finden Sie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md).

- **Weisen Sie Ihren MX-Eintrag auf Microsoft 365**zu: damit EoP den bestmöglichen Schutz bietet, empfehlen wir Ihnen, zuerst eine e-Mail an Microsoft 365 zu senden. Anweisungen finden Sie unter [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostanbieter für Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

  Wenn der MX-Eintrag auf einen anderen Speicherort verweist (beispielsweise eine Antispam-Lösung oder eine Appliance eines Drittanbieters), ist es für EoP schwierig, eine genaue Spamfilterung bereitzustellen. In diesem Szenario müssen Sie die erweiterte Filterung für Connectors (auch bekannt als _Liste überspringen_) konfigurieren. Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **E-Mail-Authentifizierung verwenden**: Wenn Sie eine e-Mail-Domäne besitzen, können Sie DNS verwenden, um sicherzustellen, dass Nachrichten von Absendern in dieser Domäne legitim sind. Verwenden Sie die folgenden e-Mail-Authentifizierungsmethoden, um Spam und unerwünschte Spoofing in EoP zu verhindern:

  - **SPF**: Sender Policy Framework überprüft die Quell-IP-Adresse der Nachricht anhand des Besitzers der sendenden Domäne. Eine kurze Einführung in SPF und die schnelle Konfiguration finden Sie unter Einrichten von [SPF, um Spoofing zu verhindern](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Für ein tieferes Verständnis der Verwendung von SPF durch Microsoft 365 oder für die Problembehandlung oder nicht standardmäßige Bereitstellungen wie hybridbereitstellungen beginnen Sie mit der Verwendung von [SPF (Sender Policy Framework) durch Microsoft 365, um Spoofing zu verhindern](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM**: DomainKeys Identified Mail fügt eine digitale Signatur zur Nachrichtenkopfzeile von Nachrichten hinzu, die von Ihrer Domäne gesendet werden. Weitere Informationen finden Sie unter [Verwenden von DKIM zum Überprüfen von ausgehenden e-Mails, die von Ihrer benutzerdefinierten Domäne in Microsoft 365 gesendet wurden](use-dkim-to-validate-outbound-email.md).

  - **DMARC**: die domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität hilft Ziel-e-Mail-Systemen zu ermitteln, was mit Nachrichten zu tun ist, die SPF-oder DKIM-Prüfungen nicht ausführen, und bietet eine weitere Vertrauensebene für Ihre e-Mail-Partner. Weitere Informationen finden Sie unter [Verwenden von DMARC zum Überprüfen von e-Mails in Microsoft 365](use-dmarc-to-validate-email.md).

- **Überprüfen Sie Ihre Massen-e-Mail-Einstellungen**: der in den Antispam-Richtlinien konfigurierte Schwellenwert für die Massen konforme Stufe (Bulk compliant Level) bestimmt, ob Massen-e-Mails (auch als _graue e-Mails_bezeichnet) als Spam gekennzeichnet werden. Der standardmäßige PowerShell-Einstellung _MarkAsSpamBulkMail_ , der standardmäßig aktiviert ist, trägt auch zu den Ergebnissen bei. Weitere Informationen finden Sie unter [configure Anti-Spam Policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Verhindern der Zustellung von Spam im Posteingang

- **Überprüfen Sie Ihre Organisationseinstellungen**: Achten Sie auf Einstellungen, mit denen Nachrichten Spamfilterung überspringen können (beispielsweise, wenn Sie Ihre eigene Domäne der Liste zugelassene Domänen in den Antispam-Richtlinien hinzufügen). Unsere empfohlenen Einstellungen finden Sie unter [recommended settings for EoP and Microsoft 365 ATP Security](recommended-settings-for-eop-and-office365-atp.md) und [Create Safe Sender lists](create-safe-sender-lists-in-office-365.md).

- **Überprüfen, ob die Junk-e-Mail-Regel im Postfach des Benutzers aktiviert ist**: Sie ist standardmäßig aktiviert, wenn Sie jedoch deaktiviert ist, können Nachrichten, die als Junk gekennzeichnet sind, nicht in den Junk-e-Mail-Ordner verschoben werden. Weitere Informationen finden Sie unter [Konfigurieren von Junk-e-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Verwenden der Listen verfügbarer blockierter Absender**: Weitere Informationen finden Sie unter [Create blocked Sender lists](create-block-sender-lists-in-office-365.md).

- **Abbestellen von Massen-e-Mails** Wenn sich der Benutzer für die Nachricht (Newsletter, Produktankündigungen usw.) angemeldet hat und einen Unsubscribe-Link von einer seriösen Quelle enthält, sollten Sie ihn bitten, sich einfach abzumelden.

- **Eigenständige EoP: Erstellen von Nachrichtenfluss Regeln im lokalen Exchange für EoP-Spamfilter Urteile**: in eigenständigen EoP-Umgebungen, in denen EoP lokale Exchange-Postfächer schützt, müssen Sie Nachrichtenfluss Regeln (auch bekannt als Transportregeln) in lokalem Exchange konfigurieren, um das EoP Spamfilter Urteil zu übersetzen, damit die Junk-e-Mail-Regel die Nachricht in den Junk- Ausführliche Informationen finden Sie unter [Konfigurieren eigenständiger EOP zur Zustellung von Spam in den Junk-E-Mail-Ordner in Hybridumgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Verhindern, dass gute e-Mail-Nachrichten als Spam identifiziert werden

Hier sind einige Schritte, die Sie ausführen können, um falsch positive Ergebnisse zu vermeiden:

- **Überprüfen Sie die Einstellungen des Outlook-Junk-e-Mail-Filters des Benutzers**:

  - **Überprüfen, ob der Outlook-Junk-e-Mail-Filter deaktiviert ist**: Wenn der Outlook-Junk-e-Mail-Filter auf den Standardwert **keine automatische Filterung**festgelegt ist, versucht Outlook nicht, Massagen als Spam zu klassifizieren.  Wenn er auf **niedrig** oder **hoch**festgelegt ist, verwendet der Outlook-Junk-e-Mail-Filter eine eigene SmartScreen-Filtertechnologie, um Spam in den Junk-e-Mail-Ordner zu identifizieren und zu verlagern, damit Sie falsch positive Ergebnisse erhalten. Beachten Sie, dass Microsoft nicht mehr die Erstellung von Spamdefinitionsupdates für die SmartScreen-Filter in Exchange und Outlook im November 2016. Die vorhandenen SmartScreen-Spamdefinitionen wurden beibehalten, aber ihre Effektivität wird sich im Laufe der Zeit wahrscheinlich vermindern.

  - **Stellen Sie sicher, dass die Einstellung Outlook "nur sichere Listen" deaktiviert ist**: Wenn diese Einstellung aktiviert ist, werden nur Nachrichten von Absendern in der Liste sicherer Absender oder sicherer Empfänger von Benutzern an den Posteingang übermittelt. e-Mails von allen anderen Personen werden automatisch in den Junk-e-Mail-Ordner verschoben.

  Weitere Informationen zu diesen Einstellungen finden Sie unter [Konfigurieren von Junk-e-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Verwenden der verfügbaren Listen für sichere Absender**: Weitere Informationen finden Sie unter [Create Safe Sender Lists] (Create-Safe-Sender-Lists-in-Office-365.MD.

- **Stellen Sie sicher, dass Benutzer innerhalb der Sende-und Empfangs Grenzen liegen** , wie unter [empfangen und Senden von Grenzwerten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) in der Exchange Online Dienstbeschreibung beschrieben.

- **Eigenständige EoP: Verwenden der Verzeichnissynchronisierung**: Wenn Sie eigenständige EoP zum Schutz Ihrer lokalen Exchange-Organisation verwenden, sollten Sie die Benutzereinstellungen mithilfe der Verzeichnissynchronisierung mit dem Dienst synchronisieren. Auf diese Weise wird sichergestellt, dass die Liste der sicheren Absender des Benutzers von EOP berücksichtigt wird. Weitere Informationen finden Sie unter [Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).

## <a name="anti-spam-legislation"></a>Anti-Spam-Gesetzgebung

Bei Microsoft glauben wir, dass die Entwicklung neuer Technologien und die Selbstregulierung die Unterstützung effektiver Regierungsrichtlinien und rechtlicher Rahmenbedingungen erfordert. Die weltweite Spam Verbreitung hat zahlreiche Gesetzestexte dazu veranlasst, kommerzielle e-Mails zu regulieren. In vielen Ländern sind derzeit Spam Schutzgesetze vorhanden. Die Vereinigten Staaten haben sowohl föderale als auch staatliche Gesetze für Spam, und dieser komplementäre Ansatz hilft, Spam zu beschneiden und gleichzeitig legitimen e-Commerce erfolgreich zu ermöglichen. Das CAN-SPAM Act erweitert die verfügbaren Tools für die Eindämmung betrügerischer und betrügerischer e-Mail-Nachrichten.