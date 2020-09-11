---
title: Verwalten von Microsoft 365 mit Windows PowerShell für DAP-Partner
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: Wie Anbieter von Syndication-und Cloud Solution Providern (CSP) Windows PowerShell zum Verwalten von Microsoft 365-Kundenmandanten verwenden können
ms.openlocfilehash: a7b2fbb5423e3b923e17aa2d9c488e7dd085be35
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429878"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="9875d-103">Vorgehensweise Verwalten von Microsoft 365 mit Windows PowerShell für Partner mit Delegierten Zugriffsberechtigungen</span><span class="sxs-lookup"><span data-stu-id="9875d-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="9875d-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9875d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9875d-105">DAP-Partner (Delegated Access Permission, delegierte Zugriffsberechtigung) sind Syndication-Partner und Cloudlösungsanbieter (Cloud Solution Providers, CSP).</span><span class="sxs-lookup"><span data-stu-id="9875d-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="9875d-106">Viele sind Netzwerk-oder Telekom-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="9875d-106">Many are network or telecom providers.</span></span> <span data-ttu-id="9875d-107">Sie bündeln Microsoft 365-Abonnements in ihren Dienst angeboten.</span><span class="sxs-lookup"><span data-stu-id="9875d-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="9875d-108">Wenn Sie ein Microsoft 365-Abonnement verkaufen, erhalten Sie automatisch verwalten im Namen von (AOBO) Berechtigungen für den Mandanten des Kunden, damit Sie diese Mandanten verwalten und melden können.</span><span class="sxs-lookup"><span data-stu-id="9875d-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="9875d-109">Diese Aufgaben sind im Microsoft 365 Admin Center schwierig.</span><span class="sxs-lookup"><span data-stu-id="9875d-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9875d-110">Es ist viel einfacher, PowerShell für Microsoft 365 zu verwenden, um administrative Aufgaben wie:</span><span class="sxs-lookup"><span data-stu-id="9875d-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="9875d-111">Auflisten aller Kunden- **TenantIds** und ihrer Domänen</span><span class="sxs-lookup"><span data-stu-id="9875d-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="9875d-112">Identifizieren aller Benutzer in einer Kunden Mandantschaft und ihrer zugewiesenen Lizenzen</span><span class="sxs-lookup"><span data-stu-id="9875d-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="9875d-113">Einige Verwaltungsaufgaben können nur in PowerShell durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9875d-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="9875d-114">In den folgenden Artikeln wird gezeigt, wie Syndication-und CSP-Partner PowerShell zur Verwaltung Ihrer Kundenmandanten verwenden:</span><span class="sxs-lookup"><span data-stu-id="9875d-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="9875d-115">Verwalten von Microsoft 365-Mandanten mit Windows PowerShell für Partner mit Delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP)</span><span class="sxs-lookup"><span data-stu-id="9875d-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="9875d-116">Hinzufügen einer Domäne zu einem Kundenmandanten mit Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP)</span><span class="sxs-lookup"><span data-stu-id="9875d-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="9875d-117">Herstellen einer Verbindung mit Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="9875d-117">Connect to Exchange Online PowerShell</span></span>](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [<span data-ttu-id="9875d-118">Abrufen von Kundenberichtsdaten über Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP)</span><span class="sxs-lookup"><span data-stu-id="9875d-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
   