---
title: Häufig gestellte Fragen (FAQ) zu Domänen
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
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Erfahren Sie mehr über Domänen in Office 365, indem Sie Antworten auf Ihre Fragen in FAQ finden.
ms.custom: okr_smb
ms.openlocfilehash: f3c72f1ce772e3021d79aa4568dbfdb700400803
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2020
ms.locfileid: "42543804"
---
# <a name="domains-faq"></a><span data-ttu-id="3aef6-103">Häufig gestellte Fragen (FAQ) zu Domänen</span><span class="sxs-lookup"><span data-stu-id="3aef6-103">Domains FAQ</span></span>

<span data-ttu-id="3aef6-104">[] In diesem Artikel finden Sie Antworten auf häufig gestellte Fragen zu Domänen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="3aef6-104">This article contains answers to Frequently Asked Questions about domains in Office 365.</span></span>

<span data-ttu-id="3aef6-105">Wenn Sie keine Antwort auf Ihre Frage finden können, lassen Sie es uns wissen, indem Sie einen Kommentar hinterlassen, den wir der Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-105">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="3aef6-106">Was ist MX-Priorität?</span><span class="sxs-lookup"><span data-stu-id="3aef6-106">What is MX priority?</span></span>

<span data-ttu-id="3aef6-107">E-Mail wird an MX-Server (Mail Exchange) mit der niedrigsten Einstellungsnummer (d. h. der höchsten Priorität) übermittelt. Deshalb muss der MX-Eintrag, den Sie für das Routing von E-Mail nutzen, die niedrigste Einstellungsnummer haben (in der Regel 0 oder die Priorität  *Hoch*  ).</span><span class="sxs-lookup"><span data-stu-id="3aef6-107">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="3aef6-108">Wenn Sie einen MX-Eintrag erstellen, verlangen die meisten DNS-Hostinganbieter, dass Sie die Einstellungsnummer festlegen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-108">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="3aef6-109">Bei einigen heißt das Feld  *Einstellung*  , bei anderen  *Priorität*  .</span><span class="sxs-lookup"><span data-stu-id="3aef6-109">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="3aef6-110">Einige verlangen einen Wert und andere die Auswahl von  *Niedrig*  ,  *Mittel*  oder  *Hoch*  .</span><span class="sxs-lookup"><span data-stu-id="3aef6-110">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="3aef6-111">Wenn Sie nur über einen MX-Eintrag verfügen, spielt der Wert für "Priorität" oder "Einstellung" keine Rolle.</span><span class="sxs-lookup"><span data-stu-id="3aef6-111">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="3aef6-112">Wenn Sie über mehrere verfügen, stellen Sie sicher, dass der MX-Eintrag für das E-Mail-Routing eine höhere Priorität als derjenige hat, der zum Überprüfen genutzt wird, ob Ihnen die Domäne gehört.</span><span class="sxs-lookup"><span data-stu-id="3aef6-112">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="3aef6-113">Wie kann ich SPF-Einträge für meine Domäne überprüfen?</span><span class="sxs-lookup"><span data-stu-id="3aef6-113">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="3aef6-p101">Wichtig ist, dass Sie **nur einen TXT-Eintrag für SPF** haben bzw. erstellen. Wenn Sie bereits über einen SPF-Eintrag verfügen, müssen Sie die neuen Office 365-Werte daran anfügen, statt einen neuen Eintrag zu erstellen. Nachdem Sie Ihren SPF-Eintrag für Office 365-E-Mail hinzugefügt oder aktualisiert haben, müssen Sie mit einem dieser Tools prüfen, ob die Syntax ordnungsgemäß ist:</span><span class="sxs-lookup"><span data-stu-id="3aef6-p101">It's important that you have or create **only one TXT record for SPF**. If you already have an SPF record, you should append the new Office 365 values to it, rather than create a new one. After you've added or updated your SPF record for Office 365 email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="3aef6-117">SPF Record Testing Tools</span><span class="sxs-lookup"><span data-stu-id="3aef6-117">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="3aef6-118">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="3aef6-118">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="3aef6-119">Dig Web Interface</span><span class="sxs-lookup"><span data-stu-id="3aef6-119">Dig web interface</span></span>](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a><span data-ttu-id="3aef6-120">Wie verwaltet Office 365 meine DNS-Einträge?</span><span class="sxs-lookup"><span data-stu-id="3aef6-120">How does Office 365 manage my DNS records?</span></span>

<span data-ttu-id="3aef6-121">Es gibt zwei Optionen für die DNS-Verwaltung in Office 365:</span><span class="sxs-lookup"><span data-stu-id="3aef6-121">There are two options for DNS management with Office 365:</span></span>
  
1. <span data-ttu-id="3aef6-p102">Sie ändern Ihre Namenservereinträge, woraufhin Office 365 sich um alle dienstspezifischen Einträge kümmert, z. B. das Einrichten Ihres MX-Eintrags für E-Mail. **(Empfohlen)**</span><span class="sxs-lookup"><span data-stu-id="3aef6-p102">You change your nameserver (NS) records, and then Office 365 takes care of all the service-specific records, like setting up your MX record for email. **(Recommended)**</span></span>
    
2. <span data-ttu-id="3aef6-p103">Sie fügen DNS-Einträge für E-Mail und andere Office 365-Dienste bei Ihrem DNS-Host selbst hinzu. **(Nur für Experten)**</span><span class="sxs-lookup"><span data-stu-id="3aef6-p103">You add DNS records for email and other Office 365 services at your DNS host yourself. **(Experts only)**</span></span>
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a><span data-ttu-id="3aef6-126">Office 365 erstellt und hostet die DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="3aef6-126">Office 365 creates and hosts the DNS records</span></span> 
<span data-ttu-id="3aef6-127">**Vorteile**</span><span class="sxs-lookup"><span data-stu-id="3aef6-127">**Advantages**</span></span> 
- <span data-ttu-id="3aef6-128">Sie müssen keine Sorge haben, dass Sie bei der Eingabe der Werte in den DNS-Einträgen für Office 365-Dienste Fehler machen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-128">You don't have to worry about making mistakes in the values you enter for the DNS records for Office 365 services.</span></span>  
- <span data-ttu-id="3aef6-129">Sie haben mehr Flexibilität bei der Auswahl von Domänenregistrierungsstelle und DNS-Host.</span><span class="sxs-lookup"><span data-stu-id="3aef6-129">You have more flexibility in your choice of domain registrar and DNS host.</span></span> 
- <span data-ttu-id="3aef6-130">Jeder Anbieter, bei dem Sie Ihre Namenservereinträge ändern können, kann verwendet werden, selbst wenn der Anbieter nicht alle erforderlichen Eintragstypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3aef6-130">Any provider that lets you change your nameserver records will work, even if the provider doesn't support all the required record types.</span></span>   
- <span data-ttu-id="3aef6-131">Wenn Office 365 neue DNS-Einträge hinzufügt, müssen Sie keine Aktualisierungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-131">When Office 365 adds new DNS records, you don't have to make updates.</span></span>  

#### <a name="disadvantages"></a><span data-ttu-id="3aef6-132">Nachteile</span><span class="sxs-lookup"><span data-stu-id="3aef6-132">Disadvantages</span></span> 
- <span data-ttu-id="3aef6-133">Sie können Ihre DNS-Einträge nicht ändern, um E-Mails außerhalb von Office 365 zu hosten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-133">You can't change your DNS records to host email outside of Office 365.</span></span> 
- <span data-ttu-id="3aef6-134">Wenn Sie bereits eine öffentliche Website mit Ihrer Domäne als Adresse verwenden, wie etwa "www.fourthcoffee.com", müssen Sie Personen von Office 365 an diese Adresse umleiten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-134">If you already use a public website with your domain for its address, like www.fourthcoffee.com, you must redirect people to that address from Office 365.</span></span> 
- <span data-ttu-id="3aef6-135">Zum Einrichten der Umleitung ist eine statische IP-Adresse erforderlich, die für öffentliche Websites nicht immer so einfach verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3aef6-135">Setting up redirection requires a static IP address, which is not always easily available for public websites.</span></span> <span data-ttu-id="3aef6-136">-Wenn Ihre aktuelle Domänenregistrierungsstelle es Ihnen nicht erlaubt, die Namenservereinträge Ihrer Domäne zu ändern, müssen Sie zu einer anderen Registrierungsstelle wechseln, um diese DNS-Verwaltungsoption zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3aef6-136">- If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.</span></span>  

 ### <a name="you-manage-the-dns-records-yourself"></a><span data-ttu-id="3aef6-137">Sie verwalten die DNS-Einträge selbst.</span><span class="sxs-lookup"><span data-stu-id="3aef6-137">You manage the DNS records yourself</span></span> 
 #### <a name="advantages"></a><span data-ttu-id="3aef6-138">Vorteile</span><span class="sxs-lookup"><span data-stu-id="3aef6-138">Advantages</span></span>
- <span data-ttu-id="3aef6-139">Sie steuern die DNS-Einträge für Office 365-Dienste.</span><span class="sxs-lookup"><span data-stu-id="3aef6-139">You control the DNS records for Office 365 services.</span></span>   
- <span data-ttu-id="3aef6-140">Wenn Sie über eine öffentliche Website mit Ihrer Domäne als Adresse verfügen, wie etwa "www.fourthcoffee.com", müssen Sie sich keine Gedanken um eine Umleitung machen, damit sichergestellt ist, dass Benutzer weiterhin Ihre Website aufrufen können, nachdem Sie Ihre Domäne in Office 365 eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="3aef6-140">If you have a public website with your domain for its address, like www.fourthcoffee.com, you don't have to worry about using redirection to make sure people can still get to your website after you set up your domain in Office 365.</span></span>    
- <span data-ttu-id="3aef6-141">Sie haben die Flexibilität, E-Mails an einer anderen Stelle zu hosten, beispielsweise auf einem lokalen Exchange-Server.</span><span class="sxs-lookup"><span data-stu-id="3aef6-141">You have the flexibility to host email somewhere else, such as with an on-premises Exchange server.</span></span>  
 
#### <a name="disadvantages"></a><span data-ttu-id="3aef6-142">Nachteile</span><span class="sxs-lookup"><span data-stu-id="3aef6-142">Disadvantages</span></span>
<span data-ttu-id="3aef6-143">Sie müssen die DNS-Einträge für Office 365-Dienste selbst einrichten (sofern Sie nicht über eine GoDaddy-Domäne verfügen).</span><span class="sxs-lookup"><span data-stu-id="3aef6-143">You have to set up the DNS records for Office 365 services yourself (unless you have a GoDaddy domain).</span></span> 
-  <span data-ttu-id="3aef6-144">Wenn Ihr aktueller DNS-Host nicht alle erforderlichen Eintragstypen für Office 365 unterstützt, sind einige Office 365-Features nicht verfügbar, und Sie müssen möglicherweise zu einem anderen DNS-Host wechseln.</span><span class="sxs-lookup"><span data-stu-id="3aef6-144">If your current DNS host doesn't support all of the required record types for Office 365, some Office 365 features won't be available and you might need to switch to a different DNS host.</span></span> 
- <span data-ttu-id="3aef6-145">Wenn Office 365 die Anforderungen für DNS-Einträge ändert oder neue Dienste hinzufügt, müssen Sie die Aktualisierungen bei Ihrem DNS-Host selbst durchführen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-145">When Office 365 changes requirements for DNS records, or adds new services, you have to make updates yourself at your DNS host.</span></span> 
   
## <a name="what-is-a-domain-name"></a><span data-ttu-id="3aef6-146">Was ist ein Domänenname?</span><span class="sxs-lookup"><span data-stu-id="3aef6-146">What is a domain name?</span></span>


<span data-ttu-id="3aef6-p105">Eine Domäne ist ein eindeutiger Name, der in E-Mail-Adressen hinter dem **@** -Zeichen und in Internetadressen hinter **www.** angezeigt wird. Er besteht normalerweise aus dem Namen Ihrer Organisation und einem standardmäßigen Internetsuffix, z. B.  *ihrunternehmen.com*  oder  *musikhochschule.edu*  .</span><span class="sxs-lookup"><span data-stu-id="3aef6-p105">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="3aef6-150">Die Verwendung einer benutzerdefinierten Domäne wie "**Rob\@contoso.com**" mit Office 365 kann dazu beitragen, Glaubwürdigkeit und Anerkennung für Ihre Marke aufzubauen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-150">Using a custom domain like "**rob\@contoso.com**" with Office 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="3aef6-151">Sie können [eine Domäne in Office 365 erwerben](../get-help-with-domains/buy-a-domain-name.md), die wir dann automatisch einrichten, oder Sie können eine Domäne bei Ihrer Domänenregistrierungsstelle erwerben oder eine dort bereits erworbene Domäne übertragen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-151">You can [buy a domain in Office 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a><span data-ttu-id="3aef6-152">Kann ich eine von Microsoft erworbene Domäne an einen anderen Anbieter übertragen?</span><span class="sxs-lookup"><span data-stu-id="3aef6-152">Can I transfer a domain I purchased from Microsoft to another provider?</span></span>

<span data-ttu-id="3aef6-153">Ja, aber Sie können eine Office 365 Domäne erst nach 60 Tagen, nachdem Sie Sie mit Office 365 erworben haben, an eine andere Registrierungsstelle übertragen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-153">Yes, but you can't transfer an Office 365 domain to another registrar until 60 days after you purchased it with Office 365.</span></span>

<span data-ttu-id="3aef6-154">Beachten Sie, dass eine *Whois* -Abfrage eine Office 365 erworbene Domänenregistrierungsstelle als "Wild West Domains LLC" anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="3aef6-154">Please note that a *Whois* query will show an Office 365 purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="3aef6-155">In Bezug auf Ihre Office 365 erworbene Domäne sollten jedoch nur Office 365 kontaktiert werden.</span><span class="sxs-lookup"><span data-stu-id="3aef6-155">However, only Office 365 should be contacted regarding your Office 365 purchased domain.</span></span>
  
<span data-ttu-id="3aef6-156">Führen Sie die nachstehenden Schritte aus, um den Code bei Office 365 zu erhalten. Wechseln Sie dann zur Website der anderen Domänenregistrierungsstelle, um die Übertragung Ihres Domänennamens an diese Registrierungsstelle einzurichten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-156">Follow the steps below to get the code at Office 365, and then go to the other domain registrar's website to set up transferring your domain name to that registrar.</span></span>
  
1. <span data-ttu-id="3aef6-157">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="3aef6-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="3aef6-158">Wenn Sie Office 365 Deutschland verwenden, navigieren Sie zu dieser <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a> Seite.</span><span class="sxs-lookup"><span data-stu-id="3aef6-158">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="3aef6-159">Wenn Sie Office 365 betrieben von 21Vianet verwenden, navigieren Sie zu dieser <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a> Seite.</span><span class="sxs-lookup"><span data-stu-id="3aef6-159">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="3aef6-160">Wählen Sie auf der Seite **Domänen** die Office 365 Domäne aus, die Sie an eine andere Domänenregistrierungsstelle übertragen möchten **, und wählen Sie dann Domaintransfer** > **enable Domaintransfer**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-160">On the **Domains** page, select the Office 365 domain that you want to transfer to another domain registrar, and then select **Domain Transfer** > **Enable domain transfer**.</span></span>
       
4. <span data-ttu-id="3aef6-161">Führen Sie die nachstehenden Schritte aus, um die Übertragung Ihrer Domäne vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-161">Follow the steps to prepare for transferring your domain.</span></span>
    
5. <span data-ttu-id="3aef6-162">Nachdem Sie den Code erhalten haben, wechseln Sie zur Website der Domänenregistrierungsstelle, bei der Sie Ihren Domänennamen verwalten möchten. Folgen Sie dann den Anweisungen der Registrierungsstelle zur Übertragung einer Domäne (suchen Sie auf deren Website nach Hilfe).</span><span class="sxs-lookup"><span data-stu-id="3aef6-162">After you get the code, go to the website of the domain registrar where you want to manage your domain name going forward and follow their directions for transferring a domain (search for help on their website).</span></span>
    
6. <span data-ttu-id="3aef6-163">Wenn Sie den Code erneut sehen müssen, wählen Sie auf der Seite **Domäneneinstellungen** in Office 365 die Option **Autorisierungscode für die Domänen Übertragung anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-163">If you need to see the code again, on the **Domain settings** page in Office 365, select **View authorization code for domain transfer**.</span></span>
    
7. <span data-ttu-id="3aef6-164">Nach Abschluss der Übertragung erneuern Sie Ihre Domäne bei der neuen Domänenregistrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="3aef6-164">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>
    
8. <span data-ttu-id="3aef6-165">Um den Vorgang abzuschließen, kehren Sie zur Seite Admin Center- **Domänen** zurück, und wählen Sie **vollständige Domänen Übertragung**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-165">To finish the process, go back to the admin center **Domains** page and select **Complete Domain Transfer**.</span></span> 

<span data-ttu-id="3aef6-166">*Hinweis: Beachten Sie, dass Office 365 erworbenen Domänen nicht für Namen Server Änderungen oder die Übertragung der Domäne zwischen Office 365 Mandanten berechtigt sind.  Wenn eine dieser Anforderungen erforderlich ist, muss die Domänenregistrierung an eine andere Registrierungsstelle übertragen werden.*</span><span class="sxs-lookup"><span data-stu-id="3aef6-166">*Note: Please note that Office 365 purchased domains are not eligible for Name Server changes or transferring the domain between Office 365 Tenants.  If either of these are required, the domain registration will need to be transferred to another registrar.*</span></span>
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a><span data-ttu-id="3aef6-167">Wie ändere ich die Verwaltung meiner DNS-Einträge in Office 365?</span><span class="sxs-lookup"><span data-stu-id="3aef6-167">How do I change how my DNS records are managed in Office 365?</span></span>

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a><span data-ttu-id="3aef6-168">Wechseln der DNS-Verwaltung auf einen DNS-Host außerhalb von Office 365</span><span class="sxs-lookup"><span data-stu-id="3aef6-168">Change DNS management to a DNS host outside Office 365</span></span>
   
1. <span data-ttu-id="3aef6-169">Melden Sie sich bei der Domänenregistrierungsstelle für Ihre Domäne an.</span><span class="sxs-lookup"><span data-stu-id="3aef6-169">Sign in to the domain registrar for your domain.</span></span>
    
2. <span data-ttu-id="3aef6-p107">Suchen Sie den Bereich auf der Website der Registrierungsstelle, auf der Sie die Namenservereinträge aktualisieren, und aktualisieren Sie die Namenserver so, dass sie auf den DNS-Host Ihrer Domäne verweisen. (Der DNS-Host ist oft die Domänenregistrierungsstelle.)</span><span class="sxs-lookup"><span data-stu-id="3aef6-p107">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host. (The DNS host is often the domain registrar.)</span></span>
    
3. <span data-ttu-id="3aef6-172">Klicken Sie auf einen Link, um zum Setup-Assistenten für Domänen zu wechseln:</span><span class="sxs-lookup"><span data-stu-id="3aef6-172">Follow a link to go to the domains setup wizard:</span></span>
    
4. <span data-ttu-id="3aef6-173">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="3aef6-173">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="3aef6-174">Wenn Sie Office 365 Deutschland verwenden, navigieren Sie zu dieser <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a> Seite.</span><span class="sxs-lookup"><span data-stu-id="3aef6-174">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="3aef6-175">Wenn Sie Office 365 betrieben von 21Vianet verwenden, navigieren Sie zu dieser <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a> Seite.</span><span class="sxs-lookup"><span data-stu-id="3aef6-175">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
5. <span data-ttu-id="3aef6-176">Wählen Sie auf der Seite **Domänen** die Domäne aus, die Sie wechseln möchten, und wählen Sie **DNS-Verwaltung**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-176">On the **Domains** page, select the domain you're switching, and select **DNS management**.</span></span>
    
6. <span data-ttu-id="3aef6-177">Wählen Sie im Setup-Assistenten für Domänen auf der Seite **richten Sie Ihre Onlinedienste** aus die Option **Ich werde meine eigenen DNS-Einträge verwalten**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-177">In the domains setup wizard, on the **Set up your online services** page, select **I'll manage my own DNS records**, and then select **Next**.</span></span>
    
7. <span data-ttu-id="3aef6-178">Fügen Sie der Website der Registrierungsstelle die vom Assistenten vorgeschlagenen DNS-Einträge auf der Seite " **DNS-Einstellungen aktualisieren** " hinzu.</span><span class="sxs-lookup"><span data-stu-id="3aef6-178">Add the DNS records suggested by the wizard on the **Update DNS settings** page to your registrar's website.</span></span> 
    
8. <span data-ttu-id="3aef6-179">Nachdem Sie die Datensätze hinzugefügt haben, kehren Sie zu Office 365 zurück, und wählen Sie **überprüfen**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-179">After you've added the records, come back to Office 365 and select **Verify**.</span></span>
    

### <a name="change-dns-management-to-office-365"></a><span data-ttu-id="3aef6-180">Wechseln der DNS-Verwaltung zu Office 365</span><span class="sxs-lookup"><span data-stu-id="3aef6-180">Change DNS management to Office 365</span></span>
  
1. <span data-ttu-id="3aef6-181">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="3aef6-181">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="3aef6-182">Wenn Sie Office 365 Deutschland verwenden, navigieren Sie zu dieser <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a> Seite.</span><span class="sxs-lookup"><span data-stu-id="3aef6-182">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="3aef6-183">Wenn Sie Office 365 betrieben von 21Vianet verwenden, navigieren Sie zu dieser <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a> Seite.</span><span class="sxs-lookup"><span data-stu-id="3aef6-183">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="3aef6-184">Wählen Sie auf der Seite **Domänen** die Domäne aus, die Sie wechseln möchten, und wählen Sie **DNS-Verwaltung**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-184">On the **Domains** page, select the domain you're switching, and select **DNS Management**.</span></span>
    
3. <span data-ttu-id="3aef6-185">Wählen Sie im Setup-Assistenten für Domänen auf der Seite **richten Sie Ihre Onlinedienste** aus die Option **meine Onlinedienste für mich einrichten aus. (Empfohlen)**, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-185">In the domains setup wizard, on the **Set up your online services** page, select **Set up my online services for me. (Recommended)**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="3aef6-186">Wenn Sie die Domäne noch nicht überprüft haben, führen Sie hierzu zuerst die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-186">If you haven't verified the domain yet, follow the steps to do that first.</span></span>
    
5. <span data-ttu-id="3aef6-p108">Auf der Seite **DNS-Einstellungen aktualisieren** werden die Namenserver für Office 365 aufgelistet. Wechseln Sie zur Domänenregistrierungsstelle für Ihre Domäne, und ändern Sie die Namenserver in die Office 365-Namenserver.</span><span class="sxs-lookup"><span data-stu-id="3aef6-p108">On the **Update DNS settings** page, we list the nameservers for Office 365. Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span></span> 
    
4. <span data-ttu-id="3aef6-189">Nachdem Sie die Namenserver aktualisiert haben, **warten Sie mindestens eine Stunde**.</span><span class="sxs-lookup"><span data-stu-id="3aef6-189">After you've updated the nameservers, **wait at least an hour**.</span></span> <span data-ttu-id="3aef6-190">Wählen Sie dann zurück im Assistenten in Office 365 die Option **überprüfen**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-190">Then, back in the wizard in Office 365, select **Verify**.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="3aef6-191">Was geschieht, wenn mein DNS-Anbieter bestimmte Eintragstypen nicht unterstützt?</span><span class="sxs-lookup"><span data-stu-id="3aef6-191">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="3aef6-p110">Wenn Sie Ihre eigenen DNS-Einträge verwalten und Ihr DNS-Host nicht alle von Office 365 benötigten DNS-Einträge unterstützt, funktionieren einige der Office 365-Funktionen nicht. Wir empfehlen, in diesem Fall Ihre Domäne zu übertragen, und zwar zu einer Domänenregistrierungsstelle, die alle erforderlichen DNS-Einträge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3aef6-p110">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work. We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="3aef6-194">Anbieter, die alle erforderlichen DNS-Einträge unterstützen:</span><span class="sxs-lookup"><span data-stu-id="3aef6-194">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="3aef6-195">Dynadot</span><span class="sxs-lookup"><span data-stu-id="3aef6-195">Dynadot</span></span>
    
- <span data-ttu-id="3aef6-196">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="3aef6-196">eNomCentral</span></span>
    
- <span data-ttu-id="3aef6-197">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="3aef6-197">Europe Registry</span></span>
    
- <span data-ttu-id="3aef6-198">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="3aef6-198">GoDaddy</span></span>
    
- <span data-ttu-id="3aef6-199">Hover</span><span class="sxs-lookup"><span data-stu-id="3aef6-199">Hover</span></span>
    
- <span data-ttu-id="3aef6-200">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="3aef6-200">MyHosting.com</span></span>
    
- <span data-ttu-id="3aef6-201">Name.com</span><span class="sxs-lookup"><span data-stu-id="3aef6-201">Name.com</span></span>
    
- <span data-ttu-id="3aef6-202">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="3aef6-202">Nearly Free Speech</span></span>
    
- <span data-ttu-id="3aef6-203">Nettica</span><span class="sxs-lookup"><span data-stu-id="3aef6-203">Nettica</span></span>
    
- <span data-ttu-id="3aef6-204">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="3aef6-204">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="3aef6-205">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="3aef6-205">Network Solutions</span></span>
    
- <span data-ttu-id="3aef6-206">Register.com</span><span class="sxs-lookup"><span data-stu-id="3aef6-206">Register.com</span></span>
    
 <span data-ttu-id="3aef6-207">**Wenn keine SRV-Einträge unterstützt werden**, stehen die folgenden Office 365-Funktionen nicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="3aef6-207">**If SRV records are not supported**, the following Office 365 features are not available:</span></span> 
  
- <span data-ttu-id="3aef6-208">Skype for Business Online-Chat und Integration von Anwesenheitsinformationen in Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="3aef6-208">Skype for Business Online IM and presence integration with Outlook Web App</span></span>
    
- <span data-ttu-id="3aef6-209">Externe Kommunikation (Verbund) mit Skype for Business Online-Benutzern in anderen Organisationen</span><span class="sxs-lookup"><span data-stu-id="3aef6-209">External communication (federation) with Skype for Business Online users in other organizations.</span></span>
    
- <span data-ttu-id="3aef6-210">PIC (Public Internet Connectivity) mit Skype for Business Online-Benutzern, die mit einem Microsoft-Konto (vormals Windows Live ID) angemeldet sind</span><span class="sxs-lookup"><span data-stu-id="3aef6-210">Public Internet Connectivity (PIC) with Skype for Business Online users signed in with a Microsoft account (formerly known as a Windows Live ID).</span></span>
    
 <span data-ttu-id="3aef6-211">**Wenn mehrere CNAME-Einträge nicht unterstützt werden,** müssen Sie zwischen den folgenden Features für Skype for Business Online wählen:</span><span class="sxs-lookup"><span data-stu-id="3aef6-211">**If multiple CNAME records are not supported,** you have to choose between the following features for Skype for Business Online:</span></span> 
  
- <span data-ttu-id="3aef6-212">E-Mail-Desktop- und mobile Clients können mit dem AutoErmittlungsdienst automatisch den Exchange Online-Dienst finden, sodass die Benutzer sich anmelden können, ohne den Servernamen eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-212">Email desktop clients and mobile clients can use Autodiscover to automatically find the Exchange Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="3aef6-213">Skype for Business Online-Desktopclients können mit dem AutoErmittlungsdienst automatisch den Skype for Business Online-Dienst finden, sodass die Benutzer sich anmelden können, ohne den Servernamen eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-213">Skype for Business Online desktop clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="3aef6-214">Mobile Skype for Business Online-Clients können mit dem AutoErmittlungsdienst automatisch den Skype for Business Online-Dienst finden, sodass die Benutzer sich anmelden können, ohne den Servernamen eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-214">Skype for Business Online mobile clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
 <span data-ttu-id="3aef6-p111">**Wenn SPF-/TXT-Einträge nicht unterstützt werden**, sind andere Personen möglicherweise in der Lage, über Ihre Domäne Spam oder andere schädliche E-Mails zu senden. Mithilfe von SPF-Einträgen werden die Server bestimmt, denen es gestattet ist, E-Mails über Ihre Domäne zu senden.</span><span class="sxs-lookup"><span data-stu-id="3aef6-p111">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email. SPF records work by identifying the servers that are authorized to send email from your domain.</span></span> 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a><span data-ttu-id="3aef6-217">Wie kann ich die Standarddomäne in Office 365 festlegen oder ändern?</span><span class="sxs-lookup"><span data-stu-id="3aef6-217">How do I set or change the default domain in Office 365?</span></span>

<span data-ttu-id="3aef6-218">Sie müssen über mindestens eine benutzerdefinierte Domäne verfügen, die Sie Office 365 hinzugefügt haben, bevor Sie eine Standarddomäne auswählen können.</span><span class="sxs-lookup"><span data-stu-id="3aef6-218">You must have at least one custom domain that you've added to Office 365 before you can choose a default domain.</span></span>
  
1. <span data-ttu-id="3aef6-219">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="3aef6-219">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="3aef6-220">Wenn Sie Office 365 Deutschland verwenden, navigieren Sie zu dieser <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a> Seite.</span><span class="sxs-lookup"><span data-stu-id="3aef6-220">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="3aef6-221">Wenn Sie Office 365 betrieben von 21Vianet verwenden, navigieren Sie zu dieser <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a> Seite.</span><span class="sxs-lookup"><span data-stu-id="3aef6-221">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="3aef6-222">Wählen Sie auf der Seite **Domänen** die Domäne aus, die Sie als Standard für neue e-Mail-Adressen festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-222">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="3aef6-223">Wählen Sie **als Standard festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-223">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="3aef6-224">Sie können den Namen der ursprünglichen Domäne  *.onmicrosoft.com*  nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="3aef6-224">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="3aef6-225">Sie können den Namen ihrer ursprünglichen *. onmicrosoft.de-* Domäne nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="3aef6-225">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="3aef6-226">Sie können den Namen ihrer ursprünglichen *. Partner.onmschina.cn-* Domäne nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="3aef6-226">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a><span data-ttu-id="3aef6-227">Kann ich in Office 365 benutzerdefinierte Unterdomänen oder mehrere Domänen hinzufügen?</span><span class="sxs-lookup"><span data-stu-id="3aef6-227">Can I add custom subdomains or multiple domains to Office 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="3aef6-228">Ja!</span><span class="sxs-lookup"><span data-stu-id="3aef6-228">Yes!</span></span> <span data-ttu-id="3aef6-229">Zum Hinzufügen von Unterdomänen müssen Sie Ihre eigenen DNS-Einstellungen auf der Website Ihrer Registrierungsstelle verwalten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-229">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="3aef6-230">Wenn Sie Microsoft Ihre DNS-Einstellungen mit NS-Datensätzen verwalten lassen oder wenn Sie die Domäne von Microsoft erworben haben, können Sie keine Unterdomänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-230">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="3aef6-231">Ja!</span><span class="sxs-lookup"><span data-stu-id="3aef6-231">Yes!</span></span> <span data-ttu-id="3aef6-232">Zum Hinzufügen von Unterdomänen müssen Sie Ihre eigenen DNS-Einstellungen auf der Website Ihrer Registrierungsstelle verwalten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-232">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="3aef6-233">Wenn Sie Microsoft Ihre DNS-Einstellungen mit NS-Datensätzen verwalten lassen oder wenn Sie die Domäne von Microsoft erworben haben, können Sie keine Unterdomänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-233">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="3aef6-234">Ja!</span><span class="sxs-lookup"><span data-stu-id="3aef6-234">Yes!</span></span> <span data-ttu-id="3aef6-235">Zum Hinzufügen von Unterdomänen müssen Sie Ihre eigenen DNS-Einstellungen auf der Website Ihrer Registrierungsstelle verwalten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-235">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="3aef6-236">Wenn Sie 21Vianet Ihre DNS-Einstellungen mit NS-Datensätzen verwalten lassen, können Sie keine Unterdomänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-236">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="3aef6-237">Sie können Ihrem Office 365-Abonnement in der Regel bis zu 900 Domänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-237">Typically, you can add up to 900 domains to your Office 365 subscription.</span></span>
  
<span data-ttu-id="3aef6-238">Sie können beispielsweise die Domänen "contoso.com" und "contosomarketing.com" und dann die Unterdomänen "www.contoso.com", "www.partner.contoso.com", "www.partner.marketing.contoso.com" usw. hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-238">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="3aef6-239">Wenn Sie eine Unterdomäne hinzufügen, wird Sie automatisch basierend auf der überprüften übergeordneten Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="3aef6-239">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="3aef6-p115">Wenn Sie Office 365 mehrere Domänen hinzufügen, können Sie beliebige dieser Dienste (wie E-Mail) in jeder der von Ihnen hinzugefügten Domäne hosten.  *Wenn Sie Ihr E-Mail-System in Office 365 ändern, indem Sie den MX-Eintrag der Domäne ändern, werden von nun an ALLE an diese Domäne gesendeten E-Mails an Office 365 gesendet.*</span><span class="sxs-lookup"><span data-stu-id="3aef6-p115">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.  *When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="3aef6-242">Wenn Sie bereits eine contoso.com-Domäne zu einem Office 365 Mandanten hinzugefügt haben, können Sie auch die Unterdomäne XYZ.contoso.com zu einem anderen Office 365 Mandanten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-242">If you have already added a contoso.com domain to an Office 365 tenant, you can also add the subdomain xyz.contoso.com to another Office 365 tenant.</span></span> <span data-ttu-id="3aef6-243">Beim Hinzufügen der Unterdomäne werden Sie aufgefordert, einen TXT-Eintrag im DNS-Hostanbieter hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-243">When adding the subdomain, you will be prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="3aef6-244">Warum habe ich eine Domäne des Typs "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="3aef6-244">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="3aef6-245">Office 365 erstellt eine Domäne für Sie wie *contoso.onmicrosoft.com*, wenn Sie sich beim Dienst anmelden.</span><span class="sxs-lookup"><span data-stu-id="3aef6-245">Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="3aef6-246">Die Benutzer-ID, die Sie bei der Registrierung erstellen, umfasst die Domäne, wie *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="3aef6-246">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="3aef6-247">**Wenn Sie möchten, dass Ihre e-Mails wie *Alan\@contoso.com*aussehen:** [kaufen Sie die Domäne](../get-help-with-domains/buy-a-domain-name.md) , oder befolgen Sie die Schritte unter [Hinzufügen Ihrer Benutzer und Domäne zu Office 365,](add-domain.md) Wenn Sie bereits Besitzer sind.</span><span class="sxs-lookup"><span data-stu-id="3aef6-247">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="3aef6-p118">**Sie können die "onmicrosoft.com"-Domäne nach der Registrierung nicht umbenennen**. Wenn Sie beispielsweise "fourthcoffee.onmicrosoft.com" als ursprüngliche Domäne ausgewählt haben, können Sie sie nicht in "fabrikam.onmicrosoft.com" ändern. Um eine andere "onmicrosoft.com"-Domäne verwenden zu können, müssen Sie ein neues Abonnement bei Office 365 einrichten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-p118">**You can't rename the onmicrosoft domain after sign-up.** For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com. To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="3aef6-251">**Die URL der Teamwebsite kann nicht umbenannt werden.**</span><span class="sxs-lookup"><span data-stu-id="3aef6-251">**You can't rename your team site URL.**</span></span> <span data-ttu-id="3aef6-252">Ihre Teamwebsite-URL basiert auf Ihrem onmicrosoft.com-Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-252">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="3aef6-253">Aufgrund der Funktionsweise SharePoint Online Architektur können Sie die Teamwebsite leider nicht umbenennen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-253">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="3aef6-p120">**Sie können Ihre "onmicrosoft.com"-Domäne nicht entfernen.** Office 365 muss diese Domäne beibehalten, weil sie im Hintergrund für Ihr Abonnement verwendet wird. Sie müssen diese Domäne jedoch nicht verwenden, nachdem Sie eine benutzerdefinierte Domäne hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="3aef6-p120">**You can't remove your onmicrosoft domain.** Office 365 needs to keep it around because it's used behind the scenes for your subscription. But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="3aef6-p121">Sie können die ursprüngliche Domäne "onmicrosoft.com" auch nach Hinzufügen Ihrer Domäne weiterverwenden. Sie funktioniert nämlich weiterhin für E-Mail und andere Dienste. Wählen Sie also selbst.</span><span class="sxs-lookup"><span data-stu-id="3aef6-p121">You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="3aef6-259">Warum habe ich eine "onmicrosoft.de"-Domäne?</span><span class="sxs-lookup"><span data-stu-id="3aef6-259">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="3aef6-260">Office 365 erstellt eine Domäne für Sie wie *contoso.onmicrosoft.de*, wenn Sie sich beim Dienst anmelden.</span><span class="sxs-lookup"><span data-stu-id="3aef6-260">Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="3aef6-261">Die Benutzer-ID, die Sie bei der Registrierung erstellen, umfasst die Domäne, wie *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="3aef6-261">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="3aef6-262">**Wenn Sie möchten, dass Ihre e-Mails wie *Alan@contoso.de*aussehen:** [kaufen Sie die Domäne](../get-help-with-domains/buy-a-domain-name.md) , oder befolgen Sie die Schritte unter [Hinzufügen Ihrer Benutzer und Domäne zu Office 365,](add-domain.md) Wenn Sie bereits Besitzer sind.</span><span class="sxs-lookup"><span data-stu-id="3aef6-262">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="3aef6-263">**Sie können die "onmicrosoft.com"-Domäne nach der Registrierung nicht umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="3aef6-263">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="3aef6-264">Wenn beispielsweise die anfängliche Domäne, die Sie ausgewählt haben, fourthcoffee.onmicrosoft.de war, können Sie Sie nicht in fabrikam.onmicrosoft.de ändern.</span><span class="sxs-lookup"><span data-stu-id="3aef6-264">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="3aef6-265">Um eine andere onmicrosoft.de-Domäne verwenden zu können, müssen Sie ein neues Abonnement mit Office 365 starten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-265">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="3aef6-266">**Die URL der Teamwebsite kann nicht umbenannt werden.**</span><span class="sxs-lookup"><span data-stu-id="3aef6-266">**You can't rename your team site URL.**</span></span> <span data-ttu-id="3aef6-267">Ihre Teamwebsite-URL basiert auf Ihrem onmicrosoft.de-Domänennamen. Aufgrund der Funktionsweise SharePoint Online Architektur können Sie die Teamwebsite leider nicht umbenennen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-267">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="3aef6-p125">**Sie können Ihre "onmicrosoft.com"-Domäne nicht entfernen.** Office 365 muss diese Domäne beibehalten, weil sie im Hintergrund für Ihr Abonnement verwendet wird. Sie müssen diese Domäne jedoch nicht verwenden, nachdem Sie eine benutzerdefinierte Domäne hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="3aef6-p125">**You can't remove your onmicrosoft domain.** Office 365 needs to keep it around because it's used behind the scenes for your subscription. But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="3aef6-271">Sie können die anfängliche onmicrosoft.de-Domäne auch dann weiterhin verwenden, wenn Sie Ihre Domäne hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="3aef6-271">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="3aef6-272">Es funktioniert immer noch für e-Mail und andere Dienste, daher ist es Ihre Wahl.</span><span class="sxs-lookup"><span data-stu-id="3aef6-272">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="3aef6-273">Wie kann ich meinen gemeinnützigen oder Bildungsstatus überprüfen?</span><span class="sxs-lookup"><span data-stu-id="3aef6-273">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="3aef6-274">Wählen Sie im [Admin Center](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) die Option **Setup** aus, um den Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-274">Select **Setup** in the [admin center](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) to start the wizard.</span></span> <span data-ttu-id="3aef6-275">(Achten Sie darauf, dass Sie sich zuerst bei Office 365 anmelden.)</span><span class="sxs-lookup"><span data-stu-id="3aef6-275">(Be sure to sign in to Office 365 first.)</span></span> 
    
2. <span data-ttu-id="3aef6-276">Um Administrator für Ihre Schule zu werden, wählen Sie die Option **Administrator werden** in Office 365 aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-276">To become the admin for your school, select the **Become an admin** option in Office 365.</span></span> 
    
3. <span data-ttu-id="3aef6-277">Sie werden aufgefordert, einen txt-DNS-Eintrag auf der DNS-Hostwebsite für Ihre Domäne hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-277">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="3aef6-278">Warum?</span><span class="sxs-lookup"><span data-stu-id="3aef6-278">Why?</span></span> <span data-ttu-id="3aef6-279">Da Sie sich auf dem DNS-Host anmelden und einen Eintrag für Ihre Domäne hinzufügen, belegen Sie Office 365, dass Sie der Domänenname besitzen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-279">Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="3aef6-280">Nachdem Sie den Eintrag hinzugefügt haben, kehren Sie zum Office 365 Portal zurück und bestätigen, dass Sie es hinzugefügt haben, damit Office 365 überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="3aef6-280">After you add the record, you'll go back to the Office 365 portal and confirm that you've added it, so Office 365 can check.</span></span>
    
<span data-ttu-id="3aef6-281">Sie haben eine gemeinnützige Organisation und möchten Office 365 erhalten?</span><span class="sxs-lookup"><span data-stu-id="3aef6-281">Have a nonprofit and want to get Office 365?</span></span> <span data-ttu-id="3aef6-282">[Stellen Sie sicher, dass Ihre Organisation qualifiziert](https://www.microsoft.com/en-us/nonprofits/eligibility) ist, und melden Sie sich für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="3aef6-282">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="3aef6-283">Möchten Sie mehr darüber erfahren, wie Sie Administrator für Ihre Schule werden?</span><span class="sxs-lookup"><span data-stu-id="3aef6-283">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="3aef6-284">[Erfahren Sie alles darüber](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="3aef6-284">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a><span data-ttu-id="3aef6-285">Kann ich Office 365 mit nur wenigen e-Mail-Adressen aus meiner benutzerdefinierten Domäne pilotieren?</span><span class="sxs-lookup"><span data-stu-id="3aef6-285">Can I pilot Office 365 with just a few email addresses from my custom domain?</span></span>

<span data-ttu-id="3aef6-286">Sie können, aber es gibt Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="3aef6-286">You can, but there are limitations:</span></span>
  
- <span data-ttu-id="3aef6-287">Ihr aktueller e-Mail-Anbieter muss eine e-Mail weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-287">Your current email provider must provide email forwarding.</span></span>
    
- <span data-ttu-id="3aef6-288">Sie müssen Ihre Office 365 bezogenen DNS-Einträge bei Ihrem DNS-Hostinganbieter verwalten, anstatt diese Einträge Office 365 verwalten zu müssen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-288">You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you.</span></span> <span data-ttu-id="3aef6-289">Weitere Informationen dazu finden Sie unter Hinzufügen Ihrer Domäne zu Office 365, wenn Sie Ihre eigenen DNS-Einträge verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-289">To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.</span></span>
    
- <span data-ttu-id="3aef6-290">Einige Office 365 Funktionen stehen nicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="3aef6-290">Some Office 365 features won't be available:</span></span>
- <span data-ttu-id="3aef6-291">Benutzer können keine Frei/Gebucht-Informationen für die Benutzer anzeigen, die sich auf dem anderen e-Mail-Anbieter befinden.</span><span class="sxs-lookup"><span data-stu-id="3aef6-291">Users won't be able to see free/busy information for the users who are on the other email provider.</span></span>
- <span data-ttu-id="3aef6-292">Administratoren können nicht alle Konten von einem Ort aus verwalten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-292">Admins won't be able to administer everyone's accounts from one place.</span></span>
- <span data-ttu-id="3aef6-293">Benutzer können Office 365 Spamfilterung möglicherweise nicht verwenden</span><span class="sxs-lookup"><span data-stu-id="3aef6-293">Users may not be able to use Office 365 spam filtering</span></span>

### <a name="how-to-set-up-an-office-365-pilot"></a><span data-ttu-id="3aef6-294">Einrichten eines Office 365 Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="3aef6-294">How to set up an Office 365 pilot</span></span>
    
1. <span data-ttu-id="3aef6-295">Melden Sie sich beim Microsoft 365 Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="3aef6-295">Sign in to the Microsoft 365 admin center</span></span>
    
    1. <span data-ttu-id="3aef6-296">Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="3aef6-296">Sign in to Office 365 with your work or school account.</span></span>
        
    2. <span data-ttu-id="3aef6-297">Wechseln Sie zu **Einstellungen** \> **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="3aef6-297">Go to **Settings** \> **Domains**.</span></span> 
    
2. <span data-ttu-id="3aef6-298">Stellen Sie sicher, dass Sie die Domäne besitzen, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-298">Verify that you own the domain you want to use</span></span>
    
    1. <span data-ttu-id="3aef6-299">Wählen Sie auf der Seite **Domänen** die Option **Domäne hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-299">On the **Domains** page, select **Add domain**.</span></span> 
        
    2. <span data-ttu-id="3aef6-300">Geben Sie im Bereich die Domäne in diesem Beispiel cohowinery.com ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-300">In the panel, type the domain, in this example cohowinery.com, and then select **Next**.</span></span> 
        
    3. <span data-ttu-id="3aef6-301">Führen Sie auf der Seite Domäne **überprüfen** die schrittweisen Anleitungen aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-301">On the **Verify** domain page, follow the step-by-step instructions.</span></span> 
        
    4. <span data-ttu-id="3aef6-302">Wählen Sie in der Dropdownliste Ihren DNS-Hostinganbieter aus, und befolgen Sie die Anweisungen, um anzuzeigen, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="3aef6-302">In the drop-down list, select your DNS hosting provider, and follow the instructions to show that you own the domain.</span></span>
        
    5. <span data-ttu-id="3aef6-303">Wählen Sie **überprüfen**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-303">Select **Verify**.</span></span> <span data-ttu-id="3aef6-304">Es dauert zwischen ein paar Minuten und 72 Stunden, bis DNS-Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="3aef6-304">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span> 
        
    6. <span data-ttu-id="3aef6-305">Wenn die Überprüfung erfolgreich verläuft, werden Sie aufgefordert, Ihre DNS-Einträge zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3aef6-305">When verification is successful, you'll be asked to modify your DNS records.</span></span>
    
3. <span data-ttu-id="3aef6-306">Markieren der Domäne als freigegeben in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3aef6-306">Mark the domain as shared in Exchange Online</span></span>
    
    1. <span data-ttu-id="3aef6-307">Wechseln Sie zum **Exchange Admin Center** (EAC).</span><span class="sxs-lookup"><span data-stu-id="3aef6-307">Go to the **Exchange admin center** (EAC).</span></span> 
        
    2. <span data-ttu-id="3aef6-308">Wählen Sie im Abschnitt **Nachrichtenfluss** die Option **akzeptierte Domänen**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-308">In the **Mail flow** section, select **Accepted domains**.</span></span> 
        
    3. <span data-ttu-id="3aef6-309">Doppelklicken Sie auf die Domäne, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-309">Double-click the domain you want to modify.</span></span>
        
    4. <span data-ttu-id="3aef6-310">Wählen Sie im daraufhin geöffneten Fenster **Internes Relay**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-310">In the window that opens, select **Internal Relay**.</span></span> 
        
    5. <span data-ttu-id="3aef6-311">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3aef6-311">Select **Save**.</span></span> <span data-ttu-id="3aef6-312">Diese Einstellung erfordert möglicherweise einige Minuten, um wirksam zu werden.</span><span class="sxs-lookup"><span data-stu-id="3aef6-312">This setting may require a few minutes to take effect.</span></span> 
    
4. <span data-ttu-id="3aef6-313">Optional: Aufheben der Blockierung des vorhandenen e-Mail-Servers</span><span class="sxs-lookup"><span data-stu-id="3aef6-313">Optionally, unblock the existing email server</span></span>
    
    1. <span data-ttu-id="3aef6-314">Office 365 verwendet Exchange Online Protection (EoP) zum Schutz vor Spam.</span><span class="sxs-lookup"><span data-stu-id="3aef6-314">Office 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="3aef6-315">Wenn EoP eine große Menge an Spam erkennt, die von Ihrem aktuellen e-Mail-Server weitergeleitet wird, kann dies dazu führen, dass die Weiterleitung möglicherweise nicht mehr funktioniert.</span><span class="sxs-lookup"><span data-stu-id="3aef6-315">If EOP detects a high volume of spam being forwarded by your current mail server, it may block it, which would prevent forwarding from working.</span></span> <span data-ttu-id="3aef6-316">Wenn Sie mit dem Spam Schutz vertraut sind, den Ihr anderer e-Mail-Anbieter verwendet, können Sie den Server in Office 365 Whitelisten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-316">If you are confident with the spam protection your other email provider uses, you can whitelist their server in Office 365.</span></span> <span data-ttu-id="3aef6-317">Auf diese Weise können jedoch auch alle Spam-Mails, die über den ursprünglichen Server eingehen, in die Office 365 Postfächer gelangen, und Sie können nicht auswerten, wie gut Office 365 Spam verhindert.</span><span class="sxs-lookup"><span data-stu-id="3aef6-317">However, this will also allow any spam that arrives through your original server to come through to the Office 365 mailboxes, and you won't be able to evaluate how well Office 365 prevents spam.</span></span>
    
    2. <span data-ttu-id="3aef6-318">Wechseln Sie zu Exchange Admin Center (EAC).</span><span class="sxs-lookup"><span data-stu-id="3aef6-318">Go to Exchange admin center (EAC).</span></span>
        
    3. <span data-ttu-id="3aef6-319">Wählen Sie in der Exchange-Verwaltungskonsole **Schutz**aus, und wählen Sie **Verbindungsfilter**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-319">In EAC, select **Protection**, and then select **Connection filter**.</span></span> 
        
    4. <span data-ttu-id="3aef6-320">Wählen **+** Sie in der **Liste der zugelassenen IP**-Adressen die IP-Adresse des e-Mail-Servers aus, die Sie von Ihrem aktuellen e-Mail-Anbieter erhalten können.</span><span class="sxs-lookup"><span data-stu-id="3aef6-320">In the **IP Allow list**, select **+**, and add the mail server IP address that you can get from your current email provider.</span></span> 
    
5. <span data-ttu-id="3aef6-321">Erstellen von Benutzerkonten und Festlegen der primären Adresse (Reply-to)</span><span class="sxs-lookup"><span data-stu-id="3aef6-321">Create user accounts and set the primary (reply-to) address</span></span>
    
    1. <span data-ttu-id="3aef6-322">Gehen Sie zum Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="3aef6-322">Go to the Microsoft 365 admin center.</span></span>
        
    2. <span data-ttu-id="3aef6-323">Wählen Sie in der linken Navigationsleiste **Benutzer** \> **aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-323">On the left navigation bar, select **Users** \> **Active Users**.</span></span> 
        
    3. <span data-ttu-id="3aef6-324">Erstellen Sie die Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-324">Create the user accounts.</span></span>
        
    4. <span data-ttu-id="3aef6-325">Wählen Sie für jedes Konto Select **+ (New)** aus, und füllen Sie die erforderlichen Informationen aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-325">For each account select **+ (New)**, and fill out the required information.</span></span> 
        
    5. <span data-ttu-id="3aef6-326">Damit die e-Mail-Adresse des Benutzers unverändert bleibt, sollte das Feld **Benutzername** exakt mit der vorhandenen e-Mail-Adresse des Benutzers identisch sein.</span><span class="sxs-lookup"><span data-stu-id="3aef6-326">To keep user's email the same as it is currently, the **User name** field should be exactly the same as the user's existing email address.</span></span> 
        
    6. <span data-ttu-id="3aef6-327">Wählen Sie neben Benutzername Ihren benutzerdefinierten Domänennamen aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-327">Next to User name, select your custom domain name from the drop-down list.</span></span>
        
    7. <span data-ttu-id="3aef6-328">Wählen Sie **Close** **Erstellen** \> aus.</span><span class="sxs-lookup"><span data-stu-id="3aef6-328">Select **Create** \> **Close**.</span></span> 
        
6. <span data-ttu-id="3aef6-329">Aktualisieren von DNS-Einträgen bei Ihrem DNS-Hostanbieter</span><span class="sxs-lookup"><span data-stu-id="3aef6-329">Update DNS records at your DNS hosting provider</span></span>
    
    1. <span data-ttu-id="3aef6-330">Melden Sie sich bei der Website Ihres DNS-Host Anbieters an, und folgen Sie den DNS- [Einträgen bei einem beliebigen DNS-Hostinganbieter für Office 365 Schritte](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="3aef6-330">Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="3aef6-331">**Nehmen Sie die folgenden Ausnahmen vor:**</span><span class="sxs-lookup"><span data-stu-id="3aef6-331">**Make the following exceptions:**</span></span>
    
        1. <span data-ttu-id="3aef6-332">Erstellen Sie keinen neuen MX-Eintrag, oder ändern Sie den vorhandenen MX-Eintrag nicht.</span><span class="sxs-lookup"><span data-stu-id="3aef6-332">Do not create a new MX record or change your existing MX record.</span></span>
            
        2. <span data-ttu-id="3aef6-333">Wenn Sie bereits einen SPF-Eintrag (Sender Policy Framework) für Ihren vorherigen e-Mail-Anbieter haben, fügen Sie dem aktuellen TXT-Eintrag einfach "include:SPF. Protection. Outlook. com" hinzu, anstatt einen neuen SPF (txt)-Eintrag für Exchange Online zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-333">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record.</span></span> <span data-ttu-id="3aef6-334">Beispiel: "v = spf1 MX include:adatum. com include:SPF. Protection. Outlook. com ~ all".</span><span class="sxs-lookup"><span data-stu-id="3aef6-334">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>
            
        3. <span data-ttu-id="3aef6-335">Wenn Sie noch keinen SPF-Eintrag haben, ändern Sie den von Office 365 empfohlenen, um die Domäne für Ihren aktuellen e-Mail-Anbieter sowie SPF.Protection.Outlook.com hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3aef6-335">If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com.</span></span> <span data-ttu-id="3aef6-336">Dadurch werden ausgehende Nachrichten von beiden e-Mail-Systemen autorisiert.</span><span class="sxs-lookup"><span data-stu-id="3aef6-336">This authorizes outgoing messages from both email systems.</span></span>
            
7. <span data-ttu-id="3aef6-337">Einrichten der e-Mail-Weiterleitung bei Ihrem aktuellen Anbieter</span><span class="sxs-lookup"><span data-stu-id="3aef6-337">Set up email forwarding at your current provider</span></span>
    
    1. <span data-ttu-id="3aef6-338">Richten Sie bei Ihrem aktuellen e-Mail-Anbieter die Weiterleitung für Ihre Benutzer-e-Mail-Konten auf Ihre onmicrosoft.com-Domäne ein:</span><span class="sxs-lookup"><span data-stu-id="3aef6-338">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>
        
    2. <span data-ttu-id="3aef6-339">Das Postfach von Benutzer A sollte an UserA@yourcompany.onmicrosoft.com weitergeleitet werden</span><span class="sxs-lookup"><span data-stu-id="3aef6-339">User A's mailbox should forward to usera@yourcompany.onmicrosoft.com</span></span>
        
    3. <span data-ttu-id="3aef6-340">Postfach des Benutzers B sollte an UserB@yourcompany.onmicrosoft.com weitergeleitet werden</span><span class="sxs-lookup"><span data-stu-id="3aef6-340">User B's mailbox should forward to userb@yourcompany.onmicrosoft.com</span></span>
        
    4. <span data-ttu-id="3aef6-341">Wenn Sie diesen Schritt ausführen:</span><span class="sxs-lookup"><span data-stu-id="3aef6-341">When you complete this step:</span></span>
        
    5. <span data-ttu-id="3aef6-342">Alle e-Mails, die an UserA@yourcompany.com und UserB@yourcompany.com gesendet werden, stehen in Office 365 zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3aef6-342">All mail sent to usera@yourcompany.com and userb@yourcompany.com will be available in Office 365.</span></span>
    
    6. <span data-ttu-id="3aef6-343">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="3aef6-343">Notes:</span></span>
        
        - <span data-ttu-id="3aef6-344">Wenden Sie sich an Ihren aktuellen e-Mail-Anbieter, um die genauen Schritte zum Einrichten der Weiterleitung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3aef6-344">Contact your current email provider for the exact steps for setting up forwarding.</span></span>
            
        - <span data-ttu-id="3aef6-345">Sie müssen keine Kopie der Nachrichten beim aktuellen e-Mail-Anbieter aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="3aef6-345">You don't need to keep a copy of messages at the current email provider.</span></span>
            
        - <span data-ttu-id="3aef6-346">Die meisten Anbieter senden e-Mails, die die Antwort-an-Adresse des Absenders hinterlassen, intakt, sodass Antworten an den ursprünglichen Absender gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="3aef6-346">Most providers forward email leaving the Reply-to address of the sender intact, so that replies go to the original sender.</span></span>
    
8. <span data-ttu-id="3aef6-347">Testen der Nachrichtenübermittlung</span><span class="sxs-lookup"><span data-stu-id="3aef6-347">Test mail flow</span></span>
    
    1. <span data-ttu-id="3aef6-348">Melden Sie sich bei Outlook Web App mit den Anmeldeinformationen von Benutzer A an.</span><span class="sxs-lookup"><span data-stu-id="3aef6-348">Sign in to Outlook Web App using User A's credentials.</span></span>
        
    2. <span data-ttu-id="3aef6-349">Führen Sie die folgenden Tests aus:</span><span class="sxs-lookup"><span data-stu-id="3aef6-349">Perform the following tests:</span></span>
        
    3. <span data-ttu-id="3aef6-350">Testen Sie lokale Office 365 e-Mail.</span><span class="sxs-lookup"><span data-stu-id="3aef6-350">Test local Office 365 email.</span></span> <span data-ttu-id="3aef6-351">Senden Sie beispielsweise eine e-Mail an Benutzer B. Diese e-Mail sollte sofort zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3aef6-351">For example, send an email to User B. This email should be delivered immediately.</span></span> <span data-ttu-id="3aef6-352">In diesem Szenario wird die Nachricht nicht an das Postfach des Benutzers B auf dem ursprünglichen Server weitergeleitet, da Office 365 das Postfach als lokal betrachtet.</span><span class="sxs-lookup"><span data-stu-id="3aef6-352">In this scenario, the message will not be routed to User B's mailbox on your original server because Office 365 sees the mailbox as being local.</span></span>
        
    4. <span data-ttu-id="3aef6-353">Testen Sie e-Mails an Personen, die sich im anderen e-Mail-System befinden.</span><span class="sxs-lookup"><span data-stu-id="3aef6-353">Test email to someone who's on the other email system.</span></span> <span data-ttu-id="3aef6-354">Senden Sie beispielsweise eine e-Mail an den Benutzer C. Diese e-Mail sollte an das Postfach des Benutzers C auf dem ursprünglichen e-Mail-Server übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="3aef6-354">For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.</span></span>
        
    5. <span data-ttu-id="3aef6-355">Überprüfen Sie von einem externen Konto oder aus dem e-Mail-Konto eines Mitarbeiters im anderen e-Mail-System, dass die Weiterleitung ordnungsgemäß auf dem anderen e-Mail-System eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="3aef6-355">From an outside account, or from an employee's email account on the other email system, verify that forwarding is set up properly on the other email system.</span></span> <span data-ttu-id="3aef6-356">Senden Sie beispielsweise aus dem Gründungs-Server Konto von Benutzer C oder einem Hotmail-Konto Benutzer eine e-Mail, und vergewissern Sie sich, dass Sie im Office 365 Postfach von Benutzer a eintrifft.</span><span class="sxs-lookup"><span data-stu-id="3aef6-356">For example, from User C's origninal server account or a Hotmail account, send User A an email and verify that it arrives in User A's Office 365 mailbox.</span></span>
        
9. <span data-ttu-id="3aef6-357">Postfachinhalt migrieren</span><span class="sxs-lookup"><span data-stu-id="3aef6-357">Move mailbox contents</span></span>
    
    1. <span data-ttu-id="3aef6-358">Da sich nur zwei Benutzer bewegen müssen und Benutzer a und Benutzer B beide Outlook bereits verwenden, kann die e-Mail-Nachricht durch Öffnen der alten verschoben werden. PST-Datei im neuen Outlook-Profil und Kopieren der Nachrichten, Kalenderelemente, Kontakte usw. wie unter Importieren von Outlook-Elementen aus einer Outlook-Datendatei (PST) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3aef6-358">Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst).</span></span> <span data-ttu-id="3aef6-359">Nachdem die Elemente in den richtigen Speicherorten im Office 365 Postfach organisiert wurden, können alle auf alle Geräte zugegriffen werden, und zwar überall.</span><span class="sxs-lookup"><span data-stu-id="3aef6-359">Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.</span></span>
        
    2. <span data-ttu-id="3aef6-360">Wenn mehr Postfächer beteiligt sind oder wenn die Mitarbeiter nicht bereits Outlook verwenden, können Sie die im Exchange Admin Center verfügbaren Migrationstools verwenden.</span><span class="sxs-lookup"><span data-stu-id="3aef6-360">When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="3aef6-361">Wechseln Sie zunächst zu Exchange Admin Center, und befolgen Sie die Anweisungen unter Migrieren von e-Mails von einem IMAP-Server zu Exchange Online Postfächern.</span><span class="sxs-lookup"><span data-stu-id="3aef6-361">To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.</span></span>
    
