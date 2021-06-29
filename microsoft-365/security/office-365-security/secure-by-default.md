---
title: Standardmäßige Sicherheit in Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über die Standardmäßige Sicherheitseinstellung in Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c737647202e82af0fc217c0eadb3e2573d13a9b1
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177645"
---
# <a name="secure-by-default-in-office-365"></a>Standardmäßige Sicherheit in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

"Standardmäßig sicher" ist ein Begriff, der verwendet wird, um die Standardeinstellungen zu definieren, die so sicher wie möglich sind.

Die Sicherheit muss jedoch mit der Produktivität ausgeglichen werden. Dies kann einen Ausgleich über Folgendes umfassen:

- **Benutzerfreundlichkeit:** Einstellungen sollte der Produktivität der Benutzer nicht im Wege kommen.
- **Risiko:** Die Sicherheit kann wichtige Aktivitäten blockieren.
- **Legacyeinstellungen:** Einige Konfigurationen für ältere Produkte und Features müssen möglicherweise aus geschäftlichen Gründen beibehalten werden, auch wenn neue, moderne Einstellungen verbessert werden.

Microsoft 365 Organisationen mit Postfächern in Exchange Online sind durch Exchange Online Protection (EOP) geschützt. Dieser Schutz umfasst:

- E-Mails mit verdächtiger Schadsoftware werden automatisch unter Quarantäne gestellt, und die Empfänger werden benachrichtigt. Siehe [Konfigurieren von Antischadsoftwarerichtlinien in EOP.](configure-anti-malware-policies.md)
- E-Mails, die als Phishing mit hohem Vertrauen erkannt werden, werden gemäß der Antispamrichtlinienaktion behandelt. Siehe [Konfigurieren von Antispamrichtlinien in EOP.](configure-your-spam-filter-policies.md)

Weitere Informationen zu EOP finden Sie unter [Exchange Online Protection Übersicht.](exchange-online-protection-overview.md)

Da Microsoft unsere Kunden standardmäßig schützen möchte, werden einige Außerkraftsetzungen von Mandanten nicht auf Schadsoftware oder Phishing mit hoher Vertrauenswürdigkeit angewendet. Zu diesen Außerkraftsetzungen gehören:

- Listen zulässiger Absender oder listen zugelassener Domänen (Antispamrichtlinien)
- Outlook Tresor Absender
- IP-Zulassungsliste (Verbindungsfilterung)

Weitere Informationen zu diesen Außerkraftsetzungen finden Sie unter Erstellen von [Listen sicherer Absender.](create-safe-sender-lists-in-office-365.md)

> [!NOTE]
> Wir haben die Aktion **"Nachricht in Junk-E-Mail-Ordner verschieben"** für ein **Hochzuverlässigen von Phishing-E-Mails** in EOP-Antispamrichtlinien als veraltet eingestuft. Antispamrichtlinien, die diese Aktion für Phishing-Nachrichten mit hoher Konfidenz verwenden, werden in **Quarantäne-Nachrichten** konvertiert. Die Aktion **"Nachricht an E-Mail-Adresse umleiten"** für Phishingnachrichten mit hoher Konfidenz ist davon nicht betroffen.

"Sicher" ist standardmäßig keine Einstellung, die aktiviert oder deaktiviert werden kann, aber unsere Filterung funktioniert sofort, um potenziell gefährliche oder unerwünschte Nachrichten aus Ihren Postfächern fernzuhalten. Phishingnachrichten mit hoher Vertrauenswürdigkeit sollten unter Quarantäne gestellt werden. Nur Administratoren können Nachrichten verwalten, die als Schadsoftware oder Phishing mit hohem Vertrauen unter Quarantäne gestellt werden, und sie können von dort aus auch falsch positive Ergebnisse an Microsoft melden. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Weitere Informationen dazu, warum wir dies tun

Die Sicherheit ist standardmäßig: Wir ergreifen die gleiche Aktion für die Nachricht, die Sie ausführen würden, wenn Sie die Nachricht schädlich erkannt hätten, auch wenn eine konfigurierte Ausnahme andernfalls die Zustellung der Nachricht zulassen würde. Dies ist der gleiche Ansatz, den wir immer für Schadsoftware verwendet haben, und jetzt erweitern wir dieses Verhalten auf Phishingnachrichten mit hoher Vertrauenswürdigkeit.

Unsere Daten deuten darauf hin, dass ein Benutzer 30 Mal häufiger auf einen schädlichen Link in Nachrichten im Junk-E-Mail-Ordner klickt als auf Quarantäne. Unsere Daten deuten außerdem darauf hin, dass die falsch positive Rate (gute Nachrichten als schlecht markiert) für Phishing-Nachrichten mit hoher Konfidenz sehr niedrig ist und Administratoren falsch positive Ergebnisse mit Administratorübermittlungen beheben können.

Außerdem haben wir festgestellt, dass die Listen zulässiger und zulässiger Domänen in Antispamrichtlinien und Tresor Absender in Outlook zu breit waren und mehr Schaden als Nutzen verursachen.

Anders ausgedrückt: Als Sicherheitsdienst agieren wir in Ihrem Auftrag, um zu verhindern, dass Ihre Benutzer kompromittiert werden.

## <a name="exceptions"></a>Ausnahmen

> [!NOTE]
> Im August 2021 wird die standardmäßige Sicherheit auf Exchange Nachrichtenflussregeln (auch als Transportregeln bezeichnet) erweitert. Wenn Sie Nachrichtenflussregeln verwenden, um Phishingsimulationen von Drittanbietern oder die ungefilterte Übermittlung an Postfächer für Sicherheitsvorgänge zuzulassen, müssen Sie diese Regeln schließlich entfernen und zur Verwendung der [erweiterten Übermittlungsrichtlinie](configure-advanced-delivery.md) _wechseln, wenn das Feature für Sie verfügbar ist._

Die einzige Außerkraftsetzung, die das Umgehen der Filterung durch Phishingnachrichten mit hoher Konfidenz ermöglicht, sind Nachrichtenflussregeln. Informationen zum Verwenden von Nachrichtenflussregeln zum Umgehen der Filterung finden Sie unter [Verwenden von Nachrichtenflussregeln zum Festlegen der SCL in Nachrichten.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)

Sie sollten die Verwendung von Außerkraftsetzungen nur in den folgenden Szenarien in Betracht ziehen:

- Phishingsimulationen: Simulierte Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren, bevor sich ein realer Angriff auf Ihre Organisation auswirkt.
- Security/SecOps-Postfächer: Dedizierte Postfächer, die von Sicherheitsteams verwendet werden, um ungefilterte Nachrichten zu erhalten (sowohl gut als auch schlecht). Teams können dann überprüfen, ob sie schädliche Inhalte enthalten.
- Filter von Drittanbietern: "Sicher" gilt standardmäßig nicht, wenn der MX-Eintrag der Domäne nicht auf Office 365 verweist.
- Falsch positive Ergebnisse: Möglicherweise möchten Sie bestimmte Nachrichten, die noch von Microsoft [über Administratorübermittlungen](admin-submission.md)analysiert werden, vorübergehend zulassen. Wie bei allen Außerkraftsetzungen wird empfohlen, dass sie temporär sind.
