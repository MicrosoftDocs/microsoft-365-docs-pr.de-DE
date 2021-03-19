---
title: Konfigurieren und Steuern der externen E-Mail-Weiterleitung, automatische Weiterleitung, 5.7.520 Zugriff verweigert, externe Weiterleitung deaktivieren, Ihr Administrator hat die externe Weiterleitung deaktiviert, ausgehende Antispamrichtlinie
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77f666e5eeceee3f5b324e5b9b6fac721c10e410
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286866"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Automatische externe E-Mail-Weiterleitung in Microsoft 365 steuern

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Als Administrator haben Sie möglicherweise Unternehmensanforderungen, um automatisch weitergeleitete Nachrichten an externe Empfänger (Empfänger außerhalb Ihrer Organisation) einzuschränken oder zu kontrollieren. Die E-Mail-Weiterleitung kann nützlich sein, aber auch ein Sicherheitsrisiko aufgrund der möglichen Veröffentlichung von Informationen darstellen. Angreifer könnten diese Informationen nutzen, um Ihr Unternehmen oder Ihre Partner anzugreifen.


Die folgenden Arten der automatischen Weiterleitung sind in Microsoft 365 verfügbar:

- Benutzer können [Posteingangsregeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) konfigurieren, um Nachrichten automatisch an externe Absender weiterzuleiten (absichtlich oder als Folge eines kompromittierten Kontos).

- Administratoren können eine [Postfach-Weiterleitung](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (auch _SMTP-Weiterleitung_ genannt) konfigurieren, um Nachrichten automatisch an externe Empfänger weiterzuleiten. Der Administrator kann wählen, ob er Nachrichten einfach weiterleiten oder Kopien der weitergeleiteten Nachrichten in dem Postfach behalten möchte.

Sie können ausgehende Spamfilterrichtlinien verwenden, um die automatische Weiterleitung an externe Empfänger zu steuern. Es stehen drei Einstellungen zur Verfügung:

- **Automatisch**: Die automatische externe Weiterleitung ist gesperrt. Die interne automatische Weiterleitung von Nachrichten funktioniert weiterhin. Dies ist die Standardeinstellung.
- **Ein**: Die automatische externe Weiterleitung ist erlaubt und nicht eingeschränkt.
- **Aus**: Die automatische externe Weiterleitung ist deaktiviert und führt zu einem Unzustellbarkeitsbericht (auch als NDR oder Unzustellbarkeitsnachricht bezeichnet) an den Absender.

Eine Anleitung zur Konfiguration dieser Einstellungen finden Sie unter [Konfigurieren der ausgehenden Spam-Filterung in EO](configure-the-outbound-spam-policy.md).

> [!NOTE]
>
> - Durch das Deaktivieren der automatischen Weiterleitung werden alle Posteingangsregeln (Benutzer) oder Postfachweiterleitungen (Admins) deaktiviert, die Nachrichten an externe Adressen umleiten.
>
> - Die automatische Weiterleitung von Nachrichten zwischen internen Benutzern ist nicht von den Einstellungen für ausgehende Spamfilterrichtlinien betroffen.
>
> - Sie können Informationen über Benutzer, die Nachrichten automatisch an externe Empfänger weiterleiten, im Bericht [Automatisch weitergeleitete Nachrichten](mfi-auto-forwarded-messages-report.md) sehen.

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Wie die Richtlinieneinstellungen des Filters für ausgehende Spamnachrichten mit anderen Steuerungen für die automatische E-Mail-Weiterleitung zusammenarbeiten

Als Administrator haben Sie möglicherweise bereits andere Steuerelemente konfiguriert, um die automatische E-Mail-Weiterleitung zuzulassen oder zu blockieren. Zum Beispiel:

- [Remotedomänen](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains), um die automatische E-Mail-Weiterleitung an einige oder alle externen Domänen zuzulassen oder zu blockieren.

- Bedingungen und Aktionen in Exchange [E-Mailflussregeln](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch Transportregeln genannt), um automatisch weitergeleitete Nachrichten an externe Empfänger zu erkennen und zu blockieren.

Die Einstellungen für die Remotedomäne und die E-Mailflussregeln sind unabhängig von den Einstellungen für ausgehende Spamfilterrichtlinien. Zum Beispiel:

- Sie erlauben die automatische Weiterleitung für eine Remotedomäne, blockieren aber die automatische Weiterleitung in den ausgehenden Spamfilterrichtlinien. In diesem Beispiel werden automatisch weitergeleitete Nachrichten blockiert.

- Sie erlauben die automatische Weiterleitung in den ausgehenden Spamfilterrichtlinien, aber Sie verwenden E-Mailflussregeln oder Einstellungen für Remotedomänen, um automatisch weitergeleitete E-Mails zu blockieren. In diesem Beispiel blockieren die E-Mailflussregeln oder die Remotedomäneneinstellungen automatisch weitergeleitete Nachrichten.

Mit dieser Funktionsunabhängigkeit können Sie (z. B.) die automatische Weiterleitung für ausgehende Spamfilterrichtlinien zulassen, aber die externen Domänen, an die Benutzer Nachrichten weiterleiten können, über Remotedomänen steuern.

## <a name="blocked-email-forwarding-messages"></a>Blockierte E-Mail-Weiterleitungsnachrichten

Wenn eine Nachricht als automatisch weitergeleitet erkannt wird und die [ausgehende Spamfilterrichtlinie](configure-the-outbound-spam-policy.md) diese Aktivität *blockiert*, wird die Nachricht in einem NDR an den Absender zurückgesendet, der die folgenden Informationen enthält:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
