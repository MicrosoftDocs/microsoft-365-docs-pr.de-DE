---
title: Hinzufügen einer Domäne zu Office 365
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
ms.openlocfilehash: 336e6ee78d7020d73c7e00f639e8f1e1b20c62cd
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222339"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="6c0d7-104">Hinzufügen einer Domäne zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6c0d7-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6c0d7-105">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-105">The admin center is changing.</span></span> <span data-ttu-id="6c0d7-106">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="6c0d7-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="6c0d7-107">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="6c0d7-108">*Um Domänen hinzuzufügen, zu ändern oder zu entfernen, **müssen** Sie ein **globaler Administrator** eines [Geschäfts- oder Unternehmensplans](https://products.office.com/business/office) sein. Diese Änderungen betreffen den gesamten Mandanten. *Benutzerdefinierte Administratoren* oder *reguläre Benutzer* können diese Änderungen nicht vornehmen.*</span><span class="sxs-lookup"><span data-stu-id="6c0d7-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="6c0d7-109">Führen Sie die folgenden Schritte aus, um eine Domäne hinzuzufügen, einzurichten oder die Einrichtung einer Domäne fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6c0d7-110">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="6c0d7-111">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6c0d7-112">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="6c0d7-113">Wechseln Sie zur Seite **Setup**  >  **Domänen** .</span><span class="sxs-lookup"><span data-stu-id="6c0d7-113">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="6c0d7-114">Wählen Sie **Domäne hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="6c0d7-115">Geben Sie den Namen der Domäne ein, die Sie hinzufügen möchten, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="6c0d7-116">Wählen Sie aus, wie Sie überprüfen möchten, ob Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="6c0d7-117">Wenn Ihre Domäne bei GoDaddy oder 1 1 registriert ist &amp; , wählen Sie weiter **Anmelden**aus,  >  **Next** und Microsoft [wird Ihre Einträge automatisch einrichten](../get-help-with-domains/domain-connect.md).</span><span class="sxs-lookup"><span data-stu-id="6c0d7-117">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="6c0d7-118">Sie können auch eine E-Mail mit einem Prüfcode an den registrierten Kontakt für die Domäne senden lassen.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-118">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="6c0d7-119">Wenn Sie diese E-Mail nicht erkennen oder keinen Zugriff darauf haben, können Sie die dritte Option verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-119">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="6c0d7-120">Sie können einen TXT-Eintrag zur Überprüfung Ihrer Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-120">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="6c0d7-121">Wählen Sie dies und dann **Weiter** aus, um Anleitungen dazu anzuzeigen, wie Sie diesen DNS-Eintrag zur Website Ihrer Registrierungsstelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-121">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="6c0d7-122">Nachdem Sie den Eintrag hinzugefügt haben, kann die Überprüfung bis zu 30 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-122">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="6c0d7-123">Wählen Sie aus, wie Sie die erforderlichen DNS-Änderungen vornehmen möchten, damit Office Ihre Domäne verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-123">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="6c0d7-124">Wählen Sie **DNS-Einträge für mich hinzufügen** aus, wenn Office Ihr DNS automatisch konfigurieren soll.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-124">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="6c0d7-125">Wählen Sie **Ich füge die DNS-Einträge selbst hinzu** aus, wenn Sie nur bestimmte Office 365-Dienste an Ihre Domäne anfügen oder diesen Schritt zunächst überspringen und erst zu einem späteren Zeitpunkt ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-125">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="6c0d7-126">**Wählen Sie diese Option aus, wenn Sie genau wissen, was Sie tun.**</span><span class="sxs-lookup"><span data-stu-id="6c0d7-126">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="6c0d7-127">Wenn Sie ausgewählt haben, dass Sie *DNS-Einträge selbst hinzufügen* möchten, wählen Sie **Weiter** aus. Anschließend wird eine Seite mit allen Einträgen angezeigt, die Sie zur Website Ihrer Registrierungsstelle hinzufügen müssen, um Ihre Domäne einzurichten.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-127">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="6c0d7-128">Wenn das Portal Ihre Registrierungsstelle nicht erkennt, können Sie [diesen allgemeinen Anleitungen folgen](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="6c0d7-128">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="6c0d7-129">Suchen Sie in der Liste der [hostspezifischen Anweisungen](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) Ihren Host, und führen Sie die Schritte zum Hinzufügen aller benötigten Datensätze aus.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-129">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="6c0d7-130">Wenn Sie den DNS-Hostinganbieter oder die Domänenregistrierungsstelle für Ihre Domäne nicht kennen, lesen Sie [Finden Ihrer Domänenregistrierungsstelle oder Ihres DNS-Hostinganbieters](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="6c0d7-130">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="6c0d7-131">Wenn Sie auf einen späteren Zeitpunkt warten möchten, scrollen Sie bis ans Ende, und wählen Sie **Diesen Schritt überspringen** aus.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-131">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="6c0d7-132">Wählen Sie **Fertig stellen** aus. Sie haben es geschafft!</span><span class="sxs-lookup"><span data-stu-id="6c0d7-132">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="6c0d7-133">Hinzufügen oder Bearbeiten von benutzerdefinierten DNS-Einträgen</span><span class="sxs-lookup"><span data-stu-id="6c0d7-133">Add or edit custom DNS records</span></span>

<span data-ttu-id="6c0d7-134">Führen Sie die folgenden Schritte aus, um einen benutzerdefinierten Datensatz für eine Website oder einen Drittanbieterdienst hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-134">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="6c0d7-135">Melden Sie sich beim Microsoft Admin Center an <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="6c0d7-135">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="6c0d7-136">Wechseln Sie zur Seite **Einstellungen**  > **Domänen**.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-136">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="6c0d7-137">Wählen Sie auf der Seite **Domänen** eine Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-137">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="6c0d7-138">Wählen Sie unter **DNS-Einstellungen**die Option **Benutzerdefinierte Datensätze**aus. Wählen Sie dann **neuer benutzerdefinierter Datensatz**aus.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-138">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="6c0d7-139">Wählen Sie den Typ des DNS-Eintrags aus, den Sie hinzufügen möchten, und geben Sie die Informationen für den neuen Datensatz ein.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-139">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="6c0d7-140">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-140">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="6c0d7-141">Registrierungsstellen mit Domäne Connect</span><span class="sxs-lookup"><span data-stu-id="6c0d7-141">Registrars with Domain Connect</span></span>

<span data-ttu-id="6c0d7-142">Mit [Domänen Verbindungs](https://www.domainconnect.org/) fähigen Registrierungsstellen können Sie Ihre Domäne in einem dreistufigen Prozess, der Minuten dauert, zu Microsoft 365 hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-142">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="6c0d7-143">Im Assistenten bestätigen wir lediglich, dass Sie die Domäne besitzen und dann automatisch die Datensätze Ihrer Domäne einrichten, sodass e-Mails an Microsoft 365 und andere Microsoft 365-Dienste wie Teams mit Ihrer Domäne arbeiten.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-143">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c0d7-144">Stellen Sie sicher, dass Sie alle Popupblocker in Ihrem Browser deaktivieren, bevor Sie den Setup-Assistenten starten.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-144">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="6c0d7-145">Domänen Verbindungs Registrierungsstellen, die in Microsoft 365 integriert sind</span><span class="sxs-lookup"><span data-stu-id="6c0d7-145">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="6c0d7-146">1 &amp; 1 Ionos</span><span class="sxs-lookup"><span data-stu-id="6c0d7-146">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="6c0d7-147">123reg wußte</span><span class="sxs-lookup"><span data-stu-id="6c0d7-147">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="6c0d7-148">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="6c0d7-148">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="6c0d7-149">WordPress</span><span class="sxs-lookup"><span data-stu-id="6c0d7-149">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="6c0d7-150">Plesk</span><span class="sxs-lookup"><span data-stu-id="6c0d7-150">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="6c0d7-151">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="6c0d7-151">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="6c0d7-152">SecureServer oder WildWestDomains (GoDaddy Reseller mit SecureServer DNS-Hosting)</span><span class="sxs-lookup"><span data-stu-id="6c0d7-152">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="6c0d7-153">Maddog-Domänen</span><span class="sxs-lookup"><span data-stu-id="6c0d7-153">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="6c0d7-154">CheapNames</span><span class="sxs-lookup"><span data-stu-id="6c0d7-154">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="6c0d7-155">Was geschieht mit meiner e-Mail und Website?</span><span class="sxs-lookup"><span data-stu-id="6c0d7-155">What happens to my email and website?</span></span>

<span data-ttu-id="6c0d7-156">Nachdem Sie das Setup abgeschlossen haben, wird der MX-Eintrag für Ihre Domäne so aktualisiert, dass er auf Microsoft 365 verweist, und alle e-Mails für Ihre Domäne beginnen mit Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-156">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="6c0d7-157">Stellen Sie sicher, dass Sie Benutzer hinzugefügt haben, und richten Sie in Office 365 Postfächer für jeden ein, der e-Mails in Ihrer Domäne erhält!</span><span class="sxs-lookup"><span data-stu-id="6c0d7-157">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="6c0d7-158">Wenn Sie über eine Website verfügen, die Sie für Ihr Unternehmen verwenden, funktioniert sie weiterhin wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-158">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="6c0d7-159">Die Schritte zum Einrichten von Domänen Verbindungen wirken sich nicht auf Ihre Website aus.</span><span class="sxs-lookup"><span data-stu-id="6c0d7-159">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6c0d7-160">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="6c0d7-160">Related articles</span></span>

[<span data-ttu-id="6c0d7-161">Häufig gestellte Fragen zu Domänen</span><span class="sxs-lookup"><span data-stu-id="6c0d7-161">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="6c0d7-162">Was ist eine Domäne?</span><span class="sxs-lookup"><span data-stu-id="6c0d7-162">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="6c0d7-163">Erwerben eines Domänennamens in Office 365</span><span class="sxs-lookup"><span data-stu-id="6c0d7-163">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="6c0d7-164">Einrichten Ihrer Domäne (hostspezifische Anweisungen)</span><span class="sxs-lookup"><span data-stu-id="6c0d7-164">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="6c0d7-165">Abrufen von Hilfe zu Domänen</span><span class="sxs-lookup"><span data-stu-id="6c0d7-165">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
