---
title: Häufig gestellte Fragen zu Domänen
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- seo-marvel-may2020
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Erfahren Sie mehr über Domains (onmicrosoft-Domäne und Transfer Domäne), indem Sie Antworten auf Ihre Fragen in FAQ finden.
ms.openlocfilehash: 8d504711f46383000697736d6825a813f01fbe69
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906477"
---
# <a name="domains-faq"></a><span data-ttu-id="75acb-103">FAQ zu Domänen</span><span class="sxs-lookup"><span data-stu-id="75acb-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="75acb-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="75acb-104">The admin center is changing.</span></span> <span data-ttu-id="75acb-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview).</span><span class="sxs-lookup"><span data-stu-id="75acb-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview).</span></span>

::: moniker-end

<span data-ttu-id="75acb-106">Dieser Artikel enthält Antworten auf häufig gestellte Fragen zu Domänen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75acb-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="75acb-107">Wenn Sie keine Antwort auf Ihre Frage finden können, lassen Sie es uns wissen, indem Sie einen Kommentar hinterlassen, den wir der Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="75acb-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="75acb-108">Inhalt dieses Artikels</span><span class="sxs-lookup"><span data-stu-id="75acb-108">In this article</span></span>

- [<span data-ttu-id="75acb-109">Was ist MX-Priorität?</span><span class="sxs-lookup"><span data-stu-id="75acb-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="75acb-110">Wie kann ich SPF-Einträge für meine Domäne überprüfen?</span><span class="sxs-lookup"><span data-stu-id="75acb-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="75acb-111">Was ist ein Domänenname?</span><span class="sxs-lookup"><span data-stu-id="75acb-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="75acb-112">Was geschieht, wenn mein DNS-Anbieter bestimmte Eintragstypen nicht unterstützt?</span><span class="sxs-lookup"><span data-stu-id="75acb-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="75acb-113">Wie kann ich die Standarddomäne in Microsoft 365 festlegen oder ändern?</span><span class="sxs-lookup"><span data-stu-id="75acb-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="75acb-114">Kann ich Microsoft 365 benutzerdefinierte Unterdomänen oder mehrere Domänen hinzufügen?</span><span class="sxs-lookup"><span data-stu-id="75acb-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="75acb-115">Wie übertrage ich eine Domäne von Microsoft 365 auf einen anderen Host?</span><span class="sxs-lookup"><span data-stu-id="75acb-115">How do I transfer a domain from Microsoft 365 to another host?</span></span>](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- [<span data-ttu-id="75acb-116">Warum habe ich eine Domäne des Typs "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="75acb-116">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="75acb-117">Warum habe ich eine "onmicrosoft.de"-Domäne?</span><span class="sxs-lookup"><span data-stu-id="75acb-117">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="75acb-118">Wie kann ich meinen gemeinnützigen oder Bildungsstatus überprüfen?</span><span class="sxs-lookup"><span data-stu-id="75acb-118">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="75acb-119">Was ist MX-Priorität?</span><span class="sxs-lookup"><span data-stu-id="75acb-119">What is MX priority?</span></span>

<span data-ttu-id="75acb-120">E-Mail wird an MX-Server (Mail Exchange) mit der niedrigsten Einstellungsnummer (d. h. der höchsten Priorität) übermittelt. Deshalb muss der MX-Eintrag, den Sie für das Routing von E-Mail nutzen, die niedrigste Einstellungsnummer haben (in der Regel 0 oder die Priorität  *Hoch*  ).</span><span class="sxs-lookup"><span data-stu-id="75acb-120">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="75acb-121">Wenn Sie einen MX-Eintrag erstellen, verlangen die meisten DNS-Hostinganbieter, dass Sie die Einstellungsnummer festlegen.</span><span class="sxs-lookup"><span data-stu-id="75acb-121">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="75acb-122">Bei einigen heißt das Feld  *Einstellung*  , bei anderen  *Priorität*  .</span><span class="sxs-lookup"><span data-stu-id="75acb-122">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="75acb-123">Einige verlangen einen Wert und andere die Auswahl von  *Niedrig*  ,  *Mittel*  oder  *Hoch*  .</span><span class="sxs-lookup"><span data-stu-id="75acb-123">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="75acb-124">Wenn Sie nur über einen MX-Eintrag verfügen, spielt der Wert für "Priorität" oder "Einstellung" keine Rolle.</span><span class="sxs-lookup"><span data-stu-id="75acb-124">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="75acb-125">Wenn Sie über mehrere verfügen, stellen Sie sicher, dass der MX-Eintrag für das E-Mail-Routing eine höhere Priorität als derjenige hat, der zum Überprüfen genutzt wird, ob Ihnen die Domäne gehört.</span><span class="sxs-lookup"><span data-stu-id="75acb-125">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="75acb-126">Wie kann ich SPF-Einträge für meine Domäne überprüfen?</span><span class="sxs-lookup"><span data-stu-id="75acb-126">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="75acb-127">Es ist wichtig, dass Sie  **nur einen TXT-Eintrag für SPF** haben oder erstellen.</span><span class="sxs-lookup"><span data-stu-id="75acb-127">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="75acb-128">Wenn Sie bereits einen SPF-Eintrag haben, sollten Sie die neuen Microsoft 365-Werte an diese anfügen, anstatt eine neue zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="75acb-128">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="75acb-129">Nachdem Sie den SPF-Eintrag für Microsoft e-Mail hinzugefügt oder aktualisiert haben, sollten Sie überprüfen, ob die Syntax für eines dieser Tools richtig ist:</span><span class="sxs-lookup"><span data-stu-id="75acb-129">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="75acb-130">SPF Record Testing Tools</span><span class="sxs-lookup"><span data-stu-id="75acb-130">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="75acb-131">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="75acb-131">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="75acb-132">Dig Web Interface</span><span class="sxs-lookup"><span data-stu-id="75acb-132">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="75acb-133">Was ist ein Domänenname?</span><span class="sxs-lookup"><span data-stu-id="75acb-133">What is a domain name?</span></span>

<span data-ttu-id="75acb-p103">Eine Domäne ist ein eindeutiger Name, der in E-Mail-Adressen hinter dem **@** -Zeichen und in Internetadressen hinter **www.** angezeigt wird. Er besteht normalerweise aus dem Namen Ihrer Organisation und einem standardmäßigen Internetsuffix, z. B.  *ihrunternehmen.com*  oder  *musikhochschule.edu*  .</span><span class="sxs-lookup"><span data-stu-id="75acb-p103">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="75acb-137">Die Verwendung einer benutzerdefinierten Domäne wie " **Rob \@ contoso.com** " mit Microsoft 365 kann dazu beitragen, Glaubwürdigkeit und Anerkennung für Ihre Marke zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="75acb-137">Using a custom domain like " **rob\@contoso.com** " with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="75acb-138">Sie können [eine Domäne in Microsoft 365 kaufen, und wir werden Sie automatisch](../get-help-with-domains/buy-a-domain-name.md)einrichten, oder Sie können eine ihrer Besitzer aus einer Domänenregistrierungsstelle kaufen oder holen.</span><span class="sxs-lookup"><span data-stu-id="75acb-138">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="75acb-139">Was geschieht, wenn mein DNS-Anbieter bestimmte Eintragstypen nicht unterstützt?</span><span class="sxs-lookup"><span data-stu-id="75acb-139">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="75acb-140">Wenn Sie Ihre eigenen DNS-Einträge verwalten und Ihr DNS-Host nicht alle DNS-Einträge unterstützt, die von Microsoft 365 benötigt werden, funktionieren einige Features von Microsoft 365 nicht.</span><span class="sxs-lookup"><span data-stu-id="75acb-140">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="75acb-141">Wir empfehlen, in diesem Fall Ihre Domäne zu übertragen, und zwar zu einer Domänenregistrierungsstelle, die alle erforderlichen DNS-Einträge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="75acb-141">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="75acb-142">Anbieter, die alle erforderlichen DNS-Einträge unterstützen:</span><span class="sxs-lookup"><span data-stu-id="75acb-142">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="75acb-143">Dynadot</span><span class="sxs-lookup"><span data-stu-id="75acb-143">Dynadot</span></span>
    
- <span data-ttu-id="75acb-144">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="75acb-144">eNomCentral</span></span>
    
- <span data-ttu-id="75acb-145">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="75acb-145">Europe Registry</span></span>
    
- <span data-ttu-id="75acb-146">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="75acb-146">GoDaddy</span></span>
    
- <span data-ttu-id="75acb-147">Hover</span><span class="sxs-lookup"><span data-stu-id="75acb-147">Hover</span></span>
    
- <span data-ttu-id="75acb-148">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="75acb-148">MyHosting.com</span></span>
    
- <span data-ttu-id="75acb-149">Name.com</span><span class="sxs-lookup"><span data-stu-id="75acb-149">Name.com</span></span>
    
- <span data-ttu-id="75acb-150">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="75acb-150">Nearly Free Speech</span></span>
    
- <span data-ttu-id="75acb-151">Nettica</span><span class="sxs-lookup"><span data-stu-id="75acb-151">Nettica</span></span>
    
- <span data-ttu-id="75acb-152">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="75acb-152">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="75acb-153">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="75acb-153">Network Solutions</span></span>
    
- <span data-ttu-id="75acb-154">Register.com</span><span class="sxs-lookup"><span data-stu-id="75acb-154">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="75acb-155">Wie kann ich die Standarddomäne in Microsoft 365 festlegen oder ändern?</span><span class="sxs-lookup"><span data-stu-id="75acb-155">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="75acb-156">Sie müssen über mindestens eine benutzerdefinierte Domäne verfügen, die Sie zu Microsoft 365 hinzugefügt haben, bevor Sie eine Standarddomäne auswählen können.</span><span class="sxs-lookup"><span data-stu-id="75acb-156">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="75acb-157">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="75acb-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="75acb-158">Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="75acb-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="75acb-159">Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="75acb-159">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="75acb-160">Wählen Sie auf der Seite **Domänen** die Domäne aus, die Sie als Standard für neue e-Mail-Adressen festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="75acb-160">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="75acb-161">Wählen Sie **Als Standard festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="75acb-161">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="75acb-162">Sie können den Namen der ursprünglichen Domäne  *.onmicrosoft.com*  nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="75acb-162">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="75acb-163">Sie können den Namen ihrer ursprünglichen  *. onmicrosoft.de-*  Domäne nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="75acb-163">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="75acb-164">Sie können den Namen ihrer ursprünglichen  *. Partner.onmschina.cn-*  Domäne nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="75acb-164">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="75acb-165">Kann ich Microsoft 365 benutzerdefinierte Unterdomänen oder mehrere Domänen hinzufügen?</span><span class="sxs-lookup"><span data-stu-id="75acb-165">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="75acb-166">Ja.</span><span class="sxs-lookup"><span data-stu-id="75acb-166">Yes.</span></span> <span data-ttu-id="75acb-167">Zum Hinzufügen von Unterdomänen müssen Sie Ihre eigenen DNS-Einstellungen auf der Website Ihrer Registrierungsstelle verwalten.</span><span class="sxs-lookup"><span data-stu-id="75acb-167">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="75acb-168">Wenn Sie Microsoft Ihre DNS-Einstellungen mit NS-Datensätzen verwalten lassen oder wenn Sie die Domäne von Microsoft erworben haben, können Sie keine Unterdomänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="75acb-168">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="75acb-169">Ja!</span><span class="sxs-lookup"><span data-stu-id="75acb-169">Yes!</span></span> <span data-ttu-id="75acb-170">Zum Hinzufügen von Unterdomänen müssen Sie Ihre eigenen DNS-Einstellungen auf der Website Ihrer Registrierungsstelle verwalten.</span><span class="sxs-lookup"><span data-stu-id="75acb-170">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="75acb-171">Wenn Sie Microsoft Ihre DNS-Einstellungen mit NS-Datensätzen verwalten lassen oder wenn Sie die Domäne von Microsoft erworben haben, können Sie keine Unterdomänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="75acb-171">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="75acb-172">Ja!</span><span class="sxs-lookup"><span data-stu-id="75acb-172">Yes!</span></span> <span data-ttu-id="75acb-173">Zum Hinzufügen von Unterdomänen müssen Sie Ihre eigenen DNS-Einstellungen auf der Website Ihrer Registrierungsstelle verwalten.</span><span class="sxs-lookup"><span data-stu-id="75acb-173">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="75acb-174">Wenn Sie 21Vianet Ihre DNS-Einstellungen mit NS-Datensätzen verwalten lassen, können Sie keine Unterdomänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="75acb-174">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="75acb-175">In der Regel können Sie Ihrem Microsoft 365-Abonnement bis zu 900 Domänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="75acb-175">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="75acb-176">Sie können beispielsweise die Domänen "contoso.com" und "contosomarketing.com" und dann die Unterdomänen "www.contoso.com", "www.partner.contoso.com", "www.partner.marketing.contoso.com" usw. hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="75acb-176">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="75acb-177">Wenn Sie eine Unterdomäne hinzufügen, wird Sie automatisch basierend auf der überprüften übergeordneten Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="75acb-177">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="75acb-178">Wenn Sie Microsoft 365 mehrere Domänen hinzufügen, können Sie alle Dienste (wie e-Mail) in allen Domänen hosten, die Sie hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="75acb-178">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="75acb-179">*Wenn Sie Ihre e-Mail an Microsoft 365 ändern, indem Sie den MX-Eintrag einer Domäne aktualisieren, werden alle e-Mails, die an diese Domäne gesendet werden, mit Microsoft 365 gestartet.*</span><span class="sxs-lookup"><span data-stu-id="75acb-179">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="75acb-180">Wenn Sie eine contoso.com-Domäne zu einem Microsoft 365-Abonnement hinzugefügt haben, können Sie auch die Unterdomäne XYZ.contoso.com zu einer anderen Microsoft 365-Organisation hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="75acb-180">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="75acb-181">Beim Hinzufügen der Unterdomäne werden Sie aufgefordert, einen TXT-Eintrag im DNS-Hostanbieter hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="75acb-181">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a><span data-ttu-id="75acb-182">Wie übertrage ich eine Domäne von Microsoft 365 auf einen anderen Host?</span><span class="sxs-lookup"><span data-stu-id="75acb-182">How do I transfer a domain from Microsoft 365 to another host?</span></span>

<span data-ttu-id="75acb-183">Informationen zum Verfahren zum Übertragen einer Domäne finden Sie unter [übertragen einer Domäne von Microsoft auf einen anderen Host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span><span class="sxs-lookup"><span data-stu-id="75acb-183">For the procedure to transfer a domain, see [Transfer a domain from Microsoft to another host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span></span>

## <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="75acb-184">Microsoft 365-Pilot aus benutzerdefinierter Domäne</span><span class="sxs-lookup"><span data-stu-id="75acb-184">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="75acb-185">Das Verfahren zum pilotieren von Microsoft 365-e-Mail-Funktionen von einer benutzerdefinierten Domäne zu einem Microsoft 365-Postfach finden Sie unter [Pilot Microsoft 365 aus meiner benutzerdefinierten Domäne](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="75acb-185">For the procedure to pilot Microsoft 365 email functionality from a custom domain to a Microsoft 365 mailbox, see [Pilot Microsoft 365 from my custom domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="75acb-186">Warum habe ich eine Domäne des Typs "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="75acb-186">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="75acb-187">Microsoft 365 erstellt eine Domäne für Sie wie *contoso.onmicrosoft.com* , wenn Sie sich beim Dienst anmelden.</span><span class="sxs-lookup"><span data-stu-id="75acb-187">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com* , when you sign up with the service.</span></span> <span data-ttu-id="75acb-188">Die Benutzer-ID, die Sie bei der Registrierung erstellen, umfasst die Domäne, wie *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="75acb-188">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="75acb-189">**Wenn Sie möchten, dass Ihre e-Mails wie *Alan \@ contoso.com* aussehen:** [kaufen Sie die Domäne](../get-help-with-domains/buy-a-domain-name.md) , oder befolgen Sie einfach die Schritte unter [Hinzufügen Ihrer Benutzer und Domäne zu Microsoft 365,](add-domain.md) Wenn Sie bereits Besitzer sind.</span><span class="sxs-lookup"><span data-stu-id="75acb-189">**If you want to have your email look like *alan\@contoso.com* :** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="75acb-190">**Sie können die "onmicrosoft.com"-Domäne nach der Registrierung nicht umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="75acb-190">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="75acb-191">Wenn Sie beispielsweise "fourthcoffee.onmicrosoft.com" als ursprüngliche Domäne ausgewählt haben, können Sie sie nicht in "fabrikam.onmicrosoft.com" ändern.</span><span class="sxs-lookup"><span data-stu-id="75acb-191">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="75acb-192">Um eine andere onmicrosoft.com-Domäne verwenden zu können, müssen Sie ein neues Abonnement mit Microsoft 365 starten.</span><span class="sxs-lookup"><span data-stu-id="75acb-192">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="75acb-193">**Die URL der Teamwebsite kann nicht umbenannt werden.**</span><span class="sxs-lookup"><span data-stu-id="75acb-193">**You can't rename your team site URL.**</span></span> <span data-ttu-id="75acb-194">Ihre Teamwebsite-URL basiert auf Ihrem onmicrosoft.com-Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="75acb-194">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="75acb-195">Aufgrund der Funktionsweise SharePoint Online Architektur können Sie die Teamwebsite leider nicht umbenennen.</span><span class="sxs-lookup"><span data-stu-id="75acb-195">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="75acb-196">**Sie können Ihre "onmicrosoft.com"-Domäne nicht entfernen.**</span><span class="sxs-lookup"><span data-stu-id="75acb-196">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="75acb-197">Microsoft 365 muss ihn beibehalten, da es hinter den Kulissen für Ihr Abonnement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="75acb-197">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="75acb-198">Sie müssen diese Domäne jedoch nicht verwenden, nachdem Sie eine benutzerdefinierte Domäne hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="75acb-198">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="75acb-p114">Sie können die ursprüngliche Domäne "onmicrosoft.com" auch nach Hinzufügen Ihrer Domäne weiterverwenden. Sie funktioniert nämlich weiterhin für E-Mail und andere Dienste. Wählen Sie also selbst.</span><span class="sxs-lookup"><span data-stu-id="75acb-p114">You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="75acb-201">Warum habe ich eine "onmicrosoft.de"-Domäne?</span><span class="sxs-lookup"><span data-stu-id="75acb-201">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="75acb-202">Microsoft 365 erstellt eine Domäne für Sie wie *contoso.onmicrosoft.de* , wenn Sie sich beim Dienst anmelden.</span><span class="sxs-lookup"><span data-stu-id="75acb-202">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de* , when you sign up with the service.</span></span> <span data-ttu-id="75acb-203">Die Benutzer-ID, die Sie bei der Registrierung erstellen, umfasst die Domäne, wie *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="75acb-203">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="75acb-204">**Wenn Sie möchten, dass Ihre e-Mails wie *Alan@contoso.de* aussehen:** [kaufen Sie die Domäne](../get-help-with-domains/buy-a-domain-name.md) , oder befolgen Sie einfach die Schritte unter [Hinzufügen Ihrer Benutzer und Domäne zu Microsoft 365,](add-domain.md) Wenn Sie bereits Besitzer sind.</span><span class="sxs-lookup"><span data-stu-id="75acb-204">**If you want to have your email look like *alan@contoso.de* :** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="75acb-205">**Sie können die "onmicrosoft.com"-Domäne nach der Registrierung nicht umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="75acb-205">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="75acb-206">Wenn beispielsweise die anfängliche Domäne, die Sie ausgewählt haben, fourthcoffee.onmicrosoft.de war, können Sie Sie nicht in fabrikam.onmicrosoft.de ändern.</span><span class="sxs-lookup"><span data-stu-id="75acb-206">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="75acb-207">Um eine andere onmicrosoft.de-Domäne verwenden zu können, müssen Sie ein neues Abonnement mit Microsoft 365 starten.</span><span class="sxs-lookup"><span data-stu-id="75acb-207">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="75acb-208">**Die URL der Teamwebsite kann nicht umbenannt werden.**</span><span class="sxs-lookup"><span data-stu-id="75acb-208">**You can't rename your team site URL.**</span></span> <span data-ttu-id="75acb-209">Ihre Teamwebsite-URL basiert auf Ihrem onmicrosoft.de-Domänennamen. Aufgrund der Funktionsweise SharePoint Online Architektur können Sie die Teamwebsite leider nicht umbenennen.</span><span class="sxs-lookup"><span data-stu-id="75acb-209">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="75acb-210">**Sie können Ihre "onmicrosoft.com"-Domäne nicht entfernen.**</span><span class="sxs-lookup"><span data-stu-id="75acb-210">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="75acb-211">Microsoft 365 muss ihn beibehalten, da es hinter den Kulissen für Ihr Abonnement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="75acb-211">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="75acb-212">Sie müssen diese Domäne jedoch nicht verwenden, nachdem Sie eine benutzerdefinierte Domäne hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="75acb-212">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="75acb-213">Sie können die anfängliche onmicrosoft.de-Domäne auch dann weiterhin verwenden, wenn Sie Ihre Domäne hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="75acb-213">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="75acb-214">Es funktioniert immer noch für e-Mail und andere Dienste, daher ist es Ihre Wahl.</span><span class="sxs-lookup"><span data-stu-id="75acb-214">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="75acb-215">Wie kann ich meinen gemeinnützigen oder Bildungsstatus überprüfen?</span><span class="sxs-lookup"><span data-stu-id="75acb-215">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="75acb-216">Wählen Sie im [Admin Center](https://docs.microsoft.com/microsoft-365/admin/admin-home) die Option **Setup** aus, um den Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="75acb-216">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="75acb-217">(Achten Sie darauf, sich zuerst bei Microsoft 365 anzumelden.)</span><span class="sxs-lookup"><span data-stu-id="75acb-217">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="75acb-218">Um Administrator für Ihre Schule zu werden, wählen Sie die Option  **Administrator werden** in Microsoft 365 aus.</span><span class="sxs-lookup"><span data-stu-id="75acb-218">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="75acb-219">Sie werden aufgefordert, einen txt-DNS-Eintrag auf der DNS-Hostwebsite für Ihre Domäne hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="75acb-219">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="75acb-220">Warum?</span><span class="sxs-lookup"><span data-stu-id="75acb-220">Why?</span></span> <span data-ttu-id="75acb-221">Da Sie sich auf dem DNS-Host anmelden und einen Eintrag für Ihre Domäne hinzufügen, beweisen Sie Microsoft 365, dass Sie der Domänenname besitzen.</span><span class="sxs-lookup"><span data-stu-id="75acb-221">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="75acb-222">Nachdem Sie den Eintrag hinzugefügt haben, kehren Sie zum Microsoft 365-Portal zurück und bestätigen, dass Sie es hinzugefügt haben, damit Microsoft 365 überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="75acb-222">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="75acb-223">Sie haben eine gemeinnützige Organisation und möchten Microsoft 365 erhalten?</span><span class="sxs-lookup"><span data-stu-id="75acb-223">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="75acb-224">[Stellen Sie sicher, dass Ihre Organisation qualifiziert](https://www.microsoft.com/en-us/nonprofits/eligibility) ist, und melden Sie sich für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="75acb-224">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="75acb-225">Möchten Sie mehr darüber erfahren, wie Sie Administrator für Ihre Schule werden?</span><span class="sxs-lookup"><span data-stu-id="75acb-225">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="75acb-226">[Erfahren Sie alles darüber](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="75acb-226">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>
