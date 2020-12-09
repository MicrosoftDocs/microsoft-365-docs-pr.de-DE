---
title: Standardmäßig sichern in Office 365
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
description: Erfahren Sie mehr über die Einstellung "standardmäßig sicher" in Exchange Online Protection (EoP).
ms.openlocfilehash: 758d2169d80630a38c0b498e8c1848568e5ec941
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602031"
---
# <a name="secure-by-default-in-office-365"></a>Standardmäßig sichern in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Standardmäßig sichern" ist ein Begriff, der verwendet wird, um die Standardeinstellungen zu definieren, die möglichst sicher sind.

Die Sicherheit muss jedoch mit der Produktivität ausgeglichen werden. Dies kann das Balancing in folgenden Bereichen umfassen:

- **Usability**: die Einstellungen sollten nicht die Produktivität des Benutzers in den Weg legen.
- **Risiko**: Sicherheit blockiert möglicherweise wichtige Aktivitäten.
- **Legacy Einstellungen**: einige Konfigurationen für ältere Produkte und Features müssen möglicherweise aus geschäftlichen Gründen verwaltet werden, selbst wenn neue, moderne Einstellungen verbessert werden.

Microsoft 365-Organisationen mit Postfächern in Exchange Online sind durch Exchange Online Protection (EoP) geschützt. Dieser Schutz umfasst Folgendes:

- E-Mails mit mutmaßlicher Schadsoftware werden automatisch isoliert, und Empfänger werden benachrichtigt. Weitere Informationen finden Sie unter [configure Anti-Malware Policies in EoP](configure-anti-malware-policies.md).
- E-Mail-Nachrichten, die als Phishing mit hoher Vertrauenswürdigkeit identifiziert werden, werden gemäß der Anti-Spam-Richtlinie behandelt. Weitere Informationen finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md).

Weitere Informationen zu EoP finden Sie unter [Exchange Online Protection Overview](exchange-online-protection-overview.md).

Da Microsoft unsere Kunden standardmäßig schützen möchte, werden einige Überschreibungen von Mandanten nicht auf Schadsoftware oder Phishing für hohe Vertrauenswürdigkeit angewendet. Zu diesen Außerkraftsetzungen gehören:

- Zugelassene Absenderlisten oder zugelassene Domänenlisten (Anti-Spam-Richtlinien)
- Outlook-sichere Absender
- IP-Zulassungsliste (Verbindungsfilterung)

Weitere Informationen zu diesen Außerkraftsetzungen finden Sie unter [Create Safe Sender lists](create-safe-sender-lists-in-office-365.md).

"Standardmäßig sichern" ist keine Einstellung, die aktiviert oder deaktiviert werden kann, aber die Art und Weise, wie unsere Filterung funktioniert, um potenziell gefährliche oder unerwünschte Nachrichten aus ihren Postfächern zu halten. Schadsoftware und Phishing-Nachrichten mit hoher Vertrauenswürdigkeit sollten unter Quarantäne gestellt werden. Nur Administratoren können Nachrichten verwalten, die als Schadsoftware oder Phishing für hohe Vertrauenswürdigkeit unter Quarantäne gestellt werden, und Sie können von dort aus auch falsch positive Ergebnisse an Microsoft melden. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EoP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Weitere Informationen dazu, warum wir dies tun

Der Geist, standardmäßig sicher zu sein, lautet: Wir nehmen dieselbe Aktion in der Nachricht vor, die Sie durchführen würden, wenn Sie die Nachricht als bösartig erachten würden, selbst wenn eine entsprechende Möglichkeit vorhanden war. Dies ist der gleiche Ansatz, den wir bei Schadsoftware verwendet haben, und jetzt erweitern wir dieses gleiche Verhalten auf hoch vertrauenswürdige Phishing-Nachrichten. Unsere Daten deuten darauf hin, dass die falsch Positive Rate für Phishing-Nachrichten mit hoher Zuverlässigkeit sehr niedrig ist und Administratoren alle falsch positiven Ergebnisse mit Administratoreingaben auflösen können. Unsere Daten deuten auch darauf hin, dass die zulässigen Absenderlisten und zulässigen Domänenlisten in Anti-Spam-Richtlinien und sicheren Absendern in Outlook zu weitreichend waren und mehr Schaden als nützen.

Anders ausgedrückt: als Sicherheitsdienst handeln wir in Ihrem Namen, um zu verhindern, dass Ihre Benutzer gefährdet sind. Darüber hinaus stellt Secure standardmäßig keine vollständige Übernahme ihrer verfügbaren Optionen für Phishing-Nachrichten mit hoher Zuverlässigkeit in Anti-Spam-Richtlinien dar. Obwohl die Quarantäne empfohlen wird, sind die anderen Aktionen, die immer verfügbar waren, weiterhin verfügbar (Verschieben in den Junk-e-Mail-Ordner oder Umleiten an eine e-Mail-Adresse).

## <a name="exceptions"></a>Ausnahmen

Die einzige Außerkraftsetzung, die eine hohe vertrauenswürdige Phishing-Nachricht zur Umgehung der Filterung zulässt, ist Exchange-Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet). Informationen zum Verwenden von Nachrichtenfluss Regeln zum Umgehen der Filterung finden Sie unter [Verwenden von Nachrichtenfluss Regeln zum Festlegen der SCL-Bewertung in Nachrichten](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Sie sollten die Verwendung von Außerkraftsetzungen in den folgenden Szenarien nur in Betracht nehmen:

- Phishing-Simulationen: Simulierte Angriffe können Sie bei der Identifizierung von anfälligen Benutzern unterstützen, bevor ein echter Angriff Ihre Organisation beeinträchtigt.
- Security/Cops Mailboxes: dedizierte Postfächer, die von Sicherheitsteams verwendet werden, um nicht gefilterte Nachrichten (sowohl gut als auch schlecht) abzurufen. Teams können dann überprüfen, ob Sie schädlichen Inhalt enthalten.
- Drittanbieter Filter: einige Drittanbieter empfehlen das Deaktivieren von EoP (SCL =-1), da der Filter eines Drittanbieters die e-Mail-Filterung verwalten wird. Microsoft rät davon ab, EoP zu deaktivieren, da EoP für [Microsoft Defender für Office 365](office-365-atp.md)erforderlich ist. Stattdessen empfiehlt es sich, die [Erweiterte Filterung für Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)zu aktivieren.
- Falsch positive Ergebnisse: Sie möchten möglicherweise vorübergehend bestimmte Nachrichten zulassen, die von Microsoft [über Administrator übermittungen](admin-submission.md)noch analysiert werden. Wie bei allen Außerkraftsetzungen wird empfohlen, dass Sie temporär sind.
