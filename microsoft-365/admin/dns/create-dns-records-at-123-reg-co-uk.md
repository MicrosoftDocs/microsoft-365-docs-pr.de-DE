---
title: Erstellen von DNS-Einträgen bei 123-reg.co.uk für Microsoft
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
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter 123-reg.co.uk für Microsoft einrichten.
ms.openlocfilehash: c7a6db51bd1c2b2af06a1dde8c317850db0d9e35
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646360"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="4f30f-103">Erstellen von DNS-Einträgen bei 123-reg.co.uk für Microsoft</span><span class="sxs-lookup"><span data-stu-id="4f30f-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="4f30f-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="4f30f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4f30f-105">Wenn 123-reg.co.uk Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="4f30f-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="4f30f-106">Nachdem Sie diese Einträge bei 123-reg.co.uk hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="4f30f-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="4f30f-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4f30f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4f30f-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="4f30f-110">Add a TXT record for verification</span></span>
<span data-ttu-id="4f30f-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4f30f-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4f30f-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="4f30f-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f30f-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="4f30f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4f30f-p104">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4f30f-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4f30f-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="4f30f-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="4f30f-119">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="4f30f-119">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="4f30f-120">Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="4f30f-120">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="4f30f-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4f30f-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4f30f-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4f30f-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="4f30f-123">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="4f30f-123">**Hostname**</span></span> <br/> |<span data-ttu-id="4f30f-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="4f30f-124">**Type**</span></span> <br/> |<span data-ttu-id="4f30f-125">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="4f30f-125">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="4f30f-126">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="4f30f-126">TXT/SPF</span></span>  <br/> |<span data-ttu-id="4f30f-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4f30f-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4f30f-p105">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel- oder Verweisadresse** aus der Tabelle in [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="4f30f-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
6. <span data-ttu-id="4f30f-131">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4f30f-131">Select **Add**.</span></span>
    
7. <span data-ttu-id="4f30f-132">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4f30f-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4f30f-133">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern eine Suche nach dem Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="4f30f-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="4f30f-134">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="4f30f-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4f30f-135">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="4f30f-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4f30f-136">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="4f30f-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="4f30f-137">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="4f30f-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="4f30f-138">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="4f30f-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4f30f-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4f30f-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="4f30f-142">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4f30f-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="4f30f-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4f30f-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="4f30f-p107">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4f30f-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4f30f-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="4f30f-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="4f30f-147">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="4f30f-147">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="4f30f-148">Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="4f30f-148">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="4f30f-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4f30f-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4f30f-150">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4f30f-150">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4f30f-151">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="4f30f-151">**Hostname**</span></span>|<span data-ttu-id="4f30f-152">**Type**</span><span class="sxs-lookup"><span data-stu-id="4f30f-152">**Type**</span></span>|<span data-ttu-id="4f30f-153">**Priority**</span><span class="sxs-lookup"><span data-stu-id="4f30f-153">**Priority**</span></span>|<span data-ttu-id="4f30f-154">**Destination MX**</span><span class="sxs-lookup"><span data-stu-id="4f30f-154">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="4f30f-155">MX</span><span class="sxs-lookup"><span data-stu-id="4f30f-155">MX</span></span>  <br/> |<span data-ttu-id="4f30f-156">1</span><span class="sxs-lookup"><span data-stu-id="4f30f-156">1</span></span>  <br/> <span data-ttu-id="4f30f-157">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="4f30f-157">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="4f30f-158">*\<domain-key\>*  . Mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="4f30f-158">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="4f30f-159">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f30f-159">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="4f30f-160">**Hinweis:** Erhalten Sie Ihren \<domain-key\> über Ihr Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="4f30f-160">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="4f30f-161">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="4f30f-161">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopieren und Einfügen von Werten aus der Tabelle](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="4f30f-163">Wählen Sie **Add** aus.</span><span class="sxs-lookup"><span data-stu-id="4f30f-163">Select **Add**.</span></span>
    
    !["Add" auswählen](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="4f30f-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span><span class="sxs-lookup"><span data-stu-id="4f30f-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Wählen Sie löschen (das Papierkorbsymbol)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="4f30f-167">Hinzufügen der sechs CNAME-Einträge, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="4f30f-167">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="4f30f-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4f30f-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="4f30f-p109">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4f30f-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4f30f-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="4f30f-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="4f30f-172">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="4f30f-172">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="4f30f-173">Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="4f30f-173">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="4f30f-174">Fügen Sie den ersten der sechs CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="4f30f-174">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="4f30f-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4f30f-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4f30f-176">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4f30f-176">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4f30f-177">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="4f30f-177">**Hostname**</span></span>|<span data-ttu-id="4f30f-178">**Type**</span><span class="sxs-lookup"><span data-stu-id="4f30f-178">**Type**</span></span>|<span data-ttu-id="4f30f-179">**Destination CNAME**</span><span class="sxs-lookup"><span data-stu-id="4f30f-179">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="4f30f-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4f30f-180">autodiscover</span></span>  <br/> |<span data-ttu-id="4f30f-181">CNAME</span><span class="sxs-lookup"><span data-stu-id="4f30f-181">CNAME</span></span>  <br/> |<span data-ttu-id="4f30f-182">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="4f30f-182">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="4f30f-183">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f30f-183">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="4f30f-184">sip</span><span class="sxs-lookup"><span data-stu-id="4f30f-184">sip</span></span>  <br/> |<span data-ttu-id="4f30f-185">CNAME</span><span class="sxs-lookup"><span data-stu-id="4f30f-185">CNAME</span></span>  <br/> |<span data-ttu-id="4f30f-186">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4f30f-186">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="4f30f-187">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f30f-187">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="4f30f-188">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4f30f-188">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4f30f-189">CNAME</span><span class="sxs-lookup"><span data-stu-id="4f30f-189">CNAME</span></span>  <br/> |<span data-ttu-id="4f30f-190">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4f30f-190">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="4f30f-191">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f30f-191">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="4f30f-192">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4f30f-192">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4f30f-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="4f30f-193">CNAME</span></span>  <br/> |<span data-ttu-id="4f30f-194">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="4f30f-194">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="4f30f-195">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f30f-195">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="4f30f-196">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4f30f-196">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4f30f-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="4f30f-197">CNAME</span></span>  <br/> |<span data-ttu-id="4f30f-198">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4f30f-198">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="4f30f-199">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f30f-199">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Kopieren Sie die Werte aus der Tabelle, und fügen Sie Sie ein.](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="4f30f-201">Wählen Sie **Add** aus.</span><span class="sxs-lookup"><span data-stu-id="4f30f-201">Select **Add**.</span></span>
    
    !["Add" auswählen](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="4f30f-203">Fügen Sie die fünf anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="4f30f-203">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="4f30f-204">Erstellen Sie im Abschnitt **Advanced DNS** einen Datensatz mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Hinzufügen** aus, um diesen Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4f30f-204">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="4f30f-205">Wiederholen Sie diesen Vorgang, bis Sie alle sechs CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="4f30f-205">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4f30f-206">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="4f30f-206">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4f30f-207"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4f30f-207"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f30f-208">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="4f30f-208">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4f30f-209">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="4f30f-209">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4f30f-210">Wenn Sie bereits einen SPF-Eintrag für Ihre Domäne haben, erstellen Sie keinen neuen für Microsfot.</span><span class="sxs-lookup"><span data-stu-id="4f30f-210">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="4f30f-211">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen  *einzelnen*  SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="4f30f-211">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="4f30f-212">Benötigen Sie Beispiele?</span><span class="sxs-lookup"><span data-stu-id="4f30f-212">Need examples?</span></span> <span data-ttu-id="4f30f-213">Lesen Sie die Informationen unter [Externe DNS-Einträge für Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf).</span><span class="sxs-lookup"><span data-stu-id="4f30f-213">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf).</span></span> <span data-ttu-id="4f30f-214">Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4f30f-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="4f30f-215">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk.</span><span class="sxs-lookup"><span data-stu-id="4f30f-215">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="4f30f-216">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4f30f-216">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4f30f-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="4f30f-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="4f30f-218">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="4f30f-218">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="4f30f-219">Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="4f30f-219">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="4f30f-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4f30f-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4f30f-221">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4f30f-221">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4f30f-222">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="4f30f-222">**Hostname**</span></span>|<span data-ttu-id="4f30f-223">**Type**</span><span class="sxs-lookup"><span data-stu-id="4f30f-223">**Type**</span></span>|<span data-ttu-id="4f30f-224">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="4f30f-224">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="4f30f-225">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="4f30f-225">TXT/SPF</span></span>  <br/> |<span data-ttu-id="4f30f-226">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4f30f-226">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="4f30f-227">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="4f30f-227">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123reg wußte-BP-configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="4f30f-229">Wählen Sie **Add** aus.</span><span class="sxs-lookup"><span data-stu-id="4f30f-229">Select **Add**.</span></span>
    
    !["Add" auswählen](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="4f30f-231">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="4f30f-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="4f30f-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4f30f-232"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="4f30f-p112">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4f30f-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4f30f-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="4f30f-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="4f30f-236">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="4f30f-236">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="4f30f-237">Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="4f30f-237">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="4f30f-238">Fügen Sie den ersten der zwei SRV-Einträge hinzu:</span><span class="sxs-lookup"><span data-stu-id="4f30f-238">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="4f30f-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="4f30f-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="4f30f-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4f30f-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4f30f-241">Hostname</span><span class="sxs-lookup"><span data-stu-id="4f30f-241">Hostname</span></span>|<span data-ttu-id="4f30f-242">Type</span><span class="sxs-lookup"><span data-stu-id="4f30f-242">Type</span></span>|<span data-ttu-id="4f30f-243">Priority</span><span class="sxs-lookup"><span data-stu-id="4f30f-243">Priority</span></span>|<span data-ttu-id="4f30f-244">TTL</span><span class="sxs-lookup"><span data-stu-id="4f30f-244">TTL</span></span>|<span data-ttu-id="4f30f-245">Destination SRV</span><span class="sxs-lookup"><span data-stu-id="4f30f-245">Destination SRV</span></span>|
    |<span data-ttu-id="4f30f-246">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="4f30f-246">_sip._tls</span></span>|<span data-ttu-id="4f30f-247">SRV</span><span class="sxs-lookup"><span data-stu-id="4f30f-247">SRV</span></span>|<span data-ttu-id="4f30f-248">100</span><span class="sxs-lookup"><span data-stu-id="4f30f-248">100</span></span>|<span data-ttu-id="4f30f-249">3600</span><span class="sxs-lookup"><span data-stu-id="4f30f-249">3600</span></span>|<span data-ttu-id="4f30f-250">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4f30f-250">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="4f30f-251">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f30f-251">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="4f30f-252">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="4f30f-252">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="4f30f-253">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="4f30f-253">_sipfederationtls._tcp</span></span>|<span data-ttu-id="4f30f-254">SRV</span><span class="sxs-lookup"><span data-stu-id="4f30f-254">SRV</span></span>|<span data-ttu-id="4f30f-255">100</span><span class="sxs-lookup"><span data-stu-id="4f30f-255">100</span></span>|<span data-ttu-id="4f30f-256">3600</span><span class="sxs-lookup"><span data-stu-id="4f30f-256">3600</span></span>|<span data-ttu-id="4f30f-257">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4f30f-257">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="4f30f-258">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="4f30f-258">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="4f30f-259">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="4f30f-259">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Kopieren Sie die Werte aus der Tabelle, und fügen Sie Sie ein.](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="4f30f-261">Wählen Sie **Add** aus.</span><span class="sxs-lookup"><span data-stu-id="4f30f-261">Select **Add**.</span></span>
    
    !["Add" auswählen](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="4f30f-263">Fügen Sie den anderen SRV-Eintrag hinzu:</span><span class="sxs-lookup"><span data-stu-id="4f30f-263">To add the other SRV record:</span></span>
    
    <span data-ttu-id="4f30f-264">Erstellen Sie im Abschnitt **Advanced DNS** einen Datensatz unter Verwendung der Werte aus der zweiten Zeile in der Tabelle, und wählen Sie dann erneut **Hinzufügen** aus, um diesen Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4f30f-264">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="4f30f-p115">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4f30f-p115">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
