---
title: Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: Verbinden Sie eine Domäne bei einem beliebigen DNS-Hostinganbieter mit Microsoft 365, indem Sie Ihre Domäne überprüfen und die DNS-Einträge im Konto Ihrer Registrierungsstelle aktualisieren.
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
ms.openlocfilehash: 4b4c09ce6a4161c713490daef46157b5555e124b
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393919"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="b56bc-103">Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="b56bc-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="b56bc-104">Wenn Sie eine Domäne bei einem Drittanbieter-Hostinganbieter gekauft haben, können Sie diese mit Microsoft 365 verbinden, indem Sie die DNS-Einträge im Konto Ihrer Registrierungsstelle aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b56bc-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="b56bc-105">Am Ende dieser Schritte bleibt Ihre Domäne bei dem Host registriert, von dem Sie die Domäne gekauft haben. Microsoft 365 kann sie aber für E-Mail-Adressen (z. B. „Benutzer@IhreDomäne.com“) und andere Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="b56bc-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for your email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="b56bc-106">Wenn Sie keine Domäne hinzufügen, verwenden Personen in Ihrer Organisation die Domäne „onmicrosoft.com“ für ihre E-Mail-Adressen, bis Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="b56bc-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="b56bc-107">Es ist wichtig, dass Sie Ihre Domäne hinzufügen, bevor Sie Benutzer hinzufügen, damit Sie diese nicht zweimal einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="b56bc-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="b56bc-108">[Lesen Sie in den die häufig gestellten Fragen (FAQ) zu Domänen nach](../setup/domains-faq.yml), wenn Sie unten nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="b56bc-108">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a><span data-ttu-id="b56bc-109">Schritt 1: Fügen Sie einen TXT- oder MX-Eintrag hinzu, um den Besitz der Domäne zu verifizieren</span><span class="sxs-lookup"><span data-stu-id="b56bc-109">Step 1: Add a TXT or MX record to verify you own the domain</span></span>

### <a name="recommended-verify-with-a-txt-record"></a><span data-ttu-id="b56bc-110">Die Verifizierung anhand eines TXT-Eintrags wird empfohlen</span><span class="sxs-lookup"><span data-stu-id="b56bc-110">Recommended: Verify with a TXT record</span></span>

<span data-ttu-id="b56bc-111">Zunächst müssen Sie nachweisen, dass Sie der Besitzer der Domäne sind, die Sie Microsoft 365 hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="b56bc-111">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="b56bc-112">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com/) an, und wählen Sie **Alle anzeigen** > **Einstellungen** > **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="b56bc-112">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="b56bc-113">Melden Sie sich auf einer neuen Browserregisterkarte oder in einem neuen Browserfenster bei Ihrem DNS-Hostinganbieter an, und suchen Sie dann die Stelle, an der Sie Ihre DNS-Einstellungen verwalten (z. B. Zonendateieinstellungen, Domänen verwalten, Domänen-Manager, DNS-Manager).</span><span class="sxs-lookup"><span data-stu-id="b56bc-113">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="b56bc-114">Wechseln Sie zur Seite „DNS-Manager“ Ihres Anbieters, und fügen Sie den im Admin Center angegebenen TXT-Eintrag zu Ihrer Domäne hinzu.</span><span class="sxs-lookup"><span data-stu-id="b56bc-114">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="b56bc-115">Das Hinzufügen dieses Eintrags wirkt sich nicht auf Ihre bestehende E-Mail oder andere Dienste aus, und Sie können ihn bedenkenlos entfernen, sobald Ihre Domäne mit Microsoft 365 verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="b56bc-115">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="b56bc-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b56bc-116">Example:</span></span>
- <span data-ttu-id="b56bc-117">TXT-Name: `@`</span><span class="sxs-lookup"><span data-stu-id="b56bc-117">TXT Name: `@`</span></span>
- <span data-ttu-id="b56bc-118">TXT-Wert: MS=ms######## (eindeutige ID aus dem Admin Center)</span><span class="sxs-lookup"><span data-stu-id="b56bc-118">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="b56bc-119">TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)</span><span class="sxs-lookup"><span data-stu-id="b56bc-119">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="b56bc-120">Speichern Sie den Eintrag, wechseln Sie zurück zum Admin Center, und wählen Sie **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="b56bc-120">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="b56bc-121">Normalerweise dauert es ungefähr 15 Minuten, bis Eintragsänderungen registriert werden, doch manchmal kann es auch länger dauern.</span><span class="sxs-lookup"><span data-stu-id="b56bc-121">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="b56bc-122">Gewähren Sie dem Vorgang etwas Zeit sowie ein paar Versuche, um die Änderung zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="b56bc-122">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="b56bc-123">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="b56bc-123">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

### <a name="verify-with-an-mx-record"></a><span data-ttu-id="b56bc-124">Verifizierung anhand eines MX-Eintrags</span><span class="sxs-lookup"><span data-stu-id="b56bc-124">Verify with an MX record</span></span>

<span data-ttu-id="b56bc-125">Wenn Ihre Registrierungsstelle das Hinzufügen von TXT-Einträgen nicht unterstützt, können Sie die Verifizierung anhand eines MX-Eintrags vornehmen.</span><span class="sxs-lookup"><span data-stu-id="b56bc-125">If your registrar doesn't support adding TXT records, you can verify by adding an MX record.</span></span>

1. <span data-ttu-id="b56bc-126">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com/) an, und wählen Sie **Alle anzeigen** > **Einstellungen** > **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="b56bc-126">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="b56bc-127">Melden Sie sich auf einer neuen Browserregisterkarte oder in einem neuen Browserfenster bei Ihrem DNS-Hostinganbieter an, und suchen Sie dann die Stelle, an der Sie Ihre DNS-Einstellungen verwalten (z. B. Zonendateieinstellungen, Domänen verwalten, Domänen-Manager, DNS-Manager).</span><span class="sxs-lookup"><span data-stu-id="b56bc-127">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="b56bc-128">Wechseln Sie zur Seite „DNS-Manager“ Ihres Anbieters und fügen Sie den im Admin Center angegebenen MX-Eintrag zu Ihrer Domäne hinzu.</span><span class="sxs-lookup"><span data-stu-id="b56bc-128">Go to your provider's DNS Manager page, and add the MX record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="b56bc-129">Die **Priorität** dieses MX-Eintrags muss die höchste für alle vorhandenen MX-Einträge der Domäne sein.</span><span class="sxs-lookup"><span data-stu-id="b56bc-129">This MX record's **Priority** must be the highest of all existing MX records for the domain.</span></span> <span data-ttu-id="b56bc-130">Andernfalls kann dies Auswirkungen auf das Senden und Empfangen von E-Mails haben.</span><span class="sxs-lookup"><span data-stu-id="b56bc-130">Otherwise, it can interfere with sending and receiving email.</span></span> <span data-ttu-id="b56bc-131">Sie sollten diese Einträge löschen, sobald die Verifizierung der Domäne abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b56bc-131">You should delete this records as soon as domain verification is complete.</span></span>

<span data-ttu-id="b56bc-132">Stellen Sie sicher, dass die Felder auf die folgenden Werte festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="b56bc-132">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="b56bc-133">Eintragstyp: `MX`</span><span class="sxs-lookup"><span data-stu-id="b56bc-133">Record Type: `MX`</span></span>
- <span data-ttu-id="b56bc-134">Priorität: Legen Sie dies auf den höchsten verfügbaren Wert fest, in der Regel `0`.</span><span class="sxs-lookup"><span data-stu-id="b56bc-134">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="b56bc-135">Hostname: `@`</span><span class="sxs-lookup"><span data-stu-id="b56bc-135">Host Name: `@`</span></span>
- <span data-ttu-id="b56bc-136">Verweist auf die Adresse: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="b56bc-136">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="b56bc-137">TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)</span><span class="sxs-lookup"><span data-stu-id="b56bc-137">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="b56bc-138">Wenn Microsoft den richtigen MX-Eintrag findet, ist die Domäne verifiziert.</span><span class="sxs-lookup"><span data-stu-id="b56bc-138">When Microsoft finds the correct MX record, your domain is verified.</span></span>

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="b56bc-139">Schritt 2: Hinzufügen von DNS-Einträgen zum Verbinden von Microsoft-Diensten</span><span class="sxs-lookup"><span data-stu-id="b56bc-139">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="b56bc-140">Melden Sie sich auf einer neuen Browserregisterkarte oder in einem neuen Browserfenster bei Ihrem DNS-Hostinganbieter an, und suchen Sie die Stelle, an der Sie Ihre DNS-Einstellungen verwalten (z. B. Zonendateieinstellungen, Domänen verwalten, Domänen-Manager, DNS-Manager).</span><span class="sxs-lookup"><span data-stu-id="b56bc-140">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="b56bc-141">Sie fügen mehrere unterschiedliche Typen von DNS-Einträgen hinzu, je nachdem, welche Dienste Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b56bc-141">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="b56bc-142">Hinzufügen eines MX-Eintrags für E-Mail (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="b56bc-142">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="b56bc-143">**Bevor Sie beginnen:** Wenn Benutzer bereits über E-Mail-Adressen mit Ihrer Domäne verfügen (z. B. „Benutzer@IhreDomäne.com“), erstellen Sie deren Konten im Admin Center, bevor Sie Ihre MX-Einträge einrichten.</span><span class="sxs-lookup"><span data-stu-id="b56bc-143">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="b56bc-144">Auf diese Weise erhalten sie weiterhin E-Mail.</span><span class="sxs-lookup"><span data-stu-id="b56bc-144">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="b56bc-145">Nachdem Sie den MX-Eintrag Ihrer Domäne aktualisiert haben, treffen alle neuen E-Mails für jeden Benutzer Ihr Domäne in Microsoft 365 ein.</span><span class="sxs-lookup"><span data-stu-id="b56bc-145">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="b56bc-146">Alle E-Mails, die Sie bereits erhalten haben, bleiben so lange auf Ihrem aktuellen E-Mail-Host gespeichert, bis Sie die [Migration von E-Mails und Kontakten zu Microsoft 365](../setup/migrate-email-and-contacts-admin.md) beschließen.</span><span class="sxs-lookup"><span data-stu-id="b56bc-146">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="b56bc-147">Sie erhalten nun die Informationen zu dem MX-Eintrag vom Assistenten für die Domäneneinrichtung im Admin Center.</span><span class="sxs-lookup"><span data-stu-id="b56bc-147">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="b56bc-148">Fügen Sie auf der Website Ihres Hostinganbieters einen neuen MX-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="b56bc-148">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="b56bc-149">Stellen Sie sicher, dass die Felder auf die folgenden Werte festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="b56bc-149">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="b56bc-150">Eintragstyp: `MX`</span><span class="sxs-lookup"><span data-stu-id="b56bc-150">Record Type: `MX`</span></span>
- <span data-ttu-id="b56bc-151">Priorität: Legen Sie dies auf den höchsten verfügbaren Wert fest, in der Regel `0`.</span><span class="sxs-lookup"><span data-stu-id="b56bc-151">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="b56bc-152">Hostname: `@`</span><span class="sxs-lookup"><span data-stu-id="b56bc-152">Host Name: `@`</span></span>
- <span data-ttu-id="b56bc-153">Verweist auf die Adresse: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="b56bc-153">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="b56bc-154">TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)</span><span class="sxs-lookup"><span data-stu-id="b56bc-154">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="b56bc-155">Speichern Sie den Eintrag, und entfernen Sie dann alle anderen MX-Einträge.</span><span class="sxs-lookup"><span data-stu-id="b56bc-155">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="b56bc-156">Hinzufügen von CNAME-Einträgen zum Verbinden anderer Dienste (Teams, Exchange Online, AAD, MDM)</span><span class="sxs-lookup"><span data-stu-id="b56bc-156">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="b56bc-157">Sie erhalten nun die Informationen zu den CNAME-Einträgen vom Assistenten für die Domäneneinrichtung im Admin Center.</span><span class="sxs-lookup"><span data-stu-id="b56bc-157">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="b56bc-158">Fügen Sie auf der Website Ihres Hostinganbieters CNAME-Einträge für jeden Dienst hinzu, den Sie verbinden möchten.</span><span class="sxs-lookup"><span data-stu-id="b56bc-158">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="b56bc-159">Stellen Sie sicher, dass jedes der Felder auf die jeweiligen folgenden Werte festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="b56bc-159">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="b56bc-160">Eintragstyp: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="b56bc-160">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="b56bc-161">Host: Fügen Sie hier die Werte ein, die Sie aus dem Admin Center kopieren.</span><span class="sxs-lookup"><span data-stu-id="b56bc-161">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="b56bc-162">Verweist auf die Adresse: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="b56bc-162">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="b56bc-163">TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)</span><span class="sxs-lookup"><span data-stu-id="b56bc-163">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="b56bc-164">Hinzufügen oder Bearbeiten eines SPF TXT-Eintrags, um E-Mail-Spam zu verhindern (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="b56bc-164">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="b56bc-165">**Bevor Sie beginnen:** Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft 365 keinen neuen.</span><span class="sxs-lookup"><span data-stu-id="b56bc-165">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="b56bc-166">Fügen Sie stattdessen die erforderlichen Microsoft 365-Werte dem aktuellen Eintrag auf der Website Ihres Hostinganbieters hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b56bc-166">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="b56bc-167">Bearbeiten Sie auf der Website Ihres Hostinganbieters den vorhandenen SPF-Eintrag, oder erstellen Sie einen neuen SPF-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="b56bc-167">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="b56bc-168">Stellen Sie sicher, dass die Felder auf die folgenden Werte festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="b56bc-168">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="b56bc-169">Eintragstyp: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="b56bc-169">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="b56bc-170">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="b56bc-170">Host: `@`</span></span>
- <span data-ttu-id="b56bc-171">TXT-Wert: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="b56bc-171">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="b56bc-172">TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)</span><span class="sxs-lookup"><span data-stu-id="b56bc-172">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="b56bc-173">Speichern Sie den Eintrag.</span><span class="sxs-lookup"><span data-stu-id="b56bc-173">Save the record.</span></span>

<span data-ttu-id="b56bc-174">Überprüfen Sie Ihren SPF-Eintrag, indem Sie eines dieser [SPF-Überprüfungstools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b56bc-174">Validate your SPF record by using one of these [SPF validation tools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="b56bc-175">SPF ist dafür vorgesehen, Spoofing möglichst zu verhindern, es gibt aber Spoofing-Techniken, vor denen SPF nicht schützen kann.</span><span class="sxs-lookup"><span data-stu-id="b56bc-175">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="b56bc-176">Zum Schutz vor diesen Techniken sollten Sie, nachdem Sie SPF eingerichtet haben, auch DKIM und DMARC für Microsoft 365 einrichten.</span><span class="sxs-lookup"><span data-stu-id="b56bc-176">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="b56bc-177">Um hiermit zu beginnen, lesen Sie [Verwenden von DKIM zur Überprüfung von ausgehenden E-Mails, die von Ihrer Domäne in Microsoft 365 gesendet wurden](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) und [Verwenden von DMARC zum Überprüfen von E-Mail in Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="b56bc-177">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) and [Use DMARC to validate email in Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="b56bc-178">Hinzufügen von SRV-Einträgen für Kommunikationsdienste (Teams, Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="b56bc-178">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="b56bc-179">Fügen Sie auf der Website Ihres Hostinganbieters SRV-Einträge für jeden Dienst hinzu, den Sie verbinden möchten.</span><span class="sxs-lookup"><span data-stu-id="b56bc-179">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="b56bc-180">Stellen Sie sicher, dass jedes der Felder auf die jeweiligen folgenden Werte festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="b56bc-180">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="b56bc-181">Eintragstyp: `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="b56bc-181">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="b56bc-182">Name: `@`</span><span class="sxs-lookup"><span data-stu-id="b56bc-182">Name: `@`</span></span>
- <span data-ttu-id="b56bc-183">Ziel: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="b56bc-183">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="b56bc-184">Protokoll: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="b56bc-184">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="b56bc-185">Dienst: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="b56bc-185">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="b56bc-186">Priorität: `100`</span><span class="sxs-lookup"><span data-stu-id="b56bc-186">Priority: `100`</span></span>
- <span data-ttu-id="b56bc-187">Gewichtung: `1`</span><span class="sxs-lookup"><span data-stu-id="b56bc-187">Weight: `1`</span></span>
- <span data-ttu-id="b56bc-188">Port: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.</span><span class="sxs-lookup"><span data-stu-id="b56bc-188">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="b56bc-189">TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)</span><span class="sxs-lookup"><span data-stu-id="b56bc-189">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="b56bc-190">Speichern Sie den Eintrag.</span><span class="sxs-lookup"><span data-stu-id="b56bc-190">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="b56bc-191">Einschränkungen und Problemumgehungen für SRV-Eintragsfelder</span><span class="sxs-lookup"><span data-stu-id="b56bc-191">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="b56bc-192">Einige Hostinganbieter richten Beschränkungen für Feldwerte in SRV-Einträgen ein.</span><span class="sxs-lookup"><span data-stu-id="b56bc-192">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="b56bc-193">Hier finden Sie einige gängige Problemumgehungen für diese Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="b56bc-193">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="b56bc-194">Name</span><span class="sxs-lookup"><span data-stu-id="b56bc-194">Name</span></span>
<span data-ttu-id="b56bc-195">Wenn Ihr Hostinganbieter die Einstellung dieses Felds auf **@** nicht zulässt, lassen Sie es leer.</span><span class="sxs-lookup"><span data-stu-id="b56bc-195">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="b56bc-196">Verwenden Sie diesen Ansatz *nur*, wenn Ihr Hostinganbieter über separate Felder für die Werte „Dienst“ und „Protokoll“ verfügt.</span><span class="sxs-lookup"><span data-stu-id="b56bc-196">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="b56bc-197">Andernfalls lesen Sie die Anmerkungen unten zu „Dienst“ und „Protokoll“.</span><span class="sxs-lookup"><span data-stu-id="b56bc-197">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="b56bc-198">„Dienst“ und „Protokoll“</span><span class="sxs-lookup"><span data-stu-id="b56bc-198">Service and Protocol</span></span>
<span data-ttu-id="b56bc-199">Wenn Ihr Hostinganbieter diese Felder für SRV-Einträge nicht bereitstellt, müssen Sie die Werte für **Dienst** und **Protokoll** im Feld **Name** des Eintrags angeben.</span><span class="sxs-lookup"><span data-stu-id="b56bc-199">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="b56bc-200">(Hinweis: Abhängig von Ihrem Hostinganbieter kann das Feld **Name** auch anders heißen, z. B: **Host**, **Hostname** oder **Subdomäne**). Um diese Werte hinzuzufügen, erstellen Sie eine einzelne Zeichenfolge und trennen die Werte durch einen Punkt.</span><span class="sxs-lookup"><span data-stu-id="b56bc-200">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="b56bc-201">Beispiel: `_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="b56bc-201">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="b56bc-202">„Priorität“, „Gewichtung“ und „Port“</span><span class="sxs-lookup"><span data-stu-id="b56bc-202">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="b56bc-203">Wenn Ihr Hostinganbieter diese Felder für SRV-Einträge nicht bereitstellt, müssen Sie sie im Feld **Ziel** des Eintrags angeben.</span><span class="sxs-lookup"><span data-stu-id="b56bc-203">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="b56bc-204">(Hinweis: Abhängig von Ihrem Hostinganbieter kann das Feld **Ziel** auch anders heißen, z. B.: **Inhalt**, **IP-Adresse** oder **Zielhost**.)</span><span class="sxs-lookup"><span data-stu-id="b56bc-204">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="b56bc-205">Um diese Werte hinzuzufügen, erstellen Sie eine einzelne Zeichenfolge, trennen die Werte durch Leerzeichen und lassen diese *manchmal mit einem Punkt enden* (wenden Sie sich an Ihren Anbieter, wenn Sie unsicher sind).</span><span class="sxs-lookup"><span data-stu-id="b56bc-205">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="b56bc-206">Die Werte müssen in dieser Reihenfolge eingegeben werden: „Priorität“, „Gewichtung“, „Port“, „Ziel“.</span><span class="sxs-lookup"><span data-stu-id="b56bc-206">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="b56bc-207">Beispiel 1: `100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="b56bc-207">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="b56bc-208">Beispiel 2: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="b56bc-208">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>

## <a name="related-content"></a><span data-ttu-id="b56bc-209">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="b56bc-209">Related content</span></span>

<span data-ttu-id="b56bc-210">[Ändern des Namenservers zum Einrichten von Microsoft 365 mit einer beliebigen Domänenregistrierungsstelle](change-nameservers-at-any-domain-registrar.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="b56bc-210">[Change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md) (article)</span></span>\
<span data-ttu-id="b56bc-211">[Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](find-and-fix-issues.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="b56bc-211">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="b56bc-212">[Domänen verwalten](index.yml) (Linkseite)</span><span class="sxs-lookup"><span data-stu-id="b56bc-212">[Manage domains](index.yml) (link page)</span></span>