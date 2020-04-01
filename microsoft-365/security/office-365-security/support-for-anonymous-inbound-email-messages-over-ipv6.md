---
title: Hinzufügen von Unterstützung für anonyme eingehende e-Mails über IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: Der Administrator kann erfahren, wie die Unterstützung für anonyme eingehende e-Mails aus IPv6-Quellen in Exchange Online und Exchange Online Schutz konfiguriert wird.
ms.openlocfilehash: 67e839249d41381be22bbccf6b09d1616c387c66
ms.sourcegitcommit: 748bc3484b7ccbd65b558f495b6fa42196c3c571
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2020
ms.locfileid: "43083641"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a>Hinzufügen von Unterstützung für anonyme eingehende e-Mails über IPv6 in Office 365

Office 365 Organisationen mit Exchange Online Postfächern und eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer unterstützen anonyme eingehende e-Mails über IPv6. Der Quell-IPv6-e-Mail-Server muss die folgenden Anforderungen erfüllen:

- Die IPv6-Quelladresse muss einen gültigen PTR-Eintrag (Reverse DNS Lookup) besitzen, mit dem das Ziel den Domänennamen aus der IPv6-Adresse ermitteln kann.

- Der Absender muss entweder die SPF-Verifizierung (definiert in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oder die [DKIM-Verifizierung](https://dkim.org/) (definiert in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)) bestehen.

Bevor Ihre Organisation anonyme eingehende e-Mails über IPv6 erhalten kann, muss sich ein Administrator an den Microsoft-Support wenden und ihn Fragen:

1. Öffnen Sie das Microsoft 365 Admin Center <https://admin.microsoft.com/adminportal/home> unter, und klicken Sie auf **Hilfe** (?).

2. Geben Sie im Dialogfeld **Hilfe benötigen?** ein, das angezeigt wird, in das Suchfeld ein (beispielsweise "Anonym eingehende IPv6-e-Mail anfordern"), und drücken Sie dann die EINGABETASTE.

3. Klicken Sie unten auf der Seite auf **Support kontaktieren**.

4. Füllen Sie auf der angezeigten Seite **Kontakt Support** die Informationen aus, und überprüfen Sie diese (Scrollen Sie nach Bedarf), und klicken Sie dann auf **Kontakt mit mir**.

Nachdem die anonyme eingehende IPv6-Nachrichten Unterstützung in Ihrer Organisation aktiviert wurde, wird die Nachricht durch die normale Nachrichtenfilterung geleitet, die vom Dienst bereitgestellt wird.

## <a name="troubleshooting"></a>Problembehandlung

- Wenn der Quell-e-Mail-Server keinen IPv6-Reverse-DNS-Nachschlage Eintrag aufweist, werden die Nachrichten mit folgendem Fehler zurückgewiesen:

  > 450 4.7.25-Dienst nicht verfügbar ist, muss das Senden einer IPv6-Adresse [2a01:111: F200:2004:: 240] einen Reverse-DNS-Eintrag aufweisen.

- Wenn der Absender die SPF-oder DKIM-Validierung nicht übergibt, werden die Nachrichten mit folgendem Fehler zurückgewiesen:

  > 450 4.7.26-Dienst nicht verfügbar, Nachrichten, die über IPv6 gesendet werden [2a01:111: F200:2004:: 240] müssen die SPF-oder DKIM-Validierung übergeben.

- Wenn Sie versuchen, anonyme IPv6-Nachrichten zu erhalten, bevor Sie sich entschieden haben, wird die Nachricht mit folgendem Fehler zurückgewiesen:

  > 550 5.2.1 Dienst nicht verfügbar; [contoso.com] akzeptiert keine e-Mails über IPv6.

## <a name="for-more-information"></a>Weitere Informationen

[Unterstützung für die Validierung von mit DKIM signierten Nachrichten](support-for-validation-of-dkim-signed-messages.md)
