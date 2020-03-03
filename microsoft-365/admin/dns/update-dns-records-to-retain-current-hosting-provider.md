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
description: Hier erfahren Sie, wie Sie Datenverkehr an eine vorhandene öffentliche Website weiterleiten, die außerhalb von Office 365 gehostet wird, wenn Sie Office 365 für die Verwaltung von DNS-Einträgen für Ihre benutzerdefinierte Domäne festgelegt haben.
ms.openlocfilehash: b92e778fb2fe0353a0d1d6bf83a4c617ab4541e2
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362410"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="362c5-103">Aktualisieren von DNS-Einträgen, um die Website beim aktuellen Hostinganbieter zu belassen</span><span class="sxs-lookup"><span data-stu-id="362c5-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="362c5-p101">[] **Wenn Sie alle Office 365-Einträge Ihrer Domäne bei Ihrem DNS-Hostinganbieter verwalten**, sind die Schritte in diesem Artikel für Sie irrelevant. Ihre Website bleibt, wo sie ist, und Benutzer können die Site weiterhin aufrufen.</span><span class="sxs-lookup"><span data-stu-id="362c5-p101">**If you manage your domain's Office 365 records at your DNS hosting provider**, you don't have to worry about the steps in this topic. Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="362c5-106">**Wenn Ihre DNS-Einträge von Office 365 verwaltet werden**, gehen Sie, nachdem Sie Ihre Domäne zu Office 365 hinzugefügt haben, wie folgt vor, um den Datenverkehr auf eine vorhandene öffentliche Website zu leiten, die außerhalb von Office 365 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="362c5-106">**If Office 365 manages your DNS records**, to route traffic to an existing public website hosted outside of Office 365, after you add your domain to Office 365, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="362c5-107">Aktualisieren von DNS-Einträgen im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="362c5-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="362c5-108">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="362c5-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="362c5-109">Wählen Sie auf der Seite **Domänen** in der Liste der Domänen die Domäne aus, die Sie für Ihre Website verwenden, und wählen Sie dann im Verwaltungsbereich **DNS-Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="362c5-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="362c5-110">Wählen Sie **+ Neuer benutzerdefinierter Eintrag** aus, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="362c5-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="362c5-111">Geben Sie unter **DNS-Typ** ein: **A (Adresse)**</span><span class="sxs-lookup"><span data-stu-id="362c5-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="362c5-112">Geben Sie unter **Hostname oder Alias** Folgendes ein: **@**</span><span class="sxs-lookup"><span data-stu-id="362c5-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="362c5-113">Geben Sie unter **IP-Adresse** die statische IP-Adresse für Ihre Website ein, unter der diese derzeit gehostet wird, beispielsweise "172.16.140.1".</span><span class="sxs-lookup"><span data-stu-id="362c5-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="362c5-p102">Es muss eine  *statische*  IP-Adresse für die Website sein, keine  *dynamische*  . Überprüfen Sie bei der Website, auf der Ihre Website gehostet wird, dass Sie eine statische IP-Adresse für Ihre öffentliche Website erhalten können.</span><span class="sxs-lookup"><span data-stu-id="362c5-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="362c5-116">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="362c5-116">Select **Save**.</span></span> 
    
<span data-ttu-id="362c5-117">Darüber hinaus können Sie einen CNAME-Eintrag erstellen, damit Kunden Ihre Website besser finden können.</span><span class="sxs-lookup"><span data-stu-id="362c5-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="362c5-118">Wählen Sie **+ Neuer benutzerdefinierter Eintrag** aus, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="362c5-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="362c5-119">Geben Sie unter **DNS-Typ** ein: **CNAME (Alias)**</span><span class="sxs-lookup"><span data-stu-id="362c5-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="362c5-120">Geben Sie unter **Hostname oder Alias** Folgendes ein: **www**</span><span class="sxs-lookup"><span data-stu-id="362c5-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="362c5-121">Geben Sie unter **Verweist auf die Adresse** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer Website ein, beispielsweise contoso.com.</span><span class="sxs-lookup"><span data-stu-id="362c5-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="362c5-122">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="362c5-122">Select **Save**.</span></span> 
    
<span data-ttu-id="362c5-123">Führen Sie schließlich die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="362c5-123">Finally, do the following:</span></span>
  
<span data-ttu-id="362c5-124">[Aktualisieren Ihrer Domänennamenservereinträge](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx), sodass sie auf Office 365 verweisen.</span><span class="sxs-lookup"><span data-stu-id="362c5-124">[Update your domain's NS records](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) to point to Office 365.</span></span> 
  
<span data-ttu-id="362c5-p103">Wenn die Namenservereinträge so aktualisiert wurden, dass sie auf Office 365 verweisen, ist Ihre Domäne wie folgt eingerichtet: E-Mail-Nachrichten werden an Office 365 weitergeleitet, und der an Ihre Websiteadresse gerichtete Datenverkehr geht weiterhin bei Ihrem aktuellen Websitehost ein.</span><span class="sxs-lookup"><span data-stu-id="362c5-p103">When the NS records have been updated to point to Office 365, your domain is all set up. Email will be routed to Office 365, and traffic to your website address will continue to go to your current website host.</span></span>
 
