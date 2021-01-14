---
title: Unterstützung für die Überprüfung von DKIM (Domain Keys Identified Mail)-signierten Nachrichten
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über die Überprüfung von MIT DKIM signierten Nachrichten in Exchange Online Protection und Exchange Online
ms.openlocfilehash: 91a01f89bb633a38d27ddd3f2945b8707643d7e9
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845059"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Unterstützung für die Validierung von mit DKIM signierten Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Exchange Online Protection (EOP) und Exchange Online unterstützen beide die eingehende Überprüfung von Domänenschlüsseln identifizierter E-Mail-Nachrichten[(DKIM).](https://www.rfc-editor.org/rfc/rfc6376.txt)

DKIM überprüft, ob eine E-Mail-Nachricht von einer anderen Person gefälscht wurde und dass sie von der Domäne gesendet wurde, von der sie sagt, dass *sie* stammt.  Es bindet eine E-Mail-Nachricht an die Organisation, die sie gesendet hat. Die DKIM-Überprüfung wird automatisch für alle Nachrichten verwendet, die mit IPv6 gesendet werden. Microsoft 365 unterstützt dkIM auch, wenn E-Mails über IPv4 gesendet werden. Weitere Informationen zur Unterstützung von IPv6 finden Sie unter [Unterstützung für anonym eingehende E-Mail-Nachrichten über IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).

DKIM überprüft eine digital signierte Nachricht, die in DKIM-Signature Kopfzeile der Nachrichtenkopfzeilen angezeigt wird. Die Ergebnisse einer DKIM-Signature werden in der Kopfzeile Authentication-Results gestempelt. Der Nachrichtenkopftext sieht in etwa folgendermaßen aus (wobei "contoso.com" der Sender ist):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Weitere Informationen zum Nachrichtenkopf Authentication-Results finden Sie unter RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt). Die Microsoft -DKIM-Implementierung entspricht dieser RFC.

Administratoren können [Exchange-Nachrichtenflussregeln](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch als Transportregeln bezeichnet) für die Ergebnisse der DKIM-Überprüfung erstellen. Diese Nachrichtenflussregeln ermöglichen Administratoren das Filtern oder Routen von Nachrichten nach Bedarf.
