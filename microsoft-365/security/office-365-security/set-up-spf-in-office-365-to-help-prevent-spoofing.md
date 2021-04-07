---
title: Einrichten von SPF zum Verhindern von Spoofing
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie ein DNS-Eintrag (Domain Name Service) für die Verwendung von SPF (Sender Policy Framework) mit Ihrer benutzerdefinierten Domäne in Office 365 aktualisiert wird.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0a2c400e77c83fa61e276dee1d870835d466b5af
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599547"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>Einrichten von SPF zum Verhindern von Spoofing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Dieser Artikel enthält Informationen zum Aktualisieren eines DNS-Eintrags (Domain Name Service) für die Verwendung von SPF (Sender Policy Framework) -E-Mail-Authentifizierung mit Ihrer benutzerdefinierten Domäne in Office 365.

SPF hilft bei der Überprüfung ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne gesendet werden. Es ist ein erster Schritt zur Einrichtung der anderen empfohlenen E-Mail-Authentifizierungsmethoden DMARC und DKIM (zwei weitere in Office 365 unterstützte E-Mail-Authentifizierungsmethoden).

## <a name="prerequisites"></a>Voraussetzungen

> [!IMPORTANT]
> Wenn Sie ein **kleines Unternehmen** sind oder mit IP-Adressen oder DNS-Konfigurationen nicht vertraut sind, wenden Sie sich an Ihre Internet-Domänenregistrierungsstelle (z. B. GoDaddy, Bluehost, web.com), um Hilfe zur DNS-Konfiguration von SPF (und anderen E-Mail-Authentifizierungsmethoden) zu erhalten. *Ebenfalls*, wenn Sie keine benutzerdefinierte URL gekauft haben oder verwenden (d. h. die URL, die Sie und Ihre Kunden durchsuchen, um Office 365 zu erreichen, endet auf **onmicrosoft.com**), wurde SPF für Sie im Office 365-Dienst eingerichtet. In diesem Fall sind keine weiteren Schritte mehr erforderlich. Vielen Dank fürs Lesen.

Bevor Sie den SPF TXT-Eintrag für Office 365 im externen DNS erstellen oder aktualisieren, müssen Sie einige Informationen sammeln, die für die Erstellung des Eintrags erforderlich sind. Erweiterte Beispiele und eine ausführlichere Erläuterung zur unterstützten SPF-Syntax finden Sie unter [Funktionsweise von SPF zur Verhinderung von Spoofing und Phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

Sammeln Sie folgende Informationen:

- Den aktuellen SPF TXT-Eintrag für Ihre benutzerdefinierte Domäne (falls vorhanden). Anweisungen finden Sie unter [Sammeln der zum Erstellen von Office 365-DNS-Einträgen erforderlichen Informationen](../../admin/get-help-with-domains/information-for-dns-records.md).

- Gehen Sie zu Ihrem/Ihren Nachrichten-Server(n) und ermitteln Sie die externen IP-Adressen (die von allen lokalen Nachrichten-Servern benötigt werden). Beispiel: **131.107.2.200**.

- Domänennamen für alle Domänen von Drittanbietern, die Sie in Ihren SPF TXT-Eintrag einschließen müssen. Einige Massen-E-Mail-Anbieter haben Unterdomänen für ihre Kunden eingerichtet. Das Unternehmen MailChimp hat beispielsweise **servers.mcsv.net** eingerichtet.

- Finden Sie heraus, welche Erzwingungsregel Sie für Ihren SPF TXT-Eintrag verwenden möchten. Die Regel **-all** wird empfohlen. Weitere Informationen zu anderen Syntaxoptionen finden Sie unter [Syntax des SPF TXT-Eintrags für Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).

> [!IMPORTANT]
> Für die Verwendung einer benutzerdefinierten Domäne erfordert Office 365, einen SPF (Sender Policy Framework) TXT-Eintrag Ihrem DNS-Eintrag hinzuzufügen, um Spoofing zu verhindern.

## <a name="create-or-update-your-spf-txt-record"></a>Erstellen oder aktualisieren Sie Ihren SPF TXT-Eintrag

1. Machen Sie sich mit der SPF-Syntax in der folgenden Tabelle vertraut.

   ****

   |Element|Wenn Sie Folgendes verwenden...|Für Kunden üblich?|Fügen Sie Folgendes hinzu ...|
   |---|---|---|---|
   |1|Beliebiges E-Mail-System (erforderlich)|Standard. Alle SPF TXT-Einträge beginnen mit dem folgenden Wert|`v=spf1`|
   |2|Exchange Online|Standard|`include:spf.protection.outlook.com`|
   |3|Nur dediziert für Exchange Online|Kein Standard|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |4|Office 365 Deutschland, nur Microsoft Cloud Deutschland|Kein Standard|`include:spf.protection.outlook.de`|
   |5|Drittanbieter-E-Mail-System|Kein Standard|`include:<domain_name>` <p> \<domain_name\> entspricht dem Domänennamen des Drittanbieter-E-Mail-Systems.|
   |6|Lokales E-Mail-System. Beispielsweise Exchange Online Protection und ein anderes E-Mail-System|Kein Standard|Verwenden Sie einen der folgenden Einträge für jedes zusätzliche E-Mail-System: <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> \<IP_address\> und \<domain_name\> entsprechen jeweils der IP-Adresse und der Domäne des anderen E-Mail-Systems, das E-Mails im Auftrag Ihrer Domäne sendet.|
   |7|Beliebiges E-Mail-System (erforderlich)|Standard. Alle SPF TXT-Einträge enden mit diesem Wert|`<enforcement rule>` <p> Kann einer von mehreren Werten sein. Empfohlen wird der Wert `-all`.|
   |

2. Erstellen Sie Ihren SPF TXT-Eintrag, falls noch nicht geschehen, indem Sie die Syntax aus der Tabelle verwenden.

   Wenn Sie in Office 365 vollständig gehostet werden (Sie haben also keine lokalen E-Mail-Server), sieht Ihr SPF TXT-Eintrag wie folgt aus und enthält Zeilen 1, 2 und 7:

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   Dies ist der häufigste SPF TXT-Eintrag. Dieser Eintrag eignet sich für fast alle Benutzer, unabhängig davon, ob sich Ihr Microsoft-Rechenzentrum in den USA, in Europa (einschließlich Deutschland) oder an einem anderen Standort befindet.

   Wenn Sie Office 365 Deutschland, Teil von Microsoft Cloud Deutschland, erworben haben, sollten Sie jedoch die Include-Anweisung aus Zeile 4 anstelle von Zeile 2 verwenden. Wenn Sie vollständig in Office 365 Deutschland gehostet werden (Sie haben also keine lokalen E-Mail-Server), sieht Ihr SPF TXT-Eintrag wie folgt aus und enthält Zeilen 1, 4 und 7:

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   Wenn Sie bereits in Office 365 bereitgestellt und Ihre SPF TXT-Einträge für Ihre benutzerdefinierte Domäne eingerichtet haben und anschließend zu Office 365 Deutschland migrieren möchten, müssen Sie Ihren SPF TXT-Eintrag aktualisieren. Ändern Sie dazu `include:spf.protection.outlook.com` in `include:spf.protection.outlook.de`.

3. Nachdem Sie Ihren SPF TXT-Eintrag erstellt haben, müssen Sie den Eintrag in DNS aktualisieren. Sie dürfen nur einen SPF TXT-Eintrag für eine Domäne haben. Wenn ein SPF TXT-Eintrag vorhanden ist, müssen Sie den vorhandenen Eintrag aktualisieren, statt einen neuen Eintrag hinzuzufügen. Wechseln Sie zu [Erstellen von DNS-Einträgen für Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md), und klicken Sie dann auf den Link für Ihren DNS-Hostinganbieter.

4. Testen Sie Ihren SPF TXT-Eintrag.

## <a name="how-to-handle-subdomains"></a>Wie kann ich Subdomänen behandeln?

Es ist wichtig zu beachten, *dass Sie für jede Subdomäne einen separaten Eintrag erstellen müssen, da Subdomänen nicht den SPF-Eintrag der Domäne der obersten Ebene erben*.

Ein zusätzlicher Wildcard-SPF-Eintrag (`*.`) ist für jede Domäne und Subdomäne erforderlich, um Angreifer daran zu hindern, E-Mails zu versenden, die vorgeben, von nicht existierenden Subdomänen zu stammen. Zum Beispiel:

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a>Problembehandlung von SPF

Gibt es Probleme mit Ihrem SPF TXT-Eintrag? Lesen Sie [Problembehandlung: Bewährte Methoden für SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).


## <a name="what-does-spf-email-authentication-actually-do"></a>Was ist der Zweck der SPF-E-Mail-Authentifizierung?

SPF identifiziert, welche E-Mail-Server E-Mails in Ihrem Auftrag senden dürfen. Im Grunde trägt SPF zusammen mit DKIM, DMARC und anderen von Office 365 unterstützten Technologien dazu bei, Spoofing und Phishing zu verhindern. SPF wird als TXT-Eintrag hinzugefügt, der von DNS verwendet wird, um zu identifizieren, welche E-Mail-Server E-Mails im Auftrag Ihrer benutzerdefinierten Domäne senden können. Empfänger können auf den SPF TXT-Eintrag zugreifen, um festzustellen, ob eine Nachricht von Ihrer benutzerdefinierten Domäne über einen autorisierten Messagingserver kommt.

Nehmen wir beispielsweise an, dass Ihre benutzerdefinierte Domäne „contoso.com“ Office 365 verwendet. Sie fügen einen SPF TXT-Eintrag hinzu, der die Office 365-Messagingserver als berechtigte E-Mail-Server für Ihre Domäne auflistet. Wenn der empfangende Messagingserver eine Nachricht von „joe@contoso.com“ erhält, sucht der Server im SPF TXT-Eintrag nach „contoso.com“ und findet heraus, ob die Nachricht gültig ist. Wenn der empfangende Server herausfindet, dass die Nachricht von einem anderen Server als den Office 365-Messagingservern kommt, die im SPF-Eintrag aufgelistet sind, kann der empfangende E-Mail-Server die Nachricht als Spam ablehnen.

Wenn Ihre benutzerdefinierte Domäne keinen SPF TXT-Eintrag aufweist, können einige empfangende Server die Nachricht auch sofort ablehnen. Das liegt daran, dass der empfangende Server nicht überprüfen kann, ob die Nachricht von einem autorisierten Messagingserver stammt.

Wenn Sie bereits E-Mail für Office 365 eingerichtet haben, haben Sie bereits die Messagingserver von Microsoft in DNS als SPF TXT-Eintrag hinzugefügt. Es gibt jedoch einige Fälle, in denen Sie Ihren SPF TXT-Eintrag in DNS möglicherweise aktualisieren müssen. Beispiel:

- In früheren Versionen mussten Sie Ihrer benutzerdefinierten Domäne einen anderen SPF TXT-Eintrag hinzufügen, wenn Sie SharePoint Online verwendet haben. Dies ist nicht mehr erforderlich. Diese Änderung sollte das Risiko reduzieren, dass SharePoint Online-Benachrichtigungsnachrichten im Junk-E-Mail-Ordner landen. Aktualisieren Sie Ihren SPF TXT-Eintrag, wenn Sie die Beschränkung von 10 Lookups erreichen und Fehlermeldungen erhalten wie z. B. „Suchlimit überschritten" und „Zu viele Hops".

- Wenn Sie eine Hybridumgebung mit Office 365 und Exchange (lokal) haben.

- Sie möchten DKIM und DMARC einrichten (empfohlen).

## <a name="more-information-about-spf"></a>Weitere Informationen zu SPF

Erweiterte Beispiele, eine ausführlichere Erläuterung zur unterstützten SPF-Syntax, zu Spoofing, zur Problembehandlung und zur Unterstützung von SPF durch Office 365 finden Sie unter [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

## <a name="links-to-configure-dkim-and-dmarc"></a>Links, um DKIM und DMARC zu konfigurieren

 SPF ist dafür vorgesehen, Spoofing möglichst zu verhindern, es gibt aber Spoofing-Techniken, vor denen SPF nicht schützen kann. Um sich dagegen zu verteidigen, sollten Sie nach dem Einrichten von SPF auch DKIM und DMARC für Office 365 konfigurieren.

Das Ziel der [DKIM](use-dkim-to-validate-outbound-email.md)-E-Mail-Authentifizierung ist es, nachzuweisen, dass der Inhalt der E-Mail nicht manipuliert wurde.

Das Ziel der [DMARC](use-dmarc-to-validate-email.md)-E-Mail-Authentifizierung ist es, sicherzustellen, dass die SPF- und DKIM-Informationen mit der Absenderadresse übereinstimmen.
