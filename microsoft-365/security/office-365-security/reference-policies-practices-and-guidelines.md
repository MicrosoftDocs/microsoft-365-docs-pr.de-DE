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
description: Microsoft hat verschiedene Richtlinien, Verfahren und verschiedene bewährte Methoden für die Branche entwickelt, um unsere Benutzer vor beleidigenden, unerwünschten oder schädlichen E-Mails zu schützen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f1a71b891829a2c9ea31502342c855db4126a6b5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205759"
---
# <a name="reference-policies-practices-and-guidelines"></a>Referenz: Richtlinien, Methoden und Anleitungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft ist bestrebt, die vertrauenswürdigste Benutzerfreundlichkeit im Internet bereitzustellen. Daher hat Microsoft verschiedenen Richtlinien, Verfahren entwickelt und mehrere bewährte Branchenmethoden übernommen, um unsere Benutzer vor beleidigenden, unerwünschten oder schädlichen E-Mails zu schützen. Absender, die versuchen, E-Mails an Benutzer zu senden, sollten sicherstellen, dass sie die Anweisungen in diesem Artikel vollständig verstehen und folgen, um bei dieser Arbeit zu helfen und potenzielle Übermittlungsprobleme zu vermeiden.

Wenn Sie nicht nach diesen Richtlinien und Anleitungen handeln, ist es möglich, dass unser Supportteam Sie nicht unterstützen kann. Wenn Sie die Richtlinien, Methoden und Anleitungen, die in diesem Artikel vorgestellt werden, beachten, und trotzdem Probleme bei der Übermittlung basierend auf der IP-Adresse des Absenders haben, führen Sie bitte die Schritte aus, um eine Delisting-Anforderung zu übermitteln. Anweisungen finden Sie unter [Verwenden des Listendelist-Portals,](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)um sich selbst aus der Liste blockierter Absender zu entfernen.

## <a name="general-microsoft-policies"></a>Allgemeine Microsoft-Richtlinien

E-Mails, die an Microsoft 365 gesendet werden, müssen alle Microsoft-Richtlinien für die E-Mail-Übertragung und -Verwendung von Microsoft 365.

- Nutzungsbedingungen für Microsoft 365; insbesondere das Verbot, den Dienst zum Spamen oder Verteilen von Schadsoftware zu verwenden.

- [Microsoft-Servicevertrag](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Einhaltung von gesetzlichen Vorschriften

E-Mails, die an Microsoft 365 benutzer gesendet werden, müssen alle geltenden Gesetze und Vorschriften für die E-Mail-Kommunikation in der jeweiligen Gerichtsbarkeit einhalten.

- [CAN-SPAM Act: Compliance-Leitfaden für Unternehmen](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [„Remove Me"-Antworten und -Verantwortlichkeiten: E-Mail-Vermarkter müssen „Unsubscribe"-Ansprüche beachten](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>Technische Richtlinien

E-Mails, die an Microsoft 365 gesendet werden, sollten den anwendbaren Empfehlungen entsprechen, die in den folgenden Dokumenten aufgeführt sind (einige Links sind nur in Englisch verfügbar).

- [RFC 2505: Anti-Spam Recommendations for SMTP MTAs](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: SMTP Service Extension for Command Pipelining](https://www.ietf.org/rfc/rfc2920.txt)

Darüber hinaus müssen E-Mail-Server, die eine Verbindung Microsoft 365, die folgenden Anforderungen erfüllen:

- Absender muss allen technischen Standards für die Übermittlung von Internet-E-Mails entsprechen - gemäß der Veröffentlichungen der Internet Engineering Task Force (IETF) von The Internet Society, einschließlich RFC 5321, RFC 5322 und anderen.

- Nachdem ein numerischer SMTP-Antwortfehlercode zwischen 500 und 599 (auch bekannt als permanenter Unzustellbarkeitsbericht oder NDR) ausgegeben wurde, darf der Absender nicht erneut versuchen, dem Empfänger die Nachricht zuzustellen.

- Nach mehreren Unzustellbarkeitsberichte, darf der Absender nicht weiter versuchen, E-Mails an diesen Empfänger zu senden.

- Nachrichten dürfen nicht über unsichere E-Mail-Relay- oder Proxyserver übertragen werden.

- Der Mechanismus für die Entfernung aus einzelnen Listen oder allen vom Absender gehosteten Listen muss klar dokumentiert und für Empfänger einfach zu finden und zu verwenden sein.

- Verbindungen aus dynamischen IP-Adressräumen werden möglicherweise nicht akzeptiert.

- E-Mail-Server müssen gültige Reverse-DNS-Einträge haben.

## <a name="reputation-management"></a>Zuverlässigkeitsverwaltung

Absender, ISPs und andere Dienstanbietern sollten die Zuverlässigkeit Ihrer ausgehenden IP-Adressen aktiv verwalten.

## <a name="microsoft-365-limits"></a>Microsoft 365 Grenzwerte

Absender müssen die in Microsoft 365 grenzwerte aufgeführten [Exchange Online Protection einhalten.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)

## <a name="email-delivery-resources-and-organizations"></a>E-Mail-Übermittlungsressourcen und -Organisationen

Microsoft arbeitet aktiv mit Branchenvertretern und Dienstanbietern zusammen, um das Internet- und das E-Mail-Ökosystem zu verbessern. Diese Organisationen haben Dokumente mit bewährten Methoden veröffentlicht, die wir unterstützen und für Absender empfehlen. Dadurch wird Ihre Möglichkeit, E-Mails zwischen verschiedenen E-Mail-Dienstanbietern auf der ganzen Welt zu übermitteln, verbessert.

- [Messaging Malware Mobile Anti-Abuse Working Group](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.internetsociety.org/ota/)

- [Email Sender & Provider Coalition](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Missbrauchs- und Spamberichte

Informationen zu unrechtmäßigen, beleidigenden, unerwünschten oder schädlichen E-Mails finden Sie unter Melden von Nachrichten [und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md). Das Senden dieser Kommunikationstypen stellt einen Verstoß gegen die Microsoft-Richtlinie dar, und es werden geeignete Maßnahmen für bestätigte Berichte ergriffen.

## <a name="law-enforcement"></a>Strafverfolgung

Wenn Sie in der Strafverfolgung tätig sind und Microsoft Corporation gesetzliche Dokumentationen zu Office 365 bereitstellen möchten oder wenn Sie Fragen zu gesetzlichen Dokumentationen haben, die Sie an Microsoft übermittelt haben, wenden Sie sich unter (1) (425) 722-1299 an Microsoft.