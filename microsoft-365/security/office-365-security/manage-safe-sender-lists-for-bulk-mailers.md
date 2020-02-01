---
title: Verwalten sicherer Absenderlisten für Absender von Massen-E-Mails
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 'Wenn Sie Listen sicherer Absender verwenden möchten, sollten Sie wissen, dass die Verarbeitung in Exchange Online Protection (EOP) und Outlook auf verschiedene Weise erfolgt. Der Dienst berücksichtigt sichere Absender und Domänen, indem er die RFC 5321.MailFrom-Adresse und die RFC 5322.From-Adresse prüft, während Outlook die RFC 5322.From-Adresse zur Liste sicherer Absender eines Benutzers hinzufügt. (Anmerkung: Der Dienst prüft sowohl die 5321.MailFrom-Adresse als auch die 5322.From-Adresse auf blockierte Absender und Domänen.)'
ms.openlocfilehash: aaede7cab2e640603c20804f4015e19f61b6c2f3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598942"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>Verwalten sicherer Absenderlisten für Absender von Massen-E-Mails

Wenn Sie Listen sicherer Absender verwenden möchten, sollten Sie wissen, dass die Verarbeitung in Exchange Online Protection (EOP) und Outlook auf verschiedene Weise erfolgt. Der Office 365 Dienst respektiert sichere Absender und Domänen, indem er die `RFC 5321.MailFrom` Adresse und die `RFC 5322.From` Adresse überprüft, während Outlook die Adresse `RFC 5322.From` der Liste sicherer Absender eines Benutzers hinzufügt. (Hinweis: der Dienst untersucht sowohl `5321.MailFrom` Adresse als auch `5322.From` Adresse für blockierte Absender und Domänen.)

Die `SMTP MAIL FROM` Adresse, auch bekannt als die `RFC 5321.MailFrom address`, ist die e-Mail-Adresse, die zum Durchführen von SPF-Überprüfungen verwendet wird, und wenn die e-Mail nicht zugestellt werden kann, der Pfad, an den die zurückgegebene Nachricht übermittelt wird. Es handelt sich um diese e-Mail-Adresse `Return-Path` , die standardmäßig in die Nachrichtenkopfzeilen eingefügt wird, obwohl es dem Absender möglich ist, `Return-Path` eine andere Adresse festzulegen.

Die `From:` Adresse in den Nachrichtenkopfzeilen, die sonst als `RFC 5322.From` Adresse bezeichnet wird, ist die e-Mail-Adresse, die im e-Mail-Client wie Outlook angezeigt wird.

Ein Großteil der Zeit sind die `5321.MailFrom` - `5322.From` und-Adressen identisch. Dies ist z. B. bei der Kommunikation zwischen zwei privaten Nutzern normal. Wenn allerdings die E-Mail im Auftrag eines anderen Benutzers gesendet wird, sind die Adressen häufig verschieden. Dies ist am häufigsten bei Massen-E-Mail-Nachrichten der Fall.

Nehmen wir beispielsweise an, dass die Blue Yonder Airlines Margie es Travel angeheuert hat, um Ihre e-Mail-Werbung zu senden. Sie finden dann eine E-Mail in Ihrem Posteingang vor, die vom Absender blueyonder@news.blueyonderairlines.com stammt. In diesem Beispiel:

- Die `5321.MailFrom` Adresse lautet blueyonder.Airlines@margiestravel.com.

- Die `5322.From` Adresse lautet blueyonder@News.blueyonderairlines.com, was Sie in Outlook sehen.

Um zu verhindern, dass diese Nachricht gefiltert wird, haben Sie folgende Möglichkeiten:

- **Als Benutzer**: Fügen Sie die `RFC 5322.From` Adresse als sicherer Absender in Outlook hinzu.

- **Als Administrator**: richten Sie eine [e-Mail-Fluss Regel](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) ein (auch als Transportregel bezeichnet).
