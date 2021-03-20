---
title: Erstellen von DNS-Einträgen Names.co.uk Microsoft
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mails, Skype for Business Online und andere Dienste bei Names.co.uk Microsoft einrichten.
ms.openlocfilehash: ddd7286d983a0f180c9aefdbf5218eb9765c8669
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910042"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="332c6-103">Erstellen von DNS-Einträgen Names.co.uk Microsoft</span><span class="sxs-lookup"><span data-stu-id="332c6-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="332c6-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="332c6-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="332c6-105">Wenn Names.co.uk Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="332c6-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="332c6-106">Nachdem Sie diese Datensätze unter Names.co.uk hinzugefügt haben, wird Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="332c6-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="332c6-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="332c6-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="332c6-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="332c6-110">Add a TXT record for verification</span></span>
<span data-ttu-id="332c6-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="332c6-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="332c6-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="332c6-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="332c6-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="332c6-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="332c6-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="332c6-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="332c6-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="332c6-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="332c6-120">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="332c6-120">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="332c6-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="332c6-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="332c6-123">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="332c6-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="332c6-124">(Wenn Sie eine Zeile hinzufügen müssen, wählen Sie **ADD A/CNAME RECORDS (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="332c6-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="332c6-125">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="332c6-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="332c6-126">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="332c6-126">**Host name**</span></span>|<span data-ttu-id="332c6-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="332c6-127">**Type**</span></span>|<span data-ttu-id="332c6-128">**Result**</span><span class="sxs-lookup"><span data-stu-id="332c6-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="332c6-129">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="332c6-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="332c6-130">TXT</span><span class="sxs-lookup"><span data-stu-id="332c6-130">TXT</span></span>  <br/> |<span data-ttu-id="332c6-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="332c6-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="332c6-132">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="332c6-132">**Note:** This is an example.</span></span> <span data-ttu-id="332c6-133">Verwenden Sie hier Ihren spezifischen „Ziel“- oder **Verweist auf die Adresse**-Wert aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="332c6-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="332c6-134">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="332c6-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="332c6-136">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="332c6-136">Select **Save**.</span></span>
    
    <span data-ttu-id="332c6-137">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="332c6-137">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="332c6-139">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="332c6-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="332c6-140">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="332c6-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="332c6-141">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="332c6-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="332c6-142">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="332c6-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="332c6-143">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="332c6-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="332c6-144">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="332c6-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="332c6-145">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="332c6-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="332c6-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="332c6-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="332c6-149">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="332c6-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="332c6-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="332c6-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="332c6-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="332c6-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="332c6-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="332c6-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="332c6-155">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="332c6-155">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="332c6-157">Geben Sie auf der Seite **Add/Modify DNS Zone** im Abschnitt **Mail exchange records** in den Feldern für den neuen Eintrag die Werte aus der nachstehenden Tabelle manuell ein, oder kopieren Sie die Werte, und fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="332c6-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="332c6-158">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="332c6-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="332c6-159">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="332c6-159">**Host name**</span></span>|<span data-ttu-id="332c6-160">**Priority**</span><span class="sxs-lookup"><span data-stu-id="332c6-160">**Priority**</span></span>|<span data-ttu-id="332c6-161">**Result**</span><span class="sxs-lookup"><span data-stu-id="332c6-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="332c6-162">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="332c6-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="332c6-163">1</span><span class="sxs-lookup"><span data-stu-id="332c6-163">1</span></span>  <br/> <span data-ttu-id="332c6-164">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="332c6-164">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="332c6-165">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="332c6-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="332c6-166">> [!NOTE]> Von Ihrem  *\<domain-key\>*  Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="332c6-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="332c6-167">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="332c6-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="332c6-169">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="332c6-169">Select **Save**.</span></span>
    
    <span data-ttu-id="332c6-170">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="332c6-170">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="332c6-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="332c6-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-Configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="332c6-174">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="332c6-174">Select **Save**.</span></span>
    
    <span data-ttu-id="332c6-175">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="332c6-175">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="332c6-177">Hinzufügen der für Microsoft erforderlichen sechs CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="332c6-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="332c6-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="332c6-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="332c6-p109">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="332c6-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="332c6-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="332c6-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="332c6-183">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="332c6-183">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="332c6-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="332c6-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="332c6-186">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="332c6-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="332c6-187">(Wenn Sie eine Zeile hinzufügen müssen, wählen Sie **ADD A/CNAME RECORDS (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="332c6-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="332c6-188">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="332c6-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="332c6-189">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="332c6-189">**Host Name**</span></span>|<span data-ttu-id="332c6-190">**Type**</span><span class="sxs-lookup"><span data-stu-id="332c6-190">**Type**</span></span>|<span data-ttu-id="332c6-191">**Result**</span><span class="sxs-lookup"><span data-stu-id="332c6-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="332c6-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="332c6-192">autodiscover</span></span>  <br/> |<span data-ttu-id="332c6-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="332c6-193">CNAME</span></span>  <br/> |<span data-ttu-id="332c6-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="332c6-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="332c6-195">sip</span><span class="sxs-lookup"><span data-stu-id="332c6-195">sip</span></span>  <br/> |<span data-ttu-id="332c6-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="332c6-196">CNAME</span></span>  <br/> |<span data-ttu-id="332c6-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="332c6-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="332c6-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="332c6-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="332c6-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="332c6-199">CNAME</span></span>  <br/> |<span data-ttu-id="332c6-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="332c6-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="332c6-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="332c6-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="332c6-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="332c6-202">CNAME</span></span>  <br/> |<span data-ttu-id="332c6-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="332c6-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="332c6-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="332c6-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="332c6-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="332c6-205">CNAME</span></span>  <br/> |<span data-ttu-id="332c6-206">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="332c6-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="332c6-208">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="332c6-208">Select **Save**.</span></span>
    
    ![NamesUK-BP-Configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="332c6-210">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="332c6-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="332c6-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="332c6-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="332c6-212">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="332c6-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="332c6-213">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="332c6-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="332c6-214">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="332c6-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="332c6-215">sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="332c6-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="332c6-p111">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="332c6-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="332c6-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="332c6-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="332c6-220">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="332c6-220">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="332c6-222">Wählen Sie auf der Seite **DNS-Zonen** im Konto in der Spalte **Domänenname** den Namen der Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="332c6-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-Configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="332c6-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="332c6-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="332c6-225">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="332c6-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="332c6-226">(Wenn Sie eine Zeile hinzufügen müssen, wählen Sie **ADD A/CNAME RECORDS (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="332c6-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="332c6-227">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="332c6-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="332c6-228">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="332c6-228">**Host name**</span></span>|<span data-ttu-id="332c6-229">**Type**</span><span class="sxs-lookup"><span data-stu-id="332c6-229">**Type**</span></span>|<span data-ttu-id="332c6-230">**Result**</span><span class="sxs-lookup"><span data-stu-id="332c6-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="332c6-231">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="332c6-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="332c6-232">TXT</span><span class="sxs-lookup"><span data-stu-id="332c6-232">TXT</span></span>  <br/> |<span data-ttu-id="332c6-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="332c6-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="332c6-234">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="332c6-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-Configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="332c6-236">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="332c6-236">Select **Save**.</span></span>
    
    <span data-ttu-id="332c6-237">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="332c6-237">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="332c6-239">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="332c6-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="332c6-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="332c6-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="332c6-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="332c6-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="332c6-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="332c6-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="332c6-245">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="332c6-245">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="332c6-247">Geben Sie auf der Seite **Add/Modify DNS Zone** im Abschnitt **Service records** in den Feldern für den neuen Eintrag die Werte aus der nachstehenden Tabelle manuell ein, oder kopieren Sie die Werte, und fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="332c6-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="332c6-248">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="332c6-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="332c6-249">**Name**</span><span class="sxs-lookup"><span data-stu-id="332c6-249">**Name**</span></span>|<span data-ttu-id="332c6-250">**Priority**</span><span class="sxs-lookup"><span data-stu-id="332c6-250">**Priority**</span></span>|<span data-ttu-id="332c6-251">**Weight**</span><span class="sxs-lookup"><span data-stu-id="332c6-251">**Weight**</span></span>|<span data-ttu-id="332c6-252">**Port**</span><span class="sxs-lookup"><span data-stu-id="332c6-252">**Port**</span></span>|<span data-ttu-id="332c6-253">**Result**</span><span class="sxs-lookup"><span data-stu-id="332c6-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="332c6-254">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="332c6-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="332c6-255">100</span><span class="sxs-lookup"><span data-stu-id="332c6-255">100</span></span>  <br/> |<span data-ttu-id="332c6-256">1</span><span class="sxs-lookup"><span data-stu-id="332c6-256">1</span></span>  <br/> |<span data-ttu-id="332c6-257">443</span><span class="sxs-lookup"><span data-stu-id="332c6-257">443</span></span>  <br/> |<span data-ttu-id="332c6-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="332c6-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="332c6-259">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="332c6-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="332c6-260">100</span><span class="sxs-lookup"><span data-stu-id="332c6-260">100</span></span>  <br/> |<span data-ttu-id="332c6-261">1</span><span class="sxs-lookup"><span data-stu-id="332c6-261">1</span></span>  <br/> |<span data-ttu-id="332c6-262">5061</span><span class="sxs-lookup"><span data-stu-id="332c6-262">5061</span></span>  <br/> |<span data-ttu-id="332c6-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="332c6-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="332c6-265">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="332c6-265">Select **Save**.</span></span>
    
    <span data-ttu-id="332c6-266">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="332c6-266">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="332c6-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="332c6-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
