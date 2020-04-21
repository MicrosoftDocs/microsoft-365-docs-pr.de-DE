---
title: Erstellen von DNS-Einträgen bei dyn.com für Microsoft
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter dyn.com für Microsoft einrichten.
ms.openlocfilehash: f9b705f94f05799b0aa97539e372c3efcfe2e4c8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629587"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="d0a16-103">Erstellen von DNS-Einträgen bei dyn.com für Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0a16-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="d0a16-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="d0a16-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d0a16-105">Wenn Dyn.com Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="d0a16-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="d0a16-106">Informationen über Webhosting und DNS für Websites mit Microsoft finden Sie unter [Verwenden einer öffentlichen Website mit Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="d0a16-106">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="d0a16-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d0a16-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d0a16-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="d0a16-110">Add a TXT record for verification</span></span>
<span data-ttu-id="d0a16-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d0a16-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="d0a16-p102">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="d0a16-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="d0a16-115">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d0a16-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="d0a16-116">Wählen Sie auf der Seite **DNS** für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="d0a16-117">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="d0a16-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d0a16-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d0a16-119">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d0a16-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d0a16-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="d0a16-120">**Host**</span></span>|<span data-ttu-id="d0a16-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d0a16-121">**TTL**</span></span>|<span data-ttu-id="d0a16-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="d0a16-122">**Type**</span></span>|<span data-ttu-id="d0a16-123">**Data**</span><span class="sxs-lookup"><span data-stu-id="d0a16-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d0a16-124">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d0a16-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d0a16-125">600</span><span class="sxs-lookup"><span data-stu-id="d0a16-125">600</span></span>  <br/> |<span data-ttu-id="d0a16-126">TXT</span><span class="sxs-lookup"><span data-stu-id="d0a16-126">TXT</span></span>  <br/> |<span data-ttu-id="d0a16-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d0a16-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d0a16-128">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d0a16-128">**Note:** This is an example.</span></span> <span data-ttu-id="d0a16-129">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d0a16-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="d0a16-130">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="d0a16-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="d0a16-132">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="d0a16-134">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d0a16-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d0a16-135">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="d0a16-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="d0a16-136">Wenn Microsoft den richtigen TXT-Eintrag findet, wird Ihre Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="d0a16-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d0a16-137">Wechseln Sie im Microsoft Admin Center zur Seite mit den **Einstellungs** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="d0a16-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d0a16-138">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="d0a16-139">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="d0a16-140">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="d0a16-p104">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d0a16-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d0a16-144">Hinzufügen eines MX-Eintrags, damit e-Mails für Ihre Domäne an Microsoft gelangen</span><span class="sxs-lookup"><span data-stu-id="d0a16-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d0a16-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d0a16-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d0a16-p105">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="d0a16-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="d0a16-149">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d0a16-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="d0a16-150">Wählen Sie auf der Seite DNS für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="d0a16-151">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="d0a16-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d0a16-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d0a16-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d0a16-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d0a16-154">**Host**</span><span class="sxs-lookup"><span data-stu-id="d0a16-154">**Host**</span></span>|<span data-ttu-id="d0a16-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d0a16-155">**TTL**</span></span>|<span data-ttu-id="d0a16-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="d0a16-156">**Type**</span></span>|<span data-ttu-id="d0a16-157">**Data**</span><span class="sxs-lookup"><span data-stu-id="d0a16-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d0a16-158">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d0a16-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d0a16-159">600</span><span class="sxs-lookup"><span data-stu-id="d0a16-159">600</span></span>  <br/> |<span data-ttu-id="d0a16-160">MX</span><span class="sxs-lookup"><span data-stu-id="d0a16-160">MX</span></span>  <br/> |<span data-ttu-id="d0a16-161">10  *\<Domänenschlüssel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d0a16-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="d0a16-162">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d0a16-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="d0a16-p106">Die **10** ist der MX-Prioritätswert. Fügen Sie ihn am Anfang des MX-Werts hinzu, vom Rest des Werts durch ein Leerzeichen getrennt.  </span><span class="sxs-lookup"><span data-stu-id="d0a16-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="d0a16-165">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="d0a16-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="d0a16-166">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="d0a16-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="d0a16-167">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="d0a16-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-BP-configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="d0a16-169">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-169">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="d0a16-171">Falls es andere MX-Einträge gibt, entfernen Sie diese durch Aktivieren des Kontrollkästchens für jeden Eintrag in der Spalte **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="d0a16-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="d0a16-173">Wählen Sie **Änderungen übernehmen**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-173">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d0a16-175">Hinzufügen der sechs CNAME-Einträge, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="d0a16-175">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d0a16-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d0a16-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d0a16-p108">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="d0a16-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="d0a16-180">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d0a16-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="d0a16-181">Wählen Sie auf der Seite **DNS** für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="d0a16-182">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="d0a16-183">Fügen Sie den ersten der sechs CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="d0a16-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="d0a16-184">Geben Sie im Bereich **Add DNS Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="d0a16-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="d0a16-185">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="d0a16-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d0a16-186">**Host**</span><span class="sxs-lookup"><span data-stu-id="d0a16-186">**Host**</span></span>|<span data-ttu-id="d0a16-187">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d0a16-187">**TTL**</span></span>|<span data-ttu-id="d0a16-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="d0a16-188">**Type**</span></span>|<span data-ttu-id="d0a16-189">**Data**</span><span class="sxs-lookup"><span data-stu-id="d0a16-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d0a16-190">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d0a16-190">autodiscover</span></span>  <br/> |<span data-ttu-id="d0a16-191">600</span><span class="sxs-lookup"><span data-stu-id="d0a16-191">600</span></span>  <br/> |<span data-ttu-id="d0a16-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="d0a16-192">CNAME</span></span>  <br/> |<span data-ttu-id="d0a16-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d0a16-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="d0a16-194">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d0a16-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d0a16-195">sip</span><span class="sxs-lookup"><span data-stu-id="d0a16-195">sip</span></span>  <br/> |<span data-ttu-id="d0a16-196">600</span><span class="sxs-lookup"><span data-stu-id="d0a16-196">600</span></span>  <br/> |<span data-ttu-id="d0a16-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="d0a16-197">CNAME</span></span>  <br/> |<span data-ttu-id="d0a16-198">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d0a16-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d0a16-199">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d0a16-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d0a16-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d0a16-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d0a16-201">600</span><span class="sxs-lookup"><span data-stu-id="d0a16-201">600</span></span>  <br/> |<span data-ttu-id="d0a16-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="d0a16-202">CNAME</span></span>  <br/> |<span data-ttu-id="d0a16-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d0a16-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d0a16-204">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d0a16-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d0a16-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d0a16-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d0a16-206">600</span><span class="sxs-lookup"><span data-stu-id="d0a16-206">600</span></span>  <br/> |<span data-ttu-id="d0a16-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="d0a16-207">CNAME</span></span>  <br/> |<span data-ttu-id="d0a16-208">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="d0a16-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="d0a16-209">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d0a16-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d0a16-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d0a16-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d0a16-211">600</span><span class="sxs-lookup"><span data-stu-id="d0a16-211">600</span></span>  <br/> |<span data-ttu-id="d0a16-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="d0a16-212">CNAME</span></span>  <br/> |<span data-ttu-id="d0a16-213">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d0a16-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="d0a16-214">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d0a16-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="d0a16-216">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-216">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="d0a16-218">Fügen Sie die fünf restlichen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="d0a16-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="d0a16-219">Erstellen Sie im Abschnitt **DNS-Eintrag hinzufügen** einen Datensatz mithilfe der Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Datensatz erstellen** aus, um den Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d0a16-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="d0a16-220">Wiederholen Sie diesen Vorgang, bis Sie alle sechs CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="d0a16-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d0a16-221">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="d0a16-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d0a16-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d0a16-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0a16-223">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="d0a16-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d0a16-224">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="d0a16-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d0a16-225">Wenn Sie bereits einen SPF-Eintrag für Ihre Domäne haben, erstellen Sie keinen neuen für Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d0a16-225">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d0a16-226">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="d0a16-226">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="d0a16-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="d0a16-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="d0a16-230">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d0a16-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="d0a16-231">Wählen Sie auf der Seite **DNS** für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="d0a16-232">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="d0a16-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d0a16-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d0a16-234">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d0a16-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d0a16-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="d0a16-235">**Host**</span></span>|<span data-ttu-id="d0a16-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d0a16-236">**TTL**</span></span>|<span data-ttu-id="d0a16-237">**Type**</span><span class="sxs-lookup"><span data-stu-id="d0a16-237">**Type**</span></span>|<span data-ttu-id="d0a16-238">**Data**</span><span class="sxs-lookup"><span data-stu-id="d0a16-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d0a16-239">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d0a16-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d0a16-240">600</span><span class="sxs-lookup"><span data-stu-id="d0a16-240">600</span></span>  <br/> |<span data-ttu-id="d0a16-241">TXT</span><span class="sxs-lookup"><span data-stu-id="d0a16-241">TXT</span></span>  <br/> |<span data-ttu-id="d0a16-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d0a16-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d0a16-243">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="d0a16-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="d0a16-245">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-245">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d0a16-247">Fügen Sie die beiden SRV-Einträge hinzu, die für Microsoft erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d0a16-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d0a16-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d0a16-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="d0a16-249">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com.</span><span class="sxs-lookup"><span data-stu-id="d0a16-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="d0a16-250">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="d0a16-250">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="d0a16-252">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d0a16-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="d0a16-253">Wählen Sie auf der Seite **DNS** für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="d0a16-254">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="d0a16-255">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="d0a16-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="d0a16-256">Geben Sie im Bereich **Add DNS Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="d0a16-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="d0a16-257">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="d0a16-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d0a16-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="d0a16-258">**Host**</span></span>|<span data-ttu-id="d0a16-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d0a16-259">**TTL**</span></span>|<span data-ttu-id="d0a16-260">**Type**</span><span class="sxs-lookup"><span data-stu-id="d0a16-260">**Type**</span></span>|<span data-ttu-id="d0a16-261">**Data**</span><span class="sxs-lookup"><span data-stu-id="d0a16-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d0a16-262">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="d0a16-262">_sip._tls</span></span>|<span data-ttu-id="d0a16-263">600</span><span class="sxs-lookup"><span data-stu-id="d0a16-263">600</span></span>|<span data-ttu-id="d0a16-264">SRV</span><span class="sxs-lookup"><span data-stu-id="d0a16-264">SRV</span></span>|<span data-ttu-id="d0a16-265">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d0a16-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="d0a16-266">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d0a16-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="d0a16-267">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="d0a16-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="d0a16-268">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="d0a16-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="d0a16-269">600</span><span class="sxs-lookup"><span data-stu-id="d0a16-269">600</span></span>|<span data-ttu-id="d0a16-270">SRV</span><span class="sxs-lookup"><span data-stu-id="d0a16-270">SRV</span></span>|<span data-ttu-id="d0a16-271">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d0a16-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="d0a16-272">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d0a16-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="d0a16-273">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="d0a16-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="d0a16-275">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="d0a16-275">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="d0a16-277">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="d0a16-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="d0a16-278">Erstellen Sie im Abschnitt **DNS-Eintrag hinzufügen** einen Datensatz mithilfe der Werte aus der zweiten Zeile in der Tabelle, und wählen Sie dann erneut **Datensatz erstellen** aus, um den Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d0a16-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="d0a16-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d0a16-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
