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
description: Administratoren können sich über das Nachrichtenfluss-Dashboard im Security & Compliance Center informieren.
ms.openlocfilehash: 792fb07c1faae54696354619347d1eb5367d45b2
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081436"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="ff9fd-103">Nachrichtenfluss-Einblicke im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ff9fd-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="ff9fd-104">Administratoren können das Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um Trends, Einblicke zu ermitteln und Aktionen zum Beheben von Problemen im Zusammenhang mit dem Nachrichtenfluss in Ihrer Office 365 Organisation durchführen.</span><span class="sxs-lookup"><span data-stu-id="ff9fd-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their Office 365 organization.</span></span>

<span data-ttu-id="ff9fd-105">Die im e-Mail-Fluss-Dashboard verfügbaren Einblicke, Berichte und Widgets sind:</span><span class="sxs-lookup"><span data-stu-id="ff9fd-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="ff9fd-106">Nachrichtenfluss-Bericht</span><span class="sxs-lookup"><span data-stu-id="ff9fd-106">Mail flow map report</span></span>](mfi-mail-flow-map-report.md)

- [<span data-ttu-id="ff9fd-107">Einblick in den Domänen Nachrichtenflussstatus</span><span class="sxs-lookup"><span data-stu-id="ff9fd-107">Domain mail flow status insight</span></span>](mfi-domain-mail-flow-status-insight.md)

- [<span data-ttu-id="ff9fd-108">SMTP-Auth-Clientbericht</span><span class="sxs-lookup"><span data-stu-id="ff9fd-108">SMTP Auth clients report</span></span>](mfi-smtp-auth-clients-report.md)

- [<span data-ttu-id="ff9fd-109">Absenderdomänen Einblicke</span><span class="sxs-lookup"><span data-stu-id="ff9fd-109">Sender domain insight</span></span>](mfi-sender-domain-insight.md)

- [<span data-ttu-id="ff9fd-110">Unzustellbarkeitsbericht</span><span class="sxs-lookup"><span data-stu-id="ff9fd-110">Non-delivery report</span></span>](mfi-non-delivery-report.md)

- [<span data-ttu-id="ff9fd-111">Bericht "nicht akzeptierte Domäne"</span><span class="sxs-lookup"><span data-stu-id="ff9fd-111">Non-accepted domain report</span></span>](mfi-non-accepted-domain-report.md)

- [<span data-ttu-id="ff9fd-112">Fluss eingehenden und ausgehender E-Mails</span><span class="sxs-lookup"><span data-stu-id="ff9fd-112">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="ff9fd-113">Warteschlangenwarnungen und Warteschlangen</span><span class="sxs-lookup"><span data-stu-id="ff9fd-113">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="ff9fd-114">Bericht über automatisch weitergeleitete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="ff9fd-114">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="ff9fd-115">Einblick für E-Mail-Schleife</span><span class="sxs-lookup"><span data-stu-id="ff9fd-115">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="ff9fd-116">Einblick für langsame Nachrichtenflussregeln</span><span class="sxs-lookup"><span data-stu-id="ff9fd-116">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="ff9fd-117">Erforderliche Berechtigungen zum Anzeigen des Nachrichtenfluss-Dashboards</span><span class="sxs-lookup"><span data-stu-id="ff9fd-117">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="ff9fd-118">Das Nachrichtenfluss-Dashboard steht für Folgendes zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="ff9fd-118">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="ff9fd-119">Mitglieder der **globalen Administratorrolle Office 365** .</span><span class="sxs-lookup"><span data-stu-id="ff9fd-119">Members of the **Office 365 global administrator** role.</span></span>

- <span data-ttu-id="ff9fd-120">Mitglieder Office 365 Rolle " **Exchange-Administrator** ".</span><span class="sxs-lookup"><span data-stu-id="ff9fd-120">Members of **Office 365 Exchange administrator** role.</span></span>

- <span data-ttu-id="ff9fd-121">Mitglieder der **Rolle "Nachrichtenfluss-Administrator** " im Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="ff9fd-121">Members of the **Mail flow administrator role** in the Security & Compliance Center.</span></span> <span data-ttu-id="ff9fd-122">Wenn diese Rolle explizit einem Benutzer zugewiesen ist, der kein Mitglied der globalen Administrator-oder Exchange-Administratorrolle ist:</span><span class="sxs-lookup"><span data-stu-id="ff9fd-122">If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="ff9fd-123">Der Benutzer muss sich direkt bei [https://protection.office.com](https://protection.office.com)dem Security & Compliance Center anmelden.</span><span class="sxs-lookup"><span data-stu-id="ff9fd-123">The user must log in to the Security & Compliance Center directly at [https://protection.office.com](https://protection.office.com).</span></span>

  - <span data-ttu-id="ff9fd-124">Der Benutzer verfügt nur über eine schreibgeschützte Berechtigung für das Nachrichtenfluss-Dashboard.</span><span class="sxs-lookup"><span data-stu-id="ff9fd-124">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="ff9fd-125">Der Benutzer hat keinen Zugriff auf das Office 365-Verwaltungsportal.</span><span class="sxs-lookup"><span data-stu-id="ff9fd-125">The user won't have access to the Office 365 admin portal.</span></span>

<span data-ttu-id="ff9fd-126">Weitere Informationen zur Rolle Office 365 globalen Administrators finden Sie unter [Informationen zu Office 365 Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="ff9fd-126">For more information about the Office 365 global administrator role, see [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="ff9fd-127">Informationen zum Zuweisen von Sicherheits & Compliance Center-Rollen für Benutzer finden Sie unter [Gewähren von Benutzern Zugriff auf das Office 365 Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ff9fd-127">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Office 365 Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="ff9fd-128">So finden Sie das Nachrichtenfluss-Dashboard</span><span class="sxs-lookup"><span data-stu-id="ff9fd-128">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="ff9fd-129">Wechseln Sie zum Security & Compliance Center unter [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="ff9fd-129">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="ff9fd-130">Erweitern Sie **Nachrichtenfluss** , und wählen Sie dann **Dashboard**aus.</span><span class="sxs-lookup"><span data-stu-id="ff9fd-130">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![Das Nachrichtenfluss-Dashboard im Office 365 Security & Compliance Center](../../media/mail-flow-dashboard-v2.png)
