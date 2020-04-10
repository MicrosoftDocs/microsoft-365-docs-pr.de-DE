---
title: Erstellen von DNS-Einträgen bei Names.co.uk für Office 365
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
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Names.co.uk für Office 365 einrichten.
ms.openlocfilehash: 8f8d76c1aebaa7fec80b264e0a9d2c8fffec9f41
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211667"
---
# <a name="create-dns-records-at-namescouk-for-office-365"></a><span data-ttu-id="ac742-103">Erstellen von DNS-Einträgen bei Names.co.uk für Office 365</span><span class="sxs-lookup"><span data-stu-id="ac742-103">Create DNS records at Names.co.uk for Office 365</span></span>

 <span data-ttu-id="ac742-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="ac742-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ac742-105">Wenn Names.co.uk Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ac742-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="ac742-106">Nachdem Sie diese Einträge bei Names.co.uk hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="ac742-106">After you add these records at Names.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="ac742-107">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="ac742-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="ac742-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ac742-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ac742-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="ac742-111">Add a TXT record for verification</span></span>
<span data-ttu-id="ac742-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ac742-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ac742-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="ac742-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac742-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="ac742-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ac742-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ac742-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ac742-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="ac742-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ac742-121">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ac742-121">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ac742-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ac742-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ac742-124">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ac742-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="ac742-125">(Wenn Sie eine Zeile hinzufügen möchten, wählen Sie **Add a/CNAME Records (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="ac742-125">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="ac742-126">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ac742-126">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="ac742-127">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="ac742-127">**Host name**</span></span>|<span data-ttu-id="ac742-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="ac742-128">**Type**</span></span>|<span data-ttu-id="ac742-129">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="ac742-129">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ac742-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="ac742-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ac742-131">TXT</span><span class="sxs-lookup"><span data-stu-id="ac742-131">TXT</span></span>  <br/> |<span data-ttu-id="ac742-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ac742-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ac742-p105">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="ac742-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="ac742-137">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ac742-137">Select **Save**.</span></span>
    
    <span data-ttu-id="ac742-138">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ac742-138">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="ac742-140">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac742-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ac742-141">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ac742-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="ac742-142">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="ac742-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ac742-143">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="ac742-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ac742-144">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ac742-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ac742-145">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="ac742-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ac742-146">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="ac742-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ac742-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ac742-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="ac742-150">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="ac742-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="ac742-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ac742-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="ac742-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ac742-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ac742-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="ac742-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ac742-156">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ac742-156">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ac742-158">Geben Sie auf der Seite **Add/Modify DNS Zone** im Abschnitt **Mail exchange records** in den Feldern für den neuen Eintrag die Werte aus der nachstehenden Tabelle manuell ein, oder kopieren Sie die Werte, und fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="ac742-158">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ac742-159">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ac742-159">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ac742-160">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="ac742-160">**Host name**</span></span>|<span data-ttu-id="ac742-161">**Priority**</span><span class="sxs-lookup"><span data-stu-id="ac742-161">**Priority**</span></span>|<span data-ttu-id="ac742-162">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="ac742-162">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ac742-163">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="ac742-163">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ac742-164">1</span><span class="sxs-lookup"><span data-stu-id="ac742-164">1</span></span>  <br/> <span data-ttu-id="ac742-165">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="ac742-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="ac742-166">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ac742-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="ac742-167">> [!NOTE]> Ihren \* \<Domänenschlüssel\> \* von Ihrem Office 365 Konto abrufen.</span><span class="sxs-lookup"><span data-stu-id="ac742-167">> [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="ac742-168">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="ac742-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="ac742-170">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ac742-170">Select **Save**.</span></span>
    
    <span data-ttu-id="ac742-171">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ac742-171">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="ac742-173">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="ac742-173">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="ac742-175">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ac742-175">Select **Save**.</span></span>
    
    <span data-ttu-id="ac742-176">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ac742-176">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="ac742-178">Hinzufügen der für Office 365 erforderlichen sechs CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="ac742-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="ac742-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ac742-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="ac742-p109">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ac742-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ac742-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="ac742-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ac742-184">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ac742-184">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ac742-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ac742-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ac742-187">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ac742-187">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="ac742-188">(Wenn Sie eine Zeile hinzufügen möchten, wählen Sie **Add a/CNAME Records (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="ac742-188">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="ac742-189">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ac742-189">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ac742-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="ac742-190">**Host Name**</span></span>|<span data-ttu-id="ac742-191">**Type**</span><span class="sxs-lookup"><span data-stu-id="ac742-191">**Type**</span></span>|<span data-ttu-id="ac742-192">**Result**</span><span class="sxs-lookup"><span data-stu-id="ac742-192">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ac742-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ac742-193">autodiscover</span></span>  <br/> |<span data-ttu-id="ac742-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="ac742-194">CNAME</span></span>  <br/> |<span data-ttu-id="ac742-195">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ac742-195">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="ac742-196">sip</span><span class="sxs-lookup"><span data-stu-id="ac742-196">sip</span></span>  <br/> |<span data-ttu-id="ac742-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="ac742-197">CNAME</span></span>  <br/> |<span data-ttu-id="ac742-198">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ac742-198">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ac742-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ac742-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ac742-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="ac742-200">CNAME</span></span>  <br/> |<span data-ttu-id="ac742-201">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ac742-201">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ac742-202">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ac742-202">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ac742-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="ac742-203">CNAME</span></span>  <br/> |<span data-ttu-id="ac742-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ac742-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="ac742-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ac742-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ac742-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="ac742-206">CNAME</span></span>  <br/> |<span data-ttu-id="ac742-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ac742-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="ac742-209">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ac742-209">Select **Save**.</span></span>
    
    ![NamesUK-BP-configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ac742-211">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="ac742-211">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ac742-212"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ac742-212"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac742-213">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="ac742-213">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ac742-214">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="ac742-214">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ac742-215">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac742-215">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="ac742-216">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ac742-216">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="ac742-p111">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ac742-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ac742-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="ac742-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ac742-221">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ac742-221">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ac742-223">Wählen Sie auf der Seite **DNS-Zonen auf dem Konto** in der Spalte **Domänenname** den Namen der Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ac742-223">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="ac742-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ac742-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ac742-226">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ac742-226">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="ac742-227">(Wenn Sie eine Zeile hinzufügen möchten, wählen Sie **Add a/CNAME Records (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="ac742-227">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="ac742-228">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ac742-228">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ac742-229">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="ac742-229">**Host name**</span></span>|<span data-ttu-id="ac742-230">**Type**</span><span class="sxs-lookup"><span data-stu-id="ac742-230">**Type**</span></span>|<span data-ttu-id="ac742-231">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="ac742-231">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ac742-232">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="ac742-232">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ac742-233">TXT</span><span class="sxs-lookup"><span data-stu-id="ac742-233">TXT</span></span>  <br/> |<span data-ttu-id="ac742-234">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ac742-234">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ac742-235">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="ac742-235">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="ac742-237">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ac742-237">Select **Save**.</span></span>
    
    <span data-ttu-id="ac742-238">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ac742-238">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="ac742-240">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="ac742-240">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="ac742-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ac742-241"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="ac742-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://account.names.co.uk/dashboard#/) zu Ihrer Domänenseite bei Names.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ac742-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ac742-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="ac742-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ac742-246">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ac742-246">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ac742-248">Geben Sie auf der Seite **Add/Modify DNS Zone** im Abschnitt **Service records** in den Feldern für den neuen Eintrag die Werte aus der nachstehenden Tabelle manuell ein, oder kopieren Sie die Werte, und fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="ac742-248">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ac742-249">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ac742-249">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ac742-250">**Name**</span><span class="sxs-lookup"><span data-stu-id="ac742-250">**Name**</span></span>|<span data-ttu-id="ac742-251">**Priority**</span><span class="sxs-lookup"><span data-stu-id="ac742-251">**Priority**</span></span>|<span data-ttu-id="ac742-252">**Weight**</span><span class="sxs-lookup"><span data-stu-id="ac742-252">**Weight**</span></span>|<span data-ttu-id="ac742-253">**Port**</span><span class="sxs-lookup"><span data-stu-id="ac742-253">**Port**</span></span>|<span data-ttu-id="ac742-254">**Result**</span><span class="sxs-lookup"><span data-stu-id="ac742-254">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ac742-255">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="ac742-255">_sip._tls</span></span>  <br/> |<span data-ttu-id="ac742-256">100</span><span class="sxs-lookup"><span data-stu-id="ac742-256">100</span></span>  <br/> |<span data-ttu-id="ac742-257">1</span><span class="sxs-lookup"><span data-stu-id="ac742-257">1</span></span>  <br/> |<span data-ttu-id="ac742-258">443</span><span class="sxs-lookup"><span data-stu-id="ac742-258">443</span></span>  <br/> |<span data-ttu-id="ac742-259">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ac742-259">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ac742-260">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="ac742-260">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="ac742-261">100</span><span class="sxs-lookup"><span data-stu-id="ac742-261">100</span></span>  <br/> |<span data-ttu-id="ac742-262">1</span><span class="sxs-lookup"><span data-stu-id="ac742-262">1</span></span>  <br/> |<span data-ttu-id="ac742-263">5061</span><span class="sxs-lookup"><span data-stu-id="ac742-263">5061</span></span>  <br/> |<span data-ttu-id="ac742-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ac742-264">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="ac742-266">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ac742-266">Select **Save**.</span></span>
    
    <span data-ttu-id="ac742-267">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ac742-267">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="ac742-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ac742-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
