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
description: Administratoren können mehr über Spambenachrichtigungen für Endbenutzer für isolierte Nachrichten in Exchange Online Protection (EOP) erfahren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71f2a33ad83f94895c396f92c18753bfca7f2905
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933167"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Verwenden von Spambenachrichtigungen von Benutzern zum Freigeben und Melden von isolierten Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten. Weitere Informationen finden Sie unter ["Isolierte Nachrichten" in EOP.](quarantine-email-messages.md)

Standardmäßig sind Spambenachrichtigungen von Endbenutzern in Antispamrichtlinien deaktiviert. Wenn ein Administrator [Spambenachrichtigungen](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)für Endbenutzer aktiviert, erhalten Empfänger (einschließlich freigegebener Postfächer mit aktivierter automatischer Zuordnung) regelmäßige Benachrichtigungen über ihre Nachrichten, die als Spam, Massen-E-Mail oder (ab April 2020) Phishing unter Quarantäne gestellt wurden.

Bei freigegebenen Postfächern werden Spambenachrichtigungen für Endbenutzer nur für Benutzer unterstützt, denen die Berechtigung "FullAccess" für das freigegebene Postfach gewährt wurde. Weitere Informationen finden Sie unter [Verwenden des EAC zum Bearbeiten der delegierung freigegebener Postfächer.](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)

Endbenutzer-Spambenachrichtigungen werden für Gruppen nicht unterstützt.

> [!NOTE]
> Nachrichten, die als Phishing mit hohem Vertrauen, Schadsoftware oder durch Nachrichtenflussregeln (auch als Transportregeln bezeichnet) unter Quarantäne gestellt wurden, sind nur für Administratoren verfügbar. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md).

Eine Spambenachrichtigung für Endbenutzer enthält die folgenden Informationen für jede isolierte Nachricht:

- **Absender:** Der Sendename und die E-Mail-Adresse der isolierten Nachricht.
- **Betreff:** Der Betreffzeilentext der isolierten Nachricht.
- **Datum:** Datum und Uhrzeit (in UTC), zu denen die Nachricht in Quarantäne gestellt wurde.
- **Absender blockieren:** Klicken Sie auf diesen Link, um den Absender der Liste blockierter Absender in Ihrem Postfach hinzuzufügen. Weitere Informationen finden Sie unter [E-Mail-Absender blockieren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).
- **Release:** Für Spamnachrichten (nicht Phishingnachrichten) können Sie die Nachricht hier freigeben, ohne das Microsoft 365 Defender-Portal unter **Quarantäne** zu stellen.
- **Überprüfen Sie:** Klicken Sie auf diesen Link, um im Microsoft 365 Defender-Portal zur **Quarantäne** zu wechseln, wo Sie (je nachdem, warum die Nachricht unter Quarantäne gestellt wurde) Ihre isolierten Nachrichten anzeigen, freigeben, löschen oder melden können. Weitere Informationen finden Sie unter [Suchen und Freigeben von isolierten Nachrichten als Benutzer in EOP.](find-and-release-quarantined-messages-as-a-user.md)

![Beispiel für Spambenachrichtigungen für Endbenutzer](../../media/end-user-spam-notification.png)

> [!NOTE]
> Ein blockierter Absender kann Ihnen weiterhin E-Mails senden. Alle Nachrichten von diesem Absender, die sie an Ihr Postfach senden, werden sofort in den Junk-E-Mail-Ordner verschoben. Zukünftige Nachrichten von diesem Absender werden in Ihren Junk-E-Mail-Ordner oder in die Endbenutzerquarantäne verschoben. Wenn Sie diese Nachrichten bei der Ankunft löschen möchten, anstatt sie zu blockieren, verwenden Sie [Nachrichtenflussregeln](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch als Transportregeln bezeichnet), um die Nachrichten bei der Ankunft zu löschen.
