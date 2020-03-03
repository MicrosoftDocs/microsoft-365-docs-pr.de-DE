---
title: Erstellen von DNS-Einträgen für Office 365 bei Dyn.com
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter dyn.com für Office 365 einrichten.
ms.openlocfilehash: a09ba409b1788432c5cd5c060252bb76b6903342
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349346"
---
# <a name="create-dns-records-at-dyncom-for-office-365"></a><span data-ttu-id="dc3e5-103">Erstellen von DNS-Einträgen für Office 365 bei Dyn.com</span><span class="sxs-lookup"><span data-stu-id="dc3e5-103">Create DNS records at Dyn.com for Office 365</span></span>

 <span data-ttu-id="dc3e5-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="dc3e5-105">Wenn Dyn.com Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="dc3e5-106">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="dc3e5-106">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="dc3e5-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dc3e5-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="dc3e5-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="dc3e5-110">Add a TXT record for verification</span></span>
<span data-ttu-id="dc3e5-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="dc3e5-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="dc3e5-p102">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="dc3e5-115">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="dc3e5-116">Wählen Sie auf der Seite **DNS** für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="dc3e5-117">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="dc3e5-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="dc3e5-119">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="dc3e5-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="dc3e5-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-120">**Host**</span></span>|<span data-ttu-id="dc3e5-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-121">**TTL**</span></span>|<span data-ttu-id="dc3e5-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-122">**Type**</span></span>|<span data-ttu-id="dc3e5-123">**Data**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dc3e5-124">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="dc3e5-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="dc3e5-125">600</span><span class="sxs-lookup"><span data-stu-id="dc3e5-125">600</span></span>  <br/> |<span data-ttu-id="dc3e5-126">TXT</span><span class="sxs-lookup"><span data-stu-id="dc3e5-126">TXT</span></span>  <br/> |<span data-ttu-id="dc3e5-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="dc3e5-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="dc3e5-p103">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="dc3e5-p103">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="dc3e5-132">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="dc3e5-134">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="dc3e5-135">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-135">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="dc3e5-136">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-136">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="dc3e5-137">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-137">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="dc3e5-138">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="dc3e5-139">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="dc3e5-140">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="dc3e5-p104">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dc3e5-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="dc3e5-144">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="dc3e5-144">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="dc3e5-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="dc3e5-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="dc3e5-p105">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="dc3e5-149">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="dc3e5-150">Wählen Sie auf der Seite DNS für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="dc3e5-151">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="dc3e5-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="dc3e5-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="dc3e5-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="dc3e5-154">**Host**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-154">**Host**</span></span>|<span data-ttu-id="dc3e5-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-155">**TTL**</span></span>|<span data-ttu-id="dc3e5-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-156">**Type**</span></span>|<span data-ttu-id="dc3e5-157">**Data**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dc3e5-158">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="dc3e5-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="dc3e5-159">600</span><span class="sxs-lookup"><span data-stu-id="dc3e5-159">600</span></span>  <br/> |<span data-ttu-id="dc3e5-160">MX</span><span class="sxs-lookup"><span data-stu-id="dc3e5-160">MX</span></span>  <br/> |<span data-ttu-id="dc3e5-161">10  *\<Domänenschlüssel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="dc3e5-162">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="dc3e5-p106">Die **10** ist der MX-Prioritätswert. Fügen Sie ihn am Anfang des MX-Werts hinzu, vom Rest des Werts durch ein Leerzeichen getrennt.  </span><span class="sxs-lookup"><span data-stu-id="dc3e5-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="dc3e5-165">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-165">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="dc3e5-166">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="dc3e5-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="dc3e5-167">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="dc3e5-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-BP-configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="dc3e5-169">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-169">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="dc3e5-171">Falls es andere MX-Einträge gibt, entfernen Sie diese durch Aktivieren des Kontrollkästchens für jeden Eintrag in der Spalte **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="dc3e5-173">Wählen Sie **Änderungen übernehmen**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-173">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="dc3e5-175">Hinzufügen der für Office 365 erforderlichen sechs CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="dc3e5-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="dc3e5-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="dc3e5-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="dc3e5-p108">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="dc3e5-180">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="dc3e5-181">Wählen Sie auf der Seite **DNS** für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="dc3e5-182">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="dc3e5-183">Fügen Sie den ersten der sechs CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="dc3e5-184">Geben Sie im Bereich **Add DNS Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="dc3e5-185">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="dc3e5-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="dc3e5-186">**Host**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-186">**Host**</span></span>|<span data-ttu-id="dc3e5-187">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-187">**TTL**</span></span>|<span data-ttu-id="dc3e5-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-188">**Type**</span></span>|<span data-ttu-id="dc3e5-189">**Data**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dc3e5-190">autodiscover</span><span class="sxs-lookup"><span data-stu-id="dc3e5-190">autodiscover</span></span>  <br/> |<span data-ttu-id="dc3e5-191">600</span><span class="sxs-lookup"><span data-stu-id="dc3e5-191">600</span></span>  <br/> |<span data-ttu-id="dc3e5-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc3e5-192">CNAME</span></span>  <br/> |<span data-ttu-id="dc3e5-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="dc3e5-194">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="dc3e5-195">sip</span><span class="sxs-lookup"><span data-stu-id="dc3e5-195">sip</span></span>  <br/> |<span data-ttu-id="dc3e5-196">600</span><span class="sxs-lookup"><span data-stu-id="dc3e5-196">600</span></span>  <br/> |<span data-ttu-id="dc3e5-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc3e5-197">CNAME</span></span>  <br/> |<span data-ttu-id="dc3e5-198">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="dc3e5-199">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="dc3e5-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="dc3e5-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="dc3e5-201">600</span><span class="sxs-lookup"><span data-stu-id="dc3e5-201">600</span></span>  <br/> |<span data-ttu-id="dc3e5-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc3e5-202">CNAME</span></span>  <br/> |<span data-ttu-id="dc3e5-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="dc3e5-204">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="dc3e5-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="dc3e5-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="dc3e5-206">600</span><span class="sxs-lookup"><span data-stu-id="dc3e5-206">600</span></span>  <br/> |<span data-ttu-id="dc3e5-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc3e5-207">CNAME</span></span>  <br/> |<span data-ttu-id="dc3e5-208">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="dc3e5-209">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="dc3e5-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="dc3e5-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="dc3e5-211">600</span><span class="sxs-lookup"><span data-stu-id="dc3e5-211">600</span></span>  <br/> |<span data-ttu-id="dc3e5-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="dc3e5-212">CNAME</span></span>  <br/> |<span data-ttu-id="dc3e5-213">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="dc3e5-214">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="dc3e5-216">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-216">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="dc3e5-218">Fügen Sie die fünf restlichen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="dc3e5-219">Erstellen Sie im Abschnitt **DNS-Eintrag hinzufügen** einen Datensatz mithilfe der Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Datensatz erstellen** aus, um den Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="dc3e5-220">Wiederholen Sie diesen Vorgang, bis Sie alle sechs CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="dc3e5-221">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="dc3e5-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="dc3e5-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="dc3e5-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc3e5-223">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="dc3e5-224">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="dc3e5-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="dc3e5-226">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="dc3e5-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="dc3e5-230">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="dc3e5-231">Wählen Sie auf der Seite **DNS** für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="dc3e5-232">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="dc3e5-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="dc3e5-234">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="dc3e5-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="dc3e5-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-235">**Host**</span></span>|<span data-ttu-id="dc3e5-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-236">**TTL**</span></span>|<span data-ttu-id="dc3e5-237">**Type**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-237">**Type**</span></span>|<span data-ttu-id="dc3e5-238">**Data**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dc3e5-239">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="dc3e5-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="dc3e5-240">600</span><span class="sxs-lookup"><span data-stu-id="dc3e5-240">600</span></span>  <br/> |<span data-ttu-id="dc3e5-241">TXT</span><span class="sxs-lookup"><span data-stu-id="dc3e5-241">TXT</span></span>  <br/> |<span data-ttu-id="dc3e5-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="dc3e5-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="dc3e5-243">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="dc3e5-245">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-245">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="dc3e5-247">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="dc3e5-247">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="dc3e5-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="dc3e5-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="dc3e5-249">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="dc3e5-250">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-250">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="dc3e5-252">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="dc3e5-253">Wählen Sie auf der Seite **DNS** für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="dc3e5-254">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="dc3e5-255">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="dc3e5-256">Geben Sie im Bereich **Add DNS Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="dc3e5-257">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="dc3e5-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="dc3e5-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-258">**Host**</span></span>|<span data-ttu-id="dc3e5-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-259">**TTL**</span></span>|<span data-ttu-id="dc3e5-260">**Type**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-260">**Type**</span></span>|<span data-ttu-id="dc3e5-261">**Data**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dc3e5-262">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="dc3e5-262">_sip._tls</span></span>|<span data-ttu-id="dc3e5-263">600</span><span class="sxs-lookup"><span data-stu-id="dc3e5-263">600</span></span>|<span data-ttu-id="dc3e5-264">SRV</span><span class="sxs-lookup"><span data-stu-id="dc3e5-264">SRV</span></span>|<span data-ttu-id="dc3e5-265">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="dc3e5-266">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="dc3e5-267">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="dc3e5-268">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="dc3e5-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="dc3e5-269">600</span><span class="sxs-lookup"><span data-stu-id="dc3e5-269">600</span></span>|<span data-ttu-id="dc3e5-270">SRV</span><span class="sxs-lookup"><span data-stu-id="dc3e5-270">SRV</span></span>|<span data-ttu-id="dc3e5-271">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="dc3e5-272">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="dc3e5-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="dc3e5-273">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="dc3e5-275">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-275">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="dc3e5-277">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="dc3e5-278">Erstellen Sie im Abschnitt **DNS-Eintrag hinzufügen** einen Datensatz mithilfe der Werte aus der zweiten Zeile in der Tabelle, und wählen Sie dann erneut **Datensatz erstellen** aus, um den Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="dc3e5-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dc3e5-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
