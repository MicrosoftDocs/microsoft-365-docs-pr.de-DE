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
ms.openlocfilehash: 76cd560c3b97bb67d25d2e4ff2c219669c3d4f0d
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658881"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="524d5-103">Steuern der automatischen externen e-Mail-Weiterleitung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="524d5-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="524d5-104">Als Administrator haben Sie möglicherweise Unternehmens Anforderungen zum einschränken oder Steuern der automatischen Weiterleitung von Nachrichten an externe Empfänger (Empfänger außerhalb Ihrer Organisation).</span><span class="sxs-lookup"><span data-stu-id="524d5-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="524d5-105">Die e-Mail-Weiterleitung kann nützlich sein, kann aber auch ein Sicherheitsrisiko darstellen, da Informationen möglicherweise offen gelegt werden.</span><span class="sxs-lookup"><span data-stu-id="524d5-105">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="524d5-106">Angreifer können diese Informationen verwenden, um Ihre Organisation oder Ihre Partner anzugreifen.</span><span class="sxs-lookup"><span data-stu-id="524d5-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="524d5-107">Die folgenden Arten der automatischen Weiterleitung stehen in Microsoft 365 zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="524d5-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="524d5-108">Benutzer können [Posteingangsregeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) so konfigurieren, dass Nachrichten automatisch an externe Absender weitergeleitet werden (absichtlich oder als Ergebnis eines kompromittierten Kontos).</span><span class="sxs-lookup"><span data-stu-id="524d5-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="524d5-109">Administratoren können die [Post Fach Weiterleitung](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (auch bekannt als _SMTP-Weiterleitung_) so konfigurieren, dass Nachrichten automatisch an externe Empfänger weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="524d5-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="524d5-110">Der Administrator kann auswählen, ob Nachrichten einfach weitergeleitet oder Kopien von weitergeleiteten Nachrichten im Postfach aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="524d5-110">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="524d5-111">Sie können ausgehende Spamfilter-Richtlinien verwenden, um die automatische Weiterleitung an externe Empfänger zu steuern.</span><span class="sxs-lookup"><span data-stu-id="524d5-111">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="524d5-112">Es stehen drei Einstellungen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="524d5-112">Three settings are available:</span></span>

- <span data-ttu-id="524d5-113">**Automatic**: automatische externe Weiterleitung wird blockiert.</span><span class="sxs-lookup"><span data-stu-id="524d5-113">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="524d5-114">Die interne automatische Weiterleitung von Nachrichten funktioniert weiterhin.</span><span class="sxs-lookup"><span data-stu-id="524d5-114">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="524d5-115">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="524d5-115">This is the default setting.</span></span>
- <span data-ttu-id="524d5-116">**On**: automatische externe Weiterleitung ist zulässig und nicht eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="524d5-116">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="524d5-117">**Off**: die automatische externe Weiterleitung ist deaktiviert und führt zu einem Unzustellbarkeitsbericht (auch als NDR-oder bounc-Nachricht bezeichnet) an den Absender.</span><span class="sxs-lookup"><span data-stu-id="524d5-117">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="524d5-118">Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter [Configure outbound Spam Filtering in EoP](configure-the-outbound-spam-policy.md).</span><span class="sxs-lookup"><span data-stu-id="524d5-118">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="524d5-119">Durch Deaktivieren der automatischen Weiterleitung werden alle Posteingangsregeln (Benutzer) oder Post Fach Weiterleitung (Administratoren) deaktiviert, die Nachrichten an externe Adressen umleiten.</span><span class="sxs-lookup"><span data-stu-id="524d5-119">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="524d5-120">Die automatische Weiterleitung von Nachrichten zwischen internen Benutzern ist von den Einstellungen in den Richtlinien für ausgehende Spamfilter nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="524d5-120">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="524d5-121">Informationen zu Benutzern, die Nachrichten automatisch an externe Empfänger weiterleiten, finden Sie im [Bericht automatisch weitergeleitete Nachrichten](mfi-auto-forwarded-messages-report.md).</span><span class="sxs-lookup"><span data-stu-id="524d5-121">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="524d5-122">Funktionsweise der Einstellungen für ausgehende Spamfilter Richtlinien für andere automatische e-Mail-Weiterleitungs Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="524d5-122">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="524d5-123">Als Administrator haben Sie möglicherweise bereits andere Steuerelemente konfiguriert, um die automatische e-Mail-Weiterleitung zuzulassen oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="524d5-123">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="524d5-124">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="524d5-124">For example:</span></span>

- <span data-ttu-id="524d5-125">[Remote Domänen](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) zum Zulassen oder Blockieren der automatischen e-Mail-Weiterleitung an einige oder alle externen Domänen.</span><span class="sxs-lookup"><span data-stu-id="524d5-125">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="524d5-126">Bedingungen und Aktionen in Exchange [-Nachrichtenfluss Regeln](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch bekannt als Transportregeln) zum erkennen und Blockieren von automatisch weitergeleiteten Nachrichten an externe Empfänger.</span><span class="sxs-lookup"><span data-stu-id="524d5-126">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="524d5-127">Remote Domäneneinstellungen und Nachrichtenfluss Regeln sind unabhängig von den Einstellungen in den Richtlinien für ausgehende Spamfilter.</span><span class="sxs-lookup"><span data-stu-id="524d5-127">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="524d5-128">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="524d5-128">For example:</span></span>

- <span data-ttu-id="524d5-129">Sie können die automatische Weiterleitung für eine Remotedomäne zulassen, aber Sie blockieren die automatische Weiterleitung in ausgehenden Spamfilter Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="524d5-129">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="524d5-130">In diesem Beispiel werden automatisch weitergeleitete Nachrichten blockiert.</span><span class="sxs-lookup"><span data-stu-id="524d5-130">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="524d5-131">Sie können die automatische Weiterleitung in ausgehenden Spamfilter Richtlinien zulassen, verwenden jedoch Nachrichtenfluss Regeln oder Remotedomäneneinstellungen, um automatisch weitergeleitete e-Mails zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="524d5-131">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="524d5-132">In diesem Beispiel werden die Nachrichtenfluss Regeln oder Remotedomäneneinstellungen automatisch weitergeleitete Nachrichten blockieren.</span><span class="sxs-lookup"><span data-stu-id="524d5-132">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="524d5-133">Durch diese Funktions Unabhängigkeit können Sie (beispielsweise) die automatische Weiterleitung in ausgehenden Spamfilter Richtlinien zulassen, aber Remotedomänen verwenden, um die externen Domänen zu steuern, an die Benutzer Nachrichten weiterleiten können.</span><span class="sxs-lookup"><span data-stu-id="524d5-133">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="524d5-134">Die Nachricht für blockierte e-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="524d5-134">The blocked email forwarding message</span></span>

<span data-ttu-id="524d5-135">Wenn eine Nachricht als automatisch weitergeleitet erkannt wird und die Organisationsrichtlinie diese Aktivität *blockiert* , wird die Nachricht in einem Unzustellbarkeitsbericht an den Absender zurückgegeben, der die folgenden Informationen enthält:</span><span class="sxs-lookup"><span data-stu-id="524d5-135">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
