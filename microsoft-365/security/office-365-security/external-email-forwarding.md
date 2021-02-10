---
title: Konfigurieren und Steuern der externen E-Mail-Weiterleitung, automatische Weiterleitung, 5.7.520 Zugriff verweigert, externe Weiterleitung deaktivieren, Ihr Administrator hat die externe Weiterleitung, ausgehende Antispamrichtlinie deaktiviert
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
ms.openlocfilehash: e578cadf6687e02c900299a75bdd00a9d6e5b2ee
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166147"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Steuern der automatischen externen E-Mail-Weiterleitung in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Als Administrator haben Sie möglicherweise Unternehmensanforderungen, um automatisch weitergeleitete Nachrichten an externe Empfänger (Empfänger außerhalb Ihrer Organisation) einzuschränken oder zu steuern. Die E-Mail-Weiterleitung kann hilfreich sein, aber auch ein Sicherheitsrisiko aufgrund der potenziellen Offenlegung von Informationen darstellen. Angreifer verwenden diese Informationen möglicherweise, um Ihre Organisation oder Ihre Partner angreift.


Die folgenden Arten der automatischen Weiterleitung sind in Microsoft 365 verfügbar:

- Benutzer können [Posteingangsregeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) so konfigurieren, dass Nachrichten automatisch an externe Absender weitergeleitet werden (absichtlich oder als Folge eines gefährdeten Kontos).

- Administratoren können die [Postfach weiterleitung](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (auch als SMTP-Weiterleitung _bezeichnet)_ so konfigurieren, dass Nachrichten automatisch an externe Empfänger weitergeleitet werden. Der Administrator kann auswählen, ob Nachrichten einfach weitergeleitet oder Kopien der weitergeleiteten Nachrichten im Postfach gespeichert werden sollen.

Sie können Filterrichtlinien für ausgehende Spamnachrichten verwenden, um die automatische Weiterleitung an externe Empfänger zu steuern. Drei Einstellungen sind verfügbar:

- **Automatisch:** Die automatische externe Weiterleitung wird blockiert. Die interne automatische Weiterleitung von Nachrichten funktioniert weiterhin. Dies ist die Standardeinstellung.
- **On:** Die automatische externe Weiterleitung ist zulässig und nicht eingeschränkt.
- **Aus:** Die automatische externe Weiterleitung ist deaktiviert und führt zu einem Unzustellbarkeitsbericht (auch NDR oder Unzustellbarkeitsnachricht bezeichnet) an den Absender.

Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter "Konfigurieren der Filterung ausgehender [Spamnachrichten in EOP".](configure-the-outbound-spam-policy.md)

> [!NOTE]
>
> - Durch das Deaktivieren der automatischen Weiterleitung werden alle Posteingangsregeln (Benutzer) oder Postfachumleitung (Administratoren) deaktiviert, die Nachrichten an externe Adressen umleiten.
>
> - Die automatische Weiterleitung von Nachrichten zwischen internen Benutzern ist von den Einstellungen in den Filterrichtlinien für ausgehende Spamnachrichten nicht betroffen.
>
> - Informationen zu Benutzern, die Nachrichten automatisch an externe Empfänger weiterleiten, finden Sie im Bericht über [automatisch weitergeleitete Nachrichten.](mfi-auto-forwarded-messages-report.md)

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Funktionsweise der Richtlinieneinstellungen für den Filter für ausgehende Spamnachrichten mit anderen Steuerelementen für die automatische E-Mail-Weiterleitung

Als Administrator haben Sie möglicherweise bereits andere Steuerelemente konfiguriert, um die automatische E-Mail-Weiterleitung zu erlauben oder zu blockieren. Zum Beispiel:

- [Remotedomänen](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) zum Zulassen oder Blockieren der automatischen E-Mail-Weiterleitung an einige oder alle externen Domänen.

- Bedingungen und Aktionen in [Exchange-Nachrichtenflussregeln](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch als Transportregeln bezeichnet), um automatisch weitergeleitete Nachrichten an externe Empfänger zu erkennen und zu blockieren.

Remotedomäneneinstellungen und Nachrichtenflussregeln sind unabhängig von den Einstellungen in richtlinien für ausgehende Spamnachrichten. Zum Beispiel:

- Sie lassen die automatische Weiterleitung für eine Remotedomäne zu, aber Sie blockieren die automatische Weiterleitung in Filterrichtlinien für ausgehende Spamnachrichten. In diesem Beispiel werden automatisch weitergeleitete Nachrichten blockiert.

- Sie lassen die automatische Weiterleitung in Filterrichtlinien für ausgehende Spamnachrichten zu, verwenden jedoch Nachrichtenflussregeln oder Remotedomäneneinstellungen, um automatisch weitergeleitete E-Mails zu blockieren. In diesem Beispiel blockieren die Nachrichtenflussregeln oder Remotedomäneneinstellungen automatisch weitergeleitete Nachrichten.

Mit dieser Featureunabhängigkeit können Sie (z. B.) die automatische Weiterleitung in Filterrichtlinien für ausgehende Spamnachrichten zulassen, aber Remotedomänen verwenden, um die externen Domänen zu steuern, an die Benutzer Nachrichten weiterleiten können.

## <a name="the-blocked-email-forwarding-message"></a>Die blockierte E-Mail-Weiterleitungsnachricht

Wenn eine Nachricht als automatisch weitergeleitet erkannt  wird und die Organisationsrichtlinie diese Aktivität blockiert, wird die Nachricht an den Absender in einem NDR mit den folgenden Informationen zurückgegeben:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
