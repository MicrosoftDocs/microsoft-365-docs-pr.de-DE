---
title: Verbinden Ihrer Domäne zu Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie, wie Sie Ihre Domäne bestätigen und DNS-Einträge mit Microsoft 365 erstellen.
ms.custom:
- AdminSurgePortfolio
ms.openlocfilehash: 506ee887edbc59956aee11059a7085bc4b22624e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914594"
---
# <a name="connect-your-domain-to-microsoft-365"></a>Verbinden Ihrer Domäne zu Microsoft 365

> [!NOTE]
> Wenn Sie keine Domäne hinzufügen, verwenden Personen in Ihrer Organisation die Domäne „onmicrosoft.com“ für ihre E-Mail-Adressen, bis Sie dies tun. Es ist wichtig, dass Sie Ihre Domäne hinzufügen, bevor Sie Benutzer hinzufügen, damit Sie diese nicht zweimal einrichten müssen.

[Lesen Sie in den die häufig gestellten Fragen (FAQ) zu Domänen nach](../setup/domains-faq.yml), wenn Sie unten nicht finden, wonach Sie suchen.

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.

Sie erhalten nun die Informationen zu dem MX-Eintrag vom Assistenten für die Domäneneinrichtung im Admin Center.

Fügen Sie auf der Website Ihres Hostinganbieters einen neuen MX-Eintrag hinzu.
Stellen Sie sicher, dass die Felder auf die folgenden Werte festgelegt sind:

- Eintragstyp: `MX`
- Priorität: Legen Sie dies auf den höchsten verfügbaren Wert fest, in der Regel `0`.
- Hostname: `@`
- Verweist auf die Adresse: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.
- TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)

Speichern Sie den Eintrag, und entfernen Sie dann alle anderen MX-Einträge.

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a>CNAME-Eintrag hinzufügen, um Benutzer zu ihren Postfächern zu verbinden
Sie erhalten die Informationen zu den CNAME-Einträgen vom Assistenten für die Domäneneinrichtung im Admin Center.

Fügen Sie auf der Website Ihres Hosting-Anbieters die folgenden CNAME-Einträge hinzu. Stellen Sie sicher, dass jedes der Felder auf die jeweiligen folgenden Werte festgelegt ist:

- Eintragstyp: `CNAME (Alias)`
- Host: Fügen Sie hier die Werte ein, die Sie aus dem Admin Center kopieren.
- Verweist auf die Adresse: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.
- TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)

## <a name="add-a-txt-record-to-help-prevent-spam"></a>Hinzufügen eines TXT-Eintrags, um Spam zu verhindern
**Bevor Sie beginnen:** Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft 365 keinen neuen. Fügen Sie stattdessen die erforderlichen Microsoft 365-Werte dem aktuellen Eintrag auf der Website Ihres Hostinganbieters hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.

Bearbeiten Sie auf der Website Ihres Hostinganbieters den vorhandenen SPF-Eintrag, oder erstellen Sie einen neuen SPF-Eintrag.
Stellen Sie sicher, dass die Felder auf die folgenden Werte festgelegt sind:

- Eintragstyp: `TXT (Text)`
- Host: `@`
- TXT-Wert: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)

Speichern Sie den Eintrag.

Überprüfen Sie Ihren SPF-Eintrag, indem Sie eines dieser [SPF-Überprüfungstools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) verwenden.

SPF ist dafür vorgesehen, Spoofing möglichst zu verhindern, es gibt aber Spoofing-Techniken, vor denen SPF nicht schützen kann. Zum Schutz vor diesen Techniken sollten Sie, nachdem Sie SPF eingerichtet haben, auch DKIM und DMARC für Microsoft 365 einrichten.

Um hiermit zu beginnen, lesen Sie [Verwenden von DKIM zur Überprüfung von ausgehenden E-Mails, die von Ihrer Domäne in Microsoft 365 gesendet wurden](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) und [Verwenden von DMARC zum Überprüfen von E-Mail in Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).

Wechseln Sie schlussendlich zurück zum Assistenten für die Domäneneinrichtung im Admin Center, um Ihre Einrichtung abzuschließen.