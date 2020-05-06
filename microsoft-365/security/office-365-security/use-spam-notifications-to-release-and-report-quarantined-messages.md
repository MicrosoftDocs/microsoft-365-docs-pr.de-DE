---
title: Spambenachrichtigungen für Endbenutzer in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie mehr über die Endbenutzer-Spambenachrichtigungen für isolierte Nachrichten.
ms.openlocfilehash: 2a865130bf1fa0c09b5b68254fb604795b204c22
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034998"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Verwenden von Spambenachrichtigungen für Benutzer zum Freigeben und melden von Nachrichten in Quarantäne

Die Quarantäne enthält potenziell gefährliche oder unerwünschte Nachrichten in Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer. Weitere Informationen finden Sie unter [Quarantäne in Office 365](quarantine-email-messages.md).

Standardmäßig sind Spambenachrichtigungen für Endbenutzer in Anti-Spam-Richtlinien deaktiviert. Wenn ein Administrator [Spambenachrichtigungen für Endbenutzer aktiviert](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), erhalten die Empfängerregel mäßig Benachrichtigungen über Ihre Nachrichten, die als Spam, Massen-e-Mails oder (ab April 2020) als Phishing isoliert wurden.

> [!NOTE]
> Nachrichten, die als vertrauenswürdiges Phishing, Schadsoftware oder Nachrichtenfluss Regeln (auch bekannt als Transportregeln) unter Quarantäne gestellt wurden, stehen nur Administratoren zur Verfügung. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365](manage-quarantined-messages-and-files.md).

Eine spambenachrichtigung für Endbenutzer enthält für jede isolierte Nachricht die folgenden Informationen:

- **Sender**: der Absender Name und die e-Mail-Adresse der isolierten Nachricht.

- **Betreff**: der Text der Betreffzeile der isolierten Nachricht.

- **Date**: das Datum und die Uhrzeit (in UTC), in denen die Nachricht isoliert wurde.

- **Absender blockieren**: Klicken Sie auf diesen Link, um den Absender der Liste blockierter Absender hinzuzufügen. Weitere Informationen finden Sie unter [Blockieren eines e-Mail-Absenders in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Release**: für Spamnachrichten (nicht für Phishing) können Sie die Nachricht hier freigeben, ohne das Sicherheits & Compliance Center zu isolieren.

- **Überprüfung**: Klicken Sie auf diesen Link, um im Security & Compliance Center auf Quarantäne zu wechseln, wo Sie Ihre isolierten Nachrichten freigeben, löschen oder melden können. Weitere Informationen finden Sie unter [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Office 365](find-and-release-quarantined-messages-as-a-user.md).

![Beispiel-spambenachrichtigung für Endbenutzer](../../media/end-user-spam-notification.png)
