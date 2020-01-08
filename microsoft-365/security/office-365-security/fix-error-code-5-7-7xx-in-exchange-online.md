---
title: Beheben von Problemen mit der Zustellung von e-Mails bei Fehlercode 5.7.7 XX in Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Hier erfahren Sie, wie Sie e-Mail-Probleme für den Fehlercode 5.7.7 XX in Exchange Online beheben (vom Senden von e-Mails blockierte Mandanten).
ms.openlocfilehash: cbfff7fc0905206a0302f7e1a458718637d934b7
ms.sourcegitcommit: 8ac1b6586678035050fc422e6fb503fa478be397
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962304"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a>Beheben von Problemen mit der Zustellung von e-Mails bei Fehlercode 5.7.7 XX in Exchange Online

In diesem Thema wird beschrieben, was Sie tun können, wenn Sie den Statuscode 550 5.7.7 XX in einem Unzustellbarkeitsbericht (auch bekannt als NDR, Bounce-Nachricht, Benachrichtigung über den Zustellungsstatus oder DSN) sehen. Diese automatische Benachrichtigung wird angezeigt, wenn Ihr Mandant vom Senden von e-Mails auf die eine oder andere Weise eingeschränkt ist. Diese Fehlercodes werden normalerweise als 705 oder 750 verwendet.

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a>5.7.705: Mandant hat die Schwellenwertbeschränkung überschritten: was Sie wissen müssen

Sobald Ihre Benutzer (gemeinsam, als Organisation) eine bestimmte Menge verdächtiger e-Mails über den Dienst senden, können alle Benutzer daran gehindert werden, eine e-Mail zu senden, bis das Problem behoben ist. Dies ist normalerweise das Ergebnis eines Kompromisses (am häufigsten) oder das Senden zu viel Massen-e-Mail. Benutzer erhalten einen NDR, der besagt:

`550 5.7.705 Access denied, tenant has exceeded threshold`

In seltenen Fällen kann dies auch passieren, wenn Sie Ihr Abonnement erneuern, nachdem es bereits abgelaufen ist. Es dauert Zeit, bis der Dienst die neuen Abonnementinformationen synchronisiert (normalerweise nicht mehr als einen Tag), aber Ihre Organisation könnte in der Zwischenzeit daran gehindert werden, e-Mails zu senden. Die beste Möglichkeit, dies zu verhindern, besteht darin, sicherzustellen, dass Ihr Abonnement nicht abläuft.

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a>5.7.750: nicht registrierte Domänen-e-Mail-Einschränkung: was Sie wissen müssen

Office 365 ermöglicht Mandanten das Weiterleiten einiger Nachrichten über Exchange Online Protection (EoP). Beispiel:

- Ein Office 365 Postfach empfängt e-Mails von einem externen Absender. Die e-Mail-Weiterleitung ist für das Office 365 Postfach konfiguriert, sodass die Nachricht an die externe e-Mail-Adresse des Benutzers zurückgeht. Dieses Szenario ist am häufigsten in Bildungsumgebungen, in denen Kursteilnehmer ihre persönlichen e-Mail-Konten zum Anzeigen von schulbezogenen Nachrichten verwenden möchten.

- Hybrid Umgebungen mit lokalen e-Mail-Servern, die ausgehende e-Mails über EoP senden.

### <a name="problems-with-unregistered-domains"></a>Probleme mit nicht registrierten Domänen

Das Problem besteht darin, dass kompromittierte lokale e-Mail-Server eine große Menge von Spam über EoP weiterleiten. In fast allen Fällen sind die Connectors ordnungsgemäß eingerichtet, aber e-Mails werden von nicht registrierten Domänen (auch als Nichtbereitstellung bezeichnet) gesendet. Office 365 eine angemessene Menge an e-Mails aus nicht registrierten Domänen zulässt, sollten Sie jedoch jede Domäne konfigurieren, die Sie zum Senden von e-Mails als akzeptierte Domäne verwenden.

Nachdem die Mandanten kompromittiert wurden, wird verhindert, dass ausgehende e-Mails für nicht registrierte Domänen gesendet werden. Benutzer erhalten einen NDR, der besagt:

`550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains`

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a>Gewusst wie Aufheben der Blockierung von Mandanten, um erneut zu senden

Es gibt verschiedene Dinge, die Sie ausführen müssen, wenn Ihr Mandant für das Senden von e-Mails gesperrt ist:

1. Stellen Sie sicher, dass alle Ihre e-Mail-Domänen registriert sind. Weitere Informationen finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) und [Verwalten von akzeptierten Domänen in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

2. Suchen Sie nach ungewöhnlichen [Konnektoren](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow). Böswillige Akteure erstellen häufig neue eingehende Connectors in Ihrer Office 365 Organisation, um Spam zu senden. Informationen zum Anzeigen der vorhandenen Connectors finden Sie unter [Validate Connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors).

3. Suchen Sie nach kompromittierten Benutzern, wie unter [Antworten auf ein kompromittiertes e-Mail-Konto in Office 365](responding-to-a-compromised-email-account.md)beschrieben.

4. [Aktivieren Sie MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) für alle Administratoren in Ihrer Office 365 Organisation.

5. Sperren Sie Ihre lokalen e-Mail-Server, und stellen Sie sicher, dass Sie nicht beeinträchtigt werden.

   > [!TIP]
   > Es gibt viele Faktoren, vor allem, wenn Sie Drittanbieterserver verwenden. Unabhängig davon müssen Sie sicherstellen, dass alle ausgehenden e-Mails jetzt legitim sind.

6. Wenden Sie sich an den Microsoft-Support, und bitten Sie den Mandanten, die Blockierung für das Senden von nicht registrierten Domänen wieder aufzuheben. Der Fehlercode ist hilfreich, aber Sie müssen nachweisen, dass Ihre Umgebung gesichert wurde und keine Spamnachrichten senden kann. Informationen zum Öffnen eines Support Falls finden Sie unter [kontaktieren des Supports für Geschäftsprodukte-Administratorhilfe](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

## <a name="for-more-information"></a>Weitere Informationen

[Antispamschutz für Office 365-E-Mails](anti-spam-protection.md)

[Massen-e-Mail-Anleitung im Abschnitt Senden von Grenzwerten der Exchange Online Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

[Unzustellbarkeitsberichte für E-Mails in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

[Konfigurieren der E-Mail-Weiterleitung für ein Postfach](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Einrichten eines Multifunktionsgeräts oder einer Anwendung zum Senden von E-Mails mit Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-office-3)

[Verwalten von akzeptierten Domänen in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
