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
ms.openlocfilehash: 30b956ff12b878d42971413fa4a2f610015d5c97
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081673"
---
# <a name="best-practices-for-configuring-eop"></a>Bewährte Methoden für das Konfigurieren von EOP
  
Beachten Sie die folgenden Empfehlungen für Exchange Online Protection (EOP), um allgemeine Konfigurationsfehler zu vermeiden und eine erfolgreiche Funktion zu gewährleisten. Es ist grundsätzlich empfehlenswert, die Standardkonfigurationseinstellungen zu verwenden. In diesem Thema wird vorausgesetzt, dass Sie den Setup-Prozess bereits abgeschlossen haben. Wenn Sie das EOP-Setup nicht abgeschlossen haben, finden Sie weitere Informationen unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md).
  
## <a name="use-a-test-domain"></a>Verwenden einer Testdomäne

Es wird empfohlen, eine Testdomäne, eine Unterdomäne oder eine Domäne von geringem Volumen zu verwenden, um Dienstfunktionen zu prüfen, bevor Sie sie auf Ihren Produktionsdomänen mit höherem Volumen implementieren.
  
## <a name="synchronize-recipients"></a>Synchronisieren von Empfängern

Wenn Ihre Organisation über vorhandene Benutzerkonten in einer lokalen Active Directory-Umgebung verfügt, können Sie diese Konten mit Azure Active Directory in der Cloud synchronisieren. Es wird empfohlen, Verzeichnissynchronisierung zu verwenden. Weitere Informationen über die Vorteile der Verzeichnissynchronisierung und über die Schritte zu ihrer Einrichtung finden Sie unter [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).
  
## <a name="spf-record-customization-to-help-prevent-spoofing"></a>SPF-Eintrags-Anpassung zur Verhinderung von Spoofing

Bei der Einrichtung von EOP haben Sie zu Ihren DNS-Datensätzen einen SPF-Datensatz (Sender Policy Framework) für EOP hinzugefügt. Der SPF-Datensatz erleichtert die Vermeidung von Spoofing. Weitere Informationen darüber, wie ein SPF-Eintrag Spoofing verhindert und wie Sie Ihre lokalen IP-Adressen zum SPF-Eintrag hinzufügen können, finden Sie unter [Einrichten von SPF in Office 365, um Spoofing zu verhindern](set-up-spf-in-office-365-to-help-prevent-spoofing.md). 
  
## <a name="set-anti-spam-options"></a>Festlegen von Antispamoptionen

Verwalten Sie die Filter der Verbindungseinstellungen durch das Hinzufügen von IP-Adressen zur IP-Zulassungs- und IP-Sperrliste, indem Sie die Option **Liste sicherer Adressen** aktivieren, wodurch die Anzahl der falsch positiven Nachrichten (Nachrichten, die fälschlicherweise als Spam eingestuft werden) reduziert werden sollte. Weitere Informationen finden Sie unter [Konfigurieren der Verbindungsfilter Richtlinie](configure-the-connection-filter-policy.md). Weitere Spameinstellungen, die für die gesamte Organisation gelten, sehen Sie sich an, [wie Sie verhindern können, dass echte e-Mails in Office 365 als Spam markiert werden](../../compliance/prevent-email-from-being-marked-as-spam.md) , oder [wie Spam-e-Mails in Office 365 reduziert](reduce-spam-email.md)werden). Diese Themen sind hilfreich, wenn Sie über die Steuerung auf Administratorebene verfügen und false positives oder falsch negative Ergebnisse verhindern möchten.
  
Verwalten Sie Ihre Inhaltsfilter, indem Sie die Standardeinstellungen überprüfen und optional ändern. Sie können beispielsweise die Aktion für das geschehen mit Spam erkannten Nachrichten ändern. Wenn Sie einen aggressiven Ansatz für die Spamfilterung verfolgen möchten, können Sie erweiterte Spamfilter Optionen konfigurieren. Es wird empfohlen, dass Sie diese Optionen zuerst testen, bevor Sie Sie in Ihrer Produktionsumgebung implementieren (indem Sie Sie aktivieren) Es wird empfohlen, dass Organisationen, die sich für Phishing befassen, die Option **SPF Record: Hard Fail** aktivieren. Weitere Informationen finden Sie unter [configure your Spamfilter Policies](configure-your-spam-filter-policies.md) and [Advanced Spam Filtering Options](advanced-spam-filtering-asf-options.md).
  
> [!IMPORTANT]
> Wenn Sie die Standardaktion für den Inhaltsfilter verwenden, verschieben Sie die Nachricht in den **Junk-e-Mail-Ordner**, um sicherzustellen, dass diese Aktion mit lokalen Postfächern funktioniert, müssen Sie Nachrichtenfluss Regeln (auch bekannt als Transportregeln) auf Ihrem lokalen Exchange-Server konfigurieren. Server zum Erkennen von Spam Kopfzeilen, die von EoP hinzugefügt wurden. Weitere Informationen finden Sie unter [Sicherstellen, dass Spam an die Junk-E-Mail-Ordner der einzelnen Benutzer geleitet wird](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).
  
Es wird empfohlen, die häufig gestellten [Fragen zum Anti-Spam-Schutz](anti-spam-protection-faq.md)zu lesen, einschließlich des Abschnitts bewährte Methoden für ausgehende Nachrichten, mit denen sichergestellt wird, dass Ihre ausgehenden e-Mails zugestellt werden.
  
Sie können falsche negative Meldungen (Spam) und falsche positive Meldungen (kein Spam) auf verschiedene Weise an Microsoft zur Analyse schicken. Ausführliche Informationen finden Sie unter [Submit Spam, Non-Spam, and Phishing Scam messages to Microsoft for Analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).
  
## <a name="set-anti-malware-options"></a>Festlegen von Antimalwareoptionen

Sie können Ihre Malwarefiltereinstellungen in der Exchange-Verwaltungskonsole (EAC) überprüfen und anpassen. Weitere Informationen finden Sie unter [configure Anti-Malware Policies](configure-anti-malware-policies.md). Außerdem empfehlen wir Ihnen, sich in unseren häufig gestellten Fragen und Antworten zum Schutz vor Schadsoftware in unseren [FAQ zu Anti-Malware Protection ](anti-malware-protection-faq-eop.md)zu lesen.
  
Wenn Sie befürchten, dass ausführbare Dateien Schadsoftware enthalten könnten, können Sie eine Exchange-Nachrichtenflussregel erstellen, durch die alle E-Mail-Anhänge mit ausführbaren Inhalten blockiert werden. Befolgen Sie die Schritte unter [How to Reduce Malware Threats through File Attachment Blocking in Exchange Online Protection](https://support.microsoft.com/kb/2959596) , um die in [use Mail Flow Rules aufgeführten Dateitypen zu blockieren, um Nachrichtenanlagen in Exchange Online zu überprüfen](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).
  
Sie können den Filter für gängige Anlagetypen in der Exchange-Verwaltungskonsole verwenden. Wählen Sie **Schutz** \> für **Malware Filter**aus. Sie können eine e-Mail-Fluss Regel erstellen, die alle e-Mail-Anlagen mit ausführbaren Inhalten blockiert.
  
Für einen höheren Schutz empfehlen wir, auch einige oder alle der folgenden Erweiterungen mithilfe von Nachrichtenflussregeln zu blockieren: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh. Dies kann mithilfe der Bedingung **Mindestens eine Anlage... eine Dateierweiterung hat, die diese Wörter enthält** erfolgen.
  
Administratoren und Endbenutzer können Malware, die an den Filtern vorbei gelangt ist, oder Dateien, die fälschlicherweise als Malware erkannt wurden, zur Analyse an Microsoft übermitteln. Weitere Informationen finden Sie unter [Submitting malware and non-malware to Microsoft for analysis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).
  
## <a name="create-mail-flow-rules"></a>Erstellen von Nachrichtenflussregeln

Erstellen von Nachrichtenfluss Regeln oder benutzerdefinierten Filtern, um Ihre geschäftlichen Anforderungen zu erfüllen.
  
Wenn Sie eine neue Regel in die Produktion übernehmen, wählen Sie zunächst einen der Testmodi aus, um die Wirkung der Regeln zu überprüfen. Wenn Sie sicher sind, dass die Regel so funktioniert wie beabsichtigt, ändern Sie den Regelmodus in **Erzwingen**.
  
Beim Bereitstellen neuer Regeln sollten Sie in Erwägung ziehen, als zusätzliche Aktion **Schadensbericht generieren** hinzuzufügen, um die betreffende Regel zu überwachen.
  
Bei der Konfiguration einer Hybridbereitstellung, bei der ein Teil der Organisation lokal und ein Teil in Office 365 verwaltet wird, können Sie Regeln erstellen, die sich auf die gesamte Organisation anwenden lassen. Dies ist nur möglich, wenn Sie Bedingungen verwenden, die sowohl lokal als auch in Office 365 verfügbar sind. Die meisten Bedingungen stehen zwar in beiden Bereitstellungen zur Verfügung, doch sind einige davon nur für bestimmte Bereitstellungsszenarien geeignet. Weitere Informationen finden Sie unter [Nachrichtenfluss Regeln (Transportregeln) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
  
Wenn Sie in Ihrer Organisation E-Mail-Anlagen von Nachrichten während der Übermittlung überprüfen möchten, können Sie dazu Nachrichtenflussregeln einrichten. Führen Sie dann Aktionen für die überprüften Nachrichten basierend auf deren Inhalten oder Merkmalen dieser Anlagen durch. Weitere Informationen finden Sie unter [use Mail Flow Rules to Inspect Message Attachments in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments).
  
### <a name="phishing-and-spoofing-prevention"></a>Schutz vor Phishing und Spoofing

Sie können den Antiphishingschutz verbessern, indem Sie ermitteln, wann persönliche Informationen die Organisation in einer E-Mail verlassen. Beispielsweise können Sie die folgenden normalen Ausdrücke in Nachrichtenflussregeln verwenden, um die Übertragung persönlicher Finanzdaten oder Informationen, die urheberrechtlich geschützte Daten enthalten, zu erkennen:
  
- `\d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d`(MasterCard oder Visa)

- `\d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d`(American Express)

- `\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d`(eine beliebige 16-stellige Zahl)

- `\d\d\d\-\d\d\-\d\d\d\d`(Sozialversicherungsnummern)

Spam und Phishing können ebenfalls durch Blockieren eingehender bösartiger E-Mails erfolgreich verhindert werden, die scheinbar von Ihrer eigenen Domäne gesendet wurden. Sie können zum Beispiel eine Nachrichtenflussregel erstellen, die Nachrichten von Ihrer Firmendomäne an dieselbe Firmendomäne ablehnt, um diese Art von Absenderfilterung zu blockieren.
  
> [!CAUTION]
> Wir empfehlen Ihnen, diese Regel nur in solchen Fällen zu erstellen, in denen Sie sicher sind, dass keine legitime E-Mail von Ihrer Domäne über das Internet an Ihrem Mailserver gesendet wird. Dies kann in Fällen passieren, in denen eine Nachricht von einem Benutzer in Ihrer Organisation an einen externen Empfänger gesendet und anschließend an einen anderen Empfänger in Ihrer Organisation weitergeleitet wird. 
  
### <a name="extension-blocking"></a>Erweiterungsblockierung

Wenn Sie befürchten, dass ausführbare Dateien Schadsoftware enthalten könnten, können Sie Antischadsoftwarerichtlinien erstellen, durch die alle E-Mail-Anhänge mit ausführbaren Inhalten blockiert werden. Befolgen Sie die Schritte unter [configure Anti-Malware Policies](configure-anti-malware-policies.md).
  
Für einen höheren Schutz empfehlen wir, auch einige oder alle der folgenden Erweiterungen zu blockieren: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh.
  
## <a name="reporting-and-troubleshooting"></a>Berichterstellung und Problembehandlung

Behandeln allgemeiner Probleme und Trends mithilfe der Berichte im Admin Center. Mithilfe des Nachrichtenablaufverfolgungs-Tools können Sie nach einzelnen quellenspezifischen Daten zu einer Nachricht suchen. Weitere Informationen zu Berichten finden Sie unter [Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Weitere Informationen zum Nachrichtenablaufverfolgungs-Tool finden Sie unter [Trace an Email Message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message).
  
## <a name="for-more-information"></a>Weitere Informationen

[EOP - Allgemeine häufig gestellte Fragen](eop-general-faq.md)
  
[Hilfe und Support für EOP](help-and-support-for-eop.md)
  
[Verhindern, dass echte E-Mails in Office 365 als Spam gekennzeichnet werden](../../compliance/prevent-email-from-being-marked-as-spam.md)
  
[Reduzieren von Spam-E-Mails in Office 365](reduce-spam-email.md)
