---
title: Nachrichtenfluss-Einblicke im Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Administratoren können sich über das Nachrichtenfluss-Dashboard im Security & Compliance Center informieren, einschließlich Einblicke, Berichte und Widgets.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e3139fa6a139c7fa159c2e5e5daa3879322f4bf0
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552674"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="ba618-103">Nachrichtenfluss-Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ba618-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="ba618-104">Administratoren können das Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um Trends, Einblicke zu ermitteln und Aktionen zum Beheben von Problemen im Zusammenhang mit dem Nachrichtenfluss in Ihrer Organisation durchführen.</span><span class="sxs-lookup"><span data-stu-id="ba618-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their organization.</span></span>

<span data-ttu-id="ba618-105">Die im e-Mail-Fluss-Dashboard verfügbaren Einblicke, Berichte und Widgets sind:</span><span class="sxs-lookup"><span data-stu-id="ba618-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="ba618-106">Nachrichtenfluss-Bericht</span><span class="sxs-lookup"><span data-stu-id="ba618-106">Mail flow map report</span></span>](mfi-mail-flow-map-report.md)

- [<span data-ttu-id="ba618-107">Einblick in den Domänen Nachrichtenflussstatus</span><span class="sxs-lookup"><span data-stu-id="ba618-107">Domain mail flow status insight</span></span>](mfi-domain-mail-flow-status-insight.md)

- [<span data-ttu-id="ba618-108">SMTP-Auth-Clientbericht</span><span class="sxs-lookup"><span data-stu-id="ba618-108">SMTP Auth clients report</span></span>](mfi-smtp-auth-clients-report.md)

- [<span data-ttu-id="ba618-109">Absenderdomänen Einblicke</span><span class="sxs-lookup"><span data-stu-id="ba618-109">Sender domain insight</span></span>](mfi-sender-domain-insight.md)

- [<span data-ttu-id="ba618-110">Unzustellbarkeitsbericht</span><span class="sxs-lookup"><span data-stu-id="ba618-110">Non-delivery report</span></span>](mfi-non-delivery-report.md)

- [<span data-ttu-id="ba618-111">Bericht "nicht akzeptierte Domäne"</span><span class="sxs-lookup"><span data-stu-id="ba618-111">Non-accepted domain report</span></span>](mfi-non-accepted-domain-report.md)

- [<span data-ttu-id="ba618-112">Fluss eingehenden und ausgehender E-Mails</span><span class="sxs-lookup"><span data-stu-id="ba618-112">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="ba618-113">Warteschlangenwarnungen und Warteschlangen</span><span class="sxs-lookup"><span data-stu-id="ba618-113">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="ba618-114">Bericht über automatisch weitergeleitete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="ba618-114">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="ba618-115">Einblick für E-Mail-Schleife</span><span class="sxs-lookup"><span data-stu-id="ba618-115">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="ba618-116">Einblick für langsame Nachrichtenflussregeln</span><span class="sxs-lookup"><span data-stu-id="ba618-116">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="ba618-117">Erforderliche Berechtigungen zum Anzeigen des Nachrichtenfluss-Dashboards</span><span class="sxs-lookup"><span data-stu-id="ba618-117">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="ba618-118">Das Nachrichtenfluss-Dashboard steht für Folgendes zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="ba618-118">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="ba618-119">Mitglieder der **globalen Administrator** Rolle.</span><span class="sxs-lookup"><span data-stu-id="ba618-119">Members of the **global administrator** role.</span></span>

- <span data-ttu-id="ba618-120">Mitglieder der **Exchange-Administrator** Rolle.</span><span class="sxs-lookup"><span data-stu-id="ba618-120">Members of **Exchange administrator** role.</span></span>

- <span data-ttu-id="ba618-121">Mitglieder der **Rolle "Nachrichtenfluss-Administrator** " im Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="ba618-121">Members of the **Mail flow administrator role** in the Security & Compliance Center.</span></span> <span data-ttu-id="ba618-122">Wenn diese Rolle explizit einem Benutzer zugewiesen ist, der kein Mitglied der globalen Administrator-oder Exchange-Administratorrolle ist:</span><span class="sxs-lookup"><span data-stu-id="ba618-122">If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="ba618-123">Der Benutzer muss sich direkt bei dem Security & Compliance Center anmelden <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="ba618-123">The user must log in to the Security & Compliance Center directly at <https://protection.office.com>.</span></span>

  - <span data-ttu-id="ba618-124">Der Benutzer verfügt nur über eine schreibgeschützte Berechtigung für das Nachrichtenfluss-Dashboard.</span><span class="sxs-lookup"><span data-stu-id="ba618-124">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="ba618-125">Der Benutzer hat keinen Zugriff auf das Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="ba618-125">The user won't have access to the Microsoft 365 admin center.</span></span>

<span data-ttu-id="ba618-126">Weitere Informationen zur Rolle "globaler Administrator" finden Sie unter [Informationen zu Microsoft 365 Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="ba618-126">For more information about the global administrator role, see [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="ba618-127">Informationen zum Zuweisen von Sicherheits & Compliance Center-Rollen für Benutzer finden Sie unter [Gewähren von Benutzern Zugriff auf das Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ba618-127">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="ba618-128">So finden Sie das Nachrichtenfluss-Dashboard</span><span class="sxs-lookup"><span data-stu-id="ba618-128">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="ba618-129">Wechseln Sie zum Security & Compliance Center unter [https://protection.office.com](https://protection.office.com) .</span><span class="sxs-lookup"><span data-stu-id="ba618-129">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="ba618-130">Erweitern Sie **Nachrichtenfluss** , und wählen Sie dann **Dashboard**aus.</span><span class="sxs-lookup"><span data-stu-id="ba618-130">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![Das Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mail-flow-dashboard-v2.png)
