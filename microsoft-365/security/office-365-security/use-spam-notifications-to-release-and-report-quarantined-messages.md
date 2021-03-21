---
title: Spambenachrichtigungen für Endbenutzer in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: Administratoren können sich in Exchange Online Protection (EOP) über Spambenachrichtigungen für Endbenutzer für isolierte Nachrichten informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 617ff9b6325ac2d5d95d8bc591b9e4ebb7f5434d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921120"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Verwenden von Spambenachrichtigungen von Benutzern zum Veröffentlichen und Melden isolierter Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten. Weitere Informationen finden Sie unter [Quarantined messages in EOP](quarantine-email-messages.md).

Standardmäßig sind Spambenachrichtigungen für Endbenutzer in Antispamrichtlinien deaktiviert. Wenn ein Administrator [Spambenachrichtigungen](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)für Endbenutzer aktiviert, erhalten Empfänger (einschließlich freigegebener Postfächer mit aktivierter automatischemMapping) regelmäßig Benachrichtigungen zu ihren Nachrichten, die als Spam, Massen-E-Mail oder (ab April 2020) Phishing isoliert wurden.

Bei freigegebenen Postfächern werden Spambenachrichtigungen für Endbenutzer nur für Benutzer unterstützt, denen die Berechtigung FullAccess für das freigegebene Postfach erteilt wurde. Weitere Informationen finden Sie unter [Verwenden der EAC zum Bearbeiten der freigegebenen Postfachdelegierung](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).

Spambenachrichtigungen für Endbenutzer werden für Gruppen nicht unterstützt.

> [!NOTE]
> Nachrichten, die als Phishing mit hoher Sicherheit, Schadsoftware oder durch Nachrichtenflussregeln (auch transport rules bezeichnet) isoliert wurden, stehen nur Administratoren zur Verfügung. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md).

Eine Spambenachrichtigung für Endbenutzer enthält die folgenden Informationen für jede isolierte Nachricht:

- **Sender**: Der Sendename und die E-Mail-Adresse der isolierten Nachricht.

- **Betreff**: Der Betreffzeilentext der isolierten Nachricht.

- **Date**: Das Datum und die Uhrzeit (in UTC), zu der die Nachricht isoliert wurde.

- **Absender blockieren**: Klicken Sie auf diesen Link, um den Absender ihrer Liste blockierter Absender hinzuzufügen. Weitere Informationen finden Sie unter [Blockieren eines E-Mail-Absenders.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)

- **Release**: Für Spamnachrichten (keine Phishing)-Nachrichten können Sie die Nachricht hier veröffentlichen, ohne das Security & Compliance Center unter Quarantäne zu stellen.

- **Review**: Klicken Sie auf diesen Link, um zu Quarantäne im Security & Compliance Center zu wechseln, in dem Sie (je nachdem, warum die Nachricht isoliert wurde) Ihre isolierten Nachrichten anzeigen, veröffentlichen, löschen oder melden können. Weitere Informationen finden Sie unter [Suchen und Veröffentlichen isolierter Nachrichten als Benutzer in EOP](find-and-release-quarantined-messages-as-a-user.md).

![Beispiel für Spambenachrichtigungen für Endbenutzer](../../media/end-user-spam-notification.png)

> [!NOTE]
> Ein blockierter Absender kann Ihnen weiterhin E-Mails senden. Alle Nachrichten von diesem Absender, die es in Ihr Postfach senden, werden sofort in den Junk-E-Mail-Ordner verschoben. Zukünftige Nachrichten von diesem Absender werden in Ihren Junk-E-Mail-Ordner oder in die Endbenutzerquarantäne verschoben. Wenn Sie diese Nachrichten bei der Ankunft löschen möchten, anstatt sie zu quarantinieren, verwenden Sie Nachrichtenflussregeln [(auch](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) als Transportregeln bezeichnet), um die Nachrichten bei der Ankunft zu löschen.