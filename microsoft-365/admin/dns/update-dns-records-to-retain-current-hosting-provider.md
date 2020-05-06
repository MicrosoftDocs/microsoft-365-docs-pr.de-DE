---
title: Aktualisieren von DNS-Einträgen, um die Website beim aktuellen Hostinganbieter zu belassen
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Hier erfahren Sie, wie Sie Datenverkehr zu einer vorhandenen öffentlichen Website weiterleiten, die außerhalb von Microsoft gehostet wird, wenn Sie Microsoft zum Verwalten von DNS-Einträgen für Ihre benutzerdefinierte Domäne festgelegt haben.
ms.openlocfilehash: 58b58479a2c880cc0193058abc328cc5feea4af1
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048831"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="7814a-103">Aktualisieren von DNS-Einträgen, um die Website beim aktuellen Hostinganbieter zu belassen</span><span class="sxs-lookup"><span data-stu-id="7814a-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="7814a-104">**Wenn Sie die Microsoft-Einträge Ihrer Domäne bei Ihrem DNS-Hostinganbieter verwalten**, müssen Sie sich keine Gedanken über die Schritte in diesem Thema machen.</span><span class="sxs-lookup"><span data-stu-id="7814a-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="7814a-105">Ihre Website bleibt, wo sie ist, und Benutzer können die Site weiterhin aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7814a-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="7814a-106">**Wenn Microsoft Ihre DNS-Einträge verwaltet**, führen Sie die folgenden Schritte aus, um Datenverkehr an eine vorhandene öffentliche Website zu leiten, die außerhalb von Microsoft gehostet wird, nachdem Sie Ihre Domäne zu Microsoft hinzugefügt haben:</span><span class="sxs-lookup"><span data-stu-id="7814a-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="7814a-107">Aktualisieren von DNS-Einträgen im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="7814a-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="7814a-108">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="7814a-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="7814a-109">Wählen Sie auf der Seite **Domänen** in der Liste der Domänen die Domäne aus, die Sie für Ihre Website verwenden, und wählen Sie dann im Verwaltungsbereich **DNS-Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="7814a-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="7814a-110">Wählen Sie **+ Neuer benutzerdefinierter Eintrag** aus, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7814a-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="7814a-111">Geben Sie unter **DNS-Typ** ein: **A (Adresse)**</span><span class="sxs-lookup"><span data-stu-id="7814a-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="7814a-112">Geben Sie unter **Hostname oder Alias** Folgendes ein: **@**</span><span class="sxs-lookup"><span data-stu-id="7814a-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="7814a-113">Geben Sie unter **IP-Adresse** die statische IP-Adresse für Ihre Website ein, unter der diese derzeit gehostet wird, beispielsweise "172.16.140.1".</span><span class="sxs-lookup"><span data-stu-id="7814a-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="7814a-p102">Es muss eine  *statische*  IP-Adresse für die Website sein, keine  *dynamische*  . Überprüfen Sie bei der Website, auf der Ihre Website gehostet wird, dass Sie eine statische IP-Adresse für Ihre öffentliche Website erhalten können.</span><span class="sxs-lookup"><span data-stu-id="7814a-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="7814a-116">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7814a-116">Select **Save**.</span></span> 
    
<span data-ttu-id="7814a-117">Darüber hinaus können Sie einen CNAME-Eintrag erstellen, damit Kunden Ihre Website besser finden können.</span><span class="sxs-lookup"><span data-stu-id="7814a-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="7814a-118">Wählen Sie **+ Neuer benutzerdefinierter Eintrag** aus, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7814a-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="7814a-119">Geben Sie unter **DNS-Typ** ein: **CNAME (Alias)**</span><span class="sxs-lookup"><span data-stu-id="7814a-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="7814a-120">Geben Sie unter **Hostname oder Alias** Folgendes ein: **www**</span><span class="sxs-lookup"><span data-stu-id="7814a-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="7814a-121">Geben Sie unter **Verweist auf die Adresse** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer Website ein, beispielsweise contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7814a-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="7814a-122">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="7814a-122">Select **Save**.</span></span> 
    
<span data-ttu-id="7814a-123">Führen Sie schließlich die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7814a-123">Finally, do the following:</span></span>
  
<span data-ttu-id="7814a-124">[Aktualisieren Sie die NS-Einträge Ihrer Domäne](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) so, dass Sie auf Microsoft verweist.</span><span class="sxs-lookup"><span data-stu-id="7814a-124">[Update your domain's NS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to point to Microsoft.</span></span> 
  
<span data-ttu-id="7814a-125">Wenn die NS-Einträge so aktualisiert wurden, dass Sie auf Microsoft verweist, ist Ihre Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="7814a-125">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="7814a-126">E-Mail-Nachrichten werden an Microsoft weitergeleitet, und der Datenverkehr zu Ihrer Website-Adresse wird weiterhin an Ihren aktuellen Website-Host weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="7814a-126">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
 
