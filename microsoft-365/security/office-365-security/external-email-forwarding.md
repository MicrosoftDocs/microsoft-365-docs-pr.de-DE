---
title: Konfigurieren und Steuern der externen e-Mail-Weiterleitung, automatische Weiterleitung, 5.7.520 Zugriff verweigert, externe Weiterleitung deaktivieren, Ihr Administrator hat externe Weiterleitung deaktiviert, ausgehende Anti-Spam-Richtlinie
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: c1a7cd4d8f00c9e2433601903efd1fba7bb587f9
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681732"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Steuern der automatischen externen e-Mail-Weiterleitung in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Als Administrator haben Sie möglicherweise Unternehmens Anforderungen zum einschränken oder Steuern der automatischen Weiterleitung von Nachrichten an externe Empfänger (Empfänger außerhalb Ihrer Organisation). Die e-Mail-Weiterleitung kann nützlich sein, kann aber auch ein Sicherheitsrisiko darstellen, da Informationen möglicherweise offen gelegt werden. Angreifer können diese Informationen verwenden, um Ihre Organisation oder Ihre Partner anzugreifen.

Die folgenden Arten der automatischen Weiterleitung stehen in Microsoft 365 zur Verfügung:

- Benutzer können [Posteingangsregeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) so konfigurieren, dass Nachrichten automatisch an externe Absender weitergeleitet werden (absichtlich oder als Ergebnis eines kompromittierten Kontos).

- Administratoren können die [Post Fach Weiterleitung](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (auch bekannt als SMTP-Weiterleitung) so konfigurieren, dass Nachrichten automatisch an externe Empfänger weitergeleitet werden.

Sie können ausgehende Spamfilter-Richtlinien verwenden, um die automatische Weiterleitung an externe Empfänger zu steuern. Es stehen drei Einstellungen zur Verfügung:

- **Automatic**: automatische externe Weiterleitung wird blockiert. Die interne automatische Weiterleitung von Nachrichten funktioniert weiterhin. Dies ist die Standardeinstellung.
- **On**: automatische externe Weiterleitung ist zulässig und nicht eingeschränkt.
- **Off**: die automatische externe Weiterleitung ist deaktiviert und führt zu einem Unzustellbarkeitsbericht (auch als NDR-oder bounc-Nachricht bezeichnet) an den Absender.

Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter [Configure outbound Spam Filtering in EoP](configure-the-outbound-spam-policy.md).

**Hinweise**:

- Durch das Deaktivieren der automatischen Weiterleitung werden auch Posteingangsregeln deaktiviert, die Nachrichten an externe Adressen umleiten.

- Die automatische Weiterleitung von Nachrichten zwischen internen Benutzern ist von den Einstellungen in den Richtlinien für ausgehende Spamfilter nicht betroffen.

- Informationen zu Benutzern, die Nachrichten automatisch an externe Empfänger weiterleiten, finden Sie im [Bericht automatisch weitergeleitete Nachrichten](mfi-auto-forwarded-messages-report.md).

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Funktionsweise der Einstellungen für ausgehende Spamfilter Richtlinien für andere automatische e-Mail-Weiterleitungs Steuerelemente

Als Administrator haben Sie möglicherweise bereits andere Steuerelemente konfiguriert, um die automatische e-Mail-Weiterleitung zuzulassen oder zu blockieren. Zum Beispiel:

- [Remote Domänen](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) zum Zulassen oder Blockieren der automatischen e-Mail-Weiterleitung an einige oder alle externen Domänen.
- Bedingungen und Aktionen in Exchange [-Nachrichtenfluss Regeln](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch bekannt als Transportregeln) zum erkennen und Blockieren von automatisch weitergeleiteten Nachrichten an externe Empfänger.

Remote Domäneneinstellungen und Nachrichtenfluss Regeln sind unabhängig von den Einstellungen in den Richtlinien für ausgehende Spamfilter. Zum Beispiel:

- Sie können die automatische Weiterleitung für eine Remotedomäne zulassen, aber Sie blockieren die automatische Weiterleitung in ausgehenden Spamfilter Richtlinien. In diesem Beispiel werden automatisch weitergeleitete Nachrichten blockiert.
- Sie können die automatische Weiterleitung in ausgehenden Spamfilter Richtlinien zulassen, verwenden jedoch Nachrichtenfluss Regeln oder Remotedomäneneinstellungen, um automatisch weitergeleitete e-Mails zu blockieren. In diesem Beispiel werden die Nachrichtenfluss Regeln oder Remotedomäneneinstellungen automatisch weitergeleitete Nachrichten blockieren.

Durch diese Funktions Unabhängigkeit können Sie (beispielsweise) die automatische Weiterleitung in ausgehenden Spamfilter Richtlinien zulassen, aber Remotedomänen verwenden, um die externen Domänen zu steuern, an die Benutzer Nachrichten weiterleiten können.

## <a name="the-blocked-email-forwarding-message"></a>Die Nachricht für blockierte e-Mail-Weiterleitung

Wenn eine Nachricht als automatisch weitergeleitet erkannt wird und die Organisationsrichtlinie diese Aktivität *blockiert* , wird die Nachricht in einem Unzustellbarkeitsbericht an den Absender zurückgegeben, der die folgenden Informationen enthält:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
