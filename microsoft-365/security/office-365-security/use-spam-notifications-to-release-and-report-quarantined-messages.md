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
description: Administratoren können sich über Spambenachrichtigungen für Endbenutzer für isolierte Nachrichten in Exchange Online Protection (EOP) informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb347f7fd3d3793b563714e8116316b30165ef9a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287545"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Verwenden von Spambenachrichtigungen für Benutzer zum Veröffentlichen und Melden von isolierten Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten. Weitere Informationen finden Sie unter ["Isolierte Nachrichten" in EOP.](quarantine-email-messages.md)

Standardmäßig sind Spambenachrichtigungen für Endbenutzer in Antispamrichtlinien deaktiviert. Wenn ein Administrator Spambenachrichtigungen für Endbenutzer aktiviert, erhalten Empfänger (einschließlich freigegebener Postfächer mit aktivierter automatischerMapping) regelmäßige Benachrichtigungen zu ihren Nachrichten, die als Spam, [Massen-E-Mail](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)oder (ab April 2020) Phishing isoliert wurden.

Bei freigegebenen Postfächern werden Spambenachrichtigungen für Endbenutzer nur für Benutzer unterstützt, denen die Berechtigung "FullAccess" für das freigegebene Postfach erteilt wurde. Weitere Informationen finden Sie unter Bearbeiten der delegierung freigegebener Postfächer mithilfe [der EAC.](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)

Spambenachrichtigungen für Endbenutzer werden für Gruppen nicht unterstützt.

> [!NOTE]
> Nachrichten, die als Phishing mit hoher Confidence, Schadsoftware oder durch Nachrichtenflussregeln (auch als Transportregeln bezeichnet) isoliert wurden, sind nur für Administratoren verfügbar. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md).

Eine Spambenachrichtigung für Endbenutzer enthält die folgenden Informationen für jede isolierte Nachricht:

- **Absender:** Der Sendename und die E-Mail-Adresse der isolierten Nachricht.

- **Betreff:** Der Betreffzeilentext der isolierten Nachricht.

- **Datum**: Datum und Uhrzeit (in UTC), zu der die Nachricht isoliert wurde.

- **Absender blockieren:** Klicken Sie auf diesen Link, um den Absender ihrer Liste blockierter Absender hinzuzufügen. Weitere Informationen finden Sie unter ["Blockieren eines E-Mail-Absenders".](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)

- **Release:** Für Spamnachrichten (keine Phishing-Nachrichten) können Sie die Nachricht hier frei geben, ohne das Security & Compliance Center unter Quarantäne zu stellen.

- **Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages. Weitere Informationen finden Sie unter "Suchen und Veröffentlichen von Nachrichten in Quarantäne [als Benutzer in EOP".](find-and-release-quarantined-messages-as-a-user.md)

![Beispiel für eine Spambenachrichtigung für Endbenutzer](../../media/end-user-spam-notification.png)

> [!NOTE]
> Ein blockierter Absender kann Ihnen weiterhin E-Mails senden. Alle Nachrichten von diesem Absender, die es an Ihr Postfach senden, werden sofort in den Junk-E-Mail-Ordner verschoben. Zukünftige Nachrichten von diesem Absender werden in Ihren Junk-E-Mail-Ordner oder in die Quarantäne des Endbenutzers verschoben. Wenn Sie diese Nachrichten beim Eintreffen löschen möchten, anstatt sie zu quarantinieren, verwenden Sie Nachrichtenflussregeln [(auch](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) als Transportregeln bezeichnet), um die Nachrichten beim Eintreffen zu löschen.
