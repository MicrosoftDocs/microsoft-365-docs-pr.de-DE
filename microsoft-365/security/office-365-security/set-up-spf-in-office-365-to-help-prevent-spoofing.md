---
title: Einrichten von SPF zum Verhindern von Spoofing
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie ein DNS-Eintrag (Domain Name Service) für die Verwendung von SPF (Sender Policy Framework) mit Ihrer benutzerdefinierten Domäne in Office 365 aktualisiert wird.
ms.openlocfilehash: 9d5d300b7397d719d9ab85139cd27d912627a3ff
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035308"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>Einrichten von SPF zum Verhindern von Spoofing

 **Zusammenfassung:** Dieser Artikel enthält Informationen zum Aktualisieren des DNS-Eintrags (Domain Name Service) für die Verwendung von SPF (Sender Policy Framework) mit Ihrer benutzerdefinierten Domäne in Office 365. SPF hilft bei der Überprüfung ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne gesendet werden.

Für die Verwendung einer benutzerdefinierten Domäne erfordert Office 365, einen SPF (Sender Policy Framework) TXT-Eintrag Ihrem DNS-Eintrag hinzuzufügen, um Spoofing zu verhindern. SPF identifiziert, welche E-Mail-Server zum Senden von E-Mails in Ihrem Auftrag berechtigt sind. Im Grunde trägt SPF zusammen mit DKIM, DMARC und anderen Technologien von Office 365 dazu bei, Spoofing und Phishing zu verhindern. SPF wird als TXT-Eintrag hinzugefügt, der von DNS verwendet wird, um zu identifizieren, welche E-Mail-Server E-Mails im Auftrag Ihrer benutzerdefinierten Domäne senden können. Empfänger können auf den SPF TXT-Eintrag zugreifen, um festzustellen, ob eine Nachricht von Ihrer benutzerdefinierten Domäne über einen autorisierten Messagingserver kommt.

Nehmen wir beispielsweise an, dass Ihre benutzerdefinierte Domäne „contoso.com“ Office 365 verwendet. Sie fügen einen SPF TXT-Eintrag hinzu, der die Office 365-Messagingserver als berechtigte E-Mail-Server für Ihre Domäne auflistet. Wenn der empfangende Messagingserver eine Nachricht von „joe@contoso.com“ erhält, sucht der Server im SPF TXT-Eintrag nach „contoso.com“ und findet heraus, ob die Nachricht gültig ist. Wenn der empfangende Server herausfindet, dass die Nachricht von einem anderen Server als den Office 365-Messagingservern kommt, die im SPF-Eintrag aufgelistet sind, kann der empfangende E-Mail-Server die Nachricht als Spam ablehnen.

Wenn Ihre benutzerdefinierte Domäne keinen SPF TXT-Eintrag aufweist, können einige empfangende Server die Nachricht auch sofort ablehnen. Das liegt daran, dass der empfangende Server nicht überprüfen kann, ob die Nachricht von einem autorisierten Messagingserver stammt.

Wenn Sie bereits E-Mail für Office 365 eingerichtet haben, haben Sie bereits die Messagingserver von Microsoft in DNS als SPF TXT-Eintrag hinzugefügt. Es gibt jedoch einige Fälle, in denen Sie Ihren SPF TXT-Eintrag in DNS möglicherweise aktualisieren müssen. Beispiel:

- In früheren Versionen mussten Sie Ihrer benutzerdefinierten Domäne einen anderen SPF TXT-Eintrag hinzufügen, wenn Sie SharePoint Online verwendet haben. Dies ist nicht mehr erforderlich. Diese Änderung sollte das Risiko reduzieren, dass SharePoint Online-Benachrichtigungsnachrichten im Junk-E-Mail-Ordner landen. Aktualisieren Sie Ihren SPF TXT-Eintrag, wenn Sie die Beschränkung von 10 Lookups erreichen und Fehlermeldungen erhalten wie z. B. „Suchlimit überschritten" und „Zu viele Hops".

- Wenn Sie eine Hybridumgebung mit Office 365 und Exchange (lokal) haben.

- Sie möchten DKIM und DMARC einrichten (empfohlen).

## <a name="updating-your-spf-txt-record-for-office-365"></a>Aktualisieren Ihres SPF TXT-Eintrags für Office 365

Bevor Sie den TXT-Eintrag im DNS aktualisieren, müssen Sie einige Informationen sammeln und das Format des Eintrags bestimmen. Auf diese Weise können Sie DNS-Fehler vermeiden. Erweiterte Beispiele, eine ausführlichere Erläuterung zur unterstützten SPF-Syntax finden Sie unter [Funktionsweise von SPF zur Verhinderung von Spoofing und Phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

Sammeln Sie folgende Informationen:

- Den aktuellen SPF TXT-Eintrag für Ihre benutzerdefinierte Domäne. Anweisungen finden Sie unter [Sammeln der zum Erstellen von Office 365-DNS-Einträgen erforderlichen Informationen](https://docs.microsoft.com/office365/admin/get-help-with-domains/information-for-dns-records).

- Externe IP-Adressen aller lokalen Messaging-Server. Zum Beispiel **131.107.2.200**.

- Domänennamen für alle Domänen von Drittanbietern, die Sie in Ihren SPF TXT-Eintrag einschließen müssen. Einige Massen-E-Mail-Anbieter haben Unterdomänen für ihre Kunden eingerichtet. Das Unternehmen MailChimp hat beispielsweise **servers.mcsv.net** eingerichtet.

- Bestimmen Sie, welche Erzwingungsregel Sie für Ihren SPF TXT-Eintrag verwenden möchten. Wir empfehlen **-all**. Weitere Informationen zu anderen Syntaxoptionen finden Sie unter [Syntax des SPF TXT-Eintrags für Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).

### <a name="to-add-or-update-your-spf-txt-record"></a>So aktualisieren Sie den SPF TXT-Eintrag oder fügen ihn hinzu

1. Machen Sie sich mit der SFP-Syntax in der folgenden Tabelle vertraut.

   ||**Wenn Sie Folgendes verwenden ...**|**Für Kunden üblich?**|**Fügen Sie Folgendes hinzu ...**|
   |:-----|:-----|:-----|:-----|
   |1|Beliebiges E-Mail-System (erforderlich)|Standard. Alle SPF TXT-Einträge beginnen mit dem folgenden Wert|v=spf1|
   |2|Exchange Online|Standard|include:spf.protection.outlook.com|
   |3|Nur dediziert für Exchange Online|Kein Standard|ip4:23.103.224.0/19 ip4:206.191.224.0/19 ip4:40.103.0.0/16 include:spf.protection.outlook.com|
   |4|Office 365 Deutschland, nur Microsoft Cloud Deutschland|Kein Standard|include:spf.protection.outlook.de|
   |5|Drittanbieter-E-Mail-System|Kein Standard|include:\<Domänenname\>  <br/> Wobei „Domänenname“ dem Domänennamen des Drittanbieter-E-Mail-Systems entspricht.|
   |6|Lokales E-Mail-System Zum Beispiel Exchange Online Protection und ein anderes E-Mail-System|Kein Standard| Verwenden Sie einen der folgenden Einträge für jedes zusätzliche E-Mail-System: <br> ip4:\<_IP address_\>  <br/>  ip6:\<_IP address_\>  <br/>  include:\<_domain name_\>  <br/>  Dabei steht der Wert von \<_IP address_\> für die IP-Adresse des anderen E-Mail-Systems und \<_domain name_\> für den Domänennamen des anderen E-Mail-Systems, das E-Mails im Auftrag Ihrer Domäne sendet.|
   |7|Beliebiges E-Mail-System (erforderlich)|Standard. Alle SPF TXT-Einträge enden mit diesem Wert|\< _enforcement rule_\>  <br/> Kann einer von mehreren Werten sein. Es wird empfohlen, **-all** zu verwenden.|

2. Erstellen Sie Ihren SPF TXT-Eintrag, falls noch nicht geschehen, indem Sie die Syntax aus der Tabelle verwenden:

   Wenn Sie in Office 365 vollständig gehostet werden (Sie haben also keine lokalen E-Mail-Server), sieht Ihr SPF TXT-Eintrag wie folgt aus und enthält Zeilen 1, 2 und 7:

   `v=spf1 include:spf.protection.outlook.com -all`

   Dies ist der häufigste SPF TXT-Eintrag. Dieser Eintrag eignet sich für fast alle Benutzer, unabhängig davon, ob sich Ihr Microsoft-Rechenzentrum in den USA, in Europa (einschließlich Deutschland) oder an einem anderen Standort befindet.

   Wenn Sie Office 365 Deutschland, Teil von Microsoft Cloud Deutschland, erworben haben, sollten Sie jedoch die Include-Anweisung aus Zeile 4 anstelle von Zeile 2 verwenden. Wenn Sie vollständig in Office 365 Deutschland gehostet werden (Sie haben also keine lokalen E-Mail-Server), sieht Ihr SPF TXT-Eintrag wie folgt aus und enthält Zeilen 1, 4 und 7:

   `v=spf1 include:spf.protection.outlook.de -all`

   Wenn Sie bereits in Office 365 bereitgestellt und Ihre SPF TXT-Einträge für Ihre benutzerdefinierte Domäne eingerichtet haben und anschließend zu Office 365 Deutschland migrieren möchten, müssen Sie Ihren SPF TXT-Eintrag aktualisieren. Ändern Sie dazu **include:spf.protection.outlook.com** in **include:spf.protection.outlook.de**.

3. Nachdem Sie Ihren SPF TXT-Eintrag erstellt haben, müssen Sie den Eintrag in DNS aktualisieren. Sie dürfen nur einen SPF TXT-Eintrag für eine Domäne haben. Wenn ein SPF TXT-Eintrag vorhanden ist, müssen Sie den vorhandenen Eintrag aktualisieren, statt einen neuen Eintrag hinzuzufügen. Wechseln Sie zu [Erstellen von DNS-Einträgen für Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), und klicken Sie dann auf den Link für Ihren DNS-Hostinganbieter.

4. Testen Sie Ihren SPF TXT-Eintrag.

## <a name="more-information-about-spf"></a>Weitere Informationen zu SPF

Erweiterte Beispiele, eine ausführlichere Erläuterung zur unterstützten SPF-Syntax, zu Spoofing, zur Problembehandlung und zur Unterstützung von SPF durch Office 365 finden Sie unter [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

## <a name="next-steps-after-you-set-up-spf-for-office-365"></a>Nächste Schritte: Nach dem Einrichten von SPF für Office 365

Gibt es Probleme mit Ihrem SPF TXT-Eintrag? Lesen Sie [Problembehandlung: Bewährte Methoden für SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

 Obwohl SPF Spoofing verhindern soll, gibt es Spoofingtechniken, gegen die SPF nicht schützen kann. Zum Einrichten eines entsprechenden Schutzes sollten Sie nach dem Einrichten von SPF auch DKIM und DMARC für Office 365 konfigurieren. Die ersten Schritte finden Sie unter [Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet werden](use-dkim-to-validate-outbound-email.md). Lesen Sie anschließend [Verwenden von DMARC zum Überprüfen von E-Mails in Office 365](use-dmarc-to-validate-email.md).
