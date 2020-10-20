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
description: Administratoren können Informationen zu Endbenutzer-Spambenachrichtigungen für isolierte Nachrichten in Exchange Online Protection (EoP) erhalten.
ms.openlocfilehash: 0440056e8e31d24e659f9d0ff6662f86f31a6189
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600297"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Verwenden von Spambenachrichtigungen für Benutzer zum Freigeben und melden von Nachrichten in Quarantäne

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten. Weitere Informationen finden Sie unter [Quarantined Messages in EoP](quarantine-email-messages.md).

Standardmäßig sind Spambenachrichtigungen für Endbenutzer in Anti-Spam-Richtlinien deaktiviert. Wenn ein Administrator [Spambenachrichtigungen für Endbenutzer aktiviert](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), erhalten die Empfänger (einschließlich freigegebener Postfächer mit aktivierter Automapping) regelmäßig Benachrichtigungen über Ihre Nachrichten, die als Spam, Massen-e-Mails oder (ab April 2020) als Phishing-Nachricht isoliert wurden.

Bei freigegebenen Postfächern werden Endbenutzer-Spambenachrichtigungen nur für Benutzer unterstützt, denen FullAccess-Berechtigungen für das freigegebene Postfach erteilt werden. Weitere Informationen finden Sie unter [Verwenden der Exchange-Verwaltungskonsole zum Bearbeiten der Delegierung freigegebener Postfächer](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).

Spam Benachrichtigungen für Endbenutzer werden für Gruppen nicht unterstützt.

> [!NOTE]
> Nachrichten, die als vertrauenswürdiges Phishing, Schadsoftware oder Nachrichtenfluss Regeln (auch bekannt als Transportregeln) unter Quarantäne gestellt wurden, stehen nur Administratoren zur Verfügung. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md).

Eine spambenachrichtigung für Endbenutzer enthält für jede isolierte Nachricht die folgenden Informationen:

- **Sender**: der Absender Name und die e-Mail-Adresse der isolierten Nachricht.

- **Betreff**: der Text der Betreffzeile der isolierten Nachricht.

- **Date**: das Datum und die Uhrzeit (in UTC), in denen die Nachricht isoliert wurde.

- **Absender blockieren**: Klicken Sie auf diesen Link, um den Absender der Liste blockierter Absender hinzuzufügen. Weitere Informationen finden Sie unter [Blockieren eines e-Mail-Absenders](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Release**: bei Spamnachrichten (keine Phishing-Nachrichten) können Sie die Nachricht hier freigeben, ohne das Sicherheits & Compliance Center zu isolieren.

- **Review**: Klicken Sie auf diesen Link, um im Security & Compliance Center auf Quarantäne zu wechseln, wo Sie (je nachdem, warum die Nachricht unter Quarantäne gestellt wurde) die isolierten Nachrichten anzeigen, freigeben, löschen oder melden können. Weitere Informationen finden Sie unter [Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer in EoP](find-and-release-quarantined-messages-as-a-user.md).

![Beispiel-spambenachrichtigung für Endbenutzer](../../media/end-user-spam-notification.png)

> [!NOTE]
> Ein blockierter Absender kann Ihnen weiterhin e-Mails senden. Alle Nachrichten von diesem Absender, die es in Ihrem Postfach vornehmen, werden sofort in den Ordner Junk-e-Mail verschoben. Zukünftige Nachrichten von diesem Absender werden in den Junk-e-Mail-Ordner oder in die Endbenutzer Quarantäne verschoben. Wenn Sie diese Nachrichten bei der Ankunft löschen möchten, statt sie zu isolieren, verwenden Sie [Nachrichtenfluss Regeln](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch als Transportregeln bezeichnet), um die Nachrichten bei der Ankunft zu löschen.
