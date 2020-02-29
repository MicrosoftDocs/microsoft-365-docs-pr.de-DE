---
title: Hinzufügen einer Domäne zu Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Fügen Sie Ihre Domäne zu Office 365 im Microsoft 365-Verwaltungszentrum hinzu, indem Sie einen DNS-Eintrag bei Ihrem DNS-Host hinzufügen. Der Setup-Assistent führt Sie nun durch den Vorgang.
ms.openlocfilehash: 4170fd74ae734a6fda9e535c17086997b1db6f6b
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42243982"
---
# <a name="add-a-domain-to-office-365"></a><span data-ttu-id="ff4b4-104">Hinzufügen einer Domäne zu Office 365</span><span class="sxs-lookup"><span data-stu-id="ff4b4-104">Add a domain to Office 365</span></span>

 <span data-ttu-id="ff4b4-105">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-105">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="ff4b4-106">*Um Domänen hinzuzufügen, zu ändern oder zu entfernen, **müssen** Sie ein **globaler Administrator** eines [Geschäfts- oder Unternehmensplans](https://products.office.com/business/office) sein. Diese Änderungen betreffen den gesamten Mandanten. *Benutzerdefinierte Administratoren* oder *reguläre Benutzer* können diese Änderungen nicht vornehmen.*</span><span class="sxs-lookup"><span data-stu-id="ff4b4-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="ff4b4-107">Führen Sie die folgenden Schritte aus, um eine Domäne hinzuzufügen, einzurichten oder die Einrichtung einer Domäne fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ff4b4-108">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="ff4b4-109">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ff4b4-110">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="ff4b4-111">Wechseln Sie zur Seite **Einstellungen** > **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="ff4b4-112">Wählen Sie **Domäne hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="ff4b4-113">Geben Sie den Namen der Domäne ein, die Sie hinzufügen möchten, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="ff4b4-114">Wählen Sie aus, wie Sie überprüfen möchten, ob Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="ff4b4-115">Wenn Ihre Domäne bei GoDaddy oder 1&amp;1 registriert ist, wählen Sie **Anmelden** > **Weiter** aus. Office 365 [richtet Ihre Einträge dann automatisch ein](../get-help-with-domains/domain-connect.md).</span><span class="sxs-lookup"><span data-stu-id="ff4b4-115">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Office 365 [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="ff4b4-116">Sie können auch eine E-Mail mit einem Prüfcode an den registrierten Kontakt für die Domäne senden lassen.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-116">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="ff4b4-117">Wenn Sie diese E-Mail nicht erkennen oder keinen Zugriff darauf haben, können Sie die dritte Option verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-117">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="ff4b4-118">Sie können einen TXT-Eintrag zur Überprüfung Ihrer Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-118">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="ff4b4-119">Wählen Sie dies und dann **Weiter** aus, um Anleitungen dazu anzuzeigen, wie Sie diesen DNS-Eintrag zur Website Ihrer Registrierungsstelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-119">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="ff4b4-120">Nachdem Sie den Eintrag hinzugefügt haben, kann die Überprüfung bis zu 30 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-120">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="ff4b4-121">Wählen Sie aus, wie Sie die erforderlichen DNS-Änderungen vornehmen möchten, damit Office Ihre Domäne verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-121">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="ff4b4-122">Wählen Sie **DNS-Einträge für mich hinzufügen** aus, wenn Office Ihr DNS automatisch konfigurieren soll.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-122">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="ff4b4-123">Wählen Sie **Ich füge die DNS-Einträge selbst hinzu** aus, wenn Sie nur bestimmte Office 365-Dienste an Ihre Domäne anfügen oder diesen Schritt zunächst überspringen und erst zu einem späteren Zeitpunkt ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-123">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="ff4b4-124">**Wählen Sie diese Option aus, wenn Sie genau wissen, was Sie tun.**</span><span class="sxs-lookup"><span data-stu-id="ff4b4-124">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="ff4b4-125">Wenn Sie ausgewählt haben, dass Sie *DNS-Einträge selbst hinzufügen* möchten, wählen Sie **Weiter** aus. Anschließend wird eine Seite mit allen Einträgen angezeigt, die Sie zur Website Ihrer Registrierungsstelle hinzufügen müssen, um Ihre Domäne einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-125">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="ff4b4-126">Wenn das Portal Ihre Registrierungsstelle nicht erkennt, können Sie [diesen allgemeinen Anleitungen folgen](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="ff4b4-126">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="ff4b4-127">Suchen Sie in der Liste der [hostspezifischen Anweisungen](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) Ihren Host, und führen Sie die Schritte zum Hinzufügen aller benötigten Datensätze aus.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-127">Check our list of [host-specific instructions](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="ff4b4-128">Wenn Sie den DNS-Hostinganbieter oder die Domänenregistrierungsstelle für Ihre Domäne nicht kennen, lesen Sie [Finden Ihrer Domänenregistrierungsstelle oder Ihres DNS-Hostinganbieters](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="ff4b4-128">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="ff4b4-129">Wenn Sie auf einen späteren Zeitpunkt warten möchten, scrollen Sie bis ans Ende, und wählen Sie **Diesen Schritt überspringen** aus.</span><span class="sxs-lookup"><span data-stu-id="ff4b4-129">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="ff4b4-130">Wählen Sie **Fertig stellen** aus. Sie haben es geschafft!</span><span class="sxs-lookup"><span data-stu-id="ff4b4-130">Select **Finish** - you're done!</span></span> 

## <a name="related-articles"></a><span data-ttu-id="ff4b4-131">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="ff4b4-131">Related articles</span></span>

[<span data-ttu-id="ff4b4-132">Häufig gestellte Fragen zu Domänen</span><span class="sxs-lookup"><span data-stu-id="ff4b4-132">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="ff4b4-133">Was ist eine Domäne?</span><span class="sxs-lookup"><span data-stu-id="ff4b4-133">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="ff4b4-134">Erwerben eines Domänennamens in Office 365</span><span class="sxs-lookup"><span data-stu-id="ff4b4-134">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="ff4b4-135">Einrichten Ihrer Domäne (hostspezifische Anweisungen)</span><span class="sxs-lookup"><span data-stu-id="ff4b4-135">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="ff4b4-136">Hilfe zu Office 365-Domänen erhalten</span><span class="sxs-lookup"><span data-stu-id="ff4b4-136">Get help with Office 365 domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
