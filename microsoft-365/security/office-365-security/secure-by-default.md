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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über die Standardmäßige Sicherheitseinstellung in Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 957ca3b563d4f1466dd537c3ae974a4fd61aa6f2
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346316"
---
# <a name="secure-by-default-in-office-365"></a>Standardmäßig sicher in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

"Standardmäßig sicher" ist ein Begriff, der verwendet wird, um die Standardeinstellungen zu definieren, die möglichst sicher sind.

Sicherheit muss jedoch mit Produktivität abgewogen werden. Dies kann einen Abgleich zwischen folgenden Übergreifend umfassen:

- **Benutzerfreundlichkeit**: Einstellungen benutzerproduktivität sollte nicht in Frage kommen.
- **Risiko**: Sicherheit kann wichtige Aktivitäten blockieren.
- **Legacyeinstellungen:** Einige Konfigurationen für ältere Produkte und Features müssen möglicherweise aus geschäftlichen Gründen beibehalten werden, auch wenn neue, moderne Einstellungen verbessert werden.

Microsoft 365 Organisationen mit Postfächern in Exchange Online sind durch Exchange Online Protection (EOP) geschützt. Dieser Schutz umfasst:

- E-Mails mit mutmaßlicher Schadsoftware werden automatisch isoliert, und Empfänger werden benachrichtigt. Weitere Informationen finden Sie unter [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).
- E-Mails, die als Phishing mit hoher Sicherheit identifiziert werden, werden gemäß der Antispamrichtlinienaktion behandelt. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

Weitere Informationen zu EOP finden Sie [unter Exchange Online Protection Übersicht](exchange-online-protection-overview.md).

Da Microsoft unsere Kunden standardmäßig schützen möchte, werden einige Mandantenüberschreibungen nicht für Schadsoftware oder Phishing mit hoher Sicherheit angewendet. Zu diesen Außerkraftsetzungen gehören:

- Zugelassene Absenderlisten oder zulässige Domänenlisten (Antispamrichtlinien)
- Outlook Sichere Absender
- IP-Zulässige Liste (Verbindungsfilterung)

Weitere Informationen zu diesen Außerkraftsetzungen finden Sie unter [Create safe sender lists](create-safe-sender-lists-in-office-365.md).

> [!NOTE]
> Wir sind dabei, die Aktion Nachricht  in Junk-E-Mail-Ordner verschieben für ein Phishing-E-Mail-Urteil mit hoher Vertrauen in EOP-Antispamrichtlinien zu veraltet.  Antispamrichtlinien, die diese Aktion für Phishingnachrichten mit hoher Vertrauenssicherheit verwenden, werden in **Quarantänenachrichten konvertiert.** Die **Aktion Nachricht an E-Mail-Adresse** umleiten für Phishingnachrichten mit hoher Vertrauen ist davon nicht betroffen.

Sicherheit ist standardmäßig keine Einstellung, die aktiviert oder deaktiviert werden kann, sondern ist die Art und Weise, wie unsere Filterung aus dem Feld heraus funktioniert, um potenziell gefährliche oder unerwünschte Nachrichten aus Ihren Postfächern zu entfernen. Schadsoftware und Phishingnachrichten mit hoher Vertrauenssicherheit sollten in Quarantäne gestellt werden. Nur Administratoren können Nachrichten verwalten, die als Schadsoftware oder Phishing mit hoher Vertrauen in Quarantäne gestellt werden, und sie können auch falsch positive Nachrichten von dort an Microsoft melden. Weitere Informationen finden Sie unter [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Weitere Informationen dazu, warum wir dies tun

Der Geist der Standardmäßigen Sicherheit lautet: Wir ergreifen dieselbe Aktion für die Nachricht, die Sie ergreifen würden, wenn Sie die Nachricht als bösartig kennen, auch wenn eine konfigurierte Ausnahme andernfalls die Zugestellte Nachricht zu ermöglichen würde. Dies ist der gleiche Ansatz, den wir immer bei Schadsoftware verwendet haben, und jetzt erweitern wir dieses Verhalten auf Phishingnachrichten mit hoher Vertrauenssicherheit.

Unsere Daten deuten darauf hin, dass ein Benutzer 30-mal häufiger auf einen schädlichen Link in Nachrichten im Ordner Junk-E-Mail im Vergleich zur Quarantäne klickt. Unsere Daten deuten auch darauf hin, dass die falsch positive Rate (gute Nachrichten, die als schlecht gekennzeichnet sind) für Phishingnachrichten mit hoher Vertrauensrate sehr niedrig ist, und Administratoren können falsch positive Nachrichten mit Administratorübermittlungen beheben.

Außerdem haben wir festgestellt, dass die zulässigen Absender- und zulässigen Domänenlisten in Antispamrichtlinien und sicheren Absendern in Outlook zu breit waren und mehr Schaden als Schaden anrichten.

Anders ausgedrückt: Als Sicherheitsdienst handeln wir in Ihrem Namen, um zu verhindern, dass Ihre Benutzer gefährdet werden.

## <a name="exceptions"></a>Ausnahmen

> [!NOTE]
> Im Juli 2021 wird die Sicherheit standardmäßig auf Exchange Nachrichtenflussregeln (auch als Transportregeln bekannt) erweitert. Wenn Sie Nachrichtenflussregeln verwenden, um Phishingsimulationen von Drittanbietern oder die ungefilterte Zustellung an Sicherheitsvorgangspostfächer [](configure-advanced-delivery.md) zu ermöglichen, müssen Sie diese Regeln schließlich entfernen und zur Verwendung der erweiterten Übermittlungsrichtlinie wechseln, wenn das Feature für Sie verfügbar _ist._

Die einzige Außerkraftsetzung, mit der Phishingnachrichten mit hoher Vertrauen die Filterung umgehen können, sind Nachrichtenflussregeln. Informationen zur Verwendung von Nachrichtenflussregeln zum Umgehen der Filterung finden Sie unter Verwenden von Nachrichtenflussregeln zum Festlegen der [SCL in Nachrichten.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

Sie sollten die Verwendung von Außerkraftsetzungen nur in den folgenden Szenarien in Betracht ziehen:

- Phishing-Simulationen: Simulierte Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren, bevor sich ein tatsächlicher Angriff auf Ihre Organisation aus wirkt.
- Sicherheits-/SecOps-Postfächer: Dedizierte Postfächer, die von Sicherheitsteams verwendet werden, um ungefilterte Nachrichten (sowohl gut als auch schlecht) zu erhalten. Teams können dann überprüfen, ob sie schädliche Inhalte enthalten.
- Filter von Drittanbietern: Sicherheit gilt standardmäßig nicht, wenn der MX-Eintrag der Domäne nicht auf Office 365.
- Falsch positive Ergebnisse: Möglicherweise möchten Sie bestimmte Nachrichten, die noch von Microsoft über Administratorübermittlungen analysiert werden, [vorübergehend zulassen.](admin-submission.md) Wie bei allen Außerkraftsetzungen wird empfohlen, dass sie temporär sind.
