---
title: Verwalten Microsoft 365 mit Windows PowerShell für DAP-Partner
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
description: Wie Syndication- und Cloud Solution Provider (CSP)-Partner Windows PowerShell zum Verwalten Microsoft 365 Kunden mandanten verwenden können.
ms.openlocfilehash: 352a9a01414b94a1593de6a734151b687524fe7d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909526"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="31517-103">Verwalten von Microsoft 365 mit Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen</span><span class="sxs-lookup"><span data-stu-id="31517-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="31517-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="31517-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="31517-105">DAP-Partner (Delegated Access Permission, delegierte Zugriffsberechtigung) sind Syndication-Partner und Cloudlösungsanbieter (Cloud Solution Providers, CSP).</span><span class="sxs-lookup"><span data-stu-id="31517-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="31517-106">Viele sind Netzwerk- oder Telekommunikationsanbieter.</span><span class="sxs-lookup"><span data-stu-id="31517-106">Many are network or telecom providers.</span></span> <span data-ttu-id="31517-107">Sie bündeln Microsoft 365 Abonnements in ihren Serviceangeboten.</span><span class="sxs-lookup"><span data-stu-id="31517-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="31517-108">Wenn sie ein Microsoft 365-Abonnement verkaufen, erhalten sie automatisch Die Berechtigung Verwalten im Auftrag von (AOBO) für die Kundenmandschaften, damit sie diese Vermandungen verwalten und melden können.</span><span class="sxs-lookup"><span data-stu-id="31517-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="31517-109">Diese Aufgaben sind im Admin Center Microsoft 365 schwierig.</span><span class="sxs-lookup"><span data-stu-id="31517-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="31517-110">Es ist viel einfacher, PowerShell für Microsoft 365 verwaltungstechnische Aufgaben auszuführen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="31517-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="31517-111">Auflisten aller **Kunden-TenantIds und** ihrer Domänen</span><span class="sxs-lookup"><span data-stu-id="31517-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="31517-112">Identifizieren aller Benutzer in einem Kunden-Mandanz und den zugewiesenen Lizenzen</span><span class="sxs-lookup"><span data-stu-id="31517-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="31517-113">Einige administrative Aufgaben können nur in PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="31517-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="31517-114">Die folgenden Artikel zeigen, wie Syndication- und #A0 PowerShell verwenden, um ihre Kundenmandationen zu verwalten:</span><span class="sxs-lookup"><span data-stu-id="31517-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="31517-115">Verwalten Microsoft 365 Mandanten mit Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permissions, DAP)</span><span class="sxs-lookup"><span data-stu-id="31517-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="31517-116">Hinzufügen einer Domäne zu einem Kundenmandanten mit Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP)</span><span class="sxs-lookup"><span data-stu-id="31517-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="31517-117">Herstellen einer Verbindung mit Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="31517-117">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
- [<span data-ttu-id="31517-118">Abrufen von Kundenberichtsdaten über Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP)</span><span class="sxs-lookup"><span data-stu-id="31517-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
