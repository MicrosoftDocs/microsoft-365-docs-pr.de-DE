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
ms.openlocfilehash: dff2ea4e144f8f8fcc0f42732141e110effe7e9e
ms.sourcegitcommit: 45c0afcf958069c5c1b31f9b6c762d8dd806e1e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48774093"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="f5614-103">Steuern der automatischen externen e-Mail-Weiterleitung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f5614-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f5614-104">Als Administrator haben Sie möglicherweise Unternehmens Anforderungen zum einschränken oder Steuern der automatischen Weiterleitung von Nachrichten an externe Empfänger (Empfänger außerhalb Ihrer Organisation).</span><span class="sxs-lookup"><span data-stu-id="f5614-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="f5614-105">Die e-Mail-Weiterleitung kann nützlich sein, kann aber auch ein Sicherheitsrisiko darstellen, da Informationen möglicherweise offen gelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f5614-105">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="f5614-106">Angreifer können diese Informationen verwenden, um Ihre Organisation oder Ihre Partner anzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f5614-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="f5614-107">Die folgenden Arten der automatischen Weiterleitung stehen in Microsoft 365 zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f5614-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="f5614-108">Benutzer können [Posteingangsregeln](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) so konfigurieren, dass Nachrichten automatisch an externe Absender weitergeleitet werden (absichtlich oder als Ergebnis eines kompromittierten Kontos).</span><span class="sxs-lookup"><span data-stu-id="f5614-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="f5614-109">Administratoren können die [Post Fach Weiterleitung](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (auch bekannt als SMTP-Weiterleitung) so konfigurieren, dass Nachrichten automatisch an externe Empfänger weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="f5614-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as SMTP forwarding) to automatically forward messages to external recipients.</span></span>

<span data-ttu-id="f5614-110">Sie können ausgehende Spamfilter-Richtlinien verwenden, um die automatische Weiterleitung an externe Empfänger zu steuern.</span><span class="sxs-lookup"><span data-stu-id="f5614-110">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="f5614-111">Es stehen drei Einstellungen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f5614-111">Three settings are available:</span></span>

- <span data-ttu-id="f5614-112">**Automatic** : automatische externe Weiterleitung wird blockiert.</span><span class="sxs-lookup"><span data-stu-id="f5614-112">**Automatic** : Automatic external forwarding is blocked.</span></span> <span data-ttu-id="f5614-113">Die interne automatische Weiterleitung von Nachrichten funktioniert weiterhin.</span><span class="sxs-lookup"><span data-stu-id="f5614-113">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="f5614-114">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="f5614-114">This is the default setting.</span></span>

- <span data-ttu-id="f5614-115">**On** : automatische externe Weiterleitung ist zulässig und nicht eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="f5614-115">**On** : Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="f5614-116">**Off** : die automatische externe Weiterleitung ist deaktiviert und führt zu einem Unzustellbarkeitsbericht (auch als NDR-oder bounc-Nachricht bezeichnet) an den Absender.</span><span class="sxs-lookup"><span data-stu-id="f5614-116">**Off** : Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="f5614-117">Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter [Configure outbound Spam Filtering in EoP](configure-the-outbound-spam-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f5614-117">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="f5614-118">Durch das Deaktivieren der automatischen Weiterleitung werden auch Posteingangsregeln deaktiviert, die Nachrichten an externe Adressen umleiten.</span><span class="sxs-lookup"><span data-stu-id="f5614-118">Disabling automatic forwarding will also disable Inbox rules that redirect messages to external addresses.</span></span>
> 
>   <span data-ttu-id="f5614-119">Office 365 erlaubt keine automatische externe Weiterleitung durch Posteingangsregeln oder Postfachkonfiguration, die eine sichere Standardrichtlinie bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f5614-119">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mailbox configuration, which provides a secure default policy.</span></span> <span data-ttu-id="f5614-120">Der Administrator kann diese Einstellungen jedoch für alle oder einige Benutzer in der Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="f5614-120">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="f5614-121">Erstellen Sie [ausgehende Spam Richtlinien](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true#use-the-security--compliance-center-to-create-outbound-spam-policies) , und ändern Sie den Abschnitt Automatische Weiterleitung, um die automatische e-Mail-Weiterleitung von Benutzern an externe Absender zu steuern.</span><span class="sxs-lookup"><span data-stu-id="f5614-121">Create [outbound spam policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true#use-the-security--compliance-center-to-create-outbound-spam-policies) and modify the automatic forwarding section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="f5614-122">Dies kann später auf die internen Absender angewendet werden, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f5614-122">This can be later applied to the internal senders that the policy applies to.</span></span> <span data-ttu-id="f5614-123">Das Weiterleiten von Nachrichten zwischen internen Benutzern ist von einer solchen Änderung nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="f5614-123">Forwarding messages between internal users isn't affected by such a modification.</span></span>
> 
> - <span data-ttu-id="f5614-124">Informationen zu Benutzern, die Nachrichten automatisch an externe Empfänger weiterleiten, finden Sie im [Bericht automatisch weitergeleitete Nachrichten](mfi-auto-forwarded-messages-report.md).</span><span class="sxs-lookup"><span data-stu-id="f5614-124">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="f5614-125">Funktionsweise der Einstellungen für ausgehende Spamfilter Richtlinien für andere automatische e-Mail-Weiterleitungs Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="f5614-125">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="f5614-126">Als Administrator haben Sie möglicherweise bereits andere Steuerelemente konfiguriert, um die automatische e-Mail-Weiterleitung zuzulassen oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="f5614-126">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="f5614-127">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f5614-127">For example:</span></span>

- <span data-ttu-id="f5614-128">[Remote Domänen](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) zum Zulassen oder Blockieren der automatischen e-Mail-Weiterleitung an einige oder alle externen Domänen.</span><span class="sxs-lookup"><span data-stu-id="f5614-128">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="f5614-129">Bedingungen und Aktionen in Exchange [-Nachrichtenfluss Regeln](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (auch bekannt als Transportregeln) zum erkennen und Blockieren von automatisch weitergeleiteten Nachrichten an externe Empfänger.</span><span class="sxs-lookup"><span data-stu-id="f5614-129">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="f5614-130">Remote Domäneneinstellungen und Nachrichtenfluss Regeln sind unabhängig von den Einstellungen in den Richtlinien für ausgehende Spamfilter.</span><span class="sxs-lookup"><span data-stu-id="f5614-130">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="f5614-131">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f5614-131">For example:</span></span>

- <span data-ttu-id="f5614-132">Sie können die automatische Weiterleitung für eine Remotedomäne zulassen, aber Sie blockieren die automatische Weiterleitung in ausgehenden Spamfilter Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="f5614-132">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="f5614-133">In diesem Beispiel werden automatisch weitergeleitete Nachrichten blockiert.</span><span class="sxs-lookup"><span data-stu-id="f5614-133">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="f5614-134">Sie können die automatische Weiterleitung in ausgehenden Spamfilter Richtlinien zulassen, verwenden jedoch Nachrichtenfluss Regeln oder Remotedomäneneinstellungen, um automatisch weitergeleitete e-Mails zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="f5614-134">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="f5614-135">In diesem Beispiel werden die Nachrichtenfluss Regeln oder Remotedomäneneinstellungen automatisch weitergeleitete Nachrichten blockieren.</span><span class="sxs-lookup"><span data-stu-id="f5614-135">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="f5614-136">Durch diese Funktions Unabhängigkeit können Sie (beispielsweise) die automatische Weiterleitung in ausgehenden Spamfilter Richtlinien zulassen, aber Remotedomänen verwenden, um die externen Domänen zu steuern, an die Benutzer Nachrichten weiterleiten können.</span><span class="sxs-lookup"><span data-stu-id="f5614-136">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="f5614-137">Die Nachricht für blockierte e-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="f5614-137">The blocked email forwarding message</span></span>

<span data-ttu-id="f5614-138">Wenn eine Nachricht als automatisch weitergeleitet erkannt wird und die Organisationsrichtlinie diese Aktivität *blockiert* , wird die Nachricht in einem Unzustellbarkeitsbericht an den Absender zurückgegeben, der die folgenden Informationen enthält:</span><span class="sxs-lookup"><span data-stu-id="f5614-138">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
