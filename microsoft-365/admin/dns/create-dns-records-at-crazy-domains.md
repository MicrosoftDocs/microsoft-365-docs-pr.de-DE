---
title: Erstellen von DNS-Einträgen für Office 365 bei Crazy Domains
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste in Crazy Domains für Office 365 einrichten.
ms.openlocfilehash: 74c9a940f8d6f52c31712357557ea8cfda76e6bb
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211823"
---
# <a name="create-dns-records-at-crazy-domains-for-office-365"></a><span data-ttu-id="98d30-103">Erstellen von DNS-Einträgen für Office 365 bei Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="98d30-103">Create DNS records at Crazy Domains for Office 365</span></span>

 <span data-ttu-id="98d30-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="98d30-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="98d30-105">Wenn Crazy Domains Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="98d30-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="98d30-106">Nachdem Sie diese Einträge bei Crazy Domains hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="98d30-106">After you add these records at Crazy Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="98d30-107">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="98d30-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="98d30-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="98d30-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="98d30-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="98d30-111">Add a TXT record for verification</span></span>
<span data-ttu-id="98d30-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="98d30-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="98d30-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="98d30-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="98d30-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="98d30-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="98d30-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://manage.crazydomains.com/members/domains/) zu Ihrer Domänenseite bei Crazy Domains. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="98d30-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="98d30-120">Wählen Sie im Abschnitt **mein Konto** die Option **Domänen**aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-120">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="98d30-122">Wählen Sie auf der Seite **Domänennamen** im Abschnitt **Domäne** den Namen der Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="98d30-122">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="98d30-124">Wählen Sie im Abschnitt **DNS-Einstellungen** das Dropdownlisten-Symbol aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-124">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="98d30-126">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-126">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="98d30-128">Wählen Sie in der Dropdownliste **Add Record** den Eintrag **TXT Record** aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-128">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Verify-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="98d30-130">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="98d30-130">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="98d30-132">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="98d30-132">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="98d30-133">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="98d30-133">**Sub Domain**</span></span>|<span data-ttu-id="98d30-134">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="98d30-134">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="98d30-135">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="98d30-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="98d30-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="98d30-136">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="98d30-p105">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="98d30-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![CrazyDomains-BP-Verify-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="98d30-141">Wählen Sie **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-141">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="98d30-143">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="98d30-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="98d30-144">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="98d30-144">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="98d30-145">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="98d30-145">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="98d30-146">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="98d30-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="98d30-147">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="98d30-148">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="98d30-149">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="98d30-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="98d30-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="98d30-153">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="98d30-153">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="98d30-154"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="98d30-154"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="98d30-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://manage.crazydomains.com/members/domains/) zu Ihrer Domänenseite bei Crazy Domains. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="98d30-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="98d30-158">Wählen Sie im Abschnitt **mein Konto** die Option **Domänen**aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-158">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="98d30-160">Wählen Sie auf der Seite **Domänennamen** im Abschnitt **Domäne** den Namen der Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="98d30-160">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="98d30-162">Wählen Sie im Abschnitt **DNS-Einstellungen** das Dropdownlisten-Symbol aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-162">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="98d30-164">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-164">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="98d30-166">Wählen Sie in der Dropdownliste **Add Record:** den Eintrag **MX Record** aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-166">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="98d30-168">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="98d30-168">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="98d30-170">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="98d30-170">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="98d30-171">(Wählen Sie in der Dropdownliste den Wert **Priority** aus.)</span><span class="sxs-lookup"><span data-stu-id="98d30-171">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="98d30-172">**Mail For Zone**</span><span class="sxs-lookup"><span data-stu-id="98d30-172">**Mail For Zone**</span></span>|<span data-ttu-id="98d30-173">**Priority**</span><span class="sxs-lookup"><span data-stu-id="98d30-173">**Priority**</span></span>|<span data-ttu-id="98d30-174">**Assigned To Server**</span><span class="sxs-lookup"><span data-stu-id="98d30-174">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="98d30-175">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="98d30-175">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="98d30-176">1</span><span class="sxs-lookup"><span data-stu-id="98d30-176">1</span></span>  <br/> <span data-ttu-id="98d30-177">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="98d30-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="98d30-178">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="98d30-178">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="98d30-179">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="98d30-179">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="98d30-180">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="98d30-180">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-configure-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="98d30-182">Wählen Sie **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-182">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-configure-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="98d30-184">Wenn im Abschnitt **MX Record** andere MX-Einträge aufgeführt sind, wählen Sie für einen dieser Einträge die Option **Modify** aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-184">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-BP-configure-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="98d30-186">Wählen Sie **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-186">Select **Delete**.</span></span>
    
    ![CrazyDomains-BP-configure-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="98d30-188">Wählen Sie **Aktualisieren** aus, um den Löschvorgang zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="98d30-188">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-BP-configure-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="98d30-190">Wiederholen Sie diesen Vorgang, um alle anderen MX-Einträge aus der Liste zu entfernen, bis nur noch der Eintrag übrig ist, den Sie zuvor in diesem Verfahren hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="98d30-190">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="98d30-191">Hinzufügen der für Office 365 erforderlichen sechs CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="98d30-191">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="98d30-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="98d30-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="98d30-p109">Um zu beginnen, navigieren Sie über [diesen Link](https://manage.crazydomains.com/members/domains/) zu Ihrer Domänenseite bei Crazy Domains. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="98d30-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="98d30-196">Wählen Sie im Abschnitt **mein Konto** die Option **Domänen**aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-196">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="98d30-198">Wählen Sie auf der Seite **Domänennamen** im Abschnitt **Domäne** den Namen der Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="98d30-198">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="98d30-200">Wählen Sie im Abschnitt **DNS-Einstellungen** das Dropdownlisten-Symbol aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-200">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="98d30-202">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-202">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="98d30-204">Wählen Sie in der Dropdownliste **Add Record** den Eintrag **CNAME Record** aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="98d30-206">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="98d30-206">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="98d30-208">Fügen Sie den ersten der sechs CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="98d30-208">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="98d30-209">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="98d30-209">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="98d30-210">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="98d30-210">**Sub Domain**</span></span>|<span data-ttu-id="98d30-211">**Alias for**</span><span class="sxs-lookup"><span data-stu-id="98d30-211">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="98d30-212">autodiscover</span><span class="sxs-lookup"><span data-stu-id="98d30-212">autodiscover</span></span>  <br/> |<span data-ttu-id="98d30-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="98d30-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="98d30-214">sip</span><span class="sxs-lookup"><span data-stu-id="98d30-214">sip</span></span>  <br/> |<span data-ttu-id="98d30-215">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="98d30-215">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="98d30-216">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="98d30-216">lyncdiscover</span></span>  <br/> |<span data-ttu-id="98d30-217">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="98d30-217">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="98d30-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="98d30-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="98d30-219">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="98d30-219">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="98d30-220">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="98d30-220">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="98d30-221">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="98d30-221">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-configure-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="98d30-223">Wählen Sie **CNAME-Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-223">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-BP-configure-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="98d30-225">Fügen Sie den zweiten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="98d30-225">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="98d30-226">Verwenden Sie in den Feldern für den neuen Datensatz die Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **CNAME-Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-226">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="98d30-227">Wiederholen Sie diesen Vorgang, bis Sie alle sechs CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="98d30-227">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="98d30-228">Wählen Sie **Aktualisieren** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="98d30-228">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-configure-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="98d30-230">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="98d30-230">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="98d30-231"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="98d30-231"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="98d30-232">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="98d30-232">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="98d30-233">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="98d30-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="98d30-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="98d30-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="98d30-235">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="98d30-235">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="98d30-p111">Um zu beginnen, navigieren Sie über [diesen Link](https://manage.crazydomains.com/members/domains/) zu Ihrer Domänenseite bei Crazy Domains. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="98d30-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="98d30-239">Wählen Sie im Abschnitt **mein Konto** die Option **Domänen**aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-239">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="98d30-241">Wählen Sie auf der Seite **Domänennamen** im Abschnitt **Domäne** den Namen der Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="98d30-241">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="98d30-243">Wählen Sie im Abschnitt **DNS-Einstellungen** das Dropdownlisten-Symbol aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-243">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="98d30-245">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-245">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="98d30-247">Wählen Sie in der Dropdownliste **Add Record:** den Eintrag **TXT Record** aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-247">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="98d30-249">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="98d30-249">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="98d30-251">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="98d30-251">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="98d30-252">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="98d30-252">**Sub Domain**</span></span>|<span data-ttu-id="98d30-253">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="98d30-253">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="98d30-254">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="98d30-254">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="98d30-255">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="98d30-255">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="98d30-256">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="98d30-256">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-BP-configure-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="98d30-258">Wählen Sie **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-258">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-configure-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="98d30-260">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="98d30-260">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="98d30-261"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="98d30-261"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="98d30-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://manage.crazydomains.com/members/domains/) zu Ihrer Domänenseite bei Crazy Domains. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="98d30-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="98d30-265">Wählen Sie im Abschnitt **mein Konto** die Option **Domänen**aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-265">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="98d30-267">Wählen Sie auf der Seite **Domänennamen** im Abschnitt **Domäne** den Namen der Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="98d30-267">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="98d30-269">Wählen Sie im Abschnitt **DNS-Einstellungen** das Dropdownlisten-Symbol aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-269">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="98d30-271">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-271">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="98d30-273">Wählen Sie in der Dropdownliste **Add Record:** den Eintrag **SRV Record** aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-273">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="98d30-275">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="98d30-275">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="98d30-277">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="98d30-277">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="98d30-278">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="98d30-278">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="98d30-279">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="98d30-279">**Record Type**</span></span>|<span data-ttu-id="98d30-280">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="98d30-280">**Sub Domain**</span></span>|<span data-ttu-id="98d30-281">**Priority**</span><span class="sxs-lookup"><span data-stu-id="98d30-281">**Priority**</span></span>|<span data-ttu-id="98d30-282">**Weight**</span><span class="sxs-lookup"><span data-stu-id="98d30-282">**Weight**</span></span>|<span data-ttu-id="98d30-283">**Port**</span><span class="sxs-lookup"><span data-stu-id="98d30-283">**Port**</span></span>|<span data-ttu-id="98d30-284">**Target**</span><span class="sxs-lookup"><span data-stu-id="98d30-284">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="98d30-285">SRV-Eintrag</span><span class="sxs-lookup"><span data-stu-id="98d30-285">SRV Record</span></span>  <br/> |<span data-ttu-id="98d30-286">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="98d30-286">_sip._tls</span></span>  <br/> |<span data-ttu-id="98d30-287">100</span><span class="sxs-lookup"><span data-stu-id="98d30-287">100</span></span>  <br/> |<span data-ttu-id="98d30-288">1</span><span class="sxs-lookup"><span data-stu-id="98d30-288">1</span></span>  <br/> |<span data-ttu-id="98d30-289">443</span><span class="sxs-lookup"><span data-stu-id="98d30-289">443</span></span>  <br/> |<span data-ttu-id="98d30-290">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="98d30-290">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="98d30-291">SRV Record</span><span class="sxs-lookup"><span data-stu-id="98d30-291">SRV Record</span></span>  <br/> |<span data-ttu-id="98d30-292">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="98d30-292">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="98d30-293">100</span><span class="sxs-lookup"><span data-stu-id="98d30-293">100</span></span>  <br/> |<span data-ttu-id="98d30-294">1</span><span class="sxs-lookup"><span data-stu-id="98d30-294">1</span></span>  <br/> |<span data-ttu-id="98d30-295">5061</span><span class="sxs-lookup"><span data-stu-id="98d30-295">5061</span></span>  <br/> |<span data-ttu-id="98d30-296">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="98d30-296">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-configure-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="98d30-298">Wählen Sie **SRV-Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="98d30-298">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-BP-configure-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="98d30-300">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="98d30-300">Add the other SRV record.</span></span>
    
    <span data-ttu-id="98d30-301">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der zweiten Zeile der Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="98d30-301">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="98d30-302">Wählen Sie **Aktualisieren** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="98d30-302">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-configure-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="98d30-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="98d30-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
