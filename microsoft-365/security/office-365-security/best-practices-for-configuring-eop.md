---
title: Bewährte Methoden für das Konfigurieren von EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Beachten Sie die folgenden Empfehlungen für Exchange Online Protection (EOP), um allgemeine Konfigurationsfehler zu vermeiden und eine erfolgreiche Funktion zu gewährleisten.
ms.openlocfilehash: 95b415038fdddd1548b23edb89921084d70850c6
ms.sourcegitcommit: 2de2faea7da80712f448e35c2d6c425944013b7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "39204244"
---
# <a name="best-practices-for-configuring-eop"></a>Bewährte Methoden für das Konfigurieren von EOP

Beachten Sie die folgenden Empfehlungen für Exchange Online Protection (EOP), um allgemeine Konfigurationsfehler zu vermeiden und eine erfolgreiche Funktion zu gewährleisten. Es ist grundsätzlich empfehlenswert, die Standardkonfigurationseinstellungen zu verwenden. In diesem Thema wird vorausgesetzt, dass Sie den Setup-Prozess bereits abgeschlossen haben. Wenn Sie das EOP-Setup nicht abgeschlossen haben, finden Sie weitere Informationen unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Verwenden einer Testdomäne

Es wird empfohlen, eine Testdomäne, eine Unterdomäne oder eine Domäne von geringem Volumen zu verwenden, um Dienstfunktionen zu prüfen, bevor Sie sie auf Ihren Produktionsdomänen mit höherem Volumen implementieren.

## <a name="synchronize-recipients"></a>Synchronisieren von Empfängern

Wenn Ihre Organisation über vorhandene Benutzerkonten in einer lokalen Active Directory-Umgebung verfügt, können Sie diese Konten mit Azure Active Directory in der Cloud synchronisieren. Es wird empfohlen, Verzeichnissynchronisierung zu verwenden. Weitere Informationen über die Vorteile der Verzeichnissynchronisierung und über die Schritte zu ihrer Einrichtung finden Sie unter [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).

## <a name="spf-record-customization-to-help-prevent-spoofing"></a>SPF-Eintrags-Anpassung zur Verhinderung von Spoofing

Beim Einrichten von EoP haben Sie einen SPF-Eintrag (Sender Policy Framework) für EoP zu Ihren DNS-Einträgen hinzugefügt. Der SPF-Datensatz erleichtert die Vermeidung von Spoofing. Weitere Informationen darüber, wie ein SPF-Eintrag Spoofing verhindert und wie Sie Ihre lokalen IP-Adressen zum SPF-Eintrag hinzufügen können, finden Sie unter [Einrichten von SPF in Office 365, um Spoofing zu verhindern](set-up-spf-in-office-365-to-help-prevent-spoofing.md).

## <a name="set-anti-spam-options"></a>Festlegen von Antispamoptionen

Verwalten Sie die Einstellungen für den Verbindungsfilter, indem Sie IP-Adressen zu IP-Zulassungs-und IP-Sperrlisten hinzufügen und die Option **sichere Liste aktivieren** auswählen, wodurch die Anzahl falsch positiver Nachrichten, die fälschlicherweise als Spam klassifiziert wurden, verringert wird. Weitere Informationen finden Sie unter [Konfigurieren der Verbindungsfilter Richtlinie](configure-the-connection-filter-policy.md). Weitere Spameinstellungen, die für die gesamte Organisation gelten, sehen Sie sich an, [wie Sie verhindern können, dass echte e-Mails in Office 365 als Spam markiert werden](../../compliance/prevent-email-from-being-marked-as-spam.md) , oder [wie Spam-e-Mails in Office 365 reduziert](reduce-spam-email.md)werden). Diese Themen sind hilfreich, wenn Sie über die Steuerung auf Administratorebene verfügen und false positives oder falsch negative Ergebnisse verhindern möchten.

Verwalten Sie Ihre Inhaltsfilter, indem Sie die Standardeinstellungen überprüfen und optional ändern. Sie können beispielsweise die Aktion für das geschehen mit Spam erkannten Nachrichten ändern. Wenn Sie einen aggressiven Ansatz für die Spamfilterung verfolgen möchten, können Sie erweiterte Spamfilter Optionen konfigurieren. Es wird empfohlen, dass Sie diese Optionen zuerst testen, bevor Sie Sie in Ihrer Produktionsumgebung implementieren (indem Sie Sie aktivieren). Es wurde empfohlen, dass Organisationen, die sich um Phishing kümmern, die Option **SPF Record: Hard Fail** aktivieren. Weitere Informationen finden Sie unter [configure your Spamfilter Policies](configure-your-spam-filter-policies.md) and [Advanced Spam Filtering Options](advanced-spam-filtering-asf-options.md).

> [!IMPORTANT]
> Wenn Sie die Standardaktion "Inhaltsfilter" verwenden und **Nachrichten in den Junk-e-Mail-Ordner verschieben**, um sicherzustellen, dass die Aktion mit lokalen Postfächern funktioniert, müssen Sie in Ihrer lokalen Exchange-Organisation Nachrichtenfluss Regeln (auch bekannt als Transportregeln) konfigurieren, um Spam Kopfzeilen zu erkennen, die von EoP hinzugefügt werden. Weitere Informationen finden Sie unter [Sicherstellen, dass Spam an die Junk-E-Mail-Ordner der einzelnen Benutzer geleitet wird](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

Es wird empfohlen, die häufig gestellten [Fragen zum Anti-Spam-Schutz](anti-spam-protection-faq.md)zu lesen, einschließlich des Abschnitts bewährte Methoden für ausgehende Nachrichten, mit denen sichergestellt wird, dass Ihre ausgehenden e-Mails zugestellt werden.

Sie können falsche negative Meldungen (Spam) und falsche positive Meldungen (kein Spam) auf verschiedene Weise an Microsoft zur Analyse schicken. Ausführliche Informationen finden Sie unter [Submit Spam, Non-Spam, and Phishing Scam messages to Microsoft for Analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="set-anti-malware-options"></a>Festlegen von Antimalwareoptionen

Überprüfen und optimieren Sie die Filtereinstellungen für Schadsoftware. Weitere Informationen finden Sie unter [configure Anti-Malware Policies](configure-anti-malware-policies.md). Lesen Sie weitere häufig gestellten Fragen und Antworten zum Thema Schadsoftwareschutz unter [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).

Wenn Sie von ausführbaren Dateien betroffen sind, die Schadsoftware enthalten, können Sie eine e-Mail-Fluss Regel erstellen, die alle e-Mail-Anlagen mit ausführbaren Inhalten blockiert. Befolgen Sie die Schritte unter [How to Reduce Malware Threats through File Attachment Blocking in Exchange Online Protection](https://support.microsoft.com/kb/2959596) , um die in [use Mail Flow Rules aufgeführten Dateitypen zu blockieren, um Nachrichtenanlagen in Exchange Online zu überprüfen](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

Sie können den [Filter "allgemeine Anlagentypen](protect-against-threats.md#part-1---anti-malware-protection) " in den Richtlinien für Antischadsoftware verwenden.

Für einen höheren Schutz empfehlen wir, auch einige oder alle der folgenden Erweiterungen mithilfe von Nachrichtenflussregeln zu blockieren: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh. Sie können dies tun, indem Sie die Anlage **Dateierweiterung enthält diese Wörter** Bedingung verwenden.

Administratoren und Endbenutzer können Schadsoftware übermitteln, die Sie an den Filtern vorbei gemacht hat, oder eine Datei übermitteln, die fälschlicherweise als Schadsoftware erkannt wurde, indem Sie Sie zur Analyse an Microsoft senden. Weitere Informationen finden Sie unter [Submitting malware and non-malware to Microsoft for analysis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).

## <a name="create-mail-flow-rules"></a>Erstellen von Nachrichtenflussregeln

Erstellen von Nachrichtenfluss Regeln oder benutzerdefinierten Filtern, um Ihre geschäftlichen Anforderungen zu erfüllen.

Wenn Sie eine neue Regel in die Produktion übernehmen, wählen Sie zunächst einen der Testmodi aus, um die Wirkung der Regeln zu überprüfen. Wenn Sie sicher sind, dass die Regel so funktioniert wie beabsichtigt, ändern Sie den Regelmodus in **Erzwingen**.

Beim Bereitstellen neuer Regeln sollten Sie in Erwägung ziehen, als zusätzliche Aktion **Schadensbericht generieren** hinzuzufügen, um die betreffende Regel zu überwachen.

In Hybrid Umgebungen, in denen Ihre Organisation sowohl lokale Exchange-als auch Office 365 umfasst, sollten Sie die Bedingungen beachten, die Sie in Nachrichtenfluss Regeln verwenden. Wenn die Regeln auf die gesamte Organisation angewendet werden sollen, müssen Sie unbedingt Bedingungen verwenden, die sowohl in lokalen Exchange-als auch in Office 365 verfügbar sind. Während die meisten Bedingungen in beiden Umgebungen zur Verfügung stehen, gibt es einige wenige, die nur in der einen oder anderen Umgebung verfügbar sind. Weitere Informationen finden Sie unter [Nachrichtenfluss Regeln (Transportregeln) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

Mithilfe von Nachrichtenfluss Regeln können Sie Nachrichtenanlagen für in Ihrer Organisation in Transit befindliche Nachrichten überprüfen. Konfigurieren Sie die Regelbedingungen so, dass Sie nach Anlagen suchen, und nehmen Sie dann eine Aktion für die erkannten Anlagen vor. Weitere Informationen finden Sie unter [use Mail Flow Rules to Inspect Message Attachments in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments).

### <a name="phishing-and-spoofing-prevention"></a>Schutz vor Phishing und Spoofing

Sie können den Antiphishingschutz verbessern, indem Sie ermitteln, wann persönliche Informationen die Organisation in einer E-Mail verlassen. Beispielsweise können Sie die folgenden normalen Ausdrücke in Nachrichtenflussregeln verwenden, um die Übertragung persönlicher Finanzdaten oder Informationen, die urheberrechtlich geschützte Daten enthalten, zu erkennen:

- `\d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d`(MasterCard oder Visa)

- `\d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d`(American Express)

- `\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d`(eine beliebige 16-stellige Zahl)

- `\d\d\d\-\d\d\-\d\d\d\d`(Sozialversicherungsnummern)

Spam und Phishing können ebenfalls durch Blockieren eingehender bösartiger E-Mails erfolgreich verhindert werden, die scheinbar von Ihrer eigenen Domäne gesendet wurden. Sie können zum Beispiel eine Nachrichtenflussregel erstellen, die Nachrichten von Ihrer Firmendomäne an dieselbe Firmendomäne ablehnt, um diese Art von Absenderfilterung zu blockieren.

> [!CAUTION]
> Wir empfehlen Ihnen, diese Regel nur in solchen Fällen zu erstellen, in denen Sie sicher sind, dass keine legitime E-Mail von Ihrer Domäne über das Internet an Ihrem Mailserver gesendet wird. Dies kann in Fällen passieren, in denen eine Nachricht von einem Benutzer in Ihrer Organisation an einen externen Empfänger gesendet und anschließend an einen anderen Empfänger in Ihrer Organisation weitergeleitet wird.

## <a name="reporting-and-troubleshooting"></a>Berichterstellung und Problembehandlung

Behandeln allgemeiner Probleme und Trends mithilfe der Berichte im Admin Center. Mithilfe des Nachrichtenablaufverfolgungs-Tools können Sie nach einzelnen quellenspezifischen Daten zu einer Nachricht suchen. Weitere Informationen zu Berichten finden Sie unter [Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Weitere Informationen zum Nachrichtenablaufverfolgungs-Tool finden Sie unter [Trace an Email Message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message).

## <a name="for-more-information"></a>Weitere Informationen

[EOP - Allgemeine häufig gestellte Fragen](eop-general-faq.md)

[Hilfe und Support für EOP](help-and-support-for-eop.md)

[Verhindern, dass echte E-Mails in Office 365 als Spam gekennzeichnet werden](../../compliance/prevent-email-from-being-marked-as-spam.md)

[Reduzieren von Spam-E-Mails in Office 365](reduce-spam-email.md)
