---
title: Standardmäßige Sicherheit in Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Weitere Informationen zur Standardmäßigen Einstellung "Sicherheit" in Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c8af609b8ed50b0bfacb7d9f5397fab4c4726927
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040544"
---
# <a name="secure-by-default-in-office-365"></a>Standardmäßige Sicherheit in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Standardmäßig sicher" ist ein Begriff, der verwendet wird, um die Standardeinstellungen zu definieren, die möglichst sicher sind.

Sicherheit muss jedoch mit Produktivität abgewogen werden. Dies kann einen Ausgleich zwischen:

- **Benutzerfreundlichkeit:** Einstellungen sollten der Benutzerproduktivität nicht im Wege kommen.
- **Risiko:** Sicherheit blockiert möglicherweise wichtige Aktivitäten.
- **Legacyeinstellungen:** Einige Konfigurationen für ältere Produkte und Features müssen möglicherweise aus geschäftlichen Gründen beibehalten werden, auch wenn neue, moderne Einstellungen verbessert werden.

Microsoft 365-Organisationen mit Postfächern in Exchange Online sind durch Exchange Online Protection (EOP) geschützt. Dieser Schutz umfasst:

- E-Mails mit mutmaßlicher Schadsoftware werden automatisch in Quarantäne gestellt, und Empfänger werden benachrichtigt. Weitere [Informationen finden Sie unter "Konfigurieren von An malware-Richtlinien in EOP".](configure-anti-malware-policies.md)
- E-Mails, die als Phishing mit hoher Confidence identifiziert werden, werden gemäß der Antispamrichtlinienaktion verarbeitet. Weitere [Informationen finden Sie unter Konfigurieren von Antispamrichtlinien in EOP.](configure-your-spam-filter-policies.md)

Weitere Informationen zu EOP finden Sie in [der Exchange Online Protection-Übersicht.](exchange-online-protection-overview.md)

Da Microsoft unsere Kunden standardmäßig schützen möchte, werden einige Mandanten nicht auf Schadsoftware oder Phishing mit hoher Sicherheit angewendet. Zu diesen Außerkraftsetzungen gehören:

- Listen zulässiger Absender oder zulässiger Domänen (Antispamrichtlinien)
- Sichere Absender in Outlook
- LISTE der zulässigen IP-Adressen (Verbindungsfilterung)

Weitere Informationen zu diesen Außerkraftsetzungen finden Sie unter "Listen [sicherer Absender erstellen".](create-safe-sender-lists-in-office-365.md)

> [!NOTE]
> We're in the process of deprecating the **Move message to Junk Email folder action** for a High confidence phishing **email** verdict in EOP anti-spam policies. Antispamrichtlinien, die diese Aktion für Phishingnachrichten mit hoher Sicherheit verwenden, werden in **Quarantänenachrichten konvertiert.** Die **Aktion "Nachricht an E-Mail-Adresse** umleiten" für Phishingnachrichten mit hoher Confidence ist davon nicht betroffen.

"Sicherheit" ist standardmäßig keine Einstellung, die aktiviert oder deaktiviert werden kann, aber unsere Filterung funktioniert so, dass potenziell gefährliche oder unerwünschte Nachrichten aus Ihren Postfächern herausgefiltert werden. Schadsoftware und Phishingnachrichten mit hoher Confidence sollten unter Quarantäne gestellt werden. Nur Administratoren können Nachrichten verwalten, die als Schadsoftware oder Phishing mit hoher Sicherheit isoliert sind, und sie können von dort auch falsch positive Ergebnisse an Microsoft melden. Weitere Informationen finden Sie unter ["Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP"](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Weitere Informationen dazu, warum wir dies tun

Der Standardwert für Sicherheit ist: Wir ergreifen dieselbe Aktion für die Nachricht, die Sie ergreifen würden, wenn Sie die Nachricht als bösartig einwünssten, auch wenn eine konfigurierte Ausnahme andernfalls die Zugestellt werden würde. Dies ist der gleiche Ansatz, den wir immer für Schadsoftware verwendet haben, und jetzt erweitern wir dieses Verhalten auf Phishingnachrichten mit hoher Sicherheit.

Unsere Daten deuten darauf hin, dass ein Benutzer 30-mal häufiger auf einen schädlichen Link in Nachrichten im Junk-E-Mail-Ordner im Vergleich zur Quarantäne klickt. Unsere Daten weisen auch darauf hin, dass die Rate falsch positiver Ergebnisse (gute Nachrichten, die als schlecht gekennzeichnet sind) für Phishingnachrichten mit hoher Confidence sehr niedrig ist, und Administratoren alle falsch positiven Ergebnisse mit Administratorübermittlungen beheben können.

Außerdem haben wir festgestellt, dass die Listen zulässiger Absender und zulässiger Domänen in Antispamrichtlinien und sicheren Absendern in Outlook zu breit waren und mehr Schaden als Schaden anrichten.

Anders ausgedrückt: Als Sicherheitsdienst handeln wir in Ihrem Namen, um zu verhindern, dass Ihre Benutzer gefährdet werden. 

## <a name="exceptions"></a>Ausnahmen

Die einzige Außerkraftsetzung, die eine Umgehung der Filterung durch Phishingnachrichten mit hoher Sicherheit ermöglicht, sind Exchange-Nachrichtenflussregeln (auch als Transportregeln bekannt). Informationen zur Verwendung von Nachrichtenflussregeln zum Umgehen der Filterung finden Sie unter Verwenden von Nachrichtenflussregeln zum Festlegen der [SCL in Nachrichten.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

Sie sollten die Verwendung von Außerkraftsetzungen nur in den folgenden Szenarien in Betracht ziehen:

- Phishingsimulationen: Simulierte Angriffe können Ihnen dabei helfen, anfällige Benutzer zu identifizieren, bevor sich ein tatsächlicher Angriff auf Ihre Organisation ausdingt.
- Security/SecOps-Postfächer: Dedizierte Postfächer, die von Sicherheitsteams verwendet werden, um ungefilterte Nachrichten (sowohl gut als auch schlecht) zu erhalten. Teams können dann überprüfen, ob sie schädliche Inhalte enthalten.
- Filter von Drittanbietern: "Sicherheit" gilt standardmäßig nicht, wenn der MX-Eintrag der Domäne nicht auf Office 365 verweisen soll.
- Falsch positive Ergebnisse: Möglicherweise möchten Sie vorübergehend bestimmte Nachrichten zulassen, die noch von Microsoft über [Administratorübermittlungen analysiert werden.](admin-submission.md) Wie bei allen Außerkraftsetzungen wird empfohlen, dass sie temporär sind.
