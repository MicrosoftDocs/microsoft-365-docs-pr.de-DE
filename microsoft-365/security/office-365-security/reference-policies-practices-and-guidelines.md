---
title: Referenz Richtlinien, Methoden und Anleitungen
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft hat verschiedene Richtlinien und Verfahren entwickelt und mehrere bewährte Methoden für die Industrie eingeführt, um unsere Benutzer vor missbräuchlichen, unerwünschten oder böswilligen e-Mails zu schützen.
ms.openlocfilehash: a1e1e213c01eea5a07b616e72955303f21c6d2ae
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "39872061"
---
# <a name="reference-policies-practices-and-guidelines"></a>Referenz: Richtlinien, Methoden und Anleitungen

Microsoft ist bestrebt, die vertrauenswürdigste Benutzerfreundlichkeit im Internet bereitzustellen. Daher hat Microsoft verschiedenen Richtlinien, Verfahren entwickelt und mehrere bewährte Branchenmethoden übernommen, um unsere Benutzer vor beleidigenden, unerwünschten oder schädlichen E-Mails zu schützen. Absender, die versuchen E-Mails an Office 365-Benutzer zu senden, sollten sicherstellen, dass sie diese vollständig verstehen und die Anleitungen in diesem Artikel befolgen, um potenzielle Probleme bei der Zustellung zu vermeiden.

Wenn Sie nicht nach diesen Richtlinien und Anleitungen handeln, ist es möglich, dass unser Supportteam Sie nicht unterstützen kann. Wenn Sie die Richtlinien, Methoden und Anleitungen, die in diesem Artikel vorgestellt werden, beachten, und trotzdem Probleme bei der Übermittlung basierend auf der IP-Adresse des Absenders haben, führen Sie bitte die Schritte aus, um eine Delisting-Anforderung zu übermitteln. Anweisungen finden Sie unter [Verwenden des Listenentfernungsportals, um sich selbst aus der Liste der blockierten Absender von Office 365 zu entfernen](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="general-microsoft-policies"></a>Allgemeine Microsoft-Richtlinien

E-Mail-Nachrichten, die an Office 365-Benutzer gesendet werden, müssen allen Microsoft-Richtlinien entsprechen, die die Übertragung von E-Mails und die Verwendung von Office 365 regeln.

- Nutzungsbedingungen Office 365; insbesondere das Verbot der Verwendung des Diensts zum Verbreiten von Spam oder Malware

- [Microsoft-Servicevertrag](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Einhaltung von gesetzlichen Vorschriften

An Office 365-Benutzer gesendete E-Mails müssen alle geltenden Gesetze und Vorschriften für die E-Mail-Kommunikation in der entsprechenden Zuständigkeit einhalten.

- [CAN-SPAM Act: Compliance-Leitfaden für Unternehmen](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [„Remove Me"-Antworten und -Verantwortlichkeiten: E-Mail-Vermarkter müssen „Unsubscribe"-Ansprüche beachten](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)

## <a name="technical-guidelines"></a>Technische Richtlinien

An Office 365 gesendete E-Mail-Nachrichten sollten den jeweiligen Empfehlungen entsprechen, die in den folgenden Dokumenten aufgelistet werden (einige Links sind nur auf Englisch verfügbar).

- [RFC 2505: Anti-Spam Recommendations for SMTP MTAs](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP Service Extension for Command Pipelining](https://www.ietf.org/rfc/rfc2920.txt)

Darüber hinaus müssen E-Mail-Server, die eine Verbindung mit Office 365 herstellen, die folgenden Anforderungen erfüllen:

- Absender muss allen technischen Standards für die Übermittlung von Internet-E-Mails entsprechen - gemäß der Veröffentlichungen der Internet Engineering Task Force (IETF) von The Internet Society, einschließlich RFC 5321, RFC 5322 und anderen.

- Nachdem ein numerischer SMTP-Antwortfehlercode zwischen 500 und 599 (auch bekannt als permanenter Unzustellbarkeitsbericht oder NDR) ausgegeben wurde, darf der Absender nicht erneut versuchen, dem Empfänger die Nachricht zuzustellen.

- Nach mehreren Unzustellbarkeitsberichte, darf der Absender nicht weiter versuchen, E-Mails an diesen Empfänger zu senden.

- Nachrichten dürfen nicht über unsichere E-Mail-Relay- oder Proxyserver übertragen werden.

- Der Mechanismus für die Entfernung aus einzelnen Listen oder allen vom Absender gehosteten Listen muss klar dokumentiert und für Empfänger einfach zu finden und zu verwenden sein.

- Verbindungen aus dynamischen IP-Adressräumen werden möglicherweise nicht akzeptiert.

- E-Mail-Server müssen gültige Reverse-DNS-Einträge haben.

## <a name="reputation-management"></a>Zuverlässigkeitsverwaltung

Absender, ISPs und andere Dienstanbietern sollten die Zuverlässigkeit Ihrer ausgehenden IP-Adressen aktiv verwalten.

## <a name="office-365-limits"></a>Office 365-Beschränkungen

Absender müssen die Office 365-Beschränkungen einhalten, die in [Beschränkungen von Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits) aufgeführt werden.

## <a name="email-delivery-resources-and-organizations"></a>E-Mail-Übermittlungsressourcen und -Organisationen

Microsoft arbeitet aktiv mit Branchenvertretern und Dienstanbietern zusammen, um das Internet- und das E-Mail-Ökosystem zu verbessern. Diese Organisationen haben Dokumente mit bewährten Methoden veröffentlicht, die wir unterstützen und für Absender empfehlen. Dadurch wird Ihre Möglichkeit, E-Mails zwischen verschiedenen E-Mail-Dienstanbietern auf der ganzen Welt zu übermitteln, verbessert.

- [Messaging Malware Mobile Anti-Abuse Working Group](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.otalliance.org/resources)

- [Email Sender &amp; Provider Coalition](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Missbrauchs- und Spamberichte

Melden Sie [Junk-e-Mails und Phishing-Scams in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), um unrechtmäßige, missbräuchliche, unerwünschte oder böswillige e-Mails zu melden. Das Senden dieser Kommunikationstypen ist eine Verletzung der Microsoft-Richtlinie, und entsprechende Maßnahmen werden bei bestätigten Berichten ergriffen.

## <a name="law-enforcement"></a>Strafverfolgung

Wenn Sie in der Strafverfolgung tätig sind und Microsoft Corporation gesetzliche Dokumentationen zu Office 365 bereitstellen möchten oder wenn Sie Fragen zu gesetzlichen Dokumentationen haben, die Sie an Microsoft übermittelt haben, wenden Sie sich unter (1) (425) 722-1299 an Microsoft.
