---
title: Spambenachrichtigungen für Endbenutzer in Office 36
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
description: Wenn ein Administrator Spambenachrichtigungen für Endbenutzer in Anti-Spam-Richtlinien aktiviert, erhalten die Nachrichtenempfänger regelmäßig Benachrichtigungen über Ihre isolierten Nachrichten.
ms.openlocfilehash: 67dbf311c37ae61c007b78110522033d79c0b161
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857145"
---
# <a name="end-user-spam-notifications-in-office-365"></a>Spambenachrichtigungen für Endbenutzer in Office 365

In Quarantäne werden potenziell gefährliche oder unerwünschte Nachrichten in Office 365 Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächern gespeichert. Weitere Informationen finden Sie unter [Quarantine in Office 365](quarantine-email-messages.md).

Standardmäßig sind Spambenachrichtigungen für Endbenutzer in Anti-Spam-Richtlinien deaktiviert. Wenn ein Administrator [Spambenachrichtigungen für Endbenutzer aktiviert](configure-your-spam-filter-policies.md), erhalten die Nachrichtenempfänger regelmäßig Benachrichtigungen über Ihre Nachrichten, die als Spam, Massen-e-Mails oder (ab April 2020) als Phishing isoliert wurden.

> [!NOTE]
> Im Oktober 2019 wurde die Möglichkeit, isolierte Nachrichten direkt von Endbenutzer-Spambenachrichtigungen freizugeben, entfernt. Stattdessen können Benutzer nun zum Office 365 Security & Compliance Center wechseln, um Ihre isolierten Nachrichten freizugeben (entweder direkt oder durch Klicken auf **überprüfen** in der Benachrichtigung). Weitere Informationen finden Sie unter [Suchen und Freigeben von isolierten Nachrichten als Benutzer in Office 365](find-and-release-quarantined-messages-as-a-user.md). <br/><br/> Nachrichten, die als vertrauenswürdiges Phishing, Schadsoftware oder Nachrichtenfluss Regeln (auch bekannt als Transportregeln) unter Quarantäne gestellt wurden, stehen nur Administratoren zur Verfügung. Weitere Informationen finden Sie unter [Suchen und Freigeben von isolierten Nachrichten als Administrator in Office 365](find-and-release-quarantined-messages-as-an-administrator.md).

Eine spambenachrichtigung für Endbenutzer enthält für jede isolierte Nachricht die folgenden Informationen:

- **Sender**: der Absender Name und die e-Mail-Adresse der isolierten Nachricht.

- **Betreff**: der Text der Betreffzeile der isolierten Nachricht.

- **Date**: das Datum und die Uhrzeit (in UTC), in denen die Nachricht isoliert wurde.

- **Absender blockieren**: Klicken Sie auf diesen Link, um den Absender der Liste blockierter Absender hinzuzufügen.

- **Review**: Klicken Sie auf diesen Link, um die Quarantäne im Security & Compliance Center zu wechseln, in der Sie Ihre isolierten Nachrichten freigeben, löschen oder melden können.

![Beispiel-spambenachrichtigung für Endbenutzer](../../media/end-user-spam-notification.png)
