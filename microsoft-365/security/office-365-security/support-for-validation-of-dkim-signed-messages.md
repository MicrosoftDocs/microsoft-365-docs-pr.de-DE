---
title: Unterstützung für die Überprüfung von dkIM (Domain Keys Identified Mail) signierten Nachrichten
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über die Überprüfung von DKIM-signierten Nachrichten in Exchange Online Protection und Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8695e25000390cf6c5d58adf63db1984c873d75b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206461"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Unterstützung für die Validierung von mit DKIM signierten Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) und Exchange Online unterstützen die eingehende Überprüfung von Domänenschlüsseln identifizierte E-Mails ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) Nachrichten.

DKIM überprüft, ob eine E-Mail-Nachricht nicht von einer anderen Person gefälscht wurde und von der Domäne gesendet wurde, von der sie sagt, *dass* sie stammt.  Es bindet eine E-Mail-Nachricht an die Organisation, die sie gesendet hat. Die DKIM-Überprüfung wird automatisch für alle Nachrichten verwendet, die mit IPv6 gesendet werden. Microsoft 365 unterstützt auch DKIM, wenn E-Mails über IPv4 gesendet werden. Weitere Informationen zur Unterstützung von IPv6 finden Sie unter [Unterstützung für anonym eingehende E-Mail-Nachrichten über IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).

DKIM überprüft eine digital signierte Nachricht, die im DKIM-Signature der Nachrichtenkopfzeilen angezeigt wird. Die Ergebnisse einer DKIM-Signature werden in der Kopfzeile Authentication-Results gestempelt. Der Nachrichtenkopftext sieht in etwa folgendermaßen aus (wobei "contoso.com" der Sender ist):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Weitere Informationen zum Authentication-Results finden Sie unter RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt). Die DKIM-Implementierung von Microsoft entspricht dieser RFC.

Administratoren können Exchange [E-Mail-Flussregeln](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch als Transportregeln bezeichnet) für die Ergebnisse der DKIM-Überprüfung erstellen. Diese Nachrichtenflussregeln ermöglichen Administratoren das Filtern oder Routen von Nachrichten nach Bedarf.