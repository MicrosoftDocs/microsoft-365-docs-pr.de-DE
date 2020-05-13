---
title: Referenz Richtlinien, Methoden und Anleitungen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
ms.openlocfilehash: 9684453503329e955c21051885c5d93e8c927c48
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208210"
---
# <a name="reference-policies-practices-and-guidelines"></a>Referenz: Richtlinien, Methoden und Anleitungen

Microsoft ist bestrebt, die vertrauenswürdigste Benutzerfreundlichkeit im Internet bereitzustellen. Daher hat Microsoft verschiedenen Richtlinien, Verfahren entwickelt und mehrere bewährte Branchenmethoden übernommen, um unsere Benutzer vor beleidigenden, unerwünschten oder schädlichen E-Mails zu schützen. Absender, die versuchen, e-Mails an Benutzer zu senden, sollten sicherstellen, dass Sie die Anleitungen in diesem Artikel vollständig verstehen und befolgen, um diese Bemühungen zu unterstützen und potenzielle Zustellungsprobleme zu vermeiden.

Wenn Sie nicht nach diesen Richtlinien und Anleitungen handeln, ist es möglich, dass unser Supportteam Sie nicht unterstützen kann. Wenn Sie die Richtlinien, Methoden und Anleitungen, die in diesem Artikel vorgestellt werden, beachten, und trotzdem Probleme bei der Übermittlung basierend auf der IP-Adresse des Absenders haben, führen Sie bitte die Schritte aus, um eine Delisting-Anforderung zu übermitteln. Anweisungen finden Sie unter [Verwenden des Delist-Portals, um sich selbst aus der Liste blockierter Absender zu entfernen](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="general-microsoft-policies"></a>Allgemeine Microsoft-Richtlinien

An Microsoft 365-Benutzer gesendete e-Mails müssen alle Microsoft-Richtlinien für die e-Mail-Übermittlung und die Verwendung von Microsoft 365 einhalten.

- Für Microsoft 365 geltende Dienstbedingungen; insbesondere das Verbot der Verwendung des Diensts zum Spam oder zur Verteilung von Schadsoftware.

- [Microsoft-Servicevertrag](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Einhaltung von gesetzlichen Vorschriften

An Microsoft 365-Benutzer gesendete e-Mails müssen alle geltenden Gesetze und Vorschriften für die e-Mail-Kommunikation in der jeweiligen Jurisdiktion einhalten.

- [CAN-SPAM Act: Compliance-Leitfaden für Unternehmen](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [„Remove Me"-Antworten und -Verantwortlichkeiten: E-Mail-Vermarkter müssen „Unsubscribe"-Ansprüche beachten](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)

## <a name="technical-guidelines"></a>Technische Richtlinien

E-Mail-Nachrichten, die an Microsoft 365 gesendet werden, sollten den einschlägigen Empfehlungen entsprechen, die in den unten stehenden Dokumenten aufgeführt sind (einige Links sind nur in Englisch verfügbar).

- [RFC 2505: Anti-Spam Recommendations for SMTP MTAs](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP Service Extension for Command Pipelining](https://www.ietf.org/rfc/rfc2920.txt)

Darüber hinaus müssen e-Mail-Server, die eine Verbindung mit Microsoft 365 herstellen, die folgenden Anforderungen erfüllen:

- Absender muss allen technischen Standards für die Übermittlung von Internet-E-Mails entsprechen - gemäß der Veröffentlichungen der Internet Engineering Task Force (IETF) von The Internet Society, einschließlich RFC 5321, RFC 5322 und anderen.

- Nachdem ein numerischer SMTP-Antwortfehlercode zwischen 500 und 599 (auch bekannt als permanenter Unzustellbarkeitsbericht oder NDR) ausgegeben wurde, darf der Absender nicht erneut versuchen, dem Empfänger die Nachricht zuzustellen.

- Nach mehreren Unzustellbarkeitsberichte, darf der Absender nicht weiter versuchen, E-Mails an diesen Empfänger zu senden.

- Nachrichten dürfen nicht über unsichere E-Mail-Relay- oder Proxyserver übertragen werden.

- Der Mechanismus für die Entfernung aus einzelnen Listen oder allen vom Absender gehosteten Listen muss klar dokumentiert und für Empfänger einfach zu finden und zu verwenden sein.

- Verbindungen aus dynamischen IP-Adressräumen werden möglicherweise nicht akzeptiert.

- E-Mail-Server müssen gültige Reverse-DNS-Einträge haben.

## <a name="reputation-management"></a>Zuverlässigkeitsverwaltung

Absender, ISPs und andere Dienstanbietern sollten die Zuverlässigkeit Ihrer ausgehenden IP-Adressen aktiv verwalten.

## <a name="microsoft-365-limits"></a>Microsoft 365-Beschränkungen

Absender müssen die Microsoft 365-Grenzwerte einhalten, die unter [Exchange Online Protection Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)aufgeführt sind.

## <a name="email-delivery-resources-and-organizations"></a>E-Mail-Übermittlungsressourcen und -Organisationen

Microsoft arbeitet aktiv mit Branchenvertretern und Dienstanbietern zusammen, um das Internet- und das E-Mail-Ökosystem zu verbessern. Diese Organisationen haben Dokumente mit bewährten Methoden veröffentlicht, die wir unterstützen und für Absender empfehlen. Dadurch wird Ihre Möglichkeit, E-Mails zwischen verschiedenen E-Mail-Dienstanbietern auf der ganzen Welt zu übermitteln, verbessert.

- [Messaging Malware Mobile Anti-Abuse Working Group](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.otalliance.org/resources)

- [E-Mail-Absender & Anbieter Koalition](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Missbrauchs- und Spamberichte

Informationen zum Melden von unrechtmäßigen, missbräuchlichen, unerwünschten oder böswilligen e-Mails finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md). Das Senden dieser Kommunikationstypen stellt einen Verstoß gegen die Microsoft-Richtlinie dar, und es werden entsprechende Aktionen für bestätigte Berichte ausgeführt.

## <a name="law-enforcement"></a>Strafverfolgung

Wenn Sie in der Strafverfolgung tätig sind und Microsoft Corporation gesetzliche Dokumentationen zu Office 365 bereitstellen möchten oder wenn Sie Fragen zu gesetzlichen Dokumentationen haben, die Sie an Microsoft übermittelt haben, wenden Sie sich unter (1) (425) 722-1299 an Microsoft.
