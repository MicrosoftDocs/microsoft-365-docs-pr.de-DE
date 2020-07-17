---
title: Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge bei einem beliebigen DNS-Hostinganbieter für Microsoft 365 erstellen.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: d3a9e3787afc30b33122edf91c1cf9e3dd84b847
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049666"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="36e22-103">Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="36e22-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="36e22-104">Wenn Sie eine Domäne bei einem Drittanbieter-Hostinganbieter gekauft haben, können Sie diese mit Microsoft 365 verbinden, indem Sie die DNS-Einträge im Konto Ihrer Registrierungsstelle aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="36e22-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="36e22-105">Am Ende dieser Schritte bleibt Ihre Domäne bei dem Host registriert, von dem Sie die Domäne gekauft haben. Microsoft 365 kann sie aber für E-Mail-Adressen (z. B. „Benutzer@IhreDomäne.com“) und andere Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="36e22-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for you email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="36e22-106">Wenn Sie keine Domäne hinzufügen, verwenden Personen in Ihrer Organisation die Domäne „onmicrosoft.com“ für ihre E-Mail-Adressen, bis Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="36e22-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="36e22-107">Es ist wichtig, dass Sie Ihre Domäne hinzufügen, bevor Sie Benutzer hinzufügen, damit Sie diese nicht zweimal einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="36e22-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="36e22-108">[Lesen Sie in den die häufig gestellten Fragen (FAQ) zu Domänen nach](../setup/domains-faq.md), wenn Sie unten nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="36e22-108">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-record-to-verify-you-own-the-domain"></a><span data-ttu-id="36e22-109">Schritt 1: Hinzufügen eines TXT-Eintrags, um zu überprüfen, ob Sie die Domäne besitzen</span><span class="sxs-lookup"><span data-stu-id="36e22-109">Step 1: Add a TXT record to verify you own the domain</span></span>

<span data-ttu-id="36e22-110">Zunächst müssen Sie nachweisen, dass Sie der Besitzer der Domäne sind, die Sie Microsoft 365 hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="36e22-110">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="36e22-111">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com/) an, und wählen Sie **Alle anzeigen** > **Einstellungen** > **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="36e22-111">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="36e22-112">Melden Sie sich auf einer neuen Browserregisterkarte oder in einem neuen Browserfenster bei Ihrem DNS-Hostinganbieter an, und suchen Sie dann die Stelle, an der Sie Ihre DNS-Einstellungen verwalten (z. B. Zonendateieinstellungen, Domänen verwalten, Domänen-Manager, DNS-Manager).</span><span class="sxs-lookup"><span data-stu-id="36e22-112">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="36e22-113">Wechseln Sie zur Seite „DNS-Manager“ Ihres Anbieters, und fügen Sie den im Admin Center angegebenen TXT-Eintrag zu Ihrer Domäne hinzu.</span><span class="sxs-lookup"><span data-stu-id="36e22-113">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="36e22-114">Das Hinzufügen dieses Eintrags wirkt sich nicht auf Ihre bestehende E-Mail oder andere Dienste aus, und Sie können ihn bedenkenlos entfernen, sobald Ihre Domäne mit Microsoft 365 verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="36e22-114">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="36e22-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="36e22-115">Example:</span></span>
- <span data-ttu-id="36e22-116">TXT-Name: `@`</span><span class="sxs-lookup"><span data-stu-id="36e22-116">TXT Name: `@`</span></span>
- <span data-ttu-id="36e22-117">TXT-Wert: MS=ms######## (eindeutige ID aus dem Admin Center)</span><span class="sxs-lookup"><span data-stu-id="36e22-117">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="36e22-118">TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)</span><span class="sxs-lookup"><span data-stu-id="36e22-118">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="36e22-119">Speichern Sie den Eintrag, wechseln Sie zurück zum Admin Center, und wählen Sie **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="36e22-119">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="36e22-120">Normalerweise dauert es ungefähr 15 Minuten, bis Eintragsänderungen registriert werden, doch manchmal kann es auch länger dauern.</span><span class="sxs-lookup"><span data-stu-id="36e22-120">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="36e22-121">Gewähren Sie dem Vorgang etwas Zeit sowie ein paar Versuche, um die Änderung zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="36e22-121">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="36e22-122">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="36e22-122">When Microsoft finds the correct TXT record, your domain is verified.</span></span>


## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="36e22-123">Schritt 2: Hinzufügen von DNS-Einträgen zum Verbinden von Microsoft-Diensten</span><span class="sxs-lookup"><span data-stu-id="36e22-123">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="36e22-124">Melden Sie sich auf einer neuen Browserregisterkarte oder in einem neuen Browserfenster bei Ihrem DNS-Hostinganbieter an, und suchen Sie die Stelle, an der Sie Ihre DNS-Einstellungen verwalten (z. B. Zonendateieinstellungen, Domänen verwalten, Domänen-Manager, DNS-Manager).</span><span class="sxs-lookup"><span data-stu-id="36e22-124">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="36e22-125">Sie fügen mehrere unterschiedliche Typen von DNS-Einträgen hinzu, je nachdem, welche Dienste Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="36e22-125">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="36e22-126">Hinzufügen eines MX-Eintrags für E-Mail (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="36e22-126">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="36e22-127">**Bevor Sie beginnen:** Wenn Benutzer bereits über E-Mail-Adressen mit Ihrer Domäne verfügen (z. B. „Benutzer@IhreDomäne.com“), erstellen Sie deren Konten im Admin Center, bevor Sie Ihre MX-Einträge einrichten.</span><span class="sxs-lookup"><span data-stu-id="36e22-127">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="36e22-128">Auf diese Weise erhalten sie weiterhin E-Mail.</span><span class="sxs-lookup"><span data-stu-id="36e22-128">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="36e22-129">Nachdem Sie den MX-Eintrag Ihrer Domäne aktualisiert haben, treffen alle neuen E-Mails für jeden Benutzer Ihr Domäne in Microsoft 365 ein.</span><span class="sxs-lookup"><span data-stu-id="36e22-129">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="36e22-130">Alle E-Mails, die Sie bereits erhalten haben, bleiben so lange auf Ihrem aktuellen E-Mail-Host gespeichert, bis Sie die [Migration von E-Mails und Kontakten zu Microsoft 365](../setup/migrate-email-and-contacts-admin.md) beschließen.</span><span class="sxs-lookup"><span data-stu-id="36e22-130">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="36e22-131">Sie erhalten nun die Informationen zu dem MX-Eintrag vom Assistenten für die Domäneneinrichtung im Admin Center.</span><span class="sxs-lookup"><span data-stu-id="36e22-131">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="36e22-132">Fügen Sie auf der Website Ihres Hostinganbieters einen neuen MX-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="36e22-132">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="36e22-133">Stellen Sie sicher, dass die Felder auf die folgenden Werte festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="36e22-133">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="36e22-134">Eintragstyp: `MX`</span><span class="sxs-lookup"><span data-stu-id="36e22-134">Record Type: `MX`</span></span>
- <span data-ttu-id="36e22-135">Priorität: Legen Sie dies auf den höchsten verfügbaren Wert fest, in der Regel `0`.</span><span class="sxs-lookup"><span data-stu-id="36e22-135">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="36e22-136">Hostname: `@`</span><span class="sxs-lookup"><span data-stu-id="36e22-136">Host Name: `@`</span></span>
- <span data-ttu-id="36e22-137">Verweist auf die Adresse: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="36e22-137">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="36e22-138">TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)</span><span class="sxs-lookup"><span data-stu-id="36e22-138">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="36e22-139">Speichern Sie den Eintrag, und entfernen Sie dann alle anderen MX-Einträge.</span><span class="sxs-lookup"><span data-stu-id="36e22-139">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="36e22-140">Hinzufügen von CNAME-Einträgen zum Verbinden anderer Dienste (Teams, Exchange Online, AAD, MDM)</span><span class="sxs-lookup"><span data-stu-id="36e22-140">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="36e22-141">Sie erhalten nun die Informationen zu den CNAME-Einträgen vom Assistenten für die Domäneneinrichtung im Admin Center.</span><span class="sxs-lookup"><span data-stu-id="36e22-141">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="36e22-142">Fügen Sie auf der Website Ihres Hostinganbieters CNAME-Einträge für jeden Dienst hinzu, den Sie verbinden möchten.</span><span class="sxs-lookup"><span data-stu-id="36e22-142">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="36e22-143">Stellen Sie sicher, dass jedes der Felder auf die jeweiligen folgenden Werte festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="36e22-143">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="36e22-144">Eintragstyp: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="36e22-144">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="36e22-145">Host: Fügen Sie hier die Werte ein, die Sie aus dem Admin Center kopieren.</span><span class="sxs-lookup"><span data-stu-id="36e22-145">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="36e22-146">Verweist auf die Adresse: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="36e22-146">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="36e22-147">TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)</span><span class="sxs-lookup"><span data-stu-id="36e22-147">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="36e22-148">Hinzufügen oder Bearbeiten eines SPF TXT-Eintrags, um E-Mail-Spam zu verhindern (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="36e22-148">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="36e22-149">**Bevor Sie beginnen:** Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft 365 keinen neuen.</span><span class="sxs-lookup"><span data-stu-id="36e22-149">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="36e22-150">Fügen Sie stattdessen die erforderlichen Microsoft 365-Werte dem aktuellen Eintrag auf der Website Ihres Hostinganbieters hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="36e22-150">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="36e22-151">Bearbeiten Sie auf der Website Ihres Hostinganbieters den vorhandenen SPF-Eintrag, oder erstellen Sie einen neuen SPF-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="36e22-151">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="36e22-152">Stellen Sie sicher, dass die Felder auf die folgenden Werte festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="36e22-152">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="36e22-153">Eintragstyp: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="36e22-153">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="36e22-154">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="36e22-154">Host: `@`</span></span>
- <span data-ttu-id="36e22-155">TXT-Wert: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="36e22-155">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="36e22-156">TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)</span><span class="sxs-lookup"><span data-stu-id="36e22-156">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="36e22-157">Speichern Sie den Eintrag.</span><span class="sxs-lookup"><span data-stu-id="36e22-157">Save the record.</span></span>

<span data-ttu-id="36e22-158">Überprüfen Sie Ihren SPF-Eintrag, indem Sie eines dieser [SPF-Überprüfungstools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) verwenden.</span><span class="sxs-lookup"><span data-stu-id="36e22-158">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="36e22-159">SPF ist dafür vorgesehen, Spoofing möglichst zu verhindern, es gibt aber Spoofing-Techniken, vor denen SPF nicht schützen kann.</span><span class="sxs-lookup"><span data-stu-id="36e22-159">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="36e22-160">Zum Schutz vor diesen Techniken sollten Sie, nachdem Sie SPF eingerichtet haben, auch DKIM und DMARC für Microsoft 365 einrichten.</span><span class="sxs-lookup"><span data-stu-id="36e22-160">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="36e22-161">Um hiermit zu beginnen, lesen Sie [Verwenden von DKIM zur Überprüfung von ausgehenden E-Mails, die von Ihrer Domäne in Microsoft 365 gesendet wurden](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) und [Verwenden von DMARC zum Überprüfen von E-Mail in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="36e22-161">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="36e22-162">Hinzufügen von SRV-Einträgen für Kommunikationsdienste (Teams, Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="36e22-162">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="36e22-163">Fügen Sie auf der Website Ihres Hostinganbieters SRV-Einträge für jeden Dienst hinzu, den Sie verbinden möchten.</span><span class="sxs-lookup"><span data-stu-id="36e22-163">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="36e22-164">Stellen Sie sicher, dass jedes der Felder auf die jeweiligen folgenden Werte festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="36e22-164">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="36e22-165">Eintragstyp: `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="36e22-165">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="36e22-166">Name: `@`</span><span class="sxs-lookup"><span data-stu-id="36e22-166">Name: `@`</span></span>
- <span data-ttu-id="36e22-167">Ziel: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="36e22-167">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="36e22-168">Protokoll: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="36e22-168">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="36e22-169">Dienst: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="36e22-169">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="36e22-170">Priorität: `100`</span><span class="sxs-lookup"><span data-stu-id="36e22-170">Priority: `100`</span></span>
- <span data-ttu-id="36e22-171">Gewichtung: `1`</span><span class="sxs-lookup"><span data-stu-id="36e22-171">Weight: `1`</span></span>
- <span data-ttu-id="36e22-172">Port: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="36e22-172">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="36e22-173">TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)</span><span class="sxs-lookup"><span data-stu-id="36e22-173">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="36e22-174">Speichern Sie den Eintrag.</span><span class="sxs-lookup"><span data-stu-id="36e22-174">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="36e22-175">Einschränkungen und Problemumgehungen für SRV-Eintragsfelder</span><span class="sxs-lookup"><span data-stu-id="36e22-175">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="36e22-176">Einige Hostinganbieter richten Beschränkungen für Feldwerte in SRV-Einträgen ein.</span><span class="sxs-lookup"><span data-stu-id="36e22-176">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="36e22-177">Hier finden Sie einige gängige Problemumgehungen für diese Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="36e22-177">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="36e22-178">Name</span><span class="sxs-lookup"><span data-stu-id="36e22-178">Name</span></span>
<span data-ttu-id="36e22-179">Wenn Ihr Hostinganbieter die Einstellung dieses Felds auf **@** nicht zulässt, lassen Sie es leer.</span><span class="sxs-lookup"><span data-stu-id="36e22-179">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="36e22-180">Verwenden Sie diesen Ansatz *nur*, wenn Ihr Hostinganbieter über separate Felder für die Werte „Dienst“ und „Protokoll“ verfügt.</span><span class="sxs-lookup"><span data-stu-id="36e22-180">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="36e22-181">Andernfalls lesen Sie die Anmerkungen unten zu „Dienst“ und „Protokoll“.</span><span class="sxs-lookup"><span data-stu-id="36e22-181">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="36e22-182">„Dienst“ und „Protokoll“</span><span class="sxs-lookup"><span data-stu-id="36e22-182">Service and Protocol</span></span>
<span data-ttu-id="36e22-183">Wenn Ihr Hostinganbieter diese Felder für SRV-Einträge nicht bereitstellt, müssen Sie die Werte für **Dienst** und **Protokoll** im Feld **Name** des Eintrags angeben.</span><span class="sxs-lookup"><span data-stu-id="36e22-183">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="36e22-184">(Hinweis: Abhängig von Ihrem Hostinganbieter kann das Feld **Name** auch anders heißen, z. B: **Host**, **Hostname** oder **Subdomäne**). Um diese Werte hinzuzufügen, erstellen Sie eine einzelne Zeichenfolge und trennen die Werte durch einen Punkt.</span><span class="sxs-lookup"><span data-stu-id="36e22-184">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="36e22-185">Beispiel: `_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="36e22-185">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="36e22-186">„Priorität“, „Gewichtung“ und „Port“</span><span class="sxs-lookup"><span data-stu-id="36e22-186">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="36e22-187">Wenn Ihr Hostinganbieter diese Felder für SRV-Einträge nicht bereitstellt, müssen Sie sie im Feld **Ziel** des Eintrags angeben.</span><span class="sxs-lookup"><span data-stu-id="36e22-187">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="36e22-188">(Hinweis: Abhängig von Ihrem Hostinganbieter kann das Feld **Ziel** auch anders heißen, z. B.: **Inhalt**, **IP-Adresse** oder **Zielhost**.)</span><span class="sxs-lookup"><span data-stu-id="36e22-188">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="36e22-189">Um diese Werte hinzuzufügen, erstellen Sie eine einzelne Zeichenfolge, trennen die Werte durch Leerzeichen und lassen diese *manchmal mit einem Punkt enden* (wenden Sie sich an Ihren Anbieter, wenn Sie unsicher sind).</span><span class="sxs-lookup"><span data-stu-id="36e22-189">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="36e22-190">Die Werte müssen in dieser Reihenfolge eingegeben werden: „Priorität“, „Gewichtung“, „Port“, „Ziel“.</span><span class="sxs-lookup"><span data-stu-id="36e22-190">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="36e22-191">Beispiel 1: `100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="36e22-191">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="36e22-192">Beispiel 2: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="36e22-192">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>
