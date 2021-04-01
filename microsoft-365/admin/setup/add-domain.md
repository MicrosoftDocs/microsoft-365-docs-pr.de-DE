---
title: Hinzufügen einer Domäne zu Microsoft 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Fügen Sie Ihre Domäne zu Microsoft 365 im Microsoft 365 Admin Center hinzu, indem Sie einen DNS-Eintrag auf Ihrem DNS-Host hinzufügen. Der Setup-Assistent führt Sie nun durch den Vorgang.
ms.openlocfilehash: 747de5f61dc9fce53f82f52b65f701572a56f8d4
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470881"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="88e20-104">Hinzufügen einer Domäne zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="88e20-104">Add a domain to Microsoft 365</span></span>

 <span data-ttu-id="88e20-105">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="88e20-105">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="88e20-106">*Um Domänen hinzuzufügen, zu ändern oder zu entfernen, **müssen** Sie ein **globaler Administrator** eines [Geschäfts- oder Unternehmensplans](https://products.office.com/business/office) sein. Diese Änderungen betreffen den gesamten Mandanten. *Benutzerdefinierte Administratoren* oder *reguläre Benutzer* können diese Änderungen nicht vornehmen.*</span><span class="sxs-lookup"><span data-stu-id="88e20-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="88e20-107">Führen Sie die folgenden Schritte aus, um eine Domäne hinzuzufügen, einzurichten oder die Einrichtung einer Domäne fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="88e20-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="88e20-108">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="88e20-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="88e20-109">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="88e20-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="88e20-110">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="88e20-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="88e20-111">Wechseln Sie zur Seite **Einstellungen** > **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="88e20-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="88e20-112">Wählen Sie **Domäne hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="88e20-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="88e20-113">Geben Sie den Namen der Domäne ein, die Sie hinzufügen möchten, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="88e20-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="88e20-114">Wählen Sie aus, wie Sie überprüfen möchten, ob Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="88e20-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="88e20-115">Wenn Ihre Domänenregistrierungsstelle [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365)verwendet, [wird](../get-help-with-domains/domain-connect.md) Microsoft Ihre Datensätze automatisch einrichten, indem Sie sich bei Ihrer Registrierungsstelle anmelden und die Verbindung zu Microsoft 365 bestätigen.</span><span class="sxs-lookup"><span data-stu-id="88e20-115">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="88e20-116">Sie werden an das Admin Center zurückgegeben, und Microsoft überprüft dann automatisch Ihre Domäne.</span><span class="sxs-lookup"><span data-stu-id="88e20-116">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="88e20-117">Sie können einen TXT-Eintrag zur Überprüfung Ihrer Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="88e20-117">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="88e20-118">Wählen Sie dies und dann **Weiter** aus, um Anleitungen dazu anzuzeigen, wie Sie diesen DNS-Eintrag zur Website Ihrer Registrierungsstelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="88e20-118">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="88e20-119">Nachdem Sie den Eintrag hinzugefügt haben, kann die Überprüfung bis zu 30 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="88e20-119">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="88e20-120">Sie können der Website Ihrer Domäne eine Textdatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="88e20-120">You can add a text file to your domain's website.</span></span> <span data-ttu-id="88e20-121">Wählen Sie die TXT-Datei aus dem Setup-Assistenten aus, und laden Sie sie dann in den Ordner der obersten Ebene Ihrer Website hoch.</span><span class="sxs-lookup"><span data-stu-id="88e20-121">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="88e20-122">Der Pfad zur Datei sollte ähnlich aussehen wie: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="88e20-122">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="88e20-123">Wir bestätigen, dass Sie DerEnt der Domäne sind, indem wir die Datei auf Ihrer Website suchen.</span><span class="sxs-lookup"><span data-stu-id="88e20-123">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="88e20-124">Wählen Sie aus, wie Sie die für die Verwendung Ihrer Domäne von Microsoft erforderlichen DNS-Änderungen vornehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="88e20-124">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="88e20-125">Wählen **Sie Hinzufügen der DNS-Einträge** für mich aus, wenn Ihre Registrierungsstelle Domain [Connect](#domain-connect-registrars-integrating-with-microsoft-365)unterstützt, und [Microsoft](../get-help-with-domains/domain-connect.md) wird Ihre Einträge automatisch einrichten, indem Sie sich bei Ihrer Registrierungsstelle anmelden und die Verbindung zu Microsoft 365 bestätigen.</span><span class="sxs-lookup"><span data-stu-id="88e20-125">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="88e20-126">Wählen **Sie I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span><span class="sxs-lookup"><span data-stu-id="88e20-126">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="88e20-127">**Wählen Sie diese Option aus, wenn Sie genau wissen, was Sie tun.**</span><span class="sxs-lookup"><span data-stu-id="88e20-127">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="88e20-128">Wenn Sie selbst *DNS-Einträge*  hinzufügen möchten, wählen Sie **Weiter** aus, und Es wird eine Seite mit allen Datensätzen angezeigt, die Sie zur Registrierungsstellenwebsite hinzufügen müssen, um Ihre Domäne einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="88e20-128">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="88e20-129">Wenn das Portal Ihre Registrierungsstelle nicht erkennt, können Sie [diesen allgemeinen Anleitungen folgen](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="88e20-129">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="88e20-130">Suchen Sie in der Liste der [hostspezifischen Anweisungen](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) Ihren Host, und führen Sie die Schritte zum Hinzufügen aller benötigten Datensätze aus.</span><span class="sxs-lookup"><span data-stu-id="88e20-130">Check our list of [host-specific instructions](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="88e20-131">Wenn Sie den DNS-Hostinganbieter oder die Domänenregistrierungsstelle für Ihre Domäne nicht kennen, lesen Sie [Finden Ihrer Domänenregistrierungsstelle oder Ihres DNS-Hostinganbieters](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="88e20-131">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="88e20-132">Wenn Sie später warten möchten, deaktivieren Sie entweder die Auswahl aller Dienste, und klicken Sie auf **Weiter**, oder wählen Sie im vorherigen Schritt domänenverbindung die Option **Weitere Optionen** aus, und wählen Sie diese option für den Moment **überspringen aus.**</span><span class="sxs-lookup"><span data-stu-id="88e20-132">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="88e20-133">Wählen Sie **Fertig stellen** aus. Sie haben es geschafft!</span><span class="sxs-lookup"><span data-stu-id="88e20-133">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="88e20-134">Hinzufügen oder Bearbeiten von benutzerdefinierten DNS-Einträgen</span><span class="sxs-lookup"><span data-stu-id="88e20-134">Add or edit custom DNS records</span></span>

<span data-ttu-id="88e20-135">Führen Sie die folgenden Schritte aus, um einen benutzerdefinierten Datensatz für eine Website oder einen Drittanbieterdienst hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="88e20-135">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="88e20-136">Melden Sie sich beim Microsoft Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> an.</span><span class="sxs-lookup"><span data-stu-id="88e20-136">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="88e20-137">Wechseln Sie zur Seite **Einstellungen**  > **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="88e20-137">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="88e20-138">Wählen Sie auf der Seite **Domänen** eine Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="88e20-138">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="88e20-139">Wählen **Sie unter #A0** **benutzerdefinierte Datensätze aus.** wählen Sie dann **Neuer benutzerdefinierter Datensatz aus.**</span><span class="sxs-lookup"><span data-stu-id="88e20-139">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="88e20-140">Wählen Sie den Typ des DNS-Eintrags aus, den Sie hinzufügen möchten, und geben Sie die Informationen für den neuen Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="88e20-140">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="88e20-141">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="88e20-141">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="88e20-142">Registrierungsstellen mit Domänen verbinden</span><span class="sxs-lookup"><span data-stu-id="88e20-142">Registrars with Domain Connect</span></span>

<span data-ttu-id="88e20-143">[Domain](https://www.domainconnect.org/) Connect-aktivierte Registrierungsstellen ermöglicht es Ihnen, Ihre Domäne in einem Drei-Schritt-Prozess, der Minuten dauert, zu Microsoft 365 hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="88e20-143">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="88e20-144">Im Assistenten bestätigen wir nur, dass Sie der Domänenname sind, und richten dann automatisch die Datensätze Ihrer Domäne ein, damit E-Mails an Microsoft 365 und andere Microsoft 365-Dienste wie Teams mit Ihrer Domäne funktionieren.</span><span class="sxs-lookup"><span data-stu-id="88e20-144">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="88e20-145">Stellen Sie sicher, dass Sie alle Popupblocker in Ihrem Browser deaktivieren, bevor Sie den Setup-Assistenten starten.</span><span class="sxs-lookup"><span data-stu-id="88e20-145">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="88e20-146">Integration von Domänen-Connect-Registrierungsstellen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="88e20-146">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="88e20-147">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="88e20-147">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="88e20-148">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="88e20-148">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="88e20-149">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="88e20-149">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="88e20-150">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="88e20-150">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="88e20-151">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="88e20-151">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="88e20-152">Plesk</span><span class="sxs-lookup"><span data-stu-id="88e20-152">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="88e20-153">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="88e20-153">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="88e20-154">SecureServer oder WildWestDomains (GoDaddy-Vertriebspartner, die SecureServer-DNS-Hosting verwenden)</span><span class="sxs-lookup"><span data-stu-id="88e20-154">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="88e20-155">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="88e20-155">Examples:</span></span>
        - [<span data-ttu-id="88e20-156">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="88e20-156">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="88e20-157">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="88e20-157">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="88e20-158">Was geschieht mit meiner E-Mail und Website?</span><span class="sxs-lookup"><span data-stu-id="88e20-158">What happens to my email and website?</span></span>

<span data-ttu-id="88e20-159">Nachdem Sie das Setup abgeschlossen haben, wird der MX-Eintrag für Ihre Domäne auf Microsoft 365 aktualisiert, und alle E-Mails für Ihre Domäne werden an Microsoft 365 gesendet.</span><span class="sxs-lookup"><span data-stu-id="88e20-159">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="88e20-160">Stellen Sie sicher, dass Sie Benutzer hinzugefügt und Postfächer in Microsoft 365 für alle Benutzer eingerichtet haben, die E-Mails in Ihrer Domäne erhalten!</span><span class="sxs-lookup"><span data-stu-id="88e20-160">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="88e20-161">Wenn Sie über eine Website verfügen, die Sie für Ihr Unternehmen verwenden, funktioniert sie weiterhin wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="88e20-161">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="88e20-162">Die Schritte zum Einrichten von Domänen verbinden wirken sich nicht auf Ihre Website aus.</span><span class="sxs-lookup"><span data-stu-id="88e20-162">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="88e20-163">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="88e20-163">Related articles</span></span>

[<span data-ttu-id="88e20-164">Häufig gestellte Fragen zu Domänen</span><span class="sxs-lookup"><span data-stu-id="88e20-164">Domains FAQ</span></span>](domains-faq.yml)

[<span data-ttu-id="88e20-165">Was ist eine Domäne?</span><span class="sxs-lookup"><span data-stu-id="88e20-165">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="88e20-166">Erwerben eines Domänennamens in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="88e20-166">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="88e20-167">Einrichten Ihrer Domäne (hostspezifische Anweisungen)</span><span class="sxs-lookup"><span data-stu-id="88e20-167">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)