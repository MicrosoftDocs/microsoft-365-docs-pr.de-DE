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
description: Administratoren erfahren, wie Sie die Unterstützung für anonyme eingehende E-Mails aus IPv6-Quellen in Exchange Online und Exchange Online Protection konfigurieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: df06891401802d212cbfdb55085662901f5546e9
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206474"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Hinzufügen von Unterstützung für anonyme eingehende E-Mails über IPv6 in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365-Organisationen mit Exchange Online-Postfächern und eigenständige Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer unterstützen anonyme eingehende E-Mails über IPv6. Der Quell-IPv6-E-Mail-Server muss die beiden folgenden Anforderungen erfüllen:

- Die Quell-IPv6-Adresse muss über einen gültigen Reverse-DNS-Nachschlagedatensatz (Reverse DNS Lookup, PTR) verfügen, mit dem das Ziel den Domänennamen von der IPv6-Adresse finden kann.

- Der Absender muss entweder die SPF-Verifizierung (definiert in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oder die [DKIM-Verifizierung](http://dkim.org/) (definiert in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)) bestehen.

Bevor Ihre Organisation anonyme eingehende E-Mails über IPv6 empfangen kann, muss sich ein Administrator an den Microsoft-Support wenden und diese fragen. Anweisungen zum Öffnen einer Supportanfrage finden Sie unter [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).

Nachdem die Unterstützung für anonyme eingehende IPv6-Nachrichten in Ihrer Organisation aktiviert wurde, wird die Nachricht durch die normale Nachrichtenfilterung durchgehen, die vom Dienst bereitgestellt wird.

## <a name="troubleshooting"></a>Problembehandlung

- Wenn der Quell-E-Mail-Server keinen IPv6-Reverse-DNS-Nachschlagedatensatz hat, werden die Nachrichten mit dem folgenden Fehler zurückgewiesen:

  > 450 4.7.25 Dienst nicht verfügbar, sendende IPv6-Adresse [2a01:111:f200:2004::240] muss über einen reversen DNS-Eintrag verfügen.

- Wenn der Absender die SPF- oder DKIM-Überprüfung nicht besteht, werden die Nachrichten mit dem folgenden Fehler zurückgewiesen:

  > 450 4.7.26 Dienst nicht verfügbar, über IPv6 gesendete Nachricht [2a01:111:f200:2004::240] muss entweder die SPF- oder die DKIM-Überprüfung bestehen.

- Wenn Sie versuchen, anonyme IPv6-Nachrichten zu empfangen, bevor Sie sich angemeldet haben, wird die Nachricht mit dem folgenden Fehler zurückgewiesen:

  > 550 5.2.1 Dienst nicht verfügbar, [contoso.com] akzeptiert keine E-Mails über IPv6.

## <a name="related-topics"></a>Verwandte Themen

[Unterstützung für die Validierung von mit DKIM signierten Nachrichten](support-for-validation-of-dkim-signed-messages.md)
