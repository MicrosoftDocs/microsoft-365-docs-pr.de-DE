---
title: Listen sicherer und blockierter Absender in Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Als Exchange Online- oder Exchange Online Protection-Administrator (EOP) können Sie sicherstellen, dass eine E-Mail-Nachricht, die den Dienst durchläuft, nicht als Spam gekennzeichnet wird. Eine Möglichkeit hierzu ist das Erstellen von Listen mit sicheren Absendern und blockierten Absendern für die Personen in Ihrer Organisation.
ms.openlocfilehash: 959af558c32e71e5a4cede2aff7bbcd1dbb092e2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598512"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Listen sicherer und blockierter Absender in Exchange Online

Als Exchange Online- oder Exchange Online Protection-Administrator (EOP) können Sie sicherstellen, dass eine E-Mail-Nachricht, die den Dienst durchläuft, nicht als Spam gekennzeichnet wird. Eine Möglichkeit hierzu ist das Erstellen von Listen mit sicheren Absendern und blockierten Absendern für die Personen in Ihrer Organisation.

*Lesen Sie die aktualisierte Version der Tipps und Verfahren für die Verwendung dieser Listen als Administrator* , [um zu verhindern, dass gute e-Mails in Office 365 als Spam gekennzeichnet werden](prevent-email-from-being-marked-as-spam.md).

Wenn Sie kein Administrator sind und nur Ihre eigenen Junk-e-Mails in Outlook mithilfe einer Liste sicherer Absender verwalten möchten, lesen Sie die Schritte in der Übersicht über[den Junk-e-Mail-Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Was sind die Grenzwerte sicherer und blockierter Absender in Exchange Online?

Die Grenzwerte sicherer und blockierter Absender in Exchange Online unterscheiden sich von den Grenzwerten von Active Directory und Outlook. Dies sind:

- Grenzwert sicherer Absender: 1.024

- Grenzwert blockierter Absender: 500

Hinweis:

Sie können den in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)beschriebenen Fehler auftreten. Um dieses Problem zu beheben, deaktivieren Sie das Kontrollkästchen „E-Mails von meinen Kontakten vertrauen". Alternativ verringern Sie die Anzahl der e-Mail-Adressen, die sich in Ihrem Standardordner Kontakte befinden, so, dass Sie innerhalb des zulässigen Höchstwerts von 1024 in Exchange Online, die für das Attribut "Parameter MaxSafeSenders" festgelegt sind, zurückgegeben wird. Weitere Informationen über dieses Attribut und das Cmdlet „Set-Mailbox" finden Sie in dem folgenden Artikel:

[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a>Siehe auch

[Absenderfilterung in Exchange Server](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
