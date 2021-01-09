---
title: Standardmäßig sicher in Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Weitere Informationen zur standardmäßig sicheren Einstellung in Exchange Online Protection (EOP)
ms.openlocfilehash: 8db8e7af569114e5829d24d65b8eee89c9dce8c3
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787973"
---
# <a name="secure-by-default-in-office-365"></a>Standardmäßig sicher in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Standardmäßig sicher" ist ein Begriff, der verwendet wird, um die Standardeinstellungen zu definieren, die möglichst sicher sind.

Sicherheit muss jedoch mit Produktivität abgewogen werden. Dies kann einen Ausgleich zwischen:

- **Benutzerfreundlichkeit:** Einstellungen sollten der Benutzerproduktivität nicht im Wege kommen.
- **Risiko:** Sicherheit blockiert möglicherweise wichtige Aktivitäten.
- **Legacyeinstellungen:** Einige Konfigurationen für ältere Produkte und Features müssen möglicherweise aus geschäftlichen Gründen beibehalten werden, auch wenn neue, moderne Einstellungen verbessert werden.

Microsoft 365-Organisationen mit Postfächern in Exchange Online sind durch Exchange Online Protection (EOP) geschützt. Dieser Schutz umfasst:

- E-Mails mit mutmaßlicher Schadsoftware werden automatisch unter Quarantäne gestellt, und Empfänger werden benachrichtigt. Weitere [Informationen finden Sie unter "Konfigurieren von An malware-Richtlinien in EOP".](configure-anti-malware-policies.md)
- E-Mails, die als Phishing mit hoher Confidence identifiziert werden, werden gemäß der Antispamrichtlinienaktion verarbeitet. Weitere [Informationen finden Sie unter Konfigurieren von Antispamrichtlinien in EOP.](configure-your-spam-filter-policies.md)

Weitere Informationen zu EOP finden Sie in [der Exchange Online Protection-Übersicht.](exchange-online-protection-overview.md)

Da Microsoft unsere Kunden standardmäßig schützen möchte, werden einige Mandantenüberschreibungen nicht auf Schadsoftware oder Phishing mit hoher Sicherheit angewendet. Zu diesen Außerkraftsetzungen gehören:

- Listen zulässiger Absender oder zulässiger Domänen (Antispamrichtlinien)
- Sichere Absender in Outlook
- LISTE der zulässigen IP-Adressen (Verbindungsfilterung)

Weitere Informationen zu diesen Außerkraftsetzungen finden Sie unter "Listen [sicherer Absender erstellen".](create-safe-sender-lists-in-office-365.md)

"Sicherheit" ist standardmäßig keine Einstellung, die aktiviert oder deaktiviert werden kann, aber unsere Filterung funktioniert so, dass potenziell gefährliche oder unerwünschte Nachrichten aus Ihren Postfächern herausgefiltert werden. Schadsoftware und Phishingnachrichten mit hoher Sicherheit sollten unter Quarantäne gestellt werden. Nur Administratoren können Nachrichten verwalten, die als Schadsoftware oder Phishing mit hoher Sicherheit isoliert sind, und sie können von dort auch falsch positive Ergebnisse an Microsoft melden. Weitere Informationen finden Sie unter ["Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP"](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Weitere Informationen dazu, warum wir dies tun

Der Standardwert für Sicherheit ist: Wir ergreifen dieselbe Aktion für die Nachricht, die Sie ergreifen würden, wenn Sie die Nachricht als bösartig einwünsten, auch wenn es eine Zulässige gab. Dies ist der gleiche Ansatz, den wir für Schadsoftware verwendet haben, und jetzt erweitern wir dieses Verhalten auf Phishingnachrichten mit hoher Sicherheit. Unsere Daten deuten darauf hin, dass die Rate falsch positiver Ergebnisse für Phishingnachrichten mit hoher Confidence sehr niedrig ist, und Administratoren können alle falsch positiven Ergebnisse mit Administratorübermittlungen beheben. Unsere Daten deuten auch darauf hin, dass die Listen zulässiger absender und zulässiger Domänen in Antispamrichtlinien und sicheren Absendern in Outlook zu breit waren und mehr Schaden als Schaden anrichten.

Anders ausgedrückt: Als Sicherheitsdienst handeln wir in Ihrem Namen, um zu verhindern, dass Ihre Benutzer gefährdet werden. Darüber hinaus ist "Sicherheit standardmäßig" keine vollständige Übernahme Ihrer verfügbaren Optionen für Phishingnachrichten mit hoher Confidence in Antispamrichtlinien. Obwohl die Quarantäne empfohlen wird, sind die anderen Aktionen, die immer verfügbar waren, weiterhin verfügbar (In Junk-E-Mail-Ordner verschieben oder an E-Mail-Adresse umleiten).

## <a name="exceptions"></a>Ausnahmen

Die einzige Außerkraftsetzung, die eine Umgehung der Filterung durch Phishingnachrichten mit hoher Sicherheit ermöglicht, sind Exchange-Nachrichtenflussregeln (auch als Transportregeln bekannt). Informationen zur Verwendung von Nachrichtenflussregeln zum Umgehen der Filterung finden Sie unter Verwenden von Nachrichtenflussregeln zum Festlegen der [SCL in Nachrichten.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

Sie sollten die Verwendung von Außerkraftsetzungen nur in den folgenden Szenarien in Betracht ziehen:

- Phishingsimulationen: Simulierte Angriffe können Ihnen dabei helfen, anfällige Benutzer zu identifizieren, bevor sich ein tatsächlicher Angriff auf Ihre Organisation ausdingt.
- Security/SecOps-Postfächer: Dedizierte Postfächer, die von Sicherheitsteams verwendet werden, um ungefilterte Nachrichten (sowohl gut als auch schlecht) zu erhalten. Teams können dann überprüfen, ob sie schädliche Inhalte enthalten.
- Filter von Drittanbietern: "Sicherheit" gilt standardmäßig nicht, wenn der MX-Eintrag der Domäne nicht auf Office 365 verweisen soll.
- Falsch positive Ergebnisse: Möglicherweise möchten Sie vorübergehend bestimmte Nachrichten zulassen, die noch von Microsoft über [Administratorübermittlungen analysiert werden.](admin-submission.md) Wie bei allen Außerkraftsetzungen wird empfohlen, dass sie temporär sind.
