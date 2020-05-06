---
title: Erstellen von DNS-Einträgen bei Names.co.uk für Microsoft
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Names.co.uk für Microsoft einrichten.
ms.openlocfilehash: 2df1a18f00fd7cd48b0d24860ddcf651c2fdac4e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048939"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="f9e0e-103">Erstellen von DNS-Einträgen bei Names.co.uk für Microsoft</span><span class="sxs-lookup"><span data-stu-id="f9e0e-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="f9e0e-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f9e0e-105">Wenn Names.co.uk Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="f9e0e-106">Nachdem Sie diese Einträge bei Names.co.uk hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="f9e0e-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f9e0e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f9e0e-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="f9e0e-110">Add a TXT record for verification</span></span>
<span data-ttu-id="f9e0e-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f9e0e-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f9e0e-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f9e0e-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f9e0e-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="f9e0e-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="f9e0e-120">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-120">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="f9e0e-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f9e0e-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="f9e0e-124">(Wenn Sie eine Zeile hinzufügen möchten, wählen Sie **Add a/CNAME Records (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="f9e0e-125">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="f9e0e-126">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-126">**Host name**</span></span>|<span data-ttu-id="f9e0e-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-127">**Type**</span></span>|<span data-ttu-id="f9e0e-128">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f9e0e-129">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="f9e0e-130">TXT</span><span class="sxs-lookup"><span data-stu-id="f9e0e-130">TXT</span></span>  <br/> |<span data-ttu-id="f9e0e-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f9e0e-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f9e0e-132">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-132">**Note:** This is an example.</span></span> <span data-ttu-id="f9e0e-133">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="f9e0e-134">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="f9e0e-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="f9e0e-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-136">Select **Save**.</span></span>
    
    <span data-ttu-id="f9e0e-137">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-137">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="f9e0e-139">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f9e0e-140">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="f9e0e-141">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f9e0e-142">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="f9e0e-143">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f9e0e-144">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="f9e0e-145">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f9e0e-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f9e0e-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="f9e0e-149">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="f9e0e-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f9e0e-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="f9e0e-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="f9e0e-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="f9e0e-155">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-155">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="f9e0e-157">Geben Sie auf der Seite **Add/Modify DNS Zone** im Abschnitt **Mail exchange records** in den Feldern für den neuen Eintrag die Werte aus der nachstehenden Tabelle manuell ein, oder kopieren Sie die Werte, und fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f9e0e-158">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="f9e0e-159">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-159">**Host name**</span></span>|<span data-ttu-id="f9e0e-160">**Priority**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-160">**Priority**</span></span>|<span data-ttu-id="f9e0e-161">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f9e0e-162">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="f9e0e-163">1</span><span class="sxs-lookup"><span data-stu-id="f9e0e-163">1</span></span>  <br/> <span data-ttu-id="f9e0e-164">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="f9e0e-165">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f9e0e-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="f9e0e-166">> [!NOTE]> Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto abrufen.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="f9e0e-167">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="f9e0e-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="f9e0e-169">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-169">Select **Save**.</span></span>
    
    <span data-ttu-id="f9e0e-170">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-170">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="f9e0e-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="f9e0e-174">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-174">Select **Save**.</span></span>
    
    <span data-ttu-id="f9e0e-175">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-175">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="f9e0e-177">Hinzufügen der sechs CNAME-Einträge, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="f9e0e-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="f9e0e-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f9e0e-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="f9e0e-p109">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="f9e0e-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="f9e0e-183">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-183">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="f9e0e-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f9e0e-186">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="f9e0e-187">(Wenn Sie eine Zeile hinzufügen möchten, wählen Sie **Add a/CNAME Records (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="f9e0e-188">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="f9e0e-189">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-189">**Host Name**</span></span>|<span data-ttu-id="f9e0e-190">**Type**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-190">**Type**</span></span>|<span data-ttu-id="f9e0e-191">**Result**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f9e0e-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f9e0e-192">autodiscover</span></span>  <br/> |<span data-ttu-id="f9e0e-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="f9e0e-193">CNAME</span></span>  <br/> |<span data-ttu-id="f9e0e-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f9e0e-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="f9e0e-195">sip</span><span class="sxs-lookup"><span data-stu-id="f9e0e-195">sip</span></span>  <br/> |<span data-ttu-id="f9e0e-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="f9e0e-196">CNAME</span></span>  <br/> |<span data-ttu-id="f9e0e-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f9e0e-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f9e0e-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f9e0e-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f9e0e-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="f9e0e-199">CNAME</span></span>  <br/> |<span data-ttu-id="f9e0e-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f9e0e-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f9e0e-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f9e0e-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f9e0e-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="f9e0e-202">CNAME</span></span>  <br/> |<span data-ttu-id="f9e0e-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f9e0e-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="f9e0e-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f9e0e-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f9e0e-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="f9e0e-205">CNAME</span></span>  <br/> |<span data-ttu-id="f9e0e-206">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f9e0e-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="f9e0e-208">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-208">Select **Save**.</span></span>
    
    ![NamesUK-BP-configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f9e0e-210">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="f9e0e-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f9e0e-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f9e0e-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9e0e-212">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f9e0e-213">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f9e0e-214">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="f9e0e-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="f9e0e-215">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="f9e0e-p111">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="f9e0e-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="f9e0e-220">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-220">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="f9e0e-222">Wählen Sie auf der Seite **DNS-Zonen auf dem Konto** in der Spalte **Domänenname** den Namen der Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="f9e0e-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f9e0e-225">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="f9e0e-226">(Wenn Sie eine Zeile hinzufügen möchten, wählen Sie **Add a/CNAME Records (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="f9e0e-227">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="f9e0e-228">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-228">**Host name**</span></span>|<span data-ttu-id="f9e0e-229">**Type**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-229">**Type**</span></span>|<span data-ttu-id="f9e0e-230">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f9e0e-231">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="f9e0e-232">TXT</span><span class="sxs-lookup"><span data-stu-id="f9e0e-232">TXT</span></span>  <br/> |<span data-ttu-id="f9e0e-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f9e0e-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="f9e0e-234">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="f9e0e-236">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-236">Select **Save**.</span></span>
    
    <span data-ttu-id="f9e0e-237">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-237">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="f9e0e-239">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="f9e0e-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="f9e0e-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f9e0e-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="f9e0e-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="f9e0e-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="f9e0e-245">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-245">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="f9e0e-247">Geben Sie auf der Seite **Add/Modify DNS Zone** im Abschnitt **Service records** in den Feldern für den neuen Eintrag die Werte aus der nachstehenden Tabelle manuell ein, oder kopieren Sie die Werte, und fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f9e0e-248">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="f9e0e-249">**Name**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-249">**Name**</span></span>|<span data-ttu-id="f9e0e-250">**Priority**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-250">**Priority**</span></span>|<span data-ttu-id="f9e0e-251">**Weight**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-251">**Weight**</span></span>|<span data-ttu-id="f9e0e-252">**Port**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-252">**Port**</span></span>|<span data-ttu-id="f9e0e-253">**Result**</span><span class="sxs-lookup"><span data-stu-id="f9e0e-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f9e0e-254">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="f9e0e-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="f9e0e-255">100</span><span class="sxs-lookup"><span data-stu-id="f9e0e-255">100</span></span>  <br/> |<span data-ttu-id="f9e0e-256">1</span><span class="sxs-lookup"><span data-stu-id="f9e0e-256">1</span></span>  <br/> |<span data-ttu-id="f9e0e-257">443</span><span class="sxs-lookup"><span data-stu-id="f9e0e-257">443</span></span>  <br/> |<span data-ttu-id="f9e0e-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f9e0e-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f9e0e-259">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="f9e0e-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="f9e0e-260">100</span><span class="sxs-lookup"><span data-stu-id="f9e0e-260">100</span></span>  <br/> |<span data-ttu-id="f9e0e-261">1</span><span class="sxs-lookup"><span data-stu-id="f9e0e-261">1</span></span>  <br/> |<span data-ttu-id="f9e0e-262">5061</span><span class="sxs-lookup"><span data-stu-id="f9e0e-262">5061</span></span>  <br/> |<span data-ttu-id="f9e0e-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f9e0e-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="f9e0e-265">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f9e0e-265">Select **Save**.</span></span>
    
    <span data-ttu-id="f9e0e-266">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="f9e0e-266">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="f9e0e-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f9e0e-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
