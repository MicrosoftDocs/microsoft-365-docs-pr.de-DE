---
title: Microsoft 365-Client-App-Unterstützung – einmaliges Anmelden
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, welche Plattformen, Clients und PowerShell-Module einmaliges Anmelden für Microsoft 365 unterstützen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0171e277d6072515e7fe0ca8ede8b8005ad8fe2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690494"
---
# <a name="microsoft-365-client-app-support--single-sign-on"></a><span data-ttu-id="371b1-103">Microsoft 365-Client-App-Unterstützung – einmaliges Anmelden</span><span class="sxs-lookup"><span data-stu-id="371b1-103">Microsoft 365 Client App Support — Single Sign-On</span></span>

<span data-ttu-id="371b1-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="371b1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="371b1-105">Einmaliges Anmelden (Single Sign-on, SSO) fügt Sicherheit und Bequemlichkeit hinzu, wenn sich Ihre Benutzer bei Anwendungen in Azure Active Directory (Azure AD) anmelden.</span><span class="sxs-lookup"><span data-stu-id="371b1-105">Single sign-on (SSO) adds security and convenience when your users sign on to applications in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="371b1-106">Bei der einmaligen Anmeldung melden sich Benutzer mit einem Konto einmal an, um auf Domänen verbundene Geräte, Unternehmensressourcen, Software as a Service (SaaS)-Anwendungen und Webanwendungen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="371b1-106">With single sign-on, users sign in once with one account to access domain-joined devices, company resources, software as a service (SaaS) applications, and web applications.</span></span>

<span data-ttu-id="371b1-107">Weitere Informationen finden Sie [unter Single Sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="371b1-107">Learn more about [single sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="371b1-108">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="371b1-108">Supported platforms</span></span>

 - <span data-ttu-id="371b1-109">Windows 10 Desktop<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="371b1-109">Windows 10 Desktop<sup>2</sup></span></span>
 - <span data-ttu-id="371b1-110">Windows 10-moderne apps</span><span class="sxs-lookup"><span data-stu-id="371b1-110">Windows 10 Modern Apps</span></span>
 - <span data-ttu-id="371b1-111">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="371b1-111">Web browsers</span></span>
 - <span data-ttu-id="371b1-112">Android<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="371b1-112">Android<sup>3</sup></span></span>
 - <span data-ttu-id="371b1-113">IOS<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="371b1-113">iOS<sup>1</sup></span></span>
 - <span data-ttu-id="371b1-114">macOS<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="371b1-114">macOS<sup>4</sup></span></span>

<span data-ttu-id="371b1-115">Weitere Informationen zur Plattformunterstützung in Microsoft 365 finden Sie unter [System Requirements for Microsoft 365](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="371b1-115">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-clients"></a><span data-ttu-id="371b1-116">Unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="371b1-116">Supported clients</span></span>

<span data-ttu-id="371b1-117">Die neuesten Versionen der folgenden Clients unterstützen einmaliges Anmelden:</span><span class="sxs-lookup"><span data-stu-id="371b1-117">The latest versions of the following clients support single sign-on:</span></span>

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="371b1-118">![Access-Symbol](../media/o365-access-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-118">![Access icon](../media/o365-access-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-119">Access</span><span class="sxs-lookup"><span data-stu-id="371b1-119">Access</span></span>](https://products.office.com/access) | <span data-ttu-id="371b1-120">![Symbol des Unternehmensportals](../media/o365-microsoft-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-120">![Company portal icon](../media/o365-microsoft-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-121">Unternehmens <br> Portal<sup>3, 4</sup></span><span class="sxs-lookup"><span data-stu-id="371b1-121">Company <br> Portal<sup>3,4</sup> </span></span>](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | <span data-ttu-id="371b1-122">![Vertiefen (Symbol)](../media/o365-delve-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-122">![Delve icon](../media/o365-delve-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-123">Delve</span><span class="sxs-lookup"><span data-stu-id="371b1-123">Delve</span></span>](https://products.office.com/business/intelligent-search) | <span data-ttu-id="371b1-124">![Edge-Symbol](../media/o365-edge-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-124">![Edge icon](../media/o365-edge-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-125">Rand<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="371b1-125">Edge<sup>1</sup></span></span>](https://www.microsoft.com/windows/microsoft-edge) | <span data-ttu-id="371b1-126">![Excel-Symbol](../media/o365-excel-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-126">![Excel icon](../media/o365-excel-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-127">Excel</span><span class="sxs-lookup"><span data-stu-id="371b1-127">Excel</span></span>](https://products.office.com/excel) 
| <span data-ttu-id="371b1-128">![Kaizala-Symbol](../media/o365-kaizala-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-128">![Kaizala icon](../media/o365-kaizala-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-129">Kaizala<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="371b1-129">Kaizala<sup>1</sup></span></span>](https://products.office.com/en/business/microsoft-kaizala) | <span data-ttu-id="371b1-130">![Office.com-Symbol](../media/o365-office-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-130">![Office.com icon](../media/o365-office-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-131">Office.com</span><span class="sxs-lookup"><span data-stu-id="371b1-131">Office.com</span></span>](https://www.office.com/) | <span data-ttu-id="371b1-132">![Linsen Symbol](../media/o365-lens-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-132">![Lens icon](../media/o365-lens-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-133">Office Lens</span><span class="sxs-lookup"><span data-stu-id="371b1-133">Office Lens</span></span>](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | <span data-ttu-id="371b1-134">![OneDrive für Unternehmen Symbol](../media/o365-OneDrive-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-134">![OneDrive for Business icon](../media/o365-OneDrive-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-135">OneDrive</span><span class="sxs-lookup"><span data-stu-id="371b1-135">OneDrive</span></span>](https://products.office.com/onedrive-for-business/online-cloud-storage) | <span data-ttu-id="371b1-136">![OneNote-Symbol](../media/o365-OneNote-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-136">![OneNote icon](../media/o365-OneNote-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-137">OneNote<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="371b1-137">OneNote<sup>2</sup></span></span>](https://products.office.com/onenote) 
| <span data-ttu-id="371b1-138">![Outlook-Symbol](../media/o365-outlook-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-138">![Outlook icon](../media/o365-outlook-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-139">Outlook<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="371b1-139">Outlook<sup>4</sup></span></span>](https://products.office.com/outlook) | <span data-ttu-id="371b1-140">![Planner-Symbol](../media/o365-planner-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-140">![Planner icon](../media/o365-planner-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-141">Planner</span><span class="sxs-lookup"><span data-stu-id="371b1-141">Planner</span></span>](https://products.office.com/business/task-management-software) | <span data-ttu-id="371b1-142">![Power-Automatisierungs Symbol](../media/o365-flow-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-142">![Power Automate icon](../media/o365-flow-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-143">Power- <br> Automatisierung</span><span class="sxs-lookup"><span data-stu-id="371b1-143">Power <br> Automate</span></span>](https://flow.microsoft.com) | <span data-ttu-id="371b1-144">![PowerBI-Symbol](../media/o365-powerbi-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-144">![PowerBI icon](../media/o365-powerbi-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-145">Power BI<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="371b1-145">Power BI<sup>2</sup></span></span>](https://powerbi.microsoft.com)| <span data-ttu-id="371b1-146">![PowerPoint-Symbol](../media/o365-powerpoint-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-146">![PowerPoint icon](../media/o365-powerpoint-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-147">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="371b1-147">PowerPoint</span></span>](https://products.office.com/powerpoint) 
| <span data-ttu-id="371b1-148">![Project-Symbol](../media/o365-project-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-148">![Project icon](../media/o365-project-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-149">Project</span><span class="sxs-lookup"><span data-stu-id="371b1-149">Project</span></span>](https://products.office.com/project) | <span data-ttu-id="371b1-150">![Publisher-Symbol](../media/o365-publisher-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-150">![Publisher icon](../media/o365-publisher-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-151">Publisher</span><span class="sxs-lookup"><span data-stu-id="371b1-151">Publisher</span></span>](https://products.office.com/publisher) | <span data-ttu-id="371b1-152">![SharePoint-Symbol](../media/o365-sharepoint-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-152">![SharePoint icon](../media/o365-sharepoint-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-153">Share</span><span class="sxs-lookup"><span data-stu-id="371b1-153">Sharepoint</span></span>](https://products.office.com/sharepoint) | <span data-ttu-id="371b1-154">![Symbol für Notizen](../media/o365-stickynotes-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-154">![Sticky Notes icon](../media/o365-stickynotes-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-155">Kurznotizen</span><span class="sxs-lookup"><span data-stu-id="371b1-155">Sticky Notes</span></span>](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw)  | <span data-ttu-id="371b1-156">![Sway-Symbol](../media/o365-sway-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-156">![Sway icon](../media/o365-sway-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-157">Sway</span><span class="sxs-lookup"><span data-stu-id="371b1-157">Sway</span></span>](https://sway.com) 
| <span data-ttu-id="371b1-158">![Teams-Symbol](../media/o365-teams-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-158">![Teams icon](../media/o365-teams-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-159">Teams<sup>2, 4</sup></span><span class="sxs-lookup"><span data-stu-id="371b1-159">Teams<sup>2,4</sup></span></span>](https://products.office.com/microsoft-teams/group-chat-software) | <span data-ttu-id="371b1-160">![To-do-Symbol](../media/o365-todo-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-160">![To Do icon](../media/o365-todo-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-161">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="371b1-161">To Do</span></span>](https://todo.microsoft.com) | <span data-ttu-id="371b1-162">![Visio-Symbol](../media/o365-visio-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-162">![Visio icon](../media/o365-visio-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-163">Visio</span><span class="sxs-lookup"><span data-stu-id="371b1-163">Visio</span></span>](https://products.office.com/visio/flowchart-software) | <span data-ttu-id="371b1-164">![Whiteboard-Symbol](../media/o365-whiteboard-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-164">![Whiteboard icon](../media/o365-whiteboard-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-165">Whiteboard<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="371b1-165">Whiteboard<sup>3</sup></span></span>](https://whiteboard.microsoft.com/) | <span data-ttu-id="371b1-166">![Word-Symbol](../media/o365-word-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-166">![Word icon](../media/o365-word-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-167">Word</span><span class="sxs-lookup"><span data-stu-id="371b1-167">Word</span></span>](https://products.office.com/word) 
| <span data-ttu-id="371b1-168">![Yammer-Symbol](../media/o365-yammer-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-168">![Yammer icon](../media/o365-yammer-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-169">Jammern<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="371b1-169">Yammer<sup>2</sup></span></span>](https://products.office.com/yammer/yammer-overview) |

## <a name="supported-powershell-modules"></a><span data-ttu-id="371b1-170">Unterstützte PowerShell-Module</span><span class="sxs-lookup"><span data-stu-id="371b1-170">Supported PowerShell modules</span></span>

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="371b1-171">![Azure-Symbol](../media/o365-azure-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-171">![Azure icon](../media/o365-azure-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-172">Azure AD <br> PowerShell</span><span class="sxs-lookup"><span data-stu-id="371b1-172">Azure AD <br> PowerShell</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | <span data-ttu-id="371b1-173">![Exchange-Symbol](../media/o365-exchange-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-173">![Exchange icon](../media/o365-exchange-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-174">Exchange Online <br> PowerShell</span><span class="sxs-lookup"><span data-stu-id="371b1-174">Exchange Online <br> PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) | <span data-ttu-id="371b1-175">![SharePoint-Symbol](../media/o365-sharepoint-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="371b1-175">![SharePoint icon](../media/o365-sharepoint-64x64.png)</span></span> <br> [<span data-ttu-id="371b1-176">SharePoint Online <br> PowerShell</span><span class="sxs-lookup"><span data-stu-id="371b1-176">SharePoint Online <br> PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <span data-ttu-id="371b1-177"><sup>1</sup> Unterstützung für Edge-und Kaizala in ios in Kürze verfügbar.</span><span class="sxs-lookup"><span data-stu-id="371b1-177"><sup>1</sup> Support for Edge and Kaizala on iOS available soon.</span></span> <br>
> <span data-ttu-id="371b1-178"><sup>2</sup> Unterstützung für OneNote, PowerBI, Teams und jammern auf Windows 10-Desktop verfügbar in Kürze.</span><span class="sxs-lookup"><span data-stu-id="371b1-178"><sup>2</sup> Support for OneNote, PowerBI, Teams, and Yammer on Windows 10 Desktop available soon.</span></span> <br>
> <span data-ttu-id="371b1-179"><sup>3</sup> Unterstützung für Whiteboard auf Android in Kürze verfügbar.</span><span class="sxs-lookup"><span data-stu-id="371b1-179"><sup>3</sup> Support for Whiteboard on Android available soon.</span></span> <br>
> <span data-ttu-id="371b1-180"><sup>4</sup> Unterstützung für Outlook, Teams und Unternehmens Portal auf macOS in Kürze verfügbar.</span><span class="sxs-lookup"><span data-stu-id="371b1-180"><sup>4</sup> Support for Outlook, Teams, and Company Portal on macOS available soon.</span></span> <br>

## <a name="see-also"></a><span data-ttu-id="371b1-181">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="371b1-181">See also</span></span>

[<span data-ttu-id="371b1-182">Übersicht zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="371b1-182">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)