---
title: Konfigurieren und Steuern der externen e-Mail-Weiterleitung, automatische Weiterleitung, 5.7.520 Zugriff verweigert, externe Weiterleitung deaktivieren, Ihr Administrator hat externe Weiterleitung deaktiviert, ausgehende Anti-Spam-Richtlinie
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 78ba5183667f4e5c6f713182969338f3ef2e7262
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600529"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="caac5-103">Konfigurieren der externen e-Mail-Weiterleitung in Office 365</span><span class="sxs-lookup"><span data-stu-id="caac5-103">Configuring external email forwarding in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="caac5-104">Die externe Weiterleitung wird von der *ausgehenden Anti-Spam-Richtlinie* gesteuert und auf der Grundlage der konfigurierten Einstellung auf Benutzer beschränkt.</span><span class="sxs-lookup"><span data-stu-id="caac5-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="caac5-105">Derzeit werden 3 Einstellungen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="caac5-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="caac5-106">**Automatic** – automatische externe Weiterleitung wird blockiert.</span><span class="sxs-lookup"><span data-stu-id="caac5-106">**Automatic** – Automatic external forwarding is blocked.</span></span> <span data-ttu-id="caac5-107">Die interne automatische Weiterleitung von Nachrichten funktioniert weiterhin.</span><span class="sxs-lookup"><span data-stu-id="caac5-107">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="caac5-108">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="caac5-108">This is the default setting.</span></span>

- <span data-ttu-id="caac5-109">**On** – automatische externe Weiterleitung ist zulässig und nicht eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="caac5-109">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="caac5-110">**Off** – die automatische externe Weiterleitung ist deaktiviert und führt zu einem Unzustellbarkeitsbericht (Non-Delivery Report, NDR) an den Endbenutzer.</span><span class="sxs-lookup"><span data-stu-id="caac5-110">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="caac5-111">Weitere Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Configure outbound Spam Filtering in EoP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) .</span><span class="sxs-lookup"><span data-stu-id="caac5-111">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) for more information on how to configure these settings.</span></span>

> [!NOTE]
> <span data-ttu-id="caac5-112">Durch das Deaktivieren der automatischen Weiterleitung werden auch Posteingangsregeln deaktiviert, die Nachrichten an externe Adressen umleiten.</span><span class="sxs-lookup"><span data-stu-id="caac5-112">Disabling automatic forwarding will also disable Inbox rules that redirect messages to external addresses.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="caac5-113">Steuern der externen e-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="caac5-113">Controlling external email forwarding</span></span>

<span data-ttu-id="caac5-114">Als Administrator einer Organisation haben Sie möglicherweise Unternehmens-Anforderungen zum einschränken oder Steuern, wer e-Mails mithilfe von Posteingangsregeln oder SMTP-Weiterleitung außerhalb der Organisation automatisch weiterleiten kann.</span><span class="sxs-lookup"><span data-stu-id="caac5-114">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="caac5-115">Die e-Mail-Weiterleitung kann ein nützliches Feature sein, kann aber auch durch die potenzielle Offenlegung von Informationen ein Risiko darstellen, auch durch Bereitstellen von Informationen für Angreifer, die zum Angriff auf die Organisation oder Ihre Partner genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="caac5-115">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="caac5-116">Office 365 lässt keine automatische externe Weiterleitung von Posteingangsregeln oder Mail Box-Konfiguration zu, die eine sichere Standardrichtlinie bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="caac5-116">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="caac5-117">Der Administrator kann diese Einstellungen jedoch für alle oder einige Benutzer in der Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="caac5-117">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="caac5-118">Das Weiterleiten von Nachrichten zwischen internen Benutzern ist von einer solchen Änderung nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="caac5-118">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="caac5-119">Das Deaktivieren der automatischen Weiterleitung an externe Adressen in Office 365 wird in Phasen mit Details, die über [Nachrichten Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) -Beiträge mitgeteilt werden, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="caac5-119">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="caac5-120">Um Administratoren bei der Vorbereitung auf diese Änderungen zu unterstützen, müssen Sie die Richtlinien vor der Zeit ändern, um sicherzustellen, dass Ihre Benutzer keine Unterbrechung finden.</span><span class="sxs-lookup"><span data-stu-id="caac5-120">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="caac5-121">Weitere Informationen zu Benutzern, die die automatische Weiterleitung (Posteingangsregeln oder SMTP-Weiterleitung) in Ihrer Organisation verwenden, finden Sie im [Bericht automatisch weitergeleitete Nachrichten](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="caac5-121">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span></span>

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a><span data-ttu-id="caac5-122">Wie funktioniert diese Richtlinie mit anderen automatischen Weiterleitungs Steuerelementen?</span><span class="sxs-lookup"><span data-stu-id="caac5-122">How does this policy work with other automatic forwarding controls</span></span>

<span data-ttu-id="caac5-123">Als Administrator verfügen Sie möglicherweise bereits über andere Arten von Steuerelementen, wie das Blockieren der automatischen Weiterleitung in [Remotedomänen](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) und die Verwendung einer Exchange-Transport Regel (ETR).</span><span class="sxs-lookup"><span data-stu-id="caac5-123">As an admin, you may already have other types of controls in place, such blocking automatic forwarding in [remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) and the use of an Exchange Transport Rule (ETR).</span></span> <span data-ttu-id="caac5-124">Beide Steuerelemente sind unabhängig von dieser Funktion, beispielsweise wenn Sie die automatische Weiterleitung für eine Remotedomäne zulassen, die automatische Weiterleitung jedoch über die ausgehende Spam Richtlinie blockieren, wird das Ergebnis sein, dass die automatisch weitergeleitete Nachricht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="caac5-124">Both of these controls are independent of this particular feature, for example if you allow automatic forwarding for a remote domain, but block automatic forwarding via the outbound spam policy the result will be that the automatically forwarded message is blocked.</span></span> <span data-ttu-id="caac5-125">Wenn Sie die automatische Weiterleitung in der ausgehenden Spam Richtlinie zulassen, Sie jedoch in einer ETR-oder Remotedomäne blockieren, wird die Nachricht durch eines dieser Steuerelemente blockiert.</span><span class="sxs-lookup"><span data-stu-id="caac5-125">Similarly if you allow automatic forwarding in the outbound spam policy but block it in an ETR or remote domain then the message will be blocked by either of these controls.</span></span> <span data-ttu-id="caac5-126">So können Sie beispielsweise die automatische Weiterleitung in der ausgehenden Spam Richtlinie zulassen und Remotedomänen verwenden, um die Domänen zu steuern, an die Benutzer Nachrichten automatisch weiterleiten können.</span><span class="sxs-lookup"><span data-stu-id="caac5-126">This allows you to, for example, allow automatic forwarding in the outbound spam policy and utilize remote domains to control the domains that users can automatic forward messages to.</span></span>


## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="caac5-127">Die Nachricht für blockierte e-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="caac5-127">The blocked email forwarding message</span></span>

<span data-ttu-id="caac5-128">Wenn eine Nachricht als automatisch weitergeleitet erkannt wird und die Organisationsrichtlinie diese Aktivität *blockiert* , wird ein **Unzustellbarkeitsbericht (Non-Delivery Report, NDR)** zurück an den Endbenutzer generiert.</span><span class="sxs-lookup"><span data-stu-id="caac5-128">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="caac5-129">Der Bericht zeigt an, dass die Nachricht nicht zugestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="caac5-129">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="caac5-130">Der NDR weist das folgende Format auf:</span><span class="sxs-lookup"><span data-stu-id="caac5-130">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
