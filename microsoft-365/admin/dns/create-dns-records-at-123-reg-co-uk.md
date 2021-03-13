---
title: Erstellen von DNS-Einträgen 123-reg.co.uk Microsoft
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
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mails, Skype for Business Online und andere Dienste bei 123-reg.co.uk Microsoft einrichten.
ms.openlocfilehash: 3c9af6909f37082a63170adac94ac3d92b717ad1
ms.sourcegitcommit: bf9e0091e5bdc78d9b23be64583eb816bb059eb2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "50758904"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="98812-103">Erstellen von DNS-Einträgen 123-reg.co.uk Microsoft</span><span class="sxs-lookup"><span data-stu-id="98812-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="98812-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="98812-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="98812-105">Wenn 123-reg.co.uk Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="98812-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="98812-106">Nachdem Sie diese Datensätze unter 123-reg.co.uk hinzugefügt haben, wird Ihre Domäne für die Arbeit mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="98812-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="98812-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="98812-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="98812-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="98812-110">Add a TXT record for verification</span></span>
<span data-ttu-id="98812-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="98812-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="98812-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="98812-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="98812-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="98812-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="98812-p104">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="98812-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="98812-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="98812-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="98812-119">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="98812-119">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="98812-120">Wählen Sie **auf der Seite Verwalten** Ihres DNS die Registerkarte **Erweitertes DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="98812-120">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="98812-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="98812-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="98812-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="98812-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="98812-123">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="98812-123">**Hostname**</span></span> <br/> |<span data-ttu-id="98812-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="98812-124">**Type**</span></span> <br/> |<span data-ttu-id="98812-125">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="98812-125">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="98812-126">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="98812-126">TXT/SPF</span></span>  <br/> |<span data-ttu-id="98812-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="98812-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="98812-p105">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel- oder Verweisadresse** aus der Tabelle in [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="98812-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
6. <span data-ttu-id="98812-131">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="98812-131">Select **Add**.</span></span>
    
7. <span data-ttu-id="98812-132">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="98812-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="98812-133">Nachdem Sie den Eintrag nun an der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, wechseln Sie zurück zu Microsoft und fordern eine Suche nach dem Datensatz an.</span><span class="sxs-lookup"><span data-stu-id="98812-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="98812-134">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="98812-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="98812-135">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="98812-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="98812-136">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="98812-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="98812-137">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="98812-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="98812-138">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="98812-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="98812-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="98812-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="98812-142">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="98812-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="98812-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="98812-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="98812-p107">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="98812-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="98812-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="98812-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="98812-147">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="98812-147">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="98812-148">Wählen Sie **auf der Seite Verwalten** Ihres DNS die Registerkarte **Erweitertes DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="98812-148">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="98812-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="98812-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="98812-150">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="98812-150">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="98812-151">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="98812-151">**Hostname**</span></span>|<span data-ttu-id="98812-152">**Type**</span><span class="sxs-lookup"><span data-stu-id="98812-152">**Type**</span></span>|<span data-ttu-id="98812-153">**Priority**</span><span class="sxs-lookup"><span data-stu-id="98812-153">**Priority**</span></span>|<span data-ttu-id="98812-154">**Destination MX**</span><span class="sxs-lookup"><span data-stu-id="98812-154">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="98812-155">MX</span><span class="sxs-lookup"><span data-stu-id="98812-155">MX</span></span>  <br/> |<span data-ttu-id="98812-156">1</span><span class="sxs-lookup"><span data-stu-id="98812-156">1</span></span>  <br/> <span data-ttu-id="98812-157">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="98812-157">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="98812-158">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="98812-158">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="98812-159">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="98812-159">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="98812-160">**Hinweis:** Erhalten Sie Ihren \<domain-key\> über Ihr Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="98812-160">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="98812-161">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="98812-161">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopieren und Einfügen von Werten aus der Tabelle](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="98812-163">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="98812-163">Select **Add**.</span></span>
    
    ![Screenshot des Dialogfelds mit ausgewählter Schaltfläche Hinzufügen](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="98812-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span><span class="sxs-lookup"><span data-stu-id="98812-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Select Delete (the trash can icon)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="98812-167">Hinzufügen der fünf für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="98812-167">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="98812-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="98812-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="98812-p109">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="98812-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="98812-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="98812-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="98812-172">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="98812-172">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="98812-173">Wählen Sie **auf der Seite Verwalten** Ihres DNS die Registerkarte **Erweitertes DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="98812-173">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="98812-174">Fügen Sie den ersten der fünf CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="98812-174">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="98812-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="98812-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="98812-176">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="98812-176">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="98812-177">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="98812-177">**Hostname**</span></span>|<span data-ttu-id="98812-178">**Type**</span><span class="sxs-lookup"><span data-stu-id="98812-178">**Type**</span></span>|<span data-ttu-id="98812-179">**Destination CNAME**</span><span class="sxs-lookup"><span data-stu-id="98812-179">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="98812-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="98812-180">autodiscover</span></span>  <br/> |<span data-ttu-id="98812-181">CNAME</span><span class="sxs-lookup"><span data-stu-id="98812-181">CNAME</span></span>  <br/> |<span data-ttu-id="98812-182">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="98812-182">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="98812-183">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="98812-183">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="98812-184">sip</span><span class="sxs-lookup"><span data-stu-id="98812-184">sip</span></span>  <br/> |<span data-ttu-id="98812-185">CNAME</span><span class="sxs-lookup"><span data-stu-id="98812-185">CNAME</span></span>  <br/> |<span data-ttu-id="98812-186">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="98812-186">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="98812-187">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="98812-187">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="98812-188">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="98812-188">lyncdiscover</span></span>  <br/> |<span data-ttu-id="98812-189">CNAME</span><span class="sxs-lookup"><span data-stu-id="98812-189">CNAME</span></span>  <br/> |<span data-ttu-id="98812-190">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="98812-190">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="98812-191">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="98812-191">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="98812-192">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="98812-192">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="98812-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="98812-193">CNAME</span></span>  <br/> |<span data-ttu-id="98812-194">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="98812-194">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="98812-195">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="98812-195">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="98812-196">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="98812-196">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="98812-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="98812-197">CNAME</span></span>  <br/> |<span data-ttu-id="98812-198">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="98812-198">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="98812-199">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="98812-199">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Screenshot mit Ziel-CNAME zum Kopieren und Einfügen](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="98812-201">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="98812-201">Select **Add**.</span></span>
    
    ![Screenshot zum Hinzufügen von Ziel-CNAME](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="98812-203">Fügen Sie die anderen vier CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="98812-203">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="98812-204">Erstellen Sie **im Abschnitt Advanced DNS** einen Eintrag mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Hinzufügen** aus, um diesen Eintrag zu vervollständigen.</span><span class="sxs-lookup"><span data-stu-id="98812-204">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="98812-205">Wiederholen Sie diesen Vorgang, bis Sie alle fünf CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="98812-205">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="98812-206">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="98812-206">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="98812-207"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="98812-207"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="98812-208">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="98812-208">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="98812-209">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="98812-209">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="98812-210">Wenn Sie bereits über einen SPF-Eintrag für Ihre Domäne verfügen, erstellen Sie keinen neuen für Microsfot.</span><span class="sxs-lookup"><span data-stu-id="98812-210">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="98812-211">Fügen Sie stattdessen dem aktuellen Datensatz die erforderlichen  Microsoft-Werte hinzu, sodass Sie über einen einzelnen SPF-Datensatz verfügen, der beide Wertesätze enthält.</span><span class="sxs-lookup"><span data-stu-id="98812-211">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="98812-212">Benötigen Sie Beispiele?</span><span class="sxs-lookup"><span data-stu-id="98812-212">Need examples?</span></span> <span data-ttu-id="98812-213">Lesen Sie die Informationen unter [Externe DNS-Einträge für Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf).</span><span class="sxs-lookup"><span data-stu-id="98812-213">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf).</span></span> <span data-ttu-id="98812-214">Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.yml) verwenden.</span><span class="sxs-lookup"><span data-stu-id="98812-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="98812-215">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk.</span><span class="sxs-lookup"><span data-stu-id="98812-215">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="98812-216">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="98812-216">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="98812-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="98812-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="98812-218">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="98812-218">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="98812-219">Wählen Sie **auf der Seite Verwalten** Ihres DNS die Registerkarte **Erweitertes DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="98812-219">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="98812-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="98812-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="98812-221">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="98812-221">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="98812-222">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="98812-222">**Hostname**</span></span>|<span data-ttu-id="98812-223">**Type**</span><span class="sxs-lookup"><span data-stu-id="98812-223">**Type**</span></span>|<span data-ttu-id="98812-224">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="98812-224">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="98812-225">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="98812-225">TXT/SPF</span></span>  <br/> |<span data-ttu-id="98812-226">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="98812-226">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="98812-227">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="98812-227">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-Configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="98812-229">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="98812-229">Select **Add**.</span></span>
    
    ![Screenshot mit Destination TXT/SPF](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="98812-231">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="98812-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="98812-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="98812-232"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="98812-p112">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="98812-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="98812-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="98812-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="98812-236">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="98812-236">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="98812-237">Wählen Sie **auf der Seite Verwalten** Ihres DNS die Registerkarte **Erweitertes DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="98812-237">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="98812-238">Fügen Sie den ersten der zwei SRV-Einträge hinzu:</span><span class="sxs-lookup"><span data-stu-id="98812-238">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="98812-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="98812-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="98812-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="98812-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="98812-241">Hostname</span><span class="sxs-lookup"><span data-stu-id="98812-241">Hostname</span></span>|<span data-ttu-id="98812-242">Type</span><span class="sxs-lookup"><span data-stu-id="98812-242">Type</span></span>|<span data-ttu-id="98812-243">Priority</span><span class="sxs-lookup"><span data-stu-id="98812-243">Priority</span></span>|<span data-ttu-id="98812-244">TTL</span><span class="sxs-lookup"><span data-stu-id="98812-244">TTL</span></span>|<span data-ttu-id="98812-245">Destination SRV</span><span class="sxs-lookup"><span data-stu-id="98812-245">Destination SRV</span></span>|
    |<span data-ttu-id="98812-246">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="98812-246">_sip._tls</span></span>|<span data-ttu-id="98812-247">SRV</span><span class="sxs-lookup"><span data-stu-id="98812-247">SRV</span></span>|<span data-ttu-id="98812-248">100</span><span class="sxs-lookup"><span data-stu-id="98812-248">100</span></span>|<span data-ttu-id="98812-249">3600</span><span class="sxs-lookup"><span data-stu-id="98812-249">3600</span></span>|<span data-ttu-id="98812-250">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="98812-250">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="98812-251">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="98812-251">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="98812-252">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="98812-252">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="98812-253">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="98812-253">_sipfederationtls._tcp</span></span>|<span data-ttu-id="98812-254">SRV</span><span class="sxs-lookup"><span data-stu-id="98812-254">SRV</span></span>|<span data-ttu-id="98812-255">100</span><span class="sxs-lookup"><span data-stu-id="98812-255">100</span></span>|<span data-ttu-id="98812-256">3600</span><span class="sxs-lookup"><span data-stu-id="98812-256">3600</span></span>|<span data-ttu-id="98812-257">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="98812-257">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="98812-258">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="98812-258">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="98812-259">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="98812-259">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Screenshot mit DNS-Werten aus der Tabelle](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="98812-261">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="98812-261">Select **Add**.</span></span>
    
    ![Screenshot zum Hinzufügen von Ziel-SRV](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="98812-263">Fügen Sie den anderen SRV-Eintrag hinzu:</span><span class="sxs-lookup"><span data-stu-id="98812-263">To add the other SRV record:</span></span>
    
    <span data-ttu-id="98812-264">Erstellen Sie **im Abschnitt Advanced DNS** einen Datensatz mithilfe der Werte aus der zweiten Zeile in der Tabelle, und wählen Sie dann erneut **Hinzufügen** aus, um diesen Eintrag zu vervollständigen.</span><span class="sxs-lookup"><span data-stu-id="98812-264">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="98812-p115">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="98812-p115">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
