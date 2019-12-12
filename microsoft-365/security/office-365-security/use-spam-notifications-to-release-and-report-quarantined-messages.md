---
title: Verwenden von Spambenachrichtigungen für Benutzer zum Freigeben und Melden von isolierten Nachrichten in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: Wenn Ihr Administrator die Benachrichtigungen für Benutzer aktiviert, erhalten Sie eine Benachrichtigungsmeldung, in der Nachrichten aufgelistet werden, die an Ihr Postfach gesendet wurden, die als Spam-, Massen-oder Phishing-Nachrichten identifiziert wurden. Nach der Benachrichtigung können Sie Nachrichten freigeben oder melden.
ms.openlocfilehash: 4cf592f0aec948c3c8f6383cf288fb32ac644cd6
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971363"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a>Verwenden von Spambenachrichtigungen für Benutzer zum Freigeben und Melden von isolierten Nachrichten in Office 365

Wenn Ihr Administrator Spambenachrichtigungen für Benutzer aktiviert, erhalten Sie eine Benachrichtigungsmeldung, in der an Ihr Postfach adressierte Nachrichten aufgelistet werden, die stattdessen als Spam identifiziert und isoliert wurden.

> [!TIP]
> Wenn Sie Administrator sind und dieses Feature aktivieren möchten, können Sie die Option auswählen, wenn Sie [eine standardmäßige Anti-Spam-Richtlinie ändern](configure-your-spam-filter-policies.md).

Die empfangene Nachricht enthält die Anzahl der Spam isolierten Nachrichten, die Sie haben, und das Datum und die Uhrzeit (in Universal Coordinated Time oder UTC) der letzten Nachricht in der Liste. Die Liste enthält für jede Nachricht Folgendes:

- **Absender** Der Absender Name und die e-Mail-Adresse der isolierten Nachricht.

- **Betreff** Der Betreffzeilentext der in Quarantäne verschobenen Nachricht.

- **Datum** Datum und Uhrzeit (UTC-Angabe) der Verschiebung der Nachricht in Quarantäne.

Dies sind die Aktionen, die Sie mit einer isolierten Nachricht durchführen können:

- **Absender blockieren** , wenn Office 365 den Absender zu Ihrer Liste blockierter Absender hinzufügen möchten.

- **Überprüfen** Sie, um zum Quarantäne Portal innerhalb des Security and Compliance Centers zu navigieren, wenn Sie andere Aktionen wie Preview oder Release durchführen möchten.

Beachten Sie Folgendes:

- Nachrichten, die in Quarantäne verschoben werden, da Sie einer Nachrichtenfluss Regel entsprechen, werden nicht in Nachrichten mit Benutzerquarantäne eingeschlossen. Es werden nur Spamquarantäne-Nachrichten aufgeführt.

- Sie können eine Nachricht nur einmal freigeben und als falsch positiv markiert (keine Junk-E-Mail) melden.
