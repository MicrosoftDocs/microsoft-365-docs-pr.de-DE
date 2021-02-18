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
ms.openlocfilehash: 77f666e5eeceee3f5b324e5b9b6fac721c10e410
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286866"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="23273-103">Steuern der automatischen externen E-Mail-Weiterleitung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="23273-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="23273-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="23273-104">**Applies to**</span></span>
- [<span data-ttu-id="23273-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="23273-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="23273-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="23273-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="23273-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23273-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="23273-108">Als Administrator haben Sie möglicherweise Unternehmensanforderungen, um automatisch weitergeleitete Nachrichten an externe Empfänger (Empfänger außerhalb Ihrer Organisation) einzuschränken oder zu steuern.</span><span class="sxs-lookup"><span data-stu-id="23273-108">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="23273-109">Die E-Mail-Weiterleitung kann hilfreich sein, aber auch ein Sicherheitsrisiko aufgrund der potenziellen Offenlegung von Informationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="23273-109">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="23273-110">Angreifer verwenden diese Informationen möglicherweise, um Ihre Organisation oder Ihre Partner angreift.</span><span class="sxs-lookup"><span data-stu-id="23273-110">Attackers might use this information to attack your organization or partners.</span></span>


<span data-ttu-id="23273-111">Die folgenden Arten der automatischen Weiterleitung sind in Microsoft 365 verfügbar:</span><span class="sxs-lookup"><span data-stu-id="23273-111">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="23273-112">Benutzer können [Posteingangsregeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) so konfigurieren, dass Nachrichten automatisch an externe Absender weitergeleitet werden (absichtlich oder als Folge eines gefährdeten Kontos).</span><span class="sxs-lookup"><span data-stu-id="23273-112">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="23273-113">Administratoren können die [Postfach weiterleitung](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (auch als SMTP-Weiterleitung _bezeichnet)_ so konfigurieren, dass Nachrichten automatisch an externe Empfänger weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="23273-113">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="23273-114">Der Administrator kann auswählen, ob Nachrichten einfach weitergeleitet oder Kopien der weitergeleiteten Nachrichten im Postfach gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="23273-114">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="23273-115">Sie können Filterrichtlinien für ausgehende Spamnachrichten verwenden, um die automatische Weiterleitung an externe Empfänger zu steuern.</span><span class="sxs-lookup"><span data-stu-id="23273-115">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="23273-116">Drei Einstellungen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="23273-116">Three settings are available:</span></span>

- <span data-ttu-id="23273-117">**Automatisch:** Die automatische externe Weiterleitung wird blockiert.</span><span class="sxs-lookup"><span data-stu-id="23273-117">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="23273-118">Die interne automatische Weiterleitung von Nachrichten funktioniert weiterhin.</span><span class="sxs-lookup"><span data-stu-id="23273-118">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="23273-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="23273-119">This is the default setting.</span></span>
- <span data-ttu-id="23273-120">**On:** Die automatische externe Weiterleitung ist zulässig und nicht eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="23273-120">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="23273-121">**Aus:** Die automatische externe Weiterleitung ist deaktiviert und führt zu einem Unzustellbarkeitsbericht (auch NDR oder Unzustellbarkeitsnachricht bezeichnet) an den Absender.</span><span class="sxs-lookup"><span data-stu-id="23273-121">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="23273-122">Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter "Konfigurieren der Filterung ausgehender [Spamnachrichten in EOP".](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="23273-122">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="23273-123">Durch das Deaktivieren der automatischen Weiterleitung werden alle Posteingangsregeln (Benutzer) oder Postfachumleitung (Administratoren) deaktiviert, die Nachrichten an externe Adressen umleiten.</span><span class="sxs-lookup"><span data-stu-id="23273-123">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="23273-124">Die automatische Weiterleitung von Nachrichten zwischen internen Benutzern ist von den Einstellungen in den Filterrichtlinien für ausgehende Spamnachrichten nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="23273-124">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="23273-125">Informationen zu Benutzern, die Nachrichten automatisch an externe Empfänger weiterleiten, finden Sie im Bericht über [automatisch weitergeleitete Nachrichten.](mfi-auto-forwarded-messages-report.md)</span><span class="sxs-lookup"><span data-stu-id="23273-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="23273-126">Funktionsweise der Richtlinieneinstellungen für den Filter für ausgehende Spamnachrichten mit anderen Steuerelementen für die automatische E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="23273-126">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="23273-127">Als Administrator haben Sie möglicherweise bereits andere Steuerelemente konfiguriert, um die automatische E-Mail-Weiterleitung zu erlauben oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="23273-127">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="23273-128">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="23273-128">For example:</span></span>

- <span data-ttu-id="23273-129">[Remotedomänen](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) zum Zulassen oder Blockieren der automatischen E-Mail-Weiterleitung an einige oder alle externen Domänen.</span><span class="sxs-lookup"><span data-stu-id="23273-129">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="23273-130">Bedingungen und Aktionen in [Exchange-Nachrichtenflussregeln](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch als Transportregeln bezeichnet), um automatisch weitergeleitete Nachrichten an externe Empfänger zu erkennen und zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="23273-130">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="23273-131">Remotedomäneneinstellungen und Nachrichtenflussregeln sind unabhängig von den Einstellungen in richtlinien für ausgehende Spamnachrichten.</span><span class="sxs-lookup"><span data-stu-id="23273-131">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="23273-132">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="23273-132">For example:</span></span>

- <span data-ttu-id="23273-133">Sie lassen die automatische Weiterleitung für eine Remotedomäne zu, aber Sie blockieren die automatische Weiterleitung in Filterrichtlinien für ausgehende Spamnachrichten.</span><span class="sxs-lookup"><span data-stu-id="23273-133">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="23273-134">In diesem Beispiel werden automatisch weitergeleitete Nachrichten blockiert.</span><span class="sxs-lookup"><span data-stu-id="23273-134">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="23273-135">Sie lassen die automatische Weiterleitung in Filterrichtlinien für ausgehende Spamnachrichten zu, verwenden jedoch Nachrichtenflussregeln oder Remotedomäneneinstellungen, um automatisch weitergeleitete E-Mails zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="23273-135">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="23273-136">In diesem Beispiel blockieren die Nachrichtenflussregeln oder Remotedomäneneinstellungen automatisch weitergeleitete Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="23273-136">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="23273-137">Mit dieser Featureunabhängigkeit können Sie (z. B.) die automatische Weiterleitung in Filterrichtlinien für ausgehende Spamnachrichten zulassen, aber Remotedomänen verwenden, um die externen Domänen zu steuern, an die Benutzer Nachrichten weiterleiten können.</span><span class="sxs-lookup"><span data-stu-id="23273-137">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="blocked-email-forwarding-messages"></a><span data-ttu-id="23273-138">Blockierte E-Mail-Weiterleitungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="23273-138">Blocked email forwarding messages</span></span>

<span data-ttu-id="23273-139">Wenn eine Nachricht als automatisch weitergeleitet [](configure-the-outbound-spam-policy.md) erkannt wird  und die Filterrichtlinie für ausgehende Spamnachrichten diese Aktivität blockiert, wird die Nachricht an den Absender in einem NDR mit den folgenden Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="23273-139">When a message is detected as automatically forwarded, and the [outbound spam filter](configure-the-outbound-spam-policy.md) policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
