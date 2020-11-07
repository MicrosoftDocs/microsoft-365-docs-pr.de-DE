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
description: Hier erfahren Sie, wie Sie e-Mail-Sicherheitsberichte für Ihre Organisation suchen und verwenden. E-Mail-Sicherheitsberichte sind im Security & Compliance Center verfügbar.
ms.openlocfilehash: 0e38091981cd379dfc912be429c00d168dff775c
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944481"
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
1. E-Mails mit mutmaßlicher Schadsoftware werden automatisch isoliert, und Empfänger werden benachrichtigt. Weitere Informationen finden Sie unter [configure Anti-Malware Policies in EoP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).
1. Phishing-e-Mails, die als "hohes Vertrauen" identifiziert werden, werden gemäß der Antispampolitik-Aktion verarbeitet. Weitere Informationen finden Sie unter [configure Anti-Spam Policies in EoP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).

Da Microsoft unsere Kunden standardmäßig schützen möchte, werden einige Mandanten Außerkraftsetzungen nicht auf Schadsoftware oder Phishing mit hoher Zuverlässigkeit angewendet. Zu diesen Außerkraftsetzungen gehören:
- Zugelassene Absenderlisten oder zugelassene Domänenlisten (Anti-Spam-Richtlinien)
- Outlook-sichere Absender
- IP-Zulassungsliste (Verbindungsfilterung)

Weitere Informationen zu diesen Außerkraftsetzungen finden Sie unter [Create Safe Sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).

Secure standardmäßig ist hier keine Einstellung, die aktiviert oder deaktiviert werden könnte, aber die Art und Weise, wie unsere Filterung funktioniert, um potenziell gefährliche oder unerwünschte Nachrichten aus ihren Postfächern zu halten. Schadsoftware und Phishing mit hoher Zuverlässigkeit sollten an die Quarantäne gesendet werden. Nur Administratoren können Nachrichten verwalten, die als Schadsoftware oder Phishing für hohe Vertrauenswürdigkeit isoliert wurden, und Sie können von dort aus auch falsch positive Ergebnisse an Microsoft melden. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EoP](manage-quarantined-messages-and-files.md)

## <a name="exceptions"></a>Ausnahmen
Die einzigen Außerkraftsetzungen, die alle Filter umgehen werden, umfassen Folgendes:
- Exchange-Transport Regeln (ETR)/Mail-Flussregeln.  Verwenden Sie Nachrichtenfluss Regeln, um die SCL-Bewertung (Spam Confidence Level) in Nachrichten in EoP festzulegen.
- Mandanten-Zulassungs-und Sperrliste: Verwalten von URLs und Dateien in der Liste Mandanten-Allow/Block.


Diese Arten von Außerkraftsetzungen sind für Folgendes nützlich:
- Phishing-Simulationen: Simulierte Angriffe können Sie bei der Identifizierung von anfälligen Benutzern unterstützen, bevor ein echter Angriff Ihre Organisation beeinträchtigt.
- Security/Cops Mailboxes: dedizierte Postfächer, die von Sicherheitsteams verwendet werden, um nicht gefilterte Nachrichten (sowohl gut als auch schlecht) abzurufen. Teams können dann überprüfen, ob Sie schädlichen Inhalt enthalten.
- Drittanbieter Filter: einige Drittanbieter empfehlen das Deaktivieren von EoP (SCL =-1), da der Filter eines Drittanbieters die e-Mail-Filterung verwalten wird.  Microsoft rät davon ab, EoP zu deaktivieren, da EoP für Defender für Office 365 erforderlich ist. 
- Falsch positive Ergebnisse: möglicherweise möchten Sie bestimmte Nachrichten zulassen, die von Microsoft [über Administrator übermittungen](admin-submission.md)noch analysiert werden. Wie bei allen Außerkraftsetzungen wird empfohlen, dass Sie temporär sind.
