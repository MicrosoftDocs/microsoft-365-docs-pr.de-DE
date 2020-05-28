---
title: Erstellen von DNS-Einträgen bei easyDNS für Microsoft
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
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter easyDNS für Microsoft einrichten.
ms.openlocfilehash: 24f477d240af936975141c53d382e114a24c0ac5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400232"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="1de9e-103">Erstellen von DNS-Einträgen bei easyDNS für Microsoft</span><span class="sxs-lookup"><span data-stu-id="1de9e-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="1de9e-104">[] [Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md) , wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="1de9e-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1de9e-105">Sie müssen alle folgenden DNS-Einträge auf der Website Ihrer Registrierungsstelle hinzufügen, um e-Mails an Microsoft weiterzuleiten, Ihre Domäne für Teams und Skype for Business zu verwenden usw.</span><span class="sxs-lookup"><span data-stu-id="1de9e-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="1de9e-106">Hinweis: SRV-Einträge sind derzeit nicht in allen easyDNS-Dienst Paketen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1de9e-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="1de9e-107">Möglicherweise müssen Sie ein Upgrade auf ein höheres Service Level mit easyDNS durchführen, um SRV-Einträge hinzuzufügen, die für Skype for Business erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1de9e-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="1de9e-108">Überprüfen, ob Sie die Domäne mit einem TXT-Eintrag besitzen</span><span class="sxs-lookup"><span data-stu-id="1de9e-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="1de9e-109">Wechseln Sie zu, [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="1de9e-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="1de9e-110">Wählen Sie unter der Überschrift **alle Domänen** die Option **DNS aus.**</span><span class="sxs-lookup"><span data-stu-id="1de9e-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="1de9e-111">Wählen Sie unter der Überschrift **TXT-Datensätze** die Schaltfläche Bearbeiten (Schlüsselsymbol) aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="1de9e-112">Geben Sie die folgenden Einträge in die Textfelder ein:</span><span class="sxs-lookup"><span data-stu-id="1de9e-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="1de9e-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="1de9e-113">**Host**</span></span>|<span data-ttu-id="1de9e-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="1de9e-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="1de9e-115">MS = msXXXXXXXX (verwenden Sie den auf der Seite Admin Center-Domänen bereitgestellten Wert)</span><span class="sxs-lookup"><span data-stu-id="1de9e-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="1de9e-116">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="1de9e-117">Stellen Sie sicher, dass der Eintrag richtig ist, und wählen Sie dann **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="1de9e-118">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag über das Internet verbreitet und von Microsoft erkannt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1de9e-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="1de9e-119">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="1de9e-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="1de9e-120">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="1de9e-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="1de9e-121">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="1de9e-122">Wählen Sie auf der Seite **Setup** die Option **Setup starten aus.**</span><span class="sxs-lookup"><span data-stu-id="1de9e-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="1de9e-123">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="1de9e-124">Hinzufügen eines MX-Eintrags zum Weiterleiten von e-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="1de9e-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="1de9e-125">Wechseln Sie zu, [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="1de9e-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="1de9e-126">Wählen Sie unter der Überschrift **alle Domänen** die Option **DNS aus.**</span><span class="sxs-lookup"><span data-stu-id="1de9e-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="1de9e-127">Wählen Sie unter der Überschrift **MX Records** die Schaltfläche Bearbeiten (Schlüsselsymbol) aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="1de9e-128">Geben Sie die folgenden Einträge in die Textfelder ein:</span><span class="sxs-lookup"><span data-stu-id="1de9e-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="1de9e-129">**e-Mail für Zone**</span><span class="sxs-lookup"><span data-stu-id="1de9e-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="1de9e-130">**e-Mail-Server**</span><span class="sxs-lookup"><span data-stu-id="1de9e-130">**MAIL SERVER**</span></span>|<span data-ttu-id="1de9e-131">**Präferenz**</span><span class="sxs-lookup"><span data-stu-id="1de9e-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="1de9e-132">\<domain-key\>. Mail.Protection.Outlook.com (Abrufen Ihres \<domain-key\> Werts über die Admin Center-Domänen Seite)</span><span class="sxs-lookup"><span data-stu-id="1de9e-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="1de9e-133">0</span><span class="sxs-lookup"><span data-stu-id="1de9e-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="1de9e-134">Wenn Sie Ihre anderen MX-Einträge zu Sicherungszwecken speichern möchten, kopieren Sie Sie an einer beliebigen Stelle.</span><span class="sxs-lookup"><span data-stu-id="1de9e-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="1de9e-135">Bevor Sie fortfahren, entfernen Sie alle anderen MX-Einträge hier.</span><span class="sxs-lookup"><span data-stu-id="1de9e-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="1de9e-136">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="1de9e-137">Stellen Sie sicher, dass der Eintrag richtig ist, und wählen Sie dann **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="1de9e-138">Hinzufügen der erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="1de9e-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="1de9e-139">Wechseln Sie zu, [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="1de9e-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="1de9e-140">Wählen Sie unter der Überschrift **alle Domänen** die Option **DNS aus.**</span><span class="sxs-lookup"><span data-stu-id="1de9e-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="1de9e-141">Wählen Sie unter der Überschrift **CNAME/Alias Datensätze** die Schaltfläche Bearbeiten (Schlüsselsymbol) aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="1de9e-142">Geben Sie die folgenden Einträge in die Textfelder ein:</span><span class="sxs-lookup"><span data-stu-id="1de9e-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="1de9e-143">**HOST**</span><span class="sxs-lookup"><span data-stu-id="1de9e-143">**HOST**</span></span>|<span data-ttu-id="1de9e-144">**Address (muss mit einem "." enden)**</span><span class="sxs-lookup"><span data-stu-id="1de9e-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1de9e-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1de9e-145">autodiscover</span></span>  <br/> |<span data-ttu-id="1de9e-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1de9e-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="1de9e-147">sip</span><span class="sxs-lookup"><span data-stu-id="1de9e-147">sip</span></span>  <br/> |<span data-ttu-id="1de9e-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1de9e-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="1de9e-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1de9e-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1de9e-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1de9e-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="1de9e-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1de9e-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1de9e-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="1de9e-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="1de9e-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1de9e-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1de9e-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1de9e-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="1de9e-155">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="1de9e-156">Stellen Sie sicher, dass der Eintrag richtig ist, und wählen Sie dann **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1de9e-157">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="1de9e-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="1de9e-158">Wechseln Sie zu, [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="1de9e-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="1de9e-159">Wählen Sie unter der Überschrift **alle Domänen** die Option **DNS aus.**</span><span class="sxs-lookup"><span data-stu-id="1de9e-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="1de9e-160">Wählen Sie unter der Überschrift **TXT-Datensätze** die Schaltfläche Bearbeiten (Schlüsselsymbol) aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="1de9e-161">Geben Sie die folgenden Einträge in die Textfelder ein:</span><span class="sxs-lookup"><span data-stu-id="1de9e-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="1de9e-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="1de9e-162">**Host**</span></span>|<span data-ttu-id="1de9e-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="1de9e-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="1de9e-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1de9e-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="1de9e-165">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="1de9e-166">Stellen Sie sicher, dass der Eintrag richtig ist, und wählen Sie dann **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1de9e-167">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="1de9e-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="1de9e-168">Hinweis: SRV-Einträge sind derzeit unter easyDNS ' Domain plus Service Level nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1de9e-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="1de9e-169">Möglicherweise müssen Sie ein Upgrade auf ein höheres Service Level mit easyDNS durchführen, um SRV-Einträge hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1de9e-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="1de9e-170">Wechseln Sie zu, [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="1de9e-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="1de9e-171">Wählen Sie unter der Überschrift **alle Domänen** die Option **DNS aus.**</span><span class="sxs-lookup"><span data-stu-id="1de9e-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="1de9e-172">Wählen Sie unter der Überschrift **SRV-Datensätze** die Schaltfläche Bearbeiten (Schlüsselsymbol) aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="1de9e-173">Geben Sie die folgenden Einträge in die Textfelder ein:</span><span class="sxs-lookup"><span data-stu-id="1de9e-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="1de9e-174">**SERVICE**</span><span class="sxs-lookup"><span data-stu-id="1de9e-174">**SERVICE**</span></span>|<span data-ttu-id="1de9e-175">**Proto**</span><span class="sxs-lookup"><span data-stu-id="1de9e-175">**PROTO**</span></span>|<span data-ttu-id="1de9e-176">**HOST**</span><span class="sxs-lookup"><span data-stu-id="1de9e-176">**HOST**</span></span>|<span data-ttu-id="1de9e-177">**PRI**</span><span class="sxs-lookup"><span data-stu-id="1de9e-177">**PRI**</span></span>|<span data-ttu-id="1de9e-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="1de9e-178">**WGT**</span></span>|<span data-ttu-id="1de9e-179">**PORT**</span><span class="sxs-lookup"><span data-stu-id="1de9e-179">**PORT**</span></span>|<span data-ttu-id="1de9e-180">**Target (muss mit einem "." enden)**</span><span class="sxs-lookup"><span data-stu-id="1de9e-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="1de9e-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1de9e-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1de9e-182">_sip</span><span class="sxs-lookup"><span data-stu-id="1de9e-182">_sip</span></span>  <br/> |<span data-ttu-id="1de9e-183">TLS</span><span class="sxs-lookup"><span data-stu-id="1de9e-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="1de9e-184">100</span><span class="sxs-lookup"><span data-stu-id="1de9e-184">100</span></span>  <br/> |<span data-ttu-id="1de9e-185">1 </span><span class="sxs-lookup"><span data-stu-id="1de9e-185">1</span></span>  <br/> |<span data-ttu-id="1de9e-186">443</span><span class="sxs-lookup"><span data-stu-id="1de9e-186">443</span></span>  <br/> |<span data-ttu-id="1de9e-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1de9e-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="1de9e-188">1800</span><span class="sxs-lookup"><span data-stu-id="1de9e-188">1800</span></span>  <br/> |
    |<span data-ttu-id="1de9e-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="1de9e-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="1de9e-190">TCP</span><span class="sxs-lookup"><span data-stu-id="1de9e-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="1de9e-191">100</span><span class="sxs-lookup"><span data-stu-id="1de9e-191">100</span></span>  <br/> |<span data-ttu-id="1de9e-192">1 </span><span class="sxs-lookup"><span data-stu-id="1de9e-192">1</span></span>  <br/> |<span data-ttu-id="1de9e-193">5061</span><span class="sxs-lookup"><span data-stu-id="1de9e-193">5061</span></span>  <br/> |<span data-ttu-id="1de9e-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1de9e-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="1de9e-195">1800</span><span class="sxs-lookup"><span data-stu-id="1de9e-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="1de9e-196">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="1de9e-197">Stellen Sie sicher, dass der Eintrag richtig ist, und wählen Sie dann **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

