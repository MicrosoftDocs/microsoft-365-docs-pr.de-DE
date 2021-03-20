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
ms.openlocfilehash: 30bce7dd207532c441fdfaf572add44baec16d8d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914270"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="b0826-104">Hinzufügen einer Domäne zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0826-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b0826-105">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="b0826-105">The admin center is changing.</span></span> <span data-ttu-id="b0826-106">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="b0826-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="b0826-107">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="b0826-107">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="b0826-108">*Um Domänen hinzuzufügen, zu ändern oder zu entfernen, **müssen** Sie ein **globaler Administrator** eines [Geschäfts- oder Unternehmensplans](https://products.office.com/business/office) sein. Diese Änderungen betreffen den gesamten Mandanten. *Benutzerdefinierte Administratoren* oder *reguläre Benutzer* können diese Änderungen nicht vornehmen.*</span><span class="sxs-lookup"><span data-stu-id="b0826-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="b0826-109">Führen Sie die folgenden Schritte aus, um eine Domäne hinzuzufügen, einzurichten oder die Einrichtung einer Domäne fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="b0826-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b0826-110">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="b0826-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="b0826-111">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="b0826-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b0826-112">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="b0826-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="b0826-113">Wechseln Sie zur Seite **Einstellungen** > **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="b0826-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="b0826-114">Wählen Sie **Domäne hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="b0826-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="b0826-115">Geben Sie den Namen der Domäne ein, die Sie hinzufügen möchten, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="b0826-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="b0826-116">Wählen Sie aus, wie Sie überprüfen möchten, ob Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="b0826-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="b0826-117">Wenn Ihre Domänenregistrierungsstelle [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365)verwendet, [wird](../get-help-with-domains/domain-connect.md) Microsoft Ihre Datensätze automatisch einrichten, indem Sie sich bei Ihrer Registrierungsstelle anmelden und die Verbindung zu Microsoft 365 bestätigen.</span><span class="sxs-lookup"><span data-stu-id="b0826-117">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="b0826-118">Sie werden an das Admin Center zurückgegeben, und Microsoft überprüft dann automatisch Ihre Domäne.</span><span class="sxs-lookup"><span data-stu-id="b0826-118">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="b0826-119">Sie können einen TXT-Eintrag zur Überprüfung Ihrer Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0826-119">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="b0826-120">Wählen Sie dies und dann **Weiter** aus, um Anleitungen dazu anzuzeigen, wie Sie diesen DNS-Eintrag zur Website Ihrer Registrierungsstelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b0826-120">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="b0826-121">Nachdem Sie den Eintrag hinzugefügt haben, kann die Überprüfung bis zu 30 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="b0826-121">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="b0826-122">Sie können der Website Ihrer Domäne eine Textdatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b0826-122">You can add a text file to your domain's website.</span></span> <span data-ttu-id="b0826-123">Wählen Sie die TXT-Datei aus dem Setup-Assistenten aus, und laden Sie sie dann in den Ordner der obersten Ebene Ihrer Website hoch.</span><span class="sxs-lookup"><span data-stu-id="b0826-123">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="b0826-124">Der Pfad zur Datei sollte ähnlich aussehen wie: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="b0826-124">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="b0826-125">Wir bestätigen, dass Sie DerEnt der Domäne sind, indem wir die Datei auf Ihrer Website suchen.</span><span class="sxs-lookup"><span data-stu-id="b0826-125">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="b0826-126">Wählen Sie aus, wie Sie die für die Verwendung Ihrer Domäne von Microsoft erforderlichen DNS-Änderungen vornehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="b0826-126">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="b0826-127">Wählen **Sie Hinzufügen der DNS-Einträge** für mich aus, wenn Ihre Registrierungsstelle Domain [Connect](#domain-connect-registrars-integrating-with-microsoft-365)unterstützt, und [Microsoft](../get-help-with-domains/domain-connect.md) wird Ihre Einträge automatisch einrichten, indem Sie sich bei Ihrer Registrierungsstelle anmelden und die Verbindung zu Microsoft 365 bestätigen.</span><span class="sxs-lookup"><span data-stu-id="b0826-127">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="b0826-128">Wählen **Sie I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span><span class="sxs-lookup"><span data-stu-id="b0826-128">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="b0826-129">**Wählen Sie diese Option aus, wenn Sie genau wissen, was Sie tun.**</span><span class="sxs-lookup"><span data-stu-id="b0826-129">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="b0826-130">Wenn Sie selbst *DNS-Einträge*  hinzufügen möchten, wählen Sie **Weiter** aus, und Es wird eine Seite mit allen Datensätzen angezeigt, die Sie zur Registrierungsstellenwebsite hinzufügen müssen, um Ihre Domäne einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="b0826-130">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="b0826-131">Wenn das Portal Ihre Registrierungsstelle nicht erkennt, können Sie [diesen allgemeinen Anleitungen folgen](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="b0826-131">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="b0826-132">Suchen Sie in der Liste der [hostspezifischen Anweisungen](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) Ihren Host, und führen Sie die Schritte zum Hinzufügen aller benötigten Datensätze aus.</span><span class="sxs-lookup"><span data-stu-id="b0826-132">Check our list of [host-specific instructions](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="b0826-133">Wenn Sie den DNS-Hostinganbieter oder die Domänenregistrierungsstelle für Ihre Domäne nicht kennen, lesen Sie [Finden Ihrer Domänenregistrierungsstelle oder Ihres DNS-Hostinganbieters](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="b0826-133">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="b0826-134">Wenn Sie später warten möchten, deaktivieren Sie entweder die Auswahl aller Dienste, und klicken Sie auf **Weiter**, oder wählen Sie im vorherigen Schritt domänenverbindung die Option **Weitere Optionen** aus, und wählen Sie diese option für den Moment **überspringen aus.**</span><span class="sxs-lookup"><span data-stu-id="b0826-134">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="b0826-135">Wählen Sie **Fertig stellen** aus. Sie haben es geschafft!</span><span class="sxs-lookup"><span data-stu-id="b0826-135">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="b0826-136">Hinzufügen oder Bearbeiten von benutzerdefinierten DNS-Einträgen</span><span class="sxs-lookup"><span data-stu-id="b0826-136">Add or edit custom DNS records</span></span>

<span data-ttu-id="b0826-137">Führen Sie die folgenden Schritte aus, um einen benutzerdefinierten Datensatz für eine Website oder einen Drittanbieterdienst hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b0826-137">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="b0826-138">Melden Sie sich beim Microsoft Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> an.</span><span class="sxs-lookup"><span data-stu-id="b0826-138">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="b0826-139">Wechseln Sie zur Seite **Einstellungen**  > **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="b0826-139">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="b0826-140">Wählen Sie auf der Seite **Domänen** eine Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="b0826-140">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="b0826-141">Wählen **Sie unter #A0** **benutzerdefinierte Datensätze aus.** wählen Sie dann **Neuer benutzerdefinierter Datensatz aus.**</span><span class="sxs-lookup"><span data-stu-id="b0826-141">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="b0826-142">Wählen Sie den Typ des DNS-Eintrags aus, den Sie hinzufügen möchten, und geben Sie die Informationen für den neuen Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="b0826-142">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="b0826-143">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="b0826-143">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="b0826-144">Registrierungsstellen mit Domänen verbinden</span><span class="sxs-lookup"><span data-stu-id="b0826-144">Registrars with Domain Connect</span></span>

<span data-ttu-id="b0826-145">[Domain](https://www.domainconnect.org/) Connect-aktivierte Registrierungsstellen ermöglicht es Ihnen, Ihre Domäne in einem Drei-Schritt-Prozess, der Minuten dauert, zu Microsoft 365 hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b0826-145">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="b0826-146">Im Assistenten bestätigen wir nur, dass Sie der Domänenname sind, und richten dann automatisch die Datensätze Ihrer Domäne ein, damit E-Mails an Microsoft 365 und andere Microsoft 365-Dienste wie Teams mit Ihrer Domäne funktionieren.</span><span class="sxs-lookup"><span data-stu-id="b0826-146">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b0826-147">Stellen Sie sicher, dass Sie alle Popupblocker in Ihrem Browser deaktivieren, bevor Sie den Setup-Assistenten starten.</span><span class="sxs-lookup"><span data-stu-id="b0826-147">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="b0826-148">Integration von Domänen-Connect-Registrierungsstellen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0826-148">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="b0826-149">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="b0826-149">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="b0826-150">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="b0826-150">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="b0826-151">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="b0826-151">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="b0826-152">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="b0826-152">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="b0826-153">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="b0826-153">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="b0826-154">Plesk</span><span class="sxs-lookup"><span data-stu-id="b0826-154">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="b0826-155">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="b0826-155">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="b0826-156">SecureServer oder WildWestDomains (GoDaddy-Vertriebspartner, die SecureServer-DNS-Hosting verwenden)</span><span class="sxs-lookup"><span data-stu-id="b0826-156">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="b0826-157">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="b0826-157">Examples:</span></span>
        - [<span data-ttu-id="b0826-158">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="b0826-158">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="b0826-159">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="b0826-159">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="b0826-160">Was geschieht mit meiner E-Mail und Website?</span><span class="sxs-lookup"><span data-stu-id="b0826-160">What happens to my email and website?</span></span>

<span data-ttu-id="b0826-161">Nachdem Sie das Setup abgeschlossen haben, wird der MX-Eintrag für Ihre Domäne auf Microsoft 365 aktualisiert, und alle E-Mails für Ihre Domäne werden an Microsoft 365 gesendet.</span><span class="sxs-lookup"><span data-stu-id="b0826-161">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="b0826-162">Stellen Sie sicher, dass Sie Benutzer hinzugefügt und Postfächer in Microsoft 365 für alle Benutzer eingerichtet haben, die E-Mails in Ihrer Domäne erhalten!</span><span class="sxs-lookup"><span data-stu-id="b0826-162">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="b0826-163">Wenn Sie über eine Website verfügen, die Sie für Ihr Unternehmen verwenden, funktioniert sie weiterhin wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="b0826-163">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="b0826-164">Die Schritte zum Einrichten von Domänen verbinden wirken sich nicht auf Ihre Website aus.</span><span class="sxs-lookup"><span data-stu-id="b0826-164">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b0826-165">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="b0826-165">Related articles</span></span>

[<span data-ttu-id="b0826-166">Häufig gestellte Fragen zu Domänen</span><span class="sxs-lookup"><span data-stu-id="b0826-166">Domains FAQ</span></span>](domains-faq.yml)

[<span data-ttu-id="b0826-167">Was ist eine Domäne?</span><span class="sxs-lookup"><span data-stu-id="b0826-167">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="b0826-168">Erwerben eines Domänennamens in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0826-168">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="b0826-169">Einrichten Ihrer Domäne (hostspezifische Anweisungen)</span><span class="sxs-lookup"><span data-stu-id="b0826-169">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)