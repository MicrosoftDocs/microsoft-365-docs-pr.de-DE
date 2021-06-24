---
title: Nachrichtenablaufverfolgung im Microsoft 365 Defender-Portal
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Administratoren können den Link zur Nachrichtenablaufverfolgung im Microsoft 365 Defender-Portal verwenden, um herauszufinden, was mit Nachrichten passiert ist.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108127"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="afe96-103">Nachrichtenablaufverfolgung im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="afe96-103">Message trace in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="afe96-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="afe96-104">**Applies to**</span></span>
- [<span data-ttu-id="afe96-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="afe96-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="afe96-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="afe96-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="afe96-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="afe96-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="afe96-108">Die Nachrichtenablaufverfolgung im Microsoft 365 Defender Portal folgt E-Mail-Nachrichten, während sie ihre Exchange Online Organisation durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="afe96-108">Message trace in the Microsoft 365 Defender portal follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="afe96-109">Sie können ermitteln, ob eine Nachricht empfangen, abgelehnt, zurückgestellt oder vom Dienst übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="afe96-109">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="afe96-110">Außerdem werden die Aktionen der Nachricht gezeigt, bevor diese ihren finalen Status erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="afe96-110">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="afe96-111">Sie können die Informationen aus der Nachrichtenablaufverfolgung verwenden, um Benutzerfragen zu den Nachrichten effizient zu beantworten, Probleme mit dem Nachrichtenfluss zu beheben und Richtlinienänderungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="afe96-111">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
> <span data-ttu-id="afe96-112">Die Nachrichtenablaufverfolgung im Microsoft 365 Defender-Portal ist nur eine Übergabe an die Nachrichtenablaufverfolgung im Exchange Admin Center.</span><span class="sxs-lookup"><span data-stu-id="afe96-112">Message trace in the Microsoft 365 Defender portal is just a pass through to Message trace in the Exchange admin center.</span></span> <span data-ttu-id="afe96-113">Weitere Informationen finden Sie unter [Nachrichtenablaufverfolgung im modernen Exchange Admin Center.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="afe96-113">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="afe96-114">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="afe96-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="afe96-115">Sie müssen Mitglied der **Rollengruppen "Organisationsverwaltung",** **"Complianceverwaltung"** oder **"Helpdesk"** in **Exchange Online** sein, um die Nachrichtenablaufverfolgung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="afe96-115">You need to be a member of the **Organization Management**, **Compliance Management** or **Help Desk** role groups in **Exchange Online** to use message trace.</span></span> <span data-ttu-id="afe96-116">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="afe96-116">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="afe96-117">**Hinweis:** Die Mitgliedschaft in der entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center gewährt Benutzern die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="afe96-117">**Notes**: Membership in the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="afe96-118">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="afe96-118">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="afe96-119">Die maximale Anzahl von Nachrichten, die in den Ergebnissen einer Nachrichtenablaufverfolgung angezeigt werden, hängt vom ausgewählten Berichtstyp ab (Details finden Sie im Abschnitt ["Berichtstyp auswählen").](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type)</span><span class="sxs-lookup"><span data-stu-id="afe96-119">The maximum number of messages that are displayed in the results of a message trace depends on the report type you selected (see the [Choose report type](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) section for details).</span></span> <span data-ttu-id="afe96-120">Das Cmdlet ["Get-HistoricalSearch"](/powershell/module/exchange/get-historicalsearch) in Exchange Online PowerShell oder der eigenständigen EOP-PowerShell gibt alle Nachrichten in den Ergebnissen zurück.</span><span class="sxs-lookup"><span data-stu-id="afe96-120">The [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="afe96-121">Öffnen der Nachrichtenablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="afe96-121">Open message trace</span></span>

<span data-ttu-id="afe96-122">Wechseln Sie im Microsoft 365 Defender Portal ( <https://security.microsoft.com> ) zu **E-Mail & Zusammenarbeit** Exchange \> **Nachrichtenablaufverfolgung.**</span><span class="sxs-lookup"><span data-stu-id="afe96-122">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration** \> **Exchange message trace**.</span></span> <span data-ttu-id="afe96-123">Oder verwenden Sie , um direkt zur Nachrichtenablaufverfolgungsseite zu <https://admin.exchange.microsoft.com/#/messagetrace> wechseln.</span><span class="sxs-lookup"><span data-stu-id="afe96-123">Or, to go directly to the message trace page, use <https://admin.exchange.microsoft.com/#/messagetrace>.</span></span>

<span data-ttu-id="afe96-124">An diesem Punkt wird die Nachrichtenablaufverfolgung im EAC geöffnet.</span><span class="sxs-lookup"><span data-stu-id="afe96-124">At this point, message trace in the EAC opens.</span></span> <span data-ttu-id="afe96-125">Weitere Informationen finden Sie unter [Nachrichtenablaufverfolgung im modernen Exchange Admin Center.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="afe96-125">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>
