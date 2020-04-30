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
ms.openlocfilehash: afce9c21b0f717a038f378d4bf7114724748c2ac
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939283"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="10a5c-103">Erstellen von DNS-Einträgen bei dyn.com für Microsoft</span><span class="sxs-lookup"><span data-stu-id="10a5c-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="10a5c-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="10a5c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="10a5c-105">Wenn Dyn.com Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="10a5c-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 

  
> [!NOTE]
>  <span data-ttu-id="10a5c-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="10a5c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="10a5c-109">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="10a5c-109">Add a TXT record for verification</span></span>
<span data-ttu-id="10a5c-110"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="10a5c-110"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="10a5c-p102">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="10a5c-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="10a5c-114">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="10a5c-114">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="10a5c-115">Wählen Sie auf der Seite **DNS** für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-115">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="10a5c-116">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-116">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="10a5c-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="10a5c-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="10a5c-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="10a5c-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="10a5c-119">**Host**</span><span class="sxs-lookup"><span data-stu-id="10a5c-119">**Host**</span></span>|<span data-ttu-id="10a5c-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10a5c-120">**TTL**</span></span>|<span data-ttu-id="10a5c-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="10a5c-121">**Type**</span></span>|<span data-ttu-id="10a5c-122">**Data**</span><span class="sxs-lookup"><span data-stu-id="10a5c-122">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10a5c-123">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="10a5c-123">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="10a5c-124">600</span><span class="sxs-lookup"><span data-stu-id="10a5c-124">600</span></span>  <br/> |<span data-ttu-id="10a5c-125">TXT</span><span class="sxs-lookup"><span data-stu-id="10a5c-125">TXT</span></span>  <br/> |<span data-ttu-id="10a5c-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="10a5c-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="10a5c-127">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="10a5c-127">**Note:** This is an example.</span></span> <span data-ttu-id="10a5c-128">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="10a5c-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="10a5c-129">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="10a5c-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="10a5c-131">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-131">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="10a5c-133">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="10a5c-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="10a5c-134">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="10a5c-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="10a5c-135">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="10a5c-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="10a5c-136">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="10a5c-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="10a5c-137">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="10a5c-138">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-138">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="10a5c-139">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-139">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="10a5c-p104">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="10a5c-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="10a5c-143">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="10a5c-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="10a5c-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="10a5c-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="10a5c-p105">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="10a5c-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="10a5c-148">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="10a5c-148">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="10a5c-149">Wählen Sie auf der Seite DNS für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-149">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="10a5c-150">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-150">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="10a5c-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="10a5c-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="10a5c-152">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="10a5c-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="10a5c-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="10a5c-153">**Host**</span></span>|<span data-ttu-id="10a5c-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10a5c-154">**TTL**</span></span>|<span data-ttu-id="10a5c-155">**Type**</span><span class="sxs-lookup"><span data-stu-id="10a5c-155">**Type**</span></span>|<span data-ttu-id="10a5c-156">**Data**</span><span class="sxs-lookup"><span data-stu-id="10a5c-156">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10a5c-157">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="10a5c-157">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="10a5c-158">600</span><span class="sxs-lookup"><span data-stu-id="10a5c-158">600</span></span>  <br/> |<span data-ttu-id="10a5c-159">MX</span><span class="sxs-lookup"><span data-stu-id="10a5c-159">MX</span></span>  <br/> |<span data-ttu-id="10a5c-160">10  *\<Domänenschlüssel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="10a5c-160">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="10a5c-161">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="10a5c-161">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="10a5c-p106">Die **10** ist der MX-Prioritätswert. Fügen Sie ihn am Anfang des MX-Werts hinzu, vom Rest des Werts durch ein Leerzeichen getrennt.  </span><span class="sxs-lookup"><span data-stu-id="10a5c-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="10a5c-164">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="10a5c-164">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="10a5c-165">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="10a5c-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="10a5c-166">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="10a5c-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-BP-configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="10a5c-168">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-168">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="10a5c-170">Falls es andere MX-Einträge gibt, entfernen Sie diese durch Aktivieren des Kontrollkästchens für jeden Eintrag in der Spalte **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="10a5c-170">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="10a5c-172">Wählen Sie **Änderungen übernehmen**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-172">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="10a5c-174">Hinzufügen der sechs CNAME-Einträge, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="10a5c-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="10a5c-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="10a5c-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="10a5c-p108">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="10a5c-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="10a5c-179">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="10a5c-179">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="10a5c-180">Wählen Sie auf der Seite **DNS** für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-180">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="10a5c-181">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-181">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="10a5c-182">Fügen Sie den ersten der sechs CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="10a5c-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="10a5c-183">Geben Sie im Bereich **Add DNS Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="10a5c-183">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="10a5c-184">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="10a5c-184">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="10a5c-185">**Host**</span><span class="sxs-lookup"><span data-stu-id="10a5c-185">**Host**</span></span>|<span data-ttu-id="10a5c-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10a5c-186">**TTL**</span></span>|<span data-ttu-id="10a5c-187">**Type**</span><span class="sxs-lookup"><span data-stu-id="10a5c-187">**Type**</span></span>|<span data-ttu-id="10a5c-188">**Data**</span><span class="sxs-lookup"><span data-stu-id="10a5c-188">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10a5c-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="10a5c-189">autodiscover</span></span>  <br/> |<span data-ttu-id="10a5c-190">600</span><span class="sxs-lookup"><span data-stu-id="10a5c-190">600</span></span>  <br/> |<span data-ttu-id="10a5c-191">CNAME</span><span class="sxs-lookup"><span data-stu-id="10a5c-191">CNAME</span></span>  <br/> |<span data-ttu-id="10a5c-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="10a5c-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="10a5c-193">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="10a5c-193">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="10a5c-194">sip</span><span class="sxs-lookup"><span data-stu-id="10a5c-194">sip</span></span>  <br/> |<span data-ttu-id="10a5c-195">600</span><span class="sxs-lookup"><span data-stu-id="10a5c-195">600</span></span>  <br/> |<span data-ttu-id="10a5c-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="10a5c-196">CNAME</span></span>  <br/> |<span data-ttu-id="10a5c-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="10a5c-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="10a5c-198">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="10a5c-198">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="10a5c-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="10a5c-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="10a5c-200">600</span><span class="sxs-lookup"><span data-stu-id="10a5c-200">600</span></span>  <br/> |<span data-ttu-id="10a5c-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="10a5c-201">CNAME</span></span>  <br/> |<span data-ttu-id="10a5c-202">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="10a5c-202">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="10a5c-203">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="10a5c-203">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="10a5c-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="10a5c-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="10a5c-205">600</span><span class="sxs-lookup"><span data-stu-id="10a5c-205">600</span></span>  <br/> |<span data-ttu-id="10a5c-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="10a5c-206">CNAME</span></span>  <br/> |<span data-ttu-id="10a5c-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="10a5c-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="10a5c-208">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="10a5c-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="10a5c-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="10a5c-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="10a5c-210">600</span><span class="sxs-lookup"><span data-stu-id="10a5c-210">600</span></span>  <br/> |<span data-ttu-id="10a5c-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="10a5c-211">CNAME</span></span>  <br/> |<span data-ttu-id="10a5c-212">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="10a5c-212">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="10a5c-213">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="10a5c-213">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="10a5c-215">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-215">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="10a5c-217">Fügen Sie die fünf restlichen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="10a5c-217">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="10a5c-218">Erstellen Sie im Abschnitt **DNS-Eintrag hinzufügen** einen Datensatz mithilfe der Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Datensatz erstellen** aus, um den Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="10a5c-218">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="10a5c-219">Wiederholen Sie diesen Vorgang, bis Sie alle sechs CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="10a5c-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="10a5c-220">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="10a5c-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="10a5c-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="10a5c-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="10a5c-222">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="10a5c-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="10a5c-223">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="10a5c-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="10a5c-224">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="10a5c-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="10a5c-225">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="10a5c-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="10a5c-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="10a5c-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="10a5c-229">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="10a5c-229">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="10a5c-230">Wählen Sie auf der Seite **DNS** für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-230">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="10a5c-231">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-231">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="10a5c-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="10a5c-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="10a5c-233">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="10a5c-233">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="10a5c-234">**Host**</span><span class="sxs-lookup"><span data-stu-id="10a5c-234">**Host**</span></span>|<span data-ttu-id="10a5c-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10a5c-235">**TTL**</span></span>|<span data-ttu-id="10a5c-236">**Type**</span><span class="sxs-lookup"><span data-stu-id="10a5c-236">**Type**</span></span>|<span data-ttu-id="10a5c-237">**Data**</span><span class="sxs-lookup"><span data-stu-id="10a5c-237">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10a5c-238">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="10a5c-238">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="10a5c-239">600</span><span class="sxs-lookup"><span data-stu-id="10a5c-239">600</span></span>  <br/> |<span data-ttu-id="10a5c-240">TXT</span><span class="sxs-lookup"><span data-stu-id="10a5c-240">TXT</span></span>  <br/> |<span data-ttu-id="10a5c-241">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="10a5c-241">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="10a5c-242">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="10a5c-242">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="10a5c-244">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-244">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="10a5c-246">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="10a5c-246">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="10a5c-247"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="10a5c-247"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="10a5c-248">Um zu beginnen, navigieren Sie über [diesen Link](https://account.dyn.com/dns/) zu Ihrer Domänenseite bei Dyn.com.</span><span class="sxs-lookup"><span data-stu-id="10a5c-248">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="10a5c-249">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="10a5c-249">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="10a5c-251">Wählen Sie auf der Seite **Dienste auf Zonenebene** **dyn Standard-DNS-Dienst** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="10a5c-251">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="10a5c-252">Wählen Sie auf der Seite **DNS** für Ihre Domäne die Option **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-252">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="10a5c-253">Wählen Sie **Expert-Schnittstelle aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-253">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="10a5c-254">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="10a5c-254">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="10a5c-255">Geben Sie im Bereich **Add DNS Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="10a5c-255">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="10a5c-256">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="10a5c-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="10a5c-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="10a5c-257">**Host**</span></span>|<span data-ttu-id="10a5c-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10a5c-258">**TTL**</span></span>|<span data-ttu-id="10a5c-259">**Type**</span><span class="sxs-lookup"><span data-stu-id="10a5c-259">**Type**</span></span>|<span data-ttu-id="10a5c-260">**Data**</span><span class="sxs-lookup"><span data-stu-id="10a5c-260">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10a5c-261">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="10a5c-261">_sip._tls</span></span>|<span data-ttu-id="10a5c-262">600</span><span class="sxs-lookup"><span data-stu-id="10a5c-262">600</span></span>|<span data-ttu-id="10a5c-263">SRV</span><span class="sxs-lookup"><span data-stu-id="10a5c-263">SRV</span></span>|<span data-ttu-id="10a5c-264">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="10a5c-264">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="10a5c-265">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="10a5c-265">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="10a5c-266">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="10a5c-266">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="10a5c-267">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="10a5c-267">_sipfederationtls._tcp</span></span>|<span data-ttu-id="10a5c-268">600</span><span class="sxs-lookup"><span data-stu-id="10a5c-268">600</span></span>|<span data-ttu-id="10a5c-269">SRV</span><span class="sxs-lookup"><span data-stu-id="10a5c-269">SRV</span></span>|<span data-ttu-id="10a5c-270">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="10a5c-270">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="10a5c-271">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="10a5c-271">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="10a5c-272">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="10a5c-272">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="10a5c-274">Wählen Sie **Create Record**aus.</span><span class="sxs-lookup"><span data-stu-id="10a5c-274">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="10a5c-276">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="10a5c-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="10a5c-277">Erstellen Sie im Abschnitt **DNS-Eintrag hinzufügen** einen Datensatz mithilfe der Werte aus der zweiten Zeile in der Tabelle, und wählen Sie dann erneut **Datensatz erstellen** aus, um den Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="10a5c-277">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="10a5c-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="10a5c-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
