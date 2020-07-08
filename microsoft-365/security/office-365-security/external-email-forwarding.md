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
ms.openlocfilehash: 88c3dae4f5a6786fe4eddea0d5e1c61dda837a87
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080113"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="55ff1-103">Konfigurieren der externen e-Mail-Weiterleitung in Office 365</span><span class="sxs-lookup"><span data-stu-id="55ff1-103">Configuring external email forwarding in Office 365</span></span>

<span data-ttu-id="55ff1-104">Die externe Weiterleitung wird von der *ausgehenden Anti-Spam-Richtlinie* gesteuert und auf der Grundlage der konfigurierten Einstellung auf Benutzer beschränkt.</span><span class="sxs-lookup"><span data-stu-id="55ff1-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="55ff1-105">Derzeit werden 3 Einstellungen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="55ff1-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="55ff1-106">**Automatic** – in diesem Modus ist das System für die Entscheidung zuständig, ob eine weitergeleitete Nachricht zulässig ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="55ff1-106">**Automatic** – In this mode the system is responsible for deciding if a forwarded message is allowed or not.</span></span>  <span data-ttu-id="55ff1-107">Dies ist der Standardmodus, und in diesem Modus wird das System die automatische externe Weiterleitung blockieren.</span><span class="sxs-lookup"><span data-stu-id="55ff1-107">This is the default mode and in this mode the system will block automatic external forwarding.</span></span>

- <span data-ttu-id="55ff1-108">**On** – automatische externe Weiterleitung ist zulässig und nicht eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="55ff1-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="55ff1-109">**Off** – die automatische externe Weiterleitung ist deaktiviert und führt zu einem Unzustellbarkeitsbericht (Non-Delivery Report, NDR) an den Endbenutzer.</span><span class="sxs-lookup"><span data-stu-id="55ff1-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="55ff1-110">Weitere Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Configure outbound Spam Filtering in EoP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) .</span><span class="sxs-lookup"><span data-stu-id="55ff1-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) for more information on how to configure these settings.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="55ff1-111">Steuern der externen e-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="55ff1-111">Controlling external email forwarding</span></span>

<span data-ttu-id="55ff1-112">Als Administrator einer Organisation haben Sie möglicherweise Unternehmens-Anforderungen zum einschränken oder Steuern, wer e-Mails mithilfe von Posteingangsregeln oder SMTP-Weiterleitung außerhalb der Organisation automatisch weiterleiten kann.</span><span class="sxs-lookup"><span data-stu-id="55ff1-112">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="55ff1-113">Die e-Mail-Weiterleitung kann ein nützliches Feature sein, kann aber auch durch die potenzielle Offenlegung von Informationen ein Risiko darstellen, auch durch Bereitstellen von Informationen für Angreifer, die zum Angriff auf die Organisation oder Ihre Partner genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="55ff1-113">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="55ff1-114">Office 365 lässt keine automatische externe Weiterleitung von Posteingangsregeln oder Mail Box-Konfiguration zu, die eine sichere Standardrichtlinie bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="55ff1-114">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="55ff1-115">Der Administrator kann diese Einstellungen jedoch für alle oder einige Benutzer in der Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="55ff1-115">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="55ff1-116">Das Weiterleiten von Nachrichten zwischen internen Benutzern ist von einer solchen Änderung nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="55ff1-116">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="55ff1-117">Das Deaktivieren der automatischen Weiterleitung an externe Adressen in Office 365 wird in Phasen mit Details, die über [Nachrichten Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) -Beiträge mitgeteilt werden, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="55ff1-117">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="55ff1-118">Um Administratoren bei der Vorbereitung auf diese Änderungen zu unterstützen, müssen Sie die Richtlinien vor der Zeit ändern, um sicherzustellen, dass Ihre Benutzer keine Unterbrechung finden.</span><span class="sxs-lookup"><span data-stu-id="55ff1-118">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="55ff1-119">Weitere Informationen zu Benutzern, die die automatische Weiterleitung (Posteingangsregeln oder SMTP-Weiterleitung) in Ihrer Organisation verwenden, finden Sie im [Bericht automatisch weitergeleitete Nachrichten](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="55ff1-119">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="55ff1-120">Die Nachricht für blockierte e-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="55ff1-120">The blocked email forwarding message</span></span>

<span data-ttu-id="55ff1-121">Wenn eine Nachricht als automatisch weitergeleitet erkannt wird und die Organisationsrichtlinie diese Aktivität *blockiert* , wird ein **Unzustellbarkeitsbericht (Non-Delivery Report, NDR)** zurück an den Endbenutzer generiert.</span><span class="sxs-lookup"><span data-stu-id="55ff1-121">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="55ff1-122">Der Bericht zeigt an, dass die Nachricht nicht zugestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="55ff1-122">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="55ff1-123">Der NDR weist das folgende Format auf:</span><span class="sxs-lookup"><span data-stu-id="55ff1-123">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
