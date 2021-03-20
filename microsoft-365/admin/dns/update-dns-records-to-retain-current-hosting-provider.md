---
title: Aktualisieren von DNS-Einträgen, um die Website beim aktuellen Hostinganbieter zu belassen
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Erfahren Sie, wie Sie Datenverkehr an eine vorhandene öffentliche Website, die außerhalb von Microsoft gehostet wird, weiterrouten, wenn Sie Microsoft zum Verwalten von DNS-Einträgen für Ihre benutzerdefinierte Domäne festgelegt haben.
ms.openlocfilehash: ceef82345e562e2aa4c291f416c454fb831ee45b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915974"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="e9fc7-103">Aktualisieren von DNS-Einträgen, um die Website beim aktuellen Hostinganbieter zu belassen</span><span class="sxs-lookup"><span data-stu-id="e9fc7-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="e9fc7-104">**Wenn Sie die Microsoft-Einträge** Ihrer Domäne bei Ihrem DNS-Hostinganbieter verwalten, müssen Sie sich keine Gedanken über die Schritte in diesem Thema machen.</span><span class="sxs-lookup"><span data-stu-id="e9fc7-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="e9fc7-105">Ihre Website bleibt, wo sie ist, und Benutzer können die Site weiterhin aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e9fc7-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="e9fc7-106">**Wenn Microsoft Ihre DNS-Einträge** verwaltet, um Datenverkehr an eine vorhandene öffentliche Website zu routen, die außerhalb von Microsoft gehostet wird, gehen Sie nach dem Hinzufügen Ihrer Domäne zu Microsoft wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="e9fc7-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="e9fc7-107">Aktualisieren von DNS-Einträgen im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="e9fc7-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="e9fc7-108">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="e9fc7-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="e9fc7-109">Wählen Sie **auf der** Seite Domänen die Domäne aus, und wählen Sie dann **DNS-Einträge aus.**</span><span class="sxs-lookup"><span data-stu-id="e9fc7-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="e9fc7-110">Wählen **Sie unter DNS-Einstellungen** **benutzerdefinierte Datensätze aus.**</span><span class="sxs-lookup"><span data-stu-id="e9fc7-110">Under **DNS settings**, select **Custom Records**.</span></span>

4. <span data-ttu-id="e9fc7-111">Wählen Sie **+ Neuer benutzerdefinierter Eintrag** aus, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e9fc7-111">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="e9fc7-112">Geben Sie unter **DNS-Typ** ein: **A (Adresse)**</span><span class="sxs-lookup"><span data-stu-id="e9fc7-112">For **DNS type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="e9fc7-113">Geben Sie unter **Hostname oder Alias** Folgendes ein: **@**</span><span class="sxs-lookup"><span data-stu-id="e9fc7-113">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="e9fc7-114">Geben Sie unter **IP-Adresse** die statische IP-Adresse für Ihre Website ein, unter der diese derzeit gehostet wird, beispielsweise "172.16.140.1".</span><span class="sxs-lookup"><span data-stu-id="e9fc7-114">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="e9fc7-p102">Es muss eine  *statische*  IP-Adresse für die Website sein, keine  *dynamische*  . Überprüfen Sie bei der Website, auf der Ihre Website gehostet wird, dass Sie eine statische IP-Adresse für Ihre öffentliche Website erhalten können.</span><span class="sxs-lookup"><span data-stu-id="e9fc7-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
5. <span data-ttu-id="e9fc7-117">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e9fc7-117">Select **Save**.</span></span> 
    
<span data-ttu-id="e9fc7-118">Darüber hinaus können Sie einen CNAME-Eintrag erstellen, damit Kunden Ihre Website besser finden können.</span><span class="sxs-lookup"><span data-stu-id="e9fc7-118">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="e9fc7-119">Wählen Sie **+ Neuer benutzerdefinierter Eintrag** aus, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e9fc7-119">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="e9fc7-120">Geben Sie unter **DNS-Typ** ein: **CNAME (Alias)**</span><span class="sxs-lookup"><span data-stu-id="e9fc7-120">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="e9fc7-121">Geben Sie unter **Hostname oder Alias** Folgendes ein: **www**</span><span class="sxs-lookup"><span data-stu-id="e9fc7-121">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="e9fc7-122">Geben Sie unter **Verweist auf die Adresse** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer Website ein, beispielsweise contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e9fc7-122">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="e9fc7-123">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e9fc7-123">Select **Save**.</span></span> 
    
<span data-ttu-id="e9fc7-124">Führen Sie schließlich die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e9fc7-124">Finally, do the following:</span></span>
  
<span data-ttu-id="e9fc7-125">[Aktualisieren Sie die NS-Einträge Ihrer Domäne so, dass](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) sie auf Microsoft verweisen.</span><span class="sxs-lookup"><span data-stu-id="e9fc7-125">[Update your domain's NS records](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to point to Microsoft.</span></span> 
  
<span data-ttu-id="e9fc7-126">Wenn die NS-Einträge so aktualisiert wurden, dass sie auf Microsoft verweisen, ist Ihre Domäne alle eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="e9fc7-126">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="e9fc7-127">E-Mails werden an Microsoft geroutet, und der Datenverkehr zu Ihrer Websiteadresse wird weiterhin an Ihren aktuellen Websitehost gesendet.</span><span class="sxs-lookup"><span data-stu-id="e9fc7-127">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
