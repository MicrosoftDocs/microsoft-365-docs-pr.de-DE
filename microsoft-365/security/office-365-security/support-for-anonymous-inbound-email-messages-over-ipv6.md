---
title: Hinzufügen von Unterstützung für anonym eingehende E-Mails über IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Der Administrator kann erfahren, wie die Unterstützung für anonyme eingehende e-Mails aus IPv6-Quellen in Exchange Online und Exchange Online Schutz konfiguriert wird.
ms.openlocfilehash: f2e14fe2e8e46d6085fc3764d3a41382f15049e9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950294"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Hinzufügen von Unterstützung für anonyme eingehende e-Mails über IPv6 in Microsoft 365

Microsoft 365-Organisationen mit Exchange Online-Postfächern und eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer unterstützen anonyme eingehende e-Mails über IPv6. Der Quell-IPv6-e-Mail-Server muss die folgenden Anforderungen erfüllen:

- Die IPv6-Quelladresse muss einen gültigen PTR-Eintrag (Reverse DNS Lookup) besitzen, mit dem das Ziel den Domänennamen aus der IPv6-Adresse ermitteln kann.

- Der Absender muss entweder die SPF-Verifizierung (definiert in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oder die [DKIM-Verifizierung](http://dkim.org/) (definiert in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)) bestehen.

Bevor Ihre Organisation anonyme eingehende e-Mails über IPv6 erhalten kann, muss sich ein Administrator an den Microsoft-Support wenden und ihn Fragen. Anweisungen zum Öffnen einer Supportanforderung finden Sie unter [kontaktieren des Supports für Business-Produkte – Administratorhilfe](../../admin/contact-support-for-business-products.md).

Nachdem die anonyme eingehende IPv6-Nachrichten Unterstützung in Ihrer Organisation aktiviert wurde, wird die Nachricht durch die normale Nachrichtenfilterung geleitet, die vom Dienst bereitgestellt wird.

## <a name="troubleshooting"></a>Problembehandlung

- Wenn der Quell-e-Mail-Server keinen IPv6-Reverse-DNS-Nachschlage Eintrag aufweist, werden die Nachrichten mit folgendem Fehler zurückgewiesen:

  > 450 4.7.25-Dienst nicht verfügbar ist, muss das Senden einer IPv6-Adresse [2a01:111: F200:2004:: 240] einen Reverse-DNS-Eintrag aufweisen.

- Wenn der Absender die SPF-oder DKIM-Validierung nicht übergibt, werden die Nachrichten mit folgendem Fehler zurückgewiesen:

  > 450 4.7.26-Dienst nicht verfügbar, Nachrichten, die über IPv6 gesendet werden [2a01:111: F200:2004:: 240] müssen die SPF-oder DKIM-Validierung übergeben.

- Wenn Sie versuchen, anonyme IPv6-Nachrichten zu erhalten, bevor Sie sich entschieden haben, wird die Nachricht mit folgendem Fehler zurückgewiesen:

  > 550 5.2.1 Dienst nicht verfügbar; [contoso.com] akzeptiert keine e-Mails über IPv6.

## <a name="related-topics"></a>Verwandte Themen

[Unterstützung für die Validierung von mit DKIM signierten Nachrichten](support-for-validation-of-dkim-signed-messages.md)