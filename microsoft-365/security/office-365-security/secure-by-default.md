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
ms.openlocfilehash: 9f676dcd89f0322792bd40e06879b9758082d94e
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131097"
---
# <a name="secure-by-default-in-office-365"></a>Standardmäßig sichern in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Standardmäßig sichern" ist ein Begriff, der verwendet wird, um die Standardeinstellungen zu definieren, die möglichst sicher sind.

Die Sicherheit muss jedoch mit der Produktivität ausgeglichen werden. Dies kann das Balancing in folgenden Bereichen umfassen:

- Usability: die Einstellungen sollten nicht die Produktivität des Benutzers in den Weg legen.
- Risiko: Sicherheit blockiert möglicherweise wichtige Aktivitäten.
- Legacy Einstellungen: einige Konfigurationen für ältere Produkte und Features müssen möglicherweise aus geschäftlichen Gründen verwaltet werden, selbst wenn neue, moderne Einstellungen verbessert werden.

Microsoft 365-Organisationen mit Postfächern in Exchange Online sind durch Exchange Online Protection (EoP) geschützt. Dieser Schutz umfasst Folgendes:

1. E-Mails mit mutmaßlicher Schadsoftware werden automatisch isoliert, und Empfänger werden benachrichtigt. Weitere Informationen finden Sie unter [configure Anti-Malware Policies in EoP](configure-anti-malware-policies.md).
1. Phishing-e-Mails, die als "hohes Vertrauen" identifiziert werden, werden gemäß der Antispampolitik-Aktion verarbeitet. Weitere Informationen finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md).

Da Microsoft unsere Kunden standardmäßig schützen möchte, werden einige Überschreibungen von Mandanten nicht auf Schadsoftware oder Phishing für hohe Vertrauenswürdigkeit angewendet. Zu diesen Außerkraftsetzungen gehören:

- Zugelassene Absenderlisten oder zugelassene Domänenlisten (Anti-Spam-Richtlinien)
- Outlook-sichere Absender
- IP-Zulassungsliste (Verbindungsfilterung)

Weitere Informationen zu diesen Außerkraftsetzungen finden Sie unter [Create Safe Sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).

Secure standardmäßig ist hier keine Einstellung, die aktiviert oder deaktiviert werden könnte, aber die Art und Weise, wie unsere Filterung funktioniert, um potenziell gefährliche oder unerwünschte Nachrichten aus ihren Postfächern zu halten. Schadsoftware und Phishing mit hoher Zuverlässigkeit sollten an die Quarantäne gesendet werden. Nur Administratoren können Nachrichten verwalten, die als Schadsoftware oder Phishing für hohe Vertrauenswürdigkeit isoliert wurden, und Sie können von dort aus auch falsch positive Ergebnisse an Microsoft melden. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EoP](manage-quarantined-messages-and-files.md)

## <a name="exceptions"></a>Ausnahmen

Die einzige Außerkraftsetzung, die eine hohe vertrauenswürdige Phishing-Nachricht zur Umgehung der Filterung zulässt, ist Exchange-Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet). Informationen zum Verwenden von Nachrichtenfluss Regeln zum Umgehen der Filterung finden Sie unter [Verwenden von Nachrichtenfluss Regeln zum Festlegen der SCL-Bewertung in Nachrichten](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Außerkraftsetzungen sollten nur für Folgendes verwendet werden:

- Phishing-Simulationen: Simulierte Angriffe können Sie bei der Identifizierung von anfälligen Benutzern unterstützen, bevor ein echter Angriff Ihre Organisation beeinträchtigt.
- Security/Cops Mailboxes: dedizierte Postfächer, die von Sicherheitsteams verwendet werden, um nicht gefilterte Nachrichten (sowohl gut als auch schlecht) abzurufen. Teams können dann überprüfen, ob Sie schädlichen Inhalt enthalten.
- Drittanbieter Filter: einige Drittanbieter empfehlen das Deaktivieren von EoP (SCL =-1), da der Filter eines Drittanbieters die e-Mail-Filterung verwalten wird. Microsoft rät davon ab, EoP zu deaktivieren, da EoP für Defender für Office 365 erforderlich ist.
- Falsch positive Ergebnisse: möglicherweise möchten Sie bestimmte Nachrichten zulassen, die von Microsoft [über Administrator übermittungen](admin-submission.md)noch analysiert werden. Wie bei allen Außerkraftsetzungen wird empfohlen, dass Sie temporär sind.
