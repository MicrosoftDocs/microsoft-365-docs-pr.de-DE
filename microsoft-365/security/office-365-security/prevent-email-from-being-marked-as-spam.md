---
title: Vermeiden falsch positiver Ergebnisse in Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Hier erfahren Sie, wie Sie falsch positive Ergebnisse verhindern und gewährleisten, dass legitime E-Mails in Office 365, Exchange Online und eigenständigen Exchange Online Protection-Installationen (EOP) nicht im Junk-E-Mail-Ordner landen.
ms.openlocfilehash: 483bad168aa421e3fba4b0cc51e0b2e286f5701d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809300"
---
# <a name="how-to-prevent-good-email-messages-from-being-marked-as-spam-in-office-365"></a>Verhindern, dass echte E-Mail-Nachrichten in Office 365 als Spam gekennzeichnet werden

 **Werden echte E-Mails in Office 365 als Spam gekennzeichnet? Hier kommt die Lösung.**

Wenn eine legitime eingehende E-Mail-Nachricht in Office 365, Exchange Online oder einer eigenständigen Exchange Online Protection-Installation (EOP) als Spam gekennzeichnet wird (ein _falsch positives Ergebnis_), sollten Sie die Nachricht mithilfe von [Verwenden des Add-Ins "Nachricht melden"](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) an Microsoft melden. Darüber hinaus können Sie die Nachricht mithilfe des [Übermittlungen-Explorers](admin-submission.md) senden.

## <a name="determine-why-the-message-was-marked-as-spam"></a>Ermitteln, warum die Nachricht als Spam gekennzeichnet wurde

Sie können zahlreiche Probleme mit falsch positiven Ergebnissen beheben, indem Sie anhand der E-Mail-Nachrichtenkopfzeile ermitteln, warum die Nachricht als Spam gekennzeichnet wurde. Informationen zum Anzeigen der Nachrichtenkopfzeile finden Sie unter [Anzeigen von Internet-Nachrichtenkopfzeilen in Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

Insbesondere müssen Sie nach einem Kopfzeilenfeld namens **X-Forefront-Antispam-Report** suchen. Die wichtigsten Werte, nach denen Sie suchen sollten, sind:

- **SFV:SPM**: Die Nachricht wurde vom Antispamfilter (auch als _Inhaltsfilter_ bezeichnet) als Spam gekennzeichnet. Weitere Informationen finden Sie unter [Office 365-Antispamschutz für E-Mails](anti-spam-protection.md).

- **SFV:BLK**: Die Nachricht wurde als Spam gekennzeichnet, da sich die E-Mail-Adresse des Absenders in der **Liste blockierter Absender** befindet. Weitere Informationen finden Sie unter [Filtern von Junk-E-Mails und Spam in Outlook im Web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d) sowie [Übersicht über den Junk-E-Mail-Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

- **SFV:SKS**: Die Nachricht wurde als Spam markiert, **bevor** sie vom Antispamfilter überprüft werden konnte. Die SCL-Bewertung (Spam Confidence Level) der Nachricht wurde beispielsweise von der Nachrichtenflussregel (auch bekannt als Transportregel) auf einen hohen Wert (9) festgelegt, der angibt, dass die Nachricht Spam war. Weitere Informationen zu SCL-Bewertungen finden Sie unter [SCL-Bewertungen (Spam Confidence Level)](spam-confidence-levels.md).

  Führen Sie eine Nachrichtenablaufverfolgung aus, um festzustellen, ob eine Nachrichtenflussregel für den hohen SCL-Wert verantwortlich ist. Weitere Informationen finden Sie unter [Nachrichtenablaufverfolgung im Security & Compliance Center](message-trace-scc.md).

- **SFV:SKB**: Die Nachricht wurde als Spam gekennzeichnet, da sie einem blockierenden Eintrag in einer Spamfilterrichtlinie (z. B. blockierte Absender oder blockierte Absenderdomänen) entspricht. Weitere Informationen finden Sie unter [Konfigurieren Ihrer Richtlinien für Spamfilter](configure-your-spam-filter-policies.md).

- **SFV:BULK**: Die Nachricht wurde vom Antispamfilter nicht als "Spam", sondern als "Massen-E-Mail" erkannt. Dies geschieht, wenn der BCL-Wert (Bulk Complaint Level) der Nachricht **größer als** der in den Antispamrichtlinien-Einstellungen definierte Schwellenwert ist (ein niedrigerer BCL-Wert gibt an, dass die Nachricht eher Spam ist). Der BCL-Wert wird im Kopfzeilenfeld "**X-Microsoft-Antispam-**" angezeigt.

  Bei einer Massen-E-Mail (auch als _Gray Mail_ bezeichnet) handelt es sich um unerwünschte aber nicht schädliche E-Mail-Inhalte, die absichtlich oder versehentlich vom Benutzer angefordert wurden. Verschiedene Benutzer haben unterschiedliche Erwartungen hinsichtlich der Art und Weise, wie Massen-E-Mails behandelt werden sollen. Deshalb können Sie unterschiedliche Richtlinien oder Regeln erstellen, mit denen Massen-E-Mails entsprechend zugelassen oder blockiert werden. Weitere Informationen hierzu finden Sie in den folgenden Themen:

  - [Worin besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)

  - [BCL-Werte (Bulk Complaint Level)](bulk-complaint-level-values.md)

- **CAT:SPOOF** oder **CAT:PHISH**: Weist auf eine mögliche gefälschte E-Mail (Spoofing) hin, was bedeutet, dass die Nachrichtenquelle nicht überprüft werden kann und möglicherweise verdächtig ist.

  Wenn die Nachricht von einem gefälschten Absender stammt, muss der entsprechende legitime Absender die SPF- und DKIM-Einträge seiner E-Mail-Domäne in seinem öffentlichen DNS überprüfen. Überprüfen Sie das **Authentication-Results**-Kopfzeilenfeld auf weitere Informationen. Obwohl es möglicherweise schwierig ist, alle Absender dazu zu bringen, die richtigen E-Mail-Authentifizierungsverfahren zu verwenden, kann das Umgehen dieser Prüfungen extrem gefährlich sein und stellt die Hauptursache für Spoofing- und Phishingnachrichten dar.

> [!NOTE]
> • Weitere Informationen zu anderen Antispamkopfzeilen und -werten finden Sie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md). <br/><br/>• Andere hier nicht explizit beschriebene Kopfzeilenfelder und -werte werden ausschließlich vom Microsoft-Antispamteam zu Diagnosezwecken verwendet. <br/><br/>• Ein **X-CustomSpam**-Kopfzeilenfeld in der Nachrichtenkopfzeile gibt an, dass die Nachricht von der erweiterten Spamfilterung (ASF) als Spam gekennzeichnet wurde. Wir sind dabei, die ASF-Funktionen in andere Teile der Filterung zu verschieben, und wir empfehlen, dass Sie die ASF-Einstellungen, die aktuell in den Antispamrichtlinien zur Verfügung stehen, **deaktivieren**. Weitere Informationen finden Sie unter [Erweiterte Spamfilterungsoptionen](advanced-spam-filtering-asf-options.md).

## <a name="solutions-for-too-much-spam"></a>Lösungen für zu viel Spam

Administratoren sollten bestimmte Einstellungen in der Organisation konfigurieren, um die Antispamfilterung so effektiv wie möglich zu gestalten. Wenn Sie kein Administrator sind, können Sie zum Abschnitt für Benutzer wechseln.

### <a name="for-admins"></a>Für Administratoren

- **Konfigurieren Sie den MX-Eintrag für Ihre E-Mail-Domäne so, dass er auf Office 365 verweist**: Damit Office 365 Schutz bieten kann, muss der MX-Eintrag für alle E-Mail-Domänen in Office 365 ausschließlich auf Office 365 verweisen. (Das heißt, dass E-Mails für Empfänger in diesen Domänen immer zuerst an Office 365 übermittelt werden.) Wenn der MX-Eintrag auf einen anderen Speicherort (z. B. eine Antispamlösung oder Appliance eines Drittanbieters) verweist, kann Office 365 keine Spamfilterung für Ihre Benutzer bereitstellen. In diesem Szenario sollten Sie erwägen, eine Nachrichtenflussregel zu erstellen, die den Spamfilter für alle Nachrichten umgeht. (Legen Sie den SCL-Wert aller eingehenden Nachrichten auf "-1" fest.) Wenn Sie sich später entscheiden, mit dem MX-Eintrag zuerst auf Office 365 zu verweisen, müssen Sie die Regel entfernen.

- **Aktivieren Sie das Add-In "Nachricht melden" für Benutzer**: Es wird dringend empfohlen, das Add-In "Nachricht melden" für Ihre Benutzer zu aktivieren. Anweisungen finden Sie unter [Aktivieren des Add-Ins "Nachricht melden"](enable-the-report-message-add-in.md).

- **Verwenden Sie den Übermittlungen-Explorer**: Administratoren können jetzt E-Mail-Nachrichten übermitteln, um sie von Microsoft überprüfen zu lassen. Als Administrator können Sie möglicherweise auch das von Ihren Benutzers gesendete Feedback anzeigen. Sie können Muster in deren gemeldeten falsch positiven Ergebnissen verwenden, um Ihre Spamfiltereinstellungen anzupassen. Weitere Informationen finden Sie unter [Senden von verdächtiger Spam- und Phishing-Nachrichten, URLs und Dateien an Microsoft zur Office 365-Überprüfung](admin-submission.md).

- **Vergewissern Sie sich, dass Ihre Benutzer die zulässigen Grenzen einhalten**, wie unter [Empfangs- und Sendegrenzen](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) in der Exchange Online-Dienstbeschreibung beschrieben.

- **Überprüfen Sie die BCL-Ebenen in ihren Antispamrichtlinien**, wie weiter oben in diesem Thema beschrieben.

### <a name="for-users"></a>Für Benutzer

- **Fügen Sie den Absender zur Liste der sicheren Absender** in [Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) oder [Outlook im Web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d) hinzu.

  Office 365 verwendet die Liste der sicheren Absender und die Liste der sicheren Empfänger, aber nicht die Liste der sicheren Domänen. Dies gilt unabhängig davon, wie Sie die Domäne zur Liste hinzufügen (in Outlook, in Outlook im Web oder in Outlook bei anschließender Synchronisierung durch die Verzeichnissynchronisierung).

- **Deaktivieren Sie die SmartScreen-Filterung in Outlook**: Aktivieren Sie in älteren Outlook-Desktopclients nicht die SmartScreen-Filterung in Ihren **Junk-E-Mail-Optionen**. Updates für die SmartScreen-Filterung wurden im November 2016 eingestellt. Wenn Sie **niedrigen** oder **hohen** Schutz vor Junk-E-Mails in Outlook aktivieren, verwenden Sie die SmartScreen-Filterung und erhalten möglicherweise falsch positive Ergebnisse. Beachten Sie, dass die SmartScreen-Filterung in modernen Outlook-Desktopclients nicht verfügbar ist. Weitere Informationen finden Sie unter [Support für SmartScreen in Outlook und Exchange eingestellt](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/Deprecating-support-for-SmartScreen-in-Outlook-and-Exchange/ba-p/605332).

## <a name="troubleshooting-a-message-is-delivered-to-the-junk-email-folder-after-passing-anti-spam-filtering"></a>Problembehandlung: Eine Nachricht wird an den Junk-E-Mail-Ordner übermittelt, nachdem sie die Antispamfilterung bestanden hat.

Wenn ein Benutzer in seinen Junk-E-Mail-Optionen von Outlook **Nur sichere Absender und Empfänger** ausgewählt hat, werden alle Nachrichten von Personen, die sich nicht in der Liste der sicheren Absender oder der Liste der sicheren Empfänger des Benutzers befinden, in den **Junk-E-Mail**-Ordner verschoben, und zwar unabhängig davon, ob die Nachricht die Antispamfilterung Ihrer Organisation bestanden hat oder von einer Nachrichtenflussregel als "Kein Spam" gekennzeichnet wurde (SCL-Wert von "-1").

In Outlook im Web wird dem Empfänger ein gelber Sicherheitshinweis angezeigt, der darauf hinweist, dass sich die Nachricht im **Junk-E-Mail**-Ordner befindet, da der Absender nicht in der Liste der sicheren Absender oder der Liste der sicheren Empfänger enthalten ist.

Die Nachrichtenkopfzeile enthält den **X-Forefront-Antispam-Report**-Kopfzeilenfeldwert `SFV:SKN` (die Nachricht wurde vor der Verarbeitung durch den Antispamfilter als "Kein Spam" gekennzeichnet) oder `SFV:NSPM` (der Antispamfilter hat ermittelt, dass die Nachricht kein Spam ist), aber die Nachricht wird dennoch an den **Junk-E-Mail**-Ordner des Benutzers übermittelt.

Die Nachrichtenkopfzeile enthält keine Angabe, die darauf hinweist, dass die Nachricht an den Junk-E-Mail-Ordner übermittelt wurde, weil die Einstellung **Nur sichere Absender und Empfänger** aktiviert ist. Sie können aber das Cmdlet **Get-MailboxJunkEmailConfiguration** in Exchange Online PowerShell verwenden, um zu ermitteln, ob ein Benutzer nur Nachrichten von vertrauenswürdigen Absendern an seinen Posteingang übermitteln lässt.

Ersetzen Sie \<MailboxIdentity\> durch den Namen, den Alias oder die E-Mail-Adresse des Postfachs, und führen Sie den folgenden Befehl in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) aus:

```PowerShell
Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
```

- Wenn der Wert der *TrustedListsOnly*-Eigenschaft `True` lautet: Nachrichten, die nicht von vertrauenswürdigen Absendern oder Empfängern stammen (sondern von Personen, die sich nicht in der Liste der sicheren Absender oder der Liste der sicheren Empfänger des Benutzers befinden) werden in den Ordner **Junk-E-Mail** verschoben.

- Wenn der Wert der *ContactsTrusted*-Eigenschaft `True` lautet: Die Kontakte des Benutzers gelten auch als vertrauenswürdige Absender. Wenn der Wert der *TrustedListsOnly*-Eigenschaft ebenfalls `True` lautet werden Nachrichten von Personen, die sich nicht in der Liste der sicheren Absender oder der Liste der sicheren Empfänger des Benutzers befinden oder Kontakte des Benutzers sind, in den Ordner **Junk-E-Mail** verschoben.

- Der Wert der *TrustedSendersAndDomains*-Eigenschaft enthält die Liste der sicheren Absender des Benutzers.

Um diese Einstellungen im Postfach zu ändern, ersetzen Sie \<MailboxIdentity\> durch den Namen, den Alias oder die E-Mail-Adresse des Postfachs, und führen Sie den folgenden Befehl aus:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" -TrustedListsOnly $false -ContactsTrusted $false
```

Ausführliche Informationen zu Syntax, Parametern und erforderlichen Berechtigungen finden Sie in den Themen [Get-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-mailboxjunkemailconfiguration) und [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration).

## <a name="directory-synchronization-for-standalone-eop-customers"></a>Verzeichnissynchronisierung für eigenständige EOP-Kunden

Wenn Sie eine eigenständige EOP-Installation zum Schutz Ihrer lokalen Exchange-Organisation verwenden, sollten Sie die Benutzereinstellungen mithilfe der Verzeichnissynchronisierung mit dem Dienst synchronisieren. Auf diese Weise wird sichergestellt, dass die Liste der sicheren Absender des Benutzers von EOP berücksichtigt wird. Weitere Informationen finden Sie unter [Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).
