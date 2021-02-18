---
title: Referenz Richtlinien, Methoden und Anleitungen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft hat verschiedene Richtlinien, Verfahren entwickelt und mehrere bewährte Methoden aus der Branche übernommen, um unsere Benutzer vor beleidigenden, unerwünschten oder schädlichen E-Mails zu schützen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1065fdef5f804214ca48f7ca54170e6e417490d7
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289199"
---
# <a name="reference-policies-practices-and-guidelines"></a>Referenz: Richtlinien, Methoden und Anleitungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft ist bestrebt, die vertrauenswürdigste Benutzerfreundlichkeit im Internet bereitzustellen. Daher hat Microsoft verschiedenen Richtlinien, Verfahren entwickelt und mehrere bewährte Branchenmethoden übernommen, um unsere Benutzer vor beleidigenden, unerwünschten oder schädlichen E-Mails zu schützen. Absender, die versuchen, E-Mails an Benutzer zu senden, sollten sicherstellen, dass sie die Anweisungen in diesem Artikel vollständig verstehen und folgen, um dabei zu helfen und potenzielle Zustellungsprobleme zu vermeiden.

Wenn Sie nicht nach diesen Richtlinien und Anleitungen handeln, ist es möglich, dass unser Supportteam Sie nicht unterstützen kann. Wenn Sie die Richtlinien, Methoden und Anleitungen, die in diesem Artikel vorgestellt werden, beachten, und trotzdem Probleme bei der Übermittlung basierend auf der IP-Adresse des Absenders haben, führen Sie bitte die Schritte aus, um eine Delisting-Anforderung zu übermitteln. Anweisungen finden Sie unter [Verwenden des Listendelist-Portals, um sich selbst aus der Liste blockierter Absender zu entfernen.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)

## <a name="general-microsoft-policies"></a>Allgemeine Microsoft-Richtlinien

An Microsoft 365-Benutzer gesendete E-Mails müssen allen Microsoft-Richtlinien entsprechen, die die Übertragung und Verwendung von Microsoft 365 regeln.

- Nutzungsbedingungen für Microsoft 365; insbesondere das Werben gegen die Verwendung des Diensts für Spam oder die Verteilung von Schadsoftware.

- [Microsoft-Servicevertrag](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Einhaltung von gesetzlichen Vorschriften

E-Mails, die an Microsoft 365-Benutzer gesendet werden, müssen alle geltenden Gesetze und Bestimmungen für die E-Mail-Kommunikation in der anwendbaren Gerichtsbarkeit einhalten.

- [CAN-SPAM Act: Compliance-Leitfaden für Unternehmen](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [„Remove Me"-Antworten und -Verantwortlichkeiten: E-Mail-Vermarkter müssen „Unsubscribe"-Ansprüche beachten](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>Technische Richtlinien

An Microsoft 365 gesendete E-Mails sollten den geltenden Empfehlungen entsprechen, die in den folgenden Dokumenten aufgeführt sind (einige Links sind nur in Englisch verfügbar).

- [RFC 2505: Anti-Spam Recommendations for SMTP MTAs](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP Service Extension for Command Pipelining](https://www.ietf.org/rfc/rfc2920.txt)

Darüber hinaus müssen E-Mail-Server, die eine Verbindung mit Microsoft 365 herstellen, die folgenden Anforderungen erfüllen:

- Absender muss allen technischen Standards für die Übermittlung von Internet-E-Mails entsprechen - gemäß der Veröffentlichungen der Internet Engineering Task Force (IETF) von The Internet Society, einschließlich RFC 5321, RFC 5322 und anderen.

- Nachdem ein numerischer SMTP-Antwortfehlercode zwischen 500 und 599 (auch bekannt als permanenter Unzustellbarkeitsbericht oder NDR) ausgegeben wurde, darf der Absender nicht erneut versuchen, dem Empfänger die Nachricht zuzustellen.

- Nach mehreren Unzustellbarkeitsberichte, darf der Absender nicht weiter versuchen, E-Mails an diesen Empfänger zu senden.

- Nachrichten dürfen nicht über unsichere E-Mail-Relay- oder Proxyserver übertragen werden.

- Der Mechanismus für die Entfernung aus einzelnen Listen oder allen vom Absender gehosteten Listen muss klar dokumentiert und für Empfänger einfach zu finden und zu verwenden sein.

- Verbindungen aus dynamischen IP-Adressräumen werden möglicherweise nicht akzeptiert.

- E-Mail-Server müssen gültige Reverse-DNS-Einträge haben.

## <a name="reputation-management"></a>Zuverlässigkeitsverwaltung

Absender, ISPs und andere Dienstanbietern sollten die Zuverlässigkeit Ihrer ausgehenden IP-Adressen aktiv verwalten.

## <a name="microsoft-365-limits"></a>Microsoft 365-Grenzwerte

Absender müssen die microsoft 365-Grenzwerte einhalten, die in [den Exchange Online Protection-Beschränkungen aufgeführt sind.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)

## <a name="email-delivery-resources-and-organizations"></a>E-Mail-Übermittlungsressourcen und -Organisationen

Microsoft arbeitet aktiv mit Branchenvertretern und Dienstanbietern zusammen, um das Internet- und das E-Mail-Ökosystem zu verbessern. Diese Organisationen haben Dokumente mit bewährten Methoden veröffentlicht, die wir unterstützen und für Absender empfehlen. Dadurch wird Ihre Möglichkeit, E-Mails zwischen verschiedenen E-Mail-Dienstanbietern auf der ganzen Welt zu übermitteln, verbessert.

- [Messaging Malware Mobile Anti-Abuse Working Group](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.otalliance.org/resources)

- [Email Sender & Provider Union](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Missbrauchs- und Spamberichte

Informationen zum Melden unrechtmäßiger, beleidigender, unerwünschter oder schädlicher E-Mails finden Sie unter "Nachrichten und Dateien an [Microsoft melden".](report-junk-email-messages-to-microsoft.md) Das Senden dieser Kommunikationsarten stellt einen Verstoß gegen die Microsoft-Richtlinie dar, und es werden geeignete Maßnahmen für bestätigte Berichte ergriffen.

## <a name="law-enforcement"></a>Strafverfolgung

Wenn Sie in der Strafverfolgung tätig sind und Microsoft Corporation gesetzliche Dokumentationen zu Office 365 bereitstellen möchten oder wenn Sie Fragen zu gesetzlichen Dokumentationen haben, die Sie an Microsoft übermittelt haben, wenden Sie sich unter (1) (425) 722-1299 an Microsoft.
