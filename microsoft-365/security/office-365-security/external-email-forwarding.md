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
ms.openlocfilehash: 0f42da077ca84341824fad01fcb23eae976336a1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204204"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="8e03d-103">Automatische externe E-Mail-Weiterleitung in Microsoft 365 steuern</span><span class="sxs-lookup"><span data-stu-id="8e03d-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8e03d-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="8e03d-104">**Applies to**</span></span>
- [<span data-ttu-id="8e03d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8e03d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8e03d-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="8e03d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8e03d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e03d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8e03d-108">Als Administrator haben Sie möglicherweise Unternehmensanforderungen, um automatisch weitergeleitete Nachrichten an externe Empfänger (Empfänger außerhalb Ihrer Organisation) einzuschränken oder zu kontrollieren.</span><span class="sxs-lookup"><span data-stu-id="8e03d-108">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="8e03d-109">Die E-Mail-Weiterleitung kann nützlich sein, aber auch ein Sicherheitsrisiko aufgrund der möglichen Veröffentlichung von Informationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="8e03d-109">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="8e03d-110">Angreifer könnten diese Informationen nutzen, um Ihr Unternehmen oder Ihre Partner anzugreifen.</span><span class="sxs-lookup"><span data-stu-id="8e03d-110">Attackers might use this information to attack your organization or partners.</span></span>


<span data-ttu-id="8e03d-111">Die folgenden Arten der automatischen Weiterleitung sind in Microsoft 365 verfügbar:</span><span class="sxs-lookup"><span data-stu-id="8e03d-111">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="8e03d-112">Benutzer können [Posteingangsregeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) konfigurieren, um Nachrichten automatisch an externe Absender weiterzuleiten (absichtlich oder als Folge eines kompromittierten Kontos).</span><span class="sxs-lookup"><span data-stu-id="8e03d-112">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="8e03d-113">Administratoren können eine [Postfach-Weiterleitung](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (auch _SMTP-Weiterleitung_ genannt) konfigurieren, um Nachrichten automatisch an externe Empfänger weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="8e03d-113">Admins can configure [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="8e03d-114">Der Administrator kann wählen, ob er Nachrichten einfach weiterleiten oder Kopien der weitergeleiteten Nachrichten in dem Postfach behalten möchte.</span><span class="sxs-lookup"><span data-stu-id="8e03d-114">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="8e03d-115">Sie können ausgehende Spamfilterrichtlinien verwenden, um die automatische Weiterleitung an externe Empfänger zu steuern.</span><span class="sxs-lookup"><span data-stu-id="8e03d-115">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="8e03d-116">Es stehen drei Einstellungen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="8e03d-116">Three settings are available:</span></span>

- <span data-ttu-id="8e03d-117">**Automatisch**: Die automatische externe Weiterleitung ist gesperrt.</span><span class="sxs-lookup"><span data-stu-id="8e03d-117">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="8e03d-118">Die interne automatische Weiterleitung von Nachrichten funktioniert weiterhin.</span><span class="sxs-lookup"><span data-stu-id="8e03d-118">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="8e03d-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="8e03d-119">This is the default setting.</span></span>
- <span data-ttu-id="8e03d-120">**Ein**: Die automatische externe Weiterleitung ist erlaubt und nicht eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="8e03d-120">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="8e03d-121">**Aus**: Die automatische externe Weiterleitung ist deaktiviert und führt zu einem Unzustellbarkeitsbericht (auch als NDR oder Unzustellbarkeitsnachricht bezeichnet) an den Absender.</span><span class="sxs-lookup"><span data-stu-id="8e03d-121">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="8e03d-122">Eine Anleitung zur Konfiguration dieser Einstellungen finden Sie unter [Konfigurieren der ausgehenden Spam-Filterung in EO](configure-the-outbound-spam-policy.md).</span><span class="sxs-lookup"><span data-stu-id="8e03d-122">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="8e03d-123">Durch das Deaktivieren der automatischen Weiterleitung werden alle Posteingangsregeln (Benutzer) oder Postfachweiterleitungen (Admins) deaktiviert, die Nachrichten an externe Adressen umleiten.</span><span class="sxs-lookup"><span data-stu-id="8e03d-123">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="8e03d-124">Die automatische Weiterleitung von Nachrichten zwischen internen Benutzern ist nicht von den Einstellungen für ausgehende Spamfilterrichtlinien betroffen.</span><span class="sxs-lookup"><span data-stu-id="8e03d-124">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="8e03d-125">Sie können Informationen über Benutzer, die Nachrichten automatisch an externe Empfänger weiterleiten, im Bericht [Automatisch weitergeleitete Nachrichten](mfi-auto-forwarded-messages-report.md) sehen.</span><span class="sxs-lookup"><span data-stu-id="8e03d-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="8e03d-126">Wie die Richtlinieneinstellungen des Filters für ausgehende Spamnachrichten mit anderen Steuerungen für die automatische E-Mail-Weiterleitung zusammenarbeiten</span><span class="sxs-lookup"><span data-stu-id="8e03d-126">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="8e03d-127">Als Administrator haben Sie möglicherweise bereits andere Steuerelemente konfiguriert, um die automatische E-Mail-Weiterleitung zuzulassen oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="8e03d-127">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="8e03d-128">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8e03d-128">For example:</span></span>

- <span data-ttu-id="8e03d-129">[Remotedomänen](/exchange/mail-flow-best-practices/remote-domains/remote-domains), um die automatische E-Mail-Weiterleitung an einige oder alle externen Domänen zuzulassen oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="8e03d-129">[Remote domains](/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="8e03d-130">Bedingungen und Aktionen in Exchange [E-Mailflussregeln](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch Transportregeln genannt), um automatisch weitergeleitete Nachrichten an externe Empfänger zu erkennen und zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="8e03d-130">Conditions and actions in Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="8e03d-131">Die Einstellungen für die Remotedomäne und die E-Mailflussregeln sind unabhängig von den Einstellungen für ausgehende Spamfilterrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="8e03d-131">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="8e03d-132">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8e03d-132">For example:</span></span>

- <span data-ttu-id="8e03d-133">Sie erlauben die automatische Weiterleitung für eine Remotedomäne, blockieren aber die automatische Weiterleitung in den ausgehenden Spamfilterrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="8e03d-133">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="8e03d-134">In diesem Beispiel werden automatisch weitergeleitete Nachrichten blockiert.</span><span class="sxs-lookup"><span data-stu-id="8e03d-134">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="8e03d-135">Sie erlauben die automatische Weiterleitung in den ausgehenden Spamfilterrichtlinien, aber Sie verwenden E-Mailflussregeln oder Einstellungen für Remotedomänen, um automatisch weitergeleitete E-Mails zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="8e03d-135">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="8e03d-136">In diesem Beispiel blockieren die E-Mailflussregeln oder die Remotedomäneneinstellungen automatisch weitergeleitete Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="8e03d-136">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="8e03d-137">Mit dieser Funktionsunabhängigkeit können Sie (z. B.) die automatische Weiterleitung für ausgehende Spamfilterrichtlinien zulassen, aber die externen Domänen, an die Benutzer Nachrichten weiterleiten können, über Remotedomänen steuern.</span><span class="sxs-lookup"><span data-stu-id="8e03d-137">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="blocked-email-forwarding-messages"></a><span data-ttu-id="8e03d-138">Blockierte E-Mail-Weiterleitungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="8e03d-138">Blocked email forwarding messages</span></span>

<span data-ttu-id="8e03d-139">Wenn eine Nachricht als automatisch weitergeleitet erkannt wird und die [ausgehende Spamfilterrichtlinie](configure-the-outbound-spam-policy.md) diese Aktivität *blockiert*, wird die Nachricht in einem NDR an den Absender zurückgesendet, der die folgenden Informationen enthält:</span><span class="sxs-lookup"><span data-stu-id="8e03d-139">When a message is detected as automatically forwarded, and the [outbound spam filter](configure-the-outbound-spam-policy.md) policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`