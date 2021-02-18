---
title: Hinzufügen von Unterstützung für anonym eingehende E-Mails über IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Der Administrator kann erfahren, wie Sie die Unterstützung für anonym eingehende E-Mails aus IPv6-Quellen in Exchange Online und Exchange Online Protection konfigurieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63c9434fbd1f69c0cbd3145717b712857eb17e28
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290273"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Hinzufügen von Unterstützung für anonym eingehende E-Mails über IPv6 in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft 365-Organisationen mit Exchange Online-Postfächern und eigenständige Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer unterstützen anonyme eingehende E-Mails über IPv6. Der Quell-IPv6-E-Mail-Server muss die beiden folgenden Anforderungen erfüllen:

- Die Quell-IPv6-Adresse muss über einen gültigen Reverse-DNS-Lookup (PTR)-Eintrag verfügen, mit dem das Ziel den Domänennamen aus der IPv6-Adresse finden kann.

- Der Absender muss entweder die SPF-Verifizierung (definiert in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oder die [DKIM-Verifizierung](http://dkim.org/) (definiert in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)) bestehen.

Bevor Ihre Organisation anonyme eingehende E-Mails über IPv6 empfangen kann, muss sich ein Administrator an den Support von Microsoft wenden und ihn bitten. Anweisungen zum Öffnen einer Supportanfrage finden Sie unter Kontaktieren des Support [für Geschäftsprodukte - Administratorhilfe.](../../admin/contact-support-for-business-products.md)

Nachdem die Unterstützung für anonyme eingehende IPv6-Nachrichten in Ihrer Organisation aktiviert wurde, wird die Nachricht durch die normale Nachrichtenfilterung durch den Dienst gesendet.

## <a name="troubleshooting"></a>Problembehandlung

- Wenn der Quell-E-Mail-Server keinen IPv6-Reverse-DNS-Lookup-Eintrag hat, werden die Nachrichten mit dem folgenden Fehler zurückgewiesen:

  > 450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.

- Wenn der Absender die SPF- oder DKIM-Überprüfung nicht besteht, werden die Nachrichten mit dem folgenden Fehler zurückgewiesen:

  > 450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.

- Wenn Sie versuchen, anonyme IPv6-Nachrichten zu empfangen, bevor Sie sich angemeldet haben, wird die Nachricht mit dem folgenden Fehler zurückgewiesen:

  > 550 5.2.1 Dienst nicht verfügbar; [contoso.com] akzeptiert keine E-Mails über IPv6.

## <a name="related-topics"></a>Verwandte Themen

[Unterstützung für die Validierung von mit DKIM signierten Nachrichten](support-for-validation-of-dkim-signed-messages.md)
